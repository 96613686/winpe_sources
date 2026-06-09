# CheckSlowLink(void *,ushort const *,ulong *,int *,ulong *,ulong *)

- ea: `0x18000fed8`
- end: `0x1800101ee`
- name: `?CheckSlowLink@@YAJPEAXPEBGPEAKPEAH22@Z`
- size: `790`
- prototype: `__int64 __fastcall(void *, const WCHAR *this, unsigned int *, int *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009f38`
- `0x180018a3c`

## callees

- `0x180002960`
- `0x1800029b0`
- `0x180003cd0`
- `0x180005558`
- `0x180006a9c`
- `0x180006c1c`
- `0x1800079f0`
- `0x18000fed8`
- `0x1800101f4`
- `0x1800102e0`
- `0x180010558`
- `0x18001059c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ff66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ff66`
- `PROFSVC!GetUserChoiceForSlowLink` at `0x18001016e`
- `PROFSVC!GetUserChoiceForSlowLink` at `0x18001016e`

## string_xrefs

- `0x180010039`: `clientcore\ds\security\gina\profile\roaming\network.cpp`
- `0x18000ff7b`: `SlowLinkDetectEnabled`
- `0x18000ffa0`: `SlowLinkTimeOut`
- `0x18000ffcc`: `SlowLinkUIEnabled`
- `0x18000ffe0`: `SlowLinkProfileDefault`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CheckSlowLink(
        void *a1,
        const WCHAR *this,
        unsigned int *a3,
        int *a4,
        unsigned int *a5,
        unsigned int *a6)
{
  int *v10; // rsi
  unsigned int *v11; // rdi
  const unsigned __int16 *v12; // rdx
  int Bool; // eax
  char v14; // dl
  const unsigned __int16 *v15; // rdx
  const unsigned __int16 *v16; // rdx
  __int64 v17; // r8
  unsigned int LocalSetting; // ebx
  __int64 v19; // rdx
  __int64 v21; // r8
  __int64 v22; // r8
  int v23; // ebx
  int phkResult; // [rsp+20h] [rbp-59h]
  unsigned int v25; // [rsp+30h] [rbp-49h] BYREF
  unsigned __int16 *v26; // [rsp+34h] [rbp-45h] BYREF
  HKEY v27; // [rsp+40h] [rbp-39h] BYREF
  int v28; // [rsp+48h] [rbp-31h] BYREF
  __int64 v29; // [rsp+50h] [rbp-29h]
  __int64 v30; // [rsp+58h] [rbp-21h]
  int v31; // [rsp+60h] [rbp-19h]
  __int128 v32; // [rsp+68h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]
  bool v34; // [rsp+E8h] [rbp+6Fh] BYREF

  *a4 = 0;
  v10 = (int *)a5;
  if ( a5 )
    *a5 = 0;
  v11 = a6;
  if ( a6 )
    *a6 = 0;
  LOBYTE(a5) = 1;
  v34 = 0;
  LOBYTE(a6) = 0;
  v26 = (unsigned __int16 *)0x1E00000078LL;
  v25 = 500;
  v27 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v27,
    0);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          0,
          0x20019u,
          &v27) )
  {
    LOBYTE(a5) = 0;
    Bool = SHRegGetBool(v27, v12, L"SlowLinkDetectEnabled", (bool *)&a5);
    v14 = 1;
    if ( Bool >= 0 )
      v14 = (char)a5;
    LOBYTE(a5) = v14;
    SHRegGetDWORD(v27, 0, L"SlowLinkTimeOut", (unsigned int *)&v26);
    SHRegGetDWORD(v27, 0, L"ProfileDlgTimeOut", (unsigned int *)&v26 + 1);
    SHRegGetBool(v27, v15, L"SlowLinkUIEnabled", &v34);
    SHRegGetBool(v27, v16, L"SlowLinkProfileDefault", (bool *)&a6);
    SHRegGetDWORD(v27, 0, L"UserProfileMinTransferRate", &v25);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
  LocalSetting = Profile::GetLocalSetting(17, &a5, v17);
  if ( (int)(LocalSetting + 0x80000000) >= 0 && LocalSetting != -2147024894 )
  {
    v19 = 1466;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\network.cpp",
      (const char *)LocalSetting,
      phkResult);
    return LocalSetting;
  }
  LocalSetting = Profile::GetLocalSetting(18, &v26);
  if ( (int)(LocalSetting + 0x80000000) >= 0 && LocalSetting != -2147024894 )
  {
    v19 = 1467;
    goto LABEL_12;
  }
  LocalSetting = Profile::GetLocalSetting(12, (char *)&v26 + 4);
  if ( (int)(LocalSetting + 0x80000000) >= 0 && LocalSetting != -2147024894 )
  {
    v19 = 1468;
    goto LABEL_12;
  }
  LocalSetting = Profile::GetLocalSetting(19, &v34, v21);
  if ( (int)(LocalSetting + 0x80000000) >= 0 && LocalSetting != -2147024894 )
  {
    v19 = 1469;
    goto LABEL_12;
  }
  LocalSetting = Profile::GetLocalSetting(20, &a6, v22);
  if ( (int)(LocalSetting + 0x80000000) >= 0 && LocalSetting != -2147024894 )
  {
    v19 = 1470;
    goto LABEL_12;
  }
  LocalSetting = Profile::GetLocalSetting(21, &v25);
  if ( (int)(LocalSetting + 0x80000000) >= 0 && LocalSetting != -2147024894 )
  {
    v19 = 1471;
    goto LABEL_12;
  }
  if ( (_BYTE)a5 && !(_BYTE)a6 && v25 )
  {
    v23 = 0;
    LODWORD(a5) = 0;
    if ( (_DWORD)v26 )
    {
      if ( !v34 || !a3 || !GetUserChoiceForSlowLink(*a3, 0) )
      {
        v28 = 0;
        v29 = 0;
        v30 = 0;
        v31 = 0;
        v32 = 0;
        if ( CThreadContext::ImpersonateUser((CThreadContext *)&v28, a1) >= 0 )
        {
          if ( (unsigned int)IsUNCPath(this) )
          {
            roaming::_CheckLatencyAndBandwithForSlowLink(
              this,
              (const unsigned __int16 *)(unsigned int)v26,
              v25,
              &a5,
              v10,
              v11);
            v23 = (int)a5;
          }
        }
        CThreadContext::~CThreadContext((CThreadContext *)&v28);
      }
    }
    else
    {
      v23 = 1;
    }
    *a4 = v23;
  }
  return 0;
}

