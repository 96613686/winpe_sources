# IopDevObjApplyPostCreationSettings

- ea: `0x1400851d4`
- end: `0x1400852c3`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140085040`

## callees

- `0x1400851d4`
- `0x1400862ac`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x140085279`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140085279`
- `ntoskrnl!IoDeviceObjectType` at `0x140085235`
- `ntoskrnl!ZwSetSecurityObject` at `0x140085296`
- `ntoskrnl!ZwSetSecurityObject` at `0x140085296`
- `ntoskrnl!ZwClose` at `0x1400852a9`
- `ntoskrnl!ZwClose` at `0x1400852a9`

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
0x1400851d4  mov     rax, rsp
0x1400851d7  mov     [rax+8], rbx
0x1400851db  push    rsi
0x1400851dc  sub     rsp, 40h
0x1400851e0  mov     dword ptr [rax+18h], 0
0x1400851e7  mov     rbx, rdx
0x1400851ea  mov     byte ptr [rax+10h], 0
0x1400851ee  mov     rsi, rcx
0x1400851f1  mov     qword ptr [rax+20h], 0
0x1400851f9  mov     eax, [rdx]
0x1400851fb  test    al, 2
0x1400851fd  jnz     short loc_140085206
0x1400851ff  xor     eax, eax
0x140085201  jmp     loc_1400852B7
0x140085206  mov     rcx, [rbx+8]; SecurityDescriptor
0x14008520a  lea     r8, [rsp+48h+SecurityInformation]
0x14008520f  lea     rdx, [rsp+48h+arg_8]
0x140085214  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140085219  test    eax, eax
0x14008521b  js      loc_1400852B7
0x140085221  mov     eax, [rsp+48h+SecurityInformation]
0x140085225  and     al, 3
0x140085227  neg     al
0x140085229  lea     rax, [rsp+48h+arg_18]
0x14008522e  sbb     ecx, ecx
0x140085230  mov     [rsp+48h+Handle], rax; Handle
0x140085235  mov     rax, cs:IoDeviceObjectType
0x14008523c  and     ecx, 80000h
0x140085242  mov     edx, ecx
0x140085244  mov     [rsp+48h+AccessMode], 0; AccessMode
0x140085249  bts     edx, 12h
0x14008524d  test    byte ptr [rsp+48h+SecurityInformation], 4
0x140085252  cmovz   edx, ecx
0x140085255  mov     rcx, [rax]
0x140085258  mov     r9d, edx
0x14008525b  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x140085260  bts     r9d, 18h
0x140085265  mov     rcx, rsi; Object
0x140085268  test    byte ptr [rsp+48h+SecurityInformation], 8
0x14008526d  cmovz   r9d, edx; DesiredAccess
0x140085271  xor     r8d, r8d; PassedAccessState
0x140085274  mov     edx, 200h; HandleAttributes
0x140085279  call    cs:__imp_ObOpenObjectByPointer
0x140085280  nop     dword ptr [rax+rax+00h]
0x140085285  test    eax, eax
0x140085287  js      short loc_1400852B7
0x140085289  mov     r8, [rbx+8]; SecurityDescriptor
0x14008528d  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x140085291  mov     rcx, [rsp+48h+arg_18]; Handle
0x140085296  call    cs:__imp_ZwSetSecurityObject
0x14008529d  nop     dword ptr [rax+rax+00h]
0x1400852a2  mov     rcx, [rsp+48h+arg_18]; Handle
0x1400852a7  mov     ebx, eax
0x1400852a9  call    cs:__imp_ZwClose
0x1400852b0  nop     dword ptr [rax+rax+00h]
0x1400852b5  mov     eax, ebx
0x1400852b7  mov     rbx, [rsp+48h+arg_0]
0x1400852bc  add     rsp, 40h
0x1400852c0  pop     rsi
0x1400852c1  retn
```
