# NgcStatusStorage::ReadKey(HKEY__ *,ushort const *,_GUID,STRUCT_NGC_REG_KEY *)

- ea: `0x1800049f0`
- end: `0x1800051cc`
- name: `?ReadKey@NgcStatusStorage@@CAKPEAUHKEY__@@PEBGU_GUID@@PEAUSTRUCT_NGC_REG_KEY@@@Z`
- size: `2012`
- prototype: `static unsigned int(HKEY, const unsigned __int16 *, struct _GUID *__struct_ptr, struct STRUCT_NGC_REG_KEY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180012280`

## callees

- `0x1800049f0`
- `0x180006750`
- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x180012948`
- `0x18003334c`
- `0x180043e54`
- `0x18008cf68`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004c92`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004d6d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004c92`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004d6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004a45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004a45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004e46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004e46`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004a9f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004b29`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004bac`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004c4d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004cd0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004d2f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004dab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004a9f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004b29`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004bac`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004c4d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004cd0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004d2f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004dab`

## string_xrefs

- `0x180004aa5`: `RegReadDwordValue`
- `0x180004ff7`: `RegReadDwordValue`
- `0x180004c53`: `RegReadStringValue`
- `0x180005045`: `RegReadStringValue`
- `0x180004abb`: `%s: The registry key value "%s@%s" does not exist. Using default value %lu. Error code: 0x%08x.`
- `0x180004b3e`: `%s: The registry key value "%s@%s" does not exist. Using default value %lu. Error code: 0x%08x.`
- `0x180004bcf`: `%s: The registry key value "%s@%s" does not exist. Using default value %lu. Error code: 0x%08x.`
- `0x180004ec6`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`
- `0x180004eeb`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`
- `0x180004fac`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x180004fb8`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x180004f36`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x1800050a5`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x18000513a`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x180004fc7`: `RegOpenKeyExW`
- `0x180004e1f`: `NgcStatusStorage::ReadKey`
- `0x180004f4e`: `NgcStatusStorage::ReadKey`
- `0x180004fd8`: `NgcStatusStorage::ReadKey`
- `0x18000515b`: `NgcStatusStorage::ReadKey`
- `0x180004e94`: `%s: The registry key value "%s@%s" is not of type DWORD. Using default value %lu. Error code: 0x%08x.`
- `0x180004eba`: `%s: The registry key value "%s@%s" is not of type DWORD. Using default value %lu. Error code: 0x%08x.`
- `0x180005034`: `%s: The registry key value "%s@%s" is not of type DWORD. Using default value %lu. Error code: 0x%08x.`
- `0x180004fe2`: `%s: Cannot open NGC key registry. Key name: %s. Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall NgcStatusStorage::ReadKey(
        HKEY a1,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        struct STRUCT_NGC_REG_KEY *a4)
{
  void **v4; // r13
  void **v5; // r14
  void **v6; // rsi
  struct STRUCT_NGC_REG_KEY *v7; // r15
  LSTATUS v9; // eax
  DWORD v10; // ebx
  DWORD *v11; // r14
  LSTATUS ValueW; // eax
  const wchar_t *v13; // rsi
  wchar_t *v14; // rcx
  LSTATUS v15; // eax
  wchar_t *v16; // rcx
  LSTATUS v17; // eax
  HKEY v18; // r12
  LSTATUS v19; // eax
  LSTATUS v20; // r14d
  DWORD v21; // ebx
  HANDLE ProcessHeap; // rax
  void *v23; // rax
  HKEY v24; // r12
  LSTATUS v25; // eax
  LSTATUS v26; // r14d
  DWORD v27; // ebx
  HANDLE v28; // rax
  void *v29; // rax
  unsigned int StringValue; // eax
  void **v31; // r12
  unsigned int v32; // eax
  wchar_t *v34; // rcx
  wchar_t *v35; // rcx
  const WCHAR *v36; // r9
  __int64 v37; // r9
  __int64 v38; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-30h]
  PHKEY phkResulta; // [rsp+20h] [rbp-30h]
  PHKEY phkResultb; // [rsp+20h] [rbp-30h]
  PVOID pvData; // [rsp+28h] [rbp-28h]
  PVOID pvDataa; // [rsp+28h] [rbp-28h]
  PVOID pvDatab; // [rsp+28h] [rbp-28h]
  DWORD pdwType; // [rsp+40h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-Ch] BYREF
  HKEY hkey; // [rsp+48h] [rbp-8h] BYREF
  DWORD v49; // [rsp+A8h] [rbp+58h] BYREF

  v4 = (void **)((char *)a4 + 16);
  v5 = (void **)((char *)a4 + 40);
  *((_QWORD *)a4 + 7) = 0;
  v6 = (void **)((char *)a4 + 48);
  hkey = 0;
  v7 = a4;
  *((_QWORD *)a4 + 2) = 0;
  *((_QWORD *)a4 + 5) = 0;
  *((_QWORD *)a4 + 6) = 0;
  v9 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hkey);
  v10 = v9;
  if ( !v9 )
  {
    v11 = (DWORD *)((char *)v7 + 24);
    pdwType = 0;
    v49 = 0;
    pcbData = 4;
    if ( v7 == (struct STRUCT_NGC_REG_KEY *)-24LL )
    {
      v13 = L"RegReadDwordValue";
      goto LABEL_64;
    }
    ValueW = RegGetValueW(hkey, 0, L"AttestationLevel", 0xFFFFu, &pdwType, &v49, &pcbData);
    v13 = L"RegReadDwordValue";
    v10 = ValueW;
    if ( ValueW == 2 )
    {
      LODWORD(pvData) = 2;
      v14 = (wchar_t *)L"%s: The registry key value \"%s@%s\" does not exist. Using default value %lu. Error code: 0x%08x.";
    }
    else
    {
      if ( ValueW != 234 )
      {
        if ( ValueW )
        {
          Logger::WriteRegistryFailureEvent(ValueW, L"RegGetValueW", a2, L"AttestationLevel");
          v36 = L"AttestationLevel";
          goto LABEL_55;
        }
        if ( pdwType == 4 )
        {
LABEL_6:
          *v11 = v49;
          v11 = (DWORD *)((char *)v7 + 28);
          pdwType = 0;
          v49 = 0;
          pcbData = 4;
          if ( v7 == (struct STRUCT_NGC_REG_KEY *)-28LL )
            goto LABEL_64;
          v15 = RegGetValueW(hkey, 0, L"AikCertStatus", 0xFFFFu, &pdwType, &v49, &pcbData);
          v10 = v15;
          if ( v15 == 2 )
          {
            LODWORD(pvDataa) = 2;
            v16 = (wchar_t *)L"%s: The registry key value \"%s@%s\" does not exist. Using default value %lu. Error code: 0x%08x.";
          }
          else
          {
            if ( v15 != 234 )
            {
              if ( v15 )
              {
                Logger::WriteRegistryFailureEvent(v15, L"RegGetValueW", a2, L"AikCertStatus");
                v36 = L"AikCertStatus";
                goto LABEL_55;
              }
              if ( pdwType == 4 )
                goto LABEL_10;
            }
            LODWORD(pvDataa) = v15;
            v16 = (wchar_t *)L"%s: The registry key value \"%s@%s\" is not of type DWORD. Using default value %lu. Error code: 0x%08x.";
          }
          LODWORD(phkResult) = 0;
          Logger::TraceWarning(v16, L"RegReadDwordValue", a2, L"AikCertStatus", phkResult, pvDataa);
LABEL_10:
          *v11 = v49;
          v11 = (DWORD *)((char *)v7 + 32);
          pdwType = 0;
          v49 = 0;
          pcbData = 4;
          if ( v7 != (struct STRUCT_NGC_REG_KEY *)-32LL )
          {
            v17 = RegGetValueW(hkey, 0, L"NgcKeyStatus", 0xFFFFu, &pdwType, &v49, &pcbData);
            v10 = v17;
            switch ( v17 )
            {
              case 2:
                LODWORD(pvDatab) = 2;
                LODWORD(phkResult) = 0;
                Logger::TraceWarning(
                  (wchar_t *)L"%s: The registry key value \"%s@%s\" does not exist. Using default value %lu. Error code: 0x%08x.",
                  L"RegReadDwordValue",
                  a2,
                  L"NgcKeyStatus",
                  phkResult,
                  pvDatab);
LABEL_17:
                *v11 = v49;
                v49 = 0;
                pdwType = 0;
                if ( v4 )
                {
                  v18 = hkey;
                  *v4 = 0;
                  v19 = RegGetValueW(v18, 0, L"NgcKeyName", v10, &pdwType, 0, &v49);
                  v13 = L"RegReadStringValue";
                  v20 = v19;
                  if ( v19 == v10 )
                  {
                    v34 = (wchar_t *)L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.";
                  }
                  else
                  {
                    if ( v19 != 1630 )
                    {
                      if ( (!v19 || v19 == 234) && v49 )
                      {
                        v21 = v49;
                        ProcessHeap = GetProcessHeap();
                        v23 = HeapAlloc(ProcessHeap, 8u, v21);
                        *v4 = v23;
                        if ( !v23 )
                        {
                          v10 = 14;
                          v20 = 14;
                          Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadStringValue");
LABEL_71:
                          Logger::WriteRegistryFailureEvent(v20, L"RegGetValueW", a2, L"NgcKeyName");
                          LODWORD(phkResulta) = v20;
                          Logger::TraceWarning(
                            (wchar_t *)L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
                            L"RegReadStringValue",
                            a2,
                            L"NgcKeyName",
                            phkResulta);
                          SafeFree(*v4);
                          *v4 = 0;
                          goto LABEL_56;
                        }
                        v10 = 2;
                        v20 = RegGetValueW(v18, 0, L"NgcKeyName", 2u, &pdwType, v23, &v49);
                      }
                      if ( !v20 )
                        goto LABEL_25;
                      v10 = v20;
                      goto LABEL_71;
                    }
                    v34 = (wchar_t *)L"%s: The registry key value \"%s@%s\" is not of one of the specified types (flags = "
                                      "0x%08x). Using default value NULL.";
                  }
                  LODWORD(phkResulta) = v10;
                  Logger::TraceWarning(v34, L"RegReadStringValue", a2, L"NgcKeyName", phkResulta);
LABEL_25:
                  v5 = (void **)((char *)v7 + 40);
                  pdwType = 0;
                  v49 = 0;
                  if ( v7 == (struct STRUCT_NGC_REG_KEY *)-40LL )
                  {
                    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadStringValue", L"pData");
                    v10 = 87;
LABEL_78:
                    Logger::TraceError(
                      L"%s: %s failed with win32 error code: 0x%08x.",
                      L"NgcStatusStorage::ReadKey",
                      L"RegReadStringValue",
                      v10);
                    v31 = (void **)((char *)v7 + 56);
                    goto LABEL_37;
                  }
                  v24 = hkey;
                  *v5 = 0;
                  v25 = RegGetValueW(v24, 0, L"IdpDomain", v10, &pdwType, 0, &v49);
                  v26 = v25;
                  if ( v25 == v10 )
                  {
                    v35 = (wchar_t *)L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.";
                  }
                  else
                  {
                    if ( v25 != 1630 )
                    {
                      if ( (!v25 || v25 == 234) && v49 )
                      {
                        v27 = v49;
                        v28 = GetProcessHeap();
                        v29 = HeapAlloc(v28, 8u, v27);
                        *((_QWORD *)v7 + 5) = v29;
                        if ( !v29 )
                        {
                          v10 = 14;
                          v26 = 14;
                          Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadStringValue");
LABEL_77:
                          Logger::WriteRegistryFailureEvent(v26, L"RegGetValueW", a2, L"IdpDomain");
                          LODWORD(phkResultb) = v26;
                          Logger::TraceWarning(
                            (wchar_t *)L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
                            L"RegReadStringValue",
                            a2,
                            L"IdpDomain",
                            phkResultb);
                          v5 = (void **)((char *)v7 + 40);
                          SafeFree(*((void **)v7 + 5));
                          *((_QWORD *)v7 + 5) = 0;
                          goto LABEL_78;
                        }
                        v10 = 2;
                        v26 = RegGetValueW(v24, 0, L"IdpDomain", 2u, &pdwType, v29, &v49);
                      }
                      if ( !v26 )
                      {
LABEL_33:
                        StringValue = RegReadStringValue(hkey, 0, L"TenantDomain", a2, v10, (unsigned __int16 **)v7 + 6);
                        v10 = StringValue;
                        if ( !StringValue )
                        {
                          v31 = (void **)((char *)v7 + 56);
                          v32 = RegReadStringValue(hkey, 0, L"UserId", a2, 2u, (unsigned __int16 **)v7 + 7);
                          v10 = v32;
                          if ( v32 )
                            Logger::TraceError(
                              L"%s: %s failed with win32 error code: 0x%08x.",
                              L"NgcStatusStorage::ReadKey",
                              L"RegReadStringValue",
                              v32);
                          else
                            *(struct _GUID *)v7 = *a3;
                          goto LABEL_36;
                        }
                        v37 = StringValue;
LABEL_57:
                        Logger::TraceError(
                          L"%s: %s failed with win32 error code: 0x%08x.",
                          L"NgcStatusStorage::ReadKey",
                          v13,
                          v37);
                        v31 = (void **)((char *)v7 + 56);
LABEL_36:
                        v5 = (void **)((char *)v7 + 40);
LABEL_37:
                        v6 = (void **)((char *)v7 + 48);
                        goto LABEL_38;
                      }
                      v10 = v26;
                      goto LABEL_77;
                    }
                    v35 = (wchar_t *)L"%s: The registry key value \"%s@%s\" is not of one of the specified types (flags = "
                                      "0x%08x). Using default value NULL.";
                  }
                  LODWORD(phkResultb) = v10;
                  Logger::TraceWarning(v35, L"RegReadStringValue", a2, L"IdpDomain", phkResultb);
                  goto LABEL_33;
                }
                v13 = L"RegReadStringValue";
                goto LABEL_64;
              case 234:
                goto LABEL_65;
              case 0:
                if ( pdwType == 4 )
                {
LABEL_16:
                  v10 = 2;
                  goto LABEL_17;
                }
LABEL_65:
                LODWORD(pvDatab) = v17;
                LODWORD(phkResult) = 0;
                Logger::TraceWarning(
                  (wchar_t *)L"%s: The registry key value \"%s@%s\" is not of type DWORD. Using default value %lu. Error code: 0x%08x.",
                  L"RegReadDwordValue",
                  a2,
                  L"NgcKeyStatus",
                  phkResult,
                  pvDatab);
                goto LABEL_16;
            }
            Logger::WriteRegistryFailureEvent(v17, L"RegGetValueW", a2, L"NgcKeyStatus");
            v36 = L"NgcKeyStatus";
LABEL_55:
            LODWORD(phkResult) = v10;
            Logger::TraceWarning(
              (wchar_t *)L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
              L"RegReadDwordValue",
              a2,
              v36,
              phkResult);
            *v11 = v49;
LABEL_56:
            v37 = v10;
            goto LABEL_57;
          }
LABEL_64:
          Logger::TraceError(L"%s: \"%s\" should not be null.", v13, L"pData");
          v10 = 87;
          goto LABEL_56;
        }
      }
      LODWORD(pvData) = ValueW;
      v14 = (wchar_t *)L"%s: The registry key value \"%s@%s\" is not of type DWORD. Using default value %lu. Error code: 0x%08x.";
    }
    LODWORD(phkResult) = 0;
    Logger::TraceWarning(v14, L"RegReadDwordValue", a2, L"AttestationLevel", phkResult, pvData);
    goto LABEL_6;
  }
  Logger::WriteRegistryFailureEvent(v9, L"RegOpenKeyExW", a2);
  Logger::TraceInformation(
    L"%s: Cannot open NGC key registry. Key name: %s. Error code: 0x%08x.",
    L"NgcStatusStorage::ReadKey",
    a2,
    v10);
  v31 = (void **)((char *)v7 + 56);
LABEL_38:
  if ( hkey )
  {
    RegCloseKey(hkey);
    hkey = 0;
  }
  if ( v10 )
  {
    SafeFree(*v4);
    SafeFree(*v5);
    SafeFree(*v6);
    SafeFree(*v31);
    v38 = 64;
    do
    {
      *(_BYTE *)v7 = 0;
      v7 = (struct STRUCT_NGC_REG_KEY *)((char *)v7 + 1);
      --v38;
    }
    while ( v38 );
  }
  return v10;
}

```

