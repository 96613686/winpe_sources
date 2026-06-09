# WPP_SF_ZZsd

- ea: `0x18003af20`
- end: `0x18003b09a`
- name: `WPP_SF_ZZsd`
- size: `378`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002e40`

## callees

- `0x18003af20`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003b086`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003b086`

## string_xrefs

- `0x18003b036`: `onecore\ds\security\protocols\pku2u\token.cxx`

## pseudocode

```c
ULONG __fastcall WPP_SF_ZZsd(TRACEHANDLE LoggerHandle, __int64 a2, __int64 a3, int *a4, _WORD *a5)
{
  int *v5; // rdx
  const wchar_t *v6; // rbx
  __int64 v7; // r8
  const wchar_t **v9; // rax
  __int64 v10; // r11
  const wchar_t *v11; // rcx
  const wchar_t *v12; // r10
  const wchar_t **v13; // rax
  const wchar_t *v14; // rcx
  int v16[14]; // [rsp+90h] [rbp-38h] BYREF

  v5 = (int *)a5;
  v6 = L"(empty)";
  v7 = 16;
  v16[0] = 645;
  v9 = (const wchar_t **)(a5 + 4);
  if ( a5 && *v9 )
  {
    if ( *a5 )
      v10 = (unsigned __int16)*a5;
    else
      v10 = 16;
    v11 = *v9;
LABEL_9:
    v12 = L"(empty)";
    if ( *a5 )
      v12 = v11;
    goto LABEL_14;
  }
  v10 = 14;
  if ( a5 )
  {
    v11 = *v9;
    if ( *v9 )
      goto LABEL_9;
  }
  v12 = L"(null)";
  if ( !a5 || !*v9 )
  {
    v5 = &dword_18004AC8C;
    goto LABEL_18;
  }
LABEL_14:
  if ( !*a5 )
    v5 = (int *)byte_18004AC88;
LABEL_18:
  v13 = (const wchar_t **)(a4 + 2);
  if ( a4 && *v13 )
  {
    if ( *(_WORD *)a4 )
      v7 = *(unsigned __int16 *)a4;
    v14 = *v13;
    goto LABEL_25;
  }
  v7 = 14;
  if ( a4 )
  {
    v14 = *v13;
    if ( *v13 )
    {
LABEL_25:
      if ( *(_WORD *)a4 )
        v6 = v14;
      goto LABEL_30;
    }
  }
  v6 = L"(null)";
  if ( !a4 || !*v13 )
  {
    a4 = &dword_18004AC8C;
    return TraceMessage(
             LoggerHandle,
             0x2Bu,
             &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
             0x13u,
             a4,
             2,
             v6,
             v7,
             v5,
             2,
             v12,
             v10,
             "onecore\\ds\\security\\protocols\\pku2u\\token.cxx",
             46,
             v16,
             4,
             0);
  }
LABEL_30:
  if ( !*(_WORD *)a4 )
    a4 = (int *)byte_18004AC88;
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
           0x13u,
           a4,
           2,
           v6,
           v7,
           v5,
           2,
           v12,
           v10,
           "onecore\\ds\\security\\protocols\\pku2u\\token.cxx",
           46,
           v16,
           4,
           0);
}

