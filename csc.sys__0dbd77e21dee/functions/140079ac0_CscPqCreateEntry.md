# CscPqCreateEntry

- ea: `0x140079ac0`
- end: `0x140079e19`
- name: `CscPqCreateEntry`
- size: `857`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14006bc40`
- `0x14006e0b0`

## callees

- `0x140007330`
- `0x140010be0`
- `0x140016ad8`
- `0x140016d08`
- `0x140016eb0`
- `0x1400171c0`
- `0x14001a494`
- `0x14002d0f4`
- `0x140079ac0`
- `0x14007a25c`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140079dae`
- `ntoskrnl!ExReleaseResourceLite` at `0x140079dae`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140079b52`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140079b52`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140079b2a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140079b2a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140079d9b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140079d9b`

## pseudocode

```c
__int64 __fastcall CscPqCreateEntry(__int64 a1, unsigned int *a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v5; // r14d
  PERESOURCE *v7; // r15
  int updated; // ebx
  int v9; // esi
  PVOID v10; // r12
  unsigned int v11; // edx
  unsigned int v12; // eax
  unsigned int v13; // ecx
  unsigned int v14; // r13d
  unsigned __int128 v15; // rax
  unsigned __int64 v16; // r15
  unsigned __int64 v17; // rsi
  __int64 v18; // rax
  int v19; // r13d
  unsigned int v20; // esi
  __int64 v21; // rdx
  __int64 v22; // rdx
  unsigned __int64 v23; // r9
  __int64 FileInformation[3]; // [rsp+50h] [rbp-18h] BYREF
  __int64 v26; // [rsp+B0h] [rbp+48h] BYREF
  unsigned int *v27; // [rsp+B8h] [rbp+50h]
  __int64 v28; // [rsp+C0h] [rbp+58h]
  __int64 v29; // [rsp+C8h] [rbp+60h]

  v29 = a4;
  v28 = a3;
  v27 = a2;
  v5 = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_iqq(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a3, a4, a5);
  v7 = (PERESOURCE *)(a1 + 96);
  ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 96), 1u);
  if ( *(_BYTE *)(a1 + 88) )
  {
    updated = -1073741596;
    v9 = 1587;
    goto LABEL_43;
  }
  v10 = ExAllocateFromPagedLookasideList(*(PPAGED_LOOKASIDE_LIST *)(a1 + 152));
  if ( !v10 )
  {
    updated = -1073741670;
    v9 = 1594;
    goto LABEL_43;
  }
  if ( !*(_DWORD *)(a1 + 40) )
  {
    v11 = *(_DWORD *)(a1 + 36);
    if ( v11 >= 0xFFFFFFFE )
    {
      updated = -1073741670;
      v9 = 1613;
      goto LABEL_42;
    }
    v12 = *(_DWORD *)(a1 + 92);
    v13 = -2 - v11;
    FileInformation[0] = 0;
    if ( -2 - v11 >= v12 )
      v13 = v12;
    v14 = v13;
    v15 = v13 * (unsigned __int128)*(unsigned int *)(a1 + 24);
    if ( (v15 & 0x8000000000000000uLL) == 0LL )
    {
      if ( is_mul_ok(v13, *(unsigned int *)(a1 + 24)) )
      {
LABEL_15:
        v16 = *(_QWORD *)(a1 + 80);
        v17 = v16 + v15;
        if ( v16 >> 63 == (unsigned int)((v13 * (unsigned __int64)*(unsigned int *)(a1 + 24)) >> 32) >> 31 )
        {
          *((_QWORD *)&v15 + 1) = 0x7FFFFFFFFFFFFFFFLL;
          if ( v16 >> 63 != v17 > 0x7FFFFFFFFFFFFFFFLL )
          {
            updated = -1073741675;
            v9 = 1627;
            goto LABEL_42;
          }
        }
        BYTE8(v15) = 1;
        FileInformation[0] = v16 + v15;
        updated = CscPqpChangePqHeaderState(a1, *((_QWORD *)&v15 + 1));
        if ( updated < 0 )
        {
          v9 = 1646;
          goto LABEL_42;
        }
        updated = CscStorepLowIoSetInformationFile(*(HANDLE *)(a1 + 8), FileInformation, 8u, FileEndOfFileInformation);
        if ( updated < 0 )
        {
          v9 = 1652;
          goto LABEL_42;
        }
        v18 = FileInformation[0];
        *(_DWORD *)(a1 + 36) += v14;
        *(_QWORD *)(a1 + 80) = v18;
        updated = CscPqpLinkNewAllocation(a1, v16, v17);
        if ( updated < 0 )
        {
          v9 = 1658;
          goto LABEL_42;
        }
        goto LABEL_26;
      }
    }
    else if ( *((_QWORD *)&v15 + 1) == -1 )
    {
      goto LABEL_15;
    }
    updated = -1073741675;
    v9 = 1622;
    goto LABEL_42;
  }
