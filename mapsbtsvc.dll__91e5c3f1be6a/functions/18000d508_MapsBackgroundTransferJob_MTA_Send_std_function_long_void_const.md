# MapsBackgroundTransferJob::MTA_Send(std::function<long (void)> const &)

- ea: `0x18000d508`
- end: `0x18000d64d`
- name: `?MTA_Send@MapsBackgroundTransferJob@@AEAAJAEBV?$function@$$A6AJXZ@std@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(const void *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000b9c0`

## callees

- `0x180006dc4`
- `0x1800071a0`
- `0x180007728`
- `0x180009344`
- `0x18000d508`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000d53b`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000d53b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000d5e3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000d5e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d592`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000d588`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000d588`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000d5c3`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000d5c3`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000d62d`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000d62d`

## pseudocode

```c
__int64 __fastcall MapsBackgroundTransferJob::MTA_Send(const void *a1, __int64 a2)
{
  HANDLE v4; // rbx
  wil::details *v5; // rcx
  HANDLE Event; // rsi
  signed int LastError; // eax
  int LastErrorFailHr; // eax
  int v9; // r8d
  int v10; // ecx
  unsigned int v11; // eax
  void *v12; // rdx
  int v13; // r8d
  int v14; // ecx
  DWORD v15; // eax
  __int64 v16; // r8
  const char *v17; // r9
  unsigned int v18; // ebx
  __int128 Context; // [rsp+20h] [rbp-48h] BYREF
  HANDLE v21; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HANDLE hHandle; // [rsp+80h] [rbp+18h] BYREF

  Context = 0;
  v21 = 0;
  v4 = 0;
  hHandle = 0;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &hHandle,
      Event);
    v4 = hHandle;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    if ( LastErrorFailHr < 0 )
    {
      v9 = 1556;
      v10 = LastErrorFailHr;
LABEL_9:
      v11 = ZTraceReportPropagation(v10, "MapsBackgroundTransferJob::MTA_Send", v9, a1);
LABEL_20:
      v18 = v11;
      goto LABEL_21;
    }
  }
  *(_QWORD *)&Context = a2;
  DWORD2(Context) = 0;
  v21 = v4;
  if ( !QueueUserWorkItem(MapsBackgroundTransferJob::s_ThreadProcMarshalCallInMTA, &Context, 0) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v13 = 1563;
    v14 = LastError;
    goto LABEL_19;
  }
  v15 = WaitForSingleObjectEx(v4, 0xFFFFFFFF, 0);
  if ( v15 == 258 )
  {
    v13 = 1564;
    v14 = -2147418113;
LABEL_19:
    v11 = ZTraceReportOrigination(v14, "MapsBackgroundTransferJob::MTA_Send", v13, a1);
    goto LABEL_20;
  }
  if ( v15 )
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v16, v17);
  v10 = DWORD2(Context);
  if ( SDWORD2(Context) < 0 )
  {
    v9 = 1565;
    goto LABEL_9;
  }
  v18 = 0;
LABEL_21:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    (wil::details **)&hHandle,
    v12);
  return v18;
}

```

## disassembly

