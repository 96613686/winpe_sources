# SharedSocket::DnsServiceDeregistration(_DNS_SERVICE_INSTANCE *,uchar)

- ea: `0x180027d70`
- end: `0x180027e62`
- name: `?DnsServiceDeregistration@SharedSocket@@AEAAKPEAU_DNS_SERVICE_INSTANCE@@E@Z`
- size: `242`
- prototype: `unsigned int __fastcall(SharedSocket *__hidden this, struct _DNS_SERVICE_INSTANCE *, unsigned __int8)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002548`

## callees

- `0x18000a0a0`
- `0x180027d70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027db7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027db7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027e48`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027e48`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027da9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027da9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027e51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027e51`
- `DNSAPI!DnsServiceRegister` at `0x180027e19`
- `DNSAPI!DnsServiceRegister` at `0x180027e19`

## string_xrefs

- `0x180027dcf`: `DnsServiceDeregistration: CreateEvent failed`
- `0x180027e34`: `DnsServiceRegister: returned`

## pseudocode

```c
__int64 __fastcall SharedSocket::DnsServiceDeregistration(
        SharedSocket *this,
        struct _DNS_SERVICE_INSTANCE *a2,
        char a3)
{
  HANDLE EventW; // rdi
  DWORD LastError; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  DWORD v9; // ebx
  DWORD v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int128 v14; // [rsp+20h] [rbp-38h] BYREF
  __int128 v15; // [rsp+30h] [rbp-28h]
  __int128 v16; // [rsp+40h] [rbp-18h]
  __int64 v17; // [rsp+80h] [rbp+28h] BYREF

  v17 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW )
  {
    *(_QWORD *)&v14 = 1;
    *(_QWORD *)&v16 = 0;
    *((_QWORD *)&v14 + 1) = a2;
    *((_QWORD *)&v16 + 1) = a3 != 0;
    *((_QWORD *)&v15 + 1) = EventW;
    *(_QWORD *)&v15 = SharedSocket::RegistrationCompletion;
    v10 = DnsServiceRegister(&v14, &v17);
    v9 = v10;
    if ( v10 == 9506 )
    {
      WaitForSingleObject(EventW, 0xFFFFFFFF);
    }
    else if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      McTemplateU0zq_EventWriteTransfer(v12, v11, L"DnsServiceRegister: returned", v10);
    }
    CloseHandle(EventW);
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v8,
        v7,
        L"DnsServiceDeregistration: CreateEvent failed",
        LastError,
        v14,
        v15,
        v16);
  }
  return v9;
}

```

## disassembly

```asm
0x180027d70  mov     [rsp-20h+arg_0], rcx
0x180027d75  push    rbp
0x180027d76  push    rbx
0x180027d77  push    rsi
0x180027d78  push    rdi
0x180027d79  mov     rbp, rsp
0x180027d7c  sub     rsp, 58h
0x180027d80  xorps   xmm0, xmm0
0x180027d83  mov     [rbp+arg_0], 0
0x180027d8b  xor     r9d, r9d; lpName
0x180027d8e  mov     bl, r8b
0x180027d91  mov     rsi, rdx
0x180027d94  xor     r8d, r8d; bInitialState
0x180027d97  xor     ecx, ecx; lpEventAttributes
0x180027d99  movups  [rbp+var_38], xmm0
0x180027d9d  lea     edx, [r9+1]; bManualReset
0x180027da1  movups  [rbp+var_28], xmm0
0x180027da5  movups  [rbp+var_18], xmm0
0x180027da9  call    cs:__imp_CreateEventW
0x180027daf  mov     rdi, rax
0x180027db2  test    rax, rax
0x180027db5  jnz     short loc_180027DDD
0x180027db7  call    cs:__imp_GetLastError
0x180027dbd  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180027dc4  mov     ebx, eax
0x180027dc6  jz      loc_180027E57
0x180027dcc  mov     r9d, eax
0x180027dcf  lea     r8, aDnsservicedere_0; "DnsServiceDeregistration: CreateEvent f"...
0x180027dd6  call    McTemplateU0zq_EventWriteTransfer
0x180027ddb  jmp     short loc_180027E57
0x180027ddd  xor     eax, eax
0x180027ddf  mov     qword ptr [rbp+var_38], 1
0x180027de7  test    bl, bl
0x180027de9  mov     qword ptr [rbp+var_18], 0
0x180027df1  lea     rdx, [rbp+arg_0]
0x180027df5  mov     dword ptr [rbp+var_18+0Ch], 0
0x180027dfc  setnz   al
0x180027dff  mov     qword ptr [rbp+var_38+8], rsi
0x180027e03  mov     dword ptr [rbp+var_18+8], eax
0x180027e06  lea     rcx, [rbp+var_38]
0x180027e0a  lea     rax, ?RegistrationCompletion@SharedSocket@@CAXKPEAXPEAU_DNS_SERVICE_INSTANCE@@@Z; SharedSocket::RegistrationCompletion(ulong,void *,_DNS_SERVICE_INSTANCE *)
0x180027e11  mov     qword ptr [rbp+var_28+8], rdi
0x180027e15  mov     qword ptr [rbp+var_28], rax
0x180027e19  call    cs:__imp_DnsServiceRegister
0x180027e1f  mov     ebx, eax
0x180027e21  cmp     eax, 2522h
0x180027e26  jz      short loc_180027E42
0x180027e28  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180027e2f  jz      short loc_180027E4E
0x180027e31  mov     r9d, eax
0x180027e34  lea     r8, aDnsserviceregi_0; "DnsServiceRegister: returned"
0x180027e3b  call    McTemplateU0zq_EventWriteTransfer
0x180027e40  jmp     short loc_180027E4E
0x180027e42  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180027e45  mov     rcx, rdi; hHandle
0x180027e48  call    cs:__imp_WaitForSingleObject
0x180027e4e  mov     rcx, rdi; hObject
0x180027e51  call    cs:__imp_CloseHandle
0x180027e57  mov     eax, ebx
0x180027e59  add     rsp, 58h
0x180027e5d  pop     rdi
0x180027e5e  pop     rsi
0x180027e5f  pop     rbx
0x180027e60  pop     rbp
0x180027e61  retn
```
