# AllowNetworkServiceSecurityDescriptor(_DEVICE_OBJECT *,ulong *)

- ea: `0x1400114c4`
- end: `0x14001174e`
- name: `?AllowNetworkServiceSecurityDescriptor@@YAJPEAU_DEVICE_OBJECT@@PEAK@Z`
- size: `650`
- prototype: `int(struct _DEVICE_OBJECT *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14002e078`

## callees

- `0x140001e30`
- `0x14000324c`
- `0x14000327c`
- `0x1400114c4`
- `0x14002ce44`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14001157b`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14001157b`
- `ntoskrnl!ObGetObjectSecurity` at `0x14001151d`
- `ntoskrnl!ObGetObjectSecurity` at `0x14001151d`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400116d2`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400116d2`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140011721`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140011721`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140011647`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140011647`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140011691`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140011691`
- `ntoskrnl!SeValidSecurityDescriptor` at `0x14001158d`
- `ntoskrnl!SeValidSecurityDescriptor` at `0x14001158d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400115b1`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400115b1`

## pseudocode

```c
__int64 __fastcall AllowNetworkServiceSecurityDescriptor(struct _DEVICE_OBJECT *a1, unsigned int *a2)
{
  PKDPC BufferChainingDpc; // rdi
  NTSTATUS ObjectSecurity; // ebx
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  PSECURITY_DESCRIPTOR v7; // rdx
  ULONG v8; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-40h] BYREF
  PACL v11; // [rsp+28h] [rbp-38h] BYREF
  PACL Dacl; // [rsp+30h] [rbp-30h] BYREF
  _OWORD v13[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v14; // [rsp+58h] [rbp-8h]
  struct _DEVICE_OBJECT *MemoryAllocated; // [rsp+80h] [rbp+20h] BYREF
  unsigned __int8 DaclDefaulted; // [rsp+90h] [rbp+30h] BYREF
  unsigned __int8 DaclPresent; // [rsp+98h] [rbp+38h] BYREF

  MemoryAllocated = a1;
  BufferChainingDpc = WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc;
  Dacl = 0;
  DaclDefaulted = 0;
  DaclPresent = 0;
  v11 = 0;
  v14 = 0;
  memset(v13, 0, sizeof(v13));
  SecurityDescriptor = 0;
  LOBYTE(MemoryAllocated) = 0;
  ObjectSecurity = ObGetObjectSecurity(
                     WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                     &SecurityDescriptor,
                     (PBOOLEAN)&MemoryAllocated);
  if ( ObjectSecurity >= 0 )
  {
    v7 = SecurityDescriptor;
    v8 = 0;
    if ( SecurityDescriptor )
    {
      v8 = RtlLengthSecurityDescriptor(SecurityDescriptor);
      v7 = SecurityDescriptor;
    }
    if ( SeValidSecurityDescriptor(v8, v7) )
    {
      ObjectSecurity = RtlGetDaclSecurityDescriptor(SecurityDescriptor, &DaclPresent, &Dacl, &DaclDefaulted);
      if ( ObjectSecurity >= 0 )
      {
        if ( Dacl )
        {
          ObjectSecurity = BuildServiceAcl(a2, Dacl, &v11);
          if ( ObjectSecurity >= 0 )
          {
            ObjectSecurity = RtlCreateSecurityDescriptor(v13, 1u);
            if ( ObjectSecurity >= 0 )
            {
              ObjectSecurity = RtlSetDaclSecurityDescriptor(v13, 1u, v11, 0);
              if ( ObjectSecurity >= 0 )
              {
                ObjectSecurity = ObSetSecurityObjectByPointer(BufferChainingDpc, 4, v13);
              }
              else
              {
                v5 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v6 = 101;
                  goto LABEL_5;
                }
              }
            }
            else
            {
              v5 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v6 = 100;
                goto LABEL_5;
              }
            }
          }
          else
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v6 = 99;
              goto LABEL_5;
            }
          }
        }
        else
        {
          ObjectSecurity = -1073741823;
        }
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v6 = 98;
          goto LABEL_5;
        }
      }
    }
    else
    {
      ObjectSecurity = -1073741811;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v6 = 97;
LABEL_5:
      WPP_SF_d(v5->AttachedDevice, v6, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids, (unsigned int)ObjectSecurity);
    }
  }
  if ( SecurityDescriptor )
    ObReleaseObjectSecurity(SecurityDescriptor, (BOOLEAN)MemoryAllocated);
  if ( v11 )
    operator delete(v11);
  return (unsigned int)ObjectSecurity;
}

