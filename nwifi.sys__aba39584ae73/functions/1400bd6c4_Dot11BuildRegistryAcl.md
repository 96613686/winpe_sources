# Dot11BuildRegistryAcl

- ea: `0x1400bd6c4`
- end: `0x1400bd8b4`
- name: `Dot11BuildRegistryAcl`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1400bd2d8`

## callees

- `0x140020dc0`
- `0x1400bd6c4`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400bd785`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400bd785`
- `ntoskrnl!ExAllocatePool2` at `0x1400bd79d`
- `ntoskrnl!ExAllocatePool2` at `0x1400bd79d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400bd846`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400bd846`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd857`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd857`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400bd6dc`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400bd6dc`
- `ntoskrnl!RtlMapGenericMask` at `0x1400bd6f0`
- `ntoskrnl!RtlMapGenericMask` at `0x1400bd6f0`
- `ntoskrnl!SeExports` at `0x1400bd6fc`
- `ntoskrnl!RtlLengthSid` at `0x1400bd717`
- `ntoskrnl!RtlLengthSid` at `0x1400bd728`
- `ntoskrnl!RtlLengthSid` at `0x1400bd717`
- `ntoskrnl!RtlLengthSid` at `0x1400bd728`
- `ntoskrnl!RtlCreateAcl` at `0x1400bd7cd`
- `ntoskrnl!RtlCreateAcl` at `0x1400bd7cd`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400bd7ef`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400bd811`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400bd7ef`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400bd811`

## pseudocode