LABEL_26:
  v5 = *(_DWORD *)(a1 + 52);
  updated = CscPqpReadLinks(a1, v5, 0, &v26);
  if ( updated >= 0 )
  {
    v19 = v26;
    v20 = HIDWORD(v26);
    if ( (unsigned int)v26 > 1 )
    {
      updated = CscPqpReadLinks(a1, v5 + 1, 0, &v26);
      if ( updated < 0 )
      {
        v9 = 1682;
        goto LABEL_42;
      }
      HIDWORD(v26) = v20;
      LODWORD(v26) = v19 - 1;
      updated = CscPqpWriteLinks(a1, v5 + 1, 0, &v26);
      if ( updated < 0 )
      {
        v9 = 1688;
        goto LABEL_42;
      }
      v20 = v5 + 1;
    }
    v21 = v28;
    --*(_DWORD *)(a1 + 40);
    *(_DWORD *)(a1 + 52) = v20;
    CscPqpIntializeEntry(v10, v21);
    if ( v5 && v5 <= *(_DWORD *)(a1 + 36) )
    {
      v22 = *(unsigned int *)(a1 + 24);
      v23 = *(unsigned int *)(a1 + 20) + (unsigned __int64)((unsigned int)v22 * (v5 - 1));
      if ( ((v23 ^ (v23 + v22)) & 0xFFFFFFFFFFFC0000uLL) != 0 )
        LODWORD(v23) = 0;
    }
    else
    {
      LODWORD(v23) = 0;
    }
    updated = CscPqpUpdateEntry(a1, v5, (_DWORD)v10, v23, 1, 0, v29, a5, 0);
    v9 = 0;
    if ( updated < 0 )
      v9 = 1710;
    goto LABEL_42;
  }
  v9 = 1670;
LABEL_42:
  ExFreeToPagedLookasideList(*(PPAGED_LOOKASIDE_LIST *)(a1 + 152), v10);
  v7 = (PERESOURCE *)(a1 + 96);
LABEL_43:
  ExReleaseResourceLite(*v7);
  if ( updated < 0 )
    v5 = 0;
  *v27 = v5;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_DDd(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_eb62243048b93ac38d7f5193621ee294_Traceguids, v5, updated, v9);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140079ac0  mov     r11, rsp
