# WfpFwpmNetEventHeaderPrint

- ea: `0x18000f7f0`
- end: `0x18000fb30`
- name: `WfpFwpmNetEventHeaderPrint`
- size: `832`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001055c`

## callees

- `0x18000ef2c`
- `0x18000f020`
- `0x18000f124`
- `0x18000f7f0`
- `0x1800107e8`
- `0x180010974`
- `0x180011340`
- `0x180012010`

## import_xrefs

- `ntdll!RtlTimeToTimeFields` at `0x18000f880`
- `ntdll!RtlTimeToTimeFields` at `0x18000f880`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000f9af`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000f9c7`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000f9af`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000f9c7`

## string_xrefs

- `0x18000f982`: `%sIP protocol: %lu\n`
- `0x18000fa80`: `%sUser SID: `

## pseudocode

```c
__int64 __fastcall WfpFwpmNetEventHeaderPrint(
        void (__fastcall *a1)(__int64, const wchar_t *),
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  wchar_t **v8; // r15
  wchar_t *v9; // r15
  unsigned int v10; // r14d
  __int64 v11; // rax
  const wchar_t *v12; // r9
  int Month; // [rsp+20h] [rbp-E0h]
  int Day; // [rsp+28h] [rbp-D8h]
  int Hour; // [rsp+30h] [rbp-D0h]
  int Minute; // [rsp+38h] [rbp-C8h]
  int Second; // [rsp+40h] [rbp-C0h]
  int Milliseconds; // [rsp+48h] [rbp-B8h]
  union _LARGE_INTEGER Time; // [rsp+50h] [rbp-B0h] BYREF
  _TIME_FIELDS TimeFields; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszDest[28]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR v23[72]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR S[72]; // [rsp+130h] [rbp+30h] BYREF

  if ( a3 < 7 )
    v8 = (wchar_t **)((char *)&off_180014118 + 8 * a3);
  else
    v8 = off_180014148;
  v9 = *v8;
  ((void (*)(__int64, const wchar_t *, ...))a1)(a2, L"%sTimestamp: ", v9);
  Time = *(union _LARGE_INTEGER *)a4;
  TimeFields = 0;
  RtlTimeToTimeFields(&Time, &TimeFields);
  Milliseconds = TimeFields.Milliseconds;
  Second = TimeFields.Second;
  Minute = TimeFields.Minute;
  Hour = TimeFields.Hour;
  Day = TimeFields.Day;
  Month = TimeFields.Month;
  StringCchPrintfW(
    pszDest,
    0x19u,
    L"%04hu-%02hu-%02huT%02hu:%02hu:%02hu.%03huZ",
    (unsigned int)TimeFields.Year,
    Month,
    Day,
    Hour,
    Minute,
    Second,
    Milliseconds);
  ((void (*)(__int64, const wchar_t *, ...))a1)(a2, L"%s", pszDest);
  a1(a2, L"\n");
  ((void (*)(__int64, const wchar_t *, ...))a1)(a2, L"%sFlags: 0x%08x\n", v9, *(unsigned int *)(a4 + 8));
  v10 = a3 + 1;
  WfpFlagsPrint((_DWORD)a1, a2, v10, 11, (__int64)&qword_180014280, *(_DWORD *)(a4 + 8));
  v11 = *(int *)(a4 + 12);
  if ( (unsigned int)v11 > 2 )
    v12 = L"<invalid>";
  else
    v12 = off_180014218[v11];
  ((void (*)(__int64, const wchar_t *, ...))a1)(a2, L"%sIP version: %s\n", v9, v12);
  ((void (*)(__int64, const wchar_t *, ...))a1)(a2, L"%sIP protocol: %lu\n", v9, *(unsigned __int8 *)(a4 + 16));
  if ( *(_DWORD *)(a4 + 12) )
  {
    if ( *(_DWORD *)(a4 + 12) == 1 )
    {
      WfpIPv6AddrToString(a4 + 20, S);
      WfpIPv6AddrToString(a4 + 36, v23);
    }
    else
    {
      S[0] = 0;
      v23[0] = 0;
    }
  }
  else
  {
    Time.LowPart = _byteswap_ulong(*(_DWORD *)(a4 + 20));
    RtlIpv4AddressToStringW((const struct in_addr *)&Time, S);
    Time.LowPart = _byteswap_ulong(*(_DWORD *)(a4 + 36));
    RtlIpv4AddressToStringW((const struct in_addr *)&Time, v23);
  }
  ((void (*)(__int64, const wchar_t *, ...))a1)(a2, L"%sLocal address: %s\n%sRemote address: %s\n", v9, S, v9, v23);
  ((void (*)(__int64, const wchar_t *, ...))a1)(a2, L"%sLocal Port: %lu\n", v9, *(unsigned __int16 *)(a4 + 52));
  ((void (*)(__int64, const wchar_t *, ...))a1)(a2, L"%sRemote Port: %lu\n", v9, *(unsigned __int16 *)(a4 + 54));
  ((void (*)(__int64, const wchar_t *, ...))a1)(a2, L"%sApplication ID:\n", v9);
  WfpFwpByteBlobPrint(a1, a2, v10, a4 + 64);
  ((void (*)(__int64, const wchar_t *, ...))a1)(a2, L"%sUser SID: ", v9);
  WfpSidPrint(a1, a2, *(void **)(a4 + 80));
  ((void (*)(__int64, const wchar_t *, ...))a1)(a2, L"%Enterprise ID: %s", v9, *(_QWORD *)(a4 + 104));
  ((void (*)(__int64, const wchar_t *, ...))a1)(a2, L"%sPolicy Flags: %I64u\n", v9, *(_QWORD *)(a4 + 112));
  ((void (*)(__int64, const wchar_t *, ...))a1)(a2, L"%sEffevtive Name:\n", v9);
  WfpFwpByteBlobPrint(a1, a2, v10, a4 + 120);
  return ((__int64 (__fastcall *)(__int64, const wchar_t *, wchar_t *))a1)(a2, L"\n", v9);
}

