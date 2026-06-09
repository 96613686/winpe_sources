# IopDevObjApplyPostCreationSettings

- ea: `0x140042e54`
- end: `0x140042f43`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140042cc0`

## callees

- `0x140042e54`
- `0x140043f3c`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x140042ef9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140042ef9`
- `ntoskrnl!IoDeviceObjectType` at `0x140042eb5`
- `ntoskrnl!ZwSetSecurityObject` at `0x140042f16`
- `ntoskrnl!ZwSetSecurityObject` at `0x140042f16`
- `ntoskrnl!ZwClose` at `0x140042f29`
- `ntoskrnl!ZwClose` at `0x140042f29`

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
0x140042e54  mov     rax, rsp
0x140042e57  mov     [rax+8], rbx
0x140042e5b  push    rsi
0x140042e5c  sub     rsp, 40h
0x140042e60  mov     dword ptr [rax+18h], 0
0x140042e67  mov     rbx, rdx
0x140042e6a  mov     byte ptr [rax+10h], 0
0x140042e6e  mov     rsi, rcx
0x140042e71  mov     qword ptr [rax+20h], 0
0x140042e79  mov     eax, [rdx]
0x140042e7b  test    al, 2
0x140042e7d  jnz     short loc_140042E86
0x140042e7f  xor     eax, eax
0x140042e81  jmp     loc_140042F37
0x140042e86  mov     rcx, [rbx+8]; SecurityDescriptor
0x140042e8a  lea     r8, [rsp+48h+SecurityInformation]
0x140042e8f  lea     rdx, [rsp+48h+arg_8]
0x140042e94  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140042e99  test    eax, eax
0x140042e9b  js      loc_140042F37
0x140042ea1  mov     eax, [rsp+48h+SecurityInformation]
0x140042ea5  and     al, 3
0x140042ea7  neg     al
0x140042ea9  lea     rax, [rsp+48h+arg_18]
0x140042eae  sbb     ecx, ecx
0x140042eb0  mov     [rsp+48h+Handle], rax; Handle
0x140042eb5  mov     rax, cs:IoDeviceObjectType
0x140042ebc  and     ecx, 80000h
0x140042ec2  mov     edx, ecx
0x140042ec4  mov     [rsp+48h+AccessMode], 0; AccessMode
0x140042ec9  bts     edx, 12h
0x140042ecd  test    byte ptr [rsp+48h+SecurityInformation], 4
0x140042ed2  cmovz   edx, ecx
0x140042ed5  mov     rcx, [rax]
0x140042ed8  mov     r9d, edx
0x140042edb  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x140042ee0  bts     r9d, 18h
0x140042ee5  mov     rcx, rsi; Object
0x140042ee8  test    byte ptr [rsp+48h+SecurityInformation], 8
0x140042eed  cmovz   r9d, edx; DesiredAccess
0x140042ef1  xor     r8d, r8d; PassedAccessState
0x140042ef4  mov     edx, 200h; HandleAttributes
0x140042ef9  call    cs:__imp_ObOpenObjectByPointer
0x140042f00  nop     dword ptr [rax+rax+00h]
0x140042f05  test    eax, eax
0x140042f07  js      short loc_140042F37
0x140042f09  mov     r8, [rbx+8]; SecurityDescriptor
0x140042f0d  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x140042f11  mov     rcx, [rsp+48h+arg_18]; Handle
0x140042f16  call    cs:__imp_ZwSetSecurityObject
0x140042f1d  nop     dword ptr [rax+rax+00h]
0x140042f22  mov     rcx, [rsp+48h+arg_18]; Handle
0x140042f27  mov     ebx, eax
0x140042f29  call    cs:__imp_ZwClose
0x140042f30  nop     dword ptr [rax+rax+00h]
0x140042f35  mov     eax, ebx
0x140042f37  mov     rbx, [rsp+48h+arg_0]
0x140042f3c  add     rsp, 40h
0x140042f40  pop     rsi
0x140042f41  retn
```
