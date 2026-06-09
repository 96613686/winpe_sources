# Smb2FindOrCreateDirCacheObject

- ea: `0x140004b30`
- end: `0x140004d24`
- name: `Smb2FindOrCreateDirCacheObject`
- size: `500`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140002b80`
- `0x140003570`
- `0x140004640`
- `0x140004940`
- `0x140005820`
- `0x140014db0`

## callees

- `0x140004b30`
- `0x1400126c0`
- `0x140015100`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140004c4c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140004c4c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140004bd9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140004bd9`
- `rdbss!RxNameCacheCheckEntry` at `0x140004c0e`
- `rdbss!RxNameCacheCheckEntry` at `0x140004c0e`
- `rdbss!RxNameCacheExpireEntry` at `0x140004c9c`
- `rdbss!RxNameCacheExpireEntry` at `0x140004cbf`
- `rdbss!RxNameCacheExpireEntry` at `0x140004c9c`
- `rdbss!RxNameCacheExpireEntry` at `0x140004cbf`
- `rdbss!RxNameCacheActivateEntry` at `0x1400384d7`
- `rdbss!RxNameCacheActivateEntry` at `0x1400384d7`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14003841e`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14003841e`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140004bf5`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140004bf5`
- `rdbss!RxCrackPathName` at `0x140004b90`
- `rdbss!RxCrackPathName` at `0x140004b90`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x1400384ae`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x1400384ae`
- `mrxsmb!MRxSmbDeviceObject` at `0x140038463`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140038473`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140038473`

## pseudocode

