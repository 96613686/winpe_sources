# InitializePackages

- ea: `0x180021b18`
- end: `0x180021ff3`
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
- `0x180010920`
- `0x180010c80`
- `0x180020b14`
- `0x180020ccc`
- `0x180021b18`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x180021eed`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x180021eed`
- `ntoskrnl!KeWaitForSingleObject` at `0x180021fa7`
- `ntoskrnl!KeWaitForSingleObject` at `0x180021fa7`
- `ntoskrnl!ExAcquireFastMutex` at `0x180021b96`
- `ntoskrnl!ExAcquireFastMutex` at `0x180021b96`
- `ntoskrnl!ExReleaseFastMutex` at `0x180021bae`
- `ntoskrnl!ExReleaseFastMutex` at `0x180021bd9`
- `ntoskrnl!ExReleaseFastMutex` at `0x180021f85`
- `ntoskrnl!ExReleaseFastMutex` at `0x180021bae`
- `ntoskrnl!ExReleaseFastMutex` at `0x180021bd9`
- `ntoskrnl!ExReleaseFastMutex` at `0x180021f85`
- `ntoskrnl!KeSetEvent` at `0x180021f59`
- `ntoskrnl!KeSetEvent` at `0x180021f59`
- `ntoskrnl!ExAllocatePool2` at `0x180021c01`
- `ntoskrnl!ExAllocatePool2` at `0x180021c2a`
- `ntoskrnl!ExAllocatePool2` at `0x180021c01`
- `ntoskrnl!ExAllocatePool2` at `0x180021c2a`
- `ntoskrnl!RtlInitUnicodeString` at `0x180021c77`
- `ntoskrnl!RtlInitUnicodeString` at `0x180021c77`

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
  PKDEFERRED_ROUTINE DeferredRoutine; // rdx
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
  ExAcquireFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
  if ( *(_BYTE *)(v3 + 468) )
  {
    ExReleaseFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
    v2 = 0;
    goto LABEL_51;
  }
  if ( KsecConnectionIndicator )
  {
    ExReleaseFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
    KeWaitForSingleObject(&WPP_MAIN_CB.Queue, UserRequest, 0, 0, 0);
    if ( !*(_BYTE *)(v3 + 468) )
    {
      KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v24);
      return 3221225473LL;
    }
    goto LABEL_54;
  }
  KsecConnectionIndicator = 1;
  ExReleaseFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
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
      Package = SecpFindPackage(*((_QWORD *)WPP_MAIN_CB.Dpc.DeferredRoutine + 5 * v14 + 1), &v25);
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
            *(_QWORD *)(*((_QWORD *)WPP_MAIN_CB.Dpc.DeferredRoutine + 5 * v14 + 1) + 8LL));
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
          WPP_SF_SI(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            12,
            v15,
            *(_QWORD *)(*((_QWORD *)WPP_MAIN_CB.Dpc.DeferredRoutine + 5 * v14 + 1) + 8LL),
            v16);
        DeferredRoutine = WPP_MAIN_CB.Dpc.DeferredRoutine;
        *(_QWORD *)(*(_QWORD *)(v3 + 456) + 8 * v16) = *((_QWORD *)WPP_MAIN_CB.Dpc.DeferredRoutine + 5 * v14);
        v18 = HIDWORD(v22[6]);
        *((_QWORD *)DeferredRoutine + 5 * v14 + 2) = v16;
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
  KeSetEvent((PRKEVENT)&WPP_MAIN_CB.Queue, 1, 0);
  KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v24);
  return (unsigned int)Package;
}

