# LauncherReadBootNextFile(_BOOT_NEXT_HEADER *)

- ea: `0x180007e74`
- end: `0x180008103`
- name: `?LauncherReadBootNextFile@@YAHPEAU_BOOT_NEXT_HEADER@@@Z`
- size: `655`
- prototype: `__int64 __fastcall(struct _BOOT_NEXT_HEADER *lpBuffer)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x1800070ec`

## callees

- `0x180005528`
- `0x1800077f8`
- `0x180007e74`
- `0x180008ac8`
- `0x180008cf0`
- `0x18000fdd6`
- `0x18000fe10`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180008078`
- `KERNEL32!CloseHandle` at `0x180008078`
- `KERNEL32!GetLastError` at `0x180007f46`
- `KERNEL32!GetLastError` at `0x180007fab`
- `KERNEL32!GetLastError` at `0x180008001`
- `KERNEL32!GetLastError` at `0x180008098`
- `KERNEL32!GetLastError` at `0x180007f46`
- `KERNEL32!GetLastError` at `0x180007fab`
- `KERNEL32!GetLastError` at `0x180008001`
- `KERNEL32!GetLastError` at `0x180008098`
- `KERNEL32!ReadFile` at `0x180007ff7`
- `KERNEL32!ReadFile` at `0x180007ff7`
- `KERNEL32!SetLastError` at `0x180008080`
- `KERNEL32!SetLastError` at `0x180008080`
- `KERNEL32!CreateFileW` at `0x180007f9c`
- `KERNEL32!CreateFileW` at `0x180007f9c`

## string_xrefs

- `0x180007f1d`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180008030`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
__int64 __fastcall LauncherReadBootNextFile(struct _BOOT_NEXT_HEADER *lpBuffer)
{
  unsigned int v2; // esi
  _QWORD *v3; // rcx
  DWORD v4; // ebx
  DWORD v5; // eax
  HANDLE FileW; // rax
  void *v7; // rdi
  DWORD LastError; // eax
  DWORD v9; // eax
  int v10; // r8d
  int v11; // r9d
  const char *v12; // rcx
  char hTemplateFile; // [rsp+30h] [rbp-258h]
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-248h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-238h] BYREF

  v2 = 0;
  memset_0(FileName, 0, 0x20Au);
  NumberOfBytesRead = 0;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  if ( lpBuffer )
  {
    if ( (unsigned int)LauncherGetSystemPartitionFilePath(L"\\\\?\\GlobalRoot%s\\BOOTNXT", FileName) )
    {
      FileW = CreateFileW(FileName, 0x80000000, 0, 0, 3u, 0, 0);
      v7 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sdD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
            (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
            136,
            LastError);
      }
      else
      {
        if ( ReadFile(FileW, lpBuffer, 1u, &NumberOfBytesRead, 0) )
        {
          if ( NumberOfBytesRead == 1 )
          {
            v4 = 0;
            v2 = 1;
          }
          else
          {
            v4 = 24;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sdD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                33,
                (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
                (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
                144,
                24);
          }
        }
        else
        {
          v9 = GetLastError();
          v4 = v9;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sdD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              32,
              (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
              (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
              142,
              v9);
        }
        CloseHandle(v7);
      }
    }
    else
    {
      v5 = GetLastError();
      v4 = v5;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          125,
          v5);
    }
  }
  else
  {
    v4 = 87;
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 )
      WPP_SF_sdD(
        v3[2],
        29,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        122,
        87);
  }
  SetLastError(v4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    hTemplateFile = GetLastError();
    v12 = "Success";
    if ( !v2 )
      v12 = "Failure";
    WPP_SF_sdsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, v10, v11, 156, (__int64)v12, hTemplateFile);
  }
  return v2;
}

