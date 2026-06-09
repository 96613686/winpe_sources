# NdfCreateSharingIncident

- ea: `0x18000afb0`
- end: `0x18000b0d9`
- name: `NdfCreateSharingIncident`
- size: `297`
- prototype: `HRESULT __stdcall(LPCWSTR UNCPath, NDFHANDLE *handle)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180010664`

## callees

- `0x18000721c`
- `0x1800098b0`
- `0x18000a9e0`
- `0x18000afb0`
- `0x18001f690`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18000b068`
- `KERNEL32!GetModuleFileNameW` at `0x18000b068`
- `wdi!WdiCancel` at `0x18000b01b`
- `wdi!WdiCancel` at `0x18000b01b`

## string_xrefs

- `0x18000aff3`: `NdfCreateSharingIncident`
- `0x18000b03e`: `UNCPath`

## pseudocode

```c
HRESULT __stdcall NdfCreateSharingIncident(LPCWSTR UNCPath, NDFHANDLE *handle)
{
  HRESULT result; // eax
  ULONG v5; // edi
  size_t v6[4]; // [rsp+20h] [rbp-E0h] BYREF
  HELPER_ATTRIBUTE attributes; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v8; // [rsp+D0h] [rbp-30h]
  int v9; // [rsp+D8h] [rbp-28h]
  WCHAR *v10; // [rsp+E0h] [rbp-20h]
  WCHAR Filename[264]; // [rsp+160h] [rbp+60h] BYREF

  v6[3] = 15;
  v6[2] = 0;
  LOBYTE(v6[0]) = 0;
  std::string::assign(v6, "NdfCreateSharingIncident", 0x18u);
  TelemeterAPICall(v6);
  if ( (unsigned int)WdiCancel(0) == -2147023611 )
    return -2147467260;
  if ( !handle )
    return -2146895611;
  attributes.Int64 = (LONGLONG)UNCPath;
  attributes.pwszName = L"UNCPath";
  attributes.type = AT_STRING;
  v5 = 1;
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    v9 = 10;
    v8 = L"AppID";
    v5 = 2;
    v10 = Filename;
  }
  result = NdfCreateIncident(L"SMBHelperClass", v5, &attributes, handle);
  if ( result >= 0 )
    *((_DWORD *)*handle + 4) = 3;
  return result;
}

```

## disassembly

```asm
0x18000afb0  mov     [rsp-8+arg_0], rbx
0x18000afb5  mov     [rsp-8+arg_10], rdi
0x18000afba  push    rbp
0x18000afbb  lea     rbp, [rsp-280h]
0x18000afc3  sub     rsp, 380h
0x18000afca  mov     rax, cs:__security_cookie
0x18000afd1  xor     rax, rsp
0x18000afd4  mov     [rbp+280h+var_10], rax
0x18000afdb  mov     rbx, rdx
0x18000afde  mov     [rsp+380h+var_348], 0Fh
0x18000afe7  mov     rdi, rcx
0x18000afea  mov     [rsp+380h+var_350], 0
0x18000aff3  lea     rdx, aNdfcreateshari_0; "NdfCreateSharingIncident"
0x18000affa  mov     [rsp+380h+var_360], 0
0x18000afff  lea     rcx, [rsp+380h+var_360]; void *
0x18000b004  mov     r8d, 18h; Size
0x18000b00a  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x18000b00f  lea     rcx, [rsp+380h+var_360]
0x18000b014  call    ?TelemeterAPICall@@YAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; TelemeterAPICall(std::string)
0x18000b019  xor     ecx, ecx
0x18000b01b  call    cs:__imp_WdiCancel
0x18000b021  cmp     eax, 80070505h
0x18000b026  jnz     short loc_18000B032
0x18000b028  mov     eax, 80004004h
0x18000b02d  jmp     loc_18000B0B5
0x18000b032  test    rbx, rbx
0x18000b035  jnz     short loc_18000B03E
0x18000b037  mov     eax, 8008F905h
0x18000b03c  jmp     short loc_18000B0B5
0x18000b03e  lea     rax, aUncpath; "UNCPath"
0x18000b045  mov     qword ptr [rsp+380h+attributes.10h], rdi
0x18000b04a  mov     r8d, 104h; nSize
0x18000b050  mov     [rsp+380h+attributes.pwszName], rax
0x18000b055  lea     rdx, [rbp+280h+Filename]; lpFilename
0x18000b059  mov     [rsp+380h+attributes.type], 0Ah
0x18000b061  xor     ecx, ecx; hModule
0x18000b063  mov     edi, 1
0x18000b068  call    cs:__imp_GetModuleFileNameW
0x18000b06e  test    eax, eax
0x18000b070  jz      short loc_18000B091
0x18000b072  lea     rax, aAppid_1; "AppID"
0x18000b079  mov     [rbp+280h+var_2A8], 0Ah
0x18000b080  mov     [rbp+280h+var_2B0], rax
0x18000b084  mov     edi, 2
0x18000b089  lea     rax, [rbp+280h+Filename]
0x18000b08d  mov     [rbp+280h+var_2A0], rax
0x18000b091  mov     r9, rbx; handle
0x18000b094  lea     r8, [rsp+380h+attributes]; attributes
0x18000b099  mov     edx, edi; celt
0x18000b09b  lea     rcx, aSmbhelperclass; "SMBHelperClass"
0x18000b0a2  call    NdfCreateIncident
0x18000b0a7  test    eax, eax
0x18000b0a9  js      short loc_18000B0B5
0x18000b0ab  mov     rcx, [rbx]
0x18000b0ae  mov     dword ptr [rcx+10h], 3
0x18000b0b5  mov     rcx, [rbp+280h+var_10]
0x18000b0bc  xor     rcx, rsp; StackCookie
0x18000b0bf  call    __security_check_cookie
0x18000b0c4  lea     r11, [rsp+380h+var_s0]
0x18000b0cc  mov     rbx, [r11+10h]
0x18000b0d0  mov     rdi, [r11+20h]
0x18000b0d4  mov     rsp, r11
0x18000b0d7  pop     rbp
0x18000b0d8  retn
```
