# BfsInitializeGlobalFileTable

- ea: `0x14000cb34`
- end: `0x14000ceac`
- name: `BfsInitializeGlobalFileTable`
- size: `888`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x140001008`
- `0x14000cb34`
- `0x14000ceb4`
- `0x140013860`
- `0x14001e008`

## import_xrefs

- `ntoskrnl!ExInitializePushLock` at `0x14000cc26`
- `ntoskrnl!ExInitializePushLock` at `0x14000cc36`
- `ntoskrnl!ExInitializePushLock` at `0x14000cc26`
- `ntoskrnl!ExInitializePushLock` at `0x14000cc36`
- `ntoskrnl!RtlCreateHashTable` at `0x14000ccb9`
- `ntoskrnl!RtlCreateHashTable` at `0x14000ccb9`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000cde1`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000cde1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000cbb6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000cbb6`
- `ntoskrnl!KeSetEvent` at `0x14000ce4d`
- `ntoskrnl!KeSetEvent` at `0x14000ce4d`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000cd86`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000cd86`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cb86`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cd26`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cb86`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cd26`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000ce71`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000ce71`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cdc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cdf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cdc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cdf2`
- `ntoskrnl!ExAllocatePool2` at `0x14000cc58`
- `ntoskrnl!ExAllocatePool2` at `0x14000ccf7`
- `ntoskrnl!ExAllocatePool2` at `0x14000cc58`
- `ntoskrnl!ExAllocatePool2` at `0x14000ccf7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cbe6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ce5e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cbe6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ce5e`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000cbf9`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000cbf9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cc0b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ce7d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cc0b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ce7d`

## pseudocode

