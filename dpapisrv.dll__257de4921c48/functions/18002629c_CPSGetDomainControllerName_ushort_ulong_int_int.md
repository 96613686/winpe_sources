# CPSGetDomainControllerName(ushort *,ulong *,int,int)

- ea: `0x18002629c`
- end: `0x180026354`
- name: `?CPSGetDomainControllerName@@YAKPEAGPEAKHH@Z`
- size: `184`
- prototype: `DWORD __fastcall(unsigned __int16 *, unsigned int *, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002677c`

## callees

- `0x180007f10`
- `0x18002629c`
- `0x18002658c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800262e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800262e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800262d7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800262d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800262ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800262ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002633c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002633c`

## string_xrefs

- `0x18002631b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`

## pseudocode

```c
DWORD __fastcall CPSGetDomainControllerName(unsigned __int16 *a1, unsigned int *a2, int a3, int a4)
{
  HANDLE CurrentThread; // rax
  int v10; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-38h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    return GetLastError();
  if ( GetDomainControllerNameByToken(TokenHandle, a1, a2, a3, a4) )
  {
    v10 = 0;
  }
  else
  {
    v10 = 58;
    DebugTraceError(58, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 797);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v10;
}

```

## disassembly

```asm
0x18002629c  push    rbx
0x18002629e  push    rbp
0x18002629f  push    rsi
0x1800262a0  push    rdi
0x1800262a1  sub     rsp, 48h
0x1800262a5  mov     ebx, r9d
0x1800262a8  mov     [rsp+68h+TokenHandle], 0
0x1800262b1  mov     edi, r8d
0x1800262b4  mov     rsi, rdx
0x1800262b7  mov     rbp, rcx
0x1800262ba  call    cs:__imp_GetCurrentThread
0x1800262c1  nop     dword ptr [rax+rax+00h]
0x1800262c6  mov     edx, 8; DesiredAccess
0x1800262cb  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x1800262d0  mov     rcx, rax; ThreadHandle
0x1800262d3  lea     r8d, [rdx-7]; OpenAsSelf
0x1800262d7  call    cs:__imp_OpenThreadToken
0x1800262de  nop     dword ptr [rax+rax+00h]
0x1800262e3  test    eax, eax
0x1800262e5  jnz     short loc_1800262F5
0x1800262e7  call    cs:__imp_GetLastError
0x1800262ee  nop     dword ptr [rax+rax+00h]
0x1800262f3  jmp     short loc_18002634A
0x1800262f5  mov     rcx, [rsp+68h+TokenHandle]; void *
0x1800262fa  mov     r9d, edi; int
0x1800262fd  mov     r8, rsi; unsigned int *
0x180026300  mov     [rsp+68h+var_48], ebx; int
0x180026304  mov     rdx, rbp; unsigned __int16 *
0x180026307  call    ?GetDomainControllerNameByToken@@YAHPEAXPEAGPEAKHH@Z; GetDomainControllerNameByToken(void *,ushort *,ulong *,int,int)
0x18002630c  test    eax, eax
0x18002630e  jnz     short loc_180026330
0x180026310  lea     ebx, [rax+3Ah]
0x180026313  mov     r9d, 31Dh
0x180026319  mov     ecx, ebx
0x18002631b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180026322  lea     rdx, aDwlasterror; "dwLastError"
0x180026329  call    DebugTraceError
0x18002632e  jmp     short loc_180026332
0x180026330  xor     ebx, ebx
0x180026332  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x180026337  test    rcx, rcx
0x18002633a  jz      short loc_180026348
0x18002633c  call    cs:__imp_CloseHandle
0x180026343  nop     dword ptr [rax+rax+00h]
0x180026348  mov     eax, ebx
0x18002634a  add     rsp, 48h
0x18002634e  pop     rdi
0x18002634f  pop     rsi
0x180026350  pop     rbp
0x180026351  pop     rbx
0x180026352  retn
```
