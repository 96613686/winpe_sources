# ThreadGlobals::ThreadGlobals(void)

- ea: `0x180002240`
- end: `0x1800022e5`
- name: `??0ThreadGlobals@@AEAA@XZ`
- size: `165`
- prototype: `ThreadGlobals *__fastcall(ThreadGlobals *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002160`

## callees

- `0x180002240`
- `0x18000f5e0`
- `0x18000f630`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x1800022d6`
- `KERNEL32!TlsSetValue` at `0x1800022d6`
- `KERNEL32!GetCurrentThreadId` at `0x180002271`
- `KERNEL32!GetCurrentThreadId` at `0x180002271`

## pseudocode

```c
ThreadGlobals *__fastcall ThreadGlobals::ThreadGlobals(ThreadGlobals *this)
{
  __int64 v2; // rax

  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 4) = 0;
  if ( (unsigned int)MUTX::Enter((MUTX *)&ThreadGlobals::g_mutx) )
  {
    *(_DWORD *)this = GetCurrentThreadId();
    *((_QWORD *)this + 2) = ThreadGlobals::g_ptgFirst;
    *((_QWORD *)this + 1) = &ThreadGlobals::g_ptgFirst;
    ThreadGlobals::g_ptgFirst = this;
    v2 = *((_QWORD *)this + 2);
    if ( v2 )
      *(_QWORD *)(v2 + 8) = (char *)this + 16;
    MUTX::Leave((MUTX *)&ThreadGlobals::g_mutx);
    *((_DWORD *)this + 1) = 0;
    *((_QWORD *)this + 6) = -1;
    *((_QWORD *)this + 7) = -1;
    *((_DWORD *)this + 16) = -1;
    *((_DWORD *)this + 17) = -1;
    TlsSetValue(g_luTls, this);
  }
  return this;
}

```

## disassembly

```asm
0x180002240  push    rbx
0x180002242  sub     rsp, 20h
0x180002246  mov     rbx, rcx
0x180002249  mov     qword ptr [rcx+18h], 0
0x180002251  mov     qword ptr [rcx+28h], 0
0x180002259  mov     qword ptr [rcx+20h], 0
0x180002261  lea     rcx, ?g_mutx@ThreadGlobals@@0VMUTX@@A; this
0x180002268  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18000226d  test    eax, eax
0x18000226f  jz      short loc_1800022DC
0x180002271  call    cs:__imp_GetCurrentThreadId
0x180002277  mov     [rbx], eax
0x180002279  lea     rdx, [rbx+10h]
0x18000227d  mov     rax, cs:?g_ptgFirst@ThreadGlobals@@0PEAV1@EA; ThreadGlobals * ThreadGlobals::g_ptgFirst
0x180002284  mov     [rdx], rax
0x180002287  lea     rax, ?g_ptgFirst@ThreadGlobals@@0PEAV1@EA; ThreadGlobals * ThreadGlobals::g_ptgFirst
0x18000228e  mov     [rbx+8], rax
0x180002292  mov     cs:?g_ptgFirst@ThreadGlobals@@0PEAV1@EA, rbx; ThreadGlobals * ThreadGlobals::g_ptgFirst
0x180002299  mov     rax, [rdx]
0x18000229c  test    rax, rax
0x18000229f  jz      short loc_1800022A5
0x1800022a1  mov     [rax+8], rdx
0x1800022a5  lea     rcx, ?g_mutx@ThreadGlobals@@0VMUTX@@A; this
0x1800022ac  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x1800022b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800022b5  mov     dword ptr [rbx+4], 0
0x1800022bc  mov     [rbx+30h], rax
0x1800022c0  mov     rdx, rbx; lpTlsValue
0x1800022c3  mov     [rbx+38h], rax
0x1800022c7  or      eax, 0FFFFFFFFh
0x1800022ca  mov     [rbx+40h], eax
0x1800022cd  mov     [rbx+44h], eax
0x1800022d0  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800022d6  call    cs:__imp_TlsSetValue
0x1800022dc  mov     rax, rbx
0x1800022df  add     rsp, 20h
0x1800022e3  pop     rbx
0x1800022e4  retn
```
