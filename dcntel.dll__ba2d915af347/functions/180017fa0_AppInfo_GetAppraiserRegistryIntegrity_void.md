# AppInfo::GetAppraiserRegistryIntegrity(void)

- ea: `0x180017fa0`
- end: `0x18001838c`
- name: `?GetAppraiserRegistryIntegrity@AppInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `1004`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800088e0`
- `0x180008dc0`
- `0x180009f14`
- `0x180014f2c`
- `0x18001502c`
- `0x180015fd4`
- `0x180016748`
- `0x1800167b4`
- `0x180016904`
- `0x180016db0`
- `0x180017fa0`
- `0x180019354`
- `0x180019970`
- `0x1800d331c`
- `0x18016796c`
- `0x18018e010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001821d`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001823e`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001821d`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001823e`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x180018286`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x180018286`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180018313`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180018313`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18001831d`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18001831d`
- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x18001825f`
- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x18001825f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018351`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018351`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800181a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800181a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001803d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001803d`

## string_xrefs

- `0x18001802f`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\TelemetryController\Appraiser`
- `0x18001806f`: `Binary;Command;Dependencies;Network;Sku;Frequency;SchedulingNeeded`
- `0x1800182ce`: `AppInfo::GetAppraiserRegistryIntegrity`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall AppInfo::GetAppraiserRegistryIntegrity(__int64 a1, __int64 a2)
{
  int v3; // r12d
  unsigned __int64 v4; // r15
  __int128 *v5; // r14
  char *v6; // rbx
  __int64 trivial_2; // rax
  __int64 v8; // rcx
  __int64 v9; // rsi
  unsigned __int64 v10; // r8
  __int128 *v11; // rax
  const WCHAR *v12; // rdx
  __int64 v13; // rax
  unsigned __int8 *i; // rsi
  unsigned __int8 *v15; // r14
  unsigned int v16; // ebx
  __int64 v17; // rax
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h]
  __int128 v23; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h]
  __int64 v25; // [rsp+70h] [rbp-90h]
  int v26; // [rsp+7Ch] [rbp-84h]
  _QWORD v27[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v28; // [rsp+90h] [rbp-70h] BYREF
  char v29[8]; // [rsp+98h] [rbp-68h] BYREF
  char v30[120]; // [rsp+A0h] [rbp-60h] BYREF
  char v31[104]; // [rsp+118h] [rbp+18h] BYREF
  __int128 v32; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 v33; // [rsp+190h] [rbp+90h]
  unsigned __int64 v34; // [rsp+198h] [rbp+98h]
  LPCWSTR lpValueName[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v36; // [rsp+1B0h] [rbp+B0h]
  BYTE Data[272]; // [rsp+1C0h] [rbp+C0h] BYREF

  v25 = a2;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)a2, L"#", 1u);
  v3 = 1;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\TelemetryController\\Appraiser",
          0,
          0x20019u,
          &hKey) )
  {
    v32 = 0;
    v33 = 0;
    v34 = 0;
    std::wstring::_Construct<1,unsigned short const *>(
      (char **)&v32,
      L"Binary;Command;Dependencies;Network;Sku;Frequency;SchedulingNeeded",
      0x42u);
    v4 = 0;
    v23 = 0;
    v24 = 0;
    while ( 1 )
    {
      v5 = &v32;
      if ( v34 > 7 )
        v5 = (__int128 *)v32;
      if ( v4 >= v33 )
        break;
      v6 = (char *)v5 + 2 * v33;
      trivial_2 = _std_find_trivial_2((char *)v5 + 2 * v4, v6, 59);
      if ( (char *)trivial_2 == v6 )
        break;
      v9 = (trivial_2 - (__int64)v5) >> 1;
      if ( v9 == -1 )
        break;
      *(_OWORD *)lpValueName = 0;
      v36 = 0;
      if ( v33 < v4 )
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v8);
      v10 = v33 - v4;
      if ( v33 - v4 >= v9 - v4 )
        v10 = v9 - v4;
      v11 = &v32;
      if ( v34 > 7 )
        v11 = (__int128 *)v32;
      std::wstring::_Construct<1,unsigned short const *>((char **)lpValueName, (char *)v11 + 2 * v4, v10);
      v3 |= 2u;
      v4 = v9 + 1;
      memset_0(Data, 0, 0x104u);
      cbData = 260;
      v12 = (const WCHAR *)lpValueName;
      if ( *((_QWORD *)&v36 + 1) > 7u )
        v12 = lpValueName[0];
      if ( !RegQueryValueExW(hKey, v12, 0, 0, Data, &cbData) )
        std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(
          &v23,
          *((_QWORD *)&v23 + 1),
          Data,
          cbData);
      std::wstring::~wstring((char **)lpValueName);
    }
    v21 = 0;
    v22 = 0;
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v27);
    if ( (int)Utils::GetSHA256CngHash((__int64)&v23, (__int64)&v21) < 0 )
    {
      AslLogCallPrintf(1, "AppInfo::GetAppraiserRegistryIntegrity", 210, "GetSHA256CngHash failed");
    }
    else
    {
      v13 = std::basic_ostream<unsigned short>::operator<<(&v28, std::internal);
      *(_WORD *)(*(int *)(*(_QWORD *)v13 + 4LL) + v13 + 88) = 48;
      std::basic_ostream<unsigned short>::operator<<(v13, std::hex);
      v15 = (unsigned __int8 *)*((_QWORD *)&v21 + 1);
      for ( i = (unsigned __int8 *)v21; i != v15; ++i )
      {
        v16 = *i;
        v17 = std::setw(lpValueName, 2);
        (*(void (__fastcall **)(char *, _QWORD))v17)(&v29[*(int *)(v28 + 4) - 8], *(_QWORD *)(v17 + 8));
        std::basic_ostream<unsigned short>::operator<<(&v28, v16);
      }
      std::basic_stringbuf<unsigned short>::str(v29, lpValueName);
      std::wstring::operator=(a2, lpValueName);
      std::wstring::~wstring((char **)lpValueName);
    }
    *(_QWORD *)((char *)v27 + *(int *)(v27[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
    *(int *)((char *)&v26 + *(int *)(v27[0] + 4LL)) = *(_DWORD *)(v27[0] + 4LL) - 152;
    std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v29);
    std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(v30);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v31);
    std::vector<unsigned char>::~vector<unsigned char>((char **)&v21);
    std::vector<unsigned char>::~vector<unsigned char>((char **)&v23);
    std::wstring::~wstring((char **)&v32);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return a2;
}

