# PerfDiagSecondaryLogons::CSecondaryLogonScenario::LogEventArrival(_EVENT_RECORD * const,_EVENT_DESCRIPTOR const *)

- ea: `0x18003f3ac`
- end: `0x18003f462`
- name: `?LogEventArrival@CSecondaryLogonScenario@PerfDiagSecondaryLogons@@AEAAXQEAU_EVENT_RECORD@@PEBU_EVENT_DESCRIPTOR@@@Z`
- size: `182`
- prototype: `void __fastcall(PerfDiagSecondaryLogons::CSecondaryLogonScenario *__hidden this, struct _EVENT_RECORD *const, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003f1b8`

## callees

- `0x18003f3ac`
- `0x1800cf080`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18003f43b`
- `ntdll!EtwEventWrite` at `0x18003f43b`
- `ntdll!EtwEventEnabled` at `0x18003f3ea`
- `ntdll!EtwEventEnabled` at `0x18003f3ea`

## pseudocode

```c
void __fastcall PerfDiagSecondaryLogons::CSecondaryLogonScenario::LogEventArrival(
        PerfDiagSecondaryLogons::CSecondaryLogonScenario *this,
        struct _EVENT_RECORD *const a2,
        const struct _EVENT_DESCRIPTOR *a3)
{
  unsigned __int64 v3; // rbx
  int v7; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v8[6]; // [rsp+28h] [rbp-38h] BYREF

  v3 = PerfDiagOutput::StatusLog::g_RegHandle;
  if ( PerfDiagOutput::StatusLog::g_RegHandle )
  {
    if ( (unsigned __int8)EtwEventEnabled(PerfDiagOutput::StatusLog::g_RegHandle, a3) )
    {
      v7 = *((_DWORD *)this + 6);
      v8[1] = 16;
      v8[0] = &a2->EventHeader.ProviderId;
      v8[3] = 2;
      v8[2] = &a2->EventHeader.EventDescriptor;
      v8[5] = 4;
      v8[4] = &v7;
      EtwEventWrite(v3, a3, 3, v8);
    }
  }
}

```

## disassembly

```asm
0x18003f3ac  mov     [rsp-18h+arg_0], rbx
0x18003f3b1  mov     [rsp-18h+arg_8], rsi
0x18003f3b6  push    rbp
0x18003f3b7  push    rdi
0x18003f3b8  push    r14
0x18003f3ba  mov     rbp, rsp
0x18003f3bd  sub     rsp, 60h
0x18003f3c1  mov     rax, cs:__security_cookie
0x18003f3c8  xor     rax, rsp
0x18003f3cb  mov     [rbp+var_8], rax
0x18003f3cf  mov     rbx, cs:?g_RegHandle@StatusLog@PerfDiagOutput@@3_KA; unsigned __int64 PerfDiagOutput::StatusLog::g_RegHandle
0x18003f3d6  mov     rdi, r8
0x18003f3d9  mov     rsi, rdx
0x18003f3dc  mov     r14, rcx
0x18003f3df  test    rbx, rbx
0x18003f3e2  jz      short loc_18003F441
0x18003f3e4  mov     rdx, r8
0x18003f3e7  mov     rcx, rbx
0x18003f3ea  call    cs:__imp_EtwEventEnabled
0x18003f3f0  test    al, al
0x18003f3f2  jz      short loc_18003F441
0x18003f3f4  mov     eax, [r14+18h]
0x18003f3f8  lea     r9, [rbp+var_38]
0x18003f3fc  mov     [rbp+var_40], eax
0x18003f3ff  mov     r8d, 3
0x18003f405  lea     rax, [rsi+18h]
0x18003f409  mov     [rbp+var_30], 10h
0x18003f411  mov     [rbp+var_38], rax
0x18003f415  mov     rdx, rdi
0x18003f418  lea     rax, [rsi+28h]
0x18003f41c  mov     [rbp+var_20], 2
0x18003f424  mov     [rbp+var_28], rax
0x18003f428  mov     rcx, rbx
0x18003f42b  lea     rax, [rbp+var_40]
0x18003f42f  mov     [rbp+var_10], 4
0x18003f437  mov     [rbp+var_18], rax
0x18003f43b  call    cs:__imp_EtwEventWrite
0x18003f441  mov     rcx, [rbp+var_8]
0x18003f445  xor     rcx, rsp; StackCookie
0x18003f448  call    __security_check_cookie
0x18003f44d  lea     r11, [rsp+60h+var_s0]
0x18003f452  mov     rbx, [r11+20h]
0x18003f456  mov     rsi, [r11+28h]
0x18003f45a  mov     rsp, r11
0x18003f45d  pop     r14
0x18003f45f  pop     rdi
0x18003f460  pop     rbp
0x18003f461  retn
```
