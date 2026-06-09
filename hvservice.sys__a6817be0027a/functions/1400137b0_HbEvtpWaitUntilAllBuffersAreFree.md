# HbEvtpWaitUntilAllBuffersAreFree

- ea: `0x1400137b0`
- end: `0x140013964`
- name: `HbEvtpWaitUntilAllBuffersAreFree`
- size: `436`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140010a78`

## callees

- `0x140001230`
- `0x140001600`
- `0x1400137b0`
- `0x14001396c`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400138a7`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400138a7`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140013933`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140013933`
- `winhvr!WinHvSetEventLogGroupSources` at `0x140013826`
- `winhvr!WinHvSetEventLogGroupSources` at `0x140013826`

## pseudocode

```c
__int64 __fastcall HbEvtpWaitUntilAllBuffersAreFree(__int64 a1, unsigned int a2)
{
  int LogConfiguration; // edi
  int v5; // eax
  __int64 *v6; // rsi
  unsigned int v7; // ebp
  __int64 v8; // rbx
  __int64 v9; // r12
  __int64 v10; // r14
  __int64 *v11; // [rsp+60h] [rbp+8h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+70h] [rbp+18h] BYREF

  v11 = 0;
  if ( a2 == 2 )
    return 0;
  LogConfiguration = HbEvtpGetLogConfiguration(a2, &v11);
  if ( LogConfiguration >= 0 )
  {
    if ( a2 == 1 )
    {
      HbpTraceEvent(3, "HbEvtpWaitUntilAllBuffersAreFree", 2638, "Setting HbEvtpLocalDiagnosticsDisableSession");
      HbEvtpLocalDiagnosticsDisableSession = 1;
    }
    LogConfiguration = WinHvSetEventLogGroupSources(a2, 0);
    if ( LogConfiguration >= 0 )
    {
      HbpTraceEvent(3, "HbEvtpWaitUntilAllBuffersAreFree", 2651, "Flushing event log type %d", a2);
      v5 = HbpEvtpFlushEventLog(a2);
      v6 = v11;
      v7 = 0;
      v8 = 0;
      Interval.QuadPart = -500000;
      for ( LogConfiguration = v5; (unsigned int)v8 < *((_DWORD *)v6 + 2); v8 = (unsigned int)(v8 + 1) )
      {
        v9 = v6[4];
        v10 = 112LL * (unsigned int)v8;
        if ( *(_DWORD *)(*(_QWORD *)(v10 + v9) + 44LL) != 1 )
        {
          do
          {
            if ( v7 >= 0x258 )
              break;
            KeDelayExecutionThread(0, 0, &Interval);
            ++v7;
          }
          while ( *(_DWORD *)(*(_QWORD *)(v10 + v6[4]) + 44LL) != 1 );
        }
        if ( *(_DWORD *)(*(_QWORD *)(v10 + v6[4]) + 44LL) != 1 )
        {
          HbpTraceEvent(
            0,
            "HbEvtpWaitUntilAllBuffersAreFree",
            2706,
            "Timeout waiting for buffer %d to be freed (owned by ETW: %d)",
            v8,
            *(_DWORD *)(v10 + v9 + 88));
          if ( *(_DWORD *)(v10 + v6[4] + 88) )
          {
            HbpTraceEvent(1, "HbEvtpWaitUntilAllBuffersAreFree", 2716, "Force-releasing rundown for buffer %d", v8);
            ExReleaseRundownProtection((PEX_RUNDOWN_REF)(v6[5] + 8 * v8));
          }
        }
      }
    }
  }
  return (unsigned int)LogConfiguration;
}

