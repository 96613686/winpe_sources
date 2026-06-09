# CNetDiagHelperImpl::GetRepairInfo(tagPROBLEM_TYPE,ulong *,tagRepairInfo * *)

- ea: `0x18000d6c0`
- end: `0x18000d71a`
- name: `?GetRepairInfo@CNetDiagHelperImpl@@UEAAJW4tagPROBLEM_TYPE@@PEAKPEAPEAUtagRepairInfo@@@Z`
- size: `90`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *this, __int64, unsigned int *, struct tagRepairInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000d6c0`
- `0x18000dd64`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetRepairInfo(
        CNetDiagHelperImpl *this,
        __int64 a2,
        unsigned int *a3,
        struct tagRepairInfo **a4)
{
  __int64 result; // rax

  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, 0, a4);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  result = 2147500033LL;
  *a4 = 0;
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x18000d6c0  mov     [rsp+arg_0], rbx
0x18000d6c5  mov     [rsp+arg_8], rsi
0x18000d6ca  push    rdi
0x18000d6cb  sub     rsp, 20h
0x18000d6cf  mov     rbx, r9
0x18000d6d2  mov     rdi, r8
0x18000d6d5  mov     rsi, rcx
0x18000d6d8  test    r8, r8
0x18000d6db  jnz     short loc_18000D6E2
0x18000d6dd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d6e2  test    rbx, rbx
0x18000d6e5  jnz     short loc_18000D6EC
0x18000d6e7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d6ec  cmp     dword ptr [rsi+10h], 1
0x18000d6f0  jz      short loc_18000D6F7
0x18000d6f2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d6f7  mov     rsi, [rsp+28h+arg_8]
0x18000d6fc  mov     eax, 80004001h
0x18000d701  mov     qword ptr [rbx], 0
0x18000d708  mov     rbx, [rsp+28h+arg_0]
0x18000d70d  mov     dword ptr [rdi], 0
0x18000d713  add     rsp, 20h
0x18000d717  pop     rdi
0x18000d718  retn
```
