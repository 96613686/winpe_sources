# IISCORE_PROTOCOL_MANAGER::StopListenerChannel(ushort const *,IWpfListenerChannelCallback *,int)

- ea: `0x1800342a0`
- end: `0x18003436a`
- name: `?StopListenerChannel@IISCORE_PROTOCOL_MANAGER@@UEAAJPEBGPEAVIWpfListenerChannelCallback@@H@Z`
- size: `202`
- prototype: `int(IISCORE_PROTOCOL_MANAGER *__hidden this, const unsigned __int16 *, struct IWpfListenerChannelCallback *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18001a730`
- `0x18001fc38`
- `0x180020148`
- `0x1800202bc`
- `0x180033514`
- `0x1800342a0`
- `0x180038010`

## import_xrefs

- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800342da`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800342da`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180034351`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180034351`

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
0x1800342a0  push    rbx
0x1800342a2  push    rsi
0x1800342a3  push    rdi
0x1800342a4  push    r14
0x1800342a6  sub     rsp, 28h
0x1800342aa  mov     rax, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x1800342b1  mov     ebx, r9d
0x1800342b4  mov     r14, r8
0x1800342b7  mov     rdi, rcx
0x1800342ba  cmp     dword ptr [rax+8], 0
0x1800342be  jz      short loc_1800342D6
0x1800342c0  test    byte ptr [rax+28h], 2
0x1800342c4  jz      short loc_1800342D6
0x1800342c6  cmp     dword ptr [rax+2Ch], 4
0x1800342ca  jb      short loc_1800342D6
0x1800342cc  mov     r8d, ebx; int
0x1800342cf  mov     edx, ebx; int
0x1800342d1  call    ?RaiseEvent@GLOBAL_PROCESS_SHUTDOWN_MODE@IISShutdownEvents@@SAJPEAVCEtwTracer@@HH@Z; IISShutdownEvents::GLOBAL_PROCESS_SHUTDOWN_MODE::RaiseEvent(CEtwTracer *,int,int)
0x1800342d6  lea     rcx, [rdi+50h]
0x1800342da  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800342e1  nop     dword ptr [rax+rax+00h]
0x1800342e6  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x1800342ee  jz      short loc_18003431D
0x1800342f0  mov     edx, ebx; int
0x1800342f2  call    ?StopListen@W3_SERVER@@QEAAXH@Z; W3_SERVER::StopListen(int)
0x1800342f7  call    ?ReportCounters@W3_SERVER@@QEAAJXZ; W3_SERVER::ReportCounters(void)
0x1800342fc  call    ?Terminate@W3_SERVER@@QEAAXXZ; W3_SERVER::Terminate(void)
0x180034301  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; this
0x180034308  test    rcx, rcx
0x18003430b  jz      short loc_180034312
0x18003430d  call    ??_GW3_SERVER@@QEAAPEAXI@Z; W3_SERVER::`scalar deleting destructor'(uint)
0x180034312  mov     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x18003431d  mov     rcx, [rdi+30h]
0x180034321  mov     rax, [rcx]
0x180034324  mov     rax, [rax+8]
0x180034328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003432d  mov     qword ptr [rdi+30h], 0
0x180034335  xor     edx, edx
0x180034337  mov     rax, [r14]
0x18003433a  mov     rcx, r14
0x18003433d  mov     rax, [rax+18h]
0x180034341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034346  lea     rcx, [rdi+50h]
0x18003434a  mov     dword ptr [rdi+4Ch], 0
0x180034351  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180034358  nop     dword ptr [rax+rax+00h]
0x18003435d  xor     eax, eax
0x18003435f  add     rsp, 28h
0x180034363  pop     r14
0x180034365  pop     rdi
0x180034366  pop     rsi
0x180034367  pop     rbx
0x180034368  retn
```
