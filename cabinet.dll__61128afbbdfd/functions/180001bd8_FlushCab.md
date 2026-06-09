# FlushCab

- ea: `0x180001bd8`
- end: `0x180002396`
- name: `FlushCab`
- size: `1982`
- prototype: `__int64 __fastcall(int, int, int, int, size_t)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180001b40`
- `0x1800039b8`

## callees

- `0x180001674`
- `0x1800018e4`
- `0x180001bd8`
- `0x18000239c`
- `0x180002cfc`
- `0x180004700`
- `0x180011324`
- `0x180014dc0`
- `0x18001562a`
- `0x180016c44`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall FlushCab(
        __int64 a1,
        unsigned int (__fastcall *a2)(__int64, __int64, _QWORD, __int64),
        _DWORD *a3,
        unsigned int a4,
        size_t a5)
{
  char *v5; // r8
  char *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdx
  char *v10; // rax
  __int64 (__fastcall *v11)(char *, __int64, __int64, unsigned int *, size_t); // rax
  __int64 v12; // rsi
  _DWORD *v13; // rcx
  unsigned int v14; // eax
  _DWORD *v15; // r13
  unsigned int v16; // r12d
  int v17; // ebx
  int v18; // r15d
  unsigned int v19; // r11d
  unsigned int v20; // ecx
  int v21; // eax
  bool v22; // sf
  unsigned int v23; // edx
  __int16 v24; // ax
  size_t *v25; // r8
  _DWORD *v26; // rcx
  unsigned int v27; // eax
  unsigned int (__fastcall *v28)(__int64, __int64, __int64, unsigned int *); // rax
  _DWORD *v29; // rcx
  unsigned int v30; // eax
  unsigned __int16 i; // bx
  unsigned __int16 v32; // r15
  unsigned __int16 (__fastcall *v33)(__int64, __int64, _QWORD, unsigned int *); // rax
  unsigned int v34; // r10d
  size_t *v35; // r8
  __int64 v36; // rcx
  unsigned int (__fastcall *v37)(__int64, _QWORD, _QWORD, unsigned int *, size_t); // rax
  __int64 v38; // r8
  __int64 v39; // rcx
  __int64 (__fastcall *v40)(__int64, _DWORD *, __int64, unsigned int *, size_t); // rax
  unsigned int v41; // eax
  unsigned int v42; // ebx
  unsigned int (__fastcall *v43)(__int64, _DWORD *, _QWORD, unsigned int *, size_t); // rax
  _DWORD *v44; // r15
  unsigned int (__fastcall *v45)(__int64, __int64, _QWORD, __int64); // r12
  unsigned int v46; // ebx
  __int64 (__fastcall *v47)(__int64, _QWORD, __int64, unsigned int *, size_t); // rax
  unsigned int v48; // ebx
  unsigned int (__fastcall *v49)(__int64, _QWORD, _QWORD, unsigned int *, size_t); // rax
  __int64 (__fastcall *v50)(__int64, unsigned int *, size_t); // rax
  int v51; // eax
  unsigned int v52; // eax
  __int64 v53; // rax
  __int64 v55; // rax
  void (__fastcall *v56)(__int64, unsigned int *, size_t); // rax
  void (__fastcall *v57)(char *, unsigned int *, size_t); // rax
  size_t cchToCopy; // [rsp+20h] [rbp-E0h]
  size_t cchToCopya; // [rsp+20h] [rbp-E0h]
  unsigned int v60; // [rsp+40h] [rbp-C0h] BYREF
  size_t pcbLength; // [rsp+48h] [rbp-B8h] BYREF
  size_t v62; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v63; // [rsp+58h] [rbp-A8h]
  __int64 v64; // [rsp+60h] [rbp-A0h]
  _DWORD *v65; // [rsp+68h] [rbp-98h]
  unsigned int (__fastcall *v66)(__int64, __int64, _QWORD, __int64); // [rsp+70h] [rbp-90h]
  char pszDest[256]; // [rsp+80h] [rbp-80h] BYREF

  v65 = a3;
  v66 = a2;
  v5 = (char *)(a1 + 1466);
  v63 = a4;
  v60 = 0;
  pcbLength = 0;
  v7 = pszDest;
  v62 = 0;
  v8 = 2147483646;
  v9 = 256;
  do
  {
    if ( !v8 )
      break;
    if ( !*v5 )
      break;
    *v7++ = *v5++;
    --v8;
    --v9;
  }
  while ( v9 );
  v10 = v7 - 1;
  if ( v9 )
    v10 = v7;
  *v10 = 0;
  StringCchCatA(pszDest, 0x100u, (STRSAFE_LPCSTR)(a1 + 1210));
  v11 = *(__int64 (__fastcall **)(char *, __int64, __int64, unsigned int *, size_t))(a1 + 40);
  v60 = 0;
  v12 = v11(pszDest, 33538, 384, &v60, a5);
  if ( v12 != -1 )
  {
    v64 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 24))(*(unsigned int *)(a1 + 2844));
    v15 = (_DWORD *)v64;
    if ( !v64 )
      goto LABEL_64;
    v16 = *(_DWORD *)(a1 + 2840);
    v17 = a1 + 3115;
    if ( *(_BYTE *)(a1 + 3115) )
    {
      *(_WORD *)(a1 + 2558) |= 1u;
      if ( StringCbLengthA((STRSAFE_PCNZCH)(a1 + 3115), 0x101u, &pcbLength) < 0
        || StringCbLengthA((STRSAFE_PCNZCH)(a1 + 3372), 0x101u, &v62) < 0 )
      {
        return 0;
      }
      v16 += pcbLength + v62 + 2;
    }
    v18 = a1 + 4143;
    v19 = 0;
    if ( *(_BYTE *)(a1 + 4143) )
    {
      *(_WORD *)(a1 + 2558) |= 2u;
      if ( StringCbLengthA((STRSAFE_PCNZCH)(a1 + 4143), 0x101u, &pcbLength) < 0
        || StringCbLengthA((STRSAFE_PCNZCH)(a1 + 4400), 0x101u, &v62) < 0 )
      {
        return 0;
      }
      v16 += v62 + pcbLength + 2;
    }
    v20 = v16 + *(_DWORD *)(a1 + 648);
    if ( v16 > v20
      || (*(_DWORD *)(a1 + 2544) = v20, v21 = *(_DWORD *)(a1 + 376), v20 > v21 + v20)
      || (v22 = (int)(*(_DWORD *)(a1 + 104) + v21 + v20) < 0,
          v23 = *(_DWORD *)(a1 + 104) + v21 + v20,
          *(_DWORD *)(a1 + 2536) = v23,
          v22)
      || v23 < v21 + v20 )
    {
      v55 = *(_QWORD *)(a1 + 88);
      *(_QWORD *)v55 = 9;
      *(_DWORD *)(v55 + 8) = 1;
    }
    else
    {
      if ( *(_DWORD *)(a1 + 2836) > v19 )
        *(_WORD *)(a1 + 2558) |= 4u;
      *(_WORD *)(a1 + 2560) = *(_WORD *)(a1 + 2854);
      v24 = *(_WORD *)(a1 + 2856);
      *(_WORD *)(a1 + 2562) = v24;
      v60 = v19;
      *(_WORD *)(a1 + 2856) = v24 + 1;
      cchToCopy = a5;
      if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64, unsigned int *))(a1 + 56))(
             v12,
             a1 + 2528,
             36,
             &v60) != 36 )
      {
LABEL_25:
        v26 = *(_DWORD **)(a1 + 88);
        v27 = v60;
        *v26 = 6;
        v26[1] = v27;
        v26[2] = 1;
        goto LABEL_63;
      }
      if ( *(_DWORD *)(a1 + 2836) )
      {
        *(_WORD *)(a1 + 2580) = *(_WORD *)(a1 + 928);
        *(_BYTE *)(a1 + 2582) = *(_BYTE *)(a1 + 932);
        *(_BYTE *)(a1 + 2583) = *(_BYTE *)(a1 + 936);
        v28 = *(unsigned int (__fastcall **)(__int64, __int64, __int64, unsigned int *))(a1 + 56);
        v60 = 0;
        cchToCopy = a5;
        if ( v28(v12, a1 + 2580, 4, &v60) != 4 )
        {
LABEL_28:
          v29 = *(_DWORD **)(a1 + 88);
LABEL_29:
          v30 = v60;
          *v29 = 6;
LABEL_30:
          v29[1] = v30;
          v29[2] = 1;
          goto LABEL_63;
        }
        memset_0((void *)(a1 + 2580), 0, 0x100u);
        for ( i = *(_WORD *)(a1 + 2836) - 4; i; i -= v32 )
        {
          v32 = 256;
          if ( i <= 0x100u )
            v32 = i;
          v33 = *(unsigned __int16 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(a1 + 56);
          v60 = 0;
          cchToCopy = a5;
          if ( v32 != v33(v12, a1 + 2580, v32, &v60) )
            goto LABEL_25;
        }
        v15 = (_DWORD *)v64;
        v17 = a1 + 3115;
        v18 = a1 + 4143;
      }
      if ( ((*(_BYTE *)(a1 + 2558) & 1) == 0
         || (unsigned int)WritePsz(v12, v17, *(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 88), a5)
         && (unsigned int)WritePsz(v12, (int)a1 + 3372, *(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 88), a5))
        && ((*(_BYTE *)(a1 + 2558) & 2) == 0
         || (unsigned int)WritePsz(v12, v18, *(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 88), a5)
         && (unsigned int)WritePsz(v12, (int)a1 + 4400, *(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 88), a5)) )
      {
        *(_BYTE *)(a1 + 4143) = 0;
        *(_BYTE *)(a1 + 4400) = 0;
        StringCopyWorkerA((STRSAFE_LPSTR)(a1 + 3115), 0x101u, v25, (STRSAFE_PCNZCH)(a1 + 3629), cchToCopy);
        StringCopyWorkerA((STRSAFE_LPSTR)(a1 + 3372), v34, v35, (STRSAFE_PCNZCH)(a1 + 3886), cchToCopya);
        v36 = *(_QWORD *)(a1 + 656);
        v37 = *(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, unsigned int *, size_t))(a1 + 72);
        v60 = 0;
        if ( v37(v36, 0, 0, &v60, a5) == -1 )
        {
          v29 = *(_DWORD **)(a1 + 88);
LABEL_46:
          v30 = v60;
          *v29 = 4;
          goto LABEL_30;
        }
        while ( 1 )
        {
          v38 = *(unsigned int *)(a1 + 2844);
          v39 = *(_QWORD *)(a1 + 656);
          v40 = *(__int64 (__fastcall **)(__int64, _DWORD *, __int64, unsigned int *, size_t))(a1 + 48);
          v60 = 0;
          v41 = v40(v39, v15, v38, &v60, a5);
          if ( *(_DWORD *)(a1 + 2844) != v41 )
            break;
          *v15 += v16 + *(_DWORD *)(a1 + 376) + *(_DWORD *)(a1 + 648);
          v42 = *(_DWORD *)(a1 + 2844);
          v43 = *(unsigned int (__fastcall **)(__int64, _DWORD *, _QWORD, unsigned int *, size_t))(a1 + 56);
          v60 = 0;
          if ( v42 != v43(v12, v15, v42, &v60, a5) )
            goto LABEL_28;
        }
        v29 = *(_DWORD **)(a1 + 88);
        if ( *(_DWORD *)(a1 + 2844) < v41 )
          goto LABEL_46;
        v44 = v65;
        v45 = v66;
        v46 = v63;
        if ( (unsigned int)filecopy(v12, *(_QWORD *)(a1 + 384), v66, v65, v63, a5, a1, *(_DWORD **)(a1 + 88))
          && (unsigned int)filecopy(v12, *(_QWORD *)(a1 + 112), v45, v44, v46, a5, a1, *(_DWORD **)(a1 + 88)) )
        {
          v47 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, unsigned int *, size_t))(a1 + 72);
          v60 = 0;
          v48 = v47(v12, 0, 2, &v60, a5);
          if ( v48 == -1 )
            goto LABEL_28;
          v49 = *(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, unsigned int *, size_t))(a1 + 72);
          v60 = 0;
          *(_DWORD *)(a1 + 2528) = 1178817357;
          if ( v49(v12, 0, 0, &v60, a5) == -1
            || (*(unsigned int (__fastcall **)(__int64, __int64, __int64, unsigned int *, size_t))(a1 + 56))(
                 v12,
                 a1 + 2528,
                 4,
                 &v60,
                 a5) != 4 )
          {
            goto LABEL_28;
          }
          v50 = *(__int64 (__fastcall **)(__int64, unsigned int *, size_t))(a1 + 64);
          v60 = 0;
          v51 = v50(v12, &v60, a5);
          v29 = *(_DWORD **)(a1 + 88);
          v12 = -1;
          if ( v51 == -1 )
            goto LABEL_29;
          if ( (unsigned int)DeleteTempFiles(
                               a1 + 104,
                               3,
                               *(unsigned int (__fastcall **)(__int64, int *, __int64))(a1 + 64),
                               *(unsigned int (__fastcall **)(__int64, int *, __int64))(a1 + 80),
                               v29,
                               a5)
            && (unsigned int)CrTempFiles(
                               a1 + 104,
                               3,
                               *(__int64 (__fastcall **)(__int64, __int64, __int64, int *, __int64))(a1 + 40),
                               *(void (__fastcall **)(__int64, int *, __int64))(a1 + 64),
                               *(void (__fastcall **)(__int64, int *, __int64))(a1 + 80),
                               *(unsigned int (__fastcall **)(__int64, __int64, __int64))(a1 + 16),
                               *(_DWORD **)(a1 + 88),
                               a5) )
          {
            v52 = v45(2, *(unsigned int *)(a1 + 96), v48, a5);
            if ( v52 != -1 )
            {
              *(_DWORD *)(a1 + 920) -= v52;
              *(_QWORD *)(a1 + 2528) = 1111573281;
              *(_QWORD *)(a1 + 2536) = 0;
              *(_QWORD *)(a1 + 2552) = 259;
              *(_QWORD *)(a1 + 2544) = 0;
              (*(void (__fastcall **)(_DWORD *))(a1 + 32))(v15);
              return 1;
            }
            v53 = *(_QWORD *)(a1 + 88);
            *(_QWORD *)v53 = 7;
            *(_DWORD *)(v53 + 8) = 1;
          }
        }
      }
    }
