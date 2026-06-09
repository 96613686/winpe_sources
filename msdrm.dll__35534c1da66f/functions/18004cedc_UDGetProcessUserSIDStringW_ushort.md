# UDGetProcessUserSIDStringW(ushort * *)

- ea: `0x18004cedc`
- end: `0x18004d021`
- name: `?UDGetProcessUserSIDStringW@@YAJPEAPEAG@Z`
- size: `325`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180035184`
- `0x1800379a4`

## callees

- `0x18004cedc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cf6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cfcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cf6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cfcf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004cf08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004cf08`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004cf23`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004cf23`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004cf3d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004cf3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004cf2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004cf2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d006`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d006`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004cfc3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004cfc3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004cf62`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004cfb1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004cf62`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004cfb1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cf83`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cf83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ceff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ceff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004cff6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004cff6`

## pseudocode

```c
__int64 __fastcall UDGetProcessUserSIDStringW(LPWSTR *StringSid)
{
  PSID *v1; // rdi
  HANDLE ProcessHeap; // rbp
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  BOOL TokenInformation; // esi
  signed int v7; // ebx
  signed int LastError; // eax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  v1 = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  ProcessHeap = GetProcessHeap();
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle)
    || (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle)) )
  {
    TokenInformation = GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( TokenInformation || GetLastError() == 122 )
    {
      v1 = (PSID *)HeapAlloc(ProcessHeap, 0, TokenInformationLength);
      if ( !v1 )
      {
        v7 = -2147024882;
        goto LABEL_9;
      }
      if ( GetTokenInformation(TokenHandle, TokenUser, v1, TokenInformationLength, &TokenInformationLength) )
      {
        v7 = 0;
        TokenInformation = ConvertSidToStringSidW(*v1, StringSid);
LABEL_9:
        if ( TokenInformation )
          goto LABEL_14;
      }
    }
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
    v7 = -2147467259;
LABEL_14:
  HeapFree(ProcessHeap, 0, v1);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004cedc  mov     rax, rsp
0x18004cedf  mov     [rax+8], rbx
0x18004cee3  mov     [rax+20h], rbp
0x18004cee7  push    rsi
0x18004cee8  push    rdi
0x18004cee9  push    r14
0x18004ceeb  sub     rsp, 30h
0x18004ceef  xor     edi, edi
0x18004cef1  mov     qword ptr [rax+18h], 0
0x18004cef9  mov     [rax+10h], edi
0x18004cefc  mov     r14, rcx
0x18004ceff  call    cs:__imp_GetProcessHeap
0x18004cf05  mov     rbp, rax
0x18004cf08  call    cs:__imp_GetCurrentThread
0x18004cf0e  lea     ebx, [rdi+1]
0x18004cf11  mov     esi, 20008h
0x18004cf16  mov     rcx, rax; ThreadHandle
0x18004cf19  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18004cf1e  mov     r8d, ebx; OpenAsSelf
0x18004cf21  mov     edx, esi; DesiredAccess
0x18004cf23  call    cs:__imp_OpenThreadToken
0x18004cf29  test    eax, eax
0x18004cf2b  jnz     short loc_18004CF4B
0x18004cf2d  call    cs:__imp_GetCurrentProcess
0x18004cf33  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x18004cf38  mov     edx, esi; DesiredAccess
0x18004cf3a  mov     rcx, rax; ProcessHandle
0x18004cf3d  call    cs:__imp_OpenProcessToken
0x18004cf43  test    eax, eax
0x18004cf45  jz      loc_18004CFCF
0x18004cf4b  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18004cf50  lea     rax, [rsp+48h+TokenInformationLength]
0x18004cf55  xor     r9d, r9d; TokenInformationLength
0x18004cf58  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18004cf5d  xor     r8d, r8d; TokenInformation
0x18004cf60  mov     edx, ebx; TokenInformationClass
0x18004cf62  call    cs:__imp_GetTokenInformation
0x18004cf68  mov     esi, eax
0x18004cf6a  test    eax, eax
0x18004cf6c  jnz     short loc_18004CF79
0x18004cf6e  call    cs:__imp_GetLastError
0x18004cf74  cmp     eax, 7Ah ; 'z'
0x18004cf77  jnz     short loc_18004CFCF
0x18004cf79  mov     r8d, [rsp+48h+TokenInformationLength]; dwBytes
0x18004cf7e  xor     edx, edx; dwFlags
0x18004cf80  mov     rcx, rbp; hHeap
0x18004cf83  call    cs:__imp_HeapAlloc
0x18004cf89  mov     rdi, rax
0x18004cf8c  test    rax, rax
0x18004cf8f  jnz     short loc_18004CF98
0x18004cf91  mov     ebx, 8007000Eh
0x18004cf96  jmp     short loc_18004CFCB
0x18004cf98  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18004cf9d  lea     rax, [rsp+48h+TokenInformationLength]
0x18004cfa2  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18004cfa7  mov     r8, rdi; TokenInformation
0x18004cfaa  mov     edx, ebx; TokenInformationClass
0x18004cfac  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18004cfb1  call    cs:__imp_GetTokenInformation
0x18004cfb7  test    eax, eax
0x18004cfb9  jz      short loc_18004CFCF
0x18004cfbb  mov     rcx, [rdi]; Sid
0x18004cfbe  xor     ebx, ebx
0x18004cfc0  mov     rdx, r14; StringSid
0x18004cfc3  call    cs:__imp_ConvertSidToStringSidW
0x18004cfc9  mov     esi, eax
0x18004cfcb  test    esi, esi
0x18004cfcd  jnz     short loc_18004CFEE
0x18004cfcf  call    cs:__imp_GetLastError
0x18004cfd5  mov     ebx, eax
0x18004cfd7  test    eax, eax
0x18004cfd9  jle     short loc_18004CFE4
0x18004cfdb  movzx   ebx, ax
0x18004cfde  or      ebx, 80070000h
0x18004cfe4  test    ebx, ebx
0x18004cfe6  mov     eax, 80004005h
0x18004cfeb  cmovns  ebx, eax
0x18004cfee  mov     r8, rdi; lpMem
0x18004cff1  xor     edx, edx; dwFlags
0x18004cff3  mov     rcx, rbp; hHeap
0x18004cff6  call    cs:__imp_HeapFree
0x18004cffc  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18004d001  test    rcx, rcx
0x18004d004  jz      short loc_18004D00C
0x18004d006  call    cs:__imp_CloseHandle
0x18004d00c  mov     rbp, [rsp+48h+arg_18]
0x18004d011  mov     eax, ebx
0x18004d013  mov     rbx, [rsp+48h+arg_0]
0x18004d018  add     rsp, 30h
0x18004d01c  pop     r14
0x18004d01e  pop     rdi
0x18004d01f  pop     rsi
0x18004d020  retn
```
