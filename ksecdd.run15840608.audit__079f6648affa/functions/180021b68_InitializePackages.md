# InitializePackages

- ea: `0x180021b68`
- end: `0x180022043`
- name: `InitializePackages`
- size: `1243`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180006bf4`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180001f90`
- `0x180002820`
- `0x180002900`
- `0x18000c44c`
- `0x18000c4c0`
- `0x180010980`
- `0x180010d00`
- `0x180020b14`
- `0x180020ccc`
- `0x180021b68`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x180021f3d`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x180021f3d`
- `ntoskrnl!KeWaitForSingleObject` at `0x180021ff7`
- `ntoskrnl!KeWaitForSingleObject` at `0x180021ff7`
- `ntoskrnl!ExAcquireFastMutex` at `0x180021be6`
- `ntoskrnl!ExAcquireFastMutex` at `0x180021be6`
- `ntoskrnl!ExReleaseFastMutex` at `0x180021bfe`
- `ntoskrnl!ExReleaseFastMutex` at `0x180021c29`
- `ntoskrnl!ExReleaseFastMutex` at `0x180021fd5`
- `ntoskrnl!ExReleaseFastMutex` at `0x180021bfe`
- `ntoskrnl!ExReleaseFastMutex` at `0x180021c29`
- `ntoskrnl!ExReleaseFastMutex` at `0x180021fd5`
- `ntoskrnl!KeSetEvent` at `0x180021fa9`
- `ntoskrnl!KeSetEvent` at `0x180021fa9`
- `ntoskrnl!ExAllocatePool2` at `0x180021c51`
- `ntoskrnl!ExAllocatePool2` at `0x180021c7a`
- `ntoskrnl!ExAllocatePool2` at `0x180021c51`
- `ntoskrnl!ExAllocatePool2` at `0x180021c7a`
- `ntoskrnl!RtlInitUnicodeString` at `0x180021cc7`
- `ntoskrnl!RtlInitUnicodeString` at `0x180021cc7`

## pseudocode

