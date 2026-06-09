# std::basic_filebuf<char,std::char_traits<char>>::_Reset_back(void)

- ea: `0x18000c484`
- end: `0x18000c4bc`
- name: `?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ`
- size: `56`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180007774`
- `0x18000c578`
- `0x18000c7d0`
- `0x18000cd00`
- `0x18000cde0`
- `0x18000cf40`
- `0x18000d3e0`

## callees

- `0x18000c484`

## import_xrefs

- `msvcp_win!?setg@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXPEAD00@Z` at `0x18000c4b0`
- `msvcp_win!?setg@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXPEAD00@Z` at `0x18000c4b0`
- `msvcp_win!?eback@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18000c48d`
- `msvcp_win!?eback@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18000c48d`

## pseudocode

```c
__int64 __fastcall std::filebuf::_Reset_back(__int64 a1)
{
  __int64 result; // rax

  result = std::streambuf::eback();
  if ( result == a1 + 112 )
    return std::streambuf::setg(a1, *(_QWORD *)(a1 + 136), *(_QWORD *)(a1 + 136), *(_QWORD *)(a1 + 144));
  return result;
}

```

## disassembly

```asm
0x18000c484  push    rbx
0x18000c486  sub     rsp, 20h
0x18000c48a  mov     rbx, rcx
0x18000c48d  call    cs:__imp_?eback@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::eback(void)
0x18000c493  lea     rdx, [rbx+70h]
0x18000c497  cmp     rax, rdx
0x18000c49a  jnz     short loc_18000C4B6
0x18000c49c  mov     rdx, [rbx+88h]
0x18000c4a3  mov     rcx, rbx
0x18000c4a6  mov     r9, [rbx+90h]
0x18000c4ad  mov     r8, rdx
0x18000c4b0  call    cs:__imp_?setg@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXPEAD00@Z; std::streambuf::setg(char *,char *,char *)
0x18000c4b6  add     rsp, 20h
0x18000c4ba  pop     rbx
0x18000c4bb  retn
```
