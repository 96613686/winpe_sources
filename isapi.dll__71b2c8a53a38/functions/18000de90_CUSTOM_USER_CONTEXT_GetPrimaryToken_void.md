# CUSTOM_USER_CONTEXT::GetPrimaryToken(void)

- ea: `0x18000de90`
- end: `0x18000dee0`
- name: `?GetPrimaryToken@CUSTOM_USER_CONTEXT@@UEAAPEAXXZ`
- size: `80`
- prototype: `void *__fastcall(CUSTOM_USER_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000de90`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000decd`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000decd`

## pseudocode

```c
void *__fastcall CUSTOM_USER_CONTEXT::GetPrimaryToken(CUSTOM_USER_CONTEXT *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 16);
  if ( v2 && !*((_QWORD *)this + 17) )
    DuplicateTokenEx(v2, 0xF01FFu, 0, SecurityImpersonation, TokenPrimary, (PHANDLE)this + 17);
  return (void *)*((_QWORD *)this + 17);
}

```

## disassembly

```asm
0x18000de90  push    rbx
0x18000de92  sub     rsp, 30h
0x18000de96  mov     rbx, rcx
0x18000de99  mov     rcx, [rcx+80h]; hExistingToken
0x18000dea0  test    rcx, rcx
0x18000dea3  jz      short loc_18000DED3
0x18000dea5  lea     rax, [rbx+88h]
0x18000deac  cmp     qword ptr [rax], 0
0x18000deb0  jnz     short loc_18000DED3
0x18000deb2  mov     [rsp+38h+phNewToken], rax; phNewToken
0x18000deb7  mov     r9d, 2; ImpersonationLevel
0x18000debd  xor     r8d, r8d; lpTokenAttributes
0x18000dec0  mov     [rsp+38h+TokenType], 1; TokenType
0x18000dec8  mov     edx, 0F01FFh; dwDesiredAccess
0x18000decd  call    cs:__imp_DuplicateTokenEx
0x18000ded3  mov     rax, [rbx+88h]
0x18000deda  add     rsp, 30h
0x18000dede  pop     rbx
0x18000dedf  retn
```
