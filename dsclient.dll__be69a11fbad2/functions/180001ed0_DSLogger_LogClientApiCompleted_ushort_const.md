# DSLogger::LogClientApiCompleted(ushort const *)

- ea: `0x180001ed0`
- end: `0x180001ef8`
- name: `?LogClientApiCompleted@DSLogger@@QEAAXPEBG@Z`
- size: `40`
- prototype: `void __fastcall(DSLogger *__hidden this, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001290`
- `0x1800031d0`
- `0x1800032a0`
- `0x180003380`
- `0x180003460`

## callees

- `0x180001ed0`
- `0x18000384c`

## pseudocode

```c
void __fastcall DSLogger::LogClientApiCompleted(DSLogger *this, const unsigned __int16 *a2)
{
  if ( *(_DWORD *)this )
  {
    if ( (Microsoft_WindowsPhone_DataSharingEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(this, DSClientApiCompletedEvent, a2);
  }
}

```

## disassembly

```asm
0x180001ed0  sub     rsp, 28h
0x180001ed4  cmp     dword ptr [rcx], 0
0x180001ed7  jz      short loc_180001EE2
0x180001ed9  test    cs:Microsoft_WindowsPhone_DataSharingEnableBits, 40h
0x180001ee0  jnz     short loc_180001EE7
0x180001ee2  add     rsp, 28h
0x180001ee6  retn
0x180001ee7  mov     r8, rdx
0x180001eea  lea     rdx, DSClientApiCompletedEvent
0x180001ef1  call    McTemplateU0z_EventWriteTransfer
0x180001ef6  jmp     short loc_180001EE2
```