```c
__int64 __fastcall InitializePackages(unsigned int a1)
{
  __int64 v1; // r12
  unsigned int v2; // ebx
  __int64 v3; // rbx
  __int64 Pool2; // rax
  __int64 v5; // rax
  int Package; // r15d
  unsigned int v7; // r14d
  UNICODE_STRING *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdi
  _OWORD *v11; // rcx
  int v12; // ecx
  __int64 v13; // rax
  unsigned int v14; // esi
  __int64 v15; // r8
  __int64 v16; // rdi
  KAFFINITY ProcessorHistory; // rdx
  int v18; // eax
  unsigned int i; // edi
  void (__fastcall **v20)(__int64 (__fastcall **)(unsigned int)); // rax
  _QWORD v22[24]; // [rsp+30h] [rbp-69h] BYREF
  char v24; // [rsp+108h] [rbp+6Fh] BYREF
  __int64 v25; // [rsp+110h] [rbp+77h] BYREF

  v1 = a1;
  v25 = 0;
  memset((char *)v22 + 2, 0, 0x8Eu);
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v24);
  if ( !KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)&v24) )
  {
    v2 = -1073741058;
LABEL_51:
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v24);
    return v2;
  }
  v3 = KsecddLsaStateRef::operator _KSECDDLSASTATE *(&v24);
  if ( *(_BYTE *)(v3 + 468) )
  {
LABEL_54:
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v24);
    return 0;
  }
  ExAcquireFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.DeviceQueue);
  if ( *(_BYTE *)(v3 + 468) )
  {
    ExReleaseFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.DeviceQueue);
    v2 = 0;
    goto LABEL_51;
  }
  if ( KsecConnectionIndicator )
  {
    ExReleaseFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.DeviceQueue);
    KeWaitForSingleObject(&WPP_MAIN_CB.Queue.Wcb.CurrentIrp, UserRequest, 0, 0, 0);
    if ( !*(_BYTE *)(v3 + 468) )
    {
      KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v24);
      return 3221225473LL;
    }
    goto LABEL_54;
  }
  KsecConnectionIndicator = 1;
  ExReleaseFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.DeviceQueue);
  Pool2 = ExAllocatePool2(64, 8 * v1, 1667593035);
  *(_QWORD *)(v3 + 456) = Pool2;
  if ( !Pool2 || (v5 = ExAllocatePool2(64, 16 * v1, 1667593035), (*(_QWORD *)(v3 + 528) = v5) == 0) )
  {
    v2 = -2146893056;
    goto LABEL_51;
  }
  Package = 0;
  v7 = 0;
  if ( *(_DWORD *)(v3 + 480) )
  {
    do
    {
      v8 = *(UNICODE_STRING **)(*(_QWORD *)(v3 + 472) + 40LL * v7 + 8);
      RtlInitUnicodeString(v8, v8->Buffer);
      Package = SecpFindPackage(*(_QWORD *)(*(_QWORD *)(v3 + 472) + 40LL * v7 + 8), &v25);
      if ( Package < 0 )
        goto LABEL_23;
      v10 = v25;
      Package = SecpGetBinding(v25, v22);
      if ( v22[1] )
      {
        SecFreeForKsecCaller();
        v22[1] = 0;
      }
      if ( Package < 0 || *(_QWORD *)(*(_QWORD *)(v3 + 456) + 8 * v10) )
      {
LABEL_23:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            11,
            v9,
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 472) + 40LL * v7 + 8) + 8LL));
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
          WPP_SF_SI(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            10,
            v9,
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 472) + 40LL * v7 + 8) + 8LL),
            v10);
        *(_QWORD *)(*(_QWORD *)(v3 + 456) + 8 * v10) = *(_QWORD *)(*(_QWORD *)(v3 + 472) + 40LL * v7);
        v11 = *(_OWORD **)(*(_QWORD *)(v3 + 472) + 40LL * v7 + 32);
        if ( v11 )
          *(_OWORD *)(*(_QWORD *)(v3 + 528) + 16 * v10) = *v11;
        v12 = HIDWORD(v22[6]);
        *(_QWORD *)(*(_QWORD *)(v3 + 472) + 40LL * v7 + 16) = v10;
        *(_DWORD *)(*(_QWORD *)(v3 + 472) + 40LL * v7 + 24) = v12;
        if ( (v12 & 0x100000) != 0 )
        {
          v13 = *(_QWORD *)(v3 + 456);
          KsecddGlobalExtenderPackageId = v10;
          KsecddGlobalExtenderPackage = *(_QWORD *)(v13 + 8 * v10);
        }
      }
      ++v7;
    }
    while ( v7 < *(_DWORD *)(v3 + 480) );
    LODWORD(v1) = a1;
  }
  if ( KsecDeferredPackageCount )
  {
    v14 = 0;
    do
    {
      Package = SecpFindPackage(*(_QWORD *)(WPP_MAIN_CB.Dpc.ProcessorHistory + 40LL * v14 + 8), &v25);
      if ( Package < 0 )
        goto LABEL_39;
      v16 = v25;
      Package = SecpGetBinding(v25, v22);
      if ( v22[1] )
      {
        SecFreeForKsecCaller();
        v22[1] = 0;
      }
      if ( Package < 0 || *(_QWORD *)(*(_QWORD *)(v3 + 456) + 8 * v16) )
      {
LABEL_39:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            13,
            v15,
            *(_QWORD *)(*(_QWORD *)(WPP_MAIN_CB.Dpc.ProcessorHistory + 40LL * v14 + 8) + 8LL));
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
          WPP_SF_SI(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            12,
            v15,
            *(_QWORD *)(*(_QWORD *)(WPP_MAIN_CB.Dpc.ProcessorHistory + 40LL * v14 + 8) + 8LL),
            v16);
        ProcessorHistory = WPP_MAIN_CB.Dpc.ProcessorHistory;
        *(_QWORD *)(*(_QWORD *)(v3 + 456) + 8 * v16) = *(_QWORD *)(WPP_MAIN_CB.Dpc.ProcessorHistory + 40LL * v14);
        v18 = HIDWORD(v22[6]);
        *(_QWORD *)(ProcessorHistory + 40LL * v14 + 16) = v16;
        *(_DWORD *)(*(_QWORD *)(v3 + 472) + 40LL * v14 + 24) = v18;
      }
      ++v14;
    }
    while ( v14 < KsecDeferredPackageCount );
    LODWORD(v1) = a1;
  }
  if ( (unsigned __int8)PsIsCurrentThreadInServerSilo() )
  {
    *(_BYTE *)(v3 + 468) = 1;
  }
  else
  {
    for ( i = 0; i < (unsigned int)v1; ++i )
    {
      v20 = *(void (__fastcall ***)(__int64 (__fastcall **)(unsigned int)))(*(_QWORD *)(v3 + 456) + 8LL * i);
      if ( v20 )
      {
        (*v20)(&KspKernelFunctions);
        *(_BYTE *)(v3 + 468) = 1;
      }
    }
  }
  *(_DWORD *)(v3 + 464) = v1;
  KsecConnectionIndicator = 0;
  KeSetEvent((PRKEVENT)&WPP_MAIN_CB.Queue.Wcb.CurrentIrp, 1, 0);
  KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v24);
  return (unsigned int)Package;
}

```

