# CUSTOM_USER_CONTEXT::Create(void *,ushort const *,ushort const *)

- ea: `0x18000c728`
- end: `0x18000c7cf`
- name: `?Create@CUSTOM_USER_CONTEXT@@QEAAJPEAXPEBG1@Z`
- size: `167`
- prototype: `int(CUSTOM_USER_CONTEXT *__hidden this, void *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000cc50`

## callees

- `0x18000c728`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c77d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c77d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000c773`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000c773`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000c798`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000c7a9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000c798`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000c7a9`

## pseudocode

```c
int __fastcall CUSTOM_USER_CONTEXT::Create(
        void **this,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int result; // eax
  int v8; // eax
  int v9; // ecx

  if ( !a3 || !a4 )
    return -2147024809;
  if ( !a2 || DuplicateTokenEx(a2, 0xF01FFu, 0, SecurityImpersonation, TokenImpersonation, this + 16) )
  {
    result = STRU::Copy((STRU *)(this + 2), a3);
    if ( result >= 0 )
    {
      v8 = STRU::Copy((STRU *)(this + 9), a4);
      v9 = 0;
      if ( v8 < 0 )
        return v8;
      return v9;
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000c728  mov     r11, rsp
0x18000c72b  mov     [r11+8], rbx
0x18000c72f  mov     [r11+10h], rsi
0x18000c733  push    rdi
0x18000c734  sub     rsp, 30h
0x18000c738  mov     rdi, r9
0x18000c73b  mov     rsi, r8
0x18000c73e  mov     r10, rdx
0x18000c741  mov     rbx, rcx
0x18000c744  test    r8, r8
0x18000c747  jz      short loc_18000C7BA
0x18000c749  test    r9, r9
0x18000c74c  jz      short loc_18000C7BA
0x18000c74e  test    rdx, rdx
0x18000c751  jz      short loc_18000C791
0x18000c753  lea     rax, [rcx+80h]
0x18000c75a  mov     r9d, 2; ImpersonationLevel
0x18000c760  mov     [r11-10h], rax
0x18000c764  xor     r8d, r8d; lpTokenAttributes
0x18000c767  mov     edx, 0F01FFh; dwDesiredAccess
0x18000c76c  mov     [r11-18h], r9d
0x18000c770  mov     rcx, r10; hExistingToken
0x18000c773  call    cs:__imp_DuplicateTokenEx
0x18000c779  test    eax, eax
0x18000c77b  jnz     short loc_18000C791
0x18000c77d  call    cs:__imp_GetLastError
0x18000c783  test    eax, eax
0x18000c785  jle     short loc_18000C7BF
0x18000c787  movzx   eax, ax
0x18000c78a  or      eax, 80070000h
0x18000c78f  jmp     short loc_18000C7BF
0x18000c791  lea     rcx, [rbx+10h]
0x18000c795  mov     rdx, rsi
0x18000c798  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000c79e  test    eax, eax
0x18000c7a0  js      short loc_18000C7BF
0x18000c7a2  lea     rcx, [rbx+48h]
0x18000c7a6  mov     rdx, rdi
0x18000c7a9  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000c7af  xor     ecx, ecx
0x18000c7b1  test    eax, eax
0x18000c7b3  cmovs   ecx, eax
0x18000c7b6  mov     eax, ecx
0x18000c7b8  jmp     short loc_18000C7BF
0x18000c7ba  mov     eax, 80070057h
0x18000c7bf  mov     rbx, [rsp+38h+arg_0]
0x18000c7c4  mov     rsi, [rsp+38h+arg_8]
0x18000c7c9  add     rsp, 30h
0x18000c7cd  pop     rdi
0x18000c7ce  retn
```
