# MupiGetPathComponents

- ea: `0x1400013e0`
- end: `0x14000173b`
- name: `MupiGetPathComponents`
- size: `859`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001360`
- `0x140015930`
- `0x140017f00`
- `0x140018520`
- `0x14001a8d0`

## callees

- `0x1400013e0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400016ce`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400016f6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001714`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000172a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400016ce`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400016f6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001714`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000172a`

## pseudocode

```c
void __fastcall MupiGetPathComponents(
        __int64 a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        PUNICODE_STRING a5)
{
  __int64 v5; // r10
  struct _UNICODE_STRING *v6; // rbx
  BOOL v8; // r12d
  struct _UNICODE_STRING *v9; // r15
  BOOL v10; // ebp
  BOOL v11; // r14d
  BOOL v12; // esi
  unsigned __int16 v13; // r15
  unsigned __int16 v14; // r8
  unsigned __int16 v15; // ax
  __int16 v16; // cx
  struct _UNICODE_STRING *v17; // rdi
  struct _UNICODE_STRING *v18; // r9
  __int16 v19; // bx
  unsigned __int16 v20; // r11
  unsigned __int16 v21; // r9
  __int16 v22; // dx
  unsigned __int16 v23; // di
  __int16 v24; // r9
  USHORT v25; // r9
  unsigned __int16 v26; // di
  unsigned __int16 v27; // r9
  __int64 v28; // r10
  unsigned __int16 v29; // dx
  __int16 v30; // r8
  __int16 v31; // cx
  USHORT v32; // r8
  unsigned __int16 v33; // r8
  __int64 v34; // rax
  USHORT v35; // r8
  WCHAR *Buffer; // rax
  bool v37; // zf
  USHORT Length; // cx
  __int16 v39; // [rsp+70h] [rbp+8h]

  v5 = *(_QWORD *)(a1 + 8);
  v6 = a2;
  v8 = a2 != 0;
  v9 = a4;
  v10 = a3 != 0;
  v11 = a4 != 0;
  v12 = a5 != 0;
  if ( !v5 || !*(_WORD *)a1 )
    goto LABEL_7;
  v13 = 0;
  v14 = *(_WORD *)a1 >> 1;
  v39 = 0;
  if ( v14 )
  {
    do
    {
      if ( *(_WORD *)(v5 + 2LL * v13) != 92 )
        break;
      if ( v13 >= 2u )
        break;
      v39 = ++v13;
    }
    while ( v13 < v14 );
  }
  v15 = v13;
  v16 = v13;
  if ( v13 >= v14 )
    goto LABEL_6;
  do
  {
    v19 = v16;
    v20 = v15;
    v21 = v15;
    v22 = *(_WORD *)(v5 + 2LL * v15);
    if ( v22 == 92 )
      break;
    v16 = ++v15;
  }
  while ( v15 < v14 );
  v23 = v20 + 1;
  if ( v22 == 92 )
    v23 = v20;
  v24 = v21 + 1;
  if ( v22 == 92 )
    v24 = v19;
  v6 = a2;
  if ( v23 == v13 )
    goto LABEL_6;
  if ( a2 )
  {
    v8 = 0;
    v25 = 2 * (v24 - v39);
    a2->Length = v25;
    a2->MaximumLength = v25;
    a2->Buffer = (PWSTR)(v5 + 2LL * v13);
  }
  v26 = v23 + 1;
  v27 = *(_WORD *)a1 >> 1;
  if ( v26 >= v27 )
    goto LABEL_6;
  v28 = *(_QWORD *)(a1 + 8);
  v29 = v26;
  v30 = v26;
  do
  {
    v31 = *(_WORD *)(v28 + 2LL * v29);
    if ( v31 == 92 )
      break;
    if ( v31 == 58 )
      break;
    v30 = ++v29;
  }
  while ( v29 < v27 );
  if ( v29 <= v26 )
  {
LABEL_6:
    v9 = a4;
LABEL_7:
    v17 = a5;
    v18 = a3;
    goto LABEL_8;
  }
  v18 = a3;
  if ( a3 )
  {
    v10 = 0;
    v32 = 2 * (v30 - v26);
    a3->Length = v32;
    a3->MaximumLength = v32;
    a3->Buffer = (PWSTR)(v28 + 2LL * v26);
  }
  if ( a4 )
  {
    Buffer = a2->Buffer;
    v11 = 0;
    a4->Buffer = Buffer;
    v37 = v13 == 0;
    Length = a2->Length;
    v9 = a4;
    a4->Length = a2->Length;
    if ( !v37 )
    {
      Length += 2;
      a4->Buffer = Buffer - 1;
      a4->Length = Length;
    }
    if ( a3->Length )
    {
      a4->Length = Length + 2;
      Length += a3->Length + 2;
      a4->Length = Length;
    }
    a4->MaximumLength = Length;
  }
  else
  {
    v9 = 0;
  }
  v33 = *(_WORD *)a1 >> 1;
  if ( v29 < v33 && *(_WORD *)(*(_QWORD *)(a1 + 8) + 2LL * v29) == 92 )
    ++v29;
  v17 = a5;
  if ( a5 && v29 < v33 )
  {
    v34 = *(_QWORD *)(a1 + 8);
    v12 = 0;
    v35 = 2 * (v33 - v29);
    a5->Length = v35;
    a5->MaximumLength = v35;
    a5->Buffer = (PWSTR)(v34 + 2LL * v29);
  }
LABEL_8:
  if ( v8 )
  {
    RtlInitUnicodeString(v6, 0);
    v18 = a3;
  }
  if ( v10 )
    RtlInitUnicodeString(v18, 0);
  if ( v11 )
    RtlInitUnicodeString(v9, 0);
  if ( v12 )
    RtlInitUnicodeString(v17, 0);
}

