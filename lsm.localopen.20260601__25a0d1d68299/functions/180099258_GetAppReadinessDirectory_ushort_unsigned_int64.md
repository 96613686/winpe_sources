# GetAppReadinessDirectory(ushort *,unsigned __int64)

- ea: `0x180099258`
- end: `0x180099387`
- name: `?GetAppReadinessDirectory@@YAJPEAG_K@Z`
- size: `303`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x18000c500`

## callees

- `0x180099258`
- `0x180099390`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x1800992b3`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800992b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800992fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800992fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099353`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800992e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800992e9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180099343`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180099343`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009932c`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009932c`

## string_xrefs

- `0x18009929a`: `AppReadinessDirectory`
- `0x18009931d`: `AppReadiness`

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
0x180099258  mov     rax, rsp
0x18009925b  mov     [rax+8], rbx
0x18009925f  mov     [rax+10h], rdx
0x180099263  push    rdi
0x180099264  sub     rsp, 40h
0x180099268  mov     rdi, rcx
0x18009926b  mov     dword ptr [rax+10h], 0
0x180099272  mov     ecx, 208h; unsigned __int64
0x180099277  lea     rdx, [rax+10h]; unsigned int *
0x18009927b  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180099280  mov     ebx, eax
0x180099282  test    eax, eax
0x180099284  js      loc_18009937B
0x18009928a  lea     rax, [rsp+48h+arg_8]
0x18009928f  mov     r9d, 1
0x180099295  mov     [rsp+48h+var_18], rax
0x18009929a  lea     rcx, aAppreadinessdi; "AppReadinessDirectory"
0x1800992a1  mov     eax, [rsp+48h+arg_8]
0x1800992a5  xor     r8d, r8d
0x1800992a8  mov     [rsp+48h+var_20], eax
0x1800992ac  xor     edx, edx
0x1800992ae  mov     [rsp+48h+var_28], rdi
0x1800992b3  call    cs:__imp_RtlGetPersistedStateLocation
0x1800992ba  nop     dword ptr [rax+rax+00h]
0x1800992bf  test    eax, eax
0x1800992c1  jns     short loc_18009933E
0x1800992c3  lea     rdx, [rsp+48h+uSize]; unsigned int *
0x1800992c8  mov     [rsp+48h+uSize], 0
0x1800992d0  mov     ecx, 104h; unsigned __int64
0x1800992d5  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800992da  test    eax, eax
0x1800992dc  js      loc_18009937B
0x1800992e2  mov     edx, [rsp+48h+uSize]; uSize
0x1800992e6  mov     rcx, rdi; lpBuffer
0x1800992e9  call    cs:__imp_GetWindowsDirectoryW
0x1800992f0  nop     dword ptr [rax+rax+00h]
0x1800992f5  dec     eax
0x1800992f7  cmp     eax, 102h
0x1800992fc  jbe     short loc_18009931D
0x1800992fe  call    cs:__imp_GetLastError
0x180099305  nop     dword ptr [rax+rax+00h]
0x18009930a  mov     ebx, eax
0x18009930c  test    eax, eax
0x18009930e  jle     short loc_180099319
0x180099310  movzx   ebx, ax
0x180099313  or      ebx, 80070000h
0x180099319  test    ebx, ebx
0x18009931b  js      short loc_180099379
0x18009931d  lea     r8, pszMore; "AppReadiness"
0x180099324  mov     edx, 104h; cchPath
0x180099329  mov     rcx, rdi; pszPath
0x18009932c  call    cs:__imp_PathCchAppend
0x180099333  nop     dword ptr [rax+rax+00h]
0x180099338  mov     ebx, eax
0x18009933a  test    eax, eax
0x18009933c  js      short loc_180099379
0x18009933e  xor     edx, edx; lpSecurityAttributes
0x180099340  mov     rcx, rdi; lpPathName
0x180099343  call    cs:__imp_CreateDirectoryW
0x18009934a  nop     dword ptr [rax+rax+00h]
0x18009934f  test    eax, eax
0x180099351  jnz     short loc_180099379
0x180099353  call    cs:__imp_GetLastError
0x18009935a  nop     dword ptr [rax+rax+00h]
0x18009935f  mov     ebx, eax
0x180099361  test    eax, eax
0x180099363  jle     short loc_18009936E
0x180099365  movzx   ebx, ax
0x180099368  or      ebx, 80070000h
0x18009936e  xor     eax, eax
0x180099370  cmp     ebx, 800700B7h
0x180099376  cmovz   ebx, eax
0x180099379  mov     eax, ebx
0x18009937b  mov     rbx, [rsp+48h+arg_0]
0x180099380  add     rsp, 40h
0x180099384  pop     rdi
0x180099385  retn
```
