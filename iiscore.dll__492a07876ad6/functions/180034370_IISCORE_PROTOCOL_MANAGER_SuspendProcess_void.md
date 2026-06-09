# IISCORE_PROTOCOL_MANAGER::SuspendProcess(void)

- ea: `0x180034370`
- end: `0x1800343c2`
- name: `?SuspendProcess@IISCORE_PROTOCOL_MANAGER@@UEAAJXZ`
- size: `82`
- prototype: `__int64 __fastcall(IISCORE_PROTOCOL_MANAGER *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001ead4`
- `0x180034370`

## import_xrefs

- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800343a8`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800343a8`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180034381`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180034381`

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
0x180034370  mov     [rsp+arg_0], rbx
0x180034375  push    rdi
0x180034376  sub     rsp, 20h
0x18003437a  lea     rdi, [rcx+40h]
0x18003437e  mov     rcx, rdi
0x180034381  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180034388  nop     dword ptr [rax+rax+00h]
0x18003438d  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x180034395  jz      short loc_1800343A0
0x180034397  call    ?NotifySuspendProcess@W3_SERVER@@QEAAJXZ; W3_SERVER::NotifySuspendProcess(void)
0x18003439c  mov     ebx, eax
0x18003439e  jmp     short loc_1800343A5
0x1800343a0  mov     ebx, 80004001h
0x1800343a5  mov     rcx, rdi
0x1800343a8  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800343af  nop     dword ptr [rax+rax+00h]
0x1800343b4  mov     eax, ebx
0x1800343b6  mov     rbx, [rsp+28h+arg_0]
0x1800343bb  add     rsp, 20h
0x1800343bf  pop     rdi
0x1800343c0  retn
```
