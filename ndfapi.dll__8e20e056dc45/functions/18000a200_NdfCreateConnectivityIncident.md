# NdfCreateConnectivityIncident

- ea: `0x18000a200`
- end: `0x18000a308`
- name: `NdfCreateConnectivityIncident`
- size: `264`
- prototype: `HRESULT __stdcall(NDFHANDLE *handle)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800095c0`
- `0x180010054`

## callees

- `0x18000721c`
- `0x1800098b0`
- `0x18000a200`
- `0x18000a9e0`
- `0x18001f690`

## import_xrefs

- `wdi!WdiCancel` at `0x18000a263`
- `wdi!WdiCancel` at `0x18000a263`

## string_xrefs

- `0x18000a24b`: `NdfCreateConnectivityIncident`

## pseudocode

```c
HRESULT __stdcall NdfCreateConnectivityIncident(NDFHANDLE *handle)
{
  HRESULT result; // eax
  size_t v3[4]; // [rsp+20h] [rbp-E0h] BYREF
  HELPER_ATTRIBUTE attributes; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v5; // [rsp+D0h] [rbp-30h]
  int v6; // [rsp+D8h] [rbp-28h]
  int v7; // [rsp+E0h] [rbp-20h]

  v3[3] = 15;
  v3[2] = 0;
  LOBYTE(v3[0]) = 0;
  std::string::assign(v3, "NdfCreateConnectivityIncident", 0x1Du);
  TelemeterAPICall(v3);
  if ( (unsigned int)WdiCancel(0) == -2147023611 )
    return -2147467260;
  if ( !handle )
    return -2146895611;
  attributes.type = AT_STRING;
  attributes.pwszName = L"URL";
  v6 = 1;
  attributes.Int64 = (LONGLONG)&qword_180026B78;
  v7 = 1;
  v5 = L"UseWinHTTP";
  result = NdfCreateIncident(L"WinInetHelperClass", 2u, &attributes, handle);
  if ( result >= 0 )
  {
    if ( *handle )
      *((_DWORD *)*handle + 4) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000a200  mov     [rsp-8+arg_8], rbx
0x18000a205  push    rbp
0x18000a206  lea     rbp, [rsp-100h]
0x18000a20e  sub     rsp, 200h
0x18000a215  mov     rax, cs:__security_cookie
0x18000a21c  xor     rax, rsp
0x18000a21f  mov     [rbp+100h+var_10], rax
0x18000a226  mov     rbx, rcx
0x18000a229  mov     [rsp+200h+var_1C8], 0Fh
0x18000a232  lea     rcx, [rsp+200h+var_1E0]; void *
0x18000a237  mov     [rsp+200h+var_1D0], 0
0x18000a240  mov     r8d, 1Dh; Size
0x18000a246  mov     [rsp+200h+var_1E0], 0
0x18000a24b  lea     rdx, aNdfcreateconne_0; "NdfCreateConnectivityIncident"
0x18000a252  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x18000a257  lea     rcx, [rsp+200h+var_1E0]
0x18000a25c  call    ?TelemeterAPICall@@YAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; TelemeterAPICall(std::string)
0x18000a261  xor     ecx, ecx
0x18000a263  call    cs:__imp_WdiCancel
0x18000a269  cmp     eax, 80070505h
0x18000a26e  jnz     short loc_18000A277
0x18000a270  mov     eax, 80004004h
0x18000a275  jmp     short loc_18000A2E8
0x18000a277  test    rbx, rbx
0x18000a27a  jnz     short loc_18000A283
0x18000a27c  mov     eax, 8008F905h
0x18000a281  jmp     short loc_18000A2E8
0x18000a283  lea     rax, aUrl; "URL"
0x18000a28a  mov     [rsp+200h+attributes.type], 0Ah
0x18000a292  mov     [rsp+200h+attributes.pwszName], rax
0x18000a297  lea     r8, [rsp+200h+attributes]; attributes
0x18000a29c  lea     rax, qword_180026B78
0x18000a2a3  mov     [rbp+100h+var_128], 1
0x18000a2aa  mov     qword ptr [rsp+200h+attributes.10h], rax
0x18000a2af  lea     rcx, helperClassName; "WinInetHelperClass"
0x18000a2b6  lea     rax, aUsewinhttp; "UseWinHTTP"
0x18000a2bd  mov     [rbp+100h+var_120], 1
0x18000a2c4  mov     r9, rbx; handle
0x18000a2c7  mov     [rbp+100h+var_130], rax
0x18000a2cb  mov     edx, 2; celt
0x18000a2d0  call    NdfCreateIncident
0x18000a2d5  test    eax, eax
0x18000a2d7  js      short loc_18000A2E8
0x18000a2d9  mov     rcx, [rbx]
0x18000a2dc  test    rcx, rcx
0x18000a2df  jz      short loc_18000A2E8
0x18000a2e1  mov     dword ptr [rcx+10h], 1
0x18000a2e8  mov     rcx, [rbp+100h+var_10]
0x18000a2ef  xor     rcx, rsp; StackCookie
0x18000a2f2  call    __security_check_cookie
0x18000a2f7  mov     rbx, [rsp+200h+arg_8]
0x18000a2ff  add     rsp, 200h
0x18000a306  pop     rbp
0x18000a307  retn
```
