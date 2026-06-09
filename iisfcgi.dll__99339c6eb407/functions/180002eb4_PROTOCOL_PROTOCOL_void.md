# PROTOCOL::~PROTOCOL(void)

- ea: `0x180002eb4`
- end: `0x180002f59`
- name: `??1PROTOCOL@@AEAA@XZ`
- size: `165`
- prototype: `void __fastcall(PROTOCOL *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800033e0`

## callees

- `0x180002eb4`
- `0x180009128`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002f3b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002f3b`

## pseudocode

```c
void __fastcall PROTOCOL::~PROTOCOL(PROTOCOL *this)
{
  __int64 v2; // rcx
  FCGI_BUFFER *v3; // rcx
  FCGI_BUFFER *v4; // rcx

  *(_QWORD *)this = &PROTOCOL::`vftable'{for `ITRANSPORT_CALLBACK'};
  *((_QWORD *)this + 1) = &PROTOCOL::`vftable'{for `ISEND_QUEUE_CONSUMER'};
  *((_QWORD *)this + 2) = &PROTOCOL::`vftable'{for `ISEND_QUEUE_PRODUCER'};
  v2 = *((_QWORD *)this + 4);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 40LL))(v2, 1);
    *((_QWORD *)this + 4) = 0;
  }
  v3 = (FCGI_BUFFER *)*((_QWORD *)this + 15);
  if ( v3 )
  {
    FCGI_BUFFER::Free(v3);
    *((_QWORD *)this + 15) = 0;
  }
  v4 = (FCGI_BUFFER *)*((_QWORD *)this + 18);
  if ( v4 )
  {
    FCGI_BUFFER::Free(v4);
    *((_QWORD *)this + 18) = 0;
  }
  if ( *((_DWORD *)this + 26) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  *((_QWORD *)this + 23) = 0;
  *((_DWORD *)this + 6) = 1885823846;
}

```

## disassembly

```asm
0x180002eb4  push    rbx
0x180002eb6  sub     rsp, 20h
0x180002eba  lea     rax, ??_7PROTOCOL@@6BITRANSPORT_CALLBACK@@@; const PROTOCOL::`vftable'{for `ITRANSPORT_CALLBACK'}
0x180002ec1  mov     rbx, rcx
0x180002ec4  mov     [rcx], rax
0x180002ec7  lea     rax, ??_7PROTOCOL@@6BISEND_QUEUE_CONSUMER@@@; const PROTOCOL::`vftable'{for `ISEND_QUEUE_CONSUMER'}
0x180002ece  mov     [rcx+8], rax
0x180002ed2  lea     rax, ??_7PROTOCOL@@6BISEND_QUEUE_PRODUCER@@@; const PROTOCOL::`vftable'{for `ISEND_QUEUE_PRODUCER'}
0x180002ed9  mov     [rcx+10h], rax
0x180002edd  mov     rcx, [rcx+20h]
0x180002ee1  test    rcx, rcx
0x180002ee4  jz      short loc_180002EFF
0x180002ee6  mov     rax, [rcx]
0x180002ee9  mov     edx, 1
0x180002eee  mov     rax, [rax+28h]
0x180002ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ef7  mov     qword ptr [rbx+20h], 0
0x180002eff  mov     rcx, [rbx+78h]; this
0x180002f03  test    rcx, rcx
0x180002f06  jz      short loc_180002F15
0x180002f08  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x180002f0d  mov     qword ptr [rbx+78h], 0
0x180002f15  mov     rcx, [rbx+90h]; this
0x180002f1c  test    rcx, rcx
0x180002f1f  jz      short loc_180002F31
0x180002f21  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x180002f26  mov     qword ptr [rbx+90h], 0
0x180002f31  cmp     dword ptr [rbx+68h], 0
0x180002f35  jz      short loc_180002F41
0x180002f37  lea     rcx, [rbx+40h]; lpCriticalSection
0x180002f3b  call    cs:__imp_DeleteCriticalSection
0x180002f41  mov     qword ptr [rbx+0B8h], 0
0x180002f4c  mov     dword ptr [rbx+18h], 70676366h
0x180002f53  add     rsp, 20h
0x180002f57  pop     rbx
0x180002f58  retn
```
