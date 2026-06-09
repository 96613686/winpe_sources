# Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager::GetManagementServerAddressList(ushort const *,ushort * *,unsigned __int64 &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x14004e9b0`
- end: `0x14004ef1f`
- name: `?GetManagementServerAddressList@SyncmlSessionStateManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBGPEAPEAGAEA_KAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1391`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004f290`

## callees

- `0x140003450`
- `0x140005500`
- `0x14000b0f4`
- `0x14000e610`
- `0x140013404`
- `0x1400146d8`
- `0x140029118`
- `0x14002a5ec`
- `0x14004e4e0`
- `0x14004e728`
- `0x14004e9b0`
- `0x14005224c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14004ec4b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14004ec4b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14004ec0c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14004ec0c`
- `DMCmnUtils!CopyString` at `0x14004eb58`
- `DMCmnUtils!CopyString` at `0x14004eb58`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x14004ec65`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x14004ec65`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14004ec7d`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14004ec7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager::GetManagementServerAddressList(
        __int64 a1,
        __int64 a2,
        unsigned __int16 **a3,
        unsigned __int64 *a4,
        __int64 *a5)
{
  unsigned int v8; // ebx
  __int64 v10; // rsi
  __int64 v11; // rbx
  __int64 v12; // r8
  __int128 *v13; // r14
  char *v14; // rbx
  __int64 end_2; // rax
  __int64 v16; // rsi
  unsigned __int64 v17; // r8
  __int128 *v18; // rdx
  const unsigned __int16 *v19; // rcx
  int v20; // eax
  unsigned int v21; // ebx
  unsigned __int64 v22; // rsi
  __int64 v23; // r8
  __int128 *v24; // rax
  _DWORD *v25; // rax
  _DWORD *v26; // rsi
  const wchar_t *v27; // rbx
  int v28; // eax
  __int64 v29; // rbx
  unsigned __int64 v30; // rsi
  __int64 v31; // rax
  __int64 v32; // r14
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // r8
  __int128 *v35; // rax
  unsigned __int64 v36; // rax
  int v37; // [rsp+20h] [rbp-F8h] BYREF
  _QWORD v38[3]; // [rsp+28h] [rbp-F0h] BYREF
  int v39; // [rsp+40h] [rbp-D8h]
  int *v40; // [rsp+48h] [rbp-D0h]
  wchar_t *EndPtr; // [rsp+50h] [rbp-C8h] BYREF
  __int128 v42; // [rsp+58h] [rbp-C0h] BYREF
  unsigned __int64 v43; // [rsp+68h] [rbp-B0h]
  unsigned __int64 v44; // [rsp+70h] [rbp-A8h]
  __int128 v45; // [rsp+78h] [rbp-A0h] BYREF
  __int128 v46; // [rsp+88h] [rbp-90h]
  wchar_t *String[2]; // [rsp+98h] [rbp-80h] BYREF
  __int128 v48; // [rsp+A8h] [rbp-70h]
  __int128 v49; // [rsp+B8h] [rbp-60h] BYREF
  __int128 v50; // [rsp+C8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v37 = 0;
  v38[0] = 0;
  v38[1] = "GetManagementServerAddressList";
  v38[2] = COmaDmLogger::GetLogger();
  v39 = 1;
  v40 = &v37;
  if ( !a3 )
  {
    v8 = -805306128;
    v37 = -805306128;
LABEL_3:
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v38);
    return v8;
  }
  v10 = a5[1];
  v11 = *a5;
  if ( *a5 != v10 )
  {
    do
    {
      std::wstring::~wstring(v11);
      v11 += 32;
    }
    while ( v11 != v10 );
    a5[1] = *a5;
  }
  *a4 = 0;
  *a3 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(a2 + 2 * v12) );
  std::wstring::_Construct<1,unsigned short const *>(&v42, a2, v12);
  v13 = &v42;
  if ( v44 > 7 )
    v13 = (__int128 *)v42;
  if ( v43 < 2
    || (v14 = (char *)v13 + 2 * v43, end_2 = _std_find_end_2(v13, v14, L">:"), (char *)end_2 == v14)
    || (v16 = (end_2 - (__int64)v13) >> 1, v16 == -1) )
  {
    v38[0] = 0x8000FFFF00002355uLL;
    std::wstring::~wstring(&v42);
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v38);
    return 2147549183LL;
  }
  else
  {
    v45 = 0;
    v46 = 0;
    v17 = v43;
    if ( v43 >= v16 + 1 )
      v17 = v16 + 1;
    v18 = &v42;
    if ( v44 > 7 )
      v18 = (__int128 *)v42;
    std::wstring::_Construct<1,unsigned short const *>(&v45, v18, v17);
    v19 = (const unsigned __int16 *)&v45;
    if ( *((_QWORD *)&v46 + 1) > 7u )
      v19 = (const unsigned __int16 *)v45;
    v20 = CopyString(v19, 0xFFFFFFFF, a3);
    v21 = v20;
    v37 = v20;
    if ( v20 >= 0 )
    {
      v22 = v16 + 2;
      *(_OWORD *)String = 0;
      v48 = 0;
      if ( v43 < v22 )
      {
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
LABEL_56:
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
        JUMPOUT(0x14004EF1DLL);
      }
      v23 = -1;
      if ( v43 - v22 != -1 )
        v23 = v43 - v22;
      v24 = &v42;
      if ( v44 > 7 )
        v24 = (__int128 *)v42;
      std::wstring::_Construct<1,unsigned short const *>(String, (char *)v24 + 2 * v22, v23);
      v25 = (_DWORD *)_o__errno();
      v26 = v25;
      v27 = (const wchar_t *)String;
      if ( *((_QWORD *)&v48 + 1) > 7u )
        v27 = String[0];
      EndPtr = 0;
      *v25 = 0;
      v28 = wcstol(v27, &EndPtr, 10);
      if ( v27 == EndPtr )
        std::_Xinvalid_argument("invalid stoi argument");
      if ( *v26 == 34 )
        std::_Xout_of_range("stoi argument out of range");
      *a4 = v28;
      v29 = std::wstring::find(&v42, L"<", 0);
      if ( v29 == -1 )
      {
LABEL_34:
        v38[0] = 0x8000FFFF00002355uLL;
        std::wstring::~wstring(String);
        std::wstring::~wstring(&v45);
        std::wstring::~wstring(&v42);
        Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v38);
        return 2147549183LL;
      }
      else
      {
        while ( v29 != -1 )
        {
          v30 = v29 + 1;
          v31 = std::wstring::find(&v42, L">", v29 + 1);
          v32 = v31;
          if ( v31 == -1 )
          {
            if ( v29 != v43 )
              goto LABEL_34;
            break;
          }
          v49 = 0;
          v50 = 0;
          if ( v43 < v30 )
            goto LABEL_56;
          v33 = v31 - v29 - 1;
          v34 = v43 - v30;
          if ( v43 - v30 >= v33 )
            v34 = v33;
          v35 = &v42;
          if ( v44 > 7 )
            v35 = (__int128 *)v42;
          std::wstring::_Construct<1,unsigned short const *>(&v49, (char *)v35 + 2 * v30, v34);
          if ( (_QWORD)v50 )
          {
            if ( a5[1] == a5[2] )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a5, a5[1], &v49);
            }
            else
            {
              std::wstring::wstring(a5[1], &v49);
              a5[1] += 32;
            }
          }
          v29 = std::wstring::find(&v42, L"<", v32 + 1);
          std::wstring::~wstring(&v49);
        }
        v36 = (a5[1] - *a5) >> 5;
        if ( v36 )
        {
          if ( *a4 >= v36 )
            *a4 = 0;
          std::wstring::~wstring(String);
          std::wstring::~wstring(&v45);
          std::wstring::~wstring(&v42);
          v8 = v37;
          goto LABEL_3;
        }
        v38[0] = 0x8000FFFF00002354uLL;
        std::wstring::~wstring(String);
        std::wstring::~wstring(&v45);
        std::wstring::~wstring(&v42);
        Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v38);
        return 2147549183LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4EB,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\syncmlsessionstatemanager.cpp",
        (const char *)(unsigned int)v20,
        v37);
      std::wstring::~wstring(&v45);
      std::wstring::~wstring(&v42);
      Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v38);
      return v21;
    }
  }
}

