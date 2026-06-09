# BfsRevertTokenImpersonation

- ea: `0x140010070`
- end: `0x1400100d7`
- name: `BfsRevertTokenImpersonation`
- size: `103`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400069a0`
- `0x14000a530`
- `0x14000a930`
- `0x14000e2a0`

## callees

- `0x140010070`

## import_xrefs

- `ntoskrnl!PsRevertToSelf` at `0x14001007f`
- `ntoskrnl!PsRevertToSelf` at `0x14001007f`
- `ntoskrnl!PsImpersonateClient` at `0x1400100bb`
- `ntoskrnl!PsImpersonateClient` at `0x1400100bb`
- `ntoskrnl!ObfDereferenceObject` at `0x14001008e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001008e`

## pseudocode

```c
__int64 __fastcall BfsRevertTokenImpersonation(__int64 a1)
{
  unsigned int v2; // edi
  void *v3; // rdx

  v2 = 0;
  PsRevertToSelf();
  ObfDereferenceObject(*(PVOID *)a1);
  v3 = *(void **)(a1 + 8);
  if ( v3 )
    return (unsigned int)PsImpersonateClient(
                           KeGetCurrentThread(),
                           v3,
                           *(_BYTE *)(a1 + 16),
                           *(_BYTE *)(a1 + 17),
                           *(SECURITY_IMPERSONATION_LEVEL *)(a1 + 20));
  return v2;
}

```

## disassembly

```asm
0x140010070  mov     [rsp+arg_0], rbx
0x140010075  push    rdi
0x140010076  sub     rsp, 30h
0x14001007a  mov     rbx, rcx
0x14001007d  xor     edi, edi
0x14001007f  call    cs:__imp_PsRevertToSelf
0x140010086  nop     dword ptr [rax+rax+00h]
0x14001008b  mov     rcx, [rbx]; Object
0x14001008e  call    cs:__imp_ObfDereferenceObject
0x140010095  nop     dword ptr [rax+rax+00h]
0x14001009a  mov     rdx, [rbx+8]; Token
0x14001009e  test    rdx, rdx
0x1400100a1  jz      short loc_1400100C9
0x1400100a3  mov     rcx, gs:188h; Thread
0x1400100ac  mov     eax, [rbx+14h]
0x1400100af  mov     r9b, [rbx+11h]; EffectiveOnly
0x1400100b3  mov     r8b, [rbx+10h]; CopyOnOpen
0x1400100b7  mov     [rsp+38h+ImpersonationLevel], eax; ImpersonationLevel
0x1400100bb  call    cs:__imp_PsImpersonateClient
0x1400100c2  nop     dword ptr [rax+rax+00h]
0x1400100c7  mov     edi, eax
0x1400100c9  mov     rbx, [rsp+38h+arg_0]
0x1400100ce  mov     eax, edi
0x1400100d0  add     rsp, 30h
0x1400100d4  pop     rdi
0x1400100d5  retn
```
