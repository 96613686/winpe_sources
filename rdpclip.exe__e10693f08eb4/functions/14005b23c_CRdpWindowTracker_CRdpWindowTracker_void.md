# CRdpWindowTracker::~CRdpWindowTracker(void)

- ea: `0x14005b23c`
- end: `0x14005b363`
- name: `??1CRdpWindowTracker@@MEAA@XZ`
- size: `295`
- prototype: `void __fastcall(CRdpWindowTracker *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14005b3c8`

## callees

- `0x140004b1c`
- `0x1400081d0`
- `0x1400107ac`
- `0x14001ff80`
- `0x14005b23c`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005b292`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005b292`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14005b2b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14005b2b8`
- `GDI32!DeleteObject` at `0x14005b275`
- `GDI32!DeleteObject` at `0x14005b275`

## pseudocode

```c
void __fastcall CRdpWindowTracker::~CRdpWindowTracker(CRdpWindowTracker *this)
{
  void *v2; // rcx
  void *v3; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v5; // rcx

  *(_QWORD *)this = &CRdpWindowTracker::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 1) = &CRdpWindowTracker::`vftable'{for `CTSObject'};
  *((_QWORD *)this + 6) = &CRdpWindowTracker::`vftable';
  v2 = (void *)*((_QWORD *)this + 16);
  if ( v2 )
  {
    DeleteObject(v2);
    *((_QWORD *)this + 16) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 35);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 35) = 0;
  }
  if ( *((_DWORD *)this + 16) )
    CTSCriticalSection::Terminate((CRdpWindowTracker *)((char *)this + 56));
  if ( *((_DWORD *)this + 22) )
  {
    CoUninitialize();
    *((_DWORD *)this + 22) = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
      CurrentThreadActivityIdPrefix,
      this);
  }
  v5 = *((_QWORD *)this + 10);
  if ( v5 )
  {
    *((_QWORD *)this + 10) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 72);
  CTSCriticalSection::Terminate((CRdpWindowTracker *)((char *)this + 56));
  *(_QWORD *)this = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 1) = &CTSObject::`vftable';
  *((_DWORD *)this + 7) |= 8u;
}

```

## disassembly

```asm
0x14005b23c  mov     [rsp+arg_0], rbx
0x14005b241  push    rdi
0x14005b242  sub     rsp, 30h
0x14005b246  lea     rax, ??_7CRdpWindowTracker@@6BINonDelegatingUnknown@@@; const CRdpWindowTracker::`vftable'{for `INonDelegatingUnknown'}
0x14005b24d  mov     rbx, rcx
0x14005b250  mov     [rcx], rax
0x14005b253  lea     rax, ??_7CRdpWindowTracker@@6BCTSObject@@@; const CRdpWindowTracker::`vftable'{for `CTSObject'}
0x14005b25a  mov     [rcx+8], rax
0x14005b25e  lea     rax, ??_7CRdpWindowTracker@@6B@; const CRdpWindowTracker::`vftable'
0x14005b265  mov     [rcx+30h], rax
0x14005b269  mov     rcx, [rcx+80h]; ho
0x14005b270  test    rcx, rcx
0x14005b273  jz      short loc_14005B286
0x14005b275  call    cs:__imp_DeleteObject
0x14005b27b  mov     qword ptr [rbx+80h], 0
0x14005b286  mov     rcx, [rbx+118h]; pv
0x14005b28d  test    rcx, rcx
0x14005b290  jz      short loc_14005B2A3
0x14005b292  call    cs:__imp_CoTaskMemFree
0x14005b298  mov     qword ptr [rbx+118h], 0
0x14005b2a3  cmp     dword ptr [rbx+40h], 0
0x14005b2a7  jz      short loc_14005B2B2
0x14005b2a9  lea     rcx, [rbx+38h]; this
0x14005b2ad  call    ?Terminate@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Terminate(void)
0x14005b2b2  cmp     dword ptr [rbx+58h], 0
0x14005b2b6  jz      short loc_14005B2C5
0x14005b2b8  call    cs:__imp_CoUninitialize
0x14005b2be  mov     dword ptr [rbx+58h], 0
0x14005b2c5  mov     rax, cs:WPP_GLOBAL_Control
0x14005b2cc  lea     rcx, WPP_GLOBAL_Control
0x14005b2d3  cmp     rax, rcx
0x14005b2d6  jz      short loc_14005B310
0x14005b2d8  test    dword ptr [rax+1Ch], 200h
0x14005b2df  jz      short loc_14005B310
0x14005b2e1  cmp     byte ptr [rax+19h], 4
0x14005b2e5  jb      short loc_14005B310
0x14005b2e7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005b2ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b2f3  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005b2fa  mov     edx, 10h
0x14005b2ff  mov     [rsp+38h+var_18], rbx
0x14005b304  mov     r9d, eax
0x14005b307  mov     rcx, [rcx+10h]
0x14005b30b  call    WPP_SF_Dq
0x14005b310  mov     rcx, [rbx+50h]
0x14005b314  test    rcx, rcx
0x14005b317  jz      short loc_14005B32D
0x14005b319  mov     qword ptr [rbx+50h], 0
0x14005b321  mov     rax, [rcx]
0x14005b324  mov     rax, [rax+10h]
0x14005b328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b32d  lea     rcx, [rbx+48h]
0x14005b331  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14005b336  lea     rcx, [rbx+38h]; this
0x14005b33a  call    ?Terminate@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Terminate(void)
0x14005b33f  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x14005b346  mov     [rbx], rax
0x14005b349  lea     rax, ??_7CTSObject@@6B@; const CTSObject::`vftable'
0x14005b350  mov     [rbx+8], rax
0x14005b354  or      dword ptr [rbx+1Ch], 8
0x14005b358  mov     rbx, [rsp+38h+arg_0]
0x14005b35d  add     rsp, 30h
0x14005b361  pop     rdi
0x14005b362  retn
```
