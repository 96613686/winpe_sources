# ProvisioningFileManager::RetrieveFile(ushort const *)

- ea: `0x14000d760`
- end: `0x14000d926`
- name: `?RetrieveFile@ProvisioningFileManager@@UEBA?AV?$ComPtr@UIStream@@@WRL@Microsoft@@PEBG@Z`
- size: `454`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140002294`
- `0x140008b88`
- `0x140008e50`
- `0x14000be30`
- `0x14000d760`
- `0x14000ded0`
- `0x140010010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000d8bc`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000d8d0`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000d8bc`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000d8d0`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x14000d8a3`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x14000d8a3`

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
0x14000d760  mov     [rsp-28h+arg_18], rbx
0x14000d765  push    rbp
0x14000d766  push    rsi
0x14000d767  push    rdi
0x14000d768  push    r14
0x14000d76a  push    r15
0x14000d76c  mov     rbp, rsp
0x14000d76f  sub     rsp, 80h
0x14000d776  mov     rax, cs:__security_cookie
0x14000d77d  xor     rax, rsp
0x14000d780  mov     [rbp+var_8], rax
0x14000d784  mov     rdi, r8
0x14000d787  mov     r14, rdx
0x14000d78a  mov     rbx, rcx
0x14000d78d  mov     [rbp+var_48], rdx
0x14000d791  xor     r15d, r15d
0x14000d794  mov     [rbp+var_50], r15d
0x14000d798  lea     rcx, [rbp+pszFile]; void *
0x14000d79c  call    ?GetFullTempFilePath@FileUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; FileUtility::GetFullTempFilePath(void)
0x14000d7a1  nop
0x14000d7a2  mov     rcx, [rbx+10h]
0x14000d7a6  mov     rax, [rcx]
0x14000d7a9  lea     r8, [rbp+pszFile]
0x14000d7ad  cmp     [rbp+var_10], 8
0x14000d7b2  cmovnb  r8, [rbp+pszFile]
0x14000d7b7  lea     r9d, [r15+1]
0x14000d7bb  mov     rdx, rdi
0x14000d7be  mov     rax, [rax+30h]
0x14000d7c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d7c7  mov     rcx, [rbp+28h]; this
0x14000d7cb  test    eax, eax
0x14000d7cd  js      loc_14000D911
0x14000d7d3  lea     rdi, [rbp+pszFile]
0x14000d7d7  cmp     [rbp+var_10], 8
0x14000d7dc  cmovnb  rdi, [rbp+pszFile]
0x14000d7e1  mov     [rbp+var_48], r15
0x14000d7e5  mov     [rbp+var_50], 2
0x14000d7ec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000d7f3  lea     ecx, [r15+38h]; unsigned __int64
0x14000d7f7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000d7fc  mov     rbx, rax
0x14000d7ff  mov     rcx, rax
0x14000d802  mov     [rbp+var_40], rax
0x14000d806  mov     [rbp+var_38], rax
0x14000d80a  mov     esi, r15d
0x14000d80d  test    rax, rax
0x14000d810  jz      loc_14000D8B7
0x14000d816  mov     [rbp+var_30], rax
0x14000d81a  mov     dword ptr [rax+0Ch], 1
0x14000d821  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIStream@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStream>::`vftable'
0x14000d828  mov     [rcx], rax
0x14000d82b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000d832  test    rcx, rcx
0x14000d835  jz      short loc_14000D844
0x14000d837  mov     rax, [rcx]
0x14000d83a  mov     rax, [rax+8]
0x14000d83e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d843  nop
0x14000d844  lea     rax, ??_7AutoDeleteFileStream@@6B@; const AutoDeleteFileStream::`vftable'
0x14000d84b  mov     [rbx], rax
0x14000d84e  lea     rcx, [rbx+10h]; void *
0x14000d852  mov     qword ptr [rcx+18h], 7
0x14000d85a  mov     [rcx+10h], r15
0x14000d85e  mov     [rcx], r15w
0x14000d862  cmp     [rdi], r15w
0x14000d866  jnz     short loc_14000D86D
0x14000d868  mov     r8, r15
0x14000d86b  jmp     short loc_14000D87B
0x14000d86d  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000d871  inc     r8
0x14000d874  cmp     [rdi+r8*2], r15w
0x14000d879  jnz     short loc_14000D871
0x14000d87b  mov     rdx, rdi; Src
0x14000d87e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14000d883  nop
0x14000d884  lea     rax, [rbx+30h]
0x14000d888  mov     [rax], r15
0x14000d88b  mov     [rsp+80h+ppstm], rax; ppstm
0x14000d890  mov     [rsp+80h+pstmTemplate], r15; int
0x14000d895  xor     r9d, r9d; fCreate
0x14000d898  xor     edx, edx; grfMode
0x14000d89a  mov     r8d, 80h; dwAttributes
0x14000d8a0  mov     rcx, rdi; pszFile
0x14000d8a3  call    cs:__imp_SHCreateStreamOnFileEx
0x14000d8a9  mov     rcx, [rbp+28h]; this
0x14000d8ad  test    eax, eax
0x14000d8af  js      short loc_14000D8FC
0x14000d8b1  mov     rcx, r15
0x14000d8b4  mov     rsi, rbx
0x14000d8b7  test    rcx, rcx
0x14000d8ba  jz      short loc_14000D8C2
0x14000d8bc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000d8c2  mov     [r14], rsi
0x14000d8c5  cmp     [rbp+var_10], 8
0x14000d8ca  jb      short loc_14000D8D6
0x14000d8cc  mov     rcx, [rbp+pszFile]
0x14000d8d0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000d8d6  mov     rax, r14
0x14000d8d9  mov     rcx, [rbp+var_8]
0x14000d8dd  xor     rcx, rsp; StackCookie
0x14000d8e0  call    __security_check_cookie
0x14000d8e5  mov     rbx, [rsp+80h+arg_18]
0x14000d8ed  add     rsp, 80h
0x14000d8f4  pop     r15
0x14000d8f6  pop     r14
0x14000d8f8  pop     rdi
0x14000d8f9  pop     rsi
0x14000d8fa  pop     rbp
0x14000d8fb  retn
0x14000d8fc  mov     r9d, eax; char *
0x14000d8ff  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\lib\\provision"...
0x14000d906  mov     edx, 1Bh; void *
0x14000d90b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000d911  mov     r9d, eax; char *
0x14000d914  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\lib\\provision"...
0x14000d91b  mov     edx, 0BDh; void *
0x14000d920  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
