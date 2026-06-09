# CmpStartCLFSLog

- ea: `0x14073b510`
- end: `0x14073b8fe`
- name: `CmpStartCLFSLog`
- size: `1006`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING Source@<rcx>, PCUNICODE_STRING@<rdx>, int, __int64, char, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1408b0708`

## callees

- `0x1403199a0`
- `0x14031b800`
- `0x1403f4830`
- `0x14051136c`
- `0x140697724`
- `0x1406d9d70`
- `0x14073b510`
- `0x1408061fc`
- `0x140806484`
- `0x1409cdfe0`
- `0x1409e9990`
- `0x140bae410`
- `0x140bae8e0`

## import_xrefs

- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateMarshallingArea` at `0x14073b7b7`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateMarshallingArea` at `0x14073b7b7`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateLogFile` at `0x14073b697`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateLogFile` at `0x14073b89f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateLogFile` at `0x14073b697`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateLogFile` at `0x14073b89f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x14073b761`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x14073b761`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x14073b81d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x14073b81d`

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
0x14073b510  mov     [rsp-8+arg_10], rbx
0x14073b515  push    rbp
0x14073b516  push    rsi
0x14073b517  push    rdi
0x14073b518  push    r12
0x14073b51a  push    r13
0x14073b51c  push    r14
0x14073b51e  push    r15
0x14073b520  lea     rbp, [rsp-7]
0x14073b525  sub     rsp, 0F0h
0x14073b52c  mov     rax, cs:__security_cookie
0x14073b533  xor     rax, rsp
0x14073b536  mov     [rbp+37h+var_40], rax
0x14073b53a  mov     rax, [rbp+37h+arg_28]
0x14073b53e  xor     ebx, ebx
0x14073b540  mov     r12, [rbp+37h+arg_40]
0x14073b547  xorps   xmm0, xmm0
0x14073b54a  mov     r13, [rbp+37h+arg_48]
0x14073b551  mov     r14, rcx
0x14073b554  mov     [rbp+37h+pcbContainer], rax
0x14073b558  mov     r15, rdx
0x14073b55b  mov     rax, [rbp+37h+arg_38]
0x14073b55f  xorps   xmm1, xmm1
0x14073b562  mov     [r12], rbx
0x14073b566  mov     r8d, 20204D43h
0x14073b56c  mov     [r13+0], rbx
0x14073b570  mov     rsi, r9
0x14073b573  mov     [rbp+37h+var_88], rax
0x14073b577  movzx   eax, word ptr [rcx]
0x14073b57a  movzx   ecx, word ptr [rdx]
0x14073b57d  add     ax, 1Ah
0x14073b581  add     cx, ax
0x14073b584  mov     [rbp+37h+pcbInfoBuffer], ebx
0x14073b587  movzx   edx, cx
0x14073b58a  mov     ecx, 100h
0x14073b58f  movups  xmmword ptr [rbp+37h+Destination.Length], xmm0
0x14073b593  mov     [rbp+37h+Destination.MaximumLength], dx
0x14073b597  mov     [rsp+120h+pplfoLog], rbx
0x14073b59c  mov     [rbp+37h+ppvMarshalContext], rbx
0x14073b5a0  movups  xmmword ptr [rbp+37h+ImpersonationState.Token], xmm1
0x14073b5a4  movups  xmmword ptr [rbp+37h+ApcState.ApcListHead.Flink], xmm0
0x14073b5a8  movups  xmmword ptr [rbp+37h+ApcState.ApcListHead.Flink+10h], xmm0
0x14073b5ac  movups  xmmword ptr [rbp+37h+ApcState.Process], xmm0
0x14073b5b0  call    ExAllocatePool2
0x14073b5b5  mov     [rbp+37h+Destination.Buffer], rax
0x14073b5b9  test    rax, rax
0x14073b5bc  jnz     short loc_14073B5C8
0x14073b5be  mov     eax, 0C000009Ah
0x14073b5c3  jmp     loc_14073B82B
0x14073b5c8  mov     [r12], rbx
0x14073b5cc  lea     rdx, CmpLogPrefix; Source
0x14073b5d3  lea     rcx, [rbp+37h+Destination]; Destination
0x14073b5d7  mov     [r13+0], rbx
0x14073b5db  call    RtlAppendUnicodeStringToString
0x14073b5e0  mov     rdx, r14; Source
0x14073b5e3  lea     rcx, [rbp+37h+Destination]; Destination
0x14073b5e7  call    RtlAppendUnicodeStringToString
0x14073b5ec  mov     rdx, r15; Source
0x14073b5ef  lea     rcx, [rbp+37h+Destination]; Destination
0x14073b5f3  call    RtlAppendUnicodeStringToString
0x14073b5f8  lea     rdx, CmpLogExt; Source
0x14073b5ff  lea     rcx, [rbp+37h+Destination]; Destination
0x14073b603  call    RtlAppendUnicodeStringToString
0x14073b608  mov     edi, 200h
0x14073b60d  mov     eax, cs:Feature_CLFS_Signing__private_featureState
0x14073b613  test    al, 10h
0x14073b615  jz      short loc_14073B61C
0x14073b617  and     eax, 1
0x14073b61a  jmp     short loc_14073B621
0x14073b61c  call    Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline
0x14073b621  test    eax, eax
0x14073b623  jz      short loc_14073B630
0x14073b625  cmp     [rbp+37h+arg_30], bl
0x14073b628  mov     eax, 1000200h
0x14073b62d  cmovz   edi, eax
0x14073b630  mov     [rsp+120h+pplfoLog], rbx
0x14073b635  lea     rdx, [rbp+37h+ImpersonationState]; ImpersonationState
0x14073b639  mov     [rbp+37h+ppvMarshalContext], rbx
0x14073b63d  mov     rcx, gs:188h; Thread
0x14073b646  call    PsDisableImpersonation
0x14073b64b  mov     rcx, cs:PsInitialSystemProcess; PROCESS
0x14073b652  lea     rdx, [rbp+37h+ApcState]; ApcState
0x14073b656  mov     [rsp+120h+var_C0], al
0x14073b65a  call    KeStackAttachProcess
0x14073b65f  mov     [rsp+120h+cbContext], ebx; cbContext
0x14073b663  lea     rdx, [rbp+37h+Destination]; puszLogFileName
0x14073b667  mov     [rsp+120h+pvContext], rbx; pvContext
0x14073b66c  lea     rcx, [rsp+120h+pplfoLog]; pplfoLog
0x14073b671  mov     [rsp+120h+fLogOptionFlag], edi; fLogOptionFlag
0x14073b675  xor     r9d, r9d; dwShareMode
0x14073b678  mov     [rsp+120h+fFlagsAndAttributes], ebx; fFlagsAndAttributes
0x14073b67c  mov     r8d, 0C0010000h; fDesiredAccess
0x14073b682  mov     [rsp+120h+fCreateOptions], 8; fCreateOptions
0x14073b68a  mov     [rsp+120h+fCreateDisposition], 1; fCreateDisposition
0x14073b692  mov     [rsp+120h+psdLogFile], rsi; psdLogFile
0x14073b697  call    cs:__imp_ClfsCreateLogFile
0x14073b69e  nop     dword ptr [rax+rax+00h]
0x14073b6a3  mov     ebx, eax
0x14073b6a5  mov     eax, cs:Feature_CLFS_Signing__private_featureState
0x14073b6ab  mov     ecx, 10h
0x14073b6b0  test    cl, al
0x14073b6b2  jz      short loc_14073B6B9
0x14073b6b4  and     eax, 1
0x14073b6b7  jmp     short loc_14073B6C3
0x14073b6b9  call    Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline
0x14073b6be  mov     ecx, 10h
0x14073b6c3  test    eax, eax
0x14073b6c5  jz      short loc_14073B723
0x14073b6c7  mov     eax, cs:Feature_AutoCleanupClfsLogfiles__private_featureState
0x14073b6cd  test    cl, al
0x14073b6cf  jz      short loc_14073B6D6
0x14073b6d1  and     eax, 1
0x14073b6d4  jmp     short loc_14073B6E0
0x14073b6d6  call    Feature_AutoCleanupClfsLogfiles__private_IsEnabledDeviceUsageNoInline
0x14073b6db  mov     ecx, 10h
0x14073b6e0  test    eax, eax
0x14073b6e2  jz      short loc_14073B723
0x14073b6e4  cmp     ebx, 0C01A000Dh
0x14073b6ea  jnz     short loc_14073B723
0x14073b6ec  mov     word ptr [rsp+120h+fCreateOptions], cx
0x14073b6f1  lea     rax, aD_4; ".%d"
0x14073b6f8  mov     qword ptr [rsp+120h+fCreateDisposition], rax
0x14073b6fd  lea     r9, CmpContainerSuffix
0x14073b704  lea     r8, CmpLogExt
0x14073b70b  mov     dword ptr [rsp+120h+psdLogFile], 0
0x14073b713  mov     rdx, r15
0x14073b716  mov     rcx, r14
0x14073b719  call    CmpDeleteCorruptedLogfile
0x14073b71e  jmp     loc_14073B7E0
0x14073b723  test    ebx, ebx
0x14073b725  js      loc_14073B853
0x14073b72b  mov     edx, 78h ; 'x'
0x14073b730  mov     ecx, 100h
0x14073b735  mov     r8d, 20204D43h
0x14073b73b  mov     [rbp+37h+pcbInfoBuffer], edx
0x14073b73e  call    ExAllocatePool2
0x14073b743  mov     rsi, rax
0x14073b746  test    rax, rax
0x14073b749  jnz     short loc_14073B755
0x14073b74b  mov     ebx, 0C000009Ah
0x14073b750  jmp     loc_14073B7E0
0x14073b755  mov     rcx, [rsp+120h+pplfoLog]; plfoLog
0x14073b75a  lea     r8, [rbp+37h+pcbInfoBuffer]; pcbInfoBuffer
0x14073b75e  mov     rdx, rsi; pinfoBuffer
0x14073b761  call    cs:__imp_ClfsGetLogFileInformation
0x14073b768  nop     dword ptr [rax+rax+00h]
0x14073b76d  xor     edx, edx; Tag
0x14073b76f  mov     rcx, rsi; P
0x14073b772  mov     ebx, eax
0x14073b774  test    eax, eax
0x14073b776  jns     short loc_14073B77F
0x14073b778  call    ExFreePoolWithTag
0x14073b77d  jmp     short loc_14073B7E0
0x14073b77f  mov     edi, [rsi+28h]
0x14073b782  call    ExFreePoolWithTag
0x14073b787  mov     rcx, [rsp+120h+pplfoLog]; plfoLog
0x14073b78c  lea     rax, [rbp+37h+ppvMarshalContext]
0x14073b790  mov     qword ptr [rsp+120h+fFlagsAndAttributes], rax; ppvMarshalContext
0x14073b795  xor     r9d, r9d; pfnFreeBuffer
0x14073b798  mov     [rsp+120h+fCreateOptions], 14h; cMaxReadBuffers
0x14073b7a0  xor     r8d, r8d; pfnAllocBuffer
0x14073b7a3  mov     [rsp+120h+fCreateDisposition], 2; cMaxWriteBuffers
0x14073b7ab  mov     dword ptr [rsp+120h+psdLogFile], 1000h; cbMarshallingBuffer
0x14073b7b3  lea     edx, [r9+1]; ePoolType
0x14073b7b7  call    cs:__imp_ClfsCreateMarshallingArea
0x14073b7be  nop     dword ptr [rax+rax+00h]
0x14073b7c3  mov     ebx, eax
0x14073b7c5  test    eax, eax
0x14073b7c7  js      short loc_14073B7E0
0x14073b7c9  mov     rax, [rbp+37h+var_88]
0x14073b7cd  mov     [rax], edi
0x14073b7cf  mov     rax, [rsp+120h+pplfoLog]
0x14073b7d4  mov     [r12], rax
0x14073b7d8  mov     rax, [rbp+37h+ppvMarshalContext]
0x14073b7dc  mov     [r13+0], rax
0x14073b7e0  xor     edx, edx
0x14073b7e2  lea     rcx, [rbp+37h+ApcState]
0x14073b7e6  call    KiUnstackDetachProcess
0x14073b7eb  cmp     [rsp+120h+var_C0], 0
0x14073b7f0  jz      short loc_14073B804
0x14073b7f2  mov     rcx, gs:188h; Thread
0x14073b7fb  lea     rdx, [rbp+37h+ImpersonationState]; ImpersonationState
0x14073b7ff  call    PsRestoreImpersonation
0x14073b804  mov     rcx, [rbp+37h+Destination.Buffer]; P
0x14073b808  xor     edx, edx; Tag
0x14073b80a  call    ExFreePoolWithTag
0x14073b80f  test    ebx, ebx
0x14073b811  jns     short loc_14073B829
0x14073b813  mov     rcx, [rsp+120h+pplfoLog]; plfoLog
0x14073b818  test    rcx, rcx
0x14073b81b  jz      short loc_14073B829
0x14073b81d  call    cs:__imp_ClfsCloseLogFileObject
0x14073b824  nop     dword ptr [rax+rax+00h]
0x14073b829  mov     eax, ebx
0x14073b82b  mov     rcx, [rbp+37h+var_40]
0x14073b82f  xor     rcx, rsp; StackCookie
0x14073b832  call    __security_check_cookie
0x14073b837  mov     rbx, [rsp+120h+arg_10]
0x14073b83f  add     rsp, 0F0h
0x14073b846  pop     r15
0x14073b848  pop     r14
0x14073b84a  pop     r13
0x14073b84c  pop     r12
0x14073b84e  pop     rdi
0x14073b84f  pop     rsi
0x14073b850  pop     rbp
0x14073b851  retn
0x14073b853  cmp     ebx, 0C0000034h
0x14073b859  jnz     short loc_14073B7E0
0x14073b85b  mov     [rsp+120h+cbContext], 0; cbContext
0x14073b863  lea     rdx, [rbp+37h+Destination]; puszLogFileName
0x14073b867  mov     [rsp+120h+pvContext], 0; pvContext
0x14073b870  lea     rcx, [rsp+120h+pplfoLog]; pplfoLog
0x14073b875  mov     [rsp+120h+fLogOptionFlag], edi; fLogOptionFlag
0x14073b879  xor     r9d, r9d; dwShareMode
0x14073b87c  mov     [rsp+120h+fFlagsAndAttributes], 0; fFlagsAndAttributes
0x14073b884  mov     r8d, 0C0010000h; fDesiredAccess
0x14073b88a  mov     [rsp+120h+fCreateOptions], 8; fCreateOptions
0x14073b892  mov     [rsp+120h+fCreateDisposition], 2; fCreateDisposition
0x14073b89a  mov     [rsp+120h+psdLogFile], rsi; psdLogFile
0x14073b89f  call    cs:__imp_ClfsCreateLogFile
0x14073b8a6  nop     dword ptr [rax+rax+00h]
0x14073b8ab  mov     ebx, eax
0x14073b8ad  test    eax, eax
0x14073b8af  js      loc_14073B7E0
0x14073b8b5  xor     edi, edi
0x14073b8b7  lea     rsi, CmpContainerSuffix
0x14073b8be  cmp     edi, 3
0x14073b8c1  jnb     loc_14073B787
0x14073b8c7  mov     rax, [rbp+37h+pcbContainer]
0x14073b8cb  lea     r9, CmpLogExt; PCUNICODE_STRING
0x14073b8d2  mov     rcx, [rsp+120h+pplfoLog]; plfoLog
0x14073b8d7  mov     r8, r15; PCUNICODE_STRING
0x14073b8da  mov     qword ptr [rsp+120h+fCreateOptions], rax; pcbContainer
0x14073b8df  mov     rdx, r14; Source
0x14073b8e2  mov     [rsp+120h+fCreateDisposition], edi; int
0x14073b8e6  mov     [rsp+120h+psdLogFile], rsi; PCUNICODE_STRING
0x14073b8eb  call    CmpAddRemoveContainerToCLFSLog
0x14073b8f0  mov     ebx, eax
0x14073b8f2  test    eax, eax
0x14073b8f4  js      loc_14073B7E0
0x14073b8fa  inc     edi
0x14073b8fc  jmp     short loc_14073B8BE
```
