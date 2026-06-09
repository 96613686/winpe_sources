# ClfsReserveAndAppendLogInternal

- ea: `0x140057980`
- end: `0x140057f4d`
- name: `ClfsReserveAndAppendLogInternal`
- size: `1485`
- prototype: `__int64 __fastcall(int, int, int, int, __int64 *, __int64 *, __int64 *, int, union _CLS_LSN *, __int64, union _CLS_LSN *, union _CLS_LSN *, char, struct _IRP *)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004b2b0`
- `0x1400572a0`
- `0x1400705e8`

## callees

- `0x14000c2f0`
- `0x14000d0dc`
- `0x14000ed64`
- `0x140017f20`
- `0x140033ac0`
- `0x140057980`
- `0x140057f54`
- `0x140058660`
- `0x140058670`
- `0x1400587c0`
- `0x140059e80`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140057a68`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140057a68`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140057e0d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079a31`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140057e0d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079a31`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140057e9a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140057e9a`
- `ntoskrnl!IoFreeIrp` at `0x140057d33`
- `ntoskrnl!IoFreeIrp` at `0x140057d33`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140057c83`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140057c83`
- `ntoskrnl!IoAllocateIrp` at `0x140057c5f`
- `ntoskrnl!IoAllocateIrp` at `0x140057c5f`

## pseudocode

```c
__int64 __fastcall ClfsReserveAndAppendLogInternal(
        struct _FILE_OBJECT *a1,
        struct CClfsLogFcbCommon *a2,
        void *a3,
        unsigned int a4,
        __int64 *a5,
        __int64 *a6,
        __int64 *a7,
        char a8,
        union _CLS_LSN *a9,
        unsigned int *a10,
        union _CLS_LSN *a11,
        union _CLS_LSN *a12)
{
  __int64 v12; // r12
  CClfsRequest *v13; // rsi
  volatile signed __int32 *v14; // r14
  union _CLS_LSN *v15; // r15
  int v16; // ecx
  struct CClfsLogFcbCommon *v17; // rax
  int appended; // ecx
  struct _FILE_OBJECT *const v19; // rcx
  CClfsRequest *v20; // rax
  int v21; // ecx
  struct _KEVENT *v23; // [rsp+40h] [rbp-B8h]
  char v24; // [rsp+70h] [rbp-88h]
  unsigned int v25; // [rsp+78h] [rbp-80h] BYREF
  __int64 v26; // [rsp+80h] [rbp-78h]
  struct CClfsLogFcbCommon *v27; // [rsp+88h] [rbp-70h]
  CClfsLogCcb *FsContext2; // [rsp+90h] [rbp-68h]
  CClfsRequest *v29; // [rsp+98h] [rbp-60h]
  PIRP Irp[2]; // [rsp+A0h] [rbp-58h] BYREF
  int v31; // [rsp+B0h] [rbp-48h]
  CLFS_LSN v32; // [rsp+B8h] [rbp-40h] BYREF
  unsigned int v38; // [rsp+168h] [rbp+70h]
  struct _IRP *v39; // [rsp+168h] [rbp+70h]
  struct CClfsLogCcb *v40; // [rsp+168h] [rbp+70h]

