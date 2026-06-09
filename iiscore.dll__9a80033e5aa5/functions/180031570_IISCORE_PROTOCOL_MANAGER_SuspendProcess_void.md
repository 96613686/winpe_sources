# IISCORE_PROTOCOL_MANAGER::SuspendProcess(void)

- ea: `0x180031570`
- end: `0x1800315b5`
- name: `?SuspendProcess@IISCORE_PROTOCOL_MANAGER@@UEAAJXZ`
- size: `69`
- prototype: `__int64 __fastcall(IISCORE_PROTOCOL_MANAGER *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001d0f8`
- `0x180031570`

## import_xrefs

- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800315a2`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800315a2`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180031581`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180031581`

## pseudocode

```c
__int64 __fastcall IISCORE_PROTOCOL_MANAGER::SuspendProcess(IISCORE_PROTOCOL_MANAGER *this)
{
  CReaderWriterLock3 *v1; // rdi
  W3_SERVER *v2; // rcx
  unsigned int v3; // ebx

  v1 = (IISCORE_PROTOCOL_MANAGER *)((char *)this + 64);
  CReaderWriterLock3::ReadLock((IISCORE_PROTOCOL_MANAGER *)((char *)this + 64));
  if ( g_pW3Server )
    v3 = W3_SERVER::NotifySuspendProcess(v2);
  else
    v3 = -2147467263;
  CReaderWriterLock3::ReadUnlock(v1);
  return v3;
}

```

## disassembly

```asm
0x180031570  mov     [rsp+arg_0], rbx
0x180031575  push    rdi
0x180031576  sub     rsp, 20h
0x18003157a  lea     rdi, [rcx+40h]
0x18003157e  mov     rcx, rdi
0x180031581  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180031587  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x18003158f  jz      short loc_18003159A
0x180031591  call    ?NotifySuspendProcess@W3_SERVER@@QEAAJXZ; W3_SERVER::NotifySuspendProcess(void)
0x180031596  mov     ebx, eax
0x180031598  jmp     short loc_18003159F
0x18003159a  mov     ebx, 80004001h
0x18003159f  mov     rcx, rdi
0x1800315a2  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800315a8  mov     eax, ebx
0x1800315aa  mov     rbx, [rsp+28h+arg_0]
0x1800315af  add     rsp, 20h
0x1800315b3  pop     rdi
0x1800315b4  retn
```
