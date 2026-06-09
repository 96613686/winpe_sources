# CreatePath

- ea: `0x14005dbd0`
- end: `0x14005de03`
- name: `CreatePath`
- size: `563`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140031250`
- `0x140031560`

## callees

- `0x14005dbd0`
- `0x14005dee4`
- `0x14005e1a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14005dc53`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14005dc53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14005dd91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14005dd91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005dda5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005dda5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005dc87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005dcee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005dd19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005dd6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ddb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005dc87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005dcee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005dd19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005dd6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ddb3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005dcbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005ddc3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005dddd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005dcbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005ddc3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005dddd`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14005dc77`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14005dd09`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14005dc77`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14005dd09`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14005dd3d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14005dd3d`

## string_xrefs

- `0x14005dca8`: `CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x`
- `0x14005dd79`: `CreatePath: Unable to get attributes for [%s]; GLE = 0x%x`
- `0x14005dd5e`: `CreatePath: Existing path [%s] is not a directory; GLE = 0x%x`
- `0x14005dcfd`: `CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x`
- `0x14005dd31`: `CreatePath: Unable to create [%s]; GLE = 0x%x`

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
0x14005dbd0  mov     r11, rsp
0x14005dbd3  mov     [r11+10h], rbx
0x14005dbd7  mov     [r11+18h], rbp
0x14005dbdb  push    rsi
0x14005dbdc  push    rdi
0x14005dbdd  push    r13
0x14005dbdf  push    r14
0x14005dbe1  push    r15
0x14005dbe3  sub     rsp, 30h
0x14005dbe7  mov     qword ptr [r11+8], 0
0x14005dbef  mov     rsi, rcx
0x14005dbf2  test    rcx, rcx
0x14005dbf5  jz      loc_14005DDD8
0x14005dbfb  xor     eax, eax
0x14005dbfd  cmp     ax, [rcx]
0x14005dc00  jz      loc_14005DDD8
0x14005dc06  lea     rdx, [r11+8]
0x14005dc0a  call    PrepareUnicodePathEx
0x14005dc0f  mov     rdi, rax
0x14005dc12  test    rax, rax
0x14005dc15  jz      loc_14005DDB3
0x14005dc1b  mov     rax, [rsp+58h+arg_0]
0x14005dc20  xor     ebx, ebx
0x14005dc22  mov     ebp, 1
0x14005dc27  test    rax, rax
0x14005dc2a  jz      short loc_14005DC32
0x14005dc2c  add     rax, 2
0x14005dc30  jmp     short loc_14005DC35
0x14005dc32  mov     rax, rdi
0x14005dc35  mov     [rsp+58h+arg_0], rax
0x14005dc3a  lea     r15, g_WdsLibLog
0x14005dc41  mov     r13d, 5Ch ; '\'
0x14005dc47  mov     r14d, 3000000h
0x14005dc4d  mov     edx, r13d; Ch
0x14005dc50  mov     rcx, rax; Str
0x14005dc53  call    cs:__imp_wcschr
0x14005dc5a  nop     dword ptr [rax+rax+00h]
0x14005dc5f  xor     edx, edx; lpSecurityAttributes
0x14005dc61  mov     [rsp+58h+arg_0], rax
0x14005dc66  test    rax, rax
0x14005dc69  jz      loc_14005DD06
0x14005dc6f  xor     ecx, ecx
0x14005dc71  mov     [rax], cx
0x14005dc74  mov     rcx, rdi; lpPathName
0x14005dc77  call    cs:__imp_CreateDirectoryW
0x14005dc7e  nop     dword ptr [rax+rax+00h]
0x14005dc83  test    eax, eax
0x14005dc85  jnz     short loc_14005DCCE
0x14005dc87  call    cs:__imp_GetLastError
0x14005dc8e  nop     dword ptr [rax+rax+00h]
0x14005dc93  mov     ebx, eax
0x14005dc95  cmp     eax, 5
0x14005dc98  jz      short loc_14005DCCC
0x14005dc9a  cmp     eax, 0B7h
0x14005dc9f  jz      short loc_14005DCCC
0x14005dca1  mov     r9, rdi
0x14005dca4  mov     dword ptr [rsp+58h+var_38], eax
0x14005dca8  lea     r8, aCreatepathUnab; "CreatePath: Unable to create intermedia"...
0x14005dcaf  mov     edx, r14d
0x14005dcb2  mov     rcx, r15
0x14005dcb5  call    LibLog
0x14005dcba  mov     ecx, ebx; dwErrCode
0x14005dcbc  call    cs:__imp_SetLastError
0x14005dcc3  nop     dword ptr [rax+rax+00h]
0x14005dcc8  xor     ebp, ebp
0x14005dcca  jmp     short loc_14005DCCE
0x14005dccc  xor     ebx, ebx
0x14005dcce  mov     rax, [rsp+58h+arg_0]
0x14005dcd3  mov     [rax], r13w
0x14005dcd7  mov     rax, [rsp+58h+arg_0]
0x14005dcdc  add     rax, 2
0x14005dce0  mov     [rsp+58h+arg_0], rax
0x14005dce5  cmp     ebp, 1
0x14005dce8  jz      loc_14005DC4D
0x14005dcee  call    cs:__imp_GetLastError
0x14005dcf5  nop     dword ptr [rax+rax+00h]
0x14005dcfa  mov     r9, rsi
0x14005dcfd  lea     r8, aCreatepathUnab_2; "CreatePath: Unable to create parent dir"...
0x14005dd04  jmp     short loc_14005DD80
0x14005dd06  mov     rcx, rdi; lpPathName
0x14005dd09  call    cs:__imp_CreateDirectoryW
0x14005dd10  nop     dword ptr [rax+rax+00h]
0x14005dd15  test    eax, eax
0x14005dd17  jnz     short loc_14005DD91
0x14005dd19  call    cs:__imp_GetLastError
0x14005dd20  nop     dword ptr [rax+rax+00h]
0x14005dd25  mov     ebx, eax
0x14005dd27  cmp     eax, 0B7h
0x14005dd2c  jz      short loc_14005DD3A
0x14005dd2e  mov     r9, rdi
0x14005dd31  lea     r8, aCreatepathUnab_1; "CreatePath: Unable to create [%s]; GLE "...
0x14005dd38  jmp     short loc_14005DD82
0x14005dd3a  mov     rcx, rdi; lpFileName
0x14005dd3d  call    cs:__imp_GetFileAttributesW
0x14005dd44  nop     dword ptr [rax+rax+00h]
0x14005dd49  cmp     eax, 0FFFFFFFFh
0x14005dd4c  jz      short loc_14005DD6A
0x14005dd4e  test    al, 10h
0x14005dd50  jz      short loc_14005DD56
0x14005dd52  xor     ebx, ebx
0x14005dd54  jmp     short loc_14005DD91
0x14005dd56  mov     dword ptr [rsp+58h+var_38], 0B7h
0x14005dd5e  lea     r8, aCreatepathExis; "CreatePath: Existing path [%s] is not a"...
0x14005dd65  mov     r9, rdi
0x14005dd68  jmp     short loc_14005DD86
0x14005dd6a  call    cs:__imp_GetLastError
0x14005dd71  nop     dword ptr [rax+rax+00h]
0x14005dd76  mov     r9, rdi
0x14005dd79  lea     r8, aCreatepathUnab_0; "CreatePath: Unable to get attributes fo"...
0x14005dd80  mov     ebx, eax
0x14005dd82  mov     dword ptr [rsp+58h+var_38], eax
0x14005dd86  mov     edx, r14d
0x14005dd89  mov     rcx, r15
0x14005dd8c  call    LibLog
0x14005dd91  call    cs:__imp_GetProcessHeap
0x14005dd98  nop     dword ptr [rax+rax+00h]
0x14005dd9d  mov     r8, rdi; lpMem
0x14005dda0  xor     edx, edx; dwFlags
0x14005dda2  mov     rcx, rax; hHeap
0x14005dda5  call    cs:__imp_HeapFree
0x14005ddac  nop     dword ptr [rax+rax+00h]
0x14005ddb1  jmp     short loc_14005DDC1
0x14005ddb3  call    cs:__imp_GetLastError
0x14005ddba  nop     dword ptr [rax+rax+00h]
0x14005ddbf  mov     ebx, eax
0x14005ddc1  mov     ecx, ebx; dwErrCode
0x14005ddc3  call    cs:__imp_SetLastError
0x14005ddca  nop     dword ptr [rax+rax+00h]
0x14005ddcf  xor     eax, eax
0x14005ddd1  test    ebx, ebx
0x14005ddd3  setz    al
0x14005ddd6  jmp     short loc_14005DDEB
0x14005ddd8  mov     ecx, 57h ; 'W'; dwErrCode
0x14005dddd  call    cs:__imp_SetLastError
0x14005dde4  nop     dword ptr [rax+rax+00h]
0x14005dde9  xor     eax, eax
0x14005ddeb  mov     rbx, [rsp+58h+arg_8]
0x14005ddf0  mov     rbp, [rsp+58h+arg_10]
0x14005ddf5  add     rsp, 30h
0x14005ddf9  pop     r15
0x14005ddfb  pop     r14
0x14005ddfd  pop     r13
0x14005ddff  pop     rdi
0x14005de00  pop     rsi
0x14005de01  retn
```
