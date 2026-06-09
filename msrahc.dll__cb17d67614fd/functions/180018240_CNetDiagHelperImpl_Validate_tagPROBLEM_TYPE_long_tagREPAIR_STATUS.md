# CNetDiagHelperImpl::Validate(tagPROBLEM_TYPE,long *,tagREPAIR_STATUS *)

- ea: `0x180018240`
- end: `0x180018298`
- name: `?Validate@CNetDiagHelperImpl@@UEAAJW4tagPROBLEM_TYPE@@PEAJPEAW4tagREPAIR_STATUS@@@Z`
- size: `88`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *this, __int64, int *, enum tagREPAIR_STATUS *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180018240`
- `0x18001a178`

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
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, 0);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  result = 2147500033LL;
  *a3 = 0;
  *a4 = RS_NOT_IMPLEMENTED;
  return result;
}

```

## disassembly

```asm
0x180018240  mov     [rsp+arg_0], rbx
0x180018245  mov     [rsp+arg_8], rsi
0x18001824a  push    rdi
0x18001824b  sub     rsp, 20h
0x18001824f  mov     rbx, r9
0x180018252  mov     rdi, r8
0x180018255  mov     rsi, rcx
0x180018258  test    r8, r8
0x18001825b  jnz     short loc_180018262
0x18001825d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018262  test    rbx, rbx
0x180018265  jnz     short loc_18001826C
0x180018267  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001826c  cmp     dword ptr [rsi+10h], 1
0x180018270  jz      short loc_180018277
0x180018272  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018277  mov     rsi, [rsp+28h+arg_8]
0x18001827c  mov     eax, 80004001h
0x180018281  mov     dword ptr [rdi], 0
0x180018287  mov     dword ptr [rbx], 0
0x18001828d  mov     rbx, [rsp+28h+arg_0]
0x180018292  add     rsp, 20h
0x180018296  pop     rdi
0x180018297  retn
```
