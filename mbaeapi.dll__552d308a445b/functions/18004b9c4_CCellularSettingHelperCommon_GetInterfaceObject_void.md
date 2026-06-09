# CCellularSettingHelperCommon::_GetInterfaceObject(void)

- ea: `0x18004b9c4`
- end: `0x18004bd1f`
- name: `?_GetInterfaceObject@CCellularSettingHelperCommon@@IEAAJXZ`
- size: `859`
- prototype: `int __fastcall(CCellularSettingHelperCommon *this)`
- caller_count: `1`
- callee_count: `10`
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
- `0x180037098`
- `0x180037ae8`
- `0x18004b9c4`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004bd09`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004bd09`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004bbbe`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004bc2b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004bcfb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004bbbe`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004bc2b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004bcfb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004bab1`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004bab1`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004bb3c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004bb3c`

## string_xrefs

- `0x18004bac2`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004bb4d`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004bba3`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004bc0c`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004ba42`: `CCellularSettingHelperCommon::_GetInterfaceObject`
- `0x18004bc9e`: `CCellularSettingHelperCommon::_GetInterfaceObject`

## pseudocode

```c
int __fastcall CCellularSettingHelperCommon::_GetInterfaceObject(CCellularSettingHelperCommon *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // eax
  unsigned int Interface; // eax
  int v8; // ebx
  __int64 v9; // r14
  __int64 v10; // rcx
  int v11; // eax
  int v12; // edi
  __int64 v13; // rcx
  int v14; // eax
  const struct _tlgProvider_t *v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned int v18; // [rsp+20h] [rbp-69h]
  unsigned int *v19; // [rsp+20h] [rbp-69h]
  __int64 v20; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v21[4]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v22; // [rsp+58h] [rbp-31h] BYREF
  unsigned __int16 *v23[2]; // [rsp+60h] [rbp-29h] BYREF
  __int64 v24; // [rsp+70h] [rbp-19h]
  unsigned __int16 *v25[2]; // [rsp+78h] [rbp-11h] BYREF
  __int64 v26; // [rsp+88h] [rbp-1h]
  unsigned __int16 *v27[2]; // [rsp+90h] [rbp+7h] BYREF
  __int64 v28; // [rsp+A0h] [rbp+17h]
  unsigned __int16 *v29[2]; // [rsp+A8h] [rbp+1Fh] BYREF
  __int64 v30; // [rsp+B8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  int v32; // [rsp+F8h] [rbp+6Fh] BYREF
  int v33; // [rsp+100h] [rbp+77h] BYREF
  unsigned int v34; // [rsp+108h] [rbp+7Fh] BYREF

  *(_OWORD *)v23 = 0;
  v24 = 0;
  *(_OWORD *)v25 = 0;
  v26 = 0;
  std::vector<unsigned short>::resize(v23);
  std::vector<unsigned short>::resize(v25);
  StringCchPrintfW(v23[0], v23[1] - v23[0], L"Enter");
  v18 = 374;
  StringCchPrintfW(v25[0], v25[1] - v25[0], L"%S(%d):%s", "CCellularSettingHelperCommon::_GetInterfaceObject");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    *(unsigned __int16 **)v21 = v25[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)&word_180078FCE,
      v3,
      v4,
      (const unsigned __int16 **)v21);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v25);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v23);
  v22 = 0;
  v32 = 0;
  v5 = WwanOpenHandle(1, 0, &v32, &v22);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x178,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
             (const char *)v5,
             v18);
  v23[0] = (unsigned __int16 *)&v22;
  LOBYTE(v23[1]) = 1;
  v20 = 0;
  v34 = 0;
  v33 = 0;
  v25[0] = (unsigned __int16 *)&v20;
  LOBYTE(v25[1]) = 1;
  v19 = &v34;
  Interface = WwanQueryInterface(v22, (char *)this + 8, 7);
  if ( Interface )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x184,
           (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
           (const char *)Interface,
           (unsigned int)&v34);
  }
  else
  {
    v9 = v20;
    *(_OWORD *)v21 = 0;
    v10 = *((_QWORD *)this + 5);
    if ( v10 )
    {
      *(_QWORD *)v21 = *((_QWORD *)this + 4);
      *(_QWORD *)&v21[2] = v10;
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 12));
    }
    v11 = CWwanTranslator::ProcessModemCap(v21, (char *)this + 8);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x188,
        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
        (const char *)(unsigned int)v11,
        (int)&v34);
      if ( v20 )
        WwanFreeMemory(v20);
      v8 = v12;
      goto LABEL_24;
    }
    *(_OWORD *)v21 = 0;
    v13 = *((_QWORD *)this + 5);
    if ( v13 )
    {
      *(_QWORD *)v21 = *((_QWORD *)this + 4);
      *(_QWORD *)&v21[2] = v13;
      _InterlockedIncrement((volatile signed __int32 *)(v13 + 12));
    }
    v14 = CWwanTranslator::ProcessRadioState(v21, (char *)this + 8, v9 + 1036);
    v8 = v14;
    if ( v14 >= 0 )
    {
      *(_OWORD *)v29 = 0;
      v30 = 0;
      *(_OWORD *)v27 = 0;
      v28 = 0;
      std::vector<unsigned short>::resize(v29);
      std::vector<unsigned short>::resize(v27);
      StringCchPrintfW(v29[0], v29[1] - v29[0], L"Exit");
      LODWORD(v19) = 397;
      StringCchPrintfW(
        v27[0],
        v27[1] - v27[0],
        L"%S(%d):%s",
        "CCellularSettingHelperCommon::_GetInterfaceObject",
        v19,
        v29[0],
        &v33,
        0);
      v15 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v15 > 5u )
      {
        *(unsigned __int16 **)v21 = v27[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v15,
          (__int64)qword_180078F88,
          v16,
          v17,
          (const unsigned __int16 **)v21);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v27);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v29);
      if ( v20 )
        WwanFreeMemory(v20);
      v8 = 0;
      goto LABEL_24;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
      (const char *)(unsigned int)v14,
      (int)&v34);
  }
  if ( v20 )
    WwanFreeMemory(v20);
