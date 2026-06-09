# PrjfGetSetStreamContext

- ea: `0x1400217a4`
- end: `0x140021c55`
- name: `PrjfGetSetStreamContext`
- size: `1201`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, PFLT_CONTEXT Context@<r8>, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140002f3c`

## callees

- `0x1400020b4`
- `0x140003480`
- `0x140003e6c`
- `0x14000b1d0`
- `0x14000ba20`
- `0x14000d008`
- `0x14000d128`
- `0x14000dab0`
- `0x1400217a4`

## import_xrefs

- `ntoskrnl!FsRtlReleaseFile` at `0x140021bbf`
- `ntoskrnl!FsRtlReleaseFile` at `0x140021bbf`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140021b9d`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140021b9d`
- `ntoskrnl!FsRtlAcquireFileExclusive` at `0x140021b7c`
- `ntoskrnl!FsRtlAcquireFileExclusive` at `0x140021b7c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140021b6a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140021bb0`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140021b6a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140021bb0`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140021b56`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140021b56`
- `FLTMGR!FltSetStreamContext` at `0x140021a8a`
- `FLTMGR!FltSetStreamContext` at `0x140021a8a`
- `FLTMGR!FltQueryInformationFile` at `0x140021920`
- `FLTMGR!FltQueryInformationFile` at `0x140021920`
- `FLTMGR!FltDeleteContext` at `0x1400218db`
- `FLTMGR!FltDeleteContext` at `0x1400218db`
- `FLTMGR!FltGetStreamContext` at `0x140021896`
- `FLTMGR!FltGetStreamContext` at `0x140021896`
- `FLTMGR!FltDeleteStreamContext` at `0x140021c19`
- `FLTMGR!FltDeleteStreamContext` at `0x140021c19`
- `FLTMGR!FltReleaseContext` at `0x1400218eb`
- `FLTMGR!FltReleaseContext` at `0x1400219ba`
- `FLTMGR!FltReleaseContext` at `0x140021aa4`
- `FLTMGR!FltReleaseContext` at `0x1400218eb`
- `FLTMGR!FltReleaseContext` at `0x1400219ba`
- `FLTMGR!FltReleaseContext` at `0x140021aa4`

## pseudocode

