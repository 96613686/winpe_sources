# CMsiServerProxy::CMsiServerProxy(IMsiServices &,IMsiServer &)

- ea: `0x180007c44`
- end: `0x180007f34`
- name: `??0CMsiServerProxy@@QEAA@AEAVIMsiServices@@AEAUIMsiServer@@@Z`
- size: `752`
- prototype: `CMsiServerProxy *__fastcall(CMsiServerProxy *__hidden this, struct IMsiServices *, struct IMsiServer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180007bdc`

## callees

- `0x180007c44`
- `0x18000c4bc`
- `0x180027634`
- `0x18009cdb8`
- `0x18009d06c`
- `0x18011a2f8`
- `0x1801c7c0c`
- `0x180266010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180007e03`
- `ADVAPI32!SetThreadToken` at `0x180007e60`
- `ADVAPI32!SetThreadToken` at `0x180007e8e`
- `ADVAPI32!SetThreadToken` at `0x180007e03`
- `ADVAPI32!SetThreadToken` at `0x180007e60`
- `ADVAPI32!SetThreadToken` at `0x180007e8e`
- `ADVAPI32!DuplicateTokenEx` at `0x180007dc5`
- `ADVAPI32!DuplicateTokenEx` at `0x180007dc5`
- `ADVAPI32!OpenThreadToken` at `0x180007d57`
- `ADVAPI32!OpenThreadToken` at `0x180007d57`
- `ADVAPI32!OpenProcessToken` at `0x180007d93`
- `ADVAPI32!OpenProcessToken` at `0x180007d93`
- `KERNEL32!CloseHandle` at `0x180007ddd`
- `KERNEL32!CloseHandle` at `0x180007ea2`
- `KERNEL32!CloseHandle` at `0x180007f0b`
- `KERNEL32!CloseHandle` at `0x180007ddd`
- `KERNEL32!CloseHandle` at `0x180007ea2`
- `KERNEL32!CloseHandle` at `0x180007f0b`
- `KERNEL32!GetLastError` at `0x180007d67`
- `KERNEL32!GetLastError` at `0x180007e70`
- `KERNEL32!GetLastError` at `0x180007d67`
- `KERNEL32!GetLastError` at `0x180007e70`
- `KERNEL32!GetCurrentThread` at `0x180007d39`
- `KERNEL32!GetCurrentThread` at `0x180007d39`
- `KERNEL32!GetCurrentProcess` at `0x180007d7e`
- `KERNEL32!GetCurrentProcess` at `0x180007d7e`

## string_xrefs

- `0x180007d08`: `Attempting to enable all disabled privileges before calling Install on Server`

## pseudocode

```c
CMsiServerProxy *__fastcall CMsiServerProxy::CMsiServerProxy(
        CMsiServerProxy *this,
        struct IMsiServices *a2,
        struct IMsiServer *a3)
{
  unsigned int *v3; // r14
  char v7; // di
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  BOOL v10; // eax
  void *v11; // rcx
  signed int v12; // eax
  char v13; // cl
  signed int LastError; // ebx
  unsigned int v16; // [rsp+50h] [rbp-10h]
  void *v17; // [rsp+58h] [rbp-8h]
  HANDLE Token; // [rsp+90h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+98h] [rbp+38h] BYREF

  v3 = (unsigned int *)((char *)this + 28);
  *((_QWORD *)this + 1) = a3;
  *((_QWORD *)this + 2) = a2;
  *(_QWORD *)this = &CMsiServerProxy::`vftable';
  *((_DWORD *)this + 6) = 1;
  *((_DWORD *)this + 7) = 0;
  (*(void (__fastcall **)(struct IMsiServer *))(*(_QWORD *)a3 + 8LL))(a3);
  (*(void (__fastcall **)(struct IMsiServices *))(*(_QWORD *)a2 + 8LL))(a2);
  if ( g_dmDiagnosticMode )
    DebugString(10, 0, 0, "Cloaking enabled.", "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", v16, v17);
  StartImpersonating();
  v7 = 0;
  Token = (HANDLE)-1LL;
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      "Attempting to enable all disabled privileges before calling Install on Server",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      v16,
      v17);
  TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 2u, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
      return this;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 2u, &TokenHandle) )
      return this;
    v7 = 1;
  }
  v10 = DuplicateTokenEx(TokenHandle, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, &Token);
  v11 = TokenHandle;
  if ( !v10 )
  {
LABEL_22:
    CloseHandle(v11);
    return this;
  }
  CloseHandle(TokenHandle);
  if ( !EnableAndMapDisabledPrivileges(Token, v3) || !SetThreadToken(0, Token) )
  {
LABEL_21:
    v11 = Token;
    goto LABEL_22;
  }
  v12 = ((__int64 (__fastcall *)(struct IMsiServer *, __int64, _QWORD, __int64, int, int, _QWORD, int))OLE32::CoSetProxyBlanket)(
          a3,
          0xFFFFFFFFLL,
          0,
          -1,
          2,
          3,
          0,
          32);
  v13 = (char)Token;
  LastError = v12;
  if ( Token != (HANDLE)-1LL )
  {
    if ( v7 )
    {
      if ( !SetThreadToken(0, 0) )
        LastError = GetLastError();
      goto LABEL_17;
    }
    DisablePrivilegesFromMap(Token, *v3);
    if ( SetThreadToken(0, Token) )
    {
LABEL_17:
      CloseHandle(Token);
      goto LABEL_18;
    }
    goto LABEL_21;
  }
