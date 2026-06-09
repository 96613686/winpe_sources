# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x18000d038`
- end: `0x18000d127`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `HRESULT __fastcall(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d3d0`

## callees

- `0x18000886c`
- `0x18000d038`
- `0x18000fe10`

## import_xrefs

- `ole32!StringFromGUID2` at `0x18000d094`
- `ole32!StringFromGUID2` at `0x18000d094`
- `ole32!CoGetObject` at `0x18000d0fd`
- `ole32!CoGetObject` at `0x18000d0fd`

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
  if ( !StringFromGUID2(&CLSID_PortableWorkspaceLauncher, sz, 50) )
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
    return CoGetObject(pszName, pBindOptions, &GUID_ad6b3b23_c74a_4b2c_839f_c1149cb42e7f, a4);
  }
  return result;
}

```

## disassembly

```asm
0x18000d038  mov     [rsp-8+arg_8], rbx
0x18000d03d  mov     [rsp-8+arg_10], rdi
0x18000d042  push    rbp
0x18000d043  lea     rbp, [rsp-230h]
0x18000d04b  sub     rsp, 330h
0x18000d052  mov     rax, cs:__security_cookie
0x18000d059  xor     rax, rsp
0x18000d05c  mov     [rbp+230h+var_10], rax
0x18000d063  xorps   xmm0, xmm0
0x18000d066  mov     qword ptr [r9], 0
0x18000d06d  mov     rdi, rcx
0x18000d070  lea     rdx, [rsp+330h+sz]; lpsz
0x18000d075  lea     rcx, CLSID_PortableWorkspaceLauncher; rguid
0x18000d07c  mov     r8d, 32h ; '2'; cchMax
0x18000d082  movups  xmmword ptr [rsp+330h+pBindOptions.cbStruct], xmm0
0x18000d087  mov     rbx, r9
0x18000d08a  movups  [rsp+330h+var_300], xmm0
0x18000d08f  movups  [rsp+330h+var_2F0], xmm0
0x18000d094  call    cs:__imp_StringFromGUID2
0x18000d09a  test    eax, eax
0x18000d09c  jnz     short loc_18000D0A5
0x18000d09e  mov     eax, 8007000Eh
0x18000d0a3  jmp     short loc_18000D103
0x18000d0a5  lea     r9, [rsp+330h+sz]
0x18000d0aa  mov     edx, 12Ch; unsigned __int64
0x18000d0af  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x18000d0b6  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x18000d0ba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d0bf  test    eax, eax
0x18000d0c1  js      short loc_18000D103
0x18000d0c3  xorps   xmm0, xmm0
0x18000d0c6  mov     [rsp+330h+pBindOptions.cbStruct], 30h ; '0'
0x18000d0ce  xorps   xmm1, xmm1
0x18000d0d1  mov     qword ptr [rsp+330h+var_2F0+8], rdi
0x18000d0d6  mov     r9, rbx; ppv
0x18000d0d9  mov     dword ptr [rsp+330h+var_300+4], 4
0x18000d0e1  lea     r8, _GUID_ad6b3b23_c74a_4b2c_839f_c1149cb42e7f; riid
0x18000d0e8  lea     rdx, [rsp+330h+pBindOptions]; pBindOptions
0x18000d0ed  lea     rcx, [rbp+230h+pszName]; pszName
0x18000d0f1  movdqu  xmmword ptr [rsp+330h+pBindOptions.grfFlags], xmm0
0x18000d0f7  movdqu  [rsp+330h+var_300+8], xmm1
0x18000d0fd  call    cs:__imp_CoGetObject
0x18000d103  mov     rcx, [rbp+230h+var_10]
0x18000d10a  xor     rcx, rsp; StackCookie
0x18000d10d  call    __security_check_cookie
0x18000d112  lea     r11, [rsp+330h+var_s0]
0x18000d11a  mov     rbx, [r11+18h]
0x18000d11e  mov     rdi, [r11+20h]
0x18000d122  mov     rsp, r11
0x18000d125  pop     rbp
0x18000d126  retn
```
