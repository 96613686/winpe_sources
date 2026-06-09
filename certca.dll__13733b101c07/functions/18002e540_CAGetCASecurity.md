# CAGetCASecurity

- ea: `0x18002e540`
- end: `0x18002e5ce`
- name: `CAGetCASecurity`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180013a86`
- `0x18002e540`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e59c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e59c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18002e590`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18002e590`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002e57b`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002e57b`

## pseudocode

```c
__int64 __fastcall CAGetCASecurity(__int64 a1, _QWORD *a2)
{
  void *v5; // rcx
  SIZE_T SecurityDescriptorLength; // rbp
  HLOCAL v7; // rax
  HLOCAL v8; // rsi

  if ( !a1 )
    return 2147500035LL;
  if ( !*(_DWORD *)(a1 + 64) )
    return 2147500033LL;
  if ( !a2 )
    return 2147500035LL;
  v5 = *(void **)(a1 + 56);
  if ( v5 )
  {
    if ( !IsValidSecurityDescriptor(v5) )
      return 2147943738LL;
    SecurityDescriptorLength = GetSecurityDescriptorLength(*(PSECURITY_DESCRIPTOR *)(a1 + 56));
    v7 = LocalAlloc(0, SecurityDescriptorLength);
    v8 = v7;
    if ( !v7 )
      return 2147942414LL;
    memcpy_0(v7, *(const void **)(a1 + 56), SecurityDescriptorLength);
    *a2 = v8;
  }
  else
  {
    *a2 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18002e540  push    rbx
0x18002e542  push    rbp
0x18002e543  push    rsi
0x18002e544  push    rdi
0x18002e545  sub     rsp, 28h
0x18002e549  mov     rdi, rdx
0x18002e54c  mov     rbx, rcx
0x18002e54f  test    rcx, rcx
0x18002e552  jz      short loc_18002E566
0x18002e554  cmp     dword ptr [rcx+40h], 0
0x18002e558  jnz     short loc_18002E561
0x18002e55a  mov     eax, 80004001h
0x18002e55f  jmp     short loc_18002E5C5
0x18002e561  test    rdi, rdi
0x18002e564  jnz     short loc_18002E56D
0x18002e566  mov     eax, 80004003h
0x18002e56b  jmp     short loc_18002E5C5
0x18002e56d  mov     rcx, [rcx+38h]; pSecurityDescriptor
0x18002e571  test    rcx, rcx
0x18002e574  jnz     short loc_18002E57B
0x18002e576  mov     [rdx], rcx
0x18002e579  jmp     short loc_18002E5C3
0x18002e57b  call    cs:__imp_IsValidSecurityDescriptor
0x18002e581  test    eax, eax
0x18002e583  jnz     short loc_18002E58C
0x18002e585  mov     eax, 8007053Ah
0x18002e58a  jmp     short loc_18002E5C5
0x18002e58c  mov     rcx, [rbx+38h]; pSecurityDescriptor
0x18002e590  call    cs:__imp_GetSecurityDescriptorLength
0x18002e596  mov     edx, eax; uBytes
0x18002e598  xor     ecx, ecx; uFlags
0x18002e59a  mov     ebp, eax
0x18002e59c  call    cs:__imp_LocalAlloc
0x18002e5a2  mov     rsi, rax
0x18002e5a5  test    rax, rax
0x18002e5a8  jnz     short loc_18002E5B1
0x18002e5aa  mov     eax, 8007000Eh
0x18002e5af  jmp     short loc_18002E5C5
0x18002e5b1  mov     rdx, [rbx+38h]; Src
0x18002e5b5  mov     r8, rbp; Size
0x18002e5b8  mov     rcx, rsi; void *
0x18002e5bb  call    memcpy_0
0x18002e5c0  mov     [rdi], rsi
0x18002e5c3  xor     eax, eax
0x18002e5c5  add     rsp, 28h
0x18002e5c9  pop     rdi
0x18002e5ca  pop     rsi
0x18002e5cb  pop     rbp
0x18002e5cc  pop     rbx
0x18002e5cd  retn
```
