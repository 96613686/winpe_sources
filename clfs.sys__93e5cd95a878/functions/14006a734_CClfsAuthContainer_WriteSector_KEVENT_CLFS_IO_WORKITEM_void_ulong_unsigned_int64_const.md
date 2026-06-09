# CClfsAuthContainer::WriteSector(_KEVENT *,_CLFS_IO_WORKITEM *,void *,ulong,unsigned __int64 * const)

- ea: `0x14006a734`
- end: `0x14006a9a8`
- name: `?WriteSector@CClfsAuthContainer@@QEAAJPEAU_KEVENT@@PEAU_CLFS_IO_WORKITEM@@PEAXKQEA_K@Z`
- size: `628`
- prototype: `__int64 __usercall@<rax>(CClfsAuthContainer *__hidden this@<rcx>, struct _KEVENT *@<rdx>, struct _CLFS_IO_WORKITEM *@<r8>, void *@<r9>, unsigned int, unsigned __int64 *const)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14000cd20`
- `0x14004ae18`
- `0x140060efc`

## callees

- `0x1400018d8`
- `0x140001990`
- `0x14001091c`
- `0x1400125b0`
- `0x140012788`
- `0x140013928`
- `0x140013c9c`
- `0x140017f20`
- `0x14006a734`
- `0x14006a9b0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14006a901`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006a901`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006a7f2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006a869`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006a7f2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006a869`
- `ntoskrnl!IoQueueWorkItem` at `0x14006a995`
- `ntoskrnl!IoQueueWorkItem` at `0x14007b454`
- `ntoskrnl!IoQueueWorkItem` at `0x14006a995`
- `ntoskrnl!IoQueueWorkItem` at `0x14007b454`

## pseudocode

```c
__int64 __fastcall CClfsAuthContainer::WriteSector(
        CClfsAuthContainer *this,
        struct _KEVENT *a2,
        struct _CLFS_IO_WORKITEM *a3,
        void *a4,
        unsigned int a5,
        unsigned __int64 *const a6)
{
  CClfsAuthContainerIoRequest *v9; // rdi
  CClfsSectorIoNode *v10; // rsi
  char v11; // r12
  ULONG_PTR v12; // rcx
  int v13; // ebx
  CClfsSectorIoNode *v14; // rax
  CClfsAuthContainerIoRequest *v15; // rax
  char v17; // [rsp+31h] [rbp-57h]

  v9 = 0;
  v10 = 0;
  v11 = 0;
  v17 = 0;
  v12 = *((_QWORD *)this + 15);
  if ( !v12 )
  {
    v13 = -1073741816;
    goto LABEL_19;
  }
  if ( (*((_BYTE *)this + 172) & 1) == 0 )
  {
    v13 = CClfsContainer::WriteSector(v12, a2, a3, a4, a5, a6);
    v11 = 1;
    goto LABEL_19;
  }
  v13 = CClfsAuthContainer::Lock(this, a2 != 0);
  if ( v13 >= 0 )
  {
    v17 = 1;
    v14 = (CClfsSectorIoNode *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.Reserved);
    if ( v14 )
      v10 = CClfsSectorIoNode::CClfsSectorIoNode(v14, *((struct _DEVICE_OBJECT **)this + 22));
    else
      v10 = 0;
    if ( !v10 )
      goto LABEL_13;
    (**(void (__fastcall ***)(CClfsSectorIoNode *))v10)(v10);
    v13 = CClfsSectorIoNode::Initialize(v10, a4, a5, *a6);
    if ( v13 < 0 )
      goto LABEL_19;
    v15 = (CClfsAuthContainerIoRequest *)ExAllocateFromNPagedLookasideList(&CClfsAuthContainerIoRequest::m_laList);
    v9 = v15
       ? CClfsAuthContainerIoRequest::CClfsAuthContainerIoRequest(v15, *((struct _DEVICE_OBJECT **)this + 22))
       : 0LL;
    if ( v9 )
    {
      (**(void (__fastcall ***)(CClfsAuthContainerIoRequest *))v9)(v9);
      v13 = CClfsAuthContainerIoRequest::PrepareForIo(v9, a2, a3, v10, this);
      if ( v13 >= 0 )
      {
        v13 = CClfsAuthContainerIoRequest::Dispatch(v9);
        v11 = 1;
        if ( a2 )
        {
          KeWaitForSingleObject(a2, Executive, 0, 0, 0);
          v13 = *((_DWORD *)v9 + 100);
        }
      }
    }
    else
    {
LABEL_13:
      v13 = -1073741670;
    }
  }
LABEL_19:
  if ( v9 )
    (*(void (__fastcall **)(CClfsAuthContainerIoRequest *))(*(_QWORD *)v9 + 8LL))(v9);
  if ( v10 )
    (*(void (__fastcall **)(CClfsSectorIoNode *))(*(_QWORD *)v10 + 8LL))(v10);
  if ( !v11 )
  {
    if ( v17 )
      CClfsAuthContainer::Unlock(this);
    if ( a3 )
    {
      *((_DWORD *)a3 + 10) = v13;
      *((_QWORD *)a3 + 6) = 0;
      IoQueueWorkItem(*(PIO_WORKITEM *)a3, CClfsContainer::WorkRoutine, CriticalWorkQueue, a3);
      return 259;
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14006a734  mov     rax, rsp
0x14006a737  mov     [rax+20h], r9
0x14006a73b  mov     [rax+18h], r8
0x14006a73f  mov     [rax+8], rcx
0x14006a743  push    rbx
0x14006a744  push    rsi
0x14006a745  push    rdi
0x14006a746  push    r12
0x14006a748  push    r13
0x14006a74a  push    r14
0x14006a74c  push    r15
0x14006a74e  sub     rsp, 50h
0x14006a752  mov     r14, r8
0x14006a755  mov     r13, rdx
0x14006a758  mov     r15, rcx
0x14006a75b  mov     dword ptr [rax-54h], 0
0x14006a762  xor     edi, edi
0x14006a764  mov     [rax-50h], rdi
0x14006a768  xor     esi, esi
0x14006a76a  mov     [rax-48h], rsi
0x14006a76e  xor     r12b, r12b
0x14006a771  mov     [rax-58h], r12b
0x14006a775  mov     [rax-57h], sil
0x14006a779  mov     rcx, [rcx+78h]; BugCheckParameter3
0x14006a77d  test    rcx, rcx
0x14006a780  jz      short loc_14006A7BC
0x14006a782  test    byte ptr [r15+0ACh], 1
0x14006a78a  jnz     short loc_14006A7CA
0x14006a78c  mov     rax, [rsp+88h+arg_28]
0x14006a794  mov     [rsp+88h+var_60], rax; unsigned __int64 *
0x14006a799  mov     eax, [rsp+88h+arg_20]
0x14006a7a0  mov     dword ptr [rsp+88h+Timeout], eax; unsigned int
0x14006a7a4  call    ?WriteSector@CClfsContainer@@QEAAJPEAU_KEVENT@@PEAU_CLFS_IO_WORKITEM@@PEAXKQEA_K@Z; CClfsContainer::WriteSector(_KEVENT *,_CLFS_IO_WORKITEM *,void *,ulong,unsigned __int64 * const)
0x14006a7a9  mov     ebx, eax
0x14006a7ab  mov     [rsp+88h+var_54], eax
0x14006a7af  mov     r12b, 1
0x14006a7b2  mov     [rsp+88h+var_58], r12b
0x14006a7b7  jmp     loc_14006A91C
0x14006a7bc  mov     ebx, 0C0000008h
0x14006a7c1  mov     [rsp+88h+var_54], ebx
0x14006a7c5  jmp     loc_14006A91C
0x14006a7ca  test    r13, r13
0x14006a7cd  setnz   dl; unsigned __int8
0x14006a7d0  mov     rcx, r15; this
0x14006a7d3  call    ?Lock@CClfsAuthContainer@@AEAAJE@Z; CClfsAuthContainer::Lock(uchar)
0x14006a7d8  mov     ebx, eax
0x14006a7da  mov     [rsp+88h+var_54], eax
0x14006a7de  test    eax, eax
0x14006a7e0  js      loc_14006A91C
0x14006a7e6  mov     [rsp+88h+var_57], 1
0x14006a7eb  lea     rcx, WPP_MAIN_CB.Reserved; Lookaside
0x14006a7f2  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006a7f9  nop     dword ptr [rax+rax+00h]
0x14006a7fe  test    rax, rax
0x14006a801  jz      short loc_14006A817
0x14006a803  mov     rdx, [r15+0B0h]; struct _DEVICE_OBJECT *
0x14006a80a  mov     rcx, rax; this
0x14006a80d  call    ??0CClfsSectorIoNode@@QEAA@PEAU_DEVICE_OBJECT@@@Z; CClfsSectorIoNode::CClfsSectorIoNode(_DEVICE_OBJECT *)
0x14006a812  mov     rsi, rax
0x14006a815  jmp     short loc_14006A819
0x14006a817  xor     esi, esi
0x14006a819  mov     [rsp+88h+var_48], rsi
0x14006a81e  test    rsi, rsi
0x14006a821  jz      short loc_14006A88E
0x14006a823  mov     rax, [rsi]
0x14006a826  mov     rax, [rax]
0x14006a829  mov     rcx, rsi
0x14006a82c  call    _guard_dispatch_icall
0x14006a831  mov     r9, [rsp+88h+arg_28]
0x14006a839  mov     r9, [r9]; unsigned __int64
0x14006a83c  mov     r8d, [rsp+88h+arg_20]; unsigned int
0x14006a844  mov     rdx, [rsp+88h+arg_18]; void *
0x14006a84c  mov     rcx, rsi; this
0x14006a84f  call    ?Initialize@CClfsSectorIoNode@@QEAAJPEAXK_K@Z; CClfsSectorIoNode::Initialize(void *,ulong,unsigned __int64)
0x14006a854  mov     ebx, eax
0x14006a856  mov     [rsp+88h+var_54], eax
0x14006a85a  test    eax, eax
0x14006a85c  js      loc_14006A91C
0x14006a862  lea     rcx, ?m_laList@CClfsAuthContainerIoRequest@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x14006a869  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006a870  nop     dword ptr [rax+rax+00h]
0x14006a875  test    rax, rax
0x14006a878  jz      short loc_14006A898
0x14006a87a  mov     rdx, [r15+0B0h]; struct _DEVICE_OBJECT *
0x14006a881  mov     rcx, rax; this
0x14006a884  call    ??0CClfsAuthContainerIoRequest@@QEAA@PEAU_DEVICE_OBJECT@@@Z; CClfsAuthContainerIoRequest::CClfsAuthContainerIoRequest(_DEVICE_OBJECT *)
0x14006a889  mov     rdi, rax
0x14006a88c  jmp     short loc_14006A89A
0x14006a88e  mov     ebx, 0C000009Ah
0x14006a893  jmp     loc_14006A7C1
0x14006a898  xor     edi, edi
0x14006a89a  mov     [rsp+88h+var_50], rdi
0x14006a89f  test    rdi, rdi
0x14006a8a2  jz      short loc_14006A88E
0x14006a8a4  mov     rax, [rdi]
0x14006a8a7  mov     rax, [rax]
0x14006a8aa  mov     rcx, rdi
0x14006a8ad  call    _guard_dispatch_icall
0x14006a8b2  mov     [rsp+88h+Timeout], r15; struct CClfsAuthContainer *
0x14006a8b7  mov     r9, rsi; struct IContainerWritable *
0x14006a8ba  mov     r8, r14; struct _CLFS_IO_WORKITEM *
0x14006a8bd  mov     rdx, r13; struct _KEVENT *
0x14006a8c0  mov     rcx, rdi; this
0x14006a8c3  call    ?PrepareForIo@CClfsAuthContainerIoRequest@@QEAAJPEAU_KEVENT@@PEAU_CLFS_IO_WORKITEM@@PEAUIContainerWritable@@PEAVCClfsAuthContainer@@@Z; CClfsAuthContainerIoRequest::PrepareForIo(_KEVENT *,_CLFS_IO_WORKITEM *,IContainerWritable *,CClfsAuthContainer *)
0x14006a8c8  mov     ebx, eax
0x14006a8ca  mov     [rsp+88h+var_54], eax
0x14006a8ce  test    eax, eax
0x14006a8d0  js      short loc_14006A91C
0x14006a8d2  mov     rcx, rdi; this
0x14006a8d5  call    ?Dispatch@CClfsAuthContainerIoRequest@@QEAAJXZ; CClfsAuthContainerIoRequest::Dispatch(void)
0x14006a8da  mov     ebx, eax
0x14006a8dc  mov     [rsp+88h+var_54], eax
0x14006a8e0  mov     r12b, 1
0x14006a8e3  mov     [rsp+88h+var_58], r12b
0x14006a8e8  test    r13, r13
0x14006a8eb  jz      short loc_14006A91C
0x14006a8ed  mov     [rsp+88h+Timeout], 0; Timeout
0x14006a8f6  xor     r9d, r9d; Alertable
0x14006a8f9  xor     r8d, r8d; WaitMode
0x14006a8fc  xor     edx, edx; WaitReason
0x14006a8fe  mov     rcx, r13; Object
0x14006a901  call    cs:__imp_KeWaitForSingleObject
0x14006a908  nop     dword ptr [rax+rax+00h]
0x14006a90d  mov     [rsp+88h+var_54], eax
0x14006a911  mov     ebx, [rdi+190h]
0x14006a917  jmp     loc_14006A7C1
0x14006a91c  test    rdi, rdi
0x14006a91f  jnz     short loc_14006A93E
0x14006a921  test    rsi, rsi
0x14006a924  jnz     short loc_14006A94F
0x14006a926  test    r12b, r12b
0x14006a929  jz      short loc_14006A960
0x14006a92b  mov     eax, ebx
0x14006a92d  add     rsp, 50h
0x14006a931  pop     r15
0x14006a933  pop     r14
0x14006a935  pop     r13
0x14006a937  pop     r12
0x14006a939  pop     rdi
0x14006a93a  pop     rsi
0x14006a93b  pop     rbx
0x14006a93c  retn
0x14006a93e  mov     rax, [rdi]
0x14006a941  mov     rax, [rax+8]
0x14006a945  mov     rcx, rdi
0x14006a948  call    _guard_dispatch_icall
0x14006a94d  jmp     short loc_14006A921
0x14006a94f  mov     rax, [rsi]
0x14006a952  mov     rax, [rax+8]
0x14006a956  mov     rcx, rsi
0x14006a959  call    _guard_dispatch_icall
0x14006a95e  jmp     short loc_14006A926
0x14006a960  cmp     [rsp+88h+var_57], 0
0x14006a965  jz      short loc_14006A96F
0x14006a967  mov     rcx, r15; this
0x14006a96a  call    ?Unlock@CClfsAuthContainer@@AEAAXXZ; CClfsAuthContainer::Unlock(void)
0x14006a96f  test    r12b, r12b
0x14006a972  jnz     short loc_14006A92B
0x14006a974  test    r14, r14
0x14006a977  jz      short loc_14006A92B
0x14006a979  mov     [r14+28h], ebx
0x14006a97d  mov     qword ptr [r14+30h], 0
0x14006a985  mov     r9, r14; Context
0x14006a988  xor     r8d, r8d; QueueType
0x14006a98b  lea     rdx, ?WorkRoutine@CClfsContainer@@SAXPEAU_DEVICE_OBJECT@@PEAX@Z; WorkerRoutine
0x14006a992  mov     rcx, [r14]; IoWorkItem
0x14006a995  call    cs:__imp_IoQueueWorkItem
0x14006a99c  nop     dword ptr [rax+rax+00h]
0x14006a9a1  mov     ebx, 103h
0x14006a9a6  jmp     short loc_14006A92B
0x14007b3c9  push    rbx
0x14007b3cb  push    rbp
0x14007b3cc  sub     rsp, 38h
0x14007b3d0  mov     rbp, rdx
0x14007b3d3  mov     rcx, [rbp+38h]
0x14007b3d7  test    rcx, rcx
0x14007b3da  jz      short loc_14007B3F0
0x14007b3dc  mov     rax, [rcx]
0x14007b3df  mov     rax, [rax+8]
0x14007b3e3  call    _guard_dispatch_icall
0x14007b3e8  mov     qword ptr [rbp+38h], 0
0x14007b3f0  mov     rcx, [rbp+40h]
0x14007b3f4  test    rcx, rcx
0x14007b3f7  jz      short loc_14007B40D
0x14007b3f9  mov     rax, [rcx]
0x14007b3fc  mov     rax, [rax+8]
0x14007b400  call    _guard_dispatch_icall
0x14007b405  mov     qword ptr [rbp+40h], 0
0x14007b40d  mov     bl, [rbp+30h]
0x14007b410  test    bl, bl
0x14007b412  jnz     short loc_14007B467
0x14007b414  cmp     [rbp+31h], bl
0x14007b417  jz      short loc_14007B426
0x14007b419  mov     rcx, [rbp+90h]; this
0x14007b420  call    ?Unlock@CClfsAuthContainer@@AEAAXXZ; CClfsAuthContainer::Unlock(void)
0x14007b425  nop
0x14007b426  test    bl, bl
0x14007b428  jnz     short loc_14007B467
0x14007b42a  mov     rcx, [rbp+0A0h]
0x14007b431  test    rcx, rcx
0x14007b434  jz      short loc_14007B467
0x14007b436  mov     eax, [rbp+34h]
0x14007b439  mov     [rcx+28h], eax
0x14007b43c  mov     qword ptr [rcx+30h], 0
0x14007b444  mov     r9, rcx; Context
0x14007b447  xor     r8d, r8d; QueueType
0x14007b44a  lea     rdx, ?WorkRoutine@CClfsContainer@@SAXPEAU_DEVICE_OBJECT@@PEAX@Z; WorkerRoutine
0x14007b451  mov     rcx, [rcx]; IoWorkItem
0x14007b454  call    cs:__imp_IoQueueWorkItem
0x14007b45b  nop     dword ptr [rax+rax+00h]
0x14007b460  mov     dword ptr [rbp+34h], 103h
0x14007b467  add     rsp, 38h
0x14007b46b  pop     rbp
0x14007b46c  pop     rbx
0x14007b46d  retn
```
