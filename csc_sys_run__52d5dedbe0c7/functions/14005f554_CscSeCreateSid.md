# CscSeCreateSid

- ea: `0x14005f554`
- end: `0x14005f674`
- name: `CscSeCreateSid`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400173e8`

## callees

- `0x140019284`
- `0x14002f010`
- `0x14005f554`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005f5b1`
- `ntoskrnl!ExAllocatePool2` at `0x14005f5b1`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14005f598`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14005f598`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14005f62d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14005f647`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14005f660`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14005f62d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14005f647`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14005f660`
- `ntoskrnl!RtlInitializeSid` at `0x14005f5dc`
- `ntoskrnl!RtlInitializeSid` at `0x14005f5dc`

## pseudocode

```c
__int64 __fastcall CscSeCreateSid(_QWORD *a1, int a2)
{
  void *v2; // rdi
  NTSTATUS v5; // ebx
  UCHAR v6; // bl
  ULONG v7; // eax
  __int64 v8; // r9
  void *Pool2; // rax
  void *v11; // [rsp+20h] [rbp-48h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+28h] [rbp-40h] BYREF

  v2 = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  if ( a2 )
  {
    if ( a2 != 1 )
    {
      v5 = -1073741811;
      goto LABEL_13;
    }
    v6 = 2;
  }
  else
  {
    v6 = 1;
  }
  v7 = RtlLengthRequiredSid(v6);
  Pool2 = (void *)ExAllocatePool2(258, v7, 557871939, v8);
  v11 = Pool2;
  v2 = Pool2;
  if ( Pool2 )
  {
    v5 = RtlInitializeSid(Pool2, &IdentifierAuthority, v6);
    if ( v5 >= 0 )
    {
      if ( !a2 )
      {
        *RtlSubAuthoritySid(v2, 0) = 18;
        goto LABEL_13;
      }
      if ( a2 == 1 )
      {
        *RtlSubAuthoritySid(v2, 0) = 32;
        *RtlSubAuthoritySid(v2, 1u) = 544;
        goto LABEL_13;
      }
      v5 = -1073741811;
    }
    CscSeDestroySid(&v11);
    v2 = v11;
  }
  else
  {
    v5 = -1073741670;
  }
LABEL_13:
  *a1 = v2;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14005f554  push    rbx
0x14005f556  push    rsi
0x14005f557  push    rdi
0x14005f558  push    r14
0x14005f55a  sub     rsp, 48h
0x14005f55e  mov     rax, cs:__security_cookie
0x14005f565  xor     rax, rsp
0x14005f568  mov     [rsp+68h+var_38], rax
0x14005f56d  xor     edi, edi
0x14005f56f  mov     word ptr [rsp+68h+IdentifierAuthority.Value+4], 500h
0x14005f576  mov     dword ptr [rsp+68h+IdentifierAuthority.Value], edi
0x14005f57a  mov     esi, edx
0x14005f57c  mov     r14, rcx
0x14005f57f  test    edx, edx
0x14005f581  jz      short loc_14005F593
0x14005f583  cmp     edx, 1
0x14005f586  jz      short loc_14005F58F
0x14005f588  mov     ebx, 0C000000Dh
0x14005f58d  jmp     short loc_14005F60B
0x14005f58f  mov     bl, 2
0x14005f591  jmp     short loc_14005F595
0x14005f593  mov     bl, 1
0x14005f595  movzx   ecx, bl; SubAuthorityCount
0x14005f598  call    cs:__imp_RtlLengthRequiredSid
0x14005f59f  nop     dword ptr [rax+rax+00h]
0x14005f5a4  mov     edx, eax
0x14005f5a6  mov     ecx, 102h
0x14005f5ab  mov     r8d, 21407343h
0x14005f5b1  call    cs:__imp_ExAllocatePool2
0x14005f5b8  nop     dword ptr [rax+rax+00h]
0x14005f5bd  mov     [rsp+68h+var_48], rax
0x14005f5c2  mov     rdi, rax
0x14005f5c5  test    rax, rax
0x14005f5c8  jnz     short loc_14005F5D1
0x14005f5ca  mov     ebx, 0C000009Ah
0x14005f5cf  jmp     short loc_14005F60B
0x14005f5d1  mov     r8b, bl; SubAuthorityCount
0x14005f5d4  lea     rdx, [rsp+68h+IdentifierAuthority]; IdentifierAuthority
0x14005f5d9  mov     rcx, rdi; Sid
0x14005f5dc  call    cs:__imp_RtlInitializeSid
0x14005f5e3  nop     dword ptr [rax+rax+00h]
0x14005f5e8  mov     ebx, eax
0x14005f5ea  test    eax, eax
0x14005f5ec  js      short loc_14005F5FC
0x14005f5ee  test    esi, esi
0x14005f5f0  jz      short loc_14005F65B
0x14005f5f2  cmp     esi, 1
0x14005f5f5  jz      short loc_14005F628
0x14005f5f7  mov     ebx, 0C000000Dh
0x14005f5fc  lea     rcx, [rsp+68h+var_48]
0x14005f601  call    CscSeDestroySid
0x14005f606  mov     rdi, [rsp+68h+var_48]
0x14005f60b  mov     [r14], rdi
0x14005f60e  mov     eax, ebx
0x14005f610  mov     rcx, [rsp+68h+var_38]
0x14005f615  xor     rcx, rsp; StackCookie
0x14005f618  call    __security_check_cookie
0x14005f61d  add     rsp, 48h
0x14005f621  pop     r14
0x14005f623  pop     rdi
0x14005f624  pop     rsi
0x14005f625  pop     rbx
0x14005f626  retn
0x14005f628  xor     edx, edx; SubAuthority
0x14005f62a  mov     rcx, rdi; Sid
0x14005f62d  call    cs:__imp_RtlSubAuthoritySid
0x14005f634  nop     dword ptr [rax+rax+00h]
0x14005f639  mov     edx, 1; SubAuthority
0x14005f63e  mov     rcx, rdi; Sid
0x14005f641  mov     dword ptr [rax], 20h ; ' '
0x14005f647  call    cs:__imp_RtlSubAuthoritySid
0x14005f64e  nop     dword ptr [rax+rax+00h]
0x14005f653  mov     dword ptr [rax], 220h
0x14005f659  jmp     short loc_14005F60B
0x14005f65b  xor     edx, edx; SubAuthority
0x14005f65d  mov     rcx, rdi; Sid
0x14005f660  call    cs:__imp_RtlSubAuthoritySid
0x14005f667  nop     dword ptr [rax+rax+00h]
0x14005f66c  mov     dword ptr [rax], 12h
0x14005f672  jmp     short loc_14005F60B
```
