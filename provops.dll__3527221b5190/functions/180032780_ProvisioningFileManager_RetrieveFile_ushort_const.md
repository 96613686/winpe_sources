# ProvisioningFileManager::RetrieveFile(ushort const *)

- ea: `0x180032780`
- end: `0x180032946`
- name: `?RetrieveFile@ProvisioningFileManager@@UEBA?AV?$ComPtr@UIStream@@@WRL@Microsoft@@PEBG@Z`
- size: `454`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003e78`
- `0x18001b388`
- `0x1800210f0`
- `0x18002fc7c`
- `0x180032780`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800328dc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800328f0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800328dc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800328f0`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800328c3`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800328c3`

## pseudocode

```c
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
0x180032780  mov     [rsp-28h+arg_18], rbx
0x180032785  push    rbp
0x180032786  push    rsi
0x180032787  push    rdi
0x180032788  push    r14
0x18003278a  push    r15
0x18003278c  mov     rbp, rsp
0x18003278f  sub     rsp, 80h
0x180032796  mov     rax, cs:__security_cookie
0x18003279d  xor     rax, rsp
0x1800327a0  mov     [rbp+var_8], rax
0x1800327a4  mov     rdi, r8
0x1800327a7  mov     r14, rdx
0x1800327aa  mov     rbx, rcx
0x1800327ad  mov     [rbp+var_48], rdx
0x1800327b1  xor     r15d, r15d
0x1800327b4  mov     [rbp+var_50], r15d
0x1800327b8  lea     rcx, [rbp+pszFile]; void *
0x1800327bc  call    ?GetFullTempFilePath@FileUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; FileUtility::GetFullTempFilePath(void)
0x1800327c1  nop
0x1800327c2  mov     rcx, [rbx+10h]
0x1800327c6  mov     rax, [rcx]
0x1800327c9  lea     r8, [rbp+pszFile]
0x1800327cd  cmp     [rbp+var_10], 8
0x1800327d2  cmovnb  r8, [rbp+pszFile]
0x1800327d7  lea     r9d, [r15+1]
0x1800327db  mov     rdx, rdi
0x1800327de  mov     rax, [rax+30h]
0x1800327e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800327e7  mov     rcx, [rbp+28h]; this
0x1800327eb  test    eax, eax
0x1800327ed  js      loc_180032931
0x1800327f3  lea     rdi, [rbp+pszFile]
0x1800327f7  cmp     [rbp+var_10], 8
0x1800327fc  cmovnb  rdi, [rbp+pszFile]
0x180032801  mov     [rbp+var_48], r15
0x180032805  mov     [rbp+var_50], 2
0x18003280c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180032813  lea     ecx, [r15+38h]; unsigned __int64
0x180032817  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003281c  mov     rbx, rax
0x18003281f  mov     rcx, rax
0x180032822  mov     [rbp+var_40], rax
0x180032826  mov     [rbp+var_38], rax
0x18003282a  mov     esi, r15d
0x18003282d  test    rax, rax
0x180032830  jz      loc_1800328D7
0x180032836  mov     [rbp+var_30], rax
0x18003283a  mov     dword ptr [rax+0Ch], 1
0x180032841  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIStream@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStream>::`vftable'
0x180032848  mov     [rcx], rax
0x18003284b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180032852  test    rcx, rcx
0x180032855  jz      short loc_180032864
0x180032857  mov     rax, [rcx]
0x18003285a  mov     rax, [rax+8]
0x18003285e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032863  nop
0x180032864  lea     rax, ??_7AutoDeleteFileStream@@6B@; const AutoDeleteFileStream::`vftable'
0x18003286b  mov     [rbx], rax
0x18003286e  lea     rcx, [rbx+10h]; void *
0x180032872  mov     qword ptr [rcx+18h], 7
0x18003287a  mov     [rcx+10h], r15
0x18003287e  mov     [rcx], r15w
0x180032882  cmp     [rdi], r15w
0x180032886  jnz     short loc_18003288D
0x180032888  mov     r8, r15
0x18003288b  jmp     short loc_18003289B
0x18003288d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180032891  inc     r8
0x180032894  cmp     [rdi+r8*2], r15w
0x180032899  jnz     short loc_180032891
0x18003289b  mov     rdx, rdi; Src
0x18003289e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800328a3  nop
0x1800328a4  lea     rax, [rbx+30h]
0x1800328a8  mov     [rax], r15
0x1800328ab  mov     [rsp+80h+ppstm], rax; ppstm
0x1800328b0  mov     [rsp+80h+pstmTemplate], r15; int
0x1800328b5  xor     r9d, r9d; fCreate
0x1800328b8  xor     edx, edx; grfMode
0x1800328ba  mov     r8d, 80h; dwAttributes
0x1800328c0  mov     rcx, rdi; pszFile
0x1800328c3  call    cs:__imp_SHCreateStreamOnFileEx
0x1800328c9  mov     rcx, [rbp+28h]; this
0x1800328cd  test    eax, eax
0x1800328cf  js      short loc_18003291C
0x1800328d1  mov     rcx, r15
0x1800328d4  mov     rsi, rbx
0x1800328d7  test    rcx, rcx
0x1800328da  jz      short loc_1800328E2
0x1800328dc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800328e2  mov     [r14], rsi
0x1800328e5  cmp     [rbp+var_10], 8
0x1800328ea  jb      short loc_1800328F6
0x1800328ec  mov     rcx, [rbp+pszFile]
0x1800328f0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800328f6  mov     rax, r14
0x1800328f9  mov     rcx, [rbp+var_8]
0x1800328fd  xor     rcx, rsp; StackCookie
0x180032900  call    __security_check_cookie
0x180032905  mov     rbx, [rsp+80h+arg_18]
0x18003290d  add     rsp, 80h
0x180032914  pop     r15
0x180032916  pop     r14
0x180032918  pop     rdi
0x180032919  pop     rsi
0x18003291a  pop     rbp
0x18003291b  retn
0x18003291c  mov     r9d, eax; char *
0x18003291f  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\lib\\provision"...
0x180032926  mov     edx, 1Bh; void *
0x18003292b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032931  mov     r9d, eax; char *
0x180032934  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\lib\\provision"...
0x18003293b  mov     edx, 0BDh; void *
0x180032940  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
