# AslpFileGetVersionBlockFromResourceRoot

- ea: `0x14082cc80`
- end: `0x14082ceca`
- name: `AslpFileGetVersionBlockFromResourceRoot`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x14082ced0`

## callees

- `0x1406ce66c`
- `0x14082bf9c`
- `0x14082cc80`
- `0x14082e044`
- `0x1408c2f88`

## string_xrefs

- `0x14082cd47`: `Found resource directory out of image bounds`
- `0x14082cda5`: `Found resource directory out of image bounds`
- `0x14082ccf9`: `Found resource directory entry out of image bounds`
- `0x14082ce8d`: `AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileGetVersionBlockFromResourceRoot(_QWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdi
  __int64 v5; // rsi
  unsigned __int64 v7; // rbx
  unsigned __int64 v11; // r11
  __int64 v12; // rcx
  __int64 v13; // r11
  int v14; // r8d
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // r8
  __int64 v21; // r9
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // r11
  int ImageNtHeader; // ebx
  __int64 v29; // rcx
  __int64 v30; // rax
  unsigned __int16 *v31; // rcx
  __int64 v32; // [rsp+90h] [rbp+18h] BYREF

  v4 = *(_QWORD *)(a4 + 32);
  v5 = *(_QWORD *)(a4 + 40);
  v7 = *(unsigned __int16 *)(a3 + 14);
  v32 = 0;
  v11 = 0;
  v12 = a3 + 16 + 8LL * *(unsigned __int16 *)(a3 + 12);
  while ( v11 < v7 )
  {
    if ( !(unsigned __int8)AslpMemoryCheckBounds(v12, 8, v4, v5) )
    {
      v14 = 2097;
      goto LABEL_7;
    }
    if ( *(_WORD *)v12 == 16 )
      goto LABEL_10;
    v12 += 8;
    v11 = v13 + 1;
  }
  if ( v11 == v7 )
    return 3221225609LL;
LABEL_10:
  v16 = *(_DWORD *)(v12 + 4);
  if ( v16 >= 0 )
    goto LABEL_24;
  if ( !(unsigned __int8)AslpMemoryCheckBounds((v16 & 0x7FFFFFFF) + a3, 16, v4, v5) )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"AslpFileGetVersionBlockFromResourceRoot",
      2124,
      (unsigned int)"Found resource directory out of image bounds");
    return 3221226030LL;
  }
  if ( !*(_WORD *)(v17 + 14) && !*(_WORD *)(v17 + 12) )
    return 3221225609LL;
  if ( !(unsigned __int8)AslpMemoryCheckBounds(v17 + 16, 8, v18, v19) )
  {
    v14 = 2134;
LABEL_7:
    AslLogCallPrintf(
      1,
      (unsigned int)"AslpFileGetVersionBlockFromResourceRoot",
      v14,
      (unsigned int)"Found resource directory entry out of image bounds");
    return 3221226030LL;
  }
  v22 = *(_DWORD *)(v12 + 4);
  if ( v22 < 0 )
  {
    if ( !(unsigned __int8)AslpMemoryCheckBounds((v22 & 0x7FFFFFFF) + a3, 16, v20, v21) )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"AslpFileGetVersionBlockFromResourceRoot",
        2145,
        (unsigned int)"Found resource directory out of image bounds");
      return 3221226030LL;
    }
    if ( *(_WORD *)(v24 + 14) || *(_WORD *)(v24 + 12) )
    {
      if ( !(unsigned __int8)AslpMemoryCheckBounds(v23 + v24, v27, v25, v26) )
      {
        v14 = 2155;
        goto LABEL_7;
      }
      goto LABEL_24;
    }
    return 3221225609LL;
  }
LABEL_24:
  if ( !(unsigned __int8)AslpMemoryCheckBounds(a3 + *(unsigned int *)(v12 + 4), 16, v4, v5) )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"AslpFileGetVersionBlockFromResourceRoot",
      2169,
      (unsigned int)"Found resource data entry out of image bounds");
    return 3221226030LL;
  }
  ImageNtHeader = AslpFileGetImageNtHeader(&v32, a4);
  if ( ImageNtHeader < 0 )
    goto LABEL_32;
  if ( !(unsigned __int8)AslpMemoryCheckBounds(v32, 8, v4, v5) )
  {
    ImageNtHeader = -1073741266;
LABEL_32:
    AslLogCallPrintf(
      1,
      (unsigned int)"AslpFileGetVersionBlockFromResourceRoot",
      2179,
      (unsigned int)"AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]",
      ImageNtHeader);
    return (unsigned int)ImageNtHeader;
  }
  v30 = AslpImageRvaToVa(v29, a4);
  if ( !(unsigned __int8)AslpMemoryCheckBounds(v30, 38, v4, v5) )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"AslpFileGetVersionBlockFromResourceRoot",
      2185,
      (unsigned int)"Found version block root but it was out of image bounds");
    return 3221226030LL;
  }
  *a1 = v31;
  *a2 = *v31;
  return 0;
}

