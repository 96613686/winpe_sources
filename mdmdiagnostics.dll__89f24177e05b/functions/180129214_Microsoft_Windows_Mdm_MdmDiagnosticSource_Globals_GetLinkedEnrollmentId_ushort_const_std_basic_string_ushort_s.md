# Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetLinkedEnrollmentId(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180129214`
- end: `0x1801293ec`
- name: `?GetLinkedEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `472`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18012cad4`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800e7124`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ef188`
- `0x180104108`
- `0x18011129c`
- `0x18012886c`
- `0x180129214`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801292d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012932f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801292d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012932f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180129298`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801292fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180129298`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801292fb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012938e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012938e`

## string_xrefs

- `0x180129382`: `LinkedEnrollment`
- `0x18012937b`: `LinkedEnrollmentId`
- `0x180129348`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetLinkedEnrollmentId(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3)
{
  const WCHAR *v5; // rax
  unsigned int ValueW; // eax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE pvData[528]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  hKey = 0;
  hkey = 0;
  memset_0(pvData, 0, 0x208u);
  pcbData = 520;
  *(_QWORD *)(a3 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3) = 0;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v14);
    RegCloseKey(hKey);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v14);
  }
  hKey = 0;
  v5 = (const WCHAR *)DMGetKnownRegPath();
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey);
  if ( ValueW )
  {
    v7 = 163;
  }
  else
  {
    if ( hkey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v14);
      RegCloseKey(hkey);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v14);
    }
    hkey = 0;
    ValueW = RegOpenKeyExW(hKey, a2, 0, 0x20019u, &hkey);
    if ( !ValueW )
    {
      ValueW = RegGetValueW(hkey, L"LinkedEnrollment", L"LinkedEnrollmentId", 2u, 0, pvData, &pcbData);
      if ( ValueW != 2 )
      {
        if ( ValueW )
        {
          v7 = 171;
          goto LABEL_9;
        }
        std::wstring::assign(a3, pvData);
      }
      v8 = 0;
      goto LABEL_15;
    }
    v7 = 164;
  }
LABEL_9:
  v8 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v7,
         (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
         (const char *)ValueW,
         phkResult);
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v8;
}

```

## disassembly

```asm
0x180129214  mov     [rsp-8+arg_0], rbx
0x180129219  push    rbp
0x18012921a  push    rsi
0x18012921b  push    rdi
0x18012921c  lea     rbp, [rsp-180h]
0x180129224  sub     rsp, 280h
0x18012922b  mov     rax, cs:__security_cookie
0x180129232  xor     rax, rsp
0x180129235  mov     [rbp+190h+var_20], rax
0x18012923c  mov     rdi, r8
0x18012923f  mov     rsi, rdx
0x180129242  mov     [rsp+290h+hKey], 0
0x18012924b  mov     [rsp+290h+hkey], 0
0x180129254  mov     ebx, 208h
0x180129259  mov     r8d, ebx; Size
0x18012925c  xor     edx, edx; Val
0x18012925e  lea     rcx, [rsp+290h+var_230]; void *
0x180129263  call    memset_0
0x180129268  mov     [rsp+290h+var_240], ebx
0x18012926c  mov     qword ptr [rdi+10h], 0
0x180129274  mov     rcx, rdi
0x180129277  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012927c  xor     ecx, ecx
0x18012927e  mov     [rax], cx
0x180129281  mov     rbx, [rsp+290h+hKey]
0x180129286  test    rbx, rbx
0x180129289  jz      short loc_1801292A8
0x18012928b  lea     rcx, [rsp+290h+var_238]; this
0x180129290  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180129295  mov     rcx, rbx; hKey
0x180129298  call    cs:__imp_RegCloseKey
0x18012929e  lea     rcx, [rsp+290h+var_238]; this
0x1801292a3  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801292a8  mov     [rsp+290h+hKey], 0
0x1801292b1  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1801292b6  lea     rcx, [rsp+290h+hKey]
0x1801292bb  mov     [rsp+290h+phkResult], rcx; phkResult
0x1801292c0  mov     r9d, 20019h; samDesired
0x1801292c6  xor     r8d, r8d; ulOptions
0x1801292c9  mov     rdx, rax; lpSubKey
0x1801292cc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801292d3  call    cs:__imp_RegOpenKeyExW
0x1801292d9  test    eax, eax
0x1801292db  jz      short loc_1801292E4
0x1801292dd  mov     edx, 0A3h
0x1801292e2  jmp     short loc_18012933E
0x1801292e4  mov     rbx, [rsp+290h+hkey]
0x1801292e9  test    rbx, rbx
0x1801292ec  jz      short loc_18012930B
0x1801292ee  lea     rcx, [rsp+290h+var_238]; this
0x1801292f3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801292f8  mov     rcx, rbx; hKey
0x1801292fb  call    cs:__imp_RegCloseKey
0x180129301  lea     rcx, [rsp+290h+var_238]; this
0x180129306  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18012930b  mov     [rsp+290h+hkey], 0
0x180129314  lea     rax, [rsp+290h+hkey]
0x180129319  mov     [rsp+290h+phkResult], rax; unsigned int
0x18012931e  mov     r9d, 20019h; samDesired
0x180129324  xor     r8d, r8d; ulOptions
0x180129327  mov     rdx, rsi; lpSubKey
0x18012932a  mov     rcx, [rsp+290h+hKey]; hKey
0x18012932f  call    cs:__imp_RegOpenKeyExW
0x180129335  test    eax, eax
0x180129337  jz      short loc_180129358
0x180129339  mov     edx, 0A4h; void *
0x18012933e  mov     rcx, [rbp+198h]; this
0x180129345  mov     r9d, eax; char *
0x180129348  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012934f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180129354  mov     ebx, eax
0x180129356  jmp     short loc_1801293B3
0x180129358  lea     rax, [rsp+290h+var_240]
0x18012935d  mov     [rsp+290h+pcbData], rax; pcbData
0x180129362  lea     rax, [rsp+290h+var_230]
0x180129367  mov     [rsp+290h+pvData], rax; pvData
0x18012936c  mov     [rsp+290h+phkResult], 0; pdwType
0x180129375  mov     r9d, 2; dwFlags
0x18012937b  lea     r8, aLinkedenrollme_1; "LinkedEnrollmentId"
0x180129382  lea     rdx, aLinkedenrollme; "LinkedEnrollment"
0x180129389  mov     rcx, [rsp+290h+hkey]; hkey
0x18012938e  call    cs:__imp_RegGetValueW
0x180129394  cmp     eax, 2
0x180129397  jz      short loc_1801293B1
0x180129399  test    eax, eax
0x18012939b  jz      short loc_1801293A4
0x18012939d  mov     edx, 0ABh
0x1801293a2  jmp     short loc_18012933E
0x1801293a4  lea     rdx, [rsp+290h+var_230]
0x1801293a9  mov     rcx, rdi
0x1801293ac  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801293b1  xor     ebx, ebx
0x1801293b3  lea     rcx, [rsp+290h+hkey]
0x1801293b8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801293bd  nop
0x1801293be  lea     rcx, [rsp+290h+hKey]
0x1801293c3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801293c8  mov     eax, ebx
0x1801293ca  mov     rcx, [rbp+190h+var_20]
0x1801293d1  xor     rcx, rsp; StackCookie
0x1801293d4  call    __security_check_cookie
0x1801293d9  mov     rbx, [rsp+290h+arg_0]
0x1801293e1  add     rsp, 280h
0x1801293e8  pop     rdi
0x1801293e9  pop     rsi
0x1801293ea  pop     rbp
0x1801293eb  retn
```
