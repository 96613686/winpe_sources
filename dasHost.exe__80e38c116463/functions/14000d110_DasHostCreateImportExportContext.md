# DasHostCreateImportExportContext

- ea: `0x14000d110`
- end: `0x14000d1e0`
- name: `DasHostCreateImportExportContext`
- size: `208`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64, struct _RTL_CRITICAL_SECTION **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400020d0`
- `0x140008eec`
- `0x140008f88`
- `0x14000d110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14000d19e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14000d19e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d169`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d169`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d15a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d15a`

## pseudocode

```c
__int64 __fastcall DasHostCreateImportExportContext(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        struct _RTL_CRITICAL_SECTION **a4)
{
  HANDLE ProcessHeap; // rax
  struct _RTL_CRITICAL_SECTION *v8; // rax
  int v9; // edx
  int v10; // r8d
  struct _RTL_CRITICAL_SECTION *v11; // rdi
  unsigned int v12; // ebx
  __int128 v13; // xmm0
  int v15; // [rsp+28h] [rbp-50h]

  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      a3,
      10,
      &WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids);
  ProcessHeap = GetProcessHeap();
  v8 = (struct _RTL_CRITICAL_SECTION *)HeapAlloc(ProcessHeap, 0, 0x70u);
  v11 = v8;
  if ( v8 )
  {
    v12 = 0;
    memset_0(v8, 0, 0x70u);
    v13 = *a2;
    *(_QWORD *)&v11[2].LockCount = a3;
    *(_OWORD *)&v11->DebugInfo = v13;
    InitializeCriticalSection(v11 + 1);
    *a4 = v11;
  }
  else
  {
    v12 = -2147024882;
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v9,
      v10,
      11,
      &WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids,
      v15,
      v12);
  return v12;
}

```

## disassembly

```asm
0x14000d110  push    rbx
0x14000d112  push    rbp
0x14000d113  push    rsi
0x14000d114  push    rdi
0x14000d115  push    r12
0x14000d117  push    r14
0x14000d119  push    r15
0x14000d11b  sub     rsp, 40h
0x14000d11f  mov     rsi, r9
0x14000d122  mov     rbp, r8
0x14000d125  mov     r14, rdx
0x14000d128  lea     r15, WPP_RECORDER_INITIALIZED
0x14000d12f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000d136  lea     r12, WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids
0x14000d13d  jz      short loc_14000D15A
0x14000d13f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d146  mov     r9d, 0Ah; int
0x14000d14c  mov     [rsp+78h+MessageGuid], r12; MessageGuid
0x14000d151  mov     rcx, [rcx+28h]; int
0x14000d155  call    WPP_RECORDER_SF_s
0x14000d15a  call    cs:__imp_GetProcessHeap
0x14000d160  xor     edx, edx; dwFlags
0x14000d162  mov     rcx, rax; hHeap
0x14000d165  lea     r8d, [rdx+70h]; dwBytes
0x14000d169  call    cs:__imp_HeapAlloc
0x14000d16f  mov     rdi, rax
0x14000d172  test    rax, rax
0x14000d175  jnz     short loc_14000D17E
0x14000d177  mov     ebx, 8007000Eh
0x14000d17c  jmp     short loc_14000D1A7
0x14000d17e  xor     ebx, ebx
0x14000d180  xor     edx, edx; Val
0x14000d182  mov     rcx, rdi; void *
0x14000d185  lea     r8d, [rbx+70h]; Size
0x14000d189  call    memset_0
0x14000d18e  movups  xmm0, xmmword ptr [r14]
0x14000d192  lea     rcx, [rdi+28h]; lpCriticalSection
0x14000d196  mov     [rdi+58h], rbp
0x14000d19a  movdqu  xmmword ptr [rdi], xmm0
0x14000d19e  call    cs:__imp_InitializeCriticalSection
0x14000d1a4  mov     [rsi], rdi
0x14000d1a7  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000d1ae  jz      short loc_14000D1CF
0x14000d1b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d1b7  mov     r9d, 0Bh; int
0x14000d1bd  mov     dword ptr [rsp+78h+var_48], ebx; char
0x14000d1c1  mov     [rsp+78h+MessageGuid], r12; MessageGuid
0x14000d1c6  mov     rcx, [rcx+28h]; int
0x14000d1ca  call    WPP_RECORDER_SF_sd
0x14000d1cf  mov     eax, ebx
0x14000d1d1  add     rsp, 40h
0x14000d1d5  pop     r15
0x14000d1d7  pop     r14
0x14000d1d9  pop     r12
0x14000d1db  pop     rdi
0x14000d1dc  pop     rsi
0x14000d1dd  pop     rbp
0x14000d1de  pop     rbx
0x14000d1df  retn
```
