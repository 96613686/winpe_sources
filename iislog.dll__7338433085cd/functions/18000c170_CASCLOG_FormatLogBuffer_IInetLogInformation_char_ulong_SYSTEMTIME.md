# CASCLOG::FormatLogBuffer(IInetLogInformation *,char *,ulong *,_SYSTEMTIME *)

- ea: `0x18000c170`
- end: `0x18000c62c`
- name: `?FormatLogBuffer@CASCLOG@@UEAAHPEAVIInetLogInformation@@PEADPEAKPEAU_SYSTEMTIME@@@Z`
- size: `1212`
- prototype: `int(CASCLOG *__hidden this, struct IInetLogInformation *, char *, unsigned int *, struct _SYSTEMTIME *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800022a8`
- `0x18000c170`
- `0x18000c634`
- `0x18000ec56`
- `0x18000eca0`
- `0x180010010`

## import_xrefs

- `IisRTL!?SetLocalTime@ASCLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z` at `0x18000c287`
- `IisRTL!?SetLocalTime@ASCLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z` at `0x18000c287`
- `IisRTL!?GetFormattedDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEBU_SYSTEMTIME@@PEAD@Z` at `0x18000c29c`
- `IisRTL!?GetFormattedDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEBU_SYSTEMTIME@@PEAD@Z` at `0x18000c29c`
- `KERNEL32!SetLastError` at `0x18000c5ff`
- `KERNEL32!SetLastError` at `0x18000c5ff`

## pseudocode

