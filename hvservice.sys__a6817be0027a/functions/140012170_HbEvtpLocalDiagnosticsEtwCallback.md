# HbEvtpLocalDiagnosticsEtwCallback

- ea: `0x140012170`
- end: `0x14001251c`
- name: `HbEvtpLocalDiagnosticsEtwCallback`
- size: `940`
- prototype: `void __fastcall(__int64, char, unsigned __int16 *, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001600`
- `0x1400020f8`
- `0x140002ae0`
- `0x140010914`
- `0x140010a78`
- `0x140012170`
- `0x14001320c`
- `0x14001396c`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400124d6`
- `ntoskrnl!KeReleaseMutex` at `0x1400124d6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001220f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400123ae`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001220f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400123ae`
- `ntoskrnl!WmiQueryTraceInformation` at `0x1400121d2`
- `ntoskrnl!WmiQueryTraceInformation` at `0x1400121d2`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400124e9`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400124e9`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140012235`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140012235`
- `ntoskrnl!ExAcquireFastMutex` at `0x140012222`
- `ntoskrnl!ExAcquireFastMutex` at `0x140012222`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001244f`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400124c5`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001244f`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400124c5`

## string_xrefs

- `0x140012288`: `Failed to create local diagnostics log with code 0x%x`
- `0x1400122c0`: `Local diagnostics session already existed; updating event sources`

## pseudocode

