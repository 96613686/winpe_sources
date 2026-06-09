# PmQueryDepends(_DEVICE_EXTENSION *,_LIST_ENTRY *)

- ea: `0x140005454`
- end: `0x14000589d`
- name: `?PmQueryDepends@@YAXPEAU_DEVICE_EXTENSION@@PEAU_LIST_ENTRY@@@Z`
- size: `1097`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400087c0`

## callees

- `0x140005454`
- `0x14000c14c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005729`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005804`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005858`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005878`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005729`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005804`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005858`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005878`
- `ntoskrnl!ObfDereferenceObject` at `0x140005710`
- `ntoskrnl!ObfDereferenceObject` at `0x14000583f`
- `ntoskrnl!ObfDereferenceObject` at `0x140005710`
- `ntoskrnl!ObfDereferenceObject` at `0x14000583f`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140005565`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140005565`
- `ntoskrnl!ObfReferenceObject` at `0x14000579f`
- `ntoskrnl!ObfReferenceObject` at `0x14000579f`
- `ntoskrnl!ExAllocatePool2` at `0x1400054ba`
- `ntoskrnl!ExAllocatePool2` at `0x1400056e4`
- `ntoskrnl!ExAllocatePool2` at `0x1400054ba`
- `ntoskrnl!ExAllocatePool2` at `0x1400056e4`
- `ntoskrnl!IoReuseIrp` at `0x14000550e`
- `ntoskrnl!IoReuseIrp` at `0x14000550e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000560f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000560f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400055a5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400055a5`

## pseudocode

