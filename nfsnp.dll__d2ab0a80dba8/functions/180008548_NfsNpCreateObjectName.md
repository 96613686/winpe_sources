# NfsNpCreateObjectName

- ea: `0x180008548`
- end: `0x18000872a`
- name: `NfsNpCreateObjectName`
- size: `482`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x180004720`

## callees

- `0x1800023f0`
- `0x180008548`
- `0x180011ba0`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x180008637`
- `msvcrt!_snwprintf_s` at `0x180008637`
- `ntdll!RtlCopyLuid` at `0x18000860f`
- `ntdll!RtlCopyLuid` at `0x18000860f`
- `ntdll!NtQueryInformationToken` at `0x1800085f7`
- `ntdll!NtQueryInformationToken` at `0x1800085f7`
- `ntdll!RtlAppendUnicodeToString` at `0x1800085aa`
- `ntdll!RtlAppendUnicodeToString` at `0x180008648`
- `ntdll!RtlAppendUnicodeToString` at `0x18000865d`
- `ntdll!RtlAppendUnicodeToString` at `0x180008673`
- `ntdll!RtlAppendUnicodeToString` at `0x18000868c`
- `ntdll!RtlAppendUnicodeToString` at `0x18000869d`
- `ntdll!RtlAppendUnicodeToString` at `0x1800086b2`
- `ntdll!RtlAppendUnicodeToString` at `0x1800086c3`
- `ntdll!RtlAppendUnicodeToString` at `0x1800085aa`
- `ntdll!RtlAppendUnicodeToString` at `0x180008648`
- `ntdll!RtlAppendUnicodeToString` at `0x18000865d`
- `ntdll!RtlAppendUnicodeToString` at `0x180008673`
- `ntdll!RtlAppendUnicodeToString` at `0x18000868c`
- `ntdll!RtlAppendUnicodeToString` at `0x18000869d`
- `ntdll!RtlAppendUnicodeToString` at `0x1800086b2`
- `ntdll!RtlAppendUnicodeToString` at `0x1800086c3`

## pseudocode

