# _IsTokenLocalSystem

- ea: `0x18000c020`
- end: `0x18000c0c7`
- name: `_IsTokenLocalSystem`
- size: `167`
- prototype: `__int64 __fastcall(HANDLE ClientToken)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000b988`

## callees

- `0x18000c020`
- `0x18000fb50`

## import_xrefs

- `ADVAPI32!AccessCheck` at `0x18000c093`
- `ADVAPI32!AccessCheck` at `0x18000c093`

## pseudocode

```c
__int64 __fastcall IsTokenLocalSystem(HANDLE ClientToken)
{
  unsigned int v1; // ebx
  WINBOOL v3; // [rsp+40h] [rbp-58h] BYREF
  DWORD v4; // [rsp+44h] [rbp-54h] BYREF
  DWORD v5; // [rsp+48h] [rbp-50h] BYREF
  struct _PRIVILEGE_SET v6[2]; // [rsp+50h] [rbp-48h] BYREF

  v5 = 56;
  v4 = 0;
  v3 = 0;
  if ( !ClientToken )
    return 0;
  v1 = 1;
  if ( AccessCheck(qword_180016FB0, ClientToken, 1u, &g_GenericMappingLocalSystem, v6, &v5, &v4, &v3) )
  {
    if ( v3 && v4 == 1 )
      return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x18000c020  mov     r11, rsp
0x18000c023  push    rbx
0x18000c024  sub     rsp, 90h
0x18000c02b  mov     rax, cs:__security_cookie
0x18000c032  xor     rax, rsp
0x18000c035  mov     [rsp+98h+var_10], rax
0x18000c03d  mov     [rsp+98h+var_50], 38h ; '8'
0x18000c045  mov     [rsp+98h+var_54], 0
0x18000c04d  mov     [rsp+98h+var_58], 0
0x18000c055  test    rcx, rcx
0x18000c058  jz      short loc_18000C0AA
0x18000c05a  lea     rax, [r11-58h]
0x18000c05e  mov     rdx, rcx; ClientToken
0x18000c061  mov     [r11-60h], rax
0x18000c065  lea     r9, ?g_GenericMappingLocalSystem@@3U_GENERIC_MAPPING@@A; GenericMapping
0x18000c06c  lea     rax, [r11-54h]
0x18000c070  mov     ebx, 1
0x18000c075  mov     [r11-68h], rax
0x18000c079  lea     rcx, qword_180016FB0; pSecurityDescriptor
0x18000c080  lea     rax, [r11-50h]
0x18000c084  mov     r8d, ebx; DesiredAccess
0x18000c087  mov     [r11-70h], rax
0x18000c08b  lea     rax, [r11-48h]
0x18000c08f  mov     [r11-78h], rax
0x18000c093  call    cs:__imp_AccessCheck
0x18000c099  test    eax, eax
0x18000c09b  jz      short loc_18000C0AC
0x18000c09d  cmp     [rsp+98h+var_58], 0
0x18000c0a2  jz      short loc_18000C0AC
0x18000c0a4  cmp     [rsp+98h+var_54], ebx
0x18000c0a8  jnz     short loc_18000C0AC
0x18000c0aa  xor     ebx, ebx
0x18000c0ac  mov     eax, ebx
0x18000c0ae  mov     rcx, [rsp+98h+var_10]
0x18000c0b6  xor     rcx, rsp; StackCookie
0x18000c0b9  call    __security_check_cookie
0x18000c0be  add     rsp, 90h
0x18000c0c5  pop     rbx
0x18000c0c6  retn
```
