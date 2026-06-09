# MFCreateD3D12SynchronizationObjectInternal

- ea: `0x18006cc58`
- end: `0x18006cf74`
- name: `MFCreateD3D12SynchronizationObjectInternal`
- size: `796`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800587e4`

## callees

- `0x18002312c`
- `0x180045060`
- `0x180056638`
- `0x180066b9c`
- `0x180066d24`
- `0x1800696c8`
- `0x18006cc58`
- `0x18006dc78`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cd1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006ce28`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cf02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cd1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006ce28`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cf02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ccc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cdd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cdef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ccc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cdd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cdef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cec9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006ccd1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006cddf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006ceb9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006ccd1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006cddf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006ceb9`

## string_xrefs

- `0x18006cc7c`: `MFCreateD3D12SynchronizationObjectInternal`
- `0x18006cd31`: `MFCreateD3D12SynchronizationObjectInternal`
- `0x18006ce3f`: `MFCreateD3D12SynchronizationObjectInternal`
- `0x18006cf19`: `MFCreateD3D12SynchronizationObjectInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MFCreateD3D12SynchronizationObjectInternal(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  CallStackTracing *v5; // rdi
  int v6; // ebx
  CallStackContext *v7; // rsi
  DWORD v8; // r14d
  CallStackContext *v9; // rax
  CallStackTracing *v10; // rcx
  __int64 v11; // rax
  CallStackTracing *v12; // rdi
  CallStackContext *v13; // rsi
  DWORD v14; // r14d
  CallStackContext *v15; // rax
  CallStackTracing *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rdx
  CallStackTracing *v19; // rdi
  CallStackContext *v20; // rsi
  DWORD LastError; // r14d
  CallStackContext *Value; // rax
  CallStackTracing *v23; // rcx
  __int64 v24; // rax
  char v26[16]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v27; // [rsp+70h] [rbp+30h] BYREF
  char v28; // [rsp+78h] [rbp+38h] BYREF
  __int64 v29; // [rsp+80h] [rbp+40h] BYREF

  v29 = a3;
  v27 = a1;
  v26[0] = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v28,
    "MFCreateD3D12SynchronizationObjectInternal",
    37);
  if ( a4 )
  {
    *a4 = 0;
    v29 = 0;
    Microsoft::WRL::ComPtr<MFD3D12Sync>::InternalRelease(&v29);
    v6 = Microsoft::WRL::Details::MakeAndInitialize<MFD3D12Sync,MFD3D12Sync,ID3D12Device * &,bool &>(&v29, &v27, v26);
    if ( v6 >= 0 )
    {
      v6 = Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>>(
             v29,
             &GUID_802302b0_82de_45e1_b421_f19ee5bdaf23,
             a4);
      if ( v6 >= 0 )
        goto LABEL_47;
      v19 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)&qword_18009CF60;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v20 = (CallStackTracing *)((char *)v19 + 208);
        LastError = GetLastError();
        Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v19 + 3));
        if ( Value )
        {
          v20 = Value;
        }
        else if ( !GetLastError() )
        {
          v23 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)&qword_18009CF60;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
          }
          v24 = (**(__int64 (__fastcall ***)(CallStackTracing *))v23)(v23);
          if ( v24 )
            v20 = (CallStackContext *)v24;
        }
        SetLastError(LastError);
        if ( *((_DWORD *)v20 + 499) != v6 )
          CallStackContext::TraceFailure(v20, "MFCreateD3D12SynchronizationObjectInternal", 45, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_47;
      v18 = 13;
    }
    else
    {
      v12 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)&qword_18009CF60;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v13 = (CallStackTracing *)((char *)v12 + 208);
        v14 = GetLastError();
        v15 = (CallStackContext *)TlsGetValue(*((_DWORD *)v12 + 3));
        if ( v15 )
        {
          v13 = v15;
        }
        else if ( !GetLastError() )
        {
          v16 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v16 = (CallStackTracing *)&qword_18009CF60;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
          }
          v17 = (**(__int64 (__fastcall ***)(CallStackTracing *))v16)(v16);
          if ( v17 )
            v13 = (CallStackContext *)v17;
        }
        SetLastError(v14);
        if ( *((_DWORD *)v13 + 499) != v6 )
          CallStackContext::TraceFailure(v13, "MFCreateD3D12SynchronizationObjectInternal", 44, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_47;
      v18 = 12;
    }
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids, 0, v6);
LABEL_47:
    Microsoft::WRL::ComPtr<MFD3D12Sync>::InternalRelease(&v29);
    goto LABEL_48;
  }
  v5 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v5 = (CallStackTracing *)&qword_18009CF60;
    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
  }
  v6 = -2147024809;
  if ( *((_BYTE *)v5 + 8) )
  {
    v7 = (CallStackTracing *)((char *)v5 + 208);
    v8 = GetLastError();
    v9 = (CallStackContext *)TlsGetValue(*((_DWORD *)v5 + 3));
    if ( v9 )
    {
      v7 = v9;
    }
    else if ( !GetLastError() )
    {
      v10 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)&qword_18009CF60;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
      }
      v11 = (**(__int64 (__fastcall ***)(CallStackTracing *))v10)(v10);
      if ( v11 )
        v7 = (CallStackContext *)v11;
    }
    SetLastError(v8);
    if ( *((_DWORD *)v7 + 499) != -2147024809 )
      CallStackContext::TraceFailure(v7, "MFCreateD3D12SynchronizationObjectInternal", 39, -2147024809);
  }
  if ( g_wppLevels )
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids, 0, -2147024809);
LABEL_48:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v28);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006cc58  mov     [rsp-28h+arg_10], r8
0x18006cc5d  mov     [rsp-28h+arg_0], rcx
0x18006cc62  push    rbp
0x18006cc63  push    rbx
0x18006cc64  push    rsi
0x18006cc65  push    rdi
0x18006cc66  push    r14
0x18006cc68  mov     rbp, rsp
0x18006cc6b  sub     rsp, 40h
0x18006cc6f  mov     rdi, r9
0x18006cc72  mov     [rbp+var_10], 0
0x18006cc76  mov     r8d, 25h ; '%'; int
0x18006cc7c  lea     rdx, aMfcreated3d12s; "MFCreateD3D12SynchronizationObjectInter"...
0x18006cc83  lea     rcx, [rbp+arg_8]; this
0x18006cc87  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006cc8c  test    rdi, rdi
0x18006cc8f  jnz     loc_18006CD75
0x18006cc95  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cc9c  test    rdi, rdi
0x18006cc9f  jnz     short loc_18006CCAF
0x18006cca1  lea     rdi, qword_18009CF60
0x18006cca8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ccaf  mov     ebx, 80070057h
0x18006ccb4  cmp     byte ptr [rdi+8], 0
0x18006ccb8  jz      loc_18006CD40
0x18006ccbe  lea     rsi, [rdi+0D0h]
0x18006ccc5  call    cs:__imp_GetLastError
0x18006cccb  mov     r14d, eax
0x18006ccce  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18006ccd1  call    cs:__imp_TlsGetValue
0x18006ccd7  test    rax, rax
0x18006ccda  jz      short loc_18006CCE1
0x18006ccdc  mov     rsi, rax
0x18006ccdf  jmp     short loc_18006CD17
0x18006cce1  call    cs:__imp_GetLastError
0x18006cce7  test    eax, eax
0x18006cce9  jnz     short loc_18006CD17
0x18006cceb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ccf2  test    rcx, rcx
0x18006ccf5  jnz     short loc_18006CD05
0x18006ccf7  lea     rcx, qword_18009CF60
0x18006ccfe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cd05  mov     rax, [rcx]
0x18006cd08  mov     rax, [rax]
0x18006cd0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cd10  test    rax, rax
0x18006cd13  cmovnz  rsi, rax
0x18006cd17  mov     ecx, r14d; dwErrCode
0x18006cd1a  call    cs:__imp_SetLastError
0x18006cd20  cmp     [rsi+7CCh], ebx
0x18006cd26  jz      short loc_18006CD40
0x18006cd28  mov     r9d, ebx; int
0x18006cd2b  mov     r8d, 27h ; '''; int
0x18006cd31  lea     rdx, aMfcreated3d12s; "MFCreateD3D12SynchronizationObjectInter"...
0x18006cd38  mov     rcx, rsi; this
0x18006cd3b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006cd40  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006cd47  jb      loc_18006CF5E
0x18006cd4d  mov     edx, 0Bh
0x18006cd52  mov     [rsp+40h+var_20], ebx
0x18006cd56  xor     r9d, r9d
0x18006cd59  lea     r8, WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids
0x18006cd60  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cd67  mov     rcx, [rcx+10h]
0x18006cd6b  call    WPP_SF_qd
0x18006cd70  jmp     loc_18006CF5E
0x18006cd75  mov     qword ptr [rdi], 0
0x18006cd7c  mov     [rbp+arg_10], 0
0x18006cd84  lea     rcx, [rbp+arg_10]
0x18006cd88  call    ?InternalRelease@?$ComPtr@VMFD3D12Sync@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<MFD3D12Sync>::InternalRelease(void)
0x18006cd8d  lea     r8, [rbp+var_10]
0x18006cd91  lea     rdx, [rbp+arg_0]
0x18006cd95  lea     rcx, [rbp+arg_10]
0x18006cd99  call    ??$MakeAndInitialize@VMFD3D12Sync@@V1@AEAPEAUID3D12Device@@AEA_N@Details@WRL@Microsoft@@YAJPEAPEAVMFD3D12Sync@@AEAPEAUID3D12Device@@AEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<MFD3D12Sync,MFD3D12Sync,ID3D12Device * &,bool &>(MFD3D12Sync * *,ID3D12Device * &,bool &)
0x18006cd9e  mov     ebx, eax
0x18006cda0  test    eax, eax
0x18006cda2  jns     loc_18006CE65
0x18006cda8  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cdaf  test    rdi, rdi
0x18006cdb2  jnz     short loc_18006CDC2
0x18006cdb4  lea     rdi, qword_18009CF60
0x18006cdbb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cdc2  cmp     byte ptr [rdi+8], 0
0x18006cdc6  jz      loc_18006CE4E
0x18006cdcc  lea     rsi, [rdi+0D0h]
0x18006cdd3  call    cs:__imp_GetLastError
0x18006cdd9  mov     r14d, eax
0x18006cddc  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18006cddf  call    cs:__imp_TlsGetValue
0x18006cde5  test    rax, rax
0x18006cde8  jz      short loc_18006CDEF
0x18006cdea  mov     rsi, rax
0x18006cded  jmp     short loc_18006CE25
0x18006cdef  call    cs:__imp_GetLastError
0x18006cdf5  test    eax, eax
0x18006cdf7  jnz     short loc_18006CE25
0x18006cdf9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ce00  test    rcx, rcx
0x18006ce03  jnz     short loc_18006CE13
0x18006ce05  lea     rcx, qword_18009CF60
0x18006ce0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ce13  mov     rax, [rcx]
0x18006ce16  mov     rax, [rax]
0x18006ce19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ce1e  test    rax, rax
0x18006ce21  cmovnz  rsi, rax
0x18006ce25  mov     ecx, r14d; dwErrCode
0x18006ce28  call    cs:__imp_SetLastError
0x18006ce2e  cmp     [rsi+7CCh], ebx
0x18006ce34  jz      short loc_18006CE4E
0x18006ce36  mov     r9d, ebx; int
0x18006ce39  mov     r8d, 2Ch ; ','; int
0x18006ce3f  lea     rdx, aMfcreated3d12s; "MFCreateD3D12SynchronizationObjectInter"...
0x18006ce46  mov     rcx, rsi; this
0x18006ce49  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006ce4e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ce55  jb      loc_18006CF54
0x18006ce5b  mov     edx, 0Ch
0x18006ce60  jmp     loc_18006CF36
0x18006ce65  mov     r8, rdi
0x18006ce68  lea     rdx, _GUID_802302b0_82de_45e1_b421_f19ee5bdaf23
0x18006ce6f  mov     rcx, [rbp+arg_10]
0x18006ce73  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMFD3D12SynchronizationObjectCommands@@UIMFD3D12SynchronizationObject@@UIMFD3D12SynchronizationObjectCommandsInternal@@UIMFD3D11SynchronizationObjectCommands@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMFD3D12SynchronizationObjectCommands@@UIMFD3D12SynchronizationObject@@UIMFD3D12SynchronizationObjectCommandsInternal@@UIMFD3D11SynchronizationObjectCommands@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x18006ce78  mov     ebx, eax
0x18006ce7a  test    eax, eax
0x18006ce7c  jns     loc_18006CF54
0x18006ce82  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ce89  test    rdi, rdi
0x18006ce8c  jnz     short loc_18006CE9C
0x18006ce8e  lea     rdi, qword_18009CF60
0x18006ce95  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ce9c  cmp     byte ptr [rdi+8], 0
0x18006cea0  jz      loc_18006CF28
0x18006cea6  lea     rsi, [rdi+0D0h]
0x18006cead  call    cs:__imp_GetLastError
0x18006ceb3  mov     r14d, eax
0x18006ceb6  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18006ceb9  call    cs:__imp_TlsGetValue
0x18006cebf  test    rax, rax
0x18006cec2  jz      short loc_18006CEC9
0x18006cec4  mov     rsi, rax
0x18006cec7  jmp     short loc_18006CEFF
0x18006cec9  call    cs:__imp_GetLastError
0x18006cecf  test    eax, eax
0x18006ced1  jnz     short loc_18006CEFF
0x18006ced3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ceda  test    rcx, rcx
0x18006cedd  jnz     short loc_18006CEED
0x18006cedf  lea     rcx, qword_18009CF60
0x18006cee6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ceed  mov     rax, [rcx]
0x18006cef0  mov     rax, [rax]
0x18006cef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cef8  test    rax, rax
0x18006cefb  cmovnz  rsi, rax
0x18006ceff  mov     ecx, r14d; dwErrCode
0x18006cf02  call    cs:__imp_SetLastError
0x18006cf08  cmp     [rsi+7CCh], ebx
0x18006cf0e  jz      short loc_18006CF28
0x18006cf10  mov     r9d, ebx; int
0x18006cf13  mov     r8d, 2Dh ; '-'; int
0x18006cf19  lea     rdx, aMfcreated3d12s; "MFCreateD3D12SynchronizationObjectInter"...
0x18006cf20  mov     rcx, rsi; this
0x18006cf23  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006cf28  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006cf2f  jb      short loc_18006CF54
0x18006cf31  mov     edx, 0Dh
0x18006cf36  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cf3d  mov     [rsp+40h+var_20], ebx
0x18006cf41  xor     r9d, r9d
0x18006cf44  lea     r8, WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids
0x18006cf4b  mov     rcx, [rcx+10h]
0x18006cf4f  call    WPP_SF_qd
0x18006cf54  lea     rcx, [rbp+arg_10]
0x18006cf58  call    ?InternalRelease@?$ComPtr@VMFD3D12Sync@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<MFD3D12Sync>::InternalRelease(void)
0x18006cf5d  nop
0x18006cf5e  lea     rcx, [rbp+arg_8]; this
0x18006cf62  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006cf67  mov     eax, ebx
0x18006cf69  add     rsp, 40h
0x18006cf6d  pop     r14
0x18006cf6f  pop     rdi
0x18006cf70  pop     rsi
0x18006cf71  pop     rbx
0x18006cf72  pop     rbp
0x18006cf73  retn
```
