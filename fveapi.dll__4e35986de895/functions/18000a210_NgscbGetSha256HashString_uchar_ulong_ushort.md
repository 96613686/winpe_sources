# NgscbGetSha256HashString(uchar *,ulong,ushort * *)

- ea: `0x18000a210`
- end: `0x18000a645`
- name: `?NgscbGetSha256HashString@@YAJPEAEKPEAPEAG@Z`
- size: `1077`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180037794`

## callees

- `0x1800090c0`
- `0x18000a210`
- `0x18000aae0`
- `0x180018b10`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a376`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a376`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a38d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a38d`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000a298`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000a298`
- `bcrypt!BCryptDestroyHash` at `0x18000a3ff`
- `bcrypt!BCryptDestroyHash` at `0x18000a3ff`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000a41c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000a41c`
- `bcrypt!BCryptCreateHash` at `0x18000a2cb`
- `bcrypt!BCryptCreateHash` at `0x18000a2cb`
- `bcrypt!BCryptHashData` at `0x18000a2ed`
- `bcrypt!BCryptHashData` at `0x18000a2ed`
- `bcrypt!BCryptFinishHash` at `0x18000a314`
- `bcrypt!BCryptFinishHash` at `0x18000a314`

## pseudocode

```c
__int64 __fastcall NgscbGetSha256HashString(PUCHAR pbInput, ULONG cbInput, unsigned __int16 **a3)
{
  NTSTATUS v6; // eax
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  NTSTATUS v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rbx
  unsigned int v12; // eax
  unsigned int v13; // esi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rdi
  __int64 v17; // rcx
  unsigned __int16 *v18; // rdx
  unsigned __int16 *v19; // r8
  unsigned __int16 *v20; // rcx
  unsigned int v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  HANDLE v29; // rax
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-F8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-F0h] BYREF
  UCHAR pbOutput[16]; // [rsp+50h] [rbp-E8h] BYREF
  __int128 v33; // [rsp+60h] [rbp-D8h]
  unsigned __int16 v34[72]; // [rsp+70h] [rbp-C8h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  *(_OWORD *)pbOutput = 0;
  v33 = 0;
  memset_0(v34, 0, 0x82u);
  if ( !a3 )
  {
    v13 = -2147467261;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return v13;
    v24 = 98;
    goto LABEL_57;
  }
  *a3 = 0;
  if ( !pbInput || !cbInput )
  {
    v13 = -2147024809;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return v13;
    v24 = 99;
    goto LABEL_57;
  }
  v6 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( v6 < 0 )
  {
    v22 = FromNtStatus(v6);
    v13 = v22;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_22;
    v24 = 100;
    v25 = v22;
    goto LABEL_58;
  }
  v7 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
  if ( v7 < 0 )
  {
    v27 = FromNtStatus(v7);
    v13 = v27;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_22;
    v24 = 101;
    v25 = v27;
    goto LABEL_58;
  }
  v8 = BCryptHashData(phHash, pbInput, cbInput, 0);
  if ( v8 < 0 )
  {
    v28 = FromNtStatus(v8);
    v13 = v28;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_22;
    v24 = 102;
    v25 = v28;
    goto LABEL_58;
  }
  v9 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
  if ( v9 < 0 )
  {
    v26 = FromNtStatus(v9);
    v13 = v26;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_22;
    v24 = 103;
    v25 = v26;
    goto LABEL_58;
  }
  v10 = 0;
  v11 = 65;
  while ( v10 < 0x20 && 2 * v10 < 0x41 )
  {
    v12 = StringCchPrintfW(&v34[2 * v10], 65LL - 2 * v10, L"%02X", pbOutput[v10]);
    v13 = v12;
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v12);
      if ( (v13 & 0x80000000) != 0 )
        goto LABEL_22;
    }
    ++v10;
  }
  ProcessHeap = GetProcessHeap();
  v15 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x82u);
  v16 = v15;
  if ( v15 )
  {
    v17 = 2147483646;
    v18 = v34;
    v19 = v15;
    do
    {
      if ( !v17 )
        break;
      if ( !*v18 )
        break;
      *v19++ = *v18++;
      --v17;
      --v11;
    }
    while ( v11 );
    v20 = v19 - 1;
    v13 = -2147024774;
    if ( v11 )
    {
      v20 = v19;
      v13 = 0;
    }
    *v20 = 0;
    if ( v11 )
    {
      *a3 = v15;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v13);
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v16);
    }
    goto LABEL_22;
  }
  v23 = WPP_GLOBAL_Control;
  v13 = -2147024882;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v24 = 105;
