# ExtensionHost::~ExtensionHost(void)

- ea: `0x1800031c0`
- end: `0x18000324b`
- name: `??1ExtensionHost@@QEAA@XZ`
- size: `139`
- prototype: `void __fastcall(ExtensionHost *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002b58`
- `0x180003038`

## callees

- `0x18000309c`
- `0x1800031c0`
- `0x1800121c0`

## import_xrefs

- `KERNEL32!Sleep` at `0x180003201`
- `KERNEL32!Sleep` at `0x180003201`
- `ADVAPI32!DeregisterEventSource` at `0x1800031df`
- `ADVAPI32!DeregisterEventSource` at `0x1800031df`
- `rtutils!TraceDeregisterW` at `0x180003225`
- `rtutils!TraceDeregisterW` at `0x180003225`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ExtensionHost::~ExtensionHost(ExtensionHost *this)
{
  *(_QWORD *)this = &ExtensionHost::`vftable';
  if ( g_NPSEventLog )
  {
    DeregisterEventSource(g_NPSEventLog);
    g_NPSEventLog = 0;
  }
  RadiusExtensionPoint::~RadiusExtensionPoint((ExtensionHost *)((char *)this + 72));
  while ( _InterlockedExchange(&lLocked, 1) )
    Sleep(5u);
  if ( !--lRefCount )
  {
    TraceDeregisterW(dwTraceID);
    dwTraceID = -1;
  }
  _InterlockedExchange(&lLocked, 0);
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((char *)this + 8);
}

```

## disassembly

```asm
0x1800031c0  push    rbx
0x1800031c2  sub     rsp, 20h
0x1800031c6  mov     rbx, rcx
0x1800031c9  lea     rax, ??_7ExtensionHost@@6B@; const ExtensionHost::`vftable'
0x1800031d0  mov     [rcx], rax
0x1800031d3  mov     rcx, cs:?g_NPSEventLog@@3PEAXEA; hEventLog
0x1800031da  test    rcx, rcx
0x1800031dd  jz      short loc_1800031F0
0x1800031df  call    cs:__imp_DeregisterEventSource
0x1800031e5  mov     cs:?g_NPSEventLog@@3PEAXEA, 0; void * g_NPSEventLog
0x1800031f0  lea     rcx, [rbx+48h]; this
0x1800031f4  call    ??1RadiusExtensionPoint@@QEAA@XZ; RadiusExtensionPoint::~RadiusExtensionPoint(void)
0x1800031f9  nop
0x1800031fa  jmp     short loc_180003207
0x1800031fc  mov     ecx, 5; dwMilliseconds
0x180003201  call    cs:__imp_Sleep
0x180003207  mov     eax, 1
0x18000320c  xchg    eax, cs:lLocked
0x180003212  test    eax, eax
0x180003214  jnz     short loc_1800031FC
0x180003216  sub     cs:lRefCount, 1
0x18000321d  jnz     short loc_180003235
0x18000321f  mov     ecx, cs:dwTraceID; dwTraceID
0x180003225  call    cs:__imp_TraceDeregisterW
0x18000322b  mov     cs:dwTraceID, 0FFFFFFFFh
0x180003235  xor     eax, eax
0x180003237  xchg    eax, cs:lLocked
0x18000323d  lea     rcx, [rbx+8]
0x180003241  add     rsp, 20h
0x180003245  pop     rbx
0x180003246  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
