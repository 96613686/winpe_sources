# UserTokenUtility::GetTokenSessionId(void *,ulong *)

- ea: `0x180024df8`
- end: `0x180024ed5`
- name: `?GetTokenSessionId@UserTokenUtility@@SAJPEAXPEAK@Z`
- size: `221`
- prototype: `__int64 __fastcall(void *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e7c0`
- `0x180024edc`

## callees

- `0x180009f00`
- `0x180024df8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024e46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024e46`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024e3c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024e3c`

## pseudocode

```c
__int64 __fastcall UserTokenUtility::GetTokenSessionId(void *a1, unsigned int *a2)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  DWORD ReturnLength; // [rsp+40h] [rbp+8h] BYREF
  unsigned int TokenInformation; // [rsp+50h] [rbp+18h] BYREF

  TokenInformation = 0;
  ReturnLength = 0;
  if ( !a1 || !a2 )
    return (unsigned int)-2147024809;
  if ( GetTokenInformation(a1, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
  {
    v7 = ReturnLength;
    if ( ReturnLength == 4 )
    {
      *a2 = TokenInformation;
      return 0;
    }
    v4 = -2147467259;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 11;
      goto LABEL_9;
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 10;
      v7 = v4;
LABEL_9:
      WPP_SF_d(v5[2], v6, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids, v7);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180024df8  push    rbx
0x180024dfa  sub     rsp, 30h
0x180024dfe  mov     [rsp+38h+TokenInformation], 0
0x180024e06  mov     rbx, rdx
0x180024e09  mov     [rsp+38h+arg_0], 0
0x180024e11  test    rcx, rcx
0x180024e14  jz      loc_180024EC8
0x180024e1a  test    rdx, rdx
0x180024e1d  jz      loc_180024EC8
0x180024e23  mov     r9d, 4; TokenInformationLength
0x180024e29  lea     rax, [rsp+38h+arg_0]
0x180024e2e  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180024e33  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180024e38  lea     edx, [r9+8]; TokenInformationClass
0x180024e3c  call    cs:__imp_GetTokenInformation
0x180024e42  test    eax, eax
0x180024e44  jnz     short loc_180024E8E
0x180024e46  call    cs:__imp_GetLastError
0x180024e4c  mov     ebx, eax
0x180024e4e  test    eax, eax
0x180024e50  jle     short loc_180024E5B
0x180024e52  movzx   ebx, ax
0x180024e55  or      ebx, 80070000h
0x180024e5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e62  lea     rax, WPP_GLOBAL_Control
0x180024e69  cmp     rcx, rax
0x180024e6c  jz      short loc_180024ECD
0x180024e6e  test    byte ptr [rcx+1Ch], 1
0x180024e72  jz      short loc_180024ECD
0x180024e74  mov     edx, 0Ah
0x180024e79  mov     r9d, ebx
0x180024e7c  mov     rcx, [rcx+10h]
0x180024e80  lea     r8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids
0x180024e87  call    WPP_SF_d
0x180024e8c  jmp     short loc_180024ECD
0x180024e8e  mov     r9d, [rsp+38h+arg_0]
0x180024e93  cmp     r9d, 4
0x180024e97  jz      short loc_180024EBE
0x180024e99  mov     ebx, 80004005h
0x180024e9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024ea5  lea     rax, WPP_GLOBAL_Control
0x180024eac  cmp     rcx, rax
0x180024eaf  jz      short loc_180024ECD
0x180024eb1  test    byte ptr [rcx+1Ch], 1
0x180024eb5  jz      short loc_180024ECD
0x180024eb7  mov     edx, 0Bh
0x180024ebc  jmp     short loc_180024E7C
0x180024ebe  mov     eax, [rsp+38h+TokenInformation]
0x180024ec2  mov     [rbx], eax
0x180024ec4  xor     ebx, ebx
0x180024ec6  jmp     short loc_180024ECD
0x180024ec8  mov     ebx, 80070057h
0x180024ecd  mov     eax, ebx
0x180024ecf  add     rsp, 30h
0x180024ed3  pop     rbx
0x180024ed4  retn
```
