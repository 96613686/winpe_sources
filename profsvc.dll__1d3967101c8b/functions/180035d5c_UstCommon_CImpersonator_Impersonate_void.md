# UstCommon::CImpersonator::Impersonate(void *)

- ea: `0x180035d5c`
- end: `0x180035df3`
- name: `?Impersonate@CImpersonator@UstCommon@@QEAAJPEAX@Z`
- size: `151`
- prototype: `int(UstCommon::CImpersonator *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000cc80`

## callees

- `0x180035d5c`
- `0x18004ef50`
- `0x18004f108`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035da2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035da2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180035d91`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180035d91`

## pseudocode

```c
__int64 __fastcall UstCommon::CImpersonator::Impersonate(UstCommon::CImpersonator *this, void *a2, __int64 a3)
{
  unsigned int v5; // ebx
  signed int LastError; // eax

  v5 = 1;
  if ( !*(_BYTE *)this && !UstCommon::CImpersonator::_IsThreadImpersonating(this) )
  {
    v5 = -2147024809;
    if ( a2 )
    {
      if ( ImpersonateLoggedOnUser(a2) )
      {
        *(_BYTE *)this = 1;
        v5 = 0;
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, a3, v5);
  return v5;
}

```

## disassembly

```asm
0x180035d5c  mov     [rsp+arg_0], rbx
0x180035d61  mov     [rsp+arg_8], rsi
0x180035d66  push    rdi
0x180035d67  sub     rsp, 20h
0x180035d6b  cmp     byte ptr [rcx], 0
0x180035d6e  mov     rdi, rdx
0x180035d71  mov     rsi, rcx
0x180035d74  mov     ebx, 1
0x180035d79  jnz     short loc_180035DB7
0x180035d7b  call    ?_IsThreadImpersonating@CImpersonator@UstCommon@@AEAA_NXZ; UstCommon::CImpersonator::_IsThreadImpersonating(void)
0x180035d80  test    al, al
0x180035d82  jnz     short loc_180035DB7
0x180035d84  mov     ebx, 80070057h
0x180035d89  test    rdi, rdi
0x180035d8c  jz      short loc_180035DB7
0x180035d8e  mov     rcx, rdi; hToken
0x180035d91  call    cs:__imp_ImpersonateLoggedOnUser
0x180035d97  test    eax, eax
0x180035d99  jz      short loc_180035DA2
0x180035d9b  mov     byte ptr [rsi], 1
0x180035d9e  xor     ebx, ebx
0x180035da0  jmp     short loc_180035DB7
0x180035da2  call    cs:__imp_GetLastError
0x180035da8  mov     ebx, eax
0x180035daa  test    eax, eax
0x180035dac  jle     short loc_180035DB7
0x180035dae  movzx   ebx, ax
0x180035db1  or      ebx, 80070000h
0x180035db7  mov     rcx, cs:WPP_GLOBAL_Control
0x180035dbe  lea     rax, WPP_GLOBAL_Control
0x180035dc5  cmp     rcx, rax
0x180035dc8  jz      short loc_180035DE1
0x180035dca  test    byte ptr [rcx+1Ch], 2
0x180035dce  jz      short loc_180035DE1
0x180035dd0  mov     rcx, [rcx+10h]
0x180035dd4  mov     edx, 0Dh
0x180035dd9  mov     r9d, ebx
0x180035ddc  call    WPP_SF_D
0x180035de1  mov     rsi, [rsp+28h+arg_8]
0x180035de6  mov     eax, ebx
0x180035de8  mov     rbx, [rsp+28h+arg_0]
0x180035ded  add     rsp, 20h
0x180035df1  pop     rdi
0x180035df2  retn
```