```c
__int64 __fastcall BfsInitializeGlobalFileTable(__int64 a1, __int64 a2, __int64 a3)
{
  signed __int64 v4; // rax
  __int64 v5; // rax
  char v7; // r13
  __int64 Pool2; // rax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  PRTL_DYNAMIC_HASH_TABLE *v12; // rsi
  int UserPolicyEntriesToGlobalFileTable; // edi
  void *RootDirectory; // rsi
  __int64 FileInformation; // r15
  NTSTATUS i; // eax
  unsigned __int64 v17; // rax
  __int64 v18; // rdx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int Timeout; // [rsp+20h] [rbp-A9h]
  int Timeouta; // [rsp+20h] [rbp-A9h]
  BOOLEAN v24; // [rsp+60h] [rbp-69h]
  PFLT_FILTER v25; // [rsp+68h] [rbp-61h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-59h] BYREF
  struct _UNICODE_STRING v27; // [rsp+80h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+A0h] [rbp-29h] BYREF
  PFLT_FILTER *v30; // [rsp+C0h] [rbp-9h]
  __int64 v31; // [rsp+C8h] [rbp-1h]

  v25 = gBfsFilterHandle;
  IoStatusBlock = 0;
  DestinationString = 0;
  v27 = 0;
  RtlInitUnicodeString(&DestinationString, L"S-1-*");
  v4 = _InterlockedCompareExchange64((volatile signed __int64 *)(a3 + 64), -1, 0);
  if ( v4 == -1 )
  {
    KeWaitForSingleObject((PVOID)(a3 + 16), Executive, 0, 0, 0);
    v5 = *(_QWORD *)(a3 + 64);
    if ( !v5 || v5 == -1 )
      return 3221225473LL;
    return 0;
  }
  if ( v4 )
    return 0;
  KeEnterCriticalRegion();
  v24 = ExAcquireRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
  if ( v24 )
  {
    v7 = 0;
    ExInitializePushLock((PULONG_PTR)a3);
    ExInitializePushLock((PULONG_PTR)(a3 + 8));
    Pool2 = ExAllocatePool2(256, 40, 1416848962);
    v12 = (PRTL_DYNAMIC_HASH_TABLE *)(a3 + 40);
    *(_QWORD *)(a3 + 40) = Pool2;
    if ( Pool2 )
    {
      if ( RtlCreateHashTable((PRTL_DYNAMIC_HASH_TABLE *)(a3 + 40), 0, 0) )
      {
        v7 = 1;
        *(_QWORD *)(a3 + 56) = a3 + 48;
        *(_QWORD *)(a3 + 48) = a3 + 48;
        RootDirectory = (void *)BfsGetRootDirectory();
        FileInformation = ExAllocatePool2(256, 390, 1316185666);
        for ( i = ZwQueryDirectoryFile(
                    RootDirectory,
                    0,
                    0,
                    0,
                    &IoStatusBlock,
                    (PVOID)FileInformation,
                    0x186u,
                    FileNamesInformation,
                    0,
                    &DestinationString,
                    1u);
              ;
              i = ZwQueryDirectoryFile(
                    RootDirectory,
                    0,
                    0,
                    0,
                    &IoStatusBlock,
                    (PVOID)FileInformation,
                    0x186u,
                    FileNamesInformation,
                    0,
                    &DestinationString,
                    0) )
        {
          UserPolicyEntriesToGlobalFileTable = i;
          if ( i < 0 )
          {
            if ( i == -2147483642 || i == -1073741809 )
              UserPolicyEntriesToGlobalFileTable = 0;
            _InterlockedExchange64((volatile __int64 *)(a3 + 64), 1);
            goto LABEL_23;
          }
          v17 = *(unsigned int *)(FileInformation + 8);
          if ( (_DWORD)v17 )
          {
            *(_WORD *)(FileInformation + 2 * (v17 >> 1) + 12) = 0;
            RtlInitUnicodeString(&v27, (PCWSTR)(FileInformation + 12));
            UserPolicyEntriesToGlobalFileTable = BfsLoadUserPolicyEntriesToGlobalFileTable(
                                                   (int)v25,
                                                   v18,
                                                   a3,
                                                   (__int64)&v27);
            if ( UserPolicyEntriesToGlobalFileTable < 0 )
              break;
          }
        }
        if ( (unsigned int)dword_140019000 > 3 )
        {
          LODWORD(v25) = UserPolicyEntriesToGlobalFileTable;
          v30 = &v25;
          v31 = 4;
          tlgWriteTransfer_EtwWriteTransfer(v19, (int)&byte_140016D91, v20, v21, Timeouta, &v29);
        }
LABEL_23:
        v12 = (PRTL_DYNAMIC_HASH_TABLE *)(a3 + 40);
        if ( FileInformation )
          ExFreePoolWithTag((PVOID)FileInformation, 0);
        if ( UserPolicyEntriesToGlobalFileTable >= 0 )
          goto LABEL_34;
        goto LABEL_26;
      }
      UserPolicyEntriesToGlobalFileTable = -1073741823;
    }
    else
    {
      UserPolicyEntriesToGlobalFileTable = -1073741801;
    }
    if ( (unsigned int)dword_140019000 > 3 )
    {
      LODWORD(v25) = UserPolicyEntriesToGlobalFileTable;
      v30 = &v25;
      v31 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v9, (int)&byte_140016D91, v10, v11, Timeout, &v29);
    }
LABEL_26:
    if ( *v12 )
    {
      if ( v7 )
        RtlDeleteHashTable(*v12);
      ExFreePoolWithTag(*v12, 0);
      *v12 = 0;
    }
    _InterlockedExchange64((volatile __int64 *)(a3 + 64), 0);
    goto LABEL_34;
  }
  UserPolicyEntriesToGlobalFileTable = 0;
LABEL_34:
  KeSetEvent((PRKEVENT)(a3 + 16), 0, 0);
  if ( v24 )
  {
    KeEnterCriticalRegion();
    ExReleaseRundownProtection(&gBfsRundownProtection);
    KeLeaveCriticalRegion();
  }
  return (unsigned int)UserPolicyEntriesToGlobalFileTable;
}

```

## disassembly

