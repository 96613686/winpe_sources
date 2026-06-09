# MapsPackageSvcAddMapPackageAsync

- ea: `0x180008f90`
- end: `0x18000906a`
- name: `MapsPackageSvcAddMapPackageAsync`
- size: `218`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008f90`
- `0x18000a480`
- `0x18000d010`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180009054`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180009054`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180008fcd`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180008fcd`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180009001`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180009001`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180009042`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180009042`
- `api-ms-win-security-capability-l1-1-0!RpcClientCapabilityCheck` at `0x180008fda`
- `api-ms-win-security-capability-l1-1-0!RpcClientCapabilityCheck` at `0x180008fda`

## pseudocode

```c
RPC_STATUS __fastcall MapsPackageSvcAddMapPackageAsync(PRPC_ASYNC_STATE pAsync, __int64 a2, unsigned int a3)
{
  unsigned int ClientProcessId; // esi
  int v6; // eax
  int v7; // ecx
  int v8; // r8d
  int v9; // eax
  int v10; // eax
  int Reply; // [rsp+48h] [rbp+20h] BYREF

  Reply = 0;
  ClientProcessId = GetClientProcessId();
  ZTraceHelperNoThis(3, "MapsPackageSvcAddMapPackageAsync", 137, "[MosHost] MapsPackageSvcAddMapPackageAsync");
  v6 = RpcClientCapabilityCheck(L"offlineMapsManagement");
  Reply = v6;
  if ( v6 == -2147024891 )
  {
    v7 = -2080374755;
    v8 = 143;
    Reply = -2080374755;
LABEL_3:
    v9 = ZTraceReportOriginationNoThis(v7, "MapsPackageSvcAddMapPackageAsync", v8);
LABEL_8:
    Reply = v9;
    return RpcAsyncCompleteCall(pAsync, &Reply);
  }
  if ( v6 < 0 )
  {
    v8 = 145;
    v7 = v6;
    goto LABEL_3;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)qword_1800185D0 + 72LL))(
          qword_1800185D0,
          a3,
          ClientProcessId);
  if ( v10 < 0 )
  {
    v9 = ZTraceReportPropagationNoThis(v10, "MapsPackageSvcAddMapPackageAsync", 147);
    goto LABEL_8;
  }
  return RpcAsyncCompleteCall(pAsync, &Reply);
}

```

## disassembly

```asm
0x180008f90  mov     [rsp+arg_0], rbx
0x180008f95  mov     [rsp+arg_8], rsi
0x180008f9a  push    rdi
0x180008f9b  sub     rsp, 20h
0x180008f9f  mov     edi, r8d
0x180008fa2  mov     [rsp+28h+Reply], 0
0x180008faa  mov     rbx, rcx
0x180008fad  call    ?GetClientProcessId@@YAKXZ; GetClientProcessId(void)
0x180008fb2  lea     r9, aMoshostMapspac; "[MosHost] MapsPackageSvcAddMapPackageAs"...
0x180008fb9  mov     r8d, 89h
0x180008fbf  lea     rdx, aMapspackagesvc_2; "MapsPackageSvcAddMapPackageAsync"
0x180008fc6  mov     ecx, 3
0x180008fcb  mov     esi, eax
0x180008fcd  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180008fd3  lea     rcx, aOfflinemapsman; "offlineMapsManagement"
0x180008fda  call    cs:__imp_RpcClientCapabilityCheck
0x180008fe0  mov     [rsp+28h+Reply], eax
0x180008fe4  cmp     eax, 80070005h
0x180008fe9  jnz     short loc_180009009
0x180008feb  mov     ecx, 8400001Dh
0x180008ff0  mov     r8d, 8Fh
0x180008ff6  mov     [rsp+28h+Reply], ecx
0x180008ffa  lea     rdx, aMapspackagesvc_2; "MapsPackageSvcAddMapPackageAsync"
0x180009001  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180009007  jmp     short loc_180009048
0x180009009  test    eax, eax
0x18000900b  jns     short loc_180009017
0x18000900d  mov     r8d, 91h
0x180009013  mov     ecx, eax
0x180009015  jmp     short loc_180008FFA
0x180009017  mov     rcx, cs:qword_1800185D0
0x18000901e  mov     r8d, esi
0x180009021  mov     edx, edi
0x180009023  mov     rax, [rcx]
0x180009026  mov     rax, [rax+48h]
0x18000902a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000902f  test    eax, eax
0x180009031  jns     short loc_18000904C
0x180009033  mov     r8d, 93h
0x180009039  lea     rdx, aMapspackagesvc_2; "MapsPackageSvcAddMapPackageAsync"
0x180009040  mov     ecx, eax
0x180009042  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180009048  mov     [rsp+28h+Reply], eax
0x18000904c  lea     rdx, [rsp+28h+Reply]; Reply
0x180009051  mov     rcx, rbx; pAsync
0x180009054  call    cs:__imp_RpcAsyncCompleteCall
0x18000905a  mov     rbx, [rsp+28h+arg_0]
0x18000905f  mov     rsi, [rsp+28h+arg_8]
0x180009064  add     rsp, 20h
0x180009068  pop     rdi
0x180009069  retn
```
