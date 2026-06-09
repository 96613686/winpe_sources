# OpenRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)

- ea: `0x140005760`
- end: `0x1400058ab`
- name: `?OpenRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z`
- size: `331`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWCH lpWideCharStr, REGSAM samDesired, PHKEY phkResult)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140001950`
- `0x1400051cc`
- `0x14000f7d8`

## callees

- `0x140005760`
- `0x1400161d0`
- `0x140016200`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1400057fa`
- `KERNEL32!WideCharToMultiByte` at `0x14000584e`
- `KERNEL32!WideCharToMultiByte` at `0x1400057fa`
- `KERNEL32!WideCharToMultiByte` at `0x14000584e`
- `KERNEL32!GetLastError` at `0x140005858`
- `KERNEL32!GetLastError` at `0x140005858`
- `ADVAPI32!RegOpenKeyExA` at `0x140005883`
- `ADVAPI32!RegOpenKeyExA` at `0x140005883`
- `ADVAPI32!RegOpenKeyExW` at `0x1400057a2`
- `ADVAPI32!RegOpenKeyExW` at `0x1400057a2`

## pseudocode

```c
int __fastcall OpenRegSettings(HKEY hKey, LPCWCH lpWideCharStr, REGSAM samDesired, PHKEY phkResult)
{
  int result; // eax
  int cbMultiByte; // eax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  CHAR *v14; // r12
  CHAR MultiByteStr[64]; // [rsp+40h] [rbp+0h] BYREF

  if ( Global::g_fWindowsNT )
  {
    result = RegOpenKeyExW(hKey, lpWideCharStr, 0, samDesired, phkResult);
    goto LABEL_3;
  }
  if ( !lpWideCharStr || !*lpWideCharStr )
  {
    v14 = 0;
LABEL_15:
    result = RegOpenKeyExA(hKey, v14, 0, samDesired, phkResult);
LABEL_3:
    if ( !result )
      return 0;
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  cbMultiByte = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
  if ( cbMultiByte )
  {
    v10 = cbMultiByte + 15LL;
    if ( v10 < cbMultiByte )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
    v12 = alloca(v11);
    v13 = alloca(v11);
    v14 = MultiByteStr;
    if ( WideCharToMultiByte(0, 0, lpWideCharStr, -1, MultiByteStr, cbMultiByte, 0, 0) )
      goto LABEL_15;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140005760  push    rbp
0x140005762  push    rbx
0x140005763  push    rsi
0x140005764  push    rdi
0x140005765  push    r12
0x140005767  push    r14
0x140005769  push    r15
0x14000576b  sub     rsp, 50h
0x14000576f  lea     rbp, [rsp+40h]
0x140005774  mov     rax, cs:__security_cookie
0x14000577b  xor     rax, rbp
0x14000577e  mov     qword ptr [rbp+40h+MultiByteStr], rax
0x140005782  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x140005789  mov     rdi, r9
0x14000578c  mov     esi, r8d
0x14000578f  mov     rbx, rdx
0x140005792  mov     r14, rcx
0x140005795  jz      short loc_1400057C3
0x140005797  mov     [rsp+80h+phkResult], r9; phkResult
0x14000579c  mov     r9d, r8d; samDesired
0x14000579f  xor     r8d, r8d; ulOptions
0x1400057a2  call    cs:__imp_RegOpenKeyExW
0x1400057a8  test    eax, eax
0x1400057aa  jz      loc_14000588E
0x1400057b0  jle     loc_140005890
0x1400057b6  movzx   eax, ax
0x1400057b9  or      eax, 80070000h
0x1400057be  jmp     loc_140005890
0x1400057c3  test    rbx, rbx
0x1400057c6  jz      loc_14000586C
0x1400057cc  cmp     word ptr [rdx], 0
0x1400057d0  jz      loc_14000586C
0x1400057d6  xor     r15d, r15d
0x1400057d9  mov     r9d, 0FFFFFFFFh; cchWideChar
0x1400057df  mov     [rsp+80h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1400057e4  mov     r8, rbx; lpWideCharStr
0x1400057e7  mov     [rsp+80h+lpDefaultChar], r15; lpDefaultChar
0x1400057ec  xor     edx, edx; dwFlags
0x1400057ee  mov     [rsp+80h+cbMultiByte], r15d; cbMultiByte
0x1400057f3  xor     ecx, ecx; CodePage
0x1400057f5  mov     [rsp+80h+phkResult], r15; lpMultiByteStr
0x1400057fa  call    cs:__imp_WideCharToMultiByte
0x140005800  movsxd  rdx, eax
0x140005803  test    eax, eax
0x140005805  jz      short loc_140005858
0x140005807  lea     rcx, [rdx+0Fh]
0x14000580b  cmp     rcx, rdx
0x14000580e  ja      short loc_14000581A
0x140005810  mov     rcx, 0FFFFFFFFFFFFFF0h
0x14000581a  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000581e  mov     rax, rcx
0x140005821  call    _alloca_probe
0x140005826  sub     rsp, rcx
0x140005829  mov     r9d, 0FFFFFFFFh; cchWideChar
0x14000582f  mov     r8, rbx; lpWideCharStr
0x140005832  xor     ecx, ecx; CodePage
0x140005834  mov     [rsp+80h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x140005839  lea     r12, [rsp+80h+MultiByteStr]
0x14000583e  mov     [rsp+80h+lpDefaultChar], r15; lpDefaultChar
0x140005843  mov     [rsp+80h+cbMultiByte], edx; cbMultiByte
0x140005847  xor     edx, edx; dwFlags
0x140005849  mov     [rsp+80h+phkResult], r12; lpMultiByteStr
0x14000584e  call    cs:__imp_WideCharToMultiByte
0x140005854  test    eax, eax
0x140005856  jnz     short loc_140005872
0x140005858  call    cs:__imp_GetLastError
0x14000585e  test    eax, eax
0x140005860  jle     short loc_140005890
0x140005862  movzx   eax, ax
0x140005865  or      eax, 80070000h
0x14000586a  jmp     short loc_140005890
0x14000586c  xor     r15d, r15d
0x14000586f  mov     r12d, r15d
0x140005872  mov     r9d, esi; samDesired
0x140005875  mov     [rsp+80h+phkResult], rdi; phkResult
0x14000587a  xor     r8d, r8d; ulOptions
0x14000587d  mov     rdx, r12; lpSubKey
0x140005880  mov     rcx, r14; hKey
0x140005883  call    cs:__imp_RegOpenKeyExA
0x140005889  jmp     loc_1400057A8
0x14000588e  xor     eax, eax
0x140005890  mov     rcx, qword ptr [rbp+40h+MultiByteStr]
0x140005894  xor     rcx, rbp; StackCookie
0x140005897  call    __security_check_cookie
0x14000589c  lea     rsp, [rbp+10h]
0x1400058a0  pop     r15
0x1400058a2  pop     r14
0x1400058a4  pop     r12
0x1400058a6  pop     rdi
0x1400058a7  pop     rsi
0x1400058a8  pop     rbx
0x1400058a9  pop     rbp
0x1400058aa  retn
```
