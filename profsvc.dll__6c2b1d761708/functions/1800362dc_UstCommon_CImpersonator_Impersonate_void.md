# UstCommon::CImpersonator::Impersonate(void *)

- ea: `0x1800362dc`
- end: `0x180036380`
- name: `?Impersonate@CImpersonator@UstCommon@@QEAAJPEAX@Z`
- size: `164`
- prototype: `int(UstCommon::CImpersonator *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a7e0`

## callees

- `0x1800362dc`
- `0x180052270`
- `0x18005245c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036328`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180036311`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180036311`

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
0x1800362dc  mov     [rsp+arg_0], rbx
0x1800362e1  mov     [rsp+arg_8], rsi
0x1800362e6  push    rdi
0x1800362e7  sub     rsp, 20h
0x1800362eb  cmp     byte ptr [rcx], 0
0x1800362ee  mov     rdi, rdx
0x1800362f1  mov     rsi, rcx
0x1800362f4  mov     ebx, 1
0x1800362f9  jnz     short loc_180036343
0x1800362fb  call    ?_IsThreadImpersonating@CImpersonator@UstCommon@@AEAA_NXZ; UstCommon::CImpersonator::_IsThreadImpersonating(void)
0x180036300  test    al, al
0x180036302  jnz     short loc_180036343
0x180036304  mov     ebx, 80070057h
0x180036309  test    rdi, rdi
0x18003630c  jz      short loc_180036343
0x18003630e  mov     rcx, rdi; hToken
0x180036311  call    cs:__imp_ImpersonateLoggedOnUser
0x180036318  nop     dword ptr [rax+rax+00h]
0x18003631d  test    eax, eax
0x18003631f  jz      short loc_180036328
0x180036321  mov     byte ptr [rsi], 1
0x180036324  xor     ebx, ebx
0x180036326  jmp     short loc_180036343
0x180036328  call    cs:__imp_GetLastError
0x18003632f  nop     dword ptr [rax+rax+00h]
0x180036334  mov     ebx, eax
0x180036336  test    eax, eax
0x180036338  jle     short loc_180036343
0x18003633a  movzx   ebx, ax
0x18003633d  or      ebx, 80070000h
0x180036343  mov     rcx, cs:WPP_GLOBAL_Control
0x18003634a  lea     rax, WPP_GLOBAL_Control
0x180036351  cmp     rcx, rax
0x180036354  jz      short loc_18003636D
0x180036356  test    byte ptr [rcx+1Ch], 2
0x18003635a  jz      short loc_18003636D
0x18003635c  mov     rcx, [rcx+10h]
0x180036360  mov     edx, 0Dh
0x180036365  mov     r9d, ebx
0x180036368  call    WPP_SF_D
0x18003636d  mov     rsi, [rsp+28h+arg_8]
0x180036372  mov     eax, ebx
0x180036374  mov     rbx, [rsp+28h+arg_0]
0x180036379  add     rsp, 20h
0x18003637d  pop     rdi
0x18003637e  retn
```