```

## disassembly

```asm
0x18003af20  mov     rax, rsp
0x18003af23  push    rbx
0x18003af24  push    rbp
0x18003af25  push    rsi
0x18003af26  push    rdi
0x18003af27  push    r14
0x18003af29  sub     rsp, 0A0h
0x18003af30  mov     rdx, [rsp+0C8h+arg_20]
0x18003af38  lea     rbx, aEmpty; "(empty)"
0x18003af3f  mov     r8d, 10h
0x18003af45  mov     dword ptr [rax-38h], 285h
0x18003af4c  xor     esi, esi
0x18003af4e  lea     r14, byte_18004AC88
0x18003af55  mov     rdi, rcx
0x18003af58  lea     rax, [rdx+8]
0x18003af5c  lea     ebp, [r8-2]
0x18003af60  test    rdx, rdx
0x18003af63  jz      short loc_18003AF7D
0x18003af65  cmp     [rax], rsi
0x18003af68  jz      short loc_18003AF7D
0x18003af6a  cmp     [rdx], si
0x18003af6d  jz      short loc_18003AF75
0x18003af6f  movzx   r11d, word ptr [rdx]
0x18003af73  jmp     short loc_18003AF78
0x18003af75  mov     r11, r8
0x18003af78  mov     rcx, [rax]
0x18003af7b  jmp     short loc_18003AF8D
0x18003af7d  mov     r11, rbp
0x18003af80  test    rdx, rdx
0x18003af83  jz      short loc_18003AF99
0x18003af85  mov     rcx, [rax]
0x18003af88  test    rcx, rcx
0x18003af8b  jz      short loc_18003AF99
0x18003af8d  cmp     [rdx], si
0x18003af90  mov     r10, rbx
0x18003af93  cmovnz  r10, rcx
0x18003af97  jmp     short loc_18003AFAA
0x18003af99  lea     r10, aNull_0; "(null)"
0x18003afa0  test    rdx, rdx
0x18003afa3  jz      short loc_18003AFB3
0x18003afa5  cmp     [rax], rsi
0x18003afa8  jz      short loc_18003AFB3
0x18003afaa  cmp     [rdx], si
0x18003afad  cmovz   rdx, r14
0x18003afb1  jmp     short loc_18003AFBA
0x18003afb3  lea     rdx, dword_18004AC8C
0x18003afba  lea     rax, [r9+8]
0x18003afbe  test    r9, r9
0x18003afc1  jz      short loc_18003AFD7
0x18003afc3  cmp     [rax], rsi
0x18003afc6  jz      short loc_18003AFD7
0x18003afc8  cmp     [r9], si
0x18003afcc  jz      short loc_18003AFD2
0x18003afce  movzx   r8d, word ptr [r9]
0x18003afd2  mov     rcx, [rax]
0x18003afd5  jmp     short loc_18003AFE7
0x18003afd7  mov     r8, rbp
0x18003afda  test    r9, r9
0x18003afdd  jz      short loc_18003AFF1
0x18003afdf  mov     rcx, [rax]
0x18003afe2  test    rcx, rcx
0x18003afe5  jz      short loc_18003AFF1
0x18003afe7  cmp     [r9], si
0x18003afeb  cmovnz  rbx, rcx
0x18003afef  jmp     short loc_18003B002
0x18003aff1  lea     rbx, aNull_0; "(null)"
0x18003aff8  test    r9, r9
0x18003affb  jz      short loc_18003B00C
0x18003affd  cmp     [rax], rsi
0x18003b000  jz      short loc_18003B00C
0x18003b002  cmp     [r9], si
0x18003b006  cmovz   r9, r14
0x18003b00a  jmp     short loc_18003B013
0x18003b00c  lea     r9, dword_18004AC8C
0x18003b013  mov     [rsp+0C8h+var_48], rsi
0x18003b01b  lea     rax, [rsp+0C8h+var_38]
0x18003b023  mov     [rsp+0C8h+var_50], 4
0x18003b02c  mov     ecx, 13h
0x18003b031  mov     [rsp+0C8h+var_58], rax
0x18003b036  lea     rax, aOnecoreDsSecur_3; "onecore\\ds\\security\\protocols\\pku2u"...
0x18003b03d  mov     [rsp+0C8h+var_60], 2Eh ; '.'
0x18003b046  mov     [rsp+0C8h+var_68], rax
0x18003b04b  mov     [rsp+0C8h+var_70], r11
0x18003b050  lea     eax, [rcx-11h]
0x18003b053  mov     [rsp+0C8h+var_78], r10
0x18003b058  mov     [rsp+0C8h+var_80], rax
0x18003b05d  mov     [rsp+0C8h+var_88], rdx
0x18003b062  lea     edx, [rcx+18h]; MessageFlags
0x18003b065  mov     [rsp+0C8h+var_90], r8
0x18003b06a  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids; MessageGuid
0x18003b071  mov     [rsp+0C8h+var_98], rbx
0x18003b076  mov     [rsp+0C8h+var_A0], rax
0x18003b07b  mov     [rsp+0C8h+var_A8], r9
0x18003b080  mov     r9d, ecx; MessageNumber
0x18003b083  mov     rcx, rdi; LoggerHandle
0x18003b086  call    cs:__imp_TraceMessage
0x18003b08c  add     rsp, 0A0h
0x18003b093  pop     r14
0x18003b095  pop     rdi
0x18003b096  pop     rsi
0x18003b097  pop     rbp
0x18003b098  pop     rbx
0x18003b099  retn
```
