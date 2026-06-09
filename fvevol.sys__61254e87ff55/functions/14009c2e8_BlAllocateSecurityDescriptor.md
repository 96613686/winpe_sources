# BlAllocateSecurityDescriptor

- ea: `0x14009c2e8`
- end: `0x14009c451`
- name: `BlAllocateSecurityDescriptor`
- size: `361`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400f20c4`
- `0x1400f2c84`

## callees

- `0x140022cd0`
- `0x140022d40`
- `0x140084fa0`
- `0x14009c2e8`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14009c3b6`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14009c3ee`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14009c3b6`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14009c3ee`
- `ntoskrnl!IoDeleteDevice` at `0x14009c432`
- `ntoskrnl!IoDeleteDevice` at `0x14009c432`
- `ntoskrnl!ObGetObjectSecurity` at `0x14009c3a0`
- `ntoskrnl!ObGetObjectSecurity` at `0x14009c3a0`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14009c415`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14009c415`
- `ntoskrnl!ExAllocatePool2` at `0x14009c3cf`
- `ntoskrnl!ExAllocatePool2` at `0x14009c3cf`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009c332`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009c332`

## string_xrefs

- `0x14009c319`: `\Device\BitLocker_Temp`

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
0x14009c2e8  mov     [rsp-18h+arg_0], rbx
0x14009c2ed  mov     [rsp-18h+MemoryAllocated], r9d
0x14009c2f2  push    rbp
0x14009c2f3  push    rsi
0x14009c2f4  push    rdi
0x14009c2f5  mov     rbp, rsp
0x14009c2f8  sub     rsp, 70h
0x14009c2fc  mov     rbx, rdx
0x14009c2ff  mov     [rbp+Object], 0
0x14009c307  mov     rsi, rcx
0x14009c30a  mov     [rbp+SecurityDescriptor], 0
0x14009c312  xorps   xmm0, xmm0
0x14009c315  mov     byte ptr [rbp+MemoryAllocated], 0
0x14009c319  lea     rdx, aDeviceBitlocke; "\\Device\\BitLocker_Temp"
0x14009c320  mov     qword ptr [r8], 0
0x14009c327  lea     rcx, [rbp+DestinationString]; DestinationString
0x14009c32b  mov     rdi, r8
0x14009c32e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14009c332  call    cs:__imp_RtlInitUnicodeString
0x14009c339  nop     dword ptr [rax+rax+00h]
0x14009c33e  cmp     cs:WdmlibInitialized, 0
0x14009c345  jnz     short loc_14009C34C
0x14009c347  call    WdmlibInit
0x14009c34c  mov     rax, cs:PfnIoCreateDeviceSecure
0x14009c353  lea     rcx, [rbp+Object]
0x14009c357  mov     [rsp+70h+var_30], rcx
0x14009c35c  lea     r8, [rbp+DestinationString]
0x14009c360  lea     rcx, BTLCKR_TMP_GUID
0x14009c367  mov     r9d, 22h ; '"'
0x14009c36d  mov     [rsp+70h+var_38], rcx
0x14009c372  xor     edx, edx
0x14009c374  mov     [rsp+70h+var_40], rbx
0x14009c379  mov     rcx, rsi
0x14009c37c  mov     [rsp+70h+var_48], 0
0x14009c381  mov     [rsp+70h+var_50], 100h
0x14009c389  call    _guard_dispatch_icall
0x14009c38e  mov     ebx, eax
0x14009c390  test    eax, eax
0x14009c392  js      short loc_14009C409
0x14009c394  mov     rcx, [rbp+Object]; Object
0x14009c398  lea     r8, [rbp+MemoryAllocated]; MemoryAllocated
0x14009c39c  lea     rdx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14009c3a0  call    cs:__imp_ObGetObjectSecurity
0x14009c3a7  nop     dword ptr [rax+rax+00h]
0x14009c3ac  mov     ebx, eax
0x14009c3ae  test    eax, eax
0x14009c3b0  js      short loc_14009C409
0x14009c3b2  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14009c3b6  call    cs:__imp_RtlLengthSecurityDescriptor
0x14009c3bd  nop     dword ptr [rax+rax+00h]
0x14009c3c2  mov     edx, eax
0x14009c3c4  mov     ecx, 100h
0x14009c3c9  mov     r8d, 30455646h
0x14009c3cf  call    cs:__imp_ExAllocatePool2
0x14009c3d6  nop     dword ptr [rax+rax+00h]
0x14009c3db  mov     [rdi], rax
0x14009c3de  test    rax, rax
0x14009c3e1  jnz     short loc_14009C3EA
0x14009c3e3  mov     ebx, 0C000009Ah
0x14009c3e8  jmp     short loc_14009C409
0x14009c3ea  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14009c3ee  call    cs:__imp_RtlLengthSecurityDescriptor
0x14009c3f5  nop     dword ptr [rax+rax+00h]
0x14009c3fa  mov     rdx, [rbp+SecurityDescriptor]; Src
0x14009c3fe  mov     rcx, [rdi]; void *
0x14009c401  mov     r8d, eax; Size
0x14009c404  call    memmove
0x14009c409  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14009c40d  test    rcx, rcx
0x14009c410  jz      short loc_14009C429
0x14009c412  mov     dl, byte ptr [rbp+MemoryAllocated]; MemoryAllocated
0x14009c415  call    cs:__imp_ObReleaseObjectSecurity
0x14009c41c  nop     dword ptr [rax+rax+00h]
0x14009c421  mov     [rbp+SecurityDescriptor], 0
0x14009c429  mov     rcx, [rbp+Object]; DeviceObject
0x14009c42d  test    rcx, rcx
0x14009c430  jz      short loc_14009C43E
0x14009c432  call    cs:__imp_IoDeleteDevice
0x14009c439  nop     dword ptr [rax+rax+00h]
0x14009c43e  mov     eax, ebx
0x14009c440  mov     rbx, [rsp+70h+arg_0]
0x14009c448  add     rsp, 70h
0x14009c44c  pop     rdi
0x14009c44d  pop     rsi
0x14009c44e  pop     rbp
0x14009c44f  retn
```
