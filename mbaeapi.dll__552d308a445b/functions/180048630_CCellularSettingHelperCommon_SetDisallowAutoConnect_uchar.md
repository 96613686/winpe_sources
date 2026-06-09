# CCellularSettingHelperCommon::SetDisallowAutoConnect(uchar)

- ea: `0x180048630`
- end: `0x180048890`
- name: `?SetDisallowAutoConnect@CCellularSettingHelperCommon@@UEAAJE@Z`
- size: `608`
- prototype: `__int64 __fastcall(CCellularSettingHelperCommon *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000178c`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x180048630`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180048873`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180048873`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004871f`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004871f`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x180048786`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x180048786`

## string_xrefs

- `0x18004872d`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x180048794`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x180048697`: `CCellularSettingHelperCommon::SetDisallowAutoConnect`
- `0x1800487ff`: `CCellularSettingHelperCommon::SetDisallowAutoConnect`

## pseudocode

```c
int __fastcall CCellularSettingHelperCommon::SetDisallowAutoConnect(CCellularSettingHelperCommon *this, char a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // eax
  unsigned int v9; // eax
  int v10; // ebx
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int v14; // [rsp+20h] [rbp-60h]
  unsigned int *v15; // [rsp+20h] [rbp-60h]
  __int64 v16; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v17[2]; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *v18[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v19; // [rsp+60h] [rbp-20h]
  unsigned __int16 *v20[2]; // [rsp+68h] [rbp-18h] BYREF
  __int64 v21; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]
  int v23; // [rsp+A0h] [rbp+20h] BYREF
  unsigned int v24; // [rsp+A8h] [rbp+28h] BYREF

  v21 = 0;
  v19 = 0;
  *(_OWORD *)v20 = 0;
  *(_OWORD *)v18 = 0;
  std::vector<unsigned short>::resize(v20);
  std::vector<unsigned short>::resize(v18);
  StringCchPrintfW(v20[0], v20[1] - v20[0], L"Enter");
  v14 = 225;
  StringCchPrintfW(v18[0], v18[1] - v18[0], L"%S(%d):%s", "CCellularSettingHelperCommon::SetDisallowAutoConnect");
  v4 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v4 > 5u )
  {
    *(unsigned __int16 **)v17 = v18[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)word_1800791AA,
      v5,
      v6,
      (const unsigned __int16 **)v17);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v18);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v20);
  v16 = 0;
  v23 = 0;
  v7 = WwanOpenHandle(1, 0, &v23, &v16);
  if ( v7 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xE3,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
             (const char *)v7,
             v14);
  v24 = a2 != 0;
  v15 = &v24;
  v9 = WwanSetInterface(v16, (char *)this + 8, 39, 4);
  if ( v9 )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xE8,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
            (const char *)v9,
            (unsigned int)&v24);
  }
  else
  {
    v19 = 0;
    v21 = 0;
    *(_OWORD *)v18 = 0;
    *(_OWORD *)v20 = 0;
    std::vector<unsigned short>::resize(v18);
    std::vector<unsigned short>::resize(v20);
    StringCchPrintfW(v18[0], v18[1] - v18[0], L"Exit");
    LODWORD(v15) = 234;
    StringCchPrintfW(
      v20[0],
      v20[1] - v20[0],
      L"%S(%d):%s",
      "CCellularSettingHelperCommon::SetDisallowAutoConnect",
      v15,
      v18[0],
      0,
      0);
    v11 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v11 > 5u )
    {
      *(unsigned __int16 **)v17 = v20[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v11,
        (__int64)byte_180079141,
        v12,
        v13,
        (const unsigned __int16 **)v17);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v20);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v18);
    v10 = 0;
  }
  WwanCloseHandle(v16, 0);
  return v10;
}

