# Dispatcher::initialize(ulong,ulong)

- ea: `0x1800175cc`
- end: `0x180017691`
- name: `?initialize@Dispatcher@@QEAAHKK@Z`
- size: `197`
- prototype: `__int64 __fastcall(Dispatcher *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000c070`

## callees

- `0x1800175cc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180017669`
- `KERNEL32!CloseHandle` at `0x180017669`
- `KERNEL32!GetSystemInfo` at `0x18001760f`
- `KERNEL32!GetSystemInfo` at `0x18001760f`
- `KERNEL32!CreateEventW` at `0x180017650`
- `KERNEL32!CreateEventW` at `0x180017650`
- `KERNEL32!CreateIoCompletionPort` at `0x18001762e`
- `KERNEL32!CreateIoCompletionPort` at `0x18001762e`

## pseudocode

```c
__int64 __fastcall Dispatcher::initialize(Dispatcher *this)
{
  struct _SYSTEM_INFO v2; // [rsp+20h] [rbp-38h] BYREF

  qword_180024F18 = 0;
  dword_180024F20 = 0;
  memset(&v2, 0, sizeof(v2));
  dword_180024F24 = 300000;
  dword_180024F40 = 0;
  GetSystemInfo(&v2);
  HIDWORD(qword_180024F18) = v2.dwNumberOfProcessors << 6;
  CompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
  if ( !CompletionPort )
    return 0;
  hHandle = CreateEventW(0, 1, 1, 0);
  if ( !hHandle )
  {
    CloseHandle(CompletionPort);
    CompletionPort = 0;
    return 0;
  }
  hObject = 0;
  return 1;
}

```

## disassembly

```asm
0x1800175cc  mov     rax, rsp
0x1800175cf  sub     rsp, 58h
0x1800175d3  xorps   xmm0, xmm0
0x1800175d6  mov     cs:qword_180024F18, 0
0x1800175e1  lea     rcx, [rax-38h]; lpSystemInfo
0x1800175e5  mov     cs:dword_180024F20, 0
0x1800175ef  movups  xmmword ptr [rax-38h], xmm0
0x1800175f3  mov     cs:dword_180024F24, 493E0h
0x1800175fd  movups  xmmword ptr [rax-28h], xmm0
0x180017601  mov     cs:dword_180024F40, 0
0x18001760b  movups  xmmword ptr [rax-18h], xmm0
0x18001760f  call    cs:__imp_GetSystemInfo
0x180017615  mov     eax, [rsp+58h+var_18]
0x180017619  xor     r9d, r9d; NumberOfConcurrentThreads
0x18001761c  shl     eax, 6
0x18001761f  xor     r8d, r8d; CompletionKey
0x180017622  xor     edx, edx; ExistingCompletionPort
0x180017624  mov     dword ptr cs:qword_180024F18+4, eax
0x18001762a  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18001762e  call    cs:__imp_CreateIoCompletionPort
0x180017634  mov     cs:CompletionPort, rax
0x18001763b  test    rax, rax
0x18001763e  jnz     short loc_180017644
0x180017640  xor     eax, eax
0x180017642  jmp     short loc_18001768C
0x180017644  xor     r9d, r9d; lpName
0x180017647  xor     ecx, ecx; lpEventAttributes
0x180017649  lea     edx, [r9+1]; bManualReset
0x18001764d  mov     r8d, edx; bInitialState
0x180017650  call    cs:__imp_CreateEventW
0x180017656  mov     cs:hHandle, rax
0x18001765d  test    rax, rax
0x180017660  jnz     short loc_18001767C
0x180017662  mov     rcx, cs:CompletionPort; hObject
0x180017669  call    cs:__imp_CloseHandle
0x18001766f  mov     cs:CompletionPort, 0
0x18001767a  jmp     short loc_180017640
0x18001767c  mov     cs:hObject, 0
0x180017687  mov     eax, 1
0x18001768c  add     rsp, 58h
0x180017690  retn
```
