# ADAPTER_RENDER::FreeAllocationHandleAndWaitForZeroReferences(DXGALLOCATION *,COREDEVICEACCESS *)

- ea: `0x140327880`
- end: `0x140327ccd`
- name: `?FreeAllocationHandleAndWaitForZeroReferences@ADAPTER_RENDER@@QEAAXPEAVDXGALLOCATION@@PEAVCOREDEVICEACCESS@@@Z`
- size: `1101`
- prototype: `void(ADAPTER_RENDER *__hidden this, struct DXGALLOCATION *, struct COREDEVICEACCESS *)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1403246a8`
- `0x14032537c`
- `0x1403952cc`

## callees

- `0x140012540`
- `0x14001ac0c`
- `0x14001b9c0`
- `0x14001d214`
- `0x1400497f0`
- `0x140317c80`
- `0x1403276f8`
- `0x140327880`
- `0x140327fd0`
- `0x14032829c`
- `0x1403284e0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140327907`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140327907`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x1403278ea`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x1403278ea`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403278d9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403278d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14032794c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14032794c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140327940`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140327940`
- `ntoskrnl!KeReadStateEvent` at `0x140327a59`
- `ntoskrnl!KeReadStateEvent` at `0x140327aa4`
- `ntoskrnl!KeReadStateEvent` at `0x140327a59`
- `ntoskrnl!KeReadStateEvent` at `0x140327aa4`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14032798b`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14032798b`
- `ntoskrnl!PsGetCurrentProcess` at `0x140327893`
- `ntoskrnl!PsGetCurrentProcess` at `0x140327893`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140327a0d`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140327a0d`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x1403278a2`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x1403278a2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140327b06`
- `ntoskrnl!KeWaitForSingleObject` at `0x140327b44`
- `ntoskrnl!KeWaitForSingleObject` at `0x140327b06`
- `ntoskrnl!KeWaitForSingleObject` at `0x140327b44`
- `watchdog!WdLogSingleEntry0` at `0x140327b99`
- `watchdog!WdLogSingleEntry0` at `0x140327b99`
- `watchdog!WdLogSingleEntry5` at `0x140327bfd`
- `watchdog!WdLogSingleEntry5` at `0x140327c30`
- `watchdog!WdLogSingleEntry5` at `0x140327c63`
- `watchdog!WdLogSingleEntry5` at `0x140327ca4`
- `watchdog!WdLogSingleEntry5` at `0x140327bfd`
- `watchdog!WdLogSingleEntry5` at `0x140327c30`
- `watchdog!WdLogSingleEntry5` at `0x140327c63`
- `watchdog!WdLogSingleEntry5` at `0x140327ca4`

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

  CurrentProcess = PsGetCurrentProcess(this, a2);
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
    WdLogGlobalForLineNumber = 3109;
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Failed to find DXGPROCESS", 3109, 0, 0, 0, 0);
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
        WdLogGlobalForLineNumber = 7839;
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
          WdLogGlobalForLineNumber = 7839;
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
        WdLogGlobalForLineNumber = 7724;
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
      WdLogGlobalForLineNumber = 7724;
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
0x140327880  push    rbx
0x140327882  push    rbp
0x140327883  push    rsi
0x140327884  push    rdi
0x140327885  push    r13
0x140327887  push    r14
0x140327889  sub     rsp, 58h
0x14032788d  mov     rsi, r8
0x140327890  mov     rbp, rdx
0x140327893  call    cs:__imp_PsGetCurrentProcess
0x14032789a  nop     dword ptr [rax+rax+00h]
0x14032789f  mov     rcx, rax
0x1403278a2  call    cs:__imp_PsGetProcessDxgProcess
0x1403278a9  nop     dword ptr [rax+rax+00h]
0x1403278ae  xor     r14d, r14d
0x1403278b1  mov     rdi, rax
0x1403278b4  test    rax, rax
0x1403278b7  jz      loc_140327B55
0x1403278bd  mov     ecx, [rax+198h]
0x1403278c3  shr     ecx, 7
0x1403278c6  test    cl, 1
0x1403278c9  jnz     loc_140327B55
0x1403278cf  mov     rbx, rdi
0x1403278d2  lea     rdi, [rbx+0F8h]
0x1403278d9  call    cs:__imp_KeEnterCriticalRegion
0x1403278e0  nop     dword ptr [rax+rax+00h]
0x1403278e5  xor     edx, edx
0x1403278e7  mov     rcx, rdi
0x1403278ea  call    cs:__imp_ExTryAcquirePushLockExclusiveEx
0x1403278f1  nop     dword ptr [rax+rax+00h]
0x1403278f6  test    al, al
0x1403278f8  jnz     short loc_140327913
0x1403278fa  mov     rcx, rdi; this
0x1403278fd  call    ?LogEvent@DXGPUSHLOCK@@IEAAXXZ; DXGPUSHLOCK::LogEvent(void)
0x140327902  xor     edx, edx
0x140327904  mov     rcx, rdi
0x140327907  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14032790e  nop     dword ptr [rax+rax+00h]
0x140327913  mov     rax, gs:188h
0x14032791c  lea     rcx, [rbx+118h]; this
0x140327923  mov     [rdi+8], rax
0x140327927  mov     edx, [rbp+10h]; unsigned int
0x14032792a  call    ?FreeHandle@HMGRTABLE@@QEAAXI@Z; HMGRTABLE::FreeHandle(uint)
0x14032792f  mov     rcx, rbp; struct DXGALLOCATION *
0x140327932  call    ?DxgkUnreferenceDxgAllocation@@YAXPEAVDXGALLOCATION@@@Z; DxgkUnreferenceDxgAllocation(DXGALLOCATION *)
0x140327937  xor     edx, edx
0x140327939  mov     [rdi+8], r14
0x14032793d  mov     rcx, rdi
0x140327940  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140327947  nop     dword ptr [rax+rax+00h]
0x14032794c  call    cs:__imp_KeLeaveCriticalRegion
0x140327953  nop     dword ptr [rax+rax+00h]
0x140327958  mov     dil, r14b
0x14032795b  mov     r13d, 4
0x140327961  test    rsi, rsi
0x140327964  jz      loc_140327A09
0x14032796a  mov     rcx, [rsi+18h]
0x14032796e  mov     rax, gs:188h
0x140327977  cmp     rax, [rcx+0B8h]
0x14032797e  jz      loc_140327A09
0x140327984  mov     rcx, [rcx+0A8h]; Resource
0x14032798b  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x140327992  nop     dword ptr [rax+rax+00h]
0x140327997  test    al, al
0x140327999  jnz     short loc_140327A09
0x14032799b  mov     dil, 1
0x14032799e  cmp     [rsi+20h], r14b
0x1403279a2  jz      loc_140327BE5
0x1403279a8  mov     rcx, [rsi+18h]; this
0x1403279ac  mov     [rsi+20h], r14b
0x1403279b0  mov     rax, gs:188h
0x1403279b9  cmp     rax, [rcx+0B8h]
0x1403279c0  jz      short loc_1403279CB
0x1403279c2  mov     rdx, [rsi+28h]; char *
0x1403279c6  call    ?ReleaseCoreResource@DXGADAPTER@@AEAAXPEBD@Z; DXGADAPTER::ReleaseCoreResource(char const *)
0x1403279cb  mov     [rsi+28h], r14
0x1403279cf  cmp     [rsi+90h], r14b
0x1403279d6  jz      short loc_140327A09
0x1403279d8  cmp     [rsi+60h], r14b
0x1403279dc  jz      loc_140327C18
0x1403279e2  mov     rcx, [rsi+58h]; this
0x1403279e6  mov     [rsi+60h], r14b
0x1403279ea  mov     rax, gs:188h
0x1403279f3  cmp     rax, [rcx+0B8h]
0x1403279fa  jz      short loc_140327A05
0x1403279fc  mov     rdx, [rsi+68h]; char *
0x140327a00  call    ?ReleaseCoreResource@DXGADAPTER@@AEAAXPEBD@Z; DXGADAPTER::ReleaseCoreResource(char const *)
0x140327a05  mov     [rsi+68h], r14
0x140327a09  lea     rcx, [rbp+58h]; RunRef
0x140327a0d  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140327a14  nop     dword ptr [rax+rax+00h]
0x140327a19  test    dil, dil
0x140327a1c  jz      loc_140327ACB
0x140327a22  mov     edi, 1E2Ch
0x140327a27  mov     ebp, 48h ; 'H'
0x140327a2c  cmp     [rsi+90h], r14b
0x140327a33  jz      short loc_140327A80
0x140327a35  cmp     [rsi+60h], r14b
0x140327a39  jnz     loc_140327C4B
0x140327a3f  mov     rcx, [rsi+58h]
0x140327a43  mov     rax, gs:188h
0x140327a4c  cmp     rax, [rcx+0B8h]
0x140327a53  jz      short loc_140327A78
0x140327a55  add     rcx, 30h ; '0'; Event
0x140327a59  call    cs:__imp_KeReadStateEvent
0x140327a60  nop     dword ptr [rax+rax+00h]
0x140327a65  test    eax, eax
0x140327a67  jz      loc_140327C7A
0x140327a6d  mov     rcx, [rsi+58h]; this
0x140327a71  xor     edx, edx; char *
0x140327a73  call    ?AcquireCoreResourceShared@DXGADAPTER@@AEAAXPEBD@Z; DXGADAPTER::AcquireCoreResourceShared(char const *)
0x140327a78  mov     [rsi+68h], r14
0x140327a7c  mov     byte ptr [rsi+60h], 1
0x140327a80  cmp     [rsi+20h], r14b
0x140327a84  jnz     loc_140327C8C
0x140327a8a  mov     rcx, [rsi+18h]
0x140327a8e  mov     rax, gs:188h
0x140327a97  cmp     rax, [rcx+0B8h]
0x140327a9e  jz      short loc_140327AC3
0x140327aa0  add     rcx, 30h ; '0'; Event
0x140327aa4  call    cs:__imp_KeReadStateEvent
0x140327aab  nop     dword ptr [rax+rax+00h]
0x140327ab0  test    eax, eax
0x140327ab2  jz      loc_140327CBB
0x140327ab8  mov     rcx, [rsi+18h]; this
0x140327abc  xor     edx, edx; char *
0x140327abe  call    ?AcquireCoreResourceShared@DXGADAPTER@@AEAAXPEBD@Z; DXGADAPTER::AcquireCoreResourceShared(char const *)
0x140327ac3  mov     [rsi+28h], r14
0x140327ac7  mov     byte ptr [rsi+20h], 1
0x140327acb  add     rsp, 58h
0x140327acf  pop     r14
0x140327ad1  pop     r13
0x140327ad3  pop     rdi
0x140327ad4  pop     rsi
0x140327ad5  pop     rbp
0x140327ad6  pop     rbx
0x140327ad7  retn
0x140327ad9  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x140327ae0  jz      short loc_140327AF1
0x140327ae2  mov     r9d, ebp
0x140327ae5  lea     rdx, EventBlockThread
0x140327aec  call    McTemplateK0q_EtwWriteTransfer
0x140327af1  mov     rcx, [rsi+58h]
0x140327af5  xor     r9d, r9d; Alertable
0x140327af8  add     rcx, 30h ; '0'; Object
0x140327afc  mov     [rsp+88h+Timeout], r14; Timeout
0x140327b01  xor     r8d, r8d; WaitMode
0x140327b04  xor     edx, edx; WaitReason
0x140327b06  call    cs:__imp_KeWaitForSingleObject
0x140327b0d  nop     dword ptr [rax+rax+00h]
0x140327b12  jmp     loc_140327A6D
0x140327b17  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x140327b1e  jz      short loc_140327B2F
0x140327b20  mov     r9d, ebp
0x140327b23  lea     rdx, EventBlockThread
0x140327b2a  call    McTemplateK0q_EtwWriteTransfer
0x140327b2f  mov     rcx, [rsi+18h]
0x140327b33  xor     r9d, r9d; Alertable
0x140327b36  add     rcx, 30h ; '0'; Object
0x140327b3a  mov     [rsp+88h+Timeout], r14; Timeout
0x140327b3f  xor     r8d, r8d; WaitMode
0x140327b42  xor     edx, edx; WaitReason
0x140327b44  call    cs:__imp_KeWaitForSingleObject
0x140327b4b  nop     dword ptr [rax+rax+00h]
0x140327b50  jmp     loc_140327AB8
0x140327b55  call    ?GetCurrent@DXGTHREAD@@SAPEAV1@XZ; DXGTHREAD::GetCurrent(void)
0x140327b5a  test    rax, rax
0x140327b5d  jz      short loc_140327B71
0x140327b5f  mov     rbx, [rax+18h]
0x140327b63  test    rbx, rbx
0x140327b66  jz      loc_1403278CF
0x140327b6c  jmp     loc_1403278D2
0x140327b71  mov     rbx, gs:188h
0x140327b7a  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140327b7f  mov     rdx, rbx; struct _ETHREAD *
0x140327b82  mov     rcx, rax; this
0x140327b85  call    ?SearchDxgThreadList@DXGGLOBAL@@QEAAPEAVDXGPROCESS@@PEAU_ETHREAD@@@Z; DXGGLOBAL::SearchDxgThreadList(_ETHREAD *)
0x140327b8a  mov     rbx, rax
0x140327b8d  test    rax, rax
0x140327b90  jnz     loc_1403278D2
0x140327b96  lea     ecx, [rax+2]
0x140327b99  call    cs:__imp_WdLogSingleEntry0
0x140327ba0  nop     dword ptr [rax+rax+00h]
0x140327ba5  mov     [rsp+88h+var_48], r14
0x140327baa  lea     r9, aFailedToFindDx_0; "Failed to find DXGPROCESS"
0x140327bb1  mov     [rsp+88h+var_50], r14
0x140327bb6  mov     eax, 0C25h
0x140327bbb  mov     [rsp+88h+var_58], r14
0x140327bc0  or      r8d, 0FFFFFFFFh
0x140327bc4  mov     [rsp+88h+var_60], r14
0x140327bc9  mov     edx, 40000h
0x140327bce  xor     ecx, ecx
0x140327bd0  mov     [rsp+88h+Timeout], rax
0x140327bd5  mov     cs:WdLogGlobalForLineNumber, eax
0x140327bdb  call    DxgkLogInternalTriageEvent
0x140327be0  jmp     loc_1403278CF
0x140327be5  mov     [rsp+88h+var_60], r14
0x140327bea  lea     r9, [rsi+8]
0x140327bee  mov     r8, r13
0x140327bf1  mov     [rsp+88h+Timeout], r14
0x140327bf6  mov     edx, 113h
0x140327bfb  xor     ecx, ecx
0x140327bfd  call    cs:__imp_WdLogSingleEntry5
0x140327c04  nop     dword ptr [rax+rax+00h]
0x140327c09  mov     cs:WdLogGlobalForLineNumber, 1E9Fh
0x140327c13  jmp     loc_1403279A8
0x140327c18  mov     [rsp+88h+var_60], r14
0x140327c1d  lea     r9, [rsi+48h]
0x140327c21  mov     r8, r13
0x140327c24  mov     [rsp+88h+Timeout], r14
0x140327c29  mov     edx, 113h
0x140327c2e  xor     ecx, ecx
0x140327c30  call    cs:__imp_WdLogSingleEntry5
0x140327c37  nop     dword ptr [rax+rax+00h]
0x140327c3c  mov     cs:WdLogGlobalForLineNumber, 1E9Fh
0x140327c46  jmp     loc_1403279E2
0x140327c4b  mov     [rsp+88h+var_60], r14
0x140327c50  lea     r9, [rsi+48h]
0x140327c54  mov     r8, r13
0x140327c57  mov     [rsp+88h+Timeout], r14
0x140327c5c  mov     edx, 113h
0x140327c61  xor     ecx, ecx
0x140327c63  call    cs:__imp_WdLogSingleEntry5
0x140327c6a  nop     dword ptr [rax+rax+00h]
0x140327c6f  mov     cs:WdLogGlobalForLineNumber, edi
0x140327c75  jmp     loc_140327A3F
0x140327c7a  cmp     cs:bTracingEnabled, r14b
0x140327c81  jz      loc_140327AF1
0x140327c87  jmp     loc_140327AD9
0x140327c8c  mov     [rsp+88h+var_60], r14
0x140327c91  lea     r9, [rsi+8]
0x140327c95  mov     r8, r13
0x140327c98  mov     [rsp+88h+Timeout], r14
0x140327c9d  mov     edx, 113h
0x140327ca2  xor     ecx, ecx
0x140327ca4  call    cs:__imp_WdLogSingleEntry5
0x140327cab  nop     dword ptr [rax+rax+00h]
0x140327cb0  mov     cs:WdLogGlobalForLineNumber, edi
0x140327cb6  jmp     loc_140327A8A
0x140327cbb  cmp     cs:bTracingEnabled, r14b
0x140327cc2  jz      loc_140327B2F
0x140327cc8  jmp     loc_140327B17
```
