# DxgkOpenProtectedSessionFromNtHandle

- ea: `0x140259e50`
- end: `0x14025a3ec`
- name: `DxgkOpenProtectedSessionFromNtHandle`
- size: `1436`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140012b14`
- `0x140013860`
- `0x14001b890`
- `0x14001bd70`
- `0x14001d0e4`
- `0x1400670a4`
- `0x1401c8758`
- `0x1401e5360`
- `0x140258b58`
- `0x140259e50`
- `0x140323854`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14025a2ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14025a2ec`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14025a2e0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14025a2e0`
- `ntoskrnl!ObfDereferenceObject` at `0x14025a209`
- `ntoskrnl!ObfDereferenceObject` at `0x14025a37a`
- `ntoskrnl!ObfDereferenceObject` at `0x14025a209`
- `ntoskrnl!ObfDereferenceObject` at `0x14025a37a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14025a00b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14025a00b`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x140259ec4`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x140259ec4`
- `watchdog!WdLogSingleEntry2` at `0x14025a033`
- `watchdog!WdLogSingleEntry2` at `0x14025a08c`
- `watchdog!WdLogSingleEntry2` at `0x14025a17b`
- `watchdog!WdLogSingleEntry2` at `0x14025a33d`
- `watchdog!WdLogSingleEntry2` at `0x14025a033`
- `watchdog!WdLogSingleEntry2` at `0x14025a08c`
- `watchdog!WdLogSingleEntry2` at `0x14025a17b`
- `watchdog!WdLogSingleEntry2` at `0x14025a33d`
- `watchdog!WdLogSingleEntry0` at `0x140259ed9`
- `watchdog!WdLogSingleEntry0` at `0x14025a0c1`
- `watchdog!WdLogSingleEntry0` at `0x14025a127`
- `watchdog!WdLogSingleEntry0` at `0x14025a1a1`
- `watchdog!WdLogSingleEntry0` at `0x14025a283`
- `watchdog!WdLogSingleEntry0` at `0x140259ed9`
- `watchdog!WdLogSingleEntry0` at `0x14025a0c1`
- `watchdog!WdLogSingleEntry0` at `0x14025a127`
- `watchdog!WdLogSingleEntry0` at `0x14025a1a1`
- `watchdog!WdLogSingleEntry0` at `0x14025a283`
- `watchdog!WdLogSingleEntry1` at `0x140259f3e`
- `watchdog!WdLogSingleEntry1` at `0x14025a397`
- `watchdog!WdLogSingleEntry1` at `0x140259f3e`
- `watchdog!WdLogSingleEntry1` at `0x14025a397`

## string_xrefs

- `0x140259f09`: `PsGetCurrentThreadPreviousMode() == UserMode`
- `0x14025a157`: `NULL == KMOpenProtectedSessionFromNtHandle.hHandle`
- `0x14025a1d1`: `KMOpenProtectedSessionFromNtHandle.hHandle`

## pseudocode

```c
__int64 __fastcall DxgkOpenProtectedSessionFromNtHandle(char *Src, __int64 a2, __int64 a3)
{
  struct DXGPROCESS *Current; // r13
  unsigned int v5; // esi
  __int64 v6; // rcx
  __int64 v7; // r8
  NTSTATUS v9; // eax
  int v10; // r14d
  __int64 v11; // rcx
  __int64 v12; // r8
  DXGPROTECTEDSESSION **v13; // rsi
  unsigned __int64 v14; // rsi
  __int64 v15; // rax
  __int64 v16; // r8
  __int64 v17; // rsi
  __int64 v18; // rcx
  __int64 v19; // r8
  HANDLE Handle[2]; // [rsp+50h] [rbp-58h] BYREF
  unsigned int v21; // [rsp+60h] [rbp-48h] BYREF
  __int64 v22; // [rsp+68h] [rbp-40h]
  char v23; // [rsp+70h] [rbp-38h]
  PVOID Object; // [rsp+B8h] [rbp+10h] BYREF
  struct _OBJECT_HANDLE_INFORMATION HandleInformation; // [rsp+C0h] [rbp+18h] BYREF
  PVOID v27; // [rsp+C8h] [rbp+20h]

  v21 = -1;
  v22 = 0;
  if ( (qword_14015C500 & 2) != 0 )
  {
    v23 = 1;
    v21 = 2152;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(Src, EventProfilerEnter, a3, 2152);
  }
  else
  {
    v23 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v21, 2152);
  HandleInformation = 0;
  if ( (unsigned __int8)PsGetCurrentThreadPreviousMode() != 1 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 730;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"PsGetCurrentThreadPreviousMode() == UserMode",
      730,
      0,
      0,
      0,
      0);
  }
  Current = DXGPROCESS::GetCurrent();
  if ( !Current )
  {
    v5 = -1073741811;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 737;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid process context, returning 0x%I64x",
      -1073741811,
      0,
      0,
      0,
      0);
