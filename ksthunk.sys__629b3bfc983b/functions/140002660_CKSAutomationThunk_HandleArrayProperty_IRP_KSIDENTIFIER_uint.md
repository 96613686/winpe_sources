# CKSAutomationThunk::HandleArrayProperty(_IRP *,KSIDENTIFIER *,uint *)

- ea: `0x140002660`
- end: `0x14000291a`
- name: `?HandleArrayProperty@CKSAutomationThunk@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAI@Z`
- size: `698`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140002660`
- `0x140003ac0`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400026f2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140002815`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400026f2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140002815`
- `ntoskrnl!ExFreePool` at `0x1400028fa`
- `ntoskrnl!ExFreePool` at `0x1400028fa`
- `ks!KsSynchronousIoControlDevice` at `0x140002780`
- `ks!KsSynchronousIoControlDevice` at `0x1400027d3`
- `ks!KsSynchronousIoControlDevice` at `0x14000287d`
- `ks!KsSynchronousIoControlDevice` at `0x140002780`
- `ks!KsSynchronousIoControlDevice` at `0x1400027d3`
- `ks!KsSynchronousIoControlDevice` at `0x14000287d`

## pseudocode

```c
__int64 __fastcall CKSAutomationThunk::HandleArrayProperty(struct _IRP *a1, struct KSIDENTIFIER *a2, unsigned int *a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  unsigned int *v4; // r14
  __int64 v8; // rcx
  unsigned int Length; // eax
  ULONG OutSize; // esi
  _QWORD *v11; // rax
  _QWORD *OutBuffer; // rbx
  _QWORD *v13; // rcx
  unsigned int v14; // edx
  unsigned int *j; // rdi
  NTSTATUS v16; // ebx
  ULONG v17; // ebx
  unsigned int *PoolWithTag; // rax
  unsigned int *v19; // rsi
  unsigned int v20; // eax
  unsigned int v21; // ecx
  unsigned __int64 v22; // rdx
  unsigned int *v23; // rsi
  unsigned int i; // ecx
  ULONG BytesReturned; // [rsp+90h] [rbp+8h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v4 = a3 + 1;
  BytesReturned = 0;
  if ( (a2->Flags & 2) == 0 )
  {
    v16 = KsSynchronousIoControlDevice(
            CurrentStackLocation->FileObject,
            0,
            0x2F0003u,
            a2,
            CurrentStackLocation->Parameters.Create.Options,
            0,
            0,
            &BytesReturned);
    if ( v16 < 0 )
      return (unsigned int)v16;
    if ( !CurrentStackLocation->Parameters.Read.Length )
    {
      a1->IoStatus.Information = (unsigned __int64)BytesReturned >> 1;
      return (unsigned int)v16;
    }
    v17 = BytesReturned;
    PoolWithTag = (unsigned int *)ExAllocatePoolWithTag((POOL_TYPE)1536, BytesReturned, 0x6268534Bu);
    v19 = PoolWithTag;
    if ( ExPoolZeroingNativelySupported )
    {
      if ( !PoolWithTag )
        return (unsigned int)-1073741670;
    }
    else
    {
      if ( !PoolWithTag )
        return (unsigned int)-1073741670;
      memset(PoolWithTag, 0, v17);
    }
    j = v19;
    v16 = KsSynchronousIoControlDevice(
            CurrentStackLocation->FileObject,
            0,
            0x2F0003u,
            a2,
            CurrentStackLocation->Parameters.Create.Options,
            v19,
            BytesReturned,
            &BytesReturned);
    if ( v16 < 0 )
    {
LABEL_33:
      ExFreePool(j);
      return (unsigned int)v16;
    }
    v20 = *v19;
    v21 = *v19 + 1;
    if ( v21 < *v19
      || (v22 = 4LL * v21, v22 > 0xFFFFFFFF)
      || CurrentStackLocation->Parameters.Read.Length < (unsigned int)v22 )
    {
      v16 = -1073741811;
    }
    else
    {
      v23 = v19 + 2;
      *a3 = v20;
      for ( i = 0; i < *a3; ++v4 )
      {
        ++i;
        *v4 = *v23;
        v23 += 2;
        v20 = *a3;
      }
      a1->IoStatus.Information = 4LL * (v20 + 1);
    }
    goto LABEL_32;
  }
  v8 = *a3 + 1;
  if ( (unsigned int)v8 < *a3
    || (unsigned __int64)(4 * v8) > 0xFFFFFFFF
    || 8 * (unsigned __int64)(unsigned int)v8 > 0xFFFFFFFF )
  {
    return (unsigned int)-1073741675;
  }
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( Length < 4 || Length < 4 * (int)v8 )
    return (unsigned int)-1073741811;
  OutSize = 8 * v8;
  v11 = ExAllocatePoolWithTag((POOL_TYPE)1536, (unsigned int)(8 * v8), 0x6268534Bu);
  OutBuffer = v11;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( v11 )
      goto LABEL_11;
    return (unsigned int)-1073741670;
  }
  if ( !v11 )
    return (unsigned int)-1073741670;
  memset(v11, 0, OutSize);
