# GetFullHostName

- ea: `0x180021444`
- end: `0x1800214fd`
- name: `GetFullHostName`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019310`

## callees

- `0x18000d5f4`
- `0x180021444`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800214ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800214ea`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800214c1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800214c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214cb`

## string_xrefs

- `0x18002145f`: `GetFullHostName (com\complus\dtc\dtc\msdtcprx\src\dtcinit.cpp@393): GetFullyQualitifedHostName, i_pTmInstance != NULL`
- `0x180021471`: `GetFullHostName (com\complus\dtc\dtc\msdtcprx\src\dtcinit.cpp@394): GetFullyQualitifedHostName, pszFullName != NULL`

## pseudocode

```c
__int64 __fastcall GetFullHostName(__int64 a1, CHAR *a2)
{
  signed int v3; // ebx
  signed int LastError; // eax
  LPCWCH lpWideCharStr; // [rsp+50h] [rbp+8h] BYREF

  lpWideCharStr = 0;
  if ( !a1 )
    DtcInternalErrorW(
      L"GetFullHostName (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinit.cpp@393): GetFullyQualitifedHostName, i_pTmInstance != NULL");
  if ( !a2 )
    DtcInternalErrorW(
      L"GetFullHostName (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinit.cpp@394): GetFullyQualitifedHostName, pszFullName != NULL");
  v3 = (*(__int64 (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)a1 + 48LL))(a1, &lpWideCharStr);
  if ( v3 >= 0 && !WideCharToMultiByte(0, 0, lpWideCharStr, -1, a2, 1026, 0, 0) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( lpWideCharStr )
    CoTaskMemFree((LPVOID)lpWideCharStr);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180021444  mov     [rsp+arg_8], rbx
0x180021449  push    rdi
0x18002144a  sub     rsp, 40h
0x18002144e  mov     [rsp+48h+lpWideCharStr], 0
0x180021457  mov     rdi, rdx
0x18002145a  test    rcx, rcx
0x18002145d  jnz     short loc_18002146C
0x18002145f  lea     rcx, aGetfullhostnam; "GetFullHostName (com\\complus\\dtc\\dtc"...
0x180021466  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18002146c  test    rdi, rdi
0x18002146f  jnz     short loc_18002147E
0x180021471  lea     rcx, aGetfullhostnam_0; "GetFullHostName (com\\complus\\dtc\\dtc"...
0x180021478  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18002147e  mov     rax, [rcx]
0x180021481  lea     rdx, [rsp+48h+lpWideCharStr]
0x180021486  mov     rax, [rax+30h]
0x18002148a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002148f  mov     ebx, eax
0x180021491  test    eax, eax
0x180021493  js      short loc_1800214E0
0x180021495  mov     r8, [rsp+48h+lpWideCharStr]; lpWideCharStr
0x18002149a  or      r9d, 0FFFFFFFFh; cchWideChar
0x18002149e  mov     [rsp+48h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800214a7  xor     edx, edx; dwFlags
0x1800214a9  mov     [rsp+48h+lpDefaultChar], 0; lpDefaultChar
0x1800214b2  xor     ecx, ecx; CodePage
0x1800214b4  mov     [rsp+48h+cbMultiByte], 402h; cbMultiByte
0x1800214bc  mov     [rsp+48h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800214c1  call    cs:__imp_WideCharToMultiByte
0x1800214c7  test    eax, eax
0x1800214c9  jnz     short loc_1800214E0
0x1800214cb  call    cs:__imp_GetLastError
0x1800214d1  mov     ebx, eax
0x1800214d3  test    eax, eax
0x1800214d5  jle     short loc_1800214E0
0x1800214d7  movzx   ebx, ax
0x1800214da  or      ebx, 80070000h
0x1800214e0  mov     rcx, [rsp+48h+lpWideCharStr]; pv
0x1800214e5  test    rcx, rcx
0x1800214e8  jz      short loc_1800214F0
0x1800214ea  call    cs:__imp_CoTaskMemFree
0x1800214f0  mov     eax, ebx
0x1800214f2  mov     rbx, [rsp+48h+arg_8]
0x1800214f7  add     rsp, 40h
0x1800214fb  pop     rdi
0x1800214fc  retn
```
