# GetTokenInformation_HeapFree<_TOKEN_DEFAULT_DACL>(void *,void *,_TOKEN_INFORMATION_CLASS,_TOKEN_DEFAULT_DACL * *)

- ea: `0x1800649d0`
- end: `0x180064a96`
- name: `??$GetTokenInformation_HeapFree@U_TOKEN_DEFAULT_DACL@@@@YAJPEAX0W4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_DEFAULT_DACL@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(HANDLE hHeap, HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180065324`

## callees

- `0x180025c18`
- `0x180050060`
- `0x1800649d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a0f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064a24`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064a24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064a6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064a6c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064a05`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064a4c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064a05`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064a4c`

## pseudocode

```c
__int64 __fastcall GetTokenInformation_HeapFree<_TOKEN_DEFAULT_DACL>(
        HANDLE hHeap,
        HANDLE TokenHandle,
        __int64 a3,
        _QWORD *a4)
{
  DWORD LastError; // eax
  void *v8; // rdi
  unsigned int ErrorError; // ebx
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenDefaultDacl, 0, 0, &TokenInformationLength) )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      v8 = HeapAlloc(hHeap, 0, TokenInformationLength);
      if ( v8 )
      {
        if ( GetTokenInformation(TokenHandle, TokenDefaultDacl, v8, TokenInformationLength, &TokenInformationLength) )
        {
          *a4 = v8;
          return 0;
        }
        else
        {
          ErrorError = HRESULTFromLastErrorError();
          HeapFree(hHeap, 0, v8);
        }
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      return (unsigned int)HRESULTFromWin32ErrorError(LastError);
    }
  }
  return ErrorError;
}

```

## disassembly

```asm
0x1800649d0  mov     [rsp+TokenInformationLength], r8d
0x1800649d5  push    rbx
0x1800649d6  push    rbp
0x1800649d7  push    rsi
0x1800649d8  push    rdi
0x1800649d9  sub     rsp, 38h
0x1800649dd  mov     rbp, rdx
0x1800649e0  mov     [rsp+58h+TokenInformationLength], 0
0x1800649e8  mov     rbx, r9
0x1800649eb  lea     rax, [rsp+58h+TokenInformationLength]
0x1800649f0  xor     r9d, r9d; TokenInformationLength
0x1800649f3  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800649f8  mov     rsi, rcx
0x1800649fb  xor     r8d, r8d; TokenInformation
0x1800649fe  mov     rcx, rbp; TokenHandle
0x180064a01  lea     edx, [r9+6]; TokenInformationClass
0x180064a05  call    cs:__imp_GetTokenInformation
0x180064a0b  test    eax, eax
0x180064a0d  jnz     short loc_180064A86
0x180064a0f  call    cs:__imp_GetLastError
0x180064a15  cmp     eax, 7Ah ; 'z'
0x180064a18  jnz     short loc_180064A7B
0x180064a1a  mov     r8d, [rsp+58h+TokenInformationLength]; dwBytes
0x180064a1f  xor     edx, edx; dwFlags
0x180064a21  mov     rcx, rsi; hHeap
0x180064a24  call    cs:__imp_HeapAlloc
0x180064a2a  mov     rdi, rax
0x180064a2d  test    rax, rax
0x180064a30  jz      short loc_180064A74
0x180064a32  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180064a37  lea     rax, [rsp+58h+TokenInformationLength]
0x180064a3c  mov     r8, rdi; TokenInformation
0x180064a3f  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180064a44  mov     edx, 6; TokenInformationClass
0x180064a49  mov     rcx, rbp; TokenHandle
0x180064a4c  call    cs:__imp_GetTokenInformation
0x180064a52  test    eax, eax
0x180064a54  jz      short loc_180064A5D
0x180064a56  mov     [rbx], rdi
0x180064a59  xor     ebx, ebx
0x180064a5b  jmp     short loc_180064A8B
0x180064a5d  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x180064a62  mov     r8, rdi; lpMem
0x180064a65  xor     edx, edx; dwFlags
0x180064a67  mov     rcx, rsi; hHeap
0x180064a6a  mov     ebx, eax
0x180064a6c  call    cs:__imp_HeapFree
0x180064a72  jmp     short loc_180064A8B
0x180064a74  mov     ebx, 8007000Eh
0x180064a79  jmp     short loc_180064A8B
0x180064a7b  mov     ecx, eax; unsigned int
0x180064a7d  call    ?HRESULTFromWin32ErrorError@@YAJK@Z; HRESULTFromWin32ErrorError(ulong)
0x180064a82  mov     ebx, eax
0x180064a84  jmp     short loc_180064A8B
0x180064a86  mov     ebx, 8000FFFFh
0x180064a8b  mov     eax, ebx
0x180064a8d  add     rsp, 38h
0x180064a91  pop     rdi
0x180064a92  pop     rsi
0x180064a93  pop     rbp
0x180064a94  pop     rbx
0x180064a95  retn
```