```asm
0x18000d508  mov     r11, rsp
0x18000d50b  push    rbx
0x18000d50c  push    rbp
0x18000d50d  push    rsi
0x18000d50e  push    rdi
0x18000d50f  sub     rsp, 48h
0x18000d513  mov     rbp, rdx
0x18000d516  mov     rdi, rcx
0x18000d519  xorps   xmm0, xmm0
0x18000d51c  xor     eax, eax
0x18000d51e  movups  [rsp+68h+Context], xmm0
0x18000d523  mov     [r11-38h], rax
0x18000d527  xor     ebx, ebx
0x18000d529  mov     [r11+18h], rbx
0x18000d52d  xor     edx, edx; lpName
0x18000d52f  xor     ecx, ecx; lpEventAttributes
0x18000d531  mov     r9d, 1F0003h; dwDesiredAccess
0x18000d537  lea     r8d, [rax+1]; dwFlags
0x18000d53b  call    cs:__imp_CreateEventExW
0x18000d541  mov     rsi, rax
0x18000d544  test    rax, rax
0x18000d547  jz      short loc_18000D5A8
0x18000d549  call    cs:__imp_GetLastError
0x18000d54f  mov     rdx, rsi
0x18000d552  lea     rcx, [rsp+68h+hHandle]
0x18000d55a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000d55f  mov     rbx, [rsp+68h+hHandle]
0x18000d567  mov     qword ptr [rsp+68h+Context], rbp
0x18000d56c  mov     dword ptr [rsp+68h+Context+8], 0
0x18000d574  mov     [rsp+68h+var_38], rbx
0x18000d579  xor     r8d, r8d; Flags
0x18000d57c  lea     rdx, [rsp+68h+Context]; Context
0x18000d581  lea     rcx, ?s_ThreadProcMarshalCallInMTA@MapsBackgroundTransferJob@@CAKPEAX@Z; Function
0x18000d588  call    cs:__imp_QueueUserWorkItem
0x18000d58e  test    eax, eax
0x18000d590  jnz     short loc_18000D5DA
0x18000d592  call    cs:__imp_GetLastError
0x18000d598  test    eax, eax
0x18000d59a  jz      short loc_18000D5CB
0x18000d59c  jle     short loc_18000D5D0
0x18000d59e  movzx   eax, ax
0x18000d5a1  or      eax, 80070000h
0x18000d5a6  jmp     short loc_18000D5D0
0x18000d5a8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000d5ad  test    eax, eax
0x18000d5af  jns     short loc_18000D567
0x18000d5b1  mov     r8d, 614h
0x18000d5b7  mov     ecx, eax
0x18000d5b9  lea     rdx, aMapsbackground_34; "MapsBackgroundTransferJob::MTA_Send"
0x18000d5c0  mov     r9, rdi
0x18000d5c3  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000d5c9  jmp     short loc_18000D633
0x18000d5cb  mov     eax, 80390004h
0x18000d5d0  mov     r8d, 61Bh
0x18000d5d6  mov     ecx, eax
0x18000d5d8  jmp     short loc_18000D623
0x18000d5da  xor     r8d, r8d; bAlertable
0x18000d5dd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d5e0  mov     rcx, rbx; hHandle
0x18000d5e3  call    cs:__imp_WaitForSingleObjectEx
0x18000d5e9  cmp     eax, 102h
0x18000d5ee  jz      short loc_18000D618
0x18000d5f0  test    eax, eax
0x18000d5f2  jz      short loc_18000D604
0x18000d5f4  mov     rcx, [rsp+68h]; this
0x18000d5f9  mov     edx, 0B0Fh; void *
0x18000d5fe  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000d604  mov     ecx, dword ptr [rsp+68h+Context+8]
0x18000d608  test    ecx, ecx
0x18000d60a  jns     short loc_18000D614
0x18000d60c  mov     r8d, 61Dh
0x18000d612  jmp     short loc_18000D5B9
0x18000d614  xor     ebx, ebx
0x18000d616  jmp     short loc_18000D635
0x18000d618  mov     r8d, 61Ch
0x18000d61e  mov     ecx, 8000FFFFh
0x18000d623  mov     r9, rdi
0x18000d626  lea     rdx, aMapsbackground_34; "MapsBackgroundTransferJob::MTA_Send"
0x18000d62d  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18000d633  mov     ebx, eax
0x18000d635  lea     rcx, [rsp+68h+hHandle]
0x18000d63d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d642  mov     eax, ebx
0x18000d644  add     rsp, 48h
0x18000d648  pop     rdi
0x18000d649  pop     rsi
0x18000d64a  pop     rbp
0x18000d64b  pop     rbx
0x18000d64c  retn
```
