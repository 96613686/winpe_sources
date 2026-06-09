# GetTokenInformation_HeapFree<_TOKEN_USER>(void *,void *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER * *)

- ea: `0x180064a9c`
- end: `0x180064b62`
- name: `??$GetTokenInformation_HeapFree@U_TOKEN_USER@@@@YAJPEAX0W4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_USER@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(HANDLE hHeap, HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180065324`

## callees

- `0x180025c18`
- `0x180050060`
- `0x180064a9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064adb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064adb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064af0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064af0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064b38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064b38`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064ad1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064b18`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064ad1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064b18`

## pseudocode

```c
__int64 __fastcall GetTokenInformation_HeapFree<_TOKEN_USER>(HANDLE hHeap, HANDLE TokenHandle, __int64 a3, _QWORD *a4)
{
  DWORD LastError; // eax
  void *v8; // rdi
  unsigned int ErrorError; // ebx
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
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
        if ( GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
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
0x180064a9c  mov     [rsp+TokenInformationLength], r8d
0x180064aa1  push    rbx
0x180064aa2  push    rbp
0x180064aa3  push    rsi
0x180064aa4  push    rdi
0x180064aa5  sub     rsp, 38h
0x180064aa9  mov     rbp, rdx
0x180064aac  mov     [rsp+58h+TokenInformationLength], 0
0x180064ab4  mov     rbx, r9
0x180064ab7  lea     rax, [rsp+58h+TokenInformationLength]
0x180064abc  xor     r9d, r9d; TokenInformationLength
0x180064abf  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180064ac4  mov     rsi, rcx
0x180064ac7  xor     r8d, r8d; TokenInformation
0x180064aca  mov     rcx, rbp; TokenHandle
0x180064acd  lea     edx, [r9+1]; TokenInformationClass
0x180064ad1  call    cs:__imp_GetTokenInformation
0x180064ad7  test    eax, eax
0x180064ad9  jnz     short loc_180064B52
0x180064adb  call    cs:__imp_GetLastError
0x180064ae1  cmp     eax, 7Ah ; 'z'
0x180064ae4  jnz     short loc_180064B47
0x180064ae6  mov     r8d, [rsp+58h+TokenInformationLength]; dwBytes
0x180064aeb  xor     edx, edx; dwFlags
0x180064aed  mov     rcx, rsi; hHeap
0x180064af0  call    cs:__imp_HeapAlloc
0x180064af6  mov     rdi, rax
0x180064af9  test    rax, rax
0x180064afc  jz      short loc_180064B40
0x180064afe  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180064b03  lea     rax, [rsp+58h+TokenInformationLength]
0x180064b08  mov     r8, rdi; TokenInformation
0x180064b0b  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180064b10  mov     edx, 1; TokenInformationClass
0x180064b15  mov     rcx, rbp; TokenHandle
0x180064b18  call    cs:__imp_GetTokenInformation
0x180064b1e  test    eax, eax
0x180064b20  jz      short loc_180064B29
0x180064b22  mov     [rbx], rdi
0x180064b25  xor     ebx, ebx
0x180064b27  jmp     short loc_180064B57
0x180064b29  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x180064b2e  mov     r8, rdi; lpMem
0x180064b31  xor     edx, edx; dwFlags
0x180064b33  mov     rcx, rsi; hHeap
0x180064b36  mov     ebx, eax
0x180064b38  call    cs:__imp_HeapFree
0x180064b3e  jmp     short loc_180064B57
0x180064b40  mov     ebx, 8007000Eh
0x180064b45  jmp     short loc_180064B57
0x180064b47  mov     ecx, eax; unsigned int
0x180064b49  call    ?HRESULTFromWin32ErrorError@@YAJK@Z; HRESULTFromWin32ErrorError(ulong)
0x180064b4e  mov     ebx, eax
0x180064b50  jmp     short loc_180064B57
0x180064b52  mov     ebx, 8000FFFFh
0x180064b57  mov     eax, ebx
0x180064b59  add     rsp, 38h
0x180064b5d  pop     rdi
0x180064b5e  pop     rsi
0x180064b5f  pop     rbp
0x180064b60  pop     rbx
0x180064b61  retn
```
