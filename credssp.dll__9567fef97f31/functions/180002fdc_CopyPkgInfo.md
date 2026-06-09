# CopyPkgInfo

- ea: `0x180002fdc`
- end: `0x1800030c6`
- name: `CopyPkgInfo`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002470`
- `0x180002f30`

## callees

- `0x180002fdc`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180003070`
- `msvcrt!wcscpy_s` at `0x1800030a7`
- `msvcrt!wcscpy_s` at `0x180003070`
- `msvcrt!wcscpy_s` at `0x1800030a7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003035`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003035`

## pseudocode

```c
__int64 __fastcall CopyPkgInfo(_QWORD *a1)
{
  wchar_t *v1; // rdx
  __int64 v2; // rbx
  __int64 v3; // rax
  int v5; // edx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // esi
  char *v9; // rax
  char *v10; // rdi
  char *v11; // rbp
  __int128 v12; // xmm0
  const wchar_t *v13; // r8
  const wchar_t *v14; // r8
  wchar_t *v15; // rcx
  __int64 result; // rax

  v1 = Source;
  v2 = -1;
  *a1 = 0;
  v3 = -1;
  do
    ++v3;
  while ( v1[v3] );
  v5 = (unsigned __int16)v3;
  v6 = -1;
  do
    ++v6;
  while ( off_180007018[v6] );
  v7 = v5 + (unsigned __int16)v6;
  v8 = 2 * v7 + 4;
  v9 = (char *)LocalAlloc(0x40u, (unsigned int)(2 * v7 + 36));
  v10 = v9;
  if ( !v9 )
    return 2148074240LL;
  v11 = v9 + 32;
  v12 = *(_OWORD *)CREDSSPInfoW;
  v13 = Source;
  *((_QWORD *)v9 + 3) = off_180007018;
  *(_OWORD *)v9 = v12;
  *((_QWORD *)v9 + 2) = v9 + 32;
  wcscpy_s((wchar_t *)v9 + 16, (unsigned __int64)v8 >> 1, v13);
  do
    ++v2;
  while ( Source[v2] );
  v14 = off_180007018;
  v15 = (wchar_t *)&v11[2 * v2 + 2];
  *((_QWORD *)v10 + 3) = v15;
  wcscpy_s(v15, (unsigned __int64)(v8 - 2 * (unsigned __int16)v2 - 2) >> 1, v14);
  result = 0;
  *a1 = v10;
  return result;
}

```

## disassembly

```asm
0x180002fdc  push    rbx
0x180002fde  push    rbp
0x180002fdf  push    rsi
0x180002fe0  push    rdi
0x180002fe1  push    r14
0x180002fe3  push    r15
0x180002fe5  sub     rsp, 28h
0x180002fe9  mov     rdx, cs:Source
0x180002ff0  xor     r15d, r15d
0x180002ff3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002ff7  mov     [rcx], r15
0x180002ffa  mov     rax, rbx
0x180002ffd  mov     r14, rcx
0x180003000  inc     rax
0x180003003  cmp     [rdx+rax*2], r15w
0x180003008  jnz     short loc_180003000
0x18000300a  mov     rcx, cs:off_180007018; "Microsoft CredSSP Security Provider"
0x180003011  movzx   edx, ax
0x180003014  mov     rax, rbx
0x180003017  inc     rax
0x18000301a  cmp     [rcx+rax*2], r15w
0x18000301f  jnz     short loc_180003017
0x180003021  movzx   eax, ax
0x180003024  mov     ecx, 40h ; '@'; uFlags
0x180003029  add     eax, edx
0x18000302b  lea     esi, ds:4[rax*2]
0x180003032  lea     edx, [rsi+20h]; uBytes
0x180003035  call    cs:__imp_LocalAlloc
0x18000303b  mov     rdi, rax
0x18000303e  test    rax, rax
0x180003041  jz      short loc_1800030B4
0x180003043  mov     rcx, cs:off_180007018; "Microsoft CredSSP Security Provider"
0x18000304a  lea     rbp, [rax+20h]
0x18000304e  movups  xmm0, xmmword ptr cs:CREDSSPInfoW
0x180003055  mov     r8, cs:Source; Source
0x18000305c  mov     [rax+18h], rcx
0x180003060  mov     rcx, rbp; Destination
0x180003063  mov     edx, esi
0x180003065  shr     rdx, 1; SizeInWords
0x180003068  movdqu  xmmword ptr [rax], xmm0
0x18000306c  mov     [rax+10h], rbp
0x180003070  call    cs:__imp_wcscpy_s
0x180003076  mov     rax, cs:Source
0x18000307d  inc     rbx
0x180003080  cmp     [rax+rbx*2], r15w
0x180003085  jnz     short loc_18000307D
0x180003087  mov     r8, cs:off_180007018; Source
0x18000308e  lea     rcx, [rbp+2]
0x180003092  movzx   eax, bx
0x180003095  lea     rcx, [rcx+rbx*2]; Destination
0x180003099  add     eax, eax
0x18000309b  mov     [rdi+18h], rcx
0x18000309f  sub     esi, eax
0x1800030a1  lea     edx, [rsi-2]
0x1800030a4  shr     rdx, 1; SizeInWords
0x1800030a7  call    cs:__imp_wcscpy_s
0x1800030ad  xor     eax, eax
0x1800030af  mov     [r14], rdi
0x1800030b2  jmp     short loc_1800030B9
0x1800030b4  mov     eax, 80090300h
0x1800030b9  add     rsp, 28h
0x1800030bd  pop     r15
0x1800030bf  pop     r14
0x1800030c1  pop     rdi
0x1800030c2  pop     rsi
0x1800030c3  pop     rbp
0x1800030c4  pop     rbx
0x1800030c5  retn
```
