# IsInternalPackage(void)

- ea: `0x18009428c`
- end: `0x18009445f`
- name: `?IsInternalPackage@@YAHXZ`
- size: `467`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800c0a28`
- `0x1800caff0`
- `0x1801ae2b4`
- `0x1802810d4`
- `0x18038a39c`

## callees

- `0x18009428c`
- `0x1800ccda0`
- `0x1800f0f40`
- `0x1804da880`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_strnicmp` at `0x1800943f2`
- `api-ms-win-crt-string-l1-1-0!_strnicmp` at `0x1800943f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094424`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009440c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009440c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800943c9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800943c9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009438e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009438e`

## pseudocode

```c
_BOOL8 IsInternalPackage(void)
{
  bool v0; // zf
  __int64 v2; // rdi
  unsigned int i; // eax
  unsigned int v4; // ebx
  unsigned int v5; // esi
  char *FileW; // rax
  void *v7; // rbx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  int v9; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR *v10; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v11[3]; // [rsp+58h] [rbp-A8h] BYREF
  char Buffer[64]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR FileName[264]; // [rsp+B0h] [rbp-50h] BYREF

  NumberOfBytesRead = 0;
  v0 = dword_1807BEE08 == 0;
  if ( dword_1807BEE08 >= 0 )
    return v0;
  v10 = FileName;
  v9 = 260;
  v11[0] = &v9;
  v11[1] = &v10;
  if ( (int)Debugger::Utils::ConvertException__lambda_e72a00969fef81751b4ee47ab217f8cc___(v11) >= 0 )
  {
    v2 = -1;
    do
      ++v2;
    while ( FileName[v2] );
    if ( (unsigned int)v2 < 0x104 )
    {
      v4 = 260 - v2;
      v5 = 17;
      if ( (unsigned int)(260 - v2) <= 0x11 )
        v5 = v4 - 1;
      memmove(&FileName[(unsigned int)v2], L"\\winxp\\triage.ini", 2LL * v5);
      FileName[v5 + (unsigned int)v2] = 0;
      if ( v4 > 0x11 )
      {
        FileW = (char *)CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
        v7 = FileW;
        if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          dword_1807BEE08 = 1;
          if ( ReadFile(FileW, Buffer, 0x40u, &NumberOfBytesRead, 0)
            && NumberOfBytesRead > 0x11
            && !_strnicmp(Buffer, ";internal_package", 0x11u) )
          {
            dword_1807BEE08 = 0;
          }
          CloseHandle(v7);
          return dword_1807BEE08 == 0;
        }
        if ( GetLastError() == 2 )
          dword_1807BEE08 = 1;
      }
    }
    else
    {
      for ( i = 0; i < 7; ++i )
        ;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18009428c  push    rbp
0x18009428e  push    rbx
0x18009428f  push    rsi
0x180094290  push    rdi
0x180094291  push    r14
0x180094293  lea     rbp, [rsp-1D0h]
0x18009429b  sub     rsp, 2D0h
0x1800942a2  mov     rax, cs:__security_cookie
0x1800942a9  xor     rax, rsp
0x1800942ac  mov     [rbp+1F0h+var_30], rax
0x1800942b3  mov     ecx, cs:dword_1807BEE08
0x1800942b9  xor     r14d, r14d
0x1800942bc  mov     [rsp+2F0h+NumberOfBytesRead], r14d
0x1800942c1  test    ecx, ecx
0x1800942c3  js      short loc_1800942D0
0x1800942c5  mov     eax, r14d
0x1800942c8  setz    al
0x1800942cb  jmp     loc_180094441
0x1800942d0  lea     rax, [rbp+1F0h+FileName]
0x1800942d4  mov     ebx, 104h
0x1800942d9  mov     [rsp+2F0h+var_2A0], rax
0x1800942de  lea     rcx, [rsp+2F0h+var_298]
0x1800942e3  lea     rax, [rsp+2F0h+var_2A8]
0x1800942e8  mov     [rsp+2F0h+var_2A8], ebx
0x1800942ec  mov     [rsp+2F0h+var_298], rax
0x1800942f1  lea     rax, [rsp+2F0h+var_2A0]
0x1800942f6  mov     [rsp+2F0h+var_290], rax
0x1800942fb  call    Debugger__Utils__ConvertException__lambda_e72a00969fef81751b4ee47ab217f8cc___
0x180094300  test    eax, eax
0x180094302  js      loc_18009443F
0x180094308  lea     rax, [rbp+1F0h+FileName]
0x18009430c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180094310  inc     rdi
0x180094313  cmp     [rax+rdi*2], r14w
0x180094318  jnz     short loc_180094310
0x18009431a  cmp     edi, ebx
0x18009431c  jb      short loc_18009432D
0x18009431e  mov     eax, r14d
0x180094321  inc     eax
0x180094323  cmp     eax, 7
0x180094326  jb      short loc_180094321
0x180094328  jmp     loc_18009443F
0x18009432d  sub     ebx, edi
0x18009432f  mov     esi, 11h
0x180094334  cmp     ebx, esi
0x180094336  ja      short loc_18009433B
0x180094338  lea     esi, [rbx-1]
0x18009433b  mov     eax, edi
0x18009433d  lea     rcx, [rbp+1F0h+FileName]
0x180094341  mov     r8d, esi
0x180094344  lea     rdx, aWinxpTriageIni; "\\winxp\\triage.ini"
0x18009434b  add     r8, r8; Size
0x18009434e  lea     rcx, [rcx+rax*2]; void *
0x180094352  call    memmove
0x180094357  lea     eax, [rsi+rdi]
0x18009435a  mov     [rbp+rax*2+1F0h+FileName], r14w
0x180094360  cmp     ebx, 11h
0x180094363  jbe     loc_18009443F
0x180094369  xor     r9d, r9d; lpSecurityAttributes
0x18009436c  mov     [rsp+2F0h+hTemplateFile], r14; hTemplateFile
0x180094371  mov     [rsp+2F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180094379  lea     rcx, [rbp+1F0h+FileName]; lpFileName
0x18009437d  mov     edx, 80000000h; dwDesiredAccess
0x180094382  mov     [rsp+2F0h+dwCreationDisposition], 3; dwCreationDisposition
0x18009438a  lea     r8d, [r9+1]; dwShareMode
0x18009438e  call    cs:__imp_CreateFileW
0x180094395  nop     dword ptr [rax+rax+00h]
0x18009439a  mov     rbx, rax
0x18009439d  lea     rcx, [rax-1]
0x1800943a1  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800943a5  ja      short loc_180094424
0x1800943a7  lea     r9, [rsp+2F0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800943ac  mov     cs:dword_1807BEE08, 1
0x1800943b6  mov     r8d, 40h ; '@'; nNumberOfBytesToRead
0x1800943bc  mov     qword ptr [rsp+2F0h+dwCreationDisposition], r14; lpOverlapped
0x1800943c1  lea     rdx, [rsp+2F0h+Buffer]; lpBuffer
0x1800943c6  mov     rcx, rax; hFile
0x1800943c9  call    cs:__imp_ReadFile
0x1800943d0  nop     dword ptr [rax+rax+00h]
0x1800943d5  test    eax, eax
0x1800943d7  jz      short loc_180094409
0x1800943d9  cmp     [rsp+2F0h+NumberOfBytesRead], 11h
0x1800943de  jbe     short loc_180094409
0x1800943e0  mov     r8d, 11h; MaxCount
0x1800943e6  lea     rdx, aInternalPackag; ";internal_package"
0x1800943ed  lea     rcx, [rsp+2F0h+Buffer]; String1
0x1800943f2  call    cs:__imp__strnicmp
0x1800943f9  nop     dword ptr [rax+rax+00h]
0x1800943fe  test    eax, eax
0x180094400  jnz     short loc_180094409
0x180094402  mov     cs:dword_1807BEE08, r14d
0x180094409  mov     rcx, rbx; hObject
0x18009440c  call    cs:__imp_CloseHandle
0x180094413  nop     dword ptr [rax+rax+00h]
0x180094418  cmp     cs:dword_1807BEE08, r14d
0x18009441f  jmp     loc_1800942C5
0x180094424  call    cs:__imp_GetLastError
0x18009442b  nop     dword ptr [rax+rax+00h]
0x180094430  cmp     eax, 2
0x180094433  jnz     short loc_18009443F
0x180094435  mov     cs:dword_1807BEE08, 1
0x18009443f  xor     eax, eax
0x180094441  mov     rcx, [rbp+1F0h+var_30]
0x180094448  xor     rcx, rsp; StackCookie
0x18009444b  call    __security_check_cookie
0x180094450  add     rsp, 2D0h
0x180094457  pop     r14
0x180094459  pop     rdi
0x18009445a  pop     rsi
0x18009445b  pop     rbx
0x18009445c  pop     rbp
0x18009445d  retn
```
