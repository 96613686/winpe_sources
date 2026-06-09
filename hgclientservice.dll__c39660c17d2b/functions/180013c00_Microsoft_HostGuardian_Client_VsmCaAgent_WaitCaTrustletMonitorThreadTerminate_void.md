# Microsoft::HostGuardian::Client::VsmCaAgent::WaitCaTrustletMonitorThreadTerminate(void)

- ea: `0x180013c00`
- end: `0x180013d02`
- name: `?WaitCaTrustletMonitorThreadTerminate@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXXZ`
- size: `258`
- prototype: `void __fastcall(HANDLE *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c574`

## callees

- `0x180001770`
- `0x1800077a0`
- `0x180013c00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013c9c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013c9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013ca6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013ca6`

## string_xrefs

- `0x180013c27`: `Terminating CaTrustletMonitorThread...`
- `0x180013c67`: `Wait for CaTrustletMonitorThread go away ...`
- `0x180013cbd`: `CaTrustletMonitorThread is terminated.`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::VsmCaAgent::WaitCaTrustletMonitorThreadTerminate(
        HANDLE *this,
        __int64 a2,
        __int64 a3)
{
  _BYTE v4[16]; // [rsp+30h] [rbp-30h] BYREF
  const wchar_t *v5; // [rsp+40h] [rbp-20h]
  __int64 v6; // [rsp+48h] [rbp-18h]

  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    v6 = 78;
    v5 = L"Terminating CaTrustletMonitorThread...";
    McGenEventWrite_EventWriteTransfer(this, ServiceDebugInformational, a3, 2, v4);
  }
  if ( this[5] )
  {
    if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
    {
      v6 = 90;
      v5 = L"Wait for CaTrustletMonitorThread go away ...";
      McGenEventWrite_EventWriteTransfer(this, ServiceDebugInformational, a3, 2, v4);
    }
    WaitForSingleObject(this[5], 0xFFFFFFFF);
    CloseHandle(this[5]);
    this[5] = 0;
  }
  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    v6 = 78;
    v5 = L"CaTrustletMonitorThread is terminated.";
    McGenEventWrite_EventWriteTransfer(this, ServiceDebugInformational, a3, 2, v4);
  }
}

```

## disassembly

```asm
0x180013c00  mov     [rsp-8+arg_8], rbx
0x180013c05  push    rbp
0x180013c06  mov     rbp, rsp
0x180013c09  sub     rsp, 60h
0x180013c0d  mov     rax, cs:__security_cookie
0x180013c14  xor     rax, rsp
0x180013c17  mov     [rbp+var_10], rax
0x180013c1b  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 2
0x180013c22  mov     rbx, rcx
0x180013c25  jz      short loc_180013C55
0x180013c27  lea     rax, aTerminatingCat; "Terminating CaTrustletMonitorThread..."
0x180013c2e  mov     [rbp+var_18], 4Eh ; 'N'
0x180013c36  mov     [rbp+var_20], rax
0x180013c3a  lea     rdx, ServiceDebugInformational
0x180013c41  lea     rax, [rbp+var_30]
0x180013c45  mov     r9d, 2
0x180013c4b  mov     [rsp+60h+var_40], rax
0x180013c50  call    McGenEventWrite_EventWriteTransfer
0x180013c55  mov     rax, [rbx+28h]
0x180013c59  test    rax, rax
0x180013c5c  jz      short loc_180013CB4
0x180013c5e  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 2
0x180013c65  jz      short loc_180013C95
0x180013c67  lea     rax, aWaitForCatrust_0; "Wait for CaTrustletMonitorThread go awa"...
0x180013c6e  mov     [rbp+var_18], 5Ah ; 'Z'
0x180013c76  mov     [rbp+var_20], rax
0x180013c7a  lea     rdx, ServiceDebugInformational
0x180013c81  lea     rax, [rbp+var_30]
0x180013c85  mov     r9d, 2
0x180013c8b  mov     [rsp+60h+var_40], rax
0x180013c90  call    McGenEventWrite_EventWriteTransfer
0x180013c95  mov     rcx, [rbx+28h]; hHandle
0x180013c99  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180013c9c  call    cs:__imp_WaitForSingleObject
0x180013ca2  mov     rcx, [rbx+28h]; hObject
0x180013ca6  call    cs:__imp_CloseHandle
0x180013cac  mov     qword ptr [rbx+28h], 0
0x180013cb4  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 2
0x180013cbb  jz      short loc_180013CEB
0x180013cbd  lea     rax, aCatrustletmoni; "CaTrustletMonitorThread is terminated."
0x180013cc4  mov     [rbp+var_18], 4Eh ; 'N'
0x180013ccc  mov     [rbp+var_20], rax
0x180013cd0  lea     rdx, ServiceDebugInformational
0x180013cd7  lea     rax, [rbp+var_30]
0x180013cdb  mov     r9d, 2
0x180013ce1  mov     [rsp+60h+var_40], rax
0x180013ce6  call    McGenEventWrite_EventWriteTransfer
0x180013ceb  mov     rcx, [rbp+var_10]
0x180013cef  xor     rcx, rsp; StackCookie
0x180013cf2  call    __security_check_cookie
0x180013cf7  mov     rbx, [rsp+60h+arg_8]
0x180013cfc  add     rsp, 60h
0x180013d00  pop     rbp
0x180013d01  retn
```
