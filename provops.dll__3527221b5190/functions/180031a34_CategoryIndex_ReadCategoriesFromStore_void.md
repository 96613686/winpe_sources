# CategoryIndex::ReadCategoriesFromStore(void)

- ea: `0x180031a34`
- end: `0x180031c46`
- name: `?ReadCategoriesFromStore@CategoryIndex@@AEAAXXZ`
- size: `530`
- prototype: `void __fastcall(CategoryIndex *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x180031354`

## callees

- `0x180002f44`
- `0x18001b388`
- `0x180020e98`
- `0x1800210f0`
- `0x1800245fc`
- `0x180024818`
- `0x180030a6c`
- `0x180030bdc`
- `0x18003117c`
- `0x180031a34`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180031b42`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180031b42`
- `msvcrt!??3@YAXPEAX@Z` at `0x180031aae`
- `msvcrt!??3@YAXPEAX@Z` at `0x180031bf7`
- `msvcrt!??3@YAXPEAX@Z` at `0x180031aae`
- `msvcrt!??3@YAXPEAX@Z` at `0x180031bf7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180031aa5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180031aa5`

## string_xrefs

- `0x180031af3`: `categories.xml`

## pseudocode

```c
void __fastcall CategoryIndex::ReadCategoriesFromStore(CategoryIndex *this)
{
  char ***Instance; // rsi
  char **v3; // rbx
  expanded_wstring *v4; // rax
  void **v5; // rdi
  char *v6; // rdx
  unsigned __int64 v7; // r8
  const WCHAR *v8; // rdx
  _QWORD *v9; // rax
  int v10; // eax
  void *v11; // rcx
  int v12; // [rsp+20h] [rbp-49h] BYREF
  void *ppvObject; // [rsp+28h] [rbp-41h] BYREF
  __int128 v14; // [rsp+30h] [rbp-39h] BYREF
  __int64 v15; // [rsp+40h] [rbp-29h]
  __int64 v16; // [rsp+48h] [rbp-21h]
  __int64 v17; // [rsp+50h] [rbp-19h]
  expanded_wstring *v18; // [rsp+58h] [rbp-11h]
  void *Src[3]; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int64 v20; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  Instance = (char ***)ProvisioningPaths::GetInstance();
  v3 = *Instance;
  if ( !*Instance )
  {
    v4 = (expanded_wstring *)operator new(0x10u);
    v18 = v4;
    if ( v4 )
      v3 = (char **)expanded_wstring::expanded_wstring(v4, L"%WINDIR%\\Provisioning\\");
    else
      v3 = 0;
    v5 = (void **)*Instance;
    if ( v3 == *Instance )
    {
      v3 = *Instance;
    }
    else
    {
      if ( v5 )
      {
        operator delete[](*v5);
        operator delete(v5);
      }
      *Instance = v3;
    }
  }
  v6 = *v3;
  v20 = 7;
  Src[2] = 0;
  LOWORD(Src[0]) = 0;
  if ( *(_WORD *)v6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&v6[2 * v7] );
  }
  else
  {
    v7 = 0;
  }
  std::wstring::assign(Src, v6, v7);
  std::wstring::append(Src, L"categories.xml");
  v8 = (const WCHAR *)Src;
  if ( v20 >= 8 )
    v8 = (const WCHAR *)Src[0];
  CreateCategoryReader(&ppvObject, v8);
  v12 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v9 = operator new(0x10u);
  if ( !v9 )
  {
    std::_Xbad_alloc();
    __debugbreak();
  }
  *(_QWORD *)&v14 = v9;
  *v9 = 0;
  v9[1] = 0;
  *(_QWORD *)v14 = &v14;
  while ( 1 )
  {
    v10 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v12);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCF,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v10,
        v12);
    if ( v10 )
      break;
    if ( v12 == 1 )
    {
      CategoryIndex::AddNode((__int64)this, &ppvObject, (__int64)&v14);
    }
    else if ( v12 == 15 && v17 && !--v17 )
    {
      v16 = 0;
    }
  }
  if ( v17 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
      (const char *)0x8000FFFFLL,
      v12);
  std::deque<_CategoryNode *>::~deque<_CategoryNode *>(&v14);
  v11 = ppvObject;
  if ( ppvObject )
  {
    ppvObject = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  if ( v20 >= 8 )
    operator delete(Src[0]);
}

```

