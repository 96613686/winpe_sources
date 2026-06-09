# VidSchCreateSyncObject

- ea: `0x14012a910`
- end: `0x14012b153`
- name: `VidSchCreateSyncObject`
- size: `2115`
- prototype: `__int64 __fastcall(__int64, __int64, int *, int, __int64, __int64, int, __int64 *, _OWORD *, __int64, _OWORD *, struct VIDMM_DEVICE *)`
- caller_count: `3`
- callee_count: `12`
- tags: ``

## callers

- `0x1400b4cd8`
- `0x1400b6f68`
- `0x140123010`

## callees

- `0x140004268`
- `0x14002c5d0`
- `0x1400380e4`
- `0x140039218`
- `0x140039404`
- `0x14003bc7c`
- `0x14003ca0c`
- `0x14003fa0c`
- `0x140042ed0`
- `0x140045090`
- `0x140128070`
- `0x14012a910`

## import_xrefs

- `ntoskrnl!ExEventObjectType` at `0x14012ac96`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14012acc2`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14012acc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012ad08`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012ad88`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012ad08`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012ad88`
- `ntoskrnl!ExAllocatePool2` at `0x14012aa10`
- `ntoskrnl!ExAllocatePool2` at `0x14012aa10`
- `watchdog!WdLogSingleEntry0` at `0x14012aa27`
- `watchdog!WdLogSingleEntry0` at `0x14012aaf0`
- `watchdog!WdLogSingleEntry0` at `0x14012ad47`
- `watchdog!WdLogSingleEntry0` at `0x14012af5f`
- `watchdog!WdLogSingleEntry0` at `0x14012aa27`
- `watchdog!WdLogSingleEntry0` at `0x14012aaf0`
- `watchdog!WdLogSingleEntry0` at `0x14012ad47`
- `watchdog!WdLogSingleEntry0` at `0x14012af5f`
- `watchdog!WdLogSingleEntry1` at `0x14012a95a`
- `watchdog!WdLogSingleEntry1` at `0x14012a9af`
- `watchdog!WdLogSingleEntry1` at `0x14012ac33`
- `watchdog!WdLogSingleEntry1` at `0x14012aced`
- `watchdog!WdLogSingleEntry1` at `0x14012a95a`
- `watchdog!WdLogSingleEntry1` at `0x14012a9af`
- `watchdog!WdLogSingleEntry1` at `0x14012ac33`
- `watchdog!WdLogSingleEntry1` at `0x14012aced`

## string_xrefs

- `0x14012a966`: `Cannot create vidschsyncobject using both SyncObjectInfo and NativeFenceInfo, returning 0x%I64x`
- `0x14012a9bb`: `Cannot create vidschsyncobject without specifying either SyncObjectInfo and NativeFenceInfo, returning 0x%I64x`

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
  unsigned int v17; // ebx
  int v18; // ecx
  int v19; // r8d
  const wchar_t *v20; // r9
  __int64 result; // rax
  int *v22; // r12
  int *v23; // rbx
  int v24; // ebx
  __int64 Pool2; // rax
  __int64 v26; // rsi
  bool v27; // zf
  struct DXGPROCESS *Current; // rax
  unsigned int v29; // ecx
  int v30; // r8d
  int v31; // edx
  unsigned int v32; // ecx
  _OWORD *v33; // rax
  char v34; // cl
  __int64 v35; // r9
  int FenceStorageSlot; // eax
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
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
  __int64 v56; // rax
  __int64 v57; // r9
  int v58; // ecx
  int v59; // r8d
  void *v60; // rdx
  PVOID Object; // [rsp+B0h] [rbp+18h] BYREF

  v12 = a10;
  if ( a3 )
  {
    if ( a10 )
    {
      v17 = -1073741811;
      WdLogSingleEntry1(1, -1073741811);
      v20 = L"Cannot create vidschsyncobject using both SyncObjectInfo and NativeFenceInfo, returning 0x%I64x";
      WdLogGlobalForLineNumber = 10728;
LABEL_4:
      DxgkLogInternalTriageEvent(v18, 0x40000, v19, (_DWORD)v20, -1073741811, 0, 0, 0);
      return v17;
    }
  }
  else if ( !a10 )
  {
    v17 = -1073741811;
    WdLogSingleEntry1(1, -1073741811);
    v20 = L"Cannot create vidschsyncobject without specifying either SyncObjectInfo and NativeFenceInfo, returning 0x%I64x";
    WdLogGlobalForLineNumber = 10735;
    goto LABEL_4;
  }
  v22 = a3 + 1;
  v23 = (int *)(a10 + 16);
  if ( !a10 )
    v23 = a3 + 1;
  *a8 = 0;
  v24 = *v23;
  LODWORD(Object) = v24 & 4;
  Pool2 = ExAllocatePool2(64, (_DWORD)Object != 0 ? 376LL : 296LL, 945908054);
  v26 = Pool2;
  if ( !Pool2 )
  {
    WdLogSingleEntry0(3);
    result = 3221225495LL;
    WdLogGlobalForLineNumber = 10758;
    return result;
  }
  *(_QWORD *)(Pool2 + 16) = a2;
  *(_DWORD *)(Pool2 + 36) = 1;
  *(_DWORD *)Pool2 = 945908054;
  *(_QWORD *)(Pool2 + 8) = a1;
  *(_DWORD *)(Pool2 + 40) = 0;
  v27 = (_DWORD)Object == 0;
  *(_BYTE *)(Pool2 + 24) = v24 & 1;
  *(_BYTE *)(Pool2 + 27) = v24 < 0;
  *(_BYTE *)(Pool2 + 28) = !v27;
  *(_DWORD *)(Pool2 + 52) = a4;
  Current = DXGPROCESS::GetCurrent();
  if ( Current )
  {
    v29 = *((_DWORD *)Current + 102) >> 8;
    if ( (*((_DWORD *)Current + 102) & 0x100) != 0 )
      *(_BYTE *)(v26 + 32) = 1;
    if ( (*((_DWORD *)Current + 102) & 0x10) != 0 )
      *(_WORD *)(v26 + 32) = 257;
  }
  if ( a3 )
  {
    v31 = *a3;
    v29 = *a3 - 1;
    if ( *a3 == 1 )
    {
      *(_DWORD *)(v26 + 48) = 0;
      *(_BYTE *)(v26 + 25) = 0;
      if ( a3[2] )
      {
        *(_QWORD *)(v26 + 64) = 0;
        *(_QWORD *)(v26 + 72) = 0;
      }
      else
      {
        *(_QWORD *)(v26 + 64) = -1;
        *(_QWORD *)(v26 + 72) = -1;
      }
    }
    else if ( *a3 == 2 )
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
        ExFreePoolWithTag((PVOID)v26, 0);
        return -1073741811;
      }
      *(_DWORD *)(v26 + 48) = 1;
      *(_BYTE *)(v26 + 25) = 0;
      *(_DWORD *)(v26 + 64) = v45;
      *(_DWORD *)(v26 + 72) = v45;
      *(_DWORD *)(v26 + 68) = v29;
    }
    else
    {
      v29 = *a3 - 3;
      if ( *a3 == 3 )
      {
        v44 = *((_QWORD *)a3 + 1);
        *(_QWORD *)(v26 + 64) = v44;
        *(_QWORD *)(v26 + 72) = v44;
        *(_QWORD *)(v26 + 80) = v44;
        *(_DWORD *)(v26 + 48) = 2;
        *(_BYTE *)(v26 + 25) = 1;
      }
      else if ( *a3 == 4 )
      {
        if ( (a3[1] & 1) != 0 )
        {
          v17 = -1073741811;
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
        *(_DWORD *)(v26 + 48) = 3;
        *(_BYTE *)(v26 + 25) = 0;
        if ( *(_BYTE *)(v26 + 32) )
        {
          *(_QWORD *)(v26 + 72) = v42;
          DxgkAcquireGuestCpuEvent();
        }
        else
        {
          Object = 0;
          v43 = ObReferenceObjectByHandle(v42, 0x1F0003u, (POBJECT_TYPE)ExEventObjectType, 1, &Object, 0);
          v29 = (unsigned int)Object;
          *(_QWORD *)(v26 + 64) = Object;
          v17 = v43;
          if ( v43 < 0 )
          {
            WdLogSingleEntry1(3, v43);
            WdLogGlobalForLineNumber = 10884;
            goto LABEL_40;
          }
        }
      }
      else
      {
        if ( (unsigned int)(*a3 - 5) >= 2 )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 10945;
          v17 = -1073741811;
LABEL_40:
          ExFreePoolWithTag((PVOID)v26, 0);
          return v17;
        }
        v32 = a3[1];
        *(_BYTE *)(v26 + 25) = 1;
        v30 = v32 & 0x80;
        *(_DWORD *)(v26 + 48) = 5 - (v31 != 6);
        v29 = v32 >> 10;
        LOBYTE(v29) = v29 & 1;
        *(_BYTE *)(v26 + 31) = v30 != 0;
        v33 = a9;
        *(_BYTE *)(v26 + 26) = v29;
        if ( v33 )
        {
          v37 = v33[1];
          *(_OWORD *)(v26 + 64) = *v33;
          v38 = v33[2];
          *(_OWORD *)(v26 + 80) = v37;
          v39 = v33[3];
          v27 = *(_DWORD *)(a2 + 420) == 7;
          *(_BYTE *)(v26 + 30) = *(_BYTE *)(a2 + 428) & 1;
          *(_OWORD *)(v26 + 96) = v38;
          *(_BYTE *)(v26 + 56) = v27;
          *(_OWORD *)(v26 + 112) = v39;
        }
        else
        {
          if ( *(_BYTE *)(a1 + 56) || (v34 = 0, v30) )
            v34 = 1;
          *(_BYTE *)(v26 + 30) = v34;
          v35 = 0;
          *(_DWORD *)(v26 + 116) = 16;
          if ( v31 != 6 )
            v35 = *((_QWORD *)a3 + 1);
          FenceStorageSlot = VidMmAllocateFenceStorageSlot(
                               (struct VIDMM_MONITORED_FENCE_STORAGE *)(v26 + 64),
                               a2 == 0,
                               v35,
                               v34,
                               0,
                               a12);
          if ( FenceStorageSlot < 0 )
          {
            v17 = FenceStorageSlot;
            goto LABEL_40;
          }
          *(_QWORD *)(v26 + 88) = a6;
        }
      }
    }
  }
  else
  {
    *(_DWORD *)(v26 + 48) = 6;
    *(_BYTE *)(v26 + 30) = 1;
    v27 = *(_DWORD *)(v12 + 12) == 2;
    *(_BYTE *)(v26 + 57) = *(_DWORD *)(a2 + 420) == 5;
    v48 = a9;
    v49 = a9[1];
    *(_OWORD *)(v26 + 64) = *a9;
    v50 = v48[2];
    *(_OWORD *)(v26 + 80) = v49;
    v51 = v48[3];
    v52 = a11;
    *(_OWORD *)(v26 + 96) = v50;
    *(_OWORD *)(v26 + 112) = v51;
    v53 = v52[1];
    *(_OWORD *)(v26 + 128) = *v52;
    v54 = v52[2];
    *(_OWORD *)(v26 + 144) = v53;
    v55 = v52[3];
    *(_BYTE *)(v26 + 280) = v27;
    v56 = *(_QWORD *)v12;
    *(_OWORD *)(v26 + 160) = v54;
    *(_QWORD *)(v26 + 200) = v56;
    *(_OWORD *)(v26 + 176) = v55;
  }
  *(_QWORD *)(v26 + 216) = v26 + 208;
  *(_QWORD *)(v26 + 208) = v26 + 208;
  *(_QWORD *)(v26 + 232) = v26 + 224;
  *(_QWORD *)(v26 + 224) = v26 + 224;
  *(_QWORD *)(v26 + 264) = v26 + 256;
  *(_QWORD *)(v26 + 256) = v26 + 256;
  if ( *(_BYTE *)(v26 + 28) )
  {
    *(_QWORD *)(v26 + 360) = a5;
    *(_QWORD *)(v26 + 368) = VidSchPostCrossAdapterSignal;
    VidSchiAddSyncObjectToAdapterList(a1, v26);
    VidSchiAddSyncObjectToCrossAdapterInfo(v26);
  }
  *a8 = v26;
  if ( v12 )
  {
    if ( (byte_140087201 & 1) != 0 )
      McTemplateK0pptqx_EtwWriteTransfer(
        v29,
        (unsigned int)&EventCreateNativeFence,
        v30,
        *(_QWORD *)(a1 + 16),
        v26,
        0,
        *(_DWORD *)(v12 + 16),
        *(_QWORD *)v12);
    return 0;
  }
  if ( bTracingEnabled )
  {
    v57 = *(_QWORD *)(a1 + 16);
    if ( *a3 == 1 )
    {
      if ( (byte_140087201 & 1) != 0 )
        McTemplateK0ppqqpt_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          (unsigned int)&EventCreateSynchronizationMutex,
          0,
          v57,
          v26,
          0,
          *v22,
          a3[18],
          a3[2]);
      return 0;
    }
    if ( *a3 == 2 )
    {
      if ( (byte_140087201 & 1) != 0 )
        McTemplateK0ppqqpqq_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          (unsigned int)&EventCreateSemaphore,
          0,
          v57,
          v26,
          0,
          *v22,
          a3[18],
          a3[2],
          a3[3]);
      return 0;
    }
    if ( *a3 == 3 )
    {
      if ( (byte_140087201 & 1) != 0 )
      {
        v60 = &EventCreateFence;
        goto LABEL_70;
      }
    }
    else
    {
      if ( *a3 == 4 )
      {
        if ( (byte_140087201 & 1) != 0 )
          McTemplateK0ppqqpx_EtwWriteTransfer(
            (unsigned int)&DxgkControlGuid_Context,
            (unsigned int)&EventCreateCPUNotification,
            0,
            v57,
            v26,
            0,
            *v22,
            a3[18],
            *((_QWORD *)a3 + 1));
        return 0;
      }
      if ( *a3 != 5 )
      {
        if ( *a3 == 6 )
        {
          if ( (byte_140087201 & 1) != 0 )
            McTemplateK0ppqqppqi_EtwWriteTransfer(
              (unsigned int)&DxgkControlGuid_Context,
              (unsigned int)&EventCreatePeriodicMonitoredFence,
              0,
              v57,
              v26,
              0,
              *v22,
              a3[18],
              a3[2],
              a3[3],
              *((_QWORD *)a3 + 2));
        }
        else
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 1061;
          DxgkLogInternalTriageEvent(v58, 262146, v59, (unsigned int)L"FALSE", 1061, 0, 0, 0);
        }
        return 0;
      }
      if ( (byte_140087201 & 1) != 0 )
      {
        v60 = &EventCreateMonitoredFence;
LABEL_70:
        McTemplateK0ppqqpx_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          (_DWORD)v60,
          0,
          v57,
          v26,
          0,
          *v22,
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
0x14012a910  mov     [rsp+arg_0], rbx
0x14012a915  mov     [rsp+arg_8], rdx
0x14012a91a  push    rbp
0x14012a91b  push    rsi
0x14012a91c  push    rdi
0x14012a91d  push    r12
0x14012a91f  push    r13
0x14012a921  push    r14
0x14012a923  push    r15
0x14012a925  sub     rsp, 60h
0x14012a929  mov     r15, [rsp+98h+arg_48]
0x14012a931  xor     esi, esi
0x14012a933  mov     edi, r9d
0x14012a936  mov     r14, r8
0x14012a939  mov     rbp, rdx
0x14012a93c  mov     r13, rcx
0x14012a93f  test    r8, r8
0x14012a942  jz      short loc_14012A99C
0x14012a944  test    r15, r15
0x14012a947  jz      loc_14012A9CE
0x14012a94d  mov     rbx, 0FFFFFFFFC000000Dh
0x14012a954  lea     ecx, [rsi+1]
0x14012a957  mov     rdx, rbx
0x14012a95a  call    cs:__imp_WdLogSingleEntry1
0x14012a961  nop     dword ptr [rax+rax+00h]
0x14012a966  lea     r9, aCannotCreateVi; "Cannot create vidschsyncobject using bo"...
0x14012a96d  mov     cs:WdLogGlobalForLineNumber, 29E8h
0x14012a977  mov     [rsp+98h+var_60], rsi
0x14012a97c  mov     edx, 40000h
0x14012a981  mov     qword ptr [rsp+98h+var_68], rsi
0x14012a986  mov     [rsp+98h+HandleInformation], rsi
0x14012a98b  mov     [rsp+98h+Object], rbx
0x14012a990  call    DxgkLogInternalTriageEvent
0x14012a995  mov     eax, ebx
0x14012a997  jmp     loc_14012B13A
0x14012a99c  test    r15, r15
0x14012a99f  jnz     short loc_14012A9CE
0x14012a9a1  mov     rbx, 0FFFFFFFFC000000Dh
0x14012a9a8  lea     ecx, [r15+1]
0x14012a9ac  mov     rdx, rbx
0x14012a9af  call    cs:__imp_WdLogSingleEntry1
0x14012a9b6  nop     dword ptr [rax+rax+00h]
0x14012a9bb  lea     r9, aCannotCreateVi_0; "Cannot create vidschsyncobject without "...
0x14012a9c2  mov     cs:WdLogGlobalForLineNumber, 29EFh
0x14012a9cc  jmp     short loc_14012A977
0x14012a9ce  mov     rax, [rsp+98h+arg_38]
0x14012a9d6  lea     r12, [r8+4]
0x14012a9da  test    r15, r15
0x14012a9dd  lea     rbx, [r15+10h]
0x14012a9e1  mov     ecx, 40h ; '@'
0x14012a9e6  mov     r8d, 38616956h
0x14012a9ec  cmovz   rbx, r12
0x14012a9f0  mov     [rax], rsi
0x14012a9f3  mov     ebx, [rbx]
0x14012a9f5  mov     eax, ebx
0x14012a9f7  and     eax, 4
0x14012a9fa  mov     dword ptr [rsp+98h+arg_10], eax
0x14012aa01  neg     eax
0x14012aa03  sbb     rdx, rdx
0x14012aa06  and     edx, 50h
0x14012aa09  add     rdx, 128h
0x14012aa10  call    cs:__imp_ExAllocatePool2
0x14012aa17  nop     dword ptr [rax+rax+00h]
0x14012aa1c  mov     rsi, rax
0x14012aa1f  test    rax, rax
0x14012aa22  jnz     short loc_14012AA47
0x14012aa24  lea     ecx, [rax+3]
0x14012aa27  call    cs:__imp_WdLogSingleEntry0
0x14012aa2e  nop     dword ptr [rax+rax+00h]
0x14012aa33  mov     eax, 0C0000017h
0x14012aa38  mov     cs:WdLogGlobalForLineNumber, 2A06h
0x14012aa42  jmp     loc_14012B13A
0x14012aa47  mov     [rax+10h], rbp
0x14012aa4b  mov     ebp, 1
0x14012aa50  mov     [rax+24h], ebp
0x14012aa53  mov     dword ptr [rax], 38616956h
0x14012aa59  mov     [rax+8], r13
0x14012aa5d  mov     dword ptr [rax+28h], 0
0x14012aa64  mov     al, bl
0x14012aa66  and     al, bpl
0x14012aa69  shr     ebx, 1Fh
0x14012aa6c  cmp     dword ptr [rsp+98h+arg_10], 0
0x14012aa74  mov     [rsi+18h], al
0x14012aa77  setnz   al
0x14012aa7a  mov     [rsi+1Bh], bl
0x14012aa7d  mov     [rsi+1Ch], al
0x14012aa80  mov     [rsi+34h], edi
0x14012aa83  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14012aa88  xor     edi, edi
0x14012aa8a  test    rax, rax
0x14012aa8d  jz      short loc_14012AAB5
0x14012aa8f  mov     ecx, [rax+198h]
0x14012aa95  shr     ecx, 8
0x14012aa98  test    bpl, cl
0x14012aa9b  jz      short loc_14012AAA1
0x14012aa9d  mov     [rsi+20h], bpl
0x14012aaa1  mov     eax, [rax+198h]
0x14012aaa7  shr     eax, 4
0x14012aaaa  test    bpl, al
0x14012aaad  jz      short loc_14012AAB5
0x14012aaaf  mov     word ptr [rsi+20h], 101h
0x14012aab5  test    r14, r14
0x14012aab8  jz      loc_14012ADE0
0x14012aabe  mov     edx, [r14]
0x14012aac1  mov     ecx, edx
0x14012aac3  sub     ecx, ebp
0x14012aac5  jz      loc_14012ADB5
0x14012aacb  sub     ecx, ebp
0x14012aacd  jz      loc_14012AD39
0x14012aad3  sub     ecx, ebp
0x14012aad5  jz      loc_14012AD19
0x14012aadb  sub     ecx, ebp
0x14012aadd  jz      loc_14012AC1E
0x14012aae3  sub     ecx, ebp
0x14012aae5  jz      short loc_14012AB12
0x14012aae7  cmp     ecx, ebp
0x14012aae9  jz      short loc_14012AB12
0x14012aaeb  mov     ecx, 3
0x14012aaf0  call    cs:__imp_WdLogSingleEntry0
0x14012aaf7  nop     dword ptr [rax+rax+00h]
0x14012aafc  mov     cs:WdLogGlobalForLineNumber, 2AC1h
0x14012ab06  mov     rbx, 0FFFFFFFFC000000Dh
0x14012ab0d  jmp     loc_14012AD03
0x14012ab12  mov     ecx, [r14+4]
0x14012ab16  lea     eax, [rdx-6]
0x14012ab19  neg     eax
0x14012ab1b  mov     [rsi+19h], bpl
0x14012ab1f  mov     r8d, ecx
0x14012ab22  sbb     eax, eax
0x14012ab24  add     eax, 5
0x14012ab27  and     r8d, 80h
0x14012ab2e  mov     [rsi+30h], eax
0x14012ab31  setnz   al
0x14012ab34  shr     ecx, 0Ah
0x14012ab37  and     cl, bpl
0x14012ab3a  mov     [rsi+1Fh], al
0x14012ab3d  mov     rax, [rsp+98h+arg_40]
0x14012ab45  mov     [rsi+1Ah], cl
0x14012ab48  test    rax, rax
0x14012ab4b  jnz     loc_14012ABD9
0x14012ab51  cmp     [r13+38h], dil
0x14012ab55  jnz     short loc_14012AB5F
0x14012ab57  mov     cl, dil
0x14012ab5a  test    r8d, r8d
0x14012ab5d  jz      short loc_14012AB62
0x14012ab5f  mov     cl, bpl
0x14012ab62  mov     [rsi+1Eh], cl
0x14012ab65  mov     r9, rdi
0x14012ab68  mov     dword ptr [rsi+74h], 10h
0x14012ab6f  cmp     edx, 6
0x14012ab72  jz      short loc_14012AB78
0x14012ab74  mov     r9, [r14+8]
0x14012ab78  cmp     [rsp+98h+arg_8], rdi
0x14012ab80  mov     rax, [rsp+98h+arg_58]
0x14012ab88  setz    dl
0x14012ab8b  mov     [rsp+98h+var_58], rax; struct VIDMM_DEVICE *
0x14012ab90  cmp     [rsi+18h], dil
0x14012ab94  mov     [rsp+98h+var_60], rdi; struct VIDMM_FENCE_STORAGE_PLACMENT *
0x14012ab99  mov     [rsp+98h+var_68], cl; char
0x14012ab9d  setnz   r8b
0x14012aba1  mov     [rsp+98h+HandleInformation], r9; __int64
0x14012aba6  lea     rcx, [rsi+40h]; struct VIDMM_MONITORED_FENCE_STORAGE *
0x14012abaa  mov     byte ptr [rsp+98h+Object], dl; char
0x14012abae  xor     r9d, r9d
0x14012abb1  mov     edx, [rsp+98h+arg_30]
0x14012abb8  call    VidMmAllocateFenceStorageSlot
0x14012abbd  test    eax, eax
0x14012abbf  jns     short loc_14012ABC8
0x14012abc1  mov     ebx, eax
0x14012abc3  jmp     loc_14012AD03
0x14012abc8  mov     rax, [rsp+98h+arg_28]
0x14012abd0  mov     [rsi+58h], rax
0x14012abd4  jmp     loc_14012AE72
0x14012abd9  movups  xmm0, xmmword ptr [rax]
0x14012abdc  mov     rdx, [rsp+98h+arg_8]
0x14012abe4  movups  xmm1, xmmword ptr [rax+10h]
0x14012abe8  movups  xmmword ptr [rsi+40h], xmm0
0x14012abec  movups  xmm0, xmmword ptr [rax+20h]
0x14012abf0  movups  xmmword ptr [rsi+50h], xmm1
0x14012abf4  movups  xmm1, xmmword ptr [rax+30h]
0x14012abf8  mov     al, [rdx+1ACh]
0x14012abfe  and     al, bpl
0x14012ac01  cmp     dword ptr [rdx+1A4h], 7
0x14012ac08  mov     [rsi+1Eh], al
0x14012ac0b  setz    al
0x14012ac0e  movups  xmmword ptr [rsi+60h], xmm0
0x14012ac12  mov     [rsi+38h], al
0x14012ac15  movups  xmmword ptr [rsi+70h], xmm1
0x14012ac19  jmp     loc_14012AE72
0x14012ac1e  mov     eax, [r14+4]
0x14012ac22  test    bpl, al
0x14012ac25  jz      short loc_14012AC73
0x14012ac27  mov     rbx, 0FFFFFFFFC000000Dh
0x14012ac2e  mov     ecx, ebp
0x14012ac30  mov     rdx, rbx
0x14012ac33  call    cs:__imp_WdLogSingleEntry1
0x14012ac3a  nop     dword ptr [rax+rax+00h]
0x14012ac3f  mov     [rsp+98h+var_60], rdi
0x14012ac44  lea     r9, aCpunotificatio; "CPUNotification.Event is not sharable, "...
0x14012ac4b  mov     qword ptr [rsp+98h+var_68], rdi
0x14012ac50  mov     edx, 40000h
0x14012ac55  mov     [rsp+98h+HandleInformation], rdi
0x14012ac5a  mov     [rsp+98h+Object], rbx
0x14012ac5f  mov     cs:WdLogGlobalForLineNumber, 2A67h
0x14012ac69  call    DxgkLogInternalTriageEvent
0x14012ac6e  jmp     loc_14012AD03
0x14012ac73  mov     rcx, [r14+8]; Handle
0x14012ac77  mov     dword ptr [rsi+30h], 3
0x14012ac7e  mov     [rsi+19h], dil
0x14012ac82  cmp     [rsi+20h], dil
0x14012ac86  jz      short loc_14012AC96
0x14012ac88  mov     [rsi+48h], rcx
0x14012ac8c  call    DxgkAcquireGuestCpuEvent
0x14012ac91  jmp     loc_14012AE72
0x14012ac96  mov     r8, cs:ExEventObjectType
0x14012ac9d  lea     rax, [rsp+98h+arg_10]
0x14012aca5  mov     [rsp+98h+HandleInformation], rdi; HandleInformation
0x14012acaa  mov     r9b, bpl; AccessMode
0x14012acad  mov     edx, 1F0003h; DesiredAccess
0x14012acb2  mov     [rsp+98h+arg_10], rdi
0x14012acba  mov     [rsp+98h+Object], rax; Object
0x14012acbf  mov     r8, [r8]; ObjectType
0x14012acc2  call    cs:__imp_ObReferenceObjectByHandle
0x14012acc9  nop     dword ptr [rax+rax+00h]
0x14012acce  mov     rcx, [rsp+98h+arg_10]
0x14012acd6  mov     [rsi+40h], rcx
0x14012acda  movsxd  rbx, eax
0x14012acdd  test    eax, eax
0x14012acdf  jns     loc_14012AE72
0x14012ace5  mov     rdx, rbx
0x14012ace8  mov     ecx, 3
0x14012aced  call    cs:__imp_WdLogSingleEntry1
0x14012acf4  nop     dword ptr [rax+rax+00h]
0x14012acf9  mov     cs:WdLogGlobalForLineNumber, 2A84h
0x14012ad03  xor     edx, edx; Tag
0x14012ad05  mov     rcx, rsi; P
0x14012ad08  call    cs:__imp_ExFreePoolWithTag
0x14012ad0f  nop     dword ptr [rax+rax+00h]
0x14012ad14  jmp     loc_14012A995
0x14012ad19  mov     rax, [r14+8]
0x14012ad1d  mov     [rsi+40h], rax
0x14012ad21  mov     [rsi+48h], rax
0x14012ad25  mov     [rsi+50h], rax
0x14012ad29  mov     dword ptr [rsi+30h], 2
0x14012ad30  mov     [rsi+19h], bpl
0x14012ad34  jmp     loc_14012AE72
0x14012ad39  mov     ecx, [r14+8]
0x14012ad3d  mov     eax, [r14+0Ch]
0x14012ad41  cmp     eax, ecx
0x14012ad43  jbe     short loc_14012ADA0
0x14012ad45  mov     ecx, ebp
0x14012ad47  call    cs:__imp_WdLogSingleEntry0
0x14012ad4e  nop     dword ptr [rax+rax+00h]
0x14012ad53  mov     [rsp+98h+var_60], rdi
0x14012ad58  lea     r9, aCanTInitialize; "Can't initialize semaphore to larger va"...
0x14012ad5f  mov     eax, 2A51h
0x14012ad64  mov     qword ptr [rsp+98h+var_68], rdi
0x14012ad69  mov     [rsp+98h+HandleInformation], rdi
0x14012ad6e  mov     edx, 40000h
0x14012ad73  mov     cs:WdLogGlobalForLineNumber, eax
0x14012ad79  mov     [rsp+98h+Object], rax
0x14012ad7e  call    DxgkLogInternalTriageEvent
0x14012ad83  xor     edx, edx; Tag
0x14012ad85  mov     rcx, rsi; P
0x14012ad88  call    cs:__imp_ExFreePoolWithTag
0x14012ad8f  nop     dword ptr [rax+rax+00h]
0x14012ad94  mov     rax, 0FFFFFFFFC000000Dh
0x14012ad9b  jmp     loc_14012B13A
0x14012ada0  mov     [rsi+30h], ebp
0x14012ada3  mov     [rsi+19h], dil
0x14012ada7  mov     [rsi+40h], eax
0x14012adaa  mov     [rsi+48h], eax
0x14012adad  mov     [rsi+44h], ecx
0x14012adb0  jmp     loc_14012AE72
0x14012adb5  mov     [rsi+30h], edi
0x14012adb8  mov     [rsi+19h], dil
0x14012adbc  cmp     [r14+8], edi
0x14012adc0  jz      short loc_14012ADCF
0x14012adc2  mov     [rsi+40h], rdi
0x14012adc6  mov     [rsi+48h], rdi
0x14012adca  jmp     loc_14012AE72
0x14012adcf  or      rax, 0FFFFFFFFFFFFFFFFh
0x14012add3  mov     [rsi+40h], rax
0x14012add7  mov     [rsi+48h], rax
0x14012addb  jmp     loc_14012AE72
0x14012ade0  mov     rdx, [rsp+98h+arg_8]
0x14012ade8  mov     dword ptr [rsi+30h], 6
0x14012adef  mov     [rsi+1Eh], bpl
0x14012adf3  cmp     dword ptr [rdx+1A4h], 5
0x14012adfa  setz    al
0x14012adfd  cmp     dword ptr [r15+0Ch], 2
0x14012ae02  mov     [rsi+39h], al
0x14012ae05  mov     rax, [rsp+98h+arg_40]
0x14012ae0d  movups  xmm0, xmmword ptr [rax]
0x14012ae10  movups  xmm1, xmmword ptr [rax+10h]
0x14012ae14  movups  xmmword ptr [rsi+40h], xmm0
0x14012ae18  movups  xmm0, xmmword ptr [rax+20h]
0x14012ae1c  movups  xmmword ptr [rsi+50h], xmm1
0x14012ae20  movups  xmm1, xmmword ptr [rax+30h]
0x14012ae24  mov     rax, [rsp+98h+arg_50]
  ... truncated ...
```