LABEL_24:
  WwanCloseHandle(v22, 0);
  return v8;
}

```

## disassembly

```asm
0x18004b9c4  push    rbp
0x18004b9c6  push    rbx
0x18004b9c7  push    rsi
0x18004b9c8  push    rdi
0x18004b9c9  push    r14
0x18004b9cb  lea     rbp, [rsp-37h]
0x18004b9d0  sub     rsp, 0C0h
0x18004b9d7  mov     rbx, rcx
0x18004b9da  xorps   xmm0, xmm0
0x18004b9dd  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x18004b9e2  mov     [rbp+57h+var_70], 0
0x18004b9ea  movdqu  xmmword ptr [rbp+57h+var_68], xmm0
0x18004b9ef  mov     [rbp+57h+var_58], 0
0x18004b9f7  lea     rcx, [rbp+57h+var_80]
0x18004b9fb  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004ba00  lea     rcx, [rbp+57h+var_68]
0x18004ba04  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004ba09  mov     rdx, [rbp+57h+var_80+8]
0x18004ba0d  mov     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x18004ba11  sub     rdx, rcx
0x18004ba14  sar     rdx, 1; unsigned __int64
0x18004ba17  lea     r8, aEnter; "Enter"
0x18004ba1e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004ba23  mov     rdx, [rbp+57h+var_68+8]
0x18004ba27  mov     rcx, [rbp+57h+var_68]; unsigned __int16 *
0x18004ba2b  sub     rdx, rcx
0x18004ba2e  sar     rdx, 1; unsigned __int64
0x18004ba31  mov     rax, [rbp+57h+var_80]
0x18004ba35  mov     [rsp+0E0h+var_B8], rax
0x18004ba3a  mov     [rsp+0E0h+var_C0], 176h
0x18004ba42  lea     r9, aCcellularsetti_13; "CCellularSettingHelperCommon::_GetInter"...
0x18004ba49  lea     r8, aSDS; "%S(%d):%s"
0x18004ba50  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004ba55  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004ba5a  mov     ecx, [rax]
0x18004ba5c  cmp     ecx, 5
0x18004ba5f  jbe     short loc_18004BA82
0x18004ba61  mov     rcx, [rbp+57h+var_68]
0x18004ba65  mov     qword ptr [rbp+57h+var_98], rcx
0x18004ba69  lea     rcx, [rbp+57h+var_98]
0x18004ba6d  mov     qword ptr [rsp+0E0h+var_C0], rcx; unsigned int
0x18004ba72  lea     rdx, word_180078FCE
0x18004ba79  mov     rcx, rax
0x18004ba7c  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004ba81  nop
0x18004ba82  lea     rcx, [rbp+57h+var_68]
0x18004ba86  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004ba8b  nop
0x18004ba8c  lea     rcx, [rbp+57h+var_80]
0x18004ba90  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004ba95  mov     [rbp+57h+var_88], 0
0x18004ba9d  mov     [rbp+57h+arg_8], 0
0x18004baa4  lea     r9, [rbp+57h+var_88]
0x18004baa8  lea     r8, [rbp+57h+arg_8]
0x18004baac  xor     edx, edx
0x18004baae  lea     ecx, [rdx+1]
0x18004bab1  call    cs:__imp_WwanOpenHandle
0x18004bab7  test    eax, eax
0x18004bab9  jz      short loc_18004BAD8
0x18004babb  mov     rcx, [rbp+5Fh]; this
0x18004babf  mov     r9d, eax; char *
0x18004bac2  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004bac9  mov     edx, 178h; void *
0x18004bace  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004bad3  jmp     loc_18004BD11
0x18004bad8  lea     rax, [rbp+57h+var_88]
0x18004badc  mov     [rbp+57h+var_80], rax
0x18004bae0  mov     byte ptr [rbp+57h+var_80+8], 1
0x18004bae4  mov     [rbp+57h+var_A0], 0
0x18004baec  mov     [rbp+57h+arg_18], 0
0x18004baf3  mov     [rbp+57h+arg_10], 0
0x18004bafa  lea     rax, [rbp+57h+var_A0]
0x18004bafe  mov     [rbp+57h+var_68], rax
0x18004bb02  mov     byte ptr [rbp+57h+var_68+8], 1
0x18004bb06  lea     rsi, [rbx+8]
0x18004bb0a  mov     [rsp+0E0h+var_A8], 0
0x18004bb13  lea     rax, [rbp+57h+arg_10]
0x18004bb17  mov     [rsp+0E0h+var_B0], rax
0x18004bb1c  lea     rax, [rbp+57h+var_A0]
0x18004bb20  mov     [rsp+0E0h+var_B8], rax
0x18004bb25  lea     rax, [rbp+57h+arg_18]
0x18004bb29  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18004bb2e  xor     r9d, r9d
0x18004bb31  lea     r8d, [r9+7]
0x18004bb35  mov     rdx, rsi
0x18004bb38  mov     rcx, [rbp+57h+var_88]
0x18004bb3c  call    cs:__imp_WwanQueryInterface
0x18004bb42  test    eax, eax
0x18004bb44  jz      short loc_18004BB65
0x18004bb46  mov     rcx, [rbp+5Fh]; this
0x18004bb4a  mov     r9d, eax; char *
0x18004bb4d  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004bb54  mov     edx, 184h; void *
0x18004bb59  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004bb5e  mov     ebx, eax
0x18004bb60  jmp     loc_18004BC1E
0x18004bb65  mov     r14, [rbp+57h+var_A0]
0x18004bb69  xorps   xmm0, xmm0
0x18004bb6c  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x18004bb71  mov     rcx, [rbx+28h]
0x18004bb75  test    rcx, rcx
0x18004bb78  jz      short loc_18004BB8A
0x18004bb7a  mov     rax, [rbx+20h]
0x18004bb7e  mov     qword ptr [rbp+57h+var_98], rax
0x18004bb82  mov     qword ptr [rbp+57h+var_98+8], rcx
0x18004bb86  lock inc dword ptr [rcx+0Ch]
0x18004bb8a  mov     rdx, rsi
0x18004bb8d  lea     rcx, [rbp+57h+var_98]
0x18004bb91  call    ?ProcessModemCap@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@@Z; CWwanTranslator::ProcessModemCap(std::weak_ptr<CWwanTranslator>,_GUID const &)
0x18004bb96  mov     edi, eax
0x18004bb98  test    eax, eax
0x18004bb9a  jns     short loc_18004BBCB
0x18004bb9c  mov     rcx, [rbp+5Fh]; this
0x18004bba0  mov     r9d, eax; char *
0x18004bba3  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004bbaa  mov     edx, 188h; void *
0x18004bbaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bbb4  nop
0x18004bbb5  mov     rcx, [rbp+57h+var_A0]
0x18004bbb9  test    rcx, rcx
0x18004bbbc  jz      short loc_18004BBC4
0x18004bbbe  call    cs:__imp_WwanFreeMemory
0x18004bbc4  mov     ebx, edi
0x18004bbc6  jmp     loc_18004BD03
0x18004bbcb  xorps   xmm0, xmm0
0x18004bbce  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x18004bbd3  mov     rcx, [rbx+28h]
0x18004bbd7  test    rcx, rcx
0x18004bbda  jz      short loc_18004BBEC
0x18004bbdc  mov     rax, [rbx+20h]
0x18004bbe0  mov     qword ptr [rbp+57h+var_98], rax
0x18004bbe4  mov     qword ptr [rbp+57h+var_98+8], rcx
0x18004bbe8  lock inc dword ptr [rcx+0Ch]
0x18004bbec  lea     r8, [r14+40Ch]
0x18004bbf3  mov     rdx, rsi
0x18004bbf6  lea     rcx, [rbp+57h+var_98]
0x18004bbfa  call    ?ProcessRadioState@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@PEAEI@Z; CWwanTranslator::ProcessRadioState(std::weak_ptr<CWwanTranslator>,_GUID const &,uchar *,uint)
0x18004bbff  mov     ebx, eax
0x18004bc01  test    eax, eax
0x18004bc03  jns     short loc_18004BC36
0x18004bc05  mov     rcx, [rbp+5Fh]; this
0x18004bc09  mov     r9d, eax; char *
0x18004bc0c  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004bc13  mov     edx, 18Bh; void *
0x18004bc18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bc1d  nop
0x18004bc1e  mov     rcx, [rbp+57h+var_A0]
0x18004bc22  test    rcx, rcx
0x18004bc25  jz      loc_18004BD03
0x18004bc2b  call    cs:__imp_WwanFreeMemory
0x18004bc31  jmp     loc_18004BD03
0x18004bc36  xorps   xmm0, xmm0
0x18004bc39  movdqu  xmmword ptr [rbp+57h+var_38], xmm0
0x18004bc3e  mov     [rbp+57h+var_28], 0
0x18004bc46  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x18004bc4b  mov     [rbp+57h+var_40], 0
0x18004bc53  lea     rcx, [rbp+57h+var_38]
0x18004bc57  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004bc5c  lea     rcx, [rbp+57h+var_50]
0x18004bc60  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004bc65  mov     rdx, [rbp+57h+var_38+8]
0x18004bc69  mov     rcx, [rbp+57h+var_38]; unsigned __int16 *
0x18004bc6d  sub     rdx, rcx
0x18004bc70  sar     rdx, 1; unsigned __int64
0x18004bc73  lea     r8, aExit; "Exit"
0x18004bc7a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004bc7f  mov     rdx, [rbp+57h+var_50+8]
0x18004bc83  mov     rcx, [rbp+57h+var_50]; unsigned __int16 *
0x18004bc87  sub     rdx, rcx
0x18004bc8a  sar     rdx, 1; unsigned __int64
0x18004bc8d  mov     rax, [rbp+57h+var_38]
0x18004bc91  mov     [rsp+0E0h+var_B8], rax
0x18004bc96  mov     [rsp+0E0h+var_C0], 18Dh
0x18004bc9e  lea     r9, aCcellularsetti_13; "CCellularSettingHelperCommon::_GetInter"...
0x18004bca5  lea     r8, aSDS; "%S(%d):%s"
0x18004bcac  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004bcb1  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004bcb6  mov     ecx, [rax]
0x18004bcb8  cmp     ecx, 5
0x18004bcbb  jbe     short loc_18004BCDE
0x18004bcbd  mov     rcx, [rbp+57h+var_50]
0x18004bcc1  mov     qword ptr [rbp+57h+var_98], rcx
0x18004bcc5  lea     rcx, [rbp+57h+var_98]
0x18004bcc9  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x18004bcce  lea     rdx, qword_180078F88
0x18004bcd5  mov     rcx, rax
0x18004bcd8  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004bcdd  nop
0x18004bcde  lea     rcx, [rbp+57h+var_50]
0x18004bce2  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004bce7  nop
0x18004bce8  lea     rcx, [rbp+57h+var_38]
0x18004bcec  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004bcf1  nop
0x18004bcf2  mov     rcx, [rbp+57h+var_A0]
0x18004bcf6  test    rcx, rcx
0x18004bcf9  jz      short loc_18004BD01
0x18004bcfb  call    cs:__imp_WwanFreeMemory
0x18004bd01  xor     ebx, ebx
0x18004bd03  xor     edx, edx
0x18004bd05  mov     rcx, [rbp+57h+var_88]
0x18004bd09  call    cs:__imp_WwanCloseHandle
0x18004bd0f  mov     eax, ebx
0x18004bd11  add     rsp, 0C0h
0x18004bd18  pop     r14
0x18004bd1a  pop     rdi
0x18004bd1b  pop     rsi
0x18004bd1c  pop     rbx
0x18004bd1d  pop     rbp
0x18004bd1e  retn
```
