# BootScenario::logUnexpectedEvent(_EVENT_RECORD * const)

- ea: `0x180042044`
- end: `0x1800420e9`
- name: `?logUnexpectedEvent@BootScenario@@AEAAXQEAU_EVENT_RECORD@@@Z`
- size: `165`
- prototype: `void __fastcall(BootScenario *__hidden this, struct _EVENT_RECORD *const)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800286b8`

## callees

- `0x180042044`
- `0x1800cf080`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800420ce`
- `ntdll!EtwEventWrite` at `0x1800420ce`
- `ntdll!EtwEventEnabled` at `0x18004207a`
- `ntdll!EtwEventEnabled` at `0x18004207a`

## pseudocode

```c
void __fastcall BootScenario::logUnexpectedEvent(BootScenario *this, struct _EVENT_RECORD *const a2)
{
  unsigned __int64 v2; // rbx
  int v5; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v6[6]; // [rsp+28h] [rbp-40h] BYREF

  v2 = PerfDiagOutput::StatusLog::g_RegHandle;
  if ( PerfDiagOutput::StatusLog::g_RegHandle )
  {
    if ( (unsigned __int8)EtwEventEnabled(PerfDiagOutput::StatusLog::g_RegHandle, PDEvt_Boot_UnexpectedEvent) )
    {
      v5 = *((_DWORD *)this + 6);
      v6[1] = 16;
      v6[0] = &a2->EventHeader.ProviderId;
      v6[3] = 2;
      v6[2] = &a2->EventHeader.EventDescriptor;
      v6[5] = 4;
      v6[4] = &v5;
      EtwEventWrite(v2, PDEvt_Boot_UnexpectedEvent, 3, v6);
    }
  }
}

```

## disassembly

```asm
0x180042044  push    rbp
0x180042046  push    rbx
0x180042047  push    rsi
0x180042048  push    rdi
0x180042049  mov     rbp, rsp
0x18004204c  sub     rsp, 68h
0x180042050  mov     rax, cs:__security_cookie
0x180042057  xor     rax, rsp
0x18004205a  mov     [rbp+var_10], rax
0x18004205e  mov     rbx, cs:?g_RegHandle@StatusLog@PerfDiagOutput@@3_KA; unsigned __int64 PerfDiagOutput::StatusLog::g_RegHandle
0x180042065  mov     rdi, rdx
0x180042068  mov     rsi, rcx
0x18004206b  test    rbx, rbx
0x18004206e  jz      short loc_1800420D4
0x180042070  lea     rdx, PDEvt_Boot_UnexpectedEvent
0x180042077  mov     rcx, rbx
0x18004207a  call    cs:__imp_EtwEventEnabled
0x180042080  test    al, al
0x180042082  jz      short loc_1800420D4
0x180042084  mov     eax, [rsi+18h]
0x180042087  lea     r9, [rbp+var_40]
0x18004208b  mov     [rbp+var_48], eax
0x18004208e  lea     rdx, PDEvt_Boot_UnexpectedEvent
0x180042095  lea     rax, [rdi+18h]
0x180042099  mov     [rbp+var_38], 10h
0x1800420a1  mov     [rbp+var_40], rax
0x1800420a5  mov     r8d, 3
0x1800420ab  lea     rax, [rdi+28h]
0x1800420af  mov     [rbp+var_28], 2
0x1800420b7  mov     [rbp+var_30], rax
0x1800420bb  mov     rcx, rbx
0x1800420be  lea     rax, [rbp+var_48]
0x1800420c2  mov     [rbp+var_18], 4
0x1800420ca  mov     [rbp+var_20], rax
0x1800420ce  call    cs:__imp_EtwEventWrite
0x1800420d4  mov     rcx, [rbp+var_10]
0x1800420d8  xor     rcx, rsp; StackCookie
0x1800420db  call    __security_check_cookie
0x1800420e0  add     rsp, 68h
0x1800420e4  pop     rdi
0x1800420e5  pop     rsi
0x1800420e6  pop     rbx
0x1800420e7  pop     rbp
0x1800420e8  retn
```
