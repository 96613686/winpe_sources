# DrSession::Connect(tagCHANNEL_CONNECT_IN *,tagCHANNEL_CONNECT_OUT *)

- ea: `0x14001bf2c`
- end: `0x14001c6da`
- name: `?Connect@DrSession@@QEAAHPEAUtagCHANNEL_CONNECT_IN@@PEAUtagCHANNEL_CONNECT_OUT@@@Z`
- size: `1966`
- prototype: `_BOOL8 __fastcall(DrSession *this, struct tagCHANNEL_CONNECT_IN *, struct tagCHANNEL_CONNECT_OUT *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001d9d4`

## callees

- `0x1400016a0`
- `0x140001830`
- `0x140002200`
- `0x14000278c`
- `0x140002a40`
- `0x140002d20`
- `0x14000324c`
- `0x14000327c`
- `0x1400032c0`
- `0x1400049b8`
- `0x1400049fc`
- `0x140006560`
- `0x140011168`
- `0x140011204`
- `0x14001195c`
- `0x14001b144`
- `0x14001b210`
- `0x14001b4d0`
- `0x14001bf2c`
- `0x14001cb3c`
- `0x14001d698`
- `0x14001fefc`
- `0x140024830`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001c166`
- `ntoskrnl!ExAllocatePool2` at `0x14001c166`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14001c2a7`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14001c2a7`
- `ntoskrnl!ZwClose` at `0x14001c60c`
- `ntoskrnl!ZwClose` at `0x14001c652`
- `ntoskrnl!ZwClose` at `0x14001c60c`
- `ntoskrnl!ZwClose` at `0x14001c652`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001c351`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001c433`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001c351`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001c433`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c5e9`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c62f`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c5e9`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c62f`
- `ntoskrnl!IoFileObjectType` at `0x14001c325`
- `ntoskrnl!IoFileObjectType` at `0x14001c40b`
- `ntoskrnl!KeResetEvent` at `0x14001c039`
- `ntoskrnl!KeResetEvent` at `0x14001c039`

## pseudocode

```c
_BOOL8 __fastcall DrSession::Connect(
        DrSession *this,
        struct tagCHANNEL_CONNECT_IN *a2,
        struct tagCHANNEL_CONNECT_OUT *a3)
{
  VirtualChannel *v3; // rbx
  char *v6; // r15
  int v8; // ecx
  int v9; // eax
  int v10; // ecx
  int v11; // eax
  int v12; // ecx
  int v13; // eax
  int v14; // ecx
  int v15; // eax
  int v16; // ecx
  int v17; // edx
  int v18; // r13d
  NTSTATUS v19; // esi
  BOOL v20; // r12d
  VirtualChannel *Pool2; // rax
  const char *v22; // r9
  const char *v23; // rbp
  HANDLE CurrentProcessId; // rax
  const char *v25; // r9
  bool v26; // zf
  void **v27; // rcx
  unsigned int v28; // r8d
  int TermDD; // eax
  PDEVICE_OBJECT v30; // rcx
  __int64 v31; // rdx
  const char *v32; // r9
  PDEVICE_OBJECT v33; // rcx
  __int64 v34; // rdx
  NTSTATUS v35; // eax
  void *v36; // rcx
  void *v37; // rcx
  void *v38; // rcx
  void *v39; // rcx
  int v40; // [rsp+40h] [rbp-48h]
  __int64 v41; // [rsp+90h] [rbp+8h] BYREF
  VirtualChannel *v42; // [rsp+A0h] [rbp+18h] BYREF

