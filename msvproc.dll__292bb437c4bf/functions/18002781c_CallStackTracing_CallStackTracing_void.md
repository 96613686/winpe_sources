# CallStackTracing::~CallStackTracing(void)

- ea: `0x18002781c`
- end: `0x180027888`
- name: `??1CallStackTracing@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(CallStackTracing *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800d0690`

## callees

- `0x18002781c`
- `0x180035fe4`
- `0x1800362c4`
- `0x180058200`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180027868`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180027868`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180027881`

## pseudocode

```c
void __fastcall CallStackTracing::~CallStackTracing(CallStackTracing *this)
{
  int v2; // edx
  __int64 v3; // rdi
  CxCodeVideoProcWARPDataHandler *v4; // rsi

  *(_QWORD *)this = &CallStackTracing::`vftable';
  CallStackTracing::Cleanup(this);
  v3 = 124;
  v4 = (CallStackTracing *)((char *)this + 2192);
  do
  {
    v4 = (CxCodeVideoProcWARPDataHandler *)((char *)v4 - 16);
    CxCodeVideoProcWARPDataHandler::SetAutoProcessD3D(v4, v2);
    --v3;
  }
  while ( v3 );
  CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>((char *)this + 104);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x18002781c  mov     [rsp+arg_0], rbx
0x180027821  mov     [rsp+arg_8], rsi
0x180027826  push    rdi
0x180027827  sub     rsp, 20h
0x18002782b  lea     rax, ??_7CallStackTracing@@6B@; const CallStackTracing::`vftable'
0x180027832  mov     rbx, rcx
0x180027835  mov     [rcx], rax
0x180027838  call    ?Cleanup@CallStackTracing@@IEAAXXZ; CallStackTracing::Cleanup(void)
0x18002783d  mov     edi, 7Ch ; '|'
0x180027842  lea     rsi, [rbx+890h]
0x180027849  sub     rsi, 10h
0x18002784d  mov     rcx, rsi; this
0x180027850  call    ?SetAutoProcessD3D@CxCodeVideoProcWARPDataHandler@@UEAAXH@Z; CxCodeVideoProcWARPDataHandler::SetAutoProcessD3D(int)
0x180027855  sub     rdi, 1
0x180027859  jnz     short loc_180027849
0x18002785b  lea     rcx, [rbx+68h]
0x18002785f  call    ??1?$CFreeList@VCallStackContextNode@@$0BA@@@UEAA@XZ; CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>(void)
0x180027864  lea     rcx, [rbx+38h]; lpCriticalSection
0x180027868  call    cs:__imp_DeleteCriticalSection
0x18002786e  lea     rcx, [rbx+10h]
0x180027872  mov     rbx, [rsp+28h+arg_0]
0x180027877  mov     rsi, [rsp+28h+arg_8]
0x18002787c  add     rsp, 20h
0x180027880  pop     rdi
0x180027881  jmp     cs:__imp_DeleteCriticalSection
```
