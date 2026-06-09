# WAS_SQM_WRITER::PopulateGlobalData(INativeConfigurationSystem *,SQM_GLOBAL_DATA *)

- ea: `0x180055e1c`
- end: `0x180056174`
- name: `?PopulateGlobalData@WAS_SQM_WRITER@@CAXPEAVINativeConfigurationSystem@@PEAUSQM_GLOBAL_DATA@@@Z`
- size: `856`
- prototype: `void __fastcall(struct INativeConfigurationSystem *, struct SQM_GLOBAL_DATA *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180055bfc`

## callees

- `0x18005561c`
- `0x180055e1c`
- `0x18006101a`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180055faf`
- `msvcrt!_wcsicmp` at `0x180055faf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055f65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800560d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055f65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800560d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056103`
- `OLEAUT32!__imp_VariantInit` at `0x180056025`
- `OLEAUT32!__imp_VariantInit` at `0x180056025`
- `OLEAUT32!__imp_VariantClear` at `0x18005605a`
- `OLEAUT32!__imp_VariantClear` at `0x18005605a`
- `logoncli!NetGetDCName` at `0x180055f3b`
- `logoncli!NetGetDCName` at `0x180055f3b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180055f5b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180055f96`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180055f5b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180055f96`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180056146`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180056146`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180055e7e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180055e7e`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180055f7a`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180055f7a`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800560f4`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800560f4`
- `CRYPT32!CertCloseStore` at `0x180056134`
- `CRYPT32!CertCloseStore` at `0x180056134`
- `CRYPT32!CertOpenStore` at `0x1800560c3`
- `CRYPT32!CertOpenStore` at `0x1800560c3`
- `netutils!NetApiBufferFree` at `0x180055fc5`
- `netutils!NetApiBufferFree` at `0x180055fc5`

## string_xrefs

- `0x180055ea0`: `configurationRedirection`

## pseudocode

```c
void __fastcall WAS_SQM_WRITER::PopulateGlobalData(struct INativeConfigurationSystem *a1, struct SQM_GLOBAL_DATA *a2)
{
  __int64 v4; // rax
  int (__fastcall *v5)(struct INativeConfigurationSystem *, const wchar_t *, const wchar_t *, __int64 *, _QWORD, _QWORD, int); // rax
  const unsigned __int16 *v6; // rdx
  const unsigned __int16 *v7; // r8
  int v8; // r15d
  HCERTSTORE v9; // r14
  signed int v10; // eax
  signed int v11; // ebx
  const CERT_CONTEXT *v12; // rax
  int i; // esi
  signed int LastError; // eax
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nSize; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+58h] [rbp-A8h] BYREF
  LPBYTE bufptr; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v22[32]; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR lpBuffer; // [rsp+A0h] [rbp-60h]
  unsigned int v24; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v25[64]; // [rsp+C0h] [rbp-40h] BYREF

  v17 = 0;
  v15 = 0;
  bufptr = 0;
  memset_0(v25, 0, sizeof(v25));
  STRU::STRU((STRU *)v22, v25, 0x40u);
  v4 = *(_QWORD *)a1;
  nSize = 0;
  v5 = *(int (__fastcall **)(struct INativeConfigurationSystem *, const wchar_t *, const wchar_t *, __int64 *, _QWORD, _QWORD, int))(v4 + 112);
  v19 = 0;
  v18 = 0;
  if ( v5(a1, L"configurationRedirection", L"MACHINE/REDIRECTION", &v17, 0, 0, 42) >= 0
    && (*(int (__fastcall **)(__int64, const unsigned __int16 *, int *, _QWORD, _QWORD))(*(_QWORD *)v17 + 72LL))(
         v17,
         L"enabled",
         &v15,
         0,
         0) >= 0 )
  {
    *(_DWORD *)a2 = v15;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  v15 = 0;
  if ( (int)WAS_SQM_WRITER::GetBooleanPropertyFromAllLocations(a1, v6, v7, &v15) >= 0 )
    *((_DWORD *)a2 + 2) = v15;
  if ( !NetGetDCName(0, 0, &bufptr) )
  {
    nSize = v24 >> 1;
    if ( !GetComputerNameW(lpBuffer, &nSize) && GetLastError() == 111 && (int)STRU::Resize((STRU *)v22, 2 * nSize) >= 0 )
    {
      nSize = v24 >> 1;
      GetComputerNameW(lpBuffer, &nSize);
    }
    if ( *lpBuffer && !_wcsicmp((const wchar_t *)bufptr + 2, lpBuffer) )
      *((_DWORD *)a2 + 1) = 1;
    NetApiBufferFree(bufptr);
  }
  if ( (*(int (__fastcall **)(struct INativeConfigurationSystem *, const wchar_t *, __int64 *, _QWORD))(*(_QWORD *)a1 + 88LL))(
         a1,
         L"MACHINE/WEBROOT/APPHOST",
         &v18,
         0) >= 0 )
  {
    if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v18)(v18, &IID_IAppHostConfigFile, &v19) >= 0 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v19 + 56LL))(
             v19,
             L"fileSize",
             &pvarg) >= 0 )
        *((_QWORD *)a2 + 2) = pvarg.llVal;
      VariantClear(&pvarg);
    }
    if ( v18 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v18 = 0;
    }
    if ( v19 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v19 = 0;
    }
  }
  v8 = 0;
  *((_DWORD *)a2 + 6) = *((_DWORD *)g_pWebAdminService + 167);
  v9 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x2C000u, L"WebHosting");
  if ( v9 )
  {
    v12 = 0;
    for ( i = 0; ; ++i )
    {
      v12 = CertEnumCertificatesInStore(v9, v12);
      if ( !v12 )
        break;
    }
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError == -2146885628 || LastError == 18 )
    {
      v11 = 0;
      v8 = i;
    }
    else if ( LastError > 0 )
    {
      v11 = (unsigned __int16)LastError | 0x80070000;
    }
    CertCloseStore(v9, 1u);
  }
  else
  {
    v10 = GetLastError();
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
  }
  if ( v11 >= 0 )
    *((_DWORD *)a2 + 7) = v8;
  STRU::~STRU((STRU *)v22);
}

