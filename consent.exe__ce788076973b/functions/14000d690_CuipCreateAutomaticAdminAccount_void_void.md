# CuipCreateAutomaticAdminAccount(void *,void * *)

- ea: `0x14000d690`
- end: `0x14000d6dd`
- name: `?CuipCreateAutomaticAdminAccount@@YAKPEAXPEAPEAX@Z`
- size: `77`
- prototype: `__int64 __fastcall(HANDLE SourceHandle, PHANDLE TargetHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000cfdc`

## callees

- `0x14000ad90`

## import_xrefs

- `ntdll!NtDuplicateObject` at `0x14000d6ca`
- `ntdll!NtDuplicateObject` at `0x14000d6ca`

## pseudocode

```c
__int64 __fastcall CuipCreateAutomaticAdminAccount(HANDLE SourceHandle, PHANDLE TargetHandle)
{
  CuipRemoveLegacyShadowAdminAccount(SourceHandle);
  NtDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, SourceHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL, TargetHandle, 0, 0, 2u);
  return 0;
}

```

## disassembly

```asm
0x14000d690  mov     [rsp+arg_0], rbx
0x14000d695  push    rdi
0x14000d696  sub     rsp, 40h
0x14000d69a  mov     rbx, rdx
0x14000d69d  mov     rdi, rcx
0x14000d6a0  call    ?CuipRemoveLegacyShadowAdminAccount@@YAXPEAX@Z; CuipRemoveLegacyShadowAdminAccount(void *)
0x14000d6a5  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x14000d6a9  mov     [rsp+48h+Options], 2; Options
0x14000d6b1  mov     r8, rcx; TargetProcessHandle
0x14000d6b4  mov     [rsp+48h+HandleAttributes], 0; HandleAttributes
0x14000d6bc  mov     r9, rbx; TargetHandle
0x14000d6bf  mov     [rsp+48h+DesiredAccess], 0; DesiredAccess
0x14000d6c7  mov     rdx, rdi; SourceHandle
0x14000d6ca  call    cs:__imp_NtDuplicateObject
0x14000d6d0  mov     rbx, [rsp+48h+arg_0]
0x14000d6d5  xor     eax, eax
0x14000d6d7  add     rsp, 40h
0x14000d6db  pop     rdi
0x14000d6dc  retn
```
