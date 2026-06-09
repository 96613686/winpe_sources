# OpenRemoteExtObjectLibrary

- ea: `0x18001403c`
- end: `0x1800141da`
- name: `OpenRemoteExtObjectLibrary`
- size: `414`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800136b0`

## callees

- `0x18000b6d4`
- `0x18000c424`
- `0x180013274`
- `0x180013520`
- `0x18001403c`

## import_xrefs

- `ntdll!RtlRunOnceComplete` at `0x1800140bc`
- `ntdll!RtlRunOnceComplete` at `0x1800140bc`
- `ntdll!RtlRunOnceBeginInitialize` at `0x180014066`
- `ntdll!RtlRunOnceBeginInitialize` at `0x1800140e0`
- `ntdll!RtlRunOnceBeginInitialize` at `0x180014066`
- `ntdll!RtlRunOnceBeginInitialize` at `0x1800140e0`
- `RPCRT4!NdrClientCall3` at `0x180014181`
- `RPCRT4!NdrClientCall3` at `0x180014181`

## pseudocode

```c
__int64 __fastcall OpenRemoteExtObjectLibrary(__int64 a1)
{
  int v2; // eax
  __int64 result; // rax
  PVOID v4; // rdi
  unsigned int v5; // esi
  int v6; // eax
  _QWORD *started; // rsi
  unsigned int Pointer; // edi
  _QWORD v9[3]; // [rsp+30h] [rbp-30h] BYREF
  int v10; // [rsp+48h] [rbp-18h]
  int v11; // [rsp+4Ch] [rbp-14h]
  __int64 v12; // [rsp+50h] [rbp-10h]
  PVOID v13; // [rsp+88h] [rbp+28h] BYREF
  void *v14; // [rsp+90h] [rbp+30h]

  v14 = 0;
  v2 = RtlRunOnceBeginInitialize(&stru_18002BEC0, 2);
  if ( v2 < 0 )
    return 13;
  if ( v2 == 259 )
  {
    v13 = 0;
    v5 = CreateRpcBinding(&v13);
    if ( v5 || (v4 = v13) == 0 )
    {
      tlx::unique_any<tlx::handle_traits<void *,long (void *),&long MyRpcBindingFree(void *),0>>::~unique_any<tlx::handle_traits<void *,long (void *),&long MyRpcBindingFree(void *),0>>(&v13);
      return v5;
    }
    if ( (RtlRunOnceComplete(&stru_18002BEC0, 2u, v13) & 0x80000000) != 0 )
    {
      v6 = RtlRunOnceBeginInitialize(&stru_18002BEC0, 1);
      if ( v6 < 0 || v6 == 259 )
      {
        tlx::unique_any<tlx::handle_traits<void *,long (void *),&long MyRpcBindingFree(void *),0>>::~unique_any<tlx::handle_traits<void *,long (void *),&long MyRpcBindingFree(void *),0>>(&v13);
        return 6;
      }
      v4 = v14;
    }
    else
    {
      v13 = 0;
    }
    tlx::unique_any<tlx::handle_traits<void *,long (void *),&long MyRpcBindingFree(void *),0>>::~unique_any<tlx::handle_traits<void *,long (void *),&long MyRpcBindingFree(void *),0>>(&v13);
  }
  else
  {
    v4 = v14;
  }
  if ( !v4 )
    return 6;
  if ( (lPerflibConfigFlags & 4) != 0 || (*(_BYTE *)(a1 + 380) & 0x20) != 0 )
  {
    started = 0;
  }
  else
  {
    v9[1] = *(_QWORD *)(a1 + 96);
    v9[2] = *(_QWORD *)(a1 + 392);
    v10 = *(_DWORD *)(a1 + 60);
    v9[0] = 0;
    v11 = 2002;
    v12 = a1;
    started = StartPerflibFunctionTimer((struct OPEN_PROC_WAIT_INFO *)v9);
  }
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&PerfHost_ProxyInfo,
                            0,
                            0,
                            v4,
                            a1 + 88,
                            *(_QWORD *)(a1 + 392)).Pointer;
  if ( started )
    KillPerflibFunctionTimer(started);
  if ( Pointer )
    return Pointer;
  *(_BYTE *)(a1 + 80) = 1;
  result = 0;
  *(_QWORD *)(a1 + 40) = 1;
  return result;
}

