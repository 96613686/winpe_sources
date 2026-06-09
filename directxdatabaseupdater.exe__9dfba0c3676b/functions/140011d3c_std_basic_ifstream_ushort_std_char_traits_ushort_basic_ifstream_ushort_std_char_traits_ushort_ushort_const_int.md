# std::basic_ifstream<ushort,std::char_traits<ushort>>::basic_ifstream<ushort,std::char_traits<ushort>>(ushort const *,int,int)

- ea: `0x140011d3c`
- end: `0x140011e68`
- name: `??0?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAA@PEBGHH@Z`
- size: `300`
- prototype: `_QWORD *__fastcall(_QWORD *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400122f8`

## callees

- `0x140006340`
- `0x140011c70`
- `0x140011d3c`
- `0x140012b94`
- `0x140012be4`

## import_xrefs

- `msvcp_win!?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ` at `0x140011e16`
- `msvcp_win!?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ` at `0x140011e16`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x140011df2`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x140011df2`
- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x140011d91`
- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x140011d91`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x140011e4e`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x140011e4e`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x140011d72`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x140011d72`
- `msvcp_win!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x140011dbe`
- `msvcp_win!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x140011dbe`

## pseudocode

```c
_QWORD *__fastcall std::basic_ifstream<unsigned short>::basic_ifstream<unsigned short>(
        _QWORD *a1,
        const unsigned __int16 *a2)
{
  struct _iobuf *v4; // rax
  std::locale *v5; // rax
  __int64 v6; // rax
  _BYTE v8[24]; // [rsp+20h] [rbp-18h] BYREF

  *a1 = &std::basic_ifstream<unsigned short>::`vbtable';
  std::basic_ios<unsigned short>::basic_ios<unsigned short>(a1 + 22);
  std::basic_istream<unsigned short>::basic_istream<unsigned short>(a1, a1 + 2, 0, 0);
  *(_QWORD *)((char *)a1 + *(int *)(*a1 + 4LL)) = &std::basic_ifstream<unsigned short>::`vftable';
  *(_DWORD *)((char *)a1 + *(int *)(*a1 + 4LL) - 4) = *(_DWORD *)(*a1 + 4LL) - 176;
  std::basic_streambuf<unsigned short>::basic_streambuf<unsigned short>(a1 + 2);
  a1[2] = &std::basic_filebuf<unsigned short>::`vftable';
  std::basic_filebuf<unsigned short>::_Init(a1 + 2, 0, 0);
  if ( a1[18] || (v4 = std::_Fiopen(a2, 33, 64)) == 0 )
  {
    std::basic_ios<unsigned short>::setstate((char *)a1 + *(int *)(*a1 + 4LL), 2, 0);
  }
  else
  {
    std::basic_filebuf<unsigned short>::_Init(a1 + 2, v4, 1);
    v5 = (std::locale *)std::basic_streambuf<unsigned short>::getloc(a1 + 2, v8);
    v6 = std::use_facet<std::codecvt<unsigned short,char,_Mbstatet>>(v5);
    std::basic_filebuf<unsigned short>::_Initcvt(a1 + 2, v6);
    std::locale::~locale((std::locale *)v8);
  }
  return a1;
}

