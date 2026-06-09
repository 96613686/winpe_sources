# SepSddlAddAceToAcl

- ea: `0x140085390`
- end: `0x14008547b`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140085568`

## callees

- `0x140022d40`
- `0x140023040`
- `0x140085390`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x1400853b4`
- `ntoskrnl!RtlLengthSid` at `0x1400853b4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14008545d`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14008545d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400853ee`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400853ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008542e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008542e`

## pseudocode

```c
NTSTATUS __fastcall SepSddlAddAceToAcl(
        const void **a1,
        _DWORD *a2,
        __int64 a3,
        __int64 a4,
        ACCESS_MASK AccessMask,
        int a6,
        PSID Sid)
{
  unsigned __int16 *v7; // rdi
  size_t v10; // rsi
  ULONG v11; // r8d
  int v12; // ebp
  unsigned int v13; // r12d
  struct _ACL *PoolWithTag; // rax
  struct _ACL *v15; // rbx

  v7 = (unsigned __int16 *)*a1;
  v10 = (unsigned int)*a2;
  v11 = RtlLengthSid(Sid) + 8;
  v12 = v11 + v10;
  if ( v11 + (unsigned int)v10 <= v7[1] )
  {
    v15 = (struct _ACL *)v7;
  }
  else
  {
    v13 = a6 * v11 + v10;
    PoolWithTag = (struct _ACL *)ExAllocatePoolWithTag(PagedPool, v13, 0x6C416553u);
    v15 = PoolWithTag;
    if ( !PoolWithTag )
      return -1073741670;
    memset(PoolWithTag, 0, v13);
    memmove(v15, *a1, v10);
    v15->AclSize = v13;
    ExFreePoolWithTag(v7, 0);
    *a1 = v15;
  }
  *a2 = v12;
  return RtlAddAccessAllowedAce(v15, 2u, AccessMask, Sid);
}

```

## disassembly

```asm
0x140085390  push    rbx
0x140085392  push    rbp
0x140085393  push    rsi
0x140085394  push    rdi
0x140085395  push    r12
0x140085397  push    r13
0x140085399  push    r14
0x14008539b  push    r15
0x14008539d  sub     rsp, 28h
0x1400853a1  mov     rdi, [rcx]
0x1400853a4  mov     r15, rcx
0x1400853a7  mov     rcx, [rsp+68h+Sid]; Sid
0x1400853af  mov     r14, rdx
0x1400853b2  mov     esi, [rdx]
0x1400853b4  call    cs:__imp_RtlLengthSid
0x1400853bb  nop     dword ptr [rax+rax+00h]
0x1400853c0  lea     r8d, [rax+8]
0x1400853c4  movzx   eax, word ptr [rdi+2]
0x1400853c8  lea     ebp, [r8+rsi]
0x1400853cc  cmp     ebp, eax
0x1400853ce  jbe     short loc_14008543F
0x1400853d0  imul    r8d, [rsp+68h+arg_28]
0x1400853d9  mov     ecx, 1; PoolType
0x1400853de  lea     r12d, [r8+rsi]
0x1400853e2  mov     r8d, 6C416553h; Tag
0x1400853e8  mov     edx, r12d; NumberOfBytes
0x1400853eb  mov     r13d, r12d
0x1400853ee  call    cs:__imp_ExAllocatePoolWithTag
0x1400853f5  nop     dword ptr [rax+rax+00h]
0x1400853fa  mov     rbx, rax
0x1400853fd  test    rax, rax
0x140085400  jnz     short loc_140085409
0x140085402  mov     eax, 0C000009Ah
0x140085407  jmp     short loc_140085469
0x140085409  mov     r8, r13; Size
0x14008540c  xor     edx, edx; Val
0x14008540e  mov     rcx, rbx; void *
0x140085411  call    memset
0x140085416  mov     rdx, [r15]; Src
0x140085419  mov     r8, rsi; Size
0x14008541c  mov     rcx, rbx; void *
0x14008541f  call    memmove
0x140085424  xor     edx, edx; Tag
0x140085426  mov     [rbx+2], r12w
0x14008542b  mov     rcx, rdi; P
0x14008542e  call    cs:__imp_ExFreePoolWithTag
0x140085435  nop     dword ptr [rax+rax+00h]
0x14008543a  mov     [r15], rbx
0x14008543d  jmp     short loc_140085442
0x14008543f  mov     rbx, rdi
0x140085442  mov     r9, [rsp+68h+Sid]; Sid
0x14008544a  mov     edx, 2; AceRevision
0x14008544f  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x140085457  mov     rcx, rbx; Acl
0x14008545a  mov     [r14], ebp
0x14008545d  call    cs:__imp_RtlAddAccessAllowedAce
0x140085464  nop     dword ptr [rax+rax+00h]
0x140085469  add     rsp, 28h
0x14008546d  pop     r15
0x14008546f  pop     r14
0x140085471  pop     r13
0x140085473  pop     r12
0x140085475  pop     rdi
0x140085476  pop     rsi
0x140085477  pop     rbp
0x140085478  pop     rbx
0x140085479  retn
```
