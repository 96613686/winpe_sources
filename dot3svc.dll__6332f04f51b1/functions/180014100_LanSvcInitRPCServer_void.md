# LanSvcInitRPCServer(void)

- ea: `0x180014100`
- end: `0x1800142ee`
- name: `?LanSvcInitRPCServer@@YAKXZ`
- size: `494`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18000aac0`

## callees

- `0x180003114`
- `0x18000a9c0`
- `0x18000c230`
- `0x180014100`
- `0x18001ec18`
- `0x18001ee30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180014201`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180014201`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001428d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001428d`
- `MobileNetworking!RaInitSidList` at `0x1800141b0`
- `MobileNetworking!RaInitSidList` at `0x1800141b0`
- `MobileNetworking!RaFreeSidList` at `0x18001429a`
- `MobileNetworking!RaFreeSidList` at `0x18001429a`

## pseudocode

```c
__int64 LanSvcInitRPCServer(void)
{
  unsigned int Timer; // ebx
  struct _LIST_ENTRY *v1; // rcx
  unsigned int inited; // eax

  Timer = 0;
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 24, WPP_b4750df92381326559acc6db9e2d425d_Traceguids);
    v1 = WPP_GLOBAL_Control;
  }
  if ( !g_bRpcServerStarted )
  {
    memset_0(&g_RpcServerContext, 0, 0x98u);
    dword_180052F00 = 2;
    qword_180052F08 = (__int64)LocalHeartBeat;
    qword_180052F10 = 0;
    Timer = TmCreateTimer(&dword_180052F00, 0x2710u, 0x2710u, &::Timer);
    if ( Timer )
    {
LABEL_13:
      v1 = WPP_GLOBAL_Control;
      goto LABEL_14;
    }
    inited = RaInitSidList(qword_180052F20);
    Timer = inited;
    if ( !inited )
    {
      InitializeCriticalSection(&stru_180052F50);
      qword_180052EF0 = (__int64)&qword_180052EE8;
      qword_180052EE8 = (struct _RPC_CLIENT_INFO *)&qword_180052EE8;
      g_RpcServerContext = 1;
      goto LABEL_13;
    }
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 25, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, inited);
      goto LABEL_13;
    }
  }
LABEL_14:
  if ( Timer )
  {
    if ( g_RpcServerContext )
      DeleteCriticalSection(&stru_180052F50);
    RaFreeSidList(qword_180052F20);
    if ( ::Timer )
      TmDeleteTimer(::Timer);
    v1 = WPP_GLOBAL_Control;
  }
  if ( v1 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v1[1].Blink) >= 4u && (BYTE4(v1[1].Blink) & 1) != 0 )
    WPP_SF_d(v1[1].Flink, 27, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, Timer);
  return Timer;
}

