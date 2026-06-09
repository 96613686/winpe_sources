# raiseEvent

- ea: `0x18002b3a0`
- end: `0x18002b5ce`
- name: `raiseEvent`
- size: `558`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002af90`

## callees

- `0x18002b0a0`
- `0x18002b1fc`
- `0x18002b3a0`
- `0x18002c006`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002b464`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002b553`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002b464`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002b553`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b4bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b576`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b5b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b4bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b576`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b5b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b3ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b3ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b3db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b4ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b568`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b5a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b3db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b4ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b568`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b5a7`
- `ntdll!EtwEventWrite` at `0x18002b597`
- `ntdll!EtwEventWrite` at `0x18002b597`

## pseudocode

```c
__int64 __fastcall raiseEvent(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  unsigned int v5; // r13d
  unsigned int inited; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int *v10; // rdi
  __int64 v11; // r8
  __int64 v12; // r9
  struct _FILETIME **v13; // r14
  struct _FILETIME ***v14; // rsi
  __int64 v15; // r12
  struct _FILETIME **v16; // r13
  __int64 v17; // rbx
  __int64 v18; // rdx
  struct _FILETIME **v19; // rax
  struct _FILETIME *v20; // rcx
  HANDLE v21; // rax
  struct _FILETIME *v22; // rsi
  _QWORD *v23; // rdx
  struct _FILETIME *v24; // rbx
  __int64 v25; // rax
  unsigned int v26; // r12d
  unsigned int i; // r15d
  HANDLE v28; // rax
  __int64 v30; // rdx
  HANDLE v31; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp+8h] BYREF
  __int64 v33; // [rsp+88h] [rbp+10h]
  unsigned int v34; // [rsp+90h] [rbp+18h]
  __int64 v35; // [rsp+98h] [rbp+20h]

  v35 = a4;
  v34 = a3;
  v33 = a2;
  v5 = a3;
  if ( !*(_BYTE *)(a1 + 64) )
    return 6;
  ProcessHeap = GetProcessHeap();
  v10 = (unsigned int *)HeapAlloc(ProcessHeap, 0, 0x38u);
  if ( !v10 )
    return 14;
  v11 = v5;
  v12 = a4;
  if ( (*(_DWORD *)(a1 + 32) & 1) != 0 )
  {
    v12 = 0;
    v11 = 0;
  }
  inited = initEventEntry(v10, a2, v11, v12);
  if ( inited )
    return inited;
  v13 = (struct _FILETIME **)(a1 + 40);
  v14 = *(struct _FILETIME ****)(a1 + 40);
  if ( v14 != (struct _FILETIME ***)(a1 + 40) )
  {
    do
    {
      v15 = *((unsigned int *)v14 - 2);
      v16 = *v14;
      SystemTimeAsFileTime = 0;
      if ( (_DWORD)v15 != -1 )
      {
        v17 = (__int64)*(v14 - 2);
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v18 = *(_QWORD *)&SystemTimeAsFileTime - v17;
        if ( *(_QWORD *)&SystemTimeAsFileTime - v17 < 0 || v18 > 10000 * v15 )
        {
          v19 = *v14;
          if ( (*v14)[1] != (struct _FILETIME *)v14
            || (v20 = (struct _FILETIME *)v14[1], (struct _FILETIME ***)*v20 != v14) )
          {
            __fastfail(3u);
          }
          *v20 = (struct _FILETIME)v19;
          v19[1] = v20;
          deinitEventEntry(v14 - 5, v18);
          v21 = GetProcessHeap();
          HeapFree(v21, 0, v14 - 5);
        }
      }
      v14 = (struct _FILETIME ***)v16;
    }
    while ( v16 != v13 );
    v5 = v34;
  }
  v22 = *v13;
  while ( 1 )
  {
LABEL_18:
    if ( v22 == (struct _FILETIME *)v13 )
    {
      inited = EtwEventWrite(*(_QWORD *)(a1 + 56), v33, v5, v35);
      deinitEventEntry(v10, v30);
      v31 = GetProcessHeap();
      HeapFree(v31, 0, v10);
      return inited;
    }
    v23 = (_QWORD *)v22[-5];
    v24 = v22;
    v22 = (struct _FILETIME *)*v22;
    v25 = **(_QWORD **)v10 - *v23;
    if ( !v25 )
      v25 = *(_QWORD *)(*(_QWORD *)v10 + 8LL) - v23[1];
    if ( !v25 )
    {
      v26 = v10[2];
      if ( v26 == v24[-4].dwLowDateTime )
        break;
    }
  }
  for ( i = 0; i < v26; ++i )
  {
    if ( memcmp_0(
           *(const void **)(*((_QWORD *)v10 + 2) + 16LL * i),
           *(const void **)(*(_QWORD *)&v24[-3] + 16LL * i),
           *(unsigned int *)(*((_QWORD *)v10 + 2) + 16LL * i + 8)) )
    {
      goto LABEL_18;
    }
  }
  if ( (*(_BYTE *)(a1 + 32) & 2) != 0 )
  {
    GetSystemTimeAsFileTime(v24 - 2);
    v24[-1].dwLowDateTime = 0;
  }
  deinitEventEntry(v10, v23);
  v28 = GetProcessHeap();
  HeapFree(v28, 0, v10);
  return 0;
}

```

