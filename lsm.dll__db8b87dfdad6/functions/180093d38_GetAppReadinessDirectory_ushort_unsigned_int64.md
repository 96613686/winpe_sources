# GetAppReadinessDirectory(ushort *,unsigned __int64)

- ea: `0x180093d38`
- end: `0x180093e3e`
- name: `?GetAppReadinessDirectory@@YAJPEAG_K@Z`
- size: `262`
- prototype: `__int64 __fastcall(WCHAR *lpPathName, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x180018528`

## callees

- `0x180093d38`
- `0x180093e44`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180093d93`
- `ntdll!RtlGetPersistedStateLocation` at `0x180093d93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093dce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093e11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093dce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093e11`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180093dbf`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180093dbf`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180093e07`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180093e07`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180093df6`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180093df6`

## string_xrefs

- `0x180093de7`: `AppReadiness`
- `0x180093d7a`: `AppReadinessDirectory`

## pseudocode

```c
__int64 __fastcall GetAppReadinessDirectory(WCHAR *lpPathName, __int64 a2)
{
  __int64 result; // rax
  int v4; // ebx
  signed int LastError; // eax
  signed int v6; // eax
  unsigned int v7; // [rsp+58h] [rbp+10h] BYREF
  int v8; // [rsp+5Ch] [rbp+14h]
  UINT uSize; // [rsp+60h] [rbp+18h] BYREF

  v8 = HIDWORD(a2);
  v7 = 0;
  result = ULongLongToULong(0x208u, &v7);
  v4 = result;
  if ( (int)result >= 0 )
  {
    if ( (int)RtlGetPersistedStateLocation(L"AppReadinessDirectory", 0, 0, 1, lpPathName, v7, &v7) >= 0 )
      goto LABEL_17;
    uSize = 0;
    result = ULongLongToULong(0x104u, &uSize);
    if ( (int)result < 0 )
      return result;
    if ( GetWindowsDirectoryW(lpPathName, uSize) - 1 <= 0x102 )
      goto LABEL_18;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_18:
      v4 = PathCchAppend(lpPathName, 0x104u, L"AppReadiness");
      if ( v4 >= 0 )
      {
LABEL_17:
        if ( !CreateDirectoryW(lpPathName, 0) )
        {
          v6 = GetLastError();
          v4 = v6;
          if ( v6 > 0 )
            v4 = (unsigned __int16)v6 | 0x80070000;
          if ( v4 == -2147024713 )
            return 0;
        }
      }
    }
    return (unsigned int)v4;
  }
  return result;
}

```

## disassembly

```asm
0x180093d38  mov     rax, rsp
0x180093d3b  mov     [rax+8], rbx
0x180093d3f  mov     [rax+10h], rdx
0x180093d43  push    rdi
0x180093d44  sub     rsp, 40h
0x180093d48  mov     rdi, rcx
0x180093d4b  mov     dword ptr [rax+10h], 0
0x180093d52  mov     ecx, 208h; unsigned __int64
0x180093d57  lea     rdx, [rax+10h]; unsigned int *
0x180093d5b  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180093d60  mov     ebx, eax
0x180093d62  test    eax, eax
0x180093d64  js      loc_180093E33
0x180093d6a  lea     rax, [rsp+48h+arg_8]
0x180093d6f  mov     r9d, 1
0x180093d75  mov     [rsp+48h+var_18], rax
0x180093d7a  lea     rcx, aAppreadinessdi; "AppReadinessDirectory"
0x180093d81  mov     eax, [rsp+48h+arg_8]
0x180093d85  xor     r8d, r8d
0x180093d88  mov     [rsp+48h+var_20], eax
0x180093d8c  xor     edx, edx
0x180093d8e  mov     [rsp+48h+var_28], rdi
0x180093d93  call    cs:__imp_RtlGetPersistedStateLocation
0x180093d99  test    eax, eax
0x180093d9b  jns     short loc_180093E02
0x180093d9d  lea     rdx, [rsp+48h+uSize]; unsigned int *
0x180093da2  mov     [rsp+48h+uSize], 0
0x180093daa  mov     ecx, 104h; unsigned __int64
0x180093daf  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180093db4  test    eax, eax
0x180093db6  js      short loc_180093E33
0x180093db8  mov     edx, [rsp+48h+uSize]; uSize
0x180093dbc  mov     rcx, rdi; lpBuffer
0x180093dbf  call    cs:__imp_GetWindowsDirectoryW
0x180093dc5  dec     eax
0x180093dc7  cmp     eax, 102h
0x180093dcc  jbe     short loc_180093DE7
0x180093dce  call    cs:__imp_GetLastError
0x180093dd4  mov     ebx, eax
0x180093dd6  test    eax, eax
0x180093dd8  jle     short loc_180093DE3
0x180093dda  movzx   ebx, ax
0x180093ddd  or      ebx, 80070000h
0x180093de3  test    ebx, ebx
0x180093de5  js      short loc_180093E31
0x180093de7  lea     r8, pszMore; "AppReadiness"
0x180093dee  mov     edx, 104h; cchPath
0x180093df3  mov     rcx, rdi; pszPath
0x180093df6  call    cs:__imp_PathCchAppend
0x180093dfc  mov     ebx, eax
0x180093dfe  test    eax, eax
0x180093e00  js      short loc_180093E31
0x180093e02  xor     edx, edx; lpSecurityAttributes
0x180093e04  mov     rcx, rdi; lpPathName
0x180093e07  call    cs:__imp_CreateDirectoryW
0x180093e0d  test    eax, eax
0x180093e0f  jnz     short loc_180093E31
0x180093e11  call    cs:__imp_GetLastError
0x180093e17  mov     ebx, eax
0x180093e19  test    eax, eax
0x180093e1b  jle     short loc_180093E26
0x180093e1d  movzx   ebx, ax
0x180093e20  or      ebx, 80070000h
0x180093e26  xor     eax, eax
0x180093e28  cmp     ebx, 800700B7h
0x180093e2e  cmovz   ebx, eax
0x180093e31  mov     eax, ebx
0x180093e33  mov     rbx, [rsp+48h+arg_0]
0x180093e38  add     rsp, 40h
0x180093e3c  pop     rdi
0x180093e3d  retn
```
