# SafeCopyMemory

- ea: `0x140043e18`
- end: `0x140043ed7`
- name: `SafeCopyMemory`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400434bc`

## callees

- `0x140011610`
- `0x140011650`
- `0x1400119c0`
- `0x140043e18`

## import_xrefs

- `ntoskrnl!MmCopyMemory` at `0x140043ea9`
- `ntoskrnl!MmCopyMemory` at `0x140043ea9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140043e68`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140043e68`

## pseudocode

```c
__int64 __fastcall SafeCopyMemory(__int64 a1, unsigned int a2, _QWORD *a3, _DWORD *a4)
{
  unsigned int v4; // ebx
  size_t v5; // rdi
  PVOID PoolWithTag; // rax
  __int64 v11; // [rsp+30h] [rbp-38h] BYREF

  v4 = 0;
  v5 = a2;
  v11 = 0;
  if ( qword_140020008 )
    PoolWithTag = (PVOID)qword_140020008(64, a2, 1682203475);
  else
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, a2, 0x64446353u);
  *a3 = PoolWithTag;
  if ( PoolWithTag )
  {
    memset(PoolWithTag, 0, v5);
    MmCopyMemory(*a3, a1, v5, 2, &v11);
    *a4 = v11;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v4;
}

```

## disassembly

```asm
0x140043e18  push    rbx
0x140043e1a  push    rbp
0x140043e1b  push    rsi
0x140043e1c  push    rdi
0x140043e1d  push    r14
0x140043e1f  sub     rsp, 40h
0x140043e23  mov     rax, cs:__security_cookie
0x140043e2a  xor     rax, rsp
0x140043e2d  mov     [rsp+68h+var_30], rax
0x140043e32  mov     rax, cs:qword_140020008
0x140043e39  xor     ebx, ebx
0x140043e3b  mov     edi, edx
0x140043e3d  mov     rsi, r8
0x140043e40  mov     [rsp+68h+var_38], rbx
0x140043e45  mov     r14, r9
0x140043e48  mov     rbp, rcx
0x140043e4b  mov     r8d, 64446353h; Tag
0x140043e51  mov     edx, edi; NumberOfBytes
0x140043e53  test    rax, rax
0x140043e56  jz      short loc_140043E63
0x140043e58  lea     ecx, [rbx+40h]
0x140043e5b  call    cs:__guard_dispatch_icall_fptr
0x140043e61  jmp     short loc_140043E74
0x140043e63  mov     ecx, 200h; PoolType
0x140043e68  call    cs:__imp_ExAllocatePoolWithTag
0x140043e6f  nop     dword ptr [rax+rax+00h]
0x140043e74  mov     [rsi], rax
0x140043e77  test    rax, rax
0x140043e7a  jnz     short loc_140043E83
0x140043e7c  mov     ebx, 0C000009Ah
0x140043e81  jmp     short loc_140043EBC
0x140043e83  mov     r8, rdi; Size
0x140043e86  xor     edx, edx; Val
0x140043e88  mov     rcx, rax; void *
0x140043e8b  call    memset
0x140043e90  mov     rcx, [rsi]
0x140043e93  lea     rax, [rsp+68h+var_38]
0x140043e98  mov     r9d, 2
0x140043e9e  mov     [rsp+68h+var_48], rax
0x140043ea3  mov     r8, rdi
0x140043ea6  mov     rdx, rbp
0x140043ea9  call    cs:__imp_MmCopyMemory
0x140043eb0  nop     dword ptr [rax+rax+00h]
0x140043eb5  mov     ecx, dword ptr [rsp+68h+var_38]
0x140043eb9  mov     [r14], ecx
0x140043ebc  mov     eax, ebx
0x140043ebe  mov     rcx, [rsp+68h+var_30]
0x140043ec3  xor     rcx, rsp; StackCookie
0x140043ec6  call    __security_check_cookie
0x140043ecb  add     rsp, 40h
0x140043ecf  pop     r14
0x140043ed1  pop     rdi
0x140043ed2  pop     rsi
0x140043ed3  pop     rbp
0x140043ed4  pop     rbx
0x140043ed5  retn
```
