# NcaTimerTriggerRegisterWait

- ea: `0x18000eec0`
- end: `0x18000efdf`
- name: `NcaTimerTriggerRegisterWait`
- size: `287`
- prototype: `__int64 __fastcall(struct _TP_TIMER *, __int64, struct _TP_TIMER *, __int64, PTP_TIMER **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011744`

## callees

- `0x180004f34`
- `0x18000eec0`
- `0x18001abd4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000efb8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000efb8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ef57`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ef57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef6b`

## pseudocode

```c
__int64 __fastcall NcaTimerTriggerRegisterWait(
        struct _TP_TIMER *a1,
        __int64 a2,
        struct _TP_TIMER *a3,
        __int64 a4,
        PTP_TIMER **a5)
{
  PTP_TIMER *v7; // rax
  PTP_TIMER *v8; // rbx
  DWORD LastError; // edi
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  PTP_TIMER ThreadpoolTimer; // rax
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp+10h] BYREF

  pftDueTime = 0;
  v7 = (PTP_TIMER *)NcaAlloc(0x28u);
  v8 = v7;
  if ( v7 )
  {
    v7[1] = a3;
    v7[2] = 0;
    v7[3] = a1;
    *((_DWORD *)v7 + 8) = 60;
    ThreadpoolTimer = CreateThreadpoolTimer(TimerCallback, v7, 0);
    *v8 = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      pftDueTime = (struct _FILETIME)-10000000LL;
      LastError = 0;
      SetThreadpoolTimer(*v8, &pftDueTime, 0xEA60u, 0x1F4u);
      *a5 = v8;
      return LastError;
    }
    LastError = GetLastError();
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 12;
      goto LABEL_5;
    }
  }
  else
  {
    LastError = 14;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 10;
LABEL_5:
      WPP_SF_d(v10[2], v11, WPP_5d0151c57d1438c04f8a181df6bf2fb2_Traceguids, LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18000eec0  mov     rax, rsp
0x18000eec3  mov     [rax+8], rbx
0x18000eec7  mov     [rax+18h], rsi
0x18000eecb  mov     [rax+10h], rdx
0x18000eecf  push    rdi
0x18000eed0  sub     rsp, 20h
0x18000eed4  mov     rsi, rcx
0x18000eed7  mov     qword ptr [rax+10h], 0
0x18000eedf  mov     ecx, 28h ; '('
0x18000eee4  mov     rdi, r8
0x18000eee7  call    NcaAlloc
0x18000eeec  mov     rbx, rax
0x18000eeef  test    rax, rax
0x18000eef2  jnz     short loc_18000EF33
0x18000eef4  lea     edi, [rax+0Eh]
0x18000eef7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eefe  lea     rax, WPP_GLOBAL_Control
0x18000ef05  cmp     rcx, rax
0x18000ef08  jz      loc_18000EFCC
0x18000ef0e  test    byte ptr [rcx+1Ch], 1
0x18000ef12  jz      loc_18000EFCC
0x18000ef18  lea     edx, [rbx+0Ah]
0x18000ef1b  mov     rcx, [rcx+10h]
0x18000ef1f  lea     r8, WPP_5d0151c57d1438c04f8a181df6bf2fb2_Traceguids
0x18000ef26  mov     r9d, edi
0x18000ef29  call    WPP_SF_d
0x18000ef2e  jmp     loc_18000EFCC
0x18000ef33  xor     r8d, r8d; pcbe
0x18000ef36  mov     [rax+8], rdi
0x18000ef3a  mov     rdx, rbx; pv
0x18000ef3d  mov     qword ptr [rax+10h], 0
0x18000ef45  lea     rcx, ?TimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ef4c  mov     [rax+18h], rsi
0x18000ef50  mov     dword ptr [rax+20h], 3Ch ; '<'
0x18000ef57  call    cs:__imp_CreateThreadpoolTimer
0x18000ef5e  nop     dword ptr [rax+rax+00h]
0x18000ef63  mov     [rbx], rax
0x18000ef66  test    rax, rax
0x18000ef69  jnz     short loc_18000EF99
0x18000ef6b  call    cs:__imp_GetLastError
0x18000ef72  nop     dword ptr [rax+rax+00h]
0x18000ef77  mov     edi, eax
0x18000ef79  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef80  lea     rax, WPP_GLOBAL_Control
0x18000ef87  cmp     rcx, rax
0x18000ef8a  jz      short loc_18000EFCC
0x18000ef8c  test    byte ptr [rcx+1Ch], 1
0x18000ef90  jz      short loc_18000EFCC
0x18000ef92  mov     edx, 0Ch
0x18000ef97  jmp     short loc_18000EF1B
0x18000ef99  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFFF676980h
0x18000efa2  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000efa7  mov     rcx, [rbx]; pti
0x18000efaa  xor     edi, edi
0x18000efac  mov     r9d, 1F4h; msWindowLength
0x18000efb2  mov     r8d, 0EA60h; msPeriod
0x18000efb8  call    cs:__imp_SetThreadpoolTimer
0x18000efbf  nop     dword ptr [rax+rax+00h]
0x18000efc4  mov     rax, [rsp+28h+arg_20]
0x18000efc9  mov     [rax], rbx
0x18000efcc  mov     rbx, [rsp+28h+arg_0]
0x18000efd1  mov     eax, edi
0x18000efd3  mov     rsi, [rsp+28h+arg_10]
0x18000efd8  add     rsp, 20h
0x18000efdc  pop     rdi
0x18000efdd  retn
```
