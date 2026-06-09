# VMR9::CAllocatorPresenter::IsDestRectOnWrongMonitor(VMR9::CAMDDrawMonitorInfo * *)

- ea: `0x1800e56d4`
- end: `0x1800e57fa`
- name: `?IsDestRectOnWrongMonitor@CAllocatorPresenter@VMR9@@AEAA_NPEAPEAUCAMDDrawMonitorInfo@2@@Z`
- size: `294`
- prototype: `bool __fastcall(VMR9::CAllocatorPresenter *__hidden this, struct VMR9::CAMDDrawMonitorInfo **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800e51e0`

## callees

- `0x1800c2398`
- `0x1800e4004`
- `0x1800e56d4`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x1800e571c`
- `USER32!GetSystemMetrics` at `0x1800e571c`
- `USER32!IsIconic` at `0x1800e5738`
- `USER32!IsIconic` at `0x1800e5738`
- `USER32!MonitorFromRect` at `0x1800e57ba`
- `USER32!MonitorFromRect` at `0x1800e57ba`
- `USER32!IsWindow` at `0x1800e5703`
- `USER32!IsWindow` at `0x1800e5703`
- `USER32!IsRectEmpty` at `0x1800e5756`
- `USER32!IsRectEmpty` at `0x1800e5791`
- `USER32!IsRectEmpty` at `0x1800e5756`
- `USER32!IsRectEmpty` at `0x1800e5791`

## pseudocode

```c
bool __fastcall VMR9::CAllocatorPresenter::IsDestRectOnWrongMonitor(
        VMR9::CAllocatorPresenter *this,
        struct VMR9::CAMDDrawMonitorInfo **a2)
{
  __int64 v2; // rax
  HMONITOR v5; // rsi
  BOOL v6; // eax
  const RECT *v7; // rcx
  HMONITOR v8; // rax
  struct VMR9::CAMDDrawMonitorInfo *Monitor; // rax

  v2 = *((_QWORD *)this + 2976);
  *a2 = (struct VMR9::CAMDDrawMonitorInfo *)v2;
  v5 = *(HMONITOR *)(v2 + 24);
  *((_DWORD *)this + 5956) = 0;
  v6 = IsWindow(*((HWND *)this + 3005));
  if ( v6 )
  {
    if ( GetSystemMetrics(80) > 1 && !IsIconic(*((HWND *)this + 3005)) )
    {
      if ( !IsRectEmpty((const RECT *)this + 1494)
        && !ContainedRect((const struct tagRECT *)this + 1494, (const struct tagRECT *)(*((_QWORD *)this + 2976) + 4LL)) )
      {
        *((_DWORD *)this + 5956) = 1;
      }
      if ( !IsRectEmpty((const RECT *)this + 1495)
        && !ContainedRect((const struct tagRECT *)this + 1495, (const struct tagRECT *)(*((_QWORD *)this + 2976) + 4LL)) )
      {
        v8 = MonitorFromRect(v7, 0);
        if ( v8 )
          v5 = v8;
        Monitor = VMR9::CMonitorArray::FindMonitor((VMR9::CAllocatorPresenter *)((char *)this + 112), v5);
        if ( Monitor )
          *a2 = Monitor;
      }
    }
    LOBYTE(v6) = *(_QWORD *)(*((_QWORD *)this + 2976) + 24LL) != (_QWORD)v5;
  }
  return v6;
}

