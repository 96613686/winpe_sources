# DAS::Dispatcher::Dispatch::DestroyProviderServices(void)

- ea: `0x1800484e4`
- end: `0x180048633`
- name: `?DestroyProviderServices@Dispatch@Dispatcher@DAS@@SAJXZ`
- size: `335`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800436e4`

## callees

- `0x18001958c`
- `0x18001a268`
- `0x18002a948`
- `0x18002aa34`
- `0x18003c9f8`
- `0x180047624`
- `0x180047a84`
- `0x180047b58`
- `0x180047c2c`
- `0x1800484e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004853c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004854f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004853c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004854f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180048579`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180048579`

## string_xrefs

- `0x18004858b`: `onecore\base\devices\association\service\lib\dispatcher.cpp`
- `0x1800485f5`: `onecore\base\devices\association\service\lib\dispatcher.cpp`
- `0x1800485ce`: `DestroyProviderServices`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 DAS::Dispatcher::Dispatch::DestroyProviderServices(void)
{
  char *v0; // r14
  HANDLE CurrentProcess; // rdi
  void *v2; // rbx
  HANDLE v3; // rax
  const char *v4; // r9
  unsigned int LastError; // ebx
  const char *v6; // r9
  __int64 result; // rax
  __int64 v8; // rax
  int v9; // ebx
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-98h]
  _QWORD v11[2]; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v12[16]; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v13[88]; // [rsp+60h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  __int64 v15; // [rsp+C0h] [rbp+8h] BYREF

  v15 = -1;
  try
  {
    v0 = (char *)operator new(0x18u);
    *((_DWORD *)v0 + 2) = 1;
    *((_DWORD *)v0 + 3) = 1;
    *(_QWORD *)v0 = off_180083798;
    *((_QWORD *)v0 + 2) = -1;
    v11[0] = v0 + 16;
    v11[1] = v0;
    DAS::Dispatcher::Dispatch::DestroyProviderServices_::_3_::Args::_Args(&v15);
    CurrentProcess = GetCurrentProcess();
    v2 = *(void **)g_providerManager;
    v3 = GetCurrentProcess();
    if ( DuplicateHandle(v3, v2, CurrentProcess, (LPHANDLE)v0 + 2, 2u, 0, 0) )
    {
      v8 = lambda_c98e743f1264db8972e0ad7239288a61_::_lambda_c98e743f1264db8972e0ad7239288a61_(v12, v11);
      std::function_long___cdecl_void__::function_long___cdecl_void____lambda_c98e743f1264db8972e0ad7239288a61__0_(
        v13,
        v8);
      v9 = DAS::Dispatcher::Dispatch::DispatchThread((__int64)L"DestroyProviderServices");
      lambda_c98e743f1264db8972e0ad7239288a61_::__lambda_c98e743f1264db8972e0ad7239288a61_(v12);
      if ( v9 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B0,
          (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\dispatcher.cpp",
          (const char *)(unsigned int)v9,
          dwDesiredAccess);
      if ( v0 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v0);
      result = (unsigned int)v9;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2A8,
                    (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\dispatcher.cpp",
                    v4);
      if ( v0 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v0);
      result = LastError;
    }
  }
  catch ( ... )
  {
    LODWORD(v15) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x2B2,
                     (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\dispatcher.cpp",
                     v6);
    return (unsigned int)v15;
  }
  return result;
}

