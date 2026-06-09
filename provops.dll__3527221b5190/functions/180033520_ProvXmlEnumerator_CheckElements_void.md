# ProvXmlEnumerator::CheckElements(void)

- ea: `0x180033520`
- end: `0x18003371d`
- name: `?CheckElements@ProvXmlEnumerator@@AEAAPEAUIStream@@XZ`
- size: `509`
- prototype: `struct IStream *__fastcall(ProvXmlEnumerator *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config, loader_planting`

## callers

- `0x18002e740`

## callees

- `0x180003e6c`
- `0x18001b388`
- `0x18002fc7c`
- `0x180033520`
- `0x180033878`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180033629`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033629`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003363b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800336d1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003363b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800336d1`
- `msvcrt!_wcsicmp` at `0x1800335ce`
- `msvcrt!_wcsicmp` at `0x1800335ce`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800335b9`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800335b9`

## string_xrefs

- `0x1800335c3`: `.provxml`
- `0x1800336f6`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`
- `0x18003370b`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct IStream *__fastcall ProvXmlEnumerator::CheckElements(ProvXmlEnumerator *this)
{
  WCHAR *v2; // rbx
  int v3; // eax
  void **v4; // r8
  int v5; // eax
  __int64 MemStreamFromTempFile; // rsi
  size_t v7; // rbx
  __int64 v8; // rcx
  PCWSTR v9; // rbx
  const WCHAR *v10; // rcx
  int v12; // [rsp+20h] [rbp-58h]
  size_t cchPath; // [rsp+30h] [rbp-48h] BYREF
  PCWSTR ppszExt[2]; // [rsp+38h] [rbp-40h] BYREF
  void *v15[3]; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int64 v16; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  while ( 1 )
  {
    cchPath = 0;
    while ( (***((int (__fastcall ****)(_QWORD, size_t *))this + 3))(*((_QWORD *)this + 3), &cchPath) >= 0 )
    {
      v2 = (WCHAR *)operator new[](saturated_mul(cchPath, 2u));
      ppszExt[1] = v2;
      v3 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, size_t))(**((_QWORD **)this + 3) + 8LL))(
             *((_QWORD *)this + 3),
             v2,
             cchPath);
      if ( v3 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3D,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
          (const char *)(unsigned int)v3,
          v12);
      ppszExt[0] = 0;
      if ( PathCchFindExtension(v2, cchPath, ppszExt) >= 0 && !_wcsicmp(ppszExt[0], L".provxml") )
      {
        FileUtility::GetFullTempFilePath(v15);
        v4 = v15;
        if ( v16 >= 8 )
          v4 = (void **)v15[0];
        v5 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, void **, _QWORD))(**((_QWORD **)this + 2) + 48LL))(
               *((_QWORD *)this + 2),
               v2,
               v4,
               0);
        if ( v5 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x63,
            (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
            (const char *)(unsigned int)v5,
            v12);
        MemStreamFromTempFile = CreateMemStreamFromTempFile(v15);
        if ( v16 >= 8 )
          operator delete(v15[0]);
        if ( MemStreamFromTempFile )
        {
          operator delete[](v2);
          return (struct IStream *)MemStreamFromTempFile;
        }
      }
      operator delete[](v2);
    }
    cchPath = 0;
    ppszExt[0] = 0;
    if ( (***((int (__fastcall ****)(_QWORD, size_t *))this + 1))(*((_QWORD *)this + 1), &cchPath) < 0
      || (*(int (__fastcall **)(size_t, PCWSTR *))(*(_QWORD *)cchPath + 64LL))(cchPath, ppszExt) < 0 )
    {
      break;
    }
    v7 = cchPath;
    v8 = *((_QWORD *)this + 2);
    if ( cchPath != v8 )
    {
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 80LL))(v8);
      *((_QWORD *)this + 2) = v7;
    }
    v9 = ppszExt[0];
    v10 = (const WCHAR *)*((_QWORD *)this + 3);
    if ( ppszExt[0] != v10 )
    {
      if ( v10 )
        (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v10 + 16LL))(v10);
      *((_QWORD *)this + 3) = v9;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180033520  push    rbp
