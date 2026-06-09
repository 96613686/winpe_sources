# CriticalSection::`scalar deleting destructor'(uint)

- ea: `0x10060bcd`
- end: `0x10060c1e`
- name: `??_GCriticalSection@@QAEPAXI@Z`
- size: `81`
- prototype: `void *__thiscall(CriticalSection *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x10060989`
- `0x10060c29`

## callees

- `0x10122f60`
- `0x10123ae2`
- `0x10123e98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10060bfc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10060bfc`

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
0x10060bcd  mov     edi, edi
0x10060bcf  push    ebp
0x10060bd0  mov     ebp, esp
0x10060bd2  push    0FFFFFFFFh
0x10060bd4  push    offset ??_GCriticalSection@@QAEPAXI@Z_SEH
0x10060bd9  mov     eax, large fs:0
0x10060bdf  push    eax
0x10060be0  push    esi
0x10060be1  mov     eax, ___security_cookie
0x10060be6  xor     eax, ebp
0x10060be8  push    eax
0x10060be9  lea     eax, [ebp+var_C]
0x10060bec  mov     large fs:0, eax
0x10060bf2  mov     esi, ecx
0x10060bf4  push    esi; lpCriticalSection
0x10060bf5  mov     [ebp+var_4], 0
0x10060bfc  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10060c02  push    18h; unsigned int
0x10060c04  push    esi; Block
0x10060c05  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10060c0a  pop     ecx
0x10060c0b  pop     ecx
0x10060c0c  mov     eax, esi
0x10060c0e  mov     ecx, [ebp+var_C]
0x10060c11  mov     large fs:0, ecx
0x10060c18  pop     ecx
0x10060c19  pop     esi
0x10060c1a  leave
0x10060c1b  retn    4
0x10123eb0  jmp     ds:__imp____std_terminate
0x10124a73  nop
0x10124a74  nop
0x10124a75  mov     edx, [esp-4+arg_4]
0x10124a79  lea     eax, [edx+0Ch]
0x10124a7c  mov     ecx, [edx-8]
0x10124a7f  xor     ecx, eax; StackCookie
0x10124a81  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124a86  mov     eax, offset stru_101278CC
0x10124a8b  jmp     ___CxxFrameHandler3
```
