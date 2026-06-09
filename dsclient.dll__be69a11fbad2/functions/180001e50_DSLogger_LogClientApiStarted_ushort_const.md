# DSLogger::LogClientApiStarted(ushort const *)

- ea: `0x180001e50`
- end: `0x180001e78`
- name: `?LogClientApiStarted@DSLogger@@QEAAXPEBG@Z`
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

- `0x180001e50`
- `0x18000384c`

## pseudocode

```c
void __fastcall DSLogger::LogClientApiStarted(DSLogger *this, const unsigned __int16 *a2)
{
  if ( *(_DWORD *)this )
  {
    if ( (Microsoft_WindowsPhone_DataSharingEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(this, DSClientApiStartedEvent, a2);
  }
}

```

## disassembly

```asm
0x180001e50  sub     rsp, 28h
0x180001e54  cmp     dword ptr [rcx], 0
0x180001e57  jz      short loc_180001E62
0x180001e59  test    cs:Microsoft_WindowsPhone_DataSharingEnableBits, 40h
0x180001e60  jnz     short loc_180001E67
0x180001e62  add     rsp, 28h
0x180001e66  retn
0x180001e67  mov     r8, rdx
0x180001e6a  lea     rdx, DSClientApiStartedEvent
0x180001e71  call    McTemplateU0z_EventWriteTransfer
0x180001e76  jmp     short loc_180001E62
```
