# Microsoft::Windows::Performance::CEtwTraceHandleGroup::OpenTraces(ulong,ushort const * const *,void (*)(_EVENT_TRACE *),ulong (*)(_EVENT_TRACE_LOGFILEW *),ulong)

- ea: `0x18000bb44`
- end: `0x18000bc0d`
- name: `?OpenTraces@CEtwTraceHandleGroup@Performance@Windows@Microsoft@@QEAAJKPEBQEBGP6AXPEAU_EVENT_TRACE@@@ZP6AKPEAU_EVENT_TRACE_LOGFILEW@@@ZK@Z`
- size: `201`
- prototype: `int(Microsoft::Windows::Performance::CEtwTraceHandleGroup *__hidden this, unsigned int, const unsigned __int16 *const *, void (*)(struct _EVENT_TRACE *), unsigned int (*)(struct _EVENT_TRACE_LOGFILEW *), unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000aa44`

## callees

- `0x180001810`
- `0x180001860`
- `0x1800096f0`
- `0x18000ba80`
- `0x18000bb44`

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
  signed int v12; // ebp
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
      operator delete[](v14);
    }
    *(_QWORD *)this = 0;
    *((_DWORD *)this + 2) = 0;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000bb44  push    rbx
0x18000bb46  push    rbp
0x18000bb47  push    rsi
0x18000bb48  push    rdi
0x18000bb49  push    r12
0x18000bb4b  push    r14
0x18000bb4d  push    r15
0x18000bb4f  sub     rsp, 30h
0x18000bb53  mov     r15, r9
0x18000bb56  mov     r12, r8
0x18000bb59  mov     esi, edx
0x18000bb5b  mov     rdi, rcx
0x18000bb5e  mov     edx, edx
0x18000bb60  call    ?Allocate@?$CAutoVectorPtr@VCEtwTraceHandle@Performance@Windows@Microsoft@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<Microsoft::Windows::Performance::CEtwTraceHandle>::Allocate(unsigned __int64)
0x18000bb65  test    al, al
0x18000bb67  jnz     short loc_18000BB73
0x18000bb69  mov     eax, 8007000Eh
0x18000bb6e  jmp     loc_18000BBFE
0x18000bb73  mov     [rdi+8], esi
0x18000bb76  xor     ebx, ebx
0x18000bb78  mov     r14d, [rsp+68h+arg_28]
0x18000bb80  cmp     ebx, esi
0x18000bb82  jnb     short loc_18000BBFC
0x18000bb84  mov     ecx, ebx
0x18000bb86  shl     rcx, 4
0x18000bb8a  add     rcx, [rdi]; this
0x18000bb8d  mov     [rsp+68h+var_48], r14d; unsigned int
0x18000bb92  mov     r9, [rsp+68h+arg_20]; unsigned int (*)(struct _EVENT_TRACE_LOGFILEW *)
0x18000bb9a  mov     r8, r15; void (*)(struct _EVENT_TRACE *)
0x18000bb9d  mov     rdx, [r12+rbx*8]; unsigned __int16 *
0x18000bba1  call    ?OpenTraceW@CEtwTraceHandle@Performance@Windows@Microsoft@@QEAAJPEBGP6AXPEAU_EVENT_TRACE@@@ZP6AKPEAU_EVENT_TRACE_LOGFILEW@@@ZK@Z; Microsoft::Windows::Performance::CEtwTraceHandle::OpenTraceW(ushort const *,void (*)(_EVENT_TRACE *),ulong (*)(_EVENT_TRACE_LOGFILEW *),ulong)
0x18000bba6  mov     ebp, eax
0x18000bba8  test    eax, eax
0x18000bbaa  js      short loc_18000BBB0
0x18000bbac  inc     ebx
0x18000bbae  jmp     short loc_18000BB80
0x18000bbb0  cmp     dword ptr [rdi+8], 0
0x18000bbb4  jz      short loc_18000BBF8
0x18000bbb6  mov     rcx, [rdi]; void *
0x18000bbb9  test    rcx, rcx
0x18000bbbc  jz      short loc_18000BBEA
0x18000bbbe  lea     rbx, [rcx-8]
0x18000bbc2  lea     r9, ??1CEtwTraceHandle@Performance@Windows@Microsoft@@QEAA@XZ; void (*)(void *)
0x18000bbc9  mov     r8, [rbx]; unsigned __int64
0x18000bbcc  mov     edx, 10h; unsigned __int64
0x18000bbd1  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000bbd6  mov     rdx, [rbx]
0x18000bbd9  shl     rdx, 4
0x18000bbdd  add     rdx, 8; unsigned __int64
0x18000bbe1  mov     rcx, rbx; void *
0x18000bbe4  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x18000bbe9  nop
0x18000bbea  mov     qword ptr [rdi], 0
0x18000bbf1  mov     dword ptr [rdi+8], 0
0x18000bbf8  mov     eax, ebp
0x18000bbfa  jmp     short loc_18000BBFE
0x18000bbfc  xor     eax, eax
0x18000bbfe  add     rsp, 30h
0x18000bc02  pop     r15
0x18000bc04  pop     r14
0x18000bc06  pop     r12
0x18000bc08  pop     rdi
0x18000bc09  pop     rsi
0x18000bc0a  pop     rbp
0x18000bc0b  pop     rbx
0x18000bc0c  retn
```
