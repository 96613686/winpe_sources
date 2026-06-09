# CRRQueue::OpenRRSession(ulong,ulong,void * *,ulong)

- ea: `0x180043480`
- end: `0x1800435ff`
- name: `?OpenRRSession@CRRQueue@@QEAAJKKPEAPEAXK@Z`
- size: `383`
- prototype: `__int64 __fastcall(CRRQueue *__hidden this, unsigned int, unsigned int, void **, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800202e4`

## callees

- `0x180009c44`
- `0x18000f35c`
- `0x18002c61c`
- `0x180042648`
- `0x180043480`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18004350c`
- `RPCRT4!NdrClientCall3` at `0x18004350c`
- `mqsec!ProduceRPCErrorTracing` at `0x18004353e`
- `mqsec!ProduceRPCErrorTracing` at `0x18004353e`

## string_xrefs

- `0x1800434a5`: `remotereadcli`
- `0x18004351d`: `remotereadcli`
- `0x180043537`: `remotereadcli`
- `0x180043585`: `remotereadcli`
- `0x1800435e5`: `remotereadcli`

## pseudocode

```c
__int64 __fastcall CRRQueue::OpenRRSession(CRRQueue *this, int a2, int a3, void **a4, unsigned int a5)
{
  int v9; // eax
  BOOL v11; // [rsp+30h] [rbp-58h]
  int v12; // [rsp+38h] [rbp-50h]
  int v13; // [rsp+40h] [rbp-48h]
  int Pointer; // [rsp+50h] [rbp-38h]

  v9 = CRRQueue::BindRemoteQMService(this);
  if ( v9 >= 0 )
  {
    v13 = a3;
    v12 = a2;
    v11 = CQueueMgr::m_bMQSRouting;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              2u,
                              0,
                              *((_QWORD *)this + 7),
                              a4,
                              &CQueueMgr::m_guidQmQueue,
                              v11,
                              v12,
                              v13,
                              a5,
                              0).Pointer;
    return LogHR(Pointer, (wchar_t *)L"remotereadcli", 0x450u);
  }
  else
  {
    LogMsgHR(v9, (wchar_t *)L"remotereadcli", 0x78u);
    return 3222142977LL;
  }
}

