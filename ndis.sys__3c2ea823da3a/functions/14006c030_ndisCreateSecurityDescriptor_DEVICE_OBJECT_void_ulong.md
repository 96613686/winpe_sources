# ndisCreateSecurityDescriptor(_DEVICE_OBJECT *,void * *,ulong)

- ea: `0x14006c030`
- end: `0x14006c20d`
- name: `?ndisCreateSecurityDescriptor@@YAJPEAU_DEVICE_OBJECT@@PEAPEAXK@Z`
- size: `477`
- prototype: `int(struct _DEVICE_OBJECT *, void **, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14017f260`
- `0x14018ca88`

## callees

- `0x14006c030`
- `0x14006c220`
- `0x1400e6160`
- `0x1400e62c0`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14006c13c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14006c13c`
- `ntoskrnl!ObGetObjectSecurity` at `0x14006c078`
- `ntoskrnl!ObGetObjectSecurity` at `0x14006c078`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14006c0e5`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14006c0e5`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14006c1a8`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14006c1a8`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14006c0cc`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14006c0cc`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14006c0f6`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14006c0f6`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x14006c164`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x14006c164`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c184`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c1e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c1ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c184`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c1e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c1ff`
- `ntoskrnl!ExAllocatePool2` at `0x14006c111`
- `ntoskrnl!ExAllocatePool2` at `0x14006c111`

## pseudocode