LABEL_9:
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v21);
    if ( v23 )
    {
      if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v6, EventProfilerExit, v7, v21);
    }
    return v5;
  }
  *(_OWORD *)Handle = 0;
  RtlCopyFromUser(Handle, Src, 0x10u);
  LODWORD(Handle[1]) = 0;
  Object = 0;
  v9 = ObReferenceObjectByHandle(
         Handle[0],
         0x20000u,
         g_pDxgkSharedProtectedSessionObjectType,
         1,
         &Object,
         &HandleInformation);
  v5 = v9;
  v10 = -1073741788;
  if ( v9 == -1073741788 )
  {
    WdLogSingleEntry2(3, Handle[0]);
    WdLogGlobalForLineNumber = 774;
LABEL_15:
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v21);
    if ( v23 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v11, EventProfilerExit, v12, v21);
    return (unsigned int)v10;
  }
  if ( v9 < 0 )
  {
    WdLogSingleEntry2(3, Handle[0]);
    WdLogGlobalForLineNumber = 781;
    goto LABEL_9;
  }
  v13 = (DXGPROTECTEDSESSION **)Object;
  v27 = Object;
  if ( !*(_QWORD *)Object )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 792;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"pSharedProtectedSessionObject->pProtectedSession",
      792,
      0,
      0,
      0,
      0);
  }
  v10 = DXGPROTECTEDSESSION::Open(*v13, (unsigned int *)&Handle[1]);
  if ( v10 < 0 )
  {
    if ( LODWORD(Handle[1]) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 800;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"NULL == KMOpenProtectedSessionFromNtHandle.hHandle",
        800,
        0,
        0,
        0,
        0);
    }
    WdLogSingleEntry2(3, Handle[0]);
    WdLogGlobalForLineNumber = 803;
    if ( LODWORD(Handle[1]) )
    {
      DXGPROTECTEDSESSION::DestroyProtectedSession(*v13, (unsigned int)Handle[1]);
      LODWORD(Handle[1]) = 0;
    }
    ObfDereferenceObject(v13);
    goto LABEL_15;
  }
  if ( !LODWORD(Handle[1]) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 807;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"KMOpenProtectedSessionFromNtHandle.hHandle",
      807,
      0,
      0,
      0,
      0);
  }
  RtlCopyToUser(Src + 8, &Handle[1], 4u);
  ObfDereferenceObject(v13);
  v14 = LODWORD(Handle[1]);
  DXGPUSHLOCK::AcquireExclusive((struct DXGPROCESS *)((char *)Current + 248));
  v15 = ((unsigned int)v14 >> 6) & 0xFFFFFF;
  if ( (unsigned int)v15 < *((_DWORD *)Current + 74) )
  {
    v16 = *((_QWORD *)Current + 35);
    if ( (((unsigned int)v14 >> 25) & 0x60) == (*(_BYTE *)(v16 + 16 * v15 + 8) & 0x60)
      && (*(_DWORD *)(v16 + 16 * v15 + 8) & 0x1F) != 0 )
    {
      v17 = 16 * ((v14 >> 6) & 0xFFFFFF);
      if ( (*(_DWORD *)(v17 + v16 + 8) & 0x2000) == 0 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 224;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"m_pEntryTable[GetIndex(hObject)].Destroyed",
          224,
          0,
          0,
          0,
          0);
      }
      *(_DWORD *)(v17 + *((_QWORD *)Current + 35) + 8) &= ~0x2000u;
    }
  }
  *((_QWORD *)Current + 32) = 0;
  ExReleasePushLockExclusiveEx((char *)Current + 248, 0);
  KeLeaveCriticalRegion();
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v21);
  if ( v23 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v18, EventProfilerExit, v19, v21);
  return 0;
}

