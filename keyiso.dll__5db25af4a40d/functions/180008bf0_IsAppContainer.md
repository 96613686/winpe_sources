# IsAppContainer

- ea: `0x180008bf0`
- end: `0x180008c5f`
- name: `IsAppContainer`
- size: `111`
- prototype: `signed int __fastcall(void *, _DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008858`
- `0x180008b44`

## callees

- `0x180008bf0`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180008c28`
- `ntdll!NtQueryInformationToken` at `0x180008c28`
- `ntdll!RtlNtStatusToDosError` at `0x180008c34`
- `ntdll!RtlNtStatusToDosError` at `0x180008c34`

## pseudocode

```c
signed int __fastcall IsAppContainer(void *a1, _DWORD *a2)
{
  NTSTATUS v3; // eax
  signed int result; // eax
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  ULONG ReturnLength; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v3 = NtQueryInformationToken(a1, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength);
  if ( v3 )
  {
    result = RtlNtStatusToDosError(v3);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    if ( TokenInformation )
      *a2 = 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008bf0  push    rbx
0x180008bf2  sub     rsp, 30h
0x180008bf6  mov     r9d, 4; TokenInformationLength
0x180008bfc  mov     dword ptr [rdx], 0
0x180008c02  mov     rbx, rdx
0x180008c05  mov     [rsp+38h+TokenInformation], 0
0x180008c0d  lea     rax, [rsp+38h+arg_10]
0x180008c12  mov     [rsp+38h+arg_10], 0
0x180008c1a  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180008c1f  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180008c24  lea     edx, [r9+19h]; TokenInformationClass
0x180008c28  call    cs:__imp_NtQueryInformationToken
0x180008c2e  test    eax, eax
0x180008c30  jz      short loc_180008C4E
0x180008c32  mov     ecx, eax; Status
0x180008c34  call    cs:__imp_RtlNtStatusToDosError
0x180008c3a  test    eax, eax
0x180008c3c  jg      short loc_180008C44
0x180008c3e  add     rsp, 30h
0x180008c42  pop     rbx
0x180008c43  retn
0x180008c44  movzx   eax, ax
0x180008c47  or      eax, 80070000h
0x180008c4c  jmp     short loc_180008C3E
0x180008c4e  cmp     [rsp+38h+TokenInformation], 0
0x180008c53  jz      short loc_180008C5B
0x180008c55  mov     dword ptr [rbx], 1
0x180008c5b  xor     eax, eax
0x180008c5d  jmp     short loc_180008C3E
```
