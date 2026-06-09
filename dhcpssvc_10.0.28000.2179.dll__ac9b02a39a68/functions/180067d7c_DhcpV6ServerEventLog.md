# DhcpV6ServerEventLog

- ea: `0x180067d7c`
- end: `0x180067f6a`
- name: `DhcpV6ServerEventLog`
- size: `494`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800029d8`
- `0x180012ac0`
- `0x180025144`

## callees

- `0x18000282c`
- `0x180067d7c`
- `0x18008f1c0`
- `0x1800cdac0`

## import_xrefs

- `msvcrt!_ultoa` at `0x180067e0c`
- `msvcrt!_ultoa` at `0x180067e0c`
- `KERNEL32!FreeLibrary` at `0x180067e85`
- `KERNEL32!FreeLibrary` at `0x180067e85`
- `KERNEL32!LocalFree` at `0x180067ee3`
- `KERNEL32!LocalFree` at `0x180067ee3`
- `KERNEL32!LoadLibraryExW` at `0x180067e3a`
- `KERNEL32!LoadLibraryExW` at `0x180067e3a`
- `KERNEL32!FormatMessageW` at `0x180067e74`
- `KERNEL32!FormatMessageW` at `0x180067e74`

## string_xrefs

- `0x180067e31`: `dhcpssvc.dll`

## pseudocode

```c
_UNKNOWN **__fastcall DhcpV6ServerEventLog(__int64 a1, unsigned int a2, DWORD a3)
{
  unsigned int v5; // esi
  __int64 v6; // r8
  char *v7; // rdx
  char v8; // al
  char *v9; // rax
  __int64 v10; // rcx
  HMODULE Library; // rdi
  DWORD v12; // ebx
  unsigned int v13; // ebx
  _UNKNOWN **result; // rax
  DWORD dwMessageId; // [rsp+40h] [rbp-19h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-11h] BYREF
  WCHAR lpBuffer[4]; // [rsp+50h] [rbp-9h] BYREF
  char v18[2]; // [rsp+58h] [rbp-1h] BYREF
  char Buffer[38]; // [rsp+5Ah] [rbp+1h] BYREF

  dwMessageId = a3;
  hMem = 0;
  v5 = a1;
  if ( a3 )
  {
    v6 = 33;
    v7 = v18;
    do
    {
      if ( v6 == -2147483613 )
        break;
      v8 = v7["%%" - v18];
      if ( !v8 )
        break;
      *v7++ = v8;
      --v6;
    }
    while ( v6 );
    v9 = v7 - 1;
    if ( v6 )
      v9 = v7;
    *v9 = 0;
    _ultoa(a3, Buffer, 10);
    *(_QWORD *)lpBuffer = 0;
    if ( dwMessageId - 10000 > 0x18
      || (Library = LoadLibraryExW(L"dhcpssvc.dll", 0, 0),
          v12 = FormatMessageW(0xB00u, Library, dwMessageId, 0x400u, lpBuffer, 0, 0),
          FreeLibrary(Library),
          !v12)
      || (hMem = *(HLOCAL *)lpBuffer) == 0 )
    {
      hMem = v18;
    }
    v13 = DhcpReportEventA(v10, v5, a2, 1, 4, &hMem, &dwMessageId);
    result = (_UNKNOWN **)v18;
    if ( hMem != v18 )
      result = (_UNKNOWN **)LocalFree(hMem);
  }
  else
  {
    result = (_UNKNOWN **)DhcpReportEventA(a1, (unsigned int)a1, a2, 0, 0, 0, 0);
    v13 = (unsigned int)result;
  }
  if ( v13 )
  {
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      return (_UNKNOWN **)WPP_SF_D(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            17,
                            &WPP_3a03f93c2ffe32d69ed1170ace27464b_Traceguids,
                            v13);
  }
  return result;
}

