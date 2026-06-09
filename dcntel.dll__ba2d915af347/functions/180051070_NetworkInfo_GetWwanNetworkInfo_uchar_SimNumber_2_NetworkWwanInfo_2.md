# NetworkInfo::GetWwanNetworkInfo(uchar,SimNumber_2,NetworkWwanInfo_2)

- ea: `0x180051070`
- end: `0x1800519a8`
- name: `?GetWwanNetworkInfo@NetworkInfo@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@EW4SimNumber_2@@W4NetworkWwanInfo_2@@@Z`
- size: `2360`
- prototype: ``
- caller_count: `9`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004fa10`
- `0x18004fb50`
- `0x18004fed8`
- `0x180050380`
- `0x1800504b0`
- `0x1800b7b50`
- `0x1800b7c90`
- `0x1800b8210`
- `0x1800b8340`

## callees

- `0x180008dc0`
- `0x180014f2c`
- `0x1800157b8`
- `0x180016748`
- `0x180016db0`
- `0x180019354`
- `0x18001daf0`
- `0x18001dcc8`
- `0x180051070`
- `0x180052544`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180051149`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180051149`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051171`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051185`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051199`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800511b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800511ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051171`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051185`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051199`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800511b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800511ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051988`

## string_xrefs

- `0x180051142`: `wwapi.dll`
- `0x180051167`: `WwanOpenHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NetworkInfo::GetWwanNetworkInfo(__int64 a1, unsigned __int8 a2, int a3, int a4)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rsi
  FARPROC v7; // rdi
  FARPROC v8; // r15
  void (*v9)(void); // r14
  FARPROC v10; // rax
  void (__fastcall *v11)(_QWORD, _QWORD); // r12
  unsigned int v12; // edx
  unsigned __int64 v13; // r14
  int v14; // ecx
  __int64 v15; // rsi
  int v16; // eax
  int v17; // eax
  __int64 v18; // rsi
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // eax
  int v22; // edx
  __int64 v23; // rdx
  signed int LastError; // eax
  int v26; // edx
  unsigned int v27; // r8d
  __int64 v28; // rcx
  void (*v29)(void); // [rsp+50h] [rbp-B0h]
  FARPROC v30; // [rsp+58h] [rbp-A8h]
  unsigned int *v33; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v34; // [rsp+80h] [rbp-80h]
  __int64 v35; // [rsp+88h] [rbp-78h] BYREF
  int v36; // [rsp+90h] [rbp-70h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  INT_PTR (__stdcall *v38)(); // [rsp+A0h] [rbp-60h]
  const int *v39; // [rsp+A8h] [rbp-58h] BYREF
  HMODULE hModule; // [rsp+B0h] [rbp-50h]
  int v41; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD *v42; // [rsp+C0h] [rbp-40h]
  __int64 v43; // [rsp+C8h] [rbp-38h]
  __int64 v44; // [rsp+D0h] [rbp-30h]
  __int128 v45; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v46; // [rsp+E8h] [rbp-18h]
  _OWORD v47[2]; // [rsp+F8h] [rbp-8h] BYREF
  _OWORD v48[2]; // [rsp+118h] [rbp+18h] BYREF

  v36 = a4;
  v44 = a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)a1, L"#", 1u);
  memset(v48, 0, sizeof(v48));
  std::wstring::_Construct<1,unsigned short const *>((char **)v48, L"#", 1u);
  v41 = 0;
  v35 = 0;
  v33 = 0;
  v37 = 0;
  v42 = 0;
  v43 = 0;
  memset(v47, 0, sizeof(v47));
  std::wstring::_Construct<1,unsigned short const *>((char **)v47, L"#", 1u);
  Library = LoadLibraryExW(L"wwapi.dll", 0, 0x800u);
  v39 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = Library;
  if ( !Library )
    goto LABEL_68;
  ProcAddress = GetProcAddress(Library, "WwanOpenHandle");
  v7 = GetProcAddress(hModule, "WwanEnumerateInterfaces");
  v8 = GetProcAddress(hModule, "WwanQueryInterface");
  v38 = v8;
  v9 = (void (*)(void))GetProcAddress(hModule, "WwanFreeMemory");
  v29 = v9;
  v10 = GetProcAddress(hModule, "WwanCloseHandle");
  v11 = (void (__fastcall *)(_QWORD, _QWORD))v10;
  v30 = v10;
  if ( !ProcAddress || !v7 || !v8 || !v9 || !v10 )
    goto LABEL_68;
  if ( ((unsigned int (__fastcall *)(__int64, _QWORD, int *, __int64 *))ProcAddress)(1, 0, &v41, &v35) )
    goto LABEL_62;
  if ( !v35 )
    goto LABEL_62;
  if ( ((unsigned int (__fastcall *)(__int64, _QWORD, unsigned int **))v7)(v35, 0, &v33) )
    goto LABEL_62;
  if ( !v33 )
    goto LABEL_62;
  v12 = 0;
  v34 = 0;
  if ( !*v33 )
    goto LABEL_62;
  v13 = -1;
  v14 = a3;
  while ( 1 )
  {
    if ( !v14 )
      goto LABEL_23;
    v15 = 147LL * v12;
    v16 = ((__int64 (__fastcall *)(__int64, unsigned int *, __int64))v8)(v35, &v33[v15 + 1], 46);
    if ( v16 )
    {
      if ( v16 != 50 )
        goto LABEL_61;
      v17 = 0;
LABEL_28:
      v14 = a3;
      if ( a3 != 1 )
        goto LABEL_57;
      goto LABEL_20;
    }
    if ( !*v42 )
      goto LABEL_61;
    v17 = 0;
    if ( *v42 <= 1u )
      goto LABEL_28;
    if ( ((unsigned int (__fastcall *)(__int64, unsigned int *, __int64))v8)(v35, &v33[v15 + 1], 47) )
      goto LABEL_61;
    v17 = *(_DWORD *)(v43 + 8);
    if ( !v17 )
      goto LABEL_28;
    v14 = a3;
LABEL_20:
    if ( v17 == 1 && v14 != 2 )
      goto LABEL_57;
    v12 = v34;
LABEL_23:
    v18 = 147LL * v12;
    if ( ((unsigned int (__fastcall *)(__int64, unsigned int *, __int64))v8)(v35, &v33[v18 + 1], 7) )
      goto LABEL_61;
    switch ( MEMORY[0] )
    {
      case 0x8D8:
        v19 = 1432;
        v20 = 1680;
        v21 = MEMORY[0x8D4];
        goto LABEL_37;
      case 0x8B8:
        v19 = 1432;
        v20 = 1680;
        v21 = MEMORY[0x8B4];
        goto LABEL_37;
      case 0x7B0:
        v20 = 1620;
        v21 = MEMORY[0x7AC];
        goto LABEL_36;
    }
    if ( MEMORY[0] == 1960 )
      break;
LABEL_56:
    v14 = a3;
LABEL_57:
    v12 = v34 + 1;
    v34 = v12;
    if ( v12 >= *v33 )
      goto LABEL_61;
  }
  v20 = 1612;
  v21 = MEMORY[0x7A4];
LABEL_36:
  v19 = 1384;
LABEL_37:
  if ( MEMORY[0x228] == 1 || (v22 = 0, v21) )
    v22 = 1;
  if ( a2 != v22 )
  {
LABEL_55:
    v8 = v38;
    goto LABEL_56;
  }
  if ( v36 )
  {
    v23 = (unsigned int)(v36 - 1);
    if ( v36 == 1 )
    {
      if ( !*(_DWORD *)(v19 + 208) )
      {
        v23 = v19 + 26;
        if ( *(_WORD *)(v19 + 26) )
        {
          if ( !*(_DWORD *)(v20 + 256) && *(_DWORD *)(v20 + 8) == 1 )
          {
            v45 = 0;
            v46 = 0;
            do
              ++v13;
            while ( *(_WORD *)(v23 + 2 * v13) );
            goto LABEL_60;
          }
        }
      }
    }
    else
    {
      v23 = (unsigned int)(v36 - 2);
      if ( (unsigned int)v23 <= 1 )
      {
        ((__int64 (__fastcall *)(__int64, unsigned int *, __int64))v38)(v35, &v33[v18 + 1], 36);
        goto LABEL_61;
      }
    }
    if ( v37 )
    {
      ((void (__fastcall *)(__int64, __int64, __int64, __int64))v29)(v37, v23, v19, v20);
      v37 = 0;
    }
    goto LABEL_55;
  }
  v23 = 652;
  v45 = 0;
  v46 = 0;
  do
    ++v13;
  while ( *(_WORD *)(2 * v13 + 0x28C) );
LABEL_60:
  std::wstring::_Construct<1,unsigned short const *>((char **)&v45, (const void *)v23, v13);
  std::wstring::operator=(a1, &v45);
  std::wstring::~wstring((char **)&v45);
LABEL_61:
  v9 = v29;
  v11 = (void (__fastcall *)(_QWORD, _QWORD))v30;
LABEL_62:
  if ( v33 )
    v9();
  if ( v35 )
    v11(v35, 0);
  if ( v37 )
    v9();
LABEL_68:
  v39 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v39) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v26, v27);
      std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v28);
    }
    hModule = 0;
  }
  std::wstring::~wstring((char **)v47);
  std::wstring::~wstring((char **)v48);
  return a1;
}

```

