# FindAcceptBypassCacheEntry

- ea: `0x140033e20`
- end: `0x140034087`
- name: `FindAcceptBypassCacheEntry`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140033c70`

## callees

- `0x140033e20`
- `0x140078920`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14003406e`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14003406e`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140033f42`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140033f42`
- `ntoskrnl!RtlEqualSid` at `0x140034033`
- `ntoskrnl!RtlEqualSid` at `0x140034033`

## pseudocode

```c
__int64 __fastcall FindAcceptBypassCacheEntry(__int64 a1, __int64 a2, PRTL_DYNAMIC_HASH_TABLE_ENTRY *a3)
{
  __int64 result; // rax
  bool v4; // zf
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 i; // rcx
  __int64 v11; // r8
  __int64 v12; // rdx
  ULONG_PTR v13; // rdx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY j; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v15; // rdi
  unsigned int Blink; // eax
  unsigned int Signature; // eax
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-28h] BYREF

  result = 0;
  v4 = *(_DWORD *)a1 == 1;
  Context.Signature = 0;
  *a3 = 0;
  *(_OWORD *)&Context.ChainHead = 0;
  if ( v4 )
  {
    _mm_lfence();
    v8 = *(unsigned __int8 *)(a2 + 25) + 37LL * *(unsigned __int8 *)(a2 + 24);
    _mm_lfence();
    v9 = *(unsigned __int8 *)(a2 + 26) + 37 * v8;
    for ( i = 0; (unsigned int)i < *(unsigned __int8 *)(a2 + 27); v9 = v11 + 37 * v9 )
    {
      v11 = *(unsigned __int8 *)(i + a2 + 28);
      i = (unsigned int)(i + 1);
    }
    _mm_lfence();
    v12 = *(unsigned __int8 *)(a2 + 55)
        + 37
        * (*(unsigned __int8 *)(a2 + 54)
         + 37
         * (*(unsigned __int8 *)(a2 + 53)
          + 37
          * (*(unsigned __int8 *)(a2 + 52)
           + 37
           * (*(unsigned __int8 *)(a2 + 51)
            + 37
            * (*(unsigned __int8 *)(a2 + 50)
             + 37 * (*(unsigned __int8 *)(a2 + 49) + 37 * (*(unsigned __int8 *)(a2 + 48) + 37 * v9)))))));
    _mm_lfence();
    v13 = *(unsigned __int8 *)(a1 + 39)
        + 37
        * (*(unsigned __int8 *)(a1 + 38)
         + 37 * (*(unsigned __int8 *)(a1 + 37) + 37 * (*(unsigned __int8 *)(a1 + 36) + 37 * v12)));
    if ( !v13 )
      v13 = -1;
    for ( j = RtlLookupEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8), v13, &Context);
          ;
          j = RtlGetNextEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8), &Context) )
    {
      v15 = j;
      if ( !j )
        break;
      if ( *(_DWORD *)(a1 + 36) == LODWORD(j[1].Linkage.Flink)
        && LODWORD(j[4].Linkage.Flink) == *(_DWORD *)(a2 + 16)
        && HIDWORD(j[4].Linkage.Flink) == *(_DWORD *)(a2 + 20)
        && BYTE2(j[4].Linkage.Blink) == *(_BYTE *)(a2 + 26)
        && LOWORD(j[4].Linkage.Blink) == *(_WORD *)(a2 + 24)
        && j[5].Linkage.Blink == *(struct _LIST_ENTRY **)(a2 + 48)
        && LODWORD(j[5].Signature) == *(_DWORD *)(a2 + 56)
        && HIDWORD(j[5].Signature) == *(_DWORD *)(a2 + 60)
        && BYTE3(j[4].Linkage.Blink) == *(_BYTE *)(a2 + 27)
        && !memcmp((char *)&j[4].Linkage.Blink + 4, (const void *)(a2 + 28), BYTE3(j[4].Linkage.Blink)) )
      {
        Blink = (unsigned int)v15[3].Linkage.Blink;
        if ( Blink == *(_DWORD *)a2
          && !memcmp((const void *)v15[3].Signature, *(const void **)(a2 + 8), Blink)
          && HIDWORD(v15[5].Linkage.Flink) == *(_DWORD *)(a2 + 44)
          && LODWORD(v15[6].Linkage.Flink) == *(_DWORD *)(a2 + 64) )
        {
          if ( RtlEqualSid(v15[6].Linkage.Blink, *(PSID *)(a2 + 72)) )
          {
            Signature = v15[6].Signature;
            if ( Signature == *(_DWORD *)(a2 + 80)
              && !memcmp(v15[7].Linkage.Flink, *(const void **)(a2 + 88), Signature) )
            {
              *a3 = v15;
              return 0;
            }
          }
        }
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140033e20  mov     [rsp+arg_8], rbx
0x140033e25  mov     [rsp+arg_10], rsi
0x140033e2a  push    r14
0x140033e2c  sub     rsp, 40h
0x140033e30  xor     eax, eax
0x140033e32  xorps   xmm0, xmm0
0x140033e35  cmp     dword ptr [rcx], 1
0x140033e38  mov     r14, r8
0x140033e3b  mov     rbx, rdx
0x140033e3e  mov     [rsp+48h+Context.Signature], rax
0x140033e43  mov     rsi, rcx
0x140033e46  mov     [r8], rax
0x140033e49  movups  xmmword ptr [rsp+48h+Context.ChainHead], xmm0
0x140033e4e  jnz     loc_140033F5D
0x140033e54  mov     [rsp+48h+arg_0], rdi
0x140033e59  lfence
0x140033e5c  movzx   eax, byte ptr [rdx+18h]
0x140033e60  imul    rdx, rax, 25h ; '%'
0x140033e64  movzx   eax, byte ptr [rbx+19h]
0x140033e68  add     rdx, rax
0x140033e6b  lfence
0x140033e6e  movzx   ecx, byte ptr [rbx+1Ah]
0x140033e72  movzx   r9d, byte ptr [rbx+1Bh]
0x140033e77  imul    rax, rdx, 25h ; '%'
0x140033e7b  add     rax, rcx
0x140033e7e  xor     ecx, ecx
0x140033e80  test    r9d, r9d
0x140033e83  jz      short loc_140033EA4
0x140033e85  nop     word ptr [rax+rax+00000000h]
0x140033e90  movzx   r8d, byte ptr [rcx+rbx+1Ch]
0x140033e96  inc     ecx
0x140033e98  imul    rax, 25h ; '%'
0x140033e9c  add     rax, r8
0x140033e9f  cmp     ecx, r9d
0x140033ea2  jb      short loc_140033E90
0x140033ea4  lfence
0x140033ea7  imul    rcx, rax, 25h ; '%'
0x140033eab  movzx   eax, byte ptr [rbx+30h]
0x140033eaf  add     rcx, rax
0x140033eb2  movzx   eax, byte ptr [rbx+31h]
0x140033eb6  imul    rdx, rcx, 25h ; '%'
0x140033eba  add     rdx, rax
0x140033ebd  movzx   eax, byte ptr [rbx+32h]
0x140033ec1  imul    rcx, rdx, 25h ; '%'
0x140033ec5  add     rcx, rax
0x140033ec8  movzx   eax, byte ptr [rbx+33h]
0x140033ecc  imul    rdx, rcx, 25h ; '%'
0x140033ed0  add     rdx, rax
0x140033ed3  movzx   eax, byte ptr [rbx+34h]
0x140033ed7  imul    rcx, rdx, 25h ; '%'
0x140033edb  add     rcx, rax
0x140033ede  movzx   eax, byte ptr [rbx+35h]
0x140033ee2  imul    rdx, rcx, 25h ; '%'
0x140033ee6  add     rdx, rax
0x140033ee9  movzx   eax, byte ptr [rbx+36h]
0x140033eed  imul    rcx, rdx, 25h ; '%'
0x140033ef1  add     rcx, rax
0x140033ef4  movzx   eax, byte ptr [rbx+37h]
0x140033ef8  imul    rdx, rcx, 25h ; '%'
0x140033efc  add     rdx, rax
0x140033eff  lfence
0x140033f02  movzx   eax, byte ptr [rsi+24h]
0x140033f06  lea     r8, [rsp+48h+Context]; Context
0x140033f0b  imul    rcx, rdx, 25h ; '%'
0x140033f0f  add     rcx, rax
0x140033f12  movzx   eax, byte ptr [rsi+25h]
0x140033f16  imul    rdx, rcx, 25h ; '%'
0x140033f1a  add     rdx, rax
0x140033f1d  movzx   eax, byte ptr [rsi+26h]
0x140033f21  imul    rcx, rdx, 25h ; '%'
0x140033f25  add     rcx, rax
0x140033f28  movzx   eax, byte ptr [rsi+27h]
0x140033f2c  imul    rdx, rcx, 25h ; '%'
0x140033f30  mov     rcx, [rsi+8]; HashTable
0x140033f34  add     rdx, rax
0x140033f37  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140033f3e  cmovz   rdx, rax; Signature
0x140033f42  call    cs:__imp_RtlLookupEntryHashTable
0x140033f49  nop     dword ptr [rax+rax+00h]
0x140033f4e  mov     rdi, rax
0x140033f51  test    rax, rax
0x140033f54  jnz     short loc_140033F6F
0x140033f56  mov     rdi, [rsp+48h+arg_0]
0x140033f5b  xor     eax, eax
0x140033f5d  mov     rbx, [rsp+48h+arg_8]
0x140033f62  mov     rsi, [rsp+48h+arg_10]
0x140033f67  add     rsp, 40h
0x140033f6b  pop     r14
0x140033f6d  retn
0x140033f6f  mov     ecx, [rdi+18h]
0x140033f72  cmp     [rsi+24h], ecx
0x140033f75  jnz     loc_140034065
0x140033f7b  mov     ecx, [rbx+10h]
0x140033f7e  cmp     [rdi+60h], ecx
0x140033f81  jnz     loc_140034065
0x140033f87  mov     eax, [rbx+14h]
0x140033f8a  cmp     [rdi+64h], eax
0x140033f8d  jnz     loc_140034065
0x140033f93  movzx   eax, byte ptr [rbx+1Ah]
0x140033f97  cmp     [rdi+6Ah], al
0x140033f9a  jnz     loc_140034065
0x140033fa0  movzx   eax, word ptr [rbx+18h]
0x140033fa4  cmp     [rdi+68h], ax
0x140033fa8  jnz     loc_140034065
0x140033fae  mov     rax, [rbx+30h]
0x140033fb2  cmp     [rdi+80h], rax
0x140033fb9  jnz     loc_140034065
0x140033fbf  mov     eax, [rbx+38h]
0x140033fc2  cmp     [rdi+88h], eax
0x140033fc8  jnz     loc_140034065
0x140033fce  mov     eax, [rbx+3Ch]
0x140033fd1  cmp     [rdi+8Ch], eax
0x140033fd7  jnz     loc_140034065
0x140033fdd  movzx   eax, byte ptr [rdi+6Bh]
0x140033fe1  cmp     al, [rbx+1Bh]
0x140033fe4  jnz     short loc_140034065
0x140033fe6  mov     r8d, eax; Size
0x140033fe9  lea     rdx, [rbx+1Ch]; Buf2
0x140033fed  lea     rcx, [rdi+6Ch]; Buf1
0x140033ff1  call    memcmp
0x140033ff6  test    eax, eax
0x140033ff8  jnz     short loc_140034065
0x140033ffa  mov     eax, [rdi+50h]
0x140033ffd  cmp     eax, [rbx]
0x140033fff  jnz     short loc_140034065
0x140034001  mov     rdx, [rbx+8]; Buf2
0x140034005  mov     r8d, eax; Size
0x140034008  mov     rcx, [rdi+58h]; Buf1
0x14003400c  call    memcmp
0x140034011  test    eax, eax
0x140034013  jnz     short loc_140034065
0x140034015  mov     eax, [rbx+2Ch]
0x140034018  cmp     [rdi+7Ch], eax
0x14003401b  jnz     short loc_140034065
0x14003401d  mov     eax, [rbx+40h]
0x140034020  cmp     [rdi+90h], eax
0x140034026  jnz     short loc_140034065
0x140034028  mov     rdx, [rbx+48h]; Sid2
0x14003402c  mov     rcx, [rdi+98h]; Sid1
0x140034033  call    cs:__imp_RtlEqualSid
0x14003403a  nop     dword ptr [rax+rax+00h]
0x14003403f  test    al, al
0x140034041  jz      short loc_140034065
0x140034043  mov     eax, [rdi+0A0h]
0x140034049  cmp     eax, [rbx+50h]
0x14003404c  jnz     short loc_140034065
0x14003404e  mov     rdx, [rbx+58h]; Buf2
0x140034052  mov     r8d, eax; Size
0x140034055  mov     rcx, [rdi+0A8h]; Buf1
0x14003405c  call    memcmp
0x140034061  test    eax, eax
0x140034063  jz      short loc_14003407F
0x140034065  mov     rcx, [rsi+8]; HashTable
0x140034069  lea     rdx, [rsp+48h+Context]; Context
0x14003406e  call    cs:__imp_RtlGetNextEntryHashTable
0x140034075  nop     dword ptr [rax+rax+00h]
0x14003407a  jmp     loc_140033F4E
0x14003407f  mov     [r14], rdi
0x140034082  jmp     loc_140033F56
```