```

## disassembly

```asm
0x1400013e0  mov     rax, rsp
0x1400013e3  mov     [rax+20h], r9
0x1400013e7  mov     [rax+18h], r8
0x1400013eb  mov     [rax+10h], rdx
0x1400013ef  push    rdi
0x1400013f0  sub     rsp, 60h
0x1400013f4  mov     r10, [rcx+8]
0x1400013f8  mov     [rax-10h], rbx
0x1400013fc  mov     rbx, rdx
0x1400013ff  mov     [rax-18h], rbp
0x140001403  mov     [rax-20h], rsi
0x140001407  mov     [rax-28h], r12
0x14000140b  xor     r12d, r12d
0x14000140e  test    rdx, rdx
0x140001411  mov     [rax-30h], r13
0x140001415  mov     [rax-38h], r14
0x140001419  mov     r13, rcx
0x14000141c  setnz   r12b
0x140001420  mov     [rax-40h], r15
0x140001424  xor     ebp, ebp
0x140001426  mov     r15, r9
0x140001429  test    r8, r8
0x14000142c  setnz   bpl
0x140001430  xor     r14d, r14d
0x140001433  test    r9, r9
0x140001436  setnz   r14b
0x14000143a  xor     esi, esi
0x14000143c  cmp     [rsp+68h+arg_20], rsi
0x140001444  setnz   sil
0x140001448  test    r10, r10
0x14000144b  jz      short loc_140001491
0x14000144d  movzx   r8d, word ptr [rcx]
0x140001451  test    r8w, r8w
0x140001455  jz      short loc_140001491
0x140001457  xor     r15d, r15d
0x14000145a  shr     r8w, 1
0x14000145e  xor     eax, eax
0x140001460  mov     [rsp+68h+arg_0], r15d
0x140001465  cmp     ax, r8w
0x140001469  jnb     short loc_140001477
0x14000146b  movzx   eax, r15w
0x14000146f  cmp     word ptr [r10+rax*2], 5Ch ; '\'
0x140001475  jz      short loc_1400014ED
0x140001477  movzx   eax, r15w
0x14000147b  movzx   ecx, r15w
0x14000147f  cmp     r15w, r8w
0x140001483  jb      loc_140001510
0x140001489  mov     r15, [rsp+68h+arg_18]
0x140001491  mov     rdi, [rsp+68h+arg_20]
0x140001499  mov     r9, [rsp+68h+DestinationString]
0x1400014a1  mov     r13, [rsp+68h+var_30]
0x1400014a6  test    r12d, r12d
0x1400014a9  mov     r12, [rsp+68h+var_28]
0x1400014ae  jnz     loc_1400016F1
0x1400014b4  mov     rbx, [rsp+68h+var_10]
0x1400014b9  test    ebp, ebp
0x1400014bb  mov     rbp, [rsp+68h+var_18]
0x1400014c0  jnz     loc_1400016C9
0x1400014c6  test    r14d, r14d
0x1400014c9  mov     r14, [rsp+68h+var_38]
0x1400014ce  jnz     loc_14000170F
0x1400014d4  mov     r15, [rsp+68h+var_40]
0x1400014d9  test    esi, esi
0x1400014db  mov     rsi, [rsp+68h+var_20]
0x1400014e0  jnz     loc_140001725
0x1400014e6  add     rsp, 60h
0x1400014ea  pop     rdi
0x1400014eb  retn
0x1400014ed  cmp     r15w, 2
0x1400014f2  jnb     short loc_140001477
0x1400014f4  inc     r15w
0x1400014f8  mov     word ptr [rsp+68h+arg_0], r15w
0x1400014fe  cmp     r15w, r8w
0x140001502  jnb     loc_140001477
0x140001508  jmp     loc_14000146B
0x140001510  movzx   ebx, cx
0x140001513  movzx   r11d, ax
0x140001517  movzx   ecx, ax
0x14000151a  movzx   r9d, ax
0x14000151e  movzx   edx, word ptr [r10+rcx*2]
0x140001523  cmp     dx, 5Ch ; '\'
0x140001527  jz      short loc_140001535
0x140001529  inc     ax
0x14000152c  movzx   ecx, ax
0x14000152f  cmp     ax, r8w
0x140001533  jb      short loc_140001510
0x140001535  cmp     dx, 5Ch ; '\'
0x140001539  lea     edi, [r11+1]
0x14000153d  cmovz   di, r11w
0x140001542  inc     r9w
0x140001546  cmp     dx, 5Ch ; '\'
0x14000154a  cmovz   r9w, bx
0x14000154f  mov     rbx, [rsp+68h+arg_8]
0x140001554  cmp     di, r15w
0x140001558  jz      loc_140001489
0x14000155e  test    rbx, rbx
0x140001561  jz      short loc_140001585
0x140001563  sub     r9w, word ptr [rsp+68h+arg_0]
0x140001569  xor     r12d, r12d
0x14000156c  add     r9w, r9w
0x140001570  movzx   eax, r15w
0x140001574  mov     [rbx], r9w
0x140001578  mov     [rbx+2], r9w
0x14000157d  lea     rcx, [r10+rax*2]
0x140001581  mov     [rbx+8], rcx
0x140001585  movzx   r9d, word ptr [r13+0]
0x14000158a  inc     di
0x14000158d  shr     r9w, 1
0x140001591  cmp     di, r9w
0x140001595  jnb     loc_140001489
0x14000159b  mov     r10, [r13+8]
0x14000159f  movzx   edx, di
0x1400015a2  movzx   r8d, di
0x1400015a6  nop     word ptr [rax+rax+00000000h]
0x1400015b0  movzx   eax, dx
0x1400015b3  movzx   ecx, word ptr [r10+rax*2]
0x1400015b8  cmp     cx, 5Ch ; '\'
0x1400015bc  jz      short loc_1400015D1
0x1400015be  cmp     cx, 3Ah ; ':'
0x1400015c2  jz      short loc_1400015D1
0x1400015c4  inc     dx
0x1400015c7  movzx   r8d, dx
0x1400015cb  cmp     dx, r9w
0x1400015cf  jb      short loc_1400015B0
0x1400015d1  cmp     dx, di
0x1400015d4  jbe     loc_140001489
0x1400015da  mov     r9, [rsp+68h+DestinationString]
0x1400015e2  test    r9, r9
0x1400015e5  jz      short loc_140001605
0x1400015e7  movzx   eax, di
0x1400015ea  xor     ebp, ebp
0x1400015ec  sub     r8w, di
0x1400015f0  add     r8w, r8w
0x1400015f4  mov     [r9], r8w
0x1400015f8  lea     rcx, [r10+rax*2]
0x1400015fc  mov     [r9+2], r8w
0x140001601  mov     [r9+8], rcx
0x140001605  mov     r8, [rsp+68h+arg_18]
0x14000160d  test    r8, r8
0x140001610  jnz     short loc_14000166C
0x140001612  mov     r15, r8
0x140001615  movzx   eax, word ptr [r13+0]
0x14000161a  shr     ax, 1
0x14000161d  movzx   r8d, ax
0x140001621  cmp     dx, ax
0x140001624  jb      loc_1400016AF
0x14000162a  mov     rdi, [rsp+68h+arg_20]
0x140001632  test    rdi, rdi
0x140001635  jz      loc_1400014A1
0x14000163b  cmp     dx, r8w
0x14000163f  jnb     loc_1400014A1
0x140001645  mov     rax, [r13+8]
0x140001649  xor     esi, esi
0x14000164b  movzx   ecx, dx
0x14000164e  sub     r8w, dx
0x140001652  add     r8w, r8w
0x140001656  mov     [rdi], r8w
0x14000165a  mov     [rdi+2], r8w
0x14000165f  lea     rcx, [rax+rcx*2]
0x140001663  mov     [rdi+8], rcx
0x140001667  jmp     loc_1400014A1
0x14000166c  mov     rax, [rbx+8]
0x140001670  xor     r14d, r14d
0x140001673  mov     [r8+8], rax
0x140001677  test    r15w, r15w
0x14000167b  movzx   ecx, word ptr [rbx]
0x14000167e  mov     r15, [rsp+68h+arg_18]
0x140001686  mov     [r8], cx
0x14000168a  jnz     short loc_1400016DF
0x14000168c  cmp     [r9], r14w
0x140001690  jbe     short loc_1400016A5
0x140001692  lea     eax, [rcx+2]
0x140001695  add     cx, 2
0x140001699  mov     [r15], ax
0x14000169d  add     cx, [r9]
0x1400016a1  mov     [r15], cx
0x1400016a5  mov     [r15+2], cx
0x1400016aa  jmp     loc_140001615
0x1400016af  mov     rax, [r13+8]
0x1400016b3  movzx   ecx, dx
0x1400016b6  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x1400016bb  jnz     loc_14000162A
0x1400016c1  inc     dx
0x1400016c4  jmp     loc_14000162A
0x1400016c9  xor     edx, edx; SourceString
0x1400016cb  mov     rcx, r9; DestinationString
0x1400016ce  call    cs:__imp_RtlInitUnicodeString
0x1400016d5  nop     dword ptr [rax+rax+00h]
0x1400016da  jmp     loc_1400014C6
0x1400016df  add     rax, 0FFFFFFFFFFFFFFFEh
0x1400016e3  add     cx, 2
0x1400016e7  mov     [r15+8], rax
0x1400016eb  mov     [r15], cx
0x1400016ef  jmp     short loc_14000168C
0x1400016f1  xor     edx, edx; SourceString
0x1400016f3  mov     rcx, rbx; DestinationString
0x1400016f6  call    cs:__imp_RtlInitUnicodeString
0x1400016fd  nop     dword ptr [rax+rax+00h]
0x140001702  mov     r9, [rsp+68h+DestinationString]
0x14000170a  jmp     loc_1400014B4
0x14000170f  xor     edx, edx; SourceString
0x140001711  mov     rcx, r15; DestinationString
0x140001714  call    cs:__imp_RtlInitUnicodeString
0x14000171b  nop     dword ptr [rax+rax+00h]
0x140001720  jmp     loc_1400014D4
0x140001725  xor     edx, edx; SourceString
0x140001727  mov     rcx, rdi; DestinationString
0x14000172a  call    cs:__imp_RtlInitUnicodeString
0x140001731  nop     dword ptr [rax+rax+00h]
0x140001736  jmp     loc_1400014E6
```
