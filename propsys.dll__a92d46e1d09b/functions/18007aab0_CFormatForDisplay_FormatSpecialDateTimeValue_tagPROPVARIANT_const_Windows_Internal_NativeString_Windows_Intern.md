# CFormatForDisplay::_FormatSpecialDateTimeValue(tagPROPVARIANT const &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x18007aab0`
- end: `0x18007ac9a`
- name: `?_FormatSpecialDateTimeValue@CFormatForDisplay@@AEAAJAEBUtagPROPVARIANT@@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d240`

## callees

- `0x18000ca30`
- `0x18000ccd0`
- `0x180017e30`
- `0x18001a074`
- `0x180034fc0`
- `0x18006ed20`
- `0x18007aab0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007abe5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007abe5`
- `api-ms-win-core-localization-l1-2-0!GetCalendarInfoW` at `0x18007abbb`
- `api-ms-win-core-localization-l1-2-0!GetCalendarInfoW` at `0x18007ac55`
- `api-ms-win-core-localization-l1-2-0!GetCalendarInfoW` at `0x18007abbb`
- `api-ms-win-core-localization-l1-2-0!GetCalendarInfoW` at `0x18007ac55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ab51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ab51`

## pseudocode

```c
__int64 __fastcall CFormatForDisplay::_FormatSpecialDateTimeValue(__int64 a1, const PROPVARIANT *a2, __int64 a3)
{
  int v4; // ebx
  _WORD *v5; // rdx
  PWSTR ppszOut[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[32]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v10[64]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR CalData[104]; // [rsp+100h] [rbp+0h] BYREF

  if ( *(_DWORD *)(*(_QWORD *)a1 + 8LL) == 300 )
  {
    LODWORD(ppszOut[0]) = 0;
    v4 = PropVariantToInt32(a2, (LONG *)ppszOut);
    if ( v4 < 0 )
      return (unsigned int)v4;
    if ( !GetCalendarInfoW(0x400u, 1u, LODWORD(ppszOut[0]) + 20, v10, 64, 0) )
      return (unsigned int)-2147467259;
    v5 = v10;
    return (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                           a3,
                           v5);
  }
  if ( *(_DWORD *)(*(_QWORD *)a1 + 8LL) == 301 )
  {
    LODWORD(ppszOut[0]) = 0;
    v4 = PropVariantToInt32(a2, (LONG *)ppszOut);
    if ( v4 < 0 )
      return (unsigned int)v4;
    v4 = -2147467259;
    if ( !GetCalendarInfoW(0x400u, 1u, LOWORD(ppszOut[0]) + 20, CalData, 100, 0)
      || !LoadStringW(g_hModMUIResources, 0xC0u, Buffer, 32) )
    {
      return (unsigned int)v4;
    }
    return (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
                           a3,
                           Buffer,
                           WORD1(ppszOut[0]),
                           CalData);
  }
  if ( *(_DWORD *)(*(_QWORD *)a1 + 8LL) != 302 )
    return (unsigned int)-2147418113;
  if ( *(_WORD *)a2 == 31 || *(_WORD *)a2 == 8 )
  {
    v5 = PropVariantToStringWithDefault(a2, &Src);
    return (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                           a3,
                           v5);
  }
  ppszOut[0] = 0;
  v4 = PropVariantToStringAlloc(a2, ppszOut);
  if ( v4 >= 0 )
  {
    v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(a3, ppszOut[0]);
    CoTaskMemFree(ppszOut[0]);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007aab0  mov     [rsp-8+arg_0], rbx
0x18007aab5  mov     [rsp-8+arg_18], rdi
0x18007aaba  push    rbp
0x18007aabb  lea     rbp, [rsp-0E0h]
0x18007aac3  sub     rsp, 1E0h
0x18007aaca  mov     rax, cs:__security_cookie
0x18007aad1  xor     rax, rsp
0x18007aad4  mov     [rbp+0E0h+var_10], rax
0x18007aadb  mov     rcx, [rcx]
0x18007aade  mov     rdi, r8
0x18007aae1  mov     r8, rdx
0x18007aae4  mov     edx, [rcx+8]
0x18007aae7  sub     edx, 12Ch
0x18007aaed  jz      loc_18007AC12
0x18007aaf3  sub     edx, 1
0x18007aaf6  jz      short loc_18007AB73
0x18007aaf8  cmp     edx, 1
0x18007aafb  jz      short loc_18007AB07
0x18007aafd  mov     ebx, 8000FFFFh
0x18007ab02  jmp     loc_18007AC74
0x18007ab07  mov     eax, 1Fh
0x18007ab0c  cmp     ax, [r8]
0x18007ab10  jz      short loc_18007AB5C
0x18007ab12  mov     eax, 8
0x18007ab17  cmp     ax, [r8]
0x18007ab1b  jz      short loc_18007AB5C
0x18007ab1d  lea     rdx, [rsp+1E0h+ppszOut]; ppszOut
0x18007ab22  mov     [rsp+1E0h+ppszOut], 0
0x18007ab2b  mov     rcx, r8; propvar
0x18007ab2e  call    PropVariantToStringAlloc
0x18007ab33  mov     ebx, eax
0x18007ab35  test    eax, eax
0x18007ab37  js      loc_18007AC74
0x18007ab3d  mov     rdx, [rsp+1E0h+ppszOut]
0x18007ab42  mov     rcx, rdi
0x18007ab45  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18007ab4a  mov     rcx, [rsp+1E0h+ppszOut]; pv
0x18007ab4f  mov     ebx, eax
0x18007ab51  call    cs:__imp_CoTaskMemFree
0x18007ab57  jmp     loc_18007AC74
0x18007ab5c  lea     rdx, Src; pszDefault
0x18007ab63  mov     rcx, r8; propvarIn
0x18007ab66  call    PropVariantToStringWithDefault
0x18007ab6b  mov     rdx, rax
0x18007ab6e  jmp     loc_18007AC6A
0x18007ab73  lea     rdx, [rsp+1E0h+ppszOut]; plRet
0x18007ab78  mov     dword ptr [rsp+1E0h+ppszOut], 0
0x18007ab80  mov     rcx, r8; propvarIn
0x18007ab83  call    PropVariantToInt32
0x18007ab88  mov     ebx, eax
0x18007ab8a  test    eax, eax
0x18007ab8c  js      loc_18007AC74
0x18007ab92  movzx   r8d, word ptr [rsp+1E0h+ppszOut]
0x18007ab98  lea     r9, [rbp+0E0h+CalData]; lpCalData
0x18007ab9c  add     r8d, 14h; CalType
0x18007aba0  mov     [rsp+1E0h+lpValue], 0; lpValue
0x18007aba9  mov     edx, 1; Calendar
0x18007abae  mov     [rsp+1E0h+cchData], 64h ; 'd'; cchData
0x18007abb6  mov     ecx, 400h; Locale
0x18007abbb  call    cs:__imp_GetCalendarInfoW
0x18007abc1  mov     ebx, 80004005h
0x18007abc6  test    eax, eax
0x18007abc8  jz      loc_18007AC74
0x18007abce  mov     rcx, cs:?g_hModMUIResources@@3PEAUHINSTANCE__@@EA; hInstance
0x18007abd5  lea     r8, [rsp+1E0h+Buffer]; lpBuffer
0x18007abda  mov     r9d, 20h ; ' '; cchBufferMax
0x18007abe0  mov     edx, 0C0h; uID
0x18007abe5  call    cs:__imp_LoadStringW
0x18007abeb  test    eax, eax
0x18007abed  jz      loc_18007AC74
0x18007abf3  mov     eax, dword ptr [rsp+1E0h+ppszOut]
0x18007abf7  lea     r9, [rbp+0E0h+CalData]
0x18007abfb  shr     rax, 10h
0x18007abff  lea     rdx, [rsp+1E0h+Buffer]
0x18007ac04  movzx   r8d, ax
0x18007ac08  mov     rcx, rdi
0x18007ac0b  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x18007ac10  jmp     short loc_18007AC72
0x18007ac12  lea     rdx, [rsp+1E0h+ppszOut]; plRet
0x18007ac17  mov     dword ptr [rsp+1E0h+ppszOut], 0
0x18007ac1f  mov     rcx, r8; propvarIn
0x18007ac22  call    PropVariantToInt32
0x18007ac27  mov     ebx, eax
0x18007ac29  test    eax, eax
0x18007ac2b  js      short loc_18007AC74
0x18007ac2d  mov     r8d, dword ptr [rsp+1E0h+ppszOut]
0x18007ac32  lea     r9, [rbp+0E0h+var_160]; lpCalData
0x18007ac36  add     r8d, 14h; CalType
0x18007ac3a  mov     [rsp+1E0h+lpValue], 0; lpValue
0x18007ac43  mov     edx, 1; Calendar
0x18007ac48  mov     [rsp+1E0h+cchData], 40h ; '@'; cchData
0x18007ac50  mov     ecx, 400h; Locale
0x18007ac55  call    cs:__imp_GetCalendarInfoW
0x18007ac5b  test    eax, eax
0x18007ac5d  jnz     short loc_18007AC66
0x18007ac5f  mov     ebx, 80004005h
0x18007ac64  jmp     short loc_18007AC74
0x18007ac66  lea     rdx, [rbp+0E0h+var_160]
0x18007ac6a  mov     rcx, rdi
0x18007ac6d  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18007ac72  mov     ebx, eax
0x18007ac74  mov     eax, ebx
0x18007ac76  mov     rcx, [rbp+0E0h+var_10]
0x18007ac7d  xor     rcx, rsp; StackCookie
0x18007ac80  call    __security_check_cookie
0x18007ac85  lea     r11, [rsp+1E0h+var_s0]
0x18007ac8d  mov     rbx, [r11+10h]
0x18007ac91  mov     rdi, [r11+28h]
0x18007ac95  mov     rsp, r11
0x18007ac98  pop     rbp
0x18007ac99  retn
```