```

## disassembly

```asm
0x180007e74  mov     [rsp+arg_8], rbx
0x180007e79  mov     [rsp+arg_10], rsi
0x180007e7e  push    rdi
0x180007e7f  push    r14
0x180007e81  push    r15
0x180007e83  sub     rsp, 270h
0x180007e8a  mov     rax, cs:__security_cookie
0x180007e91  xor     rax, rsp
0x180007e94  mov     [rsp+288h+var_28], rax
0x180007e9c  mov     rbx, rcx
0x180007e9f  xor     esi, esi
0x180007ea1  lea     rcx, [rsp+288h+FileName]; void *
0x180007ea6  xor     edx, edx; Val
0x180007ea8  mov     r8d, 20Ah; Size
0x180007eae  call    memset_0
0x180007eb3  mov     [rsp+288h+NumberOfBytesRead], esi
0x180007eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ebe  lea     r14, WPP_GLOBAL_Control
0x180007ec5  lea     r15, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180007ecc  cmp     rcx, r14
0x180007ecf  jz      short loc_180007EED
0x180007ed1  test    byte ptr [rcx+1Ch], 8
0x180007ed5  jz      short loc_180007EED
0x180007ed7  mov     rcx, [rcx+10h]
0x180007edb  lea     edx, [rsi+1Ch]
0x180007ede  mov     r8, r15
0x180007ee1  call    WPP_SF_
0x180007ee6  mov     rcx, cs:WPP_GLOBAL_Control
0x180007eed  test    rbx, rbx
0x180007ef0  jnz     short loc_180007F31
0x180007ef2  mov     ebx, 57h ; 'W'
0x180007ef7  cmp     rcx, r14
0x180007efa  jz      loc_18000807E
0x180007f00  test    byte ptr [rcx+1Ch], 1
0x180007f04  jz      loc_18000807E
0x180007f0a  mov     [rsp+288h+dwFlagsAndAttributes], ebx
0x180007f0e  lea     edx, [rbx-3Ah]
0x180007f11  mov     [rsp+288h+dwCreationDisposition], 17Ah
0x180007f19  mov     rcx, [rcx+10h]
0x180007f1d  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180007f24  mov     r8, r15
0x180007f27  call    WPP_SF_sdD
0x180007f2c  jmp     loc_18000807E
0x180007f31  lea     rdx, [rsp+288h+FileName]; unsigned __int16 *
0x180007f36  lea     rcx, aGlobalrootSBoo_0; "\\\\?\\GlobalRoot%s\\BOOTNXT"
0x180007f3d  call    ?LauncherGetSystemPartitionFilePath@@YAHPEBGPEAG@Z; LauncherGetSystemPartitionFilePath(ushort const *,ushort *)
0x180007f42  test    eax, eax
0x180007f44  jnz     short loc_180007F7B
0x180007f46  call    cs:__imp_GetLastError
0x180007f4c  mov     ebx, eax
0x180007f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f55  cmp     rcx, r14
0x180007f58  jz      loc_18000807E
0x180007f5e  test    byte ptr [rcx+1Ch], 1
0x180007f62  jz      loc_18000807E
0x180007f68  mov     [rsp+288h+dwFlagsAndAttributes], eax
0x180007f6c  mov     edx, 1Eh
0x180007f71  mov     [rsp+288h+dwCreationDisposition], 17Dh
0x180007f79  jmp     short loc_180007F19
0x180007f7b  mov     qword ptr [rsp+288h+hTemplateFile], rsi; hTemplateFile
0x180007f80  lea     rcx, [rsp+288h+FileName]; lpFileName
0x180007f85  mov     [rsp+288h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x180007f89  xor     r9d, r9d; lpSecurityAttributes
0x180007f8c  xor     r8d, r8d; dwShareMode
0x180007f8f  mov     [rsp+288h+dwCreationDisposition], 3; dwCreationDisposition
0x180007f97  mov     edx, 80000000h; dwDesiredAccess
0x180007f9c  call    cs:__imp_CreateFileW
0x180007fa2  mov     rdi, rax
0x180007fa5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007fa9  jnz     short loc_180007FE1
0x180007fab  call    cs:__imp_GetLastError
0x180007fb1  mov     ebx, eax
0x180007fb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fba  cmp     rcx, r14
0x180007fbd  jz      loc_18000807E
0x180007fc3  test    byte ptr [rcx+1Ch], 1
0x180007fc7  jz      loc_18000807E
0x180007fcd  mov     [rsp+288h+dwFlagsAndAttributes], eax
0x180007fd1  lea     edx, [rdi+20h]
0x180007fd4  mov     [rsp+288h+dwCreationDisposition], 188h
0x180007fdc  jmp     loc_180007F19
0x180007fe1  lea     r9, [rsp+288h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180007fe6  mov     qword ptr [rsp+288h+dwCreationDisposition], rsi; lpOverlapped
0x180007feb  mov     r8d, 1; nNumberOfBytesToRead
0x180007ff1  mov     rdx, rbx; lpBuffer
0x180007ff4  mov     rcx, rdi; hFile
0x180007ff7  call    cs:__imp_ReadFile
0x180007ffd  test    eax, eax
0x180007fff  jnz     short loc_180008041
0x180008001  call    cs:__imp_GetLastError
0x180008007  mov     ebx, eax
0x180008009  mov     rcx, cs:WPP_GLOBAL_Control
0x180008010  cmp     rcx, r14
0x180008013  jz      short loc_180008075
0x180008015  test    byte ptr [rcx+1Ch], 1
0x180008019  jz      short loc_180008075
0x18000801b  mov     [rsp+288h+dwFlagsAndAttributes], eax
0x18000801f  mov     edx, 20h ; ' '
0x180008024  mov     [rsp+288h+dwCreationDisposition], 18Eh
0x18000802c  mov     rcx, [rcx+10h]
0x180008030  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180008037  mov     r8, r15
0x18000803a  call    WPP_SF_sdD
0x18000803f  jmp     short loc_180008075
0x180008041  cmp     [rsp+288h+NumberOfBytesRead], 1
0x180008046  jz      short loc_180008070
0x180008048  mov     ebx, 18h
0x18000804d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008054  cmp     rcx, r14
0x180008057  jz      short loc_180008075
0x180008059  test    byte ptr [rcx+1Ch], 1
0x18000805d  jz      short loc_180008075
0x18000805f  mov     [rsp+288h+dwFlagsAndAttributes], ebx
0x180008063  lea     edx, [rbx+9]
0x180008066  mov     [rsp+288h+dwCreationDisposition], 190h
0x18000806e  jmp     short loc_18000802C
0x180008070  xor     ebx, ebx
0x180008072  lea     esi, [rbx+1]
0x180008075  mov     rcx, rdi; hObject
0x180008078  call    cs:__imp_CloseHandle
0x18000807e  mov     ecx, ebx; dwErrCode
0x180008080  call    cs:__imp_SetLastError
0x180008086  mov     rax, cs:WPP_GLOBAL_Control
0x18000808d  cmp     rax, r14
0x180008090  jz      short loc_1800080D8
0x180008092  test    byte ptr [rax+1Ch], 4
0x180008096  jz      short loc_1800080D8
0x180008098  call    cs:__imp_GetLastError
0x18000809e  lea     rdx, aFailure; "Failure"
0x1800080a5  mov     dword ptr [rsp+288h+hTemplateFile], eax
0x1800080a9  test    esi, esi
0x1800080ab  lea     rcx, aSuccess; "Success"
0x1800080b2  cmovz   rcx, rdx
0x1800080b6  mov     edx, 22h ; '"'
0x1800080bb  mov     qword ptr [rsp+288h+dwFlagsAndAttributes], rcx
0x1800080c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080c7  mov     [rsp+288h+dwCreationDisposition], 19Ch
0x1800080cf  mov     rcx, [rcx+10h]
0x1800080d3  call    WPP_SF_sdsd
0x1800080d8  mov     eax, esi
0x1800080da  mov     rcx, [rsp+288h+var_28]
0x1800080e2  xor     rcx, rsp; StackCookie
0x1800080e5  call    __security_check_cookie
0x1800080ea  lea     r11, [rsp+288h+var_18]
0x1800080f2  mov     rbx, [r11+28h]
0x1800080f6  mov     rsi, [r11+30h]
0x1800080fa  mov     rsp, r11
0x1800080fd  pop     r15
0x1800080ff  pop     r14
0x180008101  pop     rdi
0x180008102  retn
```
