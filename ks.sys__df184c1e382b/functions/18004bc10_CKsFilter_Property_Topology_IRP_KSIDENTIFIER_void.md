# CKsFilter::Property_Topology(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x18004bc10`
- end: `0x18004bf15`
- name: `?Property_Topology@CKsFilter@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `773`
- prototype: `__int64 __fastcall(PIRP Irp, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000b7bc`
- `0x180019d00`
- `0x18004bc10`
- `0x18004ce70`
- `0x18004d5d0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18004bd61`
- `ntoskrnl!KeReleaseMutex` at `0x18004bd61`
- `ntoskrnl!KeWaitForSingleObject` at `0x18004bc73`
- `ntoskrnl!KeWaitForSingleObject` at `0x18004bc73`

## pseudocode

```c
__int64 __fastcall CKsFilter::Property_Topology(PIRP Irp, struct KSIDENTIFIER *a2, void *a3)
{
  struct KSIDENTIFIER *v4; // rdi
  __int64 v6; // rbp
  ULONG Id; // edx
  __int64 v8; // rcx
  ULONG v9; // edx
  ULONG v10; // edx
  unsigned int Data1; // eax
  __int64 v12; // rax
  __int64 v13; // r9
  _QWORD *v14; // rdx
  NTSTATUS NodeNameValue; // eax
  unsigned int v16; // ebx
  __int64 v17; // r8
  unsigned __int64 v18; // rdi
  ULONG Length; // edx
  const void *v20; // r9
  struct _IRP *v21; // rcx
  ULONG_PTR v22; // rax
  ULONG_PTR v24; // rax
  unsigned int v25; // r8d
  struct _IRP *MasterIrp; // rax
  int v27; // r9d
  __int64 v28; // r11
  PMDL *i; // r10

  v4 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      38,
      (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids);
  }
  v6 = *(_QWORD *)(*(_QWORD *)Irp->Tail.Overlay.CurrentStackLocation->FileObject->FsContext + 112LL);
  KeWaitForSingleObject((PVOID)(v6 + 312), Executive, 0, 0, 0);
  Id = v4->Id;
  v8 = *(_QWORD *)(v6 + 128);
  if ( !Id )
  {
    LODWORD(v17) = *(_DWORD *)(v8 + 48);
    v18 = 16LL * (unsigned int)v17;
    if ( v18 > 0xFFFFFFFF )
    {
LABEL_27:
      v16 = -1073741675;
      goto LABEL_24;
    }
    Length = Irp->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length;
    if ( Length )
    {
      if ( Length != 4 )
      {
        if ( Length < 8 )
          goto LABEL_47;
        v20 = *(const void **)(v8 + 56);
        goto LABEL_18;
      }
LABEL_48:
      *(_DWORD *)Irp->AssociatedIrp.MasterIrp = v18 + 8;
      Irp->IoStatus.Information = 4;
      goto LABEL_23;
    }
    goto LABEL_32;
  }
  v9 = Id - 1;
  if ( !v9 )
  {
    v25 = 16 * *(_DWORD *)(v8 + 64) + 8;
    Length = Irp->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length;
    if ( Length )
    {
      if ( Length < 8 )
        goto LABEL_47;
      MasterIrp = Irp->AssociatedIrp.MasterIrp;
      *(_DWORD *)&MasterIrp->Type = v25;
      v27 = *(_DWORD *)(v8 + 64);
      *(_DWORD *)(&MasterIrp->Size + 1) = v27;
      if ( Length >= v25 )
      {
        v28 = *(_QWORD *)(v8 + 72);
        for ( i = &MasterIrp->MdlAddress; v27; --v27 )
        {
          *(_OWORD *)i = *(_OWORD *)*(_QWORD *)(v28 + 8);
          i += 2;
          v28 += *(unsigned int *)(v8 + 68);
        }
        v22 = v25;
        goto LABEL_22;
      }
      goto LABEL_46;
    }
    v24 = v25;
LABEL_33:
    Irp->IoStatus.Information = v24;
    v16 = -2147483643;
    goto LABEL_24;
  }
  v10 = v9 - 1;
  if ( v10 )
  {
    if ( v10 != 1 )
    {
      v16 = -1073741275;
      goto LABEL_24;
    }
    Data1 = v4[1].Set.Data1;
    if ( Data1 >= *(_DWORD *)(v8 + 64) )
    {
      v16 = -1073741811;
      goto LABEL_24;
    }
    v12 = *(_DWORD *)(v8 + 68) * Data1;
    v13 = *(_QWORD *)(v8 + 72);
    v14 = *(_QWORD **)(v12 + v13 + 16);
    if ( !v14
      || *v14 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
      && v14[1] == *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
    {
      v14 = *(_QWORD **)((unsigned int)v12 + v13 + 8);
    }
    NodeNameValue = ReadNodeNameValue(Irp, v14, a3);
    goto LABEL_12;
  }
  v17 = *(unsigned int *)(v8 + 80);
  if ( (_DWORD)v17 || *(_DWORD *)(v8 + 64) != 1 )
  {
    LODWORD(v18) = 16 * v17;
    if ( (unsigned __int64)(16 * v17) > 0xFFFFFFFF )
      goto LABEL_27;
    Length = Irp->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length;
    if ( Length )
    {
      if ( Length != 4 )
      {
        if ( Length < 8 )
          goto LABEL_47;
        v20 = *(const void **)(v8 + 88);
LABEL_18:
        v21 = Irp->AssociatedIrp.MasterIrp;
        *(_DWORD *)(&v21->Size + 1) = v17;
        *(_DWORD *)&v21->Type = v18 + 8;
        if ( Length >= (int)v18 + 8 )
        {
          if ( (_DWORD)v17 )
            memmove(&v21->MdlAddress, v20, (unsigned int)v18);
          v22 = (unsigned int)v18 + 8LL;
LABEL_22:
          Irp->IoStatus.Information = v22;
LABEL_23:
          v16 = 0;
          goto LABEL_24;
        }
LABEL_46:
        if ( Length == 8 )
        {
          Irp->IoStatus.Information = 8;
          goto LABEL_23;
        }
LABEL_47:
        v16 = -1073741789;
        goto LABEL_24;
      }
      goto LABEL_48;
    }
LABEL_32:
    v24 = (unsigned int)v18 + 8LL;
    goto LABEL_33;
  }
  NodeNameValue = KsHandleSizedListQuery(Irp, *(_DWORD *)(v6 + 556), 0x10u, *(const void **)(v6 + 560));
LABEL_12:
  v16 = NodeNameValue;
LABEL_24:
  KeReleaseMutex((PRKMUTEX)(v6 + 312), 0);
  return v16;
}

```

## disassembly

```asm
0x18004bc10  push    rbx
0x18004bc12  push    rbp
0x18004bc13  push    rsi
0x18004bc14  push    rdi
0x18004bc15  push    r14
0x18004bc17  sub     rsp, 30h
0x18004bc1b  mov     rsi, r8
0x18004bc1e  mov     rdi, rdx
0x18004bc21  mov     rbx, rcx
0x18004bc24  lea     rax, WPP_RECORDER_INITIALIZED
0x18004bc2b  xor     r14d, r14d
0x18004bc2e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004bc35  jz      short loc_18004BC49
0x18004bc37  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bc3e  cmp     [rcx+48h], r14w
0x18004bc43  jnz     loc_18004BED8
0x18004bc49  mov     rax, [rbx+0B8h]
0x18004bc50  xor     r9d, r9d; Alertable
0x18004bc53  xor     r8d, r8d; WaitMode
0x18004bc56  mov     [rsp+58h+Timeout], r14; Timeout
0x18004bc5b  xor     edx, edx; WaitReason
0x18004bc5d  mov     rcx, [rax+30h]
0x18004bc61  mov     rax, [rcx+18h]
0x18004bc65  mov     rcx, [rax]
0x18004bc68  mov     rbp, [rcx+70h]
0x18004bc6c  lea     rcx, [rbp+138h]; Object
0x18004bc73  call    cs:__imp_KeWaitForSingleObject
0x18004bc7a  nop     dword ptr [rax+rax+00h]
0x18004bc7f  mov     edx, [rdi+10h]
0x18004bc82  mov     rcx, [rbp+80h]
0x18004bc89  test    edx, edx
0x18004bc8b  jz      short loc_18004BCE1
0x18004bc8d  sub     edx, 1
0x18004bc90  jz      loc_18004BDDD
0x18004bc96  sub     edx, 1
0x18004bc99  jz      loc_18004BD7B
0x18004bc9f  cmp     edx, 1
0x18004bca2  jnz     loc_18004BEFE
0x18004bca8  mov     eax, [rdi+18h]
0x18004bcab  cmp     eax, [rcx+40h]
0x18004bcae  jnb     loc_18004BECE
0x18004bcb4  imul    eax, [rcx+44h]
0x18004bcb8  mov     r9, [rcx+48h]
0x18004bcbc  mov     r8d, eax
0x18004bcbf  mov     rdx, [rax+r9+10h]
0x18004bcc4  test    rdx, rdx
0x18004bcc7  jnz     loc_18004BE51
0x18004bccd  mov     rdx, [r8+r9+8]
0x18004bcd2  mov     r8, rsi
0x18004bcd5  mov     rcx, rbx
0x18004bcd8  call    ReadNodeNameValue
0x18004bcdd  mov     ebx, eax
0x18004bcdf  jmp     short loc_18004BD58
0x18004bce1  mov     r8d, [rcx+30h]
0x18004bce5  mov     edx, 0FFFFFFFFh
0x18004bcea  mov     edi, r8d
0x18004bced  shl     rdi, 4
0x18004bcf1  cmp     rdi, rdx
0x18004bcf4  ja      loc_18004BD99
0x18004bcfa  mov     rax, [rbx+0B8h]
0x18004bd01  mov     edx, [rax+8]
0x18004bd04  test    edx, edx
0x18004bd06  jz      loc_18004BDC9
0x18004bd0c  cmp     edx, 4
0x18004bd0f  jz      loc_18004BEB8
0x18004bd15  cmp     edx, 8
0x18004bd18  jb      loc_18004BEAE
0x18004bd1e  mov     r9, [rcx+38h]
0x18004bd22  mov     rcx, [rbx+18h]
0x18004bd26  lea     eax, [rdi+8]
0x18004bd29  mov     [rcx+4], r8d
0x18004bd2d  mov     [rcx], eax
0x18004bd2f  cmp     edx, eax
0x18004bd31  jb      loc_18004BEA9
0x18004bd37  test    r8d, r8d
0x18004bd3a  jz      short loc_18004BD4B
0x18004bd3c  mov     r8d, edi; Size
0x18004bd3f  mov     rdx, r9; Src
0x18004bd42  add     rcx, 8; void *
0x18004bd46  call    memmove
0x18004bd4b  mov     eax, edi
0x18004bd4d  add     rax, 8
0x18004bd51  mov     [rbx+38h], rax
0x18004bd55  mov     ebx, r14d
0x18004bd58  lea     rcx, [rbp+138h]; Mutex
0x18004bd5f  xor     edx, edx; Wait
0x18004bd61  call    cs:__imp_KeReleaseMutex
0x18004bd68  nop     dword ptr [rax+rax+00h]
0x18004bd6d  mov     eax, ebx
0x18004bd6f  add     rsp, 30h
0x18004bd73  pop     r14
0x18004bd75  pop     rdi
0x18004bd76  pop     rsi
0x18004bd77  pop     rbp
0x18004bd78  pop     rbx
0x18004bd79  retn
0x18004bd7b  mov     r8d, [rcx+50h]
0x18004bd7f  test    r8d, r8d
0x18004bd82  jz      loc_18004BE77
0x18004bd88  mov     rdi, r8
0x18004bd8b  mov     edx, 0FFFFFFFFh
0x18004bd90  shl     rdi, 4
0x18004bd94  cmp     rdi, rdx
0x18004bd97  jbe     short loc_18004BDA0
0x18004bd99  mov     ebx, 0C0000095h
0x18004bd9e  jmp     short loc_18004BD58
0x18004bda0  mov     rax, [rbx+0B8h]
0x18004bda7  mov     edx, [rax+8]
0x18004bdaa  test    edx, edx
0x18004bdac  jz      short loc_18004BDC9
0x18004bdae  cmp     edx, 4
0x18004bdb1  jz      loc_18004BEB8
0x18004bdb7  cmp     edx, 8
0x18004bdba  jb      loc_18004BEAE
0x18004bdc0  mov     r9, [rcx+58h]
0x18004bdc4  jmp     loc_18004BD22
0x18004bdc9  mov     eax, edi
0x18004bdcb  add     rax, 8
0x18004bdcf  mov     [rbx+38h], rax
0x18004bdd3  mov     ebx, 80000005h
0x18004bdd8  jmp     loc_18004BD58
0x18004bddd  mov     rax, [rbx+0B8h]
0x18004bde4  mov     r8d, [rcx+40h]
0x18004bde8  shl     r8d, 4
0x18004bdec  add     r8d, 8
0x18004bdf0  mov     edx, [rax+8]
0x18004bdf3  test    edx, edx
0x18004bdf5  jz      loc_18004BEA1
0x18004bdfb  cmp     edx, 8
0x18004bdfe  jb      loc_18004BEAE
0x18004be04  mov     rax, [rbx+18h]
0x18004be08  mov     [rax], r8d
0x18004be0b  mov     r9d, [rcx+40h]
0x18004be0f  mov     [rax+4], r9d
0x18004be13  cmp     edx, r8d
0x18004be16  jb      loc_18004BEA9
0x18004be1c  mov     r11, [rcx+48h]
0x18004be20  lea     r10, [rax+8]
0x18004be24  test    r9d, r9d
0x18004be27  jz      short loc_18004BE49
0x18004be29  mov     edx, 0FFFFFFFFh
0x18004be2e  mov     rax, [r11+8]
0x18004be32  movups  xmm0, xmmword ptr [rax]
0x18004be35  movdqu  xmmword ptr [r10], xmm0
0x18004be3a  mov     eax, [rcx+44h]
0x18004be3d  lea     r10, [r10+10h]
0x18004be41  add     r11, rax
0x18004be44  add     r9d, edx
0x18004be47  jnz     short loc_18004BE2E
0x18004be49  mov     eax, r8d
0x18004be4c  jmp     loc_18004BD51
0x18004be51  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004be58  cmp     [rdx], rax
0x18004be5b  jnz     loc_18004BCD2
0x18004be61  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18004be68  cmp     [rdx+8], rax
0x18004be6c  jnz     loc_18004BCD2
0x18004be72  jmp     loc_18004BCCD
0x18004be77  cmp     dword ptr [rcx+40h], 1
0x18004be7b  jnz     loc_18004BD88
0x18004be81  mov     r9, [rbp+230h]; DataItems
0x18004be88  mov     r8d, 10h; DataItemSize
0x18004be8e  mov     edx, [rbp+22Ch]; DataItemsCount
0x18004be94  mov     rcx, rbx; Irp
0x18004be97  call    KsHandleSizedListQuery
0x18004be9c  jmp     loc_18004BCDD
0x18004bea1  mov     eax, r8d
0x18004bea4  jmp     loc_18004BDCF
0x18004bea9  cmp     edx, 8
0x18004beac  jz      short loc_18004BF08
0x18004beae  mov     ebx, 0C0000023h
0x18004beb3  jmp     loc_18004BD58
0x18004beb8  mov     rax, [rbx+18h]
0x18004bebc  lea     ecx, [rdi+8]
0x18004bebf  mov     [rax], ecx
0x18004bec1  mov     qword ptr [rbx+38h], 4
0x18004bec9  jmp     loc_18004BD55
0x18004bece  mov     ebx, 0C000000Dh
0x18004bed3  jmp     loc_18004BD58
0x18004bed8  mov     rcx, [rcx+40h]
0x18004bedc  lea     rax, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x18004bee3  mov     r9d, 26h ; '&'
0x18004bee9  mov     [rsp+58h+Timeout], rax
0x18004beee  mov     dl, 5
0x18004bef0  lea     r8d, [r9-25h]
0x18004bef4  call    WPP_RECORDER_SF_
0x18004bef9  jmp     loc_18004BC49
0x18004befe  mov     ebx, 0C0000225h
0x18004bf03  jmp     loc_18004BD58
0x18004bf08  mov     qword ptr [rbx+38h], 8
0x18004bf10  jmp     loc_18004BD55
```
