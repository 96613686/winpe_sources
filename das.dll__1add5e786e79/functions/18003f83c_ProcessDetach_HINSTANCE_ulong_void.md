# ProcessDetach(HINSTANCE__ *,ulong,void *)

- ea: `0x18003f83c`
- end: `0x18003f8e0`
- name: `?ProcessDetach@@YAXPEAUHINSTANCE__@@KPEAX@Z`
- size: `164`
- prototype: `void __fastcall(HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180041828`

## callees

- `0x18003f83c`

## import_xrefs

- `WppRecorderUM!WppAutoLogStop` at `0x18003f8ba`
- `WppRecorderUM!WppAutoLogStop` at `0x18003f8ba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003f85e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003f85e`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18003f89a`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18003f89a`

## pseudocode

```c
void __fastcall ProcessDetach(HINSTANCE a1, __int64 a2, void *a3)
{
  int v3; // eax
  _QWORD *v4; // rbx
  TRACEHANDLE v5; // rcx

  while ( 1 )
  {
    v3 = g_cDasCritSecInit;
    if ( g_cDasCritSecInit <= 0 )
      break;
    --g_cDasCritSecInit;
    DeleteCriticalSection((LPCRITICAL_SECTION)(&g_pcsDasCritSecInit)[v3 - 1]);
  }
  v4 = WPP_GLOBAL_Control;
  wil::details::g_pfnLoggingCallback = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( WPP_GLOBAL_Control )
    {
      do
      {
        v5 = v4[1];
        if ( v5 )
        {
          UnregisterTraceGuids(v5);
          v4[1] = 0;
        }
        v4 = (_QWORD *)*v4;
      }
      while ( v4 );
      v4 = WPP_GLOBAL_Control;
    }
    WppAutoLogStop(v4, a2, a3);
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    *(_QWORD *)&WPP_RECORDER_INITIALIZED = &WPP_RECORDER_INITIALIZED;
  }
}

```

## disassembly

```asm
0x18003f83c  mov     [rsp+arg_0], rbx
0x18003f841  push    rdi
0x18003f842  sub     rsp, 20h
0x18003f846  jmp     short loc_18003F864
0x18003f848  dec     eax
0x18003f84a  movsxd  rcx, eax
0x18003f84d  mov     cs:?g_cDasCritSecInit@@3HA, eax; int g_cDasCritSecInit
0x18003f853  lea     rax, ?g_pcsDasCritSecInit@@3PAPEAU_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION * near * g_pcsDasCritSecInit
0x18003f85a  mov     rcx, [rax+rcx*8]; lpCriticalSection
0x18003f85e  call    cs:__imp_DeleteCriticalSection
0x18003f864  mov     eax, cs:?g_cDasCritSecInit@@3HA; int g_cDasCritSecInit
0x18003f86a  test    eax, eax
0x18003f86c  jg      short loc_18003F848
0x18003f86e  mov     rbx, cs:WPP_GLOBAL_Control
0x18003f875  lea     rdi, WPP_GLOBAL_Control
0x18003f87c  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, 0
0x18003f887  cmp     rbx, rdi
0x18003f88a  jz      short loc_18003F8D5
0x18003f88c  test    rbx, rbx
0x18003f88f  jz      short loc_18003F8B7
0x18003f891  mov     rcx, [rbx+8]; RegistrationHandle
0x18003f895  test    rcx, rcx
0x18003f898  jz      short loc_18003F8A8
0x18003f89a  call    cs:__imp_UnregisterTraceGuids
0x18003f8a0  mov     qword ptr [rbx+8], 0
0x18003f8a8  mov     rbx, [rbx]
0x18003f8ab  test    rbx, rbx
0x18003f8ae  jnz     short loc_18003F891
0x18003f8b0  mov     rbx, cs:WPP_GLOBAL_Control
0x18003f8b7  mov     rcx, rbx
0x18003f8ba  call    cs:__imp_WppAutoLogStop
0x18003f8c0  lea     rax, WPP_RECORDER_INITIALIZED
0x18003f8c7  mov     cs:WPP_GLOBAL_Control, rdi
0x18003f8ce  mov     cs:WPP_RECORDER_INITIALIZED, rax
0x18003f8d5  mov     rbx, [rsp+28h+arg_0]
0x18003f8da  add     rsp, 20h
0x18003f8de  pop     rdi
0x18003f8df  retn
```
