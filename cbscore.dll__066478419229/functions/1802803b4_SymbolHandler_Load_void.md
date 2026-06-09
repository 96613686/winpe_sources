# SymbolHandler::Load(void)

- ea: `0x1802803b4`
- end: `0x1802805ee`
- name: `?Load@SymbolHandler@@QEAAXXZ`
- size: `570`
- prototype: `void __fastcall(SymbolHandler *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1802801e0`

## callees

- `0x180010cc0`
- `0x1800bca84`
- `0x1800eb920`
- `0x18011a5dc`
- `0x1802803b4`
- `0x1802d5010`

## import_xrefs

- `ntdll!LdrLoadDll` at `0x180280402`
- `ntdll!LdrLoadDll` at `0x1802804c5`
- `ntdll!LdrLoadDll` at `0x180280402`
- `ntdll!LdrLoadDll` at `0x1802804c5`
- `ntdll!LdrGetProcedureAddress` at `0x18028042f`
- `ntdll!LdrGetProcedureAddress` at `0x180280453`
- `ntdll!LdrGetProcedureAddress` at `0x180280477`
- `ntdll!LdrGetProcedureAddress` at `0x1802804eb`
- `ntdll!LdrGetProcedureAddress` at `0x18028042f`
- `ntdll!LdrGetProcedureAddress` at `0x180280453`
- `ntdll!LdrGetProcedureAddress` at `0x180280477`
- `ntdll!LdrGetProcedureAddress` at `0x1802804eb`

## pseudocode

