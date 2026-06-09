# CNetDiagHelperImpl::Validate(tagPROBLEM_TYPE,long *,tagREPAIR_STATUS *)

- ea: `0x18000d980`
- end: `0x18000d9d9`
- name: `?Validate@CNetDiagHelperImpl@@UEAAJW4tagPROBLEM_TYPE@@PEAJPEAW4tagREPAIR_STATUS@@@Z`
- size: `89`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *this, __int64, int *, enum tagREPAIR_STATUS *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000d980`
- `0x18000dd64`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::Validate(
        CNetDiagHelperImpl *this,
        __int64 a2,
        int *a3,
        enum tagREPAIR_STATUS *a4)
{
  __int64 result; // rax

  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, 0, a4);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  result = 2147500033LL;
  *a3 = 0;
  *a4 = RS_NOT_IMPLEMENTED;
  return result;
}

```

## disassembly

```asm
0x18000d980  mov     [rsp+arg_0], rbx
0x18000d985  mov     [rsp+arg_8], rsi
0x18000d98a  push    rdi
0x18000d98b  sub     rsp, 20h
0x18000d98f  mov     rbx, r9
0x18000d992  mov     rdi, r8
0x18000d995  mov     rsi, rcx
0x18000d998  test    r8, r8
0x18000d99b  jnz     short loc_18000D9A2
0x18000d99d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d9a2  test    rbx, rbx
0x18000d9a5  jnz     short loc_18000D9AC
0x18000d9a7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d9ac  cmp     dword ptr [rsi+10h], 1
0x18000d9b0  jz      short loc_18000D9B7
0x18000d9b2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d9b7  mov     rsi, [rsp+28h+arg_8]
0x18000d9bc  mov     eax, 80004001h
0x18000d9c1  mov     dword ptr [rdi], 0
0x18000d9c7  mov     dword ptr [rbx], 0
0x18000d9cd  mov     rbx, [rsp+28h+arg_0]
0x18000d9d2  add     rsp, 20h
0x18000d9d6  pop     rdi
0x18000d9d7  retn
```
