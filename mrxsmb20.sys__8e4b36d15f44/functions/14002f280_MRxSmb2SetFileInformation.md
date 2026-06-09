# MRxSmb2SetFileInformation

- ea: `0x14002f280`
- end: `0x14002f780`
- name: `MRxSmb2SetFileInformation`
- size: `1280`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x14000ab50`
- `0x140014650`
- `0x140014a00`
- `0x140014db0`
- `0x140017960`
- `0x14001fed0`
- `0x140028ba0`
- `0x140029764`
- `0x14002f280`
- `0x1400372c0`
- `0x140055eb0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002f643`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f643`
- `ntoskrnl!ExAllocatePool2` at `0x14002f3a3`
- `ntoskrnl!ExAllocatePool2` at `0x14002f3a3`
- `rdbss!RxCrackPathName` at `0x14002f3df`
- `rdbss!RxCrackPathName` at `0x14002f3df`

## pseudocode

```c
__int64 __fastcall MRxSmb2SetFileInformation(__int64 a1)
{
  __int64 v1; // rdx
  int *v2; // r14
  __int64 v3; // r15
  int v5; // esi
  __int64 v6; // r9
  __int64 v7; // r13
  __int64 v8; // rsi
  unsigned int v9; // edx
  _DWORD *v10; // rax
  int v11; // r12d
  unsigned int v12; // ecx
  unsigned int v13; // eax
  __int64 v14; // r9
  unsigned int v15; // eax
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  __int64 Pool2; // rax
  __int64 v19; // rdi
  unsigned int v21; // ecx
  const void *v22; // rdx
  size_t v23; // r8
  char v24; // di
  int v25; // r8d
  __int64 v26; // r15
  __int32 v27; // esi
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // r9
  __int64 v31; // r8
  __int64 v32; // r9
  void *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // r9
  __int64 v37; // r9
  __int64 v38; // r9
  int v39; // [rsp+20h] [rbp-28h]
  void *Src[2]; // [rsp+30h] [rbp-18h] BYREF
  bool v41; // [rsp+90h] [rbp+48h]
  int v42; // [rsp+98h] [rbp+50h]
  __int64 v43; // [rsp+A0h] [rbp+58h]
  __int64 v44; // [rsp+A8h] [rbp+60h]

  v1 = *(_QWORD *)(a1 + 56);
  v2 = (int *)(a1 + 448);
  v3 = *(_QWORD *)(a1 + 72);
  v5 = *(_DWORD *)(v1 + 232) & 0x10;
  v6 = *(_QWORD *)(v1 + 120);
  v41 = v5 != 0;
  v43 = v6;
  v7 = *(_QWORD *)(*(_QWORD *)(v3 + 40) + 40LL);
  v44 = *(_QWORD *)(v1 + 136);
  v42 = v5;
  if ( *(_DWORD *)(a1 + 448) != 10 || !*(_BYTE *)(a1 + 479) )
    goto LABEL_6;
  v8 = *(_QWORD *)(a1 + 456);
  *(_OWORD *)Src = 0;
  v9 = *(_DWORD *)(v8 + 16);
  if ( v9 > 2 && *(_WORD *)(v8 + 20) == 58 )
  {
    v5 = v42;
LABEL_6:
    v10 = (_DWORD *)(a1 + 448);
    goto LABEL_7;
  }
  v12 = **(unsigned __int16 **)(v3 + 80);
  v13 = v12 + v9;
  if ( v12 + v9 < v12 )
  {
    v14 = 3221225621LL;
LABEL_28:
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return 3221225734LL;
    }
    v17 = 12;
    goto LABEL_32;
  }
  v14 = 0;
  if ( v13 > 0xFFFE )
    goto LABEL_28;
  v15 = v13 + 24;
  if ( v15 < 0x18 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return 3221225734LL;
    }
    v17 = 13;
    v14 = 3221225621LL;
LABEL_32:
    WPP_SF_d(v16->AttachedDevice, v17, WPP_69214addf0f23a16977eb0c8dd6a2623_Traceguids, v14);
    return 3221225734LL;
  }
  Pool2 = ExAllocatePool2(258, v15, 1834184274);
  v19 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  *(_OWORD *)Pool2 = *(_OWORD *)v8;
  *(_QWORD *)(Pool2 + 16) = *(_QWORD *)(v8 + 16);
  RxCrackPathName(*(_QWORD *)(v3 + 80), Src, 0, 0);
  if ( LOWORD(Src[0]) <= 2u )
  {
    *(_WORD *)(v19 + 20) = 92;
    *(_DWORD *)(v19 + 16) += 2;
    v21 = 1;
  }
  else
  {
    memmove((void *)(v19 + 20), Src[1], LOWORD(Src[0]));
    *(_WORD *)(v19 + 2 * ((unsigned __int64)LOWORD(Src[0]) >> 1) + 20) = 92;
    *(_DWORD *)(v19 + 16) += LOWORD(Src[0]) + 2;
    v21 = (LOWORD(Src[0]) >> 1) + 1;
  }
  if ( *(_DWORD *)(v8 + 16) > 2u && *(_WORD *)(v8 + 20) == 92 )
  {
    *(_DWORD *)(v19 + 16) -= 2;
    v22 = (const void *)(v8 + 22);
    v23 = *(unsigned int *)(v8 + 16) - 2LL;
  }
  else
  {
    v23 = *(unsigned int *)(v8 + 16);
    v22 = (const void *)(v8 + 20);
  }
  memmove((void *)(v19 + 2 * (v21 + 10LL)), v22, v23);
  v6 = v43;
  v10 = (_DWORD *)(a1 + 448);
  v5 = v42;
  *(_QWORD *)(a1 + 464) = v19;
LABEL_7:
  if ( *v10 == 10 && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v6 + 40) + 88LL) + 764LL) & 0x20) != 0 )
  {
    v11 = 0;
  }
  else
  {
    v11 = Smb2SetInformation(a1, 1);
    if ( v11 < 0 )
      goto LABEL_51;
    v6 = v43;
  }
  v24 = 0;
  *(_BYTE *)(*(_QWORD *)(v3 + 48) + 320LL) = 1;
  v25 = *v2;
  if ( *v2 == 4 )
    goto LABEL_42;
  if ( *v2 == 10 || *v2 == 11 )
  {
    *(_OWORD *)Src = 0;
    if ( v25 != 10 || !*(_BYTE *)(a1 + 479) || (v34 = *(_QWORD *)(a1 + 464)) == 0 )
      v34 = *(_QWORD *)(a1 + 456);
    WORD1(Src[0]) = *(_WORD *)(v34 + 16);
    LOWORD(Src[0]) = WORD1(Src[0]);
    Src[1] = (void *)(v34 + 20);
    if ( v25 == 10 )
    {
      v35 = *(_QWORD *)(v6 + 40);
      LOBYTE(v6) = v41;
      Smb2InvalidateFileNotFoundCacheEx(a1, v35 + 560, Src, v6);
      v26 = v43;
      LOBYTE(v36) = v41;
      Smb2InvalidateFileIdentityCacheEntryEx(a1, *(_QWORD *)(v43 + 40) + 192LL, Src, v36);
      Smb2InvalidateContainingDirInfoCacheEx(a1, Src, *(_QWORD *)(v7 + 424) + 1112LL, v37);
      if ( v5 )
      {
        LOBYTE(v38) = 1;
        Smb2InvalidateDirInfoCacheEx(a1, Src, *(_QWORD *)(v7 + 424) + 1112LL, v38, 1);
      }
      v24 = 1;
    }
    else if ( v25 == 11 )
    {
      Smb2InvalidateContainingDirInfoCacheEx(a1, Src, *(_QWORD *)(v7 + 424) + 1112LL, v6);
      v26 = v43;
      Smb2InvalidateFileNotFoundCacheEx(a1, *(_QWORD *)(v43 + 40) + 560LL, Src, 0);
    }
    else
    {
      v26 = v43;
    }
    if ( !v24 )
      goto LABEL_51;
    goto LABEL_43;
  }
  if ( *v2 == 19 || *v2 == 20 || (unsigned int)(*v2 - 39) <= 1 )
  {
LABEL_42:
    v26 = v43;
LABEL_43:
    Smb2InvalidateFileInfoCacheEntry(a1, *(_QWORD *)(v26 + 40) + 376LL);
    v27 = 0;
    v28 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 288LL);
    if ( v28 )
    {
      v29 = *(_QWORD *)(v28 + 136);
      if ( v29 )
        v27 = *(_DWORD *)(v29 + 88);
    }
    Smb2InvalidateSingleFileInDirInfoCache(a1, *(_QWORD *)(v7 + 424) + 1112LL);
    _InterlockedExchange((volatile __int32 *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 136LL) + 84LL), v27);
    if ( v42 )
    {
      LOBYTE(v30) = 1;
      LOBYTE(v39) = 1;
      Smb2InvalidateDirInfoCacheEx(a1, 0, *(_QWORD *)(v7 + 424) + 1112LL, v30, v39);
    }
    if ( v24 )
    {
      LOBYTE(v30) = v41;
      Smb2InvalidateFileIdentityCacheEntryEx(a1, *(_QWORD *)(v26 + 40) + 192LL, 0, v30);
      LOBYTE(v31) = 1;
      Smb2DeleteSingleFileInDirInfoCache(a1, *(_QWORD *)(v7 + 424) + 1112LL, v31);
      if ( v42 )
      {
        LOBYTE(v32) = 1;
        LOBYTE(v39) = 1;
        Smb2InvalidateDirInfoCacheEx(a1, 0, *(_QWORD *)(v7 + 424) + 1112LL, v32, v39);
      }
    }
  }
LABEL_51:
  if ( *v2 == 10 && !*(_QWORD *)(v44 + 24) )
    *(_DWORD *)(v44 + 8) &= ~2u;
  v33 = *(void **)(a1 + 464);
  if ( v33 )
  {
    ExFreePoolWithTag(v33, 0x6D536E52u);
    *(_QWORD *)(a1 + 464) = 0;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14002f280  push    rbp
0x14002f282  push    rbx
0x14002f283  push    rsi
0x14002f284  push    rdi
0x14002f285  push    r12
0x14002f287  push    r13
0x14002f289  push    r14
0x14002f28b  push    r15
0x14002f28d  mov     rbp, rsp
0x14002f290  sub     rsp, 48h
0x14002f294  mov     rdx, [rcx+38h]
0x14002f298  lea     r14, [rcx+1C0h]
0x14002f29f  mov     r15, [rcx+48h]
0x14002f2a3  mov     rbx, rcx
0x14002f2a6  mov     esi, [rdx+0E8h]
0x14002f2ac  mov     rax, [r15+28h]
0x14002f2b0  and     esi, 10h
0x14002f2b3  mov     r9, [rdx+78h]
0x14002f2b7  setnz   [rbp+arg_0]
0x14002f2bb  mov     [rbp+arg_10], r9
0x14002f2bf  cmp     dword ptr [r14], 0Ah
0x14002f2c3  mov     r13, [rax+28h]
0x14002f2c7  mov     rax, [rdx+88h]
0x14002f2ce  mov     [rbp+arg_18], rax
0x14002f2d2  mov     [rbp+arg_8], esi
0x14002f2d5  jnz     short loc_14002F306
0x14002f2d7  cmp     byte ptr [rcx+1DFh], 0
0x14002f2de  jz      short loc_14002F306
0x14002f2e0  mov     rsi, [rcx+1C8h]
0x14002f2e7  xorps   xmm0, xmm0
0x14002f2ea  movups  xmmword ptr [rbp+Src], xmm0
0x14002f2ee  mov     r12d, 2
0x14002f2f4  mov     edx, [rsi+10h]
0x14002f2f7  cmp     edx, r12d
0x14002f2fa  jbe     short loc_14002F333
0x14002f2fc  cmp     word ptr [rsi+14h], 3Ah ; ':'
0x14002f301  jnz     short loc_14002F333
0x14002f303  mov     esi, [rbp+arg_8]
0x14002f306  mov     rax, r14
0x14002f309  mov     r8d, [rax]
0x14002f30c  cmp     r8d, 0Ah
0x14002f310  jnz     loc_14002F4D4
0x14002f316  mov     rax, [r9+28h]
0x14002f31a  mov     rcx, [rax+58h]
0x14002f31e  test    byte ptr [rcx+2FCh], 20h
0x14002f325  jz      loc_14002F4D4
0x14002f32b  xor     r12d, r12d
0x14002f32e  jmp     loc_14002F4F0
0x14002f333  mov     rax, [r15+50h]
0x14002f337  movzx   ecx, word ptr [rax]
0x14002f33a  lea     eax, [rcx+rdx]
0x14002f33d  cmp     eax, ecx
0x14002f33f  jb      loc_14002F48F
0x14002f345  xor     r9d, r9d
0x14002f348  cmp     eax, 0FFFEh
0x14002f34d  ja      loc_14002F495
0x14002f353  add     eax, 18h
0x14002f356  cmp     eax, 18h
0x14002f359  jnb     short loc_14002F396
0x14002f35b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f362  lea     rax, WPP_GLOBAL_Control
0x14002f369  cmp     rcx, rax
0x14002f36c  jz      loc_14002F4CA
0x14002f372  mov     eax, [rcx+2Ch]
0x14002f375  test    al, 1
0x14002f377  jz      loc_14002F4CA
0x14002f37d  cmp     byte ptr [rcx+29h], 1
0x14002f381  jb      loc_14002F4CA
0x14002f387  lea     edx, [r9+0Dh]
0x14002f38b  mov     r9d, 0C0000095h
0x14002f391  jmp     loc_14002F4BA
0x14002f396  mov     edx, eax
0x14002f398  mov     ecx, 102h
0x14002f39d  mov     r8d, 6D536E52h
0x14002f3a3  call    cs:__imp_ExAllocatePool2
0x14002f3aa  nop     dword ptr [rax+rax+00h]
0x14002f3af  mov     rdi, rax
0x14002f3b2  test    rax, rax
0x14002f3b5  jnz     short loc_14002F3C1
0x14002f3b7  mov     eax, 0C000009Ah
0x14002f3bc  jmp     loc_14002F65D
0x14002f3c1  movups  xmm0, xmmword ptr [rsi]
0x14002f3c4  xor     r9d, r9d
0x14002f3c7  lea     rdx, [rbp+Src]
0x14002f3cb  xor     r8d, r8d
0x14002f3ce  movups  xmmword ptr [rax], xmm0
0x14002f3d1  movsd   xmm1, qword ptr [rsi+10h]
0x14002f3d6  movsd   qword ptr [rax+10h], xmm1
0x14002f3db  mov     rcx, [r15+50h]
0x14002f3df  call    cs:__imp_RxCrackPathName
0x14002f3e6  nop     dword ptr [rax+rax+00h]
0x14002f3eb  cmp     word ptr [rbp+Src], r12w
0x14002f3f0  jbe     short loc_14002F429
0x14002f3f2  movzx   r8d, word ptr [rbp+Src]; Size
0x14002f3f7  lea     rcx, [rdi+14h]; void *
0x14002f3fb  mov     rdx, [rbp+Src+8]; Src
0x14002f3ff  call    memmove
0x14002f404  movzx   eax, word ptr [rbp+Src]
0x14002f408  mov     edx, 5Ch ; '\'
0x14002f40d  shr     rax, 1
0x14002f410  mov     [rdi+rax*2+14h], dx
0x14002f415  movzx   eax, word ptr [rbp+Src]
0x14002f419  add     eax, r12d
0x14002f41c  add     [rdi+10h], eax
0x14002f41f  movzx   ecx, word ptr [rbp+Src]
0x14002f423  shr     ecx, 1
0x14002f425  inc     ecx
0x14002f427  jmp     short loc_14002F439
0x14002f429  mov     edx, 5Ch ; '\'
0x14002f42e  mov     [rdi+14h], dx
0x14002f432  add     [rdi+10h], r12d
0x14002f436  lea     ecx, [rdx-5Bh]
0x14002f439  mov     eax, [rsi+10h]
0x14002f43c  mov     r8d, [rdi+10h]
0x14002f440  cmp     eax, r12d
0x14002f443  jbe     short loc_14002F45F
0x14002f445  cmp     [rsi+14h], dx
0x14002f449  jnz     short loc_14002F45F
0x14002f44b  lea     eax, [r8-2]
0x14002f44f  mov     [rdi+10h], eax
0x14002f452  lea     rdx, [rsi+16h]
0x14002f456  mov     r8d, [rsi+10h]
0x14002f45a  sub     r8, r12
0x14002f45d  jmp     short loc_14002F466
0x14002f45f  mov     r8, rax; Size
0x14002f462  lea     rdx, [rsi+14h]; Src
0x14002f466  mov     eax, ecx
0x14002f468  add     rax, 0Ah
0x14002f46c  lea     rcx, [rdi+rax*2]; void *
0x14002f470  call    memmove
0x14002f475  mov     r9, [rbp+arg_10]
0x14002f479  lea     rax, [rbx+1C0h]
0x14002f480  mov     esi, [rbp+arg_8]
0x14002f483  mov     [rbx+1D0h], rdi
0x14002f48a  jmp     loc_14002F309
0x14002f48f  mov     r9d, 0C0000095h
0x14002f495  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f49c  lea     rax, WPP_GLOBAL_Control
0x14002f4a3  cmp     rcx, rax
0x14002f4a6  jz      short loc_14002F4CA
0x14002f4a8  mov     eax, [rcx+2Ch]
0x14002f4ab  test    al, 1
0x14002f4ad  jz      short loc_14002F4CA
0x14002f4af  cmp     byte ptr [rcx+29h], 1
0x14002f4b3  jb      short loc_14002F4CA
0x14002f4b5  mov     edx, 0Ch
0x14002f4ba  mov     rcx, [rcx+18h]
0x14002f4be  lea     r8, WPP_69214addf0f23a16977eb0c8dd6a2623_Traceguids
0x14002f4c5  call    WPP_SF_d
0x14002f4ca  mov     eax, 0C0000106h
0x14002f4cf  jmp     loc_14002F65D
0x14002f4d4  mov     edx, 1
0x14002f4d9  mov     rcx, rbx
0x14002f4dc  call    Smb2SetInformation
0x14002f4e1  mov     r12d, eax
0x14002f4e4  test    eax, eax
0x14002f4e6  js      loc_14002F61D
0x14002f4ec  mov     r9, [rbp+arg_10]
0x14002f4f0  mov     rcx, [r15+30h]
0x14002f4f4  xor     dil, dil
0x14002f4f7  mov     byte ptr [rcx+140h], 1
0x14002f4fe  mov     r8d, [r14]
0x14002f501  mov     edx, r8d
0x14002f504  sub     edx, 4
0x14002f507  jz      short loc_14002F533
0x14002f509  sub     edx, 6
0x14002f50c  jz      loc_14002F66F
0x14002f512  sub     edx, 1
0x14002f515  jz      loc_14002F66F
0x14002f51b  sub     edx, 8
0x14002f51e  jz      short loc_14002F533
0x14002f520  sub     edx, 1
0x14002f523  jz      short loc_14002F533
0x14002f525  sub     edx, 13h
0x14002f528  jz      short loc_14002F533
0x14002f52a  cmp     edx, 1
0x14002f52d  jnz     loc_14002F61D
0x14002f533  mov     r15, [rbp+arg_10]
0x14002f537  mov     rdx, [r15+28h]
0x14002f53b  mov     rcx, rbx
0x14002f53e  add     rdx, 178h
0x14002f545  call    Smb2InvalidateFileInfoCacheEntry
0x14002f54a  mov     rax, [rbx+38h]
0x14002f54e  xor     esi, esi
0x14002f550  mov     rdx, [r13+1A8h]
0x14002f557  add     rdx, 458h
0x14002f55e  mov     rcx, [rax+120h]
0x14002f565  test    rcx, rcx
0x14002f568  jz      short loc_14002F587
0x14002f56a  mov     rcx, [rcx+88h]
0x14002f571  test    rcx, rcx
0x14002f574  jz      short loc_14002F587
0x14002f576  mov     rax, [rax+88h]
0x14002f57d  nop
0x14002f57e  mov     esi, [rcx+58h]
0x14002f581  nop
0x14002f582  nop
0x14002f583  mov     eax, [rax+54h]
0x14002f586  nop
0x14002f587  mov     rcx, rbx
0x14002f58a  call    Smb2InvalidateSingleFileInDirInfoCache
0x14002f58f  mov     rax, [rbx+38h]
0x14002f593  mov     rcx, [rax+88h]
0x14002f59a  xchg    esi, [rcx+54h]
0x14002f59d  mov     esi, [rbp+arg_8]
0x14002f5a0  test    esi, esi
0x14002f5a2  jz      short loc_14002F5C4
0x14002f5a4  mov     r8, [r13+1A8h]
0x14002f5ab  mov     r9b, 1
0x14002f5ae  add     r8, 458h
0x14002f5b5  mov     byte ptr [rsp+48h+var_28], 1
0x14002f5ba  xor     edx, edx
0x14002f5bc  mov     rcx, rbx
0x14002f5bf  call    Smb2InvalidateDirInfoCacheEx
0x14002f5c4  test    dil, dil
0x14002f5c7  jz      short loc_14002F61D
0x14002f5c9  mov     rdx, [r15+28h]
0x14002f5cd  xor     r8d, r8d
0x14002f5d0  mov     r9b, [rbp+arg_0]
0x14002f5d4  add     rdx, 0C0h
0x14002f5db  mov     rcx, rbx
0x14002f5de  call    Smb2InvalidateFileIdentityCacheEntryEx
0x14002f5e3  mov     rdx, [r13+1A8h]
0x14002f5ea  mov     edi, 458h
0x14002f5ef  add     rdx, rdi
0x14002f5f2  mov     r8b, 1
0x14002f5f5  mov     rcx, rbx
0x14002f5f8  call    Smb2DeleteSingleFileInDirInfoCache
0x14002f5fd  test    esi, esi
0x14002f5ff  jz      short loc_14002F61D
0x14002f601  mov     r8, [r13+1A8h]
0x14002f608  mov     r9b, 1
0x14002f60b  add     r8, rdi
0x14002f60e  mov     byte ptr [rsp+48h+var_28], 1
0x14002f613  xor     edx, edx
0x14002f615  mov     rcx, rbx
0x14002f618  call    Smb2InvalidateDirInfoCacheEx
0x14002f61d  cmp     dword ptr [r14], 0Ah
0x14002f621  jnz     short loc_14002F632
0x14002f623  mov     rax, [rbp+arg_18]
0x14002f627  cmp     qword ptr [rax+18h], 0
0x14002f62c  jnz     short loc_14002F632
0x14002f62e  and     dword ptr [rax+8], 0FFFFFFFDh
0x14002f632  mov     rcx, [rbx+1D0h]; P
0x14002f639  test    rcx, rcx
0x14002f63c  jz      short loc_14002F65A
0x14002f63e  mov     edx, 6D536E52h; Tag
0x14002f643  call    cs:__imp_ExFreePoolWithTag
0x14002f64a  nop     dword ptr [rax+rax+00h]
0x14002f64f  mov     qword ptr [rbx+1D0h], 0
0x14002f65a  mov     eax, r12d
0x14002f65d  add     rsp, 48h
0x14002f661  pop     r15
0x14002f663  pop     r14
0x14002f665  pop     r13
0x14002f667  pop     r12
0x14002f669  pop     rdi
0x14002f66a  pop     rsi
0x14002f66b  pop     rbx
0x14002f66c  pop     rbp
0x14002f66d  retn
0x14002f66f  xorps   xmm0, xmm0
0x14002f672  movups  xmmword ptr [rbp+Src], xmm0
0x14002f676  cmp     r8d, 0Ah
0x14002f67a  jnz     short loc_14002F691
0x14002f67c  cmp     [rbx+1DFh], dil
0x14002f683  jz      short loc_14002F691
0x14002f685  mov     rcx, [rbx+1D0h]
0x14002f68c  test    rcx, rcx
0x14002f68f  jnz     short loc_14002F698
0x14002f691  mov     rcx, [rbx+1C8h]
0x14002f698  movzx   eax, word ptr [rcx+10h]
0x14002f69c  mov     word ptr [rbp+Src+2], ax
0x14002f6a0  mov     word ptr [rbp+Src], ax
0x14002f6a4  lea     rax, [rcx+14h]
0x14002f6a8  mov     [rbp+Src+8], rax
0x14002f6ac  cmp     r8d, 0Ah
0x14002f6b0  jnz     short loc_14002F72E
0x14002f6b2  mov     rdx, [r9+28h]
0x14002f6b6  lea     r8, [rbp+Src]
0x14002f6ba  mov     r9b, [rbp+arg_0]
0x14002f6be  add     rdx, 230h
0x14002f6c5  mov     rcx, rbx
0x14002f6c8  call    Smb2InvalidateFileNotFoundCacheEx
0x14002f6cd  mov     r15, [rbp+arg_10]
0x14002f6d1  lea     r8, [rbp+Src]
0x14002f6d5  mov     r9b, [rbp+arg_0]
0x14002f6d9  mov     rcx, rbx
0x14002f6dc  mov     rdx, [r15+28h]
0x14002f6e0  add     rdx, 0C0h
0x14002f6e7  call    Smb2InvalidateFileIdentityCacheEntryEx
0x14002f6ec  mov     r8, [r13+1A8h]
0x14002f6f3  lea     rdx, [rbp+Src]
0x14002f6f7  mov     edi, 458h
0x14002f6fc  mov     rcx, rbx
0x14002f6ff  add     r8, rdi
0x14002f702  call    Smb2InvalidateContainingDirInfoCacheEx
0x14002f707  test    esi, esi
0x14002f709  jz      short loc_14002F729
0x14002f70b  mov     r8, [r13+1A8h]
  ... truncated ...
```