```

## disassembly

```asm
0x180021b18  mov     [rsp-8+arg_18], rbx
0x180021b1d  mov     [rsp-8+arg_0], ecx
0x180021b21  push    rbp
0x180021b22  push    rsi
0x180021b23  push    rdi
0x180021b24  push    r12
0x180021b26  push    r13
0x180021b28  push    r14
0x180021b2a  push    r15
0x180021b2c  lea     rbp, [rsp-27h]
0x180021b31  sub     rsp, 0C0h
0x180021b38  mov     r12d, ecx
0x180021b3b  xor     r13d, r13d
0x180021b3e  lea     rcx, [rbp+57h+var_BE]; void *
0x180021b42  mov     [rbp+57h+arg_10], r13
0x180021b46  xor     edx, edx; Val
0x180021b48  mov     r8d, 8Eh; Size
0x180021b4e  call    memset
0x180021b53  lea     rcx, [rbp+57h+arg_8]; this
0x180021b57  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180021b5c  lea     rcx, [rbp+57h+arg_8]; this
0x180021b60  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180021b65  test    al, al
0x180021b67  jnz     short loc_180021B73
0x180021b69  mov     ebx, 0C00002FEh
0x180021b6e  jmp     loc_180021F78
0x180021b73  lea     rcx, [rbp+57h+arg_8]
0x180021b77  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180021b7c  mov     rbx, rax
0x180021b7f  cmp     [rax+1D4h], r13b
0x180021b86  jnz     loc_180021FCC
0x180021b8c  lea     rdi, WPP_MAIN_CB.Queue+18h
0x180021b93  mov     rcx, rdi; FastMutex
0x180021b96  call    cs:__imp_ExAcquireFastMutex
0x180021b9d  nop     dword ptr [rax+rax+00h]
0x180021ba2  mov     rcx, rdi; FastMutex
0x180021ba5  cmp     [rbx+1D4h], r13b
0x180021bac  jz      short loc_180021BC2
0x180021bae  call    cs:__imp_ExReleaseFastMutex
0x180021bb5  nop     dword ptr [rax+rax+00h]
0x180021bba  mov     ebx, r13d
0x180021bbd  jmp     loc_180021F78
0x180021bc2  cmp     cs:?KsecConnectionIndicator@@3JA, r13d; long KsecConnectionIndicator
0x180021bc9  jnz     loc_180021F85
0x180021bcf  mov     cs:?KsecConnectionIndicator@@3JA, 1; long KsecConnectionIndicator
0x180021bd9  call    cs:__imp_ExReleaseFastMutex
0x180021be0  nop     dword ptr [rax+rax+00h]
0x180021be5  mov     esi, 6365734Bh
0x180021bea  lea     rdx, ds:0[r12*8]
0x180021bf2  mov     r14d, 40h ; '@'
0x180021bf8  mov     r8d, esi
0x180021bfb  mov     ecx, r14d
0x180021bfe  mov     rdi, r12
0x180021c01  call    cs:__imp_ExAllocatePool2
0x180021c08  nop     dword ptr [rax+rax+00h]
0x180021c0d  mov     [rbx+1C8h], rax
0x180021c14  test    rax, rax
0x180021c17  jz      loc_180021F73
0x180021c1d  shl     rdi, 4
0x180021c21  mov     r8d, esi
0x180021c24  mov     rdx, rdi
0x180021c27  mov     ecx, r14d
0x180021c2a  call    cs:__imp_ExAllocatePool2
0x180021c31  nop     dword ptr [rax+rax+00h]
0x180021c36  mov     [rbx+210h], rax
0x180021c3d  test    rax, rax
0x180021c40  jz      loc_180021F73
0x180021c46  mov     r15d, r13d
0x180021c49  mov     r14d, r13d
0x180021c4c  cmp     [rbx+1E0h], r13d
0x180021c53  jbe     loc_180021DD3
0x180021c59  lea     r12, WPP_GLOBAL_Control
0x180021c60  mov     eax, r14d
0x180021c63  lea     rsi, [rax+rax*4]
0x180021c67  mov     rax, [rbx+1D8h]
0x180021c6e  mov     rcx, [rax+rsi*8+8]; DestinationString
0x180021c73  mov     rdx, [rcx+8]; SourceString
0x180021c77  call    cs:__imp_RtlInitUnicodeString
0x180021c7e  nop     dword ptr [rax+rax+00h]
0x180021c83  mov     rcx, [rbx+1D8h]
0x180021c8a  lea     rdx, [rbp+57h+arg_10]
0x180021c8e  mov     rcx, [rcx+rsi*8+8]
0x180021c93  call    SecpFindPackage
0x180021c98  mov     r15d, eax
0x180021c9b  test    eax, eax
0x180021c9d  js      loc_180021D8E
0x180021ca3  mov     rdi, [rbp+57h+arg_10]
0x180021ca7  lea     rdx, [rbp+57h+var_C0]
0x180021cab  mov     rcx, rdi
0x180021cae  call    SecpGetBinding
0x180021cb3  mov     rcx, [rbp+57h+var_B8]
0x180021cb7  mov     r15d, eax
0x180021cba  test    rcx, rcx
0x180021cbd  jz      short loc_180021CC8
0x180021cbf  call    SecFreeForKsecCaller
0x180021cc4  mov     [rbp+57h+var_B8], r13
0x180021cc8  test    r15d, r15d
0x180021ccb  js      loc_180021D8E
0x180021cd1  mov     rax, [rbx+1C8h]
0x180021cd8  cmp     [rax+rdi*8], r13
0x180021cdc  jnz     loc_180021D8E
0x180021ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ce9  cmp     rcx, r12
0x180021cec  jz      short loc_180021D18
0x180021cee  mov     eax, [rcx+2Ch]
0x180021cf1  test    al, 4
0x180021cf3  jz      short loc_180021D18
0x180021cf5  mov     rax, [rbx+1D8h]
0x180021cfc  mov     edx, 0Ah
0x180021d01  mov     rcx, [rcx+18h]
0x180021d05  mov     [rsp+0F0h+Timeout], rdi
0x180021d0a  mov     r9, [rax+rsi*8+8]
0x180021d0f  mov     r9, [r9+8]
0x180021d13  call    WPP_SF_SI
0x180021d18  mov     rax, [rbx+1D8h]
0x180021d1f  mov     rcx, [rbx+1C8h]
0x180021d26  mov     rax, [rax+rsi*8]
0x180021d2a  mov     [rcx+rdi*8], rax
0x180021d2e  mov     rax, [rbx+1D8h]
0x180021d35  mov     rcx, [rax+rsi*8+20h]
0x180021d3a  test    rcx, rcx
0x180021d3d  jz      short loc_180021D54
0x180021d3f  movups  xmm0, xmmword ptr [rcx]
0x180021d42  mov     rax, [rbx+210h]
0x180021d49  mov     rcx, rdi
0x180021d4c  add     rcx, rcx
0x180021d4f  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x180021d54  mov     rax, [rbx+1D8h]
0x180021d5b  mov     ecx, [rbp+57h+var_8C]
0x180021d5e  mov     [rax+rsi*8+10h], rdi
0x180021d63  mov     rax, [rbx+1D8h]
0x180021d6a  mov     [rax+rsi*8+18h], ecx
0x180021d6e  bt      ecx, 14h
0x180021d72  jnb     short loc_180021DBF
0x180021d74  mov     rax, [rbx+1C8h]
0x180021d7b  mov     cs:KsecddGlobalExtenderPackageId, edi
0x180021d81  mov     rcx, [rax+rdi*8]
0x180021d85  mov     cs:KsecddGlobalExtenderPackage, rcx
0x180021d8c  jmp     short loc_180021DBF
0x180021d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d95  cmp     rcx, r12
0x180021d98  jz      short loc_180021DBF
0x180021d9a  mov     eax, [rcx+2Ch]
0x180021d9d  test    al, 1
0x180021d9f  jz      short loc_180021DBF
0x180021da1  mov     rax, [rbx+1D8h]
0x180021da8  mov     edx, 0Bh
0x180021dad  mov     rcx, [rcx+18h]
0x180021db1  mov     r9, [rax+rsi*8+8]
0x180021db6  mov     r9, [r9+8]
0x180021dba  call    WPP_SF_S
0x180021dbf  inc     r14d
0x180021dc2  cmp     r14d, [rbx+1E0h]
0x180021dc9  jb      loc_180021C60
0x180021dcf  mov     r12d, [rbp+57h+arg_0]
0x180021dd3  mov     eax, cs:?KsecDeferredPackageCount@@3KA; ulong KsecDeferredPackageCount
0x180021dd9  test    eax, eax
0x180021ddb  jz      loc_180021EED
0x180021de1  mov     esi, r13d
0x180021de4  lea     r12, WPP_GLOBAL_Control
0x180021deb  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x180021df2  lea     rdx, [rbp+57h+arg_10]
0x180021df6  mov     eax, esi
0x180021df8  lea     r14, [rax+rax*4]
0x180021dfc  mov     rcx, [rcx+r14*8+8]
0x180021e01  call    SecpFindPackage
0x180021e06  mov     r15d, eax
0x180021e09  test    eax, eax
0x180021e0b  js      loc_180021EAA
0x180021e11  mov     rdi, [rbp+57h+arg_10]
0x180021e15  lea     rdx, [rbp+57h+var_C0]
0x180021e19  mov     rcx, rdi
0x180021e1c  call    SecpGetBinding
0x180021e21  mov     rcx, [rbp+57h+var_B8]
0x180021e25  mov     r15d, eax
0x180021e28  test    rcx, rcx
0x180021e2b  jz      short loc_180021E36
0x180021e2d  call    SecFreeForKsecCaller
0x180021e32  mov     [rbp+57h+var_B8], r13
0x180021e36  test    r15d, r15d
0x180021e39  js      short loc_180021EAA
0x180021e3b  mov     rax, [rbx+1C8h]
0x180021e42  cmp     [rax+rdi*8], r13
0x180021e46  jnz     short loc_180021EAA
0x180021e48  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e4f  cmp     rcx, r12
0x180021e52  jz      short loc_180021E7E
0x180021e54  mov     eax, [rcx+2Ch]
0x180021e57  test    al, 4
0x180021e59  jz      short loc_180021E7E
0x180021e5b  mov     rax, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x180021e62  mov     edx, 0Ch
0x180021e67  mov     rcx, [rcx+18h]
0x180021e6b  mov     [rsp+0F0h+Timeout], rdi
0x180021e70  mov     r9, [rax+r14*8+8]
0x180021e75  mov     r9, [r9+8]
0x180021e79  call    WPP_SF_SI
0x180021e7e  mov     rcx, [rbx+1C8h]
0x180021e85  mov     rdx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x180021e8c  mov     rax, [rdx+r14*8]
0x180021e90  mov     [rcx+rdi*8], rax
0x180021e94  mov     eax, [rbp+57h+var_8C]
0x180021e97  mov     [rdx+r14*8+10h], rdi
0x180021e9c  mov     rcx, [rbx+1D8h]
0x180021ea3  mov     [rcx+r14*8+18h], eax
0x180021ea8  jmp     short loc_180021EDB
0x180021eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180021eb1  cmp     rcx, r12
0x180021eb4  jz      short loc_180021EDB
0x180021eb6  mov     eax, [rcx+2Ch]
0x180021eb9  test    al, 1
0x180021ebb  jz      short loc_180021EDB
0x180021ebd  mov     rax, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x180021ec4  mov     edx, 0Dh
0x180021ec9  mov     rcx, [rcx+18h]
0x180021ecd  mov     r9, [rax+r14*8+8]
0x180021ed2  mov     r9, [r9+8]
0x180021ed6  call    WPP_SF_S
0x180021edb  inc     esi
0x180021edd  cmp     esi, cs:?KsecDeferredPackageCount@@3KA; ulong KsecDeferredPackageCount
0x180021ee3  jb      loc_180021DEB
0x180021ee9  mov     r12d, [rbp+57h+arg_0]
0x180021eed  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x180021ef4  nop     dword ptr [rax+rax+00h]
0x180021ef9  test    al, al
0x180021efb  jz      short loc_180021F06
0x180021efd  mov     byte ptr [rbx+1D4h], 1
0x180021f04  jmp     short loc_180021F3D
0x180021f06  mov     edi, r13d
0x180021f09  test    r12d, r12d
0x180021f0c  jz      short loc_180021F3D
0x180021f0e  mov     rax, [rbx+1C8h]
0x180021f15  mov     ecx, edi
0x180021f17  mov     rax, [rax+rcx*8]
0x180021f1b  test    rax, rax
0x180021f1e  jz      short loc_180021F36
0x180021f20  mov     rax, [rax]
0x180021f23  lea     rcx, KspKernelFunctions
0x180021f2a  call    _guard_dispatch_icall
0x180021f2f  mov     byte ptr [rbx+1D4h], 1
0x180021f36  inc     edi
0x180021f38  cmp     edi, r12d
0x180021f3b  jb      short loc_180021F0E
0x180021f3d  xor     r8d, r8d; Wait
0x180021f40  mov     [rbx+1D0h], r12d
0x180021f47  lea     rcx, WPP_MAIN_CB.Queue; Event
0x180021f4e  mov     cs:?KsecConnectionIndicator@@3JA, r13d; long KsecConnectionIndicator
0x180021f55  lea     edx, [r8+1]; Increment
0x180021f59  call    cs:__imp_KeSetEvent
0x180021f60  nop     dword ptr [rax+rax+00h]
0x180021f65  lea     rcx, [rbp+57h+arg_8]; this
0x180021f69  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180021f6e  mov     eax, r15d
0x180021f71  jmp     short loc_180021FD7
0x180021f73  mov     ebx, 80090300h
0x180021f78  lea     rcx, [rbp+57h+arg_8]; this
0x180021f7c  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180021f81  mov     eax, ebx
0x180021f83  jmp     short loc_180021FD7
0x180021f85  call    cs:__imp_ExReleaseFastMutex
0x180021f8c  nop     dword ptr [rax+rax+00h]
0x180021f91  xor     r9d, r9d; Alertable
0x180021f94  mov     [rsp+0F0h+Timeout], r13; Timeout
0x180021f99  xor     r8d, r8d; WaitMode
0x180021f9c  lea     rcx, WPP_MAIN_CB.Queue; Object
0x180021fa3  lea     edx, [r9+6]; WaitReason
0x180021fa7  call    cs:__imp_KeWaitForSingleObject
0x180021fae  nop     dword ptr [rax+rax+00h]
0x180021fb3  cmp     [rbx+1D4h], r13b
0x180021fba  jnz     short loc_180021FCC
0x180021fbc  lea     rcx, [rbp+57h+arg_8]; this
0x180021fc0  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180021fc5  mov     eax, 0C0000001h
0x180021fca  jmp     short loc_180021FD7
0x180021fcc  lea     rcx, [rbp+57h+arg_8]; this
0x180021fd0  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180021fd5  xor     eax, eax
0x180021fd7  mov     rbx, [rsp+0F0h+arg_18]
0x180021fdf  add     rsp, 0C0h
0x180021fe6  pop     r15
0x180021fe8  pop     r14
0x180021fea  pop     r13
0x180021fec  pop     r12
0x180021fee  pop     rdi
0x180021fef  pop     rsi
0x180021ff0  pop     rbp
0x180021ff1  retn
```
