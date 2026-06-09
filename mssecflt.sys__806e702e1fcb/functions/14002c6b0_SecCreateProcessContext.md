# SecCreateProcessContext

- ea: `0x14002c6b0`
- end: `0x14002cdd9`
- name: `SecCreateProcessContext`
- size: `1833`
- prototype: ``
- caller_count: `5`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140021ca0`
- `0x14002d504`
- `0x14002ec70`
- `0x14002f6d0`
- `0x14002f800`

## callees

- `0x140006684`
- `0x14000689c`
- `0x140006b4c`
- `0x140006b6c`
- `0x140008944`
- `0x1400089c4`
- `0x14000add8`
- `0x14000b098`
- `0x14000b1e8`
- `0x14000b4f0`
- `0x140010080`
- `0x1400100a4`
- `0x1400100bc`
- `0x14001041f`
- `0x14001042b`
- `0x140010587`
- `0x140011610`
- `0x140011650`
- `0x1400119c0`
- `0x14002c580`
- `0x14002c6b0`
- `0x14002cddc`
- `0x14002d720`
- `0x14002d9b0`
- `0x14002de60`
- `0x14002e23c`
- `0x14003b390`
- `0x14003b5e4`
- `0x14003b8b4`
- `0x14003b974`
- `0x14003ba0c`
- `0x140040678`
- `0x140040718`
- `0x140041fb0`
- `0x1400420a8`
- `0x1400421bc`
- `0x1400423f8`
- `0x1400424f0`
- `0x140042558`
- `0x1400427ac`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x14002c874`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14002c874`
- `ntoskrnl!ObfReferenceObject` at `0x14002c920`
- `ntoskrnl!ObfReferenceObject` at `0x14002c920`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002c791`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002c791`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002c734`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002c734`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cd6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cd6b`
- `ntoskrnl!ZwClose` at `0x14002cd95`
- `ntoskrnl!ZwClose` at `0x14002cd95`
- `ntoskrnl!ObfDereferenceObject` at `0x14002cd80`
- `ntoskrnl!ObfDereferenceObject` at `0x14002cd80`

## pseudocode

