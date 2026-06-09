# CmpStartCLFSLog

- ea: `0x14073fcd0`
- end: `0x1407400be`
- name: `CmpStartCLFSLog`
- size: `1006`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source, PCUNICODE_STRING, __int64, void *, int, ULONGLONG *, char, unsigned int *, FILE_OBJECT **, PVOID *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1408e5618`

## callees

- `0x140366800`
- `0x140368660`
- `0x140388750`
- `0x14051754c`
- `0x14069cfd4`
- `0x1406dc8c0`
- `0x14073fcd0`
- `0x140808eec`
- `0x140809174`
- `0x1409c76d0`
- `0x1409f2a40`
- `0x140bb1410`
- `0x140bb19f0`

## import_xrefs

- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateMarshallingArea` at `0x14073ff77`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateMarshallingArea` at `0x14073ff77`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateLogFile` at `0x14073fe57`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateLogFile` at `0x14074005f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateLogFile` at `0x14073fe57`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateLogFile` at `0x14074005f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x14073ff21`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x14073ff21`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x14073ffdd`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x14073ffdd`

## pseudocode

```c
__int64 __fastcall CmpStartCLFSLog(
        PCUNICODE_STRING Source,
        PCUNICODE_STRING a2,
        __int64 a3,
        void *a4,
        int a5,
        ULONGLONG *a6,
        char a7,
        unsigned int *a8,
        FILE_OBJECT **a9,
        PVOID *a10)
{
  unsigned __int16 v13; // cx
  ULONG fLogOptionFlag; // edi
  int IsEnabledDeviceUsageNoInline; // eax
  NTSTATUS LogFileInformation; // ebx
  int v18; // eax
  int v19; // eax
  CLFS_INFORMATION *Pool2; // rax
  CLFS_INFORMATION *v21; // rsi
  unsigned int i; // edi
  ULONG fCreateOptions[2]; // [rsp+30h] [rbp-B9h]
  BOOLEAN v24; // [rsp+60h] [rbp-89h]
  FILE_OBJECT *pplfoLog; // [rsp+68h] [rbp-81h] BYREF
  ULONG pcbInfoBuffer; // [rsp+70h] [rbp-79h] BYREF
  UNICODE_STRING Destination; // [rsp+78h] [rbp-71h] BYREF
  PVOID ppvMarshalContext; // [rsp+88h] [rbp-61h] BYREF
  PULONGLONG pcbContainer; // [rsp+90h] [rbp-59h]
  unsigned int *v30; // [rsp+98h] [rbp-51h]
  _SE_IMPERSONATION_STATE ImpersonationState; // [rsp+A0h] [rbp-49h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+B0h] [rbp-39h] BYREF

  pcbContainer = a6;
  *a9 = 0;
  *a10 = 0;
  v30 = a8;
  v13 = Source->Length + 26 + a2->Length;
  pcbInfoBuffer = 0;
  *(_QWORD *)&Destination.Length = 0;
  Destination.MaximumLength = v13;
  pplfoLog = 0;
  ppvMarshalContext = 0;
  ImpersonationState = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  Destination.Buffer = (wchar_t *)ExAllocatePool2(256, v13, 538987843);
  if ( !Destination.Buffer )
    return 3221225626LL;
  *a9 = 0;
  *a10 = 0;
  RtlAppendUnicodeStringToString(&Destination, &CmpLogPrefix);
  RtlAppendUnicodeStringToString(&Destination, Source);
  RtlAppendUnicodeStringToString(&Destination, a2);
  RtlAppendUnicodeStringToString(&Destination, &CmpLogExt);
  fLogOptionFlag = 512;
  if ( (Feature_CLFS_Signing__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_CLFS_Signing__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline && !a7 )
    fLogOptionFlag = 16777728;
  pplfoLog = 0;
  ppvMarshalContext = 0;
  v24 = PsDisableImpersonation(KeGetCurrentThread(), &ImpersonationState);
  KeStackAttachProcess(PsInitialSystemProcess, &ApcState);
  LogFileInformation = ClfsCreateLogFile(&pplfoLog, &Destination, 0xC0010000, 0, a4, 1u, 8u, 0, fLogOptionFlag, 0, 0);
  if ( (Feature_CLFS_Signing__private_featureState & 0x10) != 0 )
    v18 = Feature_CLFS_Signing__private_featureState & 1;
  else
    v18 = Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline();
  if ( !v18
    || ((Feature_AutoCleanupClfsLogfiles__private_featureState & 0x10) == 0
      ? (v19 = Feature_AutoCleanupClfsLogfiles__private_IsEnabledDeviceUsageNoInline())
      : (v19 = Feature_AutoCleanupClfsLogfiles__private_featureState & 1),
        !v19 || LogFileInformation != -1072037875) )
  {
    if ( LogFileInformation < 0 )
    {
      if ( LogFileInformation != -1073741772 )
        goto LABEL_27;
      LogFileInformation = ClfsCreateLogFile(
                             &pplfoLog,
                             &Destination,
                             0xC0010000,
                             0,
                             a4,
                             2u,
                             8u,
                             0,
                             fLogOptionFlag,
                             0,
                             0);
      if ( LogFileInformation < 0 )
        goto LABEL_27;
      for ( i = 0; i < 3; ++i )
      {
        LogFileInformation = CmpAddRemoveContainerToCLFSLog(
                               pplfoLog,
                               Source,
                               a2,
                               &CmpLogExt,
                               &CmpContainerSuffix,
                               i,
                               pcbContainer);
        if ( LogFileInformation < 0 )
          goto LABEL_27;
      }
    }
    else
    {
      pcbInfoBuffer = 120;
      Pool2 = (CLFS_INFORMATION *)ExAllocatePool2(256, 120, 538987843);
      v21 = Pool2;
      if ( !Pool2 )
      {
        LogFileInformation = -1073741670;
        goto LABEL_27;
      }
      LogFileInformation = ClfsGetLogFileInformation(pplfoLog, Pool2, &pcbInfoBuffer);
      if ( LogFileInformation < 0 )
      {
        ExFreePoolWithTag(v21, 0);
        goto LABEL_27;
      }
      i = v21->TotalContainers;
      ExFreePoolWithTag(v21, 0);
    }
    LogFileInformation = ClfsCreateMarshallingArea(pplfoLog, PagedPool, 0, 0, 0x1000u, 2u, 0x14u, &ppvMarshalContext);
    if ( LogFileInformation >= 0 )
    {
      *v30 = i;
      *a9 = pplfoLog;
      *a10 = ppvMarshalContext;
    }
    goto LABEL_27;
  }
  LOWORD(fCreateOptions[0]) = 16;
  CmpDeleteCorruptedLogfile(Source, a2, &CmpLogExt, &CmpContainerSuffix, 0, L".%d", *(_QWORD *)fCreateOptions);
LABEL_27:
  KiUnstackDetachProcess(&ApcState, 0);
  if ( v24 )
    PsRestoreImpersonation(KeGetCurrentThread(), &ImpersonationState);
  ExFreePoolWithTag(Destination.Buffer, 0);
  if ( LogFileInformation < 0 )
  {
    if ( pplfoLog )
      ClfsCloseLogFileObject(pplfoLog);
  }
  return (unsigned int)LogFileInformation;
}

```

## disassembly

```asm
0x14073fcd0  mov     [rsp-8+arg_10], rbx
0x14073fcd5  push    rbp
0x14073fcd6  push    rsi
0x14073fcd7  push    rdi
0x14073fcd8  push    r12
0x14073fcda  push    r13
0x14073fcdc  push    r14
0x14073fcde  push    r15
0x14073fce0  lea     rbp, [rsp-7]
0x14073fce5  sub     rsp, 0F0h
0x14073fcec  mov     rax, cs:__security_cookie
0x14073fcf3  xor     rax, rsp
0x14073fcf6  mov     [rbp+37h+var_40], rax
0x14073fcfa  mov     rax, [rbp+37h+arg_28]
0x14073fcfe  xor     ebx, ebx
0x14073fd00  mov     r12, [rbp+37h+arg_40]
0x14073fd07  xorps   xmm0, xmm0
0x14073fd0a  mov     r13, [rbp+37h+arg_48]
0x14073fd11  mov     r14, rcx
0x14073fd14  mov     [rbp+37h+pcbContainer], rax
0x14073fd18  mov     r15, rdx
0x14073fd1b  mov     rax, [rbp+37h+arg_38]
0x14073fd1f  xorps   xmm1, xmm1
0x14073fd22  mov     [r12], rbx
0x14073fd26  mov     r8d, 20204D43h
0x14073fd2c  mov     [r13+0], rbx
0x14073fd30  mov     rsi, r9
0x14073fd33  mov     [rbp+37h+var_88], rax
0x14073fd37  movzx   eax, word ptr [rcx]
0x14073fd3a  movzx   ecx, word ptr [rdx]
0x14073fd3d  add     ax, 1Ah
0x14073fd41  add     cx, ax
0x14073fd44  mov     [rbp+37h+pcbInfoBuffer], ebx
0x14073fd47  movzx   edx, cx
0x14073fd4a  mov     ecx, 100h
0x14073fd4f  movups  xmmword ptr [rbp+37h+Destination.Length], xmm0
0x14073fd53  mov     [rbp+37h+Destination.MaximumLength], dx
0x14073fd57  mov     [rsp+120h+pplfoLog], rbx
0x14073fd5c  mov     [rbp+37h+ppvMarshalContext], rbx
0x14073fd60  movups  xmmword ptr [rbp+37h+ImpersonationState.Token], xmm1
0x14073fd64  movups  xmmword ptr [rbp+37h+ApcState.ApcListHead.Flink], xmm0
0x14073fd68  movups  xmmword ptr [rbp+37h+ApcState.ApcListHead.Flink+10h], xmm0
0x14073fd6c  movups  xmmword ptr [rbp+37h+ApcState.Process], xmm0
0x14073fd70  call    ExAllocatePool2
0x14073fd75  mov     [rbp+37h+Destination.Buffer], rax
0x14073fd79  test    rax, rax
0x14073fd7c  jnz     short loc_14073FD88
0x14073fd7e  mov     eax, 0C000009Ah
0x14073fd83  jmp     loc_14073FFEB
0x14073fd88  mov     [r12], rbx
0x14073fd8c  lea     rdx, CmpLogPrefix; Source
0x14073fd93  lea     rcx, [rbp+37h+Destination]; Destination
0x14073fd97  mov     [r13+0], rbx
0x14073fd9b  call    RtlAppendUnicodeStringToString
0x14073fda0  mov     rdx, r14; Source
0x14073fda3  lea     rcx, [rbp+37h+Destination]; Destination
0x14073fda7  call    RtlAppendUnicodeStringToString
0x14073fdac  mov     rdx, r15; Source
0x14073fdaf  lea     rcx, [rbp+37h+Destination]; Destination
0x14073fdb3  call    RtlAppendUnicodeStringToString
0x14073fdb8  lea     rdx, CmpLogExt; Source
0x14073fdbf  lea     rcx, [rbp+37h+Destination]; Destination
0x14073fdc3  call    RtlAppendUnicodeStringToString
0x14073fdc8  mov     edi, 200h
0x14073fdcd  mov     eax, cs:Feature_CLFS_Signing__private_featureState
0x14073fdd3  test    al, 10h
0x14073fdd5  jz      short loc_14073FDDC
0x14073fdd7  and     eax, 1
0x14073fdda  jmp     short loc_14073FDE1
0x14073fddc  call    Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline
0x14073fde1  test    eax, eax
0x14073fde3  jz      short loc_14073FDF0
0x14073fde5  cmp     [rbp+37h+arg_30], bl
0x14073fde8  mov     eax, 1000200h
0x14073fded  cmovz   edi, eax
0x14073fdf0  mov     [rsp+120h+pplfoLog], rbx
0x14073fdf5  lea     rdx, [rbp+37h+ImpersonationState]; ImpersonationState
0x14073fdf9  mov     [rbp+37h+ppvMarshalContext], rbx
0x14073fdfd  mov     rcx, gs:188h; Thread
0x14073fe06  call    PsDisableImpersonation
0x14073fe0b  mov     rcx, cs:PsInitialSystemProcess; PROCESS
0x14073fe12  lea     rdx, [rbp+37h+ApcState]; ApcState
0x14073fe16  mov     [rsp+120h+var_C0], al
0x14073fe1a  call    KeStackAttachProcess
0x14073fe1f  mov     [rsp+120h+cbContext], ebx; cbContext
0x14073fe23  lea     rdx, [rbp+37h+Destination]; puszLogFileName
0x14073fe27  mov     [rsp+120h+pvContext], rbx; pvContext
0x14073fe2c  lea     rcx, [rsp+120h+pplfoLog]; pplfoLog
0x14073fe31  mov     [rsp+120h+fLogOptionFlag], edi; fLogOptionFlag
0x14073fe35  xor     r9d, r9d; dwShareMode
0x14073fe38  mov     [rsp+120h+fFlagsAndAttributes], ebx; fFlagsAndAttributes
0x14073fe3c  mov     r8d, 0C0010000h; fDesiredAccess
0x14073fe42  mov     [rsp+120h+fCreateOptions], 8; fCreateOptions
0x14073fe4a  mov     [rsp+120h+fCreateDisposition], 1; fCreateDisposition
0x14073fe52  mov     [rsp+120h+psdLogFile], rsi; psdLogFile
0x14073fe57  call    cs:__imp_ClfsCreateLogFile
0x14073fe5e  nop     dword ptr [rax+rax+00h]
0x14073fe63  mov     ebx, eax
0x14073fe65  mov     eax, cs:Feature_CLFS_Signing__private_featureState
0x14073fe6b  mov     ecx, 10h
0x14073fe70  test    cl, al
0x14073fe72  jz      short loc_14073FE79
0x14073fe74  and     eax, 1
0x14073fe77  jmp     short loc_14073FE83
0x14073fe79  call    Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline
0x14073fe7e  mov     ecx, 10h
0x14073fe83  test    eax, eax
0x14073fe85  jz      short loc_14073FEE3
0x14073fe87  mov     eax, cs:Feature_AutoCleanupClfsLogfiles__private_featureState
0x14073fe8d  test    cl, al
0x14073fe8f  jz      short loc_14073FE96
0x14073fe91  and     eax, 1
0x14073fe94  jmp     short loc_14073FEA0
0x14073fe96  call    Feature_AutoCleanupClfsLogfiles__private_IsEnabledDeviceUsageNoInline
0x14073fe9b  mov     ecx, 10h
0x14073fea0  test    eax, eax
0x14073fea2  jz      short loc_14073FEE3
0x14073fea4  cmp     ebx, 0C01A000Dh
0x14073feaa  jnz     short loc_14073FEE3
0x14073feac  mov     word ptr [rsp+120h+fCreateOptions], cx
0x14073feb1  lea     rax, aD_4; ".%d"
0x14073feb8  mov     qword ptr [rsp+120h+fCreateDisposition], rax
0x14073febd  lea     r9, CmpContainerSuffix
0x14073fec4  lea     r8, CmpLogExt
0x14073fecb  mov     dword ptr [rsp+120h+psdLogFile], 0
0x14073fed3  mov     rdx, r15
0x14073fed6  mov     rcx, r14
0x14073fed9  call    CmpDeleteCorruptedLogfile
0x14073fede  jmp     loc_14073FFA0
0x14073fee3  test    ebx, ebx
0x14073fee5  js      loc_140740013
0x14073feeb  mov     edx, 78h ; 'x'
0x14073fef0  mov     ecx, 100h
0x14073fef5  mov     r8d, 20204D43h
0x14073fefb  mov     [rbp+37h+pcbInfoBuffer], edx
0x14073fefe  call    ExAllocatePool2
0x14073ff03  mov     rsi, rax
0x14073ff06  test    rax, rax
0x14073ff09  jnz     short loc_14073FF15
0x14073ff0b  mov     ebx, 0C000009Ah
0x14073ff10  jmp     loc_14073FFA0
0x14073ff15  mov     rcx, [rsp+120h+pplfoLog]; plfoLog
0x14073ff1a  lea     r8, [rbp+37h+pcbInfoBuffer]; pcbInfoBuffer
0x14073ff1e  mov     rdx, rsi; pinfoBuffer
0x14073ff21  call    cs:__imp_ClfsGetLogFileInformation
0x14073ff28  nop     dword ptr [rax+rax+00h]
0x14073ff2d  xor     edx, edx; Tag
0x14073ff2f  mov     rcx, rsi; P
0x14073ff32  mov     ebx, eax
0x14073ff34  test    eax, eax
0x14073ff36  jns     short loc_14073FF3F
0x14073ff38  call    ExFreePoolWithTag
0x14073ff3d  jmp     short loc_14073FFA0
0x14073ff3f  mov     edi, [rsi+28h]
0x14073ff42  call    ExFreePoolWithTag
0x14073ff47  mov     rcx, [rsp+120h+pplfoLog]; plfoLog
0x14073ff4c  lea     rax, [rbp+37h+ppvMarshalContext]
0x14073ff50  mov     qword ptr [rsp+120h+fFlagsAndAttributes], rax; ppvMarshalContext
0x14073ff55  xor     r9d, r9d; pfnFreeBuffer
0x14073ff58  mov     [rsp+120h+fCreateOptions], 14h; cMaxReadBuffers
0x14073ff60  xor     r8d, r8d; pfnAllocBuffer
0x14073ff63  mov     [rsp+120h+fCreateDisposition], 2; cMaxWriteBuffers
0x14073ff6b  mov     dword ptr [rsp+120h+psdLogFile], 1000h; cbMarshallingBuffer
0x14073ff73  lea     edx, [r9+1]; ePoolType
0x14073ff77  call    cs:__imp_ClfsCreateMarshallingArea
0x14073ff7e  nop     dword ptr [rax+rax+00h]
0x14073ff83  mov     ebx, eax
0x14073ff85  test    eax, eax
0x14073ff87  js      short loc_14073FFA0
0x14073ff89  mov     rax, [rbp+37h+var_88]
0x14073ff8d  mov     [rax], edi
0x14073ff8f  mov     rax, [rsp+120h+pplfoLog]
0x14073ff94  mov     [r12], rax
0x14073ff98  mov     rax, [rbp+37h+ppvMarshalContext]
0x14073ff9c  mov     [r13+0], rax
0x14073ffa0  xor     edx, edx
0x14073ffa2  lea     rcx, [rbp+37h+ApcState]
0x14073ffa6  call    KiUnstackDetachProcess
0x14073ffab  cmp     [rsp+120h+var_C0], 0
0x14073ffb0  jz      short loc_14073FFC4
0x14073ffb2  mov     rcx, gs:188h; Thread
0x14073ffbb  lea     rdx, [rbp+37h+ImpersonationState]; ImpersonationState
0x14073ffbf  call    PsRestoreImpersonation
0x14073ffc4  mov     rcx, [rbp+37h+Destination.Buffer]; P
0x14073ffc8  xor     edx, edx; Tag
0x14073ffca  call    ExFreePoolWithTag
0x14073ffcf  test    ebx, ebx
0x14073ffd1  jns     short loc_14073FFE9
0x14073ffd3  mov     rcx, [rsp+120h+pplfoLog]; plfoLog
0x14073ffd8  test    rcx, rcx
0x14073ffdb  jz      short loc_14073FFE9
0x14073ffdd  call    cs:__imp_ClfsCloseLogFileObject
0x14073ffe4  nop     dword ptr [rax+rax+00h]
0x14073ffe9  mov     eax, ebx
0x14073ffeb  mov     rcx, [rbp+37h+var_40]
0x14073ffef  xor     rcx, rsp; StackCookie
0x14073fff2  call    __security_check_cookie
0x14073fff7  mov     rbx, [rsp+120h+arg_10]
0x14073ffff  add     rsp, 0F0h
0x140740006  pop     r15
0x140740008  pop     r14
0x14074000a  pop     r13
0x14074000c  pop     r12
0x14074000e  pop     rdi
0x14074000f  pop     rsi
0x140740010  pop     rbp
0x140740011  retn
0x140740013  cmp     ebx, 0C0000034h
0x140740019  jnz     short loc_14073FFA0
0x14074001b  mov     [rsp+120h+cbContext], 0; cbContext
0x140740023  lea     rdx, [rbp+37h+Destination]; puszLogFileName
0x140740027  mov     [rsp+120h+pvContext], 0; pvContext
0x140740030  lea     rcx, [rsp+120h+pplfoLog]; pplfoLog
0x140740035  mov     [rsp+120h+fLogOptionFlag], edi; fLogOptionFlag
0x140740039  xor     r9d, r9d; dwShareMode
0x14074003c  mov     [rsp+120h+fFlagsAndAttributes], 0; fFlagsAndAttributes
0x140740044  mov     r8d, 0C0010000h; fDesiredAccess
0x14074004a  mov     [rsp+120h+fCreateOptions], 8; fCreateOptions
0x140740052  mov     [rsp+120h+fCreateDisposition], 2; fCreateDisposition
0x14074005a  mov     [rsp+120h+psdLogFile], rsi; psdLogFile
0x14074005f  call    cs:__imp_ClfsCreateLogFile
0x140740066  nop     dword ptr [rax+rax+00h]
0x14074006b  mov     ebx, eax
0x14074006d  test    eax, eax
0x14074006f  js      loc_14073FFA0
0x140740075  xor     edi, edi
0x140740077  lea     rsi, CmpContainerSuffix
0x14074007e  cmp     edi, 3
0x140740081  jnb     loc_14073FF47
0x140740087  mov     rax, [rbp+37h+pcbContainer]
0x14074008b  lea     r9, CmpLogExt; PCUNICODE_STRING
0x140740092  mov     rcx, [rsp+120h+pplfoLog]; plfoLog
0x140740097  mov     r8, r15; PCUNICODE_STRING
0x14074009a  mov     qword ptr [rsp+120h+fCreateOptions], rax; pcbContainer
0x14074009f  mov     rdx, r14; Source
0x1407400a2  mov     [rsp+120h+fCreateDisposition], edi; int
0x1407400a6  mov     [rsp+120h+psdLogFile], rsi; PCUNICODE_STRING
0x1407400ab  call    CmpAddRemoveContainerToCLFSLog
0x1407400b0  mov     ebx, eax
0x1407400b2  test    eax, eax
0x1407400b4  js      loc_14073FFA0
0x1407400ba  inc     edi
0x1407400bc  jmp     short loc_14074007E
```
