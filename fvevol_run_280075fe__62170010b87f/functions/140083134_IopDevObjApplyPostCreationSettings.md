# IopDevObjApplyPostCreationSettings

- ea: `0x140083134`
- end: `0x140083223`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140082fa0`

## callees

- `0x140083134`
- `0x14008420c`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400831d9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400831d9`
- `ntoskrnl!IoDeviceObjectType` at `0x140083195`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400831f6`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400831f6`
- `ntoskrnl!ZwClose` at `0x140083209`
- `ntoskrnl!ZwClose` at `0x140083209`

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
0x140083134  mov     rax, rsp
0x140083137  mov     [rax+8], rbx
0x14008313b  push    rsi
0x14008313c  sub     rsp, 40h
0x140083140  mov     dword ptr [rax+18h], 0
0x140083147  mov     rbx, rdx
0x14008314a  mov     byte ptr [rax+10h], 0
0x14008314e  mov     rsi, rcx
0x140083151  mov     qword ptr [rax+20h], 0
0x140083159  mov     eax, [rdx]
0x14008315b  test    al, 2
0x14008315d  jnz     short loc_140083166
0x14008315f  xor     eax, eax
0x140083161  jmp     loc_140083217
0x140083166  mov     rcx, [rbx+8]; SecurityDescriptor
0x14008316a  lea     r8, [rsp+48h+SecurityInformation]
0x14008316f  lea     rdx, [rsp+48h+arg_8]
0x140083174  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140083179  test    eax, eax
0x14008317b  js      loc_140083217
0x140083181  mov     eax, [rsp+48h+SecurityInformation]
0x140083185  and     al, 3
0x140083187  neg     al
0x140083189  lea     rax, [rsp+48h+arg_18]
0x14008318e  sbb     ecx, ecx
0x140083190  mov     [rsp+48h+Handle], rax; Handle
0x140083195  mov     rax, cs:IoDeviceObjectType
0x14008319c  and     ecx, 80000h
0x1400831a2  mov     edx, ecx
0x1400831a4  mov     [rsp+48h+AccessMode], 0; AccessMode
0x1400831a9  bts     edx, 12h
0x1400831ad  test    byte ptr [rsp+48h+SecurityInformation], 4
0x1400831b2  cmovz   edx, ecx
0x1400831b5  mov     rcx, [rax]
0x1400831b8  mov     r9d, edx
0x1400831bb  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x1400831c0  bts     r9d, 18h
0x1400831c5  mov     rcx, rsi; Object
0x1400831c8  test    byte ptr [rsp+48h+SecurityInformation], 8
0x1400831cd  cmovz   r9d, edx; DesiredAccess
0x1400831d1  xor     r8d, r8d; PassedAccessState
0x1400831d4  mov     edx, 200h; HandleAttributes
0x1400831d9  call    cs:__imp_ObOpenObjectByPointer
0x1400831e0  nop     dword ptr [rax+rax+00h]
0x1400831e5  test    eax, eax
0x1400831e7  js      short loc_140083217
0x1400831e9  mov     r8, [rbx+8]; SecurityDescriptor
0x1400831ed  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x1400831f1  mov     rcx, [rsp+48h+arg_18]; Handle
0x1400831f6  call    cs:__imp_ZwSetSecurityObject
0x1400831fd  nop     dword ptr [rax+rax+00h]
0x140083202  mov     rcx, [rsp+48h+arg_18]; Handle
0x140083207  mov     ebx, eax
0x140083209  call    cs:__imp_ZwClose
0x140083210  nop     dword ptr [rax+rax+00h]
0x140083215  mov     eax, ebx
0x140083217  mov     rbx, [rsp+48h+arg_0]
0x14008321c  add     rsp, 40h
0x140083220  pop     rsi
0x140083221  retn
```
