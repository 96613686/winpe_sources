# RealtimeProtection::DlpUtils::DeleteEmptyOutputFile(wchar_t const *)

- ea: `0x18014e01c`
- end: `0x18014e268`
- name: `?DeleteEmptyOutputFile@DlpUtils@RealtimeProtection@@YAJPEB_W@Z`
- size: `588`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18019cbe0`

## callees

- `0x180080030`
- `0x1800809d0`
- `0x180105f50`
- `0x18010cb40`
- `0x18014e01c`
- `0x18014f16c`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x18014e0a4`
- `KERNEL32!GetFileSizeEx` at `0x18014e0a4`
- `KERNEL32!DeleteFileW` at `0x18014e1d1`
- `KERNEL32!DeleteFileW` at `0x18014e1d1`
- `KERNEL32!CreateFileW` at `0x18014e073`
- `KERNEL32!CreateFileW` at `0x18014e073`
- `KERNEL32!CloseHandle` at `0x18014e118`
- `KERNEL32!CloseHandle` at `0x18014e1c1`
- `KERNEL32!CloseHandle` at `0x18014e23d`
- `KERNEL32!CloseHandle` at `0x18014e118`
- `KERNEL32!CloseHandle` at `0x18014e1c1`
- `KERNEL32!CloseHandle` at `0x18014e23d`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpUtils::DeleteEmptyOutputFile(LPCWSTR lpFileName, const wchar_t *a2)
{
  __int64 v3; // rbx
  HANDLE FileW; // rax
  int LastFailure; // esi
  PVOID *v6; // r10
  PVOID v7; // rcx
  __int64 v8; // rdx
  PVOID *v9; // rcx
  PVOID *v11; // rcx
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-28h] BYREF

  if ( !lpFileName )
    return 0;
  v3 = -1;
  FileW = CreateFileW(lpFileName, 0x80u, 7u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastFailure = HrGetLastFailure();
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_e6a39d1dc444391637ddeaca3af09117_Traceguids, lpFileName);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( LastFailure < 0 )
    {
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
        WPP_SF_d(v9[2], 46, &WPP_e6a39d1dc444391637ddeaca3af09117_Traceguids, (unsigned int)LastFailure);
      return (unsigned int)LastFailure;
    }
  }
  else
  {
    v3 = (__int64)FileW;
  }
  FileSize.QuadPart = 0;
  if ( GetFileSizeEx((HANDLE)v3, &FileSize) )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    LastFailure = HrGetLastFailure();
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_e6a39d1dc444391637ddeaca3af09117_Traceguids, lpFileName);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( LastFailure < 0 )
    {
      if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 1) == 0 )
        goto LABEL_13;
      v7 = v6[2];
      v8 = 48;
LABEL_12:
      WPP_SF_d(v7, v8, &WPP_e6a39d1dc444391637ddeaca3af09117_Traceguids, (unsigned int)LastFailure);
LABEL_13:
      if ( v3 != -1 )
        CloseHandle((HANDLE)v3);
      return (unsigned int)LastFailure;
    }
  }
  if ( FileSize.QuadPart <= 0 )
  {
    if ( !DeleteFileW(lpFileName) )
    {
      LastFailure = HrGetLastFailure();
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_e6a39d1dc444391637ddeaca3af09117_Traceguids, lpFileName);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( LastFailure < 0 )
      {
        if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
          goto LABEL_13;
        v7 = v11[2];
        v8 = 51;
        goto LABEL_12;
      }
    }
    if ( v3 != -1 )
      CloseHandle((HANDLE)v3);
    return 0;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
    WPP_SF_SI(
      (unsigned int)v6[2],
      49,
      (unsigned int)&WPP_e6a39d1dc444391637ddeaca3af09117_Traceguids,
      (_DWORD)lpFileName,
      FileSize.QuadPart);
  if ( v3 != -1 )
    CloseHandle((HANDLE)v3);
  return 1;
}

