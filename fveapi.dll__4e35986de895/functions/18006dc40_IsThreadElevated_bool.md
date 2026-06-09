# IsThreadElevated(bool *)

- ea: `0x18006dc40`
- end: `0x18006dd7c`
- name: `?IsThreadElevated@@YAJPEA_N@Z`
- size: `316`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006dbec`

## callees

- `0x180005410`
- `0x18006dc40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006dc6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006dcd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006dc6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006dcd5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006dc85`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006dcf0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006dc85`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006dcf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006dd65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180122727`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006dd65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180122727`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006dd1e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006dd1e`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18006dcb0`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18006dcb0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006dd43`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180122705`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006dd43`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180122705`

## pseudocode

```c
__int64 __fastcall IsThreadElevated(bool *a1)
{
  char v2; // di
  HANDLE CurrentThread; // rax
  unsigned int LastHresultError; // ebx
  HANDLE v5; // rax
  int TokenInformation; // [rsp+68h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+70h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+20h] BYREF

  TokenInformation = 0;
  v2 = 0;
  ReturnLength = 0;
  TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    goto LABEL_6;
  LastHresultError = GetLastHresultError();
  if ( LastHresultError == -2147023888 )
  {
    if ( !ImpersonateSelf(SecurityImpersonation)
      || (v2 = 1, v5 = GetCurrentThread(), !OpenThreadToken(v5, 8u, 0, &TokenHandle)) )
    {
LABEL_4:
      LastHresultError = GetLastHresultError();
      goto LABEL_8;
    }
LABEL_6:
    if ( GetTokenInformation(TokenHandle, TokenElevation, &TokenInformation, 4u, &ReturnLength) )
    {
      *a1 = TokenInformation != 0;
      LastHresultError = 0;
      goto LABEL_8;
    }
    goto LABEL_4;
  }
LABEL_8:
  if ( v2 && !RevertToSelf() )
    LastHresultError = GetLastHresultError();
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  return LastHresultError;
}

```

## disassembly

```asm
0x18006dc40  mov     rax, rsp
0x18006dc43  push    rbx
0x18006dc44  push    rsi
0x18006dc45  push    rdi
0x18006dc46  sub     rsp, 40h
0x18006dc4a  mov     rsi, rcx
0x18006dc4d  mov     dword ptr [rax+10h], 0
0x18006dc54  xor     dil, dil
0x18006dc57  mov     [rax-28h], dil
0x18006dc5b  mov     dword ptr [rax+18h], 0
0x18006dc62  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x18006dc6a  call    cs:__imp_GetCurrentThread
0x18006dc71  nop     dword ptr [rax+rax+00h]
0x18006dc76  mov     rcx, rax; ThreadHandle
0x18006dc79  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x18006dc7e  xor     r8d, r8d; OpenAsSelf
0x18006dc81  lea     edx, [r8+8]; DesiredAccess
0x18006dc85  call    cs:__imp_OpenThreadToken
0x18006dc8c  nop     dword ptr [rax+rax+00h]
0x18006dc91  test    eax, eax
0x18006dc93  jnz     short loc_18006DD00
0x18006dc95  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18006dc9a  mov     ebx, eax
0x18006dc9c  mov     [rsp+58h+var_24], eax
0x18006dca0  cmp     eax, 800703F0h
0x18006dca5  jnz     loc_18006DD3E
0x18006dcab  mov     ecx, 2; ImpersonationLevel
0x18006dcb0  call    cs:__imp_ImpersonateSelf
0x18006dcb7  nop     dword ptr [rax+rax+00h]
0x18006dcbc  test    eax, eax
0x18006dcbe  jnz     short loc_18006DCCD
0x18006dcc0  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18006dcc5  mov     ebx, eax
0x18006dcc7  mov     [rsp+58h+var_24], eax
0x18006dccb  jmp     short loc_18006DD3E
0x18006dccd  mov     dil, 1
0x18006dcd0  mov     [rsp+58h+var_28], dil
0x18006dcd5  call    cs:__imp_GetCurrentThread
0x18006dcdc  nop     dword ptr [rax+rax+00h]
0x18006dce1  mov     rcx, rax; ThreadHandle
0x18006dce4  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x18006dce9  xor     r8d, r8d; OpenAsSelf
0x18006dcec  lea     edx, [r8+8]; DesiredAccess
0x18006dcf0  call    cs:__imp_OpenThreadToken
0x18006dcf7  nop     dword ptr [rax+rax+00h]
0x18006dcfc  test    eax, eax
0x18006dcfe  jz      short loc_18006DCC0
0x18006dd00  lea     rax, [rsp+58h+arg_10]
0x18006dd05  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18006dd0a  mov     r9d, 4; TokenInformationLength
0x18006dd10  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x18006dd15  lea     edx, [r9+10h]; TokenInformationClass
0x18006dd19  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18006dd1e  call    cs:__imp_GetTokenInformation
0x18006dd25  nop     dword ptr [rax+rax+00h]
0x18006dd2a  test    eax, eax
0x18006dd2c  jz      short loc_18006DCC0
0x18006dd2e  cmp     [rsp+58h+TokenInformation], 0
0x18006dd33  setnz   al
0x18006dd36  mov     [rsi], al
0x18006dd38  xor     ebx, ebx
0x18006dd3a  mov     [rsp+58h+var_24], ebx
0x18006dd3e  test    dil, dil
0x18006dd41  jz      short loc_18006DD5A
0x18006dd43  call    cs:__imp_RevertToSelf
0x18006dd4a  nop     dword ptr [rax+rax+00h]
0x18006dd4f  test    eax, eax
0x18006dd51  jnz     short loc_18006DD5A
0x18006dd53  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18006dd58  mov     ebx, eax
0x18006dd5a  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18006dd5f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006dd63  jz      short loc_18006DD71
0x18006dd65  call    cs:__imp_CloseHandle
0x18006dd6c  nop     dword ptr [rax+rax+00h]
0x18006dd71  mov     eax, ebx
0x18006dd73  add     rsp, 40h
0x18006dd77  pop     rdi
0x18006dd78  pop     rsi
0x18006dd79  pop     rbx
0x18006dd7a  retn
0x1801226f6  push    rbp
0x1801226f8  sub     rsp, 30h
0x1801226fc  mov     rbp, rdx
0x1801226ff  cmp     byte ptr [rbp+30h], 0
0x180122703  jz      short loc_18012271D
0x180122705  call    cs:__imp_RevertToSelf
0x18012270c  nop     dword ptr [rax+rax+00h]
0x180122711  test    eax, eax
0x180122713  jnz     short loc_18012271D
0x180122715  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18012271a  mov     [rbp+34h], eax
0x18012271d  mov     rcx, [rbp+78h]; hObject
0x180122721  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180122725  jz      short loc_180122734
0x180122727  call    cs:__imp_CloseHandle
0x18012272e  nop     dword ptr [rax+rax+00h]
0x180122733  nop
0x180122734  add     rsp, 30h
0x180122738  pop     rbp
0x180122739  retn
```