```c
__int64 __fastcall Smb2FindOrCreateDirCacheObject(
        _QWORD *a1,
        struct _NAME_CACHE_CONTROL_ *a2,
        __int64 a3,
        char a4,
        _DWORD *a5,
        char *a6)
{
  __int64 v6; // rax
  __int64 v9; // rbx
  __int64 v11; // rax
  __int64 v12; // rdi
  ULONG v13; // r12d
  __int64 v14; // r15
  __int64 v15; // r13
  __int64 v16; // rdx
  __int64 v17; // rax
  struct _NAME_CACHE *Entry; // rax
  __int64 v19; // r9
  __int64 v20; // rbx
  int v21; // eax
  int v22; // r14d
  __int128 v24; // xmm1
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // [rsp+20h] [rbp-58h] BYREF
  _OWORD v28[5]; // [rsp+28h] [rbp-50h] BYREF
  ULONG v29; // [rsp+80h] [rbp+8h] BYREF

  v6 = a1[9];
  v29 = 0;
  v9 = *(_QWORD *)(v6 + 40);
  v11 = a1[7];
  v12 = 0;
  v13 = 0;
  v14 = *(_QWORD *)(v9 + 40);
  v28[0] = 0;
  v15 = *(_QWORD *)(v11 + 136);
  v27 = 0;
  RxCrackPathName(a3, 0, v28, 0);
  v16 = *(_QWORD *)(v9 + 40);
  if ( (*(_DWORD *)(*(_QWORD *)(v16 + 424) + 184LL) & 0x800) != 0
    || (v17 = -1, (*(_BYTE *)(*(_QWORD *)(v16 + 24) + 1314LL) & 4) == 0) )
  {
    v17 = *(_QWORD *)(v14 + 96);
  }
  v27 = v17;
  ExAcquirePushLockExclusiveEx(&Smb2DirCacheLock, 0);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, v28, &v27, 0);
  v20 = (__int64)Entry;
  if ( Entry )
  {
    if ( RxNameCacheCheckEntry(Entry, 0) )
    {
      RxNameCacheExpireEntry(a2, (PNAME_CACHE)v20);
      v20 = 0;
    }
    else
    {
      v12 = *(_QWORD *)(v20 + 40);
      if ( v12 )
      {
        v21 = *(_DWORD *)(v12 + 44);
        if ( v21 )
        {
          if ( v21 != *(_DWORD *)(v14 + 264) )
          {
            RxNameCacheExpireEntry(a2, (PNAME_CACHE)v20);
            v20 = 0;
            v12 = 0;
          }
        }
      }
    }
  }
  if ( a4 )
  {
    a4 = 0;
    if ( !v20 )
    {
      if ( (*(_DWORD *)(v15 + 8) & 2) == 0 )
        goto LABEL_10;
      LOBYTE(v19) = 1;
      v25 = RxNameCacheCreateEntryEx(a2, v28, &v27, v19);
      v20 = v25;
      if ( !v25 )
        goto LABEL_10;
      *(_DWORD *)(v25 + 48) = 0;
      a4 = 1;
      v26 = a1[7];
      if ( (*(_DWORD *)(v26 + 164) & 1) != 0 && (*(_DWORD *)(v26 + 160) & 0x2000000) != 0 )
      {
        v13 = -1;
      }
      else if ( a1[10] == MRxSmbDeviceObject && *(_BYTE *)(MRxSmbGetConfigurationBlock(MRxSmbDeviceObject) + 231) )
      {
        Smb2GetInfoCacheTimeout(*(_QWORD *)(a1[9] + 40LL), &v29);
        v13 = v29;
      }
      else
      {
        v13 = *(_DWORD *)(MRxSmbGetInstanceConfigurationBlock(a1[10]) + 20);
      }
    }
  }
  else if ( !v20 )
  {
LABEL_10:
    v22 = 0;
    goto LABEL_11;
  }
  v12 = *(_QWORD *)(v20 + 40);
  v22 = *(_DWORD *)(v20 + 48);
  if ( !v12 )
  {
    if ( a4 )
      goto LABEL_34;
LABEL_33:
    v13 = 0;
    goto LABEL_34;
  }
  Smb2ReferenceDirCacheObject(*(_QWORD *)(v20 + 40));
  if ( !a4 )
    goto LABEL_33;
  *(_OWORD *)(v12 + 72) = *(_OWORD *)(v15 + 24);
  v24 = *(_OWORD *)(v15 + 40);
  *(_DWORD *)(v12 + 52) = 37;
  *(_OWORD *)(v12 + 88) = v24;
LABEL_34:
  RxNameCacheActivateEntry(a2, (PNAME_CACHE)v20, v13, 0);
LABEL_11:
  ExReleasePushLockExclusiveEx(&Smb2DirCacheLock, 0);
  if ( a6 )
    *a6 = a4;
  if ( a5 )
    *a5 = v22;
  return v12;
}

```

## disassembly