```

## disassembly

```asm
0x18000f7f0  push    rbp
0x18000f7f2  push    rbx
0x18000f7f3  push    rsi
0x18000f7f4  push    rdi
0x18000f7f5  push    r12
0x18000f7f7  push    r14
0x18000f7f9  push    r15
0x18000f7fb  lea     rbp, [rsp-0D0h]
0x18000f803  sub     rsp, 1D0h
0x18000f80a  mov     rax, cs:__security_cookie
0x18000f811  xor     rax, rsp
0x18000f814  mov     [rbp+100h+var_40], rax
0x18000f81b  mov     r14d, r8d
0x18000f81e  mov     rbx, r9
0x18000f821  lea     r12, cs:180000000h
0x18000f828  mov     rsi, rdx
0x18000f82b  mov     rdi, rcx
0x18000f82e  cmp     r8d, 7
0x18000f832  jb      short loc_18000F83D
0x18000f834  lea     r15, off_180014148; "            "
0x18000f83b  jmp     short loc_18000F849
0x18000f83d  lea     r15, rva off_180014118[r12]
0x18000f845  lea     r15, [r15+r14*8]
0x18000f849  mov     r15, [r15]
0x18000f84c  lea     rdx, aStimestamp; "%sTimestamp: "
0x18000f853  mov     r8, r15
0x18000f856  mov     rcx, rsi
0x18000f859  mov     rax, rdi
0x18000f85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f861  mov     eax, [rbx]
0x18000f863  lea     rdx, [rsp+200h+TimeFields]; TimeFields
0x18000f868  mov     dword ptr [rsp+200h+Time], eax
0x18000f86c  lea     rcx, [rsp+200h+Time]; Time
0x18000f871  mov     eax, [rbx+4]
0x18000f874  xorps   xmm0, xmm0
0x18000f877  mov     dword ptr [rsp+200h+Time+4], eax
0x18000f87b  movups  xmmword ptr [rsp+200h+TimeFields.Year], xmm0
0x18000f880  call    cs:__imp_RtlTimeToTimeFields
0x18000f886  movsx   ecx, [rsp+200h+TimeFields.Second]
0x18000f88b  movsx   edx, [rsp+200h+TimeFields.Minute]
0x18000f890  movsx   r8d, [rsp+200h+TimeFields.Hour]
0x18000f896  movsx   eax, [rsp+200h+TimeFields.Milliseconds]
0x18000f89b  movsx   r10d, [rsp+200h+TimeFields.Day]
0x18000f8a1  movsx   r11d, [rsp+200h+TimeFields.Month]
0x18000f8a7  movsx   r9d, [rsp+200h+TimeFields.Year]
0x18000f8ad  mov     [rsp+200h+var_1B8], eax
0x18000f8b1  mov     [rsp+200h+var_1C0], ecx
0x18000f8b5  lea     rcx, [rsp+200h+pszDest]; pszDest
0x18000f8ba  mov     [rsp+200h+var_1C8], edx
0x18000f8be  mov     edx, 19h; cchDest
0x18000f8c3  mov     [rsp+200h+var_1D0], r8d
0x18000f8c8  lea     r8, a04hu02hu02hut0; "%04hu-%02hu-%02huT%02hu:%02hu:%02hu.%03"...
0x18000f8cf  mov     dword ptr [rsp+200h+var_1D8], r10d
0x18000f8d4  mov     dword ptr [rsp+200h+var_1E0], r11d
0x18000f8d9  call    StringCchPrintfW
0x18000f8de  lea     r8, [rsp+200h+pszDest]
0x18000f8e3  mov     rcx, rsi
0x18000f8e6  lea     rdx, aS_1; "%s"
0x18000f8ed  mov     rax, rdi
0x18000f8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8f5  lea     rdx, asc_180016B44; "\n"
0x18000f8fc  mov     rcx, rsi
0x18000f8ff  mov     rax, rdi
0x18000f902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f907  mov     r9d, [rbx+8]
0x18000f90b  lea     rdx, aSflags0x08x; "%sFlags: 0x%08x\n"
0x18000f912  mov     r8, r15
0x18000f915  mov     rcx, rsi
0x18000f918  mov     rax, rdi
0x18000f91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f920  mov     eax, [rbx+8]
0x18000f923  inc     r14d
0x18000f926  mov     dword ptr [rsp+200h+var_1D8], eax
0x18000f92a  mov     r9d, 0Bh
0x18000f930  lea     rax, qword_180014280
0x18000f937  mov     r8d, r14d
0x18000f93a  mov     rdx, rsi
0x18000f93d  mov     [rsp+200h+var_1E0], rax
0x18000f942  mov     rcx, rdi
0x18000f945  call    WfpFlagsPrint
0x18000f94a  movsxd  rax, dword ptr [rbx+0Ch]
0x18000f94e  test    eax, eax
0x18000f950  js      short loc_18000F961
0x18000f952  cmp     eax, 3
0x18000f955  jnb     short loc_18000F961
0x18000f957  mov     r9, ds:rva off_180014218[r12+rax*8]; "IPv4" ...
0x18000f95f  jmp     short loc_18000F968
0x18000f961  lea     r9, aInvalid; "<invalid>"
0x18000f968  mov     r8, r15
0x18000f96b  lea     rdx, aSipVersionS; "%sIP version: %s\n"
0x18000f972  mov     rcx, rsi
0x18000f975  mov     rax, rdi
0x18000f978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f97d  movzx   r9d, byte ptr [rbx+10h]
0x18000f982  lea     rdx, aSipProtocolLu; "%sIP protocol: %lu\n"
0x18000f989  mov     r8, r15
0x18000f98c  mov     rcx, rsi
0x18000f98f  mov     rax, rdi
0x18000f992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f997  cmp     dword ptr [rbx+0Ch], 0
0x18000f99b  jnz     short loc_18000F9CF
0x18000f99d  mov     eax, [rbx+14h]
0x18000f9a0  lea     rdx, [rbp+100h+S]; S
0x18000f9a4  bswap   eax
0x18000f9a6  lea     rcx, [rsp+200h+Time]; Addr
0x18000f9ab  mov     dword ptr [rsp+200h+Time], eax
0x18000f9af  call    cs:__imp_RtlIpv4AddressToStringW
0x18000f9b5  mov     eax, [rbx+24h]
0x18000f9b8  lea     rdx, [rbp+100h+var_160]; S
0x18000f9bc  bswap   eax
0x18000f9be  lea     rcx, [rsp+200h+Time]; Addr
0x18000f9c3  mov     dword ptr [rsp+200h+Time], eax
0x18000f9c7  call    cs:__imp_RtlIpv4AddressToStringW
0x18000f9cd  jmp     short loc_18000F9FB
0x18000f9cf  cmp     dword ptr [rbx+0Ch], 1
0x18000f9d3  jnz     short loc_18000F9F1
0x18000f9d5  lea     rcx, [rbx+14h]
0x18000f9d9  lea     rdx, [rbp+100h+S]
0x18000f9dd  call    WfpIPv6AddrToString
0x18000f9e2  lea     rcx, [rbx+24h]
0x18000f9e6  lea     rdx, [rbp+100h+var_160]
0x18000f9ea  call    WfpIPv6AddrToString
0x18000f9ef  jmp     short loc_18000F9FB
0x18000f9f1  xor     eax, eax
0x18000f9f3  mov     [rbp+100h+S], ax
0x18000f9f7  mov     [rbp+100h+var_160], ax
0x18000f9fb  lea     rax, [rbp+100h+var_160]
0x18000f9ff  mov     r8, r15
0x18000fa02  mov     [rsp+200h+var_1D8], rax
0x18000fa07  lea     r9, [rbp+100h+S]
0x18000fa0b  mov     rax, rdi
0x18000fa0e  mov     [rsp+200h+var_1E0], r15
0x18000fa13  lea     rdx, aSlocalAddressS; "%sLocal address: %s\n%sRemote address: "...
0x18000fa1a  mov     rcx, rsi
0x18000fa1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa22  movzx   r9d, word ptr [rbx+34h]
0x18000fa27  lea     rdx, aSlocalPortLu; "%sLocal Port: %lu\n"
0x18000fa2e  mov     r8, r15
0x18000fa31  mov     rcx, rsi
0x18000fa34  mov     rax, rdi
0x18000fa37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa3c  movzx   r9d, word ptr [rbx+36h]
0x18000fa41  lea     rdx, aSremotePortLu; "%sRemote Port: %lu\n"
0x18000fa48  mov     r8, r15
0x18000fa4b  mov     rcx, rsi
0x18000fa4e  mov     rax, rdi
0x18000fa51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa56  mov     r8, r15
0x18000fa59  lea     rdx, aSapplicationId; "%sApplication ID:\n"
0x18000fa60  mov     rcx, rsi
0x18000fa63  mov     rax, rdi
0x18000fa66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa6b  lea     r9, [rbx+40h]
0x18000fa6f  mov     r8d, r14d
0x18000fa72  mov     rdx, rsi
0x18000fa75  mov     rcx, rdi
0x18000fa78  call    WfpFwpByteBlobPrint
0x18000fa7d  mov     r8, r15
0x18000fa80  lea     rdx, aSuserSid; "%sUser SID: "
0x18000fa87  mov     rcx, rsi
0x18000fa8a  mov     rax, rdi
0x18000fa8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa92  mov     r8, [rbx+50h]
0x18000fa96  mov     rdx, rsi
0x18000fa99  mov     rcx, rdi
0x18000fa9c  call    WfpSidPrint
0x18000faa1  mov     r9, [rbx+68h]
0x18000faa5  lea     rdx, aEnterpriseIdS; "%Enterprise ID: %s"
0x18000faac  mov     r8, r15
0x18000faaf  mov     rcx, rsi
0x18000fab2  mov     rax, rdi
0x18000fab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faba  mov     r9, [rbx+70h]
0x18000fabe  lea     rdx, aSpolicyFlagsI6; "%sPolicy Flags: %I64u\n"
0x18000fac5  mov     r8, r15
0x18000fac8  mov     rcx, rsi
0x18000facb  mov     rax, rdi
0x18000face  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fad3  mov     r8, r15
0x18000fad6  lea     rdx, aSeffevtiveName; "%sEffevtive Name:\n"
0x18000fadd  mov     rcx, rsi
0x18000fae0  mov     rax, rdi
0x18000fae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fae8  lea     r9, [rbx+78h]
0x18000faec  mov     r8d, r14d
0x18000faef  mov     rdx, rsi
0x18000faf2  mov     rcx, rdi
0x18000faf5  call    WfpFwpByteBlobPrint
0x18000fafa  mov     r8, r15
0x18000fafd  lea     rdx, asc_180016B44; "\n"
0x18000fb04  mov     rcx, rsi
0x18000fb07  mov     rax, rdi
0x18000fb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb0f  mov     rcx, [rbp+100h+var_40]
0x18000fb16  xor     rcx, rsp; StackCookie
0x18000fb19  call    __security_check_cookie
0x18000fb1e  add     rsp, 1D0h
0x18000fb25  pop     r15
0x18000fb27  pop     r14
0x18000fb29  pop     r12
0x18000fb2b  pop     rdi
0x18000fb2c  pop     rsi
0x18000fb2d  pop     rbx
0x18000fb2e  pop     rbp
0x18000fb2f  retn
```
