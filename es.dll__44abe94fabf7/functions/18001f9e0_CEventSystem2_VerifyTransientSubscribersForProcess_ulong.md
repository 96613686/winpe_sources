# CEventSystem2::VerifyTransientSubscribersForProcess(ulong)

- ea: `0x18001f9e0`
- end: `0x18001fb22`
- name: `?VerifyTransientSubscribersForProcess@CEventSystem2@@UEAAJK@Z`
- size: `322`
- prototype: `__int64 __fastcall(CEventSystem2 *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010410`
- `0x18001f9e0`
- `0x18001fcac`
- `0x1800202fc`
- `0x180020350`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001faf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044bff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001faf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044bff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fad7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fad7`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x18001fa0f`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x18001fa0f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001facd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001facd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fab5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fab5`

## pseudocode

```c
__int64 __fastcall CEventSystem2::VerifyTransientSubscribersForProcess(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned int a2)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r8
  __int64 *i; // rax
  __int64 v6; // rsi
  _QWORD *v7; // r14
  OLECHAR *v8; // rbx
  OLECHAR *v9; // rcx
  unsigned int v11; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  if ( I_RpcBindingInqTransportType(0, &v11) != 1725 )
    return 2147942405LL;
  if ( LODWORD(this[10].DebugInfo) )
    return 2147549448LL;
  CSemExclusiveES::Lock((CSemExclusiveES *)&this[3]);
  DebugInfo = this[2].DebugInfo;
  if ( DebugInfo )
  {
    for ( i = (__int64 *)*((_QWORD *)&DebugInfo->Type + (a2 >> 4) % this[2].LockCount);
          i && *((_DWORD *)i + 3) != a2;
          i = (__int64 *)*i )
    {
      ;
    }
    if ( i )
    {
      v6 = i[2];
      v7 = *(_QWORD **)(v6 + 24);
      while ( v7 )
      {
        v8 = (OLECHAR *)v7[2];
        v7 = (_QWORD *)*v7;
        if ( *((int *)v8 - 3) < 0 )
          v8 = (OLECHAR *)&dword_180053104;
        else
          _InterlockedIncrement((volatile signed __int32 *)v8 - 3);
        TransientSubChecker::CheckerThread::ScheduleCheck((HANDLE *)&this[6].DebugInfo, v8);
        v9 = v8 - 6;
        if ( v8 - 6 != (OLECHAR *)&qword_1800530F8 && !_InterlockedDecrement((volatile signed __int32 *)v9) )
          CoTaskMemFree(v9);
      }
      CMap<unsigned long,unsigned long,CEventSystem2::TransientSubscriberProcessData *,CEventSystem2::TransientSubscriberProcessData *>::RemoveKey(&this[2]);
      CloseThreadpoolWait(*(PTP_WAIT *)(v6 + 16));
      CloseHandle(*(HANDLE *)(v6 + 8));
      CEventSystem2::TransientSubscriberProcessData::`scalar deleting destructor'((CEventSystem2::TransientSubscriberProcessData *)v6);
    }
  }
  LeaveCriticalSection(this + 3);
  return 0;
}

```

## disassembly

```asm
0x18001f9e0  mov     rax, rsp
0x18001f9e3  mov     [rax+10h], rbx
0x18001f9e7  mov     [rax+20h], rsi
0x18001f9eb  mov     [rax+8], rcx
0x18001f9ef  push    rdi
0x18001f9f0  push    r12
0x18001f9f2  push    r13
0x18001f9f4  push    r14
0x18001f9f6  push    r15
0x18001f9f8  sub     rsp, 20h
0x18001f9fc  mov     r13d, edx
0x18001f9ff  mov     rdi, rcx
0x18001fa02  mov     dword ptr [rax+18h], 0
0x18001fa09  lea     rdx, [rax+18h]; Type
0x18001fa0d  xor     ecx, ecx; Binding
0x18001fa0f  call    cs:__imp_I_RpcBindingInqTransportType
0x18001fa15  cmp     eax, 6BDh
0x18001fa1a  jnz     loc_18001FB14
0x18001fa20  cmp     dword ptr [rdi+190h], 0
0x18001fa27  jnz     loc_18001FB1B
0x18001fa2d  lea     rcx, [rdi+78h]; this
0x18001fa31  call    ?Lock@CSemExclusiveES@@QEAAXXZ; CSemExclusiveES::Lock(void)
0x18001fa36  nop
0x18001fa37  mov     r8, [rdi+50h]
0x18001fa3b  test    r8, r8
0x18001fa3e  jz      loc_18001FAF0
0x18001fa44  mov     eax, r13d
0x18001fa47  shr     eax, 4
0x18001fa4a  xor     edx, edx
0x18001fa4c  div     dword ptr [rdi+58h]
0x18001fa4f  mov     rax, [r8+rdx*8]
0x18001fa53  test    rax, rax
0x18001fa56  jz      short loc_18001FA63
0x18001fa58  cmp     [rax+0Ch], r13d
0x18001fa5c  jz      short loc_18001FA63
0x18001fa5e  mov     rax, [rax]
0x18001fa61  jmp     short loc_18001FA53
0x18001fa63  test    rax, rax
0x18001fa66  jz      loc_18001FAF0
0x18001fa6c  mov     rsi, [rax+10h]
0x18001fa70  mov     r14, [rsi+18h]
0x18001fa74  test    r14, r14
0x18001fa77  jz      short loc_18001FABD
0x18001fa79  mov     rbx, [r14+10h]
0x18001fa7d  mov     r14, [r14]
0x18001fa80  cmp     dword ptr [rbx-0Ch], 0
0x18001fa84  jl      short loc_18001FAE7
0x18001fa86  lock inc dword ptr [rbx-0Ch]
0x18001fa8a  lea     rcx, [rdi+0F0h]; this
0x18001fa91  mov     rdx, rbx; psz
0x18001fa94  call    ?ScheduleCheck@CheckerThread@TransientSubChecker@@QEAAXPEBG@Z; TransientSubChecker::CheckerThread::ScheduleCheck(ushort const *)
0x18001fa99  lea     rcx, [rbx-0Ch]; pv
0x18001fa9d  lea     rax, qword_1800530F8
0x18001faa4  cmp     rcx, rax
0x18001faa7  jz      short loc_18001FABB
0x18001faa9  or      eax, 0FFFFFFFFh
0x18001faac  lock xadd [rcx], eax
0x18001fab0  sub     eax, 1
0x18001fab3  jnz     short loc_18001FABB
0x18001fab5  call    cs:__imp_CoTaskMemFree
0x18001fabb  jmp     short loc_18001FA74
0x18001fabd  mov     edx, r13d
0x18001fac0  lea     rcx, [rdi+50h]
0x18001fac4  call    ?RemoveKey@?$CMap@KKPEAUTransientSubscriberProcessData@CEventSystem2@@PEAU12@@@QEAAHK@Z; CMap<ulong,ulong,CEventSystem2::TransientSubscriberProcessData *,CEventSystem2::TransientSubscriberProcessData *>::RemoveKey(ulong)
0x18001fac9  mov     rcx, [rsi+10h]; pwa
0x18001facd  call    cs:__imp_CloseThreadpoolWait
0x18001fad3  mov     rcx, [rsi+8]; hObject
0x18001fad7  call    cs:__imp_CloseHandle
0x18001fadd  mov     rcx, rsi; this
0x18001fae0  call    ??_GTransientSubscriberProcessData@CEventSystem2@@QEAAPEAXI@Z; CEventSystem2::TransientSubscriberProcessData::`scalar deleting destructor'(uint)
0x18001fae5  jmp     short loc_18001FAF0
0x18001fae7  lea     rbx, dword_180053104
0x18001faee  jmp     short loc_18001FA8A
0x18001faf0  lea     rcx, [rdi+78h]; lpCriticalSection
0x18001faf4  call    cs:__imp_LeaveCriticalSection
0x18001fafa  xor     eax, eax
0x18001fafc  mov     rbx, [rsp+48h+arg_8]
0x18001fb01  mov     rsi, [rsp+48h+arg_18]
0x18001fb06  add     rsp, 20h
0x18001fb0a  pop     r15
0x18001fb0c  pop     r14
0x18001fb0e  pop     r13
0x18001fb10  pop     r12
0x18001fb12  pop     rdi
0x18001fb13  retn
0x18001fb14  mov     eax, 80070005h
0x18001fb19  jmp     short loc_18001FAFC
0x18001fb1b  mov     eax, 80010108h
0x18001fb20  jmp     short loc_18001FAFC
0x180044bee  push    rbp
0x180044bf0  sub     rsp, 20h
0x180044bf4  mov     rbp, rdx
0x180044bf7  mov     rcx, [rbp+50h]
0x180044bfb  add     rcx, 78h ; 'x'; lpCriticalSection
0x180044bff  call    cs:__imp_LeaveCriticalSection
0x180044c05  nop
0x180044c06  add     rsp, 20h
0x180044c0a  pop     rbp
0x180044c0b  retn
```
