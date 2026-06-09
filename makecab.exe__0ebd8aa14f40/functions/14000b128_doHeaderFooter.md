# doHeaderFooter

- ea: `0x14000b128`
- end: `0x14000b2d2`
- name: `doHeaderFooter`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000cb80`

## callees

- `0x140008620`
- `0x14000b128`
- `0x14000ce88`
- `0x14000d70c`
- `0x14000dfd8`
- `0x14000e450`

## import_xrefs

- `msvcrt!fprintf` at `0x14000b210`
- `msvcrt!fprintf` at `0x14000b210`

## string_xrefs

- `0x14000b21e`: `INF header variable template`
- `0x14000b2c2`: `Write of %1 failed on INF file: %2`

## pseudocode

```c
__int64 __fastcall doHeaderFooter(
        __int64 a1,
        FILE *a2,
        const char *a3,
        const char *a4,
        __int64 a5,
        const char *a6,
        const char *a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // edi
  const char *v17; // rsi
  __int64 v18; // rax
  char pszDest[32]; // [rsp+50h] [rbp-78h] BYREF

  v13 = VarFind(*(_QWORD *)(a1 + 16), a4, a9);
  if ( !v13 )
    return 1;
  v14 = *(_QWORD *)(v13 + 8);
  v15 = -1;
  do
    ++v15;
  while ( *(_BYTE *)(v14 + v15) );
  if ( !v15 )
    return 1;
  v16 = 1;
  if ( !v14 )
    return 1;
  v17 = (const char *)(*(_QWORD *)(a1 + 144) + 24LL);
  while ( 1 )
  {
    MsgSet(v17, 512, v14, "%s%s%s", a6, a7, "5.00");
    if ( fprintf(a2, "%s\r\n", v17) < 0 )
      break;
    if ( !(unsigned int)nameFromTemplate(pszDest, (__int64)"INF header variable template", a9) )
      return 0;
    v18 = VarFind(*(_QWORD *)(a1 + 16), pszDest, a9);
    if ( !v18 )
    {
      *(_DWORD *)(a9 + 512) = 0;
      *(_BYTE *)a9 = 0;
      *(_DWORD *)(a9 + 544) = 0;
      *(_QWORD *)(a9 + 552) = 0;
      return 1;
    }
    v14 = *(_QWORD *)(v18 + 8);
    ++v16;
    if ( !v14 )
      return 1;
  }
  ErrSet(a9, "Write of %1 failed on INF file: %2", "%s%s", a4, a3);
  return 0;
}

