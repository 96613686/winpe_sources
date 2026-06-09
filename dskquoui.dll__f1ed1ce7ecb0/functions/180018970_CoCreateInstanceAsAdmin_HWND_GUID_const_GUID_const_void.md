# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x180018970`
- end: `0x180018a5f`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `int(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018b60`

## callees

- `0x180001510`
- `0x180005484`
- `0x180018970`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800189cc`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800189cc`
- `ole32!CoGetObject` at `0x180018a35`
- `ole32!CoGetObject` at `0x180018a35`

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
  if ( !StringFromGUID2(&CLSID_QuotaUIHelper, sz, 50) )
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
    return CoGetObject(pszName, pBindOptions, &GUID_9a50588e_fa80_4509_b345_664110225322, a4);
  }
  return result;
}

```

## disassembly

```asm
0x180018970  mov     [rsp-8+arg_8], rbx
0x180018975  mov     [rsp-8+arg_10], rdi
0x18001897a  push    rbp
0x18001897b  lea     rbp, [rsp-230h]
0x180018983  sub     rsp, 330h
0x18001898a  mov     rax, cs:__security_cookie
0x180018991  xor     rax, rsp
0x180018994  mov     [rbp+230h+var_10], rax
0x18001899b  xorps   xmm0, xmm0
0x18001899e  mov     qword ptr [r9], 0
0x1800189a5  mov     rdi, rcx
0x1800189a8  lea     rdx, [rsp+330h+sz]; lpsz
0x1800189ad  lea     rcx, CLSID_QuotaUIHelper; rguid
0x1800189b4  mov     r8d, 32h ; '2'; cchMax
0x1800189ba  movups  xmmword ptr [rsp+330h+pBindOptions.cbStruct], xmm0
0x1800189bf  mov     rbx, r9
0x1800189c2  movups  [rsp+330h+var_300], xmm0
0x1800189c7  movups  [rsp+330h+var_2F0], xmm0
0x1800189cc  call    cs:__imp_StringFromGUID2
0x1800189d2  test    eax, eax
0x1800189d4  jnz     short loc_1800189DD
0x1800189d6  mov     eax, 8007000Eh
0x1800189db  jmp     short loc_180018A3B
0x1800189dd  lea     r9, [rsp+330h+sz]
0x1800189e2  mov     edx, 12Ch; unsigned __int64
0x1800189e7  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x1800189ee  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x1800189f2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800189f7  test    eax, eax
0x1800189f9  js      short loc_180018A3B
0x1800189fb  xorps   xmm0, xmm0
0x1800189fe  mov     [rsp+330h+pBindOptions.cbStruct], 30h ; '0'
0x180018a06  xorps   xmm1, xmm1
0x180018a09  mov     qword ptr [rsp+330h+var_2F0+8], rdi
0x180018a0e  mov     r9, rbx; ppv
0x180018a11  mov     dword ptr [rsp+330h+var_300+4], 4
0x180018a19  lea     r8, _GUID_9a50588e_fa80_4509_b345_664110225322; riid
0x180018a20  lea     rdx, [rsp+330h+pBindOptions]; pBindOptions
0x180018a25  lea     rcx, [rbp+230h+pszName]; pszName
0x180018a29  movdqu  xmmword ptr [rsp+330h+pBindOptions.grfFlags], xmm0
0x180018a2f  movdqu  [rsp+330h+var_300+8], xmm1
0x180018a35  call    cs:__imp_CoGetObject
0x180018a3b  mov     rcx, [rbp+230h+var_10]
0x180018a42  xor     rcx, rsp; StackCookie
0x180018a45  call    __security_check_cookie
0x180018a4a  lea     r11, [rsp+330h+var_s0]
0x180018a52  mov     rbx, [r11+18h]
0x180018a56  mov     rdi, [r11+20h]
0x180018a5a  mov     rsp, r11
0x180018a5d  pop     rbp
0x180018a5e  retn
```