## disassembly

```asm
0x1800049f0  mov     [rsp-38h+arg_0], rbx
0x1800049f5  mov     [rsp-38h+arg_10], r8
0x1800049fa  push    rbp
0x1800049fb  push    rsi
0x1800049fc  push    rdi
0x1800049fd  push    r12
0x1800049ff  push    r13
0x180004a01  push    r14
0x180004a03  push    r15
0x180004a05  mov     rbp, rsp
0x180004a08  sub     rsp, 50h
0x180004a0c  xor     r12d, r12d
0x180004a0f  lea     r13, [r9+10h]
0x180004a13  lea     r14, [r9+28h]
0x180004a17  mov     [r9+38h], r12
0x180004a1b  lea     rsi, [r9+30h]
0x180004a1f  mov     [rbp+hkey], r12
0x180004a23  mov     r15, r9
0x180004a26  mov     [r13+0], r12
0x180004a2a  lea     rax, [rbp+hkey]
0x180004a2e  mov     [r14], r12
0x180004a31  mov     r9d, 20019h; samDesired
0x180004a37  mov     [rsi], r12
0x180004a3a  xor     r8d, r8d; ulOptions
0x180004a3d  mov     [rsp+50h+phkResult], rax; phkResult
0x180004a42  mov     rdi, rdx
0x180004a45  call    cs:__imp_RegOpenKeyExW
0x180004a4b  mov     ebx, eax
0x180004a4d  test    eax, eax
0x180004a4f  jnz     loc_180004FC4
0x180004a55  lea     r14, [r15+18h]
0x180004a59  mov     [rbp+pdwType], r12d
0x180004a5d  mov     [rbp+arg_18], r12d
0x180004a61  mov     [rbp+var_C], 4
0x180004a68  test    r14, r14
0x180004a6b  jz      loc_180004FF7
0x180004a71  mov     rcx, [rbp+hkey]; hkey
0x180004a75  lea     rax, [rbp+var_C]
0x180004a79  mov     [rsp+50h+pcbData], rax; pcbData
0x180004a7e  lea     r8, Value; "AttestationLevel"
0x180004a85  lea     rax, [rbp+arg_18]
0x180004a89  mov     r9d, 0FFFFh; dwFlags
0x180004a8f  mov     [rsp+50h+pvData], rax; pvData
0x180004a94  xor     edx, edx; lpSubKey
0x180004a96  lea     rax, [rbp+pdwType]
0x180004a9a  mov     [rsp+50h+phkResult], rax; pdwType
0x180004a9f  call    cs:__imp_RegGetValueW
0x180004aa5  lea     rsi, aRegreaddwordva; "RegReadDwordValue"
0x180004aac  mov     ebx, eax
0x180004aae  cmp     eax, 2
0x180004ab1  jnz     loc_180004E76
0x180004ab7  mov     dword ptr [rsp+50h+pvData], eax
0x180004abb  lea     rcx, aSTheRegistryKe_3; "%s: The registry key value \"%s@%s\" do"...
0x180004ac2  lea     r9, Value; "AttestationLevel"
0x180004ac9  mov     dword ptr [rsp+50h+phkResult], r12d
0x180004ace  mov     r8, rdi
0x180004ad1  mov     rdx, rsi
0x180004ad4  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180004ad9  mov     eax, [rbp+arg_18]
0x180004adc  mov     [r14], eax
0x180004adf  lea     r14, [r15+1Ch]
0x180004ae3  mov     [rbp+pdwType], r12d
0x180004ae7  mov     [rbp+arg_18], r12d
0x180004aeb  mov     [rbp+var_C], 4
0x180004af2  test    r14, r14
0x180004af5  jz      loc_180004FFE
0x180004afb  mov     rcx, [rbp+hkey]; hkey
0x180004aff  lea     rax, [rbp+var_C]
0x180004b03  mov     [rsp+50h+pcbData], rax; pcbData
0x180004b08  lea     r8, aAikcertstatus; "AikCertStatus"
0x180004b0f  lea     rax, [rbp+arg_18]
0x180004b13  mov     r9d, 0FFFFh; dwFlags
0x180004b19  mov     [rsp+50h+pvData], rax; pvData
0x180004b1e  xor     edx, edx; lpSubKey
0x180004b20  lea     rax, [rbp+pdwType]
0x180004b24  mov     [rsp+50h+phkResult], rax; pdwType
0x180004b29  call    cs:__imp_RegGetValueW
0x180004b2f  mov     ebx, eax
0x180004b31  cmp     eax, 2
0x180004b34  jnz     loc_180004EA0
0x180004b3a  mov     dword ptr [rsp+50h+pvData], eax
0x180004b3e  lea     rcx, aSTheRegistryKe_3; "%s: The registry key value \"%s@%s\" do"...
0x180004b45  lea     r9, aAikcertstatus; "AikCertStatus"
0x180004b4c  mov     dword ptr [rsp+50h+phkResult], r12d
0x180004b51  mov     r8, rdi
0x180004b54  mov     rdx, rsi
0x180004b57  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180004b5c  mov     eax, [rbp+arg_18]
0x180004b5f  mov     [r14], eax
0x180004b62  lea     r14, [r15+20h]
0x180004b66  mov     [rbp+pdwType], r12d
0x180004b6a  mov     [rbp+arg_18], r12d
0x180004b6e  mov     [rbp+var_C], 4
0x180004b75  test    r14, r14
0x180004b78  jz      loc_180004FFE
0x180004b7e  mov     rcx, [rbp+hkey]; hkey
0x180004b82  lea     rax, [rbp+var_C]
0x180004b86  mov     [rsp+50h+pcbData], rax; pcbData
0x180004b8b  lea     r8, aNgckeystatus; "NgcKeyStatus"
0x180004b92  lea     rax, [rbp+arg_18]
0x180004b96  mov     r9d, 0FFFFh; dwFlags
0x180004b9c  mov     [rsp+50h+pvData], rax; pvData
0x180004ba1  xor     edx, edx; lpSubKey
0x180004ba3  lea     rax, [rbp+pdwType]
0x180004ba7  mov     [rsp+50h+phkResult], rax; pdwType
0x180004bac  call    cs:__imp_RegGetValueW
0x180004bb2  mov     ebx, eax
0x180004bb4  cmp     eax, 2
0x180004bb7  jnz     short loc_180004BDD
0x180004bb9  mov     dword ptr [rsp+50h+pvData], eax
0x180004bbd  lea     r9, aNgckeystatus; "NgcKeyStatus"
0x180004bc4  mov     r8, rdi
0x180004bc7  mov     dword ptr [rsp+50h+phkResult], r12d
0x180004bcc  mov     rdx, rsi
0x180004bcf  lea     rcx, aSTheRegistryKe_3; "%s: The registry key value \"%s@%s\" do"...
0x180004bd6  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180004bdb  jmp     short loc_180004C00
0x180004bdd  cmp     ebx, 0EAh
0x180004be3  jz      loc_18000501E
0x180004be9  test    ebx, ebx
0x180004beb  jnz     loc_180004F8B
0x180004bf1  cmp     [rbp+pdwType], 4
0x180004bf5  jnz     loc_18000501E
0x180004bfb  mov     ebx, 2
0x180004c00  mov     eax, [rbp+arg_18]
0x180004c03  mov     [r14], eax
0x180004c06  mov     [rbp+arg_18], r12d
0x180004c0a  mov     [rbp+pdwType], r12d
0x180004c0e  test    r13, r13
0x180004c11  jz      loc_180005045
0x180004c17  mov     r12, [rbp+hkey]
0x180004c1b  lea     rax, [rbp+arg_18]
0x180004c1f  mov     [rsp+50h+pcbData], rax; pcbData
0x180004c24  lea     r8, aNgckeyname; "NgcKeyName"
0x180004c2b  lea     rax, [rbp+pdwType]
0x180004c2f  mov     [rsp+50h+pvData], 0; pvData
0x180004c38  mov     r9d, ebx; dwFlags
0x180004c3b  mov     [rsp+50h+phkResult], rax; pdwType
0x180004c40  xor     edx, edx; lpSubKey
0x180004c42  mov     qword ptr [r13+0], 0
0x180004c4a  mov     rcx, r12; hkey
0x180004c4d  call    cs:__imp_RegGetValueW
0x180004c53  lea     rsi, aRegreadstringv; "RegReadStringValue"
0x180004c5a  mov     r14d, eax
0x180004c5d  cmp     eax, ebx
0x180004c5f  jz      loc_180004FAC
0x180004c65  cmp     eax, 65Eh
0x180004c6a  jz      loc_180004EC6
0x180004c70  test    eax, eax
0x180004c72  jnz     loc_18000504E
0x180004c78  mov     eax, [rbp+arg_18]
0x180004c7b  test    eax, eax
0x180004c7d  jz      short loc_180004CD9
0x180004c7f  mov     ebx, eax
0x180004c81  call    cs:__imp_GetProcessHeap
0x180004c87  mov     r8d, ebx; dwBytes
0x180004c8a  mov     edx, 8; dwFlags
0x180004c8f  mov     rcx, rax; hHeap
0x180004c92  call    cs:__imp_HeapAlloc
0x180004c98  mov     [r13+0], rax
0x180004c9c  test    rax, rax
0x180004c9f  jz      loc_18000505E
0x180004ca5  lea     rcx, [rbp+arg_18]
0x180004ca9  mov     ebx, 2
0x180004cae  mov     [rsp+50h+pcbData], rcx; pcbData
0x180004cb3  lea     r8, aNgckeyname; "NgcKeyName"
0x180004cba  mov     [rsp+50h+pvData], rax; pvData
0x180004cbf  mov     r9d, ebx; dwFlags
0x180004cc2  lea     rax, [rbp+pdwType]
0x180004cc6  xor     edx, edx; lpSubKey
0x180004cc8  mov     rcx, r12; hkey
0x180004ccb  mov     [rsp+50h+phkResult], rax; pdwType
0x180004cd0  call    cs:__imp_RegGetValueW
0x180004cd6  mov     r14d, eax
0x180004cd9  xor     r12d, r12d
0x180004cdc  test    r14d, r14d
0x180004cdf  jnz     loc_18000507A
0x180004ce5  lea     r14, [r15+28h]
0x180004ce9  mov     [rbp+pdwType], r12d
0x180004ced  mov     [rbp+arg_18], r12d
0x180004cf1  test    r14, r14
0x180004cf4  jz      loc_1800050C6
0x180004cfa  mov     r12, [rbp+hkey]
0x180004cfe  lea     rax, [rbp+arg_18]
0x180004d02  mov     [rsp+50h+pcbData], rax; pcbData
0x180004d07  lea     r8, aIdpdomain; "IdpDomain"
0x180004d0e  lea     rax, [rbp+pdwType]
0x180004d12  mov     [rsp+50h+pvData], 0; pvData
0x180004d1b  mov     r9d, ebx; dwFlags
0x180004d1e  mov     [rsp+50h+phkResult], rax; pdwType
0x180004d23  xor     edx, edx; lpSubKey
0x180004d25  mov     qword ptr [r14], 0
0x180004d2c  mov     rcx, r12; hkey
0x180004d2f  call    cs:__imp_RegGetValueW
0x180004d35  mov     r14d, eax
0x180004d38  cmp     eax, ebx
0x180004d3a  jz      loc_180004FB8
0x180004d40  cmp     eax, 65Eh
0x180004d45  jz      loc_180004EEB
0x180004d4b  test    eax, eax
0x180004d4d  jnz     loc_1800050E3
0x180004d53  mov     eax, [rbp+arg_18]
0x180004d56  test    eax, eax
0x180004d58  jz      short loc_180004DB4
0x180004d5a  mov     ebx, eax
0x180004d5c  call    cs:__imp_GetProcessHeap
0x180004d62  mov     r8d, ebx; dwBytes
0x180004d65  mov     edx, 8; dwFlags
0x180004d6a  mov     rcx, rax; hHeap
0x180004d6d  call    cs:__imp_HeapAlloc
0x180004d73  mov     [r15+28h], rax
0x180004d77  test    rax, rax
0x180004d7a  jz      loc_1800050F3
0x180004d80  lea     rcx, [rbp+arg_18]
0x180004d84  mov     ebx, 2
0x180004d89  mov     [rsp+50h+pcbData], rcx; pcbData
0x180004d8e  lea     r8, aIdpdomain; "IdpDomain"
0x180004d95  mov     [rsp+50h+pvData], rax; pvData
0x180004d9a  mov     r9d, ebx; dwFlags
0x180004d9d  lea     rax, [rbp+pdwType]
0x180004da1  xor     edx, edx; lpSubKey
0x180004da3  mov     rcx, r12; hkey
0x180004da6  mov     [rsp+50h+phkResult], rax; pdwType
0x180004dab  call    cs:__imp_RegGetValueW
0x180004db1  mov     r14d, eax
0x180004db4  xor     r12d, r12d
0x180004db7  test    r14d, r14d
0x180004dba  jnz     loc_18000510F
0x180004dc0  mov     rcx, [rbp+hkey]; hkey
0x180004dc4  lea     rax, [r15+30h]
0x180004dc8  mov     [rsp+50h+pvData], rax; unsigned __int16 **
0x180004dcd  lea     r8, aTenantdomain; "TenantDomain"
0x180004dd4  mov     r9, rdi; unsigned __int16 *
0x180004dd7  mov     dword ptr [rsp+50h+phkResult], ebx; dwFlags
0x180004ddb  xor     edx, edx; lpSubKey
0x180004ddd  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x180004de2  mov     ebx, eax
0x180004de4  test    eax, eax
0x180004de6  jnz     loc_18000517A
0x180004dec  mov     rcx, [rbp+hkey]; hkey
0x180004df0  lea     r12, [r15+38h]
0x180004df4  mov     [rsp+50h+pvData], r12; unsigned __int16 **
0x180004df9  lea     r8, aUserid_0; "UserId"
0x180004e00  mov     r9, rdi; unsigned __int16 *
0x180004e03  mov     dword ptr [rsp+50h+phkResult], 2; dwFlags
0x180004e0b  xor     edx, edx; lpSubKey
0x180004e0d  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x180004e12  mov     ebx, eax
0x180004e14  test    eax, eax
0x180004e16  jz      loc_180005182
0x180004e1c  mov     r9d, eax
0x180004e1f  lea     rdx, aNgcstatusstora_3; "NgcStatusStorage::ReadKey"
0x180004e26  mov     r8, rsi
0x180004e29  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180004e30  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180004e35  lea     r14, [r15+28h]
0x180004e39  lea     rsi, [r15+30h]
0x180004e3d  mov     rcx, [rbp+hkey]; hKey
0x180004e41  test    rcx, rcx
0x180004e44  jz      short loc_180004E54
0x180004e46  call    cs:__imp_RegCloseKey
0x180004e4c  mov     [rbp+hkey], 0
0x180004e54  test    ebx, ebx
0x180004e56  jnz     loc_180005193
0x180004e5c  mov     eax, ebx
0x180004e5e  mov     rbx, [rsp+50h+arg_0]
0x180004e66  add     rsp, 50h
0x180004e6a  pop     r15
0x180004e6c  pop     r14
0x180004e6e  pop     r13
0x180004e70  pop     r12
0x180004e72  pop     rdi
0x180004e73  pop     rsi
0x180004e74  pop     rbp
0x180004e75  retn
0x180004e76  cmp     ebx, 0EAh
0x180004e7c  jz      short loc_180004E90
0x180004e7e  test    ebx, ebx
0x180004e80  jnz     loc_180004F6A
0x180004e86  cmp     [rbp+pdwType], 4
0x180004e8a  jz      loc_180004AD9
0x180004e90  mov     dword ptr [rsp+50h+pvData], ebx
0x180004e94  lea     rcx, aSTheRegistryKe_10; "%s: The registry key value \"%s@%s\" is"...
0x180004e9b  jmp     loc_180004AC2
0x180004ea0  cmp     ebx, 0EAh
0x180004ea6  jz      short loc_180004EB6
0x180004ea8  test    ebx, ebx
0x180004eaa  jnz     short loc_180004F0D
0x180004eac  cmp     [rbp+pdwType], 4
0x180004eb0  jz      loc_180004B5C
0x180004eb6  mov     dword ptr [rsp+50h+pvData], ebx
0x180004eba  lea     rcx, aSTheRegistryKe_10; "%s: The registry key value \"%s@%s\" is"...
0x180004ec1  jmp     loc_180004B45
0x180004ec6  lea     rcx, aSTheRegistryKe_6; "%s: The registry key value \"%s@%s\" is"...
0x180004ecd  mov     rdx, rsi
0x180004ed0  mov     dword ptr [rsp+50h+phkResult], ebx
0x180004ed4  mov     r8, rdi
0x180004ed7  lea     r9, aNgckeyname; "NgcKeyName"
0x180004ede  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180004ee3  xor     r12d, r12d
  ... truncated ...
```
