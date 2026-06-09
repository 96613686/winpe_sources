# EnterpriseInfo::DeviceMeetsDERequirement(void)

- ea: `0x1800258b0`
- end: `0x180025be7`
- name: `?DeviceMeetsDERequirement@EnterpriseInfo@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `823`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008dc0`
- `0x180009f08`
- `0x180009f14`
- `0x180014f2c`
- `0x1800157b8`
- `0x180016748`
- `0x180016db0`
- `0x180019d1c`
- `0x18001daf0`
- `0x18001dcc8`
- `0x180025280`
- `0x1800258b0`
- `0x180027310`
- `0x18002a350`
- `0x18002a474`
- `0x18002ad34`
- `0x180171514`
- `0x180171660`
- `0x1801716fc`
- `0x1801717ec`
- `0x180173780`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025982`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025982`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800259e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800259f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800259e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800259f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025bcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025bcd`

## string_xrefs

- `0x18002597b`: `Fveapi.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnterpriseInfo::DeviceMeetsDERequirement(__int64 a1, __int64 a2)
{
  HMODULE Library; // rax
  __int64 v5; // r8
  char *v6; // rbx
  FARPROC ProcAddress; // rsi
  FARPROC v8; // rbx
  char v9; // r14
  int v10; // r15d
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  __int64 DomainJoined; // rax
  __int64 v14; // rcx
  bool v15; // si
  __int64 v16; // rax
  signed int LastError; // eax
  int v19; // edx
  unsigned int v20; // r8d
  bool v21; // [rsp+60h] [rbp-A0h] BYREF
  bool v22; // [rsp+61h] [rbp-9Fh] BYREF
  bool v23; // [rsp+62h] [rbp-9Eh] BYREF
  bool v24; // [rsp+63h] [rbp-9Dh] BYREF
  int v25[3]; // [rsp+64h] [rbp-9Ch] BYREF
  const int *v26; // [rsp+70h] [rbp-90h] BYREF
  HMODULE hModule; // [rsp+78h] [rbp-88h]
  __int64 v28; // [rsp+80h] [rbp-80h]
  _DWORD v29[3]; // [rsp+88h] [rbp-78h] BYREF
  int v30[3]; // [rsp+94h] [rbp-6Ch]
  _DWORD v31[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v32[2]; // [rsp+A8h] [rbp-58h]
  char *Src[4]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR szFileName[1024]; // [rsp+D0h] [rbp-30h] BYREF

  v28 = a2;
  v29[0] = 20;
  v29[1] = 1;
  v29[2] = 1;
  *(_QWORD *)v30 = 0;
  v24 = 0;
  v21 = 0;
  v25[0] = 0;
  v23 = 0;
  v22 = 0;
  memset_0(szFileName, 0, sizeof(szFileName));
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)a2, L"DEVICE_REQ_UNKNOWN", 0x12u);
  v25[1] = 1;
  v31[0] = 16;
  v31[1] = 1;
  *(_QWORD *)v32 = 0;
  Library = LoadLibraryExW(L"Fveapi.DLL", 0, 0x800u);
  v26 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = Library;
  if ( Library
    && (ProcAddress = GetProcAddress(Library, "FveQueryDeviceEncryptionSupport"),
        v8 = GetProcAddress(hModule, "FveCheckTpmCapability"),
        ProcAddress) )
  {
    v9 = 0;
    v30[1] = 0;
    v10 = ((__int64 (__fastcall *)(_DWORD *))ProcAddress)(v29);
    if ( (v30[1] & 4) != 0 && (!v8 || ((int (__fastcall *)(_DWORD *))v8)(v31) < 0) )
      v32[0] = -2147467259;
    v11 = NgscbCheckPreventDeviceEncryption(&v23);
    if ( (int)NgscbCheckPreventDeviceEncryptionForAad(&v22) >= 0 )
      v12 = v11 >> 31;
    else
      LOBYTE(v12) = 1;
    if ( (int)NgscbCheckIsUpgradedOS(&v24) < 0 )
      LOBYTE(v12) = 1;
    if ( (int)NgscbGetWinReConfiguration(&v21, szFileName) < 0 )
    {
      if ( (int)CEnterpriseInfoV3::IsWinREEnabledFromBCD(&v21) >= 0 )
      {
        if ( (int)CEnterpriseInfoV3::IsOSDriveAlsoRecoveryPartition(v25) < 0 )
          LOBYTE(v12) = 1;
      }
      else
      {
        LOBYTE(v12) = 1;
      }
    }
    else if ( v21 )
    {
      CFveDriveType::CheckIsOSDrive(szFileName, v25);
    }
    DomainJoined = EnterpriseInfo::GetDomainJoined(a1, Src);
    v14 = *(_QWORD *)(DomainJoined + 16);
    if ( *(_QWORD *)(DomainJoined + 24) > 7u )
      DomainJoined = *(_QWORD *)DomainJoined;
    v15 = v14 == 1 && wmemcmp((const wchar_t *)DomainJoined, L"1", 1u) == 0;
    std::wstring::~wstring(Src);
    if ( v15 )
      v9 = !EnterpriseInfo::RecoveryKeyBackUpEnabled();
    v16 = CEnterpriseInfoV3::ComposeStringForDEReq(Src, v12, v23, v22, v9, v30[1], v30[0], v10, v32[0]);
    std::wstring::operator=(a2, v16);
    std::wstring::~wstring(Src);
  }
  else if ( *(_QWORD *)(a2 + 24) < 0x12u )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)a2,
      0x12u,
      v5,
      L"DEVICE_REQ_UNKNOWN");
  }
  else
  {
    v6 = *(char **)a2;
    *(_QWORD *)(a2 + 16) = 18;
    memmove_0(v6, L"DEVICE_REQ_UNKNOWN", 0x24u);
    *((_WORD *)v6 + 18) = 0;
  }
  v26 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v26) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v19, v20);
    JUMPOUT(0x180025BE6LL);
  }
  return a2;
}

