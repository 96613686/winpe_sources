# FveConfigManagePowerChange

- ea: `0x14002ae98`
- end: `0x14002b53b`
- name: `FveConfigManagePowerChange`
- size: `1699`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x140097cac`

## callees

- `0x14000a634`
- `0x1400251b4`
- `0x14002aa38`
- `0x14002ae98`
- `0x14002e630`
- `0x14002f334`
- `0x14002ff38`
- `0x140052e94`
- `0x140087f00`
- `0x1400dce00`
- `0x1400dd144`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14002b0ff`
- `ntoskrnl!KeReleaseMutex` at `0x14002b517`
- `ntoskrnl!KeReleaseMutex` at `0x14002b0ff`
- `ntoskrnl!KeReleaseMutex` at `0x14002b517`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002afd6`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002b344`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002afd6`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002b344`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002b381`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002b3f7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002b4f2`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002b381`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002b3f7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002b4f2`
- `ntoskrnl!MmSizeOfMdl` at `0x14002af24`
- `ntoskrnl!MmSizeOfMdl` at `0x14002b303`
- `ntoskrnl!MmSizeOfMdl` at `0x14002af24`
- `ntoskrnl!MmSizeOfMdl` at `0x14002b303`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b0e8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b0e8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b07b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b07b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002aef1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002b0a4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002aef1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002b0a4`
- `ntoskrnl!KeBugCheckEx` at `0x14002b276`
- `ntoskrnl!KeBugCheckEx` at `0x14002b276`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b3ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b506`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b3ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b506`
- `ntoskrnl!ExAllocatePool2` at `0x14002af9e`
- `ntoskrnl!ExAllocatePool2` at `0x14002af9e`

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
  v5 = (struct _KMUTANT *)(a1 + 9856);
  P = 0;
  v50 = &v50;
  v48 = (struct _KMUTANT *)(a1 + 9856);
  KeWaitForSingleObject((PVOID)(a1 + 9856), Executive, 0, 0, 0);
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
  if ( *(_QWORD *)(a1 + 9264) )
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
    if ( v28 && v28 == *(_QWORD *)(a1 + 9256) )
    {
      if ( !v27 )
        goto LABEL_57;
      v26[252] = 0;
    }
    v29 = i[2];
    v30 = v29[253];
    if ( v30 && v30 == *(_QWORD *)(a1 + 9264) )
    {
      if ( !*((_DWORD *)i + 156) )
LABEL_57:
        KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
      v29[253] = 0;
    }
  }
  if ( v8 )
  {
    *(_DWORD *)(a1 + 3932) = *(_DWORD *)(a1 + 4LL * a2 + 1372);
    *(_DWORD *)(a1 + 7188) = *(_DWORD *)(a1 + 4LL * a2 + 1384);
    v31 = LookasideList;
    Pool2 = (struct _NPAGED_LOOKASIDE_LIST *)_InterlockedExchange64((volatile __int64 *)(a1 + 9256), (__int64)Pool2);
    _InterlockedExchange64((volatile __int64 *)(a1 + 9264), v31);
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
          if ( *((_QWORD *)v33 + 252) != *(_QWORD *)(a1 + 9256) )
          {
            ExFreePoolWithTag(v32[74], 0x30455646u);
            v37 = (struct _NPAGED_LOOKASIDE_LIST *)_InterlockedExchange64(
                                                     (volatile __int64 *)v32[2] + 252,
                                                     *(_QWORD *)(a1 + 9256));
            v32[74] = v37;
            if ( v37 == *(struct _NPAGED_LOOKASIDE_LIST **)(a1 + 9256) )
            {
              v32[74] = 0;
            }
            else if ( v37 )
            {
              ExDeleteNPagedLookasideList(v37);
            }
          }
          *((_QWORD *)v32[2] + 253) = *(_QWORD *)(a1 + 9264);
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
          if ( v36 == *(struct _NPAGED_LOOKASIDE_LIST **)(a1 + 9256) )
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
0x14002ae98  mov     [rsp-8+arg_8], edx
0x14002ae9c  push    rbp
0x14002ae9d  push    rbx
0x14002ae9e  push    rsi
0x14002ae9f  push    rdi
0x14002aea0  push    r12
0x14002aea2  push    r13
0x14002aea4  push    r14
0x14002aea6  push    r15
0x14002aea8  lea     rbp, [rsp-1Fh]
0x14002aead  sub     rsp, 88h
0x14002aeb4  mov     rdi, rcx
0x14002aeb7  mov     ebx, edx
0x14002aeb9  xor     ecx, ecx
0x14002aebb  lea     rax, [rbp+57h+var_58]
0x14002aebf  mov     [rbp+57h+var_50], rax
0x14002aec3  mov     r15d, ecx
0x14002aec6  mov     [rbp+57h+var_60], rcx
0x14002aeca  lea     rax, [rbp+57h+var_58]
0x14002aece  lea     r14, [rdi+2680h]
0x14002aed5  mov     [rbp+57h+P], rcx
0x14002aed9  mov     [rsp+0C0h+Timeout], rcx; int
0x14002aede  xor     r9d, r9d; Alertable
0x14002aee1  mov     rcx, r14; Object
0x14002aee4  mov     [rbp+57h+var_58], rax
0x14002aee8  xor     r8d, r8d; WaitMode
0x14002aeeb  mov     [rbp+57h+var_68], r14
0x14002aeef  xor     edx, edx; WaitReason
0x14002aef1  call    cs:__imp_KeWaitForSingleObject
0x14002aef8  nop     dword ptr [rax+rax+00h]
0x14002aefd  lea     rax, [rdi+374h]
0x14002af04  test    ebx, ebx
0x14002af06  jz      short loc_14002AF69
0x14002af08  cmp     [rax], r15d
0x14002af0b  jz      short loc_14002AF69
0x14002af0d  xor     r13d, r13d
0x14002af10  mov     [rbp+57h+arg_18], r13d
0x14002af14  mov     edx, [rdi+rbx*4+3A8h]; Length
0x14002af1b  mov     sil, 1
0x14002af1e  xor     ecx, ecx; Base
0x14002af20  mov     [rbp+57h+arg_0], sil
0x14002af24  call    cs:__imp_MmSizeOfMdl
0x14002af2b  nop     dword ptr [rax+rax+00h]
0x14002af30  mov     ebx, [rdi+rbx*4+3A8h]
0x14002af37  add     ebx, 40h ; '@'
0x14002af3a  add     ebx, eax
0x14002af3c  cmp     [rdi+2430h], r15
0x14002af43  jz      short loc_14002AF90
0x14002af45  mov     eax, ebx
0x14002af47  mov     qword ptr [rsp+0C0h+Tag], rax; SIZE_T
0x14002af4c  call    PplCreateLookasideList
0x14002af51  mov     [rbp+57h+var_60], rax
0x14002af55  test    rax, rax
0x14002af58  jnz     loc_14002AFE2
0x14002af5e  mov     r12d, 0C000009Ah
0x14002af64  jmp     loc_14002B4A0
0x14002af69  mov     r13d, [rax]
0x14002af6c  add     r13d, ebx
0x14002af6f  mov     [rbp+57h+arg_18], r13d
0x14002af73  cmp     [r13+rdi+58Dh], r15b
0x14002af7b  jnz     short loc_14002AF14
0x14002af7d  cmp     [r13+rdi+53Eh], r15b
0x14002af85  jnz     short loc_14002AF14
0x14002af87  xor     sil, sil
0x14002af8a  mov     [rbp+57h+arg_0], sil
0x14002af8e  jmp     short loc_14002AFE2
0x14002af90  mov     edx, 80h
0x14002af95  mov     r8d, 30455646h
0x14002af9b  lea     ecx, [rdx-40h]
0x14002af9e  call    cs:__imp_ExAllocatePool2
0x14002afa5  nop     dword ptr [rax+rax+00h]
0x14002afaa  mov     r15, rax
0x14002afad  test    rax, rax
0x14002afb0  jz      short loc_14002AF5E
0x14002afb2  xor     eax, eax
0x14002afb4  mov     ecx, ebx
0x14002afb6  mov     [rsp+0C0h+Depth], ax; Depth
0x14002afbb  mov     r9d, 200h; Flags
0x14002afc1  mov     [rsp+0C0h+Tag], 70455646h; Tag
0x14002afc9  xor     r8d, r8d; Free
0x14002afcc  mov     [rsp+0C0h+Timeout], rcx; Size
0x14002afd1  xor     edx, edx; Allocate
0x14002afd3  mov     rcx, r15; Lookaside
0x14002afd6  call    cs:__imp_ExInitializeNPagedLookasideList
0x14002afdd  nop     dword ptr [rax+rax+00h]
0x14002afe2  xor     ebx, ebx
0x14002afe4  xor     r12d, r12d
0x14002afe7  xor     r14d, r14d
0x14002afea  mov     [rbp+57h+arg_10], bl
0x14002afed  jmp     short loc_14002AFF3
0x14002afef  mov     sil, [rbp+57h+arg_0]
0x14002aff3  or      r8d, 0FFFFFFFFh
0x14002aff7  mov     rdx, rbx
0x14002affa  mov     rcx, rdi
0x14002affd  call    FveDcbNextDeviceExtension
0x14002b002  mov     rbx, rax
0x14002b005  test    rax, rax
0x14002b008  jz      loc_14002B18C
0x14002b00e  test    sil, sil
0x14002b011  jnz     short loc_14002B020
0x14002b013  mov     eax, r13d
0x14002b016  cmp     [rax+rbx+7CEh], sil
0x14002b01e  jz      short loc_14002AFF3
0x14002b020  mov     edx, [rbp+57h+arg_8]
0x14002b023  lea     rax, [rbp+57h+P]
0x14002b027  mov     qword ptr [rsp+0C0h+Tag], rax
0x14002b02c  xor     r9d, r9d
0x14002b02f  xor     r8d, r8d
0x14002b032  mov     [rsp+0C0h+Timeout], 0
0x14002b03b  mov     rcx, rbx
0x14002b03e  call    FveConfigManageEntryCreate
0x14002b043  mov     r12d, eax
0x14002b046  test    eax, eax
0x14002b048  js      loc_14002B49C
0x14002b04e  lea     rcx, [rbx+38h]; BugCheckParameter2
0x14002b052  xor     edx, edx
0x14002b054  call    FvepAcquireRemoveLockEx
0x14002b059  test    eax, eax
0x14002b05b  jns     short loc_14002B068
0x14002b05d  mov     rcx, [rbp+57h+P]; P
0x14002b061  call    FveConfigManageEntryRelease
0x14002b066  jmp     short loc_14002AFF3
0x14002b068  cmp     dword ptr [rbx+344h], 2
0x14002b06f  lea     r13, [rbx+1F0h]
0x14002b076  jz      short loc_14002B08C
0x14002b078  mov     rcx, r13; SpinLock
0x14002b07b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002b082  nop     dword ptr [rax+rax+00h]
0x14002b087  mov     [rbp+57h+arg_10], al
0x14002b08a  jmp     short loc_14002B0B3
0x14002b08c  xor     r9d, r9d; Alertable
0x14002b08f  mov     [rsp+0C0h+Timeout], 0; Timeout
0x14002b098  xor     r8d, r8d; WaitMode
0x14002b09b  lea     rcx, [rbx+1F8h]; Object
0x14002b0a2  xor     edx, edx; WaitReason
0x14002b0a4  call    cs:__imp_KeWaitForSingleObject
0x14002b0ab  nop     dword ptr [rax+rax+00h]
0x14002b0b0  mov     al, [rbp+57h+arg_10]
0x14002b0b3  cmp     dword ptr [rbx+88h], 0
0x14002b0ba  jle     short loc_14002B0D6
0x14002b0bc  cmp     dword ptr [rbx+0A8h], 0
0x14002b0c3  jbe     short loc_14002B0D6
0x14002b0c5  test    r14, r14
0x14002b0c8  jnz     short loc_14002B0D6
0x14002b0ca  mov     r14, [rbp+57h+P]
0x14002b0ce  xor     esi, esi
0x14002b0d0  mov     [rbp+57h+P], rsi
0x14002b0d4  jmp     short loc_14002B0DA
0x14002b0d6  mov     rsi, [rbp+57h+P]
0x14002b0da  cmp     dword ptr [rbx+344h], 2
0x14002b0e1  jz      short loc_14002B0F6
0x14002b0e3  mov     dl, al; NewIrql
0x14002b0e5  mov     rcx, r13; SpinLock
0x14002b0e8  call    cs:__imp_KeReleaseSpinLock
0x14002b0ef  nop     dword ptr [rax+rax+00h]
0x14002b0f4  jmp     short loc_14002B10B
0x14002b0f6  xor     edx, edx; Wait
0x14002b0f8  lea     rcx, [rbx+1F8h]; Mutex
0x14002b0ff  call    cs:__imp_KeReleaseMutex
0x14002b106  nop     dword ptr [rax+rax+00h]
0x14002b10b  mov     r13d, [rbp+57h+arg_18]
0x14002b10f  test    rsi, rsi
0x14002b112  jz      loc_14002AFEF
0x14002b118  mov     rcx, [rbp+57h+var_58]
0x14002b11c  lea     rax, [rbp+57h+var_58]
0x14002b120  cmp     rcx, rax
0x14002b123  jz      short loc_14002B143
0x14002b125  mov     edx, [rbx+52Ch]
0x14002b12b  mov     rax, [rcx+10h]
0x14002b12f  cmp     edx, [rax+52Ch]
0x14002b135  ja      short loc_14002B16B
0x14002b137  mov     rcx, [rcx]
0x14002b13a  lea     rax, [rbp+57h+var_58]
0x14002b13e  cmp     rcx, rax
0x14002b141  jnz     short loc_14002B12B
0x14002b143  mov     rax, [rbp+57h+var_50]
0x14002b147  lea     rcx, [rbp+57h+var_58]
0x14002b14b  cmp     [rax], rcx
0x14002b14e  jnz     loc_14002B4E3
0x14002b154  mov     [rsi+8], rax
0x14002b158  lea     rcx, [rbp+57h+var_58]
0x14002b15c  mov     [rsi], rcx
0x14002b15f  mov     [rax], rsi
0x14002b162  mov     [rbp+57h+var_50], rsi
0x14002b166  jmp     loc_14002AFEF
0x14002b16b  mov     rax, [rcx+8]
0x14002b16f  mov     rcx, [rax]
0x14002b172  cmp     [rcx+8], rax
0x14002b176  jnz     loc_14002B4E3
0x14002b17c  mov     [rsi], rcx
0x14002b17f  mov     [rsi+8], rax
0x14002b183  mov     [rcx+8], rsi
0x14002b187  mov     [rax], rsi
0x14002b18a  jmp     short loc_14002B166
0x14002b18c  test    r14, r14
0x14002b18f  jz      short loc_14002B1B4
0x14002b191  mov     rax, [rbp+57h+var_50]
0x14002b195  lea     rcx, [rbp+57h+var_58]
0x14002b199  cmp     [rax], rcx
0x14002b19c  jnz     loc_14002B4E3
0x14002b1a2  mov     [r14+8], rax
0x14002b1a6  lea     rcx, [rbp+57h+var_58]
0x14002b1aa  mov     [r14], rcx
0x14002b1ad  mov     [rax], r14
0x14002b1b0  mov     [rbp+57h+var_50], r14
0x14002b1b4  mov     rbx, [rbp+57h+var_58]
0x14002b1b8  lea     rax, [rbp+57h+var_58]
0x14002b1bc  cmp     rbx, rax
0x14002b1bf  jz      loc_14002B283
0x14002b1c5  mov     rcx, [rbx+10h]
0x14002b1c9  lea     rdx, [rbx+18h]
0x14002b1cd  mov     r8b, 1
0x14002b1d0  call    FvepAcquireDevFveLock
0x14002b1d5  mov     rcx, [rbx+10h]
0x14002b1d9  call    FveRundownAllReadsAndWrites
0x14002b1de  mov     rax, [rbx+10h]
0x14002b1e2  cmp     qword ptr [rax+7E0h], 0
0x14002b1ea  jnz     short loc_14002B1FA
0x14002b1ec  cmp     qword ptr [rax+7E8h], 0
0x14002b1f4  jnz     short loc_14002B1FA
0x14002b1f6  xor     ecx, ecx
0x14002b1f8  jmp     short loc_14002B1FF
0x14002b1fa  mov     ecx, 1
0x14002b1ff  mov     [rbx+270h], ecx
0x14002b205  mov     rdx, [rax+7E0h]
0x14002b20c  test    rdx, rdx
0x14002b20f  jz      short loc_14002B229
0x14002b211  cmp     rdx, [rdi+2428h]
0x14002b218  jnz     short loc_14002B229
0x14002b21a  test    ecx, ecx
0x14002b21c  jz      short loc_14002B25E
0x14002b21e  mov     qword ptr [rax+7E0h], 0
0x14002b229  mov     rcx, [rbx+10h]
0x14002b22d  mov     rax, [rcx+7E8h]
0x14002b234  test    rax, rax
0x14002b237  jz      short loc_14002B256
0x14002b239  cmp     rax, [rdi+2430h]
0x14002b240  jnz     short loc_14002B256
0x14002b242  cmp     dword ptr [rbx+270h], 0
0x14002b249  jz      short loc_14002B25E
0x14002b24b  mov     qword ptr [rcx+7E8h], 0
0x14002b256  mov     rbx, [rbx]
0x14002b259  jmp     loc_14002B1B8
0x14002b25e  xor     r9d, r9d; BugCheckParameter3
0x14002b261  mov     [rsp+0C0h+Timeout], 0; BugCheckParameter4
0x14002b26a  xor     r8d, r8d; BugCheckParameter2
0x14002b26d  mov     ecx, 120h; BugCheckCode
0x14002b272  lea     edx, [r9+0Ch]; BugCheckParameter1
0x14002b276  call    cs:__imp_KeBugCheckEx
0x14002b283  test    sil, sil
0x14002b286  jz      short loc_14002B2BC
0x14002b288  mov     r14d, [rbp+57h+arg_8]
0x14002b28c  mov     eax, [rdi+r14*4+55Ch]
0x14002b294  mov     [rdi+0F5Ch], eax
0x14002b29a  mov     eax, [rdi+r14*4+568h]
0x14002b2a2  mov     [rdi+1C14h], eax
0x14002b2a8  mov     rax, [rbp+57h+var_60]
0x14002b2ac  xchg    r15, [rdi+2428h]
0x14002b2b3  xchg    rax, [rdi+2430h]
0x14002b2ba  jmp     short loc_14002B2C0
0x14002b2bc  mov     r14d, [rbp+57h+arg_8]
0x14002b2c0  mov     rbx, [rbp+57h+var_58]
0x14002b2c4  lea     rax, [rbp+57h+var_58]
0x14002b2c8  cmp     rbx, rax
0x14002b2cb  jz      loc_14002B470
0x14002b2d1  mov     r13d, 7E0h
0x14002b2d7  cmp     dword ptr [rbx+270h], 0
0x14002b2de  jz      loc_14002B460
0x14002b2e4  mov     rcx, [rbx+10h]
0x14002b2e8  mov     esi, r14d
0x14002b2eb  mov     eax, [rcx+rsi*4+638h]
0x14002b2f2  cmp     eax, [rdi+rsi*4+3A8h]
0x14002b2f9  jz      loc_14002B39E
0x14002b2ff  mov     edx, eax; Length
0x14002b301  xor     ecx, ecx; Base
0x14002b303  call    cs:__imp_MmSizeOfMdl
0x14002b30a  nop     dword ptr [rax+rax+00h]
0x14002b30f  mov     rcx, [rbx+10h]
0x14002b313  xor     r8d, r8d; Free
0x14002b316  mov     [rsp+0C0h+Depth], r8w; Depth
0x14002b31c  mov     r9d, 200h; Flags
0x14002b322  mov     [rsp+0C0h+Tag], 70455646h; Tag
0x14002b32a  mov     edx, [rcx+rsi*4+638h]
0x14002b331  lea     ecx, [rax+40h]
0x14002b334  add     ecx, edx
0x14002b336  xor     edx, edx; Allocate
0x14002b338  mov     [rsp+0C0h+Timeout], rcx; Size
0x14002b33d  mov     rcx, [rbx+250h]; Lookaside
0x14002b344  call    cs:__imp_ExInitializeNPagedLookasideList
0x14002b34b  nop     dword ptr [rax+rax+00h]
0x14002b350  mov     rcx, [rbx+250h]
0x14002b357  mov     rax, [rbx+10h]
0x14002b35b  xchg    rcx, [rax+r13]; Lookaside
0x14002b35f  mov     [rbx+250h], rcx
0x14002b366  cmp     rcx, [rdi+2428h]
0x14002b36d  jnz     short loc_14002B37C
0x14002b36f  mov     qword ptr [rbx+250h], 0
0x14002b37a  jmp     short loc_14002B38D
0x14002b37c  test    rcx, rcx
0x14002b37f  jz      short loc_14002B38D
  ... truncated ...
```
