# URLMONRequest::s_MtaWorkItemCallUrlMonStart(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1800a22c0`
- end: `0x1800a2404`
- name: `?s_MtaWorkItemCallUrlMonStart@URLMONRequest@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `324`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *Instance, void *Context, _TP_WORK *Work)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18008c600`
- `0x1800a22c0`
- `0x18015bcb4`
- `0x180189008`
- `0x1801890e0`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800a2383`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800a2383`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x1800a230d`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x1800a230d`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1800a22f7`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1800a22f7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800a23a6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800a23a6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800a2328`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800a2328`

## pseudocode

```c
void __fastcall URLMONRequest::s_MtaWorkItemCallUrlMonStart(
        struct _TP_CALLBACK_INSTANCE *Instance,
        URLMONRequest *Context,
        _TP_WORK *Work)
{
  HRESULT v6; // esi
  int v7; // eax
  int v8; // edi

  if ( (xmmword_1801FAD20 & 8) != 0 )
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
      URLMONRequest::_ReportResult(Context, v7, v7, 0);
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
0x1800a22c0  push    rbx
0x1800a22c2  push    rbp
0x1800a22c3  push    rsi
0x1800a22c4  push    rdi
0x1800a22c5  sub     rsp, 28h
0x1800a22c9  mov     rbp, Work
0x1800a22cc  mov     rbx, Context
0x1800a22cf  mov     rdi, Instance
0x1800a22d2  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x1800a22d9  jz      short loc_1800A22F4
0x1800a22db  mov     edx, 28h ; '('; id
0x1800a22e0  lea     Work, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1800a22e7  mov     ecx, 403h; LevelKeyword
0x1800a22ec  mov     r9, rbx; _a1
0x1800a22ef  call    WPP_SF_q
0x1800a22f4  mov     Instance, rdi; pci
0x1800a22f7  call    cs:__imp_CallbackMayRunLong
0x1800a22fe  nop     dword ptr [rax+rax+00h]
0x1800a2303  mov     Context, [rbx+230h]; mod
0x1800a230a  mov     Instance, rdi; pci
0x1800a230d  call    cs:__imp_FreeLibraryWhenCallbackReturns
0x1800a2314  nop     dword ptr [rax+rax+00h]
0x1800a2319  xor     edx, edx; dwCoInit
0x1800a231b  mov     qword ptr [rbx+230h], 0
0x1800a2326  xor     ecx, ecx; pvReserved
0x1800a2328  call    cs:__imp_CoInitializeEx
0x1800a232f  nop     dword ptr [rax+rax+00h]
0x1800a2334  mov     esi, eax
0x1800a2336  test    eax, eax
0x1800a2338  js      short loc_1800A237E
0x1800a233a  mov     Instance, [rbx]
0x1800a233d  mov     rax, [Instance+0F8h]
0x1800a2344  mov     Instance, rbx
0x1800a2347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a234c  mov     Instance, rbx; this
0x1800a234f  call    ?_CallUrlMonStart@URLMONRequest@@IEAAJXZ; URLMONRequest::_CallUrlMonStart(void)
0x1800a2354  mov     edi, eax
0x1800a2356  test    eax, eax
0x1800a2358  jns     short loc_1800A236A
0x1800a235a  xor     r9d, r9d; pcwszResult
0x1800a235d  mov     r8d, eax; dwError
0x1800a2360  mov     edx, eax; hrResult
0x1800a2362  mov     Instance, rbx; this
0x1800a2365  call    ?_ReportResult@URLMONRequest@@IEAAJJKPEBG@Z; URLMONRequest::_ReportResult(long,ulong,ushort const *)
0x1800a236a  mov     Instance, [rbx]
0x1800a236d  mov     rax, [Instance+100h]
0x1800a2374  mov     Instance, rbx
0x1800a2377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a237c  jmp     short $CleanUp_141
0x1800a237e  mov     edi, esi
0x1800a2380  mov     Instance, rbp; pwk
0x1800a2383  call    cs:__imp_CloseThreadpoolWork
0x1800a238a  nop     dword ptr [rax+rax+00h]
0x1800a238f  mov     Instance, [rbx+0A0h]
0x1800a2396  mov     rax, [Instance]
0x1800a2399  mov     rax, [rax+10h]
0x1800a239d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a23a2  test    esi, esi
0x1800a23a4  js      short loc_1800A23B2
0x1800a23a6  call    cs:__imp_CoUninitialize
0x1800a23ad  nop     dword ptr [rax+rax+00h]
0x1800a23b2  mov     r9d, edi; __annotation("TMF:",
0x1800a23b5  sar     r9d, 1Fh
0x1800a23b9  lea     eax, ds:4[r9*2]
0x1800a23c1  movsxd  Instance, eax
0x1800a23c4  lea     rax, g_rgFastWppLevelEnabledFlags
0x1800a23cb  test    byte ptr [rax+Instance*8], 8
0x1800a23cf  jz      short loc_1800A23FA
0x1800a23d1  add     r9w, 2
0x1800a23d6  lea     Work, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1800a23dd  movzx   ecx, r9w
0x1800a23e1  mov     eax, 200h
0x1800a23e6  imul    ecx, eax
0x1800a23e9  mov     edx, 29h ; ')'; id
0x1800a23ee  mov     r9d, edi; _a1
0x1800a23f1  or      cx, 3; LevelKeyword
0x1800a23f5  call    WPP_SF_d
0x1800a23fa  add     rsp, 28h
0x1800a23fe  pop     rdi
0x1800a23ff  pop     rsi
0x1800a2400  pop     rbp
0x1800a2401  pop     rbx
0x1800a2402  retn
```
