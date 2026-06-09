# UnifyICNRLinkInfo(ushort const *,ulong,ushort const *,ulong,tagICNRLINKW * *,uint *)

- ea: `0x180004b50`
- end: `0x180004e90`
- name: `?UnifyICNRLinkInfo@@YAHPEBGK0KPEAPEAUtagICNRLINKW@@PEAI@Z`
- size: `832`
- prototype: `__int64 __fastcall(WCHAR *lpString, int, WCHAR *, int, struct tagICNRLINKW **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180001f10`
- `0x180002500`

## callees

- `0x180003050`
- `0x180003610`
- `0x180004b50`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180004d07`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180004d23`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180004d07`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180004d23`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180004c3b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180004ce2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180004c3b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180004ce2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004c1f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004cc8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004c1f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004cc8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180004bdf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180004c87`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180004bdf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180004c87`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004d72`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004d72`

## pseudocode

```c
__int64 __fastcall UnifyICNRLinkInfo(
        WCHAR *lpString,
        int a2,
        WCHAR *a3,
        int a4,
        struct tagICNRLINKW **a5,
        unsigned int *a6)
{
  char v7; // r13
  unsigned int v9; // ebx
  int v10; // edi
  int v11; // r13d
  unsigned int v12; // esi
  unsigned int v13; // r12d
  unsigned int v14; // r15d
  unsigned int v15; // ecx
  struct tagICNRLINKW *v16; // rax
  _DWORD *v17; // rax
  int v18; // r10d
  int v19; // r11d
  int v20; // r10d
  int v21; // r10d
  int v22; // r10d
  _DWORD *v23; // r11
  int v25; // [rsp+40h] [rbp-C0h]
  unsigned int v26; // [rsp+44h] [rbp-BCh]
  CHAR MultiByteStr[272]; // [rsp+70h] [rbp-90h] BYREF
  CHAR lpMultiByteStr[272]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR WideCharStr[264]; // [rsp+290h] [rbp+190h] BYREF

  v7 = a2;
  v26 = WideCharToMultiByte(0, 0, lpString, -1, MultiByteStr, 260, 0, 0);
  v9 = 1;
  if ( !v26 )
  {
    MultiByteStr[0] = 0;
    v26 = 1;
LABEL_5:
    v10 = 1;
    goto LABEL_6;
  }
  if ( !MultiByteToWideChar(0, 0, MultiByteStr, -1, WideCharStr, 260) )
    goto LABEL_5;
  v10 = 0;
  if ( lstrcmpW(lpString, WideCharStr) )
    goto LABEL_5;
LABEL_6:
  v11 = v7 & 1;
  if ( v11 )
  {
    v12 = WideCharToMultiByte(0, 0, a3, -1, lpMultiByteStr, 260, 0, 0);
    if ( !v12 )
    {
      v10 = 1;
      lpMultiByteStr[0] = 0;
      v12 = 1;
      goto LABEL_14;
    }
    if ( !MultiByteToWideChar(0, 0, lpMultiByteStr, -1, WideCharStr, 260) || lstrcmpW(a3, WideCharStr) )
      v10 = 1;
  }
  else
  {
    v12 = 0;
  }
  if ( !v10 )
  {
    v25 = 20;
    v13 = 0;
    goto LABEL_17;
  }
LABEL_14:
  v25 = 28;
  v13 = 2 * lstrlenW(lpString) + 2;
  if ( v11 )
  {
    v14 = 2 * lstrlenW(a3) + 2;
    goto LABEL_18;
  }
LABEL_17:
  v14 = 0;
LABEL_18:
  v15 = v12 + v26 + v25;
  *a6 = v15;
  if ( v10 )
  {
    v15 = v13 + v14 + ((v15 + 1) & 0xFFFFFFFE);
    *a6 = v15;
  }
  v16 = (struct tagICNRLINKW *)LocalAlloc(0x40u, v15);
  *a5 = v16;
  if ( v16 )
  {
    *(_DWORD *)v16 = *a6;
    *((_DWORD *)*a5 + 1) = a2;
    *((_DWORD *)*a5 + 4) = (a2 & 2) != 0 ? a4 : 0;
    *((_DWORD *)*a5 + 2) = v25;
    StringCbCopyA((char *)*a5 + *((unsigned int *)*a5 + 2), v26, MultiByteStr);
    v17 = *a5;
    v20 = v19 + v18;
    if ( v11 )
    {
      v17[3] = v20;
      StringCbCopyA((char *)*a5 + *((unsigned int *)*a5 + 3), v12, lpMultiByteStr);
      v20 = v12 + v21;
    }
    else
    {
      v17[3] = 0;
    }
    if ( v10 )
    {
      *((_DWORD *)*a5 + 5) = (v20 + 1) & 0xFFFFFFFE;
      StringCbCopyW((unsigned __int16 *)((char *)*a5 + *((unsigned int *)*a5 + 5)), v13, lpString);
      v23 = *a5;
      if ( v11 )
      {
        v23[6] = v22 + v13;
        StringCbCopyW((unsigned __int16 *)((char *)*a5 + *((unsigned int *)*a5 + 6)), v14, a3);
      }
      else
      {
        v23[6] = 0;
      }
    }
  }
  else
  {
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x180004b50  mov     [rsp-8+arg_8], rbx
0x180004b55  push    rbp
0x180004b56  push    rsi
0x180004b57  push    rdi
0x180004b58  push    r12
0x180004b5a  push    r13
0x180004b5c  push    r14
0x180004b5e  push    r15
0x180004b60  lea     rbp, [rsp-3B0h]
0x180004b68  sub     rsp, 4B0h
0x180004b6f  mov     rax, cs:__security_cookie
0x180004b76  xor     rax, rsp
0x180004b79  mov     [rbp+3E0h+var_40], rax
0x180004b80  mov     rax, [rbp+3E0h+arg_28]
0x180004b87  mov     r15, r8
0x180004b8a  mov     r14, [rbp+3E0h+arg_20]
0x180004b91  mov     r13d, edx
0x180004b94  mov     [rsp+4E0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180004b9d  mov     r12, rcx
0x180004ba0  mov     [rsp+4E0h+var_490], rax
0x180004ba5  mov     edi, 104h
0x180004baa  mov     [rsp+4E0h+var_480], r8
0x180004baf  lea     rax, [rsp+4E0h+MultiByteStr]
0x180004bb4  mov     [rsp+4E0h+var_494], r9d
0x180004bb9  mov     r8, rcx; lpWideCharStr
0x180004bbc  mov     dword ptr [rsp+4E0h+var_49C+4], edx
0x180004bc0  or      r9d, 0FFFFFFFFh; cchWideChar
0x180004bc4  mov     [rsp+4E0h+var_488], rcx
0x180004bc9  xor     edx, edx; dwFlags
0x180004bcb  mov     [rsp+4E0h+lpDefaultChar], 0; lpDefaultChar
0x180004bd4  xor     ecx, ecx; CodePage
0x180004bd6  mov     [rsp+4E0h+cbMultiByte], edi; cbMultiByte
0x180004bda  mov     [rsp+4E0h+lpMultiByteStr], rax; lpMultiByteStr
0x180004bdf  call    cs:__imp_WideCharToMultiByte
0x180004be6  nop     dword ptr [rax+rax+00h]
0x180004beb  mov     dword ptr [rsp+4E0h+var_49C], eax
0x180004bef  mov     ebx, 1
0x180004bf4  test    eax, eax
0x180004bf6  jnz     short loc_180004C02
0x180004bf8  mov     [rsp+4E0h+MultiByteStr], al
0x180004bfc  mov     dword ptr [rsp+4E0h+var_49C], ebx
0x180004c00  jmp     short loc_180004C4B
0x180004c02  lea     rax, [rbp+3E0h+WideCharStr]
0x180004c09  mov     [rsp+4E0h+cbMultiByte], edi; cchWideChar
0x180004c0d  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180004c11  mov     [rsp+4E0h+lpMultiByteStr], rax; lpWideCharStr
0x180004c16  lea     r8, [rsp+4E0h+MultiByteStr]; lpMultiByteStr
0x180004c1b  xor     edx, edx; dwFlags
0x180004c1d  xor     ecx, ecx; CodePage
0x180004c1f  call    cs:__imp_MultiByteToWideChar
0x180004c26  nop     dword ptr [rax+rax+00h]
0x180004c2b  test    eax, eax
0x180004c2d  jz      short loc_180004C4B
0x180004c2f  lea     rdx, [rbp+3E0h+WideCharStr]; lpString2
0x180004c36  mov     rcx, r12; lpString1
0x180004c39  xor     edi, edi
0x180004c3b  call    cs:__imp_lstrcmpW
0x180004c42  nop     dword ptr [rax+rax+00h]
0x180004c47  test    eax, eax
0x180004c49  jz      short loc_180004C4D
0x180004c4b  mov     edi, ebx
0x180004c4d  and     r13d, ebx
0x180004c50  jz      loc_180004CF6
0x180004c56  mov     [rsp+4E0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180004c5f  lea     rax, [rbp+3E0h+var_360]
0x180004c66  mov     [rsp+4E0h+lpDefaultChar], 0; lpDefaultChar
0x180004c6f  or      r9d, 0FFFFFFFFh; cchWideChar
0x180004c73  mov     [rsp+4E0h+cbMultiByte], 104h; cbMultiByte
0x180004c7b  mov     r8, r15; lpWideCharStr
0x180004c7e  xor     edx, edx; dwFlags
0x180004c80  mov     [rsp+4E0h+lpMultiByteStr], rax; lpMultiByteStr
0x180004c85  xor     ecx, ecx; CodePage
0x180004c87  call    cs:__imp_WideCharToMultiByte
0x180004c8e  nop     dword ptr [rax+rax+00h]
0x180004c93  mov     esi, eax
0x180004c95  test    eax, eax
0x180004c97  jnz     short loc_180004CA5
0x180004c99  mov     edi, ebx
0x180004c9b  mov     [rbp+3E0h+var_360], al
0x180004ca1  mov     esi, ebx
0x180004ca3  jmp     short loc_180004CFC
0x180004ca5  lea     rax, [rbp+3E0h+WideCharStr]
0x180004cac  mov     [rsp+4E0h+cbMultiByte], 104h; cchWideChar
0x180004cb4  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180004cb8  mov     [rsp+4E0h+lpMultiByteStr], rax; lpWideCharStr
0x180004cbd  lea     r8, [rbp+3E0h+var_360]; lpMultiByteStr
0x180004cc4  xor     edx, edx; dwFlags
0x180004cc6  xor     ecx, ecx; CodePage
0x180004cc8  call    cs:__imp_MultiByteToWideChar
0x180004ccf  nop     dword ptr [rax+rax+00h]
0x180004cd4  test    eax, eax
0x180004cd6  jz      short loc_180004CF2
0x180004cd8  lea     rdx, [rbp+3E0h+WideCharStr]; lpString2
0x180004cdf  mov     rcx, r15; lpString1
0x180004ce2  call    cs:__imp_lstrcmpW
0x180004ce9  nop     dword ptr [rax+rax+00h]
0x180004cee  test    eax, eax
0x180004cf0  jz      short loc_180004CF8
0x180004cf2  mov     edi, ebx
0x180004cf4  jmp     short loc_180004CF8
0x180004cf6  xor     esi, esi
0x180004cf8  test    edi, edi
0x180004cfa  jz      short loc_180004D39
0x180004cfc  mov     rcx, r12; lpString
0x180004cff  mov     [rsp+4E0h+var_4A0], 1Ch
0x180004d07  call    cs:__imp_lstrlenW
0x180004d0e  nop     dword ptr [rax+rax+00h]
0x180004d13  lea     r12d, ds:2[rax*2]
0x180004d1b  test    r13d, r13d
0x180004d1e  jz      short loc_180004D44
0x180004d20  mov     rcx, r15; lpString
0x180004d23  call    cs:__imp_lstrlenW
0x180004d2a  nop     dword ptr [rax+rax+00h]
0x180004d2f  lea     r15d, ds:2[rax*2]
0x180004d37  jmp     short loc_180004D47
0x180004d39  mov     [rsp+4E0h+var_4A0], 14h
0x180004d41  xor     r12d, r12d
0x180004d44  xor     r15d, r15d
0x180004d47  mov     eax, dword ptr [rsp+4E0h+var_49C]
0x180004d4b  mov     ecx, [rsp+4E0h+var_4A0]
0x180004d4f  add     eax, esi
0x180004d51  mov     rdx, [rsp+4E0h+var_490]
0x180004d56  add     ecx, eax
0x180004d58  mov     [rdx], ecx
0x180004d5a  test    edi, edi
0x180004d5c  jz      short loc_180004D6B
0x180004d5e  inc     ecx
0x180004d60  and     ecx, 0FFFFFFFEh
0x180004d63  add     ecx, r15d
0x180004d66  add     ecx, r12d
0x180004d69  mov     [rdx], ecx
0x180004d6b  mov     edx, ecx; uBytes
0x180004d6d  mov     ecx, 40h ; '@'; uFlags
0x180004d72  call    cs:__imp_LocalAlloc
0x180004d79  nop     dword ptr [rax+rax+00h]
0x180004d7e  mov     [r14], rax
0x180004d81  test    rax, rax
0x180004d84  jz      loc_180004E61
0x180004d8a  mov     rcx, [rsp+4E0h+var_490]
0x180004d8f  lea     r8, [rsp+4E0h+MultiByteStr]; char *
0x180004d94  mov     r10d, [rsp+4E0h+var_4A0]
0x180004d99  mov     r11d, dword ptr [rsp+4E0h+var_49C]
0x180004d9e  mov     edx, r11d; unsigned __int64
0x180004da1  mov     ecx, [rcx]
0x180004da3  mov     [rax], ecx
0x180004da5  mov     rax, [r14]
0x180004da8  mov     ecx, dword ptr [rsp+4E0h+var_49C+4]
0x180004dac  mov     [rax+4], ecx
0x180004daf  and     cl, 2
0x180004db2  mov     rax, [r14]
0x180004db5  neg     cl
0x180004db7  sbb     ecx, ecx
0x180004db9  and     ecx, [rsp+4E0h+var_494]
0x180004dbd  mov     [rax+10h], ecx
0x180004dc0  mov     rax, [r14]
0x180004dc3  mov     [rax+8], r10d
0x180004dc7  mov     rax, [r14]
0x180004dca  mov     ecx, [rax+8]
0x180004dcd  add     rcx, rax; char *
0x180004dd0  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180004dd5  mov     rax, [r14]
0x180004dd8  add     r10d, r11d
0x180004ddb  test    r13d, r13d
0x180004dde  jz      short loc_180004E00
0x180004de0  mov     [rax+0Ch], r10d
0x180004de4  lea     r8, [rbp+3E0h+var_360]; char *
0x180004deb  mov     rax, [r14]
0x180004dee  mov     edx, esi; unsigned __int64
0x180004df0  mov     ecx, [rax+0Ch]
0x180004df3  add     rcx, rax; char *
0x180004df6  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180004dfb  add     r10d, esi
0x180004dfe  jmp     short loc_180004E07
0x180004e00  mov     dword ptr [rax+0Ch], 0
0x180004e07  test    edi, edi
0x180004e09  jz      short loc_180004E63
0x180004e0b  mov     rax, [r14]
0x180004e0e  inc     r10d
0x180004e11  mov     r8, [rsp+4E0h+var_488]; unsigned __int16 *
0x180004e16  and     r10d, 0FFFFFFFEh
0x180004e1a  mov     edx, r12d; unsigned __int64
0x180004e1d  mov     [rax+14h], r10d
0x180004e21  mov     rax, [r14]
0x180004e24  mov     ecx, [rax+14h]
0x180004e27  add     rcx, rax; unsigned __int16 *
0x180004e2a  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180004e2f  mov     r11, [r14]
0x180004e32  test    r13d, r13d
0x180004e35  jz      short loc_180004E57
0x180004e37  mov     r8, [rsp+4E0h+var_480]; unsigned __int16 *
0x180004e3c  lea     eax, [r10+r12]
0x180004e40  mov     [r11+18h], eax
0x180004e44  mov     rax, [r14]
0x180004e47  mov     edx, r15d; unsigned __int64
0x180004e4a  mov     ecx, [rax+18h]
0x180004e4d  add     rcx, rax; unsigned __int16 *
0x180004e50  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180004e55  jmp     short loc_180004E63
0x180004e57  mov     dword ptr [r11+18h], 0
0x180004e5f  jmp     short loc_180004E63
0x180004e61  xor     ebx, ebx
0x180004e63  mov     eax, ebx
0x180004e65  mov     rcx, [rbp+3E0h+var_40]
0x180004e6c  xor     rcx, rsp; StackCookie
0x180004e6f  call    __security_check_cookie
0x180004e74  mov     rbx, [rsp+4E0h+arg_8]
0x180004e7c  add     rsp, 4B0h
0x180004e83  pop     r15
0x180004e85  pop     r14
0x180004e87  pop     r13
0x180004e89  pop     r12
0x180004e8b  pop     rdi
0x180004e8c  pop     rsi
0x180004e8d  pop     rbp
0x180004e8e  retn
```
