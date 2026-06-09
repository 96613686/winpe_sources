# InstalledPackageNode::RuntimeClassInitialize(IConfigManager2URI *)

- ea: `0x180008d50`
- end: `0x180008efa`
- name: `?RuntimeClassInitialize@InstalledPackageNode@@QEAAJPEAUIConfigManager2URI@@@Z`
- size: `426`
- prototype: `__int64 __fastcall(InstalledPackageNode *__hidden this, struct IConfigManager2URI *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180007c10`

## callees

- `0x180006974`
- `0x1800082dc`
- `0x18000848c`
- `0x1800088a4`
- `0x180008d50`
- `0x18000918c`
- `0x180031968`
- `0x1800319ec`
- `0x180031ab0`
- `0x1800322c0`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180008e1c`
- `msvcrt!_wcsicmp` at `0x180008e1c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008e38`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008e76`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008e38`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008e76`

## string_xrefs

- `0x180008de0`: `onecoreuap\admin\prov\provcsp\installedpackagenode.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall InstalledPackageNode::RuntimeClassInitialize(
        InstalledPackageNode *this,
        struct IConfigManager2URI *a2)
{
  const wchar_t *v3; // r15
  _QWORD *v4; // rbx
  _QWORD *v5; // rdi
  __int64 v7; // rax
  int v8; // r14d
  void *v9; // rax
  int v10; // [rsp+20h] [rbp-88h]
  _QWORD v11[3]; // [rsp+28h] [rbp-80h] BYREF
  _BYTE v12[32]; // [rsp+40h] [rbp-68h] BYREF
  void *v13[3]; // [rsp+60h] [rbp-48h] BYREF
  unsigned __int64 v14; // [rsp+78h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v3 = (const wchar_t *)PackageIdFromUri((__int64 *)a2);
  PackageCollector::PackageCollector((PackageCollector *)v12);
  PackageCollector::AddDefaultSearchPaths((PackageCollector *)v12);
  PackageCollector::Search((__int64)v12, v11);
  v4 = (_QWORD *)v11[0];
  v5 = (_QWORD *)v11[1];
  while ( 1 )
  {
    if ( v4 == v5 )
    {
      std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(v11);
      PackageCollector::~PackageCollector((PackageCollector *)v12);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\installedpackagenode.cpp",
        (const char *)0x86000002LL,
        v10);
      return 2248146946LL;
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)*v4 + 16LL))(*v4, v13);
    if ( *(_QWORD *)(v7 + 24) >= 8u )
      v7 = *(_QWORD *)v7;
    v8 = _wcsicmp(v3, (const wchar_t *)v7);
    if ( v14 >= 8 )
      operator delete(v13[0]);
    if ( !v8 )
      break;
    ++v4;
  }
  v9 = (void *)(*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)*v4 + 16LL))(*v4, v13);
  std::wstring::operator=((char *)this + 24, v9);
  if ( v14 >= 8 )
    operator delete(v13[0]);
  if ( (InstalledPackageNode *)((char *)this + 56) != (InstalledPackageNode *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 56LL))(*v4) )
    std::wstring::assign((char *)this + 56);
  std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(v11);
  PackageCollector::~PackageCollector((PackageCollector *)v12);
  return 0;
}

```

## disassembly