## disassembly

```asm
0x180021b68  mov     [rsp-8+arg_18], rbx
0x180021b6d  mov     [rsp-8+arg_0], ecx
0x180021b71  push    rbp
0x180021b72  push    rsi
0x180021b73  push    rdi
0x180021b74  push    r12
0x180021b76  push    r13
0x180021b78  push    r14
0x180021b7a  push    r15
0x180021b7c  lea     rbp, [rsp-27h]
0x180021b81  sub     rsp, 0C0h
0x180021b88  mov     r12d, ecx
0x180021b8b  xor     r13d, r13d
0x180021b8e  lea     rcx, [rbp+57h+var_BE]; void *
0x180021b92  mov     [rbp+57h+arg_10], r13
0x180021b96  xor     edx, edx; Val
0x180021b98  mov     r8d, 8Eh; Size
0x180021b9e  call    memset
0x180021ba3  lea     rcx, [rbp+57h+arg_8]; this
0x180021ba7  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180021bac  lea     rcx, [rbp+57h+arg_8]; this
0x180021bb0  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180021bb5  test    al, al
0x180021bb7  jnz     short loc_180021BC3
0x180021bb9  mov     ebx, 0C00002FEh
0x180021bbe  jmp     loc_180021FC8
0x180021bc3  lea     rcx, [rbp+57h+arg_8]
0x180021bc7  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180021bcc  mov     rbx, rax
0x180021bcf  cmp     [rax+1D4h], r13b
0x180021bd6  jnz     loc_18002201C
0x180021bdc  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x180021be3  mov     rcx, rdi; FastMutex
0x180021be6  call    cs:__imp_ExAcquireFastMutex
0x180021bed  nop     dword ptr [rax+rax+00h]
0x180021bf2  mov     rcx, rdi; FastMutex
0x180021bf5  cmp     [rbx+1D4h], r13b
0x180021bfc  jz      short loc_180021C12
0x180021bfe  call    cs:__imp_ExReleaseFastMutex
0x180021c05  nop     dword ptr [rax+rax+00h]
0x180021c0a  mov     ebx, r13d
0x180021c0d  jmp     loc_180021FC8
0x180021c12  cmp     cs:?KsecConnectionIndicator@@3JA, r13d; long KsecConnectionIndicator
0x180021c19  jnz     loc_180021FD5
0x180021c1f  mov     cs:?KsecConnectionIndicator@@3JA, 1; long KsecConnectionIndicator
0x180021c29  call    cs:__imp_ExReleaseFastMutex
0x180021c30  nop     dword ptr [rax+rax+00h]
0x180021c35  mov     esi, 6365734Bh
0x180021c3a  lea     rdx, ds:0[r12*8]
0x180021c42  mov     r14d, 40h ; '@'
0x180021c48  mov     r8d, esi
0x180021c4b  mov     ecx, r14d
0x180021c4e  mov     rdi, r12
0x180021c51  call    cs:__imp_ExAllocatePool2
0x180021c58  nop     dword ptr [rax+rax+00h]
0x180021c5d  mov     [rbx+1C8h], rax
0x180021c64  test    rax, rax
0x180021c67  jz      loc_180021FC3
0x180021c6d  shl     rdi, 4
0x180021c71  mov     r8d, esi
0x180021c74  mov     rdx, rdi
0x180021c77  mov     ecx, r14d
0x180021c7a  call    cs:__imp_ExAllocatePool2
0x180021c81  nop     dword ptr [rax+rax+00h]
0x180021c86  mov     [rbx+210h], rax
0x180021c8d  test    rax, rax
0x180021c90  jz      loc_180021FC3
0x180021c96  mov     r15d, r13d
0x180021c99  mov     r14d, r13d
0x180021c9c  cmp     [rbx+1E0h], r13d
0x180021ca3  jbe     loc_180021E23
0x180021ca9  lea     r12, WPP_GLOBAL_Control
0x180021cb0  mov     eax, r14d
0x180021cb3  lea     rsi, [rax+rax*4]
0x180021cb7  mov     rax, [rbx+1D8h]
0x180021cbe  mov     rcx, [rax+rsi*8+8]; DestinationString
0x180021cc3  mov     rdx, [rcx+8]; SourceString
0x180021cc7  call    cs:__imp_RtlInitUnicodeString
0x180021cce  nop     dword ptr [rax+rax+00h]
0x180021cd3  mov     rcx, [rbx+1D8h]
0x180021cda  lea     rdx, [rbp+57h+arg_10]
0x180021cde  mov     rcx, [rcx+rsi*8+8]
0x180021ce3  call    SecpFindPackage
0x180021ce8  mov     r15d, eax
0x180021ceb  test    eax, eax
0x180021ced  js      loc_180021DDE
0x180021cf3  mov     rdi, [rbp+57h+arg_10]
0x180021cf7  lea     rdx, [rbp+57h+var_C0]
0x180021cfb  mov     rcx, rdi
0x180021cfe  call    SecpGetBinding
0x180021d03  mov     rcx, [rbp+57h+var_B8]
0x180021d07  mov     r15d, eax
0x180021d0a  test    rcx, rcx
0x180021d0d  jz      short loc_180021D18
0x180021d0f  call    SecFreeForKsecCaller
0x180021d14  mov     [rbp+57h+var_B8], r13
0x180021d18  test    r15d, r15d
0x180021d1b  js      loc_180021DDE
0x180021d21  mov     rax, [rbx+1C8h]
0x180021d28  cmp     [rax+rdi*8], r13
0x180021d2c  jnz     loc_180021DDE
0x180021d32  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d39  cmp     rcx, r12
0x180021d3c  jz      short loc_180021D68
0x180021d3e  mov     eax, [rcx+2Ch]
0x180021d41  test    al, 4
0x180021d43  jz      short loc_180021D68
0x180021d45  mov     rax, [rbx+1D8h]
0x180021d4c  mov     edx, 0Ah
0x180021d51  mov     rcx, [rcx+18h]
0x180021d55  mov     [rsp+0F0h+Timeout], rdi
0x180021d5a  mov     r9, [rax+rsi*8+8]
0x180021d5f  mov     r9, [r9+8]
0x180021d63  call    WPP_SF_SI
0x180021d68  mov     rax, [rbx+1D8h]
0x180021d6f  mov     rcx, [rbx+1C8h]
0x180021d76  mov     rax, [rax+rsi*8]
0x180021d7a  mov     [rcx+rdi*8], rax
0x180021d7e  mov     rax, [rbx+1D8h]
0x180021d85  mov     rcx, [rax+rsi*8+20h]
0x180021d8a  test    rcx, rcx
0x180021d8d  jz      short loc_180021DA4
0x180021d8f  movups  xmm0, xmmword ptr [rcx]
0x180021d92  mov     rax, [rbx+210h]
0x180021d99  mov     rcx, rdi
0x180021d9c  add     rcx, rcx
0x180021d9f  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x180021da4  mov     rax, [rbx+1D8h]
0x180021dab  mov     ecx, [rbp+57h+var_8C]
0x180021dae  mov     [rax+rsi*8+10h], rdi
0x180021db3  mov     rax, [rbx+1D8h]
0x180021dba  mov     [rax+rsi*8+18h], ecx
0x180021dbe  bt      ecx, 14h
0x180021dc2  jnb     short loc_180021E0F
0x180021dc4  mov     rax, [rbx+1C8h]
0x180021dcb  mov     cs:KsecddGlobalExtenderPackageId, edi
0x180021dd1  mov     rcx, [rax+rdi*8]
0x180021dd5  mov     cs:KsecddGlobalExtenderPackage, rcx
0x180021ddc  jmp     short loc_180021E0F
0x180021dde  mov     rcx, cs:WPP_GLOBAL_Control
0x180021de5  cmp     rcx, r12
0x180021de8  jz      short loc_180021E0F
0x180021dea  mov     eax, [rcx+2Ch]
0x180021ded  test    al, 1
0x180021def  jz      short loc_180021E0F
0x180021df1  mov     rax, [rbx+1D8h]
0x180021df8  mov     edx, 0Bh
0x180021dfd  mov     rcx, [rcx+18h]
0x180021e01  mov     r9, [rax+rsi*8+8]
0x180021e06  mov     r9, [r9+8]
0x180021e0a  call    WPP_SF_S
0x180021e0f  inc     r14d
0x180021e12  cmp     r14d, [rbx+1E0h]
0x180021e19  jb      loc_180021CB0
0x180021e1f  mov     r12d, [rbp+57h+arg_0]
0x180021e23  mov     eax, cs:?KsecDeferredPackageCount@@3KA; ulong KsecDeferredPackageCount
0x180021e29  test    eax, eax
0x180021e2b  jz      loc_180021F3D
0x180021e31  mov     esi, r13d
0x180021e34  lea     r12, WPP_GLOBAL_Control
0x180021e3b  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory
0x180021e42  lea     rdx, [rbp+57h+arg_10]
0x180021e46  mov     eax, esi
0x180021e48  lea     r14, [rax+rax*4]
0x180021e4c  mov     rcx, [rcx+r14*8+8]
0x180021e51  call    SecpFindPackage
0x180021e56  mov     r15d, eax
0x180021e59  test    eax, eax
0x180021e5b  js      loc_180021EFA
0x180021e61  mov     rdi, [rbp+57h+arg_10]
0x180021e65  lea     rdx, [rbp+57h+var_C0]
0x180021e69  mov     rcx, rdi
0x180021e6c  call    SecpGetBinding
0x180021e71  mov     rcx, [rbp+57h+var_B8]
0x180021e75  mov     r15d, eax
0x180021e78  test    rcx, rcx
0x180021e7b  jz      short loc_180021E86
0x180021e7d  call    SecFreeForKsecCaller
0x180021e82  mov     [rbp+57h+var_B8], r13
0x180021e86  test    r15d, r15d
0x180021e89  js      short loc_180021EFA
0x180021e8b  mov     rax, [rbx+1C8h]
0x180021e92  cmp     [rax+rdi*8], r13
0x180021e96  jnz     short loc_180021EFA
0x180021e98  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e9f  cmp     rcx, r12
0x180021ea2  jz      short loc_180021ECE
0x180021ea4  mov     eax, [rcx+2Ch]
0x180021ea7  test    al, 4
0x180021ea9  jz      short loc_180021ECE
0x180021eab  mov     rax, cs:WPP_MAIN_CB.Dpc.ProcessorHistory
0x180021eb2  mov     edx, 0Ch
0x180021eb7  mov     rcx, [rcx+18h]
0x180021ebb  mov     [rsp+0F0h+Timeout], rdi
0x180021ec0  mov     r9, [rax+r14*8+8]
0x180021ec5  mov     r9, [r9+8]
0x180021ec9  call    WPP_SF_SI
0x180021ece  mov     rcx, [rbx+1C8h]
0x180021ed5  mov     rdx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory
0x180021edc  mov     rax, [rdx+r14*8]
0x180021ee0  mov     [rcx+rdi*8], rax
0x180021ee4  mov     eax, [rbp+57h+var_8C]
0x180021ee7  mov     [rdx+r14*8+10h], rdi
0x180021eec  mov     rcx, [rbx+1D8h]
0x180021ef3  mov     [rcx+r14*8+18h], eax
0x180021ef8  jmp     short loc_180021F2B
0x180021efa  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f01  cmp     rcx, r12
0x180021f04  jz      short loc_180021F2B
0x180021f06  mov     eax, [rcx+2Ch]
0x180021f09  test    al, 1
0x180021f0b  jz      short loc_180021F2B
0x180021f0d  mov     rax, cs:WPP_MAIN_CB.Dpc.ProcessorHistory
0x180021f14  mov     edx, 0Dh
0x180021f19  mov     rcx, [rcx+18h]
0x180021f1d  mov     r9, [rax+r14*8+8]
0x180021f22  mov     r9, [r9+8]
0x180021f26  call    WPP_SF_S
0x180021f2b  inc     esi
0x180021f2d  cmp     esi, cs:?KsecDeferredPackageCount@@3KA; ulong KsecDeferredPackageCount
0x180021f33  jb      loc_180021E3B
0x180021f39  mov     r12d, [rbp+57h+arg_0]
0x180021f3d  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x180021f44  nop     dword ptr [rax+rax+00h]
0x180021f49  test    al, al
0x180021f4b  jz      short loc_180021F56
0x180021f4d  mov     byte ptr [rbx+1D4h], 1
0x180021f54  jmp     short loc_180021F8D
0x180021f56  mov     edi, r13d
0x180021f59  test    r12d, r12d
0x180021f5c  jz      short loc_180021F8D
0x180021f5e  mov     rax, [rbx+1C8h]
0x180021f65  mov     ecx, edi
0x180021f67  mov     rax, [rax+rcx*8]
0x180021f6b  test    rax, rax
0x180021f6e  jz      short loc_180021F86
0x180021f70  mov     rax, [rax]
0x180021f73  lea     rcx, KspKernelFunctions
0x180021f7a  call    _guard_dispatch_icall
0x180021f7f  mov     byte ptr [rbx+1D4h], 1
0x180021f86  inc     edi
0x180021f88  cmp     edi, r12d
0x180021f8b  jb      short loc_180021F5E
0x180021f8d  xor     r8d, r8d; Wait
0x180021f90  mov     [rbx+1D0h], r12d
0x180021f97  lea     rcx, WPP_MAIN_CB.Queue+38h; Event
0x180021f9e  mov     cs:?KsecConnectionIndicator@@3JA, r13d; long KsecConnectionIndicator
0x180021fa5  lea     edx, [r8+1]; Increment
0x180021fa9  call    cs:__imp_KeSetEvent
0x180021fb0  nop     dword ptr [rax+rax+00h]
0x180021fb5  lea     rcx, [rbp+57h+arg_8]; this
0x180021fb9  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180021fbe  mov     eax, r15d
0x180021fc1  jmp     short loc_180022027
0x180021fc3  mov     ebx, 80090300h
0x180021fc8  lea     rcx, [rbp+57h+arg_8]; this
0x180021fcc  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180021fd1  mov     eax, ebx
0x180021fd3  jmp     short loc_180022027
0x180021fd5  call    cs:__imp_ExReleaseFastMutex
0x180021fdc  nop     dword ptr [rax+rax+00h]
0x180021fe1  xor     r9d, r9d; Alertable
0x180021fe4  mov     [rsp+0F0h+Timeout], r13; Timeout
0x180021fe9  xor     r8d, r8d; WaitMode
0x180021fec  lea     rcx, WPP_MAIN_CB.Queue+38h; Object
0x180021ff3  lea     edx, [r9+6]; WaitReason
0x180021ff7  call    cs:__imp_KeWaitForSingleObject
0x180021ffe  nop     dword ptr [rax+rax+00h]
0x180022003  cmp     [rbx+1D4h], r13b
0x18002200a  jnz     short loc_18002201C
0x18002200c  lea     rcx, [rbp+57h+arg_8]; this
0x180022010  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180022015  mov     eax, 0C0000001h
0x18002201a  jmp     short loc_180022027
0x18002201c  lea     rcx, [rbp+57h+arg_8]; this
0x180022020  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180022025  xor     eax, eax
0x180022027  mov     rbx, [rsp+0F0h+arg_18]
0x18002202f  add     rsp, 0C0h
0x180022036  pop     r15
0x180022038  pop     r14
0x18002203a  pop     r13
0x18002203c  pop     r12
0x18002203e  pop     rdi
0x18002203f  pop     rsi
0x180022040  pop     rbp
0x180022041  retn
```
