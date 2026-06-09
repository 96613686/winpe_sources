# SecNetUpdateIPAddressListWorkerRoutine

- ea: `0x140009f20`
- end: `0x14000a116`
- name: `SecNetUpdateIPAddressListWorkerRoutine`
- size: `502`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update`

## callees

- `0x140009b80`
- `0x140009bb8`
- `0x140009c14`
- `0x140009d0c`
- `0x140009f20`
- `0x140010158`
- `0x14001017c`
- `0x14001041f`
- `0x14001042b`
- `0x14001155f`
- `0x140011583`
- `0x140011650`
- `0x1400119c0`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x140009f88`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140009f88`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000a0e5`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000a0e5`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14000a03c`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14000a03c`

## pseudocode

```c
void __fastcall SecNetUpdateIPAddressListWorkerRoutine(PVOID IoObject, PVOID Context, PIO_WORKITEM IoWorkItem)
{
  char v4; // r14
  PMIB_UNICASTIPADDRESS_TABLE v5; // rdx
  __int64 i; // rbx
  char *v7; // rsi
  int v8; // [rsp+20h] [rbp-E0h] BYREF
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int8 NewElement[16]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE Buffer[256]; // [rsp+40h] [rbp-C0h] BYREF

  Table = 0;
  memset(Buffer, 0, 0xFEu);
  v8 = 127;
  NewElement[0] = 0;
  _InterlockedExchange(&SecNetIpAddressUpdateWorkerState, 2);
  v4 = 0;
  if ( ExAcquireRundownProtection(&SecNetIpAddressTableRundown) )
  {
    v4 = 1;
    if ( GetUnicastIpAddressTable_0(0, &Table) >= 0 )
    {
      FltAcquirePushLockExclusiveEx_0(&SecNetIpAddressTableLock, 0);
      SecNetIpTableAvlCleanup();
      v5 = Table;
      for ( i = 0; (unsigned int)i < Table->NumEntries; i = (unsigned int)(i + 1) )
      {
        v7 = (char *)v5 + 80 * i;
        if ( !(unsigned __int8)SecNetSkipAddress(v7 + 8) )
        {
          v8 = 127;
          memset(Buffer, 0, 0xFEu);
          NewElement[0] = 0;
          if ( (int)SecNetIpAddressToString(v7 + 8, Buffer, &v8) < 0 )
            break;
          if ( RtlInsertElementGenericTableAvl(&SecNetIpAddressTable, Buffer, 2 * v8, NewElement) && NewElement[0] )
            ++SecNetIpAddressTableElements;
        }
        v5 = Table;
      }
      FltReleasePushLockEx_0(&SecNetIpAddressTableLock, 0);
    }
  }
  if ( Table )
  {
    FreeMibTable_0(Table);
    Table = 0;
  }
  _m_prefetchw(&SecNetIpAddressUpdateWorkerState);
  if ( (_InterlockedAnd(&SecNetIpAddressUpdateWorkerState, 0xFFFFFFFD) & 1) != 0 )
  {
    IoQueueWorkItemEx_0(IoWorkItem, SecNetUpdateIPAddressListWorkerRoutine, DelayedWorkQueue, 0);
  }
  else
  {
    IoUninitializeWorkItem_0(IoWorkItem);
    SecFreePool(IoWorkItem, 0x744E6353u);
  }
  if ( v4 )
    ExReleaseRundownProtection(&SecNetIpAddressTableRundown);
}

