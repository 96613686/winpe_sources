# DllMain

- ea: `0x18000cba0`
- end: `0x18000cc64`
- name: `DllMain`
- size: `196`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000f4d4`

## callees

- `0x18000cba0`
- `0x18000e5ec`
- `0x180018918`
- `0x1800190c8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18000cc36`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18000cc36`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000cbb4`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000cbb4`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  _QWORD *v3; // rdi
  TRACEHANDLE v4; // rcx

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    qword_180027BF0 = 1;
    qword_180027BE8 = 0;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_NegoExtsGlobalDebugTraceControlGuid;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    WppInitUm();
  }
  else if ( !fdwReason )
  {
    WSTWaitCleanup();
    if ( NegoExtsGlobalUserModeContextsInitialized )
    {
      WSTFreeUserModeContextList(0);
      NegoExtsGlobalUserModeContextsInitialized = 0;
    }
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      while ( v3 )
      {
        v4 = v3[1];
        if ( v4 )
        {
          UnregisterTraceGuids(v4);
          v3[1] = 0;
        }
        v3 = (_QWORD *)*v3;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000cba0  mov     [rsp+arg_0], rbx
0x18000cba5  mov     [rsp+arg_8], rsi
0x18000cbaa  push    rdi
0x18000cbab  sub     rsp, 20h
0x18000cbaf  cmp     edx, 1
0x18000cbb2  jnz     short loc_18000CBF8
0x18000cbb4  call    cs:__imp_DisableThreadLibraryCalls
0x18000cbba  xor     ebx, ebx
0x18000cbbc  mov     cs:qword_180027BF0, 1
0x18000cbc7  lea     rax, WPP_ThisDir_CTLGUID_NegoExtsGlobalDebugTraceControlGuid
0x18000cbce  mov     cs:qword_180027BE8, rbx
0x18000cbd5  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000cbdc  lea     rax, WPP_MAIN_CB
0x18000cbe3  mov     cs:WPP_GLOBAL_Control, rax
0x18000cbea  mov     cs:WPP_MAIN_CB, rbx
0x18000cbf1  call    WppInitUm
0x18000cbf6  jmp     short loc_18000CC4F
0x18000cbf8  xor     ebx, ebx
0x18000cbfa  test    edx, edx
0x18000cbfc  jnz     short loc_18000CC4F
0x18000cbfe  call    ?WSTWaitCleanup@@YAXXZ; WSTWaitCleanup(void)
0x18000cc03  cmp     cs:?NegoExtsGlobalUserModeContextsInitialized@@3EA, bl; uchar NegoExtsGlobalUserModeContextsInitialized
0x18000cc09  jz      short loc_18000CC18
0x18000cc0b  xor     ecx, ecx; unsigned int
0x18000cc0d  call    ?WSTFreeUserModeContextList@@YAXK@Z; WSTFreeUserModeContextList(ulong)
0x18000cc12  mov     cs:?NegoExtsGlobalUserModeContextsInitialized@@3EA, bl; uchar NegoExtsGlobalUserModeContextsInitialized
0x18000cc18  mov     rdi, cs:WPP_GLOBAL_Control
0x18000cc1f  lea     rsi, WPP_GLOBAL_Control
0x18000cc26  cmp     rdi, rsi
0x18000cc29  jnz     short loc_18000CC43
0x18000cc2b  jmp     short loc_18000CC4F
0x18000cc2d  mov     rcx, [rdi+8]; RegistrationHandle
0x18000cc31  test    rcx, rcx
0x18000cc34  jz      short loc_18000CC40
0x18000cc36  call    cs:__imp_UnregisterTraceGuids
0x18000cc3c  mov     [rdi+8], rbx
0x18000cc40  mov     rdi, [rdi]
0x18000cc43  test    rdi, rdi
0x18000cc46  jnz     short loc_18000CC2D
0x18000cc48  mov     cs:WPP_GLOBAL_Control, rsi
0x18000cc4f  mov     rbx, [rsp+28h+arg_0]
0x18000cc54  mov     eax, 1
0x18000cc59  mov     rsi, [rsp+28h+arg_8]
0x18000cc5e  add     rsp, 20h
0x18000cc62  pop     rdi
0x18000cc63  retn
```
