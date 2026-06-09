# Intl_IsUserLocaleSoftOverrideSet(void)

- ea: `0x180025cac`
- end: `0x180025d31`
- name: `?Intl_IsUserLocaleSoftOverrideSet@@YA_NXZ`
- size: `133`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001f95c`

## callees

- `0x18001e314`
- `0x180025480`
- `0x1800254f0`
- `0x180025cac`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025cc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025cc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025ce8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025ce8`
- `Bcp47Langs!GetAppropriateUserLocaleForUserLanguages` at `0x180025cd7`
- `Bcp47Langs!GetAppropriateUserLocaleForUserLanguages` at `0x180025cd7`

## pseudocode

```c
bool Intl_IsUserLocaleSoftOverrideSet(void)
{
  bool v0; // bl
  const WCHAR *StringRawBuffer; // rax
  unsigned int UserLocaleNameIndex; // edi
  unsigned int DefaultLocaleNameIndex; // eax
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF

  string = 0;
  v0 = 0;
  WindowsDeleteString(0);
  string = 0;
  if ( (int)GetAppropriateUserLocaleForUserLanguages(&string) >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    UserLocaleNameIndex = Intl_FindUserLocaleNameIndex(StringRawBuffer);
    if ( UserLocaleNameIndex != g_dwLocaleCount )
    {
      DefaultLocaleNameIndex = Intl_FindDefaultLocaleNameIndex();
      if ( DefaultLocaleNameIndex != g_dwLocaleCount )
        v0 = DefaultLocaleNameIndex != UserLocaleNameIndex;
    }
  }
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  return v0;
}

```

## disassembly

```asm
0x180025cac  mov     [rsp+arg_8], rbx
0x180025cb1  push    rdi
0x180025cb2  sub     rsp, 20h
0x180025cb6  xor     ecx, ecx; string
0x180025cb8  mov     [rsp+28h+string], 0
0x180025cc1  xor     bl, bl
0x180025cc3  call    cs:__imp_WindowsDeleteString
0x180025cc9  lea     rcx, [rsp+28h+string]
0x180025cce  mov     [rsp+28h+string], 0
0x180025cd7  call    cs:__imp_GetAppropriateUserLocaleForUserLanguages
0x180025cdd  test    eax, eax
0x180025cdf  js      short loc_180025D1A
0x180025ce1  mov     rcx, [rsp+28h+string]; string
0x180025ce6  xor     edx, edx; length
0x180025ce8  call    cs:__imp_WindowsGetStringRawBuffer
0x180025cee  mov     rcx, rax; lpString2
0x180025cf1  call    ?Intl_FindUserLocaleNameIndex@@YAKPEBG@Z; Intl_FindUserLocaleNameIndex(ushort const *)
0x180025cf6  cmp     eax, cs:?g_dwLocaleCount@@3KA; ulong g_dwLocaleCount
0x180025cfc  mov     edi, eax
0x180025cfe  jz      short loc_180025D1A
0x180025d00  call    ?Intl_FindDefaultLocaleNameIndex@@YAKXZ; Intl_FindDefaultLocaleNameIndex(void)
0x180025d05  cmp     eax, cs:?g_dwLocaleCount@@3KA; ulong g_dwLocaleCount
0x180025d0b  jz      short loc_180025D1A
0x180025d0d  cmp     eax, edi
0x180025d0f  movzx   ebx, bl
0x180025d12  mov     ecx, 1
0x180025d17  cmovnz  ebx, ecx
0x180025d1a  lea     rcx, [rsp+28h+string]; this
0x180025d1f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180025d24  mov     al, bl
0x180025d26  mov     rbx, [rsp+28h+arg_8]
0x180025d2b  add     rsp, 20h
0x180025d2f  pop     rdi
0x180025d30  retn
```
