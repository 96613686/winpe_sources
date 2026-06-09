# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::callback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,ulong)

- ea: `0x180008a50`
- end: `0x180008af6`
- name: `?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z`
- size: `166`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, unsigned __int8 *Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001950`
- `0x1800083b0`
- `0x1800084c8`
- `0x180008740`
- `0x180008a50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180008a8d`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180008a8d`

## pseudocode

```c
void __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::callback(
        PTP_CALLBACK_INSTANCE Instance,
        unsigned __int8 *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  int v5; // eax
  bool v6; // dl
  unsigned int v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  BOOL fAsynchronous; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( _InterlockedIncrement((volatile signed __int32 *)Context + 37) > 1 )
  {
    v5 = RegNotifyChangeKeyValue(*((HKEY *)Context + 15), Context[144], 0x10000005u, *((HANDLE *)Context + 16), 1);
    if ( !v5 || v5 == 5 )
    {
      wistd::function<void (enum wil::RegistryChangeKind)>::operator()((__int64)Context, 0);
      v6 = 1;
    }
    else
    {
      if ( v5 != 811 )
      {
        if ( v5 != 1018 )
        {
          if ( v5 > 0 )
            v5 = (unsigned __int16)v5 | 0x80070000;
          v7 = wil::verify_hresult<long>((unsigned int)v5);
          wil::details::in1diag3::FailFast_Hr(retaddr, v8, v9, (const char *)v7, fAsynchronous);
        }
        wistd::function<void (enum wil::RegistryChangeKind)>::operator()((__int64)Context, 1);
      }
      v6 = 0;
    }
    wil::details::registry_watcher_state::ReleaseFromCallback((wil::details::registry_watcher_state *)Context, v6);
  }
}

```

## disassembly

```asm
0x180008a50  push    rbx
0x180008a52  sub     rsp, 30h
0x180008a56  mov     rbx, rdx
0x180008a59  mov     eax, 1
0x180008a5e  lock xadd [rdx+94h], eax
0x180008a66  inc     eax
0x180008a68  cmp     eax, 1
0x180008a6b  jle     short loc_180008ACF
0x180008a6d  movzx   edx, byte ptr [rdx+90h]; bWatchSubtree
0x180008a74  mov     r8d, 10000005h; dwNotifyFilter
0x180008a7a  mov     r9, [rbx+80h]; hEvent
0x180008a81  mov     rcx, [rbx+78h]; hKey
0x180008a85  mov     [rsp+38h+fAsynchronous], 1; int
0x180008a8d  call    cs:__imp_RegNotifyChangeKeyValue
0x180008a93  test    eax, eax
0x180008a95  jz      short loc_180008ABB
0x180008a97  cmp     eax, 5
0x180008a9a  jz      short loc_180008ABB
0x180008a9c  cmp     eax, 32Bh
0x180008aa1  jz      short loc_180008AB7
0x180008aa3  cmp     eax, 3FAh
0x180008aa8  jnz     short loc_180008AD5
0x180008aaa  mov     edx, 1
0x180008aaf  mov     rcx, rbx
0x180008ab2  call    ??R?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@QEBAXW4RegistryChangeKind@wil@@@Z; wistd::function<void (wil::RegistryChangeKind)>::operator()(wil::RegistryChangeKind)
0x180008ab7  xor     edx, edx
0x180008ab9  jmp     short loc_180008AC7
0x180008abb  xor     edx, edx
0x180008abd  mov     rcx, rbx
0x180008ac0  call    ??R?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@QEBAXW4RegistryChangeKind@wil@@@Z; wistd::function<void (wil::RegistryChangeKind)>::operator()(wil::RegistryChangeKind)
0x180008ac5  mov     dl, 1; bool
0x180008ac7  mov     rcx, rbx; this
0x180008aca  call    ?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z; wil::details::registry_watcher_state::ReleaseFromCallback(bool)
0x180008acf  add     rsp, 30h
0x180008ad3  pop     rbx
0x180008ad4  retn
0x180008ad5  test    eax, eax
0x180008ad7  jle     short loc_180008AE1
0x180008ad9  movzx   eax, ax
0x180008adc  or      eax, 80070000h
0x180008ae1  mov     ecx, eax
0x180008ae3  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180008ae8  mov     rcx, [rsp+38h]; this
0x180008aed  mov     r9d, eax; char *
0x180008af0  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```
