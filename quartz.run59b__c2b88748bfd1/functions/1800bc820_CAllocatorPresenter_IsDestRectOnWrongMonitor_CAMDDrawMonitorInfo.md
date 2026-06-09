# CAllocatorPresenter::IsDestRectOnWrongMonitor(CAMDDrawMonitorInfo * *)

- ea: `0x1800bc820`
- end: `0x1800bc945`
- name: `?IsDestRectOnWrongMonitor@CAllocatorPresenter@@AEAA_NPEAPEAUCAMDDrawMonitorInfo@@@Z`
- size: `293`
- prototype: `bool __fastcall(CAllocatorPresenter *__hidden this, struct CAMDDrawMonitorInfo **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800bcfd0`

## callees

- `0x1800ba0e8`
- `0x1800bc820`
- `0x1800c2398`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x1800bc868`
- `USER32!GetSystemMetrics` at `0x1800bc868`
- `USER32!IsIconic` at `0x1800bc884`
- `USER32!IsIconic` at `0x1800bc884`
- `USER32!MonitorFromRect` at `0x1800bc909`
- `USER32!MonitorFromRect` at `0x1800bc909`
- `USER32!IsWindow` at `0x1800bc84f`
- `USER32!IsWindow` at `0x1800bc84f`
- `USER32!IsRectEmpty` at `0x1800bc8a2`
- `USER32!IsRectEmpty` at `0x1800bc8dd`
- `USER32!IsRectEmpty` at `0x1800bc8a2`
- `USER32!IsRectEmpty` at `0x1800bc8dd`

## pseudocode

```c
bool __fastcall CAllocatorPresenter::IsDestRectOnWrongMonitor(
        CAllocatorPresenter *this,
        struct CAMDDrawMonitorInfo **a2)
{
  __int64 v2; // rax
  HMONITOR v5; // rsi
  BOOL v6; // eax
  const RECT *v7; // rcx
  struct CAMDDrawMonitorInfo *Monitor; // rax

  v2 = *((_QWORD *)this + 4287);
  *a2 = (struct CAMDDrawMonitorInfo *)v2;
  v5 = *(HMONITOR *)(v2 + 40);
  *((_DWORD *)this + 8578) = 0;
  v6 = IsWindow(*((HWND *)this + 4326));
  if ( v6 )
  {
    if ( GetSystemMetrics(80) > 1 && !IsIconic(*((HWND *)this + 4326)) )
    {
      if ( !IsRectEmpty((const RECT *)((char *)this + 34476))
        && !ContainedRect(
              (const struct tagRECT *)((char *)this + 34476),
              (const struct tagRECT *)(*((_QWORD *)this + 4287) + 24LL)) )
      {
        *((_DWORD *)this + 8578) = 1;
      }
      if ( !IsRectEmpty((const RECT *)((char *)this + 34492))
        && !ContainedRect(
              (const struct tagRECT *)((char *)this + 34492),
              (const struct tagRECT *)(*((_QWORD *)this + 4287) + 24LL)) )
      {
        v5 = MonitorFromRect(v7, 2u);
        Monitor = CMonitorArray::FindMonitor((CAllocatorPresenter *)((char *)this + 112), v5);
        if ( Monitor )
          *a2 = Monitor;
      }
    }
    LOBYTE(v6) = *(_QWORD *)(*((_QWORD *)this + 4287) + 40LL) != (_QWORD)v5;
  }
  return v6;
}

