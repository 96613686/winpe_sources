# Smb2PopulateDirectoryCache

- ea: `0x140001c70`
- end: `0x140002097`
- name: `Smb2PopulateDirectoryCache`
- size: `1063`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140002b80`

## callees

- `0x1400019a0`
- `0x140001a40`
- `0x140001c70`
- `0x14002b568`
- `0x140032b30`
- `0x140055650`
- `0x1400575a0`

## import_xrefs

- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x140001ecc`
- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x140002079`
- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x140001ecc`
- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x140002079`
- `mrxsmb!SmbCseReleaseCompoundingKey` at `0x140001e80`
- `mrxsmb!SmbCseReleaseCompoundingKey` at `0x140001e80`
- `mrxsmb!SmbCseAllocateCompoundingKey` at `0x140001d68`
- `mrxsmb!SmbCseAllocateCompoundingKey` at `0x140001d68`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140001cca`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140001cca`
- `mrxsmb!SmbCeAssociateExchangeWithCompoundingKeyEx` at `0x140001e48`
- `mrxsmb!SmbCeAssociateExchangeWithCompoundingKeyEx` at `0x140001e48`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140001e98`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140001eb5`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140001fc7`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140001fd8`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140001e98`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140001eb5`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140001fc7`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140001fd8`
- `mrxsmb!SmbCeInitiateExchange` at `0x140001e67`
- `mrxsmb!SmbCeInitiateExchange` at `0x140001fa5`
- `mrxsmb!SmbCeInitiateExchange` at `0x140001e67`
- `mrxsmb!SmbCeInitiateExchange` at `0x140001fa5`
- `mrxsmb!SmbCeInitializeExchange` at `0x140001da8`
- `mrxsmb!SmbCeInitializeExchange` at `0x140001f56`
- `mrxsmb!SmbCeInitializeExchange` at `0x140001da8`
- `mrxsmb!SmbCeInitializeExchange` at `0x140001f56`

## pseudocode

```c
__int64 __fastcall Smb2PopulateDirectoryCache(_QWORD *a1, _DWORD *a2)
{
  __int64 v2; // rax
  unsigned __int8 v4; // bl
  __int64 v5; // r8
  __int64 v7; // rax
  __int64 v8; // r13
  __int64 v9; // r12
  __int64 v10; // rcx
  __int64 v11; // r8
  unsigned int v12; // ebx
  __int64 CompoundingKey; // r15
  int v14; // r12d
  unsigned int v15; // esi
  __int64 v16; // rax
  int v17; // eax
  int v18; // eax
  __int64 result; // rax
  __int64 v20; // [rsp+40h] [rbp-38h]
  __int64 v21; // [rsp+48h] [rbp-30h]
  __int128 v22; // [rsp+50h] [rbp-28h] BYREF
  rsize_t NumOfElements[2]; // [rsp+60h] [rbp-18h]
  char v24; // [rsp+C0h] [rbp+48h]
  unsigned int v25; // [rsp+C8h] [rbp+50h]
  unsigned int v26; // [rsp+D0h] [rbp+58h] BYREF
  __int64 v27; // [rsp+D8h] [rbp+60h] BYREF

  v2 = a1[9];
  v20 = a1[10];
  v4 = 0;
  v26 = 0;
  v5 = *(_QWORD *)(v2 + 40);
  v7 = a1[7];
  v24 = 0;
  v8 = *(_QWORD *)(v5 + 40);
  v22 = 0;
  v27 = 0;
  *(_OWORD *)NumOfElements = 0;
  v9 = *(_QWORD *)(v7 + 136);
  v21 = v9;
  *(_QWORD *)&v22 = a2;
  v10 = *(unsigned int *)(MRxSmbGetInstanceConfigurationBlock(v20) + 36);
  DWORD2(v22) = v10;
  if ( !(_DWORD)v10 )
  {
    if ( (*(_DWORD *)(a1[7] + 164LL) & 1) != 0 )
    {
      v10 = 0x7FFFFFFF;
    }
    else
    {
      v4 = 1;
      v10 = 0x100000;
      v24 = 1;
    }
    DWORD2(v22) = v10;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qDd(WPP_GLOBAL_Control->AttachedDevice, WPP_GLOBAL_Control, v11, a2, v10, v4);
  }
  Smb2FetchVolumeFeatureSupportFromCache(v10, *(_QWORD *)(v8 + 424) + 928LL, *(_QWORD *)(v9 + 32), &v26);
  v12 = v26;
  v25 = v26;
  while ( 1 )
  {
    CompoundingKey = SmbCseAllocateCompoundingKey(32);
    if ( !CompoundingKey )
    {
      v18 = -1073741670;
      goto LABEL_43;
    }
    v27 = 0;
    v14 = SmbCeInitializeExchange(&v27, a1, 0, 0, 0, v8, 4032, &PopulateDirCacheDispatch);
    v15 = -1073739516;
    if ( v14 )
      goto LABEL_36;
    if ( (v25 & 4) != 0 )
      a2[13] = (v25 & 2) != 0 || (*(_BYTE *)(v20 + 1314) & 4) == 0 ? 37 : 63;
    else
      a2[13] = 81;
    v16 = v27;
    a2[17] = 0;
    a2[15] = 0;
    a2[14] = 0;
    *(_QWORD *)(v16 + 3792) = &v22;
    *(_BYTE *)(v27 + 3800) = 1;
    *(_BYTE *)(v27 + 3801) = *((_BYTE *)a2 + 52);
    _InterlockedOr((volatile signed __int32 *)(v27 + 68), 1u);
    SmbCeAssociateExchangeWithCompoundingKeyEx(v27, CompoundingKey, 0xFFFF);
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1[7] + 136LL) + 88LL));
    v14 = SmbCeInitiateExchange(v27);
    if ( v14 == 259 )
    {
      SmbCseReleaseCompoundingKey(CompoundingKey);
      v14 = SmbCeWaitForCompletionAndFinalizeExchangeEx(v27, 0, 0, 0);
    }
    else
    {
      SmbCeWaitForCompletionAndFinalizeExchangeEx(v27, 0, 0, 0);
    }
    v27 = 0;
    SmbCseDereferenceCompoundingKey(CompoundingKey);
    CompoundingKey = 0;
    if ( (unsigned int)(v14 + 1073741822) > 1 && v14 != -1073741637 )
      break;
    v17 = a2[13];
    if ( v17 == 81 )
    {
      v25 |= 4u;
    }
    else
    {
      if ( v17 != 63 )
        break;
      v25 |= 2u;
    }
  }
  if ( v14 )
    goto LABEL_36;
  if ( v24 )
    goto LABEL_41;
  do
  {
    v27 = 0;
    v14 = SmbCeInitializeExchange(&v27, a1, 0, 0, 0, v8, 4032, &PopulateDirCacheDispatch);
    if ( v14 )
      break;
    *(_QWORD *)(v27 + 3792) = &v22;
    *(_BYTE *)(v27 + 3800) = 0;
    *(_BYTE *)(v27 + 3801) = *((_BYTE *)a2 + 52);
    _InterlockedOr((volatile signed __int32 *)(v27 + 68), 0x2001u);
    v14 = SmbCeInitiateExchange(v27);
    if ( v14 == 259 )
      v14 = SmbCeWaitForCompletionAndFinalizeExchangeEx(v27, 0, 0, 0);
    else
      SmbCeWaitForCompletionAndFinalizeExchangeEx(v27, 0, 0, 0);
  }
  while ( !v14 );
  v12 = v26;
