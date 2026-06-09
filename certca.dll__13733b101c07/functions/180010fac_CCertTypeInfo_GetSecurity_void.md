# CCertTypeInfo::GetSecurity(void * *)

- ea: `0x180010fac`
- end: `0x180011031`
- name: `?GetSecurity@CCertTypeInfo@@QEAAJPEAPEAX@Z`
- size: `133`
- prototype: `__int64 __fastcall(CCertTypeInfo *__hidden this, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d160`

## callees

- `0x180010fac`
- `0x180013a86`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010ffc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010ffc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180010ff0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180010ff0`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180010fd8`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180010fd8`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::GetSecurity(CCertTypeInfo *this, void **a2)
{
  void *v5; // rcx
  SIZE_T SecurityDescriptorLength; // rbp
  HLOCAL v7; // rax
  void *v8; // rsi

  if ( !a2 )
    return 2147500035LL;
  v5 = (void *)*((_QWORD *)this + 17);
  if ( v5 )
  {
    if ( !IsValidSecurityDescriptor(v5) )
      return 2147943738LL;
    SecurityDescriptorLength = GetSecurityDescriptorLength(*((PSECURITY_DESCRIPTOR *)this + 17));
    v7 = LocalAlloc(0, SecurityDescriptorLength);
    v8 = v7;
    if ( !v7 )
      return 2147942414LL;
    memcpy_0(v7, *((const void **)this + 17), SecurityDescriptorLength);
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
0x180010fac  push    rbx
0x180010fae  push    rbp
0x180010faf  push    rsi
0x180010fb0  push    rdi
0x180010fb1  sub     rsp, 28h
0x180010fb5  mov     rbx, rdx
0x180010fb8  mov     rdi, rcx
0x180010fbb  test    rdx, rdx
0x180010fbe  jnz     short loc_180010FC7
0x180010fc0  mov     eax, 80004003h
0x180010fc5  jmp     short loc_180011028
0x180010fc7  mov     rcx, [rcx+88h]; pSecurityDescriptor
0x180010fce  test    rcx, rcx
0x180010fd1  jnz     short loc_180010FD8
0x180010fd3  mov     [rdx], rcx
0x180010fd6  jmp     short loc_180011026
0x180010fd8  call    cs:__imp_IsValidSecurityDescriptor
0x180010fde  test    eax, eax
0x180010fe0  jnz     short loc_180010FE9
0x180010fe2  mov     eax, 8007053Ah
0x180010fe7  jmp     short loc_180011028
0x180010fe9  mov     rcx, [rdi+88h]; pSecurityDescriptor
0x180010ff0  call    cs:__imp_GetSecurityDescriptorLength
0x180010ff6  mov     edx, eax; uBytes
0x180010ff8  xor     ecx, ecx; uFlags
0x180010ffa  mov     ebp, eax
0x180010ffc  call    cs:__imp_LocalAlloc
0x180011002  mov     rsi, rax
0x180011005  test    rax, rax
0x180011008  jnz     short loc_180011011
0x18001100a  mov     eax, 8007000Eh
0x18001100f  jmp     short loc_180011028
0x180011011  mov     rdx, [rdi+88h]; Src
0x180011018  mov     r8, rbp; Size
0x18001101b  mov     rcx, rsi; void *
0x18001101e  call    memcpy_0
0x180011023  mov     [rbx], rsi
0x180011026  xor     eax, eax
0x180011028  add     rsp, 28h
0x18001102c  pop     rdi
0x18001102d  pop     rsi
0x18001102e  pop     rbp
0x18001102f  pop     rbx
0x180011030  retn
```
