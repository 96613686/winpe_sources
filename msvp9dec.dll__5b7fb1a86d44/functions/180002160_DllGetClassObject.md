# DllGetClassObject

- ea: `0x180002160`
- end: `0x180002384`
- name: `DllGetClassObject`
- size: `548`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001870`
- `0x180002160`
- `0x180004280`
- `0x180004778`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180002277`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180002277`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800021f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002329`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800021f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002329`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022f4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800021b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800022e4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800021b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800022e4`

## string_xrefs

- `0x180002210`: `DllGetClassObject`
- `0x18000233f`: `DllGetClassObject`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int v4; // edi
  int v5; // esi
  struct CallStackTracing *v6; // rbx
  CallStackContext *v7; // rdi
  DWORD v8; // ebp
  CallStackContext *v9; // rax
  struct CallStackTracing *v10; // rcx
  __int64 v11; // rax
  HRESULT result; // eax
  int v13; // edx
  __int64 v14; // r8
  HRESULT v15; // edi
  struct CallStackTracing *v16; // rbx
  CallStackContext *v17; // rbp
  DWORD LastError; // r14d
  CallStackContext *Value; // rax
  struct CallStackTracing *v20; // rcx
  __int64 v21; // rax

  v4 = (int)riid;
  v5 = (int)rclsid;
  if ( ppv )
  {
    *ppv = 0;
    InitOnceExecuteOnce(
      &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
      `Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_18000ADF8 = 1;
    result = Microsoft::WRL::Details::GetClassObject<1>(
               (int)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
               v13,
               v5,
               v4,
               ppv);
    v15 = result;
    if ( result < 0 )
    {
      v16 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (struct CallStackTracing *)&qword_18000A4C0;
        CallStackTracing::s_wpInstance = (struct CallStackTracing *)&qword_18000A4C0;
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v17 = (struct CallStackTracing *)((char *)v16 + 208);
        LastError = GetLastError();
        Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v16 + 3));
        if ( Value )
        {
          v17 = Value;
        }
        else if ( !GetLastError() )
        {
          v20 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v20 = (struct CallStackTracing *)&qword_18000A4C0;
            CallStackTracing::s_wpInstance = (struct CallStackTracing *)&qword_18000A4C0;
          }
          v21 = (**(__int64 (__fastcall ***)(struct CallStackTracing *))v20)(v20);
          if ( v21 )
            v17 = (CallStackContext *)v21;
        }
        SetLastError(LastError);
        if ( *((_DWORD *)v17 + 499) != v15 )
          CallStackContext::TraceFailure(v17, "DllGetClassObject", 185, v15);
      }
      if ( g_wppLevels )
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v14, 0, v15);
      return v15;
    }
  }
  else
  {
    v6 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (struct CallStackTracing *)&qword_18000A4C0;
      CallStackTracing::s_wpInstance = (struct CallStackTracing *)&qword_18000A4C0;
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v7 = (struct CallStackTracing *)((char *)v6 + 208);
      v8 = GetLastError();
      v9 = (CallStackContext *)TlsGetValue(*((_DWORD *)v6 + 3));
      if ( v9 )
      {
        v7 = v9;
      }
      else if ( !GetLastError() )
      {
        v10 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v10 = (struct CallStackTracing *)&qword_18000A4C0;
          CallStackTracing::s_wpInstance = (struct CallStackTracing *)&qword_18000A4C0;
        }
        v11 = (**(__int64 (__fastcall ***)(struct CallStackTracing *))v10)(v10);
        if ( v11 )
          v7 = (CallStackContext *)v11;
      }
      SetLastError(v8);
      if ( *((_DWORD *)v7 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v7, "DllGetClassObject", 180, -2147467261);
    }
    if ( g_wppLevels )
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, ppv, 0, -2147467261);
    return -2147467261;
  }
  return result;
}

```

## disassembly

```asm
0x180002160  push    rbx
0x180002162  push    rbp
0x180002163  push    rsi
0x180002164  push    rdi
0x180002165  sub     rsp, 38h
0x180002169  mov     rbx, r8
0x18000216c  mov     rdi, rdx
0x18000216f  mov     rsi, rcx
0x180002172  test    r8, r8
0x180002175  jnz     loc_18000225C
0x18000217b  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180002182  lea     rsi, qword_18000A4C0
0x180002189  test    rbx, rbx
0x18000218c  jnz     short loc_180002198
0x18000218e  mov     rbx, rsi
0x180002191  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180002198  cmp     byte ptr [rbx+8], 0
0x18000219c  jz      loc_180002225
0x1800021a2  lea     rdi, [rbx+0D0h]
0x1800021a9  call    cs:__imp_GetLastError
0x1800021af  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x1800021b2  mov     ebp, eax
0x1800021b4  call    cs:__imp_TlsGetValue
0x1800021ba  test    rax, rax
0x1800021bd  jz      short loc_1800021C4
0x1800021bf  mov     rdi, rax
0x1800021c2  jmp     short loc_1800021F6
0x1800021c4  call    cs:__imp_GetLastError
0x1800021ca  test    eax, eax
0x1800021cc  jnz     short loc_1800021F6
0x1800021ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800021d5  test    rcx, rcx
0x1800021d8  jnz     short loc_1800021E4
0x1800021da  mov     rcx, rsi
0x1800021dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800021e4  mov     rax, [rcx]
0x1800021e7  mov     rax, [rax]
0x1800021ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021ef  test    rax, rax
0x1800021f2  cmovnz  rdi, rax
0x1800021f6  mov     ecx, ebp; dwErrCode
0x1800021f8  call    cs:__imp_SetLastError
0x1800021fe  cmp     dword ptr [rdi+7CCh], 80004003h
0x180002208  jz      short loc_180002225
0x18000220a  mov     r9d, 80004003h; int
0x180002210  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x180002217  mov     r8d, 0B4h; int
0x18000221d  mov     rcx, rdi; this
0x180002220  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180002225  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000222c  jb      short loc_18000224E
0x18000222e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002235  mov     edx, 0Fh
0x18000223a  xor     r9d, r9d
0x18000223d  mov     dword ptr [rsp+58h+Ptr], 80004003h
0x180002245  mov     rcx, [rcx+10h]
0x180002249  call    WPP_SF_qd
0x18000224e  mov     eax, 80004003h
0x180002253  add     rsp, 38h
0x180002257  pop     rdi
0x180002258  pop     rsi
0x180002259  pop     rbp
0x18000225a  pop     rbx
0x18000225b  retn
0x18000225c  mov     qword ptr [r8], 0
0x180002263  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@45@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000226a  xor     r8d, r8d; Parameter
0x18000226d  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180002274  xor     r9d, r9d; Context
0x180002277  call    cs:__imp_InitOnceExecuteOnce
0x18000227d  mov     r9, rdi; int
0x180002280  mov     cs:byte_18000ADF8, 1
0x180002287  mov     r8, rsi; int
0x18000228a  mov     [rsp+58h+Ptr], rbx; Ptr
0x18000228f  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; int
0x180002296  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x18000229b  mov     edi, eax
0x18000229d  test    eax, eax
0x18000229f  jns     loc_18000237B
0x1800022a5  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800022ac  lea     rsi, qword_18000A4C0
0x1800022b3  test    rbx, rbx
0x1800022b6  jnz     short loc_1800022C2
0x1800022b8  mov     rbx, rsi
0x1800022bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800022c2  cmp     byte ptr [rbx+8], 0
0x1800022c6  jz      loc_180002354
0x1800022cc  lea     rbp, [rbx+0D0h]
0x1800022d3  mov     [rsp+58h+arg_0], r14
0x1800022d8  call    cs:__imp_GetLastError
0x1800022de  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x1800022e1  mov     r14d, eax
0x1800022e4  call    cs:__imp_TlsGetValue
0x1800022ea  test    rax, rax
0x1800022ed  jz      short loc_1800022F4
0x1800022ef  mov     rbp, rax
0x1800022f2  jmp     short loc_180002326
0x1800022f4  call    cs:__imp_GetLastError
0x1800022fa  test    eax, eax
0x1800022fc  jnz     short loc_180002326
0x1800022fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180002305  test    rcx, rcx
0x180002308  jnz     short loc_180002314
0x18000230a  mov     rcx, rsi
0x18000230d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180002314  mov     rax, [rcx]
0x180002317  mov     rax, [rax]
0x18000231a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000231f  test    rax, rax
0x180002322  cmovnz  rbp, rax
0x180002326  mov     ecx, r14d; dwErrCode
0x180002329  call    cs:__imp_SetLastError
0x18000232f  mov     r14, [rsp+58h+arg_0]
0x180002334  cmp     [rbp+7CCh], edi
0x18000233a  jz      short loc_180002354
0x18000233c  mov     r9d, edi; int
0x18000233f  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x180002346  mov     r8d, 0B9h; int
0x18000234c  mov     rcx, rbp; this
0x18000234f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180002354  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000235b  jb      short loc_180002379
0x18000235d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002364  mov     edx, 10h
0x180002369  xor     r9d, r9d
0x18000236c  mov     dword ptr [rsp+58h+Ptr], edi
0x180002370  mov     rcx, [rcx+10h]
0x180002374  call    WPP_SF_qd
0x180002379  mov     eax, edi
0x18000237b  add     rsp, 38h
0x18000237f  pop     rdi
0x180002380  pop     rsi
0x180002381  pop     rbp
0x180002382  pop     rbx
0x180002383  retn
```
