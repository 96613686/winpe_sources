# CLogFileCtrl::CLogFileCtrl(void)

- ea: `0x180001f20`
- end: `0x180001fc5`
- name: `??0CLogFileCtrl@@QEAA@XZ`
- size: `165`
- prototype: `CLogFileCtrl *__fastcall(CLogFileCtrl *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000373c`
- `0x18000744c`
- `0x18000bed8`

## import_xrefs

- `IisRTL!??0STR@@QEAA@XZ` at `0x180001f66`
- `IisRTL!??0STR@@QEAA@XZ` at `0x180001f73`
- `IisRTL!??0STR@@QEAA@XZ` at `0x180001f80`
- `IisRTL!??0STR@@QEAA@XZ` at `0x180001f8d`
- `IisRTL!??0STR@@QEAA@XZ` at `0x180001f66`
- `IisRTL!??0STR@@QEAA@XZ` at `0x180001f73`
- `IisRTL!??0STR@@QEAA@XZ` at `0x180001f80`
- `IisRTL!??0STR@@QEAA@XZ` at `0x180001f8d`
- `IisRTL!IISInitializeCriticalSection` at `0x180001fb6`
- `IisRTL!IISInitializeCriticalSection` at `0x180001fb6`
- `KERNEL32!InitializeCriticalSection` at `0x180001f3e`
- `KERNEL32!InitializeCriticalSection` at `0x180001f3e`

## pseudocode

```c
CLogFileCtrl *__fastcall CLogFileCtrl::CLogFileCtrl(CLogFileCtrl *this)
{
  *(_QWORD *)this = &ILogPluginEx::`vftable';
  *((_DWORD *)this + 2) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 18) = 1;
  *((_QWORD *)this + 14) = 1;
  *((_DWORD *)this + 30) = 0;
  STR::STR((CLogFileCtrl *)((char *)this + 128));
  STR::STR((CLogFileCtrl *)((char *)this + 184));
  STR::STR((CLogFileCtrl *)((char *)this + 240));
  STR::STR((CLogFileCtrl *)((char *)this + 296));
  *((_QWORD *)this + 44) = 0;
  *((_DWORD *)this + 90) = 0;
  *(_OWORD *)((char *)this + 76) = 0;
  IISInitializeCriticalSection((char *)this + 368);
  return this;
}

```

## disassembly

```asm
0x180001f20  push    rbx
0x180001f22  sub     rsp, 20h
0x180001f26  lea     rax, ??_7ILogPluginEx@@6B@; const ILogPluginEx::`vftable'
0x180001f2d  mov     rbx, rcx
0x180001f30  mov     [rcx], rax
0x180001f33  mov     dword ptr [rcx+8], 0
0x180001f3a  add     rcx, 10h; lpCriticalSection
0x180001f3e  call    cs:__imp_InitializeCriticalSection
0x180001f44  mov     eax, 1
0x180001f49  mov     qword ptr [rbx+38h], 0
0x180001f51  lea     rcx, [rbx+80h]
0x180001f58  mov     [rbx+48h], eax
0x180001f5b  mov     [rbx+70h], rax
0x180001f5f  mov     dword ptr [rbx+78h], 0
0x180001f66  call    cs:__imp_??0STR@@QEAA@XZ; STR::STR(void)
0x180001f6c  lea     rcx, [rbx+0B8h]
0x180001f73  call    cs:__imp_??0STR@@QEAA@XZ; STR::STR(void)
0x180001f79  lea     rcx, [rbx+0F0h]
0x180001f80  call    cs:__imp_??0STR@@QEAA@XZ; STR::STR(void)
0x180001f86  lea     rcx, [rbx+128h]
0x180001f8d  call    cs:__imp_??0STR@@QEAA@XZ; STR::STR(void)
0x180001f93  xorps   xmm0, xmm0
0x180001f96  mov     qword ptr [rbx+160h], 0
0x180001fa1  mov     dword ptr [rbx+168h], 0
0x180001fab  lea     rcx, [rbx+170h]
0x180001fb2  movups  xmmword ptr [rbx+4Ch], xmm0
0x180001fb6  call    cs:__imp_IISInitializeCriticalSection
0x180001fbc  mov     rax, rbx
0x180001fbf  add     rsp, 20h
0x180001fc3  pop     rbx
0x180001fc4  retn
```
