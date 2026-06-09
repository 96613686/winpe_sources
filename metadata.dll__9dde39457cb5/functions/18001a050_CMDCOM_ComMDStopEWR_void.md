# CMDCOM::ComMDStopEWR(void)

- ea: `0x18001a050`
- end: `0x18001a0b8`
- name: `?ComMDStopEWR@CMDCOM@@UEAAJXZ`
- size: `104`
- prototype: `__int64 __fastcall(CMDCOM *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000f0f4`
- `0x18000f2d0`
- `0x18001a050`

## import_xrefs

- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a089`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a089`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a06c`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a06c`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDStopEWR(CMDCOM *this)
{
  unsigned int v1; // edi
  CListenerController *v2; // rbx

  v1 = 0;
  if ( g_pListenerController )
  {
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
    v2 = g_pListenerController;
    if ( g_pListenerController )
      _InterlockedIncrement((volatile signed __int32 *)g_pListenerController + 17);
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
    if ( v2 )
    {
      v1 = CListenerController::Stop(v2, 1);
      CListenerController::Release(v2);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18001a050  mov     [rsp+arg_0], rbx
0x18001a055  push    rdi
0x18001a056  sub     rsp, 20h
0x18001a05a  xor     edi, edi
0x18001a05c  cmp     cs:?g_pListenerController@@3PEAVCListenerController@@EA, rdi; CListenerController * g_pListenerController
0x18001a063  jz      short loc_18001A0AB
0x18001a065  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001a06c  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18001a072  mov     rbx, cs:?g_pListenerController@@3PEAVCListenerController@@EA; CListenerController * g_pListenerController
0x18001a079  test    rbx, rbx
0x18001a07c  jz      short loc_18001A082
0x18001a07e  lock inc dword ptr [rbx+44h]
0x18001a082  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001a089  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18001a08f  test    rbx, rbx
0x18001a092  jz      short loc_18001A0AB
0x18001a094  mov     edx, 1
0x18001a099  mov     rcx, rbx
0x18001a09c  call    ?Stop@CListenerController@@QEAAJW4eSTATE@@@Z; CListenerController::Stop(eSTATE)
0x18001a0a1  mov     rcx, rbx; this
0x18001a0a4  mov     edi, eax
0x18001a0a6  call    ?Release@CListenerController@@QEAAKXZ; CListenerController::Release(void)
0x18001a0ab  mov     rbx, [rsp+28h+arg_0]
0x18001a0b0  mov     eax, edi
0x18001a0b2  add     rsp, 20h
0x18001a0b6  pop     rdi
0x18001a0b7  retn
```