```c
__int64 __fastcall SecCreateProcessContext(struct _SLIST_ENTRY *a1, struct _KPROCESS *a2, __int64 a3, PSLIST_ENTRY *a4)
{
  union _SLIST_HEADER *v7; // rdi
  PSLIST_ENTRY v8; // rbx
  struct _SLIST_ENTRY *v9; // r12
  NTSTATUS ProcessStartKey; // edi
  LONGLONG TimeQuadPart; // rax
  int ProcessSessionId_0; // eax
  HANDLE *v13; // r15
  __int64 v14; // rax
  HANDLE v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdi
  _QWORD **v21; // r8
  _QWORD *v22; // rax
  PSLIST_ENTRY v23; // rsi
  struct _SLIST_ENTRY *v24; // r9
  __int64 v25; // rax
  __int64 v26; // rdx
  PSLIST_ENTRY *v27; // rbx
  __int64 v29; // [rsp+40h] [rbp-29h] BYREF
  PSLIST_ENTRY *v30; // [rsp+48h] [rbp-21h]
  PUNICODE_STRING pImageFileName; // [rsp+50h] [rbp-19h] BYREF
  PVOID Object; // [rsp+58h] [rbp-11h] BYREF
  HANDLE v33; // [rsp+60h] [rbp-9h] BYREF
  struct _SLIST_ENTRY *v34; // [rsp+68h] [rbp-1h] BYREF
  __int64 v35; // [rsp+70h] [rbp+7h]
  __int64 v36; // [rsp+78h] [rbp+Fh] BYREF

  v30 = a4;
  pImageFileName = 0;
  Object = 0;
  v29 = 0;
  v35 = 0;
  v33 = 0;
  v34 = 0;
  v36 = 0;
  if ( (unsigned __int64)&a1[-1].Next + 15 > 0xFFFFFFFFFFFFFFFDuLL )
    return 3221225483LL;
  if ( !a4 || !a2 )
    return 3221225485LL;
  v7 = (union _SLIST_HEADER *)SecProcessTable;
  ++*((_DWORD *)SecProcessTable + 21);
  v8 = ExpInterlockedPopEntrySList(v7 + 4);
  if ( !v8 )
  {
    ++*((_DWORD *)&v7[5].HeaderX64 + 2);
    v8 = (PSLIST_ENTRY)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))v7[7].Alignment)(
                         *((unsigned int *)&v7[6].HeaderX64 + 1),
                         *((unsigned int *)&v7[6].HeaderX64 + 3),
                         *((unsigned int *)&v7[6].HeaderX64 + 2));
  }
  v9 = v8;
  if ( !v8 )
  {
    ProcessStartKey = -1073741670;
    goto LABEL_72;
  }
  memset(v8, 0, 0x2D8u);
  LODWORD(v8->Next) = 47770116;
  v8[2].Next = a1;
  TimeQuadPart = PsGetProcessCreateTimeQuadPart(a2);
  *((_QWORD *)&v8->Next + 1) = 1;
  *((_QWORD *)&v8[2].Next + 1) = TimeQuadPart;
  ProcessSessionId_0 = PsGetProcessSessionId_0(a2);
  LODWORD(v8[38].Next) = 0;
  LODWORD(v8[45].Next) = 0;
  *((_DWORD *)&v8[38].Next + 2) = ProcessSessionId_0;
  *((_QWORD *)&v8[1].Next + 1) = v8 + 1;
  v8[1].Next = v8 + 1;
  FltInitializePushLock_0((PULONG_PTR)&v8[35]);
  LODWORD(v8[21].Next) = -1;
  ProcessStartKey = SecGetProcessStartKey(a2);
  if ( ProcessStartKey >= 0 )
  {
    _mm_lfence();
    if ( (int)SecGetProcessTokenContext((__int64)a2, (__int64)(&v8[14].Next + 1)) < 0 )
      *((_DWORD *)&v8[16].Next + 2) = -1;
    SecGetProcessSecurityDescriptorDacl(a2, &v8[24].Next + 1, 0, 0);
    if ( *((_DWORD *)&v8[16].Next + 2) == 0x4000 )
      HIDWORD(v8[38].Next) |= 8u;
    v13 = (HANDLE *)(&v8[37].Next + 1);
    ProcessStartKey = ObOpenObjectByPointer(a2, 0x200u, 0, 0, 0, 0, (PHANDLE)&v8[37].Next + 1);
    if ( ProcessStartKey >= 0 )
    {
      _mm_lfence();
      if ( (dword_140020004 & 4) != 0 )
      {
        if ( (int)SecGetProcessMitigationPolicy(*v13) >= 0 )
        {
          v14 = v35;
          LODWORD(v8[38].Next) |= 1u;
          *((_QWORD *)&v8[36].Next + 1) = v14;
        }
        if ( (unsigned __int8)KclIsProtectedProcess(*v13) )
        {
          v15 = *v13;
          HIDWORD(v8[38].Next) |= 0x20u;
          BYTE4(v8[37].Next) = KclGetProtectionLevel(v15);
        }
      }
      ProcessStartKey = SecIsSpecialProcessCase(a1, a2, v8);
      if ( ProcessStartKey >= 0 )
      {
        if ( (HIDWORD(v8[38].Next) & 4) != 0 )
        {
LABEL_36:
          _mm_lfence();
          if ( (int)SecReadProcessCommandLine(*((HANDLE *)&v8[37].Next + 1)) < 0 )
            HIDWORD(v8[38].Next) |= 0x100u;
          if ( (int)SecReadProcessCommandLine(*((HANDLE *)&v8[37].Next + 1)) < 0 )
            HIDWORD(v8[38].Next) |= 0x200u;
          if ( !Object
            || (_mm_lfence(),
                ProcessStartKey = SecCreateProcessFileInformation(a2, Object, pImageFileName, v8),
                ProcessStartKey >= 0) )
          {
            _mm_lfence();
            if ( (unsigned __int8)SecIsProcessCreationAnomaliesEnabled() )
            {
              _mm_lfence();
              SecGetProcessCreationAnomalies(a2, a3, &v8[35].Next + 1);
              SecSetProcessAnomalyBasedLogging(v8);
            }
            if ( byte_14001B73C )
            {
              _mm_lfence();
              if ( (int)SecGetProcessPebStartupInfo(a2, (__int64)&v8[41], (__int64)(&v8[41].Next + 1), (__int64)&v8[43]) >= 0 )
              {
                _mm_lfence();
                SecGetProcessStdIoDeviceTypes(
                  a2,
                  *((_QWORD *)&v8[40].Next + 1),
                  v8[41].Next,
                  *((_QWORD *)&v8[41].Next + 1),
                  &v8[42],
                  (char *)&v8[42].Next + 4,
                  &v8[42].Next + 1);
              }
              v9 = v8;
            }
            LODWORD(v8[45].Next) |= 0x20u;
            if ( (HIDWORD(v8[38].Next) & 0x20) == 0 )
            {
              _mm_lfence();
              if ( !(unsigned __int8)SecIsProcessExcludedTiImpersonation(&v8[11].Next + 1) )
              {
                _mm_lfence();
                if ( (unsigned __int8)SecIsEtwTiImpersonationEnabledForIntegrityLevel(*((unsigned int *)&v8[16].Next + 2)) )
                  LODWORD(v8[45].Next) |= 0x40u;
              }
            }
            if ( (unsigned __int8)SecIsReadWriteTelemetryEnabled(&v8[10].Next + 1) )
              LODWORD(v8[45].Next) |= 3u;
            if ( (unsigned __int8)SecIsTiLocalExecProtectVmByProcessEnabled(&v8[10].Next + 1) )
              LODWORD(v8[45].Next) |= 0x10u;
            SecSetProcessThreatIntelligencePolicy(v8);
            if ( (unsigned __int8)SecProcessHasUserSpace(a2) )
            {
              _mm_lfence();
              v19 = *((_QWORD *)&v8[37].Next + 1);
              HIDWORD(v8[38].Next) |= 0x400u;
              LOBYTE(v18) = a3 != 0;
              if ( (int)SecGetProcessInitialThread(v19, v18, &v33) >= 0 )
              {
                if ( (int)SecGetThreadId(v33, &v34) >= 0 )
                  v8[39].Next = v34;
                if ( (int)SecGetThreadStartAddress(v33, &v36) >= 0 )
                  *((_QWORD *)&v8[39].Next + 1) = v36;
              }
            }
            *((_QWORD *)&v8[44].Next + 1) = SecGetProcessAccessFilters(&v8[10].Next + 1);
            if ( (unsigned __int8)SecShouldMonitorFileOpenByProcess(&v8[10].Next + 1) )
              HIDWORD(v8[38].Next) |= 0x40u;
            v20 = (__int64)v8[3].Next & 0x7F;
            FltAcquirePushLockExclusiveEx_0((char *)SecProcessTable + 8, 0);
            v21 = (_QWORD **)(*((_QWORD *)SecProcessTable + 40) + 16LL * (unsigned int)v20);
            v22 = *v21;
            if ( *v21 == v21 )
            {
LABEL_67:
              v24 = v8 + 1;
              v25 = 16 * v20 + *((_QWORD *)SecProcessTable + 40);
              v26 = *(_QWORD *)v25;
              if ( *(_QWORD *)(*(_QWORD *)v25 + 8LL) != v25 )
                __fastfail(3u);
              _mm_lfence();
              v24->Next = (struct _SLIST_ENTRY *)v26;
              *((_QWORD *)&v8[1].Next + 1) = v25;
              *(_QWORD *)(v26 + 8) = v24;
              *(_QWORD *)v25 = v24;
              _InterlockedIncrement((volatile signed __int32 *)SecProcessTable + 82);
              v9 = 0;
              v23 = v8;
            }
            else
            {
              while ( 1 )
              {
                v23 = (PSLIST_ENTRY)(v22 - 2);
                if ( (struct _SLIST_ENTRY *)v22[4] == v8[3].Next )
                  break;
                v22 = (_QWORD *)*v22;
                if ( v22 == v21 )
                  goto LABEL_67;
              }
            }
            v27 = v30;
            ProcessStartKey = 0;
            SecReferenceProcessContext(v23);
            *v27 = v23;
            FltReleasePushLockEx_0((char *)SecProcessTable + 8, 0);
            if ( !v9 )
              goto LABEL_72;
          }
          goto LABEL_71;
        }
        if ( !a3 || (*(_DWORD *)(a3 + 8) & 2) != 0 )
        {
          _mm_lfence();
          ProcessStartKey = SeLocateProcessImageName_0(a2, &pImageFileName);
          if ( ProcessStartKey >= 0 )
          {
            _mm_lfence();
            if ( (int)PsReferenceProcessFilePointer_0(a2, &Object) < 0 || !Object )
            {
              _mm_lfence();
              ProcessStartKey = SecUnicodeToNullTerminatedUnicode(pImageFileName, &v8[9].Next + 1);
              if ( ProcessStartKey < 0 )
                goto LABEL_71;
              LOBYTE(v8[36].Next) = 0;
            }
            _mm_lfence();
            if ( (int)SecGetProcessInheritedFromUniqueProcessId(*((_QWORD *)&v8[37].Next + 1), &v29) >= 0 )
            {
              _mm_lfence();
              SecCreateParentProcessEntity(v29, *((_QWORD *)&v8[2].Next + 1), 0, &v8[3].Next + 1);
            }
            *(struct _SLIST_ENTRY *)((char *)&v8[6] + 8) = 0;
            *(struct _SLIST_ENTRY *)((char *)&v8[7] + 8) = 0;
            *(struct _SLIST_ENTRY *)((char *)&v8[8] + 8) = 0;
            *((_QWORD *)&v8[6].Next + 1) = -1;
            LODWORD(v8[9].Next) = -1;
            goto LABEL_36;
          }
        }
        else
        {
          ObfReferenceObject(*(PVOID *)(a3 + 40));
          Object = *(PVOID *)(a3 + 40);
          if ( (*(_DWORD *)(a3 + 8) & 1) != 0 && *(_QWORD *)(a3 + 48) )
          {
            pImageFileName = *(PUNICODE_STRING *)(a3 + 48);
LABEL_27:
            _mm_lfence();
            LOBYTE(v16) = 1;
            SecCreateParentProcessEntity(*(_QWORD *)(a3 + 24), *((_QWORD *)&v8[2].Next + 1), v16, &v8[3].Next + 1);
            LOBYTE(v17) = 1;
            SecCreateParentProcessEntity(*(_QWORD *)(a3 + 16), *((_QWORD *)&v8[2].Next + 1), v17, &v8[6].Next + 1);
            goto LABEL_36;
          }
          _mm_lfence();
          ProcessStartKey = SeLocateProcessImageName_0(a2, &pImageFileName);
          if ( ProcessStartKey >= 0 )
            goto LABEL_27;
        }
      }
    }
  }
LABEL_71:
  SecReleaseProcessContext(v9);
LABEL_72:
  if ( pImageFileName && (!a3 || *(PUNICODE_STRING *)(a3 + 48) != pImageFileName) )
    ExFreePoolWithTag(pImageFileName, 0);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( v33 )
    ZwClose(v33);
  return (unsigned int)ProcessStartKey;
}

```

