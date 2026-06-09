# NgcUtils::GetUserNameAndDomainForHybridCloudTrust

- ea: `0x180019cd0`
- end: `0x18001a1f4`
- name: `NgcUtils::GetUserNameAndDomainForHybridCloudTrust`
- size: `1316`
- prototype: `__int64 __usercall@<rax>(PSID Sid@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180019374`

## callees

- `0x180003080`
- `0x18000530d`
- `0x18000a594`
- `0x18000a5b4`
- `0x18000c95c`
- `0x18000ce74`
- `0x180013834`
- `0x180014458`
- `0x180019cd0`
- `0x18001a67c`
- `0x18001addc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a17f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a17f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019e36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019eea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019f65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019f96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a0e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a119`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019e36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019eea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019f65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019f96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a0e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a119`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180019d6e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180019d6e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019fe2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019fe2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a010`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a010`
- `ncrypt!NCryptFreeObject` at `0x180019ed0`
- `ncrypt!NCryptFreeObject` at `0x180019f4f`
- `ncrypt!NCryptFreeObject` at `0x180019f86`
- `ncrypt!NCryptFreeObject` at `0x18001a0ad`
- `ncrypt!NCryptFreeObject` at `0x18001a105`
- `ncrypt!NCryptFreeObject` at `0x180019ed0`
- `ncrypt!NCryptFreeObject` at `0x180019f4f`
- `ncrypt!NCryptFreeObject` at `0x180019f86`
- `ncrypt!NCryptFreeObject` at `0x18001a0ad`
- `ncrypt!NCryptFreeObject` at `0x18001a105`
- `ncrypt!NCryptOpenStorageProvider` at `0x180019da6`
- `ncrypt!NCryptOpenStorageProvider` at `0x180019da6`
- `ncrypt!NCryptGetProperty` at `0x180019eb1`
- `ncrypt!NCryptGetProperty` at `0x180019eb1`
- `ncrypt!NCryptOpenKey` at `0x180019e78`
- `ncrypt!NCryptOpenKey` at `0x180019e78`
- `dsreg!DsrFreeJoinInfo` at `0x180019fa7`
- `dsreg!DsrFreeJoinInfo` at `0x18001a1bb`
- `dsreg!DsrFreeJoinInfo` at `0x180019fa7`
- `dsreg!DsrFreeJoinInfo` at `0x18001a1bb`
- `dsreg!DsrGetJoinInfo` at `0x180019d32`
- `dsreg!DsrGetJoinInfo` at `0x180019d32`
- `cryptngc!NgcFreeEnumState` at `0x180019f76`
- `cryptngc!NgcFreeEnumState` at `0x18001a0f5`
- `cryptngc!NgcFreeEnumState` at `0x180019f76`
- `cryptngc!NgcFreeEnumState` at `0x18001a0f5`
- `cryptngc!NgcEnumUserIdKeys` at `0x180019e15`
- `cryptngc!NgcEnumUserIdKeys` at `0x180019e15`

## string_xrefs

- `0x180019d7c`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180019db9`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18001a025`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18001a090`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18001a0c3`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18001a1a0`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall NgcUtils::GetUserNameAndDomainForHybridCloudTrust(
        PSID Sid,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _BYTE *a5)
{
  int JoinInfo; // eax
  int LastError; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  const char *v12; // r9
  __int64 v13; // rdx
  __int64 v14; // r8
  SECURITY_STATUS v15; // eax
  void *v16; // rcx
  __int64 v17; // rsi
  const WCHAR *v18; // r8
  SECURITY_STATUS Property; // eax
  HLOCAL v20; // rcx
  _WORD *v21; // r9
  unsigned __int64 v22; // rdx
  void **v23; // rdi
  __int64 v24; // rbx
  HLOCAL v25; // rcx
  bool v26; // zf
  _WORD *v27; // rdi
  LSTATUS v28; // eax
  signed int v29; // ebx
  int *v30; // rdx
  char v31; // bl
  __int64 v32; // rdx
  HLOCAL v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r8
  int dwFlags; // [rsp+20h] [rbp-A1h]
  int dwFlagsa; // [rsp+20h] [rbp-A1h]
  int dwFlagsb; // [rsp+20h] [rbp-A1h]
  HLOCAL hMem; // [rsp+30h] [rbp-91h] BYREF
  __int64 v41; // [rsp+38h] [rbp-89h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-81h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-79h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-71h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+58h] [rbp-69h] BYREF
  BYTE pbOutput[4]; // [rsp+60h] [rbp-61h] BYREF
  DWORD pcbResult[3]; // [rsp+64h] [rbp-5Dh] BYREF
  int v48[4]; // [rsp+70h] [rbp-51h] BYREF
  __m128i si128; // [rsp+80h] [rbp-41h]
  void *v50[2]; // [rsp+90h] [rbp-31h] BYREF
  unsigned __int64 v51; // [rsp+A0h] [rbp-21h]
  unsigned __int64 v52; // [rsp+A8h] [rbp-19h]
  _OWORD v53[2]; // [rsp+B0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  pcbResult[1] = 0;
  *(_OWORD *)v50 = 0;
  v51 = 0;
  v52 = 7;
  LOWORD(v50[0]) = 0;
  v41 = 0;
  JoinInfo = DsrGetJoinInfo(0, &v41);
  LastError = JoinInfo;
  if ( JoinInfo < 0 )
  {
    v10 = (unsigned int)JoinInfo;
    v11 = 451;
LABEL_76:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)v10,
      dwFlags);
    goto LABEL_77;
  }
  if ( !v41 || !*(_QWORD *)(v41 + 32) )
  {
    LastError = -2147418113;
    v10 = 2147549183LL;
    v11 = 452;
    goto LABEL_76;
  }
  StringSid = 0;
  if ( ConvertSidToStringSidW(Sid, &StringSid) )
  {
    phProvider = 0;
    v15 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
    LastError = v15;
    if ( v15 >= 0 )
    {
      phkResult = 0;
      while ( 1 )
      {
        hMem = 0;
        *(_QWORD *)v48 = &hMem;
        *(_QWORD *)&v48[2] = 0;
        si128.m128i_i8[0] = 1;
        LastError = NgcEnumUserIdKeys(*(_QWORD *)(v41 + 24), *(_QWORD *)(v41 + 32), &String1, StringSid);
        if ( si128.m128i_i8[0] )
        {
          v16 = **(void ***)v48;
          **(_QWORD **)v48 = *(_QWORD *)&v48[2];
          if ( v16 )
            LocalFree(v16);
        }
        v17 = -1;
        if ( LastError == -2146893782 )
          goto LABEL_31;
        if ( LastError < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1DB,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
            (const char *)(unsigned int)LastError,
            (int)&v48[2]);
          goto LABEL_57;
        }
        phKey = 0;
        v18 = (const WCHAR *)*((_QWORD *)hMem + 4);
        phKey = 0;
        Property = NCryptOpenKey(phProvider, &phKey, v18, 0, 0x40u);
        LastError = Property;
        if ( Property < 0 )
          break;
        *(_DWORD *)pbOutput = 0;
        pcbResult[0] = 0;
        Property = NCryptGetProperty(phKey, L"NgcLogonCapableKey", pbOutput, 4u, pcbResult, 0);
        LastError = Property;
        if ( Property < 0 )
        {
          v32 = 483;
          goto LABEL_53;
        }
        if ( *(_DWORD *)pbOutput )
        {
          v21 = (_WORD *)*((_QWORD *)hMem + 2);
          v22 = -1;
          do
            ++v22;
          while ( v21[v22] );
          if ( v22 > v52 )
          {
            std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v50);
          }
          else
          {
            v23 = v50;
            if ( v52 > 7 )
              v23 = (void **)v50[0];
            v51 = v22;
            v24 = 2 * v22;
            memmove_0(v23, v21, 2 * v22);
            *(_WORD *)((char *)v23 + v24) = 0;
          }
          if ( phKey )
            NCryptFreeObject(phKey);
LABEL_31:
          v25 = hMem;
          v26 = hMem == 0;
          hMem = 0;
          if ( !v26 )
            LocalFree(v25);
          if ( phkResult )
            NgcFreeEnumState();
          if ( phProvider )
            NCryptFreeObject(phProvider);
          if ( StringSid )
            LocalFree(StringSid);
          if ( v41 )
            DsrFreeJoinInfo();
          v27 = 0;
          memset(v48, 0, sizeof(v48));
          si128.m128i_i64[0] = 0;
          phkResult = 0;
          v28 = RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\IdentityStore\\Providers\\{B16898C6-A148-4967-9171-64D755DA8520}",
                  0,
                  0x20019u,
                  &phkResult);
          v29 = v28;
          if ( v28 > 0 )
            v29 = (unsigned __int16)v28 | 0x80070000;
          if ( v29 >= 0 )
          {
            v29 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                    v48,
                    phkResult);
            RegCloseKey(phkResult);
            v27 = *(_WORD **)v48;
          }
          if ( v29 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1EF,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
              (const char *)(unsigned int)v29,
              dwFlagsb);
          std::wstring::operator=(a3, v50);
          if ( v27 && *v27 )
          {
            memset(v53, 0, sizeof(v53));
            do
              ++v17;
            while ( v27[v17] );
            std::wstring::_Construct<1,unsigned short const *>(v53, v27, v17);
            v30 = (int *)v53;
            v31 = 2;
          }
          else
          {
            *(_OWORD *)v48 = 0;
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            LOWORD(v48[0]) = 0;
            v30 = v48;
            v31 = 1;
          }
          std::wstring::operator=(a4, v30);
          if ( (v31 & 2) != 0 )
          {
            v31 &= ~2u;
            std::wstring::~wstring(v53, v34, v35);
          }
          if ( (v31 & 1) != 0 )
            std::wstring::~wstring(v48, v34, v35);
          if ( a5 )
            *a5 = 1;
          if ( v27 )
            CoTaskMemFree(v27);
          std::wstring::~wstring(v50, v34, v35);
          return 0;
        }
        if ( phKey )
          NCryptFreeObject(phKey);
        v20 = hMem;
        hMem = 0;
        if ( v20 )
          LocalFree(v20);
      }
      v32 = 478;