0x180033522  push    rbx
0x180033523  push    rsi
0x180033524  push    rdi
0x180033525  mov     rbp, rsp
0x180033528  sub     rsp, 78h
0x18003352c  mov     rax, cs:__security_cookie
0x180033533  xor     rax, rsp
0x180033536  mov     [rbp+var_10], rax
0x18003353a  mov     rdi, rcx
0x18003353d  mov     [rbp+cchPath], 0
0x180033545  mov     rcx, [rdi+18h]
0x180033549  mov     rax, [rcx]
0x18003354c  lea     rdx, [rbp+cchPath]
0x180033550  mov     rax, [rax]
0x180033553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033558  test    eax, eax
0x18003355a  js      loc_180033646
0x180033560  mov     eax, 2
0x180033565  mul     [rbp+cchPath]
0x180033569  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180033570  cmovb   rax, rcx
0x180033574  mov     rcx, rax; unsigned __int64
0x180033577  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003357c  mov     rbx, rax
0x18003357f  mov     [rbp+var_38], rax
0x180033583  mov     rcx, [rdi+18h]
0x180033587  mov     rax, [rcx]
0x18003358a  mov     r8, [rbp+cchPath]
0x18003358e  mov     rdx, rbx
0x180033591  mov     rax, [rax+8]
0x180033595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003359a  mov     rcx, [rbp+20h]; this
0x18003359e  test    eax, eax
0x1800335a0  js      loc_1800336F3
0x1800335a6  mov     [rbp+ppszExt], 0
0x1800335ae  lea     r8, [rbp+ppszExt]; ppszExt
0x1800335b2  mov     rdx, [rbp+cchPath]; cchPath
0x1800335b6  mov     rcx, rbx; pszPath
0x1800335b9  call    cs:__imp_PathCchFindExtension
0x1800335bf  test    eax, eax
0x1800335c1  js      short loc_180033638
0x1800335c3  lea     rdx, ?gc_szProvxmlExtension@@3QBGB; ".provxml"
0x1800335ca  mov     rcx, [rbp+ppszExt]; String1
0x1800335ce  call    cs:__imp__wcsicmp
0x1800335d4  test    eax, eax
0x1800335d6  jnz     short loc_180033638
0x1800335d8  lea     rcx, [rbp+var_30]; void *
0x1800335dc  call    ?GetFullTempFilePath@FileUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; FileUtility::GetFullTempFilePath(void)
0x1800335e1  nop
0x1800335e2  mov     rcx, [rdi+10h]
0x1800335e6  mov     rax, [rcx]
0x1800335e9  lea     r8, [rbp+var_30]
0x1800335ed  cmp     [rbp+var_18], 8
0x1800335f2  cmovnb  r8, [rbp+var_30]
0x1800335f7  xor     r9d, r9d
0x1800335fa  mov     rdx, rbx
0x1800335fd  mov     rax, [rax+30h]
0x180033601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033606  mov     rcx, [rbp+20h]; this
0x18003360a  test    eax, eax
0x18003360c  js      loc_180033708
0x180033612  lea     rcx, [rbp+var_30]
0x180033616  call    CreateMemStreamFromTempFile
0x18003361b  mov     rsi, rax
0x18003361e  cmp     [rbp+var_18], 8
0x180033623  jb      short loc_18003362F
0x180033625  mov     rcx, [rbp+var_30]
0x180033629  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003362f  test    rsi, rsi
0x180033632  jnz     loc_1800336CE
0x180033638  mov     rcx, rbx
0x18003363b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180033641  jmp     loc_180033545
0x180033646  mov     [rbp+cchPath], 0
0x18003364e  mov     [rbp+ppszExt], 0
0x180033656  mov     rcx, [rdi+8]
0x18003365a  mov     rax, [rcx]
0x18003365d  lea     rdx, [rbp+cchPath]
0x180033661  mov     rax, [rax]
0x180033664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033669  test    eax, eax
0x18003366b  js      short loc_1800336D9
0x18003366d  mov     rcx, [rbp+cchPath]
0x180033671  mov     rax, [rcx]
0x180033674  lea     rdx, [rbp+ppszExt]
0x180033678  mov     rax, [rax+40h]
0x18003367c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033681  test    eax, eax
0x180033683  js      short loc_1800336D9
0x180033685  mov     rbx, [rbp+cchPath]
0x180033689  mov     rcx, [rdi+10h]
0x18003368d  cmp     rbx, rcx
0x180033690  jz      short loc_1800336A7
0x180033692  test    rcx, rcx
0x180033695  jz      short loc_1800336A3
0x180033697  mov     rax, [rcx]
0x18003369a  mov     rax, [rax+50h]
0x18003369e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336a3  mov     [rdi+10h], rbx
0x1800336a7  mov     rbx, [rbp+ppszExt]
0x1800336ab  mov     rcx, [rdi+18h]
0x1800336af  cmp     rbx, rcx
0x1800336b2  jz      short loc_1800336C9
0x1800336b4  test    rcx, rcx
0x1800336b7  jz      short loc_1800336C5
0x1800336b9  mov     rax, [rcx]
0x1800336bc  mov     rax, [rax+10h]
0x1800336c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336c5  mov     [rdi+18h], rbx
0x1800336c9  jmp     loc_18003353D
0x1800336ce  mov     rcx, rbx
0x1800336d1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800336d7  jmp     short loc_1800336DB
0x1800336d9  xor     esi, esi
0x1800336db  mov     rax, rsi
0x1800336de  mov     rcx, [rbp+var_10]
0x1800336e2  xor     rcx, rsp; StackCookie
0x1800336e5  call    __security_check_cookie
0x1800336ea  add     rsp, 78h
0x1800336ee  pop     rdi
0x1800336ef  pop     rsi
0x1800336f0  pop     rbx
0x1800336f1  pop     rbp
0x1800336f2  retn
0x1800336f3  mov     r9d, eax; char *
0x1800336f6  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x1800336fd  mov     edx, 3Dh ; '='; void *
0x180033702  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033708  mov     r9d, eax; char *
0x18003370b  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x180033712  mov     edx, 63h ; 'c'; void *
0x180033717  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
