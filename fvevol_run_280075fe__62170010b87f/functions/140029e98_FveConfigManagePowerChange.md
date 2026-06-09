# FveConfigManagePowerChange

- ea: `0x140029e98`
- end: `0x14002a53b`
- name: `FveConfigManagePowerChange`
- size: `1699`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x140095bfc`

## callees

- `0x14000a574`
- `0x1400241b4`
- `0x140029a38`
- `0x140029e98`
- `0x14002d630`
- `0x14002e334`
- `0x14002ef38`
- `0x140050e94`
- `0x140085e60`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14002a0ff`
- `ntoskrnl!KeReleaseMutex` at `0x14002a517`
- `ntoskrnl!KeReleaseMutex` at `0x14002a0ff`
- `ntoskrnl!KeReleaseMutex` at `0x14002a517`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140029fd6`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002a344`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140029fd6`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002a344`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002a381`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002a3f7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002a4f2`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002a381`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002a3f7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002a4f2`
- `ntoskrnl!MmSizeOfMdl` at `0x140029f24`
- `ntoskrnl!MmSizeOfMdl` at `0x14002a303`
- `ntoskrnl!MmSizeOfMdl` at `0x140029f24`
- `ntoskrnl!MmSizeOfMdl` at `0x14002a303`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a0e8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a0e8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a07b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a07b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140029ef1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002a0a4`
- `ntoskrnl!KeWaitForSingleObject` at `0x140029ef1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002a0a4`
- `ntoskrnl!KeBugCheckEx` at `0x14002a276`
- `ntoskrnl!KeBugCheckEx` at `0x14002a276`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a3ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a506`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a3ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a506`
- `ntoskrnl!ExAllocatePool2` at `0x140029f9e`
- `ntoskrnl!ExAllocatePool2` at `0x140029f9e`

## pseudocode

```c
__int64 __fastcall FveConfigManagePowerChange(__int64 a1, unsigned int a2)
{
  __int64 v3; // rbx
  struct _NPAGED_LOOKASIDE_LIST *Pool2; // r15
  struct _KMUTANT *v5; // r14
  _DWORD *v6; // rax
  unsigned int v7; // r13d
  char v8; // si
  int v9; // edx
  int v10; // ecx
  unsigned int v11; // ebx
  int v12; // r8d
  int v13; // r9d
  int v14; // r12d
  __int64 DeviceExtension; // rbx
  PVOID *v16; // r14
  __int64 v17; // r8
  KIRQL v18; // al
  PVOID *v19; // rsi
  PVOID *v20; // rcx
  PVOID *v21; // rax
  PVOID v22; // rax
  _QWORD *v23; // rcx
  PVOID *v24; // rax
  PVOID *i; // rbx
  _QWORD *v26; // rax
  BOOL v27; // ecx
  __int64 v28; // rdx
  _QWORD *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  PVOID *v32; // rbx
  _DWORD *v33; // rcx
  unsigned int v34; // eax
  int v35; // eax
  struct _NPAGED_LOOKASIDE_LIST *v36; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v37; // rcx
  __int64 v38; // rax
  volatile __int64 *v39; // rcx
  __int64 v40; // rax
  volatile __int64 *v41; // rcx
  PVOID *v42; // rbx
  _QWORD *v43; // rbx
  __int64 v44; // rax
  int Timeout; // [rsp+20h] [rbp-49h]
  PVOID P; // [rsp+50h] [rbp-19h] BYREF
  struct _KMUTANT *v48; // [rsp+58h] [rbp-11h]
  __int64 LookasideList; // [rsp+60h] [rbp-9h]
  PVOID v50; // [rsp+68h] [rbp-1h] BYREF
  PVOID *v51; // [rsp+70h] [rbp+7h]
  char v52; // [rsp+D0h] [rbp+67h]
  KIRQL v54; // [rsp+E0h] [rbp+77h]
  unsigned int v55; // [rsp+E8h] [rbp+7Fh]

  v3 = a2;
  v51 = &v50;
  Pool2 = 0;
  LookasideList = 0;
  v5 = (struct _KMUTANT *)(a1 + 9608);
  P = 0;
  v50 = &v50;
  v48 = (struct _KMUTANT *)(a1 + 9608);
  KeWaitForSingleObject((PVOID)(a1 + 9608), Executive, 0, 0, 0);
  v6 = (_DWORD *)(a1 + 884);
  if ( (_DWORD)v3 && *v6 )
  {
    v7 = 0;
    v55 = 0;
  }
  else
  {
    v55 = v3 + *v6;
    v7 = v55;
    if ( !*(_BYTE *)(v55 + a1 + 1421) && !*(_BYTE *)(v55 + a1 + 1342) )
    {
      v8 = 0;
      v52 = 0;
      goto LABEL_12;
    }
  }
  v8 = 1;
  v52 = 1;
  v11 = MmSizeOfMdl(0, *(unsigned int *)(a1 + 4 * v3 + 936)) + *(_DWORD *)(a1 + 4 * v3 + 936) + 64;
  if ( *(_QWORD *)(a1 + 9016) )
  {
    LookasideList = PplCreateLookasideList(v10, v9, v12, v13, Timeout, v11);
    if ( !LookasideList )
    {
LABEL_6:
      v14 = -1073741670;
      goto LABEL_80;
    }
  }
  else
  {
    Pool2 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, 128, 809850438);
    if ( !Pool2 )
      goto LABEL_6;
    ExInitializeNPagedLookasideList(Pool2, 0, 0, 0x200u, v11, 0x70455646u, 0);
  }
