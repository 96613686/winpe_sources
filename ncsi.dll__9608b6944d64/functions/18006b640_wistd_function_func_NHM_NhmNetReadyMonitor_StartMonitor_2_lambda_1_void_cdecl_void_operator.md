# wistd::__function::__func__NHM::NhmNetReadyMonitor::StartMonitor_::_2_::_lambda_1__void___cdecl(void)_::operator()

- ea: `0x18006b640`
- end: `0x18006b6bd`
- name: `wistd::__function::__func__NHM::NhmNetReadyMonitor::StartMonitor_::_2_::_lambda_1__void___cdecl(void)_::operator()`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180013e48`
- `0x1800249f0`
- `0x18006b640`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b66c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b66c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006b674`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006b674`

## pseudocode

```c
void __fastcall wistd::__function::__func__NHM::NhmNetReadyMonitor::StartMonitor_::_2_::_lambda_1__void___cdecl_void__::operator()(
        __int64 a1)
{
  DWORD CurrentThreadId; // ebx
  DWORD TickCount; // eax

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    TickCount = GetTickCount();
    WPP_SF_dd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      11,
      WPP_a7ccf1d6a806320f7398224d98ab91e8_Traceguids,
      (unsigned __int16)(TickCount / 0x64),
      CurrentThreadId);
  }
  NHM::NhmNetReadyMonitor::ReevaluateAdapterState(*(PTP_TIMER **)(a1 + 8));
}

```

## disassembly

```asm
0x18006b640  mov     [rsp+arg_0], rbx
0x18006b645  push    rdi
0x18006b646  sub     rsp, 30h
0x18006b64a  mov     rdi, rcx
0x18006b64d  mov     rax, cs:WPP_GLOBAL_Control
0x18006b654  lea     rcx, WPP_GLOBAL_Control
0x18006b65b  cmp     rax, rcx
0x18006b65e  jz      short loc_18006B6AA
0x18006b660  test    byte ptr [rax+1Ch], 4
0x18006b664  jz      short loc_18006B6AA
0x18006b666  cmp     byte ptr [rax+19h], 5
0x18006b66a  jb      short loc_18006B6AA
0x18006b66c  call    cs:__imp_GetCurrentThreadId
0x18006b672  mov     ebx, eax
0x18006b674  call    cs:__imp_GetTickCount
0x18006b67a  lea     r8, WPP_a7ccf1d6a806320f7398224d98ab91e8_Traceguids
0x18006b681  mov     [rsp+38h+var_18], ebx
0x18006b685  mov     ecx, eax
0x18006b687  mov     eax, 51EB851Fh
0x18006b68c  mul     ecx
0x18006b68e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b695  shr     edx, 5
0x18006b698  movzx   r9d, dx
0x18006b69c  mov     edx, 0Bh
0x18006b6a1  mov     rcx, [rcx+10h]
0x18006b6a5  call    WPP_SF_dd
0x18006b6aa  mov     rcx, [rdi+8]; this
0x18006b6ae  mov     rbx, [rsp+38h+arg_0]
0x18006b6b3  add     rsp, 30h
0x18006b6b7  pop     rdi
0x18006b6b8  jmp     ?ReevaluateAdapterState@NhmNetReadyMonitor@NHM@@QEBAXXZ; NHM::NhmNetReadyMonitor::ReevaluateAdapterState(void)
```
