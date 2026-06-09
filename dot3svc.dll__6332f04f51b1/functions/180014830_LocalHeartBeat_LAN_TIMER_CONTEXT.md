# LocalHeartBeat(_LAN_TIMER_CONTEXT *)

- ea: `0x180014830`
- end: `0x180014921`
- name: `?LocalHeartBeat@@YAXPEAU_LAN_TIMER_CONTEXT@@@Z`
- size: `241`
- prototype: `void __fastcall(struct _LAN_TIMER_CONTEXT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000c230`
- `0x180013c2c`
- `0x180014830`
- `0x180014b7c`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x1800148af`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800148af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014851`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001487f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014851`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001487f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001489c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014908`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001489c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014908`

## pseudocode

```c
void __fastcall LocalHeartBeat(struct _LAN_TIMER_CONTEXT *a1)
{
  struct _RPC_CLIENT_INFO *v1; // rdi
  struct _RPC_CLIENT_INFO *v2; // rbp
  struct _RPC_ASYNC_STATE *v3; // rsi
  __int64 v4; // rdx
  __int64 v5; // r8
  int Reply; // [rsp+48h] [rbp+10h] BYREF

  Reply = 0;
  EnterCriticalSection(&stru_180052F50);
  v1 = qword_180052EE8;
  while ( v1 != (struct _RPC_CLIENT_INFO *)&qword_180052EE8 )
  {
    v2 = v1;
    RefClientInfo(v1);
    EnterCriticalSection((LPCRITICAL_SECTION)v1 + 53);
    v3 = (struct _RPC_ASYNC_STATE *)*((_QWORD *)v1 + 3);
    *((_QWORD *)v1 + 3) = 0;
    *((_QWORD *)v1 + 4) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)v1 + 53);
    if ( v3
      && RpcAsyncCompleteCall(v3, &Reply)
      && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 18, WPP_b4750df92381326559acc6db9e2d425d_Traceguids);
    }
    v1 = *(struct _RPC_CLIENT_INFO **)v1;
    DerefClientInfo(v2, v4, v5);
  }
  LeaveCriticalSection(&stru_180052F50);
}

```

## disassembly

```asm
0x180014830  mov     [rsp+arg_0], rbx
0x180014835  mov     [rsp+arg_10], rbp
0x18001483a  push    rsi
0x18001483b  push    rdi
0x18001483c  push    r15
0x18001483e  sub     rsp, 20h
0x180014842  lea     rcx, stru_180052F50; lpCriticalSection
0x180014849  mov     [rsp+38h+Reply], 0
0x180014851  call    cs:__imp_EnterCriticalSection
0x180014857  mov     rdi, cs:qword_180052EE8
0x18001485e  lea     r15, qword_180052EE8
0x180014865  jmp     loc_1800148F8
0x18001486a  mov     rcx, rdi; struct _RPC_CLIENT_INFO *
0x18001486d  mov     rbp, rdi
0x180014870  call    ?RefClientInfo@@YAKPEAU_RPC_CLIENT_INFO@@@Z; RefClientInfo(_RPC_CLIENT_INFO *)
0x180014875  lea     rbx, [rdi+848h]
0x18001487c  mov     rcx, rbx; lpCriticalSection
0x18001487f  call    cs:__imp_EnterCriticalSection
0x180014885  mov     rsi, [rdi+18h]
0x180014889  mov     rcx, rbx; lpCriticalSection
0x18001488c  mov     qword ptr [rdi+18h], 0
0x180014894  mov     qword ptr [rdi+20h], 0
0x18001489c  call    cs:__imp_LeaveCriticalSection
0x1800148a2  test    rsi, rsi
0x1800148a5  jz      short loc_1800148ED
0x1800148a7  lea     rdx, [rsp+38h+Reply]; Reply
0x1800148ac  mov     rcx, rsi; pAsync
0x1800148af  call    cs:__imp_RpcAsyncCompleteCall
0x1800148b5  test    eax, eax
0x1800148b7  jz      short loc_1800148ED
0x1800148b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800148c0  lea     rax, WPP_GLOBAL_Control
0x1800148c7  cmp     rcx, rax
0x1800148ca  jz      short loc_1800148ED
0x1800148cc  cmp     byte ptr [rcx+19h], 1
0x1800148d0  jb      short loc_1800148ED
0x1800148d2  test    byte ptr [rcx+1Ch], 1
0x1800148d6  jz      short loc_1800148ED
0x1800148d8  mov     rcx, [rcx+10h]
0x1800148dc  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x1800148e3  mov     edx, 12h
0x1800148e8  call    WPP_SF_
0x1800148ed  mov     rdi, [rdi]
0x1800148f0  mov     rcx, rbp; lpMem
0x1800148f3  call    ?DerefClientInfo@@YAKPEAU_RPC_CLIENT_INFO@@@Z; DerefClientInfo(_RPC_CLIENT_INFO *)
0x1800148f8  cmp     rdi, r15
0x1800148fb  jnz     loc_18001486A
0x180014901  lea     rcx, stru_180052F50; lpCriticalSection
0x180014908  call    cs:__imp_LeaveCriticalSection
0x18001490e  mov     rbx, [rsp+38h+arg_0]
0x180014913  mov     rbp, [rsp+38h+arg_10]
0x180014918  add     rsp, 20h
0x18001491c  pop     r15
0x18001491e  pop     rdi
0x18001491f  pop     rsi
0x180014920  retn
```
