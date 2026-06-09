# CKsMdlcache::MdlCacheProcessPostProbeIrp(_IRP *,ulong,_KSPMDLCACHED_STREAM_POINTER * *)

- ea: `0x180009c9c`
- end: `0x18000a130`
- name: `?MdlCacheProcessPostProbeIrp@CKsMdlcache@@QEAAJPEAU_IRP@@KPEAPEAU_KSPMDLCACHED_STREAM_POINTER@@@Z`
- size: `1172`
- prototype: `__int64 __fastcall(PRKEVENT *this, struct _IRP *, ULONG, PMDL **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180009c40`

## callees

- `0x180009c9c`
- `0x18000da50`
- `0x18000dddc`
- `0x18000e1d0`
- `0x18000f854`
- `0x180019cb0`
- `0x18001a000`
- `0x180065d20`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180009e2a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000a05b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180009e2a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000a05b`
- `ntoskrnl!KeReleaseSpinLock` at `0x180009ff9`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000a0d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x180009ff9`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000a0d8`
- `ntoskrnl!IoFreeMdl` at `0x180009f39`
- `ntoskrnl!IoFreeMdl` at `0x180009f39`
- `ntoskrnl!KeReadStateEvent` at `0x180009d5d`
- `ntoskrnl!KeReadStateEvent` at `0x180009d5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180009f64`
- `ntoskrnl!ExFreePoolWithTag` at `0x180009f64`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000a08a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000a08a`

## pseudocode

