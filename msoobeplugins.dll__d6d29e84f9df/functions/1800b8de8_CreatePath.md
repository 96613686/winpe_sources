# CreatePath

- ea: `0x1800b8de8`
- end: `0x1800b8fc2`
- name: `CreatePath`
- size: `474`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800b873c`

## callees

- `0x1800b8cd4`
- `0x1800b8de8`
- `0x1800b91d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800b8e6b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800b8e6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b8f7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b8f7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b8f6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b8f6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8e8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8eea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8f4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8f85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8e8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8eea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8f4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8f85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b8ebe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b8f8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b8fa3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b8ebe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b8f8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b8fa3`
- `KERNEL32!GetFileAttributesW` at `0x1800b8f27`
- `KERNEL32!GetFileAttributesW` at `0x1800b8f27`
- `KERNEL32!CreateDirectoryW` at `0x1800b8e85`
- `KERNEL32!CreateDirectoryW` at `0x1800b8eff`
- `KERNEL32!CreateDirectoryW` at `0x1800b8e85`
- `KERNEL32!CreateDirectoryW` at `0x1800b8eff`

## string_xrefs

- `0x1800b8ef3`: `CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x`
- `0x1800b8f42`: `CreatePath: Existing path [%s] is not a directory; GLE = 0x%x`
- `0x1800b8eaa`: `CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x`
- `0x1800b8f1b`: `CreatePath: Unable to create [%s]; GLE = 0x%x`
- `0x1800b8f57`: `CreatePath: Unable to get attributes for [%s]; GLE = 0x%x`

## pseudocode

```c
_BOOL8 __fastcall CreatePath(unsigned __int16 *a1)
{
  WCHAR *v2; // rdi
  DWORD v3; // ebx
  int v4; // ebp
  const wchar_t *v5; // rax
  wchar_t *v6; // rax
  DWORD LastError; // eax
  DWORD v8; // eax
  unsigned __int16 *v9; // r9
  const wchar_t *v10; // r8
  DWORD FileAttributesW; // eax
  HANDLE ProcessHeap; // rax
  __int64 v14; // [rsp+20h] [rbp-38h]
  wchar_t *v15; // [rsp+60h] [rbp+8h]

  if ( a1 && *a1 )
  {
    v2 = (WCHAR *)PrepareUnicodePathEx(a1);
    if ( v2 )
    {
      v3 = 0;
      v4 = 1;
      v5 = v2;
      while ( 1 )
      {
        v6 = wcschr(v5, 0x5Cu);
        v15 = v6;
        if ( !v6 )
          break;
        *v6 = 0;
        if ( !CreateDirectoryW(v2, 0) )
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError == 5 || LastError == 183 )
          {
            v3 = 0;
          }
          else
          {
            LODWORD(v14) = LastError;
            LibLog(&g_WdsLibLog, 50331648, L"CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x", v2, v14);
            SetLastError(v3);
            v4 = 0;
          }
        }
        *v15 = 92;
        v5 = v15 + 1;
        if ( v4 != 1 )
        {
          v8 = GetLastError();
          v9 = a1;
          v10 = L"CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x";
          goto LABEL_21;
        }
      }
      if ( CreateDirectoryW(v2, 0) )
        goto LABEL_23;
      v8 = GetLastError();
      v3 = v8;
      if ( v8 != 183 )
      {
        v9 = v2;
        v10 = L"CreatePath: Unable to create [%s]; GLE = 0x%x";
        goto LABEL_22;
      }
      FileAttributesW = GetFileAttributesW(v2);
      if ( FileAttributesW == -1 )
      {
        v8 = GetLastError();
        v9 = v2;
        v10 = L"CreatePath: Unable to get attributes for [%s]; GLE = 0x%x";
LABEL_21:
        v3 = v8;
LABEL_22:
        LODWORD(v14) = v8;
        LibLog(&g_WdsLibLog, 50331648, v10, v9, v14);
        goto LABEL_23;
      }
      if ( (FileAttributesW & 0x10) != 0 )
      {
        v3 = 0;
      }
      else
      {
        LODWORD(v14) = 183;
        LibLog(&g_WdsLibLog, 50331648, L"CreatePath: Existing path [%s] is not a directory; GLE = 0x%x", v2, v14);
      }
LABEL_23:
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    else
    {
      v3 = GetLastError();
    }
    SetLastError(v3);
    return v3 == 0;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x1800b8de8  mov     r11, rsp
0x1800b8deb  mov     [r11+10h], rbx
0x1800b8def  mov     [r11+18h], rbp
0x1800b8df3  push    rsi
0x1800b8df4  push    rdi
0x1800b8df5  push    r13
0x1800b8df7  push    r14
0x1800b8df9  push    r15
0x1800b8dfb  sub     rsp, 30h
0x1800b8dff  mov     qword ptr [r11+8], 0
0x1800b8e07  mov     rsi, rcx
0x1800b8e0a  test    rcx, rcx
0x1800b8e0d  jz      loc_1800B8F9E
0x1800b8e13  xor     eax, eax
0x1800b8e15  cmp     ax, [rcx]
0x1800b8e18  jz      loc_1800B8F9E
0x1800b8e1e  lea     rdx, [r11+8]
0x1800b8e22  call    PrepareUnicodePathEx
0x1800b8e27  mov     rdi, rax
0x1800b8e2a  test    rax, rax
0x1800b8e2d  jz      loc_1800B8F85
0x1800b8e33  mov     rax, [rsp+58h+arg_0]
0x1800b8e38  xor     ebx, ebx
0x1800b8e3a  mov     ebp, 1
0x1800b8e3f  test    rax, rax
0x1800b8e42  jz      short loc_1800B8E4A
0x1800b8e44  add     rax, 2
0x1800b8e48  jmp     short loc_1800B8E4D
0x1800b8e4a  mov     rax, rdi
0x1800b8e4d  mov     [rsp+58h+arg_0], rax
0x1800b8e52  lea     r15, g_WdsLibLog
0x1800b8e59  mov     r13d, 5Ch ; '\'
0x1800b8e5f  mov     r14d, 3000000h
0x1800b8e65  mov     edx, r13d; Ch
0x1800b8e68  mov     rcx, rax; Str
0x1800b8e6b  call    cs:__imp_wcschr
0x1800b8e71  xor     edx, edx; lpSecurityAttributes
0x1800b8e73  mov     [rsp+58h+arg_0], rax
0x1800b8e78  test    rax, rax
0x1800b8e7b  jz      short loc_1800B8EFC
0x1800b8e7d  xor     ecx, ecx
0x1800b8e7f  mov     [rax], cx
0x1800b8e82  mov     rcx, rdi; lpPathName
0x1800b8e85  call    cs:__imp_CreateDirectoryW
0x1800b8e8b  test    eax, eax
0x1800b8e8d  jnz     short loc_1800B8ECA
0x1800b8e8f  call    cs:__imp_GetLastError
0x1800b8e95  mov     ebx, eax
0x1800b8e97  cmp     eax, 5
0x1800b8e9a  jz      short loc_1800B8EC8
0x1800b8e9c  cmp     eax, 0B7h
0x1800b8ea1  jz      short loc_1800B8EC8
0x1800b8ea3  mov     r9, rdi
0x1800b8ea6  mov     dword ptr [rsp+58h+var_38], eax
0x1800b8eaa  lea     r8, aCreatepathUnab; "CreatePath: Unable to create intermedia"...
0x1800b8eb1  mov     edx, r14d
0x1800b8eb4  mov     rcx, r15
0x1800b8eb7  call    LibLog
0x1800b8ebc  mov     ecx, ebx; dwErrCode
0x1800b8ebe  call    cs:__imp_SetLastError
0x1800b8ec4  xor     ebp, ebp
0x1800b8ec6  jmp     short loc_1800B8ECA
0x1800b8ec8  xor     ebx, ebx
0x1800b8eca  mov     rax, [rsp+58h+arg_0]
0x1800b8ecf  mov     [rax], r13w
0x1800b8ed3  mov     rax, [rsp+58h+arg_0]
0x1800b8ed8  add     rax, 2
0x1800b8edc  mov     [rsp+58h+arg_0], rax
0x1800b8ee1  cmp     ebp, 1
0x1800b8ee4  jz      loc_1800B8E65
0x1800b8eea  call    cs:__imp_GetLastError
0x1800b8ef0  mov     r9, rsi
0x1800b8ef3  lea     r8, aCreatepathUnab_2; "CreatePath: Unable to create parent dir"...
0x1800b8efa  jmp     short loc_1800B8F5E
0x1800b8efc  mov     rcx, rdi; lpPathName
0x1800b8eff  call    cs:__imp_CreateDirectoryW
0x1800b8f05  test    eax, eax
0x1800b8f07  jnz     short loc_1800B8F6F
0x1800b8f09  call    cs:__imp_GetLastError
0x1800b8f0f  mov     ebx, eax
0x1800b8f11  cmp     eax, 0B7h
0x1800b8f16  jz      short loc_1800B8F24
0x1800b8f18  mov     r9, rdi
0x1800b8f1b  lea     r8, aCreatepathUnab_1; "CreatePath: Unable to create [%s]; GLE "...
0x1800b8f22  jmp     short loc_1800B8F60
0x1800b8f24  mov     rcx, rdi; lpFileName
0x1800b8f27  call    cs:__imp_GetFileAttributesW
0x1800b8f2d  cmp     eax, 0FFFFFFFFh
0x1800b8f30  jz      short loc_1800B8F4E
0x1800b8f32  test    al, 10h
0x1800b8f34  jz      short loc_1800B8F3A
0x1800b8f36  xor     ebx, ebx
0x1800b8f38  jmp     short loc_1800B8F6F
0x1800b8f3a  mov     dword ptr [rsp+58h+var_38], 0B7h
0x1800b8f42  lea     r8, aCreatepathExis; "CreatePath: Existing path [%s] is not a"...
0x1800b8f49  mov     r9, rdi
0x1800b8f4c  jmp     short loc_1800B8F64
0x1800b8f4e  call    cs:__imp_GetLastError
0x1800b8f54  mov     r9, rdi
0x1800b8f57  lea     r8, aCreatepathUnab_0; "CreatePath: Unable to get attributes fo"...
0x1800b8f5e  mov     ebx, eax
0x1800b8f60  mov     dword ptr [rsp+58h+var_38], eax
0x1800b8f64  mov     edx, r14d
0x1800b8f67  mov     rcx, r15
0x1800b8f6a  call    LibLog
0x1800b8f6f  call    cs:__imp_GetProcessHeap
0x1800b8f75  mov     r8, rdi; lpMem
0x1800b8f78  xor     edx, edx; dwFlags
0x1800b8f7a  mov     rcx, rax; hHeap
0x1800b8f7d  call    cs:__imp_HeapFree
0x1800b8f83  jmp     short loc_1800B8F8D
0x1800b8f85  call    cs:__imp_GetLastError
0x1800b8f8b  mov     ebx, eax
0x1800b8f8d  mov     ecx, ebx; dwErrCode
0x1800b8f8f  call    cs:__imp_SetLastError
0x1800b8f95  xor     eax, eax
0x1800b8f97  test    ebx, ebx
0x1800b8f99  setz    al
0x1800b8f9c  jmp     short loc_1800B8FAB
0x1800b8f9e  mov     ecx, 57h ; 'W'; dwErrCode
0x1800b8fa3  call    cs:__imp_SetLastError
0x1800b8fa9  xor     eax, eax
0x1800b8fab  mov     rbx, [rsp+58h+arg_8]
0x1800b8fb0  mov     rbp, [rsp+58h+arg_10]
0x1800b8fb5  add     rsp, 30h
0x1800b8fb9  pop     r15
0x1800b8fbb  pop     r14
0x1800b8fbd  pop     r13
0x1800b8fbf  pop     rdi
0x1800b8fc0  pop     rsi
0x1800b8fc1  retn
```
