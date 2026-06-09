# CmsVolumeContainer::GetContainerReference(CmsTransactionContext *,unsigned __int64,SmsContainer * *,uchar,uchar,uchar)

- ea: `0x1c0024964`
- end: `0x1c0024b60`
- name: `?GetContainerReference@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@EEE@Z`
- size: `508`
- prototype: `int(CmsVolumeContainer *__hidden this, struct CmsTransactionContext *, unsigned __int64, struct SmsContainer **, unsigned __int8, unsigned __int8, unsigned __int8)`
- caller_count: `22`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1c0012080`
- `0x1c00247f0`
- `0x1c002c4cc`
- `0x1c0047b9c`
- `0x1c0047f38`
- `0x1c00c0b98`
- `0x1c00c16dc`
- `0x1c00d2db0`
- `0x1c00d34d0`
- `0x1c00d821c`
- `0x1c00d8c2c`
- `0x1c00d8c88`
- `0x1c00da6c4`
- `0x1c00dc880`
- `0x1c00dc970`
- `0x1c00dcb3c`
- `0x1c00dcbd8`
- `0x1c00dccc8`
- `0x1c00ea170`
- `0x1c00eb030`
- `0x1c00eb5b4`
- `0x1c00ec2f0`

## callees

- `0x1c0024964`
- `0x1c002c800`
- `0x1c00538e8`
- `0x1c00625fc`
- `0x1c0062754`

## import_xrefs

- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1c00249d2`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1c00249d2`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c0024a08`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c0024a08`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c0024abd`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c0024abd`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c0024b12`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c0024b12`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1c00249b8`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1c00249b8`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1c00249eb`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1c00249eb`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1c0024af0`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1c0024af0`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c0024a90`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c0024a90`

## pseudocode

```c
NTSTATUS __fastcall CmsVolumeContainer::GetContainerReference(
        CmsVolumeContainer *this,
        struct CmsTransactionContext *a2,
        ULONG_PTR a3,
        PRTL_DYNAMIC_HASH_TABLE_ENTRY *a4,
        unsigned __int8 a5,
        unsigned __int8 a6,
        unsigned __int8 a7)
{
  struct _IO_REMOVE_LOCK *v7; // r13
  char v12; // r12
  NTSTATUS result; // eax
  __int64 v14; // r15
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v15; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v16; // rbx
  int ContainerForCache; // ebx
  __int64 v18; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v19; // rbx
  int v20; // r15d
  unsigned int v21; // edx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  _QWORD v25[2]; // [rsp+30h] [rbp-38h] BYREF
  PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry; // [rsp+70h] [rbp+8h] BYREF

  Entry = 0;
  v7 = (struct _IO_REMOVE_LOCK *)((char *)this + 328);
  v25[0] = this;
  v12 = 0;
  result = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)((char *)this + 328), 0, File, 1u, 0x20u);
  if ( result >= 0 )
  {
    v14 = ExAcquireAutoExpandPushLockShared(*((_QWORD *)this + 7), 0);
    v15 = RtlLookupEntryHashTable(*((PRTL_DYNAMIC_HASH_TABLE *)this + 6), a3, 0);
    v16 = v15;
    if ( v15 )
      _InterlockedIncrement((volatile signed __int32 *)&v15[3].Signature);
    else
      v16 = 0;
    ExReleaseAutoExpandPushLockShared(v14, 0);
    if ( v16 )
    {
      *a4 = 0;
      if ( ((v16[23].Signature & 0x80000000000LL) != 0 || ((__int64)v16[1].Linkage.Flink & 2) != 0) && !a6 )
      {
        _InterlockedDecrement((volatile signed __int32 *)&v16[3].Signature);
        goto LABEL_15;
      }
      if ( !a7 )
        HIDWORD(v16[3].Signature) = 0;
      *a4 = v16;
      ContainerForCache = 0;
    }
    else
    {
      if ( a5 )
      {
LABEL_15:
        ContainerForCache = -1073741772;
LABEL_16:
        IoReleaseRemoveLockEx(v7, 0, 0x20u);
        return ContainerForCache;
      }
      ContainerForCache = CmsVolumeContainer::CreateContainerForCache(this, a2, a3, (struct SmsContainer **)&Entry);
      if ( ContainerForCache < 0 )
        goto LABEL_16;
      ExAcquireAutoExpandPushLockExclusive(*((_QWORD *)this + 7), 0);
      v18 = lambda_92acd8de50c64e0f63723dd5ec38c6f6_::operator()(v25, a3);
      v19 = Entry;
      v20 = v18;
      if ( v18 )
      {
        v12 = 1;
      }
      else
      {
        RtlInsertEntryHashTable(*((PRTL_DYNAMIC_HASH_TABLE *)this + 6), Entry, a3, 0);
        v20 = lambda_92acd8de50c64e0f63723dd5ec38c6f6_::operator()(v25, a3);
      }
      ExReleaseAutoExpandPushLockExclusive(*((_QWORD *)this + 7), 0);
      if ( v12 && v19 )
        SmsContainer::`scalar deleting destructor'(v19, v21);
      LOBYTE(v24) = a7 == 0;
      LOBYTE(v23) = a6 != 0;
      ContainerForCache = lambda_0c9c8de26fc204c063c6035cbd5d6fb0_::operator()(v22, v20, v23, v24, (__int64)a4);
      if ( ContainerForCache < 0 )
        goto LABEL_16;
    }
    ++*((_DWORD *)a2 + 706);
    return ContainerForCache;
  }
  return result;
}

```

## disassembly

```asm
0x1c0024964  mov     rax, rsp
0x1c0024967  mov     [rax+10h], rbx
0x1c002496b  mov     [rax+18h], rbp
0x1c002496f  mov     [rax+20h], rsi
0x1c0024973  push    rdi
0x1c0024974  push    r12
0x1c0024976  push    r13
0x1c0024978  push    r14
0x1c002497a  push    r15
0x1c002497c  sub     rsp, 40h
0x1c0024980  and     qword ptr [rax+8], 0
0x1c0024985  lea     r13, [rcx+148h]
0x1c002498c  mov     rsi, r9
0x1c002498f  mov     [rax-38h], rcx
0x1c0024993  mov     r14, r8
0x1c0024996  mov     dword ptr [rax-48h], 20h ; ' '
0x1c002499d  mov     rbp, rdx
0x1c00249a0  lea     r8, File; File
0x1c00249a7  mov     rdi, rcx
0x1c00249aa  mov     r9d, 1; Line
0x1c00249b0  mov     rcx, r13; RemoveLock
0x1c00249b3  xor     edx, edx; Tag
0x1c00249b5  xor     r12b, r12b
0x1c00249b8  call    cs:__imp_IoAcquireRemoveLockEx
0x1c00249bf  nop     dword ptr [rax+rax+00h]
0x1c00249c4  test    eax, eax
0x1c00249c6  js      loc_1C0024A55
0x1c00249cc  mov     rcx, [rdi+38h]
0x1c00249d0  xor     edx, edx
0x1c00249d2  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x1c00249d9  nop     dword ptr [rax+rax+00h]
0x1c00249de  mov     rcx, [rdi+30h]; HashTable
0x1c00249e2  xor     r8d, r8d; Context
0x1c00249e5  mov     rdx, r14; Signature
0x1c00249e8  mov     r15, rax
0x1c00249eb  call    cs:__imp_RtlLookupEntryHashTable
0x1c00249f2  nop     dword ptr [rax+rax+00h]
0x1c00249f7  mov     rbx, rax
0x1c00249fa  test    rax, rax
0x1c00249fd  jz      short loc_1C0024A74
0x1c00249ff  lock inc dword ptr [rax+58h]
0x1c0024a03  xor     edx, edx
0x1c0024a05  mov     rcx, r15
0x1c0024a08  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x1c0024a0f  nop     dword ptr [rax+rax+00h]
0x1c0024a14  xor     r15d, r15d
0x1c0024a17  test    rbx, rbx
0x1c0024a1a  jz      short loc_1C0024A78
0x1c0024a1c  mov     [rsi], r15
0x1c0024a1f  test    dword ptr [rbx+23Ch], 800h
0x1c0024a29  jnz     loc_1C0079E64
0x1c0024a2f  test    byte ptr [rbx+18h], 2
0x1c0024a33  jnz     loc_1C0079E64
0x1c0024a39  cmp     [rsp+68h+arg_30], r15b
0x1c0024a41  jnz     short loc_1C0024A47
0x1c0024a43  mov     [rbx+5Ch], r15d
0x1c0024a47  mov     [rsi], rbx
0x1c0024a4a  mov     ebx, r15d
0x1c0024a4d  inc     dword ptr [rbp+0B08h]
0x1c0024a53  mov     eax, ebx
0x1c0024a55  lea     r11, [rsp+68h+var_28]
0x1c0024a5a  mov     rbx, [r11+38h]
0x1c0024a5e  mov     rbp, [r11+40h]
0x1c0024a62  mov     rsi, [r11+48h]
0x1c0024a66  mov     rsp, r11
0x1c0024a69  pop     r15
0x1c0024a6b  pop     r14
0x1c0024a6d  pop     r13
0x1c0024a6f  pop     r12
0x1c0024a71  pop     rdi
0x1c0024a72  retn
0x1c0024a74  xor     ebx, ebx
0x1c0024a76  jmp     short loc_1C0024A03
0x1c0024a78  cmp     [rsp+68h+arg_20], r15b
0x1c0024a80  jz      short loc_1C0024A9E
0x1c0024a82  mov     ebx, 0C0000034h
0x1c0024a87  xor     edx, edx; Tag
0x1c0024a89  mov     rcx, r13; RemoveLock
0x1c0024a8c  lea     r8d, [rdx+20h]; RemlockSize
0x1c0024a90  call    cs:__imp_IoReleaseRemoveLockEx
0x1c0024a97  nop     dword ptr [rax+rax+00h]
0x1c0024a9c  jmp     short loc_1C0024A53
0x1c0024a9e  lea     r9, [rsp+68h+Entry]; struct SmsContainer **
0x1c0024aa3  mov     r8, r14; unsigned __int64
0x1c0024aa6  mov     rdx, rbp; struct CmsTransactionContext *
0x1c0024aa9  mov     rcx, rdi; this
0x1c0024aac  call    ?CreateContainerForCache@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@_KAEAPEAUSmsContainer@@@Z; CmsVolumeContainer::CreateContainerForCache(CmsTransactionContext *,unsigned __int64,SmsContainer * &)
0x1c0024ab1  mov     ebx, eax
0x1c0024ab3  test    eax, eax
0x1c0024ab5  js      short loc_1C0024A87
0x1c0024ab7  mov     rcx, [rdi+38h]
0x1c0024abb  xor     edx, edx
0x1c0024abd  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x1c0024ac4  nop     dword ptr [rax+rax+00h]
0x1c0024ac9  mov     rdx, r14
0x1c0024acc  lea     rcx, [rsp+68h+var_38]
0x1c0024ad1  call    _lambda_92acd8de50c64e0f63723dd5ec38c6f6___operator__
0x1c0024ad6  mov     rbx, [rsp+68h+Entry]
0x1c0024adb  mov     r15, rax
0x1c0024ade  test    rax, rax
0x1c0024ae1  jnz     short loc_1C0024B5B
0x1c0024ae3  mov     rcx, [rdi+30h]; HashTable
0x1c0024ae7  xor     r9d, r9d; Context
0x1c0024aea  mov     r8, r14; Signature
0x1c0024aed  mov     rdx, rbx; Entry
0x1c0024af0  call    cs:__imp_RtlInsertEntryHashTable
0x1c0024af7  nop     dword ptr [rax+rax+00h]
0x1c0024afc  mov     rdx, r14
0x1c0024aff  lea     rcx, [rsp+68h+var_38]
0x1c0024b04  call    _lambda_92acd8de50c64e0f63723dd5ec38c6f6___operator__
0x1c0024b09  mov     r15, rax
0x1c0024b0c  mov     rcx, [rdi+38h]
0x1c0024b10  xor     edx, edx
0x1c0024b12  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x1c0024b19  nop     dword ptr [rax+rax+00h]
0x1c0024b1e  test    r12b, r12b
0x1c0024b21  jnz     loc_1C0079E7B
0x1c0024b27  cmp     [rsp+68h+arg_30], 0
0x1c0024b2f  mov     rdx, r15
0x1c0024b32  mov     [rsp+68h+var_48], rsi
0x1c0024b37  setz    r9b
0x1c0024b3b  cmp     [rsp+68h+arg_28], 0
0x1c0024b43  setnz   r8b
0x1c0024b47  call    _lambda_0c9c8de26fc204c063c6035cbd5d6fb0___operator__
0x1c0024b4c  mov     ebx, eax
0x1c0024b4e  test    eax, eax
0x1c0024b50  jns     loc_1C0024A4D
0x1c0024b56  jmp     loc_1C0024A87
0x1c0024b5b  mov     r12b, 1
0x1c0024b5e  jmp     short loc_1C0024B0C
0x1c0079e64  cmp     [rsp+68h+arg_28], r15b
0x1c0079e6c  jnz     loc_1C0024A39
0x1c0079e72  lock dec dword ptr [rbx+58h]
0x1c0079e76  jmp     loc_1C0024A82
0x1c0079e7b  test    rbx, rbx
0x1c0079e7e  jz      loc_1C0024B27
0x1c0079e84  mov     rcx, rbx; P
0x1c0079e87  call    ??_GSmsContainer@@QEAAPEAXI@Z; SmsContainer::`scalar deleting destructor'(uint)
0x1c0079e8c  nop
0x1c0079e8d  jmp     loc_1C0024B27
```