```c
void __fastcall SymbolHandler::Load(SymbolHandler *this)
{
  PVOID *InitPointer; // rax
  unsigned int v2; // edx
  PVOID *v3; // rax
  unsigned int v4; // edx
  ULONG LastErrorValue; // ecx
  PVOID *p_BaseAddress; // rcx
  struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *v7; // [rsp+30h] [rbp-40h] BYREF
  struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER **v8; // [rsp+38h] [rbp-38h] BYREF
  PVOID BaseAddress; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v10[3]; // [rsp+48h] [rbp-28h] BYREF

  if ( g_SymbolHandler )
  {
    ++g_SymbolHandler;
  }
  else
  {
    InitPointer = (PVOID *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&qword_1803B24F8);
    LdrLoadDll(
      0,
      0,
      (PUNICODE_STRING)&___LiteralObject__2U__BaseLiteralBuffer__0M_U_UNICODE_STRING___W_Details_RtlStringLiterals__3_W0EE__0GC__0GH__0GI__0GF__0GM__0HA__0CO__0GE__0GM__0GM__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__Details_RtlStringLiterals__3U_UNICODE_STRING__B,
      InitPointer);
    if ( qword_1803B24F8 )
    {
      LdrGetProcedureAddress(
        qword_1803B24F8,
        (PANSI_STRING)&___LiteralObject__2U__BaseLiteralBuffer__0M_U_STRING__D_Details_RtlStringLiterals__3D0FD__0HJ__0GN__0EG__0HC__0GP__0GN__0EB__0GE__0GE__0HC__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__Details_RtlStringLiterals__3U_STRING__B,
        0,
        &qword_1803B2500);
      LdrGetProcedureAddress(
        qword_1803B24F8,
        (PANSI_STRING)&___LiteralObject__2U__BaseLiteralBuffer__0O_U_STRING__D_Details_RtlStringLiterals__3D0FD__0HJ__0GN__0EJ__0GO__0GJ__0HE__0GJ__0GB__0GM__0GJ__0HK__0GF__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__Details_RtlStringLiterals__3U_STRING__B,
        0,
        &qword_1803B2508);
      LdrGetProcedureAddress(
        qword_1803B24F8,
        (PANSI_STRING)&___LiteralObject__2U__BaseLiteralBuffer__0L_U_STRING__D_Details_RtlStringLiterals__3D0FD__0HJ__0GN__0ED__0GM__0GF__0GB__0GO__0HF__0HA__0A_____0A__00_01_02_03_04_05_06_07_08_09_Details_RtlStringLiterals__3U_STRING__B,
        0,
        &qword_1803B2510);
      if ( qword_1803B2508 && qword_1803B2500 && qword_1803B2510 )
      {
        BaseAddress = 0;
        v3 = (PVOID *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&BaseAddress);
        LdrLoadDll(
          0,
          0,
          (PUNICODE_STRING)&___LiteralObject__2U__BaseLiteralBuffer__09U_UNICODE_STRING___W_Details_RtlStringLiterals__3_W0GO__0HE__0GE__0GM__0GM__0CO__0GE__0GM__0GM__0A_____0A__00_01_02_03_04_05_06_07_08_Details_RtlStringLiterals__3U_UNICODE_STRING__B,
          v3);
        if ( BaseAddress )
          LdrGetProcedureAddress(
            BaseAddress,
            (PANSI_STRING)&___LiteralObject__2U__BaseLiteralBuffer__0BC_U_STRING__D_Details_RtlStringLiterals__3D0EM__0GE__0HC__0EH__0GF__0HE__0EE__0GM__0GM__0EG__0HF__0GM__0GM__0EO__0GB__0GN__0GF__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__Details_RtlStringLiterals__3U_STRING__B,
            0,
            &qword_1803B2518);
        if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, __int64))qword_1803B2508)(-1, 0, 1) )
        {
          v10[0] = 0;
          LastErrorValue = NtCurrentTeb()->LastErrorValue;
          v8 = &v7;
          v10[1] = (unsigned __int64)`Windows::WCP::Rtl::RtlAutoTrace<Windows::WCP::Rtl::FormatWin32ErrorWrapper<unsigned long>>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
          v10[2] = (unsigned __int64)&v8;
          LODWORD(v7) = LastErrorValue;
          Windows::WCP::Rtl::RtlTraceFromParameterList(
            0,
            v4,
            (unsigned int)&Windows::WCP::Rtl::Facility_General,
            (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"++ SymInitialize failed with: {0} - not pretty printing backtrace",
            (const char *const)1,
            (unsigned __int64)v10,
            v7);
          qword_1803B2508 = 0;
          qword_1803B2500 = 0;
          qword_1803B2510 = 0;
          Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(&qword_1803B24F8);
        }
        p_BaseAddress = &BaseAddress;
      }
      else
      {
        Windows::WCP::Rtl::RtlTraceFromParameterList(
          0,
          v2,
          (unsigned int)&Windows::WCP::Rtl::Facility_General,
          (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"++ Symbol functions not found - not pretty printing backtrace",
          0,
          0,
          v7);
        p_BaseAddress = &qword_1803B24F8;
        qword_1803B2508 = 0;
        qword_1803B2500 = 0;
        qword_1803B2510 = 0;
      }
      Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(p_BaseAddress);
    }
    ++g_SymbolHandler;
  }
}

