# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x180007418`
- end: `0x180007507`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `int(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009de8`

## callees

- `0x180006408`
- `0x180007418`
- `0x180018a80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180007474`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180007474`
- `ole32!CoGetObject` at `0x1800074dd`
- `ole32!CoGetObject` at `0x1800074dd`

## pseudocode

```c
HRESULT __fastcall CoCreateInstanceAsAdmin(HWND a1, const struct _GUID *a2, const struct _GUID *a3, void **a4)
{
  HRESULT result; // eax
  BIND_OPTS pBindOptions[3]; // [rsp+20h] [rbp-E0h] BYREF
  OLECHAR sz[56]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszName[304]; // [rsp+C0h] [rbp-40h] BYREF

  *a4 = 0;
  memset(pBindOptions, 0, sizeof(pBindOptions));
  if ( !StringFromGUID2(&CLSID_AdvancedSettingsWriter, sz, 50) )
    return -2147024882;
  result = StringCchPrintfW(
             pszName,
             0x12Cu,
             L"Elevation:Administrator!new:%s",
             sz,
             *(_QWORD *)&pBindOptions[0].cbStruct,
             *(_QWORD *)&pBindOptions[0].grfMode,
             *(_OWORD *)&pBindOptions[1],
             *(_OWORD *)&pBindOptions[2]);
  if ( result >= 0 )
  {
    pBindOptions[0].cbStruct = 48;
    *(_QWORD *)&pBindOptions[2].grfMode = a1;
    pBindOptions[1].grfFlags = 4;
    *(_OWORD *)&pBindOptions[0].grfFlags = 0;
    *(_OWORD *)&pBindOptions[1].grfMode = 0;
    return CoGetObject(pszName, pBindOptions, &GUID_5d703587_da7e_43c0_982c_2ba8e7ed341b, a4);
  }
  return result;
}

```

## disassembly

```asm
0x180007418  mov     [rsp-8+arg_8], rbx
0x18000741d  mov     [rsp-8+arg_10], rdi
0x180007422  push    rbp
0x180007423  lea     rbp, [rsp-230h]
0x18000742b  sub     rsp, 330h
0x180007432  mov     rax, cs:__security_cookie
0x180007439  xor     rax, rsp
0x18000743c  mov     [rbp+230h+var_10], rax
0x180007443  xorps   xmm0, xmm0
0x180007446  mov     qword ptr [r9], 0
0x18000744d  mov     rdi, rcx
0x180007450  lea     rdx, [rsp+330h+sz]; lpsz
0x180007455  lea     rcx, CLSID_AdvancedSettingsWriter; rguid
0x18000745c  mov     r8d, 32h ; '2'; cchMax
0x180007462  movups  xmmword ptr [rsp+330h+pBindOptions.cbStruct], xmm0
0x180007467  mov     rbx, r9
0x18000746a  movups  [rsp+330h+var_300], xmm0
0x18000746f  movups  [rsp+330h+var_2F0], xmm0
0x180007474  call    cs:__imp_StringFromGUID2
0x18000747a  test    eax, eax
0x18000747c  jnz     short loc_180007485
0x18000747e  mov     eax, 8007000Eh
0x180007483  jmp     short loc_1800074E3
0x180007485  lea     r9, [rsp+330h+sz]
0x18000748a  mov     edx, 12Ch; unsigned __int64
0x18000748f  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x180007496  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x18000749a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000749f  test    eax, eax
0x1800074a1  js      short loc_1800074E3
0x1800074a3  xorps   xmm0, xmm0
0x1800074a6  mov     [rsp+330h+pBindOptions.cbStruct], 30h ; '0'
0x1800074ae  xorps   xmm1, xmm1
0x1800074b1  mov     qword ptr [rsp+330h+var_2F0+8], rdi
0x1800074b6  mov     r9, rbx; ppv
0x1800074b9  mov     dword ptr [rsp+330h+var_300+4], 4
0x1800074c1  lea     r8, _GUID_5d703587_da7e_43c0_982c_2ba8e7ed341b; riid
0x1800074c8  lea     rdx, [rsp+330h+pBindOptions]; pBindOptions
0x1800074cd  lea     rcx, [rbp+230h+pszName]; pszName
0x1800074d1  movdqu  xmmword ptr [rsp+330h+pBindOptions.grfFlags], xmm0
0x1800074d7  movdqu  [rsp+330h+var_300+8], xmm1
0x1800074dd  call    cs:__imp_CoGetObject
0x1800074e3  mov     rcx, [rbp+230h+var_10]
0x1800074ea  xor     rcx, rsp; StackCookie
0x1800074ed  call    __security_check_cookie
0x1800074f2  lea     r11, [rsp+330h+var_s0]
0x1800074fa  mov     rbx, [r11+18h]
0x1800074fe  mov     rdi, [r11+20h]
0x180007502  mov     rsp, r11
0x180007505  pop     rbp
0x180007506  retn
```
