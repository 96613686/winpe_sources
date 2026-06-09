# BiOpenEffectiveToken

- ea: `0x180035268`
- end: `0x1800352f0`
- name: `BiOpenEffectiveToken`
- size: `136`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003514c`

## callees

- `0x180035268`

## import_xrefs

- `ntdll!NtOpenProcessTokenEx` at `0x1800352dd`
- `ntdll!NtOpenProcessTokenEx` at `0x1800352dd`
- `ntdll!NtOpenThreadTokenEx` at `0x180035297`
- `ntdll!NtOpenThreadTokenEx` at `0x1800352bd`
- `ntdll!NtOpenThreadTokenEx` at `0x180035297`
- `ntdll!NtOpenThreadTokenEx` at `0x1800352bd`

## pseudocode

```c
int __fastcall BiOpenEffectiveToken(PHANDLE TokenHandle)
{
  int result; // eax

  if ( !NtCurrentTeb()->IsImpersonating )
    return NtOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x28u, 0x200u, TokenHandle);
  result = NtOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 1u, 0x200u, TokenHandle);
  if ( result < 0 )
    return NtOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 0, 0x200u, TokenHandle);
  return result;
}

```

## disassembly

```asm
0x180035268  push    rbx
0x18003526a  sub     rsp, 30h
0x18003526e  mov     eax, gs:179Ch
0x180035276  mov     rbx, rcx
0x180035279  mov     edx, 28h ; '('; DesiredAccess
0x18003527e  test    eax, eax
0x180035280  jz      short loc_1800352D0
0x180035282  mov     [rsp+38h+TokenHandle], rcx; TokenHandle
0x180035287  mov     r9d, 200h; HandleAttributes
0x18003528d  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180035294  mov     r8b, 1; OpenAsSelf
0x180035297  call    cs:__imp_NtOpenThreadTokenEx
0x18003529e  nop     dword ptr [rax+rax+00h]
0x1800352a3  test    eax, eax
0x1800352a5  jns     short loc_1800352E9
0x1800352a7  xor     r8d, r8d; OpenAsSelf
0x1800352aa  mov     [rsp+38h+TokenHandle], rbx; TokenHandle
0x1800352af  mov     r9d, 200h; HandleAttributes
0x1800352b5  lea     edx, [r8+28h]; DesiredAccess
0x1800352b9  lea     rcx, [r8-2]; ThreadHandle
0x1800352bd  call    cs:__imp_NtOpenThreadTokenEx
0x1800352c4  nop     dword ptr [rax+rax+00h]
0x1800352c9  add     rsp, 30h
0x1800352cd  pop     rbx
0x1800352ce  retn
0x1800352d0  mov     r9, rbx; TokenHandle
0x1800352d3  mov     r8d, 200h; HandleAttributes
0x1800352d9  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800352dd  call    cs:__imp_NtOpenProcessTokenEx
0x1800352e4  nop     dword ptr [rax+rax+00h]
0x1800352e9  add     rsp, 30h
0x1800352ed  pop     rbx
0x1800352ee  retn
```