```c
void __fastcall PmQueryDepends(struct _DEVICE_EXTENSION *a1, struct _LIST_ENTRY *a2)
{
  int v2; // r14d
  int v3; // r8d
  struct _LIST_ENTRY *v4; // rdi
  struct _DEVICE_EXTENSION *v5; // r13
  int v6; // ecx
  unsigned int *Pool2; // rsi
  int Status; // r12d
  struct _LIST_ENTRY *Flink; // r14
  __int64 v10; // r15
  IRP *v11; // rcx
  __int64 v12; // rax
  IRP *v13; // rbx
  struct _DEVICE_OBJECT *Blink; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _LIST_ENTRY *v16; // rcx
  KIRQL v17; // al
  _QWORD *v18; // rdx
  KIRQL v19; // r8
  __int64 v20; // rcx
  _QWORD *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // r8
  _QWORD *v24; // rdi
  __int64 v25; // rax
  _QWORD *v26; // r15
  int v27; // eax
  _DWORD *v28; // rbx
  _DWORD *v29; // rax
  _DWORD *v30; // r14
  __int64 i; // r14
  __int64 v32; // r13
  unsigned int v33; // edi
  unsigned int v34; // ebx
  _DWORD *v35; // r15
  __int64 v36; // rax
  __int64 j; // rcx
  __int64 v38; // rdx
  __int64 k; // rdi
  _DWORD *v40; // rbx
  __int64 m; // r14
  _DWORD *v42; // [rsp+30h] [rbp-48h]
  _QWORD *v43; // [rsp+38h] [rbp-40h]
  __int128 v44; // [rsp+40h] [rbp-38h] BYREF
  struct _LIST_ENTRY *v45; // [rsp+50h] [rbp-28h] BYREF
  __int128 v46; // [rsp+58h] [rbp-20h]
  int v48; // [rsp+C8h] [rbp+50h]
  int v49; // [rsp+D0h] [rbp+58h]
  __int64 v50; // [rsp+D8h] [rbp+60h]

  v2 = 0;
  v48 = 0;
  v44 = 0;
  v45 = 0;
  v3 = 0;
  v46 = 0;
  v4 = a2;
  v5 = a1;
  while ( 1 )
  {
    a2 = a2->Flink;
    if ( a2 == v4 )
      break;
    v6 = v3 + 1;
    if ( !a2[-1].Blink )
      v6 = v3;
    v3 = v6;
  }
  Pool2 = (unsigned int *)ExAllocatePool2(256, (unsigned int)(8 * v3 + 8), 1381133648);
  if ( Pool2 )
  {
    Flink = v4->Flink;
    Status = 0;
    v10 = 0;
    while ( Flink != v4 )
    {
      if ( Flink[-1].Blink )
      {
        v11 = (IRP *)*((_QWORD *)v5 + 107);
        v45 = Flink[-7].Flink;
        *(_QWORD *)&v46 = *((_QWORD *)v5 + 3);
        IoReuseIrp(v11, -1073741637);
        v12 = *((_QWORD *)v5 + 107);
        --*(_BYTE *)(v12 + 67);
        *(_QWORD *)(v12 + 184) -= 72LL;
        v13 = (IRP *)*((_QWORD *)v5 + 107);
        Blink = (struct _DEVICE_OBJECT *)Flink[-1].Blink[2].Blink;
        CurrentStackLocation = v13->Tail.Overlay.CurrentStackLocation;
        CurrentStackLocation->MajorFunction = 15;
        v13->AssociatedIrp.MasterIrp = (struct _IRP *)&v45;
        CurrentStackLocation->Parameters.Read.Length = 8;
        CurrentStackLocation->Parameters.Create.Options = 24;
        CurrentStackLocation->Parameters.Read.ByteOffset.LowPart = 7733260;
        IoForwardIrpSynchronously(Blink, v13);
        Status = v13->IoStatus.Status;
        if ( Status < 0 )
          break;
        v16 = v45;
        *(_QWORD *)&Pool2[2 * v10 + 2] = v45;
        v48 += LODWORD(v16->Flink);
        v10 = (unsigned int)(v10 + 1);
      }
      Flink = Flink->Flink;
    }
    v2 = v48;
    *Pool2 = v10;
  }
  else
  {
    Status = -1073741670;
  }
  v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v5 + 14);
  v18 = (_QWORD *)((char *)v5 + 672);
  v19 = v17;
  v20 = *((_QWORD *)v5 + 84);
  if ( *(struct _DEVICE_EXTENSION **)(v20 + 8) != (struct _DEVICE_EXTENSION *)((char *)v5 + 672)
    || (*((_QWORD *)&v44 + 1) = (char *)v5 + 672,
        *(_QWORD *)&v44 = v20,
        *(_QWORD *)(v20 + 8) = &v44,
        *v18 = &v44,
        *((_QWORD **)&v44 + 1) != v18)
    || (v21 = (_QWORD *)*((_QWORD *)v5 + 85), (_QWORD *)*v21 != v18) )
  {
LABEL_64:
    __fastfail(3u);
  }
  *v21 = &v44;
  *((_QWORD *)v5 + 85) = (char *)v5 + 672;
  *v18 = v18;
  *((_QWORD *)&v44 + 1) = v21;
  KeReleaseSpinLock((PKSPIN_LOCK)v5 + 14, v19);
  if ( (__int128 *)v44 == &v44 && (Microsoft_Windows_PartitionEnableBits & 4) != 0 )
    McTemplateK0qp_EtwWriteTransfer(v22, QueryDepends, v23, *((unsigned int *)v5 + 42), 0);
  while ( 1 )
  {
    v24 = (_QWORD *)v44;
    v43 = (_QWORD *)v44;
    if ( (__int128 *)v44 == &v44 )
      break;
    if ( *(__int128 **)(v44 + 8) != &v44 )
      goto LABEL_64;
    v25 = *(_QWORD *)v44;
    if ( *(_QWORD *)(*(_QWORD *)v44 + 8LL) != (_QWORD)v44 )
      goto LABEL_64;
    *(_QWORD *)&v44 = *(_QWORD *)v44;
    *(_QWORD *)(v25 + 8) = &v44;
    v26 = v24 - 21;
    if ( (Microsoft_Windows_PartitionEnableBits & 4) != 0 )
      McTemplateK0qp_EtwWriteTransfer(&v44, QueryDepends, v23, *((unsigned int *)v5 + 42), v24 - 21);
    v24[1] = v24;
    v27 = v2;
    *v24 = v24;
    v28 = (_DWORD *)v26[7];
    v42 = v28;
    if ( v28 )
      v27 = v2 + *v28;
    if ( Status < 0 )
      goto LABEL_31;
    v29 = (_DWORD *)ExAllocatePool2(258, 8 * v27 + 8, 1381133648);
    v30 = v29;
    if ( !v29 )
    {
      Status = -1073741670;
LABEL_31:
      if ( v28 )
      {
        for ( i = 0; (unsigned int)i < *v28; i = (unsigned int)(i + 1) )
          ObfDereferenceObject(*(PVOID *)&v28[2 * i + 2]);
        ExFreePoolWithTag(v28, 0);
      }
      v26[7] = 0;
      goto LABEL_36;
    }
    v32 = 0;
    *v29 = 0;
    if ( *Pool2 )
    {
      v33 = 0;
      v34 = *Pool2;
      do
      {
        v35 = *(_DWORD **)&Pool2[2 * v33 + 2];
        if ( v35 && *v35 )
        {
          v36 = 0;
          v49 = 0;
          do
          {
            v32 = 0;
            v50 = v36;
            while ( (unsigned int)v32 < *v30 )
            {
              if ( *(_QWORD *)&v30[2 * v32 + 2] == *(_QWORD *)&v35[2 * v36 + 2] )
                goto LABEL_47;
              v36 = v50;
              v32 = (unsigned int)(v32 + 1);
            }
            ObfReferenceObject(*(PVOID *)&v35[2 * v36 + 2]);
            *(_QWORD *)&v30[2 * v32 + 2] = *(_QWORD *)&v35[2 * v50 + 2];
            ++*v30;
LABEL_47:
            v36 = (unsigned int)(v49 + 1);
            v49 = v36;
          }
          while ( (unsigned int)v36 < *v35 );
        }
        ++v33;
      }
      while ( v33 < v34 );
      v24 = v43;
      v28 = v42;
      v26 = v43 - 21;
    }
    if ( v28 )
    {
      for ( j = 0; (unsigned int)j < *v28; ++*v30 )
      {
        v38 = *(_QWORD *)&v28[2 * j + 2];
        j = (unsigned int)(j + 1);
        *(_QWORD *)&v30[2 * v32 + 2] = v38;
        v32 = (unsigned int)(v32 + 1);
      }
      ExFreePoolWithTag(v28, 0);
    }
    v5 = a1;
    v26[7] = v30;
LABEL_36:
    v2 = v48;
    *((_DWORD *)v24 - 30) = Status;
  }
  if ( Pool2 )
  {
    for ( k = 0; (unsigned int)k < *Pool2; k = (unsigned int)(k + 1) )
    {
      v40 = *(_DWORD **)&Pool2[2 * k + 2];
      if ( v40 )
      {
        for ( m = 0; (unsigned int)m < *v40; m = (unsigned int)(m + 1) )
          ObfDereferenceObject(*(PVOID *)&v40[2 * m + 2]);
        ExFreePoolWithTag(v40, 0);
        *(_QWORD *)&Pool2[2 * k + 2] = 0;
      }
    }
    ExFreePoolWithTag(Pool2, 0);
  }
}

```