```

## disassembly

```asm
0x180055e1c  mov     [rsp-8+arg_10], rbx
0x180055e21  mov     [rsp-8+arg_18], rsi
0x180055e26  push    rbp
0x180055e27  push    rdi
0x180055e28  push    r12
0x180055e2a  push    r14
0x180055e2c  push    r15
0x180055e2e  lea     rbp, [rsp-50h]
0x180055e33  sub     rsp, 150h
0x180055e3a  mov     rax, cs:__security_cookie
0x180055e41  xor     rax, rsp
0x180055e44  mov     [rbp+70h+var_30], rax
0x180055e48  xor     r12d, r12d
0x180055e4b  mov     rdi, rdx
0x180055e4e  mov     rbx, rcx
0x180055e51  mov     [rsp+170h+var_128], r12
0x180055e56  xor     edx, edx; Val
0x180055e58  mov     [rsp+170h+var_130], r12d
0x180055e5d  lea     rcx, [rbp+70h+var_B0]; void *
0x180055e61  mov     [rsp+170h+bufptr], r12
0x180055e66  mov     r8d, 80h; Size
0x180055e6c  call    memset_0
0x180055e71  lea     r8d, [r12+40h]
0x180055e76  lea     rdx, [rbp+70h+var_B0]
0x180055e7a  lea     rcx, [rbp+70h+var_F0]
0x180055e7e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180055e84  mov     rax, [rbx]
0x180055e87  lea     r9, [rsp+170h+var_128]
0x180055e8c  mov     [rsp+170h+var_140], 2Ah ; '*'
0x180055e94  lea     r8, String2; "MACHINE/REDIRECTION"
0x180055e9b  mov     [rsp+170h+var_148], r12
0x180055ea0  lea     rdx, aConfigurationr; "configurationRedirection"
0x180055ea7  mov     rcx, rbx
0x180055eaa  mov     [rsp+170h+nSize], r12d
0x180055eaf  mov     rax, [rax+70h]
0x180055eb3  mov     [rsp+170h+var_118], r12
0x180055eb8  mov     [rsp+170h+var_120], r12
0x180055ebd  mov     [rsp+170h+pvPara], r12
0x180055ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055ec7  test    eax, eax
0x180055ec9  js      short loc_180055EFA
0x180055ecb  mov     rcx, [rsp+170h+var_128]
0x180055ed0  lea     r8, [rsp+170h+var_130]
0x180055ed5  xor     r9d, r9d
0x180055ed8  mov     [rsp+170h+pvPara], r12
0x180055edd  lea     rdx, aEnabled; "enabled"
0x180055ee4  mov     rax, [rcx]
0x180055ee7  mov     rax, [rax+48h]
0x180055eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055ef0  test    eax, eax
0x180055ef2  js      short loc_180055EFA
0x180055ef4  mov     eax, [rsp+170h+var_130]
0x180055ef8  mov     [rdi], eax
0x180055efa  mov     rcx, [rsp+170h+var_128]
0x180055eff  test    rcx, rcx
0x180055f02  jz      short loc_180055F15
0x180055f04  mov     rax, [rcx]
0x180055f07  mov     rax, [rax+10h]
0x180055f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f10  mov     [rsp+170h+var_128], r12
0x180055f15  lea     r9, [rsp+170h+var_130]; int *
0x180055f1a  mov     [rsp+170h+var_130], r12d
0x180055f1f  mov     rcx, rbx; struct INativeConfigurationSystem *
0x180055f22  call    ?GetBooleanPropertyFromAllLocations@WAS_SQM_WRITER@@CAJPEAVINativeConfigurationSystem@@PEBG1PEAH@Z; WAS_SQM_WRITER::GetBooleanPropertyFromAllLocations(INativeConfigurationSystem *,ushort const *,ushort const *,int *)
0x180055f27  test    eax, eax
0x180055f29  js      short loc_180055F32
0x180055f2b  mov     eax, [rsp+170h+var_130]
0x180055f2f  mov     [rdi+8], eax
0x180055f32  lea     r8, [rsp+170h+bufptr]; bufptr
0x180055f37  xor     edx, edx; domainname
0x180055f39  xor     ecx, ecx; servername
0x180055f3b  call    cs:__imp_NetGetDCName
0x180055f41  test    eax, eax
0x180055f43  jnz     loc_180055FCB
0x180055f49  mov     eax, [rbp+70h+var_C8]
0x180055f4c  lea     rdx, [rsp+170h+nSize]; nSize
0x180055f51  mov     rcx, [rbp+70h+lpBuffer]; lpBuffer
0x180055f55  shr     eax, 1
0x180055f57  mov     [rsp+170h+nSize], eax
0x180055f5b  call    cs:__imp_GetComputerNameW
0x180055f61  test    eax, eax
0x180055f63  jnz     short loc_180055F9C
0x180055f65  call    cs:__imp_GetLastError
0x180055f6b  cmp     eax, 6Fh ; 'o'
0x180055f6e  jnz     short loc_180055F9C
0x180055f70  mov     edx, [rsp+170h+nSize]
0x180055f74  lea     rcx, [rbp+70h+var_F0]
0x180055f78  add     edx, edx
0x180055f7a  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180055f80  test    eax, eax
0x180055f82  js      short loc_180055F9C
0x180055f84  mov     eax, [rbp+70h+var_C8]
0x180055f87  lea     rdx, [rsp+170h+nSize]; nSize
0x180055f8c  mov     rcx, [rbp+70h+lpBuffer]; lpBuffer
0x180055f90  shr     eax, 1
0x180055f92  mov     [rsp+170h+nSize], eax
0x180055f96  call    cs:__imp_GetComputerNameW
0x180055f9c  mov     rdx, [rbp+70h+lpBuffer]; String2
0x180055fa0  cmp     [rdx], r12w
0x180055fa4  jz      short loc_180055FC0
0x180055fa6  mov     rcx, [rsp+170h+bufptr]
0x180055fab  add     rcx, 4; String1
0x180055faf  call    cs:__imp__wcsicmp
0x180055fb5  test    eax, eax
0x180055fb7  jnz     short loc_180055FC0
0x180055fb9  mov     dword ptr [rdi+4], 1
0x180055fc0  mov     rcx, [rsp+170h+bufptr]; Buffer
0x180055fc5  call    cs:__imp_NetApiBufferFree
0x180055fcb  mov     rax, [rbx]
0x180055fce  lea     r8, [rsp+170h+var_120]
0x180055fd3  xor     r9d, r9d
0x180055fd6  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180055fdd  mov     rcx, rbx
0x180055fe0  mov     rax, [rax+58h]
0x180055fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fe9  test    eax, eax
0x180055feb  js      loc_180056096
0x180055ff1  mov     rcx, [rsp+170h+var_120]
0x180055ff6  lea     r8, [rsp+170h+var_118]
0x180055ffb  lea     rdx, IID_IAppHostConfigFile
0x180056002  mov     rax, [rcx]
0x180056005  mov     rax, [rax]
0x180056008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005600d  test    eax, eax
0x18005600f  js      short loc_180056060
0x180056011  xorps   xmm0, xmm0
0x180056014  lea     rcx, [rsp+170h+pvarg]; pvarg
0x180056019  xor     eax, eax
0x18005601b  movups  xmmword ptr [rsp+170h+pvarg], xmm0
0x180056020  mov     qword ptr [rsp+170h+pvarg+10h], rax
0x180056025  call    cs:__imp_VariantInit
0x18005602b  mov     rcx, [rsp+170h+var_118]
0x180056030  lea     r8, [rsp+170h+pvarg]
0x180056035  lea     rdx, aFilesize; "fileSize"
0x18005603c  mov     rax, [rcx]
0x18005603f  mov     rax, [rax+38h]
0x180056043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056048  test    eax, eax
0x18005604a  js      short loc_180056055
0x18005604c  mov     rax, qword ptr [rsp+170h+pvarg+8]
0x180056051  mov     [rdi+10h], rax
0x180056055  lea     rcx, [rsp+170h+pvarg]; pvarg
0x18005605a  call    cs:__imp_VariantClear
0x180056060  mov     rcx, [rsp+170h+var_120]
0x180056065  test    rcx, rcx
0x180056068  jz      short loc_18005607B
0x18005606a  mov     rax, [rcx]
0x18005606d  mov     rax, [rax+10h]
0x180056071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056076  mov     [rsp+170h+var_120], r12
0x18005607b  mov     rcx, [rsp+170h+var_118]
0x180056080  test    rcx, rcx
0x180056083  jz      short loc_180056096
0x180056085  mov     rax, [rcx]
0x180056088  mov     rax, [rax+10h]
0x18005608c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056091  mov     [rsp+170h+var_118], r12
0x180056096  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18005609d  xor     edx, edx; dwEncodingType
0x18005609f  mov     r9d, 2C000h; dwFlags
0x1800560a5  xor     r8d, r8d; hCryptProv
0x1800560a8  mov     r15d, r12d
0x1800560ab  mov     ecx, [rax+29Ch]
0x1800560b1  lea     rax, aWebhosting; "WebHosting"
0x1800560b8  mov     [rdi+18h], ecx
0x1800560bb  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x1800560be  mov     [rsp+170h+pvPara], rax; pvPara
0x1800560c3  call    cs:__imp_CertOpenStore
0x1800560c9  mov     r14, rax
0x1800560cc  test    rax, rax
0x1800560cf  jnz     short loc_1800560E8
0x1800560d1  call    cs:__imp_GetLastError
0x1800560d7  mov     ebx, eax
0x1800560d9  test    eax, eax
0x1800560db  jle     short loc_18005613A
0x1800560dd  movzx   ebx, ax
0x1800560e0  or      ebx, 80070000h
0x1800560e6  jmp     short loc_18005613A
0x1800560e8  mov     rax, r12
0x1800560eb  mov     esi, r12d
0x1800560ee  mov     rdx, rax; pPrevCertContext
0x1800560f1  mov     rcx, r14; hCertStore
0x1800560f4  call    cs:__imp_CertEnumCertificatesInStore
0x1800560fa  test    rax, rax
0x1800560fd  jz      short loc_180056103
0x1800560ff  inc     esi
0x180056101  jmp     short loc_1800560EE
0x180056103  call    cs:__imp_GetLastError
0x180056109  mov     ebx, eax
0x18005610b  cmp     eax, 80092004h
0x180056110  jz      short loc_180056126
0x180056112  cmp     eax, 12h
0x180056115  jz      short loc_180056126
0x180056117  test    eax, eax
0x180056119  jle     short loc_18005612C
0x18005611b  movzx   ebx, ax
0x18005611e  or      ebx, 80070000h
0x180056124  jmp     short loc_18005612C
0x180056126  mov     ebx, r12d
0x180056129  mov     r15d, esi
0x18005612c  mov     edx, 1; dwFlags
0x180056131  mov     rcx, r14; hCertStore
0x180056134  call    cs:__imp_CertCloseStore
0x18005613a  test    ebx, ebx
0x18005613c  js      short loc_180056142
0x18005613e  mov     [rdi+1Ch], r15d
0x180056142  lea     rcx, [rbp+70h+var_F0]
0x180056146  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18005614c  mov     rcx, [rbp+70h+var_30]
0x180056150  xor     rcx, rsp; StackCookie
0x180056153  call    __security_check_cookie
0x180056158  lea     r11, [rsp+170h+var_20]
0x180056160  mov     rbx, [r11+40h]
0x180056164  mov     rsi, [r11+48h]
0x180056168  mov     rsp, r11
0x18005616b  pop     r15
0x18005616d  pop     r14
0x18005616f  pop     r12
0x180056171  pop     rdi
0x180056172  pop     rbp
0x180056173  retn
```
