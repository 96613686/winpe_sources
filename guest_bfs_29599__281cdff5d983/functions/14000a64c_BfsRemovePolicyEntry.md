# BfsRemovePolicyEntry

- ea: `0x14000a64c`
- end: `0x14000a927`
- name: `BfsRemovePolicyEntry`
- size: `731`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140009520`

## callees

- `0x140001008`
- `0x1400017b0`
- `0x1400061d0`
- `0x140008e38`
- `0x140008ecc`
- `0x14000a64c`
- `0x14000d58c`
- `0x140012d00`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000a703`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000a703`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000a8a3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000a8a3`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000a780`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000a7bc`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000a780`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000a7bc`
- `ntoskrnl!RtlLengthSid` at `0x14000a6ac`
- `ntoskrnl!RtlLengthSid` at `0x14000a6ca`
- `ntoskrnl!RtlLengthSid` at `0x14000a6ac`
- `ntoskrnl!RtlLengthSid` at `0x14000a6ca`
- `ntoskrnl!ZwDeleteFile` at `0x14000a857`
- `ntoskrnl!ZwDeleteFile` at `0x14000a857`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a758`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a76a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a758`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a76a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000a8c6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000a8dd`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000a8c6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000a8dd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a6f2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a6f2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a8af`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a8af`
- `FLTMGR!FltClose` at `0x14000a8f1`
- `FLTMGR!FltClose` at `0x14000a8f1`

## pseudocode

```c
__int64 __fastcall BfsRemovePolicyEntry(int a1, __int64 a2, __int64 a3, void *a4, PSID Sid)
{
  HANDLE v6; // rdi
  ULONG v9; // eax
  ULONG v10; // eax
  __int64 v11; // rax
  void *v12; // rbx
  NTSTATUS v13; // eax
  int v14; // r8d
  int v15; // r9d
  NTSTATUS v16; // ebx
  int v17; // ecx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v22; // [rsp+20h] [rbp-91h]
  __int64 v23; // [rsp+30h] [rbp-81h] BYREF
  int v24[2]; // [rsp+38h] [rbp-79h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-71h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-61h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v28; // [rsp+90h] [rbp-21h] BYREF
  __int64 *v29; // [rsp+B0h] [rbp-1h]
  __int64 v30; // [rsp+B8h] [rbp+7h]

  *(_QWORD *)v24 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v6 = 0;
  v23 = 0;
  UnicodeString = 0;
  DestinationString = 0;
  v9 = RtlLengthSid(a4);
  BfsUpdateHash(a4, v9, &v23);
  v10 = RtlLengthSid(Sid);
  BfsUpdateHash(Sid, v10, &v23);
  BfsFinalHash(&v23);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a3, 0);
  v11 = BfsLookupPolicyEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a3 + 8));
  v12 = (void *)v11;
  if ( v11 )
  {
    if ( *(_DWORD *)(v11 + 56) != 0x10000000 )
    {
      v16 = 0;
      goto LABEL_17;
    }
    *(_DWORD *)(v11 + 56) = 268435458;
    BfsRemoveAllPoliciesFromGlobalFileTable(&gBfsGlobalFileTable, v11);
    BfsDereferencePolicyEntryEx(v12);
  }
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&UnicodeString, 0);
  v13 = RtlConvertSidToUnicodeString(&DestinationString, a4, 1u);
  v16 = v13;
  if ( v13 < 0 )
  {
    v17 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_17;
    LODWORD(v23) = v13;
LABEL_16:
    v30 = 4;
    v29 = &v23;
    tlgWriteTransfer_EtwWriteTransfer(v17, (int)&byte_140016D91, v14, v15, v22, &v28);
    goto LABEL_17;
  }
  v16 = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u);
  if ( v16 < 0 )
  {
LABEL_14:
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_17;
    LODWORD(v23) = v16;
    goto LABEL_16;
  }
  LOBYTE(v15) = 1;
  v16 = BfsOpenPolicyDirectory(a1, 0, (unsigned int)&DestinationString, v15, (__int64)v24);
  if ( v16 >= 0 )
  {
    v6 = *(HANDLE *)v24;
    ObjectAttributes.RootDirectory = *(HANDLE *)v24;
    ObjectAttributes.ObjectName = &UnicodeString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 64;
    v16 = ZwDeleteFile(&ObjectAttributes);
    if ( v16 >= 0 )
      goto LABEL_17;
    goto LABEL_14;
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    LODWORD(v23) = v16;
    v29 = &v23;
    v30 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v18, (int)&byte_140016D91, v19, v20, v22, &v28);
  }
  v6 = *(HANDLE *)v24;
LABEL_17:
  ExReleasePushLockExclusiveEx(a3, 0);
  KeLeaveCriticalRegion();
  if ( UnicodeString.Length )
    RtlFreeUnicodeString(&UnicodeString);
  if ( DestinationString.Length )
    RtlFreeUnicodeString(&DestinationString);
  if ( v6 )
    FltClose(v6);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14000a64c  mov     [rsp-8+arg_8], rbx
