# CRPCTimeout::CRPCTimeout(ulong)

- ea: `0x180007540`
- end: `0x1800075b7`
- name: `??0CRPCTimeout@@QEAA@K@Z`
- size: `119`
- prototype: `CRPCTimeout *__fastcall(PVOID Parameter)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c2bc`
- `0x180021bcc`
- `0x180026c04`

## callees

- `0x180007540`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007552`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007552`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000759e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000759e`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18000756d`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18000756d`

## pseudocode

```c
// Hidden C++ exception states: #wind=44
CRPCTimeout *__fastcall CRPCTimeout::CRPCTimeout(PVOID Parameter)
{
  DWORD CurrentThreadId; // eax
  HRESULT v3; // eax

  CurrentThreadId = GetCurrentThreadId();
  *((_BYTE *)Parameter + 4) = 0;
  *(_DWORD *)Parameter = CurrentThreadId;
  *((_QWORD *)Parameter + 2) = 0;
  *((_DWORD *)Parameter + 2) = -2147467259;
  v3 = CoEnableCallCancellation(0);
  *((_DWORD *)Parameter + 2) = v3;
  if ( v3 >= 0 )
    CreateTimerQueueTimer((PHANDLE)Parameter + 2, 0, CBaseRPCTimeout::s_Callback, Parameter, 0x2710u, 0x3E8u, 0);
  return (CRPCTimeout *)Parameter;
}

```

## disassembly

```asm
0x180007540  mov     [rsp+arg_0], rbx
0x180007545  mov     [rsp+arg_8], rsi
0x18000754a  push    rdi
0x18000754b  sub     rsp, 40h
0x18000754f  mov     rbx, rcx
0x180007552  call    cs:__imp_GetCurrentThreadId
0x180007558  xor     esi, esi
0x18000755a  mov     byte ptr [rbx+4], 0
0x18000755e  xor     ecx, ecx; pReserved
0x180007560  mov     [rbx], eax
0x180007562  mov     [rbx+10h], rsi
0x180007566  mov     dword ptr [rbx+8], 80004005h
0x18000756d  call    cs:__imp_CoEnableCallCancellation
0x180007573  mov     [rbx+8], eax
0x180007576  test    eax, eax
0x180007578  js      short loc_1800075A4
0x18000757a  mov     [rsp+48h+Flags], esi; Flags
0x18000757e  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x180007585  mov     [rsp+48h+Period], 3E8h; Period
0x18000758d  lea     rcx, [rbx+10h]; phNewTimer
0x180007591  mov     r9, rbx; Parameter
0x180007594  mov     [rsp+48h+DueTime], 2710h; DueTime
0x18000759c  xor     edx, edx; TimerQueue
0x18000759e  call    cs:__imp_CreateTimerQueueTimer
0x1800075a4  mov     rsi, [rsp+48h+arg_8]
0x1800075a9  mov     rax, rbx
0x1800075ac  mov     rbx, [rsp+48h+arg_0]
0x1800075b1  add     rsp, 40h
0x1800075b5  pop     rdi
0x1800075b6  retn
```
