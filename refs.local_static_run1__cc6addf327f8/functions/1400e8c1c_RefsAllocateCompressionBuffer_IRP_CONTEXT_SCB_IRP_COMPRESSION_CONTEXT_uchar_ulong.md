# RefsAllocateCompressionBuffer(_IRP_CONTEXT *,_SCB *,_IRP *,COMPRESSION_CONTEXT *,uchar,ulong *)

- ea: `0x1400e8c1c`
- end: `0x1400e8ed1`
- name: `?RefsAllocateCompressionBuffer@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB@@PEAU_IRP@@PEAUCOMPRESSION_CONTEXT@@EPEAK@Z`
- size: `693`
- prototype: `void __usercall(struct _IRP_CONTEXT *@<rcx>, struct _SCB *@<rdx>, struct _IRP *@<r8>, struct COMPRESSION_CONTEXT *@<r9>, unsigned __int8, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400b6ba0`

## callees

- `0x1400e8c1c`
- `0x1400ebde0`
- `0x1400ee638`
- `0x14029d5e8`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x1400e8dca`
- `ntoskrnl!IoAllocateMdl` at `0x1400e8dca`
- `ntoskrnl!IoFreeMdl` at `0x1400e8c9f`
- `ntoskrnl!IoFreeMdl` at `0x1400e8d03`
- `ntoskrnl!IoFreeMdl` at `0x1400e8ea1`
- `ntoskrnl!IoFreeMdl` at `0x1400e8c9f`
- `ntoskrnl!IoFreeMdl` at `0x1400e8d03`
- `ntoskrnl!IoFreeMdl` at `0x1400e8ea1`
- `ntoskrnl!MmUnlockPages` at `0x1400e8e91`
- `ntoskrnl!MmUnlockPages` at `0x1400e8e91`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400e8de9`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400e8de9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e8cc0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e8d2f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e8e20`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e8cc0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e8d2f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e8e20`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400e8da5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400e8da5`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400e8dfd`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400e8dfd`

## pseudocode

```c
void __fastcall RefsAllocateCompressionBuffer(
        struct _IRP_CONTEXT *a1,
        struct _MDL *a2,
        struct _IRP *a3,
        struct COMPRESSION_CONTEXT *a4,
        unsigned __int8 a5,
        unsigned int *a6)
{
  unsigned int *v6; // r15
  unsigned int *v7; // r14
  ULONG v8; // ebx
  struct _MDL *MdlAddress; // r9
  __int64 CompressionLookasideIndex; // rbx
  PMDL v14; // r9
  struct _MDL *v15; // rdx
  unsigned int v16; // eax
  unsigned int v17; // ecx
  struct _MDL *v18; // rbx
  __int64 v19; // rbp
  unsigned int v20; // r8d
  __int64 v21; // r9
  PVOID v22; // rax
  struct _MDL *Mdl; // rax
  struct _MDL *v24; // rcx
  struct _MDL *Next; // rbx
  struct _MDL *v26; // [rsp+98h] [rbp+10h] BYREF

  v26 = a2;
  v6 = a6;
  v7 = (unsigned int *)((char *)a4 + 8);
  v8 = *((_DWORD *)a4 + 2);
  if ( *a6 > v8 )
  {
    if ( *((_QWORD *)a4 + 2) )
    {
      a3->MdlAddress->ByteCount = v8;
      MdlAddress = a3->MdlAddress;
      if ( *((struct _MDL **)a4 + 4) == MdlAddress )
      {
        *((_QWORD *)a4 + 4) = 0;
        *((_QWORD *)a4 + 5) = 0;
        *((_DWORD *)a4 + 12) = 0;
        *((_DWORD *)a4 + 13) = -1;
        MdlAddress = a3->MdlAddress;
      }
      if ( *((_DWORD *)a4 + 3) == -1 )
      {
        RefsDeleteMdlAndBuffer(a1, MdlAddress, *(void **)a4);
      }
      else
      {
        CompressionLookasideIndex = RefsGetCompressionLookasideIndex(*v7);
        IoFreeMdl(v14);
        ExFreeToNPagedLookasideList(
          (PNPAGED_LOOKASIDE_LIST)&(&RefsCompressionBufferLookasideList)[CompressionLookasideIndex][16 * (unsigned __int64)*((unsigned int *)a4 + 3)],
          *(PVOID *)a4);
      }
      a3->MdlAddress = (PMDL)*((_QWORD *)a4 + 2);
      a3->UserBuffer = (PVOID)*((_QWORD *)a4 + 3);
      *((_QWORD *)a4 + 2) = 0;
      *((_DWORD *)a4 + 3) = -1;
    }
    else
    {
      v15 = (struct _MDL *)*((_QWORD *)a4 + 4);
      if ( v15 )
      {
        if ( *((_DWORD *)a4 + 13) == -1 )
        {
          RefsDeleteMdlAndBuffer(a1, v15, *((void **)a4 + 5));
        }
        else
        {
          IoFreeMdl(*((PMDL *)a4 + 4));
          v16 = RefsGetCompressionLookasideIndex(v8);
          ExFreeToNPagedLookasideList(
            (PNPAGED_LOOKASIDE_LIST)&(&RefsCompressionBufferLookasideList)[v16][16
                                                                              * (unsigned __int64)*((unsigned int *)a4
                                                                                                  + 13)],
            *((PVOID *)a4 + 5));
        }
        *((_QWORD *)a4 + 4) = 0;
        *((_QWORD *)a4 + 5) = 0;
        *((_DWORD *)a4 + 12) = 0;
        *((_DWORD *)a4 + 13) = -1;
      }
    }
    v17 = *v6;
    v18 = 0;
    v26 = 0;
    *v7 = v17;
    *(_QWORD *)a4 = 0;
    if ( v17 > 0x10000 )
      goto LABEL_20;
    *((_DWORD *)a4 + 3) = HIDWORD(KeGetPcr()[1].LockArray) % RefsNumberProcessors;
    v19 = RefsGetCompressionLookasideIndex(v17);
    v22 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(v21 + 8 * v19)
                                                                   + ((unsigned __int64)v20 << 7)));
    *(_QWORD *)a4 = v22;
    if ( v22 )
    {
      Mdl = IoAllocateMdl(v22, *v7, 0, 0, 0);
      v26 = Mdl;
      v18 = Mdl;
      if ( Mdl )
      {
        MmBuildMdlForNonPagedPool(Mdl);
        MmMdlPageContentsState(v18, 1);
      }
      else
      {
        ExFreeToNPagedLookasideList(
          (PNPAGED_LOOKASIDE_LIST)&(&RefsCompressionBufferLookasideList)[v19][16
                                                                            * (unsigned __int64)*((unsigned int *)a4 + 3)],
          *(PVOID *)a4);
        *(_QWORD *)a4 = 0;
      }
    }
    if ( !*(_QWORD *)a4 )
    {
LABEL_20:
      *((_DWORD *)a4 + 3) = -1;
      RefsCreateMdlAndBuffer(a1, (struct _SCB *)v15, 2u, 0, v7, &v26, (void **)a4);
      v18 = v26;
    }
    *((_QWORD *)a4 + 2) = a3->MdlAddress;
    *((_QWORD *)a4 + 3) = a3->UserBuffer;
    a3->MdlAddress = v18;
    a3->UserBuffer = *(PVOID *)a4;
  }
  v24 = (struct _MDL *)*((_QWORD *)a4 + 10);
  if ( v24 )
  {
    do
    {
      Next = v24->Next;
      MmUnlockPages(v24);
      IoFreeMdl(*((PMDL *)a4 + 10));
      *((_QWORD *)a4 + 10) = Next;
      v24 = Next;
    }
    while ( Next );
  }
  *v6 = *v7;
}

