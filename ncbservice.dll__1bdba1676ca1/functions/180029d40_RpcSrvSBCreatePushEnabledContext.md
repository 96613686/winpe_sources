# RpcSrvSBCreatePushEnabledContext

- ea: `0x180029d40`
- end: `0x180029f0d`
- name: `RpcSrvSBCreatePushEnabledContext`
- size: `461`
- prototype: `__int64 __fastcall(__int64, struct _GUID *, int, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001128`
- `0x180001ebc`
- `0x180003ed0`
- `0x180004a30`
- `0x18000a0a0`
- `0x18001493c`
- `0x18001d8e0`
- `0x180026490`
- `0x1800298f8`
- `0x180029d40`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180029e18`
- `RPCRT4!RpcRevertToSelf` at `0x180029ebf`
- `RPCRT4!RpcRevertToSelf` at `0x180029e18`
- `RPCRT4!RpcRevertToSelf` at `0x180029ebf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029ed0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029ed0`

## string_xrefs

- `0x180029d90`: `RpcSrvSBCreatePushEnabledContext: invalid EventID`
- `0x180029dfd`: `RpcSrvSBCreatePushEnabledContext: RpcHelperRetriveSbContext failed`
- `0x180029e40`: `RpcSrvSBCreatePushEnabledContext: CreatePushEnabledContext failed`

## pseudocode

```c
__int64 __fastcall RpcSrvSBCreatePushEnabledContext(__int64 a1, struct _GUID *a2, int a3, int a4)
{
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // ebx
  bool v10; // di
  unsigned int PushEnabledContext; // eax
  bool v12; // [rsp+30h] [rbp-49h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-41h] BYREF
  SocketBrokerContext *v14; // [rsp+40h] [rbp-39h] BYREF
  struct _GUID *v15; // [rsp+48h] [rbp-31h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-29h] BYREF
  char v17[32]; // [rsp+60h] [rbp-19h] BYREF
  struct _GUID *v18; // [rsp+80h] [rbp+7h]
  __int64 v19; // [rsp+88h] [rbp+Fh]
  struct _GUID **v20; // [rsp+90h] [rbp+17h]
  __int64 v21; // [rsp+98h] [rbp+1Fh]

  v14 = 0;
  lpMem = 0;
  v12 = 0;
  hObject = 0;
  if ( a2 )
  {
    if ( (unsigned int)dword_18004D068 > 5 )
    {
      v15 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
        a1,
        (unsigned int)word_18004570A,
        a3,
        a4,
        (__int64)&v15);
    }
    v6 = RpcHelperRetriveSbContext(0, a2, &v12, (unsigned __int16 **)&lpMem, &v14, &hObject);
    v9 = v6;
    if ( v6 )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          v8,
          v7,
          L"RpcSrvSBCreatePushEnabledContext: RpcHelperRetriveSbContext failed",
          v6);
      v10 = v12;
    }
    else
    {
      v10 = v12;
      if ( v12 )
      {
        RpcRevertToSelf();
        v10 = 0;
      }
      PushEnabledContext = SocketBrokerContext::CreatePushEnabledContext(v14, hObject);
      v9 = PushEnabledContext;
      if ( PushEnabledContext && (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          v8,
          v7,
          L"RpcSrvSBCreatePushEnabledContext: CreatePushEnabledContext failed",
          PushEnabledContext);
    }
    if ( (unsigned int)dword_18004D068 > 5 )
    {
      LODWORD(v15) = v9;
      v21 = 4;
      v20 = &v15;
      v18 = a2;
      v19 = 16;
      tlgWriteTransfer_EventWriteTransfer(&dword_18004D068, &dword_180045564, 0, 0, 4, v17);
    }
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0jd_EventWriteTransfer(v8, v7, a2, (unsigned int)v9);
    VpnFree(lpMem);
    if ( v10 )
      RpcRevertToSelf();
    if ( hObject )
      CloseHandle(hObject);
    if ( v14 )
      SocketBrokerContext::ReleaseRef(v14);
    if ( v9 > 0 )
      return (unsigned __int16)v9 | 0x80070000;
    return (unsigned int)v9;
  }
  else
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(a1, 0, L"RpcSrvSBCreatePushEnabledContext: invalid EventID", 87);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180029d40  push    rbp
0x180029d42  push    rbx
0x180029d43  push    rsi
0x180029d44  push    rdi
0x180029d45  lea     rbp, [rsp-3Fh]
0x180029d4a  sub     rsp, 0B8h
0x180029d51  mov     rax, cs:__security_cookie
0x180029d58  xor     rax, rsp
0x180029d5b  mov     [rbp+57h+var_30], rax
0x180029d5f  mov     [rbp+57h+var_90], 0
0x180029d67  mov     rsi, rdx
0x180029d6a  mov     [rbp+57h+lpMem], 0
0x180029d72  mov     [rbp+57h+var_A0], 0
0x180029d76  mov     [rbp+57h+hObject], 0
0x180029d7e  test    rdx, rdx
0x180029d81  jnz     short loc_180029DA6
0x180029d83  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180029d8a  jz      short loc_180029D9C
0x180029d8c  lea     r9d, [rdx+57h]
0x180029d90  lea     r8, aRpcsrvsbcreate_0; "RpcSrvSBCreatePushEnabledContext: inval"...
0x180029d97  call    McTemplateU0zq_EventWriteTransfer
0x180029d9c  mov     eax, 80070057h
0x180029da1  jmp     loc_180029EF5
0x180029da6  mov     eax, cs:dword_18004D068
0x180029dac  cmp     eax, 5
0x180029daf  jbe     short loc_180029DCA
0x180029db1  lea     rax, [rbp+57h+var_88]
0x180029db5  mov     [rbp+57h+var_88], rsi
0x180029db9  lea     rdx, word_18004570A
0x180029dc0  mov     [rsp+0D0h+var_B0], rax
0x180029dc5  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x180029dca  lea     rax, [rbp+57h+hObject]
0x180029dce  xor     ecx, ecx; unsigned __int16 *
0x180029dd0  mov     [rsp+0D0h+var_A8], rax; void **
0x180029dd5  lea     r9, [rbp+57h+lpMem]; unsigned __int16 **
0x180029dd9  lea     rax, [rbp+57h+var_90]
0x180029ddd  lea     r8, [rbp+57h+var_A0]; bool *
0x180029de1  mov     [rsp+0D0h+var_B0], rax; struct SocketBrokerContext **
0x180029de6  call    ?RpcHelperRetriveSbContext@@YAKPEBGPEAU_GUID@@PEA_NPEAPEAGPEAPEAVSocketBrokerContext@@PEAPEAX@Z; RpcHelperRetriveSbContext(ushort const *,_GUID *,bool *,ushort * *,SocketBrokerContext * *,void * *)
0x180029deb  mov     ebx, eax
0x180029ded  test    eax, eax
0x180029def  jz      short loc_180029E0F
0x180029df1  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180029df8  jz      short loc_180029E09
0x180029dfa  mov     r9d, eax
0x180029dfd  lea     r8, aRpcsrvsbcreate; "RpcSrvSBCreatePushEnabledContext: RpcHe"...
0x180029e04  call    McTemplateU0zq_EventWriteTransfer
0x180029e09  mov     dil, [rbp+57h+var_A0]
0x180029e0d  jmp     short loc_180029E4C
0x180029e0f  mov     dil, [rbp+57h+var_A0]
0x180029e13  test    dil, dil
0x180029e16  jz      short loc_180029E21
0x180029e18  call    cs:__imp_RpcRevertToSelf
0x180029e1e  xor     dil, dil
0x180029e21  mov     rdx, [rbp+57h+hObject]; Process
0x180029e25  mov     rcx, [rbp+57h+var_90]; this
0x180029e29  call    ?CreatePushEnabledContext@SocketBrokerContext@@QEAAKPEAX@Z; SocketBrokerContext::CreatePushEnabledContext(void *)
0x180029e2e  mov     ebx, eax
0x180029e30  test    eax, eax
0x180029e32  jz      short loc_180029E4C
0x180029e34  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180029e3b  jz      short loc_180029E4C
0x180029e3d  mov     r9d, eax
0x180029e40  lea     r8, aRpcsrvsbcreate_1; "RpcSrvSBCreatePushEnabledContext: Creat"...
0x180029e47  call    McTemplateU0zq_EventWriteTransfer
0x180029e4c  mov     eax, cs:dword_18004D068
0x180029e52  cmp     eax, 5
0x180029e55  jbe     short loc_180029E9D
0x180029e57  mov     ecx, 4
0x180029e5c  mov     dword ptr [rbp+57h+var_88], ebx
0x180029e5f  lea     rax, [rbp+57h+var_88]
0x180029e63  mov     [rbp+57h+var_38], rcx
0x180029e67  mov     [rbp+57h+var_40], rax
0x180029e6b  lea     rdx, dword_180045564
0x180029e72  lea     rax, [rbp+57h+var_70]
0x180029e76  mov     [rbp+57h+var_50], rsi
0x180029e7a  mov     [rsp+0D0h+var_A8], rax
0x180029e7f  xor     r9d, r9d
0x180029e82  mov     dword ptr [rsp+0D0h+var_B0], ecx
0x180029e86  xor     r8d, r8d
0x180029e89  lea     rcx, dword_18004D068
0x180029e90  mov     [rbp+57h+var_48], 10h
0x180029e98  call    _tlgWriteTransfer_EventWriteTransfer
0x180029e9d  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180029ea4  jz      short loc_180029EB1
0x180029ea6  mov     r9d, ebx
0x180029ea9  mov     r8, rsi
0x180029eac  call    McTemplateU0jd_EventWriteTransfer
0x180029eb1  mov     rcx, [rbp+57h+lpMem]; lpMem
0x180029eb5  call    VpnFree
0x180029eba  test    dil, dil
0x180029ebd  jz      short loc_180029EC5
0x180029ebf  call    cs:__imp_RpcRevertToSelf
0x180029ec5  cmp     [rbp+57h+hObject], 0
0x180029eca  jz      short loc_180029ED6
0x180029ecc  mov     rcx, [rbp+57h+hObject]; hObject
0x180029ed0  call    cs:__imp_CloseHandle
0x180029ed6  cmp     [rbp+57h+var_90], 0
0x180029edb  jz      short loc_180029EE6
0x180029edd  mov     rcx, [rbp+57h+var_90]; this
0x180029ee1  call    ?ReleaseRef@SocketBrokerContext@@QEAAXXZ; SocketBrokerContext::ReleaseRef(void)
0x180029ee6  test    ebx, ebx
0x180029ee8  jle     short loc_180029EF3
0x180029eea  movzx   ebx, bx
0x180029eed  or      ebx, 80070000h
0x180029ef3  mov     eax, ebx
0x180029ef5  mov     rcx, [rbp+57h+var_30]
0x180029ef9  xor     rcx, rsp; StackCookie
0x180029efc  call    __security_check_cookie
0x180029f01  add     rsp, 0B8h
0x180029f08  pop     rdi
0x180029f09  pop     rsi
0x180029f0a  pop     rbx
0x180029f0b  pop     rbp
0x180029f0c  retn
```
