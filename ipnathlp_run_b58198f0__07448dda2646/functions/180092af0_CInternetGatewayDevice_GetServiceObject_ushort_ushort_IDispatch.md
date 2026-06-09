# CInternetGatewayDevice::GetServiceObject(ushort *,ushort *,IDispatch * *)

- ea: `0x180092af0`
- end: `0x180092c01`
- name: `?GetServiceObject@CInternetGatewayDevice@@UEAAJPEAG0PEAPEAUIDispatch@@@Z`
- size: `273`
- prototype: `int(CInternetGatewayDevice *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IDispatch **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180092af0`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180092b31`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180092b54`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180092b79`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180092b9d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180092bc1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180092b31`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180092b54`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180092b79`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180092b9d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180092bc1`

## string_xrefs

- `0x180092b4a`: `urn:upnp-org:serviceId:WANCommonIFC1`
- `0x180092b20`: `urn:microsoft-com:serviceId:OSInfo1`
- `0x180092b93`: `urn:upnp-org:serviceId:WANPPPConn1`
- `0x180092b6a`: `urn:upnp-org:serviceId:WANPOTSLinkC1`
- `0x180092bb7`: `urn:upnp-org:serviceId:WANIPConn1`

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
0x180092af0  push    rbx
0x180092af2  push    rbp
0x180092af3  push    rsi
0x180092af4  push    rdi
0x180092af5  sub     rsp, 28h
0x180092af9  mov     rdi, r9
0x180092afc  mov     rbx, r8
0x180092aff  mov     rsi, rcx
0x180092b02  test    r8, r8
0x180092b05  jnz     short loc_180092B11
0x180092b07  mov     eax, 80070057h
0x180092b0c  jmp     loc_180092BF7
0x180092b11  test    rdi, rdi
0x180092b14  jnz     short loc_180092B20
0x180092b16  mov     eax, 80004003h
0x180092b1b  jmp     loc_180092BF7
0x180092b20  lea     rdx, aUrnMicrosoftCo; "urn:microsoft-com:serviceId:OSInfo1"
0x180092b27  mov     qword ptr [r9], 0
0x180092b2e  mov     rcx, rbx; lpString1
0x180092b31  call    cs:__imp_lstrcmpW
0x180092b38  nop     dword ptr [rax+rax+00h]
0x180092b3d  test    eax, eax
0x180092b3f  jnz     short loc_180092B4A
0x180092b41  mov     rcx, [rsi+40h]
0x180092b45  jmp     loc_180092BDE
0x180092b4a  lea     rdx, aUrnUpnpOrgServ_0; "urn:upnp-org:serviceId:WANCommonIFC1"
0x180092b51  mov     rcx, rbx; lpString1
0x180092b54  call    cs:__imp_lstrcmpW
0x180092b5b  nop     dword ptr [rax+rax+00h]
0x180092b60  test    eax, eax
0x180092b62  jnz     short loc_180092B6A
0x180092b64  mov     rcx, [rsi+48h]
0x180092b68  jmp     short loc_180092BDE
0x180092b6a  lea     rdx, aUrnUpnpOrgServ_2; "urn:upnp-org:serviceId:WANPOTSLinkC1"
0x180092b71  mov     rcx, rbx; lpString1
0x180092b74  mov     ebp, 80004002h
0x180092b79  call    cs:__imp_lstrcmpW
0x180092b80  nop     dword ptr [rax+rax+00h]
0x180092b85  test    eax, eax
0x180092b87  jnz     short loc_180092B93
0x180092b89  mov     rax, [rsi+48h]
0x180092b8d  mov     rcx, [rax+60h]
0x180092b91  jmp     short loc_180092BD9
0x180092b93  lea     rdx, aUrnUpnpOrgServ_1; "urn:upnp-org:serviceId:WANPPPConn1"
0x180092b9a  mov     rcx, rbx; lpString1
0x180092b9d  call    cs:__imp_lstrcmpW
0x180092ba4  nop     dword ptr [rax+rax+00h]
0x180092ba9  test    eax, eax
0x180092bab  jnz     short loc_180092BB7
0x180092bad  mov     rax, [rsi+48h]
0x180092bb1  mov     rcx, [rax+58h]
0x180092bb5  jmp     short loc_180092BD9
0x180092bb7  lea     rdx, aUrnUpnpOrgServ; "urn:upnp-org:serviceId:WANIPConn1"
0x180092bbe  mov     rcx, rbx; lpString1
0x180092bc1  call    cs:__imp_lstrcmpW
0x180092bc8  nop     dword ptr [rax+rax+00h]
0x180092bcd  test    eax, eax
0x180092bcf  jnz     short loc_180092BF5
0x180092bd1  mov     rax, [rsi+48h]
0x180092bd5  mov     rcx, [rax+50h]
0x180092bd9  test    rcx, rcx
0x180092bdc  jz      short loc_180092BF5
0x180092bde  mov     rax, [rcx]
0x180092be1  lea     rdx, IID_IDispatch
0x180092be8  mov     r8, rdi
0x180092beb  mov     rax, [rax]
0x180092bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092bf3  mov     ebp, eax
0x180092bf5  mov     eax, ebp
0x180092bf7  add     rsp, 28h
0x180092bfb  pop     rdi
0x180092bfc  pop     rsi
0x180092bfd  pop     rbp
0x180092bfe  pop     rbx
0x180092bff  retn
```