```asm
0x180008d50  mov     [rsp+arg_10], rbx
0x180008d55  mov     [rsp+arg_18], rsi
0x180008d5a  push    rdi
0x180008d5b  push    r14
0x180008d5d  push    r15
0x180008d5f  sub     rsp, 90h
0x180008d66  mov     rax, cs:__security_cookie
0x180008d6d  xor     rax, rsp
0x180008d70  mov     [rsp+0A8h+var_28], rax
0x180008d78  mov     rsi, rcx
0x180008d7b  mov     rcx, rdx
0x180008d7e  call    PackageIdFromUri
0x180008d83  mov     r15, rax
0x180008d86  lea     rcx, [rsp+0A8h+var_68]; this
0x180008d8b  call    ??0PackageCollector@@QEAA@XZ; PackageCollector::PackageCollector(void)
0x180008d90  nop
0x180008d91  lea     rcx, [rsp+0A8h+var_68]; this
0x180008d96  call    ?AddDefaultSearchPaths@PackageCollector@@QEAAXXZ; PackageCollector::AddDefaultSearchPaths(void)
0x180008d9b  lea     rdx, [rsp+0A8h+var_80]
0x180008da0  lea     rcx, [rsp+0A8h+var_68]
0x180008da5  call    ?Search@PackageCollector@@QEAA?AV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@XZ; PackageCollector::Search(void)
0x180008daa  nop
0x180008dab  mov     rbx, [rsp+0A8h+var_80]
0x180008db0  mov     rdi, [rsp+0A8h+var_78]
0x180008db5  cmp     rbx, rdi
0x180008db8  jnz     short loc_180008DF8
0x180008dba  lea     rcx, [rsp+0A8h+var_80]
0x180008dbf  call    ??1?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(void)
0x180008dc4  nop
0x180008dc5  lea     rcx, [rsp+0A8h+var_68]; this
0x180008dca  call    ??1PackageCollector@@UEAA@XZ; PackageCollector::~PackageCollector(void)
0x180008dcf  nop
0x180008dd0  mov     rcx, [rsp+0A8h]; this
0x180008dd8  mov     ebx, 86000002h
0x180008ddd  mov     r9d, ebx; char *
0x180008de0  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\prov\\provcsp\\insta"...
0x180008de7  mov     edx, 41h ; 'A'; void *
0x180008dec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008df1  mov     eax, ebx
0x180008df3  jmp     loc_180008ED0
0x180008df8  mov     rcx, [rbx]
0x180008dfb  mov     rax, [rcx]
0x180008dfe  lea     rdx, [rsp+0A8h+var_48]
0x180008e03  mov     rax, [rax+10h]
0x180008e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e0c  cmp     qword ptr [rax+18h], 8
0x180008e11  jb      short loc_180008E16
0x180008e13  mov     rax, [rax]
0x180008e16  mov     rdx, rax; String2
0x180008e19  mov     rcx, r15; String1
0x180008e1c  call    cs:__imp__wcsicmp
0x180008e23  nop     dword ptr [rax+rax+00h]
0x180008e28  mov     r14d, eax
0x180008e2b  cmp     [rsp+0A8h+var_30], 8
0x180008e31  jb      short loc_180008E44
0x180008e33  mov     rcx, [rsp+0A8h+var_48]
0x180008e38  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008e3f  nop     dword ptr [rax+rax+00h]
0x180008e44  test    r14d, r14d
0x180008e47  jnz     short loc_180008EC3
0x180008e49  mov     rcx, [rbx]
0x180008e4c  mov     rax, [rcx]
0x180008e4f  lea     rdx, [rsp+0A8h+var_48]
0x180008e54  mov     rax, [rax+10h]
0x180008e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e5d  lea     rcx, [rsi+18h]; void *
0x180008e61  mov     rdx, rax; Src
0x180008e64  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180008e69  cmp     [rsp+0A8h+var_30], 8
0x180008e6f  jb      short loc_180008E82
0x180008e71  mov     rcx, [rsp+0A8h+var_48]
0x180008e76  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008e7d  nop     dword ptr [rax+rax+00h]
0x180008e82  mov     rcx, [rbx]
0x180008e85  mov     rax, [rcx]
0x180008e88  mov     rax, [rax+38h]
0x180008e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e91  lea     rcx, [rsi+38h]; void *
0x180008e95  cmp     rcx, rax
0x180008e98  jz      short loc_180008EAA
0x180008e9a  or      r9, 0FFFFFFFFFFFFFFFFh
0x180008e9e  xor     r8d, r8d
0x180008ea1  mov     rdx, rax
0x180008ea4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180008ea9  nop
0x180008eaa  lea     rcx, [rsp+0A8h+var_80]
0x180008eaf  call    ??1?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(void)
0x180008eb4  nop
0x180008eb5  lea     rcx, [rsp+0A8h+var_68]; this
0x180008eba  call    ??1PackageCollector@@UEAA@XZ; PackageCollector::~PackageCollector(void)
0x180008ebf  xor     eax, eax
0x180008ec1  jmp     short loc_180008ED0
0x180008ec3  add     rbx, 8
0x180008ec7  jmp     loc_180008DB5
0x180008ecc  mov     eax, [rsp+0A8h+var_88]
0x180008ed0  mov     rcx, [rsp+0A8h+var_28]
0x180008ed8  xor     rcx, rsp; StackCookie
0x180008edb  call    __security_check_cookie
0x180008ee0  lea     r11, [rsp+0A8h+var_18]
0x180008ee8  mov     rbx, [r11+30h]
0x180008eec  mov     rsi, [r11+38h]
0x180008ef0  mov     rsp, r11
0x180008ef3  pop     r15
0x180008ef5  pop     r14
0x180008ef7  pop     rdi
0x180008ef8  retn
```