```c
__int64 __fastcall CASCLOG::FormatLogBuffer(
        CASCLOG *this,
        struct IInetLogInformation *a2,
        char *a3,
        unsigned int *a4,
        struct _SYSTEMTIME *a5)
{
  char *v6; // rdi
  const char *v9; // rdx
  const char *v10; // r14
  unsigned int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rax
  char *v14; // rsi
  const char *v15; // rdx
  unsigned int v16; // eax
  unsigned int v17; // r15d
  __int64 v18; // rdi
  __int64 v19; // rbx
  unsigned int FormattedDateTime; // eax
  unsigned int v21; // ebx
  const char *v22; // rdx
  unsigned int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rdi
  const char *v26; // rdx
  unsigned int v27; // eax
  unsigned int v28; // ebx
  __int64 v29; // rdi
  const char *v30; // rdx
  unsigned int v31; // eax
  unsigned int v32; // ebx
  __int64 v33; // rdi
  unsigned int v34; // eax
  unsigned int v35; // r15d
  char *v36; // rbx
  unsigned int v37; // eax
  unsigned int v38; // r14d
  char *v39; // rbx
  unsigned int v40; // eax
  unsigned int v41; // esi
  char *v42; // rbx
  unsigned int v43; // eax
  unsigned int v44; // edi
  char *v45; // rbx
  unsigned int v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // ecx
  char *v49; // rbx
  unsigned int v50; // edi
  const char *v51; // rdx
  unsigned int v52; // eax
  unsigned int v53; // edi
  __int64 v54; // rax
  const char *v55; // rdx
  unsigned int v56; // eax
  unsigned int v57; // edi
  __int64 v58; // rax
  __int64 v59; // rax
  unsigned int v60; // ecx
  unsigned int v61; // edi
  __int64 v62; // rax
  size_t Size; // [rsp+20h] [rbp-58h] BYREF
  char *v64; // [rsp+28h] [rbp-50h] BYREF
  struct _SYSTEMTIME *v65; // [rsp+30h] [rbp-48h]
  unsigned int v66[2]; // [rsp+38h] [rbp-40h] BYREF
  char Src[32]; // [rsp+40h] [rbp-38h] BYREF

  v65 = a5;
  v6 = a3;
  *(_QWORD *)v66 = this;
  v64 = a3;
  LODWORD(Size) = 0;
  if ( !a3 )
    return 87;
  v9 = (const char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, size_t *))(*(_QWORD *)a2 + 40LL))(
                       a2,
                       0,
                       &Size);
  v10 = "-";
  v11 = Size;
  if ( !(_DWORD)Size )
  {
    v11 = 1;
    v9 = "-";
    LODWORD(Size) = 1;
  }
  v12 = v11 + 2;
  if ( v11 + 2 <= *a4 )
  {
    memcpy_0(v6, v9, v11);
    v13 = (unsigned int)Size;
    *(_WORD *)&v6[(unsigned int)Size] = 8236;
    v6 += v13 + 2;
    v64 = v6;
  }
  v14 = v6;
  v15 = (const char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, size_t *))(*(_QWORD *)a2 + 48LL))(
                        a2,
                        0,
                        &Size);
  v16 = Size;
  if ( !(_DWORD)Size )
  {
    v16 = 1;
    v15 = "-";
    LODWORD(Size) = 1;
  }
  v17 = v12 + v16 + 2;
  if ( v17 <= *a4 )
  {
    memcpy_0(v6, v15, v16);
    v18 = (unsigned int)Size + 2LL;
    *(_WORD *)&v14[(unsigned int)Size] = 8236;
    v6 = &v14[v18];
    v64 = v6;
    v14 = v6;
  }
  v19 = *(_QWORD *)v66;
  ASCLOG_DATETIME_CACHE::SetLocalTime((ASCLOG_DATETIME_CACHE *)(*(_QWORD *)v66 + 1576LL), v65);
  FormattedDateTime = CACHED_DATETIME_FORMATS::GetFormattedDateTime((CACHED_DATETIME_FORMATS *)(v19 + 1576), v65, Src);
  LODWORD(Size) = FormattedDateTime;
  v21 = v17 + FormattedDateTime;
  if ( v17 + FormattedDateTime <= *a4 )
  {
    memcpy_0(v14, Src, FormattedDateTime);
    v6 = &v14[(unsigned int)Size];
    v64 = v6;
    v14 = v6;
  }
  v22 = (const char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, size_t *))(*(_QWORD *)a2 + 24LL))(
                        a2,
                        0,
                        &Size);
  v23 = Size;
  if ( !(_DWORD)Size )
  {
    v23 = 1;
    v22 = "-";
    LODWORD(Size) = 1;
  }
  v24 = v23 + v21 + 2;
  if ( v24 <= *a4 )
  {
    memcpy_0(v14, v22, v23);
    v25 = (unsigned int)Size + 2LL;
    *(_WORD *)&v14[(unsigned int)Size] = 8236;
    v6 = &v14[v25];
    v64 = v6;
    v14 = v6;
  }
  v26 = (const char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, size_t *))(*(_QWORD *)a2 + 32LL))(
                        a2,
                        0,
                        &Size);
  v27 = Size;
  if ( !(_DWORD)Size )
  {
    v27 = 1;
    v26 = "-";
    LODWORD(Size) = 1;
  }
  v28 = v27 + v24 + 2;
  if ( v28 <= *a4 )
  {
    memcpy_0(v14, v26, v27);
    v29 = (unsigned int)Size + 2LL;
    *(_WORD *)&v14[(unsigned int)Size] = 8236;
    v6 = &v14[v29];
    v64 = v6;
    v14 = v6;
  }
  v30 = (const char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, size_t *))(*(_QWORD *)a2 + 56LL))(
                        a2,
                        0,
                        &Size);
  v31 = Size;
  if ( !(_DWORD)Size )
  {
    v31 = 1;
    v30 = "-";
    LODWORD(Size) = 1;
  }
  v32 = v31 + v28 + 2;
  LODWORD(v65) = v32;
  if ( v32 <= *a4 )
  {
    memcpy_0(v14, v30, v31);
    v33 = (unsigned int)Size + 2LL;
    *(_WORD *)&v14[(unsigned int)Size] = 8236;
    v6 = &v14[v33];
    v64 = v6;
    v14 = v6;
  }
  v66[0] = v32 + 10;
  if ( v32 + 60 > *a4 )
  {
    FormatLogDwords(a2, &v64, a4, v66);
    v49 = v64;
    v50 = v66[0];
  }
  else
  {
    v34 = (*(__int64 (__fastcall **)(struct IInetLogInformation *, const char *))(*(_QWORD *)a2 + 96LL))(a2, v30);
    v35 = FastDwToA(v6, v34);
    LODWORD(Size) = v35;
    v36 = &v14[v35 + 2];
    *(_WORD *)&v14[v35] = 8236;
    v37 = (*(__int64 (__fastcall **)(struct IInetLogInformation *))(*(_QWORD *)a2 + 112LL))(a2);
    v38 = FastDwToA(v36, v37);
    LODWORD(Size) = v38;
    *(_WORD *)&v36[v38] = 8236;
    v39 = &v36[v38];
    v40 = (*(__int64 (__fastcall **)(struct IInetLogInformation *))(*(_QWORD *)a2 + 104LL))(a2);
    v41 = FastDwToA(v39 + 2, v40);
    LODWORD(Size) = v41;
    *(_WORD *)&v39[v41 + 2] = 8236;
    v42 = &v39[v41 + 4];
    v43 = (*(__int64 (__fastcall **)(struct IInetLogInformation *))(*(_QWORD *)a2 + 128LL))(a2);
    v44 = FastDwToA(v42, v43);
    LODWORD(Size) = v44;
    *(_WORD *)&v42[v44] = 8236;
    v45 = &v42[v44];
    v46 = (*(__int64 (__fastcall **)(struct IInetLogInformation *))(*(_QWORD *)a2 + 120LL))(a2);
    v47 = FastDwToA(v45 + 2, v46);
    LODWORD(Size) = v47;
    v48 = v38 + v41 + v44 + v47 + (_DWORD)v65 + 10;
    *(_WORD *)&v45[v47 + 2] = 8236;
    v10 = "-";
    LODWORD(v65) = v35 + v48;
    v49 = &v45[v47 + 4];
    v50 = v35 + v48;
  }
  v51 = (const char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, size_t *))(*(_QWORD *)a2 + 64LL))(
                        a2,
                        0,
                        &Size);
  v52 = Size;
  if ( !(_DWORD)Size )
  {
    v52 = 1;
    v51 = "-";
    LODWORD(Size) = 1;
  }
  v53 = v52 + v50 + 2;
  if ( v53 <= *a4 )
  {
    memcpy_0(v49, v51, v52);
    v54 = (unsigned int)Size;
    *(_WORD *)&v49[(unsigned int)Size] = 8236;
    v49 += v54 + 2;
  }
  v55 = (const char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, size_t *))(*(_QWORD *)a2 + 72LL))(
                        a2,
                        0,
                        &Size);
  v56 = Size;
  if ( !(_DWORD)Size )
  {
    v56 = 1;
    v55 = "-";
    LODWORD(Size) = 1;
  }
  v57 = v56 + v53 + 2;
  if ( v57 <= *a4 )
  {
    memcpy_0(v49, v55, v56);
    v58 = (unsigned int)Size;
    *(_WORD *)&v49[(unsigned int)Size] = 8236;
    v49 += v58 + 2;
  }
  v59 = (*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, size_t *))(*(_QWORD *)a2 + 80LL))(a2, 0, &Size);
  v60 = Size;
  if ( (_DWORD)Size )
  {
    v10 = (const char *)v59;
  }
  else
  {
    v60 = 1;
    LODWORD(Size) = 1;
  }
  v61 = v60 + v57 + 3;
  if ( v61 <= *a4
    && (memcpy_0(v49, v10, v60),
        v62 = (unsigned int)Size,
        *(_WORD *)&v49[(unsigned int)Size] = 3372,
        v49[v62 + 2] = 10,
        v61 <= *a4) )
  {
    *a4 = v61;
    return 1;
  }
  else
  {
    *a4 = v61;
    SetLastError(0x7Au);
    return 0;
  }
}

```