LABEL_11:
  v13 = OutBuffer + 1;
  v14 = 0;
  *OutBuffer = *a3;
  for ( j = (unsigned int *)OutBuffer; v14 < *a3; ++v13 )
  {
    ++v14;
    *v13 = *v4++;
  }
  v16 = KsSynchronousIoControlDevice(
          CurrentStackLocation->FileObject,
          0,
          0x2F0003u,
          a2,
          CurrentStackLocation->Parameters.Create.Options,
          OutBuffer,
          OutSize,
          &BytesReturned);
LABEL_32:
  if ( j )
    goto LABEL_33;
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140002660  mov     rax, rsp
0x140002663  push    rbx
0x140002664  push    rbp
0x140002665  push    rsi
0x140002666  push    rdi
0x140002667  push    r12
0x140002669  push    r13
0x14000266b  push    r14
0x14000266d  push    r15
0x14000266f  sub     rsp, 48h
0x140002673  mov     rbp, [rcx+0B8h]
0x14000267a  lea     r14, [r8+4]
0x14000267e  xor     edi, edi
0x140002680  mov     r12, rdx
0x140002683  mov     [rax+8], edi
0x140002686  mov     r13, rcx
0x140002689  mov     eax, [rdx+14h]
0x14000268c  mov     r15, r8
0x14000268f  test    al, 2
0x140002691  jz      loc_1400027A7
0x140002697  mov     eax, [r8]
0x14000269a  lea     ecx, [rax+1]
0x14000269d  cmp     ecx, eax
0x14000269f  jb      loc_14000279D
0x1400026a5  lea     rdx, ds:0[rcx*4]
0x1400026ad  mov     eax, ecx
0x1400026af  mov     ecx, 0FFFFFFFFh
0x1400026b4  cmp     rdx, rcx
0x1400026b7  ja      loc_14000279D
0x1400026bd  lea     r8, ds:0[rax*8]
0x1400026c5  cmp     r8, rcx
0x1400026c8  ja      loc_14000279D
0x1400026ce  mov     eax, [rbp+8]
0x1400026d1  cmp     eax, 4
0x1400026d4  jb      loc_140002793
0x1400026da  cmp     eax, edx
0x1400026dc  jb      loc_140002793
0x1400026e2  mov     esi, r8d
0x1400026e5  mov     ecx, 600h; PoolType
0x1400026ea  mov     edx, esi; NumberOfBytes
0x1400026ec  mov     r8d, 6268534Bh; Tag
0x1400026f2  call    cs:__imp_ExAllocatePoolWithTag
0x1400026f9  nop     dword ptr [rax+rax+00h]
0x1400026fe  cmp     cs:ExPoolZeroingNativelySupported, dil
0x140002705  mov     rbx, rax
0x140002708  jnz     short loc_140002722
0x14000270a  test    rax, rax
0x14000270d  jz      loc_1400028E6
0x140002713  mov     r8d, esi; Size
0x140002716  xor     edx, edx; Val
0x140002718  mov     rcx, rax; void *
0x14000271b  call    memset
0x140002720  jmp     short loc_14000272B
0x140002722  test    rbx, rbx
0x140002725  jz      loc_1400028E6
0x14000272b  mov     eax, [r15]
0x14000272e  lea     rcx, [rbx+8]
0x140002732  xor     edx, edx
0x140002734  mov     [rbx], rax
0x140002737  mov     rdi, rbx
0x14000273a  cmp     [r15], edx
0x14000273d  jbe     short loc_140002754
0x14000273f  mov     eax, [r14]
0x140002742  inc     edx
0x140002744  mov     [rcx], rax
0x140002747  lea     r14, [r14+4]
0x14000274b  lea     rcx, [rcx+8]
0x14000274f  cmp     edx, [r15]
0x140002752  jb      short loc_14000273F
0x140002754  mov     rcx, [rbp+30h]; FileObject
0x140002758  lea     rax, [rsp+88h+arg_0]
0x140002760  mov     [rsp+88h+BytesReturned], rax; BytesReturned
0x140002765  mov     r9, r12; InBuffer
0x140002768  mov     eax, [rbp+10h]
0x14000276b  xor     edx, edx; RequestorMode
0x14000276d  mov     [rsp+88h+OutSize], esi; OutSize
0x140002771  mov     r8d, 2F0003h; IoControl
0x140002777  mov     [rsp+88h+OutBuffer], rbx; OutBuffer
0x14000277c  mov     [rsp+88h+InSize], eax; InSize
0x140002780  call    cs:__imp_KsSynchronousIoControlDevice
0x140002787  nop     dword ptr [rax+rax+00h]
0x14000278c  mov     ebx, eax
0x14000278e  jmp     loc_1400028F2
0x140002793  mov     ebx, 0C000000Dh
0x140002798  jmp     loc_140002906
0x14000279d  mov     ebx, 0C0000095h
0x1400027a2  jmp     loc_140002906
0x1400027a7  mov     rcx, [rbp+30h]; FileObject
0x1400027ab  lea     rax, [rsp+88h+arg_0]
0x1400027b3  mov     [rsp+88h+BytesReturned], rax; BytesReturned
0x1400027b8  mov     r9, r12; InBuffer
0x1400027bb  mov     eax, [rbp+10h]
0x1400027be  xor     edx, edx; RequestorMode
0x1400027c0  mov     [rsp+88h+OutSize], edi; OutSize
0x1400027c4  mov     r8d, 2F0003h; IoControl
0x1400027ca  mov     [rsp+88h+OutBuffer], rdi; OutBuffer
0x1400027cf  mov     [rsp+88h+InSize], eax; InSize
0x1400027d3  call    cs:__imp_KsSynchronousIoControlDevice
0x1400027da  nop     dword ptr [rax+rax+00h]
0x1400027df  mov     ebx, eax
0x1400027e1  test    eax, eax
0x1400027e3  js      loc_140002906
0x1400027e9  cmp     [rbp+8], edi
0x1400027ec  jnz     short loc_140002801
0x1400027ee  mov     eax, [rsp+88h+arg_0]
0x1400027f5  shr     rax, 1
0x1400027f8  mov     [r13+38h], rax
0x1400027fc  jmp     loc_140002906
0x140002801  mov     ebx, [rsp+88h+arg_0]
0x140002808  mov     r8d, 6268534Bh; Tag
0x14000280e  mov     edx, ebx; NumberOfBytes
0x140002810  mov     ecx, 600h; PoolType
0x140002815  call    cs:__imp_ExAllocatePoolWithTag
0x14000281c  nop     dword ptr [rax+rax+00h]
0x140002821  cmp     cs:ExPoolZeroingNativelySupported, dil
0x140002828  mov     rsi, rax
0x14000282b  jnz     loc_1400028DD
0x140002831  test    rax, rax
0x140002834  jz      loc_1400028E6
0x14000283a  mov     r8d, ebx; Size
0x14000283d  xor     edx, edx; Val
0x14000283f  mov     rcx, rax; void *
0x140002842  call    memset
0x140002847  mov     rcx, [rbp+30h]; FileObject
0x14000284b  lea     rax, [rsp+88h+arg_0]
0x140002853  mov     [rsp+88h+BytesReturned], rax; BytesReturned
0x140002858  mov     r9, r12; InBuffer
0x14000285b  mov     eax, [rsp+88h+arg_0]
0x140002862  xor     edx, edx; RequestorMode
0x140002864  mov     [rsp+88h+OutSize], eax; OutSize
0x140002868  mov     r8d, 2F0003h; IoControl
0x14000286e  mov     eax, [rbp+10h]
0x140002871  mov     rdi, rsi
0x140002874  mov     [rsp+88h+OutBuffer], rsi; OutBuffer
0x140002879  mov     [rsp+88h+InSize], eax; InSize
0x14000287d  call    cs:__imp_KsSynchronousIoControlDevice
0x140002884  nop     dword ptr [rax+rax+00h]
0x140002889  mov     ebx, eax
0x14000288b  test    eax, eax
0x14000288d  js      short loc_1400028F7
0x14000288f  mov     eax, [rsi]
0x140002891  lea     ecx, [rax+1]
0x140002894  cmp     ecx, eax
0x140002896  jb      short loc_1400028ED
0x140002898  mov     edx, ecx
0x14000289a  mov     ecx, 0FFFFFFFFh
0x14000289f  shl     rdx, 2
0x1400028a3  cmp     rdx, rcx
0x1400028a6  ja      short loc_1400028ED
0x1400028a8  cmp     [rbp+8], edx
0x1400028ab  jb      short loc_1400028ED
0x1400028ad  add     rsi, 8
0x1400028b1  mov     [r15], eax
0x1400028b4  xor     ecx, ecx
0x1400028b6  test    eax, eax
0x1400028b8  jz      short loc_1400028D0
0x1400028ba  mov     eax, [rsi]
0x1400028bc  inc     ecx
0x1400028be  mov     [r14], eax
0x1400028c1  lea     rsi, [rsi+8]
0x1400028c5  mov     eax, [r15]
0x1400028c8  lea     r14, [r14+4]
0x1400028cc  cmp     ecx, eax
0x1400028ce  jb      short loc_1400028BA
0x1400028d0  lea     ecx, [rax+1]
0x1400028d3  shl     rcx, 2
0x1400028d7  mov     [r13+38h], rcx
0x1400028db  jmp     short loc_1400028F2
0x1400028dd  test    rsi, rsi
0x1400028e0  jnz     loc_140002847
0x1400028e6  mov     ebx, 0C000009Ah
0x1400028eb  jmp     short loc_140002906
0x1400028ed  mov     ebx, 0C000000Dh
0x1400028f2  test    rdi, rdi
0x1400028f5  jz      short loc_140002906
0x1400028f7  mov     rcx, rdi; P
0x1400028fa  call    cs:__imp_ExFreePool
0x140002901  nop     dword ptr [rax+rax+00h]
0x140002906  mov     eax, ebx
0x140002908  add     rsp, 48h
0x14000290c  pop     r15
0x14000290e  pop     r14
0x140002910  pop     r13
0x140002912  pop     r12
0x140002914  pop     rdi
0x140002915  pop     rsi
0x140002916  pop     rbp
0x140002917  pop     rbx
0x140002918  retn
```
