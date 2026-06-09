# IntlUpdateSystemLocaleUTF8(ushort const *,ulong,int)

- ea: `0x1800222e0`
- end: `0x180022422`
- name: `?IntlUpdateSystemLocaleUTF8@@YAKPEBGKH@Z`
- size: `322`
- prototype: `unsigned int __fastcall(LPCWSTR lpLocaleName, unsigned int, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180017f80`
- `0x180017fb0`
- `0x1800222d0`

## callees

- `0x180012dc8`
- `0x180012f38`
- `0x1800130b4`
- `0x1800222e0`
- `0x1800245e0`
- `0x180024608`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800223f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800223f3`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180022354`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18002236b`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180022354`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18002236b`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18002238e`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18002238e`
- `api-ms-win-core-localization-l1-2-0!GetOEMCP` at `0x18002239a`
- `api-ms-win-core-localization-l1-2-0!GetOEMCP` at `0x18002239a`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180022316`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180022316`
- `KERNEL32!NlsUpdateSystemLocale` at `0x1800223ae`
- `KERNEL32!NlsUpdateSystemLocale` at `0x1800223ae`

## pseudocode

```c
__int64 __fastcall IntlUpdateSystemLocaleUTF8(LPCWSTR lpLocaleName, int a2, int a3)
{
  LCID v6; // eax
  DWORD LastError; // ebx
  int v8; // r14d
  __int64 LCData; // [rsp+58h] [rbp+10h] BYREF
  wchar_t v11[4]; // [rsp+68h] [rbp+20h] BYREF

  LODWORD(LCData) = 0;
  *(_DWORD *)v11 = 0;
  if ( (a2 & 0xFFFFFFFC) == 0 )
  {
    v6 = LocaleNameToLCID(lpLocaleName, 0);
    if ( v6 )
    {
      LastError = 87;
      v8 = Intl_ChangeSystemLocale(lpLocaleName, v6, a3);
      GetLocaleInfoEx(lpLocaleName, 0x20001004u, (LPWSTR)&LCData, 2);
      GetLocaleInfoEx(lpLocaleName, 0x2000000Bu, v11, 2);
      if ( a3 || !(_DWORD)LCData )
      {
        wcscpy((wchar_t *)&LCData, L"\xEF\xB7\xA9");
        wcscpy(v11, L"\xEF\xB7\xA9");
      }
      if ( !a2 || (_DWORD)LCData == GetACP() && *(_DWORD *)v11 == GetOEMCP() )
        NlsUpdateSystemLocale(lpLocaleName, 1);
      if ( v8 )
      {
        if ( (a2 & 2) != 0 && !(unsigned int)Intl_ChangeSystemFontLinking(lpLocaleName) )
          return LastError;
        if ( (a2 & 1) != 0 && (unsigned int)Input_LoadAndInitFunctions() )
        {
          if ( (unsigned int)Input_InstallLayout(0, lpLocaleName, 8u) )
            LastError = v8 == 0 ? 0x57 : 0;
          else
            LastError = GetLastError();
          Input_Unload();
          return LastError;
        }
      }
      return v8 == 0 ? 0x57 : 0;
    }
  }
  return 87;
}

