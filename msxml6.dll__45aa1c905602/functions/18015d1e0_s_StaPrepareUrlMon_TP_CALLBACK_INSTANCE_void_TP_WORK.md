# s_StaPrepareUrlMon(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18015d1e0`
- end: `0x18015d2db`
- name: `?s_StaPrepareUrlMon@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `251`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *Instance, void *Context, _TP_WORK *Work)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18015b448`
- `0x18015c03c`
- `0x18015d1e0`
- `0x180189008`
- `0x1801890e0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18015d25c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18015d25c`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18015d222`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18015d222`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18015d276`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18015d276`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18015d232`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18015d232`

## pseudocode

```c
void __fastcall s_StaPrepareUrlMon(struct _TP_CALLBACK_INSTANCE *Instance, StaPrepareContext *Context, _TP_WORK *Work)
{
  HRESULT v6; // edi
  int v7; // ebx
  StaPrepareContext *pStaPrepareContext; // [rsp+38h] [rbp+10h] BYREF

  if ( (xmmword_1801FAD20 & 8) != 0 )
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
0x18015d1e0  mov     [rsp+arg_0], rbx
0x18015d1e5  mov     [rsp+arg_10], rsi
0x18015d1ea  push    rdi
0x18015d1eb  sub     rsp, 20h
0x18015d1ef  mov     rsi, Work
0x18015d1f2  mov     rbx, Context
0x18015d1f5  mov     rdi, Instance
0x18015d1f8  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x18015d1ff  jz      short loc_18015D21A
0x18015d201  mov     edx, 33h ; '3'; id
0x18015d206  lea     Work, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015d20d  mov     ecx, 403h; LevelKeyword
0x18015d212  mov     r9, rbx; _a1
0x18015d215  call    WPP_SF_q
0x18015d21a  mov     Instance, rdi; pci
0x18015d21d  mov     [rsp+28h+pStaPrepareContext], rbx
0x18015d222  call    cs:__imp_CallbackMayRunLong
0x18015d229  nop     dword ptr [rax+rax+00h]
0x18015d22e  xor     edx, edx; dwCoInit
0x18015d230  xor     ecx, ecx; pvReserved
0x18015d232  call    cs:__imp_CoInitializeEx
0x18015d239  nop     dword ptr [rax+rax+00h]
0x18015d23e  mov     edi, eax
0x18015d240  test    eax, eax
0x18015d242  js      short loc_18015D257
0x18015d244  mov     Work, [rbx+10h]; pUri
0x18015d248  mov     edx, [rbx+8]; dwCookie
0x18015d24b  mov     Instance, [rbx]; pGIT
0x18015d24e  call    ?_StaPrepareUrlMon@@YAJPEAUIGlobalInterfaceTable@@KPEAUIUri@@@Z; _StaPrepareUrlMon(IGlobalInterfaceTable *,ulong,IUri *)
0x18015d253  mov     ebx, eax
0x18015d255  jmp     short $CleanUp_552
0x18015d257  mov     ebx, edi
0x18015d259  mov     Instance, rsi; pwk
0x18015d25c  call    cs:__imp_CloseThreadpoolWork
0x18015d263  nop     dword ptr [rax+rax+00h]
0x18015d268  lea     Instance, [rsp+28h+pStaPrepareContext]; ppPrepareContext
0x18015d26d  call    ?_DeleteStaPrepareContext@@YAXPEAPEAUStaPrepareContext@@@Z; _DeleteStaPrepareContext(StaPrepareContext * *)
0x18015d272  test    edi, edi
0x18015d274  js      short loc_18015D282
0x18015d276  call    cs:__imp_CoUninitialize
0x18015d27d  nop     dword ptr [rax+rax+00h]
0x18015d282  mov     r9d, ebx; __annotation("TMF:",
0x18015d285  sar     r9d, 1Fh
0x18015d289  lea     eax, ds:4[r9*2]
0x18015d291  movsxd  Instance, eax
0x18015d294  lea     rax, g_rgFastWppLevelEnabledFlags
0x18015d29b  test    byte ptr [rax+Instance*8], 8
0x18015d29f  jz      short loc_18015D2CA
0x18015d2a1  add     r9w, 2
0x18015d2a6  lea     Work, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015d2ad  movzx   ecx, r9w
0x18015d2b1  mov     eax, 200h
0x18015d2b6  imul    ecx, eax
0x18015d2b9  mov     edx, 34h ; '4'; id
0x18015d2be  mov     r9d, ebx; _a1
0x18015d2c1  or      cx, 3; LevelKeyword
0x18015d2c5  call    WPP_SF_d
0x18015d2ca  mov     rbx, [rsp+28h+arg_0]
0x18015d2cf  mov     rsi, [rsp+28h+arg_10]
0x18015d2d4  add     rsp, 20h
0x18015d2d8  pop     rdi
0x18015d2d9  retn
```
