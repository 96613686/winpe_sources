# CMbaeMutexFactory::_GetCurrentUserSid(ushort * *)

- ea: `0x180031aec`
- end: `0x180031c21`
- name: `?_GetCurrentUserSid@CMbaeMutexFactory@@CAJPEAPEAG@Z`
- size: `309`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031c28`

## callees

- `0x180014410`
- `0x180031aec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031b6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031b6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031bef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031bef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031b5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031be1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031b5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031be1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031b15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031b15`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180031b25`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180031b25`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031b49`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031b92`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031b49`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031b92`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180031ba3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180031ba3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031bd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031bd6`

## string_xrefs

- `0x180031c01`: `CMbaeMutexFactory::_GetCurrentUserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMbaeMutexFactory::_GetCurrentUserSid(unsigned __int16 **a1)
{
  PSID *v1; // rdi
  HANDLE CurrentProcess; // rax
  DWORD v4; // r14d
  HANDLE ProcessHeap; // rax
  unsigned int v6; // ebx
  signed int LastError; // eax
  LPWSTR v8; // rcx
  HANDLE v9; // rax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF
  LPWSTR StringSid; // [rsp+70h] [rbp+40h] BYREF

  v1 = 0;
  TokenHandle = 0;
  StringSid = 0;
  *a1 = 0;
  TokenInformationLength = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( GetLastError() == 122 )
    {
      v4 = TokenInformationLength;
      ProcessHeap = GetProcessHeap();
      v1 = (PSID *)HeapAlloc(ProcessHeap, 0, v4);
      if ( v1 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v1, v4, &TokenInformationLength)
          && ConvertSidToStringSidW(*v1, &StringSid) )
        {
          v6 = 0;
          *a1 = StringSid;
LABEL_12:
          v9 = GetProcessHeap();
          HeapFree(v9, 0, v1);
          goto LABEL_13;
        }
      }
    }
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  v8 = StringSid;
  if ( StringSid )
    LocalFree(StringSid);
  if ( v1 )
    goto LABEL_12;
LABEL_13:
  if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
    McTemplateU0sd_EventWriteTransfer(v8, CMbaeMutexFactory_cpp180, "CMbaeMutexFactory::_GetCurrentUserSid", v6);
  return v6;
}

```

## disassembly

```asm
0x180031aec  push    rbp
0x180031aee  push    rbx
0x180031aef  push    rsi
0x180031af0  push    rdi
0x180031af1  push    r14
0x180031af3  mov     rbp, rsp
0x180031af6  sub     rsp, 30h
0x180031afa  xor     edi, edi
0x180031afc  mov     [rbp+TokenHandle], 0
0x180031b04  mov     [rbp+StringSid], rdi
0x180031b08  mov     rsi, rcx
0x180031b0b  mov     [rcx], rdi
0x180031b0e  mov     [rbp+TokenInformationLength], 0
0x180031b15  call    cs:__imp_GetCurrentProcess
0x180031b1b  mov     rcx, rax; ProcessHandle
0x180031b1e  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180031b22  lea     edx, [rdi+8]; DesiredAccess
0x180031b25  call    cs:__imp_OpenProcessToken
0x180031b2b  test    eax, eax
0x180031b2d  jz      loc_180031BB8
0x180031b33  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180031b37  lea     rax, [rbp+TokenInformationLength]
0x180031b3b  xor     r9d, r9d; TokenInformationLength
0x180031b3e  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180031b43  xor     r8d, r8d; TokenInformation
0x180031b46  lea     edx, [rdi+1]; TokenInformationClass
0x180031b49  call    cs:__imp_GetTokenInformation
0x180031b4f  call    cs:__imp_GetLastError
0x180031b55  cmp     eax, 7Ah ; 'z'
0x180031b58  jnz     short loc_180031BB8
0x180031b5a  mov     r14d, [rbp+TokenInformationLength]
0x180031b5e  call    cs:__imp_GetProcessHeap
0x180031b64  mov     r8d, r14d; dwBytes
0x180031b67  xor     edx, edx; dwFlags
0x180031b69  mov     rcx, rax; hHeap
0x180031b6c  call    cs:__imp_HeapAlloc
0x180031b72  mov     rdi, rax
0x180031b75  test    rax, rax
0x180031b78  jz      short loc_180031BB8
0x180031b7a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180031b7e  lea     rax, [rbp+TokenInformationLength]
0x180031b82  mov     r9d, r14d; TokenInformationLength
0x180031b85  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180031b8a  mov     r8, rdi; TokenInformation
0x180031b8d  mov     edx, 1; TokenInformationClass
0x180031b92  call    cs:__imp_GetTokenInformation
0x180031b98  test    eax, eax
0x180031b9a  jz      short loc_180031BB8
0x180031b9c  mov     rcx, [rdi]; Sid
0x180031b9f  lea     rdx, [rbp+StringSid]; StringSid
0x180031ba3  call    cs:__imp_ConvertSidToStringSidW
0x180031ba9  test    eax, eax
0x180031bab  jz      short loc_180031BB8
0x180031bad  mov     rax, [rbp+StringSid]
0x180031bb1  xor     ebx, ebx
0x180031bb3  mov     [rsi], rax
0x180031bb6  jmp     short loc_180031BE1
0x180031bb8  call    cs:__imp_GetLastError
0x180031bbe  mov     ebx, eax
0x180031bc0  test    eax, eax
0x180031bc2  jle     short loc_180031BCD
0x180031bc4  movzx   ebx, ax
0x180031bc7  or      ebx, 80070000h
0x180031bcd  mov     rcx, [rbp+StringSid]; hMem
0x180031bd1  test    rcx, rcx
0x180031bd4  jz      short loc_180031BDC
0x180031bd6  call    cs:__imp_LocalFree
0x180031bdc  test    rdi, rdi
0x180031bdf  jz      short loc_180031BF5
0x180031be1  call    cs:__imp_GetProcessHeap
0x180031be7  mov     r8, rdi; lpMem
0x180031bea  xor     edx, edx; dwFlags
0x180031bec  mov     rcx, rax; hHeap
0x180031bef  call    cs:__imp_HeapFree
0x180031bf5  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 1
0x180031bfc  jz      short loc_180031C14
0x180031bfe  mov     r9d, ebx
0x180031c01  lea     r8, aCmbaemutexfact; "CMbaeMutexFactory::_GetCurrentUserSid"
0x180031c08  lea     rdx, CMbaeMutexFactory_cpp180
0x180031c0f  call    McTemplateU0sd_EventWriteTransfer
0x180031c14  mov     eax, ebx
0x180031c16  add     rsp, 30h
0x180031c1a  pop     r14
0x180031c1c  pop     rdi
0x180031c1d  pop     rsi
0x180031c1e  pop     rbx
0x180031c1f  pop     rbp
0x180031c20  retn
```
