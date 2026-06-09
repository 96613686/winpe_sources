# URLMONRequest::s_MtaWorkItemCallUrlMonStart(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1800a15c0`
- end: `0x1800a16e5`
- name: `?s_MtaWorkItemCallUrlMonStart@URLMONRequest@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `293`
- prototype: `void __fastcall(_TP_CALLBACK_INSTANCE *Instance, void *Context, _TP_WORK *Work)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18008c0ec`
- `0x1800a15c0`
- `0x1801585b0`
- `0x180185008`
- `0x1801850e0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800a1671`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800a1671`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x1800a1607`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x1800a1607`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1800a15f7`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1800a15f7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800a168e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800a168e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800a161c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800a161c`

## pseudocode

```c
void __fastcall URLMONRequest::s_MtaWorkItemCallUrlMonStart(
        _TP_CALLBACK_INSTANCE *Instance,
        URLMONRequest *Context,
        _TP_WORK *Work)
{
  HRESULT v6; // esi
  HRESULT v7; // eax
  int v8; // edi

  if ( (xmmword_1801F6C20 & 8) != 0 )
    WPP_SF_q(0x403u, 0x28u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (unsigned __int64)Context);
  CallbackMayRunLong(Instance);
  FreeLibraryWhenCallbackReturns(Instance, Context->_hModule);
  Context->_hModule = 0;
  v6 = CoInitializeEx(0, 0);
  if ( v6 < 0 )
  {
    v8 = v6;
  }
  else
  {
    Context->Lock(Context);
    v7 = URLMONRequest::_CallUrlMonStart(Context);
    v8 = v7;
    if ( v7 < 0 )
      URLMONRequest::_ReportResult(Context, v7, (const _GUID *)(unsigned int)v7, 0);
    Context->Unlock(Context);
  }
  CloseThreadpoolWork(Work);
  Context->_pRequestSite->Release(Context->_pRequestSite);
  if ( v6 >= 0 )
    CoUninitialize();
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v8 >> 31) + 4].rgbFlags[0] & 8) != 0 )
    WPP_SF_d((((unsigned __int16)(v8 >> 31) + 2) << 9) | 3, 0x29u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v8);
}

```

## disassembly

```asm
0x1800a15c0  push    rbx
0x1800a15c2  push    rbp
0x1800a15c3  push    rsi
0x1800a15c4  push    rdi
0x1800a15c5  sub     rsp, 28h
0x1800a15c9  mov     rbp, Work
0x1800a15cc  mov     rbx, Context
0x1800a15cf  mov     rdi, Instance
0x1800a15d2  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x1800a15d9  jz      short loc_1800A15F4
0x1800a15db  mov     edx, 28h ; '('; id
0x1800a15e0  lea     Work, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1800a15e7  mov     ecx, 403h; LevelKeyword
0x1800a15ec  mov     r9, rbx; _a1
0x1800a15ef  call    WPP_SF_q
0x1800a15f4  mov     Instance, rdi; pci
0x1800a15f7  call    cs:__imp_CallbackMayRunLong
0x1800a15fd  mov     Context, [rbx+230h]; mod
0x1800a1604  mov     Instance, rdi; pci
0x1800a1607  call    cs:__imp_FreeLibraryWhenCallbackReturns
0x1800a160d  xor     edx, edx; dwCoInit
0x1800a160f  mov     qword ptr [rbx+230h], 0
0x1800a161a  xor     ecx, ecx; pvReserved
0x1800a161c  call    cs:__imp_CoInitializeEx
0x1800a1622  mov     esi, eax
0x1800a1624  test    eax, eax
0x1800a1626  js      short loc_1800A166C
0x1800a1628  mov     Instance, [rbx]
0x1800a162b  mov     rax, [Instance+0F8h]
0x1800a1632  mov     Instance, rbx
0x1800a1635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a163a  mov     Instance, rbx; this
0x1800a163d  call    ?_CallUrlMonStart@URLMONRequest@@IEAAJXZ; URLMONRequest::_CallUrlMonStart(void)
0x1800a1642  mov     edi, eax
0x1800a1644  test    eax, eax
0x1800a1646  jns     short loc_1800A1658
0x1800a1648  xor     r9d, r9d; pcwszResult
0x1800a164b  mov     r8d, eax; dwError
0x1800a164e  mov     edx, eax; hrResult
0x1800a1650  mov     Instance, rbx; this
0x1800a1653  call    ?_ReportResult@URLMONRequest@@IEAAJJKPEBG@Z; URLMONRequest::_ReportResult(long,ulong,ushort const *)
0x1800a1658  mov     Instance, [rbx]
0x1800a165b  mov     rax, [Instance+100h]
0x1800a1662  mov     Instance, rbx
0x1800a1665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a166a  jmp     short $CleanUp_143
0x1800a166c  mov     edi, esi
0x1800a166e  mov     Instance, rbp; pwk
0x1800a1671  call    cs:__imp_CloseThreadpoolWork
0x1800a1677  mov     Instance, [rbx+0A0h]
0x1800a167e  mov     rax, [Instance]
0x1800a1681  mov     rax, [rax+10h]
0x1800a1685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a168a  test    esi, esi
0x1800a168c  js      short loc_1800A1694
0x1800a168e  call    cs:__imp_CoUninitialize
0x1800a1694  mov     r9d, edi; __annotation("TMF:",
0x1800a1697  sar     r9d, 1Fh
0x1800a169b  lea     eax, ds:4[r9*2]
0x1800a16a3  movsxd  Instance, eax
0x1800a16a6  lea     rax, g_rgFastWppLevelEnabledFlags
0x1800a16ad  test    byte ptr [rax+Instance*8], 8
0x1800a16b1  jz      short loc_1800A16DC
0x1800a16b3  add     r9w, 2
0x1800a16b8  lea     Work, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1800a16bf  movzx   ecx, r9w
0x1800a16c3  mov     eax, 200h
0x1800a16c8  imul    ecx, eax
0x1800a16cb  mov     edx, 29h ; ')'; id
0x1800a16d0  mov     r9d, edi; _a1
0x1800a16d3  or      cx, 3; LevelKeyword
0x1800a16d7  call    WPP_SF_d
0x1800a16dc  add     rsp, 28h
0x1800a16e0  pop     rdi
0x1800a16e1  pop     rsi
0x1800a16e2  pop     rbp
0x1800a16e3  pop     rbx
0x1800a16e4  retn
```
