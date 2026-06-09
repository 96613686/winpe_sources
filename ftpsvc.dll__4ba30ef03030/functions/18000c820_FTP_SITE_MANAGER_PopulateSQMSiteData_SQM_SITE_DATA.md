# FTP_SITE_MANAGER::PopulateSQMSiteData(SQM_SITE_DATA *)

- ea: `0x18000c820`
- end: `0x18000c9c2`
- name: `?PopulateSQMSiteData@FTP_SITE_MANAGER@@QEAAXPEAUSQM_SITE_DATA@@@Z`
- size: `418`
- prototype: `void __fastcall(FTP_SITE_MANAGER *__hidden this, struct SQM_SITE_DATA *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180005b60`

## callees

- `0x180009090`
- `0x18000c820`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c8b6`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c8b6`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000c946`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000c946`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18000c861`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18000c888`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18000c96c`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18000c861`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18000c888`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18000c96c`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18000c853`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18000c853`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18000c87a`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18000c95e`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18000c87a`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18000c95e`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18000c86c`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18000c893`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18000c977`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18000c992`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18000c9a4`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18000c86c`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18000c893`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18000c977`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18000c992`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18000c9a4`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x18000c951`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x18000c951`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18000c986`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18000c986`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18000c844`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18000c844`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c8eb`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c8eb`
- `iisutil!WriteRefTraceLog` at `0x18000c8db`
- `iisutil!WriteRefTraceLog` at `0x18000c929`
- `iisutil!WriteRefTraceLog` at `0x18000c8db`
- `iisutil!WriteRefTraceLog` at `0x18000c929`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall FTP_SITE_MANAGER::PopulateSQMSiteData(FTP_SITE_MANAGER *this, struct SQM_SITE_DATA *a2)
{
  char *v3; // r14
  const struct CLKRHashTable_Iterator *v4; // rax
  const struct CLKRHashTable_Iterator *v5; // rax
  __int64 v6; // rbx
  CReaderWriterLock3 *v7; // rdi
  __int64 v8; // rdx
  __int64 v9; // rbx
  unsigned __int32 v10; // edi
  const struct CLKRHashTable_Iterator *v11; // rax
  char v12; // bl
  _BYTE v13[16]; // [rsp+20h] [rbp-39h] BYREF
  __int64 v14; // [rsp+30h] [rbp-29h]
  __int16 v15; // [rsp+3Ch] [rbp-1Dh]
  _BYTE v16[40]; // [rsp+48h] [rbp-11h] BYREF
  _BYTE v17[48]; // [rsp+70h] [rbp+17h] BYREF

  v3 = (char *)this + 8;
  *(_DWORD *)a2 = CLKRHashTable::Size((FTP_SITE_MANAGER *)((char *)this + 8));
  v4 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::Begin(v3, v17);
  CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v13, v4);
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v17);
  v5 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(v3, v17);
  CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v16, v5);
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v17);
  while ( 1 )
  {
    v12 = CLKRHashTable_Iterator::operator!=(v13, v16);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v16);
    if ( !v12 )
      break;
    v6 = *(_QWORD *)(v14 + 8LL * v15 + 24);
    v7 = (CReaderWriterLock3 *)(v6 + 208);
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v6 + 208));
    v8 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v6 + 192));
    if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
      WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v8);
    v9 = *(_QWORD *)(v6 + 192);
    CReaderWriterLock3::ReadUnlock(v7);
    if ( *(_DWORD *)(v9 + 272) || *(_DWORD *)(v9 + 296) || *(_DWORD *)(v9 + 320) )
      ++*((_DWORD *)a2 + 1);
    v10 = _InterlockedDecrement((volatile signed __int32 *)v9);
    if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
      WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v10);
    if ( !v10 )
    {
      FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v9);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v9);
    }
    CLKRHashTable_Iterator::Increment((CLKRHashTable_Iterator *)v13);
    v11 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(v3, v17);
    CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v16, v11);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v17);
  }
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v13);
}