0x140079ac3  mov     [r11+20h], r9
0x140079ac7  mov     [r11+18h], r8
0x140079acb  mov     [r11+10h], rdx
0x140079acf  push    rbp
0x140079ad0  push    rbx
0x140079ad1  push    rsi
0x140079ad2  push    rdi
0x140079ad3  push    r12
0x140079ad5  push    r13
0x140079ad7  push    r14
0x140079ad9  push    r15
0x140079adb  mov     rbp, rsp
0x140079ade  sub     rsp, 68h
0x140079ae2  xor     r14d, r14d
0x140079ae5  mov     rdi, rcx
0x140079ae8  mov     [rbp+arg_0], r14
0x140079aec  mov     rcx, cs:WPP_GLOBAL_Control
0x140079af3  lea     rax, WPP_GLOBAL_Control
0x140079afa  cmp     rcx, rax
0x140079afd  jz      short loc_140079B21
0x140079aff  test    dword ptr [rcx+2Ch], 40000h
0x140079b06  jz      short loc_140079B21
0x140079b08  mov     rax, [rbp+arg_20]
0x140079b0c  mov     rcx, [rcx+18h]
0x140079b10  mov     [r11-80h], rax
0x140079b14  mov     [rsp+68h+var_48], r9
0x140079b19  mov     r9, r8
0x140079b1c  call    WPP_SF_iqq
0x140079b21  lea     r15, [rdi+60h]
0x140079b25  mov     dl, 1; Wait
0x140079b27  mov     rcx, [r15]; Resource
0x140079b2a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140079b31  nop     dword ptr [rax+rax+00h]
0x140079b36  cmp     [rdi+58h], r14b
0x140079b3a  jz      short loc_140079B4B
0x140079b3c  mov     ebx, 0C00000E4h
0x140079b41  mov     esi, 633h
0x140079b46  jmp     loc_140079DAB
0x140079b4b  mov     rcx, [rdi+98h]; Lookaside
0x140079b52  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140079b59  nop     dword ptr [rax+rax+00h]
0x140079b5e  mov     r12, rax
0x140079b61  test    rax, rax
0x140079b64  jnz     short loc_140079B75
0x140079b66  mov     ebx, 0C000009Ah
0x140079b6b  mov     esi, 63Ah
0x140079b70  jmp     loc_140079DAB
0x140079b75  cmp     [rdi+28h], r14d
0x140079b79  jnz     loc_140079C7B
0x140079b7f  mov     edx, [rdi+24h]
0x140079b82  mov     ecx, 0FFFFFFFEh
0x140079b87  cmp     edx, ecx
0x140079b89  jb      short loc_140079B9A
0x140079b8b  mov     ebx, 0C000009Ah
0x140079b90  mov     esi, 64Dh
0x140079b95  jmp     loc_140079D91
0x140079b9a  mov     eax, [rdi+5Ch]
0x140079b9d  sub     ecx, edx
0x140079b9f  cmp     ecx, eax
0x140079ba1  mov     [rbp+FileInformation], r14
0x140079ba5  cmovnb  ecx, eax
0x140079ba8  mov     eax, [rdi+18h]
0x140079bab  mov     r13d, ecx
0x140079bae  imul    r13
0x140079bb1  test    rax, rax
0x140079bb4  jns     short loc_140079BF8
0x140079bb6  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140079bba  jnz     short loc_140079BFD
0x140079bbc  mov     r15, [rdi+50h]
0x140079bc0  mov     rcx, r15
0x140079bc3  shr     rcx, 3Fh
0x140079bc7  lea     rsi, [r15+rax]
0x140079bcb  shr     rax, 3Fh
0x140079bcf  cmp     ecx, eax
0x140079bd1  jnz     short loc_140079C0C
0x140079bd3  xor     eax, eax
0x140079bd5  mov     rdx, 7FFFFFFFFFFFFFFFh
0x140079bdf  cmp     rsi, rdx
0x140079be2  setnbe  al
0x140079be5  cmp     ecx, eax
0x140079be7  jz      short loc_140079C0C
0x140079be9  mov     ebx, 0C0000095h
0x140079bee  mov     esi, 65Bh
0x140079bf3  jmp     loc_140079D91
0x140079bf8  test    rdx, rdx
0x140079bfb  jz      short loc_140079BBC
0x140079bfd  mov     ebx, 0C0000095h
0x140079c02  mov     esi, 656h
0x140079c07  jmp     loc_140079D91
0x140079c0c  mov     dl, 1
0x140079c0e  mov     [rbp+FileInformation], rsi
0x140079c12  mov     rcx, rdi
0x140079c15  call    CscPqpChangePqHeaderState
0x140079c1a  mov     ebx, eax
0x140079c1c  test    eax, eax
0x140079c1e  jns     short loc_140079C2A
0x140079c20  mov     esi, 66Eh
0x140079c25  jmp     loc_140079D91
0x140079c2a  mov     rcx, [rdi+8]; Handle
0x140079c2e  lea     rdx, [rbp+FileInformation]; FileInformation
0x140079c32  mov     r9d, 14h; FileInformationClass
0x140079c38  lea     r8d, [r9-0Ch]; Length
0x140079c3c  call    CscStorepLowIoSetInformationFile
0x140079c41  mov     ebx, eax
0x140079c43  test    eax, eax
0x140079c45  jns     short loc_140079C51
0x140079c47  mov     esi, 674h
0x140079c4c  jmp     loc_140079D91
0x140079c51  mov     rax, [rbp+FileInformation]
0x140079c55  mov     r8, rsi
0x140079c58  add     [rdi+24h], r13d
0x140079c5c  mov     rdx, r15
0x140079c5f  mov     rcx, rdi
0x140079c62  mov     [rdi+50h], rax
0x140079c66  call    CscPqpLinkNewAllocation
0x140079c6b  mov     ebx, eax
0x140079c6d  test    eax, eax
0x140079c6f  jns     short loc_140079C7B
0x140079c71  mov     esi, 67Ah
0x140079c76  jmp     loc_140079D91
0x140079c7b  mov     r14d, [rdi+34h]
0x140079c7f  lea     r9, [rbp+arg_0]
0x140079c83  mov     edx, r14d
0x140079c86  xor     r8d, r8d
0x140079c89  mov     rcx, rdi
0x140079c8c  call    CscPqpReadLinks
0x140079c91  mov     ebx, eax
0x140079c93  test    eax, eax
0x140079c95  jns     short loc_140079CA1
0x140079c97  mov     esi, 686h
0x140079c9c  jmp     loc_140079D91
0x140079ca1  mov     r13d, dword ptr [rbp+arg_0]
0x140079ca5  mov     esi, dword ptr [rbp+arg_0+4]
0x140079ca8  cmp     r13d, 1
0x140079cac  jbe     short loc_140079D03
0x140079cae  lea     r15d, [r14+1]
0x140079cb2  xor     r8d, r8d
0x140079cb5  mov     edx, r15d
0x140079cb8  lea     r9, [rbp+arg_0]
0x140079cbc  mov     rcx, rdi
0x140079cbf  call    CscPqpReadLinks
0x140079cc4  mov     ebx, eax
0x140079cc6  test    eax, eax
0x140079cc8  jns     short loc_140079CD4
0x140079cca  mov     esi, 692h
0x140079ccf  jmp     loc_140079D91
0x140079cd4  lea     eax, [r13-1]
0x140079cd8  mov     dword ptr [rbp+arg_0+4], esi
0x140079cdb  lea     r9, [rbp+arg_0]
0x140079cdf  mov     dword ptr [rbp+arg_0], eax
0x140079ce2  xor     r8d, r8d
0x140079ce5  mov     edx, r15d
0x140079ce8  mov     rcx, rdi
0x140079ceb  call    CscPqpWriteLinks
0x140079cf0  mov     ebx, eax
0x140079cf2  test    eax, eax
0x140079cf4  jns     short loc_140079D00
0x140079cf6  mov     esi, 698h
0x140079cfb  jmp     loc_140079D91
0x140079d00  mov     esi, r15d
0x140079d03  mov     rdx, [rbp+arg_10]
0x140079d07  mov     rcx, r12
0x140079d0a  dec     dword ptr [rdi+28h]
0x140079d0d  mov     [rdi+34h], esi
0x140079d10  call    CscPqpIntializeEntry
0x140079d15  test    r14d, r14d
0x140079d18  jz      short loc_140079D49
0x140079d1a  cmp     r14d, [rdi+24h]
0x140079d1e  ja      short loc_140079D49
0x140079d20  mov     edx, [rdi+18h]
0x140079d23  lea     r9d, [r14-1]
0x140079d27  mov     eax, [rdi+14h]
0x140079d2a  imul    r9d, edx
0x140079d2e  add     r9, rax
0x140079d31  mov     eax, 0
0x140079d36  add     rdx, r9
0x140079d39  xor     rdx, r9
0x140079d3c  test    rdx, 0FFFFFFFFFFFC0000h
0x140079d43  cmovnz  r9, rax
0x140079d47  jmp     short loc_140079D4C
0x140079d49  xor     r9d, r9d
0x140079d4c  mov     rax, [rbp+arg_20]
0x140079d50  mov     r8, r12
0x140079d53  mov     [rsp+68h+var_28], 0
0x140079d5c  mov     edx, r14d
0x140079d5f  mov     [rsp+68h+var_30], rax
0x140079d64  mov     rcx, rdi
0x140079d67  mov     rax, [rbp+arg_18]
0x140079d6b  mov     [rsp+68h+var_38], rax
0x140079d70  mov     [rsp+68h+var_40], 0
0x140079d79  mov     byte ptr [rsp+68h+var_48], 1
0x140079d7e  call    CscPqpUpdateEntry
0x140079d83  mov     ebx, eax
0x140079d85  xor     esi, esi
0x140079d87  test    ebx, ebx
0x140079d89  mov     eax, 6AEh
0x140079d8e  cmovs   esi, eax
0x140079d91  mov     rcx, [rdi+98h]; Lookaside
0x140079d98  mov     rdx, r12; Entry
0x140079d9b  call    cs:__imp_ExFreeToPagedLookasideList
0x140079da2  nop     dword ptr [rax+rax+00h]
0x140079da7  lea     r15, [rdi+60h]
0x140079dab  mov     rcx, [r15]; Resource
0x140079dae  call    cs:__imp_ExReleaseResourceLite
0x140079db5  nop     dword ptr [rax+rax+00h]
0x140079dba  xor     eax, eax
0x140079dbc  test    ebx, ebx
0x140079dbe  cmovs   r14d, eax
0x140079dc2  mov     rax, [rbp+arg_8]
0x140079dc6  mov     [rax], r14d
0x140079dc9  mov     rcx, cs:WPP_GLOBAL_Control
0x140079dd0  lea     rax, WPP_GLOBAL_Control
0x140079dd7  cmp     rcx, rax
0x140079dda  jz      short loc_140079E05
0x140079ddc  test    dword ptr [rcx+2Ch], 40000h
0x140079de3  jz      short loc_140079E05
0x140079de5  mov     rcx, [rcx+18h]
0x140079de9  lea     r8, WPP_eb62243048b93ac38d7f5193621ee294_Traceguids
0x140079df0  mov     edx, 27h ; '''
0x140079df5  mov     dword ptr [rsp+68h+var_40], esi
0x140079df9  mov     r9d, r14d
0x140079dfc  mov     dword ptr [rsp+68h+var_48], ebx
0x140079e00  call    WPP_SF_DDd
0x140079e05  mov     eax, ebx
0x140079e07  add     rsp, 68h
0x140079e0b  pop     r15
0x140079e0d  pop     r14
0x140079e0f  pop     r13
0x140079e11  pop     r12
0x140079e13  pop     rdi
0x140079e14  pop     rsi
0x140079e15  pop     rbx
0x140079e16  pop     rbp
0x140079e17  retn
```
