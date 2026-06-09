# CNetDiagHelperImpl::Validate(tagPROBLEM_TYPE,long *,tagREPAIR_STATUS *)

- ea: `0x18000ad00`
- end: `0x18000ad58`
- name: `?Validate@CNetDiagHelperImpl@@UEAAJW4tagPROBLEM_TYPE@@PEAJPEAW4tagREPAIR_STATUS@@@Z`
- size: `88`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, enum tagPROBLEM_TYPE, int *, enum tagREPAIR_STATUS *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000ad00`
- `0x18000edb8`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::Validate(
        CNetDiagHelperImpl *this,
        enum tagPROBLEM_TYPE a2,
        int *a3,
        enum tagREPAIR_STATUS *a4)
{
  __int64 result; // rax

  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  result = 2147500033LL;
  *a3 = 0;
  *a4 = RS_NOT_IMPLEMENTED;
  return result;
}

```

## disassembly

```asm
0x18000ad00  mov     [rsp+arg_0], rbx
0x18000ad05  mov     [rsp+arg_8], rsi
0x18000ad0a  push    rdi
0x18000ad0b  sub     rsp, 20h
0x18000ad0f  mov     rbx, r9
0x18000ad12  mov     rdi, r8
0x18000ad15  mov     rsi, rcx
0x18000ad18  test    r8, r8
0x18000ad1b  jnz     short loc_18000AD22
0x18000ad1d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ad22  test    rbx, rbx
0x18000ad25  jnz     short loc_18000AD2C
0x18000ad27  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ad2c  cmp     dword ptr [rsi+10h], 1
0x18000ad30  jz      short loc_18000AD37
0x18000ad32  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ad37  mov     rsi, [rsp+28h+arg_8]
0x18000ad3c  mov     eax, 80004001h
0x18000ad41  mov     dword ptr [rdi], 0
0x18000ad47  mov     dword ptr [rbx], 0
0x18000ad4d  mov     rbx, [rsp+28h+arg_0]
0x18000ad52  add     rsp, 20h
0x18000ad56  pop     rdi
0x18000ad57  retn
```
