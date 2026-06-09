# CKsFilter::Property_Topology(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x18004ba40`
- end: `0x18004bd45`
- name: `?Property_Topology@CKsFilter@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `773`
- prototype: `__int64 __fastcall(PIRP Irp, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000b7bc`
- `0x180019cc0`
- `0x18004ba40`
- `0x18004cca0`
- `0x18004d400`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18004bb91`
- `ntoskrnl!KeReleaseMutex` at `0x18004bb91`
- `ntoskrnl!KeWaitForSingleObject` at `0x18004baa3`
- `ntoskrnl!KeWaitForSingleObject` at `0x18004baa3`

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
  const GUID *v14; // rdx
  unsigned int NodeNameValue; // eax
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
    v14 = *(const GUID **)(v12 + v13 + 16);
    if ( !v14
      || *(_QWORD *)&v14->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
      && *(_QWORD *)v14->Data4 == *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
    {
      v14 = *(const GUID **)((unsigned int)v12 + v13 + 8);
    }
    NodeNameValue = ReadNodeNameValue((__int64)Irp, v14, a3);
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
0x18004ba40  push    rbx
0x18004ba42  push    rbp
0x18004ba43  push    rsi
0x18004ba44  push    rdi
0x18004ba45  push    r14
0x18004ba47  sub     rsp, 30h
0x18004ba4b  mov     rsi, r8
0x18004ba4e  mov     rdi, rdx
0x18004ba51  mov     rbx, rcx
0x18004ba54  lea     rax, WPP_RECORDER_INITIALIZED
0x18004ba5b  xor     r14d, r14d
0x18004ba5e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004ba65  jz      short loc_18004BA79
0x18004ba67  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ba6e  cmp     [rcx+48h], r14w
0x18004ba73  jnz     loc_18004BD08
0x18004ba79  mov     rax, [rbx+0B8h]
0x18004ba80  xor     r9d, r9d; Alertable
0x18004ba83  xor     r8d, r8d; WaitMode
0x18004ba86  mov     [rsp+58h+Timeout], r14; Timeout
0x18004ba8b  xor     edx, edx; WaitReason
0x18004ba8d  mov     rcx, [rax+30h]
0x18004ba91  mov     rax, [rcx+18h]
0x18004ba95  mov     rcx, [rax]
0x18004ba98  mov     rbp, [rcx+70h]
0x18004ba9c  lea     rcx, [rbp+138h]; Object
0x18004baa3  call    cs:__imp_KeWaitForSingleObject
0x18004baaa  nop     dword ptr [rax+rax+00h]
0x18004baaf  mov     edx, [rdi+10h]
0x18004bab2  mov     rcx, [rbp+80h]
0x18004bab9  test    edx, edx
0x18004babb  jz      short loc_18004BB11
0x18004babd  sub     edx, 1
0x18004bac0  jz      loc_18004BC0D
0x18004bac6  sub     edx, 1
0x18004bac9  jz      loc_18004BBAB
0x18004bacf  cmp     edx, 1
0x18004bad2  jnz     loc_18004BD2E
0x18004bad8  mov     eax, [rdi+18h]
0x18004badb  cmp     eax, [rcx+40h]
0x18004bade  jnb     loc_18004BCFE
0x18004bae4  imul    eax, [rcx+44h]
0x18004bae8  mov     r9, [rcx+48h]
0x18004baec  mov     r8d, eax
0x18004baef  mov     rdx, [rax+r9+10h]
0x18004baf4  test    rdx, rdx
0x18004baf7  jnz     loc_18004BC81
0x18004bafd  mov     rdx, [r8+r9+8]
0x18004bb02  mov     r8, rsi
0x18004bb05  mov     rcx, rbx
0x18004bb08  call    ReadNodeNameValue
0x18004bb0d  mov     ebx, eax
0x18004bb0f  jmp     short loc_18004BB88
0x18004bb11  mov     r8d, [rcx+30h]
0x18004bb15  mov     edx, 0FFFFFFFFh
0x18004bb1a  mov     edi, r8d
0x18004bb1d  shl     rdi, 4
0x18004bb21  cmp     rdi, rdx
0x18004bb24  ja      loc_18004BBC9
0x18004bb2a  mov     rax, [rbx+0B8h]
0x18004bb31  mov     edx, [rax+8]
0x18004bb34  test    edx, edx
0x18004bb36  jz      loc_18004BBF9
0x18004bb3c  cmp     edx, 4
0x18004bb3f  jz      loc_18004BCE8
0x18004bb45  cmp     edx, 8
0x18004bb48  jb      loc_18004BCDE
0x18004bb4e  mov     r9, [rcx+38h]
0x18004bb52  mov     rcx, [rbx+18h]
0x18004bb56  lea     eax, [rdi+8]
0x18004bb59  mov     [rcx+4], r8d
0x18004bb5d  mov     [rcx], eax
0x18004bb5f  cmp     edx, eax
0x18004bb61  jb      loc_18004BCD9
0x18004bb67  test    r8d, r8d
0x18004bb6a  jz      short loc_18004BB7B
0x18004bb6c  mov     r8d, edi; Size
0x18004bb6f  mov     rdx, r9; Src
0x18004bb72  add     rcx, 8; void *
0x18004bb76  call    memmove
0x18004bb7b  mov     eax, edi
0x18004bb7d  add     rax, 8
0x18004bb81  mov     [rbx+38h], rax
0x18004bb85  mov     ebx, r14d
0x18004bb88  lea     rcx, [rbp+138h]; Mutex
0x18004bb8f  xor     edx, edx; Wait
0x18004bb91  call    cs:__imp_KeReleaseMutex
0x18004bb98  nop     dword ptr [rax+rax+00h]
0x18004bb9d  mov     eax, ebx
0x18004bb9f  add     rsp, 30h
0x18004bba3  pop     r14
0x18004bba5  pop     rdi
0x18004bba6  pop     rsi
0x18004bba7  pop     rbp
0x18004bba8  pop     rbx
0x18004bba9  retn
0x18004bbab  mov     r8d, [rcx+50h]
0x18004bbaf  test    r8d, r8d
0x18004bbb2  jz      loc_18004BCA7
0x18004bbb8  mov     rdi, r8
0x18004bbbb  mov     edx, 0FFFFFFFFh
0x18004bbc0  shl     rdi, 4
0x18004bbc4  cmp     rdi, rdx
0x18004bbc7  jbe     short loc_18004BBD0
0x18004bbc9  mov     ebx, 0C0000095h
0x18004bbce  jmp     short loc_18004BB88
0x18004bbd0  mov     rax, [rbx+0B8h]
0x18004bbd7  mov     edx, [rax+8]
0x18004bbda  test    edx, edx
0x18004bbdc  jz      short loc_18004BBF9
0x18004bbde  cmp     edx, 4
0x18004bbe1  jz      loc_18004BCE8
0x18004bbe7  cmp     edx, 8
0x18004bbea  jb      loc_18004BCDE
0x18004bbf0  mov     r9, [rcx+58h]
0x18004bbf4  jmp     loc_18004BB52
0x18004bbf9  mov     eax, edi
0x18004bbfb  add     rax, 8
0x18004bbff  mov     [rbx+38h], rax
0x18004bc03  mov     ebx, 80000005h
0x18004bc08  jmp     loc_18004BB88
0x18004bc0d  mov     rax, [rbx+0B8h]
0x18004bc14  mov     r8d, [rcx+40h]
0x18004bc18  shl     r8d, 4
0x18004bc1c  add     r8d, 8
0x18004bc20  mov     edx, [rax+8]
0x18004bc23  test    edx, edx
0x18004bc25  jz      loc_18004BCD1
0x18004bc2b  cmp     edx, 8
0x18004bc2e  jb      loc_18004BCDE
0x18004bc34  mov     rax, [rbx+18h]
0x18004bc38  mov     [rax], r8d
0x18004bc3b  mov     r9d, [rcx+40h]
0x18004bc3f  mov     [rax+4], r9d
0x18004bc43  cmp     edx, r8d
0x18004bc46  jb      loc_18004BCD9
0x18004bc4c  mov     r11, [rcx+48h]
0x18004bc50  lea     r10, [rax+8]
0x18004bc54  test    r9d, r9d
0x18004bc57  jz      short loc_18004BC79
0x18004bc59  mov     edx, 0FFFFFFFFh
0x18004bc5e  mov     rax, [r11+8]
0x18004bc62  movups  xmm0, xmmword ptr [rax]
0x18004bc65  movdqu  xmmword ptr [r10], xmm0
0x18004bc6a  mov     eax, [rcx+44h]
0x18004bc6d  lea     r10, [r10+10h]
0x18004bc71  add     r11, rax
0x18004bc74  add     r9d, edx
0x18004bc77  jnz     short loc_18004BC5E
0x18004bc79  mov     eax, r8d
0x18004bc7c  jmp     loc_18004BB81
0x18004bc81  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004bc88  cmp     [rdx], rax
0x18004bc8b  jnz     loc_18004BB02
0x18004bc91  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18004bc98  cmp     [rdx+8], rax
0x18004bc9c  jnz     loc_18004BB02
0x18004bca2  jmp     loc_18004BAFD
0x18004bca7  cmp     dword ptr [rcx+40h], 1
0x18004bcab  jnz     loc_18004BBB8
0x18004bcb1  mov     r9, [rbp+230h]; DataItems
0x18004bcb8  mov     r8d, 10h; DataItemSize
0x18004bcbe  mov     edx, [rbp+22Ch]; DataItemsCount
0x18004bcc4  mov     rcx, rbx; Irp
0x18004bcc7  call    KsHandleSizedListQuery
0x18004bccc  jmp     loc_18004BB0D
0x18004bcd1  mov     eax, r8d
0x18004bcd4  jmp     loc_18004BBFF
0x18004bcd9  cmp     edx, 8
0x18004bcdc  jz      short loc_18004BD38
0x18004bcde  mov     ebx, 0C0000023h
0x18004bce3  jmp     loc_18004BB88
0x18004bce8  mov     rax, [rbx+18h]
0x18004bcec  lea     ecx, [rdi+8]
0x18004bcef  mov     [rax], ecx
0x18004bcf1  mov     qword ptr [rbx+38h], 4
0x18004bcf9  jmp     loc_18004BB85
0x18004bcfe  mov     ebx, 0C000000Dh
0x18004bd03  jmp     loc_18004BB88
0x18004bd08  mov     rcx, [rcx+40h]
0x18004bd0c  lea     rax, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x18004bd13  mov     r9d, 26h ; '&'
0x18004bd19  mov     [rsp+58h+Timeout], rax
0x18004bd1e  mov     dl, 5
0x18004bd20  lea     r8d, [r9-25h]
0x18004bd24  call    WPP_RECORDER_SF_
0x18004bd29  jmp     loc_18004BA79
0x18004bd2e  mov     ebx, 0C0000225h
0x18004bd33  jmp     loc_18004BB88
0x18004bd38  mov     qword ptr [rbx+38h], 8
0x18004bd40  jmp     loc_18004BB85
```
