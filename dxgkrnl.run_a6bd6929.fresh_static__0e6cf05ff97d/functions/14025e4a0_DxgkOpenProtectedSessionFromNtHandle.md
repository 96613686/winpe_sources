# DxgkOpenProtectedSessionFromNtHandle

- ea: `0x14025e4a0`
- end: `0x14025ea3c`
- name: `DxgkOpenProtectedSessionFromNtHandle`
- size: `1436`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140012cd4`
- `0x140013a20`
- `0x14001b9c0`
- `0x14001bea0`
- `0x14001d214`
- `0x1400674c4`
- `0x1401cb358`
- `0x1401e76e0`
- `0x14025d1a8`
- `0x14025e4a0`
- `0x14032a5c4`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14025e93c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14025e93c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14025e930`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14025e930`
- `ntoskrnl!ObfDereferenceObject` at `0x14025e859`
- `ntoskrnl!ObfDereferenceObject` at `0x14025e9ca`
- `ntoskrnl!ObfDereferenceObject` at `0x14025e859`
- `ntoskrnl!ObfDereferenceObject` at `0x14025e9ca`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14025e65b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14025e65b`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14025e514`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14025e514`
- `watchdog!WdLogSingleEntry2` at `0x14025e683`
- `watchdog!WdLogSingleEntry2` at `0x14025e6dc`
- `watchdog!WdLogSingleEntry2` at `0x14025e7cb`
- `watchdog!WdLogSingleEntry2` at `0x14025e98d`
- `watchdog!WdLogSingleEntry2` at `0x14025e683`
- `watchdog!WdLogSingleEntry2` at `0x14025e6dc`
- `watchdog!WdLogSingleEntry2` at `0x14025e7cb`
- `watchdog!WdLogSingleEntry2` at `0x14025e98d`
- `watchdog!WdLogSingleEntry0` at `0x14025e529`
- `watchdog!WdLogSingleEntry0` at `0x14025e711`
- `watchdog!WdLogSingleEntry0` at `0x14025e777`
- `watchdog!WdLogSingleEntry0` at `0x14025e7f1`
- `watchdog!WdLogSingleEntry0` at `0x14025e8d3`
- `watchdog!WdLogSingleEntry0` at `0x14025e529`
- `watchdog!WdLogSingleEntry0` at `0x14025e711`
- `watchdog!WdLogSingleEntry0` at `0x14025e777`
- `watchdog!WdLogSingleEntry0` at `0x14025e7f1`
- `watchdog!WdLogSingleEntry0` at `0x14025e8d3`
- `watchdog!WdLogSingleEntry1` at `0x14025e58e`
- `watchdog!WdLogSingleEntry1` at `0x14025e9e7`
- `watchdog!WdLogSingleEntry1` at `0x14025e58e`
- `watchdog!WdLogSingleEntry1` at `0x14025e9e7`

## string_xrefs

- `0x14025e559`: `PsGetCurrentThreadPreviousMode() == UserMode`
- `0x14025e821`: `KMOpenProtectedSessionFromNtHandle.hHandle`
- `0x14025e7a7`: `NULL == KMOpenProtectedSessionFromNtHandle.hHandle`

## pseudocode

