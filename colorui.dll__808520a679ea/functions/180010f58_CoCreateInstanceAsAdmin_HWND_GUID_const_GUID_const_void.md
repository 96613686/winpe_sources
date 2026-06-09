# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x180010f58`
- end: `0x180011047`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `HRESULT __fastcall(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012528`

## callees

- `0x180009ff4`
- `0x180010f58`
- `0x180018500`

## import_xrefs

- `ole32!StringFromGUID2` at `0x180010fb4`
- `ole32!StringFromGUID2` at `0x180010fb4`
- `ole32!CoGetObject` at `0x18001101d`
- `ole32!CoGetObject` at `0x18001101d`

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
  if ( !StringFromGUID2(&CLSID_ColorDataProxy, sz, 50) )
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
    return CoGetObject(pszName, pBindOptions, &IID_IColorDataProxy, a4);
  }
  return result;
}

```

## disassembly

```asm
0x180010f58  mov     [rsp-8+arg_8], rbx
0x180010f5d  mov     [rsp-8+arg_10], rdi
0x180010f62  push    rbp
0x180010f63  lea     rbp, [rsp-230h]
0x180010f6b  sub     rsp, 330h
0x180010f72  mov     rax, cs:__security_cookie
0x180010f79  xor     rax, rsp
0x180010f7c  mov     [rbp+230h+var_10], rax
0x180010f83  xorps   xmm0, xmm0
0x180010f86  mov     qword ptr [r9], 0
0x180010f8d  mov     rdi, rcx
0x180010f90  lea     rdx, [rsp+330h+sz]; lpsz
0x180010f95  lea     rcx, CLSID_ColorDataProxy; rguid
0x180010f9c  mov     r8d, 32h ; '2'; cchMax
0x180010fa2  movups  xmmword ptr [rsp+330h+pBindOptions.cbStruct], xmm0
0x180010fa7  mov     rbx, r9
0x180010faa  movups  [rsp+330h+var_300], xmm0
0x180010faf  movups  [rsp+330h+var_2F0], xmm0
0x180010fb4  call    cs:__imp_StringFromGUID2
0x180010fba  test    eax, eax
0x180010fbc  jnz     short loc_180010FC5
0x180010fbe  mov     eax, 8007000Eh
0x180010fc3  jmp     short loc_180011023
0x180010fc5  lea     r9, [rsp+330h+sz]
0x180010fca  mov     edx, 12Ch; unsigned __int64
0x180010fcf  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x180010fd6  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x180010fda  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010fdf  test    eax, eax
0x180010fe1  js      short loc_180011023
0x180010fe3  xorps   xmm0, xmm0
0x180010fe6  mov     [rsp+330h+pBindOptions.cbStruct], 30h ; '0'
0x180010fee  xorps   xmm1, xmm1
0x180010ff1  mov     qword ptr [rsp+330h+var_2F0+8], rdi
0x180010ff6  mov     r9, rbx; ppv
0x180010ff9  mov     dword ptr [rsp+330h+var_300+4], 4
0x180011001  lea     r8, IID_IColorDataProxy; riid
0x180011008  lea     rdx, [rsp+330h+pBindOptions]; pBindOptions
0x18001100d  lea     rcx, [rbp+230h+pszName]; pszName
0x180011011  movdqu  xmmword ptr [rsp+330h+pBindOptions.grfFlags], xmm0
0x180011017  movdqu  [rsp+330h+var_300+8], xmm1
0x18001101d  call    cs:__imp_CoGetObject
0x180011023  mov     rcx, [rbp+230h+var_10]
0x18001102a  xor     rcx, rsp; StackCookie
0x18001102d  call    __security_check_cookie
0x180011032  lea     r11, [rsp+330h+var_s0]
0x18001103a  mov     rbx, [r11+18h]
0x18001103e  mov     rdi, [r11+20h]
0x180011042  mov     rsp, r11
0x180011045  pop     rbp
0x180011046  retn
```
