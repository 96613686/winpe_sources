# AslpFileGetVersionBlockFromResourceRoot

- ea: `0x14000eab4`
- end: `0x14000ee05`
- name: `AslpFileGetVersionBlockFromResourceRoot`
- size: `849`
- prototype: `__int64 __fastcall(unsigned __int16 **, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000ee0c`

## callees

- `0x140007074`
- `0x14000dc74`
- `0x14000eab4`
- `0x1400101cc`

## string_xrefs

- `0x14000edb2`: `AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]`
- `0x14000ed50`: `Found resource directory entry out of image bounds`
- `0x14000ed78`: `Found resource directory out of image bounds`
- `0x14000ed8f`: `Found resource directory out of image bounds`

## pseudocode

```c
__int64 __fastcall AslpFileGetVersionBlockFromResourceRoot(unsigned __int16 **a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rdi
  __int64 v7; // r10
  unsigned __int64 v8; // r15
  unsigned __int64 v11; // r11
  unsigned __int64 v12; // r10
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  int v15; // eax
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rax
  int v19; // eax
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // r14
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rsi
  int ImageNtHeader; // ebx
  unsigned __int64 v26; // rax
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rcx
  __int64 v30; // r8
  const char *v31; // r9
  unsigned __int64 v32; // [rsp+90h] [rbp+18h] BYREF

  v5 = *(unsigned __int16 *)(a3 + 14);
  v6 = *(_QWORD *)(a4 + 32);
  v7 = *(unsigned __int16 *)(a3 + 12) + 2LL;
  v8 = *(_QWORD *)(a4 + 40);
  v32 = 0;
  v11 = 0;
  v12 = a3 + 8 * v7;
  if ( v5 )
  {
    while ( v12 >= v6 )
    {
      v13 = v12 + 8;
      if ( v12 >= v12 + 8 )
        break;
      v14 = v8 + v6;
      if ( v12 > v8 + v6 || v13 < v6 || v13 > v14 || v6 > v14 || v8 < 8 )
        break;
      if ( *(_WORD *)v12 != 16 )
      {
        ++v11;
        v12 += 8LL;
        if ( v11 < v5 )
          continue;
      }
      goto LABEL_11;
    }
    v30 = 2097;
    goto LABEL_57;
  }
LABEL_11:
  if ( v11 == v5 )
    return 3221225609LL;
  v15 = *(_DWORD *)(v12 + 4);
  if ( v15 < 0 )
  {
    v16 = a3 + (v15 & 0x7FFFFFFF);
    if ( v16 < v6
      || (v12 = v16 + 16, v16 >= v16 + 16)
      || (v17 = v8 + v6, v16 > v8 + v6)
      || v12 < v6
      || v12 > v17
      || v6 > v17
      || v8 < 0x10 )
    {
      v31 = "Found resource directory out of image bounds";
      v30 = 2124;
      goto LABEL_58;
    }
    if ( !*(_WORD *)(v16 + 14) && !*(_WORD *)(v16 + 12) )
      return 3221225609LL;
    v18 = v16 + 24;
    if ( v12 >= v12 + 8 || v18 < v6 || v18 > v17 )
    {
      v30 = 2134;
      goto LABEL_57;
    }
    v19 = *(_DWORD *)(v12 + 4);
    if ( v19 < 0 )
    {
      v20 = a3 + (v19 & 0x7FFFFFFF);
      if ( v20 < v6 || (v12 = v20 + 16, v20 >= v20 + 16) || v20 > v17 || v12 < v6 || v12 > v17 )
      {
        v31 = "Found resource directory out of image bounds";
        v30 = 2145;
        goto LABEL_58;
      }
      if ( *(_WORD *)(v20 + 14) || *(_WORD *)(v20 + 12) )
      {
        v21 = v20 + 24;
        if ( v12 < v12 + 8 && v21 >= v6 && v21 <= v17 )
          goto LABEL_36;
        v30 = 2155;
LABEL_57:
        v31 = "Found resource directory entry out of image bounds";
LABEL_58:
        AslLogCallPrintf(1, "AslpFileGetVersionBlockFromResourceRoot", v30, v31);
        return 3221226030LL;
      }
      return 3221225609LL;
    }
  }
LABEL_36:
  v22 = a3 + *(unsigned int *)(v12 + 4);
  if ( v22 < v6
    || (v23 = v22 + 16, v22 >= v22 + 16)
    || (v24 = v8 + v6, v22 > v8 + v6)
    || v23 < v6
    || v23 > v24
    || v6 > v24
    || v8 < 0x10 )
  {
    v31 = "Found resource data entry out of image bounds";
    v30 = 2169;
    goto LABEL_58;
  }
  ImageNtHeader = AslpFileGetImageNtHeader(&v32, a4);
  if ( ImageNtHeader >= 0 )
  {
    if ( v32 >= v6 )
    {
      v26 = v32 + 8;
      if ( v32 < v32 + 8 && v32 <= v24 && v26 >= v6 && v26 <= v24 )
      {
        v27 = (unsigned __int16 *)AslpImageRvaToVa(v32, a4);
        if ( (unsigned __int64)v27 >= v6 )
        {
          v28 = v27 + 19;
          if ( v27 < v27 + 19
            && (unsigned __int64)v27 <= v24
            && (unsigned __int64)v28 >= v6
            && (unsigned __int64)v28 <= v24
            && v8 >= 0x26 )
          {
            *a1 = v27;
            *a2 = *v27;
            return 0;
          }
        }
        v31 = "Found version block root but it was out of image bounds";
        v30 = 2185;
        goto LABEL_58;
      }
    }
    ImageNtHeader = -1073741266;
  }
  AslLogCallPrintf(
    1,
    "AslpFileGetVersionBlockFromResourceRoot",
    2179,
    "AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]",
    ImageNtHeader);
  return (unsigned int)ImageNtHeader;
}

```