```

## disassembly

```asm
0x14004e9b0  push    rbx
0x14004e9b2  push    rsi
0x14004e9b3  push    rdi
0x14004e9b4  push    r12
0x14004e9b6  push    r13
0x14004e9b8  push    r14
0x14004e9ba  push    r15
0x14004e9bc  sub     rsp, 0E0h
0x14004e9c3  mov     rax, cs:__security_cookie
0x14004e9ca  xor     rax, rsp
0x14004e9cd  mov     [rsp+118h+var_40], rax
0x14004e9d5  mov     r15, r9
0x14004e9d8  mov     r12, r8
0x14004e9db  mov     r14, rdx
0x14004e9de  mov     rdi, [rsp+118h+arg_20]
0x14004e9e6  xor     r13d, r13d
0x14004e9e9  mov     [rsp+118h+var_F8], r13d
0x14004e9ee  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004e9f3  mov     [rsp+118h+var_F0], r13
0x14004e9f8  lea     rcx, aGetmanagements; "GetManagementServerAddressList"
0x14004e9ff  mov     [rsp+118h+var_E8], rcx
0x14004ea04  mov     [rsp+118h+var_E0], rax
0x14004ea09  mov     [rsp+118h+var_D8], 1
0x14004ea11  lea     rax, [rsp+118h+var_F8]
0x14004ea16  mov     [rsp+118h+var_D0], rax
0x14004ea1b  test    r12, r12
0x14004ea1e  jnz     short loc_14004EA3A
0x14004ea20  mov     ebx, 0D00000F0h
0x14004ea25  mov     [rsp+118h+var_F8], ebx
0x14004ea29  lea     rcx, [rsp+118h+var_F0]; this
0x14004ea2e  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004ea33  mov     eax, ebx
0x14004ea35  jmp     loc_14004EEEE
0x14004ea3a  mov     rsi, [rdi+8]
0x14004ea3e  mov     rbx, [rdi]
0x14004ea41  cmp     rbx, rsi
0x14004ea44  jz      short loc_14004EA5E
0x14004ea46  mov     rcx, rbx
0x14004ea49  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ea4e  add     rbx, 20h ; ' '
0x14004ea52  cmp     rbx, rsi
0x14004ea55  jnz     short loc_14004EA46
0x14004ea57  mov     rax, [rdi]
0x14004ea5a  mov     [rdi+8], rax
0x14004ea5e  mov     [r15], r13
0x14004ea61  mov     [r12], r13
0x14004ea65  xorps   xmm0, xmm0
0x14004ea68  movups  [rsp+118h+var_C0], xmm0
0x14004ea6d  mov     [rsp+118h+var_B0], r13
0x14004ea72  mov     [rsp+118h+var_A8], r13
0x14004ea77  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14004ea7b  mov     r8, rbx
0x14004ea7e  inc     r8
0x14004ea81  cmp     [r14+r8*2], r13w
0x14004ea86  jnz     short loc_14004EA7E
0x14004ea88  mov     rdx, r14
0x14004ea8b  lea     rcx, [rsp+118h+var_C0]
0x14004ea90  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14004ea95  nop
0x14004ea96  mov     rax, [rsp+118h+var_B0]
0x14004ea9b  lea     r14, [rsp+118h+var_C0]
0x14004eaa0  cmp     [rsp+118h+var_A8], 7
0x14004eaa6  cmova   r14, qword ptr [rsp+118h+var_C0]
0x14004eaac  mov     r9d, 2
0x14004eab2  cmp     rax, r9
0x14004eab5  jb      loc_14004EEB5
0x14004eabb  add     rax, 0FFFFFFFFFFFFFFFEh
0x14004eabf  mov     rcx, rbx
0x14004eac2  cmp     rax, rbx
0x14004eac5  cmovb   rcx, rax
0x14004eac9  add     rcx, r9
0x14004eacc  lea     rbx, [r14+rcx*2]
0x14004ead0  lea     r8, asc_1400753A8; ">:"
0x14004ead7  mov     rdx, rbx
0x14004eada  mov     rcx, r14
0x14004eadd  call    __std_find_end_2
0x14004eae2  mov     rsi, rax
0x14004eae5  cmp     rax, rbx
0x14004eae8  jz      loc_14004EEB5
0x14004eaee  sub     rsi, r14
0x14004eaf1  sar     rsi, 1
0x14004eaf4  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14004eaf8  jz      loc_14004EEB5
0x14004eafe  xorps   xmm0, xmm0
0x14004eb01  movups  [rsp+118h+var_A0], xmm0
0x14004eb06  xorps   xmm1, xmm1
0x14004eb09  movdqu  [rsp+118h+var_90], xmm1
0x14004eb12  mov     r8, [rsp+118h+var_B0]
0x14004eb17  lea     rax, [rsi+1]
0x14004eb1b  cmp     r8, rax
0x14004eb1e  cmovnb  r8, rax
0x14004eb22  lea     rdx, [rsp+118h+var_C0]
0x14004eb27  cmp     [rsp+118h+var_A8], 7
0x14004eb2d  cmova   rdx, qword ptr [rsp+118h+var_C0]
0x14004eb33  lea     rcx, [rsp+118h+var_A0]
0x14004eb38  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14004eb3d  nop
0x14004eb3e  lea     rcx, [rsp+118h+var_A0]
0x14004eb43  cmp     qword ptr [rsp+118h+var_90+8], 7
0x14004eb4c  cmova   rcx, qword ptr [rsp+118h+var_A0]
0x14004eb52  mov     r8, r12
0x14004eb55  or      edx, 0FFFFFFFFh
0x14004eb58  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x14004eb5f  nop     dword ptr [rax+rax+00h]
0x14004eb64  mov     ebx, eax
0x14004eb66  mov     [rsp+118h+var_F8], eax; int
0x14004eb6a  test    eax, eax
0x14004eb6c  jns     short loc_14004EBB2
0x14004eb6e  mov     rcx, [rsp+118h]; this
0x14004eb76  mov     r9d, eax; char *
0x14004eb79  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14004eb80  mov     edx, 4EBh; void *
0x14004eb85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004eb8a  nop
0x14004eb8b  lea     rcx, [rsp+118h+var_A0]
0x14004eb90  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004eb95  nop
0x14004eb96  lea     rcx, [rsp+118h+var_C0]
0x14004eb9b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004eba0  nop
0x14004eba1  lea     rcx, [rsp+118h+var_F0]; this
0x14004eba6  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004ebab  mov     eax, ebx
0x14004ebad  jmp     loc_14004EEEE
0x14004ebb2  add     rsi, 2
0x14004ebb6  xorps   xmm0, xmm0
0x14004ebb9  movups  xmmword ptr [rsp+118h+String], xmm0
0x14004ebc1  xorps   xmm1, xmm1
0x14004ebc4  movdqu  [rsp+118h+var_70], xmm1
0x14004ebcd  mov     rax, [rsp+118h+var_B0]
0x14004ebd2  cmp     rax, rsi
0x14004ebd5  jb      loc_14004EF12
0x14004ebdb  sub     rax, rsi
0x14004ebde  or      r8, 0FFFFFFFFFFFFFFFFh
0x14004ebe2  cmp     rax, r8
0x14004ebe5  cmovb   r8, rax
0x14004ebe9  lea     rax, [rsp+118h+var_C0]
0x14004ebee  cmp     [rsp+118h+var_A8], 7
0x14004ebf4  cmova   rax, qword ptr [rsp+118h+var_C0]
0x14004ebfa  lea     rdx, [rax+rsi*2]
0x14004ebfe  lea     rcx, [rsp+118h+String]
0x14004ec06  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14004ec0b  nop
0x14004ec0c  call    cs:__imp__o__errno
0x14004ec13  nop     dword ptr [rax+rax+00h]
0x14004ec18  mov     rsi, rax
0x14004ec1b  lea     rbx, [rsp+118h+String]
0x14004ec23  cmp     qword ptr [rsp+118h+var_70+8], 7
0x14004ec2c  cmova   rbx, [rsp+118h+String]
0x14004ec35  mov     [rsp+118h+EndPtr], r13
0x14004ec3a  mov     [rax], r13d
0x14004ec3d  mov     r8d, 0Ah; Radix
0x14004ec43  lea     rdx, [rsp+118h+EndPtr]; EndPtr
0x14004ec48  mov     rcx, rbx; String
0x14004ec4b  call    cs:__imp_wcstol
0x14004ec52  nop     dword ptr [rax+rax+00h]
0x14004ec57  cmp     rbx, [rsp+118h+EndPtr]
0x14004ec5c  jnz     short loc_14004EC71
0x14004ec5e  lea     rcx, aInvalidStoiArg; "invalid stoi argument"
0x14004ec65  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x14004ec6c  nop     dword ptr [rax+rax+00h]
0x14004ec71  cmp     dword ptr [rsi], 22h ; '"'
0x14004ec74  jnz     short loc_14004EC89
0x14004ec76  lea     rcx, aStoiArgumentOu; "stoi argument out of range"
0x14004ec7d  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x14004ec84  nop     dword ptr [rax+rax+00h]
0x14004ec89  cdqe
0x14004ec8b  mov     [r15], rax
0x14004ec8e  xor     r8d, r8d
0x14004ec91  lea     rdx, asc_140074D70; "<"
0x14004ec98  lea     rcx, [rsp+118h+var_C0]
0x14004ec9d  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x14004eca2  mov     rbx, rax
0x14004eca5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14004eca9  jnz     short loc_14004ECF1
0x14004ecab  mov     dword ptr [rsp+118h+var_F0], 2355h
0x14004ecb3  mov     ebx, 8000FFFFh
0x14004ecb8  mov     dword ptr [rsp+118h+var_F0+4], ebx
0x14004ecbc  lea     rcx, [rsp+118h+String]
0x14004ecc4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ecc9  nop
0x14004ecca  lea     rcx, [rsp+118h+var_A0]
0x14004eccf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ecd4  nop
0x14004ecd5  lea     rcx, [rsp+118h+var_C0]
0x14004ecda  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ecdf  nop
0x14004ece0  lea     rcx, [rsp+118h+var_F0]; this
0x14004ece5  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004ecea  mov     eax, ebx
0x14004ecec  jmp     loc_14004EEEE
0x14004ecf1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14004ecf5  jz      loc_14004EE2D
0x14004ecfb  lea     rsi, [rbx+1]
0x14004ecff  mov     r8, rsi
0x14004ed02  lea     rdx, asc_140074D6C; ">"
0x14004ed09  lea     rcx, [rsp+118h+var_C0]
0x14004ed0e  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x14004ed13  mov     r14, rax
0x14004ed16  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14004ed1a  jnz     short loc_14004ED6D
0x14004ed1c  cmp     rbx, [rsp+118h+var_B0]
0x14004ed21  jz      loc_14004EE2D
0x14004ed27  mov     dword ptr [rsp+118h+var_F0], 2355h
0x14004ed2f  mov     ebx, 8000FFFFh
0x14004ed34  mov     dword ptr [rsp+118h+var_F0+4], ebx
0x14004ed38  lea     rcx, [rsp+118h+String]
0x14004ed40  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ed45  nop
0x14004ed46  lea     rcx, [rsp+118h+var_A0]
0x14004ed4b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ed50  nop
0x14004ed51  lea     rcx, [rsp+118h+var_C0]
0x14004ed56  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ed5b  nop
0x14004ed5c  lea     rcx, [rsp+118h+var_F0]; this
0x14004ed61  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004ed66  mov     eax, ebx
0x14004ed68  jmp     loc_14004EEEE
0x14004ed6d  xorps   xmm0, xmm0
0x14004ed70  movups  [rsp+118h+var_60], xmm0
0x14004ed78  xorps   xmm1, xmm1
0x14004ed7b  movdqu  [rsp+118h+var_50], xmm1
0x14004ed84  mov     r8, [rsp+118h+var_B0]
0x14004ed89  cmp     r8, rsi
0x14004ed8c  jb      loc_14004EF18
0x14004ed92  sub     rax, rbx
0x14004ed95  dec     rax
0x14004ed98  sub     r8, rsi
0x14004ed9b  cmp     r8, rax
0x14004ed9e  cmovnb  r8, rax
0x14004eda2  lea     rax, [rsp+118h+var_C0]
0x14004eda7  cmp     [rsp+118h+var_A8], 7
0x14004edad  cmova   rax, qword ptr [rsp+118h+var_C0]
0x14004edb3  lea     rdx, [rax+rsi*2]
0x14004edb7  lea     rcx, [rsp+118h+var_60]
0x14004edbf  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14004edc4  nop
0x14004edc5  cmp     qword ptr [rsp+118h+var_50], r13
0x14004edcd  jbe     short loc_14004EE03
0x14004edcf  mov     rax, [rdi+8]
0x14004edd3  cmp     rax, [rdi+10h]
0x14004edd7  jz      short loc_14004EDF0
0x14004edd9  lea     rdx, [rsp+118h+var_60]
0x14004ede1  mov     rcx, rax
0x14004ede4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14004ede9  add     qword ptr [rdi+8], 20h ; ' '
0x14004edee  jmp     short loc_14004EE03
0x14004edf0  lea     r8, [rsp+118h+var_60]
0x14004edf8  mov     rdx, rax
0x14004edfb  mov     rcx, rdi
0x14004edfe  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x14004ee03  lea     r8, [r14+1]
0x14004ee07  lea     rdx, asc_140074D70; "<"
0x14004ee0e  lea     rcx, [rsp+118h+var_C0]
0x14004ee13  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x14004ee18  mov     rbx, rax
0x14004ee1b  lea     rcx, [rsp+118h+var_60]
0x14004ee23  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ee28  jmp     loc_14004ECF1
0x14004ee2d  mov     rax, [rdi+8]
0x14004ee31  sub     rax, [rdi]
0x14004ee34  sar     rax, 5
0x14004ee38  test    rax, rax
0x14004ee3b  jnz     short loc_14004EE80
0x14004ee3d  mov     dword ptr [rsp+118h+var_F0], 2354h
0x14004ee45  mov     ebx, 8000FFFFh
0x14004ee4a  mov     dword ptr [rsp+118h+var_F0+4], ebx
0x14004ee4e  lea     rcx, [rsp+118h+String]
0x14004ee56  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ee5b  nop
0x14004ee5c  lea     rcx, [rsp+118h+var_A0]
0x14004ee61  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ee66  nop
0x14004ee67  lea     rcx, [rsp+118h+var_C0]
0x14004ee6c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ee71  nop
0x14004ee72  lea     rcx, [rsp+118h+var_F0]; this
0x14004ee77  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004ee7c  mov     eax, ebx
0x14004ee7e  jmp     short loc_14004EEEE
0x14004ee80  cmp     [r15], rax
0x14004ee83  jb      short loc_14004EE88
0x14004ee85  mov     [r15], r13
0x14004ee88  lea     rcx, [rsp+118h+String]
0x14004ee90  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ee95  nop
0x14004ee96  lea     rcx, [rsp+118h+var_A0]
0x14004ee9b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004eea0  nop
0x14004eea1  lea     rcx, [rsp+118h+var_C0]
0x14004eea6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004eeab  nop
0x14004eeac  mov     ebx, [rsp+118h+var_F8]
0x14004eeb0  jmp     loc_14004EA29
0x14004eeb5  mov     dword ptr [rsp+118h+var_F0], 2355h
0x14004eebd  mov     ebx, 8000FFFFh
0x14004eec2  mov     dword ptr [rsp+118h+var_F0+4], ebx
0x14004eec6  lea     rcx, [rsp+118h+var_C0]
0x14004eecb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
  ... truncated ...
```
