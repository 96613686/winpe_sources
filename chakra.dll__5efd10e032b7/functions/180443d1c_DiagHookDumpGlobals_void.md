# DiagHookDumpGlobals(void)

- ea: `0x180443d1c`
- end: `0x180443e0f`
- name: `?DiagHookDumpGlobals@@YAXXZ`
- size: `243`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180423f70`

## callees

- `0x180443d1c`

## import_xrefs

- `msvcrt!wprintf` at `0x180443d53`
- `msvcrt!wprintf` at `0x180443d88`
- `msvcrt!wprintf` at `0x180443da5`
- `msvcrt!wprintf` at `0x180443dc2`
- `msvcrt!wprintf` at `0x180443ddf`
- `msvcrt!wprintf` at `0x180443dfc`
- `msvcrt!wprintf` at `0x180443d53`
- `msvcrt!wprintf` at `0x180443d88`
- `msvcrt!wprintf` at `0x180443da5`
- `msvcrt!wprintf` at `0x180443dc2`
- `msvcrt!wprintf` at `0x180443ddf`
- `msvcrt!wprintf` at `0x180443dfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180443d64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180443d64`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180443d37`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180443d37`

## string_xrefs

- `0x180443d81`: `Configuration	%Ix\n`
- `0x180443d9e`: `ThreadContextList	%Ix\n`
- `0x180443dbb`: `DllBaseAddress	%Ix\n`
- `0x180443dd8`: `DllHighAddress	%Ix\n`

## pseudocode

```c
void DiagHookDumpGlobals(void)
{
  HMODULE v0; // rbx
  LPOLESTR lpsz; // [rsp+20h] [rbp-18h] BYREF

  lpsz = 0;
  if ( StringFromIID(&rclsid, &lpsz) >= 0 )
  {
    wprintf(L"Build\t%s\n", lpsz);
    CoTaskMemFree(lpsz);
  }
  v0 = g_hInstance;
  wprintf(L"Configuration\t%Ix\n", &Js::Configuration::Global - (char *)g_hInstance);
  wprintf(L"ThreadContextList\t%Ix\n", (char *)&ThreadContext::globalListFirst - (char *)v0);
  wprintf(L"DllBaseAddress\t%Ix\n", (char *)&qword_18073F450 - (char *)v0);
  wprintf(L"DllHighAddress\t%Ix\n", (char *)&qword_18073F458 - (char *)v0);
  wprintf(L"Amd64FakeEHFrameProcOffset\t%Ix\n", (char *)amd64_ReturnFromCallWithFakeFrame - (char *)v0);
}

```

## disassembly

```asm
0x180443d1c  push    rbx
0x180443d1e  sub     rsp, 30h
0x180443d22  lea     rdx, [rsp+38h+lpsz]; lplpsz
0x180443d27  mov     [rsp+38h+lpsz], 0
0x180443d30  lea     rcx, rclsid; rclsid
0x180443d37  call    cs:__imp_StringFromIID
0x180443d3e  nop     dword ptr [rax+rax+00h]
0x180443d43  test    eax, eax
0x180443d45  js      short loc_180443D70
0x180443d47  mov     rdx, [rsp+38h+lpsz]
0x180443d4c  lea     rcx, aBuildS; "Build\t%s\n"
0x180443d53  call    cs:__imp_wprintf
0x180443d5a  nop     dword ptr [rax+rax+00h]
0x180443d5f  mov     rcx, [rsp+38h+lpsz]; pv
0x180443d64  call    cs:__imp_CoTaskMemFree
0x180443d6b  nop     dword ptr [rax+rax+00h]
0x180443d70  mov     rbx, cs:?g_hInstance@@3PEAXEA; void * g_hInstance
0x180443d77  lea     rdx, ?Global@Configuration@Js@@2V12@A; Js::Configuration Js::Configuration::Global
0x180443d7e  sub     rdx, rbx
0x180443d81  lea     rcx, aConfigurationI; "Configuration\t%Ix\n"
0x180443d88  call    cs:__imp_wprintf
0x180443d8f  nop     dword ptr [rax+rax+00h]
0x180443d94  lea     rdx, ?globalListFirst@ThreadContext@@2PEAV1@EA; ThreadContext * ThreadContext::globalListFirst
0x180443d9b  sub     rdx, rbx
0x180443d9e  lea     rcx, aThreadcontextl; "ThreadContextList\t%Ix\n"
0x180443da5  call    cs:__imp_wprintf
0x180443dac  nop     dword ptr [rax+rax+00h]
0x180443db1  lea     rdx, qword_18073F450
0x180443db8  sub     rdx, rbx
0x180443dbb  lea     rcx, aDllbaseaddress; "DllBaseAddress\t%Ix\n"
0x180443dc2  call    cs:__imp_wprintf
0x180443dc9  nop     dword ptr [rax+rax+00h]
0x180443dce  lea     rdx, qword_18073F458
0x180443dd5  sub     rdx, rbx
0x180443dd8  lea     rcx, aDllhighaddress; "DllHighAddress\t%Ix\n"
0x180443ddf  call    cs:__imp_wprintf
0x180443de6  nop     dword ptr [rax+rax+00h]
0x180443deb  lea     rdx, amd64_ReturnFromCallWithFakeFrame
0x180443df2  sub     rdx, rbx
0x180443df5  lea     rcx, aAmd64fakeehfra; "Amd64FakeEHFrameProcOffset\t%Ix\n"
0x180443dfc  call    cs:__imp_wprintf
0x180443e03  nop     dword ptr [rax+rax+00h]
0x180443e08  add     rsp, 30h
0x180443e0c  pop     rbx
0x180443e0d  retn
```
