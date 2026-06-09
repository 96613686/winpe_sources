# ProcessGroupPolicyCompletedWorker(_GUID *,unsigned __int64,ulong)

- ea: `0x18001d660`
- end: `0x18001d6ae`
- name: `?ProcessGroupPolicyCompletedWorker@@YAKPEAU_GUID@@_KK@Z`
- size: `78`
- prototype: `unsigned int __fastcall(struct _GUID *, unsigned __int64, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800122d8`
- `0x18001d660`

## import_xrefs

- `ext-ms-win-gpsvc-grouppolicy-l1-1-0!ProcessGroupPolicyCompletedInternal` at `0x18001d691`
- `ext-ms-win-gpsvc-grouppolicy-l1-1-0!ProcessGroupPolicyCompletedInternal` at `0x18001d691`

## pseudocode

```c
__int64 __fastcall ProcessGroupPolicyCompletedWorker(struct _GUID *a1, __int64 a2, unsigned int a3)
{
  if ( (unsigned __int8)IsRsopAccessCheckByTypeInternalPresent() )
    return ProcessGroupPolicyCompletedInternal(a1, a2, a3);
  else
    return 127;
}

```

## disassembly

```asm
0x18001d660  mov     [rsp+arg_0], rbx
0x18001d665  mov     [rsp+arg_8], rsi
0x18001d66a  push    rdi
0x18001d66b  sub     rsp, 20h
0x18001d66f  mov     ebx, r8d
0x18001d672  mov     rdi, rdx
0x18001d675  mov     rsi, rcx
0x18001d678  call    IsRsopAccessCheckByTypeInternalPresent
0x18001d67d  test    al, al
0x18001d67f  jnz     short loc_18001D688
0x18001d681  mov     eax, 7Fh
0x18001d686  jmp     short loc_18001D69D
0x18001d688  mov     r8d, ebx
0x18001d68b  mov     rdx, rdi
0x18001d68e  mov     rcx, rsi
0x18001d691  call    cs:__imp_ProcessGroupPolicyCompletedInternal
0x18001d698  nop     dword ptr [rax+rax+00h]
0x18001d69d  mov     rbx, [rsp+28h+arg_0]
0x18001d6a2  mov     rsi, [rsp+28h+arg_8]
0x18001d6a7  add     rsp, 20h
0x18001d6ab  pop     rdi
0x18001d6ac  retn
```
