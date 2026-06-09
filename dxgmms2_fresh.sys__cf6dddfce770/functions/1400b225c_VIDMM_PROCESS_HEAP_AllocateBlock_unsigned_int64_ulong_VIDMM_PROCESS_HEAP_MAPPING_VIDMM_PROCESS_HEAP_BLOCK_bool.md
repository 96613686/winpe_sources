# VIDMM_PROCESS_HEAP::AllocateBlock(unsigned __int64,ulong,VIDMM_PROCESS_HEAP_MAPPING,_VIDMM_PROCESS_HEAP_BLOCK * *,bool)

- ea: `0x1400b225c`
- end: `0x1400b28ff`
- name: `?AllocateBlock@VIDMM_PROCESS_HEAP@@AEAAJ_KKW4VIDMM_PROCESS_HEAP_MAPPING@@PEAPEAU_VIDMM_PROCESS_HEAP_BLOCK@@_N@Z`
- size: `1699`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1400b02e4`

## callees

- `0x140003490`
- `0x140004268`
- `0x14002e6c0`
- `0x14002f7d0`
- `0x14003a8dc`
- `0x140049794`
- `0x140059030`
- `0x1400b225c`
- `0x1400b2908`
- `0x1400deb34`
- `0x1400df33c`
- `0x1400fc094`

## import_xrefs

- `ntoskrnl!MmSecureVirtualMemory` at `0x1400b23dc`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1400b23dc`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1400b284c`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1400b284c`
- `ntoskrnl!ObfReferenceObject` at `0x1400b24c0`
- `ntoskrnl!ObfReferenceObject` at `0x1400b24c0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b28c2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b28c2`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1400b288d`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1400b288d`
- `ntoskrnl!MmCreateSection` at `0x1400b2459`
- `ntoskrnl!MmCreateSection` at `0x1400b2459`
- `ntoskrnl!ObCloseHandle` at `0x1400b28b2`
- `ntoskrnl!ObCloseHandle` at `0x1400b28b2`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1400b2559`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1400b2559`
- `ntoskrnl!ObInsertObject` at `0x1400b24e6`
- `ntoskrnl!ObInsertObject` at `0x1400b24e6`
- `watchdog!WdLogSingleEntry2` at `0x1400b2505`
- `watchdog!WdLogSingleEntry2` at `0x1400b2505`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b26f6`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b26f6`
- `watchdog!WdLogSingleEntry0` at `0x1400b23f8`
- `watchdog!WdLogSingleEntry0` at `0x1400b247b`
- `watchdog!WdLogSingleEntry0` at `0x1400b2674`
- `watchdog!WdLogSingleEntry0` at `0x1400b27e7`
- `watchdog!WdLogSingleEntry0` at `0x1400b23f8`
- `watchdog!WdLogSingleEntry0` at `0x1400b247b`
- `watchdog!WdLogSingleEntry0` at `0x1400b2674`
- `watchdog!WdLogSingleEntry0` at `0x1400b27e7`
- `watchdog!WdLogSingleEntry1` at `0x1400b2384`
- `watchdog!WdLogSingleEntry1` at `0x1400b257b`
- `watchdog!WdLogSingleEntry1` at `0x1400b2614`
- `watchdog!WdLogSingleEntry1` at `0x1400b2384`
- `watchdog!WdLogSingleEntry1` at `0x1400b257b`
- `watchdog!WdLogSingleEntry1` at `0x1400b2614`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b26ea`

## pseudocode

```c
__int64 __fastcall VIDMM_PROCESS_HEAP::AllocateBlock(
        __int64 a1,
        SIZE_T a2,
        unsigned int a3,
        unsigned int a4,
        _QWORD *a5,
        char a6)
{
  unsigned int v6; // r12d
  unsigned __int64 v9; // rcx
  SIZE_T v10; // rcx
  VIDMM_LINEAR_POOL *v11; // r14
  unsigned int v12; // ebx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdi
  int v16; // ecx
  int v17; // r8d
  int v18; // eax
  int v19; // eax
  int v20; // ecx
  int v21; // r8d
  const wchar_t *v22; // r9
  NTSTATUS inserted; // eax
  int v24; // ecx
  int v25; // r8d
  NTSTATUS v26; // eax
  VIDMM_LINEAR_POOL *v27; // rax
  VIDMM_LINEAR_POOL *v28; // rax
  int v29; // eax
  __int64 v30; // rax
  __int64 v31; // rdx
  int v32; // r8d
  _QWORD *v33; // rsi
  int v34; // ecx
  int v35; // r8d
  __int64 v36; // rax
  const wchar_t *v37; // r9
  __int64 v38; // rcx
  int v39; // ebx
  _QWORD *v40; // rax
  __int64 v41; // rcx
  int v42; // r9d
  __int64 BlockListHead; // rax
  __int64 v44; // rdx
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *VirtualMemoryInterface; // rax
  __int64 NewObject; // [rsp+20h] [rbp-59h]
  PVOID Object; // [rsp+50h] [rbp-29h] BYREF
  SIZE_T Size; // [rsp+58h] [rbp-21h] BYREF
  HANDLE SecureHandle; // [rsp+60h] [rbp-19h]
  HANDLE Handle; // [rsp+68h] [rbp-11h] BYREF
  SIZE_T v52[10]; // [rsp+70h] [rbp-9h] BYREF
  PVOID Address; // [rsp+D8h] [rbp+5Fh] BYREF

  v6 = 0;
  Address = 0;
  v9 = a2 + a3;
  SecureHandle = 0;
  Object = 0;
  if ( v9 <= (unsigned int)dword_14008742C )
    v9 = (unsigned int)dword_14008742C;
  Handle = 0;
  *a5 = 0;
  v10 = (v9 + 4095) & 0xFFFFFFFFFFFFF000uLL;
  v11 = 0;
  Size = v10;
  if ( v10 < a2 )
    goto LABEL_57;
  switch ( a4 )
  {
    case 3u:
      goto LABEL_23;
    case 4u:
LABEL_22:
      v18 = 134479872;
      goto LABEL_24;
    case 5u:
LABEL_23:
      v18 = 1208221696;
LABEL_24:
      v19 = *(_DWORD *)(a1 + 288) | v18;
      v52[0] = v10;
      LODWORD(v15) = MmCreateSection(&Object, 0, 0, v52, 4, v19, -1, 0);
      if ( (int)v15 >= 0 )
      {
        ObfReferenceObject(Object);
        inserted = ObInsertObject(Object, 0, 0, 0, 0, &Handle);
        v15 = inserted;
        if ( inserted < 0 )
        {
          WdLogSingleEntry2(1, Object, inserted);
          WdLogGlobalForLineNumber = 1959;
          DxgkLogInternalTriageEvent(
            v24,
            0x40000,
            v25,
            (unsigned int)L"Unable to insert section object 0x%I64p into handle table, Status = 0x%I64p",
            (__int64)Object,
            v15,
            0,
            0);
          goto LABEL_58;
        }
        if ( a4 - 5 > 1 || (v26 = MmMapViewInSystemSpace(Object, &Address, &Size), v15 = v26, v26 >= 0) )
        {
          v12 = 0;
          goto LABEL_33;
        }
        _InterlockedIncrement(&dword_1400877AC);
        WdLogSingleEntry1(6, v26);
        v22 = L"Failed VA mapping. Status = 0x%I64x\n";
        NewObject = v15;
        WdLogGlobalForLineNumber = 1972;
      }
      else
      {
        Object = 0;
        _InterlockedIncrement(&dword_1400877B0);
        WdLogSingleEntry0(6);
        v22 = L"Couldn't allocate a backing section for a large allocation";
        WdLogGlobalForLineNumber = 1939;
        NewObject = 1939;
      }
LABEL_26:
      DxgkLogInternalTriageEvent(v20, 262145, v21, (_DWORD)v22, NewObject, 0, 0, 0);
LABEL_58:
      if ( a4 != 3 && a4 != 4 )
      {
        if ( a4 != 5 && a4 != 6 )
          goto LABEL_62;
        if ( Address )
          MmUnmapViewInSystemSpace(Address);
      }
      if ( Object )
      {
        if ( Handle )
          ObCloseHandle(Handle, ((unsigned __int64)Handle & 0xFFFFFFFF80000000uLL) == 0);
        ObfDereferenceObject(Object);
      }
      goto LABEL_72;
    case 6u:
      goto LABEL_22;
  }
  v6 = 4;
  v12 = 8400896;
  if ( a4 != 2 )
    v6 = 1028;
  v13 = 12288;
  if ( a4 != 2 )
    v13 = 8400896;
  if ( !a6 )
    v12 = v13;
  if ( dword_1400872B8 )
    v12 &= ~0x1000u;
  if ( (int)VidMmAllocateVirtualMemory(&Address, &Size, v12, v6, *(_DWORD *)(a1 + 288)) < 0 )
  {
    v12 &= ~0x800000u;
    v14 = VidMmAllocateVirtualMemory(&Address, &Size, v12, v6, *(_DWORD *)(a1 + 288));
    v15 = v14;
    if ( v14 < 0 )
    {
      Address = 0;
      _InterlockedIncrement(&dword_1400876E8);
      WdLogSingleEntry1(6, v14);
      WdLogGlobalForLineNumber = 2019;
      DxgkLogInternalTriageEvent(
        v16,
        262145,
        v17,
        (unsigned int)L"Couldn't allocate virtual memory range for the block. Status 0x%08X.\n",
        v15,
        0,
        0,
        0);
LABEL_62:
      if ( SecureHandle )
        MmUnsecureVirtualMemory(SecureHandle);
      if ( Address )
      {
        VirtualMemoryInterface = DxgkGetVirtualMemoryInterface();
        (*((void (__fastcall **)(__int64, PVOID *, SIZE_T *, __int64))VirtualMemoryInterface + 2))(
          -1,
          &Address,
          &Size,
          0x8000);
        Address = 0;
      }
LABEL_72:
      if ( v11 )
        VIDMM_LINEAR_POOL::`scalar deleting destructor'(v11, a2);
      return (unsigned int)v15;
    }
  }
  if ( (v12 & 0x1000) != 0 )
  {
    SecureHandle = MmSecureVirtualMemory(Address, Size, 4u);
    if ( !SecureHandle )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 2040;
      LODWORD(v15) = -1073741801;
      goto LABEL_62;
    }
  }
LABEL_33:
  v27 = (VIDMM_LINEAR_POOL *)operator new(320, 925985110, 64);
  if ( !v27 || (v28 = VIDMM_LINEAR_POOL::VIDMM_LINEAR_POOL(v27, 0), (v11 = v28) == 0) )
  {
    _InterlockedIncrement(&dword_1400876EC);
    WdLogSingleEntry0(6);
    v36 = 2055;
    v37 = L"Couldn't allocate memory for VIDMM_LINEAR_POOL structure.\n";
    goto LABEL_56;
  }
  v29 = VIDMM_LINEAR_POOL::Init(v28, Size, 0, 0, 0);
  v15 = v29;
  if ( v29 < 0 )
  {
    _InterlockedIncrement(&dword_1400876F0);
    WdLogSingleEntry1(6, v29);
    WdLogGlobalForLineNumber = 2065;
    v22 = L"Couldn't initialized pool for process heap block, Status = 0x%08X.\n";
    NewObject = v15;
    goto LABEL_26;
  }
  v30 = operator new(104, 825321814, 256);
  v33 = (_QWORD *)v30;
  if ( !v30 )
  {
    _InterlockedIncrement(&dword_1400876F4);
    WdLogSingleEntry0(6);
    v36 = 2077;
    v37 = L"Couldn't allocate memory for VIDMM_PROCESS_HEAP_BLOCK() structure.\n";
LABEL_56:
    WdLogGlobalForLineNumber = v36;
    DxgkLogInternalTriageEvent(v34, 262145, v35, (_DWORD)v37, v36, 0, 0, 0);
LABEL_57:
    LODWORD(v15) = -1073741801;
    goto LABEL_58;
  }
  *(_QWORD *)v30 = a1;
  v38 = 2;
  *(_DWORD *)(v30 + 24) = 0;
  *(_QWORD *)(v30 + 32) = Address;
  *(_QWORD *)(v30 + 40) = Size;
  v39 = (v12 >> 23) & 1;
  *(_DWORD *)(v30 + 48) = v6;
  *(_QWORD *)(v30 + 72) = v11;
  *(_DWORD *)(v30 + 80) = a4;
  if ( a4 != 2 )
    v38 = 0;
  *(_QWORD *)(v30 + 56) = SecureHandle;
  *(_DWORD *)(v30 + 64) = v38 | v39;
  *(_QWORD *)(v30 + 88) = Object;
  *(_QWORD *)(v30 + 96) = Handle;
  if ( g_IsInternalReleaseOrDbg )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace(v38, v31) + 24) = v30;
    WdLogGlobalForLineNumber = 2101;
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 192LL) += v33[5];
  ++*(_DWORD *)(*(_QWORD *)(a1 + 8) + 200LL);
  v40 = *(_QWORD **)(a1 + 8);
  v41 = v33[5];
  if ( a4 == 1 )
  {
    v40[27] += v41;
  }
  else if ( a4 == 2 )
  {
    v40[29] += v41;
  }
  else
  {
    v40[31] += v41;
  }
  if ( (byte_140087202 & 4) != 0 )
  {
    v42 = (int)Address;
    if ( a4 - 3 <= 3 )
      v42 = (int)Object;
    McTemplateK0pxqqt_EtwWriteTransfer(
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24LL),
      (unsigned int)&EventCreateProcessAllocation,
      v32,
      v42,
      Size,
      a4,
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24LL),
      1);
  }
  BlockListHead = VIDMM_PROCESS_HEAP::GetBlockListHead(a1, a4);
  v44 = *(_QWORD *)BlockListHead;
  if ( *(_QWORD *)(*(_QWORD *)BlockListHead + 8LL) != BlockListHead )
    __fastfail(3u);
  v33[1] = v44;
  v33[2] = BlockListHead;
  *(_QWORD *)(v44 + 8) = v33 + 1;
  *(_QWORD *)BlockListHead = v33 + 1;
  *a5 = v33;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400b225c  push    rbp
0x1400b225e  push    rbx
0x1400b225f  push    rsi
0x1400b2260  push    rdi
0x1400b2261  push    r12
0x1400b2263  push    r13
0x1400b2265  push    r14
0x1400b2267  push    r15
0x1400b2269  lea     rbp, [rsp-0Fh]
0x1400b226e  sub     rsp, 88h
0x1400b2275  mov     rax, [rbp+47h+arg_20]
0x1400b2279  xor     r12d, r12d
0x1400b227c  mov     r13, rcx
0x1400b227f  mov     [rbp+47h+Address], r12
0x1400b2283  mov     ecx, r8d
0x1400b2286  mov     r15d, r9d
0x1400b2289  mov     r9d, cs:dword_14008742C
0x1400b2290  add     rcx, rdx
0x1400b2293  cmp     rcx, r9
0x1400b2296  mov     [rbp+47h+SecureHandle], r12
0x1400b229a  mov     esi, r12d
0x1400b229d  mov     [rbp+47h+Object], r12
0x1400b22a1  cmovbe  rcx, r9
0x1400b22a5  mov     [rbp+47h+var_58], r12
0x1400b22a9  add     rcx, 0FFFh
0x1400b22b0  mov     [rax], r12
0x1400b22b3  and     rcx, 0FFFFFFFFFFFFF000h
0x1400b22ba  mov     r14d, r12d
0x1400b22bd  mov     [rbp+47h+Size], rcx
0x1400b22c1  cmp     rcx, rdx
0x1400b22c4  jb      loc_1400B2823
0x1400b22ca  cmp     r15d, 3
0x1400b22ce  jz      loc_1400B2422
0x1400b22d4  cmp     r15d, 4
0x1400b22d8  jz      loc_1400B241B
0x1400b22de  cmp     r15d, 5
0x1400b22e2  jz      loc_1400B2422
0x1400b22e8  cmp     r15d, 6
0x1400b22ec  jz      loc_1400B241B
0x1400b22f2  cmp     r15d, 2
0x1400b22f6  lea     r12d, [r14+4]
0x1400b22fa  mov     eax, 404h
0x1400b22ff  mov     ebx, 803000h
0x1400b2304  cmovnz  r12d, eax
0x1400b2308  mov     eax, 3000h
0x1400b230d  cmovnz  eax, ebx
0x1400b2310  cmp     [rbp+47h+arg_28], sil
0x1400b2314  cmovz   ebx, eax
0x1400b2317  cmp     cs:dword_1400872B8, esi
0x1400b231d  jz      short loc_1400B2323
0x1400b231f  btr     ebx, 0Ch
0x1400b2323  mov     eax, [r13+120h]
0x1400b232a  lea     rdx, [rbp+47h+Size]; unsigned __int64 *
0x1400b232e  mov     r9d, r12d; unsigned int
0x1400b2331  mov     dword ptr [rsp+0C0h+NewObject], eax; unsigned int
0x1400b2335  mov     r8d, ebx; unsigned int
0x1400b2338  lea     rcx, [rbp+47h+Address]; void **
0x1400b233c  call    ?VidMmAllocateVirtualMemory@@YAJPEAPEAXPEA_KKKK@Z; VidMmAllocateVirtualMemory(void * *,unsigned __int64 *,ulong,ulong,ulong)
0x1400b2341  test    eax, eax
0x1400b2343  jns     short loc_1400B23C4
0x1400b2345  mov     eax, [r13+120h]
0x1400b234c  lea     rdx, [rbp+47h+Size]; unsigned __int64 *
0x1400b2350  btr     ebx, 17h
0x1400b2354  mov     dword ptr [rsp+0C0h+NewObject], eax; unsigned int
0x1400b2358  mov     r8d, ebx; unsigned int
0x1400b235b  lea     rcx, [rbp+47h+Address]; void **
0x1400b235f  mov     r9d, r12d; unsigned int
0x1400b2362  call    ?VidMmAllocateVirtualMemory@@YAJPEAPEAXPEA_KKKK@Z; VidMmAllocateVirtualMemory(void * *,unsigned __int64 *,ulong,ulong,ulong)
0x1400b2367  movsxd  rdi, eax
0x1400b236a  test    eax, eax
0x1400b236c  jns     short loc_1400B23C4
0x1400b236e  xor     r12d, r12d
0x1400b2371  mov     [rbp+47h+Address], r12
0x1400b2375  lock inc cs:dword_1400876E8
0x1400b237c  mov     rdx, rdi
0x1400b237f  lea     ecx, [r12+6]
0x1400b2384  call    cs:__imp_WdLogSingleEntry1
0x1400b238b  nop     dword ptr [rax+rax+00h]
0x1400b2390  mov     [rsp+0C0h+var_88], r12
0x1400b2395  lea     r9, aCouldnTAllocat_42; "Couldn't allocate virtual memory range "...
0x1400b239c  mov     [rsp+0C0h+var_90], r12
0x1400b23a1  mov     edx, 40001h
0x1400b23a6  mov     [rsp+0C0h+Handle], r12
0x1400b23ab  mov     [rsp+0C0h+NewObject], rdi
0x1400b23b0  mov     cs:WdLogGlobalForLineNumber, 7E3h
0x1400b23ba  call    DxgkLogInternalTriageEvent
0x1400b23bf  jmp     loc_1400B2840
0x1400b23c4  bt      ebx, 0Ch
0x1400b23c8  jnb     loc_1400B25B3
0x1400b23ce  mov     rdx, [rbp+47h+Size]; Size
0x1400b23d2  mov     r8d, 4; ProbeMode
0x1400b23d8  mov     rcx, [rbp+47h+Address]; Address
0x1400b23dc  call    cs:__imp_MmSecureVirtualMemory
0x1400b23e3  nop     dword ptr [rax+rax+00h]
0x1400b23e8  mov     [rbp+47h+SecureHandle], rax
0x1400b23ec  test    rax, rax
0x1400b23ef  jnz     loc_1400B25B3
0x1400b23f5  lea     ecx, [rax+3]
0x1400b23f8  call    cs:__imp_WdLogSingleEntry0
0x1400b23ff  nop     dword ptr [rax+rax+00h]
0x1400b2404  xor     r12d, r12d
0x1400b2407  mov     cs:WdLogGlobalForLineNumber, 7F8h
0x1400b2411  mov     edi, 0C0000017h
0x1400b2416  jmp     loc_1400B2840
0x1400b241b  mov     eax, 8040000h
0x1400b2420  jmp     short loc_1400B2427
0x1400b2422  mov     eax, 48040000h
0x1400b2427  or      eax, [r13+120h]
0x1400b242e  lea     r9, [rbp+47h+var_50]
0x1400b2432  mov     [rsp+0C0h+var_88], r12
0x1400b2437  xor     r8d, r8d
0x1400b243a  mov     [rsp+0C0h+var_90], 0FFFFFFFFFFFFFFFFh
0x1400b2443  xor     edx, edx
0x1400b2445  mov     [rbp+47h+var_50], rcx
0x1400b2449  lea     rcx, [rbp+47h+Object]
0x1400b244d  mov     dword ptr [rsp+0C0h+Handle], eax
0x1400b2451  mov     dword ptr [rsp+0C0h+NewObject], 4
0x1400b2459  call    cs:__imp_MmCreateSection
0x1400b2460  nop     dword ptr [rax+rax+00h]
0x1400b2465  mov     edi, eax
0x1400b2467  test    eax, eax
0x1400b2469  jns     short loc_1400B24BC
0x1400b246b  mov     [rbp+47h+Object], r12
0x1400b246f  lock inc cs:dword_1400877B0
0x1400b2476  mov     ecx, 6
0x1400b247b  call    cs:__imp_WdLogSingleEntry0
0x1400b2482  nop     dword ptr [rax+rax+00h]
0x1400b2487  mov     [rsp+0C0h+var_88], r12
0x1400b248c  lea     r9, aCouldnTAllocat_5; "Couldn't allocate a backing section for"...
0x1400b2493  mov     eax, 793h
0x1400b2498  mov     [rsp+0C0h+var_90], r12
0x1400b249d  mov     [rsp+0C0h+Handle], r12
0x1400b24a2  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b24a8  mov     [rsp+0C0h+NewObject], rax
0x1400b24ad  mov     edx, 40001h
0x1400b24b2  call    DxgkLogInternalTriageEvent
0x1400b24b7  jmp     loc_1400B2828
0x1400b24bc  mov     rcx, [rbp+47h+Object]; Object
0x1400b24c0  call    cs:__imp_ObfReferenceObject
0x1400b24c7  nop     dword ptr [rax+rax+00h]
0x1400b24cc  mov     rcx, [rbp+47h+Object]; Object
0x1400b24d0  lea     rax, [rbp+47h+var_58]
0x1400b24d4  mov     [rsp+0C0h+Handle], rax; Handle
0x1400b24d9  xor     r9d, r9d; ObjectPointerBias
0x1400b24dc  xor     r8d, r8d; DesiredAccess
0x1400b24df  mov     [rsp+0C0h+NewObject], r12; NewObject
0x1400b24e4  xor     edx, edx; PassedAccessState
0x1400b24e6  call    cs:__imp_ObInsertObject
0x1400b24ed  nop     dword ptr [rax+rax+00h]
0x1400b24f2  movsxd  rdi, eax
0x1400b24f5  test    eax, eax
0x1400b24f7  jns     short loc_1400B2544
0x1400b24f9  mov     rdx, [rbp+47h+Object]
0x1400b24fd  mov     r8, rdi
0x1400b2500  mov     ecx, 1
0x1400b2505  call    cs:__imp_WdLogSingleEntry2
0x1400b250c  nop     dword ptr [rax+rax+00h]
0x1400b2511  mov     rax, [rbp+47h+Object]
0x1400b2515  lea     r9, aUnableToInsert; "Unable to insert section object 0x%I64p"...
0x1400b251c  mov     [rsp+0C0h+var_88], r12
0x1400b2521  mov     edx, 40000h
0x1400b2526  mov     [rsp+0C0h+var_90], r12
0x1400b252b  mov     [rsp+0C0h+Handle], rdi
0x1400b2530  mov     [rsp+0C0h+NewObject], rax
0x1400b2535  mov     cs:WdLogGlobalForLineNumber, 7A7h
0x1400b253f  jmp     loc_1400B24B2
0x1400b2544  lea     eax, [r15-5]
0x1400b2548  cmp     eax, 1
0x1400b254b  ja      short loc_1400B25B1
0x1400b254d  mov     rcx, [rbp+47h+Object]; Section
0x1400b2551  lea     r8, [rbp+47h+Size]; ViewSize
0x1400b2555  lea     rdx, [rbp+47h+Address]; MappedBase
0x1400b2559  call    cs:__imp_MmMapViewInSystemSpace
0x1400b2560  nop     dword ptr [rax+rax+00h]
0x1400b2565  movsxd  rdi, eax
0x1400b2568  test    eax, eax
0x1400b256a  jns     short loc_1400B25B1
0x1400b256c  lock inc cs:dword_1400877AC
0x1400b2573  mov     rdx, rdi
0x1400b2576  mov     ecx, 6
0x1400b257b  call    cs:__imp_WdLogSingleEntry1
0x1400b2582  nop     dword ptr [rax+rax+00h]
0x1400b2587  mov     [rsp+0C0h+var_88], r12
0x1400b258c  lea     r9, aFailedVaMappin; "Failed VA mapping. Status = 0x%I64x\n"
0x1400b2593  mov     [rsp+0C0h+var_90], r12
0x1400b2598  mov     [rsp+0C0h+Handle], r12
0x1400b259d  mov     [rsp+0C0h+NewObject], rdi
0x1400b25a2  mov     cs:WdLogGlobalForLineNumber, 7B4h
0x1400b25ac  jmp     loc_1400B24AD
0x1400b25b1  xor     ebx, ebx
0x1400b25b3  mov     edx, 37316956h
0x1400b25b8  mov     ecx, 140h
0x1400b25bd  mov     r8d, 40h ; '@'
0x1400b25c3  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400b25c8  test    rax, rax
0x1400b25cb  jz      loc_1400B27D8
0x1400b25d1  xor     edx, edx; void *
0x1400b25d3  mov     rcx, rax; this
0x1400b25d6  call    ??0VIDMM_LINEAR_POOL@@QEAA@PEAX@Z; VIDMM_LINEAR_POOL::VIDMM_LINEAR_POOL(void *)
0x1400b25db  mov     r14, rax
0x1400b25de  test    rax, rax
0x1400b25e1  jz      loc_1400B27D8
0x1400b25e7  mov     rdx, [rbp+47h+Size]; unsigned __int64
0x1400b25eb  xor     r9d, r9d; void (*)(void *, void *)
0x1400b25ee  xor     r8d, r8d; unsigned __int8
0x1400b25f1  mov     [rsp+0C0h+NewObject], rsi; bool (*)(void *)
0x1400b25f6  mov     rcx, rax; this
0x1400b25f9  call    ?Init@VIDMM_LINEAR_POOL@@QEAAJ_KEP6AXPEAX1@ZP6A_N1@Z@Z; VIDMM_LINEAR_POOL::Init(unsigned __int64,uchar,void (*)(void *,void *),bool (*)(void *))
0x1400b25fe  movsxd  rdi, eax
0x1400b2601  test    eax, eax
0x1400b2603  jns     short loc_1400B264D
0x1400b2605  lock inc cs:dword_1400876F0
0x1400b260c  mov     rdx, rdi
0x1400b260f  mov     ecx, 6
0x1400b2614  call    cs:__imp_WdLogSingleEntry1
0x1400b261b  nop     dword ptr [rax+rax+00h]
0x1400b2620  xor     r12d, r12d
0x1400b2623  mov     cs:WdLogGlobalForLineNumber, 811h
0x1400b262d  mov     [rsp+0C0h+var_88], r12
0x1400b2632  lea     r9, aCouldnTInitial_7; "Couldn't initialized pool for process h"...
0x1400b2639  mov     [rsp+0C0h+var_90], r12
0x1400b263e  mov     [rsp+0C0h+Handle], r12
0x1400b2643  mov     [rsp+0C0h+NewObject], rdi
0x1400b2648  jmp     loc_1400B24AD
0x1400b264d  mov     edx, 31316956h
0x1400b2652  mov     ecx, 68h ; 'h'
0x1400b2657  mov     r8d, 100h
0x1400b265d  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400b2662  mov     rsi, rax
0x1400b2665  test    rax, rax
0x1400b2668  jnz     short loc_1400B2694
0x1400b266a  lock inc cs:dword_1400876F4
0x1400b2671  lea     ecx, [rax+6]
0x1400b2674  call    cs:__imp_WdLogSingleEntry0
0x1400b267b  nop     dword ptr [rax+rax+00h]
0x1400b2680  mov     eax, 81Dh
0x1400b2685  lea     r9, aCouldnTAllocat_21; "Couldn't allocate memory for VIDMM_PROC"...
0x1400b268c  xor     r12d, r12d
0x1400b268f  jmp     loc_1400B27FF
0x1400b2694  mov     [rax], r13
0x1400b2697  mov     ecx, 2
0x1400b269c  mov     dword ptr [rax+18h], 0
0x1400b26a3  mov     rax, [rbp+47h+Address]
0x1400b26a7  mov     [rsi+20h], rax
0x1400b26ab  mov     rax, [rbp+47h+Size]
0x1400b26af  mov     [rsi+28h], rax
0x1400b26b3  xor     eax, eax
0x1400b26b5  shr     ebx, 17h
0x1400b26b8  and     ebx, 1
0x1400b26bb  mov     [rsi+30h], r12d
0x1400b26bf  mov     [rsi+48h], r14
0x1400b26c3  cmp     r15d, ecx
0x1400b26c6  mov     [rsi+50h], r15d
0x1400b26ca  cmovnz  ecx, eax
0x1400b26cd  mov     rax, [rbp+47h+SecureHandle]
0x1400b26d1  mov     [rsi+38h], rax
0x1400b26d5  or      ebx, ecx
0x1400b26d7  mov     [rsi+40h], ebx
0x1400b26da  mov     rax, [rbp+47h+Object]
0x1400b26de  mov     [rsi+58h], rax
0x1400b26e2  mov     rax, [rbp+47h+var_58]
0x1400b26e6  mov     [rsi+60h], rax
0x1400b26ea  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b26f1  cmp     byte ptr [rax], 0
0x1400b26f4  jz      short loc_1400B2710
0x1400b26f6  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b26fd  nop     dword ptr [rax+rax+00h]
0x1400b2702  mov     [rax+18h], rsi
0x1400b2706  mov     cs:WdLogGlobalForLineNumber, 835h
0x1400b2710  mov     rcx, [r13+8]
0x1400b2714  mov     rax, [rsi+28h]
0x1400b2718  add     [rcx+0C0h], rax
0x1400b271f  mov     rax, [r13+8]
0x1400b2723  inc     dword ptr [rax+0C8h]
0x1400b2729  mov     rax, [r13+8]
0x1400b272d  mov     rcx, [rsi+28h]
0x1400b2731  cmp     r15d, 1
0x1400b2735  jnz     short loc_1400B2740
0x1400b2737  add     [rax+0D8h], rcx
0x1400b273e  jmp     short loc_1400B2756
0x1400b2740  cmp     r15d, 2
0x1400b2744  jnz     short loc_1400B274F
0x1400b2746  add     [rax+0E8h], rcx
0x1400b274d  jmp     short loc_1400B2756
0x1400b274f  add     [rax+0F8h], rcx
0x1400b2756  test    cs:byte_140087202, 4
0x1400b275d  jz      short loc_1400B279C
0x1400b275f  mov     rax, [r13+8]
0x1400b2763  mov     rdx, [rbp+47h+Size]
0x1400b2767  mov     r9, [rbp+47h+Address]
0x1400b276b  mov     dword ptr [rsp+0C0h+var_88], 1
0x1400b2773  mov     ecx, [rax+18h]
0x1400b2776  lea     eax, [r15-3]
0x1400b277a  mov     dword ptr [rsp+0C0h+var_90], ecx
0x1400b277e  cmp     eax, 3
0x1400b2781  mov     dword ptr [rsp+0C0h+Handle], r15d
0x1400b2786  cmovbe  r9, [rbp+47h+Object]
0x1400b278b  mov     [rsp+0C0h+NewObject], rdx
0x1400b2790  lea     rdx, EventCreateProcessAllocation
0x1400b2797  call    McTemplateK0pxqqt_EtwWriteTransfer
  ... truncated ...
```
