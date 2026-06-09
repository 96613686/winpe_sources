# Vml::VmAccessToken::EnablePrivilege(_LUID const &,int)

- ea: `0x18000ab54`
- end: `0x18000abff`
- name: `?EnablePrivilege@VmAccessToken@Vml@@QEAAHAEBU_LUID@@H@Z`
- size: `171`
- prototype: `__int64 __fastcall(void **this, const struct _LUID *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008a8c`
- `0x18000971c`

## callees

- `0x180002690`
- `0x18000ab54`
- `0x1800136f8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000abb1`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000abb1`

## string_xrefs

- `0x18000abed`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
__int64 __fastcall Vml::VmAccessToken::EnablePrivilege(void **this, const struct _LUID *a2, int a3)
{
  LUID v3; // rax
  void *v4; // rcx
  unsigned int v5; // ebx
  const char *v6; // r9
  DWORD v8; // [rsp+30h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES v9; // [rsp+38h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES v10; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = *a2;
  v4 = *this;
  v8 = 16;
  v5 = 1;
  v9.PrivilegeCount = 1;
  v9.Privileges[0].Luid = v3;
  v9.Privileges[0].Attributes = a3 != 0 ? 2 : 0;
  v10 = 0;
  if ( !AdjustTokenPrivileges(v4, 0, &v9, 0x10u, &v10, &v8) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1B67,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v6);
  if ( v10.PrivilegeCount )
    return (v10.Privileges[0].Attributes & 2) != 0;
  return v5;
}

```

## disassembly

```asm
0x18000ab54  mov     r11, rsp
0x18000ab57  push    rbx
0x18000ab58  sub     rsp, 60h
0x18000ab5c  mov     rax, cs:__security_cookie
0x18000ab63  xor     rax, rsp
0x18000ab66  mov     [rsp+68h+var_10], rax
0x18000ab6b  mov     rax, [rdx]
0x18000ab6e  mov     r9d, 10h; BufferLength
0x18000ab74  mov     rcx, [rcx]; TokenHandle
0x18000ab77  neg     r8d
0x18000ab7a  xorps   xmm0, xmm0
0x18000ab7d  mov     [r11-38h], r9d
0x18000ab81  lea     r8, [r11-30h]; NewState
0x18000ab85  lea     ebx, [r9-0Fh]
0x18000ab89  mov     [rsp+68h+var_30], ebx
0x18000ab8d  mov     [r11-2Ch], rax
0x18000ab91  sbb     eax, eax
0x18000ab93  and     eax, 2
0x18000ab96  xor     edx, edx; DisableAllPrivileges
0x18000ab98  mov     [rsp+68h+var_24], eax
0x18000ab9c  lea     rax, [r11-38h]
0x18000aba0  mov     [r11-40h], rax
0x18000aba4  lea     rax, [r11-20h]
0x18000aba8  mov     [r11-48h], rax
0x18000abac  movups  [rsp+68h+var_20], xmm0
0x18000abb1  call    cs:__imp_AdjustTokenPrivileges
0x18000abb8  nop     dword ptr [rax+rax+00h]
0x18000abbd  test    eax, eax
0x18000abbf  jz      short loc_18000ABE8
0x18000abc1  cmp     dword ptr [rsp+68h+var_20], 0
0x18000abc6  jz      short loc_18000ABD2
0x18000abc8  mov     eax, dword ptr [rsp+68h+var_20+0Ch]
0x18000abcc  test    al, 2
0x18000abce  jnz     short loc_18000ABD2
0x18000abd0  xor     ebx, ebx
0x18000abd2  mov     eax, ebx
0x18000abd4  mov     rcx, [rsp+68h+var_10]
0x18000abd9  xor     rcx, rsp; StackCookie
0x18000abdc  call    __security_check_cookie
0x18000abe1  add     rsp, 60h
0x18000abe5  pop     rbx
0x18000abe6  retn
0x18000abe8  mov     rcx, [rsp+68h]; this
0x18000abed  lea     r8, aOnecoreVmCommo_7; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18000abf4  mov     edx, 1B67h; void *
0x18000abf9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