```asm
0x14000cb34  push    rbp
0x14000cb36  push    rbx
0x14000cb37  push    rsi
0x14000cb38  push    rdi
0x14000cb39  push    r12
0x14000cb3b  push    r13
0x14000cb3d  push    r14
0x14000cb3f  push    r15
0x14000cb41  lea     rbp, [rsp-1Fh]
0x14000cb46  sub     rsp, 0E8h
0x14000cb4d  mov     rax, cs:__security_cookie
0x14000cb54  xor     rax, rsp
0x14000cb57  mov     [rbp+57h+var_50], rax
0x14000cb5b  mov     rax, cs:gBfsFilterHandle
0x14000cb62  lea     rdx, aS1; "S-1-*"
0x14000cb69  xorps   xmm0, xmm0
0x14000cb6c  mov     [rbp+57h+var_B8], rax
0x14000cb70  xorps   xmm1, xmm1
0x14000cb73  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000cb77  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14000cb7b  mov     r14, r8
0x14000cb7e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14000cb82  movups  xmmword ptr [rbp+57h+var_A0.Length], xmm0
0x14000cb86  call    cs:__imp_RtlInitUnicodeString
0x14000cb8d  nop     dword ptr [rax+rax+00h]
0x14000cb92  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000cb96  xor     eax, eax
0x14000cb98  lock cmpxchg [r14+40h], rdi
0x14000cb9e  xor     ebx, ebx
0x14000cba0  cmp     rax, rdi
0x14000cba3  jnz     short loc_14000CBDA
0x14000cba5  lea     rcx, [r14+10h]; Object
0x14000cba9  mov     [rsp+120h+Timeout], rbx; Timeout
0x14000cbae  xor     r9d, r9d; Alertable
0x14000cbb1  xor     r8d, r8d; WaitMode
0x14000cbb4  xor     edx, edx; WaitReason
0x14000cbb6  call    cs:__imp_KeWaitForSingleObject
0x14000cbbd  nop     dword ptr [rax+rax+00h]
0x14000cbc2  mov     rax, [r14+40h]
0x14000cbc6  test    rax, rax
0x14000cbc9  jz      short loc_14000CBD0
0x14000cbcb  cmp     rax, rdi
0x14000cbce  jnz     short loc_14000CBDF
0x14000cbd0  mov     eax, 0C0000001h
0x14000cbd5  jmp     loc_14000CE8B
0x14000cbda  test    rax, rax
0x14000cbdd  jz      short loc_14000CBE6
0x14000cbdf  xor     eax, eax
0x14000cbe1  jmp     loc_14000CE8B
0x14000cbe6  call    cs:__imp_KeEnterCriticalRegion
0x14000cbed  nop     dword ptr [rax+rax+00h]
0x14000cbf2  lea     rcx, gBfsRundownProtection; RunRef
0x14000cbf9  call    cs:__imp_ExAcquireRundownProtection
0x14000cc00  nop     dword ptr [rax+rax+00h]
0x14000cc05  mov     dil, al
0x14000cc08  mov     [rbp+57h+var_C0], al
0x14000cc0b  call    cs:__imp_KeLeaveCriticalRegion
0x14000cc12  nop     dword ptr [rax+rax+00h]
0x14000cc17  test    dil, dil
0x14000cc1a  jz      loc_14000CE42
0x14000cc20  mov     rcx, r14; PushLock
0x14000cc23  mov     r13b, bl
0x14000cc26  call    cs:__imp_ExInitializePushLock
0x14000cc2d  nop     dword ptr [rax+rax+00h]
0x14000cc32  lea     rcx, [r14+8]; PushLock
0x14000cc36  call    cs:__imp_ExInitializePushLock
0x14000cc3d  nop     dword ptr [rax+rax+00h]
0x14000cc42  mov     r12d, 28h ; '('
0x14000cc48  mov     edi, 100h
0x14000cc4d  mov     edx, r12d
0x14000cc50  mov     ecx, edi
0x14000cc52  mov     r8d, 54736642h
0x14000cc58  call    cs:__imp_ExAllocatePool2
0x14000cc5f  nop     dword ptr [rax+rax+00h]
0x14000cc64  lea     rsi, [r14+28h]
0x14000cc68  mov     [rsi], rax
0x14000cc6b  test    rax, rax
0x14000cc6e  jnz     short loc_14000CCB1
0x14000cc70  mov     edi, 0C0000017h
0x14000cc75  mov     eax, cs:dword_140019000
0x14000cc7b  cmp     eax, 3
0x14000cc7e  jbe     loc_14000CDD4
0x14000cc84  lea     rax, [rbp+57h+var_B8]
0x14000cc88  mov     dword ptr [rbp+57h+var_B8], edi
0x14000cc8b  mov     [rbp+57h+var_60], rax
0x14000cc8f  lea     rdx, byte_140016D91; int
0x14000cc96  lea     rax, [rbp+57h+var_80]
0x14000cc9a  mov     [rbp+57h+var_58], 4
0x14000cca2  mov     [rsp+120h+FileInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000cca7  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ccac  jmp     loc_14000CDD4
0x14000ccb1  xor     r8d, r8d; Flags
0x14000ccb4  xor     edx, edx; Shift
0x14000ccb6  mov     rcx, rsi; HashTable
0x14000ccb9  call    cs:__imp_RtlCreateHashTable
0x14000ccc0  nop     dword ptr [rax+rax+00h]
0x14000ccc5  test    al, al
0x14000ccc7  jnz     short loc_14000CCD0
0x14000ccc9  mov     edi, 0C0000001h
0x14000ccce  jmp     short loc_14000CC75
0x14000ccd0  lea     rax, [r14+30h]
0x14000ccd4  mov     r13d, 1
0x14000ccda  mov     [rax+8], rax
0x14000ccde  mov     [rax], rax
0x14000cce1  call    BfsGetRootDirectory
0x14000cce6  mov     edx, 186h
0x14000cceb  mov     r8d, 4E736642h
0x14000ccf1  mov     rcx, rdi
0x14000ccf4  mov     rsi, rax
0x14000ccf7  call    cs:__imp_ExAllocatePool2
0x14000ccfe  nop     dword ptr [rax+rax+00h]
0x14000cd03  mov     r15, rax
0x14000cd06  mov     [rsp+120h+RestartScan], r13b
0x14000cd0b  jmp     short loc_14000CD50
0x14000cd0d  mov     eax, [r15+8]
0x14000cd11  test    eax, eax
0x14000cd13  jz      short loc_14000CD4C
0x14000cd15  shr     rax, 1
0x14000cd18  lea     rdx, [r15+0Ch]; SourceString
0x14000cd1c  lea     rcx, [rbp+57h+var_A0]; DestinationString
0x14000cd20  mov     [r15+rax*2+0Ch], bx
0x14000cd26  call    cs:__imp_RtlInitUnicodeString
0x14000cd2d  nop     dword ptr [rax+rax+00h]
0x14000cd32  mov     rcx, [rbp+57h+var_B8]
0x14000cd36  lea     r9, [rbp+57h+var_A0]
0x14000cd3a  mov     r8, r14
0x14000cd3d  call    BfsLoadUserPolicyEntriesToGlobalFileTable
0x14000cd42  mov     edi, eax
0x14000cd44  test    eax, eax
0x14000cd46  js      loc_14000CE0A
0x14000cd4c  mov     [rsp+120h+RestartScan], bl; RestartScan
0x14000cd50  lea     rax, [rbp+57h+DestinationString]
0x14000cd54  xor     r9d, r9d; ApcContext
0x14000cd57  mov     [rsp+120h+FileName], rax; FileName
0x14000cd5c  xor     r8d, r8d; ApcRoutine
0x14000cd5f  mov     [rsp+120h+ReturnSingleEntry], bl; ReturnSingleEntry
0x14000cd63  lea     rax, [rbp+57h+IoStatusBlock]
0x14000cd67  mov     [rsp+120h+FileInformationClass], 0Ch; FileInformationClass
0x14000cd6f  xor     edx, edx; Event
0x14000cd71  mov     [rsp+120h+Length], 186h; Length
0x14000cd79  mov     rcx, rsi; FileHandle
0x14000cd7c  mov     [rsp+120h+FileInformation], r15; FileInformation
0x14000cd81  mov     [rsp+120h+Timeout], rax; int
0x14000cd86  call    cs:__imp_ZwQueryDirectoryFile
0x14000cd8d  nop     dword ptr [rax+rax+00h]
0x14000cd92  mov     edi, eax
0x14000cd94  test    eax, eax
0x14000cd96  jns     loc_14000CD0D
0x14000cd9c  cmp     eax, 80000006h
0x14000cda1  jz      short loc_14000CDAA
0x14000cda3  cmp     eax, 0C000000Fh
0x14000cda8  jnz     short loc_14000CDAC
0x14000cdaa  mov     edi, ebx
0x14000cdac  mov     rax, r13
0x14000cdaf  xchg    rax, [r14+40h]
0x14000cdb3  mov     rax, r14
0x14000cdb6  lea     rsi, [r12+rax]
0x14000cdba  test    r15, r15
0x14000cdbd  jz      short loc_14000CDD0
0x14000cdbf  xor     edx, edx; Tag
0x14000cdc1  mov     rcx, r15; P
0x14000cdc4  call    cs:__imp_ExFreePoolWithTag
0x14000cdcb  nop     dword ptr [rax+rax+00h]
0x14000cdd0  test    edi, edi
0x14000cdd2  jns     short loc_14000CE44
0x14000cdd4  mov     rcx, [rsi]; HashTable
0x14000cdd7  test    rcx, rcx
0x14000cdda  jz      short loc_14000CE01
0x14000cddc  test    r13b, r13b
0x14000cddf  jz      short loc_14000CDED
0x14000cde1  call    cs:__imp_RtlDeleteHashTable
0x14000cde8  nop     dword ptr [rax+rax+00h]
0x14000cded  mov     rcx, [rsi]; P
0x14000cdf0  xor     edx, edx; Tag
0x14000cdf2  call    cs:__imp_ExFreePoolWithTag
0x14000cdf9  nop     dword ptr [rax+rax+00h]
0x14000cdfe  mov     [rsi], rbx
0x14000ce01  mov     rax, rbx
0x14000ce04  xchg    rax, [r14+40h]
0x14000ce08  jmp     short loc_14000CE44
0x14000ce0a  mov     eax, cs:dword_140019000
0x14000ce10  cmp     eax, 3
0x14000ce13  jbe     short loc_14000CDB3
0x14000ce15  lea     rax, [rbp+57h+var_B8]
0x14000ce19  mov     dword ptr [rbp+57h+var_B8], edi
0x14000ce1c  mov     [rbp+57h+var_60], rax
0x14000ce20  lea     rdx, byte_140016D91; int
0x14000ce27  lea     rax, [rbp+57h+var_80]
0x14000ce2b  mov     [rbp+57h+var_58], 4
0x14000ce33  mov     [rsp+120h+FileInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000ce38  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ce3d  jmp     loc_14000CDB3
0x14000ce42  mov     edi, ebx
0x14000ce44  lea     rcx, [r14+10h]; Event
0x14000ce48  xor     r8d, r8d; Wait
0x14000ce4b  xor     edx, edx; Increment
0x14000ce4d  call    cs:__imp_KeSetEvent
0x14000ce54  nop     dword ptr [rax+rax+00h]
0x14000ce59  cmp     [rbp+57h+var_C0], bl
0x14000ce5c  jz      short loc_14000CE89
0x14000ce5e  call    cs:__imp_KeEnterCriticalRegion
0x14000ce65  nop     dword ptr [rax+rax+00h]
0x14000ce6a  lea     rcx, gBfsRundownProtection; RunRef
0x14000ce71  call    cs:__imp_ExReleaseRundownProtection
0x14000ce78  nop     dword ptr [rax+rax+00h]
0x14000ce7d  call    cs:__imp_KeLeaveCriticalRegion
0x14000ce84  nop     dword ptr [rax+rax+00h]
0x14000ce89  mov     eax, edi
0x14000ce8b  mov     rcx, [rbp+57h+var_50]
0x14000ce8f  xor     rcx, rsp; StackCookie
0x14000ce92  call    __security_check_cookie
0x14000ce97  add     rsp, 0E8h
0x14000ce9e  pop     r15
0x14000cea0  pop     r14
0x14000cea2  pop     r13
0x14000cea4  pop     r12
0x14000cea6  pop     rdi
0x14000cea7  pop     rsi
0x14000cea8  pop     rbx
0x14000cea9  pop     rbp
0x14000ceaa  retn
```
