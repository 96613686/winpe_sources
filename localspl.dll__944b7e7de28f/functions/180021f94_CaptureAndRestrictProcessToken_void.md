# CaptureAndRestrictProcessToken(void)

- ea: `0x180021f94`
- end: `0x18002213c`
- name: `?CaptureAndRestrictProcessToken@@YAHXZ`
- size: `424`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007685c`

## callees

- `0x180011e64`
- `0x180011ed0`
- `0x180021f94`
- `0x180046aa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002203c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002203c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022031`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022112`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022031`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022112`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021fa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021fa9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180021fbd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180021fbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002212c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002212c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180021ff3`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180021ff3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022024`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022097`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022024`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022097`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180022103`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180022103`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800220ae`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800220ae`

## string_xrefs

- `0x1800220a5`: `SeLoadDriverPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CaptureAndRestrictProcessToken(void)
{
  unsigned int v0; // edi
  HANDLE CurrentProcess; // rax
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rax
  struct _TOKEN_PRIVILEGES *v5; // rbx
  void *v6; // rcx
  __int64 i; // rcx
  void *v8; // rcx
  DWORD ReturnLength; // [rsp+50h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+28h] BYREF
  struct _LUID Luid; // [rsp+60h] [rbp+30h] BYREF
  LPVOID TokenInformation; // [rsp+68h] [rbp+38h] BYREF

  v0 = 0;
  TokenHandle = (void *)-1LL;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xF01FFu, &TokenHandle) )
  {
    v2 = TokenHandle;
    if ( TokenHandle == (void *)-1LL )
      v2 = 0;
    if ( DuplicateTokenEx(v2, 0xF01FFu, 0, SecurityImpersonation, TokenImpersonation, &g_hOriginalProcessToken) )
    {
      ReturnLength = 0;
      v3 = TokenHandle;
      if ( TokenHandle == (void *)-1LL )
        v3 = 0;
      if ( GetTokenInformation(v3, TokenPrivileges, 0, 0, &ReturnLength) )
      {
        SetLastError(1u);
      }
      else if ( GetLastError() == 122 )
      {
        v4 = operator new[](ReturnLength);
        NCoreLibrary::TAutoPtrArray<PrintNamedProperty>::TAutoPtrArray<PrintNamedProperty>(&TokenInformation, v4);
        v5 = (struct _TOKEN_PRIVILEGES *)TokenInformation;
        if ( TokenInformation )
        {
          Luid = 0;
          v6 = TokenHandle;
          if ( TokenHandle == (void *)-1LL )
            v6 = 0;
          if ( GetTokenInformation(v6, TokenPrivileges, TokenInformation, ReturnLength, &ReturnLength)
            && LookupPrivilegeValueW(0, L"SeLoadDriverPrivilege", &Luid) )
          {
            for ( i = 0; (unsigned int)i < v5->PrivilegeCount; i = (unsigned int)(i + 1) )
            {
              if ( v5->Privileges[i].Luid.LowPart == Luid.LowPart && v5->Privileges[i].Luid.HighPart == Luid.HighPart )
                v5->Privileges[i].Attributes = 4;
            }
            v8 = TokenHandle;
            if ( TokenHandle == (void *)-1LL )
              v8 = 0;
            v0 = AdjustTokenPrivileges(v8, 0, v5, ReturnLength, 0, 0);
          }
        }
        else
        {
          SetLastError(8u);
        }
        NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&TokenInformation);
      }
    }
  }
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  return v0;
}

