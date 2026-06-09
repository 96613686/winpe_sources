# DirCacheCompareShortNames

- ea: `0x140001740`
- end: `0x14000198c`
- name: `DirCacheCompareShortNames`
- size: `588`
- prototype: `int __cdecl(void *, const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001740`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140001904`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140001904`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x140001757`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400017ca`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x140001757`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400017ca`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140001886`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400018a9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400018c8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400018e7`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140001886`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400018a9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400018c8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400018e7`

## pseudocode

```c
LONG __fastcall DirCacheCompareShortNames(_QWORD *a1, unsigned int *a2, unsigned int *a3)
{
  unsigned int v3; // esi
  CCHAR MostSignificantBit; // al
  __int64 v7; // rbx
  unsigned int v8; // edx
  unsigned int v9; // ecx
  __int64 v10; // rdx
  __int64 v11; // r14
  unsigned int v12; // esi
  CCHAR v13; // al
  unsigned int v14; // edx
  unsigned int v15; // eax
  __int64 v16; // rdx
  UNICODE_STRING String2; // [rsp+20h] [rbp-58h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-48h] BYREF

  v3 = *a2;
  MostSignificantBit = RtlFindMostSignificantBit(*a2);
  v7 = 0;
  if ( MostSignificantBit <= 4 )
  {
    v8 = 0;
  }
  else
  {
    v8 = (unsigned int)(MostSignificantBit - 3) >> 1;
    if ( v8 >= 8 )
      goto LABEL_29;
  }
  _mm_lfence();
  if ( v8 )
    v9 = v3 - (32 << (2 * v8 - 2));
  else
    v9 = v3;
  v10 = a1[v8 + 19];
  if ( v10 && v3 < *((_DWORD *)a1 + 54) )
  {
    v11 = v10 + (v9 << 7);
    goto LABEL_8;
  }
LABEL_29:
  __int2c();
  v11 = 0;
LABEL_8:
  v12 = *a3;
  v13 = RtlFindMostSignificantBit(*a3);
  if ( v13 <= 4 )
  {
    v14 = 0;
  }
  else
  {
    v14 = (unsigned int)(v13 - 3) >> 1;
    if ( v14 >= 8 )
      goto LABEL_30;
  }
  _mm_lfence();
  v15 = v12;
  if ( v14 )
    v15 = v12 - (32 << (2 * v14 - 2));
  v16 = a1[v14 + 19];
  if ( v16 && v12 < *((_DWORD *)a1 + 54) )
  {
    v7 = v16 + (v15 << 7);
    goto LABEL_15;
  }
LABEL_30:
  __int2c();
LABEL_15:
  String1 = 0;
  String2 = 0;
  String1.MaximumLength = 2 * (*(_WORD *)(v11 + 86) & 0xF);
  String1.Length = String1.MaximumLength;
  String1.Buffer = (PWSTR)(v11 + 88);
  String2.MaximumLength = 2 * (*(_WORD *)(v7 + 86) & 0xF);
  String2.Length = String2.MaximumLength;
  String2.Buffer = (PWSTR)(v7 + 88);
  if ( !RtlEqualUnicodeString(&String1, &::String2, 0) )
  {
    if ( RtlEqualUnicodeString(&String2, &::String2, 0) )
      return 1;
    if ( !RtlEqualUnicodeString(&String1, &stru_14003E010, 0) )
    {
      if ( !RtlEqualUnicodeString(&String2, &stru_14003E010, 0) )
        return RtlCompareUnicodeString(&String1, &String2, 1u);
      return 1;
    }
  }
  return -1;
}

```

## disassembly

