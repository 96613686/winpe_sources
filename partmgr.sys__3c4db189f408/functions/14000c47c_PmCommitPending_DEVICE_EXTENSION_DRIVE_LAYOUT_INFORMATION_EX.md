# PmCommitPending(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x14000c47c`
- end: `0x14000c680`
- name: `?PmCommitPending@@YAXPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `516`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005c50`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x140005438`
- `0x140005994`
- `0x140005a84`
- `0x140008498`
- `0x14000a0fc`
- `0x14000b39c`
- `0x14000b700`
- `0x14000c47c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000c64a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c64a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c617`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c617`

## pseudocode

```c
void __fastcall PmCommitPending(struct _DEVICE_EXTENSION *a1, struct _DRIVE_LAYOUT_INFORMATION_EX *a2)
{
  char *v2; // rsi
  char *i; // rdi
  char *v5; // rbx
  unsigned int v6; // r12d
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // ecx
  int v11; // r8d
  __int64 v12; // r9
  int v13; // ecx
  int v14; // r8d
  __int64 v15; // r9
  unsigned __int64 v16; // rax
  __int64 v17; // r8
  unsigned __int64 v18; // rax
  __int64 v19; // r8
  KIRQL v20; // r9
  _QWORD *v21; // [rsp+50h] [rbp-18h] BYREF
  __int64 v22; // [rsp+58h] [rbp-10h] BYREF
  int v23; // [rsp+B0h] [rbp+48h] BYREF
  struct _DRIVE_LAYOUT_INFORMATION_EX *v24; // [rsp+B8h] [rbp+50h]
  unsigned int v25; // [rsp+C0h] [rbp+58h] BYREF
  _QWORD *v26; // [rsp+C8h] [rbp+60h] BYREF

  v24 = a2;
  v2 = (char *)a1 + 896;
  for ( i = (char *)*((_QWORD *)a1 + 112); i != v2; i = *(char **)i )
  {
    v5 = i - 144;
    if ( *((char **)i + 23) != i + 184 )
    {
      v6 = PmCountList((struct _LIST_ENTRY *)(v5 + 312));
      v7 = PmCountList((struct _LIST_ENTRY *)(i + 184));
      if ( v6 != v7 )
      {
        if ( v6 )
        {
          if ( (unsigned int)dword_140017088 > 5 && (unsigned __int8)tlgKeywordOn(v9, v8, v7) )
          {
            v23 = v14;
            v21 = v5 + 216;
            LODWORD(v26) = *(_DWORD *)(v15 + 4);
            v22 = v15 + 8;
            v25 = v6;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v13,
              (unsigned int)byte_140014849,
              v14,
              v15,
              (__int64)&v22,
              (__int64)&v26,
              (__int64)&v21,
              (__int64)&v25,
              (__int64)&v23);
          }
        }
        else if ( v7 > 1
               && (unsigned int)dword_140017088 > 5
               && (unsigned __int8)tlgKeywordOn((unsigned int)dword_140017088, v8, v7) )
        {
          v23 = v11;
          v26 = v5 + 216;
          v25 = *(_DWORD *)(v12 + 4);
          v21 = (_QWORD *)(v12 + 8);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            v10,
            (unsigned int)&word_1400148AE,
            v11,
            v12,
            (__int64)&v21,
            (__int64)&v25,
            (__int64)&v26,
            (__int64)&v23);
        }
      }
      if ( (*((_DWORD *)v5 + 10) & 0x10) != 0
        || (PartitionOffset((struct _PARTITION_EXTENSION *)(i - 144), 1u),
            v16 = PartitionOffset((struct _PARTITION_EXTENSION *)(i - 144), 0),
            v17 != v16)
        || (PartitionLength((struct _PARTITION_EXTENSION *)(i - 144), 1u),
            v18 = PartitionLength((struct _PARTITION_EXTENSION *)(i - 144), 0),
            v19 != v18) )
      {
        PartitionAcquireRundownExclusive((struct _PARTITION_EXTENSION *)(i - 144));
        KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
        PmSwapList((struct _LIST_ENTRY *)(v5 + 312), (struct _LIST_ENTRY *)(i + 184));
        if ( v6 )
          *((_DWORD *)v5 + 10) |= 0x10u;
        KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v20);
        PartitionReleaseRundownExclusive((struct _PARTITION_EXTENSION *)(i - 144));
      }
    }
  }
}

```