LABEL_53:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
        (const char *)(unsigned int)Property,
        dwFlagsa);
      if ( phKey )
        NCryptFreeObject(phKey);
LABEL_57:
      v33 = hMem;
      hMem = 0;
      if ( v33 )
        LocalFree(v33);
      if ( phkResult )
        NgcFreeEnumState();
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CA,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
        (const char *)(unsigned int)v15,
        dwFlags);
    }
    if ( phProvider )
      NCryptFreeObject(phProvider);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1C7,
                  (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                  v12);
  }
  if ( StringSid )
    LocalFree(StringSid);
LABEL_77:
  if ( v41 )
    DsrFreeJoinInfo();
  std::wstring::~wstring(v50, v13, v14);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180019cd0  mov     [rsp-8+arg_8], rbx
0x180019cd5  push    rbp
0x180019cd6  push    rsi
0x180019cd7  push    rdi
0x180019cd8  push    r12
0x180019cda  push    r13
0x180019cdc  push    r14
0x180019cde  push    r15
0x180019ce0  lea     rbp, [rsp-1Fh]
0x180019ce5  sub     rsp, 0E0h
0x180019cec  mov     rax, cs:__security_cookie
0x180019cf3  xor     rax, rsp
0x180019cf6  mov     [rbp+4Fh+var_40], rax
0x180019cfa  mov     r12, r9
0x180019cfd  mov     r15, r8
0x180019d00  mov     rdi, rcx
0x180019d03  mov     r14, [rbp+4Fh+arg_20]
0x180019d07  xor     r13d, r13d
0x180019d0a  mov     [rbp+4Fh+var_A8], r13d
0x180019d0e  xorps   xmm0, xmm0
0x180019d11  movups  xmmword ptr [rbp+4Fh+var_80], xmm0
0x180019d15  mov     [rbp+4Fh+var_70], r13
0x180019d19  mov     [rbp+4Fh+var_68], 7
0x180019d21  mov     word ptr [rbp+4Fh+var_80], r13w
0x180019d26  mov     [rsp+110h+var_D8], r13
0x180019d2b  lea     rdx, [rsp+110h+var_D8]
0x180019d30  xor     ecx, ecx
0x180019d32  call    cs:__imp_DsrGetJoinInfo
0x180019d38  mov     ebx, eax
0x180019d3a  test    eax, eax
0x180019d3c  jns     short loc_180019D4B
0x180019d3e  mov     r9d, eax
0x180019d41  mov     edx, 1C3h
0x180019d46  jmp     loc_18001A1A0
0x180019d4b  mov     rax, [rsp+110h+var_D8]
0x180019d50  test    rax, rax
0x180019d53  jz      loc_18001A193
0x180019d59  cmp     [rax+20h], r13
0x180019d5d  jz      loc_18001A193
0x180019d63  mov     [rbp+4Fh+StringSid], r13
0x180019d67  lea     rdx, [rbp+4Fh+StringSid]; StringSid
0x180019d6b  mov     rcx, rdi; Sid
0x180019d6e  call    cs:__imp_ConvertSidToStringSidW
0x180019d74  test    eax, eax
0x180019d76  jnz     short loc_180019D94
0x180019d78  mov     rcx, [rbp+57h]; this
0x180019d7c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180019d83  mov     edx, 1C7h; void *
0x180019d88  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019d8d  mov     ebx, eax
0x180019d8f  jmp     loc_18001A10C
0x180019d94  mov     [rbp+4Fh+phProvider], r13
0x180019d98  xor     r8d, r8d; dwFlags
0x180019d9b  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x180019da2  lea     rcx, [rbp+4Fh+phProvider]; phProvider
0x180019da6  call    cs:__imp_NCryptOpenStorageProvider
0x180019dac  mov     ebx, eax
0x180019dae  test    eax, eax
0x180019db0  jns     short loc_180019DCF
0x180019db2  mov     rcx, [rbp+57h]; this
0x180019db6  mov     r9d, eax; char *
0x180019db9  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180019dc0  mov     edx, 1CAh; void *
0x180019dc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019dca  jmp     loc_18001A0FC
0x180019dcf  mov     [rsp+110h+phkResult], r13
0x180019dd4  mov     [rsp+110h+hMem], r13
0x180019dd9  lea     rax, [rsp+110h+hMem]
0x180019dde  mov     qword ptr [rbp+4Fh+var_A0], rax
0x180019de2  mov     qword ptr [rbp+4Fh+var_A0+8], r13
0x180019de6  mov     byte ptr [rbp+4Fh+var_90], 1
0x180019dea  lea     rax, [rsp+110h+phkResult]
0x180019def  mov     qword ptr [rsp+110h+var_E8], rax
0x180019df4  lea     rax, [rbp+4Fh+var_A0+8]
0x180019df8  mov     qword ptr [rsp+110h+dwFlags], rax; int
0x180019dfd  mov     r9, [rbp+4Fh+StringSid]
0x180019e01  lea     r8, String1
0x180019e08  mov     rcx, [rsp+110h+var_D8]
0x180019e0d  mov     rdx, [rcx+20h]
0x180019e11  mov     rcx, [rcx+18h]
0x180019e15  call    cs:__imp_NgcEnumUserIdKeys
0x180019e1b  mov     ebx, eax
0x180019e1d  cmp     byte ptr [rbp+4Fh+var_90], r13b
0x180019e21  jz      short loc_180019E3C
0x180019e23  mov     r8, qword ptr [rbp+4Fh+var_A0]
0x180019e27  mov     rcx, [r8]; hMem
0x180019e2a  mov     rdx, qword ptr [rbp+4Fh+var_A0+8]
0x180019e2e  mov     [r8], rdx
0x180019e31  test    rcx, rcx
0x180019e34  jz      short loc_180019E3C
0x180019e36  call    cs:__imp_LocalFree
0x180019e3c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180019e40  cmp     ebx, 8009002Ah
0x180019e46  jz      loc_180019F56
0x180019e4c  test    ebx, ebx
0x180019e4e  js      loc_18001A0BC
0x180019e54  mov     [rbp+4Fh+phKey], r13
0x180019e58  mov     rax, [rsp+110h+hMem]
0x180019e5d  mov     r8, [rax+20h]; pszKeyName
0x180019e61  mov     [rbp+4Fh+phKey], r13
0x180019e65  mov     [rsp+110h+dwFlags], 40h ; '@'; dwFlags
0x180019e6d  xor     r9d, r9d; dwLegacyKeySpec
0x180019e70  lea     rdx, [rbp+4Fh+phKey]; phKey
0x180019e74  mov     rcx, [rbp+4Fh+phProvider]; hProvider
0x180019e78  call    cs:__imp_NCryptOpenKey
0x180019e7e  mov     ebx, eax
0x180019e80  test    eax, eax
0x180019e82  js      loc_18001A0B5
0x180019e88  mov     dword ptr [rbp+4Fh+pbOutput], r13d
0x180019e8c  mov     [rbp+4Fh+pcbResult], r13d
0x180019e90  mov     [rsp+110h+var_E8], r13d; dwFlags
0x180019e95  lea     rax, [rbp+4Fh+pcbResult]
0x180019e99  mov     qword ptr [rsp+110h+dwFlags], rax; int
0x180019e9e  lea     r9d, [rsi+5]; cbOutput
0x180019ea2  lea     r8, [rbp+4Fh+pbOutput]; pbOutput
0x180019ea6  lea     rdx, aNgclogoncapabl; "NgcLogonCapableKey"
0x180019ead  mov     rcx, [rbp+4Fh+phKey]; hObject
0x180019eb1  call    cs:__imp_NCryptGetProperty
0x180019eb7  mov     ebx, eax
0x180019eb9  test    eax, eax
0x180019ebb  js      loc_18001A08B
0x180019ec1  cmp     dword ptr [rbp+4Fh+pbOutput], r13d
0x180019ec5  jnz     short loc_180019EF5
0x180019ec7  mov     rcx, [rbp+4Fh+phKey]; hObject
0x180019ecb  test    rcx, rcx
0x180019ece  jz      short loc_180019ED7
0x180019ed0  call    cs:__imp_NCryptFreeObject
0x180019ed6  nop
0x180019ed7  mov     rcx, [rsp+110h+hMem]; hMem
0x180019edc  mov     [rsp+110h+hMem], r13
0x180019ee1  test    rcx, rcx
0x180019ee4  jz      loc_180019DD4
0x180019eea  call    cs:__imp_LocalFree
0x180019ef0  jmp     loc_180019DD4
0x180019ef5  mov     rax, [rsp+110h+hMem]
0x180019efa  mov     r9, [rax+10h]
0x180019efe  mov     rdx, rsi
0x180019f01  inc     rdx
0x180019f04  cmp     [r9+rdx*2], r13w
0x180019f09  jnz     short loc_180019F01
0x180019f0b  cmp     rdx, [rbp+4Fh+var_68]
0x180019f0f  ja      short loc_180019F3C
0x180019f11  lea     rdi, [rbp+4Fh+var_80]
0x180019f15  cmp     [rbp+4Fh+var_68], 7
0x180019f1a  cmova   rdi, [rbp+4Fh+var_80]
0x180019f1f  mov     [rbp+4Fh+var_70], rdx
0x180019f23  lea     rbx, [rdx+rdx]
0x180019f27  mov     r8, rbx; Size
0x180019f2a  mov     rdx, r9; Src
0x180019f2d  mov     rcx, rdi; void *
0x180019f30  call    memmove_0
0x180019f35  mov     [rbx+rdi], r13w
0x180019f3a  jmp     short loc_180019F46
0x180019f3c  lea     rcx, [rbp+4Fh+var_80]
0x180019f40  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180019f45  nop
0x180019f46  mov     rcx, [rbp+4Fh+phKey]; hObject
0x180019f4a  test    rcx, rcx
0x180019f4d  jz      short loc_180019F56
0x180019f4f  call    cs:__imp_NCryptFreeObject
0x180019f55  nop
0x180019f56  mov     rcx, [rsp+110h+hMem]; hMem
0x180019f5b  test    rcx, rcx
0x180019f5e  mov     [rsp+110h+hMem], r13
0x180019f63  jz      short loc_180019F6C
0x180019f65  call    cs:__imp_LocalFree
0x180019f6b  nop
0x180019f6c  mov     rcx, [rsp+110h+phkResult]
0x180019f71  test    rcx, rcx
0x180019f74  jz      short loc_180019F7D
0x180019f76  call    cs:__imp_NgcFreeEnumState
0x180019f7c  nop
0x180019f7d  mov     rcx, [rbp+4Fh+phProvider]; hObject
0x180019f81  test    rcx, rcx
0x180019f84  jz      short loc_180019F8D
0x180019f86  call    cs:__imp_NCryptFreeObject
0x180019f8c  nop
0x180019f8d  mov     rcx, [rbp+4Fh+StringSid]; hMem
0x180019f91  test    rcx, rcx
0x180019f94  jz      short loc_180019F9D
0x180019f96  call    cs:__imp_LocalFree
0x180019f9c  nop
0x180019f9d  mov     rcx, [rsp+110h+var_D8]
0x180019fa2  test    rcx, rcx
0x180019fa5  jz      short loc_180019FAD
0x180019fa7  call    cs:__imp_DsrFreeJoinInfo
0x180019fad  mov     rdi, r13
0x180019fb0  mov     qword ptr [rbp+4Fh+var_A0], r13
0x180019fb4  mov     qword ptr [rbp+4Fh+var_A0+8], r13
0x180019fb8  mov     qword ptr [rbp+4Fh+var_90], r13
0x180019fbc  mov     [rsp+110h+phkResult], r13
0x180019fc1  lea     rax, [rsp+110h+phkResult]
0x180019fc6  mov     qword ptr [rsp+110h+dwFlags], rax; int
0x180019fcb  mov     r9d, 20019h; samDesired
0x180019fd1  xor     r8d, r8d; ulOptions
0x180019fd4  lea     rdx, SubKey; "Software\\Microsoft\\IdentityStore\\Pro"...
0x180019fdb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019fe2  call    cs:__imp_RegOpenKeyExW
0x180019fe8  mov     ebx, eax
0x180019fea  test    eax, eax
0x180019fec  jle     short loc_180019FF7
0x180019fee  movzx   ebx, ax
0x180019ff1  or      ebx, 80070000h
0x180019ff7  test    ebx, ebx
0x180019ff9  js      short loc_18001A01A
0x180019ffb  mov     rdx, [rsp+110h+phkResult]
0x18001a000  lea     rcx, [rbp+4Fh+var_A0]
0x18001a004  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *)
0x18001a009  mov     ebx, eax
0x18001a00b  mov     rcx, [rsp+110h+phkResult]; hKey
0x18001a010  call    cs:__imp_RegCloseKey
0x18001a016  mov     rdi, qword ptr [rbp+4Fh+var_A0]
0x18001a01a  mov     rcx, [rbp+57h]; this
0x18001a01e  test    ebx, ebx
0x18001a020  jns     short loc_18001A036
0x18001a022  mov     r9d, ebx; char *
0x18001a025  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001a02c  mov     edx, 1EFh; void *
0x18001a031  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001a036  lea     rdx, [rbp+4Fh+var_80]
0x18001a03a  mov     rcx, r15
0x18001a03d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001a042  test    rdi, rdi
0x18001a045  jz      loc_18001A124
0x18001a04b  cmp     [rdi], r13w
0x18001a04f  jz      loc_18001A124
0x18001a055  xorps   xmm0, xmm0
0x18001a058  movups  [rbp+4Fh+var_60], xmm0
0x18001a05c  xorps   xmm1, xmm1
0x18001a05f  movdqu  [rbp+4Fh+var_50], xmm1
0x18001a064  inc     rsi
0x18001a067  cmp     [rdi+rsi*2], r13w
0x18001a06c  jnz     short loc_18001A064
0x18001a06e  mov     r8, rsi
0x18001a071  mov     rdx, rdi
0x18001a074  lea     rcx, [rbp+4Fh+var_60]
0x18001a078  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001a07d  lea     rdx, [rbp+4Fh+var_60]
0x18001a081  mov     ebx, 2
0x18001a086  jmp     loc_18001A146
0x18001a08b  mov     edx, 1E3h; void *
0x18001a090  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001a097  mov     r9d, eax; char *
0x18001a09a  mov     rcx, [rbp+57h]; this
0x18001a09e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a0a3  nop
0x18001a0a4  mov     rcx, [rbp+4Fh+phKey]; hObject
0x18001a0a8  test    rcx, rcx
0x18001a0ab  jz      short loc_18001A0D5
0x18001a0ad  call    cs:__imp_NCryptFreeObject
0x18001a0b3  jmp     short loc_18001A0D5
0x18001a0b5  mov     edx, 1DEh
0x18001a0ba  jmp     short loc_18001A090
0x18001a0bc  mov     rcx, [rbp+57h]; this
0x18001a0c0  mov     r9d, ebx; char *
0x18001a0c3  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001a0ca  mov     edx, 1DBh; void *
0x18001a0cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a0d4  nop
0x18001a0d5  mov     rcx, [rsp+110h+hMem]; hMem
0x18001a0da  mov     [rsp+110h+hMem], r13
0x18001a0df  test    rcx, rcx
0x18001a0e2  jz      short loc_18001A0EB
0x18001a0e4  call    cs:__imp_LocalFree
0x18001a0ea  nop
0x18001a0eb  mov     rcx, [rsp+110h+phkResult]
0x18001a0f0  test    rcx, rcx
0x18001a0f3  jz      short loc_18001A0FC
0x18001a0f5  call    cs:__imp_NgcFreeEnumState
0x18001a0fb  nop
0x18001a0fc  mov     rcx, [rbp+4Fh+phProvider]; hObject
0x18001a100  test    rcx, rcx
0x18001a103  jz      short loc_18001A10C
0x18001a105  call    cs:__imp_NCryptFreeObject
0x18001a10b  nop
0x18001a10c  mov     rcx, [rbp+4Fh+StringSid]; hMem
0x18001a110  test    rcx, rcx
0x18001a113  jz      loc_18001A1B1
0x18001a119  call    cs:__imp_LocalFree
0x18001a11f  jmp     loc_18001A1B1
0x18001a124  xorps   xmm0, xmm0
0x18001a127  movups  xmmword ptr [rbp+4Fh+var_A0], xmm0
0x18001a12b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001a133  movdqu  [rbp+4Fh+var_90], xmm1
0x18001a138  mov     word ptr [rbp+4Fh+var_A0], r13w
0x18001a13d  lea     rdx, [rbp+4Fh+var_A0]
0x18001a141  mov     ebx, 1
0x18001a146  mov     rcx, r12
0x18001a149  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001a14e  test    bl, 2
0x18001a151  jz      short loc_18001A160
0x18001a153  and     ebx, 0FFFFFFFDh
0x18001a156  lea     rcx, [rbp+4Fh+var_60]
0x18001a15a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a15f  nop
0x18001a160  test    bl, 1
0x18001a163  jz      short loc_18001A16E
0x18001a165  lea     rcx, [rbp+4Fh+var_A0]
0x18001a169  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a16e  test    r14, r14
  ... truncated ...
```
