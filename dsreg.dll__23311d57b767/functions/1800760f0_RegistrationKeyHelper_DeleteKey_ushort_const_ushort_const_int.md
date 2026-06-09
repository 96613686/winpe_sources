# RegistrationKeyHelper::DeleteKey(ushort const *,ushort const *,int)

- ea: `0x1800760f0`
- end: `0x180076272`
- name: `?DeleteKey@RegistrationKeyHelper@@SAJPEBG0H@Z`
- size: `386`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR pszKeyName, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180056ccc`
- `0x180058074`
- `0x1800b7794`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x1800307c4`
- `0x1800760f0`
- `0x180076278`
- `0x180076b8c`
- `0x180076bd8`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x1800761ed`
- `ncrypt!NCryptOpenKey` at `0x1800761ed`
- `ncrypt!NCryptFreeObject` at `0x180076235`
- `ncrypt!NCryptFreeObject` at `0x180076245`
- `ncrypt!NCryptFreeObject` at `0x180076235`
- `ncrypt!NCryptFreeObject` at `0x180076245`

## string_xrefs

- `0x180076123`: `RegistrationKeyHelper::DeleteKey`
- `0x18007619a`: `OpenNCryptStorageProvider`
- `0x180076212`: `DeleteNCryptKey`
- `0x1800761f9`: `NCryptOpenKey`

## pseudocode

```c
__int64 __fastcall RegistrationKeyHelper::DeleteKey(const unsigned __int16 *a1, LPCWSTR pszKeyName, int a3)
{
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rdx
  SECURITY_STATUS IsTpmProvider; // eax
  const wchar_t *v9; // r8
  NCRYPT_PROV_HANDLE hProvider[5]; // [rsp+30h] [rbp-28h] BYREF
  int v12; // [rsp+60h] [rbp+8h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+78h] [rbp+20h] BYREF

  hProvider[0] = 0;
  phKey = 0;
  v12 = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationKeyHelper::DeleteKey", L"providerName");
    v7 = L"providerName";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationKeyHelper::DeleteKey", v7);
    goto LABEL_15;
  }
  if ( !pszKeyName )
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationKeyHelper::DeleteKey", L"keyContainer");
    v7 = L"keyContainer";
    goto LABEL_3;
  }
  IsTpmProvider = RegistrationKeyHelper::OpenNCryptStorageProvider(a1, hProvider, 0);
  v6 = IsTpmProvider;
  if ( IsTpmProvider >= 0 )
  {
    IsTpmProvider = RegistrationKeyHelper::IsTpmProvider(a1, &v12);
    v6 = IsTpmProvider;
    if ( IsTpmProvider >= 0 )
    {
      IsTpmProvider = NCryptOpenKey(
                        hProvider[0],
                        &phKey,
                        pszKeyName,
                        0,
                        (v12 != 0 ? 268435520 : 64) | (a3 != 0 ? 0x20 : 0));
      v6 = IsTpmProvider;
      if ( IsTpmProvider >= 0 )
      {
        IsTpmProvider = RegistrationKeyHelper::DeleteNCryptKey(&phKey);
        v6 = IsTpmProvider;
        if ( IsTpmProvider >= 0 )
          goto LABEL_15;
        v9 = L"DeleteNCryptKey";
      }
      else
      {
        v9 = L"NCryptOpenKey";
      }
    }
    else
    {
      v9 = L"RegistrationKeyHelper::IsTpmProvider";
    }
  }
  else
  {
    v9 = L"OpenNCryptStorageProvider";
  }
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x.",
    L"RegistrationKeyHelper::DeleteKey",
    v9,
    (unsigned int)IsTpmProvider);
LABEL_15:
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( hProvider[0] )
    NCryptFreeObject(hProvider[0]);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationKeyHelper::DeleteKey", v6);
  return v6;
}

