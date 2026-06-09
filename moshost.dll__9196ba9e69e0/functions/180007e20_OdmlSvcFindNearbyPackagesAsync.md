# OdmlSvcFindNearbyPackagesAsync

- ea: `0x180007e20`
- end: `0x180007eea`
- name: `OdmlSvcFindNearbyPackagesAsync`
- size: `202`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007e20`
- `0x18000d010`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180007ed7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180007ed7`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180007e90`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180007e90`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007e69`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007e69`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007ec5`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007ec5`

## pseudocode

```c
RPC_STATUS __fastcall OdmlSvcFindNearbyPackagesAsync(
        PRPC_ASYNC_STATE pAsync,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  int v8; // r8d
  int v9; // eax
  int v10; // eax
  _DWORD Reply[10]; // [rsp+30h] [rbp-28h] BYREF

  if ( dword_1800185C4 != a2 )
    __int2c();
  Reply[0] = 0;
  if ( !a4 )
  {
    v8 = 199;
LABEL_5:
    v9 = ZTraceReportOriginationNoThis(-2147467261, "OdmlSvcFindNearbyPackagesAsync", v8);
LABEL_10:
    Reply[0] = v9;
    return RpcAsyncCompleteCall(pAsync, Reply);
  }
  if ( !a5 )
  {
    v8 = 200;
    goto LABEL_5;
  }
  ZTraceHelperNoThis(3, "OdmlSvcFindNearbyPackagesAsync", 202, "[MosHost] OdmlSvcFindNearbyPackagesAsync");
  v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)qword_1800185D0 + 56LL))(
          qword_1800185D0,
          a3,
          a4,
          a5);
  if ( v10 < 0 )
  {
    v9 = ZTraceReportPropagationNoThis(v10, "OdmlSvcFindNearbyPackagesAsync", 206);
    goto LABEL_10;
  }
  return RpcAsyncCompleteCall(pAsync, Reply);
}

```

## disassembly

```asm
0x180007e20  mov     [rsp+arg_8], rbx
0x180007e25  push    rbp
0x180007e26  push    rsi
0x180007e27  push    rdi
0x180007e28  sub     rsp, 40h
0x180007e2c  mov     eax, cs:dword_1800185C4
0x180007e32  mov     rbx, r9
0x180007e35  mov     rdi, [rsp+58h+arg_20]
0x180007e3d  mov     rbp, r8
0x180007e40  mov     rsi, rcx
0x180007e43  nop
0x180007e44  cmp     eax, edx
0x180007e46  jz      short loc_180007E4A
0x180007e48  int     2Ch; Windows NT - assertion failure
0x180007e4a  mov     [rsp+58h+Reply], 0
0x180007e52  lea     rdx, aOdmlsvcfindnea; "OdmlSvcFindNearbyPackagesAsync"
0x180007e59  test    rbx, rbx
0x180007e5c  jnz     short loc_180007E71
0x180007e5e  mov     r8d, 0C7h
0x180007e64  mov     ecx, 80004003h
0x180007e69  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180007e6f  jmp     short loc_180007ECB
0x180007e71  test    rdi, rdi
0x180007e74  jnz     short loc_180007E7E
0x180007e76  mov     r8d, 0C8h
0x180007e7c  jmp     short loc_180007E64
0x180007e7e  lea     r9, aMoshostOdmlsvc_10; "[MosHost] OdmlSvcFindNearbyPackagesAsyn"...
0x180007e85  mov     r8d, 0CAh
0x180007e8b  mov     ecx, 3
0x180007e90  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180007e96  mov     rcx, cs:qword_1800185D0
0x180007e9d  mov     r9, rdi
0x180007ea0  mov     r8, rbx
0x180007ea3  mov     rdx, rbp
0x180007ea6  mov     rax, [rcx]
0x180007ea9  mov     rax, [rax+38h]
0x180007ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eb2  test    eax, eax
0x180007eb4  jns     short loc_180007ECF
0x180007eb6  mov     r8d, 0CEh
0x180007ebc  lea     rdx, aOdmlsvcfindnea; "OdmlSvcFindNearbyPackagesAsync"
0x180007ec3  mov     ecx, eax
0x180007ec5  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180007ecb  mov     [rsp+58h+Reply], eax
0x180007ecf  lea     rdx, [rsp+58h+Reply]; Reply
0x180007ed4  mov     rcx, rsi; pAsync
0x180007ed7  call    cs:__imp_RpcAsyncCompleteCall
0x180007edd  mov     rbx, [rsp+58h+arg_8]
0x180007ee2  add     rsp, 40h
0x180007ee6  pop     rdi
0x180007ee7  pop     rsi
0x180007ee8  pop     rbp
0x180007ee9  retn
```
