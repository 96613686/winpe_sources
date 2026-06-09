# BfsVerifyPolicySecurity

- ea: `0x14000b0d0`
- end: `0x14000b467`
- name: `BfsVerifyPolicySecurity`
- size: `919`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x140001008`
- `0x140004614`
- `0x14000b0d0`
- `0x140013860`

## import_xrefs

- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14000b243`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14000b243`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14000b29c`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14000b29c`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14000b3c9`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14000b3c9`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14000b2fd`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14000b2fd`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000b145`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000b1ea`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000b145`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000b1ea`
- `ntoskrnl!RtlEqualSid` at `0x14000b27d`
- `ntoskrnl!RtlEqualSid` at `0x14000b2da`
- `ntoskrnl!RtlEqualSid` at `0x14000b27d`
- `ntoskrnl!RtlEqualSid` at `0x14000b2da`
- `ntoskrnl!SeExports` at `0x14000b26c`
- `ntoskrnl!SeExports` at `0x14000b2c9`
- `ntoskrnl!SeExports` at `0x14000b335`
- `ntoskrnl!SeExports` at `0x14000b37a`
- `ntoskrnl!SeExports` at `0x14000b3ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b435`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b435`
- `ntoskrnl!ExAllocatePool2` at `0x14000b1a6`
- `ntoskrnl!ExAllocatePool2` at `0x14000b1a6`

## pseudocode

