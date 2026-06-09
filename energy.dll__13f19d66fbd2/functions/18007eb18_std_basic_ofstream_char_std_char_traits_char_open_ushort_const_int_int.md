# std::basic_ofstream<char,std::char_traits<char>>::open(ushort const *,int,int)

- ea: `0x18007eb18`
- end: `0x18007ebc1`
- name: `?open@?$basic_ofstream@DU?$char_traits@D@std@@@std@@QEAAXPEBGHH@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18007b860`

## callees

- `0x1800338ac`
- `0x18007ab40`
- `0x18007e704`
- `0x18007e804`
- `0x18007eb18`

## import_xrefs

- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x18007ebb0`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x18007ebb0`
- `msvcp_win!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x18007eba3`
- `msvcp_win!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x18007eba3`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x18007eb6a`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x18007eb6a`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x18007eb46`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x18007eb46`

## pseudocode

```c
__int64 __fastcall std::ofstream::open(_QWORD *a1, const unsigned __int16 *a2)
{
  _QWORD *v3; // rbx
  struct _iobuf *v4; // rax
  std::locale *v5; // rax
  __int64 v6; // rax
  char *v7; // rcx
  _BYTE v9[24]; // [rsp+20h] [rbp-18h] BYREF

  v3 = a1 + 1;
  if ( a1[17] || (v4 = std::_Fiopen(a2, 2, 64)) == 0 )
  {
    v3 = 0;
  }
  else
  {
    std::filebuf::_Init(v3, v4, 1);
    v5 = (std::locale *)std::streambuf::getloc(v3, v9);
    v6 = std::use_facet<std::codecvt<char,char,_Mbstatet>>(v5);
    std::filebuf::_Initcvt(v3, v6);
    std::locale::~locale((std::locale *)v9);
  }
  v7 = (char *)a1 + *(int *)(*a1 + 4LL);
  if ( v3 )
    return std::ios::clear(v7, 0, 0);
  else
    return std::ios::setstate(v7, 2, 0);
}

```

## disassembly

```asm
0x18007eb18  mov     [rsp+arg_0], rbx
0x18007eb1d  push    rdi
0x18007eb1e  sub     rsp, 30h
0x18007eb22  mov     rax, rdx
0x18007eb25  mov     rdi, rcx
0x18007eb28  lea     rbx, [rcx+8]
0x18007eb2c  cmp     qword ptr [rbx+80h], 0
0x18007eb34  jz      short loc_18007EB3A
0x18007eb36  xor     ebx, ebx
0x18007eb38  jmp     short loc_18007EB8F
0x18007eb3a  mov     edx, 2
0x18007eb3f  lea     r8d, [rdx+3Eh]
0x18007eb43  mov     rcx, rax
0x18007eb46  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z; std::_Fiopen(ushort const *,int,int)
0x18007eb4c  test    rax, rax
0x18007eb4f  jz      short loc_18007EB36
0x18007eb51  mov     r8d, 1
0x18007eb57  mov     rdx, rax
0x18007eb5a  mov     rcx, rbx
0x18007eb5d  call    ?_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)
0x18007eb62  lea     rdx, [rsp+38h+var_18]
0x18007eb67  mov     rcx, rbx
0x18007eb6a  call    cs:__imp_?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ; std::streambuf::getloc(void)
0x18007eb70  nop
0x18007eb71  mov     rcx, rax; this
0x18007eb74  call    ??$use_facet@V?$codecvt@DDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@DDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<char,char,_Mbstatet>>(std::locale const &)
0x18007eb79  mov     rdx, rax
0x18007eb7c  mov     rcx, rbx
0x18007eb7f  call    ?_Initcvt@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXAEBV?$codecvt@DDU_Mbstatet@@@2@@Z; std::filebuf::_Initcvt(std::codecvt<char,char,_Mbstatet> const &)
0x18007eb84  nop
0x18007eb85  lea     rcx, [rsp+38h+var_18]; this
0x18007eb8a  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x18007eb8f  mov     rax, [rdi]
0x18007eb92  movsxd  rcx, dword ptr [rax+4]
0x18007eb96  add     rcx, rdi
0x18007eb99  xor     r8d, r8d
0x18007eb9c  test    rbx, rbx
0x18007eb9f  jz      short loc_18007EBAB
0x18007eba1  xor     edx, edx
0x18007eba3  call    cs:__imp_?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::clear(int,bool)
0x18007eba9  jmp     short loc_18007EBB6
0x18007ebab  mov     edx, 2
0x18007ebb0  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x18007ebb6  mov     rbx, [rsp+38h+arg_0]
0x18007ebbb  add     rsp, 30h
0x18007ebbf  pop     rdi
0x18007ebc0  retn
```
