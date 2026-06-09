# CheckForLowIntegrityAndGenerateMediumIntegrityToken(void *,void * *,int *)

- ea: `0x1800232c4`
- end: `0x180023456`
- name: `?CheckForLowIntegrityAndGenerateMediumIntegrityToken@@YAKPEAXPEAPEAXPEAH@Z`
- size: `402`
- prototype: `__int64 __fastcall(HANDLE hExistingToken, void **, int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800231b8`
- `0x180023c10`
- `0x180023e20`

## callees

- `0x1800232c4`
- `0x180023580`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002338b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002338b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002342d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002342d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023379`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002341f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023379`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002341f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002335d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002335d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023414`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023444`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023414`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023444`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002332a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002332a`
- `ADVAPI32!SetTokenInformation` at `0x1800233e5`
- `ADVAPI32!SetTokenInformation` at `0x1800233e5`
- `ADVAPI32!CreateWellKnownSid` at `0x180023353`
- `ADVAPI32!CreateWellKnownSid` at `0x1800233b2`
- `ADVAPI32!CreateWellKnownSid` at `0x180023353`
- `ADVAPI32!CreateWellKnownSid` at `0x1800233b2`

## pseudocode

```c
__int64 __fastcall CheckForLowIntegrityAndGenerateMediumIntegrityToken(HANDLE hExistingToken, void **a2, int *a3)
{
  DWORD LastError; // ebx
  _DWORD *v7; // rdi
  DWORD v8; // eax
  __int64 v9; // rbx
  HANDLE ProcessHeap; // rax
  char *v11; // rax
  char *v12; // rsi
  HANDLE v13; // rsi
  HANDLE v14; // rax
  HANDLE TokenHandle; // [rsp+30h] [rbp-38h] BYREF
  DWORD cbSid; // [rsp+88h] [rbp+20h] BYREF

  LastError = IsLowIntegrityToken(hExistingToken, a3);
  if ( LastError || !*a3 )
    return LastError;
  v7 = 0;
  TokenHandle = 0;
  cbSid = 0;
  if ( !hExistingToken )
  {
    LastError = 87;
LABEL_16:
    v13 = 0;
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    goto LABEL_18;
  }
  if ( !DuplicateTokenEx(hExistingToken, 0x8Eu, 0, SecurityImpersonation, TokenImpersonation, &TokenHandle) )
  {
LABEL_5:
    LastError = GetLastError();
    goto LABEL_16;
  }
  LastError = 0;
  if ( !CreateWellKnownSid(WinMediumLabelSid, 0, 0, &cbSid) )
  {
    v8 = GetLastError();
    LastError = v8;
    if ( v8 )
    {
      if ( v8 != 122 )
        goto LABEL_16;
      v9 = cbSid;
      ProcessHeap = GetProcessHeap();
      v11 = (char *)HeapAlloc(ProcessHeap, 8u, v9 + 16);
      v7 = v11;
      if ( !v11 )
      {
        LastError = 14;
        goto LABEL_16;
      }
      v12 = v11 + 16;
      if ( !CreateWellKnownSid(WinMediumLabelSid, 0, v11 + 16, &cbSid) )
        goto LABEL_5;
      LastError = 0;
      v7[2] = 96;
      *(_QWORD *)v7 = v12;
    }
  }
  if ( !SetTokenInformation(TokenHandle, TokenIntegrityLevel, v7, cbSid + 16) )
    goto LABEL_5;
  v13 = TokenHandle;
  TokenHandle = 0;
LABEL_18:
  if ( v7 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v7);
  }
  if ( LastError )
  {
    if ( v13 )
      CloseHandle(v13);
  }
  else
  {
    *a2 = v13;
  }
  return LastError;
}