LABEL_18:
  StopImpersonating(v13);
  if ( LastError && g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"SetProxyBlanket failed with: 0x%X",
      (const unsigned __int16 *)LastError,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  return this;
}

```

## disassembly

```asm
0x180007c44  mov     [rsp-28h+arg_10], rbx
0x180007c49  mov     [rsp-28h+arg_18], rsi
0x180007c4e  push    rbp
0x180007c4f  push    rdi
0x180007c50  push    r13
0x180007c52  push    r14
0x180007c54  push    r15
0x180007c56  mov     rbp, rsp
0x180007c59  sub     rsp, 60h
0x180007c5d  lea     r14, [rcx+1Ch]
0x180007c61  mov     [rcx+8], r8
0x180007c65  mov     [rcx+10h], rdx
0x180007c69  lea     rax, ??_7CMsiServerProxy@@6B@; const CMsiServerProxy::`vftable'
0x180007c70  mov     [rcx], rax
0x180007c73  mov     rsi, rcx
0x180007c76  mov     dword ptr [rcx+18h], 1
0x180007c7d  mov     r15, r8
0x180007c80  mov     dword ptr [r14], 0
0x180007c87  mov     rcx, r8
0x180007c8a  mov     rax, [r8]
0x180007c8d  mov     rbx, rdx
0x180007c90  mov     rax, [rax+8]
0x180007c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c99  mov     rax, [rbx]
0x180007c9c  mov     rcx, rbx
0x180007c9f  mov     rax, [rax+8]
0x180007ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ca8  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x180007caf  lea     rbx, aNull_0; "(NULL)"
0x180007cb6  jz      short loc_180007CEA
0x180007cb8  mov     [rsp+60h+var_18], rbx; char *
0x180007cbd  lea     r9, aCloakingEnable; "Cloaking enabled."
0x180007cc4  mov     [rsp+60h+var_20], rbx; char *
0x180007cc9  xor     edx, edx; unsigned __int16
0x180007ccb  mov     [rsp+60h+var_28], rbx; char *
0x180007cd0  xor     r8d, r8d; int
0x180007cd3  mov     [rsp+60h+var_30], rbx; char *
0x180007cd8  mov     [rsp+60h+phNewToken], rbx; char *
0x180007cdd  lea     ecx, [rdx+0Ah]; int
0x180007ce0  mov     qword ptr [rsp+60h+TokenType], rbx; char *
0x180007ce5  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180007cea  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x180007cef  or      r13, 0FFFFFFFFFFFFFFFFh
0x180007cf3  xor     dil, dil
0x180007cf6  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x180007cfd  mov     [rbp+Token], r13
0x180007d01  jz      short loc_180007D35
0x180007d03  mov     [rsp+60h+var_18], rbx; char *
0x180007d08  lea     r9, aAttemptingToEn; "Attempting to enable all disabled privi"...
0x180007d0f  mov     [rsp+60h+var_20], rbx; char *
0x180007d14  xor     edx, edx; unsigned __int16
0x180007d16  mov     [rsp+60h+var_28], rbx; char *
0x180007d1b  xor     r8d, r8d; int
0x180007d1e  mov     [rsp+60h+var_30], rbx; char *
0x180007d23  mov     [rsp+60h+phNewToken], rbx; char *
0x180007d28  lea     ecx, [rdx+9]; int
0x180007d2b  mov     qword ptr [rsp+60h+TokenType], rbx; char *
0x180007d30  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180007d35  mov     [rbp+TokenHandle], r13
0x180007d39  call    cs:__imp_GetCurrentThread
0x180007d40  nop     dword ptr [rax+rax+00h]
0x180007d45  mov     ebx, 2
0x180007d4a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180007d4e  mov     rcx, rax; ThreadHandle
0x180007d51  mov     edx, ebx; DesiredAccess
0x180007d53  lea     r8d, [rbx-1]; OpenAsSelf
0x180007d57  call    cs:__imp_OpenThreadToken
0x180007d5e  nop     dword ptr [rax+rax+00h]
0x180007d63  test    eax, eax
0x180007d65  jnz     short loc_180007DAA
0x180007d67  call    cs:__imp_GetLastError
0x180007d6e  nop     dword ptr [rax+rax+00h]
0x180007d73  cmp     eax, 3F0h
0x180007d78  jnz     loc_180007F17
0x180007d7e  call    cs:__imp_GetCurrentProcess
0x180007d85  nop     dword ptr [rax+rax+00h]
0x180007d8a  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180007d8e  mov     edx, ebx; DesiredAccess
0x180007d90  mov     rcx, rax; ProcessHandle
0x180007d93  call    cs:__imp_OpenProcessToken
0x180007d9a  nop     dword ptr [rax+rax+00h]
0x180007d9f  test    eax, eax
0x180007da1  jz      loc_180007F17
0x180007da7  mov     dil, 1
0x180007daa  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180007dae  lea     rax, [rbp+Token]
0x180007db2  xor     r8d, r8d; lpTokenAttributes
0x180007db5  mov     [rsp+60h+phNewToken], rax; phNewToken
0x180007dba  mov     r9d, ebx; ImpersonationLevel
0x180007dbd  mov     [rsp+60h+TokenType], ebx; TokenType
0x180007dc1  lea     edx, [r8+2Ch]; dwDesiredAccess
0x180007dc5  call    cs:__imp_DuplicateTokenEx
0x180007dcc  nop     dword ptr [rax+rax+00h]
0x180007dd1  mov     rcx, [rbp+TokenHandle]; hObject
0x180007dd5  test    eax, eax
0x180007dd7  jz      loc_180007F0B
0x180007ddd  call    cs:__imp_CloseHandle
0x180007de4  nop     dword ptr [rax+rax+00h]
0x180007de9  mov     rcx, [rbp+Token]; TokenHandle
0x180007ded  mov     rdx, r14; unsigned int *
0x180007df0  call    ?EnableAndMapDisabledPrivileges@@YA_NPEAXAEAK@Z; EnableAndMapDisabledPrivileges(void *,ulong &)
0x180007df5  test    al, al
0x180007df7  jz      loc_180007F07
0x180007dfd  mov     rdx, [rbp+Token]; Token
0x180007e01  xor     ecx, ecx; Thread
0x180007e03  call    cs:__imp_SetThreadToken
0x180007e0a  nop     dword ptr [rax+rax+00h]
0x180007e0f  test    eax, eax
0x180007e11  jz      loc_180007F07
0x180007e17  mov     rax, cs:?CoSetProxyBlanket@OLE32@@3P6AJPEAUIUnknown@@KKPEAGKKPEAXK@ZEA; long (*OLE32::CoSetProxyBlanket)(IUnknown *,ulong,ulong,ushort *,ulong,ulong,void *,ulong)
0x180007e1e  mov     r9, r13
0x180007e21  mov     dword ptr [rsp+60h+var_28], 20h ; ' '
0x180007e29  xor     r8d, r8d
0x180007e2c  mov     [rsp+60h+var_30], 0
0x180007e35  or      edx, 0FFFFFFFFh
0x180007e38  mov     dword ptr [rsp+60h+phNewToken], 3
0x180007e40  mov     rcx, r15
0x180007e43  mov     [rsp+60h+TokenType], ebx
0x180007e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e4c  mov     rcx, [rbp+Token]; TokenHandle
0x180007e50  mov     ebx, eax
0x180007e52  cmp     rcx, r13
0x180007e55  jz      short loc_180007EAE
0x180007e57  test    dil, dil
0x180007e5a  jz      short loc_180007E80
0x180007e5c  xor     edx, edx; Token
0x180007e5e  xor     ecx, ecx; Thread
0x180007e60  call    cs:__imp_SetThreadToken
0x180007e67  nop     dword ptr [rax+rax+00h]
0x180007e6c  test    eax, eax
0x180007e6e  jnz     short loc_180007E9E
0x180007e70  call    cs:__imp_GetLastError
0x180007e77  nop     dword ptr [rax+rax+00h]
0x180007e7c  mov     ebx, eax
0x180007e7e  jmp     short loc_180007E9E
0x180007e80  mov     edx, [r14]; unsigned int
0x180007e83  call    ?DisablePrivilegesFromMap@@YA_NPEAXK@Z; DisablePrivilegesFromMap(void *,ulong)
0x180007e88  mov     rdx, [rbp+Token]; Token
0x180007e8c  xor     ecx, ecx; Thread
0x180007e8e  call    cs:__imp_SetThreadToken
0x180007e95  nop     dword ptr [rax+rax+00h]
0x180007e9a  test    eax, eax
0x180007e9c  jz      short loc_180007F07
0x180007e9e  mov     rcx, [rbp+Token]; hObject
0x180007ea2  call    cs:__imp_CloseHandle
0x180007ea9  nop     dword ptr [rax+rax+00h]
0x180007eae  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x180007eb3  test    ebx, ebx
0x180007eb5  jz      short loc_180007F17
0x180007eb7  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x180007ebe  jz      short loc_180007F17
0x180007ec0  lea     r8, aNull; "(NULL)"
0x180007ec7  movsxd  rax, ebx
0x180007eca  xor     edx, edx; unsigned __int16
0x180007ecc  lea     r9, aSetproxyblanke; "SetProxyBlanket failed with: 0x%X"
0x180007ed3  mov     [rsp+60h+var_8], rdx; void *
0x180007ed8  mov     [rsp+60h+var_10], edx; unsigned int
0x180007edc  mov     [rsp+60h+var_18], r8; unsigned __int16 *
0x180007ee1  mov     [rsp+60h+var_20], r8; unsigned __int16 *
0x180007ee6  lea     ecx, [rdx+9]; int
0x180007ee9  mov     [rsp+60h+var_28], r8; unsigned __int16 *
0x180007eee  mov     [rsp+60h+var_30], r8; unsigned __int16 *
0x180007ef3  mov     [rsp+60h+phNewToken], r8; unsigned __int16 *
0x180007ef8  xor     r8d, r8d; int
0x180007efb  mov     qword ptr [rsp+60h+TokenType], rax; unsigned __int16 *
0x180007f00  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180007f05  jmp     short loc_180007F17
0x180007f07  mov     rcx, [rbp+Token]; hObject
0x180007f0b  call    cs:__imp_CloseHandle
0x180007f12  nop     dword ptr [rax+rax+00h]
0x180007f17  lea     r11, [rsp+60h+var_s0]
0x180007f1c  mov     rax, rsi
0x180007f1f  mov     rbx, [r11+40h]
0x180007f23  mov     rsi, [r11+48h]
0x180007f27  mov     rsp, r11
0x180007f2a  pop     r15
0x180007f2c  pop     r14
0x180007f2e  pop     r13
0x180007f30  pop     rdi
0x180007f31  pop     rbp
0x180007f32  retn
```
