# MspImpersonateNetworkService

- ea: `0x1800346a0`
- end: `0x18003470f`
- name: `MspImpersonateNetworkService`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180033148`

## callees

- `0x1800346a0`
- `0x18006d010`

## import_xrefs

- `ntdll!NtClose` at `0x180034701`
- `ntdll!NtClose` at `0x180034701`
- `ntdll!NtSetInformationThread` at `0x1800346ef`
- `ntdll!NtSetInformationThread` at `0x1800346ef`

## pseudocode

```c
__int64 MspImpersonateNetworkService()
{
  NTSTATUS v0; // ebx
  HANDLE ThreadInformation; // [rsp+30h] [rbp+8h] BYREF
  __int64 v3; // [rsp+38h] [rbp+10h] BYREF

  ThreadInformation = 0;
  v3 = 996;
  v0 = ((__int64 (__fastcall *)(__int64 *, HANDLE *))LsaFunctions->OpenTokenByLogonId)(&v3, &ThreadInformation);
  if ( v0 >= 0 )
    v0 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  if ( ThreadInformation )
    NtClose(ThreadInformation);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1800346a0  mov     r11, rsp
0x1800346a3  push    rbx
0x1800346a4  sub     rsp, 20h
0x1800346a8  mov     rax, cs:LsaFunctions
0x1800346af  lea     rdx, [r11+8]
0x1800346b3  lea     rcx, [r11+10h]
0x1800346b7  mov     qword ptr [r11+8], 0
0x1800346bf  mov     qword ptr [r11+10h], 3E4h
0x1800346c7  mov     rax, [rax+170h]
0x1800346ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800346d3  mov     ebx, eax
0x1800346d5  test    eax, eax
0x1800346d7  js      short loc_1800346F7
0x1800346d9  mov     r9d, 8; ThreadInformationLength
0x1800346df  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x1800346e4  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800346eb  lea     edx, [r9-3]; ThreadInformationClass
0x1800346ef  call    cs:__imp_NtSetInformationThread
0x1800346f5  mov     ebx, eax
0x1800346f7  mov     rcx, [rsp+28h+ThreadInformation]; Handle
0x1800346fc  test    rcx, rcx
0x1800346ff  jz      short loc_180034707
0x180034701  call    cs:__imp_NtClose
0x180034707  mov     eax, ebx
0x180034709  add     rsp, 20h
0x18003470d  pop     rbx
0x18003470e  retn
```
