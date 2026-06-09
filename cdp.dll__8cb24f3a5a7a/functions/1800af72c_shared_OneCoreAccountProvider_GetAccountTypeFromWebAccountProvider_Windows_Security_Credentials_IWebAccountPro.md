# shared::OneCoreAccountProvider::GetAccountTypeFromWebAccountProvider(Windows::Security::Credentials::IWebAccountProvider *)

- ea: `0x1800af72c`
- end: `0x1800af9b5`
- name: `?GetAccountTypeFromWebAccountProvider@OneCoreAccountProvider@shared@@AEAA?AW4CDPAccountType@@PEAUIWebAccountProvider@Credentials@Security@Windows@@@Z`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800af2a4`

## callees

- `0x18001ce80`
- `0x1800624cc`
- `0x1800af72c`
- `0x18011d8c4`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800af808`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800af863`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800af808`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800af863`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800af793`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800af877`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800af8bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800af998`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800af793`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800af877`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800af8bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800af998`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800af7ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800af821`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800af7ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800af821`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall shared::OneCoreAccountProvider::GetAccountTypeFromWebAccountProvider(
        _QWORD *a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *))
{
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rbx
  int v5; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  PCWSTR StringRawBuffer; // rax
  int v10; // r9d
  const WCHAR *v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rbx
  const WCHAR *v14; // rcx
  PCWSTR v15; // rax
  int v16; // r9d
  const WCHAR *v17; // r8
  const WCHAR *v18; // rcx
  __int64 v19; // rcx
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  const char *v26; // [rsp+30h] [rbp-50h] BYREF
  int v27; // [rsp+38h] [rbp-48h]
  _BYTE v28[64]; // [rsp+40h] [rbp-40h] BYREF
  HSTRING string; // [rsp+B8h] [rbp+38h] BYREF
  __int64 v30; // [rsp+C0h] [rbp+40h] BYREF

  v30 = 0;
  v4 = **a2;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
  v5 = v4(a2, &GUID_4a01eb05_4e42_41d4_b518_e008a5163614, &v30);
  if ( v5 < 0 )
  {
    v26 = ".\\onecoreaccountprovider.cpp";
    v27 = 1200;
    v22 = cdp::MakeException<cdp::hresult_exception>(v28, &v26, (unsigned int)v5);
    cdp::CdpThrow<cdp::hresult_exception>(&v26, v22);
  }
  string = 0;
  v6 = v30;
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v8 = v7(v6, &string);
  if ( v8 < 0 )
  {
    v26 = ".\\onecoreaccountprovider.cpp";
    v27 = 1203;
    v23 = cdp::MakeException<cdp::hresult_exception>(v28, &v26, (unsigned int)v8);
    cdp::CdpThrow<cdp::hresult_exception>(&v26, v23);
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v10 = -(StringRawBuffer != 0);
  v11 = &pNodeName;
  if ( StringRawBuffer )
    v11 = StringRawBuffer;
  v12 = a1[31];
  v13 = -1;
  if ( v12 != -1 )
  {
    v14 = (const WCHAR *)a1[30];
    if ( v14 )
      goto LABEL_8;
    goto LABEL_7;
  }
  v24 = a1[30];
  if ( !v24 )
  {
    LODWORD(v12) = 0;
LABEL_7:
    v14 = &pNodeName;
    goto LABEL_8;
  }
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(v24 + 2 * v12) );
  v14 = (const WCHAR *)a1[30];
LABEL_8:
  if ( CompareStringOrdinal(v14, v12, v11, v10, 1) != 2 )
  {
    v15 = WindowsGetStringRawBuffer(string, 0);
    v16 = -(v15 != 0);
    v17 = &pNodeName;
    if ( v15 )
      v17 = v15;
    if ( a1[34] == -1 )
    {
      v25 = a1[33];
      if ( v25 )
      {
        do
          ++v13;
        while ( *(_WORD *)(v25 + 2 * v13) );
        v18 = (const WCHAR *)a1[33];
        goto LABEL_14;
      }
      LODWORD(v13) = 0;
    }
    else
    {
      v18 = (const WCHAR *)a1[33];
      v13 = a1[34];
      if ( v18 )
        goto LABEL_14;
    }
    v18 = &pNodeName;
LABEL_14:
    if ( CompareStringOrdinal(v18, v13, v17, v16, 1) == 2 )
    {
      WindowsDeleteString(string);
      string = 0;
      v19 = v30;
      if ( v30 )
      {
        v30 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      return 2;
    }
    else
    {
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
      return 3;
    }
  }
  WindowsDeleteString(string);
  string = 0;
  v21 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return 1;
}

```