  v3 = 0;
  v42 = 0;
  v41 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      31,
      WPP_5c887063686c325024567ba4647d07cf_Traceguids,
      *(unsigned int *)a2);
  v6 = (char *)this + 208;
  (*(void (__fastcall **)(char *, struct tagCHANNEL_CONNECT_IN *, struct tagCHANNEL_CONNECT_OUT *))(*((_QWORD *)this + 26)
                                                                                                  + 24LL))(
    (char *)this + 208,
    a2,
    a3);
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 150, 1, 0) )
  {
    DrSession::LockRDPDYNConnectStateChange(this);
    *((_DWORD *)this + 345) = *((_DWORD *)a2 + 6);
    *((_DWORD *)this + 345) = *((_DWORD *)a2 + 6);
    RDPDYN_SessionConnected(*(unsigned int *)a2);
    DrSession::UnlockRDPDYNConnectStateChange(this);
    KeResetEvent((PRKEVENT)((char *)this + 640));
    *((_DWORD *)this + 282) = *(_DWORD *)a2;
    v8 = *((_DWORD *)this + 148) ^ (*((_DWORD *)a2 + 9) ^ *((_DWORD *)this + 148)) & 1;
    *((_DWORD *)this + 148) = v8;
    v9 = v8 ^ (*((_DWORD *)a2 + 9) ^ v8) & 2;
    *((_DWORD *)this + 148) = v9;
    v10 = v9 ^ (*((_DWORD *)a2 + 9) ^ v9) & 4;
    *((_DWORD *)this + 148) = v10;
    v11 = v10 ^ (*((_DWORD *)a2 + 9) ^ v10) & 8;
    *((_DWORD *)this + 148) = v11;
    v12 = v11 ^ (*((_DWORD *)a2 + 9) ^ v11) & 0x10;
    *((_DWORD *)this + 148) = v12;
    v13 = v12 ^ (*((_DWORD *)a2 + 9) ^ v12) & 0x20;
    *((_DWORD *)this + 148) = v13;
    v14 = v13 ^ (*((_DWORD *)a2 + 9) ^ v13) & 0x40;
    *((_DWORD *)this + 148) = v14;
    v15 = v14 ^ (*((_DWORD *)a2 + 9) ^ v14) & 0x80;
    *((_DWORD *)this + 148) = v15;
    v16 = v15 ^ (*((_DWORD *)a2 + 9) ^ v15) & 0x100;
    *((_DWORD *)this + 148) = v16;
    v17 = v16 ^ (*((_DWORD *)a2 + 9) ^ v16) & 0x200;
    *((_DWORD *)this + 148) = v17;
    *((_DWORD *)this + 148) = v17 ^ ((unsigned __int16)v17 ^ (unsigned __int16)(*((_DWORD *)a2 + 9) >> 1)) & 0x400;
    *((_DWORD *)this + 170) = *(_DWORD *)a2;
    v18 = DrExchangeManager::Start((DrSession *)((char *)this + 688));
    v19 = v18 == 0 ? 0xC0000001 : 0;
    v20 = *((_QWORD *)a2 + 2) == 1234;
    if ( v18 )
    {
      Pool2 = (VirtualChannel *)ExAllocatePool2(64, 184, 1245859668);
      if ( Pool2 )
        Pool2 = VirtualChannel::VirtualChannel(Pool2);
      SmartPtr<VirtualChannel>::operator=(&v42, Pool2);
      v3 = v42;
      if ( v42 )
      {
        if ( VirtualChannel::Create(
               v42,
               *(void **)((char *)a2 + (*((_DWORD *)this + 345) != 0 ? 0x20 : 0) + 8),
               *(_DWORD *)a2,
               v22,
               (struct _KEVENT *)((char *)this + 640),
               this,
               v20,
               *((_DWORD *)this + 345),
               v40) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              33,
              WPP_5c887063686c325024567ba4647d07cf_Traceguids,
              *(unsigned int *)a2);
          v19 = 0;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              34,
              WPP_5c887063686c325024567ba4647d07cf_Traceguids,
              *(unsigned int *)a2);
          v19 = -1073741823;
        }
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        35,
        WPP_5c887063686c325024567ba4647d07cf_Traceguids,
        (unsigned int)v19);
    *((_QWORD *)this + 166) = 0;
    v23 = "AUDIO_PLAYBACK_DVC";
    if ( !*((_DWORD *)a2 + 14) )
      v23 = "RDPSND";
    if ( (*((_DWORD *)this + 148) & 0x200) != 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v31 = 43;
        goto LABEL_62;
      }
      goto LABEL_63;
    }
    CurrentProcessId = PsGetCurrentProcessId();
    v26 = *((_DWORD *)this + 345) == 0;
    *((_QWORD *)this + 166) = CurrentProcessId;
    v27 = (void **)((char *)this + 1336);
    v28 = *(_DWORD *)a2;
    if ( v26 )
      TermDD = CreateTermDD(v27, *((void **)a2 + 1), v28, v23, v20);
    else
      TermDD = ReferenceRdpExtensionChannel(v27, *((HANDLE *)a2 + 6), v28, v25);
    if ( TermDD < 0 )
    {
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_55;
      v34 = 38;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          36,
          WPP_5c887063686c325024567ba4647d07cf_Traceguids,
          *(unsigned int *)a2);
      v19 = ObReferenceObjectByHandle(
              *((HANDLE *)this + 167),
              3u,
              (POBJECT_TYPE)IoFileObjectType,
              0,
              (PVOID *)this + 168,
              0);
      if ( v19 < 0 )
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v31 = 37;
LABEL_62:
          WPP_SF_d(v30->AttachedDevice, v31, WPP_5c887063686c325024567ba4647d07cf_Traceguids, *(unsigned int *)a2);
          goto LABEL_63;
        }
        goto LABEL_63;
      }
      v32 = (const char *)*((unsigned int *)a2 + 18);
      if ( !(_DWORD)v32 )
        goto LABEL_63;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          39,
          WPP_5c887063686c325024567ba4647d07cf_Traceguids,
          v32,
          *((_DWORD *)a2 + 16));
      if ( (int)ReferenceRdpExtensionChannel((PHANDLE)this + 169, *((HANDLE *)a2 + 8), *(_DWORD *)a2, v32) >= 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            40,
            WPP_5c887063686c325024567ba4647d07cf_Traceguids,
            *(unsigned int *)a2);
        v19 = ObReferenceObjectByHandle(
                *((HANDLE *)this + 169),
                3u,
                (POBJECT_TYPE)IoFileObjectType,
                0,
                (PVOID *)this + 170,
                0);
        if ( v19 < 0 )
        {
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v31 = 41;
            goto LABEL_62;
          }
        }
