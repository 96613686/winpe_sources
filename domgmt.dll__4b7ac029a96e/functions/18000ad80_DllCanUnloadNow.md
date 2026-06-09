# DllCanUnloadNow

- ea: `0x18000ad80`
- end: `0x18000ae77`
- name: `DllCanUnloadNow`
- size: `247`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000214c`
- `0x1800021b4`
- `0x180005964`
- `0x180009d10`
- `0x18000a2f0`
- `0x18000ad80`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ae6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ae6b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000adfe`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000adfe`

## string_xrefs

- `0x18000adc5`: `onecore\enduser\deliveryoptimization\management\dllmain.cpp`
- `0x18000ae64`: `DllCanUnloadNow`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  struct Microsoft::WRL::Details::ModuleBase *v1; // rdx
  bool v2; // r9
  HMODULE v3; // rcx
  __int64 (*ProcAddress)(void); // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( g_fMiProviderLoaded )
  {
    if ( dword_180018900 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_180018900);
      if ( dword_180018900 == -1 )
      {
        v3 = (HMODULE)*((_QWORD *)GetDllForwarder() + 1);
        if ( v3 )
          ProcAddress = GetProcAddress(v3, "DllCanUnloadNow");
        else
          ProcAddress = 0;
        qword_180018908 = ProcAddress;
        Init_thread_footer(&dword_180018900);
      }
    }
    if ( qword_180018908 )
    {
      return qword_180018908();
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39,
        (int)"onecore\\enduser\\deliveryoptimization\\management\\dllmain.cpp",
        (const char *)0x8000FFFFLL);
      return -2147418113;
    }
  }
  else
  {
    InitOnceExecuteOnce(
      &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
      (PINIT_ONCE_FN)`Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_180018928 = 1;
    return !Microsoft::WRL::Details::TerminateMap(
              (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
              v1,
              0,
              v2);
  }
}

```

## disassembly

```asm
0x18000ad80  sub     rsp, 28h
0x18000ad84  cmp     cs:?g_fMiProviderLoaded@@3_NA, 0; bool g_fMiProviderLoaded
0x18000ad8b  jz      short loc_18000ADEA
0x18000ad8d  mov     ecx, cs:_tls_index
0x18000ad93  mov     rax, gs:58h
0x18000ad9c  mov     edx, 4
0x18000ada1  mov     rax, [rax+rcx*8]
0x18000ada5  mov     eax, [rdx+rax]
0x18000ada8  cmp     cs:dword_180018900, eax
0x18000adae  jg      loc_18000AE3D
0x18000adb4  mov     rax, cs:qword_180018908
0x18000adbb  test    rax, rax
0x18000adbe  jnz     short loc_18000ADE1
0x18000adc0  mov     rcx, [rsp+28h]; this
0x18000adc5  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\deliveryoptimization"...
0x18000adcc  mov     r9d, 8000FFFFh; char *
0x18000add2  lea     edx, [rax+39h]; void *
0x18000add5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000adda  mov     eax, 8000FFFFh
0x18000addf  jmp     short loc_18000AE20
0x18000ade1  add     rsp, 28h
0x18000ade5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000adea  xor     r9d, r9d; Context
0x18000aded  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@45@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000adf4  xor     r8d, r8d; Parameter
0x18000adf7  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000adfe  call    cs:__imp_InitOnceExecuteOnce
0x18000ae04  xor     r8d, r8d; unsigned __int16 *
0x18000ae07  mov     cs:byte_180018928, 1
0x18000ae0e  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000ae15  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18000ae1a  movzx   eax, al
0x18000ae1d  xor     eax, 1
0x18000ae20  add     rsp, 28h
0x18000ae24  retn
0x18000ae25  lea     rcx, dword_180018900
0x18000ae2c  mov     cs:qword_180018908, rax
0x18000ae33  call    _Init_thread_footer
0x18000ae38  jmp     loc_18000ADB4
0x18000ae3d  lea     rcx, dword_180018900
0x18000ae44  call    _Init_thread_header
0x18000ae49  cmp     cs:dword_180018900, 0FFFFFFFFh
0x18000ae50  jnz     loc_18000ADB4
0x18000ae56  call    ?GetDllForwarder@@YAAEAUDllForwarder@@XZ; GetDllForwarder(void)
0x18000ae5b  mov     rcx, [rax+8]; hModule
0x18000ae5f  test    rcx, rcx
0x18000ae62  jz      short loc_18000AE73
0x18000ae64  lea     rdx, aDllcanunloadno_0; "DllCanUnloadNow"
0x18000ae6b  call    cs:__imp_GetProcAddress
0x18000ae71  jmp     short loc_18000AE25
0x18000ae73  xor     eax, eax
0x18000ae75  jmp     short loc_18000AE25
```
