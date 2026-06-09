# CSNOCplCore::OnNavigateAway(void)

- ea: `0x18000df98`
- end: `0x18000e140`
- name: `?OnNavigateAway@CSNOCplCore@@QEAAJXZ`
- size: `424`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1800151a0`

## callees

- `0x180006b70`
- `0x18000df98`
- `0x180011fa8`
- `0x180014274`
- `0x1800159c4`
- `0x180019510`
- `0x180019ad8`
- `0x18002192c`
- `0x180023010`

## import_xrefs

- `USER32!RemovePropW` at `0x18000e0e6`
- `USER32!RemovePropW` at `0x18000e0e6`
- `USER32!DestroyWindow` at `0x18000e0f3`
- `USER32!DestroyWindow` at `0x18000e0f3`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::OnNavigateAway(CSNOCplCore *this)
{
  CServiceMonitor *v2; // rcx
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  CServiceMonitor *v4; // rcx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  CServiceMonitor *v6; // rcx
  void (__fastcall ***v7)(_QWORD, __int64); // rcx
  CWwanHelper *v8; // rcx
  unsigned int v9; // edi
  HWND v10; // rdx
  HWND v11; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
  v2 = (CServiceMonitor *)*((_QWORD *)this + 33);
  *((_DWORD *)this + 62) = 1;
  if ( v2 )
  {
    CServiceMonitor::Stop(v2);
    v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 33);
    if ( v3 )
      (**v3)(v3, 1);
    *((_QWORD *)this + 33) = 0;
  }
  v4 = (CServiceMonitor *)*((_QWORD *)this + 34);
  if ( v4 )
  {
    CServiceMonitor::Stop(v4);
    v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 34);
    if ( v5 )
      (**v5)(v5, 1);
    *((_QWORD *)this + 34) = 0;
  }
  v6 = (CServiceMonitor *)*((_QWORD *)this + 35);
  if ( v6 )
  {
    CServiceMonitor::Stop(v6);
    v7 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 35);
    if ( v7 )
      (**v7)(v7, 1);
    *((_QWORD *)this + 35) = 0;
  }
  CWlanHelper::UnregisterWLANEvent((char *)this + 184);
  v8 = (CWwanHelper *)*((_QWORD *)this + 26);
  if ( v8 )
  {
    CWwanHelper::UnregisterWwanEvent(v8);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 26) + 16LL) + 16LL))(*((_QWORD *)this + 26) + 16LL);
    *((_QWORD *)this + 26) = 0;
  }
  v9 = CProfileMgr::UnregisterEvents(this);
  HrRemoveNSCInstance(this, v10);
  v11 = (HWND)*((_QWORD *)this + 32);
  if ( v11 )
  {
    RemovePropW(v11, L"_Netcenter_ptr");
    DestroyWindow(*((HWND *)this + 32));
    *((_QWORD *)this + 32) = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18000df98  mov     [rsp+arg_0], rbx
0x18000df9d  mov     [rsp+arg_8], rbp
0x18000dfa2  push    rdi
0x18000dfa3  sub     rsp, 20h
0x18000dfa7  mov     rbx, rcx
0x18000dfaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfb1  lea     rbp, WPP_GLOBAL_Control
0x18000dfb8  cmp     rcx, rbp
0x18000dfbb  jz      short loc_18000DFD8
0x18000dfbd  test    byte ptr [rcx+1Ch], 8
0x18000dfc1  jz      short loc_18000DFD8
0x18000dfc3  mov     rcx, [rcx+10h]
0x18000dfc7  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000dfce  mov     edx, 1Bh
0x18000dfd3  call    WPP_SF_
0x18000dfd8  mov     rcx, [rbx+108h]; this
0x18000dfdf  mov     edi, 1
0x18000dfe4  mov     [rbx+0F8h], edi
0x18000dfea  test    rcx, rcx
0x18000dfed  jz      short loc_18000E018
0x18000dfef  call    ?Stop@CServiceMonitor@@QEAAJXZ; CServiceMonitor::Stop(void)
0x18000dff4  mov     rcx, [rbx+108h]
0x18000dffb  test    rcx, rcx
0x18000dffe  jz      short loc_18000E00D
0x18000e000  mov     rax, [rcx]
0x18000e003  mov     edx, edi
0x18000e005  mov     rax, [rax]
0x18000e008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e00d  mov     qword ptr [rbx+108h], 0
0x18000e018  mov     rcx, [rbx+110h]; this
0x18000e01f  test    rcx, rcx
0x18000e022  jz      short loc_18000E04D
0x18000e024  call    ?Stop@CServiceMonitor@@QEAAJXZ; CServiceMonitor::Stop(void)
0x18000e029  mov     rcx, [rbx+110h]
0x18000e030  test    rcx, rcx
0x18000e033  jz      short loc_18000E042
0x18000e035  mov     rax, [rcx]
0x18000e038  mov     edx, edi
0x18000e03a  mov     rax, [rax]
0x18000e03d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e042  mov     qword ptr [rbx+110h], 0
0x18000e04d  mov     rcx, [rbx+118h]; this
0x18000e054  test    rcx, rcx
0x18000e057  jz      short loc_18000E082
0x18000e059  call    ?Stop@CServiceMonitor@@QEAAJXZ; CServiceMonitor::Stop(void)
0x18000e05e  mov     rcx, [rbx+118h]
0x18000e065  test    rcx, rcx
0x18000e068  jz      short loc_18000E077
0x18000e06a  mov     rax, [rcx]
0x18000e06d  mov     edx, edi
0x18000e06f  mov     rax, [rax]
0x18000e072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e077  mov     qword ptr [rbx+118h], 0
0x18000e082  lea     rcx, [rbx+0B8h]; pCallbackContext
0x18000e089  call    ?UnregisterWLANEvent@CWlanHelper@@QEAAJXZ; CWlanHelper::UnregisterWLANEvent(void)
0x18000e08e  mov     rcx, [rbx+0D0h]; this
0x18000e095  test    rcx, rcx
0x18000e098  jz      short loc_18000E0C1
0x18000e09a  call    ?UnregisterWwanEvent@CWwanHelper@@QEAAJXZ; CWwanHelper::UnregisterWwanEvent(void)
0x18000e09f  mov     rcx, [rbx+0D0h]
0x18000e0a6  add     rcx, 10h
0x18000e0aa  mov     rax, [rcx]
0x18000e0ad  mov     rax, [rax+10h]
0x18000e0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0b6  mov     qword ptr [rbx+0D0h], 0
0x18000e0c1  mov     rcx, rbx; this
0x18000e0c4  call    ?UnregisterEvents@CProfileMgr@@QEAAJXZ; CProfileMgr::UnregisterEvents(void)
0x18000e0c9  mov     rcx, rbx; void *
0x18000e0cc  mov     edi, eax
0x18000e0ce  call    ?HrRemoveNSCInstance@@YAJPEAXQEAUHWND__@@@Z; HrRemoveNSCInstance(void *,HWND__ * const)
0x18000e0d3  mov     rcx, [rbx+100h]; hWnd
0x18000e0da  test    rcx, rcx
0x18000e0dd  jz      short loc_18000E104
0x18000e0df  lea     rdx, String; "_Netcenter_ptr"
0x18000e0e6  call    cs:__imp_RemovePropW
0x18000e0ec  mov     rcx, [rbx+100h]; hWnd
0x18000e0f3  call    cs:__imp_DestroyWindow
0x18000e0f9  mov     qword ptr [rbx+100h], 0
0x18000e104  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e10b  cmp     rcx, rbp
0x18000e10e  jz      short loc_18000E12E
0x18000e110  test    byte ptr [rcx+1Ch], 8
0x18000e114  jz      short loc_18000E12E
0x18000e116  mov     rcx, [rcx+10h]
0x18000e11a  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000e121  mov     edx, 1Ch
0x18000e126  mov     r9d, edi
0x18000e129  call    WPP_SF_d
0x18000e12e  mov     rbx, [rsp+28h+arg_0]
0x18000e133  mov     eax, edi
0x18000e135  mov     rbp, [rsp+28h+arg_8]
0x18000e13a  add     rsp, 20h
0x18000e13e  pop     rdi
0x18000e13f  retn
```