LABEL_63:
        DrSession::LoadQueryDirPrefetchSettings(this);
        *((_DWORD *)this + 317) = DrDeviceManager::GetSpecialDeviceCap((DrSession *)((char *)this + 912));
        if ( v19 >= 0 )
        {
          SmartPtr<VirtualChannel>::operator=((char *)this + 40, &v42);
          v35 = DrSession::ServerAnnounceWrite(this);
          v19 = 0;
          if ( v35 != 259 )
            v19 = v35;
          if ( v19 >= 0 )
          {
            *((_DWORD *)this + 149) = 1;
            DrSession::ReadPacket(this);
            (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 32LL))((char *)this + 208);
LABEL_86:
            SmartPtr<DrFile>::~SmartPtr<DrFile>(&v41);
            SmartPtr<DrFile>::~SmartPtr<DrFile>(&v42);
            return v19 >= 0;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              44,
              WPP_5c887063686c325024567ba4647d07cf_Traceguids,
              (unsigned int)v19);
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            45,
            WPP_5c887063686c325024567ba4647d07cf_Traceguids,
            (unsigned int)v19);
        if ( v3 )
        {
          SmartPtr<VirtualChannel>::operator=(&v42, 0);
          DrSession::DeleteChannel(this, 1);
        }
        if ( v18 )
          DrExchangeManager::Stop((DrSession *)((char *)this + 688));
        DrSession::LockRDPDYNConnectStateChange(this);
        *((_DWORD *)this + 149) = 4;
        RDPDYN_SessionDisconnected(*(_DWORD *)a2);
        DrSession::UnlockRDPDYNConnectStateChange(this);
        v36 = (void *)*((_QWORD *)this + 168);
        if ( v36 )
        {
          ObfDereferenceObject(v36);
          *((_QWORD *)this + 168) = 0;
        }
        v37 = (void *)*((_QWORD *)this + 167);
        if ( v37 )
        {
          ZwClose(v37);
          *((_QWORD *)this + 167) = 0;
        }
        v38 = (void *)*((_QWORD *)this + 170);
        if ( v38 )
        {
          ObfDereferenceObject(v38);
          *((_QWORD *)this + 170) = 0;
        }
        v39 = (void *)*((_QWORD *)this + 169);
        if ( v39 )
        {
          ZwClose(v39);
          *((_QWORD *)this + 169) = 0;
        }
        _InterlockedCompareExchange((volatile signed __int32 *)this + 150, 0, 1);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 32LL))((char *)this + 208);
        goto LABEL_86;
      }
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
LABEL_55:
        v19 = -1073741823;
        goto LABEL_63;
      }
      v34 = 42;
    }
    WPP_SF_d(v33->AttachedDevice, v34, WPP_5c887063686c325024567ba4647d07cf_Traceguids, *(unsigned int *)a2);
    goto LABEL_55;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_5c887063686c325024567ba4647d07cf_Traceguids);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 32LL))((char *)this + 208);
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v41);
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v42);
  return 0;
}

