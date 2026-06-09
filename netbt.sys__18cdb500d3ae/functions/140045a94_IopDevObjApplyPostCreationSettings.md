# IopDevObjApplyPostCreationSettings

- ea: `0x140045a94`
- end: `0x140045b83`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140045900`

## callees

- `0x140045a94`
- `0x140046b6c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140045b69`
- `ntoskrnl!ZwClose` at `0x140045b69`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140045b39`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140045b39`
- `ntoskrnl!IoDeviceObjectType` at `0x140045af5`
- `ntoskrnl!ZwSetSecurityObject` at `0x140045b56`
- `ntoskrnl!ZwSetSecurityObject` at `0x140045b56`

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
0x140045a94  mov     rax, rsp
0x140045a97  mov     [rax+8], rbx
0x140045a9b  push    rsi
0x140045a9c  sub     rsp, 40h
0x140045aa0  mov     dword ptr [rax+18h], 0
0x140045aa7  mov     rbx, rdx
0x140045aaa  mov     byte ptr [rax+10h], 0
0x140045aae  mov     rsi, rcx
0x140045ab1  mov     qword ptr [rax+20h], 0
0x140045ab9  mov     eax, [rdx]
0x140045abb  test    al, 2
0x140045abd  jnz     short loc_140045AC6
0x140045abf  xor     eax, eax
0x140045ac1  jmp     loc_140045B77
0x140045ac6  mov     rcx, [rbx+8]; SecurityDescriptor
0x140045aca  lea     r8, [rsp+48h+SecurityInformation]
0x140045acf  lea     rdx, [rsp+48h+arg_8]
0x140045ad4  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140045ad9  test    eax, eax
0x140045adb  js      loc_140045B77
0x140045ae1  mov     eax, [rsp+48h+SecurityInformation]
0x140045ae5  and     al, 3
0x140045ae7  neg     al
0x140045ae9  lea     rax, [rsp+48h+arg_18]
0x140045aee  sbb     ecx, ecx
0x140045af0  mov     [rsp+48h+Handle], rax; Handle
0x140045af5  mov     rax, cs:IoDeviceObjectType
0x140045afc  and     ecx, 80000h
0x140045b02  mov     edx, ecx
0x140045b04  mov     [rsp+48h+AccessMode], 0; AccessMode
0x140045b09  bts     edx, 12h
0x140045b0d  test    byte ptr [rsp+48h+SecurityInformation], 4
0x140045b12  cmovz   edx, ecx
0x140045b15  mov     rcx, [rax]
0x140045b18  mov     r9d, edx
0x140045b1b  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x140045b20  bts     r9d, 18h
0x140045b25  mov     rcx, rsi; Object
0x140045b28  test    byte ptr [rsp+48h+SecurityInformation], 8
0x140045b2d  cmovz   r9d, edx; DesiredAccess
0x140045b31  xor     r8d, r8d; PassedAccessState
0x140045b34  mov     edx, 200h; HandleAttributes
0x140045b39  call    cs:__imp_ObOpenObjectByPointer
0x140045b40  nop     dword ptr [rax+rax+00h]
0x140045b45  test    eax, eax
0x140045b47  js      short loc_140045B77
0x140045b49  mov     r8, [rbx+8]; SecurityDescriptor
0x140045b4d  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x140045b51  mov     rcx, [rsp+48h+arg_18]; Handle
0x140045b56  call    cs:__imp_ZwSetSecurityObject
0x140045b5d  nop     dword ptr [rax+rax+00h]
0x140045b62  mov     rcx, [rsp+48h+arg_18]; Handle
0x140045b67  mov     ebx, eax
0x140045b69  call    cs:__imp_ZwClose
0x140045b70  nop     dword ptr [rax+rax+00h]
0x140045b75  mov     eax, ebx
0x140045b77  mov     rbx, [rsp+48h+arg_0]
0x140045b7c  add     rsp, 40h
0x140045b80  pop     rsi
0x140045b81  retn
```
