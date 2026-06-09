# ShowHelp

- ea: `0x18005ac68`
- end: `0x18005ae0e`
- name: `ShowHelp`
- size: `422`
- prototype: `__int64 __fastcall(HWND hWndMain, ULONG_PTR dwData)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005a500`

## callees

- `0x180013870`
- `0x180029560`
- `0x18005ac68`
- `0x18007e6ca`
- `0x18007e700`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x18005ad3e`
- `msvcrt!_wsplitpath_s` at `0x18005ad3e`
- `msvcrt!_wmakepath_s` at `0x18005ad73`
- `msvcrt!_wmakepath_s` at `0x18005ad73`
- `KERNEL32!GetModuleFileNameW` at `0x18005ad05`
- `KERNEL32!GetModuleFileNameW` at `0x18005ad05`
- `USER32!WinHelpW` at `0x18005ad8b`
- `USER32!WinHelpW` at `0x18005ad8b`

## pseudocode

```c
__int64 __fastcall ShowHelp(HWND hWndMain, ULONG_PTR dwData)
{
  unsigned int v2; // esi
  unsigned int v4; // ebx
  wchar_t Drive[2]; // [rsp+54h] [rbp-644h] BYREF
  __int16 v7; // [rsp+58h] [rbp-640h]
  wchar_t Dir[2]; // [rsp+60h] [rbp-638h] BYREF
  _BYTE v9[508]; // [rsp+64h] [rbp-634h] BYREF
  WCHAR Filename[2]; // [rsp+260h] [rbp-438h] BYREF
  _BYTE v11[524]; // [rsp+264h] [rbp-434h] BYREF
  wchar_t Buffer[2]; // [rsp+470h] [rbp-228h] BYREF
  _BYTE v13[524]; // [rsp+474h] [rbp-224h] BYREF

  v2 = dwData;
  v4 = 0;
  *(_DWORD *)Buffer = 0;
  memset_0(v13, 0, 0x204u);
  *(_DWORD *)Filename = 0;
  memset_0(v11, 0, 0x204u);
  *(_DWORD *)Drive = 0;
  v7 = 0;
  *(_DWORD *)Dir = 0;
  memset_0(v9, 0, sizeof(v9));
  GetModuleFileNameW(hModule, Filename, 0x104u);
  _wsplitpath_s(Filename, Drive, 3u, Dir, 0x100u, 0, 0, 0, 0);
  _wmakepath_s(Buffer, 0x104u, Drive, Dir, L"MSDASC", L"HLP");
  if ( !WinHelpW(hWndMain, Buffer, 1u, v2) )
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(0, L"<ShowHelp|OLEDB|ERR> ", 0x15Fu);
    v4 = -2147467259;
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C8408[0], 369673, L"<ShowHelp|Trace|HR> ", v4);
  return v4;
}

