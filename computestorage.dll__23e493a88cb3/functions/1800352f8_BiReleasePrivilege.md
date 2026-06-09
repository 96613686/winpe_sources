# BiReleasePrivilege

- ea: `0x1800352f8`
- end: `0x180035352`
- name: `BiReleasePrivilege`
- size: `90`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800334d4`
- `0x180033e80`
- `0x180035684`
- `0x1800368f0`
- `0x18003699c`
- `0x180036b18`
- `0x180036d98`
- `0x180037abc`
- `0x180037b54`
- `0x180037c88`
- `0x180037dc4`
- `0x180037e68`

## callees

- `0x18003514c`
- `0x1800352f8`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18003533f`
- `ntdll!NtSetInformationThread` at `0x18003533f`

## pseudocode

```c
NTSTATUS __fastcall BiReleasePrivilege(unsigned int *a1)
{
  bool v1; // zf
  NTSTATUS result; // eax
  __int64 ThreadInformation; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_BYTE *)a1 + 4) == 0;
  LOBYTE(ThreadInformation) = 0;
  if ( v1 )
    result = BiAdjustPrivilege(*a1, 0, &ThreadInformation);
  if ( !*((_BYTE *)a1 + 5) )
  {
    ThreadInformation = 0;
    return NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  }
  return result;
}

```

## disassembly

```asm
0x1800352f8  push    rbx
0x1800352fa  sub     rsp, 20h
0x1800352fe  cmp     byte ptr [rcx+4], 0
0x180035302  mov     rbx, rcx
0x180035305  mov     byte ptr [rsp+28h+ThreadInformation], 0
0x18003530a  jnz     short loc_18003531A
0x18003530c  mov     ecx, [rcx]
0x18003530e  lea     r8, [rsp+28h+ThreadInformation]
0x180035313  xor     edx, edx
0x180035315  call    BiAdjustPrivilege
0x18003531a  cmp     byte ptr [rbx+5], 0
0x18003531e  jnz     short loc_18003534B
0x180035320  mov     r9d, 8; ThreadInformationLength
0x180035326  mov     [rsp+28h+ThreadInformation], 0
0x18003532f  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x180035334  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18003533b  lea     edx, [r9-3]; ThreadInformationClass
0x18003533f  call    cs:__imp_NtSetInformationThread
0x180035346  nop     dword ptr [rax+rax+00h]
0x18003534b  add     rsp, 20h
0x18003534f  pop     rbx
0x180035350  retn
```
