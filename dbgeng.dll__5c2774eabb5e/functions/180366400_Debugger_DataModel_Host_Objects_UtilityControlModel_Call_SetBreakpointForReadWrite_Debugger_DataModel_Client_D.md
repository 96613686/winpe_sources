# Debugger::DataModel::Host::Objects::UtilityControlModel::Call_SetBreakpointForReadWrite(Debugger::DataModel::Client::Details::ObjectImpl<0> const &,unsigned __int64,Debugger::DataModel::Client::Details::ObjectImpl<0> *,Debugger::DataModel::Client::Details::ObjectImpl<0> *,Debugger::DataModel::Client::Metadata *)

- ea: `0x180366400`
- end: `0x18036689a`
- name: `?Call_SetBreakpointForReadWrite@UtilityControlModel@Objects@Host@DataModel@Debugger@@AEAAJAEBV?$ObjectImpl@$0A@@Details@Client@45@_KPEAV67845@2PEAVMetadata@845@@Z`
- size: `1178`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, struct Breakpoint *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x180075b88`
- `0x180077c1c`
- `0x180077c44`
- `0x1800937ac`
- `0x1800bcd74`
- `0x1800c0838`
- `0x1800c4868`
- `0x1800c4a7c`
- `0x1800dbedc`
- `0x1800efd50`
- `0x1801899c4`
- `0x18018c0a8`
- `0x1802f62b4`
- `0x1802f8f38`
- `0x180366400`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180366518`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180366537`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180366556`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180366575`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180366594`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1803665b3`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1803665d2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1803665ed`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180366608`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180366623`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180366518`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180366537`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180366556`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180366575`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180366594`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1803665b3`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1803665d2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1803665ed`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180366608`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180366623`

## string_xrefs

- `0x18036652c`: `Hardware Read`
- `0x1803665a8`: `Hardware Read/Write`
- `0x18036656a`: `Hardware Write`
- `0x180366633`: `Invalid second argument passed to method 'SetBreakpointForReadWrite'`
- `0x1803666a7`: `Invalid argument passed to method 'SetBreakpointForReadWrite'`
- `0x180366470`: `Incorrect number of arguments to method 'SetBreakpointForReadWrite'`
- `0x1803664b5`: `Invalid first argument passed to method 'SetBreakpointForReadWrite'`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Debugger::DataModel::Host::Objects::UtilityControlModel::Call_SetBreakpointForReadWrite(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        _QWORD *a4,
        __int64 a5,
        wchar_t **a6)
{
  wchar_t **v8; // rcx
  const wchar_t *v9; // rdx
  int v10; // ebx
  unsigned int v11; // r15d
  const wchar_t *v12; // rdx
  unsigned int v13; // ebx
  Debugger::DataModel::Host::DataModelHostContext *v14; // r14
  struct MachineInfo *Machine; // rax
  int v16; // eax
  struct Breakpoint *v17; // rsi
  Debugger::DataModel::Client *v18; // rcx
  struct IDataModelManager *Manager; // rax
  wchar_t **v20; // rsi
  __int128 *v22; // [rsp+38h] [rbp-59h] BYREF
  wchar_t *String1[2]; // [rsp+40h] [rbp-51h] BYREF
  __int64 v24; // [rsp+50h] [rbp-41h]
  Debugger::DataModel::Host::DataModelHostContext *v25; // [rsp+58h] [rbp-39h] BYREF
  __int64 v26; // [rsp+60h] [rbp-31h] BYREF
  _QWORD v27[3]; // [rsp+68h] [rbp-29h] BYREF
  __int128 *v28; // [rsp+80h] [rbp-11h] BYREF
  __int128 v29; // [rsp+88h] [rbp-9h] BYREF
  __int64 v30; // [rsp+98h] [rbp+7h]
  __int128 v31; // [rsp+A0h] [rbp+Fh] BYREF
  __int64 v32; // [rsp+B0h] [rbp+1Fh]
  __int64 v33; // [rsp+B8h] [rbp+27h]
  __int64 v34; // [rsp+F8h] [rbp+67h] BYREF

  v33 = -2;
  v22 = 0;
  Debugger::DataModel::Client::Details::ObjectImpl<0>::operator=(a5, &v22);
  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v22);
  v8 = a6;
  if ( a6 )
  {
    a6 = 0;
    Microsoft::WRL::ComPtr<IDebugHostSymbol>::operator=(v8, &a6);
    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&a6);
  }
  if ( a3 )
  {
    v31 = 0;
    v32 = 0;
    if ( (*(int (__fastcall **)(_QWORD, __int64, __int128 *))(*(_QWORD *)*a4 + 48LL))(*a4, 20, &v31) < 0 )
    {
      v9 = L"Invalid first argument passed to method 'SetBreakpointForReadWrite'";
      goto LABEL_5;
    }
    v11 = 1;
    v28 = &v31;
    if ( a3 <= 1 )
    {
      v13 = 2;
    }
    else
    {
      *(_OWORD *)String1 = 0;
      v24 = 0;
      v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, wchar_t **))(*(_QWORD *)a4[1] + 48LL))(a4[1], 8, String1);
      if ( v10 < 0 )
      {
LABEL_42:
        std::unique_ptr<tagVARIANT,VARIANTDeleter>::~unique_ptr<tagVARIANT,VARIANTDeleter>(&v28);
        return (unsigned int)v10;
      }
      a6 = String1;
      if ( _wcsicmp(String1[1], L"R") && _wcsicmp(String1[1], L"Hardware Read") )
      {
        if ( _wcsicmp(String1[1], L"W") && _wcsicmp(String1[1], L"Hardware Write") )
        {
          if ( _wcsicmp(String1[1], L"RW") && _wcsicmp(String1[1], L"Hardware Read/Write") )
          {
            if ( _wcsicmp(String1[1], L"E") && _wcsicmp(String1[1], L"Hardware Execute") )
            {
              if ( _wcsicmp(String1[1], L"IO") && _wcsicmp(String1[1], L"Hardware I/O") )
              {
                v12 = L"Invalid second argument passed to method 'SetBreakpointForReadWrite'";
LABEL_21:
                v10 = -2147024809;
                Debugger::DataModel::Client::Details::ObjectImpl<0>::CreateError(2147942487LL, v12, a5);
                std::unique_ptr<tagVARIANT,VARIANTDeleter>::~unique_ptr<tagVARIANT,VARIANTDeleter>(&a6);
                goto LABEL_42;
              }
              v13 = 8;
            }
            else
            {
              v13 = 4;
            }
          }
          else
          {
            v13 = 3;
          }
        }
        else
        {
          v13 = 2;
        }
      }
      else
      {
        v13 = 1;
      }
      if ( a3 == 3 )
      {
        v29 = 0;
        v30 = 0;
        if ( (*(int (__fastcall **)(_QWORD, __int64, __int128 *))(*(_QWORD *)a4[2] + 48LL))(a4[2], 3, &v29) < 0 )
        {
          v12 = L"Invalid argument passed to method 'SetBreakpointForReadWrite'";
          goto LABEL_21;
        }
        v22 = &v29;
        v11 = DWORD2(v29);
        std::unique_ptr<tagVARIANT,VARIANTDeleter>::~unique_ptr<tagVARIANT,VARIANTDeleter>(&v22);
      }
      std::unique_ptr<tagVARIANT,VARIANTDeleter>::~unique_ptr<tagVARIANT,VARIANTDeleter>(&a6);
    }
    v25 = 0;
    ((void (__fastcall *)(struct IDebugHost *, Debugger::DataModel::Host::DataModelHostContext **))Debugger::DataModel::Host::DataModelHost::s_pHostSingleton->lpVtbl->GetCurrentContext)(
      Debugger::DataModel::Host::DataModelHost::s_pHostSingleton,
      &v25);
    v14 = v25;
    Machine = Debugger::DataModel::Host::DataModelHostContext::GetMachine(v25);
    a6 = 0;
    v16 = AddBreakpoint(0, Machine, 1u, 0xFFFFFFFF, 0, (struct Breakpoint **)&a6);
    if ( v16 < 0 )
      goto LABEL_34;
    v27[0] = 8;
    v27[2] = 0;
    v27[1] = *((_QWORD *)&v31 + 1);
    ComputeFlatAddress((struct _ADDR *)v27, 0);
    v17 = (struct Breakpoint *)a6;
    v16 = Breakpoint::SetAddr(a6, v27, 1);
    if ( v16 < 0
      || (v16 = (*(__int64 (__fastcall **)(struct Breakpoint *, __int64))(*(_QWORD *)v17 + 56LL))(v17, 4), v16 < 0)
      || (v16 = (*(__int64 (__fastcall **)(struct Breakpoint *, _QWORD, _QWORD))(*(_QWORD *)v17 + 104LL))(v17, v11, v13),
          v16 < 0) )
    {
LABEL_34:
      v10 = v16;
    }
    else
    {
      a6 = 0;
      v26 = 0;
      Manager = Debugger::DataModel::Client::GetManager(v18);
      ((void (__fastcall *)(struct IDataModelManager *, const OLECHAR *, __int64 *))Manager->lpVtbl->AcquireNamedModel)(
        Manager,
        L"Debugger.Models.Breakpoint",
        &v26);
      Debugger::DataModel::Client::Details::ObjectImpl<0>::ObjectImpl<0>(&v22, v26);
      Debugger::DataModel::Client::Details::ObjectImpl<0>::CreateInstanceOf(&v22, v14, &a6);
      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v22);
      v34 = 0;
      v10 = Debugger::DataModel::Client::Details::ObjectImpl<0>::CreateIntrinsic<unsigned __int64>(
              *((_QWORD *)v17 + 51),
              &v34);
      if ( v10 >= 0 )
      {
        v20 = a6;
        v10 = (*((__int64 (__fastcall **)(wchar_t **, const wchar_t *, __int64, _QWORD))*a6 + 24))(
                a6,
                L"UniqueID",
                v34,
                0);
        if ( v10 >= 0 )
        {
          a6 = 0;
          Debugger::DataModel::Client::Details::ObjectImpl<0>::operator=(a5, v20);
        }
      }
      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v34);
      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&a6);
    }
    goto LABEL_42;
  }
  v9 = L"Incorrect number of arguments to method 'SetBreakpointForReadWrite'";
LABEL_5:
  v10 = -2147024809;
  Debugger::DataModel::Client::Details::ObjectImpl<0>::CreateError(2147942487LL, v9, a5);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180366400  mov     rax, rsp
0x180366403  push    rbp
0x180366404  push    r14
0x180366406  push    r15
0x180366408  lea     rbp, [rax-4Fh]
0x18036640c  sub     rsp, 0C0h
0x180366413  mov     [rbp+47h+var_20], 0FFFFFFFFFFFFFFFEh
0x18036641b  mov     [rax+8], rbx
0x18036641f  mov     [rax+10h], rsi
0x180366423  mov     r14, r9
0x180366426  mov     rsi, r8
0x180366429  mov     [rbp+47h+var_A0], 0
0x180366431  lea     rdx, [rbp+47h+var_A0]
0x180366435  mov     rcx, [rbp+47h+arg_20]
0x180366439  call    ??4?$ObjectImpl@$0A@@Details@Client@DataModel@Debugger@@QEAAAEAV01234@$$QEAV01234@@Z; Debugger::DataModel::Client::Details::ObjectImpl<0>::operator=(Debugger::DataModel::Client::Details::ObjectImpl<0> &&)
0x18036643e  lea     rcx, [rbp+47h+var_A0]
0x180366442  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x180366447  mov     rcx, [rbp+47h+arg_28]
0x18036644b  test    rcx, rcx
0x18036644e  jz      short loc_18036646A
0x180366450  mov     [rbp+47h+arg_28], 0
0x180366458  lea     rdx, [rbp+47h+arg_28]
0x18036645c  call    ??4?$ComPtr@UIDebugHostSymbol@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IDebugHostSymbol>::operator=(Microsoft::WRL::ComPtr<IDebugHostSymbol> &&)
0x180366461  lea     rcx, [rbp+47h+arg_28]
0x180366465  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x18036646a  cmp     rsi, 1
0x18036646e  jnb     short loc_18036648C
0x180366470  lea     rdx, aIncorrectNumbe_7; "Incorrect number of arguments to method"...
0x180366477  mov     r8, [rbp+47h+arg_20]
0x18036647b  mov     ebx, 80070057h
0x180366480  mov     ecx, ebx
0x180366482  call    ?CreateError@?$ObjectImpl@$0A@@Details@Client@DataModel@Debugger@@SAJJPEBGPEAV12345@@Z; Debugger::DataModel::Client::Details::ObjectImpl<0>::CreateError(long,ushort const *,Debugger::DataModel::Client::Details::ObjectImpl<0> *)
0x180366487  jmp     loc_18036687E
0x18036648c  xorps   xmm0, xmm0
0x18036648f  xor     eax, eax
0x180366491  movups  [rbp+47h+var_38], xmm0
0x180366495  mov     [rbp+47h+var_28], rax
0x180366499  mov     rcx, [r14]
0x18036649c  mov     rax, [rcx]
0x18036649f  mov     edx, 14h
0x1803664a4  lea     r8, [rbp+47h+var_38]
0x1803664a8  mov     rax, [rax+30h]
0x1803664ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803664b1  test    eax, eax
0x1803664b3  jns     short loc_1803664BE
0x1803664b5  lea     rdx, aInvalidFirstAr; "Invalid first argument passed to method"...
0x1803664bc  jmp     short loc_180366477
0x1803664be  mov     r15d, 1
0x1803664c4  lea     rax, [rbp+47h+var_38]
0x1803664c8  mov     [rbp+47h+var_58], rax
0x1803664cc  cmp     rsi, 1
0x1803664d0  jbe     loc_1803666D1
0x1803664d6  xorps   xmm0, xmm0
0x1803664d9  xor     eax, eax
0x1803664db  movups  xmmword ptr [rbp+47h+String1], xmm0
0x1803664df  mov     [rbp+47h+var_88], rax
0x1803664e3  mov     rcx, [r14+8]
0x1803664e7  mov     rax, [rcx]
0x1803664ea  lea     edx, [r15+7]
0x1803664ee  lea     r8, [rbp+47h+String1]
0x1803664f2  mov     rax, [rax+30h]
0x1803664f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803664fb  mov     ebx, eax
0x1803664fd  test    eax, eax
0x1803664ff  js      loc_180366875
0x180366505  lea     rax, [rbp+47h+String1]
0x180366509  mov     [rbp+47h+arg_28], rax
0x18036650d  lea     rdx, aR_0; "R"
0x180366514  mov     rcx, [rbp+47h+String1+8]; String1
0x180366518  call    cs:__imp__wcsicmp
0x18036651f  nop     dword ptr [rax+rax+00h]
0x180366524  test    eax, eax
0x180366526  jz      loc_180366675
0x18036652c  lea     rdx, aHardwareRead; "Hardware Read"
0x180366533  mov     rcx, [rbp+47h+String1+8]; String1
0x180366537  call    cs:__imp__wcsicmp
0x18036653e  nop     dword ptr [rax+rax+00h]
0x180366543  test    eax, eax
0x180366545  jz      loc_180366675
0x18036654b  lea     rdx, aW_2; "W"
0x180366552  mov     rcx, [rbp+47h+String1+8]; String1
0x180366556  call    cs:__imp__wcsicmp
0x18036655d  nop     dword ptr [rax+rax+00h]
0x180366562  test    eax, eax
0x180366564  jz      loc_18036666E
0x18036656a  lea     rdx, aHardwareWrite; "Hardware Write"
0x180366571  mov     rcx, [rbp+47h+String1+8]; String1
0x180366575  call    cs:__imp__wcsicmp
0x18036657c  nop     dword ptr [rax+rax+00h]
0x180366581  test    eax, eax
0x180366583  jz      loc_18036666E
0x180366589  lea     rdx, aRw; "RW"
0x180366590  mov     rcx, [rbp+47h+String1+8]; String1
0x180366594  call    cs:__imp__wcsicmp
0x18036659b  nop     dword ptr [rax+rax+00h]
0x1803665a0  test    eax, eax
0x1803665a2  jz      loc_180366667
0x1803665a8  lea     rdx, aHardwareReadWr; "Hardware Read/Write"
0x1803665af  mov     rcx, [rbp+47h+String1+8]; String1
0x1803665b3  call    cs:__imp__wcsicmp
0x1803665ba  nop     dword ptr [rax+rax+00h]
0x1803665bf  test    eax, eax
0x1803665c1  jz      loc_180366667
0x1803665c7  lea     rdx, aE; "E"
0x1803665ce  mov     rcx, [rbp+47h+String1+8]; String1
0x1803665d2  call    cs:__imp__wcsicmp
0x1803665d9  nop     dword ptr [rax+rax+00h]
0x1803665de  test    eax, eax
0x1803665e0  jz      short loc_180366660
0x1803665e2  lea     rdx, aHardwareExecut; "Hardware Execute"
0x1803665e9  mov     rcx, [rbp+47h+String1+8]; String1
0x1803665ed  call    cs:__imp__wcsicmp
0x1803665f4  nop     dword ptr [rax+rax+00h]
0x1803665f9  test    eax, eax
0x1803665fb  jz      short loc_180366660
0x1803665fd  lea     rdx, aIo; "IO"
0x180366604  mov     rcx, [rbp+47h+String1+8]; String1
0x180366608  call    cs:__imp__wcsicmp
0x18036660f  nop     dword ptr [rax+rax+00h]
0x180366614  test    eax, eax
0x180366616  jz      short loc_180366659
0x180366618  lea     rdx, aHardwareIO; "Hardware I/O"
0x18036661f  mov     rcx, [rbp+47h+String1+8]; String1
0x180366623  call    cs:__imp__wcsicmp
0x18036662a  nop     dword ptr [rax+rax+00h]
0x18036662f  test    eax, eax
0x180366631  jz      short loc_180366659
0x180366633  lea     rdx, aInvalidSecondA; "Invalid second argument passed to metho"...
0x18036663a  mov     r8, [rbp+47h+arg_20]
0x18036663e  mov     ebx, 80070057h
0x180366643  mov     ecx, ebx
0x180366645  call    ?CreateError@?$ObjectImpl@$0A@@Details@Client@DataModel@Debugger@@SAJJPEBGPEAV12345@@Z; Debugger::DataModel::Client::Details::ObjectImpl<0>::CreateError(long,ushort const *,Debugger::DataModel::Client::Details::ObjectImpl<0> *)
0x18036664a  nop
0x18036664b  lea     rcx, [rbp+47h+arg_28]
0x18036664f  call    ??1?$unique_ptr@UtagVARIANT@@UVARIANTDeleter@@@std@@QEAA@XZ; std::unique_ptr<tagVARIANT,VARIANTDeleter>::~unique_ptr<tagVARIANT,VARIANTDeleter>(void)
0x180366654  jmp     loc_180366875
0x180366659  mov     ebx, 8
0x18036665e  jmp     short loc_18036667A
0x180366660  mov     ebx, 4
0x180366665  jmp     short loc_18036667A
0x180366667  mov     ebx, 3
0x18036666c  jmp     short loc_18036667A
0x18036666e  mov     ebx, 2
0x180366673  jmp     short loc_18036667A
0x180366675  mov     ebx, 1
0x18036667a  cmp     rsi, 3
0x18036667e  jnz     short loc_1803666C6
0x180366680  xorps   xmm0, xmm0
0x180366683  xor     eax, eax
0x180366685  movups  [rbp+47h+var_50], xmm0
0x180366689  mov     [rbp+47h+var_40], rax
0x18036668d  mov     rcx, [r14+10h]
0x180366691  mov     rax, [rcx]
0x180366694  mov     edx, esi
0x180366696  lea     r8, [rbp+47h+var_50]
0x18036669a  mov     rax, [rax+30h]
0x18036669e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803666a3  test    eax, eax
0x1803666a5  jns     short loc_1803666B0
0x1803666a7  lea     rdx, aInvalidArgumen_1; "Invalid argument passed to method 'SetB"...
0x1803666ae  jmp     short loc_18036663A
0x1803666b0  lea     rax, [rbp+47h+var_50]
0x1803666b4  mov     [rbp+47h+var_A0], rax
0x1803666b8  mov     r15d, dword ptr [rbp+47h+var_50+8]
0x1803666bc  lea     rcx, [rbp+47h+var_A0]
0x1803666c0  call    ??1?$unique_ptr@UtagVARIANT@@UVARIANTDeleter@@@std@@QEAA@XZ; std::unique_ptr<tagVARIANT,VARIANTDeleter>::~unique_ptr<tagVARIANT,VARIANTDeleter>(void)
0x1803666c5  nop
0x1803666c6  lea     rcx, [rbp+47h+arg_28]
0x1803666ca  call    ??1?$unique_ptr@UtagVARIANT@@UVARIANTDeleter@@@std@@QEAA@XZ; std::unique_ptr<tagVARIANT,VARIANTDeleter>::~unique_ptr<tagVARIANT,VARIANTDeleter>(void)
0x1803666cf  jmp     short loc_1803666D6
0x1803666d1  mov     ebx, 2
0x1803666d6  mov     [rbp+47h+var_80], 0
0x1803666de  mov     rcx, cs:?s_pHostSingleton@DataModelHost@Host@DataModel@Debugger@@0PEAV1234@EA; Debugger::DataModel::Host::DataModelHost * Debugger::DataModel::Host::DataModelHost::s_pHostSingleton
0x1803666e5  mov     rax, [rcx]
0x1803666e8  lea     rdx, [rbp+47h+var_80]
0x1803666ec  mov     rax, [rax+20h]
0x1803666f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803666f5  mov     r14, [rbp+47h+var_80]
0x1803666f9  mov     rcx, r14; this
0x1803666fc  call    ?GetMachine@DataModelHostContext@Host@DataModel@Debugger@@QEBAPEAVMachineInfo@@XZ; Debugger::DataModel::Host::DataModelHostContext::GetMachine(void)
0x180366701  mov     [rbp+47h+arg_28], 0
0x180366709  lea     rcx, [rbp+47h+arg_28]
0x18036670d  mov     [rsp+0D0h+var_A8], rcx; struct Breakpoint **
0x180366712  mov     [rsp+0D0h+var_B0], 0; unsigned int
0x18036671a  or      r9d, 0FFFFFFFFh; unsigned int
0x18036671e  mov     r8d, 1; unsigned int
0x180366724  mov     rdx, rax; struct MachineInfo *
0x180366727  xor     ecx, ecx; struct DebugClient *
0x180366729  call    ?AddBreakpoint@@YAJPEAVDebugClient@@PEAVMachineInfo@@KKKPEAPEAVBreakpoint@@@Z; AddBreakpoint(DebugClient *,MachineInfo *,ulong,ulong,ulong,Breakpoint * *)
0x18036672e  test    eax, eax
0x180366730  jns     short loc_180366739
0x180366732  mov     ebx, eax
0x180366734  jmp     loc_180366875
0x180366739  mov     [rbp+47h+var_70], 8
0x180366741  mov     [rbp+47h+var_60], 0
0x180366749  mov     rax, qword ptr [rbp+47h+var_38+8]
0x18036674d  mov     [rbp+47h+var_68], rax
0x180366751  xor     edx, edx; struct _DESCRIPTOR64 *
0x180366753  lea     rcx, [rbp+47h+var_70]; struct _ADDR *
0x180366757  call    ?ComputeFlatAddress@@YAXPEAU_ADDR@@PEAU_DESCRIPTOR64@@@Z; ComputeFlatAddress(_ADDR *,_DESCRIPTOR64 *)
0x18036675c  mov     r8d, 1
0x180366762  lea     rdx, [rbp+47h+var_70]
0x180366766  mov     rsi, [rbp+47h+arg_28]
0x18036676a  mov     rcx, rsi
0x18036676d  call    ?SetAddr@Breakpoint@@QEAAJPEAU_ADDR@@W4BreakpointMatchAction@@@Z; Breakpoint::SetAddr(_ADDR *,BreakpointMatchAction)
0x180366772  test    eax, eax
0x180366774  js      short loc_180366732
0x180366776  mov     rax, [rsi]
0x180366779  mov     edx, 4
0x18036677e  mov     rcx, rsi
0x180366781  mov     rax, [rax+38h]
0x180366785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036678a  test    eax, eax
0x18036678c  js      short loc_180366732
0x18036678e  mov     rax, [rsi]
0x180366791  mov     r8d, ebx
0x180366794  mov     edx, r15d
0x180366797  mov     rcx, rsi
0x18036679a  mov     rax, [rax+68h]
0x18036679e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803667a3  test    eax, eax
0x1803667a5  js      short loc_180366732
0x1803667a7  mov     [rbp+47h+arg_28], 0
0x1803667af  mov     [rbp+47h+var_78], 0
0x1803667b7  call    ?GetManager@Client@DataModel@Debugger@@YAPEAUIDataModelManager@@XZ; Debugger::DataModel::Client::GetManager(void)
0x1803667bc  mov     r9, rax
0x1803667bf  mov     rcx, [rax]
0x1803667c2  mov     rax, [rcx+0B0h]
0x1803667c9  lea     r8, [rbp+47h+var_78]
0x1803667cd  lea     rdx, psz; "Debugger.Models.Breakpoint"
0x1803667d4  mov     rcx, r9
0x1803667d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803667dc  mov     rdx, [rbp+47h+var_78]
0x1803667e0  lea     rcx, [rbp+47h+var_A0]
0x1803667e4  call    ??0?$ObjectImpl@$0A@@Details@Client@DataModel@Debugger@@QEAA@PEAUIModelObject@@@Z; Debugger::DataModel::Client::Details::ObjectImpl<0>::ObjectImpl<0>(IModelObject *)
0x1803667e9  nop
0x1803667ea  lea     r8, [rbp+47h+arg_28]
0x1803667ee  mov     rdx, r14
0x1803667f1  lea     rcx, [rbp+47h+var_A0]
0x1803667f5  call    ?CreateInstanceOf@?$ObjectImpl@$0A@@Details@Client@DataModel@Debugger@@SAJAEBV12345@PEAUIDebugHostContext@@PEAV12345@@Z; Debugger::DataModel::Client::Details::ObjectImpl<0>::CreateInstanceOf(Debugger::DataModel::Client::Details::ObjectImpl<0> const &,IDebugHostContext *,Debugger::DataModel::Client::Details::ObjectImpl<0> *)
0x1803667fa  nop
0x1803667fb  lea     rcx, [rbp+47h+var_A0]
0x1803667ff  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x180366804  mov     [rbp+47h+arg_10], 0
0x18036680c  lea     rdx, [rbp+47h+arg_10]
0x180366810  mov     rcx, [rsi+198h]
0x180366817  call    ??$CreateIntrinsic@_K@?$ObjectImpl@$0A@@Details@Client@DataModel@Debugger@@SAJ_KPEAV01234@@Z; Debugger::DataModel::Client::Details::ObjectImpl<0>::CreateIntrinsic<unsigned __int64>(unsigned __int64,Debugger::DataModel::Client::Details::ObjectImpl<0> *)
0x18036681c  mov     ebx, eax
0x18036681e  test    eax, eax
0x180366820  js      short loc_180366861
0x180366822  mov     rsi, [rbp+47h+arg_28]
0x180366826  mov     rax, [rsi]
0x180366829  xor     r9d, r9d
0x18036682c  mov     r8, [rbp+47h+arg_10]
0x180366830  lea     rdx, aUniqueid; "UniqueID"
0x180366837  mov     rcx, rsi
0x18036683a  mov     rax, [rax+0C0h]
0x180366841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180366846  mov     ebx, eax
0x180366848  test    eax, eax
0x18036684a  js      short loc_180366861
0x18036684c  mov     [rbp+47h+arg_28], 0
0x180366854  mov     rdx, rsi
0x180366857  mov     rcx, [rbp+47h+arg_20]
0x18036685b  call    ??4?$ObjectImpl@$0A@@Details@Client@DataModel@Debugger@@QEAAAEAV01234@PEAUIModelObject@@@Z; Debugger::DataModel::Client::Details::ObjectImpl<0>::operator=(IModelObject *)
0x180366860  nop
0x180366861  lea     rcx, [rbp+47h+arg_10]
0x180366865  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x18036686a  nop
0x18036686b  lea     rcx, [rbp+47h+arg_28]
0x18036686f  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x180366874  nop
0x180366875  lea     rcx, [rbp+47h+var_58]
0x180366879  call    ??1?$unique_ptr@UtagVARIANT@@UVARIANTDeleter@@@std@@QEAA@XZ; std::unique_ptr<tagVARIANT,VARIANTDeleter>::~unique_ptr<tagVARIANT,VARIANTDeleter>(void)
0x18036687e  mov     eax, ebx
0x180366880  lea     r11, [rsp+0D0h+var_10]
0x180366888  mov     rbx, [r11+20h]
0x18036688c  mov     rsi, [r11+28h]
0x180366890  mov     rsp, r11
0x180366893  pop     r15
0x180366895  pop     r14
0x180366897  pop     rbp
0x180366898  retn
```
