# DXGDEVICELOCKONAPPROPRIATETHREADMODEL::DXGDEVICELOCKONAPPROPRIATETHREADMODEL(DXGDEVICE *)

- ea: `0x14001c660`
- end: `0x14001c906`
- name: `??0DXGDEVICELOCKONAPPROPRIATETHREADMODEL@@QEAA@PEAVDXGDEVICE@@@Z`
- size: `678`
- prototype: `DXGDEVICELOCKONAPPROPRIATETHREADMODEL *__fastcall(DXGDEVICELOCKONAPPROPRIATETHREADMODEL *__hidden this, struct DXGDEVICE *)`
- caller_count: `29`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1401abe40`
- `0x1401c9c90`
- `0x1401d9c60`
- `0x14020ef20`
- `0x140269f20`
- `0x14026a6f0`
- `0x140270bf0`
- `0x14027df58`
- `0x140289300`
- `0x140293ad0`
- `0x140293fd0`
- `0x140319248`
- `0x14031bb50`
- `0x140324128`
- `0x14032620c`
- `0x140370d40`
- `0x1403760ec`
- `0x14037c65c`
- `0x1403a2cec`
- `0x1403b692c`
- `0x1403bcba0`
- `0x1403bd7a0`
- `0x1403c21a0`
- `0x1403c65f0`
- `0x1403c6e10`
- `0x1403cc6cc`
- `0x1403d4110`
- `0x1403d5380`
- `0x1403f80d0`

## callees

- `0x14001b890`
- `0x14001c660`
- `0x14001d0e4`
- `0x140321790`
- `0x14036729c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c702`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c747`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c760`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c800`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c702`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c747`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c760`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c800`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c73b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c7ca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c73b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c7ca`
- `ntoskrnl!KeReadStateEvent` at `0x14001c6c1`
- `ntoskrnl!KeReadStateEvent` at `0x14001c890`
- `ntoskrnl!KeReadStateEvent` at `0x14001c6c1`
- `ntoskrnl!KeReadStateEvent` at `0x14001c890`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001c7ad`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001c7ad`
- `ntoskrnl!ExTryAcquirePushLockSharedEx` at `0x14001c713`
- `ntoskrnl!ExTryAcquirePushLockSharedEx` at `0x14001c771`
- `ntoskrnl!ExTryAcquirePushLockSharedEx` at `0x14001c713`
- `ntoskrnl!ExTryAcquirePushLockSharedEx` at `0x14001c771`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c815`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c85f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c815`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c85f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c6e2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c6e2`
- `watchdog!WdLogSingleEntry0` at `0x14001c8b2`
- `watchdog!WdLogSingleEntry0` at `0x14001c8b2`

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
  if ( *(int *)(v3 + 2848) >= 0x2000 || *(_BYTE *)(v3 + 3148) )
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
0x14001c660  mov     [rsp+arg_8], rsi
0x14001c665  push    rdi
0x14001c666  sub     rsp, 50h
0x14001c66a  mov     [rcx], rdx
0x14001c66d  mov     rdi, rcx
0x14001c670  mov     rax, [rdx+10h]
0x14001c674  mov     rcx, [rax+10h]
0x14001c678  cmp     dword ptr [rcx+0B20h], 2000h
0x14001c682  jl      loc_14001C7EA
0x14001c688  xor     esi, esi
0x14001c68a  cmp     cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA, rsi; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x14001c691  jz      loc_14001C8AD
0x14001c697  mov     rax, cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x14001c69e  mov     eax, [rax+560h]
0x14001c6a4  mov     [rsp+58h+arg_0], rbx
0x14001c6a9  mov     [rdi+8], eax
0x14001c6ac  cmp     dword ptr [rdx+1D0h], 2
0x14001c6b3  mov     rbx, [rdx+10h]
0x14001c6b7  jz      loc_14001C88C
0x14001c6bd  lea     rcx, [rbx+60h]; Event
0x14001c6c1  call    cs:__imp_KeReadStateEvent
0x14001c6c8  nop     dword ptr [rax+rax+00h]
0x14001c6cd  test    eax, eax
0x14001c6cf  jnz     short loc_14001C6EE
0x14001c6d1  lea     rcx, [rbx+60h]; Object
0x14001c6d5  xor     r9d, r9d; Alertable
0x14001c6d8  mov     [rsp+58h+Timeout], rsi; Timeout
0x14001c6dd  xor     r8d, r8d; WaitMode
0x14001c6e0  xor     edx, edx; WaitReason
0x14001c6e2  call    cs:__imp_KeWaitForSingleObject
0x14001c6e9  nop     dword ptr [rax+rax+00h]
0x14001c6ee  cmp     dword ptr [rdi+8], 0
0x14001c6f2  mov     rsi, [rdi]
0x14001c6f5  jz      loc_14001C800
0x14001c6fb  lea     rbx, [rsi+90h]
0x14001c702  call    cs:__imp_KeEnterCriticalRegion
0x14001c709  nop     dword ptr [rax+rax+00h]
0x14001c70e  xor     edx, edx
0x14001c710  mov     rcx, rbx
0x14001c713  call    cs:__imp_ExTryAcquirePushLockSharedEx
0x14001c71a  nop     dword ptr [rax+rax+00h]
0x14001c71f  test    al, al
0x14001c721  jz      short loc_14001C73B
0x14001c723  lock inc dword ptr [rbx+10h]
0x14001c727  mov     rax, rdi
0x14001c72a  mov     rbx, [rsp+58h+arg_0]
0x14001c72f  mov     rsi, [rsp+58h+arg_8]
0x14001c734  add     rsp, 50h
0x14001c738  pop     rdi
0x14001c739  retn
0x14001c73b  call    cs:__imp_KeLeaveCriticalRegion
0x14001c742  nop     dword ptr [rax+rax+00h]
0x14001c747  call    cs:__imp_KeEnterCriticalRegion
0x14001c74e  nop     dword ptr [rax+rax+00h]
0x14001c753  mov     rcx, [rsi+10h]
0x14001c757  mov     rcx, [rcx+10h]; this
0x14001c75b  call    ?TryWakeUpFromD3State@DXGADAPTER@@QEAAEXZ; DXGADAPTER::TryWakeUpFromD3State(void)
0x14001c760  call    cs:__imp_KeEnterCriticalRegion
0x14001c767  nop     dword ptr [rax+rax+00h]
0x14001c76c  xor     edx, edx
0x14001c76e  mov     rcx, rbx
0x14001c771  call    cs:__imp_ExTryAcquirePushLockSharedEx
0x14001c778  nop     dword ptr [rax+rax+00h]
0x14001c77d  test    al, al
0x14001c77f  jnz     short loc_14001C7B9
0x14001c781  cmp     cs:bTracingEnabled, al
0x14001c787  jz      short loc_14001C7A8
0x14001c789  mov     r9d, [rbx+18h]
0x14001c78d  cmp     r9d, 0FFFFFFFFh
0x14001c791  jz      short loc_14001C7A8
0x14001c793  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x14001c79a  jz      short loc_14001C7A8
0x14001c79c  lea     rdx, EventBlockThread
0x14001c7a3  call    McTemplateK0q_EtwWriteTransfer
0x14001c7a8  xor     edx, edx
0x14001c7aa  mov     rcx, rbx
0x14001c7ad  call    cs:__imp_ExAcquirePushLockSharedEx
0x14001c7b4  nop     dword ptr [rax+rax+00h]
0x14001c7b9  lock inc dword ptr [rbx+10h]
0x14001c7bd  mov     rcx, [rsi+10h]
0x14001c7c1  mov     rcx, [rcx+10h]; this
0x14001c7c5  call    ?EnableD3Requests@DXGADAPTER@@QEAAXXZ; DXGADAPTER::EnableD3Requests(void)
0x14001c7ca  call    cs:__imp_KeLeaveCriticalRegion
0x14001c7d1  nop     dword ptr [rax+rax+00h]
0x14001c7d6  mov     rax, rdi
0x14001c7d9  mov     rbx, [rsp+58h+arg_0]
0x14001c7de  mov     rsi, [rsp+58h+arg_8]
0x14001c7e3  add     rsp, 50h
0x14001c7e7  pop     rdi
0x14001c7e8  retn
0x14001c7ea  cmp     byte ptr [rcx+0C4Ch], 0
0x14001c7f1  jnz     loc_14001C688
0x14001c7f7  xor     esi, esi
0x14001c7f9  mov     eax, esi
0x14001c7fb  jmp     loc_14001C6A4
0x14001c800  call    cs:__imp_KeEnterCriticalRegion
0x14001c807  nop     dword ptr [rax+rax+00h]
0x14001c80c  mov     rcx, [rsi+88h]; Resource
0x14001c813  xor     edx, edx; Wait
0x14001c815  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001c81c  nop     dword ptr [rax+rax+00h]
0x14001c821  test    al, al
0x14001c823  jnz     short loc_14001C7D6
0x14001c825  mov     rcx, [rsi+10h]
0x14001c829  mov     rcx, [rcx+10h]; this
0x14001c82d  call    ?TryWakeUpFromD3State@DXGADAPTER@@QEAAEXZ; DXGADAPTER::TryWakeUpFromD3State(void)
0x14001c832  cmp     cs:bTracingEnabled, 0
0x14001c839  jz      short loc_14001C856
0x14001c83b  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x14001c842  jz      short loc_14001C856
0x14001c844  mov     r9d, 28h ; '('
0x14001c84a  lea     rdx, EventBlockThread
0x14001c851  call    McTemplateK0q_EtwWriteTransfer
0x14001c856  mov     rcx, [rsi+88h]; Resource
0x14001c85d  mov     dl, 1; Wait
0x14001c85f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001c866  nop     dword ptr [rax+rax+00h]
0x14001c86b  mov     rcx, [rsi+10h]
0x14001c86f  mov     rcx, [rcx+10h]; this
0x14001c873  call    ?EnableD3Requests@DXGADAPTER@@QEAAXXZ; DXGADAPTER::EnableD3Requests(void)
0x14001c878  mov     rbx, [rsp+58h+arg_0]
0x14001c87d  mov     rax, rdi
0x14001c880  mov     rsi, [rsp+58h+arg_8]
0x14001c885  add     rsp, 50h
0x14001c889  pop     rdi
0x14001c88a  retn
0x14001c88c  lea     rcx, [rbx+78h]; Event
0x14001c890  call    cs:__imp_KeReadStateEvent
0x14001c897  nop     dword ptr [rax+rax+00h]
0x14001c89c  test    eax, eax
0x14001c89e  jnz     loc_14001C6EE
0x14001c8a4  lea     rcx, [rbx+78h]
0x14001c8a8  jmp     loc_14001C6D5
0x14001c8ad  mov     ecx, 1
0x14001c8b2  call    cs:__imp_WdLogSingleEntry0
0x14001c8b9  nop     dword ptr [rax+rax+00h]
0x14001c8be  mov     [rsp+58h+var_18], rsi
0x14001c8c3  lea     r9, aMPglobalNull; "m_pGlobal != NULL"
0x14001c8ca  mov     [rsp+58h+var_20], rsi
0x14001c8cf  mov     edx, 40002h
0x14001c8d4  mov     [rsp+58h+var_28], rsi
0x14001c8d9  xor     ecx, ecx
0x14001c8db  mov     [rsp+58h+var_30], rsi
0x14001c8e0  mov     r8d, 0FFFFFFFFh
0x14001c8e6  mov     [rsp+58h+Timeout], 0A5Ah
0x14001c8ef  mov     cs:WdLogGlobalForLineNumber, 0A5Ah
0x14001c8f9  call    DxgkLogInternalTriageEvent
0x14001c8fe  mov     rdx, [rdi]
0x14001c901  jmp     loc_14001C697
```
