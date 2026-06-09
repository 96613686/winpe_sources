# StartManagementTimer::Start(IAepDevnodeManagementCallback *,CWiGigDAFProviderDevnodeManagement *)

- ea: `0x18000f208`
- end: `0x18000f2e8`
- name: `?Start@StartManagementTimer@@QEAAJPEAUIAepDevnodeManagementCallback@@PEAVCWiGigDAFProviderDevnodeManagement@@@Z`
- size: `224`
- prototype: `signed int __fastcall(struct _TP_TIMER **pv, struct IAepDevnodeManagementCallback *, struct CWiGigDAFProviderDevnodeManagement *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f2f0`

## callees

- `0x18000f208`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f29f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f29f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f2d0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f2d0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f291`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f291`

## pseudocode

```c
signed int __fastcall StartManagementTimer::Start(
        struct _TP_TIMER **pv,
        struct IAepDevnodeManagementCallback *a2,
        struct CWiGigDAFProviderDevnodeManagement *a3)
{
  struct IAepDevnodeManagementCallback *v5; // rcx
  struct CWiGigDAFProviderDevnodeManagement *v7; // rcx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  signed int result; // eax
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v5 = pv[2];
  if ( v5 != a2 )
  {
    if ( v5 )
      (*(void (__fastcall **)(struct IAepDevnodeManagementCallback *))(*(_QWORD *)v5 + 16LL))(v5);
    pv[2] = a2;
    if ( a2 )
      (*(void (__fastcall **)(struct IAepDevnodeManagementCallback *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  v7 = pv[3];
  if ( v7 != a3 )
  {
    if ( v7 )
      (*(void (__fastcall **)(struct CWiGigDAFProviderDevnodeManagement *))(*(_QWORD *)v7 + 16LL))(v7);
    pv[3] = a3;
    if ( a3 )
      (*(void (__fastcall **)(struct CWiGigDAFProviderDevnodeManagement *))(*(_QWORD *)a3 + 8LL))(a3);
  }
  ThreadpoolTimer = CreateThreadpoolTimer(StartManagementTimer::StaticTimerCallback, pv, 0);
  *pv = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    pftDueTime = 0;
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0x3E8u, 0x1F4u);
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000f208  mov     [rsp+arg_8], rbx
0x18000f20d  mov     [rsp+arg_10], rsi
0x18000f212  push    rdi
0x18000f213  sub     rsp, 20h
0x18000f217  mov     rbx, rcx
0x18000f21a  mov     rdi, r8
0x18000f21d  mov     rcx, [rcx+10h]
0x18000f221  mov     rsi, rdx
0x18000f224  cmp     rcx, rdx
0x18000f227  jz      short loc_18000F252
0x18000f229  test    rcx, rcx
0x18000f22c  jz      short loc_18000F23A
0x18000f22e  mov     rax, [rcx]
0x18000f231  mov     rax, [rax+10h]
0x18000f235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f23a  mov     [rbx+10h], rsi
0x18000f23e  test    rsi, rsi
0x18000f241  jz      short loc_18000F252
0x18000f243  mov     rax, [rsi]
0x18000f246  mov     rcx, rsi
0x18000f249  mov     rax, [rax+8]
0x18000f24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f252  mov     rcx, [rbx+18h]
0x18000f256  cmp     rcx, rdi
0x18000f259  jz      short loc_18000F284
0x18000f25b  test    rcx, rcx
0x18000f25e  jz      short loc_18000F26C
0x18000f260  mov     rax, [rcx]
0x18000f263  mov     rax, [rax+10h]
0x18000f267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f26c  mov     [rbx+18h], rdi
0x18000f270  test    rdi, rdi
0x18000f273  jz      short loc_18000F284
0x18000f275  mov     rax, [rdi]
0x18000f278  mov     rcx, rdi
0x18000f27b  mov     rax, [rax+8]
0x18000f27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f284  xor     r8d, r8d; pcbe
0x18000f287  lea     rcx, ?StaticTimerCallback@StartManagementTimer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000f28e  mov     rdx, rbx; pv
0x18000f291  call    cs:__imp_CreateThreadpoolTimer
0x18000f297  mov     [rbx], rax
0x18000f29a  test    rax, rax
0x18000f29d  jnz     short loc_18000F2B3
0x18000f29f  call    cs:__imp_GetLastError
0x18000f2a5  test    eax, eax
0x18000f2a7  jle     short loc_18000F2D8
0x18000f2a9  movzx   eax, ax
0x18000f2ac  or      eax, 80070000h
0x18000f2b1  jmp     short loc_18000F2D8
0x18000f2b3  mov     r9d, 1F4h; msWindowLength
0x18000f2b9  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0
0x18000f2c2  mov     r8d, 3E8h; msPeriod
0x18000f2c8  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000f2cd  mov     rcx, rax; pti
0x18000f2d0  call    cs:__imp_SetThreadpoolTimer
0x18000f2d6  xor     eax, eax
0x18000f2d8  mov     rbx, [rsp+28h+arg_8]
0x18000f2dd  mov     rsi, [rsp+28h+arg_10]
0x18000f2e2  add     rsp, 20h
0x18000f2e6  pop     rdi
0x18000f2e7  retn
```
