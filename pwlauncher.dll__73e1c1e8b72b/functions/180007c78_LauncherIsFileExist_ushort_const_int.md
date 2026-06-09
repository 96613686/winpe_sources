# LauncherIsFileExist(ushort const *,int *)

- ea: `0x180007c78`
- end: `0x180007e6c`
- name: `?LauncherIsFileExist@@YAHPEBGPEAH@Z`
- size: `500`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int *, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x1800070ec`

## callees

- `0x180005528`
- `0x180007c78`
- `0x180008ac8`
- `0x180008b30`
- `0x180008ba4`
- `0x180008cf0`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180007cfc`
- `KERNEL32!GetFileAttributesW` at `0x180007cfc`
- `KERNEL32!GetLastError` at `0x180007d40`
- `KERNEL32!GetLastError` at `0x180007d98`
- `KERNEL32!GetLastError` at `0x180007dc9`
- `KERNEL32!GetLastError` at `0x180007e1f`
- `KERNEL32!GetLastError` at `0x180007d40`
- `KERNEL32!GetLastError` at `0x180007d98`
- `KERNEL32!GetLastError` at `0x180007dc9`
- `KERNEL32!GetLastError` at `0x180007e1f`
- `KERNEL32!SetLastError` at `0x180007e07`
- `KERNEL32!SetLastError` at `0x180007e07`

## string_xrefs

- `0x180007d1d`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180007d64`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180007da5`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180007dee`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
__int64 __fastcall LauncherIsFileExist(LPCWSTR lpFileName, int *a2, int a3, int a4)
{
  unsigned int v6; // edi
  _QWORD *v7; // rcx
  int v8; // eax
  DWORD LastError; // ebx
  int v10; // r8d
  int v11; // r9d
  const char *v12; // rcx
  __int64 v14; // [rsp+28h] [rbp-40h]
  char v15; // [rsp+30h] [rbp-38h]

  v6 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( a2 && lpFileName )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
      WPP_SF_sdS(v7[2], 56, a3, a4, 211, (__int64)lpFileName);
    if ( GetFileAttributesW(lpFileName) != -1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          57,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          217);
      v8 = 1;
LABEL_19:
      LastError = 0;
      *a2 = v8;
      v6 = 1;
      goto LABEL_27;
    }
    if ( GetLastError() == 2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          58,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          224);
      v8 = 0;
      goto LABEL_19;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LODWORD(v14) = GetLastError();
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        229,
        v14);
    }
    LastError = GetLastError();
  }
  else
  {
    LastError = 87;
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
      WPP_SF_sdD(
        v7[2],
        55,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        209,
        87);
  }
LABEL_27:
  SetLastError(LastError);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v15 = GetLastError();
    v12 = "Success";
    if ( !v6 )
      v12 = "Failure";
    WPP_SF_sdsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, v10, v11, 240, (__int64)v12, v15);
  }
  return v6;
}

```

## disassembly

