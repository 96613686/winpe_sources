# Dot11BuildRegistryAcl

- ea: `0x1400ba714`
- end: `0x1400ba904`
- name: `Dot11BuildRegistryAcl`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1400ba328`

## callees

- `0x140020dc0`
- `0x1400ba714`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400ba7d5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400ba7d5`
- `ntoskrnl!ExAllocatePool2` at `0x1400ba7ed`
- `ntoskrnl!ExAllocatePool2` at `0x1400ba7ed`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba896`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba896`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba8a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba8a7`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400ba72c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400ba72c`
- `ntoskrnl!RtlMapGenericMask` at `0x1400ba740`
- `ntoskrnl!RtlMapGenericMask` at `0x1400ba740`
- `ntoskrnl!SeExports` at `0x1400ba74c`
- `ntoskrnl!RtlLengthSid` at `0x1400ba767`
- `ntoskrnl!RtlLengthSid` at `0x1400ba778`
- `ntoskrnl!RtlLengthSid` at `0x1400ba767`
- `ntoskrnl!RtlLengthSid` at `0x1400ba778`
- `ntoskrnl!RtlCreateAcl` at `0x1400ba81d`
- `ntoskrnl!RtlCreateAcl` at `0x1400ba81d`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400ba83f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400ba861`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400ba83f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400ba861`

## pseudocode

