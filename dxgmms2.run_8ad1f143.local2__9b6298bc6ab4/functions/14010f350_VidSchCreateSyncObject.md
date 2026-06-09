# VidSchCreateSyncObject

- ea: `0x14010f350`
- end: `0x14010fb99`
- name: `VidSchCreateSyncObject`
- size: `2121`
- prototype: `__int64 __fastcall(__int64, __int64, int *, int, __int64, __int64, int, __int64 *, _OWORD *, __int64, _OWORD *, struct VIDMM_DEVICE *)`
- caller_count: `3`
- callee_count: `12`
- tags: ``

## callers

- `0x1400b3698`
- `0x140105808`
- `0x14011f830`

## callees

- `0x1400045ec`
- `0x14002f510`
- `0x140039084`
- `0x14003a298`
- `0x14003a484`
- `0x14003cf6c`
- `0x14003dcfc`
- `0x14004108c`
- `0x140042d60`
- `0x140044e8c`
- `0x14010f350`
- `0x14010fba0`

## import_xrefs

- `ntoskrnl!ExEventObjectType` at `0x14010f6dc`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14010f708`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14010f708`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010f74e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010f7ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010f74e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010f7ce`
- `ntoskrnl!ExAllocatePool2` at `0x14010f450`
- `ntoskrnl!ExAllocatePool2` at `0x14010f450`
- `watchdog!WdLogSingleEntry0` at `0x14010f467`
- `watchdog!WdLogSingleEntry0` at `0x14010f533`
- `watchdog!WdLogSingleEntry0` at `0x14010f78d`
- `watchdog!WdLogSingleEntry0` at `0x14010f9a5`
- `watchdog!WdLogSingleEntry0` at `0x14010f467`
- `watchdog!WdLogSingleEntry0` at `0x14010f533`
- `watchdog!WdLogSingleEntry0` at `0x14010f78d`
- `watchdog!WdLogSingleEntry0` at `0x14010f9a5`
- `watchdog!WdLogSingleEntry1` at `0x14010f39c`
- `watchdog!WdLogSingleEntry1` at `0x14010f3f1`
- `watchdog!WdLogSingleEntry1` at `0x14010f679`
- `watchdog!WdLogSingleEntry1` at `0x14010f733`
- `watchdog!WdLogSingleEntry1` at `0x14010f39c`
- `watchdog!WdLogSingleEntry1` at `0x14010f3f1`
- `watchdog!WdLogSingleEntry1` at `0x14010f679`
- `watchdog!WdLogSingleEntry1` at `0x14010f733`

## string_xrefs

- `0x14010f3a8`: `Cannot create vidschsyncobject using both SyncObjectInfo and NativeFenceInfo, returning 0x%I64x`
- `0x14010f3fd`: `Cannot create vidschsyncobject without specifying either SyncObjectInfo and NativeFenceInfo, returning 0x%I64x`

## pseudocode

```c
__int64 __fastcall VidSchCreateSyncObject(
        __int64 a1,
        __int64 a2,
        int *a3,
        int a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 *a8,
        _OWORD *a9,
        __int64 a10,
        _OWORD *a11,
        struct VIDMM_DEVICE *a12)
{
  __int64 v12; // r15
  unsigned int v16; // ebx
  int v17; // ecx
  int v18; // r8d
  const wchar_t *v19; // r9
  __int64 result; // rax
  _DWORD *v21; // r12
  int *v22; // rbx
  int v23; // ebx
  __int64 Pool2; // rax
  __int64 v25; // rsi
  struct DXGPROCESS *Current; // rax
  int v27; // r8d
  int v28; // edx
  unsigned int v29; // ecx
  int v30; // ecx
  __int64 v31; // rbx
  _OWORD *v32; // rax
  char v33; // cl
  __int64 v34; // r9
  int FenceStorageSlot; // eax
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  bool v39; // zf
  int v40; // ecx
  int v41; // r8d
  void *v42; // rcx
  NTSTATUS v43; // eax
  __int64 v44; // rax
  unsigned int v45; // eax
  int v46; // ecx
  int v47; // r8d
  _OWORD *v48; // rax
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  _OWORD *v52; // rax
  __int128 v53; // xmm1
  __int128 v54; // xmm0
  __int128 v55; // xmm1
  __int64 v56; // r9
  int v57; // ecx
  int v58; // r8d
  __int64 *v59; // rdx
  PVOID Object; // [rsp+B0h] [rbp+18h] BYREF

