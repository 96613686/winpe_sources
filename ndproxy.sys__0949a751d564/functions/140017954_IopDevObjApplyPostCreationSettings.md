# IopDevObjApplyPostCreationSettings

- ea: `0x140017954`
- end: `0x140017a43`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400177c0`

## callees

- `0x140017954`
- `0x140018a1c`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400179f9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400179f9`
- `ntoskrnl!IoDeviceObjectType` at `0x1400179b5`
- `ntoskrnl!ZwSetSecurityObject` at `0x140017a16`
- `ntoskrnl!ZwSetSecurityObject` at `0x140017a16`
- `ntoskrnl!ZwClose` at `0x140017a29`
- `ntoskrnl!ZwClose` at `0x140017a29`

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
0x140017954  mov     rax, rsp
0x140017957  mov     [rax+8], rbx
0x14001795b  push    rsi
0x14001795c  sub     rsp, 40h
0x140017960  mov     dword ptr [rax+18h], 0
0x140017967  mov     rbx, rdx
0x14001796a  mov     byte ptr [rax+10h], 0
0x14001796e  mov     rsi, rcx
0x140017971  mov     qword ptr [rax+20h], 0
0x140017979  mov     eax, [rdx]
0x14001797b  test    al, 2
0x14001797d  jnz     short loc_140017986
0x14001797f  xor     eax, eax
0x140017981  jmp     loc_140017A37
0x140017986  mov     rcx, [rbx+8]; SecurityDescriptor
0x14001798a  lea     r8, [rsp+48h+SecurityInformation]
0x14001798f  lea     rdx, [rsp+48h+arg_8]
0x140017994  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140017999  test    eax, eax
0x14001799b  js      loc_140017A37
0x1400179a1  mov     eax, [rsp+48h+SecurityInformation]
0x1400179a5  and     al, 3
0x1400179a7  neg     al
0x1400179a9  lea     rax, [rsp+48h+arg_18]
0x1400179ae  sbb     ecx, ecx
0x1400179b0  mov     [rsp+48h+Handle], rax; Handle
0x1400179b5  mov     rax, cs:IoDeviceObjectType
0x1400179bc  and     ecx, 80000h
0x1400179c2  mov     edx, ecx
0x1400179c4  mov     [rsp+48h+AccessMode], 0; AccessMode
0x1400179c9  bts     edx, 12h
0x1400179cd  test    byte ptr [rsp+48h+SecurityInformation], 4
0x1400179d2  cmovz   edx, ecx
0x1400179d5  mov     rcx, [rax]
0x1400179d8  mov     r9d, edx
0x1400179db  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x1400179e0  bts     r9d, 18h
0x1400179e5  mov     rcx, rsi; Object
0x1400179e8  test    byte ptr [rsp+48h+SecurityInformation], 8
0x1400179ed  cmovz   r9d, edx; DesiredAccess
0x1400179f1  xor     r8d, r8d; PassedAccessState
0x1400179f4  mov     edx, 200h; HandleAttributes
0x1400179f9  call    cs:__imp_ObOpenObjectByPointer
0x140017a00  nop     dword ptr [rax+rax+00h]
0x140017a05  test    eax, eax
0x140017a07  js      short loc_140017A37
0x140017a09  mov     r8, [rbx+8]; SecurityDescriptor
0x140017a0d  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x140017a11  mov     rcx, [rsp+48h+arg_18]; Handle
0x140017a16  call    cs:__imp_ZwSetSecurityObject
0x140017a1d  nop     dword ptr [rax+rax+00h]
0x140017a22  mov     rcx, [rsp+48h+arg_18]; Handle
0x140017a27  mov     ebx, eax
0x140017a29  call    cs:__imp_ZwClose
0x140017a30  nop     dword ptr [rax+rax+00h]
0x140017a35  mov     eax, ebx
0x140017a37  mov     rbx, [rsp+48h+arg_0]
0x140017a3c  add     rsp, 40h
0x140017a40  pop     rsi
0x140017a41  retn
```
