# DlnaUrlHelpers::ParsePlaysingleUrl(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x18000d68c`
- end: `0x18000d988`
- name: `?ParsePlaysingleUrl@DlnaUrlHelpers@@YAJPEAUHSTRING__@@PEAPEAU2@1@Z`
- size: `764`
- prototype: `__int64 __fastcall(DlnaUrlHelpers *__hidden this, HSTRING, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180001c70`

## callees

- `0x18000d68c`
- `0x18000d990`
- `0x180011930`
- `0x18001bb64`
- `0x18002b820`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d71d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d71d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d82b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d861`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d88f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d82b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d861`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d88f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d7bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d7bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d8d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d8e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d8f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d8d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d8e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d8f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d703`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d703`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000d964`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000d964`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000d740`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000d740`

## string_xrefs

- `0x18000d6de`: `Windows.Foundation.Uri`
- `0x18000d858`: `urn:upnp-org:serviceId:ContentDirectory`

## pseudocode

```c
__int64 __fastcall DlnaUrlHelpers::ParsePlaysingleUrl(DlnaUrlHelpers *this, HSTRING *a2, HSTRING *a3, HSTRING *a4)
{
  HSTRING v7; // rbx
  int ActivationFactory; // edi
  char v9; // si
  const WCHAR *v10; // rbx
  HSTRING v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rcx
  UINT32 length; // [rsp+30h] [rbp-99h] BYREF
  __int64 v16; // [rsp+38h] [rbp-91h] BYREF
  __int64 v17; // [rsp+40h] [rbp-89h] BYREF
  HSTRING v18; // [rsp+48h] [rbp-81h] BYREF
  HSTRING v19; // [rsp+50h] [rbp-79h] BYREF
  HSTRING v20; // [rsp+58h] [rbp-71h] BYREF
  _DWORD v21[4]; // [rsp+60h] [rbp-69h] BYREF
  LPCWCH sourceString[2]; // [rsp+70h] [rbp-59h]
  int v23; // [rsp+80h] [rbp-49h]
  LPCWCH lpString1; // [rsp+88h] [rbp-41h]
  __int64 v25; // [rsp+90h] [rbp-39h]
  int v26; // [rsp+98h] [rbp-31h]
  PCWSTR StringRawBuffer; // [rsp+A0h] [rbp-29h]
  const WCHAR *v28; // [rsp+A8h] [rbp-21h]
  __int16 v29; // [rsp+B0h] [rbp-19h]
  int v30; // [rsp+B4h] [rbp-15h]
  HSTRING string; // [rsp+C0h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp-1h] BYREF

  *a2 = 0;
  *a3 = 0;
  v17 = 0;
  v16 = 0;
  v20 = 0;
  v19 = 0;
  v18 = 0;
  v21[2] = 0;
  v23 = 0;
  v26 = 0;
  v30 = 0;
  length = 0;
  if ( WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v7 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v17);
  ActivationFactory = RoGetActivationFactory(v7, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v17);
  if ( ActivationFactory >= 0 )
  {
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, DlnaUrlHelpers *, __int64 *))(*(_QWORD *)v17 + 48LL))(
                          v17,
                          this,
                          &v16);
    if ( ActivationFactory >= 0 )
    {
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v16 + 88LL))(v16, &v19);
      if ( ActivationFactory >= 0 )
      {
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v16 + 112LL))(v16, &v20);
        if ( ActivationFactory >= 0 )
        {
          v9 = 0;
          StringRawBuffer = WindowsGetStringRawBuffer(v20, &length);
          lpString1 = 0;
          v25 = 0;
          *(_OWORD *)sourceString = 0;
          v28 = &StringRawBuffer[length];
          v21[0] = 0;
          v29 = 0;
          while ( (int)CTokenReaderT<unsigned short,DlnaUrlHelpers::CQueryStringSeparator>::ReadNextToken(v21) >= 0 )
          {
            v10 = lpString1;
            if ( (unsigned int)((v25 - (__int64)lpString1) >> 1) == 3 )
            {
              if ( CompareStringOrdinal(lpString1, 3, L"sid", 3, 1) == 2 )
              {
                if ( (unsigned int)(sourceString[1] - sourceString[0]) != 39
                  || CompareStringOrdinal(sourceString[0], 39, L"urn:upnp-org:serviceId:ContentDirectory", 39, 1) != 2 )
                {
                  v11 = v18;
LABEL_18:
                  ActivationFactory = -2147024809;
                  goto LABEL_19;
                }
                v9 = 1;
              }
              else if ( CompareStringOrdinal(v10, 3, L"iid", 3, 1) == 2 )
              {
                ActivationFactory = Windows::Internal::String::Initialize(
                                      &v18,
                                      sourceString[0],
                                      sourceString[1] - sourceString[0]);
                if ( ActivationFactory < 0 )
                {
                  v11 = v18;
                  goto LABEL_19;
                }
              }
            }
          }
          v11 = v18;
          if ( !v9 || WindowsIsStringEmpty(v18) )
            goto LABEL_18;
          *a2 = v19;
          *a3 = v11;
          v11 = 0;
          v19 = 0;
LABEL_19:
          if ( v11 )
            WindowsDeleteString(v11);
        }
      }
    }
  }
  if ( v19 )
    WindowsDeleteString(v19);
  if ( v20 )
    WindowsDeleteString(v20);
  v12 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18000d68c  push    rbp
0x18000d68e  push    rbx
0x18000d68f  push    rsi
0x18000d690  push    rdi
0x18000d691  push    r12
0x18000d693  push    r14
0x18000d695  push    r15
0x18000d697  lea     rbp, [rsp-27h]
0x18000d69c  sub     rsp, 0F0h
0x18000d6a3  mov     rax, cs:__security_cookie
0x18000d6aa  xor     rax, rsp
0x18000d6ad  mov     [rbp+57h+var_40], rax
0x18000d6b1  xor     r12d, r12d
0x18000d6b4  lea     r9, [rbp+57h+string]; string
0x18000d6b8  mov     [rdx], r12
0x18000d6bb  mov     r15, r8
0x18000d6be  mov     r14, rdx
0x18000d6c1  mov     [r8], r12
0x18000d6c4  mov     rsi, rcx
0x18000d6c7  mov     [rsp+120h+var_E0], r12
0x18000d6cc  lea     edx, [r12+16h]; length
0x18000d6d1  mov     [rsp+120h+var_E8], r12
0x18000d6d6  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000d6da  mov     [rbp+57h+var_C8], r12
0x18000d6de  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18000d6e5  mov     [rbp+57h+var_D0], r12
0x18000d6e9  mov     [rsp+120h+var_D8], r12
0x18000d6ee  mov     [rbp+57h+var_B8], r12d
0x18000d6f2  mov     [rbp+57h+var_A0], r12d
0x18000d6f6  mov     [rbp+57h+var_88], r12d
0x18000d6fa  mov     [rbp+57h+var_6C], r12d
0x18000d6fe  mov     [rsp+120h+length], r12d
0x18000d703  call    cs:__imp_WindowsCreateStringReference
0x18000d709  test    eax, eax
0x18000d70b  jns     short loc_18000D723
0x18000d70d  xor     r9d, r9d; lpArguments
0x18000d710  lea     edx, [r12+1]; dwExceptionFlags
0x18000d715  xor     r8d, r8d; nNumberOfArguments
0x18000d718  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000d71d  call    cs:__imp_RaiseException
0x18000d723  mov     rbx, [rbp+57h+string]
0x18000d727  lea     rcx, [rsp+120h+var_E0]
0x18000d72c  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18000d731  lea     r8, [rsp+120h+var_E0]
0x18000d736  mov     rcx, rbx
0x18000d739  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x18000d740  call    cs:__imp_RoGetActivationFactory
0x18000d746  mov     edi, eax
0x18000d748  test    eax, eax
0x18000d74a  js      loc_18000D8DF
0x18000d750  mov     rcx, [rsp+120h+var_E0]
0x18000d755  lea     r8, [rsp+120h+var_E8]
0x18000d75a  mov     rdx, rsi
0x18000d75d  mov     rax, [rcx]
0x18000d760  mov     rax, [rax+30h]
0x18000d764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d769  mov     edi, eax
0x18000d76b  test    eax, eax
0x18000d76d  js      loc_18000D8DF
0x18000d773  mov     rcx, [rsp+120h+var_E8]
0x18000d778  lea     rdx, [rbp+57h+var_D0]
0x18000d77c  mov     rax, [rcx]
0x18000d77f  mov     rax, [rax+58h]
0x18000d783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d788  mov     edi, eax
0x18000d78a  test    eax, eax
0x18000d78c  js      loc_18000D8DF
0x18000d792  mov     rcx, [rsp+120h+var_E8]
0x18000d797  lea     rdx, [rbp+57h+var_C8]
0x18000d79b  mov     rax, [rcx]
0x18000d79e  mov     rax, [rax+70h]
0x18000d7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7a7  mov     edi, eax
0x18000d7a9  test    eax, eax
0x18000d7ab  js      loc_18000D8DF
0x18000d7b1  mov     rcx, [rbp+57h+var_C8]; string
0x18000d7b5  lea     rdx, [rsp+120h+length]; length
0x18000d7ba  mov     sil, r12b
0x18000d7bd  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d7c3  mov     ecx, [rsp+120h+length]
0x18000d7c7  xorps   xmm0, xmm0
0x18000d7ca  mov     [rbp+57h+var_80], rax
0x18000d7ce  mov     [rbp+57h+lpString1], r12
0x18000d7d2  mov     [rbp+57h+var_90], r12
0x18000d7d6  lea     rax, [rax+rcx*2]
0x18000d7da  movdqa  xmmword ptr [rbp+57h+sourceString], xmm0
0x18000d7df  mov     [rbp+57h+var_78], rax
0x18000d7e3  mov     [rbp+57h+var_C0], r12d
0x18000d7e7  mov     [rbp+57h+var_70], r12w
0x18000d7ec  lea     rcx, [rbp+57h+var_C0]
0x18000d7f0  call    ?ReadNextToken@?$CTokenReaderT@GVCQueryStringSeparator@DlnaUrlHelpers@@@@QEAAJXZ; CTokenReaderT<ushort,DlnaUrlHelpers::CQueryStringSeparator>::ReadNextToken(void)
0x18000d7f5  test    eax, eax
0x18000d7f7  js      loc_18000D953
0x18000d7fd  mov     rbx, [rbp+57h+lpString1]
0x18000d801  mov     ecx, 3
0x18000d806  mov     rax, [rbp+57h+var_90]
0x18000d80a  sub     rax, rbx
0x18000d80d  sar     rax, 1
0x18000d810  cmp     eax, ecx
0x18000d812  jnz     short loc_18000D7EC
0x18000d814  mov     r9d, ecx; cchCount2
0x18000d817  mov     [rsp+120h+bIgnoreCase], 1; bIgnoreCase
0x18000d81f  mov     edx, ecx; cchCount1
0x18000d821  lea     r8, aSid; "sid"
0x18000d828  mov     rcx, rbx; lpString1
0x18000d82b  call    cs:__imp_CompareStringOrdinal
0x18000d831  cmp     eax, 2
0x18000d834  jnz     short loc_18000D874
0x18000d836  mov     rcx, [rbp+57h+sourceString]; lpString1
0x18000d83a  mov     ebx, 27h ; '''
0x18000d83f  mov     rax, [rbp+57h+sourceString+8]
0x18000d843  sub     rax, rcx
0x18000d846  sar     rax, 1
0x18000d849  cmp     eax, ebx
0x18000d84b  jnz     short loc_18000D8C7
0x18000d84d  mov     r9d, ebx; cchCount2
0x18000d850  mov     [rsp+120h+bIgnoreCase], 1; bIgnoreCase
0x18000d858  lea     r8, aUrnUpnpOrgServ; "urn:upnp-org:serviceId:ContentDirectory"
0x18000d85f  mov     edx, ebx; cchCount1
0x18000d861  call    cs:__imp_CompareStringOrdinal
0x18000d867  cmp     eax, 2
0x18000d86a  jnz     short loc_18000D8C7
0x18000d86c  mov     sil, 1
0x18000d86f  jmp     loc_18000D7EC
0x18000d874  mov     r9d, 3; cchCount2
0x18000d87a  mov     [rsp+120h+bIgnoreCase], 1; bIgnoreCase
0x18000d882  mov     edx, r9d; cchCount1
0x18000d885  lea     r8, aIid; "iid"
0x18000d88c  mov     rcx, rbx; lpString1
0x18000d88f  call    cs:__imp_CompareStringOrdinal
0x18000d895  cmp     eax, 2
0x18000d898  jnz     loc_18000D7EC
0x18000d89e  mov     rdx, [rbp+57h+sourceString]; sourceString
0x18000d8a2  lea     rcx, [rsp+120h+var_D8]; this
0x18000d8a7  mov     r8, [rbp+57h+sourceString+8]
0x18000d8ab  sub     r8, rdx
0x18000d8ae  sar     r8, 1; length
0x18000d8b1  call    ?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z; Windows::Internal::String::Initialize(ushort const *,uint)
0x18000d8b6  mov     edi, eax
0x18000d8b8  test    eax, eax
0x18000d8ba  jns     loc_18000D7EC
0x18000d8c0  mov     rbx, [rsp+120h+var_D8]
0x18000d8c5  jmp     short loc_18000D8D1
0x18000d8c7  mov     rbx, [rsp+120h+var_D8]
0x18000d8cc  mov     edi, 80070057h
0x18000d8d1  test    rbx, rbx
0x18000d8d4  jz      short loc_18000D8DF
0x18000d8d6  mov     rcx, rbx; string
0x18000d8d9  call    cs:__imp_WindowsDeleteString
0x18000d8df  mov     rcx, [rbp+57h+var_D0]; string
0x18000d8e3  test    rcx, rcx
0x18000d8e6  jz      short loc_18000D8EE
0x18000d8e8  call    cs:__imp_WindowsDeleteString
0x18000d8ee  mov     rcx, [rbp+57h+var_C8]; string
0x18000d8f2  test    rcx, rcx
0x18000d8f5  jz      short loc_18000D8FD
0x18000d8f7  call    cs:__imp_WindowsDeleteString
0x18000d8fd  mov     rcx, [rsp+120h+var_E8]
0x18000d902  test    rcx, rcx
0x18000d905  jz      short loc_18000D918
0x18000d907  mov     [rsp+120h+var_E8], r12
0x18000d90c  mov     rax, [rcx]
0x18000d90f  mov     rax, [rax+10h]
0x18000d913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d918  mov     rcx, [rsp+120h+var_E0]
0x18000d91d  test    rcx, rcx
0x18000d920  jz      short loc_18000D933
0x18000d922  mov     [rsp+120h+var_E0], r12
0x18000d927  mov     rax, [rcx]
0x18000d92a  mov     rax, [rax+10h]
0x18000d92e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d933  mov     eax, edi
0x18000d935  mov     rcx, [rbp+57h+var_40]
0x18000d939  xor     rcx, rsp; StackCookie
0x18000d93c  call    __security_check_cookie
0x18000d941  add     rsp, 0F0h
0x18000d948  pop     r15
0x18000d94a  pop     r14
0x18000d94c  pop     r12
0x18000d94e  pop     rdi
0x18000d94f  pop     rsi
0x18000d950  pop     rbx
0x18000d951  pop     rbp
0x18000d952  retn
0x18000d953  mov     rbx, [rsp+120h+var_D8]
0x18000d958  test    sil, sil
0x18000d95b  jz      loc_18000D8CC
0x18000d961  mov     rcx, rbx; string
0x18000d964  call    cs:__imp_WindowsIsStringEmpty
0x18000d96a  test    eax, eax
0x18000d96c  jnz     loc_18000D8CC
0x18000d972  mov     rax, [rbp+57h+var_D0]
0x18000d976  mov     [r14], rax
0x18000d979  mov     [r15], rbx
0x18000d97c  mov     rbx, r12
0x18000d97f  mov     [rbp+57h+var_D0], r12
0x18000d983  jmp     loc_18000D8D1
```
