# EnableSinglePrivilege(long)

- ea: `0x180036b78`
- end: `0x180036d55`
- name: `?EnableSinglePrivilege@@YAHJ@Z`
- size: `477`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003827c`

## callees

- `0x18001ad48`
- `0x18001ad74`
- `0x18001ae3c`
- `0x180036b78`
- `0x1800a0fb0`

## import_xrefs

- `ADVAPI32!AdjustTokenPrivileges` at `0x180036c9e`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180036c9e`
- `ADVAPI32!OpenProcessToken` at `0x180036c1c`
- `ADVAPI32!OpenProcessToken` at `0x180036c1c`
- `ntdll!NtClose` at `0x180036cfb`
- `ntdll!NtClose` at `0x180036cfb`
- `KERNEL32!GetCurrentProcess` at `0x180036c03`
- `KERNEL32!GetCurrentProcess` at `0x180036c03`
- `KERNEL32!GetLastError` at `0x180036c48`
- `KERNEL32!GetLastError` at `0x180036cc2`
- `KERNEL32!GetLastError` at `0x180036c48`
- `KERNEL32!GetLastError` at `0x180036cc2`

## string_xrefs

- `0x180036bc4`: `EnableSinglePrivilege`
- `0x180036d20`: `EnableSinglePrivilege`

## pseudocode

```c
__int64 __fastcall EnableSinglePrivilege()
{
  PVOID *v0; // rcx
  HANDLE CurrentProcess; // rax
  unsigned int v2; // ebx
  PVOID *v3; // rcx
  DWORD LastError; // eax
  __int64 v5; // rdx
  void *TokenHandle[2]; // [rsp+30h] [rbp-38h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-28h] BYREF

  TokenHandle[0] = 0;
  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids,
        L"EnableSinglePrivilege");
      v0 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 0x20) != 0 )
      WPP_SF_(v0[2], 18, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids);
  }
  NewState = 0;
  CurrentProcess = GetCurrentProcess();
  v2 = OpenProcessToken(CurrentProcess, 0x28u, TokenHandle);
  if ( v2 )
  {
    TokenHandle[1] = (void *)8;
    NewState.Privileges[0].Luid = (LUID)8LL;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = 2;
    v2 = AdjustTokenPrivileges(TokenHandle[0], 0, &NewState, 0x10u, 0, 0);
    if ( v2 )
    {
LABEL_16:
      v3 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_17;
    }
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      LastError = GetLastError();
      v5 = 20;
      goto LABEL_15;
    }
  }
  else
  {
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      LastError = GetLastError();
      v5 = 19;
LABEL_15:
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids, LastError);
      goto LABEL_16;
    }
  }
LABEL_17:
  if ( TokenHandle[0] )
  {
    NtClose(TokenHandle[0]);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 7) & 0x1000) != 0 )
    WPP_SF_S(v3[2], 21, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids, L"EnableSinglePrivilege");
  return v2;
}

```

## disassembly