  v27 = a2;
  v32 = CLFS_LSN_INVALID;
  v12 = 0;
  v26 = 0;
  *(_OWORD *)Irp = 0;
  v25 = 0;
  if ( !a5 || !a6 || !a7 || !a11 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        216,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReserveAndAppendLogInternal",
        249,
        13);
    }
    return 3221225485LL;
  }
  if ( *a6 < 0 || *a7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        217,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReserveAndAppendLogInternal",
        7,
        13);
    }
    return 3221225485LL;
  }
  if ( !a4 || a3 )
  {
    v13 = 0;
    v29 = 0;
    v14 = 0;
    FsContext2 = 0;
    v24 = 0;
    v15 = &v32;
    if ( a12 )
      v15 = a12;
    KeEnterCriticalRegion();
    if ( !v27 || !*((_QWORD *)v27 + 1) )
    {
      v27 = CClfsLogFcbCommon::FcbFromFileObject(a1);
      v40 = CClfsLogFcbCommon::CcbFromFileObject(v19);
      *(_OWORD *)Irp = 0;
      Irp[0] = IoAllocateIrp(1, 0);
      if ( Irp[0] )
      {
        v20 = (CClfsRequest *)ExAllocateFromNPagedLookasideList(&CClfsRequest::m_laList);
        if ( v20 )
          v20 = CClfsRequest::CClfsRequest(v20, a1, v27, v40);
        Irp[1] = (PIRP)v20;
        if ( v20 )
        {
          v21 = 0;
        }
        else
        {
          IoFreeIrp(Irp[0]);
          Irp[0] = 0;
          v21 = -1073741670;
        }
      }
      else
      {
        v21 = -1073741670;
      }
      v38 = v21;
      if ( v21 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
        {
          WPP_SF_slD(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            220,
            (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
            (unsigned int)"ClfsReserveAndAppendLogInternal",
            77,
            v21);
        }
        goto LABEL_37;
      }
      v24 = 1;
      v27 = (struct CClfsLogFcbCommon *)Irp;
    }
    v12 = *((_QWORD *)a1->FsContext + 15);
    v26 = v12;
    FsContext2 = (CClfsLogCcb *)a1->FsContext2;
    v14 = (volatile signed __int32 *)FsContext2;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 64LL))(v12);
    CClfsLogCcb::AddRef(FsContext2);
    v16 = 0;
    v38 = 0;
    v31 = 0;
    if ( !*(_BYTE *)(*((_QWORD *)FsContext2 + 9) + 75LL) )
    {
      v16 = -1073741790;
      v38 = -1073741790;
      v31 = -1073741790;
    }
    if ( v16 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          221,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsReserveAndAppendLogInternal",
          111,
          v16);
      }
    }
    else
    {
      v17 = v27;
      v39 = *(struct _IRP **)v27;
      v13 = (CClfsRequest *)*((_QWORD *)v27 + 1);
      *(_QWORD *)v27 = 0;
      *((_QWORD *)v17 + 1) = 0;
      v24 = 0;
      v29 = v13;
      (**(void (__fastcall ***)(CClfsRequest *))v13)(v13);
      appended = CClfsRequest::ReserveAndAppendLog(v13, v39, a3, a4, a5, a6, a7, (a8 & 2) != 0, v23, a11, a9, v15, &v25);
      v38 = appended;
      if ( appended < 0 )
      {
        if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
        {
          WPP_SF_slD(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            222,
            (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
            (unsigned int)"ClfsReserveAndAppendLogInternal",
            166,
            appended);
        }
      }
      else if ( a10 )
      {
        *a10 = v25;
      }
    }
LABEL_37:
    if ( v12 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 72LL))(v12);
      v26 = 0;
    }
    if ( v14 && _InterlockedExchangeAdd(v14 + 6, 0xFFFFFFFF) == 1 )
    {
      CClfsLogCcb::~CClfsLogCcb((CClfsLogCcb *)v14);
      ExFreeToNPagedLookasideList(&CClfsLogCcb::m_laList, (PVOID)v14);
    }
    if ( v13 )
      (*(void (__fastcall **)(CClfsRequest *))(*(_QWORD *)v13 + 8LL))(v13);
    if ( v24 )
      CClfsRequest::DeallocateKernelWriteContext((struct _CLFS_KERNEL_WRITE_CONTEXT *)Irp);
    KeLeaveCriticalRegion();
    return v38;
  }
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_slD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      218,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsReserveAndAppendLogInternal",
      21,
      232);
  }
  return 3221225704LL;
}

