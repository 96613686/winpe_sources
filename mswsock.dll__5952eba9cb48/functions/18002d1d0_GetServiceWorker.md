# GetServiceWorker

- ea: `0x18002d1d0`
- end: `0x18002d40e`
- name: `GetServiceWorker`
- size: `574`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x18002d0d0`
- `0x18002d190`

## callees

- `0x18002d1d0`
- `0x18002d66c`
- `0x18002ff9c`
- `0x180030078`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002d3a2`
- `ntdll!RtlFreeHeap` at `0x18002d3a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d36b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d3b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d3d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d3e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d36b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d3b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d3d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d3e6`

## pseudocode

```c
__int64 __fastcall GetServiceWorker(
        unsigned int a1,
        __int64 a2,
        const wchar_t *a3,
        unsigned int a4,
        __int64 *a5,
        _DWORD *a6,
        __int64 a7,
        int a8)
{
  int v8; // edi
  DWORD v11; // ecx
  _DWORD *v12; // rbx
  DWORD v13; // eax
  __int64 *v14; // rsi
  unsigned int v15; // eax
  void *HeapRoutine; // r12
  unsigned int v17; // ebp
  unsigned __int64 v18; // rax
  __int64 v19; // rsi
  int v20; // r13d
  __int64 (__fastcall *v21)(__int64, const wchar_t *, _QWORD, _QWORD, void *, unsigned int *); // rax
  DWORD v22; // eax
  unsigned int v24; // [rsp+40h] [rbp-58h] BYREF
  _DWORD v25[3]; // [rsp+44h] [rbp-54h] BYREF
  __int64 v26[9]; // [rsp+50h] [rbp-48h] BYREF

  v8 = 0;
  v24 = 0;
  if ( a7 )
  {
    v11 = 50;
    goto LABEL_31;
  }
  if ( !a2 || (v12 = a6) == 0 || !a3 )
  {
    v11 = 87;
LABEL_31:
    SetLastError(v11);
    return 0xFFFFFFFFLL;
  }
  if ( !NspInitialized )
  {
    v13 = InitializeNsp();
    if ( v13 )
    {
      v11 = v13;
      goto LABEL_31;
    }
  }
  v14 = a5;
  if ( !a5 )
  {
    v14 = &a7;
    *a6 = 0;
  }
  v15 = *a6;
  if ( *a6 < 0x1000u )
    v15 = 4096;
  v24 = v15;
  HeapRoutine = (void *)SockAllocateHeapRoutine(SockPrivateHeap, 0, v15);
  if ( !HeapRoutine )
  {
    v11 = 8;
    goto LABEL_31;
  }
  v17 = 0;
  v18 = (unsigned __int64)v14 + (unsigned int)*a6;
  v26[0] = (__int64)v14;
  v19 = NameSpaceListHead;
  *(_QWORD *)&v25[1] = v18 & 0xFFFFFFFFFFFFFFF8uLL;
  v20 = 0;
  v25[0] = 0;
  if ( (__int64 *)NameSpaceListHead == &NameSpaceListHead )
    goto LABEL_25;
  do
  {
    if ( (unsigned int)IsValidNameSpace(a1, v19) )
    {
      v21 = *(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, void *, unsigned int *))(v19 + 40);
      if ( v21 )
      {
        v20 = 1;
        v22 = v21(a2, a3, a4, (unsigned int)a8, HeapRoutine, &v24);
        if ( v22 )
          goto LABEL_22;
        v22 = PackBuffer(
                *(_DWORD *)(v19 + 52),
                a2,
                (int)HeapRoutine,
                a8,
                a3,
                (__int64)v26,
                (__int64)&v25[1],
                (__int64)v25);
        if ( !v22 )
        {
          ++v17;
          goto LABEL_23;
        }
        if ( v22 != 122 )
LABEL_22:
          SetLastError(v22);
      }
    }
LABEL_23:
    v19 = *(_QWORD *)v19;
  }
  while ( (__int64 *)v19 != &NameSpaceListHead );
  v8 = v25[0];
  v12 = a6;
LABEL_25:
  RtlFreeHeap(SockPrivateHeap, 0, HeapRoutine);
  if ( v8 )
  {
    SetLastError(0x7Au);
    *v12 += v8;
    return 0xFFFFFFFFLL;
  }
  if ( !v20 )
    SetLastError(0x4DBu);
  return v17;
}

```