```

## disassembly

```asm
0x14082cc80  mov     rax, rsp
0x14082cc83  push    rbx
0x14082cc84  push    rbp
0x14082cc85  push    rsi
0x14082cc86  push    rdi
0x14082cc87  push    r12
0x14082cc89  push    r13
0x14082cc8b  push    r14
0x14082cc8d  push    r15
0x14082cc8f  sub     rsp, 38h
0x14082cc93  mov     rdi, [r9+20h]
0x14082cc97  xor     r14d, r14d
0x14082cc9a  mov     rsi, [r9+28h]
0x14082cc9e  mov     r13, rcx
0x14082cca1  movzx   ebx, word ptr [r8+0Eh]
0x14082cca6  lea     rcx, [r8+10h]
0x14082ccaa  mov     [rax+18h], r14
0x14082ccae  mov     r12, rdx
0x14082ccb1  movzx   eax, word ptr [r8+0Ch]
0x14082ccb6  lea     edx, [r14+10h]
0x14082ccba  mov     r15, r9
0x14082ccbd  mov     rbp, r8
0x14082ccc0  mov     r11d, r14d
0x14082ccc3  lea     rcx, [rcx+rax*8]
0x14082ccc7  cmp     r11, rbx
0x14082ccca  jnb     short loc_14082CD1B
0x14082cccc  mov     r9, rsi
0x14082cccf  mov     r8, rdi
0x14082ccd2  mov     edx, 8
0x14082ccd7  call    AslpMemoryCheckBounds
0x14082ccdc  test    al, al
0x14082ccde  jz      short loc_14082CCF3
0x14082cce0  mov     edx, 10h
0x14082cce5  cmp     [rcx], dx
0x14082cce8  jz      short loc_14082CD21
0x14082ccea  add     rcx, 8
0x14082ccee  inc     r11
0x14082ccf1  jmp     short loc_14082CCC7
0x14082ccf3  mov     r8d, 831h
0x14082ccf9  lea     r9, aFoundResourceD; "Found resource directory entry out of i"...
0x14082cd00  lea     rdx, aAslpfilegetver_7; "AslpFileGetVersionBlockFromResourceRoot"
0x14082cd07  mov     ecx, 1
0x14082cd0c  call    AslLogCallPrintf
0x14082cd11  mov     eax, 0C000022Eh
0x14082cd16  jmp     loc_14082CEB8
0x14082cd1b  jz      loc_14082CEB3
0x14082cd21  mov     eax, [rcx+4]
0x14082cd24  test    eax, eax
0x14082cd26  jns     loc_14082CDE3
0x14082cd2c  mov     ebx, 7FFFFFFFh
0x14082cd31  mov     r9, rsi
0x14082cd34  and     rax, rbx
0x14082cd37  mov     r8, rdi
0x14082cd3a  lea     rcx, [rax+rbp]
0x14082cd3e  call    AslpMemoryCheckBounds
0x14082cd43  test    al, al
0x14082cd45  jnz     short loc_14082CD56
0x14082cd47  lea     r9, aFoundResourceD_0; "Found resource directory out of image b"...
0x14082cd4e  mov     r8d, 84Ch
0x14082cd54  jmp     short loc_14082CD00
0x14082cd56  cmp     [rcx+0Eh], r14w
0x14082cd5b  jnz     short loc_14082CD68
0x14082cd5d  cmp     [rcx+0Ch], r14w
0x14082cd62  jz      loc_14082CEB3
0x14082cd68  mov     r11d, 8
0x14082cd6e  add     rcx, 10h
0x14082cd72  mov     edx, r11d
0x14082cd75  call    AslpMemoryCheckBounds
0x14082cd7a  test    al, al
0x14082cd7c  jnz     short loc_14082CD89
0x14082cd7e  mov     r8d, 856h
0x14082cd84  jmp     loc_14082CCF9
0x14082cd89  mov     eax, [rcx+4]
0x14082cd8c  test    eax, eax
0x14082cd8e  jns     short loc_14082CDE3
0x14082cd90  and     rax, rbx
0x14082cd93  mov     edx, 10h
0x14082cd98  lea     rcx, [rax+rbp]
0x14082cd9c  call    AslpMemoryCheckBounds
0x14082cda1  test    al, al
0x14082cda3  jnz     short loc_14082CDB7
0x14082cda5  lea     r9, aFoundResourceD_0; "Found resource directory out of image b"...
0x14082cdac  mov     r8d, 861h
0x14082cdb2  jmp     loc_14082CD00
0x14082cdb7  cmp     [rcx+0Eh], r14w
0x14082cdbc  jnz     short loc_14082CDC9
0x14082cdbe  cmp     [rcx+0Ch], r14w
0x14082cdc3  jz      loc_14082CEB3
0x14082cdc9  add     rcx, rdx
0x14082cdcc  mov     rdx, r11
0x14082cdcf  call    AslpMemoryCheckBounds
0x14082cdd4  test    al, al
0x14082cdd6  jnz     short loc_14082CDE3
0x14082cdd8  mov     r8d, 86Bh
0x14082cdde  jmp     loc_14082CCF9
0x14082cde3  mov     r14d, [rcx+4]
0x14082cde7  mov     r9, rsi
0x14082cdea  add     r14, rbp
0x14082cded  mov     r8, rdi
0x14082cdf0  mov     rcx, r14
0x14082cdf3  mov     edx, 10h
0x14082cdf8  call    AslpMemoryCheckBounds
0x14082cdfd  test    al, al
0x14082cdff  jnz     short loc_14082CE13
0x14082ce01  lea     r9, aFoundResourceD_1; "Found resource data entry out of image "...
0x14082ce08  mov     r8d, 879h
0x14082ce0e  jmp     loc_14082CD00
0x14082ce13  mov     rdx, r15
0x14082ce16  lea     rcx, [rsp+78h+arg_10]
0x14082ce1e  call    AslpFileGetImageNtHeader
0x14082ce23  mov     ebx, eax
0x14082ce25  test    eax, eax
0x14082ce27  js      short loc_14082CE8D
0x14082ce29  mov     rcx, [rsp+78h+arg_10]
0x14082ce31  mov     r9, rsi
0x14082ce34  mov     r8, rdi
0x14082ce37  mov     edx, 8
0x14082ce3c  call    AslpMemoryCheckBounds
0x14082ce41  test    al, al
0x14082ce43  jz      short loc_14082CE88
0x14082ce45  mov     r8d, [r14]
0x14082ce48  mov     rdx, r15
0x14082ce4b  call    AslpImageRvaToVa
0x14082ce50  mov     rcx, rax
0x14082ce53  mov     r9, rsi
0x14082ce56  mov     r8, rdi
0x14082ce59  mov     edx, 26h ; '&'
0x14082ce5e  call    AslpMemoryCheckBounds
0x14082ce63  test    al, al
0x14082ce65  jnz     short loc_14082CE79
0x14082ce67  lea     r9, aFoundVersionBl; "Found version block root but it was out"...
0x14082ce6e  mov     r8d, 889h
0x14082ce74  jmp     loc_14082CD00
0x14082ce79  mov     [r13+0], rcx
0x14082ce7d  movzx   eax, word ptr [rcx]
0x14082ce80  mov     [r12], rax
0x14082ce84  xor     eax, eax
0x14082ce86  jmp     short loc_14082CEB8
0x14082ce88  mov     ebx, 0C000022Eh
0x14082ce8d  lea     r9, aAslpfilegetima_2; "AslpFileGetImageNtHeader failed to get "...
0x14082ce94  mov     [rsp+78h+var_58], ebx
0x14082ce98  mov     r8d, 883h
0x14082ce9e  lea     rdx, aAslpfilegetver_7; "AslpFileGetVersionBlockFromResourceRoot"
0x14082cea5  mov     ecx, 1
0x14082ceaa  call    AslLogCallPrintf
0x14082ceaf  mov     eax, ebx
0x14082ceb1  jmp     short loc_14082CEB8
0x14082ceb3  mov     eax, 0C0000089h
0x14082ceb8  add     rsp, 38h
0x14082cebc  pop     r15
0x14082cebe  pop     r14
0x14082cec0  pop     r13
0x14082cec2  pop     r12
0x14082cec4  pop     rdi
0x14082cec5  pop     rsi
0x14082cec6  pop     rbp
0x14082cec7  pop     rbx
0x14082cec8  retn
```
