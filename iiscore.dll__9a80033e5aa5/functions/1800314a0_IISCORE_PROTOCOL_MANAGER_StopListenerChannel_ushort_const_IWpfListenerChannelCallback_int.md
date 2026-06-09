# IISCORE_PROTOCOL_MANAGER::StopListenerChannel(ushort const *,IWpfListenerChannelCallback *,int)

- ea: `0x1800314a0`
- end: `0x18003155d`
- name: `?StopListenerChannel@IISCORE_PROTOCOL_MANAGER@@UEAAJPEBGPEAVIWpfListenerChannelCallback@@H@Z`
- size: `189`
- prototype: `int(IISCORE_PROTOCOL_MANAGER *__hidden this, const unsigned __int16 *, struct IWpfListenerChannelCallback *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180019178`
- `0x18001e1c0`
- `0x18001e694`
- `0x18001e7f0`
- `0x180030848`
- `0x1800314a0`
- `0x180035010`

## import_xrefs

- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800314da`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800314da`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003154b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003154b`

## pseudocode

```c
__int64 __fastcall IISCORE_PROTOCOL_MANAGER::StopListenerChannel(
        IISCORE_PROTOCOL_MANAGER *this,
        const unsigned __int16 *a2,
        struct IWpfListenerChannelCallback *a3,
        int a4)
{
  W3_SERVER *v7; // rcx
  W3_SERVER *v8; // rcx
  W3_SERVER *v9; // rcx
  unsigned int v10; // edx

  if ( *((_DWORD *)g_pEtwGlobalTracer + 2)
    && (*((_BYTE *)g_pEtwGlobalTracer + 40) & 2) != 0
    && *((_DWORD *)g_pEtwGlobalTracer + 11) >= 4u )
  {
    IISShutdownEvents::GLOBAL_PROCESS_SHUTDOWN_MODE::RaiseEvent(this, a4, a4);
  }
  CReaderWriterLock3::WriteLock((IISCORE_PROTOCOL_MANAGER *)((char *)this + 80));
  if ( g_pW3Server )
  {
    W3_SERVER::StopListen(v7, a4);
    W3_SERVER::ReportCounters(v8);
    W3_SERVER::Terminate(v9);
    if ( g_pW3Server )
      W3_SERVER::`scalar deleting destructor'(g_pW3Server, v10);
    g_pW3Server = 0;
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 8LL))(*((_QWORD *)this + 6));
  *((_QWORD *)this + 6) = 0;
  (*(void (__fastcall **)(struct IWpfListenerChannelCallback *, _QWORD))(*(_QWORD *)a3 + 24LL))(a3, 0);
  *((_DWORD *)this + 19) = 0;
  CReaderWriterLock3::WriteUnlock((IISCORE_PROTOCOL_MANAGER *)((char *)this + 80));
  return 0;
}

```

## disassembly

```asm
0x1800314a0  push    rbx
0x1800314a2  push    rsi
0x1800314a3  push    rdi
0x1800314a4  push    r14
0x1800314a6  sub     rsp, 28h
0x1800314aa  mov     rax, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x1800314b1  mov     ebx, r9d
0x1800314b4  mov     r14, r8
0x1800314b7  mov     rdi, rcx
0x1800314ba  cmp     dword ptr [rax+8], 0
0x1800314be  jz      short loc_1800314D6
0x1800314c0  test    byte ptr [rax+28h], 2
0x1800314c4  jz      short loc_1800314D6
0x1800314c6  cmp     dword ptr [rax+2Ch], 4
0x1800314ca  jb      short loc_1800314D6
0x1800314cc  mov     r8d, ebx; int
0x1800314cf  mov     edx, ebx; int
0x1800314d1  call    ?RaiseEvent@GLOBAL_PROCESS_SHUTDOWN_MODE@IISShutdownEvents@@SAJPEAVCEtwTracer@@HH@Z; IISShutdownEvents::GLOBAL_PROCESS_SHUTDOWN_MODE::RaiseEvent(CEtwTracer *,int,int)
0x1800314d6  lea     rcx, [rdi+50h]
0x1800314da  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800314e0  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x1800314e8  jz      short loc_180031517
0x1800314ea  mov     edx, ebx; int
0x1800314ec  call    ?StopListen@W3_SERVER@@QEAAXH@Z; W3_SERVER::StopListen(int)
0x1800314f1  call    ?ReportCounters@W3_SERVER@@QEAAJXZ; W3_SERVER::ReportCounters(void)
0x1800314f6  call    ?Terminate@W3_SERVER@@QEAAXXZ; W3_SERVER::Terminate(void)
0x1800314fb  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; this
0x180031502  test    rcx, rcx
0x180031505  jz      short loc_18003150C
0x180031507  call    ??_GW3_SERVER@@QEAAPEAXI@Z; W3_SERVER::`scalar deleting destructor'(uint)
0x18003150c  mov     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x180031517  mov     rcx, [rdi+30h]
0x18003151b  mov     rax, [rcx]
0x18003151e  mov     rax, [rax+8]
0x180031522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031527  mov     qword ptr [rdi+30h], 0
0x18003152f  xor     edx, edx
0x180031531  mov     rax, [r14]
0x180031534  mov     rcx, r14
0x180031537  mov     rax, [rax+18h]
0x18003153b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031540  lea     rcx, [rdi+50h]
0x180031544  mov     dword ptr [rdi+4Ch], 0
0x18003154b  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180031551  xor     eax, eax
0x180031553  add     rsp, 28h
0x180031557  pop     r14
0x180031559  pop     rdi
0x18003155a  pop     rsi
0x18003155b  pop     rbx
0x18003155c  retn
```
