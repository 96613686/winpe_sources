# xdrrec_create

- ea: `0x1800306c0`
- end: `0x1800307fc`
- name: `xdrrec_create`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002f180`

## callees

- `0x180002178`
- `0x1800306c0`

## import_xrefs

- `msvcrt!fprintf` at `0x18003070d`
- `msvcrt!fprintf` at `0x18003070d`
- `KERNEL32!GlobalAlloc` at `0x1800306e3`
- `KERNEL32!GlobalAlloc` at `0x180030750`
- `KERNEL32!GlobalAlloc` at `0x1800306e3`
- `KERNEL32!GlobalAlloc` at `0x180030750`
- `KERNEL32!GlobalFree` at `0x180030762`
- `KERNEL32!GlobalFree` at `0x180030762`

## string_xrefs

- `0x180030706`: `xdrrec_create: out of memory\n`

## pseudocode

```c
__int64 __fastcall xdrrec_create(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  FILE *v10; // rax
  __int64 result; // rax
  int v12; // edi
  int v13; // ebp
  __int64 v14; // rbp
  unsigned int v15; // edi
  char *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx

  v8 = GlobalAlloc(0x40u, 0x78u);
  *(_QWORD *)(a1 + 24) = 0;
  v9 = v8;
  if ( !v8 )
    goto LABEL_2;
  v12 = 4000;
  v13 = 4000;
  if ( a2 >= 0x64 )
    v13 = a2;
  v14 = (v13 + 3) & 0xFFFFFFFC;
  *((_DWORD *)v8 + 28) = v14;
  if ( a3 >= 0x64 )
    v12 = a3;
  v15 = (v12 + 3) & 0xFFFFFFFC;
  *((_DWORD *)v8 + 29) = v15;
  v16 = (char *)GlobalAlloc(0x40u, v15 + (_DWORD)v14 + 4);
  v9[1] = v16;
  if ( !v16 )
  {
    GlobalFree(v9);
LABEL_2:
    v10 = _acrt_iob_func(2u);
    fprintf(v10, "xdrrec_create: out of memory\n");
    return 0;
  }
  v9[3] = v16;
  if ( ((unsigned __int8)v16 & 3) != 0 )
  {
    do
      ++v16;
    while ( ((unsigned __int8)v16 & 3) != 0 );
    v9[3] = v16;
  }
  v9[10] = &v16[(unsigned int)v14];
  *(_QWORD *)(a1 + 8) = off_180054060;
  *(_QWORD *)(a1 + 24) = v9;
  v17 = v9[3];
  v18 = v9[10] + v15;
  v9[8] = &readtcp;
  v9[2] = &writetcp;
  *v9 = a4;
  v9[4] = v17 + 4;
  v9[5] = v17 + v14;
  result = 1;
  *((_DWORD *)v9 + 27) = 1;
  v9[6] = v17;
  *((_DWORD *)v9 + 14) = 0;
  *((_DWORD *)v9 + 18) = v15;
  v9[12] = v18;
  v9[11] = v18;
  *((_DWORD *)v9 + 26) = 0;
  return result;
}

```

## disassembly

```asm
0x1800306c0  push    rbx
0x1800306c2  push    rbp
0x1800306c3  push    rsi
0x1800306c4  push    rdi
0x1800306c5  push    r12
0x1800306c7  push    r14
0x1800306c9  push    r15
0x1800306cb  sub     rsp, 20h
0x1800306cf  mov     r15d, edx
0x1800306d2  mov     rsi, rcx
0x1800306d5  mov     edx, 78h ; 'x'; dwBytes
0x1800306da  mov     r12, r9
0x1800306dd  mov     r14d, r8d
0x1800306e0  lea     ecx, [rdx-38h]; uFlags
0x1800306e3  call    cs:__imp_GlobalAlloc
0x1800306e9  mov     qword ptr [rsi+18h], 0
0x1800306f1  mov     rbx, rax
0x1800306f4  test    rax, rax
0x1800306f7  jnz     short loc_18003071A
0x1800306f9  mov     ecx, 2; Ix
0x1800306fe  call    __acrt_iob_func
0x180030703  mov     rcx, rax; Stream
0x180030706  lea     rdx, aXdrrecCreateOu; "xdrrec_create: out of memory\n"
0x18003070d  call    cs:__imp_fprintf
0x180030713  xor     eax, eax
0x180030715  jmp     loc_1800307ED
0x18003071a  mov     eax, 0FFFFFFFCh
0x18003071f  mov     edi, 0FA0h
0x180030724  mov     ebp, edi
0x180030726  cmp     r15d, 64h ; 'd'
0x18003072a  mov     ecx, 40h ; '@'; uFlags
0x18003072f  cmovnb  ebp, r15d
0x180030733  add     ebp, 3
0x180030736  and     ebp, eax
0x180030738  cmp     r14d, 64h ; 'd'
0x18003073c  mov     [rbx+70h], ebp
0x18003073f  cmovnb  edi, r14d
0x180030743  lea     edx, [rbp+4]
0x180030746  add     edi, 3
0x180030749  and     edi, eax
0x18003074b  add     edx, edi; dwBytes
0x18003074d  mov     [rbx+74h], edi
0x180030750  call    cs:__imp_GlobalAlloc
0x180030756  mov     [rbx+8], rax
0x18003075a  test    rax, rax
0x18003075d  jnz     short loc_18003076A
0x18003075f  mov     rcx, rbx; hMem
0x180030762  call    cs:__imp_GlobalFree
0x180030768  jmp     short loc_1800306F9
0x18003076a  mov     [rbx+18h], rax
0x18003076e  test    al, 3
0x180030770  jz      short loc_18003077D
0x180030772  inc     rax
0x180030775  test    al, 3
0x180030777  jnz     short loc_180030772
0x180030779  mov     [rbx+18h], rax
0x18003077d  mov     edx, ebp
0x18003077f  add     rax, rdx
0x180030782  mov     edx, edi
0x180030784  mov     [rbx+50h], rax
0x180030788  lea     rax, off_180054060
0x18003078f  mov     [rsi+8], rax
0x180030793  lea     rax, readtcp
0x18003079a  mov     [rsi+18h], rbx
0x18003079e  mov     rcx, [rbx+18h]
0x1800307a2  add     rdx, [rbx+50h]
0x1800307a6  mov     [rbx+40h], rax
0x1800307aa  lea     rax, writetcp
0x1800307b1  mov     [rbx+10h], rax
0x1800307b5  lea     rax, [rcx+4]
0x1800307b9  mov     [rbx], r12
0x1800307bc  mov     [rbx+20h], rax
0x1800307c0  lea     rax, [rcx+rbp]
0x1800307c4  mov     [rbx+28h], rax
0x1800307c8  mov     eax, 1
0x1800307cd  mov     [rbx+6Ch], eax
0x1800307d0  mov     [rbx+30h], rcx
0x1800307d4  mov     dword ptr [rbx+38h], 0
0x1800307db  mov     [rbx+48h], edi
0x1800307de  mov     [rbx+60h], rdx
0x1800307e2  mov     [rbx+58h], rdx
0x1800307e6  mov     dword ptr [rbx+68h], 0
0x1800307ed  add     rsp, 20h
0x1800307f1  pop     r15
0x1800307f3  pop     r14
0x1800307f5  pop     r12
0x1800307f7  pop     rdi
0x1800307f8  pop     rsi
0x1800307f9  pop     rbp
0x1800307fa  pop     rbx
0x1800307fb  retn
```
