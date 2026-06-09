# CmsVolumeContainer::GetContainerReference(CmsTransactionContext *,unsigned __int64,SmsContainer * *,uchar,uchar)

- ea: `0x140045b30`
- end: `0x140045e41`
- name: `?GetContainerReference@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@EE@Z`
- size: `785`
- prototype: `int(CmsVolumeContainer *__hidden this, struct CmsTransactionContext *, unsigned __int64, struct SmsContainer **, unsigned __int8, unsigned __int8)`
- caller_count: `37`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140031d40`
- `0x140045910`
- `0x140045e50`
- `0x140046050`
- `0x140046af0`
- `0x140047bf0`
- `0x140059a54`
- `0x140059ef0`
- `0x14005a1e0`
- `0x1400c0cb4`
- `0x1400c7740`
- `0x1401193e8`
- `0x140120668`
- `0x14012b2fc`
- `0x140134548`
- `0x140134e54`
- `0x140135058`
- `0x140135a0c`
- `0x140135be8`
- `0x140136d9c`
- `0x140138e8c`
- `0x140138f64`
- `0x14013910c`
- `0x14013918c`
- `0x140139288`
- `0x140148e44`
- `0x14014a7e4`
- `0x14015b2ec`
- `0x14015c33c`
- `0x14015ced0`
- `0x14015ddc4`
- `0x140163738`
- `0x1401638d0`
- `0x140164238`
- `0x140164444`
- `0x140165044`
- `0x140165b50`

## callees

- `0x140045b30`
- `0x140062510`
- `0x1400a2494`

## import_xrefs

- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x140045bb2`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x140045bb2`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140045bed`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140045c61`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140045bed`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140045c61`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x140045cad`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x140045cad`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140045ce9`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140045dc7`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140045ce9`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140045dc7`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140045b8b`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140045b8b`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140045bcb`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140045cc3`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140045da3`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140045bcb`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140045cc3`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140045da3`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140045d8d`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140045d8d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140045e0c`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140045e0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045d24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045e30`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045d24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045e30`

## pseudocode

```c
NTSTATUS __fastcall CmsVolumeContainer::GetContainerReference(
        PRTL_DYNAMIC_HASH_TABLE *this,
        struct CmsTransactionContext *a2,
        ULONG_PTR a3,
        PRTL_DYNAMIC_HASH_TABLE_ENTRY *a4,
        unsigned __int8 a5,
        unsigned __int8 a6)
{
  bool v10; // r15
  struct _IO_REMOVE_LOCK *v11; // r13
  NTSTATUS result; // eax
  __int64 v13; // rbx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v14; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v15; // rsi
  int ContainerForCache; // ebx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v17; // rax
  _QWORD *v18; // rbx
  _QWORD *v19; // rcx
  void *v20; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v21; // rax
  PVOID P; // [rsp+60h] [rbp+8h] BYREF

  P = 0;
  v10 = !a2 || !_bittest64((const signed __int64 *)a2, 0x22u);
  v11 = (struct _IO_REMOVE_LOCK *)(this + 61);
  result = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(this + 61), 0, &File, 1u, 0x20u);
  if ( result >= 0 )
  {
    v13 = ExAcquireAutoExpandPushLockShared(this + 7, 2);
    v14 = RtlLookupEntryHashTable(this[6], a3, 0);
    v15 = v14;
    if ( v14 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&v14[3].Signature + 1);
      ExReleaseAutoExpandPushLockShared(v13, 2);
      *a4 = 0;
      if ( ((HIDWORD(v15[25].Linkage.Blink) & 0x800) != 0 || ((__int64)v15[1].Linkage.Flink & 4) != 0) && !a6 )
      {
LABEL_31:
        ContainerForCache = -1073741772;
        _InterlockedDecrement((volatile signed __int32 *)&v15[3].Signature + 1);
LABEL_10:
        if ( ContainerForCache >= 0 )
        {
          if ( a2 )
            ++*((_DWORD *)a2 + 88);
          return ContainerForCache;
        }
        goto LABEL_39;
      }
      if ( !v10 )
      {
LABEL_9:
        ContainerForCache = 0;
        *a4 = v15;
        goto LABEL_10;
      }
    }
    else
    {
      ExReleaseAutoExpandPushLockShared(v13, 2);
      if ( a5 )
      {
        ContainerForCache = -1073741772;
        goto LABEL_39;
      }
      if ( !a2 )
      {
        ContainerForCache = -1073741802;
        goto LABEL_39;
      }
      ContainerForCache = CmsVolumeContainer::CreateContainerForCache(
                            (CmsVolumeContainer *)this,
                            a2,
                            a3,
                            (struct SmsContainer **)&P);
      if ( ContainerForCache < 0 )
      {
LABEL_39:
        IoReleaseRemoveLockEx(v11, 0, 0x20u);
        return ContainerForCache;
      }
      ExAcquireAutoExpandPushLockExclusive(this + 7, 2);
      v17 = RtlLookupEntryHashTable(this[6], a3, 0);
      v15 = v17;
      if ( v17 )
      {
        _InterlockedIncrement((volatile signed __int32 *)&v17[3].Signature + 1);
        ExReleaseAutoExpandPushLockExclusive(this + 7, 2);
        v18 = P;
        if ( P )
        {
          v19 = (_QWORD *)*((_QWORD *)P + 21);
          if ( v19 )
            CmsLookasides::Free(v19);
          v20 = (void *)v18[71];
          if ( v20 )
            ExFreePoolWithTag(v20, 0);
          ExFreePoolWithTag(v18, 0);
        }
      }
      else
      {
        RtlInsertEntryHashTable(this[6], (PRTL_DYNAMIC_HASH_TABLE_ENTRY)P, a3, 0);
        v21 = RtlLookupEntryHashTable(this[6], a3, 0);
        v15 = v21;
        if ( v21 )
          _InterlockedIncrement((volatile signed __int32 *)&v21[3].Signature + 1);
        else
          v15 = 0;
        ExReleaseAutoExpandPushLockExclusive(this + 7, 2);
      }
      *a4 = 0;
      if ( ((HIDWORD(v15[25].Linkage.Blink) & 0x800) != 0 || ((__int64)v15[1].Linkage.Flink & 4) != 0) && !a6 )
        goto LABEL_31;
      if ( !v10 )
        goto LABEL_9;
    }
    LODWORD(v15[4].Linkage.Flink) = 0;
    goto LABEL_9;
  }
  return result;
}

