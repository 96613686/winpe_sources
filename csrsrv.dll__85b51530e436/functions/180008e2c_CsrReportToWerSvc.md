# CsrReportToWerSvc

- ea: `0x180008e2c`
- end: `0x180008eef`
- name: `CsrReportToWerSvc`
- size: `195`
- prototype: `int __fastcall(PVOID Reserved6)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008f00`

## callees

- `0x180008e2c`

## import_xrefs

- `ntdll!NtClose` at `0x180008edd`
- `ntdll!NtClose` at `0x180008edd`
- `ntdll!NtWaitForSingleObject` at `0x180008ecc`
- `ntdll!NtWaitForSingleObject` at `0x180008ecc`
- `ntdll!NtDelayExecution` at `0x180008e61`
- `ntdll!NtDelayExecution` at `0x180008e61`
- `ntdll!RtlCreateUserThread` at `0x180008eb0`
- `ntdll!RtlCreateUserThread` at `0x180008eb0`

## pseudocode

```c
int __fastcall CsrReportToWerSvc(PVOID Reserved6)
{
  int result; // eax
  LARGE_INTEGER Interval; // [rsp+70h] [rbp+18h] BYREF
  HANDLE Object; // [rsp+78h] [rbp+20h] BYREF

  Object = 0;
  Interval.QuadPart = -300000000;
  if ( _InterlockedCompareExchange(&CsrIsReportingtoWerSvc, 1, 0) )
    return NtDelayExecution(0, &Interval);
  result = RtlCreateUserThread(
             (PVOID)0xFFFFFFFFFFFFFFFFLL,
             0,
             0,
             0,
             0,
             0,
             CsrpReportToWerSvcThread,
             Reserved6,
             &Object,
             0);
  if ( result >= 0 )
  {
    NtWaitForSingleObject(Object, 0, &Interval);
    return NtClose(Object);
  }
  return result;
}

```

## disassembly

```asm
0x180008e2c  sub     rsp, 58h
0x180008e30  or      r10, 0FFFFFFFFFFFFFFFFh
0x180008e34  mov     [rsp+58h+Object], 0
0x180008e3d  mov     dword ptr [rsp+58h+Interval], 0EE1E5D00h
0x180008e45  xor     eax, eax
0x180008e47  mov     dword ptr [rsp+58h+Interval+4], r10d
0x180008e4c  lea     edx, [r10+2]
0x180008e50  lock cmpxchg cs:CsrIsReportingtoWerSvc, edx
0x180008e58  jz      short loc_180008E6F
0x180008e5a  lea     rdx, [rsp+58h+Interval]; Interval
0x180008e5f  xor     ecx, ecx; Alertable
0x180008e61  call    cs:__imp_NtDelayExecution
0x180008e68  nop     dword ptr [rax+rax+00h]
0x180008e6d  jmp     short loc_180008EE9
0x180008e6f  mov     [rsp+58h+Reserved8], 0; Reserved8
0x180008e78  lea     rax, [rsp+58h+Object]
0x180008e7d  mov     [rsp+58h+Reserved7], rax; Reserved7
0x180008e82  xor     r9d, r9d; Reserved2
0x180008e85  mov     [rsp+58h+Reserved6], rcx; Reserved6
0x180008e8a  lea     rax, CsrpReportToWerSvcThread
0x180008e91  mov     [rsp+58h+Reserved5], rax; Reserved5
0x180008e96  xor     r8d, r8d; Reserved1
0x180008e99  mov     [rsp+58h+Reserved4], 0; Reserved4
0x180008ea2  xor     edx, edx; OutThreadHandle
0x180008ea4  mov     rcx, r10; ThreadContext
0x180008ea7  mov     [rsp+58h+Reserved3], 0; Reserved3
0x180008eb0  call    cs:__imp_RtlCreateUserThread
0x180008eb7  nop     dword ptr [rax+rax+00h]
0x180008ebc  test    eax, eax
0x180008ebe  js      short loc_180008EE9
0x180008ec0  mov     rcx, [rsp+58h+Object]; Object
0x180008ec5  lea     r8, [rsp+58h+Interval]; Timeout
0x180008eca  xor     edx, edx; Alertable
0x180008ecc  call    cs:__imp_NtWaitForSingleObject
0x180008ed3  nop     dword ptr [rax+rax+00h]
0x180008ed8  mov     rcx, [rsp+58h+Object]; Handle
0x180008edd  call    cs:__imp_NtClose
0x180008ee4  nop     dword ptr [rax+rax+00h]
0x180008ee9  add     rsp, 58h
0x180008eed  retn
```