```

## disassembly

```asm
0x1800bc820  push    rbx
0x1800bc822  push    rsi
0x1800bc823  push    rdi
0x1800bc824  push    r14
0x1800bc826  sub     rsp, 28h
0x1800bc82a  mov     rax, [rcx+85F8h]
0x1800bc831  mov     rbx, rcx
0x1800bc834  mov     r14, rdx
0x1800bc837  mov     [rdx], rax
0x1800bc83a  mov     rsi, [rax+28h]
0x1800bc83e  mov     dword ptr [rcx+8608h], 0
0x1800bc848  mov     rcx, [rcx+8730h]; hWnd
0x1800bc84f  call    cs:__imp_IsWindow
0x1800bc856  nop     dword ptr [rax+rax+00h]
0x1800bc85b  test    eax, eax
0x1800bc85d  jz      loc_1800BC93A
0x1800bc863  mov     ecx, 50h ; 'P'; nIndex
0x1800bc868  call    cs:__imp_GetSystemMetrics
0x1800bc86f  nop     dword ptr [rax+rax+00h]
0x1800bc874  cmp     eax, 1
0x1800bc877  jle     loc_1800BC92C
0x1800bc87d  mov     rcx, [rbx+8730h]; hWnd
0x1800bc884  call    cs:__imp_IsIconic
0x1800bc88b  nop     dword ptr [rax+rax+00h]
0x1800bc890  test    eax, eax
0x1800bc892  jnz     loc_1800BC92C
0x1800bc898  lea     rdi, [rbx+86ACh]
0x1800bc89f  mov     rcx, rdi; lprc
0x1800bc8a2  call    cs:__imp_IsRectEmpty
0x1800bc8a9  nop     dword ptr [rax+rax+00h]
0x1800bc8ae  test    eax, eax
0x1800bc8b0  jnz     short loc_1800BC8D3
0x1800bc8b2  mov     rdx, [rbx+85F8h]
0x1800bc8b9  mov     rcx, rdi; struct tagRECT *
0x1800bc8bc  add     rdx, 18h; struct tagRECT *
0x1800bc8c0  call    ?ContainedRect@@YA_NPEBUtagRECT@@0@Z; ContainedRect(tagRECT const *,tagRECT const *)
0x1800bc8c5  test    al, al
0x1800bc8c7  jnz     short loc_1800BC8D3
0x1800bc8c9  mov     dword ptr [rbx+8608h], 1
0x1800bc8d3  lea     rdi, [rbx+86BCh]
0x1800bc8da  mov     rcx, rdi; lprc
0x1800bc8dd  call    cs:__imp_IsRectEmpty
0x1800bc8e4  nop     dword ptr [rax+rax+00h]
0x1800bc8e9  test    eax, eax
0x1800bc8eb  jnz     short loc_1800BC92C
0x1800bc8ed  mov     rdx, [rbx+85F8h]
0x1800bc8f4  mov     rcx, rdi; struct tagRECT *
0x1800bc8f7  add     rdx, 18h; struct tagRECT *
0x1800bc8fb  call    ?ContainedRect@@YA_NPEBUtagRECT@@0@Z; ContainedRect(tagRECT const *,tagRECT const *)
0x1800bc900  test    al, al
0x1800bc902  jnz     short loc_1800BC92C
0x1800bc904  mov     edx, 2; dwFlags
0x1800bc909  call    cs:__imp_MonitorFromRect
0x1800bc910  nop     dword ptr [rax+rax+00h]
0x1800bc915  mov     rdx, rax; HMONITOR
0x1800bc918  lea     rcx, [rbx+70h]; this
0x1800bc91c  mov     rsi, rax
0x1800bc91f  call    ?FindMonitor@CMonitorArray@@QEAAPEAUCAMDDrawMonitorInfo@@PEAUHMONITOR__@@@Z; CMonitorArray::FindMonitor(HMONITOR__ *)
0x1800bc924  test    rax, rax
0x1800bc927  jz      short loc_1800BC92C
0x1800bc929  mov     [r14], rax
0x1800bc92c  mov     rcx, [rbx+85F8h]
0x1800bc933  cmp     [rcx+28h], rsi
0x1800bc937  setnz   al
0x1800bc93a  add     rsp, 28h
0x1800bc93e  pop     r14
0x1800bc940  pop     rdi
0x1800bc941  pop     rsi
0x1800bc942  pop     rbx
0x1800bc943  retn
```
