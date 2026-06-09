# std::basic_ifstream<char,std::char_traits<char>>::basic_ifstream<char,std::char_traits<char>>(ushort const *,int,int)

- ea: `0x1800e6530`
- end: `0x1800e6663`
- name: `??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEBGHH@Z`
- size: `307`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800f5b18`
- `0x1800f8214`

## callees

- `0x1800e62fc`
- `0x1800e64f4`
- `0x1800e6530`
- `0x1800e852c`
- `0x1800ef684`
- `0x1800ef748`

## import_xrefs

- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x1800e65da`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x1800e65da`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x1800e6604`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x1800e6604`
- `msvcp_win!??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x1800e658b`
- `msvcp_win!??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x1800e658b`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x1800e6566`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x1800e6566`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x1800e6642`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x1800e6642`

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
0x1800e6530  mov     rax, rsp
0x1800e6533  mov     [rax+10h], rbx
0x1800e6537  mov     [rax+18h], rsi
0x1800e653b  mov     [rax+20h], r9d
0x1800e653f  mov     [rax+8], rcx
0x1800e6543  push    rdi
0x1800e6544  sub     rsp, 30h
0x1800e6548  mov     rsi, rdx
0x1800e654b  mov     rbx, rcx
0x1800e654e  mov     dword ptr [rax+20h], 0
0x1800e6555  lea     rax, ??_8?$basic_ifstream@DU?$char_traits@D@std@@@std@@7B@; const std::ifstream::`vbtable'
0x1800e655c  mov     [rcx], rax
0x1800e655f  add     rcx, 0B0h
0x1800e6566  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x1800e656d  nop     dword ptr [rax+rax+00h]
0x1800e6572  nop
0x1800e6573  mov     [rsp+38h+arg_18], 1
0x1800e657b  lea     rdi, [rbx+10h]
0x1800e657f  xor     r9d, r9d
0x1800e6582  xor     r8d, r8d
0x1800e6585  mov     rdx, rdi
0x1800e6588  mov     rcx, rbx
0x1800e658b  call    cs:__imp_??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z; std::istream::istream(std::streambuf *,bool)
0x1800e6592  nop     dword ptr [rax+rax+00h]
0x1800e6597  nop
0x1800e6598  mov     rax, [rbx]
0x1800e659b  movsxd  rcx, dword ptr [rax+4]
0x1800e659f  lea     rax, ??_7?$basic_ifstream@DU?$char_traits@D@std@@@std@@6B@; const std::ifstream::`vftable'
0x1800e65a6  mov     [rcx+rbx], rax
0x1800e65aa  mov     rax, [rbx]
0x1800e65ad  movsxd  rcx, dword ptr [rax+4]
0x1800e65b1  lea     edx, [rcx-0B0h]
0x1800e65b7  mov     [rcx+rbx-4], edx
0x1800e65bb  mov     rcx, rdi
0x1800e65be  call    ??0?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAA@XZ; std::filebuf::filebuf(void)
0x1800e65c3  nop
0x1800e65c4  cmp     qword ptr [rdi+80h], 0
0x1800e65cc  jnz     short loc_1800E6631
0x1800e65ce  mov     edx, 21h ; '!'
0x1800e65d3  lea     r8d, [rdx+1Fh]
0x1800e65d7  mov     rcx, rsi
0x1800e65da  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z; std::_Fiopen(ushort const *,int,int)
0x1800e65e1  nop     dword ptr [rax+rax+00h]
0x1800e65e6  test    rax, rax
0x1800e65e9  jz      short loc_1800E6631
0x1800e65eb  mov     r8d, 1
0x1800e65f1  mov     rdx, rax
0x1800e65f4  mov     rcx, rdi
0x1800e65f7  call    ?_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)
0x1800e65fc  lea     rdx, [rsp+38h+var_18]
0x1800e6601  mov     rcx, rdi
0x1800e6604  call    cs:__imp_?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ; std::streambuf::getloc(void)
0x1800e660b  nop     dword ptr [rax+rax+00h]
0x1800e6610  nop
0x1800e6611  mov     rcx, rax; this
0x1800e6614  call    ??$use_facet@V?$codecvt@DDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@DDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<char,char,_Mbstatet>>(std::locale const &)
0x1800e6619  mov     rdx, rax
0x1800e661c  mov     rcx, rdi
0x1800e661f  call    ?_Initcvt@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXAEBV?$codecvt@DDU_Mbstatet@@@2@@Z; std::filebuf::_Initcvt(std::codecvt<char,char,_Mbstatet> const &)
0x1800e6624  nop
0x1800e6625  lea     rcx, [rsp+38h+var_18]; this
0x1800e662a  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x1800e662f  jmp     short loc_1800E664F
0x1800e6631  mov     rax, [rbx]
0x1800e6634  movsxd  rcx, dword ptr [rax+4]
0x1800e6638  add     rcx, rbx
0x1800e663b  xor     r8d, r8d
0x1800e663e  lea     edx, [r8+2]
0x1800e6642  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x1800e6649  nop     dword ptr [rax+rax+00h]
0x1800e664e  nop
0x1800e664f  mov     rax, rbx
0x1800e6652  mov     rbx, [rsp+38h+arg_8]
0x1800e6657  mov     rsi, [rsp+38h+arg_10]
0x1800e665c  add     rsp, 30h
0x1800e6660  pop     rdi
0x1800e6661  retn
```
