# AslpFileQueryVersionString

- ea: `0x180012fa0`
- end: `0x18001320f`
- name: `AslpFileQueryVersionString`
- size: `623`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180012708`

## callees

- `0x18000e240`
- `0x180012fa0`
- `0x180013374`
- `0x180013594`
- `0x180013f04`
- `0x18001403c`
- `0x1800191f0`

## string_xrefs

- `0x1800131cb`: `RtlStringCchCopyW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileQueryVersionString(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int64 a5,
        unsigned __int16 *a6)
{
  __int64 v10; // rdi
  __int64 v11; // rcx
  wchar_t *v12; // r8
  unsigned __int16 *v13; // rax
  __int64 v14; // rdx
  unsigned __int16 *v15; // rcx
  signed int v16; // ebx
  int v17; // eax
  const char *v18; // r9
  __int64 v19; // r8
  unsigned __int64 v20; // rdi
  int v21; // eax
  __int64 v23; // [rsp+20h] [rbp-E0h]
  __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v28; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v29[128]; // [rsp+60h] [rbp-A0h] BYREF

  *a1 = 0;
  v28 = a6;
  *a2 = 0;
  v10 = 0;
  v29[0] = 0;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  while ( 1 )
  {
    v11 = 2147483646;
    v12 = off_18001BAC0[v10];
    v13 = v29;
    v14 = 128;
    do
    {
      if ( !v11 )
        break;
      if ( !*v12 )
        break;
      *v13++ = *v12++;
      --v11;
      --v14;
    }
    while ( v14 );
    v15 = v13 - 1;
    if ( v14 )
      v15 = v13;
    *v15 = 0;
    v16 = v14 == 0 ? 0x80000005 : 0;
    if ( !v14 )
      break;
    v16 = RtlStringCchCatW(v29, 0x80u, v28);
    if ( v16 < 0 )
    {
      v18 = "RtlStringCchCatW failed [%x]";
      v19 = 3110;
      goto LABEL_29;
    }
    v17 = AslpFileVerQueryBlock(a3, v29, &v25, &v24);
    v16 = v17;
    if ( v17 >= 0 )
    {
      if ( (int)AslpFileVerStringBlockGetValue(&v27, &v26, v25, v24) < 0 )
      {
LABEL_16:
        if ( !a4 )
          return 3221226021LL;
        v20 = 0;
        if ( !a5 )
          return 3221226021LL;
        while ( 1 )
        {
          LODWORD(v23) = a4[1];
          v16 = RtlStringCchPrintfW(v29, 128, L"\\StringFileInfo\\%04X%04X\\%s", *a4, v23, v28);
          if ( v16 < 0 )
          {
            v18 = "RtlStringCchPrintfW failed [%x]";
            v19 = 3158;
            goto LABEL_29;
          }
          v21 = AslpFileVerQueryBlock(a3, v29, &v25, &v24);
          v16 = v21;
          if ( v21 >= 0 )
            break;
          if ( v21 != -1073741275 )
          {
            v18 = "AslpFileVerQueryBlock failed [%x]";
            v19 = 3188;
            goto LABEL_29;
          }
          ++v20;
          a4 += 2;
          if ( v20 >= a5 )
            return 3221226021LL;
        }
        if ( (int)AslpFileVerStringBlockGetValue(&v27, &v26, v25, v24) < 0 )
          return 3221226021LL;
      }
      *a2 = v26;
      *a1 = v27;
      return 0;
    }
    if ( v17 != -1073741275 )
    {
      v18 = "AslpFileVerQueryBlock failed [%x]";
      v19 = 3140;
      goto LABEL_29;
    }
    if ( (unsigned __int64)++v10 >= 4 )
      goto LABEL_16;
  }
  v18 = "RtlStringCchCopyW failed [%x]";
  v19 = 3104;
LABEL_29:
  LODWORD(v23) = v16;
  AslLogCallPrintf(1, "AslpFileQueryVersionString", v19, v18, v23);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180012fa0  push    rbp
0x180012fa2  push    rbx
0x180012fa3  push    rsi
0x180012fa4  push    rdi
0x180012fa5  push    r12
0x180012fa7  push    r13
0x180012fa9  push    r14
0x180012fab  push    r15
0x180012fad  lea     rbp, [rsp-78h]
0x180012fb2  sub     rsp, 178h
0x180012fb9  mov     rax, cs:__security_cookie
0x180012fc0  xor     rax, rsp
0x180012fc3  mov     [rbp+0B0h+var_50], rax
0x180012fc7  xor     esi, esi
0x180012fc9  mov     r14, r9
0x180012fcc  mov     r9, [rbp+0B0h+arg_28]
0x180012fd3  mov     r13, r8
0x180012fd6  mov     [rcx], rsi
0x180012fd9  mov     r12, rdx
0x180012fdc  mov     [rsp+1B0h+var_160], r9
0x180012fe1  mov     r15, rcx
0x180012fe4  mov     [rdx], rsi
0x180012fe7  mov     edi, esi
0x180012fe9  mov     [rsp+1B0h+var_150], si
0x180012fee  mov     [rsp+1B0h+var_168], rsi
0x180012ff3  mov     [rsp+1B0h+var_170], rsi
0x180012ff8  mov     [rsp+1B0h+var_178], rsi
0x180012ffd  mov     [rsp+1B0h+var_180], rsi
0x180013002  lea     r8, off_18001BAC0; "\\StringFileInfo\\000004B0\\"
0x180013009  mov     ecx, 7FFFFFFEh
0x18001300e  mov     r8, [r8+rdi*8]
0x180013012  lea     rax, [rsp+1B0h+var_150]
0x180013017  mov     edx, 80h
0x18001301c  test    rcx, rcx
0x18001301f  jz      short loc_180013040
0x180013021  movzx   r9d, word ptr [r8]
0x180013025  test    r9w, r9w
0x180013029  jz      short loc_180013040
0x18001302b  mov     [rax], r9w
0x18001302f  add     r8, 2
0x180013033  add     rax, 2
0x180013037  dec     rcx
0x18001303a  sub     rdx, 1
0x18001303e  jnz     short loc_18001301C
0x180013040  test    rdx, rdx
0x180013043  lea     rcx, [rax-2]
0x180013047  cmovnz  rcx, rax
0x18001304b  mov     rax, rdx
0x18001304e  neg     rax
0x180013051  sbb     ebx, ebx
0x180013053  not     ebx
0x180013055  mov     [rcx], si
0x180013058  and     ebx, 80000005h
0x18001305e  test    rdx, rdx
0x180013061  jz      loc_1800131CB
0x180013067  mov     r8, [rsp+1B0h+var_160]; unsigned __int16 *
0x18001306c  lea     rcx, [rsp+1B0h+var_150]; unsigned __int16 *
0x180013071  mov     edx, 80h; unsigned __int64
0x180013076  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001307b  mov     ebx, eax
0x18001307d  test    eax, eax
0x18001307f  js      loc_1800131BC
0x180013085  lea     r9, [rsp+1B0h+var_180]
0x18001308a  mov     rcx, r13
0x18001308d  lea     r8, [rsp+1B0h+var_178]
0x180013092  lea     rdx, [rsp+1B0h+var_150]
0x180013097  call    AslpFileVerQueryBlock
0x18001309c  mov     ebx, eax
0x18001309e  test    eax, eax
0x1800130a0  jns     short loc_1800130CA
0x1800130a2  cmp     eax, 0C0000225h
0x1800130a7  jnz     short loc_1800130B8
0x1800130a9  inc     rdi
0x1800130ac  cmp     rdi, 4
0x1800130b0  jb      loc_180013002
0x1800130b6  jmp     short loc_1800130EB
0x1800130b8  lea     r9, aAslpfileverque_0; "AslpFileVerQueryBlock failed [%x]"
0x1800130bf  mov     r8d, 0C44h
0x1800130c5  jmp     loc_1800131D8
0x1800130ca  mov     r9, [rsp+1B0h+var_180]
0x1800130cf  lea     rdx, [rsp+1B0h+var_170]
0x1800130d4  mov     r8, [rsp+1B0h+var_178]
0x1800130d9  lea     rcx, [rsp+1B0h+var_168]
0x1800130de  call    AslpFileVerStringBlockGetValue
0x1800130e3  test    eax, eax
0x1800130e5  jns     loc_180013198
0x1800130eb  test    r14, r14
0x1800130ee  jz      short loc_180013162
0x1800130f0  mov     rdi, rsi
0x1800130f3  mov     rsi, [rbp+0B0h+arg_20]
0x1800130fa  test    rsi, rsi
0x1800130fd  jz      short loc_180013162
0x1800130ff  mov     rcx, [rsp+1B0h+var_160]
0x180013104  lea     r8, aStringfileinfo_2; "\\StringFileInfo\\%04X%04X\\%s"
0x18001310b  movzx   eax, word ptr [r14+2]
0x180013110  mov     edx, 80h
0x180013115  movzx   r9d, word ptr [r14]
0x180013119  mov     [rsp+1B0h+var_188], rcx
0x18001311e  lea     rcx, [rsp+1B0h+var_150]
0x180013123  mov     dword ptr [rsp+1B0h+var_190], eax
0x180013127  call    RtlStringCchPrintfW
0x18001312c  mov     ebx, eax
0x18001312e  test    eax, eax
0x180013130  js      short loc_1800131AD
0x180013132  lea     r9, [rsp+1B0h+var_180]
0x180013137  mov     rcx, r13
0x18001313a  lea     r8, [rsp+1B0h+var_178]
0x18001313f  lea     rdx, [rsp+1B0h+var_150]
0x180013144  call    AslpFileVerQueryBlock
0x180013149  mov     ebx, eax
0x18001314b  test    eax, eax
0x18001314d  jns     short loc_18001317B
0x18001314f  cmp     eax, 0C0000225h
0x180013154  jnz     short loc_18001316C
0x180013156  inc     rdi
0x180013159  add     r14, 4
0x18001315d  cmp     rdi, rsi
0x180013160  jb      short loc_1800130FF
0x180013162  mov     eax, 0C0000225h
0x180013167  jmp     loc_1800131EF
0x18001316c  lea     r9, aAslpfileverque_0; "AslpFileVerQueryBlock failed [%x]"
0x180013173  mov     r8d, 0C74h
0x180013179  jmp     short loc_1800131D8
0x18001317b  mov     r9, [rsp+1B0h+var_180]
0x180013180  lea     rdx, [rsp+1B0h+var_170]
0x180013185  mov     r8, [rsp+1B0h+var_178]
0x18001318a  lea     rcx, [rsp+1B0h+var_168]
0x18001318f  call    AslpFileVerStringBlockGetValue
0x180013194  test    eax, eax
0x180013196  js      short loc_180013162
0x180013198  mov     rax, [rsp+1B0h+var_170]
0x18001319d  mov     [r12], rax
0x1800131a1  mov     rax, [rsp+1B0h+var_168]
0x1800131a6  mov     [r15], rax
0x1800131a9  xor     eax, eax
0x1800131ab  jmp     short loc_1800131EF
0x1800131ad  lea     r9, aRtlstringcchpr; "RtlStringCchPrintfW failed [%x]"
0x1800131b4  mov     r8d, 0C56h
0x1800131ba  jmp     short loc_1800131D8
0x1800131bc  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x1800131c3  mov     r8d, 0C26h
0x1800131c9  jmp     short loc_1800131D8
0x1800131cb  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x1800131d2  mov     r8d, 0C20h
0x1800131d8  lea     rdx, aAslpfilequeryv; "AslpFileQueryVersionString"
0x1800131df  mov     dword ptr [rsp+1B0h+var_190], ebx
0x1800131e3  mov     ecx, 1
0x1800131e8  call    AslLogCallPrintf
0x1800131ed  mov     eax, ebx
0x1800131ef  mov     rcx, [rbp+0B0h+var_50]
0x1800131f3  xor     rcx, rsp; StackCookie
0x1800131f6  call    __security_check_cookie
0x1800131fb  add     rsp, 178h
0x180013202  pop     r15
0x180013204  pop     r14
0x180013206  pop     r13
0x180013208  pop     r12
0x18001320a  pop     rdi
0x18001320b  pop     rsi
0x18001320c  pop     rbx
0x18001320d  pop     rbp
0x18001320e  retn
```
