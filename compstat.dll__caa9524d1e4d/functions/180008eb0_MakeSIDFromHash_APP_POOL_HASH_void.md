# MakeSIDFromHash(APP_POOL_HASH *,void * *)

- ea: `0x180008eb0`
- end: `0x180008fbb`
- name: `?MakeSIDFromHash@@YAJPEAUAPP_POOL_HASH@@PEAPEAX@Z`
- size: `267`
- prototype: `__int64 __fastcall(struct APP_POOL_HASH *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180008e54`

## callees

- `0x180005f90`
- `0x180008eb0`

## import_xrefs

- `ntdll!RtlLengthRequiredSid` at `0x180008ee9`
- `ntdll!RtlLengthRequiredSid` at `0x180008ee9`
- `ntdll!RtlInitializeSid` at `0x180008f1e`
- `ntdll!RtlInitializeSid` at `0x180008f1e`
- `ntdll!RtlSubAuthoritySid` at `0x180008f29`
- `ntdll!RtlSubAuthoritySid` at `0x180008f3f`
- `ntdll!RtlSubAuthoritySid` at `0x180008f52`
- `ntdll!RtlSubAuthoritySid` at `0x180008f65`
- `ntdll!RtlSubAuthoritySid` at `0x180008f78`
- `ntdll!RtlSubAuthoritySid` at `0x180008f8b`
- `ntdll!RtlSubAuthoritySid` at `0x180008f29`
- `ntdll!RtlSubAuthoritySid` at `0x180008f3f`
- `ntdll!RtlSubAuthoritySid` at `0x180008f52`
- `ntdll!RtlSubAuthoritySid` at `0x180008f65`
- `ntdll!RtlSubAuthoritySid` at `0x180008f78`
- `ntdll!RtlSubAuthoritySid` at `0x180008f8b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008ef6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008ef6`

## pseudocode

```c
__int64 __fastcall MakeSIDFromHash(ULONG *a1, void **a2)
{
  ULONG v4; // eax
  HLOCAL v5; // rax
  void *v6; // rdi
  __int64 result; // rax
  ULONG v8; // ebx
  ULONG v9; // ebx
  ULONG v10; // ebx
  ULONG v11; // ebx
  ULONG v12; // ebx
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-18h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v4 = RtlLengthRequiredSid(6u);
  v5 = LocalAlloc(0x40u, v4);
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  RtlInitializeSid(v5, &IdentifierAuthority, 6u);
  *RtlSubAuthoritySid(v6, 0) = 82;
  v8 = *a1;
  *RtlSubAuthoritySid(v6, 1u) = v8;
  v9 = a1[1];
  *RtlSubAuthoritySid(v6, 2u) = v9;
  v10 = a1[2];
  *RtlSubAuthoritySid(v6, 3u) = v10;
  v11 = a1[3];
  *RtlSubAuthoritySid(v6, 4u) = v11;
  v12 = a1[4];
  *RtlSubAuthoritySid(v6, 5u) = v12;
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180008eb0  mov     [rsp+arg_10], rsi
0x180008eb5  mov     [rsp+arg_18], rdi
0x180008eba  push    r14
0x180008ebc  sub     rsp, 30h
0x180008ec0  mov     rax, cs:__security_cookie
0x180008ec7  xor     rax, rsp
0x180008eca  mov     [rsp+38h+var_10], rax
0x180008ecf  mov     rsi, rcx
0x180008ed2  mov     dword ptr [rsp+38h+IdentifierAuthority.Value], 0
0x180008eda  mov     ecx, 6; SubAuthorityCount
0x180008edf  mov     word ptr [rsp+38h+IdentifierAuthority.Value+4], 500h
0x180008ee6  mov     r14, rdx
0x180008ee9  call    cs:__imp_RtlLengthRequiredSid
0x180008eef  mov     edx, eax; uBytes
0x180008ef1  mov     ecx, 40h ; '@'; uFlags
0x180008ef6  call    cs:__imp_LocalAlloc
0x180008efc  mov     rdi, rax
0x180008eff  test    rax, rax
0x180008f02  jnz     short loc_180008F0E
0x180008f04  mov     eax, 8007000Eh
0x180008f09  jmp     loc_180008F9D
0x180008f0e  mov     r8b, 6; SubAuthorityCount
0x180008f11  mov     [rsp+38h+arg_0], rbx
0x180008f16  lea     rdx, [rsp+38h+IdentifierAuthority]; IdentifierAuthority
0x180008f1b  mov     rcx, rdi; Sid
0x180008f1e  call    cs:__imp_RtlInitializeSid
0x180008f24  xor     edx, edx; SubAuthority
0x180008f26  mov     rcx, rdi; Sid
0x180008f29  call    cs:__imp_RtlSubAuthoritySid
0x180008f2f  mov     edx, 1; SubAuthority
0x180008f34  mov     rcx, rdi; Sid
0x180008f37  mov     dword ptr [rax], 52h ; 'R'
0x180008f3d  mov     ebx, [rsi]
0x180008f3f  call    cs:__imp_RtlSubAuthoritySid
0x180008f45  mov     edx, 2; SubAuthority
0x180008f4a  mov     rcx, rdi; Sid
0x180008f4d  mov     [rax], ebx
0x180008f4f  mov     ebx, [rsi+4]
0x180008f52  call    cs:__imp_RtlSubAuthoritySid
0x180008f58  mov     edx, 3; SubAuthority
0x180008f5d  mov     rcx, rdi; Sid
0x180008f60  mov     [rax], ebx
0x180008f62  mov     ebx, [rsi+8]
0x180008f65  call    cs:__imp_RtlSubAuthoritySid
0x180008f6b  mov     edx, 4; SubAuthority
0x180008f70  mov     rcx, rdi; Sid
0x180008f73  mov     [rax], ebx
0x180008f75  mov     ebx, [rsi+0Ch]
0x180008f78  call    cs:__imp_RtlSubAuthoritySid
0x180008f7e  mov     edx, 5; SubAuthority
0x180008f83  mov     rcx, rdi; Sid
0x180008f86  mov     [rax], ebx
0x180008f88  mov     ebx, [rsi+10h]
0x180008f8b  call    cs:__imp_RtlSubAuthoritySid
0x180008f91  mov     [rax], ebx
0x180008f93  xor     eax, eax
0x180008f95  mov     rbx, [rsp+38h+arg_0]
0x180008f9a  mov     [r14], rdi
0x180008f9d  mov     rcx, [rsp+38h+var_10]
0x180008fa2  xor     rcx, rsp; StackCookie
0x180008fa5  call    __security_check_cookie
0x180008faa  mov     rsi, [rsp+38h+arg_10]
0x180008faf  mov     rdi, [rsp+38h+arg_18]
0x180008fb4  add     rsp, 30h
0x180008fb8  pop     r14
0x180008fba  retn
```
