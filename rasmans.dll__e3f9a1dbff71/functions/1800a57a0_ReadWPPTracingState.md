# ReadWPPTracingState

- ea: `0x1800a57a0`
- end: `0x1800a5a4a`
- name: `ReadWPPTracingState`
- size: `682`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a54f8`

## callees

- `0x18000e564`
- `0x1800a4ed4`
- `0x1800a5254`
- `0x1800a5770`
- `0x1800a57a0`
- `0x1800a5a50`
- `0x1800a5a90`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `msvcrt!wcsnlen` at `0x1800a58e3`
- `msvcrt!wcsnlen` at `0x1800a58e3`
- `ntdll!RtlGUIDFromString` at `0x1800a5904`
- `ntdll!RtlGUIDFromString` at `0x1800a5904`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a59a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a59a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a586a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a586a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a5a17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a5a17`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800a5974`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800a5974`

## string_xrefs

- `0x1800a5833`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Tracing\Microsoft\RemoteAccess\`

## pseudocode

```c
__int64 __fastcall ReadWPPTracingState(__int64 a1, _DWORD *a2, __int64 *a3)
{
  unsigned int v5; // r12d
  _WORD *v6; // rbx
  wchar_t *v7; // r15
  __int64 v8; // rdi
  int String_0; // eax
  const wchar_t *v10; // rcx
  __int16 v11; // ax
  int v12; // eax
  WCHAR *v13; // rcx
  WCHAR *v14; // rax
  __int64 v15; // rdx
  WCHAR *v16; // rcx
  void *FolderHandle; // rax
  void *v18; // r14
  _WORD *v19; // rcx
  _WORD *v20; // r8
  _WORD *v21; // rdx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *Source[2]; // [rsp+38h] [rbp-C8h] BYREF
  _WORD *v25; // [rsp+48h] [rbp-B8h]
  _DWORD *v26; // [rsp+50h] [rbp-B0h]
  WCHAR SubKey[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v28[524]; // [rsp+64h] [rbp-9Ch] BYREF

  v26 = a2;
  hKey = 0;
  *(_DWORD *)SubKey = 0;
  v5 = 0;
  memset_0(v28, 0, 0x206u);
  Source[0] = 0;
  v6 = 0;
  v25 = 0;
  v7 = 0;
  if ( a1 )
  {
    if ( *(_QWORD *)(a1 + 32) )
    {
      v8 = 261;
      StringCchPrintfW(
        SubKey,
        0x105u,
        L"%s%s",
        L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\Microsoft\\RemoteAccess\\",
        a1 + 562);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
      {
        RegReadDword(hKey, L"Active", a1);
        RegReadDword(hKey, L"ControlFlags", a1 + 4);
        RegReadDword(hKey, L"ControlLevel", a1 + 8);
        String_0 = RegReadString_0(hKey, L"Guid");
        v7 = Source[0];
        if ( !String_0 )
        {
          v10 = Source[0];
          *(_OWORD *)Source = 0;
          v11 = wcsnlen(v10, 0x10u);
          Source[1] = v7;
          WORD1(Source[0]) = 2 * v11;
          LOWORD(Source[0]) = 2 * v11;
          RtlGUIDFromString((PUNICODE_STRING)Source, (GUID *)(a1 + 12));
        }
        v12 = RegReadString_0(hKey, L"LogFileName");
        v6 = v25;
        if ( v12 || !v25 )
          goto LABEL_22;
        v13 = v25;
        v14 = SubKey;
        v15 = 261;
        do
        {
          if ( !*v13 )
            break;
          *v14++ = *v13++;
          --v15;
        }
        while ( v15 );
        v16 = v14 - 1;
        if ( v15 )
          v16 = v14;
        *v16 = 0;
        if ( !PathCchRemoveFileSpec(SubKey, 0x105u) )
        {
          FolderHandle = (void *)GetFolderHandle(SubKey);
          v18 = FolderHandle;
          if ( FolderHandle != (void *)-1LL )
          {
            *a3 = GetFileHandle((__int64)SubKey, FolderHandle);
            CloseHandle(v18);
            if ( *a3 != -1 )
            {
              v19 = v6;
              *v26 = 1;
              v20 = (_WORD *)(*(_QWORD *)(a1 + 32) + *(unsigned int *)(*(_QWORD *)(a1 + 32) + 112LL));
              do
              {
                if ( !*v19 )
                  break;
                *v20++ = *v19++;
                --v8;
              }
              while ( v8 );
              v21 = v20 - 1;
              if ( v8 )
                v21 = v20;
              *v21 = 0;
LABEL_22:
              v5 = 1;
            }
          }
        }
      }
    }
  }
  MprCommonFree(v6);
  MprCommonFree(v7);
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x1800a57a0  mov     [rsp-8+arg_18], rbx
0x1800a57a5  push    rbp
0x1800a57a6  push    rsi
0x1800a57a7  push    rdi
0x1800a57a8  push    r12
0x1800a57aa  push    r13
0x1800a57ac  push    r14
0x1800a57ae  push    r15
0x1800a57b0  lea     rbp, [rsp-180h]
0x1800a57b8  sub     rsp, 280h
0x1800a57bf  mov     rax, cs:__security_cookie
0x1800a57c6  xor     rax, rsp
0x1800a57c9  mov     [rbp+1B0h+var_40], rax
0x1800a57d0  xor     r14d, r14d
0x1800a57d3  mov     [rsp+2B0h+var_260], rdx
0x1800a57d8  mov     r13, r8
0x1800a57db  mov     [rsp+2B0h+hKey], r14
0x1800a57e0  mov     rsi, rcx
0x1800a57e3  mov     dword ptr [rsp+2B0h+SubKey], r14d
0x1800a57e8  xor     edx, edx; Val
0x1800a57ea  lea     rcx, [rsp+2B0h+var_24C]; void *
0x1800a57ef  mov     r8d, 206h; Size
0x1800a57f5  mov     r12d, r14d
0x1800a57f8  call    memset_0
0x1800a57fd  mov     [rsp+2B0h+Source], r14
0x1800a5802  mov     ebx, r14d
0x1800a5805  mov     [rsp+2B0h+var_268], rbx
0x1800a580a  mov     r15d, r14d
0x1800a580d  test    rsi, rsi
0x1800a5810  jz      loc_1800A59FD
0x1800a5816  cmp     [rsi+20h], r14
0x1800a581a  jz      loc_1800A59FD
0x1800a5820  lea     rax, [rsi+232h]
0x1800a5827  mov     edi, 105h
0x1800a582c  mov     edx, edi; unsigned __int64
0x1800a582e  mov     [rsp+2B0h+phkResult], rax
0x1800a5833  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800a583a  lea     r8, aSS_0; "%s%s"
0x1800a5841  lea     rcx, [rsp+2B0h+SubKey]; unsigned __int16 *
0x1800a5846  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a584b  lea     rax, [rsp+2B0h+hKey]
0x1800a5850  mov     r9d, 20019h; samDesired
0x1800a5856  xor     r8d, r8d; ulOptions
0x1800a5859  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1800a585e  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x1800a5863  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a586a  call    cs:__imp_RegOpenKeyExW
0x1800a5870  test    eax, eax
0x1800a5872  jnz     loc_1800A59FD
0x1800a5878  mov     rcx, [rsp+2B0h+hKey]
0x1800a587d  lea     rdx, aActive_0; "Active"
0x1800a5884  mov     r8, rsi
0x1800a5887  call    RegReadDword
0x1800a588c  mov     rcx, [rsp+2B0h+hKey]
0x1800a5891  lea     r8, [rsi+4]
0x1800a5895  lea     rdx, aControlflags; "ControlFlags"
0x1800a589c  call    RegReadDword
0x1800a58a1  mov     rcx, [rsp+2B0h+hKey]
0x1800a58a6  lea     r8, [rsi+8]
0x1800a58aa  lea     rdx, aControllevel; "ControlLevel"
0x1800a58b1  call    RegReadDword
0x1800a58b6  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800a58bb  lea     r8, [rsp+2B0h+Source]
0x1800a58c0  lea     rdx, aGuid_0; "Guid"
0x1800a58c7  call    RegReadString_0
0x1800a58cc  mov     r15, [rsp+2B0h+Source]
0x1800a58d1  test    eax, eax
0x1800a58d3  jnz     short loc_1800A590A
0x1800a58d5  xorps   xmm0, xmm0
0x1800a58d8  lea     edx, [rax+10h]; MaxCount
0x1800a58db  mov     rcx, r15; Source
0x1800a58de  movups  xmmword ptr [rsp+2B0h+Source], xmm0
0x1800a58e3  call    cs:__imp_wcsnlen
0x1800a58e9  lea     rdx, [rsi+0Ch]; Guid
0x1800a58ed  mov     [rsp+2B0h+Source+8], r15
0x1800a58f2  add     ax, ax
0x1800a58f5  lea     rcx, [rsp+2B0h+Source]; GuidString
0x1800a58fa  mov     word ptr [rsp+2B0h+Source+2], ax
0x1800a58ff  mov     word ptr [rsp+2B0h+Source], ax
0x1800a5904  call    cs:__imp_RtlGUIDFromString
0x1800a590a  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800a590f  lea     r8, [rsp+2B0h+var_268]
0x1800a5914  lea     rdx, aLogfilename; "LogFileName"
0x1800a591b  call    RegReadString_0
0x1800a5920  mov     rbx, [rsp+2B0h+var_268]
0x1800a5925  test    eax, eax
0x1800a5927  jnz     loc_1800A59F7
0x1800a592d  test    rbx, rbx
0x1800a5930  jz      loc_1800A59F7
0x1800a5936  mov     rcx, rbx
0x1800a5939  lea     rax, [rsp+2B0h+SubKey]
0x1800a593e  mov     rdx, rdi
0x1800a5941  movzx   r8d, word ptr [rcx]
0x1800a5945  test    r8w, r8w
0x1800a5949  jz      short loc_1800A595D
0x1800a594b  mov     [rax], r8w
0x1800a594f  add     rcx, 2
0x1800a5953  add     rax, 2
0x1800a5957  sub     rdx, 1
0x1800a595b  jnz     short loc_1800A5941
0x1800a595d  test    rdx, rdx
0x1800a5960  lea     rcx, [rax-2]
0x1800a5964  mov     rdx, rdi; cchPath
0x1800a5967  cmovnz  rcx, rax
0x1800a596b  mov     [rcx], r14w
0x1800a596f  lea     rcx, [rsp+2B0h+SubKey]; pszPath
0x1800a5974  call    cs:__imp_PathCchRemoveFileSpec
0x1800a597a  test    eax, eax
0x1800a597c  jnz     short loc_1800A59FD
0x1800a597e  lea     rcx, [rsp+2B0h+SubKey]; String1
0x1800a5983  call    GetFolderHandle
0x1800a5988  mov     r14, rax
0x1800a598b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a598f  jz      short loc_1800A59FD
0x1800a5991  mov     rdx, rax
0x1800a5994  lea     rcx, [rsp+2B0h+SubKey]
0x1800a5999  call    GetFileHandle
0x1800a599e  mov     rcx, r14; hObject
0x1800a59a1  mov     [r13+0], rax
0x1800a59a5  call    cs:__imp_CloseHandle
0x1800a59ab  cmp     qword ptr [r13+0], 0FFFFFFFFFFFFFFFFh
0x1800a59b0  jz      short loc_1800A59FD
0x1800a59b2  mov     rax, [rsp+2B0h+var_260]
0x1800a59b7  mov     rcx, rbx
0x1800a59ba  mov     dword ptr [rax], 1
0x1800a59c0  mov     rax, [rsi+20h]
0x1800a59c4  mov     r8d, [rax+70h]
0x1800a59c8  add     r8, rax
0x1800a59cb  xor     r14d, r14d
0x1800a59ce  movzx   eax, word ptr [rcx]
0x1800a59d1  test    ax, ax
0x1800a59d4  jz      short loc_1800A59E8
0x1800a59d6  mov     [r8], ax
0x1800a59da  add     rcx, 2
0x1800a59de  add     r8, 2
0x1800a59e2  sub     rdi, 1
0x1800a59e6  jnz     short loc_1800A59CE
0x1800a59e8  test    rdi, rdi
0x1800a59eb  lea     rdx, [r8-2]
0x1800a59ef  cmovnz  rdx, r8
0x1800a59f3  mov     [rdx], r14w
0x1800a59f7  mov     r12d, 1
0x1800a59fd  mov     rcx, rbx; lpMem
0x1800a5a00  call    MprCommonFree
0x1800a5a05  mov     rcx, r15; lpMem
0x1800a5a08  call    MprCommonFree
0x1800a5a0d  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800a5a12  test    rcx, rcx
0x1800a5a15  jz      short loc_1800A5A1D
0x1800a5a17  call    cs:__imp_RegCloseKey
0x1800a5a1d  mov     eax, r12d
0x1800a5a20  mov     rcx, [rbp+1B0h+var_40]
0x1800a5a27  xor     rcx, rsp; StackCookie
0x1800a5a2a  call    __security_check_cookie
0x1800a5a2f  mov     rbx, [rsp+2B0h+arg_18]
0x1800a5a37  add     rsp, 280h
0x1800a5a3e  pop     r15
0x1800a5a40  pop     r14
0x1800a5a42  pop     r13
0x1800a5a44  pop     r12
0x1800a5a46  pop     rdi
0x1800a5a47  pop     rsi
0x1800a5a48  pop     rbp
0x1800a5a49  retn
```