  v12 = a10;
  if ( a3 )
  {
    if ( a10 )
    {
      v16 = -1073741811;
      WdLogSingleEntry1(1, -1073741811);
      v19 = L"Cannot create vidschsyncobject using both SyncObjectInfo and NativeFenceInfo, returning 0x%I64x";
      WdLogGlobalForLineNumber = 10728;
LABEL_4:
      DxgkLogInternalTriageEvent(v17, 0x40000, v18, (_DWORD)v19, -1073741811, 0, 0, 0);
      return v16;
    }
  }
  else if ( !a10 )
  {
    v16 = -1073741811;
    WdLogSingleEntry1(1, -1073741811);
    v19 = L"Cannot create vidschsyncobject without specifying either SyncObjectInfo and NativeFenceInfo, returning 0x%I64x";
    WdLogGlobalForLineNumber = 10735;
    goto LABEL_4;
  }
  v21 = a3 + 1;
  v22 = (int *)(a10 + 16);
  if ( !a10 )
    v22 = a3 + 1;
  *a8 = 0;
  v23 = *v22;
  Pool2 = ExAllocatePool2(64, (v23 & 4) != 0 ? 368LL : 288LL, 945908054);
  v25 = Pool2;
  if ( !Pool2 )
  {
    WdLogSingleEntry0(3);
    result = 3221225495LL;
    WdLogGlobalForLineNumber = 10758;
    return result;
  }
  *(_QWORD *)(Pool2 + 8) = a1;
  *(_DWORD *)Pool2 = 945908054;
  *(_QWORD *)(Pool2 + 16) = a2;
  *(_BYTE *)(Pool2 + 24) = v23 & 1;
  *(_DWORD *)(Pool2 + 36) = 1;
  *(_DWORD *)(Pool2 + 40) = 0;
  *(_BYTE *)(Pool2 + 28) = (v23 & 4) != 0;
  *(_BYTE *)(Pool2 + 27) = v23 < 0;
  *(_DWORD *)(Pool2 + 52) = a4;
  Current = DXGPROCESS::GetCurrent();
  if ( Current )
  {
    if ( (*((_DWORD *)Current + 102) & 0x100) != 0 )
      *(_BYTE *)(v25 + 32) = 1;
    if ( (*((_DWORD *)Current + 102) & 0x10) != 0 )
      *(_WORD *)(v25 + 32) = 257;
  }
  if ( !a3 )
  {
    v29 = a2;
    *(_DWORD *)(v25 + 48) = 6;
    *(_BYTE *)(v25 + 57) = *(_DWORD *)(a2 + 420) == 5;
    *(_BYTE *)(v25 + 30) = *(_BYTE *)(a2 + 428) & 1;
    v48 = a9;
    v49 = a9[1];
    *(_OWORD *)(v25 + 64) = *a9;
    v50 = v48[2];
    *(_OWORD *)(v25 + 80) = v49;
    v51 = v48[3];
    v52 = a11;
    *(_OWORD *)(v25 + 96) = v50;
    *(_OWORD *)(v25 + 112) = v51;
    v53 = v52[1];
    *(_OWORD *)(v25 + 128) = *v52;
    v54 = v52[2];
    *(_OWORD *)(v25 + 144) = v53;
    v55 = v52[3];
    *(_OWORD *)(v25 + 160) = v54;
    *(_OWORD *)(v25 + 176) = v55;
    goto LABEL_49;
  }
  v28 = *a3;
  v29 = *a3 - 1;
  if ( *a3 == 1 )
  {
    v31 = a1;
    *(_DWORD *)(v25 + 48) = 0;
    *(_BYTE *)(v25 + 25) = 0;
    if ( a3[2] )
    {
      *(_QWORD *)(v25 + 64) = 0;
      *(_QWORD *)(v25 + 72) = 0;
    }
    else
    {
      *(_QWORD *)(v25 + 64) = -1;
      *(_QWORD *)(v25 + 72) = -1;
    }
    goto LABEL_50;
  }
  if ( *a3 == 2 )
  {
    v29 = a3[2];
    v45 = a3[3];
    if ( v45 > v29 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 10833;
      DxgkLogInternalTriageEvent(
        v46,
        0x40000,
        v47,
        (unsigned int)L"Can't initialize semaphore to larger value than specified maximum",
        10833,
        0,
        0,
        0);
      ExFreePoolWithTag((PVOID)v25, 0);
      return -1073741811;
    }
    *(_DWORD *)(v25 + 48) = 1;
    *(_BYTE *)(v25 + 25) = 0;
    *(_DWORD *)(v25 + 64) = v45;
    *(_DWORD *)(v25 + 72) = v45;
    *(_DWORD *)(v25 + 68) = v29;
    goto LABEL_49;
  }
  v29 = *a3 - 3;
  if ( *a3 == 3 )
  {
    v44 = *((_QWORD *)a3 + 1);
    *(_QWORD *)(v25 + 64) = v44;
    *(_QWORD *)(v25 + 72) = v44;
    *(_QWORD *)(v25 + 80) = v44;
    *(_DWORD *)(v25 + 48) = 2;
    *(_BYTE *)(v25 + 25) = 1;
LABEL_49:
    v31 = a1;
    goto LABEL_50;
  }
  if ( *a3 == 4 )
  {
    if ( (a3[1] & 1) != 0 )
    {
      v16 = -1073741811;
      WdLogSingleEntry1(1, -1073741811);
      WdLogGlobalForLineNumber = 10855;
      DxgkLogInternalTriageEvent(
        v40,
        0x40000,
        v41,
        (unsigned int)L"CPUNotification.Event is not sharable, returning 0x%I64x",
        -1073741811,
        0,
        0,
        0);
      goto LABEL_40;
    }
    v42 = (void *)*((_QWORD *)a3 + 1);
    *(_DWORD *)(v25 + 48) = 3;
    *(_BYTE *)(v25 + 25) = 0;
    if ( *(_BYTE *)(v25 + 32) )
    {
      *(_QWORD *)(v25 + 72) = v42;
      DxgkAcquireGuestCpuEvent();
    }
    else
    {
      Object = 0;
      v43 = ObReferenceObjectByHandle(v42, 0x1F0003u, (POBJECT_TYPE)ExEventObjectType, 1, &Object, 0);
      v29 = (unsigned int)Object;
      *(_QWORD *)(v25 + 64) = Object;
      v16 = v43;
      if ( v43 < 0 )
      {
        WdLogSingleEntry1(3, v43);
        WdLogGlobalForLineNumber = 10884;
        goto LABEL_40;
      }
    }
    goto LABEL_49;
  }
  if ( (unsigned int)(*a3 - 5) >= 2 )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 10944;
    v16 = -1073741811;
LABEL_40:
    ExFreePoolWithTag((PVOID)v25, 0);
    return v16;
  }
  v30 = a3[1];
  v31 = a1;
  *(_BYTE *)(v25 + 25) = 1;
  v27 = v30 & 0x80;
  *(_DWORD *)(v25 + 48) = 5 - (v28 != 6);
  *(_BYTE *)(v25 + 31) = v27 != 0;
  v32 = a9;
  *(_BYTE *)(v25 + 26) = (v30 & 0x400) != 0;
  if ( v32 )
  {
    v29 = a2;
    v36 = v32[1];
    *(_OWORD *)(v25 + 64) = *v32;
    v37 = v32[2];
    *(_OWORD *)(v25 + 80) = v36;
    v38 = v32[3];
    v39 = *(_DWORD *)(a2 + 420) == 7;
    *(_BYTE *)(v25 + 30) = *(_BYTE *)(a2 + 428) & 1;
    *(_OWORD *)(v25 + 96) = v37;
    *(_BYTE *)(v25 + 56) = v39;
    *(_OWORD *)(v25 + 112) = v38;
  }
  else
  {
    if ( *(_BYTE *)(a1 + 56) || (v33 = 0, v27) )
      v33 = 1;
    *(_BYTE *)(v25 + 30) = v33;
    v34 = 0;
    *(_DWORD *)(v25 + 116) = 16;
    if ( v28 != 6 )
      v34 = *((_QWORD *)a3 + 1);
    FenceStorageSlot = VidMmAllocateFenceStorageSlot(
                         (struct VIDMM_MONITORED_FENCE_STORAGE *)(v25 + 64),
                         a2 == 0,
                         v34,
                         v33,
                         a12);
    if ( FenceStorageSlot < 0 )
    {
      v16 = FenceStorageSlot;
      goto LABEL_40;
    }
    *(_QWORD *)(v25 + 88) = a6;
  }
