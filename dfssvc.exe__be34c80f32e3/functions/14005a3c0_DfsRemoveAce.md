# DfsRemoveAce

- ea: `0x14005a3c0`
- end: `0x14005a526`
- name: `DfsRemoveAce`
- size: `358`
- prototype: `__int64 __fastcall(LDAP *ld, PWSTR dn)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005a52c`

## callees

- `0x140001526`
- `0x140001532`
- `0x14005a3c0`
- `0x14005a6cc`
- `0x14005a780`
- `0x14005ce3a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a4ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a4ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005a4e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005a4e0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14005a4b2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14005a4b2`

## pseudocode

```c
__int64 __fastcall DfsRemoveAce(LDAP *ld, PWSTR dn, WCHAR *a3, __int64 a4)
{
  WCHAR *v5; // r12
  LDAP *v6; // r13
  __int64 v7; // rax
  size_t v8; // rbx
  WCHAR *v9; // rax
  WCHAR *v10; // rdi
  WCHAR v11; // ax
  char v12; // bl
  unsigned int v13; // ebp
  __int64 v14; // r15
  WCHAR *v15; // rsi
  __int64 v16; // rax
  DWORD LastError; // ebx
  ULONG SecurityDescriptorSize; // [rsp+30h] [rbp-48h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-40h] BYREF

  SecurityDescriptor = 0;
  v5 = dn;
  SecurityDescriptorSize = 0;
  v6 = ld;
  v7 = -1;
  do
    ++v7;
  while ( a3[v7] );
  v8 = (unsigned int)(2 * v7 + 2);
  v9 = (WCHAR *)malloc_0(v8);
  v10 = v9;
  if ( v9 )
  {
    memset_0(v9, 0, (unsigned int)v8);
    v11 = *a3;
    v12 = 1;
    v13 = 0;
    LODWORD(v14) = 0;
    if ( *a3 )
    {
      v15 = a3;
      do
      {
        if ( v11 == 40 && (unsigned __int8)DfsSidInAce(v15, a4) == 1 )
        {
          v12 = 0;
        }
        else if ( *v15 != 41 || v12 )
        {
          if ( v12 == 1 )
          {
            v16 = v13++;
            v10[v16] = *v15;
          }
        }
        else
        {
          v12 = 1;
        }
        v14 = (unsigned int)(v14 + 1);
        v15 = &a3[v14];
        v11 = *v15;
      }
      while ( *v15 );
      v5 = dn;
      v6 = ld;
    }
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v10, 1u, &SecurityDescriptor, &SecurityDescriptorSize) )
    {
      LastError = DfsStampSD(v5, v6);
      LocalFree(SecurityDescriptor);
    }
    else
    {
      LastError = GetLastError();
    }
    free_0(v10);
  }
  else
  {
    return 14;
  }
  return LastError;
}

```

## disassembly

