# Edit_SetIMEMenu(HMENU__ *,HWND__ *,EditMenuItemState)

- ea: `0x1800e8aa0`
- end: `0x1800e8da3`
- name: `?Edit_SetIMEMenu@@YAHPEAUHMENU__@@PEAUHWND__@@UEditMenuItemState@@@Z`
- size: `771`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18013be80`

## callees

- `0x1800e8aa0`
- `0x180106414`
- `0x180114520`
- `0x180114ebc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800e8b92`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800e8c29`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800e8ca2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800e8b92`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800e8c29`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800e8ca2`
- `USER32!GetKeyboardLayout` at `0x1800e8b03`
- `USER32!GetKeyboardLayout` at `0x1800e8b03`
- `USER32!GetSubMenu` at `0x1800e8b3d`
- `USER32!GetSubMenu` at `0x1800e8b3d`
- `USER32!GetMenuItemCount` at `0x1800e8b55`
- `USER32!GetMenuItemCount` at `0x1800e8b55`
- `USER32!GetSystemMetrics` at `0x1800e8aed`
- `USER32!GetSystemMetrics` at `0x1800e8aed`
- `USER32!InsertMenuItemW` at `0x1800e8bce`
- `USER32!InsertMenuItemW` at `0x1800e8c65`
- `USER32!InsertMenuItemW` at `0x1800e8d00`
- `USER32!InsertMenuItemW` at `0x1800e8d48`
- `USER32!InsertMenuItemW` at `0x1800e8bce`
- `USER32!InsertMenuItemW` at `0x1800e8c65`
- `USER32!InsertMenuItemW` at `0x1800e8d00`
- `USER32!InsertMenuItemW` at `0x1800e8d48`
- `USER32!DeleteMenu` at `0x1800e8d62`
- `USER32!DeleteMenu` at `0x1800e8d62`
- `IMM32!ImmGetContext` at `0x1800e8b26`
- `IMM32!ImmGetContext` at `0x1800e8b26`
- `IMM32!ImmIsIME` at `0x1800e8b0f`
- `IMM32!ImmIsIME` at `0x1800e8b0f`
- `IMM32!ImmReleaseContext` at `0x1800e8d70`
- `IMM32!ImmReleaseContext` at `0x1800e8d70`
- `IMM32!ImmGetConversionStatus` at `0x1800e8bfe`
- `IMM32!ImmGetConversionStatus` at `0x1800e8bfe`
- `IMM32!ImmGetProperty` at `0x1800e8bdf`
- `IMM32!ImmGetProperty` at `0x1800e8c84`
- `IMM32!ImmGetProperty` at `0x1800e8bdf`
- `IMM32!ImmGetProperty` at `0x1800e8c84`
- `IMM32!ImmGetOpenStatus` at `0x1800e8b6f`
- `IMM32!ImmGetOpenStatus` at `0x1800e8b6f`

## pseudocode

```c
__int64 __fastcall Edit_SetIMEMenu(HMENU a1, HWND a2, char a3)
{
  __int64 v6; // rcx
  HKL KeyboardLayout; // rdi
  HIMC Context; // r12
  HMENU SubMenu; // rax
  HMENU v11; // r14
  int v12; // r15d
  UINT MenuItemCount; // r13d
  BOOL OpenStatus; // eax
  UINT v15; // edx
  UINT v16; // edx
  char Property; // di
  UINT v18; // r8d
  MENUITEMINFOW mi; // [rsp+30h] [rbp-89h] BYREF
  DWORD fdwConversion[4]; // [rsp+80h] [rbp-39h] BYREF
  WCHAR Buffer[32]; // [rsp+90h] [rbp-29h] BYREF

  memset_0(&mi, 0, sizeof(mi));
  if ( !GetSystemMetrics(82) || (a3 & 8) == 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  KeyboardLayout = GetKeyboardLayout(0);
  if ( !ImmIsIME(KeyboardLayout) )
    return 1;
  Context = ImmGetContext(a2);
  if ( !Context )
    return 0;
  SubMenu = GetSubMenu(a1, 0);
  v11 = SubMenu;
  if ( !SubMenu )
    return 0;
  v12 = 0;
  MenuItemCount = GetMenuItemCount(SubMenu);
  if ( (_WORD)KeyboardLayout != 1042 )
  {
    OpenStatus = ImmGetOpenStatus(Context);
    v15 = 4179;
    if ( !OpenStatus )
      v15 = 4178;
    LoadStringW(g_hinst, v15, Buffer, 32);
    mi.cbSize = 80;
    mi.dwTypeData = Buffer;
    mi.fMask = 66;
    mi.cch = 32;
    mi.wID = 10001;
    InsertMenuItemW(v11, 0xFFFFu, 1, &mi);
    v12 = 1;
  }
  if ( (ImmGetProperty(KeyboardLayout, 8u) & 0x80u) != 0 )
  {
    fdwConversion[0] = 0;
    if ( !ImmGetConversionStatus(Context, fdwConversion, 0) || (v16 = 4181, SLOBYTE(fdwConversion[0]) >= 0) )
      v16 = 4180;
    LoadStringW(g_hinst, v16, Buffer, 32);
    mi.cbSize = 80;
    mi.dwTypeData = Buffer;
    mi.fMask = 66;
    mi.cch = 32;
    mi.wID = 10002;
    InsertMenuItemW(v11, 0xFFFFu, 1, &mi);
    ++v12;
  }
  if ( (_WORD)KeyboardLayout != 1042 )
  {
    Property = ImmGetProperty(KeyboardLayout, 0x14u);
    LoadStringW(g_hinst, 0x1056u, Buffer, 32);
    v18 = 0;
    mi.cbSize = 80;
    mi.fMask = 67;
    mi.dwTypeData = Buffer;
    mi.cch = 32;
    mi.wID = 10003;
    if ( (Property & 6) != 6 || (a3 & 1) != 0 )
      v18 = 3;
    mi.fState = v18;
    InsertMenuItemW(v11, 0xFFFFu, 1, &mi);
    ++v12;
  }
  if ( (a3 & 4) != 0 )
  {
    if ( v12 )
    {
      mi.cbSize = 80;
      mi.fMask = 256;
      mi.fType = 2048;
      mi.dwTypeData = 0;
      mi.cch = 0;
      InsertMenuItemW(v11, MenuItemCount, 1, &mi);
    }
  }
  else if ( !v12 )
  {
    DeleteMenu(v11, MenuItemCount - 1, 0x400u);
  }
  ImmReleaseContext(a2, Context);
  return 1;
}

```

## disassembly

```asm
0x1800e8aa0  mov     [rsp-8+arg_18], rbx
0x1800e8aa5  push    rbp
0x1800e8aa6  push    rsi
0x1800e8aa7  push    rdi
0x1800e8aa8  push    r12
0x1800e8aaa  push    r13
0x1800e8aac  push    r14
0x1800e8aae  push    r15
0x1800e8ab0  lea     rbp, [rsp-27h]
0x1800e8ab5  sub     rsp, 0E0h
0x1800e8abc  mov     rax, cs:__security_cookie
0x1800e8ac3  xor     rax, rsp
0x1800e8ac6  mov     [rbp+57h+var_40], rax
0x1800e8aca  mov     r14, rdx
0x1800e8acd  mov     [rsp+110h+var_F0], rdx
0x1800e8ad2  xor     edx, edx; Val
0x1800e8ad4  mov     ebx, r8d
0x1800e8ad7  mov     rsi, rcx
0x1800e8ada  lea     rcx, [rsp+110h+mi]; void *
0x1800e8adf  lea     r8d, [rdx+50h]; Size
0x1800e8ae3  call    memset_0
0x1800e8ae8  mov     ecx, 52h ; 'R'; nIndex
0x1800e8aed  call    cs:__imp_GetSystemMetrics
0x1800e8af3  test    eax, eax
0x1800e8af5  jz      short loc_1800E8AFC
0x1800e8af7  test    bl, 8
0x1800e8afa  jnz     short loc_1800E8B01
0x1800e8afc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800e8b01  xor     ecx, ecx; idThread
0x1800e8b03  call    cs:__imp_GetKeyboardLayout
0x1800e8b09  mov     rcx, rax; HKL
0x1800e8b0c  mov     rdi, rax
0x1800e8b0f  call    cs:__imp_ImmIsIME
0x1800e8b15  test    eax, eax
0x1800e8b17  jnz     short loc_1800E8B23
0x1800e8b19  mov     eax, 1
0x1800e8b1e  jmp     loc_1800E8D7C
0x1800e8b23  mov     rcx, r14; HWND
0x1800e8b26  call    cs:__imp_ImmGetContext
0x1800e8b2c  mov     r12, rax
0x1800e8b2f  test    rax, rax
0x1800e8b32  jz      loc_1800E8D7A
0x1800e8b38  xor     edx, edx; nPos
0x1800e8b3a  mov     rcx, rsi; hMenu
0x1800e8b3d  call    cs:__imp_GetSubMenu
0x1800e8b43  mov     r14, rax
0x1800e8b46  test    rax, rax
0x1800e8b49  jz      loc_1800E8D7A
0x1800e8b4f  mov     rcx, rax; hMenu
0x1800e8b52  xor     r15d, r15d
0x1800e8b55  call    cs:__imp_GetMenuItemCount
0x1800e8b5b  mov     r13d, eax
0x1800e8b5e  lea     esi, [r15+1]
0x1800e8b62  mov     eax, 412h
0x1800e8b67  cmp     di, ax
0x1800e8b6a  jz      short loc_1800E8BD7
0x1800e8b6c  mov     rcx, r12; HIMC
0x1800e8b6f  call    cs:__imp_ImmGetOpenStatus
0x1800e8b75  mov     rcx, cs:g_hinst; hInstance
0x1800e8b7c  lea     r9d, [r15+20h]; cchBufferMax
0x1800e8b80  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800e8b84  mov     edx, 1053h
0x1800e8b89  test    eax, eax
0x1800e8b8b  jnz     short loc_1800E8B92
0x1800e8b8d  mov     edx, 1052h; uID
0x1800e8b92  call    cs:__imp_LoadStringW
0x1800e8b98  lea     rax, [rbp+57h+Buffer]
0x1800e8b9c  mov     [rsp+110h+mi.cbSize], 50h ; 'P'
0x1800e8ba4  lea     r9, [rsp+110h+mi]; lpmi
0x1800e8ba9  mov     [rbp+57h+mi.dwTypeData], rax
0x1800e8bad  mov     r8d, esi; fByPosition
0x1800e8bb0  mov     [rsp+110h+mi.fMask], 42h ; 'B'
0x1800e8bb8  mov     edx, 0FFFFh; item
0x1800e8bbd  mov     [rbp+57h+mi.cch], 20h ; ' '
0x1800e8bc4  mov     rcx, r14; hmenu
0x1800e8bc7  mov     [rbp+57h+mi.wID], 2711h
0x1800e8bce  call    cs:__imp_InsertMenuItemW
0x1800e8bd4  mov     r15d, esi
0x1800e8bd7  mov     edx, 8; DWORD
0x1800e8bdc  mov     rcx, rdi; HKL
0x1800e8bdf  call    cs:__imp_ImmGetProperty
0x1800e8be5  test    al, al
0x1800e8be7  jns     loc_1800E8C6E
0x1800e8bed  xor     r8d, r8d; lpfdwSentence
0x1800e8bf0  mov     [rbp+57h+fdwConversion], 0
0x1800e8bf7  lea     rdx, [rbp+57h+fdwConversion]; lpfdwConversion
0x1800e8bfb  mov     rcx, r12; HIMC
0x1800e8bfe  call    cs:__imp_ImmGetConversionStatus
0x1800e8c04  test    eax, eax
0x1800e8c06  jz      short loc_1800E8C13
0x1800e8c08  test    byte ptr [rbp+57h+fdwConversion], 80h
0x1800e8c0c  mov     edx, 1055h
0x1800e8c11  jnz     short loc_1800E8C18
0x1800e8c13  mov     edx, 1054h; uID
0x1800e8c18  mov     rcx, cs:g_hinst; hInstance
0x1800e8c1f  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800e8c23  mov     r9d, 20h ; ' '; cchBufferMax
0x1800e8c29  call    cs:__imp_LoadStringW
0x1800e8c2f  lea     rax, [rbp+57h+Buffer]
0x1800e8c33  mov     [rsp+110h+mi.cbSize], 50h ; 'P'
0x1800e8c3b  lea     r9, [rsp+110h+mi]; lpmi
0x1800e8c40  mov     [rbp+57h+mi.dwTypeData], rax
0x1800e8c44  mov     r8d, esi; fByPosition
0x1800e8c47  mov     [rsp+110h+mi.fMask], 42h ; 'B'
0x1800e8c4f  mov     edx, 0FFFFh; item
0x1800e8c54  mov     [rbp+57h+mi.cch], 20h ; ' '
0x1800e8c5b  mov     rcx, r14; hmenu
0x1800e8c5e  mov     [rbp+57h+mi.wID], 2712h
0x1800e8c65  call    cs:__imp_InsertMenuItemW
0x1800e8c6b  add     r15d, esi
0x1800e8c6e  mov     eax, 412h
0x1800e8c73  cmp     di, ax
0x1800e8c76  jz      loc_1800E8D09
0x1800e8c7c  mov     edx, 14h; DWORD
0x1800e8c81  mov     rcx, rdi; HKL
0x1800e8c84  call    cs:__imp_ImmGetProperty
0x1800e8c8a  mov     rcx, cs:g_hinst; hInstance
0x1800e8c91  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800e8c95  mov     r9d, 20h ; ' '; cchBufferMax
0x1800e8c9b  mov     edx, 1056h; uID
0x1800e8ca0  mov     edi, eax
0x1800e8ca2  call    cs:__imp_LoadStringW
0x1800e8ca8  xor     r8d, r8d
0x1800e8cab  mov     [rsp+110h+mi.cbSize], 50h ; 'P'
0x1800e8cb3  lea     rax, [rbp+57h+Buffer]
0x1800e8cb7  mov     [rsp+110h+mi.fMask], 43h ; 'C'
0x1800e8cbf  and     dil, 6
0x1800e8cc3  mov     [rbp+57h+mi.dwTypeData], rax
0x1800e8cc7  cmp     dil, 6
0x1800e8ccb  mov     [rbp+57h+mi.cch], 20h ; ' '
0x1800e8cd2  lea     r9, [rsp+110h+mi]; lpmi
0x1800e8cd7  mov     [rbp+57h+mi.wID], 2713h
0x1800e8cde  setz    cl
0x1800e8ce1  mov     edx, 0FFFFh; item
0x1800e8ce6  test    sil, bl
0x1800e8ce9  setz    al
0x1800e8cec  test    al, cl
0x1800e8cee  lea     eax, [r8+3]
0x1800e8cf2  mov     rcx, r14; hmenu
0x1800e8cf5  cmovz   r8d, eax
0x1800e8cf9  mov     [rbp+57h+mi.fState], r8d
0x1800e8cfd  mov     r8d, esi; fByPosition
0x1800e8d00  call    cs:__imp_InsertMenuItemW
0x1800e8d06  add     r15d, esi
0x1800e8d09  test    bl, 4
0x1800e8d0c  jz      short loc_1800E8D50
0x1800e8d0e  test    r15d, r15d
0x1800e8d11  jz      short loc_1800E8D68
0x1800e8d13  lea     r9, [rsp+110h+mi]; lpmi
0x1800e8d18  mov     [rsp+110h+mi.cbSize], 50h ; 'P'
0x1800e8d20  mov     r8d, esi; fByPosition
0x1800e8d23  mov     [rsp+110h+mi.fMask], 100h
0x1800e8d2b  mov     edx, r13d; item
0x1800e8d2e  mov     [rsp+110h+mi.fType], 800h
0x1800e8d36  mov     rcx, r14; hmenu
0x1800e8d39  mov     [rbp+57h+mi.dwTypeData], 0
0x1800e8d41  mov     [rbp+57h+mi.cch], 0
0x1800e8d48  call    cs:__imp_InsertMenuItemW
0x1800e8d4e  jmp     short loc_1800E8D68
0x1800e8d50  test    r15d, r15d
0x1800e8d53  jnz     short loc_1800E8D68
0x1800e8d55  lea     edx, [r13-1]; uPosition
0x1800e8d59  mov     r8d, 400h; uFlags
0x1800e8d5f  mov     rcx, r14; hMenu
0x1800e8d62  call    cs:__imp_DeleteMenu
0x1800e8d68  mov     rcx, [rsp+110h+var_F0]; HWND
0x1800e8d6d  mov     rdx, r12; HIMC
0x1800e8d70  call    cs:__imp_ImmReleaseContext
0x1800e8d76  mov     eax, esi
0x1800e8d78  jmp     short loc_1800E8D7C
0x1800e8d7a  xor     eax, eax
0x1800e8d7c  mov     rcx, [rbp+57h+var_40]
0x1800e8d80  xor     rcx, rsp; StackCookie
0x1800e8d83  call    __security_check_cookie
0x1800e8d88  mov     rbx, [rsp+110h+arg_18]
0x1800e8d90  add     rsp, 0E0h
0x1800e8d97  pop     r15
0x1800e8d99  pop     r14
0x1800e8d9b  pop     r13
0x1800e8d9d  pop     r12
0x1800e8d9f  pop     rdi
0x1800e8da0  pop     rsi
0x1800e8da1  pop     rbp
0x1800e8da2  retn
```