```

## disassembly

```asm
0x18014e01c  mov     [rsp+arg_8], rbx
0x18014e021  mov     [rsp+arg_10], rsi
0x18014e026  push    rdi
0x18014e027  push    r13
0x18014e029  push    r15
0x18014e02b  sub     rsp, 50h
0x18014e02f  mov     rax, cs:__security_cookie
0x18014e036  xor     rax, rsp
0x18014e039  mov     [rsp+68h+var_20], rax
0x18014e03e  mov     rdi, rcx
0x18014e041  test    rcx, rcx
0x18014e044  jz      loc_18014E243
0x18014e04a  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18014e053  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18014e057  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18014e05f  xor     r9d, r9d; lpSecurityAttributes
0x18014e062  mov     edx, 80h; dwDesiredAccess
0x18014e067  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18014e06f  lea     r8d, [rbx+8]; dwShareMode
0x18014e073  call    cs:__imp_CreateFileW
0x18014e079  lea     r15, WPP_GLOBAL_Control
0x18014e080  lea     r13, WPP_e6a39d1dc444391637ddeaca3af09117_Traceguids
0x18014e087  cmp     rax, rbx
0x18014e08a  jz      loc_18014E120
0x18014e090  mov     rbx, rax
0x18014e093  lea     rdx, [rsp+68h+FileSize]; lpFileSize
0x18014e098  mov     qword ptr [rsp+68h+FileSize], 0
0x18014e0a1  mov     rcx, rbx; hFile
0x18014e0a4  call    cs:__imp_GetFileSizeEx
0x18014e0aa  test    eax, eax
0x18014e0ac  jnz     loc_18014E182
0x18014e0b2  call    HrGetLastFailure
0x18014e0b7  mov     esi, eax
0x18014e0b9  mov     r10, cs:WPP_GLOBAL_Control
0x18014e0c0  cmp     r10, r15
0x18014e0c3  jz      short loc_18014E0E7
0x18014e0c5  test    byte ptr [r10+1Ch], 1
0x18014e0ca  jz      short loc_18014E0E7
0x18014e0cc  mov     rcx, [r10+10h]
0x18014e0d0  mov     edx, 2Fh ; '/'
0x18014e0d5  mov     r9, rdi
0x18014e0d8  mov     r8, r13
0x18014e0db  call    WPP_SF_S
0x18014e0e0  mov     r10, cs:WPP_GLOBAL_Control
0x18014e0e7  test    esi, esi
0x18014e0e9  jns     loc_18014E189
0x18014e0ef  cmp     r10, r15
0x18014e0f2  jz      short loc_18014E10F
0x18014e0f4  test    byte ptr [r10+1Ch], 1
0x18014e0f9  jz      short loc_18014E10F
0x18014e0fb  mov     rcx, [r10+10h]
0x18014e0ff  mov     edx, 30h ; '0'
0x18014e104  mov     r8, r13
0x18014e107  mov     r9d, esi
0x18014e10a  call    WPP_SF_d
0x18014e10f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18014e113  jz      short loc_18014E17B
0x18014e115  mov     rcx, rbx; hObject
0x18014e118  call    cs:__imp_CloseHandle
0x18014e11e  jmp     short loc_18014E17B
0x18014e120  call    HrGetLastFailure
0x18014e125  mov     esi, eax
0x18014e127  mov     rcx, cs:WPP_GLOBAL_Control
0x18014e12e  cmp     rcx, r15
0x18014e131  jz      short loc_18014E154
0x18014e133  test    byte ptr [rcx+1Ch], 1
0x18014e137  jz      short loc_18014E154
0x18014e139  mov     rcx, [rcx+10h]
0x18014e13d  mov     edx, 2Dh ; '-'
0x18014e142  mov     r9, rdi
0x18014e145  mov     r8, r13
0x18014e148  call    WPP_SF_S
0x18014e14d  mov     rcx, cs:WPP_GLOBAL_Control
0x18014e154  test    esi, esi
0x18014e156  jns     loc_18014E093
0x18014e15c  cmp     rcx, r15
0x18014e15f  jz      short loc_18014E17B
0x18014e161  test    byte ptr [rcx+1Ch], 1
0x18014e165  jz      short loc_18014E17B
0x18014e167  mov     rcx, [rcx+10h]
0x18014e16b  mov     edx, 2Eh ; '.'
0x18014e170  mov     r9d, esi
0x18014e173  mov     r8, r13
0x18014e176  call    WPP_SF_d
0x18014e17b  mov     eax, esi
0x18014e17d  jmp     loc_18014E245
0x18014e182  mov     r10, cs:WPP_GLOBAL_Control
0x18014e189  mov     rcx, qword ptr [rsp+68h+FileSize]
0x18014e18e  test    rcx, rcx
0x18014e191  jle     short loc_18014E1CE
0x18014e193  cmp     r10, r15
0x18014e196  jz      short loc_18014E1B8
0x18014e198  test    byte ptr [r10+1Ch], 4
0x18014e19d  jz      short loc_18014E1B8
0x18014e19f  mov     qword ptr [rsp+68h+dwCreationDisposition], rcx
0x18014e1a4  mov     edx, 31h ; '1'
0x18014e1a9  mov     rcx, [r10+10h]
0x18014e1ad  mov     r9, rdi
0x18014e1b0  mov     r8, r13
0x18014e1b3  call    WPP_SF_SI
0x18014e1b8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18014e1bc  jz      short loc_18014E1C7
0x18014e1be  mov     rcx, rbx; hObject
0x18014e1c1  call    cs:__imp_CloseHandle
0x18014e1c7  mov     eax, 1
0x18014e1cc  jmp     short loc_18014E245
0x18014e1ce  mov     rcx, rdi; lpFileName
0x18014e1d1  call    cs:__imp_DeleteFileW
0x18014e1d7  test    eax, eax
0x18014e1d9  jnz     short loc_18014E234
0x18014e1db  call    HrGetLastFailure
0x18014e1e0  mov     esi, eax
0x18014e1e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18014e1e9  cmp     rcx, r15
0x18014e1ec  jz      short loc_18014E20F
0x18014e1ee  test    byte ptr [rcx+1Ch], 1
0x18014e1f2  jz      short loc_18014E20F
0x18014e1f4  mov     rcx, [rcx+10h]
0x18014e1f8  mov     edx, 32h ; '2'
0x18014e1fd  mov     r9, rdi
0x18014e200  mov     r8, r13
0x18014e203  call    WPP_SF_S
0x18014e208  mov     rcx, cs:WPP_GLOBAL_Control
0x18014e20f  test    esi, esi
0x18014e211  jns     short loc_18014E234
0x18014e213  cmp     rcx, r15
0x18014e216  jz      loc_18014E10F
0x18014e21c  test    byte ptr [rcx+1Ch], 1
0x18014e220  jz      loc_18014E10F
0x18014e226  mov     rcx, [rcx+10h]
0x18014e22a  mov     edx, 33h ; '3'
0x18014e22f  jmp     loc_18014E104
0x18014e234  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18014e238  jz      short loc_18014E243
0x18014e23a  mov     rcx, rbx; hObject
0x18014e23d  call    cs:__imp_CloseHandle
0x18014e243  xor     eax, eax
0x18014e245  mov     rcx, [rsp+68h+var_20]
0x18014e24a  xor     rcx, rsp; StackCookie
0x18014e24d  call    __security_check_cookie
0x18014e252  lea     r11, [rsp+68h+var_18]
0x18014e257  mov     rbx, [r11+28h]
0x18014e25b  mov     rsi, [r11+30h]
0x18014e25f  mov     rsp, r11
0x18014e262  pop     r15
0x18014e264  pop     r13
0x18014e266  pop     rdi
0x18014e267  retn
```
