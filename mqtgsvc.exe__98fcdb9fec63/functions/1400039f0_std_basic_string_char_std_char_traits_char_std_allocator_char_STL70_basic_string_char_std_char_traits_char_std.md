# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>(char const *)

- ea: `0x1400039f0`
- end: `0x140003a25`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z`
- size: `53`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x1400014d4`
- `0x140001530`
- `0x140004c24`
- `0x1400053dc`
- `0x140006b54`
- `0x140006d34`
- `0x140007034`
- `0x14000cac4`
- `0x140013200`
- `0x140013bf8`
- `0x140013d20`
- `0x1400149f4`
- `0x14001b928`

## callees

- `0x1400039f0`
- `0x1400050cc`

## pseudocode

```c
__int64 __fastcall std::string::string(__int64 a1, __int64 a2)
{
  __int64 v3; // r8

  *(_QWORD *)(a1 + 32) = 15;
  *(_QWORD *)(a1 + 24) = 0;
  *(_BYTE *)(a1 + 8) = 0;
  v3 = -1;
  do
    ++v3;
  while ( *(_BYTE *)(a2 + v3) );
  std::string::assign();
  return a1;
}

```

## disassembly

```asm
0x1400039f0  push    rbx
0x1400039f2  sub     rsp, 20h
0x1400039f6  xor     eax, eax
0x1400039f8  mov     qword ptr [rcx+20h], 0Fh
0x140003a00  mov     [rcx+18h], rax
0x140003a04  mov     rbx, rcx
0x140003a07  mov     [rcx+8], al
0x140003a0a  or      r8, 0FFFFFFFFFFFFFFFFh
0x140003a0e  inc     r8
0x140003a11  cmp     [rdx+r8], al
0x140003a15  jnz     short loc_140003A0E
0x140003a17  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x140003a1c  mov     rax, rbx
0x140003a1f  add     rsp, 20h
0x140003a23  pop     rbx
0x140003a24  retn
```
