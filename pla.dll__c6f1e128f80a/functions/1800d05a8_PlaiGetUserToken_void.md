# PlaiGetUserToken(void * *)

- ea: `0x1800d05a8`
- end: `0x1800d07e9`
- name: `?PlaiGetUserToken@@YAJPEAPEAX@Z`
- size: `577`
- prototype: `__int64 __fastcall(PHANDLE phNewToken)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008cc94`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x1800d05a8`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d05f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d06d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d05f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d06d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d07c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d07c6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d05e9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d05e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d05d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d05d6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800d06c8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800d06c8`

## string_xrefs

- `0x1800d0689`: `PlaiGetUserToken`
- `0x1800d0766`: `PlaiGetUserToken`

## pseudocode

```c
__int64 __fastcall PlaiGetUserToken(PHANDLE phNewToken)
{
  HANDLE CurrentThread; // rax
  DWORD v3; // eax
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rax
  DWORD LastError; // eax
  int v8; // eax
  __int64 v9; // rax
  int v11; // [rsp+70h] [rbp-90h] BYREF
  int v12; // [rsp+78h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v14[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v15[64]; // [rsp+110h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 6u, 0, &TokenHandle)
    || (v3 = GetLastError(), v4 = PlaiHResultFromWin32(v3), v5 = v4, v4 >= 0) )
  {
    if ( DuplicateTokenEx(TokenHandle, 4u, 0, SecurityImpersonation, TokenImpersonation, phNewToken) )
    {
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      v8 = PlaiHResultFromWin32(LastError);
      v5 = v8;
      if ( v8 < 0 )
      {
        v12 = 0;
        v11 = v8;
        if ( (_DWORD)xmmword_180169738 )
        {
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v15, 0x4000000000000800uLL);
            v9 = -1;
            do
              ++v9;
            while ( v15[v9] );
            EventingWriteEvent(
              &g_Eventing,
              PLA_EVENT_ERROR,
              5,
              &v11,
              4,
              qword_180147320,
              1,
              &v12,
              4,
              "PlaiGetUserToken",
              17);
          }
        }
      }
    }
  }
  else
  {
    v11 = 0;
    v12 = v4;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v14, 0x4000000000000800uLL);
      v6 = -1;
      do
        ++v6;
      while ( v14[v6] );
      EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v12, 4, qword_180147320, 1, &v11, 4, "PlaiGetUserToken", 17);
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x1800d05a8  push    rbp
0x1800d05aa  push    rbx
0x1800d05ab  push    rsi
0x1800d05ac  push    rdi
0x1800d05ad  lea     rbp, [rsp-0A8h]
0x1800d05b5  sub     rsp, 1A8h
0x1800d05bc  mov     rax, cs:__security_cookie
0x1800d05c3  xor     rax, rsp
0x1800d05c6  mov     [rbp+0C0h+var_30], rax
0x1800d05cd  xor     esi, esi
0x1800d05cf  mov     rdi, rcx
0x1800d05d2  mov     [rbp+0C0h+TokenHandle], rsi
0x1800d05d6  call    cs:__imp_GetCurrentThread
0x1800d05dc  lea     r9, [rbp+0C0h+TokenHandle]; TokenHandle
0x1800d05e0  xor     r8d, r8d; OpenAsSelf
0x1800d05e3  mov     rcx, rax; ThreadHandle
0x1800d05e6  lea     edx, [rsi+6]; DesiredAccess
0x1800d05e9  call    cs:__imp_OpenThreadToken
0x1800d05ef  test    eax, eax
0x1800d05f1  jnz     loc_1800D06A8
0x1800d05f7  call    cs:__imp_GetLastError
0x1800d05fd  mov     ecx, eax; unsigned int
0x1800d05ff  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800d0604  mov     ebx, eax
0x1800d0606  test    eax, eax
0x1800d0608  jns     loc_1800D06A8
0x1800d060e  cmp     dword ptr cs:xmmword_180169738, esi
0x1800d0614  mov     [rsp+1C0h+var_150], esi
0x1800d0618  mov     [rsp+1C0h+var_148], eax
0x1800d061c  jz      loc_1800D07BD
0x1800d0622  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d062c  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d0633  jz      loc_1800D07BD
0x1800d0639  mov     rax, cs:qword_180169748
0x1800d0640  and     rax, rdx
0x1800d0643  cmp     cs:qword_180169748, rax
0x1800d064a  jnz     loc_1800D07BD
0x1800d0650  lea     rcx, [rbp+0C0h+var_130]; unsigned __int16 *
0x1800d0654  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d0659  lea     rcx, [rbp+0C0h+var_130]
0x1800d065d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d0661  inc     rax
0x1800d0664  cmp     [rcx+rax*2], si
0x1800d0668  jnz     short loc_1800D0661
0x1800d066a  lea     ecx, [rax+rax]
0x1800d066d  mov     edi, 4
0x1800d0672  lea     rax, [rbp+0C0h+var_130]
0x1800d0676  add     rcx, 2
0x1800d067a  mov     [rsp+1C0h+var_160], rcx
0x1800d067f  lea     r9, [rsp+1C0h+var_148]
0x1800d0684  mov     [rsp+1C0h+var_168], rax
0x1800d0689  lea     rax, aPlaigetusertok; "PlaiGetUserToken"
0x1800d0690  mov     [rsp+1C0h+var_170], 11h
0x1800d0699  mov     [rsp+1C0h+var_178], rax
0x1800d069e  lea     rax, [rsp+1C0h+var_150]
0x1800d06a3  jmp     loc_1800D0780
0x1800d06a8  mov     rcx, [rbp+0C0h+TokenHandle]; hExistingToken
0x1800d06ac  mov     r9d, 2; ImpersonationLevel
0x1800d06b2  mov     [rsp+1C0h+phNewToken], rdi; phNewToken
0x1800d06b7  xor     r8d, r8d; lpTokenAttributes
0x1800d06ba  mov     [rsp+1C0h+TokenType], 2; TokenType
0x1800d06c2  lea     edi, [r9+2]
0x1800d06c6  mov     edx, edi; dwDesiredAccess
0x1800d06c8  call    cs:__imp_DuplicateTokenEx
0x1800d06ce  test    eax, eax
0x1800d06d0  jz      short loc_1800D06D9
0x1800d06d2  mov     ebx, esi
0x1800d06d4  jmp     loc_1800D07BD
0x1800d06d9  call    cs:__imp_GetLastError
0x1800d06df  mov     ecx, eax; unsigned int
0x1800d06e1  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800d06e6  mov     ebx, eax
0x1800d06e8  test    eax, eax
0x1800d06ea  jns     loc_1800D07BD
0x1800d06f0  cmp     dword ptr cs:xmmword_180169738, esi
0x1800d06f6  mov     [rsp+1C0h+var_148], esi
0x1800d06fa  mov     [rsp+1C0h+var_150], eax
0x1800d06fe  jz      loc_1800D07BD
0x1800d0704  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d070e  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d0715  jz      loc_1800D07BD
0x1800d071b  mov     rax, cs:qword_180169748
0x1800d0722  and     rax, rdx
0x1800d0725  cmp     cs:qword_180169748, rax
0x1800d072c  jnz     loc_1800D07BD
0x1800d0732  lea     rcx, [rbp+0C0h+var_B0]; unsigned __int16 *
0x1800d0736  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d073b  lea     rcx, [rbp+0C0h+var_B0]
0x1800d073f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d0743  inc     rax
0x1800d0746  cmp     [rcx+rax*2], si
0x1800d074a  jnz     short loc_1800D0743
0x1800d074c  lea     ecx, [rax+rax]
0x1800d074f  lea     rax, [rbp+0C0h+var_B0]
0x1800d0753  add     rcx, 2
0x1800d0757  mov     [rsp+1C0h+var_160], rcx
0x1800d075c  lea     r9, [rsp+1C0h+var_150]
0x1800d0761  mov     [rsp+1C0h+var_168], rax
0x1800d0766  lea     rax, aPlaigetusertok; "PlaiGetUserToken"
0x1800d076d  mov     [rsp+1C0h+var_170], 11h
0x1800d0776  mov     [rsp+1C0h+var_178], rax
0x1800d077b  lea     rax, [rsp+1C0h+var_148]
0x1800d0780  mov     [rsp+1C0h+var_180], rdi
0x1800d0785  lea     rdx, PLA_EVENT_ERROR
0x1800d078c  mov     [rsp+1C0h+var_188], rax
0x1800d0791  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800d0798  lea     rax, qword_180147320
0x1800d079f  mov     [rsp+1C0h+var_190], 1
0x1800d07a8  mov     [rsp+1C0h+phNewToken], rax
0x1800d07ad  mov     r8d, 5
0x1800d07b3  mov     qword ptr [rsp+1C0h+TokenType], rdi
0x1800d07b8  call    EventingWriteEvent
0x1800d07bd  mov     rcx, [rbp+0C0h+TokenHandle]; hObject
0x1800d07c1  test    rcx, rcx
0x1800d07c4  jz      short loc_1800D07CC
0x1800d07c6  call    cs:__imp_CloseHandle
0x1800d07cc  mov     eax, ebx
0x1800d07ce  mov     rcx, [rbp+0C0h+var_30]
0x1800d07d5  xor     rcx, rsp; StackCookie
0x1800d07d8  call    __security_check_cookie
0x1800d07dd  add     rsp, 1A8h
0x1800d07e4  pop     rdi
0x1800d07e5  pop     rsi
0x1800d07e6  pop     rbx
0x1800d07e7  pop     rbp
0x1800d07e8  retn
```
