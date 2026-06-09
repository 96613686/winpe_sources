# BIHelper::Initialize(void)

- ea: `0x18001c194`
- end: `0x18001c261`
- name: `?Initialize@BIHelper@@QEAAKXZ`
- size: `205`
- prototype: `unsigned int __fastcall(BIHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001c0e4`

## callees

- `0x18000a0a0`
- `0x18001c194`
- `0x180028208`

## import_xrefs

- `BrokerLib!BrCreateBrokerInstance2` at `0x18001c202`
- `BrokerLib!BrCreateBrokerInstance2` at `0x18001c202`
- `BrokerLib!BrInitializeBrokerInstance2` at `0x18001c228`
- `BrokerLib!BrInitializeBrokerInstance2` at `0x18001c228`

## string_xrefs

- `0x18001c217`: `BIHelper::Initialize: BrCreateBrokerInstance2 failed with`
- `0x18001c23d`: `BIHelper::Initialize: BrInitializeBrokerInstance failed with`

## pseudocode

```c
__int64 __fastcall BIHelper::Initialize(BIHelper *this)
{
  BIHelper *v1; // rdi
  int v2; // ecx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int v6; // ebx
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  _QWORD v11[7]; // [rsp+30h] [rbp-38h] BYREF
  BIHelper *v12; // [rsp+70h] [rbp+8h] BYREF

  v12 = this;
  v1 = g_BIHelper;
  v2 = *((_DWORD *)g_SocketBrokerConfig + 2);
  v11[0] = BIHelper::OnCreateEvent;
  v11[1] = &BIHelper::OnDeleteEvent;
  v11[2] = &BIHelper::OnEnableEvent;
  v11[3] = &BIHelper::OnDisableEvent;
  LODWORD(v12) = v2;
  v11[4] = 0;
  v3 = BrCreateBrokerInstance2(v11, SOCKET_BROKER_CLSID, 1, &v12, g_BIHelper);
  v6 = v3;
  if ( v3 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v5, v4, L"BIHelper::Initialize: BrCreateBrokerInstance2 failed with", v3);
LABEL_7:
    BIHelper::Cleanup(v1);
    return v6;
  }
  v7 = BrInitializeBrokerInstance2(*(_QWORD *)v1, 0, 0);
  v6 = v7;
  if ( v7 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v9, v8, L"BIHelper::Initialize: BrInitializeBrokerInstance failed with", v7);
    goto LABEL_7;
  }
  return v6;
}

```

## disassembly

```asm
0x18001c194  mov     r11, rsp
0x18001c197  mov     [r11+10h], rbx
0x18001c19b  mov     [r11+8], rcx
0x18001c19f  push    rdi
0x18001c1a0  sub     rsp, 60h
0x18001c1a4  mov     rax, cs:?g_SocketBrokerConfig@@3PEAVSocketBrokerConfig@@EA; SocketBrokerConfig * g_SocketBrokerConfig
0x18001c1ab  lea     r9, [r11+8]
0x18001c1af  mov     rdi, cs:?g_BIHelper@@3PEAVBIHelper@@EA; BIHelper * g_BIHelper
0x18001c1b6  lea     rdx, SOCKET_BROKER_CLSID
0x18001c1bd  mov     [r11-48h], rdi
0x18001c1c1  mov     ecx, [rax+8]
0x18001c1c4  lea     rax, ?OnCreateEvent@BIHelper@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAU_BR_EVENT_PARAMETERS@@PEBGPEAX55PEAPEAXPEAKPEAU_BR_NEW_EVENT_INFORMATION@@@Z; BIHelper::OnCreateEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,_BR_EVENT_PARAMETERS *,ushort const *,void *,void *,void *,void * *,ulong *,_BR_NEW_EVENT_INFORMATION *)
0x18001c1cb  mov     [r11-38h], rax
0x18001c1cf  lea     rax, ?OnDeleteEvent@BIHelper@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; BIHelper::OnDeleteEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18001c1d6  mov     [r11-30h], rax
0x18001c1da  lea     rax, ?OnEnableEvent@BIHelper@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; BIHelper::OnEnableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18001c1e1  mov     [r11-28h], rax
0x18001c1e5  lea     rax, ?OnDisableEvent@BIHelper@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; BIHelper::OnDisableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18001c1ec  mov     [r11-20h], rax
0x18001c1f0  xor     eax, eax
0x18001c1f2  mov     dword ptr [rsp+68h+arg_0], ecx
0x18001c1f6  lea     rcx, [r11-38h]
0x18001c1fa  mov     [r11-18h], rax
0x18001c1fe  lea     r8d, [rax+1]
0x18001c202  call    cs:__imp_BrCreateBrokerInstance2
0x18001c208  mov     ebx, eax
0x18001c20a  test    eax, eax
0x18001c20c  jz      short loc_18001C220
0x18001c20e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18001c215  jz      short loc_18001C24C
0x18001c217  lea     r8, aBihelperInitia; "BIHelper::Initialize: BrCreateBrokerIns"...
0x18001c21e  jmp     short loc_18001C244
0x18001c220  mov     rcx, [rdi]
0x18001c223  xor     r8d, r8d
0x18001c226  xor     edx, edx
0x18001c228  call    cs:__imp_BrInitializeBrokerInstance2
0x18001c22e  mov     ebx, eax
0x18001c230  test    eax, eax
0x18001c232  jz      short loc_18001C254
0x18001c234  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18001c23b  jz      short loc_18001C24C
0x18001c23d  lea     r8, aBihelperInitia_1; "BIHelper::Initialize: BrInitializeBroke"...
0x18001c244  mov     r9d, eax
0x18001c247  call    McTemplateU0zq_EventWriteTransfer
0x18001c24c  mov     rcx, rdi; this
0x18001c24f  call    ?Cleanup@BIHelper@@AEAAXXZ; BIHelper::Cleanup(void)
0x18001c254  mov     eax, ebx
0x18001c256  mov     rbx, [rsp+68h+arg_8]
0x18001c25b  add     rsp, 60h
0x18001c25f  pop     rdi
0x18001c260  retn
```
