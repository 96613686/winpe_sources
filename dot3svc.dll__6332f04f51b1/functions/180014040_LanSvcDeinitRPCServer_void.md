# LanSvcDeinitRPCServer(void)

- ea: `0x180014040`
- end: `0x1800140f7`
- name: `?LanSvcDeinitRPCServer@@YAKXZ`
- size: `183`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000b9fc`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x180014040`
- `0x18001ee30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800140af`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800140af`
- `MobileNetworking!RaFreeSidList` at `0x1800140a2`
- `MobileNetworking!RaFreeSidList` at `0x1800140a2`

## pseudocode

```c
__int64 LanSvcDeinitRPCServer(void)
{
  struct _LIST_ENTRY *v0; // rcx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 28, WPP_b4750df92381326559acc6db9e2d425d_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  if ( g_RpcServerContext )
  {
    if ( Timer )
      TmDeleteTimer(Timer);
    RaFreeSidList(qword_180052F20);
    DeleteCriticalSection(&stru_180052F50);
    v0 = WPP_GLOBAL_Control;
    g_RpcServerContext = 0;
  }
  if ( v0 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v0[1].Blink) >= 4u && (BYTE4(v0[1].Blink) & 1) != 0 )
    WPP_SF_d(v0[1].Flink, 29, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180014040  push    rbx
0x180014042  sub     rsp, 20h
0x180014046  mov     rcx, cs:WPP_GLOBAL_Control
0x18001404d  lea     rbx, WPP_GLOBAL_Control
0x180014054  cmp     rcx, rbx
0x180014057  jz      short loc_180014081
0x180014059  cmp     byte ptr [rcx+19h], 4
0x18001405d  jb      short loc_180014081
0x18001405f  test    byte ptr [rcx+1Ch], 1
0x180014063  jz      short loc_180014081
0x180014065  mov     rcx, [rcx+10h]
0x180014069  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180014070  mov     edx, 1Ch
0x180014075  call    WPP_SF_
0x18001407a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014081  cmp     cs:?g_RpcServerContext@@3U_RPC_SERVER_CONTEXT@@A, 0; _RPC_SERVER_CONTEXT g_RpcServerContext
0x180014088  jz      short loc_1800140C6
0x18001408a  mov     rcx, cs:Timer; Timer
0x180014091  test    rcx, rcx
0x180014094  jz      short loc_18001409B
0x180014096  call    ?TmDeleteTimer@@YAKPEAX@Z; TmDeleteTimer(void *)
0x18001409b  lea     rcx, qword_180052F20
0x1800140a2  call    cs:__imp_RaFreeSidList
0x1800140a8  lea     rcx, stru_180052F50; lpCriticalSection
0x1800140af  call    cs:__imp_DeleteCriticalSection
0x1800140b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140bc  mov     cs:?g_RpcServerContext@@3U_RPC_SERVER_CONTEXT@@A, 0; _RPC_SERVER_CONTEXT g_RpcServerContext
0x1800140c6  cmp     rcx, rbx
0x1800140c9  jz      short loc_1800140EF
0x1800140cb  cmp     byte ptr [rcx+19h], 4
0x1800140cf  jb      short loc_1800140EF
0x1800140d1  test    byte ptr [rcx+1Ch], 1
0x1800140d5  jz      short loc_1800140EF
0x1800140d7  mov     rcx, [rcx+10h]
0x1800140db  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x1800140e2  mov     edx, 1Dh
0x1800140e7  xor     r9d, r9d
0x1800140ea  call    WPP_SF_d
0x1800140ef  xor     eax, eax
0x1800140f1  add     rsp, 20h
0x1800140f5  pop     rbx
0x1800140f6  retn
```
