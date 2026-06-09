# BuildCertificateStoreFromKeyInfo(_CRYPT_XML_KEY_INFO const *)

- ea: `0x18003d1c4`
- end: `0x18003d388`
- name: `?BuildCertificateStoreFromKeyInfo@@YAPEAXPEBU_CRYPT_XML_KEY_INFO@@@Z`
- size: `452`
- prototype: `void *__fastcall(const _CRYPT_XML_KEY_INFO *pKeyInfo)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003e2ec`

## callees

- `0x1800032f4`
- `0x180012770`
- `0x180012bc8`
- `0x180013bdc`
- `0x18003d1c4`
- `0x1800677d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d1fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d2eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d1fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d2eb`
- `CRYPT32!CertDuplicateStore` at `0x18003d352`
- `CRYPT32!CertDuplicateStore` at `0x18003d352`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18003d2d9`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18003d2d9`
- `CRYPT32!CertOpenStore` at `0x18003d1ef`
- `CRYPT32!CertOpenStore` at `0x18003d1ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HCERTSTORE __fastcall BuildCertificateStoreFromKeyInfo(const _CRYPT_XML_KEY_INFO *pKeyInfo)
{
  HCERTSTORE v2; // rsi
  signed int LastError; // eax
  unsigned int v4; // ebx
  unsigned int i; // ebx
  unsigned __int64 v6; // rdi
  __int64 j; // rbp
  _CRYPT_XML_KEY_INFO_ITEM *rgKeyInfo; // rcx
  __int64 v9; // rax
  signed int v10; // eax
  unsigned int v11; // ebx
  HCERTSTORE v12; // rbx
  HrException pExceptionObject; // [rsp+30h] [rbp-58h] BYREF
  HrException v15; // [rsp+50h] [rbp-38h] BYREF

  v2 = CertOpenStore((LPCSTR)2, 1u, 0, 0, 0);
  if ( !v2 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x28u, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids, v4);
    }
    HrException::HrException(&pExceptionObject, v4);
    throw &pExceptionObject;
  }
  LOBYTE(pExceptionObject.__vftable) = 0;
  pExceptionObject._Data._What = (const char *)CertCloseStoreWrapper;
  *(_QWORD *)&pExceptionObject._Data._DoFree = v2;
  for ( i = 0; i < pKeyInfo->cKeyInfo; ++i )
  {
    v6 = (unsigned __int64)i << 7;
    if ( *(unsigned int *)((char *)&pKeyInfo->rgKeyInfo->dwType + v6) == 4 )
    {
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        rgKeyInfo = pKeyInfo->rgKeyInfo;
        if ( (unsigned int)j >= *(unsigned int *)((char *)&rgKeyInfo->KeyValue.$9F3A834B75543E45CE5F350DA7172E8F::dwType
                                                + v6) )
          break;
        v9 = *(__int64 *)((char *)&rgKeyInfo->KeyValue.ECDSAKeyValue.wszNamedCurve + v6);
        if ( *(_DWORD *)(v9 + 24 * j) == 4
          && !CertAddEncodedCertificateToStore(
                v2,
                1u,
                *(const BYTE **)(v9 + 24 * j + 16),
                *(_DWORD *)(v9 + 24 * j + 8),
                1u,
                0) )
        {
          v10 = GetLastError();
          v11 = v10;
          if ( v10 > 0 )
            v11 = (unsigned __int16)v10 | 0x80070000;
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x29u, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids, v11);
          }
          HrException::HrException(&v15, v11);
          throw &v15;
        }
      }
    }
  }
  v12 = CertDuplicateStore(v2);
  if ( !v12 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>((ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> *)&pExceptionObject);
  return v12;
}

```

## disassembly

