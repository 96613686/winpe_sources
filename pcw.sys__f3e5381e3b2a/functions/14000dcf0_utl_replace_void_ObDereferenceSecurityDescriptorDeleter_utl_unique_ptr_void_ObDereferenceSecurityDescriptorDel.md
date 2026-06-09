# utl::replace<void,ObDereferenceSecurityDescriptorDeleter>(utl::unique_ptr<void,ObDereferenceSecurityDescriptorDeleter> &)

- ea: `0x14000dcf0`
- end: `0x14000dd23`
- name: `??$replace@XUObDereferenceSecurityDescriptorDeleter@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XUObDereferenceSecurityDescriptorDeleter@@@0@@Z`
- size: `51`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000e088`
- `0x14000e6f8`
- `0x14000e8c0`

## callees

- `0x14000dcf0`

## import_xrefs

- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000dd0d`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000dd0d`

## pseudocode

```c
__int64 *__fastcall utl::replace<void,ObDereferenceSecurityDescriptorDeleter>(__int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  *a1 = 0;
  if ( v2 )
    ObDereferenceSecurityDescriptor(v2, 1);
  return a1;
}

```

## disassembly

```asm
0x14000dcf0  push    rbx
0x14000dcf2  sub     rsp, 20h
0x14000dcf6  mov     rbx, rcx
0x14000dcf9  mov     rcx, [rcx]
0x14000dcfc  mov     qword ptr [rbx], 0
0x14000dd03  test    rcx, rcx
0x14000dd06  jz      short loc_14000DD19
0x14000dd08  mov     edx, 1
0x14000dd0d  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000dd14  nop     dword ptr [rax+rax+00h]
0x14000dd19  mov     rax, rbx
0x14000dd1c  add     rsp, 20h
0x14000dd20  pop     rbx
0x14000dd21  retn
```
