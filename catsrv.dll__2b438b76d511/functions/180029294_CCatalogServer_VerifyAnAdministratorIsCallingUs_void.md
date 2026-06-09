# CCatalogServer::VerifyAnAdministratorIsCallingUs(void)

- ea: `0x180029294`
- end: `0x1800293bd`
- name: `?VerifyAnAdministratorIsCallingUs@CCatalogServer@@AEAAJXZ`
- size: `297`
- prototype: `__int64 __fastcall(CCatalogServer *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800274b0`
- `0x180028d90`
- `0x180028ec0`

## callees

- `0x180029294`
- `0x180032c6c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800292f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800292f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002937c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002937c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180029326`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180029326`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180029312`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180029312`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180029345`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180029345`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180029372`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180029372`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800292c8`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800292c8`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180029306`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180029306`

## pseudocode

```c
__int64 __fastcall CCatalogServer::VerifyAnAdministratorIsCallingUs(CCatalogServer *this)
{
  int v1; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v4; // eax
  bool v5; // sf
  WINBOOL IsMember; // [rsp+30h] [rbp+10h] BYREF
  int v8; // [rsp+34h] [rbp+14h]
  HANDLE hObject; // [rsp+38h] [rbp+18h] BYREF
  void *ppInterface; // [rsp+40h] [rbp+20h] BYREF

  v8 = HIDWORD(this);
  hObject = (HANDLE)-1LL;
  IsMember = 0;
  ppInterface = 0;
  if ( CoGetCallContext(&IID_IServerSecurity, &ppInterface) < 0 )
  {
    v4 = 0;
    goto LABEL_21;
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
  ppInterface = 0;
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  hObject = (HANDLE)-1LL;
  v1 = CoImpersonateClient();
  if ( !v1 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &hObject) )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
    }
    RevertToSelf();
  }
  if ( v1 >= 0 )
  {
    IsMember = 0;
    if ( hObject == (HANDLE)-1LL )
    {
      v4 = -2147418113;
    }
    else
    {
      if ( CheckTokenMembership(hObject, &CSid::x_sidLocalAdministrators, &IsMember) )
      {
        v4 = 0;
      }
      else
      {
        v4 = GetLastError();
        v5 = v4 < 0;
        if ( v4 > 0 )
        {
          v4 = (unsigned __int16)v4 | 0x80070000;
          v5 = v4 < 0;
        }
        if ( v5 )
          goto LABEL_21;
      }
      if ( !IsMember )
        v4 = -2147024891;
    }
LABEL_21:
    v1 = v4;
  }
  CToken::~CToken(&hObject);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180029294  mov     [rsp-8+arg_18], rbx
0x180029299  mov     qword ptr [rsp-8+IsMember], rcx
0x18002929e  push    rbp
0x18002929f  mov     rbp, rsp
0x1800292a2  sub     rsp, 20h
0x1800292a6  lea     rdx, [rbp+ppInterface]; ppInterface
0x1800292aa  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x1800292b2  lea     rcx, IID_IServerSecurity; riid
0x1800292b9  mov     [rbp+IsMember], 0
0x1800292c0  mov     [rbp+ppInterface], 0
0x1800292c8  call    cs:__imp_CoGetCallContext
0x1800292ce  test    eax, eax
0x1800292d0  js      loc_1800293A3
0x1800292d6  mov     rcx, [rbp+ppInterface]
0x1800292da  mov     rax, [rcx]
0x1800292dd  mov     rax, [rax+10h]
0x1800292e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292e6  mov     rcx, [rbp+hObject]; hObject
0x1800292ea  mov     [rbp+ppInterface], 0
0x1800292f2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800292f6  jz      short loc_1800292FE
0x1800292f8  call    cs:__imp_CloseHandle
0x1800292fe  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x180029306  call    cs:__imp_CoImpersonateClient
0x18002930c  mov     ebx, eax
0x18002930e  test    eax, eax
0x180029310  jnz     short loc_18002934B
0x180029312  call    cs:__imp_GetCurrentThread
0x180029318  mov     rcx, rax; ThreadHandle
0x18002931b  lea     r9, [rbp+hObject]; TokenHandle
0x18002931f  lea     edx, [rbx+8]; DesiredAccess
0x180029322  lea     r8d, [rbx+1]; OpenAsSelf
0x180029326  call    cs:__imp_OpenThreadToken
0x18002932c  test    eax, eax
0x18002932e  jnz     short loc_180029345
0x180029330  call    cs:__imp_GetLastError
0x180029336  mov     ebx, eax
0x180029338  test    eax, eax
0x18002933a  jle     short loc_180029345
0x18002933c  movzx   ebx, ax
0x18002933f  or      ebx, 80070000h
0x180029345  call    cs:__imp_RevertToSelf
0x18002934b  test    ebx, ebx
0x18002934d  js      short loc_1800293A7
0x18002934f  mov     rcx, [rbp+hObject]; TokenHandle
0x180029353  mov     [rbp+IsMember], 0
0x18002935a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002935e  jnz     short loc_180029367
0x180029360  mov     eax, 8000FFFFh
0x180029365  jmp     short loc_1800293A5
0x180029367  lea     r8, [rbp+IsMember]; IsMember
0x18002936b  lea     rdx, ?x_sidLocalAdministrators@CSid@@0U_SID2@1@B; SidToCheck
0x180029372  call    cs:__imp_CheckTokenMembership
0x180029378  test    eax, eax
0x18002937a  jnz     short loc_180029394
0x18002937c  call    cs:__imp_GetLastError
0x180029382  test    eax, eax
0x180029384  jle     short loc_180029390
0x180029386  movzx   eax, ax
0x180029389  or      eax, 80070000h
0x18002938e  test    eax, eax
0x180029390  jns     short loc_180029396
0x180029392  jmp     short loc_1800293A5
0x180029394  xor     eax, eax
0x180029396  cmp     [rbp+IsMember], 0
0x18002939a  jnz     short loc_1800293A5
0x18002939c  mov     eax, 80070005h
0x1800293a1  jmp     short loc_1800293A5
0x1800293a3  xor     eax, eax
0x1800293a5  mov     ebx, eax
0x1800293a7  lea     rcx, [rbp+hObject]; this
0x1800293ab  call    ??1CToken@@QEAA@XZ; CToken::~CToken(void)
0x1800293b0  mov     eax, ebx
0x1800293b2  mov     rbx, [rsp+20h+arg_18]
0x1800293b7  add     rsp, 20h
0x1800293bb  pop     rbp
0x1800293bc  retn
```
