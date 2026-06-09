# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Inside(char const *)

- ea: `0x18000ad6c`
- end: `0x18000ada5`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_NPEBD@Z`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000aef8`

## callees

- `0x18000ad6c`

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
0x18000ad6c  test    rdx, rdx
0x18000ad6f  jz      short loc_18000ADA2
0x18000ad71  cmp     qword ptr [rcx+18h], 10h
0x18000ad76  jb      short loc_18000AD7D
0x18000ad78  mov     rax, [rcx]
0x18000ad7b  jmp     short loc_18000AD80
0x18000ad7d  mov     rax, rcx
0x18000ad80  cmp     rdx, rax
0x18000ad83  jb      short loc_18000ADA2
0x18000ad85  cmp     qword ptr [rcx+18h], 10h
0x18000ad8a  jb      short loc_18000AD91
0x18000ad8c  mov     r8, [rcx]
0x18000ad8f  jmp     short loc_18000AD94
0x18000ad91  mov     r8, rcx
0x18000ad94  mov     rcx, [rcx+10h]
0x18000ad98  add     rcx, r8
0x18000ad9b  cmp     rcx, rdx
0x18000ad9e  setnbe  al
0x18000ada1  retn
0x18000ada2  xor     al, al
0x18000ada4  retn
```
