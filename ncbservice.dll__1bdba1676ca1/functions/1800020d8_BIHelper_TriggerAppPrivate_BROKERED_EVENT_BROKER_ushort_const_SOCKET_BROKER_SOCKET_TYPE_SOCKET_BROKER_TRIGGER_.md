# BIHelper::TriggerAppPrivate(_BROKERED_EVENT *,_BROKER *,ushort const *,_SOCKET_BROKER_SOCKET_TYPE,_SOCKET_BROKER_TRIGGER_REASON,ulong)

- ea: `0x1800020d8`
- end: `0x1800022db`
- name: `?TriggerAppPrivate@BIHelper@@CAKPEAU_BROKERED_EVENT@@PEAU_BROKER@@PEBGW4_SOCKET_BROKER_SOCKET_TYPE@@W4_SOCKET_BROKER_TRIGGER_REASON@@K@Z`
- size: `515`
- prototype: `__int64 __fastcall(int *, __int64, const unsigned __int16 *, int, int, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002050`
- `0x180018960`
- `0x1800267d8`

## callees

- `0x1800020d8`
- `0x18000a0a0`
- `0x180012be0`
- `0x1800152d0`
- `0x1800153a0`
- `0x18001d8e0`
- `0x18001e368`

## import_xrefs

- `BrokerLib!BrSignalBrokerEvent2` at `0x180002200`
- `BrokerLib!BrSignalBrokerEvent2` at `0x180002200`

## string_xrefs

- `0x180002233`: `BIHelper::TriggerApp: invalid Event or broker context`
- `0x1800021d5`: `BIHelper::TriggerApp: StringCchCopy of socket id failed`
- `0x180002218`: `BIHelper::TriggerApp: BrSignalBrokerEvent2 failed with`

## pseudocode

```c
__int64 __fastcall BIHelper::TriggerAppPrivate(int *a1, __int64 a2, const unsigned __int16 *a3, int a4, int a5, int a6)
{
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // r8d
  const wchar_t *v13; // r9
  __int64 v14; // xmm0_8
  __int64 v15; // r9
  unsigned int v16; // ebx
  const wchar_t *v17; // r8
  unsigned int v18; // eax
  unsigned int v20; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+54h] [rbp-ACh] BYREF
  int v22; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+5Ch] [rbp-A4h] BYREF
  const unsigned __int16 *v24; // [rsp+60h] [rbp-A0h] BYREF
  int *v25; // [rsp+68h] [rbp-98h] BYREF
  int v26; // [rsp+70h] [rbp-90h] BYREF
  __int64 v27; // [rsp+74h] [rbp-8Ch] BYREF
  int v28; // [rsp+7Ch] [rbp-84h]
  unsigned __int16 v29[258]; // [rsp+80h] [rbp-80h] BYREF
  int v30; // [rsp+284h] [rbp+184h]
  int v31; // [rsp+288h] [rbp+188h]
  int v32; // [rsp+28Ch] [rbp+18Ch]

  v26 = 0;
  memset_0(&v27, 0, 0x21Cu);
  if ( !a1 || !a2 )
  {
    v15 = 87;
    v16 = 87;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_17;
    v17 = L"BIHelper::TriggerApp: invalid Event or broker context";
    goto LABEL_16;
  }
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    LODWORD(v13) = (_DWORD)a3;
    if ( !a3 )
      v13 = L"NULL";
    McTemplateU0jzddd_EventWriteTransfer(v11, v10, (_DWORD)a1, (_DWORD)v13, a4, a5, a6);
  }
  v14 = *(_QWORD *)(a1 + 1);
  v26 = *a1;
  v28 = a1[3];
  v31 = a5;
  v32 = a6;
  v27 = v14;
  v30 = a4;
  if ( a3 && (int)StringCchCopyW(v29, 0x101u, a3) < 0 )
  {
    v15 = 87;
    v16 = 87;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_17;
    v17 = L"BIHelper::TriggerApp: StringCchCopy of socket id failed";
    goto LABEL_16;
  }
  v18 = BrSignalBrokerEvent2(a2, a1, 0, SOCKET_BROKER_EVENT_PARSER_CLSID, 544, &v26);
  v16 = v18;
  if ( v18 && (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    v15 = v18;
    v17 = L"BIHelper::TriggerApp: BrSignalBrokerEvent2 failed with";
LABEL_16:
    McTemplateU0zq_EventWriteTransfer(v11, v10, v17, v15);
  }
LABEL_17:
  if ( (unsigned int)dword_18004D068 > 5 )
  {
    v20 = v16;
    v21 = a6;
    v22 = a5;
    if ( !a3 )
      a3 = L"NULL";
    v23 = a4;
    v24 = a3;
    v25 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v11,
      (unsigned int)byte_1800453A3,
      v12,
      v15,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v21,
      (__int64)&v20);
  }
  return v16;
}

```