```c
void __fastcall HbEvtpLocalDiagnosticsEtwCallback(__int64 a1, char a2, unsigned __int16 *a3, __int64 a4)
{
  NTSTATUS v7; // eax
  __int16 v8; // r15
  unsigned int v9; // edi
  int v10; // r15d
  char v11; // bl
  int v12; // eax
  int LocalDiagnosticsEventLog; // eax
  unsigned int v14; // ebp
  int v15; // eax
  const char *v16; // r9
  __int64 v17; // r8
  int v18; // eax
  int v19; // r14d
  NTSTATUS v20; // eax
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-78h]
  ULONG v22; // [rsp+30h] [rbp-68h] BYREF
  union _LARGE_INTEGER v23; // [rsp+38h] [rbp-60h] BYREF
  __int128 v24; // [rsp+40h] [rbp-58h] BYREF
  __int128 v25; // [rsp+50h] [rbp-48h]

  v23.QuadPart = 0;
  v22 = 0;
  v24 = 0;
  v25 = 0;
  v7 = WmiQueryTraceInformation(TraceSessionSettingsClass, &v24, 0x20u, &v22, a3);
  v8 = v25;
  v9 = 0;
  if ( v7 < 0 )
    v8 = 0;
  v10 = v8 & 0x400;
  KeWaitForSingleObject((PVOID)(a4 + 208), Executive, 0, 0, 0);
  ExAcquireFastMutex(&FastMutex);
  if ( !ExAcquireRundownProtection(&RunRef) )
    goto LABEL_35;
  v11 = 1;
  if ( a2 != 1 )
  {
    if ( a2 == 2 )
    {
      v18 = *(_DWORD *)(a4 + 336);
      if ( v18 == 2 )
      {
        v19 = HbpEvtpFlushEventLog(1);
        HbpTraceEvent(1, "HbEvtpLocalDiagnosticsEtwCallback", 1699, "Flush event log returned 0x%x", v19);
        if ( v19 < 0 )
          goto LABEL_33;
        if ( v10 )
        {
          v23.QuadPart = -300000000;
          *(_DWORD *)(a4 + 336) = 3;
          v20 = KeWaitForSingleObject(&HbEvtpCompleteBufferAsyncEvent, Executive, 0, 0, &v23);
          HbpTraceEvent(3, "HbEvtpLocalDiagnosticsEtwCallback", 1718, "Received async event (waitStatus 0x%x).", v20);
          *(_DWORD *)(a4 + 336) = 2;
        }
      }
      else
      {
        if ( v18 == 1 )
        {
          HbpTraceEvent(
            2,
            "HbEvtpLocalDiagnosticsEtwCallback",
            1727,
            "CAPTURE_STATE on disabled provider; returning success");
          goto LABEL_34;
        }
        HbpTraceEvent(
          0,
          "HbEvtpLocalDiagnosticsEtwCallback",
          1733,
          "Invalid state for CAPTURE_STATE: %d",
          *(_DWORD *)(a4 + 336));
        v19 = -1073741436;
      }
      if ( v19 < 0 )
        goto LABEL_33;
LABEL_34:
      ExReleaseRundownProtection(&RunRef);
      goto LABEL_35;
    }
    if ( a2 )
      goto LABEL_34;
    v12 = *(_DWORD *)(a4 + 336);
    if ( v12 == 2 )
    {
      ExReleaseRundownProtection(&RunRef);
      *(_DWORD *)(a4 + 336) = 1;
      if ( (int)HbEvtpDeleteEventLog(a4, 1u) >= 0 )
        goto LABEL_35;
      v11 = 0;
      v12 = *(_DWORD *)(a4 + 336);
      v16 = "Invalid state for CAPTURE_STATE: %d";
      v17 = 1758;
    }
    else
    {
      if ( v12 == 1 )
        goto LABEL_34;
      v16 = "Invalid state for DISABLE_PROVIDER: %d";
      v17 = 1771;
    }
    goto LABEL_32;
  }
  v12 = *(_DWORD *)(a4 + 336);
  if ( v12 != 1 )
  {
    if ( v12 == 2 )
    {
      HbpTraceEvent(
        2,
        "HbEvtpLocalDiagnosticsEtwCallback",
        1656,
        "Local diagnostics session already existed; updating event sources");
LABEL_13:
      *(_QWORD *)(a4 + 328) = *a3;
      v15 = HbEvtpSetLocalDiagnosticsEventSources((__int64)a3);
      if ( v15 < 0 )
      {
        HbpTraceEvent(1, "HbEvtpLocalDiagnosticsEtwCallback", 1680, "Error 0x%x updating event sources", v15);
        goto LABEL_33;
      }
      goto LABEL_34;
    }
    v16 = "Local diagnostics in invalid state: %d";
    v17 = 1660;
LABEL_32:
    LODWORD(Timeout) = v12;
    HbpTraceEvent(0, "HbEvtpLocalDiagnosticsEtwCallback", v17, v16, Timeout);
    goto LABEL_33;
  }
  HbEvtpLocalDiagnosticsDisableSession = 0;
  LOBYTE(v9) = v10 != 0;
  LocalDiagnosticsEventLog = HbEvtpCreateLocalDiagnosticsEventLog((char *)a4, a3, v9);
  if ( LocalDiagnosticsEventLog >= 0 )
  {
    *(_DWORD *)(a4 + 336) = 2;
    goto LABEL_13;
  }
  LODWORD(Timeout) = LocalDiagnosticsEventLog;
  v14 = 3;
  if ( LocalDiagnosticsEventLog != -1073741738 )
    v14 = 0;
  HbpTraceEvent(
    v14,
    "HbEvtpLocalDiagnosticsEtwCallback",
    1642,
    "Failed to create local diagnostics log with code 0x%x",
    Timeout);
LABEL_33:
  HbEvtpWriteEventLog(&HV_EVENTLOG_ENABLE_ETW_TRACE_FAILED, 0, 0);
  if ( v11 )
    goto LABEL_34;
LABEL_35:
  KeReleaseMutex((PRKMUTEX)(a4 + 208), 0);
  ExReleaseFastMutex(&FastMutex);
}

```

## disassembly

