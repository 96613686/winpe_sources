# WxCreateThreadpoolTimer(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *),void *,_TP_CALLBACK_ENVIRON_V3 *,_TP_TIMER * *)

- ea: `0x180047928`
- end: `0x180047a11`
- name: `?WxCreateThreadpoolTimer@@YAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z1PEAU_TP_CALLBACK_ENVIRON_V3@@PEAPEAU2@@Z`
- size: `233`
- prototype: `__int64 __fastcall(void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *), void *, struct _TP_CALLBACK_ENVIRON_V3 *, struct _TP_TIMER **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800199d8`

## callees

- `0x18001526c`
- `0x180047928`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800479a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800479a7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180047994`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180047994`

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
    if ( *(_BYTE *)(qword_1800618B0 + 72) )
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
0x180047928  mov     rax, rsp
0x18004792b  mov     [rax+8], rbx
0x18004792f  mov     [rax+10h], rsi
0x180047933  push    rdi
0x180047934  sub     rsp, 30h
0x180047938  mov     rsi, r9
0x18004793b  mov     dword ptr [rax+1Ch], 0
0x180047942  xor     edi, edi
0x180047944  mov     [rax-18h], rdi
0x180047948  test    r9, r9
0x18004794b  jz      short loc_180047950
0x18004794d  mov     [r9], rdi
0x180047950  test    rsi, rsi
0x180047953  jnz     short loc_180047967
0x180047955  mov     ebx, 80070057h
0x18004795a  mov     [rsp+38h+arg_14], 0A3h
0x180047962  jmp     loc_1800479F7
0x180047967  mov     rax, cs:qword_1800618B0
0x18004796e  cmp     [rax+48h], dil
0x180047972  jz      short loc_180047983
0x180047974  mov     ebx, 80070057h
0x180047979  mov     [rsp+38h+arg_14], 0A5h
0x180047981  jmp     short loc_1800479F7
0x180047983  xor     r8d, r8d; pcbe
0x180047986  lea     rdx, ?g_RpcWatchDog@@3VCRpcWatchDog@@A; pv
0x18004798d  lea     rcx, ??$FailFastThreadpoolTimerCallback@$1?TimerCallback@CRpcWatchDog@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180047994  call    cs:__imp_CreateThreadpoolTimer
0x18004799a  mov     rdi, rax
0x18004799d  mov     [rsp+38h+var_18], rax
0x1800479a2  test    rax, rax
0x1800479a5  jnz     short loc_1800479D8
0x1800479a7  call    cs:__imp_GetLastError
0x1800479ad  mov     ebx, eax
0x1800479af  test    eax, eax
0x1800479b1  jle     short loc_1800479BC
0x1800479b3  movzx   ebx, ax
0x1800479b6  or      ebx, 80070000h
0x1800479bc  mov     [rsp+38h+arg_10], ebx
0x1800479c0  mov     eax, 8000FFFFh
0x1800479c5  test    ebx, ebx
0x1800479c7  cmovns  ebx, eax
0x1800479ca  mov     [rsp+38h+arg_10], ebx
0x1800479ce  mov     [rsp+38h+arg_14], 0AAh
0x1800479d6  jmp     short loc_1800479F7
0x1800479d8  xor     ebx, ebx
0x1800479da  mov     [rsp+38h+arg_10], ebx
0x1800479de  mov     [rsi], rax
0x1800479e1  xor     edi, edi
0x1800479e3  jmp     short loc_1800479F7
0x1800479e5  mov     ebx, 80070057h
0x1800479ea  mov     [rsp+38h+arg_14], 0AEh
0x1800479f2  mov     rdi, [rsp+38h+var_18]
0x1800479f7  mov     rcx, rdi; struct _TP_TIMER *
0x1800479fa  call    ?WxCloseThreadpoolTimer@@YAXPEAU_TP_TIMER@@@Z; WxCloseThreadpoolTimer(_TP_TIMER *)
0x1800479ff  mov     eax, ebx
0x180047a01  mov     rbx, [rsp+38h+arg_0]
0x180047a06  mov     rsi, [rsp+38h+arg_8]
0x180047a0b  add     rsp, 30h
0x180047a0f  pop     rdi
0x180047a10  retn
0x180048015  push    rbp
0x180048017  sub     rsp, 20h
0x18004801b  mov     rbp, rdx
0x18004801e  mov     rax, [rcx]
0x180048021  xor     ecx, ecx
0x180048023  cmp     dword ptr [rax], 0C000000Dh
0x180048029  setz    cl
0x18004802c  mov     eax, ecx
0x18004802e  add     rsp, 20h
0x180048032  pop     rbp
0x180048033  retn
```
