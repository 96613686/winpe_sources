# IISCORE_PROTOCOL_MANAGER::StartListenerChannel(ushort const *,IWpfListenerChannelCallback *)

- ea: `0x1800313a0`
- end: `0x180031493`
- name: `?StartListenerChannel@IISCORE_PROTOCOL_MANAGER@@UEAAJPEBGPEAVIWpfListenerChannelCallback@@@Z`
- size: `243`
- prototype: `int(IISCORE_PROTOCOL_MANAGER *__hidden this, const unsigned __int16 *, struct IWpfListenerChannelCallback *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18001c480`
- `0x18001e544`
- `0x18001e7f0`
- `0x180030848`
- `0x180030bac`
- `0x1800313a0`
- `0x180035010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800313be`
- `msvcrt!_wcsicmp` at `0x1800313be`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800313d5`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800313d5`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180031480`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180031480`

## pseudocode

```c
__int64 __fastcall IISCORE_PROTOCOL_MANAGER::StartListenerChannel(
        IISCORE_PROTOCOL_MANAGER *this,
        const unsigned __int16 *a2,
        struct IWpfListenerChannelCallback *a3)
{
  W3_SERVER *v5; // rcx
  int v6; // edi
  int started; // ebx
  W3_SERVER *v8; // rbx
  W3_SERVER *v9; // rcx
  unsigned int v10; // edx

  if ( _wcsicmp(a2, L"http") )
  {
    v6 = 0;
    started = -2147024809;
  }
  else
  {
    CReaderWriterLock3::WriteLock((IISCORE_PROTOCOL_MANAGER *)((char *)this + 80));
    v5 = (IISCORE_PROTOCOL_MANAGER *)((char *)this - 24);
    v6 = 1;
    if ( *((_DWORD *)this + 19) == 1 || (started = IISCORE_PROTOCOL_MANAGER::InitializeGlobals(v5), started >= 0) )
    {
      started = W3_SERVER::InitializeUlAtq(v5);
      if ( started >= 0 )
      {
        v8 = g_pW3Server;
        (**(void (__fastcall ***)(struct IWpfListenerChannelCallback *))a3)(a3);
        *((_QWORD *)v8 + 186) = a3;
        started = W3_SERVER::StartListen(v9);
        if ( started >= 0 )
        {
          (**(void (__fastcall ***)(struct IWpfListenerChannelCallback *))a3)(a3);
          *((_QWORD *)this + 6) = a3;
          (*(void (__fastcall **)(struct IWpfListenerChannelCallback *))(*(_QWORD *)a3 + 16LL))(a3);
LABEL_13:
          CReaderWriterLock3::WriteUnlock((IISCORE_PROTOCOL_MANAGER *)((char *)this + 80));
          return (unsigned int)started;
        }
      }
    }
  }
  if ( g_pW3Server )
  {
    W3_SERVER::Terminate(v5);
    if ( g_pW3Server )
      W3_SERVER::`scalar deleting destructor'(g_pW3Server, v10);
    g_pW3Server = 0;
  }
  if ( v6 )
    goto LABEL_13;
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1800313a0  push    rbx
0x1800313a2  push    rbp
0x1800313a3  push    rsi
0x1800313a4  push    rdi
0x1800313a5  push    r14
0x1800313a7  sub     rsp, 20h
0x1800313ab  mov     rax, rdx
0x1800313ae  mov     rbp, rcx
0x1800313b1  mov     rcx, rax; String1
0x1800313b4  lea     rdx, aHttp_1; "http"
0x1800313bb  mov     rsi, r8
0x1800313be  call    cs:__imp__wcsicmp
0x1800313c4  test    eax, eax
0x1800313c6  jz      short loc_1800313D1
0x1800313c8  xor     edi, edi
0x1800313ca  mov     ebx, 80070057h
0x1800313cf  jmp     short loc_18003144D
0x1800313d1  lea     rcx, [rbp+50h]
0x1800313d5  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800313db  lea     rcx, [rbp-18h]; this
0x1800313df  mov     edi, 1
0x1800313e4  cmp     [rcx+64h], edi
0x1800313e7  jz      short loc_1800313F4
0x1800313e9  call    ?InitializeGlobals@IISCORE_PROTOCOL_MANAGER@@QEAAJXZ; IISCORE_PROTOCOL_MANAGER::InitializeGlobals(void)
0x1800313ee  mov     ebx, eax
0x1800313f0  test    eax, eax
0x1800313f2  js      short loc_180031449
0x1800313f4  call    ?InitializeUlAtq@W3_SERVER@@QEAAJXZ; W3_SERVER::InitializeUlAtq(void)
0x1800313f9  mov     ebx, eax
0x1800313fb  test    eax, eax
0x1800313fd  js      short loc_180031449
0x1800313ff  mov     rax, [rsi]
0x180031402  mov     rcx, rsi
0x180031405  mov     rbx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18003140c  mov     rax, [rax]
0x18003140f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031414  mov     [rbx+5D0h], rsi
0x18003141b  call    ?StartListen@W3_SERVER@@QEAAJXZ; W3_SERVER::StartListen(void)
0x180031420  mov     ebx, eax
0x180031422  test    eax, eax
0x180031424  js      short loc_180031449
0x180031426  mov     rax, [rsi]
0x180031429  mov     rcx, rsi
0x18003142c  mov     rax, [rax]
0x18003142f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031434  mov     [rbp+30h], rsi
0x180031438  mov     rcx, rsi
0x18003143b  mov     rax, [rsi]
0x18003143e  mov     rax, [rax+10h]
0x180031442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031447  jmp     short loc_18003147C
0x180031449  test    ebx, ebx
0x18003144b  jns     short loc_18003147C
0x18003144d  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x180031455  jz      short loc_180031478
0x180031457  call    ?Terminate@W3_SERVER@@QEAAXXZ; W3_SERVER::Terminate(void)
0x18003145c  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; this
0x180031463  test    rcx, rcx
0x180031466  jz      short loc_18003146D
0x180031468  call    ??_GW3_SERVER@@QEAAPEAXI@Z; W3_SERVER::`scalar deleting destructor'(uint)
0x18003146d  mov     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x180031478  test    edi, edi
0x18003147a  jz      short loc_180031486
0x18003147c  lea     rcx, [rbp+50h]
0x180031480  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180031486  mov     eax, ebx
0x180031488  add     rsp, 20h
0x18003148c  pop     r14
0x18003148e  pop     rdi
0x18003148f  pop     rsi
0x180031490  pop     rbp
0x180031491  pop     rbx
0x180031492  retn
```
