# CscSec_GetSidFromToken(void *,void * *)

- ea: `0x18003598c`
- end: `0x180035a50`
- name: `?CscSec_GetSidFromToken@@YAJPEAXPEAPEAX@Z`
- size: `196`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18002bcec`
- `0x18002d014`
- `0x18003365c`
- `0x18004122c`

## callees

- `0x18000d640`
- `0x1800262bc`
- `0x18002f10c`
- `0x18003443c`
- `0x18003598c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800359c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800359c4`
- `ADVAPI32!GetTokenInformation` at `0x1800359ba`
- `ADVAPI32!GetTokenInformation` at `0x180035a0b`
- `ADVAPI32!GetTokenInformation` at `0x1800359ba`
- `ADVAPI32!GetTokenInformation` at `0x180035a0b`

## pseudocode

```c
__int64 __fastcall CscSec_GetSidFromToken(HANDLE TokenHandle, void **a2)
{
  int v4; // ebx
  PSID *v5; // rdi
  int SidCopy; // eax
  void *v7; // rdx
  DWORD TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF
  LPVOID TokenInformation; // [rsp+68h] [rbp+20h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    return (unsigned int)-2147467259;
  }
  else if ( GetLastError() == 122 )
  {
    TokenInformation = 0;
    v4 = CscUtil_HeapAllocArray<unsigned char>(TokenInformationLength, &TokenInformation);
    if ( v4 >= 0 )
    {
      v5 = (PSID *)TokenInformation;
      if ( GetTokenInformation(
             TokenHandle,
             TokenUser,
             TokenInformation,
             TokenInformationLength,
             &TokenInformationLength) )
      {
        SidCopy = CscSec_CreateSidCopy(*v5, a2);
      }
      else
      {
        SidCopy = ResultFromLastError();
      }
      v4 = SidCopy;
      CscUtil_HeapFree(v5, v7);
    }
  }
  else
  {
    return (unsigned int)ResultFromLastError();
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003598c  mov     [rsp+arg_0], rbx
0x180035991  push    rbp
0x180035992  push    rsi
0x180035993  push    rdi
0x180035994  sub     rsp, 30h
0x180035998  xor     r9d, r9d; TokenInformationLength
0x18003599b  mov     [rsp+48h+TokenInformationLength], 0
0x1800359a3  mov     rsi, rdx
0x1800359a6  lea     rax, [rsp+48h+TokenInformationLength]
0x1800359ab  xor     r8d, r8d; TokenInformation
0x1800359ae  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800359b3  mov     rbp, rcx
0x1800359b6  lea     edx, [r9+1]; TokenInformationClass
0x1800359ba  call    cs:__imp_GetTokenInformation
0x1800359c0  test    eax, eax
0x1800359c2  jnz     short loc_180035A3C
0x1800359c4  call    cs:__imp_GetLastError
0x1800359ca  cmp     eax, 7Ah ; 'z'
0x1800359cd  jnz     short loc_180035A33
0x1800359cf  mov     ecx, [rsp+48h+TokenInformationLength]
0x1800359d3  lea     rdx, [rsp+48h+TokenInformation]
0x1800359d8  mov     [rsp+48h+TokenInformation], 0
0x1800359e1  call    ??$CscUtil_HeapAllocArray@E@@YAJ_KPEAPEAE@Z; CscUtil_HeapAllocArray<uchar>(unsigned __int64,uchar * *)
0x1800359e6  mov     ebx, eax
0x1800359e8  test    eax, eax
0x1800359ea  js      short loc_180035A41
0x1800359ec  mov     rdi, [rsp+48h+TokenInformation]
0x1800359f1  lea     rax, [rsp+48h+TokenInformationLength]
0x1800359f6  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x1800359fb  mov     r8, rdi; TokenInformation
0x1800359fe  mov     edx, 1; TokenInformationClass
0x180035a03  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180035a08  mov     rcx, rbp; TokenHandle
0x180035a0b  call    cs:__imp_GetTokenInformation
0x180035a11  test    eax, eax
0x180035a13  jz      short loc_180035A22
0x180035a15  mov     rcx, [rdi]; pSourceSid
0x180035a18  mov     rdx, rsi; void **
0x180035a1b  call    ?CscSec_CreateSidCopy@@YAJPEAXPEAPEAX@Z; CscSec_CreateSidCopy(void *,void * *)
0x180035a20  jmp     short loc_180035A27
0x180035a22  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180035a27  mov     rcx, rdi; lpMem
0x180035a2a  mov     ebx, eax
0x180035a2c  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180035a31  jmp     short loc_180035A41
0x180035a33  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180035a38  mov     ebx, eax
0x180035a3a  jmp     short loc_180035A41
0x180035a3c  mov     ebx, 80004005h
0x180035a41  mov     eax, ebx
0x180035a43  mov     rbx, [rsp+48h+arg_0]
0x180035a48  add     rsp, 30h
0x180035a4c  pop     rdi
0x180035a4d  pop     rsi
0x180035a4e  pop     rbp
0x180035a4f  retn
```
