# VIDMM_PROCESS_HEAP::AllocateBlock(unsigned __int64,ulong,VIDMM_PROCESS_HEAP_MAPPING,_VIDMM_PROCESS_HEAP_BLOCK * *,bool)

- ea: `0x1400b0d0c`
- end: `0x1400b13af`
- name: `?AllocateBlock@VIDMM_PROCESS_HEAP@@AEAAJ_KKW4VIDMM_PROCESS_HEAP_MAPPING@@PEAPEAU_VIDMM_PROCESS_HEAP_BLOCK@@_N@Z`
- size: `1699`
- prototype: `__int64 __fastcall(__int64, SIZE_T, unsigned int, unsigned int, _QWORD *, char)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1400aed94`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x140030ae0`
- `0x140031934`
- `0x14003bbcc`
- `0x1400490c8`
- `0x140058760`
- `0x1400b0d0c`
- `0x1400b13b8`
- `0x1400d66d4`
- `0x1400d6edc`
- `0x1400f70b4`

## import_xrefs

- `ntoskrnl!MmSecureVirtualMemory` at `0x1400b0e8c`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1400b0e8c`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1400b12fc`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1400b12fc`
- `ntoskrnl!ObfReferenceObject` at `0x1400b0f70`
- `ntoskrnl!ObfReferenceObject` at `0x1400b0f70`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b1372`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b1372`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1400b133d`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1400b133d`
- `ntoskrnl!MmCreateSection` at `0x1400b0f09`
- `ntoskrnl!MmCreateSection` at `0x1400b0f09`
- `ntoskrnl!ObCloseHandle` at `0x1400b1362`
- `ntoskrnl!ObCloseHandle` at `0x1400b1362`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1400b1009`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1400b1009`
- `ntoskrnl!ObInsertObject` at `0x1400b0f96`
- `ntoskrnl!ObInsertObject` at `0x1400b0f96`
- `watchdog!WdLogSingleEntry2` at `0x1400b0fb5`
- `watchdog!WdLogSingleEntry2` at `0x1400b0fb5`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b11a6`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b11a6`
- `watchdog!WdLogSingleEntry0` at `0x1400b0ea8`
- `watchdog!WdLogSingleEntry0` at `0x1400b0f2b`
- `watchdog!WdLogSingleEntry0` at `0x1400b1124`
- `watchdog!WdLogSingleEntry0` at `0x1400b1297`
- `watchdog!WdLogSingleEntry0` at `0x1400b0ea8`
- `watchdog!WdLogSingleEntry0` at `0x1400b0f2b`
- `watchdog!WdLogSingleEntry0` at `0x1400b1124`
- `watchdog!WdLogSingleEntry0` at `0x1400b1297`
- `watchdog!WdLogSingleEntry1` at `0x1400b0e34`
- `watchdog!WdLogSingleEntry1` at `0x1400b102b`
- `watchdog!WdLogSingleEntry1` at `0x1400b10c4`
- `watchdog!WdLogSingleEntry1` at `0x1400b0e34`
- `watchdog!WdLogSingleEntry1` at `0x1400b102b`
- `watchdog!WdLogSingleEntry1` at `0x1400b10c4`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b119a`

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
  int v31; // r8d
  _QWORD *v32; // rsi
  int v33; // ecx
  int v34; // r8d
  __int64 v35; // rax
  const wchar_t *v36; // r9
  int v37; // ecx
  int v38; // ebx
  _QWORD *v39; // rax
  __int64 v40; // rcx
  int v41; // r9d
  __int64 BlockListHead; // rax
  __int64 v43; // rdx
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *VirtualMemoryInterface; // rax
  __int64 NewObject; // [rsp+20h] [rbp-59h]
  PVOID Object; // [rsp+50h] [rbp-29h] BYREF
  SIZE_T Size; // [rsp+58h] [rbp-21h] BYREF
  HANDLE SecureHandle; // [rsp+60h] [rbp-19h]
  HANDLE Handle; // [rsp+68h] [rbp-11h] BYREF
  SIZE_T v51[10]; // [rsp+70h] [rbp-9h] BYREF
  PVOID Address; // [rsp+D8h] [rbp+5Fh] BYREF

  v6 = 0;
  Address = 0;
  v9 = a2 + a3;
  SecureHandle = 0;
  Object = 0;
  if ( v9 <= (unsigned int)dword_14008645C )
    v9 = (unsigned int)dword_14008645C;
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
      v51[0] = v10;
      LODWORD(v15) = MmCreateSection(&Object, 0, 0, v51, 4, v19, -1, 0);
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
        _InterlockedIncrement(&dword_1400867CC);
        WdLogSingleEntry1(6, v26);
        v22 = L"Failed VA mapping. Status = 0x%I64x\n";
        NewObject = v15;
        WdLogGlobalForLineNumber = 1972;
      }
      else
      {
        Object = 0;
        _InterlockedIncrement(&dword_1400867D0);
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
  if ( dword_1400862E8 )
    v12 &= ~0x1000u;
  if ( (int)VidMmAllocateVirtualMemory(&Address, &Size, v12, v6, *(_DWORD *)(a1 + 288)) < 0 )
  {
    v12 &= ~0x800000u;
    v14 = VidMmAllocateVirtualMemory(&Address, &Size, v12, v6, *(_DWORD *)(a1 + 288));
    v15 = v14;
    if ( v14 < 0 )
    {
      Address = 0;
      _InterlockedIncrement(&dword_140086708);
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
    _InterlockedIncrement(&dword_14008670C);
    WdLogSingleEntry0(6);
    v35 = 2055;
    v36 = L"Couldn't allocate memory for VIDMM_LINEAR_POOL structure.\n";
    goto LABEL_56;
  }
  v29 = VIDMM_LINEAR_POOL::Init(v28, Size, 0, 0, 0);
  v15 = v29;
  if ( v29 < 0 )
  {
    _InterlockedIncrement(&dword_140086710);
    WdLogSingleEntry1(6, v29);
    WdLogGlobalForLineNumber = 2065;
    v22 = L"Couldn't initialized pool for process heap block, Status = 0x%08X.\n";
    NewObject = v15;
    goto LABEL_26;
  }
  v30 = operator new(104, 825321814, 256);
  v32 = (_QWORD *)v30;
  if ( !v30 )
  {
    _InterlockedIncrement(&dword_140086714);
    WdLogSingleEntry0(6);
    v35 = 2077;
    v36 = L"Couldn't allocate memory for VIDMM_PROCESS_HEAP_BLOCK() structure.\n";
LABEL_56:
    WdLogGlobalForLineNumber = v35;
    DxgkLogInternalTriageEvent(v33, 262145, v34, (_DWORD)v36, v35, 0, 0, 0);
LABEL_57:
    LODWORD(v15) = -1073741801;
    goto LABEL_58;
  }
  *(_QWORD *)v30 = a1;
  v37 = 2;
  *(_DWORD *)(v30 + 24) = 0;
  *(_QWORD *)(v30 + 32) = Address;
  *(_QWORD *)(v30 + 40) = Size;
  v38 = (v12 >> 23) & 1;
  *(_DWORD *)(v30 + 48) = v6;
  *(_QWORD *)(v30 + 72) = v11;
  *(_DWORD *)(v30 + 80) = a4;
  if ( a4 != 2 )
    v37 = 0;
  *(_QWORD *)(v30 + 56) = SecureHandle;
  *(_DWORD *)(v30 + 64) = v37 | v38;
  *(_QWORD *)(v30 + 88) = Object;
  *(_QWORD *)(v30 + 96) = Handle;
  if ( g_IsInternalReleaseOrDbg )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace() + 24) = v30;
    WdLogGlobalForLineNumber = 2101;
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 184LL) += v32[5];
  ++*(_DWORD *)(*(_QWORD *)(a1 + 8) + 192LL);
  v39 = *(_QWORD **)(a1 + 8);
  v40 = v32[5];
  if ( a4 == 1 )
  {
    v39[26] += v40;
  }
  else if ( a4 == 2 )
  {
    v39[28] += v40;
  }
  else
  {
    v39[30] += v40;
  }
  if ( (byte_140086202 & 4) != 0 )
  {
    v41 = (int)Address;
    if ( a4 - 3 <= 3 )
      v41 = (int)Object;
    McTemplateK0pxqqt_EtwWriteTransfer(
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24LL),
      (unsigned int)EventCreateProcessAllocation,
      v31,
      v41,
      Size,
      a4,
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24LL),
      1);
  }
  BlockListHead = VIDMM_PROCESS_HEAP::GetBlockListHead(a1, a4);
  v43 = *(_QWORD *)BlockListHead;
  if ( *(_QWORD *)(*(_QWORD *)BlockListHead + 8LL) != BlockListHead )
    __fastfail(3u);
  v32[1] = v43;
  v32[2] = BlockListHead;
  *(_QWORD *)(v43 + 8) = v32 + 1;
  *(_QWORD *)BlockListHead = v32 + 1;
  *a5 = v32;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400b0d0c  push    rbp
0x1400b0d0e  push    rbx
0x1400b0d0f  push    rsi
0x1400b0d10  push    rdi
0x1400b0d11  push    r12
0x1400b0d13  push    r13
0x1400b0d15  push    r14
0x1400b0d17  push    r15
0x1400b0d19  lea     rbp, [rsp-0Fh]
0x1400b0d1e  sub     rsp, 88h
0x1400b0d25  mov     rax, [rbp+47h+arg_20]
0x1400b0d29  xor     r12d, r12d
0x1400b0d2c  mov     r13, rcx
0x1400b0d2f  mov     [rbp+47h+Address], r12
0x1400b0d33  mov     ecx, r8d
0x1400b0d36  mov     r15d, r9d
0x1400b0d39  mov     r9d, cs:dword_14008645C
0x1400b0d40  add     rcx, rdx
0x1400b0d43  cmp     rcx, r9
0x1400b0d46  mov     [rbp+47h+SecureHandle], r12
0x1400b0d4a  mov     esi, r12d
0x1400b0d4d  mov     [rbp+47h+Object], r12
0x1400b0d51  cmovbe  rcx, r9
0x1400b0d55  mov     [rbp+47h+var_58], r12
0x1400b0d59  add     rcx, 0FFFh
0x1400b0d60  mov     [rax], r12
0x1400b0d63  and     rcx, 0FFFFFFFFFFFFF000h
0x1400b0d6a  mov     r14d, r12d
0x1400b0d6d  mov     [rbp+47h+Size], rcx
0x1400b0d71  cmp     rcx, rdx
0x1400b0d74  jb      loc_1400B12D3
0x1400b0d7a  cmp     r15d, 3
0x1400b0d7e  jz      loc_1400B0ED2
0x1400b0d84  cmp     r15d, 4
0x1400b0d88  jz      loc_1400B0ECB
0x1400b0d8e  cmp     r15d, 5
0x1400b0d92  jz      loc_1400B0ED2
0x1400b0d98  cmp     r15d, 6
0x1400b0d9c  jz      loc_1400B0ECB
0x1400b0da2  cmp     r15d, 2
0x1400b0da6  lea     r12d, [r14+4]
0x1400b0daa  mov     eax, 404h
0x1400b0daf  mov     ebx, 803000h
0x1400b0db4  cmovnz  r12d, eax
0x1400b0db8  mov     eax, 3000h
0x1400b0dbd  cmovnz  eax, ebx
0x1400b0dc0  cmp     [rbp+47h+arg_28], sil
0x1400b0dc4  cmovz   ebx, eax
0x1400b0dc7  cmp     cs:dword_1400862E8, esi
0x1400b0dcd  jz      short loc_1400B0DD3
0x1400b0dcf  btr     ebx, 0Ch
0x1400b0dd3  mov     eax, [r13+120h]
0x1400b0dda  lea     rdx, [rbp+47h+Size]; unsigned __int64 *
0x1400b0dde  mov     r9d, r12d; unsigned int
0x1400b0de1  mov     dword ptr [rsp+0C0h+NewObject], eax; unsigned int
0x1400b0de5  mov     r8d, ebx; unsigned int
0x1400b0de8  lea     rcx, [rbp+47h+Address]; void **
0x1400b0dec  call    ?VidMmAllocateVirtualMemory@@YAJPEAPEAXPEA_KKKK@Z; VidMmAllocateVirtualMemory(void * *,unsigned __int64 *,ulong,ulong,ulong)
0x1400b0df1  test    eax, eax
0x1400b0df3  jns     short loc_1400B0E74
0x1400b0df5  mov     eax, [r13+120h]
0x1400b0dfc  lea     rdx, [rbp+47h+Size]; unsigned __int64 *
0x1400b0e00  btr     ebx, 17h
0x1400b0e04  mov     dword ptr [rsp+0C0h+NewObject], eax; unsigned int
0x1400b0e08  mov     r8d, ebx; unsigned int
0x1400b0e0b  lea     rcx, [rbp+47h+Address]; void **
0x1400b0e0f  mov     r9d, r12d; unsigned int
0x1400b0e12  call    ?VidMmAllocateVirtualMemory@@YAJPEAPEAXPEA_KKKK@Z; VidMmAllocateVirtualMemory(void * *,unsigned __int64 *,ulong,ulong,ulong)
0x1400b0e17  movsxd  rdi, eax
0x1400b0e1a  test    eax, eax
0x1400b0e1c  jns     short loc_1400B0E74
0x1400b0e1e  xor     r12d, r12d
0x1400b0e21  mov     [rbp+47h+Address], r12
0x1400b0e25  lock inc cs:dword_140086708
0x1400b0e2c  mov     rdx, rdi
0x1400b0e2f  lea     ecx, [r12+6]
0x1400b0e34  call    cs:__imp_WdLogSingleEntry1
0x1400b0e3b  nop     dword ptr [rax+rax+00h]
0x1400b0e40  mov     [rsp+0C0h+var_88], r12
0x1400b0e45  lea     r9, aCouldnTAllocat_40; "Couldn't allocate virtual memory range "...
0x1400b0e4c  mov     [rsp+0C0h+var_90], r12
0x1400b0e51  mov     edx, 40001h
0x1400b0e56  mov     [rsp+0C0h+Handle], r12
0x1400b0e5b  mov     [rsp+0C0h+NewObject], rdi
0x1400b0e60  mov     cs:WdLogGlobalForLineNumber, 7E3h
0x1400b0e6a  call    DxgkLogInternalTriageEvent
0x1400b0e6f  jmp     loc_1400B12F0
0x1400b0e74  bt      ebx, 0Ch
0x1400b0e78  jnb     loc_1400B1063
0x1400b0e7e  mov     rdx, [rbp+47h+Size]; Size
0x1400b0e82  mov     r8d, 4; ProbeMode
0x1400b0e88  mov     rcx, [rbp+47h+Address]; Address
0x1400b0e8c  call    cs:__imp_MmSecureVirtualMemory
0x1400b0e93  nop     dword ptr [rax+rax+00h]
0x1400b0e98  mov     [rbp+47h+SecureHandle], rax
0x1400b0e9c  test    rax, rax
0x1400b0e9f  jnz     loc_1400B1063
0x1400b0ea5  lea     ecx, [rax+3]
0x1400b0ea8  call    cs:__imp_WdLogSingleEntry0
0x1400b0eaf  nop     dword ptr [rax+rax+00h]
0x1400b0eb4  xor     r12d, r12d
0x1400b0eb7  mov     cs:WdLogGlobalForLineNumber, 7F8h
0x1400b0ec1  mov     edi, 0C0000017h
0x1400b0ec6  jmp     loc_1400B12F0
0x1400b0ecb  mov     eax, 8040000h
0x1400b0ed0  jmp     short loc_1400B0ED7
0x1400b0ed2  mov     eax, 48040000h
0x1400b0ed7  or      eax, [r13+120h]
0x1400b0ede  lea     r9, [rbp+47h+var_50]
0x1400b0ee2  mov     [rsp+0C0h+var_88], r12
0x1400b0ee7  xor     r8d, r8d
0x1400b0eea  mov     [rsp+0C0h+var_90], 0FFFFFFFFFFFFFFFFh
0x1400b0ef3  xor     edx, edx
0x1400b0ef5  mov     [rbp+47h+var_50], rcx
0x1400b0ef9  lea     rcx, [rbp+47h+Object]
0x1400b0efd  mov     dword ptr [rsp+0C0h+Handle], eax
0x1400b0f01  mov     dword ptr [rsp+0C0h+NewObject], 4
0x1400b0f09  call    cs:__imp_MmCreateSection
0x1400b0f10  nop     dword ptr [rax+rax+00h]
0x1400b0f15  mov     edi, eax
0x1400b0f17  test    eax, eax
0x1400b0f19  jns     short loc_1400B0F6C
0x1400b0f1b  mov     [rbp+47h+Object], r12
0x1400b0f1f  lock inc cs:dword_1400867D0
0x1400b0f26  mov     ecx, 6
0x1400b0f2b  call    cs:__imp_WdLogSingleEntry0
0x1400b0f32  nop     dword ptr [rax+rax+00h]
0x1400b0f37  mov     [rsp+0C0h+var_88], r12
0x1400b0f3c  lea     r9, aCouldnTAllocat_5; "Couldn't allocate a backing section for"...
0x1400b0f43  mov     eax, 793h
0x1400b0f48  mov     [rsp+0C0h+var_90], r12
0x1400b0f4d  mov     [rsp+0C0h+Handle], r12
0x1400b0f52  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b0f58  mov     [rsp+0C0h+NewObject], rax
0x1400b0f5d  mov     edx, 40001h
0x1400b0f62  call    DxgkLogInternalTriageEvent
0x1400b0f67  jmp     loc_1400B12D8
0x1400b0f6c  mov     rcx, [rbp+47h+Object]; Object
0x1400b0f70  call    cs:__imp_ObfReferenceObject
0x1400b0f77  nop     dword ptr [rax+rax+00h]
0x1400b0f7c  mov     rcx, [rbp+47h+Object]; Object
0x1400b0f80  lea     rax, [rbp+47h+var_58]
0x1400b0f84  mov     [rsp+0C0h+Handle], rax; Handle
0x1400b0f89  xor     r9d, r9d; ObjectPointerBias
0x1400b0f8c  xor     r8d, r8d; DesiredAccess
0x1400b0f8f  mov     [rsp+0C0h+NewObject], r12; NewObject
0x1400b0f94  xor     edx, edx; PassedAccessState
0x1400b0f96  call    cs:__imp_ObInsertObject
0x1400b0f9d  nop     dword ptr [rax+rax+00h]
0x1400b0fa2  movsxd  rdi, eax
0x1400b0fa5  test    eax, eax
0x1400b0fa7  jns     short loc_1400B0FF4
0x1400b0fa9  mov     rdx, [rbp+47h+Object]
0x1400b0fad  mov     r8, rdi
0x1400b0fb0  mov     ecx, 1
0x1400b0fb5  call    cs:__imp_WdLogSingleEntry2
0x1400b0fbc  nop     dword ptr [rax+rax+00h]
0x1400b0fc1  mov     rax, [rbp+47h+Object]
0x1400b0fc5  lea     r9, aUnableToInsert; "Unable to insert section object 0x%I64p"...
0x1400b0fcc  mov     [rsp+0C0h+var_88], r12
0x1400b0fd1  mov     edx, 40000h
0x1400b0fd6  mov     [rsp+0C0h+var_90], r12
0x1400b0fdb  mov     [rsp+0C0h+Handle], rdi
0x1400b0fe0  mov     [rsp+0C0h+NewObject], rax
0x1400b0fe5  mov     cs:WdLogGlobalForLineNumber, 7A7h
0x1400b0fef  jmp     loc_1400B0F62
0x1400b0ff4  lea     eax, [r15-5]
0x1400b0ff8  cmp     eax, 1
0x1400b0ffb  ja      short loc_1400B1061
0x1400b0ffd  mov     rcx, [rbp+47h+Object]; Section
0x1400b1001  lea     r8, [rbp+47h+Size]; ViewSize
0x1400b1005  lea     rdx, [rbp+47h+Address]; MappedBase
0x1400b1009  call    cs:__imp_MmMapViewInSystemSpace
0x1400b1010  nop     dword ptr [rax+rax+00h]
0x1400b1015  movsxd  rdi, eax
0x1400b1018  test    eax, eax
0x1400b101a  jns     short loc_1400B1061
0x1400b101c  lock inc cs:dword_1400867CC
0x1400b1023  mov     rdx, rdi
0x1400b1026  mov     ecx, 6
0x1400b102b  call    cs:__imp_WdLogSingleEntry1
0x1400b1032  nop     dword ptr [rax+rax+00h]
0x1400b1037  mov     [rsp+0C0h+var_88], r12
0x1400b103c  lea     r9, aFailedVaMappin; "Failed VA mapping. Status = 0x%I64x\n"
0x1400b1043  mov     [rsp+0C0h+var_90], r12
0x1400b1048  mov     [rsp+0C0h+Handle], r12
0x1400b104d  mov     [rsp+0C0h+NewObject], rdi
0x1400b1052  mov     cs:WdLogGlobalForLineNumber, 7B4h
0x1400b105c  jmp     loc_1400B0F5D
0x1400b1061  xor     ebx, ebx
0x1400b1063  mov     edx, 37316956h
0x1400b1068  mov     ecx, 140h
0x1400b106d  mov     r8d, 40h ; '@'
0x1400b1073  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400b1078  test    rax, rax
0x1400b107b  jz      loc_1400B1288
0x1400b1081  xor     edx, edx; void *
0x1400b1083  mov     rcx, rax; this
0x1400b1086  call    ??0VIDMM_LINEAR_POOL@@QEAA@PEAX@Z; VIDMM_LINEAR_POOL::VIDMM_LINEAR_POOL(void *)
0x1400b108b  mov     r14, rax
0x1400b108e  test    rax, rax
0x1400b1091  jz      loc_1400B1288
0x1400b1097  mov     rdx, [rbp+47h+Size]; unsigned __int64
0x1400b109b  xor     r9d, r9d; void (*)(void *, void *)
0x1400b109e  xor     r8d, r8d; unsigned __int8
0x1400b10a1  mov     [rsp+0C0h+NewObject], rsi; bool (*)(void *)
0x1400b10a6  mov     rcx, rax; this
0x1400b10a9  call    ?Init@VIDMM_LINEAR_POOL@@QEAAJ_KEP6AXPEAX1@ZP6A_N1@Z@Z; VIDMM_LINEAR_POOL::Init(unsigned __int64,uchar,void (*)(void *,void *),bool (*)(void *))
0x1400b10ae  movsxd  rdi, eax
0x1400b10b1  test    eax, eax
0x1400b10b3  jns     short loc_1400B10FD
0x1400b10b5  lock inc cs:dword_140086710
0x1400b10bc  mov     rdx, rdi
0x1400b10bf  mov     ecx, 6
0x1400b10c4  call    cs:__imp_WdLogSingleEntry1
0x1400b10cb  nop     dword ptr [rax+rax+00h]
0x1400b10d0  xor     r12d, r12d
0x1400b10d3  mov     cs:WdLogGlobalForLineNumber, 811h
0x1400b10dd  mov     [rsp+0C0h+var_88], r12
0x1400b10e2  lea     r9, aCouldnTInitial_7; "Couldn't initialized pool for process h"...
0x1400b10e9  mov     [rsp+0C0h+var_90], r12
0x1400b10ee  mov     [rsp+0C0h+Handle], r12
0x1400b10f3  mov     [rsp+0C0h+NewObject], rdi
0x1400b10f8  jmp     loc_1400B0F5D
0x1400b10fd  mov     edx, 31316956h
0x1400b1102  mov     ecx, 68h ; 'h'
0x1400b1107  mov     r8d, 100h
0x1400b110d  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400b1112  mov     rsi, rax
0x1400b1115  test    rax, rax
0x1400b1118  jnz     short loc_1400B1144
0x1400b111a  lock inc cs:dword_140086714
0x1400b1121  lea     ecx, [rax+6]
0x1400b1124  call    cs:__imp_WdLogSingleEntry0
0x1400b112b  nop     dword ptr [rax+rax+00h]
0x1400b1130  mov     eax, 81Dh
0x1400b1135  lea     r9, aCouldnTAllocat_19; "Couldn't allocate memory for VIDMM_PROC"...
0x1400b113c  xor     r12d, r12d
0x1400b113f  jmp     loc_1400B12AF
0x1400b1144  mov     [rax], r13
0x1400b1147  mov     ecx, 2
0x1400b114c  mov     dword ptr [rax+18h], 0
0x1400b1153  mov     rax, [rbp+47h+Address]
0x1400b1157  mov     [rsi+20h], rax
0x1400b115b  mov     rax, [rbp+47h+Size]
0x1400b115f  mov     [rsi+28h], rax
0x1400b1163  xor     eax, eax
0x1400b1165  shr     ebx, 17h
0x1400b1168  and     ebx, 1
0x1400b116b  mov     [rsi+30h], r12d
0x1400b116f  mov     [rsi+48h], r14
0x1400b1173  cmp     r15d, ecx
0x1400b1176  mov     [rsi+50h], r15d
0x1400b117a  cmovnz  ecx, eax
0x1400b117d  mov     rax, [rbp+47h+SecureHandle]
0x1400b1181  mov     [rsi+38h], rax
0x1400b1185  or      ebx, ecx
0x1400b1187  mov     [rsi+40h], ebx
0x1400b118a  mov     rax, [rbp+47h+Object]
0x1400b118e  mov     [rsi+58h], rax
0x1400b1192  mov     rax, [rbp+47h+var_58]
0x1400b1196  mov     [rsi+60h], rax
0x1400b119a  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b11a1  cmp     byte ptr [rax], 0
0x1400b11a4  jz      short loc_1400B11C0
0x1400b11a6  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b11ad  nop     dword ptr [rax+rax+00h]
0x1400b11b2  mov     [rax+18h], rsi
0x1400b11b6  mov     cs:WdLogGlobalForLineNumber, 835h
0x1400b11c0  mov     rcx, [r13+8]
0x1400b11c4  mov     rax, [rsi+28h]
0x1400b11c8  add     [rcx+0B8h], rax
0x1400b11cf  mov     rax, [r13+8]
0x1400b11d3  inc     dword ptr [rax+0C0h]
0x1400b11d9  mov     rax, [r13+8]
0x1400b11dd  mov     rcx, [rsi+28h]
0x1400b11e1  cmp     r15d, 1
0x1400b11e5  jnz     short loc_1400B11F0
0x1400b11e7  add     [rax+0D0h], rcx
0x1400b11ee  jmp     short loc_1400B1206
0x1400b11f0  cmp     r15d, 2
0x1400b11f4  jnz     short loc_1400B11FF
0x1400b11f6  add     [rax+0E0h], rcx
0x1400b11fd  jmp     short loc_1400B1206
0x1400b11ff  add     [rax+0F0h], rcx
0x1400b1206  test    cs:byte_140086202, 4
0x1400b120d  jz      short loc_1400B124C
0x1400b120f  mov     rax, [r13+8]
0x1400b1213  mov     rdx, [rbp+47h+Size]
0x1400b1217  mov     r9, [rbp+47h+Address]
0x1400b121b  mov     dword ptr [rsp+0C0h+var_88], 1
0x1400b1223  mov     ecx, [rax+18h]
0x1400b1226  lea     eax, [r15-3]
0x1400b122a  mov     dword ptr [rsp+0C0h+var_90], ecx
0x1400b122e  cmp     eax, 3
0x1400b1231  mov     dword ptr [rsp+0C0h+Handle], r15d
0x1400b1236  cmovbe  r9, [rbp+47h+Object]
0x1400b123b  mov     [rsp+0C0h+NewObject], rdx
0x1400b1240  lea     rdx, EventCreateProcessAllocation
0x1400b1247  call    McTemplateK0pxqqt_EtwWriteTransfer
  ... truncated ...
```
