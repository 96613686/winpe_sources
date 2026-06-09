# MapsPackageSvcFindNearbyPackagesAsync

- ea: `0x1800090e0`
- end: `0x180009198`
- name: `MapsPackageSvcFindNearbyPackagesAsync`
- size: `184`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800090e0`
- `0x18000d010`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180009185`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180009185`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000913e`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000913e`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000911a`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000911a`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180009173`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180009173`

## pseudocode

```c
RPC_STATUS __fastcall MapsPackageSvcFindNearbyPackagesAsync(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  int v8; // r8d
  int v9; // eax
  int v10; // eax
  _DWORD Reply[10]; // [rsp+30h] [rbp-28h] BYREF

  Reply[0] = 0;
  if ( !a4 )
  {
    v8 = 99;
LABEL_3:
    v9 = ZTraceReportOriginationNoThis(-2147467261, "MapsPackageSvcFindNearbyPackagesAsync", v8);
LABEL_8:
    Reply[0] = v9;
    return RpcAsyncCompleteCall(pAsync, Reply);
  }
  if ( !a5 )
  {
    v8 = 100;
    goto LABEL_3;
  }
  ZTraceHelperNoThis(3, "MapsPackageSvcFindNearbyPackagesAsync", 102, "[MosHost] MapsPackageSvcFindNearbyPackages");
  v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)qword_1800185D0 + 56LL))(
          qword_1800185D0,
          a3,
          a4,
          a5);
  if ( v10 < 0 )
  {
    v9 = ZTraceReportPropagationNoThis(v10, "MapsPackageSvcFindNearbyPackagesAsync", 104);
    goto LABEL_8;
  }
  return RpcAsyncCompleteCall(pAsync, Reply);
}

```

## disassembly

```asm
0x1800090e0  mov     [rsp+arg_8], rbx
0x1800090e5  push    rbp
0x1800090e6  push    rsi
0x1800090e7  push    rdi
0x1800090e8  sub     rsp, 40h
0x1800090ec  mov     rbx, [rsp+58h+arg_20]
0x1800090f4  mov     rdi, r9
0x1800090f7  mov     [rsp+58h+Reply], 0
0x1800090ff  mov     rbp, r8
0x180009102  lea     rdx, aMapspackagesvc_0; "MapsPackageSvcFindNearbyPackagesAsync"
0x180009109  mov     rsi, rcx
0x18000910c  test    r9, r9
0x18000910f  jnz     short loc_180009122
0x180009111  lea     r8d, [r9+63h]
0x180009115  mov     ecx, 80004003h
0x18000911a  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180009120  jmp     short loc_180009179
0x180009122  test    rbx, rbx
0x180009125  jnz     short loc_18000912D
0x180009127  lea     r8d, [rbx+64h]
0x18000912b  jmp     short loc_180009115
0x18000912d  mov     r8d, 66h ; 'f'
0x180009133  lea     r9, aMoshostMapspac_1; "[MosHost] MapsPackageSvcFindNearbyPacka"...
0x18000913a  lea     ecx, [r8-63h]
0x18000913e  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180009144  mov     rcx, cs:qword_1800185D0
0x18000914b  mov     r9, rbx
0x18000914e  mov     r8, rdi
0x180009151  mov     rdx, rbp
0x180009154  mov     rax, [rcx]
0x180009157  mov     rax, [rax+38h]
0x18000915b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009160  test    eax, eax
0x180009162  jns     short loc_18000917D
0x180009164  mov     r8d, 68h ; 'h'
0x18000916a  lea     rdx, aMapspackagesvc_0; "MapsPackageSvcFindNearbyPackagesAsync"
0x180009171  mov     ecx, eax
0x180009173  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180009179  mov     [rsp+58h+Reply], eax
0x18000917d  lea     rdx, [rsp+58h+Reply]; Reply
0x180009182  mov     rcx, rsi; pAsync
0x180009185  call    cs:__imp_RpcAsyncCompleteCall
0x18000918b  mov     rbx, [rsp+58h+arg_8]
0x180009190  add     rsp, 40h
0x180009194  pop     rdi
0x180009195  pop     rsi
0x180009196  pop     rbp
0x180009197  retn
```
