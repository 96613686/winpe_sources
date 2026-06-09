# CAdminAclCache::_MoveFirst(ulong)

- ea: `0x18000c0d0`
- end: `0x18000c135`
- name: `?_MoveFirst@CAdminAclCache@@AEAAJK@Z`
- size: `101`
- prototype: `__int64 __fastcall(CAdminAclCache *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000aefc`
- `0x18000b1e4`

## callees

- `0x18000c0d0`
- `0x18000fb12`

## pseudocode

```c
__int64 __fastcall CAdminAclCache::_MoveFirst(CAdminAclCache *this, unsigned int a2)
{
  unsigned int v2; // edi
  __int64 v3; // rbx

  if ( a2 < dword_1800160F4 )
  {
    v2 = 0;
    if ( !a2 )
      return v2;
    if ( a2 < 0xFF )
    {
      v3 = qword_1800160F8[a2];
      memmove_0(qword_180016100, qword_1800160F8, 8LL * a2);
      qword_1800160F8[0] = v3;
      return v2;
    }
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x18000c0d0  mov     [rsp+arg_0], rbx
0x18000c0d5  push    rdi
0x18000c0d6  sub     rsp, 20h
0x18000c0da  mov     eax, cs:dword_1800160F4
0x18000c0e0  cmp     edx, eax
0x18000c0e2  jb      short loc_18000C0EB
0x18000c0e4  mov     edi, 80070057h
0x18000c0e9  jmp     short loc_18000C128
0x18000c0eb  xor     edi, edi
0x18000c0ed  test    edx, edx
0x18000c0ef  jz      short loc_18000C128
0x18000c0f1  cmp     edx, 0FFh
0x18000c0f7  jnb     short loc_18000C0E4
0x18000c0f9  mov     ecx, edx
0x18000c0fb  lea     rbx, qword_1800160F8
0x18000c102  lea     rdx, qword_1800160F8; Src
0x18000c109  lea     r8, ds:0[rcx*8]; Size
0x18000c111  mov     rbx, [r8+rbx]
0x18000c115  lea     rcx, qword_180016100; void *
0x18000c11c  call    memmove_0
0x18000c121  mov     cs:qword_1800160F8, rbx
0x18000c128  mov     rbx, [rsp+28h+arg_0]
0x18000c12d  mov     eax, edi
0x18000c12f  add     rsp, 20h
0x18000c133  pop     rdi
0x18000c134  retn
```
