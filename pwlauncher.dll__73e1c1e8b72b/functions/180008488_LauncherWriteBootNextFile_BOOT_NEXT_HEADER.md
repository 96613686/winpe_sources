# LauncherWriteBootNextFile(_BOOT_NEXT_HEADER *)

- ea: `0x180008488`
- end: `0x180008717`
- name: `?LauncherWriteBootNextFile@@YAHPEAU_BOOT_NEXT_HEADER@@@Z`
- size: `655`
- prototype: `__int64 __fastcall(LPCVOID lpBuffer)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x180005c98`

## callees

- `0x180005528`
- `0x1800077f8`
- `0x180008488`
- `0x180008ac8`
- `0x180008cf0`
- `0x18000fdd6`
- `0x18000fe10`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000868c`
- `KERNEL32!CloseHandle` at `0x18000868c`
- `KERNEL32!GetLastError` at `0x18000855a`
- `KERNEL32!GetLastError` at `0x1800085bf`
- `KERNEL32!GetLastError` at `0x180008615`
- `KERNEL32!GetLastError` at `0x1800086ac`
- `KERNEL32!GetLastError` at `0x18000855a`
- `KERNEL32!GetLastError` at `0x1800085bf`
- `KERNEL32!GetLastError` at `0x180008615`
- `KERNEL32!GetLastError` at `0x1800086ac`
- `KERNEL32!SetLastError` at `0x180008694`
- `KERNEL32!SetLastError` at `0x180008694`
- `KERNEL32!WriteFile` at `0x18000860b`
- `KERNEL32!WriteFile` at `0x18000860b`
- `KERNEL32!CreateFileW` at `0x1800085b0`
- `KERNEL32!CreateFileW` at `0x1800085b0`

## string_xrefs

- `0x180008531`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180008644`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
__int64 __fastcall LauncherWriteBootNextFile(LPCVOID lpBuffer)
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
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-248h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-238h] BYREF

  v2 = 0;
  memset_0(FileName, 0, 0x20Au);
  NumberOfBytesWritten = 0;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  if ( lpBuffer )
  {
    if ( (unsigned int)LauncherGetSystemPartitionFilePath(L"\\\\?\\GlobalRoot%s\\BOOTNXT", FileName) )
    {
      FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 3u, 0, 0);
      v7 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sdD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            38,
            (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
            (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
            208,
            LastError);
      }
      else
      {
        if ( WriteFile(FileW, lpBuffer, 1u, &NumberOfBytesWritten, 0) )
        {
          if ( NumberOfBytesWritten == 1 )
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
                40,
                (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
                (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
                216,
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
              39,
              (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
              (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
              214,
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
          37,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          197,
          v5);
    }
  }
  else
  {
    v4 = 87;
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 )
      WPP_SF_sdD(
        v3[2],
        36,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        194,
        87);
  }
  SetLastError(v4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    hTemplateFile = GetLastError();
    v12 = "Success";
    if ( !v2 )
      v12 = "Failure";
    WPP_SF_sdsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, v10, v11, 228, (__int64)v12, hTemplateFile);
  }
  return v2;
}

```

## disassembly

```asm
0x180008488  mov     [rsp+arg_8], rbx
0x18000848d  mov     [rsp+arg_10], rsi
0x180008492  push    rdi
0x180008493  push    r14
0x180008495  push    r15
0x180008497  sub     rsp, 270h
0x18000849e  mov     rax, cs:__security_cookie
0x1800084a5  xor     rax, rsp
0x1800084a8  mov     [rsp+288h+var_28], rax
0x1800084b0  mov     rbx, rcx
0x1800084b3  xor     esi, esi
0x1800084b5  lea     rcx, [rsp+288h+FileName]; void *
0x1800084ba  xor     edx, edx; Val
0x1800084bc  mov     r8d, 20Ah; Size
0x1800084c2  call    memset_0
0x1800084c7  mov     [rsp+288h+NumberOfBytesWritten], esi
0x1800084cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084d2  lea     r14, WPP_GLOBAL_Control
0x1800084d9  lea     r15, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x1800084e0  cmp     rcx, r14
0x1800084e3  jz      short loc_180008501
0x1800084e5  test    byte ptr [rcx+1Ch], 8
0x1800084e9  jz      short loc_180008501
0x1800084eb  mov     rcx, [rcx+10h]
0x1800084ef  lea     edx, [rsi+23h]
0x1800084f2  mov     r8, r15
0x1800084f5  call    WPP_SF_
0x1800084fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180008501  test    rbx, rbx
0x180008504  jnz     short loc_180008545
0x180008506  mov     ebx, 57h ; 'W'
0x18000850b  cmp     rcx, r14
0x18000850e  jz      loc_180008692
0x180008514  test    byte ptr [rcx+1Ch], 1
0x180008518  jz      loc_180008692
0x18000851e  mov     [rsp+288h+dwFlagsAndAttributes], ebx
0x180008522  lea     edx, [rbx-33h]
0x180008525  mov     [rsp+288h+dwCreationDisposition], 1C2h
0x18000852d  mov     rcx, [rcx+10h]
0x180008531  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180008538  mov     r8, r15
0x18000853b  call    WPP_SF_sdD
0x180008540  jmp     loc_180008692
0x180008545  lea     rdx, [rsp+288h+FileName]; unsigned __int16 *
0x18000854a  lea     rcx, aGlobalrootSBoo_0; "\\\\?\\GlobalRoot%s\\BOOTNXT"
0x180008551  call    ?LauncherGetSystemPartitionFilePath@@YAHPEBGPEAG@Z; LauncherGetSystemPartitionFilePath(ushort const *,ushort *)
0x180008556  test    eax, eax
0x180008558  jnz     short loc_18000858F
0x18000855a  call    cs:__imp_GetLastError
0x180008560  mov     ebx, eax
0x180008562  mov     rcx, cs:WPP_GLOBAL_Control
0x180008569  cmp     rcx, r14
0x18000856c  jz      loc_180008692
0x180008572  test    byte ptr [rcx+1Ch], 1
0x180008576  jz      loc_180008692
0x18000857c  mov     [rsp+288h+dwFlagsAndAttributes], eax
0x180008580  mov     edx, 25h ; '%'
0x180008585  mov     [rsp+288h+dwCreationDisposition], 1C5h
0x18000858d  jmp     short loc_18000852D
0x18000858f  mov     qword ptr [rsp+288h+hTemplateFile], rsi; hTemplateFile
0x180008594  lea     rcx, [rsp+288h+FileName]; lpFileName
0x180008599  mov     [rsp+288h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18000859d  xor     r9d, r9d; lpSecurityAttributes
0x1800085a0  xor     r8d, r8d; dwShareMode
0x1800085a3  mov     [rsp+288h+dwCreationDisposition], 3; dwCreationDisposition
0x1800085ab  mov     edx, 40000000h; dwDesiredAccess
0x1800085b0  call    cs:__imp_CreateFileW
0x1800085b6  mov     rdi, rax
0x1800085b9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800085bd  jnz     short loc_1800085F5
0x1800085bf  call    cs:__imp_GetLastError
0x1800085c5  mov     ebx, eax
0x1800085c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085ce  cmp     rcx, r14
0x1800085d1  jz      loc_180008692
0x1800085d7  test    byte ptr [rcx+1Ch], 1
0x1800085db  jz      loc_180008692
0x1800085e1  mov     [rsp+288h+dwFlagsAndAttributes], eax
0x1800085e5  lea     edx, [rdi+27h]
0x1800085e8  mov     [rsp+288h+dwCreationDisposition], 1D0h
0x1800085f0  jmp     loc_18000852D
0x1800085f5  lea     r9, [rsp+288h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800085fa  mov     qword ptr [rsp+288h+dwCreationDisposition], rsi; lpOverlapped
0x1800085ff  mov     r8d, 1; nNumberOfBytesToWrite
0x180008605  mov     rdx, rbx; lpBuffer
0x180008608  mov     rcx, rdi; hFile
0x18000860b  call    cs:__imp_WriteFile
0x180008611  test    eax, eax
0x180008613  jnz     short loc_180008655
0x180008615  call    cs:__imp_GetLastError
0x18000861b  mov     ebx, eax
0x18000861d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008624  cmp     rcx, r14
0x180008627  jz      short loc_180008689
0x180008629  test    byte ptr [rcx+1Ch], 1
0x18000862d  jz      short loc_180008689
0x18000862f  mov     [rsp+288h+dwFlagsAndAttributes], eax
0x180008633  mov     edx, 27h ; '''
0x180008638  mov     [rsp+288h+dwCreationDisposition], 1D6h
0x180008640  mov     rcx, [rcx+10h]
0x180008644  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x18000864b  mov     r8, r15
0x18000864e  call    WPP_SF_sdD
0x180008653  jmp     short loc_180008689
0x180008655  cmp     [rsp+288h+NumberOfBytesWritten], 1
0x18000865a  jz      short loc_180008684
0x18000865c  mov     ebx, 18h
0x180008661  mov     rcx, cs:WPP_GLOBAL_Control
0x180008668  cmp     rcx, r14
0x18000866b  jz      short loc_180008689
0x18000866d  test    byte ptr [rcx+1Ch], 1
0x180008671  jz      short loc_180008689
0x180008673  mov     [rsp+288h+dwFlagsAndAttributes], ebx
0x180008677  lea     edx, [rbx+10h]
0x18000867a  mov     [rsp+288h+dwCreationDisposition], 1D8h
0x180008682  jmp     short loc_180008640
0x180008684  xor     ebx, ebx
0x180008686  lea     esi, [rbx+1]
0x180008689  mov     rcx, rdi; hObject
0x18000868c  call    cs:__imp_CloseHandle
0x180008692  mov     ecx, ebx; dwErrCode
0x180008694  call    cs:__imp_SetLastError
0x18000869a  mov     rax, cs:WPP_GLOBAL_Control
0x1800086a1  cmp     rax, r14
0x1800086a4  jz      short loc_1800086EC
0x1800086a6  test    byte ptr [rax+1Ch], 4
0x1800086aa  jz      short loc_1800086EC
0x1800086ac  call    cs:__imp_GetLastError
0x1800086b2  lea     rdx, aFailure; "Failure"
0x1800086b9  mov     dword ptr [rsp+288h+hTemplateFile], eax
0x1800086bd  test    esi, esi
0x1800086bf  lea     rcx, aSuccess; "Success"
0x1800086c6  cmovz   rcx, rdx
0x1800086ca  mov     edx, 29h ; ')'
0x1800086cf  mov     qword ptr [rsp+288h+dwFlagsAndAttributes], rcx
0x1800086d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086db  mov     [rsp+288h+dwCreationDisposition], 1E4h
0x1800086e3  mov     rcx, [rcx+10h]
0x1800086e7  call    WPP_SF_sdsd
0x1800086ec  mov     eax, esi
0x1800086ee  mov     rcx, [rsp+288h+var_28]
0x1800086f6  xor     rcx, rsp; StackCookie
0x1800086f9  call    __security_check_cookie
0x1800086fe  lea     r11, [rsp+288h+var_18]
0x180008706  mov     rbx, [r11+28h]
0x18000870a  mov     rsi, [r11+30h]
0x18000870e  mov     rsp, r11
0x180008711  pop     r15
0x180008713  pop     r14
0x180008715  pop     rdi
0x180008716  retn
```
