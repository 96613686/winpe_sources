# DasHostCloseImportExportContext

- ea: `0x14000d020`
- end: `0x14000d104`
- name: `DasHostCloseImportExportContext`
- size: `228`
- prototype: `__int64 __fastcall(__int64 *, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d800`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x14000d020`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000d0ac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000d0ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d0c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d0c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d0b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d0b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d0a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d0a2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000d069`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000d069`

## pseudocode

```c
__int64 __fastcall DasHostCloseImportExportContext(__int64 *a1, int a2, int a3)
{
  __int64 v3; // rbx
  __int64 v5; // rcx
  __int64 v6; // rcx
  void *v7; // rcx
  HANDLE ProcessHeap; // rax
  int v9; // edx
  int v10; // r8d
  int v12; // [rsp+28h] [rbp-40h]

  v3 = *a1;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 5), a2, a3, 16, &WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids);
  EventActivityIdControl(2u, (LPGUID)v3);
  v5 = *(_QWORD *)(v3 + 24);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *(_QWORD *)(v3 + 32);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *(void **)(v3 + 88);
  if ( v7 )
    CloseHandle(v7);
  DeleteCriticalSection((LPCRITICAL_SECTION)(v3 + 40));
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, (LPVOID)v3);
  *a1 = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v9,
      v10,
      17,
      &WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids,
      v12,
      0);
  return 0;
}

```

## disassembly

```asm
0x14000d020  push    rbx
0x14000d022  push    rbp
0x14000d023  push    rsi
0x14000d024  push    rdi
0x14000d025  sub     rsp, 48h
0x14000d029  mov     rbx, [rcx]
0x14000d02c  mov     rdi, rcx
0x14000d02f  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000d036  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000d03d  lea     rsi, WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids
0x14000d044  jz      short loc_14000D061
0x14000d046  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d04d  mov     r9d, 10h; int
0x14000d053  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x14000d058  mov     rcx, [rcx+28h]; int
0x14000d05c  call    WPP_RECORDER_SF_s
0x14000d061  mov     rdx, rbx; ActivityId
0x14000d064  mov     ecx, 2; ControlCode
0x14000d069  call    cs:__imp_EventActivityIdControl
0x14000d06f  mov     rcx, [rbx+18h]
0x14000d073  test    rcx, rcx
0x14000d076  jz      short loc_14000D084
0x14000d078  mov     rax, [rcx]
0x14000d07b  mov     rax, [rax+10h]
0x14000d07f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d084  mov     rcx, [rbx+20h]
0x14000d088  test    rcx, rcx
0x14000d08b  jz      short loc_14000D099
0x14000d08d  mov     rax, [rcx]
0x14000d090  mov     rax, [rax+10h]
0x14000d094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d099  mov     rcx, [rbx+58h]; hObject
0x14000d09d  test    rcx, rcx
0x14000d0a0  jz      short loc_14000D0A8
0x14000d0a2  call    cs:__imp_CloseHandle
0x14000d0a8  lea     rcx, [rbx+28h]; lpCriticalSection
0x14000d0ac  call    cs:__imp_DeleteCriticalSection
0x14000d0b2  call    cs:__imp_GetProcessHeap
0x14000d0b8  mov     r8, rbx; lpMem
0x14000d0bb  xor     edx, edx; dwFlags
0x14000d0bd  mov     rcx, rax; hHeap
0x14000d0c0  call    cs:__imp_HeapFree
0x14000d0c6  mov     qword ptr [rdi], 0
0x14000d0cd  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000d0d4  jz      short loc_14000D0F9
0x14000d0d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d0dd  mov     r9d, 11h; int
0x14000d0e3  mov     dword ptr [rsp+68h+var_38], 0; char
0x14000d0eb  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x14000d0f0  mov     rcx, [rcx+28h]; int
0x14000d0f4  call    WPP_RECORDER_SF_sd
0x14000d0f9  xor     eax, eax
0x14000d0fb  add     rsp, 48h
0x14000d0ff  pop     rdi
0x14000d100  pop     rsi
0x14000d101  pop     rbp
0x14000d102  pop     rbx
0x14000d103  retn
```