```c
__int64 __fastcall BfsVerifyPolicySecurity(HANDLE Handle, _BYTE *a2)
{
  NTSTATUS v4; // eax
  int v5; // r8d
  int v6; // r9d
  NTSTATUS OwnerSecurityDescriptor; // ebx
  int v8; // ecx
  ULONG v9; // ebx
  void *Pool2; // rdi
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int LengthNeeded; // [rsp+20h] [rbp-49h]
  int LengthNeededa; // [rsp+20h] [rbp-49h]
  _BYTE v17[4]; // [rsp+30h] [rbp-39h] BYREF
  int v18; // [rsp+34h] [rbp-35h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+38h] [rbp-31h] BYREF
  unsigned __int8 GroupDefaulted; // [rsp+39h] [rbp-30h] BYREF
  unsigned __int8 DaclPresent; // [rsp+3Ah] [rbp-2Fh] BYREF
  unsigned __int8 SaclPresent; // [rsp+3Bh] [rbp-2Eh] BYREF
  unsigned __int8 DaclDefaulted; // [rsp+3Ch] [rbp-2Dh] BYREF
  unsigned __int8 SaclDefaulted[3]; // [rsp+3Dh] [rbp-2Ch] BYREF
  ULONG Length; // [rsp+40h] [rbp-29h] BYREF
  PACL Dacl; // [rsp+48h] [rbp-21h] BYREF
  PSID Owner; // [rsp+50h] [rbp-19h] BYREF
  PSID Group; // [rsp+58h] [rbp-11h] BYREF
  PACL Sacl; // [rsp+60h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+68h] [rbp-1h] BYREF
  int *v31; // [rsp+88h] [rbp+1Fh]
  __int64 v32; // [rsp+90h] [rbp+27h]

  *a2 = 1;
  v17[0] = 0;
  Dacl = 0;
  DaclDefaulted = 0;
  DaclPresent = 0;
  Group = 0;
  GroupDefaulted = 0;
  Length = 0;
  Owner = 0;
  OwnerDefaulted = 0;
  Sacl = 0;
  SaclDefaulted[0] = 0;
  SaclPresent = 0;
  v4 = ZwQuerySecurityObject(Handle, 0x1Fu, 0, 0, &Length);
  OwnerSecurityDescriptor = v4;
  if ( v4 == -1073741789 )
  {
    v9 = Length;
    Pool2 = (void *)ExAllocatePool2(256, Length, 1148413506);
    if ( !Pool2 )
    {
      OwnerSecurityDescriptor = -1073741801;
      if ( (unsigned int)dword_140019000 <= 3 )
        return (unsigned int)OwnerSecurityDescriptor;
      v18 = -1073741801;
      goto LABEL_4;
    }
    OwnerSecurityDescriptor = ZwQuerySecurityObject(Handle, 0x1Fu, Pool2, v9, &Length);
    if ( OwnerSecurityDescriptor < 0 )
      goto LABEL_9;
    OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(Pool2, &Owner, &OwnerDefaulted);
    if ( OwnerSecurityDescriptor < 0 )
      goto LABEL_9;
    if ( Owner && OwnerDefaulted != 1 && RtlEqualSid(Owner, SeExports->SeLocalSystemSid) )
    {
      OwnerSecurityDescriptor = RtlGetGroupSecurityDescriptor(Pool2, &Group, &GroupDefaulted);
      if ( OwnerSecurityDescriptor < 0 )
        goto LABEL_9;
      if ( Group && GroupDefaulted != 1 && RtlEqualSid(Group, SeExports->SeLocalSystemSid) )
      {
        OwnerSecurityDescriptor = RtlGetDaclSecurityDescriptor(Pool2, &DaclPresent, &Dacl, &DaclDefaulted);
        if ( OwnerSecurityDescriptor < 0 )
          goto LABEL_9;
        if ( DaclPresent && Dacl && Dacl->AceCount == 2 )
        {
          OwnerSecurityDescriptor = BfsVerifyAce(Dacl, SeExports->SeTrustedInstallerSid, (__int64)v17);
          if ( OwnerSecurityDescriptor < 0 )
            goto LABEL_9;
          if ( v17[0] )
          {
            OwnerSecurityDescriptor = BfsVerifyAce(Dacl, SeExports->SeLocalSystemSid, (__int64)v17);
            if ( OwnerSecurityDescriptor < 0 )
              goto LABEL_9;
            if ( v17[0] )
            {
              OwnerSecurityDescriptor = RtlGetSaclSecurityDescriptor(Pool2, &SaclPresent, &Sacl, SaclDefaulted);
              if ( OwnerSecurityDescriptor < 0 )
                goto LABEL_9;
              if ( SaclPresent && Sacl )
              {
                OwnerSecurityDescriptor = BfsVerifyAce(Sacl, SeExports->SeHighMandatorySid, (__int64)v17);
                if ( OwnerSecurityDescriptor >= 0 )
                {
                  if ( v17[0] )
                    *a2 = 0;
                  goto LABEL_33;
                }
LABEL_9:
                if ( (unsigned int)dword_140019000 > 3 )
                {
                  v18 = OwnerSecurityDescriptor;
                  v31 = &v18;
                  v32 = 4;
                  tlgWriteTransfer_EtwWriteTransfer(v11, (int)&byte_140016D91, v12, v13, LengthNeededa, &v30);
                }
              }
            }
          }
        }
      }
    }
LABEL_33:
    ExFreePoolWithTag(Pool2, 0);
    return (unsigned int)OwnerSecurityDescriptor;
  }
  v8 = dword_140019000;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v18 = v4;
LABEL_4:
    v32 = 4;
    v31 = &v18;
    tlgWriteTransfer_EtwWriteTransfer(v8, (int)&byte_140016D91, v5, v6, LengthNeeded, &v30);
  }
  return (unsigned int)OwnerSecurityDescriptor;
}

```

## disassembly

