# RefsGetRetrievalPointers

- ea: `0x1c01ab2f8`
- end: `0x1c01abfee`
- name: `RefsGetRetrievalPointers`
- size: `3318`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c015c128`

## callees

- `0x1c0004300`
- `0x1c0004484`
- `0x1c00049a0`
- `0x1c0004a30`
- `0x1c0005450`
- `0x1c0005768`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c009df4c`
- `0x1c00b1cc4`
- `0x1c00b26f0`
- `0x1c00b2850`
- `0x1c015ac58`
- `0x1c016154c`
- `0x1c01ab2f8`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c01abe26`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01abfda`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01abe26`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01abfda`
- `ntoskrnl!ProbeForWrite` at `0x1c01ab776`
- `ntoskrnl!ProbeForWrite` at `0x1c01ab776`
- `ntoskrnl!ProbeForRead` at `0x1c01ab759`
- `ntoskrnl!ProbeForRead` at `0x1c01ab759`

## pseudocode

```c
__int64 __fastcall RefsGetRetrievalPointers(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char v4; // di
  __int64 v7; // r12
  unsigned int v8; // ebx
  SIZE_T v9; // r14
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // r8
  unsigned int v13; // edi
  __int64 v14; // r15
  __int64 v15; // r15
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // eax
  NTSTATUS v19; // edi
  __int64 v20; // r12
  _QWORD *v21; // rax
  __int64 v22; // r14
  int v23; // eax
  unsigned __int64 v24; // r15
  CmsStream *v25; // rdx
  struct CmsTransactionContext *v26; // rcx
  int v27; // eax
  __int64 v28; // r8
  signed __int64 v29; // rdi
  _DWORD *v30; // r12
  unsigned int v31; // r9d
  __int64 v32; // rcx
  __int64 v33; // r10
  char v34; // r11
  signed __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rcx
  unsigned int v38; // r9d
  CmsStream *v39; // rdx
  int v40; // eax
  unsigned int Status; // [rsp+44h] [rbp-B4h]
  unsigned int Statusa; // [rsp+44h] [rbp-B4h]
  unsigned int Statusb; // [rsp+44h] [rbp-B4h]
  char v45; // [rsp+48h] [rbp-B0h]
  char v46; // [rsp+49h] [rbp-AFh]
  _DWORD Length[3]; // [rsp+4Ch] [rbp-ACh] BYREF
  unsigned int v48; // [rsp+58h] [rbp-A0h]
  unsigned int v49; // [rsp+5Ch] [rbp-9Ch]
  __int64 v50; // [rsp+60h] [rbp-98h] BYREF
  __int64 v51[2]; // [rsp+68h] [rbp-90h] BYREF
  int v52; // [rsp+78h] [rbp-80h]
  __int64 v53; // [rsp+80h] [rbp-78h] BYREF
  volatile void *Address; // [rsp+88h] [rbp-70h]
  signed __int64 v55; // [rsp+90h] [rbp-68h]
  __int64 v56; // [rsp+98h] [rbp-60h]
  __int64 v57; // [rsp+A0h] [rbp-58h] BYREF
  __int64 v58; // [rsp+A8h] [rbp-50h]
  __int64 v59; // [rsp+B0h] [rbp-48h]
  __int64 v60; // [rsp+108h] [rbp+10h] BYREF
  char v61; // [rsp+110h] [rbp+18h]
  __int64 v62; // [rsp+118h] [rbp+20h] BYREF

  v61 = a3;
  v4 = a3;
  v50 = 0;
  v53 = 0;
  *(_QWORD *)&Length[1] = 0;
  v57 = 0;
  *(_OWORD *)v51 = 0;
  v46 = 0;
  v45 = 0;
  LOBYTE(v60) = 0;
  LOWORD(v62) = 0;
  *(_DWORD *)(a1 + 8) |= 1u;
  v7 = *(_QWORD *)(a2 + 184);
  v8 = *(_DWORD *)(v7 + 16);
  v9 = *(unsigned int *)(v7 + 8);
  v48 = *(_DWORD *)(v7 + 8);
  Address = (volatile void *)RefsMapUserBuffer(a2, a2, a3, a4);
  v10 = RefsDecodeFileObject(
          a1,
          *(_QWORD *)(v7 + 48),
          (unsigned int)&v50,
          (unsigned int)&v53,
          (__int64)&Length[1],
          (__int64)&v57,
          0);
  v52 = v10;
  if ( (unsigned int)(v10 - 2) > 2 || (v12 = 8, v8 < 8) )
  {
    v13 = -1073741811;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsExtendedCompleteRequestInternal(a1, a2, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 121, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v13;
LABEL_153:
    RefsStatusDebug(v13);
    return v13;
  }
  if ( v9 < (-(__int64)(v4 != 0) & 8uLL) + 32 )
  {
    v13 = -1073741789;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741789);
    RefsExtendedCompleteRequestInternal(a1, a2, 3221225507LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 122, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225507LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v13;
    goto LABEL_153;
  }
  if ( v10 != 4 )
    goto LABEL_38;
  if ( !v4 )
  {
    if ( (*(_WORD *)(v57 + 88) & 0x200) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 124, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225506LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741790);
      Status = -1073741790;
      goto LABEL_139;
    }
    LOBYTE(v12) = 1;
    v14 = v50;
    RefsAcquireSharedVcb(a1, v50, v12, v11);
    v46 = 1;
    if ( (*(_DWORD *)(v14 + 4) & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 125, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221226094LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741202);
      Status = -1073741202;
      goto LABEL_139;
    }
    *(_QWORD *)&Length[1] = *(_QWORD *)(v14 + 72);
    v53 = *(_QWORD *)(*(_QWORD *)&Length[1] + 120LL);
LABEL_38:
    *(_DWORD *)(a1 + 4) |= 0x10000u;
    v15 = *(_QWORD *)&Length[1];
    RefsAcquireFcbWithPaging(a1, *(_QWORD *)(*(_QWORD *)&Length[1] + 120LL), *(_QWORD *)&Length[1], 4);
    v45 = 1;
    v18 = *(_DWORD *)(v15 + 304);
    if ( (v18 & 0x10000) != 0 )
      v19 = -1073741202;
    else
      v19 = (v18 & 0x1000000) != 0 ? 0xC0000008 : 0;
    if ( v19 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          126,
          WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
          (unsigned int)v19);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(v19);
      RefsRaiseStatusInternal(a1, (unsigned int)v19);
    }
    if ( !(unsigned __int8)RefsIsFileOpen(v53, v16, v17) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 127, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225768LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741528);
      RefsRaiseStatusInternal(a1, 3221225768LL);
    }
    if ( *(_BYTE *)(a2 + 64) )
    {
      ProbeForRead(*(volatile void **)(v7 + 32), v8, 1u);
      ProbeForWrite(Address, v9, 1u);
    }
    v20 = **(_QWORD **)(v7 + 32);
    v59 = v20;
    v21 = Address;
    *(_DWORD *)Address = 0;
    v21[1] = 0;
    v22 = *(_QWORD *)&Length[1];
    v23 = *(_DWORD *)(*(_QWORD *)&Length[1] + 136LL);
    if ( (v23 & 0x20) == 0 && *(_DWORD *)(*(_QWORD *)&Length[1] + 200LL) != 160 )
    {
      RefsUpdateScbFromAttribute(a1, *(_QWORD *)&Length[1], 0);
      v23 = *(_DWORD *)(v22 + 136);
    }
    if ( (v23 & 8) != 0 || v52 != 2 )
    {
      *(_QWORD *)(a2 + 56) = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 128, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225489LL);
      }
      if ( !RefsStatusDebugEnabled )
        goto LABEL_138;
    }
    else
    {
      v24 = *(__int64 *)(v22 + 24) >> *(_BYTE *)(v50 + 464);
      v55 = v24 - 1;
      if ( v20 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            129,
            WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
            3221225485LL);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741811);
        Status = -1073741811;
        goto LABEL_139;
      }
      if ( v20 <= (__int64)(v24 - 1) )
      {
        RefsBindMinstoreTransaction(a1);
        MsEnterStream(*(_QWORD *)(v22 + 360), *(_QWORD *)(a1 + 24));
        v25 = *(CmsStream **)(v22 + 360);
        v26 = *(struct CmsTransactionContext **)(a1 + 24);
        if ( v61 )
          v27 = MsLookupAllocationCoalesceWithRefCount(v26, v25, (__int64)v51, (__int64)&v62, (__int64)&v60);
        else
          v27 = MsLookupAllocationCoalesce(v26, v25, (__int64)v51, (__int64)&v60);
        Statusa = v27;
        if ( v27 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              131,
              WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
              (unsigned int)v27);
          }
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(Statusa);
          RefsRaiseStatusInternal(a1, Statusa);
        }
        v28 = v51[1];
        v29 = v59;
        if ( v51[1] + v59 > v24 && v51[0] == -1 )
        {
          v28 = v55 - v59 + 1;
          v51[1] = v28;
        }
        v58 = v28;
        v56 = v59;
        v30 = Address;
        *((_QWORD *)Address + 1) = v59;
        v31 = 0;
        v49 = 0;
        v32 = v28;
        while ( 1 )
        {
          v33 = v28;
          v34 = v61;
          if ( v61 )
          {
            v33 = v32;
            if ( 24 * v31 + 40 > v48 )
            {
              *(_QWORD *)(a2 + 56) = (int)(24 * v31 + 16);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_D(
                  WPP_GLOBAL_Control->AttachedDevice,
                  133,
                  WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
                  2147483653LL);
              }
              if ( RefsStatusDebugEnabled )
LABEL_101:
                RefsStatusDebug(-2147483643);
LABEL_102:
              Status = -2147483643;
              goto LABEL_139;
            }
          }
          else if ( 16 * (v31 + 2) > v48 )
          {
            *(_QWORD *)(a2 + 56) = (int)(16 * (v31 + 1));
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                132,
                WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
                2147483653LL);
            }
            if ( RefsStatusDebugEnabled )
              goto LABEL_101;
            goto LABEL_102;
          }
          v35 = v29 + v33;
          if ( v61 )
          {
            v37 = 3LL * v31;
            *(_QWORD *)&v30[2 * v37 + 4] = v35;
            *(_QWORD *)&v30[2 * v37 + 6] = v51[0];
            v30[6 * v31 + 8] = (unsigned __int16)v62 + 1;
          }
          else
          {
            v36 = 2LL * v31;
            *(_QWORD *)&v30[2 * v36 + 4] = v35;
            *(_QWORD *)&v30[2 * v36 + 6] = v51[0];
          }
          v38 = v31 + 1;
          *v30 = v38;
          v49 = v38;
          v29 += v28;
          if ( v29 > v55 )
          {
            if ( v34 )
              *(_QWORD *)(a2 + 56) = (int)(24 * v38 + 16);
            else
              *(_QWORD *)(a2 + 56) = (int)(16 * (v38 + 1));
            Status = 0;
            goto LABEL_139;
          }
          v39 = *(CmsStream **)(v22 + 360);
          if ( v34 )
            v40 = MsLookupAllocationCoalesceWithRefCount(
                    *(struct CmsTransactionContext **)(a1 + 24),
                    v39,
                    (__int64)v51,
                    (__int64)&v62,
                    (__int64)&v60);
          else
            v40 = MsLookupAllocationCoalesce(
                    *(struct CmsTransactionContext **)(a1 + 24),
                    v39,
                    (__int64)v51,
                    (__int64)&v60);
          Statusb = v40;
          if ( v40 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                134,
                WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
                (unsigned int)v40);
            }
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(Statusb);
            RefsRaiseStatusInternal(a1, Statusb);
          }
          v28 = v51[1];
          if ( v56 + v51[1] + v58 > v24 )
          {
            v28 = v55 - v58 - v56 + 1;
            v51[1] = v28;
          }
          v56 = v29;
          v32 = v28;
          v58 = v28;
          v31 = v49;
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 130, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225489LL);
      }
      if ( !RefsStatusDebugEnabled )
      {
LABEL_138:
        Status = -1073741807;
        goto LABEL_139;
      }
    }
    RefsStatusDebug(-1073741807);
    goto LABEL_138;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 123, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225659LL);
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741637);
  Status = -1073741637;
LABEL_139:
  if ( v45 )
    RefsReleaseFcbWithPaging(a1, *(_QWORD *)(*(_QWORD *)&Length[1] + 120LL));
  if ( v46 )
    ExReleaseResourceLite((PERESOURCE)(v50 + 1424));
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(Status);
  RefsExtendedCompleteRequestInternal(a1, a2, Status);
  return Status;
}

```

