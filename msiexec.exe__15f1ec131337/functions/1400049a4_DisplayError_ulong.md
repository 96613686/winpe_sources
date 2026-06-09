# DisplayError(ulong)

- ea: `0x1400049a4`
- end: `0x140004c9f`
- name: `?DisplayError@@YAXK@Z`
- size: `763`
- prototype: `void __fastcall(DWORD dwMessageId)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400011e4`

## callees

- `0x1400033a8`
- `0x140003883`
- `0x1400049a4`
- `0x14000810c`
- `0x1400088c0`
- `0x140009820`
- `0x14000a010`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x140004c24`
- `KERNEL32!lstrlenW` at `0x140004c24`
- `KERNEL32!WriteFile` at `0x140004c4a`
- `KERNEL32!WriteFile` at `0x140004c72`
- `KERNEL32!WriteFile` at `0x140004c4a`
- `KERNEL32!WriteFile` at `0x140004c72`
- `KERNEL32!GetLocaleInfoW` at `0x140004a6b`
- `KERNEL32!GetLocaleInfoW` at `0x140004a6b`
- `KERNEL32!GetVersionExW` at `0x140004b52`
- `KERNEL32!GetVersionExW` at `0x140004b52`
- `KERNEL32!GetACP` at `0x140004a1d`
- `KERNEL32!GetACP` at `0x140004a1d`
- `KERNEL32!FormatMessageW` at `0x140004aac`
- `KERNEL32!FormatMessageW` at `0x140004aac`
- `KERNEL32!GlobalFree` at `0x140004c03`
- `KERNEL32!GlobalFree` at `0x140004c03`
- `KERNEL32!LoadLibraryW` at `0x140004a2c`
- `KERNEL32!LoadLibraryW` at `0x140004a2c`
- `KERNEL32!GetProcAddress` at `0x140004a44`
- `KERNEL32!GetProcAddress` at `0x140004a44`
- `KERNEL32!FreeLibrary` at `0x140004a7b`
- `KERNEL32!FreeLibrary` at `0x140004a7b`
- `msi!__imp_MsiLoadStringW` at `0x140004a0a`
- `msi!__imp_MsiLoadStringW` at `0x140004b8e`
- `msi!__imp_MsiLoadStringW` at `0x140004a0a`
- `msi!__imp_MsiLoadStringW` at `0x140004b8e`
- `msi!__imp_MsiMessageBoxW` at `0x140004bf2`
- `msi!__imp_MsiMessageBoxW` at `0x140004bf2`

## string_xrefs

- `0x140004adc`: `Install error %i`

## pseudocode

```c
void __fastcall DisplayError(DWORD dwMessageId)
{
  UINT ACP; // edi
  LCID v3; // r14d
  HMODULE LibraryW; // rax
  HMODULE v5; // rsi
  unsigned __int16 (*ProcAddress)(void); // rax
  DWORD v7; // eax
  int v8; // eax
  int lpBuffer; // [rsp+20h] [rbp-E0h]
  DWORD nSize; // [rsp+28h] [rbp-D8h]
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR LCData[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v13; // [rsp+60h] [rbp-A0h]
  char v14; // [rsp+68h] [rbp-98h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[1032]; // [rsp+190h] [rbp+90h] BYREF

  memset_0(Buffer, 0, 0x802u);
  if ( dwMessageId < 0x641 || (ACP = MsiLoadStringW(-1, dwMessageId, Buffer, 1025, 0)) == 0 )
  {
    LOWORD(v3) = 0;
    ACP = GetACP();
    LibraryW = LoadLibraryW(L"KERNEL32");
    v5 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = (unsigned __int16 (*)(void))GetProcAddress(LibraryW, "GetUserDefaultUILanguage");
      if ( ProcAddress )
      {
        v3 = ProcAddress();
        if ( GetLocaleInfoW(v3, 0x20001004u, LCData, 10) )
          ACP = *(_DWORD *)LCData;
      }
      FreeLibrary(v5);
    }
    v7 = FormatMessageW(0x1000u, 0, dwMessageId, (unsigned __int16)v3, Buffer, 0x401u, 0);
    if ( v7 )
    {
      if ( 2 * (unsigned __int64)(v7 - 2) >= 0x802 )
        _report_rangecheckfailure();
      Buffer[v7 - 2] = 0;
    }
    else if ( (int)StringCchPrintfW(Buffer, 0x401u, L"Install error %i", dwMessageId) < 0 )
    {
      return;
    }
  }
  if ( g_fQuiet || (((unsigned __int64)g_hStdOut + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    if ( (char *)g_hStdOut - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      NumberOfBytesWritten = 0;
      v8 = lstrlenW(Buffer);
      WriteFile(g_hStdOut, Buffer, 2 * v8, &NumberOfBytesWritten, 0);
      WriteFile(g_hStdOut, L"\n\r", 4u, &NumberOfBytesWritten, 0);
    }
  }
  else
  {
    v13 = 1;
    *(_QWORD *)LCData = &v14;
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( !GetVersionExW(&VersionInformation)
      || VersionInformation.dwMajorVersion < 6
      || !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(LCData, 256)
      || (LOWORD(lpBuffer) = 0, !(unsigned int)MsiLoadStringW(-1, 28, *(_QWORD *)LCData, (unsigned int)v13, lpBuffer))
      || (int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, WCHAR *, _QWORD, int, __int64, _QWORD))COMCTL32::TaskDialog)(
                0,
                0,
                *(_QWORD *)LCData,
                Buffer,
                0,
                1,
                65534,
                0) < 0 )
    {
      LOWORD(nSize) = 0;
      MsiMessageBoxW(0, Buffer, 0, 16, ACP, nSize);
    }
    if ( v13 > 1 )
      GlobalFree(*(HGLOBAL *)LCData);
  }
}

