# GetThreadIntegrityLevel(ulong *)

- ea: `0x180034f78`
- end: `0x180035103`
- name: `?GetThreadIntegrityLevel@@YAJPEAK@Z`
- size: `395`
- prototype: `HRESULT __fastcall(unsigned int *pdwIntegrityLevel)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e150`
- `0x18008c104`

## callees

- `0x18001c778`
- `0x180034f78`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180035009`
- `KERNELBASE!LocalAlloc` at `0x180035009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800350b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800350ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800350b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800350ce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180034fad`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180034fad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034f90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034f90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003508c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003508c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003507b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003507b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034fda`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003503d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034fda`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003503d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180035050`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180035050`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180035066`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180035066`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800350f5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800350f5`

## pseudocode

```c
__int64 __fastcall GetThreadIntegrityLevel(unsigned int *pdwIntegrityLevel)
{
  HANDLE CurrentThread; // rax
  PSID *v3; // rdi
  PUCHAR SidSubAuthorityCount; // rax
  signed int LastError; // ebx
  bool v6; // sf
  unsigned int dwLengthNeeded; // [rsp+48h] [rbp+10h] BYREF
  void *hToken; // [rsp+50h] [rbp+18h] BYREF

  hToken = 0;
  dwLengthNeeded = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x18u, 1, &hToken) )
  {
    if ( GetTokenInformation(hToken, TokenIntegrityLevel, 0, 0, &dwLengthNeeded) || GetLastError() != 122 )
    {
      LastError = GetLastError();
    }
    else
    {
      v3 = (PSID *)LocalAlloc(0, dwLengthNeeded);
      if ( v3 )
      {
        if ( GetTokenInformation(hToken, TokenIntegrityLevel, v3, dwLengthNeeded, &dwLengthNeeded) )
        {
          SidSubAuthorityCount = GetSidSubAuthorityCount(*v3);
          *pdwIntegrityLevel = *GetSidSubAuthority(*v3, (unsigned __int8)(*SidSubAuthorityCount - 1));
          LastError = 0;
        }
        else
        {
          LastError = GetLastError();
        }
        LocalFree(v3);
      }
      else
      {
        LastError = 14;
      }
    }
    CloseHandle(hToken);
    v6 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v6 = LastError < 0;
    }
    if ( v6 )
      OleInternalOriginateError(LastError, 0x13Au);
  }
  else
  {
    LastError = -2147418113;
    RoOriginateError(2147549183LL, 0);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180034f78  mov     [rsp+arg_0], rbx
0x180034f7d  push    rdi
0x180034f7e  sub     rsp, 30h
0x180034f82  and     [rsp+38h+hToken], 0
0x180034f88  mov     rbx, pdwIntegrityLevel
0x180034f8b  and     [rsp+38h+dwLengthNeeded], 0
0x180034f90  call    cs:__imp_GetCurrentThread
0x180034f97  nop     dword ptr [rax+rax+00h]
0x180034f9c  mov     edx, 18h; DesiredAccess
0x180034fa1  lea     r9, [rsp+38h+hToken]; TokenHandle
0x180034fa6  mov     pdwIntegrityLevel, rax; ThreadHandle
0x180034fa9  lea     r8d, [rdx-17h]; OpenAsSelf
0x180034fad  call    cs:__imp_OpenThreadToken
0x180034fb4  nop     dword ptr [rax+rax+00h]
0x180034fb9  test    eax, eax
0x180034fbb  jz      loc_1800350EC
0x180034fc1  mov     pdwIntegrityLevel, [rsp+38h+hToken]; TokenHandle
0x180034fc6  lea     rax, [rsp+38h+dwLengthNeeded]
0x180034fcb  xor     r9d, r9d; TokenInformationLength
0x180034fce  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180034fd3  xor     r8d, r8d; TokenInformation
0x180034fd6  lea     edx, [r9+19h]; TokenInformationClass
0x180034fda  call    cs:__imp_GetTokenInformation
0x180034fe1  nop     dword ptr [rax+rax+00h]
0x180034fe6  test    eax, eax
0x180034fe8  jnz     loc_1800350CE
0x180034fee  call    cs:__imp_GetLastError
0x180034ff5  nop     dword ptr [rax+rax+00h]
0x180034ffa  cmp     eax, 7Ah ; 'z'
0x180034ffd  jnz     loc_1800350CE
0x180035003  mov     edx, [rsp+38h+dwLengthNeeded]; uBytes
0x180035007  xor     ecx, ecx; uFlags
0x180035009  call    cs:__imp_LocalAlloc
0x180035010  nop     dword ptr [rax+rax+00h]
0x180035015  mov     rdi, rax
0x180035018  test    rax, rax
0x18003501b  jz      loc_1800350C7
0x180035021  mov     r9d, [rsp+38h+dwLengthNeeded]; TokenInformationLength
0x180035026  lea     rax, [rsp+38h+dwLengthNeeded]
0x18003502b  mov     pdwIntegrityLevel, [rsp+38h+hToken]; TokenHandle
0x180035030  mov     r8, rdi; TokenInformation
0x180035033  mov     edx, 19h; TokenInformationClass
0x180035038  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18003503d  call    cs:__imp_GetTokenInformation
0x180035044  nop     dword ptr [rax+rax+00h]
0x180035049  test    eax, eax
0x18003504b  jz      short loc_1800350B7
0x18003504d  mov     pdwIntegrityLevel, [rdi]; pSid
0x180035050  call    cs:__imp_GetSidSubAuthorityCount
0x180035057  nop     dword ptr [rax+rax+00h]
0x18003505c  mov     cl, [rax]
0x18003505e  dec     cl
0x180035060  movzx   edx, cl; nSubAuthority
0x180035063  mov     pdwIntegrityLevel, [rdi]; pSid
0x180035066  call    cs:__imp_GetSidSubAuthority
0x18003506d  nop     dword ptr [rax+rax+00h]
0x180035072  mov     ecx, [rax]
0x180035074  mov     [rbx], ecx
0x180035076  xor     ebx, ebx
0x180035078  mov     pdwIntegrityLevel, rdi; hMem
0x18003507b  call    cs:__imp_LocalFree
0x180035082  nop     dword ptr [rax+rax+00h]
0x180035087  mov     pdwIntegrityLevel, [rsp+38h+hToken]; hObject
0x18003508c  call    cs:__imp_CloseHandle
0x180035093  nop     dword ptr [rax+rax+00h]
0x180035098  test    ebx, ebx
0x18003509a  jle     short loc_1800350A7
0x18003509c  movzx   ebx, bx
0x18003509f  or      ebx, 80070000h
0x1800350a5  test    ebx, ebx
0x1800350a7  js      short loc_1800350DE
0x1800350a9  mov     eax, ebx
0x1800350ab  mov     rbx, [rsp+38h+arg_0]
0x1800350b0  add     rsp, 30h
0x1800350b4  pop     rdi
0x1800350b5  retn
0x1800350b7  call    cs:__imp_GetLastError
0x1800350be  nop     dword ptr [rax+rax+00h]
0x1800350c3  mov     ebx, eax
0x1800350c5  jmp     short loc_180035078
0x1800350c7  mov     ebx, 0Eh
0x1800350cc  jmp     short loc_180035087
0x1800350ce  call    cs:__imp_GetLastError
0x1800350d5  nop     dword ptr [rax+rax+00h]
0x1800350da  mov     ebx, eax
0x1800350dc  jmp     short loc_180035087
0x1800350de  mov     edx, 13Ah; messageID
0x1800350e3  mov     ecx, ebx; hr
0x1800350e5  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x1800350ea  jmp     short loc_1800350A9
0x1800350ec  mov     ebx, 8000FFFFh
0x1800350f1  xor     edx, edx
0x1800350f3  mov     ecx, ebx
0x1800350f5  call    cs:__imp_RoOriginateError
0x1800350fc  nop     dword ptr [rax+rax+00h]
0x180035101  jmp     short loc_1800350A9
```
