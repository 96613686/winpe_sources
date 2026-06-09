# RefsParseNameForCreate

- ea: `0x1c017a764`
- end: `0x1c017a951`
- name: `RefsParseNameForCreate`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x1c0161594`

## callees

- `0x1c006acc0`
- `0x1c006af80`
- `0x1c0161c4c`
- `0x1c017a764`
- `0x1c017a958`
- `0x1c017a9f0`

## import_xrefs

- `ntoskrnl!FsRtlAreNamesEqual` at `0x1c018b19f`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1c018b1d4`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1c018b209`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1c018b23e`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1c018b273`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1c018b2a8`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1c018b19f`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1c018b1d4`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1c018b209`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1c018b23e`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1c018b273`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1c018b2a8`

## pseudocode

```c
char __fastcall RefsParseNameForCreate(
        __int64 a1,
        struct _UNICODE_STRING *a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        __int64 a6,
        _WORD *a7,
        _DWORD *a8)
{
  unsigned __int16 *v9; // r14
  __int64 v11; // rax
  _WORD *v12; // rbx
  char v13; // di
  __int64 v14; // rcx
  int Length; // edx
  int v16; // r13d
  int v17; // r12d
  int v18; // eax
  char v19; // dl
  __int16 v20; // cx
  unsigned __int16 v21; // cx
  int AttributeTypeCode; // eax
  __int16 v23; // r8
  __int16 v24; // cx
  __int16 v25; // dx
  char result; // al
  __int16 v27; // cx
  BOOL v28; // ecx
  const UNICODE_STRING *v29; // r14
  const UNICODE_STRING *v30; // rdi
  __int64 v31; // [rsp+38h] [rbp-61h]
  int v32[4]; // [rsp+40h] [rbp-59h] BYREF
  int v33[32]; // [rsp+58h] [rbp-41h] BYREF
  __int64 v35; // [rsp+F0h] [rbp+57h]

  v9 = a3;
  *(_OWORD *)v32 = 0;
  memset(v33, 0, 0x40u);
  v11 = *(_QWORD *)(a4 + 8);
  v12 = a7;
  v13 = 0;
  v31 = v11;
  v14 = *((_QWORD *)a5 + 1);
  *a7 = 0;
  v35 = v14;
  *a8 = 0;
  Length = a2->Length;
  v16 = *a5 - Length;
  v17 = *v9 - Length;
  if ( a2->Buffer[((unsigned __int64)a2->Length >> 1) - 1] == 58 )
    return 0;
  if ( (_WORD)Length )
  {
    while ( 1 )
    {
      v18 = RefsParsePath((int)a2, Length, (int)v32, (int)v33, a2);
      if ( v18 >= 2 )
      {
        if ( v18 <= 3 )
          return 0;
        if ( v18 == 4 )
        {
          if ( a2->Length || v13 )
            return 0;
          v27 = **((_WORD **)v9 + 1);
          if ( v27 == 92 )
          {
            v28 = *(_WORD *)(*((_QWORD *)v9 + 1) + 2LL) != 58;
          }
          else
          {
            if ( v27 != 58 )
              return 0;
            v28 = 0;
          }
          if ( v28 )
            return 0;
        }
        else if ( v18 == 5 )
        {
          return 0;
        }
      }
      v19 = v33[0];
      if ( v18 && (v33[0] & 1) != 0 )
      {
        v20 = v32[0];
        if ( LOWORD(v32[0]) > 2u || LOWORD(v32[0]) == 2 && **(_WORD **)&v32[2] != 92 )
          v20 = LOWORD(v32[0]) + 2;
        v21 = LOWORD(v33[2]) + v20;
        LOWORD(v32[0]) = v21;
      }
      else
      {
        v21 = v32[0];
      }
      v17 += v21;
      v16 += v21;
      if ( !a2->Length )
        break;
      v29 = (const UNICODE_STRING *)&v33[10];
      v30 = (const UNICODE_STRING *)&v33[6];
      if ( (v33[0] & 4) == 0 )
        v29 = &RefsEmptyString;
      if ( (v33[0] & 2) == 0 )
        v30 = &RefsEmptyString;
      if ( (v30->Length && !FsRtlAreNamesEqual(v30, &RefsIndexAllocation, 1u, *(PCWCH *)(*(_QWORD *)(a1 + 64) + 672LL))
         || v29->Length && !FsRtlAreNamesEqual(v29, &RefsFileNameIndex, 1u, *(PCWCH *)(*(_QWORD *)(a1 + 64) + 672LL)))
        && (v30->Length && !FsRtlAreNamesEqual(v30, &RefsBitmapString, 1u, *(PCWCH *)(*(_QWORD *)(a1 + 64) + 672LL))
         || v29->Length && !FsRtlAreNamesEqual(v29, &RefsFileNameIndex, 1u, *(PCWCH *)(*(_QWORD *)(a1 + 64) + 672LL)))
        && (!v30->Length
         || !FsRtlAreNamesEqual(v30, &RefsAttrListString, 1u, *(PCWCH *)(*(_QWORD *)(a1 + 64) + 672LL))
         && (!v30->Length
          || !FsRtlAreNamesEqual(v30, &RefsReparsePointString, 1u, *(PCWCH *)(*(_QWORD *)(a1 + 64) + 672LL)))) )
      {
        return 0;
      }
      v9 = a3;
      v13 = 1;
      *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * ((unsigned __int64)v17 >> 1)) = 92;
      if ( v31 != v35 )
        *(_WORD *)(*((_QWORD *)a5 + 1) + 2 * ((unsigned __int64)v16 >> 1)) = 92;
      v17 += 2;
      v16 += 2;
      memmove((void *)(*((_QWORD *)a3 + 1) + 2 * ((unsigned __int64)v17 >> 1)), a2->Buffer, a2->Length);
      if ( v31 != v35 )
        memmove((void *)(*((_QWORD *)a5 + 1) + 2 * ((unsigned __int64)v16 >> 1)), a2->Buffer, a2->Length);
      a2->Buffer = (PWSTR)(*((_QWORD *)a5 + 1) + 2 * ((unsigned __int64)v16 >> 1));
    }
    v12 = a7;
    if ( (v33[0] & 4) != 0 )
      *(_OWORD *)a7 = *(_OWORD *)&v33[10];
    if ( (v19 & 2) != 0 )
    {
      *(_DWORD *)(a6 + 152) |= 0x8000u;
      if ( (*(_DWORD *)(a6 + 152) & 0x20) != 0 )
        RefsUpcaseName(
          *(_QWORD *)(*(_QWORD *)(a1 + 64) + 672LL),
          *(unsigned int *)(*(_QWORD *)(a1 + 64) + 664LL),
          &v33[6]);
      AttributeTypeCode = RefsGetAttributeTypeCode(*(_QWORD *)(a1 + 64), &v33[6]);
      *a8 = AttributeTypeCode;
      if ( AttributeTypeCode )
      {
        v23 = v33[6];
        *(_WORD *)(a6 + 82) = v33[6];
        goto LABEL_17;
      }
      return 0;
    }
  }
  v23 = v33[6];
LABEL_17:
  *v9 = v17;
  *a5 = v16;
  v24 = *v9;
  *(_WORD *)a4 = *v9;
  if ( *v12 || (*(_DWORD *)(a6 + 152) & 0x8000) != 0 )
  {
    v25 = v24 + *v12 + 2;
    *(_WORD *)a4 = v25;
    if ( (*(_DWORD *)(a6 + 152) & 0x8000) != 0 )
      *(_WORD *)a4 = v23 + v25 + 2;
  }
  result = 1;
  *(_WORD *)(a6 + 80) = *v12;
  return result;
}

```

