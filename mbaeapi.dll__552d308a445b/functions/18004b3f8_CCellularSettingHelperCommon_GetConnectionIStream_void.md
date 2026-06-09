# CCellularSettingHelperCommon::_GetConnectionIStream(void)

- ea: `0x18004b3f8`
- end: `0x18004b6e3`
- name: `?_GetConnectionIStream@CCellularSettingHelperCommon@@IEAAJXZ`
- size: `747`
- prototype: `int __fastcall(CCellularSettingHelperCommon *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180047de0`

## callees

- `0x18000178c`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x180036438`
- `0x18004b3f8`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004b6d0`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004b6d0`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004b5f2`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004b6c2`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004b5f2`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004b6c2`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004b4e2`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004b4e2`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004b56a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004b56a`

## string_xrefs

- `0x18004b4f3`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004b57b`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004b5d3`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004b473`: `CCellularSettingHelperCommon::_GetConnectionIStream`
- `0x18004b665`: `CCellularSettingHelperCommon::_GetConnectionIStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
int __fastcall CCellularSettingHelperCommon::_GetConnectionIStream(CCellularSettingHelperCommon *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // eax
  unsigned int Interface; // eax
  int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // rcx
  int v12; // eax
  const struct _tlgProvider_t *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // [rsp+20h] [rbp-59h]
  unsigned int *v17; // [rsp+20h] [rbp-59h]
  __int64 v18; // [rsp+40h] [rbp-39h] BYREF
  __int64 v19; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v20[4]; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int16 *v21[2]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v22; // [rsp+70h] [rbp-9h]
  unsigned __int16 *v23[2]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v24; // [rsp+88h] [rbp+Fh]
  unsigned __int16 *v25[2]; // [rsp+90h] [rbp+17h] BYREF
  __int64 v26; // [rsp+A0h] [rbp+27h]
  unsigned __int16 *v27[2]; // [rsp+A8h] [rbp+2Fh] BYREF
  __int64 v28; // [rsp+B8h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  unsigned int v30; // [rsp+E8h] [rbp+6Fh] BYREF
  int v31; // [rsp+F0h] [rbp+77h] BYREF
  int v32; // [rsp+F8h] [rbp+7Fh] BYREF

  *(_OWORD *)v21 = 0;
  v22 = 0;
  *(_OWORD *)v23 = 0;
  v24 = 0;
  std::vector<unsigned short>::resize(v21);
  std::vector<unsigned short>::resize(v23);
  StringCchPrintfW(v21[0], v21[1] - v21[0], L"Enter");
  v16 = 350;
  StringCchPrintfW(v23[0], v23[1] - v23[0], L"%S(%d):%s", "CCellularSettingHelperCommon::_GetConnectionIStream");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    *(unsigned __int16 **)v20 = v23[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)&dword_180079014,
      v3,
      v4,
      (const unsigned __int16 **)v20);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v23);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v21);
  v19 = 0;
  v31 = 0;
  v5 = WwanOpenHandle(1, 0, &v31, &v19);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x160,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
             (const char *)v5,
             v16);
  v21[0] = (unsigned __int16 *)&v19;
  LOBYTE(v21[1]) = 1;
  v18 = 0;
  v30 = 0;
  v32 = 0;
  v23[0] = (unsigned __int16 *)&v18;
  LOBYTE(v23[1]) = 1;
  v17 = &v30;
  Interface = WwanQueryInterface(v19, (char *)this + 8, 8);
  if ( Interface )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x16C,
           (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
           (const char *)Interface,
           (unsigned int)&v30);
  }
  else
  {
    v9 = v30;
    v10 = v18;
    *(_OWORD *)v20 = 0;
    v11 = *((_QWORD *)this + 5);
    if ( v11 )
    {
      *(_QWORD *)v20 = *((_QWORD *)this + 4);
      *(_QWORD *)&v20[2] = v11;
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 12));
    }
    v12 = CWwanTranslator::ProcessConnectionIStream(v20, (char *)this + 8, v10, v9);
    v8 = v12;
    if ( v12 >= 0 )
    {
      *(_OWORD *)v27 = 0;
      v28 = 0;
      *(_OWORD *)v25 = 0;
      v26 = 0;
      std::vector<unsigned short>::resize(v27);
      std::vector<unsigned short>::resize(v25);
      StringCchPrintfW(v27[0], v27[1] - v27[0], L"Exit");
      LODWORD(v17) = 368;
      StringCchPrintfW(
        v25[0],
        v25[1] - v25[0],
        L"%S(%d):%s",
        "CCellularSettingHelperCommon::_GetConnectionIStream",
        v17,
        v27[0],
        &v32,
        0);
      v13 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v13 > 5u )
      {
        *(unsigned __int16 **)v20 = v25[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v13,
          (__int64)byte_180078FAB,
          v14,
          v15,
          (const unsigned __int16 **)v20);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v25);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v27);
      if ( v18 )
        WwanFreeMemory(v18);
      v8 = 0;
      goto LABEL_18;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16E,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
      (const char *)(unsigned int)v12,
      (int)&v30);
  }
  if ( v18 )
    WwanFreeMemory(v18);
