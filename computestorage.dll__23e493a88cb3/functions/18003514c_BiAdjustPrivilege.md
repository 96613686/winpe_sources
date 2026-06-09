# BiAdjustPrivilege

- ea: `0x18003514c`
- end: `0x180035261`
- name: `BiAdjustPrivilege`
- size: `277`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800350ac`
- `0x1800352f8`

## callees

- `0x180002690`
- `0x18003514c`
- `0x180035268`

## import_xrefs

- `ntdll!NtAdjustPrivilegesToken` at `0x1800351e9`
- `ntdll!NtAdjustPrivilegesToken` at `0x1800351e9`
- `ntdll!NtClose` at `0x180035231`
- `ntdll!NtClose` at `0x180035231`

## pseudocode

```c
__int64 __fastcall BiAdjustPrivilege(DWORD a1, char a2, bool *a3)
{
  int v6; // ebx
  NTSTATUS v7; // eax
  ULONG ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+50h] [rbp-20h] BYREF

  ReturnLength = 0;
  TokenHandle = (HANDLE)-1LL;
  NewState = 0;
  PreviousState = 0;
  v6 = BiOpenEffectiveToken(&TokenHandle);
  if ( v6 >= 0 )
  {
    *(_QWORD *)&NewState.Privileges[0].Luid.HighPart = 0;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Luid.LowPart = a1;
    if ( a2 )
      NewState.Privileges[0].Attributes = 2;
    v7 = NtAdjustPrivilegesToken(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength);
    v6 = v7;
    if ( v7 == 262 )
    {
      v6 = -1073741727;
    }
    else if ( v7 >= 0 )
    {
      if ( PreviousState.PrivilegeCount )
        *a3 = (PreviousState.Privileges[0].Attributes & 2) != 0;
      else
        *a3 = a2 != 0;
    }
    if ( TokenHandle != (HANDLE)-1LL )
      NtClose(TokenHandle);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003514c  mov     [rsp-18h+arg_0], rbx
0x180035151  mov     [rsp-18h+arg_8], rsi
0x180035156  push    rbp
0x180035157  push    rdi
0x180035158  push    r14
0x18003515a  mov     rbp, rsp
0x18003515d  sub     rsp, 70h
0x180035161  mov     rax, cs:__security_cookie
0x180035168  xor     rax, rsp
0x18003516b  mov     [rbp+var_10], rax
0x18003516f  mov     r14d, ecx
0x180035172  mov     [rbp+var_40], 0
0x180035179  xorps   xmm0, xmm0
0x18003517c  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180035184  xorps   xmm1, xmm1
0x180035187  lea     rcx, [rbp+TokenHandle]; TokenHandle
0x18003518b  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18003518f  mov     rdi, r8
0x180035192  mov     sil, dl
0x180035195  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm1
0x180035199  call    BiOpenEffectiveToken
0x18003519e  mov     ebx, eax
0x1800351a0  test    eax, eax
0x1800351a2  js      loc_18003523D
0x1800351a8  mov     qword ptr [rbp+NewState.Privileges.Luid.HighPart], 0
0x1800351b0  mov     [rbp+NewState.PrivilegeCount], 1
0x1800351b7  mov     [rbp+NewState.Privileges.Luid.LowPart], r14d
0x1800351bb  test    sil, sil
0x1800351be  jz      short loc_1800351C7
0x1800351c0  mov     [rbp+NewState.Privileges.Attributes], 2
0x1800351c7  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800351cb  lea     rax, [rbp+var_40]
0x1800351cf  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800351d4  lea     r8, [rbp+NewState]; NewState
0x1800351d8  lea     rax, [rbp+var_20]
0x1800351dc  mov     r9d, 10h; BufferLength
0x1800351e2  xor     edx, edx; DisableAllPrivileges
0x1800351e4  mov     [rsp+70h+PreviousState], rax; PreviousState
0x1800351e9  call    cs:__imp_NtAdjustPrivilegesToken
0x1800351f0  nop     dword ptr [rax+rax+00h]
0x1800351f5  mov     ebx, eax
0x1800351f7  cmp     eax, 106h
0x1800351fc  jnz     short loc_180035205
0x1800351fe  mov     ebx, 0C0000061h
0x180035203  jmp     short loc_180035227
0x180035205  test    eax, eax
0x180035207  js      short loc_180035227
0x180035209  cmp     [rbp+var_20.PrivilegeCount], 0
0x18003520d  jnz     short loc_180035219
0x18003520f  test    sil, sil
0x180035212  setnz   al
0x180035215  mov     [rdi], al
0x180035217  jmp     short loc_180035227
0x180035219  test    byte ptr [rbp+var_20.Privileges.Attributes], 2
0x18003521d  jz      short loc_180035224
0x18003521f  mov     byte ptr [rdi], 1
0x180035222  jmp     short loc_180035227
0x180035224  mov     byte ptr [rdi], 0
0x180035227  mov     rcx, [rbp+TokenHandle]; Handle
0x18003522b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003522f  jz      short loc_18003523D
0x180035231  call    cs:__imp_NtClose
0x180035238  nop     dword ptr [rax+rax+00h]
0x18003523d  mov     eax, ebx
0x18003523f  mov     rcx, [rbp+var_10]
0x180035243  xor     rcx, rsp; StackCookie
0x180035246  call    __security_check_cookie
0x18003524b  lea     r11, [rsp+70h+var_s0]
0x180035250  mov     rbx, [r11+20h]
0x180035254  mov     rsi, [r11+28h]
0x180035258  mov     rsp, r11
0x18003525b  pop     r14
0x18003525d  pop     rdi
0x18003525e  pop     rbp
0x18003525f  retn
```
