# NpCommonQuerySecurityInfo

- ea: `0x140014170`
- end: `0x140014365`
- name: `NpCommonQuerySecurityInfo`
- size: `501`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140014100`

## callees

- `0x140014170`

## import_xrefs

- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14001426a`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14001426a`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x1400141d9`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x1400141d9`
- `ntoskrnl!SeExports` at `0x1400141cb`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14001422d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400142c8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14001422d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400142c8`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400141f6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400142ab`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400142f6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400141f6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400142ab`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400142f6`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x14001424d`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x14001424d`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140014218`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140014313`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x14001434d`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140014218`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140014313`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x14001434d`

## pseudocode

```c
__int64 __fastcall NpCommonQuerySecurityInfo(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v4; // rdi
  __int64 v5; // rbp
  unsigned __int16 *v6; // r14
  int v7; // ecx
  KPROCESSOR_MODE v8; // dl
  void *v9; // rcx
  unsigned __int16 *v10; // rcx
  unsigned int *v11; // rdi
  unsigned int v12; // ebx
  int v14; // ecx
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+48h] [rbp+10h] BYREF

  v2 = *(_QWORD *)(a2 + 184);
  ObjectsSecurityDescriptor = 0;
  v4 = *(_QWORD *)(v2 + 48);
  if ( (*(_QWORD *)(v4 + 32) & 1) == 0 )
    return 3221225648LL;
  v5 = *(_QWORD *)(a1 + 64);
  v6 = *(unsigned __int16 **)(v4 + 24);
  v7 = *v6;
  if ( v7 == 518 )
  {
    if ( (*(_BYTE *)(v2 + 2) & 1) != 0 )
      v8 = 1;
    else
      v8 = *(_BYTE *)(a2 + 64);
    if ( SeSinglePrivilegeCheck(SeExports->SeTcbPrivilege, v8) )
    {
      ExAcquirePushLockSharedEx(v5 + 128, 0);
      v9 = *(void **)(v5 + 136);
      ObjectsSecurityDescriptor = v9;
      if ( v9 )
        ObReferenceSecurityDescriptor(v9, 1);
      v10 = (unsigned __int16 *)(v5 + 128);
      goto LABEL_9;
    }
    return 3221225485LL;
  }
  v14 = v7 - 514;
  if ( !v14 )
  {
    ExAcquirePushLockSharedEx(v6 + 64, 0);
    if ( (*(_QWORD *)(v4 + 32) & 1) == 0 )
    {
      ExReleasePushLockSharedEx(v6 + 64, 0);
      return 3221225648LL;
    }
    ObjectsSecurityDescriptor = (PSECURITY_DESCRIPTOR)*((_QWORD *)v6 + 19);
    ObReferenceSecurityDescriptor(ObjectsSecurityDescriptor, 1);
    v10 = v6 + 64;
    goto LABEL_9;
  }
  if ( v14 != 1 )
    return 3221225485LL;
  ExAcquirePushLockSharedEx(v5 + 192, 0);
  ObjectsSecurityDescriptor = (PSECURITY_DESCRIPTOR)*((_QWORD *)v6 + 19);
  ObReferenceSecurityDescriptor(ObjectsSecurityDescriptor, 1);
  v10 = (unsigned __int16 *)(v5 + 192);
LABEL_9:
  ExReleasePushLockSharedEx(v10, 0);
  v11 = (unsigned int *)(v2 + 16);
  v12 = SeQuerySecurityDescriptorInfo(
          (PSECURITY_INFORMATION)(v2 + 8),
          *(PSECURITY_DESCRIPTOR *)(a2 + 112),
          (PULONG)(v2 + 16),
          &ObjectsSecurityDescriptor);
  if ( ObjectsSecurityDescriptor )
    ObDereferenceSecurityDescriptor(ObjectsSecurityDescriptor, 1);
  if ( v12 == -1073741789 )
  {
    v12 = -2147483643;
    *(_QWORD *)(a2 + 56) = *v11;
  }
  return v12;
}

