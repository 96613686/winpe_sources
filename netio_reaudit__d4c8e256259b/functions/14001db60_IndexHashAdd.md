# IndexHashAdd

- ea: `0x14001db60`
- end: `0x14001dd93`
- name: `IndexHashAdd`
- size: `563`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009c50`
- `0x14001db60`
- `0x14001dda0`
- `0x14004efd4`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x14001dcfb`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14001dcfb`
- `ntoskrnl!ExAllocatePool2` at `0x14001db95`
- `ntoskrnl!ExAllocatePool2` at `0x14001db95`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dbc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dbc3`
- `NDIS!NdisReleaseRWLock` at `0x14001dd2c`
- `NDIS!NdisReleaseRWLock` at `0x14001dd53`
- `NDIS!NdisReleaseRWLock` at `0x14001dd2c`
- `NDIS!NdisReleaseRWLock` at `0x14001dd53`
- `NDIS!NdisAcquireRWLockWrite` at `0x14001dce1`
- `NDIS!NdisAcquireRWLockWrite` at `0x14001dce1`

## pseudocode

```c
__int64 __fastcall IndexHashAdd(__int64 a1, struct _LIST_ENTRY *a2)
{
  __int64 v4; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *Pool2; // rdi
  struct _NDIS_RW_LOCK_EX *v7; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+60h] [rbp+18h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v4 = 0;
  Pool2 = (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)ExAllocatePool2(64, 32, 1215325783);
  if ( Pool2 )
    goto LABEL_2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"ExAllocatePool2",
      23);
  }
  v4 = -1073741801;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0 )
  {
LABEL_2:
    if ( !v4 )
    {
      a2->Blink = a2;
      a2->Flink = a2;
      a2[2].Flink = &Pool2->Linkage;
      Pool2[1].Linkage.Flink = a2;
      InitializeHashEntry(a1, a2[1].Blink, Pool2);
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)a1, &LockState, 1u);
      if ( RtlInsertEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 16), Pool2, Pool2->Signature, 0) )
      {
        WfpRestructureHashtable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 16));
        v7 = *(struct _NDIS_RW_LOCK_EX **)a1;
        *(_QWORD *)(a1 + 24) += 32LL;
        NdisReleaseRWLock(v7, &LockState);
        return v4;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"RtlInsertEntryHashTable",
          23);
      }
      v4 = -1073741801;
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)a1, &LockState);
    }
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0);
  }
  else
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"WfpPoolAllocNonPaged",
      23);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"IndexHashAdd",
      v4);
  }
  return v4;
}

```

## disassembly

