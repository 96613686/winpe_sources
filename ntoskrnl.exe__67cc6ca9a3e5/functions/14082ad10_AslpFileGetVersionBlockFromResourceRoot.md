# AslpFileGetVersionBlockFromResourceRoot

- ea: `0x14082ad10`
- end: `0x14082af5a`
- name: `AslpFileGetVersionBlockFromResourceRoot`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x14082af60`

## callees

- `0x1406cba0c`
- `0x14082a02c`
- `0x14082ad10`
- `0x14082c0d4`
- `0x14097d158`

## string_xrefs

- `0x14082add7`: `Found resource directory out of image bounds`
- `0x14082ae35`: `Found resource directory out of image bounds`
- `0x14082ad89`: `Found resource directory entry out of image bounds`
- `0x14082af1d`: `AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]`

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
  const char *v15; // r9
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // r9
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // r11
  int ImageNtHeader; // ebx
  __int64 v30; // rcx
  __int64 v31; // rax
  unsigned __int16 *v32; // rcx
  __int64 v33; // [rsp+90h] [rbp+18h] BYREF

  v4 = *(_QWORD *)(a4 + 32);
  v5 = *(_QWORD *)(a4 + 40);
  v7 = *(unsigned __int16 *)(a3 + 14);
  v33 = 0;
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
  v17 = *(_DWORD *)(v12 + 4);
  if ( v17 >= 0 )
    goto LABEL_24;
  if ( !(unsigned __int8)AslpMemoryCheckBounds((v17 & 0x7FFFFFFF) + a3, 16, v4, v5) )
  {
    v15 = "Found resource directory out of image bounds";
    v14 = 2124;
    goto LABEL_8;
  }
  if ( !*(_WORD *)(v18 + 14) && !*(_WORD *)(v18 + 12) )
    return 3221225609LL;
  if ( !(unsigned __int8)AslpMemoryCheckBounds(v18 + 16, 8, v19, v20) )
  {
    v14 = 2134;
LABEL_7:
    v15 = "Found resource directory entry out of image bounds";
LABEL_8:
    AslLogCallPrintf(1, (unsigned int)"AslpFileGetVersionBlockFromResourceRoot", v14, (_DWORD)v15);
    return 3221226030LL;
  }
  v23 = *(_DWORD *)(v12 + 4);
  if ( v23 < 0 )
  {
    if ( !(unsigned __int8)AslpMemoryCheckBounds((v23 & 0x7FFFFFFF) + a3, 16, v21, v22) )
    {
      v15 = "Found resource directory out of image bounds";
      v14 = 2145;
      goto LABEL_8;
    }
    if ( *(_WORD *)(v25 + 14) || *(_WORD *)(v25 + 12) )
    {
      if ( !(unsigned __int8)AslpMemoryCheckBounds(v24 + v25, v28, v26, v27) )
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
    v15 = "Found resource data entry out of image bounds";
    v14 = 2169;
    goto LABEL_8;
  }
  ImageNtHeader = AslpFileGetImageNtHeader(&v33, a4);
  if ( ImageNtHeader < 0 )
    goto LABEL_32;
  if ( !(unsigned __int8)AslpMemoryCheckBounds(v33, 8, v4, v5) )
  {
    ImageNtHeader = -1073741266;
LABEL_32:
    AslLogCallPrintf(
      1,
      (unsigned int)"AslpFileGetVersionBlockFromResourceRoot",
      2179,
      (unsigned int)"AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]");
    return (unsigned int)ImageNtHeader;
  }
  v31 = AslpImageRvaToVa(v30, a4);
  if ( !(unsigned __int8)AslpMemoryCheckBounds(v31, 38, v4, v5) )
  {
    v15 = "Found version block root but it was out of image bounds";
    v14 = 2185;
    goto LABEL_8;
  }
  *a1 = v32;
  *a2 = *v32;
  return 0;
}

```

## disassembly

