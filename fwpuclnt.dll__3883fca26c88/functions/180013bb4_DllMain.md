# DllMain

- ea: `0x180013bb4`
- end: `0x180013ce8`
- name: `DllMain`
- size: `308`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012a44`

## callees

- `0x180007b60`
- `0x180007c78`
- `0x180007e38`
- `0x18000cc40`
- `0x18000cd30`
- `0x18000cde0`
- `0x180013bb4`

## import_xrefs

- `ntdll!EtwUnregisterTraceGuids` at `0x180013cb0`
- `ntdll!EtwUnregisterTraceGuids` at `0x180013cb0`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180013bd6`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180013bd6`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v3; // rdi
  __int64 v4; // rax
  _QWORD *v5; // rbx

  v3 = 0;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      qword_18007C890 = 0;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_FWPUCLNT;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      WPP_MAIN_CB = 0;
      qword_18007C898 = 1;
      WppInitUm();
      v3 = WfpCriticalSectionCreate(&gFwppInitializationLock);
      if ( !v3 )
      {
        gFwpProcessShutdown = 0;
        v4 = WfpComponentsStart(&FWPP_COMPONENTS);
        v3 = v4;
        if ( v4 )
          WfpReportError(v4, "FwppInit");
        else
          gFwppInitialized = 1;
      }
    }
  }
  else
  {
    if ( gFwppInitialized )
    {
      FwppShutdown(lpvReserved != 0);
      gFwppInitialized = 0;
    }
    WfpCriticalSectionDestroy(&gFwppInitializationLock);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      while ( v5 )
      {
        if ( v5[1] )
        {
          EtwUnregisterTraceGuids();
          v5[1] = 0;
        }
        v5 = (_QWORD *)*v5;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return v3 == 0;
}

```

## disassembly

```asm
0x180013bb4  mov     [rsp+arg_0], rbx
0x180013bb9  mov     [rsp+arg_8], rbp
0x180013bbe  push    rdi
0x180013bbf  sub     rsp, 20h
0x180013bc3  xor     edi, edi
0x180013bc5  test    edx, edx
0x180013bc7  jz      loc_180013C6B
0x180013bcd  cmp     edx, 1
0x180013bd0  jnz     loc_180013CCF
0x180013bd6  call    cs:__imp_DisableThreadLibraryCalls
0x180013bdd  nop     dword ptr [rax+rax+00h]
0x180013be2  lea     rax, WPP_ThisDir_CTLGUID_FWPUCLNT
0x180013be9  mov     cs:qword_18007C890, rdi
0x180013bf0  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180013bf7  lea     rax, WPP_MAIN_CB
0x180013bfe  mov     cs:WPP_GLOBAL_Control, rax
0x180013c05  mov     cs:WPP_MAIN_CB, rdi
0x180013c0c  mov     cs:qword_18007C898, 1
0x180013c17  call    WppInitUm
0x180013c1c  lea     rcx, gFwppInitializationLock
0x180013c23  call    WfpCriticalSectionCreate
0x180013c28  mov     rdi, rax
0x180013c2b  test    rax, rax
0x180013c2e  jnz     loc_180013CCF
0x180013c34  mov     cs:gFwpProcessShutdown, eax
0x180013c3a  lea     rcx, FWPP_COMPONENTS
0x180013c41  call    WfpComponentsStart
0x180013c46  mov     rdi, rax
0x180013c49  test    rax, rax
0x180013c4c  jz      short loc_180013C5F
0x180013c4e  lea     rdx, aFwppinit; "FwppInit"
0x180013c55  mov     rcx, rax
0x180013c58  call    WfpReportError
0x180013c5d  jmp     short loc_180013CCF
0x180013c5f  mov     cs:gFwppInitialized, 1
0x180013c69  jmp     short loc_180013CCF
0x180013c6b  cmp     cs:gFwppInitialized, edi
0x180013c71  jz      short loc_180013C86
0x180013c73  xor     ecx, ecx
0x180013c75  test    r8, r8
0x180013c78  setnz   cl
0x180013c7b  call    FwppShutdown
0x180013c80  mov     cs:gFwppInitialized, edi
0x180013c86  lea     rcx, gFwppInitializationLock
0x180013c8d  call    WfpCriticalSectionDestroy
0x180013c92  mov     rbx, cs:WPP_GLOBAL_Control
0x180013c99  lea     rbp, WPP_GLOBAL_Control
0x180013ca0  cmp     rbx, rbp
0x180013ca3  jz      short loc_180013CCF
0x180013ca5  jmp     short loc_180013CC3
0x180013ca7  mov     rcx, [rbx+8]
0x180013cab  test    rcx, rcx
0x180013cae  jz      short loc_180013CC0
0x180013cb0  call    cs:__imp_EtwUnregisterTraceGuids
0x180013cb7  nop     dword ptr [rax+rax+00h]
0x180013cbc  mov     [rbx+8], rdi
0x180013cc0  mov     rbx, [rbx]
0x180013cc3  test    rbx, rbx
0x180013cc6  jnz     short loc_180013CA7
0x180013cc8  mov     cs:WPP_GLOBAL_Control, rbp
0x180013ccf  mov     rbx, [rsp+28h+arg_0]
0x180013cd4  xor     eax, eax
0x180013cd6  mov     rbp, [rsp+28h+arg_8]
0x180013cdb  test    rdi, rdi
0x180013cde  setz    al
0x180013ce1  add     rsp, 20h
0x180013ce5  pop     rdi
0x180013ce6  retn
```