```c
__int64 __fastcall Dot11BuildRegistryAcl(struct _ACL **a1)
{
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  PSID SeLocalSystemSid; // r15
  PSID SeAliasAdminsSid; // r14
  ULONG v5; // ebp
  ULONG v6; // ebp
  __int64 v7; // r9
  struct _ACL *v8; // rdi
  unsigned int v9; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  char *Pool2; // rax
  NTSTATUS Acl; // ebx
  DWORD AccessMask; // [rsp+68h] [rbp+10h] BYREF

  AccessMask = 0x10000000;
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
  SeLocalSystemSid = SeExports->SeLocalSystemSid;
  SeAliasAdminsSid = SeExports->SeAliasAdminsSid;
  v5 = RtlLengthSid(SeLocalSystemSid);
  v6 = RtlLengthSid(SeAliasAdminsSid) + v5;
  v8 = 0;
  v9 = v6 + 56;
  if ( v6 + 56 < 0x10 )
    goto LABEL_18;
  if ( v9 > 0x40 )
  {
    if ( v9 > 0x100 )
    {
      if ( v9 > 0x400 )
      {
        if ( v9 > 0x800 )
        {
          p_WaitListHead = 0;
          Pool2 = (char *)ExAllocatePool2(64, v9, 1835627383, v7);
          goto LABEL_12;
        }
        p_WaitListHead = &stru_1400B0180;
      }
      else
      {
        p_WaitListHead = &Lookaside;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    }
  }
  else
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
  }
  Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_WaitListHead);
LABEL_12:
  if ( !Pool2
    || (v8 = (struct _ACL *)(Pool2 + 16),
        *(_QWORD *)Pool2 = p_WaitListHead,
        *((_DWORD *)Pool2 + 2) = 1835627383,
        Pool2 == (char *)-16LL) )
  {
LABEL_18:
    Acl = -1073741670;
    goto LABEL_19;
  }
  Acl = RtlCreateAcl((PACL)Pool2 + 2, v6 + 40, 2u);
  if ( Acl < 0 )
    goto LABEL_20;
  Acl = RtlAddAccessAllowedAce(v8, 2u, AccessMask, SeAliasAdminsSid);
  if ( Acl < 0 )
    goto LABEL_20;
  Acl = RtlAddAccessAllowedAce(v8, 2u, AccessMask, SeLocalSystemSid);
  if ( Acl >= 0 )
  {
    *a1 = v8;
    return 0;
  }
LABEL_19:
  if ( v8 )
  {
LABEL_20:
    if ( v8[-2] )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)&v8[-2], &v8[-2]);
    else
      ExFreePoolWithTag(&v8[-2], *(_DWORD *)&v8[-1].AclRevision);
  }
  *a1 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_a01680d69d263cc9eb0985aaa3057085_Traceguids, (unsigned int)Acl);
  }
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x1400ba714  push    rbx
0x1400ba716  push    rbp
0x1400ba717  push    rsi
0x1400ba718  push    rdi
0x1400ba719  push    r14
0x1400ba71b  push    r15
0x1400ba71d  sub     rsp, 28h
0x1400ba721  mov     rsi, rcx
0x1400ba724  mov     [rsp+58h+AccessMask], 10000000h
0x1400ba72c  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400ba733  nop     dword ptr [rax+rax+00h]
0x1400ba738  mov     rdx, rax; GenericMapping
0x1400ba73b  lea     rcx, [rsp+58h+AccessMask]; AccessMask
0x1400ba740  call    cs:__imp_RtlMapGenericMask
0x1400ba747  nop     dword ptr [rax+rax+00h]
0x1400ba74c  mov     rax, cs:__imp_SeExports
0x1400ba753  mov     rdx, [rax]
0x1400ba756  mov     r15, [rdx+108h]
0x1400ba75d  mov     r14, [rdx+110h]
0x1400ba764  mov     rcx, r15; Sid
0x1400ba767  call    cs:__imp_RtlLengthSid
0x1400ba76e  nop     dword ptr [rax+rax+00h]
0x1400ba773  mov     rcx, r14; Sid
0x1400ba776  mov     ebp, eax
0x1400ba778  call    cs:__imp_RtlLengthSid
0x1400ba77f  nop     dword ptr [rax+rax+00h]
0x1400ba784  add     ebp, eax
0x1400ba786  xor     edi, edi
0x1400ba788  lea     eax, [rbp+38h]
0x1400ba78b  cmp     eax, 10h
0x1400ba78e  jb      loc_1400BA87A
0x1400ba794  lea     ecx, [rdi+40h]
0x1400ba797  cmp     eax, ecx
0x1400ba799  ja      short loc_1400BA7A4
0x1400ba79b  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400ba7a2  jmp     short loc_1400BA7D2
0x1400ba7a4  cmp     eax, 100h
0x1400ba7a9  ja      short loc_1400BA7B4
0x1400ba7ab  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400ba7b2  jmp     short loc_1400BA7D2
0x1400ba7b4  cmp     eax, 400h
0x1400ba7b9  ja      short loc_1400BA7C4
0x1400ba7bb  lea     rbx, Lookaside
0x1400ba7c2  jmp     short loc_1400BA7D2
0x1400ba7c4  cmp     eax, 800h
0x1400ba7c9  ja      short loc_1400BA7E3
0x1400ba7cb  lea     rbx, stru_1400B0180
0x1400ba7d2  mov     rcx, rbx; Lookaside
0x1400ba7d5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400ba7dc  nop     dword ptr [rax+rax+00h]
0x1400ba7e1  jmp     short loc_1400BA7F9
0x1400ba7e3  xor     ebx, ebx
0x1400ba7e5  mov     edx, eax
0x1400ba7e7  mov     r8d, 6D697377h
0x1400ba7ed  call    cs:__imp_ExAllocatePool2
0x1400ba7f4  nop     dword ptr [rax+rax+00h]
0x1400ba7f9  test    rax, rax
0x1400ba7fc  jz      short loc_1400BA87A
0x1400ba7fe  lea     rdi, [rax+10h]
0x1400ba802  mov     [rax], rbx
0x1400ba805  mov     dword ptr [rax+8], 6D697377h
0x1400ba80c  test    rdi, rdi
0x1400ba80f  jz      short loc_1400BA87A
0x1400ba811  mov     r8d, 2; AclRevision
0x1400ba817  lea     edx, [rbp+28h]; AclLength
0x1400ba81a  mov     rcx, rdi; Acl
0x1400ba81d  call    cs:__imp_RtlCreateAcl
0x1400ba824  nop     dword ptr [rax+rax+00h]
0x1400ba829  mov     ebx, eax
0x1400ba82b  test    eax, eax
0x1400ba82d  js      short loc_1400BA884
0x1400ba82f  mov     r8d, [rsp+58h+AccessMask]; AccessMask
0x1400ba834  mov     r9, r14; Sid
0x1400ba837  mov     edx, 2; AceRevision
0x1400ba83c  mov     rcx, rdi; Acl
0x1400ba83f  call    cs:__imp_RtlAddAccessAllowedAce
0x1400ba846  nop     dword ptr [rax+rax+00h]
0x1400ba84b  mov     ebx, eax
0x1400ba84d  test    eax, eax
0x1400ba84f  js      short loc_1400BA884
0x1400ba851  mov     r8d, [rsp+58h+AccessMask]; AccessMask
0x1400ba856  mov     r9, r15; Sid
0x1400ba859  mov     edx, 2; AceRevision
0x1400ba85e  mov     rcx, rdi; Acl
0x1400ba861  call    cs:__imp_RtlAddAccessAllowedAce
0x1400ba868  nop     dword ptr [rax+rax+00h]
0x1400ba86d  mov     ebx, eax
0x1400ba86f  test    eax, eax
0x1400ba871  js      short loc_1400BA87F
0x1400ba873  mov     [rsi], rdi
0x1400ba876  xor     eax, eax
0x1400ba878  jmp     short loc_1400BA8F6
0x1400ba87a  mov     ebx, 0C000009Ah
0x1400ba87f  test    rdi, rdi
0x1400ba882  jz      short loc_1400BA8B3
0x1400ba884  lea     rcx, [rdi-10h]; P
0x1400ba888  mov     rax, [rcx]
0x1400ba88b  test    rax, rax
0x1400ba88e  jz      short loc_1400BA8A4
0x1400ba890  mov     rdx, rcx; Entry
0x1400ba893  mov     rcx, rax; Lookaside
0x1400ba896  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400ba89d  nop     dword ptr [rax+rax+00h]
0x1400ba8a2  jmp     short loc_1400BA8B3
0x1400ba8a4  mov     edx, [rcx+8]; Tag
0x1400ba8a7  call    cs:__imp_ExFreePoolWithTag
0x1400ba8ae  nop     dword ptr [rax+rax+00h]
0x1400ba8b3  mov     qword ptr [rsi], 0
0x1400ba8ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba8c1  lea     rax, WPP_GLOBAL_Control
0x1400ba8c8  cmp     rcx, rax
0x1400ba8cb  jz      short loc_1400BA8F4
0x1400ba8cd  cmp     byte ptr [rcx+29h], 4
0x1400ba8d1  jb      short loc_1400BA8F4
0x1400ba8d3  test    dword ptr [rcx+2Ch], 200h
0x1400ba8da  jz      short loc_1400BA8F4
0x1400ba8dc  mov     rcx, [rcx+18h]
0x1400ba8e0  lea     r8, WPP_a01680d69d263cc9eb0985aaa3057085_Traceguids
0x1400ba8e7  mov     edx, 0Eh
0x1400ba8ec  mov     r9d, ebx
0x1400ba8ef  call    WPP_SF_d
0x1400ba8f4  mov     eax, ebx
0x1400ba8f6  add     rsp, 28h
0x1400ba8fa  pop     r15
0x1400ba8fc  pop     r14
0x1400ba8fe  pop     rdi
0x1400ba8ff  pop     rsi
0x1400ba900  pop     rbp
0x1400ba901  pop     rbx
0x1400ba902  retn
```
