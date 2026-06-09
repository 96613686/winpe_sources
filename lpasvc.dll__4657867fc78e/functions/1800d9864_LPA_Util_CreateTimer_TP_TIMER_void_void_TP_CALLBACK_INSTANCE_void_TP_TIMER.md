# LPA::Util::CreateTimer(_TP_TIMER * &,void *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *))

- ea: `0x1800d9864`
- end: `0x1800d98ab`
- name: `?CreateTimer@Util@LPA@@YAJAEAPEAU_TP_TIMER@@PEAXP6AXPEAU_TP_CALLBACK_INSTANCE@@1PEAU3@@Z@Z`
- size: `71`
- prototype: `int(LPA::Util *__hidden this, struct _TP_TIMER **, void *, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *))`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18006d944`
- `0x180080484`
- `0x1800956ec`
- `0x180095738`
- `0x1800b1768`
- `0x1800d8244`

## callees

- `0x18006ba8c`
- `0x1800d96e0`
- `0x1800d9864`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d988b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d988b`

## pseudocode

```c
__int64 __fastcall LPA::Util::CreateTimer(
        PTP_TIMER *this,
        struct _TP_TIMER **a2,
        void (__stdcall *a3)(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer),
        void (*a4)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *))
{
  unsigned int v4; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
  CommonUtil *v9; // rcx

  v4 = 0;
  if ( *this )
    LPA::Util::CancelTimer(this, a2);
  ThreadpoolTimer = CreateThreadpoolTimer(a3, a2, 0);
  *this = ThreadpoolTimer;
  if ( !ThreadpoolTimer )
    return (unsigned int)CommonUtil::GetLastErrorToHResultAndForceFailure(v9);
  return v4;
}

```

## disassembly

```asm
0x1800d9864  push    rbx
0x1800d9866  push    rbp
0x1800d9867  push    rsi
0x1800d9868  push    rdi
0x1800d9869  sub     rsp, 28h
0x1800d986d  xor     ebx, ebx
0x1800d986f  mov     rsi, r8
0x1800d9872  mov     rbp, rdx
0x1800d9875  mov     rdi, rcx
0x1800d9878  cmp     [rcx], rbx
0x1800d987b  jz      short loc_1800D9882
0x1800d987d  call    ?CancelTimer@Util@LPA@@YAXAEAPEAU_TP_TIMER@@@Z; LPA::Util::CancelTimer(_TP_TIMER * &)
0x1800d9882  xor     r8d, r8d; pcbe
0x1800d9885  mov     rdx, rbp; pv
0x1800d9888  mov     rcx, rsi; pfnti
0x1800d988b  call    cs:__imp_CreateThreadpoolTimer
0x1800d9891  mov     [rdi], rax
0x1800d9894  test    rax, rax
0x1800d9897  jnz     short loc_1800D98A0
0x1800d9899  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800d989e  mov     ebx, eax
0x1800d98a0  mov     eax, ebx
0x1800d98a2  add     rsp, 28h
0x1800d98a6  pop     rdi
0x1800d98a7  pop     rsi
0x1800d98a8  pop     rbp
0x1800d98a9  pop     rbx
0x1800d98aa  retn
```
