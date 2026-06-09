# PerfDiagSecondaryLogons::CSecondaryLogonScenario::EndScenario(void)

- ea: `0x18003ff34`
- end: `0x18003ff90`
- name: `?EndScenario@CSecondaryLogonScenario@PerfDiagSecondaryLogons@@AEAAXXZ`
- size: `92`
- prototype: `void __fastcall(PerfDiagSecondaryLogons::CSecondaryLogonScenario *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800ba54c`
- `0x1800ba770`

## callees

- `0x1800cf080`

## import_xrefs

- `ntdll!EtwEventWriteEndScenario` at `0x18003ff78`
- `ntdll!EtwEventWriteEndScenario` at `0x18003ff78`
- `ntdll!EtwEventActivityIdControl` at `0x18003ff5e`
- `ntdll!EtwEventActivityIdControl` at `0x18003ff5e`

## pseudocode

```c
void __fastcall PerfDiagSecondaryLogons::CSecondaryLogonScenario::EndScenario(
        PerfDiagSecondaryLogons::CSecondaryLogonScenario *this)
{
  GUID v1; // [rsp+20h] [rbp-28h] BYREF

  v1 = GUID_9f41811a_0429_42aa_81b7_cfd4d968411f;
  EtwEventActivityIdControl(2, &v1);
  EtwEventWriteEndScenario(PerfDiagOutput::StatusLog::g_RegHandle, PDEvt_SecondaryLogonScenario_Stop, 0, 0);
}

```

## disassembly

```asm
0x18003ff34  sub     rsp, 48h
0x18003ff38  mov     rax, cs:__security_cookie
0x18003ff3f  xor     rax, rsp
0x18003ff42  mov     [rsp+48h+var_18], rax
0x18003ff47  movups  xmm0, xmmword ptr cs:_GUID_9f41811a_0429_42aa_81b7_cfd4d968411f.Data1
0x18003ff4e  lea     rdx, [rsp+48h+var_28]
0x18003ff53  mov     ecx, 2
0x18003ff58  movdqu  [rsp+48h+var_28], xmm0
0x18003ff5e  call    cs:__imp_EtwEventActivityIdControl
0x18003ff64  mov     rcx, cs:?g_RegHandle@StatusLog@PerfDiagOutput@@3_KA; unsigned __int64 PerfDiagOutput::StatusLog::g_RegHandle
0x18003ff6b  lea     rdx, PDEvt_SecondaryLogonScenario_Stop
0x18003ff72  xor     r9d, r9d
0x18003ff75  xor     r8d, r8d
0x18003ff78  call    cs:__imp_EtwEventWriteEndScenario
0x18003ff7e  mov     rcx, [rsp+48h+var_18]
0x18003ff83  xor     rcx, rsp; StackCookie
0x18003ff86  call    __security_check_cookie
0x18003ff8b  add     rsp, 48h
0x18003ff8f  retn
```
