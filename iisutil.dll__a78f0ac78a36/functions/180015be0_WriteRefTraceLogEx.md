# WriteRefTraceLogEx

- ea: `0x180015be0`
- end: `0x180015cae`
- name: `WriteRefTraceLogEx`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180019c30`

## callees

- `0x180015be0`
- `0x18002c476`
- `0x18002c48e`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x180015c6e`
- `ntdll!RtlCaptureStackBackTrace` at `0x180015c6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015c19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015c19`

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
0x180015be0  mov     rax, rsp
0x180015be3  push    rbx
0x180015be4  push    rbp
0x180015be5  push    rsi
0x180015be6  push    rdi
0x180015be7  sub     rsp, 0A8h
0x180015bee  mov     ebx, edx
0x180015bf0  mov     dword ptr [rax+10h], 0
0x180015bf7  xor     edx, edx; Val
0x180015bf9  mov     rdi, r8
0x180015bfc  mov     rbp, rcx
0x180015bff  mov     rsi, r9
0x180015c02  lea     rcx, [rsp+0C8h+Src]; void *
0x180015c07  lea     r8d, [rdx+78h]; Size
0x180015c0b  call    memset_0
0x180015c10  mov     [rsp+0C8h+Src], ebx
0x180015c14  mov     [rsp+0C8h+var_A0], rdi
0x180015c19  call    cs:__imp_GetCurrentThreadId
0x180015c1f  mov     rdx, [rsp+0C8h+arg_20]
0x180015c27  mov     ebx, 1
0x180015c2c  mov     [rsp+0C8h+var_80], eax
0x180015c30  mov     rax, [rsp+0C8h+arg_28]
0x180015c38  mov     [rsp+0C8h+var_88], rax
0x180015c3d  mov     [rsp+0C8h+var_98], rsi
0x180015c42  mov     [rsp+0C8h+var_90], rdx
0x180015c47  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180015c4b  jnz     short loc_180015C5A
0x180015c4d  cmp     rdx, rsi
0x180015c50  jnz     short loc_180015C5A
0x180015c52  lea     ecx, [rsi+3]
0x180015c55  cmp     rax, rsi
0x180015c58  jz      short loc_180015C5C
0x180015c5a  mov     ecx, ebx; FramesToSkip
0x180015c5c  lea     r9, [rsp+0C8h+BackTraceHash]; BackTraceHash
0x180015c64  mov     edx, 9; FramesToCapture
0x180015c69  lea     r8, [rsp+0C8h+BackTrace]; BackTrace
0x180015c6e  call    cs:__imp_RtlCaptureStackBackTrace
0x180015c74  mov     ecx, [rbp+4]
0x180015c77  mov     eax, ebx
0x180015c79  lock xadd [rbp+8], eax
0x180015c7e  add     eax, ebx
0x180015c80  xor     edx, edx
0x180015c82  div     ecx
0x180015c84  movsxd  rax, dword ptr [rbp+0Ch]
0x180015c88  mov     r8, rax; Size
0x180015c8b  mov     ebx, edx
0x180015c8d  imul    eax, edx
0x180015c90  lea     rdx, [rsp+0C8h+Src]; Src
0x180015c95  mov     ecx, eax
0x180015c97  add     rcx, [rbp+10h]; void *
0x180015c9b  call    memcpy_0
0x180015ca0  mov     eax, ebx
0x180015ca2  add     rsp, 0A8h
0x180015ca9  pop     rdi
0x180015caa  pop     rsi
0x180015cab  pop     rbp
0x180015cac  pop     rbx
0x180015cad  retn
```
