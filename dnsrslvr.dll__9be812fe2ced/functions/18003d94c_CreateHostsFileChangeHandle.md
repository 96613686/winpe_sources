# CreateHostsFileChangeHandle

- ea: `0x18003d94c`
- end: `0x18003db4d`
- name: `CreateHostsFileChangeHandle`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002c980`

## callees

- `0x1800088f0`
- `0x18003d94c`
- `0x18003db54`
- `0x180046ec0`
- `0x18005ecb8`
- `0x18005ecf4`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003db09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003db09`
- `api-ms-win-core-file-l1-1-0!FindFirstChangeNotificationW` at `0x18003dad6`
- `api-ms-win-core-file-l1-1-0!FindFirstChangeNotificationW` at `0x18003dad6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003da06`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003da06`

## string_xrefs

- `0x18003d9a4`: `t:\windows\system32`
- `0x18003da42`: `s:\windows\system32`

## pseudocode

```c
HANDLE CreateHostsFileChangeHandle()
{
  __int64 v0; // rdi
  const wchar_t *v1; // r8
  __int64 v2; // rdx
  WCHAR *v3; // rax
  __int64 v4; // rcx
  WCHAR *v5; // rcx
  __int64 v6; // rdx
  WCHAR *v7; // rax
  __int64 v8; // r8
  WCHAR *v9; // rax
  const wchar_t *v10; // rcx
  __int64 v11; // rbx
  WCHAR *v12; // rcx
  HANDLE result; // rax
  DWORD LastError; // eax
  WCHAR Buffer[520]; // [rsp+20h] [rbp-428h] BYREF

  if ( (xmmword_1800AB5A0 & 4) != 0 )
    WPP_SF_(1026, 15, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
  v0 = 2147483646;
  if ( (unsigned int)Util_IsRunningOnXboxGameOS() )
  {
    v1 = L"t:\\windows\\system32";
    v2 = 260;
    v3 = Buffer;
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*v1 )
        break;
      *v3++ = *v1++;
      --v4;
      --v2;
    }
    while ( v2 );
    v5 = v3 - 1;
    if ( v2 )
      v5 = v3;
    *v5 = 0;
  }
  else if ( (unsigned int)Util_IsRunningOnXbox() || (unsigned int)Util_IsRunningOnXboxSystemOS() )
  {
    StringCchCopyW(Buffer, 0x104u, L"s:\\windows\\system32");
  }
  else if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x103 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_(1035, 16, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
    return 0;
  }
  v6 = 260;
  v7 = Buffer;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  v8 = (260 - v6) & -(__int64)(v6 != 0);
  if ( v6 )
  {
    v9 = &Buffer[v8];
    v10 = L"\\drivers\\etc";
    v11 = 260 - v8;
    if ( 260 != v8 )
    {
      do
      {
        if ( !v0 )
          break;
        if ( !*v10 )
          break;
        *v9++ = *v10++;
        --v0;
        --v11;
      }
      while ( v11 );
    }
    v12 = v9 - 1;
    if ( v11 )
      v12 = v9;
    *v12 = 0;
  }
  result = FindFirstChangeNotificationW(Buffer, 0, 0x11u);
  if ( result == (HANDLE)-1LL )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      WPP_SF_(1035, 17, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(1035, 18, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids, LastError);
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18003d94c  mov     [rsp+arg_0], rbx
0x18003d951  mov     [rsp+arg_8], rsi
0x18003d956  push    rdi
0x18003d957  sub     rsp, 440h
0x18003d95e  mov     rax, cs:__security_cookie
0x18003d965  xor     rax, rsp
0x18003d968  mov     [rsp+448h+var_18], rax
0x18003d970  test    byte ptr cs:xmmword_1800AB5A0, 4
0x18003d977  jz      short loc_18003D98F
0x18003d979  mov     edx, 0Fh
0x18003d97e  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x18003d985  mov     ecx, 402h
0x18003d98a  call    WPP_SF_
0x18003d98f  call    Util_IsRunningOnXboxGameOS
0x18003d994  xor     esi, esi
0x18003d996  mov     edi, 7FFFFFFEh
0x18003d99b  test    eax, eax
0x18003d99d  jz      short loc_18003D9E8
0x18003d99f  mov     ebx, 104h
0x18003d9a4  lea     r8, aTWindowsSystem_0; "t:\\windows\\system32"
0x18003d9ab  mov     edx, ebx
0x18003d9ad  lea     rax, [rsp+448h+Buffer]
0x18003d9b2  mov     ecx, edi
0x18003d9b4  test    rcx, rcx
0x18003d9b7  jz      short loc_18003D9D8
0x18003d9b9  movzx   r9d, word ptr [r8]
0x18003d9bd  test    r9w, r9w
0x18003d9c1  jz      short loc_18003D9D8
0x18003d9c3  mov     [rax], r9w
0x18003d9c7  add     r8, 2
0x18003d9cb  add     rax, 2
0x18003d9cf  dec     rcx
0x18003d9d2  sub     rdx, 1
0x18003d9d6  jnz     short loc_18003D9B4
0x18003d9d8  test    rdx, rdx
0x18003d9db  lea     rcx, [rax-2]
0x18003d9df  cmovnz  rcx, rax
0x18003d9e3  mov     [rcx], si
0x18003d9e6  jmp     short loc_18003DA55
0x18003d9e8  call    Util_IsRunningOnXbox
0x18003d9ed  test    eax, eax
0x18003d9ef  jnz     short loc_18003DA3D
0x18003d9f1  call    Util_IsRunningOnXboxSystemOS
0x18003d9f6  test    eax, eax
0x18003d9f8  jnz     short loc_18003DA3D
0x18003d9fa  mov     ebx, 104h
0x18003d9ff  lea     rcx, [rsp+448h+Buffer]; lpBuffer
0x18003da04  mov     edx, ebx; uSize
0x18003da06  call    cs:__imp_GetSystemDirectoryW
0x18003da0c  dec     eax
0x18003da0e  cmp     eax, 103h
0x18003da13  jbe     short loc_18003DA55
0x18003da15  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003da1c  jz      loc_18003DB26
0x18003da22  mov     edx, 10h
0x18003da27  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x18003da2e  mov     ecx, 40Bh
0x18003da33  call    WPP_SF_
0x18003da38  jmp     loc_18003DB26
0x18003da3d  mov     ebx, 104h
0x18003da42  lea     r8, aSWindowsSystem; "s:\\windows\\system32"
0x18003da49  mov     edx, ebx; cchDest
0x18003da4b  lea     rcx, [rsp+448h+Buffer]; pszDest
0x18003da50  call    StringCchCopyW
0x18003da55  mov     rdx, rbx
0x18003da58  lea     rax, [rsp+448h+Buffer]
0x18003da5d  cmp     [rax], si
0x18003da60  jz      short loc_18003DA6C
0x18003da62  add     rax, 2
0x18003da66  sub     rdx, 1
0x18003da6a  jnz     short loc_18003DA5D
0x18003da6c  mov     rcx, rbx
0x18003da6f  mov     rax, rdx
0x18003da72  sub     rcx, rdx
0x18003da75  neg     rax
0x18003da78  sbb     r8, r8
0x18003da7b  and     r8, rcx
0x18003da7e  test    rdx, rdx
0x18003da81  jz      short loc_18003DAC7
0x18003da83  lea     rax, [rsp+448h+Buffer]
0x18003da88  lea     rax, [rax+r8*2]
0x18003da8c  lea     rcx, aDriversEtc; "\\drivers\\etc"
0x18003da93  sub     rbx, r8
0x18003da96  jz      short loc_18003DAB9
0x18003da98  test    rdi, rdi
0x18003da9b  jz      short loc_18003DAB9
0x18003da9d  movzx   edx, word ptr [rcx]
0x18003daa0  test    dx, dx
0x18003daa3  jz      short loc_18003DAB9
0x18003daa5  mov     [rax], dx
0x18003daa8  add     rcx, 2
0x18003daac  add     rax, 2
0x18003dab0  dec     rdi
0x18003dab3  sub     rbx, 1
0x18003dab7  jnz     short loc_18003DA98
0x18003dab9  test    rbx, rbx
0x18003dabc  lea     rcx, [rax-2]
0x18003dac0  cmovnz  rcx, rax
0x18003dac4  mov     [rcx], si
0x18003dac7  mov     ebx, 11h
0x18003dacc  lea     rcx, [rsp+448h+Buffer]; lpPathName
0x18003dad1  mov     r8d, ebx; dwNotifyFilter
0x18003dad4  xor     edx, edx; bWatchSubtree
0x18003dad6  call    cs:__imp_FindFirstChangeNotificationW
0x18003dadc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003dae0  jnz     short loc_18003DB28
0x18003dae2  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x18003dae8  test    al, 8
0x18003daea  jz      short loc_18003DB26
0x18003daec  mov     edx, ebx
0x18003daee  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x18003daf5  mov     ecx, 40Bh
0x18003dafa  call    WPP_SF_
0x18003daff  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x18003db05  test    al, 8
0x18003db07  jz      short loc_18003DB26
0x18003db09  call    cs:__imp_GetLastError
0x18003db0f  lea     edx, [rbx+1]
0x18003db12  mov     ecx, 40Bh
0x18003db17  mov     r9d, eax
0x18003db1a  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x18003db21  call    WPP_SF_d
0x18003db26  xor     eax, eax
0x18003db28  mov     rcx, [rsp+448h+var_18]
0x18003db30  xor     rcx, rsp; StackCookie
0x18003db33  call    __security_check_cookie
0x18003db38  lea     r11, [rsp+448h+var_8]
0x18003db40  mov     rbx, [r11+10h]
0x18003db44  mov     rsi, [r11+18h]
0x18003db48  mov     rsp, r11
0x18003db4b  pop     rdi
0x18003db4c  retn
```