```c
NTSTATUS __fastcall ndisCreateSecurityDescriptor(struct _DEVICE_OBJECT *a1, void **a2, char a3)
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
0x14006c030  push    rbx
0x14006c032  push    rsi
0x14006c033  push    r14
0x14006c035  sub     rsp, 80h
0x14006c03c  mov     rax, cs:__security_cookie
0x14006c043  xor     rax, rsp
0x14006c046  mov     [rsp+98h+var_20], rax
0x14006c04b  xor     r14d, r14d
0x14006c04e  mov     [rsp+98h+SecurityInformation], 4
0x14006c056  mov     [rdx], r14
0x14006c059  mov     ebx, r8d
0x14006c05c  mov     rsi, rdx
0x14006c05f  mov     [rsp+98h+Dacl], r14
0x14006c064  lea     rdx, [rsp+98h+SecurityDescriptor]; SecurityDescriptor
0x14006c069  mov     [rsp+98h+MemoryAllocated], r14b
0x14006c06e  lea     r8, [rsp+98h+MemoryAllocated]; MemoryAllocated
0x14006c073  mov     [rsp+98h+SecurityDescriptor], r14
0x14006c078  call    cs:__imp_ObGetObjectSecurity
0x14006c07f  nop     dword ptr [rax+rax+00h]
0x14006c084  test    eax, eax
0x14006c086  js      loc_14006C1C3
0x14006c08c  cmp     [rsp+98h+SecurityDescriptor], r14
0x14006c091  jz      loc_14006C1C3
0x14006c097  mov     edx, ebx; unsigned int
0x14006c099  mov     [rsp+98h+arg_18], rdi
0x14006c0a1  lea     rcx, [rsp+98h+Dacl]; struct _ACL **
0x14006c0a6  call    ?ndisBuildDeviceAcl@@YAJPEAPEAU_ACL@@K@Z; ndisBuildDeviceAcl(_ACL * *,ulong)
0x14006c0ab  mov     rdi, [rsp+98h+Dacl]
0x14006c0b0  mov     ebx, eax
0x14006c0b2  test    eax, eax
0x14006c0b4  js      loc_14006C19E
0x14006c0ba  mov     edx, 1; Revision
0x14006c0bf  mov     [rsp+98h+arg_10], rbp
0x14006c0c7  lea     rcx, [rsp+98h+ModificationDescriptor]; SecurityDescriptor
0x14006c0cc  call    cs:__imp_RtlCreateSecurityDescriptor
0x14006c0d3  nop     dword ptr [rax+rax+00h]
0x14006c0d8  xor     r9d, r9d; DaclDefaulted
0x14006c0db  lea     rcx, [rsp+98h+ModificationDescriptor]; SecurityDescriptor
0x14006c0e0  mov     r8, rdi; Dacl
0x14006c0e3  mov     dl, 1; DaclPresent
0x14006c0e5  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14006c0ec  nop     dword ptr [rax+rax+00h]
0x14006c0f1  mov     rcx, [rsp+98h+SecurityDescriptor]; SecurityDescriptor
0x14006c0f6  call    cs:__imp_RtlLengthSecurityDescriptor
0x14006c0fd  nop     dword ptr [rax+rax+00h]
0x14006c102  mov     edx, eax
0x14006c104  mov     r8d, 6573444Eh
0x14006c10a  mov     ecx, 42h ; 'B'
0x14006c10f  mov     ebx, eax
0x14006c111  call    cs:__imp_ExAllocatePool2
0x14006c118  nop     dword ptr [rax+rax+00h]
0x14006c11d  mov     rbp, rax
0x14006c120  test    rax, rax
0x14006c123  jz      loc_14006C1DD
0x14006c129  mov     rdx, [rsp+98h+SecurityDescriptor]; Src
0x14006c12e  mov     r8d, ebx; Size
0x14006c131  mov     rcx, rax; void *
0x14006c134  call    memmove
0x14006c139  mov     [rsi], rbp
0x14006c13c  call    cs:__imp_IoGetFileObjectGenericMapping
0x14006c143  nop     dword ptr [rax+rax+00h]
0x14006c148  mov     [rsp+98h+GenericMapping], rax; GenericMapping
0x14006c14d  mov     r9, rsi; ObjectsSecurityDescriptor
0x14006c150  lea     r8, [rsp+98h+ModificationDescriptor]; ModificationDescriptor
0x14006c155  mov     [rsp+98h+PoolType], 200h; PoolType
0x14006c15d  lea     rdx, [rsp+98h+SecurityInformation]; SecurityInformation
0x14006c162  xor     ecx, ecx; Object
0x14006c164  call    cs:__imp_SeSetSecurityDescriptorInfo
0x14006c16b  nop     dword ptr [rax+rax+00h]
0x14006c170  mov     ebx, eax
0x14006c172  test    eax, eax
0x14006c174  js      short loc_14006C1E4
0x14006c176  cmp     [rsi], rbp
0x14006c179  jz      loc_1400EE6FA
0x14006c17f  xor     edx, edx; Tag
0x14006c181  mov     rcx, rbp; P
0x14006c184  call    cs:__imp_ExFreePoolWithTag
0x14006c18b  nop     dword ptr [rax+rax+00h]
0x14006c190  nop
0x14006c191  jmp     loc_1400EE6FA
0x14006c196  mov     rbp, [rsp+98h+arg_10]
0x14006c19e  movzx   edx, [rsp+98h+MemoryAllocated]; MemoryAllocated
0x14006c1a3  mov     rcx, [rsp+98h+SecurityDescriptor]; SecurityDescriptor
0x14006c1a8  call    cs:__imp_ObReleaseObjectSecurity
0x14006c1af  nop     dword ptr [rax+rax+00h]
0x14006c1b4  test    rdi, rdi
0x14006c1b7  jnz     short loc_14006C1FA
0x14006c1b9  mov     rdi, [rsp+98h+arg_18]
0x14006c1c1  mov     eax, ebx
0x14006c1c3  mov     rcx, [rsp+98h+var_20]
0x14006c1c8  xor     rcx, rsp; StackCookie
0x14006c1cb  call    __security_check_cookie
0x14006c1d0  add     rsp, 80h
0x14006c1d7  pop     r14
0x14006c1d9  pop     rsi
0x14006c1da  pop     rbx
0x14006c1db  retn
0x14006c1dd  mov     ebx, 0C000009Ah
0x14006c1e2  jmp     short loc_14006C196
0x14006c1e4  mov     rcx, [rsi]; P
0x14006c1e7  xor     edx, edx; Tag
0x14006c1e9  call    cs:__imp_ExFreePoolWithTag
0x14006c1f0  nop     dword ptr [rax+rax+00h]
0x14006c1f5  mov     [rsi], r14
0x14006c1f8  jmp     short loc_14006C196
0x14006c1fa  xor     edx, edx; Tag
0x14006c1fc  mov     rcx, rdi; P
0x14006c1ff  call    cs:__imp_ExFreePoolWithTag
0x14006c206  nop     dword ptr [rax+rax+00h]
0x14006c20b  jmp     short loc_14006C1B9
0x1400ee6fa  mov     ebx, r14d
0x1400ee6fd  jmp     loc_14006C196
```