```c
__int64 __fastcall CKsMdlcache::MdlCacheProcessPostProbeIrp(PRKEVENT *this, struct _IRP *a2, ULONG a3, PMDL **a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int v5; // edi
  struct _IRP *MasterIrp; // rbp
  PMDL *v7; // r14
  PRKEVENT *v9; // r15
  ULONG Length; // r12d
  NTSTATUS Status; // edx
  char v12; // al
  __int64 v13; // rax
  CKsMdlcache *v14; // rcx
  unsigned int v15; // eax
  int v16; // ebx
  int v17; // edx
  int v18; // r8d
  int v19; // edx
  NTSTATUS v20; // eax
  KIRQL v21; // al
  PRKEVENT *v22; // rbx
  CKsMdlcache *v23; // rcx
  KIRQL v24; // r12
  CKsMdlcache *v25; // rdx
  CKsMdlcache **v26; // rax
  int v27; // edx
  int v28; // r8d
  PRKEVENT **v29; // rcx
  struct _KEVENT *v30; // rax
  PMDL MdlAddress; // rcx
  int v32; // edx
  int v33; // r8d
  PRKEVENT **v34; // r8
  KSPIN_LOCK *v35; // rcx
  CKsMdlcache *v36; // rcx
  CKsMdlcache *v37; // rcx
  unsigned int v38; // eax
  PMDL *PoolWithTag; // rax
  char v41; // [rsp+88h] [rbp+10h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = 0;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  v7 = 0;
  *a4 = 0;
  v9 = this;
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( Length > *(_DWORD *)&MasterIrp->Type )
  {
    LOBYTE(this) = 0;
    if ( Length )
    {
      do
      {
        Status = MasterIrp->IoStatus.Status;
        if ( (Status & 0x10000) != 0 )
        {
          v12 = (char)this;
          if ( !(_BYTE)this )
            v12 = 1;
          LOBYTE(this) = v12;
        }
        v13 = *(unsigned int *)&MasterIrp->Type;
        MasterIrp->IoStatus.Status = Status & 0xFFFE7FFF;
        MasterIrp = (struct _IRP *)((char *)MasterIrp + v13);
        Length -= v13;
      }
      while ( Length );
      if ( (_BYTE)this )
      {
        CKsMdlcache::DiscardMdlAddressIrp((CKsMdlcache *)this, a2);
        if ( a2->RequestorMode == 1 )
        {
          v15 = KsProbeStreamIrp(a2, a3, 0);
        }
        else
        {
          a2->AssociatedIrp.MasterIrp = 0;
          v15 = CKsMdlcache::MdlCacheHandleThunkBufferIrp(v14, a2, a3);
        }
        v5 = v15;
      }
    }
    goto LABEL_64;
  }
  v16 = *((_DWORD *)this + 26);
  v41 = v16 & (KeReadStateEvent(this[12]) != 0);
  if ( v41 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v17) = 4;
      WPP_RECORDER_SF_qq(
        WPP_GLOBAL_Control->DeviceExtension,
        v17,
        v18,
        14,
        (__int64)WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids,
        (char)v9,
        (char)a2);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = 4;
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          v19,
          1,
          15,
          (__int64)WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids,
          (char)v9);
      }
    }
  }
  if ( Length )
  {
    v20 = MasterIrp->IoStatus.Status;
    if ( (v20 & 0x8000) != 0 )
    {
      if ( (v20 & 0x40C00) != 0 )
      {
        v5 = -1073741811;
        goto LABEL_64;
      }
      if ( (v20 & 0x10000) == 0 )
      {
        if ( !MasterIrp->ThreadListEntry.Blink )
        {
          v5 = -1073741670;
          goto LABEL_64;
        }
        v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v9 + 10);
        if ( *((_DWORD *)v9 + 26) && !v41 )
        {
          PoolWithTag = (PMDL *)ExAllocatePoolWithTag(NonPagedPoolNx, 0x60u, 0x636D534Bu);
          v7 = PoolWithTag;
          if ( PoolWithTag )
          {
            memset(PoolWithTag, 0, 0x60u);
            *v7 = a2->MdlAddress;
            v7[1] = (PMDL)MasterIrp->ThreadListEntry.Blink;
            v7[11] = (PMDL)(v7 + 10);
            v7[10] = (PMDL)(v7 + 10);
            MasterIrp->IoStatus.Status |= 0x10000u;
          }
          else
          {
            v5 = -1073741670;
          }
        }
        v35 = (KSPIN_LOCK *)(v9 + 10);
        goto LABEL_61;
      }
      v21 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v9 + 10);
      v22 = v9 + 8;
      v23 = (CKsMdlcache *)v9[8];
      v24 = v21;
      while ( 1 )
      {
        v7 = 0;
        if ( v23 == (CKsMdlcache *)v22 )
          goto LABEL_49;
        v7 = (PMDL *)((char *)v23 - 80);
        v25 = *(CKsMdlcache **)v23;
        if ( (struct _LIST_ENTRY *)*((_QWORD *)v23 - 9) == MasterIrp->ThreadListEntry.Blink )
          break;
        v23 = *(CKsMdlcache **)v23;
      }
      if ( *((CKsMdlcache **)v25 + 1) == v23 )
      {
        v26 = (CKsMdlcache **)*((_QWORD *)v23 + 1);
        if ( *v26 == v23 )
        {
          *v26 = v25;
          *((_QWORD *)v25 + 1) = v26;
          --*((_DWORD *)v9 + 22);
          if ( v23 == (CKsMdlcache *)80 )
          {
LABEL_49:
            KeReleaseSpinLock((PKSPIN_LOCK)v9 + 10, v24);
            MasterIrp->IoStatus.Status &= ~0x10000u;
            CKsMdlcache::DiscardMdlAddressIrp(v36, a2);
            if ( a2->RequestorMode == 1 )
            {
              v38 = KsProbeStreamIrp(a2, a3, 0);
            }
            else
            {
              a2->AssociatedIrp.MasterIrp = 0;
              v38 = CKsMdlcache::MdlCacheHandleThunkBufferIrp(v37, a2, a3);
            }
            v5 = v38;
LABEL_62:
            if ( v41 )
            {
              ((void (__fastcall *)(PRKEVENT *, _QWORD, _QWORD))(*v9)[1].Header.WaitListHead.Blink)(v9, 0, 0);
              *((_DWORD *)v9 + 26) = 0;
            }
            goto LABEL_64;
          }
          if ( *((_DWORD *)v7 + 4) || v7[8] )
          {
            CKsMdlcache::DiscardMdlAddressIrp(v23, a2);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v32) = 2;
              WPP_RECORDER_SF_qq(
                WPP_GLOBAL_Control->DeviceExtension,
                v32,
                v33,
                16,
                (__int64)WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids,
                (char)v9,
                (char)a2);
            }
            v34 = (PRKEVENT **)v9[9];
            if ( *v34 == v22 )
            {
              v30 = (struct _KEVENT *)(v7 + 10);
              v5 = -1073741436;
              v7[10] = (PMDL)v22;
              v7[11] = (PMDL)v34;
              *v34 = (PRKEVENT *)(v7 + 10);
              goto LABEL_46;
            }
          }
          else
          {
            if ( (*v7)->ByteCount == LODWORD(MasterIrp->ThreadListEntry.Flink) )
            {
              MdlAddress = a2->MdlAddress;
              if ( MdlAddress && !MdlAddress->StartVa )
              {
                (*v7)->Next = MdlAddress->Next;
                a2->MdlAddress = *v7;
                MdlAddress->Next = 0;
                IoFreeMdl(MdlAddress);
              }
              if ( !*((_DWORD *)v9 + 26) || v41 )
              {
                ExFreePoolWithTag(v7, 0x636D534Bu);
                v7 = 0;
                MasterIrp->IoStatus.Status &= ~0x10000u;
              }
              goto LABEL_47;
            }
            CKsMdlcache::DiscardMdlAddressIrp(v23, a2);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v27) = 2;
              WPP_RECORDER_SF_qq(
                WPP_GLOBAL_Control->DeviceExtension,
                v27,
                v28,
                17,
                (__int64)WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids,
                (char)v9,
                (char)a2);
            }
            v29 = (PRKEVENT **)v9[9];
            if ( *v29 == v22 )
            {
              v30 = (struct _KEVENT *)(v7 + 10);
              v5 = -1073741811;
              v7[10] = (PMDL)v22;
              v7[11] = (PMDL)v29;
              *v29 = (PRKEVENT *)(v7 + 10);
LABEL_46:
              v9[9] = v30;
              ++*((_DWORD *)v9 + 22);
LABEL_47:
              v35 = (KSPIN_LOCK *)(v9 + 10);
LABEL_61:
              KeReleaseSpinLock(v35, v24);
              goto LABEL_62;
            }
          }
        }
      }
      __fastfail(3u);
    }
  }
LABEL_64:
  *a4 = v7;
  return v5;
}

```