```asm
0x18003d1c4  mov     [rsp+arg_8], rbx
0x18003d1c9  mov     [rsp+arg_10], rbp
0x18003d1ce  push    rsi
0x18003d1cf  push    rdi
0x18003d1d0  push    r14
0x18003d1d2  sub     rsp, 70h
0x18003d1d6  mov     r14, pKeyInfo
0x18003d1d9  mov     [rsp+88h+pvPara], 0; pvPara
0x18003d1e2  xor     r9d, r9d; dwFlags
0x18003d1e5  xor     r8d, r8d; hCryptProv
0x18003d1e8  lea     edx, [r9+1]; dwEncodingType
0x18003d1ec  lea     ecx, [rdx+1]; lpszStoreProvider
0x18003d1ef  call    cs:__imp_CertOpenStore
0x18003d1f5  mov     rsi, rax
0x18003d1f8  test    rax, rax
0x18003d1fb  jnz     short loc_18003D261
0x18003d1fd  call    cs:__imp_GetLastError
0x18003d203  mov     ebx, eax
0x18003d205  test    eax, eax
0x18003d207  jle     short loc_18003D212
0x18003d209  movzx   ebx, ax
0x18003d20c  or      ebx, 80070000h
0x18003d212  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003d219  mov     pKeyInfo, cs:WPP_GLOBAL_Control
0x18003d220  cmp     pKeyInfo, rax
0x18003d223  jz      short loc_18003D243
0x18003d225  test    byte ptr [pKeyInfo+1Ch], 10h
0x18003d229  jz      short loc_18003D243
0x18003d22b  mov     edx, 28h ; '('; id
0x18003d230  mov     r9d, ebx; _a1
0x18003d233  lea     r8, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids; TraceGuid
0x18003d23a  mov     pKeyInfo, [pKeyInfo+10h]; Logger
0x18003d23e  call    WPP_SF_d
0x18003d243  mov     edx, ebx; ErrorCode
0x18003d245  lea     pKeyInfo, [rsp+88h+pExceptionObject]; this
0x18003d24a  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x18003d24f  lea     rdx, _TI2?AVHrException@@; pThrowInfo
0x18003d256  lea     pKeyInfo, [rsp+88h+pExceptionObject]; pExceptionObject
0x18003d25b  call    _CxxThrowException_0
0x18003d261  mov     byte ptr [rsp+88h+pExceptionObject.__vftable], 0
0x18003d266  lea     rax, ?CertCloseStoreWrapper@@YAHPEAX@Z; CertCloseStoreWrapper(void *)
0x18003d26d  mov     [rsp+88h+pExceptionObject._Data._What], rax
0x18003d272  mov     qword ptr [rsp+88h+pExceptionObject._Data._DoFree], rsi
0x18003d277  xor     ebx, ebx
0x18003d279  cmp     ebx, [r14+10h]
0x18003d27d  jnb     loc_18003D34F
0x18003d283  mov     edi, ebx
0x18003d285  shl     rdi, 7
0x18003d289  mov     rax, [r14+18h]
0x18003d28d  cmp     dword ptr [rdi+rax], 4
0x18003d291  jnz     short loc_18003D2E7
0x18003d293  xor     ebp, ebp
0x18003d295  mov     pKeyInfo, [r14+18h]
0x18003d299  cmp     ebp, [pKeyInfo+rdi+8]
0x18003d29d  jnb     short loc_18003D2E7
0x18003d29f  lea     r8, ds:0[rbp*2]
0x18003d2a7  add     r8, rbp
0x18003d2aa  mov     rax, [pKeyInfo+rdi+10h]
0x18003d2af  cmp     dword ptr [rax+r8*8], 4
0x18003d2b4  jnz     short loc_18003D2E3
0x18003d2b6  mov     [rsp+88h+ppCertContext], 0; ppCertContext
0x18003d2bf  mov     dword ptr [rsp+88h+pvPara], 1; dwAddDisposition
0x18003d2c7  mov     r9d, [rax+r8*8+8]; cbCertEncoded
0x18003d2cc  mov     r8, [rax+r8*8+10h]; pbCertEncoded
0x18003d2d1  mov     edx, 1; dwCertEncodingType
0x18003d2d6  mov     pKeyInfo, rsi; hCertStore
0x18003d2d9  call    cs:__imp_CertAddEncodedCertificateToStore
0x18003d2df  test    eax, eax
0x18003d2e1  jz      short loc_18003D2EB
0x18003d2e3  inc     ebp
0x18003d2e5  jmp     short loc_18003D295
0x18003d2e7  inc     ebx
0x18003d2e9  jmp     short loc_18003D279
0x18003d2eb  call    cs:__imp_GetLastError
0x18003d2f1  mov     ebx, eax
0x18003d2f3  test    eax, eax
0x18003d2f5  jle     short loc_18003D300
0x18003d2f7  movzx   ebx, ax
0x18003d2fa  or      ebx, 80070000h
0x18003d300  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003d307  mov     pKeyInfo, cs:WPP_GLOBAL_Control
0x18003d30e  cmp     pKeyInfo, rax
0x18003d311  jz      short loc_18003D331
0x18003d313  test    byte ptr [pKeyInfo+1Ch], 10h
0x18003d317  jz      short loc_18003D331
0x18003d319  mov     edx, 29h ; ')'; id
0x18003d31e  mov     r9d, ebx; _a1
0x18003d321  lea     r8, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids; TraceGuid
0x18003d328  mov     pKeyInfo, [pKeyInfo+10h]; Logger
0x18003d32c  call    WPP_SF_d
0x18003d331  mov     edx, ebx; ErrorCode
0x18003d333  lea     pKeyInfo, [rsp+88h+var_38]; this
0x18003d338  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x18003d33d  lea     rdx, _TI2?AVHrException@@; pThrowInfo
0x18003d344  lea     pKeyInfo, [rsp+88h+var_38]; pExceptionObject
0x18003d349  call    _CxxThrowException_0
0x18003d34f  mov     pKeyInfo, rsi; hCertStore
0x18003d352  call    cs:__imp_CertDuplicateStore
0x18003d358  mov     rbx, rax
0x18003d35b  test    rax, rax
0x18003d35e  jnz     short loc_18003D366
0x18003d360  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!!hDuplicatedStore", "CertDuplicateStore only increases a refcount and shouldn't return NULL")
0x18003d365  nop
0x18003d366  lea     pKeyInfo, [rsp+88h+pExceptionObject]; j
0x18003d36b  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x18003d370  mov     rax, rbx
0x18003d373  lea     r11, [rsp+88h+var_18]
0x18003d378  mov     rbx, [r11+28h]
0x18003d37c  mov     rbp, [r11+30h]
0x18003d380  mov     rsp, r11
0x18003d383  pop     r14
0x18003d385  pop     rdi
0x18003d386  pop     rsi
0x18003d387  retn
```
