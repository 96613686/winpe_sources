# std::basic_filebuf<char,std::char_traits<char>>::open(ushort const *,int,int)

- ea: `0x18000c748`
- end: `0x18000c7c2`
- name: `?open@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@PEBGHH@Z`
- size: `122`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180007214`

## callees

- `0x180007088`
- `0x180007cb8`
- `0x18000c368`
- `0x18000c418`
- `0x18000c748`

## import_xrefs

- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x18000c76c`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x18000c76c`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x18000c790`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x18000c790`

## pseudocode

```c
__int64 __fastcall std::filebuf::open(__int64 a1, const unsigned __int16 *a2, int a3)
{
  struct _iobuf *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  _BYTE v8[24]; // [rsp+20h] [rbp-18h] BYREF

  if ( *(_QWORD *)(a1 + 128) )
    return 0;
  v4 = std::_Fiopen(a2, a3, 64);
  if ( !v4 )
    return 0;
  std::filebuf::_Init(a1, (__int64)v4, 1);
  v5 = std::streambuf::getloc(a1, v8);
  v6 = std::use_facet<std::codecvt<char,char,_Mbstatet>>(v5);
  std::filebuf::_Initcvt(a1, v6);
  std::locale::~locale((std::locale *)v8);
  return a1;
}

```

## disassembly

```asm
0x18000c748  push    rbx
0x18000c74a  sub     rsp, 30h
0x18000c74e  mov     eax, r8d
0x18000c751  mov     r9, rdx
0x18000c754  mov     rbx, rcx
0x18000c757  cmp     qword ptr [rcx+80h], 0
0x18000c75f  jnz     short loc_18000C7BA
0x18000c761  mov     r8d, 40h ; '@'
0x18000c767  mov     edx, eax
0x18000c769  mov     rcx, r9
0x18000c76c  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z; std::_Fiopen(ushort const *,int,int)
0x18000c772  test    rax, rax
0x18000c775  jz      short loc_18000C7BA
0x18000c777  mov     r8d, 1
0x18000c77d  mov     rdx, rax
0x18000c780  mov     rcx, rbx
0x18000c783  call    ?_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)
0x18000c788  lea     rdx, [rsp+38h+var_18]
0x18000c78d  mov     rcx, rbx
0x18000c790  call    cs:__imp_?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ; std::streambuf::getloc(void)
0x18000c796  nop
0x18000c797  mov     rcx, rax
0x18000c79a  call    ??$use_facet@V?$codecvt@DDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@DDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<char,char,_Mbstatet>>(std::locale const &)
0x18000c79f  mov     rdx, rax
0x18000c7a2  mov     rcx, rbx
0x18000c7a5  call    ?_Initcvt@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXAEBV?$codecvt@DDU_Mbstatet@@@2@@Z; std::filebuf::_Initcvt(std::codecvt<char,char,_Mbstatet> const &)
0x18000c7aa  nop
0x18000c7ab  lea     rcx, [rsp+38h+var_18]; this
0x18000c7b0  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x18000c7b5  mov     rax, rbx
0x18000c7b8  jmp     short loc_18000C7BC
0x18000c7ba  xor     eax, eax
0x18000c7bc  add     rsp, 30h
0x18000c7c0  pop     rbx
0x18000c7c1  retn
```