0x14000a651  push    rbp
0x14000a652  push    rsi
0x14000a653  push    rdi
0x14000a654  push    r12
0x14000a656  push    r13
0x14000a658  push    r14
0x14000a65a  push    r15
0x14000a65c  lea     rbp, [rsp-1Fh]
0x14000a661  sub     rsp, 0D0h
0x14000a668  mov     rax, cs:__security_cookie
0x14000a66f  xor     rax, rsp
0x14000a672  mov     [rbp+4Fh+var_40], rax
0x14000a676  mov     rsi, [rbp+4Fh+Sid]
0x14000a67a  xorps   xmm0, xmm0
0x14000a67d  xor     r13d, r13d
0x14000a680  mov     r12, rcx
0x14000a683  mov     rcx, r9; Sid
0x14000a686  mov     qword ptr [rbp+4Fh+var_C8], r13
0x14000a68a  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x14000a68e  mov     edi, r13d
0x14000a691  mov     [rsp+100h+var_D0], r13
0x14000a696  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x14000a69a  mov     r14, r9
0x14000a69d  mov     r15, r8
0x14000a6a0  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14000a6a4  movups  xmmword ptr [rbp+4Fh+UnicodeString.Length], xmm0
0x14000a6a8  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x14000a6ac  call    cs:__imp_RtlLengthSid
0x14000a6b3  nop     dword ptr [rax+rax+00h]
0x14000a6b8  lea     r8, [rsp+100h+var_D0]
0x14000a6bd  mov     rcx, r14
0x14000a6c0  mov     edx, eax
0x14000a6c2  call    BfsUpdateHash
0x14000a6c7  mov     rcx, rsi; Sid
0x14000a6ca  call    cs:__imp_RtlLengthSid
0x14000a6d1  nop     dword ptr [rax+rax+00h]
0x14000a6d6  lea     r8, [rsp+100h+var_D0]
0x14000a6db  mov     rcx, rsi
0x14000a6de  mov     edx, eax
0x14000a6e0  call    BfsUpdateHash
0x14000a6e5  lea     rcx, [rsp+100h+var_D0]
0x14000a6ea  call    BfsFinalHash
0x14000a6ef  mov     rbx, rax
0x14000a6f2  call    cs:__imp_KeEnterCriticalRegion
0x14000a6f9  nop     dword ptr [rax+rax+00h]
0x14000a6fe  xor     edx, edx
0x14000a700  mov     rcx, r15
0x14000a703  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000a70a  nop     dword ptr [rax+rax+00h]
0x14000a70f  mov     rcx, [r15+8]; HashTable
0x14000a713  mov     r9, rsi
0x14000a716  mov     r8, r14
0x14000a719  mov     rdx, rbx
0x14000a71c  call    BfsLookupPolicyEntryHashTable
0x14000a721  mov     rbx, rax
0x14000a724  test    rax, rax
0x14000a727  jz      short loc_14000A752
0x14000a729  cmp     dword ptr [rax+38h], 10000000h
0x14000a730  jnz     short loc_14000A7AA
0x14000a732  mov     rdx, rax
0x14000a735  mov     dword ptr [rax+38h], 10000002h
0x14000a73c  lea     rcx, gBfsGlobalFileTable
0x14000a743  call    BfsRemoveAllPoliciesFromGlobalFileTable
0x14000a748  mov     dl, 1
0x14000a74a  mov     rcx, rbx; P
0x14000a74d  call    BfsDereferencePolicyEntryEx
0x14000a752  xor     edx, edx; SourceString
0x14000a754  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x14000a758  call    cs:__imp_RtlInitUnicodeString
0x14000a75f  nop     dword ptr [rax+rax+00h]
0x14000a764  xor     edx, edx; SourceString
0x14000a766  lea     rcx, [rbp+4Fh+UnicodeString]; DestinationString
0x14000a76a  call    cs:__imp_RtlInitUnicodeString
0x14000a771  nop     dword ptr [rax+rax+00h]
0x14000a776  mov     r8b, 1; AllocateDestinationString
0x14000a779  lea     rcx, [rbp+4Fh+DestinationString]; UnicodeString
0x14000a77d  mov     rdx, r14; Sid
0x14000a780  call    cs:__imp_RtlConvertSidToUnicodeString
0x14000a787  nop     dword ptr [rax+rax+00h]
0x14000a78c  mov     ebx, eax
0x14000a78e  test    eax, eax
0x14000a790  jns     short loc_14000A7B2
0x14000a792  mov     ecx, cs:dword_140019000
0x14000a798  cmp     ecx, 3
0x14000a79b  jbe     loc_14000A89E
0x14000a7a1  mov     dword ptr [rsp+100h+var_D0], eax
0x14000a7a5  jmp     loc_14000A878
0x14000a7aa  mov     ebx, r13d
0x14000a7ad  jmp     loc_14000A89E
0x14000a7b2  mov     r8b, 1; AllocateDestinationString
0x14000a7b5  lea     rcx, [rbp+4Fh+UnicodeString]; UnicodeString
0x14000a7b9  mov     rdx, rsi; Sid
0x14000a7bc  call    cs:__imp_RtlConvertSidToUnicodeString
0x14000a7c3  nop     dword ptr [rax+rax+00h]
0x14000a7c8  mov     ebx, eax
0x14000a7ca  test    eax, eax
0x14000a7cc  js      loc_14000A869
0x14000a7d2  lea     rax, [rbp+4Fh+var_C8]
0x14000a7d6  mov     r9b, 1
0x14000a7d9  lea     r8, [rbp+4Fh+DestinationString]
0x14000a7dd  mov     qword ptr [rsp+100h+var_E0], rax; int
0x14000a7e2  xor     edx, edx
0x14000a7e4  mov     rcx, r12
0x14000a7e7  call    BfsOpenPolicyDirectory
0x14000a7ec  mov     ebx, eax
0x14000a7ee  test    eax, eax
0x14000a7f0  jns     short loc_14000A82D
0x14000a7f2  mov     eax, cs:dword_140019000
0x14000a7f8  cmp     eax, 3
0x14000a7fb  jbe     short loc_14000A827
0x14000a7fd  lea     rax, [rsp+100h+var_D0]
0x14000a802  mov     dword ptr [rsp+100h+var_D0], ebx
0x14000a806  mov     [rbp+4Fh+var_50], rax
0x14000a80a  lea     rdx, byte_140016D91; int
0x14000a811  lea     rax, [rbp+4Fh+var_70]
0x14000a815  mov     [rbp+4Fh+var_48], 4
0x14000a81d  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x14000a822  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a827  mov     rdi, qword ptr [rbp+4Fh+var_C8]
0x14000a82b  jmp     short loc_14000A89E
0x14000a82d  mov     rdi, qword ptr [rbp+4Fh+var_C8]
0x14000a831  lea     rax, [rbp+4Fh+UnicodeString]
0x14000a835  xorps   xmm0, xmm0
0x14000a838  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rdi
0x14000a83c  lea     rcx, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x14000a840  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x14000a844  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14000a849  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x14000a850  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x14000a857  call    cs:__imp_ZwDeleteFile
0x14000a85e  nop     dword ptr [rax+rax+00h]
0x14000a863  mov     ebx, eax
0x14000a865  test    eax, eax
0x14000a867  jns     short loc_14000A89E
0x14000a869  mov     eax, cs:dword_140019000
0x14000a86f  cmp     eax, 3
0x14000a872  jbe     short loc_14000A89E
0x14000a874  mov     dword ptr [rsp+100h+var_D0], ebx
0x14000a878  lea     rax, [rsp+100h+var_D0]
0x14000a87d  mov     [rbp+4Fh+var_48], 4
0x14000a885  mov     [rbp+4Fh+var_50], rax
0x14000a889  lea     rdx, byte_140016D91; int
0x14000a890  lea     rax, [rbp+4Fh+var_70]
0x14000a894  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x14000a899  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a89e  xor     edx, edx
0x14000a8a0  mov     rcx, r15
0x14000a8a3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000a8aa  nop     dword ptr [rax+rax+00h]
0x14000a8af  call    cs:__imp_KeLeaveCriticalRegion
0x14000a8b6  nop     dword ptr [rax+rax+00h]
0x14000a8bb  cmp     [rbp+4Fh+UnicodeString.Length], r13w
0x14000a8c0  jbe     short loc_14000A8D2
0x14000a8c2  lea     rcx, [rbp+4Fh+UnicodeString]; UnicodeString
0x14000a8c6  call    cs:__imp_RtlFreeUnicodeString
0x14000a8cd  nop     dword ptr [rax+rax+00h]
0x14000a8d2  cmp     [rbp+4Fh+DestinationString.Length], r13w
0x14000a8d7  jbe     short loc_14000A8E9
0x14000a8d9  lea     rcx, [rbp+4Fh+DestinationString]; UnicodeString
0x14000a8dd  call    cs:__imp_RtlFreeUnicodeString
0x14000a8e4  nop     dword ptr [rax+rax+00h]
0x14000a8e9  test    rdi, rdi
0x14000a8ec  jz      short loc_14000A8FD
0x14000a8ee  mov     rcx, rdi; FileHandle
0x14000a8f1  call    cs:__imp_FltClose
0x14000a8f8  nop     dword ptr [rax+rax+00h]
0x14000a8fd  mov     eax, ebx
0x14000a8ff  mov     rcx, [rbp+4Fh+var_40]
0x14000a903  xor     rcx, rsp; StackCookie
0x14000a906  call    __security_check_cookie
0x14000a90b  mov     rbx, [rsp+100h+arg_8]
0x14000a913  add     rsp, 0D0h
0x14000a91a  pop     r15
0x14000a91c  pop     r14
0x14000a91e  pop     r13
0x14000a920  pop     r12
0x14000a922  pop     rdi
0x14000a923  pop     rsi
0x14000a924  pop     rbp
0x14000a925  retn
```
