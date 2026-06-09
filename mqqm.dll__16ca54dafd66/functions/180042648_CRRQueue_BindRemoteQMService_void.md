# CRRQueue::BindRemoteQMService(void)

- ea: `0x180042648`
- end: `0x180042855`
- name: `?BindRemoteQMService@CRRQueue@@AEAAJXZ`
- size: `525`
- prototype: `__int64 __fastcall(CRRQueue *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180043480`

## callees

- `0x18000f35c`
- `0x18002c61c`
- `0x180042588`
- `0x180042648`
- `0x180042a00`
- `0x180043608`
- `0x1800439c8`
- `0x180043d90`
- `0x180043de8`
- `0x180043e44`
- `0x180043ee4`

## import_xrefs

- `msvcrt!free` at `0x180042733`
- `msvcrt!free` at `0x180042803`
- `msvcrt!free` at `0x180042839`
- `msvcrt!free` at `0x180042733`
- `msvcrt!free` at `0x180042803`
- `msvcrt!free` at `0x180042839`
- `mqsec!mqrpcBindQMService` at `0x1800426b8`
- `mqsec!mqrpcBindQMService` at `0x1800426b8`

## string_xrefs

- `0x1800426ca`: `remotereadcli`
- `0x180042721`: `remotereadcli`
- `0x1800427f1`: `remotereadcli`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRRQueue::BindRemoteQMService(CRRQueue *this)
{
  CBaseRRQueue *v2; // rcx
  RPC_BINDING_HANDLE *v3; // r14
  void *v4; // rdx
  void *v5; // rdi
  int v6; // eax
  int v7; // esi
  PVOID *v9; // rcx
  unsigned int v10; // [rsp+50h] [rbp+8h] BYREF
  void *Block; // [rsp+58h] [rbp+10h] BYREF

  Block = 0;
  RemoteQueueNameToMachineName(*((_QWORD *)this + 3), &Block);
  v10 = 1;
  v3 = (RPC_BINDING_HANDLE *)((char *)this + 56);
  v4 = (void *)*((_QWORD *)this + 7);
  if ( v4 )
    v10 = CBaseRRQueue::BindInqRpcAuthnLevel(v2, v4);
  v5 = Block;
  if ( !*v3 )
  {
    v6 = mqrpcBindQMService((const wchar_t *)Block, 0x65u, qword_1800E7B60, &v10, (void **)this + 7);
    v7 = v6;
    if ( v6 < 0 )
    {
      LogMsgHR(v6, (wchar_t *)L"remotereadcli", 0x44Du);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 22), v10, v7);
      LogMsgHR(v7, (wchar_t *)L"remotereadcli", 0x154u);
      free(v5);
      return (unsigned int)v7;
    }
  }
  SetBindNonCausal(*v3);
  SetBindTimeout(*v3);
  SetBindKeepAlive(*v3);
  v7 = CBaseRRQueue::CreateBind2(this, (const wchar_t *)v5, &v10, qword_1800E7B60);
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 19, WPP_5f2c7350f3303e10dc791a725285f9e5_Traceguids, v10);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 < 0 )
  {
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 188) & 1) != 0 )
      WPP_SF_Sdd((TRACEHANDLE)v9[22], v10, v7);
    LogMsgHR(v7, (wchar_t *)L"remotereadcli", 0x15Eu);
    free(v5);
    return (unsigned int)v7;
  }
  SetBindNonCausal(*((_QWORD *)this + 8));
  SetBindKeepAlive(*((_QWORD *)this + 8));
  QMpGetRemoteQmVersion(*v3, (char *)this + 80, (char *)this + 81, (char *)this + 104);
  free(v5);
  return 0;
}

