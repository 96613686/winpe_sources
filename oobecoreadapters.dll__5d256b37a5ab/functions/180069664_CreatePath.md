# CreatePath

- ea: `0x180069664`
- end: `0x18006983e`
- name: `CreatePath`
- size: `474`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18006920c`

## callees

- `0x180069550`
- `0x180069664`
- `0x180069a4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800696e7`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800696e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800697eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800697eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800697f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800697f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006973a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006980b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006981f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006973a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006980b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006981f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006970b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800697ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006970b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800697ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069801`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800697a3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800697a3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180069701`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006977b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180069701`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006977b`

## string_xrefs

- `0x180069797`: `CreatePath: Unable to create [%s]; GLE = 0x%x`
- `0x1800697d3`: `CreatePath: Unable to get attributes for [%s]; GLE = 0x%x`
- `0x1800697be`: `CreatePath: Existing path [%s] is not a directory; GLE = 0x%x`
- `0x180069726`: `CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x`
- `0x18006976f`: `CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x`

## pseudocode

```c
_BOOL8 __fastcall CreatePath(const wchar_t *a1)
{
  WCHAR *v2; // rdi
  DWORD v3; // ebx
  int v4; // ebp
  const wchar_t *v5; // rax
  wchar_t *v6; // rax
  DWORD LastError; // eax
  DWORD v8; // eax
  void *v9; // r9
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
          v9 = (void *)a1;
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
0x180069664  mov     r11, rsp
0x180069667  mov     [r11+10h], rbx
0x18006966b  mov     [r11+18h], rbp
0x18006966f  push    rsi
0x180069670  push    rdi
0x180069671  push    r13
0x180069673  push    r14
0x180069675  push    r15
0x180069677  sub     rsp, 30h
0x18006967b  mov     qword ptr [r11+8], 0
0x180069683  mov     rsi, rcx
0x180069686  test    rcx, rcx
0x180069689  jz      loc_18006981A
0x18006968f  xor     eax, eax
0x180069691  cmp     ax, [rcx]
0x180069694  jz      loc_18006981A
0x18006969a  lea     rdx, [r11+8]
0x18006969e  call    PrepareUnicodePathEx
0x1800696a3  mov     rdi, rax
0x1800696a6  test    rax, rax
0x1800696a9  jz      loc_180069801
0x1800696af  mov     rax, [rsp+58h+arg_0]
0x1800696b4  xor     ebx, ebx
0x1800696b6  mov     ebp, 1
0x1800696bb  test    rax, rax
0x1800696be  jz      short loc_1800696C6
0x1800696c0  add     rax, 2
0x1800696c4  jmp     short loc_1800696C9
0x1800696c6  mov     rax, rdi
0x1800696c9  mov     [rsp+58h+arg_0], rax
0x1800696ce  lea     r15, g_WdsLibLog
0x1800696d5  mov     r13d, 5Ch ; '\'
0x1800696db  mov     r14d, 3000000h
0x1800696e1  mov     edx, r13d; Ch
0x1800696e4  mov     rcx, rax; Str
0x1800696e7  call    cs:__imp_wcschr
0x1800696ed  xor     edx, edx; lpSecurityAttributes
0x1800696ef  mov     [rsp+58h+arg_0], rax
0x1800696f4  test    rax, rax
0x1800696f7  jz      short loc_180069778
0x1800696f9  xor     ecx, ecx
0x1800696fb  mov     [rax], cx
0x1800696fe  mov     rcx, rdi; lpPathName
0x180069701  call    cs:__imp_CreateDirectoryW
0x180069707  test    eax, eax
0x180069709  jnz     short loc_180069746
0x18006970b  call    cs:__imp_GetLastError
0x180069711  mov     ebx, eax
0x180069713  cmp     eax, 5
0x180069716  jz      short loc_180069744
0x180069718  cmp     eax, 0B7h
0x18006971d  jz      short loc_180069744
0x18006971f  mov     r9, rdi
0x180069722  mov     dword ptr [rsp+58h+var_38], eax
0x180069726  lea     r8, aCreatepathUnab; "CreatePath: Unable to create intermedia"...
0x18006972d  mov     edx, r14d
0x180069730  mov     rcx, r15
0x180069733  call    LibLog
0x180069738  mov     ecx, ebx; dwErrCode
0x18006973a  call    cs:__imp_SetLastError
0x180069740  xor     ebp, ebp
0x180069742  jmp     short loc_180069746
0x180069744  xor     ebx, ebx
0x180069746  mov     rax, [rsp+58h+arg_0]
0x18006974b  mov     [rax], r13w
0x18006974f  mov     rax, [rsp+58h+arg_0]
0x180069754  add     rax, 2
0x180069758  mov     [rsp+58h+arg_0], rax
0x18006975d  cmp     ebp, 1
0x180069760  jz      loc_1800696E1
0x180069766  call    cs:__imp_GetLastError
0x18006976c  mov     r9, rsi
0x18006976f  lea     r8, aCreatepathUnab_2; "CreatePath: Unable to create parent dir"...
0x180069776  jmp     short loc_1800697DA
0x180069778  mov     rcx, rdi; lpPathName
0x18006977b  call    cs:__imp_CreateDirectoryW
0x180069781  test    eax, eax
0x180069783  jnz     short loc_1800697EB
0x180069785  call    cs:__imp_GetLastError
0x18006978b  mov     ebx, eax
0x18006978d  cmp     eax, 0B7h
0x180069792  jz      short loc_1800697A0
0x180069794  mov     r9, rdi
0x180069797  lea     r8, aCreatepathUnab_1; "CreatePath: Unable to create [%s]; GLE "...
0x18006979e  jmp     short loc_1800697DC
0x1800697a0  mov     rcx, rdi; lpFileName
0x1800697a3  call    cs:__imp_GetFileAttributesW
0x1800697a9  cmp     eax, 0FFFFFFFFh
0x1800697ac  jz      short loc_1800697CA
0x1800697ae  test    al, 10h
0x1800697b0  jz      short loc_1800697B6
0x1800697b2  xor     ebx, ebx
0x1800697b4  jmp     short loc_1800697EB
0x1800697b6  mov     dword ptr [rsp+58h+var_38], 0B7h
0x1800697be  lea     r8, aCreatepathExis; "CreatePath: Existing path [%s] is not a"...
0x1800697c5  mov     r9, rdi
0x1800697c8  jmp     short loc_1800697E0
0x1800697ca  call    cs:__imp_GetLastError
0x1800697d0  mov     r9, rdi
0x1800697d3  lea     r8, aCreatepathUnab_0; "CreatePath: Unable to get attributes fo"...
0x1800697da  mov     ebx, eax
0x1800697dc  mov     dword ptr [rsp+58h+var_38], eax
0x1800697e0  mov     edx, r14d
0x1800697e3  mov     rcx, r15
0x1800697e6  call    LibLog
0x1800697eb  call    cs:__imp_GetProcessHeap
0x1800697f1  mov     r8, rdi; lpMem
0x1800697f4  xor     edx, edx; dwFlags
0x1800697f6  mov     rcx, rax; hHeap
0x1800697f9  call    cs:__imp_HeapFree
0x1800697ff  jmp     short loc_180069809
0x180069801  call    cs:__imp_GetLastError
0x180069807  mov     ebx, eax
0x180069809  mov     ecx, ebx; dwErrCode
0x18006980b  call    cs:__imp_SetLastError
0x180069811  xor     eax, eax
0x180069813  test    ebx, ebx
0x180069815  setz    al
0x180069818  jmp     short loc_180069827
0x18006981a  mov     ecx, 57h ; 'W'; dwErrCode
0x18006981f  call    cs:__imp_SetLastError
0x180069825  xor     eax, eax
0x180069827  mov     rbx, [rsp+58h+arg_8]
0x18006982c  mov     rbp, [rsp+58h+arg_10]
0x180069831  add     rsp, 30h
0x180069835  pop     r15
0x180069837  pop     r14
0x180069839  pop     r13
0x18006983b  pop     rdi
0x18006983c  pop     rsi
0x18006983d  retn
```
