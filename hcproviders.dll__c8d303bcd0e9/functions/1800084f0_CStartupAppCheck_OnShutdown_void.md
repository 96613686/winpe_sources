# CStartupAppCheck::_OnShutdown(void)

- ea: `0x1800084f0`
- end: `0x18000854a`
- name: `?_OnShutdown@CStartupAppCheck@@MEAAXXZ`
- size: `90`
- prototype: `void __fastcall(CStartupAppCheck *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800084f0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000850a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000850a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000851d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000851d`

## pseudocode

```c
void __fastcall CStartupAppCheck::_OnShutdown(CStartupAppCheck *this)
{
  struct _TP_WAIT *v2; // rcx
  __int64 v3; // rax

  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 30);
  if ( v2 )
  {
    SetThreadpoolWait(v2, 0, 0);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 30));
    v3 = *(_QWORD *)this;
    *((_QWORD *)this + 30) = 0;
    (*(void (__fastcall **)(CStartupAppCheck *))(v3 + 16))(this);
  }
}

```

## disassembly

```asm
0x1800084f0  push    rbx
0x1800084f2  sub     rsp, 20h
0x1800084f6  mov     rbx, rcx
0x1800084f9  mov     rcx, [rcx+0F0h]; pwa
0x180008500  test    rcx, rcx
0x180008503  jz      short loc_180008543
0x180008505  xor     r8d, r8d; pftTimeout
0x180008508  xor     edx, edx; h
0x18000850a  call    cs:__imp_SetThreadpoolWait
0x180008511  nop     dword ptr [rax+rax+00h]
0x180008516  mov     rcx, [rbx+0F0h]; pwa
0x18000851d  call    cs:__imp_CloseThreadpoolWait
0x180008524  nop     dword ptr [rax+rax+00h]
0x180008529  mov     rax, [rbx]
0x18000852c  mov     rcx, rbx
0x18000852f  mov     qword ptr [rbx+0F0h], 0
0x18000853a  mov     rax, [rax+10h]
0x18000853e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008543  add     rsp, 20h
0x180008547  pop     rbx
0x180008548  retn
```
