# _AddMandatoryAllowACEs

- ea: `0x180023e0c`
- end: `0x180023eef`
- name: `_AddMandatoryAllowACEs`
- size: `227`
- prototype: `__int64 __fastcall(PSID pSid, PACL pAcl)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800247e4`

## callees

- `0x1800049ac`
- `0x180023e0c`

## import_xrefs

- `ADVAPI32!AddAccessAllowedAce` at `0x180023e3d`
- `ADVAPI32!AddAccessAllowedAce` at `0x180023ea8`
- `ADVAPI32!AddAccessAllowedAce` at `0x180023e3d`
- `ADVAPI32!AddAccessAllowedAce` at `0x180023ea8`
- `KERNEL32!GetLastError` at `0x180023e47`
- `KERNEL32!GetLastError` at `0x180023eb2`
- `KERNEL32!GetLastError` at `0x180023e47`
- `KERNEL32!GetLastError` at `0x180023eb2`

## pseudocode

```c
__int64 __fastcall AddMandatoryAllowACEs(PSID pSid, PACL pAcl, int a3, int a4)
{
  DWORD LastError; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx

  if ( a3 || AddAccessAllowedAce(pAcl, 4u, 0xF00FFu, g_pSystemSid) )
  {
    if ( a4 || AddAccessAllowedAce(pAcl, 4u, 0x30u, pSid) )
      return 0;
    LastError = GetLastError();
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v9 = 13;
      goto LABEL_6;
    }
  }
  else
  {
    LastError = GetLastError();
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v9 = 12;
LABEL_6:
      WPP_SF_d(v8[32], v9, &WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids, LastError);
    }
  }
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x180023e0c  mov     [rsp+arg_0], rbx
0x180023e11  mov     [rsp+arg_8], rsi
0x180023e16  push    rdi
0x180023e17  sub     rsp, 20h
0x180023e1b  mov     ebx, r9d
0x180023e1e  mov     rdi, rdx
0x180023e21  mov     rsi, rcx
0x180023e24  test    r8d, r8d
0x180023e27  jnz     short loc_180023E97
0x180023e29  mov     r9, cs:?g_pSystemSid@@3PEAXEA; pSid
0x180023e30  lea     edx, [r8+4]; dwAceRevision
0x180023e34  mov     r8d, 0F00FFh; AccessMask
0x180023e3a  mov     rcx, rdi; pAcl
0x180023e3d  call    cs:__imp_AddAccessAllowedAce
0x180023e43  test    eax, eax
0x180023e45  jnz     short loc_180023E97
0x180023e47  call    cs:__imp_GetLastError
0x180023e4d  mov     ebx, eax
0x180023e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e56  lea     rax, WPP_GLOBAL_Control
0x180023e5d  cmp     rcx, rax
0x180023e60  jz      short loc_180023E86
0x180023e62  test    byte ptr [rcx+10Ch], 1
0x180023e69  jz      short loc_180023E86
0x180023e6b  mov     edx, 0Ch
0x180023e70  mov     rcx, [rcx+100h]
0x180023e77  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x180023e7e  mov     r9d, ebx
0x180023e81  call    WPP_SF_d
0x180023e86  test    ebx, ebx
0x180023e88  jle     short loc_180023E93
0x180023e8a  movzx   ebx, bx
0x180023e8d  or      ebx, 80070000h
0x180023e93  mov     eax, ebx
0x180023e95  jmp     short loc_180023EDF
0x180023e97  test    ebx, ebx
0x180023e99  jnz     short loc_180023EDD
0x180023e9b  mov     r9, rsi; pSid
0x180023e9e  lea     edx, [rbx+4]; dwAceRevision
0x180023ea1  lea     r8d, [rbx+30h]; AccessMask
0x180023ea5  mov     rcx, rdi; pAcl
0x180023ea8  call    cs:__imp_AddAccessAllowedAce
0x180023eae  test    eax, eax
0x180023eb0  jnz     short loc_180023EDD
0x180023eb2  call    cs:__imp_GetLastError
0x180023eb8  mov     ebx, eax
0x180023eba  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ec1  lea     rax, WPP_GLOBAL_Control
0x180023ec8  cmp     rcx, rax
0x180023ecb  jz      short loc_180023E86
0x180023ecd  test    byte ptr [rcx+10Ch], 1
0x180023ed4  jz      short loc_180023E86
0x180023ed6  mov     edx, 0Dh
0x180023edb  jmp     short loc_180023E70
0x180023edd  xor     eax, eax
0x180023edf  mov     rbx, [rsp+28h+arg_0]
0x180023ee4  mov     rsi, [rsp+28h+arg_8]
0x180023ee9  add     rsp, 20h
0x180023eed  pop     rdi
0x180023eee  retn
```
