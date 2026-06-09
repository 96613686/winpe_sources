# InitializeThreadPoolIo

- ea: `0x180064cd8`
- end: `0x180064dee`
- name: `InitializeThreadPoolIo`
- size: `278`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18006789c`

## callees

- `0x180064cd8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x180064d14`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x180064d14`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180064dd1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180064dd1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180064d3a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180064d63`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180064d3a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180064d63`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064d8e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064db1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064d8e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064db1`

## pseudocode

```c
__int64 __fastcall InitializeThreadPoolIo(PVOID pv)
{
  PTP_IO ThreadpoolIo; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  PTP_TIMER v4; // rax
  struct _TP_TIMER *v6; // rcx
  struct _TP_TIMER *v7; // rcx
  struct _TP_IO *v8; // rcx

  *((_QWORD *)pv + 38) = 0;
  *((_QWORD *)pv + 44) = 0;
  *((_QWORD *)pv + 12) = 0;
  ThreadpoolIo = CreateThreadpoolIo(*((HANDLE *)pv + 9), HttpCompletionDispatch, 0, &stru_1800CC278);
  *((_QWORD *)pv + 12) = ThreadpoolIo;
  if ( ThreadpoolIo )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(NeighborDiscoveryTimer, pv, &stru_1800CC278);
    *((_QWORD *)pv + 38) = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      v4 = CreateThreadpoolTimer(IpTlsNeighborDiscoveryRateLimitTimer, pv, &stru_1800CC278);
      *((_QWORD *)pv + 44) = v4;
      if ( v4 )
        return 1;
    }
  }
  v6 = (struct _TP_TIMER *)*((_QWORD *)pv + 44);
  if ( v6 )
  {
    CloseThreadpoolTimer(v6);
    *((_QWORD *)pv + 44) = 0;
  }
  v7 = (struct _TP_TIMER *)*((_QWORD *)pv + 38);
  if ( v7 )
  {
    CloseThreadpoolTimer(v7);
    *((_QWORD *)pv + 38) = 0;
  }
  v8 = (struct _TP_IO *)*((_QWORD *)pv + 12);
  if ( v8 )
  {
    CloseThreadpoolIo(v8);
    *((_QWORD *)pv + 12) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180064cd8  push    rbx
0x180064cda  sub     rsp, 20h
0x180064cde  mov     rbx, rcx
0x180064ce1  mov     qword ptr [rcx+130h], 0
0x180064cec  mov     qword ptr [rcx+160h], 0
0x180064cf7  lea     r9, stru_1800CC278; pcbe
0x180064cfe  mov     qword ptr [rcx+60h], 0
0x180064d06  lea     rdx, HttpCompletionDispatch; pfnio
0x180064d0d  mov     rcx, [rcx+48h]; fl
0x180064d11  xor     r8d, r8d; pv
0x180064d14  call    cs:__imp_CreateThreadpoolIo
0x180064d1b  nop     dword ptr [rax+rax+00h]
0x180064d20  mov     [rbx+60h], rax
0x180064d24  test    rax, rax
0x180064d27  jz      short loc_180064D82
0x180064d29  lea     r8, stru_1800CC278; pcbe
0x180064d30  mov     rdx, rbx; pv
0x180064d33  lea     rcx, NeighborDiscoveryTimer; pfnti
0x180064d3a  call    cs:__imp_CreateThreadpoolTimer
0x180064d41  nop     dword ptr [rax+rax+00h]
0x180064d46  mov     [rbx+130h], rax
0x180064d4d  test    rax, rax
0x180064d50  jz      short loc_180064D82
0x180064d52  lea     r8, stru_1800CC278; pcbe
0x180064d59  mov     rdx, rbx; pv
0x180064d5c  lea     rcx, IpTlsNeighborDiscoveryRateLimitTimer; pfnti
0x180064d63  call    cs:__imp_CreateThreadpoolTimer
0x180064d6a  nop     dword ptr [rax+rax+00h]
0x180064d6f  mov     [rbx+160h], rax
0x180064d76  test    rax, rax
0x180064d79  jz      short loc_180064D82
0x180064d7b  mov     eax, 1
0x180064d80  jmp     short loc_180064DE7
0x180064d82  mov     rcx, [rbx+160h]; pti
0x180064d89  test    rcx, rcx
0x180064d8c  jz      short loc_180064DA5
0x180064d8e  call    cs:__imp_CloseThreadpoolTimer
0x180064d95  nop     dword ptr [rax+rax+00h]
0x180064d9a  mov     qword ptr [rbx+160h], 0
0x180064da5  mov     rcx, [rbx+130h]; pti
0x180064dac  test    rcx, rcx
0x180064daf  jz      short loc_180064DC8
0x180064db1  call    cs:__imp_CloseThreadpoolTimer
0x180064db8  nop     dword ptr [rax+rax+00h]
0x180064dbd  mov     qword ptr [rbx+130h], 0
0x180064dc8  mov     rcx, [rbx+60h]; pio
0x180064dcc  test    rcx, rcx
0x180064dcf  jz      short loc_180064DE5
0x180064dd1  call    cs:__imp_CloseThreadpoolIo
0x180064dd8  nop     dword ptr [rax+rax+00h]
0x180064ddd  mov     qword ptr [rbx+60h], 0
0x180064de5  xor     eax, eax
0x180064de7  add     rsp, 20h
0x180064deb  pop     rbx
0x180064dec  retn
```
