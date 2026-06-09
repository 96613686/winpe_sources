# s_StaPrepareUrlMon(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x10139f50`
- end: `0x10139ff1`
- name: `?s_StaPrepareUrlMon@@YGXPAU_TP_CALLBACK_INSTANCE@@PAXPAU_TP_WORK@@@Z`
- size: `161`
- prototype: `void __stdcall(struct _TP_CALLBACK_INSTANCE *Instance, void *Context, _TP_WORK *Work)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1013749d`
- `0x1013887c`
- `0x10139f50`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x10139fa8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x10139fa8`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x10139f7e`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x10139f7e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x10139fba`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x10139fba`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x10139f88`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x10139f88`

## pseudocode

```c
void __stdcall s_StaPrepareUrlMon(struct _TP_CALLBACK_INSTANCE *Instance, StaPrepareContext *Context, _TP_WORK *Work)
{
  HRESULT v3; // edi
  int v4; // ebx
  StaPrepareContext *pStaPrepareContext; // [esp+Ch] [ebp-4h] BYREF

  if ( (byte_10185760[0] & 8) != 0 )
    WPP_SF_q(0x403u, 0x33u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (int)Context);
  pStaPrepareContext = Context;
  CallbackMayRunLong(Instance);
  v3 = CoInitializeEx(0, 0);
  v4 = v3;
  if ( v3 >= 0 )
    v4 = _StaPrepareUrlMon(Context->pGIT, Context->dwCookie, Context->pUri);
  CloseThreadpoolWork(Work);
  _DeleteStaPrepareContext(&pStaPrepareContext);
  if ( v3 >= 0 )
    CoUninitialize();
  if ( (byte_10185760[16 * (v4 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v4 >> 31) + 2) << 9) | 3, 0x34u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v4);
}

```

## disassembly

```asm
0x10139f50  mov     edi, edi
0x10139f52  push    ebp
0x10139f53  mov     ebp, esp
0x10139f55  push    ecx
0x10139f56  push    ebx
0x10139f57  push    esi
0x10139f58  push    edi
0x10139f59  test    byte_10185760, 8; __annotation("TMF:",
0x10139f60  mov     esi, [ebp+Context]
0x10139f63  jz      short loc_10139F78
0x10139f65  push    esi; _a1
0x10139f66  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10139f6b  push    33h ; '3'
0x10139f6d  pop     edx; id
0x10139f6e  mov     ecx, 403h; LevelKeyword
0x10139f73  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10139f78  push    [ebp+Instance]; pci
0x10139f7b  mov     [ebp+pStaPrepareContext], esi
0x10139f7e  call    ds:__imp__CallbackMayRunLong@4; CallbackMayRunLong(x)
0x10139f84  push    0; dwCoInit
0x10139f86  push    0; pvReserved
0x10139f88  call    ds:__imp__CoInitializeEx@8; CoInitializeEx(x,x)
0x10139f8e  mov     edi, eax
0x10139f90  mov     ebx, edi
0x10139f92  test    edi, edi
0x10139f94  js      short CleanUp_520
0x10139f96  push    dword ptr [esi+8]; pUri
0x10139f99  mov     edx, [esi+4]; dwCookie
0x10139f9c  mov     ecx, [esi]; pGIT
0x10139f9e  call    ?_StaPrepareUrlMon@@YGJPAUIGlobalInterfaceTable@@KPAUIUri@@@Z; _StaPrepareUrlMon(IGlobalInterfaceTable *,ulong,IUri *)
0x10139fa3  mov     ebx, eax
0x10139fa5  push    [ebp+Work]; pwk
0x10139fa8  call    ds:__imp__CloseThreadpoolWork@4; CloseThreadpoolWork(x)
0x10139fae  lea     ecx, [ebp+pStaPrepareContext]; ppPrepareContext
0x10139fb1  call    ?_DeleteStaPrepareContext@@YGXPAPAUStaPrepareContext@@@Z; _DeleteStaPrepareContext(StaPrepareContext * *)
0x10139fb6  test    edi, edi
0x10139fb8  js      short loc_10139FC0
0x10139fba  call    ds:__imp__CoUninitialize@0; CoUninitialize()
0x10139fc0  mov     ecx, ebx; __annotation("TMF:",
0x10139fc2  sar     ecx, 1Fh
0x10139fc5  mov     eax, ecx
0x10139fc7  shl     eax, 4
0x10139fca  test    byte_10185760[eax], 8
0x10139fd1  jz      short loc_10139FEA
0x10139fd3  push    ebx; _a1
0x10139fd4  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10139fd9  add     ecx, 2
0x10139fdc  shl     ecx, 9
0x10139fdf  push    34h ; '4'
0x10139fe1  or      ecx, 3; LevelKeyword
0x10139fe4  pop     edx; id
0x10139fe5  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10139fea  pop     edi
0x10139feb  pop     esi
0x10139fec  pop     ebx
0x10139fed  leave
0x10139fee  retn    0Ch
```