```c
__int64 __fastcall Dot11BuildRegistryAcl(struct _ACL **a1)
{
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  PSID SeLocalSystemSid; // r15
  PSID SeAliasAdminsSid; // r14
  ULONG v5; // ebp
  ULONG v6; // ebp
  struct _ACL *v7; // rdi
  unsigned int v8; // eax
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
  v7 = 0;
  v8 = v6 + 56;
  if ( v6 + 56 < 0x10 )
    goto LABEL_18;
  if ( v8 > 0x40 )
  {
    if ( v8 > 0x100 )
    {
      if ( v8 > 0x400 )
      {
        if ( v8 > 0x800 )
        {
          p_WaitListHead = 0;
          Pool2 = (char *)ExAllocatePool2(64, v8, 1835627383);
          goto LABEL_12;
        }
        p_WaitListHead = &stru_1400B31C0;
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
    || (v7 = (struct _ACL *)(Pool2 + 16),
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
  Acl = RtlAddAccessAllowedAce(v7, 2u, AccessMask, SeAliasAdminsSid);
  if ( Acl < 0 )
    goto LABEL_20;
  Acl = RtlAddAccessAllowedAce(v7, 2u, AccessMask, SeLocalSystemSid);
  if ( Acl >= 0 )
  {
    *a1 = v7;
    return 0;
  }
LABEL_19:
  if ( v7 )
  {
LABEL_20:
    if ( v7[-2] )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)&v7[-2], &v7[-2]);
    else
      ExFreePoolWithTag(&v7[-2], *(_DWORD *)&v7[-1].AclRevision);
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
0x1400bd6c4  push    rbx
0x1400bd6c6  push    rbp
0x1400bd6c7  push    rsi
0x1400bd6c8  push    rdi
0x1400bd6c9  push    r14
0x1400bd6cb  push    r15
0x1400bd6cd  sub     rsp, 28h
0x1400bd6d1  mov     rsi, rcx
0x1400bd6d4  mov     [rsp+58h+AccessMask], 10000000h
0x1400bd6dc  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400bd6e3  nop     dword ptr [rax+rax+00h]
0x1400bd6e8  mov     rdx, rax; GenericMapping
0x1400bd6eb  lea     rcx, [rsp+58h+AccessMask]; AccessMask
0x1400bd6f0  call    cs:__imp_RtlMapGenericMask
0x1400bd6f7  nop     dword ptr [rax+rax+00h]
0x1400bd6fc  mov     rax, cs:__imp_SeExports
0x1400bd703  mov     rdx, [rax]
0x1400bd706  mov     r15, [rdx+108h]
0x1400bd70d  mov     r14, [rdx+110h]
0x1400bd714  mov     rcx, r15; Sid
0x1400bd717  call    cs:__imp_RtlLengthSid
0x1400bd71e  nop     dword ptr [rax+rax+00h]
0x1400bd723  mov     rcx, r14; Sid
0x1400bd726  mov     ebp, eax
0x1400bd728  call    cs:__imp_RtlLengthSid
0x1400bd72f  nop     dword ptr [rax+rax+00h]
0x1400bd734  add     ebp, eax
0x1400bd736  xor     edi, edi
0x1400bd738  lea     eax, [rbp+38h]
0x1400bd73b  cmp     eax, 10h
0x1400bd73e  jb      loc_1400BD82A
0x1400bd744  lea     ecx, [rdi+40h]
0x1400bd747  cmp     eax, ecx
0x1400bd749  ja      short loc_1400BD754
0x1400bd74b  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400bd752  jmp     short loc_1400BD782
0x1400bd754  cmp     eax, 100h
0x1400bd759  ja      short loc_1400BD764
0x1400bd75b  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400bd762  jmp     short loc_1400BD782
0x1400bd764  cmp     eax, 400h
0x1400bd769  ja      short loc_1400BD774
0x1400bd76b  lea     rbx, Lookaside
0x1400bd772  jmp     short loc_1400BD782
0x1400bd774  cmp     eax, 800h
0x1400bd779  ja      short loc_1400BD793
0x1400bd77b  lea     rbx, stru_1400B31C0
0x1400bd782  mov     rcx, rbx; Lookaside
0x1400bd785  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400bd78c  nop     dword ptr [rax+rax+00h]
0x1400bd791  jmp     short loc_1400BD7A9
0x1400bd793  xor     ebx, ebx
0x1400bd795  mov     edx, eax
0x1400bd797  mov     r8d, 6D697377h
0x1400bd79d  call    cs:__imp_ExAllocatePool2
0x1400bd7a4  nop     dword ptr [rax+rax+00h]
0x1400bd7a9  test    rax, rax
0x1400bd7ac  jz      short loc_1400BD82A
0x1400bd7ae  lea     rdi, [rax+10h]
0x1400bd7b2  mov     [rax], rbx
0x1400bd7b5  mov     dword ptr [rax+8], 6D697377h
0x1400bd7bc  test    rdi, rdi
0x1400bd7bf  jz      short loc_1400BD82A
0x1400bd7c1  mov     r8d, 2; AclRevision
0x1400bd7c7  lea     edx, [rbp+28h]; AclLength
0x1400bd7ca  mov     rcx, rdi; Acl
0x1400bd7cd  call    cs:__imp_RtlCreateAcl
0x1400bd7d4  nop     dword ptr [rax+rax+00h]
0x1400bd7d9  mov     ebx, eax
0x1400bd7db  test    eax, eax
0x1400bd7dd  js      short loc_1400BD834
0x1400bd7df  mov     r8d, [rsp+58h+AccessMask]; AccessMask
0x1400bd7e4  mov     r9, r14; Sid
0x1400bd7e7  mov     edx, 2; AceRevision
0x1400bd7ec  mov     rcx, rdi; Acl
0x1400bd7ef  call    cs:__imp_RtlAddAccessAllowedAce
0x1400bd7f6  nop     dword ptr [rax+rax+00h]
0x1400bd7fb  mov     ebx, eax
0x1400bd7fd  test    eax, eax
0x1400bd7ff  js      short loc_1400BD834
0x1400bd801  mov     r8d, [rsp+58h+AccessMask]; AccessMask
0x1400bd806  mov     r9, r15; Sid
0x1400bd809  mov     edx, 2; AceRevision
0x1400bd80e  mov     rcx, rdi; Acl
0x1400bd811  call    cs:__imp_RtlAddAccessAllowedAce
0x1400bd818  nop     dword ptr [rax+rax+00h]
0x1400bd81d  mov     ebx, eax
0x1400bd81f  test    eax, eax
0x1400bd821  js      short loc_1400BD82F
0x1400bd823  mov     [rsi], rdi
0x1400bd826  xor     eax, eax
0x1400bd828  jmp     short loc_1400BD8A6
0x1400bd82a  mov     ebx, 0C000009Ah
0x1400bd82f  test    rdi, rdi
0x1400bd832  jz      short loc_1400BD863
0x1400bd834  lea     rcx, [rdi-10h]; P
0x1400bd838  mov     rax, [rcx]
0x1400bd83b  test    rax, rax
0x1400bd83e  jz      short loc_1400BD854
0x1400bd840  mov     rdx, rcx; Entry
0x1400bd843  mov     rcx, rax; Lookaside
0x1400bd846  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400bd84d  nop     dword ptr [rax+rax+00h]
0x1400bd852  jmp     short loc_1400BD863
0x1400bd854  mov     edx, [rcx+8]; Tag
0x1400bd857  call    cs:__imp_ExFreePoolWithTag
0x1400bd85e  nop     dword ptr [rax+rax+00h]
0x1400bd863  mov     qword ptr [rsi], 0
0x1400bd86a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bd871  lea     rax, WPP_GLOBAL_Control
0x1400bd878  cmp     rcx, rax
0x1400bd87b  jz      short loc_1400BD8A4
0x1400bd87d  cmp     byte ptr [rcx+29h], 4
0x1400bd881  jb      short loc_1400BD8A4
0x1400bd883  test    dword ptr [rcx+2Ch], 200h
0x1400bd88a  jz      short loc_1400BD8A4
0x1400bd88c  mov     rcx, [rcx+18h]
0x1400bd890  lea     r8, WPP_a01680d69d263cc9eb0985aaa3057085_Traceguids
0x1400bd897  mov     edx, 0Eh
0x1400bd89c  mov     r9d, ebx
0x1400bd89f  call    WPP_SF_d
0x1400bd8a4  mov     eax, ebx
0x1400bd8a6  add     rsp, 28h
0x1400bd8aa  pop     r15
0x1400bd8ac  pop     r14
0x1400bd8ae  pop     rdi
0x1400bd8af  pop     rsi
0x1400bd8b0  pop     rbp
0x1400bd8b1  pop     rbx
0x1400bd8b2  retn
```
