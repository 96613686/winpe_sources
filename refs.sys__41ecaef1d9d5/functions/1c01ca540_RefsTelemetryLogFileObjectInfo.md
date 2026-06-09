# RefsTelemetryLogFileObjectInfo

- ea: `0x1c01ca540`
- end: `0x1c01ca95c`
- name: `RefsTelemetryLogFileObjectInfo`
- size: `1052`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1c0068960`
- `0x1c00a8178`
- `0x1c00a8340`
- `0x1c00a9958`
- `0x1c016cc44`
- `0x1c01ca540`
- `0x1c01d5c98`
- `0x1c01d60b4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1c01ca8f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01ca8f6`
- `ntoskrnl!ObfDereferenceObject` at `0x1c01ca906`
- `ntoskrnl!ObfDereferenceObject` at `0x1c01ca91a`
- `ntoskrnl!ObfDereferenceObject` at `0x1c01ca906`
- `ntoskrnl!ObfDereferenceObject` at `0x1c01ca91a`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1c01ca602`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1c01ca602`
- `ntoskrnl!RtlInitAnsiString` at `0x1c01ca61b`
- `ntoskrnl!RtlInitAnsiString` at `0x1c01ca61b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c01ca8e5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c01ca8e5`
- `ntoskrnl!PsGetThreadProcess` at `0x1c01ca5dd`
- `ntoskrnl!PsGetThreadProcess` at `0x1c01ca5dd`
- `ntoskrnl!PsGetProcessId` at `0x1c01ca5ef`
- `ntoskrnl!PsGetProcessId` at `0x1c01ca5ef`

## pseudocode

```c
LONG_PTR __fastcall RefsTelemetryLogFileObjectInfo(__int64 a1, void *a2)
{
  __int64 v2; // rdi
  const char *v3; // r13
  _QWORD *v5; // rcx
  struct _KTHREAD *v6; // r14
  unsigned __int8 v7; // bl
  int v8; // r12d
  int v9; // r15d
  struct _KPROCESS *ThreadProcess; // rbx
  __int64 ProcessImageFileName; // rax
  __int64 v12; // rbx
  int v13; // eax
  int v14; // eax
  LONG_PTR result; // rax
  unsigned __int8 v16; // [rsp+A0h] [rbp-80h]
  _BYTE v17[3]; // [rsp+A1h] [rbp-7Fh] BYREF
  unsigned int v18; // [rsp+A4h] [rbp-7Ch]
  int v19; // [rsp+A8h] [rbp-78h]
  UNICODE_STRING StringIn; // [rsp+B0h] [rbp-70h] BYREF
  HANDLE ProcessId; // [rsp+C0h] [rbp-60h]
  struct _UNICODE_STRING UnicodeString; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+D8h] [rbp-48h]
  __int64 v24; // [rsp+E0h] [rbp-40h]
  __int64 v25; // [rsp+E8h] [rbp-38h]
  __int64 v26; // [rsp+F0h] [rbp-30h]
  PVOID Object; // [rsp+F8h] [rbp-28h]
  struct _STRING DestinationString; // [rsp+100h] [rbp-20h] BYREF
  char v29; // [rsp+110h] [rbp-10h] BYREF

  v2 = *(_QWORD *)(a1 + 64);
  v3 = File;
  DestinationString = 0;
  *(_DWORD *)(&StringIn.MaximumLength + 1) = 0;
  v5 = (_QWORD *)*((_QWORD *)a2 + 6);
  v6 = (struct _KTHREAD *)*((_QWORD *)a2 + 5);
  v7 = *((_BYTE *)a2 + 68);
  v8 = *((_DWORD *)a2 + 15);
  v9 = *((_DWORD *)a2 + 16);
  v23 = *((_QWORD *)a2 + 2);
  v25 = *((_QWORD *)a2 + 3);
  v26 = *((_QWORD *)a2 + 4);
  v18 = *((_DWORD *)a2 + 18);
  v19 = *((_DWORD *)a2 + 14);
  ProcessId = 0;
  v17[0] = 0;
  Object = v5;
  v16 = v7;
  UnicodeString = 0;
  v24 = v5[3];
  if ( v6 )
  {
    ThreadProcess = PsGetThreadProcess(v6);
    ProcessId = PsGetProcessId(ThreadProcess);
    ProcessImageFileName = PsGetProcessImageFileName(ThreadProcess);
    v7 = v16;
    v3 = (const char *)ProcessImageFileName;
  }
  RtlInitAnsiString(&DestinationString, v3);
  RefsGetVolumeName(0, v2, &UnicodeString, v17);
  StringIn.Buffer = (PWSTR)&v29;
  *(_DWORD *)&StringIn.Length = 4325376;
  if ( RtlUnicodeStringPrintf(
         &StringIn,
         L"%016I64X %016I64X",
         *(_QWORD *)(*(_QWORD *)(v24 + 120) + 16LL),
         *(_QWORD *)(*(_QWORD *)(v24 + 120) + 8LL)) < 0 )
    StringIn.Length = 0;
  if ( v9 == 1 )
  {
    v12 = 136LL * v18;
    if ( !(unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))FsLibIsIoAcrossSleep)(
                             v12 + v2 + 3944,
                             v25,
                             (union _LARGE_INTEGER)RefsPerformanceFrequency.QuadPart) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v12 + v2 + 4056));
      _InterlockedIncrement((volatile signed __int32 *)(v12 + v2 + 4060));
      v13 = FsLibTelemetryAddIoFailureTableEntry((int)v2 + 6000, 0, (int)a2, v8, &DestinationString, &StringIn);
      if ( v13 >= 0
        && (*(_DWORD *)(88LL * v13 + *(_QWORD *)(v2 + 6000) + 56) & 0x3FF) == 1
        && (Microsoft_Windows_ReFSEnableBits & 0x100) != 0 )
      {
        McTemplateK0jqzr1tqxqsqzr8qqxxxqd_EtwWriteTransfer(
          UnicodeString.Length >> 1,
          v16,
          StringIn.Length >> 1,
          v2 + 3376,
          UnicodeString.Length >> 1,
          (__int64)UnicodeString.Buffer,
          BYTE1(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 208) + 16LL) + 48LL)) & 1,
          v18,
          *(_QWORD *)(v12 + v2 + 4072),
          (char)ProcessId,
          (__int64)v3,
          StringIn.Length >> 1,
          (__int64)StringIn.Buffer,
          v16,
          v19,
          v23,
          v26,
          *(_QWORD *)a2,
          *((_DWORD *)a2 + 2),
          v13);
      }
    }
  }
  else
  {
    v14 = FsLibTelemetryAddIoFailureTableEntry(
            (int)v2 + 6000,
            (unsigned int)(v7 != 3) + 1,
            (int)a2,
            v8,
            &DestinationString,
            &StringIn);
    if ( v14 >= 0
      && ((*(_DWORD *)(88LL * v14 + *(_QWORD *)(v2 + 6000) + 60) + *(_DWORD *)(88LL * v14 + *(_QWORD *)(v2 + 6000) + 64))
        & 0x3FF) == 1
      && (Microsoft_Windows_ReFSEnableBits & 0x100) != 0 )
    {
      McTemplateK0jqzr1tqqsqzr7qqxxqqd_EtwWriteTransfer(
        *(_QWORD *)(*(_QWORD *)(v2 + 208) + 16LL),
        v16,
        UnicodeString.Length >> 1,
        v2 + 3376,
        UnicodeString.Length >> 1,
        (__int64)UnicodeString.Buffer,
        BYTE1(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 208) + 16LL) + 48LL)) & 1,
        v18,
        (char)ProcessId,
        (__int64)v3,
        StringIn.Length >> 1,
        (__int64)StringIn.Buffer,
        v16,
        v19,
        v23,
        *(_QWORD *)a2,
        *((_DWORD *)a2 + 2),
        v8,
        v14);
    }
  }
  if ( v17[0] )
    RtlFreeUnicodeString(&UnicodeString);
  ExFreePoolWithTag(a2, 0);
  result = ObfDereferenceObject(Object);
  if ( v6 )
    result = ObfDereferenceObject(v6);
  _InterlockedDecrement((volatile signed __int32 *)(v2 + 236));
  _InterlockedDecrement((volatile signed __int32 *)(v2 + 6108));
  return result;
}

