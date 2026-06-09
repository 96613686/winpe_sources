# ADAPTER_RENDER::FreeAllocationHandleAndWaitForZeroReferences(DXGALLOCATION *,COREDEVICEACCESS *)

- ea: `0x140320b10`
- end: `0x140320f5d`
- name: `?FreeAllocationHandleAndWaitForZeroReferences@ADAPTER_RENDER@@QEAAXPEAVDXGALLOCATION@@PEAVCOREDEVICEACCESS@@@Z`
- size: `1101`
- prototype: `void(ADAPTER_RENDER *__hidden this, struct DXGALLOCATION *, struct COREDEVICEACCESS *)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14031d938`
- `0x14031e60c`
- `0x14037ab78`

## callees

- `0x140012380`
- `0x14001aadc`
- `0x14001b890`
- `0x14001d0e4`
- `0x1400495f0`
- `0x140310f10`
- `0x140320988`
- `0x140320b10`
- `0x140321260`
- `0x14032152c`
- `0x140321770`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140320b97`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140320b97`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x140320b7a`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x140320b7a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140320b69`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140320b69`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140320bdc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140320bdc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140320bd0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140320bd0`
- `ntoskrnl!KeReadStateEvent` at `0x140320ce9`
- `ntoskrnl!KeReadStateEvent` at `0x140320d34`
- `ntoskrnl!KeReadStateEvent` at `0x140320ce9`
- `ntoskrnl!KeReadStateEvent` at `0x140320d34`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140320c1b`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140320c1b`
- `ntoskrnl!PsGetCurrentProcess` at `0x140320b23`
- `ntoskrnl!PsGetCurrentProcess` at `0x140320b23`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140320c9d`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140320c9d`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140320b32`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140320b32`
- `ntoskrnl!KeWaitForSingleObject` at `0x140320d96`
- `ntoskrnl!KeWaitForSingleObject` at `0x140320dd4`
- `ntoskrnl!KeWaitForSingleObject` at `0x140320d96`
- `ntoskrnl!KeWaitForSingleObject` at `0x140320dd4`
- `watchdog!WdLogSingleEntry0` at `0x140320e29`
- `watchdog!WdLogSingleEntry0` at `0x140320e29`
- `watchdog!WdLogSingleEntry5` at `0x140320e8d`
- `watchdog!WdLogSingleEntry5` at `0x140320ec0`
- `watchdog!WdLogSingleEntry5` at `0x140320ef3`
- `watchdog!WdLogSingleEntry5` at `0x140320f34`
- `watchdog!WdLogSingleEntry5` at `0x140320e8d`
- `watchdog!WdLogSingleEntry5` at `0x140320ec0`
- `watchdog!WdLogSingleEntry5` at `0x140320ef3`
- `watchdog!WdLogSingleEntry5` at `0x140320f34`

## pseudocode

