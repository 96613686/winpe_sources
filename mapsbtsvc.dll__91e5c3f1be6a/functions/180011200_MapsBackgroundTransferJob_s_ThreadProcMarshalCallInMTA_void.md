# MapsBackgroundTransferJob::s_ThreadProcMarshalCallInMTA(void *)

- ea: `0x180011200`
- end: `0x180011298`
- name: `?s_ThreadProcMarshalCallInMTA@MapsBackgroundTransferJob@@CAKPEAX@Z`
- size: `152`
- prototype: `__int64 __fastcall(_QWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180011200`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001127f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001127f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180011211`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180011211`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180011272`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180011272`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18001122a`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180011266`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18001122a`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180011266`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180011240`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180011240`

## string_xrefs

- `0x180011221`: `MapsBackgroundTransferJob::s_ThreadProcMarshalCallInMTA`
- `0x18001125d`: `MapsBackgroundTransferJob::s_ThreadProcMarshalCallInMTA`

## pseudocode

```c
__int64 __fastcall MapsBackgroundTransferJob::s_ThreadProcMarshalCallInMTA(_QWORD *lpThreadParameter)
{
  HRESULT v2; // eax
  int v3; // edi
  __int64 v4; // rcx
  int v5; // eax
  void *v6; // rcx

  v2 = CoInitializeEx(0, 0);
  if ( v2 >= 0 )
  {
    v4 = *(_QWORD *)(*lpThreadParameter + 56LL);
    if ( !v4 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    if ( v5 >= 0 )
      v3 = 0;
    else
      v3 = ZTraceReportPropagationNoThis(v5, "MapsBackgroundTransferJob::s_ThreadProcMarshalCallInMTA", 1580);
    CoUninitialize();
  }
  else
  {
    v3 = ZTraceReportPropagationNoThis(v2, "MapsBackgroundTransferJob::s_ThreadProcMarshalCallInMTA", 1577);
  }
  v6 = (void *)lpThreadParameter[2];
  *((_DWORD *)lpThreadParameter + 2) = v3;
  if ( !SetEvent(v6) )
    __int2c();
  return 0;
}

```

## disassembly

```asm
0x180011200  mov     [rsp+arg_0], rbx
0x180011205  push    rdi
0x180011206  sub     rsp, 20h
0x18001120a  mov     rbx, rcx
0x18001120d  xor     edx, edx; dwCoInit
0x18001120f  xor     ecx, ecx; pvReserved
0x180011211  call    cs:__imp_CoInitializeEx
0x180011217  test    eax, eax
0x180011219  jns     short loc_180011234
0x18001121b  mov     r8d, 629h
0x180011221  lea     rdx, aMapsbackground_15; "MapsBackgroundTransferJob::s_ThreadProc"...
0x180011228  mov     ecx, eax
0x18001122a  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180011230  mov     edi, eax
0x180011232  jmp     short loc_180011278
0x180011234  mov     rax, [rbx]
0x180011237  mov     rcx, [rax+38h]
0x18001123b  test    rcx, rcx
0x18001123e  jnz     short loc_180011247
0x180011240  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180011246  int     3; Trap to Debugger
0x180011247  mov     rax, [rcx]
0x18001124a  mov     rax, [rax+10h]
0x18001124e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011253  test    eax, eax
0x180011255  jns     short loc_180011270
0x180011257  mov     r8d, 62Ch
0x18001125d  lea     rdx, aMapsbackground_15; "MapsBackgroundTransferJob::s_ThreadProc"...
0x180011264  mov     ecx, eax
0x180011266  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18001126c  mov     edi, eax
0x18001126e  jmp     short loc_180011272
0x180011270  xor     edi, edi
0x180011272  call    cs:__imp_CoUninitialize
0x180011278  mov     rcx, [rbx+10h]; hEvent
0x18001127c  mov     [rbx+8], edi
0x18001127f  call    cs:__imp_SetEvent
0x180011285  test    eax, eax
0x180011287  jnz     short loc_18001128B
0x180011289  int     2Ch; Windows NT - assertion failure
0x18001128b  mov     rbx, [rsp+28h+arg_0]
0x180011290  xor     eax, eax
0x180011292  add     rsp, 20h
0x180011296  pop     rdi
0x180011297  retn
```