```

## disassembly

```asm
0x180017fa0  mov     [rsp-8+arg_0], rbx
0x180017fa5  mov     [rsp-8+arg_10], rsi
0x180017faa  push    rbp
0x180017fab  push    rdi
0x180017fac  push    r12
0x180017fae  push    r14
0x180017fb0  push    r15
0x180017fb2  lea     rbp, [rsp-1E0h]
0x180017fba  sub     rsp, 2E0h
0x180017fc1  mov     rax, cs:__security_cookie
0x180017fc8  xor     rax, rsp
0x180017fcb  mov     [rbp+200h+var_30], rax
0x180017fd2  mov     rdi, rdx
0x180017fd5  mov     [rsp+300h+var_290], rdx
0x180017fda  mov     ebx, 1
0x180017fdf  mov     [rsp+300h+var_2D0], ebx
0x180017fe3  xorps   xmm0, xmm0
0x180017fe6  movups  xmmword ptr [rdx], xmm0
0x180017fe9  mov     qword ptr [rdx+10h], 0
0x180017ff1  mov     qword ptr [rdx+18h], 0
0x180017ff9  mov     r8d, ebx
0x180017ffc  lea     rdx, asc_1801B4764; "#"
0x180018003  mov     rcx, rdi
0x180018006  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001800b  nop
0x18001800c  mov     r12d, ebx
0x18001800f  mov     [rsp+300h+var_2D0], ebx
0x180018013  mov     [rsp+300h+hKey], 0
0x18001801c  lea     rax, [rsp+300h+hKey]
0x180018021  mov     [rsp+300h+phkResult], rax; phkResult
0x180018026  mov     r9d, 20019h; samDesired
0x18001802c  xor     r8d, r8d; ulOptions
0x18001802f  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180018036  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001803d  call    cs:__imp_RegOpenKeyExW
0x180018043  test    eax, eax
0x180018045  jnz     loc_180018347
0x18001804b  xorps   xmm0, xmm0
0x18001804e  movups  [rbp+200h+var_180], xmm0
0x180018055  mov     [rbp+200h+var_170], 0
0x180018060  mov     [rbp+200h+var_168], 0
0x18001806b  lea     r8d, [rbx+41h]
0x18001806f  lea     rdx, aBinaryCommandD; "Binary;Command;Dependencies;Network;Sku"...
0x180018076  lea     rcx, [rbp+200h+var_180]
0x18001807d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018082  nop
0x180018083  xor     r15d, r15d
0x180018086  xorps   xmm0, xmm0
0x180018089  movdqu  [rsp+300h+var_2A8], xmm0
0x18001808f  mov     [rsp+300h+var_298], r15
0x180018094  mov     rax, [rbp+200h+var_170]
0x18001809b  lea     r14, [rbp+200h+var_180]
0x1800180a2  cmp     [rbp+200h+var_168], 7
0x1800180aa  cmova   r14, qword ptr [rbp+200h+var_180]
0x1800180b2  cmp     r15, rax
0x1800180b5  jnb     loc_1800181DF
0x1800180bb  lea     rbx, [r14+rax*2]
0x1800180bf  mov     r8d, 3Bh ; ';'
0x1800180c5  lea     rcx, [r14+r15*2]
0x1800180c9  mov     rdx, rbx
0x1800180cc  call    __std_find_trivial_2
0x1800180d1  mov     rsi, rax
0x1800180d4  cmp     rax, rbx
0x1800180d7  jz      loc_1800181DF
0x1800180dd  sub     rsi, r14
0x1800180e0  sar     rsi, 1
0x1800180e3  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800180e7  jz      loc_1800181DF
0x1800180ed  xorps   xmm0, xmm0
0x1800180f0  movups  xmmword ptr [rbp+200h+lpValueName], xmm0
0x1800180f7  xorps   xmm1, xmm1
0x1800180fa  movdqu  [rbp+200h+var_150], xmm1
0x180018102  mov     r8, [rbp+200h+var_170]
0x180018109  cmp     r8, r15
0x18001810c  jb      loc_180018386
0x180018112  mov     rax, rsi
0x180018115  sub     rax, r15
0x180018118  sub     r8, r15
0x18001811b  cmp     r8, rax
0x18001811e  cmovnb  r8, rax
0x180018122  lea     rax, [rbp+200h+var_180]
0x180018129  cmp     [rbp+200h+var_168], 7
0x180018131  cmova   rax, qword ptr [rbp+200h+var_180]
0x180018139  lea     rdx, [rax+r15*2]
0x18001813d  lea     rcx, [rbp+200h+lpValueName]
0x180018144  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018149  or      r12d, 2
0x18001814d  mov     [rsp+300h+var_2D0], r12d
0x180018152  lea     r15, [rsi+1]
0x180018156  mov     ebx, 104h
0x18001815b  mov     r8d, ebx; Size
0x18001815e  xor     edx, edx; Val
0x180018160  lea     rcx, [rbp+200h+Data]; void *
0x180018167  call    memset_0
0x18001816c  mov     [rsp+300h+cbData], ebx
0x180018170  lea     rdx, [rbp+200h+lpValueName]
0x180018177  cmp     qword ptr [rbp+200h+var_150+8], 7
0x18001817f  cmova   rdx, [rbp+200h+lpValueName]; lpValueName
0x180018187  lea     rax, [rsp+300h+cbData]
0x18001818c  mov     [rsp+300h+lpcbData], rax; lpcbData
0x180018191  lea     rax, [rbp+200h+Data]
0x180018198  mov     [rsp+300h+phkResult], rax; lpData
0x18001819d  xor     r9d, r9d; lpType
0x1800181a0  xor     r8d, r8d; lpReserved
0x1800181a3  mov     rcx, [rsp+300h+hKey]; hKey
0x1800181a8  call    cs:__imp_RegQueryValueExW
0x1800181ae  test    eax, eax
0x1800181b0  jnz     short loc_1800181CE
0x1800181b2  mov     r9d, [rsp+300h+cbData]
0x1800181b7  lea     r8, [rbp+200h+Data]
0x1800181be  mov     rdx, qword ptr [rsp+300h+var_2A8+8]
0x1800181c3  lea     rcx, [rsp+300h+var_2A8]
0x1800181c8  call    ??$_Insert_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,unsigned __int64)
0x1800181cd  nop
0x1800181ce  lea     rcx, [rbp+200h+lpValueName]
0x1800181d5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800181da  jmp     loc_180018094
0x1800181df  xorps   xmm0, xmm0
0x1800181e2  movdqu  [rsp+300h+var_2C0], xmm0
0x1800181e8  mov     [rsp+300h+var_2B0], 0
0x1800181f1  lea     rcx, [rbp+200h+var_280]
0x1800181f5  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x1800181fa  nop
0x1800181fb  lea     rdx, [rsp+300h+var_2C0]
0x180018200  lea     rcx, [rsp+300h+var_2A8]
0x180018205  call    ?GetSHA256CngHash@Utils@@SAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z; Utils::GetSHA256CngHash(std::vector<uchar> const &,std::vector<uchar> &)
0x18001820a  test    eax, eax
0x18001820c  js      loc_1800182C1
0x180018212  lea     rdx, ?internal@std@@YAAEAVios_base@1@AEAV21@@Z; std::internal(std::ios_base &)
0x180018219  lea     rcx, [rbp+200h+var_270]
0x18001821d  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x180018223  mov     rcx, [rax]
0x180018226  movsxd  rdx, dword ptr [rcx+4]
0x18001822a  mov     ecx, 30h ; '0'
0x18001822f  mov     [rdx+rax+58h], cx
0x180018234  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18001823b  mov     rcx, rax
0x18001823e  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x180018244  mov     rsi, qword ptr [rsp+300h+var_2C0]
0x180018249  mov     r14, qword ptr [rsp+300h+var_2C0+8]
0x18001824e  jmp     short loc_18001828F
0x180018250  movzx   ebx, byte ptr [rsi]
0x180018253  mov     edx, 2
0x180018258  lea     rcx, [rbp+200h+lpValueName]
0x18001825f  call    cs:__imp_?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z; std::setw(__int64)
0x180018265  mov     rcx, [rbp+200h+var_270]
0x180018269  movsxd  rdx, dword ptr [rcx+4]
0x18001826d  lea     rcx, [rbp+200h+var_270]
0x180018271  add     rcx, rdx
0x180018274  mov     rdx, [rax+8]
0x180018278  mov     rax, [rax]
0x18001827b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018280  mov     edx, ebx
0x180018282  lea     rcx, [rbp+200h+var_270]
0x180018286  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x18001828c  inc     rsi
0x18001828f  cmp     rsi, r14
0x180018292  jnz     short loc_180018250
0x180018294  lea     rdx, [rbp+200h+lpValueName]
0x18001829b  lea     rcx, [rbp+200h+var_268]
0x18001829f  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x1800182a4  lea     rdx, [rbp+200h+lpValueName]
0x1800182ab  mov     rcx, rdi
0x1800182ae  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800182b3  lea     rcx, [rbp+200h+lpValueName]
0x1800182ba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800182bf  jmp     short loc_1800182E0
0x1800182c1  lea     r9, aGetsha256cngha; "GetSHA256CngHash failed"
0x1800182c8  mov     r8d, 0D2h
0x1800182ce  lea     rdx, aAppinfoGetappr; "AppInfo::GetAppraiserRegistryIntegrity"
0x1800182d5  mov     ecx, 1
0x1800182da  call    AslLogCallPrintf
0x1800182df  nop
0x1800182e0  mov     rax, [rbp+200h+var_280]
0x1800182e4  movsxd  rcx, dword ptr [rax+4]
0x1800182e8  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x1800182ef  mov     [rbp+rcx+200h+var_280], rax
0x1800182f4  mov     rax, [rbp+200h+var_280]
0x1800182f8  movsxd  rcx, dword ptr [rax+4]
0x1800182fc  lea     edx, [rcx-98h]
0x180018302  mov     [rsp+rcx+300h+var_284], edx
0x180018306  lea     rcx, [rbp+200h+var_268]
0x18001830a  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x18001830f  lea     rcx, [rbp+200h+var_260]
0x180018313  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x180018319  lea     rcx, [rbp+200h+var_1E8]
0x18001831d  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180018323  nop
0x180018324  lea     rcx, [rsp+300h+var_2C0]
0x180018329  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18001832e  nop
0x18001832f  lea     rcx, [rsp+300h+var_2A8]
0x180018334  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180018339  nop
0x18001833a  lea     rcx, [rbp+200h+var_180]
0x180018341  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018346  nop
0x180018347  mov     rcx, [rsp+300h+hKey]; hKey
0x18001834c  test    rcx, rcx
0x18001834f  jz      short loc_180018358
0x180018351  call    cs:__imp_RegCloseKey
0x180018357  nop
0x180018358  mov     rax, rdi
0x18001835b  mov     rcx, [rbp+200h+var_30]
0x180018362  xor     rcx, rsp; StackCookie
0x180018365  call    __security_check_cookie
0x18001836a  lea     r11, [rsp+300h+var_20]
0x180018372  mov     rbx, [r11+30h]
0x180018376  mov     rsi, [r11+40h]
0x18001837a  mov     rsp, r11
0x18001837d  pop     r15
0x18001837f  pop     r14
0x180018381  pop     r12
0x180018383  pop     rdi
0x180018384  pop     rbp
0x180018385  retn
0x180018386  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