```asm
0x14000b0d0  mov     [rsp-8+arg_10], rbx
0x14000b0d5  push    rbp
0x14000b0d6  push    rsi
0x14000b0d7  push    rdi
0x14000b0d8  push    r14
0x14000b0da  push    r15
0x14000b0dc  lea     rbp, [rsp-37h]
0x14000b0e1  sub     rsp, 0A0h
0x14000b0e8  mov     rax, cs:__security_cookie
0x14000b0ef  xor     rax, rsp
0x14000b0f2  mov     [rbp+57h+var_28], rax
0x14000b0f6  xor     r15d, r15d
0x14000b0f9  mov     byte ptr [rdx], 1
0x14000b0fc  mov     r14, rdx
0x14000b0ff  mov     byte ptr [rbp+57h+var_90], r15b
0x14000b103  lea     rax, [rbp+57h+Length]
0x14000b107  mov     [rbp+57h+Dacl], r15
0x14000b10b  xor     r9d, r9d; Length
0x14000b10e  mov     [rbp+57h+DaclDefaulted], r15b
0x14000b112  lea     edx, [r15+1Fh]; SecurityInformation
0x14000b116  mov     [rbp+57h+DaclPresent], r15b
0x14000b11a  xor     r8d, r8d; SecurityDescriptor
0x14000b11d  mov     [rbp+57h+Group], r15
0x14000b121  mov     rsi, rcx
0x14000b124  mov     [rbp+57h+GroupDefaulted], r15b
0x14000b128  mov     [rbp+57h+Length], r15d
0x14000b12c  mov     [rbp+57h+Owner], r15
0x14000b130  mov     [rbp+57h+OwnerDefaulted], r15b
0x14000b134  mov     [rbp+57h+Sacl], r15
0x14000b138  mov     [rbp+57h+SaclDefaulted], r15b
0x14000b13c  mov     [rbp+57h+SaclPresent], r15b
0x14000b140  mov     [rsp+0C0h+LengthNeeded], rax; int
0x14000b145  call    cs:__imp_ZwQuerySecurityObject
0x14000b14c  nop     dword ptr [rax+rax+00h]
0x14000b151  mov     ebx, eax
0x14000b153  cmp     eax, 0C0000023h
0x14000b158  jz      short loc_14000B196
0x14000b15a  mov     ecx, cs:dword_140019000; int
0x14000b160  cmp     ecx, 3
0x14000b163  jbe     loc_14000B441
0x14000b169  mov     dword ptr [rbp+57h+var_90+4], eax
0x14000b16c  lea     rax, [rbp+57h+var_90+4]
0x14000b170  mov     [rbp+57h+var_30], 4
0x14000b178  mov     [rbp+57h+var_38], rax
0x14000b17c  lea     rdx, byte_140016D91; int
0x14000b183  lea     rax, [rbp+57h+var_58]
0x14000b187  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x14000b18c  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000b191  jmp     loc_14000B441
0x14000b196  mov     ebx, [rbp+57h+Length]
0x14000b199  mov     ecx, 100h
0x14000b19e  mov     edx, ebx
0x14000b1a0  mov     r8d, 44736642h
0x14000b1a6  call    cs:__imp_ExAllocatePool2
0x14000b1ad  nop     dword ptr [rax+rax+00h]
0x14000b1b2  mov     rdi, rax
0x14000b1b5  test    rax, rax
0x14000b1b8  jnz     short loc_14000B1D3
0x14000b1ba  mov     eax, cs:dword_140019000
0x14000b1c0  mov     ebx, 0C0000017h
0x14000b1c5  cmp     eax, 3
0x14000b1c8  jbe     loc_14000B441
0x14000b1ce  mov     dword ptr [rbp+57h+var_90+4], ebx
0x14000b1d1  jmp     short loc_14000B16C
0x14000b1d3  lea     rax, [rbp+57h+Length]
0x14000b1d7  mov     r9d, ebx; Length
0x14000b1da  mov     r8, rdi; SecurityDescriptor
0x14000b1dd  mov     [rsp+0C0h+LengthNeeded], rax; int
0x14000b1e2  mov     edx, 1Fh; SecurityInformation
0x14000b1e7  mov     rcx, rsi; Handle
0x14000b1ea  call    cs:__imp_ZwQuerySecurityObject
0x14000b1f1  nop     dword ptr [rax+rax+00h]
0x14000b1f6  mov     ebx, eax
0x14000b1f8  test    eax, eax
0x14000b1fa  jns     short loc_14000B238
0x14000b1fc  mov     eax, cs:dword_140019000
0x14000b202  cmp     eax, 3
0x14000b205  jbe     loc_14000B430
0x14000b20b  lea     rax, [rbp+57h+var_90+4]
0x14000b20f  mov     dword ptr [rbp+57h+var_90+4], ebx
0x14000b212  mov     [rbp+57h+var_38], rax
0x14000b216  lea     rdx, byte_140016D91; int
0x14000b21d  lea     rax, [rbp+57h+var_58]
0x14000b221  mov     [rbp+57h+var_30], 4
0x14000b229  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x14000b22e  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000b233  jmp     loc_14000B430
0x14000b238  lea     r8, [rbp+57h+OwnerDefaulted]; OwnerDefaulted
0x14000b23c  mov     rcx, rdi; SecurityDescriptor
0x14000b23f  lea     rdx, [rbp+57h+Owner]; Owner
0x14000b243  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x14000b24a  nop     dword ptr [rax+rax+00h]
0x14000b24f  mov     ebx, eax
0x14000b251  test    eax, eax
0x14000b253  js      short loc_14000B1FC
0x14000b255  mov     rcx, [rbp+57h+Owner]; Sid1
0x14000b259  test    rcx, rcx
0x14000b25c  jz      loc_14000B430
0x14000b262  cmp     [rbp+57h+OwnerDefaulted], 1
0x14000b266  jz      loc_14000B430
0x14000b26c  mov     rax, cs:__imp_SeExports
0x14000b273  mov     rdx, [rax]
0x14000b276  mov     rdx, [rdx+108h]; Sid2
0x14000b27d  call    cs:__imp_RtlEqualSid
0x14000b284  nop     dword ptr [rax+rax+00h]
0x14000b289  test    al, al
0x14000b28b  jz      loc_14000B430
0x14000b291  lea     r8, [rbp+57h+GroupDefaulted]; GroupDefaulted
0x14000b295  mov     rcx, rdi; SecurityDescriptor
0x14000b298  lea     rdx, [rbp+57h+Group]; Group
0x14000b29c  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x14000b2a3  nop     dword ptr [rax+rax+00h]
0x14000b2a8  mov     ebx, eax
0x14000b2aa  test    eax, eax
0x14000b2ac  js      loc_14000B1FC
0x14000b2b2  mov     rcx, [rbp+57h+Group]; Sid1
0x14000b2b6  test    rcx, rcx
0x14000b2b9  jz      loc_14000B430
0x14000b2bf  cmp     [rbp+57h+GroupDefaulted], 1
0x14000b2c3  jz      loc_14000B430
0x14000b2c9  mov     rax, cs:__imp_SeExports
0x14000b2d0  mov     rdx, [rax]
0x14000b2d3  mov     rdx, [rdx+108h]; Sid2
0x14000b2da  call    cs:__imp_RtlEqualSid
0x14000b2e1  nop     dword ptr [rax+rax+00h]
0x14000b2e6  test    al, al
0x14000b2e8  jz      loc_14000B430
0x14000b2ee  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x14000b2f2  mov     rcx, rdi; SecurityDescriptor
0x14000b2f5  lea     r8, [rbp+57h+Dacl]; Dacl
0x14000b2f9  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x14000b2fd  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14000b304  nop     dword ptr [rax+rax+00h]
0x14000b309  mov     ebx, eax
0x14000b30b  test    eax, eax
0x14000b30d  js      loc_14000B1FC
0x14000b313  cmp     [rbp+57h+DaclPresent], r15b
0x14000b317  jz      loc_14000B430
0x14000b31d  mov     rcx, [rbp+57h+Dacl]; Acl
0x14000b321  test    rcx, rcx
0x14000b324  jz      loc_14000B430
0x14000b32a  cmp     word ptr [rcx+4], 2
0x14000b32f  jnz     loc_14000B430
0x14000b335  mov     rax, cs:__imp_SeExports
0x14000b33c  lea     rdx, [rbp+57h+var_90]
0x14000b340  mov     [rsp+0C0h+var_98], rdx; __int64
0x14000b345  mov     esi, 1F01FFh
0x14000b34a  mov     r9d, esi
0x14000b34d  mov     r8b, 3
0x14000b350  xor     edx, edx
0x14000b352  mov     rax, [rax]
0x14000b355  mov     rax, [rax+220h]
0x14000b35c  mov     [rsp+0C0h+LengthNeeded], rax; Sid1
0x14000b361  call    BfsVerifyAce
0x14000b366  mov     ebx, eax
0x14000b368  test    eax, eax
0x14000b36a  js      loc_14000B1FC
0x14000b370  cmp     byte ptr [rbp+57h+var_90], r15b
0x14000b374  jz      loc_14000B430
0x14000b37a  mov     rax, cs:__imp_SeExports
0x14000b381  lea     rcx, [rbp+57h+var_90]
0x14000b385  mov     [rsp+0C0h+var_98], rcx; __int64
0x14000b38a  mov     r9d, esi
0x14000b38d  mov     rcx, [rbp+57h+Dacl]; Acl
0x14000b391  mov     r8b, 3
0x14000b394  xor     edx, edx
0x14000b396  mov     rax, [rax]
0x14000b399  mov     rax, [rax+108h]
0x14000b3a0  mov     [rsp+0C0h+LengthNeeded], rax; Sid1
0x14000b3a5  call    BfsVerifyAce
0x14000b3aa  mov     ebx, eax
0x14000b3ac  test    eax, eax
0x14000b3ae  js      loc_14000B1FC
0x14000b3b4  cmp     byte ptr [rbp+57h+var_90], r15b
0x14000b3b8  jz      short loc_14000B430
0x14000b3ba  lea     r9, [rbp+57h+SaclDefaulted]; SaclDefaulted
0x14000b3be  mov     rcx, rdi; SecurityDescriptor
0x14000b3c1  lea     r8, [rbp+57h+Sacl]; Sacl
0x14000b3c5  lea     rdx, [rbp+57h+SaclPresent]; SaclPresent
0x14000b3c9  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x14000b3d0  nop     dword ptr [rax+rax+00h]
0x14000b3d5  mov     ebx, eax
0x14000b3d7  test    eax, eax
0x14000b3d9  js      loc_14000B1FC
0x14000b3df  cmp     [rbp+57h+SaclPresent], r15b
0x14000b3e3  jz      short loc_14000B430
0x14000b3e5  mov     rcx, [rbp+57h+Sacl]; Acl
0x14000b3e9  test    rcx, rcx
0x14000b3ec  jz      short loc_14000B430
0x14000b3ee  mov     rax, cs:__imp_SeExports
0x14000b3f5  lea     rdx, [rbp+57h+var_90]
0x14000b3f9  mov     [rsp+0C0h+var_98], rdx; __int64
0x14000b3fe  mov     r9d, 7
0x14000b404  mov     r8b, 3
0x14000b407  mov     dl, 11h
0x14000b409  mov     rax, [rax]
0x14000b40c  mov     rax, [rax+1F0h]
0x14000b413  mov     [rsp+0C0h+LengthNeeded], rax; Sid1
0x14000b418  call    BfsVerifyAce
0x14000b41d  mov     ebx, eax
0x14000b41f  test    eax, eax
0x14000b421  js      loc_14000B1FC
0x14000b427  cmp     byte ptr [rbp+57h+var_90], r15b
0x14000b42b  jz      short loc_14000B430
0x14000b42d  mov     [r14], r15b
0x14000b430  xor     edx, edx; Tag
0x14000b432  mov     rcx, rdi; P
0x14000b435  call    cs:__imp_ExFreePoolWithTag
0x14000b43c  nop     dword ptr [rax+rax+00h]
0x14000b441  mov     eax, ebx
0x14000b443  mov     rcx, [rbp+57h+var_28]
0x14000b447  xor     rcx, rsp; StackCookie
0x14000b44a  call    __security_check_cookie
0x14000b44f  mov     rbx, [rsp+0C0h+arg_10]
0x14000b457  add     rsp, 0A0h
0x14000b45e  pop     r15
0x14000b460  pop     r14
0x14000b462  pop     rdi
0x14000b463  pop     rsi
0x14000b464  pop     rbp
0x14000b465  retn
```
