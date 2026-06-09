# ProvisioningFileManager::RetrieveFile(ushort const *)

- ea: `0x180035150`
- end: `0x180035329`
- name: `?RetrieveFile@ProvisioningFileManager@@UEBA?AV?$ComPtr@UIStream@@@WRL@Microsoft@@PEBG@Z`
- size: `473`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800030e8`
- `0x1800090e0`
- `0x180009fac`
- `0x180034a78`
- `0x180035150`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800352b2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800352cc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800352b2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800352cc`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180035293`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180035293`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall ProvisioningFileManager::RetrieveFile(__int64 a1, _QWORD *a2, __int64 a3)
{
  LPCWSTR *v6; // r8
  int v7; // eax
  LPCWSTR *v8; // rdi
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  void *v11; // rcx
  _QWORD *v12; // rsi
  __int64 v13; // r8
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
  v8 = pszFile;
  if ( v19 >= 8 )
    v8 = (LPCWSTR *)pszFile[0];
  v9 = operator new(0x38u, (const struct std::nothrow_t *)std::nothrow);
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
      while ( *((_WORD *)v8 + v13) );
    }
    std::wstring::assign(v10 + 2, v8);
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
0x180035150  mov     [rsp-28h+arg_18], rbx
0x180035155  push    rbp
0x180035156  push    rsi
0x180035157  push    rdi
0x180035158  push    r14
0x18003515a  push    r15
0x18003515c  mov     rbp, rsp
0x18003515f  sub     rsp, 80h
0x180035166  mov     rax, cs:__security_cookie
0x18003516d  xor     rax, rsp
0x180035170  mov     [rbp+var_8], rax
0x180035174  mov     rdi, r8
0x180035177  mov     r14, rdx
0x18003517a  mov     rbx, rcx
0x18003517d  mov     [rbp+var_48], rdx
0x180035181  xor     r15d, r15d
0x180035184  mov     [rbp+var_50], r15d
0x180035188  lea     rcx, [rbp+pszFile]; void *
0x18003518c  call    ?GetFullTempFilePath@FileUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; FileUtility::GetFullTempFilePath(void)
0x180035191  nop
0x180035192  mov     rcx, [rbx+10h]
0x180035196  mov     rax, [rcx]
0x180035199  lea     r8, [rbp+pszFile]
0x18003519d  cmp     [rbp+var_10], 8
0x1800351a2  cmovnb  r8, [rbp+pszFile]
0x1800351a7  lea     r9d, [r15+1]
0x1800351ab  mov     rdx, rdi
0x1800351ae  mov     rax, [rax+30h]
0x1800351b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351b7  mov     rcx, [rbp+28h]; this
0x1800351bb  test    eax, eax
0x1800351bd  js      loc_180035314
0x1800351c3  lea     rdi, [rbp+pszFile]
0x1800351c7  cmp     [rbp+var_10], 8
0x1800351cc  cmovnb  rdi, [rbp+pszFile]
0x1800351d1  mov     [rbp+var_48], r15
0x1800351d5  mov     [rbp+var_50], 2
0x1800351dc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800351e3  lea     ecx, [r15+38h]; unsigned __int64
0x1800351e7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800351ec  mov     rbx, rax
0x1800351ef  mov     rcx, rax
0x1800351f2  mov     [rbp+var_40], rax
0x1800351f6  mov     [rbp+var_38], rax
0x1800351fa  mov     esi, r15d
0x1800351fd  test    rax, rax
0x180035200  jz      loc_1800352AD
0x180035206  mov     [rbp+var_30], rax
0x18003520a  mov     dword ptr [rax+0Ch], 1
0x180035211  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIStream@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStream>::`vftable'
0x180035218  mov     [rcx], rax
0x18003521b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180035222  test    rcx, rcx
0x180035225  jz      short loc_180035234
0x180035227  mov     rax, [rcx]
0x18003522a  mov     rax, [rax+8]
0x18003522e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035233  nop
0x180035234  lea     rax, ??_7AutoDeleteFileStream@@6B@; const AutoDeleteFileStream::`vftable'
0x18003523b  mov     [rbx], rax
0x18003523e  lea     rcx, [rbx+10h]; void *
0x180035242  mov     qword ptr [rcx+18h], 7
0x18003524a  mov     [rcx+10h], r15
0x18003524e  mov     [rcx], r15w
0x180035252  cmp     [rdi], r15w
0x180035256  jnz     short loc_18003525D
0x180035258  mov     r8, r15
0x18003525b  jmp     short loc_18003526B
0x18003525d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180035261  inc     r8
0x180035264  cmp     [rdi+r8*2], r15w
0x180035269  jnz     short loc_180035261
0x18003526b  mov     rdx, rdi; Src
0x18003526e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180035273  nop
0x180035274  lea     rax, [rbx+30h]
0x180035278  mov     [rax], r15
0x18003527b  mov     [rsp+80h+ppstm], rax; ppstm
0x180035280  mov     [rsp+80h+pstmTemplate], r15; int
0x180035285  xor     r9d, r9d; fCreate
0x180035288  xor     edx, edx; grfMode
0x18003528a  mov     r8d, 80h; dwAttributes
0x180035290  mov     rcx, rdi; pszFile
0x180035293  call    cs:__imp_SHCreateStreamOnFileEx
0x18003529a  nop     dword ptr [rax+rax+00h]
0x18003529f  mov     rcx, [rbp+28h]; this
0x1800352a3  test    eax, eax
0x1800352a5  js      short loc_1800352FF
0x1800352a7  mov     rcx, r15
0x1800352aa  mov     rsi, rbx
0x1800352ad  test    rcx, rcx
0x1800352b0  jz      short loc_1800352BE
0x1800352b2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800352b9  nop     dword ptr [rax+rax+00h]
0x1800352be  mov     [r14], rsi
0x1800352c1  cmp     [rbp+var_10], 8
0x1800352c6  jb      short loc_1800352D8
0x1800352c8  mov     rcx, [rbp+pszFile]
0x1800352cc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800352d3  nop     dword ptr [rax+rax+00h]
0x1800352d8  mov     rax, r14
0x1800352db  mov     rcx, [rbp+var_8]
0x1800352df  xor     rcx, rsp; StackCookie
0x1800352e2  call    __security_check_cookie
0x1800352e7  mov     rbx, [rsp+80h+arg_18]
0x1800352ef  add     rsp, 80h
0x1800352f6  pop     r15
0x1800352f8  pop     r14
0x1800352fa  pop     rdi
0x1800352fb  pop     rsi
0x1800352fc  pop     rbp
0x1800352fd  retn
0x1800352ff  mov     r9d, eax; char *
0x180035302  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\lib\\provision"...
0x180035309  mov     edx, 1Bh; void *
0x18003530e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035314  mov     r9d, eax; char *
0x180035317  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\lib\\provision"...
0x18003531e  mov     edx, 0BDh; void *
0x180035323  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