```asm
0x180007c78  push    rbx
0x180007c7a  push    rbp
0x180007c7b  push    rsi
0x180007c7c  push    rdi
0x180007c7d  push    r15
0x180007c7f  sub     rsp, 40h
0x180007c83  mov     rsi, rdx
0x180007c86  mov     rbx, rcx
0x180007c89  xor     edi, edi
0x180007c8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c92  lea     rbp, WPP_GLOBAL_Control
0x180007c99  lea     r15, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180007ca0  cmp     rcx, rbp
0x180007ca3  jz      short loc_180007CC1
0x180007ca5  test    byte ptr [rcx+1Ch], 8
0x180007ca9  jz      short loc_180007CC1
0x180007cab  mov     rcx, [rcx+10h]
0x180007caf  lea     edx, [rdi+36h]
0x180007cb2  mov     r8, r15
0x180007cb5  call    WPP_SF_
0x180007cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cc1  test    rsi, rsi
0x180007cc4  jz      loc_180007DD3
0x180007cca  test    rbx, rbx
0x180007ccd  jz      loc_180007DD3
0x180007cd3  cmp     rcx, rbp
0x180007cd6  jz      short loc_180007CF9
0x180007cd8  test    byte ptr [rcx+1Ch], 4
0x180007cdc  jz      short loc_180007CF9
0x180007cde  mov     rcx, [rcx+10h]
0x180007ce2  mov     edx, 38h ; '8'
0x180007ce7  mov     [rsp+68h+var_40], rbx
0x180007cec  mov     [rsp+68h+var_48], 2D3h
0x180007cf4  call    WPP_SF_sdS
0x180007cf9  mov     rcx, rbx; lpFileName
0x180007cfc  call    cs:__imp_GetFileAttributesW
0x180007d02  cmp     eax, 0FFFFFFFFh
0x180007d05  jz      short loc_180007D40
0x180007d07  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d0e  cmp     rcx, rbp
0x180007d11  jz      short loc_180007D39
0x180007d13  test    byte ptr [rcx+1Ch], 4
0x180007d17  jz      short loc_180007D39
0x180007d19  mov     rcx, [rcx+10h]
0x180007d1d  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180007d24  mov     edx, 39h ; '9'
0x180007d29  mov     [rsp+68h+var_48], 2D9h
0x180007d31  mov     r8, r15
0x180007d34  call    WPP_SF_sd
0x180007d39  mov     eax, 1
0x180007d3e  jmp     short loc_180007D7D
0x180007d40  call    cs:__imp_GetLastError
0x180007d46  cmp     eax, 2
0x180007d49  jnz     short loc_180007D86
0x180007d4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d52  cmp     rcx, rbp
0x180007d55  jz      short loc_180007D7B
0x180007d57  test    byte ptr [rcx+1Ch], 4
0x180007d5b  jz      short loc_180007D7B
0x180007d5d  mov     rcx, [rcx+10h]
0x180007d61  lea     edx, [rax+38h]
0x180007d64  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180007d6b  mov     [rsp+68h+var_48], 2E0h
0x180007d73  mov     r8, r15
0x180007d76  call    WPP_SF_sd
0x180007d7b  xor     eax, eax
0x180007d7d  xor     ebx, ebx
0x180007d7f  mov     [rsi], eax
0x180007d81  lea     edi, [rbx+1]
0x180007d84  jmp     short loc_180007E05
0x180007d86  mov     rax, cs:WPP_GLOBAL_Control
0x180007d8d  cmp     rax, rbp
0x180007d90  jz      short loc_180007DC9
0x180007d92  test    byte ptr [rax+1Ch], 1
0x180007d96  jz      short loc_180007DC9
0x180007d98  call    cs:__imp_GetLastError
0x180007d9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007da5  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180007dac  mov     dword ptr [rsp+68h+var_40], eax
0x180007db0  mov     edx, 3Bh ; ';'
0x180007db5  mov     r8, r15
0x180007db8  mov     [rsp+68h+var_48], 2E5h
0x180007dc0  mov     rcx, [rcx+10h]
0x180007dc4  call    WPP_SF_sdD
0x180007dc9  call    cs:__imp_GetLastError
0x180007dcf  mov     ebx, eax
0x180007dd1  jmp     short loc_180007E05
0x180007dd3  mov     ebx, 57h ; 'W'
0x180007dd8  cmp     rcx, rbp
0x180007ddb  jz      short loc_180007E05
0x180007ddd  test    byte ptr [rcx+1Ch], 1
0x180007de1  jz      short loc_180007E05
0x180007de3  mov     rcx, [rcx+10h]
0x180007de7  lea     edx, [rbx-20h]
0x180007dea  mov     dword ptr [rsp+68h+var_40], ebx
0x180007dee  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180007df5  mov     r8, r15
0x180007df8  mov     [rsp+68h+var_48], 2D1h
0x180007e00  call    WPP_SF_sdD
0x180007e05  mov     ecx, ebx; dwErrCode
0x180007e07  call    cs:__imp_SetLastError
0x180007e0d  mov     rax, cs:WPP_GLOBAL_Control
0x180007e14  cmp     rax, rbp
0x180007e17  jz      short loc_180007E5F
0x180007e19  test    byte ptr [rax+1Ch], 4
0x180007e1d  jz      short loc_180007E5F
0x180007e1f  call    cs:__imp_GetLastError
0x180007e25  lea     rdx, aFailure; "Failure"
0x180007e2c  mov     dword ptr [rsp+68h+var_38], eax
0x180007e30  test    edi, edi
0x180007e32  lea     rcx, aSuccess; "Success"
0x180007e39  cmovz   rcx, rdx
0x180007e3d  mov     edx, 3Ch ; '<'
0x180007e42  mov     [rsp+68h+var_40], rcx
0x180007e47  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e4e  mov     [rsp+68h+var_48], 2F0h
0x180007e56  mov     rcx, [rcx+10h]
0x180007e5a  call    WPP_SF_sdsd
0x180007e5f  mov     eax, edi
0x180007e61  add     rsp, 40h
0x180007e65  pop     r15
0x180007e67  pop     rdi
0x180007e68  pop     rsi
0x180007e69  pop     rbp
0x180007e6a  pop     rbx
0x180007e6b  retn
```