LABEL_63:
    (*(void (__fastcall **)(__int64))(a1 + 32))(v64);
    if ( v12 == -1 )
      return 0;
LABEL_64:
    v56 = *(void (__fastcall **)(__int64, unsigned int *, size_t))(a1 + 64);
    v60 = 0;
    v56(v12, &v60, a5);
    v57 = *(void (__fastcall **)(char *, unsigned int *, size_t))(a1 + 80);
    v60 = 0;
    v57(pszDest, &v60, a5);
    return 0;
  }
  v13 = *(_DWORD **)(a1 + 88);
  v14 = v60;
  *v13 = 6;
  v13[1] = v14;
  v13[2] = 1;
  return 0;
}

```

## disassembly

```asm
0x180001bd8  mov     [rsp-8+arg_18], rbx
0x180001bdd  push    rbp
0x180001bde  push    rsi
0x180001bdf  push    rdi
0x180001be0  push    r12
0x180001be2  push    r13
0x180001be4  push    r14
0x180001be6  push    r15
0x180001be8  lea     rbp, [rsp-90h]
0x180001bf0  sub     rsp, 190h
0x180001bf7  mov     rax, cs:__security_cookie
0x180001bfe  xor     rax, rsp
0x180001c01  mov     [rbp+0C0h+var_40], rax
0x180001c08  mov     r14, [rbp+0C0h+arg_20]
0x180001c0f  xor     r15d, r15d
0x180001c12  mov     [rsp+1C0h+var_158], r8
0x180001c17  mov     r10d, 100h
0x180001c1d  mov     [rsp+1C0h+var_150], rdx
0x180001c22  lea     r8, [rcx+5BAh]
0x180001c29  mov     rdi, rcx
0x180001c2c  mov     [rsp+1C0h+var_168], r9d
0x180001c31  lea     ebx, [r15+1]
0x180001c35  mov     [rsp+1C0h+var_180], r15d
0x180001c3a  mov     [rsp+1C0h+pcbLength], r15
0x180001c3f  lea     rcx, [rbp+0C0h+pszDest]
0x180001c43  mov     [rsp+1C0h+var_170], r15
0x180001c48  mov     eax, 7FFFFFFEh
0x180001c4d  mov     edx, r10d
0x180001c50  test    rax, rax
0x180001c53  jz      short loc_180001C6E
0x180001c55  mov     r9b, [r8]
0x180001c58  test    r9b, r9b
0x180001c5b  jz      short loc_180001C6E
0x180001c5d  mov     [rcx], r9b
0x180001c60  add     r8, rbx
0x180001c63  add     rcx, rbx
0x180001c66  sub     rax, rbx
0x180001c69  sub     rdx, rbx
0x180001c6c  jnz     short loc_180001C50
0x180001c6e  test    rdx, rdx
0x180001c71  lea     rax, [rcx-1]
0x180001c75  lea     r8, [rdi+4BAh]; pszSrc
0x180001c7c  mov     rdx, r10; cchDest
0x180001c7f  cmovnz  rax, rcx
0x180001c83  lea     rcx, [rbp+0C0h+pszDest]; pszDest
0x180001c87  mov     [rax], r15b
0x180001c8a  call    StringCchCatA
0x180001c8f  mov     rax, [rdi+28h]
0x180001c93  lea     r9, [rsp+1C0h+var_180]
0x180001c98  mov     edx, 8302h
0x180001c9d  mov     [rsp+1C0h+var_180], r15d
0x180001ca2  mov     r8d, 180h
0x180001ca8  mov     [rsp+1C0h+cchToCopy], r14
0x180001cad  lea     rcx, [rbp+0C0h+pszDest]
0x180001cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cb6  mov     rsi, rax
0x180001cb9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001cbd  jnz     short loc_180001CD8
0x180001cbf  mov     rcx, [rdi+58h]
0x180001cc3  mov     eax, [rsp+1C0h+var_180]
0x180001cc7  mov     dword ptr [rcx], 6
0x180001ccd  mov     [rcx+4], eax
0x180001cd0  mov     [rcx+8], ebx
0x180001cd3  jmp     loc_18000236A
0x180001cd8  mov     ecx, [rdi+0B1Ch]
0x180001cde  mov     rax, [rdi+18h]
0x180001ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ce7  mov     [rsp+1C0h+var_160], rax
0x180001cec  mov     r13, rax
0x180001cef  test    rax, rax
0x180001cf2  jz      loc_180002337
0x180001cf8  mov     r12d, [rdi+0B18h]
0x180001cff  lea     rbx, [rdi+0C2Bh]
0x180001d06  cmp     [rbx], r15b
0x180001d09  jz      short loc_180001D62
0x180001d0b  mov     eax, 1
0x180001d10  lea     r8, [rsp+1C0h+pcbLength]; pcbLength
0x180001d15  or      [rdi+9FEh], ax
0x180001d1c  mov     edx, 101h; cbMax
0x180001d21  mov     rcx, rbx; psz
0x180001d24  call    StringCbLengthA
0x180001d29  test    eax, eax
0x180001d2b  js      loc_18000236A
0x180001d31  lea     rcx, [rdi+0D2Ch]; psz
0x180001d38  mov     edx, 101h; cbMax
0x180001d3d  lea     r8, [rsp+1C0h+var_170]; pcbLength
0x180001d42  call    StringCbLengthA
0x180001d47  test    eax, eax
0x180001d49  js      loc_18000236A
0x180001d4f  mov     ecx, dword ptr [rsp+1C0h+pcbLength]
0x180001d53  add     ecx, r12d
0x180001d56  mov     r12d, dword ptr [rsp+1C0h+var_170]
0x180001d5b  add     r12d, 2
0x180001d5f  add     r12d, ecx
0x180001d62  lea     r15, [rdi+102Fh]
0x180001d69  xor     r11d, r11d
0x180001d6c  mov     eax, 2
0x180001d71  cmp     [r15], r11b
0x180001d74  jz      short loc_180001DC3
0x180001d76  or      [rdi+9FEh], ax
0x180001d7d  lea     r8, [rsp+1C0h+pcbLength]; pcbLength
0x180001d82  mov     edx, 101h; cbMax
0x180001d87  mov     rcx, r15; psz
0x180001d8a  call    StringCbLengthA
0x180001d8f  test    eax, eax
0x180001d91  js      loc_18000236A
0x180001d97  lea     rcx, [rdi+1130h]; psz
0x180001d9e  mov     edx, 101h; cbMax
0x180001da3  lea     r8, [rsp+1C0h+var_170]; pcbLength
0x180001da8  call    StringCbLengthA
0x180001dad  test    eax, eax
0x180001daf  js      loc_18000236A
0x180001db5  mov     ecx, dword ptr [rsp+1C0h+pcbLength]
0x180001db9  add     ecx, 2
0x180001dbc  add     ecx, dword ptr [rsp+1C0h+var_170]
0x180001dc0  add     r12d, ecx
0x180001dc3  mov     ecx, [rdi+288h]
0x180001dc9  add     ecx, r12d
0x180001dcc  cmp     r12d, ecx
0x180001dcf  ja      loc_18000230E
0x180001dd5  mov     [rdi+9F0h], ecx
0x180001ddb  mov     eax, [rdi+178h]
0x180001de1  lea     r8d, [rax+rcx]
0x180001de5  cmp     ecx, r8d
0x180001de8  ja      loc_18000230E
0x180001dee  lea     edx, [rax+rcx]
0x180001df1  add     edx, [rdi+68h]
0x180001df4  mov     [rdi+9E8h], edx
0x180001dfa  js      loc_18000230E
0x180001e00  cmp     edx, r8d
0x180001e03  jb      loc_18000230E
0x180001e09  mov     eax, 4
0x180001e0e  cmp     [rdi+0B14h], r11d
0x180001e15  jbe     short loc_180001E1E
0x180001e17  or      [rdi+9FEh], ax
0x180001e1e  movzx   eax, word ptr [rdi+0B26h]
0x180001e25  lea     rdx, [rdi+9E0h]
0x180001e2c  mov     [rdi+0A00h], ax
0x180001e33  lea     r9, [rsp+1C0h+var_180]
0x180001e38  movzx   eax, word ptr [rdi+0B28h]
0x180001e3f  mov     r8d, 24h ; '$'
0x180001e45  mov     [rdi+0A02h], ax
0x180001e4c  mov     rcx, rsi
0x180001e4f  inc     ax
0x180001e52  mov     [rsp+1C0h+var_180], r11d
0x180001e57  mov     [rdi+0B28h], ax
0x180001e5e  mov     rax, [rdi+38h]
0x180001e62  mov     [rsp+1C0h+cchToCopy], r14
0x180001e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e6c  cmp     eax, 24h ; '$'
0x180001e6f  jz      short loc_180001E8E
0x180001e71  mov     rcx, [rdi+58h]
0x180001e75  mov     eax, [rsp+1C0h+var_180]
0x180001e79  mov     dword ptr [rcx], 6
0x180001e7f  mov     [rcx+4], eax
0x180001e82  mov     dword ptr [rcx+8], 1
0x180001e89  jmp     loc_180002320
0x180001e8e  cmp     dword ptr [rdi+0B14h], 0
0x180001e95  jbe     loc_180001F85
0x180001e9b  movzx   eax, word ptr [rdi+3A0h]
0x180001ea2  lea     r13, [rdi+0A14h]
0x180001ea9  mov     [r13+0], ax
0x180001eae  lea     r9, [rsp+1C0h+var_180]
0x180001eb3  mov     al, [rdi+3A4h]
0x180001eb9  xor     r15d, r15d
0x180001ebc  mov     [r13+2], al
0x180001ec0  mov     rdx, r13
0x180001ec3  mov     al, [rdi+3A8h]
0x180001ec9  mov     rcx, rsi
0x180001ecc  mov     [r13+3], al
0x180001ed0  mov     rax, [rdi+38h]
0x180001ed4  lea     ebx, [r15+4]
0x180001ed8  mov     r8d, ebx
0x180001edb  mov     [rsp+1C0h+var_180], r15d
0x180001ee0  mov     [rsp+1C0h+cchToCopy], r14
0x180001ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001eea  cmp     eax, ebx
0x180001eec  jz      short loc_180001F0B
0x180001eee  mov     rcx, [rdi+58h]
0x180001ef2  mov     eax, [rsp+1C0h+var_180]
0x180001ef6  mov     dword ptr [rcx], 6
0x180001efc  mov     [rcx+4], eax
0x180001eff  mov     dword ptr [rcx+8], 1
0x180001f06  jmp     loc_180002323
0x180001f0b  xor     edx, edx; Val
0x180001f0d  mov     r8d, 100h; Size
0x180001f13  mov     rcx, r13; void *
0x180001f16  call    memset_0
0x180001f1b  movzx   ebx, word ptr [rdi+0B14h]
0x180001f22  sub     bx, 4
0x180001f26  test    bx, bx
0x180001f29  jz      short loc_180001F72
0x180001f2b  mov     eax, 100h
0x180001f30  movzx   r15d, ax
0x180001f34  cmp     bx, ax
0x180001f37  ja      short loc_180001F3D
0x180001f39  movzx   r15d, bx
0x180001f3d  mov     rax, [rdi+38h]
0x180001f41  lea     r9, [rsp+1C0h+var_180]
0x180001f46  movzx   r8d, r15w
0x180001f4a  mov     rdx, r13
0x180001f4d  mov     rcx, rsi
0x180001f50  mov     [rsp+1C0h+var_180], 0
0x180001f58  mov     [rsp+1C0h+cchToCopy], r14
0x180001f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f62  cmp     r15w, ax
0x180001f66  jnz     loc_180001E71
0x180001f6c  sub     bx, r15w
0x180001f70  jmp     short loc_180001F26
0x180001f72  mov     r13, [rsp+1C0h+var_160]
0x180001f77  lea     rbx, [rdi+0C2Bh]
0x180001f7e  lea     r15, [rdi+102Fh]
0x180001f85  test    byte ptr [rdi+9FEh], 1
0x180001f8c  jz      short loc_180001FD2
0x180001f8e  mov     r9, [rdi+58h]
0x180001f92  mov     rdx, rbx
0x180001f95  mov     r8, [rdi+38h]
0x180001f99  mov     rcx, rsi
0x180001f9c  mov     [rsp+1C0h+cchToCopy], r14
0x180001fa1  call    WritePsz
0x180001fa6  test    eax, eax
0x180001fa8  jz      loc_180002320
0x180001fae  mov     r9, [rdi+58h]
0x180001fb2  lea     rdx, [rdi+0D2Ch]
0x180001fb9  mov     r8, [rdi+38h]
0x180001fbd  mov     rcx, rsi
0x180001fc0  mov     [rsp+1C0h+cchToCopy], r14; cchToCopy
0x180001fc5  call    WritePsz
0x180001fca  test    eax, eax
0x180001fcc  jz      loc_180002320
0x180001fd2  test    byte ptr [rdi+9FEh], 2
0x180001fd9  jz      short loc_180002023
0x180001fdb  mov     r9, [rdi+58h]
0x180001fdf  mov     rdx, r15
0x180001fe2  mov     r8, [rdi+38h]
0x180001fe6  mov     rcx, rsi
0x180001fe9  mov     [rsp+1C0h+cchToCopy], r14
0x180001fee  call    WritePsz
0x180001ff3  xor     r15d, r15d
0x180001ff6  test    eax, eax
0x180001ff8  jz      loc_180002323
0x180001ffe  mov     r9, [rdi+58h]
0x180002002  lea     rdx, [rdi+1130h]
0x180002009  mov     r8, [rdi+38h]
0x18000200d  mov     rcx, rsi
0x180002010  mov     [rsp+1C0h+cchToCopy], r14
0x180002015  call    WritePsz
0x18000201a  test    eax, eax
0x18000201c  jnz     short loc_180002026
0x18000201e  jmp     loc_180002323
0x180002023  xor     r15d, r15d
0x180002026  mov     r10d, 101h
0x18000202c  mov     [rdi+102Fh], r15b
0x180002033  mov     edx, r10d; cchDest
0x180002036  mov     [rdi+1130h], r15b
0x18000203d  lea     r9, [rdi+0E2Dh]; pszSrc
0x180002044  lea     rcx, [rdi+0C2Bh]; pszDest
0x18000204b  call    StringCopyWorkerA
0x180002050  lea     r9, [rdi+0F2Eh]; pszSrc
0x180002057  mov     edx, r10d; cchDest
0x18000205a  lea     rcx, [rdi+0D2Ch]; pszDest
0x180002061  call    StringCopyWorkerA
0x180002066  mov     rcx, [rdi+290h]
0x18000206d  lea     r9, [rsp+1C0h+var_180]
0x180002072  mov     rax, [rdi+48h]
0x180002076  xor     r8d, r8d
0x180002079  xor     edx, edx
0x18000207b  mov     [rsp+1C0h+var_180], r15d
0x180002080  mov     [rsp+1C0h+cchToCopy], r14
0x180002085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000208a  cmp     eax, 0FFFFFFFFh
0x18000208d  jnz     short loc_1800020A2
0x18000208f  mov     rcx, [rdi+58h]
0x180002093  mov     eax, [rsp+1C0h+var_180]
0x180002097  mov     dword ptr [rcx], 4
0x18000209d  jmp     loc_180001EFC
0x1800020a2  mov     r8d, [rdi+0B1Ch]
0x1800020a9  lea     r9, [rsp+1C0h+var_180]
0x1800020ae  mov     rcx, [rdi+290h]
0x1800020b5  mov     rdx, r13
0x1800020b8  mov     rax, [rdi+30h]
0x1800020bc  mov     [rsp+1C0h+var_180], r15d
0x1800020c1  mov     [rsp+1C0h+cchToCopy], r14
0x1800020c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020cb  cmp     [rdi+0B1Ch], eax
0x1800020d1  jnz     short loc_180002116
0x1800020d3  mov     eax, [rdi+288h]
0x1800020d9  lea     r9, [rsp+1C0h+var_180]
0x1800020de  add     eax, [rdi+178h]
0x1800020e4  mov     rdx, r13
0x1800020e7  add     eax, r12d
0x1800020ea  mov     [rsp+1C0h+cchToCopy], r14
0x1800020ef  add     [r13+0], eax
0x1800020f3  mov     rcx, rsi
0x1800020f6  mov     ebx, [rdi+0B1Ch]
0x1800020fc  mov     r8d, ebx
0x1800020ff  mov     rax, [rdi+38h]
0x180002103  mov     [rsp+1C0h+var_180], r15d
0x180002108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000210d  cmp     ebx, eax
  ... truncated ...
```
