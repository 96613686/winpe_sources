# NfsUpCallpPasswdGroupPopulatePasswdGroupData

- ea: `0x140011244`
- end: `0x14001143a`
- name: `NfsUpCallpPasswdGroupPopulatePasswdGroupData`
- size: `502`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, char, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140010da4`

## callees

- `0x1400110fc`
- `0x140011244`

## import_xrefs

- `msvcrt!_wtoi` at `0x14001134a`
- `msvcrt!_wtoi` at `0x14001137d`
- `msvcrt!_wtoi` at `0x140011389`
- `msvcrt!_wtoi` at `0x14001134a`
- `msvcrt!_wtoi` at `0x14001137d`
- `msvcrt!_wtoi` at `0x140011389`
- `ntdll!RtlCopyUnicodeString` at `0x1400113ce`
- `ntdll!RtlCopyUnicodeString` at `0x1400113ce`

## pseudocode

```c
__int64 __fastcall NfsUpCallpPasswdGroupPopulatePasswdGroupData(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        char a4,
        const wchar_t *a5,
        unsigned int a6)
{
  __int64 v6; // rax
  _QWORD *v7; // r14
  const wchar_t *j; // rcx
  unsigned int v10; // r15d
  __int64 v11; // r12
  char v12; // si
  unsigned __int64 v13; // rax
  const wchar_t *i; // rdi
  const wchar_t *v15; // rbx
  const wchar_t *v16; // rbx
  const wchar_t *v17; // rbx
  int v18; // eax
  UNICODE_STRING SourceString; // [rsp+20h] [rbp-10h] BYREF
  char v22; // [rsp+88h] [rbp+58h]
  unsigned __int64 v23; // [rsp+90h] [rbp+60h]
  unsigned int v24; // [rsp+98h] [rbp+68h]

  v22 = a4;
  v6 = a6;
  v7 = a2;
  j = a5;
  v24 = 0;
  v10 = 0;
  v11 = a2[2];
  v12 = 0;
  v13 = (unsigned __int64)&a5[v6];
  v23 = v13;
  SourceString = 0;
  while ( (unsigned __int64)j < v13 && !v12 )
  {
    ++v10;
    *(_DWORD *)(v11 + 16) = -1;
    for ( i = j; (unsigned __int64)i < v13; ++i )
    {
      if ( *i == 10 )
        break;
    }
    v15 = j;
    if ( j >= i )
      goto LABEL_27;
    do
    {
      if ( *v15 == 58 )
        break;
      ++v15;
    }
    while ( v15 < i );
    if ( v15 >= i )
      goto LABEL_27;
    *(_DWORD *)((char *)&SourceString.Buffer + 2) = (unsigned __int64)j >> 16;
    HIWORD(SourceString.Buffer) = HIWORD(j);
    LOWORD(SourceString.Buffer) = (_WORD)j;
    SourceString.Length = (_WORD)v15 - (_WORD)j;
    SourceString.MaximumLength = (_WORD)v15 - (_WORD)j;
    do
      ++v15;
    while ( v15 < i && *v15 != 58 );
    v16 = v15 + 1;
    if ( v16 >= i )
      goto LABEL_27;
    j = v16;
    do
    {
      if ( *v16 == 58 )
        break;
      ++v16;
    }
    while ( v16 < i );
    if ( v16 >= i )
    {
LABEL_27:
      NfsUpCallpPasswdGroupLogPasswdGroupBadSyntax(j, a3, v10);
      v12 = 1;
      goto LABEL_28;
    }
    *v16 = 0;
    if ( a4 )
    {
      v17 = v16 + 1;
      *(_DWORD *)(v11 + 16) = _wtoi(j);
      for ( j = v17; j < i; ++j )
      {
        if ( *j == 58 )
          break;
      }
      if ( j >= i )
        goto LABEL_27;
      *j = 0;
      v18 = _wtoi(v17);
      v7 = a2;
    }
    else
    {
      v18 = _wtoi(j);
    }
    *(_DWORD *)(v11 + 20) = v18;
    if ( SourceString.Length )
    {
      *(_QWORD *)(*v7 + 8LL * v24) = v11;
      *(_QWORD *)(v7[1] + 8LL * v24) = v11;
      *(_WORD *)v11 = 0;
      *(_WORD *)(v11 + 2) = SourceString.Length;
      *(_QWORD *)(v11 + 8) = v11 + 24;
      RtlCopyUnicodeString((PUNICODE_STRING)v11, &SourceString);
      v11 += (SourceString.Length + 31) & 0xFFFFFFF8;
      ++v24;
    }
LABEL_28:
    v13 = v23;
    j = i + 1;
    v7 = a2;
    a4 = v22;
  }
  return v12 != 0 ? 0xD : 0;
}