```c
__int64 __fastcall DxgkOpenProtectedSessionFromNtHandle(char *Src, __int64 a2, __int64 a3)
{
  struct DXGPROCESS *Current; // r13
  unsigned int v5; // esi
  __int64 v6; // rcx
  __int64 v7; // r8
  NTSTATUS v9; // eax
  __int64 v10; // r14
  __int64 v11; // rcx
  __int64 v12; // r8
  DXGPROTECTEDSESSION **v13; // rsi
  int v14; // eax
  unsigned __int64 v15; // rsi
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // rsi
  __int64 v19; // rcx
  __int64 v20; // r8
  HANDLE Handle[2]; // [rsp+50h] [rbp-58h] BYREF
  unsigned int v22; // [rsp+60h] [rbp-48h] BYREF
  __int64 v23; // [rsp+68h] [rbp-40h]
  char v24; // [rsp+70h] [rbp-38h]
  PVOID Object; // [rsp+B8h] [rbp+10h] BYREF
  struct _OBJECT_HANDLE_INFORMATION HandleInformation; // [rsp+C0h] [rbp+18h] BYREF
  PVOID v28; // [rsp+C8h] [rbp+20h]

  v22 = -1;
  v23 = 0;
  if ( (qword_1401604F0 & 2) != 0 )
  {
    v24 = 1;
    v22 = 2152;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(Src, EventProfilerEnter, a3, 2152);
  }
  else
  {
    v24 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v22, 2152);
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
    WdLogSingleEntry1(2, -1073741811);
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
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v22);
    if ( v24 )
    {
      if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v6, EventProfilerExit, v7, v22);
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
  LODWORD(v10) = -1073741788;
  if ( v9 == -1073741788 )
  {
    WdLogSingleEntry2(3, Handle[0], -1073741788);
    WdLogGlobalForLineNumber = 774;
LABEL_15:
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v22);
    if ( v24 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v11, EventProfilerExit, v12, v22);
    return (unsigned int)v10;
  }
  if ( v9 < 0 )
  {
    WdLogSingleEntry2(3, Handle[0], v9);
    WdLogGlobalForLineNumber = 781;
    goto LABEL_9;
  }
  v13 = (DXGPROTECTEDSESSION **)Object;
  v28 = Object;
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
  v14 = DXGPROTECTEDSESSION::Open(*v13, (unsigned int *)&Handle[1]);
  v10 = v14;
  if ( v14 < 0 )
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
    WdLogSingleEntry2(3, Handle[0], v10);
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
  v15 = LODWORD(Handle[1]);
  DXGPUSHLOCK::AcquireExclusive((struct DXGPROCESS *)((char *)Current + 248));
  v16 = ((unsigned int)v15 >> 6) & 0xFFFFFF;
  if ( (unsigned int)v16 < *((_DWORD *)Current + 74) )
  {
    v17 = *((_QWORD *)Current + 35);
    if ( (((unsigned int)v15 >> 25) & 0x60) == (*(_BYTE *)(v17 + 16 * v16 + 8) & 0x60)
      && (*(_DWORD *)(v17 + 16 * v16 + 8) & 0x1F) != 0 )
    {
      v18 = 16 * ((v15 >> 6) & 0xFFFFFF);
      if ( (*(_DWORD *)(v18 + v17 + 8) & 0x2000) == 0 )
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
      *(_DWORD *)(v18 + *((_QWORD *)Current + 35) + 8) &= ~0x2000u;
    }
  }
  *((_QWORD *)Current + 32) = 0;
  ExReleasePushLockExclusiveEx((char *)Current + 248, 0);
  KeLeaveCriticalRegion();
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v22);
  if ( v24 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v19, EventProfilerExit, v20, v22);
  return 0;
}

```

## disassembly

