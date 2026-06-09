# CmStringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)

- ea: `0x18000510c`
- end: `0x1800052e8`
- name: `?CmStringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ`
- size: `476`
- prototype: `__int64(char *Buffer, size_t cbDest, char **, unsigned __int64 *, unsigned int, const char *, ...)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800047e0`
- `0x180004aac`

## callees

- `0x180004d54`
- `0x18000510c`
- `0x1800052f0`
- `0x180005486`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x180005277`
- `msvcrt!_vsnprintf` at `0x180005277`

## pseudocode

```c
__int64 CmStringCchPrintfExA(
        char *Buffer,
        size_t cbDest,
        char **a3,
        unsigned __int64 *a4,
        DWORD dwFlags,
        char *cchOriginalDestLength,
        ...)
{
  bool v9; // cc
  int v10; // ebx
  const char *v11; // r8
  STRSAFE_LPSTR v12; // r15
  size_t v13; // rbp
  int *v14; // rax
  unsigned __int64 v16; // rsi
  int v17; // eax
  STRSAFE_LPSTR ppszDestEnd; // [rsp+30h] [rbp-58h] BYREF
  size_t pcchRemaining[10]; // [rsp+38h] [rbp-50h] BYREF
  va_list va; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va, cchOriginalDestLength);
  pcchRemaining[0] = 0;
  if ( (dwFlags & 0x100) != 0 )
  {
    if ( !Buffer && cbDest )
      goto LABEL_7;
    v9 = cbDest <= 0x7FFFFFFF;
  }
  else
  {
    v9 = cbDest - 1 <= 0x7FFFFFFE;
  }
  if ( v9 )
  {
    v11 = cchOriginalDestLength;
    v12 = Buffer;
    ppszDestEnd = Buffer;
    v13 = cbDest;
    pcchRemaining[0] = cbDest;
    if ( (dwFlags & 0x100) != 0 )
    {
      v14 = &dword_180009F8C;
      if ( cchOriginalDestLength )
        v14 = (int *)cchOriginalDestLength;
      v11 = (const char *)v14;
    }
    if ( (dwFlags & 0xFFFFE000) != 0 )
    {
      v10 = -2147024809;
      if ( cbDest )
        *Buffer = 0;
    }
    else if ( cbDest )
    {
      v16 = cbDest - 1;
      v17 = _vsnprintf(Buffer, cbDest - 1, v11, va);
      if ( v17 < 0 || v17 > v16 )
      {
        Buffer[v16] = 0;
        v10 = -2147024774;
      }
      else
      {
        v10 = 0;
        if ( v17 == v16 )
          Buffer[v16] = 0;
        else
          v16 = v17;
      }
      v13 = cbDest - v16;
      v12 = &Buffer[v16];
      ppszDestEnd = &Buffer[v16];
      pcchRemaining[0] = cbDest - v16;
      if ( v10 >= 0 )
      {
        if ( (dwFlags & 0x200) != 0 && v13 > 1 )
          memset_0(v12 + 1, (unsigned __int8)dwFlags, v13 - 1);
        goto LABEL_20;
      }
    }
    else
    {
      v10 = 0;
      if ( !*v11 )
        goto LABEL_20;
      v10 = Buffer != 0 ? -2147024774 : -2147024809;
    }
    if ( (dwFlags & 0x1C00) != 0 && cbDest )
    {
      StringExHandleOtherFlagsA(Buffer, cbDest, (size_t)v11, &ppszDestEnd, pcchRemaining, dwFlags);
      v12 = ppszDestEnd;
      v13 = pcchRemaining[0];
    }
    if ( v10 != -2147024774 )
      goto LABEL_24;
LABEL_20:
    if ( a3 )
      *a3 = v12;
    if ( a4 )
      *a4 = v13;
    goto LABEL_24;
  }
LABEL_7:
  v10 = -2147024809;
  if ( !cbDest )
  {
LABEL_25:
    MyDbgPrintfA(0xFFFFFFFF, "StringCchPrintfEx failed with error: 0x%x\n", v10);
    return (unsigned int)v10;
  }
  *Buffer = 0;
LABEL_24:
  if ( v10 < 0 )
    goto LABEL_25;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000510c  mov     rax, rsp