## disassembly

```asm
0x14000c47c  mov     [rsp-40h+arg_8], rdx
0x14000c481  push    rbp
0x14000c482  push    rbx
0x14000c483  push    rsi
0x14000c484  push    rdi
0x14000c485  push    r12
0x14000c487  push    r13
0x14000c489  push    r14
0x14000c48b  push    r15
0x14000c48d  mov     rbp, rsp
0x14000c490  sub     rsp, 68h
0x14000c494  lea     rsi, [rcx+380h]
0x14000c49b  mov     r9, rdx
0x14000c49e  mov     rdi, [rsi]
0x14000c4a1  mov     r13, rcx
0x14000c4a4  jmp     loc_14000C665
0x14000c4a9  lea     rbx, [rdi-90h]
0x14000c4b0  lea     r14, [rbx+148h]
0x14000c4b7  cmp     [r14], r14
0x14000c4ba  jz      loc_14000C662
0x14000c4c0  lea     rcx, [rbx+138h]; struct _LIST_ENTRY *
0x14000c4c7  call    ?PmCountList@@YAKPEAU_LIST_ENTRY@@@Z; PmCountList(_LIST_ENTRY *)
0x14000c4cc  mov     rcx, r14; struct _LIST_ENTRY *
0x14000c4cf  mov     r12d, eax
0x14000c4d2  call    ?PmCountList@@YAKPEAU_LIST_ENTRY@@@Z; PmCountList(_LIST_ENTRY *)
0x14000c4d7  mov     r8d, eax
0x14000c4da  cmp     r12d, eax
0x14000c4dd  jz      loc_14000C5CC
0x14000c4e3  test    r12d, r12d
0x14000c4e6  jnz     short loc_14000C55D
0x14000c4e8  cmp     eax, 1
0x14000c4eb  jbe     loc_14000C5CC
0x14000c4f1  mov     ecx, cs:dword_140017088
0x14000c4f7  cmp     ecx, 5
0x14000c4fa  jbe     loc_14000C5CC
0x14000c500  call    _tlgKeywordOn
0x14000c505  test    al, al
0x14000c507  jz      loc_14000C5CC
0x14000c50d  lea     rax, [rbx+0D8h]
0x14000c514  mov     [rbp+arg_0], r8d
0x14000c518  mov     [rbp+arg_18], rax
0x14000c51c  lea     rdx, word_1400148AE
0x14000c523  mov     eax, [r9+4]
0x14000c527  mov     [rbp+arg_10], eax
0x14000c52a  lea     rax, [r9+8]
0x14000c52e  mov     [rbp+var_18], rax
0x14000c532  lea     rax, [rbp+arg_0]
0x14000c536  mov     [rsp+68h+var_30], rax
0x14000c53b  lea     rax, [rbp+arg_18]
0x14000c53f  mov     [rsp+68h+var_38], rax
0x14000c544  lea     rax, [rbp+arg_10]
0x14000c548  mov     [rsp+68h+var_40], rax
0x14000c54d  lea     rax, [rbp+var_18]
0x14000c551  mov     [rsp+68h+var_48], rax
0x14000c556  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x14000c55b  jmp     short loc_14000C5CC
0x14000c55d  mov     eax, cs:dword_140017088
0x14000c563  cmp     eax, 5
0x14000c566  jbe     short loc_14000C5CC
0x14000c568  call    _tlgKeywordOn
0x14000c56d  test    al, al
0x14000c56f  jz      short loc_14000C5CC
0x14000c571  lea     rax, [rbx+0D8h]
0x14000c578  mov     [rbp+arg_0], r8d
0x14000c57c  mov     [rbp+var_18], rax
0x14000c580  lea     rdx, byte_140014849
0x14000c587  mov     eax, [r9+4]
0x14000c58b  mov     dword ptr [rbp+arg_18], eax
0x14000c58e  lea     rax, [r9+8]
0x14000c592  mov     [rbp+var_10], rax
0x14000c596  lea     rax, [rbp+arg_0]
0x14000c59a  mov     [rsp+68h+var_28], rax
0x14000c59f  lea     rax, [rbp+arg_10]
0x14000c5a3  mov     [rsp+68h+var_30], rax
0x14000c5a8  lea     rax, [rbp+var_18]
0x14000c5ac  mov     [rsp+68h+var_38], rax
0x14000c5b1  lea     rax, [rbp+arg_18]
0x14000c5b5  mov     [rsp+68h+var_40], rax
0x14000c5ba  lea     rax, [rbp+var_10]
0x14000c5be  mov     [rsp+68h+var_48], rax
0x14000c5c3  mov     [rbp+arg_10], r12d
0x14000c5c7  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000c5cc  mov     eax, [rbx+28h]
0x14000c5cf  test    al, 10h
0x14000c5d1  jnz     short loc_14000C60B
0x14000c5d3  mov     dl, 1; unsigned __int8
0x14000c5d5  mov     rcx, rbx; struct _PARTITION_EXTENSION *
0x14000c5d8  call    ?PartitionOffset@@YA_KPEAU_PARTITION_EXTENSION@@E@Z; PartitionOffset(_PARTITION_EXTENSION *,uchar)
0x14000c5dd  xor     edx, edx; unsigned __int8
0x14000c5df  mov     rcx, rbx; struct _PARTITION_EXTENSION *
0x14000c5e2  mov     r8, rax
0x14000c5e5  call    ?PartitionOffset@@YA_KPEAU_PARTITION_EXTENSION@@E@Z; PartitionOffset(_PARTITION_EXTENSION *,uchar)
0x14000c5ea  cmp     r8, rax
0x14000c5ed  jnz     short loc_14000C60B
0x14000c5ef  mov     dl, 1; unsigned __int8
0x14000c5f1  mov     rcx, rbx; struct _PARTITION_EXTENSION *
0x14000c5f4  call    ?PartitionLength@@YA_KPEAU_PARTITION_EXTENSION@@E@Z; PartitionLength(_PARTITION_EXTENSION *,uchar)
0x14000c5f9  xor     edx, edx; unsigned __int8
0x14000c5fb  mov     rcx, rbx; struct _PARTITION_EXTENSION *
0x14000c5fe  mov     r8, rax
0x14000c601  call    ?PartitionLength@@YA_KPEAU_PARTITION_EXTENSION@@E@Z; PartitionLength(_PARTITION_EXTENSION *,uchar)
0x14000c606  cmp     r8, rax
0x14000c609  jz      short loc_14000C65E
0x14000c60b  mov     rcx, rbx; struct _PARTITION_EXTENSION *
0x14000c60e  call    ?PartitionAcquireRundownExclusive@@YAXPEAU_PARTITION_EXTENSION@@@Z; PartitionAcquireRundownExclusive(_PARTITION_EXTENSION *)
0x14000c613  lea     rcx, [r13+70h]; SpinLock
0x14000c617  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c61e  nop     dword ptr [rax+rax+00h]
0x14000c623  mov     rdx, r14; struct _LIST_ENTRY *
0x14000c626  lea     rcx, [rbx+138h]; struct _LIST_ENTRY *
0x14000c62d  mov     r9b, al
0x14000c630  call    ?PmSwapList@@YAXPEAU_LIST_ENTRY@@0@Z; PmSwapList(_LIST_ENTRY *,_LIST_ENTRY *)
0x14000c635  test    r12d, r12d
0x14000c638  jz      short loc_14000C643
0x14000c63a  mov     edx, [rbx+28h]
0x14000c63d  or      edx, 10h
0x14000c640  mov     [rbx+28h], edx
0x14000c643  mov     dl, r9b; NewIrql
0x14000c646  lea     rcx, [r13+70h]; SpinLock
0x14000c64a  call    cs:__imp_KeReleaseSpinLock
0x14000c651  nop     dword ptr [rax+rax+00h]
0x14000c656  mov     rcx, rbx; struct _PARTITION_EXTENSION *
0x14000c659  call    ?PartitionReleaseRundownExclusive@@YAXPEAU_PARTITION_EXTENSION@@@Z; PartitionReleaseRundownExclusive(_PARTITION_EXTENSION *)
0x14000c65e  mov     r9, [rbp+arg_8]
0x14000c662  mov     rdi, [rdi]
0x14000c665  cmp     rdi, rsi
0x14000c668  jnz     loc_14000C4A9
0x14000c66e  add     rsp, 68h
0x14000c672  pop     r15
0x14000c674  pop     r14
0x14000c676  pop     r13
0x14000c678  pop     r12
0x14000c67a  pop     rdi
0x14000c67b  pop     rsi
0x14000c67c  pop     rbx
0x14000c67d  pop     rbp
0x14000c67e  retn
```