## disassembly

```asm
0x180009c9c  mov     [rsp+arg_0], rbx
0x180009ca1  mov     [rsp+arg_18], r9
0x180009ca6  mov     [rsp+ProbeFlags], r8d
0x180009cab  push    rbp
0x180009cac  push    rsi
0x180009cad  push    rdi
0x180009cae  push    r12
0x180009cb0  push    r13
0x180009cb2  push    r14
0x180009cb4  push    r15
0x180009cb6  sub     rsp, 40h
0x180009cba  mov     rax, [rdx+0B8h]
0x180009cc1  xor     edi, edi
0x180009cc3  mov     rbp, [rdx+18h]
0x180009cc7  xor     r14d, r14d
0x180009cca  mov     [r9], rdi
0x180009ccd  mov     rsi, rdx
0x180009cd0  mov     r15, rcx
0x180009cd3  mov     r12d, [rax+8]
0x180009cd7  cmp     r12d, [rbp+0]
0x180009cdb  jbe     short loc_180009D56
0x180009cdd  xor     cl, cl
0x180009cdf  test    r12d, r12d
0x180009ce2  jz      loc_18000A10A
0x180009ce8  lea     ebx, [rdi+1]
0x180009ceb  mov     edx, [rbp+30h]
0x180009cee  bt      edx, 10h
0x180009cf2  jnb     short loc_180009CFE
0x180009cf4  test    cl, cl
0x180009cf6  movzx   eax, cl
0x180009cf9  cmovz   eax, ebx
0x180009cfc  mov     cl, al; this
0x180009cfe  mov     eax, [rbp+0]
0x180009d01  and     edx, 0FFFE7FFFh
0x180009d07  mov     [rbp+30h], edx
0x180009d0a  add     rbp, rax
0x180009d0d  sub     r12d, eax
0x180009d10  jnz     short loc_180009CEB
0x180009d12  test    cl, cl
0x180009d14  jz      loc_18000A10A
0x180009d1a  mov     rdx, rsi; struct _IRP *
0x180009d1d  call    ?DiscardMdlAddressIrp@CKsMdlcache@@QEAAXPEAU_IRP@@@Z; CKsMdlcache::DiscardMdlAddressIrp(_IRP *)
0x180009d22  cmp     [rsi+40h], bl
0x180009d25  jnz     short loc_180009D3B
0x180009d27  mov     edx, [rsp+78h+ProbeFlags]; ProbeFlags
0x180009d2e  xor     r8d, r8d; HeaderSize
0x180009d31  mov     rcx, rsi; Irp
0x180009d34  call    KsProbeStreamIrp
0x180009d39  jmp     short loc_180009D4F
0x180009d3b  mov     r8d, [rsp+78h+ProbeFlags]; unsigned int
0x180009d43  mov     rdx, rsi; struct _IRP *
0x180009d46  mov     [rsi+18h], rdi
0x180009d4a  call    ?MdlCacheHandleThunkBufferIrp@CKsMdlcache@@QEAAJPEAU_IRP@@K@Z; CKsMdlcache::MdlCacheHandleThunkBufferIrp(_IRP *,ulong)
0x180009d4f  mov     edi, eax
0x180009d51  jmp     loc_18000A10A
0x180009d56  mov     ebx, [rcx+68h]
0x180009d59  mov     rcx, [rcx+60h]; Event
0x180009d5d  call    cs:__imp_KeReadStateEvent
0x180009d64  nop     dword ptr [rax+rax+00h]
0x180009d69  test    eax, eax
0x180009d6b  lea     r13, WPP_RECORDER_INITIALIZED
0x180009d72  lea     rcx, WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids
0x180009d79  setnz   al
0x180009d7c  and     al, bl
0x180009d7e  mov     [rsp+78h+arg_8], al
0x180009d85  jz      short loc_180009DED
0x180009d87  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180009d8e  jz      short loc_180009DED
0x180009d90  mov     [rsp+78h+var_48], rsi
0x180009d95  mov     r9d, 0Eh
0x180009d9b  mov     [rsp+78h+var_50], r15
0x180009da0  mov     dl, 4
0x180009da2  mov     [rsp+78h+var_58], rcx
0x180009da7  mov     rcx, cs:WPP_GLOBAL_Control
0x180009dae  mov     rcx, [rcx+40h]
0x180009db2  call    WPP_RECORDER_SF_qq
0x180009db7  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180009dbe  jz      short loc_180009DED
0x180009dc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180009dc7  lea     rax, WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids
0x180009dce  mov     r9d, 0Fh
0x180009dd4  mov     [rsp+78h+var_50], r15
0x180009dd9  mov     dl, 4
0x180009ddb  mov     [rsp+78h+var_58], rax
0x180009de0  mov     rcx, [rcx+40h]
0x180009de4  lea     r8d, [r9-0Eh]
0x180009de8  call    WPP_RECORDER_SF_q
0x180009ded  test    r12d, r12d
0x180009df0  jz      loc_18000A10A
0x180009df6  mov     eax, [rbp+30h]
0x180009df9  bt      eax, 0Fh
0x180009dfd  jnb     loc_18000A10A
0x180009e03  test    eax, 40C00h
0x180009e08  jz      short loc_180009E14
0x180009e0a  mov     edi, 0C000000Dh
0x180009e0f  jmp     loc_18000A10A
0x180009e14  mov     r13d, 10000h
0x180009e1a  test    r13d, eax
0x180009e1d  jz      loc_18000A047
0x180009e23  lea     r13, [r15+50h]
0x180009e27  mov     rcx, r13; SpinLock
0x180009e2a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180009e31  nop     dword ptr [rax+rax+00h]
0x180009e36  lea     rbx, [r15+40h]
0x180009e3a  xor     r8d, r8d
0x180009e3d  mov     rcx, [rbx]; this
0x180009e40  mov     r12b, al
0x180009e43  mov     r14, r8
0x180009e46  cmp     rcx, rbx
0x180009e49  jz      loc_180009FF3
0x180009e4f  mov     rax, [rbp+28h]
0x180009e53  lea     r14, [rcx-50h]
0x180009e57  mov     rdx, [rcx]
0x180009e5a  cmp     [r14+8], rax
0x180009e5e  jz      short loc_180009E65
0x180009e60  mov     rcx, rdx
0x180009e63  jmp     short loc_180009E43
0x180009e65  cmp     [rdx+8], rcx
0x180009e69  jnz     loc_180009FEC
0x180009e6f  mov     rax, [rcx+8]
0x180009e73  cmp     [rax], rcx
0x180009e76  jnz     loc_180009FEC
0x180009e7c  mov     [rax], rdx
0x180009e7f  mov     [rdx+8], rax
0x180009e83  dec     dword ptr [r15+58h]
0x180009e87  test    r14, r14
0x180009e8a  jz      loc_180009FF3
0x180009e90  cmp     [r14+10h], r8d
0x180009e94  jnz     loc_180009F7A
0x180009e9a  cmp     [r14+40h], r8
0x180009e9e  jnz     loc_180009F7A
0x180009ea4  mov     rdx, [r14]
0x180009ea7  mov     eax, [rbp+20h]
0x180009eaa  cmp     [rdx+28h], eax
0x180009ead  jz      short loc_180009F1A
0x180009eaf  mov     rdx, rsi; struct _IRP *
0x180009eb2  call    ?DiscardMdlAddressIrp@CKsMdlcache@@QEAAXPEAU_IRP@@@Z; CKsMdlcache::DiscardMdlAddressIrp(_IRP *)
0x180009eb7  lea     rax, WPP_RECORDER_INITIALIZED
0x180009ebe  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180009ec5  jz      short loc_180009EF5
0x180009ec7  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ece  lea     rax, WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids
0x180009ed5  mov     [rsp+78h+var_48], rsi
0x180009eda  mov     r9d, 11h
0x180009ee0  mov     [rsp+78h+var_50], r15
0x180009ee5  mov     dl, 2
0x180009ee7  mov     [rsp+78h+var_58], rax
0x180009eec  mov     rcx, [rcx+40h]
0x180009ef0  call    WPP_RECORDER_SF_qq
0x180009ef5  mov     rcx, [rbx+8]
0x180009ef9  cmp     [rcx], rbx
0x180009efc  jnz     loc_180009FEC
0x180009f02  lea     rax, [r14+50h]
0x180009f06  mov     edi, 0C000000Dh
0x180009f0b  mov     [rax], rbx
0x180009f0e  mov     [rax+8], rcx
0x180009f12  mov     [rcx], rax
0x180009f15  jmp     loc_180009FDC
0x180009f1a  mov     rcx, [rsi+8]; Mdl
0x180009f1e  test    rcx, rcx
0x180009f21  jz      short loc_180009F48
0x180009f23  cmp     [rcx+20h], r8
0x180009f27  jnz     short loc_180009F48
0x180009f29  mov     rax, [rcx]
0x180009f2c  mov     [rdx], rax
0x180009f2f  mov     rax, [r14]
0x180009f32  mov     [rsi+8], rax
0x180009f36  mov     [rcx], r8
0x180009f39  call    cs:__imp_IoFreeMdl
0x180009f40  nop     dword ptr [rax+rax+00h]
0x180009f45  xor     r8d, r8d
0x180009f48  cmp     [r15+68h], r8d
0x180009f4c  jz      short loc_180009F5C
0x180009f4e  cmp     [rsp+78h+arg_8], r8b
0x180009f56  jz      loc_180009FE4
0x180009f5c  mov     edx, 636D534Bh; Tag
0x180009f61  mov     rcx, r14; P
0x180009f64  call    cs:__imp_ExFreePoolWithTag
0x180009f6b  nop     dword ptr [rax+rax+00h]
0x180009f70  xor     r14d, r14d
0x180009f73  btr     dword ptr [rbp+30h], 10h
0x180009f78  jmp     short loc_180009FE4
0x180009f7a  mov     rdx, rsi; struct _IRP *
0x180009f7d  call    ?DiscardMdlAddressIrp@CKsMdlcache@@QEAAXPEAU_IRP@@@Z; CKsMdlcache::DiscardMdlAddressIrp(_IRP *)
0x180009f82  lea     rax, WPP_RECORDER_INITIALIZED
0x180009f89  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180009f90  jz      short loc_180009FC0
0x180009f92  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f99  lea     rax, WPP_4c8fdc2d191e3ec07d08eb5f682ffacd_Traceguids
0x180009fa0  mov     [rsp+78h+var_48], rsi
0x180009fa5  mov     r9d, 10h
0x180009fab  mov     [rsp+78h+var_50], r15
0x180009fb0  mov     dl, 2
0x180009fb2  mov     [rsp+78h+var_58], rax
0x180009fb7  mov     rcx, [rcx+40h]
0x180009fbb  call    WPP_RECORDER_SF_qq
0x180009fc0  mov     r8, [rbx+8]
0x180009fc4  cmp     [r8], rbx
0x180009fc7  jnz     short loc_180009FEC
0x180009fc9  lea     rax, [r14+50h]
0x180009fcd  mov     edi, 0C0000184h
0x180009fd2  mov     [rax], rbx
0x180009fd5  mov     [rax+8], r8
0x180009fd9  mov     [r8], rax
0x180009fdc  mov     [rbx+8], rax
0x180009fe0  inc     dword ptr [r15+58h]
0x180009fe4  mov     rcx, r13
0x180009fe7  jmp     loc_18000A0D5
0x180009fec  mov     ecx, 3
0x180009ff1  int     29h; Win8: RtlFailFast(ecx)
0x180009ff3  mov     dl, r12b; NewIrql
0x180009ff6  mov     rcx, r13; SpinLock
0x180009ff9  call    cs:__imp_KeReleaseSpinLock
0x18000a000  nop     dword ptr [rax+rax+00h]
0x18000a005  btr     dword ptr [rbp+30h], 10h
0x18000a00a  mov     rdx, rsi; struct _IRP *
0x18000a00d  call    ?DiscardMdlAddressIrp@CKsMdlcache@@QEAAXPEAU_IRP@@@Z; CKsMdlcache::DiscardMdlAddressIrp(_IRP *)
0x18000a012  cmp     byte ptr [rsi+40h], 1
0x18000a016  jnz     short loc_18000A02C
0x18000a018  mov     edx, [rsp+78h+ProbeFlags]; ProbeFlags
0x18000a01f  xor     r8d, r8d; HeaderSize
0x18000a022  mov     rcx, rsi; Irp
0x18000a025  call    KsProbeStreamIrp
0x18000a02a  jmp     short loc_18000A040
0x18000a02c  mov     r8d, [rsp+78h+ProbeFlags]; unsigned int
0x18000a034  mov     rdx, rsi; struct _IRP *
0x18000a037  mov     [rsi+18h], rdi
0x18000a03b  call    ?MdlCacheHandleThunkBufferIrp@CKsMdlcache@@QEAAJPEAU_IRP@@K@Z; CKsMdlcache::MdlCacheHandleThunkBufferIrp(_IRP *,ulong)
0x18000a040  mov     edi, eax
0x18000a042  jmp     loc_18000A0E4
0x18000a047  cmp     [rbp+28h], rdi
0x18000a04b  jnz     short loc_18000A057
0x18000a04d  mov     edi, 0C000009Ah
0x18000a052  jmp     loc_18000A10A
0x18000a057  lea     rcx, [r15+50h]; SpinLock
0x18000a05b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18000a062  nop     dword ptr [rax+rax+00h]
0x18000a067  mov     r12b, al
0x18000a06a  cmp     [r15+68h], edi
0x18000a06e  jz      short loc_18000A0D1
0x18000a070  cmp     [rsp+78h+arg_8], dil
0x18000a078  jnz     short loc_18000A0D1
0x18000a07a  mov     edx, 60h ; '`'; NumberOfBytes
0x18000a07f  mov     ecx, 200h; PoolType
0x18000a084  mov     r8d, 636D534Bh; Tag
0x18000a08a  call    cs:__imp_ExAllocatePoolWithTag
0x18000a091  nop     dword ptr [rax+rax+00h]
0x18000a096  mov     r14, rax
0x18000a099  test    rax, rax
0x18000a09c  jz      short loc_18000A0CC
0x18000a09e  xor     edx, edx; Val
0x18000a0a0  mov     rcx, rax; void *
0x18000a0a3  lea     r8d, [rdx+60h]; Size
0x18000a0a7  call    memset
0x18000a0ac  mov     rax, [rsi+8]
0x18000a0b0  mov     [r14], rax
0x18000a0b3  mov     rax, [rbp+28h]
0x18000a0b7  mov     [r14+8], rax
0x18000a0bb  lea     rax, [r14+50h]
0x18000a0bf  mov     [rax+8], rax
0x18000a0c3  mov     [rax], rax
0x18000a0c6  or      [rbp+30h], r13d
0x18000a0ca  jmp     short loc_18000A0D1
0x18000a0cc  mov     edi, 0C000009Ah
0x18000a0d1  lea     rcx, [r15+50h]; SpinLock
0x18000a0d5  mov     dl, r12b; NewIrql
0x18000a0d8  call    cs:__imp_KeReleaseSpinLock
0x18000a0df  nop     dword ptr [rax+rax+00h]
0x18000a0e4  cmp     [rsp+78h+arg_8], 0
0x18000a0ec  jz      short loc_18000A10A
0x18000a0ee  mov     rax, [r15]
0x18000a0f1  xor     r8d, r8d
0x18000a0f4  xor     edx, edx
0x18000a0f6  mov     rcx, r15
0x18000a0f9  mov     rax, [rax+28h]
0x18000a0fd  call    _guard_dispatch_icall
0x18000a102  mov     dword ptr [r15+68h], 0
0x18000a10a  mov     rax, [rsp+78h+arg_18]
0x18000a112  mov     rbx, [rsp+78h+arg_0]
0x18000a11a  mov     [rax], r14
0x18000a11d  mov     eax, edi
0x18000a11f  add     rsp, 40h
0x18000a123  pop     r15
0x18000a125  pop     r14
0x18000a127  pop     r13
0x18000a129  pop     r12
0x18000a12b  pop     rdi
0x18000a12c  pop     rsi
0x18000a12d  pop     rbp
0x18000a12e  retn
```
