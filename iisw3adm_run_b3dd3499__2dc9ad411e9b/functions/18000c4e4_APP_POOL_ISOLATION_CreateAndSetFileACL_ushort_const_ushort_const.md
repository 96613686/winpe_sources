# APP_POOL_ISOLATION::CreateAndSetFileACL(ushort const *,ushort const *)

- ea: `0x18000c4e4`
- end: `0x18000c74e`
- name: `?CreateAndSetFileACL@APP_POOL_ISOLATION@@SAJPEBG0@Z`
- size: `618`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000cc40`
- `0x18000e1f0`

## callees

- `0x18000c4e4`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c705`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c705`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c6df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c6df`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000c6b5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000c6b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c714`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c714`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c722`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c722`
- `iisutil!PuDbgPrint` at `0x18000c570`
- `iisutil!PuDbgPrint` at `0x18000c69f`
- `iisutil!PuDbgPrint` at `0x18000c570`
- `iisutil!PuDbgPrint` at `0x18000c69f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c516`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c516`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000c599`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000c599`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c5b4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c5cf`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c5f5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c60c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c627`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c5b4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c5cf`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c5f5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c60c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c627`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000c646`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000c646`

## string_xrefs

- `0x18000c55e`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool_isolation.cxx`
- `0x18000c67c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool_isolation.cxx`
- `0x18000c546`: `Setting ACL for file (path: %S; SID: %S)\n`
- `0x18000c552`: `APP_POOL_ISOLATION::CreateAndSetFileACL`
- `0x18000c66e`: `APP_POOL_ISOLATION::CreateAndSetFileACL`
- `0x18000c68e`: `Error generating SD for config file (path: %S; sddl: %S)\n`

## pseudocode

