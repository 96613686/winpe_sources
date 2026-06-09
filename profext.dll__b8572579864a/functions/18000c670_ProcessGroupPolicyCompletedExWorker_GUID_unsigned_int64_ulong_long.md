# ProcessGroupPolicyCompletedExWorker(_GUID *,unsigned __int64,ulong,long)

- ea: `0x18000c670`
- end: `0x18000c6b7`
- name: `?ProcessGroupPolicyCompletedExWorker@@YAKPEAU_GUID@@_KKJ@Z`
- size: `71`
- prototype: `unsigned int __fastcall(struct _GUID *, unsigned __int64, unsigned int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000c670`
- `0x1800122d8`

## import_xrefs

- `ext-ms-win-gpsvc-grouppolicy-l1-1-0!ProcessGroupPolicyCompletedExInternal` at `0x18000c69a`
- `ext-ms-win-gpsvc-grouppolicy-l1-1-0!ProcessGroupPolicyCompletedExInternal` at `0x18000c69a`

## pseudocode

```c
__int64 __fastcall ProcessGroupPolicyCompletedExWorker(struct _GUID *a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  if ( (unsigned __int8)IsRsopAccessCheckByTypeInternalPresent() )
    return ProcessGroupPolicyCompletedExInternal(a1, a2, a3, a4);
  else
    return 127;
}

```

## disassembly

```asm
0x18000c670  push    rbx
0x18000c672  push    rbp
0x18000c673  push    rsi
0x18000c674  push    rdi
0x18000c675  sub     rsp, 28h
0x18000c679  mov     ebx, r9d
0x18000c67c  mov     edi, r8d
0x18000c67f  mov     rsi, rdx
0x18000c682  mov     rbp, rcx
0x18000c685  call    IsRsopAccessCheckByTypeInternalPresent
0x18000c68a  test    al, al
0x18000c68c  jz      short loc_18000C6B0
0x18000c68e  mov     r9d, ebx
0x18000c691  mov     r8d, edi
0x18000c694  mov     rdx, rsi
0x18000c697  mov     rcx, rbp
0x18000c69a  call    cs:__imp_ProcessGroupPolicyCompletedExInternal
0x18000c6a1  nop     dword ptr [rax+rax+00h]
0x18000c6a6  add     rsp, 28h
0x18000c6aa  pop     rdi
0x18000c6ab  pop     rsi
0x18000c6ac  pop     rbp
0x18000c6ad  pop     rbx
0x18000c6ae  retn
0x18000c6b0  mov     eax, 7Fh
0x18000c6b5  jmp     short loc_18000C6A6
```