## disassembly

```asm
0x14002c6b0  mov     [rsp-8+arg_0], rbx
0x14002c6b5  push    rbp
0x14002c6b6  push    rsi
0x14002c6b7  push    rdi
0x14002c6b8  push    r12
0x14002c6ba  push    r13
0x14002c6bc  push    r14
0x14002c6be  push    r15
0x14002c6c0  lea     rbp, [rsp-27h]
0x14002c6c5  sub     rsp, 90h
0x14002c6cc  mov     rax, cs:__security_cookie
0x14002c6d3  xor     rax, rsp
0x14002c6d6  mov     [rbp+57h+var_40], rax
0x14002c6da  xor     r15d, r15d
0x14002c6dd  mov     [rbp+57h+var_78], r9
0x14002c6e1  lea     rax, [rcx-1]
0x14002c6e5  mov     [rbp+57h+pImageFileName], r15
0x14002c6e9  mov     [rbp+57h+Object], r15
0x14002c6ed  mov     r14, r8
0x14002c6f0  mov     [rbp+57h+var_80], r15
0x14002c6f4  mov     rsi, rdx
0x14002c6f7  mov     [rbp+57h+var_50], r15
0x14002c6fb  mov     r13, rcx
0x14002c6fe  mov     [rbp+57h+var_60], r15
0x14002c702  mov     [rbp+57h+var_58], r15
0x14002c706  mov     [rbp+57h+var_48], r15
0x14002c70a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002c70e  ja      loc_14002CDAC
0x14002c714  test    r9, r9
0x14002c717  jz      loc_14002CDA5
0x14002c71d  test    rdx, rdx
0x14002c720  jz      loc_14002CDA5
0x14002c726  mov     rdi, cs:SecProcessTable
0x14002c72d  inc     dword ptr [rdi+54h]
0x14002c730  lea     rcx, [rdi+40h]; ListHead
0x14002c734  call    cs:__imp_ExpInterlockedPopEntrySList
0x14002c73b  nop     dword ptr [rax+rax+00h]
0x14002c740  mov     rbx, rax
0x14002c743  test    rax, rax
0x14002c746  jnz     short loc_14002C762
0x14002c748  inc     dword ptr [rdi+58h]
0x14002c74b  mov     edx, [rdi+6Ch]
0x14002c74e  mov     rax, [rdi+70h]
0x14002c752  mov     r8d, [rdi+68h]
0x14002c756  mov     ecx, [rdi+64h]
0x14002c759  call    cs:__guard_dispatch_icall_fptr
0x14002c75f  mov     rbx, rax
0x14002c762  mov     r12, rbx
0x14002c765  test    rbx, rbx
0x14002c768  jnz     short loc_14002C774
0x14002c76a  mov     edi, 0C000009Ah
0x14002c76f  jmp     loc_14002CD55
0x14002c774  xor     edx, edx; Val
0x14002c776  mov     r8d, 2D8h; Size
0x14002c77c  mov     rcx, rbx; void *
0x14002c77f  call    memset
0x14002c784  mov     rcx, rsi; Process
0x14002c787  mov     dword ptr [rbx], 2D8EA04h
0x14002c78d  mov     [rbx+20h], r13
0x14002c791  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14002c798  nop     dword ptr [rax+rax+00h]
0x14002c79d  mov     rcx, rsi
0x14002c7a0  mov     qword ptr [rbx+8], 1
0x14002c7a8  mov     [rbx+28h], rax
0x14002c7ac  call    PsGetProcessSessionId_0
0x14002c7b1  mov     [rbx+260h], r15d
0x14002c7b8  lea     rcx, [rbx+230h]; PushLock
0x14002c7bf  mov     [rbx+2D0h], r15d
0x14002c7c6  mov     [rbx+268h], eax
0x14002c7cc  lea     rax, [rbx+10h]
0x14002c7d0  mov     [rax+8], rax
0x14002c7d4  mov     [rax], rax
0x14002c7d7  call    FltInitializePushLock_0
0x14002c7dc  lea     rdx, [rbx+30h]
0x14002c7e0  mov     dword ptr [rbx+150h], 0FFFFFFFFh
0x14002c7ea  mov     rcx, rsi; Process
0x14002c7ed  call    SecGetProcessStartKey
0x14002c7f2  mov     edi, eax
0x14002c7f4  test    eax, eax
0x14002c7f6  js      loc_14002CD4D
0x14002c7fc  lfence
0x14002c7ff  lea     rdx, [rbx+0E8h]
0x14002c806  mov     rcx, rsi
0x14002c809  call    SecGetProcessTokenContext
0x14002c80e  test    eax, eax
0x14002c810  jns     short loc_14002C81C
0x14002c812  mov     dword ptr [rbx+108h], 0FFFFFFFFh
0x14002c81c  lea     rdx, [rbx+188h]
0x14002c823  xor     r9d, r9d
0x14002c826  xor     r8d, r8d
0x14002c829  mov     rcx, rsi
0x14002c82c  call    SecGetProcessSecurityDescriptorDacl
0x14002c831  cmp     dword ptr [rbx+108h], 4000h
0x14002c83b  jnz     short loc_14002C84C
0x14002c83d  mov     eax, [rbx+264h]
0x14002c843  or      eax, 8
0x14002c846  mov     [rbx+264h], eax
0x14002c84c  lea     r15, [rbx+258h]
0x14002c853  xor     r9d, r9d; DesiredAccess
0x14002c856  mov     [rsp+0C0h+Handle], r15; Handle
0x14002c85b  xor     r8d, r8d; PassedAccessState
0x14002c85e  mov     [rsp+0C0h+AccessMode], 0; AccessMode
0x14002c863  mov     edx, 200h; HandleAttributes
0x14002c868  mov     rcx, rsi; Object
0x14002c86b  mov     [rsp+0C0h+ObjectType], 0; ObjectType
0x14002c874  call    cs:__imp_ObOpenObjectByPointer
0x14002c87b  nop     dword ptr [rax+rax+00h]
0x14002c880  mov     edi, eax
0x14002c882  test    eax, eax
0x14002c884  js      loc_14002CD4D
0x14002c88a  lfence
0x14002c88d  mov     eax, cs:dword_140020004
0x14002c893  test    al, 4
0x14002c895  jz      short loc_14002C8E2
0x14002c897  mov     rcx, [r15]; ProcessHandle
0x14002c89a  lea     rdx, [rbp+57h+var_50]
0x14002c89e  call    SecGetProcessMitigationPolicy
0x14002c8a3  test    eax, eax
0x14002c8a5  js      short loc_14002C8B9
0x14002c8a7  mov     rax, [rbp+57h+var_50]
0x14002c8ab  or      dword ptr [rbx+260h], 1
0x14002c8b2  mov     [rbx+248h], rax
0x14002c8b9  mov     rcx, [r15]
0x14002c8bc  call    KclIsProtectedProcess
0x14002c8c1  test    al, al
0x14002c8c3  jz      short loc_14002C8E2
0x14002c8c5  mov     eax, [rbx+264h]
0x14002c8cb  mov     rcx, [r15]; ProcessHandle
0x14002c8ce  or      eax, 20h
0x14002c8d1  mov     [rbx+264h], eax
0x14002c8d7  call    KclGetProtectionLevel
0x14002c8dc  mov     [rbx+254h], al
0x14002c8e2  mov     r8, rbx
0x14002c8e5  mov     rdx, rsi
0x14002c8e8  mov     rcx, r13
0x14002c8eb  call    SecIsSpecialProcessCase
0x14002c8f0  xor     r15d, r15d
0x14002c8f3  mov     edi, eax
0x14002c8f5  test    eax, eax
0x14002c8f7  js      loc_14002CD4D
0x14002c8fd  mov     eax, [rbx+264h]
0x14002c903  test    al, 4
0x14002c905  jnz     loc_14002CA3C
0x14002c90b  test    r14, r14
0x14002c90e  jz      loc_14002C994
0x14002c914  mov     eax, [r14+8]
0x14002c918  test    al, 2
0x14002c91a  jnz     short loc_14002C994
0x14002c91c  mov     rcx, [r14+28h]; Object
0x14002c920  call    cs:__imp_ObfReferenceObject
0x14002c927  nop     dword ptr [rax+rax+00h]
0x14002c92c  mov     rax, [r14+28h]
0x14002c930  mov     [rbp+57h+Object], rax
0x14002c934  mov     eax, [r14+8]
0x14002c938  test    al, 1
0x14002c93a  jz      short loc_14002C94B
0x14002c93c  mov     rax, [r14+30h]
0x14002c940  test    rax, rax
0x14002c943  jz      short loc_14002C94B
0x14002c945  mov     [rbp+57h+pImageFileName], rax
0x14002c949  jmp     short loc_14002C964
0x14002c94b  lfence
0x14002c94e  lea     rdx, [rbp+57h+pImageFileName]; pImageFileName
0x14002c952  mov     rcx, rsi; Process
0x14002c955  call    SeLocateProcessImageName_0
0x14002c95a  mov     edi, eax
0x14002c95c  test    eax, eax
0x14002c95e  js      loc_14002CD4D
0x14002c964  lfence
0x14002c967  mov     rdx, [rbx+28h]
0x14002c96b  lea     r9, [rbx+38h]
0x14002c96f  mov     rcx, [r14+18h]
0x14002c973  mov     r8b, 1
0x14002c976  call    SecCreateParentProcessEntity
0x14002c97b  mov     rdx, [rbx+28h]
0x14002c97f  lea     r9, [rbx+68h]
0x14002c983  mov     rcx, [r14+10h]
0x14002c987  mov     r8b, 1
0x14002c98a  call    SecCreateParentProcessEntity
0x14002c98f  jmp     loc_14002CA3C
0x14002c994  lfence
0x14002c997  lea     rdx, [rbp+57h+pImageFileName]; pImageFileName
0x14002c99b  mov     rcx, rsi; Process
0x14002c99e  call    SeLocateProcessImageName_0
0x14002c9a3  mov     edi, eax
0x14002c9a5  test    eax, eax
0x14002c9a7  js      loc_14002CD4D
0x14002c9ad  lfence
0x14002c9b0  lea     rdx, [rbp+57h+Object]
0x14002c9b4  mov     rcx, rsi
0x14002c9b7  call    PsReferenceProcessFilePointer_0
0x14002c9bc  test    eax, eax
0x14002c9be  js      short loc_14002C9C6
0x14002c9c0  cmp     [rbp+57h+Object], r15
0x14002c9c4  jnz     short loc_14002C9EA
0x14002c9c6  lfence
0x14002c9c9  mov     rcx, [rbp+57h+pImageFileName]
0x14002c9cd  lea     rdx, [rbx+98h]
0x14002c9d4  call    SecUnicodeToNullTerminatedUnicode
0x14002c9d9  mov     edi, eax
0x14002c9db  test    eax, eax
0x14002c9dd  js      loc_14002CD4D
0x14002c9e3  mov     [rbx+240h], r15b
0x14002c9ea  lfence
0x14002c9ed  mov     rcx, [rbx+258h]
0x14002c9f4  lea     rdx, [rbp+57h+var_80]
0x14002c9f8  call    SecGetProcessInheritedFromUniqueProcessId
0x14002c9fd  test    eax, eax
0x14002c9ff  js      short loc_14002CA18
0x14002ca01  lfence
0x14002ca04  mov     rdx, [rbx+28h]
0x14002ca08  lea     r9, [rbx+38h]
0x14002ca0c  mov     rcx, [rbp+57h+var_80]
0x14002ca10  xor     r8d, r8d
0x14002ca13  call    SecCreateParentProcessEntity
0x14002ca18  xorps   xmm0, xmm0
0x14002ca1b  movups  xmmword ptr [rbx+68h], xmm0
0x14002ca1f  movups  xmmword ptr [rbx+78h], xmm0
0x14002ca23  movups  xmmword ptr [rbx+88h], xmm0
0x14002ca2a  mov     qword ptr [rbx+68h], 0FFFFFFFFFFFFFFFFh
0x14002ca32  mov     dword ptr [rbx+90h], 0FFFFFFFFh
0x14002ca3c  lfence
0x14002ca3f  mov     rcx, [rbx+258h]; ProcessHandle
0x14002ca46  lea     rdx, [rbx+0E0h]
0x14002ca4d  call    SecReadProcessCommandLine
0x14002ca52  test    eax, eax
0x14002ca54  jns     short loc_14002CA66
0x14002ca56  mov     eax, [rbx+264h]
0x14002ca5c  bts     eax, 8
0x14002ca60  mov     [rbx+264h], eax
0x14002ca66  mov     rcx, [rbx+258h]; ProcessHandle
0x14002ca6d  lea     rdx, [rbx+228h]
0x14002ca74  call    SecReadProcessCommandLine
0x14002ca79  test    eax, eax
0x14002ca7b  jns     short loc_14002CA8D
0x14002ca7d  mov     eax, [rbx+264h]
0x14002ca83  bts     eax, 9
0x14002ca87  mov     [rbx+264h], eax
0x14002ca8d  cmp     [rbp+57h+Object], r15
0x14002ca91  jz      short loc_14002CAB3
0x14002ca93  lfence
0x14002ca96  mov     r8, [rbp+57h+pImageFileName]
0x14002ca9a  mov     r9, rbx
0x14002ca9d  mov     rdx, [rbp+57h+Object]
0x14002caa1  mov     rcx, rsi
0x14002caa4  call    SecCreateProcessFileInformation
0x14002caa9  mov     edi, eax
0x14002caab  test    eax, eax
0x14002caad  js      loc_14002CD4D
0x14002cab3  lfence
0x14002cab6  call    SecIsProcessCreationAnomaliesEnabled
0x14002cabb  test    al, al
0x14002cabd  jz      short loc_14002CADC
0x14002cabf  lfence
0x14002cac2  lea     r8, [rbx+238h]
0x14002cac9  mov     rdx, r14
0x14002cacc  mov     rcx, rsi
0x14002cacf  call    SecGetProcessCreationAnomalies
0x14002cad4  mov     rcx, rbx
0x14002cad7  call    SecSetProcessAnomalyBasedLogging
0x14002cadc  cmp     cs:byte_14001B73C, r15b
0x14002cae3  jz      loc_14002CB73
0x14002cae9  lfence
0x14002caec  lea     rax, [rbx+2B0h]
0x14002caf3  mov     rcx, rsi; PROCESS
0x14002caf6  mov     [rsp+0C0h+Handle], rax; __int64
0x14002cafb  lea     rdi, [rbx+298h]
0x14002cb02  lea     r12, [rbx+288h]
0x14002cb09  mov     qword ptr [rsp+0C0h+AccessMode], rdi; __int64
0x14002cb0e  lea     r15, [rbx+290h]
0x14002cb15  mov     r9, r12
0x14002cb18  lea     r8, [rbx+284h]
0x14002cb1f  mov     [rsp+0C0h+ObjectType], r15; __int64
0x14002cb24  lea     rdx, [rbx+280h]
0x14002cb2b  call    SecGetProcessPebStartupInfo
0x14002cb30  test    eax, eax
0x14002cb32  js      short loc_14002CB6D
0x14002cb34  lfence
0x14002cb37  mov     r9, [rdi]
0x14002cb3a  lea     rax, [rbx+2A8h]
0x14002cb41  mov     r8, [r15]
0x14002cb44  lea     rcx, [rbx+2A4h]
0x14002cb4b  mov     rdx, [r12]
0x14002cb4f  lea     r10, [rbx+2A0h]
0x14002cb56  mov     [rsp+0C0h+Handle], rax
0x14002cb5b  mov     qword ptr [rsp+0C0h+AccessMode], rcx
0x14002cb60  mov     rcx, rsi
0x14002cb63  mov     [rsp+0C0h+ObjectType], r10
0x14002cb68  call    SecGetProcessStdIoDeviceTypes
0x14002cb6d  xor     r15d, r15d
0x14002cb70  mov     r12, rbx
0x14002cb73  or      dword ptr [rbx+2D0h], 20h
0x14002cb7a  mov     eax, [rbx+264h]
0x14002cb80  test    al, 20h
0x14002cb82  jnz     short loc_14002CBB0
0x14002cb84  lfence
0x14002cb87  lea     rcx, [rbx+0B8h]
0x14002cb8e  call    SecIsProcessExcludedTiImpersonation
0x14002cb93  test    al, al
0x14002cb95  jnz     short loc_14002CBB0
  ... truncated ...
```
