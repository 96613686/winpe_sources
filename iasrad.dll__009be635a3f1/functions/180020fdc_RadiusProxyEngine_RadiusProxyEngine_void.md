# RadiusProxyEngine::~RadiusProxyEngine(void)

- ea: `0x180020fdc`
- end: `0x1800210fe`
- name: `??1RadiusProxyEngine@@QEAA@XZ`
- size: `290`
- prototype: `void __fastcall(RadiusProxyEngine *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18001d7f8`

## callees

- `0x1800094e4`
- `0x18001d31c`
- `0x180020fdc`
- `0x1800211e0`
- `0x180026440`
- `0x180026484`
- `0x1800276e8`
- `0x1800278d8`
- `0x18002d750`
- `0x18002d7d8`
- `0x18002d808`

## import_xrefs

- `msvcrt!free` at `0x18002109e`
- `msvcrt!free` at `0x18002109e`
- `KERNEL32!SwitchToThread` at `0x18002107b`
- `KERNEL32!SwitchToThread` at `0x18002107b`
- `ADVAPI32!CryptReleaseContext` at `0x18002108f`
- `ADVAPI32!CryptReleaseContext` at `0x18002108f`

## pseudocode

```c
void __fastcall RadiusProxyEngine::~RadiusProxyEngine(RadiusProxyEngine *this)
{
  HCRYPTPROV v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &RadiusProxyEngine::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Shutting down the radius proxy engine");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids, "NPSRAD");
  }
  UDPSocket::close((RadiusProxyEngine *)((char *)this + 24));
  UDPSocket::close((RadiusProxyEngine *)((char *)this + 4176));
  HashTableBase::clear((RadiusProxyEngine *)((char *)this + 8520));
  TimerQueue::cancelAllTimers((RadiusProxyEngine *)((char *)this + 8584));
  SwitchToThread();
  v2 = *((_QWORD *)this + 1108);
  if ( v2 )
    CryptReleaseContext(v2, 0);
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
    free(v3);
  RadiusProxyEngine::theProxy = 0;
  CacheBase::~CacheBase((RadiusProxyEngine *)((char *)this + 8768));
  CacheBase::~CacheBase((RadiusProxyEngine *)((char *)this + 8672));
  TimerQueue::~TimerQueue((RadiusProxyEngine *)((char *)this + 8584));
  HashTableBase::~HashTableBase((RadiusProxyEngine *)((char *)this + 8520));
  ServerGroupManager::~ServerGroupManager((RadiusProxyEngine *)((char *)this + 8328));
  UDPSocket::clean((RadiusProxyEngine *)((char *)this + 4176));
  UDPSocket::clean((RadiusProxyEngine *)((char *)this + 24));
}

```

## disassembly

```asm
0x180020fdc  push    rbx
0x180020fde  push    rbp
0x180020fdf  push    rsi
0x180020fe0  push    rdi
0x180020fe1  push    r14
0x180020fe3  sub     rsp, 20h
0x180020fe7  mov     rbx, rcx
0x180020fea  lea     rax, ??_7RadiusProxyEngine@@6B@; const RadiusProxyEngine::`vftable'
0x180020ff1  mov     [rcx], rax
0x180020ff4  lea     rcx, WPP_GLOBAL_Control
0x180020ffb  mov     rax, cs:WPP_GLOBAL_Control
0x180021002  cmp     rax, rcx
0x180021005  jz      short loc_180021045
0x180021007  cmp     byte ptr [rax+19h], 4
0x18002100b  jb      short loc_180021045
0x18002100d  test    dword ptr [rax+1Ch], 100h
0x180021014  jz      short loc_180021045
0x180021016  lea     rcx, aShuttingDownTh; "Shutting down the radius proxy engine"
0x18002101d  call    WppDbgPrint
0x180021022  mov     edx, 29h ; ')'
0x180021027  lea     r9, aNpsrad; "NPSRAD"
0x18002102e  lea     r8, WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids
0x180021035  mov     rcx, cs:WPP_GLOBAL_Control
0x18002103c  mov     rcx, [rcx+10h]
0x180021040  call    WPP_SF_s
0x180021045  lea     rcx, [rbx+18h]; this
0x180021049  call    ?close@UDPSocket@@QEAAXXZ; UDPSocket::close(void)
0x18002104e  lea     rsi, [rbx+1050h]
0x180021055  mov     rcx, rsi; this
0x180021058  call    ?close@UDPSocket@@QEAAXXZ; UDPSocket::close(void)
0x18002105d  lea     rbp, [rbx+2148h]
0x180021064  mov     rcx, rbp; this
0x180021067  call    ?clear@HashTableBase@@QEAAXXZ; HashTableBase::clear(void)
0x18002106c  lea     r14, [rbx+2188h]
0x180021073  mov     rcx, r14; this
0x180021076  call    ?cancelAllTimers@TimerQueue@@QEAAXXZ; TimerQueue::cancelAllTimers(void)
0x18002107b  call    cs:__imp_SwitchToThread
0x180021081  mov     rcx, [rbx+22A0h]; hProv
0x180021088  test    rcx, rcx
0x18002108b  jz      short loc_180021095
0x18002108d  xor     edx, edx; dwFlags
0x18002108f  call    cs:__imp_CryptReleaseContext
0x180021095  mov     rcx, [rbx+10h]; Block
0x180021099  test    rcx, rcx
0x18002109c  jz      short loc_1800210A4
0x18002109e  call    cs:__imp_free
0x1800210a4  mov     cs:?theProxy@RadiusProxyEngine@@0PEAV1@EA, 0; RadiusProxyEngine * RadiusProxyEngine::theProxy
0x1800210af  lea     rcx, [rbx+2240h]; this
0x1800210b6  call    ??1CacheBase@@QEAA@XZ; CacheBase::~CacheBase(void)
0x1800210bb  lea     rcx, [rbx+21E0h]; this
0x1800210c2  call    ??1CacheBase@@QEAA@XZ; CacheBase::~CacheBase(void)
0x1800210c7  mov     rcx, r14; this
0x1800210ca  call    ??1TimerQueue@@QEAA@XZ; TimerQueue::~TimerQueue(void)
0x1800210cf  mov     rcx, rbp; this
0x1800210d2  call    ??1HashTableBase@@QEAA@XZ; HashTableBase::~HashTableBase(void)
0x1800210d7  lea     rcx, [rbx+2088h]; this
0x1800210de  call    ??1ServerGroupManager@@QEAA@XZ; ServerGroupManager::~ServerGroupManager(void)
0x1800210e3  mov     rcx, rsi; this
0x1800210e6  call    ?clean@UDPSocket@@IEAAXXZ; UDPSocket::clean(void)
0x1800210eb  lea     rcx, [rbx+18h]; this
0x1800210ef  add     rsp, 20h
0x1800210f3  pop     r14
0x1800210f5  pop     rdi
0x1800210f6  pop     rsi
0x1800210f7  pop     rbp
0x1800210f8  pop     rbx
0x1800210f9  jmp     ?clean@UDPSocket@@IEAAXXZ; UDPSocket::clean(void)
```
