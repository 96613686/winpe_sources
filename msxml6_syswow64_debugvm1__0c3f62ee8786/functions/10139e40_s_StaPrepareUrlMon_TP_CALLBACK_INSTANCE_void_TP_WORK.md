# s_StaPrepareUrlMon(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x10139e40`
- end: `0x10139ee1`
- name: `?s_StaPrepareUrlMon@@YGXPAU_TP_CALLBACK_INSTANCE@@PAXPAU_TP_WORK@@@Z`
- size: `161`
- prototype: `void __stdcall(_TP_CALLBACK_INSTANCE *Instance, void *Context, _TP_WORK *Work)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1013738d`
- `0x1013876c`
- `0x10139e40`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x10139e98`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x10139e98`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x10139e6e`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x10139e6e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x10139eaa`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x10139eaa`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x10139e78`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x10139e78`

## pseudocode

```c
void __stdcall s_StaPrepareUrlMon(_TP_CALLBACK_INSTANCE *Instance, StaPrepareContext *Context, _TP_WORK *Work)
{
  HRESULT v3; // edi
  int v4; // ebx
  StaPrepareContext *pStaPrepareContext; // [esp+Ch] [ebp-4h] BYREF

  if ( (byte_101857A0[0] & 8) != 0 )
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
  if ( (byte_101857A0[16 * (v4 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v4 >> 31) + 2) << 9) | 3, 0x34u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v4);
}

```

## disassembly

```asm
0x10139e40  mov     edi, edi
0x10139e42  push    ebp
0x10139e43  mov     ebp, esp
0x10139e45  push    ecx
0x10139e46  push    ebx
0x10139e47  push    esi
0x10139e48  push    edi
0x10139e49  test    byte_101857A0, 8; __annotation("TMF:",
0x10139e50  mov     esi, [ebp+Context]
0x10139e53  jz      short loc_10139E68
0x10139e55  push    esi; _a1
0x10139e56  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10139e5b  push    33h ; '3'
0x10139e5d  pop     edx; id
0x10139e5e  mov     ecx, 403h; LevelKeyword
0x10139e63  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10139e68  push    [ebp+Instance]; pci
0x10139e6b  mov     [ebp+pStaPrepareContext], esi
0x10139e6e  call    ds:__imp__CallbackMayRunLong@4; CallbackMayRunLong(x)
0x10139e74  push    0; dwCoInit
0x10139e76  push    0; pvReserved
0x10139e78  call    ds:__imp__CoInitializeEx@8; CoInitializeEx(x,x)
0x10139e7e  mov     edi, eax
0x10139e80  mov     ebx, edi
0x10139e82  test    edi, edi
0x10139e84  js      short CleanUp_520
0x10139e86  push    dword ptr [esi+8]; pUri
0x10139e89  mov     edx, [esi+4]; dwCookie
0x10139e8c  mov     ecx, [esi]; pGIT
0x10139e8e  call    ?_StaPrepareUrlMon@@YGJPAUIGlobalInterfaceTable@@KPAUIUri@@@Z; _StaPrepareUrlMon(IGlobalInterfaceTable *,ulong,IUri *)
0x10139e93  mov     ebx, eax
0x10139e95  push    [ebp+Work]; pwk
0x10139e98  call    ds:__imp__CloseThreadpoolWork@4; CloseThreadpoolWork(x)
0x10139e9e  lea     ecx, [ebp+pStaPrepareContext]; ppPrepareContext
0x10139ea1  call    ?_DeleteStaPrepareContext@@YGXPAPAUStaPrepareContext@@@Z; _DeleteStaPrepareContext(StaPrepareContext * *)
0x10139ea6  test    edi, edi
0x10139ea8  js      short loc_10139EB0
0x10139eaa  call    ds:__imp__CoUninitialize@0; CoUninitialize()
0x10139eb0  mov     ecx, ebx; __annotation("TMF:",
0x10139eb2  sar     ecx, 1Fh
0x10139eb5  mov     eax, ecx
0x10139eb7  shl     eax, 4
0x10139eba  test    byte_101857A0[eax], 8
0x10139ec1  jz      short loc_10139EDA
0x10139ec3  push    ebx; _a1
0x10139ec4  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10139ec9  add     ecx, 2
0x10139ecc  shl     ecx, 9
0x10139ecf  push    34h ; '4'
0x10139ed1  or      ecx, 3; LevelKeyword
0x10139ed4  pop     edx; id
0x10139ed5  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10139eda  pop     edi
0x10139edb  pop     esi
0x10139edc  pop     ebx
0x10139edd  leave
0x10139ede  retn    0Ch
```
