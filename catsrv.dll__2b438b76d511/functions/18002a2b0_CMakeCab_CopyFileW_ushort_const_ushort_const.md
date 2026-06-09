# CMakeCab::CopyFileW(ushort const *,ushort const *)

- ea: `0x18002a2b0`
- end: `0x18002a5fb`
- name: `?CopyFileW@CMakeCab@@UEAAJPEBG0@Z`
- size: `843`
- prototype: `__int64 __fastcall(CMakeCab *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x18000a01c`
- `0x18002a2b0`
- `0x180055550`
- `0x180055610`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18002a3a2`
- `msvcrt!wcsrchr` at `0x18002a3a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5a1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002a3dc`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002a436`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002a473`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002a4ce`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002a505`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002a55d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002a3dc`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002a436`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002a473`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002a4ce`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002a505`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002a55d`
- `Cabinet!__imp_FDICreate` at `0x18002a381`
- `Cabinet!__imp_FDICreate` at `0x18002a381`
- `Cabinet!__imp_FDICopy` at `0x18002a593`
- `Cabinet!__imp_FDICopy` at `0x18002a593`
- `Cabinet!__imp_FDIDestroy` at `0x18002a5bd`
- `Cabinet!__imp_FDIDestroy` at `0x18002a5bd`

## pseudocode

```c
__int64 __fastcall CMakeCab::CopyFileW(CMakeCab *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  signed int v4; // ebx
  __int64 v5; // r11
  wchar_t *v6; // rax
  wchar_t *v7; // r14
  int v8; // eax
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // rdi
  void *v11; // rsp
  void *v12; // rsp
  CHAR *p_perf; // rdi
  int v14; // eax
  unsigned __int64 v15; // rdx
  __int64 v16; // rax
  unsigned __int64 v17; // rax
  void *v18; // rsp
  void *v19; // rsp
  __int64 v20; // r14
  int v21; // eax
  int v22; // edx
  unsigned __int64 v23; // rax
  __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  void *v26; // rsp
  void *v27; // rsp
  int v28; // eax
  CHAR *v29; // r8
  HFDI v30; // rdi
  signed int LastError; // eax
  PERF perf; // [rsp+40h] [rbp-10h] BYREF
  CHAR MultiByteStr[8]; // [rsp+50h] [rbp+0h] BYREF
  ERF v35; // [rsp+58h] [rbp+8h] BYREF

  *(_QWORD *)&v35.erfOper = 0;
  v35.fError = 0;
  if ( a2 && a3 )
  {
    v4 = StringCchCopyW(&word_180073340, 0x105u, a3);
    if ( v4 < 0 )
    {
LABEL_29:
      word_180073340 = 0;
      return (unsigned int)v4;
    }
    CodePage = *(_DWORD *)(v5 + 832) != 1 ? 0xFDE9 : 0;
    *(_QWORD *)MultiByteStr = FDICreate(
                                fcicb_Alloc,
                                (PFNFREE)operator delete,
                                fdicb_Open,
                                fdicb_Read,
                                fdicb_Write,
                                fdicb_Close,
                                fdicb_Seek,
                                -1,
                                &v35);
    if ( !*(_QWORD *)MultiByteStr )
    {
      v4 = -2147467259;
      goto LABEL_29;
    }
    v6 = wcsrchr(a2, 0x5Cu);
    v7 = v6;
    if ( v6 )
    {
      v14 = WideCharToMultiByte(CodePage, 0, v6 + 1, -1, 0, 0, 0, 0);
      v15 = v14;
      if ( v14 )
      {
        v16 = v14 + 15LL;
        if ( v15 + 15 < v15 )
          v16 = 0xFFFFFFFFFFFFFF0LL;
        v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
        v18 = alloca(v17);
        v19 = alloca(v17);
        if ( WideCharToMultiByte(CodePage, 0, v7 + 1, -1, MultiByteStr, v15, 0, 0) )
        {
          v20 = v7 - a2;
          v21 = WideCharToMultiByte(CodePage, 0, a2, v20 + 1, 0, 0, 0, 0);
          if ( v21 )
          {
            v22 = v21 + 1;
            v23 = v21 + 1LL;
            v24 = v23 + 15;
            if ( v23 + 15 < v23 )
              v24 = 0xFFFFFFFFFFFFFF0LL;
            v25 = v24 & 0xFFFFFFFFFFFFFFF0uLL;
            v26 = alloca(v25);
            v27 = alloca(v25);
            p_perf = MultiByteStr;
            v28 = WideCharToMultiByte(CodePage, 0, a2, v20 + 1, MultiByteStr, v22, 0, 0);
            if ( v28 )
            {
              MultiByteStr[v28] = 0;
LABEL_21:
              v29 = p_perf;
              v30 = *(HFDI *)MultiByteStr;
              if ( !FDICopy(*(HFDI *)MultiByteStr, MultiByteStr, v29, 0, notification_function, 0, 0) )
                v4 = -2147467259;
LABEL_27:
              if ( !FDIDestroy(v30) )
                v4 = -2147467259;
              goto LABEL_29;
            }
          }
        }
      }
    }
    else
    {
      v8 = WideCharToMultiByte(CodePage, 0, a2, -1, 0, 0, 0, 0);
      if ( v8 )
      {
        v9 = v8 + 15LL;
        if ( v9 < v8 )
          v9 = 0xFFFFFFFFFFFFFF0LL;
        v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
        v11 = alloca(v10);
        v12 = alloca(v10);
        if ( WideCharToMultiByte(CodePage, 0, a2, -1, MultiByteStr, v8, 0, 0) )
        {
          p_perf = (CHAR *)&perf;
          LOBYTE(perf) = 0;
          goto LABEL_21;
        }
      }
    }
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v30 = *(HFDI *)MultiByteStr;
    goto LABEL_27;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18002a2b0  push    rbp
0x18002a2b2  push    rsi
0x18002a2b3  push    rdi
0x18002a2b4  push    r12
0x18002a2b6  push    r13
0x18002a2b8  push    r14
0x18002a2ba  push    r15
0x18002a2bc  sub     rsp, 70h
0x18002a2c0  lea     rbp, [rsp+50h]
0x18002a2c5  mov     [rbp+50h+arg_0], rbx
0x18002a2c9  mov     rax, cs:__security_cookie
0x18002a2d0  xor     rax, rbp
0x18002a2d3  mov     [rbp+50h+var_38], rax
0x18002a2d7  xor     eax, eax
0x18002a2d9  xor     r12d, r12d
0x18002a2dc  mov     qword ptr [rbp+50h+var_48.erfOper], rax
0x18002a2e0  mov     rsi, rdx
0x18002a2e3  mov     [rbp+50h+var_48.fError], eax
0x18002a2e6  mov     r11, rcx
0x18002a2e9  test    rdx, rdx
0x18002a2ec  jz      loc_18002A5D6
0x18002a2f2  test    r8, r8
0x18002a2f5  jz      loc_18002A5D6
0x18002a2fb  mov     edx, 105h; unsigned __int64
0x18002a300  lea     rcx, word_180073340; unsigned __int16 *
0x18002a307  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a30c  mov     ebx, eax
0x18002a30e  test    eax, eax
0x18002a310  js      loc_18002A5CA
0x18002a316  mov     ecx, [r11+340h]
0x18002a31d  lea     rax, [rbp+50h+var_48]
0x18002a321  mov     [rsp+0A0h+perf], rax; perf
0x18002a326  lea     r9, fdicb_Read; pfnread
0x18002a32d  dec     ecx
0x18002a32f  lea     rax, fdicb_Seek
0x18002a336  neg     ecx
0x18002a338  lea     r8, fdicb_Open; pfnopen
0x18002a33f  lea     rdx, ??3@YAXPEAX@Z; pfnfree
0x18002a346  sbb     ecx, ecx
0x18002a348  or      r13d, 0FFFFFFFFh
0x18002a34c  mov     [rsp+0A0h+cpuType], r13d; cpuType
0x18002a351  and     ecx, 0FDE9h
0x18002a357  mov     [rsp+0A0h+pfnseek], rax; pfnseek
0x18002a35c  lea     rax, fdicb_Close
0x18002a363  mov     [rsp+0A0h+pfnclose], rax; pfnclose
0x18002a368  lea     rax, fdicb_Write
0x18002a36f  mov     cs:CodePage, ecx
0x18002a375  lea     rcx, fcicb_Alloc; pfnalloc
0x18002a37c  mov     [rsp+0A0h+pfnwrite], rax; pfnwrite
0x18002a381  call    cs:__imp_FDICreate
0x18002a387  mov     qword ptr [rbp+50h+MultiByteStr], rax
0x18002a38b  test    rax, rax
0x18002a38e  jnz     short loc_18002A39A
0x18002a390  mov     ebx, 80004005h
0x18002a395  jmp     loc_18002A5CA
0x18002a39a  mov     edx, 5Ch ; '\'; Ch
0x18002a39f  mov     rcx, rsi; Str
0x18002a3a2  call    cs:__imp_wcsrchr
0x18002a3a8  mov     ecx, cs:CodePage; CodePage
0x18002a3ae  xor     edx, edx; dwFlags
0x18002a3b0  mov     r14, rax
0x18002a3b3  mov     r15d, 80004005h
0x18002a3b9  mov     r9d, r13d; cchWideChar
0x18002a3bc  test    rax, rax
0x18002a3bf  jnz     loc_18002A45A
0x18002a3c5  mov     qword ptr [rsp+0A0h+cpuType], r12; lpUsedDefaultChar
0x18002a3ca  mov     r8, rsi; lpWideCharStr
0x18002a3cd  mov     [rsp+0A0h+pfnseek], r12; lpDefaultChar
0x18002a3d2  mov     dword ptr [rsp+0A0h+pfnclose], r12d; cbMultiByte
0x18002a3d7  mov     [rsp+0A0h+pfnwrite], r12; lpMultiByteStr
0x18002a3dc  call    cs:__imp_WideCharToMultiByte
0x18002a3e2  movsxd  rdx, eax
0x18002a3e5  test    eax, eax
0x18002a3e7  jz      loc_18002A5A1
0x18002a3ed  lea     rdi, [rdx+0Fh]
0x18002a3f1  cmp     rdi, rdx
0x18002a3f4  ja      short loc_18002A400
0x18002a3f6  mov     rdi, 0FFFFFFFFFFFFFF0h
0x18002a400  and     rdi, 0FFFFFFFFFFFFFFF0h
0x18002a404  mov     rax, rdi
0x18002a407  call    _alloca_probe
0x18002a40c  mov     ecx, cs:CodePage; CodePage
0x18002a412  sub     rsp, rdi
0x18002a415  or      r9d, 0FFFFFFFFh; cchWideChar
0x18002a419  mov     r8, rsi; lpWideCharStr
0x18002a41c  mov     qword ptr [rsp+0A0h+cpuType], r12; lpUsedDefaultChar
0x18002a421  lea     r13, [rsp+0A0h+MultiByteStr]
0x18002a426  mov     [rsp+0A0h+pfnseek], r12; lpDefaultChar
0x18002a42b  mov     dword ptr [rsp+0A0h+pfnclose], edx; cbMultiByte
0x18002a42f  xor     edx, edx; dwFlags
0x18002a431  mov     [rsp+0A0h+pfnwrite], r13; lpMultiByteStr
0x18002a436  call    cs:__imp_WideCharToMultiByte
0x18002a43c  test    eax, eax
0x18002a43e  jz      loc_18002A5A1
0x18002a444  mov     eax, [rsp+0A0h+var_A0]
0x18002a447  sub     rsp, 10h
0x18002a44b  lea     rdi, [rsp+0B0h+perf]
0x18002a450  mov     eax, [rdi]
0x18002a452  mov     [rdi], r12b
0x18002a455  jmp     loc_18002A56D
0x18002a45a  xor     edi, edi
0x18002a45c  lea     r8, [rax+2]; lpWideCharStr
0x18002a460  mov     qword ptr [rsp+0A0h+cpuType], rdi; lpUsedDefaultChar
0x18002a465  mov     [rsp+0A0h+pfnseek], rdi; lpDefaultChar
0x18002a46a  mov     dword ptr [rsp+0A0h+pfnclose], edi; cbMultiByte
0x18002a46e  mov     [rsp+0A0h+pfnwrite], rdi; lpMultiByteStr
0x18002a473  call    cs:__imp_WideCharToMultiByte
0x18002a479  movsxd  rdx, eax
0x18002a47c  test    eax, eax
0x18002a47e  jz      loc_18002A5A1
0x18002a484  lea     rax, [rdx+0Fh]
0x18002a488  mov     rdi, 0FFFFFFFFFFFFFF0h
0x18002a492  cmp     rax, rdx
0x18002a495  ja      short loc_18002A49A
0x18002a497  mov     rax, rdi
0x18002a49a  and     rax, 0FFFFFFFFFFFFFFF0h
0x18002a49e  call    _alloca_probe
0x18002a4a3  mov     ecx, cs:CodePage; CodePage
0x18002a4a9  lea     r8, [r14+2]; lpWideCharStr
0x18002a4ad  sub     rsp, rax
0x18002a4b0  or      r9d, 0FFFFFFFFh; cchWideChar
0x18002a4b4  mov     qword ptr [rsp+0A0h+cpuType], r12; lpUsedDefaultChar
0x18002a4b9  lea     r13, [rsp+0A0h+MultiByteStr]
0x18002a4be  mov     [rsp+0A0h+pfnseek], r12; lpDefaultChar
0x18002a4c3  mov     dword ptr [rsp+0A0h+pfnclose], edx; cbMultiByte
0x18002a4c7  xor     edx, edx; dwFlags
0x18002a4c9  mov     [rsp+0A0h+pfnwrite], r13; lpMultiByteStr
0x18002a4ce  call    cs:__imp_WideCharToMultiByte
0x18002a4d4  test    eax, eax
0x18002a4d6  jz      loc_18002A5A1
0x18002a4dc  mov     ecx, cs:CodePage; CodePage
0x18002a4e2  sub     r14, rsi
0x18002a4e5  mov     qword ptr [rsp+0A0h+cpuType], r12; lpUsedDefaultChar
0x18002a4ea  mov     r8, rsi; lpWideCharStr
0x18002a4ed  mov     [rsp+0A0h+pfnseek], r12; lpDefaultChar
0x18002a4f2  xor     edx, edx; dwFlags
0x18002a4f4  sar     r14, 1
0x18002a4f7  mov     dword ptr [rsp+0A0h+pfnclose], r12d; cbMultiByte
0x18002a4fc  mov     [rsp+0A0h+pfnwrite], r12; lpMultiByteStr
0x18002a501  lea     r9d, [r14+1]; cchWideChar
0x18002a505  call    cs:__imp_WideCharToMultiByte
0x18002a50b  test    eax, eax
0x18002a50d  jz      loc_18002A5A1
0x18002a513  lea     edx, [rax+1]
0x18002a516  cdqe
0x18002a518  inc     rax
0x18002a51b  lea     rcx, [rax+0Fh]
0x18002a51f  cmp     rcx, rax
0x18002a522  ja      short loc_18002A527
0x18002a524  mov     rcx, rdi
0x18002a527  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002a52b  mov     rax, rcx
0x18002a52e  call    _alloca_probe
0x18002a533  sub     rsp, rcx
0x18002a536  lea     r9d, [r14+1]; cchWideChar
0x18002a53a  mov     ecx, cs:CodePage; CodePage
0x18002a540  mov     r8, rsi; lpWideCharStr
0x18002a543  mov     qword ptr [rsp+0A0h+cpuType], r12; lpUsedDefaultChar
0x18002a548  lea     rdi, [rsp+0A0h+MultiByteStr]
0x18002a54d  mov     [rsp+0A0h+pfnseek], r12; lpDefaultChar
0x18002a552  mov     dword ptr [rsp+0A0h+pfnclose], edx; cbMultiByte
0x18002a556  xor     edx, edx; dwFlags
0x18002a558  mov     [rsp+0A0h+pfnwrite], rdi; lpMultiByteStr
0x18002a55d  call    cs:__imp_WideCharToMultiByte
0x18002a563  test    eax, eax
0x18002a565  jz      short loc_18002A5A1
0x18002a567  cdqe
0x18002a569  mov     [rax+rdi], r12b
0x18002a56d  mov     r8, rdi; pszCabPath
0x18002a570  mov     [rsp+0B0h+pfnwrite], r12; pvUser
0x18002a575  mov     rdi, qword ptr [rbp+50h+MultiByteStr]
0x18002a579  lea     rax, notification_function
0x18002a580  mov     rcx, rdi; hfdi
0x18002a583  mov     [rsp+0B0h+pfnfdid], r12; pfnfdid
0x18002a588  xor     r9d, r9d; flags
0x18002a58b  mov     [rsp+0B0h+pfnfdin], rax; pfnfdin
0x18002a590  mov     rdx, r13; pszCabinet
0x18002a593  call    cs:__imp_FDICopy
0x18002a599  test    eax, eax
0x18002a59b  cmovz   ebx, r15d
0x18002a59f  jmp     short loc_18002A5BA
0x18002a5a1  call    cs:__imp_GetLastError
0x18002a5a7  mov     ebx, eax
0x18002a5a9  test    eax, eax
0x18002a5ab  jle     short loc_18002A5B6
0x18002a5ad  movzx   ebx, ax
0x18002a5b0  or      ebx, 80070000h
0x18002a5b6  mov     rdi, qword ptr [rbp+50h+MultiByteStr]
0x18002a5ba  mov     rcx, rdi; hfdi
0x18002a5bd  call    cs:__imp_FDIDestroy
0x18002a5c3  cmp     eax, 1
0x18002a5c6  cmovnz  ebx, r15d
0x18002a5ca  mov     cs:word_180073340, r12w
0x18002a5d2  mov     eax, ebx
0x18002a5d4  jmp     short loc_18002A5DB
0x18002a5d6  mov     eax, 80070057h
0x18002a5db  mov     rcx, [rbp+50h+var_38]
0x18002a5df  xor     rcx, rbp; StackCookie
0x18002a5e2  call    __security_check_cookie
0x18002a5e7  mov     rbx, [rbp+50h+arg_0]
0x18002a5eb  lea     rsp, [rbp+20h]
0x18002a5ef  pop     r15
0x18002a5f1  pop     r14
0x18002a5f3  pop     r13
0x18002a5f5  pop     r12
0x18002a5f7  pop     rdi
0x18002a5f8  pop     rsi
0x18002a5f9  pop     rbp
0x18002a5fa  retn
```
