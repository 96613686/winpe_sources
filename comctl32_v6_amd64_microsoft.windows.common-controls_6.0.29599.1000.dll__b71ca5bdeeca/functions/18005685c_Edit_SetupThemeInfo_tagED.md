# Edit_SetupThemeInfo(tagED *)

- ea: `0x18005685c`
- end: `0x180056a3e`
- name: `?Edit_SetupThemeInfo@@YAXPEAUtagED@@@Z`
- size: `482`
- prototype: `void __fastcall(struct tagED *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180054db4`
- `0x180056a44`

## callees

- `0x18005685c`
- `0x1800e7a84`
- `0x180114520`
- `0x180114ebc`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1800569d7`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1800569d7`
- `GDI32!DeleteObject` at `0x1800569a7`
- `GDI32!DeleteObject` at `0x180056a21`
- `GDI32!DeleteObject` at `0x1800569a7`
- `GDI32!DeleteObject` at `0x180056a21`
- `GDI32!CreateFontIndirectW` at `0x180056a2c`
- `GDI32!CreateFontIndirectW` at `0x180056a2c`
- `UxTheme!IsThemePartDefined` at `0x1800568a5`
- `UxTheme!IsThemePartDefined` at `0x1800568cd`
- `UxTheme!IsThemePartDefined` at `0x1800568a5`
- `UxTheme!IsThemePartDefined` at `0x1800568cd`
- `UxTheme!GetThemeFont` at `0x18005691b`
- `UxTheme!GetThemeFont` at `0x18005691b`
- `UxTheme!GetThemeColor` at `0x180056952`
- `UxTheme!GetThemeColor` at `0x180056952`

## pseudocode

```c
void __fastcall Edit_SetupThemeInfo(struct tagED *a1)
{
  void *v2; // rcx
  bool v3; // al
  void *v4; // rcx
  int v5; // eax
  void *v6; // rcx
  void *v7; // rcx
  int v8; // edx
  int v9; // edi
  LANGID UserDefaultUILanguage; // ax
  BYTE lfItalic; // cl
  void *v12; // rcx
  LOGFONTW lf; // [rsp+30h] [rbp-78h] BYREF

  if ( (*((_BYTE *)a1 + 116) & 1) != 0 && (v2 = (void *)*((_QWORD *)a1 + 45)) != 0 )
  {
    v3 = IsThemePartDefined(v2, 5, 0);
    v4 = (void *)*((_QWORD *)a1 + 45);
    *((_DWORD *)a1 + 100) ^= ((unsigned __int8)*((_DWORD *)a1 + 100) ^ (unsigned __int8)(2 * v3)) & 2;
    if ( IsThemePartDefined(v4, 3, 0) || (v5 = 0, (*((_BYTE *)a1 + 400) & 2) != 0) )
      v5 = 128;
    *((_DWORD *)a1 + 30) &= ~0x80u;
    *((_DWORD *)a1 + 30) |= v5;
    memset_0(&lf, 0, sizeof(lf));
    if ( GetThemeFont(*((HTHEME *)a1 + 45), 0, 1, 8, 210, &lf) >= 0 )
    {
      v8 = `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi;
      if ( `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi == -1 )
      {
        v9 = 0;
        UserDefaultUILanguage = GetUserDefaultUILanguage();
        `IsBiDiLocalizedSystemEx'::`2'::s_langID = UserDefaultUILanguage;
        if ( UserDefaultUILanguage )
          v9 = IsBiDiLocale(UserDefaultUILanguage);
        _InterlockedExchange(&`IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi, v9 != 0);
        v8 = `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi;
      }
      lfItalic = lf.lfItalic;
      if ( v8 == 1 )
        lfItalic = 0;
      lf.lfItalic = lfItalic;
      v12 = (void *)*((_QWORD *)a1 + 54);
      if ( v12 )
        DeleteObject(v12);
      *((_QWORD *)a1 + 54) = CreateFontIndirectW(&lf);
    }
    v6 = (void *)*((_QWORD *)a1 + 45);
    *((_BYTE *)a1 + 396) &= ~2u;
    if ( GetThemeColor(v6, 1, 8, 3803, (COLORREF *)a1 + 110) >= 0 )
      *((_BYTE *)a1 + 396) |= 2u;
  }
  else
  {
    *((_DWORD *)a1 + 30) &= ~0x80u;
    *((_DWORD *)a1 + 100) &= ~2u;
    *((_BYTE *)a1 + 396) &= ~2u;
    v7 = (void *)*((_QWORD *)a1 + 54);
    if ( v7 )
    {
      DeleteObject(v7);
      *((_QWORD *)a1 + 54) = 0;
    }
  }
}

