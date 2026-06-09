# IopDevObjApplyPostCreationSettings

- ea: `0x140009344`
- end: `0x140009433`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400091b0`

## callees

- `0x140009344`
- `0x14000a41c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140009419`
- `ntoskrnl!ZwClose` at `0x140009419`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400093e9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400093e9`
- `ntoskrnl!IoDeviceObjectType` at `0x1400093a5`
- `ntoskrnl!ZwSetSecurityObject` at `0x140009406`
- `ntoskrnl!ZwSetSecurityObject` at `0x140009406`

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
0x140009344  mov     rax, rsp
0x140009347  mov     [rax+8], rbx
0x14000934b  push    rsi
0x14000934c  sub     rsp, 40h
0x140009350  mov     dword ptr [rax+18h], 0
0x140009357  mov     rbx, rdx
0x14000935a  mov     byte ptr [rax+10h], 0
0x14000935e  mov     rsi, rcx
0x140009361  mov     qword ptr [rax+20h], 0
0x140009369  mov     eax, [rdx]
0x14000936b  test    al, 2
0x14000936d  jnz     short loc_140009376
0x14000936f  xor     eax, eax
0x140009371  jmp     loc_140009427
0x140009376  mov     rcx, [rbx+8]; SecurityDescriptor
0x14000937a  lea     r8, [rsp+48h+SecurityInformation]
0x14000937f  lea     rdx, [rsp+48h+arg_8]
0x140009384  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140009389  test    eax, eax
0x14000938b  js      loc_140009427
0x140009391  mov     eax, [rsp+48h+SecurityInformation]
0x140009395  and     al, 3
0x140009397  neg     al
0x140009399  lea     rax, [rsp+48h+arg_18]
0x14000939e  sbb     ecx, ecx
0x1400093a0  mov     [rsp+48h+Handle], rax; Handle
0x1400093a5  mov     rax, cs:IoDeviceObjectType
0x1400093ac  and     ecx, 80000h
0x1400093b2  mov     edx, ecx
0x1400093b4  mov     [rsp+48h+AccessMode], 0; AccessMode
0x1400093b9  bts     edx, 12h
0x1400093bd  test    byte ptr [rsp+48h+SecurityInformation], 4
0x1400093c2  cmovz   edx, ecx
0x1400093c5  mov     rcx, [rax]
0x1400093c8  mov     r9d, edx
0x1400093cb  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x1400093d0  bts     r9d, 18h
0x1400093d5  mov     rcx, rsi; Object
0x1400093d8  test    byte ptr [rsp+48h+SecurityInformation], 8
0x1400093dd  cmovz   r9d, edx; DesiredAccess
0x1400093e1  xor     r8d, r8d; PassedAccessState
0x1400093e4  mov     edx, 200h; HandleAttributes
0x1400093e9  call    cs:__imp_ObOpenObjectByPointer
0x1400093f0  nop     dword ptr [rax+rax+00h]
0x1400093f5  test    eax, eax
0x1400093f7  js      short loc_140009427
0x1400093f9  mov     r8, [rbx+8]; SecurityDescriptor
0x1400093fd  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x140009401  mov     rcx, [rsp+48h+arg_18]; Handle
0x140009406  call    cs:__imp_ZwSetSecurityObject
0x14000940d  nop     dword ptr [rax+rax+00h]
0x140009412  mov     rcx, [rsp+48h+arg_18]; Handle
0x140009417  mov     ebx, eax
0x140009419  call    cs:__imp_ZwClose
0x140009420  nop     dword ptr [rax+rax+00h]
0x140009425  mov     eax, ebx
0x140009427  mov     rbx, [rsp+48h+arg_0]
0x14000942c  add     rsp, 40h
0x140009430  pop     rsi
0x140009431  retn
```
