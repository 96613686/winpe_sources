# std::basic_filebuf<char,std::char_traits<char>>::open(ushort const *,int,int)

- ea: `0x1800345fc`
- end: `0x1800346ca`
- name: `?open@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@PEBGHH@Z`
- size: `206`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002f2b4`

## callees

- `0x18002f198`
- `0x1800342bc`
- `0x1800345fc`
- `0x18003b010`

## import_xrefs

- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x180034628`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x180034628`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x180034650`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x180034650`
- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x180034680`
- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x180034680`
- `msvcp_win!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x180034665`
- `msvcp_win!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x180034665`

## pseudocode

```c
__int64 __fastcall std::filebuf::open(__int64 a1, const unsigned __int16 *a2, int a3)
{
  struct _iobuf *v4; // rax
  __int64 v5; // rax
  std::codecvt_base *v6; // rdi
  void (__fastcall ***v7)(_QWORD, __int64); // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v10; // [rsp+28h] [rbp-10h]

  if ( *(_QWORD *)(a1 + 128) )
    return 0;
  v4 = std::_Fiopen(a2, a3, 64);
  if ( !v4 )
    return 0;
  std::filebuf::_Init(a1, v4, 1);
  v5 = std::streambuf::getloc(a1, v9);
  v6 = (std::codecvt_base *)std::use_facet<std::codecvt<char,char,_Mbstatet>>(v5);
  if ( std::codecvt_base::always_noconv(v6) )
  {
    *(_QWORD *)(a1 + 104) = 0;
  }
  else
  {
    *(_QWORD *)(a1 + 104) = v6;
    std::streambuf::_Init(a1);
  }
  if ( v10 )
  {
    v7 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v7 )
      (**v7)(v7, 1);
  }
  return a1;
}

```

## disassembly

```asm
0x1800345fc  mov     [rsp+arg_0], rbx
0x180034601  push    rdi
0x180034602  sub     rsp, 30h
0x180034606  mov     eax, r8d
0x180034609  mov     r9, rdx
0x18003460c  mov     rbx, rcx
0x18003460f  cmp     qword ptr [rcx+80h], 0
0x180034617  jnz     loc_1800346BD
0x18003461d  mov     r8d, 40h ; '@'
0x180034623  mov     edx, eax
0x180034625  mov     rcx, r9
0x180034628  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z; std::_Fiopen(ushort const *,int,int)
0x18003462e  test    rax, rax
0x180034631  jz      loc_1800346BD
0x180034637  mov     r8d, 1
0x18003463d  mov     rdx, rax
0x180034640  mov     rcx, rbx
0x180034643  call    ?_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)
0x180034648  lea     rdx, [rsp+38h+var_18]
0x18003464d  mov     rcx, rbx
0x180034650  call    cs:__imp_?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ; std::streambuf::getloc(void)
0x180034656  nop
0x180034657  mov     rcx, rax
0x18003465a  call    ??$use_facet@V?$codecvt@DDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@DDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<char,char,_Mbstatet>>(std::locale const &)
0x18003465f  mov     rdi, rax
0x180034662  mov     rcx, rax
0x180034665  call    cs:__imp_?always_noconv@codecvt_base@std@@QEBA_NXZ; std::codecvt_base::always_noconv(void)
0x18003466b  test    al, al
0x18003466d  jz      short loc_180034679
0x18003466f  mov     qword ptr [rbx+68h], 0
0x180034677  jmp     short loc_180034687
0x180034679  mov     [rbx+68h], rdi
0x18003467d  mov     rcx, rbx
0x180034680  call    cs:__imp_?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ; std::streambuf::_Init(void)
0x180034686  nop
0x180034687  mov     rcx, [rsp+38h+var_10]
0x18003468c  test    rcx, rcx
0x18003468f  jz      short loc_1800346B8
0x180034691  mov     rax, [rcx]
0x180034694  mov     rax, [rax+10h]
0x180034698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003469d  mov     r8, rax
0x1800346a0  test    rax, rax
0x1800346a3  jz      short loc_1800346B8
0x1800346a5  mov     rcx, [rax]
0x1800346a8  mov     rax, [rcx]
0x1800346ab  mov     edx, 1
0x1800346b0  mov     rcx, r8
0x1800346b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800346b8  mov     rax, rbx
0x1800346bb  jmp     short loc_1800346BF
0x1800346bd  xor     eax, eax
0x1800346bf  mov     rbx, [rsp+38h+arg_0]
0x1800346c4  add     rsp, 30h
0x1800346c8  pop     rdi
0x1800346c9  retn
```
