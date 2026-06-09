# CIConnSink::~CIConnSink(void)

- ea: `0x1800b21ec`
- end: `0x1800b237c`
- name: `??1CIConnSink@@UEAA@XZ`
- size: `400`
- prototype: `void __fastcall(CIConnSink *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800b23b0`
- `0x1800b23f0`
- `0x1800b2440`

## callees

- `0x1800063b0`
- `0x1800b21ec`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b2364`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b2364`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b22f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b2340`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b22f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b2340`

## string_xrefs

- `0x1800b2232`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`
- `0x1800b2285`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`
- `0x1800b22de`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`
- `0x1800b2329`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CIConnSink::~CIConnSink(CIConnSink *this)
{
  char *v2; // rdi

  *(_QWORD *)this = &CIConnSink::`vftable';
  TraceStringInline(
    1,
    5,
    L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
    87,
    L"CIConnSink::~CIConnSink",
    0,
    L"Entering destructor for CIConnSink object this=%p",
    this);
  v2 = (char *)this + 120;
  (**((void (__fastcall ***)(char *))this + 15))((char *)this + 120);
  if ( *((_QWORD *)this + 10) )
  {
    TraceStringInline(
      1,
      5,
      L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
      94,
      L"CIConnSink::~CIConnSink",
      0,
      L"Releasing m_pISendReceiveSink=%p",
      *((_QWORD *)this + 10));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 16LL))(*((_QWORD *)this + 10));
    *((_QWORD *)this + 10) = 0;
  }
  if ( *((_QWORD *)this + 13) )
  {
    TraceStringInline(
      1,
      5,
      L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
      102,
      L"CIConnSink::~CIConnSink",
      0,
      L"Closing m_hSendReceiveEvent=0x%x",
      *((_QWORD *)this + 13));
    CloseHandle(*((HANDLE *)this + 13));
  }
  if ( *((_QWORD *)this + 14) )
  {
    TraceStringInline(
      1,
      5,
      L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
      108,
      L"CIConnSink::~CIConnSink",
      0,
      L"Closing m_hConnectionStatus=0x%x",
      *((_QWORD *)this + 14));
    CloseHandle(*((HANDLE *)this + 14));
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))((char *)this + 120);
  *(_QWORD *)v2 = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
}

```

## disassembly

```asm
0x1800b21ec  mov     r11, rsp
0x1800b21ef  mov     [r11+8], rbx
0x1800b21f3  mov     [r11+10h], rdi
0x1800b21f7  push    r12
0x1800b21f9  sub     rsp, 40h
0x1800b21fd  mov     rbx, rcx
0x1800b2200  lea     rax, ??_7CIConnSink@@6B@; const CIConnSink::`vftable'
0x1800b2207  mov     [rcx], rax
0x1800b220a  mov     [r11-10h], rcx
0x1800b220e  lea     rax, aEnteringDestru; "Entering destructor for CIConnSink obje"...
0x1800b2215  mov     [r11-18h], rax
0x1800b2219  mov     qword ptr [r11-20h], 0
0x1800b2221  lea     r12, aCiconnsinkCico; "CIConnSink::~CIConnSink"
0x1800b2228  mov     [r11-28h], r12
0x1800b222c  mov     r9d, 57h ; 'W'
0x1800b2232  lea     r8, aComComplusDtcD_109; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x1800b2239  lea     edx, [r9-52h]
0x1800b223d  lea     ecx, [rdx-4]
0x1800b2240  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b2245  lea     rdi, [rbx+78h]
0x1800b2249  mov     rax, [rdi]
0x1800b224c  mov     rcx, rdi
0x1800b224f  mov     rax, [rax]
0x1800b2252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2257  mov     rax, [rbx+50h]
0x1800b225b  test    rax, rax
0x1800b225e  jz      short loc_1800B22B0
0x1800b2260  mov     [rsp+48h+var_10], rax
0x1800b2265  lea     rax, aReleasingMPise; "Releasing m_pISendReceiveSink=%p"
0x1800b226c  mov     [rsp+48h+var_18], rax
0x1800b2271  mov     [rsp+48h+var_20], 0
0x1800b227a  mov     [rsp+48h+var_28], r12
0x1800b227f  mov     r9d, 5Eh ; '^'
0x1800b2285  lea     r8, aComComplusDtcD_109; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x1800b228c  lea     edx, [r9-59h]
0x1800b2290  lea     ecx, [rdx-4]
0x1800b2293  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b2298  mov     rcx, [rbx+50h]
0x1800b229c  mov     rax, [rcx]
0x1800b229f  mov     rax, [rax+10h]
0x1800b22a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b22a8  mov     qword ptr [rbx+50h], 0
0x1800b22b0  mov     rax, [rbx+68h]
0x1800b22b4  test    rax, rax
0x1800b22b7  jz      short loc_1800B22FB
0x1800b22b9  mov     [rsp+48h+var_10], rax
0x1800b22be  lea     rax, aClosingMHsendr; "Closing m_hSendReceiveEvent=0x%x"
0x1800b22c5  mov     [rsp+48h+var_18], rax
0x1800b22ca  mov     [rsp+48h+var_20], 0
0x1800b22d3  mov     [rsp+48h+var_28], r12
0x1800b22d8  mov     r9d, 66h ; 'f'
0x1800b22de  lea     r8, aComComplusDtcD_109; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x1800b22e5  lea     edx, [r9-61h]
0x1800b22e9  lea     ecx, [rdx-4]
0x1800b22ec  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b22f1  mov     rcx, [rbx+68h]; hObject
0x1800b22f5  call    cs:__imp_CloseHandle
0x1800b22fb  mov     rax, [rbx+70h]
0x1800b22ff  test    rax, rax
0x1800b2302  jz      short loc_1800B2346
0x1800b2304  mov     [rsp+48h+var_10], rax
0x1800b2309  lea     rax, aClosingMHconne; "Closing m_hConnectionStatus=0x%x"
0x1800b2310  mov     [rsp+48h+var_18], rax
0x1800b2315  mov     [rsp+48h+var_20], 0
0x1800b231e  mov     [rsp+48h+var_28], r12
0x1800b2323  mov     r9d, 6Ch ; 'l'
0x1800b2329  lea     r8, aComComplusDtcD_109; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x1800b2330  lea     edx, [r9-67h]
0x1800b2334  lea     ecx, [rdx-4]
0x1800b2337  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b233c  mov     rcx, [rbx+70h]; hObject
0x1800b2340  call    cs:__imp_CloseHandle
0x1800b2346  mov     rax, [rdi]
0x1800b2349  mov     rcx, rdi
0x1800b234c  mov     rax, [rax+8]
0x1800b2350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2355  nop
0x1800b2356  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x1800b235d  mov     [rdi], rax
0x1800b2360  lea     rcx, [rdi+8]; lpCriticalSection
0x1800b2364  call    cs:__imp_DeleteCriticalSection
0x1800b236a  nop
0x1800b236b  mov     rbx, [rsp+48h+arg_0]
0x1800b2370  mov     rdi, [rsp+48h+arg_8]
0x1800b2375  add     rsp, 40h
0x1800b2379  pop     r12
0x1800b237b  retn
```
