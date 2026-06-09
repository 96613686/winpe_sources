# IISCORE_PROTOCOL_MANAGER::RunCustomAction(ushort const *,ushort const *,ICustomActionResultCallback *)

- ea: `0x1800312a0`
- end: `0x1800312f4`
- name: `?RunCustomAction@IISCORE_PROTOCOL_MANAGER@@UEAAJPEBG0PEAVICustomActionResultCallback@@@Z`
- size: `84`
- prototype: `int(IISCORE_PROTOCOL_MANAGER *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct ICustomActionResultCallback *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000aae0`
- `0x1800312a0`

## import_xrefs

- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800312e3`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800312e3`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800312b9`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800312b9`

## pseudocode

```c
__int64 __fastcall IISCORE_PROTOCOL_MANAGER::RunCustomAction(
        IISCORE_PROTOCOL_MANAGER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct ICustomActionResultCallback *a4)
{
  CReaderWriterLock3 *v4; // rdi
  W3_SERVER *v8; // rcx
  unsigned int WorkerProcessInfo; // ebx

  v4 = (IISCORE_PROTOCOL_MANAGER *)((char *)this + 96);
  CReaderWriterLock3::ReadLock((IISCORE_PROTOCOL_MANAGER *)((char *)this + 96));
  if ( g_pW3Server )
    WorkerProcessInfo = W3_SERVER::GetWorkerProcessInfo(v8, a2, a3, a4);
  else
    WorkerProcessInfo = -2147467263;
  CReaderWriterLock3::ReadUnlock(v4);
  return WorkerProcessInfo;
}

```

## disassembly

```asm
0x1800312a0  push    rbx
0x1800312a2  push    rbp
0x1800312a3  push    rsi
0x1800312a4  push    rdi
0x1800312a5  sub     rsp, 28h
0x1800312a9  lea     rdi, [rcx+60h]
0x1800312ad  mov     rbx, r9
0x1800312b0  mov     rcx, rdi
0x1800312b3  mov     rsi, r8
0x1800312b6  mov     rbp, rdx
0x1800312b9  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800312bf  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x1800312c7  jz      short loc_1800312DB
0x1800312c9  mov     r9, rbx; struct ICustomActionResultCallback *
0x1800312cc  mov     r8, rsi; unsigned __int16 *
0x1800312cf  mov     rdx, rbp; unsigned __int16 *
0x1800312d2  call    ?GetWorkerProcessInfo@W3_SERVER@@QEAAJPEBG0PEAVICustomActionResultCallback@@@Z; W3_SERVER::GetWorkerProcessInfo(ushort const *,ushort const *,ICustomActionResultCallback *)
0x1800312d7  mov     ebx, eax
0x1800312d9  jmp     short loc_1800312E0
0x1800312db  mov     ebx, 80004001h
0x1800312e0  mov     rcx, rdi
0x1800312e3  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800312e9  mov     eax, ebx
0x1800312eb  add     rsp, 28h
0x1800312ef  pop     rdi
0x1800312f0  pop     rsi
0x1800312f1  pop     rbp
0x1800312f2  pop     rbx
0x1800312f3  retn
```