## disassembly

```asm
0x180031a34  push    rbp
0x180031a36  push    rbx
0x180031a37  push    rsi
0x180031a38  push    rdi
0x180031a39  push    r14
0x180031a3b  push    r15
0x180031a3d  lea     rbp, [rsp-2Fh]
0x180031a42  sub     rsp, 98h
0x180031a49  mov     rax, cs:__security_cookie
0x180031a50  xor     rax, rsp
0x180031a53  mov     [rbp+57h+var_40], rax
0x180031a57  mov     r14, rcx
0x180031a5a  call    ?GetInstance@ProvisioningPaths@@CAAEAV1@XZ; ProvisioningPaths::GetInstance(void)
0x180031a5f  mov     rsi, rax
0x180031a62  mov     rbx, [rax]
0x180031a65  xor     r15d, r15d
0x180031a68  test    rbx, rbx
0x180031a6b  jnz     short loc_180031ABC
0x180031a6d  lea     ecx, [rbx+10h]; Size
0x180031a70  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031a75  mov     [rbp+57h+var_68], rax
0x180031a79  test    rax, rax
0x180031a7c  jz      short loc_180031A92
0x180031a7e  lea     rdx, ?gc_szWindowsProvisioningFolderPath@@3QBGB; "%WINDIR%\\Provisioning\\"
0x180031a85  mov     rcx, rax; this
0x180031a88  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x180031a8d  mov     rbx, rax
0x180031a90  jmp     short loc_180031A95
0x180031a92  mov     rbx, r15
0x180031a95  mov     rdi, [rsi]
0x180031a98  cmp     rbx, rdi
0x180031a9b  jz      short loc_180031AB9
0x180031a9d  test    rdi, rdi
0x180031aa0  jz      short loc_180031AB4
0x180031aa2  mov     rcx, [rdi]
0x180031aa5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180031aab  mov     rcx, rdi
0x180031aae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180031ab4  mov     [rsi], rbx
0x180031ab7  jmp     short loc_180031ABC
0x180031ab9  mov     rbx, rdi
0x180031abc  mov     rdx, [rbx]; Src
0x180031abf  mov     [rbp+57h+var_48], 7
0x180031ac7  mov     [rbp+57h+var_50], r15
0x180031acb  mov     word ptr [rbp+57h+Src], r15w
0x180031ad0  cmp     [rdx], r15w
0x180031ad4  jnz     short loc_180031ADB
0x180031ad6  mov     r8, r15
0x180031ad9  jmp     short loc_180031AE9
0x180031adb  or      r8, 0FFFFFFFFFFFFFFFFh
0x180031adf  inc     r8
0x180031ae2  cmp     [rdx+r8*2], r15w
0x180031ae7  jnz     short loc_180031ADF
0x180031ae9  lea     rcx, [rbp+57h+Src]; void *
0x180031aed  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180031af2  nop
0x180031af3  lea     rdx, aCategoriesXml; "categories.xml"
0x180031afa  lea     rcx, [rbp+57h+Src]; Src
0x180031afe  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180031b03  lea     rdx, [rbp+57h+Src]
0x180031b07  cmp     [rbp+57h+var_48], 8
0x180031b0c  cmovnb  rdx, [rbp+57h+Src]; pszFile
0x180031b11  lea     rcx, [rbp+57h+ppvObject]; ppvObject
0x180031b15  call    CreateCategoryReader
0x180031b1a  nop
0x180031b1b  mov     [rbp+57h+var_A0], r15d
0x180031b1f  xorps   xmm0, xmm0
0x180031b22  movdqu  [rbp+57h+var_90], xmm0
0x180031b27  mov     [rbp+57h+var_80], r15
0x180031b2b  mov     [rbp+57h+var_78], r15
0x180031b2f  mov     [rbp+57h+var_70], r15
0x180031b33  mov     ecx, 10h; Size
0x180031b38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031b3d  test    rax, rax
0x180031b40  jnz     short loc_180031B49
0x180031b42  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180031b48  int     3; Trap to Debugger
0x180031b49  mov     qword ptr [rbp+57h+var_90], rax
0x180031b4d  mov     [rax], r15
0x180031b50  mov     [rax+8], r15
0x180031b54  lea     rcx, [rbp+57h+var_90]
0x180031b58  mov     rax, qword ptr [rbp+57h+var_90]
0x180031b5c  mov     [rax], rcx
0x180031b5f  mov     rcx, [rbp+57h+ppvObject]
0x180031b63  mov     rax, [rcx]
0x180031b66  lea     rdx, [rbp+57h+var_A0]
0x180031b6a  mov     rax, [rax+30h]
0x180031b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b73  mov     rcx, [rbp+5Fh]; this
0x180031b77  test    eax, eax
0x180031b79  js      loc_180031C31
0x180031b7f  jnz     short loc_180031BB9
0x180031b81  mov     ecx, [rbp+57h+var_A0]
0x180031b84  sub     ecx, 1
0x180031b87  jz      short loc_180031BA7
0x180031b89  cmp     ecx, 0Eh
0x180031b8c  jnz     short loc_180031B5F
0x180031b8e  mov     rax, [rbp+57h+var_70]
0x180031b92  test    rax, rax
0x180031b95  jz      short loc_180031B5F
0x180031b97  sub     rax, 1
0x180031b9b  mov     [rbp+57h+var_70], rax
0x180031b9f  jnz     short loc_180031B5F
0x180031ba1  mov     [rbp+57h+var_78], r15
0x180031ba5  jmp     short loc_180031B5F
0x180031ba7  lea     r8, [rbp+57h+var_90]
0x180031bab  lea     rdx, [rbp+57h+ppvObject]
0x180031baf  mov     rcx, r14
0x180031bb2  call    ?AddNode@CategoryIndex@@AEAAXAEAV?$ComPtr@UIXmlReader@@@WRL@Microsoft@@AEAV?$deque@PEAU_CategoryNode@@V?$allocator@PEAU_CategoryNode@@@std@@@std@@@Z; CategoryIndex::AddNode(Microsoft::WRL::ComPtr<IXmlReader> &,std::deque<_CategoryNode *> &)
0x180031bb7  jmp     short loc_180031B5F
0x180031bb9  cmp     [rbp+57h+var_70], r15
0x180031bbd  setnz   al
0x180031bc0  mov     rcx, [rbp+5Fh]; this
0x180031bc4  test    al, al
0x180031bc6  jnz     short loc_180031C19
0x180031bc8  lea     rcx, [rbp+57h+var_90]
0x180031bcc  call    ??1?$deque@PEAU_CategoryNode@@V?$allocator@PEAU_CategoryNode@@@std@@@std@@QEAA@XZ; std::deque<_CategoryNode *>::~deque<_CategoryNode *>(void)
0x180031bd1  nop
0x180031bd2  mov     rcx, [rbp+57h+ppvObject]
0x180031bd6  test    rcx, rcx
0x180031bd9  jz      short loc_180031BEC
0x180031bdb  mov     [rbp+57h+ppvObject], r15
0x180031bdf  mov     rax, [rcx]
0x180031be2  mov     rax, [rax+10h]
0x180031be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031beb  nop
0x180031bec  cmp     [rbp+57h+var_48], 8
0x180031bf1  jb      short loc_180031BFD
0x180031bf3  mov     rcx, [rbp+57h+Src]
0x180031bf7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180031bfd  mov     rcx, [rbp+57h+var_40]
0x180031c01  xor     rcx, rsp; StackCookie
0x180031c04  call    __security_check_cookie
0x180031c09  add     rsp, 98h
0x180031c10  pop     r15
0x180031c12  pop     r14
0x180031c14  pop     rdi
0x180031c15  pop     rsi
0x180031c16  pop     rbx
0x180031c17  pop     rbp
0x180031c18  retn
0x180031c19  mov     r9d, 8000FFFFh; char *
0x180031c1f  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x180031c26  mov     edx, 0DCh; void *
0x180031c2b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031c31  mov     r9d, eax; char *
0x180031c34  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x180031c3b  mov     edx, 0CFh; void *
0x180031c40  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