## disassembly

```asm
0x1c01ab2f8  mov     rax, rsp
0x1c01ab2fb  mov     [rax+18h], r8b
0x1c01ab2ff  mov     [rax+8], rcx
0x1c01ab303  push    rbx
0x1c01ab304  push    rsi
0x1c01ab305  push    rdi
0x1c01ab306  push    r12
0x1c01ab308  push    r13
0x1c01ab30a  push    r14
0x1c01ab30c  push    r15
0x1c01ab30e  sub     rsp, 0C0h
0x1c01ab315  mov     dil, r8b
0x1c01ab318  mov     r13, rdx
0x1c01ab31b  mov     rsi, rcx
0x1c01ab31e  xor     r15d, r15d
0x1c01ab321  mov     [rsp+0F8h+var_98], r15
0x1c01ab326  mov     [rax-78h], r15
0x1c01ab32a  mov     qword ptr [rsp+0F8h+Length+4], r15
0x1c01ab32f  mov     [rax-58h], r15
0x1c01ab333  xorps   xmm0, xmm0
0x1c01ab336  movups  xmmword ptr [rsp+0F8h+var_90], xmm0
0x1c01ab33b  mov     [rsp+0F8h+var_B8], r15b
0x1c01ab340  mov     [rsp+0F8h+var_AF], r15b
0x1c01ab345  mov     [rsp+0F8h+var_B0], r15b
0x1c01ab34a  mov     [rax+10h], r15b
0x1c01ab34e  mov     [rax+20h], r15w
0x1c01ab353  or      dword ptr [rcx+8], 1
0x1c01ab357  mov     r12, [rdx+0B8h]
0x1c01ab35e  mov     ebx, [r12+10h]
0x1c01ab363  mov     dword ptr [rsp+0F8h+Length], ebx
0x1c01ab367  mov     r14d, [r12+8]
0x1c01ab36c  mov     [rsp+0F8h+var_A0], r14d
0x1c01ab371  mov     rcx, rdx
0x1c01ab374  call    RefsMapUserBuffer
0x1c01ab379  mov     [rsp+0F8h+Address], rax
0x1c01ab381  mov     byte ptr [rsp+0F8h+var_C8], r15b
0x1c01ab386  lea     rax, [rsp+0F8h+var_58]
0x1c01ab38e  mov     [rsp+0F8h+var_D0], rax
0x1c01ab393  lea     rax, [rsp+0F8h+Length+4]
0x1c01ab398  mov     [rsp+0F8h+var_D8], rax
0x1c01ab39d  lea     r9, [rsp+0F8h+var_78]
0x1c01ab3a5  lea     r8, [rsp+0F8h+var_98]
0x1c01ab3aa  mov     rdx, [r12+30h]
0x1c01ab3af  mov     rcx, rsi
0x1c01ab3b2  call    RefsDecodeFileObject
0x1c01ab3b7  mov     [rsp+0F8h+var_80], eax
0x1c01ab3bb  lea     ecx, [rax-2]
0x1c01ab3be  cmp     ecx, 2
0x1c01ab3c1  ja      loc_1C01ABEDC
0x1c01ab3c7  lea     r8d, [r15+8]
0x1c01ab3cb  cmp     ebx, r8d
0x1c01ab3ce  jb      loc_1C01ABEDC
0x1c01ab3d4  mov     cl, dil
0x1c01ab3d7  neg     cl
0x1c01ab3d9  sbb     rdx, rdx
0x1c01ab3dc  and     rdx, r8
0x1c01ab3df  add     rdx, 20h ; ' '
0x1c01ab3e3  cmp     r14, rdx
0x1c01ab3e6  jnb     loc_1C01AB472
0x1c01ab3ec  mov     al, cs:RefsStatusDebugEnabled
0x1c01ab3f2  mov     edi, 0C0000023h
0x1c01ab3f7  test    al, al
0x1c01ab3f9  jz      short loc_1C01AB40F
0x1c01ab3fb  mov     r8d, 177Bh
0x1c01ab401  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ab408  mov     ecx, edi; Status
0x1c01ab40a  call    RefsStatusDebug
0x1c01ab40f  mov     r8d, edi
0x1c01ab412  mov     rdx, r13
0x1c01ab415  mov     rcx, rsi
0x1c01ab418  call    RefsExtendedCompleteRequestInternal
0x1c01ab41d  lea     rax, WPP_GLOBAL_Control
0x1c01ab424  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ab42b  cmp     rcx, rax
0x1c01ab42e  jz      short loc_1C01AB459
0x1c01ab430  test    dword ptr [rcx+2Ch], 100h
0x1c01ab437  jz      short loc_1C01AB459
0x1c01ab439  mov     ebx, 4
0x1c01ab43e  cmp     [rcx+29h], bl
0x1c01ab441  jb      short loc_1C01AB459
0x1c01ab443  lea     edx, [rbx+76h]
0x1c01ab446  mov     r9d, edi
0x1c01ab449  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01ab450  mov     rcx, [rcx+18h]
0x1c01ab454  call    WPP_SF_D
0x1c01ab459  mov     cl, cs:RefsStatusDebugEnabled
0x1c01ab45f  test    cl, cl
0x1c01ab461  jz      loc_1C01ABF67
0x1c01ab467  mov     r8d, 177Ch
0x1c01ab46d  jmp     loc_1C01ABF59
0x1c01ab472  mov     ebx, 4
0x1c01ab477  cmp     eax, ebx
0x1c01ab479  jnz     loc_1C01AB610
0x1c01ab47f  test    dil, dil
0x1c01ab482  jz      short loc_1C01AB4EC
0x1c01ab484  lea     rax, WPP_GLOBAL_Control
0x1c01ab48b  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ab492  cmp     rcx, rax
0x1c01ab495  jz      short loc_1C01AB4BE
0x1c01ab497  mov     eax, [rcx+2Ch]
0x1c01ab49a  bt      eax, 8
0x1c01ab49e  jnb     short loc_1C01AB4BE
0x1c01ab4a0  cmp     [rcx+29h], bl
0x1c01ab4a3  jb      short loc_1C01AB4BE
0x1c01ab4a5  lea     edx, [rbx+77h]
0x1c01ab4a8  mov     r9d, 0C00000BBh
0x1c01ab4ae  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01ab4b5  mov     rcx, [rcx+18h]
0x1c01ab4b9  call    WPP_SF_D
0x1c01ab4be  mov     al, cs:RefsStatusDebugEnabled
0x1c01ab4c4  test    al, al
0x1c01ab4c6  jz      short loc_1C01AB4DF
0x1c01ab4c8  mov     r8d, 178Eh
0x1c01ab4ce  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ab4d5  mov     ecx, 0C00000BBh; Status
0x1c01ab4da  call    RefsStatusDebug
0x1c01ab4df  mov     [rsp+0F8h+Status], 0C00000BBh
0x1c01ab4e7  jmp     loc_1C01ABDFB
0x1c01ab4ec  mov     rax, [rsp+0F8h+var_58]
0x1c01ab4f4  movzx   ecx, word ptr [rax+58h]
0x1c01ab4f8  mov     eax, 200h
0x1c01ab4fd  test    ax, cx
0x1c01ab500  jnz     short loc_1C01AB56C
0x1c01ab502  lea     rax, WPP_GLOBAL_Control
0x1c01ab509  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ab510  cmp     rcx, rax
0x1c01ab513  jz      short loc_1C01AB53E
0x1c01ab515  mov     eax, [rcx+2Ch]
0x1c01ab518  bt      eax, 8
0x1c01ab51c  jnb     short loc_1C01AB53E
0x1c01ab51e  cmp     [rcx+29h], bl
0x1c01ab521  jb      short loc_1C01AB53E
0x1c01ab523  mov     edx, 7Ch ; '|'
0x1c01ab528  mov     r9d, 0C0000022h
0x1c01ab52e  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01ab535  mov     rcx, [rcx+18h]
0x1c01ab539  call    WPP_SF_D
0x1c01ab53e  mov     al, cs:RefsStatusDebugEnabled
0x1c01ab544  test    al, al
0x1c01ab546  jz      short loc_1C01AB55F
0x1c01ab548  mov     r8d, 1798h
0x1c01ab54e  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ab555  mov     ecx, 0C0000022h; Status
0x1c01ab55a  call    RefsStatusDebug
0x1c01ab55f  mov     [rsp+0F8h+Status], 0C0000022h
0x1c01ab567  jmp     loc_1C01ABDFB
0x1c01ab56c  mov     r8b, 1
0x1c01ab56f  mov     r15, [rsp+0F8h+var_98]
0x1c01ab574  mov     rdx, r15
0x1c01ab577  mov     rcx, rsi
0x1c01ab57a  call    RefsAcquireSharedVcb
0x1c01ab57f  mov     [rsp+0F8h+var_AF], 1
0x1c01ab584  mov     eax, [r15+4]
0x1c01ab588  test    al, 1
0x1c01ab58a  jnz     short loc_1C01AB5FB
0x1c01ab58c  lea     rax, WPP_GLOBAL_Control
0x1c01ab593  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ab59a  cmp     rcx, rax
0x1c01ab59d  jz      short loc_1C01AB5CC
0x1c01ab59f  mov     eax, [rcx+2Ch]
0x1c01ab5a2  bt      eax, 8
0x1c01ab5a6  jnb     short loc_1C01AB5CC
0x1c01ab5a8  cmp     [rcx+29h], bl
0x1c01ab5ab  jb      short loc_1C01AB5CC
0x1c01ab5ad  mov     edx, 7Dh ; '}'
0x1c01ab5b2  mov     edi, 0C000026Eh
0x1c01ab5b7  mov     r9d, edi
0x1c01ab5ba  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01ab5c1  mov     rcx, [rcx+18h]
0x1c01ab5c5  call    WPP_SF_D
0x1c01ab5ca  jmp     short loc_1C01AB5D1
0x1c01ab5cc  mov     edi, 0C000026Eh
0x1c01ab5d1  mov     al, cs:RefsStatusDebugEnabled
0x1c01ab5d7  xor     r15d, r15d
0x1c01ab5da  test    al, al
0x1c01ab5dc  jz      short loc_1C01AB5F2
0x1c01ab5de  mov     r8d, 17A5h
0x1c01ab5e4  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ab5eb  mov     ecx, edi; Status
0x1c01ab5ed  call    RefsStatusDebug
0x1c01ab5f2  mov     [rsp+0F8h+Status], edi
0x1c01ab5f6  jmp     loc_1C01ABDFB
0x1c01ab5fb  mov     r15, [r15+48h]
0x1c01ab5ff  mov     qword ptr [rsp+0F8h+Length+4], r15
0x1c01ab604  mov     rax, [r15+78h]
0x1c01ab608  mov     [rsp+0F8h+var_78], rax
0x1c01ab610  mov     edi, 10000h
0x1c01ab615  or      [rsi+4], edi
0x1c01ab618  mov     r9d, ebx
0x1c01ab61b  mov     r15, qword ptr [rsp+0F8h+Length+4]
0x1c01ab620  mov     r8, r15
0x1c01ab623  mov     rdx, [r15+78h]
0x1c01ab627  mov     rcx, rsi
0x1c01ab62a  call    RefsAcquireFcbWithPaging
0x1c01ab62f  mov     [rsp+0F8h+var_B0], 1
0x1c01ab634  mov     eax, [r15+130h]
0x1c01ab63b  test    edi, eax
0x1c01ab63d  jz      short loc_1C01AB646
0x1c01ab63f  mov     edi, 0C000026Eh
0x1c01ab644  jmp     short loc_1C01AB655
0x1c01ab646  and     eax, 1000000h
0x1c01ab64b  neg     eax
0x1c01ab64d  sbb     edi, edi
0x1c01ab64f  and     edi, 0C0000008h
0x1c01ab655  mov     [rsp+0F8h+Status], edi
0x1c01ab659  test    edi, edi
0x1c01ab65b  jns     short loc_1C01AB6C2
0x1c01ab65d  lea     rax, WPP_GLOBAL_Control
0x1c01ab664  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ab66b  cmp     rcx, rax
0x1c01ab66e  jz      short loc_1C01AB696
0x1c01ab670  mov     eax, [rcx+2Ch]
0x1c01ab673  bt      eax, 8
0x1c01ab677  jnb     short loc_1C01AB696
0x1c01ab679  cmp     [rcx+29h], bl
0x1c01ab67c  jb      short loc_1C01AB696
0x1c01ab67e  mov     edx, 7Eh ; '~'
0x1c01ab683  mov     r9d, edi
0x1c01ab686  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01ab68d  mov     rcx, [rcx+18h]
0x1c01ab691  call    WPP_SF_D
0x1c01ab696  mov     al, cs:RefsStatusDebugEnabled
0x1c01ab69c  test    al, al
0x1c01ab69e  jz      short loc_1C01AB6B6
0x1c01ab6a0  mov     r8d, 17B9h
0x1c01ab6a6  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ab6ad  mov     ecx, [rsp+0F8h+Status]; Status
0x1c01ab6b1  call    RefsStatusDebug
0x1c01ab6b6  mov     edx, [rsp+0F8h+Status]
0x1c01ab6ba  mov     rcx, rsi
0x1c01ab6bd  call    RefsRaiseStatusInternal
0x1c01ab6c2  mov     rcx, [rsp+0F8h+var_78]
0x1c01ab6ca  call    RefsIsFileOpen
0x1c01ab6cf  test    al, al
0x1c01ab6d1  jnz     short loc_1C01AB73E
0x1c01ab6d3  lea     rax, WPP_GLOBAL_Control
0x1c01ab6da  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ab6e1  cmp     rcx, rax
0x1c01ab6e4  jz      short loc_1C01AB70F
0x1c01ab6e6  mov     eax, [rcx+2Ch]
0x1c01ab6e9  bt      eax, 8
0x1c01ab6ed  jnb     short loc_1C01AB70F
0x1c01ab6ef  cmp     [rcx+29h], bl
0x1c01ab6f2  jb      short loc_1C01AB70F
0x1c01ab6f4  mov     edx, 7Fh
0x1c01ab6f9  mov     r9d, 0C0000128h
0x1c01ab6ff  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01ab706  mov     rcx, [rcx+18h]
0x1c01ab70a  call    WPP_SF_D
0x1c01ab70f  mov     al, cs:RefsStatusDebugEnabled
0x1c01ab715  test    al, al
0x1c01ab717  jz      short loc_1C01AB730
0x1c01ab719  mov     r8d, 17BEh
0x1c01ab71f  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ab726  mov     ecx, 0C0000128h; Status
0x1c01ab72b  call    RefsStatusDebug
0x1c01ab730  mov     edx, 0C0000128h
0x1c01ab735  mov     rcx, rsi
0x1c01ab738  call    RefsRaiseStatusInternal
0x1c01ab73d  nop
0x1c01ab73e  mov     [rsp+0F8h+var_B8], 1
0x1c01ab743  cmp     byte ptr [r13+40h], 0
0x1c01ab748  jz      short loc_1C01AB782
0x1c01ab74a  mov     edx, dword ptr [rsp+0F8h+Length]; Length
0x1c01ab74e  mov     r8d, 1; Alignment
0x1c01ab754  mov     rcx, [r12+20h]; Address
0x1c01ab759  call    cs:__imp_ProbeForRead
0x1c01ab760  nop     dword ptr [rax+rax+00h]
0x1c01ab765  mov     r8d, 1; Alignment
0x1c01ab76b  mov     rdx, r14; Length
0x1c01ab76e  mov     rcx, [rsp+0F8h+Address]; Address
0x1c01ab776  call    cs:__imp_ProbeForWrite
0x1c01ab77d  nop     dword ptr [rax+rax+00h]
0x1c01ab782  mov     rax, [r12+20h]
0x1c01ab787  mov     r12, [rax]
0x1c01ab78a  mov     [rsp+0F8h+var_48], r12
0x1c01ab792  mov     rax, [rsp+0F8h+Address]
0x1c01ab79a  and     dword ptr [rax], 0
0x1c01ab79d  and     qword ptr [rax+8], 0
0x1c01ab7a2  mov     [rsp+0F8h+var_B8], 0
0x1c01ab7a7  mov     r14, qword ptr [rsp+0F8h+Length+4]
0x1c01ab7ac  mov     eax, [r14+88h]
0x1c01ab7b3  test    al, 20h
0x1c01ab7b5  jnz     short loc_1C01AB7D9
0x1c01ab7b7  cmp     dword ptr [r14+0C8h], 0A0h
0x1c01ab7c2  jz      short loc_1C01AB7D9
0x1c01ab7c4  xor     r8d, r8d
0x1c01ab7c7  mov     rdx, r14
0x1c01ab7ca  mov     rcx, rsi
0x1c01ab7cd  call    RefsUpdateScbFromAttribute
0x1c01ab7d2  mov     eax, [r14+88h]
0x1c01ab7d9  test    al, 8
0x1c01ab7db  jnz     loc_1C01ABD8F
0x1c01ab7e1  cmp     [rsp+0F8h+var_80], 2
0x1c01ab7e6  jnz     loc_1C01ABD8F
0x1c01ab7ec  mov     rcx, [rsp+0F8h+var_98]
0x1c01ab7f1  test    dword ptr [rcx+4], 2000000h
0x1c01ab7f8  jnz     short loc_1C01AB810
0x1c01ab7fa  mov     eax, [r15+130h]
0x1c01ab801  test    al, 2
  ... truncated ...
```
