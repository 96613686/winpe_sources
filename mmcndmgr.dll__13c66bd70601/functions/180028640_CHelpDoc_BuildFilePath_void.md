# CHelpDoc::BuildFilePath(void)

- ea: `0x180028640`
- end: `0x180028822`
- name: `?BuildFilePath@CHelpDoc@@AEAAJXZ`
- size: `482`
- prototype: `__int64 __fastcall(CHelpDoc *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180028588`
- `0x180092f44`
- `0x180093168`

## callees

- `0x180019670`
- `0x180028640`
- `0x18008b4c0`
- `0x180093254`
- `0x180134502`
- `0x180134540`

## import_xrefs

- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180028755`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180028755`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180028678`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180028678`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18002877d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18002879c`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800287ca`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18002877d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18002879c`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800287ca`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18002872f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18002872f`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18002868b`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18002868b`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180028746`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800287a7`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800287d5`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180028746`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800287a7`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800287d5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18002873b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800287f3`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18002873b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800287f3`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800286a1`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800286a1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800286b7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800286b7`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x180028706`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x180028706`

## string_xrefs

- `0x18002867f`: `CHelpDoc::BuildFilePath`

## pseudocode

```c
__int64 __fastcall CHelpDoc::BuildFilePath(CHelpDoc *this)
{
  unsigned __int16 *v2; // rsi
  DWORD FileAttributesW; // eax
  const WCHAR *v4; // rdi
  unsigned int v5; // ebx
  __int64 BaseFileName; // rax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  _BYTE v11[24]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v12[24]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v13[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR szShortPath[264]; // [rsp+260h] [rbp+160h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v11, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v11, L"CHelpDoc::BuildFilePath");
  v2 = (unsigned __int16 *)((char *)this + 80);
  if ( (unsigned int)GetTempPath2W(260, (char *)this + 80) - 1 > 0x103
    || (FileAttributesW = GetFileAttributesW((LPCWSTR)this + 40), FileAttributesW == -1)
    || (FileAttributesW & 0x10) == 0 )
  {
    *v2 = 0;
    v5 = -2147467259;
  }
  else
  {
    v4 = (const WCHAR *)**((_QWORD **)this + 1);
    v5 = 0;
    if ( v4 && *v4 && (memset_0(szShortPath, 0, 0x208u), GetShortPathNameW(v4, szShortPath, 0x104u)) )
    {
      BaseFileName = ScGetBaseFileName(v12, szShortPath, v13);
      mmcerror::SC::operator=(v11, BaseFileName);
      mmcerror::SC::~SC((mmcerror::SC *)v12);
    }
    else
    {
      v7 = StringCchCopyW(v13, 0x104u, L"default");
      mmcerror::SC::operator=(v11, v7);
    }
    if ( (unsigned __int8)mmcerror::SC::operator bool(v11)
      || (v8 = StringCchCatW(v2, 0x104u, v13),
          mmcerror::SC::operator=(v11, v8),
          (unsigned __int8)mmcerror::SC::operator bool(v11))
      || (v9 = StringCchCatW(v2, 0x104u, L".col"),
          mmcerror::SC::operator=(v11, v9),
          (unsigned __int8)mmcerror::SC::operator bool(v11)) )
    {
      v5 = mmcerror::SC::ToHr((mmcerror::SC *)v11);
    }
  }
  mmcerror::SC::~SC((mmcerror::SC *)v11);
  return v5;
}

```

## disassembly