## disassembly

```asm
0x1800020d8  push    rbp
0x1800020da  push    rbx
0x1800020db  push    rsi
0x1800020dc  push    rdi
0x1800020dd  push    r12
0x1800020df  push    r13
0x1800020e1  push    r14
0x1800020e3  push    r15
0x1800020e5  lea     rbp, [rsp-1A8h]
0x1800020ed  sub     rsp, 2A8h
0x1800020f4  mov     rax, cs:__security_cookie
0x1800020fb  xor     rax, rsp
0x1800020fe  mov     [rbp+1E0h+var_50], rax
0x180002105  mov     rdi, r8
0x180002108  mov     [rsp+2E0h+var_270], 0
0x180002110  mov     rbx, rdx
0x180002113  mov     rsi, rcx
0x180002116  xor     edx, edx; Val
0x180002118  lea     rcx, [rsp+2E0h+var_26C]; void *
0x18000211d  mov     r8d, 21Ch; Size
0x180002123  mov     r14d, r9d
0x180002126  call    memset_0
0x18000212b  mov     r15d, [rbp+1E0h+arg_28]
0x180002132  lea     r13, aNull_1; "NULL"
0x180002139  mov     r12d, [rbp+1E0h+arg_20]
0x180002140  test    rsi, rsi
0x180002143  jz      loc_180002221
0x180002149  test    rbx, rbx
0x18000214c  jz      loc_180002221
0x180002152  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180002159  jz      short loc_18000217C
0x18000215b  test    rdi, rdi
0x18000215e  mov     dword ptr [rsp+2E0h+var_2B0], r15d
0x180002163  mov     r9, rdi
0x180002166  mov     dword ptr [rsp+2E0h+var_2B8], r12d
0x18000216b  cmovz   r9, r13
0x18000216f  mov     dword ptr [rsp+2E0h+var_2C0], r14d
0x180002174  mov     r8, rsi
0x180002177  call    McTemplateU0jzddd_EventWriteTransfer
0x18000217c  mov     eax, [rsi]
0x18000217e  movsd   xmm0, qword ptr [rsi+4]
0x180002183  mov     [rsp+2E0h+var_270], eax
0x180002187  mov     eax, [rsi+0Ch]
0x18000218a  mov     [rsp+2E0h+var_264], eax
0x18000218e  mov     [rbp+1E0h+var_58], r12d
0x180002195  mov     [rbp+1E0h+var_54], r15d
0x18000219c  movsd   [rsp+2E0h+var_26C], xmm0
0x1800021a2  mov     [rbp+1E0h+var_5C], r14d
0x1800021a9  test    rdi, rdi
0x1800021ac  jz      short loc_1800021DE
0x1800021ae  mov     r8, rdi; unsigned __int16 *
0x1800021b1  lea     rcx, [rbp+1E0h+var_260]; unsigned __int16 *
0x1800021b5  mov     edx, 101h; unsigned __int64
0x1800021ba  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800021bf  test    eax, eax
0x1800021c1  jns     short loc_1800021DE
0x1800021c3  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800021ca  mov     r9d, 57h ; 'W'
0x1800021d0  mov     ebx, r9d
0x1800021d3  jz      short loc_18000223F
0x1800021d5  lea     r8, aBihelperTrigge_1; "BIHelper::TriggerApp: StringCchCopy of "...
0x1800021dc  jmp     short loc_18000223A
0x1800021de  lea     rax, [rsp+2E0h+var_270]
0x1800021e3  xor     r8d, r8d
0x1800021e6  mov     [rsp+2E0h+var_2B8], rax
0x1800021eb  lea     r9, SOCKET_BROKER_EVENT_PARSER_CLSID
0x1800021f2  mov     rdx, rsi
0x1800021f5  mov     dword ptr [rsp+2E0h+var_2C0], 220h
0x1800021fd  mov     rcx, rbx
0x180002200  call    cs:__imp_BrSignalBrokerEvent2
0x180002206  mov     ebx, eax
0x180002208  test    eax, eax
0x18000220a  jz      short loc_18000223F
0x18000220c  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180002213  jz      short loc_18000223F
0x180002215  mov     r9d, eax
0x180002218  lea     r8, aBihelperTrigge_0; "BIHelper::TriggerApp: BrSignalBrokerEve"...
0x18000221f  jmp     short loc_18000223A
0x180002221  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180002228  mov     r9d, 57h ; 'W'
0x18000222e  mov     ebx, r9d
0x180002231  jz      short loc_18000223F
0x180002233  lea     r8, aBihelperTrigge; "BIHelper::TriggerApp: invalid Event or "...
0x18000223a  call    McTemplateU0zq_EventWriteTransfer
0x18000223f  mov     eax, cs:dword_18004D068
0x180002245  cmp     eax, 5
0x180002248  jbe     short loc_1800022B6
0x18000224a  lea     rax, [rsp+2E0h+var_290]
0x18000224f  mov     [rsp+2E0h+var_290], ebx
0x180002253  mov     [rsp+2E0h+var_298], rax
0x180002258  lea     rdx, byte_1800453A3
0x18000225f  lea     rax, [rsp+2E0h+var_28C]
0x180002264  mov     [rsp+2E0h+var_28C], r15d
0x180002269  mov     [rsp+2E0h+var_2A0], rax
0x18000226e  test    rdi, rdi
0x180002271  lea     rax, [rsp+2E0h+var_288]
0x180002276  mov     [rsp+2E0h+var_288], r12d
0x18000227b  mov     [rsp+2E0h+var_2A8], rax
0x180002280  cmovz   rdi, r13
0x180002284  lea     rax, [rsp+2E0h+var_284]
0x180002289  mov     [rsp+2E0h+var_284], r14d
0x18000228e  mov     [rsp+2E0h+var_2B0], rax
0x180002293  lea     rax, [rsp+2E0h+var_280]
0x180002298  mov     [rsp+2E0h+var_2B8], rax
0x18000229d  lea     rax, [rsp+2E0h+var_278]
0x1800022a2  mov     [rsp+2E0h+var_2C0], rax
0x1800022a7  mov     [rsp+2E0h+var_280], rdi
0x1800022ac  mov     [rsp+2E0h+var_278], rsi
0x1800022b1  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800022b6  mov     eax, ebx
0x1800022b8  mov     rcx, [rbp+1E0h+var_50]
0x1800022bf  xor     rcx, rsp; StackCookie
0x1800022c2  call    __security_check_cookie
0x1800022c7  add     rsp, 2A8h
0x1800022ce  pop     r15
0x1800022d0  pop     r14
0x1800022d2  pop     r13
0x1800022d4  pop     r12
0x1800022d6  pop     rdi
0x1800022d7  pop     rsi
0x1800022d8  pop     rbx
0x1800022d9  pop     rbp
0x1800022da  retn
```