```c
__int64 __fastcall APP_POOL_ISOLATION::CreateAndSetFileACL(LPCWSTR lpFileName, const unsigned __int16 *a2)
{
  __int64 v4; // rcx
  struct _SECURITY_ATTRIBUTES *p_SecurityDescriptor; // rax
  signed int v6; // ebx
  HANDLE v7; // rax
  signed int LastError; // eax
  struct _SECURITY_ATTRIBUTES SecurityDescriptor; // [rsp+40h] [rbp-19h] BYREF
  _BYTE v11[32]; // [rsp+58h] [rbp-1h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+78h] [rbp+1Fh]

  STRU::STRU((STRU *)v11);
  memset(&SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_isolation.cxx",
      1561,
      "APP_POOL_ISOLATION::CreateAndSetFileACL",
      "Setting ACL for file (path: %S; SID: %S)\n",
      lpFileName,
      a2);
  v4 = 24;
  p_SecurityDescriptor = &SecurityDescriptor;
  do
  {
    LOBYTE(p_SecurityDescriptor->nLength) = 0;
    p_SecurityDescriptor = (struct _SECURITY_ATTRIBUTES *)((char *)p_SecurityDescriptor + 1);
    --v4;
  }
  while ( v4 );
  v6 = STRU::Copy((STRU *)v11, L"D:P");
  if ( v6 >= 0 )
  {
    v6 = STRU::Append((STRU *)v11, L"(A;OICI;GA;;;SY)");
    if ( v6 >= 0 )
    {
      v6 = STRU::Append((STRU *)v11, L"(A;OICI;GA;;;BA)");
      if ( v6 >= 0 )
      {
        if ( !a2
          || !*a2
          || (v6 = STRU::Append((STRU *)v11, L"(A;OICI;GR;;;"), v6 >= 0)
          && (v6 = STRU::Append((STRU *)v11, a2), v6 >= 0) )
        {
          v6 = STRU::Append((STRU *)v11, L")");
          if ( v6 >= 0 )
          {
            if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                   StringSecurityDescriptor,
                   1u,
                   &SecurityDescriptor.lpSecurityDescriptor,
                   0) )
            {
              SecurityDescriptor.nLength = 24;
              SecurityDescriptor.bInheritHandle = 0;
              DeleteFileW(lpFileName);
              v7 = CreateFileW(lpFileName, 0xC0000000, 0, &SecurityDescriptor, 2u, 0x80u, 0);
              if ( v7 != (HANDLE)-1LL )
              {
                CloseHandle(v7);
                goto LABEL_20;
              }
            }
            else if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
            {
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_isolation.cxx",
                1626,
                "APP_POOL_ISOLATION::CreateAndSetFileACL",
                "Error generating SD for config file (path: %S; sddl: %S)\n",
                lpFileName,
                StringSecurityDescriptor);
            }
            LastError = GetLastError();
            v6 = LastError;
            if ( LastError > 0 )
              v6 = (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
    }
  }
LABEL_20:
  if ( SecurityDescriptor.lpSecurityDescriptor )
  {
    LocalFree(SecurityDescriptor.lpSecurityDescriptor);
    SecurityDescriptor.lpSecurityDescriptor = 0;
  }
  STRU::~STRU((STRU *)v11);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000c4e4  mov     [rsp-8+arg_10], rbx
0x18000c4e9  mov     [rsp-8+arg_18], rsi
0x18000c4ee  push    rbp
0x18000c4ef  push    rdi
0x18000c4f0  push    r14
0x18000c4f2  lea     rbp, [rsp-47h]
0x18000c4f7  sub     rsp, 0A0h
0x18000c4fe  mov     rax, cs:__security_cookie
0x18000c505  xor     rax, rsp
0x18000c508  mov     [rbp+57h+var_20], rax
0x18000c50c  mov     rsi, rcx
0x18000c50f  mov     rdi, rdx
0x18000c512  lea     rcx, [rbp+57h+var_58]
0x18000c516  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000c51c  xor     eax, eax
0x18000c51e  xorps   xmm0, xmm0
0x18000c521  mov     [rbp+57h+var_60], rax
0x18000c525  mov     eax, cs:g_dwDebugFlags
0x18000c52b  test    al, 3
0x18000c52d  movups  xmmword ptr [rbp+57h+SecurityDescriptor], xmm0
0x18000c531  setnz   cl
0x18000c534  bt      eax, 1Fh
0x18000c538  setb    al
0x18000c53b  test    al, cl
0x18000c53d  jz      short loc_18000C576
0x18000c53f  mov     rcx, cs:g_pDebug
0x18000c546  lea     rax, aSettingAclForF; "Setting ACL for file (path: %S; SID: %S"...
0x18000c54d  mov     [rsp+0B0h+hTemplateFile], rdi
0x18000c552  lea     r9, aAppPoolIsolati_1; "APP_POOL_ISOLATION::CreateAndSetFileACL"
0x18000c559  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rsi
0x18000c55e  lea     rdx, aServercommonIn_28; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000c565  mov     r8d, 619h
0x18000c56b  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x18000c570  call    cs:__imp_PuDbgPrint
0x18000c576  mov     ecx, 18h
0x18000c57b  lea     rax, [rbp+57h+SecurityDescriptor]
0x18000c57f  xor     r14d, r14d
0x18000c582  mov     [rax], r14b
0x18000c585  inc     rax
0x18000c588  sub     rcx, 1
0x18000c58c  jnz     short loc_18000C582
0x18000c58e  lea     rdx, aDP; "D:P"
0x18000c595  lea     rcx, [rbp+57h+var_58]
0x18000c599  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000c59f  mov     ebx, eax
0x18000c5a1  test    eax, eax
0x18000c5a3  js      loc_18000C70B
0x18000c5a9  lea     rdx, aAOiciGaSy; "(A;OICI;GA;;;SY)"
0x18000c5b0  lea     rcx, [rbp+57h+var_58]
0x18000c5b4  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000c5ba  mov     ebx, eax
0x18000c5bc  test    eax, eax
0x18000c5be  js      loc_18000C70B
0x18000c5c4  lea     rdx, aAOiciGaBa; "(A;OICI;GA;;;BA)"
0x18000c5cb  lea     rcx, [rbp+57h+var_58]
0x18000c5cf  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000c5d5  mov     ebx, eax
0x18000c5d7  test    eax, eax
0x18000c5d9  js      loc_18000C70B
0x18000c5df  test    rdi, rdi
0x18000c5e2  jz      short loc_18000C61C
0x18000c5e4  cmp     [rdi], r14w
0x18000c5e8  jz      short loc_18000C61C
0x18000c5ea  lea     rdx, aAOiciGr; "(A;OICI;GR;;;"
0x18000c5f1  lea     rcx, [rbp+57h+var_58]
0x18000c5f5  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000c5fb  mov     ebx, eax
0x18000c5fd  test    eax, eax
0x18000c5ff  js      loc_18000C70B
0x18000c605  mov     rdx, rdi
0x18000c608  lea     rcx, [rbp+57h+var_58]
0x18000c60c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000c612  mov     ebx, eax
0x18000c614  test    eax, eax
0x18000c616  js      loc_18000C70B
0x18000c61c  lea     rdx, asc_180067C58; ")"
0x18000c623  lea     rcx, [rbp+57h+var_58]
0x18000c627  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000c62d  mov     ebx, eax
0x18000c62f  test    eax, eax
0x18000c631  js      loc_18000C70B
0x18000c637  mov     rcx, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18000c63b  lea     r8, [rbp+57h+SecurityDescriptor+8]; SecurityDescriptor
0x18000c63f  xor     r9d, r9d; SecurityDescriptorSize
0x18000c642  lea     edx, [r9+1]; StringSDRevision
0x18000c646  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000c64c  test    eax, eax
0x18000c64e  jnz     short loc_18000C6A7
0x18000c650  mov     eax, cs:g_dwDebugFlags
0x18000c656  test    al, 3
0x18000c658  setnz   cl
0x18000c65b  bt      eax, 1Fh
0x18000c65f  setb    al
0x18000c662  test    al, cl
0x18000c664  jz      loc_18000C6EB
0x18000c66a  mov     rax, [rbp+57h+StringSecurityDescriptor]
0x18000c66e  lea     r9, aAppPoolIsolati_1; "APP_POOL_ISOLATION::CreateAndSetFileACL"
0x18000c675  mov     rcx, cs:g_pDebug
0x18000c67c  lea     rdx, aServercommonIn_28; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000c683  mov     [rsp+0B0h+hTemplateFile], rax
0x18000c688  mov     r8d, 65Ah
0x18000c68e  lea     rax, aErrorGeneratin; "Error generating SD for config file (pa"...
0x18000c695  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rsi
0x18000c69a  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x18000c69f  call    cs:__imp_PuDbgPrint
0x18000c6a5  jmp     short loc_18000C6EB
0x18000c6a7  mov     rcx, rsi; lpFileName
0x18000c6aa  mov     dword ptr [rbp+57h+SecurityDescriptor], 18h
0x18000c6b1  mov     dword ptr [rbp+57h+var_60], r14d
0x18000c6b5  call    cs:__imp_DeleteFileW
0x18000c6bb  mov     [rsp+0B0h+hTemplateFile], r14; hTemplateFile
0x18000c6c0  lea     r9, [rbp+57h+SecurityDescriptor]; lpSecurityAttributes
0x18000c6c4  mov     [rsp+0B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000c6cc  xor     r8d, r8d; dwShareMode
0x18000c6cf  mov     edx, 0C0000000h; dwDesiredAccess
0x18000c6d4  mov     [rsp+0B0h+dwCreationDisposition], 2; dwCreationDisposition
0x18000c6dc  mov     rcx, rsi; lpFileName
0x18000c6df  call    cs:__imp_CreateFileW
0x18000c6e5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c6e9  jnz     short loc_18000C702
0x18000c6eb  call    cs:__imp_GetLastError
0x18000c6f1  mov     ebx, eax
0x18000c6f3  test    eax, eax
0x18000c6f5  jle     short loc_18000C70B
0x18000c6f7  movzx   ebx, ax
0x18000c6fa  or      ebx, 80070000h
0x18000c700  jmp     short loc_18000C70B
0x18000c702  mov     rcx, rax; hObject
0x18000c705  call    cs:__imp_CloseHandle
0x18000c70b  mov     rcx, [rbp+57h+SecurityDescriptor+8]; hMem
0x18000c70f  test    rcx, rcx
0x18000c712  jz      short loc_18000C71E
0x18000c714  call    cs:__imp_LocalFree
0x18000c71a  mov     [rbp+57h+SecurityDescriptor+8], r14
0x18000c71e  lea     rcx, [rbp+57h+var_58]
0x18000c722  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000c728  mov     eax, ebx
0x18000c72a  mov     rcx, [rbp+57h+var_20]
0x18000c72e  xor     rcx, rsp; StackCookie
0x18000c731  call    __security_check_cookie
0x18000c736  lea     r11, [rsp+0B0h+var_10]
0x18000c73e  mov     rbx, [r11+30h]
0x18000c742  mov     rsi, [r11+38h]
0x18000c746  mov     rsp, r11
0x18000c749  pop     r14
0x18000c74b  pop     rdi
0x18000c74c  pop     rbp
0x18000c74d  retn
```