## disassembly

```asm
0x140005454  mov     [rsp-40h+arg_0], rcx
0x140005459  push    rbp
0x14000545a  push    rbx
0x14000545b  push    rsi
0x14000545c  push    rdi
0x14000545d  push    r12
0x14000545f  push    r13
0x140005461  push    r14
0x140005463  push    r15
0x140005465  mov     rbp, rsp
0x140005468  sub     rsp, 78h
0x14000546c  xor     r14d, r14d
0x14000546f  xorps   xmm0, xmm0
0x140005472  xorps   xmm1, xmm1
0x140005475  mov     [rbp+arg_8], r14d
0x140005479  movups  [rbp+var_38], xmm0
0x14000547d  mov     [rbp+var_28], r14
0x140005481  xor     r8d, r8d
0x140005484  movups  [rbp+var_20], xmm1
0x140005488  mov     rdi, rdx
0x14000548b  mov     r13, rcx
0x14000548e  jmp     short loc_14000549F
0x140005490  cmp     [rdx-8], r14
0x140005494  lea     ecx, [r8+1]
0x140005498  cmovz   ecx, r8d
0x14000549c  mov     r8d, ecx
0x14000549f  mov     rdx, [rdx]
0x1400054a2  cmp     rdx, rdi
0x1400054a5  jnz     short loc_140005490
0x1400054a7  lea     edx, ds:8[r8*8]
0x1400054af  mov     ecx, 100h
0x1400054b4  mov     r8d, 52526D50h
0x1400054ba  call    cs:__imp_ExAllocatePool2
0x1400054c1  nop     dword ptr [rax+rax+00h]
0x1400054c6  mov     rsi, rax
0x1400054c9  test    rax, rax
0x1400054cc  jnz     short loc_1400054D9
0x1400054ce  mov     r12d, 0C000009Ah
0x1400054d4  jmp     loc_1400055A1
0x1400054d9  mov     r14, [rdi]
0x1400054dc  xor     r12d, r12d
0x1400054df  xor     r15d, r15d
0x1400054e2  jmp     loc_140005591
0x1400054e7  cmp     qword ptr [r14-8], 0
0x1400054ec  jz      loc_14000558E
0x1400054f2  mov     rax, [r14-70h]
0x1400054f6  mov     edx, 0C00000BBh; Iostatus
0x1400054fb  mov     rcx, [r13+358h]; Irp
0x140005502  mov     [rbp+var_28], rax
0x140005506  mov     rax, [r13+18h]
0x14000550a  mov     qword ptr [rbp+var_20], rax
0x14000550e  call    cs:__imp_IoReuseIrp
0x140005515  nop     dword ptr [rax+rax+00h]
0x14000551a  mov     rax, [r13+358h]
0x140005521  lea     rdx, [rbp+var_28]
0x140005525  dec     byte ptr [rax+43h]
0x140005528  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x140005530  mov     rax, [r14-8]
0x140005534  mov     rbx, [r13+358h]
0x14000553b  mov     rcx, [rax+28h]; DeviceObject
0x14000553f  mov     rax, [rbx+0B8h]
0x140005546  mov     byte ptr [rax], 0Fh
0x140005549  mov     [rbx+18h], rdx
0x14000554d  mov     rdx, rbx; Irp
0x140005550  mov     dword ptr [rax+8], 8
0x140005557  mov     dword ptr [rax+10h], 18h
0x14000555e  mov     dword ptr [rax+18h], 76000Ch
0x140005565  call    cs:__imp_IoForwardIrpSynchronously
0x14000556c  nop     dword ptr [rax+rax+00h]
0x140005571  mov     r12d, [rbx+30h]
0x140005575  test    r12d, r12d
0x140005578  js      short loc_14000559A
0x14000557a  mov     rcx, [rbp+var_28]
0x14000557e  mov     eax, [rbp+arg_8]
0x140005581  mov     [rsi+r15*8+8], rcx
0x140005586  add     eax, [rcx]
0x140005588  mov     [rbp+arg_8], eax
0x14000558b  inc     r15d
0x14000558e  mov     r14, [r14]
0x140005591  cmp     r14, rdi
0x140005594  jnz     loc_1400054E7
0x14000559a  mov     r14d, [rbp+arg_8]
0x14000559e  mov     [rsi], r15d
0x1400055a1  lea     rcx, [r13+70h]; SpinLock
0x1400055a5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400055ac  nop     dword ptr [rax+rax+00h]
0x1400055b1  lea     rdx, [r13+2A0h]
0x1400055b8  mov     r8b, al
0x1400055bb  mov     rcx, [rdx]
0x1400055be  cmp     [rcx+8], rdx
0x1400055c2  jnz     loc_140005896
0x1400055c8  lea     rax, [rbp+var_38]
0x1400055cc  mov     qword ptr [rbp+var_38+8], rdx
0x1400055d0  mov     qword ptr [rbp+var_38], rcx
0x1400055d4  mov     [rcx+8], rax
0x1400055d8  lea     rax, [rbp+var_38]
0x1400055dc  mov     [rdx], rax
0x1400055df  cmp     qword ptr [rbp+var_38+8], rdx
0x1400055e3  jnz     loc_140005896
0x1400055e9  mov     rax, [rdx+8]
0x1400055ed  cmp     [rax], rdx
0x1400055f0  jnz     loc_140005896
0x1400055f6  lea     rcx, [rbp+var_38]
0x1400055fa  mov     [rax], rcx
0x1400055fd  lea     rcx, [r13+70h]; SpinLock
0x140005601  mov     [rdx+8], rdx
0x140005605  mov     [rdx], rdx
0x140005608  mov     dl, r8b; NewIrql
0x14000560b  mov     qword ptr [rbp+var_38+8], rax
0x14000560f  call    cs:__imp_KeReleaseSpinLock
0x140005616  nop     dword ptr [rax+rax+00h]
0x14000561b  lea     rax, [rbp+var_38]
0x14000561f  cmp     qword ptr [rbp+var_38], rax
0x140005623  jnz     short loc_14000564A
0x140005625  test    cs:Microsoft_Windows_PartitionEnableBits, 4
0x14000562c  jz      short loc_14000564A
0x14000562e  mov     r9d, [r13+0A8h]
0x140005635  lea     rdx, QueryDepends
0x14000563c  mov     [rsp+78h+var_58], 0
0x140005645  call    McTemplateK0qp_EtwWriteTransfer
0x14000564a  mov     rdi, qword ptr [rbp+var_38]
0x14000564e  lea     rax, [rbp+var_38]
0x140005652  mov     [rbp+var_40], rdi
0x140005656  cmp     rdi, rax
0x140005659  jz      loc_14000581D
0x14000565f  lea     rax, [rbp+var_38]
0x140005663  cmp     [rdi+8], rax
0x140005667  jnz     loc_140005896
0x14000566d  mov     rax, [rdi]
0x140005670  cmp     [rax+8], rdi
0x140005674  jnz     loc_140005896
0x14000567a  lea     rcx, [rbp+var_38]
0x14000567e  mov     qword ptr [rbp+var_38], rax
0x140005682  mov     [rax+8], rcx
0x140005686  lea     r15, [rdi-0A8h]
0x14000568d  test    cs:Microsoft_Windows_PartitionEnableBits, 4
0x140005694  jz      short loc_1400056AE
0x140005696  mov     r9d, [r13+0A8h]
0x14000569d  lea     rdx, QueryDepends
0x1400056a4  mov     [rsp+78h+var_58], r15
0x1400056a9  call    McTemplateK0qp_EtwWriteTransfer
0x1400056ae  mov     [rdi+8], rdi
0x1400056b2  mov     eax, r14d
0x1400056b5  mov     [rdi], rdi
0x1400056b8  mov     rbx, [r15+38h]
0x1400056bc  mov     [rbp+var_48], rbx
0x1400056c0  test    rbx, rbx
0x1400056c3  jz      short loc_1400056CA
0x1400056c5  mov     eax, [rbx]
0x1400056c7  add     eax, r14d
0x1400056ca  test    r12d, r12d
0x1400056cd  js      short loc_1400056FE
0x1400056cf  lea     eax, ds:8[rax*8]
0x1400056d6  mov     ecx, 102h
0x1400056db  movsxd  rdx, eax
0x1400056de  mov     r8d, 52526D50h
0x1400056e4  call    cs:__imp_ExAllocatePool2
0x1400056eb  nop     dword ptr [rax+rax+00h]
0x1400056f0  mov     r14, rax
0x1400056f3  test    rax, rax
0x1400056f6  jnz     short loc_14000574A
0x1400056f8  mov     r12d, 0C000009Ah
0x1400056fe  test    rbx, rbx
0x140005701  jz      short loc_140005735
0x140005703  xor     r14d, r14d
0x140005706  cmp     [rbx], r14d
0x140005709  jbe     short loc_140005724
0x14000570b  mov     rcx, [rbx+r14*8+8]; Object
0x140005710  call    cs:__imp_ObfDereferenceObject
0x140005717  nop     dword ptr [rax+rax+00h]
0x14000571c  inc     r14d
0x14000571f  cmp     r14d, [rbx]
0x140005722  jb      short loc_14000570B
0x140005724  xor     edx, edx; Tag
0x140005726  mov     rcx, rbx; P
0x140005729  call    cs:__imp_ExFreePoolWithTag
0x140005730  nop     dword ptr [rax+rax+00h]
0x140005735  mov     qword ptr [r15+38h], 0
0x14000573d  mov     r14d, [rbp+arg_8]
0x140005741  mov     [rdi-78h], r12d
0x140005745  jmp     loc_14000564A
0x14000574a  xor     r13d, r13d
0x14000574d  mov     [rax], r13d
0x140005750  mov     eax, [rsi]
0x140005752  test    eax, eax
0x140005754  jz      loc_1400057DE
0x14000575a  mov     edi, r13d
0x14000575d  mov     ebx, eax
0x14000575f  mov     eax, edi
0x140005761  mov     r15, [rsi+rax*8+8]
0x140005766  test    r15, r15
0x140005769  jz      short loc_1400057C9
0x14000576b  cmp     dword ptr [r15], 0
0x14000576f  jbe     short loc_1400057C9
0x140005771  xor     eax, eax
0x140005773  mov     [rbp+arg_10], eax
0x140005776  mov     edx, [r14]
0x140005779  xor     r13d, r13d
0x14000577c  mov     [rbp+arg_18], rax
0x140005780  cmp     r13d, edx
0x140005783  jnb     short loc_14000579A
0x140005785  mov     rax, [r15+rax*8+8]
0x14000578a  cmp     [r14+r13*8+8], rax
0x14000578f  jz      short loc_1400057BC
0x140005791  mov     rax, [rbp+arg_18]
0x140005795  inc     r13d
0x140005798  jmp     short loc_140005780
0x14000579a  mov     rcx, [r15+rax*8+8]; Object
0x14000579f  call    cs:__imp_ObfReferenceObject
0x1400057a6  nop     dword ptr [rax+rax+00h]
0x1400057ab  mov     rcx, [rbp+arg_18]
0x1400057af  mov     rax, [r15+rcx*8+8]
0x1400057b4  mov     [r14+r13*8+8], rax
0x1400057b9  inc     dword ptr [r14]
0x1400057bc  mov     eax, [rbp+arg_10]
0x1400057bf  inc     eax
0x1400057c1  mov     [rbp+arg_10], eax
0x1400057c4  cmp     eax, [r15]
0x1400057c7  jb      short loc_140005776
0x1400057c9  inc     edi
0x1400057cb  cmp     edi, ebx
0x1400057cd  jb      short loc_14000575F
0x1400057cf  mov     rdi, [rbp+var_40]
0x1400057d3  mov     rbx, [rbp+var_48]
0x1400057d7  lea     r15, [rdi-0A8h]
0x1400057de  test    rbx, rbx
0x1400057e1  jz      short loc_140005810
0x1400057e3  xor     ecx, ecx
0x1400057e5  cmp     [rbx], ecx
0x1400057e7  jbe     short loc_1400057FF
0x1400057e9  mov     rdx, [rbx+rcx*8+8]
0x1400057ee  inc     ecx
0x1400057f0  mov     [r14+r13*8+8], rdx
0x1400057f5  inc     r13d
0x1400057f8  inc     dword ptr [r14]
0x1400057fb  cmp     ecx, [rbx]
0x1400057fd  jb      short loc_1400057E9
0x1400057ff  xor     edx, edx; Tag
0x140005801  mov     rcx, rbx; P
0x140005804  call    cs:__imp_ExFreePoolWithTag
0x14000580b  nop     dword ptr [rax+rax+00h]
0x140005810  mov     r13, [rbp+arg_0]
0x140005814  mov     [r15+38h], r14
0x140005818  jmp     loc_14000573D
0x14000581d  test    rsi, rsi
0x140005820  jz      short loc_140005884
0x140005822  xor     edi, edi
0x140005824  cmp     [rsi], edi
0x140005826  jbe     short loc_140005873
0x140005828  mov     rbx, [rsi+rdi*8+8]
0x14000582d  test    rbx, rbx
0x140005830  jz      short loc_14000586D
0x140005832  xor     r14d, r14d
0x140005835  cmp     [rbx], r14d
0x140005838  jbe     short loc_140005853
0x14000583a  mov     rcx, [rbx+r14*8+8]; Object
0x14000583f  call    cs:__imp_ObfDereferenceObject
0x140005846  nop     dword ptr [rax+rax+00h]
0x14000584b  inc     r14d
0x14000584e  cmp     r14d, [rbx]
0x140005851  jb      short loc_14000583A
0x140005853  xor     edx, edx; Tag
0x140005855  mov     rcx, rbx; P
0x140005858  call    cs:__imp_ExFreePoolWithTag
0x14000585f  nop     dword ptr [rax+rax+00h]
0x140005864  mov     qword ptr [rsi+rdi*8+8], 0
0x14000586d  inc     edi
0x14000586f  cmp     edi, [rsi]
0x140005871  jb      short loc_140005828
0x140005873  xor     edx, edx; Tag
0x140005875  mov     rcx, rsi; P
0x140005878  call    cs:__imp_ExFreePoolWithTag
0x14000587f  nop     dword ptr [rax+rax+00h]
0x140005884  add     rsp, 78h
0x140005888  pop     r15
0x14000588a  pop     r14
0x14000588c  pop     r13
0x14000588e  pop     r12
0x140005890  pop     rdi
0x140005891  pop     rsi
0x140005892  pop     rbx
0x140005893  pop     rbp
0x140005894  retn
0x140005896  mov     ecx, 3
0x14000589b  int     29h; Win8: RtlFailFast(ecx)
```
