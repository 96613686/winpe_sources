# ReadWPPTracingState

- ea: `0x1800ab670`
- end: `0x1800ab943`
- name: `ReadWPPTracingState`
- size: `723`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ab394`

## callees

- `0x18000eb54`
- `0x1800aac9c`
- `0x1800ab0ac`
- `0x1800ab634`
- `0x1800ab670`
- `0x1800ab94c`
- `0x1800ab994`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `msvcrt!wcsnlen` at `0x1800ab7b9`
- `msvcrt!wcsnlen` at `0x1800ab7b9`
- `ntdll!RtlGUIDFromString` at `0x1800ab7e0`
- `ntdll!RtlGUIDFromString` at `0x1800ab7e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab891`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab891`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab73a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab73a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab909`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab909`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800ab856`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800ab856`

## string_xrefs

- `0x1800ab703`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Tracing\Microsoft\RemoteAccess\`

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
0x1800ab670  mov     [rsp-8+arg_18], rbx
0x1800ab675  push    rbp
0x1800ab676  push    rsi
0x1800ab677  push    rdi
0x1800ab678  push    r12
0x1800ab67a  push    r13
0x1800ab67c  push    r14
0x1800ab67e  push    r15
0x1800ab680  lea     rbp, [rsp-180h]
0x1800ab688  sub     rsp, 280h
0x1800ab68f  mov     rax, cs:__security_cookie
0x1800ab696  xor     rax, rsp
0x1800ab699  mov     [rbp+1B0h+var_40], rax
0x1800ab6a0  xor     r14d, r14d
0x1800ab6a3  mov     [rsp+2B0h+var_260], rdx
0x1800ab6a8  mov     r13, r8
0x1800ab6ab  mov     [rsp+2B0h+hKey], r14
0x1800ab6b0  mov     rsi, rcx
0x1800ab6b3  mov     dword ptr [rsp+2B0h+SubKey], r14d
0x1800ab6b8  xor     edx, edx; Val
0x1800ab6ba  lea     rcx, [rsp+2B0h+var_24C]; void *
0x1800ab6bf  mov     r8d, 206h; Size
0x1800ab6c5  mov     r12d, r14d
0x1800ab6c8  call    memset_0
0x1800ab6cd  mov     [rsp+2B0h+Source], r14
0x1800ab6d2  mov     ebx, r14d
0x1800ab6d5  mov     [rsp+2B0h+var_268], rbx
0x1800ab6da  mov     r15d, r14d
0x1800ab6dd  test    rsi, rsi
0x1800ab6e0  jz      loc_1800AB8EF
0x1800ab6e6  cmp     [rsi+20h], r14
0x1800ab6ea  jz      loc_1800AB8EF
0x1800ab6f0  lea     rax, [rsi+232h]
0x1800ab6f7  mov     edi, 105h
0x1800ab6fc  mov     edx, edi; unsigned __int64
0x1800ab6fe  mov     [rsp+2B0h+phkResult], rax
0x1800ab703  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800ab70a  lea     r8, aSS_3; "%s%s"
0x1800ab711  lea     rcx, [rsp+2B0h+SubKey]; unsigned __int16 *
0x1800ab716  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ab71b  lea     rax, [rsp+2B0h+hKey]
0x1800ab720  mov     r9d, 20019h; samDesired
0x1800ab726  xor     r8d, r8d; ulOptions
0x1800ab729  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1800ab72e  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x1800ab733  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ab73a  call    cs:__imp_RegOpenKeyExW
0x1800ab741  nop     dword ptr [rax+rax+00h]
0x1800ab746  test    eax, eax
0x1800ab748  jnz     loc_1800AB8EF
0x1800ab74e  mov     rcx, [rsp+2B0h+hKey]
0x1800ab753  lea     rdx, aActive_0; "Active"
0x1800ab75a  mov     r8, rsi
0x1800ab75d  call    RegReadDword
0x1800ab762  mov     rcx, [rsp+2B0h+hKey]
0x1800ab767  lea     r8, [rsi+4]
0x1800ab76b  lea     rdx, aControlflags; "ControlFlags"
0x1800ab772  call    RegReadDword
0x1800ab777  mov     rcx, [rsp+2B0h+hKey]
0x1800ab77c  lea     r8, [rsi+8]
0x1800ab780  lea     rdx, aControllevel; "ControlLevel"
0x1800ab787  call    RegReadDword
0x1800ab78c  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800ab791  lea     r8, [rsp+2B0h+Source]
0x1800ab796  lea     rdx, aGuid_0; "Guid"
0x1800ab79d  call    RegReadString_0
0x1800ab7a2  mov     r15, [rsp+2B0h+Source]
0x1800ab7a7  test    eax, eax
0x1800ab7a9  jnz     short loc_1800AB7EC
0x1800ab7ab  xorps   xmm0, xmm0
0x1800ab7ae  lea     edx, [rax+10h]; MaxCount
0x1800ab7b1  mov     rcx, r15; Source
0x1800ab7b4  movups  xmmword ptr [rsp+2B0h+Source], xmm0
0x1800ab7b9  call    cs:__imp_wcsnlen
0x1800ab7c0  nop     dword ptr [rax+rax+00h]
0x1800ab7c5  lea     rdx, [rsi+0Ch]; Guid
0x1800ab7c9  mov     [rsp+2B0h+Source+8], r15
0x1800ab7ce  add     ax, ax
0x1800ab7d1  lea     rcx, [rsp+2B0h+Source]; GuidString
0x1800ab7d6  mov     word ptr [rsp+2B0h+Source+2], ax
0x1800ab7db  mov     word ptr [rsp+2B0h+Source], ax
0x1800ab7e0  call    cs:__imp_RtlGUIDFromString
0x1800ab7e7  nop     dword ptr [rax+rax+00h]
0x1800ab7ec  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800ab7f1  lea     r8, [rsp+2B0h+var_268]
0x1800ab7f6  lea     rdx, aLogfilename; "LogFileName"
0x1800ab7fd  call    RegReadString_0
0x1800ab802  mov     rbx, [rsp+2B0h+var_268]
0x1800ab807  test    eax, eax
0x1800ab809  jnz     loc_1800AB8E9
0x1800ab80f  test    rbx, rbx
0x1800ab812  jz      loc_1800AB8E9
0x1800ab818  mov     rcx, rbx
0x1800ab81b  lea     rax, [rsp+2B0h+SubKey]
0x1800ab820  mov     rdx, rdi
0x1800ab823  movzx   r8d, word ptr [rcx]
0x1800ab827  test    r8w, r8w
0x1800ab82b  jz      short loc_1800AB83F
0x1800ab82d  mov     [rax], r8w
0x1800ab831  add     rcx, 2
0x1800ab835  add     rax, 2
0x1800ab839  sub     rdx, 1
0x1800ab83d  jnz     short loc_1800AB823
0x1800ab83f  test    rdx, rdx
0x1800ab842  lea     rcx, [rax-2]
0x1800ab846  mov     rdx, rdi; cchPath
0x1800ab849  cmovnz  rcx, rax
0x1800ab84d  mov     [rcx], r14w
0x1800ab851  lea     rcx, [rsp+2B0h+SubKey]; pszPath
0x1800ab856  call    cs:__imp_PathCchRemoveFileSpec
0x1800ab85d  nop     dword ptr [rax+rax+00h]
0x1800ab862  test    eax, eax
0x1800ab864  jnz     loc_1800AB8EF
0x1800ab86a  lea     rcx, [rsp+2B0h+SubKey]; String1
0x1800ab86f  call    GetFolderHandle
0x1800ab874  mov     r14, rax
0x1800ab877  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ab87b  jz      short loc_1800AB8EF
0x1800ab87d  mov     rdx, rax
0x1800ab880  lea     rcx, [rsp+2B0h+SubKey]
0x1800ab885  call    GetFileHandle
0x1800ab88a  mov     rcx, r14; hObject
0x1800ab88d  mov     [r13+0], rax
0x1800ab891  call    cs:__imp_CloseHandle
0x1800ab898  nop     dword ptr [rax+rax+00h]
0x1800ab89d  cmp     qword ptr [r13+0], 0FFFFFFFFFFFFFFFFh
0x1800ab8a2  jz      short loc_1800AB8EF
0x1800ab8a4  mov     rax, [rsp+2B0h+var_260]
0x1800ab8a9  mov     rcx, rbx
0x1800ab8ac  mov     dword ptr [rax], 1
0x1800ab8b2  mov     rax, [rsi+20h]
0x1800ab8b6  mov     r8d, [rax+70h]
0x1800ab8ba  add     r8, rax
0x1800ab8bd  xor     r14d, r14d
0x1800ab8c0  movzx   eax, word ptr [rcx]
0x1800ab8c3  test    ax, ax
0x1800ab8c6  jz      short loc_1800AB8DA
0x1800ab8c8  mov     [r8], ax
0x1800ab8cc  add     rcx, 2
0x1800ab8d0  add     r8, 2
0x1800ab8d4  sub     rdi, 1
0x1800ab8d8  jnz     short loc_1800AB8C0
0x1800ab8da  test    rdi, rdi
0x1800ab8dd  lea     rdx, [r8-2]
0x1800ab8e1  cmovnz  rdx, r8
0x1800ab8e5  mov     [rdx], r14w
0x1800ab8e9  mov     r12d, 1
0x1800ab8ef  mov     rcx, rbx; lpMem
0x1800ab8f2  call    MprCommonFree
0x1800ab8f7  mov     rcx, r15; lpMem
0x1800ab8fa  call    MprCommonFree
0x1800ab8ff  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800ab904  test    rcx, rcx
0x1800ab907  jz      short loc_1800AB915
0x1800ab909  call    cs:__imp_RegCloseKey
0x1800ab910  nop     dword ptr [rax+rax+00h]
0x1800ab915  mov     eax, r12d
0x1800ab918  mov     rcx, [rbp+1B0h+var_40]
0x1800ab91f  xor     rcx, rsp; StackCookie
0x1800ab922  call    __security_check_cookie
0x1800ab927  mov     rbx, [rsp+2B0h+arg_18]
0x1800ab92f  add     rsp, 280h
0x1800ab936  pop     r15
0x1800ab938  pop     r14
0x1800ab93a  pop     r13
0x1800ab93c  pop     r12
0x1800ab93e  pop     rdi
0x1800ab93f  pop     rsi
0x1800ab940  pop     rbp
0x1800ab941  retn
```
