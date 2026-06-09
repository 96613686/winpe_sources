# GoBackOrCloseExplorerWindow(IUnknown *)

- ea: `0x1800154dc`
- end: `0x180015575`
- name: `?GoBackOrCloseExplorerWindow@@YAJPEAUIUnknown@@@Z`
- size: `153`
- prototype: `__int64 __fastcall(struct IUnknown *)`
- caller_count: `8`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800170e0`
- `0x180017100`
- `0x1800171c8`
- `0x180019f40`
- `0x18001a22c`
- `0x18001a4e0`
- `0x18001bcf0`
- `0x18001bd90`

## callees

- `0x180008b30`
- `0x18000994c`
- `0x1800154dc`
- `0x180032010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryServiceForWebBrowserApp` at `0x1800154f7`
- `SHLWAPI!__imp_IUnknown_QueryServiceForWebBrowserApp` at `0x1800154f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GoBackOrCloseExplorerWindow(struct IUnknown *a1)
{
  int v1; // ebx
  __int64 v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v1 = IUnknown_QueryServiceForWebBrowserApp(a1, &GUID_0002df05_0000_0000_c000_000000000046, &v3);
  if ( v1 >= 0 )
  {
    v1 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 56LL))(v3);
    if ( v1 < 0 )
      v1 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 256LL))(v3);
  }
  else if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0a8c7ea7de9f35e66365b8355c777a08_Traceguids, (unsigned int)v1);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v3);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800154dc  push    rbx
0x1800154de  sub     rsp, 20h
0x1800154e2  mov     [rsp+28h+arg_8], 0
0x1800154eb  lea     r8, [rsp+28h+arg_8]
0x1800154f0  lea     rdx, _GUID_0002df05_0000_0000_c000_000000000046
0x1800154f7  call    cs:__imp_IUnknown_QueryServiceForWebBrowserApp
0x1800154fd  mov     ebx, eax
0x1800154ff  test    eax, eax
0x180015501  jns     short loc_180015536
0x180015503  lea     rax, WPP_GLOBAL_Control
0x18001550a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015511  cmp     rcx, rax
0x180015514  jz      short loc_180015563
0x180015516  test    byte ptr [rcx+1Ch], 1
0x18001551a  jz      short loc_180015563
0x18001551c  mov     edx, 0Ah
0x180015521  mov     r9d, ebx
0x180015524  lea     r8, WPP_0a8c7ea7de9f35e66365b8355c777a08_Traceguids
0x18001552b  mov     rcx, [rcx+10h]
0x18001552f  call    WPP_SF_d
0x180015534  jmp     short loc_180015563
0x180015536  mov     rcx, [rsp+28h+arg_8]
0x18001553b  mov     rax, [rcx]
0x18001553e  mov     rax, [rax+38h]
0x180015542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015547  mov     ebx, eax
0x180015549  test    eax, eax
0x18001554b  jns     short loc_180015563
0x18001554d  mov     rcx, [rsp+28h+arg_8]
0x180015552  mov     rax, [rcx]
0x180015555  mov     rax, [rax+100h]
0x18001555c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015561  mov     ebx, eax
0x180015563  lea     rcx, [rsp+28h+arg_8]
0x180015568  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001556d  mov     eax, ebx
0x18001556f  add     rsp, 20h
0x180015573  pop     rbx
0x180015574  retn
```
