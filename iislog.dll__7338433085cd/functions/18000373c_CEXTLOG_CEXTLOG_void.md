# CEXTLOG::CEXTLOG(void)

- ea: `0x18000373c`
- end: `0x1800038e9`
- name: `??0CEXTLOG@@QEAA@XZ`
- size: `429`
- prototype: `CEXTLOG *__fastcall(CEXTLOG *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009940`

## callees

- `0x180001008`
- `0x180001f20`
- `0x18000373c`
- `0x18000849c`

## import_xrefs

- `IisRTL!??0STR@@QEAA@XZ` at `0x1800037a7`
- `IisRTL!??0STR@@QEAA@XZ` at `0x1800037b4`
- `IisRTL!??0STR@@QEAA@XZ` at `0x1800037a7`
- `IisRTL!??0STR@@QEAA@XZ` at `0x1800037b4`
- `IisRTL!??0EXTLOG_DATETIME_CACHE@@QEAA@XZ` at `0x18000378c`
- `IisRTL!??0EXTLOG_DATETIME_CACHE@@QEAA@XZ` at `0x18000378c`
- `IisRTL!??0TS_RESOURCE@@QEAA@XZ` at `0x1800037c7`
- `IisRTL!??0TS_RESOURCE@@QEAA@XZ` at `0x1800037c7`
- `IisRTL!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180003823`
- `IisRTL!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800038a1`
- `IisRTL!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180003823`
- `IisRTL!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800038a1`
- `KERNEL32!EnterCriticalSection` at `0x180003846`
- `KERNEL32!EnterCriticalSection` at `0x180003846`
- `KERNEL32!LeaveCriticalSection` at `0x1800038cf`
- `KERNEL32!LeaveCriticalSection` at `0x1800038cf`

## pseudocode