## disassembly

```asm
0x1c017a764  mov     rax, rsp
0x1c017a767  mov     [rax+20h], r9
0x1c017a76b  mov     [rax+18h], r8
0x1c017a76f  mov     [rax+8], rcx
0x1c017a773  push    rbp
0x1c017a774  push    rbx
0x1c017a775  push    rsi
0x1c017a776  push    rdi
0x1c017a777  push    r12
0x1c017a779  push    r13
0x1c017a77b  push    r14
0x1c017a77d  push    r15
0x1c017a77f  lea     rbp, [rax-47h]
0x1c017a783  sub     rsp, 98h
0x1c017a78a  mov     r15, rdx
0x1c017a78d  lea     rcx, [rbp+3Fh+var_80]; void *
0x1c017a791  xor     edx, edx; Val
0x1c017a793  mov     r14, r8
0x1c017a796  xorps   xmm0, xmm0
0x1c017a799  mov     rbx, r9
0x1c017a79c  movups  xmmword ptr [rbp+3Fh+var_98], xmm0
0x1c017a7a0  lea     r8d, [rdx+40h]; Size
0x1c017a7a4  call    memset
0x1c017a7a9  mov     rax, [rbx+8]
0x1c017a7ad  xor     r10d, r10d
0x1c017a7b0  mov     rbx, [rbp+3Fh+arg_30]
0x1c017a7b4  mov     dil, r10b
0x1c017a7b7  mov     [rbp+3Fh+var_A0], rax
0x1c017a7bb  mov     rax, [rbp+3Fh+arg_20]
0x1c017a7bf  mov     rcx, [rax+8]
0x1c017a7c3  mov     [rbx], r10w
0x1c017a7c7  mov     [rbp+3Fh+arg_8], rcx
0x1c017a7cb  mov     rcx, [rbp+3Fh+arg_38]
0x1c017a7d2  mov     [rcx], r10d
0x1c017a7d5  movzx   edx, word ptr [r15]; int
0x1c017a7d9  movzx   r13d, word ptr [rax]
0x1c017a7dd  mov     ecx, edx
0x1c017a7df  mov     rax, [r15+8]
0x1c017a7e3  sub     r13d, edx
0x1c017a7e6  movzx   r12d, word ptr [r14]
0x1c017a7ea  shr     rcx, 1
0x1c017a7ed  sub     r12d, edx
0x1c017a7f0  cmp     word ptr [rax+rcx*2-2], 3Ah ; ':'
0x1c017a7f6  jz      loc_1C017A94D
0x1c017a7fc  mov     rsi, [rbp+3Fh+arg_28]
0x1c017a800  test    dx, dx
0x1c017a803  jz      loc_1C018B35C
0x1c017a809  lea     r9, [rbp+3Fh+var_80]; int
0x1c017a80d  mov     [rsp+20h], r15; RemainingName
0x1c017a812  lea     r8, [rbp+3Fh+var_98]; int
0x1c017a816  mov     rcx, r15; int
0x1c017a819  mov     ebx, 5Ch ; '\'
0x1c017a81e  call    RefsParsePath
0x1c017a823  lea     r9d, [rbx-5Ah]
0x1c017a827  cmp     eax, r9d
0x1c017a82a  jge     loc_1C018B0DA
0x1c017a830  xor     r10d, r10d
0x1c017a833  mov     edx, [rbp+3Fh+var_80]
0x1c017a836  test    eax, eax
0x1c017a838  jz      loc_1C018B157
0x1c017a83e  test    dl, 1
0x1c017a841  jz      loc_1C018B157
0x1c017a847  movzx   ecx, word ptr [rbp+3Fh+var_98]
0x1c017a84b  cmp     cx, r9w
0x1c017a84f  jbe     loc_1C018B13F
0x1c017a855  add     cx, r9w
0x1c017a859  add     cx, [rbp+3Fh+var_78]
0x1c017a85d  mov     word ptr [rbp+3Fh+var_98], cx
0x1c017a861  movzx   eax, cx
0x1c017a864  add     r12d, eax
0x1c017a867  add     r13d, eax
0x1c017a86a  cmp     [r15], r10w
0x1c017a86e  jnz     loc_1C018B160
0x1c017a874  mov     rbx, [rbp+3Fh+arg_30]
0x1c017a878  test    dl, 4
0x1c017a87b  jz      short loc_1C017A885
0x1c017a87d  movups  xmm0, [rbp+3Fh+var_58]
0x1c017a881  movdqu  xmmword ptr [rbx], xmm0
0x1c017a885  test    r9b, dl
0x1c017a888  jz      loc_1C018B35C
0x1c017a88e  mov     edi, 8000h
0x1c017a893  or      [rsi+98h], edi
0x1c017a899  mov     eax, [rsi+98h]
0x1c017a89f  test    al, 20h
0x1c017a8a1  jz      short loc_1C017A8C1
0x1c017a8a3  mov     rax, [rbp+3Fh+arg_0]
0x1c017a8a7  lea     r8, [rbp+3Fh+var_68]
0x1c017a8ab  mov     rcx, [rax+40h]
0x1c017a8af  mov     edx, [rcx+298h]
0x1c017a8b5  mov     rcx, [rcx+2A0h]
0x1c017a8bc  call    RefsUpcaseName
0x1c017a8c1  mov     rax, [rbp+3Fh+arg_0]
0x1c017a8c5  lea     rdx, [rbp+3Fh+var_68]
0x1c017a8c9  mov     rcx, [rax+40h]
0x1c017a8cd  call    RefsGetAttributeTypeCode
0x1c017a8d2  mov     rcx, [rbp+3Fh+arg_38]
0x1c017a8d9  mov     [rcx], eax
0x1c017a8db  test    eax, eax
0x1c017a8dd  jz      short loc_1C017A94D
0x1c017a8df  movzx   r8d, [rbp+3Fh+var_68]
0x1c017a8e4  mov     [rsi+52h], r8w
0x1c017a8e9  mov     rax, [rbp+3Fh+arg_20]
0x1c017a8ed  mov     r9, [rbp+3Fh+arg_18]
0x1c017a8f1  mov     [r14], r12w
0x1c017a8f5  mov     [rax], r13w
0x1c017a8f9  movzx   ecx, word ptr [r14]
0x1c017a8fd  mov     [r9], cx
0x1c017a901  movzx   edx, word ptr [rbx]
0x1c017a904  test    dx, dx
0x1c017a907  jz      loc_1C018B36B
0x1c017a90d  add     dx, cx
0x1c017a910  mov     eax, 2
0x1c017a915  add     dx, ax
0x1c017a918  mov     [r9], dx
0x1c017a91c  test    [rsi+98h], edi
0x1c017a922  jz      short loc_1C017A92F
0x1c017a924  add     dx, r8w
0x1c017a928  add     dx, ax
0x1c017a92b  mov     [r9], dx
0x1c017a92f  movzx   ecx, word ptr [rbx]
0x1c017a932  mov     al, 1
0x1c017a934  mov     [rsi+50h], cx
0x1c017a938  add     rsp, 98h
0x1c017a93f  pop     r15
0x1c017a941  pop     r14
0x1c017a943  pop     r13
0x1c017a945  pop     r12
0x1c017a947  pop     rdi
0x1c017a948  pop     rsi
0x1c017a949  pop     rbx
0x1c017a94a  pop     rbp
0x1c017a94b  retn
0x1c017a94d  xor     al, al
0x1c017a94f  jmp     short loc_1C017A938
0x1c018b0da  cmp     eax, 3
0x1c018b0dd  jle     loc_1C017A94D
0x1c018b0e3  cmp     eax, 4
0x1c018b0e6  jz      short loc_1C018B0F6
0x1c018b0e8  cmp     eax, 5
0x1c018b0eb  jz      loc_1C017A94D
0x1c018b0f1  jmp     loc_1C017A830
0x1c018b0f6  xor     r10d, r10d
0x1c018b0f9  cmp     [r15], r10w
0x1c018b0fd  jnz     loc_1C017A94D
0x1c018b103  test    dil, dil
0x1c018b106  jnz     loc_1C017A94D
0x1c018b10c  mov     rdx, [r14+8]
0x1c018b110  movzx   ecx, word ptr [rdx]
0x1c018b113  cmp     cx, bx
0x1c018b116  jnz     short loc_1C018B125
0x1c018b118  cmp     word ptr [rdx+2], 3Ah ; ':'
0x1c018b11d  mov     ecx, r10d
0x1c018b120  setnz   cl
0x1c018b123  jmp     short loc_1C018B132
0x1c018b125  cmp     cx, 3Ah ; ':'
0x1c018b129  jnz     loc_1C017A94D
0x1c018b12f  mov     ecx, r10d
0x1c018b132  test    ecx, ecx
0x1c018b134  jnz     loc_1C017A94D
0x1c018b13a  jmp     loc_1C017A833
0x1c018b13f  jnz     loc_1C017A859
0x1c018b145  mov     rax, qword ptr [rbp+3Fh+var_98+8]
0x1c018b149  cmp     [rax], bx
0x1c018b14c  jz      loc_1C017A859
0x1c018b152  jmp     loc_1C017A855
0x1c018b157  movzx   ecx, word ptr [rbp+3Fh+var_98]
0x1c018b15b  jmp     loc_1C017A861
0x1c018b160  mov     rbx, [rbp+3Fh+arg_0]
0x1c018b164  lea     rax, RefsEmptyString
0x1c018b16b  test    dl, 4
0x1c018b16e  lea     r14, [rbp+3Fh+var_58]
0x1c018b172  lea     rdi, [rbp+3Fh+var_68]
0x1c018b176  cmovz   r14, rax
0x1c018b17a  test    r9b, dl
0x1c018b17d  cmovz   rdi, rax
0x1c018b181  cmp     [rdi], r10w
0x1c018b185  jz      short loc_1C018B1B2
0x1c018b187  mov     r9, [rbx+40h]
0x1c018b18b  lea     rdx, RefsIndexAllocation; ConstantNameB
0x1c018b192  mov     r8b, 1; IgnoreCase
0x1c018b195  mov     rcx, rdi; ConstantNameA
0x1c018b198  mov     r9, [r9+2A0h]; UpcaseTable
0x1c018b19f  call    cs:__imp_FsRtlAreNamesEqual
0x1c018b1a6  nop     dword ptr [rax+rax+00h]
0x1c018b1ab  xor     r10d, r10d
0x1c018b1ae  test    al, al
0x1c018b1b0  jz      short loc_1C018B1EB
0x1c018b1b2  cmp     [r14], r10w
0x1c018b1b6  jz      loc_1C018B2BC
0x1c018b1bc  mov     r9, [rbx+40h]
0x1c018b1c0  lea     rdx, RefsFileNameIndex; ConstantNameB
0x1c018b1c7  mov     r8b, 1; IgnoreCase
0x1c018b1ca  mov     rcx, r14; ConstantNameA
0x1c018b1cd  mov     r9, [r9+2A0h]; UpcaseTable
0x1c018b1d4  call    cs:__imp_FsRtlAreNamesEqual
0x1c018b1db  nop     dword ptr [rax+rax+00h]
0x1c018b1e0  xor     r10d, r10d
0x1c018b1e3  test    al, al
0x1c018b1e5  jnz     loc_1C018B2BC
0x1c018b1eb  cmp     [rdi], r10w
0x1c018b1ef  jz      short loc_1C018B21C
0x1c018b1f1  mov     r9, [rbx+40h]
0x1c018b1f5  lea     rdx, RefsBitmapString; ConstantNameB
0x1c018b1fc  mov     r8b, 1; IgnoreCase
0x1c018b1ff  mov     rcx, rdi; ConstantNameA
0x1c018b202  mov     r9, [r9+2A0h]; UpcaseTable
0x1c018b209  call    cs:__imp_FsRtlAreNamesEqual
0x1c018b210  nop     dword ptr [rax+rax+00h]
0x1c018b215  xor     r10d, r10d
0x1c018b218  test    al, al
0x1c018b21a  jz      short loc_1C018B251
0x1c018b21c  cmp     [r14], r10w
0x1c018b220  jz      loc_1C018B2BC
0x1c018b226  mov     r9, [rbx+40h]
0x1c018b22a  lea     rdx, RefsFileNameIndex; ConstantNameB
0x1c018b231  mov     r8b, 1; IgnoreCase
0x1c018b234  mov     rcx, r14; ConstantNameA
0x1c018b237  mov     r9, [r9+2A0h]; UpcaseTable
0x1c018b23e  call    cs:__imp_FsRtlAreNamesEqual
0x1c018b245  nop     dword ptr [rax+rax+00h]
0x1c018b24a  xor     r10d, r10d
0x1c018b24d  test    al, al
0x1c018b24f  jnz     short loc_1C018B2BC
0x1c018b251  cmp     [rdi], r10w
0x1c018b255  jz      loc_1C017A94D
0x1c018b25b  mov     r9, [rbx+40h]
0x1c018b25f  lea     rdx, RefsAttrListString; ConstantNameB
0x1c018b266  mov     r8b, 1; IgnoreCase
0x1c018b269  mov     rcx, rdi; ConstantNameA
0x1c018b26c  mov     r9, [r9+2A0h]; UpcaseTable
0x1c018b273  call    cs:__imp_FsRtlAreNamesEqual
0x1c018b27a  nop     dword ptr [rax+rax+00h]
0x1c018b27f  xor     r10d, r10d
0x1c018b282  test    al, al
0x1c018b284  jnz     short loc_1C018B2BC
0x1c018b286  cmp     [rdi], r10w
0x1c018b28a  jz      loc_1C017A94D
0x1c018b290  mov     r9, [rbx+40h]
0x1c018b294  lea     rdx, RefsReparsePointString; ConstantNameB
0x1c018b29b  mov     r8b, 1; IgnoreCase
0x1c018b29e  mov     rcx, rdi; ConstantNameA
0x1c018b2a1  mov     r9, [r9+2A0h]; UpcaseTable
0x1c018b2a8  call    cs:__imp_FsRtlAreNamesEqual
0x1c018b2af  nop     dword ptr [rax+rax+00h]
0x1c018b2b4  test    al, al
0x1c018b2b6  jz      loc_1C017A94D
0x1c018b2bc  mov     r14, [rbp+3Fh+arg_10]
0x1c018b2c0  mov     edx, 5Ch ; '\'
0x1c018b2c5  movsxd  rcx, r12d
0x1c018b2c8  mov     dil, 1
0x1c018b2cb  shr     rcx, 1
0x1c018b2ce  mov     rax, [r14+8]
0x1c018b2d2  mov     [rax+rcx*2], dx
0x1c018b2d6  mov     rax, [rbp+3Fh+arg_8]
0x1c018b2da  cmp     [rbp+3Fh+var_A0], rax
0x1c018b2de  jz      short loc_1C018B2F2
0x1c018b2e0  mov     rax, [rbp+3Fh+arg_20]
0x1c018b2e4  movsxd  rcx, r13d
0x1c018b2e7  shr     rcx, 1
0x1c018b2ea  mov     rax, [rax+8]
0x1c018b2ee  mov     [rax+rcx*2], dx
0x1c018b2f2  movzx   r8d, word ptr [r15]; Size
0x1c018b2f6  mov     eax, 2
0x1c018b2fb  mov     rdx, [r15+8]; Src
0x1c018b2ff  add     r12d, eax
0x1c018b302  add     r13d, eax
0x1c018b305  movsxd  rcx, r12d
0x1c018b308  mov     rax, [r14+8]
0x1c018b30c  shr     rcx, 1
0x1c018b30f  lea     rcx, [rax+rcx*2]; void *
0x1c018b313  call    memmove
0x1c018b318  mov     rax, [rbp+3Fh+arg_8]
0x1c018b31c  movsxd  rbx, r13d
0x1c018b31f  cmp     [rbp+3Fh+var_A0], rax
0x1c018b323  jz      short loc_1C018B344
0x1c018b325  mov     rax, [rbp+3Fh+arg_20]
0x1c018b329  mov     rcx, rbx
0x1c018b32c  movzx   r8d, word ptr [r15]; Size
0x1c018b330  mov     rdx, [r15+8]; Src
0x1c018b334  shr     rcx, 1
0x1c018b337  mov     rax, [rax+8]
0x1c018b33b  lea     rcx, [rax+rcx*2]; void *
0x1c018b33f  call    memmove
0x1c018b344  mov     rax, [rbp+3Fh+arg_20]
0x1c018b348  shr     rbx, 1
0x1c018b34b  mov     rax, [rax+8]
0x1c018b34f  lea     rcx, [rax+rbx*2]
0x1c018b353  mov     [r15+8], rcx
0x1c018b357  jmp     loc_1C017A809
0x1c018b35c  movzx   r8d, [rbp+3Fh+var_68]
0x1c018b361  mov     edi, 8000h
0x1c018b366  jmp     loc_1C017A8E9
0x1c018b36b  test    [rsi+98h], edi
0x1c018b371  jz      loc_1C017A92F
0x1c018b377  jmp     loc_1C017A90D
```