```asm
0x14001db60  mov     [rsp+arg_0], rbx
0x14001db65  mov     [rsp+arg_8], rbp
0x14001db6a  push    rsi
0x14001db6b  push    rdi
0x14001db6c  push    r14
0x14001db6e  sub     rsp, 30h
0x14001db72  xor     eax, eax
0x14001db74  mov     r14, rdx
0x14001db77  mov     rsi, rcx
0x14001db7a  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x14001db7f  mov     edx, 20h ; ' '
0x14001db84  mov     [rsp+48h+LockState.Flags], al
0x14001db88  mov     ecx, 40h ; '@'
0x14001db8d  mov     r8d, 48706657h
0x14001db93  xor     ebx, ebx
0x14001db95  call    cs:__imp_ExAllocatePool2
0x14001db9c  nop     dword ptr [rax+rax+00h]
0x14001dba1  lea     rbp, WPP_GLOBAL_Control
0x14001dba8  mov     rdi, rax
0x14001dbab  test    rax, rax
0x14001dbae  jz      short loc_14001DC21
0x14001dbb0  test    rbx, rbx
0x14001dbb3  jz      loc_14001DCB8
0x14001dbb9  test    rdi, rdi
0x14001dbbc  jz      short loc_14001DBCF
0x14001dbbe  xor     edx, edx; Tag
0x14001dbc0  mov     rcx, rdi; P
0x14001dbc3  call    cs:__imp_ExFreePoolWithTag
0x14001dbca  nop     dword ptr [rax+rax+00h]
0x14001dbcf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dbd6  cmp     rcx, rbp
0x14001dbd9  jz      short loc_14001DC0A
0x14001dbdb  cmp     byte ptr [rcx+29h], 2
0x14001dbdf  jb      short loc_14001DC0A
0x14001dbe1  test    dword ptr [rcx+2Ch], 1000h
0x14001dbe8  jz      short loc_14001DC0A
0x14001dbea  mov     rcx, [rcx+18h]
0x14001dbee  lea     r9, aIndexhashadd; "IndexHashAdd"
0x14001dbf5  mov     edx, 0Fh
0x14001dbfa  mov     [rsp+48h+var_28], ebx
0x14001dbfe  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14001dc05  call    WPP_SF_sd
0x14001dc0a  mov     rbp, [rsp+48h+arg_8]
0x14001dc0f  mov     rax, rbx
0x14001dc12  mov     rbx, [rsp+48h+arg_0]
0x14001dc17  add     rsp, 30h
0x14001dc1b  pop     r14
0x14001dc1d  pop     rdi
0x14001dc1e  pop     rsi
0x14001dc1f  retn
0x14001dc21  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dc28  cmp     rcx, rbp
0x14001dc2b  jz      short loc_14001DC33
0x14001dc2d  cmp     byte ptr [rcx+29h], 2
0x14001dc31  jnb     short loc_14001DC86
0x14001dc33  mov     rbx, 0FFFFFFFFC0000017h
0x14001dc3a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dc41  cmp     rcx, rbp
0x14001dc44  jz      loc_14001DBB0
0x14001dc4a  cmp     byte ptr [rcx+29h], 2
0x14001dc4e  jb      loc_14001DBB0
0x14001dc54  test    dword ptr [rcx+2Ch], 1000h
0x14001dc5b  jz      loc_14001DBB0
0x14001dc61  mov     rcx, [rcx+18h]
0x14001dc65  lea     r9, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x14001dc6c  mov     edx, 0Fh
0x14001dc71  mov     [rsp+48h+var_28], ebx
0x14001dc75  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14001dc7c  call    WPP_SF_sd
0x14001dc81  jmp     loc_14001DBCF
0x14001dc86  test    dword ptr [rcx+2Ch], 1000h
0x14001dc8d  jz      short loc_14001DC33
0x14001dc8f  mov     rcx, [rcx+18h]
0x14001dc93  lea     r9, aExallocatepool; "ExAllocatePool2"
0x14001dc9a  mov     edx, 0Ah
0x14001dc9f  mov     [rsp+48h+var_28], 0C0000017h
0x14001dca7  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14001dcae  call    WPP_SF_sd
0x14001dcb3  jmp     loc_14001DC33
0x14001dcb8  mov     [r14+8], r14
0x14001dcbc  mov     r8, rdi
0x14001dcbf  mov     [r14], r14
0x14001dcc2  mov     rcx, rsi
0x14001dcc5  mov     [r14+20h], rdi
0x14001dcc9  mov     [rdi+18h], r14
0x14001dccd  mov     rdx, [r14+18h]
0x14001dcd1  call    InitializeHashEntry
0x14001dcd6  mov     rcx, [rsi]; Lock
0x14001dcd9  lea     rdx, [rsp+48h+LockState]; LockState
0x14001dcde  mov     r8b, 1; Flags
0x14001dce1  call    cs:__imp_NdisAcquireRWLockWrite
0x14001dce8  nop     dword ptr [rax+rax+00h]
0x14001dced  mov     r8, [rdi+10h]; Signature
0x14001dcf1  xor     r9d, r9d; Context
0x14001dcf4  mov     rcx, [rsi+10h]; HashTable
0x14001dcf8  mov     rdx, rdi; Entry
0x14001dcfb  call    cs:__imp_RtlInsertEntryHashTable
0x14001dd02  nop     dword ptr [rax+rax+00h]
0x14001dd07  test    al, al
0x14001dd09  jnz     short loc_14001DD3D
0x14001dd0b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dd12  cmp     rcx, rbp
0x14001dd15  jz      short loc_14001DD1D
0x14001dd17  cmp     byte ptr [rcx+29h], 2
0x14001dd1b  jnb     short loc_14001DD64
0x14001dd1d  mov     rcx, [rsi]; Lock
0x14001dd20  lea     rdx, [rsp+48h+LockState]; LockState
0x14001dd25  mov     rbx, 0FFFFFFFFC0000017h
0x14001dd2c  call    cs:__imp_NdisReleaseRWLock
0x14001dd33  nop     dword ptr [rax+rax+00h]
0x14001dd38  jmp     loc_14001DBB9
0x14001dd3d  mov     rcx, [rsi+10h]; HashTable
0x14001dd41  call    WfpRestructureHashtable
0x14001dd46  mov     rcx, [rsi]; Lock
0x14001dd49  lea     rdx, [rsp+48h+LockState]; LockState
0x14001dd4e  add     qword ptr [rsi+18h], 20h ; ' '
0x14001dd53  call    cs:__imp_NdisReleaseRWLock
0x14001dd5a  nop     dword ptr [rax+rax+00h]
0x14001dd5f  jmp     loc_14001DC0A
0x14001dd64  test    dword ptr [rcx+2Ch], 1000h
0x14001dd6b  jz      short loc_14001DD1D
0x14001dd6d  mov     rcx, [rcx+18h]
0x14001dd71  lea     r9, aRtlinsertentry; "RtlInsertEntryHashTable"
0x14001dd78  mov     edx, 0Ah
0x14001dd7d  mov     [rsp+48h+var_28], 0C0000017h
0x14001dd85  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14001dd8c  call    WPP_SF_sd
0x14001dd91  jmp     short loc_14001DD1D
```