```c
void __fastcall ADAPTER_RENDER::FreeAllocationHandleAndWaitForZeroReferences(
        ADAPTER_RENDER *this,
        struct DXGALLOCATION *a2,
        struct COREDEVICEACCESS *a3)
{
  __int64 CurrentProcess; // rax
  __int64 ProcessDxgProcess; // rax
  struct DXGPROCESS *v7; // rdi
  struct DXGPROCESS *v8; // rbx
  char v9; // di
  __int64 v10; // rcx
  struct _KTHREAD **v11; // rcx
  struct _KTHREAD **v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // r8
  struct DXGTHREAD *Current; // rax
  struct _ETHREAD *CurrentThread; // rbx
  DXGGLOBAL *Global; // rax

  CurrentProcess = PsGetCurrentProcess(this);
  ProcessDxgProcess = PsGetProcessDxgProcess(CurrentProcess);
  v7 = (struct DXGPROCESS *)ProcessDxgProcess;
  if ( ProcessDxgProcess && (*(_DWORD *)(ProcessDxgProcess + 408) & 0x80) == 0 )
    goto LABEL_3;
  Current = DXGTHREAD::GetCurrent();
  if ( !Current )
  {
    CurrentThread = KeGetCurrentThread();
    Global = DXGGLOBAL::GetGlobal();
    v8 = DXGGLOBAL::SearchDxgThreadList(Global, CurrentThread);
    if ( v8 )
      goto LABEL_4;
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 3089;
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Failed to find DXGPROCESS", 3089, 0, 0, 0, 0);
LABEL_3:
    v8 = v7;
    goto LABEL_4;
  }
  v8 = (struct DXGPROCESS *)*((_QWORD *)Current + 3);
  if ( !v8 )
    goto LABEL_3;
LABEL_4:
  KeEnterCriticalRegion();
  if ( !(unsigned __int8)ExTryAcquirePushLockExclusiveEx((char *)v8 + 248, 0) )
  {
    DXGPUSHLOCK::LogEvent((struct DXGPROCESS *)((char *)v8 + 248));
    ExAcquirePushLockExclusiveEx((char *)v8 + 248, 0);
  }
  *((_QWORD *)v8 + 32) = KeGetCurrentThread();
  HMGRTABLE::FreeHandle((struct DXGPROCESS *)((char *)v8 + 280), *((_DWORD *)a2 + 4));
  DxgkUnreferenceDxgAllocation(a2);
  *((_QWORD *)v8 + 32) = 0;
  ExReleasePushLockExclusiveEx((char *)v8 + 248, 0);
  KeLeaveCriticalRegion();
  v9 = 0;
  if ( a3 )
  {
    v10 = *((_QWORD *)a3 + 3);
    if ( KeGetCurrentThread() != *(struct _KTHREAD **)(v10 + 184)
      && !ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(v10 + 168)) )
    {
      v9 = 1;
      if ( !*((_BYTE *)a3 + 32) )
      {
        WdLogSingleEntry5(0, 275, 4, (char *)a3 + 8, 0, 0);
        WdLogGlobalForLineNumber = 7835;
      }
      v11 = (struct _KTHREAD **)*((_QWORD *)a3 + 3);
      *((_BYTE *)a3 + 32) = 0;
      if ( KeGetCurrentThread() != v11[23] )
        DXGADAPTER::ReleaseCoreResource((DXGADAPTER *)v11, *((const char **)a3 + 5));
      *((_QWORD *)a3 + 5) = 0;
      if ( *((_BYTE *)a3 + 144) )
      {
        if ( !*((_BYTE *)a3 + 96) )
        {
          WdLogSingleEntry5(0, 275, 4, (char *)a3 + 72, 0, 0);
          WdLogGlobalForLineNumber = 7835;
        }
        v12 = (struct _KTHREAD **)*((_QWORD *)a3 + 11);
        *((_BYTE *)a3 + 96) = 0;
        if ( KeGetCurrentThread() != v12[23] )
          DXGADAPTER::ReleaseCoreResource((DXGADAPTER *)v12, *((const char **)a3 + 13));
        *((_QWORD *)a3 + 13) = 0;
      }
    }
  }
  ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)a2 + 11);
  if ( v9 )
  {
    if ( *((_BYTE *)a3 + 144) )
    {
      if ( *((_BYTE *)a3 + 96) )
      {
        WdLogSingleEntry5(0, 275, 4, (char *)a3 + 72, 0, 0);
        WdLogGlobalForLineNumber = 7720;
      }
      v13 = *((_QWORD *)a3 + 11);
      if ( KeGetCurrentThread() != *(struct _KTHREAD **)(v13 + 184) )
      {
        if ( !KeReadStateEvent((PRKEVENT)(v13 + 48)) )
        {
          if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
            McTemplateK0q_EtwWriteTransfer(v14, EventBlockThread, v15, 72);
          KeWaitForSingleObject((PVOID)(*((_QWORD *)a3 + 11) + 48LL), Executive, 0, 0, 0);
        }
        DXGADAPTER::AcquireCoreResourceShared(*((DXGADAPTER **)a3 + 11), 0);
      }
      *((_QWORD *)a3 + 13) = 0;
      *((_BYTE *)a3 + 96) = 1;
    }
    if ( *((_BYTE *)a3 + 32) )
    {
      WdLogSingleEntry5(0, 275, 4, (char *)a3 + 8, 0, 0);
      WdLogGlobalForLineNumber = 7720;
    }
    v16 = *((_QWORD *)a3 + 3);
    if ( KeGetCurrentThread() != *(struct _KTHREAD **)(v16 + 184) )
    {
      if ( !KeReadStateEvent((PRKEVENT)(v16 + 48)) )
      {
        if ( bTracingEnabled )
        {
          if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
            McTemplateK0q_EtwWriteTransfer(v17, EventBlockThread, v18, 72);
        }
        KeWaitForSingleObject((PVOID)(*((_QWORD *)a3 + 3) + 48LL), Executive, 0, 0, 0);
      }
      DXGADAPTER::AcquireCoreResourceShared(*((DXGADAPTER **)a3 + 3), 0);
    }
    *((_QWORD *)a3 + 5) = 0;
    *((_BYTE *)a3 + 32) = 1;
  }
}

```

