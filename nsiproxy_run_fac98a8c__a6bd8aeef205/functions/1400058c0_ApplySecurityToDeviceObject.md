# ApplySecurityToDeviceObject

- ea: `0x1400058c0`
- end: `0x140005afc`
- name: `ApplySecurityToDeviceObject`
- size: `572`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005320`

## callees

- `0x1400058c0`
- `0x140006680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400059cb`
- `ntoskrnl!ExAllocatePool2` at `0x1400059cb`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140005939`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140005939`
- `ntoskrnl!ObGetObjectSecurity` at `0x14000595a`
- `ntoskrnl!ObGetObjectSecurity` at `0x14000595a`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140005980`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140005980`
- `ntoskrnl!RtlLengthSid` at `0x1400059a4`
- `ntoskrnl!RtlLengthSid` at `0x1400059a4`
- `ntoskrnl!RtlCreateAcl` at `0x1400059f4`
- `ntoskrnl!RtlCreateAcl` at `0x1400059f4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140005a38`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140005a38`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140005a57`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140005a57`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140005a75`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140005a75`
- `ntoskrnl!ZwSetSecurityObject` at `0x140005a94`
- `ntoskrnl!ZwSetSecurityObject` at `0x140005a94`
- `ntoskrnl!ZwClose` at `0x140005aa6`
- `ntoskrnl!ZwClose` at `0x140005aa6`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140005adf`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140005adf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005ac7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005ac7`

## pseudocode

```c
__int64 __fastcall ApplySecurityToDeviceObject(__int64 a1, __int64 a2, int a3, int a4)
{
  PDEVICE_OBJECT v4; // rsi
  struct _ACL *v5; // rdi
  NTSTATUS ObjectSecurity; // ebx
  __int64 v8; // rbx
  ULONG AclSize; // esi
  ULONG v10; // eax
  struct _ACL *Pool2; // rax
  __int64 i; // rsi
  HANDLE Handle; // [rsp+40h] [rbp-40h] BYREF
  PACL Dacl; // [rsp+48h] [rbp-38h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-30h] BYREF
  _OWORD v17[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v18; // [rsp+78h] [rbp-8h]
  __int64 DaclPresent; // [rsp+B0h] [rbp+30h] BYREF
  int DaclDefaulted; // [rsp+C0h] [rbp+40h] BYREF
  int MemoryAllocated; // [rsp+C8h] [rbp+48h] BYREF

  MemoryAllocated = a4;
  DaclDefaulted = a3;
  DaclPresent = a1;
  v4 = NsiProxyDeviceObject;
  v18 = 0;
  Handle = 0;
  v5 = 0;
  LOBYTE(DaclPresent) = 0;
  LOBYTE(DaclDefaulted) = 0;
  Dacl = 0;
  SecurityDescriptor = 0;
  LOBYTE(MemoryAllocated) = 0;
  memset(v17, 0, sizeof(v17));
  ObjectSecurity = ObOpenObjectByPointer(NsiProxyDeviceObject, 0x200u, 0, 0x40000u, 0, 0, &Handle);
  if ( ObjectSecurity >= 0 )
  {
    ObjectSecurity = ObGetObjectSecurity(v4, &SecurityDescriptor, (PBOOLEAN)&MemoryAllocated);
    if ( ObjectSecurity >= 0 )
    {
      ObjectSecurity = RtlGetDaclSecurityDescriptor(
                         SecurityDescriptor,
                         (PBOOLEAN)&DaclPresent,
                         &Dacl,
                         (PBOOLEAN)&DaclDefaulted);
      if ( ObjectSecurity >= 0 )
      {
        v8 = 0;
        AclSize = Dacl->AclSize;
        do
        {
          v10 = RtlLengthSid(*(PSID *)(a2 + 8 * v8++));
          AclSize += v10 + 8;
        }
        while ( v8 != 4 );
        Pool2 = (struct _ACL *)ExAllocatePool2(256, AclSize, 4285292);
        v5 = Pool2;
        if ( Pool2 )
        {
          ObjectSecurity = RtlCreateAcl(Pool2, AclSize, 2u);
          if ( ObjectSecurity >= 0 )
          {
            memmove(v5, Dacl, Dacl->AclSize);
            v5->AclSize = AclSize;
            for ( i = 0; (unsigned int)i < 4; i = (unsigned int)(i + 1) )
            {
              ObjectSecurity = RtlAddAccessAllowedAce(v5, 2u, 0x20000000u, *(PSID *)(a2 + 8 * i));
              if ( ObjectSecurity < 0 )
                goto LABEL_16;
            }
            ObjectSecurity = RtlCreateSecurityDescriptor(v17, 1u);
            if ( ObjectSecurity >= 0 )
            {
              ObjectSecurity = RtlSetDaclSecurityDescriptor(v17, 1u, v5, 0);
              if ( ObjectSecurity >= 0 )
                ObjectSecurity = ZwSetSecurityObject(Handle, 4u, v17);
            }
          }
        }
        else
        {
          ObjectSecurity = -1073741670;
        }
      }
    }
  }
LABEL_16:
  ZwClose(Handle);
  Handle = 0;
  if ( v5 )
    ExFreePoolWithTag(v5, 0x41636Cu);
  if ( SecurityDescriptor )
    ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated);
  return (unsigned int)ObjectSecurity;
}

```