```c
__int64 __fastcall NfsNpCreateObjectName(WCHAR *a1, __int64 a2, const WCHAR *a3, const WCHAR *a4, const WCHAR *Source)
{
  NTSTATUS v7; // ebx
  NTSTATUS appended; // eax
  unsigned int v9; // edx
  PULONG ReturnLength; // [rsp+20h] [rbp-71h]
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-61h] BYREF
  ULONG v13; // [rsp+40h] [rbp-51h] BYREF
  _LUID DestinationLuid; // [rsp+48h] [rbp-49h] BYREF
  _OWORD TokenInformation[3]; // [rsp+50h] [rbp-41h] BYREF
  __int64 v16; // [rsp+80h] [rbp-11h]
  wchar_t Buffer[8]; // [rsp+88h] [rbp-9h] BYREF
  __int128 v18; // [rsp+98h] [rbp+7h]
  __int128 v19; // [rsp+A8h] [rbp+17h]

  Destination.Buffer = a1;
  DestinationLuid = 0;
  a1[259] = 0;
  *(_QWORD *)&Destination.Length = 33947648;
  *(_OWORD *)Buffer = 0;
  v18 = 0;
  v19 = 0;
  if ( RtlAppendUnicodeToString(&Destination, L"\\Device\\MRxNfs") < 0 )
    return 3221225507LL;
  if ( !a3 )
  {
LABEL_7:
    if ( RtlAppendUnicodeToString(&Destination, L"\\") >= 0
      && RtlAppendUnicodeToString(&Destination, a4) >= 0
      && RtlAppendUnicodeToString(&Destination, L"\\") >= 0 )
    {
      appended = RtlAppendUnicodeToString(&Destination, Source);
      v9 = -1073741789;
      if ( appended >= 0 )
        return 0;
      return v9;
    }
    return 3221225507LL;
  }
  v16 = 0;
  v13 = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v7 = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenStatistics, TokenInformation, 0x38u, &v13);
  if ( v7 >= 0 )
  {
    RtlCopyLuid(&DestinationLuid, (PLUID)TokenInformation + 1);
    LODWORD(ReturnLength) = DestinationLuid.HighPart;
    _snwprintf_s(Buffer, 0x18u, 0x17u, L"%08x%08x", ReturnLength, DestinationLuid.LowPart);
    if ( RtlAppendUnicodeToString(&Destination, L"\\;") < 0
      || RtlAppendUnicodeToString(&Destination, a3) < 0
      || RtlAppendUnicodeToString(&Destination, Buffer) < 0 )
    {
      return 3221225507LL;
    }
    goto LABEL_7;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008548  push    rbp
0x18000854a  push    rbx
0x18000854b  push    rsi
0x18000854c  push    rdi
0x18000854d  push    r14
0x18000854f  lea     rbp, [rsp-2Fh]
0x180008554  sub     rsp, 0C0h
0x18000855b  mov     rax, cs:__security_cookie
0x180008562  xor     rax, rsp
0x180008565  mov     [rbp+4Fh+var_28], rax
0x180008569  mov     r14, [rbp+4Fh+Source]
0x18000856d  lea     rdx, SourceString; "\\Device\\MRxNfs"
0x180008574  xorps   xmm0, xmm0
0x180008577  mov     [rbp+4Fh+Destination.Buffer], rcx
0x18000857b  xor     eax, eax
0x18000857d  mov     qword ptr [rbp+4Fh+DestinationLuid.LowPart], 0
0x180008585  mov     [rcx+206h], ax
0x18000858c  mov     rsi, r9
0x18000858f  lea     rcx, [rbp+4Fh+Destination]; Destination
0x180008593  mov     qword ptr [rbp+4Fh+Destination.Length], 2060000h
0x18000859b  mov     rdi, r8
0x18000859e  movups  xmmword ptr [rbp+4Fh+Buffer], xmm0
0x1800085a2  movups  [rbp+4Fh+var_48], xmm0
0x1800085a6  movups  [rbp+4Fh+var_38], xmm0
0x1800085aa  call    cs:__imp_RtlAppendUnicodeToString
0x1800085b0  test    eax, eax
0x1800085b2  js      loc_18000870B
0x1800085b8  test    rdi, rdi
0x1800085bb  jz      loc_180008681
0x1800085c1  xor     eax, eax
0x1800085c3  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x1800085c7  xorps   xmm0, xmm0
0x1800085ca  mov     [rbp+4Fh+var_60], rax
0x1800085ce  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800085d4  mov     [rbp+4Fh+var_A0], eax
0x1800085d7  lea     rax, [rbp+4Fh+var_A0]
0x1800085db  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x1800085e2  movups  [rbp+4Fh+TokenInformation], xmm0
0x1800085e6  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800085eb  lea     edx, [r9-2Eh]; TokenInformationClass
0x1800085ef  movups  [rbp+4Fh+var_80], xmm0
0x1800085f3  movups  [rbp+4Fh+var_70], xmm0
0x1800085f7  call    cs:__imp_NtQueryInformationToken
0x1800085fd  mov     ebx, eax
0x1800085ff  test    eax, eax
0x180008601  js      loc_1800086D9
0x180008607  lea     rdx, [rbp+4Fh+TokenInformation+8]; SourceLuid
0x18000860b  lea     rcx, [rbp+4Fh+DestinationLuid]; DestinationLuid
0x18000860f  call    cs:__imp_RtlCopyLuid
0x180008615  mov     eax, [rbp+4Fh+DestinationLuid.LowPart]
0x180008618  lea     r9, a08x08x; "%08x%08x"
0x18000861f  mov     [rsp+0E0h+var_B8], eax
0x180008623  lea     rcx, [rbp+4Fh+Buffer]; Buffer
0x180008627  mov     eax, [rbp+4Fh+DestinationLuid.HighPart]
0x18000862a  mov     edx, 18h; BufferCount
0x18000862f  mov     dword ptr [rsp+0E0h+ReturnLength], eax
0x180008633  lea     r8d, [rdx-1]; MaxCount
0x180008637  call    cs:__imp__snwprintf_s
0x18000863d  lea     rdx, asc_18001435C; "\\;"
0x180008644  lea     rcx, [rbp+4Fh+Destination]; Destination
0x180008648  call    cs:__imp_RtlAppendUnicodeToString
0x18000864e  test    eax, eax
0x180008650  js      loc_18000870B
0x180008656  mov     rdx, rdi; Source
0x180008659  lea     rcx, [rbp+4Fh+Destination]; Destination
0x18000865d  call    cs:__imp_RtlAppendUnicodeToString
0x180008663  test    eax, eax
0x180008665  js      loc_18000870B
0x18000866b  lea     rdx, [rbp+4Fh+Buffer]; Source
0x18000866f  lea     rcx, [rbp+4Fh+Destination]; Destination
0x180008673  call    cs:__imp_RtlAppendUnicodeToString
0x180008679  test    eax, eax
0x18000867b  js      loc_18000870B
0x180008681  lea     rdx, SubStr; "\\"
0x180008688  lea     rcx, [rbp+4Fh+Destination]; Destination
0x18000868c  call    cs:__imp_RtlAppendUnicodeToString
0x180008692  test    eax, eax
0x180008694  js      short loc_18000870B
0x180008696  mov     rdx, rsi; Source
0x180008699  lea     rcx, [rbp+4Fh+Destination]; Destination
0x18000869d  call    cs:__imp_RtlAppendUnicodeToString
0x1800086a3  test    eax, eax
0x1800086a5  js      short loc_18000870B
0x1800086a7  lea     rdx, SubStr; "\\"
0x1800086ae  lea     rcx, [rbp+4Fh+Destination]; Destination
0x1800086b2  call    cs:__imp_RtlAppendUnicodeToString
0x1800086b8  test    eax, eax
0x1800086ba  js      short loc_18000870B
0x1800086bc  mov     rdx, r14; Source
0x1800086bf  lea     rcx, [rbp+4Fh+Destination]; Destination
0x1800086c3  call    cs:__imp_RtlAppendUnicodeToString
0x1800086c9  xor     ecx, ecx
0x1800086cb  mov     edx, 0C0000023h
0x1800086d0  test    eax, eax
0x1800086d2  cmovns  edx, ecx
0x1800086d5  mov     eax, edx
0x1800086d7  jmp     short loc_180008710
0x1800086d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086e0  lea     rax, WPP_GLOBAL_Control
0x1800086e7  cmp     rcx, rax
0x1800086ea  jz      short loc_180008707
0x1800086ec  test    byte ptr [rcx+1Ch], 2
0x1800086f0  jz      short loc_180008707
0x1800086f2  mov     rcx, [rcx+10h]
0x1800086f6  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800086fd  mov     edx, 0FBh
0x180008702  call    WPP_SF_
0x180008707  mov     eax, ebx
0x180008709  jmp     short loc_180008710
0x18000870b  mov     eax, 0C0000023h
0x180008710  mov     rcx, [rbp+4Fh+var_28]
0x180008714  xor     rcx, rsp; StackCookie
0x180008717  call    __security_check_cookie
0x18000871c  add     rsp, 0C0h
0x180008723  pop     r14
0x180008725  pop     rdi
0x180008726  pop     rsi
0x180008727  pop     rbx
0x180008728  pop     rbp
0x180008729  retn
```