```asm
0x14005a3c0  mov     rax, rsp
0x14005a3c3  mov     [rax+18h], rbx
0x14005a3c7  mov     [rax+20h], r9
0x14005a3cb  mov     [rax+10h], rdx
0x14005a3cf  mov     [rax+8], rcx
0x14005a3d3  push    rbp
0x14005a3d4  push    rsi
0x14005a3d5  push    rdi
0x14005a3d6  push    r12
0x14005a3d8  push    r13
0x14005a3da  push    r14
0x14005a3dc  push    r15
0x14005a3de  sub     rsp, 40h
0x14005a3e2  xor     esi, esi
0x14005a3e4  mov     r14, r8
0x14005a3e7  mov     [rax-40h], rsi
0x14005a3eb  mov     r12, rdx
0x14005a3ee  mov     [rax-48h], esi
0x14005a3f1  mov     r13, rcx
0x14005a3f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x14005a3f8  inc     rax
0x14005a3fb  cmp     [r8+rax*2], si
0x14005a400  jnz     short loc_14005A3F8
0x14005a402  lea     eax, ds:2[rax*2]
0x14005a409  mov     ecx, eax; Size
0x14005a40b  mov     ebx, eax
0x14005a40d  call    malloc_0
0x14005a412  mov     rdi, rax
0x14005a415  test    rax, rax
0x14005a418  jz      loc_14005A506
0x14005a41e  mov     r8d, ebx; Size
0x14005a421  xor     edx, edx; Val
0x14005a423  mov     rcx, rax; void *
0x14005a426  call    memset_0
0x14005a42b  movzx   eax, word ptr [r14]
0x14005a42f  mov     bl, 1
0x14005a431  mov     ebp, esi
0x14005a433  mov     r15d, esi
0x14005a436  test    ax, ax
0x14005a439  jz      short loc_14005A4A0
0x14005a43b  mov     r12, [rsp+78h+arg_18]
0x14005a443  mov     rsi, r14
0x14005a446  xor     r13d, r13d
0x14005a449  cmp     ax, 28h ; '('
0x14005a44d  jnz     short loc_14005A463
0x14005a44f  mov     rdx, r12
0x14005a452  mov     rcx, rsi
0x14005a455  call    DfsSidInAce
0x14005a45a  cmp     al, 1
0x14005a45c  jnz     short loc_14005A463
0x14005a45e  mov     bl, r13b
0x14005a461  jmp     short loc_14005A481
0x14005a463  movzx   ecx, word ptr [rsi]
0x14005a466  cmp     cx, 29h ; ')'
0x14005a46a  jnz     short loc_14005A474
0x14005a46c  test    bl, bl
0x14005a46e  jnz     short loc_14005A474
0x14005a470  mov     bl, 1
0x14005a472  jmp     short loc_14005A481
0x14005a474  cmp     bl, 1
0x14005a477  jnz     short loc_14005A481
0x14005a479  mov     eax, ebp
0x14005a47b  inc     ebp
0x14005a47d  mov     [rdi+rax*2], cx
0x14005a481  inc     r15d
0x14005a484  lea     rsi, [r14+r15*2]
0x14005a488  movzx   eax, word ptr [rsi]
0x14005a48b  test    ax, ax
0x14005a48e  jnz     short loc_14005A449
0x14005a490  mov     r12, [rsp+78h+arg_8]
0x14005a498  mov     r13, [rsp+78h+arg_0]
0x14005a4a0  lea     r9, [rsp+78h+SecurityDescriptorSize]; SecurityDescriptorSize
0x14005a4a5  mov     edx, 1; StringSDRevision
0x14005a4aa  lea     r8, [rsp+78h+SecurityDescriptor]; SecurityDescriptor
0x14005a4af  mov     rcx, rdi; StringSecurityDescriptor
0x14005a4b2  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14005a4b9  nop     dword ptr [rax+rax+00h]
0x14005a4be  cmp     eax, 1
0x14005a4c1  jnz     short loc_14005A4EE
0x14005a4c3  mov     r9, [rsp+78h+SecurityDescriptor]
0x14005a4c8  mov     rcx, r12; dn
0x14005a4cb  mov     edx, [rsp+78h+SecurityDescriptorSize]
0x14005a4cf  mov     [rsp+78h+ld], r13; ld
0x14005a4d4  call    DfsStampSD
0x14005a4d9  mov     rcx, [rsp+78h+SecurityDescriptor]; hMem
0x14005a4de  mov     ebx, eax
0x14005a4e0  call    cs:__imp_LocalFree
0x14005a4e7  nop     dword ptr [rax+rax+00h]
0x14005a4ec  jmp     short loc_14005A4FC
0x14005a4ee  call    cs:__imp_GetLastError
0x14005a4f5  nop     dword ptr [rax+rax+00h]
0x14005a4fa  mov     ebx, eax
0x14005a4fc  mov     rcx, rdi; Block
0x14005a4ff  call    free_0
0x14005a504  jmp     short loc_14005A50B
0x14005a506  mov     ebx, 0Eh
0x14005a50b  mov     eax, ebx
0x14005a50d  mov     rbx, [rsp+78h+arg_10]
0x14005a515  add     rsp, 40h
0x14005a519  pop     r15
0x14005a51b  pop     r14
0x14005a51d  pop     r13
0x14005a51f  pop     r12
0x14005a521  pop     rdi
0x14005a522  pop     rsi
0x14005a523  pop     rbp
0x14005a524  retn
```
