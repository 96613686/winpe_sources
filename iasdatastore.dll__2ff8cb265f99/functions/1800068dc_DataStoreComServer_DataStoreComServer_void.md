# DataStoreComServer::~DataStoreComServer(void)

- ea: `0x1800068dc`
- end: `0x180006979`
- name: `??1DataStoreComServer@@QEAA@XZ`
- size: `157`
- prototype: `void __fastcall(DataStoreComServer *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800021b4`
- `0x180002370`
- `0x1800023d0`
- `0x180003f78`
- `0x1800058a0`

## callees

- `0x1800068dc`
- `0x180006980`

## import_xrefs

- `msvcrt!free` at `0x180006907`
- `msvcrt!free` at `0x180006907`
- `KERNEL32!Sleep` at `0x180006921`
- `KERNEL32!Sleep` at `0x180006921`
- `KERNEL32!DeleteCriticalSection` at `0x180006967`
- `KERNEL32!DeleteCriticalSection` at `0x180006967`
- `rtutils!TraceDeregisterW` at `0x180006941`
- `rtutils!TraceDeregisterW` at `0x180006941`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DataStoreComServer::~DataStoreComServer(DataStoreComServer *this)
{
  void *v2; // rdi

  *(_QWORD *)this = &DataStoreComServer::`vftable';
  v2 = (void *)*((_QWORD *)this + 9);
  if ( v2 )
  {
    DataStoreServer::~DataStoreServer(*((DataStoreServer **)this + 9));
    free(v2);
  }
  *((_QWORD *)this + 9) = 0;
  while ( _InterlockedExchange(&lLocked, 1) )
    Sleep(5u);
  if ( !--lRefCount )
  {
    TraceDeregisterW(dwTraceID);
    dwTraceID = -1;
  }
  _InterlockedExchange(&lLocked, 0);
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x1800068dc  mov     [rsp+arg_8], rbx
0x1800068e1  push    rdi
0x1800068e2  sub     rsp, 20h
0x1800068e6  mov     rbx, rcx
0x1800068e9  lea     rax, ??_7DataStoreComServer@@6B@; const DataStoreComServer::`vftable'
0x1800068f0  mov     [rcx], rax
0x1800068f3  mov     rdi, [rcx+48h]
0x1800068f7  test    rdi, rdi
0x1800068fa  jz      short loc_18000690D
0x1800068fc  mov     rcx, rdi; this
0x1800068ff  call    ??1DataStoreServer@@QEAA@XZ; DataStoreServer::~DataStoreServer(void)
0x180006904  mov     rcx, rdi; Block
0x180006907  call    cs:__imp_free
0x18000690d  mov     qword ptr [rbx+48h], 0
0x180006915  mov     edi, 1
0x18000691a  jmp     short loc_180006927
0x18000691c  mov     ecx, 5; dwMilliseconds
0x180006921  call    cs:__imp_Sleep
0x180006927  mov     eax, edi
0x180006929  xchg    eax, cs:lLocked
0x18000692f  test    eax, eax
0x180006931  jnz     short loc_18000691C
0x180006933  sub     cs:lRefCount, edi
0x180006939  jnz     short loc_180006951
0x18000693b  mov     ecx, cs:dwTraceID; dwTraceID
0x180006941  call    cs:__imp_TraceDeregisterW
0x180006947  mov     cs:dwTraceID, 0FFFFFFFFh
0x180006951  xor     eax, eax
0x180006953  xchg    eax, cs:lLocked
0x180006959  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000695d  cmp     byte ptr [rcx+28h], 0
0x180006961  jz      short loc_18000696E
0x180006963  mov     byte ptr [rcx+28h], 0
0x180006967  call    cs:__imp_DeleteCriticalSection
0x18000696d  nop
0x18000696e  mov     rbx, [rsp+28h+arg_8]
0x180006973  add     rsp, 20h
0x180006977  pop     rdi
0x180006978  retn
```
