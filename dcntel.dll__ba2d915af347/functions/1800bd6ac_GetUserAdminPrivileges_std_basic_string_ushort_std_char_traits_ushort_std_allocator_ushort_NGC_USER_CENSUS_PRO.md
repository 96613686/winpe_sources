# GetUserAdminPrivileges(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_NGC_USER_CENSUS_PROP_ADMINPRIVILEGE *)

- ea: `0x1800bd6ac`
- end: `0x1800bd8ed`
- name: `?GetUserAdminPrivileges@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAW4_NGC_USER_CENSUS_PROP_ADMINPRIVILEGE@@@Z`
- size: `577`
- prototype: `__int64 __fastcall(LPCWSTR StringSid)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800bbdd0`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x180011cc4`
- `0x180016748`
- `0x1800a5e64`
- `0x1800bd6ac`
- `0x1801835b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bd829`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bd829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd816`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd816`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd778`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd801`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd8b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd778`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd801`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd8b4`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800bd7b9`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800bd7b9`
- `netutils!NetApiBufferFree` at `0x1800bd7e7`
- `netutils!NetApiBufferFree` at `0x1800bd821`
- `netutils!NetApiBufferFree` at `0x1800bd89e`
- `netutils!NetApiBufferFree` at `0x1800bd7e7`
- `netutils!NetApiBufferFree` at `0x1800bd821`
- `netutils!NetApiBufferFree` at `0x1800bd89e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800bd751`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800bd751`
- `samcli!NetUserGetInfo` at `0x1800bd845`
- `samcli!NetUserGetInfo` at `0x1800bd845`

## string_xrefs

- `0x1800bd7c8`: `onecore\base\appcompat\programs\devicecensus\dlls\ngchelper.cpp`
- `0x1800bd859`: `onecore\base\appcompat\programs\devicecensus\dlls\ngchelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetUserAdminPrivileges(_QWORD *StringSid, _DWORD *a2)
{
  const WCHAR *v4; // rcx
  BOOL v5; // ebx
  const char *v6; // r9
  PSID v7; // r8
  __int64 v8; // rdx
  int LastError; // eax
  unsigned int v10; // ebx
  PSID v11; // rcx
  void *v12; // rsi
  DWORD v13; // ebx
  DWORD Info; // eax
  void *v15; // rcx
  int v16; // eax
  PSID v17; // rcx
  unsigned int ReferencedDomainName; // [rsp+20h] [rbp-E0h]
  PSID hMem; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID Buffer; // [rsp+48h] [rbp-B8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  PSID *p_hMem; // [rsp+60h] [rbp-A0h]
  PSID Sid; // [rsp+68h] [rbp-98h] BYREF
  char v27; // [rsp+70h] [rbp-90h]
  _QWORD *v28; // [rsp+78h] [rbp-88h]
  WCHAR Name[256]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR v30[256]; // [rsp+280h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  v28 = StringSid;
  *a2 = 0;
  memset_0(Name, 0, sizeof(Name));
  cchName = 256;
  memset_0(v30, 0, sizeof(v30));
  cchReferencedDomainName = 256;
  peUse = 0;
  hMem = 0;
  Buffer = 0;
  p_hMem = &hMem;
  Sid = 0;
  v27 = 1;
  if ( StringSid[3] <= 7u )
    v4 = (const WCHAR *)StringSid;
  else
    v4 = (const WCHAR *)*StringSid;
  v5 = ConvertStringSidToSidW(v4, &Sid);
  if ( v27 )
  {
    v7 = *p_hMem;
    *p_hMem = Sid;
    if ( v7 )
      LocalFree(v7);
  }
  if ( !v5 )
  {
    v8 = 659;
LABEL_11:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v8,
                  (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\ngchelper.cpp",
                  v6);
LABEL_12:
    v10 = LastError;
    if ( Buffer )
      NetApiBufferFree(Buffer);
    v11 = hMem;
    hMem = 0;
    if ( v11 )
      LocalFree(v11);
    goto LABEL_29;
  }
  if ( !LookupAccountSidW(0, hMem, Name, &cchName, v30, &cchReferencedDomainName, &peUse) )
  {
    v8 = 668;
    goto LABEL_11;
  }
  v12 = Buffer;
  if ( Buffer )
  {
    v13 = GetLastError();
    NetApiBufferFree(v12);
    SetLastError(v13);
  }
  Buffer = 0;
  Info = NetUserGetInfo(0, Name, 4u, (LPBYTE *)&Buffer);
  if ( Info )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x2A2,
                  (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\ngchelper.cpp",
                  (const char *)Info,
                  ReferencedDomainName);
    goto LABEL_12;
  }
  v15 = Buffer;
  if ( *((_DWORD *)Buffer + 5) == 2 )
  {
    *a2 = 2;
    v16 = LUAIsShadowAdminEnabled();
    v15 = Buffer;
    if ( v16 )
      *a2 = 1;
  }
  else
  {
    *a2 = 0;
  }
  if ( v15 )
    NetApiBufferFree(v15);
  v17 = hMem;
  hMem = 0;
  if ( v17 )
    LocalFree(v17);
  v10 = 0;
