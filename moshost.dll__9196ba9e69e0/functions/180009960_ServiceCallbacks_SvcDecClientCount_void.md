# ServiceCallbacks::SvcDecClientCount(void)

- ea: `0x180009960`
- end: `0x1800099f2`
- name: `?SvcDecClientCount@ServiceCallbacks@@UEAAHXZ`
- size: `146`
- prototype: `__int64 __fastcall(ServiceCallbacks *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180009960`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800099a6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800099a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009992`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800099e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009992`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800099e4`

## pseudocode

```c
__int64 __fastcall ServiceCallbacks::SvcDecClientCount(ServiceCallbacks *this)
{
  unsigned int v1; // ebx
  struct _FILETIME v3; // [rsp+38h] [rbp+10h] BYREF
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+18h] BYREF

  v1 = 0;
  if ( pti )
  {
    if ( dword_1800185D8 )
    {
      pftDueTime = 0;
      SetThreadpoolTimer(pti, &pftDueTime, 0, 0);
      v1 = 1;
      WaitForThreadpoolTimerCallbacks(pti, 1);
      if ( _InterlockedExchangeAdd(&dword_1800185D8, 0xFFFFFFFF) == 1 )
      {
        v3 = (struct _FILETIME)-(__int64)(unsigned int)(10000000 * dword_1800186E8);
        SetThreadpoolTimer(pti, &v3, 0, 100 * dword_1800186E8);
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180009960  push    rbx
0x180009962  sub     rsp, 20h
0x180009966  xor     ebx, ebx
0x180009968  cmp     cs:pti, rbx
0x18000996f  jz      short loc_1800099EA
0x180009971  mov     eax, cs:dword_1800185D8
0x180009977  test    eax, eax
0x180009979  jz      short loc_1800099EA
0x18000997b  mov     rcx, cs:pti; pti
0x180009982  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180009987  xor     r9d, r9d; msWindowLength
0x18000998a  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rbx
0x18000998f  xor     r8d, r8d; msPeriod
0x180009992  call    cs:__imp_SetThreadpoolTimer
0x180009998  mov     rcx, cs:pti; pti
0x18000999f  mov     ebx, 1
0x1800099a4  mov     edx, ebx; fCancelPendingCallbacks
0x1800099a6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800099ac  or      eax, 0FFFFFFFFh
0x1800099af  lock xadd cs:dword_1800185D8, eax
0x1800099b7  cmp     eax, ebx
0x1800099b9  jnz     short loc_1800099EA
0x1800099bb  imul    ecx, cs:dword_1800186E8, 989680h
0x1800099c5  lea     rdx, [rsp+28h+arg_8]; pftDueTime
0x1800099ca  imul    r9d, cs:dword_1800186E8, 64h ; 'd'; msWindowLength
0x1800099d2  xor     r8d, r8d; msPeriod
0x1800099d5  neg     rcx
0x1800099d8  mov     qword ptr [rsp+28h+arg_8.dwLowDateTime], rcx
0x1800099dd  mov     rcx, cs:pti; pti
0x1800099e4  call    cs:__imp_SetThreadpoolTimer
0x1800099ea  mov     eax, ebx
0x1800099ec  add     rsp, 20h
0x1800099f0  pop     rbx
0x1800099f1  retn
```
