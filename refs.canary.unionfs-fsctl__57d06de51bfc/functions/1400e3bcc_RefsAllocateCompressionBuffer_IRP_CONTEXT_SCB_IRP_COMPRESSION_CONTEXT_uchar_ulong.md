# RefsAllocateCompressionBuffer(_IRP_CONTEXT *,_SCB *,_IRP *,COMPRESSION_CONTEXT *,uchar,ulong *)

- ea: `0x1400e3bcc`
- end: `0x1400e3e81`
- name: `?RefsAllocateCompressionBuffer@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB@@PEAU_IRP@@PEAUCOMPRESSION_CONTEXT@@EPEAK@Z`
- size: `693`
- prototype: `void __usercall(struct _IRP_CONTEXT *@<rcx>, struct _SCB *@<rdx>, struct _IRP *@<r8>, struct COMPRESSION_CONTEXT *@<r9>, unsigned __int8, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400b97a0`

## callees

- `0x1400e3bcc`
- `0x1400e6d98`
- `0x1400e95f0`
- `0x1402966c4`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x1400e3d7a`
- `ntoskrnl!IoAllocateMdl` at `0x1400e3d7a`
- `ntoskrnl!IoFreeMdl` at `0x1400e3c4f`
- `ntoskrnl!IoFreeMdl` at `0x1400e3cb3`
- `ntoskrnl!IoFreeMdl` at `0x1400e3e51`
- `ntoskrnl!IoFreeMdl` at `0x1400e3c4f`
- `ntoskrnl!IoFreeMdl` at `0x1400e3cb3`
- `ntoskrnl!IoFreeMdl` at `0x1400e3e51`
- `ntoskrnl!MmUnlockPages` at `0x1400e3e41`
- `ntoskrnl!MmUnlockPages` at `0x1400e3e41`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400e3d99`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400e3d99`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e3c70`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e3cdf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e3dd0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e3c70`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e3cdf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e3dd0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400e3d55`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400e3d55`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400e3dad`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400e3dad`

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
0x1400e3bcc  mov     [rsp+arg_8], rdx
0x1400e3bd1  push    rbx
0x1400e3bd2  push    rbp
0x1400e3bd3  push    rsi
0x1400e3bd4  push    rdi
0x1400e3bd5  push    r12
0x1400e3bd7  push    r13
0x1400e3bd9  push    r14
0x1400e3bdb  push    r15
0x1400e3bdd  sub     rsp, 48h
0x1400e3be1  mov     r15, [rsp+88h+arg_28]
0x1400e3be9  lea     r14, [r9+8]
0x1400e3bed  mov     ebx, [r14]
0x1400e3bf0  xor     r13d, r13d
0x1400e3bf3  mov     rdi, r9
0x1400e3bf6  mov     rsi, r8
0x1400e3bf9  mov     r12, rcx
0x1400e3bfc  cmp     [r15], ebx
0x1400e3bff  jbe     loc_1400E3E35
0x1400e3c05  or      ebp, 0FFFFFFFFh
0x1400e3c08  lea     r9, ?RefsCompressionBufferLookasideList@@3PAPEAU_NPAGED_LOOKASIDE_LIST@@A; _NPAGED_LOOKASIDE_LIST * near * RefsCompressionBufferLookasideList
0x1400e3c0f  cmp     [rdi+10h], r13
0x1400e3c13  jz      loc_1400E3CA2
0x1400e3c19  mov     rax, [r8+8]
0x1400e3c1d  mov     [rax+28h], ebx
0x1400e3c20  mov     r9, [r8+8]
0x1400e3c24  cmp     [rdi+20h], r9
0x1400e3c28  jnz     short loc_1400E3C3D
0x1400e3c2a  mov     [rdi+20h], r13
0x1400e3c2e  mov     [rdi+28h], r13
0x1400e3c32  mov     [rdi+30h], r13d
0x1400e3c36  mov     [rdi+34h], ebp
0x1400e3c39  mov     r9, [r8+8]
0x1400e3c3d  cmp     [rdi+0Ch], ebp
0x1400e3c40  jz      short loc_1400E3C7E
0x1400e3c42  mov     ecx, [r14]; unsigned int
0x1400e3c45  call    ?RefsGetCompressionLookasideIndex@@YAKK@Z; RefsGetCompressionLookasideIndex(ulong)
0x1400e3c4a  mov     rcx, r9; Mdl
0x1400e3c4d  mov     ebx, eax
0x1400e3c4f  call    cs:__imp_IoFreeMdl
0x1400e3c56  nop     dword ptr [rax+rax+00h]
0x1400e3c5b  mov     ecx, [rdi+0Ch]
0x1400e3c5e  lea     rdx, ?RefsCompressionBufferLookasideList@@3PAPEAU_NPAGED_LOOKASIDE_LIST@@A; _NPAGED_LOOKASIDE_LIST * near * RefsCompressionBufferLookasideList
0x1400e3c65  shl     rcx, 7
0x1400e3c69  add     rcx, [rdx+rbx*8]; Lookaside
0x1400e3c6d  mov     rdx, [rdi]; Entry
0x1400e3c70  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400e3c77  nop     dword ptr [rax+rax+00h]
0x1400e3c7c  jmp     short loc_1400E3C89
0x1400e3c7e  mov     r8, [rdi]; void *
0x1400e3c81  mov     rdx, r9; struct _MDL *
0x1400e3c84  call    ?RefsDeleteMdlAndBuffer@@YAXPEAU_VCB@@PEAU_MDL@@PEAX@Z; RefsDeleteMdlAndBuffer(_VCB *,_MDL *,void *)
0x1400e3c89  mov     rax, [rdi+10h]
0x1400e3c8d  mov     [rsi+8], rax
0x1400e3c91  mov     rax, [rdi+18h]
0x1400e3c95  mov     [rsi+70h], rax
0x1400e3c99  mov     [rdi+10h], r13
0x1400e3c9d  mov     [rdi+0Ch], ebp
0x1400e3ca0  jmp     short loc_1400E3D05
0x1400e3ca2  mov     rdx, [rdi+20h]; struct _MDL *
0x1400e3ca6  test    rdx, rdx
0x1400e3ca9  jz      short loc_1400E3D0C
0x1400e3cab  cmp     [rdi+34h], ebp
0x1400e3cae  jz      short loc_1400E3CED
0x1400e3cb0  mov     rcx, rdx; Mdl
0x1400e3cb3  call    cs:__imp_IoFreeMdl
0x1400e3cba  nop     dword ptr [rax+rax+00h]
0x1400e3cbf  mov     ecx, ebx; unsigned int
0x1400e3cc1  call    ?RefsGetCompressionLookasideIndex@@YAKK@Z; RefsGetCompressionLookasideIndex(ulong)
0x1400e3cc6  mov     ecx, [rdi+34h]
0x1400e3cc9  lea     rdx, ?RefsCompressionBufferLookasideList@@3PAPEAU_NPAGED_LOOKASIDE_LIST@@A; _NPAGED_LOOKASIDE_LIST * near * RefsCompressionBufferLookasideList
0x1400e3cd0  mov     r8d, eax
0x1400e3cd3  shl     rcx, 7
0x1400e3cd7  add     rcx, [rdx+r8*8]; Lookaside
0x1400e3cdb  mov     rdx, [rdi+28h]; Entry
0x1400e3cdf  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400e3ce6  nop     dword ptr [rax+rax+00h]
0x1400e3ceb  jmp     short loc_1400E3CF6
0x1400e3ced  mov     r8, [rdi+28h]; void *
0x1400e3cf1  call    ?RefsDeleteMdlAndBuffer@@YAXPEAU_VCB@@PEAU_MDL@@PEAX@Z; RefsDeleteMdlAndBuffer(_VCB *,_MDL *,void *)
0x1400e3cf6  mov     [rdi+20h], r13
0x1400e3cfa  mov     [rdi+28h], r13
0x1400e3cfe  mov     [rdi+30h], r13d
0x1400e3d02  mov     [rdi+34h], ebp
0x1400e3d05  lea     r9, ?RefsCompressionBufferLookasideList@@3PAPEAU_NPAGED_LOOKASIDE_LIST@@A; _NPAGED_LOOKASIDE_LIST * near * RefsCompressionBufferLookasideList
0x1400e3d0c  mov     ecx, [r15]; unsigned int
0x1400e3d0f  mov     rbx, r13
0x1400e3d12  mov     [rsp+88h+arg_8], rbx
0x1400e3d1a  mov     [r14], ecx
0x1400e3d1d  mov     [rdi], r13
0x1400e3d20  cmp     ecx, 10000h
0x1400e3d26  ja      loc_1400E3DE7
0x1400e3d2c  mov     eax, gs:1A4h
0x1400e3d34  xor     edx, edx
0x1400e3d36  div     cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x1400e3d3c  mov     r8d, edx
0x1400e3d3f  mov     [rdi+0Ch], r8d
0x1400e3d43  call    ?RefsGetCompressionLookasideIndex@@YAKK@Z; RefsGetCompressionLookasideIndex(ulong)
0x1400e3d48  mov     ebp, eax
0x1400e3d4a  mov     ecx, r8d
0x1400e3d4d  shl     rcx, 7
0x1400e3d51  add     rcx, [r9+rbp*8]; Lookaside
0x1400e3d55  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400e3d5c  nop     dword ptr [rax+rax+00h]
0x1400e3d61  mov     [rdi], rax
0x1400e3d64  test    rax, rax
0x1400e3d67  jz      short loc_1400E3DDF
0x1400e3d69  mov     edx, [r14]; Length
0x1400e3d6c  xor     r9d, r9d; ChargeQuota
0x1400e3d6f  xor     r8d, r8d; SecondaryBuffer
0x1400e3d72  mov     [rsp+88h+Irp], r13; Irp
0x1400e3d77  mov     rcx, rax; VirtualAddress
0x1400e3d7a  call    cs:__imp_IoAllocateMdl
0x1400e3d81  nop     dword ptr [rax+rax+00h]
0x1400e3d86  mov     [rsp+88h+arg_8], rax
0x1400e3d8e  mov     rbx, rax
0x1400e3d91  test    rax, rax
0x1400e3d94  jz      short loc_1400E3DBB
0x1400e3d96  mov     rcx, rax; MemoryDescriptorList
0x1400e3d99  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400e3da0  nop     dword ptr [rax+rax+00h]
0x1400e3da5  mov     edx, 1
0x1400e3daa  mov     rcx, rbx
0x1400e3dad  call    cs:__imp_MmMdlPageContentsState
0x1400e3db4  nop     dword ptr [rax+rax+00h]
0x1400e3db9  jmp     short loc_1400E3DDF
0x1400e3dbb  mov     ecx, [rdi+0Ch]
0x1400e3dbe  lea     rdx, ?RefsCompressionBufferLookasideList@@3PAPEAU_NPAGED_LOOKASIDE_LIST@@A; _NPAGED_LOOKASIDE_LIST * near * RefsCompressionBufferLookasideList
0x1400e3dc5  shl     rcx, 7
0x1400e3dc9  add     rcx, [rdx+rbp*8]; Lookaside
0x1400e3dcd  mov     rdx, [rdi]; Entry
0x1400e3dd0  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400e3dd7  nop     dword ptr [rax+rax+00h]
0x1400e3ddc  mov     [rdi], r13
0x1400e3ddf  cmp     [rdi], r13
0x1400e3de2  jnz     short loc_1400E3E1A
0x1400e3de4  or      ebp, 0FFFFFFFFh
0x1400e3de7  lea     rax, [rsp+88h+arg_8]
0x1400e3def  mov     [rsp+88h+var_58], rdi; void **
0x1400e3df4  mov     [rsp+88h+var_60], rax; struct _MDL **
0x1400e3df9  mov     r8d, 2; unsigned __int16
0x1400e3dff  xor     r9d, r9d; unsigned __int8
0x1400e3e02  mov     [rsp+88h+Irp], r14; unsigned int *
0x1400e3e07  mov     rcx, r12; struct _IRP_CONTEXT *
0x1400e3e0a  mov     [rdi+0Ch], ebp
0x1400e3e0d  call    ?RefsCreateMdlAndBuffer@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB@@GEPEAKPEAPEAU_MDL@@PEAPEAX@Z; RefsCreateMdlAndBuffer(_IRP_CONTEXT *,_SCB *,ushort,uchar,ulong *,_MDL * *,void * *)
0x1400e3e12  mov     rbx, [rsp+88h+arg_8]
0x1400e3e1a  mov     rax, [rsi+8]
0x1400e3e1e  mov     [rdi+10h], rax
0x1400e3e22  mov     rax, [rsi+70h]
0x1400e3e26  mov     [rdi+18h], rax
0x1400e3e2a  mov     [rsi+8], rbx
0x1400e3e2e  mov     rax, [rdi]
0x1400e3e31  mov     [rsi+70h], rax
0x1400e3e35  mov     rcx, [rdi+50h]; MemoryDescriptorList
0x1400e3e39  test    rcx, rcx
0x1400e3e3c  jz      short loc_1400E3E69
0x1400e3e3e  mov     rbx, [rcx]
0x1400e3e41  call    cs:__imp_MmUnlockPages
0x1400e3e48  nop     dword ptr [rax+rax+00h]
0x1400e3e4d  mov     rcx, [rdi+50h]; Mdl
0x1400e3e51  call    cs:__imp_IoFreeMdl
0x1400e3e58  nop     dword ptr [rax+rax+00h]
0x1400e3e5d  mov     [rdi+50h], rbx
0x1400e3e61  mov     rcx, rbx
0x1400e3e64  test    rbx, rbx
0x1400e3e67  jnz     short loc_1400E3E3E
0x1400e3e69  mov     eax, [r14]
0x1400e3e6c  mov     [r15], eax
0x1400e3e6f  add     rsp, 48h
0x1400e3e73  pop     r15
0x1400e3e75  pop     r14
0x1400e3e77  pop     r13
0x1400e3e79  pop     r12
0x1400e3e7b  pop     rdi
0x1400e3e7c  pop     rsi
0x1400e3e7d  pop     rbp
0x1400e3e7e  pop     rbx
0x1400e3e7f  retn
```