0x18000510f  mov     [rax+18h], r8
0x180005113  push    rbx
0x180005114  push    rbp
0x180005115  push    rsi
0x180005116  push    rdi
0x180005117  push    r12
0x180005119  push    r13
0x18000511b  push    r14
0x18000511d  push    r15
0x18000511f  sub     rsp, 48h
0x180005123  mov     r12d, [rsp+88h+arg_20]
0x18000512b  mov     r14, rcx
0x18000512e  mov     ecx, r12d
0x180005131  mov     qword ptr [rax-50h], 0
0x180005139  mov     r13, r9
0x18000513c  mov     rdi, rdx
0x18000513f  lea     r9, [rax+38h]; ArgList
0x180005143  and     ecx, 100h
0x180005149  jz      short loc_18000515E
0x18000514b  test    r14, r14
0x18000514e  jnz     short loc_180005155
0x180005150  test    rdx, rdx
0x180005153  jnz     short loc_18000516A
0x180005155  cmp     rdi, 7FFFFFFFh
0x18000515c  jmp     short loc_180005168
0x18000515e  lea     rax, [rdx-1]
0x180005162  cmp     rax, 7FFFFFFEh
0x180005168  jbe     short loc_180005181
0x18000516a  mov     ebx, 80070057h
0x18000516f  test    rdi, rdi
0x180005172  jz      loc_180005225
0x180005178  mov     byte ptr [r14], 0
0x18000517c  jmp     loc_180005221
0x180005181  mov     r8, [rsp+88h+cchOriginalDestLength]
0x180005189  mov     r15, r14
0x18000518c  mov     [rsp+88h+ppszDestEnd], r14
0x180005191  mov     rbp, rdi
0x180005194  mov     [rsp+88h+var_50], rdi
0x180005199  test    ecx, ecx
0x18000519b  jz      short loc_1800051AE
0x18000519d  test    r8, r8
0x1800051a0  lea     rax, dword_180009F8C
0x1800051a7  cmovnz  rax, r8
0x1800051ab  mov     r8, rax; Format
0x1800051ae  test    r12d, 0FFFFE000h
0x1800051b5  jz      loc_18000524A
0x1800051bb  mov     ebx, 80070057h
0x1800051c0  test    rdi, rdi
0x1800051c3  jz      short loc_1800051C9
0x1800051c5  mov     byte ptr [r14], 0
0x1800051c9  test    r12d, 1C00h
0x1800051d0  jz      short loc_180005200
0x1800051d2  test    rdi, rdi
0x1800051d5  jz      short loc_180005200
0x1800051d7  lea     rax, [rsp+88h+var_50]
0x1800051dc  mov     [rsp+88h+dwFlags], r12d; dwFlags
0x1800051e1  lea     r9, [rsp+88h+ppszDestEnd]; ppszDestEnd
0x1800051e6  mov     [rsp+88h+pcchRemaining], rax; pcchRemaining
0x1800051eb  mov     rdx, rdi; cbDest
0x1800051ee  mov     rcx, r14; pszDest
0x1800051f1  call    StringExHandleOtherFlagsA
0x1800051f6  mov     r15, [rsp+88h+ppszDestEnd]
0x1800051fb  mov     rbp, [rsp+88h+var_50]
0x180005200  cmp     ebx, 8007007Ah
0x180005206  jnz     short loc_180005221
0x180005208  mov     rax, [rsp+88h+arg_10]
0x180005210  test    rax, rax
0x180005213  jz      short loc_180005218
0x180005215  mov     [rax], r15
0x180005218  test    r13, r13
0x18000521b  jz      short loc_180005221
0x18000521d  mov     [r13+0], rbp
0x180005221  test    ebx, ebx
0x180005223  jns     short loc_180005237
0x180005225  mov     r8d, ebx
0x180005228  lea     rdx, aStringcchprint_0; "StringCchPrintfEx failed with error: 0x"...
0x18000522f  or      ecx, 0FFFFFFFFh
0x180005232  call    MyDbgPrintfA
0x180005237  mov     eax, ebx
0x180005239  add     rsp, 48h
0x18000523d  pop     r15
0x18000523f  pop     r14
0x180005241  pop     r13
0x180005243  pop     r12
0x180005245  pop     rdi
0x180005246  pop     rsi
0x180005247  pop     rbp
0x180005248  pop     rbx
0x180005249  retn
0x18000524a  test    rdi, rdi
0x18000524d  jnz     short loc_18000526D
0x18000524f  xor     ebx, ebx
0x180005251  cmp     [r8], bl
0x180005254  jz      short loc_180005208
0x180005256  mov     rax, r14
0x180005259  mov     ebx, 80070057h
0x18000525e  neg     rax
0x180005261  sbb     ecx, ecx
0x180005263  and     ecx, 23h
0x180005266  add     ebx, ecx
0x180005268  jmp     loc_1800051C9
0x18000526d  lea     rsi, [rdx-1]
0x180005271  mov     rcx, r14; Buffer
0x180005274  mov     rdx, rsi; BufferCount
0x180005277  call    cs:__imp__vsnprintf
0x18000527d  test    eax, eax
0x18000527f  js      short loc_18000529A
0x180005281  cdqe
0x180005283  cmp     rax, rsi
0x180005286  ja      short loc_18000529A
0x180005288  xor     ebx, ebx
0x18000528a  cmp     rax, rsi
0x18000528d  jnz     short loc_180005295
0x18000528f  mov     [rsi+r14], bl
0x180005293  jmp     short loc_1800052A4
0x180005295  mov     rsi, rax
0x180005298  jmp     short loc_1800052A4
0x18000529a  mov     byte ptr [rsi+r14], 0
0x18000529f  mov     ebx, 8007007Ah
0x1800052a4  sub     rbp, rsi
0x1800052a7  lea     r15, [rsi+r14]
0x1800052ab  mov     [rsp+88h+ppszDestEnd], r15
0x1800052b0  mov     [rsp+88h+var_50], rbp
0x1800052b5  test    ebx, ebx
0x1800052b7  js      loc_1800051C9
0x1800052bd  bt      r12d, 9
0x1800052c2  jnb     loc_180005208
0x1800052c8  cmp     rbp, 1
0x1800052cc  jbe     loc_180005208
0x1800052d2  lea     r8, [rbp-1]; Size
0x1800052d6  movzx   edx, r12b; Val
0x1800052da  lea     rcx, [r15+1]; void *
0x1800052de  call    memset_0
0x1800052e3  jmp     loc_180005208
```
