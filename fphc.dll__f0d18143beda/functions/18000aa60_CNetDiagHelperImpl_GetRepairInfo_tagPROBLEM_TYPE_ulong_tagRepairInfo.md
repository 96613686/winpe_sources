# CNetDiagHelperImpl::GetRepairInfo(tagPROBLEM_TYPE,ulong *,tagRepairInfo * *)

- ea: `0x18000aa60`
- end: `0x18000aab9`
- name: `?GetRepairInfo@CNetDiagHelperImpl@@UEAAJW4tagPROBLEM_TYPE@@PEAKPEAPEAUtagRepairInfo@@@Z`
- size: `89`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, enum tagPROBLEM_TYPE, unsigned int *, struct tagRepairInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000aa60`
- `0x18000edb8`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetRepairInfo(
        CNetDiagHelperImpl *this,
        enum tagPROBLEM_TYPE a2,
        unsigned int *a3,
        struct tagRepairInfo **a4)
{
  __int64 result; // rax

  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  result = 2147500033LL;
  *a4 = 0;
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x18000aa60  mov     [rsp+arg_0], rbx
0x18000aa65  mov     [rsp+arg_8], rsi
0x18000aa6a  push    rdi
0x18000aa6b  sub     rsp, 20h
0x18000aa6f  mov     rbx, r9
0x18000aa72  mov     rdi, r8
0x18000aa75  mov     rsi, rcx
0x18000aa78  test    r8, r8
0x18000aa7b  jnz     short loc_18000AA82
0x18000aa7d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000aa82  test    rbx, rbx
0x18000aa85  jnz     short loc_18000AA8C
0x18000aa87  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000aa8c  cmp     dword ptr [rsi+10h], 1
0x18000aa90  jz      short loc_18000AA97
0x18000aa92  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000aa97  mov     rsi, [rsp+28h+arg_8]
0x18000aa9c  mov     eax, 80004001h
0x18000aaa1  mov     qword ptr [rbx], 0
0x18000aaa8  mov     rbx, [rsp+28h+arg_0]
0x18000aaad  mov     dword ptr [rdi], 0
0x18000aab3  add     rsp, 20h
0x18000aab7  pop     rdi
0x18000aab8  retn
```
