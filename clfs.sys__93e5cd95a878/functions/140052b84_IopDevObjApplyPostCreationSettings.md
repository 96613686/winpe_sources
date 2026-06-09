# IopDevObjApplyPostCreationSettings

- ea: `0x140052b84`
- end: `0x140052c73`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400529f0`

## callees

- `0x140052b84`
- `0x140053c5c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140052c59`
- `ntoskrnl!ZwClose` at `0x140052c59`
- `ntoskrnl!ZwSetSecurityObject` at `0x140052c46`
- `ntoskrnl!ZwSetSecurityObject` at `0x140052c46`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140052c29`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140052c29`
- `ntoskrnl!IoDeviceObjectType` at `0x140052be5`

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
0x140052b84  mov     rax, rsp
0x140052b87  mov     [rax+8], rbx
0x140052b8b  push    rsi
0x140052b8c  sub     rsp, 40h
0x140052b90  mov     dword ptr [rax+18h], 0
0x140052b97  mov     rbx, rdx
0x140052b9a  mov     byte ptr [rax+10h], 0
0x140052b9e  mov     rsi, rcx
0x140052ba1  mov     qword ptr [rax+20h], 0
0x140052ba9  mov     eax, [rdx]
0x140052bab  test    al, 2
0x140052bad  jnz     short loc_140052BB6
0x140052baf  xor     eax, eax
0x140052bb1  jmp     loc_140052C67
0x140052bb6  mov     rcx, [rbx+8]; SecurityDescriptor
0x140052bba  lea     r8, [rsp+48h+SecurityInformation]
0x140052bbf  lea     rdx, [rsp+48h+arg_8]
0x140052bc4  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140052bc9  test    eax, eax
0x140052bcb  js      loc_140052C67
0x140052bd1  mov     eax, [rsp+48h+SecurityInformation]
0x140052bd5  and     al, 3
0x140052bd7  neg     al
0x140052bd9  lea     rax, [rsp+48h+arg_18]
0x140052bde  sbb     ecx, ecx
0x140052be0  mov     [rsp+48h+Handle], rax; Handle
0x140052be5  mov     rax, cs:IoDeviceObjectType
0x140052bec  and     ecx, 80000h
0x140052bf2  mov     edx, ecx
0x140052bf4  mov     [rsp+48h+AccessMode], 0; AccessMode
0x140052bf9  bts     edx, 12h
0x140052bfd  test    byte ptr [rsp+48h+SecurityInformation], 4
0x140052c02  cmovz   edx, ecx
0x140052c05  mov     rcx, [rax]
0x140052c08  mov     r9d, edx
0x140052c0b  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x140052c10  bts     r9d, 18h
0x140052c15  mov     rcx, rsi; Object
0x140052c18  test    byte ptr [rsp+48h+SecurityInformation], 8
0x140052c1d  cmovz   r9d, edx; DesiredAccess
0x140052c21  xor     r8d, r8d; PassedAccessState
0x140052c24  mov     edx, 200h; HandleAttributes
0x140052c29  call    cs:__imp_ObOpenObjectByPointer
0x140052c30  nop     dword ptr [rax+rax+00h]
0x140052c35  test    eax, eax
0x140052c37  js      short loc_140052C67
0x140052c39  mov     r8, [rbx+8]; SecurityDescriptor
0x140052c3d  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x140052c41  mov     rcx, [rsp+48h+arg_18]; Handle
0x140052c46  call    cs:__imp_ZwSetSecurityObject
0x140052c4d  nop     dword ptr [rax+rax+00h]
0x140052c52  mov     rcx, [rsp+48h+arg_18]; Handle
0x140052c57  mov     ebx, eax
0x140052c59  call    cs:__imp_ZwClose
0x140052c60  nop     dword ptr [rax+rax+00h]
0x140052c65  mov     eax, ebx
0x140052c67  mov     rbx, [rsp+48h+arg_0]
0x140052c6c  add     rsp, 40h
0x140052c70  pop     rsi
0x140052c71  retn
```