```

## disassembly

```asm
0x1800484e4  mov     rax, rsp
0x1800484e7  mov     [rax+18h], rbx
0x1800484eb  push    rsi
0x1800484ec  push    rdi
0x1800484ed  push    r14
0x1800484ef  sub     rsp, 0A0h
0x1800484f6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800484fa  mov     [rax+8], rbx
0x1800484fe  lea     ecx, [rbx+19h]; Size
0x180048501  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180048506  mov     r14, rax
0x180048509  lea     eax, [rbx+2]
0x18004850c  mov     [r14+8], eax
0x180048510  mov     [r14+0Ch], eax
0x180048514  lea     rax, off_180083798
0x18004851b  mov     [r14], rax
0x18004851e  lea     rsi, [r14+10h]
0x180048522  mov     [rsi], rbx
0x180048525  mov     [rsp+0B8h+var_78], rsi
0x18004852a  mov     [rsp+0B8h+var_70], r14
0x18004852f  lea     rcx, [rsp+0B8h+arg_0]
0x180048537  call    _DAS__Dispatcher__Dispatch__DestroyProviderServices____3___Args___Args
0x18004853c  call    cs:__imp_GetCurrentProcess
0x180048542  mov     rdi, rax
0x180048545  mov     rcx, cs:?g_providerManager@@3V?$unique_ptr@VProviderManager@ProviderManagement@DAS@@U?$default_delete@VProviderManager@ProviderManagement@DAS@@@std@@@std@@A; std::unique_ptr<DAS::ProviderManagement::ProviderManager> g_providerManager
0x18004854c  mov     rbx, [rcx]
0x18004854f  call    cs:__imp_GetCurrentProcess
0x180048555  mov     [rsp+0B8h+dwOptions], 0; dwOptions
0x18004855d  mov     [rsp+0B8h+bInheritHandle], 0; bInheritHandle
0x180048565  mov     [rsp+0B8h+dwDesiredAccess], 2; int
0x18004856d  mov     r9, rsi; lpTargetHandle
0x180048570  mov     r8, rdi; hTargetProcessHandle
0x180048573  mov     rdx, rbx; hSourceHandle
0x180048576  mov     rcx, rax; hSourceProcessHandle
0x180048579  call    cs:__imp_DuplicateHandle
0x18004857f  test    eax, eax
0x180048581  jnz     short loc_1800485AF
0x180048583  mov     rcx, [rsp+0B8h]; this
0x18004858b  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\association\\se"...
0x180048592  mov     edx, 2A8h; void *
0x180048597  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004859c  mov     ebx, eax
0x18004859e  test    r14, r14
0x1800485a1  jz      short loc_1800485AB
0x1800485a3  mov     rcx, r14; this
0x1800485a6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800485ab  mov     eax, ebx
0x1800485ad  jmp     short loc_18004861E
0x1800485af  lea     rdx, [rsp+0B8h+var_78]
0x1800485b4  lea     rcx, [rsp+0B8h+var_68]
0x1800485b9  call    _lambda_c98e743f1264db8972e0ad7239288a61____lambda_c98e743f1264db8972e0ad7239288a61_
0x1800485be  mov     rdx, rax
0x1800485c1  lea     rcx, [rsp+0B8h+var_58]
0x1800485c6  call    std__function_long___cdecl_void____function_long___cdecl_void____lambda_c98e743f1264db8972e0ad7239288a61__0_
0x1800485cb  mov     rdx, rax
0x1800485ce  lea     rcx, aDestroyprovide; "DestroyProviderServices"
0x1800485d5  call    ?DispatchThread@Dispatch@Dispatcher@DAS@@CAJPEBGV?$function@$$A6AJXZ@std@@KK@Z; DAS::Dispatcher::Dispatch::DispatchThread(ushort const *,std::function<long (void)>,ulong,ulong)
0x1800485da  mov     ebx, eax
0x1800485dc  lea     rcx, [rsp+0B8h+var_68]
0x1800485e1  call    _lambda_c98e743f1264db8972e0ad7239288a61_____lambda_c98e743f1264db8972e0ad7239288a61_
0x1800485e6  test    ebx, ebx
0x1800485e8  jns     short loc_180048606
0x1800485ea  mov     rcx, [rsp+0B8h]; this
0x1800485f2  mov     r9d, ebx; char *
0x1800485f5  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\association\\se"...
0x1800485fc  mov     edx, 2B0h; void *
0x180048601  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048606  test    r14, r14
0x180048609  jz      short loc_180048613
0x18004860b  mov     rcx, r14; this
0x18004860e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180048613  mov     eax, ebx
0x180048615  jmp     short loc_18004861E
0x180048617  mov     eax, dword ptr [rsp+0B8h+arg_0]
0x18004861e  mov     rbx, [rsp+0B8h+arg_10]
0x180048626  add     rsp, 0A0h
0x18004862d  pop     r14
0x18004862f  pop     rdi
0x180048630  pop     rsi
0x180048631  retn
```
