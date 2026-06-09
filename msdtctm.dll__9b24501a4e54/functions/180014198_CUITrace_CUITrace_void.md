# CUITrace::CUITrace(void)

- ea: `0x180014198`
- end: `0x18001430d`
- name: `??0CUITrace@@QEAA@XZ`
- size: `373`
- prototype: `CUITrace *__fastcall(CUITrace *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002320`

## callees

- `0x1800063b0`
- `0x18000a7c0`
- `0x180014198`
- `0x180014508`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014296`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014296`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800141d3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800141d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142a8`

## string_xrefs

- `0x1800142d0`: `com\complus\dtc\dtc\trace\src\uitrace.cpp`
- `0x180014237`: `com\complus\src\shared\util\utsem.cpp`
- `0x1800142ae`: `CreateEvent for m_hSessionEvent Failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CUITrace *__fastcall CUITrace::CUITrace(CUITrace *this)
{
  signed int LastError; // eax
  DWORD v2; // eax
  signed int v4; // [rsp+40h] [rbp-38h] BYREF
  __int16 v5; // [rsp+44h] [rbp-34h]
  int v6; // [rsp+48h] [rbp-30h]
  const unsigned __int16 *v7; // [rsp+50h] [rbp-28h]
  __int64 v8; // [rsp+58h] [rbp-20h]
  __int64 v9; // [rsp+60h] [rbp-18h]
  int v10; // [rsp+68h] [rbp-10h]
  int v11; // [rsp+6Ch] [rbp-Ch]

  qword_18015D4C0 = (__int64)&CSemExclusive::`vftable';
  dword_18015D4F0 = 0;
  if ( InitializeCriticalSectionAndSpinCount(&stru_18015D4C8, 0x1F4u) )
  {
    dword_18015D4F0 = 1;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v4 = LastError;
    v5 = 21;
    v6 = -1073606063;
    v7 = L"InitializeCriticalSectionAndSpinCount";
    v8 = 0;
    v9 = 0;
    v11 = 1;
    v10 = 1;
    CError::WriteToLog(
      (CError *)&v4,
      L"com\\complus\\src\\shared\\util\\utsem.cpp",
      148,
      L"InitializeCriticalSectionAndSpinCount");
  }
  g_UITrace = 0;
  dword_18015D4B8 = 0;
  qword_18015DB00 = 0;
  qword_18015DB08 = 0;
  hObject = 0;
  hObject = CreateEventW(0, 1, 0, 0);
  if ( hObject )
  {
    *(&g_UITrace + 1) = (unsigned int)CheckIfTraceDisabled() != 0 ? 1 : 3;
  }
  else
  {
    v2 = GetLastError();
    TraceStringInline(
      14,
      1,
      L"com\\complus\\dtc\\dtc\\trace\\src\\uitrace.cpp",
      38,
      L"CUITrace::CUITrace",
      v2,
      L"CreateEvent for m_hSessionEvent Failed");
    *(&g_UITrace + 1) = 2;
  }
  return (CUITrace *)&g_UITrace;
}

```

## disassembly

```asm
0x180014198  mov     rax, rsp
0x18001419b  mov     [rax+8], rcx
0x18001419f  push    rsi
0x1800141a0  sub     rsp, 70h
0x1800141a4  lea     rsi, ?g_UITrace@@3VCUITrace@@A; CUITrace g_UITrace
0x1800141ab  mov     [rax+8], rsi
0x1800141af  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x1800141b6  mov     cs:qword_18015D4C0, rax
0x1800141bd  mov     cs:dword_18015D4F0, 0
0x1800141c7  mov     edx, 1F4h; dwSpinCount
0x1800141cc  lea     rcx, stru_18015D4C8; lpCriticalSection
0x1800141d3  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800141d9  test    eax, eax
0x1800141db  jnz     short loc_18001424A
0x1800141dd  call    cs:__imp_GetLastError
0x1800141e3  test    eax, eax
0x1800141e5  jle     short loc_1800141EF
0x1800141e7  movzx   eax, ax
0x1800141ea  or      eax, 80070000h
0x1800141ef  mov     [rsp+78h+var_38], eax
0x1800141f3  mov     eax, 15h
0x1800141f8  mov     [rsp+78h+var_34], ax
0x1800141fd  mov     [rsp+78h+var_30], 0C0021251h
0x180014205  lea     r9, aInitializecrit; "InitializeCriticalSectionAndSpinCount"
0x18001420c  mov     [rsp+78h+var_28], r9
0x180014211  mov     [rsp+78h+var_20], 0
0x18001421a  mov     [rsp+78h+var_18], 0
0x180014223  mov     [rsp+78h+var_C], 1
0x18001422b  mov     [rsp+78h+var_10], 1
0x180014233  lea     r8d, [rax+7Fh]; unsigned int
0x180014237  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x18001423e  lea     rcx, [rsp+78h+var_38]; this
0x180014243  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180014248  jmp     short loc_180014254
0x18001424a  mov     cs:dword_18015D4F0, 1
0x180014254  mov     cs:?g_UITrace@@3VCUITrace@@A, 0; CUITrace g_UITrace
0x18001425f  mov     cs:dword_18015D4B8, 0
0x180014269  mov     cs:qword_18015DB00, 0
0x180014274  mov     cs:qword_18015DB08, 0
0x18001427f  mov     cs:hObject, 0
0x18001428a  xor     r9d, r9d; lpName
0x18001428d  xor     r8d, r8d; bInitialState
0x180014290  lea     edx, [r9+1]; bManualReset
0x180014294  xor     ecx, ecx; lpEventAttributes
0x180014296  call    cs:__imp_CreateEventW
0x18001429c  mov     cs:hObject, rax
0x1800142a3  test    rax, rax
0x1800142a6  jnz     short loc_1800142EF
0x1800142a8  call    cs:__imp_GetLastError
0x1800142ae  lea     rcx, aCreateeventFor; "CreateEvent for m_hSessionEvent Failed"
0x1800142b5  mov     [rsp+78h+var_48], rcx
0x1800142ba  mov     [rsp+78h+var_50], eax
0x1800142be  lea     rax, aCuitraceCuitra; "CUITrace::CUITrace"
0x1800142c5  mov     [rsp+78h+var_58], rax
0x1800142ca  mov     r9d, 26h ; '&'
0x1800142d0  lea     r8, aComComplusDtcD_23; "com\\complus\\dtc\\dtc\\trace\\src\\uit"...
0x1800142d7  lea     edx, [r9-25h]
0x1800142db  lea     ecx, [rdx+0Dh]
0x1800142de  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800142e3  mov     dword ptr cs:?g_UITrace@@3VCUITrace@@A+4, 2; CUITrace g_UITrace
0x1800142ed  jmp     short loc_180014304
0x1800142ef  call    CheckIfTraceDisabled
0x1800142f4  neg     eax
0x1800142f6  sbb     ecx, ecx
0x1800142f8  and     ecx, 0FFFFFFFEh
0x1800142fb  add     ecx, 3
0x1800142fe  mov     dword ptr cs:?g_UITrace@@3VCUITrace@@A+4, ecx; CUITrace g_UITrace
0x180014304  mov     rax, rsi
0x180014307  add     rsp, 70h
0x18001430b  pop     rsi
0x18001430c  retn
```
