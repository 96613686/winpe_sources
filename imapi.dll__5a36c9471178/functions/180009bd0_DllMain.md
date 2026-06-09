# DllMain

- ea: `0x180009bd0`
- end: `0x180009deb`
- name: `DllMain`
- size: `539`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001484`

## callees

- `0x1800092d0`
- `0x180009bd0`
- `0x180019010`

## import_xrefs

- `ADVAPI32!UnregisterTraceGuids` at `0x180009d4a`
- `ADVAPI32!UnregisterTraceGuids` at `0x180009d4a`
- `ADVAPI32!RegisterTraceGuidsW` at `0x180009c93`
- `ADVAPI32!RegisterTraceGuidsW` at `0x180009c93`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180009d17`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180009d17`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  ULONG64 *v4; // rdi
  const GUID **v5; // rsi
  const GUID *v6; // r8
  __int64 v7; // rcx
  void (__fastcall **v8)(_QWORD); // rdi
  struct ATL::_ATL_OBJMAP_ENTRY30 **v9; // rdi
  __int64 *v10; // rax
  _QWORD *v11; // rdi
  TRACEHANDLE v12; // rcx
  _QWORD *v13; // rdi
  __int64 v14; // rcx
  void (__fastcall *v15)(_QWORD); // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v16; // rdi
  __int64 *v17; // rax
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-38h] BYREF

  if ( fdwReason == 1 )
  {
    qword_180022AB8 = 1;
    qword_180022AB0 = 0;
    WPP_MAIN_CB = (__int64)&qword_180022AC8;
    v4 = (ULONG64 *)&WPP_MAIN_CB;
    qword_180022AD8 = 0;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_MsftUtils;
    v5 = (const GUID **)&WPP_REGISTRATION_GUIDS;
    qword_180022AC8 = 0;
    qword_180022AF8 = (__int64)WPP_ThisDir_CTLGUID_ImapiV1Shim;
    qword_180022AE0 = 1;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    do
    {
      v6 = *v5;
      TraceGuidReg.Guid = v6;
      ++v5;
      TraceGuidReg.RegHandle = 0;
      v4[4] = (ULONG64)v6;
      RegisterTraceGuidsW(WppControlCallback, v4, v6, 1u, &TraceGuidReg, 0, 0, v4 + 1);
      v4 = (ULONG64 *)*v4;
    }
    while ( v4 );
    v8 = (void (__fastcall **)(_QWORD))&off_1800210A0;
    ATL::CAtlModule::m_libid = LIBID_IMAPILib;
    if ( &off_1800210A0 != (_UNKNOWN *)-1LL )
    {
      qword_180022B48 = (__int64)&off_1800210A0;
      if ( off_1800210A0 )
      {
        do
        {
          LOBYTE(v7) = 1;
          v8[8](v7);
          v8 += 9;
        }
        while ( *v8 );
      }
    }
    v9 = off_1800213E0;
    v10 = off_1800213E8;
    while ( v9 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v10 )
    {
      if ( *v9 )
      {
        LOBYTE(v7) = 1;
        (*((void (__fastcall **)(__int64))*v9 + 8))(v7);
        v10 = off_1800213E8;
      }
      ++v9;
    }
    DisableThreadLibraryCalls(hinstDLL);
  }
  else if ( !fdwReason )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      while ( v11 )
      {
        v12 = v11[1];
        if ( v12 )
        {
          UnregisterTraceGuids(v12);
          v11[1] = 0;
        }
        v11 = (_QWORD *)*v11;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
    v13 = (_QWORD *)qword_180022B48;
    if ( qword_180022B48 )
    {
      while ( *v13 )
      {
        v14 = v13[4];
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        v15 = (void (__fastcall *)(_QWORD))v13[8];
        v13[4] = 0;
        v15(0);
        v13 += 9;
      }
    }
    v16 = off_1800213E0;
    v17 = off_1800213E8;
    while ( v16 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v17 )
    {
      if ( *v16 )
      {
        (*((void (__fastcall **)(_QWORD))*v16 + 8))(0);
        v17 = off_1800213E8;
      }
      ++v16;
    }
    ATL::CAtlModule::Term((ATL::CAtlModule *)&_Module);
  }
  return 1;
}

```

## disassembly

