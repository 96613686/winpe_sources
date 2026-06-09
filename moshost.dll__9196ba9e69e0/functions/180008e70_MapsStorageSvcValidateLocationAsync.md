# MapsStorageSvcValidateLocationAsync

- ea: `0x180008e70`
- end: `0x180008eca`
- name: `MapsStorageSvcValidateLocationAsync`
- size: `90`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, __int64, struct _GUID *, struct _STORAGE_DEVICE_VALIDATION_RESULT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008e70`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180008ebe`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180008ebe`
- `MosStorage!MosStorageValidateLocation` at `0x180008e93`
- `MosStorage!MosStorageValidateLocation` at `0x180008e93`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008eac`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008eac`

## pseudocode

```c
RPC_STATUS __fastcall MapsStorageSvcValidateLocationAsync(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        struct _GUID *a3,
        struct _STORAGE_DEVICE_VALIDATION_RESULT *a4)
{
  struct _GUID v4; // xmm0
  int v6; // eax
  struct _GUID v8; // [rsp+20h] [rbp-18h] BYREF
  int Reply; // [rsp+50h] [rbp+18h] BYREF

  v4 = *a3;
  Reply = 0;
  v8 = v4;
  v6 = MosStorageValidateLocation(&v8, a4);
  if ( v6 < 0 )
    Reply = ZTraceReportPropagationNoThis(v6, "MapsStorageSvcValidateLocationAsync", 186);
  return RpcAsyncCompleteCall(pAsync, &Reply);
}

```

## disassembly

```asm
0x180008e70  push    rbx
0x180008e72  sub     rsp, 30h
0x180008e76  movups  xmm0, xmmword ptr [r8]
0x180008e7a  mov     rbx, rcx
0x180008e7d  mov     [rsp+38h+Reply], 0
0x180008e85  mov     rdx, r9
0x180008e88  lea     rcx, [rsp+38h+var_18]
0x180008e8d  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x180008e93  call    cs:__imp_?MosStorageValidateLocation@@YAJU_GUID@@PEAU_STORAGE_DEVICE_VALIDATION_RESULT@@@Z; MosStorageValidateLocation(_GUID,_STORAGE_DEVICE_VALIDATION_RESULT *)
0x180008e99  test    eax, eax
0x180008e9b  jns     short loc_180008EB6
0x180008e9d  mov     r8d, 0BAh
0x180008ea3  lea     rdx, aMapsstoragesvc_2; "MapsStorageSvcValidateLocationAsync"
0x180008eaa  mov     ecx, eax
0x180008eac  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180008eb2  mov     [rsp+38h+Reply], eax
0x180008eb6  lea     rdx, [rsp+38h+Reply]; Reply
0x180008ebb  mov     rcx, rbx; pAsync
0x180008ebe  call    cs:__imp_RpcAsyncCompleteCall
0x180008ec4  add     rsp, 30h
0x180008ec8  pop     rbx
0x180008ec9  retn
```
