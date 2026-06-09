# CADMCOMW::Init(void)

- ea: `0x1800068d4`
- end: `0x180006c06`
- name: `?Init@CADMCOMW@@QEAAJXZ`
- size: `818`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180009dd0`

## callees

- `0x180001064`
- `0x1800010b0`
- `0x1800010bc`
- `0x1800068d4`
- `0x180006c0c`
- `0x1800097e4`
- `0x18000d6a4`
- `0x18000fb1e`
- `0x180010010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000692b`
- `ole32!CoCreateInstance` at `0x180006a59`
- `ole32!CoCreateInstance` at `0x18000692b`
- `ole32!CoCreateInstance` at `0x180006a59`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x1800068fe`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x1800068fe`
- `KERNEL32!LeaveCriticalSection` at `0x180006b8f`
- `KERNEL32!LeaveCriticalSection` at `0x180006b8f`
- `KERNEL32!EnterCriticalSection` at `0x180006b3f`
- `KERNEL32!EnterCriticalSection` at `0x180006b3f`
- `IisRTL!PuDbgPrint` at `0x1800069cf`
- `IisRTL!PuDbgPrint` at `0x1800069cf`

## string_xrefs

- `0x18000694e`: ` CoCreateInstance(MDCOM) failed, error 0x%08x\n`
- `0x1800069bc`: `CADMCOMW::Init`
- `0x1800069c3`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x1800069a8`: `CImpIMDCOMSINKW failed, error 0x%08x\n`

## pseudocode

```c
__int64 __fastcall CADMCOMW::Init(CADMCOMW *this)
{
  HRESULT FreeThreadedMarshaler; // edi
  _QWORD *v3; // r14
  HRESULT Instance; // eax
  _DWORD *v5; // rax
  int v6; // eax
  void *v7; // rax
  void *v8; // rsi
  int v9; // eax
  struct _LIST_ENTRY *Flink; // rcx
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF
  __int64 v13; // [rsp+58h] [rbp+10h] BYREF

  v12 = 0;
  v13 = 0;
  FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler((LPUNKNOWN)this, (LPUNKNOWN *)this + 3);
  if ( FreeThreadedMarshaler < 0 )
    goto LABEL_28;
  v3 = (_QWORD *)((char *)this + 32);
  Instance = CoCreateInstance(&CLSID_MDCOM, 0, 1u, &IID_IMDCOM3, (LPVOID *)this + 4);
  FreeThreadedMarshaler = Instance;
  if ( Instance < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        116,
        "CADMCOMW::Init",
        " CoCreateInstance(MDCOM) failed, error 0x%08x\n",
        Instance);
    goto LABEL_28;
  }
  v5 = operator new(0x20u);
  if ( v5 )
  {
    v5[4] = 1;
    *(_QWORD *)v5 = &CImpIMDCOMSINKW::`vftable';
    v5[5] = 0;
    v5[6] = 0;
    *((_QWORD *)v5 + 1) = this;
  }
  *((_QWORD *)this + 11) = v5;
  if ( !v5 )
  {
    FreeThreadedMarshaler = -2147024882;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        123,
        "CADMCOMW::Init",
        "CImpIMDCOMSINKW failed, error 0x%08x\n",
        -2147024882);
    goto LABEL_28;
  }
  *((_QWORD *)this + 99) = this;
  v6 = *((_DWORD *)this + 220);
  *((_QWORD *)this + 103) = this;
  *((_QWORD *)this + 104) = this;
  if ( v6 )
  {
    FreeThreadedMarshaler = -2147418113;
LABEL_27:
    COConnectionPoint::Terminate((CADMCOMW *)((char *)this + 840), 0);
    goto LABEL_28;
  }
  *((_QWORD *)this + 107) = this;
  v7 = operator new[](0x40u);
  v8 = v7;
  if ( !v7 )
  {
    FreeThreadedMarshaler = -2147024882;
    goto LABEL_27;
  }
  memset_0(v7, 0, 0x40u);
  FreeThreadedMarshaler = CoCreateInstance(
                            &CLSID_StdGlobalInterfaceTable,
                            0,
                            1u,
                            &IID_IGlobalInterfaceTable,
                            (LPVOID *)this + 111);
  if ( FreeThreadedMarshaler < 0 )
  {
    operator delete[](v8);
    goto LABEL_27;
  }
  *((_DWORD *)this + 217) = 8;
  *((_QWORD *)this + 109) = v8;
  v9 = CADMCOMW::InitializeCallerWatch(this);
  FreeThreadedMarshaler = v9;
  if ( v9 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        149,
        "CADMCOMW::Init",
        "InitializeCallerWatch() failed hr=0x%08x.\n",
        v9);
    goto LABEL_28;
  }
  FreeThreadedMarshaler = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v3)(
                            *v3,
                            &IID_IConnectionPointContainer,
                            &v12);
  if ( FreeThreadedMarshaler < 0
    || (FreeThreadedMarshaler = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v12 + 32LL))(
                                  v12,
                                  &IID_IMDCOMSINK_W,
                                  &v13),
        FreeThreadedMarshaler < 0)
    || (FreeThreadedMarshaler = (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v13 + 40LL))(
                                  v13,
                                  *((_QWORD *)this + 11),
                                  (char *)this + 96),
        FreeThreadedMarshaler < 0)
    || (FreeThreadedMarshaler = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v3 + 536LL))(
                                  *v3,
                                  (char *)this + 164),
        FreeThreadedMarshaler < 0) )
  {
LABEL_28:
    CADMCOMW::StopNotifications(this, 1);
    goto LABEL_29;
  }
  EnterCriticalSection(&CADMCOMW::sm_csObjectListLock);
  (*(void (__fastcall **)(CADMCOMW *))(*(_QWORD *)this + 8LL))(this);
  Flink = CADMCOMW::sm_ObjectList.Flink;
  if ( CADMCOMW::sm_ObjectList.Flink->Blink != &CADMCOMW::sm_ObjectList )
    __fastfail(3u);
  *((_QWORD *)this + 18) = CADMCOMW::sm_ObjectList.Flink;
  *((_QWORD *)this + 19) = &CADMCOMW::sm_ObjectList;
  Flink->Blink = (struct _LIST_ENTRY *)((char *)this + 144);
  CADMCOMW::sm_ObjectList.Flink = (struct _LIST_ENTRY *)((char *)this + 144);
  LeaveCriticalSection(&CADMCOMW::sm_csObjectListLock);
  FreeThreadedMarshaler = 0;
