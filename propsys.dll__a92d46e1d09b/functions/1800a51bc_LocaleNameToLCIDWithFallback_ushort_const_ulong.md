# LocaleNameToLCIDWithFallback(ushort const *,ulong)

- ea: `0x1800a51bc`
- end: `0x1800a526b`
- name: `?LocaleNameToLCIDWithFallback@@YAKPEBGK@Z`
- size: `175`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001f668`

## callees

- `0x1800286c8`
- `0x18006ed20`
- `0x1800a51bc`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800a51d8`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800a5232`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800a51d8`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800a5232`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a51ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a523f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a51ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a523f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a5227`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a5227`
- `Bcp47Langs!Bcp47GetNlsForm` at `0x1800a5216`
- `Bcp47Langs!Bcp47GetNlsForm` at `0x1800a5216`

## pseudocode

```c
__int64 __fastcall LocaleNameToLCIDWithFallback(const unsigned __int16 *a1)
{
  LCID v1; // ebx
  __int64 v2; // rax
  const WCHAR *StringRawBuffer; // rax
  HSTRING string; // [rsp+20h] [rbp-48h] BYREF
  const unsigned __int16 *v6; // [rsp+28h] [rbp-40h] BYREF
  _BYTE v7[32]; // [rsp+30h] [rbp-38h] BYREF

  v6 = a1;
  v1 = LocaleNameToLCID(a1, 0);
  if ( !v1 )
  {
    WindowsDeleteString(0);
    string = 0;
    v2 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v7, &v6);
    if ( (int)Bcp47GetNlsForm(*(_QWORD *)(v2 + 24), &string) >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v1 = LocaleNameToLCID(StringRawBuffer, 0);
    }
    WindowsDeleteString(string);
    if ( !v1 )
      return 127;
  }
  if ( v1 == 4096 )
    return 127;
  return v1;
}

```

## disassembly

```asm
0x1800a51bc  push    rbx
0x1800a51be  sub     rsp, 60h
0x1800a51c2  mov     rax, cs:__security_cookie
0x1800a51c9  xor     rax, rsp
0x1800a51cc  mov     [rsp+68h+var_18], rax
0x1800a51d1  xor     edx, edx; dwFlags
0x1800a51d3  mov     [rsp+68h+var_40], rcx
0x1800a51d8  call    cs:__imp_LocaleNameToLCID
0x1800a51de  mov     ebx, eax
0x1800a51e0  test    eax, eax
0x1800a51e2  jnz     short loc_1800A5249
0x1800a51e4  xor     ecx, ecx; string
0x1800a51e6  mov     [rsp+68h+string], 0
0x1800a51ef  call    cs:__imp_WindowsDeleteString
0x1800a51f5  lea     rdx, [rsp+68h+var_40]
0x1800a51fa  mov     [rsp+68h+string], 0
0x1800a5203  lea     rcx, [rsp+68h+var_38]
0x1800a5208  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800a520d  lea     rdx, [rsp+68h+string]
0x1800a5212  mov     rcx, [rax+18h]
0x1800a5216  call    cs:__imp_Bcp47GetNlsForm
0x1800a521c  test    eax, eax
0x1800a521e  js      short loc_1800A523A
0x1800a5220  mov     rcx, [rsp+68h+string]; string
0x1800a5225  xor     edx, edx; length
0x1800a5227  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a522d  mov     rcx, rax; lpName
0x1800a5230  xor     edx, edx; dwFlags
0x1800a5232  call    cs:__imp_LocaleNameToLCID
0x1800a5238  mov     ebx, eax
0x1800a523a  mov     rcx, [rsp+68h+string]; string
0x1800a523f  call    cs:__imp_WindowsDeleteString
0x1800a5245  test    ebx, ebx
0x1800a5247  jz      short loc_1800A5251
0x1800a5249  cmp     ebx, 1000h
0x1800a524f  jnz     short loc_1800A5256
0x1800a5251  mov     ebx, 7Fh
0x1800a5256  mov     eax, ebx
0x1800a5258  mov     rcx, [rsp+68h+var_18]
0x1800a525d  xor     rcx, rsp; StackCookie
0x1800a5260  call    __security_check_cookie
0x1800a5265  add     rsp, 60h
0x1800a5269  pop     rbx
0x1800a526a  retn
```
