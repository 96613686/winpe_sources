# _CryptGetAppContainerUserPath

- ea: `0x18000b02c`
- end: `0x18000b190`
- name: `_CryptGetAppContainerUserPath`
- size: `356`
- prototype: `_WORD *__fastcall(_WORD *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006db0`

## callees

- `0x1800042e0`
- `0x18000b02c`
- `0x18000e2f0`
- `0x1800174fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b179`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b179`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000b069`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000b069`

## pseudocode

```c
_WORD *__fastcall CryptGetAppContainerUserPath(_WORD *Src)
{
  _WORD *v2; // rbx
  int BasicProfileFolderPath; // eax
  __int64 v4; // rdx
  _WORD *v5; // rax
  DWORD v6; // ecx
  __int64 v7; // rdi
  _WORD *v8; // rsi
  _WORD *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r14
  _WORD *v12; // rax
  _BYTE Srca[784]; // [rsp+20h] [rbp-358h] BYREF

  v2 = 0;
  BasicProfileFolderPath = GetBasicProfileFolderPath(6, 0, Srca, 388);
  if ( BasicProfileFolderPath < 0 )
  {
    v6 = BasicProfileFolderPath;
LABEL_19:
    SetLastError(v6);
    return v2;
  }
  v4 = 388;
  v5 = Srca;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  v6 = v4 == 0 ? 0x80070057 : 0;
  v7 = (388 - v4) & -(__int64)(v4 != 0);
  if ( !v4 )
    goto LABEL_19;
  v8 = 0;
  if ( Src )
    v8 = Src;
  if ( !v8 )
  {
    v6 = -2147024809;
    goto LABEL_19;
  }
  v9 = v8;
  v10 = 260;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v10;
  }
  while ( v10 );
  v6 = v10 == 0 ? 0x80070057 : 0;
  v11 = (260 - v10) & -(__int64)(v10 != 0);
  if ( !v10 )
    goto LABEL_19;
  v12 = (_WORD *)PkiNonzeroAlloc(2 * (v11 + v7) + 4);
  v2 = v12;
  if ( v12 )
  {
    memcpy_0(v12, Srca, 2 * v7);
    if ( *v8 != 92 )
      v2[v7++] = 92;
    memcpy_0(&v2[v7], v8, 2 * v11 + 2);
  }
  return v2;
}

```

## disassembly

```asm
0x18000b02c  push    rbx
0x18000b02e  push    rbp
0x18000b02f  push    rsi
0x18000b030  push    rdi
0x18000b031  push    r14
0x18000b033  push    r15
0x18000b035  sub     rsp, 348h
0x18000b03c  mov     rax, cs:__security_cookie
0x18000b043  xor     rax, rsp
0x18000b046  mov     [rsp+378h+var_48], rax
0x18000b04e  xor     edx, edx
0x18000b050  lea     r8, [rsp+378h+Src]
0x18000b055  mov     rbp, rcx
0x18000b058  xor     r15d, r15d
0x18000b05b  mov     esi, 184h
0x18000b060  mov     ebx, r15d
0x18000b063  mov     r9d, esi
0x18000b066  lea     ecx, [rdx+6]
0x18000b069  call    cs:__imp_GetBasicProfileFolderPath
0x18000b06f  test    eax, eax
0x18000b071  js      loc_18000B177
0x18000b077  mov     edx, esi
0x18000b079  lea     rax, [rsp+378h+Src]
0x18000b07e  cmp     [rax], r15w
0x18000b082  jz      short loc_18000B08E
0x18000b084  add     rax, 2
0x18000b088  sub     rdx, 1
0x18000b08c  jnz     short loc_18000B07E
0x18000b08e  mov     rax, rdx
0x18000b091  mov     r9d, 80070057h
0x18000b097  neg     rax
0x18000b09a  mov     rax, rdx
0x18000b09d  sbb     ecx, ecx
0x18000b09f  sub     rsi, rdx
0x18000b0a2  not     ecx
0x18000b0a4  and     ecx, r9d
0x18000b0a7  neg     rax
0x18000b0aa  sbb     rdi, rdi
0x18000b0ad  and     rdi, rsi
0x18000b0b0  test    rdx, rdx
0x18000b0b3  jz      loc_18000B179
0x18000b0b9  test    rbp, rbp
0x18000b0bc  mov     rsi, r15
0x18000b0bf  cmovnz  rsi, rbp
0x18000b0c3  test    rsi, rsi
0x18000b0c6  jz      loc_18000B18B
0x18000b0cc  mov     r8d, 104h
0x18000b0d2  mov     rax, rsi
0x18000b0d5  mov     edx, r8d
0x18000b0d8  cmp     [rax], r15w
0x18000b0dc  jz      short loc_18000B0E8
0x18000b0de  add     rax, 2
0x18000b0e2  sub     rdx, 1
0x18000b0e6  jnz     short loc_18000B0D8
0x18000b0e8  mov     rax, rdx
0x18000b0eb  neg     rax
0x18000b0ee  mov     rax, rdx
0x18000b0f1  sbb     ecx, ecx
0x18000b0f3  sub     r8, rdx
0x18000b0f6  not     ecx
0x18000b0f8  and     ecx, r9d
0x18000b0fb  neg     rax
0x18000b0fe  sbb     r14, r14
0x18000b101  and     r14, r8
0x18000b104  test    rdx, rdx
0x18000b107  jz      short loc_18000B179
0x18000b109  lea     rcx, [r14+rdi]
0x18000b10d  lea     rcx, ds:4[rcx*2]; uBytes
0x18000b115  call    PkiNonzeroAlloc
0x18000b11a  mov     rbx, rax
0x18000b11d  test    rax, rax
0x18000b120  jz      short loc_18000B154
0x18000b122  lea     r15, [rdi+rdi]
0x18000b126  mov     rcx, rax; void *
0x18000b129  mov     r8, r15; Size
0x18000b12c  lea     rdx, [rsp+378h+Src]; Src
0x18000b131  call    memcpy_0
0x18000b136  mov     eax, 5Ch ; '\'
0x18000b13b  cmp     ax, [rsi]
0x18000b13e  jnz     short loc_18000B181
0x18000b140  lea     r8, ds:2[r14*2]; Size
0x18000b148  mov     rdx, rsi; Src
0x18000b14b  lea     rcx, [rbx+rdi*2]; void *
0x18000b14f  call    memcpy_0
0x18000b154  mov     rax, rbx
0x18000b157  mov     rcx, [rsp+378h+var_48]
0x18000b15f  xor     rcx, rsp; StackCookie
0x18000b162  call    __security_check_cookie
0x18000b167  add     rsp, 348h
0x18000b16e  pop     r15
0x18000b170  pop     r14
0x18000b172  pop     rdi
0x18000b173  pop     rsi
0x18000b174  pop     rbp
0x18000b175  pop     rbx
0x18000b176  retn
0x18000b177  mov     ecx, eax; dwErrCode
0x18000b179  call    cs:__imp_SetLastError
0x18000b17f  jmp     short loc_18000B154
0x18000b181  mov     [r15+rbx], ax
0x18000b186  inc     rdi
0x18000b189  jmp     short loc_18000B140
0x18000b18b  mov     ecx, r9d
0x18000b18e  jmp     short loc_18000B179
```
