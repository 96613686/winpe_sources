# CreateAdminSecurityDescriptor

- ea: `0x1400176bc`
- end: `0x14001786c`
- name: `CreateAdminSecurityDescriptor`
- size: `432`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14002e078`

## callees

- `0x140001e30`
- `0x140003188`
- `0x14000327c`
- `0x1400176bc`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400177a3`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400177a3`
- `ntoskrnl!RtlMapGenericMask` at `0x1400177b7`
- `ntoskrnl!RtlMapGenericMask` at `0x1400177b7`
- `ntoskrnl!SeExports` at `0x1400176c9`
- `ntoskrnl!RtlLengthSid` at `0x1400176ec`
- `ntoskrnl!RtlLengthSid` at `0x1400176fd`
- `ntoskrnl!RtlLengthSid` at `0x1400176ec`
- `ntoskrnl!RtlLengthSid` at `0x1400176fd`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001773b`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001773b`
- `ntoskrnl!RtlCreateAcl` at `0x14001778d`
- `ntoskrnl!RtlCreateAcl` at `0x14001778d`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400177d0`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400177e9`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400177d0`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400177e9`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140017804`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140017804`

## pseudocode

```c
__int64 CreateAdminSecurityDescriptor()
{
  PSID SeLocalSystemSid; // r15
  PSID SeAliasAdminsSid; // r14
  ULONG v2; // ebx
  ULONG v3; // ebp
  struct _ACL *v4; // rax
  struct _ACL *v5; // rdi
  NTSTATUS SecurityDescriptor; // ebx
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  struct _ACL *v9; // rsi
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  DWORD AccessMask; // [rsp+60h] [rbp+8h] BYREF

  AccessMask = 0x10000000;
  SeLocalSystemSid = SeExports->SeLocalSystemSid;
  SeAliasAdminsSid = SeExports->SeAliasAdminsSid;
  v2 = RtlLengthSid(SeLocalSystemSid);
  v3 = v2 + RtlLengthSid(SeAliasAdminsSid) + 72;
  v4 = (struct _ACL *)operator new(v3, 0x100u);
  *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type = v4;
  v5 = v4;
  if ( !v4 )
  {
    SecurityDescriptor = -1073741801;
LABEL_13:
    operator delete(*(void **)&WPP_MAIN_CB.DeviceQueue.Type);
    *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type = 0;
    return (unsigned int)SecurityDescriptor;
  }
  SecurityDescriptor = RtlCreateSecurityDescriptor(v4, 1u);
  if ( SecurityDescriptor < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_13;
    v8 = 87;
    goto LABEL_12;
  }
  v9 = v5 + 5;
  SecurityDescriptor = RtlCreateAcl(v5 + 5, v3 - 40, 2u);
  if ( SecurityDescriptor < 0 )
    goto LABEL_13;
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
  RtlAddAccessAllowedAce(v9, 2u, AccessMask, SeLocalSystemSid);
  RtlAddAccessAllowedAce(v9, 2u, AccessMask, SeAliasAdminsSid);
  SecurityDescriptor = RtlSetDaclSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)&WPP_MAIN_CB.DeviceQueue.Type, 1u, v9, 0);
  if ( SecurityDescriptor < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_13;
    v8 = 88;
LABEL_12:
    WPP_SF_d(v7->AttachedDevice, v8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids, (unsigned int)SecurityDescriptor);
    goto LABEL_13;
  }
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x1400176bc  push    rbx
0x1400176be  push    rbp
0x1400176bf  push    rsi
0x1400176c0  push    rdi
0x1400176c1  push    r14
0x1400176c3  push    r15
0x1400176c5  sub     rsp, 28h
0x1400176c9  mov     rax, cs:__imp_SeExports
0x1400176d0  mov     [rsp+58h+AccessMask], 10000000h
0x1400176d8  mov     rcx, [rax]
0x1400176db  mov     r15, [rcx+108h]
0x1400176e2  mov     r14, [rcx+110h]
0x1400176e9  mov     rcx, r15; Sid
0x1400176ec  call    cs:__imp_RtlLengthSid
0x1400176f3  nop     dword ptr [rax+rax+00h]
0x1400176f8  mov     rcx, r14; Sid
0x1400176fb  mov     ebx, eax
0x1400176fd  call    cs:__imp_RtlLengthSid
0x140017704  nop     dword ptr [rax+rax+00h]
0x140017709  mov     edx, 100h; unsigned __int64
0x14001770e  lea     ebp, [rax+48h]
0x140017711  add     ebp, ebx
0x140017713  mov     ecx, ebp; unsigned __int64
0x140017715  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x14001771a  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, rax
0x140017721  mov     rdi, rax
0x140017724  test    rax, rax
0x140017727  jnz     short loc_140017733
0x140017729  mov     ebx, 0C0000017h
0x14001772e  jmp     loc_140017845
0x140017733  mov     edx, 1; Revision
0x140017738  mov     rcx, rdi; SecurityDescriptor
0x14001773b  call    cs:__imp_RtlCreateSecurityDescriptor
0x140017742  nop     dword ptr [rax+rax+00h]
0x140017747  mov     ebx, eax
0x140017749  test    eax, eax
0x14001774b  jns     short loc_14001777B
0x14001774d  mov     rcx, cs:WPP_GLOBAL_Control
0x140017754  lea     rax, WPP_GLOBAL_Control
0x14001775b  cmp     rcx, rax
0x14001775e  jz      loc_140017845
0x140017764  mov     edi, 2
0x140017769  cmp     [rcx+29h], dil
0x14001776d  jb      loc_140017845
0x140017773  lea     edx, [rdi+55h]
0x140017776  jmp     loc_140017832
0x14001777b  lea     rsi, [rdi+28h]
0x14001777f  mov     edi, 2
0x140017784  mov     r8d, edi; AclRevision
0x140017787  lea     edx, [rbp-28h]; AclLength
0x14001778a  mov     rcx, rsi; Acl
0x14001778d  call    cs:__imp_RtlCreateAcl
0x140017794  nop     dword ptr [rax+rax+00h]
0x140017799  mov     ebx, eax
0x14001779b  test    eax, eax
0x14001779d  js      loc_140017845
0x1400177a3  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400177aa  nop     dword ptr [rax+rax+00h]
0x1400177af  mov     rdx, rax; GenericMapping
0x1400177b2  lea     rcx, [rsp+58h+AccessMask]; AccessMask
0x1400177b7  call    cs:__imp_RtlMapGenericMask
0x1400177be  nop     dword ptr [rax+rax+00h]
0x1400177c3  mov     r8d, [rsp+58h+AccessMask]; AccessMask
0x1400177c8  mov     r9, r15; Sid
0x1400177cb  mov     edx, edi; AceRevision
0x1400177cd  mov     rcx, rsi; Acl
0x1400177d0  call    cs:__imp_RtlAddAccessAllowedAce
0x1400177d7  nop     dword ptr [rax+rax+00h]
0x1400177dc  mov     r8d, [rsp+58h+AccessMask]; AccessMask
0x1400177e1  mov     r9, r14; Sid
0x1400177e4  mov     edx, edi; AceRevision
0x1400177e6  mov     rcx, rsi; Acl
0x1400177e9  call    cs:__imp_RtlAddAccessAllowedAce
0x1400177f0  nop     dword ptr [rax+rax+00h]
0x1400177f5  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type; SecurityDescriptor
0x1400177fc  xor     r9d, r9d; DaclDefaulted
0x1400177ff  mov     r8, rsi; Dacl
0x140017802  mov     dl, 1; DaclPresent
0x140017804  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14001780b  nop     dword ptr [rax+rax+00h]
0x140017810  mov     ebx, eax
0x140017812  test    eax, eax
0x140017814  jns     short loc_14001785C
0x140017816  mov     rcx, cs:WPP_GLOBAL_Control
0x14001781d  lea     rax, WPP_GLOBAL_Control
0x140017824  cmp     rcx, rax
0x140017827  jz      short loc_140017845
0x140017829  cmp     [rcx+29h], dil
0x14001782d  jb      short loc_140017845
0x14001782f  lea     edx, [rdi+56h]
0x140017832  mov     rcx, [rcx+18h]
0x140017836  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x14001783d  mov     r9d, ebx
0x140017840  call    WPP_SF_d
0x140017845  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type; void *
0x14001784c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140017851  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, 0
0x14001785c  mov     eax, ebx
0x14001785e  add     rsp, 28h
0x140017862  pop     r15
0x140017864  pop     r14
0x140017866  pop     rdi
0x140017867  pop     rsi
0x140017868  pop     rbp
0x140017869  pop     rbx
0x14001786a  retn
```
