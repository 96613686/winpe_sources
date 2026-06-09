# MsoCreateAcl(ulong const * const,int,ulong const * const,int,void * * const)

- ea: `0x180122d2c`
- end: `0x180122e08`
- name: `?MsoCreateAcl@@YAPEAU_ACL@@QEBKH0HQEAPEAX@Z`
- size: `220`
- prototype: `struct _ACL *__fastcall(const unsigned int *const, int, const unsigned int *const, int, void **const)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1801229d0`
- `0x180122e08`
- `0x180122ea8`
- `0x180122f4c`

## callees

- `0x180122d2c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180122de5`
- `KERNEL32!LocalFree` at `0x180122de5`
- `KERNEL32!LocalAlloc` at `0x180122d61`
- `KERNEL32!LocalAlloc` at `0x180122d61`
- `ADVAPI32!GetLengthSid` at `0x180122d50`
- `ADVAPI32!GetLengthSid` at `0x180122d50`
- `ADVAPI32!InitializeAcl` at `0x180122d7a`
- `ADVAPI32!InitializeAcl` at `0x180122d7a`
- `ADVAPI32!AddAccessDeniedAce` at `0x180122d9c`
- `ADVAPI32!AddAccessDeniedAce` at `0x180122d9c`
- `ADVAPI32!AddAccessAllowedAce` at `0x180122dca`
- `ADVAPI32!AddAccessAllowedAce` at `0x180122dca`

## pseudocode

```c
struct _ACL *__fastcall MsoCreateAcl(const unsigned int *const a1, __int64 a2, DWORD *a3, __int64 a4, void **const a5)
{
  signed int v6; // edi
  ACL *v7; // rax
  ACL *v8; // rbx
  __int64 i; // rdi

  v6 = GetLengthSid(*a5) + 16;
  v7 = (ACL *)LocalAlloc(0x40u, v6);
  v8 = v7;
  if ( !v7 )
    return 0;
  if ( !InitializeAcl(v7, v6, 2u) )
  {
LABEL_8:
    LocalFree(v8);
    return 0;
  }
  for ( i = 0; i < 1; ++i )
  {
    _mm_lfence();
    if ( !AddAccessAllowedAce(v8, 2u, *a3, a5[i]) )
      goto LABEL_8;
    ++a3;
  }
  return v8;
}

```

## disassembly

```asm
0x180122d2c  mov     rax, rsp
0x180122d2f  mov     [rax+8], rbx
0x180122d33  mov     [rax+10h], rsi
0x180122d37  mov     [rax+18h], rdi
0x180122d3b  mov     [rax+20h], r14
0x180122d3f  push    r15
0x180122d41  sub     rsp, 20h
0x180122d45  mov     r15, [rsp+28h+arg_20]
0x180122d4a  mov     r14, r8
0x180122d4d  mov     rcx, [r15]; pSid
0x180122d50  call    cs:__imp_GetLengthSid
0x180122d56  mov     ecx, 40h ; '@'; uFlags
0x180122d5b  lea     edi, [rax+10h]
0x180122d5e  movsxd  rdx, edi; uBytes
0x180122d61  call    cs:__imp_LocalAlloc
0x180122d67  mov     rbx, rax
0x180122d6a  test    rax, rax
0x180122d6d  jz      short loc_180122DEB
0x180122d6f  mov     r8d, 2; dwAclRevision
0x180122d75  mov     edx, edi; nAclLength
0x180122d77  mov     rcx, rax; pAcl
0x180122d7a  call    cs:__imp_InitializeAcl
0x180122d80  test    eax, eax
0x180122d82  jz      short loc_180122DE2
0x180122d84  xor     edi, edi
0x180122d86  mov     rsi, r15
0x180122d89  test    rdi, rdi
0x180122d8c  jns     short loc_180122DB0
0x180122d8e  mov     r9, [rsi]; pSid
0x180122d91  mov     edx, 2; dwAceRevision
0x180122d96  mov     r8d, [rdi]; AccessMask
0x180122d99  mov     rcx, rbx; pAcl
0x180122d9c  call    cs:__imp_AddAccessDeniedAce
0x180122da2  test    eax, eax
0x180122da4  jz      short loc_180122DE2
0x180122da6  add     rsi, 8
0x180122daa  add     rdi, 4
0x180122dae  jmp     short loc_180122D89
0x180122db0  xor     edi, edi
0x180122db2  cmp     rdi, 1
0x180122db6  jge     short loc_180122DDD
0x180122db8  lfence
0x180122dbb  mov     r9, [r15+rdi*8]; pSid
0x180122dbf  mov     edx, 2; dwAceRevision
0x180122dc4  mov     r8d, [r14]; AccessMask
0x180122dc7  mov     rcx, rbx; pAcl
0x180122dca  call    cs:__imp_AddAccessAllowedAce
0x180122dd0  test    eax, eax
0x180122dd2  jz      short loc_180122DE2
0x180122dd4  inc     rdi
0x180122dd7  add     r14, 4
0x180122ddb  jmp     short loc_180122DB2
0x180122ddd  mov     rax, rbx
0x180122de0  jmp     short loc_180122DED
0x180122de2  mov     rcx, rbx; hMem
0x180122de5  call    cs:__imp_LocalFree
0x180122deb  xor     eax, eax
0x180122ded  mov     rbx, [rsp+28h+arg_0]
0x180122df2  mov     rsi, [rsp+28h+arg_8]
0x180122df7  mov     rdi, [rsp+28h+arg_10]
0x180122dfc  mov     r14, [rsp+28h+arg_18]
0x180122e01  add     rsp, 20h
0x180122e05  pop     r15
0x180122e07  retn
```
