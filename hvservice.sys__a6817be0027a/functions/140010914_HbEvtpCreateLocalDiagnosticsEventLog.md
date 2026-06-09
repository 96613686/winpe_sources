# HbEvtpCreateLocalDiagnosticsEventLog

- ea: `0x140010914`
- end: `0x140010a72`
- name: `HbEvtpCreateLocalDiagnosticsEventLog`
- size: `350`
- prototype: `__int64 __fastcall(char *DeferredContext, PVOID Buffer, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140012170`

## callees

- `0x140001600`
- `0x140002ae0`
- `0x140010914`
- `0x140014810`

## import_xrefs

- `ntoskrnl!WmiQueryTraceInformation` at `0x1400109d4`
- `ntoskrnl!WmiQueryTraceInformation` at `0x1400109d4`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140010956`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140010956`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140010a44`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140010a44`

## string_xrefs

- `0x140010973`: `HbEvtpCreateLocalDiagnosticsEventLog`
- `0x1400109a5`: `HbEvtpCreateLocalDiagnosticsEventLog`
- `0x140010998`: `LoggerId already set`

## pseudocode

```c
__int64 __fastcall HbEvtpCreateLocalDiagnosticsEventLog(char *DeferredContext, PVOID Buffer, unsigned int a3)
{
  int EventLog; // ebx
  ULONG RequiredLength; // [rsp+30h] [rbp-50h] BYREF
  _DWORD v9[4]; // [rsp+38h] [rbp-48h] BYREF
  int v10; // [rsp+48h] [rbp-38h]
  __int128 TraceInformation; // [rsp+50h] [rbp-30h] BYREF
  __int128 v12; // [rsp+60h] [rbp-20h]

  RequiredLength = 0;
  TraceInformation = 0;
  v12 = 0;
  if ( ExAcquireRundownProtection(&RunRef) )
  {
    if ( *((_QWORD *)DeferredContext + 41) == -1 )
    {
      EventLog = WmiQueryTraceInformation(TraceSessionSettingsClass, &TraceInformation, 0x20u, &RequiredLength, Buffer);
      if ( EventLog >= 0 )
      {
        if ( DWORD1(TraceInformation) >> 12 )
        {
          v9[0] = DWORD1(TraceInformation) >> 12;
          v9[1] = DWORD1(TraceInformation) >> 12 << 12;
          v9[2] = HIDWORD(TraceInformation);
          v9[3] = DWORD2(v12);
          if ( HIDWORD(v12) == 1 )
            v10 = 2;
          else
            v10 = HIDWORD(v12) != 2;
          EventLog = HbEvtpCreateEventLog(DeferredContext, 1, a3, v9);
        }
        else
        {
          EventLog = -1073741811;
        }
      }
    }
    else
    {
      HbpTraceEvent(0, "HbEvtpCreateLocalDiagnosticsEventLog", 1351, "LoggerId already set");
      EventLog = 255;
    }
    ExReleaseRundownProtection(&RunRef);
    return (unsigned int)EventLog;
  }
  else
  {
    HbpTraceEvent(1, "HbEvtpCreateLocalDiagnosticsEventLog", 1339, "Couldn't acquire event log rundown");
    return 3221225635LL;
  }
}

```

## disassembly

