# DelegationConfig::PackageInfo::IsFromSamePackage(DelegationConfig::PackageInfo const &)

- ea: `0x1800153d0`
- end: `0x180015486`
- name: `?IsFromSamePackage@PackageInfo@DelegationConfig@@QEBA_NAEBU12@@Z`
- size: `182`
- prototype: `bool __fastcall(DelegationConfig::PackageInfo *__hidden this, const struct DelegationConfig::PackageInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016c14`

## callees

- `0x180014d88`
- `0x1800153d0`

## pseudocode

```c
bool __fastcall DelegationConfig::PackageInfo::IsFromSamePackage(
        DelegationConfig::PackageInfo *this,
        const struct DelegationConfig::PackageInfo *a2)
{
  DelegationConfig::PackageInfo *v3; // rdi
  const struct DelegationConfig::PackageInfo *v4; // r8
  _QWORD *v5; // r8
  _QWORD *v6; // rcx
  _QWORD *v7; // r8
  _QWORD *v8; // rcx

  v3 = this;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v4 = a2;
  else
    v4 = *(const struct DelegationConfig::PackageInfo **)a2;
  if ( *((_QWORD *)this + 3) > 7u )
    this = *(DelegationConfig::PackageInfo **)this;
  if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                           this,
                           *((_QWORD *)v3 + 2),
                           v4,
                           *((_QWORD *)a2 + 2)) )
    return 0;
  v5 = (_QWORD *)((char *)a2 + 32);
  v6 = (_QWORD *)((char *)v3 + 32);
  if ( *((_QWORD *)a2 + 7) > 7u )
    v5 = (_QWORD *)*v5;
  if ( *((_QWORD *)v3 + 7) > 7u )
    v6 = (_QWORD *)*v6;
  if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v6, *((_QWORD *)v3 + 6), v5, *((_QWORD *)a2 + 6)) )
    return 0;
  v7 = (_QWORD *)((char *)a2 + 64);
  v8 = (_QWORD *)((char *)v3 + 64);
  if ( *((_QWORD *)a2 + 11) > 7u )
    v7 = (_QWORD *)*v7;
  if ( *((_QWORD *)v3 + 11) > 7u )
    v8 = (_QWORD *)*v8;
  return (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                            v8,
                            *((_QWORD *)v3 + 10),
                            v7,
                            *((_QWORD *)a2 + 10))
      && *((_QWORD *)v3 + 16) == *((_QWORD *)a2 + 16);
}

```

## disassembly

```asm
0x1800153d0  mov     [rsp+arg_0], rbx
0x1800153d5  push    rdi
0x1800153d6  sub     rsp, 20h
0x1800153da  cmp     qword ptr [rdx+18h], 7
0x1800153df  mov     rbx, rdx
0x1800153e2  mov     rdi, rcx
0x1800153e5  jbe     short loc_1800153EC
0x1800153e7  mov     r8, [rdx]
0x1800153ea  jmp     short loc_1800153EF
0x1800153ec  mov     r8, rbx
0x1800153ef  cmp     qword ptr [rcx+18h], 7
0x1800153f4  jbe     short loc_1800153F9
0x1800153f6  mov     rcx, [rcx]
0x1800153f9  mov     r9, [rdx+10h]
0x1800153fd  mov     rdx, [rdi+10h]
0x180015401  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180015406  test    al, al
0x180015408  jz      short loc_180015478
0x18001540a  lea     r8, [rbx+20h]
0x18001540e  cmp     qword ptr [r8+18h], 7
0x180015413  lea     rcx, [rdi+20h]
0x180015417  mov     r9, [r8+10h]
0x18001541b  jbe     short loc_180015420
0x18001541d  mov     r8, [r8]
0x180015420  cmp     qword ptr [rcx+18h], 7
0x180015425  mov     rdx, [rcx+10h]
0x180015429  jbe     short loc_18001542E
0x18001542b  mov     rcx, [rcx]
0x18001542e  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180015433  test    al, al
0x180015435  jz      short loc_180015478
0x180015437  lea     r8, [rbx+40h]
0x18001543b  cmp     qword ptr [r8+18h], 7
0x180015440  lea     rcx, [rdi+40h]
0x180015444  mov     r9, [r8+10h]
0x180015448  jbe     short loc_18001544D
0x18001544a  mov     r8, [r8]
0x18001544d  cmp     qword ptr [rcx+18h], 7
0x180015452  mov     rdx, [rcx+10h]
0x180015456  jbe     short loc_18001545B
0x180015458  mov     rcx, [rcx]
0x18001545b  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180015460  test    al, al
0x180015462  jz      short loc_180015478
0x180015464  mov     rax, [rdi+80h]
0x18001546b  cmp     rax, [rbx+80h]
0x180015472  jnz     short loc_180015478
0x180015474  mov     al, 1
0x180015476  jmp     short loc_18001547A
0x180015478  xor     al, al
0x18001547a  mov     rbx, [rsp+28h+arg_0]
0x18001547f  add     rsp, 20h
0x180015483  pop     rdi
0x180015484  retn
```