```c
CEXTLOG *__fastcall CEXTLOG::CEXTLOG(CEXTLOG *this)
{
  CLKRHashTable *v2; // rax
  CLKRHashTable *v3; // rbx

  CLogFileCtrl::CLogFileCtrl(this);
  CLogScript::CLogScript((CEXTLOG *)((char *)this + 408));
  *((_QWORD *)this + 197) = 1414;
  *(_QWORD *)this = &CEXTLOG::`vftable'{for `CLogFileCtrl'};
  *((_QWORD *)this + 51) = &CEXTLOG::`vftable'{for `CLogScript'};
  EXTLOG_DATETIME_CACHE::EXTLOG_DATETIME_CACHE((CEXTLOG *)((char *)this + 1584));
  *((_QWORD *)this + 332) = 0;
  *((_QWORD *)this + 347) = 0;
  STR::STR((CEXTLOG *)((char *)this + 2784));
  STR::STR((CEXTLOG *)((char *)this + 2840));
  *((_DWORD *)this + 724) = 0;
  TS_RESOURCE::TS_RESOURCE((CEXTLOG *)((char *)this + 3144));
  CLKRHashTable::CLKRHashTable(
    (CEXTLOG *)((char *)this + 3240),
    "ExtLogC",
    (unsigned __int64 (*)(const void *))ODBC_PARAMETER::QueryCbValue,
    (unsigned int (*)(unsigned __int64))CTypedHashTable<CCustomPropHashTable,LOG_PROPERTY_INFO,char const *,CLKRHashTable,CLKRHashTable::CIterator>::_CalcKeyHash,
    (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<CCustomPropHashTable,LOG_PROPERTY_INFO,char const *,CLKRHashTable,CLKRHashTable::CIterator>::_EqualKeys,
    (void (*)(const void *, int))CTypedHashTable<CCustomPropHashTable,LOG_PROPERTY_INFO,char const *,CLKRHashTable,CLKRHashTable::CIterator>::_AddRefRecord,
    4.0,
    1u,
    0,
    0);
  *((_QWORD *)this + 414) = 0;
  *((_QWORD *)this + 415) = 0;
  *((_DWORD *)this + 832) = 1;
  *((_QWORD *)this + 417) = 0;
  EnterCriticalSection(&g_csGlobalLoggingProperties);
  if ( g_pGlobalLoggingProperties )
  {
    _InterlockedIncrement((volatile signed __int32 *)g_pGlobalLoggingProperties + 22);
  }
  else
  {
    v2 = (CLKRHashTable *)operator new(0x60u);
    v3 = v2;
    if ( v2 )
    {
      CLKRHashTable::CLKRHashTable(
        v2,
        "ExtLogC",
        (unsigned __int64 (*)(const void *))ODBC_PARAMETER::QueryCbValue,
        (unsigned int (*)(unsigned __int64))CTypedHashTable<CCustomPropHashTable,LOG_PROPERTY_INFO,char const *,CLKRHashTable,CLKRHashTable::CIterator>::_CalcKeyHash,
        (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<CCustomPropHashTable,LOG_PROPERTY_INFO,char const *,CLKRHashTable,CLKRHashTable::CIterator>::_EqualKeys,
        (void (*)(const void *, int))CTypedHashTable<CCustomPropHashTable,LOG_PROPERTY_INFO,char const *,CLKRHashTable,CLKRHashTable::CIterator>::_AddRefRecord,
        4.0,
        1u,
        0,
        0);
      *((_QWORD *)v3 + 9) = 0;
      *((_QWORD *)v3 + 10) = 0;
      *((_DWORD *)v3 + 22) = 1;
    }
    else
    {
      v3 = 0;
    }
    g_pGlobalLoggingProperties = v3;
  }
  LeaveCriticalSection(&g_csGlobalLoggingProperties);
  return this;
}

```

## disassembly

```asm
0x18000373c  push    rbx
0x18000373e  push    rsi
0x18000373f  push    rdi
0x180003740  push    r14
0x180003742  push    r15
0x180003744  sub     rsp, 60h
0x180003748  movaps  [rsp+88h+var_38], xmm6
0x18000374d  mov     rdi, rcx
0x180003750  call    ??0CLogFileCtrl@@QEAA@XZ; CLogFileCtrl::CLogFileCtrl(void)
0x180003755  lea     rbx, [rdi+198h]
0x18000375c  mov     rcx, rbx; this
0x18000375f  call    ??0CLogScript@@QEAA@XZ; CLogScript::CLogScript(void)
0x180003764  lea     rax, ??_7CEXTLOG@@6BCLogFileCtrl@@@; const CEXTLOG::`vftable'{for `CLogFileCtrl'}
0x18000376b  mov     qword ptr [rdi+628h], 586h
0x180003776  mov     [rdi], rax
0x180003779  lea     rcx, [rdi+630h]
0x180003780  lea     rax, ??_7CEXTLOG@@6BCLogScript@@@; const CEXTLOG::`vftable'{for `CLogScript'}
0x180003787  xor     esi, esi
0x180003789  mov     [rbx], rax
0x18000378c  call    cs:__imp_??0EXTLOG_DATETIME_CACHE@@QEAA@XZ; EXTLOG_DATETIME_CACHE::EXTLOG_DATETIME_CACHE(void)
0x180003792  lea     rcx, [rdi+0AE0h]
0x180003799  mov     [rdi+0A60h], rsi
0x1800037a0  mov     [rdi+0AD8h], rsi
0x1800037a7  call    cs:__imp_??0STR@@QEAA@XZ; STR::STR(void)
0x1800037ad  lea     rcx, [rdi+0B18h]
0x1800037b4  call    cs:__imp_??0STR@@QEAA@XZ; STR::STR(void)
0x1800037ba  lea     rcx, [rdi+0C48h]
0x1800037c1  mov     [rdi+0B50h], esi
0x1800037c7  call    cs:__imp_??0TS_RESOURCE@@QEAA@XZ; TS_RESOURCE::TS_RESOURCE(void)
0x1800037cd  movsd   xmm6, cs:__real@4010000000000000
0x1800037d5  lea     rbx, [rdi+0CA8h]
0x1800037dc  mov     [rsp+88h+var_40], sil
0x1800037e1  lea     r14, ?_AddRefRecord@?$CTypedHashTable@VCCustomPropHashTable@@ULOG_PROPERTY_INFO@@PEBDVCLKRHashTable@@VCIterator@3@@@CAXPEBXH@Z; CTypedHashTable<CCustomPropHashTable,LOG_PROPERTY_INFO,char const *,CLKRHashTable,CLKRHashTable::CIterator>::_AddRefRecord(void const *,int)
0x1800037e8  mov     [rsp+88h+var_48], esi
0x1800037ec  lea     r15, ?_EqualKeys@?$CTypedHashTable@VCCustomPropHashTable@@ULOG_PROPERTY_INFO@@PEBDVCLKRHashTable@@VCIterator@3@@@CA_N_K0@Z; CTypedHashTable<CCustomPropHashTable,LOG_PROPERTY_INFO,char const *,CLKRHashTable,CLKRHashTable::CIterator>::_EqualKeys(unsigned __int64,unsigned __int64)
0x1800037f3  mov     [rsp+88h+var_50], 1
0x1800037fb  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VCCustomPropHashTable@@ULOG_PROPERTY_INFO@@PEBDVCLKRHashTable@@VCIterator@3@@@CAK_K@Z; CTypedHashTable<CCustomPropHashTable,LOG_PROPERTY_INFO,char const *,CLKRHashTable,CLKRHashTable::CIterator>::_CalcKeyHash(unsigned __int64)
0x180003802  movsd   [rsp+88h+var_58], xmm6
0x180003808  lea     r8, ?QueryCbValue@ODBC_PARAMETER@@QEBA_JXZ; ODBC_PARAMETER::QueryCbValue(void)
0x18000380f  mov     [rsp+88h+var_60], r14
0x180003814  lea     rdx, aExtlogc; "ExtLogC"
0x18000381b  mov     rcx, rbx
0x18000381e  mov     [rsp+88h+var_68], r15
0x180003823  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x180003829  mov     [rbx+48h], rsi
0x18000382d  lea     rcx, ?g_csGlobalLoggingProperties@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003834  mov     [rbx+50h], rsi
0x180003838  mov     dword ptr [rbx+58h], 1
0x18000383f  mov     [rdi+0D08h], rsi
0x180003846  call    cs:__imp_EnterCriticalSection
0x18000384c  mov     rax, cs:?g_pGlobalLoggingProperties@@3PEAVCCustomPropHashTable@@EA; CCustomPropHashTable * g_pGlobalLoggingProperties
0x180003853  test    rax, rax
0x180003856  jnz     short loc_1800038C4
0x180003858  lea     ecx, [rsi+60h]; Size
0x18000385b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003860  mov     rbx, rax
0x180003863  test    rax, rax
0x180003866  jz      short loc_1800038B8
0x180003868  mov     [rsp+88h+var_40], sil
0x18000386d  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VCCustomPropHashTable@@ULOG_PROPERTY_INFO@@PEBDVCLKRHashTable@@VCIterator@3@@@CAK_K@Z; CTypedHashTable<CCustomPropHashTable,LOG_PROPERTY_INFO,char const *,CLKRHashTable,CLKRHashTable::CIterator>::_CalcKeyHash(unsigned __int64)
0x180003874  mov     [rsp+88h+var_48], esi
0x180003878  lea     r8, ?QueryCbValue@ODBC_PARAMETER@@QEBA_JXZ; ODBC_PARAMETER::QueryCbValue(void)
0x18000387f  mov     [rsp+88h+var_50], 1
0x180003887  lea     rdx, aExtlogc; "ExtLogC"
0x18000388e  movsd   [rsp+88h+var_58], xmm6
0x180003894  mov     rcx, rax
0x180003897  mov     [rsp+88h+var_60], r14
0x18000389c  mov     [rsp+88h+var_68], r15
0x1800038a1  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x1800038a7  mov     [rbx+48h], rsi
0x1800038ab  mov     [rbx+50h], rsi
0x1800038af  mov     dword ptr [rbx+58h], 1
0x1800038b6  jmp     short loc_1800038BB
0x1800038b8  mov     rbx, rsi
0x1800038bb  mov     cs:?g_pGlobalLoggingProperties@@3PEAVCCustomPropHashTable@@EA, rbx; CCustomPropHashTable * g_pGlobalLoggingProperties
0x1800038c2  jmp     short loc_1800038C8
0x1800038c4  lock inc dword ptr [rax+58h]
0x1800038c8  lea     rcx, ?g_csGlobalLoggingProperties@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800038cf  call    cs:__imp_LeaveCriticalSection
0x1800038d5  movaps  xmm6, [rsp+88h+var_38]
0x1800038da  mov     rax, rdi
0x1800038dd  add     rsp, 60h
0x1800038e1  pop     r15
0x1800038e3  pop     r14
0x1800038e5  pop     rdi
0x1800038e6  pop     rsi
0x1800038e7  pop     rbx
0x1800038e8  retn
```