```

## disassembly

```asm
0x18005ac68  mov     [rsp+arg_10], rbx
0x18005ac6d  mov     [rsp+arg_18], rsi
0x18005ac72  push    rdi
0x18005ac73  sub     rsp, 690h
0x18005ac7a  mov     rax, cs:__security_cookie
0x18005ac81  xor     rax, rsp
0x18005ac84  mov     [rsp+698h+var_18], rax
0x18005ac8c  mov     esi, edx
0x18005ac8e  mov     rdi, rcx
0x18005ac91  xor     ebx, ebx
0x18005ac93  mov     [rsp+698h+var_648], ebx
0x18005ac97  mov     dword ptr [rsp+698h+Buffer], ebx
0x18005ac9e  xor     edx, edx; Val
0x18005aca0  mov     r8d, 204h; Size
0x18005aca6  lea     rcx, [rsp+698h+var_224]; void *
0x18005acae  call    memset_0
0x18005acb3  mov     dword ptr [rsp+698h+Filename], ebx
0x18005acba  xor     edx, edx; Val
0x18005acbc  mov     r8d, 204h; Size
0x18005acc2  lea     rcx, [rsp+698h+var_434]; void *
0x18005acca  call    memset_0
0x18005accf  mov     dword ptr [rsp+698h+Drive], ebx
0x18005acd3  xor     eax, eax
0x18005acd5  mov     [rsp+698h+var_640], ax
0x18005acda  mov     dword ptr [rsp+698h+Dir], eax
0x18005acde  xor     edx, edx; Val
0x18005ace0  mov     r8d, 1FCh; Size
0x18005ace6  lea     rcx, [rsp+698h+var_634]; void *
0x18005aceb  call    memset_0
0x18005acf0  mov     r8d, 104h; nSize
0x18005acf6  lea     rdx, [rsp+698h+Filename]; lpFilename
0x18005acfe  mov     rcx, cs:hModule; hModule
0x18005ad05  call    cs:__imp_GetModuleFileNameW
0x18005ad0b  mov     [rsp+698h+ExtCount], rbx; ExtCount
0x18005ad10  mov     [rsp+698h+Ext], rbx; Ext
0x18005ad15  mov     [rsp+698h+FilenameCount], rbx; FilenameCount
0x18005ad1a  mov     [rsp+698h+var_670], rbx; Filename
0x18005ad1f  mov     [rsp+698h+DirCount], 100h; DirCount
0x18005ad28  lea     r9, [rsp+698h+Dir]; Dir
0x18005ad2d  lea     r8d, [rbx+3]; DriveCount
0x18005ad31  lea     rdx, [rsp+698h+Drive]; Drive
0x18005ad36  lea     rcx, [rsp+698h+Filename]; FullPath
0x18005ad3e  call    cs:__imp__wsplitpath_s
0x18005ad44  lea     rax, aHlp; "HLP"
0x18005ad4b  mov     [rsp+698h+var_670], rax; Ext
0x18005ad50  lea     rax, aMsdasc; "MSDASC"
0x18005ad57  mov     [rsp+698h+DirCount], rax; Filename
0x18005ad5c  lea     r9, [rsp+698h+Dir]; Dir
0x18005ad61  lea     r8, [rsp+698h+Drive]; Drive
0x18005ad66  mov     edx, 104h; BufferCount
0x18005ad6b  lea     rcx, [rsp+698h+Buffer]; Buffer
0x18005ad73  call    cs:__imp__wmakepath_s
0x18005ad79  mov     r9d, esi; dwData
0x18005ad7c  lea     r8d, [rbx+1]; uCommand
0x18005ad80  lea     rdx, [rsp+698h+Buffer]; lpszHelp
0x18005ad88  mov     rcx, rdi; hWndMain
0x18005ad8b  call    cs:__imp_WinHelpW
0x18005ad91  test    eax, eax
0x18005ad93  jnz     short loc_18005ADBB
0x18005ad95  test    byte ptr cs:_bidGblFlags, 2
0x18005ad9c  jz      short loc_18005ADB2
0x18005ad9e  mov     r8d, 15Fh; unsigned int
0x18005ada4  lea     rdx, aShowhelpOledbE; "<ShowHelp|OLEDB|ERR> "
0x18005adab  xor     ecx, ecx; int
0x18005adad  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005adb2  mov     ebx, 80004005h
0x18005adb7  mov     [rsp+698h+var_648], ebx
0x18005adbb  jmp     short loc_18005ADC1
0x18005adbd  mov     ebx, [rsp+698h+var_648]
0x18005adc1  test    byte ptr cs:_bidGblFlags, 2
0x18005adc8  jz      short loc_18005ADE7
0x18005adca  mov     r9d, ebx
0x18005adcd  lea     r8, aShowhelpTraceH; "<ShowHelp|Trace|HR> "
0x18005add4  mov     edx, 5A409h
0x18005add9  mov     rcx, cs:off_1800C8408; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005ade0  call    _bidTraceHR
0x18005ade5  mov     ebx, eax
0x18005ade7  mov     eax, ebx
0x18005ade9  mov     rcx, [rsp+698h+var_18]
0x18005adf1  xor     rcx, rsp; StackCookie
0x18005adf4  call    __security_check_cookie
0x18005adf9  lea     r11, [rsp+698h+var_8]
0x18005ae01  mov     rbx, [r11+20h]
0x18005ae05  mov     rsi, [r11+28h]
0x18005ae09  mov     rsp, r11
0x18005ae0c  pop     rdi
0x18005ae0d  retn
```
