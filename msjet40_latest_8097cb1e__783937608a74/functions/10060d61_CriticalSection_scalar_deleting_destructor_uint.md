# CriticalSection::`scalar deleting destructor'(uint)

- ea: `0x10060d61`
- end: `0x10060db2`
- name: `??_GCriticalSection@@QAEPAXI@Z`
- size: `81`
- prototype: `void *__thiscall(CriticalSection *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x10060b19`
- `0x10060dbd`

## callees

- `0x10123110`
- `0x10123c92`
- `0x10124048`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10060d90`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10060d90`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__thiscall CriticalSection::`scalar deleting destructor'(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned int a2)
{
  DeleteCriticalSection(this);
  operator delete(this, 0x18u);
  return this;
}

```

## disassembly

```asm
0x10060d61  mov     edi, edi
0x10060d63  push    ebp
0x10060d64  mov     ebp, esp
0x10060d66  push    0FFFFFFFFh
0x10060d68  push    offset ??_GCriticalSection@@QAEPAXI@Z_SEH
0x10060d6d  mov     eax, large fs:0
0x10060d73  push    eax
0x10060d74  push    esi
0x10060d75  mov     eax, ___security_cookie
0x10060d7a  xor     eax, ebp
0x10060d7c  push    eax
0x10060d7d  lea     eax, [ebp+var_C]
0x10060d80  mov     large fs:0, eax
0x10060d86  mov     esi, ecx
0x10060d88  push    esi; lpCriticalSection
0x10060d89  mov     [ebp+var_4], 0
0x10060d90  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10060d96  push    18h; unsigned int
0x10060d98  push    esi; Block
0x10060d99  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10060d9e  pop     ecx
0x10060d9f  pop     ecx
0x10060da0  mov     eax, esi
0x10060da2  mov     ecx, [ebp+var_C]
0x10060da5  mov     large fs:0, ecx
0x10060dac  pop     ecx
0x10060dad  pop     esi
0x10060dae  leave
0x10060daf  retn    4
0x10124060  jmp     ds:__imp____std_terminate
0x10124c23  nop
0x10124c24  nop
0x10124c25  mov     edx, [esp-4+arg_4]
0x10124c29  lea     eax, [edx+0Ch]
0x10124c2c  mov     ecx, [edx-8]
0x10124c2f  xor     ecx, eax; StackCookie
0x10124c31  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124c36  mov     eax, offset stru_10127A7C
0x10124c3b  jmp     ___CxxFrameHandler3
```
