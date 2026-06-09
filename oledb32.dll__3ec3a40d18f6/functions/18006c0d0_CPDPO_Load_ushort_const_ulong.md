# CPDPO::Load(ushort const *,ulong)

- ea: `0x18006c0d0`
- end: `0x18006c22c`
- name: `?Load@CPDPO@@UEAAJPEBGK@Z`
- size: `348`
- prototype: `__int64 __fastcall(CPDPO *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180013870`
- `0x180029560`
- `0x180069dfc`
- `0x18006ac14`
- `0x18006bf04`
- `0x18006c0d0`
- `0x180087010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18006c0f3`
- `KERNEL32!EnterCriticalSection` at `0x18006c0f3`
- `KERNEL32!LeaveCriticalSection` at `0x18006c155`
- `KERNEL32!LeaveCriticalSection` at `0x18006c1f1`
- `KERNEL32!LeaveCriticalSection` at `0x18006c155`
- `KERNEL32!LeaveCriticalSection` at `0x18006c1f1`
- `ole32!CoTaskMemFree` at `0x18006c1e8`
- `ole32!CoTaskMemFree` at `0x18006c1e8`

## pseudocode

```c
__int64 __fastcall CPDPO::Load(CPDPO *this, const unsigned __int16 *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  CUdlCacheMap *v5; // rcx
  int StringFromStorage; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  struct IUnknown *v9; // rax
  const struct _GUID *v10; // r9
  int DataSourceForPDPO; // eax
  LPVOID pv; // [rsp+70h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  pv = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v5 = (CUdlCacheMap *)*((_QWORD *)this + 9);
  if ( v5 )
  {
    (*(void (__fastcall **)(CUdlCacheMap *))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 11) = 0;
  }
  StringFromStorage = CUdlCacheMap::LoadStringFromStorage(v5, a2, (unsigned __int16 **)&pv);
  v7 = StringFromStorage;
  if ( StringFromStorage >= 0 )
  {
    v9 = (struct IUnknown *)(*(__int64 (__fastcall **)(CPDPO *))(*(_QWORD *)this + 72LL))(this);
    DataSourceForPDPO = GetDataSourceForPDPO(v9, 0x15u, (const unsigned __int16 *)pv, v10, (struct IUnknown **)this + 9);
    v7 = DataSourceForPDPO;
    if ( DataSourceForPDPO < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(DataSourceForPDPO, L"<CPDPO::Load|OLEDB|ERR> ", 0x8Fu);
    }
    else
    {
      CPDPO::GetProviderInterface(this, &IID_IDBInitialize, (struct IUnknown **)this + 10);
      CPDPO::GetProviderInterface(this, &IID_IDBProperties, (struct IUnknown **)this + 11);
    }
    CoTaskMemFree(pv);
    LeaveCriticalSection(v2);
    if ( (bidGblFlags & 2) != 0 )
    {
      v8 = 152585;
      return (unsigned int)bidTraceHR(off_1800C8470[0], v8, L"<CPDPO::Load|Trace|HR> ", v7);
    }
  }
  else
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(StringFromStorage, L"<CPDPO::Load|OLEDB|ERR> ", 0x7Au);
    LeaveCriticalSection(v2);
    if ( (bidGblFlags & 2) != 0 )
    {
      v8 = 126985;
      return (unsigned int)bidTraceHR(off_1800C8470[0], v8, L"<CPDPO::Load|Trace|HR> ", v7);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18006c0d0  push    rbx
0x18006c0d2  push    rbp
0x18006c0d3  push    rsi
0x18006c0d4  push    rdi
0x18006c0d5  push    r14
0x18006c0d7  push    r15
0x18006c0d9  sub     rsp, 38h
0x18006c0dd  lea     rsi, [rcx+20h]
0x18006c0e1  mov     [rsp+68h+pv], 0
0x18006c0ea  mov     rdi, rcx
0x18006c0ed  mov     rbx, rdx
0x18006c0f0  mov     rcx, rsi; lpCriticalSection
0x18006c0f3  call    cs:__imp_EnterCriticalSection
0x18006c0f9  lea     rbp, [rdi+48h]
0x18006c0fd  mov     rcx, [rbp+0]
0x18006c101  test    rcx, rcx
0x18006c104  jz      short loc_18006C122
0x18006c106  mov     rax, [rcx]
0x18006c109  mov     rax, [rax+10h]
0x18006c10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c112  mov     qword ptr [rdi+50h], 0
0x18006c11a  mov     qword ptr [rdi+58h], 0
0x18006c122  lea     r8, [rsp+68h+pv]; unsigned __int16 **
0x18006c127  mov     rdx, rbx; unsigned __int16 *
0x18006c12a  call    ?LoadStringFromStorage@CUdlCacheMap@@QEAAJPEBGPEAPEAG@Z; CUdlCacheMap::LoadStringFromStorage(ushort const *,ushort * *)
0x18006c12f  mov     ebx, eax
0x18006c131  test    eax, eax
0x18006c133  jns     short loc_18006C172
0x18006c135  test    byte ptr cs:_bidGblFlags, 2
0x18006c13c  jz      short loc_18006C152
0x18006c13e  mov     r8d, 7Ah ; 'z'; unsigned int
0x18006c144  lea     rdx, aCpdpoLoadOledb; "<CPDPO::Load|OLEDB|ERR> "
0x18006c14b  mov     ecx, eax; int
0x18006c14d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006c152  mov     rcx, rsi; lpCriticalSection
0x18006c155  call    cs:__imp_LeaveCriticalSection
0x18006c15b  test    byte ptr cs:_bidGblFlags, 2
0x18006c162  jz      loc_18006C21D
0x18006c168  mov     edx, 1F009h
0x18006c16d  jmp     loc_18006C205
0x18006c172  mov     rax, [rdi]
0x18006c175  mov     rcx, rdi
0x18006c178  mov     rax, [rax+48h]
0x18006c17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c181  mov     r8, [rsp+68h+pv]; unsigned __int16 *
0x18006c186  mov     edx, 15h; unsigned int
0x18006c18b  mov     rcx, rax; struct IUnknown *
0x18006c18e  mov     [rsp+68h+var_48], rbp; struct IUnknown **
0x18006c193  call    ?GetDataSourceForPDPO@@YAJPEAUIUnknown@@KPEBGAEBU_GUID@@PEAPEAU1@@Z; GetDataSourceForPDPO(IUnknown *,ulong,ushort const *,_GUID const &,IUnknown * *)
0x18006c198  mov     ebx, eax
0x18006c19a  test    eax, eax
0x18006c19c  js      short loc_18006C1C6
0x18006c19e  lea     r8, [rdi+50h]; struct IUnknown **
0x18006c1a2  mov     rcx, rdi; this
0x18006c1a5  lea     rdx, IID_IDBInitialize; struct _GUID *
0x18006c1ac  call    ?GetProviderInterface@CPDPO@@QEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z; CPDPO::GetProviderInterface(_GUID const &,IUnknown * *)
0x18006c1b1  lea     r8, [rdi+58h]; struct IUnknown **
0x18006c1b5  mov     rcx, rdi; this
0x18006c1b8  lea     rdx, IID_IDBProperties; struct _GUID *
0x18006c1bf  call    ?GetProviderInterface@CPDPO@@QEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z; CPDPO::GetProviderInterface(_GUID const &,IUnknown * *)
0x18006c1c4  jmp     short loc_18006C1E3
0x18006c1c6  test    byte ptr cs:_bidGblFlags, 2
0x18006c1cd  jz      short loc_18006C1E3
0x18006c1cf  mov     r8d, 8Fh; unsigned int
0x18006c1d5  lea     rdx, aCpdpoLoadOledb; "<CPDPO::Load|OLEDB|ERR> "
0x18006c1dc  mov     ecx, ebx; int
0x18006c1de  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006c1e3  mov     rcx, [rsp+68h+pv]; pv
0x18006c1e8  call    cs:__imp_CoTaskMemFree
0x18006c1ee  mov     rcx, rsi; lpCriticalSection
0x18006c1f1  call    cs:__imp_LeaveCriticalSection
0x18006c1f7  test    byte ptr cs:_bidGblFlags, 2
0x18006c1fe  jz      short loc_18006C21D
0x18006c200  mov     edx, 25409h
0x18006c205  mov     rcx, cs:off_1800C8470; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006c20c  lea     r8, aCpdpoLoadTrace; "<CPDPO::Load|Trace|HR> "
0x18006c213  mov     r9d, ebx
0x18006c216  call    _bidTraceHR
0x18006c21b  mov     ebx, eax
0x18006c21d  mov     eax, ebx
0x18006c21f  add     rsp, 38h
0x18006c223  pop     r15
0x18006c225  pop     r14
0x18006c227  pop     rdi
0x18006c228  pop     rsi
0x18006c229  pop     rbp
0x18006c22a  pop     rbx
0x18006c22b  retn
```
