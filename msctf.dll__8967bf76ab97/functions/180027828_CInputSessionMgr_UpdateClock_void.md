# CInputSessionMgr::UpdateClock(void)

- ea: `0x180027828`
- end: `0x1800279c1`
- name: `?UpdateClock@CInputSessionMgr@@QEAAXXZ`
- size: `409`
- prototype: `void __fastcall(CInputSessionMgr *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x1800273c0`
- `0x1800273e0`

## callees

- `0x18002715c`
- `0x180027330`
- `0x180027828`
- `0x1800288e8`
- `0x180028a5c`
- `0x1800341b4`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18002799d`
- `msvcrt!wcsncpy_s` at `0x18002799d`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180027976`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180027976`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027899`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027899`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180027834`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180027834`

## pseudocode

```c
void __fastcall CInputSessionMgr::UpdateClock(CInputSessionMgr *this)
{
  ULONGLONG TickCount64; // rax
  unsigned __int64 v3; // rdx
  __int64 v4; // rcx
  int v5; // eax
  WCHAR *v6; // rdi
  unsigned int v7; // edi
  __int64 v8; // rcx
  __int64 v9; // r8
  const wchar_t *v10; // rsi
  int StringOrdinal; // eax
  LPCWSTR lpStringSource; // [rsp+A0h] [rbp+8h] BYREF

  TickCount64 = GetTickCount64();
  *((_QWORD *)this + 10) = TickCount64;
  if ( !*((_BYTE *)this + 207) )
  {
    *((_QWORD *)this + 8) = TickCount64;
    *((_BYTE *)this + 207) = 1;
    if ( !*((_DWORD *)this + 75) )
    {
      lpStringSource = 0;
      v5 = wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void Internal_CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>(
             v4,
             v3,
             &lpStringSource);
      v6 = (WCHAR *)lpStringSource;
      if ( v5 >= 0 )
      {
        v9 = -1;
        do
          ++v9;
        while ( lpStringSource[v9] );
        v10 = &lpStringSource[v9];
        if ( v9 && *(v10 - 1) == 92 )
          LODWORD(v9) = v9 - 1;
        StringOrdinal = FindStringOrdinal(0x800000u, lpStringSource, v9, L"\\", 1, 1);
        if ( StringOrdinal != -1 )
          v10 = &v6[StringOrdinal + 1];
        wcsncpy_s((wchar_t *)this + 106, 0x29u, v10, 0xFFFFFFFFFFFFFFFFuLL);
      }
      else
      {
        *((_WORD *)this + 106) = 0;
      }
      *((_DWORD *)this + 75) = GetCurrentProcessId();
      if ( v6 )
        Internal_CoTaskMemFree(v6);
    }
    v7 = *((_DWORD *)this + 50);
    if ( CtfTraceLoggingTelemetry::IsEnabled(v4, v3) )
    {
      wil::details::static_lazy<CtfTraceLoggingTelemetry>::get(
        v8,
        _lambda_713764b823f33d19dde9f3ebd9e274e0_::_lambda_invoker_cdecl_);
      CtfTraceLoggingTelemetry::InputSessionStarted_(
        (CInputSessionMgr *)((char *)this + 168),
        (const unsigned __int16 *)this + 106,
        *((_DWORD *)this + 75),
        (const struct _GUID *)((char *)this + 152),
        (const struct _GUID *)((char *)this + 168),
        *((_WORD *)this + 92),
        *((_BYTE *)this + 186),
        *((_DWORD *)this + 47),
        *((_DWORD *)this + 48),
        *((_DWORD *)this + 49),
        *((_BYTE *)this + 205),
        v7,
        *((_BYTE *)this + 204));
    }
  }
  *((_QWORD *)this + 9) = *((_QWORD *)this + 10);
}

