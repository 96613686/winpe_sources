# IopDevObjApplyPostCreationSettings

- ea: `0x140021094`
- end: `0x140021183`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140020f00`

## callees

- `0x140021094`
- `0x140022154`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140021169`
- `ntoskrnl!ZwClose` at `0x140021169`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140021139`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140021139`
- `ntoskrnl!IoDeviceObjectType` at `0x1400210f5`
- `ntoskrnl!ZwSetSecurityObject` at `0x140021156`
- `ntoskrnl!ZwSetSecurityObject` at `0x140021156`

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
0x140021094  mov     rax, rsp
0x140021097  mov     [rax+8], rbx
0x14002109b  push    rsi
0x14002109c  sub     rsp, 40h
0x1400210a0  mov     dword ptr [rax+18h], 0
0x1400210a7  mov     rbx, rdx
0x1400210aa  mov     byte ptr [rax+10h], 0
0x1400210ae  mov     rsi, rcx
0x1400210b1  mov     qword ptr [rax+20h], 0
0x1400210b9  mov     eax, [rdx]
0x1400210bb  test    al, 2
0x1400210bd  jnz     short loc_1400210C6
0x1400210bf  xor     eax, eax
0x1400210c1  jmp     loc_140021177
0x1400210c6  mov     rcx, [rbx+8]; SecurityDescriptor
0x1400210ca  lea     r8, [rsp+48h+SecurityInformation]
0x1400210cf  lea     rdx, [rsp+48h+arg_8]
0x1400210d4  call    SeUtilSecurityInfoFromSecurityDescriptor
0x1400210d9  test    eax, eax
0x1400210db  js      loc_140021177
0x1400210e1  mov     eax, [rsp+48h+SecurityInformation]
0x1400210e5  and     al, 3
0x1400210e7  neg     al
0x1400210e9  lea     rax, [rsp+48h+arg_18]
0x1400210ee  sbb     ecx, ecx
0x1400210f0  mov     [rsp+48h+Handle], rax; Handle
0x1400210f5  mov     rax, cs:IoDeviceObjectType
0x1400210fc  and     ecx, 80000h
0x140021102  mov     edx, ecx
0x140021104  mov     [rsp+48h+AccessMode], 0; AccessMode
0x140021109  bts     edx, 12h
0x14002110d  test    byte ptr [rsp+48h+SecurityInformation], 4
0x140021112  cmovz   edx, ecx
0x140021115  mov     rcx, [rax]
0x140021118  mov     r9d, edx
0x14002111b  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x140021120  bts     r9d, 18h
0x140021125  mov     rcx, rsi; Object
0x140021128  test    byte ptr [rsp+48h+SecurityInformation], 8
0x14002112d  cmovz   r9d, edx; DesiredAccess
0x140021131  xor     r8d, r8d; PassedAccessState
0x140021134  mov     edx, 200h; HandleAttributes
0x140021139  call    cs:__imp_ObOpenObjectByPointer
0x140021140  nop     dword ptr [rax+rax+00h]
0x140021145  test    eax, eax
0x140021147  js      short loc_140021177
0x140021149  mov     r8, [rbx+8]; SecurityDescriptor
0x14002114d  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x140021151  mov     rcx, [rsp+48h+arg_18]; Handle
0x140021156  call    cs:__imp_ZwSetSecurityObject
0x14002115d  nop     dword ptr [rax+rax+00h]
0x140021162  mov     rcx, [rsp+48h+arg_18]; Handle
0x140021167  mov     ebx, eax
0x140021169  call    cs:__imp_ZwClose
0x140021170  nop     dword ptr [rax+rax+00h]
0x140021175  mov     eax, ebx
0x140021177  mov     rbx, [rsp+48h+arg_0]
0x14002117c  add     rsp, 40h
0x140021180  pop     rsi
0x140021181  retn
```