```

## disassembly

```asm
0x140057980  mov     r11, rsp
0x140057983  mov     [r11+20h], r9d
0x140057987  mov     [r11+18h], r8
0x14005798b  mov     [r11+8], rcx
0x14005798f  push    rbx
0x140057990  push    rsi
0x140057991  push    rdi
0x140057992  push    r12
0x140057994  push    r13
0x140057996  push    r14
0x140057998  push    r15
0x14005799a  sub     rsp, 0C0h
0x1400579a1  mov     [r11-70h], rdx
0x1400579a5  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400579ac  mov     [r11-40h], rax
0x1400579b0  xor     r12d, r12d
0x1400579b3  mov     [r11-78h], r12
0x1400579b7  xorps   xmm0, xmm0
0x1400579ba  movdqu  xmmword ptr [r11-58h], xmm0
0x1400579c0  mov     [r11-80h], r12d
0x1400579c4  cmp     [rsp+0F8h+arg_20], r12
0x1400579cc  jz      loc_140057E34
0x1400579d2  mov     rbx, [rsp+0F8h+arg_28]
0x1400579da  test    rbx, rbx
0x1400579dd  jz      loc_140057E34
0x1400579e3  mov     rdi, [rsp+0F8h+arg_30]
0x1400579eb  test    rdi, rdi
0x1400579ee  jz      loc_140057E34
0x1400579f4  mov     r13, [rsp+0F8h+arg_50]
0x1400579fc  test    r13, r13
0x1400579ff  jz      loc_140057E34
0x140057a05  cmp     [rbx], r12
0x140057a08  jl      loc_140057E52
0x140057a0e  cmp     [rdi], r12
0x140057a11  jl      loc_140057E52
0x140057a17  test    r9d, r9d
0x140057a1a  jz      short loc_140057A25
0x140057a1c  test    r8, r8
0x140057a1f  jz      loc_140057EAB
0x140057a25  xor     esi, esi
0x140057a27  mov     [rsp+0F8h+var_60], rsi
0x140057a2f  xor     r14d, r14d
0x140057a32  mov     [rsp+0F8h+var_68], r14
0x140057a3a  mov     [rsp+0F8h+var_88], sil
0x140057a3f  lea     r15, [rsp+0F8h+var_40]
0x140057a47  mov     rax, [rsp+0F8h+arg_58]
0x140057a4f  test    rax, rax
0x140057a52  cmovnz  r15, rax
0x140057a56  mov     eax, dword ptr [rsp+0F8h+arg_38]
0x140057a5d  and     eax, 2
0x140057a60  setnz   [rsp+0F8h+arg_60]
0x140057a68  call    cs:__imp_KeEnterCriticalRegion
0x140057a6f  nop     dword ptr [rax+rax+00h]
0x140057a74  mov     rax, [rsp+0F8h+var_70]
0x140057a7c  test    rax, rax
0x140057a7f  jz      loc_140057C2D
0x140057a85  cmp     [rax+8], r14
0x140057a89  jz      loc_140057C2D
0x140057a8f  mov     rcx, [rsp+0F8h+arg_0]
0x140057a97  mov     rax, [rcx+18h]
0x140057a9b  mov     r12, [rax+78h]
0x140057a9f  mov     [rsp+0F8h+var_78], r12
0x140057aa7  mov     r14, [rcx+20h]
0x140057aab  mov     [rsp+0F8h+var_68], r14
0x140057ab3  mov     rax, [r12]
0x140057ab7  mov     rax, [rax+40h]
0x140057abb  mov     rcx, r12
0x140057abe  call    _guard_dispatch_icall
0x140057ac3  mov     rcx, r14; this
0x140057ac6  call    ?AddRef@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::AddRef(void)
0x140057acb  xor     ecx, ecx
0x140057acd  mov     dword ptr [rsp+0F8h+arg_68], ecx
0x140057ad4  mov     [rsp+0F8h+var_48], ecx
0x140057adb  mov     rax, [r14+48h]
0x140057adf  cmp     [rax+4Bh], cl
0x140057ae2  jz      loc_140057D7F
0x140057ae8  mov     [rsp+0F8h+var_84], ecx
0x140057aec  test    ecx, ecx
0x140057aee  js      loc_140057BF2
0x140057af4  mov     rax, [rsp+0F8h+var_70]
0x140057afc  mov     rcx, [rax]
0x140057aff  mov     [rsp+0F8h+arg_68], rcx
0x140057b07  mov     rsi, [rax+8]
0x140057b0b  mov     qword ptr [rax], 0
0x140057b12  mov     qword ptr [rax+8], 0
0x140057b1a  mov     [rsp+0F8h+var_88], 0
0x140057b1f  mov     [rsp+0F8h+var_60], rsi
0x140057b27  mov     rax, [rsi]
0x140057b2a  mov     rax, [rax]
0x140057b2d  mov     rcx, rsi
0x140057b30  call    _guard_dispatch_icall
0x140057b35  nop
0x140057b36  lea     rax, [rsp+0F8h+var_80]
0x140057b3b  mov     [rsp+0F8h+var_98], rax; unsigned int *
0x140057b40  mov     [rsp+0F8h+var_A0], r15; union _CLS_LSN *
0x140057b45  mov     rax, [rsp+0F8h+arg_40]
0x140057b4d  mov     [rsp+0F8h+var_A8], rax; union _CLS_LSN *
0x140057b52  mov     [rsp+0F8h+var_B0], r13; union _CLS_LSN *
0x140057b57  movzx   eax, [rsp+0F8h+arg_60]
0x140057b5f  mov     [rsp+0F8h+var_C0], al; char
0x140057b63  mov     [rsp+0F8h+var_C8], rdi; __int64 *
0x140057b68  mov     [rsp+0F8h+var_D0], rbx; __int64 *
0x140057b6d  mov     rax, [rsp+0F8h+arg_20]
0x140057b75  mov     [rsp+0F8h+var_D8], rax; __int64 *
0x140057b7a  mov     r9d, [rsp+0F8h+arg_18]; unsigned int
0x140057b82  mov     r8, [rsp+0F8h+arg_10]; void *
0x140057b8a  mov     rdx, [rsp+0F8h+arg_68]; struct _IRP *
0x140057b92  mov     rcx, rsi; this
0x140057b95  call    ?ReserveAndAppendLog@CClfsRequest@@QEAAJPEAU_IRP@@PEAXKAEB_JAEA_J2EPEAU_KEVENT@@AEAT_CLS_LSN@@AEBT4@5AEAK@Z; CClfsRequest::ReserveAndAppendLog(_IRP *,void *,ulong,__int64 const &,__int64 &,__int64 const &,uchar,_KEVENT *,_CLS_LSN &,_CLS_LSN const &,_CLS_LSN &,ulong &)
0x140057b9a  mov     ecx, eax
0x140057b9c  mov     dword ptr [rsp+0F8h+arg_68], eax
0x140057ba3  mov     [rsp+0F8h+var_84], eax
0x140057ba7  jmp     short loc_140057BCE
0x140057ba9  mov     ecx, eax
0x140057bab  mov     dword ptr [rsp+0F8h+arg_68], eax
0x140057bb2  mov     [rsp+0F8h+var_84], eax
0x140057bb6  mov     rsi, [rsp+0F8h+var_60]
0x140057bbe  mov     r12, [rsp+0F8h+var_78]
0x140057bc6  mov     r14, [rsp+0F8h+var_68]
0x140057bce  test    ecx, ecx
0x140057bd0  js      loc_140057D97
0x140057bd6  mov     rcx, [rsp+0F8h+arg_48]
0x140057bde  test    rcx, rcx
0x140057be1  jz      loc_140057DB4
0x140057be7  mov     eax, [rsp+0F8h+var_80]
0x140057beb  mov     [rcx], eax
0x140057bed  jmp     loc_140057DB4
0x140057bf2  lea     rax, WPP_GLOBAL_Control
0x140057bf9  mov     r10, cs:WPP_GLOBAL_Control
0x140057c00  cmp     r10, rax
0x140057c03  jz      loc_140057DB4
0x140057c09  mov     eax, [r10+2Ch]
0x140057c0d  bt      eax, 1Ah
0x140057c11  jnb     loc_140057DB4
0x140057c17  mov     edx, 0DDh
0x140057c1c  mov     dword ptr [rsp+0F8h+var_D0], ecx
0x140057c20  mov     dword ptr [rsp+0F8h+var_D8], 1A6Fh
0x140057c28  jmp     loc_140057D66
0x140057c2d  mov     rcx, [rsp+0F8h+arg_0]; struct _FILE_OBJECT *
0x140057c35  call    ?FcbFromFileObject@CClfsLogFcbCommon@@SAPEAV1@QEAU_FILE_OBJECT@@@Z; CClfsLogFcbCommon::FcbFromFileObject(_FILE_OBJECT * const)
0x140057c3a  mov     [rsp+0F8h+var_70], rax
0x140057c42  call    ?CcbFromFileObject@CClfsLogFcbCommon@@SAPEAVCClfsLogCcb@@QEAU_FILE_OBJECT@@@Z; CClfsLogFcbCommon::CcbFromFileObject(_FILE_OBJECT * const)
0x140057c47  mov     [rsp+0F8h+arg_68], rax
0x140057c4f  xorps   xmm0, xmm0
0x140057c52  movdqu  xmmword ptr [rsp+0F8h+Irp], xmm0
0x140057c5b  xor     edx, edx; ChargeQuota
0x140057c5d  mov     cl, 1; StackSize
0x140057c5f  call    cs:__imp_IoAllocateIrp
0x140057c66  nop     dword ptr [rax+rax+00h]
0x140057c6b  mov     [rsp+0F8h+Irp], rax
0x140057c73  test    rax, rax
0x140057c76  jz      loc_140057D24
0x140057c7c  lea     rcx, ?m_laList@CClfsRequest@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140057c83  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140057c8a  nop     dword ptr [rax+rax+00h]
0x140057c8f  test    rax, rax
0x140057c92  jz      short loc_140057CB4
0x140057c94  mov     r9, [rsp+0F8h+arg_68]; struct CClfsLogCcb *
0x140057c9c  mov     r8, [rsp+0F8h+var_70]; struct CClfsLogFcbCommon *
0x140057ca4  mov     rdx, [rsp+0F8h+arg_0]; struct _FILE_OBJECT *
0x140057cac  mov     rcx, rax; this
0x140057caf  call    ??0CClfsRequest@@QEAA@PEAU_FILE_OBJECT@@PEAVCClfsLogFcbCommon@@PEAVCClfsLogCcb@@@Z; CClfsRequest::CClfsRequest(_FILE_OBJECT *,CClfsLogFcbCommon *,CClfsLogCcb *)
0x140057cb4  mov     [rsp+0F8h+Irp+8], rax
0x140057cbc  test    rax, rax
0x140057cbf  jz      short loc_140057D2B
0x140057cc1  xor     ecx, ecx
0x140057cc3  mov     dword ptr [rsp+0F8h+arg_68], ecx
0x140057cca  mov     [rsp+0F8h+var_84], ecx
0x140057cce  test    ecx, ecx
0x140057cd0  jns     short loc_140057D0A
0x140057cd2  lea     rax, WPP_GLOBAL_Control
0x140057cd9  mov     r10, cs:WPP_GLOBAL_Control
0x140057ce0  cmp     r10, rax
0x140057ce3  jz      loc_140057DB4
0x140057ce9  mov     eax, [r10+2Ch]
0x140057ced  bt      eax, 1Ah
0x140057cf1  jnb     loc_140057DB4
0x140057cf7  mov     edx, 0DCh
0x140057cfc  mov     dword ptr [rsp+0F8h+var_D0], ecx
0x140057d00  mov     dword ptr [rsp+0F8h+var_D8], 1A4Dh
0x140057d08  jmp     short loc_140057D66
0x140057d0a  mov     [rsp+0F8h+var_88], 1
0x140057d0f  lea     rax, [rsp+0F8h+Irp]
0x140057d17  mov     [rsp+0F8h+var_70], rax
0x140057d1f  jmp     loc_140057A8F
0x140057d24  mov     ecx, 0C000009Ah
0x140057d29  jmp     short loc_140057CC3
0x140057d2b  mov     rcx, [rsp+0F8h+Irp]; Irp
0x140057d33  call    cs:__imp_IoFreeIrp
0x140057d3a  nop     dword ptr [rax+rax+00h]
0x140057d3f  mov     [rsp+0F8h+Irp], 0
0x140057d4b  mov     ecx, 0C000009Ah
0x140057d50  jmp     loc_140057CC3
0x140057d55  mov     edx, 0DEh
0x140057d5a  mov     dword ptr [rsp+0F8h+var_D0], ecx
0x140057d5e  mov     dword ptr [rsp+0F8h+var_D8], 1AA6h
0x140057d66  lea     r9, aClfsreserveand; "ClfsReserveAndAppendLogInternal"
0x140057d6d  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140057d74  mov     rcx, [r10+18h]
0x140057d78  call    WPP_SF_slD
0x140057d7d  jmp     short loc_140057DB4
0x140057d7f  mov     ecx, 0C0000022h
0x140057d84  mov     dword ptr [rsp+0F8h+arg_68], ecx
0x140057d8b  mov     [rsp+0F8h+var_48], ecx
0x140057d92  jmp     loc_140057AE8
0x140057d97  lea     rax, WPP_GLOBAL_Control
0x140057d9e  mov     r10, cs:WPP_GLOBAL_Control
0x140057da5  cmp     r10, rax
0x140057da8  jz      short loc_140057DB4
0x140057daa  mov     eax, [r10+2Ch]
0x140057dae  bt      eax, 1Ah
0x140057db2  jb      short loc_140057D55
0x140057db4  test    r12, r12
0x140057db7  jz      short loc_140057DD5
0x140057db9  mov     rax, [r12]
0x140057dbd  mov     rax, [rax+48h]
0x140057dc1  mov     rcx, r12
0x140057dc4  call    _guard_dispatch_icall
0x140057dc9  mov     [rsp+0F8h+var_78], 0
0x140057dd5  test    r14, r14
0x140057dd8  jz      short loc_140057DEE
0x140057dda  mov     eax, 0FFFFFFFFh
0x140057ddf  lock xadd [r14+18h], eax
0x140057de5  cmp     eax, 1
0x140057de8  jz      loc_140057E88
0x140057dee  test    rsi, rsi
0x140057df1  jz      short loc_140057E02
0x140057df3  mov     rax, [rsi]
0x140057df6  mov     rax, [rax+8]
0x140057dfa  mov     rcx, rsi
0x140057dfd  call    _guard_dispatch_icall
0x140057e02  cmp     [rsp+0F8h+var_88], 0
0x140057e07  jnz     loc_140057EFD
0x140057e0d  call    cs:__imp_KeLeaveCriticalRegion
0x140057e14  nop     dword ptr [rax+rax+00h]
0x140057e19  mov     eax, dword ptr [rsp+0F8h+arg_68]
0x140057e20  add     rsp, 0C0h
0x140057e27  pop     r15
0x140057e29  pop     r14
0x140057e2b  pop     r13
0x140057e2d  pop     r12
0x140057e2f  pop     rdi
0x140057e30  pop     rsi
0x140057e31  pop     rbx
0x140057e32  retn
0x140057e34  lea     rax, WPP_GLOBAL_Control
0x140057e3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140057e42  cmp     rcx, rax
0x140057e45  jnz     loc_140057F0F
0x140057e4b  mov     eax, 0C000000Dh
0x140057e50  jmp     short loc_140057E20
0x140057e52  lea     rax, WPP_GLOBAL_Control
0x140057e59  mov     rcx, cs:WPP_GLOBAL_Control
0x140057e60  cmp     rcx, rax
0x140057e63  jz      short loc_140057E4B
0x140057e65  test    dword ptr [rcx+2Ch], 4000000h
0x140057e6c  jz      short loc_140057E4B
0x140057e6e  mov     edx, 0D9h
0x140057e73  mov     dword ptr [rsp+0F8h+var_D0], 0C000000Dh
0x140057e7b  mov     dword ptr [rsp+0F8h+var_D8], 1A07h
0x140057e83  jmp     loc_140057F31
0x140057e88  mov     rcx, r14; this
0x140057e8b  call    ??1CClfsLogCcb@@QEAA@XZ; CClfsLogCcb::~CClfsLogCcb(void)
0x140057e90  mov     rdx, r14; Entry
0x140057e93  lea     rcx, ?m_laList@CClfsLogCcb@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140057e9a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140057ea1  nop     dword ptr [rax+rax+00h]
0x140057ea6  jmp     loc_140057DEE
0x140057eab  lea     rax, WPP_GLOBAL_Control
0x140057eb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140057eb9  cmp     rcx, rax
0x140057ebc  jz      short loc_140057EF3
0x140057ebe  test    dword ptr [rcx+2Ch], 4000000h
0x140057ec5  jz      short loc_140057EF3
0x140057ec7  mov     edx, 0DAh
0x140057ecc  mov     dword ptr [rsp+0F8h+var_D0], 0C00000E8h
0x140057ed4  mov     dword ptr [rsp+0F8h+var_D8], 1A15h
0x140057edc  lea     r9, aClfsreserveand; "ClfsReserveAndAppendLogInternal"
0x140057ee3  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140057eea  mov     rcx, [rcx+18h]
0x140057eee  call    WPP_SF_slD
0x140057ef3  mov     eax, 0C00000E8h
0x140057ef8  jmp     loc_140057E20
0x140057efd  lea     rcx, [rsp+0F8h+Irp]; struct _CLFS_KERNEL_WRITE_CONTEXT *
0x140057f05  call    ?DeallocateKernelWriteContext@CClfsRequest@@SAXAEAU_CLFS_KERNEL_WRITE_CONTEXT@@@Z; CClfsRequest::DeallocateKernelWriteContext(_CLFS_KERNEL_WRITE_CONTEXT &)
0x140057f0a  jmp     loc_140057E0D
0x140057f0f  test    dword ptr [rcx+2Ch], 4000000h
0x140057f16  jz      loc_140057E4B
0x140057f1c  mov     edx, 0D8h
0x140057f21  mov     dword ptr [rsp+0F8h+var_D0], 0C000000Dh
0x140057f29  mov     dword ptr [rsp+0F8h+var_D8], 19F9h
0x140057f31  lea     r9, aClfsreserveand; "ClfsReserveAndAppendLogInternal"
0x140057f38  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140057f3f  mov     rcx, [rcx+18h]
0x140057f43  call    WPP_SF_slD
0x140057f48  jmp     loc_140057E4B
0x1400799b0  push    rbp
0x1400799b2  sub     rsp, 70h
0x1400799b6  mov     rbp, rdx
0x1400799b9  mov     rcx, [rbp+80h]
  ... truncated ...
```