LABEL_36:
  v18 = 0;
  if ( v14 != -2147483642 )
    v18 = v14;
  if ( v18 )
  {
    if ( v18 != -1073739516 )
      goto LABEL_43;
LABEL_41:
    Smb2RememberDontCacheDirectory(a1);
    goto LABEL_44;
  }
  v18 = Smb2BuildDirectoryCacheIndex(a2, LODWORD(NumOfElements[0]), HIDWORD(NumOfElements[0]));
LABEL_43:
  v15 = v18;
LABEL_44:
  if ( v25 != v12 )
    Smb2UpdateVolumeFeatureSupportCacheEntry(a1, *(_QWORD *)(v8 + 424) + 928LL, *(_QWORD *)(v21 + 32), v25, v15);
  result = Smb2TransitionDirCacheObject(a2, *(unsigned int *)(v8 + 264), v15);
  if ( !(_BYTE)result )
    _InterlockedIncrement64((volatile signed __int64 *)(v8 + 584));
  if ( CompoundingKey )
    return SmbCseDereferenceCompoundingKey(CompoundingKey);
  return result;
}

```

## disassembly

```asm
0x140001c70  push    rbp
0x140001c72  push    rbx
0x140001c73  push    rsi
0x140001c74  push    rdi
0x140001c75  push    r12
0x140001c77  push    r13
0x140001c79  push    r14
0x140001c7b  push    r15
0x140001c7d  mov     rbp, rsp
0x140001c80  sub     rsp, 78h
0x140001c84  mov     rax, [rcx+48h]
0x140001c88  mov     r14, rcx
0x140001c8b  mov     rcx, [rcx+50h]
0x140001c8f  xorps   xmm0, xmm0
0x140001c92  xor     esi, esi
0x140001c94  mov     [rbp+var_38], rcx
0x140001c98  xor     bl, bl
0x140001c9a  mov     [rbp+arg_10], esi
0x140001c9d  mov     r8, [rax+28h]
0x140001ca1  mov     rdi, rdx
0x140001ca4  mov     rax, [r14+38h]
0x140001ca8  mov     [rbp+arg_0], bl
0x140001cab  mov     r13, [r8+28h]
0x140001caf  movups  [rbp+var_28], xmm0
0x140001cb3  mov     [rbp+arg_18], rsi
0x140001cb7  movups  xmmword ptr [rbp+NumOfElements], xmm0
0x140001cbb  mov     r12, [rax+88h]
0x140001cc2  mov     [rbp+var_30], r12
0x140001cc6  mov     qword ptr [rbp+var_28], rdx
0x140001cca  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x140001cd1  nop     dword ptr [rax+rax+00h]
0x140001cd6  mov     ecx, [rax+24h]
0x140001cd9  mov     dword ptr [rbp+var_28+8], ecx
0x140001cdc  test    ecx, ecx
0x140001cde  jnz     short loc_140001D03
0x140001ce0  mov     rax, [r14+38h]
0x140001ce4  mov     ecx, [rax+0A4h]
0x140001cea  test    cl, 1
0x140001ced  jz      short loc_140001CF6
0x140001cef  mov     ecx, 7FFFFFFFh
0x140001cf4  jmp     short loc_140001D00
0x140001cf6  mov     bl, 1
0x140001cf8  mov     ecx, 100000h
0x140001cfd  mov     [rbp+arg_0], bl
0x140001d00  mov     dword ptr [rbp+var_28+8], ecx
0x140001d03  mov     rdx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140001d0a  lea     rax, WPP_GLOBAL_Control
0x140001d11  cmp     rdx, rax
0x140001d14  jz      short loc_140001D3A
0x140001d16  mov     eax, [rdx+2Ch]
0x140001d19  test    al, al
0x140001d1b  jns     short loc_140001D3A
0x140001d1d  cmp     byte ptr [rdx+29h], 2
0x140001d21  jb      short loc_140001D3A
0x140001d23  movzx   eax, bl
0x140001d26  mov     r9, rdi
0x140001d29  mov     dword ptr [rsp+78h+var_50], eax
0x140001d2d  mov     dword ptr [rsp+78h+var_58], ecx
0x140001d31  mov     rcx, [rdx+18h]
0x140001d35  call    WPP_SF_qDd
0x140001d3a  mov     rdx, [r13+1A8h]
0x140001d41  lea     r9, [rbp+arg_10]
0x140001d45  mov     r8, [r12+20h]
0x140001d4a  add     rdx, 3A0h
0x140001d51  call    Smb2FetchVolumeFeatureSupportFromCache
0x140001d56  mov     ebx, [rbp+arg_10]
0x140001d59  mov     [rbp+arg_8], ebx
0x140001d5c  mov     ecx, 20h ; ' '
0x140001d61  lea     r12, PopulateDirCacheDispatch
0x140001d68  call    cs:__imp_SmbCseAllocateCompoundingKey
0x140001d6f  nop     dword ptr [rax+rax+00h]
0x140001d74  mov     r15, rax
0x140001d77  test    rax, rax
0x140001d7a  jz      loc_140002020
0x140001d80  mov     [rsp+78h+var_40], r12
0x140001d85  lea     rcx, [rbp+arg_18]
0x140001d89  mov     [rsp+78h+var_48], 0FC0h
0x140001d91  xor     r9d, r9d
0x140001d94  mov     [rsp+78h+var_50], r13
0x140001d99  xor     r8d, r8d
0x140001d9c  mov     rdx, r14
0x140001d9f  mov     [rsp+78h+var_58], rsi
0x140001da4  mov     [rbp+arg_18], rsi
0x140001da8  call    cs:__imp_SmbCeInitializeExchange
0x140001daf  nop     dword ptr [rax+rax+00h]
0x140001db4  mov     r12d, eax
0x140001db7  mov     esi, 0C0000904h
0x140001dbc  test    eax, eax
0x140001dbe  jnz     loc_140001FF0
0x140001dc4  mov     eax, [rbp+arg_8]
0x140001dc7  test    al, 4
0x140001dc9  jz      short loc_140001DEE
0x140001dcb  test    al, 2
0x140001dcd  jnz     short loc_140001DE5
0x140001dcf  mov     rax, [rbp+var_38]
0x140001dd3  test    byte ptr [rax+522h], 4
0x140001dda  jz      short loc_140001DE5
0x140001ddc  mov     dword ptr [rdi+34h], 3Fh ; '?'
0x140001de3  jmp     short loc_140001DF5
0x140001de5  mov     dword ptr [rdi+34h], 25h ; '%'
0x140001dec  jmp     short loc_140001DF5
0x140001dee  mov     dword ptr [rdi+34h], 51h ; 'Q'
0x140001df5  mov     rax, [rbp+arg_18]
0x140001df9  lea     rcx, [rbp+var_28]
0x140001dfd  mov     dword ptr [rdi+44h], 0
0x140001e04  mov     dword ptr [rdi+3Ch], 0
0x140001e0b  mov     dword ptr [rdi+38h], 0
0x140001e12  mov     [rax+0ED0h], rcx
0x140001e19  mov     rax, [rbp+arg_18]
0x140001e1d  mov     byte ptr [rax+0ED8h], 1
0x140001e24  mov     rax, [rbp+arg_18]
0x140001e28  movzx   ecx, byte ptr [rdi+34h]
0x140001e2c  mov     [rax+0ED9h], cl
0x140001e32  mov     rax, [rbp+arg_18]
0x140001e36  lock or dword ptr [rax+44h], 1
0x140001e3b  mov     rcx, [rbp+arg_18]
0x140001e3f  mov     r8d, 0FFFFh
0x140001e45  mov     rdx, r15
0x140001e48  call    cs:__imp_SmbCeAssociateExchangeWithCompoundingKeyEx
0x140001e4f  nop     dword ptr [rax+rax+00h]
0x140001e54  mov     rax, [r14+38h]
0x140001e58  mov     rcx, [rax+88h]
0x140001e5f  lock inc dword ptr [rcx+58h]
0x140001e63  mov     rcx, [rbp+arg_18]
0x140001e67  call    cs:__imp_SmbCeInitiateExchange
0x140001e6e  nop     dword ptr [rax+rax+00h]
0x140001e73  mov     r12d, eax
0x140001e76  cmp     eax, 103h
0x140001e7b  jnz     short loc_140001EA9
0x140001e7d  mov     rcx, r15
0x140001e80  call    cs:__imp_SmbCseReleaseCompoundingKey
0x140001e87  nop     dword ptr [rax+rax+00h]
0x140001e8c  mov     rcx, [rbp+arg_18]
0x140001e90  xor     r9d, r9d
0x140001e93  xor     r8d, r8d
0x140001e96  xor     edx, edx
0x140001e98  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140001e9f  nop     dword ptr [rax+rax+00h]
0x140001ea4  mov     r12d, eax
0x140001ea7  jmp     short loc_140001EC1
0x140001ea9  mov     rcx, [rbp+arg_18]
0x140001ead  xor     r9d, r9d
0x140001eb0  xor     r8d, r8d
0x140001eb3  xor     edx, edx
0x140001eb5  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140001ebc  nop     dword ptr [rax+rax+00h]
0x140001ec1  mov     rcx, r15
0x140001ec4  mov     [rbp+arg_18], 0
0x140001ecc  call    cs:__imp_SmbCseDereferenceCompoundingKey
0x140001ed3  nop     dword ptr [rax+rax+00h]
0x140001ed8  lea     eax, [r12+3FFFFFFEh]
0x140001ee0  xor     r15d, r15d
0x140001ee3  cmp     eax, 1
0x140001ee6  jbe     short loc_140001EF1
0x140001ee8  cmp     r12d, 0C00000BBh
0x140001eef  jnz     short loc_140001F14
0x140001ef1  mov     eax, [rdi+34h]
0x140001ef4  cmp     eax, 51h ; 'Q'
0x140001ef7  jnz     short loc_140001F04
0x140001ef9  or      [rbp+arg_8], 4
0x140001efd  xor     esi, esi
0x140001eff  jmp     loc_140001D5C
0x140001f04  cmp     eax, 3Fh ; '?'
0x140001f07  jnz     short loc_140001F14
0x140001f09  or      [rbp+arg_8], 2
0x140001f0d  xor     esi, esi
0x140001f0f  jmp     loc_140001D5C
0x140001f14  test    r12d, r12d
0x140001f17  jnz     loc_140001FF0
0x140001f1d  cmp     [rbp+arg_0], r15b
0x140001f21  jnz     loc_140002016
0x140001f27  lea     rbx, PopulateDirCacheDispatch
0x140001f2e  mov     [rsp+78h+var_40], rbx
0x140001f33  lea     rcx, [rbp+arg_18]
0x140001f37  mov     [rsp+78h+var_48], 0FC0h
0x140001f3f  xor     r9d, r9d
0x140001f42  mov     [rsp+78h+var_50], r13
0x140001f47  xor     r8d, r8d
0x140001f4a  mov     rdx, r14
0x140001f4d  mov     [rsp+78h+var_58], r15
0x140001f52  mov     [rbp+arg_18], r15
0x140001f56  call    cs:__imp_SmbCeInitializeExchange
0x140001f5d  nop     dword ptr [rax+rax+00h]
0x140001f62  mov     r12d, eax
0x140001f65  test    eax, eax
0x140001f67  jnz     loc_140001FED
0x140001f6d  mov     rax, [rbp+arg_18]
0x140001f71  lea     rcx, [rbp+var_28]
0x140001f75  mov     [rax+0ED0h], rcx
0x140001f7c  mov     rax, [rbp+arg_18]
0x140001f80  mov     [rax+0ED8h], r15b
0x140001f87  mov     rax, [rbp+arg_18]
0x140001f8b  movzx   ecx, byte ptr [rdi+34h]
0x140001f8f  mov     [rax+0ED9h], cl
0x140001f95  mov     rax, [rbp+arg_18]
0x140001f99  lock or dword ptr [rax+44h], 2001h
0x140001fa1  mov     rcx, [rbp+arg_18]
0x140001fa5  call    cs:__imp_SmbCeInitiateExchange
0x140001fac  nop     dword ptr [rax+rax+00h]
0x140001fb1  mov     rcx, [rbp+arg_18]
0x140001fb5  xor     r9d, r9d
0x140001fb8  xor     r8d, r8d
0x140001fbb  xor     edx, edx
0x140001fbd  mov     r12d, eax
0x140001fc0  cmp     eax, 103h
0x140001fc5  jnz     short loc_140001FD8
0x140001fc7  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140001fce  nop     dword ptr [rax+rax+00h]
0x140001fd3  mov     r12d, eax
0x140001fd6  jmp     short loc_140001FE4
0x140001fd8  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140001fdf  nop     dword ptr [rax+rax+00h]
0x140001fe4  test    r12d, r12d
0x140001fe7  jz      loc_140001F2E
0x140001fed  mov     ebx, [rbp+arg_10]
0x140001ff0  xor     eax, eax
0x140001ff2  cmp     r12d, 80000006h
0x140001ff9  cmovnz  eax, r12d
0x140001ffd  test    eax, eax
0x140001fff  jnz     short loc_140002012
0x140002001  mov     r8d, dword ptr [rbp+NumOfElements+4]; rsize_t
0x140002005  mov     rcx, rdi; Context
0x140002008  mov     edx, dword ptr [rbp+NumOfElements]; NumOfElements
0x14000200b  call    Smb2BuildDirectoryCacheIndex
0x140002010  jmp     short loc_140002025
0x140002012  cmp     eax, esi
0x140002014  jnz     short loc_140002025
0x140002016  mov     rcx, r14
0x140002019  call    Smb2RememberDontCacheDirectory
0x14000201e  jmp     short loc_140002027
0x140002020  mov     eax, 0C000009Ah
0x140002025  mov     esi, eax
0x140002027  mov     eax, [rbp+arg_8]
0x14000202a  cmp     eax, ebx
0x14000202c  jz      short loc_140002053
0x14000202e  mov     rdx, [r13+1A8h]
0x140002035  mov     r9d, eax
0x140002038  mov     r8, [rbp+var_30]
0x14000203c  add     rdx, 3A0h
0x140002043  mov     rcx, r14
0x140002046  mov     dword ptr [rsp+78h+var_58], esi
0x14000204a  mov     r8, [r8+20h]
0x14000204e  call    Smb2UpdateVolumeFeatureSupportCacheEntry
0x140002053  mov     edx, [r13+108h]
0x14000205a  mov     r8d, esi
0x14000205d  mov     rcx, rdi
0x140002060  call    Smb2TransitionDirCacheObject
0x140002065  test    al, al
0x140002067  jnz     short loc_140002071
0x140002069  lock inc qword ptr [r13+248h]
0x140002071  test    r15, r15
0x140002074  jz      short loc_140002085
0x140002076  mov     rcx, r15
0x140002079  call    cs:__imp_SmbCseDereferenceCompoundingKey
0x140002080  nop     dword ptr [rax+rax+00h]
0x140002085  add     rsp, 78h
0x140002089  pop     r15
0x14000208b  pop     r14
0x14000208d  pop     r13
0x14000208f  pop     r12
0x140002091  pop     rdi
0x140002092  pop     rsi
0x140002093  pop     rbx
0x140002094  pop     rbp
0x140002095  retn
```
