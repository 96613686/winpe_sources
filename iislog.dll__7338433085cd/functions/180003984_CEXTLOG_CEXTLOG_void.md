# CEXTLOG::~CEXTLOG(void)

- ea: `0x180003984`
- end: `0x180003aac`
- name: `??1CEXTLOG@@MEAA@XZ`
- size: `296`
- prototype: `void __fastcall(CEXTLOG *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180003b30`
- `0x180009640`
- `0x180009940`
- `0x18000a190`

## callees

- `0x180001048`
- `0x180001fcc`
- `0x180003918`
- `0x180003984`
- `0x180003cd8`
- `0x180008550`
- `0x180010010`

## import_xrefs

- `IisRTL!??1TS_RESOURCE@@QEAA@XZ` at `0x180003a66`
- `IisRTL!??1TS_RESOURCE@@QEAA@XZ` at `0x180003a66`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180003a73`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180003a80`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180003a73`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180003a80`
- `IisRTL!??_7CACHED_DATETIME_FORMATS@@6B@` at `0x180003a86`
- `KERNEL32!EnterCriticalSection` at `0x180003a04`
- `KERNEL32!EnterCriticalSection` at `0x180003a04`
- `KERNEL32!LeaveCriticalSection` at `0x180003a51`
- `KERNEL32!LeaveCriticalSection` at `0x180003a51`

## pseudocode

```c
void __fastcall CEXTLOG::~CEXTLOG(CEXTLOG *this)
{
  CLogScript *v1; // rsi
  CCustomPropHashTable *v3; // rbp
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  void *v5; // rcx
  CCustomPropHashTable *v6; // rdi

  v1 = (CEXTLOG *)((char *)this + 408);
  *(_QWORD *)this = &CEXTLOG::`vftable'{for `CLogFileCtrl'};
  v3 = (CEXTLOG *)((char *)this + 3240);
  *((_QWORD *)this + 51) = &CEXTLOG::`vftable'{for `CLogScript'};
  CCustomPropHashTable::ClearTableAndStorage((CEXTLOG *)((char *)this + 3240));
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 332);
  if ( v4 )
  {
    (**v4)(v4, 1);
    *((_QWORD *)this + 332) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 347);
  if ( v5 )
  {
    operator delete(v5);
    *((_QWORD *)this + 347) = 0;
  }
  EnterCriticalSection(&g_csGlobalLoggingProperties);
  if ( g_pGlobalLoggingProperties
    && _InterlockedExchangeAdd((volatile signed __int32 *)g_pGlobalLoggingProperties + 22, 0xFFFFFFFF) == 1 )
  {
    v6 = g_pGlobalLoggingProperties;
    if ( g_pGlobalLoggingProperties )
    {
      CCustomPropHashTable::~CCustomPropHashTable(g_pGlobalLoggingProperties);
      operator delete(v6);
    }
    g_pGlobalLoggingProperties = 0;
  }
  LeaveCriticalSection(&g_csGlobalLoggingProperties);
  CCustomPropHashTable::~CCustomPropHashTable(v3);
  TS_RESOURCE::~TS_RESOURCE((CEXTLOG *)((char *)this + 3144));
  STR::~STR((CEXTLOG *)((char *)this + 2840));
  STR::~STR((CEXTLOG *)((char *)this + 2784));
  *((_QWORD *)this + 198) = CACHED_DATETIME_FORMATS::`vftable';
  CLogScript::~CLogScript(v1);
  CLogFileCtrl::~CLogFileCtrl(this);
}

```

## disassembly

