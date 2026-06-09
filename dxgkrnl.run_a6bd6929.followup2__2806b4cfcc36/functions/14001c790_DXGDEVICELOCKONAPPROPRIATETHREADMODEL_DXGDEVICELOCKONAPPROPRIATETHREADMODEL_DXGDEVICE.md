# DXGDEVICELOCKONAPPROPRIATETHREADMODEL::DXGDEVICELOCKONAPPROPRIATETHREADMODEL(DXGDEVICE *)

- ea: `0x14001c790`
- end: `0x14001ca36`
- name: `??0DXGDEVICELOCKONAPPROPRIATETHREADMODEL@@QEAA@PEAVDXGDEVICE@@@Z`
- size: `678`
- prototype: `DXGDEVICELOCKONAPPROPRIATETHREADMODEL *__fastcall(DXGDEVICELOCKONAPPROPRIATETHREADMODEL *__hidden this, struct DXGDEVICE *)`
- caller_count: `29`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1401cc890`
- `0x1401dbfd0`
- `0x140211570`
- `0x14026f4e0`
- `0x14026fcb0`
- `0x1402761b0`
- `0x140280ed0`
- `0x140284b68`
- `0x14028ff10`
- `0x14029a430`
- `0x14029a930`
- `0x14031ffb8`
- `0x1403228c0`
- `0x14032ae98`
- `0x14032cf7c`
- `0x140370d80`
- `0x14037612c`
- `0x140383fdc`
- `0x1403a3acc`
- `0x1403b3b2c`
- `0x1403bbec0`
- `0x1403bcac0`
- `0x1403c1550`
- `0x1403c59a0`
- `0x1403c61c0`
- `0x1403ccaec`
- `0x1403d4530`
- `0x1403d57a0`
- `0x14040e140`

## callees

- `0x14001b9c0`
- `0x14001c790`
- `0x14001d214`
- `0x140328500`
- `0x1403672dc`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c832`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c877`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c890`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c930`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c832`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c877`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c890`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c930`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c86b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c8fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c86b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c8fa`
- `ntoskrnl!KeReadStateEvent` at `0x14001c7f1`
- `ntoskrnl!KeReadStateEvent` at `0x14001c9c0`
- `ntoskrnl!KeReadStateEvent` at `0x14001c7f1`
- `ntoskrnl!KeReadStateEvent` at `0x14001c9c0`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001c8dd`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001c8dd`
- `ntoskrnl!ExTryAcquirePushLockSharedEx` at `0x14001c843`
- `ntoskrnl!ExTryAcquirePushLockSharedEx` at `0x14001c8a1`
- `ntoskrnl!ExTryAcquirePushLockSharedEx` at `0x14001c843`
- `ntoskrnl!ExTryAcquirePushLockSharedEx` at `0x14001c8a1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c945`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c98f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c945`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c98f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c812`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c812`
- `watchdog!WdLogSingleEntry0` at `0x14001c9e2`
- `watchdog!WdLogSingleEntry0` at `0x14001c9e2`

## pseudocode

```c
DXGDEVICELOCKONAPPROPRIATETHREADMODEL *__fastcall DXGDEVICELOCKONAPPROPRIATETHREADMODEL::DXGDEVICELOCKONAPPROPRIATETHREADMODEL(
        DXGDEVICELOCKONAPPROPRIATETHREADMODEL *this,
        struct DXGDEVICE *a2)
{
  __int64 v3; // rcx
  int v4; // eax
  struct _KEVENT *v5; // rbx
  struct _KEVENT *v6; // rcx
  __int64 v7; // rsi
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // r8