```asm
0x140010914  mov     [rsp-18h+arg_18], rbx
0x140010919  push    rbp
0x14001091a  push    rsi
0x14001091b  push    rdi
0x14001091c  mov     rbp, rsp
0x14001091f  sub     rsp, 80h
0x140010926  mov     rax, cs:__security_cookie
0x14001092d  xor     rax, rsp
0x140010930  mov     [rbp+var_10], rax
0x140010934  xorps   xmm0, xmm0
0x140010937  mov     [rbp+RequiredLength], 0
0x14001093e  mov     rdi, rcx
0x140010941  mov     esi, r8d
0x140010944  lea     rcx, RunRef; RunRef
0x14001094b  mov     rbx, rdx
0x14001094e  movups  [rbp+TraceInformation], xmm0
0x140010952  movups  [rbp+var_20], xmm0
0x140010956  call    cs:__imp_ExAcquireRundownProtection
0x14001095d  nop     dword ptr [rax+rax+00h]
0x140010962  test    al, al
0x140010964  jnz     short loc_14001098E
0x140010966  lea     r9, aCouldnTAcquire_0; "Couldn't acquire event log rundown"
0x14001096d  mov     r8d, 53Bh
0x140010973  lea     rdx, aHbevtpcreatelo; "HbEvtpCreateLocalDiagnosticsEventLog"
0x14001097a  mov     ecx, 1
0x14001097f  call    HbpTraceEvent
0x140010984  mov     eax, 0C00000A3h
0x140010989  jmp     loc_140010A52
0x14001098e  cmp     qword ptr [rdi+148h], 0FFFFFFFFFFFFFFFFh
0x140010996  jz      short loc_1400109BD
0x140010998  lea     r9, aLoggeridAlread; "LoggerId already set"
0x14001099f  mov     r8d, 547h
0x1400109a5  lea     rdx, aHbevtpcreatelo; "HbEvtpCreateLocalDiagnosticsEventLog"
0x1400109ac  xor     ecx, ecx
0x1400109ae  call    HbpTraceEvent
0x1400109b3  mov     ebx, 0FFh
0x1400109b8  jmp     loc_140010A3D
0x1400109bd  mov     r8d, 20h ; ' '; TraceInformationLength
0x1400109c3  mov     [rsp+80h+Buffer], rbx; Buffer
0x1400109c8  lea     r9, [rbp+RequiredLength]; RequiredLength
0x1400109cc  lea     rdx, [rbp+TraceInformation]; TraceInformation
0x1400109d0  lea     ecx, [r8-17h]; TraceInformationClass
0x1400109d4  call    cs:__imp_WmiQueryTraceInformation
0x1400109db  nop     dword ptr [rax+rax+00h]
0x1400109e0  mov     ebx, eax
0x1400109e2  test    eax, eax
0x1400109e4  js      short loc_140010A3D
0x1400109e6  mov     eax, dword ptr [rbp+TraceInformation+4]
0x1400109e9  shr     eax, 0Ch
0x1400109ec  test    eax, eax
0x1400109ee  jnz     short loc_1400109F7
0x1400109f0  mov     ebx, 0C000000Dh
0x1400109f5  jmp     short loc_140010A3D
0x1400109f7  mov     [rbp+var_48], eax
0x1400109fa  shl     eax, 0Ch
0x1400109fd  cmp     dword ptr [rbp+var_20+0Ch], 1
0x140010a01  mov     [rbp+var_44], eax
0x140010a04  mov     eax, dword ptr [rbp+TraceInformation+0Ch]
0x140010a07  mov     [rbp+var_40], eax
0x140010a0a  mov     eax, dword ptr [rbp+var_20+8]
0x140010a0d  mov     [rbp+var_3C], eax
0x140010a10  jnz     short loc_140010A1B
0x140010a12  mov     [rbp+var_38], 2
0x140010a19  jmp     short loc_140010A27
0x140010a1b  xor     eax, eax
0x140010a1d  cmp     dword ptr [rbp+var_20+0Ch], 2
0x140010a21  setnz   al
0x140010a24  mov     [rbp+var_38], eax
0x140010a27  lea     r9, [rbp+var_48]
0x140010a2b  mov     r8d, esi
0x140010a2e  mov     edx, 1
0x140010a33  mov     rcx, rdi; DeferredContext
0x140010a36  call    HbEvtpCreateEventLog
0x140010a3b  mov     ebx, eax
0x140010a3d  lea     rcx, RunRef; RunRef
0x140010a44  call    cs:__imp_ExReleaseRundownProtection
0x140010a4b  nop     dword ptr [rax+rax+00h]
0x140010a50  mov     eax, ebx
0x140010a52  mov     rcx, [rbp+var_10]
0x140010a56  xor     rcx, rsp; StackCookie
0x140010a59  call    __security_check_cookie
0x140010a5e  mov     rbx, [rsp+80h+arg_18]
0x140010a66  add     rsp, 80h
0x140010a6d  pop     rdi
0x140010a6e  pop     rsi
0x140010a6f  pop     rbp
0x140010a70  retn
```
