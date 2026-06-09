# NlSendChangeLogNotification(CHANGELOG_NOTIFICATION_TYPE,_UNICODE_STRING *,void *,ulong,_GUID *,_GUID *,_UNICODE_STRING *)

- ea: `0x180007588`
- end: `0x180007900`
- name: `?NlSendChangeLogNotification@@YAJW4CHANGELOG_NOTIFICATION_TYPE@@PEAU_UNICODE_STRING@@PEAXKPEAU_GUID@@31@Z`
- size: `888`
- prototype: `int __high(enum CHANGELOG_NOTIFICATION_TYPE, struct _UNICODE_STRING *, void *, unsigned int, struct _GUID *, struct _GUID *, struct _UNICODE_STRING *)`
- caller_count: `8`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180007150`
- `0x180016970`
- `0x180016f10`
- `0x180016fc0`
- `0x180017070`
- `0x1800171b0`
- `0x180017250`
- `0x1800172f0`

## callees

- `0x180003320`
- `0x180007518`
- `0x180007588`
- `0x18000f3e4`
- `0x180016a70`
- `0x180016aa4`
- `0x180041b98`
- `0x180041ccc`
- `0x180090204`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800078bc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800078bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078cc`
- `ntdll!RtlLeaveCriticalSection` at `0x180007858`
- `ntdll!RtlLeaveCriticalSection` at `0x1800078a9`
- `ntdll!RtlLeaveCriticalSection` at `0x180007858`
- `ntdll!RtlLeaveCriticalSection` at `0x1800078a9`
- `ntdll!RtlEnterCriticalSection` at `0x18000777b`
- `ntdll!RtlEnterCriticalSection` at `0x18000786b`
- `ntdll!RtlEnterCriticalSection` at `0x18000777b`
- `ntdll!RtlEnterCriticalSection` at `0x18000786b`
- `ntdll!RtlInitUnicodeString` at `0x1800076cf`
- `ntdll!RtlInitUnicodeString` at `0x1800076ee`
- `ntdll!RtlInitUnicodeString` at `0x18000773d`
- `ntdll!RtlInitUnicodeString` at `0x1800076cf`
- `ntdll!RtlInitUnicodeString` at `0x1800076ee`
- `ntdll!RtlInitUnicodeString` at `0x18000773d`
- `ntdll!RtlLengthSid` at `0x1800075d9`
- `ntdll!RtlLengthSid` at `0x1800075d9`
- `ntdll!RtlValidSid` at `0x1800075bc`
- `ntdll!RtlValidSid` at `0x1800075bc`

## string_xrefs