LABEL_57:
    v25 = v13;
LABEL_58:
    WPP_SF_d(v23[2], v24, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v25);
  }
LABEL_22:
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v13;
}

```

## disassembly

```asm
0x18000a210  mov     [rsp+arg_18], rbx
0x18000a215  push    rbp
0x18000a216  push    rsi
0x18000a217  push    rdi
0x18000a218  push    r14
0x18000a21a  push    r15
0x18000a21c  sub     rsp, 110h
0x18000a223  mov     rax, cs:__security_cookie
0x18000a22a  xor     rax, rsp
0x18000a22d  mov     [rsp+138h+var_38], rax
0x18000a235  xorps   xmm0, xmm0
0x18000a238  mov     r14, r8
0x18000a23b  mov     edi, edx
0x18000a23d  mov     rbx, rcx
0x18000a240  xor     r15d, r15d
0x18000a243  lea     rcx, [rsp+138h+var_C8]; void *
0x18000a248  xor     edx, edx; Val
0x18000a24a  mov     [rsp+138h+phAlgorithm], r15
0x18000a24f  mov     r8d, 82h; Size
0x18000a255  mov     [rsp+138h+phHash], r15
0x18000a25a  movups  xmmword ptr [rsp+138h+pbOutput], xmm0
0x18000a25f  movups  [rsp+138h+var_D8], xmm0
0x18000a264  call    memset_0
0x18000a269  test    r14, r14
0x18000a26c  jz      loc_18000A4EF
0x18000a272  mov     [r14], r15
0x18000a275  test    rbx, rbx
0x18000a278  jz      loc_18000A602
0x18000a27e  test    edi, edi
0x18000a280  jz      loc_18000A602
0x18000a286  xor     r9d, r9d; dwFlags
0x18000a289  lea     rdx, pszAlgId; "SHA256"
0x18000a290  xor     r8d, r8d; pszImplementation
0x18000a293  lea     rcx, [rsp+138h+phAlgorithm]; phAlgorithm
0x18000a298  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000a29f  nop     dword ptr [rax+rax+00h]
0x18000a2a4  test    eax, eax
0x18000a2a6  js      loc_18000A452
0x18000a2ac  mov     rcx, [rsp+138h+phAlgorithm]; hAlgorithm
0x18000a2b1  lea     rdx, [rsp+138h+phHash]; phHash
0x18000a2b6  mov     [rsp+138h+dwFlags], r15d; dwFlags
0x18000a2bb  xor     r9d, r9d; cbHashObject
0x18000a2be  mov     [rsp+138h+cbSecret], r15d; cbSecret
0x18000a2c3  xor     r8d, r8d; pbHashObject
0x18000a2c6  mov     [rsp+138h+pbSecret], r15; pbSecret
0x18000a2cb  call    cs:__imp_BCryptCreateHash
0x18000a2d2  nop     dword ptr [rax+rax+00h]
0x18000a2d7  test    eax, eax
0x18000a2d9  js      loc_18000A51F
0x18000a2df  mov     rcx, [rsp+138h+phHash]; hHash
0x18000a2e4  xor     r9d, r9d; dwFlags
0x18000a2e7  mov     r8d, edi; cbInput
0x18000a2ea  mov     rdx, rbx; pbInput
0x18000a2ed  call    cs:__imp_BCryptHashData
0x18000a2f4  nop     dword ptr [rax+rax+00h]
0x18000a2f9  test    eax, eax
0x18000a2fb  js      loc_18000A556
0x18000a301  mov     rcx, [rsp+138h+phHash]; hHash
0x18000a306  lea     rdx, [rsp+138h+pbOutput]; pbOutput
0x18000a30b  xor     r9d, r9d; dwFlags
0x18000a30e  mov     r8d, 20h ; ' '; cbOutput
0x18000a314  call    cs:__imp_BCryptFinishHash
0x18000a31b  nop     dword ptr [rax+rax+00h]
0x18000a320  test    eax, eax
0x18000a322  js      loc_18000A481
0x18000a328  mov     edi, r15d
0x18000a32b  lea     rbp, WPP_GLOBAL_Control
0x18000a332  mov     ebx, 41h ; 'A'
0x18000a337  cmp     edi, 20h ; ' '
0x18000a33a  jnb     short loc_18000A376
0x18000a33c  lea     eax, [rdi+rdi]
0x18000a33f  cmp     eax, ebx
0x18000a341  jnb     short loc_18000A376
0x18000a343  mov     ecx, eax
0x18000a345  lea     r8, a02x_0; "%02X"
0x18000a34c  mov     eax, edi
0x18000a34e  mov     rdx, rbx
0x18000a351  sub     rdx, rcx; unsigned __int64
0x18000a354  movzx   r9d, [rsp+rax+138h+pbOutput]
0x18000a35a  lea     rax, [rsp+138h+var_C8]
0x18000a35f  lea     rcx, [rax+rcx*2]; unsigned __int16 *
0x18000a363  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a368  mov     esi, eax
0x18000a36a  test    eax, eax
0x18000a36c  jnz     loc_18000A4B8
0x18000a372  inc     edi
0x18000a374  jmp     short loc_18000A337
0x18000a376  call    cs:__imp_GetProcessHeap
0x18000a37d  nop     dword ptr [rax+rax+00h]
0x18000a382  xor     edx, edx; dwFlags
0x18000a384  mov     r8d, 82h; dwBytes
0x18000a38a  mov     rcx, rax; hHeap
0x18000a38d  call    cs:__imp_HeapAlloc
0x18000a394  nop     dword ptr [rax+rax+00h]
0x18000a399  mov     rdi, rax
0x18000a39c  test    rax, rax
0x18000a39f  jz      loc_18000A58D
0x18000a3a5  mov     ecx, 7FFFFFFEh
0x18000a3aa  lea     rdx, [rsp+138h+var_C8]
0x18000a3af  mov     r8, rax
0x18000a3b2  test    rcx, rcx
0x18000a3b5  jz      short loc_18000A3D4
0x18000a3b7  movzx   eax, word ptr [rdx]
0x18000a3ba  test    ax, ax
0x18000a3bd  jz      short loc_18000A3D4
0x18000a3bf  mov     [r8], ax
0x18000a3c3  add     rdx, 2
0x18000a3c7  add     r8, 2
0x18000a3cb  dec     rcx
0x18000a3ce  sub     rbx, 1
0x18000a3d2  jnz     short loc_18000A3B2
0x18000a3d4  test    rbx, rbx
0x18000a3d7  lea     rcx, [r8-2]
0x18000a3db  mov     esi, 8007007Ah
0x18000a3e0  cmovnz  rcx, r8
0x18000a3e4  cmovnz  esi, r15d
0x18000a3e8  mov     [rcx], r15w
0x18000a3ec  jz      loc_18000A5B3
0x18000a3f2  mov     [r14], rdi
0x18000a3f5  mov     rcx, [rsp+138h+phHash]; hHash
0x18000a3fa  test    rcx, rcx
0x18000a3fd  jz      short loc_18000A410
0x18000a3ff  call    cs:__imp_BCryptDestroyHash
0x18000a406  nop     dword ptr [rax+rax+00h]
0x18000a40b  mov     [rsp+138h+phHash], r15
0x18000a410  mov     rcx, [rsp+138h+phAlgorithm]; hAlgorithm
0x18000a415  test    rcx, rcx
0x18000a418  jz      short loc_18000A428
0x18000a41a  xor     edx, edx; dwFlags
0x18000a41c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000a423  nop     dword ptr [rax+rax+00h]
0x18000a428  mov     eax, esi
0x18000a42a  mov     rcx, [rsp+138h+var_38]
0x18000a432  xor     rcx, rsp; StackCookie
0x18000a435  call    __security_check_cookie
0x18000a43a  mov     rbx, [rsp+138h+arg_18]
0x18000a442  add     rsp, 110h
0x18000a449  pop     r15
0x18000a44b  pop     r14
0x18000a44d  pop     rdi
0x18000a44e  pop     rsi
0x18000a44f  pop     rbp
0x18000a450  retn
0x18000a452  mov     ecx, eax; int
0x18000a454  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18000a459  mov     esi, eax
0x18000a45b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a462  lea     rbp, WPP_GLOBAL_Control
0x18000a469  cmp     rcx, rbp
0x18000a46c  jz      short loc_18000A3F5
0x18000a46e  test    byte ptr [rcx+1Ch], 40h
0x18000a472  jz      short loc_18000A3F5
0x18000a474  mov     edx, 64h ; 'd'
0x18000a479  mov     r9d, eax
0x18000a47c  jmp     loc_18000A630
0x18000a481  mov     ecx, eax; int
0x18000a483  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18000a488  mov     esi, eax
0x18000a48a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a491  lea     rbp, WPP_GLOBAL_Control
0x18000a498  cmp     rcx, rbp
0x18000a49b  jz      loc_18000A3F5
0x18000a4a1  test    byte ptr [rcx+1Ch], 40h
0x18000a4a5  jz      loc_18000A3F5
0x18000a4ab  mov     edx, 67h ; 'g'
0x18000a4b0  mov     r9d, eax
0x18000a4b3  jmp     loc_18000A630
0x18000a4b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4bf  cmp     rcx, rbp
0x18000a4c2  jz      short loc_18000A4E2
0x18000a4c4  test    byte ptr [rcx+1Ch], 40h
0x18000a4c8  jz      short loc_18000A4E2
0x18000a4ca  mov     rcx, [rcx+10h]
0x18000a4ce  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18000a4d5  mov     edx, 68h ; 'h'
0x18000a4da  mov     r9d, esi
0x18000a4dd  call    WPP_SF_d
0x18000a4e2  test    esi, esi
0x18000a4e4  jns     loc_18000A372
0x18000a4ea  jmp     loc_18000A3F5
0x18000a4ef  mov     esi, 80004003h
0x18000a4f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4fb  lea     rbp, WPP_GLOBAL_Control
0x18000a502  cmp     rcx, rbp
0x18000a505  jz      loc_18000A428
0x18000a50b  test    byte ptr [rcx+1Ch], 40h
0x18000a50f  jz      loc_18000A428
0x18000a515  mov     edx, 62h ; 'b'
0x18000a51a  jmp     loc_18000A62D
0x18000a51f  mov     ecx, eax; int
0x18000a521  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18000a526  mov     esi, eax
0x18000a528  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a52f  lea     rbp, WPP_GLOBAL_Control
0x18000a536  cmp     rcx, rbp
0x18000a539  jz      loc_18000A3F5
0x18000a53f  test    byte ptr [rcx+1Ch], 40h
0x18000a543  jz      loc_18000A3F5
0x18000a549  mov     edx, 65h ; 'e'
0x18000a54e  mov     r9d, eax
0x18000a551  jmp     loc_18000A630
0x18000a556  mov     ecx, eax; int
0x18000a558  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18000a55d  mov     esi, eax
0x18000a55f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a566  lea     rbp, WPP_GLOBAL_Control
0x18000a56d  cmp     rcx, rbp
0x18000a570  jz      loc_18000A3F5
0x18000a576  test    byte ptr [rcx+1Ch], 40h
0x18000a57a  jz      loc_18000A3F5
0x18000a580  mov     edx, 66h ; 'f'
0x18000a585  mov     r9d, eax
0x18000a588  jmp     loc_18000A630
0x18000a58d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a594  mov     esi, 8007000Eh
0x18000a599  cmp     rcx, rbp
0x18000a59c  jz      loc_18000A3F5
0x18000a5a2  test    byte ptr [rcx+1Ch], 40h
0x18000a5a6  jz      loc_18000A3F5
0x18000a5ac  mov     edx, 69h ; 'i'
0x18000a5b1  jmp     short loc_18000A62D
0x18000a5b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5ba  cmp     rcx, rbp
0x18000a5bd  jz      short loc_18000A5DD
0x18000a5bf  test    byte ptr [rcx+1Ch], 40h
0x18000a5c3  jz      short loc_18000A5DD
0x18000a5c5  mov     rcx, [rcx+10h]
0x18000a5c9  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18000a5d0  mov     edx, 6Ah ; 'j'
0x18000a5d5  mov     r9d, esi
0x18000a5d8  call    WPP_SF_d
0x18000a5dd  call    cs:__imp_GetProcessHeap
0x18000a5e4  nop     dword ptr [rax+rax+00h]
0x18000a5e9  mov     r8, rdi; lpMem
0x18000a5ec  xor     edx, edx; dwFlags
0x18000a5ee  mov     rcx, rax; hHeap
0x18000a5f1  call    cs:__imp_HeapFree
0x18000a5f8  nop     dword ptr [rax+rax+00h]
0x18000a5fd  jmp     loc_18000A3F5
0x18000a602  mov     esi, 80070057h
0x18000a607  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a60e  lea     rbp, WPP_GLOBAL_Control
0x18000a615  cmp     rcx, rbp
0x18000a618  jz      loc_18000A428
0x18000a61e  test    byte ptr [rcx+1Ch], 40h
0x18000a622  jz      loc_18000A428
0x18000a628  mov     edx, 63h ; 'c'
0x18000a62d  mov     r9d, esi
0x18000a630  mov     rcx, [rcx+10h]
0x18000a634  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18000a63b  call    WPP_SF_d
0x18000a640  jmp     loc_18000A3F5
```
