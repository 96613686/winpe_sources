# IopDevObjApplyPostCreationSettings

- ea: `0x140011124`
- end: `0x140011213`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140010f90`

## callees

- `0x140011124`
- `0x1400121fc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400111f9`
- `ntoskrnl!ZwClose` at `0x1400111f9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400111c9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400111c9`
- `ntoskrnl!IoDeviceObjectType` at `0x140011185`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400111e6`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400111e6`

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
0x140011124  mov     rax, rsp
0x140011127  mov     [rax+8], rbx
0x14001112b  push    rsi
0x14001112c  sub     rsp, 40h
0x140011130  mov     dword ptr [rax+18h], 0
0x140011137  mov     rbx, rdx
0x14001113a  mov     byte ptr [rax+10h], 0
0x14001113e  mov     rsi, rcx
0x140011141  mov     qword ptr [rax+20h], 0
0x140011149  mov     eax, [rdx]
0x14001114b  test    al, 2
0x14001114d  jnz     short loc_140011156
0x14001114f  xor     eax, eax
0x140011151  jmp     loc_140011207
0x140011156  mov     rcx, [rbx+8]; SecurityDescriptor
0x14001115a  lea     r8, [rsp+48h+SecurityInformation]
0x14001115f  lea     rdx, [rsp+48h+arg_8]
0x140011164  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140011169  test    eax, eax
0x14001116b  js      loc_140011207
0x140011171  mov     eax, [rsp+48h+SecurityInformation]
0x140011175  and     al, 3
0x140011177  neg     al
0x140011179  lea     rax, [rsp+48h+arg_18]
0x14001117e  sbb     ecx, ecx
0x140011180  mov     [rsp+48h+Handle], rax; Handle
0x140011185  mov     rax, cs:IoDeviceObjectType
0x14001118c  and     ecx, 80000h
0x140011192  mov     edx, ecx
0x140011194  mov     [rsp+48h+AccessMode], 0; AccessMode
0x140011199  bts     edx, 12h
0x14001119d  test    byte ptr [rsp+48h+SecurityInformation], 4
0x1400111a2  cmovz   edx, ecx
0x1400111a5  mov     rcx, [rax]
0x1400111a8  mov     r9d, edx
0x1400111ab  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x1400111b0  bts     r9d, 18h
0x1400111b5  mov     rcx, rsi; Object
0x1400111b8  test    byte ptr [rsp+48h+SecurityInformation], 8
0x1400111bd  cmovz   r9d, edx; DesiredAccess
0x1400111c1  xor     r8d, r8d; PassedAccessState
0x1400111c4  mov     edx, 200h; HandleAttributes
0x1400111c9  call    cs:__imp_ObOpenObjectByPointer
0x1400111d0  nop     dword ptr [rax+rax+00h]
0x1400111d5  test    eax, eax
0x1400111d7  js      short loc_140011207
0x1400111d9  mov     r8, [rbx+8]; SecurityDescriptor
0x1400111dd  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x1400111e1  mov     rcx, [rsp+48h+arg_18]; Handle
0x1400111e6  call    cs:__imp_ZwSetSecurityObject
0x1400111ed  nop     dword ptr [rax+rax+00h]
0x1400111f2  mov     rcx, [rsp+48h+arg_18]; Handle
0x1400111f7  mov     ebx, eax
0x1400111f9  call    cs:__imp_ZwClose
0x140011200  nop     dword ptr [rax+rax+00h]
0x140011205  mov     eax, ebx
0x140011207  mov     rbx, [rsp+48h+arg_0]
0x14001120c  add     rsp, 40h
0x140011210  pop     rsi
0x140011211  retn
```