```

## disassembly

```asm
0x1800e56d4  push    rbx
0x1800e56d6  push    rsi
0x1800e56d7  push    rdi
0x1800e56d8  push    r14
0x1800e56da  sub     rsp, 28h
0x1800e56de  mov     rax, [rcx+5D00h]
0x1800e56e5  mov     rbx, rcx
0x1800e56e8  mov     r14, rdx
0x1800e56eb  mov     [rdx], rax
0x1800e56ee  mov     rsi, [rax+18h]
0x1800e56f2  mov     dword ptr [rcx+5D10h], 0
0x1800e56fc  mov     rcx, [rcx+5DE8h]; hWnd
0x1800e5703  call    cs:__imp_IsWindow
0x1800e570a  nop     dword ptr [rax+rax+00h]
0x1800e570f  test    eax, eax
0x1800e5711  jz      loc_1800E57EF
0x1800e5717  mov     ecx, 50h ; 'P'; nIndex
0x1800e571c  call    cs:__imp_GetSystemMetrics
0x1800e5723  nop     dword ptr [rax+rax+00h]
0x1800e5728  cmp     eax, 1
0x1800e572b  jle     loc_1800E57E1
0x1800e5731  mov     rcx, [rbx+5DE8h]; hWnd
0x1800e5738  call    cs:__imp_IsIconic
0x1800e573f  nop     dword ptr [rax+rax+00h]
0x1800e5744  test    eax, eax
0x1800e5746  jnz     loc_1800E57E1
0x1800e574c  lea     rdi, [rbx+5D60h]
0x1800e5753  mov     rcx, rdi; lprc
0x1800e5756  call    cs:__imp_IsRectEmpty
0x1800e575d  nop     dword ptr [rax+rax+00h]
0x1800e5762  test    eax, eax
0x1800e5764  jnz     short loc_1800E5787
0x1800e5766  mov     rdx, [rbx+5D00h]
0x1800e576d  mov     rcx, rdi; struct tagRECT *
0x1800e5770  add     rdx, 4; struct tagRECT *
0x1800e5774  call    ?ContainedRect@@YA_NPEBUtagRECT@@0@Z; ContainedRect(tagRECT const *,tagRECT const *)
0x1800e5779  test    al, al
0x1800e577b  jnz     short loc_1800E5787
0x1800e577d  mov     dword ptr [rbx+5D10h], 1
0x1800e5787  lea     rdi, [rbx+5D70h]
0x1800e578e  mov     rcx, rdi; lprc
0x1800e5791  call    cs:__imp_IsRectEmpty
0x1800e5798  nop     dword ptr [rax+rax+00h]
0x1800e579d  test    eax, eax
0x1800e579f  jnz     short loc_1800E57E1
0x1800e57a1  mov     rdx, [rbx+5D00h]
0x1800e57a8  mov     rcx, rdi; struct tagRECT *
0x1800e57ab  add     rdx, 4; struct tagRECT *
0x1800e57af  call    ?ContainedRect@@YA_NPEBUtagRECT@@0@Z; ContainedRect(tagRECT const *,tagRECT const *)
0x1800e57b4  test    al, al
0x1800e57b6  jnz     short loc_1800E57E1
0x1800e57b8  xor     edx, edx; dwFlags
0x1800e57ba  call    cs:__imp_MonitorFromRect
0x1800e57c1  nop     dword ptr [rax+rax+00h]
0x1800e57c6  test    rax, rax
0x1800e57c9  lea     rcx, [rbx+70h]; this
0x1800e57cd  cmovnz  rsi, rax
0x1800e57d1  mov     rdx, rsi; HMONITOR
0x1800e57d4  call    ?FindMonitor@CMonitorArray@VMR9@@QEAAPEAUCAMDDrawMonitorInfo@2@PEAUHMONITOR__@@@Z; VMR9::CMonitorArray::FindMonitor(HMONITOR__ *)
0x1800e57d9  test    rax, rax
0x1800e57dc  jz      short loc_1800E57E1
0x1800e57de  mov     [r14], rax
0x1800e57e1  mov     rax, [rbx+5D00h]
0x1800e57e8  cmp     [rax+18h], rsi
0x1800e57ec  setnz   al
0x1800e57ef  add     rsp, 28h
0x1800e57f3  pop     r14
0x1800e57f5  pop     rdi
0x1800e57f6  pop     rsi
0x1800e57f7  pop     rbx
0x1800e57f8  retn
```
