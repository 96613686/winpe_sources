# ProvisioningFileManager::RetrieveFile(ushort const *)

- ea: `0x180042f20`
- end: `0x1800430e6`
- name: `?RetrieveFile@ProvisioningFileManager@@UEBA?AV?$ComPtr@UIStream@@@WRL@Microsoft@@PEBG@Z`
- size: `454`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800026c8`
- `0x18000b030`
- `0x180021cf4`
- `0x18004289c`
- `0x180042f20`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18004307c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180043090`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004307c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180043090`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180043063`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180043063`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall ProvisioningFileManager::RetrieveFile(__int64 a1, _QWORD *a2, __int64 a3)
{
  LPCWSTR *v6; // r8
  int v7; // eax
  char *v8; // rdi
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  void *v11; // rcx
  _QWORD *v12; // rsi
  unsigned __int64 v13; // r8
  HRESULT v14; // eax
  int pstmTemplate; // [rsp+20h] [rbp-60h]
  int pstmTemplatea; // [rsp+20h] [rbp-60h]
  LPCWSTR pszFile[3]; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v19; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  FileUtility::GetFullTempFilePath(pszFile);
  v6 = pszFile;
  if ( v19 >= 8 )
    v6 = (LPCWSTR *)pszFile[0];
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPCWSTR *, __int64))(**(_QWORD **)(a1 + 16) + 48LL))(
         *(_QWORD *)(a1 + 16),
         a3,
         v6,
         1);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provisioningfilemanager.cpp",
      (const char *)(unsigned int)v7,
      pstmTemplate);
  v8 = (char *)pszFile;
  if ( v19 >= 8 )
    v8 = (char *)pszFile[0];
  v9 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  v11 = v9;
  v12 = 0;
  if ( v9 )
  {
    *((_DWORD *)v9 + 3) = 1;
    *v9 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStream>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v10 = &AutoDeleteFileStream::`vftable';
    v10[5] = 7;
    v10[4] = 0;
    *((_WORD *)v10 + 8) = 0;
    if ( *(_WORD *)v8 )
    {
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)&v8[2 * v13] );
    }
    else
    {
      v13 = 0;
    }
    std::wstring::assign(v10 + 2, v8, v13);
    v10[6] = 0;
    v14 = SHCreateStreamOnFileEx((LPCWSTR)v8, 0, 0x80u, 0, 0, (IStream **)v10 + 6);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provisioningfilemanager.cpp",
        (const char *)(unsigned int)v14,
        pstmTemplatea);
    v11 = 0;
    v12 = v10;
  }
  if ( v11 )
    operator delete(v11);
  *a2 = v12;
  if ( v19 >= 8 )
    operator delete((void *)pszFile[0]);
  return a2;
}

