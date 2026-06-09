# BlAllocateSecurityDescriptor

- ea: `0x14009a238`
- end: `0x14009a3a1`
- name: `BlAllocateSecurityDescriptor`
- size: `361`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400ed058`
- `0x1400edc18`

## callees

- `0x1400219a0`
- `0x140021a00`
- `0x140082f00`
- `0x14009a238`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14009a306`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14009a33e`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14009a306`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14009a33e`
- `ntoskrnl!IoDeleteDevice` at `0x14009a382`
- `ntoskrnl!IoDeleteDevice` at `0x14009a382`
- `ntoskrnl!ObGetObjectSecurity` at `0x14009a2f0`
- `ntoskrnl!ObGetObjectSecurity` at `0x14009a2f0`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14009a365`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14009a365`
- `ntoskrnl!ExAllocatePool2` at `0x14009a31f`
- `ntoskrnl!ExAllocatePool2` at `0x14009a31f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009a282`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009a282`

## string_xrefs

- `0x14009a269`: `\Device\BitLocker_Temp`

## pseudocode

```c
__int64 __fastcall BlAllocateSecurityDescriptor(__int64 a1, __int64 a2, void **a3, int a4)
{
  NTSTATUS ObjectSecurity; // ebx
  ULONG v8; // eax
  __int64 Pool2; // rax
  ULONG v10; // eax
  PVOID Object; // [rsp+50h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-18h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+A0h] [rbp+30h] BYREF
  int MemoryAllocated; // [rsp+A8h] [rbp+38h] BYREF

  MemoryAllocated = a4;
  Object = 0;
  SecurityDescriptor = 0;
  LOBYTE(MemoryAllocated) = 0;
  *a3 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\BitLocker_Temp");
  if ( !WdmlibInitialized )
    WdmlibInit();
  ObjectSecurity = ((__int64 (__fastcall *)(__int64, _QWORD, struct _UNICODE_STRING *, __int64, int, _BYTE, __int64, __int64 *, PVOID *))PfnIoCreateDeviceSecure)(
                     a1,
                     0,
                     &DestinationString,
                     34,
                     256,
                     0,
                     a2,
                     BTLCKR_TMP_GUID,
                     &Object);
  if ( ObjectSecurity >= 0 )
  {
    ObjectSecurity = ObGetObjectSecurity(Object, &SecurityDescriptor, (PBOOLEAN)&MemoryAllocated);
    if ( ObjectSecurity >= 0 )
    {
      v8 = RtlLengthSecurityDescriptor(SecurityDescriptor);
      Pool2 = ExAllocatePool2(256, v8, 809850438);
      *a3 = (void *)Pool2;
      if ( Pool2 )
      {
        v10 = RtlLengthSecurityDescriptor(SecurityDescriptor);
        memmove(*a3, SecurityDescriptor, v10);
      }
      else
      {
        ObjectSecurity = -1073741670;
      }
    }
  }
  if ( SecurityDescriptor )
  {
    ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated);
    SecurityDescriptor = 0;
  }
  if ( Object )
    IoDeleteDevice((PDEVICE_OBJECT)Object);
  return (unsigned int)ObjectSecurity;
}

```

## disassembly

