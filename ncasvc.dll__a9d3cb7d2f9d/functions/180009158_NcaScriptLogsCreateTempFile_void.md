# NcaScriptLogsCreateTempFile(void * *)

- ea: `0x180009158`
- end: `0x1800092e8`
- name: `?NcaScriptLogsCreateTempFile@@YAKPEAPEAX@Z`
- size: `400`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180009f1c`

## callees

- `0x180004f34`
- `0x180009158`
- `0x18001cc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009285`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009285`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009240`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009240`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800091cd`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800091cd`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18000919d`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18000919d`

## pseudocode

```c
__int64 __fastcall NcaScriptLogsCreateTempFile(void **a1)
{
  DWORD LastError; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  HANDLE v5; // rax
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-458h] BYREF
  WCHAR PathName[264]; // [rsp+60h] [rbp-438h] BYREF
  WCHAR TempFileName[264]; // [rsp+270h] [rbp-228h] BYREF

  *(_QWORD *)&SecurityAttributes.nLength = 24;
  LastError = 0;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 1;
  SecurityAttributes.lpSecurityDescriptor = 0;
  if ( (unsigned int)GetTempPath2W(260, PathName) - 1 > 0x103 )
  {
    LastError = GetLastError();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 36;
      goto LABEL_14;
    }
  }
  else if ( GetTempFileNameW(PathName, L"NCA", 0, TempFileName) )
  {
    v5 = CreateFileW(TempFileName, 0xC0000000, 0, &SecurityAttributes, 2u, 0x4000100u, 0);
    if ( v5 == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 38;
        goto LABEL_14;
      }
    }
    else
    {
      *a1 = v5;
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 37;
LABEL_14:
      WPP_SF_d(v3[2], v4, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids, LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180009158  mov     [rsp+arg_8], rbx
0x18000915d  push    rdi
0x18000915e  sub     rsp, 490h
0x180009165  mov     rax, cs:__security_cookie
0x18000916c  xor     rax, rsp
0x18000916f  mov     [rsp+498h+var_18], rax
0x180009177  mov     rdi, rcx
0x18000917a  mov     qword ptr [rsp+498h+SecurityAttributes.nLength], 18h
0x180009183  xor     ebx, ebx
0x180009185  mov     qword ptr [rsp+498h+SecurityAttributes.bInheritHandle], 1
0x18000918e  mov     ecx, 104h
0x180009193  mov     [rsp+498h+SecurityAttributes.lpSecurityDescriptor], rbx
0x180009198  lea     rdx, [rsp+498h+PathName]
0x18000919d  call    cs:__imp_GetTempPath2W
0x1800091a4  nop     dword ptr [rax+rax+00h]
0x1800091a9  dec     eax
0x1800091ab  cmp     eax, 103h
0x1800091b0  ja      loc_180009285
0x1800091b6  lea     r9, [rsp+498h+TempFileName]; lpTempFileName
0x1800091be  xor     r8d, r8d; uUnique
0x1800091c1  lea     rdx, PrefixString; "NCA"
0x1800091c8  lea     rcx, [rsp+498h+PathName]; lpPathName
0x1800091cd  call    cs:__imp_GetTempFileNameW
0x1800091d4  nop     dword ptr [rax+rax+00h]
0x1800091d9  test    eax, eax
0x1800091db  jnz     short loc_180009216
0x1800091dd  call    cs:__imp_GetLastError
0x1800091e4  nop     dword ptr [rax+rax+00h]
0x1800091e9  mov     ebx, eax
0x1800091eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091f2  lea     rax, WPP_GLOBAL_Control
0x1800091f9  cmp     rcx, rax
0x1800091fc  jz      loc_1800092C4
0x180009202  test    byte ptr [rcx+1Ch], 1
0x180009206  jz      loc_1800092C4
0x18000920c  mov     edx, 25h ; '%'
0x180009211  jmp     loc_1800092B1
0x180009216  mov     [rsp+498h+hTemplateFile], rbx; hTemplateFile
0x18000921b  lea     r9, [rsp+498h+SecurityAttributes]; lpSecurityAttributes
0x180009220  mov     [rsp+498h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x180009228  lea     rcx, [rsp+498h+TempFileName]; lpFileName
0x180009230  xor     r8d, r8d; dwShareMode
0x180009233  mov     [rsp+498h+dwCreationDisposition], 2; dwCreationDisposition
0x18000923b  mov     edx, 0C0000000h; dwDesiredAccess
0x180009240  call    cs:__imp_CreateFileW
0x180009247  nop     dword ptr [rax+rax+00h]
0x18000924c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009250  jnz     short loc_180009280
0x180009252  call    cs:__imp_GetLastError
0x180009259  nop     dword ptr [rax+rax+00h]
0x18000925e  mov     ebx, eax
0x180009260  mov     rcx, cs:WPP_GLOBAL_Control
0x180009267  lea     rax, WPP_GLOBAL_Control
0x18000926e  cmp     rcx, rax
0x180009271  jz      short loc_1800092C4
0x180009273  test    byte ptr [rcx+1Ch], 1
0x180009277  jz      short loc_1800092C4
0x180009279  mov     edx, 26h ; '&'
0x18000927e  jmp     short loc_1800092B1
0x180009280  mov     [rdi], rax
0x180009283  jmp     short loc_1800092C4
0x180009285  call    cs:__imp_GetLastError
0x18000928c  nop     dword ptr [rax+rax+00h]
0x180009291  mov     ebx, eax
0x180009293  mov     rcx, cs:WPP_GLOBAL_Control
0x18000929a  lea     rax, WPP_GLOBAL_Control
0x1800092a1  cmp     rcx, rax
0x1800092a4  jz      short loc_1800092C4
0x1800092a6  test    byte ptr [rcx+1Ch], 1
0x1800092aa  jz      short loc_1800092C4
0x1800092ac  mov     edx, 24h ; '$'
0x1800092b1  mov     rcx, [rcx+10h]
0x1800092b5  lea     r8, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids
0x1800092bc  mov     r9d, ebx
0x1800092bf  call    WPP_SF_d
0x1800092c4  mov     eax, ebx
0x1800092c6  mov     rcx, [rsp+498h+var_18]
0x1800092ce  xor     rcx, rsp; StackCookie
0x1800092d1  call    __security_check_cookie
0x1800092d6  mov     rbx, [rsp+498h+arg_8]
0x1800092de  add     rsp, 490h
0x1800092e5  pop     rdi
0x1800092e6  retn
```
