# CASetCASecurity

- ea: `0x18002eb50`
- end: `0x18002ebe1`
- name: `CASetCASecurity`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180013a86`
- `0x18002eb50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002eba0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002eba0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ebcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ebcc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18002eb94`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18002eb94`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002eb80`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002eb80`

## pseudocode

```c
__int64 __fastcall CASetCASecurity(__int64 a1, void *a2)
{
  SIZE_T SecurityDescriptorLength; // rbp
  HLOCAL v6; // rax
  HLOCAL v7; // rsi
  void *v8; // rcx

  if ( !a1 )
    return 2147500035LL;
  if ( !*(_DWORD *)(a1 + 64) )
    return 2147500033LL;
  if ( !a2 )
    return 2147500035LL;
  if ( !IsValidSecurityDescriptor(a2) )
    return 2147943738LL;
  SecurityDescriptorLength = GetSecurityDescriptorLength(a2);
  v6 = LocalAlloc(0, SecurityDescriptorLength);
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  memcpy_0(v6, a2, SecurityDescriptorLength);
  v8 = *(void **)(a1 + 56);
  if ( v8 )
    LocalFree(v8);
  *(_QWORD *)(a1 + 56) = v7;
  return 0;
}

```

## disassembly

```asm
0x18002eb50  push    rbx
0x18002eb52  push    rbp
0x18002eb53  push    rsi
0x18002eb54  push    rdi
0x18002eb55  sub     rsp, 28h
0x18002eb59  mov     rdi, rdx
0x18002eb5c  mov     rbx, rcx
0x18002eb5f  test    rcx, rcx
0x18002eb62  jz      short loc_18002EB76
0x18002eb64  cmp     dword ptr [rcx+40h], 0
0x18002eb68  jnz     short loc_18002EB71
0x18002eb6a  mov     eax, 80004001h
0x18002eb6f  jmp     short loc_18002EBD8
0x18002eb71  test    rdi, rdi
0x18002eb74  jnz     short loc_18002EB7D
0x18002eb76  mov     eax, 80004003h
0x18002eb7b  jmp     short loc_18002EBD8
0x18002eb7d  mov     rcx, rdi; pSecurityDescriptor
0x18002eb80  call    cs:__imp_IsValidSecurityDescriptor
0x18002eb86  test    eax, eax
0x18002eb88  jnz     short loc_18002EB91
0x18002eb8a  mov     eax, 8007053Ah
0x18002eb8f  jmp     short loc_18002EBD8
0x18002eb91  mov     rcx, rdi; pSecurityDescriptor
0x18002eb94  call    cs:__imp_GetSecurityDescriptorLength
0x18002eb9a  mov     edx, eax; uBytes
0x18002eb9c  xor     ecx, ecx; uFlags
0x18002eb9e  mov     ebp, eax
0x18002eba0  call    cs:__imp_LocalAlloc
0x18002eba6  mov     rsi, rax
0x18002eba9  test    rax, rax
0x18002ebac  jnz     short loc_18002EBB5
0x18002ebae  mov     eax, 8007000Eh
0x18002ebb3  jmp     short loc_18002EBD8
0x18002ebb5  mov     r8, rbp; Size
0x18002ebb8  mov     rdx, rdi; Src
0x18002ebbb  mov     rcx, rsi; void *
0x18002ebbe  call    memcpy_0
0x18002ebc3  mov     rcx, [rbx+38h]; hMem
0x18002ebc7  test    rcx, rcx
0x18002ebca  jz      short loc_18002EBD2
0x18002ebcc  call    cs:__imp_LocalFree
0x18002ebd2  mov     [rbx+38h], rsi
0x18002ebd6  xor     eax, eax
0x18002ebd8  add     rsp, 28h
0x18002ebdc  pop     rdi
0x18002ebdd  pop     rsi
0x18002ebde  pop     rbp
0x18002ebdf  pop     rbx
0x18002ebe0  retn
```