```

## disassembly

```asm
0x140011d3c  mov     rax, rsp
0x140011d3f  mov     [rax+10h], rbx
0x140011d43  mov     [rax+18h], rsi
0x140011d47  mov     [rax+20h], r9d
0x140011d4b  mov     [rax+8], rcx
0x140011d4f  push    rdi
0x140011d50  sub     rsp, 30h
0x140011d54  mov     rsi, rdx
0x140011d57  mov     rbx, rcx
0x140011d5a  mov     dword ptr [rax+20h], 0
0x140011d61  lea     rax, ??_8?$basic_ifstream@GU?$char_traits@G@std@@@std@@7B@; const std::basic_ifstream<ushort>::`vbtable'
0x140011d68  mov     [rcx], rax
0x140011d6b  add     rcx, 0B0h
0x140011d72  call    cs:__imp_??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_ios<ushort>::basic_ios<ushort>(void)
0x140011d78  nop
0x140011d79  mov     [rsp+38h+arg_18], 1
0x140011d81  lea     rdi, [rbx+10h]
0x140011d85  xor     r9d, r9d
0x140011d88  xor     r8d, r8d
0x140011d8b  mov     rdx, rdi
0x140011d8e  mov     rcx, rbx
0x140011d91  call    cs:__imp_??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z; std::basic_istream<ushort>::basic_istream<ushort>(std::basic_streambuf<ushort> *,bool)
0x140011d97  nop
0x140011d98  mov     rax, [rbx]
0x140011d9b  movsxd  rcx, dword ptr [rax+4]
0x140011d9f  lea     rax, ??_7?$basic_ifstream@GU?$char_traits@G@std@@@std@@6B@; const std::basic_ifstream<ushort>::`vftable'
0x140011da6  mov     [rcx+rbx], rax
0x140011daa  mov     rax, [rbx]
0x140011dad  movsxd  rcx, dword ptr [rax+4]
0x140011db1  lea     edx, [rcx-0B0h]
0x140011db7  mov     [rcx+rbx-4], edx
0x140011dbb  mov     rcx, rdi
0x140011dbe  call    cs:__imp_??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_streambuf<ushort>::basic_streambuf<ushort>(void)
0x140011dc4  lea     rax, ??_7?$basic_filebuf@GU?$char_traits@G@std@@@std@@6B@; const std::basic_filebuf<ushort>::`vftable'
0x140011dcb  mov     [rdi], rax
0x140011dce  xor     r8d, r8d
0x140011dd1  xor     edx, edx
0x140011dd3  mov     rcx, rdi
0x140011dd6  call    ?_Init@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::basic_filebuf<ushort>::_Init(_iobuf *,std::basic_filebuf<ushort>::_Initfl)
0x140011ddb  nop
0x140011ddc  cmp     qword ptr [rdi+80h], 0
0x140011de4  jnz     short loc_140011E3D
0x140011de6  mov     edx, 21h ; '!'
0x140011deb  lea     r8d, [rdx+1Fh]
0x140011def  mov     rcx, rsi
0x140011df2  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z; std::_Fiopen(ushort const *,int,int)
0x140011df8  test    rax, rax
0x140011dfb  jz      short loc_140011E3D
0x140011dfd  mov     r8d, 1
0x140011e03  mov     rdx, rax
0x140011e06  mov     rcx, rdi
0x140011e09  call    ?_Init@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::basic_filebuf<ushort>::_Init(_iobuf *,std::basic_filebuf<ushort>::_Initfl)
0x140011e0e  lea     rdx, [rsp+38h+var_18]
0x140011e13  mov     rcx, rdi
0x140011e16  call    cs:__imp_?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ; std::basic_streambuf<ushort>::getloc(void)
0x140011e1c  nop
0x140011e1d  mov     rcx, rax; this
0x140011e20  call    ??$use_facet@V?$codecvt@GDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@GDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<ushort,char,_Mbstatet>>(std::locale const &)
0x140011e25  mov     rdx, rax
0x140011e28  mov     rcx, rdi
0x140011e2b  call    ?_Initcvt@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAAXAEBV?$codecvt@GDU_Mbstatet@@@2@@Z; std::basic_filebuf<ushort>::_Initcvt(std::codecvt<ushort,char,_Mbstatet> const &)
0x140011e30  nop
0x140011e31  lea     rcx, [rsp+38h+var_18]; this
0x140011e36  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x140011e3b  jmp     short loc_140011E55
0x140011e3d  mov     rax, [rbx]
0x140011e40  movsxd  rcx, dword ptr [rax+4]
0x140011e44  add     rcx, rbx
0x140011e47  xor     r8d, r8d
0x140011e4a  lea     edx, [r8+2]
0x140011e4e  call    cs:__imp_?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x140011e54  nop
0x140011e55  mov     rax, rbx
0x140011e58  mov     rbx, [rsp+38h+arg_8]
0x140011e5d  mov     rsi, [rsp+38h+arg_10]
0x140011e62  add     rsp, 30h
0x140011e66  pop     rdi
0x140011e67  retn
```
