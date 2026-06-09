# DllMain

- ea: `0x18003aef0`
- end: `0x18003b01a`
- name: `DllMain`
- size: `298`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x18001d684`

## callees

- `0x18003aef0`
- `0x18003b020`
- `0x18003b060`
- `0x18003b13c`
- `0x18003c204`
- `0x18003c31c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18003af08`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18003af08`
- `ntdll!EtwUnregisterTraceGuids` at `0x18003afdb`
- `ntdll!EtwUnregisterTraceGuids` at `0x18003afdb`
- `ntdll!RtlImageNtHeader` at `0x18003af26`
- `ntdll!RtlImageNtHeader` at `0x18003af26`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 GuaranteedStackBytes; // rax
  __int64 **v4; // rdi

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    McGenEventRegister_EtwEventRegister();
    if ( RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress) )
    {
      GuaranteedStackBytes = NtCurrentTeb()->GuaranteedStackBytes;
      g_ulAdditionalProbeSize = GuaranteedStackBytes;
      if ( !GuaranteedStackBytes )
      {
        g_ulAdditionalProbeSize = 12288;
LABEL_7:
        qword_18004C810 = 0;
        WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_DPAPIGlobalDebugTraceControlGuid;
        WPP_GLOBAL_Control = &WPP_MAIN_CB;
        WPP_MAIN_CB = 0;
        qword_18004C818 = 1;
        WppInitUm();
        TlgRegisterAggregateProviderEx();
        return 1;
      }
      if ( (unsigned __int64)(GuaranteedStackBytes + 8) >= 8 )
        goto LABEL_7;
    }
    g_ulAdditionalProbeSize = -9;
    goto LABEL_7;
  }
  if ( !fdwReason )
  {
    v4 = (__int64 **)WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      while ( v4 )
      {
        hinstDLL = (HINSTANCE)v4[1];
        if ( hinstDLL )
        {
          EtwUnregisterTraceGuids();
          v4[1] = 0;
        }
        v4 = (__int64 **)*v4;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
    McGenEventUnregister_EtwEventUnregister(hinstDLL, *(_QWORD *)&fdwReason, lpvReserved);
    TlgUnregisterAggregateProvider();
  }
  return 1;
}

```

## disassembly

```asm
0x18003aef0  mov     [rsp+arg_0], rbx
0x18003aef5  mov     [rsp+arg_8], rsi
0x18003aefa  push    rdi
0x18003aefb  sub     rsp, 20h
0x18003aeff  cmp     edx, 1
0x18003af02  jnz     loc_18003AFB7
0x18003af08  call    cs:__imp_DisableThreadLibraryCalls
0x18003af0f  nop     dword ptr [rax+rax+00h]
0x18003af14  call    McGenEventRegister_EtwEventRegister
0x18003af19  mov     rcx, gs:60h
0x18003af22  mov     rcx, [rcx+10h]; BaseAddress
0x18003af26  call    cs:__imp_RtlImageNtHeader
0x18003af2d  nop     dword ptr [rax+rax+00h]
0x18003af32  xor     ebx, ebx
0x18003af34  test    rax, rax
0x18003af37  jz      short loc_18003AF6B
0x18003af39  mov     rax, gs:30h
0x18003af42  mov     eax, [rax+1748h]
0x18003af48  mov     cs:g_ulAdditionalProbeSize, rax
0x18003af4f  test    rax, rax
0x18003af52  jnz     short loc_18003AF61
0x18003af54  mov     cs:g_ulAdditionalProbeSize, 3000h
0x18003af5f  jmp     short loc_18003AF76
0x18003af61  add     rax, 8
0x18003af65  cmp     rax, 8
0x18003af69  jnb     short loc_18003AF76
0x18003af6b  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18003af76  lea     rax, WPP_ThisDir_CTLGUID_DPAPIGlobalDebugTraceControlGuid
0x18003af7d  mov     cs:qword_18004C810, rbx
0x18003af84  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18003af8b  lea     rax, WPP_MAIN_CB
0x18003af92  mov     cs:WPP_GLOBAL_Control, rax
0x18003af99  mov     cs:WPP_MAIN_CB, rbx
0x18003afa0  mov     cs:qword_18004C818, 1
0x18003afab  call    WppInitUm
0x18003afb0  call    TlgRegisterAggregateProviderEx
0x18003afb5  jmp     short loc_18003B004
0x18003afb7  xor     ebx, ebx
0x18003afb9  test    edx, edx
0x18003afbb  jnz     short loc_18003B004
0x18003afbd  mov     rdi, cs:WPP_GLOBAL_Control
0x18003afc4  lea     rsi, WPP_GLOBAL_Control
0x18003afcb  cmp     rdi, rsi
0x18003afce  jz      short loc_18003AFFA
0x18003afd0  jmp     short loc_18003AFEE
0x18003afd2  mov     rcx, [rdi+8]
0x18003afd6  test    rcx, rcx
0x18003afd9  jz      short loc_18003AFEB
0x18003afdb  call    cs:__imp_EtwUnregisterTraceGuids
0x18003afe2  nop     dword ptr [rax+rax+00h]
0x18003afe7  mov     [rdi+8], rbx
0x18003afeb  mov     rdi, [rdi]
0x18003afee  test    rdi, rdi
0x18003aff1  jnz     short loc_18003AFD2
0x18003aff3  mov     cs:WPP_GLOBAL_Control, rsi
0x18003affa  call    McGenEventUnregister_EtwEventUnregister
0x18003afff  call    TlgUnregisterAggregateProvider
0x18003b004  mov     rbx, [rsp+28h+arg_0]
0x18003b009  mov     eax, 1
0x18003b00e  mov     rsi, [rsp+28h+arg_8]
0x18003b013  add     rsp, 20h
0x18003b017  pop     rdi
0x18003b018  retn
```