```

## disassembly

```asm
0x14000b128  push    rbx
0x14000b12a  push    rbp
0x14000b12b  push    rsi
0x14000b12c  push    rdi
0x14000b12d  push    r12
0x14000b12f  push    r13
0x14000b131  push    r14
0x14000b133  push    r15
0x14000b135  sub     rsp, 88h
0x14000b13c  mov     rax, cs:__security_cookie
0x14000b143  xor     rax, rsp
0x14000b146  mov     [rsp+0C8h+var_58], rax
0x14000b14b  mov     rax, [rsp+0C8h+arg_28]
0x14000b153  mov     r15, r8
0x14000b156  mov     rbx, [rsp+0C8h+arg_40]
0x14000b15e  mov     r13, rdx
0x14000b161  mov     r12, [rsp+0C8h+arg_20]
0x14000b169  mov     rbp, rcx
0x14000b16c  mov     rcx, [rcx+10h]
0x14000b170  mov     r8, rbx
0x14000b173  mov     [rsp+0C8h+var_80], rax
0x14000b178  mov     rdx, r9
0x14000b17b  mov     rax, [rsp+0C8h+arg_30]
0x14000b183  mov     r14, r9
0x14000b186  mov     [rsp+0C8h+var_88], rax
0x14000b18b  call    VarFind
0x14000b190  test    rax, rax
0x14000b193  jz      loc_14000B273
0x14000b199  mov     rax, [rax+8]
0x14000b19d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000b1a1  inc     rcx
0x14000b1a4  cmp     byte ptr [rax+rcx], 0
0x14000b1a8  jnz     short loc_14000B1A1
0x14000b1aa  test    rcx, rcx
0x14000b1ad  jz      loc_14000B273
0x14000b1b3  mov     rcx, [rbp+90h]
0x14000b1ba  mov     edi, 1
0x14000b1bf  test    rax, rax
0x14000b1c2  jz      loc_14000B273
0x14000b1c8  lea     rsi, [rcx+18h]
0x14000b1cc  lea     rcx, a500; "5.00"
0x14000b1d3  mov     r8, rax
0x14000b1d6  mov     [rsp+0C8h+var_98], rcx
0x14000b1db  lea     r9, aSSS; "%s%s%s"
0x14000b1e2  mov     rcx, [rsp+0C8h+var_88]
0x14000b1e7  mov     edx, 200h
0x14000b1ec  mov     [rsp+0C8h+var_A0], rcx
0x14000b1f1  mov     rcx, [rsp+0C8h+var_80]
0x14000b1f6  mov     [rsp+0C8h+var_A8], rcx
0x14000b1fb  mov     rcx, rsi
0x14000b1fe  call    MsgSet
0x14000b203  mov     r8, rsi
0x14000b206  lea     rdx, aS_1; "%s\r\n"
0x14000b20d  mov     rcx, r13; Stream
0x14000b210  call    cs:__imp_fprintf
0x14000b216  test    eax, eax
0x14000b218  js      loc_14000B2B0
0x14000b21e  lea     rax, aInfHeaderVaria; "INF header variable template"
0x14000b225  mov     [rsp+0C8h+var_A0], rbx; __int64
0x14000b22a  mov     r9d, edi
0x14000b22d  mov     [rsp+0C8h+var_A8], rax; __int64
0x14000b232  mov     r8, r12
0x14000b235  lea     rcx, [rsp+0C8h+pszDest]; pszDest
0x14000b23a  mov     edx, 20h ; ' '
0x14000b23f  call    nameFromTemplate
0x14000b244  test    eax, eax
0x14000b246  jz      loc_14000B2CE
0x14000b24c  mov     rcx, [rbp+10h]
0x14000b250  lea     rdx, [rsp+0C8h+pszDest]
0x14000b255  mov     r8, rbx
0x14000b258  call    VarFind
0x14000b25d  xor     ecx, ecx
0x14000b25f  test    rax, rax
0x14000b262  jz      short loc_14000B299
0x14000b264  mov     rax, [rax+8]
0x14000b268  inc     edi
0x14000b26a  test    rax, rax
0x14000b26d  jnz     loc_14000B1CC
0x14000b273  mov     eax, 1
0x14000b278  mov     rcx, [rsp+0C8h+var_58]
0x14000b27d  xor     rcx, rsp; StackCookie
0x14000b280  call    __security_check_cookie
0x14000b285  add     rsp, 88h
0x14000b28c  pop     r15
0x14000b28e  pop     r14
0x14000b290  pop     r13
0x14000b292  pop     r12
0x14000b294  pop     rdi
0x14000b295  pop     rsi
0x14000b296  pop     rbp
0x14000b297  pop     rbx
0x14000b298  retn
0x14000b299  mov     [rbx+200h], ecx
0x14000b29f  mov     [rbx], cl
0x14000b2a1  mov     [rbx+220h], ecx
0x14000b2a7  mov     [rbx+228h], rcx
0x14000b2ae  jmp     short loc_14000B273
0x14000b2b0  mov     r9, r14
0x14000b2b3  mov     [rsp+0C8h+var_A8], r15
0x14000b2b8  lea     r8, aSS_1; "%s%s"
0x14000b2bf  mov     rcx, rbx
0x14000b2c2  lea     rdx, aWriteOf1Failed; "Write of %1 failed on INF file: %2"
0x14000b2c9  call    ErrSet
0x14000b2ce  xor     eax, eax
0x14000b2d0  jmp     short loc_14000B278
```
