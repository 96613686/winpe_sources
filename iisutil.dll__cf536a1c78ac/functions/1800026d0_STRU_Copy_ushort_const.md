# STRU::Copy(ushort const *)

- ea: `0x1800026d0`
- end: `0x180002855`
- name: `?Copy@STRU@@QEAAJPEBG@Z`
- size: `389`
- prototype: `int(STRU *__hidden this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002210`
- `0x180002460`
- `0x180002860`
- `0x18001ebd0`
- `0x180024650`
- `0x18002b4d0`

## callees

- `0x1800026d0`
- `0x18002e516`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000281e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000281e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000282a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000282a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000280b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000280b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002796`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800027f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002796`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800027f7`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800027ad`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800027ad`

## pseudocode

```c
int __fastcall STRU::Copy(STRU *this, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned __int64 v6; // rcx
  __int64 v7; // rbp
  __int64 v8; // rcx
  __int64 v9; // rbp
  int result; // eax
  unsigned int v11; // r15d
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  void *v14; // rax
  void *v15; // rbx
  HANDLE v16; // rax

  if ( !a2 )
    return -2147024809;
  v4 = -1;
  while ( a2[++v4] != 0 )
    ;
  v6 = *((unsigned int *)this + 10);
  v7 = (unsigned int)(2 * v4);
  if ( v6 >= v7 + 2 )
    goto LABEL_5;
  v11 = v7 + 128;
  if ( (unsigned __int64)(v7 + 128) > 0xFFFFFFFF )
    return -2147024362;
  if ( v11 <= (unsigned int)v6 )
    goto LABEL_5;
  if ( *((_BYTE *)this + 44) )
  {
    v12 = (void *)*((_QWORD *)this + 4);
    ProcessHeap = GetProcessHeap();
    v14 = HeapReAlloc(ProcessHeap, 0, v12, v11);
  }
  else
  {
    v16 = GetProcessHeap();
    v14 = HeapAlloc(v16, 0, v11);
  }
  v15 = v14;
  if ( v14 )
  {
    if ( !*((_BYTE *)this + 44) )
    {
      memcpy_0(v14, *((const void **)this + 4), *((unsigned int *)this + 10));
      *((_BYTE *)this + 44) = 1;
    }
    *((_QWORD *)this + 4) = v15;
    *((_DWORD *)this + 10) = v11;
LABEL_5:
    memcpy_0(*((void **)this + 4), a2, (unsigned int)v7);
    v8 = *((_QWORD *)this + 4);
    v9 = (unsigned int)v7 >> 1;
    result = 0;
    *((_DWORD *)this + 12) = v9;
    *(_WORD *)(v8 + 2 * v9) = 0;
    return result;
  }
  SetLastError(8u);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800026d0  push    rsi
0x1800026d2  push    rdi
0x1800026d3  sub     rsp, 38h
0x1800026d7  mov     rdi, rdx
0x1800026da  mov     rsi, rcx
0x1800026dd  test    rdx, rdx
0x1800026e0  jz      loc_18000284B
0x1800026e6  mov     [rsp+48h+arg_8], rbp
0x1800026eb  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800026f2  mov     [rsp+48h+var_20], r14
0x1800026f7  nop     word ptr [rax+rax+00000000h]
0x180002700  cmp     word ptr [rdx+rax*2+2], 0
0x180002706  lea     rax, [rax+1]
0x18000270a  jnz     short loc_180002700
0x18000270c  mov     ecx, [rcx+28h]
0x18000270f  lea     ebp, [rax+rax]
0x180002712  mov     [rsp+48h+arg_0], rbx
0x180002717  lea     rax, [rbp+2]
0x18000271b  mov     [rsp+48h+arg_10], r12
0x180002720  mov     [rsp+48h+var_28], r15
0x180002725  mov     r14d, ebp
0x180002728  cmp     rcx, rax
0x18000272b  jb      short loc_18000276E
0x18000272d  mov     rcx, [rsi+20h]; void *
0x180002731  mov     r8, r14; Size
0x180002734  mov     rdx, rdi; Src
0x180002737  call    memcpy_0
0x18000273c  mov     rcx, [rsi+20h]
0x180002740  shr     ebp, 1
0x180002742  mov     edx, ebp
0x180002744  xor     eax, eax
0x180002746  mov     [rsi+30h], edx
0x180002749  mov     [rcx+rbp*2], ax
0x18000274d  mov     r15, [rsp+48h+var_28]
0x180002752  mov     r14, [rsp+48h+var_20]
0x180002757  mov     r12, [rsp+48h+arg_10]
0x18000275c  mov     rbp, [rsp+48h+arg_8]
0x180002761  mov     rbx, [rsp+48h+arg_0]
0x180002766  add     rsp, 38h
0x18000276a  pop     rdi
0x18000276b  pop     rsi
0x18000276c  retn
0x18000276e  lea     r15, [rbp+80h]
0x180002775  mov     eax, 0FFFFFFFFh
0x18000277a  cmp     r15, rax
0x18000277d  ja      short loc_1800027ED
0x18000277f  cmp     r15d, ecx
0x180002782  jbe     short loc_18000272D
0x180002784  cmp     byte ptr [rsi+2Ch], 0
0x180002788  mov     [rsp+48h+var_18], r13
0x18000278d  mov     r13d, r15d
0x180002790  jz      short loc_1800027F7
0x180002792  mov     rbx, [rsi+20h]
0x180002796  call    cs:__imp_GetProcessHeap
0x18000279d  nop     dword ptr [rax+rax+00h]
0x1800027a2  mov     r9d, r13d; dwBytes
0x1800027a5  mov     r8, rbx; lpMem
0x1800027a8  mov     rcx, rax; hHeap
0x1800027ab  xor     edx, edx; dwFlags
0x1800027ad  call    cs:__imp_HeapReAlloc
0x1800027b4  nop     dword ptr [rax+rax+00h]
0x1800027b9  mov     r13, [rsp+48h+var_18]
0x1800027be  mov     rbx, rax
0x1800027c1  test    rax, rax
0x1800027c4  jz      short loc_180002819
0x1800027c6  cmp     byte ptr [rsi+2Ch], 0
0x1800027ca  jnz     short loc_1800027E0
0x1800027cc  mov     r8d, [rsi+28h]; Size
0x1800027d0  mov     rcx, rax; void *
0x1800027d3  mov     rdx, [rsi+20h]; Src
0x1800027d7  call    memcpy_0
0x1800027dc  mov     byte ptr [rsi+2Ch], 1
0x1800027e0  mov     [rsi+20h], rbx
0x1800027e4  mov     [rsi+28h], r15d
0x1800027e8  jmp     loc_18000272D
0x1800027ed  mov     eax, 80070216h
0x1800027f2  jmp     loc_18000274D
0x1800027f7  call    cs:__imp_GetProcessHeap
0x1800027fe  nop     dword ptr [rax+rax+00h]
0x180002803  mov     r8, r13; dwBytes
0x180002806  xor     edx, edx; dwFlags
0x180002808  mov     rcx, rax; hHeap
0x18000280b  call    cs:__imp_HeapAlloc
0x180002812  nop     dword ptr [rax+rax+00h]
0x180002817  jmp     short loc_1800027B9
0x180002819  mov     ecx, 8; dwErrCode
0x18000281e  call    cs:__imp_SetLastError
0x180002825  nop     dword ptr [rax+rax+00h]
0x18000282a  call    cs:__imp_GetLastError
0x180002831  nop     dword ptr [rax+rax+00h]
0x180002836  test    eax, eax
0x180002838  jle     loc_18000274D
0x18000283e  movzx   eax, ax
0x180002841  or      eax, 80070000h
0x180002846  jmp     loc_18000274D
0x18000284b  mov     eax, 80070057h
0x180002850  jmp     loc_180002766
```
