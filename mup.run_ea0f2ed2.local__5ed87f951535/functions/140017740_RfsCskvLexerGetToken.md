# RfsCskvLexerGetToken

- ea: `0x140017740`
- end: `0x14001789a`
- name: `RfsCskvLexerGetToken`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140017a48`

## callees

- `0x140017314`
- `0x1400173a4`
- `0x1400174e8`
- `0x14001761c`
- `0x140017740`
- `0x1400178c8`
- `0x14001795c`

## import_xrefs

- `ntoskrnl!iswdigit` at `0x140017850`
- `ntoskrnl!iswdigit` at `0x140017850`

## pseudocode

```c
__int64 __fastcall RfsCskvLexerGetToken(__int64 a1, _OWORD *a2)
{
  __int64 v4; // rcx
  __int128 v6; // xmm0
  __int64 v7; // rdx
  wint_t i; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  a2[1] = 0;
  for ( i = 0; (unsigned __int8)RfsCskvLexerStreamPeekChar(a1, &i); RfsCskvLexerStreamGetChar(a1, &i) )
  {
    if ( i > 0x20u )
      break;
    v4 = 0x100002601LL;
    if ( !_bittest64(&v4, i) )
      break;
  }
  if ( !(unsigned __int8)RfsCskvLexerStreamPeekChar(a1, &i) )
  {
    *(_DWORD *)a2 = 0;
    return 0;
  }
  switch ( i )
  {
    case '\'':
    case '"':
      *(_OWORD *)((char *)a2 + 8) = *(_OWORD *)(a1 + 32);
      return RfsCskvLexerGetString(a1, a2);
    case ',':
      RfsCskvLexerStreamGetChar(a1, &i);
      v6 = *(_OWORD *)RfsCskvCommaString;
      *(_DWORD *)a2 = 1;
LABEL_13:
      *(_OWORD *)((char *)a2 + 8) = v6;
      return 0;
    case '=':
      RfsCskvLexerStreamGetChar(a1, &i);
      v6 = *(_OWORD *)RfsCskvEqualsString;
      *(_DWORD *)a2 = 2;
      goto LABEL_13;
    default:
      if ( (unsigned __int16)(i - 65) <= 0x39u && (v7 = 0x3FFFFFF43FFFFFFLL, _bittest64(&v7, (unsigned int)i - 65)) )
      {
        return RfsCskvLexerGetIdentifier(a1, a2);
      }
      else if ( i == 45 || (unsigned __int16)(i - 48) <= 9u || iswdigit(i) )
      {
        return RfsCskvLexerGetNumber(a1, a2);
      }
      else
      {
        return RfsCskvLexerGetError(a1, a2);
      }
  }
}

```

## disassembly

```asm
0x140017740  mov     [rsp+arg_8], rbx
0x140017745  push    rdi
0x140017746  sub     rsp, 20h
0x14001774a  xorps   xmm0, xmm0
0x14001774d  xor     eax, eax
0x14001774f  movups  xmmword ptr [rdx], xmm0
0x140017752  mov     rbx, rdx
0x140017755  mov     rdi, rcx
0x140017758  movups  xmmword ptr [rdx+10h], xmm0
0x14001775c  mov     [rsp+28h+arg_0], ax
0x140017761  jmp     short loc_14001778D
0x140017763  cmp     [rsp+28h+arg_0], 20h ; ' '
0x140017769  ja      short loc_14001779B
0x14001776b  movzx   eax, [rsp+28h+arg_0]
0x140017770  mov     rcx, 100002601h
0x14001777a  bt      rcx, rax
0x14001777e  jnb     short loc_14001779B
0x140017780  lea     rdx, [rsp+28h+arg_0]
0x140017785  mov     rcx, rdi
0x140017788  call    RfsCskvLexerStreamGetChar
0x14001778d  lea     rdx, [rsp+28h+arg_0]
0x140017792  call    RfsCskvLexerStreamPeekChar
0x140017797  test    al, al
0x140017799  jnz     short loc_140017763
0x14001779b  lea     rdx, [rsp+28h+arg_0]
0x1400177a0  mov     rcx, rdi
0x1400177a3  call    RfsCskvLexerStreamPeekChar
0x1400177a8  test    al, al
0x1400177aa  jnz     short loc_1400177B9
0x1400177ac  mov     dword ptr [rbx], 0
0x1400177b2  xor     eax, eax
0x1400177b4  jmp     loc_14001788E
0x1400177b9  movzx   ecx, [rsp+28h+arg_0]; C
0x1400177be  cmp     cx, 27h ; '''
0x1400177c2  jz      loc_14001787A
0x1400177c8  cmp     cx, 22h ; '"'
0x1400177cc  jz      loc_14001787A
0x1400177d2  cmp     cx, 2Ch ; ','
0x1400177d6  jnz     short loc_1400177F9
0x1400177d8  lea     rdx, [rsp+28h+arg_0]
0x1400177dd  mov     rcx, rdi
0x1400177e0  call    RfsCskvLexerStreamGetChar
0x1400177e5  movups  xmm0, xmmword ptr cs:RfsCskvCommaString
0x1400177ec  mov     dword ptr [rbx], 1
0x1400177f2  movdqu  xmmword ptr [rbx+8], xmm0
0x1400177f7  jmp     short loc_1400177B2
0x1400177f9  cmp     cx, 3Dh ; '='
0x1400177fd  jnz     short loc_14001781B
0x1400177ff  lea     rdx, [rsp+28h+arg_0]
0x140017804  mov     rcx, rdi
0x140017807  call    RfsCskvLexerStreamGetChar
0x14001780c  movups  xmm0, xmmword ptr cs:RfsCskvEqualsString
0x140017813  mov     dword ptr [rbx], 2
0x140017819  jmp     short loc_1400177F2
0x14001781b  lea     eax, [rcx-41h]
0x14001781e  cmp     ax, 39h ; '9'
0x140017822  ja      short loc_140017841
0x140017824  mov     rdx, 3FFFFFF43FFFFFFh
0x14001782e  bt      rdx, rax
0x140017832  jnb     short loc_140017841
0x140017834  mov     rdx, rbx
0x140017837  mov     rcx, rdi
0x14001783a  call    RfsCskvLexerGetIdentifier
0x14001783f  jmp     short loc_14001788E
0x140017841  cmp     cx, 2Dh ; '-'
0x140017845  jz      short loc_14001786D
0x140017847  lea     eax, [rcx-30h]
0x14001784a  cmp     ax, 9
0x14001784e  jbe     short loc_14001786D
0x140017850  call    cs:__imp_iswdigit
0x140017857  nop     dword ptr [rax+rax+00h]
0x14001785c  test    eax, eax
0x14001785e  jnz     short loc_14001786D
0x140017860  mov     rdx, rbx
0x140017863  mov     rcx, rdi
0x140017866  call    RfsCskvLexerGetError
0x14001786b  jmp     short loc_14001788E
0x14001786d  mov     rdx, rbx
0x140017870  mov     rcx, rdi
0x140017873  call    RfsCskvLexerGetNumber
0x140017878  jmp     short loc_14001788E
0x14001787a  movups  xmm0, xmmword ptr [rdi+20h]
0x14001787e  mov     rdx, rbx
0x140017881  mov     rcx, rdi
0x140017884  movdqu  xmmword ptr [rbx+8], xmm0
0x140017889  call    RfsCskvLexerGetString
0x14001788e  mov     rbx, [rsp+28h+arg_8]
0x140017893  add     rsp, 20h
0x140017897  pop     rdi
0x140017898  retn
```