```

## disassembly

```asm
0x1800232c4  push    rbx
0x1800232c6  push    rsi
0x1800232c7  push    rdi
0x1800232c8  push    r14
0x1800232ca  sub     rsp, 48h
0x1800232ce  mov     r14, rdx
0x1800232d1  mov     rdi, r8
0x1800232d4  mov     rdx, r8; int *
0x1800232d7  mov     rsi, rcx
0x1800232da  call    ?IsLowIntegrityToken@@YAKPEAXPEAH@Z; IsLowIntegrityToken(void *,int *)
0x1800232df  mov     ebx, eax
0x1800232e1  test    eax, eax
0x1800232e3  jnz     loc_18002344A
0x1800232e9  cmp     [rdi], eax
0x1800232eb  jz      loc_18002344A
0x1800232f1  xor     edi, edi
0x1800232f3  mov     [rsp+68h+TokenHandle], 0
0x1800232fc  mov     [rsp+68h+cbSid], eax
0x180023303  test    rsi, rsi
0x180023306  jz      loc_180023403
0x18002330c  lea     rax, [rsp+68h+TokenHandle]
0x180023311  xor     r8d, r8d; lpTokenAttributes
0x180023314  lea     r9d, [rbx+2]; ImpersonationLevel
0x180023318  mov     [rsp+68h+phNewToken], rax; phNewToken
0x18002331d  mov     edx, 8Eh; dwDesiredAccess
0x180023322  mov     [rsp+68h+TokenType], r9d; TokenType
0x180023327  mov     rcx, rsi; hExistingToken
0x18002332a  call    cs:__imp_DuplicateTokenEx
0x180023330  test    eax, eax
0x180023332  jnz     short loc_180023341
0x180023334  call    cs:__imp_GetLastError
0x18002333a  mov     ebx, eax
0x18002333c  jmp     loc_180023408
0x180023341  xor     ebx, ebx
0x180023343  lea     r9, [rsp+68h+cbSid]; cbSid
0x18002334b  xor     r8d, r8d; pSid
0x18002334e  xor     edx, edx; DomainSid
0x180023350  lea     ecx, [rbx+43h]; WellKnownSidType
0x180023353  call    cs:__imp_CreateWellKnownSid
0x180023359  test    eax, eax
0x18002335b  jnz     short loc_1800233CC
0x18002335d  call    cs:__imp_GetLastError
0x180023363  mov     ebx, eax
0x180023365  test    eax, eax
0x180023367  jz      short loc_1800233CC
0x180023369  cmp     eax, 7Ah ; 'z'
0x18002336c  jnz     loc_180023408
0x180023372  mov     ebx, [rsp+68h+cbSid]
0x180023379  call    cs:__imp_GetProcessHeap
0x18002337f  lea     r8, [rbx+10h]; dwBytes
0x180023383  mov     edx, 8; dwFlags
0x180023388  mov     rcx, rax; hHeap
0x18002338b  call    cs:__imp_HeapAlloc
0x180023391  mov     rdi, rax
0x180023394  test    rax, rax
0x180023397  jnz     short loc_18002339E
0x180023399  lea     ebx, [rax+0Eh]
0x18002339c  jmp     short loc_180023408
0x18002339e  xor     edx, edx; DomainSid
0x1800233a0  lea     rsi, [rax+10h]
0x1800233a4  lea     r9, [rsp+68h+cbSid]; cbSid
0x1800233ac  mov     r8, rsi; pSid
0x1800233af  lea     ecx, [rdx+43h]; WellKnownSidType
0x1800233b2  call    cs:__imp_CreateWellKnownSid
0x1800233b8  test    eax, eax
0x1800233ba  jz      loc_180023334
0x1800233c0  xor     ebx, ebx
0x1800233c2  mov     dword ptr [rdi+8], 60h ; '`'
0x1800233c9  mov     [rdi], rsi
0x1800233cc  mov     r9d, [rsp+68h+cbSid]
0x1800233d4  mov     r8, rdi; TokenInformation
0x1800233d7  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x1800233dc  add     r9d, 10h; TokenInformationLength
0x1800233e0  mov     edx, 19h; TokenInformationClass
0x1800233e5  call    cs:__imp_SetTokenInformation
0x1800233eb  test    eax, eax
0x1800233ed  jz      loc_180023334
0x1800233f3  mov     rsi, [rsp+68h+TokenHandle]
0x1800233f8  mov     [rsp+68h+TokenHandle], 0
0x180023401  jmp     short loc_18002341A
0x180023403  mov     ebx, 57h ; 'W'
0x180023408  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x18002340d  xor     esi, esi
0x18002340f  test    rcx, rcx
0x180023412  jz      short loc_18002341A
0x180023414  call    cs:__imp_CloseHandle
0x18002341a  test    rdi, rdi
0x18002341d  jz      short loc_180023433
0x18002341f  call    cs:__imp_GetProcessHeap
0x180023425  mov     r8, rdi; lpMem
0x180023428  xor     edx, edx; dwFlags
0x18002342a  mov     rcx, rax; hHeap
0x18002342d  call    cs:__imp_HeapFree
0x180023433  test    ebx, ebx
0x180023435  jnz     short loc_18002343C
0x180023437  mov     [r14], rsi
0x18002343a  jmp     short loc_18002344A
0x18002343c  test    rsi, rsi
0x18002343f  jz      short loc_18002344A
0x180023441  mov     rcx, rsi; hObject
0x180023444  call    cs:__imp_CloseHandle
0x18002344a  mov     eax, ebx
0x18002344c  add     rsp, 48h
0x180023450  pop     r14
0x180023452  pop     rdi
0x180023453  pop     rsi
0x180023454  pop     rbx
0x180023455  retn
```
