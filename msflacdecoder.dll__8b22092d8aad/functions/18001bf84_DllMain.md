# DllMain

- ea: `0x18001bf84`
- end: `0x18001c1c5`
- name: `DllMain`
- size: `577`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180001cf4`

## callees

- `0x180001008`
- `0x1800010b8`
- `0x18001b74c`
- `0x18001bf84`
- `0x18001c36c`
- `0x18001c5a4`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001c077`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001c077`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18001c116`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18001c116`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=1
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  HINSTANCE v3; // rbx
  __int64 v4; // rcx
  void (__fastcall **v5)(_QWORD); // rdi
  __int64 *v6; // rdi
  __int64 *v7; // rax
  PVOID v8; // rdi
  __int64 v9; // rdi
  __int64 v10; // rcx
  __int64 *v11; // rdi
  __int64 *v12; // rax

  v3 = hinstDLL;
  if ( fdwReason == 1 )
  {
    WPP_INIT_CONTROL_ARRAY(hinstDLL, fdwReason, lpvReserved);
    WPP_REGISTRATION_GUIDS = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_PLATFORM;
    qword_18006EA68 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_PIPELINE;
    qword_18006EA70 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_CORE_SINKS;
    qword_18006EA78 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_CORE_SOURCES;
    qword_18006EA80 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_NETWORK;
    qword_18006EA88 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_CORE_MFTS;
    qword_18006EA90 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_PLAY;
    qword_18006EA98 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_CAPTURE_ENGINE;
    qword_18006EAA0 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_VIDEO_PROCESSOR;
    qword_18006EAA8 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_PIPELINE_HIGH_VOLUME;
    qword_18006EAB0 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_TEMP_DEBUG_REFCOUNT_TRACE;
    qword_18006EAB8 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_PERSAMPLE_INFO_TRACE;
    qword_18006EAC0 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_CAMERA_SETTINGS_HANDLERS;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WppInitUm();
    g_TransformDLLInstance = v3;
    DisableThreadLibraryCalls(v3);
    v5 = (void (__fastcall **)(_QWORD))&off_18006E020;
    if ( &off_18006E020 != (_UNKNOWN *)-1LL )
    {
      qword_18006EB18 = (__int64)&off_18006E020;
      if ( off_18006E020 )
      {
        do
        {
          LOBYTE(v4) = 1;
          v5[8](v4);
          v5 += 9;
        }
        while ( *v5 );
      }
    }
    v6 = off_18006E270[0];
    v7 = off_18006E278;
    while ( v6 < v7 )
    {
      if ( *v6 )
      {
        LOBYTE(v4) = 1;
        (*(void (__fastcall **)(__int64))(*v6 + 64))(v4);
        v7 = off_18006E278;
      }
      ++v6;
    }
    TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  }
  else if ( !fdwReason )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      while ( v8 )
      {
        hinstDLL = (HINSTANCE)*((_QWORD *)v8 + 1);
        if ( hinstDLL )
        {
          UnregisterTraceGuids((TRACEHANDLE)hinstDLL);
          *((_QWORD *)v8 + 1) = 0;
        }
        v8 = *(PVOID *)v8;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
    TraceLoggingUnregister_EventUnregister(hinstDLL, *(_QWORD *)&fdwReason, lpvReserved);
    v9 = qword_18006EB18;
    if ( qword_18006EB18 )
    {
      while ( *(_QWORD *)v9 )
      {
        v10 = *(_QWORD *)(v9 + 32);
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        *(_QWORD *)(v9 + 32) = 0;
        (*(void (__fastcall **)(_QWORD))(v9 + 64))(0);
        v9 += 72;
      }
    }
    v11 = off_18006E270[0];
    v12 = off_18006E278;
    while ( v11 < v12 )
    {
      if ( *v11 )
      {
        (*(void (__fastcall **)(_QWORD))(*v11 + 64))(0);
        v12 = off_18006E278;
      }
      ++v11;
    }
    ATL::CAtlModule::Term((ATL::CAtlModule *)&_Module);
  }
  return 1;
}

```

## disassembly

