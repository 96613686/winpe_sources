# DSLogger::LogServiceApiCompleted(ushort const *)

- ea: `0x18000c100`
- end: `0x18000c126`
- name: `?LogServiceApiCompleted@DSLogger@@QEAAXPEBG@Z`
- size: `38`
- prototype: `void __fastcall(DSLogger *__hidden this, const unsigned __int16 *)`
- caller_count: `11`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800047f4`
- `0x180005508`
- `0x180007220`
- `0x180007300`
- `0x180007440`
- `0x180007530`
- `0x1800075e0`
- `0x1800076f0`
- `0x180007800`
- `0x180007870`
- `0x1800083c0`

## callees

- `0x18000c100`
- `0x18000c3e4`

## pseudocode

```c
void __fastcall DSLogger::LogServiceApiCompleted(DSLogger *this, const unsigned __int16 *a2)
{
  if ( *(_DWORD *)this )
  {
    if ( (Microsoft_WindowsPhone_DataSharingEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(this, DSServiceApiCompletedEvent, a2);
  }
}

```

## disassembly

```asm
0x18000c100  sub     rsp, 28h
0x18000c104  cmp     dword ptr [rcx], 0
0x18000c107  jz      short loc_18000C121
0x18000c109  test    cs:Microsoft_WindowsPhone_DataSharingEnableBits, 40h
0x18000c110  jz      short loc_18000C121
0x18000c112  mov     r8, rdx
0x18000c115  lea     rdx, DSServiceApiCompletedEvent
0x18000c11c  call    McTemplateU0z_EventWriteTransfer
0x18000c121  add     rsp, 28h
0x18000c125  retn
```
