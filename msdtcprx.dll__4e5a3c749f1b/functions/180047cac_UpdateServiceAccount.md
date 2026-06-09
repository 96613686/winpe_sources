# UpdateServiceAccount

- ea: `0x180047cac`
- end: `0x180047dc0`
- name: `UpdateServiceAccount`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180010110`

## callees

- `0x180011ac0`
- `0x180047cac`
- `0x180073390`
- `0x180073a3c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047dad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047dad`
- `msvcrt!_wcsicmp` at `0x180047cfa`
- `msvcrt!_wcsicmp` at `0x180047cfa`

## string_xrefs

- `0x180047d0e`: `com\complus\dtc\dtc\msdtcprx\src\proxyplugin.cpp`
- `0x180047d95`: `com\complus\dtc\dtc\msdtcprx\src\proxyplugin.cpp`
- `0x180047ce2`: `UpdateServiceAccount: GetServiceAccount failed`
- `0x180047d15`: `UpdateServiceAccount: Changing service account from LocalSystem to NT Authority\Network Service`
- `0x180047d21`: `NT Authority\NetworkService`
- `0x180047d4f`: `NT Authority\NetworkService`
- `0x180047d3c`: `UpdateServiceAccount: SetAccountInfoInRegistryW failed`
- `0x180047d71`: `UpdateServiceAccount: pService->SetAccount failed`
- `0x180047d8e`: `UpdateServiceAccount: SetSddlOnMsdtcService failed`

## pseudocode

```c
__int64 __fastcall UpdateServiceAccount(struct ITmInstance *a1)
{
  __int64 v1; // rax
  int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // r9d
  char *v6; // rdx
  unsigned __int16 *v7; // rdx
  wchar_t *String1; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(_QWORD *)a1;
  String1 = 0;
  v3 = (*(__int64 (__fastcall **)(struct ITmInstance *, wchar_t **))(v1 + 312))(a1, &String1);
  v4 = v3;
  if ( v3 >= 0 )
  {
    if ( _wcsicmp(String1, L"LocalSystem") )
      goto LABEL_11;
    TraceFile(
      0,
      "UpdateServiceAccount: Changing service account from LocalSystem to NT Authority\\Network Service",
      "com\\complus\\dtc\\dtc\\msdtcprx\\src\\proxyplugin.cpp",
      0x73u);
    v3 = SetAccountInfoInRegistryW(a1, L"NT Authority\\NetworkService");
    v4 = v3;
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(struct ITmInstance *, const unsigned __int16 *, const WCHAR *))(*(_QWORD *)a1 + 304LL))(
             a1,
             L"NT Authority\\NetworkService",
             &cchOriginalDestLength);
      v4 = v3;
      if ( v3 >= 0 )
      {
        v3 = SetSddlOnMsdtcService(a1, v7);
        v4 = v3;
        if ( v3 >= 0 )
          goto LABEL_11;
        v5 = 136;
        v6 = "UpdateServiceAccount: SetSddlOnMsdtcService failed";
      }
      else
      {
        v5 = 129;
        v6 = "UpdateServiceAccount: pService->SetAccount failed";
      }
    }
    else
    {
      v5 = 121;
      v6 = "UpdateServiceAccount: SetAccountInfoInRegistryW failed";
    }
  }
  else
  {
    v5 = 106;
    v6 = "UpdateServiceAccount: GetServiceAccount failed";
  }
  TraceFile(v3, v6, "com\\complus\\dtc\\dtc\\msdtcprx\\src\\proxyplugin.cpp", v5);
LABEL_11:
  if ( String1 )
    CoTaskMemFree(String1);
  return v4;
}

```

## disassembly

```asm
0x180047cac  mov     [rsp+arg_8], rbx
0x180047cb1  push    rsi
0x180047cb2  sub     rsp, 20h
0x180047cb6  mov     rax, [rcx]
0x180047cb9  lea     rdx, [rsp+28h+String1]
0x180047cbe  mov     rsi, rcx
0x180047cc1  mov     [rsp+28h+String1], 0
0x180047cca  mov     rax, [rax+138h]
0x180047cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047cd6  mov     ebx, eax
0x180047cd8  test    eax, eax
0x180047cda  jns     short loc_180047CEE
0x180047cdc  mov     r9d, 6Ah ; 'j'
0x180047ce2  lea     rdx, aUpdateservicea; "UpdateServiceAccount: GetServiceAccount"...
0x180047ce9  jmp     loc_180047D95
0x180047cee  mov     rcx, [rsp+28h+String1]; String1
0x180047cf3  lea     rdx, aLocalsystem; "LocalSystem"
0x180047cfa  call    cs:__imp__wcsicmp
0x180047d00  test    eax, eax
0x180047d02  jnz     loc_180047DA3
0x180047d08  lea     r9d, [rax+73h]; unsigned int
0x180047d0c  xor     ecx, ecx; int
0x180047d0e  lea     r8, aComComplusDtcD_27; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180047d15  lea     rdx, aUpdateservicea_2; "UpdateServiceAccount: Changing service "...
0x180047d1c  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180047d21  lea     rdx, aNtAuthorityNet_0; "NT Authority\\NetworkService"
0x180047d28  mov     rcx, rsi; struct ITmInstance *
0x180047d2b  call    ?SetAccountInfoInRegistryW@@YAJPEAUITmInstance@@PEAG@Z; SetAccountInfoInRegistryW(ITmInstance *,ushort *)
0x180047d30  mov     ebx, eax
0x180047d32  test    eax, eax
0x180047d34  jns     short loc_180047D45
0x180047d36  mov     r9d, 79h ; 'y'
0x180047d3c  lea     rdx, aUpdateservicea_1; "UpdateServiceAccount: SetAccountInfoInR"...
0x180047d43  jmp     short loc_180047D95
0x180047d45  mov     rax, [rsi]
0x180047d48  lea     r8, cchOriginalDestLength
0x180047d4f  lea     rdx, aNtAuthorityNet_0; "NT Authority\\NetworkService"
0x180047d56  mov     rcx, rsi
0x180047d59  mov     rax, [rax+130h]
0x180047d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d65  mov     ebx, eax
0x180047d67  test    eax, eax
0x180047d69  jns     short loc_180047D7A
0x180047d6b  mov     r9d, 81h
0x180047d71  lea     rdx, aUpdateservicea_3; "UpdateServiceAccount: pService->SetAcco"...
0x180047d78  jmp     short loc_180047D95
0x180047d7a  mov     rcx, rsi; struct ITmInstance *
0x180047d7d  call    ?SetSddlOnMsdtcService@@YAJPEAUITmInstance@@PEAG@Z; SetSddlOnMsdtcService(ITmInstance *,ushort *)
0x180047d82  mov     ebx, eax
0x180047d84  test    eax, eax
0x180047d86  jns     short loc_180047DA3
0x180047d88  mov     r9d, 88h; unsigned int
0x180047d8e  lea     rdx, aUpdateservicea_0; "UpdateServiceAccount: SetSddlOnMsdtcSer"...
0x180047d95  lea     r8, aComComplusDtcD_27; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180047d9c  mov     ecx, eax; int
0x180047d9e  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180047da3  mov     rcx, [rsp+28h+String1]; pv
0x180047da8  test    rcx, rcx
0x180047dab  jz      short loc_180047DB3
0x180047dad  call    cs:__imp_CoTaskMemFree
0x180047db3  mov     eax, ebx
0x180047db5  mov     rbx, [rsp+28h+arg_8]
0x180047dba  add     rsp, 20h
0x180047dbe  pop     rsi
0x180047dbf  retn
```