```asm
0x14025e4a0  mov     [rsp+arg_0], rcx
0x14025e4a5  push    rbx
0x14025e4a6  push    rsi
0x14025e4a7  push    r13
0x14025e4a9  push    r14
0x14025e4ab  sub     rsp, 88h
0x14025e4b2  mov     rsi, rcx
0x14025e4b5  mov     [rsp+0A8h+var_48], 0FFFFFFFFh
0x14025e4bd  xor     ebx, ebx
0x14025e4bf  mov     [rsp+0A8h+var_40], rbx
0x14025e4c4  mov     rax, cs:qword_1401604F0
0x14025e4cb  test    al, 2
0x14025e4cd  jz      short loc_14025E4F9
0x14025e4cf  mov     [rsp+0A8h+var_38], 1
0x14025e4d4  mov     [rsp+0A8h+var_48], 868h
0x14025e4dc  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x14025e4e3  jz      short loc_14025E4FD
0x14025e4e5  mov     r9d, 868h
0x14025e4eb  lea     rdx, EventProfilerEnter
0x14025e4f2  call    McTemplateK0q_EtwWriteTransfer
0x14025e4f7  jmp     short loc_14025E4FD
0x14025e4f9  mov     [rsp+0A8h+var_38], bl
0x14025e4fd  mov     edx, 868h
0x14025e502  lea     rcx, [rsp+0A8h+var_48]
0x14025e507  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x14025e50c  mov     qword ptr [rsp+0A8h+arg_10.HandleAttributes], rbx
0x14025e514  call    cs:__imp_PsGetCurrentThreadPreviousMode
0x14025e51b  nop     dword ptr [rax+rax+00h]
0x14025e520  cmp     al, 1
0x14025e522  jz      short loc_14025E570
0x14025e524  mov     ecx, 1
0x14025e529  call    cs:__imp_WdLogSingleEntry0
0x14025e530  nop     dword ptr [rax+rax+00h]
0x14025e535  mov     eax, 2DAh
0x14025e53a  mov     cs:WdLogGlobalForLineNumber, eax
0x14025e540  mov     [rsp+0A8h+var_68], rbx
0x14025e545  mov     [rsp+0A8h+var_70], rbx
0x14025e54a  mov     [rsp+0A8h+var_78], rbx
0x14025e54f  mov     [rsp+0A8h+HandleInformation], rbx
0x14025e554  mov     [rsp+0A8h+Object], rax
0x14025e559  lea     r9, aPsgetcurrentth; "PsGetCurrentThreadPreviousMode() == Use"...
0x14025e560  or      r8d, 0FFFFFFFFh
0x14025e564  mov     edx, 40002h
0x14025e569  xor     ecx, ecx
0x14025e56b  call    DxgkLogInternalTriageEvent
0x14025e570  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14025e575  mov     r13, rax
0x14025e578  test    rax, rax
0x14025e57b  jnz     loc_14025E605
0x14025e581  mov     rsi, 0FFFFFFFFC000000Dh
0x14025e588  mov     rdx, rsi
0x14025e58b  lea     ecx, [rax+2]
0x14025e58e  call    cs:__imp_WdLogSingleEntry1
0x14025e595  nop     dword ptr [rax+rax+00h]
0x14025e59a  mov     cs:WdLogGlobalForLineNumber, 2E1h
0x14025e5a4  mov     [rsp+0A8h+var_68], rbx
0x14025e5a9  mov     [rsp+0A8h+var_70], rbx
0x14025e5ae  mov     [rsp+0A8h+var_78], rbx
0x14025e5b3  mov     [rsp+0A8h+HandleInformation], rbx
0x14025e5b8  mov     [rsp+0A8h+Object], rsi
0x14025e5bd  lea     r9, aInvalidProcess_4; "Invalid process context, returning 0x%I"...
0x14025e5c4  or      r8d, 0FFFFFFFFh
0x14025e5c8  mov     edx, 40000h
0x14025e5cd  xor     ecx, ecx
0x14025e5cf  call    DxgkLogInternalTriageEvent
0x14025e5d4  lea     rcx, [rsp+0A8h+var_48]; this
0x14025e5d9  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14025e5de  cmp     [rsp+0A8h+var_38], bl
0x14025e5e2  jz      short loc_14025E5FE
0x14025e5e4  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x14025e5eb  jz      short loc_14025E5FE
0x14025e5ed  mov     r9d, [rsp+0A8h+var_48]
0x14025e5f2  lea     rdx, EventProfilerExit
0x14025e5f9  call    McTemplateK0q_EtwWriteTransfer
0x14025e5fe  mov     eax, esi
0x14025e600  jmp     loc_14025EA2D
0x14025e605  xorps   xmm0, xmm0
0x14025e608  movups  xmmword ptr [rsp+0A8h+Handle], xmm0
0x14025e60d  mov     r8d, 10h; Size
0x14025e613  mov     rdx, rsi; Src
0x14025e616  lea     rcx, [rsp+0A8h+Handle]; void *
0x14025e61b  call    RtlCopyFromUser
0x14025e620  nop
0x14025e621  mov     dword ptr [rsp+0A8h+Handle+8], ebx
0x14025e625  mov     r8, cs:g_pDxgkSharedProtectedSessionObjectType; ObjectType
0x14025e62c  mov     [rsp+0A8h+arg_8], rbx
0x14025e634  lea     rax, [rsp+0A8h+arg_10]
0x14025e63c  mov     [rsp+0A8h+HandleInformation], rax; HandleInformation
0x14025e641  lea     rax, [rsp+0A8h+arg_8]
0x14025e649  mov     [rsp+0A8h+Object], rax; Object
0x14025e64e  mov     r9b, 1; AccessMode
0x14025e651  mov     edx, 20000h; DesiredAccess
0x14025e656  mov     rcx, [rsp+0A8h+Handle]; Handle
0x14025e65b  call    cs:__imp_ObReferenceObjectByHandle
0x14025e662  nop     dword ptr [rax+rax+00h]
0x14025e667  movsxd  rsi, eax
0x14025e66a  mov     r14, 0FFFFFFFFC0000024h
0x14025e671  cmp     esi, r14d
0x14025e674  jnz     short loc_14025E6CB
0x14025e676  mov     r8, r14
0x14025e679  mov     rdx, [rsp+0A8h+Handle]
0x14025e67e  mov     ecx, 3
0x14025e683  call    cs:__imp_WdLogSingleEntry2
0x14025e68a  nop     dword ptr [rax+rax+00h]
0x14025e68f  mov     cs:WdLogGlobalForLineNumber, 306h
0x14025e699  lea     rcx, [rsp+0A8h+var_48]; this
0x14025e69e  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14025e6a3  cmp     [rsp+0A8h+var_38], bl
0x14025e6a7  jz      short loc_14025E6C3
0x14025e6a9  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x14025e6b0  jz      short loc_14025E6C3
0x14025e6b2  mov     r9d, [rsp+0A8h+var_48]
0x14025e6b7  lea     rdx, EventProfilerExit
0x14025e6be  call    McTemplateK0q_EtwWriteTransfer
0x14025e6c3  mov     eax, r14d
0x14025e6c6  jmp     loc_14025EA2D
0x14025e6cb  test    eax, eax
0x14025e6cd  jns     short loc_14025E6F7
0x14025e6cf  mov     r8, rsi
0x14025e6d2  mov     rdx, [rsp+0A8h+Handle]
0x14025e6d7  mov     ecx, 3
0x14025e6dc  call    cs:__imp_WdLogSingleEntry2
0x14025e6e3  nop     dword ptr [rax+rax+00h]
0x14025e6e8  mov     cs:WdLogGlobalForLineNumber, 30Dh
0x14025e6f2  jmp     loc_14025E5D4
0x14025e6f7  mov     rsi, [rsp+0A8h+arg_8]
0x14025e6ff  mov     [rsp+0A8h+arg_18], rsi
0x14025e707  cmp     [rsi], rbx
0x14025e70a  jnz     short loc_14025E758
0x14025e70c  mov     ecx, 1
0x14025e711  call    cs:__imp_WdLogSingleEntry0
0x14025e718  nop     dword ptr [rax+rax+00h]
0x14025e71d  mov     eax, 318h
0x14025e722  mov     cs:WdLogGlobalForLineNumber, eax
0x14025e728  mov     [rsp+0A8h+var_68], rbx
0x14025e72d  mov     [rsp+0A8h+var_70], rbx
0x14025e732  mov     [rsp+0A8h+var_78], rbx
0x14025e737  mov     [rsp+0A8h+HandleInformation], rbx
0x14025e73c  mov     [rsp+0A8h+Object], rax
0x14025e741  lea     r9, aPsharedprotect; "pSharedProtectedSessionObject->pProtect"...
0x14025e748  or      r8d, 0FFFFFFFFh
0x14025e74c  mov     edx, 40002h
0x14025e751  xor     ecx, ecx
0x14025e753  call    DxgkLogInternalTriageEvent
0x14025e758  lea     rdx, [rsp+0A8h+Handle+8]; unsigned int *
0x14025e75d  mov     rcx, [rsi]; this
0x14025e760  call    ?Open@DXGPROTECTEDSESSION@@QEAAJPEAI@Z; DXGPROTECTEDSESSION::Open(uint *)
0x14025e765  movsxd  r14, eax
0x14025e768  test    eax, eax
0x14025e76a  jns     short loc_14025E7E6
0x14025e76c  cmp     dword ptr [rsp+0A8h+Handle+8], ebx
0x14025e770  jz      short loc_14025E7BE
0x14025e772  mov     ecx, 1
0x14025e777  call    cs:__imp_WdLogSingleEntry0
0x14025e77e  nop     dword ptr [rax+rax+00h]
0x14025e783  mov     eax, 320h
0x14025e788  mov     cs:WdLogGlobalForLineNumber, eax
0x14025e78e  mov     [rsp+0A8h+var_68], rbx
0x14025e793  mov     [rsp+0A8h+var_70], rbx
0x14025e798  mov     [rsp+0A8h+var_78], rbx
0x14025e79d  mov     [rsp+0A8h+HandleInformation], rbx
0x14025e7a2  mov     [rsp+0A8h+Object], rax
0x14025e7a7  lea     r9, aNullKmopenprot; "NULL == KMOpenProtectedSessionFromNtHan"...
0x14025e7ae  or      r8d, 0FFFFFFFFh
0x14025e7b2  mov     edx, 40002h
0x14025e7b7  xor     ecx, ecx
0x14025e7b9  call    DxgkLogInternalTriageEvent
0x14025e7be  mov     r8, r14
0x14025e7c1  mov     rdx, [rsp+0A8h+Handle]
0x14025e7c6  mov     ecx, 3
0x14025e7cb  call    cs:__imp_WdLogSingleEntry2
0x14025e7d2  nop     dword ptr [rax+rax+00h]
0x14025e7d7  mov     cs:WdLogGlobalForLineNumber, 323h
0x14025e7e1  jmp     loc_14025E9B3
0x14025e7e6  cmp     dword ptr [rsp+0A8h+Handle+8], ebx
0x14025e7ea  jnz     short loc_14025E839
0x14025e7ec  mov     ecx, 1
0x14025e7f1  call    cs:__imp_WdLogSingleEntry0
0x14025e7f8  nop     dword ptr [rax+rax+00h]
0x14025e7fd  mov     eax, 327h
0x14025e802  mov     cs:WdLogGlobalForLineNumber, eax
0x14025e808  mov     [rsp+0A8h+var_68], rbx
0x14025e80d  mov     [rsp+0A8h+var_70], rbx
0x14025e812  mov     [rsp+0A8h+var_78], rbx
0x14025e817  mov     [rsp+0A8h+HandleInformation], rbx
0x14025e81c  mov     [rsp+0A8h+Object], rax
0x14025e821  lea     r9, aKmopenprotecte; "KMOpenProtectedSessionFromNtHandle.hHan"...
0x14025e828  or      r8d, 0FFFFFFFFh
0x14025e82c  mov     edx, 40002h
0x14025e831  xor     ecx, ecx
0x14025e833  call    DxgkLogInternalTriageEvent
0x14025e838  nop
0x14025e839  mov     rcx, [rsp+0A8h+arg_0]
0x14025e841  add     rcx, 8; void *
0x14025e845  mov     r8d, 4; Size
0x14025e84b  lea     rdx, [rsp+0A8h+Handle+8]; Src
0x14025e850  call    RtlCopyToUser
0x14025e855  nop
0x14025e856  mov     rcx, rsi; Object
0x14025e859  call    cs:__imp_ObfDereferenceObject
0x14025e860  nop     dword ptr [rax+rax+00h]
0x14025e865  mov     esi, dword ptr [rsp+0A8h+Handle+8]
0x14025e869  lea     r14, [r13+0F8h]
0x14025e870  mov     rcx, r14; this
0x14025e873  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x14025e878  mov     eax, esi
0x14025e87a  shr     eax, 6
0x14025e87d  mov     r9d, 0FFFFFFh
0x14025e883  and     eax, r9d
0x14025e886  cmp     eax, [r13+128h]
0x14025e88d  jnb     loc_14025E927
0x14025e893  mov     r8, [r13+118h]
0x14025e89a  add     rax, rax
0x14025e89d  mov     edx, [r8+rax*8+8]
0x14025e8a2  mov     ecx, esi
0x14025e8a4  shr     ecx, 19h
0x14025e8a7  and     ecx, 60h
0x14025e8aa  mov     eax, edx
0x14025e8ac  and     eax, 60h
0x14025e8af  cmp     cl, al
0x14025e8b1  jnz     short loc_14025E927
0x14025e8b3  test    dl, 1Fh
0x14025e8b6  jz      short loc_14025E927
0x14025e8b8  shr     rsi, 6
0x14025e8bc  and     rsi, r9
0x14025e8bf  shl     rsi, 4
0x14025e8c3  test    dword ptr [rsi+r8+8], 2000h
0x14025e8cc  jnz     short loc_14025E91A
0x14025e8ce  mov     ecx, 1
0x14025e8d3  call    cs:__imp_WdLogSingleEntry0
0x14025e8da  nop     dword ptr [rax+rax+00h]
0x14025e8df  mov     eax, 0E0h
0x14025e8e4  mov     cs:WdLogGlobalForLineNumber, eax
0x14025e8ea  mov     [rsp+0A8h+var_68], rbx
0x14025e8ef  mov     [rsp+0A8h+var_70], rbx
0x14025e8f4  mov     [rsp+0A8h+var_78], rbx
0x14025e8f9  mov     [rsp+0A8h+HandleInformation], rbx
0x14025e8fe  mov     [rsp+0A8h+Object], rax
0x14025e903  lea     r9, aMPentrytableGe; "m_pEntryTable[GetIndex(hObject)].Destro"...
0x14025e90a  or      r8d, 0FFFFFFFFh
0x14025e90e  mov     edx, 40002h
0x14025e913  xor     ecx, ecx
0x14025e915  call    DxgkLogInternalTriageEvent
0x14025e91a  mov     rax, [r13+118h]
0x14025e921  btr     dword ptr [rsi+rax+8], 0Dh
0x14025e927  mov     [r14+8], rbx
0x14025e92b  xor     edx, edx
0x14025e92d  mov     rcx, r14
0x14025e930  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14025e937  nop     dword ptr [rax+rax+00h]
0x14025e93c  call    cs:__imp_KeLeaveCriticalRegion
0x14025e943  nop     dword ptr [rax+rax+00h]
0x14025e948  lea     rcx, [rsp+0A8h+var_48]; this
0x14025e94d  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14025e952  cmp     [rsp+0A8h+var_38], bl
0x14025e956  jz      short loc_14025E972
0x14025e958  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x14025e95f  jz      short loc_14025E972
0x14025e961  mov     r9d, [rsp+0A8h+var_48]
0x14025e966  lea     rdx, EventProfilerExit
0x14025e96d  call    McTemplateK0q_EtwWriteTransfer
0x14025e972  xor     eax, eax
0x14025e974  jmp     loc_14025EA2D
0x14025e979  mov     r8, 0FFFFFFFFC000000Dh
0x14025e980  mov     rdx, [rsp+0A8h+arg_0]
0x14025e988  mov     ecx, 3
0x14025e98d  call    cs:__imp_WdLogSingleEntry2
0x14025e994  nop     dword ptr [rax+rax+00h]
0x14025e999  mov     cs:WdLogGlobalForLineNumber, 333h
0x14025e9a3  xor     ebx, ebx
0x14025e9a5  mov     r14d, 0C000000Dh
0x14025e9ab  mov     rsi, [rsp+0A8h+arg_18]
0x14025e9b3  mov     edx, dword ptr [rsp+0A8h+Handle+8]; unsigned int
0x14025e9b7  test    edx, edx
0x14025e9b9  jz      short loc_14025E9C7
0x14025e9bb  mov     rcx, [rsi]; this
0x14025e9be  call    ?DestroyProtectedSession@DXGPROTECTEDSESSION@@SAJPEAV1@I@Z; DXGPROTECTEDSESSION::DestroyProtectedSession(DXGPROTECTEDSESSION *,uint)
0x14025e9c3  mov     dword ptr [rsp+0A8h+Handle+8], ebx
0x14025e9c7  mov     rcx, rsi; Object
0x14025e9ca  call    cs:__imp_ObfDereferenceObject
0x14025e9d1  nop     dword ptr [rax+rax+00h]
0x14025e9d6  jmp     loc_14025E699
0x14025e9db  mov     rdx, 0FFFFFFFFC000000Dh
0x14025e9e2  mov     ecx, 3
0x14025e9e7  call    cs:__imp_WdLogSingleEntry1
0x14025e9ee  nop     dword ptr [rax+rax+00h]
0x14025e9f3  mov     cs:WdLogGlobalForLineNumber, 2F1h
0x14025e9fd  lea     rcx, [rsp+0A8h+var_48]; this
0x14025ea02  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14025ea07  cmp     [rsp+0A8h+var_38], 0
0x14025ea0c  jz      short loc_14025EA28
0x14025ea0e  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x14025ea15  jz      short loc_14025EA28
0x14025ea17  mov     r9d, [rsp+0A8h+var_48]
0x14025ea1c  lea     rdx, EventProfilerExit
0x14025ea23  call    McTemplateK0q_EtwWriteTransfer
0x14025ea28  mov     eax, 0C000000Dh
0x14025ea2d  add     rsp, 88h
0x14025ea34  pop     r14
0x14025ea36  pop     r13
  ... truncated ...
```
