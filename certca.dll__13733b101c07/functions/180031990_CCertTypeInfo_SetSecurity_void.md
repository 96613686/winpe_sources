# CCertTypeInfo::SetSecurity(void *)

- ea: `0x180031990`
- end: `0x180031a23`
- name: `?SetSecurity@CCertTypeInfo@@QEAAJPEAX@Z`
- size: `147`
- prototype: `__int64 __fastcall(CCertTypeInfo *this, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d190`
- `0x180030224`
- `0x180033314`
- `0x180033b78`

## callees

- `0x180013a86`
- `0x180031990`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800319cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800319cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800319fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800319fa`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800319bb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800319bb`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800319ae`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800319ae`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::SetSecurity(CCertTypeInfo *this, void *a2)
{
  __int64 result; // rax
  DWORD SecurityDescriptorLength; // eax
  size_t v6; // rbp
  HLOCAL v7; // rax
  HLOCAL v8; // rsi
  void *v9; // rcx

  if ( !a2 )
    return 2147500035LL;
  if ( !IsValidSecurityDescriptor(a2) )
    return 2147943738LL;
  SecurityDescriptorLength = GetSecurityDescriptorLength(a2);
  if ( !SecurityDescriptorLength )
    return 2147943738LL;
  v6 = SecurityDescriptorLength;
  v7 = LocalAlloc(0, SecurityDescriptorLength);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  memcpy_0(v7, a2, v6);
  v9 = (void *)*((_QWORD *)this + 17);
  if ( v9 )
    LocalFree(v9);
  *((_QWORD *)this + 17) = v8;
  result = 0;
  *((_DWORD *)this + 46) = 1;
  return result;
}

```

## disassembly

```asm
0x180031990  push    rbx
0x180031992  push    rbp
0x180031993  push    rsi
0x180031994  push    rdi
0x180031995  sub     rsp, 28h
0x180031999  mov     rbx, rdx
0x18003199c  mov     rdi, rcx
0x18003199f  test    rdx, rdx
0x1800319a2  jnz     short loc_1800319AB
0x1800319a4  mov     eax, 80004003h
0x1800319a9  jmp     short loc_180031A1A
0x1800319ab  mov     rcx, rbx; pSecurityDescriptor
0x1800319ae  call    cs:__imp_IsValidSecurityDescriptor
0x1800319b4  test    eax, eax
0x1800319b6  jz      short loc_180031A15
0x1800319b8  mov     rcx, rbx; pSecurityDescriptor
0x1800319bb  call    cs:__imp_GetSecurityDescriptorLength
0x1800319c1  test    eax, eax
0x1800319c3  jz      short loc_180031A15
0x1800319c5  mov     edx, eax; uBytes
0x1800319c7  xor     ecx, ecx; uFlags
0x1800319c9  mov     ebp, eax
0x1800319cb  call    cs:__imp_LocalAlloc
0x1800319d1  mov     rsi, rax
0x1800319d4  test    rax, rax
0x1800319d7  jnz     short loc_1800319E0
0x1800319d9  mov     eax, 8007000Eh
0x1800319de  jmp     short loc_180031A1A
0x1800319e0  mov     r8, rbp; Size
0x1800319e3  mov     rdx, rbx; Src
0x1800319e6  mov     rcx, rsi; void *
0x1800319e9  call    memcpy_0
0x1800319ee  mov     rcx, [rdi+88h]; hMem
0x1800319f5  test    rcx, rcx
0x1800319f8  jz      short loc_180031A00
0x1800319fa  call    cs:__imp_LocalFree
0x180031a00  mov     [rdi+88h], rsi
0x180031a07  xor     eax, eax
0x180031a09  mov     dword ptr [rdi+0B8h], 1
0x180031a13  jmp     short loc_180031A1A
0x180031a15  mov     eax, 8007053Ah
0x180031a1a  add     rsp, 28h
0x180031a1e  pop     rdi
0x180031a1f  pop     rsi
0x180031a20  pop     rbp
0x180031a21  pop     rbx
0x180031a22  retn
```
