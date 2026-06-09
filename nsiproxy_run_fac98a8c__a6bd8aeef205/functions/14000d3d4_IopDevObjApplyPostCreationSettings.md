# IopDevObjApplyPostCreationSettings

- ea: `0x14000d3d4`
- end: `0x14000d4c3`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000d240`

## callees

- `0x14000d3d4`
- `0x14000e4ac`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x14000d479`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000d479`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000d496`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000d496`
- `ntoskrnl!ZwClose` at `0x14000d4a9`
- `ntoskrnl!ZwClose` at `0x14000d4a9`
- `ntoskrnl!IoDeviceObjectType` at `0x14000d435`

## pseudocode

```c
NTSTATUS __fastcall IopDevObjApplyPostCreationSettings(PVOID Object, __int64 a2)
{
  NTSTATUS result; // eax
  int v5; // edx
  ACCESS_MASK v6; // r9d
  NTSTATUS v7; // ebx
  unsigned __int8 v8; // [rsp+58h] [rbp+10h] BYREF
  SECURITY_INFORMATION SecurityInformation; // [rsp+60h] [rbp+18h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp+20h] BYREF

  SecurityInformation = 0;
  v8 = 0;
  Handle = 0;
  if ( (*(_DWORD *)a2 & 2) == 0 )
    return 0;
  result = SeUtilSecurityInfoFromSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 8), &v8, &SecurityInformation);
  if ( result >= 0 )
  {
    v5 = ((SecurityInformation & 3) != 0 ? 0x80000 : 0) | 0x40000;
    if ( (SecurityInformation & 4) == 0 )
      v5 = (SecurityInformation & 3) != 0 ? 0x80000 : 0;
    v6 = v5 | 0x1000000;
    if ( (SecurityInformation & 8) == 0 )
      v6 = v5;
    result = ObOpenObjectByPointer(Object, 0x200u, 0, v6, IoDeviceObjectType, 0, &Handle);
    if ( result >= 0 )
    {
      v7 = ZwSetSecurityObject(Handle, SecurityInformation, *(PSECURITY_DESCRIPTOR *)(a2 + 8));
      ZwClose(Handle);
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d3d4  mov     rax, rsp
0x14000d3d7  mov     [rax+8], rbx
0x14000d3db  push    rsi
0x14000d3dc  sub     rsp, 40h
0x14000d3e0  mov     dword ptr [rax+18h], 0
0x14000d3e7  mov     rbx, rdx
0x14000d3ea  mov     byte ptr [rax+10h], 0
0x14000d3ee  mov     rsi, rcx
0x14000d3f1  mov     qword ptr [rax+20h], 0
0x14000d3f9  mov     eax, [rdx]
0x14000d3fb  test    al, 2
0x14000d3fd  jnz     short loc_14000D406
0x14000d3ff  xor     eax, eax
0x14000d401  jmp     loc_14000D4B7
0x14000d406  mov     rcx, [rbx+8]; SecurityDescriptor
0x14000d40a  lea     r8, [rsp+48h+SecurityInformation]
0x14000d40f  lea     rdx, [rsp+48h+arg_8]
0x14000d414  call    SeUtilSecurityInfoFromSecurityDescriptor
0x14000d419  test    eax, eax
0x14000d41b  js      loc_14000D4B7
0x14000d421  mov     eax, [rsp+48h+SecurityInformation]
0x14000d425  and     al, 3
0x14000d427  neg     al
0x14000d429  lea     rax, [rsp+48h+arg_18]
0x14000d42e  sbb     ecx, ecx
0x14000d430  mov     [rsp+48h+Handle], rax; Handle
0x14000d435  mov     rax, cs:IoDeviceObjectType
0x14000d43c  and     ecx, 80000h
0x14000d442  mov     edx, ecx
0x14000d444  mov     [rsp+48h+AccessMode], 0; AccessMode
0x14000d449  bts     edx, 12h
0x14000d44d  test    byte ptr [rsp+48h+SecurityInformation], 4
0x14000d452  cmovz   edx, ecx
0x14000d455  mov     rcx, [rax]
0x14000d458  mov     r9d, edx
0x14000d45b  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x14000d460  bts     r9d, 18h
0x14000d465  mov     rcx, rsi; Object
0x14000d468  test    byte ptr [rsp+48h+SecurityInformation], 8
0x14000d46d  cmovz   r9d, edx; DesiredAccess
0x14000d471  xor     r8d, r8d; PassedAccessState
0x14000d474  mov     edx, 200h; HandleAttributes
0x14000d479  call    cs:__imp_ObOpenObjectByPointer
0x14000d480  nop     dword ptr [rax+rax+00h]
0x14000d485  test    eax, eax
0x14000d487  js      short loc_14000D4B7
0x14000d489  mov     r8, [rbx+8]; SecurityDescriptor
0x14000d48d  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x14000d491  mov     rcx, [rsp+48h+arg_18]; Handle
0x14000d496  call    cs:__imp_ZwSetSecurityObject
0x14000d49d  nop     dword ptr [rax+rax+00h]
0x14000d4a2  mov     rcx, [rsp+48h+arg_18]; Handle
0x14000d4a7  mov     ebx, eax
0x14000d4a9  call    cs:__imp_ZwClose
0x14000d4b0  nop     dword ptr [rax+rax+00h]
0x14000d4b5  mov     eax, ebx
0x14000d4b7  mov     rbx, [rsp+48h+arg_0]
0x14000d4bc  add     rsp, 40h
0x14000d4c0  pop     rsi
0x14000d4c1  retn
```
