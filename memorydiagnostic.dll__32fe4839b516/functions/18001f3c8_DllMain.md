# DllMain

- ea: `0x18001f3c8`
- end: `0x18001f55a`
- name: `DllMain`
- size: `402`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180002528`

## callees

- `0x180001008`
- `0x180003374`
- `0x18000f144`
- `0x180015bec`
- `0x18001e7fc`
- `0x18001f10c`
- `0x18001f3c8`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x18001f402`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18001f4fd`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18001f402`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18001f4fd`

## string_xrefs

- `0x18001f471`: `DllMain_Attach`
- `0x18001f4c0`: `DllMain_Detach`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct _tlgProvider_t *v5; // rax
  int v6; // r8d
  int v7; // r9d
  const struct _tlgProvider_t *v8; // rax
  int v9; // r8d
  int v10; // r9d
  const struct wil::FailureInfo *v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  _BYTE v14[168]; // [rsp+30h] [rbp-A8h] BYREF
  const wchar_t *v15; // [rsp+F8h] [rbp+20h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::__private_IsEnabled(
                          &`wil::Feature<__WilFeatureTraits_Feature_57054134>::GetImpl'::`2'::impl,
                          fdwReason,
                          lpvReserved) )
  {
    if ( fdwReason )
    {
      if ( fdwReason == 1 )
      {
        DisableThreadLibraryCalls(hinstDLL);
        if ( wil::details::g_pfnTelemetryCallback
          && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != TlgHelper::WilFallbackTelemetryCallback )
        {
          memset_0(v14, 0, 0x98u);
          wil::details::WilFailFast((wil::details *)v14, v12);
        }
        wil::details::g_pfnTelemetryCallback = (__int64)TlgHelper::WilFallbackTelemetryCallback;
        if ( wil::g_pfnResultFromCaughtException
          && (void (__fastcall __noreturn *)(Utils *__hidden))wil::g_pfnResultFromCaughtException != Utils::ResultFromCaughtExceptionBase )
        {
          memset_0(v14, 0, 0x98u);
          wil::details::WilFailFast((wil::details *)v14, v13);
        }
        wil::g_pfnResultFromCaughtException = (__int64)Utils::ResultFromCaughtExceptionBase;
        v5 = TlgHelper::Provider();
        if ( *(_DWORD *)v5 > 4u && (*((_BYTE *)v5 + 16) & 1) != 0 && (*((_QWORD *)v5 + 3) & 1LL) == *((_QWORD *)v5 + 3) )
        {
          v15 = L"DllMain_Attach";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (_DWORD)v5,
            (unsigned int)&unk_18002AF12,
            v6,
            v7,
            (__int64)&v15);
        }
        WaitForDebugger();
      }
    }
    else
    {
      v8 = TlgHelper::Provider();
      if ( *(_DWORD *)v8 > 4u && (*((_BYTE *)v8 + 16) & 1) != 0 && (*((_QWORD *)v8 + 3) & 1LL) == *((_QWORD *)v8 + 3) )
      {
        v15 = L"DllMain_Detach";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v8,
          (unsigned int)&unk_18002AF12,
          v9,
          v10,
          (__int64)&v15);
      }
      wil::details::g_pfnTelemetryCallback = 0;
    }
  }
  else if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x18001f3c8  mov     [rsp+arg_0], rbx
