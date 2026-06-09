# GetTokenInformation_HeapFree<_TOKEN_MANDATORY_LABEL>(void *,void *,_TOKEN_INFORMATION_CLASS,_TOKEN_MANDATORY_LABEL * *)

- ea: `0x180025368`
- end: `0x180025432`
- name: `??$GetTokenInformation_HeapFree@U_TOKEN_MANDATORY_LABEL@@@@YAJPEAX0W4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_MANDATORY_LABEL@@@Z`
- size: `202`
- prototype: `__int64 __fastcall(HANDLE hHeap, HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800252e0`

## callees

- `0x180025368`
- `0x180025c18`
- `0x180050060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800253ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800253ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800253c0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800253c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002541c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002541c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002539d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800253e8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002539d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800253e8`

## pseudocode

```c
__int64 __fastcall GetTokenInformation_HeapFree<_TOKEN_MANDATORY_LABEL>(
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
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) )
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
        if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v8, TokenInformationLength, &TokenInformationLength) )
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
0x180025368  mov     [rsp+TokenInformationLength], r8d
0x18002536d  push    rbx
0x18002536e  push    rbp
0x18002536f  push    rsi
0x180025370  push    rdi
0x180025371  sub     rsp, 38h
0x180025375  mov     rbp, rdx
0x180025378  mov     [rsp+58h+TokenInformationLength], 0
0x180025380  mov     rbx, r9
0x180025383  lea     rax, [rsp+58h+TokenInformationLength]
0x180025388  xor     r9d, r9d; TokenInformationLength
0x18002538b  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180025390  mov     rsi, rcx
0x180025393  xor     r8d, r8d; TokenInformation
0x180025396  mov     rcx, rbp; TokenHandle
0x180025399  lea     edx, [r9+19h]; TokenInformationClass
0x18002539d  call    cs:__imp_GetTokenInformation
0x1800253a3  test    eax, eax
0x1800253a5  jnz     loc_18002542B
0x1800253ab  call    cs:__imp_GetLastError
0x1800253b1  cmp     eax, 7Ah ; 'z'
0x1800253b4  jnz     short loc_180025402
0x1800253b6  mov     r8d, [rsp+58h+TokenInformationLength]; dwBytes
0x1800253bb  xor     edx, edx; dwFlags
0x1800253bd  mov     rcx, rsi; hHeap
0x1800253c0  call    cs:__imp_HeapAlloc
0x1800253c6  mov     rdi, rax
0x1800253c9  test    rax, rax
0x1800253cc  jz      short loc_180025424
0x1800253ce  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1800253d3  lea     rax, [rsp+58h+TokenInformationLength]
0x1800253d8  mov     r8, rdi; TokenInformation
0x1800253db  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800253e0  mov     edx, 19h; TokenInformationClass
0x1800253e5  mov     rcx, rbp; TokenHandle
0x1800253e8  call    cs:__imp_GetTokenInformation
0x1800253ee  test    eax, eax
0x1800253f0  jz      short loc_18002540D
0x1800253f2  mov     [rbx], rdi
0x1800253f5  xor     ebx, ebx
0x1800253f7  mov     eax, ebx
0x1800253f9  add     rsp, 38h
0x1800253fd  pop     rdi
0x1800253fe  pop     rsi
0x1800253ff  pop     rbp
0x180025400  pop     rbx
0x180025401  retn
0x180025402  mov     ecx, eax; unsigned int
0x180025404  call    ?HRESULTFromWin32ErrorError@@YAJK@Z; HRESULTFromWin32ErrorError(ulong)
0x180025409  mov     ebx, eax
0x18002540b  jmp     short loc_1800253F7
0x18002540d  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x180025412  mov     r8, rdi; lpMem
0x180025415  xor     edx, edx; dwFlags
0x180025417  mov     rcx, rsi; hHeap
0x18002541a  mov     ebx, eax
0x18002541c  call    cs:__imp_HeapFree
0x180025422  jmp     short loc_1800253F7
0x180025424  mov     ebx, 8007000Eh
0x180025429  jmp     short loc_1800253F7
0x18002542b  mov     ebx, 8000FFFFh
0x180025430  jmp     short loc_1800253F7
```