## disassembly

```asm
0x180051070  push    rbp
0x180051072  push    rbx
0x180051073  push    rsi
0x180051074  push    rdi
0x180051075  push    r12
0x180051077  push    r13
0x180051079  push    r14
0x18005107b  push    r15
0x18005107d  lea     rbp, [rsp-48h]
0x180051082  sub     rsp, 148h
0x180051089  mov     rax, cs:__security_cookie
0x180051090  xor     rax, rsp
0x180051093  mov     [rbp+80h+var_48], rax
0x180051097  mov     [rbp+80h+var_F0], r9d
0x18005109b  mov     [rsp+180h+var_11C], r8d
0x1800510a0  mov     [rsp+180h+var_120], dl
0x1800510a4  mov     rbx, rcx
0x1800510a7  mov     [rbp+80h+var_B0], rcx
0x1800510ab  xor     r14d, r14d
0x1800510ae  mov     [rsp+180h+var_114], r14d
0x1800510b3  xorps   xmm0, xmm0
0x1800510b6  movups  xmmword ptr [rcx], xmm0
0x1800510b9  mov     [rcx+10h], r14
0x1800510bd  mov     [rcx+18h], r14
0x1800510c1  lea     esi, [r14+1]
0x1800510c5  mov     r8d, esi
0x1800510c8  lea     rdi, asc_1801B4764; "#"
0x1800510cf  mov     rdx, rdi
0x1800510d2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800510d7  mov     r13d, esi
0x1800510da  mov     [rsp+180h+var_114], esi
0x1800510de  xorps   xmm0, xmm0
0x1800510e1  movups  [rbp+80h+var_68], xmm0
0x1800510e5  xorps   xmm1, xmm1
0x1800510e8  movdqu  [rbp+80h+var_58], xmm1
0x1800510ed  mov     r8d, esi
0x1800510f0  mov     rdx, rdi
0x1800510f3  lea     rcx, [rbp+80h+var_68]
0x1800510f7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800510fc  nop
0x1800510fd  mov     [rbp+80h+var_C8], r14d
0x180051101  mov     [rbp+80h+var_F8], r14
0x180051105  mov     [rsp+180h+var_108], r14
0x18005110a  mov     [rsp+180h+var_110], r14
0x18005110f  mov     [rbp+80h+var_E8], r14
0x180051113  mov     [rbp+80h+var_C0], r14
0x180051117  mov     [rbp+80h+var_B8], r14
0x18005111b  xorps   xmm0, xmm0
0x18005111e  movups  [rbp+80h+var_88], xmm0
0x180051122  xorps   xmm1, xmm1
0x180051125  movdqu  [rbp+80h+var_78], xmm1
0x18005112a  mov     r8d, esi
0x18005112d  mov     rdx, rdi
0x180051130  lea     rcx, [rbp+80h+var_88]
0x180051134  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180051139  nop
0x18005113a  xor     edx, edx; hFile
0x18005113c  mov     r8d, 800h; dwFlags
0x180051142  lea     rcx, aWwapiDll; "wwapi.dll"
0x180051149  call    cs:__imp_LoadLibraryExW
0x18005114f  lea     rcx, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180051156  mov     [rbp+80h+var_D8], rcx
0x18005115a  mov     [rbp+80h+hModule], rax
0x18005115e  test    rax, rax
0x180051161  jz      loc_180051930
0x180051167  lea     rdx, aWwanopenhandle; "WwanOpenHandle"
0x18005116e  mov     rcx, rax; hModule
0x180051171  call    cs:__imp_GetProcAddress
0x180051177  mov     rsi, rax
0x18005117a  lea     rdx, aWwanenumeratei; "WwanEnumerateInterfaces"
0x180051181  mov     rcx, [rbp+80h+hModule]; hModule
0x180051185  call    cs:__imp_GetProcAddress
0x18005118b  mov     rdi, rax
0x18005118e  lea     rdx, aWwanqueryinter; "WwanQueryInterface"
0x180051195  mov     rcx, [rbp+80h+hModule]; hModule
0x180051199  call    cs:__imp_GetProcAddress
0x18005119f  mov     r15, rax
0x1800511a2  mov     [rbp+80h+var_E0], rax
0x1800511a6  lea     rdx, aWwanfreememory; "WwanFreeMemory"
0x1800511ad  mov     rcx, [rbp+80h+hModule]; hModule
0x1800511b1  call    cs:__imp_GetProcAddress
0x1800511b7  mov     r14, rax
0x1800511ba  mov     [rsp+180h+var_130], rax
0x1800511bf  lea     rdx, aWwanclosehandl; "WwanCloseHandle"
0x1800511c6  mov     rcx, [rbp+80h+hModule]; hModule
0x1800511ca  call    cs:__imp_GetProcAddress
0x1800511d0  mov     r12, rax
0x1800511d3  mov     [rsp+180h+var_128], rax
0x1800511d8  test    rsi, rsi
0x1800511db  jz      loc_18005192D
0x1800511e1  test    rdi, rdi
0x1800511e4  jz      loc_18005192D
0x1800511ea  test    r15, r15
0x1800511ed  jz      loc_18005192D
0x1800511f3  test    r14, r14
0x1800511f6  jz      loc_18005192D
0x1800511fc  test    rax, rax
0x1800511ff  jz      loc_18005192D
0x180051205  lea     r9, [rbp+80h+var_F8]
0x180051209  lea     r8, [rbp+80h+var_C8]
0x18005120d  xor     edx, edx
0x18005120f  lea     ecx, [rdx+1]
0x180051212  mov     rax, rsi
0x180051215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005121a  test    eax, eax
0x18005121c  jnz     loc_1800518E5
0x180051222  mov     rcx, [rbp+80h+var_F8]
0x180051226  test    rcx, rcx
0x180051229  jz      loc_1800518E5
0x18005122f  lea     r8, [rsp+180h+var_108]
0x180051234  xor     edx, edx
0x180051236  mov     rax, rdi
0x180051239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005123e  xor     r11d, r11d
0x180051241  test    eax, eax
0x180051243  jnz     loc_1800518E5
0x180051249  mov     rcx, [rsp+180h+var_108]
0x18005124e  test    rcx, rcx
0x180051251  jz      loc_1800518E5
0x180051257  mov     edx, r11d
0x18005125a  mov     [rbp+80h+var_100], edx
0x18005125d  cmp     [rcx], r11d
0x180051260  jbe     loc_1800518E5
0x180051266  lea     edi, [rax+2]
0x180051269  or      r14, 0FFFFFFFFFFFFFFFFh
0x18005126d  lea     r12d, [r11+3]
0x180051271  mov     ecx, [rsp+180h+var_11C]
0x180051275  mov     [rsp+180h+var_118], r11d
0x18005127a  test    ecx, ecx
0x18005127c  jz      loc_180051354
0x180051282  mov     eax, edx
0x180051284  imul    rsi, rax, 24Ch
0x18005128b  mov     rdx, [rsp+180h+var_108]
0x180051290  add     rdx, 4
0x180051294  add     rdx, rsi
0x180051297  xor     eax, eax
0x180051299  mov     [rsp+180h+var_148], rax
0x18005129e  mov     [rsp+180h+var_150], rax
0x1800512a3  lea     rax, [rbp+80h+var_C0]
0x1800512a7  mov     [rsp+180h+var_158], rax
0x1800512ac  lea     rax, [rsp+180h+var_118]
0x1800512b1  mov     [rsp+180h+var_160], rax
0x1800512b6  xor     r9d, r9d
0x1800512b9  lea     r8d, [r9+2Eh]
0x1800512bd  mov     rcx, [rbp+80h+var_F8]
0x1800512c1  mov     rax, r15
0x1800512c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800512c9  xor     ecx, ecx
0x1800512cb  test    eax, eax
0x1800512cd  jnz     loc_1800513D5
0x1800512d3  mov     rax, [rbp+80h+var_C0]
0x1800512d7  mov     ecx, [rax]
0x1800512d9  xor     r9d, r9d
0x1800512dc  test    ecx, ecx
0x1800512de  jz      loc_1800518DB
0x1800512e4  mov     eax, r9d
0x1800512e7  cmp     ecx, 1
0x1800512ea  jbe     loc_1800513E0
0x1800512f0  mov     rdx, [rsp+180h+var_108]
0x1800512f5  add     rdx, 4
0x1800512f9  add     rdx, rsi
0x1800512fc  mov     [rsp+180h+var_148], rax
0x180051301  mov     [rsp+180h+var_150], rax
0x180051306  lea     rax, [rbp+80h+var_B8]
0x18005130a  mov     [rsp+180h+var_158], rax
0x18005130f  lea     rax, [rsp+180h+var_118]
0x180051314  mov     [rsp+180h+var_160], rax
0x180051319  lea     r8d, [r9+2Fh]
0x18005131d  mov     rcx, [rbp+80h+var_F8]
0x180051321  mov     rax, r15
0x180051324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051329  test    eax, eax
0x18005132b  jnz     loc_1800518DB
0x180051331  mov     rax, [rbp+80h+var_B8]
0x180051335  mov     eax, [rax+8]
0x180051338  test    eax, eax
0x18005133a  jz      loc_1800513E0
0x180051340  mov     ecx, [rsp+180h+var_11C]
0x180051344  cmp     eax, 1
0x180051347  jnz     short loc_180051351
0x180051349  cmp     ecx, edi
0x18005134b  jnz     loc_1800513ED
0x180051351  mov     edx, [rbp+80h+var_100]
0x180051354  mov     eax, edx
0x180051356  imul    rsi, rax, 24Ch
0x18005135d  mov     rdx, [rsp+180h+var_108]
0x180051362  add     rdx, 4
0x180051366  add     rdx, rsi
0x180051369  xor     eax, eax
0x18005136b  mov     [rsp+180h+var_148], rax
0x180051370  mov     [rsp+180h+var_150], rax
0x180051375  lea     rax, [rsp+180h+var_110]
0x18005137a  mov     [rsp+180h+var_158], rax
0x18005137f  lea     rax, [rsp+180h+var_118]
0x180051384  mov     [rsp+180h+var_160], rax
0x180051389  xor     r9d, r9d
0x18005138c  lea     r8d, [r9+7]
0x180051390  mov     rcx, [rbp+80h+var_F8]
0x180051394  mov     rax, r15
0x180051397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005139c  xor     r11d, r11d
0x18005139f  test    eax, eax
0x1800513a1  jnz     loc_1800518DB
0x1800513a7  mov     rcx, [rsp+180h+var_110]
0x1800513ac  mov     eax, [rcx]
0x1800513ae  cmp     eax, 8D8h
0x1800513b3  jnz     short loc_1800513F5
0x1800513b5  lea     r15, [rcx+500h]
0x1800513bc  lea     r8, [rcx+598h]
0x1800513c3  lea     r9, [rcx+690h]
0x1800513ca  mov     eax, [rcx+8D4h]
0x1800513d0  jmp     loc_180051464
0x1800513d5  cmp     eax, 32h ; '2'
0x1800513d8  jnz     loc_1800518DB
0x1800513de  mov     eax, ecx
0x1800513e0  mov     ecx, [rsp+180h+var_11C]
0x1800513e4  cmp     ecx, 1
0x1800513e7  jz      loc_180051344
0x1800513ed  xor     r11d, r11d
0x1800513f0  jmp     loc_18005171C
0x1800513f5  cmp     eax, 8B8h
0x1800513fa  jnz     short loc_18005141E
0x1800513fc  mov     rcx, [rsp+180h+var_110]
0x180051401  lea     r15, [rcx+500h]
0x180051408  lea     r8, [rcx+598h]
0x18005140f  lea     r9, [rcx+690h]
0x180051416  mov     eax, [rcx+8B4h]
0x18005141c  jmp     short loc_180051464
0x18005141e  cmp     eax, 7B0h
0x180051423  jnz     short loc_180051439
0x180051425  mov     rcx, [rsp+180h+var_110]
0x18005142a  lea     r9, [rcx+654h]
0x180051431  mov     eax, [rcx+7ACh]
0x180051437  jmp     short loc_180051456
0x180051439  cmp     eax, 7A8h
0x18005143e  jnz     loc_180051718
0x180051444  mov     rcx, [rsp+180h+var_110]
0x180051449  lea     r9, [rcx+64Ch]
0x180051450  mov     eax, [rcx+7A4h]
0x180051456  lea     r8, [rcx+568h]
0x18005145d  lea     r15, [rcx+4D0h]
0x180051464  cmp     dword ptr [rcx+228h], 1
0x18005146b  jz      short loc_180051474
0x18005146d  test    eax, eax
0x18005146f  mov     edx, r11d
0x180051472  jz      short loc_180051479
0x180051474  mov     edx, 1
0x180051479  movzx   eax, [rsp+180h+var_120]
0x18005147e  cmp     eax, edx
0x180051480  jnz     loc_180051714
0x180051486  mov     r10d, [rbp+80h+var_F0]
0x18005148a  mov     edx, r10d
0x18005148d  test    r10d, r10d
0x180051490  jz      loc_1800516CB
0x180051496  sub     edx, 1
0x180051499  jz      loc_180051689
0x18005149f  sub     edx, 1
0x1800514a2  jz      short loc_1800514AD
0x1800514a4  cmp     edx, 1
0x1800514a7  jnz     loc_1800516DD
0x1800514ad  mov     rdx, [rsp+180h+var_108]
0x1800514b2  add     rdx, 4
0x1800514b6  add     rdx, rsi
0x1800514b9  xor     eax, eax
0x1800514bb  mov     [rsp+180h+var_148], rax
0x1800514c0  mov     [rsp+180h+var_150], rax
0x1800514c5  lea     rax, [rbp+80h+var_E8]
0x1800514c9  mov     [rsp+180h+var_158], rax
0x1800514ce  lea     rax, [rsp+180h+var_118]
0x1800514d3  mov     [rsp+180h+var_160], rax
0x1800514d8  xor     r9d, r9d
0x1800514db  lea     r8d, [r9+24h]
0x1800514df  mov     rcx, [rbp+80h+var_F8]
0x1800514e3  mov     rax, [rbp+80h+var_E0]
0x1800514e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800514ec  xor     r9d, r9d
0x1800514ef  test    eax, eax
0x1800514f1  jnz     loc_1800518DB
0x1800514f7  mov     rcx, [rbp+80h+var_E8]
0x1800514fb  test    rcx, rcx
0x1800514fe  jz      loc_1800518DB
0x180051504  cmp     [rsp+180h+var_118], 5Ch ; '\'
0x180051509  jb      loc_1800518DB
0x18005150f  cmp     [rcx], edi
0x180051511  jz      loc_180051871
0x180051517  cmp     dword ptr [rcx], 1
0x18005151a  jnz     loc_180051841
0x180051520  lea     rdx, [rcx+8]
0x180051524  xorps   xmm0, xmm0
0x180051527  movups  [rbp+80h+var_A8], xmm0
0x18005152b  xorps   xmm1, xmm1
0x18005152e  movdqu  [rbp+80h+var_98], xmm1
0x180051533  mov     r8, r14
0x180051536  inc     r8
0x180051539  cmp     [rdx+r8*2], r9w
0x18005153e  jnz     short loc_180051536
0x180051540  lea     rcx, [rbp+80h+var_A8]
0x180051544  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180051549  lea     rdx, [rbp+80h+var_A8]
0x18005154d  lea     rcx, [rbp+80h+var_68]
  ... truncated ...
```
