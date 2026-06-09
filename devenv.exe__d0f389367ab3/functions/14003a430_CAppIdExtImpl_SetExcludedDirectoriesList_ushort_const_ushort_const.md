# CAppIdExtImpl::SetExcludedDirectoriesList(ushort const *,ushort const *)

- ea: `0x14003a430`
- end: `0x14003a6e4`
- name: `?SetExcludedDirectoriesList@CAppIdExtImpl@@KAJPEBG0@Z`
- size: `692`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x14000905c`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002c10`
- `0x140003160`
- `0x140009b10`
- `0x140009ba4`
- `0x140017330`
- `0x140033ab0`
- `0x14003734c`
- `0x140039b24`
- `0x14003a430`
- `0x14003ab18`
- `0x14003b6bc`
- `0x14003be28`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14003a660`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14003a66b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14003a676`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14003a660`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14003a66b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14003a676`
- `MSVCP140!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003a636`
- `MSVCP140!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003a636`
- `MSVCP140!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x14003a537`
- `MSVCP140!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x14003a537`
- `MSVCP140!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003a640`
- `MSVCP140!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003a640`
- `MSVCP140!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x14003a547`
- `MSVCP140!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x14003a547`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x14003a5d8`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x14003a5d8`
- `api-ms-win-crt-filesystem-l1-1-0!_wremove` at `0x14003a64d`
- `api-ms-win-crt-filesystem-l1-1-0!_wremove` at `0x14003a64d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CAppIdExtImpl::SetExcludedDirectoriesList(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  _QWORD *LocalAppDataStoragePath; // rax
  _QWORD *v4; // rdx
  int v5; // ebx
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned int v11; // edi
  struct ATL::IAtlStringMgr *Instance; // rax
  __int64 v13; // rbx
  HINSTANCE StringResourceInstance; // rax
  int v15; // eax
  int *v16; // rax
  wchar_t *v17; // rdx
  wchar_t *FileName[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[8]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v22[152]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v23[104]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v24; // [rsp+150h] [rbp+50h] BYREF

  FileName[0] = 0;
  LocalAppDataStoragePath = (_QWORD *)CAppIdExtImpl::GetLocalAppDataStoragePath(&v24, a1);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    FileName,
    *LocalAppDataStoragePath);
  v4 = (_QWORD *)(v24 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v24 - 24 + 16)) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 8LL))(*v4);
  }
  ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
    FileName,
    L"ExcludedDirectories.lst");
  v5 = 1;
  if ( a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    if ( v6 )
    {
      memset_0(&v20, 0, 0x108u);
      std::ofstream::ofstream(&v20, FileName[0]);
      while ( 1 )
      {
        v10 = v20;
        if ( (v22[*(int *)(v20 + 4)] & 2) == 0 )
          break;
        v7 = v5++;
        if ( v7 >= 10 )
          break;
        v8 = std::filebuf::open(v21, FileName[0], 34);
        v9 = *(int *)(v20 + 4);
        if ( v8 )
          std::ios::clear(&v21[v9 - 8], 0, 0);
        else
          std::ios::setstate(&v21[v9 - 8], 2, 0);
      }
      if ( (v22[*(int *)(v20 + 4)] & 2) != 0 )
      {
        v11 = -2147024891;
LABEL_24:
        *(_QWORD *)&v21[*(int *)(v10 + 4) - 8] = &std::ofstream::`vftable';
        *(_DWORD *)((char *)&FileName[1] + *(int *)(v20 + 4) + 4) = *(_DWORD *)(v20 + 4) - 168;
        std::filebuf::~filebuf<char,std::char_traits<char>>(v21);
        std::ostream::~ostream<char,std::char_traits<char>>(v22);
        std::ios::~ios<char,std::char_traits<char>>(v23);
        goto LABEL_33;
      }
      Instance = ATL::CAtlStringMgr::GetInstance();
      if ( !Instance )
        ATL::AtlThrowImpl(-2147467259);
      v13 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
      v24 = v13;
      if ( (unsigned __int64)a2 >= 0x10000 )
      {
        CRegKeyPathToDetour::CMyStringT<char>::operator=(&v24, a2);
      }
      else
      {
        StringResourceInstance = ATL::AtlFindStringResourceInstance((unsigned __int16)a2, 0);
        if ( !StringResourceInstance )
        {
LABEL_21:
          std::ostream::write(&v20, v13, *(int *)(v13 - 16));
          v11 = 0;
          if ( _InterlockedDecrement((volatile signed __int32 *)(v13 - 24 + 16)) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v13 - 24) + 8LL))(*(_QWORD *)(v13 - 24));
          }
          v10 = v20;
          goto LABEL_24;
        }
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::LoadStringW(
          &v24,
          StringResourceInstance,
          (unsigned __int16)a2);
      }
      v13 = v24;
      goto LABEL_21;
    }
  }
  do
  {
    if ( !_wremove(FileName[0]) )
      goto LABEL_32;
    v15 = v5++;
  }
  while ( v15 < 10 && *_errno() != 2 );
  if ( *_errno() == 2 )
  {
LABEL_32:
    v11 = 0;
    goto LABEL_33;
  }
  v16 = _errno();
  v11 = *(unsigned __int16 *)v16 | 0x80070000;
  if ( *v16 <= 0 )
    v11 = *v16;
