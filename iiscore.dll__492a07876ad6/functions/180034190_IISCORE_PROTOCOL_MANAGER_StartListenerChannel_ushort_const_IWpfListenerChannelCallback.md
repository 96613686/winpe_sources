# IISCORE_PROTOCOL_MANAGER::StartListenerChannel(ushort const *,IWpfListenerChannelCallback *)

- ea: `0x180034190`
- end: `0x180034299`
- name: `?StartListenerChannel@IISCORE_PROTOCOL_MANAGER@@UEAAJPEBGPEAVIWpfListenerChannelCallback@@@Z`
- size: `265`
- prototype: `int(IISCORE_PROTOCOL_MANAGER *__hidden this, const unsigned __int16 *, struct IWpfListenerChannelCallback *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18001dd3c`
- `0x18001ffd4`
- `0x1800202bc`
- `0x180033514`
- `0x1800338ac`
- `0x180034190`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800341ae`
- `msvcrt!_wcsicmp` at `0x1800341ae`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800341ce`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800341ce`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003427f`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003427f`

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
0x180034190  push    rbx
0x180034192  push    rbp
0x180034193  push    rsi
0x180034194  push    rdi
0x180034195  push    r14
0x180034197  sub     rsp, 20h
0x18003419b  mov     rax, rdx
0x18003419e  mov     rbp, rcx
0x1800341a1  mov     rcx, rax; String1
0x1800341a4  lea     rdx, aHttp_1; "http"
0x1800341ab  mov     rsi, r8
0x1800341ae  call    cs:__imp__wcsicmp
0x1800341b5  nop     dword ptr [rax+rax+00h]
0x1800341ba  test    eax, eax
0x1800341bc  jz      short loc_1800341CA
0x1800341be  xor     edi, edi
0x1800341c0  mov     ebx, 80070057h
0x1800341c5  jmp     loc_18003424C
0x1800341ca  lea     rcx, [rbp+50h]
0x1800341ce  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800341d5  nop     dword ptr [rax+rax+00h]
0x1800341da  lea     rcx, [rbp-18h]; this
0x1800341de  mov     edi, 1
0x1800341e3  cmp     [rcx+64h], edi
0x1800341e6  jz      short loc_1800341F3
0x1800341e8  call    ?InitializeGlobals@IISCORE_PROTOCOL_MANAGER@@QEAAJXZ; IISCORE_PROTOCOL_MANAGER::InitializeGlobals(void)
0x1800341ed  mov     ebx, eax
0x1800341ef  test    eax, eax
0x1800341f1  js      short loc_180034248
0x1800341f3  call    ?InitializeUlAtq@W3_SERVER@@QEAAJXZ; W3_SERVER::InitializeUlAtq(void)
0x1800341f8  mov     ebx, eax
0x1800341fa  test    eax, eax
0x1800341fc  js      short loc_180034248
0x1800341fe  mov     rax, [rsi]
0x180034201  mov     rcx, rsi
0x180034204  mov     rbx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18003420b  mov     rax, [rax]
0x18003420e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034213  mov     [rbx+5D0h], rsi
0x18003421a  call    ?StartListen@W3_SERVER@@QEAAJXZ; W3_SERVER::StartListen(void)
0x18003421f  mov     ebx, eax
0x180034221  test    eax, eax
0x180034223  js      short loc_180034248
0x180034225  mov     rax, [rsi]
0x180034228  mov     rcx, rsi
0x18003422b  mov     rax, [rax]
0x18003422e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034233  mov     [rbp+30h], rsi
0x180034237  mov     rcx, rsi
0x18003423a  mov     rax, [rsi]
0x18003423d  mov     rax, [rax+10h]
0x180034241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034246  jmp     short loc_18003427B
0x180034248  test    ebx, ebx
0x18003424a  jns     short loc_18003427B
0x18003424c  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x180034254  jz      short loc_180034277
0x180034256  call    ?Terminate@W3_SERVER@@QEAAXXZ; W3_SERVER::Terminate(void)
0x18003425b  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; this
0x180034262  test    rcx, rcx
0x180034265  jz      short loc_18003426C
0x180034267  call    ??_GW3_SERVER@@QEAAPEAXI@Z; W3_SERVER::`scalar deleting destructor'(uint)
0x18003426c  mov     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x180034277  test    edi, edi
0x180034279  jz      short loc_18003428B
0x18003427b  lea     rcx, [rbp+50h]
0x18003427f  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180034286  nop     dword ptr [rax+rax+00h]
0x18003428b  mov     eax, ebx
0x18003428d  add     rsp, 20h
0x180034291  pop     r14
0x180034293  pop     rdi
0x180034294  pop     rsi
0x180034295  pop     rbp
0x180034296  pop     rbx
0x180034297  retn
```
