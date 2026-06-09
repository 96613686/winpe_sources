# GetTokenInformation_HeapFree<_SID_AND_ATTRIBUTES>(void *,void *,_TOKEN_INFORMATION_CLASS,_SID_AND_ATTRIBUTES * *)

- ea: `0x180032870`
- end: `0x180032936`
- name: `??$GetTokenInformation_HeapFree@U_SID_AND_ATTRIBUTES@@@@YAJPEAX0W4_TOKEN_INFORMATION_CLASS@@PEAPEAU_SID_AND_ATTRIBUTES@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(HANDLE hHeap, HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800327b0`

## callees

- `0x180025c18`
- `0x180032870`
- `0x180050060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800328af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800328af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800328c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800328c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032923`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032923`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800328a5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800328ec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800328a5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800328ec`

## pseudocode

```c
__int64 __fastcall GetTokenInformation_HeapFree<_SID_AND_ATTRIBUTES>(
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
0x180032870  mov     [rsp+TokenInformationLength], r8d
0x180032875  push    rbx
0x180032876  push    rbp
0x180032877  push    rsi
0x180032878  push    rdi
0x180032879  sub     rsp, 38h
0x18003287d  mov     rbp, rdx
0x180032880  mov     [rsp+58h+TokenInformationLength], 0
0x180032888  mov     rbx, r9
0x18003288b  lea     rax, [rsp+58h+TokenInformationLength]
0x180032890  xor     r9d, r9d; TokenInformationLength
0x180032893  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180032898  mov     rsi, rcx
0x18003289b  xor     r8d, r8d; TokenInformation
0x18003289e  mov     rcx, rbp; TokenHandle
0x1800328a1  lea     edx, [r9+1]; TokenInformationClass
0x1800328a5  call    cs:__imp_GetTokenInformation
0x1800328ab  test    eax, eax
0x1800328ad  jnz     short loc_180032906
0x1800328af  call    cs:__imp_GetLastError
0x1800328b5  cmp     eax, 7Ah ; 'z'
0x1800328b8  jnz     short loc_18003292B
0x1800328ba  mov     r8d, [rsp+58h+TokenInformationLength]; dwBytes
0x1800328bf  xor     edx, edx; dwFlags
0x1800328c1  mov     rcx, rsi; hHeap
0x1800328c4  call    cs:__imp_HeapAlloc
0x1800328ca  mov     rdi, rax
0x1800328cd  test    rax, rax
0x1800328d0  jz      short loc_18003290D
0x1800328d2  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1800328d7  lea     rax, [rsp+58h+TokenInformationLength]
0x1800328dc  mov     r8, rdi; TokenInformation
0x1800328df  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800328e4  mov     edx, 1; TokenInformationClass
0x1800328e9  mov     rcx, rbp; TokenHandle
0x1800328ec  call    cs:__imp_GetTokenInformation
0x1800328f2  test    eax, eax
0x1800328f4  jz      short loc_180032914
0x1800328f6  mov     [rbx], rdi
0x1800328f9  xor     ebx, ebx
0x1800328fb  mov     eax, ebx
0x1800328fd  add     rsp, 38h
0x180032901  pop     rdi
0x180032902  pop     rsi
0x180032903  pop     rbp
0x180032904  pop     rbx
0x180032905  retn
0x180032906  mov     ebx, 8000FFFFh
0x18003290b  jmp     short loc_1800328FB
0x18003290d  mov     ebx, 8007000Eh
0x180032912  jmp     short loc_1800328FB
0x180032914  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x180032919  mov     r8, rdi; lpMem
0x18003291c  xor     edx, edx; dwFlags
0x18003291e  mov     rcx, rsi; hHeap
0x180032921  mov     ebx, eax
0x180032923  call    cs:__imp_HeapFree
0x180032929  jmp     short loc_1800328FB
0x18003292b  mov     ecx, eax; unsigned int
0x18003292d  call    ?HRESULTFromWin32ErrorError@@YAJK@Z; HRESULTFromWin32ErrorError(ulong)
0x180032932  mov     ebx, eax
0x180032934  jmp     short loc_1800328FB
```