0x18001f3cd  push    rdi
0x18001f3ce  sub     rsp, 0D0h
0x18001f3d5  mov     ebx, edx
0x18001f3d7  mov     rdi, rcx
0x18001f3da  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57054134@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134> `wil::Feature<__WilFeatureTraits_Feature_57054134>::GetImpl(void)'::`2'::impl
0x18001f3e1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::__private_IsEnabled(void)
0x18001f3e6  test    al, al
0x18001f3e8  jz      loc_18001F4F5
0x18001f3ee  test    ebx, ebx
0x18001f3f0  jz      loc_18001F4A3
0x18001f3f6  cmp     ebx, 1
0x18001f3f9  jnz     loc_18001F509
0x18001f3ff  mov     rcx, rdi; hLibModule
0x18001f402  call    cs:__imp_DisableThreadLibraryCalls
0x18001f409  nop     dword ptr [rax+rax+00h]
0x18001f40e  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18001f415  lea     rcx, ?WilFallbackTelemetryCallback@TlgHelper@@SAX_NAEBUFailureInfo@wil@@@Z; TlgHelper::WilFallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18001f41c  test    rax, rax
0x18001f41f  jz      short loc_18001F42A
0x18001f421  cmp     rax, rcx
0x18001f424  jnz     loc_18001F520
0x18001f42a  mov     rax, cs:?g_pfnResultFromCaughtException@wil@@3P6AJX_EEA
0x18001f431  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x18001f438  lea     rcx, ?ResultFromCaughtExceptionBase@Utils@@YAJXZ; Utils::ResultFromCaughtExceptionBase(void)
0x18001f43f  test    rax, rax
0x18001f442  jz      short loc_18001F44D
0x18001f444  cmp     rax, rcx
0x18001f447  jnz     loc_18001F53D
0x18001f44d  mov     cs:?g_pfnResultFromCaughtException@wil@@3P6AJX_EEA, rcx
0x18001f454  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18001f459  cmp     dword ptr [rax], 4
0x18001f45c  jbe     short loc_18001F49C
0x18001f45e  test    byte ptr [rax+10h], 1
0x18001f462  jz      short loc_18001F49C
0x18001f464  mov     rcx, [rax+18h]
0x18001f468  and     ecx, 1
0x18001f46b  cmp     rcx, [rax+18h]
0x18001f46f  jnz     short loc_18001F49C
0x18001f471  lea     rcx, aDllmainAttach; "DllMain_Attach"
0x18001f478  mov     [rsp+0D8h+arg_18], rcx
0x18001f480  lea     rdx, byte_18002AF12
0x18001f487  lea     rcx, [rsp+0D8h+arg_18]
0x18001f48f  mov     [rsp+0D8h+var_B8], rcx
0x18001f494  mov     rcx, rax
0x18001f497  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18001f49c  call    ?WaitForDebugger@@YAXXZ; WaitForDebugger(void)
0x18001f4a1  jmp     short loc_18001F509
0x18001f4a3  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18001f4a8  cmp     dword ptr [rax], 4
0x18001f4ab  jbe     short loc_18001F4EB
0x18001f4ad  test    byte ptr [rax+10h], 1
0x18001f4b1  jz      short loc_18001F4EB
0x18001f4b3  mov     rcx, [rax+18h]
0x18001f4b7  and     ecx, 1
0x18001f4ba  cmp     rcx, [rax+18h]
0x18001f4be  jnz     short loc_18001F4EB
0x18001f4c0  lea     rcx, aDllmainDetach; "DllMain_Detach"
0x18001f4c7  mov     [rsp+0D8h+arg_18], rcx
0x18001f4cf  lea     rdx, byte_18002AF12
0x18001f4d6  lea     rcx, [rsp+0D8h+arg_18]
0x18001f4de  mov     [rsp+0D8h+var_B8], rcx
0x18001f4e3  mov     rcx, rax
0x18001f4e6  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18001f4eb  and     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, 0
0x18001f4f3  jmp     short loc_18001F509
0x18001f4f5  cmp     ebx, 1
0x18001f4f8  jnz     short loc_18001F509
0x18001f4fa  mov     rcx, rdi; hLibModule
0x18001f4fd  call    cs:__imp_DisableThreadLibraryCalls
0x18001f504  nop     dword ptr [rax+rax+00h]
0x18001f509  mov     rbx, [rsp+0D8h+arg_0]
0x18001f511  mov     eax, 1
0x18001f516  add     rsp, 0D0h
0x18001f51d  pop     rdi
0x18001f51e  retn
0x18001f520  xor     edx, edx; Val
0x18001f522  lea     rcx, [rsp+0D8h+var_A8]; void *
0x18001f527  mov     r8d, 98h; Size
0x18001f52d  call    memset_0
0x18001f532  lea     rcx, [rsp+0D8h+var_A8]; this
0x18001f537  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001f53d  xor     edx, edx; Val
0x18001f53f  lea     rcx, [rsp+0D8h+var_A8]; void *
0x18001f544  mov     r8d, 98h; Size
0x18001f54a  call    memset_0
0x18001f54f  lea     rcx, [rsp+0D8h+var_A8]; this
0x18001f554  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
