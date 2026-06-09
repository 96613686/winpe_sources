# std::basic_fstream<ushort,std::char_traits<ushort>>::open(ushort const *,int,int)

- ea: `0x18007ea68`
- end: `0x18007eb11`
- name: `?open@?$basic_fstream@GU?$char_traits@G@std@@@std@@QEAAXPEBGHH@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18004a180`

## callees

- `0x1800338ac`
- `0x18007ac0c`
- `0x18007e7b4`
- `0x18007e84c`
- `0x18007ea68`

## import_xrefs

- `msvcp_win!?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18007eaf3`
- `msvcp_win!?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18007eaf3`
- `msvcp_win!?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ` at `0x18007eaba`
- `msvcp_win!?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ` at `0x18007eaba`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x18007ea96`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x18007ea96`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18007eb00`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18007eb00`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::basic_fstream<unsigned short>::open(_QWORD *a1, const unsigned __int16 *a2)
{
  _QWORD *v3; // rbx
  struct _iobuf *v4; // rax
  std::locale *v5; // rax
  __int64 v6; // rax
  char *v7; // rcx
  _BYTE v9[24]; // [rsp+20h] [rbp-18h] BYREF

  v3 = a1 + 3;
  if ( a1[19] || (v4 = std::_Fiopen(a2, 2, 64)) == 0 )
  {
    v3 = 0;
  }
  else
  {
    std::basic_filebuf<unsigned short>::_Init(v3, v4, 1);
    v5 = (std::locale *)std::basic_streambuf<unsigned short>::getloc(v3, v9);
    v6 = std::use_facet<std::codecvt<unsigned short,char,_Mbstatet>>(v5);
    std::basic_filebuf<unsigned short>::_Initcvt(v3, v6);
    std::locale::~locale((std::locale *)v9);
  }
  v7 = (char *)a1 + *(int *)(*a1 + 4LL);
  if ( v3 )
    return std::basic_ios<unsigned short>::clear(v7, 0, 0);
  else
    return std::basic_ios<unsigned short>::setstate(v7, 2, 0);
}

```

## disassembly

```asm
0x18007ea68  mov     [rsp+arg_0], rbx
0x18007ea6d  push    rdi
0x18007ea6e  sub     rsp, 30h
0x18007ea72  mov     rax, rdx
0x18007ea75  mov     rdi, rcx
0x18007ea78  lea     rbx, [rcx+18h]
0x18007ea7c  cmp     qword ptr [rbx+80h], 0
0x18007ea84  jz      short loc_18007EA8A
0x18007ea86  xor     ebx, ebx
0x18007ea88  jmp     short loc_18007EADF
0x18007ea8a  mov     edx, 2
0x18007ea8f  lea     r8d, [rdx+3Eh]
0x18007ea93  mov     rcx, rax
0x18007ea96  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z; std::_Fiopen(ushort const *,int,int)
0x18007ea9c  test    rax, rax
0x18007ea9f  jz      short loc_18007EA86
0x18007eaa1  mov     r8d, 1
0x18007eaa7  mov     rdx, rax
0x18007eaaa  mov     rcx, rbx
0x18007eaad  call    ?_Init@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::basic_filebuf<ushort>::_Init(_iobuf *,std::basic_filebuf<ushort>::_Initfl)
0x18007eab2  lea     rdx, [rsp+38h+var_18]
0x18007eab7  mov     rcx, rbx
0x18007eaba  call    cs:__imp_?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ; std::basic_streambuf<ushort>::getloc(void)
0x18007eac0  nop
0x18007eac1  mov     rcx, rax; this
0x18007eac4  call    ??$use_facet@V?$codecvt@GDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@GDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<ushort,char,_Mbstatet>>(std::locale const &)
0x18007eac9  mov     rdx, rax
0x18007eacc  mov     rcx, rbx
0x18007eacf  call    ?_Initcvt@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAAXAEBV?$codecvt@GDU_Mbstatet@@@2@@Z; std::basic_filebuf<ushort>::_Initcvt(std::codecvt<ushort,char,_Mbstatet> const &)
0x18007ead4  nop
0x18007ead5  lea     rcx, [rsp+38h+var_18]; this
0x18007eada  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x18007eadf  mov     rax, [rdi]
0x18007eae2  movsxd  rcx, dword ptr [rax+4]
0x18007eae6  add     rcx, rdi
0x18007eae9  xor     r8d, r8d
0x18007eaec  test    rbx, rbx
0x18007eaef  jz      short loc_18007EAFB
0x18007eaf1  xor     edx, edx
0x18007eaf3  call    cs:__imp_?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::clear(int,bool)
0x18007eaf9  jmp     short loc_18007EB06
0x18007eafb  mov     edx, 2
0x18007eb00  call    cs:__imp_?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x18007eb06  mov     rbx, [rsp+38h+arg_0]
0x18007eb0b  add     rsp, 30h
0x18007eb0f  pop     rdi
0x18007eb10  retn
```
