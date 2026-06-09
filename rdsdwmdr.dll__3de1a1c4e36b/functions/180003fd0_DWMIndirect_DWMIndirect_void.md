# DWMIndirect::~DWMIndirect(void)

- ea: `0x180003fd0`
- end: `0x180004128`
- name: `??1DWMIndirect@@MEAA@XZ`
- size: `344`
- prototype: `void __fastcall(DWMIndirect *this, __int64, unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800041ec`

## callees

- `0x180001bfc`
- `0x180003fac`
- `0x180003fd0`
- `0x180005fcc`
- `0x180019a6c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004098`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004098`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040d2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800040c3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800040c3`
- `GDI32!DeleteDC` at `0x1800040a7`
- `GDI32!DeleteDC` at `0x1800040b6`
- `GDI32!DeleteDC` at `0x1800040a7`
- `GDI32!DeleteDC` at `0x1800040b6`
- `GDI32!DeleteObject` at `0x18000405f`
- `GDI32!DeleteObject` at `0x180004077`
- `GDI32!DeleteObject` at `0x180004089`
- `GDI32!DeleteObject` at `0x18000405f`
- `GDI32!DeleteObject` at `0x180004077`
- `GDI32!DeleteObject` at `0x180004089`

## pseudocode

```c
void __fastcall DWMIndirect::~DWMIndirect(DWMIndirect *this, __int64 a2, unsigned __int16 *a3, __int64 a4)
{
  __int64 i; // rdi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  HDC v10; // rcx
  HDC v11; // rcx
  void *v12; // rcx
  __int64 v13; // rcx
  DWMIndirect *v14; // [rsp+40h] [rbp+8h] BYREF
  const char *v15; // [rsp+48h] [rbp+10h] BYREF

  *(_QWORD *)this = &DWMIndirect::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 1) = &DWMIndirect::`vftable'{for `CTSObject'};
  *((_QWORD *)this + 6) = &DWMIndirect::`vftable';
  if ( (unsigned int)dword_180044008 > 4 )
  {
    v14 = this;
    v15 = "Destroying DWMIndirect instance %p.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)this,
      (__int64)byte_18003797B,
      (__int64)a3,
      a4,
      (const unsigned __int16 **)&v15,
      (__int64)&v14);
  }
  RDSDWMDirectTraceLogging::LogDWMIndirectDestroy(
    (RDSDWMDirectTraceLogging *)&stru_1800440EC,
    (struct _GUID *)((char *)this + 836),
    a3);
  DWMIndirect::StopSyncThread(this);
  for ( i = 0; i != 3; ++i )
  {
    v6 = (void *)*((_QWORD *)this + i + 29);
    if ( v6 )
      DeleteObject(v6);
  }
  v7 = (void *)*((_QWORD *)this + 11);
  if ( v7 )
    DeleteObject(v7);
  v8 = (void *)*((_QWORD *)this + 103);
  if ( v8 )
    DeleteObject(v8);
  v9 = (void *)*((_QWORD *)this + 8);
  if ( v9 )
    CloseHandle(v9);
  v10 = (HDC)*((_QWORD *)this + 10);
  if ( v10 )
    DeleteDC(v10);
  v11 = (HDC)*((_QWORD *)this + 9);
  if ( v11 )
    DeleteDC(v11);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v12 = (void *)*((_QWORD *)this + 15);
  if ( v12 )
    CloseHandle(v12);
  v13 = *((_QWORD *)this + 114);
  if ( v13 )
  {
    *((_QWORD *)this + 114) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  TSRegisteredObject<DWMIndirect,32>::~TSRegisteredObject<DWMIndirect,32>((char *)this + 56);
  *(_QWORD *)this = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
  *((_DWORD *)this + 7) |= 8u;
  *((_QWORD *)this + 1) = &CTSObject::`vftable';
}