```asm
0x18001bf84  mov     [rsp+arg_0], rbx
0x18001bf89  mov     [rsp+arg_8], rsi
0x18001bf8e  push    rdi
0x18001bf8f  sub     rsp, 20h
0x18001bf93  mov     rbx, rcx
0x18001bf96  cmp     edx, 1
0x18001bf99  jnz     loc_18001C0EE
0x18001bf9f  call    WPP_INIT_CONTROL_ARRAY
0x18001bfa4  lea     rdx, WPP_ThisDir_CTLGUID_CTRLGUID_MF_PLATFORM
0x18001bfab  mov     cs:WPP_REGISTRATION_GUIDS, rdx
0x18001bfb2  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_PIPELINE
0x18001bfb9  mov     cs:qword_18006EA68, rax
0x18001bfc0  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_CORE_SINKS
0x18001bfc7  mov     cs:qword_18006EA70, rax
0x18001bfce  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_CORE_SOURCES
0x18001bfd5  mov     cs:qword_18006EA78, rax
0x18001bfdc  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_NETWORK
0x18001bfe3  mov     cs:qword_18006EA80, rax
0x18001bfea  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_CORE_MFTS
0x18001bff1  mov     cs:qword_18006EA88, rax
0x18001bff8  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_PLAY
0x18001bfff  mov     cs:qword_18006EA90, rax
0x18001c006  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_CAPTURE_ENGINE
0x18001c00d  mov     cs:qword_18006EA98, rax
0x18001c014  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_VIDEO_PROCESSOR
0x18001c01b  mov     cs:qword_18006EAA0, rax
0x18001c022  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_PIPELINE_HIGH_VOLUME
0x18001c029  mov     cs:qword_18006EAA8, rax
0x18001c030  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_TEMP_DEBUG_REFCOUNT_TRACE
0x18001c037  mov     cs:qword_18006EAB0, rax
0x18001c03e  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_PERSAMPLE_INFO_TRACE
0x18001c045  mov     cs:qword_18006EAB8, rax
0x18001c04c  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_CAMERA_SETTINGS_HANDLERS
0x18001c053  mov     cs:qword_18006EAC0, rax
0x18001c05a  lea     rax, WPP_MAIN_CB
0x18001c061  mov     cs:WPP_GLOBAL_Control, rax
0x18001c068  call    WppInitUm
0x18001c06d  mov     cs:?g_TransformDLLInstance@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_TransformDLLInstance
0x18001c074  mov     rcx, rbx; hLibModule
0x18001c077  call    cs:__imp_DisableThreadLibraryCalls
0x18001c07d  nop
0x18001c07e  lea     rdi, off_18006E020
0x18001c085  xor     ebx, ebx
0x18001c087  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001c08b  jz      short loc_18001C0B1
0x18001c08d  mov     cs:qword_18006EB18, rdi
0x18001c094  cmp     cs:off_18006E020, rbx
0x18001c09b  jz      short loc_18001C0B1
0x18001c09d  mov     cl, 1
0x18001c09f  mov     rax, [rdi+40h]
0x18001c0a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0a8  lea     rdi, [rdi+48h]
0x18001c0ac  cmp     [rdi], rbx
0x18001c0af  jnz     short loc_18001C09D
0x18001c0b1  mov     rdi, cs:off_18006E270
0x18001c0b8  mov     rax, cs:off_18006E278
0x18001c0bf  jmp     short loc_18001C0DF
0x18001c0c1  mov     rdx, [rdi]
0x18001c0c4  test    rdx, rdx
0x18001c0c7  jz      short loc_18001C0DB
0x18001c0c9  mov     cl, 1
0x18001c0cb  mov     rax, [rdx+40h]
0x18001c0cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0d4  mov     rax, cs:off_18006E278
0x18001c0db  add     rdi, 8
0x18001c0df  cmp     rdi, rax
0x18001c0e2  jb      short loc_18001C0C1
0x18001c0e4  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001c0e9  jmp     loc_18001C1B0
0x18001c0ee  xor     ebx, ebx
0x18001c0f0  test    edx, edx
0x18001c0f2  jnz     loc_18001C1B0
0x18001c0f8  lea     rsi, WPP_GLOBAL_Control
0x18001c0ff  mov     rdi, cs:WPP_GLOBAL_Control
0x18001c106  cmp     rdi, rsi
0x18001c109  jz      short loc_18001C12F
0x18001c10b  jmp     short loc_18001C123
0x18001c10d  mov     rcx, [rdi+8]; RegistrationHandle
0x18001c111  test    rcx, rcx
0x18001c114  jz      short loc_18001C120
0x18001c116  call    cs:__imp_UnregisterTraceGuids
0x18001c11c  mov     [rdi+8], rbx
0x18001c120  mov     rdi, [rdi]
0x18001c123  test    rdi, rdi
0x18001c126  jnz     short loc_18001C10D
0x18001c128  mov     cs:WPP_GLOBAL_Control, rsi
0x18001c12f  call    TraceLoggingUnregister_EventUnregister
0x18001c134  nop
0x18001c135  mov     rdi, cs:qword_18006EB18
0x18001c13c  test    rdi, rdi
0x18001c13f  jz      short loc_18001C170
0x18001c141  jmp     short loc_18001C16B
0x18001c143  mov     rcx, [rdi+20h]
0x18001c147  test    rcx, rcx
0x18001c14a  jz      short loc_18001C158
0x18001c14c  mov     rax, [rcx]
0x18001c14f  mov     rax, [rax+10h]
0x18001c153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c158  mov     [rdi+20h], rbx
0x18001c15c  xor     ecx, ecx
0x18001c15e  mov     rax, [rdi+40h]
0x18001c162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c167  add     rdi, 48h ; 'H'
0x18001c16b  cmp     [rdi], rbx
0x18001c16e  jnz     short loc_18001C143
0x18001c170  mov     rdi, cs:off_18006E270
0x18001c177  mov     rax, cs:off_18006E278
0x18001c17e  jmp     short loc_18001C19E
0x18001c180  mov     rdx, [rdi]
0x18001c183  test    rdx, rdx
0x18001c186  jz      short loc_18001C19A
0x18001c188  xor     ecx, ecx
0x18001c18a  mov     rax, [rdx+40h]
0x18001c18e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c193  mov     rax, cs:off_18006E278
0x18001c19a  add     rdi, 8
0x18001c19e  cmp     rdi, rax
0x18001c1a1  jb      short loc_18001C180
0x18001c1a3  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x18001c1aa  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18001c1af  nop
0x18001c1b0  mov     eax, 1
0x18001c1b5  mov     rbx, [rsp+28h+arg_0]
0x18001c1ba  mov     rsi, [rsp+28h+arg_8]
0x18001c1bf  add     rsp, 20h
0x18001c1c3  pop     rdi
0x18001c1c4  retn
```
