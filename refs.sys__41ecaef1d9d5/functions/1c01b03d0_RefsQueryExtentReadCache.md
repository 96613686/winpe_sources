# RefsQueryExtentReadCache

- ea: `0x1c01b03d0`
- end: `0x1c01b0f5e`
- name: `RefsQueryExtentReadCache`
- size: `2958`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
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
- `0x1c0010b30`
- `0x1c0013f90`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c009df4c`
- `0x1c00b15cc`
- `0x1c00b1cc4`
- `0x1c015ac58`
- `0x1c016154c`
- `0x1c01b03d0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c01b0d7a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01b0f4a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01b0d7a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01b0f4a`
- `ntoskrnl!ProbeForWrite` at `0x1c01b0815`
- `ntoskrnl!ProbeForWrite` at `0x1c01b0815`
- `ntoskrnl!ProbeForRead` at `0x1c01b07f7`
- `ntoskrnl!ProbeForRead` at `0x1c01b07f7`

## pseudocode

```c
__int64 __fastcall RefsQueryExtentReadCache(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // r14
  SIZE_T v7; // r13
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // edi
  __int64 v13; // r15
  __int64 v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // eax
  NTSTATUS v18; // edi
  __int64 v19; // rdi
  _QWORD *v20; // rax
  __int64 v21; // r14
  int v22; // eax
  unsigned __int64 v23; // r13
  signed __int64 v24; // r15
  SIZE_T v25; // r14
  __int128 v26; // xmm0
  __int64 v27; // r15
  SIZE_T v28; // rcx
  SIZE_T v29; // rdi
  _QWORD *v30; // rax
  unsigned int Status; // [rsp+54h] [rbp-F4h]
  int Statusa; // [rsp+54h] [rbp-F4h]
  int Statusb; // [rsp+54h] [rbp-F4h]
  char v35; // [rsp+58h] [rbp-F0h]
  char v36; // [rsp+59h] [rbp-EFh]
  _BYTE v37[14]; // [rsp+5Ah] [rbp-EEh] BYREF
  __int64 v38; // [rsp+68h] [rbp-E0h] BYREF
  SIZE_T Length; // [rsp+70h] [rbp-D8h]
  SIZE_T v40; // [rsp+78h] [rbp-D0h]
  __int64 v41; // [rsp+80h] [rbp-C8h]
  unsigned int v42; // [rsp+88h] [rbp-C0h]
  __int64 v43; // [rsp+90h] [rbp-B8h] BYREF
  __int64 v44; // [rsp+98h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+A0h] [rbp-A8h] BYREF
  __int64 v46; // [rsp+A8h] [rbp-A0h] BYREF
  volatile void *Address; // [rsp+B0h] [rbp-98h]
  __int64 v48; // [rsp+B8h] [rbp-90h]
  __int128 v49; // [rsp+C0h] [rbp-88h]
  __int64 v50; // [rsp+D0h] [rbp-78h]
  __int64 v51; // [rsp+D8h] [rbp-70h] BYREF
  SIZE_T v52; // [rsp+E0h] [rbp-68h]
  unsigned __int64 v53; // [rsp+E8h] [rbp-60h]
  _QWORD v54[3]; // [rsp+F0h] [rbp-58h] BYREF
  __int128 v55; // [rsp+108h] [rbp-40h] BYREF

  v48 = a1;
  v38 = 0;
  v43 = 0;
  *(_QWORD *)&v37[6] = 0;
  v51 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v55 = 0;
  v36 = 0;
  v35 = 0;
  *(_DWORD *)v37 = 0;
  *(_DWORD *)(a1 + 8) |= 1u;
  v6 = *(_QWORD *)(a2 + 184);
  v7 = *(unsigned int *)(v6 + 16);
  v8 = *(_DWORD *)(v6 + 8);
  LODWORD(Length) = v8;
  Address = (volatile void *)RefsMapUserBuffer(a2, a2, a3, a4);
  v9 = RefsDecodeFileObject(
         a1,
         *(_QWORD *)(v6 + 48),
         (unsigned int)&v38,
         (unsigned int)&v43,
         (__int64)&v37[6],
         (__int64)&v51,
         0);
  LODWORD(v41) = v9;
  if ( (unsigned int)(v9 - 2) > 2 || (unsigned int)v7 < 0x10 )
  {
    v12 = -1073741811;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsExtendedCompleteRequestInternal(a1, a2, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 155, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v12;
LABEL_124:
    RefsStatusDebug(v12);
    return v12;
  }
  if ( v8 < 0x18 )
  {
    v12 = -1073741789;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741789);
    RefsExtendedCompleteRequestInternal(a1, a2, 3221225507LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 156, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225507LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v12;
    goto LABEL_124;
  }
  v13 = v38;
  v42 = 1 << *(_DWORD *)(v38 + 464);
  if ( v9 == 4 )
  {
    if ( (*(_WORD *)(v51 + 88) & 0x200) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 157, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225506LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741790);
      Status = -1073741790;
      goto LABEL_110;
    }
    LOBYTE(v10) = 1;
    RefsAcquireSharedVcb(a1, v38, v10, v11);
    v36 = 1;
    if ( (*(_DWORD *)(v13 + 4) & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 158, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221226094LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741202);
      Status = -1073741202;
      goto LABEL_110;
    }
    *(_QWORD *)&v37[6] = *(_QWORD *)(v13 + 72);
    v43 = *(_QWORD *)(*(_QWORD *)&v37[6] + 120LL);
  }
  *(_DWORD *)(a1 + 4) |= 0x10000u;
  v14 = *(_QWORD *)&v37[6];
  RefsAcquireFcbWithPaging(a1, *(_QWORD *)(*(_QWORD *)&v37[6] + 120LL), *(_QWORD *)&v37[6], 4);
  v35 = 1;
  v17 = *(_DWORD *)(v14 + 304);
  if ( (v17 & 0x10000) != 0 )
    v18 = -1073741202;
  else
    v18 = (v17 & 0x1000000) != 0 ? 0xC0000008 : 0;
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        159,
        WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
        (unsigned int)v18);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(v18);
    RefsRaiseStatusInternal(a1, (unsigned int)v18);
  }
  if ( !(unsigned __int8)RefsIsFileOpen(v43, v15, v16) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 160, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225768LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741528);
    RefsRaiseStatusInternal(a1, 3221225768LL);
  }
  if ( *(_BYTE *)(a2 + 64) )
  {
    ProbeForRead(*(volatile void **)(v6 + 32), v7, 1u);
    ProbeForWrite(Address, (unsigned int)Length, 1u);
  }
  Length = **(_QWORD **)(v6 + 32);
  v19 = *(_QWORD *)(*(_QWORD *)(v6 + 32) + 8LL);
  v54[2] = v19;
  v20 = Address;
  *(_QWORD *)Address = 0;
  v20[1] = 0;
  v20[2] = 0;
  v49 = 0;
  v50 = 0;
  v21 = *(_QWORD *)&v37[6];
  v22 = *(_DWORD *)(*(_QWORD *)&v37[6] + 136LL);
  if ( (v22 & 0x20) == 0 && *(_DWORD *)(*(_QWORD *)&v37[6] + 200LL) != 160 )
  {
    RefsUpdateScbFromAttribute(a1, *(_QWORD *)&v37[6], 0);
    v22 = *(_DWORD *)(v21 + 136);
  }
  if ( (v22 & 8) != 0 || (_DWORD)v41 != 2 )
  {
    *(_QWORD *)(a2 + 56) = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 161, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225489LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_109;
  }
  else
  {
    v23 = *(__int64 *)(*(_QWORD *)&v37[6] + 24LL) >> *(_BYTE *)(v13 + 464);
    v24 = v23 - 1;
    v53 = v23 - 1;
    v25 = Length;
    if ( (Length & 0x8000000000000000uLL) != 0LL || v19 <= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 162, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741811);
      Status = -1073741811;
      goto LABEL_110;
    }
    if ( (__int64)Length <= v24 )
    {
      RefsBindMinstoreTransaction(a1);
      v41 = *(_QWORD *)&v37[6];
      MsEnterStream(*(_QWORD *)(*(_QWORD *)&v37[6] + 360LL), *(_QWORD *)(a1 + 24));
      v40 = v19;
      if ( v19 > v24 && (v24 != v25 || v19 > 1) )
      {
        v19 = v23 - 1;
        v40 = v23 - 1;
      }
      v52 = v25;
      v26 = 0;
      v27 = v41;
      while ( v19 > 0 )
      {
        Statusa = MsLookupAllocation(
                    *(struct CmsTransactionContext **)(a1 + 24),
                    *(CmsStream **)(v27 + 360),
                    0,
                    (__int64)&v55,
                    (__int64)&v37[3],
                    (__int64)&v37[2],
                    (__int64)&v37[1],
                    (__int64)v37);
        if ( Statusa < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              164,
              WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
              (unsigned int)Statusa);
          }
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(Statusa);
          RefsRaiseStatusInternal(a1, (unsigned int)Statusa);
        }
        v28 = *((_QWORD *)&v55 + 1);
        if ( *((_QWORD *)&v55 + 1) + Length > v23 && (_QWORD)v55 == -1 )
        {
          v28 = v53 - Length + 1;
          *((_QWORD *)&v55 + 1) = v28;
        }
        v29 = v40;
        if ( v28 > v40 )
          v28 = v40;
        *((_QWORD *)&v55 + 1) = v28;
        if ( (_QWORD)v55 != -1 )
        {
          v44 = 0;
          v45 = 0;
          v46 = 0;
          v54[0] = v42 * (_QWORD)v55;
          v54[1] = v42 * v28;
          Statusb = MsCheckRangeForReadCache(*(_QWORD *)(v38 + 104), v54[0], v54, &v44, &v45, &v46);
          if ( Statusb < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                165,
                WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
                (unsigned int)Statusb);
            }
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(Statusb);
            RefsRaiseStatusInternal(a1, (unsigned int)Statusb);
          }
          *(_QWORD *)&v49 = v44 + v49;
          *((_QWORD *)&v49 + 1) += v45;
          v50 += v46;
          v29 = v40;
          v28 = *((_QWORD *)&v55 + 1);
        }
        v52 += v28;
        v19 = v29 - v28;
        v40 = v19;
        v26 = v49;
      }
      v30 = Address;
      *(_OWORD *)Address = v26;
      v30[2] = v50;
      *(_QWORD *)(a2 + 56) = 24;
      Status = 0;
      goto LABEL_110;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 163, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225489LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_109;
  }
  RefsStatusDebug(-1073741807);