LABEL_50:
  *(_QWORD *)(v25 + 216) = v25 + 208;
  *(_QWORD *)(v25 + 208) = v25 + 208;
  *(_QWORD *)(v25 + 232) = v25 + 224;
  *(_QWORD *)(v25 + 224) = v25 + 224;
  *(_QWORD *)(v25 + 264) = v25 + 256;
  *(_QWORD *)(v25 + 256) = v25 + 256;
  if ( *(_BYTE *)(v25 + 28) )
  {
    *(_QWORD *)(v25 + 352) = a5;
    *(_QWORD *)(v25 + 360) = VidSchPostCrossAdapterSignal;
    VidSchiAddSyncObjectToAdapterList(v31, v25);
    VidSchiAddSyncObjectToCrossAdapterInfo(v25);
  }
  *a8 = v25;
  if ( v12 )
  {
    if ( (byte_140086201 & 1) != 0 )
      McTemplateK0pptqx_EtwWriteTransfer(
        v29,
        (unsigned int)EventCreateNativeFence,
        v27,
        *(_QWORD *)(v31 + 16),
        v25,
        0,
        *(_DWORD *)(v12 + 16),
        *(_QWORD *)v12);
    return 0;
  }
  if ( bTracingEnabled )
  {
    v56 = *(_QWORD *)(v31 + 16);
    if ( *a3 == 1 )
    {
      if ( (byte_140086201 & 1) != 0 )
        McTemplateK0ppqqpt_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          (unsigned int)EventCreateSynchronizationMutex,
          0,
          v56,
          v25,
          0,
          *v21,
          a3[18],
          a3[2]);
      return 0;
    }
    if ( *a3 == 2 )
    {
      if ( (byte_140086201 & 1) != 0 )
        McTemplateK0ppqqpqq_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          (unsigned int)EventCreateSemaphore,
          0,
          v56,
          v25,
          0,
          *v21,
          a3[18],
          a3[2],
          a3[3]);
      return 0;
    }
    if ( *a3 == 3 )
    {
      if ( (byte_140086201 & 1) != 0 )
      {
        v59 = EventCreateFence;
        goto LABEL_71;
      }
    }
    else
    {
      if ( *a3 == 4 )
      {
        if ( (byte_140086201 & 1) != 0 )
          McTemplateK0ppqqpx_EtwWriteTransfer(
            (unsigned int)&DxgkControlGuid_Context,
            (unsigned int)EventCreateCPUNotification,
            0,
            v56,
            v25,
            0,
            *v21,
            a3[18],
            *((_QWORD *)a3 + 1));
        return 0;
      }
      if ( *a3 != 5 )
      {
        if ( *a3 == 6 )
        {
          if ( (byte_140086201 & 1) != 0 )
            McTemplateK0ppqqppqi_EtwWriteTransfer(
              (unsigned int)&DxgkControlGuid_Context,
              (unsigned int)EventCreatePeriodicMonitoredFence,
              0,
              v56,
              v25,
              0,
              *v21,
              a3[18],
              a3[2],
              a3[3],
              *((_QWORD *)a3 + 2));
        }
        else
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 1061;
          DxgkLogInternalTriageEvent(v57, 262146, v58, (unsigned int)L"FALSE", 1061, 0, 0, 0);
        }
        return 0;
      }
      if ( (byte_140086201 & 1) != 0 )
      {
        v59 = EventCreateMonitoredFence;
LABEL_71:
        McTemplateK0ppqqpx_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          (_DWORD)v59,
          0,
          v56,
          v25,
          0,
          *v21,
          a3[18],
          *((_QWORD *)a3 + 1));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14010f350  mov     [rsp+arg_18], rbx
