# RTSecurityContextBase::AllocateAndCopyUserCert(void *,ulong)

- ea: `0x1800164a8`
- end: `0x1800164f8`
- name: `?AllocateAndCopyUserCert@RTSecurityContextBase@@IEAAXPEAXK@Z`
- size: `80`
- prototype: `void(RTSecurityContextBase *__hidden this, void *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016f9c`
- `0x180017728`

## callees

- `0x1800164a8`
- `0x180021010`
- `0x180023c4e`

## pseudocode

```c
void __fastcall RTSecurityContextBase::AllocateAndCopyUserCert(RTSecurityContextBase *this, void *a2, unsigned int a3)
{
  void *v6; // rax

  *((_DWORD *)this + 12) = a3;
  if ( a2 )
  {
    if ( a3 )
    {
      v6 = MmAllocate(a3);
      *((_QWORD *)this + 2) = v6;
      memcpy_0(v6, a2, a3);
    }
  }
}

```

## disassembly

```asm
0x1800164a8  mov     [rsp+arg_0], rbx
0x1800164ad  mov     [rsp+arg_8], rsi
0x1800164b2  push    rdi
0x1800164b3  sub     rsp, 20h
0x1800164b7  mov     [rcx+30h], r8d
0x1800164bb  mov     rdi, rdx
0x1800164be  mov     rsi, rcx
0x1800164c1  test    rdx, rdx
0x1800164c4  jz      short loc_1800164E8
0x1800164c6  test    r8d, r8d
0x1800164c9  jz      short loc_1800164E8
0x1800164cb  mov     ecx, r8d; unsigned __int64
0x1800164ce  mov     ebx, r8d
0x1800164d1  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800164d6  mov     r8d, ebx; Size
0x1800164d9  mov     [rsi+10h], rax
0x1800164dd  mov     rdx, rdi; Src
0x1800164e0  mov     rcx, rax; void *
0x1800164e3  call    memcpy_0
0x1800164e8  mov     rbx, [rsp+28h+arg_0]
0x1800164ed  mov     rsi, [rsp+28h+arg_8]
0x1800164f2  add     rsp, 20h
0x1800164f6  pop     rdi
0x1800164f7  retn
```
