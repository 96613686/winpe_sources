# InitializeRdpBusSecurity

- ea: `0x14000857c`
- end: `0x14000880a`
- name: `InitializeRdpBusSecurity`
- size: `654`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000b078`

## callees

- `0x1400020b4`
- `0x1400020e4`
- `0x14000857c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140008615`
- `ntoskrnl!ExAllocatePool2` at `0x140008615`
- `ntoskrnl!RtlMapGenericMask` at `0x1400086f3`
- `ntoskrnl!RtlMapGenericMask` at `0x1400086f3`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000878c`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000878c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400086df`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400086df`
- `ntoskrnl!RtlLengthSid` at `0x1400085e6`
- `ntoskrnl!RtlLengthSid` at `0x1400085f7`
- `ntoskrnl!RtlLengthSid` at `0x1400085e6`
- `ntoskrnl!RtlLengthSid` at `0x1400085f7`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000870f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140008752`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000870f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140008752`
- `ntoskrnl!RtlCreateAcl` at `0x1400086a9`
- `ntoskrnl!RtlCreateAcl` at `0x1400086a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400087d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400087d5`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140008663`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140008663`
- `ntoskrnl!SeExports` at `0x1400085cb`

## pseudocode

```c
__int64 InitializeRdpBusSecurity()
{
  PSID SeAliasAdminsSid; // rbp
  PSID SeLocalSystemSid; // r14
  ULONG v2; // ebx
  ULONG v3; // esi
  struct _ACL *Pool2; // rax
  struct _ACL *v5; // rdi
  NTSTATUS SecurityDescriptor; // eax
  unsigned int v8; // ebx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  struct _ACL *v11; // rdi
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  DWORD AccessMask; // [rsp+50h] [rbp+8h] BYREF

  AccessMask = 0x10000000;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_decc11c9483a3275477ae1b226799886_Traceguids);
  SeAliasAdminsSid = SeExports->SeAliasAdminsSid;
  SeLocalSystemSid = SeExports->SeLocalSystemSid;
  v2 = RtlLengthSid(SeAliasAdminsSid);
  v3 = v2 + RtlLengthSid(SeLocalSystemSid) + 72;
  Pool2 = (struct _ACL *)ExAllocatePool2(256, v3, 1114662002);
  *(_QWORD *)&WPP_MAIN_CB.DeviceType = Pool2;
  v5 = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_decc11c9483a3275477ae1b226799886_Traceguids);
    return 3221225495LL;
  }
  SecurityDescriptor = RtlCreateSecurityDescriptor(Pool2, 1u);
  v8 = SecurityDescriptor;
  if ( SecurityDescriptor >= 0 )
  {
    v11 = v5 + 5;
    SecurityDescriptor = RtlCreateAcl(v11, v3 - 40, 2u);
    v8 = SecurityDescriptor;
    if ( SecurityDescriptor >= 0 )
    {
      FileObjectGenericMapping = IoGetFileObjectGenericMapping();
      RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
      SecurityDescriptor = RtlAddAccessAllowedAce(v11, 2u, AccessMask, SeLocalSystemSid);
      v8 = SecurityDescriptor;
      if ( SecurityDescriptor >= 0 )
      {
        SecurityDescriptor = RtlAddAccessAllowedAce(v11, 2u, AccessMask, SeAliasAdminsSid);
        v8 = SecurityDescriptor;
        if ( SecurityDescriptor >= 0 )
        {
          SecurityDescriptor = RtlSetDaclSecurityDescriptor(
                                 *(PSECURITY_DESCRIPTOR *)&WPP_MAIN_CB.DeviceType,
                                 1u,
                                 v11,
                                 0);
          v8 = SecurityDescriptor;
          if ( SecurityDescriptor >= 0 )
            return 0;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            goto LABEL_30;
          v10 = 16;
        }
        else
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            goto LABEL_30;
          v10 = 15;
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_30;
        v10 = 14;
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_30;
      v10 = 13;
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_30;
    v10 = 12;
  }
  WPP_SF_D(v9->AttachedDevice, v10, WPP_decc11c9483a3275477ae1b226799886_Traceguids, (unsigned int)SecurityDescriptor);
LABEL_30:
  if ( *(_QWORD *)&WPP_MAIN_CB.DeviceType )
  {
    ExFreePoolWithTag(*(PVOID *)&WPP_MAIN_CB.DeviceType, 0x42706472u);
    *(_QWORD *)&WPP_MAIN_CB.DeviceType = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x14000857c  mov     [rsp+arg_8], rbx
0x140008581  mov     [rsp+arg_10], rbp
0x140008586  push    rsi
0x140008587  push    rdi
0x140008588  push    r12
0x14000858a  push    r14
0x14000858c  push    r15
0x14000858e  sub     rsp, 20h
0x140008592  mov     [rsp+48h+AccessMask], 10000000h
0x14000859a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400085a1  lea     r15, WPP_GLOBAL_Control
0x1400085a8  lea     r12, WPP_decc11c9483a3275477ae1b226799886_Traceguids
0x1400085af  cmp     rcx, r15
0x1400085b2  jz      short loc_1400085CB
0x1400085b4  cmp     byte ptr [rcx+29h], 4
0x1400085b8  jb      short loc_1400085CB
0x1400085ba  mov     rcx, [rcx+18h]
0x1400085be  mov     edx, 0Ah
0x1400085c3  mov     r8, r12
0x1400085c6  call    WPP_SF_
0x1400085cb  mov     rax, cs:__imp_SeExports
0x1400085d2  mov     rcx, [rax]
0x1400085d5  mov     rbp, [rcx+110h]
0x1400085dc  mov     r14, [rcx+108h]
0x1400085e3  mov     rcx, rbp; Sid
0x1400085e6  call    cs:__imp_RtlLengthSid
0x1400085ed  nop     dword ptr [rax+rax+00h]
0x1400085f2  mov     rcx, r14; Sid
0x1400085f5  mov     ebx, eax
0x1400085f7  call    cs:__imp_RtlLengthSid
0x1400085fe  nop     dword ptr [rax+rax+00h]
0x140008603  mov     ecx, 100h
0x140008608  mov     r8d, 42706472h
0x14000860e  lea     esi, [rax+48h]
0x140008611  add     esi, ebx
0x140008613  mov     edx, esi
0x140008615  call    cs:__imp_ExAllocatePool2
0x14000861c  nop     dword ptr [rax+rax+00h]
0x140008621  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rax
0x140008628  mov     rdi, rax
0x14000862b  test    rax, rax
0x14000862e  jnz     short loc_14000865B
0x140008630  mov     rcx, cs:WPP_GLOBAL_Control
0x140008637  cmp     rcx, r15
0x14000863a  jz      short loc_140008651
0x14000863c  cmp     byte ptr [rcx+29h], 2
0x140008640  jb      short loc_140008651
0x140008642  mov     rcx, [rcx+18h]
0x140008646  lea     edx, [rax+0Bh]
0x140008649  mov     r8, r12
0x14000864c  call    WPP_SF_
0x140008651  mov     eax, 0C0000017h
0x140008656  jmp     loc_1400087F2
0x14000865b  mov     edx, 1; Revision
0x140008660  mov     rcx, rdi; SecurityDescriptor
0x140008663  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000866a  nop     dword ptr [rax+rax+00h]
0x14000866f  mov     ebx, eax
0x140008671  test    eax, eax
0x140008673  jns     short loc_140008699
0x140008675  mov     rcx, cs:WPP_GLOBAL_Control
0x14000867c  cmp     rcx, r15
0x14000867f  jz      loc_1400087C4
0x140008685  cmp     byte ptr [rcx+29h], 2
0x140008689  jb      loc_1400087C4
0x14000868f  mov     edx, 0Ch
0x140008694  jmp     loc_1400087B5
0x140008699  add     rdi, 28h ; '('
0x14000869d  lea     edx, [rsi-28h]; AclLength
0x1400086a0  mov     rcx, rdi; Acl
0x1400086a3  mov     r8d, 2; AclRevision
0x1400086a9  call    cs:__imp_RtlCreateAcl
0x1400086b0  nop     dword ptr [rax+rax+00h]
0x1400086b5  mov     ebx, eax
0x1400086b7  test    eax, eax
0x1400086b9  jns     short loc_1400086DF
0x1400086bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400086c2  cmp     rcx, r15
0x1400086c5  jz      loc_1400087C4
0x1400086cb  cmp     byte ptr [rcx+29h], 2
0x1400086cf  jb      loc_1400087C4
0x1400086d5  mov     edx, 0Dh
0x1400086da  jmp     loc_1400087B5
0x1400086df  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400086e6  nop     dword ptr [rax+rax+00h]
0x1400086eb  mov     rdx, rax; GenericMapping
0x1400086ee  lea     rcx, [rsp+48h+AccessMask]; AccessMask
0x1400086f3  call    cs:__imp_RtlMapGenericMask
0x1400086fa  nop     dword ptr [rax+rax+00h]
0x1400086ff  mov     r8d, [rsp+48h+AccessMask]; AccessMask
0x140008704  mov     r9, r14; Sid
0x140008707  mov     edx, 2; AceRevision
0x14000870c  mov     rcx, rdi; Acl
0x14000870f  call    cs:__imp_RtlAddAccessAllowedAce
0x140008716  nop     dword ptr [rax+rax+00h]
0x14000871b  mov     ebx, eax
0x14000871d  test    eax, eax
0x14000871f  jns     short loc_140008742
0x140008721  mov     rcx, cs:WPP_GLOBAL_Control
0x140008728  cmp     rcx, r15
0x14000872b  jz      loc_1400087C4
0x140008731  cmp     byte ptr [rcx+29h], 2
0x140008735  jb      loc_1400087C4
0x14000873b  mov     edx, 0Eh
0x140008740  jmp     short loc_1400087B5
0x140008742  mov     r8d, [rsp+48h+AccessMask]; AccessMask
0x140008747  mov     r9, rbp; Sid
0x14000874a  mov     edx, 2; AceRevision
0x14000874f  mov     rcx, rdi; Acl
0x140008752  call    cs:__imp_RtlAddAccessAllowedAce
0x140008759  nop     dword ptr [rax+rax+00h]
0x14000875e  mov     ebx, eax
0x140008760  test    eax, eax
0x140008762  jns     short loc_14000877D
0x140008764  mov     rcx, cs:WPP_GLOBAL_Control
0x14000876b  cmp     rcx, r15
0x14000876e  jz      short loc_1400087C4
0x140008770  cmp     byte ptr [rcx+29h], 2
0x140008774  jb      short loc_1400087C4
0x140008776  mov     edx, 0Fh
0x14000877b  jmp     short loc_1400087B5
0x14000877d  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceType; SecurityDescriptor
0x140008784  xor     r9d, r9d; DaclDefaulted
0x140008787  mov     r8, rdi; Dacl
0x14000878a  mov     dl, 1; DaclPresent
0x14000878c  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140008793  nop     dword ptr [rax+rax+00h]
0x140008798  mov     ebx, eax
0x14000879a  test    eax, eax
0x14000879c  jns     short loc_1400087F0
0x14000879e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400087a5  cmp     rcx, r15
0x1400087a8  jz      short loc_1400087C4
0x1400087aa  cmp     byte ptr [rcx+29h], 2
0x1400087ae  jb      short loc_1400087C4
0x1400087b0  mov     edx, 10h
0x1400087b5  mov     rcx, [rcx+18h]
0x1400087b9  mov     r9d, eax
0x1400087bc  mov     r8, r12
0x1400087bf  call    WPP_SF_D
0x1400087c4  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceType; P
0x1400087cb  test    rcx, rcx
0x1400087ce  jz      short loc_1400087EC
0x1400087d0  mov     edx, 42706472h; Tag
0x1400087d5  call    cs:__imp_ExFreePoolWithTag
0x1400087dc  nop     dword ptr [rax+rax+00h]
0x1400087e1  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, 0
0x1400087ec  mov     eax, ebx
0x1400087ee  jmp     short loc_1400087F2
0x1400087f0  xor     eax, eax
0x1400087f2  mov     rbx, [rsp+48h+arg_8]
0x1400087f7  mov     rbp, [rsp+48h+arg_10]
0x1400087fc  add     rsp, 20h
0x140008800  pop     r15
0x140008802  pop     r14
0x140008804  pop     r12
0x140008806  pop     rdi
0x140008807  pop     rsi
0x140008808  retn
```
