# s_StaPrepareUrlMon(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180159a70`
- end: `0x180159b52`
- name: `?s_StaPrepareUrlMon@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `226`
- prototype: `void __fastcall(_TP_CALLBACK_INSTANCE *Instance, void *Context, _TP_WORK *Work)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180157d70`
- `0x180158920`
- `0x180159a70`
- `0x180185008`
- `0x1801850e0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180159ae0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180159ae0`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180159ab2`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180159ab2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180159af4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180159af4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180159abc`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180159abc`

## pseudocode

```c
void __fastcall s_StaPrepareUrlMon(_TP_CALLBACK_INSTANCE *Instance, StaPrepareContext *Context, _TP_WORK *Work)
{
  HRESULT v6; // edi
  int v7; // ebx
  StaPrepareContext *pStaPrepareContext; // [rsp+38h] [rbp+10h] BYREF

  if ( (xmmword_1801F6C20 & 8) != 0 )
    WPP_SF_q(0x403u, 0x33u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (unsigned __int64)Context);
  pStaPrepareContext = Context;
  CallbackMayRunLong(Instance);
  v6 = CoInitializeEx(0, 0);
  if ( v6 < 0 )
    v7 = v6;
  else
    v7 = _StaPrepareUrlMon(Context->pGIT, Context->dwCookie, Context->pUri);
  CloseThreadpoolWork(Work);
  _DeleteStaPrepareContext(&pStaPrepareContext);
  if ( v6 >= 0 )
    CoUninitialize();
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v7 >> 31) + 4].rgbFlags[0] & 8) != 0 )
    WPP_SF_d((((unsigned __int16)(v7 >> 31) + 2) << 9) | 3, 0x34u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v7);
}

```

## disassembly

```asm
0x180159a70  mov     [rsp+arg_0], rbx
0x180159a75  mov     [rsp+arg_10], rsi
0x180159a7a  push    rdi
0x180159a7b  sub     rsp, 20h
0x180159a7f  mov     rsi, Work
0x180159a82  mov     rbx, Context
0x180159a85  mov     rdi, Instance
0x180159a88  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x180159a8f  jz      short loc_180159AAA
0x180159a91  mov     edx, 33h ; '3'; id
0x180159a96  lea     Work, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180159a9d  mov     ecx, 403h; LevelKeyword
0x180159aa2  mov     r9, rbx; _a1
0x180159aa5  call    WPP_SF_q
0x180159aaa  mov     Instance, rdi; pci
0x180159aad  mov     [rsp+28h+pStaPrepareContext], rbx
0x180159ab2  call    cs:__imp_CallbackMayRunLong
0x180159ab8  xor     edx, edx; dwCoInit
0x180159aba  xor     ecx, ecx; pvReserved
0x180159abc  call    cs:__imp_CoInitializeEx
0x180159ac2  mov     edi, eax
0x180159ac4  test    eax, eax
0x180159ac6  js      short loc_180159ADB
0x180159ac8  mov     Work, [rbx+10h]; pUri
0x180159acc  mov     edx, [rbx+8]; dwCookie
0x180159acf  mov     Instance, [rbx]; pGIT
0x180159ad2  call    ?_StaPrepareUrlMon@@YAJPEAUIGlobalInterfaceTable@@KPEAUIUri@@@Z; _StaPrepareUrlMon(IGlobalInterfaceTable *,ulong,IUri *)
0x180159ad7  mov     ebx, eax
0x180159ad9  jmp     short $CleanUp_552
0x180159adb  mov     ebx, edi
0x180159add  mov     Instance, rsi; pwk
0x180159ae0  call    cs:__imp_CloseThreadpoolWork
0x180159ae6  lea     Instance, [rsp+28h+pStaPrepareContext]; ppPrepareContext
0x180159aeb  call    ?_DeleteStaPrepareContext@@YAXPEAPEAUStaPrepareContext@@@Z; _DeleteStaPrepareContext(StaPrepareContext * *)
0x180159af0  test    edi, edi
0x180159af2  js      short loc_180159AFA
0x180159af4  call    cs:__imp_CoUninitialize
0x180159afa  mov     r9d, ebx; __annotation("TMF:",
0x180159afd  sar     r9d, 1Fh
0x180159b01  lea     eax, ds:4[r9*2]
0x180159b09  movsxd  Instance, eax
0x180159b0c  lea     rax, g_rgFastWppLevelEnabledFlags
0x180159b13  test    byte ptr [rax+Instance*8], 8
0x180159b17  jz      short loc_180159B42
0x180159b19  add     r9w, 2
0x180159b1e  lea     Work, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180159b25  movzx   ecx, r9w
0x180159b29  mov     eax, 200h
0x180159b2e  imul    ecx, eax
0x180159b31  mov     edx, 34h ; '4'; id
0x180159b36  mov     r9d, ebx; _a1
0x180159b39  or      cx, 3; LevelKeyword
0x180159b3d  call    WPP_SF_d
0x180159b42  mov     rbx, [rsp+28h+arg_0]
0x180159b47  mov     rsi, [rsp+28h+arg_10]
0x180159b4c  add     rsp, 20h
0x180159b50  pop     rdi
0x180159b51  retn
```
