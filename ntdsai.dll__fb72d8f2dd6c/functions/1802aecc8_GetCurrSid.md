# GetCurrSid

- ea: `0x1802aecc8`
- end: `0x1802aee87`
- name: `GetCurrSid`
- size: `447`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180239828`
- `0x1802410d4`
- `0x1802afa5c`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x180021aa3`
- `0x1800f80e0`
- `0x1800f8280`
- `0x1802aecc8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802aed30`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802aed30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802aed11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802aed11`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1802aede9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1802aede9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802aed62`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802aedcc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802aed62`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802aedcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802aed3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802aed6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802aedd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802aed3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802aed6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802aedd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802aee3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18046c514`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802aee3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18046c514`

## pseudocode

```c
void *__fastcall GetCurrSid(int a1)
{
  PSID *v2; // rsi
  void *v3; // rdi
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  void *v7; // rax
  int v8; // r8d
  int v9; // r9d
  DWORD TokenInformationLength; // [rsp+78h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp+18h] BYREF

  v2 = 0;
  TokenInformationLength = 0;
  TokenHandle = (void *)-1LL;
  v3 = 0;
  LastError = ImpersonateAnyClient();
  if ( LastError )
    return 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
      LastError = GetLastError();
    if ( !LastError )
    {
      v2 = (PSID *)THAlloc_(a1, 1, TokenInformationLength, 1, 0, 19138004);
      if ( !GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
        LastError = GetLastError();
      if ( !LastError )
      {
        TokenInformationLength = GetLengthSid(*v2);
        v7 = (void *)THAlloc_(a1, 1, TokenInformationLength, 1, 0, 19138019);
        v3 = v7;
        if ( v7 )
          memcpy_0(v7, *v2, TokenInformationLength);
      }
    }
    if ( TokenHandle != (void *)-1LL )
      CloseHandle(TokenHandle);
  }
  else
  {
    LastError = GetLastError();
  }
  UnImpersonateAnyClient();
  if ( v2 )
    THFreeAux(a1, (_DWORD)v2, v8, v9, 19138035);
  if ( LastError )
  {
    if ( v3 )
    {
      THFreeAux(a1, (_DWORD)v3, v8, v9, 19138039);
      return 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1802aecc8  mov     rax, rsp
0x1802aeccb  mov     [rax+8], rbx
0x1802aeccf  mov     [rax+20h], rsi
0x1802aecd3  push    rdi
0x1802aecd4  push    r12
0x1802aecd6  push    r14
0x1802aecd8  sub     rsp, 50h
0x1802aecdc  mov     r14, rcx
0x1802aecdf  xor     esi, esi
0x1802aece1  mov     [rax+10h], esi
0x1802aece4  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x1802aecec  xor     edi, edi
0x1802aecee  call    ImpersonateAnyClient
0x1802aecf3  mov     ebx, eax
0x1802aecf5  test    eax, eax
0x1802aecf7  jz      short loc_1802AED11
0x1802aecf9  xor     eax, eax
0x1802aecfb  lea     r11, [rsp+68h+var_18]
0x1802aed00  mov     rbx, [r11+20h]
0x1802aed04  mov     rsi, [r11+38h]
0x1802aed08  mov     rsp, r11
0x1802aed0b  pop     r14
0x1802aed0d  pop     r12
0x1802aed0f  pop     rdi
0x1802aed10  retn
0x1802aed11  call    cs:__imp_GetCurrentThread
0x1802aed17  mov     rcx, rax; ThreadHandle
0x1802aed1a  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x1802aed22  mov     r12d, 1
0x1802aed28  mov     r8d, r12d; OpenAsSelf
0x1802aed2b  mov     edx, 20008h; DesiredAccess
0x1802aed30  call    cs:__imp_OpenThreadToken
0x1802aed36  test    eax, eax
0x1802aed38  jnz     short loc_1802AED47
0x1802aed3a  call    cs:__imp_GetLastError
0x1802aed40  mov     ebx, eax
0x1802aed42  jmp     loc_1802AEE44
0x1802aed47  lea     rax, [rsp+68h+TokenInformationLength]
0x1802aed4c  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1802aed51  xor     r9d, r9d; TokenInformationLength
0x1802aed54  xor     r8d, r8d; TokenInformation
0x1802aed57  mov     edx, r12d; TokenInformationClass
0x1802aed5a  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x1802aed62  call    cs:__imp_GetTokenInformation
0x1802aed68  test    eax, eax
0x1802aed6a  jz      short loc_1802AED78
0x1802aed6c  call    cs:__imp_GetLastError
0x1802aed72  mov     ebx, eax
0x1802aed74  mov     [rsp+68h+var_38], eax
0x1802aed78  test    ebx, ebx
0x1802aed7a  jnz     loc_1802AEE2F
0x1802aed80  mov     r8d, [rsp+68h+TokenInformationLength]
0x1802aed85  mov     [rsp+68h+var_40], 12405D4h
0x1802aed8d  mov     dword ptr [rsp+68h+ReturnLength], ebx
0x1802aed91  mov     r9d, r12d
0x1802aed94  mov     rdx, r12
0x1802aed97  mov     rcx, r14
0x1802aed9a  call    THAlloc_
0x1802aed9f  mov     rsi, rax
0x1802aeda2  mov     [rsp+68h+var_30], rax
0x1802aeda7  test    ebx, ebx
0x1802aeda9  jnz     loc_1802AEE2F
0x1802aedaf  lea     rax, [rsp+68h+TokenInformationLength]
0x1802aedb4  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1802aedb9  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x1802aedbe  mov     r8, rsi; TokenInformation
0x1802aedc1  mov     edx, r12d; TokenInformationClass
0x1802aedc4  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x1802aedcc  call    cs:__imp_GetTokenInformation
0x1802aedd2  test    eax, eax
0x1802aedd4  jnz     short loc_1802AEDE2
0x1802aedd6  call    cs:__imp_GetLastError
0x1802aeddc  mov     ebx, eax
0x1802aedde  mov     [rsp+68h+var_38], eax
0x1802aede2  test    ebx, ebx
0x1802aede4  jnz     short loc_1802AEE2F
0x1802aede6  mov     rcx, [rsi]; pSid
0x1802aede9  call    cs:__imp_GetLengthSid
0x1802aedef  mov     r8d, eax
0x1802aedf2  mov     [rsp+68h+TokenInformationLength], r8d
0x1802aedf7  mov     [rsp+68h+var_40], 12405E3h
0x1802aedff  mov     dword ptr [rsp+68h+ReturnLength], ebx
0x1802aee03  mov     r9d, r12d
0x1802aee06  mov     rdx, r12
0x1802aee09  mov     rcx, r14
0x1802aee0c  call    THAlloc_
0x1802aee11  mov     rdi, rax
0x1802aee14  mov     [rsp+68h+var_28], rax
0x1802aee19  test    rax, rax
0x1802aee1c  jz      short loc_1802AEE2F
0x1802aee1e  mov     r8d, [rsp+68h+TokenInformationLength]; Size
0x1802aee23  mov     rdx, [rsi]; Src
0x1802aee26  mov     rcx, rax; void *
0x1802aee29  call    memcpy_0
0x1802aee2e  nop
0x1802aee2f  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x1802aee37  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1802aee3b  jz      short loc_1802AEE44
0x1802aee3d  call    cs:__imp_CloseHandle
0x1802aee43  nop
0x1802aee44  call    UnImpersonateAnyClient
0x1802aee49  test    rsi, rsi
0x1802aee4c  jz      short loc_1802AEE61
0x1802aee4e  mov     dword ptr [rsp+68h+ReturnLength], 12405F3h
0x1802aee56  mov     rdx, rsi
0x1802aee59  mov     rcx, r14
0x1802aee5c  call    THFreeAux
0x1802aee61  test    ebx, ebx
0x1802aee63  jz      short loc_1802AEE7F
0x1802aee65  test    rdi, rdi
0x1802aee68  jz      short loc_1802AEE7F
0x1802aee6a  mov     dword ptr [rsp+68h+ReturnLength], 12405F7h
0x1802aee72  mov     rdx, rdi
0x1802aee75  mov     rcx, r14
0x1802aee78  call    THFreeAux
0x1802aee7d  xor     edi, edi
0x1802aee7f  mov     rax, rdi
0x1802aee82  jmp     loc_1802AECFB
0x18046c4fe  push    rbp
0x18046c500  sub     rsp, 30h
0x18046c504  mov     rbp, rdx
0x18046c507  mov     rcx, [rbp+80h]; hObject
0x18046c50e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18046c512  jz      short loc_18046C51B
0x18046c514  call    cs:__imp_CloseHandle
0x18046c51a  nop
0x18046c51b  add     rsp, 30h
0x18046c51f  pop     rbp
0x18046c520  retn
0x18046c522  push    rbp
0x18046c524  sub     rsp, 30h
0x18046c528  mov     rbp, rdx
0x18046c52b  call    UnImpersonateAnyClient
0x18046c530  nop
0x18046c531  add     rsp, 30h
0x18046c535  pop     rbp
0x18046c536  retn
```
