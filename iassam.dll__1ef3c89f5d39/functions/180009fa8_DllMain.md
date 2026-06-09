# DllMain

- ea: `0x180009fa8`
- end: `0x18000a06e`
- name: `DllMain`
- size: `198`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800016d4`

## callees

- `0x180006c58`
- `0x18000894c`
- `0x180009fa8`
- `0x18000a1f8`
- `0x1800251a0`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x180009fce`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180009fce`
- `ADVAPI32!UnregisterTraceGuids` at `0x18000a03b`
- `ADVAPI32!UnregisterTraceGuids` at `0x18000a03b`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct _GUID *v3; // r9
  HINSTANCE v4; // rbx
  PVOID v5; // rdi

  v4 = hinstDLL;
  if ( fdwReason == 1 )
  {
    hProxyDll = hinstDLL;
    ATL::CComModule::Init(
      (ATL::CComModule *)hinstDLL,
      *(struct ATL::_ATL_OBJMAP_ENTRY30 **)&fdwReason,
      (HINSTANCE)lpvReserved,
      v3);
    DisableThreadLibraryCalls(v4);
    qword_180040128 = 1;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_napnps;
    qword_180040120 = 0;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    WppInitUm();
    SafeAllocaInitialize();
  }
  else if ( !fdwReason )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      while ( v5 )
      {
        hinstDLL = (HINSTANCE)*((_QWORD *)v5 + 1);
        if ( hinstDLL )
        {
          UnregisterTraceGuids((TRACEHANDLE)hinstDLL);
          *((_QWORD *)v5 + 1) = 0;
        }
        v5 = *(PVOID *)v5;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
    ATL::CComModule::Term((ATL::CComModule *)hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x180009fa8  mov     [rsp+arg_0], rbx
0x180009fad  mov     [rsp+arg_8], rsi
0x180009fb2  push    rdi
0x180009fb3  sub     rsp, 20h
0x180009fb7  mov     rbx, rcx
0x180009fba  cmp     edx, 1
0x180009fbd  jnz     short loc_18000A017
0x180009fbf  mov     cs:hProxyDll, rcx
0x180009fc6  call    ?Init@CComModule@ATL@@QEAAJPEAU_ATL_OBJMAP_ENTRY30@2@PEAUHINSTANCE__@@PEBU_GUID@@@Z; ATL::CComModule::Init(ATL::_ATL_OBJMAP_ENTRY30 *,HINSTANCE__ *,_GUID const *)
0x180009fcb  mov     rcx, rbx; hLibModule
0x180009fce  call    cs:__imp_DisableThreadLibraryCalls
0x180009fd4  lea     rax, WPP_ThisDir_CTLGUID_napnps
0x180009fdb  mov     cs:qword_180040128, 1
0x180009fe6  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180009fed  xor     ebx, ebx
0x180009fef  lea     rax, WPP_MAIN_CB
0x180009ff6  mov     cs:qword_180040120, rbx
0x180009ffd  mov     cs:WPP_GLOBAL_Control, rax
0x18000a004  mov     cs:WPP_MAIN_CB, rbx
0x18000a00b  call    WppInitUm
0x18000a010  call    SafeAllocaInitialize
0x18000a015  jmp     short loc_18000A059
0x18000a017  xor     ebx, ebx
0x18000a019  test    edx, edx
0x18000a01b  jnz     short loc_18000A059
0x18000a01d  mov     rdi, cs:WPP_GLOBAL_Control
0x18000a024  lea     rsi, WPP_GLOBAL_Control
0x18000a02b  cmp     rdi, rsi
0x18000a02e  jz      short loc_18000A054
0x18000a030  jmp     short loc_18000A048
0x18000a032  mov     rcx, [rdi+8]; RegistrationHandle
0x18000a036  test    rcx, rcx
0x18000a039  jz      short loc_18000A045
0x18000a03b  call    cs:__imp_UnregisterTraceGuids
0x18000a041  mov     [rdi+8], rbx
0x18000a045  mov     rdi, [rdi]
0x18000a048  test    rdi, rdi
0x18000a04b  jnz     short loc_18000A032
0x18000a04d  mov     cs:WPP_GLOBAL_Control, rsi
0x18000a054  call    ?Term@CComModule@ATL@@QEAAXXZ; ATL::CComModule::Term(void)
0x18000a059  mov     rbx, [rsp+28h+arg_0]
0x18000a05e  mov     eax, 1
0x18000a063  mov     rsi, [rsp+28h+arg_8]
0x18000a068  add     rsp, 20h
0x18000a06c  pop     rdi
0x18000a06d  retn
```
