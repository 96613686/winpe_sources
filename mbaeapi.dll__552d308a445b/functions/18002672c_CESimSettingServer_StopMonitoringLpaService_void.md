# CESimSettingServer::StopMonitoringLpaService(void)

- ea: `0x18002672c`
- end: `0x1800268d8`
- name: `?StopMonitoringLpaService@CESimSettingServer@@AEAAJXZ`
- size: `428`
- prototype: `__int64 __fastcall(CESimSettingServer *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180028500`

## callees

- `0x18000178c`
- `0x180009ffc`
- `0x18001105c`
- `0x1800172bc`
- `0x18001dd10`
- `0x18002672c`

## import_xrefs

- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x1800267ff`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x1800267ff`

## string_xrefs

- `0x180026781`: `LpaSvc monitoring already stopped.`
- `0x1800267ac`: `CESimSettingServer::StopMonitoringLpaService`
- `0x180026878`: `CESimSettingServer::StopMonitoringLpaService`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CESimSettingServer::StopMonitoringLpaService(CESimSettingServer *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned __int16 **v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  int v10; // [rsp+20h] [rbp-40h]
  int v11; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v12[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v13; // [rsp+40h] [rbp-20h]
  unsigned __int16 *v14[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v15; // [rsp+58h] [rbp-8h]
  unsigned __int16 *v16; // [rsp+70h] [rbp+10h] BYREF

  if ( *((_QWORD *)this + 16) )
  {
    UnsubscribeServiceChangeNotifications();
    *((_QWORD *)this + 16) = 0;
    *(_OWORD *)v12 = 0;
    v13 = 0;
    *(_OWORD *)v14 = 0;
    v15 = 0;
    std::vector<unsigned short>::resize(v12);
    std::vector<unsigned short>::resize(v14);
    StringCchPrintfW(v12[0], v12[1] - v12[0], L"LpaSvc monitoring stopped.");
    v11 = 111;
    StringCchPrintfW(v14[0], v14[1] - v14[0], L"%S(%d):%s", "CESimSettingServer::StopMonitoringLpaService", v11, v12[0]);
    v6 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v6 > 4u )
    {
      v16 = v14[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v6,
        (__int64)byte_180075E29,
        v7,
        v8,
        (const unsigned __int16 **)&v16);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v14);
    v5 = v12;
  }
  else
  {
    *(_OWORD *)v14 = 0;
    v15 = 0;
    *(_OWORD *)v12 = 0;
    v13 = 0;
    std::vector<unsigned short>::resize(v14);
    std::vector<unsigned short>::resize(v12);
    StringCchPrintfW(v14[0], v14[1] - v14[0], L"LpaSvc monitoring already stopped.");
    v10 = 104;
    StringCchPrintfW(v12[0], v12[1] - v12[0], L"%S(%d):%s", "CESimSettingServer::StopMonitoringLpaService", v10, v14[0]);
    v2 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v2 > 3u )
    {
      v16 = v12[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v2,
        (__int64)byte_180075E49,
        v3,
        v4,
        (const unsigned __int16 **)&v16);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v12);
    v5 = v14;
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v5);
  return 0;
}

