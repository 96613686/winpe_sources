# UnifyILinkInfo(_volumeid const *,uint,ushort const *,_cnrlink const *,uint,ushort const *,_ilinkinfoW * *)

- ea: `0x180002b00`
- end: `0x18000303e`
- name: `?UnifyILinkInfo@@YAHPEBU_volumeid@@IPEBGPEBU_cnrlink@@I1PEAPEAU_ilinkinfoW@@@Z`
- size: `1342`
- prototype: `__int64 __usercall@<rax>(const struct _volumeid *Src@<rcx>, size_t Size@<rdx>, LPCWSTR lpString1@<r8>, const struct _cnrlink *@<r9>, size_t, LPCWCH lpWideCharStr, struct _ilinkinfoW **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180001f10`
- `0x180002500`

## callees

- `0x180002b00`
- `0x180003050`
- `0x180005715`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180002c00`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180002c1a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180002ff0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180002c00`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180002c1a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180002ff0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180002f0d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180002f7c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180002f0d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180002f7c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180002ef2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180002f50`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180002ef2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180002f50`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180002b78`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180002eb4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180002b78`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180002eb4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002c7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002c7c`

## pseudocode

```c
__int64 __fastcall UnifyILinkInfo(
        const struct _volumeid *Src,
        size_t Size,
        LPCWSTR lpString1,
        const struct _cnrlink *a4,
        size_t Sizea,
        LPCWCH lpWideCharStr,
        struct _ilinkinfoW **a7)
{
  LPCWCH v8; // rsi
  unsigned int v9; // r13d
  size_t v11; // r14
  int v12; // r12d
  unsigned int v13; // r15d
  int v14; // ecx
  int v15; // edx
  int v16; // eax
  unsigned int v17; // ebx
  __int64 result; // rax
  struct _ilinkinfoW **v19; // r11
  __int64 v20; // rdi
  int v21; // ebx
  __int64 v22; // r9
  _BYTE *v23; // r8
  __int64 v24; // rcx
  CHAR *v25; // rdx
  _BYTE *v26; // rax
  int v27; // ebp
  unsigned int v28; // eax
  __int64 v29; // r8
  _BYTE *v30; // r9
  __int64 v31; // rcx
  CHAR *v32; // rdx
  _BYTE *v33; // rax
  unsigned __int64 v34; // r8
  _WORD *v35; // rcx
  _WORD *v36; // rdx
  unsigned int v37; // ebx
  int v38; // eax
  int v39; // r10d
  int v40; // [rsp+40h] [rbp-4B8h]
  unsigned int v41; // [rsp+44h] [rbp-4B4h]
  int v42; // [rsp+48h] [rbp-4B0h]
  unsigned int v43; // [rsp+4Ch] [rbp-4ACh]
  CHAR MultiByteStr[272]; // [rsp+70h] [rbp-488h] BYREF
  CHAR lpMultiByteStr[272]; // [rsp+180h] [rbp-378h] BYREF
  WCHAR WideCharStr[264]; // [rsp+290h] [rbp-268h] BYREF

  v8 = lpWideCharStr;
  v9 = 0;
  v11 = (unsigned int)Size;
  v43 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, MultiByteStr, 260, 0, 0);
  MultiByteStr[259] = 0;
  if ( !v43 )
  {
    v12 = 1;
    MultiByteStr[0] = 0;
    v43 = 1;
LABEL_3:
    v40 = 1;
    goto LABEL_4;
  }
  v38 = MultiByteToWideChar(0, 0, MultiByteStr, -1, WideCharStr, 260);
  WideCharStr[259] = 0;
  if ( !v38 || (v40 = 0, v12 = 0, lstrcmpW(lpWideCharStr, WideCharStr)) )
  {
    v12 = 1;
    goto LABEL_3;
  }
LABEL_4:
  if ( !(_DWORD)v11 )
  {
    v13 = 0;
    goto LABEL_6;
  }
  v13 = WideCharToMultiByte(0, 0, lpString1, -1, lpMultiByteStr, 260, 0, 0);
  if ( !v13 )
  {
    v12 = 1;
    lpMultiByteStr[0] = 0;
    v13 = 1;
LABEL_9:
    v40 = 1;
    v42 = 36;
    v41 = 2 * lstrlenW(lpWideCharStr) + 2;
    goto LABEL_10;
  }
  if ( !MultiByteToWideChar(0, 0, lpMultiByteStr, -1, WideCharStr, 260) || lstrcmpW(lpString1, WideCharStr) )
  {
    v12 = 1;
    goto LABEL_9;
  }