## disassembly

```asm
0x18002d1d0  mov     rax, rsp
0x18002d1d3  mov     [rax+10h], rbx
0x18002d1d7  mov     [rax+20h], r9d
0x18002d1db  mov     [rax+8], ecx
0x18002d1de  push    rbp
0x18002d1df  push    rsi
0x18002d1e0  push    rdi
0x18002d1e1  push    r12
0x18002d1e3  push    r13
0x18002d1e5  push    r14
0x18002d1e7  push    r15
0x18002d1e9  sub     rsp, 60h
0x18002d1ed  xor     edi, edi
0x18002d1ef  mov     r15, r8
0x18002d1f2  mov     r14, rdx
0x18002d1f5  mov     [rax-58h], edi
0x18002d1f8  cmp     [rsp+98h+arg_30], rdi
0x18002d200  jz      short loc_18002D20A
0x18002d202  lea     ecx, [rdi+32h]
0x18002d205  jmp     loc_18002D3E6
0x18002d20a  test    r14, r14
0x18002d20d  jz      loc_18002D3E1
0x18002d213  mov     rbx, [rsp+98h+arg_28]
0x18002d21b  test    rbx, rbx
0x18002d21e  jz      loc_18002D3E1
0x18002d224  test    r15, r15
0x18002d227  jz      loc_18002D3E1
0x18002d22d  cmp     cs:NspInitialized, edi
0x18002d233  jnz     short loc_18002D245
0x18002d235  call    InitializeNsp
0x18002d23a  test    eax, eax
0x18002d23c  jz      short loc_18002D245
0x18002d23e  mov     ecx, eax
0x18002d240  jmp     loc_18002D3E6
0x18002d245  mov     rsi, [rsp+98h+arg_20]
0x18002d24d  test    rsi, rsi
0x18002d250  jnz     short loc_18002D25C
0x18002d252  lea     rsi, [rsp+98h+arg_30]
0x18002d25a  mov     [rbx], edi
0x18002d25c  mov     eax, [rbx]
0x18002d25e  mov     ecx, 1000h
0x18002d263  cmp     eax, ecx
0x18002d265  cmovb   eax, ecx
0x18002d268  mov     rcx, cs:SockPrivateHeap
0x18002d26f  mov     [rsp+98h+var_58], eax
0x18002d273  xor     edx, edx
0x18002d275  mov     r8d, eax
0x18002d278  mov     rax, cs:SockAllocateHeapRoutine
0x18002d27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d284  mov     r12, rax
0x18002d287  test    rax, rax
0x18002d28a  jnz     short loc_18002D294
0x18002d28c  lea     ecx, [rax+8]
0x18002d28f  jmp     loc_18002D3E6
0x18002d294  mov     eax, [rbx]
0x18002d296  mov     ebp, edi
0x18002d298  add     rax, rsi
0x18002d29b  mov     [rsp+98h+var_48], rsi
0x18002d2a0  mov     rsi, cs:NameSpaceListHead
0x18002d2a7  and     rax, 0FFFFFFFFFFFFFFF8h
0x18002d2ab  mov     qword ptr [rsp+98h+var_54+4], rax
0x18002d2b0  mov     r13d, edi
0x18002d2b3  lea     rax, NameSpaceListHead
0x18002d2ba  mov     dword ptr [rsp+98h+var_54], edi
0x18002d2be  cmp     rsi, rax
0x18002d2c1  jz      loc_18002D396
0x18002d2c7  mov     edi, [rsp+98h+arg_0]
0x18002d2ce  mov     ebx, [rsp+98h+arg_18]
0x18002d2d5  mov     rdx, rsi
0x18002d2d8  mov     ecx, edi
0x18002d2da  call    IsValidNameSpace
0x18002d2df  test    eax, eax
0x18002d2e1  jz      loc_18002D377
0x18002d2e7  mov     rax, [rsi+28h]
0x18002d2eb  test    rax, rax
0x18002d2ee  jz      loc_18002D377
0x18002d2f4  mov     r9d, [rsp+98h+arg_38]
0x18002d2fc  lea     rcx, [rsp+98h+var_58]
0x18002d301  mov     [rsp+98h+var_70], rcx
0x18002d306  mov     r8d, ebx
0x18002d309  mov     rcx, r14
0x18002d30c  mov     [rsp+98h+pszSrc], r12
0x18002d311  mov     rdx, r15
0x18002d314  mov     r13d, 1
0x18002d31a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d31f  test    eax, eax
0x18002d321  jnz     short loc_18002D369
0x18002d323  mov     r9d, [rsp+98h+arg_38]; int
0x18002d32b  lea     rax, [rsp+98h+var_54]
0x18002d330  mov     ecx, [rsi+34h]; int
0x18002d333  mov     r8, r12; int
0x18002d336  mov     [rsp+98h+var_60], rax; __int64
0x18002d33b  mov     rdx, r14; int
0x18002d33e  lea     rax, [rsp+98h+var_54+4]
0x18002d343  mov     [rsp+98h+var_68], rax; __int64
0x18002d348  lea     rax, [rsp+98h+var_48]
0x18002d34d  mov     [rsp+98h+var_70], rax; __int64
0x18002d352  mov     [rsp+98h+pszSrc], r15; pszSrc
0x18002d357  call    PackBuffer
0x18002d35c  test    eax, eax
0x18002d35e  jnz     short loc_18002D364
0x18002d360  inc     ebp
0x18002d362  jmp     short loc_18002D377
0x18002d364  cmp     eax, 7Ah ; 'z'
0x18002d367  jz      short loc_18002D377
0x18002d369  mov     ecx, eax; dwErrCode
0x18002d36b  call    cs:__imp_SetLastError
0x18002d372  nop     dword ptr [rax+rax+00h]
0x18002d377  mov     rsi, [rsi]
0x18002d37a  lea     rax, NameSpaceListHead
0x18002d381  cmp     rsi, rax
0x18002d384  jnz     loc_18002D2D5
0x18002d38a  mov     edi, dword ptr [rsp+98h+var_54]
0x18002d38e  mov     rbx, [rsp+98h+arg_28]
0x18002d396  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002d39d  mov     r8, r12; P
0x18002d3a0  xor     edx, edx; Flags
0x18002d3a2  call    cs:__imp_RtlFreeHeap
0x18002d3a9  nop     dword ptr [rax+rax+00h]
0x18002d3ae  test    edi, edi
0x18002d3b0  jz      short loc_18002D3C7
0x18002d3b2  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18002d3b7  call    cs:__imp_SetLastError
0x18002d3be  nop     dword ptr [rax+rax+00h]
0x18002d3c3  add     [rbx], edi
0x18002d3c5  jmp     short loc_18002D3F2
0x18002d3c7  test    r13d, r13d
0x18002d3ca  jnz     short loc_18002D3DD
0x18002d3cc  mov     ecx, 4DBh; dwErrCode
0x18002d3d1  call    cs:__imp_SetLastError
0x18002d3d8  nop     dword ptr [rax+rax+00h]
0x18002d3dd  mov     eax, ebp
0x18002d3df  jmp     short loc_18002D3F5
0x18002d3e1  mov     ecx, 57h ; 'W'; dwErrCode
0x18002d3e6  call    cs:__imp_SetLastError
0x18002d3ed  nop     dword ptr [rax+rax+00h]
0x18002d3f2  or      eax, 0FFFFFFFFh
0x18002d3f5  mov     rbx, [rsp+98h+arg_8]
0x18002d3fd  add     rsp, 60h
0x18002d401  pop     r15
0x18002d403  pop     r14
0x18002d405  pop     r13
0x18002d407  pop     r12
0x18002d409  pop     rdi
0x18002d40a  pop     rsi
0x18002d40b  pop     rbp
0x18002d40c  retn
```
