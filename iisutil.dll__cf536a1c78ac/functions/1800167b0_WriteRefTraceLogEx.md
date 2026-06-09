# WriteRefTraceLogEx

- ea: `0x1800167b0`
- end: `0x18001688b`
- name: `WriteRefTraceLogEx`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001aaa0`

## callees

- `0x1800167b0`
- `0x18002e516`
- `0x18002e52e`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x180016844`
- `ntdll!RtlCaptureStackBackTrace` at `0x180016844`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800167e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800167e9`

## pseudocode

```c
__int64 __fastcall WriteRefTraceLogEx(__int64 a1, int a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  ULONG v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ebx
  int Src; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v15; // [rsp+28h] [rbp-A0h]
  __int64 v16; // [rsp+30h] [rbp-98h]
  __int64 v17; // [rsp+38h] [rbp-90h]
  __int64 v18; // [rsp+40h] [rbp-88h]
  DWORD CurrentThreadId; // [rsp+48h] [rbp-80h]
  PVOID BackTrace; // [rsp+50h] [rbp-78h] BYREF
  ULONG BackTraceHash; // [rsp+D8h] [rbp+10h] BYREF

  BackTraceHash = 0;
  memset_0(&Src, 0, 0x78u);
  Src = a2;
  v15 = a3;
  CurrentThreadId = GetCurrentThreadId();
  v18 = a6;
  v16 = a4;
  v17 = a5;
  if ( a4 != -1 || a5 != -1 || (v10 = 2, a6 != -1) )
    v10 = 1;
  RtlCaptureStackBackTrace(v10, 9u, &BackTrace, &BackTraceHash);
  v11 = *(_DWORD *)(a1 + 4);
  v12 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 8)) % v11;
  memcpy_0((void *)(*(_QWORD *)(a1 + 16) + v12 * *(_DWORD *)(a1 + 12)), &Src, *(int *)(a1 + 12));
  return v12;
}

```

## disassembly

```asm
0x1800167b0  mov     rax, rsp
0x1800167b3  push    rbx
0x1800167b4  push    rbp
0x1800167b5  push    rsi
0x1800167b6  push    rdi
0x1800167b7  sub     rsp, 0A8h
0x1800167be  mov     ebx, edx
0x1800167c0  mov     dword ptr [rax+10h], 0
0x1800167c7  xor     edx, edx; Val
0x1800167c9  mov     rdi, r8
0x1800167cc  mov     rbp, rcx
0x1800167cf  mov     rsi, r9
0x1800167d2  lea     rcx, [rsp+0C8h+Src]; void *
0x1800167d7  lea     r8d, [rdx+78h]; Size
0x1800167db  call    memset_0
0x1800167e0  mov     [rsp+0C8h+Src], ebx
0x1800167e4  mov     [rsp+0C8h+var_A0], rdi
0x1800167e9  call    cs:__imp_GetCurrentThreadId
0x1800167f0  nop     dword ptr [rax+rax+00h]
0x1800167f5  mov     rdx, [rsp+0C8h+arg_20]
0x1800167fd  mov     ebx, 1
0x180016802  mov     [rsp+0C8h+var_80], eax
0x180016806  mov     rax, [rsp+0C8h+arg_28]
0x18001680e  mov     [rsp+0C8h+var_88], rax
0x180016813  mov     [rsp+0C8h+var_98], rsi
0x180016818  mov     [rsp+0C8h+var_90], rdx
0x18001681d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180016821  jnz     short loc_180016830
0x180016823  cmp     rdx, rsi
0x180016826  jnz     short loc_180016830
0x180016828  lea     ecx, [rsi+3]
0x18001682b  cmp     rax, rsi
0x18001682e  jz      short loc_180016832
0x180016830  mov     ecx, ebx; FramesToSkip
0x180016832  lea     r9, [rsp+0C8h+BackTraceHash]; BackTraceHash
0x18001683a  mov     edx, 9; FramesToCapture
0x18001683f  lea     r8, [rsp+0C8h+BackTrace]; BackTrace
0x180016844  call    cs:__imp_RtlCaptureStackBackTrace
0x18001684b  nop     dword ptr [rax+rax+00h]
0x180016850  mov     ecx, [rbp+4]
0x180016853  mov     eax, ebx
0x180016855  lock xadd [rbp+8], eax
0x18001685a  add     eax, ebx
0x18001685c  xor     edx, edx
0x18001685e  div     ecx
0x180016860  movsxd  rax, dword ptr [rbp+0Ch]
0x180016864  mov     r8, rax; Size
0x180016867  mov     ebx, edx
0x180016869  imul    eax, edx
0x18001686c  lea     rdx, [rsp+0C8h+Src]; Src
0x180016871  mov     ecx, eax
0x180016873  add     rcx, [rbp+10h]; void *
0x180016877  call    memcpy_0
0x18001687c  mov     eax, ebx
0x18001687e  add     rsp, 0A8h
0x180016885  pop     rdi
0x180016886  pop     rsi
0x180016887  pop     rbp
0x180016888  pop     rbx
0x180016889  retn
```
