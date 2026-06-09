# CleanDeviceDirectories

- ea: `0x180007c00`
- end: `0x180007de6`
- name: `CleanDeviceDirectories`
- size: `486`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000829c`

## callees

- `0x180007c00`
- `0x1800083ac`
- `0x180008438`
- `0x180008dfe`
- `0x180008e30`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180007caa`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180007db2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180007caa`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180007db2`
- `KERNEL32!FindClose` at `0x180007dbd`
- `KERNEL32!FindClose` at `0x180007dbd`
- `KERNEL32!FindNextFileW` at `0x180007da0`
- `KERNEL32!FindNextFileW` at `0x180007da0`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180007c61`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180007c61`
- `KERNEL32!FindFirstFileW` at `0x180007cbe`
- `KERNEL32!FindFirstFileW` at `0x180007cbe`
- `KERNEL32!GetLastError` at `0x180007c7a`
- `KERNEL32!GetLastError` at `0x180007c7a`
- `SETUPAPI!pSetupStringTableLookUpString` at `0x180007d16`
- `SETUPAPI!pSetupStringTableLookUpString` at `0x180007d16`

## pseudocode

```c
__int64 __fastcall CleanDeviceDirectories(__int64 a1, const WCHAR *a2, __int64 a3)
{
  DWORD v6; // eax
  ULONG v7; // ebx
  NTSTATUS v9; // eax
  HANDLE FirstFileW; // rdi
  NTSTATUS v11; // eax
  int DirectorySize; // eax
  __int64 v13; // rdx
  bool v14; // zf
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rcx
  __int64 v17; // rdx
  int v18; // ecx
  unsigned int v19; // eax
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR Dst[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v21 = 0;
  v6 = ExpandEnvironmentStringsW(a2, Dst, 0x104u);
  if ( v6 > 0x104 )
    return 1359;
  if ( !v6 )
    return GetLastError();
  v9 = RtlStringCchPrintfW(FileName, 260, L"%s\\*", Dst);
  if ( v9 < 0 )
    return RtlNtStatusToDosErrorNoTeb(v9);
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    return GetLastError();
  v7 = 0;
  while ( (FindFileData.dwFileAttributes & 0x10) == 0
       || FindFileData.cFileName[0] == 46
       && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2])
       || (unsigned int)pSetupStringTableLookUpString(a3, FindFileData.cFileName, 0) != -1 )
  {
LABEL_24:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_27;
  }
  v11 = RtlStringCchPrintfW(FileName, 260, L"%s\\%s\\", Dst, FindFileData.cFileName);
  if ( v11 >= 0 )
  {
    DirectorySize = pUtilGetDirectorySize(FileName, *(unsigned int *)(a1 + 80), &v21);
    v13 = v21;
    v14 = DirectorySize == 0;
    v15 = *(_QWORD *)(a1 + 72);
    if ( !v14 )
      v13 = 0;
    v21 = v13;
    v16 = v15 + v13;
    v17 = -1;
    if ( v16 >= v15 )
      v17 = v16;
    v18 = -1;
    *(_QWORD *)(a1 + 72) = v17;
    v19 = *(_DWORD *)(a1 + 64);
    if ( v19 + 1 >= v19 )
      v18 = v19 + 1;
    *(_DWORD *)(a1 + 64) = v18;
    goto LABEL_24;
  }
  v7 = RtlNtStatusToDosErrorNoTeb(v11);
LABEL_27:
  FindClose(FirstFileW);
  return v7;
}

```

## disassembly