LABEL_29:
  std::wstring::~wstring((char **)StringSid);
  return v10;
}

```

## disassembly

```asm
0x1800bd6ac  mov     [rsp-8+arg_10], rbx
0x1800bd6b1  push    rbp
0x1800bd6b2  push    rsi
0x1800bd6b3  push    rdi
0x1800bd6b4  push    r14
0x1800bd6b6  push    r15
0x1800bd6b8  lea     rbp, [rsp-390h]
0x1800bd6c0  sub     rsp, 490h
0x1800bd6c7  mov     rax, cs:__security_cookie
0x1800bd6ce  xor     rax, rsp
0x1800bd6d1  mov     [rbp+3B0h+var_30], rax
0x1800bd6d8  mov     rdi, rdx
0x1800bd6db  mov     r14, rcx
0x1800bd6de  mov     [rsp+4B0h+var_438], rcx
0x1800bd6e3  xor     r15d, r15d
0x1800bd6e6  mov     [rdx], r15d
0x1800bd6e9  mov     esi, 200h
0x1800bd6ee  mov     r8d, esi; Size
0x1800bd6f1  xor     edx, edx; Val
0x1800bd6f3  lea     rcx, [rbp+3B0h+Name]; void *
0x1800bd6f7  call    memset_0
0x1800bd6fc  mov     ebx, 100h
0x1800bd701  mov     [rsp+4B0h+cchName], ebx
0x1800bd705  mov     r8d, esi; Size
0x1800bd708  xor     edx, edx; Val
0x1800bd70a  lea     rcx, [rbp+3B0h+var_230]; void *
0x1800bd711  call    memset_0
0x1800bd716  mov     [rsp+4B0h+var_45C], ebx
0x1800bd71a  mov     [rsp+4B0h+var_460], r15d
0x1800bd71f  mov     [rsp+4B0h+hMem], r15
0x1800bd724  mov     [rsp+4B0h+Buffer], r15
0x1800bd729  lea     rax, [rsp+4B0h+hMem]
0x1800bd72e  mov     [rsp+4B0h+var_450], rax
0x1800bd733  mov     [rsp+4B0h+Sid], r15
0x1800bd738  mov     [rsp+4B0h+var_440], 1
0x1800bd73d  cmp     qword ptr [r14+18h], 7
0x1800bd742  jbe     short loc_1800BD749
0x1800bd744  mov     rcx, [r14]
0x1800bd747  jmp     short loc_1800BD74C
0x1800bd749  mov     rcx, r14; StringSid
0x1800bd74c  lea     rdx, [rsp+4B0h+Sid]; Sid
0x1800bd751  call    cs:__imp_ConvertStringSidToSidW
0x1800bd757  mov     ebx, eax
0x1800bd759  cmp     [rsp+4B0h+var_440], r15b
0x1800bd75e  jz      short loc_1800BD77E
0x1800bd760  mov     rdx, [rsp+4B0h+var_450]
0x1800bd765  mov     r8, [rdx]
0x1800bd768  mov     rcx, [rsp+4B0h+Sid]
0x1800bd76d  mov     [rdx], rcx
0x1800bd770  test    r8, r8
0x1800bd773  jz      short loc_1800BD77E
0x1800bd775  mov     rcx, r8; hMem
0x1800bd778  call    cs:__imp_LocalFree
0x1800bd77e  test    ebx, ebx
0x1800bd780  jnz     short loc_1800BD789
0x1800bd782  mov     edx, 293h
0x1800bd787  jmp     short loc_1800BD7C8
0x1800bd789  lea     rax, [rsp+4B0h+var_460]
0x1800bd78e  mov     [rsp+4B0h+peUse], rax; peUse
0x1800bd793  lea     rax, [rsp+4B0h+var_45C]
0x1800bd798  mov     [rsp+4B0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800bd79d  lea     rax, [rbp+3B0h+var_230]
0x1800bd7a4  mov     [rsp+4B0h+ReferencedDomainName], rax; unsigned int
0x1800bd7a9  lea     r9, [rsp+4B0h+cchName]; cchName
0x1800bd7ae  lea     r8, [rbp+3B0h+Name]; Name
0x1800bd7b2  mov     rdx, [rsp+4B0h+hMem]; Sid
0x1800bd7b7  xor     ecx, ecx; lpSystemName
0x1800bd7b9  call    cs:__imp_LookupAccountSidW
0x1800bd7bf  test    eax, eax
0x1800bd7c1  jnz     short loc_1800BD80C
0x1800bd7c3  mov     edx, 29Ch; void *
0x1800bd7c8  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appcompat\\programs\\dev"...
0x1800bd7cf  mov     rcx, [rbp+3B8h]; this
0x1800bd7d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800bd7db  mov     ebx, eax
0x1800bd7dd  mov     rcx, [rsp+4B0h+Buffer]; Buffer
0x1800bd7e2  test    rcx, rcx
0x1800bd7e5  jz      short loc_1800BD7EE
0x1800bd7e7  call    cs:__imp_NetApiBufferFree
0x1800bd7ed  nop
0x1800bd7ee  mov     rcx, [rsp+4B0h+hMem]; hMem
0x1800bd7f3  mov     [rsp+4B0h+hMem], r15
0x1800bd7f8  test    rcx, rcx
0x1800bd7fb  jz      loc_1800BD8BD
0x1800bd801  call    cs:__imp_LocalFree
0x1800bd807  jmp     loc_1800BD8BD
0x1800bd80c  mov     rsi, [rsp+4B0h+Buffer]
0x1800bd811  test    rsi, rsi
0x1800bd814  jz      short loc_1800BD82F
0x1800bd816  call    cs:__imp_GetLastError
0x1800bd81c  mov     ebx, eax
0x1800bd81e  mov     rcx, rsi; Buffer
0x1800bd821  call    cs:__imp_NetApiBufferFree
0x1800bd827  mov     ecx, ebx; dwErrCode
0x1800bd829  call    cs:__imp_SetLastError
0x1800bd82f  mov     [rsp+4B0h+Buffer], r15
0x1800bd834  lea     r9, [rsp+4B0h+Buffer]; bufptr
0x1800bd839  mov     r8d, 4; level
0x1800bd83f  lea     rdx, [rbp+3B0h+Name]; username
0x1800bd843  xor     ecx, ecx; servername
0x1800bd845  call    cs:__imp_NetUserGetInfo
0x1800bd84b  test    eax, eax
0x1800bd84d  jz      short loc_1800BD86F
0x1800bd84f  mov     rcx, [rbp+3B8h]; this
0x1800bd856  mov     r9d, eax; char *
0x1800bd859  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appcompat\\programs\\dev"...
0x1800bd860  mov     edx, 2A2h; void *
0x1800bd865  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800bd86a  jmp     loc_1800BD7DB
0x1800bd86f  mov     rcx, [rsp+4B0h+Buffer]; Buffer
0x1800bd874  cmp     dword ptr [rcx+14h], 2
0x1800bd878  jnz     short loc_1800BD896
0x1800bd87a  mov     dword ptr [rdi], 2
0x1800bd880  call    LUAIsShadowAdminEnabled
0x1800bd885  mov     rcx, [rsp+4B0h+Buffer]
0x1800bd88a  test    eax, eax
0x1800bd88c  jz      short loc_1800BD899
0x1800bd88e  mov     dword ptr [rdi], 1
0x1800bd894  jmp     short loc_1800BD899
0x1800bd896  mov     [rdi], r15d
0x1800bd899  test    rcx, rcx
0x1800bd89c  jz      short loc_1800BD8A5
0x1800bd89e  call    cs:__imp_NetApiBufferFree
0x1800bd8a4  nop
0x1800bd8a5  mov     rcx, [rsp+4B0h+hMem]; hMem
0x1800bd8aa  mov     [rsp+4B0h+hMem], r15
0x1800bd8af  test    rcx, rcx
0x1800bd8b2  jz      short loc_1800BD8BA
0x1800bd8b4  call    cs:__imp_LocalFree
0x1800bd8ba  mov     ebx, r15d
0x1800bd8bd  mov     rcx, r14
0x1800bd8c0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800bd8c5  mov     eax, ebx
0x1800bd8c7  mov     rcx, [rbp+3B0h+var_30]
0x1800bd8ce  xor     rcx, rsp; StackCookie
0x1800bd8d1  call    __security_check_cookie
0x1800bd8d6  mov     rbx, [rsp+4B0h+arg_10]
0x1800bd8de  add     rsp, 490h
0x1800bd8e5  pop     r15
0x1800bd8e7  pop     r14
0x1800bd8e9  pop     rdi
0x1800bd8ea  pop     rsi
0x1800bd8eb  pop     rbp
0x1800bd8ec  retn
```