```

## disassembly

```asm
0x18000c820  mov     [rsp-8+arg_8], rbx
0x18000c825  mov     [rsp-8+arg_10], rsi
0x18000c82a  push    rbp
0x18000c82b  push    rdi
0x18000c82c  push    r14
0x18000c82e  lea     rbp, [rsp-47h]
0x18000c833  sub     rsp, 0A0h
0x18000c83a  mov     rsi, rdx
0x18000c83d  lea     r14, [rcx+8]
0x18000c841  mov     rcx, r14
0x18000c844  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18000c84a  mov     [rsi], eax
0x18000c84c  lea     rdx, [rbp+57h+var_40]
0x18000c850  mov     rcx, r14
0x18000c853  call    cs:__imp_?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::Begin(void)
0x18000c859  nop
0x18000c85a  mov     rdx, rax
0x18000c85d  lea     rcx, [rbp+57h+var_90]
0x18000c861  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x18000c867  nop
0x18000c868  lea     rcx, [rbp+57h+var_40]
0x18000c86c  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18000c872  nop
0x18000c873  lea     rdx, [rbp+57h+var_40]
0x18000c877  mov     rcx, r14
0x18000c87a  call    cs:__imp_?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::End(void)
0x18000c880  nop
0x18000c881  mov     rdx, rax
0x18000c884  lea     rcx, [rbp+57h+var_68]
0x18000c888  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x18000c88e  nop
0x18000c88f  lea     rcx, [rbp+57h+var_40]
0x18000c893  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18000c899  jmp     loc_18000C97E
0x18000c89e  movsx   rcx, [rbp+57h+var_74]
0x18000c8a3  mov     rax, [rbp+57h+var_80]
0x18000c8a7  mov     rbx, [rax+rcx*8+18h]
0x18000c8ac  lea     rdi, [rbx+0D0h]
0x18000c8b3  mov     rcx, rdi
0x18000c8b6  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000c8bc  mov     r8, [rbx+0C0h]
0x18000c8c3  mov     edx, 1
0x18000c8c8  lock xadd [r8], edx
0x18000c8cd  inc     edx
0x18000c8cf  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18000c8d6  test    rcx, rcx
0x18000c8d9  jz      short loc_18000C8E1
0x18000c8db  call    cs:__imp_WriteRefTraceLog
0x18000c8e1  mov     rbx, [rbx+0C0h]
0x18000c8e8  mov     rcx, rdi
0x18000c8eb  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000c8f1  cmp     dword ptr [rbx+110h], 0
0x18000c8f8  ja      short loc_18000C90C
0x18000c8fa  cmp     dword ptr [rbx+128h], 0
0x18000c901  ja      short loc_18000C90C
0x18000c903  cmp     dword ptr [rbx+140h], 0
0x18000c90a  jbe     short loc_18000C90F
0x18000c90c  inc     dword ptr [rsi+4]
0x18000c90f  or      edi, 0FFFFFFFFh
0x18000c912  lock xadd [rbx], edi
0x18000c916  dec     edi
0x18000c918  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18000c91f  test    rcx, rcx
0x18000c922  jz      short loc_18000C92F
0x18000c924  mov     r8, rbx
0x18000c927  mov     edx, edi
0x18000c929  call    cs:__imp_WriteRefTraceLog
0x18000c92f  test    edi, edi
0x18000c931  jnz     short loc_18000C94D
0x18000c933  mov     rcx, rbx; this
0x18000c936  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18000c93b  nop
0x18000c93c  mov     rdx, rbx
0x18000c93f  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18000c946  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000c94c  nop
0x18000c94d  lea     rcx, [rbp+57h+var_90]
0x18000c951  call    cs:__imp_?Increment@CLKRHashTable_Iterator@@QEAA_NXZ; CLKRHashTable_Iterator::Increment(void)
0x18000c957  lea     rdx, [rbp+57h+var_40]
0x18000c95b  mov     rcx, r14
0x18000c95e  call    cs:__imp_?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::End(void)
0x18000c964  nop
0x18000c965  mov     rdx, rax
0x18000c968  lea     rcx, [rbp+57h+var_68]
0x18000c96c  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x18000c972  nop
0x18000c973  lea     rcx, [rbp+57h+var_40]
0x18000c977  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18000c97d  nop
0x18000c97e  lea     rdx, [rbp+57h+var_68]
0x18000c982  lea     rcx, [rbp+57h+var_90]
0x18000c986  call    cs:__imp_??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z; CLKRHashTable_Iterator::operator!=(CLKRHashTable_Iterator const &)
0x18000c98c  mov     bl, al
0x18000c98e  lea     rcx, [rbp+57h+var_68]
0x18000c992  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18000c998  test    bl, bl
0x18000c99a  jnz     loc_18000C89E
0x18000c9a0  lea     rcx, [rbp+57h+var_90]
0x18000c9a4  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18000c9aa  lea     r11, [rsp+0B0h+var_10]
0x18000c9b2  mov     rbx, [r11+28h]
0x18000c9b6  mov     rsi, [r11+30h]
0x18000c9ba  mov     rsp, r11
0x18000c9bd  pop     r14
0x18000c9bf  pop     rdi
0x18000c9c0  pop     rbp
0x18000c9c1  retn
```
