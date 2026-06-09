# CClfsContainer::IsEqualSecurityDescriptor(void *,void *)

- ea: `0x14000fe74`
- end: `0x14000fee1`
- name: `?IsEqualSecurityDescriptor@CClfsContainer@@SAEPEAX0@Z`
- size: `109`
- prototype: `static unsigned __int8(void *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140034a20`

## callees

- `0x14000fe74`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000feba`
- `ntoskrnl!RtlCompareMemory` at `0x14000feba`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000fe90`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000fea1`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000fe90`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000fea1`

## pseudocode

```c
bool __fastcall CClfsContainer::IsEqualSecurityDescriptor(void *a1, void *a2)
{
  PSECURITY_DESCRIPTOR v2; // rsi
  __int64 v4; // rbx

  v2 = CClfsContainer::m_psdNoSecurity;
  v4 = RtlLengthSecurityDescriptor(CClfsContainer::m_psdNoSecurity);
  return RtlLengthSecurityDescriptor(a2) == (_DWORD)v4 && RtlCompareMemory(v2, a2, (unsigned int)v4) == v4;
}

```

## disassembly

```asm
0x14000fe74  mov     [rsp+arg_0], rbx
0x14000fe79  mov     [rsp+arg_8], rsi
0x14000fe7e  push    rdi
0x14000fe7f  sub     rsp, 20h
0x14000fe83  mov     rsi, cs:?m_psdNoSecurity@CClfsContainer@@0PEAXEA; void * CClfsContainer::m_psdNoSecurity
0x14000fe8a  mov     rdi, rdx
0x14000fe8d  mov     rcx, rsi; SecurityDescriptor
0x14000fe90  call    cs:__imp_RtlLengthSecurityDescriptor
0x14000fe97  nop     dword ptr [rax+rax+00h]
0x14000fe9c  mov     rcx, rdi; SecurityDescriptor
0x14000fe9f  mov     ebx, eax
0x14000fea1  call    cs:__imp_RtlLengthSecurityDescriptor
0x14000fea8  nop     dword ptr [rax+rax+00h]
0x14000fead  cmp     eax, ebx
0x14000feaf  jnz     short loc_14000FECE
0x14000feb1  mov     r8d, ebx; Length
0x14000feb4  mov     rdx, rdi; Source2
0x14000feb7  mov     rcx, rsi; Source1
0x14000feba  call    cs:__imp_RtlCompareMemory
0x14000fec1  nop     dword ptr [rax+rax+00h]
0x14000fec6  cmp     rax, rbx
0x14000fec9  setz    al
0x14000fecc  jmp     short loc_14000FED0
0x14000fece  xor     al, al
0x14000fed0  mov     rbx, [rsp+28h+arg_0]
0x14000fed5  mov     rsi, [rsp+28h+arg_8]
0x14000feda  add     rsp, 20h
0x14000fede  pop     rdi
0x14000fedf  retn
```