```

## disassembly

```asm
0x180067d7c  push    rbp
0x180067d7e  push    rbx
0x180067d7f  push    rsi
0x180067d80  push    rdi
0x180067d81  push    r14
0x180067d83  lea     rbp, [rsp-37h]
0x180067d88  sub     rsp, 90h
0x180067d8f  mov     rax, cs:__security_cookie
0x180067d96  xor     rax, rsp
0x180067d99  mov     [rbp+57h+var_30], rax
0x180067d9d  mov     [rbp+57h+dwMessageId], r8d
0x180067da1  mov     r10d, r8d
0x180067da4  mov     [rbp+57h+hMem], 0
0x180067dac  mov     r14d, edx
0x180067daf  mov     esi, ecx
0x180067db1  test    r8d, r8d
0x180067db4  jz      loc_180067EF1
0x180067dba  lea     r9, asc_1800E6910; "%%"
0x180067dc1  mov     r8d, 21h ; '!'
0x180067dc7  lea     rax, [rbp+57h+var_58]
0x180067dcb  sub     r9, rax
0x180067dce  lea     rdx, [rbp+57h+var_58]
0x180067dd2  lea     rax, [r8+7FFFFFDDh]
0x180067dd9  test    rax, rax
0x180067ddc  jz      short loc_180067DF1
0x180067dde  mov     al, [rdx+r9]
0x180067de2  test    al, al
0x180067de4  jz      short loc_180067DF1
0x180067de6  mov     [rdx], al
0x180067de8  inc     rdx
0x180067deb  sub     r8, 1
0x180067def  jnz     short loc_180067DD2
0x180067df1  test    r8, r8
0x180067df4  lea     rax, [rdx-1]
0x180067df8  mov     r8d, 0Ah; Radix
0x180067dfe  mov     ecx, r10d; Value
0x180067e01  cmovnz  rax, rdx
0x180067e05  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180067e09  mov     byte ptr [rax], 0
0x180067e0c  call    cs:__imp__ultoa
0x180067e13  nop     dword ptr [rax+rax+00h]
0x180067e18  mov     ebx, [rbp+57h+dwMessageId]
0x180067e1b  mov     qword ptr [rbp+57h+var_60], 0
0x180067e23  lea     eax, [rbx-2710h]
0x180067e29  cmp     eax, 18h
0x180067e2c  ja      short loc_180067EA2
0x180067e2e  xor     r8d, r8d; dwFlags
0x180067e31  lea     rcx, LibFileName; "dhcpssvc.dll"
0x180067e38  xor     edx, edx; hFile
0x180067e3a  call    cs:__imp_LoadLibraryExW
0x180067e41  nop     dword ptr [rax+rax+00h]
0x180067e46  mov     [rsp+0B0h+Arguments], 0; Arguments
0x180067e4f  mov     r9d, 400h; dwLanguageId
0x180067e55  mov     rdi, rax
0x180067e58  mov     [rsp+0B0h+nSize], 0; nSize
0x180067e60  lea     rax, [rbp+57h+var_60]
0x180067e64  mov     rdx, rdi; lpSource
0x180067e67  mov     r8d, ebx; dwMessageId
0x180067e6a  mov     [rsp+0B0h+lpBuffer], rax; lpBuffer
0x180067e6f  mov     ecx, 0B00h; dwFlags
0x180067e74  call    cs:__imp_FormatMessageW
0x180067e7b  nop     dword ptr [rax+rax+00h]
0x180067e80  mov     rcx, rdi; hLibModule
0x180067e83  mov     ebx, eax
0x180067e85  call    cs:__imp_FreeLibrary
0x180067e8c  nop     dword ptr [rax+rax+00h]
0x180067e91  test    ebx, ebx
0x180067e93  jz      short loc_180067EA2
0x180067e95  mov     rax, qword ptr [rbp+57h+var_60]
0x180067e99  mov     [rbp+57h+hMem], rax
0x180067e9d  test    rax, rax
0x180067ea0  jnz     short loc_180067EAA
0x180067ea2  lea     rax, [rbp+57h+var_58]
0x180067ea6  mov     [rbp+57h+hMem], rax
0x180067eaa  lea     rax, [rbp+57h+dwMessageId]
0x180067eae  mov     r9d, 1
0x180067eb4  mov     [rsp+0B0h+Arguments], rax
0x180067eb9  mov     r8d, r14d
0x180067ebc  lea     rax, [rbp+57h+hMem]
0x180067ec0  mov     edx, esi
0x180067ec2  mov     qword ptr [rsp+0B0h+nSize], rax
0x180067ec7  mov     dword ptr [rsp+0B0h+lpBuffer], 4
0x180067ecf  call    DhcpReportEventA
0x180067ed4  mov     rcx, [rbp+57h+hMem]; hMem
0x180067ed8  mov     ebx, eax
0x180067eda  lea     rax, [rbp+57h+var_58]
0x180067ede  cmp     rcx, rax
0x180067ee1  jz      short loc_180067F1A
0x180067ee3  call    cs:__imp_LocalFree
0x180067eea  nop     dword ptr [rax+rax+00h]
0x180067eef  jmp     short loc_180067F1A
0x180067ef1  mov     [rsp+0B0h+Arguments], 0
0x180067efa  xor     r9d, r9d
0x180067efd  mov     qword ptr [rsp+0B0h+nSize], 0
0x180067f06  mov     r8d, r14d
0x180067f09  mov     edx, esi
0x180067f0b  mov     dword ptr [rsp+0B0h+lpBuffer], 0
0x180067f13  call    DhcpReportEventA
0x180067f18  mov     ebx, eax
0x180067f1a  test    ebx, ebx
0x180067f1c  jz      short loc_180067F4F
0x180067f1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180067f25  lea     rax, WPP_GLOBAL_Control
0x180067f2c  cmp     rcx, rax
0x180067f2f  jz      short loc_180067F4F
0x180067f31  test    byte ptr [rcx+1Ch], 10h
0x180067f35  jz      short loc_180067F4F
0x180067f37  mov     rcx, [rcx+10h]
0x180067f3b  lea     r8, WPP_3a03f93c2ffe32d69ed1170ace27464b_Traceguids
0x180067f42  mov     edx, 11h
0x180067f47  mov     r9d, ebx
0x180067f4a  call    WPP_SF_D
0x180067f4f  mov     rcx, [rbp+57h+var_30]
0x180067f53  xor     rcx, rsp; StackCookie
0x180067f56  call    __security_check_cookie
0x180067f5b  add     rsp, 90h
0x180067f62  pop     r14
0x180067f64  pop     rdi
0x180067f65  pop     rsi
0x180067f66  pop     rbx
0x180067f67  pop     rbp
0x180067f68  retn
```