```

## disassembly

```asm
0x18000fed8  push    rbp
0x18000feda  push    rbx
0x18000fedb  push    rsi
0x18000fedc  push    rdi
0x18000fedd  push    r12
0x18000fedf  push    r13
0x18000fee1  push    r14
0x18000fee3  push    r15
0x18000fee5  lea     rbp, [rsp-0Fh]
0x18000feea  sub     rsp, 88h
0x18000fef1  mov     r14, r9
0x18000fef4  mov     r15, r8
0x18000fef7  mov     r12, rdx
0x18000fefa  mov     r13, rcx
0x18000fefd  xor     ebx, ebx
0x18000feff  mov     [r9], ebx
0x18000ff02  mov     rsi, [rbp+47h+arg_20]
0x18000ff06  test    rsi, rsi
0x18000ff09  jz      short loc_18000FF0D
0x18000ff0b  mov     [rsi], ebx
0x18000ff0d  mov     rdi, [rbp+47h+arg_28]
0x18000ff11  test    rdi, rdi
0x18000ff14  jz      short loc_18000FF18
0x18000ff16  mov     [rdi], ebx
0x18000ff18  mov     byte ptr [rbp+47h+arg_20], 1
0x18000ff1c  mov     [rbp+47h+arg_18], bl
0x18000ff1f  mov     byte ptr [rbp+47h+arg_28], bl
0x18000ff22  mov     dword ptr [rbp+47h+var_8C], 78h ; 'x'
0x18000ff29  mov     dword ptr [rbp+47h+var_8C+4], 1Eh
0x18000ff30  mov     [rbp+47h+var_90], 1F4h
0x18000ff37  mov     [rbp+47h+var_80], rbx
0x18000ff3b  xor     edx, edx
0x18000ff3d  lea     rcx, [rbp+47h+var_80]
0x18000ff41  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000ff46  lea     rax, [rbp+47h+var_80]
0x18000ff4a  mov     [rsp+0C0h+phkResult], rax; int
0x18000ff4f  mov     r9d, 20019h; samDesired
0x18000ff55  xor     r8d, r8d; ulOptions
0x18000ff58  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000ff5f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ff66  call    cs:__imp_RegOpenKeyExW
0x18000ff6c  test    eax, eax
0x18000ff6e  jnz     loc_180010007
0x18000ff74  mov     byte ptr [rbp+47h+arg_20], bl
0x18000ff77  lea     r9, [rbp+47h+arg_20]; bool *
0x18000ff7b  lea     r8, aSlowlinkdetect; "SlowLinkDetectEnabled"
0x18000ff82  mov     rcx, [rbp+47h+var_80]; HKEY
0x18000ff86  call    ?SHRegGetBool@@YAJPEAUHKEY__@@PEBG1PEA_N@Z; SHRegGetBool(HKEY__ *,ushort const *,ushort const *,bool *)
0x18000ff8b  mov     edx, 1
0x18000ff90  movzx   ecx, byte ptr [rbp+47h+arg_20]
0x18000ff94  test    eax, eax
0x18000ff96  cmovns  edx, ecx
0x18000ff99  mov     byte ptr [rbp+47h+arg_20], dl
0x18000ff9c  lea     r9, [rbp+47h+var_8C]; unsigned int *
0x18000ffa0  lea     r8, aSlowlinktimeou; "SlowLinkTimeOut"
0x18000ffa7  xor     edx, edx; unsigned __int16 *
0x18000ffa9  mov     rcx, [rbp+47h+var_80]; HKEY
0x18000ffad  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000ffb2  lea     r9, [rbp+47h+var_8C+4]; unsigned int *
0x18000ffb6  lea     r8, aProfiledlgtime; "ProfileDlgTimeOut"
0x18000ffbd  xor     edx, edx; unsigned __int16 *
0x18000ffbf  mov     rcx, [rbp+47h+var_80]; HKEY
0x18000ffc3  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000ffc8  lea     r9, [rbp+47h+arg_18]; bool *
0x18000ffcc  lea     r8, aSlowlinkuienab; "SlowLinkUIEnabled"
0x18000ffd3  mov     rcx, [rbp+47h+var_80]; HKEY
0x18000ffd7  call    ?SHRegGetBool@@YAJPEAUHKEY__@@PEBG1PEA_N@Z; SHRegGetBool(HKEY__ *,ushort const *,ushort const *,bool *)
0x18000ffdc  lea     r9, [rbp+47h+arg_28]; bool *
0x18000ffe0  lea     r8, aSlowlinkprofil; "SlowLinkProfileDefault"
0x18000ffe7  mov     rcx, [rbp+47h+var_80]; HKEY
0x18000ffeb  call    ?SHRegGetBool@@YAJPEAUHKEY__@@PEBG1PEA_N@Z; SHRegGetBool(HKEY__ *,ushort const *,ushort const *,bool *)
0x18000fff0  lea     r9, [rbp+47h+var_90]; unsigned int *
0x18000fff4  lea     r8, aUserprofilemin; "UserProfileMinTransferRate"
0x18000fffb  xor     edx, edx; unsigned __int16 *
0x18000fffd  mov     rcx, [rbp+47h+var_80]; HKEY
0x180010001  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180010006  nop
0x180010007  lea     rcx, [rbp+47h+var_80]
0x18001000b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180010010  lea     rdx, [rbp+47h+arg_20]
0x180010014  mov     ecx, 11h
0x180010019  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEA_NPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,bool &,ushort const *,USERSTATE_SETTING_SOURCES)
0x18001001e  mov     ebx, eax
0x180010020  mov     eax, 80000000h
0x180010025  lea     ecx, [rbx+rax]
0x180010028  test    eax, ecx
0x18001002a  jnz     short loc_180010053
0x18001002c  cmp     ebx, 80070002h
0x180010032  jz      short loc_180010053
0x180010034  mov     edx, 5BAh; void *
0x180010039  lea     r8, aClientcoreDsSe_4; "clientcore\\ds\\security\\gina\\profile"...
0x180010040  mov     r9d, ebx; char *
0x180010043  mov     rcx, [rbp+4Fh]; this
0x180010047  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001004c  mov     eax, ebx
0x18001004e  jmp     loc_1800101DA
0x180010053  lea     rdx, [rbp+47h+var_8C]
0x180010057  mov     ecx, 12h
0x18001005c  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEAKPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,ulong &,ushort const *,USERSTATE_SETTING_SOURCES)
0x180010061  mov     ebx, eax
0x180010063  mov     eax, 80000000h
0x180010068  lea     ecx, [rbx+rax]
0x18001006b  test    eax, ecx
0x18001006d  jnz     short loc_18001007E
0x18001006f  cmp     ebx, 80070002h
0x180010075  jz      short loc_18001007E
0x180010077  mov     edx, 5BBh
0x18001007c  jmp     short loc_180010039
0x18001007e  lea     rdx, [rbp+47h+var_8C+4]
0x180010082  mov     ecx, 0Ch
0x180010087  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEAKPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,ulong &,ushort const *,USERSTATE_SETTING_SOURCES)
0x18001008c  mov     ebx, eax
0x18001008e  mov     eax, 80000000h
0x180010093  lea     ecx, [rbx+rax]
0x180010096  test    eax, ecx
0x180010098  jnz     short loc_1800100A9
0x18001009a  cmp     ebx, 80070002h
0x1800100a0  jz      short loc_1800100A9
0x1800100a2  mov     edx, 5BCh
0x1800100a7  jmp     short loc_180010039
0x1800100a9  lea     rdx, [rbp+47h+arg_18]
0x1800100ad  mov     ecx, 13h
0x1800100b2  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEA_NPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,bool &,ushort const *,USERSTATE_SETTING_SOURCES)
0x1800100b7  mov     ebx, eax
0x1800100b9  mov     eax, 80000000h
0x1800100be  lea     ecx, [rbx+rax]
0x1800100c1  test    eax, ecx
0x1800100c3  jnz     short loc_1800100D7
0x1800100c5  cmp     ebx, 80070002h
0x1800100cb  jz      short loc_1800100D7
0x1800100cd  mov     edx, 5BDh
0x1800100d2  jmp     loc_180010039
0x1800100d7  lea     rdx, [rbp+47h+arg_28]
0x1800100db  mov     ecx, 14h
0x1800100e0  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEA_NPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,bool &,ushort const *,USERSTATE_SETTING_SOURCES)
0x1800100e5  mov     ebx, eax
0x1800100e7  mov     eax, 80000000h
0x1800100ec  lea     ecx, [rbx+rax]
0x1800100ef  test    eax, ecx
0x1800100f1  jnz     short loc_180010105
0x1800100f3  cmp     ebx, 80070002h
0x1800100f9  jz      short loc_180010105
0x1800100fb  mov     edx, 5BEh
0x180010100  jmp     loc_180010039
0x180010105  lea     rdx, [rbp+47h+var_90]
0x180010109  mov     ecx, 15h
0x18001010e  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEAKPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,ulong &,ushort const *,USERSTATE_SETTING_SOURCES)
0x180010113  mov     ebx, eax
0x180010115  mov     eax, 80000000h
0x18001011a  lea     ecx, [rbx+rax]
0x18001011d  test    eax, ecx
0x18001011f  jnz     short loc_180010133
0x180010121  cmp     ebx, 80070002h
0x180010127  jz      short loc_180010133
0x180010129  mov     edx, 5BFh
0x18001012e  jmp     loc_180010039
0x180010133  xor     eax, eax
0x180010135  cmp     byte ptr [rbp+47h+arg_20], al
0x180010138  jz      loc_1800101D8
0x18001013e  cmp     byte ptr [rbp+47h+arg_28], al
0x180010141  jnz     loc_1800101D8
0x180010147  cmp     [rbp+47h+var_90], eax
0x18001014a  jz      loc_1800101D8
0x180010150  mov     ebx, eax
0x180010152  mov     dword ptr [rbp+47h+arg_20], eax
0x180010155  cmp     dword ptr [rbp+47h+var_8C], eax
0x180010158  jnz     short loc_18001015F
0x18001015a  lea     ebx, [rax+1]
0x18001015d  jmp     short loc_1800101D5
0x18001015f  cmp     [rbp+47h+arg_18], al
0x180010162  jz      short loc_18001017A
0x180010164  test    r15, r15
0x180010167  jz      short loc_18001017A
0x180010169  xor     edx, edx
0x18001016b  mov     ecx, [r15]
0x18001016e  call    cs:__imp_?GetUserChoiceForSlowLink@@YAHKH@Z; GetUserChoiceForSlowLink(ulong,int)
0x180010174  test    eax, eax
0x180010176  jnz     short loc_1800101D5
0x180010178  xor     eax, eax
0x18001017a  mov     [rbp+47h+var_78], eax
0x18001017d  mov     [rbp+47h+var_70], rax
0x180010181  mov     [rbp+47h+var_68], rbx
0x180010185  mov     [rbp+47h+var_60], eax
0x180010188  xorps   xmm0, xmm0
0x18001018b  movdqu  [rbp+47h+var_58], xmm0
0x180010190  mov     rdx, r13; void *
0x180010193  lea     rcx, [rbp+47h+var_78]; this
0x180010197  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x18001019c  test    eax, eax
0x18001019e  js      short loc_1800101CC
0x1800101a0  mov     rcx, r12; unsigned __int16 *
0x1800101a3  call    ?IsUNCPath@@YAHPEBG@Z; IsUNCPath(ushort const *)
0x1800101a8  test    eax, eax
0x1800101aa  jz      short loc_1800101CC
0x1800101ac  mov     [rsp+0C0h+var_98], rdi; unsigned int *
0x1800101b1  mov     [rsp+0C0h+phkResult], rsi; int *
0x1800101b6  lea     r9, [rbp+47h+arg_20]; unsigned int
0x1800101ba  mov     r8d, [rbp+47h+var_90]; unsigned int
0x1800101be  mov     edx, dword ptr [rbp+47h+var_8C]; unsigned __int16 *
0x1800101c1  mov     rcx, r12; this
0x1800101c4  call    ?_CheckLatencyAndBandwithForSlowLink@roaming@@YAJPEBGKKAEAHPEAK2@Z; roaming::_CheckLatencyAndBandwithForSlowLink(ushort const *,ulong,ulong,int &,ulong *,ulong *)
0x1800101c9  mov     ebx, dword ptr [rbp+47h+arg_20]
0x1800101cc  lea     rcx, [rbp+47h+var_78]; this
0x1800101d0  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x1800101d5  mov     [r14], ebx
0x1800101d8  xor     eax, eax
0x1800101da  add     rsp, 88h
0x1800101e1  pop     r15
0x1800101e3  pop     r14
0x1800101e5  pop     r13
0x1800101e7  pop     r12
0x1800101e9  pop     rdi
0x1800101ea  pop     rsi
0x1800101eb  pop     rbx
0x1800101ec  pop     rbp
0x1800101ed  retn
```
