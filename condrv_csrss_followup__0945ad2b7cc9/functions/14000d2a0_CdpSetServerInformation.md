# CdpSetServerInformation

- ea: `0x14000d2a0`
- end: `0x14000d3d9`
- name: `CdpSetServerInformation`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000c870`

## callees

- `0x140001500`
- `0x140008128`
- `0x14000d2a0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000d384`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d384`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d354`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d354`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d3be`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d3be`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d366`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d366`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d3b2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d3b2`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14000d2db`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14000d2db`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000d33d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000d33d`
- `ntoskrnl!ExEventObjectType` at `0x14000d32b`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14000d392`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14000d392`

## pseudocode

```c
NTSTATUS __fastcall CdpSetServerInformation(__int64 a1, KPROCESSOR_MODE a2, const void *a3, int a4)
{
  NTSTATUS result; // eax
  void *ULong64FromUser; // rax
  int v8; // ebx
  PVOID v9; // rsi
  void *v10; // [rsp+38h] [rbp-40h] BYREF
  PVOID Object; // [rsp+40h] [rbp-38h] BYREF

  v10 = 0;
  if ( a4 != 8 )
    return -1073741306;
  if ( a2 )
  {
    if ( ((unsigned __int8)a3 & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    ULong64FromUser = (void *)RtlReadULong64FromUser(a3);
    v10 = ULong64FromUser;
  }
  else
  {
    RtlCopyVolatileMemory(&v10, a3, 8u);
    ULong64FromUser = v10;
  }
  Object = 0;
  result = ObReferenceObjectByHandle(ULong64FromUser, 0x100000u, (POBJECT_TYPE)ExEventObjectType, a2, &Object, 0);
  v8 = result;
  if ( result >= 0 )
  {
    v9 = Object;
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a1 + 40, 0);
    if ( *(_QWORD *)(a1 + 184) )
    {
      v8 = -1073741436;
      ObfDereferenceObject(v9);
    }
    else
    {
      *(_QWORD *)(a1 + 184) = PsGetCurrentProcessId();
      *(_QWORD *)(a1 + 192) = v9;
    }
    ExReleasePushLockExclusiveEx(a1 + 40, 0);
    KeLeaveCriticalRegion();
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x14000d2a0  mov     [rsp+arg_8], dl
0x14000d2a4  push    rbx
0x14000d2a5  push    rsi
0x14000d2a6  push    rdi
0x14000d2a7  push    r14
0x14000d2a9  sub     rsp, 58h
0x14000d2ad  mov     rax, r8
0x14000d2b0  movzx   ebx, dl
0x14000d2b3  mov     rdi, rcx
0x14000d2b6  xor     esi, esi
0x14000d2b8  mov     [rsp+78h+var_40], rsi
0x14000d2bd  cmp     r9d, 8
0x14000d2c1  jz      short loc_14000D2D3
0x14000d2c3  mov     eax, 0C0000206h
0x14000d2c8  add     rsp, 58h
0x14000d2cc  pop     r14
0x14000d2ce  pop     rdi
0x14000d2cf  pop     rsi
0x14000d2d0  pop     rbx
0x14000d2d1  retn
0x14000d2d3  test    bl, bl
0x14000d2d5  jz      short loc_14000D2FB
0x14000d2d7  test    al, 3
0x14000d2d9  jz      short loc_14000D2E8
0x14000d2db  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14000d2e2  nop     dword ptr [rax+rax+00h]
0x14000d2e7  int     3; Trap to Debugger
0x14000d2e8  test    bl, bl
0x14000d2ea  jz      short loc_14000D2FB
0x14000d2ec  mov     rcx, rax
0x14000d2ef  call    RtlReadULong64FromUser
0x14000d2f4  mov     [rsp+78h+var_40], rax
0x14000d2f9  jmp     short loc_14000D313
0x14000d2fb  mov     r8d, 8; Size
0x14000d301  mov     rdx, rax; Src
0x14000d304  lea     rcx, [rsp+78h+var_40]; void *
0x14000d309  call    RtlCopyVolatileMemory
0x14000d30e  mov     rax, [rsp+78h+var_40]
0x14000d313  mov     [rsp+78h+var_38], rsi
0x14000d318  mov     [rsp+78h+HandleInformation], rsi; HandleInformation
0x14000d31d  lea     rcx, [rsp+78h+var_38]
0x14000d322  mov     [rsp+78h+Object], rcx; Object
0x14000d327  movzx   r9d, bl; AccessMode
0x14000d32b  mov     r8, cs:ExEventObjectType
0x14000d332  mov     r8, [r8]; ObjectType
0x14000d335  mov     edx, 100000h; DesiredAccess
0x14000d33a  mov     rcx, rax; Handle
0x14000d33d  call    cs:__imp_ObReferenceObjectByHandle
0x14000d344  nop     dword ptr [rax+rax+00h]
0x14000d349  mov     ebx, eax
0x14000d34b  test    eax, eax
0x14000d34d  js      short loc_14000D3CE
0x14000d34f  mov     rsi, [rsp+78h+var_38]
0x14000d354  call    cs:__imp_KeEnterCriticalRegion
0x14000d35b  nop     dword ptr [rax+rax+00h]
0x14000d360  xor     edx, edx
0x14000d362  lea     rcx, [rdi+28h]
0x14000d366  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000d36d  nop     dword ptr [rax+rax+00h]
0x14000d372  cmp     qword ptr [rdi+0B8h], 0
0x14000d37a  jz      short loc_14000D392
0x14000d37c  mov     ebx, 0C0000184h
0x14000d381  mov     rcx, rsi; Object
0x14000d384  call    cs:__imp_ObfDereferenceObject
0x14000d38b  nop     dword ptr [rax+rax+00h]
0x14000d390  jmp     short loc_14000D3AC
0x14000d392  call    cs:__imp_PsGetCurrentProcessId
0x14000d399  nop     dword ptr [rax+rax+00h]
0x14000d39e  mov     [rdi+0B8h], rax
0x14000d3a5  mov     [rdi+0C0h], rsi
0x14000d3ac  xor     edx, edx
0x14000d3ae  lea     rcx, [rdi+28h]
0x14000d3b2  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000d3b9  nop     dword ptr [rax+rax+00h]
0x14000d3be  call    cs:__imp_KeLeaveCriticalRegion
0x14000d3c5  nop     dword ptr [rax+rax+00h]
0x14000d3ca  mov     eax, ebx
0x14000d3cc  jmp     short $+2
0x14000d3ce  add     rsp, 58h
0x14000d3d2  pop     r14
0x14000d3d4  pop     rdi
0x14000d3d5  pop     rsi
0x14000d3d6  pop     rbx
0x14000d3d7  retn
0x14000e770  push    rbp
0x14000e772  sub     rsp, 30h
0x14000e776  mov     rbp, rdx
0x14000e779  xor     eax, eax
0x14000e77b  cmp     [rbp+88h], al
0x14000e781  setnz   al
0x14000e784  mov     [rbp+30h], eax
0x14000e787  mov     eax, [rbp+30h]
0x14000e78a  add     rsp, 30h
0x14000e78e  pop     rbp
0x14000e78f  retn
```
