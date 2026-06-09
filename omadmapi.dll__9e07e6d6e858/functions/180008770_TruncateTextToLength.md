# TruncateTextToLength

- ea: `0x180008770`
- end: `0x180008975`
- name: `TruncateTextToLength`
- size: `517`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800031b0`
- `0x180006cd4`
- `0x180006d9c`
- `0x180008770`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008942`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008942`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000881f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000881f`
- `DMCmnUtils!CopyString` at `0x180008917`
- `DMCmnUtils!CopyString` at `0x180008917`

## pseudocode

```c
__int64 __fastcall TruncateTextToLength(unsigned __int16 *a1, int a2, unsigned int a3, HLOCAL *a4)
{
  unsigned __int64 v4; // r15
  unsigned __int16 *v8; // rax
  __int64 v9; // r8
  signed int v10; // ebx
  unsigned int v11; // edx
  unsigned int v12; // esi
  _WORD *v13; // rax
  _WORD *v14; // rdx
  unsigned int v15; // r15d
  int v16; // edi
  unsigned __int64 v17; // r9
  unsigned __int16 *v18; // r8
  unsigned __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // rax
  unsigned __int16 *v22; // rcx
  __int64 v23; // r8
  _WORD *v24; // rcx
  HLOCAL hMem; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 v27[4]; // [rsp+28h] [rbp-18h] BYREF

  v4 = a3;
  hMem = 0;
  *(_QWORD *)v27 = 0x2E002E002ELL;
  if ( !a1 )
  {
    v11 = -2147024809;
LABEL_32:
    v10 = v11;
    goto LABEL_33;
  }
  v8 = a1;
  v9 = 0x7FFFFFFF;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v9;
  }
  while ( v9 );
  v10 = -2147024809;
  v11 = v9 == 0 ? 0x80070057 : 0;
  if ( !v9 )
    goto LABEL_32;
  if ( ((0x7FFFFFFF - v9) & (unsigned __int64)-(__int64)(v9 != 0)) <= v4 )
  {
    v20 = CopyString(a1, 0xFFFFFFFF, (unsigned __int16 **)&hMem);
LABEL_29:
    v10 = v20;
    if ( v20 >= 0 )
    {
      *a4 = hMem;
      hMem = 0;
    }
    goto LABEL_33;
  }
  v12 = v4 + 1;
  if ( (int)v4 + 1 < 0 )
  {
    v10 = -2147467259;
    goto LABEL_33;
  }
  v13 = LocalAlloc(0x40u, 2 * v12);
  hMem = v13;
  v14 = v13;
  if ( !v13 )
  {
    v10 = -2147024882;
    goto LABEL_33;
  }
  v15 = v4 - 4;
  v16 = a2 - 1;
  if ( v16 )
  {
    if ( v16 != 1 )
    {
      v10 = -2147418113;
      goto LABEL_33;
    }
    v10 = StringCchCopyNW((unsigned __int16 *)hMem, v12, a1, v15);
    if ( v10 < 0 )
      goto LABEL_33;
    v17 = 4;
    v18 = v27;
    v19 = v12;
    goto LABEL_15;
  }
  if ( v12 )
  {
    if ( v12 > 0x7FFFFFFFuLL )
    {
      *v13 = 0;
      goto LABEL_33;
    }
    v21 = 2147483646;
    v22 = v27;
    v23 = v12;
    do
    {
      if ( !v21 )
        break;
      if ( !*v22 )
        break;
      *v14++ = *v22++;
      --v21;
      --v23;
    }
    while ( v23 );
    v24 = v14 - 1;
    v10 = v23 == 0 ? 0x8007007A : 0;
    if ( v23 )
      v24 = v14;
    *v24 = 0;
    if ( v23 )
    {
      v17 = v15;
      v18 = a1;
      v19 = v12;
LABEL_15:
      v20 = StringCchCatNW((unsigned __int16 *)hMem, v19, v18, v17);
      goto LABEL_29;
    }
  }
LABEL_33:
  LocalFree(hMem);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180008770  mov     [rsp-38h+arg_8], rbx
0x180008775  push    rbp
0x180008776  push    rsi
0x180008777  push    rdi
0x180008778  push    r12
0x18000877a  push    r13
0x18000877c  push    r14
0x18000877e  push    r15
0x180008780  mov     rbp, rsp
0x180008783  sub     rsp, 40h
0x180008787  mov     rax, cs:__security_cookie
0x18000878e  xor     rax, rsp
0x180008791  mov     [rbp+var_10], rax
0x180008795  xor     r13d, r13d
0x180008798  mov     r15d, r8d
0x18000879b  mov     [rbp+hMem], r13
0x18000879f  mov     rax, 2E002E002Eh
0x1800087a9  mov     qword ptr [rbp+var_18], rax
0x1800087ad  mov     r12, r9
0x1800087b0  mov     edi, edx
0x1800087b2  mov     r14, rcx
0x1800087b5  test    rcx, rcx
0x1800087b8  jz      loc_180008937
0x1800087be  mov     ecx, 7FFFFFFFh
0x1800087c3  mov     rax, r14
0x1800087c6  mov     r8d, ecx
0x1800087c9  cmp     [rax], r13w
0x1800087cd  jz      short loc_1800087D9
0x1800087cf  add     rax, 2
0x1800087d3  sub     r8, 1
0x1800087d7  jnz     short loc_1800087C9
0x1800087d9  mov     rax, r8
0x1800087dc  mov     ebx, 80070057h
0x1800087e1  neg     rax
0x1800087e4  mov     rax, r8
0x1800087e7  sbb     edx, edx
0x1800087e9  sub     rcx, r8
0x1800087ec  not     edx
0x1800087ee  and     edx, ebx
0x1800087f0  neg     rax
0x1800087f3  sbb     r9, r9
0x1800087f6  and     r9, rcx
0x1800087f9  test    r8, r8
0x1800087fc  jz      loc_18000893C
0x180008802  cmp     r9, r15
0x180008805  jbe     loc_18000890D
0x18000880b  lea     esi, [r15+1]
0x18000880f  test    esi, esi
0x180008811  js      loc_180008906
0x180008817  lea     edx, [rsi+rsi]; uBytes
0x18000881a  mov     ecx, 40h ; '@'; uFlags
0x18000881f  call    cs:__imp_LocalAlloc
0x180008826  nop     dword ptr [rax+rax+00h]
0x18000882b  mov     [rbp+hMem], rax
0x18000882f  mov     rdx, rax
0x180008832  test    rax, rax
0x180008835  jnz     short loc_180008841
0x180008837  mov     ebx, 8007000Eh
0x18000883c  jmp     loc_18000893E
0x180008841  add     r15d, 0FFFFFFFCh
0x180008845  sub     edi, 1
0x180008848  jz      short loc_180008890
0x18000884a  cmp     edi, 1
0x18000884d  jz      short loc_180008859
0x18000884f  mov     ebx, 8000FFFFh
0x180008854  jmp     loc_18000893E
0x180008859  mov     rcx, [rbp+hMem]; unsigned __int16 *
0x18000885d  mov     r8, r14; unsigned __int16 *
0x180008860  mov     r9d, r15d; unsigned __int64
0x180008863  mov     edx, esi; unsigned __int64
0x180008865  mov     edi, esi
0x180008867  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000886c  mov     ebx, eax
0x18000886e  test    eax, eax
0x180008870  js      loc_18000893E
0x180008876  mov     r9d, 4; unsigned __int64
0x18000887c  lea     r8, [rbp+var_18]; unsigned __int16 *
0x180008880  mov     edx, edi; unsigned __int64
0x180008882  mov     rcx, [rbp+hMem]; unsigned __int16 *
0x180008886  call    ?StringCchCatNW@@YAJPEAG_KPEBG1@Z; StringCchCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000888b  jmp     loc_180008923
0x180008890  mov     r10d, esi
0x180008893  test    esi, esi
0x180008895  jz      loc_18000893E
0x18000889b  cmp     r10, 7FFFFFFFh
0x1800088a2  ja      short loc_180008900
0x1800088a4  mov     eax, 7FFFFFFEh
0x1800088a9  lea     rcx, [rbp+var_18]
0x1800088ad  mov     r8d, r10d
0x1800088b0  test    rax, rax
0x1800088b3  jz      short loc_1800088D4
0x1800088b5  movzx   r9d, word ptr [rcx]
0x1800088b9  test    r9w, r9w
0x1800088bd  jz      short loc_1800088D4
0x1800088bf  mov     [rdx], r9w
0x1800088c3  add     rcx, 2
0x1800088c7  add     rdx, 2
0x1800088cb  dec     rax
0x1800088ce  sub     r8, 1
0x1800088d2  jnz     short loc_1800088B0
0x1800088d4  mov     rax, r8
0x1800088d7  lea     rcx, [rdx-2]
0x1800088db  neg     rax
0x1800088de  sbb     ebx, ebx
0x1800088e0  not     ebx
0x1800088e2  and     ebx, 8007007Ah
0x1800088e8  test    r8, r8
0x1800088eb  cmovnz  rcx, rdx
0x1800088ef  mov     [rcx], r13w
0x1800088f3  jz      short loc_18000893E
0x1800088f5  mov     r9d, r15d
0x1800088f8  mov     r8, r14
0x1800088fb  mov     rdx, r10
0x1800088fe  jmp     short loc_180008882
0x180008900  mov     [rax], r13w
0x180008904  jmp     short loc_18000893E
0x180008906  mov     ebx, 80004005h
0x18000890b  jmp     short loc_18000893E
0x18000890d  lea     r8, [rbp+hMem]
0x180008911  or      edx, 0FFFFFFFFh
0x180008914  mov     rcx, r14
0x180008917  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18000891e  nop     dword ptr [rax+rax+00h]
0x180008923  mov     ebx, eax
0x180008925  test    eax, eax
0x180008927  js      short loc_18000893E
0x180008929  mov     rax, [rbp+hMem]
0x18000892d  mov     [r12], rax
0x180008931  mov     [rbp+hMem], r13
0x180008935  jmp     short loc_18000893E
0x180008937  mov     edx, 80070057h
0x18000893c  mov     ebx, edx
0x18000893e  mov     rcx, [rbp+hMem]; hMem
0x180008942  call    cs:__imp_LocalFree
0x180008949  nop     dword ptr [rax+rax+00h]
0x18000894e  mov     eax, ebx
0x180008950  mov     rcx, [rbp+var_10]
0x180008954  xor     rcx, rsp; StackCookie
0x180008957  call    __security_check_cookie
0x18000895c  mov     rbx, [rsp+40h+arg_8]
0x180008964  add     rsp, 40h
0x180008968  pop     r15
0x18000896a  pop     r14
0x18000896c  pop     r13
0x18000896e  pop     r12
0x180008970  pop     rdi
0x180008971  pop     rsi
0x180008972  pop     rbp
0x180008973  retn
```