```

## disassembly

```asm
0x180042648  mov     rax, rsp
0x18004264b  mov     [rax+18h], rbx
0x18004264f  mov     [rax+20h], rbp
0x180042653  push    rsi
0x180042654  push    rdi
0x180042655  push    r14
0x180042657  sub     rsp, 30h
0x18004265b  mov     rbx, rcx
0x18004265e  mov     qword ptr [rax+10h], 0
0x180042666  lea     rdx, [rax+10h]
0x18004266a  mov     rcx, [rcx+18h]
0x18004266e  call    ?RemoteQueueNameToMachineName@@YAXPEB_WAEAV?$AP@_W@@@Z; RemoteQueueNameToMachineName(wchar_t const *,AP<wchar_t> &)
0x180042673  mov     [rsp+48h+arg_0], 1
0x18004267b  lea     r14, [rbx+38h]
0x18004267f  mov     rdx, [r14]; void *
0x180042682  test    rdx, rdx
0x180042685  jz      short loc_180042690
0x180042687  call    ?BindInqRpcAuthnLevel@CBaseRRQueue@@IEAAKPEAX@Z; CBaseRRQueue::BindInqRpcAuthnLevel(void *)
0x18004268c  mov     [rsp+48h+arg_0], eax
0x180042690  mov     rdi, [rsp+48h+Block]
0x180042695  cmp     qword ptr [r14], 0
0x180042699  jnz     loc_180042741
0x18004269f  mov     qword ptr [rsp+48h+var_28], r14
0x1800426a4  lea     r9, [rsp+48h+arg_0]
0x1800426a9  lea     r8, qword_1800E7B60
0x1800426b0  mov     edx, 65h ; 'e'
0x1800426b5  mov     rcx, rdi
0x1800426b8  call    cs:__imp_?mqrpcBindQMService@@YAJPEB_WKPEAXPEAKPEAPEAX@Z; mqrpcBindQMService(wchar_t const *,ulong,void *,ulong *,void * *)
0x1800426be  mov     esi, eax
0x1800426c0  test    eax, eax
0x1800426c2  jns     short loc_180042741
0x1800426c4  mov     r8d, 44Dh; unsigned __int16
0x1800426ca  lea     rdx, aRemotereadcli; "remotereadcli"
0x1800426d1  mov     ecx, eax; int
0x1800426d3  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800426d8  lea     rbp, WPP_GLOBAL_Control
0x1800426df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800426e6  cmp     rcx, rbp
0x1800426e9  jz      short loc_18004271B
0x1800426eb  test    byte ptr [rcx+0BCh], 1
0x1800426f2  jz      short loc_18004271B
0x1800426f4  mov     edx, 12h
0x1800426f9  mov     dword ptr [rsp+48h+var_20], esi; char
0x1800426fd  mov     eax, [rsp+48h+arg_0]
0x180042701  mov     dword ptr [rsp+48h+var_28], eax; char
0x180042705  mov     r9, rdi
0x180042708  lea     r8, WPP_5f2c7350f3303e10dc791a725285f9e5_Traceguids
0x18004270f  mov     rcx, [rcx+0B0h]; LoggerHandle
0x180042716  call    WPP_SF_Sdd
0x18004271b  mov     r8d, 154h; unsigned __int16
0x180042721  lea     rdx, aRemotereadcli; "remotereadcli"
0x180042728  mov     ecx, esi; int
0x18004272a  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18004272f  nop
0x180042730  mov     rcx, rdi; Block
0x180042733  call    cs:__imp_free
0x180042739  nop
0x18004273a  mov     eax, esi
0x18004273c  jmp     loc_180042842
0x180042741  mov     rcx, [r14]
0x180042744  call    SetBindNonCausal
0x180042749  mov     rcx, [r14]; hBinding
0x18004274c  call    ?SetBindTimeout@@YAXPEAX@Z; SetBindTimeout(void *)
0x180042751  mov     rcx, [r14]
0x180042754  call    SetBindKeepAlive
0x180042759  lea     r9, qword_1800E7B60; void *
0x180042760  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x180042765  mov     rdx, rdi; wchar_t *
0x180042768  mov     rcx, rbx; this
0x18004276b  call    ?CreateBind2@CBaseRRQueue@@IEAAJPEB_WPEAKPEAX@Z; CBaseRRQueue::CreateBind2(wchar_t const *,ulong *,void *)
0x180042770  mov     esi, eax
0x180042772  lea     rbp, WPP_GLOBAL_Control
0x180042779  mov     rcx, cs:WPP_GLOBAL_Control
0x180042780  cmp     rcx, rbp
0x180042783  jz      short loc_1800427B2
0x180042785  test    byte ptr [rcx+0BCh], 4
0x18004278c  jz      short loc_1800427B2
0x18004278e  mov     edx, 13h
0x180042793  mov     r9d, [rsp+48h+arg_0]
0x180042798  lea     r8, WPP_5f2c7350f3303e10dc791a725285f9e5_Traceguids
0x18004279f  mov     rcx, [rcx+0B0h]
0x1800427a6  call    WPP_SF_d
0x1800427ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800427b2  test    esi, esi
0x1800427b4  jns     short loc_18004280F
0x1800427b6  cmp     rcx, rbp
0x1800427b9  jz      short loc_1800427EB
0x1800427bb  test    byte ptr [rcx+0BCh], 1
0x1800427c2  jz      short loc_1800427EB
0x1800427c4  mov     edx, 14h
0x1800427c9  mov     dword ptr [rsp+48h+var_20], esi; char
0x1800427cd  mov     eax, [rsp+48h+arg_0]
0x1800427d1  mov     dword ptr [rsp+48h+var_28], eax; char
0x1800427d5  mov     r9, rdi
0x1800427d8  lea     r8, WPP_5f2c7350f3303e10dc791a725285f9e5_Traceguids
0x1800427df  mov     rcx, [rcx+0B0h]; LoggerHandle
0x1800427e6  call    WPP_SF_Sdd
0x1800427eb  mov     r8d, 15Eh; unsigned __int16
0x1800427f1  lea     rdx, aRemotereadcli; "remotereadcli"
0x1800427f8  mov     ecx, esi; int
0x1800427fa  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800427ff  nop
0x180042800  mov     rcx, rdi; Block
0x180042803  call    cs:__imp_free
0x180042809  nop
0x18004280a  jmp     loc_18004273A
0x18004280f  mov     rcx, [rbx+40h]
0x180042813  call    SetBindNonCausal
0x180042818  mov     rcx, [rbx+40h]
0x18004281c  call    SetBindKeepAlive
0x180042821  lea     r9, [rbx+68h]
0x180042825  lea     r8, [rbx+51h]
0x180042829  lea     rdx, [rbx+50h]
0x18004282d  mov     rcx, [r14]
0x180042830  call    QMpGetRemoteQmVersion
0x180042835  nop
0x180042836  mov     rcx, rdi; Block
0x180042839  call    cs:__imp_free
0x18004283f  nop
0x180042840  xor     eax, eax
0x180042842  mov     rbx, [rsp+48h+arg_10]
0x180042847  mov     rbp, [rsp+48h+arg_18]
0x18004284c  add     rsp, 30h
0x180042850  pop     r14
0x180042852  pop     rdi
0x180042853  pop     rsi
0x180042854  retn
```