```

## disassembly

```asm
0x1800258b0  mov     [rsp-8+arg_10], rbx
0x1800258b5  mov     [rsp-8+arg_18], rsi
0x1800258ba  push    rbp
0x1800258bb  push    rdi
0x1800258bc  push    r12
0x1800258be  push    r14
0x1800258c0  push    r15
0x1800258c2  lea     rbp, [rsp-7E0h]
0x1800258ca  sub     rsp, 8E0h
0x1800258d1  mov     rax, cs:__security_cookie
0x1800258d8  xor     rax, rsp
0x1800258db  mov     [rbp+800h+var_30], rax
0x1800258e2  mov     rdi, rdx
0x1800258e5  mov     r12, rcx
0x1800258e8  mov     [rbp+800h+var_880], rdx
0x1800258ec  mov     [rsp+900h+var_898], 0
0x1800258f4  mov     [rbp+800h+var_878], 14h
0x1800258fb  mov     esi, 1
0x180025900  mov     [rbp+800h+var_874], esi
0x180025903  mov     [rbp+800h+var_870], esi
0x180025906  xor     eax, eax
0x180025908  mov     qword ptr [rbp+800h+var_86C], rax
0x18002590c  mov     [rsp+900h+var_89D], al
0x180025910  mov     [rsp+900h+var_8A0], al
0x180025914  mov     [rsp+900h+var_89C], eax
0x180025918  mov     [rsp+900h+var_89E], al
0x18002591c  mov     [rsp+900h+var_89F], al
0x180025920  mov     ebx, 800h
0x180025925  mov     r8d, ebx; Size
0x180025928  xor     edx, edx; Val
0x18002592a  lea     rcx, [rbp+800h+szFileName]; void *
0x18002592e  call    memset_0
0x180025933  xorps   xmm0, xmm0
0x180025936  movups  xmmword ptr [rdi], xmm0
0x180025939  mov     qword ptr [rdi+10h], 0
0x180025941  mov     qword ptr [rdi+18h], 0
0x180025949  lea     r14d, [rsi+11h]
0x18002594d  mov     r8d, r14d
0x180025950  lea     r15, aDeviceReqUnkno; "DEVICE_REQ_UNKNOWN"
0x180025957  mov     rdx, r15
0x18002595a  mov     rcx, rdi
0x18002595d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180025962  mov     [rsp+900h+var_898], esi
0x180025966  mov     [rbp+800h+var_860], 10h
0x18002596d  mov     [rbp+800h+var_85C], esi
0x180025970  xor     eax, eax
0x180025972  mov     qword ptr [rbp+800h+var_858], rax
0x180025976  mov     r8d, ebx; dwFlags
0x180025979  xor     edx, edx; hFile
0x18002597b  lea     rcx, aFveapiDll_0; "Fveapi.DLL"
0x180025982  call    cs:__imp_LoadLibraryExW
0x180025988  lea     rcx, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18002598f  mov     [rsp+900h+var_890], rcx
0x180025994  mov     [rsp+900h+hModule], rax
0x180025999  test    rax, rax
0x18002599c  jnz     short loc_1800259DA
0x18002599e  cmp     [rdi+18h], r14
0x1800259a2  jb      short loc_1800259C7
0x1800259a4  mov     rbx, [rdi]
0x1800259a7  mov     [rdi+10h], r14
0x1800259ab  mov     r8d, 24h ; '$'; Size
0x1800259b1  mov     rdx, r15; Src
0x1800259b4  mov     rcx, rbx; void *
0x1800259b7  call    memmove_0
0x1800259bc  xor     eax, eax
0x1800259be  mov     [rbx+24h], ax
0x1800259c2  jmp     loc_180025B7D
0x1800259c7  mov     r9, r15
0x1800259ca  mov     rdx, r14
0x1800259cd  mov     rcx, rdi
0x1800259d0  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800259d5  jmp     loc_180025B7D
0x1800259da  lea     rdx, aFvequerydevice; "FveQueryDeviceEncryptionSupport"
0x1800259e1  mov     rcx, rax; hModule
0x1800259e4  call    cs:__imp_GetProcAddress
0x1800259ea  mov     rsi, rax
0x1800259ed  lea     rdx, aFvechecktpmcap; "FveCheckTpmCapability"
0x1800259f4  mov     rcx, [rsp+900h+hModule]; hModule
0x1800259f9  call    cs:__imp_GetProcAddress
0x1800259ff  mov     rbx, rax
0x180025a02  test    rsi, rsi
0x180025a05  jz      short loc_18002599E
0x180025a07  xor     r14b, r14b
0x180025a0a  mov     [rbp+800h+var_86C+4], 0
0x180025a11  lea     rcx, [rbp+800h+var_878]
0x180025a15  mov     rax, rsi
0x180025a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a1d  mov     r15d, eax
0x180025a20  test    byte ptr [rbp+800h+var_86C+4], 4
0x180025a24  jz      short loc_180025A42
0x180025a26  test    rbx, rbx
0x180025a29  jz      short loc_180025A3B
0x180025a2b  lea     rcx, [rbp+800h+var_860]
0x180025a2f  mov     rax, rbx
0x180025a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a37  test    eax, eax
0x180025a39  jns     short loc_180025A42
0x180025a3b  mov     [rbp+800h+var_858], 80004005h
0x180025a42  lea     rcx, [rsp+900h+var_89E]; bool *
0x180025a47  call    ?NgscbCheckPreventDeviceEncryption@@YAJPEA_N@Z; NgscbCheckPreventDeviceEncryption(bool *)
0x180025a4c  mov     ebx, eax
0x180025a4e  lea     rcx, [rsp+900h+var_89F]; bool *
0x180025a53  call    ?NgscbCheckPreventDeviceEncryptionForAad@@YAJPEA_N@Z; NgscbCheckPreventDeviceEncryptionForAad(bool *)
0x180025a58  mov     esi, 1
0x180025a5d  test    eax, eax
0x180025a5f  jns     short loc_180025A66
0x180025a61  mov     bl, sil
0x180025a64  jmp     short loc_180025A69
0x180025a66  shr     ebx, 1Fh
0x180025a69  lea     rcx, [rsp+900h+var_89D]; bool *
0x180025a6e  call    ?NgscbCheckIsUpgradedOS@@YAJPEA_N@Z; NgscbCheckIsUpgradedOS(bool *)
0x180025a73  movzx   ebx, bl
0x180025a76  test    eax, eax
0x180025a78  cmovs   ebx, esi
0x180025a7b  lea     rdx, [rbp+800h+szFileName]; unsigned __int16 *
0x180025a7f  lea     rcx, [rsp+900h+var_8A0]; bool *
0x180025a84  call    ?NgscbGetWinReConfiguration@@YAJPEA_NPEAGK@Z; NgscbGetWinReConfiguration(bool *,ushort *,ulong)
0x180025a89  test    eax, eax
0x180025a8b  js      short loc_180025AA4
0x180025a8d  cmp     [rsp+900h+var_8A0], r14b
0x180025a92  jz      short loc_180025AC9
0x180025a94  lea     rdx, [rsp+900h+var_89C]; int *
0x180025a99  lea     rcx, [rbp+800h+szFileName]; lpszFileName
0x180025a9d  call    ?CheckIsOSDrive@CFveDriveType@@SAJPEBGPEAH@Z; CFveDriveType::CheckIsOSDrive(ushort const *,int *)
0x180025aa2  jmp     short loc_180025AC9
0x180025aa4  lea     rcx, [rsp+900h+var_8A0]; bool *
0x180025aa9  call    ?IsWinREEnabledFromBCD@CEnterpriseInfoV3@@CAJPEA_N@Z; CEnterpriseInfoV3::IsWinREEnabledFromBCD(bool *)
0x180025aae  test    eax, eax
0x180025ab0  jns     short loc_180025AB7
0x180025ab2  mov     bl, sil
0x180025ab5  jmp     short loc_180025AC9
0x180025ab7  lea     rcx, [rsp+900h+var_89C]; int *
0x180025abc  call    ?IsOSDriveAlsoRecoveryPartition@CEnterpriseInfoV3@@CAJPEAH@Z; CEnterpriseInfoV3::IsOSDriveAlsoRecoveryPartition(int *)
0x180025ac1  movzx   ebx, bl
0x180025ac4  test    eax, eax
0x180025ac6  cmovs   ebx, esi
0x180025ac9  lea     rdx, [rbp+800h+Src]
0x180025acd  mov     rcx, r12
0x180025ad0  call    ?GetDomainJoined@EnterpriseInfo@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; EnterpriseInfo::GetDomainJoined(void)
0x180025ad5  mov     rcx, [rax+10h]
0x180025ad9  cmp     qword ptr [rax+18h], 7
0x180025ade  jbe     short loc_180025AE3
0x180025ae0  mov     rax, [rax]
0x180025ae3  cmp     rcx, rsi
0x180025ae6  jz      short loc_180025AED
0x180025ae8  xor     sil, sil
0x180025aeb  jmp     short loc_180025B05
0x180025aed  mov     r8, rsi; N
0x180025af0  lea     rdx, a1_0; "1"
0x180025af7  mov     rcx, rax; S1
0x180025afa  call    wmemcmp
0x180025aff  test    eax, eax
0x180025b01  setz    sil
0x180025b05  lea     rcx, [rbp+800h+Src]
0x180025b09  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025b0e  test    sil, sil
0x180025b11  jz      short loc_180025B1E
0x180025b13  call    ?RecoveryKeyBackUpEnabled@EnterpriseInfo@@CA_NXZ; EnterpriseInfo::RecoveryKeyBackUpEnabled(void)
0x180025b18  test    al, al
0x180025b1a  setz    r14b
0x180025b1e  mov     eax, [rbp+800h+var_858]
0x180025b21  mov     [rsp+900h+var_8A8], eax; int
0x180025b25  mov     [rsp+900h+var_8B0], r15d; int
0x180025b2a  mov     eax, [rbp+800h+var_86C]
0x180025b2d  mov     [rsp+900h+var_8B8], eax; int
0x180025b31  mov     eax, [rbp+800h+var_86C+4]
0x180025b34  mov     [rsp+900h+var_8C0], eax; int
0x180025b38  mov     [rsp+900h+var_8C8], r14b; char
0x180025b3d  mov     al, [rsp+900h+var_89F]
0x180025b41  mov     [rsp+900h+var_8D0], al; char
0x180025b45  mov     al, [rsp+900h+var_89E]
0x180025b49  mov     [rsp+900h+var_8D8], al; char
0x180025b4d  mov     [rsp+900h+var_8E0], bl; char
0x180025b51  mov     r9d, [rsp+900h+var_89C]
0x180025b56  mov     r8b, [rsp+900h+var_8A0]
0x180025b5b  mov     dl, [rsp+900h+var_89D]
0x180025b5f  lea     rcx, [rbp+800h+Src]; Src
0x180025b63  call    ?ComposeStringForDEReq@CEnterpriseInfoV3@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N0H0000KJJJ@Z; CEnterpriseInfoV3::ComposeStringForDEReq(bool,bool,int,bool,bool,bool,bool,ulong,long,long,long)
0x180025b68  mov     rdx, rax
0x180025b6b  mov     rcx, rdi
0x180025b6e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180025b73  lea     rcx, [rbp+800h+Src]
0x180025b77  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025b7c  nop
0x180025b7d  lea     rax, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180025b84  mov     [rsp+900h+var_890], rax
0x180025b89  cmp     [rsp+900h+hModule], 0
0x180025b8f  jz      short loc_180025B9F
0x180025b91  lea     rcx, [rsp+900h+var_890]
0x180025b96  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180025b9b  test    al, al
0x180025b9d  jz      short loc_180025BCD
0x180025b9f  mov     rax, rdi
0x180025ba2  mov     rcx, [rbp+800h+var_30]
0x180025ba9  xor     rcx, rsp; StackCookie
0x180025bac  call    __security_check_cookie
0x180025bb1  lea     r11, [rsp+900h+var_20]
0x180025bb9  mov     rbx, [r11+40h]
0x180025bbd  mov     rsi, [r11+48h]
0x180025bc1  mov     rsp, r11
0x180025bc4  pop     r15
0x180025bc6  pop     r14
0x180025bc8  pop     r12
0x180025bca  pop     rdi
0x180025bcb  pop     rbp
0x180025bcc  retn
0x180025bcd  call    cs:__imp_GetLastError
0x180025bd3  test    eax, eax
0x180025bd5  jle     short loc_180025BDF
0x180025bd7  movzx   eax, ax
0x180025bda  or      eax, 80070000h
0x180025bdf  mov     ecx, eax; this
0x180025be1  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
