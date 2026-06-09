# CInstrument::~CInstrument(void)

- ea: `0x18000ebdc`
- end: `0x18000ec46`
- name: `??1CInstrument@@AEAA@XZ`
- size: `106`
- prototype: `void __fastcall(CInstrument *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000ef40`

## callees

- `0x1800012c4`
- `0x18000ebdc`
- `0x18000ec80`
- `0x180014034`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ec07`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ec07`

## pseudocode

```c
void __fastcall CInstrument::~CInstrument(CInstrument *this)
{
  unsigned __int64 v2; // rdx
  _QWORD *v3; // rbx
  CWaveObj *v4; // rcx

  *(_QWORD *)this = &CInstrument::`vftable'{for `IDirectMusicInstrument'};
  *((_QWORD *)this + 1) = &CInstrument::`vftable'{for `IDirectMusicInstrumentPrivate'};
  CInstrument::Cleanup(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  while ( 1 )
  {
    v3 = (_QWORD *)*((_QWORD *)this + 11);
    if ( !v3 )
      break;
    v4 = (CWaveObj *)*((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = *v3;
    *v3 = 0;
    CWaveObj::~CWaveObj(v4, v2);
    operator delete(v3, 0xC0u);
  }
}

```

## disassembly

```asm
0x18000ebdc  mov     [rsp+arg_0], rbx
0x18000ebe1  push    rdi
0x18000ebe2  sub     rsp, 20h
0x18000ebe6  lea     rax, ??_7CInstrument@@6BIDirectMusicInstrument@@@; const CInstrument::`vftable'{for `IDirectMusicInstrument'}
0x18000ebed  mov     rdi, rcx
0x18000ebf0  mov     [rcx], rax
0x18000ebf3  lea     rax, ??_7CInstrument@@6BIDirectMusicInstrumentPrivate@@@; const CInstrument::`vftable'{for `IDirectMusicInstrumentPrivate'}
0x18000ebfa  mov     [rcx+8], rax
0x18000ebfe  call    ?Cleanup@CInstrument@@AEAAXXZ; CInstrument::Cleanup(void)
0x18000ec03  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000ec07  call    cs:__imp_DeleteCriticalSection
0x18000ec0d  mov     rbx, [rdi+58h]
0x18000ec11  test    rbx, rbx
0x18000ec14  jz      short loc_18000EC3B
0x18000ec16  mov     rax, [rbx]
0x18000ec19  mov     rcx, rbx; this
0x18000ec1c  mov     [rdi+58h], rax
0x18000ec20  mov     qword ptr [rbx], 0
0x18000ec27  call    ??1CWaveObj@@AEAA@XZ; CWaveObj::~CWaveObj(void)
0x18000ec2c  mov     edx, 0C0h; unsigned __int64
0x18000ec31  mov     rcx, rbx; void *
0x18000ec34  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ec39  jmp     short loc_18000EC0D
0x18000ec3b  mov     rbx, [rsp+28h+arg_0]
0x18000ec40  add     rsp, 20h
0x18000ec44  pop     rdi
0x18000ec45  retn
```
