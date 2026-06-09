# FwGetSysPathName

- ea: `0x180007180`
- end: `0x1800072c0`
- name: `FwGetSysPathName`
- size: `320`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callees

- `0x180002b30`
- `0x180004750`
- `0x1800047e0`
- `0x180004840`
- `0x1800048c0`
- `0x180007010`
- `0x180007180`
- `0x1800205fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000720d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000720d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800071fe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800071fe`

## string_xrefs

- `0x1800071b6`: `FwGetSysPathName`
- `0x180007213`: `CreateFileW`

## pseudocode

```c
__int64 __fastcall FwGetSysPathName(__int64 a1, _QWORD *a2)
{
  wchar_t *v2; // rdi
  __int64 v4; // rsi
  int ExpandedCanonicalLongPathName; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  int ObjectName; // eax
  int v12; // [rsp+78h] [rbp+10h] BYREF
  wchar_t *String2; // [rsp+80h] [rbp+18h]
  LPCWSTR lpFileName; // [rsp+88h] [rbp+20h] BYREF

  v2 = 0;
  lpFileName = 0;
  *a2 = 0;
  String2 = 0;
  v12 = 0;
  v4 = -1;
  ExpandedCanonicalLongPathName = FwGetExpandedCanonicalLongPathName(a1, &lpFileName, &v12);
  v6 = ExpandedCanonicalLongPathName;
  if ( ExpandedCanonicalLongPathName >= 0 )
  {
    if ( v12 )
    {
      FileW = CreateFileW(lpFileName, 0x80u, 0, 0, 3u, 0x80u, 0);
      v4 = (__int64)FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v6 = FwReportErrorAsWinError("FwGetSysPathName", "CreateFileW", LastError);
        goto LABEL_14;
      }
      ObjectName = FwQueryObjectName(FileW);
      v6 = ObjectName;
      if ( ObjectName < 0 )
      {
        FwReportReturnError("FwGetSysPathName", (unsigned int)ObjectName);
        v2 = String2;
        goto LABEL_14;
      }
      v2 = String2;
      ExpandedCanonicalLongPathName = FwSubstituteDeviceName(String2, a2);
      v6 = ExpandedCanonicalLongPathName;
      if ( ExpandedCanonicalLongPathName < 0 )
        goto LABEL_2;
      if ( *a2 )
        goto LABEL_14;
      v6 = -2147467261;
    }
    else
    {
      v6 = -2147024894;
    }
    v7 = v6;
    goto LABEL_13;
  }
LABEL_2:
  v7 = (unsigned int)ExpandedCanonicalLongPathName;
LABEL_13:
  FwReportReturnError("FwGetSysPathName", v7);
LABEL_14:
  FwFree(v2);
  FwCloseHandle(v4);
  FwFree(lpFileName);
  if ( (v6 & 0x80000000) != 0 )
    return (unsigned int)FwReportReturnError("FwGetSysPathName", v6);
  return v6;
}

```

## disassembly

```asm
0x180007180  mov     rax, rsp
0x180007183  push    rbx
0x180007184  push    rsi
0x180007185  push    rdi
0x180007186  push    r14
0x180007188  push    r15
0x18000718a  sub     rsp, 40h
0x18000718e  xor     edi, edi
0x180007190  mov     qword ptr [rax+20h], 0
0x180007198  mov     [rdx], rdi
0x18000719b  lea     r8, [rax+10h]
0x18000719f  mov     r14, rdx
0x1800071a2  mov     [rax+18h], rdi
0x1800071a6  lea     rdx, [rax+20h]
0x1800071aa  mov     [rax+10h], edi
0x1800071ad  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800071b1  call    FwGetExpandedCanonicalLongPathName
0x1800071b6  lea     r15, aFwgetsyspathna_0; "FwGetSysPathName"
0x1800071bd  mov     ebx, eax
0x1800071bf  test    eax, eax
0x1800071c1  jns     short loc_1800071CA
0x1800071c3  mov     edx, eax
0x1800071c5  jmp     loc_18000727D
0x1800071ca  cmp     [rsp+68h+arg_8], edi
0x1800071ce  jnz     short loc_1800071DA
0x1800071d0  mov     ebx, 80070002h
0x1800071d5  jmp     loc_18000727B
0x1800071da  mov     rcx, [rsp+68h+lpFileName]; lpFileName
0x1800071e2  mov     edx, 80h; dwDesiredAccess
0x1800071e7  mov     [rsp+68h+hTemplateFile], rdi; hTemplateFile
0x1800071ec  xor     r9d, r9d; lpSecurityAttributes
0x1800071ef  mov     [rsp+68h+dwFlagsAndAttributes], edx; dwFlagsAndAttributes
0x1800071f3  xor     r8d, r8d; dwShareMode
0x1800071f6  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800071fe  call    cs:__imp_CreateFileW
0x180007204  mov     rsi, rax
0x180007207  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000720b  jnz     short loc_180007229
0x18000720d  call    cs:__imp_GetLastError
0x180007213  lea     rdx, aCreatefilew; "CreateFileW"
0x18000721a  mov     rcx, r15
0x18000721d  mov     r8d, eax
0x180007220  call    FwReportErrorAsWinError
0x180007225  mov     ebx, eax
0x180007227  jmp     short loc_180007285
0x180007229  lea     rdx, [rsp+68h+String2]
0x180007231  mov     rcx, rax; Handle
0x180007234  call    FwQueryObjectName
0x180007239  mov     ebx, eax
0x18000723b  test    eax, eax
0x18000723d  jns     short loc_180007253
0x18000723f  mov     edx, eax
0x180007241  mov     rcx, r15
0x180007244  call    FwReportReturnError
0x180007249  mov     rdi, [rsp+68h+String2]
0x180007251  jmp     short loc_180007285
0x180007253  mov     rdi, [rsp+68h+String2]
0x18000725b  mov     rdx, r14
0x18000725e  mov     rcx, rdi; String2
0x180007261  call    FwSubstituteDeviceName
0x180007266  mov     ebx, eax
0x180007268  test    eax, eax
0x18000726a  js      loc_1800071C3
0x180007270  cmp     qword ptr [r14], 0
0x180007274  jnz     short loc_180007285
0x180007276  mov     ebx, 80004003h
0x18000727b  mov     edx, ebx
0x18000727d  mov     rcx, r15
0x180007280  call    FwReportReturnError
0x180007285  mov     rcx, rdi
0x180007288  call    FwFree
0x18000728d  mov     rcx, rsi
0x180007290  call    FwCloseHandle
0x180007295  mov     rcx, [rsp+68h+lpFileName]
0x18000729d  call    FwFree
0x1800072a2  test    ebx, ebx
0x1800072a4  jns     short loc_1800072B2
0x1800072a6  mov     edx, ebx
0x1800072a8  mov     rcx, r15
0x1800072ab  call    FwReportReturnError
0x1800072b0  mov     ebx, eax
0x1800072b2  mov     eax, ebx
0x1800072b4  add     rsp, 40h
0x1800072b8  pop     r15
0x1800072ba  pop     r14
0x1800072bc  pop     rdi
0x1800072bd  pop     rsi
0x1800072be  pop     rbx
0x1800072bf  retn
```
