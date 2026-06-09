# MupLocateUncProviderForPath

- ea: `0x140001cf8`
- end: `0x1400022bd`
- name: `MupLocateUncProviderForPath`
- size: `1477`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x14001bb60`
- `0x14001ea10`

## callees

- `0x140001360`
- `0x140001cf8`
- `0x1400022d0`
- `0x140002614`
- `0x140002a14`
- `0x140002a44`
- `0x140002dcc`
- `0x140002e74`
- `0x1400059c0`
- `0x1400100c8`
- `0x140010138`
- `0x1400101f8`
- `0x140010314`
- `0x140019880`
- `0x14001c760`
- `0x14001c870`
- `0x14001d364`
- `0x14001d6f4`
- `0x14001dc50`
- `0x14001e100`
- `0x14001e11c`
- `0x14001e9b8`

## import_xrefs

- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x140001f62`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x140001f62`
- `ntoskrnl!KeInitializeEvent` at `0x14000210a`
- `ntoskrnl!KeInitializeEvent` at `0x14000210a`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400020b3`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400020b3`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400020d4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140002297`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400020d4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140002297`

## pseudocode

```c
__int64 __fastcall MupLocateUncProviderForPath(
        __int64 a1,
        IRP *a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        struct _UNICODE_PREFIX_TABLE *PrefixTable)
{
  __int64 v8; // r14
  int v13; // r8d
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  PFILE_OBJECT FileObject; // r15
  int FileRequiredUncHardeningCapabilities; // edi
  int v17; // edx
  NTSTATUS RequiredHardeningCapabilitiesFromIrp; // ebx
  int v19; // r8d
  int v20; // r9d
  int v21; // esi
  __int64 v22; // rax
  __int64 v23; // rdi
  __int64 v24; // r12
  __int64 v25; // rsi
  __int64 v26; // rax
  int v27; // ecx
  int v28; // esi
  __int64 PathRequest; // rax
  int v30; // esi
  int v31; // ecx
  KIRQL Irql[4]; // [rsp+48h] [rbp-C0h] BYREF
  int v34; // [rsp+4Ch] [rbp-BCh]
  __int64 v35; // [rsp+50h] [rbp-B8h] BYREF
  PVOID P; // [rsp+58h] [rbp-B0h] BYREF
  PECP_LIST EcpList; // [rsp+60h] [rbp-A8h] BYREF
  PCUNICODE_STRING String1; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+70h] [rbp-98h]
  PIO_SECURITY_CONTEXT SecurityContext; // [rsp+78h] [rbp-90h]
  __int128 v41; // [rsp+80h] [rbp-88h] BYREF
  __int64 v42[28]; // [rsp+98h] [rbp-70h] BYREF

  v8 = 0;
  LODWORD(v35) = 0;
  P = 0;
  memset(v42, 0, 0xB0u);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  EcpList = 0;
  v41 = 0;
  Irql[1] = 0;
  FileObject = CurrentStackLocation->FileObject;
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  String1 = 0;
  v34 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_Zqq(WPP_GLOBAL_Control->AttachedDevice, 21, v13, (_DWORD)FileObject + 88, (char)FileObject, a4);
  }
  FileRequiredUncHardeningCapabilities = MupiGetFileRequiredUncHardeningCapabilities(a1);
  RequiredHardeningCapabilitiesFromIrp = MupGetRequiredHardeningCapabilitiesFromIrp(a2, (int *)&v35);
  if ( RequiredHardeningCapabilitiesFromIrp < 0 )
    goto LABEL_80;
  v20 = v35;
  v21 = v35 | FileRequiredUncHardeningCapabilities;
  v39 = 0;
  LODWORD(v35) = v35 | FileRequiredUncHardeningCapabilities;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_DDqZ(
      WPP_GLOBAL_Control->AttachedDevice,
      v17,
      v19,
      v20,
      FileRequiredUncHardeningCapabilities,
      (char)FileObject,
      (__int64)&FileObject->FileName);
  }
  v22 = MupAcquireProviderFromKnownPrefix(PrefixTable, &FileObject->FileName, (__int64)&P);
  *a3 = v22;
  if ( v22 )
  {
    if ( P )
      MupReleaseSurrogateProvider(P);
    RequiredHardeningCapabilitiesFromIrp = 0;
    if ( a7 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids);
      }
      RequiredHardeningCapabilitiesFromIrp = -1073741275;
    }
    if ( (~*(_DWORD *)(*a3 + 152) & v21) != 0 )
    {
      if ( v34 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids);
        }
        RequiredHardeningCapabilitiesFromIrp = -1073741311;
        goto LABEL_80;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids);
      }
    }
    else if ( RequiredHardeningCapabilitiesFromIrp >= 0 )
    {
      goto LABEL_80;
    }
    if ( v34 )
      v39 = *a3;
    else
      MupReleaseUncProvider(*a3);
    *a3 = 0;
  }
  FsRtlGetEcpListFromIrp(a2, &EcpList);
  MupiInitQueryContext(
    (unsigned int)v42,
    (_DWORD)a2,
    (_DWORD)FileObject,
    (_DWORD)SecurityContext,
    a5,
    a6,
    a7,
    (__int64)EcpList);
  if ( MupiCheckForProviderAvoidPath((__int64)&v42[14], &String1, 0) )
    v8 = MupAcquireUncProviderByName(String1);
  v23 = 0;
  v24 = 0;
  v34 = 0;
  Irql[2] = 0;
  RequiredHardeningCapabilitiesFromIrp = -1073741823;
  LODWORD(P) = 0;
  Irql[0] = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v25 = v23;
        if ( v39 )
        {
          v26 = 0;
          if ( v23 != v39 )
            v26 = v39;
        }
        else
        {
          v26 = MupAcquireNextUncProvider(v23, &P, (__int64)&v42[14], v42[3]);
        }
        v23 = v26;
        if ( v25 )
          MupReleaseUncProvider(v25);
        if ( !v23 )
          goto LABEL_70;
        v27 = *(_DWORD *)(v23 + 148);
        Irql[0] = 1;
        if ( ((v27 & 0x10) != 0 || !a7) && (!PrefixTable || (v27 & 0x20) != 0) )
        {
          v28 = v35;
          if ( (~*(_DWORD *)(v23 + 152) & (unsigned int)v35) == 0 )
            break;
        }
      }
      Irql[2] = 1;
      if ( v23 != v8 )
        break;
      MupReleaseUncProvider(v8);
      v8 = 0;
    }
    if ( (v27 & 8) != 0 && !v24 )
    {
      PathRequest = MupiAllocLegacyQueryPathRequest(SecurityContext, &v42[14]);
      v24 = PathRequest;
      if ( !PathRequest )
        goto LABEL_63;
      v42[21] = PathRequest;
    }
    IoAcquireCancelSpinLock(&Irql[1]);
    if ( a2->Cancel == 1 )
    {
      IoReleaseCancelSpinLock(Irql[1]);
      RequiredHardeningCapabilitiesFromIrp = -1073741536;
      MupReleaseUncProvider(v23);
      v42[4] = 0;
      goto LABEL_71;
    }
    IoReleaseCancelSpinLock(Irql[1]);
    v42[6] = v23;
    v42[4] = MupiAllocQueryIrp(v42, &v41);
    if ( !v42[4] )
    {
LABEL_63:
      RequiredHardeningCapabilitiesFromIrp = -1073741670;
      MupReleaseUncProvider(v23);
      goto LABEL_71;
    }
    KeInitializeEvent((PRKEVENT)&v42[7], SynchronizationEvent, 0);
    v30 = MupiIssueQueryRequest(v42, &v41);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids,
        (unsigned int)v30);
    }
    if ( v30 == -1073741536 || v30 == -1073741749 )
    {
      RequiredHardeningCapabilitiesFromIrp = v30;
      MupReleaseUncProvider(v23);
LABEL_70:
      v28 = v35;
LABEL_71:
      v31 = v34;
      goto LABEL_72;
    }
    if ( v30 >= 0 )
      break;