0x14010f355  mov     [rsp+arg_8], rdx
0x14010f35a  mov     [rsp+arg_0], rcx
0x14010f35f  push    rbp
0x14010f360  push    rsi
0x14010f361  push    rdi
0x14010f362  push    r12
0x14010f364  push    r13
0x14010f366  push    r14
0x14010f368  push    r15
0x14010f36a  sub     rsp, 60h
0x14010f36e  mov     r15, [rsp+98h+arg_48]
0x14010f376  xor     esi, esi
0x14010f378  mov     edi, r9d
0x14010f37b  mov     r14, r8
0x14010f37e  mov     rbp, rcx
0x14010f381  test    r8, r8
0x14010f384  jz      short loc_14010F3DE
0x14010f386  test    r15, r15
0x14010f389  jz      loc_14010F410
0x14010f38f  mov     rbx, 0FFFFFFFFC000000Dh
0x14010f396  lea     ecx, [rsi+1]
0x14010f399  mov     rdx, rbx
0x14010f39c  call    cs:__imp_WdLogSingleEntry1
0x14010f3a3  nop     dword ptr [rax+rax+00h]
0x14010f3a8  lea     r9, aCannotCreateVi; "Cannot create vidschsyncobject using bo"...
0x14010f3af  mov     cs:WdLogGlobalForLineNumber, 29E8h
0x14010f3b9  mov     [rsp+98h+var_60], rsi
0x14010f3be  mov     edx, 40000h
0x14010f3c3  mov     qword ptr [rsp+98h+var_68], rsi
0x14010f3c8  mov     [rsp+98h+HandleInformation], rsi
0x14010f3cd  mov     [rsp+98h+Object], rbx
0x14010f3d2  call    DxgkLogInternalTriageEvent
0x14010f3d7  mov     eax, ebx
0x14010f3d9  jmp     loc_14010FB80
0x14010f3de  test    r15, r15
0x14010f3e1  jnz     short loc_14010F410
0x14010f3e3  mov     rbx, 0FFFFFFFFC000000Dh
0x14010f3ea  lea     ecx, [r15+1]
0x14010f3ee  mov     rdx, rbx
0x14010f3f1  call    cs:__imp_WdLogSingleEntry1
0x14010f3f8  nop     dword ptr [rax+rax+00h]
0x14010f3fd  lea     r9, aCannotCreateVi_0; "Cannot create vidschsyncobject without "...
0x14010f404  mov     cs:WdLogGlobalForLineNumber, 29EFh
0x14010f40e  jmp     short loc_14010F3B9
0x14010f410  mov     rax, [rsp+98h+arg_38]
0x14010f418  lea     r12, [r8+4]
0x14010f41c  test    r15, r15
0x14010f41f  lea     rbx, [r15+10h]
0x14010f423  mov     ecx, 40h ; '@'
0x14010f428  mov     r8d, 38616956h
0x14010f42e  cmovz   rbx, r12
0x14010f432  mov     [rax], rsi
0x14010f435  mov     ebx, [rbx]
0x14010f437  mov     r13d, ebx
0x14010f43a  and     r13d, 4
0x14010f43e  mov     eax, r13d
0x14010f441  neg     eax
0x14010f443  sbb     rdx, rdx
0x14010f446  and     edx, 50h
0x14010f449  add     rdx, 120h
0x14010f450  call    cs:__imp_ExAllocatePool2
0x14010f457  nop     dword ptr [rax+rax+00h]
0x14010f45c  mov     rsi, rax
0x14010f45f  test    rax, rax
0x14010f462  jnz     short loc_14010F487
0x14010f464  lea     ecx, [rax+3]
0x14010f467  call    cs:__imp_WdLogSingleEntry0
0x14010f46e  nop     dword ptr [rax+rax+00h]
0x14010f473  mov     eax, 0C0000017h
0x14010f478  mov     cs:WdLogGlobalForLineNumber, 2A06h
0x14010f482  jmp     loc_14010FB80
0x14010f487  mov     [rax+8], rbp
0x14010f48b  mov     ebp, 1
0x14010f490  mov     dword ptr [rax], 38616956h
0x14010f496  mov     rax, [rsp+98h+arg_8]
0x14010f49e  mov     [rsi+10h], rax
0x14010f4a2  mov     al, bl
0x14010f4a4  and     al, bpl
0x14010f4a7  shr     ebx, 1Fh
0x14010f4aa  mov     [rsi+18h], al
0x14010f4ad  test    r13d, r13d
0x14010f4b0  mov     [rsi+24h], ebp
0x14010f4b3  setnz   al
0x14010f4b6  mov     dword ptr [rsi+28h], 0
0x14010f4bd  mov     [rsi+1Ch], al
0x14010f4c0  mov     [rsi+1Bh], bl
0x14010f4c3  mov     [rsi+34h], edi
0x14010f4c6  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14010f4cb  xor     edi, edi
0x14010f4cd  test    rax, rax
0x14010f4d0  jz      short loc_14010F4F8
0x14010f4d2  mov     ecx, [rax+198h]
0x14010f4d8  shr     ecx, 8
0x14010f4db  test    bpl, cl
0x14010f4de  jz      short loc_14010F4E4
0x14010f4e0  mov     [rsi+20h], bpl
0x14010f4e4  mov     eax, [rax+198h]
0x14010f4ea  shr     eax, 4
0x14010f4ed  test    bpl, al
0x14010f4f0  jz      short loc_14010F4F8
0x14010f4f2  mov     word ptr [rsi+20h], 101h
0x14010f4f8  test    r14, r14
0x14010f4fb  jz      loc_14010F82E
0x14010f501  mov     edx, [r14]
0x14010f504  mov     ecx, edx
0x14010f506  sub     ecx, ebp
0x14010f508  jz      loc_14010F7FB
0x14010f50e  sub     ecx, ebp
0x14010f510  jz      loc_14010F77F
0x14010f516  sub     ecx, ebp
0x14010f518  jz      loc_14010F75F
0x14010f51e  sub     ecx, ebp
0x14010f520  jz      loc_14010F664
0x14010f526  sub     ecx, ebp
0x14010f528  jz      short loc_14010F555
0x14010f52a  cmp     ecx, ebp
0x14010f52c  jz      short loc_14010F555
0x14010f52e  mov     ecx, 3
0x14010f533  call    cs:__imp_WdLogSingleEntry0
0x14010f53a  nop     dword ptr [rax+rax+00h]
0x14010f53f  mov     cs:WdLogGlobalForLineNumber, 2AC0h
0x14010f549  mov     rbx, 0FFFFFFFFC000000Dh
0x14010f550  jmp     loc_14010F749
0x14010f555  mov     ecx, [r14+4]
0x14010f559  lea     eax, [rdx-6]
0x14010f55c  mov     rbx, [rsp+98h+arg_0]
0x14010f564  neg     eax
0x14010f566  mov     r8d, ecx
0x14010f569  mov     [rsi+19h], bpl
0x14010f56d  sbb     eax, eax
0x14010f56f  add     eax, 5
0x14010f572  and     r8d, 80h
0x14010f579  mov     [rsi+30h], eax
0x14010f57c  setnz   al
0x14010f57f  shr     ecx, 0Ah
0x14010f582  and     cl, bpl
0x14010f585  mov     [rsi+1Fh], al
0x14010f588  mov     rax, [rsp+98h+arg_40]
0x14010f590  mov     [rsi+1Ah], cl
0x14010f593  test    rax, rax
0x14010f596  jnz     loc_14010F61F
0x14010f59c  cmp     [rbx+38h], dil
0x14010f5a0  jnz     short loc_14010F5AA
0x14010f5a2  mov     cl, dil
0x14010f5a5  test    r8d, r8d
0x14010f5a8  jz      short loc_14010F5AD
0x14010f5aa  mov     cl, bpl
0x14010f5ad  mov     [rsi+1Eh], cl
0x14010f5b0  mov     r9, rdi
0x14010f5b3  mov     dword ptr [rsi+74h], 10h
0x14010f5ba  cmp     edx, 6
0x14010f5bd  jz      short loc_14010F5C3
0x14010f5bf  mov     r9, [r14+8]
0x14010f5c3  cmp     [rsp+98h+arg_8], rdi
0x14010f5cb  mov     rax, [rsp+98h+arg_58]
0x14010f5d3  setz    dl
0x14010f5d6  mov     [rsp+98h+var_60], rax; struct VIDMM_DEVICE *
0x14010f5db  cmp     [rsi+18h], dil
0x14010f5df  mov     [rsp+98h+var_68], cl; char
0x14010f5e3  lea     rcx, [rsi+40h]; struct VIDMM_MONITORED_FENCE_STORAGE *
0x14010f5e7  mov     [rsp+98h+HandleInformation], r9; __int64
0x14010f5ec  setnz   r8b
0x14010f5f0  mov     byte ptr [rsp+98h+Object], dl; char
0x14010f5f4  xor     r9d, r9d
0x14010f5f7  mov     edx, [rsp+98h+arg_30]
0x14010f5fe  call    VidMmAllocateFenceStorageSlot
0x14010f603  test    eax, eax
0x14010f605  jns     short loc_14010F60E
0x14010f607  mov     ebx, eax
0x14010f609  jmp     loc_14010F749
0x14010f60e  mov     rax, [rsp+98h+arg_28]
0x14010f616  mov     [rsi+58h], rax
0x14010f61a  jmp     loc_14010F8B8
0x14010f61f  movups  xmm0, xmmword ptr [rax]
0x14010f622  mov     rcx, [rsp+98h+arg_8]
0x14010f62a  movups  xmm1, xmmword ptr [rax+10h]
0x14010f62e  movups  xmmword ptr [rsi+40h], xmm0
0x14010f632  movups  xmm0, xmmword ptr [rax+20h]
0x14010f636  movups  xmmword ptr [rsi+50h], xmm1
0x14010f63a  movups  xmm1, xmmword ptr [rax+30h]
0x14010f63e  mov     al, [rcx+1ACh]
0x14010f644  and     al, bpl
0x14010f647  cmp     dword ptr [rcx+1A4h], 7
0x14010f64e  mov     [rsi+1Eh], al
0x14010f651  setz    al
0x14010f654  movups  xmmword ptr [rsi+60h], xmm0
0x14010f658  mov     [rsi+38h], al
0x14010f65b  movups  xmmword ptr [rsi+70h], xmm1
0x14010f65f  jmp     loc_14010F8B8
0x14010f664  mov     eax, [r14+4]
0x14010f668  test    bpl, al
0x14010f66b  jz      short loc_14010F6B9
0x14010f66d  mov     rbx, 0FFFFFFFFC000000Dh
0x14010f674  mov     ecx, ebp
0x14010f676  mov     rdx, rbx
0x14010f679  call    cs:__imp_WdLogSingleEntry1
0x14010f680  nop     dword ptr [rax+rax+00h]
0x14010f685  mov     [rsp+98h+var_60], rdi
0x14010f68a  lea     r9, aCpunotificatio; "CPUNotification.Event is not sharable, "...
0x14010f691  mov     qword ptr [rsp+98h+var_68], rdi
0x14010f696  mov     edx, 40000h
0x14010f69b  mov     [rsp+98h+HandleInformation], rdi
0x14010f6a0  mov     [rsp+98h+Object], rbx
0x14010f6a5  mov     cs:WdLogGlobalForLineNumber, 2A67h
0x14010f6af  call    DxgkLogInternalTriageEvent
0x14010f6b4  jmp     loc_14010F749
0x14010f6b9  mov     rcx, [r14+8]; Handle
0x14010f6bd  mov     dword ptr [rsi+30h], 3
0x14010f6c4  mov     [rsi+19h], dil
0x14010f6c8  cmp     [rsi+20h], dil
0x14010f6cc  jz      short loc_14010F6DC
0x14010f6ce  mov     [rsi+48h], rcx
0x14010f6d2  call    DxgkAcquireGuestCpuEvent
0x14010f6d7  jmp     loc_14010F8B0
0x14010f6dc  mov     r8, cs:ExEventObjectType
0x14010f6e3  lea     rax, [rsp+98h+arg_10]
0x14010f6eb  mov     [rsp+98h+HandleInformation], rdi; HandleInformation
0x14010f6f0  mov     r9b, bpl; AccessMode
0x14010f6f3  mov     edx, 1F0003h; DesiredAccess
0x14010f6f8  mov     [rsp+98h+arg_10], rdi
0x14010f700  mov     [rsp+98h+Object], rax; Object
0x14010f705  mov     r8, [r8]; ObjectType
0x14010f708  call    cs:__imp_ObReferenceObjectByHandle
0x14010f70f  nop     dword ptr [rax+rax+00h]
0x14010f714  mov     rcx, [rsp+98h+arg_10]
0x14010f71c  mov     [rsi+40h], rcx
0x14010f720  movsxd  rbx, eax
0x14010f723  test    eax, eax
0x14010f725  jns     loc_14010F8B0
0x14010f72b  mov     rdx, rbx
0x14010f72e  mov     ecx, 3
0x14010f733  call    cs:__imp_WdLogSingleEntry1
0x14010f73a  nop     dword ptr [rax+rax+00h]
0x14010f73f  mov     cs:WdLogGlobalForLineNumber, 2A84h
0x14010f749  xor     edx, edx; Tag
0x14010f74b  mov     rcx, rsi; P
0x14010f74e  call    cs:__imp_ExFreePoolWithTag
0x14010f755  nop     dword ptr [rax+rax+00h]
0x14010f75a  jmp     loc_14010F3D7
0x14010f75f  mov     rax, [r14+8]
0x14010f763  mov     [rsi+40h], rax
0x14010f767  mov     [rsi+48h], rax
0x14010f76b  mov     [rsi+50h], rax
0x14010f76f  mov     dword ptr [rsi+30h], 2
0x14010f776  mov     [rsi+19h], bpl
0x14010f77a  jmp     loc_14010F8B0
0x14010f77f  mov     ecx, [r14+8]
0x14010f783  mov     eax, [r14+0Ch]
0x14010f787  cmp     eax, ecx
0x14010f789  jbe     short loc_14010F7E6
0x14010f78b  mov     ecx, ebp
0x14010f78d  call    cs:__imp_WdLogSingleEntry0
0x14010f794  nop     dword ptr [rax+rax+00h]
0x14010f799  mov     [rsp+98h+var_60], rdi
0x14010f79e  lea     r9, aCanTInitialize; "Can't initialize semaphore to larger va"...
0x14010f7a5  mov     eax, 2A51h
0x14010f7aa  mov     qword ptr [rsp+98h+var_68], rdi
0x14010f7af  mov     [rsp+98h+HandleInformation], rdi
0x14010f7b4  mov     edx, 40000h
0x14010f7b9  mov     cs:WdLogGlobalForLineNumber, eax
0x14010f7bf  mov     [rsp+98h+Object], rax
0x14010f7c4  call    DxgkLogInternalTriageEvent
0x14010f7c9  xor     edx, edx; Tag
0x14010f7cb  mov     rcx, rsi; P
0x14010f7ce  call    cs:__imp_ExFreePoolWithTag
0x14010f7d5  nop     dword ptr [rax+rax+00h]
0x14010f7da  mov     rax, 0FFFFFFFFC000000Dh
0x14010f7e1  jmp     loc_14010FB80
0x14010f7e6  mov     [rsi+30h], ebp
0x14010f7e9  mov     [rsi+19h], dil
0x14010f7ed  mov     [rsi+40h], eax
0x14010f7f0  mov     [rsi+48h], eax
0x14010f7f3  mov     [rsi+44h], ecx
0x14010f7f6  jmp     loc_14010F8B0
0x14010f7fb  mov     rbx, [rsp+98h+arg_0]
0x14010f803  mov     [rsi+30h], edi
0x14010f806  mov     [rsi+19h], dil
0x14010f80a  cmp     [r14+8], edi
0x14010f80e  jz      short loc_14010F81D
0x14010f810  mov     [rsi+40h], rdi
0x14010f814  mov     [rsi+48h], rdi
0x14010f818  jmp     loc_14010F8B8
0x14010f81d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14010f821  mov     [rsi+40h], rax
0x14010f825  mov     [rsi+48h], rax
0x14010f829  jmp     loc_14010F8B8
0x14010f82e  mov     rcx, [rsp+98h+arg_8]
0x14010f836  mov     dword ptr [rsi+30h], 6
0x14010f83d  cmp     dword ptr [rcx+1A4h], 5
0x14010f844  setz    al
0x14010f847  mov     [rsi+39h], al
0x14010f84a  mov     al, [rcx+1ACh]
0x14010f850  and     al, bpl
0x14010f853  mov     [rsi+1Eh], al
0x14010f856  mov     rax, [rsp+98h+arg_40]
0x14010f85e  movups  xmm0, xmmword ptr [rax]
0x14010f861  movups  xmm1, xmmword ptr [rax+10h]
0x14010f865  movups  xmmword ptr [rsi+40h], xmm0
0x14010f869  movups  xmm0, xmmword ptr [rax+20h]
  ... truncated ...
```
