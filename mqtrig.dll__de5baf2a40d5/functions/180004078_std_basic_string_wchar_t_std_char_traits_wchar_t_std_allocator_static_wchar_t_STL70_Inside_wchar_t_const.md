# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Inside(wchar_t const *)

- ea: `0x180004078`
- end: `0x1800040ac`
- name: `?_Inside@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAA_NPEB_W@Z`
- size: `52`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180004478`
- `0x180015c74`

## callees

- `0x180004078`

## pseudocode

```c
bool __fastcall std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Inside(
        _QWORD *a1,
        unsigned __int64 a2)
{
  _QWORD *v2; // r8
  _QWORD *v3; // rax

  v2 = a1 + 1;
  if ( a1[4] < 8u )
    v3 = a1 + 1;
  else
    v3 = (_QWORD *)*v2;
  if ( a2 < (unsigned __int64)v3 )
    return 0;
  if ( a1[4] >= 8u )
    v2 = (_QWORD *)*v2;
  return (unsigned __int64)v2 + 2 * a1[3] > a2;
}

```

## disassembly

```asm
0x180004078  cmp     qword ptr [rcx+20h], 8
0x18000407d  lea     r8, [rcx+8]
0x180004081  jb      short loc_180004088
0x180004083  mov     rax, [r8]
0x180004086  jmp     short loc_18000408B
0x180004088  mov     rax, r8
0x18000408b  cmp     rdx, rax
0x18000408e  jb      short loc_1800040A9
0x180004090  cmp     qword ptr [rcx+20h], 8
0x180004095  jb      short loc_18000409A
0x180004097  mov     r8, [r8]
0x18000409a  mov     rax, [rcx+18h]
0x18000409e  lea     rcx, [r8+rax*2]
0x1800040a2  cmp     rcx, rdx
0x1800040a5  setnbe  al
0x1800040a8  retn
0x1800040a9  xor     al, al
0x1800040ab  retn
```