```

## disassembly

```asm
0x1802803b4  mov     [rsp-8+arg_0], rbx
0x1802803b9  push    rbp
0x1802803ba  mov     rbp, rsp
0x1802803bd  sub     rsp, 70h
0x1802803c1  mov     rax, cs:__security_cookie
0x1802803c8  xor     rax, rsp
0x1802803cb  mov     [rbp+var_10], rax
0x1802803cf  mov     eax, cs:?g_SymbolHandler@@3VSymbolHandler@@A; SymbolHandler g_SymbolHandler
0x1802803d5  xor     ebx, ebx
0x1802803d7  test    eax, eax
0x1802803d9  jz      short loc_1802803E8
0x1802803db  inc     eax
0x1802803dd  mov     cs:?g_SymbolHandler@@3VSymbolHandler@@A, eax; SymbolHandler g_SymbolHandler
0x1802803e3  jmp     loc_1802805D3
0x1802803e8  lea     rcx, qword_1803B24F8
0x1802803ef  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1802803f4  mov     r9, rax; BaseAddress
0x1802803f7  lea     r8, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0M@U_UNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0EE@@0GC@@0GH@@0GI@@0GF@@0GM@@0HA@@0CO@@0GE@@0GM@@0GM@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@@Details@RtlStringLiterals@@3U_UNICODE_STRING@@B; Name
0x1802803fe  xor     edx, edx; LoadFlags
0x180280400  xor     ecx, ecx; SearchPath
0x180280402  call    cs:__imp_LdrLoadDll
0x180280409  nop     dword ptr [rax+rax+00h]
0x18028040e  mov     rcx, cs:qword_1803B24F8; BaseAddress
0x180280415  test    rcx, rcx
0x180280418  jz      loc_1802805CD
0x18028041e  lea     r9, qword_1803B2500; ProcedureAddress
0x180280425  xor     r8d, r8d; Ordinal
0x180280428  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0M@U_STRING@@D@Details@RtlStringLiterals@@3D0FD@@0HJ@@0GN@@0EG@@0HC@@0GP@@0GN@@0EB@@0GE@@0GE@@0HC@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@@Details@RtlStringLiterals@@3U_STRING@@B; Name
0x18028042f  call    cs:__imp_LdrGetProcedureAddress
0x180280436  nop     dword ptr [rax+rax+00h]
0x18028043b  mov     rcx, cs:qword_1803B24F8; BaseAddress
0x180280442  lea     r9, qword_1803B2508; ProcedureAddress
0x180280449  xor     r8d, r8d; Ordinal
0x18028044c  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0O@U_STRING@@D@Details@RtlStringLiterals@@3D0FD@@0HJ@@0GN@@0EJ@@0GO@@0GJ@@0HE@@0GJ@@0GB@@0GM@@0GJ@@0HK@@0GF@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@@Details@RtlStringLiterals@@3U_STRING@@B; Name
0x180280453  call    cs:__imp_LdrGetProcedureAddress
0x18028045a  nop     dword ptr [rax+rax+00h]
0x18028045f  mov     rcx, cs:qword_1803B24F8; BaseAddress
0x180280466  lea     r9, qword_1803B2510; ProcedureAddress
0x18028046d  xor     r8d, r8d; Ordinal
0x180280470  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0L@U_STRING@@D@Details@RtlStringLiterals@@3D0FD@@0HJ@@0GN@@0ED@@0GM@@0GF@@0GB@@0GO@@0HF@@0HA@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09@Details@RtlStringLiterals@@3U_STRING@@B; Name
0x180280477  call    cs:__imp_LdrGetProcedureAddress
0x18028047e  nop     dword ptr [rax+rax+00h]
0x180280483  cmp     cs:qword_1803B2508, rbx
0x18028048a  jz      loc_18028058D
0x180280490  cmp     cs:qword_1803B2500, rbx
0x180280497  jz      loc_18028058D
0x18028049d  cmp     cs:qword_1803B2510, rbx
0x1802804a4  jz      loc_18028058D
0x1802804aa  lea     rcx, [rbp+BaseAddress]
0x1802804ae  mov     [rbp+BaseAddress], rbx
0x1802804b2  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1802804b7  mov     r9, rax; BaseAddress
0x1802804ba  lea     r8, ??$LiteralObject@$2U?$BaseLiteralBuffer@$09U_UNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0GO@@0HE@@0GE@@0GM@@0GM@@0CO@@0GE@@0GM@@0GM@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08@Details@RtlStringLiterals@@3U_UNICODE_STRING@@B; Name
0x1802804c1  xor     edx, edx; LoadFlags
0x1802804c3  xor     ecx, ecx; SearchPath
0x1802804c5  call    cs:__imp_LdrLoadDll
0x1802804cc  nop     dword ptr [rax+rax+00h]
0x1802804d1  mov     rcx, [rbp+BaseAddress]; BaseAddress
0x1802804d5  test    rcx, rcx
0x1802804d8  jz      short loc_1802804F7
0x1802804da  lea     r9, qword_1803B2518; ProcedureAddress
0x1802804e1  xor     r8d, r8d; Ordinal
0x1802804e4  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0BC@U_STRING@@D@Details@RtlStringLiterals@@3D0EM@@0GE@@0HC@@0EH@@0GF@@0HE@@0EE@@0GM@@0GM@@0EG@@0HF@@0GM@@0GM@@0EO@@0GB@@0GN@@0GF@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@$0P@$0BA@$0BB@@Details@RtlStringLiterals@@3U_STRING@@B; Name
0x1802804eb  call    cs:__imp_LdrGetProcedureAddress
0x1802804f2  nop     dword ptr [rax+rax+00h]
0x1802804f7  mov     rax, cs:qword_1803B2508
0x1802804fe  xor     edx, edx
0x180280500  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180280504  lea     r8d, [rdx+1]
0x180280508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028050d  test    eax, eax
0x18028050f  jnz     short loc_180280587
0x180280511  mov     rax, gs:30h
0x18028051a  lea     r9, aSyminitializeF; "++ SymInitialize failed with: {0} - not"...
0x180280521  lea     r8, ?Facility_General@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x180280528  mov     [rbp+var_28], rbx
0x18028052c  mov     ecx, [rax+68h]
0x18028052f  lea     rax, [rbp+var_40]
0x180280533  mov     [rbp+var_38], rax
0x180280537  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlAutoTrace@U?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@234@QEBDAEBU?$FormatWin32ErrorWrapper@K@234@@Z@SA@PEAUIRtlFormattedOutputStream@24@PEBX@Z; `Windows::WCP::Rtl::RtlAutoTrace<Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong>>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong> const &)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18028053e  mov     [rbp+var_20], rax
0x180280542  lea     rax, [rbp+var_38]
0x180280546  mov     [rbp+var_18], rax
0x18028054a  lea     rax, [rbp+var_28]
0x18028054e  mov     dword ptr [rbp+var_40], ecx
0x180280551  xor     ecx, ecx; this
0x180280553  mov     [rsp+70h+var_48], rax; unsigned __int64
0x180280558  mov     [rsp+70h+var_50], 1; char *
0x180280561  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x180280566  lea     rcx, qword_1803B24F8
0x18028056d  mov     cs:qword_1803B2508, rbx
0x180280574  mov     cs:qword_1803B2500, rbx
0x18028057b  mov     cs:qword_1803B2510, rbx
0x180280582  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithLdrUnloadDll@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(void)
0x180280587  lea     rcx, [rbp+BaseAddress]
0x18028058b  jmp     short loc_1802805C8
0x18028058d  mov     [rsp+70h+var_48], rbx; unsigned __int64
0x180280592  lea     r9, aSymbolFunction; "++ Symbol functions not found - not pre"...
0x180280599  lea     r8, ?Facility_General@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x1802805a0  mov     [rsp+70h+var_50], rbx; char *
0x1802805a5  xor     ecx, ecx; this
0x1802805a7  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x1802805ac  lea     rcx, qword_1803B24F8
0x1802805b3  mov     cs:qword_1803B2508, rbx
0x1802805ba  mov     cs:qword_1803B2500, rbx
0x1802805c1  mov     cs:qword_1803B2510, rbx
0x1802805c8  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithLdrUnloadDll@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(void)
0x1802805cd  inc     cs:?g_SymbolHandler@@3VSymbolHandler@@A; SymbolHandler g_SymbolHandler
0x1802805d3  mov     rcx, [rbp+var_10]
0x1802805d7  xor     rcx, rsp; StackCookie
0x1802805da  call    __security_check_cookie
0x1802805df  mov     rbx, [rsp+70h+arg_0]
0x1802805e7  add     rsp, 70h
0x1802805eb  pop     rbp
0x1802805ec  retn
```