```

## disassembly

```asm
0x180027828  push    rbx
0x18002782a  push    rbp
0x18002782b  push    rsi
0x18002782c  push    rdi
0x18002782d  sub     rsp, 78h
0x180027831  mov     rbx, rcx
0x180027834  call    cs:__imp_GetTickCount64
0x18002783a  xor     ebp, ebp
0x18002783c  mov     [rbx+50h], rax
0x180027840  cmp     [rbx+0CFh], bpl
0x180027847  jz      short loc_18002785A
0x180027849  mov     rax, [rbx+50h]
0x18002784d  mov     [rbx+48h], rax
0x180027851  add     rsp, 78h
0x180027855  pop     rdi
0x180027856  pop     rsi
0x180027857  pop     rbp
0x180027858  pop     rbx
0x180027859  retn
0x18002785a  mov     [rbx+40h], rax
0x18002785e  mov     byte ptr [rbx+0CFh], 1
0x180027865  cmp     [rbx+12Ch], ebp
0x18002786b  jnz     short loc_1800278AE
0x18002786d  lea     r8, [rsp+98h+lpStringSource]
0x180027875  mov     [rsp+98h+lpStringSource], rbp
0x18002787d  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?Internal_CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?Internal_CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&Internal_CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&Internal_CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180027882  mov     rdi, [rsp+98h+lpStringSource]
0x18002788a  test    eax, eax
0x18002788c  jns     loc_180027940
0x180027892  mov     [rbx+0D4h], bp
0x180027899  call    cs:__imp_GetCurrentProcessId
0x18002789f  mov     [rbx+12Ch], eax
0x1800278a5  test    rdi, rdi
0x1800278a8  jnz     loc_1800279B4
0x1800278ae  mov     edi, [rbx+0C8h]
0x1800278b4  call    ?IsEnabled@CtfTraceLoggingTelemetry@@SA_NE_K@Z; CtfTraceLoggingTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800278b9  test    al, al
0x1800278bb  jz      short loc_180027849
0x1800278bd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_713764b823f33d19dde9f3ebd9e274e0_@@CA@XZ; _lambda_713764b823f33d19dde9f3ebd9e274e0_::_lambda_invoker_cdecl_(void)
0x1800278c4  call    ?get@?$static_lazy@VCtfTraceLoggingTelemetry@@@details@wil@@QEAAPEAVCtfTraceLoggingTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CtfTraceLoggingTelemetry>::get(void (*)(void))
0x1800278c9  mov     al, [rbx+0CCh]
0x1800278cf  lea     rcx, [rbx+0A8h]; this
0x1800278d6  mov     r8d, [rbx+12Ch]; unsigned int
0x1800278dd  lea     r9, [rbx+98h]; struct _GUID *
0x1800278e4  mov     [rsp+98h+var_38], al; bool
0x1800278e8  lea     rdx, [rbx+0D4h]; unsigned __int16 *
0x1800278ef  mov     al, [rbx+0CDh]
0x1800278f5  mov     [rsp+98h+var_40], edi; unsigned int
0x1800278f9  mov     [rsp+98h+var_48], al; bool
0x1800278fd  mov     eax, [rbx+0C4h]
0x180027903  mov     [rsp+98h+var_50], eax; unsigned int
0x180027907  mov     eax, [rbx+0C0h]
0x18002790d  mov     [rsp+98h+var_58], eax; unsigned int
0x180027911  mov     eax, [rbx+0BCh]
0x180027917  mov     [rsp+98h+var_60], eax; unsigned int
0x18002791b  mov     al, [rbx+0BAh]
0x180027921  mov     [rsp+98h+var_68], al; bool
0x180027925  movzx   eax, word ptr [rbx+0B8h]
0x18002792c  mov     word ptr [rsp+98h+bIgnoreCase], ax; unsigned __int16
0x180027931  mov     qword ptr [rsp+98h+cchValue], rcx; struct _GUID *
0x180027936  call    ?InputSessionStarted_@CtfTraceLoggingTelemetry@@QEAAXPEBGKAEBU_GUID@@1G_NKKK2K2@Z; CtfTraceLoggingTelemetry::InputSessionStarted_(ushort const *,ulong,_GUID const &,_GUID const &,ushort,bool,ulong,ulong,ulong,bool,ulong,bool)
0x18002793b  jmp     loc_180027849
0x180027940  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027944  inc     r8; cchSource
0x180027947  cmp     [rdi+r8*2], bp
0x18002794c  jnz     short loc_180027944
0x18002794e  lea     rsi, [rdi+r8*2]
0x180027952  test    r8, r8
0x180027955  jnz     short loc_1800279A8
0x180027957  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x18002795f  lea     r9, SubBlock; "\\"
0x180027966  mov     rdx, rdi; lpStringSource
0x180027969  mov     [rsp+98h+cchValue], 1; cchValue
0x180027971  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x180027976  call    cs:__imp_FindStringOrdinal
0x18002797c  cmp     eax, 0FFFFFFFFh
0x18002797f  jz      short loc_18002798B
0x180027981  movsxd  rsi, eax
0x180027984  inc     rsi
0x180027987  lea     rsi, [rdi+rsi*2]
0x18002798b  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18002798f  lea     rcx, [rbx+0D4h]; Destination
0x180027996  mov     r8, rsi; Source
0x180027999  lea     edx, [r9+2Ah]; SizeInWords
0x18002799d  call    cs:__imp_wcsncpy_s
0x1800279a3  jmp     loc_180027899
0x1800279a8  cmp     word ptr [rsi-2], 5Ch ; '\'
0x1800279ad  jnz     short loc_180027957
0x1800279af  dec     r8
0x1800279b2  jmp     short loc_180027957
0x1800279b4  mov     rcx, rdi; void *
0x1800279b7  call    ?Internal_CoTaskMemFree@@YAXPEAX@Z; Internal_CoTaskMemFree(void *)
0x1800279bc  jmp     loc_1800278AE
```
