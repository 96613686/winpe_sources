# SepSddlAddAceToAcl

- ea: `0x140045c50`
- end: `0x140045d3b`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140045e28`

## callees

- `0x140031140`
- `0x140031440`
- `0x140045c50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140045cee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045cee`
- `ntoskrnl!RtlLengthSid` at `0x140045c74`
- `ntoskrnl!RtlLengthSid` at `0x140045c74`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140045d1d`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140045d1d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045cae`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045cae`

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
0x140045c50  push    rbx
0x140045c52  push    rbp
0x140045c53  push    rsi
0x140045c54  push    rdi
0x140045c55  push    r12
0x140045c57  push    r13
0x140045c59  push    r14
0x140045c5b  push    r15
0x140045c5d  sub     rsp, 28h
0x140045c61  mov     rdi, [rcx]
0x140045c64  mov     r15, rcx
0x140045c67  mov     rcx, [rsp+68h+Sid]; Sid
0x140045c6f  mov     r14, rdx
0x140045c72  mov     esi, [rdx]
0x140045c74  call    cs:__imp_RtlLengthSid
0x140045c7b  nop     dword ptr [rax+rax+00h]
0x140045c80  lea     r8d, [rax+8]
0x140045c84  movzx   eax, word ptr [rdi+2]
0x140045c88  lea     ebp, [r8+rsi]
0x140045c8c  cmp     ebp, eax
0x140045c8e  jbe     short loc_140045CFF
0x140045c90  imul    r8d, [rsp+68h+arg_28]
0x140045c99  mov     ecx, 1; PoolType
0x140045c9e  lea     r12d, [r8+rsi]
0x140045ca2  mov     r8d, 6C416553h; Tag
0x140045ca8  mov     edx, r12d; NumberOfBytes
0x140045cab  mov     r13d, r12d
0x140045cae  call    cs:__imp_ExAllocatePoolWithTag
0x140045cb5  nop     dword ptr [rax+rax+00h]
0x140045cba  mov     rbx, rax
0x140045cbd  test    rax, rax
0x140045cc0  jnz     short loc_140045CC9
0x140045cc2  mov     eax, 0C000009Ah
0x140045cc7  jmp     short loc_140045D29
0x140045cc9  mov     r8, r13; Size
0x140045ccc  xor     edx, edx; Val
0x140045cce  mov     rcx, rbx; void *
0x140045cd1  call    memset
0x140045cd6  mov     rdx, [r15]; Src
0x140045cd9  mov     r8, rsi; Size
0x140045cdc  mov     rcx, rbx; void *
0x140045cdf  call    memmove
0x140045ce4  xor     edx, edx; Tag
0x140045ce6  mov     [rbx+2], r12w
0x140045ceb  mov     rcx, rdi; P
0x140045cee  call    cs:__imp_ExFreePoolWithTag
0x140045cf5  nop     dword ptr [rax+rax+00h]
0x140045cfa  mov     [r15], rbx
0x140045cfd  jmp     short loc_140045D02
0x140045cff  mov     rbx, rdi
0x140045d02  mov     r9, [rsp+68h+Sid]; Sid
0x140045d0a  mov     edx, 2; AceRevision
0x140045d0f  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x140045d17  mov     rcx, rbx; Acl
0x140045d1a  mov     [r14], ebp
0x140045d1d  call    cs:__imp_RtlAddAccessAllowedAce
0x140045d24  nop     dword ptr [rax+rax+00h]
0x140045d29  add     rsp, 28h
0x140045d2d  pop     r15
0x140045d2f  pop     r14
0x140045d31  pop     r13
0x140045d33  pop     r12
0x140045d35  pop     rdi
0x140045d36  pop     rsi
0x140045d37  pop     rbp
0x140045d38  pop     rbx
0x140045d39  retn
```