```

## disassembly

```asm
0x180014100  mov     [rsp+arg_0], rbx
0x180014105  push    rdi
0x180014106  sub     rsp, 20h
0x18001410a  xor     ebx, ebx
0x18001410c  lea     rdi, WPP_GLOBAL_Control
0x180014113  mov     rcx, cs:WPP_GLOBAL_Control
0x18001411a  cmp     rcx, rdi
0x18001411d  jz      short loc_180014145
0x18001411f  cmp     byte ptr [rcx+19h], 4
0x180014123  jb      short loc_180014145
0x180014125  test    byte ptr [rcx+1Ch], 1
0x180014129  jz      short loc_180014145
0x18001412b  lea     edx, [rbx+18h]
0x18001412e  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180014135  mov     rcx, [rcx+10h]
0x180014139  call    WPP_SF_
0x18001413e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014145  cmp     cs:?g_bRpcServerStarted@@3EA, bl; uchar g_bRpcServerStarted
0x18001414b  jnz     loc_180014279
0x180014151  xor     edx, edx; Val
0x180014153  mov     r8d, 98h; Size
0x180014159  lea     rcx, ?g_RpcServerContext@@3U_RPC_SERVER_CONTEXT@@A; void *
0x180014160  call    memset_0
0x180014165  mov     cs:dword_180052F00, 2
0x18001416f  lea     rax, ?LocalHeartBeat@@YAXPEAU_LAN_TIMER_CONTEXT@@@Z; LocalHeartBeat(_LAN_TIMER_CONTEXT *)
0x180014176  mov     cs:qword_180052F08, rax
0x18001417d  mov     cs:qword_180052F10, rbx
0x180014184  lea     r9, Timer; phNewTimer
0x18001418b  mov     edx, 2710h; DueTime
0x180014190  mov     r8d, edx; Period
0x180014193  lea     rcx, dword_180052F00; Parameter
0x18001419a  call    ?TmCreateTimer@@YAKPEAU_LAN_TIMER_CONTEXT@@KKPEAPEAX@Z; TmCreateTimer(_LAN_TIMER_CONTEXT *,ulong,ulong,void * *)
0x18001419f  mov     ebx, eax
0x1800141a1  test    eax, eax
0x1800141a3  jnz     loc_180014272
0x1800141a9  lea     rcx, qword_180052F20
0x1800141b0  call    cs:__imp_RaInitSidList
0x1800141b6  mov     ebx, eax
0x1800141b8  test    eax, eax
0x1800141ba  jz      short loc_1800141FA
0x1800141bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141c3  cmp     rcx, rdi
0x1800141c6  jz      loc_180014279
0x1800141cc  cmp     byte ptr [rcx+19h], 1
0x1800141d0  jb      loc_180014279
0x1800141d6  test    byte ptr [rcx+1Ch], 1
0x1800141da  jz      loc_180014279
0x1800141e0  mov     edx, 19h
0x1800141e5  mov     r9d, eax
0x1800141e8  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x1800141ef  mov     rcx, [rcx+10h]
0x1800141f3  call    WPP_SF_d
0x1800141f8  jmp     short loc_180014272
0x1800141fa  lea     rcx, stru_180052F50; lpCriticalSection
0x180014201  call    cs:__imp_InitializeCriticalSection
0x180014207  nop
0x180014208  lea     rax, qword_180052EE8
0x18001420f  mov     cs:qword_180052EF0, rax
0x180014216  mov     cs:qword_180052EE8, rax
0x18001421d  mov     cs:?g_RpcServerContext@@3U_RPC_SERVER_CONTEXT@@A, 1; _RPC_SERVER_CONTEXT g_RpcServerContext
0x180014227  jmp     short loc_180014272
0x180014229  mov     ebx, eax
0x18001422b  lea     rax, WPP_GLOBAL_Control
0x180014232  mov     rcx, cs:WPP_GLOBAL_Control
0x180014239  cmp     rcx, rax
0x18001423c  jz      short loc_180014269
0x18001423e  cmp     byte ptr [rcx+19h], 1
0x180014242  jb      short loc_180014269
0x180014244  test    byte ptr [rcx+1Ch], 1
0x180014248  jz      short loc_180014269
0x18001424a  mov     edx, 1Ah
0x18001424f  mov     r9d, ebx
0x180014252  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180014259  mov     rcx, [rcx+10h]
0x18001425d  call    WPP_SF_d
0x180014262  mov     rcx, cs:WPP_GLOBAL_Control
0x180014269  lea     rdi, WPP_GLOBAL_Control
0x180014270  jmp     short loc_180014279
0x180014272  mov     rcx, cs:WPP_GLOBAL_Control
0x180014279  test    ebx, ebx
0x18001427b  jz      short loc_1800142B8
0x18001427d  cmp     cs:?g_RpcServerContext@@3U_RPC_SERVER_CONTEXT@@A, 0; _RPC_SERVER_CONTEXT g_RpcServerContext
0x180014284  jz      short loc_180014293
0x180014286  lea     rcx, stru_180052F50; lpCriticalSection
0x18001428d  call    cs:__imp_DeleteCriticalSection
0x180014293  lea     rcx, qword_180052F20
0x18001429a  call    cs:__imp_RaFreeSidList
0x1800142a0  mov     rcx, cs:Timer; Timer
0x1800142a7  test    rcx, rcx
0x1800142aa  jz      short loc_1800142B1
0x1800142ac  call    ?TmDeleteTimer@@YAKPEAX@Z; TmDeleteTimer(void *)
0x1800142b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142b8  cmp     rcx, rdi
0x1800142bb  jz      short loc_1800142E1
0x1800142bd  cmp     byte ptr [rcx+19h], 4
0x1800142c1  jb      short loc_1800142E1
0x1800142c3  test    byte ptr [rcx+1Ch], 1
0x1800142c7  jz      short loc_1800142E1
0x1800142c9  mov     edx, 1Bh
0x1800142ce  mov     r9d, ebx
0x1800142d1  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x1800142d8  mov     rcx, [rcx+10h]
0x1800142dc  call    WPP_SF_d
0x1800142e1  mov     eax, ebx
0x1800142e3  mov     rbx, [rsp+28h+arg_0]
0x1800142e8  add     rsp, 20h
0x1800142ec  pop     rdi
0x1800142ed  retn
```
