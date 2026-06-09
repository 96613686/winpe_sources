# CQueryContext::AcquireResource(void)

- ea: `0x180050438`
- end: `0x180050579`
- name: `?AcquireResource@CQueryContext@@IEAAJXZ`
- size: `321`
- prototype: `signed int __fastcall(_QWORD *pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800272ec`

## callees

- `0x18003bc80`
- `0x180050438`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180050487`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180050487`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050499`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050499`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800504e0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800504e0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800504c1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800504c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005050d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005050d`
- `RMCLIENT!RmAcquireResources` at `0x18005055d`
- `RMCLIENT!RmAcquireResources` at `0x18005055d`

## pseudocode

```c
signed int __fastcall CQueryContext::AcquireResource(_QWORD *pv)
{
  HANDLE EventW; // rax
  signed int result; // eax
  PTP_WAIT ThreadpoolWait; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  void *v6; // rdx
  struct _TP_WAIT *v7; // rcx
  int v8; // [rsp+50h] [rbp-38h] BYREF
  _QWORD v9[2]; // [rsp+58h] [rbp-30h] BYREF
  int v10; // [rsp+68h] [rbp-20h]
  int v11; // [rsp+6Ch] [rbp-1Ch]

  v8 = 0;
  v9[0] = 47;
  v9[1] = 1;
  v10 = 2;
  v11 = 1;
  EventW = CreateEventW(0, 0, 0, 0);
  pv[64] = EventW;
  if ( EventW
    && (ThreadpoolWait = CreateThreadpoolWait(CQueryContext::ResourceWaitCallback, pv, 0), (pv[65] = ThreadpoolWait) != 0)
    && (ThreadpoolTimer = CreateThreadpoolTimer(CQueryContext::ResourceTimerCallback, pv, 0),
        (pv[66] = ThreadpoolTimer) != 0) )
  {
    v6 = (void *)pv[64];
    v7 = (struct _TP_WAIT *)pv[65];
    *((_DWORD *)pv + 138) = 1;
    SetThreadpoolWait(v7, v6, 0);
    return ((__int64 (__fastcall *)(__int64, _QWORD *, _QWORD, _QWORD, _QWORD *, _QWORD, _DWORD, int, int *, _QWORD *))RmAcquireResources)(
             1,
             v9,
             0,
             *((unsigned int *)pv + 100),
             pv,
             pv[64],
             0,
             2,
             &v8,
             pv + 67);
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
0x180050438  push    rbx
0x18005043a  sub     rsp, 80h
0x180050441  mov     rax, cs:__security_cookie
0x180050448  xor     rax, rsp
0x18005044b  mov     [rsp+88h+var_18], rax
0x180050450  mov     rbx, rcx
0x180050453  mov     [rsp+88h+var_38], 0
0x18005045b  xor     ecx, ecx; lpEventAttributes
0x18005045d  mov     [rsp+88h+var_30], 2Fh ; '/'
0x180050466  xor     r9d, r9d; lpName
0x180050469  mov     [rsp+88h+var_28], 1
0x180050472  xor     r8d, r8d; bInitialState
0x180050475  mov     [rsp+88h+var_20], 2
0x18005047d  xor     edx, edx; bManualReset
0x18005047f  mov     [rsp+88h+var_1C], 1
0x180050487  call    cs:__imp_CreateEventW
0x18005048d  mov     [rbx+200h], rax
0x180050494  test    rax, rax
0x180050497  jnz     short loc_1800504B4
0x180050499  call    cs:__imp_GetLastError
0x18005049f  test    eax, eax
0x1800504a1  jle     loc_180050563
0x1800504a7  movzx   eax, ax
0x1800504aa  or      eax, 80070000h
0x1800504af  jmp     loc_180050563
0x1800504b4  xor     r8d, r8d; pcbe
0x1800504b7  lea     rcx, ?ResourceWaitCallback@CQueryContext@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800504be  mov     rdx, rbx; pv
0x1800504c1  call    cs:__imp_CreateThreadpoolWait
0x1800504c7  mov     [rbx+208h], rax
0x1800504ce  test    rax, rax
0x1800504d1  jz      short loc_180050499
0x1800504d3  xor     r8d, r8d; pcbe
0x1800504d6  lea     rcx, ?ResourceTimerCallback@CQueryContext@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800504dd  mov     rdx, rbx; pv
0x1800504e0  call    cs:__imp_CreateThreadpoolTimer
0x1800504e6  mov     [rbx+210h], rax
0x1800504ed  test    rax, rax
0x1800504f0  jz      short loc_180050499
0x1800504f2  mov     rdx, [rbx+200h]; h
0x1800504f9  xor     r8d, r8d; pftTimeout
0x1800504fc  mov     rcx, [rbx+208h]; pwa
0x180050503  mov     dword ptr [rbx+228h], 1
0x18005050d  call    cs:__imp_SetThreadpoolWait
0x180050513  mov     r9d, [rbx+190h]
0x18005051a  lea     rax, [rbx+218h]
0x180050521  mov     [rsp+88h+var_40], rax
0x180050526  lea     rdx, [rsp+88h+var_30]
0x18005052b  lea     rax, [rsp+88h+var_38]
0x180050530  xor     r8d, r8d
0x180050533  mov     [rsp+88h+var_48], rax
0x180050538  mov     rax, [rbx+200h]
0x18005053f  mov     [rsp+88h+var_50], 2
0x180050547  mov     [rsp+88h+var_58], 0
0x18005054f  lea     ecx, [r8+1]
0x180050553  mov     [rsp+88h+var_60], rax
0x180050558  mov     [rsp+88h+var_68], rbx
0x18005055d  call    cs:__imp_RmAcquireResources
0x180050563  mov     rcx, [rsp+88h+var_18]
0x180050568  xor     rcx, rsp; StackCookie
0x18005056b  call    __security_check_cookie
0x180050570  add     rsp, 80h
0x180050577  pop     rbx
0x180050578  retn
```