```

## disassembly

```asm
0x1400137b0  mov     rax, rsp
0x1400137b3  mov     [rax+10h], rbx
0x1400137b7  mov     [rax+20h], rbp
0x1400137bb  mov     [rax+8], rcx
0x1400137bf  push    rsi
0x1400137c0  push    rdi
0x1400137c1  push    r12
0x1400137c3  push    r14
0x1400137c5  push    r15
0x1400137c7  sub     rsp, 30h
0x1400137cb  mov     qword ptr [rax+8], 0
0x1400137d3  mov     ebx, edx
0x1400137d5  cmp     edx, 2
0x1400137d8  jnz     short loc_1400137E1
0x1400137da  xor     eax, eax
0x1400137dc  jmp     loc_14001394C
0x1400137e1  lea     rdx, [rsp+58h+arg_0]
0x1400137e6  mov     ecx, ebx
0x1400137e8  call    HbEvtpGetLogConfiguration
0x1400137ed  mov     edi, eax
0x1400137ef  test    eax, eax
0x1400137f1  js      loc_14001394A
0x1400137f7  mov     esi, 3
0x1400137fc  cmp     ebx, 1
0x1400137ff  jnz     short loc_140013822
0x140013801  lea     r9, aSettingHbevtpl; "Setting HbEvtpLocalDiagnosticsDisableSe"...
0x140013808  mov     r8d, 0A4Eh
0x14001380e  lea     rdx, aHbevtpwaitunti; "HbEvtpWaitUntilAllBuffersAreFree"
0x140013815  mov     ecx, esi
0x140013817  call    HbpTraceEvent
0x14001381c  mov     cs:HbEvtpLocalDiagnosticsDisableSession, bl
0x140013822  xor     edx, edx
0x140013824  mov     ecx, ebx
0x140013826  call    cs:__imp_WinHvSetEventLogGroupSources
0x14001382d  nop     dword ptr [rax+rax+00h]
0x140013832  mov     edi, eax
0x140013834  test    eax, eax
0x140013836  js      loc_14001394A
0x14001383c  lea     r9, aFlushingEventL; "Flushing event log type %d"
0x140013843  mov     [rsp+58h+var_38], ebx
0x140013847  mov     r8d, 0A5Bh
0x14001384d  lea     rdx, aHbevtpwaitunti; "HbEvtpWaitUntilAllBuffersAreFree"
0x140013854  mov     ecx, esi
0x140013856  call    HbpTraceEvent
0x14001385b  mov     ecx, ebx
0x14001385d  call    HbpEvtpFlushEventLog
0x140013862  mov     rsi, [rsp+58h+arg_0]
0x140013867  xor     ebp, ebp
0x140013869  xor     ebx, ebx
0x14001386b  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFF85EE0h
0x140013874  mov     edi, eax
0x140013876  cmp     [rsi+8], ebx
0x140013879  jbe     loc_14001394A
0x14001387f  mov     r12, [rsi+20h]
0x140013883  mov     r15d, ebx
0x140013886  imul    r14, r15, 70h ; 'p'
0x14001388a  mov     rax, [r14+r12]
0x14001388e  mov     ecx, [rax+2Ch]
0x140013891  cmp     ecx, 1
0x140013894  jz      short loc_1400138C5
0x140013896  cmp     ebp, 258h
0x14001389c  jnb     short loc_1400138C5
0x14001389e  lea     r8, [rsp+58h+Interval]; Interval
0x1400138a3  xor     edx, edx; Alertable
0x1400138a5  xor     ecx, ecx; WaitMode
0x1400138a7  call    cs:__imp_KeDelayExecutionThread
0x1400138ae  nop     dword ptr [rax+rax+00h]
0x1400138b3  mov     rax, [rsi+20h]
0x1400138b7  inc     ebp
0x1400138b9  mov     rcx, [r14+rax]
0x1400138bd  mov     eax, [rcx+2Ch]
0x1400138c0  cmp     eax, 1
0x1400138c3  jnz     short loc_140013896
0x1400138c5  mov     rax, [rsi+20h]
0x1400138c9  mov     rcx, [r14+rax]
0x1400138cd  mov     eax, [rcx+2Ch]
0x1400138d0  cmp     eax, 1
0x1400138d3  jz      short loc_14001393F
0x1400138d5  mov     eax, [r14+r12+58h]
0x1400138da  lea     r9, aTimeoutWaiting; "Timeout waiting for buffer %d to be fre"...
0x1400138e1  mov     [rsp+58h+var_30], eax
0x1400138e5  lea     rdx, aHbevtpwaitunti; "HbEvtpWaitUntilAllBuffersAreFree"
0x1400138ec  mov     r8d, 0A92h
0x1400138f2  mov     [rsp+58h+var_38], ebx
0x1400138f6  xor     ecx, ecx
0x1400138f8  call    HbpTraceEvent
0x1400138fd  mov     rax, [rsi+20h]
0x140013901  cmp     dword ptr [r14+rax+58h], 0
0x140013907  jz      short loc_14001393F
0x140013909  lea     r9, aForceReleasing; "Force-releasing rundown for buffer %d"
0x140013910  mov     [rsp+58h+var_38], ebx
0x140013914  mov     r8d, 0A9Ch
0x14001391a  lea     rdx, aHbevtpwaitunti; "HbEvtpWaitUntilAllBuffersAreFree"
0x140013921  mov     ecx, 1
0x140013926  call    HbpTraceEvent
0x14001392b  mov     rax, [rsi+28h]
0x14001392f  lea     rcx, [rax+rbx*8]; RunRef
0x140013933  call    cs:__imp_ExReleaseRundownProtection
0x14001393a  nop     dword ptr [rax+rax+00h]
0x14001393f  inc     ebx
0x140013941  cmp     ebx, [rsi+8]
0x140013944  jb      loc_14001387F
0x14001394a  mov     eax, edi
0x14001394c  mov     rbx, [rsp+58h+arg_8]
0x140013951  mov     rbp, [rsp+58h+arg_18]
0x140013956  add     rsp, 30h
0x14001395a  pop     r15
0x14001395c  pop     r14
0x14001395e  pop     r12
0x140013960  pop     rdi
0x140013961  pop     rsi
0x140013962  retn
```