## disassembly

```asm
0x18002b3a0  mov     [rsp+arg_18], r9
0x18002b3a5  mov     [rsp+arg_10], r8d
0x18002b3aa  mov     [rsp+arg_8], rdx
0x18002b3af  push    rbx
0x18002b3b0  push    rbp
0x18002b3b1  push    rsi
0x18002b3b2  push    rdi
0x18002b3b3  push    r12
0x18002b3b5  push    r13
0x18002b3b7  push    r14
0x18002b3b9  push    r15
0x18002b3bb  sub     rsp, 38h
0x18002b3bf  cmp     byte ptr [rcx+40h], 0
0x18002b3c3  mov     r15, r9
0x18002b3c6  mov     r13d, r8d
0x18002b3c9  mov     rbx, rdx
0x18002b3cc  mov     rbp, rcx
0x18002b3cf  jnz     short loc_18002B3DB
0x18002b3d1  mov     ebx, 6
0x18002b3d6  jmp     loc_18002B5BB
0x18002b3db  call    cs:__imp_GetProcessHeap
0x18002b3e1  xor     edx, edx; dwFlags
0x18002b3e3  mov     rcx, rax; hHeap
0x18002b3e6  lea     r8d, [rdx+38h]; dwBytes
0x18002b3ea  call    cs:__imp_HeapAlloc
0x18002b3f0  mov     rdi, rax
0x18002b3f3  test    rax, rax
0x18002b3f6  jnz     short loc_18002B400
0x18002b3f8  lea     ebx, [rax+0Eh]
0x18002b3fb  jmp     loc_18002B5BB
0x18002b400  test    dword ptr [rbp+20h], 1
0x18002b407  mov     eax, 0
0x18002b40c  mov     r8d, r13d
0x18002b40f  mov     r9, r15
0x18002b412  cmovnz  r9, rax
0x18002b416  cmovnz  r8d, eax
0x18002b41a  mov     rdx, rbx
0x18002b41d  mov     rcx, rdi
0x18002b420  call    initEventEntry
0x18002b425  mov     ebx, eax
0x18002b427  test    eax, eax
0x18002b429  jnz     loc_18002B5BB
0x18002b42f  lea     r14, [rbp+28h]
0x18002b433  mov     rsi, [r14]
0x18002b436  cmp     rsi, r14
0x18002b439  jz      loc_18002B4D6
0x18002b43f  mov     r12d, [rsi-8]
0x18002b443  mov     r13, [rsi]
0x18002b446  mov     qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002b452  cmp     r12d, 0FFFFFFFFh
0x18002b456  jz      short loc_18002B4C2
0x18002b458  mov     rbx, [rsi-10h]
0x18002b45c  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002b464  call    cs:__imp_GetSystemTimeAsFileTime
0x18002b46a  mov     rdx, qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]
0x18002b472  sub     rdx, rbx
0x18002b475  js      short loc_18002B483
0x18002b477  imul    rcx, r12, 2710h
0x18002b47e  cmp     rdx, rcx
0x18002b481  jle     short loc_18002B4C2
0x18002b483  mov     rax, [rsi]
0x18002b486  cmp     [rax+8], rsi
0x18002b48a  jnz     loc_18002B542
0x18002b490  mov     rcx, [rsi+8]
0x18002b494  cmp     [rcx], rsi
0x18002b497  jnz     loc_18002B542
0x18002b49d  mov     [rcx], rax
0x18002b4a0  mov     [rax+8], rcx
0x18002b4a4  lea     rcx, [rsi-28h]
0x18002b4a8  call    deinitEventEntry
0x18002b4ad  call    cs:__imp_GetProcessHeap
0x18002b4b3  lea     r8, [rsi-28h]; lpMem
0x18002b4b7  xor     edx, edx; dwFlags
0x18002b4b9  mov     rcx, rax; hHeap
0x18002b4bc  call    cs:__imp_HeapFree
0x18002b4c2  mov     rsi, r13
0x18002b4c5  cmp     r13, r14
0x18002b4c8  jnz     loc_18002B43F
0x18002b4ce  mov     r13d, [rsp+78h+arg_10]
0x18002b4d6  mov     rsi, [r14]
0x18002b4d9  cmp     rsi, r14
0x18002b4dc  jz      loc_18002B580
0x18002b4e2  mov     rcx, [rdi]
0x18002b4e5  lea     rax, [rsi-28h]
0x18002b4e9  mov     rdx, [rax]
0x18002b4ec  mov     rbx, rsi
0x18002b4ef  mov     rsi, [rsi]
0x18002b4f2  mov     rax, [rcx]
0x18002b4f5  sub     rax, [rdx]
0x18002b4f8  jnz     short loc_18002B502
0x18002b4fa  mov     rax, [rcx+8]
0x18002b4fe  sub     rax, [rdx+8]
0x18002b502  test    rax, rax
0x18002b505  jnz     short loc_18002B4D9
0x18002b507  mov     r12d, [rdi+8]
0x18002b50b  cmp     r12d, [rbx-20h]
0x18002b50f  jnz     short loc_18002B4D9
0x18002b511  xor     r15d, r15d
0x18002b514  cmp     r15d, r12d
0x18002b517  jnb     short loc_18002B549
0x18002b519  mov     rcx, [rdi+10h]
0x18002b51d  mov     rdx, [rbx-18h]
0x18002b521  mov     eax, r15d
0x18002b524  add     rax, rax
0x18002b527  mov     r8d, [rcx+rax*8+8]; Size
0x18002b52c  mov     rcx, [rcx+rax*8]; Buf1
0x18002b530  mov     rdx, [rdx+rax*8]; Buf2
0x18002b534  call    memcmp_0
0x18002b539  test    eax, eax
0x18002b53b  jnz     short loc_18002B4D9
0x18002b53d  inc     r15d
0x18002b540  jmp     short loc_18002B514
0x18002b542  mov     ecx, 3
0x18002b547  int     29h; Win8: RtlFailFast(ecx)
0x18002b549  test    byte ptr [rbp+20h], 2
0x18002b54d  jz      short loc_18002B560
0x18002b54f  lea     rcx, [rbx-10h]; lpSystemTimeAsFileTime
0x18002b553  call    cs:__imp_GetSystemTimeAsFileTime
0x18002b559  mov     dword ptr [rbx-8], 0
0x18002b560  mov     rcx, rdi
0x18002b563  call    deinitEventEntry
0x18002b568  call    cs:__imp_GetProcessHeap
0x18002b56e  mov     r8, rdi; lpMem
0x18002b571  xor     edx, edx; dwFlags
0x18002b573  mov     rcx, rax; hHeap
0x18002b576  call    cs:__imp_HeapFree
0x18002b57c  xor     eax, eax
0x18002b57e  jmp     short loc_18002B5BD
0x18002b580  mov     r9, [rsp+78h+arg_18]
0x18002b588  mov     r8d, r13d
0x18002b58b  mov     rdx, [rsp+78h+arg_8]
0x18002b593  mov     rcx, [rbp+38h]
0x18002b597  call    cs:__imp_EtwEventWrite
0x18002b59d  mov     rcx, rdi
0x18002b5a0  mov     ebx, eax
0x18002b5a2  call    deinitEventEntry
0x18002b5a7  call    cs:__imp_GetProcessHeap
0x18002b5ad  mov     r8, rdi; lpMem
0x18002b5b0  xor     edx, edx; dwFlags
0x18002b5b2  mov     rcx, rax; hHeap
0x18002b5b5  call    cs:__imp_HeapFree
0x18002b5bb  mov     eax, ebx
0x18002b5bd  add     rsp, 38h
0x18002b5c1  pop     r15
0x18002b5c3  pop     r14
0x18002b5c5  pop     r13
0x18002b5c7  pop     r12
0x18002b5c9  pop     rdi
0x18002b5ca  pop     rsi
0x18002b5cb  pop     rbp
0x18002b5cc  pop     rbx
0x18002b5cd  retn
```
