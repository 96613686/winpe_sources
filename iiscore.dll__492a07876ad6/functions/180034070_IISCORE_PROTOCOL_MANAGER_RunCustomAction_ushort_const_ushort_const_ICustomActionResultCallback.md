# IISCORE_PROTOCOL_MANAGER::RunCustomAction(ushort const *,ushort const *,ICustomActionResultCallback *)

- ea: `0x180034070`
- end: `0x1800340d1`
- name: `?RunCustomAction@IISCORE_PROTOCOL_MANAGER@@UEAAJPEBG0PEAVICustomActionResultCallback@@@Z`
- size: `97`
- prototype: `int(IISCORE_PROTOCOL_MANAGER *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct ICustomActionResultCallback *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000b3e0`
- `0x180034070`

## import_xrefs

- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800340b9`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800340b9`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180034089`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180034089`

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
0x180034070  push    rbx
0x180034072  push    rbp
0x180034073  push    rsi
0x180034074  push    rdi
0x180034075  sub     rsp, 28h
0x180034079  lea     rdi, [rcx+60h]
0x18003407d  mov     rbx, r9
0x180034080  mov     rcx, rdi
0x180034083  mov     rsi, r8
0x180034086  mov     rbp, rdx
0x180034089  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180034090  nop     dword ptr [rax+rax+00h]
0x180034095  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x18003409d  jz      short loc_1800340B1
0x18003409f  mov     r9, rbx; struct ICustomActionResultCallback *
0x1800340a2  mov     r8, rsi; unsigned __int16 *
0x1800340a5  mov     rdx, rbp; unsigned __int16 *
0x1800340a8  call    ?GetWorkerProcessInfo@W3_SERVER@@QEAAJPEBG0PEAVICustomActionResultCallback@@@Z; W3_SERVER::GetWorkerProcessInfo(ushort const *,ushort const *,ICustomActionResultCallback *)
0x1800340ad  mov     ebx, eax
0x1800340af  jmp     short loc_1800340B6
0x1800340b1  mov     ebx, 80004001h
0x1800340b6  mov     rcx, rdi
0x1800340b9  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800340c0  nop     dword ptr [rax+rax+00h]
0x1800340c5  mov     eax, ebx
0x1800340c7  add     rsp, 28h
0x1800340cb  pop     rdi
0x1800340cc  pop     rsi
0x1800340cd  pop     rbp
0x1800340ce  pop     rbx
0x1800340cf  retn
```
