# std::basic_filebuf<char,std::char_traits<char>>::open(ushort const *,int,int)

- ea: `0x14003be28`
- end: `0x14003bede`
- name: `?open@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@PEBGHH@Z`
- size: `182`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000972c`
- `0x14003a430`
- `0x14003ab18`
- `0x14003b7a0`

## callees

- `0x14003bd70`
- `0x14003be28`
- `0x14003d01c`

## import_xrefs

- `MSVCP140!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x14003bea1`
- `MSVCP140!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x14003bea1`
- `MSVCP140!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x14003be89`
- `MSVCP140!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x14003be89`
- `MSVCP140!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x14003be51`
- `MSVCP140!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x14003be51`
- `MSVCP140!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x14003be75`
- `MSVCP140!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x14003be75`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::filebuf::open(__int64 a1, const unsigned __int16 *a2, int a3, int a4)
{
  struct _iobuf *v5; // rax
  __int64 v6; // rax
  std::codecvt_base *v7; // rdi
  void (__fastcall ***v8)(_QWORD, __int64); // rax
  _BYTE v10[8]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v11; // [rsp+28h] [rbp-10h]

  if ( *(_QWORD *)(a1 + 128) )
    return 0;
  v5 = std::_Fiopen(a2, a3, a4);
  if ( !v5 )
    return 0;
  std::filebuf::_Init(a1, v5, 1);
  v6 = std::streambuf::getloc(a1, v10);
  v7 = (std::codecvt_base *)std::use_facet<std::codecvt<char,char,_Mbstatet>>(v6);
  if ( std::codecvt_base::always_noconv(v7) )
  {
    *(_QWORD *)(a1 + 104) = 0;
  }
  else
  {
    *(_QWORD *)(a1 + 104) = v7;
    std::streambuf::_Init(a1);
  }
  if ( v11 )
  {
    v8 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    if ( v8 )
      (**v8)(v8, 1);
  }
  return a1;
}

```

## disassembly

```asm
0x14003be28  mov     [rsp+arg_0], rbx
0x14003be2d  push    rdi
0x14003be2e  sub     rsp, 30h
0x14003be32  mov     eax, r8d
0x14003be35  mov     r10, rdx
0x14003be38  mov     rbx, rcx
0x14003be3b  cmp     qword ptr [rcx+80h], 0
0x14003be43  jnz     loc_14003BED1
0x14003be49  mov     r8d, r9d
0x14003be4c  mov     edx, eax
0x14003be4e  mov     rcx, r10
0x14003be51  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z; std::_Fiopen(ushort const *,int,int)
0x14003be57  test    rax, rax
0x14003be5a  jz      short loc_14003BED1
0x14003be5c  mov     r8d, 1
0x14003be62  mov     rdx, rax
0x14003be65  mov     rcx, rbx
0x14003be68  call    ?_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)
0x14003be6d  lea     rdx, [rsp+38h+var_18]
0x14003be72  mov     rcx, rbx
0x14003be75  call    cs:__imp_?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ; std::streambuf::getloc(void)
0x14003be7b  mov     rcx, rax
0x14003be7e  call    ??$use_facet@V?$codecvt@DDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@DDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<char,char,_Mbstatet>>(std::locale const &)
0x14003be83  mov     rdi, rax
0x14003be86  mov     rcx, rax
0x14003be89  call    cs:__imp_?always_noconv@codecvt_base@std@@QEBA_NXZ; std::codecvt_base::always_noconv(void)
0x14003be8f  test    al, al
0x14003be91  jz      short loc_14003BE9A
0x14003be93  and     qword ptr [rbx+68h], 0
0x14003be98  jmp     short loc_14003BEA8
0x14003be9a  mov     [rbx+68h], rdi
0x14003be9e  mov     rcx, rbx
0x14003bea1  call    cs:__imp_?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ; std::streambuf::_Init(void)
0x14003bea7  nop
0x14003bea8  mov     rcx, [rsp+38h+var_10]
0x14003bead  test    rcx, rcx
0x14003beb0  jz      short loc_14003BECC
0x14003beb2  mov     rax, [rcx]
0x14003beb5  call    qword ptr [rax+10h]
0x14003beb8  test    rax, rax
0x14003bebb  jz      short loc_14003BECC
0x14003bebd  mov     r8, [rax]
0x14003bec0  mov     edx, 1
0x14003bec5  mov     rcx, rax
0x14003bec8  call    qword ptr [r8]
0x14003becb  nop
0x14003becc  mov     rax, rbx
0x14003becf  jmp     short loc_14003BED3
0x14003bed1  xor     eax, eax
0x14003bed3  mov     rbx, [rsp+38h+arg_0]
0x14003bed8  add     rsp, 30h
0x14003bedc  pop     rdi
0x14003bedd  retn
```