LABEL_33:
  v17 = FileName[0] - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)FileName[0] - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v17 + 8LL))(*(_QWORD *)v17);
  }
  return v11;
}

```

## disassembly

```asm
0x14003a430  mov     [rsp-8+arg_10], rbx
0x14003a435  mov     [rsp-8+arg_18], rsi
0x14003a43a  push    rbp
0x14003a43b  push    rdi
0x14003a43c  push    r14
0x14003a43e  lea     rbp, [rsp-60h]
0x14003a443  sub     rsp, 160h
0x14003a44a  mov     rax, cs:__security_cookie
0x14003a451  xor     rax, rsp
0x14003a454  mov     [rbp+70h+var_18], rax
0x14003a458  mov     rdi, rdx
0x14003a45b  xor     esi, esi
0x14003a45d  mov     [rsp+170h+FileName], rsi
0x14003a462  mov     rdx, rcx
0x14003a465  lea     rcx, [rbp+70h+var_20]
0x14003a469  call    ?GetLocalAppDataStoragePath@CAppIdExtImpl@@KA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z
0x14003a46e  mov     rdx, [rax]
0x14003a471  lea     rcx, [rsp+170h+FileName]
0x14003a476  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z
0x14003a47b  mov     rdx, [rbp+70h+var_20]
0x14003a47f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14003a483  or      r14, 0FFFFFFFFFFFFFFFFh
0x14003a487  mov     eax, r14d
0x14003a48a  lock xadd [rdx+10h], eax
0x14003a48f  add     eax, r14d
0x14003a492  test    eax, eax
0x14003a494  jg      short loc_14003A4A2
0x14003a496  lfence
0x14003a499  mov     rcx, [rdx]
0x14003a49c  mov     rax, [rcx]
0x14003a49f  call    qword ptr [rax+8]
0x14003a4a2  lea     rdx, aExcludeddirect
0x14003a4a9  lea     rcx, [rsp+170h+FileName]
0x14003a4ae  call    ?Append@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z
0x14003a4b3  mov     ebx, 1
0x14003a4b8  test    rdi, rdi
0x14003a4bb  jz      loc_14003A648
0x14003a4c1  mov     rax, r14
0x14003a4c4  inc     rax
0x14003a4c7  cmp     [rdi+rax*2], si
0x14003a4cb  jnz     short loc_14003A4C4
0x14003a4cd  test    rax, rax
0x14003a4d0  jz      loc_14003A648
0x14003a4d6  xor     edx, edx; Val
0x14003a4d8  mov     r8d, 108h; Size
0x14003a4de  lea     rcx, [rsp+170h+var_130]; void *
0x14003a4e3  call    memset_0
0x14003a4e8  mov     rdx, [rsp+170h+FileName]
0x14003a4ed  lea     rcx, [rsp+170h+var_130]
0x14003a4f2  call    ??0?$basic_ofstream@DU?$char_traits@D@std@@@std@@QEAA@PEBGHH@Z
0x14003a4f7  nop
0x14003a4f8  jmp     short loc_14003A54D
0x14003a4fa  mov     eax, ebx
0x14003a4fc  inc     ebx
0x14003a4fe  cmp     eax, 0Ah
0x14003a501  jge     short loc_14003A55D
0x14003a503  mov     r9d, 10h
0x14003a509  lea     r8d, [r9+12h]
0x14003a50d  mov     rdx, [rsp+170h+FileName]
0x14003a512  lea     rcx, [rsp+170h+var_128]
0x14003a517  call    ?open@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@PEBGHH@Z
0x14003a51c  xor     r8d, r8d
0x14003a51f  test    rax, rax
0x14003a522  mov     rax, [rsp+170h+var_130]
0x14003a527  movsxd  rcx, dword ptr [rax+4]
0x14003a52b  lea     rax, [rsp+170h+var_130]
0x14003a530  jz      short loc_14003A53F
0x14003a532  add     rcx, rax
0x14003a535  xor     edx, edx
0x14003a537  call    cs:__imp_?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z
0x14003a53d  jmp     short loc_14003A54D
0x14003a53f  add     rcx, rax
0x14003a542  mov     edx, 2
0x14003a547  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z
0x14003a54d  mov     rcx, [rsp+170h+var_130]
0x14003a552  movsxd  rax, dword ptr [rcx+4]
0x14003a556  test    [rsp+rax+170h+var_120], 2
0x14003a55b  jnz     short loc_14003A4FA
0x14003a55d  movsxd  rax, dword ptr [rcx+4]
0x14003a561  test    [rsp+rax+170h+var_120], 2
0x14003a566  jz      short loc_14003A572
0x14003a568  mov     edi, 80070005h
0x14003a56d  jmp     loc_14003A604
0x14003a572  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ
0x14003a577  mov     rcx, rax
0x14003a57a  test    rax, rax
0x14003a57d  jz      loc_14003A6D9
0x14003a583  mov     rax, [rax]
0x14003a586  call    qword ptr [rax+18h]
0x14003a589  lea     rbx, [rax+18h]
0x14003a58d  mov     [rbp+70h+var_20], rbx
0x14003a591  cmp     rdi, 10000h
0x14003a598  jnb     short loc_14003A5BC
0x14003a59a  movzx   edi, di
0x14003a59d  xor     edx, edx; unsigned __int16
0x14003a59f  mov     ecx, edi; unsigned int
0x14003a5a1  call    ?AtlFindStringResourceInstance@ATL@@YAPEAUHINSTANCE__@@IG@Z
0x14003a5a6  test    rax, rax
0x14003a5a9  jz      short loc_14003A5CC
0x14003a5ab  mov     r8d, edi
0x14003a5ae  mov     rdx, rax
0x14003a5b1  lea     rcx, [rbp+70h+var_20]
0x14003a5b5  call    ?LoadStringW@?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z
0x14003a5ba  jmp     short loc_14003A5C8
0x14003a5bc  mov     rdx, rdi
0x14003a5bf  lea     rcx, [rbp+70h+var_20]
0x14003a5c3  call    ??4?$CMyStringT@D@CRegKeyPathToDetour@@QEAAAEAV01@PEBG@Z
0x14003a5c8  mov     rbx, [rbp+70h+var_20]
0x14003a5cc  movsxd  r8, dword ptr [rbx-10h]
0x14003a5d0  mov     rdx, rbx
0x14003a5d3  lea     rcx, [rsp+170h+var_130]
0x14003a5d8  call    cs:__imp_?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z
0x14003a5de  mov     edi, esi
0x14003a5e0  lea     rdx, [rbx-18h]
0x14003a5e4  mov     eax, r14d
0x14003a5e7  lock xadd [rdx+10h], eax
0x14003a5ec  add     eax, r14d
0x14003a5ef  test    eax, eax
0x14003a5f1  jg      short loc_14003A5FF
0x14003a5f3  lfence
0x14003a5f6  mov     rcx, [rdx]
0x14003a5f9  mov     rax, [rcx]
0x14003a5fc  call    qword ptr [rax+8]
0x14003a5ff  mov     rcx, [rsp+170h+var_130]
0x14003a604  movsxd  rax, dword ptr [rcx+4]
0x14003a608  lea     rcx, ??_7?$basic_ofstream@DU?$char_traits@D@std@@@std@@6B@
0x14003a60f  mov     [rsp+rax+170h+var_130], rcx
0x14003a614  mov     rax, [rsp+170h+var_130]
0x14003a619  movsxd  rcx, dword ptr [rax+4]
0x14003a61d  lea     edx, [rcx-0A8h]
0x14003a623  mov     [rsp+rcx+170h+var_134], edx
0x14003a627  lea     rcx, [rsp+170h+var_128]
0x14003a62c  call    ??1?$basic_filebuf@DU?$char_traits@D@std@@@std@@UEAA@XZ
0x14003a631  lea     rcx, [rsp+170h+var_120]
0x14003a636  call    cs:__imp_??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ
0x14003a63c  lea     rcx, [rbp+70h+var_88]
0x14003a640  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ
0x14003a646  jmp     short loc_14003A68E
0x14003a648  mov     rcx, [rsp+170h+FileName]; FileName
0x14003a64d  call    cs:__imp__wremove
0x14003a653  test    eax, eax
0x14003a655  jz      short loc_14003A68C
0x14003a657  mov     eax, ebx
0x14003a659  inc     ebx
0x14003a65b  cmp     eax, 0Ah
0x14003a65e  jge     short loc_14003A66B
0x14003a660  call    cs:__imp__errno
0x14003a666  cmp     dword ptr [rax], 2
0x14003a669  jnz     short loc_14003A648
0x14003a66b  call    cs:__imp__errno
0x14003a671  cmp     dword ptr [rax], 2
0x14003a674  jz      short loc_14003A68C
0x14003a676  call    cs:__imp__errno
0x14003a67c  movzx   edi, word ptr [rax]
0x14003a67f  or      edi, 80070000h
0x14003a685  cmp     [rax], esi
0x14003a687  cmovle  edi, [rax]
0x14003a68a  jmp     short loc_14003A68E
0x14003a68c  mov     edi, esi
0x14003a68e  mov     rdx, [rsp+170h+FileName]
0x14003a693  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14003a697  mov     ecx, r14d
0x14003a69a  lock xadd [rdx+10h], ecx
0x14003a69f  add     ecx, r14d
0x14003a6a2  test    ecx, ecx
0x14003a6a4  jg      short loc_14003A6B3
0x14003a6a6  lfence
0x14003a6a9  mov     rcx, [rdx]
0x14003a6ac  mov     r8, [rcx]
0x14003a6af  call    qword ptr [r8+8]
0x14003a6b3  mov     eax, edi
0x14003a6b5  mov     rcx, [rbp+70h+var_18]
0x14003a6b9  xor     rcx, rsp; StackCookie
0x14003a6bc  call    __security_check_cookie
0x14003a6c1  lea     r11, [rsp+170h+var_10]
0x14003a6c9  mov     rbx, [r11+30h]
0x14003a6cd  mov     rsi, [r11+38h]
0x14003a6d1  mov     rsp, r11
0x14003a6d4  pop     r14
0x14003a6d6  pop     rdi
0x14003a6d7  pop     rbp
0x14003a6d8  retn
0x14003a6d9  mov     ecx, 80004005h; int
0x14003a6de  call    ?AtlThrowImpl@ATL@@YAXJ@Z
```
