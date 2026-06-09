# ConfigParser::SetOutputFile(ushort const *,ushort const *)

- ea: `0x1802237a0`
- end: `0x1802239eb`
- name: `?SetOutputFile@ConfigParser@@SAJPEBG0@Z`
- size: `587`
- prototype: `__int64 __fastcall(wchar_t *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18021c350`

## callees

- `0x1801ad6e8`
- `0x1802237a0`
- `0x1803481f0`

## import_xrefs

- `msvcrt!_wfsopen` at `0x180223986`
- `msvcrt!_wfsopen` at `0x180223986`
- `msvcrt!_wsplitpath_s` at `0x1802238eb`
- `msvcrt!_wsplitpath_s` at `0x1802238eb`
- `msvcrt!wcsstr` at `0x1802237eb`
- `msvcrt!wcsstr` at `0x1802237eb`
- `msvcrt!_wcsicmp` at `0x180223903`
- `msvcrt!_wcsicmp` at `0x180223903`
- `msvcrt!wcscat_s` at `0x18022394e`
- `msvcrt!wcscat_s` at `0x180223965`
- `msvcrt!wcscat_s` at `0x18022394e`
- `msvcrt!wcscat_s` at `0x180223965`
- `msvcrt!_ultow_s` at `0x180223857`
- `msvcrt!_ultow_s` at `0x180223857`
- `msvcrt!wcscpy_s` at `0x180223893`
- `msvcrt!wcscpy_s` at `0x180223893`
- `msvcrt!wcsncpy_s` at `0x180223822`
- `msvcrt!wcsncpy_s` at `0x180223822`
- `KERNEL32!GetEnvironmentVariableW` at `0x18022392f`
- `KERNEL32!GetEnvironmentVariableW` at `0x18022392f`
- `KERNEL32!GetModuleFileNameW` at `0x1802238b2`
- `KERNEL32!GetModuleFileNameW` at `0x1802238b2`
- `KERNEL32!GetCurrentProcessId` at `0x18022383f`
- `KERNEL32!GetCurrentProcessId` at `0x18022383f`

## pseudocode

```c
__int64 __fastcall ConfigParser::SetOutputFile(wchar_t *a1, const unsigned __int16 *a2)
{
  wchar_t *v2; // rdi
  wchar_t *v3; // rax
  rsize_t v4; // rsi
  wchar_t *v5; // r14
  DWORD CurrentProcessId; // eax
  __int64 v7; // rax
  __int64 v8; // rcx
  wchar_t *v9; // rcx
  const wchar_t *v10; // rbx
  FILE *v11; // rbx
  wchar_t String1[264]; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t Destination[264]; // [rsp+268h] [rbp+160h] BYREF
  WCHAR Filename[264]; // [rsp+478h] [rbp+370h] BYREF

  v2 = a1;
  v3 = wcsstr(a1, L"{PID}");
  if ( v3 )
  {
    v4 = v3 - v2;
    wcsncpy_s(Destination, 0x104u, v2, v4);
    v5 = &Destination[v4];
    CurrentProcessId = GetCurrentProcessId();
    _ultow_s(CurrentProcessId, v5, 260 - v4, 10);
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( v5[v8] );
    v9 = &v5[v8];
    do
      ++v7;
    while ( v9[v7] );
    wcscpy_s(v9, 260 - v4 - v7, &v2[v4 + 5]);
    v2 = Destination;
  }
  GetModuleFileNameW(0, Filename, 0x104u);
  _wsplitpath_s(Filename, 0, 0, 0, 0, String1, 0x104u, 0, 0);
  if ( !_wcsicmp(String1, L"WWAHost") )
  {
    v10 = v2 + 2;
    if ( v2[1] != 58 )
      v10 = v2;
    if ( GetEnvironmentVariableW(L"temp", String1, 0x104u) )
    {
      wcscat_s(String1, 0x104u, L"\\");
      wcscat_s(String1, 0x104u, v10);
    }
    v2 = String1;
  }
  v11 = _wfsopen(v2, L"wt", 32);
  if ( !v11 )
    return 2147500037LL;
  if ( !Output::s_outputFile )
  {
    AutoFILE::Close((AutoFILE *)&Output::s_outputFile);
    Output::s_outputFile = v11;
  }
  return 0;
}

```