```

## disassembly

```asm
0x140045b30  mov     [rsp+arg_18], rbp
0x140045b35  push    rdi
0x140045b36  push    r12
0x140045b38  push    r13
0x140045b3a  push    r14
0x140045b3c  push    r15
0x140045b3e  sub     rsp, 30h
0x140045b42  mov     [rsp+58h+P], 0
0x140045b4b  mov     r14, r9
0x140045b4e  mov     r12, r8
0x140045b51  mov     rdi, rdx
0x140045b54  mov     rbp, rcx
0x140045b57  test    rdx, rdx
0x140045b5a  jz      short loc_140045B67
0x140045b5c  bt      qword ptr [rdx], 22h ; '"'
0x140045b61  jb      loc_140045C59
0x140045b67  mov     r15b, 1
0x140045b6a  lea     r13, [rcx+1E8h]
0x140045b71  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x140045b79  mov     rcx, r13; RemoveLock
0x140045b7c  lea     r8, File; File
0x140045b83  mov     r9d, 1; Line
0x140045b89  xor     edx, edx; Tag
0x140045b8b  call    cs:__imp_IoAcquireRemoveLockEx
0x140045b92  nop     dword ptr [rax+rax+00h]
0x140045b97  test    eax, eax
0x140045b99  js      loc_140045C45
0x140045b9f  mov     [rsp+58h+arg_8], rbx
0x140045ba4  lea     rcx, [rbp+38h]
0x140045ba8  mov     edx, 2
0x140045bad  mov     [rsp+58h+arg_10], rsi
0x140045bb2  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x140045bb9  nop     dword ptr [rax+rax+00h]
0x140045bbe  mov     rcx, [rbp+30h]; HashTable
0x140045bc2  xor     r8d, r8d; Context
0x140045bc5  mov     rdx, r12; Signature
0x140045bc8  mov     rbx, rax
0x140045bcb  call    cs:__imp_RtlLookupEntryHashTable
0x140045bd2  nop     dword ptr [rax+rax+00h]
0x140045bd7  mov     edx, 2
0x140045bdc  mov     rcx, rbx
0x140045bdf  mov     rsi, rax
0x140045be2  test    rax, rax
0x140045be5  jz      short loc_140045C61
0x140045be7  nop
0x140045be8  lock inc dword ptr [rax+5Ch]
0x140045bec  nop
0x140045bed  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x140045bf4  nop     dword ptr [rax+rax+00h]
0x140045bf9  xor     ebp, ebp
0x140045bfb  mov     [r14], rbp
0x140045bfe  test    dword ptr [rsi+264h], 800h
0x140045c08  jnz     loc_140045D60
0x140045c0e  test    byte ptr [rsi+18h], 4
0x140045c12  jnz     loc_140045D60
0x140045c18  test    r15b, r15b
0x140045c1b  jnz     loc_140045D58
0x140045c21  mov     ebx, ebp
0x140045c23  mov     [r14], rsi
0x140045c26  test    ebx, ebx
0x140045c28  js      loc_140045E01
0x140045c2e  test    rdi, rdi
0x140045c31  jz      short loc_140045C39
0x140045c33  inc     dword ptr [rdi+160h]
0x140045c39  mov     rsi, [rsp+58h+arg_10]
0x140045c3e  mov     eax, ebx
0x140045c40  mov     rbx, [rsp+58h+arg_8]
0x140045c45  mov     rbp, [rsp+58h+arg_18]
0x140045c4a  add     rsp, 30h
0x140045c4e  pop     r15
0x140045c50  pop     r14
0x140045c52  pop     r13
0x140045c54  pop     r12
0x140045c56  pop     rdi
0x140045c57  retn
0x140045c59  xor     r15b, r15b
0x140045c5c  jmp     loc_140045B6A
0x140045c61  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x140045c68  nop     dword ptr [rax+rax+00h]
0x140045c6d  cmp     [rsp+58h+arg_20], 0
0x140045c75  jnz     loc_140045DFC
0x140045c7b  test    rdi, rdi
0x140045c7e  jz      loc_140045E1D
0x140045c84  lea     r9, [rsp+58h+P]; struct SmsContainer **
0x140045c89  mov     r8, r12; unsigned __int64
0x140045c8c  mov     rdx, rdi; struct CmsTransactionContext *
0x140045c8f  mov     rcx, rbp; this
0x140045c92  call    ?CreateContainerForCache@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@_KAEAPEAUSmsContainer@@@Z; CmsVolumeContainer::CreateContainerForCache(CmsTransactionContext *,unsigned __int64,SmsContainer * &)
0x140045c97  mov     ebx, eax
0x140045c99  test    eax, eax
0x140045c9b  js      loc_140045E01
0x140045ca1  lea     rbx, [rbp+38h]
0x140045ca5  mov     edx, 2
0x140045caa  mov     rcx, rbx
0x140045cad  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x140045cb4  nop     dword ptr [rax+rax+00h]
0x140045cb9  mov     rcx, [rbp+30h]; HashTable
0x140045cbd  xor     r8d, r8d; Context
0x140045cc0  mov     rdx, r12; Signature
0x140045cc3  call    cs:__imp_RtlLookupEntryHashTable
0x140045cca  nop     dword ptr [rax+rax+00h]
0x140045ccf  mov     rsi, rax
0x140045cd2  test    rax, rax
0x140045cd5  jz      loc_140045D7E
0x140045cdb  nop
0x140045cdc  lock inc dword ptr [rax+5Ch]
0x140045ce0  mov     edx, 2
0x140045ce5  mov     rcx, rbx
0x140045ce8  nop
0x140045ce9  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x140045cf0  nop     dword ptr [rax+rax+00h]
0x140045cf5  mov     rbx, [rsp+58h+P]
0x140045cfa  test    rbx, rbx
0x140045cfd  jz      short loc_140045D30
0x140045cff  mov     rcx, [rbx+0A8h]; void *
0x140045d06  test    rcx, rcx
0x140045d09  jnz     loc_140045E24
0x140045d0f  mov     rcx, [rbx+238h]; P
0x140045d16  test    rcx, rcx
0x140045d19  jnz     loc_140045E2E
0x140045d1f  xor     edx, edx; Tag
0x140045d21  mov     rcx, rbx; P
0x140045d24  call    cs:__imp_ExFreePoolWithTag
0x140045d2b  nop     dword ptr [rax+rax+00h]
0x140045d30  xor     ebp, ebp
0x140045d32  mov     [r14], rbp
0x140045d35  test    dword ptr [rsi+264h], 800h
0x140045d3f  jnz     loc_140045DDE
0x140045d45  test    byte ptr [rsi+18h], 4
0x140045d49  jnz     loc_140045DDE
0x140045d4f  test    r15b, r15b
0x140045d52  jz      loc_140045C21
0x140045d58  mov     [rsi+60h], ebp
0x140045d5b  jmp     loc_140045C21
0x140045d60  cmp     [rsp+58h+arg_28], bpl
0x140045d68  jnz     loc_140045C18
0x140045d6e  nop
0x140045d6f  mov     ebx, 0C0000034h
0x140045d74  lock dec dword ptr [rsi+5Ch]
0x140045d78  nop
0x140045d79  jmp     loc_140045C26
0x140045d7e  mov     rdx, [rsp+58h+P]; Entry
0x140045d83  xor     r9d, r9d; Context
0x140045d86  mov     rcx, [rbp+30h]; HashTable
0x140045d8a  mov     r8, r12; Signature
0x140045d8d  call    cs:__imp_RtlInsertEntryHashTable
0x140045d94  nop     dword ptr [rax+rax+00h]
0x140045d99  mov     rcx, [rbp+30h]; HashTable
0x140045d9d  xor     r8d, r8d; Context
0x140045da0  mov     rdx, r12; Signature
0x140045da3  call    cs:__imp_RtlLookupEntryHashTable
0x140045daa  nop     dword ptr [rax+rax+00h]
0x140045daf  mov     rsi, rax
0x140045db2  test    rax, rax
0x140045db5  jz      short loc_140045DD8
0x140045db7  nop
0x140045db8  lock inc dword ptr [rax+5Ch]
0x140045dbc  nop
0x140045dbd  xor     ebp, ebp
0x140045dbf  mov     edx, 2
0x140045dc4  mov     rcx, rbx
0x140045dc7  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x140045dce  nop     dword ptr [rax+rax+00h]
0x140045dd3  jmp     loc_140045D32
0x140045dd8  xor     ebp, ebp
0x140045dda  mov     esi, ebp
0x140045ddc  jmp     short loc_140045DBF
0x140045dde  cmp     [rsp+58h+arg_28], 0
0x140045de6  jnz     loc_140045D4F
0x140045dec  nop
0x140045ded  mov     ebx, 0C0000034h
0x140045df2  lock dec dword ptr [rsi+5Ch]
0x140045df6  nop
0x140045df7  jmp     loc_140045C26
0x140045dfc  mov     ebx, 0C0000034h
0x140045e01  xor     edx, edx; Tag
0x140045e03  mov     r8d, 20h ; ' '; RemlockSize
0x140045e09  mov     rcx, r13; RemoveLock
0x140045e0c  call    cs:__imp_IoReleaseRemoveLockEx
0x140045e13  nop     dword ptr [rax+rax+00h]
0x140045e18  jmp     loc_140045C39
0x140045e1d  mov     ebx, 0C0000016h
0x140045e22  jmp     short loc_140045E01
0x140045e24  call    ?Free@CmsLookasides@@SAXPEAX@Z; CmsLookasides::Free(void *)
0x140045e29  jmp     loc_140045D0F
0x140045e2e  xor     edx, edx; Tag
0x140045e30  call    cs:__imp_ExFreePoolWithTag
0x140045e37  nop     dword ptr [rax+rax+00h]
0x140045e3c  jmp     loc_140045D1F
```