```asm
0x140012170  mov     r11, rsp
0x140012173  mov     [r11+8], rbx
0x140012177  mov     [r11+10h], rbp
0x14001217b  push    rsi
0x14001217c  push    rdi
0x14001217d  push    r12
0x14001217f  push    r14
0x140012181  push    r15
0x140012183  sub     rsp, 70h
0x140012187  mov     rax, cs:__security_cookie
0x14001218e  xor     rax, rsp
0x140012191  mov     [rsp+98h+var_38], rax
0x140012196  xorps   xmm0, xmm0
0x140012199  mov     [r11-78h], r8
0x14001219d  mov     r14, r8
0x1400121a0  mov     qword ptr [r11-60h], 0
0x1400121a8  mov     r8d, 20h ; ' '; TraceInformationLength
0x1400121ae  mov     [rsp+98h+var_68], 0
0x1400121b6  mov     rsi, r9
0x1400121b9  mov     bpl, dl
0x1400121bc  lea     r9, [r11-68h]; RequiredLength
0x1400121c0  lea     rdx, [r11-58h]; TraceInformation
0x1400121c4  lea     ecx, [r8-17h]; TraceInformationClass
0x1400121c8  movups  [rsp+98h+var_58], xmm0
0x1400121cd  movups  [rsp+98h+var_48], xmm0
0x1400121d2  call    cs:__imp_WmiQueryTraceInformation
0x1400121d9  nop     dword ptr [rax+rax+00h]
0x1400121de  mov     r15d, dword ptr [rsp+98h+var_48]
0x1400121e3  lea     r12, [rsi+0D0h]
0x1400121ea  xor     ecx, ecx
0x1400121ec  test    eax, eax
0x1400121ee  mov     [rsp+98h+Timeout], rcx; Timeout
0x1400121f3  mov     edi, ecx
0x1400121f5  cmovs   r15d, ecx
0x1400121f9  mov     rcx, r12; Object
0x1400121fc  and     r15d, 400h
0x140012203  setnz   dil
0x140012207  xor     r9d, r9d; Alertable
0x14001220a  xor     r8d, r8d; WaitMode
0x14001220d  xor     edx, edx; WaitReason
0x14001220f  call    cs:__imp_KeWaitForSingleObject
0x140012216  nop     dword ptr [rax+rax+00h]
0x14001221b  lea     rcx, FastMutex; FastMutex
0x140012222  call    cs:__imp_ExAcquireFastMutex
0x140012229  nop     dword ptr [rax+rax+00h]
0x14001222e  lea     rcx, RunRef; RunRef
0x140012235  call    cs:__imp_ExAcquireRundownProtection
0x14001223c  nop     dword ptr [rax+rax+00h]
0x140012241  test    al, al
0x140012243  jz      loc_1400124D1
0x140012249  mov     ebx, 1
0x14001224e  cmp     bpl, bl
0x140012251  jnz     loc_14001232C
0x140012257  mov     eax, [rsi+150h]
0x14001225d  cmp     eax, ebx
0x14001225f  jnz     short loc_1400122B7
0x140012261  mov     r8d, edi
0x140012264  mov     cs:HbEvtpLocalDiagnosticsDisableSession, 0
0x14001226b  mov     rdx, r14; Buffer
0x14001226e  mov     rcx, rsi; DeferredContext
0x140012271  call    HbEvtpCreateLocalDiagnosticsEventLog
0x140012276  test    eax, eax
0x140012278  jns     short loc_1400122AB
0x14001227a  xor     ecx, ecx
0x14001227c  mov     dword ptr [rsp+98h+Timeout], eax
0x140012280  cmp     eax, 0C0000056h
0x140012285  lea     ebp, [rbx+2]
0x140012288  lea     r9, aFailedToCreate; "Failed to create local diagnostics log "...
0x14001228f  mov     r8d, 66Ah
0x140012295  cmovnz  ebp, ecx
0x140012298  lea     rdx, aHbevtplocaldia; "HbEvtpLocalDiagnosticsEtwCallback"
0x14001229f  mov     ecx, ebp
0x1400122a1  call    HbpTraceEvent
0x1400122a6  jmp     loc_1400124A9
0x1400122ab  mov     dword ptr [rsi+150h], 2
0x1400122b5  jmp     short loc_1400122DB
0x1400122b7  mov     edi, 2
0x1400122bc  cmp     eax, edi
0x1400122be  jnz     short loc_14001231A
0x1400122c0  lea     r9, aLocalDiagnosti; "Local diagnostics session already exist"...
0x1400122c7  mov     r8d, 678h
0x1400122cd  lea     rdx, aHbevtplocaldia; "HbEvtpLocalDiagnosticsEtwCallback"
0x1400122d4  mov     ecx, edi
0x1400122d6  call    HbpTraceEvent
0x1400122db  movzx   eax, word ptr [r14]
0x1400122df  mov     rcx, r14
0x1400122e2  mov     [rsi+148h], rax
0x1400122e9  call    HbEvtpSetLocalDiagnosticsEventSources
0x1400122ee  test    eax, eax
0x1400122f0  jns     loc_1400124BE
0x1400122f6  lea     r9, aError0xXUpdati; "Error 0x%x updating event sources"
0x1400122fd  mov     dword ptr [rsp+98h+Timeout], eax
0x140012301  mov     r8d, 690h
0x140012307  lea     rdx, aHbevtplocaldia; "HbEvtpLocalDiagnosticsEtwCallback"
0x14001230e  mov     ecx, ebx
0x140012310  call    HbpTraceEvent
0x140012315  jmp     loc_1400124A9
0x14001231a  lea     r9, aLocalDiagnosti_0; "Local diagnostics in invalid state: %d"
0x140012321  mov     r8d, 67Ch
0x140012327  jmp     loc_140012497
0x14001232c  mov     edi, 2
0x140012331  cmp     bpl, dil
0x140012334  jnz     loc_140012435
0x14001233a  mov     eax, [rsi+150h]
0x140012340  cmp     eax, edi
0x140012342  jnz     loc_1400123E1
0x140012348  mov     ecx, ebx
0x14001234a  call    HbpEvtpFlushEventLog
0x14001234f  mov     r14d, eax
0x140012352  lea     r9, aFlushEventLogR; "Flush event log returned 0x%x"
0x140012359  mov     dword ptr [rsp+98h+Timeout], eax
0x14001235d  mov     r8d, 6A3h
0x140012363  lea     rdx, aHbevtplocaldia; "HbEvtpLocalDiagnosticsEtwCallback"
0x14001236a  mov     ecx, ebx
0x14001236c  call    HbpTraceEvent
0x140012371  test    r14d, r14d
0x140012374  js      loc_1400124A9
0x14001237a  test    r15d, r15d
0x14001237d  jz      loc_14001242A
0x140012383  lea     rax, [rsp+98h+var_60]
0x140012388  mov     qword ptr [rsp+98h+var_60], 0FFFFFFFFEE1E5D00h
0x140012391  lea     ebp, [rdi+1]
0x140012394  mov     [rsp+98h+Timeout], rax; Timeout
0x140012399  xor     r9d, r9d; Alertable
0x14001239c  mov     [rsi+150h], ebp
0x1400123a2  xor     r8d, r8d; WaitMode
0x1400123a5  lea     rcx, HbEvtpCompleteBufferAsyncEvent; Object
0x1400123ac  xor     edx, edx; WaitReason
0x1400123ae  call    cs:__imp_KeWaitForSingleObject
0x1400123b5  nop     dword ptr [rax+rax+00h]
0x1400123ba  lea     r9, aReceivedAsyncE; "Received async event (waitStatus 0x%x)."
0x1400123c1  mov     dword ptr [rsp+98h+Timeout], eax
0x1400123c5  mov     r8d, 6B6h
0x1400123cb  lea     rdx, aHbevtplocaldia; "HbEvtpLocalDiagnosticsEtwCallback"
0x1400123d2  mov     ecx, ebp
0x1400123d4  call    HbpTraceEvent
0x1400123d9  mov     [rsi+150h], edi
0x1400123df  jmp     short loc_14001242A
0x1400123e1  cmp     eax, ebx
0x1400123e3  jnz     short loc_140012405
0x1400123e5  lea     r9, aCaptureStateOn; "CAPTURE_STATE on disabled provider; ret"...
0x1400123ec  mov     r8d, 6BFh
0x1400123f2  lea     rdx, aHbevtplocaldia; "HbEvtpLocalDiagnosticsEtwCallback"
0x1400123f9  mov     ecx, edi
0x1400123fb  call    HbpTraceEvent
0x140012400  jmp     loc_1400124BE
0x140012405  lea     r9, aInvalidStateFo_0; "Invalid state for CAPTURE_STATE: %d"
0x14001240c  mov     dword ptr [rsp+98h+Timeout], eax
0x140012410  mov     r8d, 6C5h
0x140012416  lea     rdx, aHbevtplocaldia; "HbEvtpLocalDiagnosticsEtwCallback"
0x14001241d  xor     ecx, ecx
0x14001241f  call    HbpTraceEvent
0x140012424  mov     r14d, 0C0000184h
0x14001242a  test    r14d, r14d
0x14001242d  jns     loc_1400124BE
0x140012433  jmp     short loc_1400124A9
0x140012435  test    bpl, bpl
0x140012438  jnz     loc_1400124BE
0x14001243e  mov     eax, [rsi+150h]
0x140012444  cmp     eax, edi
0x140012446  jnz     short loc_140012486
0x140012448  lea     rcx, RunRef; RunRef
0x14001244f  call    cs:__imp_ExReleaseRundownProtection
0x140012456  nop     dword ptr [rax+rax+00h]
0x14001245b  mov     edx, ebx
0x14001245d  mov     [rsi+150h], ebx
0x140012463  mov     rcx, rsi
0x140012466  call    HbEvtpDeleteEventLog
0x14001246b  test    eax, eax
0x14001246d  jns     short loc_1400124D1
0x14001246f  xor     bl, bl
0x140012471  mov     eax, [rsi+150h]
0x140012477  lea     r9, aInvalidStateFo_0; "Invalid state for CAPTURE_STATE: %d"
0x14001247e  mov     r8d, 6DEh
0x140012484  jmp     short loc_140012497
0x140012486  cmp     eax, ebx
0x140012488  jz      short loc_1400124BE
0x14001248a  lea     r9, aInvalidStateFo; "Invalid state for DISABLE_PROVIDER: %d"
0x140012491  mov     r8d, 6EBh
0x140012497  lea     rdx, aHbevtplocaldia; "HbEvtpLocalDiagnosticsEtwCallback"
0x14001249e  mov     dword ptr [rsp+98h+Timeout], eax
0x1400124a2  xor     ecx, ecx
0x1400124a4  call    HbpTraceEvent
0x1400124a9  xor     r8d, r8d; UserData
0x1400124ac  lea     rcx, HV_EVENTLOG_ENABLE_ETW_TRACE_FAILED; EventDescriptor
0x1400124b3  xor     edx, edx; UserDataCount
0x1400124b5  call    HbEvtpWriteEventLog
0x1400124ba  test    bl, bl
0x1400124bc  jz      short loc_1400124D1
0x1400124be  lea     rcx, RunRef; RunRef
0x1400124c5  call    cs:__imp_ExReleaseRundownProtection
0x1400124cc  nop     dword ptr [rax+rax+00h]
0x1400124d1  xor     edx, edx; Wait
0x1400124d3  mov     rcx, r12; Mutex
0x1400124d6  call    cs:__imp_KeReleaseMutex
0x1400124dd  nop     dword ptr [rax+rax+00h]
0x1400124e2  lea     rcx, FastMutex; FastMutex
0x1400124e9  call    cs:__imp_ExReleaseFastMutex
0x1400124f0  nop     dword ptr [rax+rax+00h]
0x1400124f5  mov     rcx, [rsp+98h+var_38]
0x1400124fa  xor     rcx, rsp; StackCookie
0x1400124fd  call    __security_check_cookie
0x140012502  lea     r11, [rsp+98h+var_28]
0x140012507  mov     rbx, [r11+30h]
0x14001250b  mov     rbp, [r11+38h]
0x14001250f  mov     rsp, r11
0x140012512  pop     r15
0x140012514  pop     r14
0x140012516  pop     r12
0x140012518  pop     rdi
0x140012519  pop     rsi
0x14001251a  retn
```