```

## disassembly

```asm
0x1400049a4  mov     [rsp-8+arg_8], rbx
0x1400049a9  mov     [rsp-8+arg_10], rsi
0x1400049ae  push    rbp
0x1400049af  push    rdi
0x1400049b0  push    r14
0x1400049b2  lea     rbp, [rsp-8B0h]
0x1400049ba  sub     rsp, 9B0h
0x1400049c1  mov     rax, cs:__security_cookie
0x1400049c8  xor     rax, rsp
0x1400049cb  mov     [rbp+8C0h+var_20], rax
0x1400049d2  mov     ebx, ecx
0x1400049d4  xor     edx, edx; Val
0x1400049d6  lea     rcx, [rbp+8C0h+Buffer]; void *
0x1400049dd  mov     r8d, 802h; Size
0x1400049e3  call    memset_0
0x1400049e8  cmp     ebx, 641h
0x1400049ee  jb      short loc_140004A1A
0x1400049f0  xor     eax, eax
0x1400049f2  lea     r8, [rbp+8C0h+Buffer]
0x1400049f9  mov     r9d, 401h
0x1400049ff  mov     word ptr [rsp+9C0h+lpBuffer], ax
0x140004a04  mov     edx, ebx
0x140004a06  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140004a0a  call    cs:__imp_MsiLoadStringW
0x140004a10  mov     edi, eax
0x140004a12  test    eax, eax
0x140004a14  jnz     loc_140004AFC
0x140004a1a  xor     r14d, r14d
0x140004a1d  call    cs:__imp_GetACP
0x140004a23  lea     rcx, aKernel32; "KERNEL32"
0x140004a2a  mov     edi, eax
0x140004a2c  call    cs:__imp_LoadLibraryW
0x140004a32  mov     rsi, rax
0x140004a35  test    rax, rax
0x140004a38  jz      short loc_140004A81
0x140004a3a  lea     rdx, aGetuserdefault; "GetUserDefaultUILanguage"
0x140004a41  mov     rcx, rax; hModule
0x140004a44  call    cs:__imp_GetProcAddress
0x140004a4a  test    rax, rax
0x140004a4d  jz      short loc_140004A78
0x140004a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a54  movzx   ecx, ax; Locale
0x140004a57  lea     r8, [rsp+9C0h+LCData]; lpLCData
0x140004a5c  mov     r9d, 0Ah; cchData
0x140004a62  mov     edx, 20001004h; LCType
0x140004a67  movzx   r14d, ax
0x140004a6b  call    cs:__imp_GetLocaleInfoW
0x140004a71  test    eax, eax
0x140004a73  cmovnz  edi, dword ptr [rsp+9C0h+LCData]
0x140004a78  mov     rcx, rsi; hLibModule
0x140004a7b  call    cs:__imp_FreeLibrary
0x140004a81  mov     [rsp+9C0h+Arguments], 0; Arguments
0x140004a8a  lea     rax, [rbp+8C0h+Buffer]
0x140004a91  mov     [rsp+9C0h+nSize], 401h; nSize
0x140004a99  mov     r8d, ebx; dwMessageId
0x140004a9c  movzx   r9d, r14w; dwLanguageId
0x140004aa0  xor     edx, edx; lpSource
0x140004aa2  mov     ecx, 1000h; dwFlags
0x140004aa7  mov     [rsp+9C0h+lpBuffer], rax; lpBuffer
0x140004aac  call    cs:__imp_FormatMessageW
0x140004ab2  test    eax, eax
0x140004ab4  jz      short loc_140004AD9
0x140004ab6  add     eax, 0FFFFFFFEh
0x140004ab9  mov     ecx, eax
0x140004abb  add     rcx, rcx
0x140004abe  cmp     rcx, 802h
0x140004ac5  jnb     short loc_140004AD3
0x140004ac7  xor     eax, eax
0x140004ac9  mov     [rbp+rcx+8C0h+Buffer], ax
0x140004ad1  jmp     short loc_140004AFC
0x140004ad3  call    __report_rangecheckfailure
0x140004ad9  mov     r9d, ebx
0x140004adc  lea     r8, aInstallErrorI; "Install error %i"
0x140004ae3  mov     edx, 401h; unsigned __int64
0x140004ae8  lea     rcx, [rbp+8C0h+Buffer]; unsigned __int16 *
0x140004aef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004af4  test    eax, eax
0x140004af6  js      loc_140004C78
0x140004afc  cmp     cs:?g_fQuiet@@3W4Bool@@A, 0; Bool g_fQuiet
0x140004b03  mov     rcx, cs:?g_hStdOut@@3PEAXEA; void * g_hStdOut
0x140004b0a  jnz     loc_140004C0B
0x140004b10  lea     rax, [rcx+1]
0x140004b14  test    rax, 0FFFFFFFFFFFFFFFEh
0x140004b1a  jnz     loc_140004C0B
0x140004b20  lea     rax, [rsp+9C0h+var_958]
0x140004b25  mov     ebx, 1
0x140004b2a  xor     edx, edx; Val
0x140004b2c  mov     [rsp+9C0h+var_960], ebx
0x140004b30  mov     r8d, 118h; Size
0x140004b36  mov     qword ptr [rsp+9C0h+LCData], rax
0x140004b3b  lea     rcx, [rsp+9C0h+VersionInformation.dwMajorVersion]; void *
0x140004b40  call    memset_0
0x140004b45  lea     rcx, [rsp+9C0h+VersionInformation]; lpVersionInformation
0x140004b4a  mov     [rsp+9C0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140004b52  call    cs:__imp_GetVersionExW
0x140004b58  test    eax, eax
0x140004b5a  jz      short loc_140004BD7
0x140004b5c  cmp     [rsp+9C0h+VersionInformation.dwMajorVersion], 6
0x140004b61  jb      short loc_140004BD7
0x140004b63  mov     edx, 100h
0x140004b68  lea     rcx, [rsp+9C0h+LCData]
0x140004b6d  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x140004b72  test    al, al
0x140004b74  jz      short loc_140004BD7
0x140004b76  mov     r9d, [rsp+9C0h+var_960]
0x140004b7b  lea     edx, [rbx+1Bh]
0x140004b7e  mov     r8, qword ptr [rsp+9C0h+LCData]
0x140004b83  xor     eax, eax
0x140004b85  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140004b89  mov     word ptr [rsp+9C0h+lpBuffer], ax
0x140004b8e  call    cs:__imp_MsiLoadStringW
0x140004b94  test    eax, eax
0x140004b96  jz      short loc_140004BD7
0x140004b98  mov     r8, qword ptr [rsp+9C0h+LCData]
0x140004b9d  lea     r9, [rbp+8C0h+Buffer]
0x140004ba4  mov     rax, cs:?TaskDialog@COMCTL32@@3P6AJPEAUHWND__@@PEAUHINSTANCE__@@PEBG22K2PEAH@ZEA; long (*COMCTL32::TaskDialog)(HWND__ *,HINSTANCE__ *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,int *)
0x140004bab  xor     edx, edx
0x140004bad  mov     [rsp+9C0h+var_988], 0
0x140004bb6  xor     ecx, ecx
0x140004bb8  mov     [rsp+9C0h+Arguments], 0FFFEh
0x140004bc1  mov     [rsp+9C0h+nSize], ebx
0x140004bc5  mov     [rsp+9C0h+lpBuffer], 0
0x140004bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004bd3  test    eax, eax
0x140004bd5  jns     short loc_140004BF8
0x140004bd7  xor     eax, eax
0x140004bd9  lea     rdx, [rbp+8C0h+Buffer]
0x140004be0  mov     word ptr [rsp+9C0h+nSize], ax
0x140004be5  xor     r8d, r8d
0x140004be8  xor     ecx, ecx
0x140004bea  mov     dword ptr [rsp+9C0h+lpBuffer], edi
0x140004bee  lea     r9d, [rax+10h]
0x140004bf2  call    cs:__imp_MsiMessageBoxW
0x140004bf8  cmp     [rsp+9C0h+var_960], ebx
0x140004bfc  jle     short loc_140004C78
0x140004bfe  mov     rcx, qword ptr [rsp+9C0h+LCData]; hMem
0x140004c03  call    cs:__imp_GlobalFree
0x140004c09  jmp     short loc_140004C78
0x140004c0b  lea     rax, [rcx-1]
0x140004c0f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140004c13  ja      short loc_140004C78
0x140004c15  lea     rcx, [rbp+8C0h+Buffer]; lpString
0x140004c1c  mov     [rsp+9C0h+NumberOfBytesWritten], 0
0x140004c24  call    cs:__imp_lstrlenW
0x140004c2a  mov     rcx, cs:?g_hStdOut@@3PEAXEA; hFile
0x140004c31  lea     r9, [rsp+9C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140004c36  lea     rdx, [rbp+8C0h+Buffer]; lpBuffer
0x140004c3d  mov     [rsp+9C0h+lpBuffer], 0; lpOverlapped
0x140004c46  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x140004c4a  call    cs:__imp_WriteFile
0x140004c50  mov     rcx, cs:?g_hStdOut@@3PEAXEA; hFile
0x140004c57  lea     r9, [rsp+9C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140004c5c  mov     r8d, 4; nNumberOfBytesToWrite
0x140004c62  mov     [rsp+9C0h+lpBuffer], 0; lpOverlapped
0x140004c6b  lea     rdx, asc_14000CC90; "\n\r"
0x140004c72  call    cs:__imp_WriteFile
0x140004c78  mov     rcx, [rbp+8C0h+var_20]
0x140004c7f  xor     rcx, rsp; StackCookie
0x140004c82  call    __security_check_cookie
0x140004c87  lea     r11, [rsp+9C0h+var_10]
0x140004c8f  mov     rbx, [r11+28h]
0x140004c93  mov     rsi, [r11+30h]
0x140004c97  mov     rsp, r11
0x140004c9a  pop     r14
0x140004c9c  pop     rdi
0x140004c9d  pop     rbp
0x140004c9e  retn
```
