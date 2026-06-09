# WebRuntimeDiagnostics::LCIEDiagnosticsSession::CreateEventAndSetSecurityAccess(void)

- ea: `0x1800687ac`
- end: `0x18006899b`
- name: `?CreateEventAndSetSecurityAccess@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@AEAAJXZ`
- size: `495`
- prototype: `__int64 __fastcall(WebRuntimeDiagnostics::LCIEDiagnosticsSession *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800689a4`

## callees

- `0x1800073a0`
- `0x18002b530`
- `0x18002c5b0`
- `0x1800687ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180068800`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180068800`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180068813`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180068813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006884e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006886c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006889e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800688ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068942`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006884e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006886c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006889e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800688ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068942`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068864`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068864`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068905`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068978`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068905`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068978`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800688e5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800688e5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180068894`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180068894`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006883f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006883f`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x180068964`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x180068964`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x18006896d`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x18006896d`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x180068934`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x180068934`

## pseudocode

```c
__int64 __fastcall WebRuntimeDiagnostics::LCIEDiagnosticsSession::CreateEventAndSetSecurityAccess(
        WebRuntimeDiagnostics::LCIEDiagnosticsSession *this)
{
  HANDLE CurrentProcess; // rax
  signed int v2; // ebx
  signed int LastError; // eax
  signed int v4; // eax
  signed int v5; // eax
  signed int v6; // eax
  HANDLE BoundaryDescriptorW; // rax
  void *v8; // rsi
  signed int v9; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  struct _SECURITY_ATTRIBUTES PrivateNamespaceAttributes; // [rsp+50h] [rbp-B0h] BYREF
  PSID TokenInformation[12]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR StringSecurityDescriptor[304]; // [rsp+D0h] [rbp-30h] BYREF

  StringSid = 0;
  SecurityDescriptor = 0;
  TokenHandle = 0;
  memset_0(TokenInformation, 0, sizeof(TokenInformation));
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xF01FFu, &TokenHandle) )
  {
    v2 = 0;
    ReturnLength = 0;
    if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x60u, &ReturnLength) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(TokenHandle);
  }
  else
  {
    v4 = GetLastError();
    v2 = v4;
    if ( v4 > 0 )
      v2 = (unsigned __int16)v4 | 0x80070000;
  }
  if ( v2 >= 0 )
  {
    if ( !ConvertSidToStringSidW(TokenInformation[0], &StringSid) )
    {
      v5 = GetLastError();
      v2 = v5;
      if ( v5 > 0 )
        v2 = (unsigned __int16)v5 | 0x80070000;
    }
    if ( v2 >= 0 )
    {
      v2 = StringCchPrintfW(
             StringSecurityDescriptor,
             0x12Cu,
             L"S:(ML;;NW;;;LW)D:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;S-1-15-2-1)(A;;GA;;;%s)",
             StringSid);
      if ( v2 >= 0
        && !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
      {
        v6 = GetLastError();
        v2 = v6;
        if ( v6 > 0 )
          v2 = (unsigned __int16)v6 | 0x80070000;
      }
      LocalFree(StringSid);
      if ( v2 >= 0 )
      {
        PrivateNamespaceAttributes.lpSecurityDescriptor = SecurityDescriptor;
        *(_QWORD *)&PrivateNamespaceAttributes.nLength = 24;
        *(_QWORD *)&PrivateNamespaceAttributes.bInheritHandle = 0;
        BoundaryDescriptorW = CreateBoundaryDescriptorW(L"WebRuntimeDiagnosticsBoundary", 0);
        v8 = BoundaryDescriptorW;
        if ( BoundaryDescriptorW )
        {
          CreatePrivateNamespaceW(&PrivateNamespaceAttributes, BoundaryDescriptorW, L"WebRuntimeDiagnosticsBoundary");
          DeleteBoundaryDescriptor(v8);
        }
        else
        {
          v9 = GetLastError();
          v2 = v9;
          if ( v9 > 0 )
            v2 = (unsigned __int16)v9 | 0x80070000;
        }
        LocalFree(SecurityDescriptor);
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800687ac  push    rbp
0x1800687ae  push    rbx
0x1800687af  push    rsi
0x1800687b0  push    rdi
0x1800687b1  lea     rbp, [rsp-248h]
0x1800687b9  sub     rsp, 348h
0x1800687c0  mov     rax, cs:__security_cookie
0x1800687c7  xor     rax, rsp
0x1800687ca  mov     [rbp+260h+var_30], rax
0x1800687d1  mov     edi, 60h ; '`'
0x1800687d6  mov     [rsp+360h+StringSid], 0
0x1800687df  mov     r8d, edi; Size
0x1800687e2  mov     [rsp+360h+SecurityDescriptor], 0
0x1800687eb  xor     edx, edx; Val
0x1800687ed  mov     [rsp+360h+TokenHandle], 0
0x1800687f6  lea     rcx, [rsp+360h+TokenInformation]; void *
0x1800687fb  call    memset_0
0x180068800  call    cs:__imp_GetCurrentProcess
0x180068806  lea     r8, [rsp+360h+TokenHandle]; TokenHandle
0x18006880b  mov     edx, 0F01FFh; DesiredAccess
0x180068810  mov     rcx, rax; ProcessHandle
0x180068813  call    cs:__imp_OpenProcessToken
0x180068819  lea     esi, [rdi-5Fh]
0x18006881c  test    eax, eax
0x18006881e  jz      short loc_18006886C
0x180068820  mov     rcx, [rsp+360h+TokenHandle]; TokenHandle
0x180068825  lea     rax, [rsp+360h+var_330]
0x18006882a  xor     ebx, ebx
0x18006882c  mov     [rsp+360h+ReturnLength], rax; ReturnLength
0x180068831  mov     r9d, edi; TokenInformationLength
0x180068834  mov     [rsp+360h+var_330], ebx
0x180068838  lea     r8, [rsp+360h+TokenInformation]; TokenInformation
0x18006883d  mov     edx, esi; TokenInformationClass
0x18006883f  call    cs:__imp_GetTokenInformation
0x180068845  mov     edi, 80070000h
0x18006884a  test    eax, eax
0x18006884c  jnz     short loc_18006885F
0x18006884e  call    cs:__imp_GetLastError
0x180068854  mov     ebx, eax
0x180068856  test    eax, eax
0x180068858  jle     short loc_18006885F
0x18006885a  movzx   ebx, ax
0x18006885d  or      ebx, edi
0x18006885f  mov     rcx, [rsp+360h+TokenHandle]; hObject
0x180068864  call    cs:__imp_CloseHandle
0x18006886a  jmp     short loc_180068882
0x18006886c  call    cs:__imp_GetLastError
0x180068872  mov     ebx, eax
0x180068874  mov     edi, 80070000h
0x180068879  test    eax, eax
0x18006887b  jle     short loc_180068882
0x18006887d  movzx   ebx, ax
0x180068880  or      ebx, edi
0x180068882  test    ebx, ebx
0x180068884  js      loc_18006897E
0x18006888a  mov     rcx, [rsp+360h+TokenInformation]; Sid
0x18006888f  lea     rdx, [rsp+360h+StringSid]; StringSid
0x180068894  call    cs:__imp_ConvertSidToStringSidW
0x18006889a  test    eax, eax
0x18006889c  jnz     short loc_1800688AF
0x18006889e  call    cs:__imp_GetLastError
0x1800688a4  mov     ebx, eax
0x1800688a6  test    eax, eax
0x1800688a8  jle     short loc_1800688AF
0x1800688aa  movzx   ebx, ax
0x1800688ad  or      ebx, edi
0x1800688af  test    ebx, ebx
0x1800688b1  js      loc_18006897E
0x1800688b7  mov     r9, [rsp+360h+StringSid]
0x1800688bc  lea     r8, aSMlNwLwDAGaBaA; "S:(ML;;NW;;;LW)D:(A;;GA;;;BA)(A;;GA;;;O"...
0x1800688c3  mov     edx, 12Ch; unsigned __int64
0x1800688c8  lea     rcx, [rbp+260h+StringSecurityDescriptor]; unsigned __int16 *
0x1800688cc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800688d1  mov     ebx, eax
0x1800688d3  test    eax, eax
0x1800688d5  js      short loc_180068900
0x1800688d7  xor     r9d, r9d; SecurityDescriptorSize
0x1800688da  lea     r8, [rsp+360h+SecurityDescriptor]; SecurityDescriptor
0x1800688df  mov     edx, esi; StringSDRevision
0x1800688e1  lea     rcx, [rbp+260h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800688e5  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800688eb  test    eax, eax
0x1800688ed  jnz     short loc_180068900
0x1800688ef  call    cs:__imp_GetLastError
0x1800688f5  mov     ebx, eax
0x1800688f7  test    eax, eax
0x1800688f9  jle     short loc_180068900
0x1800688fb  movzx   ebx, ax
0x1800688fe  or      ebx, edi
0x180068900  mov     rcx, [rsp+360h+StringSid]; hMem
0x180068905  call    cs:__imp_LocalFree
0x18006890b  test    ebx, ebx
0x18006890d  js      short loc_18006897E
0x18006890f  mov     rax, [rsp+360h+SecurityDescriptor]
0x180068914  lea     rcx, aWebruntimediag; "WebRuntimeDiagnosticsBoundary"
0x18006891b  xor     edx, edx; Flags
0x18006891d  mov     [rsp+360h+PrivateNamespaceAttributes.lpSecurityDescriptor], rax
0x180068922  mov     qword ptr [rsp+360h+PrivateNamespaceAttributes.nLength], 18h
0x18006892b  mov     qword ptr [rsp+360h+PrivateNamespaceAttributes.bInheritHandle], 0
0x180068934  call    cs:__imp_CreateBoundaryDescriptorW
0x18006893a  mov     rsi, rax
0x18006893d  test    rax, rax
0x180068940  jnz     short loc_180068955
0x180068942  call    cs:__imp_GetLastError
0x180068948  mov     ebx, eax
0x18006894a  test    eax, eax
0x18006894c  jle     short loc_180068973
0x18006894e  movzx   ebx, ax
0x180068951  or      ebx, edi
0x180068953  jmp     short loc_180068973
0x180068955  lea     r8, aWebruntimediag; "WebRuntimeDiagnosticsBoundary"
0x18006895c  mov     rdx, rsi; lpBoundaryDescriptor
0x18006895f  lea     rcx, [rsp+360h+PrivateNamespaceAttributes]; lpPrivateNamespaceAttributes
0x180068964  call    cs:__imp_CreatePrivateNamespaceW
0x18006896a  mov     rcx, rsi; BoundaryDescriptor
0x18006896d  call    cs:__imp_DeleteBoundaryDescriptor
0x180068973  mov     rcx, [rsp+360h+SecurityDescriptor]; hMem
0x180068978  call    cs:__imp_LocalFree
0x18006897e  mov     eax, ebx
0x180068980  mov     rcx, [rbp+260h+var_30]
0x180068987  xor     rcx, rsp; StackCookie
0x18006898a  call    __security_check_cookie
0x18006898f  add     rsp, 348h
0x180068996  pop     rdi
0x180068997  pop     rsi
0x180068998  pop     rbx
0x180068999  pop     rbp
0x18006899a  retn
```