```asm
0x14009a238  mov     [rsp-18h+arg_0], rbx
0x14009a23d  mov     [rsp-18h+MemoryAllocated], r9d
0x14009a242  push    rbp
0x14009a243  push    rsi
0x14009a244  push    rdi
0x14009a245  mov     rbp, rsp
0x14009a248  sub     rsp, 70h
0x14009a24c  mov     rbx, rdx
0x14009a24f  mov     [rbp+Object], 0
0x14009a257  mov     rsi, rcx
0x14009a25a  mov     [rbp+SecurityDescriptor], 0
0x14009a262  xorps   xmm0, xmm0
0x14009a265  mov     byte ptr [rbp+MemoryAllocated], 0
0x14009a269  lea     rdx, aDeviceBitlocke; "\\Device\\BitLocker_Temp"
0x14009a270  mov     qword ptr [r8], 0
0x14009a277  lea     rcx, [rbp+DestinationString]; DestinationString
0x14009a27b  mov     rdi, r8
0x14009a27e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14009a282  call    cs:__imp_RtlInitUnicodeString
0x14009a289  nop     dword ptr [rax+rax+00h]
0x14009a28e  cmp     cs:WdmlibInitialized, 0
0x14009a295  jnz     short loc_14009A29C
0x14009a297  call    WdmlibInit
0x14009a29c  mov     rax, cs:PfnIoCreateDeviceSecure
0x14009a2a3  lea     rcx, [rbp+Object]
0x14009a2a7  mov     [rsp+70h+var_30], rcx
0x14009a2ac  lea     r8, [rbp+DestinationString]
0x14009a2b0  lea     rcx, BTLCKR_TMP_GUID
0x14009a2b7  mov     r9d, 22h ; '"'
0x14009a2bd  mov     [rsp+70h+var_38], rcx
0x14009a2c2  xor     edx, edx
0x14009a2c4  mov     [rsp+70h+var_40], rbx
0x14009a2c9  mov     rcx, rsi
0x14009a2cc  mov     [rsp+70h+var_48], 0
0x14009a2d1  mov     [rsp+70h+var_50], 100h
0x14009a2d9  call    _guard_dispatch_icall
0x14009a2de  mov     ebx, eax
0x14009a2e0  test    eax, eax
0x14009a2e2  js      short loc_14009A359
0x14009a2e4  mov     rcx, [rbp+Object]; Object
0x14009a2e8  lea     r8, [rbp+MemoryAllocated]; MemoryAllocated
0x14009a2ec  lea     rdx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14009a2f0  call    cs:__imp_ObGetObjectSecurity
0x14009a2f7  nop     dword ptr [rax+rax+00h]
0x14009a2fc  mov     ebx, eax
0x14009a2fe  test    eax, eax
0x14009a300  js      short loc_14009A359
0x14009a302  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14009a306  call    cs:__imp_RtlLengthSecurityDescriptor
0x14009a30d  nop     dword ptr [rax+rax+00h]
0x14009a312  mov     edx, eax
0x14009a314  mov     ecx, 100h
0x14009a319  mov     r8d, 30455646h
0x14009a31f  call    cs:__imp_ExAllocatePool2
0x14009a326  nop     dword ptr [rax+rax+00h]
0x14009a32b  mov     [rdi], rax
0x14009a32e  test    rax, rax
0x14009a331  jnz     short loc_14009A33A
0x14009a333  mov     ebx, 0C000009Ah
0x14009a338  jmp     short loc_14009A359
0x14009a33a  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14009a33e  call    cs:__imp_RtlLengthSecurityDescriptor
0x14009a345  nop     dword ptr [rax+rax+00h]
0x14009a34a  mov     rdx, [rbp+SecurityDescriptor]; Src
0x14009a34e  mov     rcx, [rdi]; void *
0x14009a351  mov     r8d, eax; Size
0x14009a354  call    memmove
0x14009a359  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14009a35d  test    rcx, rcx
0x14009a360  jz      short loc_14009A379
0x14009a362  mov     dl, byte ptr [rbp+MemoryAllocated]; MemoryAllocated
0x14009a365  call    cs:__imp_ObReleaseObjectSecurity
0x14009a36c  nop     dword ptr [rax+rax+00h]
0x14009a371  mov     [rbp+SecurityDescriptor], 0
0x14009a379  mov     rcx, [rbp+Object]; DeviceObject
0x14009a37d  test    rcx, rcx
0x14009a380  jz      short loc_14009A38E
0x14009a382  call    cs:__imp_IoDeleteDevice
0x14009a389  nop     dword ptr [rax+rax+00h]
0x14009a38e  mov     eax, ebx
0x14009a390  mov     rbx, [rsp+70h+arg_0]
0x14009a398  add     rsp, 70h
0x14009a39c  pop     rdi
0x14009a39d  pop     rsi
0x14009a39e  pop     rbp
0x14009a39f  retn
```