```

## disassembly

```asm
0x1c01ca540  mov     [rsp-8+arg_10], rbx
0x1c01ca545  push    rbp
0x1c01ca546  push    rsi
0x1c01ca547  push    rdi
0x1c01ca548  push    r12
0x1c01ca54a  push    r13
0x1c01ca54c  push    r14
0x1c01ca54e  push    r15
0x1c01ca550  lea     rbp, [rsp-50h]
0x1c01ca555  sub     rsp, 170h
0x1c01ca55c  mov     rax, cs:__security_cookie
0x1c01ca563  xor     rax, rsp
0x1c01ca566  mov     [rbp+80h+var_40], rax
0x1c01ca56a  mov     rdi, [rcx+40h]
0x1c01ca56e  lea     r13, File
0x1c01ca575  mov     rsi, rdx
0x1c01ca578  xorps   xmm0, xmm0
0x1c01ca57b  xor     edx, edx
0x1c01ca57d  movups  xmmword ptr [rbp+80h+DestinationString.Length], xmm0
0x1c01ca581  mov     dword ptr [rbp+80h+var_F0+4], edx
0x1c01ca584  mov     rax, [rsi+10h]
0x1c01ca588  mov     rcx, [rsi+30h]
0x1c01ca58c  mov     r14, [rsi+28h]
0x1c01ca590  mov     bl, [rsi+44h]
0x1c01ca593  mov     r12d, [rsi+3Ch]
0x1c01ca597  mov     r15d, [rsi+40h]
0x1c01ca59b  mov     [rbp+80h+var_C8], rax
0x1c01ca59f  mov     rax, [rsi+18h]
0x1c01ca5a3  mov     [rbp+80h+var_B8], rax
0x1c01ca5a7  mov     rax, [rsi+20h]
0x1c01ca5ab  mov     [rbp+80h+var_B0], rax
0x1c01ca5af  mov     eax, [rsi+48h]
0x1c01ca5b2  mov     [rbp+80h+var_FC], eax
0x1c01ca5b5  mov     eax, [rsi+38h]
0x1c01ca5b8  mov     [rbp+80h+var_F8], eax
0x1c01ca5bb  mov     [rbp+80h+var_E0], rdx
0x1c01ca5bf  mov     [rbp+80h+var_FF], dl
0x1c01ca5c2  mov     [rbp+80h+Object], rcx
0x1c01ca5c6  mov     [rbp+80h+var_100], bl
0x1c01ca5c9  movups  xmmword ptr [rbp+80h+UnicodeString.Length], xmm0
0x1c01ca5cd  mov     rax, [rcx+18h]
0x1c01ca5d1  mov     [rbp+80h+var_C0], rax
0x1c01ca5d5  test    r14, r14
0x1c01ca5d8  jz      short loc_1C01CA614
0x1c01ca5da  mov     rcx, r14; Thread
0x1c01ca5dd  call    cs:__imp_PsGetThreadProcess
0x1c01ca5e4  nop     dword ptr [rax+rax+00h]
0x1c01ca5e9  mov     rcx, rax; Process
0x1c01ca5ec  mov     rbx, rax
0x1c01ca5ef  call    cs:__imp_PsGetProcessId
0x1c01ca5f6  nop     dword ptr [rax+rax+00h]
0x1c01ca5fb  mov     rcx, rbx
0x1c01ca5fe  mov     [rbp+80h+var_E0], rax
0x1c01ca602  call    cs:__imp_PsGetProcessImageFileName
0x1c01ca609  nop     dword ptr [rax+rax+00h]
0x1c01ca60e  mov     bl, [rbp+80h+var_100]
0x1c01ca611  mov     r13, rax
0x1c01ca614  mov     rdx, r13; SourceString
0x1c01ca617  lea     rcx, [rbp+80h+DestinationString]; DestinationString
0x1c01ca61b  call    cs:__imp_RtlInitAnsiString
0x1c01ca622  nop     dword ptr [rax+rax+00h]
0x1c01ca627  lea     r9, [rbp+80h+var_FF]
0x1c01ca62b  mov     rdx, rdi
0x1c01ca62e  lea     r8, [rbp+80h+UnicodeString]
0x1c01ca632  xor     ecx, ecx
0x1c01ca634  call    RefsGetVolumeName
0x1c01ca639  mov     r8, [rbp+80h+var_C0]
0x1c01ca63d  lea     rax, [rbp+80h+var_90]
0x1c01ca641  mov     [rbp+80h+var_F0.Buffer], rax
0x1c01ca645  lea     rdx, a016i64x016i64x; "%016I64X %016I64X"
0x1c01ca64c  mov     dword ptr [rbp+80h+var_F0.Length], 420000h
0x1c01ca653  lea     rcx, [rbp+80h+var_F0]; DestinationString
0x1c01ca657  mov     r8, [r8+78h]
0x1c01ca65b  mov     r9, [r8+8]
0x1c01ca65f  mov     r8, [r8+10h]
0x1c01ca663  call    RtlUnicodeStringPrintf
0x1c01ca668  xor     ecx, ecx
0x1c01ca66a  test    eax, eax
0x1c01ca66c  jns     short loc_1C01CA672
0x1c01ca66e  mov     [rbp+80h+var_F0.Length], cx
0x1c01ca672  cmp     r15d, 1
0x1c01ca676  jnz     loc_1C01CA7CF
0x1c01ca67c  mov     eax, [rbp+80h+var_FC]
0x1c01ca67f  lea     rcx, [rdi+0F68h]
0x1c01ca686  mov     r8, qword ptr cs:RefsPerformanceFrequency
0x1c01ca68d  mov     rdx, [rbp+80h+var_B8]
0x1c01ca691  imul    rbx, rax, 88h
0x1c01ca698  add     rcx, rbx
0x1c01ca69b  call    FsLibIsIoAcrossSleep
0x1c01ca6a0  test    al, al
0x1c01ca6a2  jnz     loc_1C01CA8DA
0x1c01ca6a8  lock inc dword ptr [rbx+rdi+0FD8h]
0x1c01ca6b0  lock inc dword ptr [rbx+rdi+0FDCh]
0x1c01ca6b8  lea     rax, [rbp+80h+var_F0]
0x1c01ca6bc  mov     r9d, r12d; int
0x1c01ca6bf  mov     [rsp+1A0h+StringIn], rax; StringIn
0x1c01ca6c4  lea     r15, [rdi+1770h]
0x1c01ca6cb  lea     rax, [rbp+80h+DestinationString]
0x1c01ca6cf  mov     r8, rsi; int
0x1c01ca6d2  xor     edx, edx; int
0x1c01ca6d4  mov     [rsp+1A0h+SourceString], rax; SourceString
0x1c01ca6d9  mov     rcx, r15; int
0x1c01ca6dc  call    FsLibTelemetryAddIoFailureTableEntry
0x1c01ca6e1  movsxd  r11, eax
0x1c01ca6e4  test    r11d, r11d
0x1c01ca6e7  js      loc_1C01CA8DA
0x1c01ca6ed  mov     rcx, [r15]
0x1c01ca6f0  imul    rdx, r11, 58h ; 'X'
0x1c01ca6f4  mov     r8d, [rdx+rcx+38h]
0x1c01ca6f9  and     r8d, 3FFh
0x1c01ca700  cmp     r8d, 1
0x1c01ca704  jnz     loc_1C01CA8DA
0x1c01ca70a  test    byte ptr cs:Microsoft_Windows_ReFSEnableBits+1, r8b
0x1c01ca711  jz      loc_1C01CA8DA
0x1c01ca717  mov     rax, [rdi+0D0h]
0x1c01ca71e  lea     r9, [rdi+0D30h]
0x1c01ca725  movzx   edx, [rbp+80h+var_100]
0x1c01ca729  movzx   r8d, [rbp+80h+var_F0.Length]
0x1c01ca72e  mov     [rsp+1A0h+var_108], r11d
0x1c01ca736  mov     rcx, [rax+10h]
0x1c01ca73a  mov     eax, [rsi+8]
0x1c01ca73d  mov     [rsp+1A0h+var_110], eax
0x1c01ca744  mov     rax, [rsi]
0x1c01ca747  mov     r10d, [rcx+30h]
0x1c01ca74b  movzx   ecx, [rbp+80h+UnicodeString.Length]
0x1c01ca74f  mov     [rsp+1A0h+var_118], rax
0x1c01ca757  mov     rax, [rbp+80h+var_B0]
0x1c01ca75b  mov     [rsp+1A0h+var_120], rax
0x1c01ca763  mov     rax, [rbp+80h+var_C8]
0x1c01ca767  mov     [rsp+1A0h+var_128], rax
0x1c01ca76c  mov     eax, [rbp+80h+var_F8]
0x1c01ca76f  mov     dword ptr [rsp+1A0h+var_130], eax
0x1c01ca773  mov     rax, [rbp+80h+var_F0.Buffer]
0x1c01ca777  mov     [rsp+1A0h+var_138], edx
0x1c01ca77b  mov     [rsp+1A0h+var_140], rax
0x1c01ca780  mov     rax, [rbp+80h+var_E0]
0x1c01ca784  shr     r8d, 1
0x1c01ca787  mov     dword ptr [rsp+1A0h+var_148], r8d
0x1c01ca78c  mov     [rsp+1A0h+var_150], r13
0x1c01ca791  mov     dword ptr [rsp+1A0h+var_158], eax
0x1c01ca795  mov     rax, [rbx+rdi+0FE8h]
0x1c01ca79d  mov     [rsp+1A0h+var_160], rax
0x1c01ca7a2  mov     eax, [rbp+80h+var_FC]
0x1c01ca7a5  mov     [rsp+1A0h+var_168], eax
0x1c01ca7a9  mov     rax, [rbp+80h+UnicodeString.Buffer]
0x1c01ca7ad  shr     r10d, 8
0x1c01ca7b1  and     r10d, 1
0x1c01ca7b5  shr     ecx, 1
0x1c01ca7b7  mov     [rsp+1A0h+var_170], r10d
0x1c01ca7bc  mov     [rsp+1A0h+StringIn], rax
0x1c01ca7c1  mov     dword ptr [rsp+1A0h+SourceString], ecx
0x1c01ca7c5  call    McTemplateK0jqzr1tqxqsqzr8qqxxxqd_EtwWriteTransfer
0x1c01ca7ca  jmp     loc_1C01CA8DA
0x1c01ca7cf  mov     edx, ecx
0x1c01ca7d1  lea     rax, [rbp+80h+var_F0]
0x1c01ca7d5  mov     [rsp+1A0h+StringIn], rax; StringIn
0x1c01ca7da  lea     r15, [rdi+1770h]
0x1c01ca7e1  lea     rax, [rbp+80h+DestinationString]
0x1c01ca7e5  cmp     bl, 3
0x1c01ca7e8  mov     r9d, r12d; int
0x1c01ca7eb  mov     [rsp+1A0h+SourceString], rax; SourceString
0x1c01ca7f0  setnz   dl
0x1c01ca7f3  mov     r8, rsi; int
0x1c01ca7f6  inc     edx; int
0x1c01ca7f8  mov     rcx, r15; int
0x1c01ca7fb  call    FsLibTelemetryAddIoFailureTableEntry
0x1c01ca800  movsxd  rbx, eax
0x1c01ca803  test    ebx, ebx
0x1c01ca805  js      loc_1C01CA8DA
0x1c01ca80b  mov     rcx, [r15]
0x1c01ca80e  imul    rdx, rbx, 58h ; 'X'
0x1c01ca812  mov     r8d, [rdx+rcx+40h]
0x1c01ca817  add     r8d, [rdx+rcx+3Ch]
0x1c01ca81c  and     r8d, 3FFh
0x1c01ca823  cmp     r8d, 1
0x1c01ca827  jnz     loc_1C01CA8DA
0x1c01ca82d  test    byte ptr cs:Microsoft_Windows_ReFSEnableBits+1, r8b
0x1c01ca834  jz      loc_1C01CA8DA
0x1c01ca83a  mov     rax, [rdi+0D0h]
0x1c01ca841  lea     r9, [rdi+0D30h]
0x1c01ca848  movzx   edx, [rbp+80h+var_100]
0x1c01ca84c  movzx   r10d, [rbp+80h+var_F0.Length]
0x1c01ca851  mov     [rsp+1A0h+var_110], ebx
0x1c01ca858  mov     rcx, [rax+10h]
0x1c01ca85c  mov     eax, [rsi+8]
0x1c01ca85f  mov     dword ptr [rsp+1A0h+var_118], r12d
0x1c01ca867  mov     dword ptr [rsp+1A0h+var_120], eax
0x1c01ca86e  mov     rax, [rsi]
0x1c01ca871  mov     r11d, [rcx+30h]
0x1c01ca875  mov     [rsp+1A0h+var_128], rax
0x1c01ca87a  mov     rax, [rbp+80h+var_C8]
0x1c01ca87e  mov     [rsp+1A0h+var_130], rax
0x1c01ca883  mov     eax, [rbp+80h+var_F8]
0x1c01ca886  mov     [rsp+1A0h+var_138], eax
0x1c01ca88a  mov     rax, [rbp+80h+var_F0.Buffer]
0x1c01ca88e  mov     dword ptr [rsp+1A0h+var_140], edx
0x1c01ca892  mov     [rsp+1A0h+var_148], rax
0x1c01ca897  mov     rax, [rbp+80h+var_E0]
0x1c01ca89b  shr     r10d, 1
0x1c01ca89e  mov     dword ptr [rsp+1A0h+var_150], r10d
0x1c01ca8a3  mov     [rsp+1A0h+var_158], r13
0x1c01ca8a8  mov     dword ptr [rsp+1A0h+var_160], eax
0x1c01ca8ac  mov     eax, [rbp+80h+var_FC]
0x1c01ca8af  mov     [rsp+1A0h+var_168], eax
0x1c01ca8b3  mov     rax, [rbp+80h+UnicodeString.Buffer]
0x1c01ca8b7  shr     r11d, 8
0x1c01ca8bb  and     r11d, r8d
0x1c01ca8be  movzx   r8d, [rbp+80h+UnicodeString.Length]
0x1c01ca8c3  mov     [rsp+1A0h+var_170], r11d
0x1c01ca8c8  shr     r8d, 1
0x1c01ca8cb  mov     [rsp+1A0h+StringIn], rax
0x1c01ca8d0  mov     dword ptr [rsp+1A0h+SourceString], r8d
0x1c01ca8d5  call    McTemplateK0jqzr1tqqsqzr7qqxxqqd_EtwWriteTransfer
0x1c01ca8da  xor     ebx, ebx
0x1c01ca8dc  cmp     [rbp+80h+var_FF], bl
0x1c01ca8df  jz      short loc_1C01CA8F1
0x1c01ca8e1  lea     rcx, [rbp+80h+UnicodeString]; UnicodeString
0x1c01ca8e5  call    cs:__imp_RtlFreeUnicodeString
0x1c01ca8ec  nop     dword ptr [rax+rax+00h]
0x1c01ca8f1  xor     edx, edx; Tag
0x1c01ca8f3  mov     rcx, rsi; P
0x1c01ca8f6  call    cs:__imp_ExFreePoolWithTag
0x1c01ca8fd  nop     dword ptr [rax+rax+00h]
0x1c01ca902  mov     rcx, [rbp+80h+Object]; Object
0x1c01ca906  call    cs:__imp_ObfDereferenceObject
0x1c01ca90d  nop     dword ptr [rax+rax+00h]
0x1c01ca912  test    r14, r14
0x1c01ca915  jz      short loc_1C01CA926
0x1c01ca917  mov     rcx, r14; Object
0x1c01ca91a  call    cs:__imp_ObfDereferenceObject
0x1c01ca921  nop     dword ptr [rax+rax+00h]
0x1c01ca926  lock dec dword ptr [rdi+0ECh]
0x1c01ca92d  lock dec dword ptr [rdi+17DCh]
0x1c01ca934  mov     rcx, [rbp+80h+var_40]
0x1c01ca938  xor     rcx, rsp; StackCookie
0x1c01ca93b  call    __security_check_cookie
0x1c01ca940  mov     rbx, [rsp+1A0h+arg_10]
0x1c01ca948  add     rsp, 170h
0x1c01ca94f  pop     r15
0x1c01ca951  pop     r14
0x1c01ca953  pop     r13
0x1c01ca955  pop     r12
0x1c01ca957  pop     rdi
0x1c01ca958  pop     rsi
0x1c01ca959  pop     rbp
0x1c01ca95a  retn
```