```

## disassembly

```asm
0x1800222e0  mov     [rsp+arg_0], rbx
0x1800222e5  push    rbp
0x1800222e6  push    rsi
0x1800222e7  push    rdi
0x1800222e8  push    r14
0x1800222ea  push    r15
0x1800222ec  sub     rsp, 20h
0x1800222f0  mov     dword ptr [rsp+48h+LCData], 0
0x1800222f8  mov     r15d, r8d
0x1800222fb  mov     dword ptr [rsp+48h+arg_18], 0
0x180022303  mov     ebp, edx
0x180022305  mov     rsi, rcx
0x180022308  test    edx, 0FFFFFFFCh
0x18002230e  jnz     loc_18002240C
0x180022314  xor     edx, edx; dwFlags
0x180022316  call    cs:__imp_LocaleNameToLCID
0x18002231c  test    eax, eax
0x18002231e  jz      loc_18002240C
0x180022324  mov     r8d, r15d; int
0x180022327  mov     edx, eax; unsigned int
0x180022329  mov     rcx, rsi; lpLocaleName
0x18002232c  call    ?Intl_ChangeSystemLocale@@YAHPEBGKH@Z; Intl_ChangeSystemLocale(ushort const *,ulong,int)
0x180022331  mov     ecx, eax
0x180022333  lea     r8, [rsp+48h+LCData]; lpLCData
0x180022338  neg     ecx
0x18002233a  mov     ebx, 57h ; 'W'
0x18002233f  mov     edx, 20001004h; LCType
0x180022344  mov     rcx, rsi; lpLocaleName
0x180022347  sbb     edi, edi
0x180022349  mov     r14d, eax
0x18002234c  not     edi
0x18002234e  lea     r9d, [rbx-55h]; cchData
0x180022352  and     edi, ebx
0x180022354  call    cs:__imp_GetLocaleInfoEx
0x18002235a  lea     r9d, [rbx-55h]; cchData
0x18002235e  mov     edx, 2000000Bh; LCType
0x180022363  lea     r8, [rsp+48h+arg_18]; lpLCData
0x180022368  mov     rcx, rsi; lpLocaleName
0x18002236b  call    cs:__imp_GetLocaleInfoEx
0x180022371  test    r15d, r15d
0x180022374  jnz     short loc_18002237D
0x180022376  cmp     dword ptr [rsp+48h+LCData], r15d
0x18002237b  jnz     short loc_18002238A
0x18002237d  mov     eax, 0FDE9h
0x180022382  mov     dword ptr [rsp+48h+LCData], eax
0x180022386  mov     dword ptr [rsp+48h+arg_18], eax
0x18002238a  test    ebp, ebp
0x18002238c  jz      short loc_1800223A6
0x18002238e  call    cs:__imp_GetACP
0x180022394  cmp     dword ptr [rsp+48h+LCData], eax
0x180022398  jnz     short loc_1800223B4
0x18002239a  call    cs:__imp_GetOEMCP
0x1800223a0  cmp     dword ptr [rsp+48h+arg_18], eax
0x1800223a4  jnz     short loc_1800223B4
0x1800223a6  mov     edx, 1
0x1800223ab  mov     rcx, rsi
0x1800223ae  call    cs:__imp_NlsUpdateSystemLocale
0x1800223b4  test    r14d, r14d
0x1800223b7  jz      short loc_180022406
0x1800223b9  test    bpl, 2
0x1800223bd  jz      short loc_1800223D0
0x1800223bf  mov     rcx, rsi; unsigned __int16 *
0x1800223c2  call    ?Intl_ChangeSystemFontLinking@@YAHPEBG@Z; Intl_ChangeSystemFontLinking(ushort const *)
0x1800223c7  test    eax, eax
0x1800223c9  jz      short loc_180022408
0x1800223cb  test    r14d, r14d
0x1800223ce  jz      short loc_180022406
0x1800223d0  test    bpl, 1
0x1800223d4  jz      short loc_180022406
0x1800223d6  call    ?Input_LoadAndInitFunctions@@YAHXZ; Input_LoadAndInitFunctions(void)
0x1800223db  test    eax, eax
0x1800223dd  jz      short loc_180022406
0x1800223df  mov     r8d, 8; unsigned int
0x1800223e5  mov     rdx, rsi; lpLocaleName
0x1800223e8  xor     ecx, ecx; hWnd
0x1800223ea  call    ?Input_InstallLayout@@YAHPEAUHWND__@@PEBGK@Z; Input_InstallLayout(HWND__ *,ushort const *,ulong)
0x1800223ef  test    eax, eax
0x1800223f1  jnz     short loc_1800223FD
0x1800223f3  call    cs:__imp_GetLastError
0x1800223f9  mov     ebx, eax
0x1800223fb  jmp     short loc_1800223FF
0x1800223fd  mov     ebx, edi
0x1800223ff  call    ?Input_Unload@@YAXXZ; Input_Unload(void)
0x180022404  jmp     short loc_180022408
0x180022406  mov     ebx, edi
0x180022408  mov     eax, ebx
0x18002240a  jmp     short loc_180022411
0x18002240c  mov     eax, 57h ; 'W'
0x180022411  mov     rbx, [rsp+48h+arg_0]
0x180022416  add     rsp, 20h
0x18002241a  pop     r15
0x18002241c  pop     r14
0x18002241e  pop     rdi
0x18002241f  pop     rsi
0x180022420  pop     rbp
0x180022421  retn
```