```

## disassembly

```asm
0x140009f20  mov     [rsp-8+arg_0], rbx
0x140009f25  mov     [rsp-8+arg_8], rsi
0x140009f2a  push    rbp
0x140009f2b  push    rdi
0x140009f2c  push    r14
0x140009f2e  lea     rbp, [rsp-50h]
0x140009f33  sub     rsp, 150h
0x140009f3a  mov     rax, cs:__security_cookie
0x140009f41  xor     rax, rsp
0x140009f44  mov     [rbp+60h+var_20], rax
0x140009f48  mov     rdi, r8
0x140009f4b  mov     [rsp+160h+Table], 0
0x140009f54  mov     r8d, 0FEh; Size
0x140009f5a  lea     rcx, [rsp+160h+Buffer]; void *
0x140009f5f  xor     edx, edx; Val
0x140009f61  call    memset
0x140009f66  mov     eax, 2
0x140009f6b  mov     [rsp+160h+var_140], 7Fh
0x140009f73  mov     [rsp+160h+NewElement], 0
0x140009f78  lea     rcx, SecNetIpAddressTableRundown; RunRef
0x140009f7f  xchg    eax, cs:SecNetIpAddressUpdateWorkerState
0x140009f85  xor     r14b, r14b
0x140009f88  call    cs:__imp_ExAcquireRundownProtection
0x140009f8f  nop     dword ptr [rax+rax+00h]
0x140009f94  test    al, al
0x140009f96  jz      loc_14000A077
0x140009f9c  xor     ecx, ecx; Family
0x140009f9e  lea     rdx, [rsp+160h+Table]; Table
0x140009fa3  mov     r14b, 1
0x140009fa6  call    GetUnicastIpAddressTable_0
0x140009fab  test    eax, eax
0x140009fad  js      loc_14000A077
0x140009fb3  xor     edx, edx
0x140009fb5  lea     rcx, SecNetIpAddressTableLock
0x140009fbc  call    FltAcquirePushLockExclusiveEx_0
0x140009fc1  call    SecNetIpTableAvlCleanup
0x140009fc6  mov     rdx, [rsp+160h+Table]
0x140009fcb  xor     ebx, ebx
0x140009fcd  cmp     [rdx], ebx
0x140009fcf  jbe     loc_14000A069
0x140009fd5  lea     rsi, [rbx+rbx*4]
0x140009fd9  shl     rsi, 4
0x140009fdd  add     rsi, rdx
0x140009fe0  lea     rcx, [rsi+8]
0x140009fe4  call    SecNetSkipAddress
0x140009fe9  test    al, al
0x140009feb  jnz     short loc_14000A05A
0x140009fed  xor     edx, edx; Val
0x140009fef  mov     [rsp+160h+var_140], 7Fh
0x140009ff7  mov     r8d, 0FEh; Size
0x140009ffd  lea     rcx, [rsp+160h+Buffer]; void *
0x14000a002  call    memset
0x14000a007  lea     r8, [rsp+160h+var_140]
0x14000a00c  mov     [rsp+160h+NewElement], 0
0x14000a011  lea     rdx, [rsp+160h+Buffer]
0x14000a016  lea     rcx, [rsi+8]
0x14000a01a  call    SecNetIpAddressToString
0x14000a01f  test    eax, eax
0x14000a021  js      short loc_14000A069
0x14000a023  mov     r8d, [rsp+160h+var_140]
0x14000a028  lea     r9, [rsp+160h+NewElement]; NewElement
0x14000a02d  add     r8d, r8d; BufferSize
0x14000a030  lea     rdx, [rsp+160h+Buffer]; Buffer
0x14000a035  lea     rcx, SecNetIpAddressTable; Table
0x14000a03c  call    cs:__imp_RtlInsertElementGenericTableAvl
0x14000a043  nop     dword ptr [rax+rax+00h]
0x14000a048  test    rax, rax
0x14000a04b  jz      short loc_14000A05A
0x14000a04d  cmp     [rsp+160h+NewElement], 0
0x14000a052  jz      short loc_14000A05A
0x14000a054  inc     cs:SecNetIpAddressTableElements
0x14000a05a  mov     rdx, [rsp+160h+Table]
0x14000a05f  inc     ebx
0x14000a061  cmp     ebx, [rdx]
0x14000a063  jb      loc_140009FD5
0x14000a069  xor     edx, edx
0x14000a06b  lea     rcx, SecNetIpAddressTableLock
0x14000a072  call    FltReleasePushLockEx_0
0x14000a077  mov     rcx, [rsp+160h+Table]; Memory
0x14000a07c  test    rcx, rcx
0x14000a07f  jz      short loc_14000A08F
0x14000a081  call    FreeMibTable_0
0x14000a086  mov     [rsp+160h+Table], 0
0x14000a08f  prefetchw byte ptr cs:SecNetIpAddressUpdateWorkerState
0x14000a096  mov     eax, cs:SecNetIpAddressUpdateWorkerState
0x14000a09c  mov     edx, eax
0x14000a09e  and     edx, 0FFFFFFFDh
0x14000a0a1  lock cmpxchg cs:SecNetIpAddressUpdateWorkerState, edx
0x14000a0a9  jnz     short loc_14000A09C
0x14000a0ab  mov     rcx, rdi; IoWorkItem
0x14000a0ae  test    al, 1
0x14000a0b0  jz      short loc_14000A0C7
0x14000a0b2  xor     r9d, r9d; Context
0x14000a0b5  lea     rdx, SecNetUpdateIPAddressListWorkerRoutine; WorkerRoutine
0x14000a0bc  lea     r8d, [r9+1]; QueueType
0x14000a0c0  call    IoQueueWorkItemEx_0
0x14000a0c5  jmp     short loc_14000A0D9
0x14000a0c7  call    IoUninitializeWorkItem_0
0x14000a0cc  mov     edx, 744E6353h; Tag
0x14000a0d1  mov     rcx, rdi; P
0x14000a0d4  call    SecFreePool
0x14000a0d9  test    r14b, r14b
0x14000a0dc  jz      short loc_14000A0F1
0x14000a0de  lea     rcx, SecNetIpAddressTableRundown; RunRef
0x14000a0e5  call    cs:__imp_ExReleaseRundownProtection
0x14000a0ec  nop     dword ptr [rax+rax+00h]
0x14000a0f1  mov     rcx, [rbp+60h+var_20]
0x14000a0f5  xor     rcx, rsp; StackCookie
0x14000a0f8  call    __security_check_cookie
0x14000a0fd  lea     r11, [rsp+160h+var_10]
0x14000a105  mov     rbx, [r11+20h]
0x14000a109  mov     rsi, [r11+28h]
0x14000a10d  mov     rsp, r11
0x14000a110  pop     r14
0x14000a112  pop     rdi
0x14000a113  pop     rbp
0x14000a114  retn
```
