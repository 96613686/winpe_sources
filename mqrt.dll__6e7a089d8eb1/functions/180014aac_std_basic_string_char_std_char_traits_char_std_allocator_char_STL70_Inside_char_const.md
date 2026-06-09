# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::_Inside(char const *)

- ea: `0x180014aac`
- end: `0x180014adf`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAA_NPEBD@Z`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180014cac`

## callees

- `0x180014aac`

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
0x180014aac  cmp     qword ptr [rcx+20h], 10h
0x180014ab1  lea     r8, [rcx+8]
0x180014ab5  jb      short loc_180014ABC
0x180014ab7  mov     rax, [r8]
0x180014aba  jmp     short loc_180014ABF
0x180014abc  mov     rax, r8
0x180014abf  cmp     rdx, rax
0x180014ac2  jb      short loc_180014ADC
0x180014ac4  cmp     qword ptr [rcx+20h], 10h
0x180014ac9  jb      short loc_180014ACE
0x180014acb  mov     r8, [r8]
0x180014ace  mov     rcx, [rcx+18h]
0x180014ad2  add     rcx, r8
0x180014ad5  cmp     rcx, rdx
0x180014ad8  setnbe  al
0x180014adb  retn
0x180014adc  xor     al, al
0x180014ade  retn
```
