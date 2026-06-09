# Microsoft::HostGuardian::Client::VsmCaAgent::TerminateCaTrustlet(void)

- ea: `0x180013a88`
- end: `0x180013bfa`
- name: `?TerminateCaTrustlet@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXXZ`
- size: `370`
- prototype: `void __fastcall(RPC_BINDING_HANDLE *Binding, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c574`
- `0x180013954`

## callees

- `0x180001770`
- `0x1800077a0`
- `0x180013a88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013b8d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013b8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013b97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013b97`
- `RPCRT4!NdrClientCall3` at `0x180013b03`
- `RPCRT4!NdrClientCall3` at `0x180013b03`
- `RPCRT4!RpcBindingFree` at `0x180013ab8`
- `RPCRT4!RpcBindingFree` at `0x180013b2b`
- `RPCRT4!RpcBindingFree` at `0x180013ab8`
- `RPCRT4!RpcBindingFree` at `0x180013b2b`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::VsmCaAgent::TerminateCaTrustlet(
        RPC_BINDING_HANDLE *Binding,
        __int64 a2,
        __int64 a3)
{
  RPC_BINDING_HANDLE *v5; // rcx
  RPC_BINDING_HANDLE *v6; // rcx
  _BYTE v7[16]; // [rsp+48h] [rbp-30h] BYREF
  const wchar_t *v8; // [rsp+58h] [rbp-20h]
  __int64 v9; // [rsp+60h] [rbp-18h]

  v5 = Binding + 1;
  if ( *v5 )
  {
    RpcBindingFree(v5);
    Binding[1] = 0;
  }
  v6 = Binding + 2;
  if ( Binding[2] && *Binding )
  {
    NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, *Binding, Binding + 2);
    Binding[2] = 0;
  }
  if ( *Binding )
  {
    RpcBindingFree(Binding);
    *Binding = 0;
  }
  if ( Binding[4] != (RPC_BINDING_HANDLE)-1LL )
  {
    if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
    {
      v8 = L"Wait for CaTrustlet go away.";
      v9 = 58;
      McGenEventWrite_EventWriteTransfer(v6, ServiceDebugInformational, a3, 2, v7);
    }
    WaitForSingleObject(Binding[4], 0xFFFFFFFF);
    CloseHandle(Binding[4]);
    Binding[4] = (RPC_BINDING_HANDLE)-1LL;
  }
  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    v8 = L"Terminated CATrustlet.";
    v9 = 46;
    McGenEventWrite_EventWriteTransfer(v6, ServiceDebugInformational, a3, 2, v7);
  }
}

```

## disassembly

```asm
0x180013a88  mov     [rsp+arg_8], rbx
0x180013a8d  push    rdi
0x180013a8e  sub     rsp, 70h
0x180013a92  mov     rax, cs:__security_cookie
0x180013a99  xor     rax, rsp
0x180013a9c  mov     [rsp+78h+var_10], rax
0x180013aa1  mov     rdi, rcx
0x180013aa4  mov     rbx, rcx
0x180013aa7  mov     [rsp+78h+var_48], rcx
0x180013aac  add     rcx, 8; Binding
0x180013ab0  mov     rax, [rcx]
0x180013ab3  test    rax, rax
0x180013ab6  jz      short loc_180013AD0
0x180013ab8  call    cs:__imp_RpcBindingFree
0x180013abe  jmp     short loc_180013AC8
0x180013ac0  mov     rbx, [rsp+78h+var_48]
0x180013ac5  mov     rdi, rbx
0x180013ac8  mov     qword ptr [rbx+8], 0
0x180013ad0  lea     rcx, [rbx+10h]
0x180013ad4  mov     rax, [rcx]
0x180013ad7  test    rax, rax
0x180013ada  jz      short loc_180013B20
0x180013adc  mov     rax, [rdi]
0x180013adf  test    rax, rax
0x180013ae2  jz      short loc_180013B20
0x180013ae4  mov     r9, [rdi]
0x180013ae7  mov     [rsp+78h+var_38], 0
0x180013af0  mov     [rsp+78h+var_58], rcx
0x180013af5  xor     r8d, r8d; pReturnValue
0x180013af8  lea     edx, [r8+1]; nProcNum
0x180013afc  lea     rcx, pProxyInfo; pProxyInfo
0x180013b03  call    cs:__imp_NdrClientCall3
0x180013b09  mov     [rsp+78h+var_38], rax
0x180013b0e  jmp     short loc_180013B18
0x180013b10  mov     rbx, [rsp+78h+var_48]
0x180013b15  mov     rdi, rbx
0x180013b18  mov     qword ptr [rbx+10h], 0
0x180013b20  mov     rax, [rdi]
0x180013b23  test    rax, rax
0x180013b26  jz      short loc_180013B42
0x180013b28  mov     rcx, rbx; Binding
0x180013b2b  call    cs:__imp_RpcBindingFree
0x180013b31  jmp     short loc_180013B3B
0x180013b33  mov     rbx, [rsp+78h+var_48]
0x180013b38  mov     rdi, rbx
0x180013b3b  mov     qword ptr [rdi], 0
0x180013b42  mov     rax, [rbx+20h]
0x180013b46  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013b4a  jz      short loc_180013BA5
0x180013b4c  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 2
0x180013b53  jz      short loc_180013B86
0x180013b55  lea     rax, aWaitForCatrust; "Wait for CaTrustlet go away."
0x180013b5c  mov     [rsp+78h+var_20], rax
0x180013b61  mov     [rsp+78h+var_18], 3Ah ; ':'
0x180013b6a  lea     rax, [rsp+78h+var_30]
0x180013b6f  mov     [rsp+78h+var_58], rax
0x180013b74  mov     r9d, 2
0x180013b7a  lea     rdx, ServiceDebugInformational
0x180013b81  call    McGenEventWrite_EventWriteTransfer
0x180013b86  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180013b89  mov     rcx, [rbx+20h]; hHandle
0x180013b8d  call    cs:__imp_WaitForSingleObject
0x180013b93  mov     rcx, [rbx+20h]; hObject
0x180013b97  call    cs:__imp_CloseHandle
0x180013b9d  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x180013ba5  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 2
0x180013bac  jz      short loc_180013BDF
0x180013bae  lea     rax, aTerminatedCatr; "Terminated CATrustlet."
0x180013bb5  mov     [rsp+78h+var_20], rax
0x180013bba  mov     [rsp+78h+var_18], 2Eh ; '.'
0x180013bc3  lea     rax, [rsp+78h+var_30]
0x180013bc8  mov     [rsp+78h+var_58], rax
0x180013bcd  mov     r9d, 2
0x180013bd3  lea     rdx, ServiceDebugInformational
0x180013bda  call    McGenEventWrite_EventWriteTransfer
0x180013bdf  mov     rcx, [rsp+78h+var_10]
0x180013be4  xor     rcx, rsp; StackCookie
0x180013be7  call    __security_check_cookie
0x180013bec  mov     rbx, [rsp+78h+arg_8]
0x180013bf4  add     rsp, 70h
0x180013bf8  pop     rdi
0x180013bf9  retn
```
