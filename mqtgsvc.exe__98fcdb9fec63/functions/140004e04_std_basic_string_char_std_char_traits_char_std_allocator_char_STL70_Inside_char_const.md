# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::_Inside(char const *)

- ea: `0x140004e04`
- end: `0x140004e37`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAA_NPEBD@Z`
- size: `51`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400050cc`
- `0x140013aac`

## callees

- `0x140004e04`

## pseudocode

```c
bool __fastcall std::string::_Inside(_QWORD *a1, unsigned __int64 a2)
{
  _QWORD *v2; // r8
  _QWORD *v3; // rax

  v2 = a1 + 1;
  if ( a1[4] < 0x10u )
    v3 = a1 + 1;
  else
    v3 = (_QWORD *)*v2;
  if ( a2 < (unsigned __int64)v3 )
    return 0;
  if ( a1[4] >= 0x10u )
    v2 = (_QWORD *)*v2;
  return (unsigned __int64)v2 + a1[3] > a2;
}

```

## disassembly

```asm
0x140004e04  cmp     qword ptr [rcx+20h], 10h
0x140004e09  lea     r8, [rcx+8]
0x140004e0d  jb      short loc_140004E14
0x140004e0f  mov     rax, [r8]
0x140004e12  jmp     short loc_140004E17
0x140004e14  mov     rax, r8
0x140004e17  cmp     rdx, rax
0x140004e1a  jb      short loc_140004E34
0x140004e1c  cmp     qword ptr [rcx+20h], 10h
0x140004e21  jb      short loc_140004E26
0x140004e23  mov     r8, [r8]
0x140004e26  mov     rcx, [rcx+18h]
0x140004e2a  add     rcx, r8
0x140004e2d  cmp     rcx, rdx
0x140004e30  setnbe  al
0x140004e33  retn
0x140004e34  xor     al, al
0x140004e36  retn
```
