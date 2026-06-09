# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Inside(char const *)

- ea: `0x1800077a4`
- end: `0x1800077dd`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_NPEBD@Z`
- size: `57`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800079e0`

## callees

- `0x1800077a4`

## pseudocode

```c
bool __fastcall std::string::_Inside(_QWORD *a1, unsigned __int64 a2)
{
  _QWORD *v2; // rax
  _QWORD *v3; // r8

  if ( !a2 )
    return 0;
  v2 = a1[3] < 0x10u ? a1 : (_QWORD *)*a1;
  if ( a2 < (unsigned __int64)v2 )
    return 0;
  if ( a1[3] < 0x10u )
    v3 = a1;
  else
    v3 = (_QWORD *)*a1;
  return (unsigned __int64)v3 + a1[2] > a2;
}

```

## disassembly

```asm
0x1800077a4  test    rdx, rdx
0x1800077a7  jz      short loc_1800077DA
0x1800077a9  cmp     qword ptr [rcx+18h], 10h
0x1800077ae  jb      short loc_1800077B5
0x1800077b0  mov     rax, [rcx]
0x1800077b3  jmp     short loc_1800077B8
0x1800077b5  mov     rax, rcx
0x1800077b8  cmp     rdx, rax
0x1800077bb  jb      short loc_1800077DA
0x1800077bd  cmp     qword ptr [rcx+18h], 10h
0x1800077c2  jb      short loc_1800077C9
0x1800077c4  mov     r8, [rcx]
0x1800077c7  jmp     short loc_1800077CC
0x1800077c9  mov     r8, rcx
0x1800077cc  mov     rcx, [rcx+10h]
0x1800077d0  add     rcx, r8
0x1800077d3  cmp     rcx, rdx
0x1800077d6  setnbe  al
0x1800077d9  retn
0x1800077da  xor     al, al
0x1800077dc  retn
```