```asm
0x140004b30  mov     [rsp+arg_8], rbx
0x140004b35  push    rbp
0x140004b36  push    rsi
0x140004b37  push    rdi
0x140004b38  push    r12
0x140004b3a  push    r13
0x140004b3c  push    r14
0x140004b3e  push    r15
0x140004b40  sub     rsp, 40h
0x140004b44  mov     rax, [rcx+48h]
0x140004b48  mov     r14, rcx
0x140004b4b  xor     ecx, ecx
0x140004b4d  mov     r10, r8
0x140004b50  xorps   xmm0, xmm0
0x140004b53  mov     [rsp+78h+arg_0], ecx
0x140004b5a  movzx   esi, r9b
0x140004b5e  lea     r8, [rsp+78h+var_50]
0x140004b63  mov     rbx, [rax+28h]
0x140004b67  mov     rbp, rdx
0x140004b6a  mov     rax, [r14+38h]
0x140004b6e  mov     edi, ecx
0x140004b70  mov     r12d, ecx
0x140004b73  xor     r9d, r9d
0x140004b76  xor     edx, edx
0x140004b78  mov     r15, [rbx+28h]
0x140004b7c  movups  [rsp+78h+var_50], xmm0
0x140004b81  mov     r13, [rax+88h]
0x140004b88  mov     [rsp+78h+var_58], rcx
0x140004b8d  mov     rcx, r10
0x140004b90  call    cs:__imp_RxCrackPathName
0x140004b97  nop     dword ptr [rax+rax+00h]
0x140004b9c  mov     rdx, [rbx+28h]
0x140004ba0  mov     rax, [rdx+1A8h]
0x140004ba7  test    dword ptr [rax+0B8h], 800h
0x140004bb1  jnz     short loc_140004BC7
0x140004bb3  mov     rax, [rdx+18h]
0x140004bb7  test    byte ptr [rax+522h], 4
0x140004bbe  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140004bc5  jnz     short loc_140004BCB
0x140004bc7  mov     rax, [r15+60h]
0x140004bcb  xor     edx, edx
0x140004bcd  mov     [rsp+78h+var_58], rax
0x140004bd2  lea     rcx, Smb2DirCacheLock
0x140004bd9  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140004be0  nop     dword ptr [rax+rax+00h]
0x140004be5  xor     r9d, r9d
0x140004be8  lea     r8, [rsp+78h+var_58]
0x140004bed  lea     rdx, [rsp+78h+var_50]
0x140004bf2  mov     rcx, rbp
0x140004bf5  call    cs:__imp_RxNameCacheFetchEntryEx
0x140004bfc  nop     dword ptr [rax+rax+00h]
0x140004c01  mov     rbx, rax
0x140004c04  test    rax, rax
0x140004c07  jz      short loc_140004C2E
0x140004c09  xor     edx, edx; MRxContext
0x140004c0b  mov     rcx, rax; NameCache
0x140004c0e  call    cs:__imp_RxNameCacheCheckEntry
0x140004c15  nop     dword ptr [rax+rax+00h]
0x140004c1a  test    eax, eax
0x140004c1c  jnz     short loc_140004C96
0x140004c1e  mov     rdi, [rbx+28h]
0x140004c22  test    rdi, rdi
0x140004c25  jz      short loc_140004C2E
0x140004c27  mov     eax, [rdi+2Ch]
0x140004c2a  test    eax, eax
0x140004c2c  jnz     short loc_140004CAC
0x140004c2e  test    sil, sil
0x140004c31  jnz     loc_1400383F6
0x140004c37  test    rbx, rbx
0x140004c3a  jnz     loc_140004CD4
0x140004c40  mov     r14d, r12d
0x140004c43  xor     edx, edx
0x140004c45  lea     rcx, Smb2DirCacheLock
0x140004c4c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140004c53  nop     dword ptr [rax+rax+00h]
0x140004c58  mov     rax, [rsp+78h+arg_28]
0x140004c60  test    rax, rax
0x140004c63  jnz     loc_140004D14
0x140004c69  mov     rax, [rsp+78h+arg_20]
0x140004c71  test    rax, rax
0x140004c74  jnz     loc_140004D1C
0x140004c7a  mov     rbx, [rsp+78h+arg_8]
0x140004c82  mov     rax, rdi
0x140004c85  add     rsp, 40h
0x140004c89  pop     r15
0x140004c8b  pop     r14
0x140004c8d  pop     r13
0x140004c8f  pop     r12
0x140004c91  pop     rdi
0x140004c92  pop     rsi
0x140004c93  pop     rbp
0x140004c94  retn
0x140004c96  mov     rdx, rbx; NameCache
0x140004c99  mov     rcx, rbp; NameCacheCtl
0x140004c9c  call    cs:__imp_RxNameCacheExpireEntry
0x140004ca3  nop     dword ptr [rax+rax+00h]
0x140004ca8  xor     ebx, ebx
0x140004caa  jmp     short loc_140004C2E
0x140004cac  cmp     eax, [r15+108h]
0x140004cb3  jz      loc_140004C2E
0x140004cb9  mov     rdx, rbx; NameCache
0x140004cbc  mov     rcx, rbp; NameCacheCtl
0x140004cbf  call    cs:__imp_RxNameCacheExpireEntry
0x140004cc6  nop     dword ptr [rax+rax+00h]
0x140004ccb  xor     ebx, ebx
0x140004ccd  xor     edi, edi
0x140004ccf  jmp     loc_140004C2E
0x140004cd4  mov     rdi, [rbx+28h]
0x140004cd8  mov     r14d, [rbx+30h]
0x140004cdc  test    rdi, rdi
0x140004cdf  jz      loc_1400384C3
0x140004ce5  mov     rcx, rdi
0x140004ce8  call    Smb2ReferenceDirCacheObject
0x140004ced  test    sil, sil
0x140004cf0  jz      loc_1400384C8
0x140004cf6  movups  xmm0, xmmword ptr [r13+18h]
0x140004cfb  movups  xmmword ptr [rdi+48h], xmm0
0x140004cff  movups  xmm1, xmmword ptr [r13+28h]
0x140004d04  mov     dword ptr [rdi+34h], 25h ; '%'
0x140004d0b  movups  xmmword ptr [rdi+58h], xmm1
0x140004d0f  jmp     loc_1400384CB
0x140004d14  mov     [rax], sil
0x140004d17  jmp     loc_140004C69
0x140004d1c  mov     [rax], r14d
0x140004d1f  jmp     loc_140004C7A
0x1400383f6  xor     sil, sil
0x1400383f9  test    rbx, rbx
0x1400383fc  jnz     loc_140004CD4
0x140038402  mov     eax, [r13+8]
0x140038406  test    al, 2
0x140038408  jz      loc_140004C40
0x14003840e  mov     r9b, 1
0x140038411  lea     r8, [rsp+78h+var_58]
0x140038416  lea     rdx, [rsp+78h+var_50]
0x14003841b  mov     rcx, rbp
0x14003841e  call    cs:__imp_RxNameCacheCreateEntryEx
0x140038425  nop     dword ptr [rax+rax+00h]
0x14003842a  mov     rbx, rax
0x14003842d  test    rax, rax
0x140038430  jz      loc_140004C40
0x140038436  mov     [rax+30h], r12d
0x14003843a  mov     sil, 1
0x14003843d  mov     rcx, [r14+38h]
0x140038441  mov     eax, [rcx+0A4h]
0x140038447  test    sil, al
0x14003844a  jz      short loc_140038463
0x14003844c  test    dword ptr [rcx+0A0h], 2000000h
0x140038456  jz      short loc_140038463
0x140038458  mov     r12d, 0FFFFFFFFh
0x14003845e  jmp     loc_140004CD4
0x140038463  mov     rax, cs:__imp_MRxSmbDeviceObject
0x14003846a  mov     rcx, [rax]
0x14003846d  cmp     [r14+50h], rcx
0x140038471  jnz     short loc_1400384AA
0x140038473  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14003847a  nop     dword ptr [rax+rax+00h]
0x14003847f  cmp     [rax+0E7h], r12b
0x140038486  jz      short loc_1400384AA
0x140038488  mov     rcx, [r14+48h]
0x14003848c  lea     rdx, [rsp+78h+arg_0]
0x140038494  mov     rcx, [rcx+28h]
0x140038498  call    Smb2GetInfoCacheTimeout
0x14003849d  mov     r12d, [rsp+78h+arg_0]
0x1400384a5  jmp     loc_140004CD4
0x1400384aa  mov     rcx, [r14+50h]
0x1400384ae  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x1400384b5  nop     dword ptr [rax+rax+00h]
0x1400384ba  mov     r12d, [rax+14h]
0x1400384be  jmp     loc_140004CD4
0x1400384c3  test    sil, sil
0x1400384c6  jnz     short loc_1400384CB
0x1400384c8  xor     r12d, r12d
0x1400384cb  xor     r9d, r9d; MRxContext
0x1400384ce  mov     r8d, r12d; LifeTime
0x1400384d1  mov     rdx, rbx; NameCache
0x1400384d4  mov     rcx, rbp; NameCacheCtl
0x1400384d7  call    cs:__imp_RxNameCacheActivateEntry
0x1400384de  nop     dword ptr [rax+rax+00h]
0x1400384e3  nop
0x1400384e4  jmp     loc_140004C43
```
