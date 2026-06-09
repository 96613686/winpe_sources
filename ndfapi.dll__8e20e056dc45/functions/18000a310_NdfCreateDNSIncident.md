# NdfCreateDNSIncident

- ea: `0x18000a310`
- end: `0x18000a45b`
- name: `NdfCreateDNSIncident`
- size: `331`
- prototype: `HRESULT __stdcall(LPCWSTR hostname, WORD queryType, NDFHANDLE *handle)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000721c`
- `0x1800098b0`
- `0x18000a310`
- `0x18000a9e0`
- `0x18001f690`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18000a3e4`
- `KERNEL32!GetModuleFileNameW` at `0x18000a3e4`
- `wdi!WdiCancel` at `0x18000a378`
- `wdi!WdiCancel` at `0x18000a378`

## string_xrefs

- `0x18000a35b`: `NdfCreateDNSIncident`

## pseudocode

```c
HRESULT __stdcall NdfCreateDNSIncident(LPCWSTR hostname, WORD queryType, NDFHANDLE *handle)
{
  HRESULT result; // eax
  ULONG v7; // edi
  size_t v8[4]; // [rsp+20h] [rbp-E0h] BYREF
  HELPER_ATTRIBUTE attributes; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v10; // [rsp+D0h] [rbp-30h]
  int v11; // [rsp+D8h] [rbp-28h]
  WORD v12; // [rsp+E0h] [rbp-20h]
  const wchar_t *v13; // [rsp+160h] [rbp+60h]
  int v14; // [rsp+168h] [rbp+68h]
  WCHAR *v15; // [rsp+170h] [rbp+70h]
  WCHAR Filename[264]; // [rsp+1F0h] [rbp+F0h] BYREF

  v8[3] = 15;
  v8[2] = 0;
  LOBYTE(v8[0]) = 0;
  std::string::assign(v8, "NdfCreateDNSIncident", 0x14u);
  TelemeterAPICall(v8);
  if ( (unsigned int)WdiCancel(0) == -2147023611 )
    return -2147467260;
  if ( !hostname || !handle )
    return -2146895611;
  attributes.Int64 = (LONGLONG)hostname;
  attributes.pwszName = L"QueryName";
  attributes.type = AT_STRING;
  v10 = L"QueryType";
  v11 = 5;
  v12 = queryType;
  v7 = 2;
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    v14 = 10;
    v13 = L"AppID";
    v7 = 3;
    v15 = Filename;
  }
  result = NdfCreateIncident(L"DnsHelperClass", v7, &attributes, handle);
  if ( result >= 0 )
  {
    if ( *handle )
      *((_DWORD *)*handle + 4) = 4;
  }
  return result;
}

```

## disassembly

```asm
0x18000a310  push    rbp
0x18000a312  push    rbx
0x18000a313  push    rsi
0x18000a314  push    rdi
0x18000a315  lea     rbp, [rsp-318h]
0x18000a31d  sub     rsp, 418h
0x18000a324  mov     rax, cs:__security_cookie
0x18000a32b  xor     rax, rsp
0x18000a32e  mov     [rbp+330h+var_30], rax
0x18000a335  mov     rbx, r8
0x18000a338  mov     [rsp+430h+var_3F8], 0Fh
0x18000a341  movzx   esi, dx
0x18000a344  mov     [rsp+430h+var_400], 0
0x18000a34d  mov     rdi, rcx
0x18000a350  mov     [rsp+430h+var_410], 0
0x18000a355  mov     r8d, 14h; Size
0x18000a35b  lea     rdx, aNdfcreatednsin_0; "NdfCreateDNSIncident"
0x18000a362  lea     rcx, [rsp+430h+var_410]; void *
0x18000a367  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x18000a36c  lea     rcx, [rsp+430h+var_410]
0x18000a371  call    ?TelemeterAPICall@@YAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; TelemeterAPICall(std::string)
0x18000a376  xor     ecx, ecx
0x18000a378  call    cs:__imp_WdiCancel
0x18000a37e  cmp     eax, 80070505h
0x18000a383  jnz     short loc_18000A38F
0x18000a385  mov     eax, 80004004h
0x18000a38a  jmp     loc_18000A440
0x18000a38f  test    rdi, rdi
0x18000a392  jz      loc_18000A43B
0x18000a398  test    rbx, rbx
0x18000a39b  jz      loc_18000A43B
0x18000a3a1  lea     rax, aQueryname; "QueryName"
0x18000a3a8  mov     qword ptr [rsp+430h+attributes.10h], rdi
0x18000a3ad  mov     [rsp+430h+attributes.pwszName], rax
0x18000a3b2  lea     rdx, [rbp+330h+Filename]; lpFilename
0x18000a3b9  lea     rax, aQuerytype; "QueryType"
0x18000a3c0  mov     [rsp+430h+attributes.type], 0Ah
0x18000a3c8  mov     r8d, 104h; nSize
0x18000a3ce  mov     [rbp+330h+var_360], rax
0x18000a3d2  xor     ecx, ecx; hModule
0x18000a3d4  mov     [rbp+330h+var_358], 5
0x18000a3db  mov     [rbp+330h+var_350], si
0x18000a3df  mov     edi, 2
0x18000a3e4  call    cs:__imp_GetModuleFileNameW
0x18000a3ea  test    eax, eax
0x18000a3ec  jz      short loc_18000A410
0x18000a3ee  lea     rax, aAppid_1; "AppID"
0x18000a3f5  mov     [rbp+330h+var_2C8], 0Ah
0x18000a3fc  mov     [rbp+330h+var_2D0], rax
0x18000a400  mov     edi, 3
0x18000a405  lea     rax, [rbp+330h+Filename]
0x18000a40c  mov     [rbp+330h+var_2C0], rax
0x18000a410  mov     r9, rbx; handle
0x18000a413  lea     r8, [rsp+430h+attributes]; attributes
0x18000a418  mov     edx, edi; celt
0x18000a41a  lea     rcx, aDnshelperclass; "DnsHelperClass"
0x18000a421  call    NdfCreateIncident
0x18000a426  test    eax, eax
0x18000a428  js      short loc_18000A440
0x18000a42a  mov     rcx, [rbx]
0x18000a42d  test    rcx, rcx
0x18000a430  jz      short loc_18000A440
0x18000a432  mov     dword ptr [rcx+10h], 4
0x18000a439  jmp     short loc_18000A440
0x18000a43b  mov     eax, 8008F905h
0x18000a440  mov     rcx, [rbp+330h+var_30]
0x18000a447  xor     rcx, rsp; StackCookie
0x18000a44a  call    __security_check_cookie
0x18000a44f  add     rsp, 418h
0x18000a456  pop     rdi
0x18000a457  pop     rsi
0x18000a458  pop     rbx
0x18000a459  pop     rbp
0x18000a45a  retn
```
