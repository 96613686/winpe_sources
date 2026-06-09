# WxCreateThreadpoolTimer(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *),void *,_TP_CALLBACK_ENVIRON_V3 *,_TP_TIMER * *)

- ea: `0x1800195a8`
- end: `0x1800196a1`
- name: `?WxCreateThreadpoolTimer@@YAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z1PEAU_TP_CALLBACK_ENVIRON_V3@@PEAPEAU2@@Z`
- size: `249`
- prototype: `__int64 __fastcall(void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *), void *, struct _TP_CALLBACK_ENVIRON_V3 *, struct _TP_TIMER **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018cb8`

## callees

- `0x1800195a8`
- `0x1800196a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019630`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019630`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019617`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019617`

## pseudocode

```c
__int64 __fastcall WxCreateThreadpoolTimer(
        void (*a1)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *),
        void *a2,
        struct _TP_CALLBACK_ENVIRON_V3 *a3,
        struct _TP_TIMER **a4)
{
  signed int v5; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  signed int LastError; // eax

  if ( a4 )
  {
    *a4 = 0;
    if ( *(_BYTE *)(qword_1800426A0 + 72) )
    {
      v5 = -2147024809;
    }
    else
    {
      ThreadpoolTimer = CreateThreadpoolTimer(
                          (PTP_TIMER_CALLBACK)FailFastThreadpoolTimerCallback<&private: static void CRpcWatchDog::TimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)>,
                          &g_RpcWatchDog,
                          0);
      if ( ThreadpoolTimer )
      {
        v5 = 0;
        *a4 = ThreadpoolTimer;
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( v5 >= 0 )
          v5 = -2147418113;
      }
    }
  }
  else
  {
    v5 = -2147024809;
  }
  WxCloseThreadpoolTimer(0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800195a8  mov     rax, rsp
0x1800195ab  mov     [rax+8], rbx
0x1800195af  mov     [rax+10h], rsi
0x1800195b3  push    rdi
0x1800195b4  sub     rsp, 30h
0x1800195b8  mov     rsi, r9
0x1800195bb  mov     dword ptr [rax+1Ch], 0
0x1800195c2  xor     edi, edi
0x1800195c4  mov     [rax-18h], rdi
0x1800195c8  test    r9, r9
0x1800195cb  jz      short loc_1800195D0
0x1800195cd  mov     [r9], rdi
0x1800195d0  test    rsi, rsi
0x1800195d3  jnz     short loc_1800195E7
0x1800195d5  mov     ebx, 80070057h
0x1800195da  mov     [rsp+38h+arg_14], 0A3h
0x1800195e2  jmp     loc_180019686
0x1800195e7  mov     rax, cs:qword_1800426A0
0x1800195ee  cmp     [rax+48h], dil
0x1800195f2  jz      short loc_180019606
0x1800195f4  mov     ebx, 80070057h
0x1800195f9  mov     [rsp+38h+arg_14], 0A5h
0x180019601  jmp     loc_180019686
0x180019606  xor     r8d, r8d; pcbe
0x180019609  lea     rdx, ?g_RpcWatchDog@@3VCRpcWatchDog@@A; pv
0x180019610  lea     rcx, ??$FailFastThreadpoolTimerCallback@$1?TimerCallback@CRpcWatchDog@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180019617  call    cs:__imp_CreateThreadpoolTimer
0x18001961e  nop     dword ptr [rax+rax+00h]
0x180019623  mov     rdi, rax
0x180019626  mov     [rsp+38h+var_18], rax
0x18001962b  test    rax, rax
0x18001962e  jnz     short loc_180019667
0x180019630  call    cs:__imp_GetLastError
0x180019637  nop     dword ptr [rax+rax+00h]
0x18001963c  mov     ebx, eax
0x18001963e  test    eax, eax
0x180019640  jle     short loc_18001964B
0x180019642  movzx   ebx, ax
0x180019645  or      ebx, 80070000h
0x18001964b  mov     [rsp+38h+arg_10], ebx
0x18001964f  mov     eax, 8000FFFFh
0x180019654  test    ebx, ebx
0x180019656  cmovns  ebx, eax
0x180019659  mov     [rsp+38h+arg_10], ebx
0x18001965d  mov     [rsp+38h+arg_14], 0AAh
0x180019665  jmp     short loc_180019686
0x180019667  xor     ebx, ebx
0x180019669  mov     [rsp+38h+arg_10], ebx
0x18001966d  mov     [rsi], rax
0x180019670  xor     edi, edi
0x180019672  jmp     short loc_180019686
0x180019674  mov     ebx, 80070057h
0x180019679  mov     [rsp+38h+arg_14], 0AEh
0x180019681  mov     rdi, [rsp+38h+var_18]
0x180019686  mov     rcx, rdi; struct _TP_TIMER *
0x180019689  call    ?WxCloseThreadpoolTimer@@YAXPEAU_TP_TIMER@@@Z; WxCloseThreadpoolTimer(_TP_TIMER *)
0x18001968e  mov     eax, ebx
0x180019690  mov     rbx, [rsp+38h+arg_0]
0x180019695  mov     rsi, [rsp+38h+arg_8]
0x18001969a  add     rsp, 30h
0x18001969e  pop     rdi
0x18001969f  retn
0x180030a36  push    rbp
0x180030a38  sub     rsp, 20h
0x180030a3c  mov     rbp, rdx
0x180030a3f  mov     rax, [rcx]
0x180030a42  xor     ecx, ecx
0x180030a44  cmp     dword ptr [rax], 0C000000Dh
0x180030a4a  setz    cl
0x180030a4d  mov     eax, ecx
0x180030a4f  add     rsp, 20h
0x180030a53  pop     rbp
0x180030a54  retn
```
