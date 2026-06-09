# NdfCreateWebIncidentEx

- ea: `0x18000b240`
- end: `0x18000b3ba`
- name: `NdfCreateWebIncidentEx`
- size: `378`
- prototype: `HRESULT __stdcall(LPCWSTR url, BOOL useWinHTTP, LPWSTR moduleName, NDFHANDLE *handle)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000721c`
- `0x1800098b0`
- `0x18000a9e0`
- `0x18000b240`
- `0x18001f690`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18000b33a`
- `KERNEL32!GetModuleFileNameW` at `0x18000b33a`
- `wdi!WdiCancel` at `0x18000b2b4`
- `wdi!WdiCancel` at `0x18000b2b4`

## string_xrefs

- `0x18000b294`: `NdfCreateWebIncidentEx`

## pseudocode

```c
HRESULT __stdcall NdfCreateWebIncidentEx(LPCWSTR url, BOOL useWinHTTP, LPWSTR moduleName, NDFHANDLE *handle)
{
  HRESULT result; // eax
  ULONG v9; // ebx
  size_t v10[4]; // [rsp+20h] [rbp-E0h] BYREF
  HELPER_ATTRIBUTE attributes; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v12; // [rsp+D0h] [rbp-30h]
  int v13; // [rsp+D8h] [rbp-28h]
  BOOL v14; // [rsp+E0h] [rbp-20h]
  const wchar_t *v15; // [rsp+160h] [rbp+60h]
  int v16; // [rsp+168h] [rbp+68h]
  LPWSTR v17; // [rsp+170h] [rbp+70h]
  WCHAR Filename[264]; // [rsp+1F0h] [rbp+F0h] BYREF

  v10[3] = 15;
  v10[2] = 0;
  LOBYTE(v10[0]) = 0;
  std::string::assign(v10, "NdfCreateWebIncidentEx", 0x16u);
  TelemeterAPICall(v10);
  if ( (unsigned int)WdiCancel(0) == -2147023611 )
    return -2147467260;
  if ( !url || !handle )
    return -2146895611;
  v14 = useWinHTTP;
  attributes.pwszName = L"URL";
  v12 = L"UseWinHTTP";
  attributes.type = AT_STRING;
  attributes.Int64 = (LONGLONG)url;
  v13 = 1;
  if ( moduleName )
  {
    v17 = moduleName;
    v15 = L"AppID";
  }
  else
  {
    v9 = 2;
    if ( !GetModuleFileNameW(0, Filename, 0x104u) )
      goto LABEL_10;
    v15 = L"AppID";
    v17 = Filename;
  }
  v9 = 3;
  v16 = 10;
LABEL_10:
  result = NdfCreateIncident(L"WinInetHelperClass", v9, &attributes, handle);
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
0x18000b240  mov     [rsp-8+arg_0], rbx
0x18000b245  mov     [rsp-8+arg_8], rsi
0x18000b24a  push    rbp
0x18000b24b  push    rdi
0x18000b24c  push    r14
0x18000b24e  lea     rbp, [rsp-310h]
0x18000b256  sub     rsp, 410h
0x18000b25d  mov     rax, cs:__security_cookie
0x18000b264  xor     rax, rsp
0x18000b267  mov     [rbp+320h+var_20], rax
0x18000b26e  mov     rsi, r8
0x18000b271  mov     [rsp+420h+var_3E8], 0Fh
0x18000b27a  mov     r14d, edx
0x18000b27d  mov     [rsp+420h+var_3F0], 0
0x18000b286  mov     rbx, rcx
0x18000b289  mov     [rsp+420h+var_400], 0
0x18000b28e  mov     r8d, 16h; Size
0x18000b294  lea     rdx, aNdfcreatewebin_2; "NdfCreateWebIncidentEx"
0x18000b29b  lea     rcx, [rsp+420h+var_400]; void *
0x18000b2a0  mov     rdi, r9
0x18000b2a3  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x18000b2a8  lea     rcx, [rsp+420h+var_400]
0x18000b2ad  call    ?TelemeterAPICall@@YAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; TelemeterAPICall(std::string)
0x18000b2b2  xor     ecx, ecx
0x18000b2b4  call    cs:__imp_WdiCancel
0x18000b2ba  cmp     eax, 80070505h
0x18000b2bf  jnz     short loc_18000B2CB
0x18000b2c1  mov     eax, 80004004h
0x18000b2c6  jmp     loc_18000B393
0x18000b2cb  test    rbx, rbx
0x18000b2ce  jz      loc_18000B38E
0x18000b2d4  test    rdi, rdi
0x18000b2d7  jz      loc_18000B38E
0x18000b2dd  mov     [rbp+320h+var_340], r14d
0x18000b2e1  lea     rax, aUrl; "URL"
0x18000b2e8  mov     [rsp+420h+attributes.pwszName], rax
0x18000b2ed  lea     rax, aUsewinhttp; "UseWinHTTP"
0x18000b2f4  mov     [rbp+320h+var_350], rax
0x18000b2f8  mov     r14d, 2
0x18000b2fe  mov     [rsp+420h+attributes.type], 0Ah
0x18000b306  mov     qword ptr [rsp+420h+attributes.10h], rbx
0x18000b30b  mov     [rbp+320h+var_348], 1
0x18000b312  test    rsi, rsi
0x18000b315  jz      short loc_18000B328
0x18000b317  lea     rax, aAppid_1; "AppID"
0x18000b31e  mov     [rbp+320h+var_2B0], rsi
0x18000b322  mov     [rbp+320h+var_2C0], rax
0x18000b326  jmp     short loc_18000B35A
0x18000b328  mov     r8d, 104h; nSize
0x18000b32e  lea     rdx, [rbp+320h+Filename]; lpFilename
0x18000b335  xor     ecx, ecx; hModule
0x18000b337  mov     ebx, r14d
0x18000b33a  call    cs:__imp_GetModuleFileNameW
0x18000b340  test    eax, eax
0x18000b342  jz      short loc_18000B366
0x18000b344  lea     rax, aAppid_1; "AppID"
0x18000b34b  mov     [rbp+320h+var_2C0], rax
0x18000b34f  lea     rax, [rbp+320h+Filename]
0x18000b356  mov     [rbp+320h+var_2B0], rax
0x18000b35a  mov     ebx, 3
0x18000b35f  mov     [rbp+320h+var_2B8], 0Ah
0x18000b366  mov     r9, rdi; handle
0x18000b369  lea     r8, [rsp+420h+attributes]; attributes
0x18000b36e  mov     edx, ebx; celt
0x18000b370  lea     rcx, helperClassName; "WinInetHelperClass"
0x18000b377  call    NdfCreateIncident
0x18000b37c  test    eax, eax
0x18000b37e  js      short loc_18000B393
0x18000b380  mov     rcx, [rdi]
0x18000b383  test    rcx, rcx
0x18000b386  jz      short loc_18000B393
0x18000b388  mov     [rcx+10h], r14d
0x18000b38c  jmp     short loc_18000B393
0x18000b38e  mov     eax, 8008F905h
0x18000b393  mov     rcx, [rbp+320h+var_20]
0x18000b39a  xor     rcx, rsp; StackCookie
0x18000b39d  call    __security_check_cookie
0x18000b3a2  lea     r11, [rsp+420h+var_10]
0x18000b3aa  mov     rbx, [r11+20h]
0x18000b3ae  mov     rsi, [r11+28h]
0x18000b3b2  mov     rsp, r11
0x18000b3b5  pop     r14
0x18000b3b7  pop     rdi
0x18000b3b8  pop     rbp
0x18000b3b9  retn
```