LABEL_29:
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)FreeThreadedMarshaler;
}

```

## disassembly

```asm
0x1800068d4  mov     rax, rsp
0x1800068d7  mov     [rax+18h], rbx
0x1800068db  mov     [rax+20h], rbp
0x1800068df  push    rsi
0x1800068e0  push    rdi
0x1800068e1  push    r14
0x1800068e3  sub     rsp, 30h
0x1800068e7  lea     rdx, [rcx+18h]; ppunkMarshal
0x1800068eb  mov     qword ptr [rax+8], 0
0x1800068f3  mov     rbx, rcx
0x1800068f6  mov     qword ptr [rax+10h], 0
0x1800068fe  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180006904  mov     edi, eax
0x180006906  test    eax, eax
0x180006908  js      loc_180006BAF
0x18000690e  xor     edx, edx; pUnkOuter
0x180006910  lea     r14, [rbx+20h]
0x180006914  lea     r9, IID_IMDCOM3; riid
0x18000691b  mov     [rsp+48h+ppv], r14; ppv
0x180006920  lea     rcx, CLSID_MDCOM; rclsid
0x180006927  lea     r8d, [rdx+1]; dwClsContext
0x18000692b  call    cs:__imp_CoCreateInstance
0x180006931  mov     edi, eax
0x180006933  test    eax, eax
0x180006935  jns     short loc_180006957
0x180006937  test    byte ptr cs:g_dwDebugFlags, 3
0x18000693e  jz      loc_180006BAF
0x180006944  mov     [rsp+48h+var_20], eax
0x180006948  mov     r8d, 74h ; 't'
0x18000694e  lea     rax, aCocreateinstan; " CoCreateInstance(MDCOM) failed, error "...
0x180006955  jmp     short loc_1800069B5
0x180006957  mov     ecx, 20h ; ' '; Size
0x18000695c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006961  test    rax, rax
0x180006964  jz      short loc_180006989
0x180006966  lea     rcx, ??_7CImpIMDCOMSINKW@@6B@; const CImpIMDCOMSINKW::`vftable'
0x18000696d  mov     dword ptr [rax+10h], 1
0x180006974  mov     [rax], rcx
0x180006977  mov     dword ptr [rax+14h], 0
0x18000697e  mov     dword ptr [rax+18h], 0
0x180006985  mov     [rax+8], rbx
0x180006989  mov     [rbx+58h], rax
0x18000698d  test    rax, rax
0x180006990  jnz     short loc_1800069DA
0x180006992  test    byte ptr cs:g_dwDebugFlags, 3
0x180006999  mov     edi, 8007000Eh
0x18000699e  jz      loc_180006BAF
0x1800069a4  mov     [rsp+48h+var_20], edi
0x1800069a8  lea     rax, aCimpimdcomsink; "CImpIMDCOMSINKW failed, error 0x%08x\n"
0x1800069af  mov     r8d, 7Bh ; '{'
0x1800069b5  mov     rcx, cs:g_pDebug
0x1800069bc  lea     r9, aCadmcomwInit; "CADMCOMW::Init"
0x1800069c3  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x1800069ca  mov     [rsp+48h+ppv], rax
0x1800069cf  call    cs:__imp_PuDbgPrint
0x1800069d5  jmp     loc_180006BAF
0x1800069da  lea     rbp, [rbx+348h]
0x1800069e1  mov     [rbx+318h], rbx
0x1800069e8  mov     eax, [rbp+28h]
0x1800069eb  mov     [rbx+338h], rbx
0x1800069f2  mov     [rbx+340h], rbx
0x1800069f9  test    eax, eax
0x1800069fb  jz      short loc_180006A07
0x1800069fd  mov     edi, 8000FFFFh
0x180006a02  jmp     loc_180006BA1
0x180006a07  mov     edi, 40h ; '@'
0x180006a0c  mov     [rbx+358h], rbx
0x180006a13  mov     ecx, edi; unsigned __int64
0x180006a15  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180006a1a  mov     rsi, rax
0x180006a1d  test    rax, rax
0x180006a20  jnz     short loc_180006A2C
0x180006a22  mov     edi, 8007000Eh
0x180006a27  jmp     loc_180006BA1
0x180006a2c  mov     r8, rdi; Size
0x180006a2f  xor     edx, edx; Val
0x180006a31  mov     rcx, rsi; void *
0x180006a34  call    memset_0
0x180006a39  xor     edx, edx; pUnkOuter
0x180006a3b  lea     rax, [rbx+378h]
0x180006a42  lea     r9, IID_IGlobalInterfaceTable; riid
0x180006a49  mov     [rsp+48h+ppv], rax; ppv
0x180006a4e  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180006a55  lea     r8d, [rdx+1]; dwClsContext
0x180006a59  call    cs:__imp_CoCreateInstance
0x180006a5f  mov     edi, eax
0x180006a61  test    eax, eax
0x180006a63  js      loc_180006B99
0x180006a69  mov     rcx, rbx; Context
0x180006a6c  mov     dword ptr [rbx+364h], 8
0x180006a76  mov     [rbx+368h], rsi
0x180006a7d  call    ?InitializeCallerWatch@CADMCOMW@@AEAAJXZ; CADMCOMW::InitializeCallerWatch(void)
0x180006a82  mov     edi, eax
0x180006a84  test    eax, eax
0x180006a86  jns     short loc_180006AAB
0x180006a88  test    byte ptr cs:g_dwDebugFlags, 3
0x180006a8f  jz      loc_180006BAF
0x180006a95  mov     [rsp+48h+var_20], eax
0x180006a99  mov     r8d, 95h
0x180006a9f  lea     rax, aInitializecall; "InitializeCallerWatch() failed hr=0x%08"...
0x180006aa6  jmp     loc_1800069B5
0x180006aab  mov     rcx, [r14]
0x180006aae  lea     r8, [rsp+48h+arg_0]
0x180006ab3  lea     rdx, IID_IConnectionPointContainer
0x180006aba  mov     rax, [rcx]
0x180006abd  mov     rax, [rax]
0x180006ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ac5  mov     edi, eax
0x180006ac7  test    eax, eax
0x180006ac9  js      loc_180006BAF
0x180006acf  mov     rcx, [rsp+48h+arg_0]
0x180006ad4  lea     r8, [rsp+48h+arg_8]
0x180006ad9  lea     rdx, IID_IMDCOMSINK_W
0x180006ae0  mov     rax, [rcx]
0x180006ae3  mov     rax, [rax+20h]
0x180006ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aec  mov     edi, eax
0x180006aee  test    eax, eax
0x180006af0  js      loc_180006BAF
0x180006af6  mov     rcx, [rsp+48h+arg_8]
0x180006afb  lea     r8, [rbx+60h]
0x180006aff  mov     rdx, [rbx+58h]
0x180006b03  mov     rax, [rcx]
0x180006b06  mov     rax, [rax+28h]
0x180006b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b0f  mov     edi, eax
0x180006b11  test    eax, eax
0x180006b13  js      loc_180006BAF
0x180006b19  mov     rcx, [r14]
0x180006b1c  lea     rdx, [rbx+0A4h]
0x180006b23  mov     rax, [rcx]
0x180006b26  mov     rax, [rax+218h]
0x180006b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b32  mov     edi, eax
0x180006b34  test    eax, eax
0x180006b36  js      short loc_180006BAF
0x180006b38  lea     rcx, ?sm_csObjectListLock@CADMCOMW@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180006b3f  call    cs:__imp_EnterCriticalSection
0x180006b45  mov     rax, [rbx]
0x180006b48  mov     rcx, rbx
0x180006b4b  mov     rax, [rax+8]
0x180006b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b54  mov     rcx, qword ptr cs:?sm_ObjectList@CADMCOMW@@2U_LIST_ENTRY@@A; _LIST_ENTRY CADMCOMW::sm_ObjectList
0x180006b5b  lea     rdx, ?sm_ObjectList@CADMCOMW@@2U_LIST_ENTRY@@A; _LIST_ENTRY CADMCOMW::sm_ObjectList
0x180006b62  cmp     [rcx+8], rdx
0x180006b66  jz      short loc_180006B6F
0x180006b68  mov     ecx, 3
0x180006b6d  int     29h; Win8: RtlFailFast(ecx)
0x180006b6f  lea     rax, [rbx+90h]
0x180006b76  mov     [rax], rcx
0x180006b79  mov     [rax+8], rdx
0x180006b7d  mov     [rcx+8], rax
0x180006b81  lea     rcx, ?sm_csObjectListLock@CADMCOMW@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180006b88  mov     qword ptr cs:?sm_ObjectList@CADMCOMW@@2U_LIST_ENTRY@@A, rax; _LIST_ENTRY CADMCOMW::sm_ObjectList
0x180006b8f  call    cs:__imp_LeaveCriticalSection
0x180006b95  xor     edi, edi
0x180006b97  jmp     short loc_180006BBC
0x180006b99  mov     rcx, rsi; Block
0x180006b9c  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180006ba1  xor     edx, edx; int
0x180006ba3  mov     rcx, rbp; this
0x180006ba6  call    ?Terminate@COConnectionPoint@@QEAAJH@Z; COConnectionPoint::Terminate(int)
0x180006bab  test    edi, edi
0x180006bad  jns     short loc_180006BBC
0x180006baf  mov     edx, 1; int
0x180006bb4  mov     rcx, rbx; this
0x180006bb7  call    ?StopNotifications@CADMCOMW@@AEAAJH@Z; CADMCOMW::StopNotifications(int)
0x180006bbc  mov     rcx, [rsp+48h+arg_0]
0x180006bc1  test    rcx, rcx
0x180006bc4  jz      short loc_180006BDB
0x180006bc6  mov     rax, [rcx]
0x180006bc9  mov     rax, [rax+10h]
0x180006bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bd2  mov     [rsp+48h+arg_0], 0
0x180006bdb  mov     rcx, [rsp+48h+arg_8]
0x180006be0  test    rcx, rcx
0x180006be3  jz      short loc_180006BF1
0x180006be5  mov     rax, [rcx]
0x180006be8  mov     rax, [rax+10h]
0x180006bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bf1  mov     rbx, [rsp+48h+arg_10]
0x180006bf6  mov     eax, edi
0x180006bf8  mov     rbp, [rsp+48h+arg_18]
0x180006bfd  add     rsp, 30h
0x180006c01  pop     r14
0x180006c03  pop     rdi
0x180006c04  pop     rsi
0x180006c05  retn
```