## disassembly

```asm
0x1802237a0  mov     rax, rsp
0x1802237a3  mov     [rax+18h], rbx
0x1802237a7  mov     [rax+20h], rsi
0x1802237ab  mov     [rax+10h], rdx
0x1802237af  mov     [rax+8], rcx
0x1802237b3  push    rbp
0x1802237b4  push    rdi
0x1802237b5  push    r12
0x1802237b7  push    r14
0x1802237b9  push    r15
0x1802237bb  lea     rbp, [rax-5B8h]
0x1802237c2  sub     rsp, 690h
0x1802237c9  mov     rax, cs:__security_cookie
0x1802237d0  xor     rax, rsp
0x1802237d3  mov     [rbp+5B0h+var_30], rax
0x1802237da  mov     rdi, [rbp+5B0h+Str]
0x1802237e1  lea     rdx, aPid; "{PID}"
0x1802237e8  mov     rcx, rdi; Str
0x1802237eb  call    cs:__imp_wcsstr
0x1802237f2  nop     dword ptr [rax+rax+00h]
0x1802237f7  xor     r15d, r15d
0x1802237fa  mov     r12d, 104h
0x180223800  mov     rsi, rax
0x180223803  test    rax, rax
0x180223806  jz      loc_1802238A6
0x18022380c  sub     rsi, rdi
0x18022380f  lea     rcx, [rbp+5B0h+Destination]; Destination
0x180223816  sar     rsi, 1
0x180223819  mov     r8, rdi; Source
0x18022381c  mov     r9, rsi; MaxCount
0x18022381f  mov     edx, r12d; SizeInWords
0x180223822  call    cs:__imp_wcsncpy_s
0x180223829  nop     dword ptr [rax+rax+00h]
0x18022382e  lea     r14, [rbp+5B0h+Destination]
0x180223835  mov     ebx, r12d
0x180223838  lea     r14, [r14+rsi*2]
0x18022383c  sub     rbx, rsi
0x18022383f  call    cs:__imp_GetCurrentProcessId
0x180223846  nop     dword ptr [rax+rax+00h]
0x18022384b  lea     r9d, [r15+0Ah]; Radix
0x18022384f  mov     r8, rbx; BufferCount
0x180223852  mov     ecx, eax; Value
0x180223854  mov     rdx, r14; Buffer
0x180223857  call    cs:__imp__ultow_s
0x18022385e  nop     dword ptr [rax+rax+00h]
0x180223863  or      rax, 0FFFFFFFFFFFFFFFFh
0x180223867  mov     rcx, rax
0x18022386a  inc     rcx
0x18022386d  cmp     [r14+rcx*2], r15w
0x180223872  jnz     short loc_18022386A
0x180223874  lea     rcx, [r14+rcx*2]; Destination
0x180223878  inc     rax
0x18022387b  cmp     [rcx+rax*2], r15w
0x180223880  jnz     short loc_180223878
0x180223882  mov     rdx, r12
0x180223885  lea     r8, [rdi+0Ah]
0x180223889  sub     rdx, rsi
0x18022388c  lea     r8, [r8+rsi*2]; Source
0x180223890  sub     rdx, rax; SizeInWords
0x180223893  call    cs:__imp_wcscpy_s
0x18022389a  nop     dword ptr [rax+rax+00h]
0x18022389f  lea     rdi, [rbp+5B0h+Destination]
0x1802238a6  mov     r8d, r12d; nSize
0x1802238a9  lea     rdx, [rbp+5B0h+Filename]; lpFilename
0x1802238b0  xor     ecx, ecx; hModule
0x1802238b2  call    cs:__imp_GetModuleFileNameW
0x1802238b9  nop     dword ptr [rax+rax+00h]
0x1802238be  mov     [rsp+6B0h+ExtCount], r15; ExtCount
0x1802238c3  lea     rax, [rsp+6B0h+String1]
0x1802238c8  mov     [rsp+6B0h+Ext], r15; Ext
0x1802238cd  lea     rcx, [rbp+5B0h+Filename]; FullPath
0x1802238d4  mov     [rsp+6B0h+FilenameCount], r12; FilenameCount
0x1802238d9  xor     r9d, r9d; Dir
0x1802238dc  mov     [rsp+6B0h+var_688], rax; Filename
0x1802238e1  xor     r8d, r8d; DriveCount
0x1802238e4  xor     edx, edx; Drive
0x1802238e6  mov     [rsp+6B0h+DirCount], r15; DirCount
0x1802238eb  call    cs:__imp__wsplitpath_s
0x1802238f2  nop     dword ptr [rax+rax+00h]
0x1802238f7  lea     rdx, aWwahost; "WWAHost"
0x1802238fe  lea     rcx, [rsp+6B0h+String1]; String1
0x180223903  call    cs:__imp__wcsicmp
0x18022390a  nop     dword ptr [rax+rax+00h]
0x18022390f  test    eax, eax
0x180223911  jnz     short loc_180223976
0x180223913  cmp     word ptr [rdi+2], 3Ah ; ':'
0x180223918  lea     rbx, [rdi+4]
0x18022391c  mov     r8d, r12d; nSize
0x18022391f  lea     rdx, [rsp+6B0h+String1]; lpBuffer
0x180223924  lea     rcx, aTemp; "temp"
0x18022392b  cmovnz  rbx, rdi
0x18022392f  call    cs:__imp_GetEnvironmentVariableW
0x180223936  nop     dword ptr [rax+rax+00h]
0x18022393b  test    eax, eax
0x18022393d  jz      short loc_180223971
0x18022393f  lea     r8, SubBlock; "\\"
0x180223946  mov     rdx, r12; SizeInWords
0x180223949  lea     rcx, [rsp+6B0h+String1]; Destination
0x18022394e  call    cs:__imp_wcscat_s
0x180223955  nop     dword ptr [rax+rax+00h]
0x18022395a  mov     r8, rbx; Source
0x18022395d  lea     rcx, [rsp+6B0h+String1]; Destination
0x180223962  mov     rdx, r12; SizeInWords
0x180223965  call    cs:__imp_wcscat_s
0x18022396c  nop     dword ptr [rax+rax+00h]
0x180223971  lea     rdi, [rsp+6B0h+String1]
0x180223976  mov     r8d, 20h ; ' '; ShFlag
0x18022397c  lea     rdx, aWt; "wt"
0x180223983  mov     rcx, rdi; FileName
0x180223986  call    cs:__imp__wfsopen
0x18022398d  nop     dword ptr [rax+rax+00h]
0x180223992  mov     rbx, rax
0x180223995  test    rax, rax
0x180223998  jz      short loc_1802239BA
0x18022399a  cmp     cs:?s_outputFile@Output@@0VAutoFILE@@A, r15; AutoFILE Output::s_outputFile
0x1802239a1  jnz     short loc_1802239B6
0x1802239a3  lea     rcx, ?s_outputFile@Output@@0VAutoFILE@@A; this
0x1802239aa  call    ?Close@AutoFILE@@QEAAXXZ; AutoFILE::Close(void)
0x1802239af  mov     cs:?s_outputFile@Output@@0VAutoFILE@@A, rbx; AutoFILE Output::s_outputFile
0x1802239b6  xor     eax, eax
0x1802239b8  jmp     short loc_1802239BF
0x1802239ba  mov     eax, 80004005h
0x1802239bf  mov     rcx, [rbp+5B0h+var_30]
0x1802239c6  xor     rcx, rsp; StackCookie
0x1802239c9  call    __security_check_cookie
0x1802239ce  lea     r11, [rsp+6B0h+var_20]
0x1802239d6  mov     rbx, [r11+40h]
0x1802239da  mov     rsi, [r11+48h]
0x1802239de  mov     rsp, r11
0x1802239e1  pop     r15
0x1802239e3  pop     r14
0x1802239e5  pop     r12
0x1802239e7  pop     rdi
0x1802239e8  pop     rbp
0x1802239e9  retn
```