```asm
0x180028640  mov     [rsp-8+arg_8], rbx
0x180028645  mov     [rsp-8+arg_10], rsi
0x18002864a  push    rbp
0x18002864b  push    rdi
0x18002864c  push    r14
0x18002864e  lea     rbp, [rsp-380h]
0x180028656  sub     rsp, 480h
0x18002865d  mov     rax, cs:__security_cookie
0x180028664  xor     rax, rsp
0x180028667  mov     [rbp+390h+var_20], rax
0x18002866e  mov     rbx, rcx
0x180028671  xor     edx, edx
0x180028673  lea     rcx, [rsp+490h+var_470]
0x180028678  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18002867e  nop
0x18002867f  lea     rdx, aChelpdocBuildf; "CHelpDoc::BuildFilePath"
0x180028686  lea     rcx, [rsp+490h+var_470]
0x18002868b  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x180028691  lea     rsi, [rbx+50h]
0x180028695  mov     rdx, rsi
0x180028698  mov     r14d, 104h
0x18002869e  mov     ecx, r14d
0x1800286a1  call    cs:__imp_GetTempPath2W
0x1800286a7  dec     eax
0x1800286a9  cmp     eax, 103h
0x1800286ae  ja      loc_1800287E4
0x1800286b4  mov     rcx, rsi; lpFileName
0x1800286b7  call    cs:__imp_GetFileAttributesW
0x1800286bd  cmp     eax, 0FFFFFFFFh
0x1800286c0  jz      loc_1800287E4
0x1800286c6  test    al, 10h
0x1800286c8  jz      loc_1800287E4
0x1800286ce  mov     rax, [rbx+8]
0x1800286d2  mov     rdi, [rax]
0x1800286d5  xor     ebx, ebx
0x1800286d7  test    rdi, rdi
0x1800286da  jz      loc_180028762
0x1800286e0  cmp     [rdi], bx
0x1800286e3  jz      short loc_180028762
0x1800286e5  xor     edx, edx; Val
0x1800286e7  mov     r8d, 208h; Size
0x1800286ed  lea     rcx, [rbp+390h+szShortPath]; void *
0x1800286f4  call    memset_0
0x1800286f9  mov     r8d, r14d; cchBuffer
0x1800286fc  lea     rdx, [rbp+390h+szShortPath]; lpszShortPath
0x180028703  mov     rcx, rdi; lpszLongPath
0x180028706  call    cs:__imp_GetShortPathNameW
0x18002870c  test    eax, eax
0x18002870e  jz      short loc_180028762
0x180028710  lea     r8, [rsp+490h+var_440]
0x180028715  lea     rdx, [rbp+390h+szShortPath]
0x18002871c  lea     rcx, [rsp+490h+var_458]
0x180028721  call    ?ScGetBaseFileName@@YA?AVSC@mmcerror@@PEBGPEAGH@Z; ScGetBaseFileName(ushort const *,ushort *,int)
0x180028726  nop
0x180028727  mov     rdx, rax
0x18002872a  lea     rcx, [rsp+490h+var_470]
0x18002872f  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180028735  nop
0x180028736  lea     rcx, [rsp+490h+var_458]
0x18002873b  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180028741  lea     rcx, [rsp+490h+var_470]
0x180028746  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18002874c  test    al, al
0x18002874e  jz      short loc_180028785
0x180028750  lea     rcx, [rsp+490h+var_470]
0x180028755  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18002875b  mov     ebx, eax
0x18002875d  jmp     loc_1800287EE
0x180028762  lea     r8, aDefault; "default"
0x180028769  mov     rdx, r14; unsigned __int64
0x18002876c  lea     rcx, [rsp+490h+var_440]; unsigned __int16 *
0x180028771  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028776  mov     edx, eax
0x180028778  lea     rcx, [rsp+490h+var_470]
0x18002877d  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180028783  jmp     short loc_180028741
0x180028785  lea     r8, [rsp+490h+var_440]; unsigned __int16 *
0x18002878a  mov     rdx, r14; unsigned __int64
0x18002878d  mov     rcx, rsi; unsigned __int16 *
0x180028790  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180028795  mov     edx, eax
0x180028797  lea     rcx, [rsp+490h+var_470]
0x18002879c  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800287a2  lea     rcx, [rsp+490h+var_470]
0x1800287a7  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1800287ad  test    al, al
0x1800287af  jnz     short loc_180028750
0x1800287b1  lea     r8, aCol; ".col"
0x1800287b8  mov     rdx, r14; unsigned __int64
0x1800287bb  mov     rcx, rsi; unsigned __int16 *
0x1800287be  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800287c3  mov     edx, eax
0x1800287c5  lea     rcx, [rsp+490h+var_470]
0x1800287ca  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800287d0  lea     rcx, [rsp+490h+var_470]
0x1800287d5  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1800287db  test    al, al
0x1800287dd  jz      short loc_1800287EE
0x1800287df  jmp     loc_180028750
0x1800287e4  xor     ebx, ebx
0x1800287e6  mov     [rsi], bx
0x1800287e9  mov     ebx, 80004005h
0x1800287ee  lea     rcx, [rsp+490h+var_470]
0x1800287f3  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1800287f9  mov     eax, ebx
0x1800287fb  mov     rcx, [rbp+390h+var_20]
0x180028802  xor     rcx, rsp; StackCookie
0x180028805  call    __security_check_cookie
0x18002880a  lea     r11, [rsp+490h+var_10]
0x180028812  mov     rbx, [r11+28h]
0x180028816  mov     rsi, [r11+30h]
0x18002881a  mov     rsp, r11
0x18002881d  pop     r14
0x18002881f  pop     rdi
0x180028820  pop     rbp
0x180028821  retn
```