LABEL_109:
  Status = -1073741807;
LABEL_110:
  if ( v35 )
    RefsReleaseFcbWithPaging(a1, *(_QWORD *)(*(_QWORD *)&v37[6] + 120LL));
  if ( v36 )
    ExReleaseResourceLite((PERESOURCE)(v38 + 1424));
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(Status);
  RefsExtendedCompleteRequestInternal(a1, a2, Status);
  return Status;
}

```

## disassembly

```asm
0x1c01b03d0  mov     r11, rsp
0x1c01b03d3  mov     [r11+18h], rbx
0x1c01b03d7  mov     [r11+20h], rsi
0x1c01b03db  push    rdi
0x1c01b03dc  push    r12
0x1c01b03de  push    r13
0x1c01b03e0  push    r14
0x1c01b03e2  push    r15
0x1c01b03e4  sub     rsp, 120h
0x1c01b03eb  mov     rax, cs:__security_cookie
0x1c01b03f2  xor     rax, rsp
0x1c01b03f5  mov     [rsp+148h+var_30], rax
0x1c01b03fd  mov     r12, rdx
0x1c01b0400  mov     rsi, rcx
0x1c01b0403  mov     [rsp+148h+var_90], rcx
0x1c01b040b  xor     edi, edi
0x1c01b040d  mov     [rsp+148h+var_E0], rdi
0x1c01b0412  mov     [r11-0B8h], rdi
0x1c01b0419  mov     qword ptr [rsp+148h+var_EE+6], rdi
0x1c01b041e  mov     [r11-70h], rdi
0x1c01b0422  mov     [r11-0B0h], rdi
0x1c01b0429  mov     [r11-0A8h], rdi
0x1c01b0430  mov     [r11-0A0h], rdi
0x1c01b0437  xorps   xmm0, xmm0
0x1c01b043a  movups  xmmword ptr [r11-40h], xmm0
0x1c01b043f  mov     [rsp+148h+var_F8], dil
0x1c01b0444  mov     [rsp+148h+var_EF], dil
0x1c01b0449  mov     [rsp+148h+var_F0], dil
0x1c01b044e  mov     [rsp+148h+var_EE+3], dil
0x1c01b0453  mov     [rsp+148h+var_EE+2], dil
0x1c01b0458  mov     [rsp+148h+var_EE+1], dil
0x1c01b045d  mov     [rsp+148h+var_EE], dil
0x1c01b0462  or      dword ptr [rcx+8], 1
0x1c01b0466  mov     r14, [rdx+0B8h]
0x1c01b046d  mov     r13d, [r14+10h]
0x1c01b0471  mov     ebx, [r14+8]
0x1c01b0475  mov     dword ptr [rsp+148h+Length], ebx
0x1c01b0479  mov     rcx, rdx
0x1c01b047c  call    RefsMapUserBuffer
0x1c01b0481  mov     [rsp+148h+Address], rax
0x1c01b0489  mov     byte ptr [rsp+148h+var_118], dil
0x1c01b048e  lea     rax, [rsp+148h+var_70]
0x1c01b0496  mov     [rsp+148h+var_120], rax
0x1c01b049b  lea     rax, [rsp+148h+var_EE+6]
0x1c01b04a0  mov     [rsp+148h+var_128], rax; __int64
0x1c01b04a5  lea     r9, [rsp+148h+var_B8]
0x1c01b04ad  lea     r8, [rsp+148h+var_E0]
0x1c01b04b2  mov     rdx, [r14+30h]
0x1c01b04b6  mov     rcx, rsi
0x1c01b04b9  call    RefsDecodeFileObject
0x1c01b04be  mov     dword ptr [rsp+148h+var_C8], eax
0x1c01b04c5  lea     ecx, [rax-2]
0x1c01b04c8  cmp     ecx, 2
0x1c01b04cb  ja      loc_1C01B0E30
0x1c01b04d1  cmp     r13d, 10h
0x1c01b04d5  jb      loc_1C01B0E30
0x1c01b04db  cmp     ebx, 18h
0x1c01b04de  jnb     loc_1C01B056C
0x1c01b04e4  mov     al, cs:RefsStatusDebugEnabled
0x1c01b04ea  mov     edi, 0C0000023h
0x1c01b04ef  test    al, al
0x1c01b04f1  jz      short loc_1C01B0507
0x1c01b04f3  mov     r8d, 1B88h
0x1c01b04f9  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01b0500  mov     ecx, edi; Status
0x1c01b0502  call    RefsStatusDebug
0x1c01b0507  mov     r8d, edi
0x1c01b050a  mov     rdx, r12
0x1c01b050d  mov     rcx, rsi
0x1c01b0510  call    RefsExtendedCompleteRequestInternal
0x1c01b0515  lea     rax, WPP_GLOBAL_Control
0x1c01b051c  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01b0523  cmp     rcx, rax
0x1c01b0526  jz      short loc_1C01B0553
0x1c01b0528  test    dword ptr [rcx+2Ch], 100h
0x1c01b052f  jz      short loc_1C01B0553
0x1c01b0531  mov     ebx, 4
0x1c01b0536  cmp     [rcx+29h], bl
0x1c01b0539  jb      short loc_1C01B0553
0x1c01b053b  mov     edx, 9Ch
0x1c01b0540  mov     r9d, edi
0x1c01b0543  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01b054a  mov     rcx, [rcx+18h]
0x1c01b054e  call    WPP_SF_D
0x1c01b0553  mov     cl, cs:RefsStatusDebugEnabled
0x1c01b0559  test    cl, cl
0x1c01b055b  jz      loc_1C01B0EBD
0x1c01b0561  mov     r8d, 1B89h
0x1c01b0567  jmp     loc_1C01B0EAF
0x1c01b056c  mov     r15, [rsp+148h+var_E0]
0x1c01b0571  mov     ecx, [r15+1D0h]
0x1c01b0578  mov     edx, 1
0x1c01b057d  shl     edx, cl
0x1c01b057f  mov     [rsp+148h+var_C0], edx
0x1c01b0586  mov     ebx, 4
0x1c01b058b  cmp     eax, ebx
0x1c01b058d  jnz     loc_1C01B06B1
0x1c01b0593  mov     rax, [rsp+148h+var_70]
0x1c01b059b  movzx   ecx, word ptr [rax+58h]
0x1c01b059f  mov     eax, 200h
0x1c01b05a4  test    ax, cx
0x1c01b05a7  jnz     short loc_1C01B0613
0x1c01b05a9  lea     rax, WPP_GLOBAL_Control
0x1c01b05b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01b05b7  cmp     rcx, rax
0x1c01b05ba  jz      short loc_1C01B05E5
0x1c01b05bc  mov     eax, [rcx+2Ch]
0x1c01b05bf  bt      eax, 8
0x1c01b05c3  jnb     short loc_1C01B05E5
0x1c01b05c5  cmp     [rcx+29h], bl
0x1c01b05c8  jb      short loc_1C01B05E5
0x1c01b05ca  mov     edx, 9Dh
0x1c01b05cf  mov     r9d, 0C0000022h
0x1c01b05d5  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01b05dc  mov     rcx, [rcx+18h]
0x1c01b05e0  call    WPP_SF_D
0x1c01b05e5  mov     al, cs:RefsStatusDebugEnabled
0x1c01b05eb  test    al, al
0x1c01b05ed  jz      short loc_1C01B0606
0x1c01b05ef  mov     r8d, 1B9Dh
0x1c01b05f5  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01b05fc  mov     ecx, 0C0000022h; Status
0x1c01b0601  call    RefsStatusDebug
0x1c01b0606  mov     [rsp+148h+Status], 0C0000022h
0x1c01b060e  jmp     loc_1C01B0D4F
0x1c01b0613  mov     r8b, 1
0x1c01b0616  mov     rdx, r15
0x1c01b0619  mov     rcx, rsi
0x1c01b061c  call    RefsAcquireSharedVcb
0x1c01b0621  mov     [rsp+148h+var_EF], 1
0x1c01b0626  mov     eax, [r15+4]
0x1c01b062a  test    al, 1
0x1c01b062c  jnz     short loc_1C01B069C
0x1c01b062e  lea     rax, WPP_GLOBAL_Control
0x1c01b0635  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01b063c  cmp     rcx, rax
0x1c01b063f  jz      short loc_1C01B066E
0x1c01b0641  mov     eax, [rcx+2Ch]
0x1c01b0644  bt      eax, 8
0x1c01b0648  jnb     short loc_1C01B066E
0x1c01b064a  cmp     [rcx+29h], bl
0x1c01b064d  jb      short loc_1C01B066E
0x1c01b064f  mov     edx, 9Eh
0x1c01b0654  mov     edi, 0C000026Eh
0x1c01b0659  mov     r9d, edi
0x1c01b065c  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01b0663  mov     rcx, [rcx+18h]
0x1c01b0667  call    WPP_SF_D
0x1c01b066c  jmp     short loc_1C01B0673
0x1c01b066e  mov     edi, 0C000026Eh
0x1c01b0673  mov     al, cs:RefsStatusDebugEnabled
0x1c01b0679  test    al, al
0x1c01b067b  jz      short loc_1C01B0691
0x1c01b067d  mov     r8d, 1BAAh
0x1c01b0683  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01b068a  mov     ecx, edi; Status
0x1c01b068c  call    RefsStatusDebug
0x1c01b0691  mov     [rsp+148h+Status], edi
0x1c01b0695  xor     edi, edi
0x1c01b0697  jmp     loc_1C01B0D4F
0x1c01b069c  mov     rdi, [r15+48h]
0x1c01b06a0  mov     qword ptr [rsp+148h+var_EE+6], rdi
0x1c01b06a5  mov     rax, [rdi+78h]
0x1c01b06a9  mov     [rsp+148h+var_B8], rax
0x1c01b06b1  bts     dword ptr [rsi+4], 10h
0x1c01b06b6  mov     r9d, ebx
0x1c01b06b9  mov     rdi, qword ptr [rsp+148h+var_EE+6]
0x1c01b06be  mov     r8, rdi
0x1c01b06c1  mov     rdx, [rdi+78h]
0x1c01b06c5  mov     rcx, rsi
0x1c01b06c8  call    RefsAcquireFcbWithPaging
0x1c01b06cd  mov     [rsp+148h+var_F0], 1
0x1c01b06d2  mov     eax, [rdi+130h]
0x1c01b06d8  bt      eax, 10h
0x1c01b06dc  jnb     short loc_1C01B06E5
0x1c01b06de  mov     edi, 0C000026Eh
0x1c01b06e3  jmp     short loc_1C01B06F4
0x1c01b06e5  and     eax, 1000000h
0x1c01b06ea  neg     eax
0x1c01b06ec  sbb     edi, edi
0x1c01b06ee  and     edi, 0C0000008h
0x1c01b06f4  mov     [rsp+148h+Status], edi
0x1c01b06f8  test    edi, edi
0x1c01b06fa  jns     short loc_1C01B0761
0x1c01b06fc  lea     rax, WPP_GLOBAL_Control
0x1c01b0703  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01b070a  cmp     rcx, rax
0x1c01b070d  jz      short loc_1C01B0735
0x1c01b070f  mov     eax, [rcx+2Ch]
0x1c01b0712  bt      eax, 8
0x1c01b0716  jnb     short loc_1C01B0735
0x1c01b0718  cmp     [rcx+29h], bl
0x1c01b071b  jb      short loc_1C01B0735
0x1c01b071d  mov     edx, 9Fh
0x1c01b0722  mov     r9d, edi
0x1c01b0725  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01b072c  mov     rcx, [rcx+18h]
0x1c01b0730  call    WPP_SF_D
0x1c01b0735  mov     al, cs:RefsStatusDebugEnabled
0x1c01b073b  test    al, al
0x1c01b073d  jz      short loc_1C01B0755
0x1c01b073f  mov     r8d, 1BBEh
0x1c01b0745  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01b074c  mov     ecx, [rsp+148h+Status]; Status
0x1c01b0750  call    RefsStatusDebug
0x1c01b0755  mov     edx, [rsp+148h+Status]
0x1c01b0759  mov     rcx, rsi
0x1c01b075c  call    RefsRaiseStatusInternal
0x1c01b0761  mov     rcx, [rsp+148h+var_B8]
0x1c01b0769  call    RefsIsFileOpen
0x1c01b076e  test    al, al
0x1c01b0770  jnz     short loc_1C01B07DD
0x1c01b0772  lea     rax, WPP_GLOBAL_Control
0x1c01b0779  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01b0780  cmp     rcx, rax
0x1c01b0783  jz      short loc_1C01B07AE
0x1c01b0785  mov     eax, [rcx+2Ch]
0x1c01b0788  bt      eax, 8
0x1c01b078c  jnb     short loc_1C01B07AE
0x1c01b078e  cmp     [rcx+29h], bl
0x1c01b0791  jb      short loc_1C01B07AE
0x1c01b0793  mov     edx, 0A0h
0x1c01b0798  mov     r9d, 0C0000128h
0x1c01b079e  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01b07a5  mov     rcx, [rcx+18h]
0x1c01b07a9  call    WPP_SF_D
0x1c01b07ae  mov     al, cs:RefsStatusDebugEnabled
0x1c01b07b4  test    al, al
0x1c01b07b6  jz      short loc_1C01B07CF
0x1c01b07b8  mov     r8d, 1BC3h
0x1c01b07be  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01b07c5  mov     ecx, 0C0000128h; Status
0x1c01b07ca  call    RefsStatusDebug
0x1c01b07cf  mov     edx, 0C0000128h
0x1c01b07d4  mov     rcx, rsi
0x1c01b07d7  call    RefsRaiseStatusInternal
0x1c01b07dc  nop
0x1c01b07dd  mov     [rsp+148h+var_F8], 1
0x1c01b07e2  cmp     byte ptr [r12+40h], 0
0x1c01b07e8  jz      short loc_1C01B0821
0x1c01b07ea  mov     rdx, r13; Length
0x1c01b07ed  mov     r8d, 1; Alignment
0x1c01b07f3  mov     rcx, [r14+20h]; Address
0x1c01b07f7  call    cs:__imp_ProbeForRead
0x1c01b07fe  nop     dword ptr [rax+rax+00h]
0x1c01b0803  mov     edx, dword ptr [rsp+148h+Length]; Length
0x1c01b0807  mov     r8d, 1; Alignment
0x1c01b080d  mov     rcx, [rsp+148h+Address]; Address
0x1c01b0815  call    cs:__imp_ProbeForWrite
0x1c01b081c  nop     dword ptr [rax+rax+00h]
0x1c01b0821  mov     rax, [r14+20h]
0x1c01b0825  mov     rcx, [rax]
0x1c01b0828  mov     [rsp+148h+Length], rcx
0x1c01b082d  mov     rax, [r14+20h]
0x1c01b0831  mov     rdi, [rax+8]
0x1c01b0835  mov     [rsp+148h+var_48], rdi
0x1c01b083d  mov     rax, [rsp+148h+Address]
0x1c01b0845  and     qword ptr [rax], 0
0x1c01b0849  and     qword ptr [rax+8], 0
0x1c01b084e  and     qword ptr [rax+10h], 0
0x1c01b0853  mov     [rsp+148h+var_F8], 0
0x1c01b0858  xorps   xmm0, xmm0
0x1c01b085b  xor     eax, eax
0x1c01b085d  movups  [rsp+148h+var_88], xmm0
0x1c01b0865  mov     [rsp+148h+var_78], rax
0x1c01b086d  mov     r14, qword ptr [rsp+148h+var_EE+6]
0x1c01b0872  mov     eax, [r14+88h]
0x1c01b0879  test    al, 20h
0x1c01b087b  jnz     short loc_1C01B089F
0x1c01b087d  cmp     dword ptr [r14+0C8h], 0A0h
0x1c01b0888  jz      short loc_1C01B089F
0x1c01b088a  xor     r8d, r8d
0x1c01b088d  mov     rdx, r14
0x1c01b0890  mov     rcx, rsi
0x1c01b0893  call    RefsUpdateScbFromAttribute
0x1c01b0898  mov     eax, [r14+88h]
0x1c01b089f  test    al, 8
0x1c01b08a1  jnz     loc_1C01B0CE3
0x1c01b08a7  cmp     dword ptr [rsp+148h+var_C8], 2
0x1c01b08af  jnz     loc_1C01B0CE3
0x1c01b08b5  mov     cl, [r15+1D0h]
0x1c01b08bc  mov     rax, qword ptr [rsp+148h+var_EE+6]
0x1c01b08c1  mov     r13, [rax+18h]
0x1c01b08c5  sar     r13, cl
0x1c01b08c8  lea     r15, [r13-1]
0x1c01b08cc  mov     [rsp+148h+var_60], r15
0x1c01b08d4  mov     r14, [rsp+148h+Length]
0x1c01b08d9  test    r14, r14
0x1c01b08dc  js      loc_1C01B0C78
0x1c01b08e2  test    rdi, rdi
0x1c01b08e5  jle     loc_1C01B0C78
0x1c01b08eb  cmp     r14, r15
0x1c01b08ee  jle     short loc_1C01B0947
0x1c01b08f0  lea     rax, WPP_GLOBAL_Control
0x1c01b08f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01b08fe  cmp     rcx, rax
0x1c01b0901  jz      short loc_1C01B092C
0x1c01b0903  mov     eax, [rcx+2Ch]
0x1c01b0906  bt      eax, 8
0x1c01b090a  jnb     short loc_1C01B092C
  ... truncated ...
```