```

## disassembly

```asm
0x14001bf2c  mov     rax, rsp
0x14001bf2f  mov     [rax+10h], rbx
0x14001bf33  mov     [rax+18h], r8
0x14001bf37  push    rbp
0x14001bf38  push    rsi
0x14001bf39  push    rdi
0x14001bf3a  push    r12
0x14001bf3c  push    r13
0x14001bf3e  push    r14
0x14001bf40  push    r15
0x14001bf42  sub     rsp, 50h
0x14001bf46  xor     ebx, ebx
0x14001bf48  mov     r14, rdx
0x14001bf4b  mov     [rax+18h], rbx
0x14001bf4f  mov     rdi, rcx
0x14001bf52  mov     [rax+8], rbx
0x14001bf56  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf5d  lea     rsi, WPP_GLOBAL_Control
0x14001bf64  cmp     rcx, rsi
0x14001bf67  jz      short loc_14001BF85
0x14001bf69  cmp     byte ptr [rcx+29h], 4
0x14001bf6d  jb      short loc_14001BF85
0x14001bf6f  mov     r9d, [r14]
0x14001bf72  lea     edx, [rbx+1Fh]
0x14001bf75  mov     rcx, [rcx+18h]
0x14001bf79  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x14001bf80  call    WPP_SF_d
0x14001bf85  lea     r15, [rdi+0D0h]
0x14001bf8c  mov     rax, [r15]
0x14001bf8f  mov     rcx, r15
0x14001bf92  mov     rax, [rax+18h]
0x14001bf96  call    _guard_dispatch_icall
0x14001bf9b  xor     eax, eax
0x14001bf9d  lea     r12d, [rax+1]
0x14001bfa1  lock cmpxchg [rdi+258h], r12d
0x14001bfaa  jz      short loc_14001C003
0x14001bfac  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bfb3  cmp     rcx, rsi
0x14001bfb6  jz      short loc_14001BFD3
0x14001bfb8  cmp     byte ptr [rcx+29h], 5
0x14001bfbc  jb      short loc_14001BFD3
0x14001bfbe  mov     rcx, [rcx+18h]
0x14001bfc2  lea     edx, [r12+1Fh]
0x14001bfc7  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x14001bfce  call    WPP_SF_
0x14001bfd3  mov     rax, [r15]
0x14001bfd6  mov     rcx, r15
0x14001bfd9  mov     rax, [rax+20h]
0x14001bfdd  call    _guard_dispatch_icall
0x14001bfe2  lea     rcx, [rsp+88h+arg_0]
0x14001bfea  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001bfef  lea     rcx, [rsp+88h+arg_10]
0x14001bff7  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001bffc  xor     eax, eax
0x14001bffe  jmp     loc_14001C6A6
0x14001c003  mov     rcx, rdi; this
0x14001c006  call    ?LockRDPDYNConnectStateChange@DrSession@@QEAAXXZ; DrSession::LockRDPDYNConnectStateChange(void)
0x14001c00b  mov     eax, [r14+18h]
0x14001c00f  mov     [rdi+564h], eax
0x14001c015  mov     eax, [r14+18h]
0x14001c019  mov     [rdi+564h], eax
0x14001c01f  mov     ecx, [r14]
0x14001c022  call    RDPDYN_SessionConnected
0x14001c027  mov     rcx, rdi; this
0x14001c02a  call    ?UnlockRDPDYNConnectStateChange@DrSession@@QEAAXXZ; DrSession::UnlockRDPDYNConnectStateChange(void)
0x14001c02f  lea     rbp, [rdi+280h]
0x14001c036  mov     rcx, rbp; Event
0x14001c039  call    cs:__imp_KeResetEvent
0x14001c040  nop     dword ptr [rax+rax+00h]
0x14001c045  mov     eax, [r14]
0x14001c048  mov     [rdi+468h], eax
0x14001c04e  mov     eax, [rdi+250h]
0x14001c054  mov     ecx, eax
0x14001c056  xor     ecx, [r14+24h]
0x14001c05a  and     ecx, r12d
0x14001c05d  xor     ecx, eax
0x14001c05f  mov     [rdi+250h], ecx
0x14001c065  mov     eax, ecx
0x14001c067  xor     eax, [r14+24h]
0x14001c06b  and     eax, 2
0x14001c06e  xor     eax, ecx
0x14001c070  mov     [rdi+250h], eax
0x14001c076  mov     ecx, eax
0x14001c078  xor     ecx, [r14+24h]
0x14001c07c  and     ecx, 4
0x14001c07f  xor     ecx, eax
0x14001c081  mov     [rdi+250h], ecx
0x14001c087  mov     eax, ecx
0x14001c089  xor     eax, [r14+24h]
0x14001c08d  and     eax, 8
0x14001c090  xor     eax, ecx
0x14001c092  mov     [rdi+250h], eax
0x14001c098  mov     ecx, eax
0x14001c09a  xor     ecx, [r14+24h]
0x14001c09e  and     ecx, 10h
0x14001c0a1  xor     ecx, eax
0x14001c0a3  mov     [rdi+250h], ecx
0x14001c0a9  mov     eax, ecx
0x14001c0ab  xor     eax, [r14+24h]
0x14001c0af  and     eax, 20h
0x14001c0b2  xor     eax, ecx
0x14001c0b4  mov     [rdi+250h], eax
0x14001c0ba  mov     ecx, eax
0x14001c0bc  xor     ecx, [r14+24h]
0x14001c0c0  and     ecx, 40h
0x14001c0c3  xor     ecx, eax
0x14001c0c5  mov     [rdi+250h], ecx
0x14001c0cb  mov     eax, ecx
0x14001c0cd  xor     eax, [r14+24h]
0x14001c0d1  and     eax, 80h
0x14001c0d6  xor     eax, ecx
0x14001c0d8  mov     [rdi+250h], eax
0x14001c0de  mov     ecx, eax
0x14001c0e0  xor     ecx, [r14+24h]
0x14001c0e4  and     ecx, 100h
0x14001c0ea  xor     ecx, eax
0x14001c0ec  mov     [rdi+250h], ecx
0x14001c0f2  mov     edx, ecx
0x14001c0f4  xor     edx, [r14+24h]
0x14001c0f8  and     edx, 200h
0x14001c0fe  xor     edx, ecx
0x14001c100  lea     rcx, [rdi+2B0h]; this
0x14001c107  mov     [rdi+250h], edx
0x14001c10d  mov     eax, [r14+24h]
0x14001c111  shr     eax, 1
0x14001c113  xor     eax, edx
0x14001c115  and     eax, 400h
0x14001c11a  xor     eax, edx
0x14001c11c  mov     [rdi+250h], eax
0x14001c122  mov     eax, [r14]
0x14001c125  mov     [rdi+2A8h], eax
0x14001c12b  call    ?Start@DrExchangeManager@@QEAAHXZ; DrExchangeManager::Start(void)
0x14001c130  mov     ecx, eax
0x14001c132  mov     r13d, eax
0x14001c135  neg     ecx
0x14001c137  sbb     esi, esi
0x14001c139  not     esi
0x14001c13b  xor     r12d, r12d
0x14001c13e  and     esi, 0C0000001h
0x14001c144  cmp     qword ptr [r14+10h], 4D2h
0x14001c14c  setz    r12b
0x14001c150  test    eax, eax
0x14001c152  jz      loc_14001C244
0x14001c158  mov     edx, 0B8h
0x14001c15d  mov     r8d, 4A424F54h
0x14001c163  lea     ecx, [rdx-78h]
0x14001c166  call    cs:__imp_ExAllocatePool2
0x14001c16d  nop     dword ptr [rax+rax+00h]
0x14001c172  test    rax, rax
0x14001c175  jz      short loc_14001C17F
0x14001c177  mov     rcx, rax; this
0x14001c17a  call    ??0VirtualChannel@@QEAA@XZ; VirtualChannel::VirtualChannel(void)
0x14001c17f  mov     rdx, rax
0x14001c182  lea     rcx, [rsp+88h+arg_10]
0x14001c18a  call    ??4?$SmartPtr@VVirtualChannel@@@@QEAAAEAV0@PEAVVirtualChannel@@@Z; SmartPtr<VirtualChannel>::operator=(VirtualChannel *)
0x14001c18f  mov     rbx, [rsp+88h+arg_10]
0x14001c197  test    rbx, rbx
0x14001c19a  jz      loc_14001C244
0x14001c1a0  mov     ecx, [rdi+564h]
0x14001c1a6  mov     eax, ecx
0x14001c1a8  mov     r8d, [r14]; unsigned int
0x14001c1ab  neg     eax
0x14001c1ad  mov     [rsp+88h+var_50], ecx; int
0x14001c1b1  mov     rcx, rbx; this
0x14001c1b4  sbb     rdx, rdx
0x14001c1b7  mov     [rsp+88h+var_58], r12d; int
0x14001c1bc  and     edx, 20h
0x14001c1bf  mov     [rsp+88h+HandleInformation], rdi; struct RefCount *
0x14001c1c4  mov     [rsp+88h+Object], rbp; struct _KEVENT *
0x14001c1c9  mov     rdx, [rdx+r14+8]; void *
0x14001c1ce  call    ?Create@VirtualChannel@@QEAAHPEAXKPEBDPEAU_KEVENT@@PEAVRefCount@@HHH@Z; VirtualChannel::Create(void *,ulong,char const *,_KEVENT *,RefCount *,int,int,int)
0x14001c1d3  test    eax, eax
0x14001c1d5  jz      short loc_14001C20C
0x14001c1d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c1de  lea     rbp, WPP_GLOBAL_Control
0x14001c1e5  cmp     rcx, rbp
0x14001c1e8  jz      short loc_14001C208
0x14001c1ea  cmp     byte ptr [rcx+29h], 4
0x14001c1ee  jb      short loc_14001C208
0x14001c1f0  mov     r9d, [r14]
0x14001c1f3  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x14001c1fa  mov     rcx, [rcx+18h]
0x14001c1fe  mov     edx, 21h ; '!'
0x14001c203  call    WPP_SF_d
0x14001c208  xor     esi, esi
0x14001c20a  jmp     short loc_14001C24B
0x14001c20c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c213  lea     rbp, WPP_GLOBAL_Control
0x14001c21a  cmp     rcx, rbp
0x14001c21d  jz      short loc_14001C23D
0x14001c21f  cmp     byte ptr [rcx+29h], 5
0x14001c223  jb      short loc_14001C23D
0x14001c225  mov     r9d, [r14]
0x14001c228  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x14001c22f  mov     rcx, [rcx+18h]
0x14001c233  mov     edx, 22h ; '"'
0x14001c238  call    WPP_SF_d
0x14001c23d  mov     esi, 0C0000001h
0x14001c242  jmp     short loc_14001C24B
0x14001c244  lea     rbp, WPP_GLOBAL_Control
0x14001c24b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c252  cmp     rcx, rbp
0x14001c255  jz      short loc_14001C275
0x14001c257  cmp     byte ptr [rcx+29h], 4
0x14001c25b  jb      short loc_14001C275
0x14001c25d  mov     rcx, [rcx+18h]
0x14001c261  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x14001c268  mov     edx, 23h ; '#'
0x14001c26d  mov     r9d, esi
0x14001c270  call    WPP_SF_d
0x14001c275  mov     qword ptr [rdi+530h], 0
0x14001c280  lea     rcx, aRdpsnd; "RDPSND"
0x14001c287  cmp     dword ptr [r14+38h], 0
0x14001c28c  lea     rbp, aAudioPlaybackD; "AUDIO_PLAYBACK_DVC"
0x14001c293  cmovz   rbp, rcx
0x14001c297  test    dword ptr [rdi+250h], 200h
0x14001c2a1  jnz     loc_14001C4BB
0x14001c2a7  call    cs:__imp_PsGetCurrentProcessId
0x14001c2ae  nop     dword ptr [rax+rax+00h]
0x14001c2b3  cmp     dword ptr [rdi+564h], 0
0x14001c2ba  lea     rsi, [rdi+538h]
0x14001c2c1  mov     [rdi+530h], rax
0x14001c2c8  mov     rcx, rsi; Handle
0x14001c2cb  mov     r8d, [r14]; unsigned int
0x14001c2ce  jnz     short loc_14001C2E3
0x14001c2d0  mov     rdx, [r14+8]; void *
0x14001c2d4  mov     r9, rbp; char *
0x14001c2d7  mov     dword ptr [rsp+88h+Object], r12d; int
0x14001c2dc  call    ?CreateTermDD@@YAJPEAPEAXPEAXKPEBDH@Z; CreateTermDD(void * *,void *,ulong,char const *,int)
0x14001c2e1  jmp     short loc_14001C2EC
0x14001c2e3  mov     rdx, [r14+30h]; HANDLE
0x14001c2e7  call    ?ReferenceRdpExtensionChannel@@YAJPEAPEAXPEAXKPEBD@Z; ReferenceRdpExtensionChannel(void * *,void *,ulong,char const *)
0x14001c2ec  test    eax, eax
0x14001c2ee  js      loc_14001C49B
0x14001c2f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c2fb  lea     rbp, WPP_GLOBAL_Control
0x14001c302  cmp     rcx, rbp
0x14001c305  jz      short loc_14001C325
0x14001c307  cmp     byte ptr [rcx+29h], 4
0x14001c30b  jb      short loc_14001C325
0x14001c30d  mov     r9d, [r14]
0x14001c310  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x14001c317  mov     rcx, [rcx+18h]
0x14001c31b  mov     edx, 24h ; '$'
0x14001c320  call    WPP_SF_d
0x14001c325  mov     r8, cs:__imp_IoFileObjectType
0x14001c32c  lea     rax, [rdi+540h]
0x14001c333  mov     rcx, [rsi]; Handle
0x14001c336  xor     r9d, r9d; AccessMode
0x14001c339  mov     [rsp+88h+HandleInformation], 0; HandleInformation
0x14001c342  mov     [rsp+88h+Object], rax; Object
0x14001c347  mov     r8, [r8]; ObjectType
0x14001c34a  lea     r12d, [r9+3]
0x14001c34e  mov     edx, r12d; DesiredAccess
0x14001c351  call    cs:__imp_ObReferenceObjectByHandle
0x14001c358  nop     dword ptr [rax+rax+00h]
0x14001c35d  mov     esi, eax
0x14001c35f  test    eax, eax
0x14001c361  jns     short loc_14001C387
0x14001c363  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c36a  cmp     rcx, rbp
0x14001c36d  jz      loc_14001C4EC
0x14001c373  cmp     byte ptr [rcx+29h], 2
0x14001c377  jb      loc_14001C4EC
0x14001c37d  lea     edx, [r12+22h]
0x14001c382  jmp     loc_14001C4D9
0x14001c387  mov     r9d, [r14+48h]
0x14001c38b  test    r9d, r9d
0x14001c38e  jz      loc_14001C4EC
0x14001c394  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c39b  cmp     rcx, rbp
0x14001c39e  jz      short loc_14001C3C3
0x14001c3a0  cmp     byte ptr [rcx+29h], 4
0x14001c3a4  jb      short loc_14001C3C3
0x14001c3a6  mov     eax, [r14+40h]
0x14001c3aa  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x14001c3b1  mov     rcx, [rcx+18h]
0x14001c3b5  mov     edx, 27h ; '''
0x14001c3ba  mov     dword ptr [rsp+88h+Object], eax
0x14001c3be  call    WPP_SF_dd
0x14001c3c3  mov     r8d, [r14]; unsigned int
0x14001c3c6  lea     rsi, [rdi+548h]
0x14001c3cd  mov     rdx, [r14+40h]; HANDLE
0x14001c3d1  mov     rcx, rsi; Handle
0x14001c3d4  call    ?ReferenceRdpExtensionChannel@@YAJPEAPEAXPEAXKPEBD@Z; ReferenceRdpExtensionChannel(void * *,void *,ulong,char const *)
0x14001c3d9  test    eax, eax
0x14001c3db  js      loc_14001C46A
0x14001c3e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c3e8  cmp     rcx, rbp
0x14001c3eb  jz      short loc_14001C40B
0x14001c3ed  cmp     byte ptr [rcx+29h], 4
0x14001c3f1  jb      short loc_14001C40B
0x14001c3f3  mov     r9d, [r14]
0x14001c3f6  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x14001c3fd  mov     rcx, [rcx+18h]
0x14001c401  mov     edx, 28h ; '('
0x14001c406  call    WPP_SF_d
0x14001c40b  mov     r8, cs:__imp_IoFileObjectType
0x14001c412  lea     rax, [rdi+550h]
0x14001c419  mov     rcx, [rsi]; Handle
  ... truncated ...
```