```asm
0x180036b78  mov     [rsp+arg_0], rbx
0x180036b7d  mov     [rsp+arg_8], rdi
0x180036b82  push    r14
0x180036b84  sub     rsp, 60h
0x180036b88  mov     rax, cs:__security_cookie
0x180036b8f  xor     rax, rsp
0x180036b92  mov     [rsp+68h+var_18], rax
0x180036b97  and     [rsp+68h+TokenHandle], 0
0x180036b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ba4  lea     rdi, WPP_GLOBAL_Control
0x180036bab  lea     r14, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids
0x180036bb2  cmp     rcx, rdi
0x180036bb5  jz      short loc_180036BFB
0x180036bb7  test    dword ptr [rcx+1Ch], 1000h
0x180036bbe  jz      short loc_180036BDF
0x180036bc0  mov     rcx, [rcx+10h]
0x180036bc4  lea     r9, aEnablesinglepr; "EnableSinglePrivilege"
0x180036bcb  mov     edx, 11h
0x180036bd0  mov     r8, r14
0x180036bd3  call    WPP_SF_S
0x180036bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180036bdf  cmp     rcx, rdi
0x180036be2  jz      short loc_180036BFB
0x180036be4  test    byte ptr [rcx+1Ch], 20h
0x180036be8  jz      short loc_180036BFB
0x180036bea  mov     rcx, [rcx+10h]
0x180036bee  mov     edx, 12h
0x180036bf3  mov     r8, r14
0x180036bf6  call    WPP_SF_
0x180036bfb  xorps   xmm0, xmm0
0x180036bfe  movups  xmmword ptr [rsp+68h+NewState.PrivilegeCount], xmm0
0x180036c03  call    cs:__imp_GetCurrentProcess
0x180036c0a  nop     dword ptr [rax+rax+00h]
0x180036c0f  lea     r8, [rsp+68h+TokenHandle]; TokenHandle
0x180036c14  mov     edx, 28h ; '('; DesiredAccess
0x180036c19  mov     rcx, rax; ProcessHandle
0x180036c1c  call    cs:__imp_OpenProcessToken
0x180036c23  nop     dword ptr [rax+rax+00h]
0x180036c28  mov     ebx, eax
0x180036c2a  test    eax, eax
0x180036c2c  jnz     short loc_180036C59
0x180036c2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036c35  cmp     rcx, rdi
0x180036c38  jz      loc_180036CEE
0x180036c3e  test    byte ptr [rcx+1Ch], 20h
0x180036c42  jz      loc_180036CEE
0x180036c48  call    cs:__imp_GetLastError
0x180036c4f  nop     dword ptr [rax+rax+00h]
0x180036c54  lea     edx, [rbx+13h]
0x180036c57  jmp     short loc_180036CD1
0x180036c59  and     dword ptr [rsp+68h+var_30+4], 0
0x180036c5e  lea     r8, [rsp+68h+NewState]; NewState
0x180036c63  and     [rsp+68h+var_40], 0
0x180036c69  mov     r9d, 10h; BufferLength
0x180036c6f  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x180036c74  xor     edx, edx; DisableAllPrivileges
0x180036c76  and     [rsp+68h+var_48], 0
0x180036c7c  mov     dword ptr [rsp+68h+var_30], 8
0x180036c84  mov     rax, [rsp+68h+var_30]
0x180036c89  mov     qword ptr [rsp+68h+NewState.Privileges.Luid.LowPart], rax
0x180036c8e  mov     [rsp+68h+NewState.PrivilegeCount], 1
0x180036c96  mov     [rsp+68h+NewState.Privileges.Attributes], 2
0x180036c9e  call    cs:__imp_AdjustTokenPrivileges
0x180036ca5  nop     dword ptr [rax+rax+00h]
0x180036caa  mov     ebx, eax
0x180036cac  test    eax, eax
0x180036cae  jnz     short loc_180036CE7
0x180036cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180036cb7  cmp     rcx, rdi
0x180036cba  jz      short loc_180036CEE
0x180036cbc  test    byte ptr [rcx+1Ch], 20h
0x180036cc0  jz      short loc_180036CEE
0x180036cc2  call    cs:__imp_GetLastError
0x180036cc9  nop     dword ptr [rax+rax+00h]
0x180036cce  lea     edx, [rbx+14h]
0x180036cd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180036cd8  mov     r9d, eax
0x180036cdb  mov     r8, r14
0x180036cde  mov     rcx, [rcx+10h]
0x180036ce2  call    WPP_SF_D
0x180036ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x180036cee  mov     rax, [rsp+68h+TokenHandle]
0x180036cf3  test    rax, rax
0x180036cf6  jz      short loc_180036D0E
0x180036cf8  mov     rcx, rax; Handle
0x180036cfb  call    cs:__imp_NtClose
0x180036d02  nop     dword ptr [rax+rax+00h]
0x180036d07  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d0e  cmp     rcx, rdi
0x180036d11  jz      short loc_180036D34
0x180036d13  test    dword ptr [rcx+1Ch], 1000h
0x180036d1a  jz      short loc_180036D34
0x180036d1c  mov     rcx, [rcx+10h]
0x180036d20  lea     r9, aEnablesinglepr; "EnableSinglePrivilege"
0x180036d27  mov     edx, 15h
0x180036d2c  mov     r8, r14
0x180036d2f  call    WPP_SF_S
0x180036d34  mov     eax, ebx
0x180036d36  mov     rcx, [rsp+68h+var_18]
0x180036d3b  xor     rcx, rsp; StackCookie
0x180036d3e  call    __security_check_cookie
0x180036d43  mov     rbx, [rsp+68h+arg_0]
0x180036d48  mov     rdi, [rsp+68h+arg_8]
0x180036d4d  add     rsp, 60h
0x180036d51  pop     r14
0x180036d53  retn
```
