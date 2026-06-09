# ADsObject(CLexer *,_objectinfo *)

- ea: `0x180003fdc`
- end: `0x18000421e`
- name: `?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z`
- size: `578`
- prototype: `__int64 __fastcall(struct CLexer *this, struct _objectinfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180005a58`
- `0x18000683c`
- `0x18000745c`
- `0x18000828c`
- `0x180008fc0`
- `0x180009df0`
- `0x18000a94c`

## callees

- `0x180003fdc`
- `0x180004304`
- `0x18000449c`
- `0x180004790`
- `0x1800111e0`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsStr` at `0x180004090`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800040d4`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180004090`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800040d4`

## pseudocode

```c
__int64 __fastcall ADsObject(struct CLexer *this, struct _objectinfo *a2)
{
  int NextToken; // ecx
  bool v6; // zf
  struct _objectinfo *v7; // rdx
  struct _objectinfo *v8; // rdx
  unsigned int v9; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v10[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR pStr[264]; // [rsp+30h] [rbp-D0h] BYREF

  v9 = 0;
  v10[0] = 0;
  NextToken = CLexer::GetNextToken(this, pStr, v10);
  if ( NextToken < 0 )
    goto LABEL_18;
  if ( v10[0] != 11 )
  {
    if ( v10[0] != 1 )
      return (unsigned int)-2147463168;
    if ( pStr[0] )
      *(_QWORD *)a2 = AllocADsStr(pStr);
    NextToken = CLexer::GetNextToken(this, pStr, v10);
    if ( NextToken >= 0 )
    {
      v6 = v10[0] == 13;
      goto LABEL_11;
    }
LABEL_18:
    if ( NextToken < 0 )
      return (unsigned int)NextToken;
    goto LABEL_19;
  }
  NextToken = CLexer::GetNextToken(this, pStr, v10);
  if ( NextToken < 0 )
    goto LABEL_18;
  if ( v10[0] != 1 )
    return (unsigned int)-2147463168;
  if ( pStr[0] )
    *(_QWORD *)a2 = AllocADsStr(pStr);
  NextToken = CLexer::GetNextToken(this, pStr, v10);
  if ( NextToken < 0 )
    goto LABEL_18;
  v6 = v10[0] == 12;
LABEL_11:
  if ( !v6 )
    return (unsigned int)-2147463168;
  *((_DWORD *)this + 7) = 1;
LABEL_19:
  *((_QWORD *)a2 + 4) = 0;
  NextToken = CLexer::GetNextToken(this, pStr, &v9);
  if ( NextToken < 0 )
    return (unsigned int)NextToken;
  if ( v9 == 2 )
  {
    NextToken = Type(this, v7);
    if ( NextToken < 0 )
      return (unsigned int)NextToken;
    NextToken = CLexer::GetNextToken(this, pStr, &v9);
    if ( NextToken < 0 )
      return (unsigned int)NextToken;
    return v9 != 4 ? 0x80005000 : 0;
  }
  else
  {
    if ( v9 != 4 )
    {
      if ( *((_DWORD *)this + 5) != 4 )
        *(_QWORD *)this += -2LL * *((unsigned int *)this + 4);
      NextToken = IISObject(this, a2);
      if ( NextToken < 0 )
        return (unsigned int)NextToken;
      NextToken = CLexer::GetNextToken(this, pStr, &v9);
      if ( NextToken < 0 )
        return (unsigned int)NextToken;
      if ( v9 == 2 )
      {
        NextToken = Type(this, v8);
        if ( NextToken < 0 )
          return (unsigned int)NextToken;
        NextToken = CLexer::GetNextToken(this, pStr, &v9);
        if ( NextToken < 0 )
          return (unsigned int)NextToken;
        if ( v9 != 4 )
          return 2147504128LL;
      }
      else if ( v9 != 4 )
      {
        return 2147500037LL;
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180003fdc  mov     [rsp-8+arg_10], rbx
0x180003fe1  push    rbp
0x180003fe2  push    rsi
0x180003fe3  push    rdi
0x180003fe4  lea     rbp, [rsp-150h]
0x180003fec  sub     rsp, 250h
0x180003ff3  mov     rax, cs:__security_cookie
0x180003ffa  xor     rax, rsp
0x180003ffd  mov     [rbp+160h+var_20], rax
0x180004004  mov     rdi, rdx
0x180004007  lea     r8, [rsp+260h+var_23C]; unsigned int *
0x18000400c  xor     esi, esi
0x18000400e  lea     rdx, [rsp+260h+pStr]; unsigned __int16 *
0x180004013  mov     [rsp+260h+var_240], esi
0x180004017  mov     rbx, rcx
0x18000401a  mov     [rsp+260h+var_23C], esi
0x18000401e  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x180004023  mov     ecx, eax
0x180004025  test    eax, eax
0x180004027  js      loc_1800040FC
0x18000402d  cmp     [rsp+260h+var_23C], 0Bh
0x180004032  jnz     loc_1800040C1
0x180004038  lea     r8, [rsp+260h+var_23C]; unsigned int *
0x18000403d  mov     rcx, rbx; this
0x180004040  lea     rdx, [rsp+260h+pStr]; unsigned __int16 *
0x180004045  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x18000404a  mov     ecx, eax
0x18000404c  test    eax, eax
0x18000404e  js      loc_1800040FC
0x180004054  cmp     [rsp+260h+var_23C], 1
0x180004059  jz      short loc_180004084
0x18000405b  mov     ecx, 80005000h
0x180004060  mov     eax, ecx
0x180004062  mov     rcx, [rbp+160h+var_20]
0x180004069  xor     rcx, rsp; StackCookie
0x18000406c  call    __security_check_cookie
0x180004071  mov     rbx, [rsp+260h+arg_10]
0x180004079  add     rsp, 250h
0x180004080  pop     rdi
0x180004081  pop     rsi
0x180004082  pop     rbp
0x180004083  retn
0x180004084  cmp     [rsp+260h+pStr], si
0x180004089  jz      short loc_180004099
0x18000408b  lea     rcx, [rsp+260h+pStr]; pStr
0x180004090  call    cs:__imp_AllocADsStr
0x180004096  mov     [rdi], rax
0x180004099  lea     r8, [rsp+260h+var_23C]; unsigned int *
0x18000409e  mov     rcx, rbx; this
0x1800040a1  lea     rdx, [rsp+260h+pStr]; unsigned __int16 *
0x1800040a6  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x1800040ab  mov     ecx, eax
0x1800040ad  test    eax, eax
0x1800040af  js      short loc_1800040FC
0x1800040b1  cmp     [rsp+260h+var_23C], 0Ch
0x1800040b6  jnz     short loc_18000405B
0x1800040b8  mov     dword ptr [rbx+1Ch], 1
0x1800040bf  jmp     short loc_180004104
0x1800040c1  cmp     [rsp+260h+var_23C], 1
0x1800040c6  jnz     short loc_18000405B
0x1800040c8  cmp     [rsp+260h+pStr], si
0x1800040cd  jz      short loc_1800040DD
0x1800040cf  lea     rcx, [rsp+260h+pStr]; pStr
0x1800040d4  call    cs:__imp_AllocADsStr
0x1800040da  mov     [rdi], rax
0x1800040dd  lea     r8, [rsp+260h+var_23C]; unsigned int *
0x1800040e2  mov     rcx, rbx; this
0x1800040e5  lea     rdx, [rsp+260h+pStr]; unsigned __int16 *
0x1800040ea  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x1800040ef  mov     ecx, eax
0x1800040f1  test    eax, eax
0x1800040f3  js      short loc_1800040FC
0x1800040f5  cmp     [rsp+260h+var_23C], 0Dh
0x1800040fa  jmp     short loc_1800040B6
0x1800040fc  test    ecx, ecx
0x1800040fe  js      loc_180004060
0x180004104  lea     r8, [rsp+260h+var_240]; unsigned int *
0x180004109  mov     [rdi+20h], rsi
0x18000410d  lea     rdx, [rsp+260h+pStr]; unsigned __int16 *
0x180004112  mov     rcx, rbx; this
0x180004115  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x18000411a  mov     ecx, eax
0x18000411c  test    eax, eax
0x18000411e  js      loc_180004060
0x180004124  cmp     [rsp+260h+var_240], 2
0x180004129  jz      loc_1800041DB
0x18000412f  cmp     [rsp+260h+var_240], 4
0x180004134  jz      loc_1800041D4
0x18000413a  cmp     dword ptr [rbx+14h], 4
0x18000413e  jz      short loc_18000414C
0x180004140  mov     eax, [rbx+10h]
0x180004143  neg     rax
0x180004146  add     rax, rax
0x180004149  add     [rbx], rax
0x18000414c  mov     rdx, rdi; struct _objectinfo *
0x18000414f  mov     rcx, rbx; this
0x180004152  call    ?IISObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; IISObject(CLexer *,_objectinfo *)
0x180004157  mov     ecx, eax
0x180004159  test    eax, eax
0x18000415b  js      loc_180004060
0x180004161  lea     r8, [rsp+260h+var_240]; unsigned int *
0x180004166  mov     rcx, rbx; this
0x180004169  lea     rdx, [rsp+260h+pStr]; unsigned __int16 *
0x18000416e  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x180004173  mov     ecx, eax
0x180004175  test    eax, eax
0x180004177  js      loc_180004060
0x18000417d  cmp     [rsp+260h+var_240], 2
0x180004182  jz      short loc_180004195
0x180004184  cmp     [rsp+260h+var_240], 4
0x180004189  jz      short loc_1800041D4
0x18000418b  mov     eax, 80004005h
0x180004190  jmp     loc_180004062
0x180004195  mov     rcx, rbx; struct CLexer *
0x180004198  call    ?Type@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; Type(CLexer *,_objectinfo *)
0x18000419d  mov     ecx, eax
0x18000419f  test    eax, eax
0x1800041a1  js      loc_180004060
0x1800041a7  lea     r8, [rsp+260h+var_240]; unsigned int *
0x1800041ac  mov     rcx, rbx; this
0x1800041af  lea     rdx, [rsp+260h+pStr]; unsigned __int16 *
0x1800041b4  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x1800041b9  mov     ecx, eax
0x1800041bb  test    eax, eax
0x1800041bd  js      loc_180004060
0x1800041c3  cmp     [rsp+260h+var_240], 4
0x1800041c8  jz      short loc_1800041D4
0x1800041ca  mov     eax, 80005000h
0x1800041cf  jmp     loc_180004062
0x1800041d4  xor     eax, eax
0x1800041d6  jmp     loc_180004062
0x1800041db  mov     rcx, rbx; struct CLexer *
0x1800041de  call    ?Type@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; Type(CLexer *,_objectinfo *)
0x1800041e3  mov     ecx, eax
0x1800041e5  test    eax, eax
0x1800041e7  js      loc_180004060
0x1800041ed  lea     r8, [rsp+260h+var_240]; unsigned int *
0x1800041f2  mov     rcx, rbx; this
0x1800041f5  lea     rdx, [rsp+260h+pStr]; unsigned __int16 *
0x1800041fa  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x1800041ff  mov     ecx, eax
0x180004201  test    eax, eax
0x180004203  js      loc_180004060
0x180004209  mov     eax, [rsp+260h+var_240]
0x18000420d  sub     eax, 4
0x180004210  neg     eax
0x180004212  sbb     eax, eax
0x180004214  and     eax, 80005000h
0x180004219  jmp     loc_180004062
```
