# CMsiServerProxy::CMsiServerProxy(IMsiServices &,IMsiServer &)

- ea: `0x180099de4`
- end: `0x18009a085`
- name: `??0CMsiServerProxy@@QEAA@AEAVIMsiServices@@AEAUIMsiServer@@@Z`
- size: `673`
- prototype: `CMsiServerProxy *__fastcall(CMsiServerProxy *__hidden this, struct IMsiServices *, struct IMsiServer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180099d84`

## callees

- `0x18000a150`
- `0x180025a18`
- `0x180083178`
- `0x1800833ec`
- `0x180099de4`
- `0x180110d98`
- `0x1801bf804`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180099f79`
- `ADVAPI32!SetThreadToken` at `0x180099fd0`
- `ADVAPI32!SetThreadToken` at `0x180099ff2`
- `ADVAPI32!SetThreadToken` at `0x180099f79`
- `ADVAPI32!SetThreadToken` at `0x180099fd0`
- `ADVAPI32!SetThreadToken` at `0x180099ff2`
- `ADVAPI32!DuplicateTokenEx` at `0x180099f47`
- `ADVAPI32!DuplicateTokenEx` at `0x180099f47`
- `ADVAPI32!OpenThreadToken` at `0x180099ef1`
- `ADVAPI32!OpenThreadToken` at `0x180099ef1`
- `ADVAPI32!OpenProcessToken` at `0x180099f1b`
- `ADVAPI32!OpenProcessToken` at `0x180099f1b`
- `KERNEL32!CloseHandle` at `0x180099f59`
- `KERNEL32!CloseHandle` at `0x18009a000`
- `KERNEL32!CloseHandle` at `0x18009a063`
- `KERNEL32!CloseHandle` at `0x180099f59`
- `KERNEL32!CloseHandle` at `0x18009a000`
- `KERNEL32!CloseHandle` at `0x18009a063`
- `KERNEL32!GetLastError` at `0x180099efb`
- `KERNEL32!GetLastError` at `0x180099fda`
- `KERNEL32!GetLastError` at `0x180099efb`
- `KERNEL32!GetLastError` at `0x180099fda`
- `KERNEL32!GetCurrentThread` at `0x180099ed9`
- `KERNEL32!GetCurrentThread` at `0x180099ed9`
- `KERNEL32!GetCurrentProcess` at `0x180099f0c`
- `KERNEL32!GetCurrentProcess` at `0x180099f0c`

## string_xrefs

- `0x180099ea8`: `Attempting to enable all disabled privileges before calling Install on Server`

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
0x180099de4  mov     [rsp-28h+arg_10], rbx
0x180099de9  mov     [rsp-28h+arg_18], rsi
0x180099dee  push    rbp
0x180099def  push    rdi
0x180099df0  push    r13
0x180099df2  push    r14
0x180099df4  push    r15
0x180099df6  mov     rbp, rsp
0x180099df9  sub     rsp, 60h
0x180099dfd  lea     r14, [rcx+1Ch]
0x180099e01  mov     [rcx+8], r8
0x180099e05  mov     [rcx+10h], rdx
0x180099e09  lea     rax, ??_7CMsiServerProxy@@6B@; const CMsiServerProxy::`vftable'
0x180099e10  mov     [rcx], rax
0x180099e13  mov     rsi, rcx
0x180099e16  mov     dword ptr [rcx+18h], 1
0x180099e1d  mov     r15, r8
0x180099e20  mov     dword ptr [r14], 0
0x180099e27  mov     rcx, r8
0x180099e2a  mov     rax, [r8]
0x180099e2d  mov     rbx, rdx
0x180099e30  mov     rax, [rax+8]
0x180099e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099e39  mov     rax, [rbx]
0x180099e3c  mov     rcx, rbx
0x180099e3f  mov     rax, [rax+8]
0x180099e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099e48  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x180099e4f  lea     rbx, aNull_0; "(NULL)"
0x180099e56  jz      short loc_180099E8A
0x180099e58  mov     [rsp+60h+var_18], rbx; char *
0x180099e5d  lea     r9, aCloakingEnable; "Cloaking enabled."
0x180099e64  mov     [rsp+60h+var_20], rbx; char *
0x180099e69  xor     edx, edx; unsigned __int16
0x180099e6b  mov     [rsp+60h+var_28], rbx; char *
0x180099e70  xor     r8d, r8d; int
0x180099e73  mov     [rsp+60h+var_30], rbx; char *
0x180099e78  mov     [rsp+60h+phNewToken], rbx; char *
0x180099e7d  lea     ecx, [rdx+0Ah]; int
0x180099e80  mov     qword ptr [rsp+60h+TokenType], rbx; char *
0x180099e85  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180099e8a  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x180099e8f  or      r13, 0FFFFFFFFFFFFFFFFh
0x180099e93  xor     dil, dil
0x180099e96  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x180099e9d  mov     [rbp+Token], r13
0x180099ea1  jz      short loc_180099ED5
0x180099ea3  mov     [rsp+60h+var_18], rbx; char *
0x180099ea8  lea     r9, aAttemptingToEn; "Attempting to enable all disabled privi"...
0x180099eaf  mov     [rsp+60h+var_20], rbx; char *
0x180099eb4  xor     edx, edx; unsigned __int16
0x180099eb6  mov     [rsp+60h+var_28], rbx; char *
0x180099ebb  xor     r8d, r8d; int
0x180099ebe  mov     [rsp+60h+var_30], rbx; char *
0x180099ec3  mov     [rsp+60h+phNewToken], rbx; char *
0x180099ec8  lea     ecx, [rdx+9]; int
0x180099ecb  mov     qword ptr [rsp+60h+TokenType], rbx; char *
0x180099ed0  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180099ed5  mov     [rbp+TokenHandle], r13
0x180099ed9  call    cs:__imp_GetCurrentThread
0x180099edf  mov     ebx, 2
0x180099ee4  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180099ee8  mov     rcx, rax; ThreadHandle
0x180099eeb  mov     edx, ebx; DesiredAccess
0x180099eed  lea     r8d, [rbx-1]; OpenAsSelf
0x180099ef1  call    cs:__imp_OpenThreadToken
0x180099ef7  test    eax, eax
0x180099ef9  jnz     short loc_180099F2C
0x180099efb  call    cs:__imp_GetLastError
0x180099f01  cmp     eax, 3F0h
0x180099f06  jnz     loc_18009A069
0x180099f0c  call    cs:__imp_GetCurrentProcess
0x180099f12  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180099f16  mov     edx, ebx; DesiredAccess
0x180099f18  mov     rcx, rax; ProcessHandle
0x180099f1b  call    cs:__imp_OpenProcessToken
0x180099f21  test    eax, eax
0x180099f23  jz      loc_18009A069
0x180099f29  mov     dil, 1
0x180099f2c  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180099f30  lea     rax, [rbp+Token]
0x180099f34  xor     r8d, r8d; lpTokenAttributes
0x180099f37  mov     [rsp+60h+phNewToken], rax; phNewToken
0x180099f3c  mov     r9d, ebx; ImpersonationLevel
0x180099f3f  mov     [rsp+60h+TokenType], ebx; TokenType
0x180099f43  lea     edx, [r8+2Ch]; dwDesiredAccess
0x180099f47  call    cs:__imp_DuplicateTokenEx
0x180099f4d  mov     rcx, [rbp+TokenHandle]; hObject
0x180099f51  test    eax, eax
0x180099f53  jz      loc_18009A063
0x180099f59  call    cs:__imp_CloseHandle
0x180099f5f  mov     rcx, [rbp+Token]; TokenHandle
0x180099f63  mov     rdx, r14; unsigned int *
0x180099f66  call    ?EnableAndMapDisabledPrivileges@@YA_NPEAXAEAK@Z; EnableAndMapDisabledPrivileges(void *,ulong &)
0x180099f6b  test    al, al
0x180099f6d  jz      loc_18009A05F
0x180099f73  mov     rdx, [rbp+Token]; Token
0x180099f77  xor     ecx, ecx; Thread
0x180099f79  call    cs:__imp_SetThreadToken
0x180099f7f  test    eax, eax
0x180099f81  jz      loc_18009A05F
0x180099f87  mov     rax, cs:?CoSetProxyBlanket@OLE32@@3P6AJPEAUIUnknown@@KKPEAGKKPEAXK@ZEA; long (*OLE32::CoSetProxyBlanket)(IUnknown *,ulong,ulong,ushort *,ulong,ulong,void *,ulong)
0x180099f8e  mov     r9, r13
0x180099f91  mov     dword ptr [rsp+60h+var_28], 20h ; ' '
0x180099f99  xor     r8d, r8d
0x180099f9c  mov     [rsp+60h+var_30], 0
0x180099fa5  or      edx, 0FFFFFFFFh
0x180099fa8  mov     dword ptr [rsp+60h+phNewToken], 3
0x180099fb0  mov     rcx, r15
0x180099fb3  mov     [rsp+60h+TokenType], ebx
0x180099fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099fbc  mov     rcx, [rbp+Token]; TokenHandle
0x180099fc0  mov     ebx, eax
0x180099fc2  cmp     rcx, r13
0x180099fc5  jz      short loc_18009A006
0x180099fc7  test    dil, dil
0x180099fca  jz      short loc_180099FE4
0x180099fcc  xor     edx, edx; Token
0x180099fce  xor     ecx, ecx; Thread
0x180099fd0  call    cs:__imp_SetThreadToken
0x180099fd6  test    eax, eax
0x180099fd8  jnz     short loc_180099FFC
0x180099fda  call    cs:__imp_GetLastError
0x180099fe0  mov     ebx, eax
0x180099fe2  jmp     short loc_180099FFC
0x180099fe4  mov     edx, [r14]; unsigned int
0x180099fe7  call    ?DisablePrivilegesFromMap@@YA_NPEAXK@Z; DisablePrivilegesFromMap(void *,ulong)
0x180099fec  mov     rdx, [rbp+Token]; Token
0x180099ff0  xor     ecx, ecx; Thread
0x180099ff2  call    cs:__imp_SetThreadToken
0x180099ff8  test    eax, eax
0x180099ffa  jz      short loc_18009A05F
0x180099ffc  mov     rcx, [rbp+Token]; hObject
0x18009a000  call    cs:__imp_CloseHandle
0x18009a006  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x18009a00b  test    ebx, ebx
0x18009a00d  jz      short loc_18009A069
0x18009a00f  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x18009a016  jz      short loc_18009A069
0x18009a018  lea     r8, aNull; "(NULL)"
0x18009a01f  movsxd  rax, ebx
0x18009a022  xor     edx, edx; unsigned __int16
0x18009a024  lea     r9, aSetproxyblanke; "SetProxyBlanket failed with: 0x%X"
0x18009a02b  mov     [rsp+60h+var_8], rdx; void *
0x18009a030  mov     [rsp+60h+var_10], edx; unsigned int
0x18009a034  mov     [rsp+60h+var_18], r8; unsigned __int16 *
0x18009a039  mov     [rsp+60h+var_20], r8; unsigned __int16 *
0x18009a03e  lea     ecx, [rdx+9]; int
0x18009a041  mov     [rsp+60h+var_28], r8; unsigned __int16 *
0x18009a046  mov     [rsp+60h+var_30], r8; unsigned __int16 *
0x18009a04b  mov     [rsp+60h+phNewToken], r8; unsigned __int16 *
0x18009a050  xor     r8d, r8d; int
0x18009a053  mov     qword ptr [rsp+60h+TokenType], rax; unsigned __int16 *
0x18009a058  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18009a05d  jmp     short loc_18009A069
0x18009a05f  mov     rcx, [rbp+Token]; hObject
0x18009a063  call    cs:__imp_CloseHandle
0x18009a069  lea     r11, [rsp+60h+var_s0]
0x18009a06e  mov     rax, rsi
0x18009a071  mov     rbx, [r11+40h]
0x18009a075  mov     rsi, [r11+48h]
0x18009a079  mov     rsp, r11
0x18009a07c  pop     r15
0x18009a07e  pop     r14
0x18009a080  pop     r13
0x18009a082  pop     rdi
0x18009a083  pop     rbp
0x18009a084  retn
```
