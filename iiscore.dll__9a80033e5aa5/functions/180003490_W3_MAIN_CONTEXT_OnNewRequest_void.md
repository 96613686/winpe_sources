# W3_MAIN_CONTEXT::OnNewRequest(void *)

- ea: `0x180003490`
- end: `0x18000379d`
- name: `?OnNewRequest@W3_MAIN_CONTEXT@@SA?AW4NREQ_STATUS@@PEAX@Z`
- size: `781`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003490`
- `0x1800037a4`
- `0x180004b2c`
- `0x180014d00`
- `0x180019558`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800035f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800035f6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003763`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003763`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800034c4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000370b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800034c4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000370b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800036eb`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800036eb`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003792`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003792`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180003598`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180003598`
- `iisutil!WriteRefTraceLog` at `0x18000364f`
- `iisutil!WriteRefTraceLog` at `0x18000368c`
- `iisutil!WriteRefTraceLog` at `0x18000364f`
- `iisutil!WriteRefTraceLog` at `0x18000368c`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180003537`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180003537`

## pseudocode

```c
__int64 __fastcall W3_MAIN_CONTEXT::OnNewRequest(void *a1)
{
  W3_SERVER *v1; // rdi
  VIRTUAL_MODULE **Ptr; // r14
  __int64 v4; // rcx
  struct W3_MAIN_CONTEXT *MainContext; // rax
  struct W3_MAIN_CONTEXT *v6; // rdi
  __int64 v7; // rbp
  __int64 v8; // rcx
  __int64 v9; // rsi
  char *v10; // rbx
  _DWORD *v12; // rbx
  DWORD TickCount; // eax
  __int64 v14; // rdx
  __int64 v15; // rsi
  __int64 v16; // rbx
  int *v17; // rbx
  int i; // eax
  __int64 v19; // rcx
  FILETIME FileTime1; // [rsp+58h] [rbp+10h] BYREF

  v1 = g_pW3Server;
  if ( *((_DWORD *)g_pW3Server + 396) )
  {
    Ptr = (VIRTUAL_MODULE **)BUFFER::QueryPtr((W3_SERVER *)((char *)g_pW3Server + 560));
    FileTime1 = 0;
    if ( *((_DWORD *)v1 + 396) )
    {
      CReaderWriterLock3::WriteLock((W3_SERVER *)((char *)v1 + 1588));
      if ( *((_DWORD *)v1 + 396) )
      {
        v16 = *((unsigned int *)v1 + 295);
        v17 = (int *)((char *)BUFFER::QueryPtr((W3_SERVER *)((char *)v1 + 1056)) + 4 * v16);
        for ( i = *v17; i != -1; ++v17 )
        {
          VIRTUAL_MODULE::Resume(Ptr[i]);
          i = v17[1];
        }
        v19 = *((_QWORD *)v1 + 187);
        if ( v19
          && (*(int (__fastcall **)(__int64, FILETIME *))(*(_QWORD *)v19 + 176LL))(v19, &FileTime1) >= 0
          && CompareFileTime(&FileTime1, (const FILETIME *)((char *)v1 + 1612)) == 1 )
        {
          (*(void (__fastcall **)(W3_SERVER *, const wchar_t *))(*(_QWORD *)v1 + 112LL))(v1, L"MACHINE/WEBROOT/APPHOST");
        }
        *((_DWORD *)v1 + 396) = 0;
      }
      CReaderWriterLock3::WriteUnlock((W3_SERVER *)((char *)v1 + 1588));
    }
    v1 = g_pW3Server;
  }
  v4 = *((_QWORD *)v1 + 186);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 32LL))(v4);
  MainContext = W3_MAIN_CONTEXT::AllocateMainContext(a1);
  v6 = MainContext;
  if ( !MainContext )
    return 0;
  v7 = *(_QWORD *)(*((_QWORD *)MainContext + 6) + 40LL);
  v8 = *(_QWORD *)(v7 + 840);
  if ( v8 )
  {
    v9 = *(_QWORD *)(v8 + 32);
    if ( v9 )
    {
      v10 = (char *)ALLOC_CACHE_HANDLER::Alloc(CERTIFICATE_CONTEXT::sm_pachCertContexts);
      if ( !v10 )
      {
        *((_QWORD *)v6 + 1185) = 0;
LABEL_11:
        (*(void (__fastcall **)(struct W3_MAIN_CONTEXT *, __int64))(*(_QWORD *)v6 + 392LL))(v6, 1);
        return 0;
      }
      *((_QWORD *)v10 + 1) = v9;
      *(_QWORD *)v10 = &CERTIFICATE_CONTEXT::`vftable';
      *((_DWORD *)v10 + 4) = 0;
      BUFFER::BUFFER((BUFFER *)(v10 + 24), (unsigned __int8 *)v10 + 72, 0xD0u);
      *((_QWORD *)v6 + 1185) = v10;
    }
  }
  *((_DWORD *)v6 + 2373) = *(_DWORD *)(v7 + 808);
  v12 = operator new(0x90u);
  if ( !v12 )
    goto LABEL_11;
  v12[2] = 0;
  *(_QWORD *)v12 = &NOTIFICATION_CONTEXT::`vftable';
  *((_WORD *)v12 + 6) = 0;
  v12[4] = -1;
  *((_QWORD *)v12 + 3) = v6;
  v12[8] = 1480807502;
  v12[9] = 1;
  v12[10] = 1;
  TickCount = GetTickCount();
  v14 = *((_QWORD *)v12 + 3);
  v12[11] = TickCount;
  *((_QWORD *)v12 + 6) = 0;
  *((_QWORD *)v12 + 7) = 0;
  *((_QWORD *)v12 + 8) = 0;
  *((_QWORD *)v12 + 9) = 0;
  *((_QWORD *)v12 + 10) = 0;
  *((_QWORD *)v12 + 11) = 0;
  *((_QWORD *)v12 + 12) = 0;
  *((_QWORD *)v12 + 13) = 0;
  *((_QWORD *)v12 + 14) = 0;
  v12[30] = 0;
  v12[31] = -1;
  *((_QWORD *)v12 + 16) = 0;
  _InterlockedIncrement((volatile signed __int32 *)(v14 + 76));
  if ( W3_CONTEXT_BASE::sm_pTraceLog )
    WriteRefTraceLog(W3_CONTEXT_BASE::sm_pTraceLog, *(unsigned int *)(v14 + 76), v14);
  *((_QWORD *)v12 + 17) = v6;
  *(_QWORD *)v12 = &NOTIFICATION_MAIN::`vftable';
  v15 = *((_QWORD *)v6 + 10);
  *((_QWORD *)v6 + 250) = v12;
  if ( v15 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 36));
    if ( NOTIFICATION_CONTEXT::sm_pTraceLog )
      WriteRefTraceLog(NOTIFICATION_CONTEXT::sm_pTraceLog, *(unsigned int *)(v15 + 36), v15);
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 52));
  }
  *((_QWORD *)v12 + 7) = v15;
  *((_QWORD *)v6 + 10) = v12;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v12 + 24LL))(v12);
  if ( !(*(unsigned int (__fastcall **)(_DWORD *, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v12 + 8LL))(
          v12,
          0,
          0,
          0,
          0) )
  {
    W3_CONTEXT_BASE::FinishNotificationLoop(v12);
    goto LABEL_11;
  }
  return 1;
}

```

## disassembly

```asm
0x180003490  mov     [rsp+arg_10], rbx
0x180003495  mov     [rsp+arg_18], rbp
0x18000349a  push    rsi
0x18000349b  push    rdi
0x18000349c  push    r15
0x18000349e  sub     rsp, 30h
0x1800034a2  mov     rdi, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800034a9  xor     r15d, r15d
0x1800034ac  mov     rsi, rcx
0x1800034af  cmp     [rdi+630h], r15d
0x1800034b6  jz      short loc_1800034EB
0x1800034b8  lea     rcx, [rdi+230h]
0x1800034bf  mov     [rsp+48h+arg_0], r14
0x1800034c4  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800034ca  mov     r14, rax
0x1800034cd  mov     qword ptr [rsp+48h+FileTime1.dwLowDateTime], r15
0x1800034d2  cmp     [rdi+630h], r15d
0x1800034d9  jnz     loc_1800036E4
0x1800034df  mov     rdi, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800034e6  mov     r14, [rsp+48h+arg_0]
0x1800034eb  mov     rcx, [rdi+5D0h]
0x1800034f2  test    rcx, rcx
0x1800034f5  jz      short loc_180003503
0x1800034f7  mov     rax, [rcx]
0x1800034fa  mov     rax, [rax+20h]
0x1800034fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003503  mov     rcx, rsi; void *
0x180003506  call    ?AllocateMainContext@W3_MAIN_CONTEXT@@SAPEAV1@PEAX@Z; W3_MAIN_CONTEXT::AllocateMainContext(void *)
0x18000350b  mov     rdi, rax
0x18000350e  test    rax, rax
0x180003511  jz      short loc_180003563
0x180003513  mov     rcx, [rax+30h]
0x180003517  mov     rbp, [rcx+28h]
0x18000351b  mov     rcx, [rbp+348h]
0x180003522  test    rcx, rcx
0x180003525  jz      short loc_1800035A5
0x180003527  mov     rsi, [rcx+20h]
0x18000352b  test    rsi, rsi
0x18000352e  jz      short loc_1800035A5
0x180003530  mov     rcx, cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CERTIFICATE_CONTEXT::sm_pachCertContexts
0x180003537  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000353d  mov     rbx, rax
0x180003540  test    rax, rax
0x180003543  jnz     short loc_180003578
0x180003545  mov     [rdi+2508h], r15
0x18000354c  mov     rax, [rdi]
0x18000354f  mov     edx, 1
0x180003554  mov     rcx, rdi
0x180003557  mov     rax, [rax+188h]
0x18000355e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003563  xor     eax, eax
0x180003565  mov     rbx, [rsp+48h+arg_10]
0x18000356a  mov     rbp, [rsp+48h+arg_18]
0x18000356f  add     rsp, 30h
0x180003573  pop     r15
0x180003575  pop     rdi
0x180003576  pop     rsi
0x180003577  retn
0x180003578  lea     rax, ??_7CERTIFICATE_CONTEXT@@6B@; const CERTIFICATE_CONTEXT::`vftable'
0x18000357f  mov     [rbx+8], rsi
0x180003583  lea     rdx, [rbx+48h]
0x180003587  mov     [rbx], rax
0x18000358a  lea     rcx, [rbx+18h]
0x18000358e  mov     [rbx+10h], r15d
0x180003592  mov     r8d, 0D0h
0x180003598  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18000359e  mov     [rdi+2508h], rbx
0x1800035a5  mov     eax, [rbp+328h]
0x1800035ab  mov     ecx, 90h; Size
0x1800035b0  mov     [rdi+2514h], eax
0x1800035b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800035bb  mov     rbx, rax
0x1800035be  test    rax, rax
0x1800035c1  jz      short loc_18000354C
0x1800035c3  lea     rax, ??_7NOTIFICATION_CONTEXT@@6B@; const NOTIFICATION_CONTEXT::`vftable'
0x1800035ca  mov     [rbx+8], r15d
0x1800035ce  mov     [rbx], rax
0x1800035d1  mov     [rbx+0Ch], r15w
0x1800035d6  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x1800035dd  mov     [rbx+18h], rdi
0x1800035e1  mov     dword ptr [rbx+20h], 5843544Eh
0x1800035e8  mov     dword ptr [rbx+24h], 1
0x1800035ef  mov     dword ptr [rbx+28h], 1
0x1800035f6  call    cs:__imp_GetTickCount
0x1800035fc  mov     rdx, [rbx+18h]
0x180003600  mov     [rbx+2Ch], eax
0x180003603  mov     [rbx+30h], r15
0x180003607  mov     [rbx+38h], r15
0x18000360b  mov     [rbx+40h], r15
0x18000360f  mov     [rbx+48h], r15
0x180003613  mov     [rbx+50h], r15
0x180003617  mov     [rbx+58h], r15
0x18000361b  mov     [rbx+60h], r15
0x18000361f  mov     [rbx+68h], r15
0x180003623  mov     [rbx+70h], r15
0x180003627  mov     [rbx+78h], r15d
0x18000362b  mov     dword ptr [rbx+7Ch], 0FFFFFFFFh
0x180003632  mov     [rbx+80h], r15
0x180003639  lock inc dword ptr [rdx+4Ch]
0x18000363d  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x180003644  test    rcx, rcx
0x180003647  jz      short loc_180003655
0x180003649  mov     r8, rdx
0x18000364c  mov     edx, [rdx+4Ch]
0x18000364f  call    cs:__imp_WriteRefTraceLog
0x180003655  mov     [rbx+88h], rdi
0x18000365c  lea     rax, ??_7NOTIFICATION_MAIN@@6B@; const NOTIFICATION_MAIN::`vftable'
0x180003663  mov     [rbx], rax
0x180003666  mov     rsi, [rdi+50h]
0x18000366a  mov     [rdi+7D0h], rbx
0x180003671  test    rsi, rsi
0x180003674  jz      short loc_180003696
0x180003676  lock inc dword ptr [rsi+24h]
0x18000367a  mov     rcx, cs:?sm_pTraceLog@NOTIFICATION_CONTEXT@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * NOTIFICATION_CONTEXT::sm_pTraceLog
0x180003681  test    rcx, rcx
0x180003684  jz      short loc_180003692
0x180003686  mov     edx, [rsi+24h]
0x180003689  mov     r8, rsi
0x18000368c  call    cs:__imp_WriteRefTraceLog
0x180003692  lock inc dword ptr [rsi+34h]
0x180003696  mov     [rbx+38h], rsi
0x18000369a  mov     rcx, rbx
0x18000369d  mov     [rdi+50h], rbx
0x1800036a1  mov     rax, [rbx]
0x1800036a4  mov     rax, [rax+18h]
0x1800036a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036ad  mov     rax, [rbx]
0x1800036b0  xor     r9d, r9d
0x1800036b3  xor     r8d, r8d
0x1800036b6  mov     [rsp+48h+var_28], r15d
0x1800036bb  xor     edx, edx
0x1800036bd  mov     rcx, rbx
0x1800036c0  mov     rax, [rax+8]
0x1800036c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036c9  test    eax, eax
0x1800036cb  jz      short loc_1800036D7
0x1800036cd  mov     eax, 1
0x1800036d2  jmp     loc_180003565
0x1800036d7  mov     rcx, rbx
0x1800036da  call    ?FinishNotificationLoop@W3_CONTEXT_BASE@@SA?AW4ASYNC_STATUS@@PEAVNOTIFICATION_CONTEXT@@@Z; W3_CONTEXT_BASE::FinishNotificationLoop(NOTIFICATION_CONTEXT *)
0x1800036df  jmp     loc_18000354C
0x1800036e4  lea     rcx, [rdi+634h]
0x1800036eb  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800036f1  cmp     [rdi+630h], r15d
0x1800036f8  jz      loc_18000378B
0x1800036fe  mov     ebx, [rdi+49Ch]
0x180003704  lea     rcx, [rdi+420h]
0x18000370b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180003711  lea     rbx, [rax+rbx*4]
0x180003715  mov     eax, [rbx]
0x180003717  cmp     eax, 0FFFFFFFFh
0x18000371a  jz      short loc_180003733
0x18000371c  mov     ecx, eax
0x18000371e  mov     rcx, [r14+rcx*8]; this
0x180003722  call    ?Resume@VIRTUAL_MODULE@@QEAAXXZ; VIRTUAL_MODULE::Resume(void)
0x180003727  mov     eax, [rbx+4]
0x18000372a  lea     rbx, [rbx+4]
0x18000372e  cmp     eax, 0FFFFFFFFh
0x180003731  jnz     short loc_18000371C
0x180003733  mov     rcx, [rdi+5D8h]
0x18000373a  test    rcx, rcx
0x18000373d  jz      short loc_180003784
0x18000373f  mov     rax, [rcx]
0x180003742  lea     rdx, [rsp+48h+FileTime1]
0x180003747  mov     rax, [rax+0B0h]
0x18000374e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003753  test    eax, eax
0x180003755  js      short loc_180003784
0x180003757  lea     rdx, [rdi+64Ch]; lpFileTime2
0x18000375e  lea     rcx, [rsp+48h+FileTime1]; lpFileTime1
0x180003763  call    cs:__imp_CompareFileTime
0x180003769  cmp     eax, 1
0x18000376c  jnz     short loc_180003784
0x18000376e  mov     rax, [rdi]
0x180003771  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180003778  mov     rcx, rdi
0x18000377b  mov     rax, [rax+70h]
0x18000377f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003784  mov     [rdi+630h], r15d
0x18000378b  lea     rcx, [rdi+634h]
0x180003792  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180003798  jmp     loc_1800034DF
```