## disassembly

```asm
0x18000c170  push    rbp
0x18000c172  push    rbx
0x18000c173  push    rsi
0x18000c174  push    rdi
0x18000c175  push    r12
0x18000c177  push    r13
0x18000c179  push    r14
0x18000c17b  push    r15
0x18000c17d  mov     rbp, rsp
0x18000c180  sub     rsp, 78h
0x18000c184  mov     rax, cs:__security_cookie
0x18000c18b  xor     rax, rsp
0x18000c18e  mov     [rbp+var_18], rax
0x18000c192  mov     rax, [rbp+arg_20]
0x18000c196  mov     r13, r9
0x18000c199  mov     [rbp+var_48], rax
0x18000c19d  mov     rdi, r8
0x18000c1a0  mov     qword ptr [rbp+var_40], rcx
0x18000c1a4  mov     r12, rdx
0x18000c1a7  mov     [rbp+var_50], r8
0x18000c1ab  mov     dword ptr [rbp+Size], 0
0x18000c1b2  test    r8, r8
0x18000c1b5  jnz     short loc_18000C1C0
0x18000c1b7  lea     eax, [r8+57h]
0x18000c1bb  jmp     loc_18000C60F
0x18000c1c0  mov     rax, [rdx]
0x18000c1c3  lea     r8, [rbp+Size]
0x18000c1c7  xor     edx, edx
0x18000c1c9  mov     rcx, r12
0x18000c1cc  mov     rax, [rax+28h]
0x18000c1d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1d5  mov     rdx, rax
0x18000c1d8  lea     r14, Src; "-"
0x18000c1df  mov     eax, dword ptr [rbp+Size]
0x18000c1e2  mov     r15d, 1
0x18000c1e8  test    eax, eax
0x18000c1ea  jnz     short loc_18000C1F5
0x18000c1ec  mov     eax, r15d
0x18000c1ef  mov     rdx, r14; Src
0x18000c1f2  mov     dword ptr [rbp+Size], eax
0x18000c1f5  lea     ebx, [rax+2]
0x18000c1f8  cmp     ebx, [r13+0]
0x18000c1fc  ja      short loc_18000C21D
0x18000c1fe  mov     r8d, eax; Size
0x18000c201  mov     rcx, rdi; void *
0x18000c204  call    memcpy_0
0x18000c209  mov     eax, dword ptr [rbp+Size]
0x18000c20c  mov     word ptr [rax+rdi], 202Ch
0x18000c212  add     rdi, 2
0x18000c216  add     rdi, rax
0x18000c219  mov     [rbp+var_50], rdi
0x18000c21d  mov     rax, [r12]
0x18000c221  lea     r8, [rbp+Size]
0x18000c225  xor     edx, edx
0x18000c227  mov     rcx, r12
0x18000c22a  mov     rsi, rdi
0x18000c22d  mov     rax, [rax+30h]
0x18000c231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c236  mov     rdx, rax
0x18000c239  mov     eax, dword ptr [rbp+Size]
0x18000c23c  test    eax, eax
0x18000c23e  jnz     short loc_18000C249
0x18000c240  mov     eax, r15d
0x18000c243  mov     rdx, r14; Src
0x18000c246  mov     dword ptr [rbp+Size], eax
0x18000c249  lea     r15d, [rax+2]
0x18000c24d  add     r15d, ebx
0x18000c250  cmp     r15d, [r13+0]
0x18000c254  ja      short loc_18000C278
0x18000c256  mov     r8d, eax; Size
0x18000c259  mov     rcx, rsi; void *
0x18000c25c  call    memcpy_0
0x18000c261  mov     eax, dword ptr [rbp+Size]
0x18000c264  lea     rdi, [rax+2]
0x18000c268  mov     word ptr [rax+rsi], 202Ch
0x18000c26e  add     rdi, rsi
0x18000c271  mov     [rbp+var_50], rdi
0x18000c275  mov     rsi, rdi
0x18000c278  mov     rbx, qword ptr [rbp+var_40]
0x18000c27c  mov     rdx, [rbp+var_48]
0x18000c280  lea     rcx, [rbx+628h]
0x18000c287  call    cs:__imp_?SetLocalTime@ASCLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z; ASCLOG_DATETIME_CACHE::SetLocalTime(_SYSTEMTIME *)
0x18000c28d  mov     rdx, [rbp+var_48]
0x18000c291  lea     r8, [rbp+Src]
0x18000c295  lea     rcx, [rbx+628h]
0x18000c29c  call    cs:__imp_?GetFormattedDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEBU_SYSTEMTIME@@PEAD@Z; CACHED_DATETIME_FORMATS::GetFormattedDateTime(_SYSTEMTIME const *,char *)
0x18000c2a2  mov     dword ptr [rbp+Size], eax
0x18000c2a5  lea     ebx, [r15+rax]
0x18000c2a9  cmp     ebx, [r13+0]
0x18000c2ad  ja      short loc_18000C2CB
0x18000c2af  mov     r8d, eax; Size
0x18000c2b2  lea     rdx, [rbp+Src]; Src
0x18000c2b6  mov     rcx, rsi; void *
0x18000c2b9  call    memcpy_0
0x18000c2be  mov     edi, dword ptr [rbp+Size]
0x18000c2c1  add     rdi, rsi
0x18000c2c4  mov     [rbp+var_50], rdi
0x18000c2c8  mov     rsi, rdi
0x18000c2cb  mov     rax, [r12]
0x18000c2cf  lea     r8, [rbp+Size]
0x18000c2d3  xor     edx, edx
0x18000c2d5  mov     rcx, r12
0x18000c2d8  mov     rax, [rax+18h]
0x18000c2dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2e1  mov     rdx, rax
0x18000c2e4  mov     eax, dword ptr [rbp+Size]
0x18000c2e7  test    eax, eax
0x18000c2e9  jnz     short loc_18000C2F6
0x18000c2eb  mov     eax, 1
0x18000c2f0  mov     rdx, r14; Src
0x18000c2f3  mov     dword ptr [rbp+Size], eax
0x18000c2f6  add     ebx, 2
0x18000c2f9  add     ebx, eax
0x18000c2fb  cmp     ebx, [r13+0]
0x18000c2ff  ja      short loc_18000C323
0x18000c301  mov     r8d, eax; Size
0x18000c304  mov     rcx, rsi; void *
0x18000c307  call    memcpy_0
0x18000c30c  mov     eax, dword ptr [rbp+Size]
0x18000c30f  lea     rdi, [rax+2]
0x18000c313  mov     word ptr [rax+rsi], 202Ch
0x18000c319  add     rdi, rsi
0x18000c31c  mov     [rbp+var_50], rdi
0x18000c320  mov     rsi, rdi
0x18000c323  mov     rax, [r12]
0x18000c327  lea     r8, [rbp+Size]
0x18000c32b  xor     edx, edx
0x18000c32d  mov     rcx, r12
0x18000c330  mov     rax, [rax+20h]
0x18000c334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c339  mov     rdx, rax
0x18000c33c  mov     eax, dword ptr [rbp+Size]
0x18000c33f  test    eax, eax
0x18000c341  jnz     short loc_18000C34E
0x18000c343  mov     eax, 1
0x18000c348  mov     rdx, r14; Src
0x18000c34b  mov     dword ptr [rbp+Size], eax
0x18000c34e  add     ebx, 2
0x18000c351  add     ebx, eax
0x18000c353  cmp     ebx, [r13+0]
0x18000c357  ja      short loc_18000C37B
0x18000c359  mov     r8d, eax; Size
0x18000c35c  mov     rcx, rsi; void *
0x18000c35f  call    memcpy_0
0x18000c364  mov     eax, dword ptr [rbp+Size]
0x18000c367  lea     rdi, [rax+2]
0x18000c36b  mov     word ptr [rax+rsi], 202Ch
0x18000c371  add     rdi, rsi
0x18000c374  mov     [rbp+var_50], rdi
0x18000c378  mov     rsi, rdi
0x18000c37b  mov     rax, [r12]
0x18000c37f  lea     r8, [rbp+Size]
0x18000c383  xor     edx, edx
0x18000c385  mov     rcx, r12
0x18000c388  mov     rax, [rax+38h]
0x18000c38c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c391  mov     rdx, rax
0x18000c394  mov     eax, dword ptr [rbp+Size]
0x18000c397  test    eax, eax
0x18000c399  jnz     short loc_18000C3A6
0x18000c39b  mov     eax, 1
0x18000c3a0  mov     rdx, r14; Src
0x18000c3a3  mov     dword ptr [rbp+Size], eax
0x18000c3a6  add     ebx, 2
0x18000c3a9  add     ebx, eax
0x18000c3ab  mov     dword ptr [rbp+var_48], ebx
0x18000c3ae  cmp     ebx, [r13+0]
0x18000c3b2  ja      short loc_18000C3D6
0x18000c3b4  mov     r8d, eax; Size
0x18000c3b7  mov     rcx, rsi; void *
0x18000c3ba  call    memcpy_0
0x18000c3bf  mov     eax, dword ptr [rbp+Size]
0x18000c3c2  lea     rdi, [rax+2]
0x18000c3c6  mov     word ptr [rax+rsi], 202Ch
0x18000c3cc  add     rdi, rsi
0x18000c3cf  mov     [rbp+var_50], rdi
0x18000c3d3  mov     rsi, rdi
0x18000c3d6  lea     eax, [rbx+0Ah]
0x18000c3d9  mov     rcx, r12; struct IInetLogInformation *
0x18000c3dc  mov     [rbp+var_40], eax
0x18000c3df  add     eax, 32h ; '2'
0x18000c3e2  cmp     eax, [r13+0]
0x18000c3e6  ja      loc_18000C4EA
0x18000c3ec  mov     rax, [r12]
0x18000c3f0  mov     rax, [rax+60h]
0x18000c3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3f9  mov     edx, eax; Value
0x18000c3fb  mov     rcx, rdi; Buffer
0x18000c3fe  call    ?FastDwToA@@YAKPEADK@Z; FastDwToA(char *,ulong)
0x18000c403  mov     r15d, eax
0x18000c406  lea     rbx, [rsi+2]
0x18000c40a  mov     dword ptr [rbp+Size], r15d
0x18000c40e  mov     rcx, r12
0x18000c411  add     rbx, r15
0x18000c414  mov     word ptr [r15+rsi], 202Ch
0x18000c41b  mov     rax, [r12]
0x18000c41f  mov     rax, [rax+70h]
0x18000c423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c428  mov     edx, eax; Value
0x18000c42a  mov     rcx, rbx; Buffer
0x18000c42d  call    ?FastDwToA@@YAKPEADK@Z; FastDwToA(char *,ulong)
0x18000c432  mov     r14d, eax
0x18000c435  mov     rcx, r12
0x18000c438  mov     dword ptr [rbp+Size], r14d
0x18000c43c  mov     word ptr [r14+rbx], 202Ch
0x18000c443  add     rbx, r14
0x18000c446  mov     rax, [r12]
0x18000c44a  mov     rax, [rax+68h]
0x18000c44e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c453  mov     edx, eax; Value
0x18000c455  lea     rcx, [rbx+2]; Buffer
0x18000c459  call    ?FastDwToA@@YAKPEADK@Z; FastDwToA(char *,ulong)
0x18000c45e  mov     esi, eax
0x18000c460  mov     rcx, r12
0x18000c463  mov     dword ptr [rbp+Size], esi
0x18000c466  mov     word ptr [rsi+rbx+2], 202Ch
0x18000c46d  add     rbx, 4
0x18000c471  mov     rax, [r12]
0x18000c475  add     rbx, rsi
0x18000c478  mov     rax, [rax+80h]
0x18000c47f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c484  mov     edx, eax; Value
0x18000c486  mov     rcx, rbx; Buffer
0x18000c489  call    ?FastDwToA@@YAKPEADK@Z; FastDwToA(char *,ulong)
0x18000c48e  mov     edi, eax
0x18000c490  mov     rcx, r12
0x18000c493  mov     dword ptr [rbp+Size], edi
0x18000c496  mov     word ptr [rdi+rbx], 202Ch
0x18000c49c  add     rbx, rdi
0x18000c49f  mov     rax, [r12]
0x18000c4a3  mov     rax, [rax+78h]
0x18000c4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4ac  mov     edx, eax; Value
0x18000c4ae  lea     rcx, [rbx+2]; Buffer
0x18000c4b2  call    ?FastDwToA@@YAKPEADK@Z; FastDwToA(char *,ulong)
0x18000c4b7  mov     ecx, dword ptr [rbp+var_48]
0x18000c4ba  add     ecx, 0Ah
0x18000c4bd  mov     eax, eax
0x18000c4bf  add     ecx, eax
0x18000c4c1  mov     dword ptr [rbp+Size], eax
0x18000c4c4  add     ecx, edi
0x18000c4c6  add     ecx, esi
0x18000c4c8  add     ecx, r14d
0x18000c4cb  mov     word ptr [rax+rbx+2], 202Ch
0x18000c4d2  add     ecx, r15d
0x18000c4d5  lea     r14, Src; "-"
0x18000c4dc  add     rbx, 4
0x18000c4e0  mov     dword ptr [rbp+var_48], ecx
0x18000c4e3  add     rbx, rax
0x18000c4e6  mov     edi, ecx
0x18000c4e8  jmp     short loc_18000C501
0x18000c4ea  lea     r9, [rbp+var_40]; unsigned int *
0x18000c4ee  mov     r8, r13; unsigned int *
0x18000c4f1  lea     rdx, [rbp+var_50]; char **
0x18000c4f5  call    ?FormatLogDwords@@YAXPEAVIInetLogInformation@@PEAPEADPEAK2@Z; FormatLogDwords(IInetLogInformation *,char * *,ulong *,ulong *)
0x18000c4fa  mov     rbx, [rbp+var_50]
0x18000c4fe  mov     edi, [rbp+var_40]
0x18000c501  mov     rax, [r12]
0x18000c505  lea     r8, [rbp+Size]
0x18000c509  xor     edx, edx
0x18000c50b  mov     rcx, r12
0x18000c50e  mov     rax, [rax+40h]
0x18000c512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c517  mov     rdx, rax
0x18000c51a  mov     esi, 1
0x18000c51f  mov     eax, dword ptr [rbp+Size]
0x18000c522  test    eax, eax
0x18000c524  jnz     short loc_18000C52E
0x18000c526  mov     eax, esi
0x18000c528  mov     rdx, r14; Src
0x18000c52b  mov     dword ptr [rbp+Size], eax
0x18000c52e  add     edi, 2
0x18000c531  add     edi, eax
0x18000c533  cmp     edi, [r13+0]
0x18000c537  ja      short loc_18000C554
0x18000c539  mov     r8d, eax; Size
0x18000c53c  mov     rcx, rbx; void *
0x18000c53f  call    memcpy_0
0x18000c544  mov     eax, dword ptr [rbp+Size]
0x18000c547  mov     word ptr [rax+rbx], 202Ch
0x18000c54d  add     rbx, 2
0x18000c551  add     rbx, rax
0x18000c554  mov     rax, [r12]
0x18000c558  lea     r8, [rbp+Size]
0x18000c55c  xor     edx, edx
0x18000c55e  mov     rcx, r12
0x18000c561  mov     rax, [rax+48h]
0x18000c565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c56a  mov     rdx, rax
0x18000c56d  mov     eax, dword ptr [rbp+Size]
0x18000c570  test    eax, eax
0x18000c572  jnz     short loc_18000C57C
0x18000c574  mov     eax, esi
0x18000c576  mov     rdx, r14; Src
0x18000c579  mov     dword ptr [rbp+Size], eax
0x18000c57c  add     edi, 2
0x18000c57f  add     edi, eax
0x18000c581  cmp     edi, [r13+0]
0x18000c585  ja      short loc_18000C5A2
0x18000c587  mov     r8d, eax; Size
  ... truncated ...
```
