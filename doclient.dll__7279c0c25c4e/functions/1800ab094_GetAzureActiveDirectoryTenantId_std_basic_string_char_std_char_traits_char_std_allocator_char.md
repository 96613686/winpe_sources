# GetAzureActiveDirectoryTenantId(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x1800ab094`
- end: `0x1800ab20f`
- name: `?GetAzureActiveDirectoryTenantId@@YAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800d68a8`

## callees

- `0x18000933c`
- `0x1800095a0`
- `0x1800179a4`
- `0x1800a1ea4`
- `0x1800a98f8`
- `0x1800ab094`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ab102`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ab11e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ab102`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ab11e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ab1e4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ab1e4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800ab0e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800ab0e1`

## string_xrefs

- `0x1800ab0da`: `Netapi32.dll`
- `0x1800ab1c2`: `GetAzureActiveDirectoryTenantId`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetAzureActiveDirectoryTenantId(const char *a1)
{
  const char *v1; // rsi
  const char *v2; // rax
  HMODULE Library; // rax
  HMODULE v4; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v6; // rbp
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rax
  int v11; // [rsp+20h] [rbp-58h]
  _QWORD v12[4]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v13; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v1 = a1;
  *((_QWORD *)a1 + 2) = 0;
  v2 = a1;
  if ( *((_QWORD *)a1 + 3) > 0xFu )
    v2 = *(const char **)a1;
  *v2 = 0;
  Library = LoadLibraryExA("Netapi32.dll", 0, 0x800u);
  v4 = Library;
  if ( !Library )
    goto LABEL_12;
  ProcAddress = GetProcAddress(Library, "NetGetAadJoinInformation");
  if ( !ProcAddress )
    goto LABEL_12;
  v6 = GetProcAddress(v4, "NetFreeAadJoinInformation");
  if ( !v6 )
    goto LABEL_12;
  v13 = 0;
  v7 = ((__int64 (__fastcall *)(_QWORD, __int64 *))ProcAddress)(0, &v13);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
      (const char *)(unsigned int)v7,
      v11);
    goto LABEL_13;
  }
  if ( v13 )
  {
    v9 = WstrToUTF8(v12, *(_QWORD *)(v13 + 32), 0);
    std::string::operator=(v1, v9);
    std::string::~string(v12);
    ((void (__fastcall *)(__int64))v6)(v13);
    if ( *((_QWORD *)v1 + 3) > 0xFu )
      v1 = *(const char **)v1;
    LogMessage(5u, "GetAzureActiveDirectoryTenantId", 0x12Du, "szID = %s", v1);
    v8 = 0;
  }
  else
  {
LABEL_12:
    v8 = -2147023728;
  }
LABEL_13:
  if ( v4 )
    FreeLibrary(v4);
  return v8;
}

```

## disassembly

