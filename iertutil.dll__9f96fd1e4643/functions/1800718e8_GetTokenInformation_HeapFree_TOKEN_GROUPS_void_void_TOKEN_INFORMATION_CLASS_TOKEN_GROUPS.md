# GetTokenInformation_HeapFree<_TOKEN_GROUPS>(void *,void *,_TOKEN_INFORMATION_CLASS,_TOKEN_GROUPS * *)

- ea: `0x1800718e8`
- end: `0x1800719ae`
- name: `??$GetTokenInformation_HeapFree@U_TOKEN_GROUPS@@@@YAJPEAX0W4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_GROUPS@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(HANDLE hHeap, HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800719b4`

## callees

- `0x180025c18`
- `0x180050060`
- `0x1800718e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071927`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071927`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007193c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007193c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071984`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071984`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007191d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180071964`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007191d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180071964`

## pseudocode

```c
__int64 __fastcall GetTokenInformation_HeapFree<_TOKEN_GROUPS>(
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
  if ( GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength) )
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
        if ( GetTokenInformation(TokenHandle, TokenGroups, v8, TokenInformationLength, &TokenInformationLength) )
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
0x1800718e8  mov     [rsp+TokenInformationLength], r8d
0x1800718ed  push    rbx
0x1800718ee  push    rbp
0x1800718ef  push    rsi
0x1800718f0  push    rdi
0x1800718f1  sub     rsp, 38h
0x1800718f5  mov     rbp, rdx
0x1800718f8  mov     [rsp+58h+TokenInformationLength], 0
0x180071900  mov     rbx, r9
0x180071903  lea     rax, [rsp+58h+TokenInformationLength]
0x180071908  xor     r9d, r9d; TokenInformationLength
0x18007190b  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180071910  mov     rsi, rcx
0x180071913  xor     r8d, r8d; TokenInformation
0x180071916  mov     rcx, rbp; TokenHandle
0x180071919  lea     edx, [r9+2]; TokenInformationClass
0x18007191d  call    cs:__imp_GetTokenInformation
0x180071923  test    eax, eax
0x180071925  jnz     short loc_18007199E
0x180071927  call    cs:__imp_GetLastError
0x18007192d  cmp     eax, 7Ah ; 'z'
0x180071930  jnz     short loc_180071993
0x180071932  mov     r8d, [rsp+58h+TokenInformationLength]; dwBytes
0x180071937  xor     edx, edx; dwFlags
0x180071939  mov     rcx, rsi; hHeap
0x18007193c  call    cs:__imp_HeapAlloc
0x180071942  mov     rdi, rax
0x180071945  test    rax, rax
0x180071948  jz      short loc_18007198C
0x18007194a  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18007194f  lea     rax, [rsp+58h+TokenInformationLength]
0x180071954  mov     r8, rdi; TokenInformation
0x180071957  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18007195c  mov     edx, 2; TokenInformationClass
0x180071961  mov     rcx, rbp; TokenHandle
0x180071964  call    cs:__imp_GetTokenInformation
0x18007196a  test    eax, eax
0x18007196c  jz      short loc_180071975
0x18007196e  mov     [rbx], rdi
0x180071971  xor     ebx, ebx
0x180071973  jmp     short loc_1800719A3
0x180071975  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x18007197a  mov     r8, rdi; lpMem
0x18007197d  xor     edx, edx; dwFlags
0x18007197f  mov     rcx, rsi; hHeap
0x180071982  mov     ebx, eax
0x180071984  call    cs:__imp_HeapFree
0x18007198a  jmp     short loc_1800719A3
0x18007198c  mov     ebx, 8007000Eh
0x180071991  jmp     short loc_1800719A3
0x180071993  mov     ecx, eax; unsigned int
0x180071995  call    ?HRESULTFromWin32ErrorError@@YAJK@Z; HRESULTFromWin32ErrorError(ulong)
0x18007199a  mov     ebx, eax
0x18007199c  jmp     short loc_1800719A3
0x18007199e  mov     ebx, 8000FFFFh
0x1800719a3  mov     eax, ebx
0x1800719a5  add     rsp, 38h
0x1800719a9  pop     rdi
0x1800719aa  pop     rsi
0x1800719ab  pop     rbp
0x1800719ac  pop     rbx
0x1800719ad  retn
```
