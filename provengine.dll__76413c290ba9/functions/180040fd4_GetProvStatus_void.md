# GetProvStatus(void)

- ea: `0x180040fd4`
- end: `0x180041068`
- name: `?GetProvStatus@@YA?AW4ProvStatus@@XZ`
- size: `148`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180041070`

## callees

- `0x1800092dc`
- `0x18002f9bc`
- `0x180040fd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041032`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041032`

## string_xrefs

- `0x180041006`: `OSData\SOFTWARE\Microsoft\Provisioning\Agent`
- `0x180040fef`: `SOFTWARE\Microsoft\Provisioning\Agent`

## pseudocode

```c
__int64 GetProvStatus()
{
  bool IsStateSeparationEnabled; // al
  const WCHAR *v1; // rdx
  unsigned int ValueW; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF

  pvData = 0;
  pcbData = 4;
  IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
  v1 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Agent";
  if ( !IsStateSeparationEnabled )
    v1 = L"SOFTWARE\\Microsoft\\Provisioning\\Agent";
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v1, L"Status", 0x10u, 0, &pvData, &pcbData);
  if ( ValueW == 2 )
    return 0;
  if ( ValueW )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x13,
      (int)"onecoreuap\\admin\\prov\\lib\\provstatus.cpp",
      (const char *)ValueW,
      pdwType);
  return pvData;
}

```

## disassembly

```asm
0x180040fd4  sub     rsp, 48h
0x180040fd8  mov     [rsp+48h+arg_0], 0
0x180040fe0  mov     [rsp+48h+arg_8], 4
0x180040fe8  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x180040fed  test    al, al
0x180040fef  lea     rcx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Provisioning\\Agen"...
0x180040ff6  lea     rax, [rsp+48h+arg_8]
0x180040ffb  mov     r9d, 10h; dwFlags
0x180041001  mov     [rsp+48h+pcbData], rax; pcbData
0x180041006  lea     rdx, aOsdataSoftware_4; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x18004100d  lea     rax, [rsp+48h+arg_0]
0x180041012  cmovz   rdx, rcx; lpSubKey
0x180041016  mov     [rsp+48h+pvData], rax; pvData
0x18004101b  lea     r8, aStatus; "Status"
0x180041022  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180041029  mov     [rsp+48h+pdwType], 0; unsigned int
0x180041032  call    cs:__imp_RegGetValueW
0x180041038  cmp     eax, 2
0x18004103b  jnz     short loc_180041041
0x18004103d  xor     eax, eax
0x18004103f  jmp     short loc_180041049
0x180041041  test    eax, eax
0x180041043  jnz     short loc_18004104E
0x180041045  mov     eax, [rsp+48h+arg_0]
0x180041049  add     rsp, 48h
0x18004104d  retn
0x18004104e  mov     rcx, [rsp+48h]; this
0x180041053  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\lib\\provstatu"...
0x18004105a  mov     r9d, eax; char *
0x18004105d  mov     edx, 13h; void *
0x180041062  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