```c
__int64 __fastcall PrjfGetSetStreamContext(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        _OWORD *Context,
        char *a4,
        _QWORD *a5)
{
  char v9; // si
  int v10; // edx
  __int64 UnionContext; // rdi
  int v12; // r8d
  NTSTATUS StreamContext; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  PFLT_CONTEXT v16; // rdx
  NTSTATUS Status; // ebx
  NTSTATUS v18; // eax
  _QWORD *v19; // r15
  PFLT_CONTEXT v20; // rcx
  int v21; // eax
  int v22; // edx
  char v23; // r15
  PFLT_CONTEXT Contexta; // [rsp+60h] [rbp-51h] BYREF
  _QWORD *v26; // [rsp+68h] [rbp-49h]
  PFLT_CONTEXT OldContext; // [rsp+70h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+78h] [rbp-39h] BYREF
  __int128 v29; // [rsp+90h] [rbp-21h] BYREF
  __int128 FileInformation; // [rsp+A0h] [rbp-11h] BYREF
  __int64 v31; // [rsp+B0h] [rbp-1h]

  v26 = a5;
  Contexta = 0;
  OldContext = 0;
  *a5 = 0;
  IoStatus = 0;
  v31 = 0;
  v29 = Context[6];
  v9 = 0;
  FileInformation = 0;
  UnionContext = PrjfGetUnionContext(Instance, &v29);
  if ( !UnionContext
    && ((BYTE1(xmmword_14001A3E0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
  {
    LOBYTE(v10) = BYTE1(xmmword_14001A3E0) & 2;
    LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(
      1033,
      v10,
      v12,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      4,
      9,
      26,
      (__int64)&WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
      30);
  }
  StreamContext = FltGetStreamContext(Instance, FileObject, &Contexta);
  v16 = Contexta;
  Status = StreamContext;
  if ( StreamContext == -1073741275 )
  {
    if ( !UnionContext )
      goto LABEL_13;
  }
  else if ( !UnionContext || *(_DWORD *)(UnionContext + 60) == *((_DWORD *)Contexta + 1) )
  {
    goto LABEL_42;
  }
  if ( Contexta && *(_DWORD *)(UnionContext + 60) != *((_DWORD *)Contexta + 1) )
  {
    FltDeleteContext(Contexta);
    FltReleaseContext(Contexta);
    Contexta = 0;
  }
LABEL_13:
  v18 = FltQueryInformationFile(Instance, FileObject, &FileInformation, 0x18u, FileStandardInformation, 0);
  if ( v18 < 0 )
  {
    LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v16) = BYTE1(xmmword_14001A3D0) & 2;
    if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_sDqd(
        521,
        (_DWORD)v16,
        v14,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        9,
        27,
        (__int64)&WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
        64,
        (char)FileObject,
        v18);
    Status = -1073741790;
    goto LABEL_18;
  }
  v21 = PrjfCreateStreamContext(Context);
  Status = v21;
  if ( v21 < 0 )
  {
    LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v16) = BYTE1(xmmword_14001A3D0) & 2;
    if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_sDL(
        521,
        (_DWORD)v16,
        v14,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        9,
        28,
        (__int64)&WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
        79,
        v21);
    goto LABEL_18;
  }
  v9 = 1;
  Status = FltSetStreamContext(Instance, FileObject, FLT_SET_CONTEXT_KEEP_IF_EXISTS, Contexta, &OldContext);
  if ( Status >= 0 )
  {
    v16 = Contexta;
    if ( !*(_DWORD *)Contexta )
    {
      v23 = 0;
      if ( !IoGetTopLevelIrp() )
      {
        IoSetTopLevelIrp((PIRP)1);
        v23 = 1;
      }
      FsRtlAcquireFileExclusive(FileObject);
      CcCoherencyFlushAndPurgeCache(FileObject->SectionObjectPointer, 0, 0, &IoStatus, 0);
      if ( v23 )
        IoSetTopLevelIrp(0);
      FsRtlReleaseFile(FileObject);
      if ( IoStatus.Status < 0 )
      {
        Status = IoStatus.Status;
LABEL_18:
        v19 = v26;
LABEL_19:
        v20 = Contexta;
        if ( Contexta )
          FltReleaseContext(Contexta);
        if ( Status < 0 )
        {
          if ( v9 )
          {
            if ( a4 && *a4 )
              MicrosoftTelemetryAssertTriggeredNoArgsKM(v20, v16, v14, v15);
            FltDeleteStreamContext(Instance, FileObject, 0);
          }
        }
        else if ( !*v19 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v20, v16, v14, v15);
        }
        if ( UnionContext )
          PrjfReleaseUnionContext((char *)UnionContext, (__int64)v16, v14, v15);
        return (unsigned int)Status;
      }
      v16 = Contexta;
    }
LABEL_42:
    if ( a4 )
      *a4 = v9;
    v19 = v26;
    Contexta = 0;
    *v26 = v16;
    goto LABEL_19;
  }
  FltReleaseContext(Contexta);
  Contexta = 0;
  if ( Status == -1071906814 )
  {
    v16 = OldContext;
    v9 = 0;
    Status = 0;
    goto LABEL_42;
  }
  if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v22) = BYTE1(xmmword_14001A3D0) & 2;
    LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      521,
      v22,
      v14,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      9,
      29,
      (__int64)&WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
      103,
      Status);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400217a4  push    rbp
0x1400217a6  push    rbx
0x1400217a7  push    rsi
0x1400217a8  push    rdi
0x1400217a9  push    r12
0x1400217ab  push    r13
0x1400217ad  push    r14
0x1400217af  push    r15
0x1400217b1  lea     rbp, [rsp-17h]
0x1400217b6  sub     rsp, 0C8h
0x1400217bd  mov     rax, cs:__security_cookie
0x1400217c4  xor     rax, rsp
0x1400217c7  mov     [rbp+4Fh+var_48], rax
0x1400217cb  mov     rax, [rbp+4Fh+arg_20]
0x1400217cf  xor     ebx, ebx
0x1400217d1  xorps   xmm0, xmm0
0x1400217d4  mov     [rbp+4Fh+var_98], rax
0x1400217d8  mov     r13, rcx
0x1400217db  mov     [rbp+4Fh+Context], rbx
0x1400217df  xor     ecx, ecx
0x1400217e1  mov     [rbp+4Fh+OldContext], rbx
0x1400217e5  mov     [rax], rbx
0x1400217e8  mov     r14, rdx
0x1400217eb  movups  xmmword ptr [rbp+4Fh+IoStatus], xmm0
0x1400217ef  mov     [rbp+4Fh+var_50], rcx
0x1400217f3  lea     rdx, [rbp+4Fh+var_70]
0x1400217f7  movups  xmm0, xmmword ptr [r8+60h]
0x1400217fc  mov     rcx, r13
0x1400217ff  mov     r12, r9
0x140021802  xorps   xmm1, xmm1
0x140021805  mov     r15, r8
0x140021808  movdqu  [rbp+4Fh+var_70], xmm0
0x14002180d  mov     sil, bl
0x140021810  movups  [rbp+4Fh+FileInformation], xmm1
0x140021814  call    PrjfGetUnionContext
0x140021819  mov     rdi, rax
0x14002181c  lea     r9, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140021823  lea     rax, WPP_RECORDER_INITIALIZED
0x14002182a  lea     r10, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140021831  test    rdi, rdi
0x140021834  jnz     short loc_14002188C
0x140021836  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002183d  mov     dl, byte ptr cs:xmmword_14001A3E0+1
0x140021843  setnz   r8b
0x140021847  and     dl, 2
0x14002184a  jnz     short loc_140021851
0x14002184c  test    r8b, r8b
0x14002184f  jz      short loc_14002188C
0x140021851  mov     [rsp+100h+var_B8], 51Eh
0x140021859  mov     ecx, 409h
0x14002185e  mov     [rsp+100h+var_C0], r9
0x140021863  mov     r9, cs:WPP_GLOBAL_Control
0x14002186a  mov     [rsp+100h+var_C8], r10
0x14002186f  mov     [rsp+100h+var_D0], 1Ah
0x140021876  mov     dword ptr [rsp+100h+LengthReturned], 9
0x14002187e  mov     r9, [r9+40h]
0x140021882  mov     byte ptr [rsp+100h+FileInformationClass], 4
0x140021887  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14002188c  lea     r8, [rbp+4Fh+Context]; Context
0x140021890  mov     rdx, r14; FileObject
0x140021893  mov     rcx, r13; Instance
0x140021896  call    cs:__imp_FltGetStreamContext
0x14002189d  nop     dword ptr [rax+rax+00h]
0x1400218a2  mov     rdx, [rbp+4Fh+Context]
0x1400218a6  mov     ebx, eax
0x1400218a8  cmp     eax, 0C0000225h
0x1400218ad  jz      short loc_1400218C6
0x1400218af  test    rdi, rdi
0x1400218b2  jz      loc_140021BDD
0x1400218b8  mov     ecx, [rdx+4]
0x1400218bb  cmp     [rdi+3Ch], ecx
0x1400218be  jz      loc_140021BDD
0x1400218c4  jmp     short loc_1400218CB
0x1400218c6  test    rdi, rdi
0x1400218c9  jz      short loc_1400218FF
0x1400218cb  test    rdx, rdx
0x1400218ce  jz      short loc_1400218FF
0x1400218d0  mov     eax, [rdx+4]
0x1400218d3  cmp     [rdi+3Ch], eax
0x1400218d6  jz      short loc_1400218FF
0x1400218d8  mov     rcx, rdx; Context
0x1400218db  call    cs:__imp_FltDeleteContext
0x1400218e2  nop     dword ptr [rax+rax+00h]
0x1400218e7  mov     rcx, [rbp+4Fh+Context]; Context
0x1400218eb  call    cs:__imp_FltReleaseContext
0x1400218f2  nop     dword ptr [rax+rax+00h]
0x1400218f7  mov     [rbp+4Fh+Context], 0
0x1400218ff  mov     [rsp+100h+LengthReturned], 0; LengthReturned
0x140021908  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x14002190c  mov     r9d, 18h; Length
0x140021912  mov     [rsp+100h+FileInformationClass], 5; FileInformationClass
0x14002191a  mov     rdx, r14; FileObject
0x14002191d  mov     rcx, r13; Instance
0x140021920  call    cs:__imp_FltQueryInformationFile
0x140021927  nop     dword ptr [rax+rax+00h]
0x14002192c  test    eax, eax
0x14002192e  jns     loc_1400219E2
0x140021934  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002193a  lea     rcx, WPP_RECORDER_INITIALIZED
0x140021941  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140021948  setnz   r8b
0x14002194c  and     dl, 2
0x14002194f  jnz     short loc_140021956
0x140021951  test    r8b, r8b
0x140021954  jz      short loc_1400219A8
0x140021956  mov     r9, cs:WPP_GLOBAL_Control
0x14002195d  lea     r10, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140021964  mov     [rsp+100h+var_A8], eax
0x140021968  mov     ecx, 209h
0x14002196d  mov     [rsp+100h+var_B0], r14
0x140021972  mov     [rsp+100h+var_B8], 540h
0x14002197a  mov     r9, [r9+40h]
0x14002197e  mov     [rsp+100h+var_C0], r10
0x140021983  lea     r10, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x14002198a  mov     [rsp+100h+var_C8], r10
0x14002198f  mov     [rsp+100h+var_D0], 1Bh
0x140021996  mov     dword ptr [rsp+100h+LengthReturned], 9
0x14002199e  mov     byte ptr [rsp+100h+FileInformationClass], 2
0x1400219a3  call    WPP_RECORDER_AND_TRACE_SF_sDqd
0x1400219a8  mov     ebx, 0C0000022h
0x1400219ad  mov     r15, [rbp+4Fh+var_98]
0x1400219b1  mov     rcx, [rbp+4Fh+Context]; Context
0x1400219b5  test    rcx, rcx
0x1400219b8  jz      short loc_1400219C6
0x1400219ba  call    cs:__imp_FltReleaseContext
0x1400219c1  nop     dword ptr [rax+rax+00h]
0x1400219c6  test    ebx, ebx
0x1400219c8  js      loc_140021BFA
0x1400219ce  cmp     qword ptr [r15], 0
0x1400219d2  jnz     loc_140021C25
0x1400219d8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400219dd  jmp     loc_140021C25
0x1400219e2  lea     r9, [rbp+4Fh+Context]
0x1400219e6  mov     r8, rdi
0x1400219e9  lea     rdx, [rbp+4Fh+FileInformation]
0x1400219ed  mov     rcx, r15; Context
0x1400219f0  call    PrjfCreateStreamContext
0x1400219f5  mov     ebx, eax
0x1400219f7  test    eax, eax
0x1400219f9  jns     short loc_140021A6F
0x1400219fb  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140021a01  lea     rcx, WPP_RECORDER_INITIALIZED
0x140021a08  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140021a0f  setnz   r8b
0x140021a13  and     dl, 2
0x140021a16  jnz     short loc_140021A1D
0x140021a18  test    r8b, r8b
0x140021a1b  jz      short loc_1400219AD
0x140021a1d  mov     r9, cs:WPP_GLOBAL_Control
0x140021a24  lea     r10, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140021a2b  mov     dword ptr [rsp+100h+var_B0], eax
0x140021a2f  mov     ecx, 209h
0x140021a34  mov     [rsp+100h+var_B8], 54Fh
0x140021a3c  mov     [rsp+100h+var_C0], r10
0x140021a41  lea     r10, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140021a48  mov     r9, [r9+40h]
0x140021a4c  mov     [rsp+100h+var_C8], r10
0x140021a51  mov     [rsp+100h+var_D0], 1Ch
0x140021a58  mov     dword ptr [rsp+100h+LengthReturned], 9
0x140021a60  mov     byte ptr [rsp+100h+FileInformationClass], 2
0x140021a65  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140021a6a  jmp     loc_1400219AD
0x140021a6f  mov     r9, [rbp+4Fh+Context]; NewContext
0x140021a73  lea     rax, [rbp+4Fh+OldContext]
0x140021a77  mov     esi, 1
0x140021a7c  mov     qword ptr [rsp+100h+FileInformationClass], rax; OldContext
0x140021a81  mov     r8d, esi; Operation
0x140021a84  mov     rdx, r14; FileObject
0x140021a87  mov     rcx, r13; Instance
0x140021a8a  call    cs:__imp_FltSetStreamContext
0x140021a91  nop     dword ptr [rax+rax+00h]
0x140021a96  mov     ebx, eax
0x140021a98  test    eax, eax
0x140021a9a  jns     loc_140021B46
0x140021aa0  mov     rcx, [rbp+4Fh+Context]; Context
0x140021aa4  call    cs:__imp_FltReleaseContext
0x140021aab  nop     dword ptr [rax+rax+00h]
0x140021ab0  mov     [rbp+4Fh+Context], 0
0x140021ab8  cmp     ebx, 0C01C0002h
0x140021abe  jz      short loc_140021B38
0x140021ac0  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140021ac6  lea     rcx, WPP_RECORDER_INITIALIZED
0x140021acd  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140021ad4  setnz   r8b
0x140021ad8  and     dl, 2
0x140021adb  jnz     short loc_140021AE6
0x140021add  test    r8b, r8b
0x140021ae0  jz      loc_140021C32
0x140021ae6  mov     r9, cs:WPP_GLOBAL_Control
0x140021aed  lea     r10, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140021af4  mov     dword ptr [rsp+100h+var_B0], ebx
0x140021af8  mov     ecx, 209h
0x140021afd  mov     [rsp+100h+var_B8], 567h
0x140021b05  mov     [rsp+100h+var_C0], r10
0x140021b0a  lea     r10, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140021b11  mov     r9, [r9+40h]
0x140021b15  mov     [rsp+100h+var_C8], r10
0x140021b1a  mov     [rsp+100h+var_D0], 1Dh
0x140021b21  mov     dword ptr [rsp+100h+LengthReturned], 9
0x140021b29  mov     byte ptr [rsp+100h+FileInformationClass], 2
0x140021b2e  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140021b33  jmp     loc_140021C32
0x140021b38  mov     rdx, [rbp+4Fh+OldContext]
0x140021b3c  xor     sil, sil
0x140021b3f  xor     ebx, ebx
0x140021b41  jmp     loc_140021BDD
0x140021b46  mov     rdx, [rbp+4Fh+Context]
0x140021b4a  cmp     dword ptr [rdx], 0
0x140021b4d  jnz     loc_140021BDD
0x140021b53  xor     r15b, r15b
0x140021b56  call    cs:__imp_IoGetTopLevelIrp
0x140021b5d  nop     dword ptr [rax+rax+00h]
0x140021b62  test    rax, rax
0x140021b65  jnz     short loc_140021B79
0x140021b67  mov     rcx, rsi; Irp
0x140021b6a  call    cs:__imp_IoSetTopLevelIrp
0x140021b71  nop     dword ptr [rax+rax+00h]
0x140021b76  mov     r15b, sil
0x140021b79  mov     rcx, r14; FileObject
0x140021b7c  call    cs:__imp_FsRtlAcquireFileExclusive
0x140021b83  nop     dword ptr [rax+rax+00h]
0x140021b88  mov     rcx, [r14+28h]; SectionObjectPointer
0x140021b8c  lea     r9, [rbp+4Fh+IoStatus]; IoStatus
0x140021b90  xor     r8d, r8d; Length
0x140021b93  mov     [rsp+100h+FileInformationClass], 0; Flags
0x140021b9b  xor     edx, edx; FileOffset
0x140021b9d  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x140021ba4  nop     dword ptr [rax+rax+00h]
0x140021ba9  test    r15b, r15b
0x140021bac  jz      short loc_140021BBC
0x140021bae  xor     ecx, ecx; Irp
0x140021bb0  call    cs:__imp_IoSetTopLevelIrp
0x140021bb7  nop     dword ptr [rax+rax+00h]
0x140021bbc  mov     rcx, r14; FileObject
0x140021bbf  call    cs:__imp_FsRtlReleaseFile
0x140021bc6  nop     dword ptr [rax+rax+00h]
0x140021bcb  mov     eax, dword ptr [rbp+4Fh+IoStatus]
0x140021bce  test    eax, eax
0x140021bd0  jns     short loc_140021BD9
0x140021bd2  mov     ebx, eax
0x140021bd4  jmp     loc_1400219AD
0x140021bd9  mov     rdx, [rbp+4Fh+Context]
0x140021bdd  test    r12, r12
0x140021be0  jz      short loc_140021BE6
0x140021be2  mov     [r12], sil
0x140021be6  mov     r15, [rbp+4Fh+var_98]
0x140021bea  mov     [rbp+4Fh+Context], 0
0x140021bf2  mov     [r15], rdx
0x140021bf5  jmp     loc_1400219B1
0x140021bfa  test    sil, sil
0x140021bfd  jz      short loc_140021C25
0x140021bff  test    r12, r12
0x140021c02  jz      short loc_140021C10
0x140021c04  cmp     byte ptr [r12], 0
0x140021c09  jz      short loc_140021C10
0x140021c0b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140021c10  xor     r8d, r8d; OldContext
0x140021c13  mov     rdx, r14; FileObject
0x140021c16  mov     rcx, r13; Instance
0x140021c19  call    cs:__imp_FltDeleteStreamContext
0x140021c20  nop     dword ptr [rax+rax+00h]
0x140021c25  test    rdi, rdi
0x140021c28  jz      short loc_140021C32
0x140021c2a  mov     rcx, rdi; P
0x140021c2d  call    PrjfReleaseUnionContext
0x140021c32  mov     eax, ebx
0x140021c34  mov     rcx, [rbp+4Fh+var_48]
0x140021c38  xor     rcx, rsp; StackCookie
0x140021c3b  call    __security_check_cookie
0x140021c40  add     rsp, 0C8h
0x140021c47  pop     r15
0x140021c49  pop     r14
0x140021c4b  pop     r13
0x140021c4d  pop     r12
0x140021c4f  pop     rdi
0x140021c50  pop     rsi
0x140021c51  pop     rbx
0x140021c52  pop     rbp
0x140021c53  retn
```
