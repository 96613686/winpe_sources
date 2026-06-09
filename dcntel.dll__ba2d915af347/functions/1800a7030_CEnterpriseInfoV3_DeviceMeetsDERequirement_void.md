# CEnterpriseInfoV3::DeviceMeetsDERequirement(void)

- ea: `0x1800a7030`
- end: `0x1800a7367`
- name: `?DeviceMeetsDERequirement@CEnterpriseInfoV3@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
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
- `0x180027310`
- `0x18002a350`
- `0x18002a474`
- `0x1800a7030`
- `0x1800a79f0`
- `0x180171514`
- `0x180171660`
- `0x1801716fc`
- `0x1801717ec`
- `0x180173780`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a7102`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a7102`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a7164`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a7179`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a7164`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a7179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a734d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a734d`

## string_xrefs

- `0x1800a70fb`: `Fveapi.DLL`

## pseudocode

```c
__int64 __fastcall CEnterpriseInfoV3::DeviceMeetsDERequirement(__int64 a1, __int64 a2)
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
      v9 = !CEnterpriseInfoV3::RecoveryKeyBackUpEnabled();
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
    JUMPOUT(0x1800A7366LL);
  }
  return a2;
}

```

## disassembly

```asm
0x1800a7030  mov     [rsp-8+arg_10], rbx
0x1800a7035  mov     [rsp-8+arg_18], rsi
0x1800a703a  push    rbp
0x1800a703b  push    rdi
0x1800a703c  push    r12
0x1800a703e  push    r14
0x1800a7040  push    r15
0x1800a7042  lea     rbp, [rsp-7E0h]
0x1800a704a  sub     rsp, 8E0h
0x1800a7051  mov     rax, cs:__security_cookie
0x1800a7058  xor     rax, rsp
0x1800a705b  mov     [rbp+800h+var_30], rax
0x1800a7062  mov     rdi, rdx
0x1800a7065  mov     r12, rcx
0x1800a7068  mov     [rbp+800h+var_880], rdx
0x1800a706c  mov     [rsp+900h+var_898], 0
0x1800a7074  mov     [rbp+800h+var_878], 14h
0x1800a707b  mov     esi, 1
0x1800a7080  mov     [rbp+800h+var_874], esi
0x1800a7083  mov     [rbp+800h+var_870], esi
0x1800a7086  xor     eax, eax
0x1800a7088  mov     qword ptr [rbp+800h+var_86C], rax
0x1800a708c  mov     [rsp+900h+var_89D], al
0x1800a7090  mov     [rsp+900h+var_8A0], al
0x1800a7094  mov     [rsp+900h+var_89C], eax
0x1800a7098  mov     [rsp+900h+var_89E], al
0x1800a709c  mov     [rsp+900h+var_89F], al
0x1800a70a0  mov     ebx, 800h
0x1800a70a5  mov     r8d, ebx; Size
0x1800a70a8  xor     edx, edx; Val
0x1800a70aa  lea     rcx, [rbp+800h+szFileName]; void *
0x1800a70ae  call    memset_0
0x1800a70b3  xorps   xmm0, xmm0
0x1800a70b6  movups  xmmword ptr [rdi], xmm0
0x1800a70b9  mov     qword ptr [rdi+10h], 0
0x1800a70c1  mov     qword ptr [rdi+18h], 0
0x1800a70c9  lea     r14d, [rsi+11h]
0x1800a70cd  mov     r8d, r14d
0x1800a70d0  lea     r15, aDeviceReqUnkno; "DEVICE_REQ_UNKNOWN"
0x1800a70d7  mov     rdx, r15
0x1800a70da  mov     rcx, rdi
0x1800a70dd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800a70e2  mov     [rsp+900h+var_898], esi
0x1800a70e6  mov     [rbp+800h+var_860], 10h
0x1800a70ed  mov     [rbp+800h+var_85C], esi
0x1800a70f0  xor     eax, eax
0x1800a70f2  mov     qword ptr [rbp+800h+var_858], rax
0x1800a70f6  mov     r8d, ebx; dwFlags
0x1800a70f9  xor     edx, edx; hFile
0x1800a70fb  lea     rcx, aFveapiDll_0; "Fveapi.DLL"
0x1800a7102  call    cs:__imp_LoadLibraryExW
0x1800a7108  lea     rcx, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800a710f  mov     [rsp+900h+var_890], rcx
0x1800a7114  mov     [rsp+900h+hModule], rax
0x1800a7119  test    rax, rax
0x1800a711c  jnz     short loc_1800A715A
0x1800a711e  cmp     [rdi+18h], r14
0x1800a7122  jb      short loc_1800A7147
0x1800a7124  mov     rbx, [rdi]
0x1800a7127  mov     [rdi+10h], r14
0x1800a712b  mov     r8d, 24h ; '$'; Size
0x1800a7131  mov     rdx, r15; Src
0x1800a7134  mov     rcx, rbx; void *
0x1800a7137  call    memmove_0
0x1800a713c  xor     eax, eax
0x1800a713e  mov     [rbx+24h], ax
0x1800a7142  jmp     loc_1800A72FD
0x1800a7147  mov     r9, r15
0x1800a714a  mov     rdx, r14
0x1800a714d  mov     rcx, rdi
0x1800a7150  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800a7155  jmp     loc_1800A72FD
0x1800a715a  lea     rdx, aFvequerydevice; "FveQueryDeviceEncryptionSupport"
0x1800a7161  mov     rcx, rax; hModule
0x1800a7164  call    cs:__imp_GetProcAddress
0x1800a716a  mov     rsi, rax
0x1800a716d  lea     rdx, aFvechecktpmcap; "FveCheckTpmCapability"
0x1800a7174  mov     rcx, [rsp+900h+hModule]; hModule
0x1800a7179  call    cs:__imp_GetProcAddress
0x1800a717f  mov     rbx, rax
0x1800a7182  test    rsi, rsi
0x1800a7185  jz      short loc_1800A711E
0x1800a7187  xor     r14b, r14b
0x1800a718a  mov     [rbp+800h+var_86C+4], 0
0x1800a7191  lea     rcx, [rbp+800h+var_878]
0x1800a7195  mov     rax, rsi
0x1800a7198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a719d  mov     r15d, eax
0x1800a71a0  test    byte ptr [rbp+800h+var_86C+4], 4
0x1800a71a4  jz      short loc_1800A71C2
0x1800a71a6  test    rbx, rbx
0x1800a71a9  jz      short loc_1800A71BB
0x1800a71ab  lea     rcx, [rbp+800h+var_860]
0x1800a71af  mov     rax, rbx
0x1800a71b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a71b7  test    eax, eax
0x1800a71b9  jns     short loc_1800A71C2
0x1800a71bb  mov     [rbp+800h+var_858], 80004005h
0x1800a71c2  lea     rcx, [rsp+900h+var_89E]; bool *
0x1800a71c7  call    ?NgscbCheckPreventDeviceEncryption@@YAJPEA_N@Z; NgscbCheckPreventDeviceEncryption(bool *)
0x1800a71cc  mov     ebx, eax
0x1800a71ce  lea     rcx, [rsp+900h+var_89F]; bool *
0x1800a71d3  call    ?NgscbCheckPreventDeviceEncryptionForAad@@YAJPEA_N@Z; NgscbCheckPreventDeviceEncryptionForAad(bool *)
0x1800a71d8  mov     esi, 1
0x1800a71dd  test    eax, eax
0x1800a71df  jns     short loc_1800A71E6
0x1800a71e1  mov     bl, sil
0x1800a71e4  jmp     short loc_1800A71E9
0x1800a71e6  shr     ebx, 1Fh
0x1800a71e9  lea     rcx, [rsp+900h+var_89D]; bool *
0x1800a71ee  call    ?NgscbCheckIsUpgradedOS@@YAJPEA_N@Z; NgscbCheckIsUpgradedOS(bool *)
0x1800a71f3  movzx   ebx, bl
0x1800a71f6  test    eax, eax
0x1800a71f8  cmovs   ebx, esi
0x1800a71fb  lea     rdx, [rbp+800h+szFileName]; unsigned __int16 *
0x1800a71ff  lea     rcx, [rsp+900h+var_8A0]; bool *
0x1800a7204  call    ?NgscbGetWinReConfiguration@@YAJPEA_NPEAGK@Z; NgscbGetWinReConfiguration(bool *,ushort *,ulong)
0x1800a7209  test    eax, eax
0x1800a720b  js      short loc_1800A7224
0x1800a720d  cmp     [rsp+900h+var_8A0], r14b
0x1800a7212  jz      short loc_1800A7249
0x1800a7214  lea     rdx, [rsp+900h+var_89C]; int *
0x1800a7219  lea     rcx, [rbp+800h+szFileName]; lpszFileName
0x1800a721d  call    ?CheckIsOSDrive@CFveDriveType@@SAJPEBGPEAH@Z; CFveDriveType::CheckIsOSDrive(ushort const *,int *)
0x1800a7222  jmp     short loc_1800A7249
0x1800a7224  lea     rcx, [rsp+900h+var_8A0]; bool *
0x1800a7229  call    ?IsWinREEnabledFromBCD@CEnterpriseInfoV3@@CAJPEA_N@Z; CEnterpriseInfoV3::IsWinREEnabledFromBCD(bool *)
0x1800a722e  test    eax, eax
0x1800a7230  jns     short loc_1800A7237
0x1800a7232  mov     bl, sil
0x1800a7235  jmp     short loc_1800A7249
0x1800a7237  lea     rcx, [rsp+900h+var_89C]; int *
0x1800a723c  call    ?IsOSDriveAlsoRecoveryPartition@CEnterpriseInfoV3@@CAJPEAH@Z; CEnterpriseInfoV3::IsOSDriveAlsoRecoveryPartition(int *)
0x1800a7241  movzx   ebx, bl
0x1800a7244  test    eax, eax
0x1800a7246  cmovs   ebx, esi
0x1800a7249  lea     rdx, [rbp+800h+Src]
0x1800a724d  mov     rcx, r12
0x1800a7250  call    ?GetDomainJoined@EnterpriseInfo@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; EnterpriseInfo::GetDomainJoined(void)
0x1800a7255  mov     rcx, [rax+10h]
0x1800a7259  cmp     qword ptr [rax+18h], 7
0x1800a725e  jbe     short loc_1800A7263
0x1800a7260  mov     rax, [rax]
0x1800a7263  cmp     rcx, rsi
0x1800a7266  jz      short loc_1800A726D
0x1800a7268  xor     sil, sil
0x1800a726b  jmp     short loc_1800A7285
0x1800a726d  mov     r8, rsi; N
0x1800a7270  lea     rdx, a1_0; "1"
0x1800a7277  mov     rcx, rax; S1
0x1800a727a  call    wmemcmp
0x1800a727f  test    eax, eax
0x1800a7281  setz    sil
0x1800a7285  lea     rcx, [rbp+800h+Src]
0x1800a7289  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a728e  test    sil, sil
0x1800a7291  jz      short loc_1800A729E
0x1800a7293  call    ?RecoveryKeyBackUpEnabled@CEnterpriseInfoV3@@CA_NXZ; CEnterpriseInfoV3::RecoveryKeyBackUpEnabled(void)
0x1800a7298  test    al, al
0x1800a729a  setz    r14b
0x1800a729e  mov     eax, [rbp+800h+var_858]
0x1800a72a1  mov     [rsp+900h+var_8A8], eax; int
0x1800a72a5  mov     [rsp+900h+var_8B0], r15d; int
0x1800a72aa  mov     eax, [rbp+800h+var_86C]
0x1800a72ad  mov     [rsp+900h+var_8B8], eax; int
0x1800a72b1  mov     eax, [rbp+800h+var_86C+4]
0x1800a72b4  mov     [rsp+900h+var_8C0], eax; int
0x1800a72b8  mov     [rsp+900h+var_8C8], r14b; char
0x1800a72bd  mov     al, [rsp+900h+var_89F]
0x1800a72c1  mov     [rsp+900h+var_8D0], al; char
0x1800a72c5  mov     al, [rsp+900h+var_89E]
0x1800a72c9  mov     [rsp+900h+var_8D8], al; char
0x1800a72cd  mov     [rsp+900h+var_8E0], bl; char
0x1800a72d1  mov     r9d, [rsp+900h+var_89C]
0x1800a72d6  mov     r8b, [rsp+900h+var_8A0]
0x1800a72db  mov     dl, [rsp+900h+var_89D]
0x1800a72df  lea     rcx, [rbp+800h+Src]; Src
0x1800a72e3  call    ?ComposeStringForDEReq@CEnterpriseInfoV3@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N0H0000KJJJ@Z; CEnterpriseInfoV3::ComposeStringForDEReq(bool,bool,int,bool,bool,bool,bool,ulong,long,long,long)
0x1800a72e8  mov     rdx, rax
0x1800a72eb  mov     rcx, rdi
0x1800a72ee  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800a72f3  lea     rcx, [rbp+800h+Src]
0x1800a72f7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a72fc  nop
0x1800a72fd  lea     rax, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800a7304  mov     [rsp+900h+var_890], rax
0x1800a7309  cmp     [rsp+900h+hModule], 0
0x1800a730f  jz      short loc_1800A731F
0x1800a7311  lea     rcx, [rsp+900h+var_890]
0x1800a7316  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800a731b  test    al, al
0x1800a731d  jz      short loc_1800A734D
0x1800a731f  mov     rax, rdi
0x1800a7322  mov     rcx, [rbp+800h+var_30]
0x1800a7329  xor     rcx, rsp; StackCookie
0x1800a732c  call    __security_check_cookie
0x1800a7331  lea     r11, [rsp+900h+var_20]
0x1800a7339  mov     rbx, [r11+40h]
0x1800a733d  mov     rsi, [r11+48h]
0x1800a7341  mov     rsp, r11
0x1800a7344  pop     r15
0x1800a7346  pop     r14
0x1800a7348  pop     r12
0x1800a734a  pop     rdi
0x1800a734b  pop     rbp
0x1800a734c  retn
0x1800a734d  call    cs:__imp_GetLastError
0x1800a7353  test    eax, eax
0x1800a7355  jle     short loc_1800A735F
0x1800a7357  movzx   eax, ax
0x1800a735a  or      eax, 80070000h
0x1800a735f  mov     ecx, eax; this
0x1800a7361  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
