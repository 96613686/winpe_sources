# NpCommonSetSecurityInfo

- ea: `0x140015bf8`
- end: `0x140015f43`
- name: `NpCommonSetSecurityInfo`
- size: `843`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140015b90`

## callees

- `0x140015bf8`
- `0x140015f4c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140015d5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d5c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015d7e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015d7e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140015dc1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140015def`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140015dc1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140015def`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140015cd5`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140015cd5`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140015d16`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140015e06`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140015e18`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140015d16`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140015e06`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140015e18`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x140015eea`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x140015eea`
- `ntoskrnl!SeExports` at `0x140015edc`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x140015d48`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x140015d48`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140015cb4`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140015cb4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140015c7c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140015c7c`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140015c96`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140015c96`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x140015cfb`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x140015cfb`

## pseudocode

```c
__int64 __fastcall NpCommonSetSecurityInfo(__int64 a1, __int64 a2)
{
  __int64 v2; // r13
  __int64 v3; // r12
  __int64 v4; // rsi
  __int64 v5; // rdi
  _WORD *v6; // rcx
  __int64 v7; // r14
  PSECURITY_DESCRIPTOR *v8; // r15
  __int64 v9; // rcx
  PSECURITY_DESCRIPTOR v10; // rcx
  __int64 v11; // rcx
  void *v12; // rax
  void *v13; // rbx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  NTSTATUS v15; // ebx
  __int64 v16; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  KPROCESSOR_MODE v23; // dl
  PSECURITY_DESCRIPTOR v24; // [rsp+78h] [rbp+48h] BYREF
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+80h] [rbp+50h] BYREF
  void *v26; // [rsp+88h] [rbp+58h] BYREF

  v2 = *(_QWORD *)(a2 + 184);
  v24 = 0;
  ObjectsSecurityDescriptor = 0;
  v26 = 0;
  v3 = *(_QWORD *)(v2 + 48);
  if ( (*(_QWORD *)(v3 + 32) & 1) == 0 )
    return 3221225648LL;
  v4 = *(_QWORD *)(a1 + 64);
  v5 = 0;
  v6 = *(_WORD **)(v3 + 24);
  v7 = 0;
  if ( *v6 == 514 )
  {
    v5 = *(_QWORD *)(v3 + 24);
LABEL_4:
    v8 = (PSECURITY_DESCRIPTOR *)(v6 + 76);
    goto LABEL_5;
  }
  if ( *v6 == 515 )
  {
    v7 = *(_QWORD *)(v3 + 24);
    goto LABEL_4;
  }
  if ( *v6 != 518 )
    return 3221225485LL;
  v23 = (*(_BYTE *)(v2 + 2) & 1) != 0 ? 1 : *(_BYTE *)(a2 + 64);
  if ( !SeSinglePrivilegeCheck(SeExports->SeTcbPrivilege, v23) )
    return 3221225485LL;
  v8 = (PSECURITY_DESCRIPTOR *)(v4 + 136);
  while ( 1 )
  {
LABEL_5:
    if ( v5 )
    {
      v9 = v5 + 128;
    }
    else
    {
      v9 = v4 + 192;
      if ( !v7 )
        v9 = v4 + 128;
    }
    ExAcquirePushLockSharedEx(v9, 0);
    v10 = *v8;
    v24 = v10;
    if ( v10 )
      ObReferenceSecurityDescriptor(v10, 1);
    if ( v5 )
    {
      v11 = v5 + 128;
    }
    else
    {
      v11 = v4 + 192;
      if ( !v7 )
        v11 = v4 + 128;
    }
    ExReleasePushLockSharedEx(v11, 0);
    v12 = v24;
    if ( !v24 )
    {
      v15 = NpCreateDefaultRootSecurity(&v24);
      if ( v15 < 0 )
        return (unsigned int)v15;
      v12 = v24;
    }
    ObjectsSecurityDescriptor = v12;
    v13 = *(void **)(v2 + 16);
    GenericMapping = IoGetFileObjectGenericMapping();
    v15 = SeSetSecurityDescriptorInfo(
            0,
            (PSECURITY_INFORMATION)(v2 + 8),
            v13,
            &ObjectsSecurityDescriptor,
            PagedPool,
            GenericMapping);
    if ( v15 < 0
      || (v15 = ObLogSecurityDescriptor(ObjectsSecurityDescriptor, &v26, 1),
          ExFreePoolWithTag(ObjectsSecurityDescriptor, 0),
          v15 < 0) )
    {
      v16 = 1;
      goto LABEL_14;
    }
    if ( v5 )
    {
      v20 = v5 + 128;
    }
    else
    {
      v20 = v4 + 192;
      if ( !v7 )
        v20 = v4 + 128;
    }
    ExAcquirePushLockExclusiveEx(v20, 0, v18, v19);
    ObjectsSecurityDescriptor = *v8;
    if ( (*(_QWORD *)(v3 + 32) & 1) != 0 && (ObjectsSecurityDescriptor == v24 || !ObjectsSecurityDescriptor) )
      break;
    if ( v5 )
    {
      v22 = v5 + 128;
    }
    else
    {
      v22 = v4 + 192;
      if ( !v7 )
        v22 = v4 + 128;
    }
    ExReleasePushLockExclusiveEx(v22, 0);
    ObDereferenceSecurityDescriptor(v24, 1);
    ObDereferenceSecurityDescriptor(v26, 1);
  }
  *v8 = v26;
  if ( v5 )
  {
    v21 = v5 + 128;
  }
  else
  {
    v21 = v4 + 192;
    if ( !v7 )
      v21 = v4 + 128;
  }
  ExReleasePushLockExclusiveEx(v21, 0);
  v16 = (unsigned int)(ObjectsSecurityDescriptor != 0) + 1;
LABEL_14:
  ObDereferenceSecurityDescriptor(v24, v16);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140015bf8  mov     [rsp-38h+arg_0], rbx
0x140015bfd  push    rbp
0x140015bfe  push    rsi
0x140015bff  push    rdi
0x140015c00  push    r12
0x140015c02  push    r13
0x140015c04  push    r14
0x140015c06  push    r15
0x140015c08  mov     rbp, rsp
0x140015c0b  sub     rsp, 30h
0x140015c0f  mov     r13, [rdx+0B8h]
0x140015c16  mov     ebx, 1
0x140015c1b  mov     [rbp+arg_8], 0
0x140015c23  mov     [rbp+ObjectsSecurityDescriptor], 0
0x140015c2b  mov     [rbp+arg_18], 0
0x140015c33  mov     r12, [r13+30h]
0x140015c37  mov     rax, [r12+20h]
0x140015c3c  test    bl, al
0x140015c3e  jz      loc_140015F0F
0x140015c44  mov     rsi, [rcx+40h]
0x140015c48  xor     edi, edi
0x140015c4a  mov     rcx, [r12+18h]
0x140015c4f  xor     r14d, r14d
0x140015c52  movzx   eax, word ptr [rcx]
0x140015c55  sub     eax, 202h
0x140015c5a  jnz     loc_140015E29
0x140015c60  mov     rdi, rcx
0x140015c63  lea     r15, [rcx+98h]
0x140015c6a  test    rdi, rdi
0x140015c6d  jz      loc_140015E40
0x140015c73  lea     rcx, [rdi+80h]
0x140015c7a  xor     edx, edx
0x140015c7c  call    cs:__imp_ExAcquirePushLockSharedEx
0x140015c83  nop     dword ptr [rax+rax+00h]
0x140015c88  mov     rcx, [r15]
0x140015c8b  mov     [rbp+arg_8], rcx
0x140015c8f  test    rcx, rcx
0x140015c92  jz      short loc_140015CA2
0x140015c94  mov     edx, ebx
0x140015c96  call    cs:__imp_ObReferenceSecurityDescriptor
0x140015c9d  nop     dword ptr [rax+rax+00h]
0x140015ca2  test    rdi, rdi
0x140015ca5  jz      loc_140015E5C
0x140015cab  lea     rcx, [rdi+80h]
0x140015cb2  xor     edx, edx
0x140015cb4  call    cs:__imp_ExReleasePushLockSharedEx
0x140015cbb  nop     dword ptr [rax+rax+00h]
0x140015cc0  mov     rax, [rbp+arg_8]
0x140015cc4  test    rax, rax
0x140015cc7  jz      loc_140015EB8
0x140015ccd  mov     [rbp+ObjectsSecurityDescriptor], rax
0x140015cd1  mov     rbx, [r13+10h]
0x140015cd5  call    cs:__imp_IoGetFileObjectGenericMapping
0x140015cdc  nop     dword ptr [rax+rax+00h]
0x140015ce1  mov     [rsp+30h+GenericMapping], rax; GenericMapping
0x140015ce6  lea     rdx, [r13+8]; SecurityInformation
0x140015cea  mov     r8, rbx; ModificationDescriptor
0x140015ced  mov     [rsp+30h+PoolType], 1; PoolType
0x140015cf5  lea     r9, [rbp+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x140015cf9  xor     ecx, ecx; Object
0x140015cfb  call    cs:__imp_SeSetSecurityDescriptorInfo
0x140015d02  nop     dword ptr [rax+rax+00h]
0x140015d07  mov     ebx, eax
0x140015d09  test    eax, eax
0x140015d0b  jns     short loc_140015D3A
0x140015d0d  mov     edx, 1
0x140015d12  mov     rcx, [rbp+arg_8]
0x140015d16  call    cs:__imp_ObDereferenceSecurityDescriptor
0x140015d1d  nop     dword ptr [rax+rax+00h]
0x140015d22  mov     eax, ebx
0x140015d24  mov     rbx, [rsp+30h+arg_0]
0x140015d29  add     rsp, 30h
0x140015d2d  pop     r15
0x140015d2f  pop     r14
0x140015d31  pop     r13
0x140015d33  pop     r12
0x140015d35  pop     rdi
0x140015d36  pop     rsi
0x140015d37  pop     rbp
0x140015d38  retn
0x140015d3a  mov     rcx, [rbp+ObjectsSecurityDescriptor]
0x140015d3e  lea     rdx, [rbp+arg_18]
0x140015d42  mov     r8d, 1
0x140015d48  call    cs:__imp_ObLogSecurityDescriptor
0x140015d4f  nop     dword ptr [rax+rax+00h]
0x140015d54  mov     rcx, [rbp+ObjectsSecurityDescriptor]; P
0x140015d58  xor     edx, edx; Tag
0x140015d5a  mov     ebx, eax
0x140015d5c  call    cs:__imp_ExFreePoolWithTag
0x140015d63  nop     dword ptr [rax+rax+00h]
0x140015d68  test    ebx, ebx
0x140015d6a  js      short loc_140015D0D
0x140015d6c  test    rdi, rdi
0x140015d6f  jz      loc_140015E80
0x140015d75  lea     rcx, [rdi+80h]
0x140015d7c  xor     edx, edx
0x140015d7e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140015d85  nop     dword ptr [rax+rax+00h]
0x140015d8a  mov     rax, [r15]
0x140015d8d  mov     [rbp+ObjectsSecurityDescriptor], rax
0x140015d91  mov     rax, [r12+20h]
0x140015d96  test    al, 1
0x140015d98  jz      short loc_140015DDD
0x140015d9a  mov     rax, [rbp+ObjectsSecurityDescriptor]
0x140015d9e  cmp     rax, [rbp+arg_8]
0x140015da2  jnz     loc_140015F19
0x140015da8  mov     rax, [rbp+arg_18]
0x140015dac  mov     [r15], rax
0x140015daf  test    rdi, rdi
0x140015db2  jz      loc_140015E9C
0x140015db8  lea     rcx, [rdi+80h]
0x140015dbf  xor     edx, edx
0x140015dc1  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140015dc8  nop     dword ptr [rax+rax+00h]
0x140015dcd  xor     edx, edx
0x140015dcf  cmp     [rbp+ObjectsSecurityDescriptor], rdx
0x140015dd3  setnz   dl
0x140015dd6  inc     edx
0x140015dd8  jmp     loc_140015D12
0x140015ddd  test    rdi, rdi
0x140015de0  jz      loc_140015F27
0x140015de6  lea     rcx, [rdi+80h]
0x140015ded  xor     edx, edx
0x140015def  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140015df6  nop     dword ptr [rax+rax+00h]
0x140015dfb  mov     rcx, [rbp+arg_8]
0x140015dff  mov     ebx, 1
0x140015e04  mov     edx, ebx
0x140015e06  call    cs:__imp_ObDereferenceSecurityDescriptor
0x140015e0d  nop     dword ptr [rax+rax+00h]
0x140015e12  mov     rcx, [rbp+arg_18]
0x140015e16  mov     edx, ebx
0x140015e18  call    cs:__imp_ObDereferenceSecurityDescriptor
0x140015e1f  nop     dword ptr [rax+rax+00h]
0x140015e24  jmp     loc_140015C6A
0x140015e29  sub     eax, ebx
0x140015e2b  jz      short loc_140015E78
0x140015e2d  cmp     eax, 3
0x140015e30  jz      loc_140015ED4
0x140015e36  mov     eax, 0C000000Dh
0x140015e3b  jmp     loc_140015D24
0x140015e40  lea     rcx, [rsi+0C0h]
0x140015e47  test    r14, r14
0x140015e4a  jnz     loc_140015C7A
0x140015e50  lea     rcx, [rsi+80h]
0x140015e57  jmp     loc_140015C7A
0x140015e5c  lea     rcx, [rsi+0C0h]
0x140015e63  test    r14, r14
0x140015e66  jnz     loc_140015CB2
0x140015e6c  lea     rcx, [rsi+80h]
0x140015e73  jmp     loc_140015CB2
0x140015e78  mov     r14, rcx
0x140015e7b  jmp     loc_140015C63
0x140015e80  lea     rcx, [rsi+0C0h]
0x140015e87  test    r14, r14
0x140015e8a  jnz     loc_140015D7C
0x140015e90  lea     rcx, [rsi+80h]
0x140015e97  jmp     loc_140015D7C
0x140015e9c  lea     rcx, [rsi+0C0h]
0x140015ea3  test    r14, r14
0x140015ea6  jnz     loc_140015DBF
0x140015eac  lea     rcx, [rsi+80h]
0x140015eb3  jmp     loc_140015DBF
0x140015eb8  lea     rcx, [rbp+arg_8]
0x140015ebc  call    NpCreateDefaultRootSecurity
0x140015ec1  mov     ebx, eax
0x140015ec3  test    eax, eax
0x140015ec5  js      loc_140015D22
0x140015ecb  mov     rax, [rbp+arg_8]
0x140015ecf  jmp     loc_140015CCD
0x140015ed4  test    [r13+2], bl
0x140015ed8  jz      short loc_140015F0A
0x140015eda  mov     dl, bl; PreviousMode
0x140015edc  mov     rax, cs:__imp_SeExports
0x140015ee3  mov     rcx, [rax]
0x140015ee6  mov     rcx, [rcx+28h]; PrivilegeValue
0x140015eea  call    cs:__imp_SeSinglePrivilegeCheck
0x140015ef1  nop     dword ptr [rax+rax+00h]
0x140015ef6  test    al, al
0x140015ef8  jz      loc_140015E36
0x140015efe  lea     r15, [rsi+88h]
0x140015f05  jmp     loc_140015C6A
0x140015f0a  mov     dl, [rdx+40h]
0x140015f0d  jmp     short loc_140015EDC
0x140015f0f  mov     eax, 0C00000B0h
0x140015f14  jmp     loc_140015D24
0x140015f19  test    rax, rax
0x140015f1c  jz      loc_140015DA8
0x140015f22  jmp     loc_140015DDD
0x140015f27  lea     rcx, [rsi+0C0h]
0x140015f2e  test    r14, r14
0x140015f31  jnz     loc_140015DED
0x140015f37  lea     rcx, [rsi+80h]
0x140015f3e  jmp     loc_140015DED
```
