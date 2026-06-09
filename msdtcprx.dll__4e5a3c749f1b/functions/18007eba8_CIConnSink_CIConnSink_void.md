# CIConnSink::~CIConnSink(void)

- ea: `0x18007eba8`
- end: `0x18007ed38`
- name: `??1CIConnSink@@UEAA@XZ`
- size: `400`
- prototype: `void __fastcall(CIConnSink *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18007ed70`
- `0x18007edb0`

## callees

- `0x180003cf0`
- `0x18007eba8`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007ed20`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007ed20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ecb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ecfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ecb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ecfc`

## string_xrefs

- `0x18007ebee`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`
- `0x18007ec41`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`
- `0x18007ec9a`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`
- `0x18007ece5`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`

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
0x18007eba8  mov     r11, rsp
0x18007ebab  mov     [r11+8], rbx
0x18007ebaf  mov     [r11+10h], rdi
0x18007ebb3  push    r12
0x18007ebb5  sub     rsp, 40h
0x18007ebb9  mov     rbx, rcx
0x18007ebbc  lea     rax, ??_7CIConnSink@@6B@; const CIConnSink::`vftable'
0x18007ebc3  mov     [rcx], rax
0x18007ebc6  mov     [r11-10h], rcx
0x18007ebca  lea     rax, aEnteringDestru; "Entering destructor for CIConnSink obje"...
0x18007ebd1  mov     [r11-18h], rax
0x18007ebd5  mov     qword ptr [r11-20h], 0
0x18007ebdd  lea     r12, aCiconnsinkCico; "CIConnSink::~CIConnSink"
0x18007ebe4  mov     [r11-28h], r12
0x18007ebe8  mov     r9d, 57h ; 'W'
0x18007ebee  lea     r8, aComComplusDtcD_44; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x18007ebf5  lea     edx, [r9-52h]
0x18007ebf9  lea     ecx, [rdx-4]
0x18007ebfc  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18007ec01  lea     rdi, [rbx+78h]
0x18007ec05  mov     rax, [rdi]
0x18007ec08  mov     rcx, rdi
0x18007ec0b  mov     rax, [rax]
0x18007ec0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ec13  mov     rax, [rbx+50h]
0x18007ec17  test    rax, rax
0x18007ec1a  jz      short loc_18007EC6C
0x18007ec1c  mov     [rsp+48h+var_10], rax
0x18007ec21  lea     rax, aReleasingMPise; "Releasing m_pISendReceiveSink=%p"
0x18007ec28  mov     [rsp+48h+var_18], rax
0x18007ec2d  mov     [rsp+48h+var_20], 0
0x18007ec36  mov     [rsp+48h+var_28], r12
0x18007ec3b  mov     r9d, 5Eh ; '^'
0x18007ec41  lea     r8, aComComplusDtcD_44; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x18007ec48  lea     edx, [r9-59h]
0x18007ec4c  lea     ecx, [rdx-4]
0x18007ec4f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18007ec54  mov     rcx, [rbx+50h]
0x18007ec58  mov     rax, [rcx]
0x18007ec5b  mov     rax, [rax+10h]
0x18007ec5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ec64  mov     qword ptr [rbx+50h], 0
0x18007ec6c  mov     rax, [rbx+68h]
0x18007ec70  test    rax, rax
0x18007ec73  jz      short loc_18007ECB7
0x18007ec75  mov     [rsp+48h+var_10], rax
0x18007ec7a  lea     rax, aClosingMHsendr; "Closing m_hSendReceiveEvent=0x%x"
0x18007ec81  mov     [rsp+48h+var_18], rax
0x18007ec86  mov     [rsp+48h+var_20], 0
0x18007ec8f  mov     [rsp+48h+var_28], r12
0x18007ec94  mov     r9d, 66h ; 'f'
0x18007ec9a  lea     r8, aComComplusDtcD_44; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x18007eca1  lea     edx, [r9-61h]
0x18007eca5  lea     ecx, [rdx-4]
0x18007eca8  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18007ecad  mov     rcx, [rbx+68h]; hObject
0x18007ecb1  call    cs:__imp_CloseHandle
0x18007ecb7  mov     rax, [rbx+70h]
0x18007ecbb  test    rax, rax
0x18007ecbe  jz      short loc_18007ED02
0x18007ecc0  mov     [rsp+48h+var_10], rax
0x18007ecc5  lea     rax, aClosingMHconne; "Closing m_hConnectionStatus=0x%x"
0x18007eccc  mov     [rsp+48h+var_18], rax
0x18007ecd1  mov     [rsp+48h+var_20], 0
0x18007ecda  mov     [rsp+48h+var_28], r12
0x18007ecdf  mov     r9d, 6Ch ; 'l'
0x18007ece5  lea     r8, aComComplusDtcD_44; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x18007ecec  lea     edx, [r9-67h]
0x18007ecf0  lea     ecx, [rdx-4]
0x18007ecf3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18007ecf8  mov     rcx, [rbx+70h]; hObject
0x18007ecfc  call    cs:__imp_CloseHandle
0x18007ed02  mov     rax, [rdi]
0x18007ed05  mov     rcx, rdi
0x18007ed08  mov     rax, [rax+8]
0x18007ed0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ed11  nop
0x18007ed12  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x18007ed19  mov     [rdi], rax
0x18007ed1c  lea     rcx, [rdi+8]; lpCriticalSection
0x18007ed20  call    cs:__imp_DeleteCriticalSection
0x18007ed26  nop
0x18007ed27  mov     rbx, [rsp+48h+arg_0]
0x18007ed2c  mov     rdi, [rsp+48h+arg_8]
0x18007ed31  add     rsp, 40h
0x18007ed35  pop     r12
0x18007ed37  retn
```
