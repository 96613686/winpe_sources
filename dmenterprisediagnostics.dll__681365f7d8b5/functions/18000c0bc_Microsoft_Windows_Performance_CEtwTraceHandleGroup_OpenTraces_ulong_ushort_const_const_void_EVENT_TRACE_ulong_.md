# Microsoft::Windows::Performance::CEtwTraceHandleGroup::OpenTraces(ulong,ushort const * const *,void (*)(_EVENT_TRACE *),ulong (*)(_EVENT_TRACE_LOGFILEW *),ulong)

- ea: `0x18000c0bc`
- end: `0x18000c186`
- name: `?OpenTraces@CEtwTraceHandleGroup@Performance@Windows@Microsoft@@QEAAJKPEBQEBGP6AXPEAU_EVENT_TRACE@@@ZP6AKPEAU_EVENT_TRACE_LOGFILEW@@@ZK@Z`
- size: `202`
- prototype: `int(Microsoft::Windows::Performance::CEtwTraceHandleGroup *__hidden this, unsigned int, const unsigned __int16 *const *, void (*)(struct _EVENT_TRACE *), unsigned int (*)(struct _EVENT_TRACE_LOGFILEW *), unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000afdc`

## callees

- `0x180001830`
- `0x180001880`
- `0x180009bb0`
- `0x18000bff0`
- `0x18000c0bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CEtwTraceHandleGroup::OpenTraces(
        Microsoft::Windows::Performance::CEtwTraceHandleGroup *this,
        unsigned int a2,
        const unsigned __int16 *const *a3,
        void (*a4)(struct _EVENT_TRACE *),
        unsigned int (*a5)(struct _EVENT_TRACE_LOGFILEW *),
        ULONG a6)
{
  __int64 i; // rbx
  int v12; // ebp
  char *v13; // rcx
  char *v14; // rbx

  if ( !(unsigned __int8)ATL::CAutoVectorPtr<Microsoft::Windows::Performance::CEtwTraceHandle>::Allocate(this, a2) )
    return 2147942414LL;
  *((_DWORD *)this + 2) = a2;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= a2 )
      return 0;
    v12 = Microsoft::Windows::Performance::CEtwTraceHandle::OpenTraceW(
            (Microsoft::Windows::Performance::CEtwTraceHandle *)(*(_QWORD *)this + 16LL * (unsigned int)i),
            (WCHAR *)a3[i],
            a4,
            a5,
            a6);
    if ( v12 < 0 )
      break;
  }
  if ( *((_DWORD *)this + 2) )
  {
    v13 = *(char **)this;
    if ( *(_QWORD *)this )
    {
      v14 = v13 - 8;
      `eh vector destructor iterator'(
        v13,
        0x10u,
        *((_QWORD *)v13 - 1),
        (void (*)(void *))Microsoft::Windows::Performance::CEtwTraceHandle::~CEtwTraceHandle);
      operator delete[](v14, 16LL * *(_QWORD *)v14 + 8);
    }
    *(_QWORD *)this = 0;
    *((_DWORD *)this + 2) = 0;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000c0bc  push    rbx
0x18000c0be  push    rbp
0x18000c0bf  push    rsi
0x18000c0c0  push    rdi
0x18000c0c1  push    r12
0x18000c0c3  push    r14
0x18000c0c5  push    r15
0x18000c0c7  sub     rsp, 30h
0x18000c0cb  mov     r15, r9
0x18000c0ce  mov     r12, r8
0x18000c0d1  mov     esi, edx
0x18000c0d3  mov     rdi, rcx
0x18000c0d6  mov     edx, edx
0x18000c0d8  call    ?Allocate@?$CAutoVectorPtr@VCEtwTraceHandle@Performance@Windows@Microsoft@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<Microsoft::Windows::Performance::CEtwTraceHandle>::Allocate(unsigned __int64)
0x18000c0dd  test    al, al
0x18000c0df  jnz     short loc_18000C0EB
0x18000c0e1  mov     eax, 8007000Eh
0x18000c0e6  jmp     loc_18000C176
0x18000c0eb  mov     [rdi+8], esi
0x18000c0ee  xor     ebx, ebx
0x18000c0f0  mov     r14d, [rsp+68h+arg_28]
0x18000c0f8  cmp     ebx, esi
0x18000c0fa  jnb     short loc_18000C174
0x18000c0fc  mov     ecx, ebx
0x18000c0fe  shl     rcx, 4
0x18000c102  add     rcx, [rdi]; this
0x18000c105  mov     [rsp+68h+var_48], r14d; unsigned int
0x18000c10a  mov     r9, [rsp+68h+arg_20]; unsigned int (*)(struct _EVENT_TRACE_LOGFILEW *)
0x18000c112  mov     r8, r15; void (*)(struct _EVENT_TRACE *)
0x18000c115  mov     rdx, [r12+rbx*8]; unsigned __int16 *
0x18000c119  call    ?OpenTraceW@CEtwTraceHandle@Performance@Windows@Microsoft@@QEAAJPEBGP6AXPEAU_EVENT_TRACE@@@ZP6AKPEAU_EVENT_TRACE_LOGFILEW@@@ZK@Z; Microsoft::Windows::Performance::CEtwTraceHandle::OpenTraceW(ushort const *,void (*)(_EVENT_TRACE *),ulong (*)(_EVENT_TRACE_LOGFILEW *),ulong)
0x18000c11e  mov     ebp, eax
0x18000c120  test    eax, eax
0x18000c122  js      short loc_18000C128
0x18000c124  inc     ebx
0x18000c126  jmp     short loc_18000C0F8
0x18000c128  cmp     dword ptr [rdi+8], 0
0x18000c12c  jz      short loc_18000C170
0x18000c12e  mov     rcx, [rdi]; void *
0x18000c131  test    rcx, rcx
0x18000c134  jz      short loc_18000C162
0x18000c136  lea     rbx, [rcx-8]
0x18000c13a  lea     r9, ??1CEtwTraceHandle@Performance@Windows@Microsoft@@QEAA@XZ; void (*)(void *)
0x18000c141  mov     r8, [rbx]; unsigned __int64
0x18000c144  mov     edx, 10h; unsigned __int64
0x18000c149  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000c14e  mov     rdx, [rbx]
0x18000c151  shl     rdx, 4
0x18000c155  add     rdx, 8; unsigned __int64
0x18000c159  mov     rcx, rbx; void *
0x18000c15c  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x18000c161  nop
0x18000c162  mov     qword ptr [rdi], 0
0x18000c169  mov     dword ptr [rdi+8], 0
0x18000c170  mov     eax, ebp
0x18000c172  jmp     short loc_18000C176
0x18000c174  xor     eax, eax
0x18000c176  add     rsp, 30h
0x18000c17a  pop     r15
0x18000c17c  pop     r14
0x18000c17e  pop     r12
0x18000c180  pop     rdi
0x18000c181  pop     rsi
0x18000c182  pop     rbp
0x18000c183  pop     rbx
0x18000c184  retn
```
