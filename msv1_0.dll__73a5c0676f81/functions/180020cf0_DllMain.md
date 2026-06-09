# DllMain

- ea: `0x180020cf0`
- end: `0x180020e0f`
- name: `DllMain`
- size: `287`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18002f9c4`

## callees

- `0x18001418c`
- `0x18001f5c0`
- `0x180020cf0`
- `0x180021dfc`
- `0x18002ee7c`
- `0x1800486ec`
- `0x180048724`
- `0x18004c494`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180020d08`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180020d08`
- `ntdll!EtwUnregisterTraceGuids` at `0x180020dcd`
- `ntdll!EtwUnregisterTraceGuids` at `0x180020dcd`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  int v3; // eax
  _QWORD *v4; // rdi

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    McGenEventRegister_EtwEventRegister();
    qword_180086EE0 = 1;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_NtLmGlobalDebugTraceControlGuid;
    qword_180086ED8 = 0;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    WppInitUm();
    v3 = TlgRegisterAggregateProviderEx(&dword_1800861D8);
    dword_180089CA8 = v3;
    if ( v3 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        81,
        WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids,
        (unsigned int)v3);
    }
  }
  else if ( !fdwReason )
  {
    if ( !lpvReserved )
      SspCleanup(hinstDLL);
    McGenEventUnregister_EtwEventUnregister(hinstDLL);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      while ( v4 )
      {
        if ( v4[1] )
        {
          EtwUnregisterTraceGuids();
          v4[1] = 0;
        }
        v4 = (_QWORD *)*v4;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
    if ( dword_180089CA8 >= 0 )
      TlgUnregisterAggregateProvider(&dword_1800861D8);
  }
  return 1;
}

```

## disassembly

```asm
0x180020cf0  mov     [rsp+arg_0], rbx
0x180020cf5  mov     [rsp+arg_8], rsi
0x180020cfa  push    rdi
0x180020cfb  sub     rsp, 20h
0x180020cff  cmp     edx, 1
0x180020d02  jnz     loc_180020D9A
0x180020d08  call    cs:__imp_DisableThreadLibraryCalls
0x180020d0e  call    McGenEventRegister_EtwEventRegister
0x180020d13  lea     rax, WPP_ThisDir_CTLGUID_NtLmGlobalDebugTraceControlGuid
0x180020d1a  mov     cs:qword_180086EE0, 1
0x180020d25  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180020d2c  xor     ebx, ebx
0x180020d2e  lea     rax, WPP_MAIN_CB
0x180020d35  mov     cs:qword_180086ED8, rbx
0x180020d3c  mov     cs:WPP_GLOBAL_Control, rax
0x180020d43  mov     cs:WPP_MAIN_CB, rbx
0x180020d4a  call    WppInitUm
0x180020d4f  lea     rcx, dword_1800861D8; CallbackContext
0x180020d56  call    TlgRegisterAggregateProviderEx
0x180020d5b  mov     cs:dword_180089CA8, eax
0x180020d61  test    eax, eax
0x180020d63  jns     loc_180020DFA
0x180020d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d70  lea     rsi, WPP_GLOBAL_Control
0x180020d77  cmp     rcx, rsi
0x180020d7a  jz      short loc_180020DFA
0x180020d7c  test    byte ptr [rcx+1Ch], 2
0x180020d80  jz      short loc_180020DFA
0x180020d82  mov     rcx, [rcx+10h]
0x180020d86  lea     edx, [rbx+51h]
0x180020d89  mov     r9d, eax
0x180020d8c  lea     r8, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids
0x180020d93  call    WPP_SF_d
0x180020d98  jmp     short loc_180020DFA
0x180020d9a  xor     ebx, ebx
0x180020d9c  test    edx, edx
0x180020d9e  jnz     short loc_180020DFA
0x180020da0  test    r8, r8
0x180020da3  jnz     short loc_180020DAA
0x180020da5  call    SspCleanup
0x180020daa  call    McGenEventUnregister_EtwEventUnregister
0x180020daf  mov     rdi, cs:WPP_GLOBAL_Control
0x180020db6  lea     rsi, WPP_GLOBAL_Control
0x180020dbd  cmp     rdi, rsi
0x180020dc0  jnz     short loc_180020DDA
0x180020dc2  jmp     short loc_180020DE6
0x180020dc4  mov     rcx, [rdi+8]
0x180020dc8  test    rcx, rcx
0x180020dcb  jz      short loc_180020DD7
0x180020dcd  call    cs:__imp_EtwUnregisterTraceGuids
0x180020dd3  mov     [rdi+8], rbx
0x180020dd7  mov     rdi, [rdi]
0x180020dda  test    rdi, rdi
0x180020ddd  jnz     short loc_180020DC4
0x180020ddf  mov     cs:WPP_GLOBAL_Control, rsi
0x180020de6  cmp     cs:dword_180089CA8, ebx
0x180020dec  jl      short loc_180020DFA
0x180020dee  lea     rcx, dword_1800861D8
0x180020df5  call    TlgUnregisterAggregateProvider
0x180020dfa  mov     rbx, [rsp+28h+arg_0]
0x180020dff  mov     eax, 1
0x180020e04  mov     rsi, [rsp+28h+arg_8]
0x180020e09  add     rsp, 20h
0x180020e0d  pop     rdi
0x180020e0e  retn
```
