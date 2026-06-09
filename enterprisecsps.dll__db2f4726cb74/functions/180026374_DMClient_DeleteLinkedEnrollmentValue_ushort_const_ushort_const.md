# DMClient::DeleteLinkedEnrollmentValue(ushort const *,ushort const *)

- ea: `0x180026374`
- end: `0x1800264e1`
- name: `?DeleteLinkedEnrollmentValue@DMClient@@YAJPEBG0@Z`
- size: `365`
- prototype: `__int64 __fastcall(DMClient *__hidden this, LPCWSTR lpValueName, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800262c4`
- `0x1800341f0`

## callees

- `0x180008de0`
- `0x18000da10`
- `0x18000db08`
- `0x180025d20`
- `0x180026374`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180026485`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180026485`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800264a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800264a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002645d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002645d`

## string_xrefs

- `0x180026427`: `LinkedEnrollment`

## pseudocode

```c
int __fastcall DMClient::DeleteLinkedEnrollmentValue(DMClient *this, LPCWSTR lpValueName, const unsigned __int16 *a3)
{
  const unsigned __int16 *v5; // rax
  int result; // eax
  LSTATUS v7; // eax
  signed int v8; // ebx
  LSTATUS v9; // eax
  HKEY hKey; // [rsp+30h] [rbp-F8h] BYREF
  WCHAR SubKey[104]; // [rsp+40h] [rbp-E8h] BYREF

  hKey = 0;
  if ( !lpValueName || !this )
    return -2147024809;
  v5 = DMGetNonVolatileRegPrefix();
  result = StringCchCopyW(SubKey, 0x61u, v5);
  if ( result >= 0 )
  {
    result = StringCchCatW(SubKey, 0x61u, c_szEnrollmentsDB);
    if ( result >= 0 )
    {
      result = StringCchCatW(SubKey, 0x61u, (const unsigned __int16 *)this);
      if ( result >= 0 )
      {
        result = StringCchCatW(SubKey, 0x61u, L"\\");
        if ( result >= 0 )
        {
          result = StringCchCatW(SubKey, 0x61u, c_szEnrollmentsDBLinkedEnrollment);
          if ( result >= 0 )
          {
            v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &hKey);
            v8 = v7;
            if ( v7 > 0 )
              v8 = (unsigned __int16)v7 | 0x80070000;
            if ( v8 >= 0 )
            {
              v9 = RegDeleteValueW(hKey, lpValueName);
              v8 = v9;
              if ( v9 > 0 )
                v8 = (unsigned __int16)v9 | 0x80070000;
            }
            if ( hKey )
              RegCloseKey(hKey);
            return v8;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180026374  mov     [rsp+arg_10], rbx
0x180026379  mov     [rsp+arg_18], rsi
0x18002637e  push    rdi
0x18002637f  sub     rsp, 120h
0x180026386  mov     rax, cs:__security_cookie
0x18002638d  xor     rax, rsp
0x180026390  mov     [rsp+128h+var_18], rax
0x180026398  mov     [rsp+128h+hKey], 0
0x1800263a1  mov     rdi, rdx
0x1800263a4  mov     rbx, rcx
0x1800263a7  test    rdx, rdx
0x1800263aa  jz      loc_1800264B4
0x1800263b0  test    rcx, rcx
0x1800263b3  jz      loc_1800264B4
0x1800263b9  call    ?DMGetNonVolatileRegPrefix@@YAPEBGXZ; DMGetNonVolatileRegPrefix(void)
0x1800263be  mov     esi, 61h ; 'a'
0x1800263c3  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x1800263c8  mov     edx, esi; unsigned __int64
0x1800263ca  mov     r8, rax; unsigned __int16 *
0x1800263cd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800263d2  test    eax, eax
0x1800263d4  js      loc_1800264BB
0x1800263da  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x1800263e1  mov     edx, esi; unsigned __int64
0x1800263e3  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x1800263e8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800263ed  test    eax, eax
0x1800263ef  js      loc_1800264BB
0x1800263f5  mov     r8, rbx; unsigned __int16 *
0x1800263f8  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x1800263fd  mov     edx, esi; unsigned __int64
0x1800263ff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180026404  test    eax, eax
0x180026406  js      loc_1800264BB
0x18002640c  lea     r8, StringValue; "\\"
0x180026413  mov     edx, esi; unsigned __int64
0x180026415  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x18002641a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002641f  test    eax, eax
0x180026421  js      loc_1800264BB
0x180026427  lea     r8, ?c_szEnrollmentsDBLinkedEnrollment@@3PAGA; "LinkedEnrollment"
0x18002642e  mov     edx, esi; unsigned __int64
0x180026430  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x180026435  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002643a  test    eax, eax
0x18002643c  js      short loc_1800264BB
0x18002643e  lea     rax, [rsp+128h+hKey]
0x180026443  mov     r9d, 0F003Fh; samDesired
0x180026449  xor     r8d, r8d; ulOptions
0x18002644c  mov     [rsp+128h+phkResult], rax; phkResult
0x180026451  lea     rdx, [rsp+128h+SubKey]; lpSubKey
0x180026456  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002645d  call    cs:__imp_RegOpenKeyExW
0x180026464  nop     dword ptr [rax+rax+00h]
0x180026469  mov     ebx, eax
0x18002646b  mov     esi, 80070000h
0x180026470  test    eax, eax
0x180026472  jle     short loc_180026479
0x180026474  movzx   ebx, ax
0x180026477  or      ebx, esi
0x180026479  test    ebx, ebx
0x18002647b  js      short loc_18002649C
0x18002647d  mov     rcx, [rsp+128h+hKey]; hKey
0x180026482  mov     rdx, rdi; lpValueName
0x180026485  call    cs:__imp_RegDeleteValueW
0x18002648c  nop     dword ptr [rax+rax+00h]
0x180026491  mov     ebx, eax
0x180026493  test    eax, eax
0x180026495  jle     short loc_18002649C
0x180026497  movzx   ebx, ax
0x18002649a  or      ebx, esi
0x18002649c  mov     rcx, [rsp+128h+hKey]; hKey
0x1800264a1  test    rcx, rcx
0x1800264a4  jz      short loc_1800264B9
0x1800264a6  call    cs:__imp_RegCloseKey
0x1800264ad  nop     dword ptr [rax+rax+00h]
0x1800264b2  jmp     short loc_1800264B9
0x1800264b4  mov     ebx, 80070057h
0x1800264b9  mov     eax, ebx
0x1800264bb  mov     rcx, [rsp+128h+var_18]
0x1800264c3  xor     rcx, rsp; StackCookie
0x1800264c6  call    __security_check_cookie
0x1800264cb  lea     r11, [rsp+128h+var_8]
0x1800264d3  mov     rbx, [r11+20h]
0x1800264d7  mov     rsi, [r11+28h]
0x1800264db  mov     rsp, r11
0x1800264de  pop     rdi
0x1800264df  retn
```
