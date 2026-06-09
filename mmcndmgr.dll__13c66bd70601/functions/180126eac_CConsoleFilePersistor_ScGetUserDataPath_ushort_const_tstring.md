# CConsoleFilePersistor::ScGetUserDataPath(ushort const *,tstring &)

- ea: `0x180126eac`
- end: `0x1801270e6`
- name: `?ScGetUserDataPath@CConsoleFilePersistor@@CA?AVSC@mmcerror@@PEBGAEAVtstring@@@Z`
- size: `570`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180127778`

## callees

- `0x1800130e0`
- `0x18002fca0`
- `0x1800304c0`
- `0x180040d94`
- `0x18006fa60`
- `0x180071370`
- `0x180126eac`

## import_xrefs

- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x180126ff8`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x180126ff8`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180126ed0`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180126ed0`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1801270da`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1801270da`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1801270ae`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1801270ae`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180126f02`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180126f98`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180126f02`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180126f98`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180126ee2`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180126ee2`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180126f17`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180126fad`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180126f17`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180126fad`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180126f0d`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180126fa3`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1801270b9`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180126f0d`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180126fa3`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1801270b9`
- `msvcrt!wcsrchr` at `0x180126f3e`
- `msvcrt!wcsrchr` at `0x180126f3e`
- `msvcrt!iswspace` at `0x180126f64`
- `msvcrt!iswspace` at `0x180126f64`
- `msvcrt!_wcsicmp` at `0x180127028`
- `msvcrt!_wcsicmp` at `0x180127028`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180126fca`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180126fca`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180126fea`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180126fea`

## string_xrefs

- `0x180126ed7`: `CConsoleFilePersistor::ScGetUserDataPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
mmcerror::SC *__fastcall CConsoleFilePersistor::ScGetUserDataPath(mmcerror::SC *a1, const wchar_t *a2, const WCHAR *a3)
{
  __int64 v6; // rax
  __int64 v7; // r14
  wchar_t *v8; // rax
  wint_t *v9; // rdi
  wint_t v10; // ax
  __int64 UserDataFolder; // rax
  const WCHAR *v12; // rcx
  DWORD FileAttributesW; // eax
  const WCHAR *v14; // rcx
  struct mmcerror::SC *Error; // rax
  const struct mmcerror::SC *v16; // rdx
  __int64 v17; // r15
  const WCHAR *v18; // rax
  const WCHAR *v19; // rcx
  _BYTE v21[24]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v22[32]; // [rsp+40h] [rbp-20h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v21, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v21, L"CConsoleFilePersistor::ScGetUserDataPath");
  v6 = ScCheckPointers(v22, a2, 2147942487LL);
  mmcerror::SC::operator=(v21, v6);
  mmcerror::SC::~SC((mmcerror::SC *)v22);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v21) )
    goto LABEL_36;
  v7 = -1;
  std::wstring::erase(a3, 0, -1);
  v8 = wcsrchr(a2, 0x5Cu);
  if ( v8 )
    v9 = v8 + 1;
  else
    v9 = (wint_t *)a2;
  v10 = *v9;
  if ( !*v9 )
    goto LABEL_38;
  do
  {
    if ( !iswspace(v10) )
      break;
    v10 = *++v9;
  }
  while ( *v9 );
  if ( !*v9 )
  {
LABEL_38:
    Error = (struct mmcerror::SC *)mmcerror::SC::operator=(v21, 2147942487LL);
    goto LABEL_20;
  }
  UserDataFolder = CConsoleFilePersistor::ScGetUserDataFolder(v22, a3);
  mmcerror::SC::operator=(v21, UserDataFolder);
  mmcerror::SC::~SC((mmcerror::SC *)v22);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v21) )
  {
LABEL_36:
    v16 = (const struct mmcerror::SC *)v21;
    goto LABEL_37;
  }
  if ( *((_QWORD *)a3 + 3) < 8u )
    v12 = a3;
  else
    v12 = *(const WCHAR **)a3;
  FileAttributesW = GetFileAttributesW(v12);
  if ( (FileAttributesW & 0x10) != 0 && FileAttributesW != -1
    || (*((_QWORD *)a3 + 3) < 8u ? (v14 = a3) : (v14 = *(const WCHAR **)a3), CreateDirectoryW(v14, 0)) )
  {
    do
      ++v7;
    while ( v9[v7] );
    if ( (int)v7 > 4 && !_wcsicmp(L".msc", &v9[(int)v7 - 4]) )
      LODWORD(v7) = v7 - 3;
    if ( *((_QWORD *)a3 + 2) == -1 || ~*((_QWORD *)a3 + 2) == 1 )
      std::_Xlength_error("string too long");
    v17 = *((_QWORD *)a3 + 2) + 1LL;
    if ( (unsigned __int8)std::wstring::_Grow(a3, v17, 0) )
    {
      if ( *((_QWORD *)a3 + 3) < 8u )
        v18 = a3;
      else
        v18 = *(const WCHAR **)a3;
      v18[*((_QWORD *)a3 + 2)] = 92;
      if ( *((_QWORD *)a3 + 3) < 8u )
        v19 = a3;
      else
        v19 = *(const WCHAR **)a3;
      *((_QWORD *)a3 + 2) = v17;
      v19[v17] = 0;
    }
    std::wstring::append(a3, v9, (int)v7);
    goto LABEL_36;
  }
  Error = mmcerror::SC::FromLastError((mmcerror::SC *)v21);
