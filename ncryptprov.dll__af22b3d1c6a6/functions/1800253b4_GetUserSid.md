# GetUserSid

- ea: `0x1800253b4`
- end: `0x18002552c`
- name: `GetUserSid`
- size: `376`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002529c`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000def0`
- `0x1800110b8`
- `0x1800253b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002546a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800254e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002546a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800254e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025512`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025512`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025456`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800254d7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025456`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800254d7`

## string_xrefs

- `0x180025412`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x18002548c`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`

## pseudocode

```c
__int64 __fastcall GetUserSid(LPVOID *a1, __int64 a2, DWORD *a3, _DWORD *a4)
{
  int v7; // edx
  unsigned int v8; // ebx
  DWORD LastError; // eax
  __int64 v10; // r9
  __int64 v11; // rcx
  DWORD v12; // ebx
  void *v13; // rax
  HANDLE v14; // rcx
  HANDLE TokenHandle; // [rsp+88h] [rbp+20h] BYREF

  TokenHandle = 0;
  *a4 = 0;
  v8 = OpenCallerToken(8u, &TokenHandle);
  if ( !v8 )
  {
    if ( !GetTokenInformation(TokenHandle, TokenUser, *a1, 0x100u, a3) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError != 122 )
      {
        v10 = 174;
LABEL_8:
        v11 = LastError;
LABEL_9:
        DebugTraceError(v11, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", v10);
        goto LABEL_15;
      }
      v12 = *a3;
      v13 = (void *)SafeAllocaAllocateFromHeap(*a3);
      *a1 = v13;
      if ( !v13 )
      {
        v8 = 8;
        v10 = 187;
        v11 = 8;
        goto LABEL_9;
      }
      v14 = TokenHandle;
      *a4 = 1;
      if ( !GetTokenInformation(v14, TokenUser, v13, v12, a3) )
      {
        LastError = GetLastError();
        v8 = LastError;
        v10 = 202;
        goto LABEL_8;
      }
    }
    v8 = 0;
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
      (unsigned int)"dwReturn",
      v8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
      158);
LABEL_15:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v8;
}

```

## disassembly

```asm
0x1800253b4  mov     rax, rsp
0x1800253b7  push    rbx
0x1800253b8  push    rsi
0x1800253b9  push    r14
0x1800253bb  push    r15
0x1800253bd  sub     rsp, 48h
0x1800253c1  mov     r14, rcx
0x1800253c4  mov     qword ptr [rax+20h], 0
0x1800253cc  mov     ecx, 8; DesiredAccess
0x1800253d1  mov     dword ptr [r9], 0
0x1800253d8  lea     rdx, [rax+20h]
0x1800253dc  mov     r15, r9
0x1800253df  mov     rsi, r8
0x1800253e2  call    OpenCallerToken
0x1800253e7  mov     ebx, eax
0x1800253e9  test    eax, eax
0x1800253eb  jz      short loc_18002543B
0x1800253ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800253f4  lea     rax, WPP_GLOBAL_Control
0x1800253fb  cmp     rcx, rax
0x1800253fe  jz      loc_1800254FF
0x180025404  test    byte ptr [rcx+1Ch], 1
0x180025408  jz      loc_1800254FF
0x18002540e  mov     rcx, [rcx+10h]
0x180025412  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180025419  mov     [rsp+68h+var_38], 9Eh
0x180025421  lea     r9, aDwreturn; "dwReturn"
0x180025428  mov     [rsp+68h+var_40], r8
0x18002542d  mov     dword ptr [rsp+68h+ReturnLength], ebx
0x180025431  call    WPP_SF_sDsd
0x180025436  jmp     loc_1800254FF
0x18002543b  mov     r8, [r14]; TokenInformation
0x18002543e  mov     r9d, 100h; TokenInformationLength
0x180025444  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x18002544c  mov     edx, 1; TokenInformationClass
0x180025451  mov     [rsp+68h+ReturnLength], rsi; ReturnLength
0x180025456  call    cs:__imp_GetTokenInformation
0x18002545d  nop     dword ptr [rax+rax+00h]
0x180025462  test    eax, eax
0x180025464  jnz     loc_1800254FD
0x18002546a  call    cs:__imp_GetLastError
0x180025471  nop     dword ptr [rax+rax+00h]
0x180025476  mov     ebx, eax
0x180025478  cmp     eax, 7Ah ; 'z'
0x18002547b  jz      short loc_18002549A
0x18002547d  mov     r9d, 0AEh
0x180025483  mov     ecx, eax
0x180025485  lea     rdx, aDwreturn; "dwReturn"
0x18002548c  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180025493  call    DebugTraceError
0x180025498  jmp     short loc_1800254FF
0x18002549a  mov     ebx, [rsi]
0x18002549c  mov     ecx, ebx
0x18002549e  call    SafeAllocaAllocateFromHeap
0x1800254a3  mov     [r14], rax
0x1800254a6  test    rax, rax
0x1800254a9  jnz     short loc_1800254B8
0x1800254ab  lea     ebx, [rax+8]
0x1800254ae  mov     r9d, 0BBh
0x1800254b4  mov     ecx, ebx
0x1800254b6  jmp     short loc_180025485
0x1800254b8  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x1800254c0  mov     r9d, ebx; TokenInformationLength
0x1800254c3  mov     r8, rax; TokenInformation
0x1800254c6  mov     dword ptr [r15], 1
0x1800254cd  mov     edx, 1; TokenInformationClass
0x1800254d2  mov     [rsp+68h+ReturnLength], rsi; ReturnLength
0x1800254d7  call    cs:__imp_GetTokenInformation
0x1800254de  nop     dword ptr [rax+rax+00h]
0x1800254e3  test    eax, eax
0x1800254e5  jnz     short loc_1800254FD
0x1800254e7  call    cs:__imp_GetLastError
0x1800254ee  nop     dword ptr [rax+rax+00h]
0x1800254f3  mov     ebx, eax
0x1800254f5  mov     r9d, 0CAh
0x1800254fb  jmp     short loc_180025483
0x1800254fd  xor     ebx, ebx
0x1800254ff  cmp     [rsp+68h+TokenHandle], 0
0x180025508  jz      short loc_18002551E
0x18002550a  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x180025512  call    cs:__imp_CloseHandle
0x180025519  nop     dword ptr [rax+rax+00h]
0x18002551e  mov     eax, ebx
0x180025520  add     rsp, 48h
0x180025524  pop     r15
0x180025526  pop     r14
0x180025528  pop     rsi
0x180025529  pop     rbx
0x18002552a  retn
```