```asm
0x140001740  push    rbx
0x140001742  push    rbp
0x140001743  push    rsi
0x140001744  push    rdi
0x140001745  push    r14
0x140001747  push    r15
0x140001749  sub     rsp, 48h
0x14000174d  mov     esi, [rdx]
0x14000174f  mov     rdi, rcx
0x140001752  mov     ecx, esi; Set
0x140001754  mov     r15, r8
0x140001757  call    cs:__imp_RtlFindMostSignificantBit
0x14000175e  nop     dword ptr [rax+rax+00h]
0x140001763  xor     ebx, ebx
0x140001765  mov     ebp, 20h ; ' '
0x14000176a  cmp     al, 4
0x14000176c  jle     loc_14000191E
0x140001772  movsx   edx, al
0x140001775  sub     edx, 3
0x140001778  shr     edx, 1
0x14000177a  cmp     edx, 8
0x14000177d  jnb     loc_14000197B
0x140001783  lfence
0x140001786  test    edx, edx
0x140001788  jz      loc_14000193F
0x14000178e  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x140001795  mov     eax, ebp
0x140001797  shl     eax, cl
0x140001799  mov     ecx, esi
0x14000179b  sub     ecx, eax
0x14000179d  mov     eax, edx
0x14000179f  mov     rdx, [rdi+rax*8+98h]
0x1400017a7  test    rdx, rdx
0x1400017aa  jz      loc_140001959
0x1400017b0  cmp     esi, [rdi+0D8h]
0x1400017b6  jnb     loc_14000196A
0x1400017bc  shl     ecx, 7
0x1400017bf  mov     r14d, ecx
0x1400017c2  add     r14, rdx
0x1400017c5  mov     esi, [r15]
0x1400017c8  mov     ecx, esi; Set
0x1400017ca  call    cs:__imp_RtlFindMostSignificantBit
0x1400017d1  nop     dword ptr [rax+rax+00h]
0x1400017d6  cmp     al, 4
0x1400017d8  jle     loc_140001925
0x1400017de  movsx   edx, al
0x1400017e1  sub     edx, 3
0x1400017e4  shr     edx, 1
0x1400017e6  cmp     edx, 8
0x1400017e9  jnb     loc_140001985
0x1400017ef  lfence
0x1400017f2  mov     eax, esi
0x1400017f4  test    edx, edx
0x1400017f6  jz      short loc_140001803
0x1400017f8  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x1400017ff  shl     ebp, cl
0x140001801  sub     eax, ebp
0x140001803  mov     ecx, edx
0x140001805  mov     rdx, [rdi+rcx*8+98h]
0x14000180d  test    rdx, rdx
0x140001810  jz      loc_140001963
0x140001816  cmp     esi, [rdi+0D8h]
0x14000181c  jnb     loc_140001974
0x140001822  shl     eax, 7
0x140001825  mov     ebx, eax
0x140001827  add     rbx, rdx
0x14000182a  xorps   xmm0, xmm0
0x14000182d  lea     rdx, String2; String2
0x140001834  movups  xmmword ptr [rsp+78h+String1.Length], xmm0
0x140001839  lea     rcx, [rsp+78h+String1]; String1
0x14000183e  xor     r8d, r8d; CaseInSensitive
0x140001841  xorps   xmm1, xmm1
0x140001844  movups  xmmword ptr [rsp+78h+String2.Length], xmm1
0x140001849  movzx   eax, word ptr [r14+56h]
0x14000184e  and     ax, 0Fh
0x140001852  add     ax, ax
0x140001855  mov     [rsp+78h+String1.MaximumLength], ax
0x14000185a  mov     [rsp+78h+String1.Length], ax
0x14000185f  lea     rax, [r14+58h]
0x140001863  mov     [rsp+78h+String1.Buffer], rax
0x140001868  movzx   eax, word ptr [rbx+56h]
0x14000186c  and     ax, 0Fh
0x140001870  add     ax, ax
0x140001873  mov     [rsp+78h+String2.MaximumLength], ax
0x140001878  mov     [rsp+78h+String2.Length], ax
0x14000187d  lea     rax, [rbx+58h]
0x140001881  mov     [rsp+78h+String2.Buffer], rax
0x140001886  call    cs:__imp_RtlEqualUnicodeString
0x14000188d  nop     dword ptr [rax+rax+00h]
0x140001892  test    al, al
0x140001894  jnz     loc_140001946
0x14000189a  xor     r8d, r8d; CaseInSensitive
0x14000189d  lea     rdx, String2; String2
0x1400018a4  lea     rcx, [rsp+78h+String2]; String1
0x1400018a9  call    cs:__imp_RtlEqualUnicodeString
0x1400018b0  nop     dword ptr [rax+rax+00h]
0x1400018b5  test    al, al
0x1400018b7  jnz     short loc_14000192C
0x1400018b9  xor     r8d, r8d; CaseInSensitive
0x1400018bc  lea     rdx, stru_14003E010; String2
0x1400018c3  lea     rcx, [rsp+78h+String1]; String1
0x1400018c8  call    cs:__imp_RtlEqualUnicodeString
0x1400018cf  nop     dword ptr [rax+rax+00h]
0x1400018d4  test    al, al
0x1400018d6  jnz     short loc_140001946
0x1400018d8  xor     r8d, r8d; CaseInSensitive
0x1400018db  lea     rdx, stru_14003E010; String2
0x1400018e2  lea     rcx, [rsp+78h+String2]; String1
0x1400018e7  call    cs:__imp_RtlEqualUnicodeString
0x1400018ee  nop     dword ptr [rax+rax+00h]
0x1400018f3  test    al, al
0x1400018f5  jnz     short loc_14000192C
0x1400018f7  mov     r8b, 1; CaseInSensitive
0x1400018fa  lea     rdx, [rsp+78h+String2]; String2
0x1400018ff  lea     rcx, [rsp+78h+String1]; String1
0x140001904  call    cs:__imp_RtlCompareUnicodeString
0x14000190b  nop     dword ptr [rax+rax+00h]
0x140001910  add     rsp, 48h
0x140001914  pop     r15
0x140001916  pop     r14
0x140001918  pop     rdi
0x140001919  pop     rsi
0x14000191a  pop     rbp
0x14000191b  pop     rbx
0x14000191c  retn
0x14000191e  mov     edx, ebx
0x140001920  jmp     loc_140001783
0x140001925  mov     edx, ebx
0x140001927  jmp     loc_1400017EF
0x14000192c  mov     eax, 1
0x140001931  add     rsp, 48h
0x140001935  pop     r15
0x140001937  pop     r14
0x140001939  pop     rdi
0x14000193a  pop     rsi
0x14000193b  pop     rbp
0x14000193c  pop     rbx
0x14000193d  retn
0x14000193f  mov     ecx, esi
0x140001941  jmp     loc_14000179D
0x140001946  mov     eax, 0FFFFFFFFh
0x14000194b  add     rsp, 48h
0x14000194f  pop     r15
0x140001951  pop     r14
0x140001953  pop     rdi
0x140001954  pop     rsi
0x140001955  pop     rbp
0x140001956  pop     rbx
0x140001957  retn
0x140001959  int     2Ch; Windows NT - assertion failure
0x14000195b  mov     r14, rbx
0x14000195e  jmp     loc_1400017C5
0x140001963  int     2Ch; Windows NT - assertion failure
0x140001965  jmp     loc_14000182A
0x14000196a  int     2Ch; Windows NT - assertion failure
0x14000196c  mov     r14, rbx
0x14000196f  jmp     loc_1400017C5
0x140001974  int     2Ch; Windows NT - assertion failure
0x140001976  jmp     loc_14000182A
0x14000197b  int     2Ch; Windows NT - assertion failure
0x14000197d  mov     r14, rbx
0x140001980  jmp     loc_1400017C5
0x140001985  int     2Ch; Windows NT - assertion failure
0x140001987  jmp     loc_14000182A
```