```

## disassembly

```asm
0x180021f94  push    rbp
0x180021f96  push    rbx
0x180021f97  push    rdi
0x180021f98  mov     rbp, rsp
0x180021f9b  sub     rsp, 30h
0x180021f9f  xor     edi, edi
0x180021fa1  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180021fa9  call    cs:__imp_GetCurrentProcess
0x180021faf  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180021fb3  mov     ebx, 0F01FFh
0x180021fb8  mov     edx, ebx; DesiredAccess
0x180021fba  mov     rcx, rax; ProcessHandle
0x180021fbd  call    cs:__imp_OpenProcessToken
0x180021fc3  test    eax, eax
0x180021fc5  jz      loc_180022122
0x180021fcb  mov     rcx, [rbp+TokenHandle]
0x180021fcf  xor     eax, eax
0x180021fd1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180021fd5  cmovz   rcx, rax; hExistingToken
0x180021fd9  lea     rax, ?g_hOriginalProcessToken@@3PEAXEA; void * g_hOriginalProcessToken
0x180021fe0  mov     [rsp+30h+phNewToken], rax; phNewToken
0x180021fe5  lea     r9d, [rdi+2]; ImpersonationLevel
0x180021fe9  mov     [rsp+30h+TokenType], r9d; TokenType
0x180021fee  xor     r8d, r8d; lpTokenAttributes
0x180021ff1  mov     edx, ebx; dwDesiredAccess
0x180021ff3  call    cs:__imp_DuplicateTokenEx
0x180021ff9  test    eax, eax
0x180021ffb  jz      loc_180022122
0x180022001  mov     [rbp+ReturnLength], edi
0x180022004  mov     rcx, [rbp+TokenHandle]
0x180022008  xor     eax, eax
0x18002200a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002200e  cmovz   rcx, rax; TokenHandle
0x180022012  lea     rax, [rbp+ReturnLength]
0x180022016  mov     qword ptr [rsp+30h+TokenType], rax; ReturnLength
0x18002201b  xor     r9d, r9d; TokenInformationLength
0x18002201e  xor     r8d, r8d; TokenInformation
0x180022021  lea     edx, [rdi+3]; TokenInformationClass
0x180022024  call    cs:__imp_GetTokenInformation
0x18002202a  test    eax, eax
0x18002202c  jz      short loc_18002203C
0x18002202e  lea     ecx, [rdi+1]; dwErrCode
0x180022031  call    cs:__imp_SetLastError
0x180022037  jmp     loc_180022122
0x18002203c  call    cs:__imp_GetLastError
0x180022042  cmp     eax, 7Ah ; 'z'
0x180022045  jnz     loc_180022122
0x18002204b  mov     ecx, [rbp+ReturnLength]; unsigned __int64
0x18002204e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180022053  mov     rdx, rax
0x180022056  lea     rcx, [rbp+TokenInformation]
0x18002205a  call    ??0?$TAutoPtrArray@UPrintNamedProperty@@@NCoreLibrary@@QEAA@PEAUPrintNamedProperty@@@Z; NCoreLibrary::TAutoPtrArray<PrintNamedProperty>::TAutoPtrArray<PrintNamedProperty>(PrintNamedProperty *)
0x18002205f  mov     rbx, [rbp+TokenInformation]
0x180022063  test    rbx, rbx
0x180022066  jz      loc_18002210D
0x18002206c  mov     qword ptr [rbp+Luid.LowPart], 0
0x180022074  mov     rcx, [rbp+TokenHandle]
0x180022078  xor     eax, eax
0x18002207a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002207e  cmovz   rcx, rax; TokenHandle
0x180022082  lea     rax, [rbp+ReturnLength]
0x180022086  mov     qword ptr [rsp+30h+TokenType], rax; ReturnLength
0x18002208b  mov     r9d, [rbp+ReturnLength]; TokenInformationLength
0x18002208f  mov     r8, rbx; TokenInformation
0x180022092  mov     edx, 3; TokenInformationClass
0x180022097  call    cs:__imp_GetTokenInformation
0x18002209d  test    eax, eax
0x18002209f  jz      short loc_180022118
0x1800220a1  lea     r8, [rbp+Luid]; lpLuid
0x1800220a5  lea     rdx, Name; "SeLoadDriverPrivilege"
0x1800220ac  xor     ecx, ecx; lpSystemName
0x1800220ae  call    cs:__imp_LookupPrivilegeValueW
0x1800220b4  test    eax, eax
0x1800220b6  jz      short loc_180022118
0x1800220b8  xor     ecx, ecx
0x1800220ba  cmp     [rbx], ecx
0x1800220bc  jbe     short loc_1800220E2
0x1800220be  lea     rdx, [rcx+rcx*2]
0x1800220c2  mov     eax, [rbp+Luid.LowPart]
0x1800220c5  cmp     [rbx+rdx*4+4], eax
0x1800220c9  jnz     short loc_1800220DC
0x1800220cb  mov     eax, [rbp+Luid.HighPart]
0x1800220ce  cmp     [rbx+rdx*4+8], eax
0x1800220d2  jnz     short loc_1800220DC
0x1800220d4  mov     dword ptr [rbx+rdx*4+0Ch], 4
0x1800220dc  inc     ecx
0x1800220de  cmp     ecx, [rbx]
0x1800220e0  jb      short loc_1800220BE
0x1800220e2  mov     rcx, [rbp+TokenHandle]
0x1800220e6  xor     eax, eax
0x1800220e8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800220ec  cmovz   rcx, rax; TokenHandle
0x1800220f0  mov     [rsp+30h+phNewToken], rax; ReturnLength
0x1800220f5  mov     qword ptr [rsp+30h+TokenType], rax; PreviousState
0x1800220fa  mov     r9d, [rbp+ReturnLength]; BufferLength
0x1800220fe  mov     r8, rbx; NewState
0x180022101  xor     edx, edx; DisableAllPrivileges
0x180022103  call    cs:__imp_AdjustTokenPrivileges
0x180022109  mov     edi, eax
0x18002210b  jmp     short loc_180022118
0x18002210d  mov     ecx, 8; dwErrCode
0x180022112  call    cs:__imp_SetLastError
0x180022118  lea     rcx, [rbp+TokenInformation]
0x18002211c  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x180022121  nop
0x180022122  mov     rcx, [rbp+TokenHandle]; hObject
0x180022126  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002212a  jz      short loc_180022132
0x18002212c  call    cs:__imp_CloseHandle
0x180022132  mov     eax, edi
0x180022134  add     rsp, 30h
0x180022138  pop     rdi
0x180022139  pop     rbx
0x18002213a  pop     rbp
0x18002213b  retn
```