```

## disassembly

```asm
0x1400114c4  mov     [rsp-18h+arg_8], rbx
0x1400114c9  mov     [rsp-18h+MemoryAllocated], rcx
0x1400114ce  push    rbp
0x1400114cf  push    rsi
0x1400114d0  push    rdi
0x1400114d1  mov     rbp, rsp
0x1400114d4  sub     rsp, 60h
0x1400114d8  mov     rdi, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x1400114df  lea     r8, [rbp+MemoryAllocated]; MemoryAllocated
0x1400114e3  xor     eax, eax
0x1400114e5  mov     [rbp+Dacl], 0
0x1400114ed  xorps   xmm0, xmm0
0x1400114f0  mov     [rbp+DaclDefaulted], 0
0x1400114f4  mov     rsi, rdx
0x1400114f7  mov     [rbp+DaclPresent], 0
0x1400114fb  mov     rcx, rdi; Object
0x1400114fe  mov     [rbp+var_38], 0
0x140011506  lea     rdx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14001150a  mov     [rbp+var_8], rax
0x14001150e  movups  [rbp+var_28], xmm0
0x140011512  mov     [rbp+SecurityDescriptor], rax
0x140011516  movups  [rbp+var_18], xmm0
0x14001151a  mov     byte ptr [rbp+MemoryAllocated], al
0x14001151d  call    cs:__imp_ObGetObjectSecurity
0x140011524  nop     dword ptr [rax+rax+00h]
0x140011529  mov     ebx, eax
0x14001152b  test    eax, eax
0x14001152d  jns     short loc_14001156D
0x14001152f  mov     rcx, cs:WPP_GLOBAL_Control
0x140011536  lea     rax, WPP_GLOBAL_Control
0x14001153d  cmp     rcx, rax
0x140011540  jz      loc_140011715
0x140011546  cmp     byte ptr [rcx+29h], 2
0x14001154a  jb      loc_140011715
0x140011550  mov     edx, 61h ; 'a'
0x140011555  mov     rcx, [rcx+18h]
0x140011559  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x140011560  mov     r9d, ebx
0x140011563  call    WPP_SF_d
0x140011568  jmp     loc_140011715
0x14001156d  mov     rdx, [rbp+SecurityDescriptor]
0x140011571  xor     eax, eax
0x140011573  test    rdx, rdx
0x140011576  jz      short loc_14001158B
0x140011578  mov     rcx, rdx; SecurityDescriptor
0x14001157b  call    cs:__imp_RtlLengthSecurityDescriptor
0x140011582  nop     dword ptr [rax+rax+00h]
0x140011587  mov     rdx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14001158b  mov     ecx, eax; Length
0x14001158d  call    cs:__imp_SeValidSecurityDescriptor
0x140011594  nop     dword ptr [rax+rax+00h]
0x140011599  test    al, al
0x14001159b  jz      loc_1400116E2
0x1400115a1  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400115a5  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x1400115a9  lea     r8, [rbp+Dacl]; Dacl
0x1400115ad  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x1400115b1  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1400115b8  nop     dword ptr [rax+rax+00h]
0x1400115bd  mov     ebx, eax
0x1400115bf  test    eax, eax
0x1400115c1  jns     short loc_1400115EE
0x1400115c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400115ca  lea     rax, WPP_GLOBAL_Control
0x1400115d1  cmp     rcx, rax
0x1400115d4  jz      loc_140011715
0x1400115da  cmp     byte ptr [rcx+29h], 2
0x1400115de  jb      loc_140011715
0x1400115e4  mov     edx, 62h ; 'b'
0x1400115e9  jmp     loc_140011555
0x1400115ee  mov     rdx, [rbp+Dacl]; Src
0x1400115f2  test    rdx, rdx
0x1400115f5  jnz     short loc_140011601
0x1400115f7  mov     ebx, 0C0000001h
0x1400115fc  jmp     loc_140011715
0x140011601  lea     r8, [rbp+var_38]; struct _ACL **
0x140011605  mov     rcx, rsi; unsigned int *
0x140011608  call    ?BuildServiceAcl@@YAJPEAKPEAU_ACL@@PEAPEAU1@@Z; BuildServiceAcl(ulong *,_ACL *,_ACL * *)
0x14001160d  mov     ebx, eax
0x14001160f  test    eax, eax
0x140011611  jns     short loc_14001163E
0x140011613  mov     rcx, cs:WPP_GLOBAL_Control
0x14001161a  lea     rax, WPP_GLOBAL_Control
0x140011621  cmp     rcx, rax
0x140011624  jz      loc_140011715
0x14001162a  cmp     byte ptr [rcx+29h], 2
0x14001162e  jb      loc_140011715
0x140011634  mov     edx, 63h ; 'c'
0x140011639  jmp     loc_140011555
0x14001163e  mov     edx, 1; Revision
0x140011643  lea     rcx, [rbp+var_28]; SecurityDescriptor
0x140011647  call    cs:__imp_RtlCreateSecurityDescriptor
0x14001164e  nop     dword ptr [rax+rax+00h]
0x140011653  mov     ebx, eax
0x140011655  test    eax, eax
0x140011657  jns     short loc_140011684
0x140011659  mov     rcx, cs:WPP_GLOBAL_Control
0x140011660  lea     rax, WPP_GLOBAL_Control
0x140011667  cmp     rcx, rax
0x14001166a  jz      loc_140011715
0x140011670  cmp     byte ptr [rcx+29h], 2
0x140011674  jb      loc_140011715
0x14001167a  mov     edx, 64h ; 'd'
0x14001167f  jmp     loc_140011555
0x140011684  mov     r8, [rbp+var_38]; Dacl
0x140011688  lea     rcx, [rbp+var_28]; SecurityDescriptor
0x14001168c  xor     r9d, r9d; DaclDefaulted
0x14001168f  mov     dl, 1; DaclPresent
0x140011691  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140011698  nop     dword ptr [rax+rax+00h]
0x14001169d  mov     ebx, eax
0x14001169f  test    eax, eax
0x1400116a1  jns     short loc_1400116C6
0x1400116a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400116aa  lea     rax, WPP_GLOBAL_Control
0x1400116b1  cmp     rcx, rax
0x1400116b4  jz      short loc_140011715
0x1400116b6  cmp     byte ptr [rcx+29h], 2
0x1400116ba  jb      short loc_140011715
0x1400116bc  mov     edx, 65h ; 'e'
0x1400116c1  jmp     loc_140011555
0x1400116c6  lea     r8, [rbp+var_28]
0x1400116ca  mov     edx, 4
0x1400116cf  mov     rcx, rdi
0x1400116d2  call    cs:__imp_ObSetSecurityObjectByPointer
0x1400116d9  nop     dword ptr [rax+rax+00h]
0x1400116de  mov     ebx, eax
0x1400116e0  jmp     short loc_140011715
0x1400116e2  mov     ebx, 0C000000Dh
0x1400116e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400116ee  lea     rax, WPP_GLOBAL_Control
0x1400116f5  cmp     rcx, rax
0x1400116f8  jz      short loc_140011715
0x1400116fa  cmp     byte ptr [rcx+29h], 2
0x1400116fe  jb      short loc_140011715
0x140011700  mov     rcx, [rcx+18h]
0x140011704  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x14001170b  mov     edx, 66h ; 'f'
0x140011710  call    WPP_SF_
0x140011715  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140011719  test    rcx, rcx
0x14001171c  jz      short loc_14001172D
0x14001171e  mov     dl, byte ptr [rbp+MemoryAllocated]; MemoryAllocated
0x140011721  call    cs:__imp_ObReleaseObjectSecurity
0x140011728  nop     dword ptr [rax+rax+00h]
0x14001172d  mov     rcx, [rbp+var_38]; void *
0x140011731  test    rcx, rcx
0x140011734  jz      short loc_14001173B
0x140011736  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001173b  mov     eax, ebx
0x14001173d  mov     rbx, [rsp+60h+arg_8]
0x140011745  add     rsp, 60h
0x140011749  pop     rdi
0x14001174a  pop     rsi
0x14001174b  pop     rbp
0x14001174c  retn
```
