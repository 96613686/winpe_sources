# CreateCVMapForMDMEnrollments(ushort const *,char const *)

- ea: `0x180011360`
- end: `0x18001171e`
- name: `?CreateCVMapForMDMEnrollments@@YAJPEBGPEBD@Z`
- size: `958`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const char *Str)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x18000e5dc`

## callees

- `0x1800071c0`
- `0x18000dd20`
- `0x180011360`
- `0x1800118f8`
- `0x180011938`
- `0x18002d998`
- `0x18002e1a0`
- `0x1800404a8`
- `0x180070880`
- `0x1800745a4`
- `0x180074980`
- `0x180074df8`
- `0x180075210`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800113f2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011572`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800113f2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011572`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800114e9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800114e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011420`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001147a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800114bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011517`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011681`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011692`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011420`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001147a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800114bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011517`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011681`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011692`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall CreateCVMapForMDMEnrollments(const unsigned __int16 *a1, const char *Str)
{
  const WCHAR *v4; // rax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  int v8; // eax
  int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  bool v12; // dl
  unsigned int v13; // edx
  struct TraceLoggingCorrelationVector *v14; // rbx
  __int64 i; // rdi
  int updated; // eax
  unsigned int v17; // edx
  unsigned int v18; // esi
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  char v26[144]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  if ( !Str || !a1 )
    return 2147942487LL;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v4 = (const WCHAR *)DMGetKnownRegPath(0);
  v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0, 0, 6u, 0, &hKey, 0);
  if ( v5 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xE0,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\logger\\loggerutils.cpp",
           (const char *)v5,
           dwOptions);
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
  v25 = 0;
  cbData = 0;
  v8 = StringCbLengthW(a1, 0xFFFFFFFE, &v25);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\logger\\loggerutils.cpp",
      (const char *)(unsigned int)v8,
      dwOptions);
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
  v9 = ULongLongToULong(v25, &cbData);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\logger\\loggerutils.cpp",
      (const char *)(unsigned int)v9,
      dwOptions);
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
  v10 = RegSetValueExW(hKey, L"CurrentEnrollmentId", 0, 1u, (const BYTE *)a1, cbData);
  if ( v10 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xF0,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\logger\\loggerutils.cpp",
           (const char *)v10,
           dwOptionsa);
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v11 = RegCreateKeyExW(hKey, a1, 0, 0, 0, 6u, 0, &phkResult, 0);
  if ( v11 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xFD,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\logger\\loggerutils.cpp",
           (const char *)v11,
           dwOptionsb);
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
  v14 = TraceLoggingCorrelationVector::Set(Str, v12);
  if ( v14 )
  {
    for ( i = 0; (unsigned int)i < 7; i = (unsigned int)(i + 1) )
    {
      if ( !TraceLoggingCorrelationVector::ToStringImpl(
              v14,
              _InterlockedExchangeAdd64((volatile signed __int64 *)v14 + 17, 0),
              v26) )
      {
        if ( phkResult )
          RegCloseKey(phkResult);
        if ( hKey )
          RegCloseKey(hKey);
        return 2147500037LL;
      }
      updated = UpdateMapWithCV(v26, (const unsigned __int16 *)*(&off_18007CE40 + i), phkResult);
      v18 = updated;
      if ( updated < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x110,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\logger\\loggerutils.cpp",
          (const char *)(unsigned int)updated,
          dwOptionsb);
        if ( phkResult )
          RegCloseKey(phkResult);
        if ( hKey )
          RegCloseKey(hKey);
        return v18;
      }
      if ( v14 )
        TraceLoggingCorrelationVector::`scalar deleting destructor'(v14, v17);
      v14 = TraceLoggingCorrelationVector::Extend(v26, v17);
    }
    if ( v14 )
      TraceLoggingCorrelationVector::`scalar deleting destructor'(v14, v13);
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x180011360  mov     [rsp-8+arg_10], rbx
0x180011365  push    rbp
0x180011366  push    rsi
0x180011367  push    rdi
0x180011368  lea     rbp, [rsp-10h]
0x18001136d  sub     rsp, 110h
0x180011374  mov     rax, cs:__security_cookie
0x18001137b  xor     rax, rsp
0x18001137e  mov     [rbp+20h+var_20], rax
0x180011382  mov     rsi, rdx
0x180011385  mov     rdi, rcx
0x180011388  test    rdx, rdx
0x18001138b  jz      loc_1800116FA
0x180011391  test    rcx, rcx
0x180011394  jz      loc_1800116FA
0x18001139a  mov     [rsp+120h+hKey], 0
0x1800113a3  xor     edx, edx
0x1800113a5  lea     rcx, [rsp+120h+hKey]
0x1800113aa  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800113af  xor     ecx, ecx
0x1800113b1  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1800113b6  mov     [rsp+120h+lpdwDisposition], 0; lpdwDisposition
0x1800113bf  lea     rcx, [rsp+120h+hKey]
0x1800113c4  mov     [rsp+120h+phkResult], rcx; phkResult
0x1800113c9  mov     [rsp+120h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800113d2  mov     [rsp+120h+samDesired], 6; samDesired
0x1800113da  mov     [rsp+120h+dwOptions], 0; int
0x1800113e2  xor     r9d, r9d; lpClass
0x1800113e5  xor     r8d, r8d; Reserved
0x1800113e8  mov     rdx, rax; lpSubKey
0x1800113eb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800113f2  call    cs:__imp_RegCreateKeyExW
0x1800113f8  test    eax, eax
0x1800113fa  jz      short loc_18001142E
0x1800113fc  mov     rcx, [rbp+28h]; this
0x180011400  mov     r9d, eax; char *
0x180011403  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001140a  mov     edx, 0E0h; void *
0x18001140f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180011414  mov     ebx, eax
0x180011416  mov     rcx, [rsp+120h+hKey]; hKey
0x18001141b  test    rcx, rcx
0x18001141e  jz      short loc_180011427
0x180011420  call    cs:__imp_RegCloseKey
0x180011426  nop
0x180011427  mov     eax, ebx
0x180011429  jmp     loc_1800116FF
0x18001142e  mov     [rsp+120h+var_B8], 0
0x180011437  mov     [rsp+120h+cbData], 0
0x18001143f  lea     r8, [rsp+120h+var_B8]; unsigned __int64 *
0x180011444  mov     edx, 0FFFFFFFEh; unsigned __int64
0x180011449  mov     rcx, rdi; unsigned __int16 *
0x18001144c  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180011451  mov     ebx, eax
0x180011453  test    eax, eax
0x180011455  jns     short loc_180011483
0x180011457  mov     rcx, [rbp+28h]; this
0x18001145b  mov     r9d, eax; char *
0x18001145e  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180011465  mov     edx, 0E5h; void *
0x18001146a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001146f  nop
0x180011470  mov     rcx, [rsp+120h+hKey]; hKey
0x180011475  test    rcx, rcx
0x180011478  jz      short loc_180011481
0x18001147a  call    cs:__imp_RegCloseKey
0x180011480  nop
0x180011481  jmp     short loc_180011427
0x180011483  lea     rdx, [rsp+120h+cbData]; unsigned int *
0x180011488  mov     rcx, [rsp+120h+var_B8]; unsigned __int64
0x18001148d  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180011492  mov     ebx, eax
0x180011494  test    eax, eax
0x180011496  jns     short loc_1800114C7
0x180011498  mov     rcx, [rbp+28h]; this
0x18001149c  mov     r9d, eax; char *
0x18001149f  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800114a6  mov     edx, 0E7h; void *
0x1800114ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800114b0  nop
0x1800114b1  mov     rcx, [rsp+120h+hKey]; hKey
0x1800114b6  test    rcx, rcx
0x1800114b9  jz      short loc_1800114C2
0x1800114bb  call    cs:__imp_RegCloseKey
0x1800114c1  nop
0x1800114c2  jmp     loc_180011427
0x1800114c7  mov     eax, [rsp+120h+cbData]
0x1800114cb  mov     [rsp+120h+samDesired], eax; cbData
0x1800114cf  mov     qword ptr [rsp+120h+dwOptions], rdi; unsigned int
0x1800114d4  mov     r9d, 1; dwType
0x1800114da  xor     r8d, r8d; Reserved
0x1800114dd  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x1800114e4  mov     rcx, [rsp+120h+hKey]; hKey
0x1800114e9  call    cs:__imp_RegSetValueExW
0x1800114ef  test    eax, eax
0x1800114f1  jz      short loc_180011523
0x1800114f3  mov     rcx, [rbp+28h]; this
0x1800114f7  mov     r9d, eax; char *
0x1800114fa  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180011501  mov     edx, 0F0h; void *
0x180011506  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001150b  mov     ebx, eax
0x18001150d  mov     rcx, [rsp+120h+hKey]; hKey
0x180011512  test    rcx, rcx
0x180011515  jz      short loc_18001151E
0x180011517  call    cs:__imp_RegCloseKey
0x18001151d  nop
0x18001151e  jmp     loc_180011427
0x180011523  mov     [rsp+120h+var_C8], 0
0x18001152c  xor     edx, edx
0x18001152e  lea     rcx, [rsp+120h+var_C8]
0x180011533  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180011538  mov     [rsp+120h+lpdwDisposition], 0; lpdwDisposition
0x180011541  lea     rax, [rsp+120h+var_C8]
0x180011546  mov     [rsp+120h+phkResult], rax; phkResult
0x18001154b  mov     [rsp+120h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180011554  mov     [rsp+120h+samDesired], 6; samDesired
0x18001155c  mov     [rsp+120h+dwOptions], 0; int
0x180011564  xor     r9d, r9d; lpClass
0x180011567  xor     r8d, r8d; Reserved
0x18001156a  mov     rdx, rdi; lpSubKey
0x18001156d  mov     rcx, [rsp+120h+hKey]; hKey
0x180011572  call    cs:__imp_RegCreateKeyExW
0x180011578  test    eax, eax
0x18001157a  jz      short loc_1800115BD
0x18001157c  mov     rcx, [rbp+28h]; this
0x180011580  mov     r9d, eax; char *
0x180011583  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001158a  mov     edx, 0FDh; void *
0x18001158f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180011594  mov     ebx, eax
0x180011596  mov     rcx, [rsp+120h+var_C8]; hKey
0x18001159b  test    rcx, rcx
0x18001159e  jz      short loc_1800115A7
0x1800115a0  call    cs:__imp_RegCloseKey
0x1800115a6  nop
0x1800115a7  mov     rcx, [rsp+120h+hKey]; hKey
0x1800115ac  test    rcx, rcx
0x1800115af  jz      short loc_1800115B8
0x1800115b1  call    cs:__imp_RegCloseKey
0x1800115b7  nop
0x1800115b8  jmp     loc_180011427
0x1800115bd  mov     rcx, rsi; Str
0x1800115c0  call    ?Set@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Set(char const *,bool)
0x1800115c5  mov     rbx, rax
0x1800115c8  test    rax, rax
0x1800115cb  jnz     short loc_1800115F9
0x1800115cd  mov     rcx, [rsp+120h+var_C8]; hKey
0x1800115d2  test    rcx, rcx
0x1800115d5  jz      short loc_1800115DE
0x1800115d7  call    cs:__imp_RegCloseKey
0x1800115dd  nop
0x1800115de  mov     rcx, [rsp+120h+hKey]; hKey
0x1800115e3  test    rcx, rcx
0x1800115e6  jz      short loc_1800115EF
0x1800115e8  call    cs:__imp_RegCloseKey
0x1800115ee  nop
0x1800115ef  mov     eax, 8000FFFFh
0x1800115f4  jmp     loc_1800116FF
0x1800115f9  xor     edi, edi
0x1800115fb  cmp     edi, 7
0x1800115fe  jnb     loc_1800116C6
0x180011604  xor     edx, edx
0x180011606  lock xadd [rbx+88h], rdx; unsigned __int64
0x18001160f  lea     r8, [rsp+120h+var_B0]; char *
0x180011614  mov     rcx, rbx; this
0x180011617  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18001161c  test    al, al
0x18001161e  jz      short loc_18001169D
0x180011620  lea     rax, off_18007CE40; "E\x00n\x00r\x00o\x00l\x00l\x00m\x00e"...
0x180011627  mov     r8, [rsp+120h+var_C8]; HKEY
0x18001162c  mov     rdx, [rax+rdi*8]; unsigned __int16 *
0x180011630  lea     rcx, [rsp+120h+var_B0]; char *
0x180011635  call    ?UpdateMapWithCV@@YAJPEBDPEBGPEAUHKEY__@@@Z; UpdateMapWithCV(char const *,ushort const *,HKEY__ *)
0x18001163a  mov     esi, eax
0x18001163c  test    eax, eax
0x18001163e  js      short loc_18001165E
0x180011640  test    rbx, rbx
0x180011643  jz      short loc_18001164D
0x180011645  mov     rcx, rbx; this
0x180011648  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x18001164d  lea     rcx, [rsp+120h+var_B0]; char *
0x180011652  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x180011657  mov     rbx, rax
0x18001165a  inc     edi
0x18001165c  jmp     short loc_1800115FB
0x18001165e  mov     rcx, [rbp+28h]; this
0x180011662  mov     r9d, esi; char *
0x180011665  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001166c  mov     edx, 110h; void *
0x180011671  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011676  nop
0x180011677  mov     rcx, [rsp+120h+var_C8]; hKey
0x18001167c  test    rcx, rcx
0x18001167f  jz      short loc_180011688
0x180011681  call    cs:__imp_RegCloseKey
0x180011687  nop
0x180011688  mov     rcx, [rsp+120h+hKey]; hKey
0x18001168d  test    rcx, rcx
0x180011690  jz      short loc_180011699
0x180011692  call    cs:__imp_RegCloseKey
0x180011698  nop
0x180011699  mov     eax, esi
0x18001169b  jmp     short loc_1800116FF
0x18001169d  mov     rcx, [rsp+120h+var_C8]; hKey
0x1800116a2  test    rcx, rcx
0x1800116a5  jz      short loc_1800116AE
0x1800116a7  call    cs:__imp_RegCloseKey
0x1800116ad  nop
0x1800116ae  mov     rcx, [rsp+120h+hKey]; hKey
0x1800116b3  test    rcx, rcx
0x1800116b6  jz      short loc_1800116BF
0x1800116b8  call    cs:__imp_RegCloseKey
0x1800116be  nop
0x1800116bf  mov     eax, 80004005h
0x1800116c4  jmp     short loc_1800116FF
0x1800116c6  test    rbx, rbx
0x1800116c9  jz      short loc_1800116D4
0x1800116cb  mov     rcx, rbx; this
0x1800116ce  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x1800116d3  nop
0x1800116d4  mov     rcx, [rsp+120h+var_C8]; hKey
0x1800116d9  test    rcx, rcx
0x1800116dc  jz      short loc_1800116E5
0x1800116de  call    cs:__imp_RegCloseKey
0x1800116e4  nop
0x1800116e5  mov     rcx, [rsp+120h+hKey]; hKey
0x1800116ea  test    rcx, rcx
0x1800116ed  jz      short loc_1800116F6
0x1800116ef  call    cs:__imp_RegCloseKey
0x1800116f5  nop
0x1800116f6  xor     eax, eax
0x1800116f8  jmp     short loc_1800116FF
0x1800116fa  mov     eax, 80070057h
0x1800116ff  mov     rcx, [rbp+20h+var_20]
0x180011703  xor     rcx, rsp; StackCookie
0x180011706  call    __security_check_cookie
0x18001170b  mov     rbx, [rsp+120h+arg_10]
0x180011713  add     rsp, 110h
0x18001171a  pop     rdi
0x18001171b  pop     rsi
0x18001171c  pop     rbp
0x18001171d  retn
```