- `0x1800077ea`: ` Sid:`

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
      NetpULongPtrRoundUp(v17, 2u, Size);
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
      NetpULongPtrRoundUp(v17, 2u, Size);
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
    v21 = (__int64 *)qword_1800F7A38;
    if ( *(struct _LIST_ENTRY **)qword_1800F7A38 != &NlGlobalChangeLogNotifications )
      __fastfail(3u);
    *(_QWORD *)v16 = &NlGlobalChangeLogNotifications;
    *(_QWORD *)(v16 + 8) = v21;
    *v21 = v16;
    qword_1800F7A38 = v16;
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
0x180007588  push    rbx
0x18000758a  push    rbp
0x18000758b  push    rsi
0x18000758c  push    rdi
0x18000758d  push    r12
0x18000758f  push    r13
0x180007591  push    r14
0x180007593  push    r15
0x180007595  sub     rsp, 38h
0x180007599  cmp     cs:?NlGlobalChangeLogNetlogonState@@3W4_CHANGELOG_NETLOGON_STATE@@A, 0; _CHANGELOG_NETLOGON_STATE NlGlobalChangeLogNetlogonState
0x1800075a0  mov     r13d, r9d
0x1800075a3  mov     rbp, r8
0x1800075a6  mov     r15, rdx
0x1800075a9  mov     r14d, ecx
0x1800075ac  jz      loc_1800078EC
0x1800075b2  xor     ebx, ebx
0x1800075b4  test    r8, r8
0x1800075b7  jz      short loc_1800075E7
0x1800075b9  mov     rcx, r8; Sid
0x1800075bc  call    cs:__imp_RtlValidSid
0x1800075c3  nop     dword ptr [rax+rax+00h]
0x1800075c8  test    al, al
0x1800075ca  jnz     short loc_1800075D6
0x1800075cc  mov     eax, 0C000000Dh
0x1800075d1  jmp     loc_1800078EE
0x1800075d6  mov     rcx, rbp; Sid
0x1800075d9  call    cs:__imp_RtlLengthSid
0x1800075e0  nop     dword ptr [rax+rax+00h]
0x1800075e5  mov     ebx, eax
0x1800075e7  xor     r12d, r12d
0x1800075ea  test    r15, r15
0x1800075ed  jz      short loc_1800075F7
0x1800075ef  movzx   r12d, word ptr [r15]
0x1800075f3  add     r12d, 2
0x1800075f7  mov     rsi, [rsp+78h+arg_30]
0x1800075ff  test    rsi, rsi
0x180007602  jz      short loc_18000760C
0x180007604  movzx   eax, word ptr [rsi]
0x180007607  add     eax, 6Ah ; 'j'
0x18000760a  jmp     short loc_180007611
0x18000760c  mov     eax, 68h ; 'h'
0x180007611  lea     ecx, [rax+r12]
0x180007615  mov     edx, 8; unsigned int
0x18000761a  add     ecx, ebx; unsigned int
0x18000761c  lea     r8, [rsp+78h+Size]; unsigned int *
0x180007621  mov     dword ptr [rsp+78h+Size], ecx
0x180007625  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x18000762a  mov     ecx, dword ptr [rsp+78h+Size]
0x18000762e  call    NetpMemoryAllocate
0x180007633  mov     rdi, rax
0x180007636  test    rax, rax
0x180007639  jnz     short loc_180007645
0x18000763b  mov     eax, 0C0000017h
0x180007640  jmp     loc_1800078EE
0x180007645  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x18000764a  xor     edx, edx; Val
0x18000764c  mov     rcx, rdi; void *
0x18000764f  call    memset_0
0x180007654  mov     [rdi+10h], r14d
0x180007658  lea     r14, [rdi+68h]
0x18000765c  mov     [rsp+78h+Size], r14
0x180007661  mov     [rdi+30h], r13d
0x180007665  test    rbp, rbp
0x180007668  jz      short loc_180007686
0x18000766a  mov     r8, rbx; Size
0x18000766d  mov     rdx, rbp; Src
0x180007670  mov     rcx, r14; void *
0x180007673  call    memcpy_0
0x180007678  mov     [rdi+28h], r14
0x18000767c  add     r14, rbx
0x18000767f  mov     [rsp+78h+Size], r14
0x180007684  jmp     short loc_18000768E
0x180007686  mov     qword ptr [rdi+28h], 0
0x18000768e  test    r15, r15
0x180007691  jz      short loc_1800076E8
0x180007693  lea     r8, [rsp+78h+Size]; unsigned __int64 *
0x180007698  mov     edx, 2; unsigned __int64
0x18000769d  mov     rcx, r14; unsigned __int64
0x1800076a0  call    ?NetpULongPtrRoundUp@@YAJ_K0PEA_K@Z; NetpULongPtrRoundUp(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800076a5  mov     r14, [rsp+78h+Size]
0x1800076aa  movzx   r8d, word ptr [r15]; Size
0x1800076ae  mov     rcx, r14; void *
0x1800076b1  mov     rdx, [r15+8]; Src
0x1800076b5  call    memcpy_0
0x1800076ba  movzx   ecx, word ptr [r15]
0x1800076be  xor     eax, eax
0x1800076c0  shr     rcx, 1
0x1800076c3  mov     rdx, r14; SourceString
0x1800076c6  mov     [r14+rcx*2], ax
0x1800076cb  lea     rcx, [rdi+18h]; DestinationString
0x1800076cf  call    cs:__imp_RtlInitUnicodeString
0x1800076d6  nop     dword ptr [rax+rax+00h]
0x1800076db  mov     eax, r12d
0x1800076de  add     r14, rax
0x1800076e1  mov     [rsp+78h+Size], r14
0x1800076e6  jmp     short loc_1800076FA
0x1800076e8  lea     rcx, [rdi+18h]; DestinationString
0x1800076ec  xor     edx, edx; SourceString
0x1800076ee  call    cs:__imp_RtlInitUnicodeString
0x1800076f5  nop     dword ptr [rax+rax+00h]
0x1800076fa  test    rsi, rsi
0x1800076fd  jz      short loc_180007737
0x1800076ff  lea     r8, [rsp+78h+Size]; unsigned __int64 *
0x180007704  mov     edx, 2; unsigned __int64
0x180007709  mov     rcx, r14; unsigned __int64
0x18000770c  call    ?NetpULongPtrRoundUp@@YAJ_K0PEA_K@Z; NetpULongPtrRoundUp(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180007711  mov     rbx, [rsp+78h+Size]
0x180007716  movzx   r8d, word ptr [rsi]; Size
0x18000771a  mov     rcx, rbx; void *
0x18000771d  mov     rdx, [rsi+8]; Src
0x180007721  call    memcpy_0
0x180007726  movzx   ecx, word ptr [rsi]
0x180007729  mov     rdx, rbx
0x18000772c  shr     rcx, 1
0x18000772f  xor     eax, eax
0x180007731  mov     [rbx+rcx*2], ax
0x180007735  jmp     short loc_180007739
0x180007737  xor     edx, edx; SourceString
0x180007739  lea     rcx, [rdi+58h]; DestinationString
0x18000773d  call    cs:__imp_RtlInitUnicodeString
0x180007744  nop     dword ptr [rax+rax+00h]
0x180007749  mov     rbx, [rsp+78h+Uuid]
0x180007751  test    rbx, rbx
0x180007754  jz      short loc_18000775E
0x180007756  movups  xmm0, xmmword ptr [rbx]
0x180007759  movdqu  xmmword ptr [rdi+34h], xmm0
0x18000775e  mov     r14, [rsp+78h+arg_28]
0x180007766  test    r14, r14
0x180007769  jz      short loc_180007774
0x18000776b  movups  xmm0, xmmword ptr [r14]
0x18000776f  movdqu  xmmword ptr [rdi+44h], xmm0
0x180007774  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18000777b  call    cs:__imp_RtlEnterCriticalSection
0x180007782  nop     dword ptr [rax+rax+00h]
0x180007787  mov     r8d, [rdi+10h]
0x18000778b  lea     rdx, aNlsendchangelo; "NlSendChangeLogNotification: sent %ld f"...
0x180007792  mov     r12d, 2000h
0x180007798  mov     ecx, r12d; unsigned int
0x18000779b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800077a0  test    r15, r15
0x1800077a3  jz      short loc_1800077B7
0x1800077a5  mov     r8, r15
0x1800077a8  lea     rdx, aWz_0; " %wZ"
0x1800077af  mov     ecx, r12d; unsigned int
0x1800077b2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800077b7  test    rsi, rsi
0x1800077ba  jz      short loc_1800077CE
0x1800077bc  mov     r8, rsi
0x1800077bf  lea     rdx, aDomWz; " Dom:%wZ"
0x1800077c6  mov     ecx, r12d; unsigned int
0x1800077c9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800077ce  test    r13d, r13d
0x1800077d1  jz      short loc_1800077E5
0x1800077d3  mov     r8d, r13d
0x1800077d6  lea     rdx, aRid0xLx; " Rid:0x%lx"
0x1800077dd  mov     ecx, r12d; unsigned int
0x1800077e0  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800077e5  test    rbp, rbp
0x1800077e8  jz      short loc_180007804
0x1800077ea  lea     rdx, aSid; " Sid:"
0x1800077f1  mov     ecx, r12d; unsigned int
0x1800077f4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800077f9  mov     rdx, rbp; void *
0x1800077fc  mov     ecx, r12d; unsigned int
0x1800077ff  call    ?NlpDumpSid@@YAXKPEAX@Z; NlpDumpSid(ulong,void *)
0x180007804  test    rbx, rbx
0x180007807  jz      short loc_180007823
0x180007809  lea     rdx, aObjGuid; " Obj Guid:"
0x180007810  mov     ecx, r12d; unsigned int
0x180007813  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180007818  mov     rdx, rbx; Uuid
0x18000781b  mov     ecx, r12d; unsigned int
0x18000781e  call    ?NlpDumpGuid@@YAXKPEAU_GUID@@@Z; NlpDumpGuid(ulong,_GUID *)
0x180007823  test    r14, r14
0x180007826  jz      short loc_180007842
0x180007828  lea     rdx, aDomGuid; " Dom Guid:"
0x18000782f  mov     ecx, r12d; unsigned int
0x180007832  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180007837  mov     rdx, r14; Uuid
0x18000783a  mov     ecx, r12d; unsigned int
0x18000783d  call    ?NlpDumpGuid@@YAXKPEAU_GUID@@@Z; NlpDumpGuid(ulong,_GUID *)
0x180007842  lea     rdx, asc_18009D398; "\n"
0x180007849  mov     ecx, r12d; unsigned int
0x18000784c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180007851  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180007858  call    cs:__imp_RtlLeaveCriticalSection
0x18000785f  nop     dword ptr [rax+rax+00h]
0x180007864  lea     rcx, ?NlGlobalChangeLogCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18000786b  call    cs:__imp_RtlEnterCriticalSection
0x180007872  nop     dword ptr [rax+rax+00h]
0x180007877  mov     rax, cs:qword_1800F7A38
0x18000787e  lea     rcx, ?NlGlobalChangeLogNotifications@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalChangeLogNotifications
0x180007885  cmp     [rax], rcx
0x180007888  jz      short loc_180007891
0x18000788a  mov     ecx, 3
0x18000788f  int     29h; Win8: RtlFailFast(ecx)
0x180007891  mov     [rdi], rcx
0x180007894  lea     rcx, ?NlGlobalChangeLogCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18000789b  mov     [rdi+8], rax
0x18000789f  mov     [rax], rdi
0x1800078a2  mov     cs:qword_1800F7A38, rdi
0x1800078a9  call    cs:__imp_RtlLeaveCriticalSection
0x1800078b0  nop     dword ptr [rax+rax+00h]
0x1800078b5  mov     rcx, cs:?NlGlobalChangeLogEvent@@3PEAXEA; hEvent
0x1800078bc  call    cs:__imp_SetEvent
0x1800078c3  nop     dword ptr [rax+rax+00h]
0x1800078c8  test    eax, eax
0x1800078ca  jnz     short loc_1800078EC
0x1800078cc  call    cs:__imp_GetLastError
0x1800078d3  nop     dword ptr [rax+rax+00h]
0x1800078d8  lea     rdx, aCannotSetChang; "Cannot set ChangeLog event: %lu\n"
0x1800078df  mov     ecx, 100h; unsigned int
0x1800078e4  mov     r8d, eax
0x1800078e7  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800078ec  xor     eax, eax
0x1800078ee  add     rsp, 38h
0x1800078f2  pop     r15
0x1800078f4  pop     r14
0x1800078f6  pop     r13
0x1800078f8  pop     r12
0x1800078fa  pop     rdi
0x1800078fb  pop     rsi
0x1800078fc  pop     rbp
0x1800078fd  pop     rbx
0x1800078fe  retn
```
