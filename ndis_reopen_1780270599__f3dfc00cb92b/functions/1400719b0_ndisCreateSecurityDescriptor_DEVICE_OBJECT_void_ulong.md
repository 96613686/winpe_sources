# ndisCreateSecurityDescriptor(_DEVICE_OBJECT *,void * *,ulong)

- ea: `0x1400719b0`
- end: `0x140071b8d`
- name: `?ndisCreateSecurityDescriptor@@YAJPEAU_DEVICE_OBJECT@@PEAPEAXK@Z`
- size: `477`
- prototype: `NTSTATUS __fastcall(struct _DEVICE_OBJECT *, void **, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140185810`
- `0x140192a98`

## callees

- `0x1400719b0`
- `0x140071ba0`
- `0x1400eb380`
- `0x1400eb4c0`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140071abc`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140071abc`
- `ntoskrnl!ObGetObjectSecurity` at `0x1400719f8`
- `ntoskrnl!ObGetObjectSecurity` at `0x1400719f8`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140071a65`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140071a65`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140071b28`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140071b28`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140071a4c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140071a4c`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140071a76`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140071a76`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x140071ae4`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x140071ae4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071b04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071b69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071b7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071b04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071b69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071b7f`
- `ntoskrnl!ExAllocatePool2` at `0x140071a91`
- `ntoskrnl!ExAllocatePool2` at `0x140071a91`

## pseudocode

```c
NTSTATUS __fastcall ndisCreateSecurityDescriptor(struct _DEVICE_OBJECT *a1, void **a2, unsigned int a3)
{
  NTSTATUS result; // eax
  int v6; // eax
  struct _ACL *v7; // rdi
  NTSTATUS v8; // ebx
  ULONG v9; // ebx
  void *Pool2; // rax
  void *v11; // rbp
  struct _GENERIC_MAPPING *GenericMapping; // rax
  unsigned __int8 MemoryAllocated[8]; // [rsp+30h] [rbp-68h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-60h] BYREF
  DWORD SecurityInformation; // [rsp+40h] [rbp-58h] BYREF
  PACL Dacl; // [rsp+48h] [rbp-50h] BYREF
  _BYTE ModificationDescriptor[40]; // [rsp+50h] [rbp-48h] BYREF

  SecurityInformation = 4;
  *a2 = 0;
  Dacl = 0;
  MemoryAllocated[0] = 0;
  SecurityDescriptor = 0;
  result = ObGetObjectSecurity(a1, &SecurityDescriptor, MemoryAllocated);
  if ( result >= 0 && SecurityDescriptor )
  {
    v6 = ndisBuildDeviceAcl(&Dacl, a3);
    v7 = Dacl;
    v8 = v6;
    if ( v6 >= 0 )
    {
      RtlCreateSecurityDescriptor(ModificationDescriptor, 1u);
      RtlSetDaclSecurityDescriptor(ModificationDescriptor, 1u, v7, 0);
      v9 = RtlLengthSecurityDescriptor(SecurityDescriptor);
      Pool2 = (void *)ExAllocatePool2(66, v9, 1702052942);
      v11 = Pool2;
      if ( Pool2 )
      {
        memmove(Pool2, SecurityDescriptor, v9);
        *a2 = v11;
        GenericMapping = IoGetFileObjectGenericMapping();
        v8 = SeSetSecurityDescriptorInfo(
               0,
               &SecurityInformation,
               ModificationDescriptor,
               a2,
               NonPagedPoolNx,
               GenericMapping);
        if ( v8 < 0 )
        {
          ExFreePoolWithTag(*a2, 0);
          *a2 = 0;
        }
        else
        {
          if ( *a2 != v11 )
            ExFreePoolWithTag(v11, 0);
          v8 = 0;
        }
      }
      else
      {
        v8 = -1073741670;
      }
    }
    ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated[0]);
    if ( v7 )
      ExFreePoolWithTag(v7, 0);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x1400719b0  push    rbx
0x1400719b2  push    rsi
0x1400719b3  push    r14
0x1400719b5  sub     rsp, 80h
0x1400719bc  mov     rax, cs:__security_cookie
0x1400719c3  xor     rax, rsp
0x1400719c6  mov     [rsp+98h+var_20], rax
0x1400719cb  xor     r14d, r14d
0x1400719ce  mov     [rsp+98h+SecurityInformation], 4
0x1400719d6  mov     [rdx], r14
0x1400719d9  mov     ebx, r8d
0x1400719dc  mov     rsi, rdx
0x1400719df  mov     [rsp+98h+Dacl], r14
0x1400719e4  lea     rdx, [rsp+98h+SecurityDescriptor]; SecurityDescriptor
0x1400719e9  mov     [rsp+98h+MemoryAllocated], r14b
0x1400719ee  lea     r8, [rsp+98h+MemoryAllocated]; MemoryAllocated
0x1400719f3  mov     [rsp+98h+SecurityDescriptor], r14
0x1400719f8  call    cs:__imp_ObGetObjectSecurity
0x1400719ff  nop     dword ptr [rax+rax+00h]
0x140071a04  test    eax, eax
0x140071a06  js      loc_140071B43
0x140071a0c  cmp     [rsp+98h+SecurityDescriptor], r14
0x140071a11  jz      loc_140071B43
0x140071a17  mov     edx, ebx; unsigned int
0x140071a19  mov     [rsp+98h+arg_18], rdi
0x140071a21  lea     rcx, [rsp+98h+Dacl]; struct _ACL **
0x140071a26  call    ?ndisBuildDeviceAcl@@YAJPEAPEAU_ACL@@K@Z; ndisBuildDeviceAcl(_ACL * *,ulong)
0x140071a2b  mov     rdi, [rsp+98h+Dacl]
0x140071a30  mov     ebx, eax
0x140071a32  test    eax, eax
0x140071a34  js      loc_140071B1E
0x140071a3a  mov     edx, 1; Revision
0x140071a3f  mov     [rsp+98h+arg_10], rbp
0x140071a47  lea     rcx, [rsp+98h+ModificationDescriptor]; SecurityDescriptor
0x140071a4c  call    cs:__imp_RtlCreateSecurityDescriptor
0x140071a53  nop     dword ptr [rax+rax+00h]
0x140071a58  xor     r9d, r9d; DaclDefaulted
0x140071a5b  lea     rcx, [rsp+98h+ModificationDescriptor]; SecurityDescriptor
0x140071a60  mov     r8, rdi; Dacl
0x140071a63  mov     dl, 1; DaclPresent
0x140071a65  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140071a6c  nop     dword ptr [rax+rax+00h]
0x140071a71  mov     rcx, [rsp+98h+SecurityDescriptor]; SecurityDescriptor
0x140071a76  call    cs:__imp_RtlLengthSecurityDescriptor
0x140071a7d  nop     dword ptr [rax+rax+00h]
0x140071a82  mov     edx, eax
0x140071a84  mov     r8d, 6573444Eh
0x140071a8a  mov     ecx, 42h ; 'B'
0x140071a8f  mov     ebx, eax
0x140071a91  call    cs:__imp_ExAllocatePool2
0x140071a98  nop     dword ptr [rax+rax+00h]
0x140071a9d  mov     rbp, rax
0x140071aa0  test    rax, rax
0x140071aa3  jz      loc_140071B5D
0x140071aa9  mov     rdx, [rsp+98h+SecurityDescriptor]; Src
0x140071aae  mov     r8d, ebx; Size
0x140071ab1  mov     rcx, rax; void *
0x140071ab4  call    memmove
0x140071ab9  mov     [rsi], rbp
0x140071abc  call    cs:__imp_IoGetFileObjectGenericMapping
0x140071ac3  nop     dword ptr [rax+rax+00h]
0x140071ac8  mov     [rsp+98h+GenericMapping], rax; GenericMapping
0x140071acd  mov     r9, rsi; ObjectsSecurityDescriptor
0x140071ad0  lea     r8, [rsp+98h+ModificationDescriptor]; ModificationDescriptor
0x140071ad5  mov     [rsp+98h+PoolType], 200h; PoolType
0x140071add  lea     rdx, [rsp+98h+SecurityInformation]; SecurityInformation
0x140071ae2  xor     ecx, ecx; Object
0x140071ae4  call    cs:__imp_SeSetSecurityDescriptorInfo
0x140071aeb  nop     dword ptr [rax+rax+00h]
0x140071af0  mov     ebx, eax
0x140071af2  test    eax, eax
0x140071af4  js      short loc_140071B64
0x140071af6  cmp     [rsi], rbp
0x140071af9  jz      loc_1400F3A16
0x140071aff  xor     edx, edx; Tag
0x140071b01  mov     rcx, rbp; P
0x140071b04  call    cs:__imp_ExFreePoolWithTag
0x140071b0b  nop     dword ptr [rax+rax+00h]
0x140071b10  nop
0x140071b11  jmp     loc_1400F3A16
0x140071b16  mov     rbp, [rsp+98h+arg_10]
0x140071b1e  movzx   edx, [rsp+98h+MemoryAllocated]; MemoryAllocated
0x140071b23  mov     rcx, [rsp+98h+SecurityDescriptor]; SecurityDescriptor
0x140071b28  call    cs:__imp_ObReleaseObjectSecurity
0x140071b2f  nop     dword ptr [rax+rax+00h]
0x140071b34  test    rdi, rdi
0x140071b37  jnz     short loc_140071B7A
0x140071b39  mov     rdi, [rsp+98h+arg_18]
0x140071b41  mov     eax, ebx
0x140071b43  mov     rcx, [rsp+98h+var_20]
0x140071b48  xor     rcx, rsp; StackCookie
0x140071b4b  call    __security_check_cookie
0x140071b50  add     rsp, 80h
0x140071b57  pop     r14
0x140071b59  pop     rsi
0x140071b5a  pop     rbx
0x140071b5b  retn
0x140071b5d  mov     ebx, 0C000009Ah
0x140071b62  jmp     short loc_140071B16
0x140071b64  mov     rcx, [rsi]; P
0x140071b67  xor     edx, edx; Tag
0x140071b69  call    cs:__imp_ExFreePoolWithTag
0x140071b70  nop     dword ptr [rax+rax+00h]
0x140071b75  mov     [rsi], r14
0x140071b78  jmp     short loc_140071B16
0x140071b7a  xor     edx, edx; Tag
0x140071b7c  mov     rcx, rdi; P
0x140071b7f  call    cs:__imp_ExFreePoolWithTag
0x140071b86  nop     dword ptr [rax+rax+00h]
0x140071b8b  jmp     short loc_140071B39
0x1400f3a16  mov     ebx, r14d
0x1400f3a19  jmp     loc_140071B16
```