```

## disassembly

```asm
0x18001403c  mov     [rsp-18h+arg_0], rbx
0x180014041  push    rbp
0x180014042  push    rsi
0x180014043  push    rdi
0x180014044  mov     rbp, rsp
0x180014047  sub     rsp, 60h
0x18001404b  mov     rbx, rcx
0x18001404e  mov     [rbp+arg_10], 0
0x180014056  lea     rcx, stru_18002BEC0
0x18001405d  mov     edx, 2
0x180014062  lea     r8, [rbp+arg_10]
0x180014066  call    cs:__imp_RtlRunOnceBeginInitialize
0x18001406c  test    eax, eax
0x18001406e  jns     short loc_18001407A
0x180014070  mov     eax, 0Dh
0x180014075  jmp     loc_1800141CA
0x18001407a  cmp     eax, 103h
0x18001407f  jz      short loc_180014087
0x180014081  mov     rdi, [rbp+arg_10]
0x180014085  jmp     short loc_180014106
0x180014087  lea     rcx, [rbp+arg_8]
0x18001408b  mov     [rbp+arg_8], 0
0x180014093  call    CreateRpcBinding
0x180014098  mov     esi, eax
0x18001409a  test    eax, eax
0x18001409c  jnz     loc_1800141BF
0x1800140a2  mov     rdi, [rbp+arg_8]
0x1800140a6  test    rdi, rdi
0x1800140a9  jz      loc_1800141BF
0x1800140af  mov     r8, rdi; PVOID
0x1800140b2  lea     edx, [rax+2]; DWORD
0x1800140b5  lea     rcx, stru_18002BEC0; PRTL_RUN_ONCE
0x1800140bc  call    cs:__imp_RtlRunOnceComplete
0x1800140c2  test    eax, eax
0x1800140c4  js      short loc_1800140D0
0x1800140c6  mov     [rbp+arg_8], 0
0x1800140ce  jmp     short loc_1800140FD
0x1800140d0  lea     r8, [rbp+arg_10]
0x1800140d4  mov     edx, 1
0x1800140d9  lea     rcx, stru_18002BEC0
0x1800140e0  call    cs:__imp_RtlRunOnceBeginInitialize
0x1800140e6  test    eax, eax
0x1800140e8  js      loc_1800141AF
0x1800140ee  cmp     eax, 103h
0x1800140f3  jz      loc_1800141AF
0x1800140f9  mov     rdi, [rbp+arg_10]
0x1800140fd  lea     rcx, [rbp+arg_8]
0x180014101  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AJPEAX@Z$1?MyRpcBindingFree@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,long (void *),&MyRpcBindingFree(void *),0>>::~unique_any<tlx::handle_traits<void *,long (void *),&MyRpcBindingFree(void *),0>>(void)
0x180014106  test    rdi, rdi
0x180014109  jz      loc_1800141B8
0x18001410f  test    byte ptr cs:?lPerflibConfigFlags@@3JA, 4; long lPerflibConfigFlags
0x180014116  jnz     short loc_18001415B
0x180014118  test    byte ptr [rbx+17Ch], 20h
0x18001411f  jnz     short loc_18001415B
0x180014121  mov     rax, [rbx+60h]
0x180014125  lea     rcx, [rbp+var_30]; struct OPEN_PROC_WAIT_INFO *
0x180014129  mov     [rbp+var_28], rax
0x18001412d  mov     rax, [rbx+188h]
0x180014134  mov     [rbp+var_20], rax
0x180014138  mov     eax, [rbx+3Ch]
0x18001413b  mov     [rbp+var_18], eax
0x18001413e  mov     [rbp+var_30], 0
0x180014146  mov     [rbp+var_14], 7D2h
0x18001414d  mov     [rbp+var_10], rbx
0x180014151  call    ?StartPerflibFunctionTimer@@YAPEAXPEAUOPEN_PROC_WAIT_INFO@@@Z; StartPerflibFunctionTimer(OPEN_PROC_WAIT_INFO *)
0x180014156  mov     rsi, rax
0x180014159  jmp     short loc_18001415D
0x18001415b  xor     esi, esi
0x18001415d  mov     rax, [rbx+188h]
0x180014164  lea     rcx, [rbx+58h]
0x180014168  mov     [rsp+60h+var_38], rax
0x18001416d  mov     r9, rdi
0x180014170  mov     [rsp+60h+var_40], rcx
0x180014175  xor     r8d, r8d; pReturnValue
0x180014178  lea     rcx, ?PerfHost_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001417f  xor     edx, edx; nProcNum
0x180014181  call    cs:__imp_NdrClientCall3
0x180014187  mov     rdi, rax
0x18001418a  test    rsi, rsi
0x18001418d  jz      short loc_180014197
0x18001418f  mov     rcx, rsi; Block
0x180014192  call    ?KillPerflibFunctionTimer@@YAKPEAX@Z; KillPerflibFunctionTimer(void *)
0x180014197  test    edi, edi
0x180014199  jz      short loc_18001419F
0x18001419b  mov     eax, edi
0x18001419d  jmp     short loc_1800141CA
0x18001419f  mov     byte ptr [rbx+50h], 1
0x1800141a3  xor     eax, eax
0x1800141a5  mov     qword ptr [rbx+28h], 1
0x1800141ad  jmp     short loc_1800141CA
0x1800141af  lea     rcx, [rbp+arg_8]
0x1800141b3  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AJPEAX@Z$1?MyRpcBindingFree@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,long (void *),&MyRpcBindingFree(void *),0>>::~unique_any<tlx::handle_traits<void *,long (void *),&MyRpcBindingFree(void *),0>>(void)
0x1800141b8  mov     eax, 6
0x1800141bd  jmp     short loc_1800141CA
0x1800141bf  lea     rcx, [rbp+arg_8]
0x1800141c3  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AJPEAX@Z$1?MyRpcBindingFree@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,long (void *),&MyRpcBindingFree(void *),0>>::~unique_any<tlx::handle_traits<void *,long (void *),&MyRpcBindingFree(void *),0>>(void)
0x1800141c8  mov     eax, esi
0x1800141ca  mov     rbx, [rsp+60h+arg_0]
0x1800141d2  add     rsp, 60h
0x1800141d6  pop     rdi
0x1800141d7  pop     rsi
0x1800141d8  pop     rbp
0x1800141d9  retn
```
