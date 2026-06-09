# Windows::Internal::ServiceModuleBase::Uninitialize(void)

- ea: `0x180007a88`
- end: `0x180007b46`
- name: `?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ`
- size: `190`
- prototype: `__int64 __fastcall(Windows::Internal::ServiceModuleBase *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000289c`
- `0x180004474`
- `0x180006dc0`

## callees

- `0x180006160`
- `0x180007a88`
- `0x180008010`
- `0x180008150`
- `0x180012010`

## import_xrefs

- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180007adf`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180007adf`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180007b2c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180007b2c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModuleBase::Uninitialize(Windows::Internal::ServiceModuleBase *this)
{
  __int64 v2; // rcx
  int v3; // eax
  void *v4; // rdx
  __int64 v5; // r8
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = *((_QWORD *)this + 3);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64, __int64 (__fastcall *)(struct tagComCallData *), Windows::Internal::ServiceModuleBase *, GUID *, int, _QWORD))(*(_QWORD *)v2 + 24LL))(
      v2,
      Windows::Internal::ServiceModuleBase::DisconnectCallbackThunk,
      this,
      &IID_IContextCallback,
      5,
      0);
    Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease((__int64 *)this + 3);
  }
  if ( *((_BYTE *)this + 21) )
  {
    v3 = CoRegisterServerShutdownDelay(0, 0);
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, v4, v5, (const char *)(unsigned int)v3);
    *((_BYTE *)this + 21) = 0;
  }
  if ( *((_BYTE *)this + 20) )
  {
    (*(void (__fastcall **)(Windows::Internal::ServiceModuleBase *))(*(_QWORD *)this + 24LL))(this);
    *((_BYTE *)this + 20) = 0;
  }
  if ( *((int *)this + 4) >= 0 )
  {
    if ( *((_QWORD *)this + 1) )
      wil::details::unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&long CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>::reset(
        (char *)this + 8,
        0);
    else
      RoUninitialize();
    *((_DWORD *)this + 4) = -2147467259;
  }
  return 0;
}

```

## disassembly

```asm
0x180007a88  mov     [rsp+arg_0], rbx
0x180007a8d  push    rdi
0x180007a8e  sub     rsp, 40h
0x180007a92  mov     rbx, rcx
0x180007a95  mov     rcx, [rcx+18h]
0x180007a99  test    rcx, rcx
0x180007a9c  jz      short loc_180007AD5
0x180007a9e  mov     rax, [rcx]
0x180007aa1  lea     r9, IID_IContextCallback
0x180007aa8  mov     [rsp+48h+var_20], 0
0x180007ab1  lea     rdx, ?DisconnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z; Windows::Internal::ServiceModuleBase::DisconnectCallbackThunk(tagComCallData *)
0x180007ab8  mov     r8, rbx
0x180007abb  mov     [rsp+48h+var_28], 5; int
0x180007ac3  mov     rax, [rax+18h]
0x180007ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007acc  lea     rcx, [rbx+18h]
0x180007ad0  call    ?InternalRelease@?$ComPtr@UIGlobalOptions@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease(void)
0x180007ad5  cmp     byte ptr [rbx+15h], 0
0x180007ad9  jz      short loc_180007AFA
0x180007adb  xor     edx, edx
0x180007add  xor     ecx, ecx
0x180007adf  call    cs:__imp_CoRegisterServerShutdownDelay
0x180007ae5  test    eax, eax
0x180007ae7  jns     short loc_180007AF6
0x180007ae9  mov     rcx, [rsp+48h]; this
0x180007aee  mov     r9d, eax; char *
0x180007af1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007af6  mov     byte ptr [rbx+15h], 0
0x180007afa  cmp     byte ptr [rbx+14h], 0
0x180007afe  jz      short loc_180007B13
0x180007b00  mov     rax, [rbx]
0x180007b03  mov     rcx, rbx
0x180007b06  mov     rax, [rax+18h]
0x180007b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b0f  mov     byte ptr [rbx+14h], 0
0x180007b13  cmp     dword ptr [rbx+10h], 0
0x180007b17  jl      short loc_180007B39
0x180007b19  lea     rcx, [rbx+8]
0x180007b1d  cmp     qword ptr [rcx], 0
0x180007b21  jz      short loc_180007B2C
0x180007b23  xor     edx, edx
0x180007b25  call    ?reset@?$unique_storage@U?$resource_policy@PEAUCO_MTA_USAGE_COOKIE__@@P6AJPEAU1@@Z$1?CoDecrementMTAUsage@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUCO_MTA_USAGE_COOKIE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>::reset(CO_MTA_USAGE_COOKIE__ *)
0x180007b2a  jmp     short loc_180007B32
0x180007b2c  call    cs:__imp_RoUninitialize
0x180007b32  mov     dword ptr [rbx+10h], 80004005h
0x180007b39  mov     rbx, [rsp+48h+arg_0]
0x180007b3e  xor     eax, eax
0x180007b40  add     rsp, 40h
0x180007b44  pop     rdi
0x180007b45  retn
```