```

## disassembly

```asm
0x180043480  push    rbx
0x180043482  push    rsi
0x180043483  push    rdi
0x180043484  push    r14
0x180043486  sub     rsp, 68h
0x18004348a  mov     rdi, r9
0x18004348d  mov     esi, r8d
0x180043490  mov     r14d, edx
0x180043493  mov     rbx, rcx
0x180043496  call    ?BindRemoteQMService@CRRQueue@@AEAAJXZ; CRRQueue::BindRemoteQMService(void)
0x18004349b  test    eax, eax
0x18004349d  jns     short loc_1800434BD
0x18004349f  mov     r8d, 78h ; 'x'; unsigned __int16
0x1800434a5  lea     rdx, aRemotereadcli; "remotereadcli"
0x1800434ac  mov     ecx, eax; int
0x1800434ae  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800434b3  mov     eax, 0C00E0001h
0x1800434b8  jmp     loc_1800435F5
0x1800434bd  xor     ecx, ecx
0x1800434bf  cmp     cs:?m_bMQSRouting@CQueueMgr@@0_NA, cl; bool CQueueMgr::m_bMQSRouting
0x1800434c5  setnz   cl
0x1800434c8  mov     qword ptr [rsp+88h+var_38], 0
0x1800434d1  mov     eax, [rsp+88h+arg_20]
0x1800434d8  mov     [rsp+88h+var_40], eax
0x1800434dc  mov     [rsp+88h+var_48], esi
0x1800434e0  mov     [rsp+88h+var_50], r14d
0x1800434e5  mov     [rsp+88h+var_58], ecx
0x1800434e9  lea     rax, ?m_guidQmQueue@CQueueMgr@@0U_GUID@@A; _GUID CQueueMgr::m_guidQmQueue
0x1800434f0  mov     [rsp+88h+var_60], rax
0x1800434f5  mov     [rsp+88h+var_68], rdi
0x1800434fa  mov     r9, [rbx+38h]
0x1800434fe  xor     r8d, r8d; pReturnValue
0x180043501  lea     edx, [r8+2]; nProcNum
0x180043505  lea     rcx, pProxyInfo; pProxyInfo
0x18004350c  call    cs:__imp_NdrClientCall3
0x180043512  mov     qword ptr [rsp+88h+var_38], rax
0x180043517  mov     r8d, 450h; unsigned __int16
0x18004351d  lea     rdx, aRemotereadcli; "remotereadcli"
0x180043524  mov     ecx, eax; int
0x180043526  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18004352b  jmp     loc_1800435F5
0x180043530  mov     ebx, eax
0x180043532  mov     edx, 4EDh
0x180043537  lea     rcx, aRemotereadcli; "remotereadcli"
0x18004353e  call    cs:__imp_?ProduceRPCErrorTracing@@YAXPEA_WK@Z; ProduceRPCErrorTracing(wchar_t *,ulong)
0x180043544  test    ebx, ebx
0x180043546  jns     short loc_180043597
0x180043548  lea     rax, WPP_GLOBAL_Control
0x18004354f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043556  cmp     rcx, rax
0x180043559  jz      short loc_18004357F
0x18004355b  test    byte ptr [rcx+0BCh], 1
0x180043562  jz      short loc_18004357F
0x180043564  mov     edx, 22h ; '"'
0x180043569  mov     r9d, ebx
0x18004356c  lea     r8, WPP_5f2c7350f3303e10dc791a725285f9e5_Traceguids
0x180043573  mov     rcx, [rcx+0B0h]
0x18004357a  call    WPP_SF_d
0x18004357f  mov     r8d, 452h; unsigned __int16
0x180043585  lea     rdx, aRemotereadcli; "remotereadcli"
0x18004358c  mov     ecx, ebx; int
0x18004358e  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180043593  mov     eax, ebx
0x180043595  jmp     short loc_1800435F5
0x180043597  lea     rax, WPP_GLOBAL_Control
0x18004359e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800435a5  cmp     rcx, rax
0x1800435a8  jz      short loc_1800435CE
0x1800435aa  test    byte ptr [rcx+0BCh], 1
0x1800435b1  jz      short loc_1800435CE
0x1800435b3  mov     edx, 23h ; '#'
0x1800435b8  mov     r9d, ebx
0x1800435bb  lea     r8, WPP_5f2c7350f3303e10dc791a725285f9e5_Traceguids
0x1800435c2  mov     rcx, [rcx+0B0h]
0x1800435c9  call    WPP_SF_d
0x1800435ce  test    ebx, ebx
0x1800435d0  jle     short loc_1800435DD
0x1800435d2  movzx   ebx, bx
0x1800435d5  or      ebx, 80070000h
0x1800435db  test    ebx, ebx
0x1800435dd  jns     short loc_1800435F3
0x1800435df  mov     r8d, 453h; unsigned __int16
0x1800435e5  lea     rdx, aRemotereadcli; "remotereadcli"
0x1800435ec  mov     ecx, ebx; int
0x1800435ee  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800435f3  mov     eax, ebx
0x1800435f5  add     rsp, 68h
0x1800435f9  pop     r14
0x1800435fb  pop     rdi
0x1800435fc  pop     rsi
0x1800435fd  pop     rbx
0x1800435fe  retn
0x1800da890  push    rbp
0x1800da892  sub     rsp, 50h
0x1800da896  mov     rbp, rdx
0x1800da899  mov     rcx, [rcx]
0x1800da89c  mov     ecx, [rcx]; ExceptionCode
0x1800da89e  call    cs:__imp_I_RpcExceptionFilter
0x1800da8a4  nop
0x1800da8a5  add     rsp, 50h
0x1800da8a9  pop     rbp
0x1800da8aa  retn
```
