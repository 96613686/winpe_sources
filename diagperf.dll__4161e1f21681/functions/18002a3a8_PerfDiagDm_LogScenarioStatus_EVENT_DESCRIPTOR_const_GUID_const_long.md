# PerfDiagDm::LogScenarioStatus(_EVENT_DESCRIPTOR const &,_GUID const &,long)

- ea: `0x18002a3a8`
- end: `0x18002a445`
- name: `?LogScenarioStatus@PerfDiagDm@@YAXAEBU_EVENT_DESCRIPTOR@@AEBU_GUID@@J@Z`
- size: `157`
- prototype: `void __fastcall(PerfDiagDm *__hidden this, const struct _EVENT_DESCRIPTOR *, const struct _GUID *, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002e9c0`
- `0x1800aeb90`
- `0x1800aedd0`

## callees

- `0x18002a3a8`
- `0x1800cf080`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18002a422`
- `ntdll!EtwEventWrite` at `0x18002a422`
- `ntdll!EtwEventEnabled` at `0x18002a3e6`
- `ntdll!EtwEventEnabled` at `0x18002a3e6`

## pseudocode

```c
void __fastcall PerfDiagDm::LogScenarioStatus(
        PerfDiagDm *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const struct _GUID *a3)
{
  unsigned __int64 v3; // rbx
  int v6; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v7[4]; // [rsp+28h] [rbp-30h] BYREF

  v3 = PerfDiagOutput::StatusLog::g_RegHandle;
  v6 = 0;
  if ( PerfDiagOutput::StatusLog::g_RegHandle )
  {
    if ( (unsigned __int8)EtwEventEnabled(PerfDiagOutput::StatusLog::g_RegHandle, this) )
    {
      v7[0] = a2;
      v7[2] = &v6;
      v7[1] = 16;
      v7[3] = 4;
      EtwEventWrite(v3, this, 2, v7);
    }
  }
}

```

## disassembly

```asm
0x18002a3a8  mov     [rsp+arg_8], rbx
0x18002a3ad  mov     [rsp+arg_10], rsi
0x18002a3b2  push    rdi
0x18002a3b3  sub     rsp, 50h
0x18002a3b7  mov     rax, cs:__security_cookie
0x18002a3be  xor     rax, rsp
0x18002a3c1  mov     [rsp+58h+var_10], rax
0x18002a3c6  mov     rbx, cs:?g_RegHandle@StatusLog@PerfDiagOutput@@3_KA; unsigned __int64 PerfDiagOutput::StatusLog::g_RegHandle
0x18002a3cd  mov     rsi, rdx
0x18002a3d0  mov     [rsp+58h+var_38], 0
0x18002a3d8  mov     rdi, rcx
0x18002a3db  test    rbx, rbx
0x18002a3de  jz      short loc_18002A428
0x18002a3e0  mov     rdx, rcx
0x18002a3e3  mov     rcx, rbx
0x18002a3e6  call    cs:__imp_EtwEventEnabled
0x18002a3ec  test    al, al
0x18002a3ee  jz      short loc_18002A428
0x18002a3f0  lea     rax, [rsp+58h+var_38]
0x18002a3f5  mov     [rsp+58h+var_30], rsi
0x18002a3fa  lea     r9, [rsp+58h+var_30]
0x18002a3ff  mov     [rsp+58h+var_20], rax
0x18002a404  mov     r8d, 2
0x18002a40a  mov     [rsp+58h+var_28], 10h
0x18002a413  mov     rdx, rdi
0x18002a416  mov     [rsp+58h+var_18], 4
0x18002a41f  mov     rcx, rbx
0x18002a422  call    cs:__imp_EtwEventWrite
0x18002a428  mov     rcx, [rsp+58h+var_10]
0x18002a42d  xor     rcx, rsp; StackCookie
0x18002a430  call    __security_check_cookie
0x18002a435  mov     rbx, [rsp+58h+arg_8]
0x18002a43a  mov     rsi, [rsp+58h+arg_10]
0x18002a43f  add     rsp, 50h
0x18002a443  pop     rdi
0x18002a444  retn
```
