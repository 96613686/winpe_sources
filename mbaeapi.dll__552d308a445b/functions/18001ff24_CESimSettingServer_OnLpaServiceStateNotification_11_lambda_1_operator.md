# _CESimSettingServer::OnLpaServiceStateNotification_::_11_::_lambda_1_::operator()

- ea: `0x18001ff24`
- end: `0x18002006e`
- name: `_CESimSettingServer::OnLpaServiceStateNotification_::_11_::_lambda_1_::operator()`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180028530`

## callees

- `0x18000178c`
- `0x180009ffc`
- `0x18001105c`
- `0x180016134`
- `0x1800172bc`
- `0x18001dd10`
- `0x18001ff24`

## import_xrefs

- `luiapi!LuiOpenHandle` at `0x18001ff5a`
- `luiapi!LuiOpenHandle` at `0x18001ff5a`
- `luiapi!LuiRegisterForLpaNotifications` at `0x18001ff7d`
- `luiapi!LuiRegisterForLpaNotifications` at `0x18001ff7d`

## string_xrefs

- `0x18001ffe5`: `LpaSvc has already started. Ignore SERVICE_NOTIFY_RUNNING`
- `0x180020010`: `CESimSettingServer::OnLpaServiceStateNotification::<lambda_1>::operator ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CESimSettingServer::OnLpaServiceStateNotification_::_11_::_lambda_1_::operator()(__int64 *a1)
{
  __int64 v2; // r9
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  int v5; // eax
  __int64 v6; // rdx
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v11[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+40h] [rbp-20h]
  unsigned __int16 *v13[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v14; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  unsigned __int16 *v16; // [rsp+70h] [rbp+10h] BYREF

  v2 = *a1;
  v3 = (_QWORD *)(*a1 + 112);
  if ( *v3 == -1 )
  {
    v4 = *(_BYTE *)(v2 + 120) != 0 ? 2 : 0;
    *v3 = -1;
    v5 = LuiOpenHandle(v3, v4, &CESimSettingServer::ProcessLpaCallback, v2);
    if ( v5 >= 0 )
    {
      LODWORD(v16) = 0;
      v5 = LuiRegisterForLpaNotifications(*(_QWORD *)(*a1 + 112), &v16);
      if ( v5 >= 0 )
        return;
      v6 = 150;
    }
    else
    {
      v6 = 147;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v6,
      (int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\esimsettingserver.cpp",
      (const char *)(unsigned int)v5);
  }
  else
  {
    *(_OWORD *)v13 = 0;
    v14 = 0;
    *(_OWORD *)v11 = 0;
    v12 = 0;
    std::vector<unsigned short>::resize(v13);
    std::vector<unsigned short>::resize(v11);
    StringCchPrintfW(v13[0], v13[1] - v13[0], L"LpaSvc has already started. Ignore SERVICE_NOTIFY_RUNNING");
    v10 = 155;
    StringCchPrintfW(
      v11[0],
      v11[1] - v11[0],
      L"%S(%d):%s",
      "CESimSettingServer::OnLpaServiceStateNotification::<lambda_1>::operator ()",
      v10,
      v13[0]);
    v7 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v7 > 4u )
    {
      v16 = v11[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v7,
        (__int64)word_180075DA2,
        v8,
        v9,
        (const unsigned __int16 **)&v16);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v11);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v13);
  }
}

```

## disassembly

```asm
0x18001ff24  mov     [rsp-8+arg_8], rbx
0x18001ff29  push    rbp
0x18001ff2a  mov     rbp, rsp
0x18001ff2d  sub     rsp, 60h
0x18001ff31  mov     rbx, rcx
0x18001ff34  mov     r9, [rcx]
0x18001ff37  lea     rcx, [r9+70h]
0x18001ff3b  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18001ff3f  jnz     short loc_18001FFA8
0x18001ff41  mov     al, [r9+78h]
0x18001ff45  neg     al
0x18001ff47  sbb     edx, edx
0x18001ff49  and     edx, 2
0x18001ff4c  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18001ff53  lea     r8, ?ProcessLpaCallback@CESimSettingServer@@SAXPEAX0W4__MIDL_imports_0004@@_KPEAE@Z; CESimSettingServer::ProcessLpaCallback(void *,void *,__MIDL_imports_0004,unsigned __int64,uchar *)
0x18001ff5a  call    cs:__imp_LuiOpenHandle
0x18001ff60  test    eax, eax
0x18001ff62  jns     short loc_18001FF6B
0x18001ff64  mov     edx, 93h
0x18001ff69  jmp     short loc_18001FF90
0x18001ff6b  mov     dword ptr [rbp+arg_0], 0
0x18001ff72  mov     rcx, [rbx]
0x18001ff75  lea     rdx, [rbp+arg_0]
0x18001ff79  mov     rcx, [rcx+70h]
0x18001ff7d  call    cs:__imp_LuiRegisterForLpaNotifications
0x18001ff83  test    eax, eax
0x18001ff85  jns     loc_180020063
0x18001ff8b  mov     edx, 96h; void *
0x18001ff90  lea     r8, aOnecoreuapNetM_5; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18001ff97  mov     r9d, eax; char *
0x18001ff9a  mov     rcx, [rbp+8]; this
0x18001ff9e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ffa3  jmp     loc_180020063
0x18001ffa8  xorps   xmm0, xmm0
0x18001ffab  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18001ffb0  mov     [rbp+var_8], 0
0x18001ffb8  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18001ffbd  mov     [rbp+var_20], 0
0x18001ffc5  lea     rcx, [rbp+var_18]
0x18001ffc9  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18001ffce  lea     rcx, [rbp+var_30]
0x18001ffd2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18001ffd7  mov     rdx, [rbp+var_18+8]
0x18001ffdb  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18001ffdf  sub     rdx, rcx
0x18001ffe2  sar     rdx, 1; unsigned __int64
0x18001ffe5  lea     r8, aLpasvcHasAlrea; "LpaSvc has already started. Ignore SERV"...
0x18001ffec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001fff1  mov     rdx, [rbp+var_30+8]
0x18001fff5  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x18001fff9  sub     rdx, rcx
0x18001fffc  sar     rdx, 1; unsigned __int64
0x18001ffff  mov     rax, [rbp+var_18]
0x180020003  mov     [rsp+60h+var_38], rax
0x180020008  mov     dword ptr [rsp+60h+var_40], 9Bh
0x180020010  lea     r9, aCesimsettingse_27; "CESimSettingServer::OnLpaServiceStateNo"...
0x180020017  lea     r8, aSDS; "%S(%d):%s"
0x18002001e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020023  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180020028  mov     ecx, [rax]
0x18002002a  cmp     ecx, 4
0x18002002d  jbe     short loc_180020050
0x18002002f  mov     rcx, [rbp+var_30]
0x180020033  mov     [rbp+arg_0], rcx
0x180020037  lea     rcx, [rbp+arg_0]
0x18002003b  mov     [rsp+60h+var_40], rcx
0x180020040  lea     rdx, word_180075DA2
0x180020047  mov     rcx, rax
0x18002004a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002004f  nop
0x180020050  lea     rcx, [rbp+var_30]
0x180020054  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180020059  nop
0x18002005a  lea     rcx, [rbp+var_18]
0x18002005e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180020063  mov     rbx, [rsp+60h+arg_8]
0x180020068  add     rsp, 60h
0x18002006c  pop     rbp
0x18002006d  retn
```