```asm
0x180009bd0  push    rbx
0x180009bd2  push    rbp
0x180009bd3  push    rsi
0x180009bd4  push    rdi
0x180009bd5  sub     rsp, 58h
0x180009bd9  mov     rbp, rcx
0x180009bdc  cmp     edx, 1
0x180009bdf  jnz     loc_180009D22
0x180009be5  xor     ebx, ebx
0x180009be7  mov     cs:qword_180022AB8, 1
0x180009bf2  lea     rax, qword_180022AC8
0x180009bf9  mov     cs:qword_180022AB0, rbx
0x180009c00  mov     cs:WPP_MAIN_CB, rax
0x180009c07  lea     rdi, WPP_MAIN_CB
0x180009c0e  lea     rax, WPP_ThisDir_CTLGUID_MsftUtils
0x180009c15  mov     cs:qword_180022AD8, rbx
0x180009c1c  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180009c23  lea     rsi, WPP_REGISTRATION_GUIDS
0x180009c2a  lea     rax, WPP_ThisDir_CTLGUID_ImapiV1Shim
0x180009c31  mov     cs:qword_180022AC8, rbx
0x180009c38  mov     cs:qword_180022AF8, rax
0x180009c3f  mov     cs:qword_180022AE0, 1
0x180009c4a  mov     cs:WPP_GLOBAL_Control, rdi
0x180009c51  mov     r8, [rsi]; ControlGuid
0x180009c54  lea     rax, [rdi+8]
0x180009c58  mov     [rsp+78h+RegistrationHandle], rax; RegistrationHandle
0x180009c5d  lea     rcx, WppControlCallback; RequestAddress
0x180009c64  mov     [rsp+78h+MofResourceName], rbx; MofResourceName
0x180009c69  lea     rax, [rsp+78h+var_38]
0x180009c6e  mov     [rsp+78h+var_38.Guid], r8
0x180009c73  lea     rsi, [rsi+8]
0x180009c77  mov     [rsp+78h+var_38.RegHandle], rbx
0x180009c7c  mov     r9d, 1; GuidCount
0x180009c82  mov     [rsp+78h+MofImagePath], rbx; MofImagePath
0x180009c87  mov     rdx, rdi; RequestContext
0x180009c8a  mov     [rsp+78h+TraceGuidReg], rax; TraceGuidReg
0x180009c8f  mov     [rdi+20h], r8
0x180009c93  call    cs:__imp_RegisterTraceGuidsW
0x180009c99  mov     rdi, [rdi]
0x180009c9c  test    rdi, rdi
0x180009c9f  jnz     short loc_180009C51
0x180009ca1  movups  xmm0, xmmword ptr cs:LIBID_IMAPILib.Data1
0x180009ca8  lea     rdi, off_1800210A0
0x180009caf  movdqu  xmmword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, xmm0; _GUID ATL::CAtlModule::m_libid ...
0x180009cb7  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180009cbb  jz      short loc_180009CE1
0x180009cbd  cmp     cs:off_1800210A0, rbx
0x180009cc4  mov     cs:qword_180022B48, rdi
0x180009ccb  jz      short loc_180009CE1
0x180009ccd  mov     rax, [rdi+40h]
0x180009cd1  mov     cl, 1
0x180009cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cd8  lea     rdi, [rdi+48h]
0x180009cdc  cmp     [rdi], rbx
0x180009cdf  jnz     short loc_180009CCD
0x180009ce1  mov     rdi, cs:off_1800213E0
0x180009ce8  mov     rax, cs:off_1800213E8
0x180009cef  jmp     short loc_180009D0F
0x180009cf1  mov     rdx, [rdi]
0x180009cf4  test    rdx, rdx
0x180009cf7  jz      short loc_180009D0B
0x180009cf9  mov     rax, [rdx+40h]
0x180009cfd  mov     cl, 1
0x180009cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d04  mov     rax, cs:off_1800213E8
0x180009d0b  add     rdi, 8
0x180009d0f  cmp     rdi, rax
0x180009d12  jb      short loc_180009CF1
0x180009d14  mov     rcx, rbp; hLibModule
0x180009d17  call    cs:__imp_DisableThreadLibraryCalls
0x180009d1d  jmp     loc_180009DDD
0x180009d22  xor     ebx, ebx
0x180009d24  test    edx, edx
0x180009d26  jnz     loc_180009DDD
0x180009d2c  mov     rdi, cs:WPP_GLOBAL_Control
0x180009d33  lea     rsi, WPP_GLOBAL_Control
0x180009d3a  cmp     rdi, rsi
0x180009d3d  jz      short loc_180009D63
0x180009d3f  jmp     short loc_180009D57
0x180009d41  mov     rcx, [rdi+8]; RegistrationHandle
0x180009d45  test    rcx, rcx
0x180009d48  jz      short loc_180009D54
0x180009d4a  call    cs:__imp_UnregisterTraceGuids
0x180009d50  mov     [rdi+8], rbx
0x180009d54  mov     rdi, [rdi]
0x180009d57  test    rdi, rdi
0x180009d5a  jnz     short loc_180009D41
0x180009d5c  mov     cs:WPP_GLOBAL_Control, rsi
0x180009d63  mov     rdi, cs:qword_180022B48
0x180009d6a  test    rdi, rdi
0x180009d6d  jz      short loc_180009D9E
0x180009d6f  jmp     short loc_180009D99
0x180009d71  mov     rcx, [rdi+20h]
0x180009d75  test    rcx, rcx
0x180009d78  jz      short loc_180009D86
0x180009d7a  mov     rax, [rcx]
0x180009d7d  mov     rax, [rax+10h]
0x180009d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d86  mov     rax, [rdi+40h]
0x180009d8a  xor     ecx, ecx
0x180009d8c  mov     [rdi+20h], rbx
0x180009d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d95  add     rdi, 48h ; 'H'
0x180009d99  cmp     [rdi], rbx
0x180009d9c  jnz     short loc_180009D71
0x180009d9e  mov     rdi, cs:off_1800213E0
0x180009da5  mov     rax, cs:off_1800213E8
0x180009dac  jmp     short loc_180009DCC
0x180009dae  mov     rdx, [rdi]
0x180009db1  test    rdx, rdx
0x180009db4  jz      short loc_180009DC8
0x180009db6  mov     rax, [rdx+40h]
0x180009dba  xor     ecx, ecx
0x180009dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dc1  mov     rax, cs:off_1800213E8
0x180009dc8  add     rdi, 8
0x180009dcc  cmp     rdi, rax
0x180009dcf  jb      short loc_180009DAE
0x180009dd1  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x180009dd8  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x180009ddd  mov     eax, 1
0x180009de2  add     rsp, 58h
0x180009de6  pop     rdi
0x180009de7  pop     rsi
0x180009de8  pop     rbp
0x180009de9  pop     rbx
0x180009dea  retn
```