## disassembly

```asm
0x14000eab4  mov     rax, rsp
0x14000eab7  push    rbx
0x14000eab8  push    rbp
0x14000eab9  push    rsi
0x14000eaba  push    rdi
0x14000eabb  push    r12
0x14000eabd  push    r13
0x14000eabf  push    r14
0x14000eac1  push    r15
0x14000eac3  sub     rsp, 38h
0x14000eac7  movzx   r10d, word ptr [r8+0Ch]
0x14000eacc  mov     r12, rdx
0x14000eacf  movzx   ebx, word ptr [r8+0Eh]
0x14000ead4  xor     edx, edx
0x14000ead6  mov     rdi, [r9+20h]
0x14000eada  add     r10, 2
0x14000eade  mov     r15, [r9+28h]
0x14000eae2  mov     rbp, r9
0x14000eae5  mov     [rax+18h], rdx
0x14000eae9  mov     r13, rcx
0x14000eaec  lea     r9d, [rdx+10h]
0x14000eaf0  mov     r11d, edx
0x14000eaf3  lea     r10, [r8+r10*8]
0x14000eaf7  lea     r14d, [rdx+1]
0x14000eafb  test    rbx, rbx
0x14000eafe  jz      short loc_14000EB59
0x14000eb00  cmp     r10, rdi
0x14000eb03  jb      loc_14000ED4A
0x14000eb09  lea     rax, [r10+8]
0x14000eb0d  cmp     r10, rax
0x14000eb10  ja      loc_14000ED4A
0x14000eb16  lea     rcx, [r15+rdi]
0x14000eb1a  cmp     r10, rcx
0x14000eb1d  ja      loc_14000ED4A
0x14000eb23  cmp     rax, rdi
0x14000eb26  jb      loc_14000ED4A
0x14000eb2c  cmp     rax, rcx
0x14000eb2f  ja      loc_14000ED4A
0x14000eb35  cmp     rdi, rcx
0x14000eb38  ja      loc_14000ED4A
0x14000eb3e  cmp     r15, 8
0x14000eb42  jb      loc_14000ED4A
0x14000eb48  cmp     [r10], r9w
0x14000eb4c  jz      short loc_14000EB59
0x14000eb4e  add     r11, r14
0x14000eb51  mov     r10, rax
0x14000eb54  cmp     r11, rbx
0x14000eb57  jb      short loc_14000EB00
0x14000eb59  cmp     r11, rbx
0x14000eb5c  jz      loc_14000EDEF
0x14000eb62  mov     eax, [r10+4]
0x14000eb66  test    eax, eax
0x14000eb68  jns     loc_14000EC65
0x14000eb6e  mov     r9d, 7FFFFFFFh
0x14000eb74  and     rax, r9
0x14000eb77  add     rax, r8
0x14000eb7a  cmp     rax, rdi
0x14000eb7d  jb      loc_14000ED8F
0x14000eb83  lea     r10, [rax+10h]
0x14000eb87  cmp     rax, r10
0x14000eb8a  ja      loc_14000ED8F
0x14000eb90  lea     rcx, [r15+rdi]
0x14000eb94  cmp     rax, rcx
0x14000eb97  ja      loc_14000ED8F
0x14000eb9d  cmp     r10, rdi
0x14000eba0  jb      loc_14000ED8F
0x14000eba6  cmp     r10, rcx
0x14000eba9  ja      loc_14000ED8F
0x14000ebaf  cmp     rdi, rcx
0x14000ebb2  ja      loc_14000ED8F
0x14000ebb8  cmp     r15, 10h
0x14000ebbc  jb      loc_14000ED8F
0x14000ebc2  cmp     [rax+0Eh], dx
0x14000ebc6  jnz     short loc_14000EBD2
0x14000ebc8  cmp     [rax+0Ch], dx
0x14000ebcc  jz      loc_14000EDEF
0x14000ebd2  lea     rax, [r10+8]
0x14000ebd6  cmp     r10, rax
0x14000ebd9  ja      loc_14000ED87
0x14000ebdf  cmp     rax, rdi
0x14000ebe2  jb      loc_14000ED87
0x14000ebe8  cmp     rax, rcx
0x14000ebeb  ja      loc_14000ED87
0x14000ebf1  mov     eax, [r10+4]
0x14000ebf5  test    eax, eax
0x14000ebf7  jns     short loc_14000EC5F
0x14000ebf9  and     rax, r9
0x14000ebfc  add     rax, r8
0x14000ebff  cmp     rax, rdi
0x14000ec02  jb      loc_14000ED78
0x14000ec08  lea     r10, [rax+10h]
0x14000ec0c  cmp     rax, r10
0x14000ec0f  ja      loc_14000ED78
0x14000ec15  cmp     rax, rcx
0x14000ec18  ja      loc_14000ED78
0x14000ec1e  cmp     r10, rdi
0x14000ec21  jb      loc_14000ED78
0x14000ec27  cmp     r10, rcx
0x14000ec2a  ja      loc_14000ED78
0x14000ec30  cmp     [rax+0Eh], dx
0x14000ec34  jnz     short loc_14000EC40
0x14000ec36  cmp     [rax+0Ch], dx
0x14000ec3a  jz      loc_14000EDEF
0x14000ec40  lea     rax, [r10+8]
0x14000ec44  cmp     r10, rax
0x14000ec47  ja      loc_14000ED70
0x14000ec4d  cmp     rax, rdi
0x14000ec50  jb      loc_14000ED70
0x14000ec56  cmp     rax, rcx
0x14000ec59  ja      loc_14000ED70
0x14000ec5f  mov     r9d, 10h
0x14000ec65  mov     r14d, [r10+4]
0x14000ec69  add     r14, r8
0x14000ec6c  cmp     r14, rdi
0x14000ec6f  jb      loc_14000EDD8
0x14000ec75  lea     rax, [r14+10h]
0x14000ec79  cmp     r14, rax
0x14000ec7c  ja      loc_14000EDD8
0x14000ec82  lea     rsi, [r15+rdi]
0x14000ec86  cmp     r14, rsi
0x14000ec89  ja      loc_14000EDD8
0x14000ec8f  cmp     rax, rdi
0x14000ec92  jb      loc_14000EDD8
0x14000ec98  cmp     rax, rsi
0x14000ec9b  ja      loc_14000EDD8
0x14000eca1  cmp     rdi, rsi
0x14000eca4  ja      loc_14000EDD8
0x14000ecaa  cmp     r15, r9
0x14000ecad  jb      loc_14000EDD8
0x14000ecb3  mov     rdx, rbp
0x14000ecb6  lea     rcx, [rsp+78h+arg_10]
0x14000ecbe  call    AslpFileGetImageNtHeader
0x14000ecc3  mov     ebx, eax
0x14000ecc5  test    eax, eax
0x14000ecc7  js      loc_14000EDB2
0x14000eccd  mov     rcx, [rsp+78h+arg_10]
0x14000ecd5  cmp     rcx, rdi
0x14000ecd8  jb      loc_14000EDAD
0x14000ecde  lea     rax, [rcx+8]
0x14000ece2  cmp     rcx, rax
0x14000ece5  ja      loc_14000EDAD
0x14000eceb  cmp     rcx, rsi
0x14000ecee  ja      loc_14000EDAD
0x14000ecf4  cmp     rax, rdi
0x14000ecf7  jb      loc_14000EDAD
0x14000ecfd  cmp     rax, rsi
0x14000ed00  ja      loc_14000EDAD
0x14000ed06  mov     r8d, [r14]
0x14000ed09  mov     rdx, rbp
0x14000ed0c  call    AslpImageRvaToVa
0x14000ed11  cmp     rax, rdi
0x14000ed14  jb      loc_14000ED9E
0x14000ed1a  lea     rcx, [rax+26h]
0x14000ed1e  cmp     rax, rcx
0x14000ed21  ja      short loc_14000ED9E
0x14000ed23  cmp     rax, rsi
0x14000ed26  ja      short loc_14000ED9E
0x14000ed28  cmp     rcx, rdi
0x14000ed2b  jb      short loc_14000ED9E
0x14000ed2d  cmp     rcx, rsi
0x14000ed30  ja      short loc_14000ED9E
0x14000ed32  cmp     r15, 26h ; '&'
0x14000ed36  jb      short loc_14000ED9E
0x14000ed38  mov     [r13+0], rax
0x14000ed3c  movzx   eax, word ptr [rax]
0x14000ed3f  mov     [r12], rax
0x14000ed43  xor     eax, eax
0x14000ed45  jmp     loc_14000EDF4
0x14000ed4a  mov     r8d, 831h
0x14000ed50  lea     r9, aFoundResourceD; "Found resource directory entry out of i"...
0x14000ed57  mov     ecx, r14d
0x14000ed5a  lea     rdx, aAslpfilegetver_7; "AslpFileGetVersionBlockFromResourceRoot"
0x14000ed61  call    AslLogCallPrintf
0x14000ed66  mov     eax, 0C000022Eh
0x14000ed6b  jmp     loc_14000EDF4
0x14000ed70  mov     r8d, 86Bh
0x14000ed76  jmp     short loc_14000ED50
0x14000ed78  lea     r9, aFoundResourceD_0; "Found resource directory out of image b"...
0x14000ed7f  mov     r8d, 861h
0x14000ed85  jmp     short loc_14000ED57
0x14000ed87  mov     r8d, 856h
0x14000ed8d  jmp     short loc_14000ED50
0x14000ed8f  lea     r9, aFoundResourceD_0; "Found resource directory out of image b"...
0x14000ed96  mov     r8d, 84Ch
0x14000ed9c  jmp     short loc_14000ED57
0x14000ed9e  lea     r9, aFoundVersionBl; "Found version block root but it was out"...
0x14000eda5  mov     r8d, 889h
0x14000edab  jmp     short loc_14000EDE5
0x14000edad  mov     ebx, 0C000022Eh
0x14000edb2  lea     r9, aAslpfilegetima_2; "AslpFileGetImageNtHeader failed to get "...
0x14000edb9  mov     [rsp+78h+var_58], ebx
0x14000edbd  mov     r8d, 883h
0x14000edc3  lea     rdx, aAslpfilegetver_7; "AslpFileGetVersionBlockFromResourceRoot"
0x14000edca  mov     ecx, 1
0x14000edcf  call    AslLogCallPrintf
0x14000edd4  mov     eax, ebx
0x14000edd6  jmp     short loc_14000EDF4
0x14000edd8  lea     r9, aFoundResourceD_1; "Found resource data entry out of image "...
0x14000eddf  mov     r8d, 879h
0x14000ede5  mov     ecx, 1
0x14000edea  jmp     loc_14000ED5A
0x14000edef  mov     eax, 0C0000089h
0x14000edf4  add     rsp, 38h
0x14000edf8  pop     r15
0x14000edfa  pop     r14
0x14000edfc  pop     r13
0x14000edfe  pop     r12
0x14000ee00  pop     rdi
0x14000ee01  pop     rsi
0x14000ee02  pop     rbp
0x14000ee03  pop     rbx
0x14000ee04  retn
```
