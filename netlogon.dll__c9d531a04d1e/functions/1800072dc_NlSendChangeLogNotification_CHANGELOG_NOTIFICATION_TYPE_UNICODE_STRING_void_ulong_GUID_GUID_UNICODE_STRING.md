# NlSendChangeLogNotification(CHANGELOG_NOTIFICATION_TYPE,_UNICODE_STRING *,void *,ulong,_GUID *,_GUID *,_UNICODE_STRING *)

- ea: `0x1800072dc`
- end: `0x180007611`
- name: `?NlSendChangeLogNotification@@YAJW4CHANGELOG_NOTIFICATION_TYPE@@PEAU_UNICODE_STRING@@PEAXKPEAU_GUID@@31@Z`
- size: `821`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006ed0`
- `0x180016000`
- `0x1800164f0`
- `0x180016590`
- `0x180016630`
- `0x180016770`
- `0x180016810`
- `0x1800168a0`

## callees

- `0x180003200`
- `0x180007278`
- `0x1800072dc`
- `0x18000ed34`
- `0x18001606c`
- `0x1800160a0`
- `0x18003f294`
- `0x18003f3bc`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800075da`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800075da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075e4`
- `ntdll!RtlLeaveCriticalSection` at `0x180007588`
- `ntdll!RtlLeaveCriticalSection` at `0x1800075cd`
- `ntdll!RtlLeaveCriticalSection` at `0x180007588`
- `ntdll!RtlLeaveCriticalSection` at `0x1800075cd`
- `ntdll!RtlEnterCriticalSection` at `0x1800074b1`
- `ntdll!RtlEnterCriticalSection` at `0x180007595`
- `ntdll!RtlEnterCriticalSection` at `0x1800074b1`
- `ntdll!RtlEnterCriticalSection` at `0x180007595`
- `ntdll!RtlInitUnicodeString` at `0x180007417`
- `ntdll!RtlInitUnicodeString` at `0x180007430`
- `ntdll!RtlInitUnicodeString` at `0x180007479`
- `ntdll!RtlInitUnicodeString` at `0x180007417`
- `ntdll!RtlInitUnicodeString` at `0x180007430`
- `ntdll!RtlInitUnicodeString` at `0x180007479`
- `ntdll!RtlLengthSid` at `0x180007327`
- `ntdll!RtlLengthSid` at `0x180007327`
- `ntdll!RtlValidSid` at `0x180007310`
- `ntdll!RtlValidSid` at `0x180007310`

## string_xrefs

- `0x18000751a`: ` Sid:`

## pseudocode

```c
__int64 __fastcall NlSendChangeLogNotification(
        int a1,
        unsigned __int16 *a2,
        void *a3,
        unsigned int a4,
        UUID *Uuid,
        UUID *a6,
        const void **a7)
{
  size_t v11; // rbx
  unsigned int v13; // r12d
  int v14; // eax
  void *v15; // rax
  __int64 v16; // rdi
  unsigned __int64 v17; // r14
  const WCHAR *v18; // r14
  size_t v19; // rbx
  const WCHAR *v20; // rdx
  __int64 *v21; // rax
  DWORD LastError; // eax
  size_t Size[11]; // [rsp+20h] [rbp-58h] BYREF

  if ( NlGlobalChangeLogNetlogonState )
  {
    v11 = 0;
    if ( a3 )
    {
      if ( !RtlValidSid(a3) )
        return 3221225485LL;
      v11 = RtlLengthSid(a3);
    }
    v13 = 0;
    if ( a2 )
      v13 = *a2 + 2;
    if ( a7 )
      v14 = *(unsigned __int16 *)a7 + 106;
    else
      v14 = 104;
    LODWORD(Size[0]) = v11 + v14 + v13;
    NetpULongRoundUp(Size[0], 8u, (unsigned int *)Size);
    v15 = (void *)NetpMemoryAllocate(LODWORD(Size[0]));
    v16 = (__int64)v15;
    if ( !v15 )
      return 3221225495LL;
    memset_0(v15, 0, LODWORD(Size[0]));
    *(_DWORD *)(v16 + 16) = a1;
    v17 = v16 + 104;
    Size[0] = v16 + 104;
    *(_DWORD *)(v16 + 48) = a4;
    if ( a3 )
    {
      memcpy_0((void *)(v16 + 104), a3, v11);
      *(_QWORD *)(v16 + 40) = v17;
      v17 += v11;
      Size[0] = v17;
    }
    else
    {
      *(_QWORD *)(v16 + 40) = 0;
    }
    if ( a2 )
    {
      NetpULongPtrRoundUp(v17, 2, Size);
      v18 = (const WCHAR *)Size[0];
      memcpy_0((void *)Size[0], *((const void **)a2 + 1), *a2);
      v18[(unsigned __int64)*a2 >> 1] = 0;
      RtlInitUnicodeString((PUNICODE_STRING)(v16 + 24), v18);
      v17 = (unsigned __int64)v18 + v13;
      Size[0] = v17;
    }
    else
    {
      RtlInitUnicodeString((PUNICODE_STRING)(v16 + 24), 0);
    }
    if ( a7 )
    {
      NetpULongPtrRoundUp(v17, 2, Size);
      v19 = Size[0];
      memcpy_0((void *)Size[0], a7[1], *(unsigned __int16 *)a7);
      v20 = (const WCHAR *)v19;
      *(_WORD *)(v19 + 2 * ((unsigned __int64)*(unsigned __int16 *)a7 >> 1)) = 0;
    }
    else
    {
      v20 = 0;
    }
    RtlInitUnicodeString((PUNICODE_STRING)(v16 + 88), v20);
    if ( Uuid )
      *(UUID *)(v16 + 52) = *Uuid;
    if ( a6 )
      *(UUID *)(v16 + 68) = *a6;
    RtlEnterCriticalSection(&NlGlobalLogFileCritSect);
    NlPrintRoutine(0x2000u, L"NlSendChangeLogNotification: sent %ld for", *(unsigned int *)(v16 + 16));
    if ( a2 )
      NlPrintRoutine(0x2000u, L" %wZ", a2);
    if ( a7 )
      NlPrintRoutine(0x2000u, L" Dom:%wZ", a7);
    if ( a4 )
      NlPrintRoutine(0x2000u, L" Rid:0x%lx", a4);
    if ( a3 )
    {
      NlPrintRoutine(0x2000u, L" Sid:");
      NlpDumpSid(0x2000u, a3);
    }
    if ( Uuid )
    {
      NlPrintRoutine(0x2000u, L" Obj Guid:");
      NlpDumpGuid(0x2000u, Uuid);
    }
    if ( a6 )
    {
      NlPrintRoutine(0x2000u, L" Dom Guid:");
      NlpDumpGuid(0x2000u, a6);
    }
    NlPrintRoutine(0x2000u, L"\n");
    RtlLeaveCriticalSection(&NlGlobalLogFileCritSect);
    RtlEnterCriticalSection(&NlGlobalChangeLogCritSect);
    v21 = (__int64 *)qword_1800F0A38;
    if ( *(struct _LIST_ENTRY **)qword_1800F0A38 != &NlGlobalChangeLogNotifications )
      __fastfail(3u);
    *(_QWORD *)v16 = &NlGlobalChangeLogNotifications;
    *(_QWORD *)(v16 + 8) = v21;
    *v21 = v16;
    qword_1800F0A38 = v16;
    RtlLeaveCriticalSection(&NlGlobalChangeLogCritSect);
    if ( !SetEvent(NlGlobalChangeLogEvent) )
    {
      LastError = GetLastError();
      NlPrintRoutine(0x100u, L"Cannot set ChangeLog event: %lu\n", LastError);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800072dc  push    rbx
0x1800072de  push    rbp
0x1800072df  push    rsi
0x1800072e0  push    rdi
0x1800072e1  push    r12
0x1800072e3  push    r13
0x1800072e5  push    r14
0x1800072e7  push    r15
0x1800072e9  sub     rsp, 38h
0x1800072ed  cmp     cs:?NlGlobalChangeLogNetlogonState@@3W4_CHANGELOG_NETLOGON_STATE@@A, 0; _CHANGELOG_NETLOGON_STATE NlGlobalChangeLogNetlogonState
0x1800072f4  mov     r13d, r9d
0x1800072f7  mov     rbp, r8
0x1800072fa  mov     r15, rdx
0x1800072fd  mov     r14d, ecx
0x180007300  jz      loc_1800075FE
0x180007306  xor     ebx, ebx
0x180007308  test    r8, r8
0x18000730b  jz      short loc_18000732F
0x18000730d  mov     rcx, r8; Sid
0x180007310  call    cs:__imp_RtlValidSid
0x180007316  test    al, al
0x180007318  jnz     short loc_180007324
0x18000731a  mov     eax, 0C000000Dh
0x18000731f  jmp     loc_180007600
0x180007324  mov     rcx, rbp; Sid
0x180007327  call    cs:__imp_RtlLengthSid
0x18000732d  mov     ebx, eax
0x18000732f  xor     r12d, r12d
0x180007332  test    r15, r15
0x180007335  jz      short loc_18000733F
0x180007337  movzx   r12d, word ptr [r15]
0x18000733b  add     r12d, 2
0x18000733f  mov     rsi, [rsp+78h+arg_30]
0x180007347  test    rsi, rsi
0x18000734a  jz      short loc_180007354
0x18000734c  movzx   eax, word ptr [rsi]
0x18000734f  add     eax, 6Ah ; 'j'
0x180007352  jmp     short loc_180007359
0x180007354  mov     eax, 68h ; 'h'
0x180007359  lea     ecx, [rax+r12]
0x18000735d  mov     edx, 8; unsigned int
0x180007362  add     ecx, ebx; unsigned int
0x180007364  lea     r8, [rsp+78h+Size]; unsigned int *
0x180007369  mov     dword ptr [rsp+78h+Size], ecx
0x18000736d  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x180007372  mov     ecx, dword ptr [rsp+78h+Size]
0x180007376  call    NetpMemoryAllocate
0x18000737b  mov     rdi, rax
0x18000737e  test    rax, rax
0x180007381  jnz     short loc_18000738D
0x180007383  mov     eax, 0C0000017h
0x180007388  jmp     loc_180007600
0x18000738d  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x180007392  xor     edx, edx; Val
0x180007394  mov     rcx, rdi; void *
0x180007397  call    memset_0
0x18000739c  mov     [rdi+10h], r14d
0x1800073a0  lea     r14, [rdi+68h]
0x1800073a4  mov     [rsp+78h+Size], r14
0x1800073a9  mov     [rdi+30h], r13d
0x1800073ad  test    rbp, rbp
0x1800073b0  jz      short loc_1800073CE
0x1800073b2  mov     r8, rbx; Size
0x1800073b5  mov     rdx, rbp; Src
0x1800073b8  mov     rcx, r14; void *
0x1800073bb  call    memcpy_0
0x1800073c0  mov     [rdi+28h], r14
0x1800073c4  add     r14, rbx
0x1800073c7  mov     [rsp+78h+Size], r14
0x1800073cc  jmp     short loc_1800073D6
0x1800073ce  mov     qword ptr [rdi+28h], 0
0x1800073d6  test    r15, r15
0x1800073d9  jz      short loc_18000742A
0x1800073db  lea     r8, [rsp+78h+Size]; unsigned __int64 *
0x1800073e0  mov     edx, 2; unsigned __int64
0x1800073e5  mov     rcx, r14; unsigned __int64
0x1800073e8  call    ?NetpULongPtrRoundUp@@YAJ_K0PEA_K@Z; NetpULongPtrRoundUp(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800073ed  mov     r14, [rsp+78h+Size]
0x1800073f2  movzx   r8d, word ptr [r15]; Size
0x1800073f6  mov     rcx, r14; void *
0x1800073f9  mov     rdx, [r15+8]; Src
0x1800073fd  call    memcpy_0
0x180007402  movzx   ecx, word ptr [r15]
0x180007406  xor     eax, eax
0x180007408  shr     rcx, 1
0x18000740b  mov     rdx, r14; SourceString
0x18000740e  mov     [r14+rcx*2], ax
0x180007413  lea     rcx, [rdi+18h]; DestinationString
0x180007417  call    cs:__imp_RtlInitUnicodeString
0x18000741d  mov     eax, r12d
0x180007420  add     r14, rax
0x180007423  mov     [rsp+78h+Size], r14
0x180007428  jmp     short loc_180007436
0x18000742a  lea     rcx, [rdi+18h]; DestinationString
0x18000742e  xor     edx, edx; SourceString
0x180007430  call    cs:__imp_RtlInitUnicodeString
0x180007436  test    rsi, rsi
0x180007439  jz      short loc_180007473
0x18000743b  lea     r8, [rsp+78h+Size]; unsigned __int64 *
0x180007440  mov     edx, 2; unsigned __int64
0x180007445  mov     rcx, r14; unsigned __int64
0x180007448  call    ?NetpULongPtrRoundUp@@YAJ_K0PEA_K@Z; NetpULongPtrRoundUp(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000744d  mov     rbx, [rsp+78h+Size]
0x180007452  movzx   r8d, word ptr [rsi]; Size
0x180007456  mov     rcx, rbx; void *
0x180007459  mov     rdx, [rsi+8]; Src
0x18000745d  call    memcpy_0
0x180007462  movzx   ecx, word ptr [rsi]
0x180007465  mov     rdx, rbx
0x180007468  shr     rcx, 1
0x18000746b  xor     eax, eax
0x18000746d  mov     [rbx+rcx*2], ax
0x180007471  jmp     short loc_180007475
0x180007473  xor     edx, edx; SourceString
0x180007475  lea     rcx, [rdi+58h]; DestinationString
0x180007479  call    cs:__imp_RtlInitUnicodeString
0x18000747f  mov     rbx, [rsp+78h+Uuid]
0x180007487  test    rbx, rbx
0x18000748a  jz      short loc_180007494
0x18000748c  movups  xmm0, xmmword ptr [rbx]
0x18000748f  movdqu  xmmword ptr [rdi+34h], xmm0
0x180007494  mov     r14, [rsp+78h+arg_28]
0x18000749c  test    r14, r14
0x18000749f  jz      short loc_1800074AA
0x1800074a1  movups  xmm0, xmmword ptr [r14]
0x1800074a5  movdqu  xmmword ptr [rdi+44h], xmm0
0x1800074aa  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800074b1  call    cs:__imp_RtlEnterCriticalSection
0x1800074b7  mov     r8d, [rdi+10h]
0x1800074bb  lea     rdx, aNlsendchangelo; "NlSendChangeLogNotification: sent %ld f"...
0x1800074c2  mov     r12d, 2000h
0x1800074c8  mov     ecx, r12d; unsigned int
0x1800074cb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800074d0  test    r15, r15
0x1800074d3  jz      short loc_1800074E7
0x1800074d5  mov     r8, r15
0x1800074d8  lea     rdx, aWz_0; " %wZ"
0x1800074df  mov     ecx, r12d; unsigned int
0x1800074e2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800074e7  test    rsi, rsi
0x1800074ea  jz      short loc_1800074FE
0x1800074ec  mov     r8, rsi
0x1800074ef  lea     rdx, aDomWz; " Dom:%wZ"
0x1800074f6  mov     ecx, r12d; unsigned int
0x1800074f9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800074fe  test    r13d, r13d
0x180007501  jz      short loc_180007515
0x180007503  mov     r8d, r13d
0x180007506  lea     rdx, aRid0xLx; " Rid:0x%lx"
0x18000750d  mov     ecx, r12d; unsigned int
0x180007510  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180007515  test    rbp, rbp
0x180007518  jz      short loc_180007534
0x18000751a  lea     rdx, aSid; " Sid:"
0x180007521  mov     ecx, r12d; unsigned int
0x180007524  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180007529  mov     rdx, rbp; void *
0x18000752c  mov     ecx, r12d; unsigned int
0x18000752f  call    ?NlpDumpSid@@YAXKPEAX@Z; NlpDumpSid(ulong,void *)
0x180007534  test    rbx, rbx
0x180007537  jz      short loc_180007553
0x180007539  lea     rdx, aObjGuid; " Obj Guid:"
0x180007540  mov     ecx, r12d; unsigned int
0x180007543  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180007548  mov     rdx, rbx; Uuid
0x18000754b  mov     ecx, r12d; unsigned int
0x18000754e  call    ?NlpDumpGuid@@YAXKPEAU_GUID@@@Z; NlpDumpGuid(ulong,_GUID *)
0x180007553  test    r14, r14
0x180007556  jz      short loc_180007572
0x180007558  lea     rdx, aDomGuid; " Dom Guid:"
0x18000755f  mov     ecx, r12d; unsigned int
0x180007562  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180007567  mov     rdx, r14; Uuid
0x18000756a  mov     ecx, r12d; unsigned int
0x18000756d  call    ?NlpDumpGuid@@YAXKPEAU_GUID@@@Z; NlpDumpGuid(ulong,_GUID *)
0x180007572  lea     rdx, asc_180096388; "\n"
0x180007579  mov     ecx, r12d; unsigned int
0x18000757c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180007581  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180007588  call    cs:__imp_RtlLeaveCriticalSection
0x18000758e  lea     rcx, ?NlGlobalChangeLogCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180007595  call    cs:__imp_RtlEnterCriticalSection
0x18000759b  mov     rax, cs:qword_1800F0A38
0x1800075a2  lea     rcx, ?NlGlobalChangeLogNotifications@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalChangeLogNotifications
0x1800075a9  cmp     [rax], rcx
0x1800075ac  jz      short loc_1800075B5
0x1800075ae  mov     ecx, 3
0x1800075b3  int     29h; Win8: RtlFailFast(ecx)
0x1800075b5  mov     [rdi], rcx
0x1800075b8  lea     rcx, ?NlGlobalChangeLogCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800075bf  mov     [rdi+8], rax
0x1800075c3  mov     [rax], rdi
0x1800075c6  mov     cs:qword_1800F0A38, rdi
0x1800075cd  call    cs:__imp_RtlLeaveCriticalSection
0x1800075d3  mov     rcx, cs:?NlGlobalChangeLogEvent@@3PEAXEA; hEvent
0x1800075da  call    cs:__imp_SetEvent
0x1800075e0  test    eax, eax
0x1800075e2  jnz     short loc_1800075FE
0x1800075e4  call    cs:__imp_GetLastError
0x1800075ea  lea     rdx, aCannotSetChang; "Cannot set ChangeLog event: %lu\n"
0x1800075f1  mov     ecx, 100h; unsigned int
0x1800075f6  mov     r8d, eax
0x1800075f9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800075fe  xor     eax, eax
0x180007600  add     rsp, 38h
0x180007604  pop     r15
0x180007606  pop     r14
0x180007608  pop     r13
0x18000760a  pop     r12
0x18000760c  pop     rdi
0x18000760d  pop     rsi
0x18000760e  pop     rbp
0x18000760f  pop     rbx
0x180007610  retn
```
