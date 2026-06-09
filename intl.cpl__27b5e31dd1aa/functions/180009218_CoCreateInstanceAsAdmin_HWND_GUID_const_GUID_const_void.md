# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x180009218`
- end: `0x180009307`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `int(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a480`

## callees

- `0x1800062b0`
- `0x180009218`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009274`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009274`
- `ole32!CoGetObject` at `0x1800092dd`
- `ole32!CoGetObject` at `0x1800092dd`

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
  if ( !StringFromGUID2(&CLSID_IntlAdmin, sz, 50) )
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
    return CoGetObject(pszName, pBindOptions, &GUID_7c92505f_53a4_4d39_b31c_871d82a907de, a4);
  }
  return result;
}

```

## disassembly

```asm
0x180009218  mov     [rsp-8+arg_8], rbx
0x18000921d  mov     [rsp-8+arg_10], rdi
0x180009222  push    rbp
0x180009223  lea     rbp, [rsp-230h]
0x18000922b  sub     rsp, 330h
0x180009232  mov     rax, cs:__security_cookie
0x180009239  xor     rax, rsp
0x18000923c  mov     [rbp+230h+var_10], rax
0x180009243  xorps   xmm0, xmm0
0x180009246  mov     qword ptr [r9], 0
0x18000924d  mov     rdi, rcx
0x180009250  lea     rdx, [rsp+330h+sz]; lpsz
0x180009255  lea     rcx, CLSID_IntlAdmin; rguid
0x18000925c  mov     r8d, 32h ; '2'; cchMax
0x180009262  movups  xmmword ptr [rsp+330h+pBindOptions.cbStruct], xmm0
0x180009267  mov     rbx, r9
0x18000926a  movups  [rsp+330h+var_300], xmm0
0x18000926f  movups  [rsp+330h+var_2F0], xmm0
0x180009274  call    cs:__imp_StringFromGUID2
0x18000927a  test    eax, eax
0x18000927c  jnz     short loc_180009285
0x18000927e  mov     eax, 8007000Eh
0x180009283  jmp     short loc_1800092E3
0x180009285  lea     r9, [rsp+330h+sz]
0x18000928a  mov     edx, 12Ch; unsigned __int64
0x18000928f  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x180009296  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x18000929a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000929f  test    eax, eax
0x1800092a1  js      short loc_1800092E3
0x1800092a3  xorps   xmm0, xmm0
0x1800092a6  mov     [rsp+330h+pBindOptions.cbStruct], 30h ; '0'
0x1800092ae  xorps   xmm1, xmm1
0x1800092b1  mov     qword ptr [rsp+330h+var_2F0+8], rdi
0x1800092b6  mov     r9, rbx; ppv
0x1800092b9  mov     dword ptr [rsp+330h+var_300+4], 4
0x1800092c1  lea     r8, _GUID_7c92505f_53a4_4d39_b31c_871d82a907de; riid
0x1800092c8  lea     rdx, [rsp+330h+pBindOptions]; pBindOptions
0x1800092cd  lea     rcx, [rbp+230h+pszName]; pszName
0x1800092d1  movdqu  xmmword ptr [rsp+330h+pBindOptions.grfFlags], xmm0
0x1800092d7  movdqu  [rsp+330h+var_300+8], xmm1
0x1800092dd  call    cs:__imp_CoGetObject
0x1800092e3  mov     rcx, [rbp+230h+var_10]
0x1800092ea  xor     rcx, rsp; StackCookie
0x1800092ed  call    __security_check_cookie
0x1800092f2  lea     r11, [rsp+330h+var_s0]
0x1800092fa  mov     rbx, [r11+18h]
0x1800092fe  mov     rdi, [r11+20h]
0x180009302  mov     rsp, r11
0x180009305  pop     rbp
0x180009306  retn
```
