# ATL::CRegParser::SkipAssignment(ushort *)

- ea: `0x1800052b4`
- end: `0x180005360`
- name: `?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `172`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800049dc`

## callees

- `0x180004060`
- `0x1800052b4`
- `0x180006030`
- `0x1800060c0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000530b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000530b`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::SkipAssignment(LPCWSTR *this, unsigned __int16 *a2)
{
  __int64 result; // rax
  int Token; // eax
  unsigned int v6; // ecx
  unsigned __int16 v7[4096]; // [rsp+20h] [rbp-2018h] BYREF

  if ( *a2 != 61 )
    return 0;
  result = ATL::CRegParser::NextToken(this, a2);
  if ( (int)result >= 0 )
  {
    while ( **this == 9 || **this == 10 || **this == 13 || **this == 32 )
      *this = CharNextW(*this);
    result = ATL::CRegParser::NextToken(this, v7);
    if ( (int)result >= 0 )
    {
      Token = ATL::CRegParser::NextToken(this, a2);
      v6 = 0;
      if ( Token < 0 )
        return (unsigned int)Token;
      return v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800052b4  mov     [rsp+arg_10], rbx
0x1800052b9  push    rdi
0x1800052ba  mov     eax, 2030h
0x1800052bf  call    _alloca_probe
0x1800052c4  sub     rsp, rax
0x1800052c7  mov     rax, cs:__security_cookie
0x1800052ce  xor     rax, rsp
0x1800052d1  mov     [rsp+2038h+var_18], rax
0x1800052d9  cmp     word ptr [rdx], 3Dh ; '='
0x1800052dd  mov     rdi, rdx
0x1800052e0  mov     rbx, rcx
0x1800052e3  jnz     short loc_18000533D
0x1800052e5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800052ea  test    eax, eax
0x1800052ec  js      short loc_18000533F
0x1800052ee  mov     rdx, [rbx]
0x1800052f1  movzx   ecx, word ptr [rdx]
0x1800052f4  sub     ecx, 9
0x1800052f7  jz      short loc_180005308
0x1800052f9  sub     ecx, 1
0x1800052fc  jz      short loc_180005308
0x1800052fe  sub     ecx, 3
0x180005301  jz      short loc_180005308
0x180005303  cmp     ecx, 13h
0x180005306  jnz     short loc_180005316
0x180005308  mov     rcx, rdx; lpsz
0x18000530b  call    cs:__imp_CharNextW
0x180005311  mov     [rbx], rax
0x180005314  jmp     short loc_1800052EE
0x180005316  lea     rdx, [rsp+2038h+var_2018]; unsigned __int16 *
0x18000531b  mov     rcx, rbx; this
0x18000531e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005323  test    eax, eax
0x180005325  js      short loc_18000533F
0x180005327  mov     rdx, rdi; unsigned __int16 *
0x18000532a  mov     rcx, rbx; this
0x18000532d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005332  xor     ecx, ecx
0x180005334  test    eax, eax
0x180005336  cmovs   ecx, eax
0x180005339  mov     eax, ecx
0x18000533b  jmp     short loc_18000533F
0x18000533d  xor     eax, eax
0x18000533f  mov     rcx, [rsp+2038h+var_18]
0x180005347  xor     rcx, rsp; StackCookie
0x18000534a  call    __security_check_cookie
0x18000534f  mov     rbx, [rsp+2038h+arg_10]
0x180005357  add     rsp, 2030h
0x18000535e  pop     rdi
0x18000535f  retn
```
