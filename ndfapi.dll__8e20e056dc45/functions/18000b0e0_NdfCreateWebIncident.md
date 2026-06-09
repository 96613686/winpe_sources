# NdfCreateWebIncident

- ea: `0x18000b0e0`
- end: `0x18000b235`
- name: `NdfCreateWebIncident`
- size: `341`
- prototype: `HRESULT __stdcall(LPCWSTR url, NDFHANDLE *handle)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000721c`
- `0x1800098b0`
- `0x18000a9e0`
- `0x18000b0e0`
- `0x18001f690`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18000b1b5`
- `KERNEL32!GetModuleFileNameW` at `0x18000b1b5`
- `wdi!WdiCancel` at `0x18000b14b`
- `wdi!WdiCancel` at `0x18000b14b`

## string_xrefs

- `0x18000b123`: `NdfCreateWebIncident`

## pseudocode

```c
HRESULT __stdcall NdfCreateWebIncident(LPCWSTR url, NDFHANDLE *handle)
{
  HRESULT result; // eax
  ULONG v5; // edi
  size_t v6[4]; // [rsp+20h] [rbp-E0h] BYREF
  HELPER_ATTRIBUTE attributes; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v8; // [rsp+D0h] [rbp-30h]
  int v9; // [rsp+D8h] [rbp-28h]
  int v10; // [rsp+E0h] [rbp-20h]
  const wchar_t *v11; // [rsp+160h] [rbp+60h]
  int v12; // [rsp+168h] [rbp+68h]
  WCHAR *v13; // [rsp+170h] [rbp+70h]
  WCHAR Filename[264]; // [rsp+1F0h] [rbp+F0h] BYREF

  v6[3] = 15;
  v6[2] = 0;
  LOBYTE(v6[0]) = 0;
  std::string::assign(v6, "NdfCreateWebIncident", 0x14u);
  TelemeterAPICall(v6);
  if ( (unsigned int)WdiCancel(0) == -2147023611 )
    return -2147467260;
  if ( !url || !handle )
    return -2146895611;
  attributes.Int64 = (LONGLONG)url;
  attributes.pwszName = L"URL";
  attributes.type = AT_STRING;
  v8 = L"UseWinHTTP";
  v9 = 1;
  v10 = 1;
  v5 = 2;
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    v12 = 10;
    v11 = L"AppID";
    v5 = 3;
    v13 = Filename;
  }
  result = NdfCreateIncident(L"WinInetHelperClass", v5, &attributes, handle);
  if ( result >= 0 )
  {
    if ( *handle )
      *((_DWORD *)*handle + 4) = 2;
  }
  return result;
}

```

## disassembly

```asm
0x18000b0e0  mov     [rsp-8+arg_0], rbx
0x18000b0e5  mov     [rsp-8+arg_10], rdi
0x18000b0ea  push    rbp
0x18000b0eb  lea     rbp, [rsp-310h]
0x18000b0f3  sub     rsp, 410h
0x18000b0fa  mov     rax, cs:__security_cookie
0x18000b101  xor     rax, rsp
0x18000b104  mov     [rbp+310h+var_10], rax
0x18000b10b  mov     rbx, rdx
0x18000b10e  mov     [rsp+410h+var_3D8], 0Fh
0x18000b117  mov     rdi, rcx
0x18000b11a  mov     [rsp+410h+var_3E0], 0
0x18000b123  lea     rdx, aNdfcreatewebin_1; "NdfCreateWebIncident"
0x18000b12a  mov     [rsp+410h+var_3F0], 0
0x18000b12f  lea     rcx, [rsp+410h+var_3F0]; void *
0x18000b134  mov     r8d, 14h; Size
0x18000b13a  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x18000b13f  lea     rcx, [rsp+410h+var_3F0]
0x18000b144  call    ?TelemeterAPICall@@YAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; TelemeterAPICall(std::string)
0x18000b149  xor     ecx, ecx
0x18000b14b  call    cs:__imp_WdiCancel
0x18000b151  cmp     eax, 80070505h
0x18000b156  jnz     short loc_18000B162
0x18000b158  mov     eax, 80004004h
0x18000b15d  jmp     loc_18000B211
0x18000b162  test    rdi, rdi
0x18000b165  jz      loc_18000B20C
0x18000b16b  test    rbx, rbx
0x18000b16e  jz      loc_18000B20C
0x18000b174  lea     rax, aUrl; "URL"
0x18000b17b  mov     qword ptr [rsp+410h+attributes.10h], rdi
0x18000b180  mov     [rsp+410h+attributes.pwszName], rax
0x18000b185  lea     rdx, [rbp+310h+Filename]; lpFilename
0x18000b18c  lea     rax, aUsewinhttp; "UseWinHTTP"
0x18000b193  mov     [rsp+410h+attributes.type], 0Ah
0x18000b19b  mov     [rbp+310h+var_340], rax
0x18000b19f  mov     r8d, 104h; nSize
0x18000b1a5  mov     eax, 1
0x18000b1aa  xor     ecx, ecx; hModule
0x18000b1ac  mov     [rbp+310h+var_338], eax
0x18000b1af  mov     [rbp+310h+var_330], eax
0x18000b1b2  lea     edi, [rax+1]
0x18000b1b5  call    cs:__imp_GetModuleFileNameW
0x18000b1bb  test    eax, eax
0x18000b1bd  jz      short loc_18000B1E1
0x18000b1bf  lea     rax, aAppid_1; "AppID"
0x18000b1c6  mov     [rbp+310h+var_2A8], 0Ah
0x18000b1cd  mov     [rbp+310h+var_2B0], rax
0x18000b1d1  mov     edi, 3
0x18000b1d6  lea     rax, [rbp+310h+Filename]
0x18000b1dd  mov     [rbp+310h+var_2A0], rax
0x18000b1e1  mov     r9, rbx; handle
0x18000b1e4  lea     r8, [rsp+410h+attributes]; attributes
0x18000b1e9  mov     edx, edi; celt
0x18000b1eb  lea     rcx, helperClassName; "WinInetHelperClass"
0x18000b1f2  call    NdfCreateIncident
0x18000b1f7  test    eax, eax
0x18000b1f9  js      short loc_18000B211
0x18000b1fb  mov     rcx, [rbx]
0x18000b1fe  test    rcx, rcx
0x18000b201  jz      short loc_18000B211
0x18000b203  mov     dword ptr [rcx+10h], 2
0x18000b20a  jmp     short loc_18000B211
0x18000b20c  mov     eax, 8008F905h
0x18000b211  mov     rcx, [rbp+310h+var_10]
0x18000b218  xor     rcx, rsp; StackCookie
0x18000b21b  call    __security_check_cookie
0x18000b220  lea     r11, [rsp+410h+var_s0]
0x18000b228  mov     rbx, [r11+10h]
0x18000b22c  mov     rdi, [r11+20h]
0x18000b230  mov     rsp, r11
0x18000b233  pop     rbp
0x18000b234  retn
```
