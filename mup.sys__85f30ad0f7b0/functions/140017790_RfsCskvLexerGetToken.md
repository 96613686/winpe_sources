# RfsCskvLexerGetToken

- ea: `0x140017790`
- end: `0x1400178ea`
- name: `RfsCskvLexerGetToken`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140017a98`

## callees

- `0x140017364`
- `0x1400173f4`
- `0x140017538`
- `0x14001766c`
- `0x140017790`
- `0x140017918`
- `0x1400179ac`

## import_xrefs

- `ntoskrnl!iswdigit` at `0x1400178a0`
- `ntoskrnl!iswdigit` at `0x1400178a0`

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
0x140017790  mov     [rsp+arg_8], rbx
0x140017795  push    rdi
0x140017796  sub     rsp, 20h
0x14001779a  xorps   xmm0, xmm0
0x14001779d  xor     eax, eax
0x14001779f  movups  xmmword ptr [rdx], xmm0
0x1400177a2  mov     rbx, rdx
0x1400177a5  mov     rdi, rcx
0x1400177a8  movups  xmmword ptr [rdx+10h], xmm0
0x1400177ac  mov     [rsp+28h+arg_0], ax
0x1400177b1  jmp     short loc_1400177DD
0x1400177b3  cmp     [rsp+28h+arg_0], 20h ; ' '
0x1400177b9  ja      short loc_1400177EB
0x1400177bb  movzx   eax, [rsp+28h+arg_0]
0x1400177c0  mov     rcx, 100002601h
0x1400177ca  bt      rcx, rax
0x1400177ce  jnb     short loc_1400177EB
0x1400177d0  lea     rdx, [rsp+28h+arg_0]
0x1400177d5  mov     rcx, rdi
0x1400177d8  call    RfsCskvLexerStreamGetChar
0x1400177dd  lea     rdx, [rsp+28h+arg_0]
0x1400177e2  call    RfsCskvLexerStreamPeekChar
0x1400177e7  test    al, al
0x1400177e9  jnz     short loc_1400177B3
0x1400177eb  lea     rdx, [rsp+28h+arg_0]
0x1400177f0  mov     rcx, rdi
0x1400177f3  call    RfsCskvLexerStreamPeekChar
0x1400177f8  test    al, al
0x1400177fa  jnz     short loc_140017809
0x1400177fc  mov     dword ptr [rbx], 0
0x140017802  xor     eax, eax
0x140017804  jmp     loc_1400178DE
0x140017809  movzx   ecx, [rsp+28h+arg_0]; C
0x14001780e  cmp     cx, 27h ; '''
0x140017812  jz      loc_1400178CA
0x140017818  cmp     cx, 22h ; '"'
0x14001781c  jz      loc_1400178CA
0x140017822  cmp     cx, 2Ch ; ','
0x140017826  jnz     short loc_140017849
0x140017828  lea     rdx, [rsp+28h+arg_0]
0x14001782d  mov     rcx, rdi
0x140017830  call    RfsCskvLexerStreamGetChar
0x140017835  movups  xmm0, xmmword ptr cs:RfsCskvCommaString
0x14001783c  mov     dword ptr [rbx], 1
0x140017842  movdqu  xmmword ptr [rbx+8], xmm0
0x140017847  jmp     short loc_140017802
0x140017849  cmp     cx, 3Dh ; '='
0x14001784d  jnz     short loc_14001786B
0x14001784f  lea     rdx, [rsp+28h+arg_0]
0x140017854  mov     rcx, rdi
0x140017857  call    RfsCskvLexerStreamGetChar
0x14001785c  movups  xmm0, xmmword ptr cs:RfsCskvEqualsString
0x140017863  mov     dword ptr [rbx], 2
0x140017869  jmp     short loc_140017842
0x14001786b  lea     eax, [rcx-41h]
0x14001786e  cmp     ax, 39h ; '9'
0x140017872  ja      short loc_140017891
0x140017874  mov     rdx, 3FFFFFF43FFFFFFh
0x14001787e  bt      rdx, rax
0x140017882  jnb     short loc_140017891
0x140017884  mov     rdx, rbx
0x140017887  mov     rcx, rdi
0x14001788a  call    RfsCskvLexerGetIdentifier
0x14001788f  jmp     short loc_1400178DE
0x140017891  cmp     cx, 2Dh ; '-'
0x140017895  jz      short loc_1400178BD
0x140017897  lea     eax, [rcx-30h]
0x14001789a  cmp     ax, 9
0x14001789e  jbe     short loc_1400178BD
0x1400178a0  call    cs:__imp_iswdigit
0x1400178a7  nop     dword ptr [rax+rax+00h]
0x1400178ac  test    eax, eax
0x1400178ae  jnz     short loc_1400178BD
0x1400178b0  mov     rdx, rbx
0x1400178b3  mov     rcx, rdi
0x1400178b6  call    RfsCskvLexerGetError
0x1400178bb  jmp     short loc_1400178DE
0x1400178bd  mov     rdx, rbx
0x1400178c0  mov     rcx, rdi
0x1400178c3  call    RfsCskvLexerGetNumber
0x1400178c8  jmp     short loc_1400178DE
0x1400178ca  movups  xmm0, xmmword ptr [rdi+20h]
0x1400178ce  mov     rdx, rbx
0x1400178d1  mov     rcx, rdi
0x1400178d4  movdqu  xmmword ptr [rbx+8], xmm0
0x1400178d9  call    RfsCskvLexerGetString
0x1400178de  mov     rbx, [rsp+28h+arg_8]
0x1400178e3  add     rsp, 20h
0x1400178e7  pop     rdi
0x1400178e8  retn
```
