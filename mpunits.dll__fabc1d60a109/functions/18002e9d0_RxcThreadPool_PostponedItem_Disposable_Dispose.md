# RxcThreadPool_PostponedItem_Disposable_Dispose

- ea: `0x18002e9d0`
- end: `0x18002eb14`
- name: `RxcThreadPool_PostponedItem_Disposable_Dispose`
- size: `324`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180008c90`
- `0x18002dd50`
- `0x18002e9d0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002eaca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002eaca`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002eabd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002eabd`

## string_xrefs

- `0x18002e9ea`: `admin\wmi\winomi\mp\rxc\rxc.schedulers.threadpool.c`
- `0x18002ea0b`: `RxcThreadPool_PostponedItem_Disposable_Dispose`

## pseudocode

```c
__int64 __fastcall RxcThreadPool_PostponedItem_Disposable_Dispose(__int64 a1)
{
  __int64 v2; // rdx
  char *v3; // rax
  __int64 (__fastcall **v4)(); // rcx
  __int128 v5; // xmm1
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int64 result; // rax
  _QWORD v15[2]; // [rsp+20h] [rbp-158h] BYREF
  int v16; // [rsp+30h] [rbp-148h]
  int v17; // [rsp+34h] [rbp-144h]
  char v18; // [rsp+40h] [rbp-138h] BYREF

  if ( NITS_PRESENCE_STUB == 1 )
  {
    v2 = 2;
    v3 = &v18;
    v4 = NITS_STUB;
    do
    {
      v5 = *((_OWORD *)v4 + 1);
      *(_OWORD *)v3 = *(_OWORD *)v4;
      v6 = *((_OWORD *)v4 + 2);
      *((_OWORD *)v3 + 1) = v5;
      v7 = *((_OWORD *)v4 + 3);
      *((_OWORD *)v3 + 2) = v6;
      v8 = *((_OWORD *)v4 + 4);
      *((_OWORD *)v3 + 3) = v7;
      v9 = *((_OWORD *)v4 + 5);
      *((_OWORD *)v3 + 4) = v8;
      v10 = *((_OWORD *)v4 + 6);
      *((_OWORD *)v3 + 5) = v9;
      v11 = *((_OWORD *)v4 + 7);
      v4 += 16;
      *((_OWORD *)v3 + 6) = v10;
      *((_OWORD *)v3 + 7) = v11;
      v3 += 128;
      --v2;
    }
    while ( v2 );
    v12 = *((_OWORD *)v4 + 1);
    *(_OWORD *)v3 = *(_OWORD *)v4;
    v13 = *((_OWORD *)v4 + 2);
    *((_OWORD *)v3 + 1) = v12;
    *((_OWORD *)v3 + 2) = v13;
  }
  else
  {
    v15[0] = 0;
    v15[1] = "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedulers.threadpool.c";
    v16 = 348;
    v17 = -1;
    ((void (__fastcall *)(const wchar_t *, _QWORD *, _QWORD))BufferPostNotificationTrapMethod)(
      L"RxcThreadPool_PostponedItem_Disposable_Dispose",
      v15,
      0);
  }
  result = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 64), 3, 1);
  if ( result == 1 )
  {
    SetThreadpoolTimer(*(PTP_TIMER *)(a1 + 48), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)(a1 + 48), 1);
    result = *(_QWORD *)(a1 + 64);
    if ( result == 3 )
    {
      RxcThreadPool_BaseItem_Destruct(a1, 0);
      result = _InterlockedExchangeAdd64((volatile signed __int64 *)(a1 + 56), 0xFFFFFFFFFFFFFFFFuLL);
      if ( result == 1 )
        return Cache_DepositBack(*(_QWORD *)(a1 + 40) + 80LL, a1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002e9d0  mov     [rsp+arg_8], rbx
0x18002e9d5  push    rbp
0x18002e9d6  sub     rsp, 170h
0x18002e9dd  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002e9e5  mov     rbx, rcx
0x18002e9e8  jz      short loc_18002EA2C
0x18002e9ea  lea     rax, aAdminWmiWinomi_3; "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedu"...
0x18002e9f1  mov     [rsp+178h+var_158], 0
0x18002e9fa  mov     [rsp+178h+var_150], rax
0x18002e9ff  lea     rdx, [rsp+178h+var_158]
0x18002ea04  mov     rax, cs:off_180047A70
0x18002ea0b  lea     rcx, aRxcthreadpoolP_1; "RxcThreadPool_PostponedItem_Disposable_"...
0x18002ea12  xor     r8d, r8d
0x18002ea15  mov     [rsp+178h+var_148], 15Ch
0x18002ea1d  mov     [rsp+178h+var_144], 0FFFFFFFFh
0x18002ea25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea2a  jmp     short loc_18002EAA1
0x18002ea2c  mov     edx, 2
0x18002ea31  lea     rax, [rsp+178h+var_138]
0x18002ea36  lea     rcx, NITS_STUB
0x18002ea3d  lea     r8d, [rdx+7Eh]
0x18002ea41  movups  xmm0, xmmword ptr [rcx]
0x18002ea44  movups  xmm1, xmmword ptr [rcx+10h]
0x18002ea48  movups  xmmword ptr [rax], xmm0
0x18002ea4b  movups  xmm0, xmmword ptr [rcx+20h]
0x18002ea4f  movups  xmmword ptr [rax+10h], xmm1
0x18002ea53  movups  xmm1, xmmword ptr [rcx+30h]
0x18002ea57  movups  xmmword ptr [rax+20h], xmm0
0x18002ea5b  movups  xmm0, xmmword ptr [rcx+40h]
0x18002ea5f  movups  xmmword ptr [rax+30h], xmm1
0x18002ea63  movups  xmm1, xmmword ptr [rcx+50h]
0x18002ea67  movups  xmmword ptr [rax+40h], xmm0
0x18002ea6b  movups  xmm0, xmmword ptr [rcx+60h]
0x18002ea6f  movups  xmmword ptr [rax+50h], xmm1
0x18002ea73  movups  xmm1, xmmword ptr [rcx+70h]
0x18002ea77  add     rcx, r8
0x18002ea7a  movups  xmmword ptr [rax+60h], xmm0
0x18002ea7e  movups  xmmword ptr [rax+70h], xmm1
0x18002ea82  add     rax, r8
0x18002ea85  sub     rdx, 1
0x18002ea89  jnz     short loc_18002EA41
0x18002ea8b  movups  xmm0, xmmword ptr [rcx]
0x18002ea8e  movups  xmm1, xmmword ptr [rcx+10h]
0x18002ea92  movups  xmmword ptr [rax], xmm0
0x18002ea95  movups  xmm0, xmmword ptr [rcx+20h]
0x18002ea99  movups  xmmword ptr [rax+10h], xmm1
0x18002ea9d  movups  xmmword ptr [rax+20h], xmm0
0x18002eaa1  mov     ebp, 3
0x18002eaa6  lea     eax, [rbp-2]
0x18002eaa9  lock cmpxchg [rbx+40h], rbp
0x18002eaaf  jnz     short loc_18002EB03
0x18002eab1  mov     rcx, [rbx+30h]; pti
0x18002eab5  xor     r9d, r9d; msWindowLength
0x18002eab8  xor     r8d, r8d; msPeriod
0x18002eabb  xor     edx, edx; pftDueTime
0x18002eabd  call    cs:__imp_SetThreadpoolTimer
0x18002eac3  mov     rcx, [rbx+30h]; pti
0x18002eac7  lea     edx, [rbp-2]; fCancelPendingCallbacks
0x18002eaca  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002ead0  mov     rax, [rbx+40h]
0x18002ead4  cmp     rax, rbp
0x18002ead7  jnz     short loc_18002EB03
0x18002ead9  xor     edx, edx
0x18002eadb  mov     rcx, rbx
0x18002eade  call    RxcThreadPool_BaseItem_Destruct
0x18002eae3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002eae7  lock xadd [rbx+38h], rax
0x18002eaed  cmp     rax, 1
0x18002eaf1  jnz     short loc_18002EB03
0x18002eaf3  mov     rcx, [rbx+28h]
0x18002eaf7  mov     rdx, rbx
0x18002eafa  add     rcx, 50h ; 'P'
0x18002eafe  call    Cache_DepositBack
0x18002eb03  mov     rbx, [rsp+178h+arg_8]
0x18002eb0b  add     rsp, 170h
0x18002eb12  pop     rbp
0x18002eb13  retn
```