  *(_QWORD *)this = a2;
  v3 = *(_QWORD *)(*((_QWORD *)a2 + 2) + 16LL);
  if ( *(int *)(v3 + 2864) >= 0x2000 || *(_BYTE *)(v3 + 3164) )
  {
    if ( !*(_QWORD *)&DXGGLOBAL::m_pGlobal )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 2650;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_pGlobal != NULL", 2650, 0, 0, 0, 0);
      a2 = *(struct DXGDEVICE **)this;
    }
    v4 = *(_DWORD *)(*(_QWORD *)&DXGGLOBAL::m_pGlobal + 1376LL);
  }
  else
  {
    v4 = 0;
  }
  *((_DWORD *)this + 2) = v4;
  v5 = (struct _KEVENT *)*((_QWORD *)a2 + 2);
  if ( *((_DWORD *)a2 + 116) != 2 )
  {
    if ( KeReadStateEvent(v5 + 4) )
      goto LABEL_9;
    v6 = v5 + 4;
    goto LABEL_8;
  }
  if ( !KeReadStateEvent(v5 + 5) )
  {
    v6 = v5 + 5;
LABEL_8:
    KeWaitForSingleObject(v6, Executive, 0, 0, 0);
  }
LABEL_9:
  v7 = *(_QWORD *)this;
  if ( *((_DWORD *)this + 2) )
  {
    KeEnterCriticalRegion();
    if ( (unsigned __int8)ExTryAcquirePushLockSharedEx(v7 + 144, 0) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 160));
      return this;
    }
    KeLeaveCriticalRegion();
    KeEnterCriticalRegion();
    DXGADAPTER::TryWakeUpFromD3State(*(DXGADAPTER **)(*(_QWORD *)(v7 + 16) + 16LL));
    KeEnterCriticalRegion();
    if ( !(unsigned __int8)ExTryAcquirePushLockSharedEx(v7 + 144, 0) )
    {
      if ( bTracingEnabled )
      {
        v11 = *(unsigned int *)(v7 + 168);
        if ( (_DWORD)v11 != -1 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
          McTemplateK0q_EtwWriteTransfer(v9, EventBlockThread, v10, v11);
      }
      ExAcquirePushLockSharedEx(v7 + 144, 0);
    }
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 160));
    DXGADAPTER::EnableD3Requests(*(DXGADAPTER **)(*(_QWORD *)(v7 + 16) + 16LL));
    KeLeaveCriticalRegion();
    return this;
  }
  KeEnterCriticalRegion();
  if ( ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v7 + 136), 0) )
    return this;
  DXGADAPTER::TryWakeUpFromD3State(*(DXGADAPTER **)(*(_QWORD *)(v7 + 16) + 16LL));
  if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
    McTemplateK0q_EtwWriteTransfer(v12, EventBlockThread, v13, 40);
  ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v7 + 136), 1u);
  DXGADAPTER::EnableD3Requests(*(DXGADAPTER **)(*(_QWORD *)(v7 + 16) + 16LL));
  return this;
}