LABEL_62:
    ++dword_14000AB54;
    RequiredHardeningCapabilitiesFromIrp = MupiGetEffectiveError(
                                             (unsigned int)RequiredHardeningCapabilitiesFromIrp,
                                             (unsigned int)v30);
  }
  if ( !LODWORD(v42[10]) )
  {
    v30 = -1073741823;
    goto LABEL_62;
  }
  if ( (v42[10] & 1) != 0 )
    __int2c();
  if ( LODWORD(v42[10]) > *(unsigned __int16 *)(v42[5] + 88) )
    __int2c();
  v28 = v35;
  v31 = v42[10];
  *a3 = v23;
  RequiredHardeningCapabilitiesFromIrp = 0;
LABEL_72:
  if ( *a3 )
    MupInsertKnownPrefix((_DWORD)PrefixTable, (_DWORD)FileObject + 88, v31, *a3, (_DWORD)P, a7 != 0, a4);
  if ( v8 )
    MupReleaseUncProvider(v8);
  MupiDeInitQueryContext(v42);
  if ( v28 && Irql[0] && !Irql[2] )
    RequiredHardeningCapabilitiesFromIrp = -1073741311;
LABEL_80:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      27,
      WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids,
      FileObject,
      RequiredHardeningCapabilitiesFromIrp);
  }
  return (unsigned int)RequiredHardeningCapabilitiesFromIrp;
}

