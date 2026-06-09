# WcmServiceListener<2>::Start(std::function<void (WcmServiceStatus)> &&)

- ea: `0x18008c258`
- end: `0x18008c398`
- name: `?Start@?$WcmServiceListener@$01@@QEAAJ$$QEAV?$function@$$A6AXW4WcmServiceStatus@@@Z@std@@@Z`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1801363a0`

## callees

- `0x18000c160`
- `0x18005530c`
- `0x18008c258`
- `0x18008c99c`
- `0x18008c9bc`
- `0x180149010`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18008c302`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18008c302`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008c2c7`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008c2c7`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18008c34b`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18008c34b`

## string_xrefs

- `0x18008c2dc`: `onecore\net\netprofiles\service\src\kryptonhostmanager\inc\ServiceListener.h`
- `0x18008c317`: `onecore\net\netprofiles\service\src\kryptonhostmanager\inc\ServiceListener.h`
- `0x18008c35a`: `onecore\net\netprofiles\service\src\kryptonhostmanager\inc\ServiceListener.h`

## pseudocode

```c
__int64 __fastcall WcmServiceListener<2>::Start(__int64 a1, __int64 a2)
{
  unsigned int v2; // esi
  __int64 v6; // rcx
  SC_HANDLE v7; // rax
  const char *v8; // r9
  unsigned int v9; // ebx
  SC_HANDLE v10; // rax
  const char *v11; // r9
  int LastError; // eax
  unsigned int v13; // eax
  SC_HANDLE v14; // [rsp+30h] [rbp-18h] BYREF
  SC_HANDLE v15[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = a1 + 64;
  if ( *(_QWORD *)(a1 + 64) )
    return 0;
  if ( a1 != a2 )
  {
    std::_Func_class<void,>::~_Func_class<void,>(a1);
    v6 = *(_QWORD *)(a2 + 56);
    if ( v6 )
    {
      if ( v6 == a2 )
      {
        *(_QWORD *)(a1 + 56) = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 8LL))(v6, a1);
        std::_Func_class<void,>::~_Func_class<void,>(a2);
      }
      else
      {
        *(_QWORD *)(a1 + 56) = v6;
        *(_QWORD *)(a2 + 56) = 0;
      }
    }
  }
  v7 = OpenSCManagerW(0, 0, 5u);
  v15[0] = v7;
  if ( v7 )
  {
    v10 = OpenServiceW(v7, L"WlanSvc", 4u);
    v14 = v10;
    if ( v10 )
    {
      v13 = SubscribeServiceChangeNotifications(v10, 2, WcmServiceListener<2>::ServiceStateChangeCallback, a1);
      if ( !v13 )
      {
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v14);
        v9 = 0;
        goto LABEL_16;
      }
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x37,
                    (unsigned int)"onecore\\net\\netprofiles\\service\\src\\kryptonhostmanager\\inc\\ServiceListener.h",
                    (const char *)v13,
                    v2);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x34,
                    (unsigned int)"onecore\\net\\netprofiles\\service\\src\\kryptonhostmanager\\inc\\ServiceListener.h",
                    v11);
    }
    v9 = LastError;
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v14);
  }
  else
  {
    v9 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x31,
           (unsigned int)"onecore\\net\\netprofiles\\service\\src\\kryptonhostmanager\\inc\\ServiceListener.h",
           v8);
  }
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v15);
  return v9;
}

```

## disassembly

```asm
0x18008c258  mov     [rsp+arg_10], rbx
0x18008c25d  mov     [rsp+arg_18], rsi
0x18008c262  push    rdi
0x18008c263  sub     rsp, 40h
0x18008c267  lea     rsi, [rcx+40h]
0x18008c26b  mov     rdi, rdx
0x18008c26e  cmp     qword ptr [rsi], 0
0x18008c272  mov     rbx, rcx
0x18008c275  jz      short loc_18008C27E
0x18008c277  xor     eax, eax
0x18008c279  jmp     loc_18008C388
0x18008c27e  cmp     rbx, rdi
0x18008c281  jz      short loc_18008C2BF
0x18008c283  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18008c288  mov     rcx, [rdi+38h]
0x18008c28c  test    rcx, rcx
0x18008c28f  jz      short loc_18008C2BF
0x18008c291  cmp     rcx, rdi
0x18008c294  jnz     short loc_18008C2B3
0x18008c296  mov     rax, [rcx]
0x18008c299  mov     rdx, rbx
0x18008c29c  mov     rax, [rax+8]
0x18008c2a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c2a5  mov     rcx, rdi
0x18008c2a8  mov     [rbx+38h], rax
0x18008c2ac  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18008c2b1  jmp     short loc_18008C2BF
0x18008c2b3  mov     [rbx+38h], rcx
0x18008c2b7  mov     qword ptr [rdi+38h], 0
0x18008c2bf  xor     edx, edx; lpDatabaseName
0x18008c2c1  xor     ecx, ecx; lpMachineName
0x18008c2c3  lea     r8d, [rdx+5]; dwDesiredAccess
0x18008c2c7  call    cs:__imp_OpenSCManagerW
0x18008c2cd  mov     [rsp+48h+var_10], rax
0x18008c2d2  test    rax, rax
0x18008c2d5  jnz     short loc_18008C2F2
0x18008c2d7  mov     rcx, [rsp+48h]; this
0x18008c2dc  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x18008c2e3  lea     edx, [rax+31h]; void *
0x18008c2e6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008c2eb  mov     ebx, eax
0x18008c2ed  jmp     loc_18008C37C
0x18008c2f2  mov     r8d, 4; dwDesiredAccess
0x18008c2f8  lea     rdx, ServiceName; "WlanSvc"
0x18008c2ff  mov     rcx, rax; hSCManager
0x18008c302  call    cs:__imp_OpenServiceW
0x18008c308  mov     [rsp+48h+var_18], rax
0x18008c30d  test    rax, rax
0x18008c310  jnz     short loc_18008C334
0x18008c312  mov     rcx, [rsp+48h]; this
0x18008c317  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x18008c31e  lea     edx, [rax+34h]; void *
0x18008c321  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008c326  lea     rcx, [rsp+48h+var_18]
0x18008c32b  mov     ebx, eax
0x18008c32d  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18008c332  jmp     short loc_18008C37C
0x18008c334  mov     r9, rbx
0x18008c337  mov     qword ptr [rsp+48h+var_28], rsi; unsigned int
0x18008c33c  lea     r8, ?ServiceStateChangeCallback@?$WcmServiceListener@$01@@CAXKPEAX@Z; WcmServiceListener<2>::ServiceStateChangeCallback(ulong,void *)
0x18008c343  mov     edx, 2
0x18008c348  mov     rcx, rax
0x18008c34b  call    cs:__imp_SubscribeServiceChangeNotifications
0x18008c351  test    eax, eax
0x18008c353  jz      short loc_18008C370
0x18008c355  mov     rcx, [rsp+48h]; this
0x18008c35a  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x18008c361  mov     r9d, eax; char *
0x18008c364  mov     edx, 37h ; '7'; void *
0x18008c369  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008c36e  jmp     short loc_18008C326
0x18008c370  lea     rcx, [rsp+48h+var_18]
0x18008c375  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18008c37a  xor     ebx, ebx
0x18008c37c  lea     rcx, [rsp+48h+var_10]
0x18008c381  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18008c386  mov     eax, ebx
0x18008c388  mov     rbx, [rsp+48h+arg_10]
0x18008c38d  mov     rsi, [rsp+48h+arg_18]
0x18008c392  add     rsp, 40h
0x18008c396  pop     rdi
0x18008c397  retn
```