```

## disassembly

```asm
0x14001c790  mov     [rsp+arg_8], rsi
0x14001c795  push    rdi
0x14001c796  sub     rsp, 50h
0x14001c79a  mov     [rcx], rdx
0x14001c79d  mov     rdi, rcx
0x14001c7a0  mov     rax, [rdx+10h]
0x14001c7a4  mov     rcx, [rax+10h]
0x14001c7a8  cmp     dword ptr [rcx+0B30h], 2000h
0x14001c7b2  jl      loc_14001C91A
0x14001c7b8  xor     esi, esi
0x14001c7ba  cmp     cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA, rsi; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x14001c7c1  jz      loc_14001C9DD
0x14001c7c7  mov     rax, cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x14001c7ce  mov     eax, [rax+560h]
0x14001c7d4  mov     [rsp+58h+arg_0], rbx
0x14001c7d9  mov     [rdi+8], eax
0x14001c7dc  cmp     dword ptr [rdx+1D0h], 2
0x14001c7e3  mov     rbx, [rdx+10h]
0x14001c7e7  jz      loc_14001C9BC
0x14001c7ed  lea     rcx, [rbx+60h]; Event
0x14001c7f1  call    cs:__imp_KeReadStateEvent
0x14001c7f8  nop     dword ptr [rax+rax+00h]
0x14001c7fd  test    eax, eax
0x14001c7ff  jnz     short loc_14001C81E
0x14001c801  lea     rcx, [rbx+60h]; Object
0x14001c805  xor     r9d, r9d; Alertable
0x14001c808  mov     [rsp+58h+Timeout], rsi; Timeout
0x14001c80d  xor     r8d, r8d; WaitMode
0x14001c810  xor     edx, edx; WaitReason
0x14001c812  call    cs:__imp_KeWaitForSingleObject
0x14001c819  nop     dword ptr [rax+rax+00h]
0x14001c81e  cmp     dword ptr [rdi+8], 0
0x14001c822  mov     rsi, [rdi]
0x14001c825  jz      loc_14001C930
0x14001c82b  lea     rbx, [rsi+90h]
0x14001c832  call    cs:__imp_KeEnterCriticalRegion
0x14001c839  nop     dword ptr [rax+rax+00h]
0x14001c83e  xor     edx, edx
0x14001c840  mov     rcx, rbx
0x14001c843  call    cs:__imp_ExTryAcquirePushLockSharedEx
0x14001c84a  nop     dword ptr [rax+rax+00h]
0x14001c84f  test    al, al
0x14001c851  jz      short loc_14001C86B
0x14001c853  lock inc dword ptr [rbx+10h]
0x14001c857  mov     rax, rdi
0x14001c85a  mov     rbx, [rsp+58h+arg_0]
0x14001c85f  mov     rsi, [rsp+58h+arg_8]
0x14001c864  add     rsp, 50h
0x14001c868  pop     rdi
0x14001c869  retn
0x14001c86b  call    cs:__imp_KeLeaveCriticalRegion
0x14001c872  nop     dword ptr [rax+rax+00h]
0x14001c877  call    cs:__imp_KeEnterCriticalRegion
0x14001c87e  nop     dword ptr [rax+rax+00h]
0x14001c883  mov     rcx, [rsi+10h]
0x14001c887  mov     rcx, [rcx+10h]; this
0x14001c88b  call    ?TryWakeUpFromD3State@DXGADAPTER@@QEAAEXZ; DXGADAPTER::TryWakeUpFromD3State(void)
0x14001c890  call    cs:__imp_KeEnterCriticalRegion
0x14001c897  nop     dword ptr [rax+rax+00h]
0x14001c89c  xor     edx, edx
0x14001c89e  mov     rcx, rbx
0x14001c8a1  call    cs:__imp_ExTryAcquirePushLockSharedEx
0x14001c8a8  nop     dword ptr [rax+rax+00h]
0x14001c8ad  test    al, al
0x14001c8af  jnz     short loc_14001C8E9
0x14001c8b1  cmp     cs:bTracingEnabled, al
0x14001c8b7  jz      short loc_14001C8D8
0x14001c8b9  mov     r9d, [rbx+18h]
0x14001c8bd  cmp     r9d, 0FFFFFFFFh
0x14001c8c1  jz      short loc_14001C8D8
0x14001c8c3  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x14001c8ca  jz      short loc_14001C8D8
0x14001c8cc  lea     rdx, EventBlockThread
0x14001c8d3  call    McTemplateK0q_EtwWriteTransfer
0x14001c8d8  xor     edx, edx
0x14001c8da  mov     rcx, rbx
0x14001c8dd  call    cs:__imp_ExAcquirePushLockSharedEx
0x14001c8e4  nop     dword ptr [rax+rax+00h]
0x14001c8e9  lock inc dword ptr [rbx+10h]
0x14001c8ed  mov     rcx, [rsi+10h]
0x14001c8f1  mov     rcx, [rcx+10h]; this
0x14001c8f5  call    ?EnableD3Requests@DXGADAPTER@@QEAAXXZ; DXGADAPTER::EnableD3Requests(void)
0x14001c8fa  call    cs:__imp_KeLeaveCriticalRegion
0x14001c901  nop     dword ptr [rax+rax+00h]
0x14001c906  mov     rax, rdi
0x14001c909  mov     rbx, [rsp+58h+arg_0]
0x14001c90e  mov     rsi, [rsp+58h+arg_8]
0x14001c913  add     rsp, 50h
0x14001c917  pop     rdi
0x14001c918  retn
0x14001c91a  cmp     byte ptr [rcx+0C5Ch], 0
0x14001c921  jnz     loc_14001C7B8
0x14001c927  xor     esi, esi
0x14001c929  mov     eax, esi
0x14001c92b  jmp     loc_14001C7D4
0x14001c930  call    cs:__imp_KeEnterCriticalRegion
0x14001c937  nop     dword ptr [rax+rax+00h]
0x14001c93c  mov     rcx, [rsi+88h]; Resource
0x14001c943  xor     edx, edx; Wait
0x14001c945  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001c94c  nop     dword ptr [rax+rax+00h]
0x14001c951  test    al, al
0x14001c953  jnz     short loc_14001C906
0x14001c955  mov     rcx, [rsi+10h]
0x14001c959  mov     rcx, [rcx+10h]; this
0x14001c95d  call    ?TryWakeUpFromD3State@DXGADAPTER@@QEAAEXZ; DXGADAPTER::TryWakeUpFromD3State(void)
0x14001c962  cmp     cs:bTracingEnabled, 0
0x14001c969  jz      short loc_14001C986
0x14001c96b  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x14001c972  jz      short loc_14001C986
0x14001c974  mov     r9d, 28h ; '('
0x14001c97a  lea     rdx, EventBlockThread
0x14001c981  call    McTemplateK0q_EtwWriteTransfer
0x14001c986  mov     rcx, [rsi+88h]; Resource
0x14001c98d  mov     dl, 1; Wait
0x14001c98f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001c996  nop     dword ptr [rax+rax+00h]
0x14001c99b  mov     rcx, [rsi+10h]
0x14001c99f  mov     rcx, [rcx+10h]; this
0x14001c9a3  call    ?EnableD3Requests@DXGADAPTER@@QEAAXXZ; DXGADAPTER::EnableD3Requests(void)
0x14001c9a8  mov     rbx, [rsp+58h+arg_0]
0x14001c9ad  mov     rax, rdi
0x14001c9b0  mov     rsi, [rsp+58h+arg_8]
0x14001c9b5  add     rsp, 50h
0x14001c9b9  pop     rdi
0x14001c9ba  retn
0x14001c9bc  lea     rcx, [rbx+78h]; Event
0x14001c9c0  call    cs:__imp_KeReadStateEvent
0x14001c9c7  nop     dword ptr [rax+rax+00h]
0x14001c9cc  test    eax, eax
0x14001c9ce  jnz     loc_14001C81E
0x14001c9d4  lea     rcx, [rbx+78h]
0x14001c9d8  jmp     loc_14001C805
0x14001c9dd  mov     ecx, 1
0x14001c9e2  call    cs:__imp_WdLogSingleEntry0
0x14001c9e9  nop     dword ptr [rax+rax+00h]
0x14001c9ee  mov     [rsp+58h+var_18], rsi
0x14001c9f3  lea     r9, aMPglobalNull; "m_pGlobal != NULL"
0x14001c9fa  mov     [rsp+58h+var_20], rsi
0x14001c9ff  mov     edx, 40002h
0x14001ca04  mov     [rsp+58h+var_28], rsi
0x14001ca09  xor     ecx, ecx
0x14001ca0b  mov     [rsp+58h+var_30], rsi
0x14001ca10  mov     r8d, 0FFFFFFFFh
0x14001ca16  mov     [rsp+58h+Timeout], 0A5Ah
0x14001ca1f  mov     cs:WdLogGlobalForLineNumber, 0A5Ah
0x14001ca29  call    DxgkLogInternalTriageEvent
0x14001ca2e  mov     rdx, [rdi]
0x14001ca31  jmp     loc_14001C7C7
```