LABEL_12:
  DeviceExtension = 0;
  v14 = 0;
  v16 = 0;
  v54 = 0;
  while ( 1 )
  {
    DeviceExtension = FveDcbNextDeviceExtension(a1, DeviceExtension, 0xFFFFFFFFLL);
    if ( !DeviceExtension )
      break;
    if ( v8 || *(_BYTE *)(v7 + DeviceExtension + 1998) )
    {
      v14 = FveConfigManageEntryCreate(DeviceExtension, a2, 0, 0, 0, (__int64)&P);
      if ( v14 < 0 )
        goto LABEL_79;
      if ( (int)FvepAcquireRemoveLockEx(DeviceExtension + 56) >= 0 )
      {
        if ( *(_DWORD *)(DeviceExtension + 836) == 2 )
        {
          KeWaitForSingleObject((PVOID)(DeviceExtension + 504), Executive, 0, 0, 0);
          v18 = v54;
        }
        else
        {
          v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(DeviceExtension + 496));
          v54 = v18;
        }
        if ( *(int *)(DeviceExtension + 136) <= 0 || !*(_DWORD *)(DeviceExtension + 168) || v16 )
        {
          v19 = (PVOID *)P;
        }
        else
        {
          v16 = (PVOID *)P;
          v19 = 0;
          P = 0;
        }
        if ( *(_DWORD *)(DeviceExtension + 836) == 2 )
          KeReleaseMutex((PRKMUTEX)(DeviceExtension + 504), 0);
        else
          KeReleaseSpinLock((PKSPIN_LOCK)(DeviceExtension + 496), v18);
        v7 = v55;
        if ( v19 )
        {
          v20 = (PVOID *)v50;
          if ( v50 == &v50 )
          {
LABEL_35:
            v21 = v51;
            if ( *v51 != &v50 )
              goto LABEL_84;
            v19[1] = v51;
            *v19 = &v50;
            *v21 = v19;
            v51 = v19;
          }
          else
          {
            while ( *(_DWORD *)(DeviceExtension + 1324) <= *((_DWORD *)v20[2] + 331) )
            {
              v20 = (PVOID *)*v20;
              if ( v20 == &v50 )
                goto LABEL_35;
            }
            v22 = v20[1];
            v23 = *(_QWORD **)v22;
            if ( *(PVOID *)(*(_QWORD *)v22 + 8LL) != v22 )
              goto LABEL_84;
            *v19 = v23;
            v19[1] = v22;
            v23[1] = v19;
            *(_QWORD *)v22 = v19;
          }
        }
        v8 = v52;
      }
      else
      {
        FveConfigManageEntryRelease(P);
      }
    }
  }
  if ( v16 )
  {
    v24 = v51;
    if ( *v51 != &v50 )
LABEL_84:
      __fastfail(3u);
    v16[1] = v51;
    *v16 = &v50;
    *v24 = v16;
    v51 = v16;
  }
  for ( i = (PVOID *)v50; i != &v50; i = (PVOID *)*i )
  {
    LOBYTE(v17) = 1;
    FvepAcquireDevFveLock(i[2], i + 3, v17);
    FveRundownAllReadsAndWrites(i[2]);
    v26 = i[2];
    v27 = v26[252] || v26[253];
    *((_DWORD *)i + 156) = v27;
    v28 = v26[252];
    if ( v28 && v28 == *(_QWORD *)(a1 + 9008) )
    {
      if ( !v27 )
        goto LABEL_57;
      v26[252] = 0;
    }
    v29 = i[2];
    v30 = v29[253];
    if ( v30 && v30 == *(_QWORD *)(a1 + 9016) )
    {
      if ( !*((_DWORD *)i + 156) )
LABEL_57:
        KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
      v29[253] = 0;
    }
  }
  if ( v8 )
  {
    *(_DWORD *)(a1 + 3684) = *(_DWORD *)(a1 + 4LL * a2 + 1372);
    *(_DWORD *)(a1 + 6940) = *(_DWORD *)(a1 + 4LL * a2 + 1384);
    v31 = LookasideList;
    Pool2 = (struct _NPAGED_LOOKASIDE_LIST *)_InterlockedExchange64((volatile __int64 *)(a1 + 9008), (__int64)Pool2);
    _InterlockedExchange64((volatile __int64 *)(a1 + 9016), v31);
  }
  v32 = (PVOID *)v50;
  if ( v50 != &v50 )
  {
    do
    {
      if ( *((_DWORD *)v32 + 156) )
      {
        v33 = v32[2];
        v34 = v33[a2 + 398];
        if ( v34 == *(_DWORD *)(a1 + 4LL * a2 + 936) )
        {
          if ( *((_QWORD *)v33 + 252) != *(_QWORD *)(a1 + 9008) )
          {
            ExFreePoolWithTag(v32[74], 0x30455646u);
            v37 = (struct _NPAGED_LOOKASIDE_LIST *)_InterlockedExchange64(
                                                     (volatile __int64 *)v32[2] + 252,
                                                     *(_QWORD *)(a1 + 9008));
            v32[74] = v37;
            if ( v37 == *(struct _NPAGED_LOOKASIDE_LIST **)(a1 + 9008) )
            {
              v32[74] = 0;
            }
            else if ( v37 )
            {
              ExDeleteNPagedLookasideList(v37);
            }
          }
          *((_QWORD *)v32[2] + 253) = *(_QWORD *)(a1 + 9016);
        }
        else
        {
          v35 = MmSizeOfMdl(0, v34);
          ExInitializeNPagedLookasideList(
            (PNPAGED_LOOKASIDE_LIST)v32[74],
            0,
            0,
            0x200u,
            (unsigned int)(*((_DWORD *)v32[2] + a2 + 398) + v35 + 64),
            0x70455646u,
            0);
          v36 = (struct _NPAGED_LOOKASIDE_LIST *)_InterlockedExchange64(
                                                   (volatile __int64 *)v32[2] + 252,
                                                   (__int64)v32[74]);
          v32[74] = v36;
          if ( v36 == *(struct _NPAGED_LOOKASIDE_LIST **)(a1 + 9008) )
          {
            v32[74] = 0;
          }
          else if ( v36 )
          {
            ExDeleteNPagedLookasideList(v36);
          }
          *((_QWORD *)v32[2] + 253) = 0;
        }
        v38 = _InterlockedExchange64((volatile __int64 *)v32[2] + 257, (__int64)v32[75]);
        v39 = (volatile __int64 *)v32[2];
        v32[75] = (PVOID)v38;
        v40 = _InterlockedExchange64(v39 + 263, (__int64)v32[76]);
        v41 = (volatile __int64 *)v32[2];
        v32[76] = (PVOID)v40;
        v32[77] = (PVOID)_InterlockedExchange64(v41 + 264, (__int64)v32[77]);
      }
      v32 = (PVOID *)*v32;
    }
    while ( v32 != &v50 );
  }
  v42 = v51;
  *(_DWORD *)(a1 + 884) = a2;
  while ( v42 != &v50 )
  {
    FveResumeAllReadsAndWrites(v42[2]);
    FvepReleaseDevFveLock(v42 + 3);
    v42 = (PVOID *)v42[1];
  }
