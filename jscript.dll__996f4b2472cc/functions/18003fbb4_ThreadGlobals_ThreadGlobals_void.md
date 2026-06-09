# ThreadGlobals::ThreadGlobals(void)

- ea: `0x18003fbb4`
- end: `0x18003fc66`
- name: `??0ThreadGlobals@@AEAA@XZ`
- size: `178`
- prototype: `ThreadGlobals *__fastcall(ThreadGlobals *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003fac8`

## callees

- `0x18000c860`
- `0x18000c8c0`
- `0x18003fbb4`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x18003fc50`
- `KERNEL32!TlsSetValue` at `0x18003fc50`
- `KERNEL32!GetCurrentThreadId` at `0x18003fbe5`
- `KERNEL32!GetCurrentThreadId` at `0x18003fbe5`

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
0x18003fbb4  push    rbx
0x18003fbb6  sub     rsp, 20h
0x18003fbba  mov     rbx, rcx
0x18003fbbd  mov     qword ptr [rcx+18h], 0
0x18003fbc5  mov     qword ptr [rcx+28h], 0
0x18003fbcd  mov     qword ptr [rcx+20h], 0
0x18003fbd5  lea     rcx, ?g_mutx@ThreadGlobals@@0VMUTX@@A; this
0x18003fbdc  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18003fbe1  test    eax, eax
0x18003fbe3  jz      short loc_18003FC5C
0x18003fbe5  call    cs:__imp_GetCurrentThreadId
0x18003fbec  nop     dword ptr [rax+rax+00h]
0x18003fbf1  mov     [rbx], eax
0x18003fbf3  lea     rdx, [rbx+10h]
0x18003fbf7  mov     rax, cs:?g_ptgFirst@ThreadGlobals@@0PEAV1@EA; ThreadGlobals * ThreadGlobals::g_ptgFirst
0x18003fbfe  mov     [rdx], rax
0x18003fc01  lea     rax, ?g_ptgFirst@ThreadGlobals@@0PEAV1@EA; ThreadGlobals * ThreadGlobals::g_ptgFirst
0x18003fc08  mov     [rbx+8], rax
0x18003fc0c  mov     cs:?g_ptgFirst@ThreadGlobals@@0PEAV1@EA, rbx; ThreadGlobals * ThreadGlobals::g_ptgFirst
0x18003fc13  mov     rax, [rdx]
0x18003fc16  test    rax, rax
0x18003fc19  jz      short loc_18003FC1F
0x18003fc1b  mov     [rax+8], rdx
0x18003fc1f  lea     rcx, ?g_mutx@ThreadGlobals@@0VMUTX@@A; this
0x18003fc26  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x18003fc2b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003fc2f  mov     dword ptr [rbx+4], 0
0x18003fc36  mov     [rbx+30h], rax
0x18003fc3a  mov     rdx, rbx; lpTlsValue
0x18003fc3d  mov     [rbx+38h], rax
0x18003fc41  or      eax, 0FFFFFFFFh
0x18003fc44  mov     [rbx+40h], eax
0x18003fc47  mov     [rbx+44h], eax
0x18003fc4a  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18003fc50  call    cs:__imp_TlsSetValue
0x18003fc57  nop     dword ptr [rax+rax+00h]
0x18003fc5c  mov     rax, rbx
0x18003fc5f  add     rsp, 20h
0x18003fc63  pop     rbx
0x18003fc64  retn
```
