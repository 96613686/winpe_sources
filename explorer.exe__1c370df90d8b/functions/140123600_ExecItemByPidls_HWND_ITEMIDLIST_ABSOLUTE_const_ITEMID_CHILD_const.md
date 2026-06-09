# _ExecItemByPidls(HWND__ *,_ITEMIDLIST_ABSOLUTE const *,_ITEMID_CHILD const *)

- ea: `0x140123600`
- end: `0x140123744`
- name: `?_ExecItemByPidls@@YAHPEAUHWND__@@PEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMID_CHILD@@@Z`
- size: `324`
- prototype: `int(HWND, const struct _ITEMIDLIST_ABSOLUTE *, const struct _ITEMID_CHILD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400ae2d0`

## callees

- `0x140034af0`
- `0x140065a60`
- `0x140065b60`
- `0x140113394`
- `0x140123600`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401236e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401236e4`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1401236ff`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1401236ff`
- `api-ms-win-shell-namespace-l1-1-0!SHGetNameFromIDList` at `0x1401236a5`
- `api-ms-win-shell-namespace-l1-1-0!SHGetNameFromIDList` at `0x1401236a5`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToObject` at `0x140123654`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToObject` at `0x140123654`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHInvokeDefaultCommand` at `0x140123668`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHInvokeDefaultCommand` at `0x140123668`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x140123632`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x140123632`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _ExecItemByPidls(HWND a1, const ITEMIDLIST *a2, const struct _ITEMID_CHILD *a3)
{
  unsigned int v6; // edi
  int v7; // edi
  __int64 *v8; // rax
  __int64 v9; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v12; // [rsp+30h] [rbp-20h] BYREF
  HWND v13; // [rsp+38h] [rbp-18h] BYREF
  PWSTR v14[2]; // [rsp+40h] [rbp-10h] BYREF
  PWSTR ppszName; // [rsp+78h] [rbp+28h] BYREF
  void *ppv; // [rsp+88h] [rbp+38h] BYREF

  v6 = 0;
  if ( a2 && a3 )
  {
    SetForegroundWindow(a1);
    ppv = 0;
    if ( SHBindToObject(0, a2, 0, &GUID_000214e6_0000_0000_c000_000000000046, &ppv) < 0 )
    {
      ppszName = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &ppszName,
        0);
      if ( SHGetNameFromIDList(a2, SIGDN_FILESYSPATH, &ppszName) >= 0 )
      {
        v13 = a1;
        v14[0] = ppszName;
        ppszName = 0;
        v8 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_208427e0a5707f3cadd1dd38d54ff18c_____lambda_208427e0a5707f3cadd1dd38d54ff18c___(
                          &v12,
                          &v13);
        v9 = *v8;
        *v8 = 0;
        if ( v12 )
        {
          v12 = 0;
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
        }
        CurrentThreadId = GetCurrentThreadId();
        SHTaskPoolQueueTask(1, 0, CurrentThreadId, 0);
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v14);
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszName);
    }
    else
    {
      v7 = SHInvokeDefaultCommand(a1, ppv, a3);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      return v7 >= 0;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140123600  mov     [rsp-18h+arg_0], rbx
0x140123605  mov     [rsp-18h+arg_10], rsi
0x14012360a  push    rbp
0x14012360b  push    rdi
0x14012360c  push    r14
0x14012360e  mov     rbp, rsp
0x140123611  sub     rsp, 50h
0x140123615  mov     r14, r8
0x140123618  mov     rbx, rdx
0x14012361b  mov     rsi, rcx
0x14012361e  xor     edi, edi
0x140123620  test    rdx, rdx
0x140123623  jz      loc_14012372D
0x140123629  test    r8, r8
0x14012362c  jz      loc_14012372D
0x140123632  call    cs:__imp_SetForegroundWindow
0x140123638  mov     [rbp+arg_18], rdi
0x14012363c  lea     rax, [rbp+arg_18]
0x140123640  mov     [rsp+50h+ppv], rax; ppv
0x140123645  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x14012364c  xor     r8d, r8d; pbc
0x14012364f  mov     rdx, rbx; pidl
0x140123652  xor     ecx, ecx; psf
0x140123654  call    cs:__imp_SHBindToObject
0x14012365a  test    eax, eax
0x14012365c  js      short loc_14012368A
0x14012365e  mov     r8, r14
0x140123661  mov     rdx, [rbp+arg_18]
0x140123665  mov     rcx, rsi
0x140123668  call    cs:__imp_SHInvokeDefaultCommand
0x14012366e  mov     edi, eax
0x140123670  mov     rcx, [rbp+arg_18]
0x140123674  mov     rax, [rcx]
0x140123677  mov     rax, [rax+10h]
0x14012367b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140123680  not     edi
0x140123682  shr     edi, 1Fh
0x140123685  jmp     loc_14012372D
0x14012368a  mov     [rbp+ppszName], rdi
0x14012368e  xor     edx, edx
0x140123690  lea     rcx, [rbp+ppszName]
0x140123694  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140123699  lea     r8, [rbp+ppszName]; ppszName
0x14012369d  mov     edx, 80058000h; sigdnName
0x1401236a2  mov     rcx, rbx; pidl
0x1401236a5  call    cs:__imp_SHGetNameFromIDList
0x1401236ab  test    eax, eax
0x1401236ad  js      short loc_140123724
0x1401236af  mov     [rbp+var_18], rsi
0x1401236b3  mov     rax, [rbp+ppszName]
0x1401236b7  mov     [rbp+var_10], rax
0x1401236bb  mov     [rbp+ppszName], rdi
0x1401236bf  lea     rdx, [rbp+var_18]
0x1401236c3  lea     rcx, [rbp+var_20]
0x1401236c7  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_208427e0a5707f3cadd1dd38d54ff18c_____lambda_208427e0a5707f3cadd1dd38d54ff18c___
0x1401236cc  mov     rbx, [rax]
0x1401236cf  mov     [rax], rdi
0x1401236d2  mov     rcx, [rbp+var_20]
0x1401236d6  test    rcx, rcx
0x1401236d9  jz      short loc_1401236E4
0x1401236db  mov     [rbp+var_20], rdi
0x1401236df  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1401236e4  call    cs:__imp_GetCurrentThreadId
0x1401236ea  mov     [rsp+50h+var_28], rdi
0x1401236ef  mov     [rsp+50h+ppv], rbx
0x1401236f4  xor     r9d, r9d
0x1401236f7  mov     r8d, eax
0x1401236fa  xor     edx, edx
0x1401236fc  lea     ecx, [rdx+1]
0x1401236ff  call    cs:__imp_SHTaskPoolQueueTask
0x140123705  nop
0x140123706  test    rbx, rbx
0x140123709  jz      short loc_14012371B
0x14012370b  mov     rax, [rbx]
0x14012370e  mov     rcx, rbx
0x140123711  mov     rax, [rax+10h]
0x140123715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012371a  nop
0x14012371b  lea     rcx, [rbp+var_10]
0x14012371f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140123724  lea     rcx, [rbp+ppszName]
0x140123728  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14012372d  mov     eax, edi
0x14012372f  lea     r11, [rsp+50h+var_s0]
0x140123734  mov     rbx, [r11+20h]
0x140123738  mov     rsi, [r11+30h]
0x14012373c  mov     rsp, r11
0x14012373f  pop     r14
0x140123741  pop     rdi
0x140123742  pop     rbp
0x140123743  retn
```
