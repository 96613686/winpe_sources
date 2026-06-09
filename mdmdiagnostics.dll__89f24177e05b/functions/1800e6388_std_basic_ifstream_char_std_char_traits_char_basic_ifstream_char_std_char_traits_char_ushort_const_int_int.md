# std::basic_ifstream<char,std::char_traits<char>>::basic_ifstream<char,std::char_traits<char>>(ushort const *,int,int)

- ea: `0x1800e6388`
- end: `0x1800e649c`
- name: `??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEBGHH@Z`
- size: `276`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800f4e94`
- `0x1800f73a4`

## callees

- `0x1800e6100`
- `0x1800e6350`
- `0x1800e6388`
- `0x1800e8304`
- `0x1800eef7c`
- `0x1800ef02c`

## import_xrefs

- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x1800e6426`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x1800e6426`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x1800e644a`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x1800e644a`
- `msvcp_win!??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x1800e63dd`
- `msvcp_win!??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x1800e63dd`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x1800e63be`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x1800e63be`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x1800e6482`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x1800e6482`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall std::ifstream::ifstream(_QWORD *a1, const unsigned __int16 *a2)
{
  struct _iobuf *v4; // rax
  std::locale *v5; // rax
  __int64 v6; // rax
  _BYTE v8[24]; // [rsp+20h] [rbp-18h] BYREF

  *a1 = &std::ifstream::`vbtable';
  std::ios::ios(a1 + 22);
  std::istream::istream(a1, a1 + 2, 0, 0);
  *(_QWORD *)((char *)a1 + *(int *)(*a1 + 4LL)) = &std::ifstream::`vftable';
  *(_DWORD *)((char *)a1 + *(int *)(*a1 + 4LL) - 4) = *(_DWORD *)(*a1 + 4LL) - 176;
  std::filebuf::filebuf(a1 + 2);
  if ( a1[18] || (v4 = std::_Fiopen(a2, 33, 64)) == 0 )
  {
    std::ios::setstate((char *)a1 + *(int *)(*a1 + 4LL), 2);
  }
  else
  {
    std::filebuf::_Init(a1 + 2, v4, 1);
    v5 = (std::locale *)std::streambuf::getloc(a1 + 2, v8);
    v6 = std::use_facet<std::codecvt<char,char,_Mbstatet>>(v5);
    std::filebuf::_Initcvt(a1 + 2, v6);
    std::locale::~locale((std::locale *)v8);
  }
  return a1;
}

```

## disassembly

```asm
0x1800e6388  mov     rax, rsp
0x1800e638b  mov     [rax+10h], rbx
0x1800e638f  mov     [rax+18h], rsi
0x1800e6393  mov     [rax+20h], r9d
0x1800e6397  mov     [rax+8], rcx
0x1800e639b  push    rdi
0x1800e639c  sub     rsp, 30h
0x1800e63a0  mov     rsi, rdx
0x1800e63a3  mov     rbx, rcx
0x1800e63a6  mov     dword ptr [rax+20h], 0
0x1800e63ad  lea     rax, ??_8?$basic_ifstream@DU?$char_traits@D@std@@@std@@7B@; const std::ifstream::`vbtable'
0x1800e63b4  mov     [rcx], rax
0x1800e63b7  add     rcx, 0B0h
0x1800e63be  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x1800e63c4  nop
0x1800e63c5  mov     [rsp+38h+arg_18], 1
0x1800e63cd  lea     rdi, [rbx+10h]
0x1800e63d1  xor     r9d, r9d
0x1800e63d4  xor     r8d, r8d
0x1800e63d7  mov     rdx, rdi
0x1800e63da  mov     rcx, rbx
0x1800e63dd  call    cs:__imp_??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z; std::istream::istream(std::streambuf *,bool)
0x1800e63e3  nop
0x1800e63e4  mov     rax, [rbx]
0x1800e63e7  movsxd  rcx, dword ptr [rax+4]
0x1800e63eb  lea     rax, ??_7?$basic_ifstream@DU?$char_traits@D@std@@@std@@6B@; const std::ifstream::`vftable'
0x1800e63f2  mov     [rcx+rbx], rax
0x1800e63f6  mov     rax, [rbx]
0x1800e63f9  movsxd  rcx, dword ptr [rax+4]
0x1800e63fd  lea     edx, [rcx-0B0h]
0x1800e6403  mov     [rcx+rbx-4], edx
0x1800e6407  mov     rcx, rdi
0x1800e640a  call    ??0?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAA@XZ; std::filebuf::filebuf(void)
0x1800e640f  nop
0x1800e6410  cmp     qword ptr [rdi+80h], 0
0x1800e6418  jnz     short loc_1800E6471
0x1800e641a  mov     edx, 21h ; '!'
0x1800e641f  lea     r8d, [rdx+1Fh]
0x1800e6423  mov     rcx, rsi
0x1800e6426  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z; std::_Fiopen(ushort const *,int,int)
0x1800e642c  test    rax, rax
0x1800e642f  jz      short loc_1800E6471
0x1800e6431  mov     r8d, 1
0x1800e6437  mov     rdx, rax
0x1800e643a  mov     rcx, rdi
0x1800e643d  call    ?_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)
0x1800e6442  lea     rdx, [rsp+38h+var_18]
0x1800e6447  mov     rcx, rdi
0x1800e644a  call    cs:__imp_?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ; std::streambuf::getloc(void)
0x1800e6450  nop
0x1800e6451  mov     rcx, rax; this
0x1800e6454  call    ??$use_facet@V?$codecvt@DDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@DDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<char,char,_Mbstatet>>(std::locale const &)
0x1800e6459  mov     rdx, rax
0x1800e645c  mov     rcx, rdi
0x1800e645f  call    ?_Initcvt@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXAEBV?$codecvt@DDU_Mbstatet@@@2@@Z; std::filebuf::_Initcvt(std::codecvt<char,char,_Mbstatet> const &)
0x1800e6464  nop
0x1800e6465  lea     rcx, [rsp+38h+var_18]; this
0x1800e646a  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x1800e646f  jmp     short loc_1800E6489
0x1800e6471  mov     rax, [rbx]
0x1800e6474  movsxd  rcx, dword ptr [rax+4]
0x1800e6478  add     rcx, rbx
0x1800e647b  xor     r8d, r8d
0x1800e647e  lea     edx, [r8+2]
0x1800e6482  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x1800e6488  nop
0x1800e6489  mov     rax, rbx
0x1800e648c  mov     rbx, [rsp+38h+arg_8]
0x1800e6491  mov     rsi, [rsp+38h+arg_10]
0x1800e6496  add     rsp, 30h
0x1800e649a  pop     rdi
0x1800e649b  retn
```
