# UstCommon::CImpersonator::Impersonate(void *)

- ea: `0x1800289d4`
- end: `0x180028a72`
- name: `?Impersonate@CImpersonator@UstCommon@@QEAAJPEAX@Z`
- size: `158`
- prototype: `int(UstCommon::CImpersonator *__hidden this, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a084`
- `0x18000ab6c`

## callees

- `0x18000f5cc`
- `0x1800289d4`
- `0x18002971c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180028a09`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180028a09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a1a`

## pseudocode

```c
__int64 __fastcall UstCommon::CImpersonator::Impersonate(UstCommon::CImpersonator *this, void *a2)
{
  unsigned int v4; // ebx
  signed int LastError; // eax

  v4 = 1;
  if ( !*(_BYTE *)this && !UstCommon::CImpersonator::_IsThreadImpersonating(this) )
  {
    v4 = -2147024809;
    if ( a2 )
    {
      if ( ImpersonateLoggedOnUser(a2) )
      {
        *(_BYTE *)this = 1;
        v4 = 0;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1800289d4  mov     [rsp+arg_0], rbx
0x1800289d9  mov     [rsp+arg_8], rsi
0x1800289de  push    rdi
0x1800289df  sub     rsp, 20h
0x1800289e3  cmp     byte ptr [rcx], 0
0x1800289e6  mov     rdi, rdx
0x1800289e9  mov     rsi, rcx
0x1800289ec  mov     ebx, 1
0x1800289f1  jnz     short loc_180028A2F
0x1800289f3  call    ?_IsThreadImpersonating@CImpersonator@UstCommon@@AEAA_NXZ; UstCommon::CImpersonator::_IsThreadImpersonating(void)
0x1800289f8  test    al, al
0x1800289fa  jnz     short loc_180028A2F
0x1800289fc  mov     ebx, 80070057h
0x180028a01  test    rdi, rdi
0x180028a04  jz      short loc_180028A2F
0x180028a06  mov     rcx, rdi; hToken
0x180028a09  call    cs:__imp_ImpersonateLoggedOnUser
0x180028a0f  test    eax, eax
0x180028a11  jz      short loc_180028A1A
0x180028a13  mov     byte ptr [rsi], 1
0x180028a16  xor     ebx, ebx
0x180028a18  jmp     short loc_180028A2F
0x180028a1a  call    cs:__imp_GetLastError
0x180028a20  mov     ebx, eax
0x180028a22  test    eax, eax
0x180028a24  jle     short loc_180028A2F
0x180028a26  movzx   ebx, ax
0x180028a29  or      ebx, 80070000h
0x180028a2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a36  lea     rax, WPP_GLOBAL_Control
0x180028a3d  cmp     rcx, rax
0x180028a40  jz      short loc_180028A60
0x180028a42  test    byte ptr [rcx+1Ch], 2
0x180028a46  jz      short loc_180028A60
0x180028a48  mov     rcx, [rcx+10h]
0x180028a4c  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x180028a53  mov     edx, 0Dh
0x180028a58  mov     r9d, ebx
0x180028a5b  call    WPP_SF_d
0x180028a60  mov     rsi, [rsp+28h+arg_8]
0x180028a65  mov     eax, ebx
0x180028a67  mov     rbx, [rsp+28h+arg_0]
0x180028a6c  add     rsp, 20h
0x180028a70  pop     rdi
0x180028a71  retn
```
