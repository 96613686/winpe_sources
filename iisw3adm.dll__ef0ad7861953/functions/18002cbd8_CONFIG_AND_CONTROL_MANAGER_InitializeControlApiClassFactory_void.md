# CONFIG_AND_CONTROL_MANAGER::InitializeControlApiClassFactory(void)

- ea: `0x18002cbd8`
- end: `0x18002cdb8`
- name: `?InitializeControlApiClassFactory@CONFIG_AND_CONTROL_MANAGER@@AEAAJXZ`
- size: `480`
- prototype: `__int64 __fastcall(CONFIG_AND_CONTROL_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002ca6c`

## callees

- `0x180001234`
- `0x18002cbd8`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18002cd47`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18002cd47`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18002cc1c`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18002cc1c`
- `iisutil!PuDbgPrint` at `0x18002cd1e`
- `iisutil!PuDbgPrint` at `0x18002cd1e`
- `iisutil!PuDbgPrintError` at `0x18002cc70`
- `iisutil!PuDbgPrintError` at `0x18002cd87`
- `iisutil!PuDbgPrintError` at `0x18002cc70`
- `iisutil!PuDbgPrintError` at `0x18002cd87`

## string_xrefs

- `0x18002cc69`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_and_control_manager.cxx`
- `0x18002cd17`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_and_control_manager.cxx`
- `0x18002cd80`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_and_control_manager.cxx`
- `0x18002cc45`: `Initializing COM security failed\n`
- `0x18002cc62`: `CONFIG_AND_CONTROL_MANAGER::InitializeControlApiClassFactory`
- `0x18002cd05`: `CONFIG_AND_CONTROL_MANAGER::InitializeControlApiClassFactory`
- `0x18002cd6f`: `CONFIG_AND_CONTROL_MANAGER::InitializeControlApiClassFactory`

## pseudocode

```c
__int64 __fastcall CONFIG_AND_CONTROL_MANAGER::InitializeControlApiClassFactory(CONFIG_AND_CONTROL_MANAGER *this)
{
  HRESULT v2; // ebx
  _DWORD *v3; // rax

  v2 = CoInitializeSecurity(&CLSID_W3Control, -1, 0, 0, 6u, 2u, 0, 0x3008u, 0);
  if ( (int)(v2 + 0x80000000) < 0 || v2 == -2147417831 )
  {
    v3 = operator new(0x10u);
    if ( v3 )
    {
      v3[3] = 1;
      *(_QWORD *)v3 = &CONTROL_API_CLASS_FACTORY::`vftable';
      v3[2] = 1178812739;
    }
    *((_QWORD *)this + 45) = v3;
    if ( v3 )
    {
      if ( (g_dwDebugFlags & 0x30000) != 0 && (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_and_control_manager.cxx",
          484,
          "CONFIG_AND_CONTROL_MANAGER::InitializeControlApiClassFactory",
          "Registering control api class factory\n");
      v2 = CoRegisterClassObject(&CLSID_W3Control, *((LPUNKNOWN *)this + 45), 4u, 1u, (LPDWORD)this + 93);
      if ( v2 < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_and_control_manager.cxx",
            502,
            "CONFIG_AND_CONTROL_MANAGER::InitializeControlApiClassFactory",
            v2,
            "Registering class object failed\n");
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 45) + 16LL))(*((_QWORD *)this + 45));
        *((_QWORD *)this + 45) = 0;
      }
    }
    else
    {
      v2 = -2147024888;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_and_control_manager.cxx",
          469,
          "CONFIG_AND_CONTROL_MANAGER::InitializeControlApiClassFactory",
          -2147024888,
          "Allocating CONTROL_API_CLASS_FACTORY failed\n");
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_and_control_manager.cxx",
      447,
      "CONFIG_AND_CONTROL_MANAGER::InitializeControlApiClassFactory",
      v2,
      "Initializing COM security failed\n");
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002cbd8  mov     rax, rsp
0x18002cbdb  mov     [rax+8], rbx
0x18002cbdf  push    rdi
0x18002cbe0  sub     rsp, 50h
0x18002cbe4  mov     qword ptr [rax-18h], 0
0x18002cbec  mov     rdi, rcx
0x18002cbef  mov     dword ptr [rax-20h], 3008h
0x18002cbf6  lea     rcx, CLSID_W3Control; pSecDesc
0x18002cbfd  mov     qword ptr [rax-28h], 0
0x18002cc05  xor     r9d, r9d; pReserved1
0x18002cc08  mov     dword ptr [rax-30h], 2
0x18002cc0f  xor     r8d, r8d; asAuthSvc
0x18002cc12  or      edx, 0FFFFFFFFh; cAuthSvc
0x18002cc15  mov     dword ptr [rax-38h], 6
0x18002cc1c  call    cs:__imp_CoInitializeSecurity
0x18002cc22  mov     ebx, eax
0x18002cc24  mov     eax, 80000000h
0x18002cc29  lea     ecx, [rbx+rax]
0x18002cc2c  test    eax, ecx
0x18002cc2e  jnz     short loc_18002CC7B
0x18002cc30  cmp     ebx, 80010119h
0x18002cc36  jz      short loc_18002CC7B
0x18002cc38  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002cc3f  jz      loc_18002CDAB
0x18002cc45  lea     rax, aInitializingCo; "Initializing COM security failed\n"
0x18002cc4c  mov     r8d, 1BFh
0x18002cc52  mov     [rsp+58h+var_30], rax
0x18002cc57  mov     dword ptr [rsp+58h+lpdwRegister], ebx
0x18002cc5b  mov     rcx, cs:g_pDebug
0x18002cc62  lea     r9, aConfigAndContr_2; "CONFIG_AND_CONTROL_MANAGER::InitializeC"...
0x18002cc69  lea     rdx, aServercommonIn_43; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002cc70  call    cs:__imp_PuDbgPrintError
0x18002cc76  jmp     loc_18002CDAB
0x18002cc7b  mov     ecx, 10h; Size
0x18002cc80  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002cc85  mov     ebx, 1
0x18002cc8a  test    rax, rax
0x18002cc8d  jz      short loc_18002CCA3
0x18002cc8f  lea     rcx, ??_7CONTROL_API_CLASS_FACTORY@@6B@; const CONTROL_API_CLASS_FACTORY::`vftable'
0x18002cc96  mov     [rax+0Ch], ebx
0x18002cc99  mov     [rax], rcx
0x18002cc9c  mov     dword ptr [rax+8], 46434143h
0x18002cca3  mov     [rdi+168h], rax
0x18002ccaa  test    rax, rax
0x18002ccad  jnz     short loc_18002CCE0
0x18002ccaf  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002ccb6  mov     ebx, 80070008h
0x18002ccbb  jz      loc_18002CDAB
0x18002ccc1  lea     rax, aAllocatingCont; "Allocating CONTROL_API_CLASS_FACTORY fa"...
0x18002ccc8  mov     r8d, 1D5h
0x18002ccce  mov     [rsp+58h+var_30], rax
0x18002ccd3  mov     dword ptr [rsp+58h+lpdwRegister], 80070008h
0x18002ccdb  jmp     loc_18002CC5B
0x18002cce0  mov     eax, cs:g_dwDebugFlags
0x18002cce6  test    eax, 30000h
0x18002cceb  setnz   cl
0x18002ccee  test    al, 3
0x18002ccf0  setnz   al
0x18002ccf3  test    al, cl
0x18002ccf5  jz      short loc_18002CD24
0x18002ccf7  mov     rcx, cs:g_pDebug
0x18002ccfe  lea     rax, aRegisteringCon; "Registering control api class factory\n"
0x18002cd05  lea     r9, aConfigAndContr_2; "CONFIG_AND_CONTROL_MANAGER::InitializeC"...
0x18002cd0c  mov     [rsp+58h+lpdwRegister], rax
0x18002cd11  mov     r8d, 1E4h
0x18002cd17  lea     rdx, aServercommonIn_43; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002cd1e  call    cs:__imp_PuDbgPrint
0x18002cd24  mov     rdx, [rdi+168h]; pUnk
0x18002cd2b  lea     rax, [rdi+174h]
0x18002cd32  mov     r9d, ebx; flags
0x18002cd35  mov     [rsp+58h+lpdwRegister], rax; lpdwRegister
0x18002cd3a  mov     r8d, 4; dwClsContext
0x18002cd40  lea     rcx, CLSID_W3Control; rclsid
0x18002cd47  call    cs:__imp_CoRegisterClassObject
0x18002cd4d  mov     ebx, eax
0x18002cd4f  test    eax, eax
0x18002cd51  jns     short loc_18002CDAB
0x18002cd53  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002cd5a  jz      short loc_18002CD8D
0x18002cd5c  mov     rcx, cs:g_pDebug
0x18002cd63  lea     rax, aRegisteringCla; "Registering class object failed\n"
0x18002cd6a  mov     [rsp+58h+var_30], rax
0x18002cd6f  lea     r9, aConfigAndContr_2; "CONFIG_AND_CONTROL_MANAGER::InitializeC"...
0x18002cd76  mov     r8d, 1F6h
0x18002cd7c  mov     dword ptr [rsp+58h+lpdwRegister], ebx
0x18002cd80  lea     rdx, aServercommonIn_43; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002cd87  call    cs:__imp_PuDbgPrintError
0x18002cd8d  mov     rcx, [rdi+168h]
0x18002cd94  mov     rax, [rcx]
0x18002cd97  mov     rax, [rax+10h]
0x18002cd9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cda0  mov     qword ptr [rdi+168h], 0
0x18002cdab  mov     eax, ebx
0x18002cdad  mov     rbx, [rsp+58h+arg_0]
0x18002cdb2  add     rsp, 50h
0x18002cdb6  pop     rdi
0x18002cdb7  retn
```