```

## disassembly

```asm
0x140259e50  mov     [rsp+arg_0], rcx
0x140259e55  push    rbx
0x140259e56  push    rsi
0x140259e57  push    r13
0x140259e59  push    r14
0x140259e5b  sub     rsp, 88h
0x140259e62  mov     rsi, rcx
0x140259e65  mov     [rsp+0A8h+var_48], 0FFFFFFFFh
0x140259e6d  xor     ebx, ebx
0x140259e6f  mov     [rsp+0A8h+var_40], rbx
0x140259e74  mov     rax, cs:qword_14015C500
0x140259e7b  test    al, 2
0x140259e7d  jz      short loc_140259EA9
0x140259e7f  mov     [rsp+0A8h+var_38], 1
0x140259e84  mov     [rsp+0A8h+var_48], 868h
0x140259e8c  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x140259e93  jz      short loc_140259EAD
0x140259e95  mov     r9d, 868h
0x140259e9b  lea     rdx, EventProfilerEnter
0x140259ea2  call    McTemplateK0q_EtwWriteTransfer
0x140259ea7  jmp     short loc_140259EAD
0x140259ea9  mov     [rsp+0A8h+var_38], bl
0x140259ead  mov     edx, 868h
0x140259eb2  lea     rcx, [rsp+0A8h+var_48]
0x140259eb7  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x140259ebc  mov     qword ptr [rsp+0A8h+arg_10.HandleAttributes], rbx
0x140259ec4  call    cs:__imp_PsGetCurrentThreadPreviousMode
0x140259ecb  nop     dword ptr [rax+rax+00h]
0x140259ed0  cmp     al, 1
0x140259ed2  jz      short loc_140259F20
0x140259ed4  mov     ecx, 1
0x140259ed9  call    cs:__imp_WdLogSingleEntry0
0x140259ee0  nop     dword ptr [rax+rax+00h]
0x140259ee5  mov     eax, 2DAh
0x140259eea  mov     cs:WdLogGlobalForLineNumber, eax
0x140259ef0  mov     [rsp+0A8h+var_68], rbx
0x140259ef5  mov     [rsp+0A8h+var_70], rbx
0x140259efa  mov     [rsp+0A8h+var_78], rbx
0x140259eff  mov     [rsp+0A8h+HandleInformation], rbx
0x140259f04  mov     [rsp+0A8h+Object], rax
0x140259f09  lea     r9, aPsgetcurrentth; "PsGetCurrentThreadPreviousMode() == Use"...
0x140259f10  or      r8d, 0FFFFFFFFh
0x140259f14  mov     edx, 40002h
0x140259f19  xor     ecx, ecx
0x140259f1b  call    DxgkLogInternalTriageEvent
0x140259f20  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140259f25  mov     r13, rax
0x140259f28  test    rax, rax
0x140259f2b  jnz     loc_140259FB5
0x140259f31  mov     rsi, 0FFFFFFFFC000000Dh
0x140259f38  mov     rdx, rsi
0x140259f3b  lea     ecx, [rax+2]
0x140259f3e  call    cs:__imp_WdLogSingleEntry1
0x140259f45  nop     dword ptr [rax+rax+00h]
0x140259f4a  mov     cs:WdLogGlobalForLineNumber, 2E1h
0x140259f54  mov     [rsp+0A8h+var_68], rbx
0x140259f59  mov     [rsp+0A8h+var_70], rbx
0x140259f5e  mov     [rsp+0A8h+var_78], rbx
0x140259f63  mov     [rsp+0A8h+HandleInformation], rbx
0x140259f68  mov     [rsp+0A8h+Object], rsi
0x140259f6d  lea     r9, aInvalidProcess_4; "Invalid process context, returning 0x%I"...
0x140259f74  or      r8d, 0FFFFFFFFh
0x140259f78  mov     edx, 40000h
0x140259f7d  xor     ecx, ecx
0x140259f7f  call    DxgkLogInternalTriageEvent
0x140259f84  lea     rcx, [rsp+0A8h+var_48]; this
0x140259f89  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x140259f8e  cmp     [rsp+0A8h+var_38], bl
0x140259f92  jz      short loc_140259FAE
0x140259f94  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x140259f9b  jz      short loc_140259FAE
0x140259f9d  mov     r9d, [rsp+0A8h+var_48]
0x140259fa2  lea     rdx, EventProfilerExit
0x140259fa9  call    McTemplateK0q_EtwWriteTransfer
0x140259fae  mov     eax, esi
0x140259fb0  jmp     loc_14025A3DD
0x140259fb5  xorps   xmm0, xmm0
0x140259fb8  movups  xmmword ptr [rsp+0A8h+Handle], xmm0
0x140259fbd  mov     r8d, 10h; Size
0x140259fc3  mov     rdx, rsi; Src
0x140259fc6  lea     rcx, [rsp+0A8h+Handle]; void *
0x140259fcb  call    RtlCopyFromUser
0x140259fd0  nop
0x140259fd1  mov     dword ptr [rsp+0A8h+Handle+8], ebx
0x140259fd5  mov     r8, cs:g_pDxgkSharedProtectedSessionObjectType; ObjectType
0x140259fdc  mov     [rsp+0A8h+arg_8], rbx
0x140259fe4  lea     rax, [rsp+0A8h+arg_10]
0x140259fec  mov     [rsp+0A8h+HandleInformation], rax; HandleInformation
0x140259ff1  lea     rax, [rsp+0A8h+arg_8]
0x140259ff9  mov     [rsp+0A8h+Object], rax; Object
0x140259ffe  mov     r9b, 1; AccessMode
0x14025a001  mov     edx, 20000h; DesiredAccess
0x14025a006  mov     rcx, [rsp+0A8h+Handle]; Handle
0x14025a00b  call    cs:__imp_ObReferenceObjectByHandle
0x14025a012  nop     dword ptr [rax+rax+00h]
0x14025a017  movsxd  rsi, eax
0x14025a01a  mov     r14, 0FFFFFFFFC0000024h
0x14025a021  cmp     esi, r14d
0x14025a024  jnz     short loc_14025A07B
0x14025a026  mov     r8, r14
0x14025a029  mov     rdx, [rsp+0A8h+Handle]
0x14025a02e  mov     ecx, 3
0x14025a033  call    cs:__imp_WdLogSingleEntry2
0x14025a03a  nop     dword ptr [rax+rax+00h]
0x14025a03f  mov     cs:WdLogGlobalForLineNumber, 306h
0x14025a049  lea     rcx, [rsp+0A8h+var_48]; this
0x14025a04e  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14025a053  cmp     [rsp+0A8h+var_38], bl
0x14025a057  jz      short loc_14025A073
0x14025a059  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x14025a060  jz      short loc_14025A073
0x14025a062  mov     r9d, [rsp+0A8h+var_48]
0x14025a067  lea     rdx, EventProfilerExit
0x14025a06e  call    McTemplateK0q_EtwWriteTransfer
0x14025a073  mov     eax, r14d
0x14025a076  jmp     loc_14025A3DD
0x14025a07b  test    eax, eax
0x14025a07d  jns     short loc_14025A0A7
0x14025a07f  mov     r8, rsi
0x14025a082  mov     rdx, [rsp+0A8h+Handle]
0x14025a087  mov     ecx, 3
0x14025a08c  call    cs:__imp_WdLogSingleEntry2
0x14025a093  nop     dword ptr [rax+rax+00h]
0x14025a098  mov     cs:WdLogGlobalForLineNumber, 30Dh
0x14025a0a2  jmp     loc_140259F84
0x14025a0a7  mov     rsi, [rsp+0A8h+arg_8]
0x14025a0af  mov     [rsp+0A8h+arg_18], rsi
0x14025a0b7  cmp     [rsi], rbx
0x14025a0ba  jnz     short loc_14025A108
0x14025a0bc  mov     ecx, 1
0x14025a0c1  call    cs:__imp_WdLogSingleEntry0
0x14025a0c8  nop     dword ptr [rax+rax+00h]
0x14025a0cd  mov     eax, 318h
0x14025a0d2  mov     cs:WdLogGlobalForLineNumber, eax
0x14025a0d8  mov     [rsp+0A8h+var_68], rbx
0x14025a0dd  mov     [rsp+0A8h+var_70], rbx
0x14025a0e2  mov     [rsp+0A8h+var_78], rbx
0x14025a0e7  mov     [rsp+0A8h+HandleInformation], rbx
0x14025a0ec  mov     [rsp+0A8h+Object], rax
0x14025a0f1  lea     r9, aPsharedprotect; "pSharedProtectedSessionObject->pProtect"...
0x14025a0f8  or      r8d, 0FFFFFFFFh
0x14025a0fc  mov     edx, 40002h
0x14025a101  xor     ecx, ecx
0x14025a103  call    DxgkLogInternalTriageEvent
0x14025a108  lea     rdx, [rsp+0A8h+Handle+8]; unsigned int *
0x14025a10d  mov     rcx, [rsi]; this
0x14025a110  call    ?Open@DXGPROTECTEDSESSION@@QEAAJPEAI@Z; DXGPROTECTEDSESSION::Open(uint *)
0x14025a115  movsxd  r14, eax
0x14025a118  test    eax, eax
0x14025a11a  jns     short loc_14025A196
0x14025a11c  cmp     dword ptr [rsp+0A8h+Handle+8], ebx
0x14025a120  jz      short loc_14025A16E
0x14025a122  mov     ecx, 1
0x14025a127  call    cs:__imp_WdLogSingleEntry0
0x14025a12e  nop     dword ptr [rax+rax+00h]
0x14025a133  mov     eax, 320h
0x14025a138  mov     cs:WdLogGlobalForLineNumber, eax
0x14025a13e  mov     [rsp+0A8h+var_68], rbx
0x14025a143  mov     [rsp+0A8h+var_70], rbx
0x14025a148  mov     [rsp+0A8h+var_78], rbx
0x14025a14d  mov     [rsp+0A8h+HandleInformation], rbx
0x14025a152  mov     [rsp+0A8h+Object], rax
0x14025a157  lea     r9, aNullKmopenprot; "NULL == KMOpenProtectedSessionFromNtHan"...
0x14025a15e  or      r8d, 0FFFFFFFFh
0x14025a162  mov     edx, 40002h
0x14025a167  xor     ecx, ecx
0x14025a169  call    DxgkLogInternalTriageEvent
0x14025a16e  mov     r8, r14
0x14025a171  mov     rdx, [rsp+0A8h+Handle]
0x14025a176  mov     ecx, 3
0x14025a17b  call    cs:__imp_WdLogSingleEntry2
0x14025a182  nop     dword ptr [rax+rax+00h]
0x14025a187  mov     cs:WdLogGlobalForLineNumber, 323h
0x14025a191  jmp     loc_14025A363
0x14025a196  cmp     dword ptr [rsp+0A8h+Handle+8], ebx
0x14025a19a  jnz     short loc_14025A1E9
0x14025a19c  mov     ecx, 1
0x14025a1a1  call    cs:__imp_WdLogSingleEntry0
0x14025a1a8  nop     dword ptr [rax+rax+00h]
0x14025a1ad  mov     eax, 327h
0x14025a1b2  mov     cs:WdLogGlobalForLineNumber, eax
0x14025a1b8  mov     [rsp+0A8h+var_68], rbx
0x14025a1bd  mov     [rsp+0A8h+var_70], rbx
0x14025a1c2  mov     [rsp+0A8h+var_78], rbx
0x14025a1c7  mov     [rsp+0A8h+HandleInformation], rbx
0x14025a1cc  mov     [rsp+0A8h+Object], rax
0x14025a1d1  lea     r9, aKmopenprotecte; "KMOpenProtectedSessionFromNtHandle.hHan"...
0x14025a1d8  or      r8d, 0FFFFFFFFh
0x14025a1dc  mov     edx, 40002h
0x14025a1e1  xor     ecx, ecx
0x14025a1e3  call    DxgkLogInternalTriageEvent
0x14025a1e8  nop
0x14025a1e9  mov     rcx, [rsp+0A8h+arg_0]
0x14025a1f1  add     rcx, 8; void *
0x14025a1f5  mov     r8d, 4; Size
0x14025a1fb  lea     rdx, [rsp+0A8h+Handle+8]; Src
0x14025a200  call    RtlCopyToUser
0x14025a205  nop
0x14025a206  mov     rcx, rsi; Object
0x14025a209  call    cs:__imp_ObfDereferenceObject
0x14025a210  nop     dword ptr [rax+rax+00h]
0x14025a215  mov     esi, dword ptr [rsp+0A8h+Handle+8]
0x14025a219  lea     r14, [r13+0F8h]
0x14025a220  mov     rcx, r14; this
0x14025a223  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x14025a228  mov     eax, esi
0x14025a22a  shr     eax, 6
0x14025a22d  mov     r9d, 0FFFFFFh
0x14025a233  and     eax, r9d
0x14025a236  cmp     eax, [r13+128h]
0x14025a23d  jnb     loc_14025A2D7
0x14025a243  mov     r8, [r13+118h]
0x14025a24a  add     rax, rax
0x14025a24d  mov     edx, [r8+rax*8+8]
0x14025a252  mov     ecx, esi
0x14025a254  shr     ecx, 19h
0x14025a257  and     ecx, 60h
0x14025a25a  mov     eax, edx
0x14025a25c  and     eax, 60h
0x14025a25f  cmp     cl, al
0x14025a261  jnz     short loc_14025A2D7
0x14025a263  test    dl, 1Fh
0x14025a266  jz      short loc_14025A2D7
0x14025a268  shr     rsi, 6
0x14025a26c  and     rsi, r9
0x14025a26f  shl     rsi, 4
0x14025a273  test    dword ptr [rsi+r8+8], 2000h
0x14025a27c  jnz     short loc_14025A2CA
0x14025a27e  mov     ecx, 1
0x14025a283  call    cs:__imp_WdLogSingleEntry0
0x14025a28a  nop     dword ptr [rax+rax+00h]
0x14025a28f  mov     eax, 0E0h
0x14025a294  mov     cs:WdLogGlobalForLineNumber, eax
0x14025a29a  mov     [rsp+0A8h+var_68], rbx
0x14025a29f  mov     [rsp+0A8h+var_70], rbx
0x14025a2a4  mov     [rsp+0A8h+var_78], rbx
0x14025a2a9  mov     [rsp+0A8h+HandleInformation], rbx
0x14025a2ae  mov     [rsp+0A8h+Object], rax
0x14025a2b3  lea     r9, aMPentrytableGe; "m_pEntryTable[GetIndex(hObject)].Destro"...
0x14025a2ba  or      r8d, 0FFFFFFFFh
0x14025a2be  mov     edx, 40002h
0x14025a2c3  xor     ecx, ecx
0x14025a2c5  call    DxgkLogInternalTriageEvent
0x14025a2ca  mov     rax, [r13+118h]
0x14025a2d1  btr     dword ptr [rsi+rax+8], 0Dh
0x14025a2d7  mov     [r14+8], rbx
0x14025a2db  xor     edx, edx
0x14025a2dd  mov     rcx, r14
0x14025a2e0  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14025a2e7  nop     dword ptr [rax+rax+00h]
0x14025a2ec  call    cs:__imp_KeLeaveCriticalRegion
0x14025a2f3  nop     dword ptr [rax+rax+00h]
0x14025a2f8  lea     rcx, [rsp+0A8h+var_48]; this
0x14025a2fd  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14025a302  cmp     [rsp+0A8h+var_38], bl
0x14025a306  jz      short loc_14025A322
0x14025a308  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x14025a30f  jz      short loc_14025A322
0x14025a311  mov     r9d, [rsp+0A8h+var_48]
0x14025a316  lea     rdx, EventProfilerExit
0x14025a31d  call    McTemplateK0q_EtwWriteTransfer
0x14025a322  xor     eax, eax
0x14025a324  jmp     loc_14025A3DD
0x14025a329  mov     r8, 0FFFFFFFFC000000Dh
0x14025a330  mov     rdx, [rsp+0A8h+arg_0]
0x14025a338  mov     ecx, 3
0x14025a33d  call    cs:__imp_WdLogSingleEntry2
0x14025a344  nop     dword ptr [rax+rax+00h]
0x14025a349  mov     cs:WdLogGlobalForLineNumber, 333h
0x14025a353  xor     ebx, ebx
0x14025a355  mov     r14d, 0C000000Dh
0x14025a35b  mov     rsi, [rsp+0A8h+arg_18]
0x14025a363  mov     edx, dword ptr [rsp+0A8h+Handle+8]; unsigned int
0x14025a367  test    edx, edx
0x14025a369  jz      short loc_14025A377
0x14025a36b  mov     rcx, [rsi]; this
0x14025a36e  call    ?DestroyProtectedSession@DXGPROTECTEDSESSION@@SAJPEAV1@I@Z; DXGPROTECTEDSESSION::DestroyProtectedSession(DXGPROTECTEDSESSION *,uint)
0x14025a373  mov     dword ptr [rsp+0A8h+Handle+8], ebx
0x14025a377  mov     rcx, rsi; Object
0x14025a37a  call    cs:__imp_ObfDereferenceObject
0x14025a381  nop     dword ptr [rax+rax+00h]
0x14025a386  jmp     loc_14025A049
0x14025a38b  mov     rdx, 0FFFFFFFFC000000Dh
0x14025a392  mov     ecx, 3
0x14025a397  call    cs:__imp_WdLogSingleEntry1
0x14025a39e  nop     dword ptr [rax+rax+00h]
0x14025a3a3  mov     cs:WdLogGlobalForLineNumber, 2F1h
0x14025a3ad  lea     rcx, [rsp+0A8h+var_48]; this
0x14025a3b2  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14025a3b7  cmp     [rsp+0A8h+var_38], 0
0x14025a3bc  jz      short loc_14025A3D8
0x14025a3be  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x14025a3c5  jz      short loc_14025A3D8
0x14025a3c7  mov     r9d, [rsp+0A8h+var_48]
0x14025a3cc  lea     rdx, EventProfilerExit
0x14025a3d3  call    McTemplateK0q_EtwWriteTransfer
0x14025a3d8  mov     eax, 0C000000Dh
0x14025a3dd  add     rsp, 88h
0x14025a3e4  pop     r14
0x14025a3e6  pop     r13
  ... truncated ...
```