## disassembly

```asm
0x1800af72c  mov     [rsp-28h+arg_0], rbx
0x1800af731  mov     [rsp-28h+arg_18], rsi
0x1800af736  push    rbp
0x1800af737  push    rdi
0x1800af738  push    r12
0x1800af73a  push    r14
0x1800af73c  push    r15
0x1800af73e  mov     rbp, rsp
0x1800af741  sub     rsp, 80h
0x1800af748  mov     rdi, rdx
0x1800af74b  mov     rsi, rcx
0x1800af74e  xor     r14d, r14d
0x1800af751  mov     [rbp+arg_10], r14
0x1800af755  mov     rax, [rdx]
0x1800af758  mov     rbx, [rax]
0x1800af75b  lea     rcx, [rbp+arg_10]
0x1800af75f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800af764  lea     r8, [rbp+arg_10]
0x1800af768  lea     rdx, _GUID_4a01eb05_4e42_41d4_b518_e008a5163614
0x1800af76f  mov     rcx, rdi
0x1800af772  mov     rax, rbx
0x1800af775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af77a  test    eax, eax
0x1800af77c  js      loc_1800AF8E9
0x1800af782  mov     [rbp+string], r14
0x1800af786  mov     rdi, [rbp+arg_10]
0x1800af78a  mov     rax, [rdi]
0x1800af78d  mov     rbx, [rax+38h]
0x1800af791  xor     ecx, ecx; string
0x1800af793  call    cs:__imp_WindowsDeleteString
0x1800af799  mov     [rbp+string], r14
0x1800af79d  lea     rdx, [rbp+string]
0x1800af7a1  mov     rcx, rdi
0x1800af7a4  mov     rax, rbx
0x1800af7a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af7ac  test    eax, eax
0x1800af7ae  js      loc_1800AF919
0x1800af7b4  xor     edx, edx; length
0x1800af7b6  mov     rcx, [rbp+string]; string
0x1800af7ba  call    cs:__imp_WindowsGetStringRawBuffer
0x1800af7c0  mov     rcx, rax
0x1800af7c3  neg     rcx
0x1800af7c6  sbb     r9d, r9d; cchCount2
0x1800af7c9  lea     rdi, pNodeName
0x1800af7d0  mov     r8, rdi
0x1800af7d3  test    rax, rax
0x1800af7d6  cmovnz  r8, rax; lpString2
0x1800af7da  mov     rdx, [rsi+0F8h]; cchCount1
0x1800af7e1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800af7e5  cmp     rdx, rbx
0x1800af7e8  jz      loc_1800AF949
0x1800af7ee  mov     rcx, [rsi+0F0h]
0x1800af7f5  test    rcx, rcx
0x1800af7f8  jnz     short loc_1800AF7FD
0x1800af7fa  mov     rcx, rdi; lpString1
0x1800af7fd  mov     r15d, 1
0x1800af803  mov     [rsp+80h+bIgnoreCase], r15d; bIgnoreCase
0x1800af808  call    cs:__imp_CompareStringOrdinal
0x1800af80e  lea     r12d, [r15+1]
0x1800af812  cmp     eax, r12d
0x1800af815  jz      loc_1800AF8BB
0x1800af81b  xor     edx, edx; length
0x1800af81d  mov     rcx, [rbp+string]; string
0x1800af821  call    cs:__imp_WindowsGetStringRawBuffer
0x1800af827  mov     rcx, rax
0x1800af82a  neg     rcx
0x1800af82d  sbb     r9d, r9d; cchCount2
0x1800af830  mov     r8, rdi
0x1800af833  test    rax, rax
0x1800af836  cmovnz  r8, rax; lpString2
0x1800af83a  mov     rax, [rsi+110h]
0x1800af841  cmp     rax, rbx
0x1800af844  jz      loc_1800AF972
0x1800af84a  mov     rcx, [rsi+108h]
0x1800af851  mov     rbx, rax
0x1800af854  test    rcx, rcx
0x1800af857  jnz     short loc_1800AF85C
0x1800af859  mov     rcx, rdi; lpString1
0x1800af85c  mov     edx, ebx; cchCount1
0x1800af85e  mov     [rsp+80h+bIgnoreCase], r15d; bIgnoreCase
0x1800af863  call    cs:__imp_CompareStringOrdinal
0x1800af869  nop
0x1800af86a  mov     rcx, [rbp+string]; string
0x1800af86e  cmp     eax, r12d
0x1800af871  jnz     loc_1800AF998
0x1800af877  call    cs:__imp_WindowsDeleteString
0x1800af87d  mov     [rbp+string], r14
0x1800af881  mov     rcx, [rbp+arg_10]
0x1800af885  test    rcx, rcx
0x1800af888  jz      short loc_1800AF89B
0x1800af88a  mov     [rbp+arg_10], r14
0x1800af88e  mov     rdx, [rcx]
0x1800af891  mov     rax, [rdx+10h]
0x1800af895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af89a  nop
0x1800af89b  movzx   eax, r12w
0x1800af89f  lea     r11, [rsp+80h+var_s0]
0x1800af8a7  mov     rbx, [r11+30h]
0x1800af8ab  mov     rsi, [r11+48h]
0x1800af8af  mov     rsp, r11
0x1800af8b2  pop     r15
0x1800af8b4  pop     r14
0x1800af8b6  pop     r12
0x1800af8b8  pop     rdi
0x1800af8b9  pop     rbp
0x1800af8ba  retn
0x1800af8bb  mov     rcx, [rbp+string]; string
0x1800af8bf  call    cs:__imp_WindowsDeleteString
0x1800af8c5  mov     [rbp+string], r14
0x1800af8c9  mov     rcx, [rbp+arg_10]
0x1800af8cd  test    rcx, rcx
0x1800af8d0  jz      short loc_1800AF8E3
0x1800af8d2  mov     [rbp+arg_10], r14
0x1800af8d6  mov     rdx, [rcx]
0x1800af8d9  mov     rax, [rdx+10h]
0x1800af8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af8e2  nop
0x1800af8e3  movzx   eax, r15w
0x1800af8e7  jmp     short loc_1800AF89F
0x1800af8e9  lea     rcx, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x1800af8f0  mov     [rbp+var_50], rcx
0x1800af8f4  mov     [rbp+var_48], 4B0h
0x1800af8fb  mov     r8d, eax
0x1800af8fe  lea     rdx, [rbp+var_50]
0x1800af902  lea     rcx, [rbp+var_40]
0x1800af906  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800af90b  nop
0x1800af90c  mov     rdx, rax
0x1800af90f  lea     rcx, [rbp+var_50]
0x1800af913  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800af919  lea     rcx, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x1800af920  mov     [rbp+var_50], rcx
0x1800af924  mov     [rbp+var_48], 4B3h
0x1800af92b  mov     r8d, eax
0x1800af92e  lea     rdx, [rbp+var_50]
0x1800af932  lea     rcx, [rbp+var_40]
0x1800af936  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800af93b  nop
0x1800af93c  mov     rdx, rax
0x1800af93f  lea     rcx, [rbp+var_50]
0x1800af943  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800af949  mov     rax, [rsi+0F0h]
0x1800af950  test    rax, rax
0x1800af953  jz      short loc_1800AF96A
0x1800af955  mov     rdx, rbx
0x1800af958  inc     rdx
0x1800af95b  cmp     [rax+rdx*2], r14w
0x1800af960  jnz     short loc_1800AF958
0x1800af962  mov     rcx, rax
0x1800af965  jmp     loc_1800AF7FD
0x1800af96a  mov     rdx, r14
0x1800af96d  jmp     loc_1800AF7FA
0x1800af972  mov     rax, [rsi+108h]
0x1800af979  test    rax, rax
0x1800af97c  jnz     short loc_1800AF986
0x1800af97e  mov     rbx, r14
0x1800af981  jmp     loc_1800AF859
0x1800af986  inc     rbx
0x1800af989  cmp     [rax+rbx*2], r14w
0x1800af98e  jnz     short loc_1800AF986
0x1800af990  mov     rcx, rax
0x1800af993  jmp     loc_1800AF85C
0x1800af998  call    cs:__imp_WindowsDeleteString
0x1800af99e  mov     [rbp+string], r14
0x1800af9a2  lea     rcx, [rbp+arg_10]
0x1800af9a6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800af9ab  mov     eax, 3
0x1800af9b0  jmp     loc_1800AF89F
```
