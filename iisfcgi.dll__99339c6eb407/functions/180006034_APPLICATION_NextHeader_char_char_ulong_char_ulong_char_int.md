# APPLICATION::NextHeader(char *,char * *,ulong *,char * *,ulong *,char * *,int *)

- ea: `0x180006034`
- end: `0x18000616f`
- name: `?NextHeader@APPLICATION@@SAJPEADPEAPEADPEAK121PEAH@Z`
- size: `315`
- prototype: `__int64 __fastcall(char *Str, char **, unsigned int *, char **, unsigned int *, char **, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004c24`
- `0x18000621c`
- `0x18000c390`

## callees

- `0x180006034`

## import_xrefs

- `msvcrt!strchr` at `0x18000608b`
- `msvcrt!strchr` at `0x1800060d3`
- `msvcrt!strchr` at `0x18000608b`
- `msvcrt!strchr` at `0x1800060d3`

## pseudocode

```c
__int64 __fastcall APPLICATION::NextHeader(
        char *Str,
        char **a2,
        unsigned int *a3,
        char **a4,
        unsigned int *a5,
        char **a6,
        int *a7)
{
  unsigned int v11; // edi
  char *v12; // rax
  char *v13; // rbx
  char *v14; // rax
  char *v15; // rcx
  char *i; // rax

  *a2 = 0;
  *a5 = 0;
  *a6 = 0;
  v11 = 0;
  *a3 = 0;
  *a4 = 0;
  if ( a7 )
    *a7 = 0;
  v12 = strchr(Str, 10);
  v13 = v12;
  if ( v12 )
  {
    if ( v12 > Str )
    {
      v14 = v12 - 1;
      if ( *v14 == 13 )
        v13 = v14;
    }
  }
  if ( !v13 || v13 == Str )
  {
    *a6 = v13;
    return v11;
  }
  *a6 = &v13[(*v13 == 13) + 1];
  v15 = strchr(Str, 58);
  if ( (unsigned __int64)(v13 - Str - 2) > 0xFFFD || !v15 || v15 == Str || v15 > v13 )
  {
    if ( a7 )
    {
      *a7 = 1;
      *a2 = Str;
      return v11;
    }
    return (unsigned int)-2147024883;
  }
  for ( i = v15 - 1; i >= Str && *i == 32; --i )
    ;
  if ( i < Str )
    return (unsigned int)-2147024883;
  do
    ++v15;
  while ( *v15 == 32 );
  if ( v15 > v13 )
    return (unsigned int)-2147024883;
  *a2 = Str;
  *a4 = v15;
  *a3 = (_DWORD)i - (_DWORD)Str + 1;
  *a5 = (_DWORD)v13 - (_DWORD)v15;
  return v11;
}

```

## disassembly

```asm
0x180006034  push    rbx
0x180006036  push    rbp
0x180006037  push    rsi
0x180006038  push    rdi
0x180006039  push    r12
0x18000603b  push    r13
0x18000603d  push    r14
0x18000603f  push    r15
0x180006041  sub     rsp, 28h
0x180006045  mov     rax, [rsp+68h+arg_20]
0x18000604d  mov     rsi, rcx
0x180006050  mov     r15, [rsp+68h+arg_28]
0x180006058  xor     ecx, ecx
0x18000605a  mov     r14, [rsp+68h+arg_30]
0x180006062  mov     r12, r9
0x180006065  mov     [rdx], rcx
0x180006068  mov     r13, r8
0x18000606b  mov     [rax], ecx
0x18000606d  mov     rbp, rdx
0x180006070  mov     [r15], rcx
0x180006073  mov     edi, ecx
0x180006075  mov     [r8], ecx
0x180006078  mov     [r9], rcx
0x18000607b  test    r14, r14
0x18000607e  jz      short loc_180006083
0x180006080  mov     [r14], ecx
0x180006083  mov     edx, 0Ah; Val
0x180006088  mov     rcx, rsi; Str
0x18000608b  call    cs:__imp_strchr
0x180006091  mov     rbx, rax
0x180006094  test    rax, rax
0x180006097  jz      short loc_1800060A8
0x180006099  cmp     rax, rsi
0x18000609c  jbe     short loc_1800060A8
0x18000609e  dec     rax
0x1800060a1  cmp     byte ptr [rax], 0Dh
0x1800060a4  cmovz   rbx, rax
0x1800060a8  test    rbx, rbx
0x1800060ab  jz      loc_180006159
0x1800060b1  cmp     rbx, rsi
0x1800060b4  jz      loc_180006159
0x1800060ba  xor     eax, eax
0x1800060bc  mov     edx, 3Ah ; ':'; Val
0x1800060c1  cmp     byte ptr [rbx], 0Dh
0x1800060c4  mov     rcx, rsi; Str
0x1800060c7  setz    al
0x1800060ca  inc     rax
0x1800060cd  add     rax, rbx
0x1800060d0  mov     [r15], rax
0x1800060d3  call    cs:__imp_strchr
0x1800060d9  mov     rcx, rax
0x1800060dc  mov     rax, rbx
0x1800060df  sub     rax, rsi
0x1800060e2  sub     rax, 2
0x1800060e6  cmp     rax, 0FFFDh
0x1800060ec  ja      short loc_180006140
0x1800060ee  test    rcx, rcx
0x1800060f1  jz      short loc_180006140
0x1800060f3  cmp     rcx, rsi
0x1800060f6  jz      short loc_180006140
0x1800060f8  cmp     rcx, rbx
0x1800060fb  ja      short loc_180006140
0x1800060fd  lea     rax, [rcx-1]
0x180006101  mov     dl, 20h ; ' '
0x180006103  jmp     short loc_18000610C
0x180006105  cmp     [rax], dl
0x180006107  jnz     short loc_180006111
0x180006109  dec     rax
0x18000610c  cmp     rax, rsi
0x18000610f  jnb     short loc_180006105
0x180006111  cmp     rax, rsi
0x180006114  jb      short loc_180006145
0x180006116  inc     rcx
0x180006119  cmp     [rcx], dl
0x18000611b  jz      short loc_180006116
0x18000611d  cmp     rcx, rbx
0x180006120  ja      short loc_180006145
0x180006122  sub     eax, esi
0x180006124  mov     [rbp+0], rsi
0x180006128  inc     eax
0x18000612a  mov     [r12], rcx
0x18000612e  mov     [r13+0], eax
0x180006132  sub     ebx, ecx
0x180006134  mov     rax, [rsp+68h+arg_20]
0x18000613c  mov     [rax], ebx
0x18000613e  jmp     short loc_18000615C
0x180006140  test    r14, r14
0x180006143  jnz     short loc_18000614C
0x180006145  mov     edi, 8007000Dh
0x18000614a  jmp     short loc_18000615C
0x18000614c  mov     dword ptr [r14], 1
0x180006153  mov     [rbp+0], rsi
0x180006157  jmp     short loc_18000615C
0x180006159  mov     [r15], rbx
0x18000615c  mov     eax, edi
0x18000615e  add     rsp, 28h
0x180006162  pop     r15
0x180006164  pop     r14
0x180006166  pop     r13
0x180006168  pop     r12
0x18000616a  pop     rdi
0x18000616b  pop     rsi
0x18000616c  pop     rbp
0x18000616d  pop     rbx
0x18000616e  retn
```
