# CSendReceiveSubordinate::Init(void)

- ea: `0x1800b36a0`
- end: `0x1800b377e`
- name: `?Init@CSendReceiveSubordinate@@UEAAHXZ`
- size: `222`
- prototype: `__int64 __fastcall(CSendReceiveSubordinate *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800063b0`
- `0x1800b36a0`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b36e9`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b370d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b36e9`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b370d`

## string_xrefs

- `0x1800b3742`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`

## pseudocode

```c
__int64 __fastcall CSendReceiveSubordinate::Init(CSendReceiveSubordinate *this)
{
  bool v1; // zf
  unsigned int v3; // edi
  HANDLE EventA; // rax
  HANDLE v5; // rax

  v1 = *((_QWORD *)this + 13) == 0;
  v3 = 1;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  if ( v1 )
  {
    EventA = CreateEventA(0, 0, 0, 0);
    *((_QWORD *)this + 13) = EventA;
    v3 = EventA != 0;
  }
  if ( !*((_QWORD *)this + 14) )
  {
    v5 = CreateEventA(0, 1, 1, 0);
    *((_QWORD *)this + 14) = v5;
    v3 &= -(v5 != 0);
  }
  (*(void (__fastcall **)(_QWORD, CSendReceiveSubordinate *))(**((_QWORD **)this + 1) + 48LL))(
    *((_QWORD *)this + 1),
    this);
  TraceStringInline(
    1,
    5,
    L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
    2155,
    L"CSendReceiveSubordinate::Init",
    0,
    L"Initializing CSendReceiveSubordinate=%p",
    this);
  return v3;
}

```

## disassembly

```asm
0x1800b36a0  mov     [rsp+arg_0], rbx
0x1800b36a5  push    rdi
0x1800b36a6  sub     rsp, 40h
0x1800b36aa  cmp     qword ptr [rcx+68h], 0
0x1800b36af  mov     rbx, rcx
0x1800b36b2  mov     edi, 1
0x1800b36b7  mov     qword ptr [rcx+30h], 0
0x1800b36bf  mov     qword ptr [rcx+38h], 0
0x1800b36c7  mov     dword ptr [rcx+40h], 0
0x1800b36ce  mov     qword ptr [rcx+58h], 0
0x1800b36d6  mov     dword ptr [rcx+60h], 0
0x1800b36dd  jnz     short loc_1800B36FA
0x1800b36df  xor     r9d, r9d; lpName
0x1800b36e2  xor     r8d, r8d; bInitialState
0x1800b36e5  xor     edx, edx; bManualReset
0x1800b36e7  xor     ecx, ecx; lpEventAttributes
0x1800b36e9  call    cs:__imp_CreateEventA
0x1800b36ef  mov     [rbx+68h], rax
0x1800b36f3  neg     rax
0x1800b36f6  sbb     eax, eax
0x1800b36f8  and     edi, eax
0x1800b36fa  cmp     qword ptr [rbx+70h], 0
0x1800b36ff  jnz     short loc_1800B371E
0x1800b3701  xor     r9d, r9d; lpName
0x1800b3704  xor     ecx, ecx; lpEventAttributes
0x1800b3706  lea     edx, [r9+1]; bManualReset
0x1800b370a  mov     r8d, edx; bInitialState
0x1800b370d  call    cs:__imp_CreateEventA
0x1800b3713  mov     [rbx+70h], rax
0x1800b3717  neg     rax
0x1800b371a  sbb     eax, eax
0x1800b371c  and     edi, eax
0x1800b371e  mov     rcx, [rbx+8]
0x1800b3722  mov     rdx, rbx
0x1800b3725  mov     rax, [rcx]
0x1800b3728  mov     rax, [rax+30h]
0x1800b372c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3731  mov     [rsp+48h+var_10], rbx
0x1800b3736  lea     rax, aInitializingCs; "Initializing CSendReceiveSubordinate=%p"
0x1800b373d  mov     [rsp+48h+var_18], rax
0x1800b3742  lea     r8, aComComplusDtcD_109; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x1800b3749  mov     edx, 5
0x1800b374e  mov     [rsp+48h+var_20], 0
0x1800b3757  lea     rax, aCsendreceivesu; "CSendReceiveSubordinate::Init"
0x1800b375e  mov     r9d, 86Bh
0x1800b3764  mov     [rsp+48h+var_28], rax
0x1800b3769  lea     ecx, [rdx-4]
0x1800b376c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b3771  mov     rbx, [rsp+48h+arg_0]
0x1800b3776  mov     eax, edi
0x1800b3778  add     rsp, 40h
0x1800b377c  pop     rdi
0x1800b377d  retn
```
