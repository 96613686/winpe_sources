# W3_MAIN_CONTEXT::OnNewRequest(void *)

- ea: `0x180003720`
- end: `0x180003a72`
- name: `?OnNewRequest@W3_MAIN_CONTEXT@@SA?AW4NREQ_STATUS@@PEAX@Z`
- size: `850`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003720`
- `0x180003a78`
- `0x180004f3c`
- `0x180015e40`
- `0x18001ab30`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800038a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800038a1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003a2c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003a2c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003754`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800039ce`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003754`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800039ce`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800039a8`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800039a8`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003a61`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003a61`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000383d`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000383d`
- `iisutil!WriteRefTraceLog` at `0x180003900`
- `iisutil!WriteRefTraceLog` at `0x180003943`
- `iisutil!WriteRefTraceLog` at `0x180003900`
- `iisutil!WriteRefTraceLog` at `0x180003943`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800037d5`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800037d5`

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
0x180003720  mov     [rsp+arg_10], rbx
0x180003725  mov     [rsp+arg_18], rbp
0x18000372a  push    rsi
0x18000372b  push    rdi
0x18000372c  push    r15
0x18000372e  sub     rsp, 30h
0x180003732  mov     rdi, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180003739  xor     r15d, r15d
0x18000373c  mov     rsi, rcx
0x18000373f  cmp     [rdi+630h], r15d
0x180003746  jz      short loc_180003781
0x180003748  lea     rcx, [rdi+230h]
0x18000374f  mov     [rsp+48h+arg_0], r14
0x180003754  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000375b  nop     dword ptr [rax+rax+00h]
0x180003760  mov     r14, rax
0x180003763  mov     qword ptr [rsp+48h+FileTime1.dwLowDateTime], r15
0x180003768  cmp     [rdi+630h], r15d
0x18000376f  jnz     loc_1800039A1
0x180003775  mov     rdi, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18000377c  mov     r14, [rsp+48h+arg_0]
0x180003781  mov     rcx, [rdi+5D0h]
0x180003788  test    rcx, rcx
0x18000378b  jz      short loc_180003799
0x18000378d  mov     rax, [rcx]
0x180003790  mov     rax, [rax+20h]
0x180003794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003799  mov     rcx, rsi; void *
0x18000379c  call    ?AllocateMainContext@W3_MAIN_CONTEXT@@SAPEAV1@PEAX@Z; W3_MAIN_CONTEXT::AllocateMainContext(void *)
0x1800037a1  mov     rdi, rax
0x1800037a4  test    rax, rax
0x1800037a7  jz      short loc_180003807
0x1800037a9  mov     rcx, [rax+30h]
0x1800037ad  mov     rbp, [rcx+28h]
0x1800037b1  mov     rcx, [rbp+348h]
0x1800037b8  test    rcx, rcx
0x1800037bb  jz      loc_180003850
0x1800037c1  mov     rsi, [rcx+20h]
0x1800037c5  test    rsi, rsi
0x1800037c8  jz      loc_180003850
0x1800037ce  mov     rcx, cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CERTIFICATE_CONTEXT::sm_pachCertContexts
0x1800037d5  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x1800037dc  nop     dword ptr [rax+rax+00h]
0x1800037e1  mov     rbx, rax
0x1800037e4  test    rax, rax
0x1800037e7  jnz     short loc_18000381D
0x1800037e9  mov     [rdi+2508h], r15
0x1800037f0  mov     rax, [rdi]
0x1800037f3  mov     edx, 1
0x1800037f8  mov     rcx, rdi
0x1800037fb  mov     rax, [rax+188h]
0x180003802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003807  xor     eax, eax
0x180003809  mov     rbx, [rsp+48h+arg_10]
0x18000380e  mov     rbp, [rsp+48h+arg_18]
0x180003813  add     rsp, 30h
0x180003817  pop     r15
0x180003819  pop     rdi
0x18000381a  pop     rsi
0x18000381b  retn
0x18000381d  lea     rax, ??_7CERTIFICATE_CONTEXT@@6B@; const CERTIFICATE_CONTEXT::`vftable'
0x180003824  mov     [rbx+8], rsi
0x180003828  lea     rdx, [rbx+48h]
0x18000382c  mov     [rbx], rax
0x18000382f  lea     rcx, [rbx+18h]
0x180003833  mov     [rbx+10h], r15d
0x180003837  mov     r8d, 0D0h
0x18000383d  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180003844  nop     dword ptr [rax+rax+00h]
0x180003849  mov     [rdi+2508h], rbx
0x180003850  mov     eax, [rbp+328h]
0x180003856  mov     ecx, 90h; Size
0x18000385b  mov     [rdi+2514h], eax
0x180003861  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003866  mov     rbx, rax
0x180003869  test    rax, rax
0x18000386c  jz      short loc_1800037F0
0x18000386e  lea     rax, ??_7NOTIFICATION_CONTEXT@@6B@; const NOTIFICATION_CONTEXT::`vftable'
0x180003875  mov     [rbx+8], r15d
0x180003879  mov     [rbx], rax
0x18000387c  mov     [rbx+0Ch], r15w
0x180003881  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x180003888  mov     [rbx+18h], rdi
0x18000388c  mov     dword ptr [rbx+20h], 5843544Eh
0x180003893  mov     dword ptr [rbx+24h], 1
0x18000389a  mov     dword ptr [rbx+28h], 1
0x1800038a1  call    cs:__imp_GetTickCount
0x1800038a8  nop     dword ptr [rax+rax+00h]
0x1800038ad  mov     rdx, [rbx+18h]
0x1800038b1  mov     [rbx+2Ch], eax
0x1800038b4  mov     [rbx+30h], r15
0x1800038b8  mov     [rbx+38h], r15
0x1800038bc  mov     [rbx+40h], r15
0x1800038c0  mov     [rbx+48h], r15
0x1800038c4  mov     [rbx+50h], r15
0x1800038c8  mov     [rbx+58h], r15
0x1800038cc  mov     [rbx+60h], r15
0x1800038d0  mov     [rbx+68h], r15
0x1800038d4  mov     [rbx+70h], r15
0x1800038d8  mov     [rbx+78h], r15d
0x1800038dc  mov     dword ptr [rbx+7Ch], 0FFFFFFFFh
0x1800038e3  mov     [rbx+80h], r15
0x1800038ea  lock inc dword ptr [rdx+4Ch]
0x1800038ee  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x1800038f5  test    rcx, rcx
0x1800038f8  jz      short loc_18000390C
0x1800038fa  mov     r8, rdx
0x1800038fd  mov     edx, [rdx+4Ch]
0x180003900  call    cs:__imp_WriteRefTraceLog
0x180003907  nop     dword ptr [rax+rax+00h]
0x18000390c  mov     [rbx+88h], rdi
0x180003913  lea     rax, ??_7NOTIFICATION_MAIN@@6B@; const NOTIFICATION_MAIN::`vftable'
0x18000391a  mov     [rbx], rax
0x18000391d  mov     rsi, [rdi+50h]
0x180003921  mov     [rdi+7D0h], rbx
0x180003928  test    rsi, rsi
0x18000392b  jz      short loc_180003953
0x18000392d  lock inc dword ptr [rsi+24h]
0x180003931  mov     rcx, cs:?sm_pTraceLog@NOTIFICATION_CONTEXT@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * NOTIFICATION_CONTEXT::sm_pTraceLog
0x180003938  test    rcx, rcx
0x18000393b  jz      short loc_18000394F
0x18000393d  mov     edx, [rsi+24h]
0x180003940  mov     r8, rsi
0x180003943  call    cs:__imp_WriteRefTraceLog
0x18000394a  nop     dword ptr [rax+rax+00h]
0x18000394f  lock inc dword ptr [rsi+34h]
0x180003953  mov     [rbx+38h], rsi
0x180003957  mov     rcx, rbx
0x18000395a  mov     [rdi+50h], rbx
0x18000395e  mov     rax, [rbx]
0x180003961  mov     rax, [rax+18h]
0x180003965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000396a  mov     rax, [rbx]
0x18000396d  xor     r9d, r9d
0x180003970  xor     r8d, r8d
0x180003973  mov     [rsp+48h+var_28], r15d
0x180003978  xor     edx, edx
0x18000397a  mov     rcx, rbx
0x18000397d  mov     rax, [rax+8]
0x180003981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003986  test    eax, eax
0x180003988  jz      short loc_180003994
0x18000398a  mov     eax, 1
0x18000398f  jmp     loc_180003809
0x180003994  mov     rcx, rbx
0x180003997  call    ?FinishNotificationLoop@W3_CONTEXT_BASE@@SA?AW4ASYNC_STATUS@@PEAVNOTIFICATION_CONTEXT@@@Z; W3_CONTEXT_BASE::FinishNotificationLoop(NOTIFICATION_CONTEXT *)
0x18000399c  jmp     loc_1800037F0
0x1800039a1  lea     rcx, [rdi+634h]
0x1800039a8  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800039af  nop     dword ptr [rax+rax+00h]
0x1800039b4  cmp     [rdi+630h], r15d
0x1800039bb  jz      loc_180003A5A
0x1800039c1  mov     ebx, [rdi+49Ch]
0x1800039c7  lea     rcx, [rdi+420h]
0x1800039ce  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800039d5  nop     dword ptr [rax+rax+00h]
0x1800039da  lea     rbx, [rax+rbx*4]
0x1800039de  mov     eax, [rbx]
0x1800039e0  cmp     eax, 0FFFFFFFFh
0x1800039e3  jz      short loc_1800039FC
0x1800039e5  mov     ecx, eax
0x1800039e7  mov     rcx, [r14+rcx*8]; this
0x1800039eb  call    ?Resume@VIRTUAL_MODULE@@QEAAXXZ; VIRTUAL_MODULE::Resume(void)
0x1800039f0  mov     eax, [rbx+4]
0x1800039f3  lea     rbx, [rbx+4]
0x1800039f7  cmp     eax, 0FFFFFFFFh
0x1800039fa  jnz     short loc_1800039E5
0x1800039fc  mov     rcx, [rdi+5D8h]
0x180003a03  test    rcx, rcx
0x180003a06  jz      short loc_180003A53
0x180003a08  mov     rax, [rcx]
0x180003a0b  lea     rdx, [rsp+48h+FileTime1]
0x180003a10  mov     rax, [rax+0B0h]
0x180003a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a1c  test    eax, eax
0x180003a1e  js      short loc_180003A53
0x180003a20  lea     rdx, [rdi+64Ch]; lpFileTime2
0x180003a27  lea     rcx, [rsp+48h+FileTime1]; lpFileTime1
0x180003a2c  call    cs:__imp_CompareFileTime
0x180003a33  nop     dword ptr [rax+rax+00h]
0x180003a38  cmp     eax, 1
0x180003a3b  jnz     short loc_180003A53
0x180003a3d  mov     rax, [rdi]
0x180003a40  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180003a47  mov     rcx, rdi
0x180003a4a  mov     rax, [rax+70h]
0x180003a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a53  mov     [rdi+630h], r15d
0x180003a5a  lea     rcx, [rdi+634h]
0x180003a61  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180003a68  nop     dword ptr [rax+rax+00h]
0x180003a6d  jmp     loc_180003775
```