```

## disassembly

```asm
0x1400e8c1c  mov     [rsp+arg_8], rdx
0x1400e8c21  push    rbx
0x1400e8c22  push    rbp
0x1400e8c23  push    rsi
0x1400e8c24  push    rdi
0x1400e8c25  push    r12
0x1400e8c27  push    r13
0x1400e8c29  push    r14
0x1400e8c2b  push    r15
0x1400e8c2d  sub     rsp, 48h
0x1400e8c31  mov     r15, [rsp+88h+arg_28]
0x1400e8c39  lea     r14, [r9+8]
0x1400e8c3d  mov     ebx, [r14]
0x1400e8c40  xor     r13d, r13d
0x1400e8c43  mov     rdi, r9
0x1400e8c46  mov     rsi, r8
0x1400e8c49  mov     r12, rcx
0x1400e8c4c  cmp     [r15], ebx
0x1400e8c4f  jbe     loc_1400E8E85
0x1400e8c55  or      ebp, 0FFFFFFFFh
0x1400e8c58  lea     r9, ?RefsCompressionBufferLookasideList@@3PAPEAU_NPAGED_LOOKASIDE_LIST@@A; _NPAGED_LOOKASIDE_LIST * near * RefsCompressionBufferLookasideList
0x1400e8c5f  cmp     [rdi+10h], r13
0x1400e8c63  jz      loc_1400E8CF2
0x1400e8c69  mov     rax, [r8+8]
0x1400e8c6d  mov     [rax+28h], ebx
0x1400e8c70  mov     r9, [r8+8]
0x1400e8c74  cmp     [rdi+20h], r9
0x1400e8c78  jnz     short loc_1400E8C8D
0x1400e8c7a  mov     [rdi+20h], r13
0x1400e8c7e  mov     [rdi+28h], r13
0x1400e8c82  mov     [rdi+30h], r13d
0x1400e8c86  mov     [rdi+34h], ebp
0x1400e8c89  mov     r9, [r8+8]
0x1400e8c8d  cmp     [rdi+0Ch], ebp
0x1400e8c90  jz      short loc_1400E8CCE
0x1400e8c92  mov     ecx, [r14]; unsigned int
0x1400e8c95  call    ?RefsGetCompressionLookasideIndex@@YAKK@Z; RefsGetCompressionLookasideIndex(ulong)
0x1400e8c9a  mov     rcx, r9; Mdl
0x1400e8c9d  mov     ebx, eax
0x1400e8c9f  call    cs:__imp_IoFreeMdl
0x1400e8ca6  nop     dword ptr [rax+rax+00h]
0x1400e8cab  mov     ecx, [rdi+0Ch]
0x1400e8cae  lea     rdx, ?RefsCompressionBufferLookasideList@@3PAPEAU_NPAGED_LOOKASIDE_LIST@@A; _NPAGED_LOOKASIDE_LIST * near * RefsCompressionBufferLookasideList
0x1400e8cb5  shl     rcx, 7
0x1400e8cb9  add     rcx, [rdx+rbx*8]; Lookaside
0x1400e8cbd  mov     rdx, [rdi]; Entry
0x1400e8cc0  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400e8cc7  nop     dword ptr [rax+rax+00h]
0x1400e8ccc  jmp     short loc_1400E8CD9
0x1400e8cce  mov     r8, [rdi]; void *
0x1400e8cd1  mov     rdx, r9; struct _MDL *
0x1400e8cd4  call    ?RefsDeleteMdlAndBuffer@@YAXPEAU_VCB@@PEAU_MDL@@PEAX@Z; RefsDeleteMdlAndBuffer(_VCB *,_MDL *,void *)
0x1400e8cd9  mov     rax, [rdi+10h]
0x1400e8cdd  mov     [rsi+8], rax
0x1400e8ce1  mov     rax, [rdi+18h]
0x1400e8ce5  mov     [rsi+70h], rax
0x1400e8ce9  mov     [rdi+10h], r13
0x1400e8ced  mov     [rdi+0Ch], ebp
0x1400e8cf0  jmp     short loc_1400E8D55
0x1400e8cf2  mov     rdx, [rdi+20h]; struct _MDL *
0x1400e8cf6  test    rdx, rdx
0x1400e8cf9  jz      short loc_1400E8D5C
0x1400e8cfb  cmp     [rdi+34h], ebp
0x1400e8cfe  jz      short loc_1400E8D3D
0x1400e8d00  mov     rcx, rdx; Mdl
0x1400e8d03  call    cs:__imp_IoFreeMdl
0x1400e8d0a  nop     dword ptr [rax+rax+00h]
0x1400e8d0f  mov     ecx, ebx; unsigned int
0x1400e8d11  call    ?RefsGetCompressionLookasideIndex@@YAKK@Z; RefsGetCompressionLookasideIndex(ulong)
0x1400e8d16  mov     ecx, [rdi+34h]
0x1400e8d19  lea     rdx, ?RefsCompressionBufferLookasideList@@3PAPEAU_NPAGED_LOOKASIDE_LIST@@A; _NPAGED_LOOKASIDE_LIST * near * RefsCompressionBufferLookasideList
0x1400e8d20  mov     r8d, eax
0x1400e8d23  shl     rcx, 7
0x1400e8d27  add     rcx, [rdx+r8*8]; Lookaside
0x1400e8d2b  mov     rdx, [rdi+28h]; Entry
0x1400e8d2f  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400e8d36  nop     dword ptr [rax+rax+00h]
0x1400e8d3b  jmp     short loc_1400E8D46
0x1400e8d3d  mov     r8, [rdi+28h]; void *
0x1400e8d41  call    ?RefsDeleteMdlAndBuffer@@YAXPEAU_VCB@@PEAU_MDL@@PEAX@Z; RefsDeleteMdlAndBuffer(_VCB *,_MDL *,void *)
0x1400e8d46  mov     [rdi+20h], r13
0x1400e8d4a  mov     [rdi+28h], r13
0x1400e8d4e  mov     [rdi+30h], r13d
0x1400e8d52  mov     [rdi+34h], ebp
0x1400e8d55  lea     r9, ?RefsCompressionBufferLookasideList@@3PAPEAU_NPAGED_LOOKASIDE_LIST@@A; _NPAGED_LOOKASIDE_LIST * near * RefsCompressionBufferLookasideList
0x1400e8d5c  mov     ecx, [r15]; unsigned int
0x1400e8d5f  mov     rbx, r13
0x1400e8d62  mov     [rsp+88h+arg_8], rbx
0x1400e8d6a  mov     [r14], ecx
0x1400e8d6d  mov     [rdi], r13
0x1400e8d70  cmp     ecx, 10000h
0x1400e8d76  ja      loc_1400E8E37
0x1400e8d7c  mov     eax, gs:1A4h
0x1400e8d84  xor     edx, edx
0x1400e8d86  div     cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x1400e8d8c  mov     r8d, edx
0x1400e8d8f  mov     [rdi+0Ch], r8d
0x1400e8d93  call    ?RefsGetCompressionLookasideIndex@@YAKK@Z; RefsGetCompressionLookasideIndex(ulong)
0x1400e8d98  mov     ebp, eax
0x1400e8d9a  mov     ecx, r8d
0x1400e8d9d  shl     rcx, 7
0x1400e8da1  add     rcx, [r9+rbp*8]; Lookaside
0x1400e8da5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400e8dac  nop     dword ptr [rax+rax+00h]
0x1400e8db1  mov     [rdi], rax
0x1400e8db4  test    rax, rax
0x1400e8db7  jz      short loc_1400E8E2F
0x1400e8db9  mov     edx, [r14]; Length
0x1400e8dbc  xor     r9d, r9d; ChargeQuota
0x1400e8dbf  xor     r8d, r8d; SecondaryBuffer
0x1400e8dc2  mov     [rsp+88h+Irp], r13; Irp
0x1400e8dc7  mov     rcx, rax; VirtualAddress
0x1400e8dca  call    cs:__imp_IoAllocateMdl
0x1400e8dd1  nop     dword ptr [rax+rax+00h]
0x1400e8dd6  mov     [rsp+88h+arg_8], rax
0x1400e8dde  mov     rbx, rax
0x1400e8de1  test    rax, rax
0x1400e8de4  jz      short loc_1400E8E0B
0x1400e8de6  mov     rcx, rax; MemoryDescriptorList
0x1400e8de9  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400e8df0  nop     dword ptr [rax+rax+00h]
0x1400e8df5  mov     edx, 1
0x1400e8dfa  mov     rcx, rbx
0x1400e8dfd  call    cs:__imp_MmMdlPageContentsState
0x1400e8e04  nop     dword ptr [rax+rax+00h]
0x1400e8e09  jmp     short loc_1400E8E2F
0x1400e8e0b  mov     ecx, [rdi+0Ch]
0x1400e8e0e  lea     rdx, ?RefsCompressionBufferLookasideList@@3PAPEAU_NPAGED_LOOKASIDE_LIST@@A; _NPAGED_LOOKASIDE_LIST * near * RefsCompressionBufferLookasideList
0x1400e8e15  shl     rcx, 7
0x1400e8e19  add     rcx, [rdx+rbp*8]; Lookaside
0x1400e8e1d  mov     rdx, [rdi]; Entry
0x1400e8e20  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400e8e27  nop     dword ptr [rax+rax+00h]
0x1400e8e2c  mov     [rdi], r13
0x1400e8e2f  cmp     [rdi], r13
0x1400e8e32  jnz     short loc_1400E8E6A
0x1400e8e34  or      ebp, 0FFFFFFFFh
0x1400e8e37  lea     rax, [rsp+88h+arg_8]
0x1400e8e3f  mov     [rsp+88h+var_58], rdi; void **
0x1400e8e44  mov     [rsp+88h+var_60], rax; struct _MDL **
0x1400e8e49  mov     r8d, 2; unsigned __int16
0x1400e8e4f  xor     r9d, r9d; unsigned __int8
0x1400e8e52  mov     [rsp+88h+Irp], r14; unsigned int *
0x1400e8e57  mov     rcx, r12; struct _IRP_CONTEXT *
0x1400e8e5a  mov     [rdi+0Ch], ebp
0x1400e8e5d  call    ?RefsCreateMdlAndBuffer@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB@@GEPEAKPEAPEAU_MDL@@PEAPEAX@Z; RefsCreateMdlAndBuffer(_IRP_CONTEXT *,_SCB *,ushort,uchar,ulong *,_MDL * *,void * *)
0x1400e8e62  mov     rbx, [rsp+88h+arg_8]
0x1400e8e6a  mov     rax, [rsi+8]
0x1400e8e6e  mov     [rdi+10h], rax
0x1400e8e72  mov     rax, [rsi+70h]
0x1400e8e76  mov     [rdi+18h], rax
0x1400e8e7a  mov     [rsi+8], rbx
0x1400e8e7e  mov     rax, [rdi]
0x1400e8e81  mov     [rsi+70h], rax
0x1400e8e85  mov     rcx, [rdi+50h]; MemoryDescriptorList
0x1400e8e89  test    rcx, rcx
0x1400e8e8c  jz      short loc_1400E8EB9
0x1400e8e8e  mov     rbx, [rcx]
0x1400e8e91  call    cs:__imp_MmUnlockPages
0x1400e8e98  nop     dword ptr [rax+rax+00h]
0x1400e8e9d  mov     rcx, [rdi+50h]; Mdl
0x1400e8ea1  call    cs:__imp_IoFreeMdl
0x1400e8ea8  nop     dword ptr [rax+rax+00h]
0x1400e8ead  mov     [rdi+50h], rbx
0x1400e8eb1  mov     rcx, rbx
0x1400e8eb4  test    rbx, rbx
0x1400e8eb7  jnz     short loc_1400E8E8E
0x1400e8eb9  mov     eax, [r14]
0x1400e8ebc  mov     [r15], eax
0x1400e8ebf  add     rsp, 48h
0x1400e8ec3  pop     r15
0x1400e8ec5  pop     r14
0x1400e8ec7  pop     r13
0x1400e8ec9  pop     r12
0x1400e8ecb  pop     rdi
0x1400e8ecc  pop     rsi
0x1400e8ecd  pop     rbp
0x1400e8ece  pop     rbx
0x1400e8ecf  retn
```