```asm
0x180007c00  push    rbp
0x180007c02  push    rbx
0x180007c03  push    rsi
0x180007c04  push    rdi
0x180007c05  push    r12
0x180007c07  push    r14
0x180007c09  push    r15
0x180007c0b  lea     rbp, [rsp-5C0h]
0x180007c13  sub     rsp, 6C0h
0x180007c1a  mov     rax, cs:__security_cookie
0x180007c21  xor     rax, rsp
0x180007c24  mov     [rbp+5F0h+var_40], rax
0x180007c2b  mov     r14, r8
0x180007c2e  mov     rbx, rdx
0x180007c31  mov     rsi, rcx
0x180007c34  xor     edx, edx; Val
0x180007c36  mov     r8d, 250h; Size
0x180007c3c  lea     rcx, [rsp+6F0h+FindFileData]; void *
0x180007c41  call    memset_0
0x180007c46  mov     r12d, 104h
0x180007c4c  lea     rdx, [rbp+5F0h+Dst]; lpDst
0x180007c53  xor     r15d, r15d
0x180007c56  mov     r8d, r12d; nSize
0x180007c59  mov     rcx, rbx; lpSrc
0x180007c5c  mov     [rsp+6F0h+var_6C0], r15
0x180007c61  call    cs:__imp_ExpandEnvironmentStringsW
0x180007c67  cmp     eax, r12d
0x180007c6a  jbe     short loc_180007C76
0x180007c6c  mov     ebx, 54Fh
0x180007c71  jmp     loc_180007DC3
0x180007c76  test    eax, eax
0x180007c78  jnz     short loc_180007C87
0x180007c7a  call    cs:__imp_GetLastError
0x180007c80  mov     ebx, eax
0x180007c82  jmp     loc_180007DC3
0x180007c87  lea     r9, [rbp+5F0h+Dst]
0x180007c8e  mov     rdx, r12
0x180007c91  lea     r8, aS; "%s\\*"
0x180007c98  lea     rcx, [rbp+5F0h+FileName]
0x180007c9f  call    RtlStringCchPrintfW
0x180007ca4  test    eax, eax
0x180007ca6  jns     short loc_180007CB2
0x180007ca8  mov     ecx, eax; Status
0x180007caa  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180007cb0  jmp     short loc_180007C80
0x180007cb2  lea     rdx, [rsp+6F0h+FindFileData]; lpFindFileData
0x180007cb7  lea     rcx, [rbp+5F0h+FileName]; lpFileName
0x180007cbe  call    cs:__imp_FindFirstFileW
0x180007cc4  mov     rdi, rax
0x180007cc7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007ccb  jz      short loc_180007C7A
0x180007ccd  mov     ebx, r15d
0x180007cd0  test    byte ptr [rsp+6F0h+FindFileData.dwFileAttributes], 10h
0x180007cd5  jz      loc_180007D98
0x180007cdb  cmp     [rsp+6F0h+FindFileData.cFileName], 2Eh ; '.'
0x180007ce1  movzx   eax, [rsp+6F0h+FindFileData.cFileName+2]
0x180007ce6  jnz     short loc_180007D0B
0x180007ce8  test    ax, ax
0x180007ceb  jz      loc_180007D98
0x180007cf1  cmp     [rsp+6F0h+FindFileData.cFileName], 2Eh ; '.'
0x180007cf7  jnz     short loc_180007D0B
0x180007cf9  cmp     ax, 2Eh ; '.'
0x180007cfd  jnz     short loc_180007D0B
0x180007cff  cmp     [rsp+6F0h+FindFileData.cFileName+4], r15w
0x180007d05  jz      loc_180007D98
0x180007d0b  xor     r8d, r8d
0x180007d0e  lea     rdx, [rsp+6F0h+FindFileData.cFileName]
0x180007d13  mov     rcx, r14
0x180007d16  call    cs:__imp_pSetupStringTableLookUpString
0x180007d1c  cmp     eax, 0FFFFFFFFh
0x180007d1f  jnz     short loc_180007D98
0x180007d21  lea     rax, [rsp+6F0h+FindFileData.cFileName]
0x180007d26  mov     rdx, r12
0x180007d29  lea     r9, [rbp+5F0h+Dst]
0x180007d30  mov     [rsp+6F0h+var_6D0], rax
0x180007d35  lea     r8, aSS; "%s\\%s\\"
0x180007d3c  lea     rcx, [rbp+5F0h+FileName]
0x180007d43  call    RtlStringCchPrintfW
0x180007d48  test    eax, eax
0x180007d4a  js      short loc_180007DB0
0x180007d4c  mov     edx, [rsi+50h]
0x180007d4f  lea     r8, [rsp+6F0h+var_6C0]
0x180007d54  lea     rcx, [rbp+5F0h+FileName]
0x180007d5b  call    pUtilGetDirectorySize
0x180007d60  mov     rdx, [rsp+6F0h+var_6C0]
0x180007d65  test    eax, eax
0x180007d67  mov     rax, [rsi+48h]
0x180007d6b  cmovnz  rdx, r15
0x180007d6f  mov     [rsp+6F0h+var_6C0], rdx
0x180007d74  lea     rcx, [rax+rdx]
0x180007d78  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180007d7c  cmp     rcx, rax
0x180007d7f  cmovnb  rdx, rcx
0x180007d83  or      ecx, 0FFFFFFFFh
0x180007d86  mov     [rsi+48h], rdx
0x180007d8a  mov     eax, [rsi+40h]
0x180007d8d  lea     edx, [rax+1]
0x180007d90  cmp     edx, eax
0x180007d92  cmovnb  ecx, edx
0x180007d95  mov     [rsi+40h], ecx
0x180007d98  lea     rdx, [rsp+6F0h+FindFileData]; lpFindFileData
0x180007d9d  mov     rcx, rdi; hFindFile
0x180007da0  call    cs:__imp_FindNextFileW
0x180007da6  test    eax, eax
0x180007da8  jnz     loc_180007CD0
0x180007dae  jmp     short loc_180007DBA
0x180007db0  mov     ecx, eax; Status
0x180007db2  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180007db8  mov     ebx, eax
0x180007dba  mov     rcx, rdi; hFindFile
0x180007dbd  call    cs:__imp_FindClose
0x180007dc3  mov     eax, ebx
0x180007dc5  mov     rcx, [rbp+5F0h+var_40]
0x180007dcc  xor     rcx, rsp; StackCookie
0x180007dcf  call    __security_check_cookie
0x180007dd4  add     rsp, 6C0h
0x180007ddb  pop     r15
0x180007ddd  pop     r14
0x180007ddf  pop     r12
0x180007de1  pop     rdi
0x180007de2  pop     rsi
0x180007de3  pop     rbx
0x180007de4  pop     rbp
0x180007de5  retn
```