```

## disassembly

```asm
0x140001cf8  mov     rax, rsp
0x140001cfb  mov     [rax+8], rbx
0x140001cff  mov     [rax+20h], r9
0x140001d03  mov     [rax+10h], rdx
0x140001d07  push    rbp
0x140001d08  push    rsi
0x140001d09  push    rdi
0x140001d0a  push    r12
0x140001d0c  push    r13
0x140001d0e  push    r14
0x140001d10  push    r15
0x140001d12  lea     rbp, [rax-78h]
0x140001d16  sub     rsp, 140h
0x140001d1d  xor     r14d, r14d
0x140001d20  mov     r13, r8
0x140001d23  mov     r12, rdx
0x140001d26  mov     dword ptr [rsp+170h+var_128], r14d
0x140001d2b  mov     rbx, rcx
0x140001d2e  mov     [rsp+170h+P], r14
0x140001d33  xor     edx, edx; Val
0x140001d35  lea     rcx, [rbp+70h+var_E0]; void *
0x140001d39  mov     r8d, 0B0h; Size
0x140001d3f  mov     rdi, r9
0x140001d42  call    memset
0x140001d47  mov     rax, [r12+0B8h]
0x140001d4f  xorps   xmm0, xmm0
0x140001d52  mov     [rsp+170h+EcpList], r14
0x140001d57  movups  [rsp+170h+var_100+8], xmm0
0x140001d5c  mov     [rsp+170h+Irql+1], r14b
0x140001d61  mov     rcx, [rax+8]
0x140001d65  mov     r15, [rax+30h]
0x140001d69  mov     qword ptr [rsp+170h+var_100], rcx
0x140001d6e  mov     [rsp+170h+String1], r14
0x140001d73  mov     [rsp+170h+Irql], r14b
0x140001d78  mov     [rsp+170h+var_12C], r14d
0x140001d7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140001d84  lea     rax, WPP_GLOBAL_Control
0x140001d8b  cmp     rcx, rax
0x140001d8e  jz      short loc_140001DB4
0x140001d90  test    dword ptr [rcx+2Ch], 4000000h
0x140001d97  jz      short loc_140001DB4
0x140001d99  mov     rcx, [rcx+18h]
0x140001d9d  lea     r9, [r15+58h]
0x140001da1  lea     edx, [r14+15h]
0x140001da5  mov     [rsp+170h+var_148], rdi
0x140001daa  mov     [rsp+170h+var_150], r15
0x140001daf  call    WPP_SF_Zqq
0x140001db4  mov     rcx, rbx
0x140001db7  call    MupiGetFileRequiredUncHardeningCapabilities
0x140001dbc  lea     rdx, [rsp+170h+var_128]
0x140001dc1  mov     rcx, r12
0x140001dc4  mov     edi, eax
0x140001dc6  call    MupGetRequiredHardeningCapabilitiesFromIrp
0x140001dcb  mov     ebx, eax
0x140001dcd  test    eax, eax
0x140001dcf  js      loc_140002241
0x140001dd5  mov     r9d, dword ptr [rsp+170h+var_128]
0x140001dda  mov     esi, edi
0x140001ddc  or      esi, r9d
0x140001ddf  mov     [rsp+170h+var_108], r14
0x140001de4  mov     dword ptr [rsp+170h+var_128], esi
0x140001de8  mov     rcx, cs:WPP_GLOBAL_Control
0x140001def  lea     rax, WPP_GLOBAL_Control
0x140001df6  cmp     rcx, rax
0x140001df9  jz      short loc_140001E1F
0x140001dfb  test    dword ptr [rcx+2Ch], 4000000h
0x140001e02  jz      short loc_140001E1F
0x140001e04  mov     rcx, [rcx+18h]
0x140001e08  lea     rax, [r15+58h]
0x140001e0c  mov     [rsp+170h+var_140], rax
0x140001e11  mov     [rsp+170h+var_148], r15
0x140001e16  mov     dword ptr [rsp+170h+var_150], edi
0x140001e1a  call    WPP_SF_DDqZ
0x140001e1f  lea     rcx, [rsp+170h+P]
0x140001e24  mov     [rsp+170h+var_150], rcx; __int64
0x140001e29  lea     rdx, [r15+58h]; FullName
0x140001e2d  mov     rcx, [rbp+70h+PrefixTable]; PrefixTable
0x140001e34  lea     r9, [rsp+170h+var_12C]
0x140001e39  lea     r8, [rsp+170h+Irql]
0x140001e3e  call    MupAcquireProviderFromKnownPrefix
0x140001e43  mov     [r13+0], rax
0x140001e47  test    rax, rax
0x140001e4a  jz      loc_140001F5A
0x140001e50  mov     rcx, [rsp+170h+P]; P
0x140001e55  test    rcx, rcx
0x140001e58  jz      short loc_140001E5F
0x140001e5a  call    MupReleaseSurrogateProvider
0x140001e5f  mov     ebx, r14d
0x140001e62  cmp     [rbp+70h+arg_30], r14
0x140001e69  jz      short loc_140001EA8
0x140001e6b  cmp     [rsp+170h+Irql], r14b
0x140001e70  jnz     short loc_140001EA8
0x140001e72  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e79  lea     rax, WPP_GLOBAL_Control
0x140001e80  cmp     rcx, rax
0x140001e83  jz      short loc_140001EA3
0x140001e85  test    dword ptr [rcx+2Ch], 4000000h
0x140001e8c  jz      short loc_140001EA3
0x140001e8e  mov     rcx, [rcx+18h]
0x140001e92  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x140001e99  mov     edx, 17h
0x140001e9e  call    WPP_SF_
0x140001ea3  mov     ebx, 0C0000225h
0x140001ea8  mov     rax, [r13+0]
0x140001eac  mov     edi, [rsp+170h+var_12C]
0x140001eb0  mov     ecx, [rax+98h]
0x140001eb6  not     ecx
0x140001eb8  test    esi, ecx
0x140001eba  jz      short loc_140001F2E
0x140001ebc  test    edi, edi
0x140001ebe  jz      short loc_140001EFB
0x140001ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x140001ec7  lea     rax, WPP_GLOBAL_Control
0x140001ece  cmp     rcx, rax
0x140001ed1  jz      short loc_140001EF1
0x140001ed3  test    dword ptr [rcx+2Ch], 1000000h
0x140001eda  jz      short loc_140001EF1
0x140001edc  mov     rcx, [rcx+18h]
0x140001ee0  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x140001ee7  mov     edx, 18h
0x140001eec  call    WPP_SF_
0x140001ef1  mov     ebx, 0C0000201h
0x140001ef6  jmp     loc_140002241
0x140001efb  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f02  lea     rax, WPP_GLOBAL_Control
0x140001f09  cmp     rcx, rax
0x140001f0c  jz      short loc_140001F42
0x140001f0e  test    dword ptr [rcx+2Ch], 1000000h
0x140001f15  jz      short loc_140001F42
0x140001f17  mov     rcx, [rcx+18h]
0x140001f1b  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x140001f22  mov     edx, 19h
0x140001f27  call    WPP_SF_
0x140001f2c  jmp     short loc_140001F42
0x140001f2e  test    ebx, ebx
0x140001f30  jns     loc_140002241
0x140001f36  cmp     ebx, 0C0000201h
0x140001f3c  jz      loc_140002241
0x140001f42  mov     rcx, [r13+0]
0x140001f46  test    edi, edi
0x140001f48  jz      short loc_140001F51
0x140001f4a  mov     [rsp+170h+var_108], rcx
0x140001f4f  jmp     short loc_140001F56
0x140001f51  call    MupReleaseUncProvider
0x140001f56  mov     [r13+0], r14
0x140001f5a  lea     rdx, [rsp+170h+EcpList]; EcpList
0x140001f5f  mov     rcx, r12; Irp
0x140001f62  call    cs:__imp_FsRtlGetEcpListFromIrp
0x140001f69  nop     dword ptr [rax+rax+00h]
0x140001f6e  mov     rax, [rsp+170h+EcpList]
0x140001f73  lea     rcx, [rbp+70h+var_E0]
0x140001f77  mov     r9, qword ptr [rsp+170h+var_100]
0x140001f7c  mov     r8, r15
0x140001f7f  mov     qword ptr [rsp+170h+var_138], rax
0x140001f84  mov     rdx, r12
0x140001f87  mov     rax, [rbp+70h+arg_30]
0x140001f8e  mov     [rsp+170h+var_140], rax
0x140001f93  mov     eax, [rbp+70h+arg_28]
0x140001f99  mov     dword ptr [rsp+170h+var_148], eax
0x140001f9d  mov     rax, [rbp+70h+arg_20]
0x140001fa4  mov     [rsp+170h+var_150], rax
0x140001fa9  call    MupiInitQueryContext
0x140001fae  xor     r8d, r8d
0x140001fb1  lea     rdx, [rsp+170h+String1]
0x140001fb6  lea     rcx, [rbp+70h+var_70]
0x140001fba  call    MupiCheckForProviderAvoidPath
0x140001fbf  test    al, al
0x140001fc1  jz      short loc_140001FD0
0x140001fc3  mov     rcx, [rsp+170h+String1]; String1
0x140001fc8  call    MupAcquireUncProviderByName
0x140001fcd  mov     r14, rax
0x140001fd0  xor     edi, edi
0x140001fd2  xor     r12d, r12d
0x140001fd5  xor     al, al
0x140001fd7  mov     [rsp+170h+var_12C], edi
0x140001fdb  mov     [rsp+170h+Irql+2], al
0x140001fdf  mov     ebx, 0C0000001h
0x140001fe4  mov     dword ptr [rsp+170h+P], edi
0x140001fe8  mov     [rsp+170h+Irql], dil
0x140001fed  mov     rcx, [rsp+170h+var_108]
0x140001ff2  mov     rsi, rdi
0x140001ff5  test    rcx, rcx
0x140001ff8  jz      short loc_140002005
0x140001ffa  xor     eax, eax
0x140001ffc  cmp     rdi, rcx
0x140001fff  cmovnz  rax, rcx
0x140002003  jmp     short loc_14000201A
0x140002005  mov     r9, [rbp+70h+var_C8]
0x140002009  lea     r8, [rbp+70h+var_70]
0x14000200d  lea     rdx, [rsp+170h+P]
0x140002012  mov     rcx, rdi
0x140002015  call    MupAcquireNextUncProvider
0x14000201a  mov     rdi, rax
0x14000201d  test    rsi, rsi
0x140002020  jz      short loc_14000202A
0x140002022  mov     rcx, rsi
0x140002025  call    MupReleaseUncProvider
0x14000202a  test    rdi, rdi
0x14000202d  jz      loc_1400021CC
0x140002033  mov     ecx, [rdi+94h]
0x140002039  mov     [rsp+170h+Irql], 1
0x14000203e  test    cl, 10h
0x140002041  jnz     short loc_14000204D
0x140002043  cmp     [rbp+70h+arg_30], 0
0x14000204b  jnz     short loc_140001FED
0x14000204d  cmp     [rbp+70h+PrefixTable], 0
0x140002055  jz      short loc_14000205C
0x140002057  test    cl, 20h
0x14000205a  jz      short loc_140001FED
0x14000205c  mov     eax, [rdi+98h]
0x140002062  mov     esi, dword ptr [rsp+170h+var_128]
0x140002066  not     eax
0x140002068  test    esi, eax
0x14000206a  jnz     short loc_140001FED
0x14000206c  mov     [rsp+170h+Irql+2], 1
0x140002071  cmp     rdi, r14
0x140002074  jnz     short loc_140002086
0x140002076  mov     rcx, r14
0x140002079  call    MupReleaseUncProvider
0x14000207e  xor     r14d, r14d
0x140002081  jmp     loc_140001FED
0x140002086  test    cl, 8
0x140002089  jz      short loc_1400020AE
0x14000208b  test    r12, r12
0x14000208e  jnz     short loc_1400020AE
0x140002090  mov     rcx, qword ptr [rsp+170h+var_100]
0x140002095  lea     rdx, [rbp+70h+var_70]
0x140002099  call    MupiAllocLegacyQueryPathRequest
0x14000209e  mov     r12, rax
0x1400020a1  test    rax, rax
0x1400020a4  jz      loc_140002190
0x1400020aa  mov     [rbp+70h+var_38], rax
0x1400020ae  lea     rcx, [rsp+170h+Irql+1]; Irql
0x1400020b3  call    cs:__imp_IoAcquireCancelSpinLock
0x1400020ba  nop     dword ptr [rax+rax+00h]
0x1400020bf  mov     rax, [rbp+70h+arg_8]
0x1400020c6  mov     cl, [rsp+170h+Irql+1]; Irql
0x1400020ca  cmp     byte ptr [rax+44h], 1
0x1400020ce  jz      loc_140002297
0x1400020d4  call    cs:__imp_IoReleaseCancelSpinLock
0x1400020db  nop     dword ptr [rax+rax+00h]
0x1400020e0  lea     rdx, [rsp+170h+var_100+8]
0x1400020e5  mov     [rbp+70h+var_B0], rdi
0x1400020e9  lea     rcx, [rbp+70h+var_E0]
0x1400020ed  call    MupiAllocQueryIrp
0x1400020f2  mov     [rbp+70h+var_C0], rax
0x1400020f6  test    rax, rax
0x1400020f9  jz      loc_140002190
0x1400020ff  xor     r8d, r8d; State
0x140002102  lea     rcx, [rbp+70h+Event]; Event
0x140002106  lea     edx, [r8+1]; Type
0x14000210a  call    cs:__imp_KeInitializeEvent
0x140002111  nop     dword ptr [rax+rax+00h]
0x140002116  lea     rdx, [rsp+170h+var_100+8]
0x14000211b  lea     rcx, [rbp+70h+var_E0]
0x14000211f  call    MupiIssueQueryRequest
0x140002124  mov     esi, eax
0x140002126  mov     rcx, cs:WPP_GLOBAL_Control
0x14000212d  lea     rax, WPP_GLOBAL_Control
0x140002134  cmp     rcx, rax
0x140002137  jz      short loc_14000215A
0x140002139  test    dword ptr [rcx+2Ch], 4000000h
0x140002140  jz      short loc_14000215A
0x140002142  mov     rcx, [rcx+18h]
0x140002146  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14000214d  mov     edx, 1Ah
0x140002152  mov     r9d, esi
0x140002155  call    WPP_SF_d
0x14000215a  cmp     esi, 0C0000120h
0x140002160  jz      short loc_1400021C2
0x140002162  cmp     esi, 0C000004Bh
0x140002168  jz      short loc_1400021C2
0x14000216a  test    esi, esi
0x14000216c  js      short loc_14000217A
0x14000216e  mov     edx, [rbp+70h+var_90]
0x140002171  test    edx, edx
0x140002173  jnz     short loc_14000219F
0x140002175  mov     esi, 0C0000001h
0x14000217a  inc     cs:dword_14000AB54
0x140002180  mov     edx, esi
0x140002182  mov     ecx, ebx
0x140002184  call    MupiGetEffectiveError
0x140002189  mov     ebx, eax
0x14000218b  jmp     loc_140001FED
0x140002190  mov     rcx, rdi
0x140002193  mov     ebx, 0C000009Ah
0x140002198  call    MupReleaseUncProvider
0x14000219d  jmp     short loc_1400021D0
0x14000219f  test    dl, 1
0x1400021a2  jz      short loc_1400021A6
0x1400021a4  int     2Ch; Windows NT - assertion failure
0x1400021a6  mov     rax, [rbp+70h+var_B8]
0x1400021aa  movzx   ecx, word ptr [rax+58h]
0x1400021ae  cmp     edx, ecx
0x1400021b0  jbe     short loc_1400021B4
0x1400021b2  int     2Ch; Windows NT - assertion failure
0x1400021b4  mov     esi, dword ptr [rsp+170h+var_128]
0x1400021b8  mov     ecx, edx
0x1400021ba  mov     [r13+0], rdi
0x1400021be  xor     ebx, ebx
  ... truncated ...
```
