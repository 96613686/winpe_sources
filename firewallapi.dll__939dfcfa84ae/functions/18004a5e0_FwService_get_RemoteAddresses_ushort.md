# FwService::get_RemoteAddresses(ushort * *)

- ea: `0x18004a5e0`
- end: `0x18004a6c7`
- name: `?get_RemoteAddresses@FwService@@UEAAJPEAPEAG@Z`
- size: `231`
- prototype: `__int64 __fastcall(FwService *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x1800294b0`
- `0x18002a1f4`
- `0x180049e84`
- `0x18004a0e8`
- `0x18004a5e0`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x18004a670`
- `fwbase!FwReportReturnError` at `0x18004a696`
- `fwbase!FwReportReturnError` at `0x18004a670`
- `fwbase!FwReportReturnError` at `0x18004a696`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x18004a659`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x18004a659`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18004a681`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18004a681`

## string_xrefs

- `0x18004a614`: `FwService::get_RemoteAddresses`

## pseudocode

```c
__int64 __fastcall FwService::get_RemoteAddresses(FwService *this, unsigned __int16 **a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  int RemoteAddrs; // eax
  _BYTE v8[80]; // [rsp+20h] [rbp-78h] BYREF

  memset_0(v8, 0, 0x48u);
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 2147500035LL;
LABEL_7:
    FwReportReturnError("FwService::get_RemoteAddresses", v5);
    goto LABEL_8;
  }
  *a2 = 0;
  RemoteAddrs = FwService::PerformLazyInitialization(this);
  v4 = RemoteAddrs;
  if ( RemoteAddrs < 0
    || (RemoteAddrs = FwService::GetRemoteAddrs(this, (struct _tag_FW_ADDRESSES *)v8), v4 = RemoteAddrs, RemoteAddrs < 0)
    || (RemoteAddrs = GetOpenPortorAuthAppAsBSTR(v8, a2), v4 = RemoteAddrs, RemoteAddrs < 0) )
  {
    v5 = (unsigned int)RemoteAddrs;
    goto LABEL_7;
  }
LABEL_8:
  FwPolioEmptyWFAddresses(v8);
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwService::get_RemoteAddresses", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004a5e0  mov     [rsp+arg_10], rbx
0x18004a5e5  push    rbp
0x18004a5e6  push    rsi
0x18004a5e7  push    rdi
0x18004a5e8  sub     rsp, 80h
0x18004a5ef  mov     rax, cs:__security_cookie
0x18004a5f6  xor     rax, rsp
0x18004a5f9  mov     [rsp+98h+var_28], rax
0x18004a5fe  mov     rdi, rdx
0x18004a601  mov     rsi, rcx
0x18004a604  xor     edx, edx; Val
0x18004a606  lea     rcx, [rsp+98h+var_78]; void *
0x18004a60b  lea     r8d, [rdx+48h]; Size
0x18004a60f  call    memset_0
0x18004a614  lea     rbp, aFwserviceGetRe; "FwService::get_RemoteAddresses"
0x18004a61b  test    rdi, rdi
0x18004a61e  jnz     short loc_18004A629
0x18004a620  mov     ebx, 80004003h
0x18004a625  mov     edx, ebx
0x18004a627  jmp     short loc_18004A66D
0x18004a629  mov     rcx, rsi; this
0x18004a62c  mov     qword ptr [rdi], 0
0x18004a633  call    ?PerformLazyInitialization@FwService@@AEAAJXZ; FwService::PerformLazyInitialization(void)
0x18004a638  mov     ebx, eax
0x18004a63a  test    eax, eax
0x18004a63c  js      short loc_18004A66B
0x18004a63e  lea     rdx, [rsp+98h+var_78]; struct _tag_FW_ADDRESSES *
0x18004a643  mov     rcx, rsi; this
0x18004a646  call    ?GetRemoteAddrs@FwService@@AEAAJPEAU_tag_FW_ADDRESSES@@@Z; FwService::GetRemoteAddrs(_tag_FW_ADDRESSES *)
0x18004a64b  mov     ebx, eax
0x18004a64d  test    eax, eax
0x18004a64f  js      short loc_18004A66B
0x18004a651  mov     rdx, rdi
0x18004a654  lea     rcx, [rsp+98h+var_78]
0x18004a659  call    cs:__imp_GetOpenPortorAuthAppAsBSTR
0x18004a660  nop     dword ptr [rax+rax+00h]
0x18004a665  mov     ebx, eax
0x18004a667  test    eax, eax
0x18004a669  jns     short loc_18004A67C
0x18004a66b  mov     edx, eax
0x18004a66d  mov     rcx, rbp
0x18004a670  call    cs:__imp_FwReportReturnError
0x18004a677  nop     dword ptr [rax+rax+00h]
0x18004a67c  lea     rcx, [rsp+98h+var_78]
0x18004a681  call    cs:__imp_FwPolioEmptyWFAddresses
0x18004a688  nop     dword ptr [rax+rax+00h]
0x18004a68d  test    ebx, ebx
0x18004a68f  jns     short loc_18004A6A4
0x18004a691  mov     edx, ebx
0x18004a693  mov     rcx, rbp
0x18004a696  call    cs:__imp_FwReportReturnError
0x18004a69d  nop     dword ptr [rax+rax+00h]
0x18004a6a2  mov     ebx, eax
0x18004a6a4  mov     eax, ebx
0x18004a6a6  mov     rcx, [rsp+98h+var_28]
0x18004a6ab  xor     rcx, rsp; StackCookie
0x18004a6ae  call    __security_check_cookie
0x18004a6b3  mov     rbx, [rsp+98h+arg_10]
0x18004a6bb  add     rsp, 80h
0x18004a6c2  pop     rdi
0x18004a6c3  pop     rsi
0x18004a6c4  pop     rbp
0x18004a6c5  retn
```