## disassembly

```asm
0x1400058c0  mov     r11, rsp
0x1400058c3  mov     [r11+20h], r9d
0x1400058c7  mov     [r11+18h], r8d
0x1400058cb  mov     [r11+8], rcx
0x1400058cf  push    rbp
0x1400058d0  push    rbx
0x1400058d1  push    rsi
0x1400058d2  push    rdi
0x1400058d3  push    r14
0x1400058d5  mov     rbp, rsp
0x1400058d8  sub     rsp, 80h
0x1400058df  mov     rsi, cs:NsiProxyDeviceObject
0x1400058e6  xor     eax, eax
0x1400058e8  xorps   xmm0, xmm0
0x1400058eb  mov     [rbp+var_8], rax
0x1400058ef  mov     [rbp+Handle], rax
0x1400058f3  xor     edi, edi
0x1400058f5  mov     byte ptr [rbp+DaclPresent], al
0x1400058f8  mov     r14, rdx
0x1400058fb  mov     byte ptr [rbp+DaclDefaulted], al
0x1400058fe  mov     r9d, 40000h; DesiredAccess
0x140005904  mov     [rbp+Dacl], rax
0x140005908  xor     r8d, r8d; PassedAccessState
0x14000590b  lea     rax, [rbp+Handle]
0x14000590f  mov     [rbp+SecurityDescriptor], 0
0x140005917  mov     [r11-78h], rax
0x14000591b  mov     edx, 200h; HandleAttributes
0x140005920  mov     [rsp+80h+AccessMode], dil; AccessMode
0x140005925  mov     rcx, rsi; Object
0x140005928  mov     [rsp+80h+ObjectType], rdi; ObjectType
0x14000592d  mov     byte ptr [rbp+MemoryAllocated], 0
0x140005931  movups  [rbp+var_28], xmm0
0x140005935  movups  [rbp+var_18], xmm0
0x140005939  call    cs:__imp_ObOpenObjectByPointer
0x140005940  nop     dword ptr [rax+rax+00h]
0x140005945  mov     ebx, eax
0x140005947  test    eax, eax
0x140005949  js      loc_140005AA2
0x14000594f  lea     r8, [rbp+MemoryAllocated]; MemoryAllocated
0x140005953  mov     rcx, rsi; Object
0x140005956  lea     rdx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000595a  call    cs:__imp_ObGetObjectSecurity
0x140005961  nop     dword ptr [rax+rax+00h]
0x140005966  mov     ebx, eax
0x140005968  test    eax, eax
0x14000596a  js      loc_140005AA2
0x140005970  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140005974  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x140005978  lea     r8, [rbp+Dacl]; Dacl
0x14000597c  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x140005980  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140005987  nop     dword ptr [rax+rax+00h]
0x14000598c  mov     ebx, eax
0x14000598e  test    eax, eax
0x140005990  js      loc_140005AA2
0x140005996  mov     rax, [rbp+Dacl]
0x14000599a  xor     ebx, ebx
0x14000599c  movzx   esi, word ptr [rax+2]
0x1400059a0  mov     rcx, [r14+rbx*8]; Sid
0x1400059a4  call    cs:__imp_RtlLengthSid
0x1400059ab  nop     dword ptr [rax+rax+00h]
0x1400059b0  add     esi, 8
0x1400059b3  inc     rbx
0x1400059b6  add     esi, eax
0x1400059b8  cmp     rbx, 4
0x1400059bc  jnz     short loc_1400059A0
0x1400059be  mov     edx, esi
0x1400059c0  mov     ecx, 100h
0x1400059c5  mov     r8d, 41636Ch
0x1400059cb  call    cs:__imp_ExAllocatePool2
0x1400059d2  nop     dword ptr [rax+rax+00h]
0x1400059d7  mov     rdi, rax
0x1400059da  test    rax, rax
0x1400059dd  jnz     short loc_1400059E9
0x1400059df  mov     ebx, 0C000009Ah
0x1400059e4  jmp     loc_140005AA2
0x1400059e9  mov     r8d, 2; AclRevision
0x1400059ef  mov     edx, esi; AclLength
0x1400059f1  mov     rcx, rdi; Acl
0x1400059f4  call    cs:__imp_RtlCreateAcl
0x1400059fb  nop     dword ptr [rax+rax+00h]
0x140005a00  mov     ebx, eax
0x140005a02  test    eax, eax
0x140005a04  js      loc_140005AA2
0x140005a0a  mov     rdx, [rbp+Dacl]; Src
0x140005a0e  mov     rcx, rdi; void *
0x140005a11  movzx   r8d, word ptr [rdx+2]; Size
0x140005a16  call    memmove
0x140005a1b  mov     [rdi+2], si
0x140005a1f  xor     esi, esi
0x140005a21  cmp     esi, 4
0x140005a24  jnb     short loc_140005A4E
0x140005a26  mov     r9, [r14+rsi*8]; Sid
0x140005a2a  mov     edx, 2; AceRevision
0x140005a2f  mov     r8d, 20000000h; AccessMask
0x140005a35  mov     rcx, rdi; Acl
0x140005a38  call    cs:__imp_RtlAddAccessAllowedAce
0x140005a3f  nop     dword ptr [rax+rax+00h]
0x140005a44  mov     ebx, eax
0x140005a46  test    eax, eax
0x140005a48  js      short loc_140005AA2
0x140005a4a  inc     esi
0x140005a4c  jmp     short loc_140005A21
0x140005a4e  mov     edx, 1; Revision
0x140005a53  lea     rcx, [rbp+var_28]; SecurityDescriptor
0x140005a57  call    cs:__imp_RtlCreateSecurityDescriptor
0x140005a5e  nop     dword ptr [rax+rax+00h]
0x140005a63  mov     ebx, eax
0x140005a65  test    eax, eax
0x140005a67  js      short loc_140005AA2
0x140005a69  xor     r9d, r9d; DaclDefaulted
0x140005a6c  lea     rcx, [rbp+var_28]; SecurityDescriptor
0x140005a70  mov     r8, rdi; Dacl
0x140005a73  mov     dl, 1; DaclPresent
0x140005a75  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140005a7c  nop     dword ptr [rax+rax+00h]
0x140005a81  mov     ebx, eax
0x140005a83  test    eax, eax
0x140005a85  js      short loc_140005AA2
0x140005a87  mov     rcx, [rbp+Handle]; Handle
0x140005a8b  lea     r8, [rbp+var_28]; SecurityDescriptor
0x140005a8f  mov     edx, 4; SecurityInformation
0x140005a94  call    cs:__imp_ZwSetSecurityObject
0x140005a9b  nop     dword ptr [rax+rax+00h]
0x140005aa0  mov     ebx, eax
0x140005aa2  mov     rcx, [rbp+Handle]; Handle
0x140005aa6  call    cs:__imp_ZwClose
0x140005aad  nop     dword ptr [rax+rax+00h]
0x140005ab2  mov     [rbp+Handle], 0
0x140005aba  test    rdi, rdi
0x140005abd  jz      short loc_140005AD3
0x140005abf  mov     edx, 41636Ch; Tag
0x140005ac4  mov     rcx, rdi; P
0x140005ac7  call    cs:__imp_ExFreePoolWithTag
0x140005ace  nop     dword ptr [rax+rax+00h]
0x140005ad3  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140005ad7  test    rcx, rcx
0x140005ada  jz      short loc_140005AEB
0x140005adc  mov     dl, byte ptr [rbp+MemoryAllocated]; MemoryAllocated
0x140005adf  call    cs:__imp_ObReleaseObjectSecurity
0x140005ae6  nop     dword ptr [rax+rax+00h]
0x140005aeb  mov     eax, ebx
0x140005aed  add     rsp, 80h
0x140005af4  pop     r14
0x140005af6  pop     rdi
0x140005af7  pop     rsi
0x140005af8  pop     rbx
0x140005af9  pop     rbp
0x140005afa  retn
```