LABEL_6:
  if ( !v12 )
  {
    v42 = 28;
    v14 = v13 + v11 + 28;
    v15 = 0;
LABEL_13:
    v41 = v15;
    goto LABEL_14;
  }
  v40 = v12;
  v42 = 36;
  v15 = 2 * lstrlenW(lpWideCharStr) + 2;
  v41 = v15;
  if ( !(_DWORD)v11 )
  {
    v40 = v12;
    goto LABEL_11;
  }
LABEL_10:
  v16 = lstrlenW(lpString1);
  v15 = v41;
  v9 = 2 * v16 + 2;
LABEL_11:
  v14 = v11 + v13 + 36;
  if ( !(_DWORD)v11 )
  {
    v40 = v12;
    v42 = 36;
    goto LABEL_13;
  }
  v14 = v9 + ((v11 + v13 + 37) & 0xFFFFFFFE);
LABEL_14:
  if ( (_DWORD)Sizea )
    v14 = Sizea + ((v14 + 3) & 0xFFFFFFFC);
  v17 = v14 + v43;
  if ( v40 )
    v17 = v15 + ((v17 + 1) & 0xFFFFFFFE);
  result = (__int64)LocalAlloc(0x40u, v17);
  v19 = a7;
  *a7 = (struct _ilinkinfoW *)result;
  if ( result )
  {
    *(_DWORD *)result = v17;
    v20 = 2147483646;
    v21 = v42;
    *((_DWORD *)*a7 + 1) = v42;
    *((_DWORD *)*a7 + 2) = 0;
    if ( (_DWORD)v11 )
    {
      *((_DWORD *)*a7 + 3) = v42;
      memcpy_0((char *)*a7 + *((unsigned int *)*a7 + 3), Src, v11);
      v19 = a7;
      v22 = v13;
      *((_DWORD *)*a7 + 4) = v11 + v42;
      v23 = (char *)*v19 + *((unsigned int *)*v19 + 4);
      if ( v13 - 1 > 0x7FFFFFFE )
      {
        if ( v13 )
          *v23 = 0;
      }
      else
      {
        v24 = 2147483646;
        v25 = lpMultiByteStr;
        do
        {
          if ( !v24 )
            break;
          if ( !*v25 )
            break;
          *v23++ = *v25++;
          --v24;
          --v22;
        }
        while ( v22 );
        v26 = v23 - 1;
        if ( v22 )
          v26 = v23;
        *v26 = 0;
      }
      v27 = v40;
      v21 = v13 + v11 + v42;
      if ( v40 )
      {
        *((_DWORD *)*a7 + 7) = (v21 + 1) & 0xFFFFFFFE;
        StringCbCopyW((unsigned __int16 *)((char *)*a7 + *((unsigned int *)*a7 + 7)), v9, lpString1);
        v21 = v39 + v9;
      }
      *((_DWORD *)*v19 + 2) |= 1u;
    }
    else
    {
      v27 = v40;
    }
    if ( (_DWORD)Sizea )
    {
      v37 = (v21 + 3) & 0xFFFFFFFC;
      *((_DWORD *)*v19 + 5) = v37;
      memcpy_0((char *)*v19 + *((unsigned int *)*v19 + 5), a4, (unsigned int)Sizea);
      v19 = a7;
      v21 = Sizea + v37;
      *((_DWORD *)*a7 + 2) |= 2u;
    }
    *((_DWORD *)*v19 + 6) = v21;
    v28 = v43;
    v29 = v43;
    v30 = (char *)*v19 + *((unsigned int *)*v19 + 6);
    if ( v43 > 0x7FFFFFFFuLL )
    {
      *v30 = 0;
    }
    else
    {
      v31 = 2147483646;
      v32 = MultiByteStr;
      do
      {
        if ( !v31 )
          break;
        if ( !*v32 )
          break;
        *v30++ = *v32++;
        --v31;
        --v29;
      }
      while ( v29 );
      v33 = v30 - 1;
      if ( v29 )
        v33 = v30;
      *v33 = 0;
      v28 = v43;
    }
    if ( v27 )
    {
      v34 = (unsigned __int64)v41 >> 1;
      *((_DWORD *)*v19 + 8) = (v21 + v28 + 1) & 0xFFFFFFFE;
      if ( v34 )
      {
        v35 = (_WORD *)((char *)*v19 + *((unsigned int *)*v19 + 8));
        do
        {
          if ( !v20 )
            break;
          if ( !*v8 )
            break;
          *v35++ = *v8++;
          --v20;
          --v34;
        }
        while ( v34 );
        v36 = v35 - 1;
        if ( v34 )
          v36 = v35;
        *v36 = 0;
      }
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180002b00  push    rbx
0x180002b02  push    rbp
0x180002b03  push    rsi
0x180002b04  push    rdi
0x180002b05  push    r12
0x180002b07  push    r13
0x180002b09  push    r14
0x180002b0b  sub     rsp, 4C0h
0x180002b12  mov     rax, cs:__security_cookie
0x180002b19  xor     rax, rsp
0x180002b1c  mov     [rsp+4F8h+var_58], rax
0x180002b24  mov     rax, [rsp+4F8h+arg_30]
0x180002b2c  mov     rbx, r8
0x180002b2f  mov     rsi, [rsp+4F8h+lpWideCharStr]
0x180002b37  xor     r13d, r13d
0x180002b3a  mov     [rsp+4F8h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x180002b3f  mov     rbp, rcx
0x180002b42  mov     [rsp+4F8h+var_4A8], rax
0x180002b47  mov     r8, rsi; lpWideCharStr
0x180002b4a  mov     [rsp+4F8h+lpDefaultChar], r13; lpDefaultChar
0x180002b4f  lea     rax, [rsp+4F8h+MultiByteStr]
0x180002b54  mov     [rsp+4F8h+Src], r9
0x180002b59  xor     ecx, ecx; CodePage
0x180002b5b  mov     r14d, edx
0x180002b5e  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180002b64  mov     [rsp+4F8h+cbMultiByte], 104h; cbMultiByte
0x180002b6c  xor     edx, edx; dwFlags
0x180002b6e  mov     [rsp+4F8h+lpMultiByteStr], rax; lpMultiByteStr
0x180002b73  mov     [rsp+4F8h+var_4A0], rbx
0x180002b78  call    cs:__imp_WideCharToMultiByte
0x180002b7f  nop     dword ptr [rax+rax+00h]
0x180002b84  mov     [rsp+4F8h+var_4AC], eax
0x180002b88  mov     [rsp+4F8h+var_385], r13b
0x180002b90  test    eax, eax
0x180002b92  jnz     loc_180002F2C
0x180002b98  mov     r12d, 1
0x180002b9e  mov     [rsp+4F8h+MultiByteStr], r13b
0x180002ba3  mov     [rsp+4F8h+var_4AC], r12d
0x180002ba8  mov     [rsp+4F8h+var_4B8], r12d
0x180002bad  mov     [rsp+4F8h+var_40], r15
0x180002bb5  test    r14d, r14d
0x180002bb8  jnz     loc_180002E88
0x180002bbe  mov     r15d, r13d
0x180002bc1  test    r12d, r12d
0x180002bc4  jnz     loc_180002FDF
0x180002bca  lea     ecx, [r14+1Ch]
0x180002bce  mov     [rsp+4F8h+var_4B0], 1Ch
0x180002bd6  add     ecx, r15d
0x180002bd9  mov     edx, r13d
0x180002bdc  jmp     short loc_180002C4A
0x180002bde  mov     r12d, 1
0x180002be4  mov     [rsp+4F8h+var_378], r13b
0x180002bec  mov     r15d, r12d
0x180002bef  mov     edi, 24h ; '$'
0x180002bf4  mov     [rsp+4F8h+var_4B8], r12d
0x180002bf9  mov     rcx, rsi; lpString
0x180002bfc  mov     [rsp+4F8h+var_4B0], edi
0x180002c00  call    cs:__imp_lstrlenW
0x180002c07  nop     dword ptr [rax+rax+00h]
0x180002c0c  lea     eax, ds:2[rax*2]
0x180002c13  mov     [rsp+4F8h+var_4B4], eax
0x180002c17  mov     rcx, rbx; lpString
0x180002c1a  call    cs:__imp_lstrlenW
0x180002c21  nop     dword ptr [rax+rax+00h]
0x180002c26  mov     edx, [rsp+4F8h+var_4B4]
0x180002c2a  lea     r13d, ds:2[rax*2]
0x180002c32  lea     ecx, [r14+r15]
0x180002c36  add     ecx, edi
0x180002c38  test    r12d, r12d
0x180002c3b  jnz     loc_180002FC9
0x180002c41  mov     [rsp+4F8h+var_4B8], r12d
0x180002c46  mov     [rsp+4F8h+var_4B0], edi
0x180002c4a  mov     [rsp+4F8h+var_4B4], edx
0x180002c4e  mov     r12d, dword ptr [rsp+4F8h+Size]
0x180002c56  test    r12d, r12d
0x180002c59  jz      short loc_180002C64
0x180002c5b  add     ecx, 3
0x180002c5e  and     ecx, 0FFFFFFFCh
0x180002c61  add     ecx, r12d
0x180002c64  mov     ebx, [rsp+4F8h+var_4AC]
0x180002c68  add     ebx, ecx
0x180002c6a  cmp     [rsp+4F8h+var_4B8], 0
0x180002c6f  jnz     loc_180002E7C
0x180002c75  mov     edx, ebx; uBytes
0x180002c77  mov     ecx, 40h ; '@'; uFlags
0x180002c7c  call    cs:__imp_LocalAlloc
0x180002c83  nop     dword ptr [rax+rax+00h]
0x180002c88  mov     r11, [rsp+4F8h+var_4A8]
0x180002c8d  mov     [r11], rax
0x180002c90  test    rax, rax
0x180002c93  jz      loc_180002DE6
0x180002c99  mov     [rax], ebx
0x180002c9b  mov     edi, 7FFFFFFEh
0x180002ca0  mov     rax, [r11]
0x180002ca3  mov     ebx, [rsp+4F8h+var_4B0]
0x180002ca7  mov     [rax+4], ebx
0x180002caa  mov     rax, [r11]
0x180002cad  mov     dword ptr [rax+8], 0
0x180002cb4  test    r14d, r14d
0x180002cb7  jz      loc_18000302C
0x180002cbd  mov     rax, [r11]
0x180002cc0  mov     r8, r14; Size
0x180002cc3  mov     rdx, rbp; Src
0x180002cc6  mov     [rax+0Ch], ebx
0x180002cc9  mov     rax, [r11]
0x180002ccc  mov     ecx, [rax+0Ch]
0x180002ccf  add     rcx, rax; void *
0x180002cd2  call    memcpy_0
0x180002cd7  mov     r11, [rsp+4F8h+var_4A8]
0x180002cdc  add     ebx, r14d
0x180002cdf  mov     r9d, r15d
0x180002ce2  mov     rax, [r11]
0x180002ce5  mov     [rax+10h], ebx
0x180002ce8  lea     eax, [r15-1]
0x180002cec  mov     rcx, [r11]
0x180002cef  mov     r8d, [rcx+10h]
0x180002cf3  add     r8, rcx
0x180002cf6  cmp     eax, edi
0x180002cf8  ja      loc_18000301A
0x180002cfe  mov     ecx, edi
0x180002d00  lea     rdx, [rsp+4F8h+var_378]
0x180002d08  test    rcx, rcx
0x180002d0b  jz      short loc_180002D26
0x180002d0d  movzx   eax, byte ptr [rdx]
0x180002d10  test    al, al
0x180002d12  jz      short loc_180002D26
0x180002d14  mov     [r8], al
0x180002d17  inc     rdx
0x180002d1a  inc     r8
0x180002d1d  dec     rcx
0x180002d20  sub     r9, 1
0x180002d24  jnz     short loc_180002D08
0x180002d26  test    r9, r9
0x180002d29  lea     rax, [r8-1]
0x180002d2d  cmovnz  rax, r8
0x180002d31  mov     byte ptr [rax], 0
0x180002d34  mov     ebp, [rsp+4F8h+var_4B8]
0x180002d38  add     ebx, r15d
0x180002d3b  test    ebp, ebp
0x180002d3d  jnz     loc_180002F9B
0x180002d43  mov     rax, [r11]
0x180002d46  or      dword ptr [rax+8], 1
0x180002d4a  test    r12d, r12d
0x180002d4d  jnz     loc_180002E46
0x180002d53  mov     rax, [r11]
0x180002d56  mov     [rax+18h], ebx
0x180002d59  mov     rcx, [r11]
0x180002d5c  mov     eax, [rsp+4F8h+var_4AC]
0x180002d60  mov     r8d, eax
0x180002d63  mov     r9d, [rcx+18h]
0x180002d67  add     r9, rcx
0x180002d6a  test    eax, eax
0x180002d6c  jz      short loc_180002DB2
0x180002d6e  cmp     rax, 7FFFFFFFh
0x180002d74  ja      loc_180003035
0x180002d7a  mov     rcx, rdi
0x180002d7d  lea     rdx, [rsp+4F8h+MultiByteStr]
0x180002d82  test    rcx, rcx
0x180002d85  jz      short loc_180002DA0
0x180002d87  movzx   eax, byte ptr [rdx]
0x180002d8a  test    al, al
0x180002d8c  jz      short loc_180002DA0
0x180002d8e  mov     [r9], al
0x180002d91  inc     rdx
0x180002d94  inc     r9
0x180002d97  dec     rcx
0x180002d9a  sub     r8, 1
0x180002d9e  jnz     short loc_180002D82
0x180002da0  test    r8, r8
0x180002da3  lea     rax, [r9-1]
0x180002da7  cmovnz  rax, r9
0x180002dab  mov     byte ptr [rax], 0
0x180002dae  mov     eax, [rsp+4F8h+var_4AC]
0x180002db2  test    ebp, ebp
0x180002db4  jnz     short loc_180002DE8
0x180002db6  mov     eax, 1
0x180002dbb  mov     r15, [rsp+4F8h+var_40]
0x180002dc3  mov     rcx, [rsp+4F8h+var_58]
0x180002dcb  xor     rcx, rsp; StackCookie
0x180002dce  call    __security_check_cookie
0x180002dd3  add     rsp, 4C0h
0x180002dda  pop     r14
0x180002ddc  pop     r13
0x180002dde  pop     r12
0x180002de0  pop     rdi
0x180002de1  pop     rsi
0x180002de2  pop     rbp
0x180002de3  pop     rbx
0x180002de4  retn
0x180002de6  jmp     short loc_180002DBB
0x180002de8  mov     r8d, [rsp+4F8h+var_4B4]
0x180002ded  lea     ecx, [rax+1]
0x180002df0  mov     rax, [r11]
0x180002df3  add     ecx, ebx
0x180002df5  and     ecx, 0FFFFFFFEh
0x180002df8  shr     r8, 1
0x180002dfb  mov     [rax+20h], ecx
0x180002dfe  jz      short loc_180002DB6
0x180002e00  mov     rax, [r11]
0x180002e03  mov     ecx, [rax+20h]
0x180002e06  add     rcx, rax
0x180002e09  nop     dword ptr [rax+00000000h]
0x180002e10  test    rdi, rdi
0x180002e13  jz      short loc_180002E31
0x180002e15  movzx   eax, word ptr [rsi]
0x180002e18  test    ax, ax
0x180002e1b  jz      short loc_180002E31
0x180002e1d  mov     [rcx], ax
0x180002e20  add     rsi, 2
0x180002e24  add     rcx, 2
0x180002e28  dec     rdi
0x180002e2b  sub     r8, 1
0x180002e2f  jnz     short loc_180002E10
0x180002e31  test    r8, r8
0x180002e34  lea     rdx, [rcx-2]
0x180002e38  cmovnz  rdx, rcx
0x180002e3c  xor     ecx, ecx
0x180002e3e  mov     [rdx], cx
0x180002e41  jmp     loc_180002DB6
0x180002e46  mov     rax, [r11]
0x180002e49  add     ebx, 3
0x180002e4c  mov     rdx, [rsp+4F8h+Src]; Src
0x180002e51  and     ebx, 0FFFFFFFCh
0x180002e54  mov     r8, r12; Size
0x180002e57  mov     [rax+14h], ebx
0x180002e5a  mov     rax, [r11]
0x180002e5d  mov     ecx, [rax+14h]
0x180002e60  add     rcx, rax; void *
0x180002e63  call    memcpy_0
0x180002e68  mov     r11, [rsp+4F8h+var_4A8]
0x180002e6d  add     ebx, r12d
0x180002e70  mov     rax, [r11]
0x180002e73  or      dword ptr [rax+8], 2
0x180002e77  jmp     loc_180002D53
0x180002e7c  inc     ebx
0x180002e7e  and     ebx, 0FFFFFFFEh
0x180002e81  add     ebx, edx
0x180002e83  jmp     loc_180002C75
0x180002e88  mov     [rsp+4F8h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x180002e8d  lea     rax, [rsp+4F8h+var_378]
0x180002e95  mov     [rsp+4F8h+lpDefaultChar], r13; lpDefaultChar
0x180002e9a  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180002ea0  mov     [rsp+4F8h+cbMultiByte], 104h; cbMultiByte
0x180002ea8  mov     r8, rbx; lpWideCharStr
0x180002eab  xor     edx, edx; dwFlags
0x180002ead  mov     [rsp+4F8h+lpMultiByteStr], rax; lpMultiByteStr
0x180002eb2  xor     ecx, ecx; CodePage
0x180002eb4  call    cs:__imp_WideCharToMultiByte
0x180002ebb  nop     dword ptr [rax+rax+00h]
0x180002ec0  mov     r15d, eax
0x180002ec3  test    eax, eax
0x180002ec5  jz      loc_180002BDE
0x180002ecb  lea     rax, [rsp+4F8h+WideCharStr]
0x180002ed3  mov     [rsp+4F8h+cbMultiByte], 104h; cchWideChar
0x180002edb  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180002ee1  mov     [rsp+4F8h+lpMultiByteStr], rax; lpWideCharStr
0x180002ee6  lea     r8, [rsp+4F8h+var_378]; lpMultiByteStr
0x180002eee  xor     edx, edx; dwFlags
0x180002ef0  xor     ecx, ecx; CodePage
0x180002ef2  call    cs:__imp_MultiByteToWideChar
0x180002ef9  nop     dword ptr [rax+rax+00h]
0x180002efe  test    eax, eax
0x180002f00  jz      short loc_180002F21
0x180002f02  lea     rdx, [rsp+4F8h+WideCharStr]; lpString2
0x180002f0a  mov     rcx, rbx; lpString1
0x180002f0d  call    cs:__imp_lstrcmpW
0x180002f14  nop     dword ptr [rax+rax+00h]
0x180002f19  test    eax, eax
0x180002f1b  jz      loc_180002BC1
0x180002f21  mov     r12d, 1
0x180002f27  jmp     loc_180002BEF
0x180002f2c  lea     rax, [rsp+4F8h+WideCharStr]
0x180002f34  mov     [rsp+4F8h+cbMultiByte], 104h; cchWideChar
0x180002f3c  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180002f42  mov     [rsp+4F8h+lpMultiByteStr], rax; lpWideCharStr
0x180002f47  lea     r8, [rsp+4F8h+MultiByteStr]; lpMultiByteStr
0x180002f4c  xor     edx, edx; dwFlags
0x180002f4e  xor     ecx, ecx; CodePage
0x180002f50  call    cs:__imp_MultiByteToWideChar
0x180002f57  nop     dword ptr [rax+rax+00h]
0x180002f5c  mov     [rsp+4F8h+var_62], r13w
0x180002f65  test    eax, eax
0x180002f67  jz      short loc_180002F90
0x180002f69  lea     rdx, [rsp+4F8h+WideCharStr]; lpString2
0x180002f71  mov     [rsp+4F8h+var_4B8], r13d
0x180002f76  mov     rcx, rsi; lpString1
0x180002f79  mov     r12d, r13d
0x180002f7c  call    cs:__imp_lstrcmpW
0x180002f83  nop     dword ptr [rax+rax+00h]
0x180002f88  test    eax, eax
0x180002f8a  jz      loc_180002BAD
0x180002f90  mov     r12d, 1
0x180002f96  jmp     loc_180002BA8
0x180002f9b  mov     rax, [r11]
0x180002f9e  lea     r10d, [rbx+1]
0x180002fa2  mov     r8, [rsp+4F8h+var_4A0]; unsigned __int16 *
0x180002fa7  and     r10d, 0FFFFFFFEh
0x180002fab  mov     edx, r13d; unsigned __int64
0x180002fae  mov     [rax+1Ch], r10d
0x180002fb2  mov     rax, [r11]
  ... truncated ...
```
