# InitializeThreadPoolIo

- ea: `0x180064cf8`
- end: `0x180064e0e`
- name: `InitializeThreadPoolIo`
- size: `278`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800678bc`

## callees

- `0x180064cf8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x180064d34`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x180064d34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180064df1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180064df1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180064d5a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180064d83`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180064d5a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180064d83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064dae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064dd1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064dae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064dd1`

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
0x180064cf8  push    rbx
0x180064cfa  sub     rsp, 20h
0x180064cfe  mov     rbx, rcx
0x180064d01  mov     qword ptr [rcx+130h], 0
0x180064d0c  mov     qword ptr [rcx+160h], 0
0x180064d17  lea     r9, stru_1800CC278; pcbe
0x180064d1e  mov     qword ptr [rcx+60h], 0
0x180064d26  lea     rdx, HttpCompletionDispatch; pfnio
0x180064d2d  mov     rcx, [rcx+48h]; fl
0x180064d31  xor     r8d, r8d; pv
0x180064d34  call    cs:__imp_CreateThreadpoolIo
0x180064d3b  nop     dword ptr [rax+rax+00h]
0x180064d40  mov     [rbx+60h], rax
0x180064d44  test    rax, rax
0x180064d47  jz      short loc_180064DA2
0x180064d49  lea     r8, stru_1800CC278; pcbe
0x180064d50  mov     rdx, rbx; pv
0x180064d53  lea     rcx, NeighborDiscoveryTimer; pfnti
0x180064d5a  call    cs:__imp_CreateThreadpoolTimer
0x180064d61  nop     dword ptr [rax+rax+00h]
0x180064d66  mov     [rbx+130h], rax
0x180064d6d  test    rax, rax
0x180064d70  jz      short loc_180064DA2
0x180064d72  lea     r8, stru_1800CC278; pcbe
0x180064d79  mov     rdx, rbx; pv
0x180064d7c  lea     rcx, IpTlsNeighborDiscoveryRateLimitTimer; pfnti
0x180064d83  call    cs:__imp_CreateThreadpoolTimer
0x180064d8a  nop     dword ptr [rax+rax+00h]
0x180064d8f  mov     [rbx+160h], rax
0x180064d96  test    rax, rax
0x180064d99  jz      short loc_180064DA2
0x180064d9b  mov     eax, 1
0x180064da0  jmp     short loc_180064E07
0x180064da2  mov     rcx, [rbx+160h]; pti
0x180064da9  test    rcx, rcx
0x180064dac  jz      short loc_180064DC5
0x180064dae  call    cs:__imp_CloseThreadpoolTimer
0x180064db5  nop     dword ptr [rax+rax+00h]
0x180064dba  mov     qword ptr [rbx+160h], 0
0x180064dc5  mov     rcx, [rbx+130h]; pti
0x180064dcc  test    rcx, rcx
0x180064dcf  jz      short loc_180064DE8
0x180064dd1  call    cs:__imp_CloseThreadpoolTimer
0x180064dd8  nop     dword ptr [rax+rax+00h]
0x180064ddd  mov     qword ptr [rbx+130h], 0
0x180064de8  mov     rcx, [rbx+60h]; pio
0x180064dec  test    rcx, rcx
0x180064def  jz      short loc_180064E05
0x180064df1  call    cs:__imp_CloseThreadpoolIo
0x180064df8  nop     dword ptr [rax+rax+00h]
0x180064dfd  mov     qword ptr [rbx+60h], 0
0x180064e05  xor     eax, eax
0x180064e07  add     rsp, 20h
0x180064e0b  pop     rbx
0x180064e0c  retn
```