LABEL_20:
  v16 = Error;
LABEL_37:
  mmcerror::SC::SC(a1, v16);
  mmcerror::SC::~SC((mmcerror::SC *)v21);
  return a1;
}

```

## disassembly

```asm
0x180126eac  push    rbp
0x180126eae  push    rbx
0x180126eaf  push    rsi
0x180126eb0  push    rdi
0x180126eb1  push    r12
0x180126eb3  push    r14
0x180126eb5  push    r15
0x180126eb7  mov     rbp, rsp
0x180126eba  sub     rsp, 60h
0x180126ebe  mov     rbx, r8
0x180126ec1  mov     r15, rdx
0x180126ec4  mov     rsi, rcx
0x180126ec7  xor     r12d, r12d
0x180126eca  xor     edx, edx
0x180126ecc  lea     rcx, [rbp+var_38]
0x180126ed0  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x180126ed6  nop
0x180126ed7  lea     rdx, aCconsolefilepe; "CConsoleFilePersistor::ScGetUserDataPat"...
0x180126ede  lea     rcx, [rbp+var_38]
0x180126ee2  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x180126ee8  mov     r8d, 80070057h
0x180126eee  mov     rdx, r15
0x180126ef1  lea     rcx, [rbp+var_20]
0x180126ef5  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x180126efa  nop
0x180126efb  mov     rdx, rax
0x180126efe  lea     rcx, [rbp+var_38]
0x180126f02  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180126f08  nop
0x180126f09  lea     rcx, [rbp+var_20]
0x180126f0d  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180126f13  lea     rcx, [rbp+var_38]
0x180126f17  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180126f1d  test    al, al
0x180126f1f  jnz     loc_1801270A7
0x180126f25  or      r14, 0FFFFFFFFFFFFFFFFh
0x180126f29  mov     r8, r14
0x180126f2c  xor     edx, edx
0x180126f2e  mov     rcx, rbx
0x180126f31  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x180126f36  lea     edx, [r12+5Ch]; Ch
0x180126f3b  mov     rcx, r15; Str
0x180126f3e  call    cs:__imp_wcsrchr
0x180126f44  mov     rdi, rax
0x180126f47  test    rax, rax
0x180126f4a  jnz     short loc_180126F51
0x180126f4c  mov     rdi, r15
0x180126f4f  jmp     short loc_180126F55
0x180126f51  add     rdi, 2
0x180126f55  movzx   eax, word ptr [rdi]
0x180126f58  test    ax, ax
0x180126f5b  jz      loc_1801270D1
0x180126f61  movzx   ecx, ax; C
0x180126f64  call    cs:__imp_iswspace
0x180126f6a  test    eax, eax
0x180126f6c  jz      short loc_180126F7A
0x180126f6e  add     rdi, 2
0x180126f72  movzx   eax, word ptr [rdi]
0x180126f75  test    ax, ax
0x180126f78  jnz     short loc_180126F61
0x180126f7a  cmp     [rdi], r12w
0x180126f7e  jz      loc_1801270D1
0x180126f84  mov     rdx, rbx
0x180126f87  lea     rcx, [rbp+var_20]
0x180126f8b  call    ?ScGetUserDataFolder@CConsoleFilePersistor@@SA?AVSC@mmcerror@@AEAVtstring@@@Z; CConsoleFilePersistor::ScGetUserDataFolder(tstring &)
0x180126f90  nop
0x180126f91  mov     rdx, rax
0x180126f94  lea     rcx, [rbp+var_38]
0x180126f98  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180126f9e  nop
0x180126f9f  lea     rcx, [rbp+var_20]
0x180126fa3  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180126fa9  lea     rcx, [rbp+var_38]
0x180126fad  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180126fb3  test    al, al
0x180126fb5  jnz     loc_1801270A7
0x180126fbb  cmp     qword ptr [rbx+18h], 8
0x180126fc0  jb      short loc_180126FC7
0x180126fc2  mov     rcx, [rbx]
0x180126fc5  jmp     short loc_180126FCA
0x180126fc7  mov     rcx, rbx; lpFileName
0x180126fca  call    cs:__imp_GetFileAttributesW
0x180126fd0  test    al, 10h
0x180126fd2  jz      short loc_180126FD9
0x180126fd4  cmp     eax, 0FFFFFFFFh
0x180126fd7  jnz     short loc_180127006
0x180126fd9  cmp     qword ptr [rbx+18h], 8
0x180126fde  jb      short loc_180126FE5
0x180126fe0  mov     rcx, [rbx]
0x180126fe3  jmp     short loc_180126FE8
0x180126fe5  mov     rcx, rbx; lpPathName
0x180126fe8  xor     edx, edx; lpSecurityAttributes
0x180126fea  call    cs:__imp_CreateDirectoryW
0x180126ff0  test    eax, eax
0x180126ff2  jnz     short loc_180127006
0x180126ff4  lea     rcx, [rbp+var_38]
0x180126ff8  call    cs:__imp_?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ; mmcerror::SC::FromLastError(void)
0x180126ffe  mov     rdx, rax
0x180127001  jmp     loc_1801270AB
0x180127006  inc     r14
0x180127009  cmp     [rdi+r14*2], r12w
0x18012700e  jnz     short loc_180127006
0x180127010  cmp     r14d, 4
0x180127014  jle     short loc_180127036
0x180127016  movsxd  rax, r14d
0x180127019  add     rax, 0FFFFFFFFFFFFFFFCh
0x18012701d  lea     rdx, [rdi+rax*2]; String2
0x180127021  lea     rcx, aMsc; ".msc"
0x180127028  call    cs:__imp__wcsicmp
0x18012702e  test    eax, eax
0x180127030  jnz     short loc_180127036
0x180127032  sub     r14d, 3
0x180127036  mov     r15, [rbx+10h]
0x18012703a  mov     rax, r15
0x18012703d  not     rax
0x180127040  cmp     rax, 1
0x180127044  ja      short loc_180127053
0x180127046  lea     rcx, aStringTooLong; "string too long"
0x18012704d  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180127053  inc     r15
0x180127056  xor     r8d, r8d
0x180127059  mov     rdx, r15
0x18012705c  mov     rcx, rbx
0x18012705f  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x180127064  test    al, al
0x180127066  jz      short loc_180127099
0x180127068  mov     rcx, [rbx+10h]
0x18012706c  cmp     qword ptr [rbx+18h], 8
0x180127071  jb      short loc_180127078
0x180127073  mov     rax, [rbx]
0x180127076  jmp     short loc_18012707B
0x180127078  mov     rax, rbx
0x18012707b  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x180127081  cmp     qword ptr [rbx+18h], 8
0x180127086  jb      short loc_18012708D
0x180127088  mov     rcx, [rbx]
0x18012708b  jmp     short loc_180127090
0x18012708d  mov     rcx, rbx
0x180127090  mov     [rbx+10h], r15
0x180127094  mov     [rcx+r15*2], r12w
0x180127099  movsxd  r8, r14d
0x18012709c  mov     rdx, rdi
0x18012709f  mov     rcx, rbx
0x1801270a2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1801270a7  lea     rdx, [rbp+var_38]
0x1801270ab  mov     rcx, rsi
0x1801270ae  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x1801270b4  nop
0x1801270b5  lea     rcx, [rbp+var_38]
0x1801270b9  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1801270bf  mov     rax, rsi
0x1801270c2  add     rsp, 60h
0x1801270c6  pop     r15
0x1801270c8  pop     r14
0x1801270ca  pop     r12
0x1801270cc  pop     rdi
0x1801270cd  pop     rsi
0x1801270ce  pop     rbx
0x1801270cf  pop     rbp
0x1801270d0  retn
0x1801270d1  mov     edx, 80070057h
0x1801270d6  lea     rcx, [rbp+var_38]
0x1801270da  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1801270e0  jmp     loc_180126FFE
```