```

## disassembly

```asm
0x180042f20  mov     [rsp-28h+arg_18], rbx
0x180042f25  push    rbp
0x180042f26  push    rsi
0x180042f27  push    rdi
0x180042f28  push    r14
0x180042f2a  push    r15
0x180042f2c  mov     rbp, rsp
0x180042f2f  sub     rsp, 80h
0x180042f36  mov     rax, cs:__security_cookie
0x180042f3d  xor     rax, rsp
0x180042f40  mov     [rbp+var_8], rax
0x180042f44  mov     rdi, r8
0x180042f47  mov     r14, rdx
0x180042f4a  mov     rbx, rcx
0x180042f4d  mov     [rbp+var_48], rdx
0x180042f51  xor     r15d, r15d
0x180042f54  mov     [rbp+var_50], r15d
0x180042f58  lea     rcx, [rbp+pszFile]; void *
0x180042f5c  call    ?GetFullTempFilePath@FileUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; FileUtility::GetFullTempFilePath(void)
0x180042f61  nop
0x180042f62  mov     rcx, [rbx+10h]
0x180042f66  mov     rax, [rcx]
0x180042f69  lea     r8, [rbp+pszFile]
0x180042f6d  cmp     [rbp+var_10], 8
0x180042f72  cmovnb  r8, [rbp+pszFile]
0x180042f77  lea     r9d, [r15+1]
0x180042f7b  mov     rdx, rdi
0x180042f7e  mov     rax, [rax+30h]
0x180042f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f87  mov     rcx, [rbp+28h]; this
0x180042f8b  test    eax, eax
0x180042f8d  js      loc_1800430D1
0x180042f93  lea     rdi, [rbp+pszFile]
0x180042f97  cmp     [rbp+var_10], 8
0x180042f9c  cmovnb  rdi, [rbp+pszFile]
0x180042fa1  mov     [rbp+var_48], r15
0x180042fa5  mov     [rbp+var_50], 2
0x180042fac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180042fb3  lea     ecx, [r15+38h]; unsigned __int64
0x180042fb7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180042fbc  mov     rbx, rax
0x180042fbf  mov     rcx, rax
0x180042fc2  mov     [rbp+var_40], rax
0x180042fc6  mov     [rbp+var_38], rax
0x180042fca  mov     esi, r15d
0x180042fcd  test    rax, rax
0x180042fd0  jz      loc_180043077
0x180042fd6  mov     [rbp+var_30], rax
0x180042fda  mov     dword ptr [rax+0Ch], 1
0x180042fe1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIStream@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStream>::`vftable'
0x180042fe8  mov     [rcx], rax
0x180042feb  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180042ff2  test    rcx, rcx
0x180042ff5  jz      short loc_180043004
0x180042ff7  mov     rax, [rcx]
0x180042ffa  mov     rax, [rax+8]
0x180042ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043003  nop
0x180043004  lea     rax, ??_7AutoDeleteFileStream@@6B@; const AutoDeleteFileStream::`vftable'
0x18004300b  mov     [rbx], rax
0x18004300e  lea     rcx, [rbx+10h]; void *
0x180043012  mov     qword ptr [rcx+18h], 7
0x18004301a  mov     [rcx+10h], r15
0x18004301e  mov     [rcx], r15w
0x180043022  cmp     [rdi], r15w
0x180043026  jnz     short loc_18004302D
0x180043028  mov     r8, r15
0x18004302b  jmp     short loc_18004303B
0x18004302d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180043031  inc     r8
0x180043034  cmp     [rdi+r8*2], r15w
0x180043039  jnz     short loc_180043031
0x18004303b  mov     rdx, rdi; Src
0x18004303e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180043043  nop
0x180043044  lea     rax, [rbx+30h]
0x180043048  mov     [rax], r15
0x18004304b  mov     [rsp+80h+ppstm], rax; ppstm
0x180043050  mov     [rsp+80h+pstmTemplate], r15; int
0x180043055  xor     r9d, r9d; fCreate
0x180043058  xor     edx, edx; grfMode
0x18004305a  mov     r8d, 80h; dwAttributes
0x180043060  mov     rcx, rdi; pszFile
0x180043063  call    cs:__imp_SHCreateStreamOnFileEx
0x180043069  mov     rcx, [rbp+28h]; this
0x18004306d  test    eax, eax
0x18004306f  js      short loc_1800430BC
0x180043071  mov     rcx, r15
0x180043074  mov     rsi, rbx
0x180043077  test    rcx, rcx
0x18004307a  jz      short loc_180043082
0x18004307c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180043082  mov     [r14], rsi
0x180043085  cmp     [rbp+var_10], 8
0x18004308a  jb      short loc_180043096
0x18004308c  mov     rcx, [rbp+pszFile]
0x180043090  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180043096  mov     rax, r14
0x180043099  mov     rcx, [rbp+var_8]
0x18004309d  xor     rcx, rsp; StackCookie
0x1800430a0  call    __security_check_cookie
0x1800430a5  mov     rbx, [rsp+80h+arg_18]
0x1800430ad  add     rsp, 80h
0x1800430b4  pop     r15
0x1800430b6  pop     r14
0x1800430b8  pop     rdi
0x1800430b9  pop     rsi
0x1800430ba  pop     rbp
0x1800430bb  retn
0x1800430bc  mov     r9d, eax; char *
0x1800430bf  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\lib\\provision"...
0x1800430c6  mov     edx, 1Bh; void *
0x1800430cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800430d1  mov     r9d, eax; char *
0x1800430d4  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\lib\\provision"...
0x1800430db  mov     edx, 0BDh; void *
0x1800430e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
