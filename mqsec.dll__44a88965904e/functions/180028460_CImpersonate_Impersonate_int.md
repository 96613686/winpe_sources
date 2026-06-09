# CImpersonate::Impersonate(int)

- ea: `0x180028460`
- end: `0x180028585`
- name: `?Impersonate@CImpersonate@@EEAAHH@Z`
- size: `293`
- prototype: `__int64 __fastcall(CImpersonate *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028214`

## callees

- `0x1800049ac`
- `0x180028460`
- `0x1800292f8`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180028480`
- `RPCRT4!RpcImpersonateClient` at `0x180028480`
- `ADVAPI32!ImpersonateSelf` at `0x180028534`
- `ADVAPI32!ImpersonateSelf` at `0x180028534`
- `ADVAPI32!ImpersonateAnonymousToken` at `0x1800284cd`
- `ADVAPI32!ImpersonateAnonymousToken` at `0x1800284cd`
- `KERNEL32!GetCurrentThread` at `0x1800284c4`
- `KERNEL32!GetCurrentThread` at `0x1800284c4`
- `KERNEL32!GetLastError` at `0x1800284f7`
- `KERNEL32!GetLastError` at `0x18002853e`
- `KERNEL32!GetLastError` at `0x1800284f7`
- `KERNEL32!GetLastError` at `0x18002853e`

## pseudocode

```c
__int64 __fastcall CImpersonate::Impersonate(CImpersonate *this, int a2)
{
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx

  if ( *((_DWORD *)this + 2) )
  {
    v4 = RpcImpersonateClient(0);
    *((_DWORD *)this + 6) = v4;
    if ( !v4 )
      return 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 32), v5, v6, v4, a2);
    if ( a2 )
    {
      CurrentThread = GetCurrentThread();
      if ( ImpersonateAnonymousToken(CurrentThread) )
      {
        *((_BYTE *)this + 28) = 1;
        *((_DWORD *)this + 6) = 0;
        return 1;
      }
      LastError = GetLastError();
      *((_DWORD *)this + 6) = LastError;
      if ( !LastError )
      {
        LastError = 1764;
        *((_DWORD *)this + 6) = 1764;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      {
        v11 = 18;
LABEL_19:
        WPP_SF_d(v10[32], v11, &WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids, LastError);
      }
    }
  }
  else
  {
    *((_DWORD *)this + 6) = 0;
    if ( ImpersonateSelf(SecurityIdentification) )
      return 1;
    LastError = GetLastError();
    *((_DWORD *)this + 6) = LastError;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v11 = 19;
      goto LABEL_19;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180028460  mov     [rsp+arg_0], rbp
0x180028465  mov     [rsp+arg_8], rsi
0x18002846a  push    rdi
0x18002846b  sub     rsp, 30h
0x18002846f  cmp     dword ptr [rcx+8], 0
0x180028473  mov     ebp, edx
0x180028475  mov     rdi, rcx
0x180028478  jz      loc_180028528
0x18002847e  xor     ecx, ecx; BindingHandle
0x180028480  call    cs:__imp_RpcImpersonateClient
0x180028486  mov     [rdi+18h], eax
0x180028489  test    eax, eax
0x18002848b  jz      short loc_1800284E2
0x18002848d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028494  lea     rsi, WPP_GLOBAL_Control
0x18002849b  cmp     rcx, rsi
0x18002849e  jz      short loc_1800284BC
0x1800284a0  test    byte ptr [rcx+10Ch], 1
0x1800284a7  jz      short loc_1800284BC
0x1800284a9  mov     rcx, [rcx+100h]
0x1800284b0  mov     r9d, eax
0x1800284b3  mov     [rsp+38h+var_18], ebp
0x1800284b7  call    WPP_SF_Dd
0x1800284bc  test    ebp, ebp
0x1800284be  jz      loc_18002857E
0x1800284c4  call    cs:__imp_GetCurrentThread
0x1800284ca  mov     rcx, rax; ThreadHandle
0x1800284cd  call    cs:__imp_ImpersonateAnonymousToken
0x1800284d3  test    eax, eax
0x1800284d5  jz      short loc_1800284F7
0x1800284d7  mov     byte ptr [rdi+1Ch], 1
0x1800284db  mov     dword ptr [rdi+18h], 0
0x1800284e2  mov     eax, 1
0x1800284e7  mov     rbp, [rsp+38h+arg_0]
0x1800284ec  mov     rsi, [rsp+38h+arg_8]
0x1800284f1  add     rsp, 30h
0x1800284f5  pop     rdi
0x1800284f6  retn
0x1800284f7  call    cs:__imp_GetLastError
0x1800284fd  mov     [rdi+18h], eax
0x180028500  test    eax, eax
0x180028502  jnz     short loc_18002850C
0x180028504  mov     eax, 6E4h
0x180028509  mov     [rdi+18h], eax
0x18002850c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028513  cmp     rcx, rsi
0x180028516  jz      short loc_18002857E
0x180028518  test    byte ptr [rcx+10Ch], 1
0x18002851f  jz      short loc_18002857E
0x180028521  mov     edx, 12h
0x180028526  jmp     short loc_180028568
0x180028528  mov     dword ptr [rcx+18h], 0
0x18002852f  mov     ecx, 1; ImpersonationLevel
0x180028534  call    cs:__imp_ImpersonateSelf
0x18002853a  test    eax, eax
0x18002853c  jnz     short loc_1800284E2
0x18002853e  call    cs:__imp_GetLastError
0x180028544  mov     [rdi+18h], eax
0x180028547  mov     rcx, cs:WPP_GLOBAL_Control
0x18002854e  lea     rsi, WPP_GLOBAL_Control
0x180028555  cmp     rcx, rsi
0x180028558  jz      short loc_18002857E
0x18002855a  test    byte ptr [rcx+10Ch], 1
0x180028561  jz      short loc_18002857E
0x180028563  mov     edx, 13h
0x180028568  mov     rcx, [rcx+100h]
0x18002856f  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x180028576  mov     r9d, eax
0x180028579  call    WPP_SF_d
0x18002857e  xor     eax, eax
0x180028580  jmp     loc_1800284E7
```