```asm
0x1800ab094  mov     [rsp+arg_8], rbx
0x1800ab099  mov     [rsp+arg_10], rbp
0x1800ab09e  mov     [rsp+arg_18], rsi
0x1800ab0a3  push    rdi
0x1800ab0a4  sub     rsp, 70h
0x1800ab0a8  mov     rax, cs:__security_cookie
0x1800ab0af  xor     rax, rsp
0x1800ab0b2  mov     [rsp+78h+var_18], rax
0x1800ab0b7  mov     rsi, rcx
0x1800ab0ba  mov     qword ptr [rcx+10h], 0
0x1800ab0c2  mov     rax, rcx
0x1800ab0c5  cmp     qword ptr [rcx+18h], 0Fh
0x1800ab0ca  jbe     short loc_1800AB0CF
0x1800ab0cc  mov     rax, [rcx]
0x1800ab0cf  mov     byte ptr [rax], 0
0x1800ab0d2  xor     edx, edx; hFile
0x1800ab0d4  mov     r8d, 800h; dwFlags
0x1800ab0da  lea     rcx, aNetapi32Dll; "Netapi32.dll"
0x1800ab0e1  call    cs:__imp_LoadLibraryExA
0x1800ab0e7  mov     rbx, rax
0x1800ab0ea  mov     [rsp+78h+var_48], rax
0x1800ab0ef  test    rax, rax
0x1800ab0f2  jz      loc_1800AB1D7
0x1800ab0f8  lea     rdx, aNetgetaadjoini; "NetGetAadJoinInformation"
0x1800ab0ff  mov     rcx, rax; hModule
0x1800ab102  call    cs:__imp_GetProcAddress
0x1800ab108  mov     rdi, rax
0x1800ab10b  test    rax, rax
0x1800ab10e  jz      loc_1800AB1D7
0x1800ab114  lea     rdx, aNetfreeaadjoin; "NetFreeAadJoinInformation"
0x1800ab11b  mov     rcx, rbx; hModule
0x1800ab11e  call    cs:__imp_GetProcAddress
0x1800ab124  mov     rbp, rax
0x1800ab127  test    rax, rax
0x1800ab12a  jz      loc_1800AB1D7
0x1800ab130  mov     [rsp+78h+var_20], 0
0x1800ab139  lea     rdx, [rsp+78h+var_20]
0x1800ab13e  xor     ecx, ecx
0x1800ab140  mov     rax, rdi
0x1800ab143  call    _guard_dispatch_icall
0x1800ab148  mov     edi, eax
0x1800ab14a  test    eax, eax
0x1800ab14c  jns     short loc_1800AB169
0x1800ab14e  mov     rcx, [rsp+78h]; this
0x1800ab153  mov     r9d, eax; char *
0x1800ab156  lea     r8, aCW1SSrcDeliver_8; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ab15d  mov     edx, 128h; void *
0x1800ab162  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab167  jmp     short loc_1800AB1DC
0x1800ab169  mov     rdx, [rsp+78h+var_20]
0x1800ab16e  test    rdx, rdx
0x1800ab171  jz      short loc_1800AB1D7
0x1800ab173  xor     r8d, r8d
0x1800ab176  mov     rdx, [rdx+20h]
0x1800ab17a  lea     rcx, [rsp+78h+var_40]
0x1800ab17f  call    ?WstrToUTF8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_K@Z; WstrToUTF8(wchar_t const *,unsigned __int64)
0x1800ab184  mov     rdx, rax
0x1800ab187  mov     rcx, rsi
0x1800ab18a  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800ab18f  lea     rcx, [rsp+78h+var_40]; void *
0x1800ab194  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ab199  mov     rcx, [rsp+78h+var_20]
0x1800ab19e  mov     rax, rbp
0x1800ab1a1  call    _guard_dispatch_icall
0x1800ab1a6  cmp     qword ptr [rsi+18h], 0Fh
0x1800ab1ab  jbe     short loc_1800AB1B0
0x1800ab1ad  mov     rsi, [rsi]
0x1800ab1b0  mov     qword ptr [rsp+78h+var_58], rsi
0x1800ab1b5  lea     r9, aSzidS; "szID = %s"
0x1800ab1bc  mov     r8d, 12Dh; unsigned int
0x1800ab1c2  lea     rdx, aGetazureactive; "GetAzureActiveDirectoryTenantId"
0x1800ab1c9  mov     ecx, 5; unsigned __int8
0x1800ab1ce  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800ab1d3  xor     edi, edi
0x1800ab1d5  jmp     short loc_1800AB1DC
0x1800ab1d7  mov     edi, 80070490h
0x1800ab1dc  test    rbx, rbx
0x1800ab1df  jz      short loc_1800AB1EA
0x1800ab1e1  mov     rcx, rbx; hLibModule
0x1800ab1e4  call    cs:__imp_FreeLibrary
0x1800ab1ea  mov     eax, edi
0x1800ab1ec  mov     rcx, [rsp+78h+var_18]
0x1800ab1f1  xor     rcx, rsp; StackCookie
0x1800ab1f4  call    __security_check_cookie
0x1800ab1f9  lea     r11, [rsp+78h+var_8]
0x1800ab1fe  mov     rbx, [r11+18h]
0x1800ab202  mov     rbp, [r11+20h]
0x1800ab206  mov     rsi, [r11+28h]
0x1800ab20a  mov     rsp, r11
0x1800ab20d  pop     rdi
0x1800ab20e  retn
```