```

## disassembly

```asm
0x140014170  push    rbx
0x140014172  push    rsi
0x140014173  push    rdi
0x140014174  sub     rsp, 20h
0x140014178  mov     rbx, [rdx+0B8h]
0x14001417f  mov     rsi, rdx
0x140014182  mov     [rsp+38h+ObjectsSecurityDescriptor], 0
0x14001418b  mov     rdi, [rbx+30h]
0x14001418f  mov     rax, [rdi+20h]
0x140014193  test    al, 1
0x140014195  jz      loc_140014332
0x14001419b  mov     [rsp+38h+arg_0], rbp
0x1400141a0  mov     rbp, [rcx+40h]
0x1400141a4  mov     [rsp+38h+arg_10], r14
0x1400141a9  mov     r14, [rdi+18h]
0x1400141ad  movzx   ecx, word ptr [r14]
0x1400141b1  cmp     ecx, 206h
0x1400141b7  jnz     loc_14001429A
0x1400141bd  test    byte ptr [rbx+2], 1
0x1400141c1  jnz     loc_14001432B
0x1400141c7  movzx   edx, byte ptr [rdx+40h]; PreviousMode
0x1400141cb  mov     rax, cs:__imp_SeExports
0x1400141d2  mov     rcx, [rax]
0x1400141d5  mov     rcx, [rcx+28h]; PrivilegeValue
0x1400141d9  call    cs:__imp_SeSinglePrivilegeCheck
0x1400141e0  nop     dword ptr [rax+rax+00h]
0x1400141e5  test    al, al
0x1400141e7  jz      loc_140014293
0x1400141ed  xor     edx, edx
0x1400141ef  lea     rcx, [rbp+80h]
0x1400141f6  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400141fd  nop     dword ptr [rax+rax+00h]
0x140014202  mov     rcx, [rbp+88h]
0x140014209  mov     [rsp+38h+ObjectsSecurityDescriptor], rcx
0x14001420e  test    rcx, rcx
0x140014211  jz      short loc_140014224
0x140014213  mov     edx, 1
0x140014218  call    cs:__imp_ObReferenceSecurityDescriptor
0x14001421f  nop     dword ptr [rax+rax+00h]
0x140014224  lea     rcx, [rbp+80h]
0x14001422b  xor     edx, edx
0x14001422d  call    cs:__imp_ExReleasePushLockSharedEx
0x140014234  nop     dword ptr [rax+rax+00h]
0x140014239  mov     rdx, [rsi+70h]; SecurityDescriptor
0x14001423d  lea     rdi, [rbx+10h]
0x140014241  mov     r8, rdi; Length
0x140014244  lea     rcx, [rbx+8]; SecurityInformation
0x140014248  lea     r9, [rsp+38h+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x14001424d  call    cs:__imp_SeQuerySecurityDescriptorInfo
0x140014254  nop     dword ptr [rax+rax+00h]
0x140014259  mov     rcx, [rsp+38h+ObjectsSecurityDescriptor]
0x14001425e  mov     ebx, eax
0x140014260  test    rcx, rcx
0x140014263  jz      short loc_140014276
0x140014265  mov     edx, 1
0x14001426a  call    cs:__imp_ObDereferenceSecurityDescriptor
0x140014271  nop     dword ptr [rax+rax+00h]
0x140014276  cmp     ebx, 0C0000023h
0x14001427c  jz      short loc_1400142DB
0x14001427e  mov     eax, ebx
0x140014280  mov     rbp, [rsp+38h+arg_0]
0x140014285  mov     r14, [rsp+38h+arg_10]
0x14001428a  add     rsp, 20h
0x14001428e  pop     rdi
0x14001428f  pop     rsi
0x140014290  pop     rbx
0x140014291  retn
0x140014293  mov     eax, 0C000000Dh
0x140014298  jmp     short loc_140014280
0x14001429a  sub     ecx, 202h
0x1400142a0  jnz     short loc_1400142E8
0x1400142a2  xor     edx, edx
0x1400142a4  lea     rcx, [r14+80h]
0x1400142ab  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400142b2  nop     dword ptr [rax+rax+00h]
0x1400142b7  mov     rax, [rdi+20h]
0x1400142bb  test    al, 1
0x1400142bd  jnz     short loc_14001433C
0x1400142bf  xor     edx, edx
0x1400142c1  lea     rcx, [r14+80h]
0x1400142c8  call    cs:__imp_ExReleasePushLockSharedEx
0x1400142cf  nop     dword ptr [rax+rax+00h]
0x1400142d4  mov     eax, 0C00000B0h
0x1400142d9  jmp     short loc_140014280
0x1400142db  mov     eax, [rdi]
0x1400142dd  mov     ebx, 80000005h
0x1400142e2  mov     [rsi+38h], rax
0x1400142e6  jmp     short loc_14001427E
0x1400142e8  cmp     ecx, 1
0x1400142eb  jnz     short loc_140014293
0x1400142ed  xor     edx, edx
0x1400142ef  lea     rcx, [rbp+0C0h]
0x1400142f6  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400142fd  nop     dword ptr [rax+rax+00h]
0x140014302  mov     rcx, [r14+98h]
0x140014309  mov     edx, 1
0x14001430e  mov     [rsp+38h+ObjectsSecurityDescriptor], rcx
0x140014313  call    cs:__imp_ObReferenceSecurityDescriptor
0x14001431a  nop     dword ptr [rax+rax+00h]
0x14001431f  lea     rcx, [rbp+0C0h]
0x140014326  jmp     loc_14001422B
0x14001432b  mov     dl, 1
0x14001432d  jmp     loc_1400141CB
0x140014332  mov     eax, 0C00000B0h
0x140014337  jmp     loc_14001428A
0x14001433c  mov     rcx, [r14+98h]
0x140014343  mov     edx, 1
0x140014348  mov     [rsp+38h+ObjectsSecurityDescriptor], rcx
0x14001434d  call    cs:__imp_ObReferenceSecurityDescriptor
0x140014354  nop     dword ptr [rax+rax+00h]
0x140014359  lea     rcx, [r14+80h]
0x140014360  jmp     loc_14001422B
```
