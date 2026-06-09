# CInternetGatewayDevice::GetServiceObject(ushort *,ushort *,IDispatch * *)

- ea: `0x18008ba90`
- end: `0x18008bb7f`
- name: `?GetServiceObject@CInternetGatewayDevice@@UEAAJPEAG0PEAPEAUIDispatch@@@Z`
- size: `239`
- prototype: `int(CInternetGatewayDevice *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IDispatch **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18008ba90`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18008bad1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18008baeb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18008bb0a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18008bb28`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18008bb46`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18008bad1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18008baeb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18008bb0a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18008bb28`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18008bb46`

## string_xrefs

- `0x18008bae1`: `urn:upnp-org:serviceId:WANCommonIFC1`
- `0x18008bac0`: `urn:microsoft-com:serviceId:OSInfo1`
- `0x18008bb1e`: `urn:upnp-org:serviceId:WANPPPConn1`
- `0x18008bafb`: `urn:upnp-org:serviceId:WANPOTSLinkC1`
- `0x18008bb3c`: `urn:upnp-org:serviceId:WANIPConn1`

## pseudocode

```c
__int64 __fastcall CInternetGatewayDevice::GetServiceObject(
        CInternetGatewayDevice *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IDispatch **a4)
{
  __int64 (__fastcall ***v8)(_QWORD, GUID *, struct IDispatch **); // rcx
  unsigned int v9; // ebp

  if ( !a3 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !lstrcmpW(a3, L"urn:microsoft-com:serviceId:OSInfo1") )
  {
    v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IDispatch **))*((_QWORD *)this + 8);
    return (unsigned int)(**v8)(v8, &IID_IDispatch, a4);
  }
  if ( !lstrcmpW(a3, L"urn:upnp-org:serviceId:WANCommonIFC1") )
  {
    v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IDispatch **))*((_QWORD *)this + 9);
    return (unsigned int)(**v8)(v8, &IID_IDispatch, a4);
  }
  v9 = -2147467262;
  if ( lstrcmpW(a3, L"urn:upnp-org:serviceId:WANPOTSLinkC1") )
  {
    if ( lstrcmpW(a3, L"urn:upnp-org:serviceId:WANPPPConn1") )
    {
      if ( lstrcmpW(a3, L"urn:upnp-org:serviceId:WANIPConn1") )
        return v9;
      v8 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IDispatch **))(*((_QWORD *)this + 9) + 80LL);
    }
    else
    {
      v8 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IDispatch **))(*((_QWORD *)this + 9) + 88LL);
    }
  }
  else
  {
    v8 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IDispatch **))(*((_QWORD *)this + 9) + 96LL);
  }
  if ( v8 )
    return (unsigned int)(**v8)(v8, &IID_IDispatch, a4);
  return v9;
}

```

## disassembly

```asm
0x18008ba90  push    rbx
0x18008ba92  push    rbp
0x18008ba93  push    rsi
0x18008ba94  push    rdi
0x18008ba95  sub     rsp, 28h
0x18008ba99  mov     rdi, r9
0x18008ba9c  mov     rbx, r8
0x18008ba9f  mov     rsi, rcx
0x18008baa2  test    r8, r8
0x18008baa5  jnz     short loc_18008BAB1
0x18008baa7  mov     eax, 80070057h
0x18008baac  jmp     loc_18008BB76
0x18008bab1  test    rdi, rdi
0x18008bab4  jnz     short loc_18008BAC0
0x18008bab6  mov     eax, 80004003h
0x18008babb  jmp     loc_18008BB76
0x18008bac0  lea     rdx, aUrnMicrosoftCo; "urn:microsoft-com:serviceId:OSInfo1"
0x18008bac7  mov     qword ptr [r9], 0
0x18008bace  mov     rcx, rbx; lpString1
0x18008bad1  call    cs:__imp_lstrcmpW
0x18008bad7  test    eax, eax
0x18008bad9  jnz     short loc_18008BAE1
0x18008badb  mov     rcx, [rsi+40h]
0x18008badf  jmp     short loc_18008BB5D
0x18008bae1  lea     rdx, aUrnUpnpOrgServ_0; "urn:upnp-org:serviceId:WANCommonIFC1"
0x18008bae8  mov     rcx, rbx; lpString1
0x18008baeb  call    cs:__imp_lstrcmpW
0x18008baf1  test    eax, eax
0x18008baf3  jnz     short loc_18008BAFB
0x18008baf5  mov     rcx, [rsi+48h]
0x18008baf9  jmp     short loc_18008BB5D
0x18008bafb  lea     rdx, aUrnUpnpOrgServ_2; "urn:upnp-org:serviceId:WANPOTSLinkC1"
0x18008bb02  mov     rcx, rbx; lpString1
0x18008bb05  mov     ebp, 80004002h
0x18008bb0a  call    cs:__imp_lstrcmpW
0x18008bb10  test    eax, eax
0x18008bb12  jnz     short loc_18008BB1E
0x18008bb14  mov     rax, [rsi+48h]
0x18008bb18  mov     rcx, [rax+60h]
0x18008bb1c  jmp     short loc_18008BB58
0x18008bb1e  lea     rdx, aUrnUpnpOrgServ_1; "urn:upnp-org:serviceId:WANPPPConn1"
0x18008bb25  mov     rcx, rbx; lpString1
0x18008bb28  call    cs:__imp_lstrcmpW
0x18008bb2e  test    eax, eax
0x18008bb30  jnz     short loc_18008BB3C
0x18008bb32  mov     rax, [rsi+48h]
0x18008bb36  mov     rcx, [rax+58h]
0x18008bb3a  jmp     short loc_18008BB58
0x18008bb3c  lea     rdx, aUrnUpnpOrgServ; "urn:upnp-org:serviceId:WANIPConn1"
0x18008bb43  mov     rcx, rbx; lpString1
0x18008bb46  call    cs:__imp_lstrcmpW
0x18008bb4c  test    eax, eax
0x18008bb4e  jnz     short loc_18008BB74
0x18008bb50  mov     rax, [rsi+48h]
0x18008bb54  mov     rcx, [rax+50h]
0x18008bb58  test    rcx, rcx
0x18008bb5b  jz      short loc_18008BB74
0x18008bb5d  mov     rax, [rcx]
0x18008bb60  lea     rdx, IID_IDispatch
0x18008bb67  mov     r8, rdi
0x18008bb6a  mov     rax, [rax]
0x18008bb6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bb72  mov     ebp, eax
0x18008bb74  mov     eax, ebp
0x18008bb76  add     rsp, 28h
0x18008bb7a  pop     rdi
0x18008bb7b  pop     rsi
0x18008bb7c  pop     rbp
0x18008bb7d  pop     rbx
0x18008bb7e  retn
```
