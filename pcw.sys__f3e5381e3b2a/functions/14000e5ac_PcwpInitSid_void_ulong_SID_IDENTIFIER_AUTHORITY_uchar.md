# PcwpInitSid(void *,ulong,_SID_IDENTIFIER_AUTHORITY *,uchar,...)

- ea: `0x14000e5ac`
- end: `0x14000e642`
- name: `?PcwpInitSid@@YAJPEAXKPEAU_SID_IDENTIFIER_AUTHORITY@@EZZ`
- size: `150`
- prototype: `__int64(PSID Sid, unsigned int, struct _SID_IDENTIFIER_AUTHORITY *, unsigned __int8, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000e088`

## callees

- `0x14000e5ac`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x14000e5ce`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14000e5ce`
- `ntoskrnl!RtlInitializeSid` at `0x14000e5f0`
- `ntoskrnl!RtlInitializeSid` at `0x14000e5f0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000e61d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000e61d`

## pseudocode

```c
NTSTATUS PcwpInitSid(PSID Sid, ULONG a2, struct _SID_IDENTIFIER_AUTHORITY *a3, UCHAR a4, ...)
{
  NTSTATUS result; // eax
  ULONG v7; // edi
  va_list v8; // rsi
  ULONG v9; // ebx
  PULONG v10; // rax
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  if ( a2 < RtlLengthRequiredSid(a4) )
    return -1073741789;
  result = RtlInitializeSid(Sid, a3, a4);
  if ( result >= 0 )
  {
    v7 = 0;
    va_copy(v8, va);
    if ( a4 )
    {
      do
      {
        v8 += 8;
        v9 = *((_DWORD *)v8 - 2);
        v10 = RtlSubAuthoritySid(Sid, v7++);
        *v10 = v9;
      }
      while ( v7 < a4 );
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000e5ac  mov     [rsp+SubAuthorityCount], r9b
0x14000e5b1  push    rbx
0x14000e5b2  push    rbp
0x14000e5b3  push    rsi
0x14000e5b4  push    rdi
0x14000e5b5  sub     rsp, 38h
0x14000e5b9  mov     rbp, rcx
0x14000e5bc  mov     [rsp+58h+var_38], 0
0x14000e5c5  movzx   ecx, r9b; SubAuthorityCount
0x14000e5c9  mov     rdi, r8
0x14000e5cc  mov     ebx, edx
0x14000e5ce  call    cs:__imp_RtlLengthRequiredSid
0x14000e5d5  nop     dword ptr [rax+rax+00h]
0x14000e5da  cmp     ebx, eax
0x14000e5dc  jnb     short loc_14000E5E5
0x14000e5de  mov     eax, 0C0000023h
0x14000e5e3  jmp     short loc_14000E638
0x14000e5e5  mov     r8b, [rsp+58h+SubAuthorityCount]; SubAuthorityCount
0x14000e5ea  mov     rdx, rdi; IdentifierAuthority
0x14000e5ed  mov     rcx, rbp; Sid
0x14000e5f0  call    cs:__imp_RtlInitializeSid
0x14000e5f7  nop     dword ptr [rax+rax+00h]
0x14000e5fc  test    eax, eax
0x14000e5fe  js      short loc_14000E638
0x14000e600  xor     edi, edi
0x14000e602  lea     rsi, [rsp+58h+arg_20]
0x14000e60a  cmp     [rsp+58h+SubAuthorityCount], dil
0x14000e60f  jbe     short loc_14000E636
0x14000e611  lea     rsi, [rsi+8]
0x14000e615  mov     edx, edi; SubAuthority
0x14000e617  mov     ebx, [rsi-8]
0x14000e61a  mov     rcx, rbp; Sid
0x14000e61d  call    cs:__imp_RtlSubAuthoritySid
0x14000e624  nop     dword ptr [rax+rax+00h]
0x14000e629  inc     edi
0x14000e62b  mov     [rax], ebx
0x14000e62d  movzx   eax, [rsp+58h+SubAuthorityCount]
0x14000e632  cmp     edi, eax
0x14000e634  jb      short loc_14000E611
0x14000e636  xor     eax, eax
0x14000e638  add     rsp, 38h
0x14000e63c  pop     rdi
0x14000e63d  pop     rsi
0x14000e63e  pop     rbp
0x14000e63f  pop     rbx
0x14000e640  retn
```