```

## disassembly

```asm
0x1800760f0  mov     rax, rsp
0x1800760f3  mov     [rax+10h], rbx
0x1800760f7  mov     [rax+18h], rbp
0x1800760fb  push    rsi
0x1800760fc  push    rdi
0x1800760fd  push    r15
0x1800760ff  sub     rsp, 40h
0x180076103  mov     qword ptr [rax-28h], 0
0x18007610b  mov     ebp, r8d
0x18007610e  mov     qword ptr [rax+20h], 0
0x180076116  mov     rsi, rdx
0x180076119  mov     dword ptr [rax+8], 0
0x180076120  mov     rdi, rcx
0x180076123  lea     r15, aRegistrationke_14; "RegistrationKeyHelper::DeleteKey"
0x18007612a  test    rcx, rcx
0x18007612d  jnz     short loc_18007615E
0x18007612f  lea     r8, aProvidername; "providerName"
0x180076136  mov     rdx, r15
0x180076139  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180076140  mov     ebx, 80070057h
0x180076145  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007614a  lea     rdx, aProvidername; "providerName"
0x180076151  mov     rcx, r15; unsigned __int16 *
0x180076154  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180076159  jmp     loc_18007622B
0x18007615e  test    rsi, rsi
0x180076161  jnz     short loc_180076187
0x180076163  lea     r8, aKeycontainer; "keyContainer"
0x18007616a  mov     rdx, r15
0x18007616d  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180076174  mov     ebx, 80070057h
0x180076179  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007617e  lea     rdx, aKeycontainer; "keyContainer"
0x180076185  jmp     short loc_180076151
0x180076187  xor     r8d, r8d; int
0x18007618a  lea     rdx, [rsp+58h+hProvider]; phProvider
0x18007618f  call    ?OpenNCryptStorageProvider@RegistrationKeyHelper@@SAJPEBGPEA_KH@Z; RegistrationKeyHelper::OpenNCryptStorageProvider(ushort const *,unsigned __int64 *,int)
0x180076194  mov     ebx, eax
0x180076196  test    eax, eax
0x180076198  jns     short loc_1800761A3
0x18007619a  lea     r8, aOpenncryptstor; "OpenNCryptStorageProvider"
0x1800761a1  jmp     short loc_180076219
0x1800761a3  lea     rdx, [rsp+58h+arg_0]; int *
0x1800761a8  mov     rcx, rdi; unsigned __int16 *
0x1800761ab  call    ?IsTpmProvider@RegistrationKeyHelper@@SAJPEBGAEAH@Z; RegistrationKeyHelper::IsTpmProvider(ushort const *,int &)
0x1800761b0  mov     ebx, eax
0x1800761b2  test    eax, eax
0x1800761b4  jns     short loc_1800761BF
0x1800761b6  lea     r8, aRegistrationke_3; "RegistrationKeyHelper::IsTpmProvider"
0x1800761bd  jmp     short loc_180076219
0x1800761bf  mov     eax, [rsp+58h+arg_0]
0x1800761c3  lea     rdx, [rsp+58h+phKey]; phKey
0x1800761c8  neg     eax
0x1800761ca  mov     r8, rsi; pszKeyName
0x1800761cd  sbb     ecx, ecx
0x1800761cf  and     ecx, 10000000h
0x1800761d5  add     ecx, 40h ; '@'
0x1800761d8  neg     ebp
0x1800761da  sbb     eax, eax
0x1800761dc  xor     r9d, r9d; dwLegacyKeySpec
0x1800761df  and     eax, 20h
0x1800761e2  or      eax, ecx
0x1800761e4  mov     rcx, [rsp+58h+hProvider]; hProvider
0x1800761e9  mov     [rsp+58h+dwFlags], eax; dwFlags
0x1800761ed  call    cs:__imp_NCryptOpenKey
0x1800761f3  mov     ebx, eax
0x1800761f5  test    eax, eax
0x1800761f7  jns     short loc_180076202
0x1800761f9  lea     r8, aNcryptopenkey_0; "NCryptOpenKey"
0x180076200  jmp     short loc_180076219
0x180076202  lea     rcx, [rsp+58h+phKey]; unsigned __int64 *
0x180076207  call    ?DeleteNCryptKey@RegistrationKeyHelper@@SAJAEA_K@Z; RegistrationKeyHelper::DeleteNCryptKey(unsigned __int64 &)
0x18007620c  mov     ebx, eax
0x18007620e  test    eax, eax
0x180076210  jns     short loc_18007622B
0x180076212  lea     r8, aDeletencryptke; "DeleteNCryptKey"
0x180076219  mov     r9d, eax
0x18007621c  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180076223  mov     rdx, r15
0x180076226  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007622b  mov     rcx, [rsp+58h+phKey]; hObject
0x180076230  test    rcx, rcx
0x180076233  jz      short loc_18007623B
0x180076235  call    cs:__imp_NCryptFreeObject
0x18007623b  mov     rcx, [rsp+58h+hProvider]; hObject
0x180076240  test    rcx, rcx
0x180076243  jz      short loc_18007624B
0x180076245  call    cs:__imp_NCryptFreeObject
0x18007624b  mov     r8d, ebx
0x18007624e  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180076255  mov     rdx, r15
0x180076258  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007625d  mov     rbp, [rsp+58h+arg_10]
0x180076262  mov     eax, ebx
0x180076264  mov     rbx, [rsp+58h+arg_8]
0x180076269  add     rsp, 40h
0x18007626d  pop     r15
0x18007626f  pop     rdi
0x180076270  pop     rsi
0x180076271  retn
```
