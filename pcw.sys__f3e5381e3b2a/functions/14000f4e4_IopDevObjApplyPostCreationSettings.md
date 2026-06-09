# IopDevObjApplyPostCreationSettings

- ea: `0x14000f4e4`
- end: `0x14000f5d3`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000f350`

## callees

- `0x14000f248`
- `0x14000f4e4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000f5b9`
- `ntoskrnl!ZwClose` at `0x14000f5b9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000f589`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000f589`
- `ntoskrnl!IoDeviceObjectType` at `0x14000f545`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000f5a6`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000f5a6`

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
0x14000f4e4  mov     rax, rsp
0x14000f4e7  mov     [rax+8], rbx
0x14000f4eb  push    rsi
0x14000f4ec  sub     rsp, 40h
0x14000f4f0  mov     dword ptr [rax+18h], 0
0x14000f4f7  mov     rbx, rdx
0x14000f4fa  mov     byte ptr [rax+10h], 0
0x14000f4fe  mov     rsi, rcx
0x14000f501  mov     qword ptr [rax+20h], 0
0x14000f509  mov     eax, [rdx]
0x14000f50b  test    al, 2
0x14000f50d  jnz     short loc_14000F516
0x14000f50f  xor     eax, eax
0x14000f511  jmp     loc_14000F5C7
0x14000f516  mov     rcx, [rbx+8]; SecurityDescriptor
0x14000f51a  lea     r8, [rsp+48h+SecurityInformation]
0x14000f51f  lea     rdx, [rsp+48h+arg_8]
0x14000f524  call    SeUtilSecurityInfoFromSecurityDescriptor
0x14000f529  test    eax, eax
0x14000f52b  js      loc_14000F5C7
0x14000f531  mov     eax, [rsp+48h+SecurityInformation]
0x14000f535  and     al, 3
0x14000f537  neg     al
0x14000f539  lea     rax, [rsp+48h+arg_18]
0x14000f53e  sbb     ecx, ecx
0x14000f540  mov     [rsp+48h+Handle], rax; Handle
0x14000f545  mov     rax, cs:IoDeviceObjectType
0x14000f54c  and     ecx, 80000h
0x14000f552  mov     edx, ecx
0x14000f554  mov     [rsp+48h+AccessMode], 0; AccessMode
0x14000f559  bts     edx, 12h
0x14000f55d  test    byte ptr [rsp+48h+SecurityInformation], 4
0x14000f562  cmovz   edx, ecx
0x14000f565  mov     rcx, [rax]
0x14000f568  mov     r9d, edx
0x14000f56b  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x14000f570  bts     r9d, 18h
0x14000f575  mov     rcx, rsi; Object
0x14000f578  test    byte ptr [rsp+48h+SecurityInformation], 8
0x14000f57d  cmovz   r9d, edx; DesiredAccess
0x14000f581  xor     r8d, r8d; PassedAccessState
0x14000f584  mov     edx, 200h; HandleAttributes
0x14000f589  call    cs:__imp_ObOpenObjectByPointer
0x14000f590  nop     dword ptr [rax+rax+00h]
0x14000f595  test    eax, eax
0x14000f597  js      short loc_14000F5C7
0x14000f599  mov     r8, [rbx+8]; SecurityDescriptor
0x14000f59d  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x14000f5a1  mov     rcx, [rsp+48h+arg_18]; Handle
0x14000f5a6  call    cs:__imp_ZwSetSecurityObject
0x14000f5ad  nop     dword ptr [rax+rax+00h]
0x14000f5b2  mov     rcx, [rsp+48h+arg_18]; Handle
0x14000f5b7  mov     ebx, eax
0x14000f5b9  call    cs:__imp_ZwClose
0x14000f5c0  nop     dword ptr [rax+rax+00h]
0x14000f5c5  mov     eax, ebx
0x14000f5c7  mov     rbx, [rsp+48h+arg_0]
0x14000f5cc  add     rsp, 40h
0x14000f5d0  pop     rsi
0x14000f5d1  retn
```