LABEL_79:
  v5 = v48;
LABEL_80:
  while ( 1 )
  {
    v43 = v50;
    if ( v50 == &v50 )
      break;
    if ( *((PVOID **)v50 + 1) != &v50 )
      goto LABEL_84;
    v44 = *(_QWORD *)v50;
    if ( *(PVOID *)(*(_QWORD *)v50 + 8LL) != v50 )
      goto LABEL_84;
    v50 = *(PVOID *)v50;
    *(_QWORD *)(v44 + 8) = &v50;
    FvepReleaseRemoveLock(v43[2] + 56LL);
    FveConfigManageEntryRelease(v43);
  }
  if ( Pool2 )
  {
    ExDeleteNPagedLookasideList(Pool2);
    ExFreePoolWithTag(Pool2, 0x30455646u);
  }
  KeReleaseMutex(v5, 0);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140029e98  mov     [rsp-8+arg_8], edx
0x140029e9c  push    rbp
0x140029e9d  push    rbx
0x140029e9e  push    rsi
0x140029e9f  push    rdi
0x140029ea0  push    r12
0x140029ea2  push    r13
0x140029ea4  push    r14
0x140029ea6  push    r15
0x140029ea8  lea     rbp, [rsp-1Fh]
0x140029ead  sub     rsp, 88h
0x140029eb4  mov     rdi, rcx
0x140029eb7  mov     ebx, edx
0x140029eb9  xor     ecx, ecx
0x140029ebb  lea     rax, [rbp+57h+var_58]
0x140029ebf  mov     [rbp+57h+var_50], rax
0x140029ec3  mov     r15d, ecx
0x140029ec6  mov     [rbp+57h+var_60], rcx
0x140029eca  lea     rax, [rbp+57h+var_58]
0x140029ece  lea     r14, [rdi+2588h]
0x140029ed5  mov     [rbp+57h+P], rcx
0x140029ed9  mov     [rsp+0C0h+Timeout], rcx; int
0x140029ede  xor     r9d, r9d; Alertable
0x140029ee1  mov     rcx, r14; Object
0x140029ee4  mov     [rbp+57h+var_58], rax
0x140029ee8  xor     r8d, r8d; WaitMode
0x140029eeb  mov     [rbp+57h+var_68], r14
0x140029eef  xor     edx, edx; WaitReason
0x140029ef1  call    cs:__imp_KeWaitForSingleObject
0x140029ef8  nop     dword ptr [rax+rax+00h]
0x140029efd  lea     rax, [rdi+374h]
0x140029f04  test    ebx, ebx
0x140029f06  jz      short loc_140029F69
0x140029f08  cmp     [rax], r15d
0x140029f0b  jz      short loc_140029F69
0x140029f0d  xor     r13d, r13d
0x140029f10  mov     [rbp+57h+arg_18], r13d
0x140029f14  mov     edx, [rdi+rbx*4+3A8h]; Length
0x140029f1b  mov     sil, 1
0x140029f1e  xor     ecx, ecx; Base
0x140029f20  mov     [rbp+57h+arg_0], sil
0x140029f24  call    cs:__imp_MmSizeOfMdl
0x140029f2b  nop     dword ptr [rax+rax+00h]
0x140029f30  mov     ebx, [rdi+rbx*4+3A8h]
0x140029f37  add     ebx, 40h ; '@'
0x140029f3a  add     ebx, eax
0x140029f3c  cmp     [rdi+2338h], r15
0x140029f43  jz      short loc_140029F90
0x140029f45  mov     eax, ebx
0x140029f47  mov     qword ptr [rsp+0C0h+Tag], rax; SIZE_T
0x140029f4c  call    PplCreateLookasideList
0x140029f51  mov     [rbp+57h+var_60], rax
0x140029f55  test    rax, rax
0x140029f58  jnz     loc_140029FE2
0x140029f5e  mov     r12d, 0C000009Ah
0x140029f64  jmp     loc_14002A4A0
0x140029f69  mov     r13d, [rax]
0x140029f6c  add     r13d, ebx
0x140029f6f  mov     [rbp+57h+arg_18], r13d
0x140029f73  cmp     [r13+rdi+58Dh], r15b
0x140029f7b  jnz     short loc_140029F14
0x140029f7d  cmp     [r13+rdi+53Eh], r15b
0x140029f85  jnz     short loc_140029F14
0x140029f87  xor     sil, sil
0x140029f8a  mov     [rbp+57h+arg_0], sil
0x140029f8e  jmp     short loc_140029FE2
0x140029f90  mov     edx, 80h
0x140029f95  mov     r8d, 30455646h
0x140029f9b  lea     ecx, [rdx-40h]
0x140029f9e  call    cs:__imp_ExAllocatePool2
0x140029fa5  nop     dword ptr [rax+rax+00h]
0x140029faa  mov     r15, rax
0x140029fad  test    rax, rax
0x140029fb0  jz      short loc_140029F5E
0x140029fb2  xor     eax, eax
0x140029fb4  mov     ecx, ebx
0x140029fb6  mov     [rsp+0C0h+Depth], ax; Depth
0x140029fbb  mov     r9d, 200h; Flags
0x140029fc1  mov     [rsp+0C0h+Tag], 70455646h; Tag
0x140029fc9  xor     r8d, r8d; Free
0x140029fcc  mov     [rsp+0C0h+Timeout], rcx; Size
0x140029fd1  xor     edx, edx; Allocate
0x140029fd3  mov     rcx, r15; Lookaside
0x140029fd6  call    cs:__imp_ExInitializeNPagedLookasideList
0x140029fdd  nop     dword ptr [rax+rax+00h]
0x140029fe2  xor     ebx, ebx
0x140029fe4  xor     r12d, r12d
0x140029fe7  xor     r14d, r14d
0x140029fea  mov     [rbp+57h+arg_10], bl
0x140029fed  jmp     short loc_140029FF3
0x140029fef  mov     sil, [rbp+57h+arg_0]
0x140029ff3  or      r8d, 0FFFFFFFFh
0x140029ff7  mov     rdx, rbx
0x140029ffa  mov     rcx, rdi
0x140029ffd  call    FveDcbNextDeviceExtension
0x14002a002  mov     rbx, rax
0x14002a005  test    rax, rax
0x14002a008  jz      loc_14002A18C
0x14002a00e  test    sil, sil
0x14002a011  jnz     short loc_14002A020
0x14002a013  mov     eax, r13d
0x14002a016  cmp     [rax+rbx+7CEh], sil
0x14002a01e  jz      short loc_140029FF3
0x14002a020  mov     edx, [rbp+57h+arg_8]
0x14002a023  lea     rax, [rbp+57h+P]
0x14002a027  mov     qword ptr [rsp+0C0h+Tag], rax
0x14002a02c  xor     r9d, r9d
0x14002a02f  xor     r8d, r8d
0x14002a032  mov     [rsp+0C0h+Timeout], 0
0x14002a03b  mov     rcx, rbx
0x14002a03e  call    FveConfigManageEntryCreate
0x14002a043  mov     r12d, eax
0x14002a046  test    eax, eax
0x14002a048  js      loc_14002A49C
0x14002a04e  lea     rcx, [rbx+38h]; BugCheckParameter2
0x14002a052  xor     edx, edx
0x14002a054  call    FvepAcquireRemoveLockEx
0x14002a059  test    eax, eax
0x14002a05b  jns     short loc_14002A068
0x14002a05d  mov     rcx, [rbp+57h+P]; P
0x14002a061  call    FveConfigManageEntryRelease
0x14002a066  jmp     short loc_140029FF3
0x14002a068  cmp     dword ptr [rbx+344h], 2
0x14002a06f  lea     r13, [rbx+1F0h]
0x14002a076  jz      short loc_14002A08C
0x14002a078  mov     rcx, r13; SpinLock
0x14002a07b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002a082  nop     dword ptr [rax+rax+00h]
0x14002a087  mov     [rbp+57h+arg_10], al
0x14002a08a  jmp     short loc_14002A0B3
0x14002a08c  xor     r9d, r9d; Alertable
0x14002a08f  mov     [rsp+0C0h+Timeout], 0; Timeout
0x14002a098  xor     r8d, r8d; WaitMode
0x14002a09b  lea     rcx, [rbx+1F8h]; Object
0x14002a0a2  xor     edx, edx; WaitReason
0x14002a0a4  call    cs:__imp_KeWaitForSingleObject
0x14002a0ab  nop     dword ptr [rax+rax+00h]
0x14002a0b0  mov     al, [rbp+57h+arg_10]
0x14002a0b3  cmp     dword ptr [rbx+88h], 0
0x14002a0ba  jle     short loc_14002A0D6
0x14002a0bc  cmp     dword ptr [rbx+0A8h], 0
0x14002a0c3  jbe     short loc_14002A0D6
0x14002a0c5  test    r14, r14
0x14002a0c8  jnz     short loc_14002A0D6
0x14002a0ca  mov     r14, [rbp+57h+P]
0x14002a0ce  xor     esi, esi
0x14002a0d0  mov     [rbp+57h+P], rsi
0x14002a0d4  jmp     short loc_14002A0DA
0x14002a0d6  mov     rsi, [rbp+57h+P]
0x14002a0da  cmp     dword ptr [rbx+344h], 2
0x14002a0e1  jz      short loc_14002A0F6
0x14002a0e3  mov     dl, al; NewIrql
0x14002a0e5  mov     rcx, r13; SpinLock
0x14002a0e8  call    cs:__imp_KeReleaseSpinLock
0x14002a0ef  nop     dword ptr [rax+rax+00h]
0x14002a0f4  jmp     short loc_14002A10B
0x14002a0f6  xor     edx, edx; Wait
0x14002a0f8  lea     rcx, [rbx+1F8h]; Mutex
0x14002a0ff  call    cs:__imp_KeReleaseMutex
0x14002a106  nop     dword ptr [rax+rax+00h]
0x14002a10b  mov     r13d, [rbp+57h+arg_18]
0x14002a10f  test    rsi, rsi
0x14002a112  jz      loc_140029FEF
0x14002a118  mov     rcx, [rbp+57h+var_58]
0x14002a11c  lea     rax, [rbp+57h+var_58]
0x14002a120  cmp     rcx, rax
0x14002a123  jz      short loc_14002A143
0x14002a125  mov     edx, [rbx+52Ch]
0x14002a12b  mov     rax, [rcx+10h]
0x14002a12f  cmp     edx, [rax+52Ch]
0x14002a135  ja      short loc_14002A16B
0x14002a137  mov     rcx, [rcx]
0x14002a13a  lea     rax, [rbp+57h+var_58]
0x14002a13e  cmp     rcx, rax
0x14002a141  jnz     short loc_14002A12B
0x14002a143  mov     rax, [rbp+57h+var_50]
0x14002a147  lea     rcx, [rbp+57h+var_58]
0x14002a14b  cmp     [rax], rcx
0x14002a14e  jnz     loc_14002A4E3
0x14002a154  mov     [rsi+8], rax
0x14002a158  lea     rcx, [rbp+57h+var_58]
0x14002a15c  mov     [rsi], rcx
0x14002a15f  mov     [rax], rsi
0x14002a162  mov     [rbp+57h+var_50], rsi
0x14002a166  jmp     loc_140029FEF
0x14002a16b  mov     rax, [rcx+8]
0x14002a16f  mov     rcx, [rax]
0x14002a172  cmp     [rcx+8], rax
0x14002a176  jnz     loc_14002A4E3
0x14002a17c  mov     [rsi], rcx
0x14002a17f  mov     [rsi+8], rax
0x14002a183  mov     [rcx+8], rsi
0x14002a187  mov     [rax], rsi
0x14002a18a  jmp     short loc_14002A166
0x14002a18c  test    r14, r14
0x14002a18f  jz      short loc_14002A1B4
0x14002a191  mov     rax, [rbp+57h+var_50]
0x14002a195  lea     rcx, [rbp+57h+var_58]
0x14002a199  cmp     [rax], rcx
0x14002a19c  jnz     loc_14002A4E3
0x14002a1a2  mov     [r14+8], rax
0x14002a1a6  lea     rcx, [rbp+57h+var_58]
0x14002a1aa  mov     [r14], rcx
0x14002a1ad  mov     [rax], r14
0x14002a1b0  mov     [rbp+57h+var_50], r14
0x14002a1b4  mov     rbx, [rbp+57h+var_58]
0x14002a1b8  lea     rax, [rbp+57h+var_58]
0x14002a1bc  cmp     rbx, rax
0x14002a1bf  jz      loc_14002A283
0x14002a1c5  mov     rcx, [rbx+10h]
0x14002a1c9  lea     rdx, [rbx+18h]
0x14002a1cd  mov     r8b, 1
0x14002a1d0  call    FvepAcquireDevFveLock
0x14002a1d5  mov     rcx, [rbx+10h]
0x14002a1d9  call    FveRundownAllReadsAndWrites
0x14002a1de  mov     rax, [rbx+10h]
0x14002a1e2  cmp     qword ptr [rax+7E0h], 0
0x14002a1ea  jnz     short loc_14002A1FA
0x14002a1ec  cmp     qword ptr [rax+7E8h], 0
0x14002a1f4  jnz     short loc_14002A1FA
0x14002a1f6  xor     ecx, ecx
0x14002a1f8  jmp     short loc_14002A1FF
0x14002a1fa  mov     ecx, 1
0x14002a1ff  mov     [rbx+270h], ecx
0x14002a205  mov     rdx, [rax+7E0h]
0x14002a20c  test    rdx, rdx
0x14002a20f  jz      short loc_14002A229
0x14002a211  cmp     rdx, [rdi+2330h]
0x14002a218  jnz     short loc_14002A229
0x14002a21a  test    ecx, ecx
0x14002a21c  jz      short loc_14002A25E
0x14002a21e  mov     qword ptr [rax+7E0h], 0
0x14002a229  mov     rcx, [rbx+10h]
0x14002a22d  mov     rax, [rcx+7E8h]
0x14002a234  test    rax, rax
0x14002a237  jz      short loc_14002A256
0x14002a239  cmp     rax, [rdi+2338h]
0x14002a240  jnz     short loc_14002A256
0x14002a242  cmp     dword ptr [rbx+270h], 0
0x14002a249  jz      short loc_14002A25E
0x14002a24b  mov     qword ptr [rcx+7E8h], 0
0x14002a256  mov     rbx, [rbx]
0x14002a259  jmp     loc_14002A1B8
0x14002a25e  xor     r9d, r9d; BugCheckParameter3
0x14002a261  mov     [rsp+0C0h+Timeout], 0; BugCheckParameter4
0x14002a26a  xor     r8d, r8d; BugCheckParameter2
0x14002a26d  mov     ecx, 120h; BugCheckCode
0x14002a272  lea     edx, [r9+0Ch]; BugCheckParameter1
0x14002a276  call    cs:__imp_KeBugCheckEx
0x14002a283  test    sil, sil
0x14002a286  jz      short loc_14002A2BC
0x14002a288  mov     r14d, [rbp+57h+arg_8]
0x14002a28c  mov     eax, [rdi+r14*4+55Ch]
0x14002a294  mov     [rdi+0E64h], eax
0x14002a29a  mov     eax, [rdi+r14*4+568h]
0x14002a2a2  mov     [rdi+1B1Ch], eax
0x14002a2a8  mov     rax, [rbp+57h+var_60]
0x14002a2ac  xchg    r15, [rdi+2330h]
0x14002a2b3  xchg    rax, [rdi+2338h]
0x14002a2ba  jmp     short loc_14002A2C0
0x14002a2bc  mov     r14d, [rbp+57h+arg_8]
0x14002a2c0  mov     rbx, [rbp+57h+var_58]
0x14002a2c4  lea     rax, [rbp+57h+var_58]
0x14002a2c8  cmp     rbx, rax
0x14002a2cb  jz      loc_14002A470
0x14002a2d1  mov     r13d, 7E0h
0x14002a2d7  cmp     dword ptr [rbx+270h], 0
0x14002a2de  jz      loc_14002A460
0x14002a2e4  mov     rcx, [rbx+10h]
0x14002a2e8  mov     esi, r14d
0x14002a2eb  mov     eax, [rcx+rsi*4+638h]
0x14002a2f2  cmp     eax, [rdi+rsi*4+3A8h]
0x14002a2f9  jz      loc_14002A39E
0x14002a2ff  mov     edx, eax; Length
0x14002a301  xor     ecx, ecx; Base
0x14002a303  call    cs:__imp_MmSizeOfMdl
0x14002a30a  nop     dword ptr [rax+rax+00h]
0x14002a30f  mov     rcx, [rbx+10h]
0x14002a313  xor     r8d, r8d; Free
0x14002a316  mov     [rsp+0C0h+Depth], r8w; Depth
0x14002a31c  mov     r9d, 200h; Flags
0x14002a322  mov     [rsp+0C0h+Tag], 70455646h; Tag
0x14002a32a  mov     edx, [rcx+rsi*4+638h]
0x14002a331  lea     ecx, [rax+40h]
0x14002a334  add     ecx, edx
0x14002a336  xor     edx, edx; Allocate
0x14002a338  mov     [rsp+0C0h+Timeout], rcx; Size
0x14002a33d  mov     rcx, [rbx+250h]; Lookaside
0x14002a344  call    cs:__imp_ExInitializeNPagedLookasideList
0x14002a34b  nop     dword ptr [rax+rax+00h]
0x14002a350  mov     rcx, [rbx+250h]
0x14002a357  mov     rax, [rbx+10h]
0x14002a35b  xchg    rcx, [rax+r13]; Lookaside
0x14002a35f  mov     [rbx+250h], rcx
0x14002a366  cmp     rcx, [rdi+2330h]
0x14002a36d  jnz     short loc_14002A37C
0x14002a36f  mov     qword ptr [rbx+250h], 0
0x14002a37a  jmp     short loc_14002A38D
0x14002a37c  test    rcx, rcx
0x14002a37f  jz      short loc_14002A38D
  ... truncated ...
```
