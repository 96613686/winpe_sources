# WEBSOCKET_CONTEXT::~WEBSOCKET_CONTEXT(void)

- ea: `0x180003180`
- end: `0x1800032ba`
- name: `??1WEBSOCKET_CONTEXT@@QEAA@XZ`
- size: `314`
- prototype: `void __fastcall(WEBSOCKET_CONTEXT *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180003370`
- `0x180007e70`
- `0x180008080`

## callees

- `0x180003180`
- `0x180003fcc`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003234`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000327f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003234`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000327f`
- `websocket!WebSocketDeleteHandle` at `0x18000324e`
- `websocket!WebSocketDeleteHandle` at `0x18000324e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003241`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003241`

## pseudocode

```c
void __fastcall WEBSOCKET_CONTEXT::~WEBSOCKET_CONTEXT(WEBSOCKET_CONTEXT *this)
{
  __int64 v2; // rax
  volatile signed __int32 *v3; // rcx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx

  *((_DWORD *)this + 3) = 2019783543;
  *(_QWORD *)this = &WEBSOCKET_CONTEXT::`vftable';
  if ( *((_DWORD *)this + 88) )
  {
    v2 = (*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v2 + 8LL))(v2, 29, 1);
  }
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 33);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v3 + 8LL))(v3, 1);
    *((_QWORD *)this + 33) = 0;
  }
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 34);
  if ( v4 )
  {
    (**v4)(v4, 1);
    *((_QWORD *)this + 34) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 392));
  STRU::~STRU((WEBSOCKET_CONTEXT *)((char *)this + 288));
  WebSocketDeleteHandle(*((_QWORD *)this + 17));
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = &WEBSOCKET_IO_MANAGER::`vftable';
  QUEUE::Clear((WEBSOCKET_CONTEXT *)((char *)this + 184));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  *((_QWORD *)this + 4) = &READ_CONTEXT::`vftable';
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
}

```

## disassembly

```asm
0x180003180  mov     [rsp+arg_0], rbx
0x180003185  push    rdi
0x180003186  sub     rsp, 20h
0x18000318a  lea     rax, ??_7WEBSOCKET_CONTEXT@@6B@; const WEBSOCKET_CONTEXT::`vftable'
0x180003191  mov     dword ptr [rcx+0Ch], 78637377h
0x180003198  mov     [rcx], rax
0x18000319b  mov     rdi, rcx
0x18000319e  mov     eax, [rcx+160h]
0x1800031a4  mov     ebx, 1
0x1800031a9  test    eax, eax
0x1800031ab  jz      short loc_1800031D8
0x1800031ad  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800031b4  mov     rax, [rcx]
0x1800031b7  mov     rax, [rax+60h]
0x1800031bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031c0  mov     r9, rax
0x1800031c3  lea     edx, [rbx+1Ch]
0x1800031c6  mov     r8d, ebx
0x1800031c9  mov     rcx, [rax]
0x1800031cc  mov     rax, [rcx+8]
0x1800031d0  mov     rcx, r9
0x1800031d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031d8  mov     rcx, [rdi+108h]
0x1800031df  test    rcx, rcx
0x1800031e2  jz      short loc_180003209
0x1800031e4  or      eax, 0FFFFFFFFh
0x1800031e7  lock xadd [rcx+8], eax
0x1800031ec  cmp     eax, ebx
0x1800031ee  jnz     short loc_1800031FE
0x1800031f0  mov     rax, [rcx]
0x1800031f3  mov     edx, ebx
0x1800031f5  mov     rax, [rax+8]
0x1800031f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031fe  mov     qword ptr [rdi+108h], 0
0x180003209  mov     rcx, [rdi+110h]
0x180003210  test    rcx, rcx
0x180003213  jz      short loc_18000322D
0x180003215  mov     rax, [rcx]
0x180003218  mov     edx, ebx
0x18000321a  mov     rax, [rax]
0x18000321d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003222  mov     qword ptr [rdi+110h], 0
0x18000322d  lea     rcx, [rdi+188h]; lpCriticalSection
0x180003234  call    cs:__imp_DeleteCriticalSection
0x18000323a  lea     rcx, [rdi+120h]
0x180003241  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003247  mov     rcx, [rdi+88h]
0x18000324e  call    cs:__imp_WebSocketDeleteHandle
0x180003254  lea     rax, ??_7WEBSOCKET_IO_MANAGER@@6B@; const WEBSOCKET_IO_MANAGER::`vftable'
0x18000325b  mov     qword ptr [rdi+88h], 0
0x180003266  lea     rbx, [rdi+0B8h]
0x18000326d  mov     [rdi+90h], rax
0x180003274  mov     rcx, rbx; this
0x180003277  call    ?Clear@QUEUE@@QEAAXXZ; QUEUE::Clear(void)
0x18000327c  mov     rcx, rbx; lpCriticalSection
0x18000327f  call    cs:__imp_DeleteCriticalSection
0x180003285  mov     rbx, [rsp+28h+arg_0]
0x18000328a  lea     rax, ??_7READ_CONTEXT@@6B@; const READ_CONTEXT::`vftable'
0x180003291  mov     [rdi+20h], rax
0x180003295  mov     qword ptr [rdi+28h], 0
0x18000329d  mov     qword ptr [rdi+30h], 0
0x1800032a5  mov     qword ptr [rdi+38h], 0
0x1800032ad  mov     dword ptr [rdi+40h], 0
0x1800032b4  add     rsp, 20h
0x1800032b8  pop     rdi
0x1800032b9  retn
```