```asm
0x14082ad10  mov     rax, rsp
0x14082ad13  push    rbx
0x14082ad14  push    rbp
0x14082ad15  push    rsi
0x14082ad16  push    rdi
0x14082ad17  push    r12
0x14082ad19  push    r13
0x14082ad1b  push    r14
0x14082ad1d  push    r15
0x14082ad1f  sub     rsp, 38h
0x14082ad23  mov     rdi, [r9+20h]
0x14082ad27  xor     r14d, r14d
0x14082ad2a  mov     rsi, [r9+28h]
0x14082ad2e  mov     r13, rcx
0x14082ad31  movzx   ebx, word ptr [r8+0Eh]
0x14082ad36  lea     rcx, [r8+10h]
0x14082ad3a  mov     [rax+18h], r14
0x14082ad3e  mov     r12, rdx
0x14082ad41  movzx   eax, word ptr [r8+0Ch]
0x14082ad46  lea     edx, [r14+10h]
0x14082ad4a  mov     r15, r9
0x14082ad4d  mov     rbp, r8
0x14082ad50  mov     r11d, r14d
0x14082ad53  lea     rcx, [rcx+rax*8]
0x14082ad57  cmp     r11, rbx
0x14082ad5a  jnb     short loc_14082ADAB
0x14082ad5c  mov     r9, rsi
0x14082ad5f  mov     r8, rdi
0x14082ad62  mov     edx, 8
0x14082ad67  call    AslpMemoryCheckBounds
0x14082ad6c  test    al, al
0x14082ad6e  jz      short loc_14082AD83
0x14082ad70  mov     edx, 10h
0x14082ad75  cmp     [rcx], dx
0x14082ad78  jz      short loc_14082ADB1
0x14082ad7a  add     rcx, 8
0x14082ad7e  inc     r11
0x14082ad81  jmp     short loc_14082AD57
0x14082ad83  mov     r8d, 831h
0x14082ad89  lea     r9, aFoundResourceD; "Found resource directory entry out of i"...
0x14082ad90  lea     rdx, aAslpfilegetver_7; "AslpFileGetVersionBlockFromResourceRoot"
0x14082ad97  mov     ecx, 1
0x14082ad9c  call    AslLogCallPrintf
0x14082ada1  mov     eax, 0C000022Eh
0x14082ada6  jmp     loc_14082AF48
0x14082adab  jz      loc_14082AF43
0x14082adb1  mov     eax, [rcx+4]
0x14082adb4  test    eax, eax
0x14082adb6  jns     loc_14082AE73
0x14082adbc  mov     ebx, 7FFFFFFFh
0x14082adc1  mov     r9, rsi
0x14082adc4  and     rax, rbx
0x14082adc7  mov     r8, rdi
0x14082adca  lea     rcx, [rax+rbp]
0x14082adce  call    AslpMemoryCheckBounds
0x14082add3  test    al, al
0x14082add5  jnz     short loc_14082ADE6
0x14082add7  lea     r9, aFoundResourceD_0; "Found resource directory out of image b"...
0x14082adde  mov     r8d, 84Ch
0x14082ade4  jmp     short loc_14082AD90
0x14082ade6  cmp     [rcx+0Eh], r14w
0x14082adeb  jnz     short loc_14082ADF8
0x14082aded  cmp     [rcx+0Ch], r14w
0x14082adf2  jz      loc_14082AF43
0x14082adf8  mov     r11d, 8
0x14082adfe  add     rcx, 10h
0x14082ae02  mov     edx, r11d
0x14082ae05  call    AslpMemoryCheckBounds
0x14082ae0a  test    al, al
0x14082ae0c  jnz     short loc_14082AE19
0x14082ae0e  mov     r8d, 856h
0x14082ae14  jmp     loc_14082AD89
0x14082ae19  mov     eax, [rcx+4]
0x14082ae1c  test    eax, eax
0x14082ae1e  jns     short loc_14082AE73
0x14082ae20  and     rax, rbx
0x14082ae23  mov     edx, 10h
0x14082ae28  lea     rcx, [rax+rbp]
0x14082ae2c  call    AslpMemoryCheckBounds
0x14082ae31  test    al, al
0x14082ae33  jnz     short loc_14082AE47
0x14082ae35  lea     r9, aFoundResourceD_0; "Found resource directory out of image b"...
0x14082ae3c  mov     r8d, 861h
0x14082ae42  jmp     loc_14082AD90
0x14082ae47  cmp     [rcx+0Eh], r14w
0x14082ae4c  jnz     short loc_14082AE59
0x14082ae4e  cmp     [rcx+0Ch], r14w
0x14082ae53  jz      loc_14082AF43
0x14082ae59  add     rcx, rdx
0x14082ae5c  mov     rdx, r11
0x14082ae5f  call    AslpMemoryCheckBounds
0x14082ae64  test    al, al
0x14082ae66  jnz     short loc_14082AE73
0x14082ae68  mov     r8d, 86Bh
0x14082ae6e  jmp     loc_14082AD89
0x14082ae73  mov     r14d, [rcx+4]
0x14082ae77  mov     r9, rsi
0x14082ae7a  add     r14, rbp
0x14082ae7d  mov     r8, rdi
0x14082ae80  mov     rcx, r14
0x14082ae83  mov     edx, 10h
0x14082ae88  call    AslpMemoryCheckBounds
0x14082ae8d  test    al, al
0x14082ae8f  jnz     short loc_14082AEA3
0x14082ae91  lea     r9, aFoundResourceD_1; "Found resource data entry out of image "...
0x14082ae98  mov     r8d, 879h
0x14082ae9e  jmp     loc_14082AD90
0x14082aea3  mov     rdx, r15
0x14082aea6  lea     rcx, [rsp+78h+arg_10]
0x14082aeae  call    AslpFileGetImageNtHeader
0x14082aeb3  mov     ebx, eax
0x14082aeb5  test    eax, eax
0x14082aeb7  js      short loc_14082AF1D
0x14082aeb9  mov     rcx, [rsp+78h+arg_10]
0x14082aec1  mov     r9, rsi
0x14082aec4  mov     r8, rdi
0x14082aec7  mov     edx, 8
0x14082aecc  call    AslpMemoryCheckBounds
0x14082aed1  test    al, al
0x14082aed3  jz      short loc_14082AF18
0x14082aed5  mov     r8d, [r14]
0x14082aed8  mov     rdx, r15
0x14082aedb  call    AslpImageRvaToVa
0x14082aee0  mov     rcx, rax
0x14082aee3  mov     r9, rsi
0x14082aee6  mov     r8, rdi
0x14082aee9  mov     edx, 26h ; '&'
0x14082aeee  call    AslpMemoryCheckBounds
0x14082aef3  test    al, al
0x14082aef5  jnz     short loc_14082AF09
0x14082aef7  lea     r9, aFoundVersionBl; "Found version block root but it was out"...
0x14082aefe  mov     r8d, 889h
0x14082af04  jmp     loc_14082AD90
0x14082af09  mov     [r13+0], rcx
0x14082af0d  movzx   eax, word ptr [rcx]
0x14082af10  mov     [r12], rax
0x14082af14  xor     eax, eax
0x14082af16  jmp     short loc_14082AF48
0x14082af18  mov     ebx, 0C000022Eh
0x14082af1d  lea     r9, aAslpfilegetima_2; "AslpFileGetImageNtHeader failed to get "...
0x14082af24  mov     [rsp+78h+var_58], ebx
0x14082af28  mov     r8d, 883h
0x14082af2e  lea     rdx, aAslpfilegetver_7; "AslpFileGetVersionBlockFromResourceRoot"
0x14082af35  mov     ecx, 1
0x14082af3a  call    AslLogCallPrintf
0x14082af3f  mov     eax, ebx
0x14082af41  jmp     short loc_14082AF48
0x14082af43  mov     eax, 0C0000089h
0x14082af48  add     rsp, 38h
0x14082af4c  pop     r15
0x14082af4e  pop     r14
0x14082af50  pop     r13
0x14082af52  pop     r12
0x14082af54  pop     rdi
0x14082af55  pop     rsi
0x14082af56  pop     rbp
0x14082af57  pop     rbx
0x14082af58  retn
```