```

## disassembly

```asm
0x140011244  mov     rax, rsp
0x140011247  mov     [rax+18h], rbx
0x14001124b  mov     [rax+20h], r9b
0x14001124f  mov     [rax+10h], rdx
0x140011253  mov     [rax+8], rcx
0x140011257  push    rbp
0x140011258  push    rsi
0x140011259  push    rdi
0x14001125a  push    r12
0x14001125c  push    r13
0x14001125e  push    r14
0x140011260  push    r15
0x140011262  mov     rbp, rsp
0x140011265  sub     rsp, 30h
0x140011269  mov     eax, [rbp+arg_28]
0x14001126c  mov     r14, rdx
0x14001126f  mov     rcx, [rbp+arg_20]
0x140011273  xor     edx, edx
0x140011275  xorps   xmm0, xmm0
0x140011278  mov     [rbp+arg_28], edx
0x14001127b  mov     r13, r8
0x14001127e  mov     r15d, edx
0x140011281  mov     r12, [r14+10h]
0x140011285  mov     sil, dl
0x140011288  lea     rax, [rcx+rax*2]
0x14001128c  mov     [rbp+arg_20], rax
0x140011290  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x140011294  jmp     loc_14001140D
0x140011299  test    sil, sil
0x14001129c  jnz     loc_14001141A
0x1400112a2  inc     r15d
0x1400112a5  mov     dword ptr [r12+10h], 0FFFFFFFFh
0x1400112ae  mov     rdi, rcx
0x1400112b1  cmp     rcx, rax
0x1400112b4  jnb     short loc_1400112C5
0x1400112b6  cmp     word ptr [rdi], 0Ah
0x1400112ba  jz      short loc_1400112C5
0x1400112bc  add     rdi, 2
0x1400112c0  cmp     rdi, rax
0x1400112c3  jb      short loc_1400112B6
0x1400112c5  mov     rbx, rcx
0x1400112c8  cmp     rcx, rdi
0x1400112cb  jnb     loc_1400113ED
0x1400112d1  cmp     word ptr [rbx], 3Ah ; ':'
0x1400112d5  jz      short loc_1400112E0
0x1400112d7  add     rbx, 2
0x1400112db  cmp     rbx, rdi
0x1400112de  jb      short loc_1400112D1
0x1400112e0  cmp     rbx, rdi
0x1400112e3  jnb     loc_1400113ED
0x1400112e9  mov     eax, [rbp+arg_2]
0x1400112ec  mov     dword ptr [rbp+SourceString.Buffer+2], eax
0x1400112ef  movzx   eax, [rbp+arg_6]
0x1400112f3  mov     word ptr [rbp+SourceString.Buffer+6], ax
0x1400112f7  movzx   eax, bx
0x1400112fa  sub     ax, cx
0x1400112fd  mov     word ptr [rbp+SourceString.Buffer], cx
0x140011301  mov     [rbp+SourceString.Length], ax
0x140011305  mov     [rbp+SourceString.MaximumLength], ax
0x140011309  jmp     short loc_140011311
0x14001130b  cmp     word ptr [rbx], 3Ah ; ':'
0x14001130f  jz      short loc_14001131A
0x140011311  add     rbx, 2
0x140011315  cmp     rbx, rdi
0x140011318  jb      short loc_14001130B
0x14001131a  add     rbx, 2
0x14001131e  cmp     rbx, rdi
0x140011321  jnb     loc_1400113ED
0x140011327  mov     rcx, rbx; String
0x14001132a  cmp     word ptr [rbx], 3Ah ; ':'
0x14001132e  jz      short loc_140011339
0x140011330  add     rbx, 2
0x140011334  cmp     rbx, rdi
0x140011337  jb      short loc_14001132A
0x140011339  cmp     rbx, rdi
0x14001133c  jnb     loc_1400113ED
0x140011342  mov     [rbx], dx
0x140011345  test    r9b, r9b
0x140011348  jz      short loc_140011389
0x14001134a  call    cs:__imp__wtoi
0x140011350  add     rbx, 2
0x140011354  mov     [r12+10h], eax
0x140011359  mov     rcx, rbx
0x14001135c  cmp     rbx, rdi
0x14001135f  jnb     short loc_140011370
0x140011361  cmp     word ptr [rcx], 3Ah ; ':'
0x140011365  jz      short loc_140011370
0x140011367  add     rcx, 2
0x14001136b  cmp     rcx, rdi
0x14001136e  jb      short loc_140011361
0x140011370  cmp     rcx, rdi
0x140011373  jnb     short loc_1400113ED
0x140011375  xor     eax, eax
0x140011377  mov     [rcx], ax
0x14001137a  mov     rcx, rbx; String
0x14001137d  call    cs:__imp__wtoi
0x140011383  mov     r14, [rbp+arg_8]
0x140011387  jmp     short loc_14001138F
0x140011389  call    cs:__imp__wtoi
0x14001138f  xor     edx, edx
0x140011391  mov     [r12+14h], eax
0x140011396  cmp     [rbp+SourceString.Length], dx
0x14001139a  jz      short loc_1400113FD
0x14001139c  mov     rax, [r14]
0x14001139f  mov     rcx, r12; DestinationString
0x1400113a2  mov     ebx, [rbp+arg_28]
0x1400113a5  mov     [rax+rbx*8], r12
0x1400113a9  mov     rax, [r14+8]
0x1400113ad  mov     [rax+rbx*8], r12
0x1400113b1  mov     [r12], dx
0x1400113b6  lea     rdx, [rbp+SourceString]; SourceString
0x1400113ba  movzx   eax, [rbp+SourceString.Length]
0x1400113be  mov     [r12+2], ax
0x1400113c4  lea     rax, [r12+18h]
0x1400113c9  mov     [r12+8], rax
0x1400113ce  call    cs:__imp_RtlCopyUnicodeString
0x1400113d4  movzx   eax, [rbp+SourceString.Length]
0x1400113d8  mov     ecx, 0FFFFFFF8h
0x1400113dd  add     eax, 1Fh
0x1400113e0  and     rax, rcx
0x1400113e3  add     r12, rax
0x1400113e6  inc     ebx
0x1400113e8  mov     [rbp+arg_28], ebx
0x1400113eb  jmp     short loc_1400113FB
0x1400113ed  mov     r8d, r15d
0x1400113f0  mov     rdx, r13
0x1400113f3  call    NfsUpCallpPasswdGroupLogPasswdGroupBadSyntax
0x1400113f8  mov     sil, 1
0x1400113fb  xor     edx, edx
0x1400113fd  mov     rax, [rbp+arg_20]
0x140011401  lea     rcx, [rdi+2]
0x140011405  mov     r14, [rbp+arg_8]
0x140011409  mov     r9b, [rbp+arg_18]
0x14001140d  mov     [rbp+40h], rcx
0x140011411  cmp     rcx, rax
0x140011414  jb      loc_140011299
0x14001141a  mov     rbx, [rsp+30h+arg_10]
0x140011422  neg     sil
0x140011425  sbb     eax, eax
0x140011427  and     eax, 0Dh
0x14001142a  add     rsp, 30h
0x14001142e  pop     r15
0x140011430  pop     r14
0x140011432  pop     r13
0x140011434  pop     r12
0x140011436  pop     rdi
0x140011437  pop     rsi
0x140011438  pop     rbp
0x140011439  retn
```