```

## disassembly

```asm
0x180048630  mov     [rsp-8+arg_0], rbx
0x180048635  mov     [rsp-8+arg_8], rdi
0x18004863a  push    rbp
0x18004863b  mov     rbp, rsp
0x18004863e  sub     rsp, 80h
0x180048645  xorps   xmm0, xmm0
0x180048648  mov     [rbp+var_8], 0
0x180048650  mov     rdi, rcx
0x180048653  mov     [rbp+var_20], 0
0x18004865b  lea     rcx, [rbp+var_18]
0x18004865f  mov     bl, dl
0x180048661  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180048666  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18004866b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180048670  lea     rcx, [rbp+var_30]
0x180048674  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180048679  mov     rdx, [rbp+var_18+8]
0x18004867d  lea     r8, aEnter; "Enter"
0x180048684  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x180048688  sub     rdx, rcx
0x18004868b  sar     rdx, 1; unsigned __int64
0x18004868e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048693  mov     rdx, [rbp+var_30+8]
0x180048697  lea     r9, aCcellularsetti_27; "CCellularSettingHelperCommon::SetDisall"...
0x18004869e  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x1800486a2  lea     r8, aSDS; "%S(%d):%s"
0x1800486a9  mov     rax, [rbp+var_18]
0x1800486ad  sub     rdx, rcx
0x1800486b0  mov     [rsp+80h+var_58], rax
0x1800486b5  sar     rdx, 1; unsigned __int64
0x1800486b8  mov     [rsp+80h+var_60], 0E1h
0x1800486c0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800486c5  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800486ca  mov     ecx, [rax]
0x1800486cc  cmp     ecx, 5
0x1800486cf  jbe     short loc_1800486F1
0x1800486d1  mov     rcx, [rbp+var_30]
0x1800486d5  lea     rdx, word_1800791AA
0x1800486dc  mov     qword ptr [rbp+var_38], rcx
0x1800486e0  lea     rcx, [rbp+var_38]
0x1800486e4  mov     qword ptr [rsp+80h+var_60], rcx; unsigned int
0x1800486e9  mov     rcx, rax
0x1800486ec  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800486f1  lea     rcx, [rbp+var_30]
0x1800486f5  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800486fa  lea     rcx, [rbp+var_18]
0x1800486fe  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180048703  xor     edx, edx
0x180048705  mov     [rbp+var_40], 0
0x18004870d  lea     r9, [rbp+var_40]
0x180048711  mov     [rbp+arg_10], 0
0x180048718  lea     r8, [rbp+arg_10]
0x18004871c  lea     ecx, [rdx+1]
0x18004871f  call    cs:__imp_WwanOpenHandle
0x180048725  test    eax, eax
0x180048727  jz      short loc_180048746
0x180048729  mov     rcx, [rbp+8]; this
0x18004872d  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180048734  mov     r9d, eax; char *
0x180048737  mov     edx, 0E3h; void *
0x18004873c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180048741  jmp     loc_18004887B
0x180048746  mov     rcx, [rbp+var_40]
0x18004874a  lea     rdx, [rdi+8]
0x18004874e  xor     eax, eax
0x180048750  mov     [rsp+80h+var_48], 0
0x180048759  mov     r9d, 4
0x18004875f  mov     [rsp+80h+var_50], 0
0x180048768  test    bl, bl
0x18004876a  mov     [rsp+80h+var_58], 0
0x180048773  setnz   al
0x180048776  mov     [rbp+arg_18], eax
0x180048779  lea     r8d, [r9+23h]
0x18004877d  lea     rax, [rbp+arg_18]
0x180048781  mov     qword ptr [rsp+80h+var_60], rax; unsigned int
0x180048786  call    cs:__imp_WwanSetInterface
0x18004878c  test    eax, eax
0x18004878e  jz      short loc_1800487AF
0x180048790  mov     rcx, [rbp+8]; this
0x180048794  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004879b  mov     r9d, eax; char *
0x18004879e  mov     edx, 0E8h; void *
0x1800487a3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800487a8  mov     ebx, eax
0x1800487aa  jmp     loc_18004886D
0x1800487af  xorps   xmm0, xmm0
0x1800487b2  mov     [rbp+var_20], 0
0x1800487ba  xorps   xmm1, xmm1
0x1800487bd  mov     [rbp+var_8], 0
0x1800487c5  lea     rcx, [rbp+var_30]
0x1800487c9  movdqu  xmmword ptr [rbp+var_30], xmm0
0x1800487ce  movdqu  xmmword ptr [rbp+var_18], xmm1
0x1800487d3  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800487d8  lea     rcx, [rbp+var_18]
0x1800487dc  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800487e1  mov     rdx, [rbp+var_30+8]
0x1800487e5  lea     r8, aExit; "Exit"
0x1800487ec  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x1800487f0  sub     rdx, rcx
0x1800487f3  sar     rdx, 1; unsigned __int64
0x1800487f6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800487fb  mov     rdx, [rbp+var_18+8]
0x1800487ff  lea     r9, aCcellularsetti_27; "CCellularSettingHelperCommon::SetDisall"...
0x180048806  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18004880a  lea     r8, aSDS; "%S(%d):%s"
0x180048811  mov     rax, [rbp+var_30]
0x180048815  sub     rdx, rcx
0x180048818  mov     [rsp+80h+var_58], rax
0x18004881d  sar     rdx, 1; unsigned __int64
0x180048820  mov     [rsp+80h+var_60], 0EAh
0x180048828  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004882d  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180048832  mov     ecx, [rax]
0x180048834  cmp     ecx, 5
0x180048837  jbe     short loc_180048859
0x180048839  mov     rcx, [rbp+var_18]
0x18004883d  lea     rdx, byte_180079141
0x180048844  mov     qword ptr [rbp+var_38], rcx
0x180048848  lea     rcx, [rbp+var_38]
0x18004884c  mov     qword ptr [rsp+80h+var_60], rcx
0x180048851  mov     rcx, rax
0x180048854  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180048859  lea     rcx, [rbp+var_18]
0x18004885d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180048862  lea     rcx, [rbp+var_30]
0x180048866  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004886b  xor     ebx, ebx
0x18004886d  mov     rcx, [rbp+var_40]
0x180048871  xor     edx, edx
0x180048873  call    cs:__imp_WwanCloseHandle
0x180048879  mov     eax, ebx
0x18004887b  lea     r11, [rsp+80h+var_s0]
0x180048883  mov     rbx, [r11+10h]
0x180048887  mov     rdi, [r11+18h]
0x18004888b  mov     rsp, r11
0x18004888e  pop     rbp
0x18004888f  retn
```
