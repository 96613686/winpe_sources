# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::_Inside(char const *)

- ea: `0x18000403c`
- end: `0x18000406f`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAA_NPEBD@Z`
- size: `51`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000431c`
- `0x18001bf04`

## callees

- `0x18000403c`

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
0x18000403c  cmp     qword ptr [rcx+20h], 10h
0x180004041  lea     r8, [rcx+8]
0x180004045  jb      short loc_18000404C
0x180004047  mov     rax, [r8]
0x18000404a  jmp     short loc_18000404F
0x18000404c  mov     rax, r8
0x18000404f  cmp     rdx, rax
0x180004052  jb      short loc_18000406C
0x180004054  cmp     qword ptr [rcx+20h], 10h
0x180004059  jb      short loc_18000405E
0x18000405b  mov     r8, [r8]
0x18000405e  mov     rcx, [rcx+18h]
0x180004062  add     rcx, r8
0x180004065  cmp     rcx, rdx
0x180004068  setnbe  al
0x18000406b  retn
0x18000406c  xor     al, al
0x18000406e  retn
```
