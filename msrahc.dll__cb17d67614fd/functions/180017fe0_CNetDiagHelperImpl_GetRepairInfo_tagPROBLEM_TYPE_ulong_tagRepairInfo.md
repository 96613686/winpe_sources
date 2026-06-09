# CNetDiagHelperImpl::GetRepairInfo(tagPROBLEM_TYPE,ulong *,tagRepairInfo * *)

- ea: `0x180017fe0`
- end: `0x180018039`
- name: `?GetRepairInfo@CNetDiagHelperImpl@@UEAAJW4tagPROBLEM_TYPE@@PEAKPEAPEAUtagRepairInfo@@@Z`
- size: `89`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *this, __int64, unsigned int *, struct tagRepairInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180017fe0`
- `0x18001a178`

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
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, 0);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  result = 2147500033LL;
  *a4 = 0;
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x180017fe0  mov     [rsp+arg_0], rbx
0x180017fe5  mov     [rsp+arg_8], rsi
0x180017fea  push    rdi
0x180017feb  sub     rsp, 20h
0x180017fef  mov     rbx, r9
0x180017ff2  mov     rdi, r8
0x180017ff5  mov     rsi, rcx
0x180017ff8  test    r8, r8
0x180017ffb  jnz     short loc_180018002
0x180017ffd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018002  test    rbx, rbx
0x180018005  jnz     short loc_18001800C
0x180018007  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001800c  cmp     dword ptr [rsi+10h], 1
0x180018010  jz      short loc_180018017
0x180018012  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018017  mov     rsi, [rsp+28h+arg_8]
0x18001801c  mov     eax, 80004001h
0x180018021  mov     qword ptr [rbx], 0
0x180018028  mov     rbx, [rsp+28h+arg_0]
0x18001802d  mov     dword ptr [rdi], 0
0x180018033  add     rsp, 20h
0x180018037  pop     rdi
0x180018038  retn
```