```

## disassembly

```asm
0x180003fd0  mov     r11, rsp
0x180003fd3  mov     [r11+18h], rbx
0x180003fd7  push    rdi
0x180003fd8  sub     rsp, 30h
0x180003fdc  lea     rax, ??_7DWMIndirect@@6BINonDelegatingUnknown@@@; const DWMIndirect::`vftable'{for `INonDelegatingUnknown'}
0x180003fe3  mov     rbx, rcx
0x180003fe6  mov     [rcx], rax
0x180003fe9  lea     rax, ??_7DWMIndirect@@6BCTSObject@@@; const DWMIndirect::`vftable'{for `CTSObject'}
0x180003ff0  mov     [rcx+8], rax
0x180003ff4  lea     rax, ??_7DWMIndirect@@6B@; const DWMIndirect::`vftable'
0x180003ffb  mov     [rcx+30h], rax
0x180003fff  mov     eax, cs:dword_180044008
0x180004005  cmp     eax, 4
0x180004008  jbe     short loc_180004035
0x18000400a  lea     rax, aDestroyingDwmi; "Destroying DWMIndirect instance %p."
0x180004011  mov     [r11+8], rcx
0x180004015  mov     [r11+10h], rax
0x180004019  lea     rdx, byte_18003797B
0x180004020  lea     rax, [r11+8]
0x180004024  mov     [r11-10h], rax
0x180004028  lea     rax, [r11+10h]
0x18000402c  mov     [r11-18h], rax
0x180004030  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180004035  lea     rdx, [rbx+344h]; struct _GUID *
0x18000403c  lea     rcx, stru_1800440EC; this
0x180004043  call    ?LogDWMIndirectDestroy@RDSDWMDirectTraceLogging@@YAXPEAU_GUID@@PEAG@Z; RDSDWMDirectTraceLogging::LogDWMIndirectDestroy(_GUID *,ushort *)
0x180004048  mov     rcx, rbx; this
0x18000404b  call    ?StopSyncThread@DWMIndirect@@IEAAXXZ; DWMIndirect::StopSyncThread(void)
0x180004050  xor     edi, edi
0x180004052  mov     rcx, [rbx+rdi*8+0E8h]; ho
0x18000405a  test    rcx, rcx
0x18000405d  jz      short loc_180004065
0x18000405f  call    cs:__imp_DeleteObject
0x180004065  inc     rdi
0x180004068  cmp     rdi, 3
0x18000406c  jnz     short loc_180004052
0x18000406e  mov     rcx, [rbx+58h]; ho
0x180004072  test    rcx, rcx
0x180004075  jz      short loc_18000407D
0x180004077  call    cs:__imp_DeleteObject
0x18000407d  mov     rcx, [rbx+338h]; ho
0x180004084  test    rcx, rcx
0x180004087  jz      short loc_18000408F
0x180004089  call    cs:__imp_DeleteObject
0x18000408f  mov     rcx, [rbx+40h]; hObject
0x180004093  test    rcx, rcx
0x180004096  jz      short loc_18000409E
0x180004098  call    cs:__imp_CloseHandle
0x18000409e  mov     rcx, [rbx+50h]; hdc
0x1800040a2  test    rcx, rcx
0x1800040a5  jz      short loc_1800040AD
0x1800040a7  call    cs:__imp_DeleteDC
0x1800040ad  mov     rcx, [rbx+48h]; hdc
0x1800040b1  test    rcx, rcx
0x1800040b4  jz      short loc_1800040BC
0x1800040b6  call    cs:__imp_DeleteDC
0x1800040bc  lea     rcx, [rbx+88h]; lpCriticalSection
0x1800040c3  call    cs:__imp_DeleteCriticalSection
0x1800040c9  mov     rcx, [rbx+78h]; hObject
0x1800040cd  test    rcx, rcx
0x1800040d0  jz      short loc_1800040D8
0x1800040d2  call    cs:__imp_CloseHandle
0x1800040d8  mov     rcx, [rbx+390h]
0x1800040df  test    rcx, rcx
0x1800040e2  jz      short loc_1800040FB
0x1800040e4  mov     qword ptr [rbx+390h], 0
0x1800040ef  mov     rax, [rcx]
0x1800040f2  mov     rax, [rax+10h]
0x1800040f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040fb  lea     rcx, [rbx+38h]
0x1800040ff  call    ??1?$TSRegisteredObject@VDWMIndirect@@$0CA@@@QEAA@XZ; TSRegisteredObject<DWMIndirect,32>::~TSRegisteredObject<DWMIndirect,32>(void)
0x180004104  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x18000410b  mov     [rbx], rax
0x18000410e  lea     rax, ??_7CTSObject@@6B@; const CTSObject::`vftable'
0x180004115  or      dword ptr [rbx+1Ch], 8
0x180004119  mov     [rbx+8], rax
0x18000411d  mov     rbx, [rsp+38h+arg_10]
0x180004122  add     rsp, 30h
0x180004126  pop     rdi
0x180004127  retn
```