```

## disassembly

```asm
0x18002672c  mov     [rsp-8+arg_8], rbx
0x180026731  push    rbp
0x180026732  mov     rbp, rsp
0x180026735  sub     rsp, 60h
0x180026739  mov     rbx, rcx
0x18002673c  mov     rcx, [rcx+80h]
0x180026743  test    rcx, rcx
0x180026746  jnz     loc_1800267FF
0x18002674c  xorps   xmm0, xmm0
0x18002674f  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180026754  mov     [rbp+var_8], rcx
0x180026758  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18002675d  mov     [rbp+var_20], rcx
0x180026761  lea     rcx, [rbp+var_18]
0x180026765  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002676a  lea     rcx, [rbp+var_30]
0x18002676e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180026773  mov     rdx, [rbp+var_18+8]
0x180026777  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18002677b  sub     rdx, rcx
0x18002677e  sar     rdx, 1; unsigned __int64
0x180026781  lea     r8, aLpasvcMonitori; "LpaSvc monitoring already stopped."
0x180026788  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002678d  mov     rdx, [rbp+var_30+8]
0x180026791  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180026795  sub     rdx, rcx
0x180026798  sar     rdx, 1; unsigned __int64
0x18002679b  mov     rax, [rbp+var_18]
0x18002679f  mov     [rsp+60h+var_38], rax
0x1800267a4  mov     dword ptr [rsp+60h+var_40], 68h ; 'h'
0x1800267ac  lea     r9, aCesimsettingse_37; "CESimSettingServer::StopMonitoringLpaSe"...
0x1800267b3  lea     r8, aSDS; "%S(%d):%s"
0x1800267ba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800267bf  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800267c4  mov     ecx, [rax]
0x1800267c6  cmp     ecx, 3
0x1800267c9  jbe     short loc_1800267EC
0x1800267cb  mov     rcx, [rbp+var_30]
0x1800267cf  mov     [rbp+arg_0], rcx
0x1800267d3  lea     rcx, [rbp+arg_0]
0x1800267d7  mov     [rsp+60h+var_40], rcx
0x1800267dc  lea     rdx, byte_180075E49
0x1800267e3  mov     rcx, rax
0x1800267e6  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800267eb  nop
0x1800267ec  lea     rcx, [rbp+var_30]
0x1800267f0  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800267f5  nop
0x1800267f6  lea     rcx, [rbp+var_18]
0x1800267fa  jmp     loc_1800268C6
0x1800267ff  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x180026805  mov     qword ptr [rbx+80h], 0
0x180026810  xorps   xmm0, xmm0
0x180026813  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180026818  mov     [rbp+var_20], 0
0x180026820  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180026825  mov     [rbp+var_8], 0
0x18002682d  lea     rcx, [rbp+var_30]
0x180026831  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180026836  lea     rcx, [rbp+var_18]
0x18002683a  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002683f  mov     rdx, [rbp+var_30+8]
0x180026843  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180026847  sub     rdx, rcx
0x18002684a  sar     rdx, 1; unsigned __int64
0x18002684d  lea     r8, aLpasvcMonitori_0; "LpaSvc monitoring stopped."
0x180026854  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026859  mov     rdx, [rbp+var_18+8]
0x18002685d  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x180026861  sub     rdx, rcx
0x180026864  sar     rdx, 1; unsigned __int64
0x180026867  mov     rax, [rbp+var_30]
0x18002686b  mov     [rsp+60h+var_38], rax
0x180026870  mov     dword ptr [rsp+60h+var_40], 6Fh ; 'o'
0x180026878  lea     r9, aCesimsettingse_37; "CESimSettingServer::StopMonitoringLpaSe"...
0x18002687f  lea     r8, aSDS; "%S(%d):%s"
0x180026886  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002688b  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180026890  mov     ecx, [rax]
0x180026892  cmp     ecx, 4
0x180026895  jbe     short loc_1800268B8
0x180026897  mov     rcx, [rbp+var_18]
0x18002689b  mov     [rbp+arg_0], rcx
0x18002689f  lea     rcx, [rbp+arg_0]
0x1800268a3  mov     [rsp+60h+var_40], rcx
0x1800268a8  lea     rdx, byte_180075E29
0x1800268af  mov     rcx, rax
0x1800268b2  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800268b7  nop
0x1800268b8  lea     rcx, [rbp+var_18]
0x1800268bc  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800268c1  nop
0x1800268c2  lea     rcx, [rbp+var_30]
0x1800268c6  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800268cb  xor     eax, eax
0x1800268cd  mov     rbx, [rsp+60h+arg_8]
0x1800268d2  add     rsp, 60h
0x1800268d6  pop     rbp
0x1800268d7  retn
```