```asm
0x180003984  push    rbx
0x180003986  push    rbp
0x180003987  push    rsi
0x180003988  push    rdi
0x180003989  sub     rsp, 28h
0x18000398d  lea     rsi, [rcx+198h]
0x180003994  mov     rbx, rcx
0x180003997  lea     rax, ??_7CEXTLOG@@6BCLogFileCtrl@@@; const CEXTLOG::`vftable'{for `CLogFileCtrl'}
0x18000399e  mov     [rcx], rax
0x1800039a1  lea     rbp, [rcx+0CA8h]
0x1800039a8  lea     rax, ??_7CEXTLOG@@6BCLogScript@@@; const CEXTLOG::`vftable'{for `CLogScript'}
0x1800039af  mov     rcx, rbp; this
0x1800039b2  mov     [rsi], rax
0x1800039b5  call    ?ClearTableAndStorage@CCustomPropHashTable@@QEAAXXZ; CCustomPropHashTable::ClearTableAndStorage(void)
0x1800039ba  mov     rcx, [rbx+0A60h]
0x1800039c1  test    rcx, rcx
0x1800039c4  jz      short loc_1800039E1
0x1800039c6  mov     rax, [rcx]
0x1800039c9  mov     edx, 1
0x1800039ce  mov     rax, [rax]
0x1800039d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039d6  mov     qword ptr [rbx+0A60h], 0
0x1800039e1  mov     rcx, [rbx+0AD8h]; Block
0x1800039e8  test    rcx, rcx
0x1800039eb  jz      short loc_1800039FD
0x1800039ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800039f2  mov     qword ptr [rbx+0AD8h], 0
0x1800039fd  lea     rcx, ?g_csGlobalLoggingProperties@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003a04  call    cs:__imp_EnterCriticalSection
0x180003a0a  mov     rcx, cs:?g_pGlobalLoggingProperties@@3PEAVCCustomPropHashTable@@EA; CCustomPropHashTable * g_pGlobalLoggingProperties
0x180003a11  test    rcx, rcx
0x180003a14  jz      short loc_180003A4A
0x180003a16  or      eax, 0FFFFFFFFh
0x180003a19  lock xadd [rcx+58h], eax
0x180003a1e  cmp     eax, 1
0x180003a21  jnz     short loc_180003A4A
0x180003a23  mov     rdi, cs:?g_pGlobalLoggingProperties@@3PEAVCCustomPropHashTable@@EA; CCustomPropHashTable * g_pGlobalLoggingProperties
0x180003a2a  test    rdi, rdi
0x180003a2d  jz      short loc_180003A3F
0x180003a2f  mov     rcx, rdi; this
0x180003a32  call    ??1CCustomPropHashTable@@QEAA@XZ; CCustomPropHashTable::~CCustomPropHashTable(void)
0x180003a37  mov     rcx, rdi; Block
0x180003a3a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003a3f  mov     cs:?g_pGlobalLoggingProperties@@3PEAVCCustomPropHashTable@@EA, 0; CCustomPropHashTable * g_pGlobalLoggingProperties
0x180003a4a  lea     rcx, ?g_csGlobalLoggingProperties@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003a51  call    cs:__imp_LeaveCriticalSection
0x180003a57  mov     rcx, rbp; this
0x180003a5a  call    ??1CCustomPropHashTable@@QEAA@XZ; CCustomPropHashTable::~CCustomPropHashTable(void)
0x180003a5f  lea     rcx, [rbx+0C48h]
0x180003a66  call    cs:__imp_??1TS_RESOURCE@@QEAA@XZ; TS_RESOURCE::~TS_RESOURCE(void)
0x180003a6c  lea     rcx, [rbx+0B18h]
0x180003a73  call    cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
0x180003a79  lea     rcx, [rbx+0AE0h]
0x180003a80  call    cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
0x180003a86  mov     rax, cs:__imp_??_7CACHED_DATETIME_FORMATS@@6B@; const CACHED_DATETIME_FORMATS::`vftable'
0x180003a8d  mov     rcx, rsi; this
0x180003a90  mov     [rbx+630h], rax
0x180003a97  call    ??1CLogScript@@MEAA@XZ; CLogScript::~CLogScript(void)
0x180003a9c  mov     rcx, rbx; this
0x180003a9f  add     rsp, 28h
0x180003aa3  pop     rdi
0x180003aa4  pop     rsi
0x180003aa5  pop     rbp
0x180003aa6  pop     rbx
0x180003aa7  jmp     ??1CLogFileCtrl@@MEAA@XZ; CLogFileCtrl::~CLogFileCtrl(void)
```