```

## disassembly

```asm
0x18005685c  mov     [rsp+arg_8], rbx
0x180056861  mov     [rsp+arg_10], rsi
0x180056866  push    rdi
0x180056867  sub     rsp, 0A0h
0x18005686e  mov     rax, cs:__security_cookie
0x180056875  xor     rax, rsp
0x180056878  mov     [rsp+0A8h+var_18], rax
0x180056880  xor     esi, esi
0x180056882  mov     rbx, rcx
0x180056885  test    byte ptr [rcx+74h], 1
0x180056889  jz      loc_180056988
0x18005688f  mov     rcx, [rcx+168h]; hTheme
0x180056896  test    rcx, rcx
0x180056899  jz      loc_180056988
0x18005689f  xor     r8d, r8d; iStateId
0x1800568a2  lea     edx, [rsi+5]; iPartId
0x1800568a5  call    cs:__imp_IsThemePartDefined
0x1800568ab  mov     ecx, [rbx+190h]
0x1800568b1  lea     edx, [rsi+3]; iPartId
0x1800568b4  add     eax, eax
0x1800568b6  xor     r8d, r8d; iStateId
0x1800568b9  xor     eax, ecx
0x1800568bb  and     eax, 2
0x1800568be  xor     eax, ecx
0x1800568c0  mov     rcx, [rbx+168h]; hTheme
0x1800568c7  mov     [rbx+190h], eax
0x1800568cd  call    cs:__imp_IsThemePartDefined
0x1800568d3  test    eax, eax
0x1800568d5  jz      loc_1800569B6
0x1800568db  mov     eax, 80h
0x1800568e0  btr     dword ptr [rbx+78h], 7
0x1800568e5  lea     rcx, [rsp+0A8h+lf]; void *
0x1800568ea  or      [rbx+78h], eax
0x1800568ed  xor     edx, edx; Val
0x1800568ef  lea     r8d, [rdx+5Ch]; Size
0x1800568f3  call    memset_0
0x1800568f8  mov     rcx, [rbx+168h]; hTheme
0x1800568ff  lea     rax, [rsp+0A8h+lf]
0x180056904  xor     edx, edx; hdc
0x180056906  mov     [rsp+0A8h+pFont], rax; pFont
0x18005690b  mov     [rsp+0A8h+iPropId], 0D2h; iPropId
0x180056913  lea     r9d, [rdx+8]; iStateId
0x180056917  lea     r8d, [rdx+1]; iPartId
0x18005691b  call    cs:__imp_GetThemeFont
0x180056921  test    eax, eax
0x180056923  jns     loc_1800569CA
0x180056929  mov     rcx, [rbx+168h]; hTheme
0x180056930  lea     rax, [rbx+1B8h]
0x180056937  and     byte ptr [rbx+18Ch], 0FDh
0x18005693e  mov     edx, 1; iPartId
0x180056943  mov     r9d, 0EDBh; iPropId
0x180056949  mov     qword ptr [rsp+0A8h+iPropId], rax; pColor
0x18005694e  lea     r8d, [rdx+7]; iStateId
0x180056952  call    cs:__imp_GetThemeColor
0x180056958  test    eax, eax
0x18005695a  js      short loc_180056963
0x18005695c  or      byte ptr [rbx+18Ch], 2
0x180056963  mov     rcx, [rsp+0A8h+var_18]
0x18005696b  xor     rcx, rsp; StackCookie
0x18005696e  call    __security_check_cookie
0x180056973  lea     r11, [rsp+0A8h+var_8]
0x18005697b  mov     rbx, [r11+18h]
0x18005697f  mov     rsi, [r11+20h]
0x180056983  mov     rsp, r11
0x180056986  pop     rdi
0x180056987  retn
0x180056988  btr     dword ptr [rbx+78h], 7
0x18005698d  and     dword ptr [rbx+190h], 0FFFFFFFDh
0x180056994  and     byte ptr [rbx+18Ch], 0FDh
0x18005699b  mov     rcx, [rbx+1B0h]; ho
0x1800569a2  test    rcx, rcx
0x1800569a5  jz      short loc_180056963
0x1800569a7  call    cs:__imp_DeleteObject
0x1800569ad  mov     [rbx+1B0h], rsi
0x1800569b4  jmp     short loc_180056963
0x1800569b6  test    byte ptr [rbx+190h], 2
0x1800569bd  mov     eax, esi
0x1800569bf  jz      loc_1800568E0
0x1800569c5  jmp     loc_1800568DB
0x1800569ca  mov     edx, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x1800569d0  cmp     edx, 0FFFFFFFFh
0x1800569d3  jnz     short loc_180056A06
0x1800569d5  mov     edi, esi
0x1800569d7  call    cs:__imp_GetUserDefaultUILanguage
0x1800569dd  mov     cs:?s_langID@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4GA, ax; ushort `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_langID
0x1800569e4  test    ax, ax
0x1800569e7  jz      short loc_1800569F3
0x1800569e9  movzx   ecx, ax; unsigned int
0x1800569ec  call    ?IsBiDiLocale@@YAHK@Z; IsBiDiLocale(ulong)
0x1800569f1  mov     edi, eax
0x1800569f3  mov     ecx, esi
0x1800569f5  test    edi, edi
0x1800569f7  setnz   cl
0x1800569fa  xchg    ecx, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x180056a00  mov     edx, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x180056a06  movzx   ecx, [rsp+0A8h+lf.lfItalic]
0x180056a0b  cmp     edx, 1
0x180056a0e  cmovz   ecx, esi
0x180056a11  mov     [rsp+0A8h+lf.lfItalic], cl
0x180056a15  mov     rcx, [rbx+1B0h]; ho
0x180056a1c  test    rcx, rcx
0x180056a1f  jz      short loc_180056A27
0x180056a21  call    cs:__imp_DeleteObject
0x180056a27  lea     rcx, [rsp+0A8h+lf]; lplf
0x180056a2c  call    cs:__imp_CreateFontIndirectW
0x180056a32  mov     [rbx+1B0h], rax
0x180056a39  jmp     loc_180056929
```
