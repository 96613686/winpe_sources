# InitHelperDll(ulong,void *)

- ea: `0x180008730`
- end: `0x180008804`
- name: `?InitHelperDll@@YAKKPEAX@Z`
- size: `212`
- prototype: `unsigned int __fastcall(unsigned int, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180008730`
- `0x18000880c`
- `0x180008b60`
- `0x1800120d0`
- `0x18001e51c`
- `0x180043010`

## string_xrefs

- `0x1800087dd`: `onecore\net\netprofiles\service\src\public\dll\netshhelper.cpp`

## pseudocode

```c
int __fastcall InitHelperDll(__int64 a1, void *a2)
{
  unsigned int NetshFunctions; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  unsigned int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // [rsp+20h] [rbp-40h] BYREF
  __int128 v9; // [rsp+28h] [rbp-38h]
  unsigned int (__fastcall *v10)(const struct _GUID *, unsigned int); // [rsp+38h] [rbp-28h]
  __int64 (__fastcall *v11)(); // [rsp+40h] [rbp-20h]
  _QWORD v12[2]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  if ( _InterlockedIncrement(&dword_180060378) != 1 )
    return 0;
  NetshFunctions = LoadNetshFunctions();
  if ( NetshFunctions )
    return wil::details::in1diag3::Return_Win32(retaddr, v4, v5, (const char *)NetshFunctions, v8);
  v8 = 0;
  v10 = StartNlmHelper;
  v12[0] = 0;
  v11 = _scrt_stub_for_is_c_termination_complete;
  v9 = xmmword_180046560;
  v12[1] = 0;
  v6 = ((__int64 (__fastcall *)(_QWORD *, __int64 *))g_netshRegisterHelper)(v12, &v8);
  v7 = v6;
  if ( v6 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\dll\\netshhelper.cpp",
      (const char *)v6,
      v8);
  return v7;
}

```

## disassembly

```asm
0x180008730  mov     [rsp-8+arg_0], rbx
0x180008735  push    rbp
0x180008736  mov     rbp, rsp
0x180008739  sub     rsp, 60h
0x18000873d  mov     rax, cs:__security_cookie
0x180008744  xor     rax, rsp
0x180008747  mov     [rbp+var_8], rax
0x18000874b  mov     eax, 1
0x180008750  lock xadd cs:dword_180060378, eax
0x180008758  inc     eax
0x18000875a  cmp     eax, 1
0x18000875d  jz      short loc_180008778
0x18000875f  xor     eax, eax
0x180008761  mov     rcx, [rbp+var_8]
0x180008765  xor     rcx, rsp; StackCookie
0x180008768  call    __security_check_cookie
0x18000876d  mov     rbx, [rsp+60h+arg_0]
0x180008772  add     rsp, 60h
0x180008776  pop     rbp
0x180008777  retn
0x180008778  call    ?LoadNetshFunctions@@YAKXZ; LoadNetshFunctions(void)
0x18000877d  test    eax, eax
0x18000877f  jnz     short loc_1800087F3
0x180008781  movups  xmm0, cs:xmmword_180046560
0x180008788  lea     rax, ?StartNlmHelper@@YAKPEBU_GUID@@K@Z; StartNlmHelper(_GUID const *,ulong)
0x18000878f  mov     [rbp+var_40], 0
0x180008797  mov     [rbp+var_28], rax
0x18000879b  lea     rdx, [rbp+var_40]
0x18000879f  lea     rax, __scrt_stub_for_is_c_termination_complete
0x1800087a6  mov     [rbp+var_18], 0
0x1800087ae  mov     [rbp+var_20], rax
0x1800087b2  lea     rcx, [rbp+var_18]
0x1800087b6  mov     rax, cs:?g_netshRegisterHelper@@3P6AKPEBU_GUID@@PEBU_NS_HELPER_ATTRIBUTES@@@ZEA; ulong (*g_netshRegisterHelper)(_GUID const *,_NS_HELPER_ATTRIBUTES const *)
0x1800087bd  movdqu  [rbp+var_38], xmm0
0x1800087c2  mov     [rbp+var_10], 0
0x1800087ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087cf  mov     ebx, eax
0x1800087d1  test    eax, eax
0x1800087d3  jnz     short loc_1800087D9
0x1800087d5  mov     eax, ebx
0x1800087d7  jmp     short loc_180008761
0x1800087d9  mov     rcx, [rbp+8]; this
0x1800087dd  lea     r8, aOnecoreNetNetp_12; "onecore\\net\\netprofiles\\service\\src"...
0x1800087e4  mov     r9d, ebx; char *
0x1800087e7  mov     edx, 46h ; 'F'; void *
0x1800087ec  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800087f1  jmp     short loc_1800087D5
0x1800087f3  mov     rcx, [rbp+8]; this
0x1800087f7  mov     r9d, eax; char *
0x1800087fa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800087ff  jmp     loc_180008761
```