LABEL_18:
  WwanCloseHandle(v19, 0);
  return v8;
}

```

## disassembly

```asm
0x18004b3f8  push    rbp
0x18004b3fa  push    rbx
0x18004b3fb  push    rdi
0x18004b3fc  lea     rbp, [rsp-47h]
0x18004b401  sub     rsp, 0C0h
0x18004b408  mov     rbx, rcx
0x18004b40b  xorps   xmm0, xmm0
0x18004b40e  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x18004b413  mov     [rbp+57h+var_60], 0
0x18004b41b  movdqu  xmmword ptr [rbp+57h+var_58], xmm0
0x18004b420  mov     [rbp+57h+var_48], 0
0x18004b428  lea     rcx, [rbp+57h+var_70]
0x18004b42c  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004b431  lea     rcx, [rbp+57h+var_58]
0x18004b435  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004b43a  mov     rdx, [rbp+57h+var_70+8]
0x18004b43e  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x18004b442  sub     rdx, rcx
0x18004b445  sar     rdx, 1; unsigned __int64
0x18004b448  lea     r8, aEnter; "Enter"
0x18004b44f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b454  mov     rdx, [rbp+57h+var_58+8]
0x18004b458  mov     rcx, [rbp+57h+var_58]; unsigned __int16 *
0x18004b45c  sub     rdx, rcx
0x18004b45f  sar     rdx, 1; unsigned __int64
0x18004b462  mov     rax, [rbp+57h+var_70]
0x18004b466  mov     [rsp+0D0h+var_A8], rax
0x18004b46b  mov     [rsp+0D0h+var_B0], 15Eh
0x18004b473  lea     r9, aCcellularsetti_34; "CCellularSettingHelperCommon::_GetConne"...
0x18004b47a  lea     r8, aSDS; "%S(%d):%s"
0x18004b481  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b486  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004b48b  mov     ecx, [rax]
0x18004b48d  cmp     ecx, 5
0x18004b490  jbe     short loc_18004B4B3
0x18004b492  mov     rcx, [rbp+57h+var_58]
0x18004b496  mov     qword ptr [rbp+57h+var_80], rcx
0x18004b49a  lea     rcx, [rbp+57h+var_80]
0x18004b49e  mov     qword ptr [rsp+0D0h+var_B0], rcx; unsigned int
0x18004b4a3  lea     rdx, dword_180079014
0x18004b4aa  mov     rcx, rax
0x18004b4ad  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004b4b2  nop
0x18004b4b3  lea     rcx, [rbp+57h+var_58]
0x18004b4b7  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004b4bc  nop
0x18004b4bd  lea     rcx, [rbp+57h+var_70]
0x18004b4c1  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004b4c6  mov     [rbp+57h+var_88], 0
0x18004b4ce  mov     [rbp+57h+arg_10], 0
0x18004b4d5  lea     r9, [rbp+57h+var_88]
0x18004b4d9  lea     r8, [rbp+57h+arg_10]
0x18004b4dd  xor     edx, edx
0x18004b4df  lea     ecx, [rdx+1]
0x18004b4e2  call    cs:__imp_WwanOpenHandle
0x18004b4e8  test    eax, eax
0x18004b4ea  jz      short loc_18004B509
0x18004b4ec  mov     rcx, [rbp+5Fh]; this
0x18004b4f0  mov     r9d, eax; char *
0x18004b4f3  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004b4fa  mov     edx, 160h; void *
0x18004b4ff  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004b504  jmp     loc_18004B6D8
0x18004b509  lea     rax, [rbp+57h+var_88]
0x18004b50d  mov     [rbp+57h+var_70], rax
0x18004b511  mov     byte ptr [rbp+57h+var_70+8], 1
0x18004b515  mov     [rbp+57h+var_90], 0
0x18004b51d  mov     [rbp+57h+arg_8], 0
0x18004b524  mov     [rbp+57h+arg_18], 0
0x18004b52b  lea     rax, [rbp+57h+var_90]
0x18004b52f  mov     [rbp+57h+var_58], rax
0x18004b533  mov     byte ptr [rbp+57h+var_58+8], 1
0x18004b537  mov     [rsp+0D0h+var_98], 0
0x18004b540  lea     rax, [rbp+57h+arg_18]
0x18004b544  mov     [rsp+0D0h+var_A0], rax
0x18004b549  lea     rax, [rbp+57h+var_90]
0x18004b54d  mov     [rsp+0D0h+var_A8], rax
0x18004b552  lea     rax, [rbp+57h+arg_8]
0x18004b556  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18004b55b  xor     r9d, r9d
0x18004b55e  lea     r8d, [r9+8]
0x18004b562  lea     rdx, [rbx+8]
0x18004b566  mov     rcx, [rbp+57h+var_88]
0x18004b56a  call    cs:__imp_WwanQueryInterface
0x18004b570  test    eax, eax
0x18004b572  jz      short loc_18004B590
0x18004b574  mov     rcx, [rbp+5Fh]; this
0x18004b578  mov     r9d, eax; char *
0x18004b57b  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004b582  mov     edx, 16Ch; void *
0x18004b587  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004b58c  mov     ebx, eax
0x18004b58e  jmp     short loc_18004B5E5
0x18004b590  mov     r9d, [rbp+57h+arg_8]
0x18004b594  mov     r8, [rbp+57h+var_90]
0x18004b598  xorps   xmm0, xmm0
0x18004b59b  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x18004b5a0  mov     rcx, [rbx+28h]
0x18004b5a4  test    rcx, rcx
0x18004b5a7  jz      short loc_18004B5B9
0x18004b5a9  mov     rax, [rbx+20h]
0x18004b5ad  mov     qword ptr [rbp+57h+var_80], rax
0x18004b5b1  mov     qword ptr [rbp+57h+var_80+8], rcx
0x18004b5b5  lock inc dword ptr [rcx+0Ch]
0x18004b5b9  lea     rdx, [rbx+8]
0x18004b5bd  lea     rcx, [rbp+57h+var_80]
0x18004b5c1  call    ?ProcessConnectionIStream@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@PEAEI@Z; CWwanTranslator::ProcessConnectionIStream(std::weak_ptr<CWwanTranslator>,_GUID const &,uchar *,uint)
0x18004b5c6  mov     ebx, eax
0x18004b5c8  test    eax, eax
0x18004b5ca  jns     short loc_18004B5FD
0x18004b5cc  mov     rcx, [rbp+5Fh]; this
0x18004b5d0  mov     r9d, eax; char *
0x18004b5d3  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004b5da  mov     edx, 16Eh; void *
0x18004b5df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b5e4  nop
0x18004b5e5  mov     rcx, [rbp+57h+var_90]
0x18004b5e9  test    rcx, rcx
0x18004b5ec  jz      loc_18004B6CA
0x18004b5f2  call    cs:__imp_WwanFreeMemory
0x18004b5f8  jmp     loc_18004B6CA
0x18004b5fd  xorps   xmm0, xmm0
0x18004b600  movdqu  xmmword ptr [rbp+57h+var_28], xmm0
0x18004b605  mov     [rbp+57h+var_18], 0
0x18004b60d  movdqu  xmmword ptr [rbp+57h+var_40], xmm0
0x18004b612  mov     [rbp+57h+var_30], 0
0x18004b61a  lea     rcx, [rbp+57h+var_28]
0x18004b61e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004b623  lea     rcx, [rbp+57h+var_40]
0x18004b627  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004b62c  mov     rdx, [rbp+57h+var_28+8]
0x18004b630  mov     rcx, [rbp+57h+var_28]; unsigned __int16 *
0x18004b634  sub     rdx, rcx
0x18004b637  sar     rdx, 1; unsigned __int64
0x18004b63a  lea     r8, aExit; "Exit"
0x18004b641  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b646  mov     rdx, [rbp+57h+var_40+8]
0x18004b64a  mov     rcx, [rbp+57h+var_40]; unsigned __int16 *
0x18004b64e  sub     rdx, rcx
0x18004b651  sar     rdx, 1; unsigned __int64
0x18004b654  mov     rax, [rbp+57h+var_28]
0x18004b658  mov     [rsp+0D0h+var_A8], rax
0x18004b65d  mov     [rsp+0D0h+var_B0], 170h
0x18004b665  lea     r9, aCcellularsetti_34; "CCellularSettingHelperCommon::_GetConne"...
0x18004b66c  lea     r8, aSDS; "%S(%d):%s"
0x18004b673  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b678  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004b67d  mov     ecx, [rax]
0x18004b67f  cmp     ecx, 5
0x18004b682  jbe     short loc_18004B6A5
0x18004b684  mov     rcx, [rbp+57h+var_40]
0x18004b688  mov     qword ptr [rbp+57h+var_80], rcx
0x18004b68c  lea     rcx, [rbp+57h+var_80]
0x18004b690  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x18004b695  lea     rdx, byte_180078FAB
0x18004b69c  mov     rcx, rax
0x18004b69f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004b6a4  nop
0x18004b6a5  lea     rcx, [rbp+57h+var_40]
0x18004b6a9  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004b6ae  nop
0x18004b6af  lea     rcx, [rbp+57h+var_28]
0x18004b6b3  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004b6b8  nop
0x18004b6b9  mov     rcx, [rbp+57h+var_90]
0x18004b6bd  test    rcx, rcx
0x18004b6c0  jz      short loc_18004B6C8
0x18004b6c2  call    cs:__imp_WwanFreeMemory
0x18004b6c8  xor     ebx, ebx
0x18004b6ca  xor     edx, edx
0x18004b6cc  mov     rcx, [rbp+57h+var_88]
0x18004b6d0  call    cs:__imp_WwanCloseHandle
0x18004b6d6  mov     eax, ebx
0x18004b6d8  add     rsp, 0C0h
0x18004b6df  pop     rdi
0x18004b6e0  pop     rbx
0x18004b6e1  pop     rbp
0x18004b6e2  retn
```