## disassembly

```asm
0x140320b10  push    rbx
0x140320b12  push    rbp
0x140320b13  push    rsi
0x140320b14  push    rdi
0x140320b15  push    r13
0x140320b17  push    r14
0x140320b19  sub     rsp, 58h
0x140320b1d  mov     rsi, r8
0x140320b20  mov     rbp, rdx
0x140320b23  call    cs:__imp_PsGetCurrentProcess
0x140320b2a  nop     dword ptr [rax+rax+00h]
0x140320b2f  mov     rcx, rax
0x140320b32  call    cs:__imp_PsGetProcessDxgProcess
0x140320b39  nop     dword ptr [rax+rax+00h]
0x140320b3e  xor     r14d, r14d
0x140320b41  mov     rdi, rax
0x140320b44  test    rax, rax
0x140320b47  jz      loc_140320DE5
0x140320b4d  mov     ecx, [rax+198h]
0x140320b53  shr     ecx, 7
0x140320b56  test    cl, 1
0x140320b59  jnz     loc_140320DE5
0x140320b5f  mov     rbx, rdi
0x140320b62  lea     rdi, [rbx+0F8h]
0x140320b69  call    cs:__imp_KeEnterCriticalRegion
0x140320b70  nop     dword ptr [rax+rax+00h]
0x140320b75  xor     edx, edx
0x140320b77  mov     rcx, rdi
0x140320b7a  call    cs:__imp_ExTryAcquirePushLockExclusiveEx
0x140320b81  nop     dword ptr [rax+rax+00h]
0x140320b86  test    al, al
0x140320b88  jnz     short loc_140320BA3
0x140320b8a  mov     rcx, rdi; this
0x140320b8d  call    ?LogEvent@DXGPUSHLOCK@@IEAAXXZ; DXGPUSHLOCK::LogEvent(void)
0x140320b92  xor     edx, edx
0x140320b94  mov     rcx, rdi
0x140320b97  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140320b9e  nop     dword ptr [rax+rax+00h]
0x140320ba3  mov     rax, gs:188h
0x140320bac  lea     rcx, [rbx+118h]; this
0x140320bb3  mov     [rdi+8], rax
0x140320bb7  mov     edx, [rbp+10h]; unsigned int
0x140320bba  call    ?FreeHandle@HMGRTABLE@@QEAAXI@Z; HMGRTABLE::FreeHandle(uint)
0x140320bbf  mov     rcx, rbp; struct DXGALLOCATION *
0x140320bc2  call    ?DxgkUnreferenceDxgAllocation@@YAXPEAVDXGALLOCATION@@@Z; DxgkUnreferenceDxgAllocation(DXGALLOCATION *)
0x140320bc7  xor     edx, edx
0x140320bc9  mov     [rdi+8], r14
0x140320bcd  mov     rcx, rdi
0x140320bd0  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140320bd7  nop     dword ptr [rax+rax+00h]
0x140320bdc  call    cs:__imp_KeLeaveCriticalRegion
0x140320be3  nop     dword ptr [rax+rax+00h]
0x140320be8  mov     dil, r14b
0x140320beb  mov     r13d, 4
0x140320bf1  test    rsi, rsi
0x140320bf4  jz      loc_140320C99
0x140320bfa  mov     rcx, [rsi+18h]
0x140320bfe  mov     rax, gs:188h
0x140320c07  cmp     rax, [rcx+0B8h]
0x140320c0e  jz      loc_140320C99
0x140320c14  mov     rcx, [rcx+0A8h]; Resource
0x140320c1b  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x140320c22  nop     dword ptr [rax+rax+00h]
0x140320c27  test    al, al
0x140320c29  jnz     short loc_140320C99
0x140320c2b  mov     dil, 1
0x140320c2e  cmp     [rsi+20h], r14b
0x140320c32  jz      loc_140320E75
0x140320c38  mov     rcx, [rsi+18h]; this
0x140320c3c  mov     [rsi+20h], r14b
0x140320c40  mov     rax, gs:188h
0x140320c49  cmp     rax, [rcx+0B8h]
0x140320c50  jz      short loc_140320C5B
0x140320c52  mov     rdx, [rsi+28h]; char *
0x140320c56  call    ?ReleaseCoreResource@DXGADAPTER@@AEAAXPEBD@Z; DXGADAPTER::ReleaseCoreResource(char const *)
0x140320c5b  mov     [rsi+28h], r14
0x140320c5f  cmp     [rsi+90h], r14b
0x140320c66  jz      short loc_140320C99
0x140320c68  cmp     [rsi+60h], r14b
0x140320c6c  jz      loc_140320EA8
0x140320c72  mov     rcx, [rsi+58h]; this
0x140320c76  mov     [rsi+60h], r14b
0x140320c7a  mov     rax, gs:188h
0x140320c83  cmp     rax, [rcx+0B8h]
0x140320c8a  jz      short loc_140320C95
0x140320c8c  mov     rdx, [rsi+68h]; char *
0x140320c90  call    ?ReleaseCoreResource@DXGADAPTER@@AEAAXPEBD@Z; DXGADAPTER::ReleaseCoreResource(char const *)
0x140320c95  mov     [rsi+68h], r14
0x140320c99  lea     rcx, [rbp+58h]; RunRef
0x140320c9d  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140320ca4  nop     dword ptr [rax+rax+00h]
0x140320ca9  test    dil, dil
0x140320cac  jz      loc_140320D5B
0x140320cb2  mov     edi, 1E28h
0x140320cb7  mov     ebp, 48h ; 'H'
0x140320cbc  cmp     [rsi+90h], r14b
0x140320cc3  jz      short loc_140320D10
0x140320cc5  cmp     [rsi+60h], r14b
0x140320cc9  jnz     loc_140320EDB
0x140320ccf  mov     rcx, [rsi+58h]
0x140320cd3  mov     rax, gs:188h
0x140320cdc  cmp     rax, [rcx+0B8h]
0x140320ce3  jz      short loc_140320D08
0x140320ce5  add     rcx, 30h ; '0'; Event
0x140320ce9  call    cs:__imp_KeReadStateEvent
0x140320cf0  nop     dword ptr [rax+rax+00h]
0x140320cf5  test    eax, eax
0x140320cf7  jz      loc_140320F0A
0x140320cfd  mov     rcx, [rsi+58h]; this
0x140320d01  xor     edx, edx; char *
0x140320d03  call    ?AcquireCoreResourceShared@DXGADAPTER@@AEAAXPEBD@Z; DXGADAPTER::AcquireCoreResourceShared(char const *)
0x140320d08  mov     [rsi+68h], r14
0x140320d0c  mov     byte ptr [rsi+60h], 1
0x140320d10  cmp     [rsi+20h], r14b
0x140320d14  jnz     loc_140320F1C
0x140320d1a  mov     rcx, [rsi+18h]
0x140320d1e  mov     rax, gs:188h
0x140320d27  cmp     rax, [rcx+0B8h]
0x140320d2e  jz      short loc_140320D53
0x140320d30  add     rcx, 30h ; '0'; Event
0x140320d34  call    cs:__imp_KeReadStateEvent
0x140320d3b  nop     dword ptr [rax+rax+00h]
0x140320d40  test    eax, eax
0x140320d42  jz      loc_140320F4B
0x140320d48  mov     rcx, [rsi+18h]; this
0x140320d4c  xor     edx, edx; char *
0x140320d4e  call    ?AcquireCoreResourceShared@DXGADAPTER@@AEAAXPEBD@Z; DXGADAPTER::AcquireCoreResourceShared(char const *)
0x140320d53  mov     [rsi+28h], r14
0x140320d57  mov     byte ptr [rsi+20h], 1
0x140320d5b  add     rsp, 58h
0x140320d5f  pop     r14
0x140320d61  pop     r13
0x140320d63  pop     rdi
0x140320d64  pop     rsi
0x140320d65  pop     rbp
0x140320d66  pop     rbx
0x140320d67  retn
0x140320d69  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x140320d70  jz      short loc_140320D81
0x140320d72  mov     r9d, ebp
0x140320d75  lea     rdx, EventBlockThread
0x140320d7c  call    McTemplateK0q_EtwWriteTransfer
0x140320d81  mov     rcx, [rsi+58h]
0x140320d85  xor     r9d, r9d; Alertable
0x140320d88  add     rcx, 30h ; '0'; Object
0x140320d8c  mov     [rsp+88h+Timeout], r14; Timeout
0x140320d91  xor     r8d, r8d; WaitMode
0x140320d94  xor     edx, edx; WaitReason
0x140320d96  call    cs:__imp_KeWaitForSingleObject
0x140320d9d  nop     dword ptr [rax+rax+00h]
0x140320da2  jmp     loc_140320CFD
0x140320da7  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x140320dae  jz      short loc_140320DBF
0x140320db0  mov     r9d, ebp
0x140320db3  lea     rdx, EventBlockThread
0x140320dba  call    McTemplateK0q_EtwWriteTransfer
0x140320dbf  mov     rcx, [rsi+18h]
0x140320dc3  xor     r9d, r9d; Alertable
0x140320dc6  add     rcx, 30h ; '0'; Object
0x140320dca  mov     [rsp+88h+Timeout], r14; Timeout
0x140320dcf  xor     r8d, r8d; WaitMode
0x140320dd2  xor     edx, edx; WaitReason
0x140320dd4  call    cs:__imp_KeWaitForSingleObject
0x140320ddb  nop     dword ptr [rax+rax+00h]
0x140320de0  jmp     loc_140320D48
0x140320de5  call    ?GetCurrent@DXGTHREAD@@SAPEAV1@XZ; DXGTHREAD::GetCurrent(void)
0x140320dea  test    rax, rax
0x140320ded  jz      short loc_140320E01
0x140320def  mov     rbx, [rax+18h]
0x140320df3  test    rbx, rbx
0x140320df6  jz      loc_140320B5F
0x140320dfc  jmp     loc_140320B62
0x140320e01  mov     rbx, gs:188h
0x140320e0a  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140320e0f  mov     rdx, rbx; struct _ETHREAD *
0x140320e12  mov     rcx, rax; this
0x140320e15  call    ?SearchDxgThreadList@DXGGLOBAL@@QEAAPEAVDXGPROCESS@@PEAU_ETHREAD@@@Z; DXGGLOBAL::SearchDxgThreadList(_ETHREAD *)
0x140320e1a  mov     rbx, rax
0x140320e1d  test    rax, rax
0x140320e20  jnz     loc_140320B62
0x140320e26  lea     ecx, [rax+2]
0x140320e29  call    cs:__imp_WdLogSingleEntry0
0x140320e30  nop     dword ptr [rax+rax+00h]
0x140320e35  mov     [rsp+88h+var_48], r14
0x140320e3a  lea     r9, aFailedToFindDx_0; "Failed to find DXGPROCESS"
0x140320e41  mov     [rsp+88h+var_50], r14
0x140320e46  mov     eax, 0C11h
0x140320e4b  mov     [rsp+88h+var_58], r14
0x140320e50  or      r8d, 0FFFFFFFFh
0x140320e54  mov     [rsp+88h+var_60], r14
0x140320e59  mov     edx, 40000h
0x140320e5e  xor     ecx, ecx
0x140320e60  mov     [rsp+88h+Timeout], rax
0x140320e65  mov     cs:WdLogGlobalForLineNumber, eax
0x140320e6b  call    DxgkLogInternalTriageEvent
0x140320e70  jmp     loc_140320B5F
0x140320e75  mov     [rsp+88h+var_60], r14
0x140320e7a  lea     r9, [rsi+8]
0x140320e7e  mov     r8, r13
0x140320e81  mov     [rsp+88h+Timeout], r14
0x140320e86  mov     edx, 113h
0x140320e8b  xor     ecx, ecx
0x140320e8d  call    cs:__imp_WdLogSingleEntry5
0x140320e94  nop     dword ptr [rax+rax+00h]
0x140320e99  mov     cs:WdLogGlobalForLineNumber, 1E9Bh
0x140320ea3  jmp     loc_140320C38
0x140320ea8  mov     [rsp+88h+var_60], r14
0x140320ead  lea     r9, [rsi+48h]
0x140320eb1  mov     r8, r13
0x140320eb4  mov     [rsp+88h+Timeout], r14
0x140320eb9  mov     edx, 113h
0x140320ebe  xor     ecx, ecx
0x140320ec0  call    cs:__imp_WdLogSingleEntry5
0x140320ec7  nop     dword ptr [rax+rax+00h]
0x140320ecc  mov     cs:WdLogGlobalForLineNumber, 1E9Bh
0x140320ed6  jmp     loc_140320C72
0x140320edb  mov     [rsp+88h+var_60], r14
0x140320ee0  lea     r9, [rsi+48h]
0x140320ee4  mov     r8, r13
0x140320ee7  mov     [rsp+88h+Timeout], r14
0x140320eec  mov     edx, 113h
0x140320ef1  xor     ecx, ecx
0x140320ef3  call    cs:__imp_WdLogSingleEntry5
0x140320efa  nop     dword ptr [rax+rax+00h]
0x140320eff  mov     cs:WdLogGlobalForLineNumber, edi
0x140320f05  jmp     loc_140320CCF
0x140320f0a  cmp     cs:bTracingEnabled, r14b
0x140320f11  jz      loc_140320D81
0x140320f17  jmp     loc_140320D69
0x140320f1c  mov     [rsp+88h+var_60], r14
0x140320f21  lea     r9, [rsi+8]
0x140320f25  mov     r8, r13
0x140320f28  mov     [rsp+88h+Timeout], r14
0x140320f2d  mov     edx, 113h
0x140320f32  xor     ecx, ecx
0x140320f34  call    cs:__imp_WdLogSingleEntry5
0x140320f3b  nop     dword ptr [rax+rax+00h]
0x140320f40  mov     cs:WdLogGlobalForLineNumber, edi
0x140320f46  jmp     loc_140320D1A
0x140320f4b  cmp     cs:bTracingEnabled, r14b
0x140320f52  jz      loc_140320DBF
0x140320f58  jmp     loc_140320DA7
```
