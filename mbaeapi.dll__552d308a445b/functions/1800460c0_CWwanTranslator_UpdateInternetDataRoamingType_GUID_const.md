# CWwanTranslator::_UpdateInternetDataRoamingType(_GUID const &)

- ea: `0x1800460c0`
- end: `0x180046394`
- name: `?_UpdateInternetDataRoamingType@CWwanTranslator@@AEAAJAEBU_GUID@@@Z`
- size: `724`
- prototype: `int __fastcall(CWwanTranslator *this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x18003b7d8`

## callees

- `0x18000178c`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x1800431f0`
- `0x1800460c0`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180046377`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180046377`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180046299`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180046369`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180046299`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180046369`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x1800461b4`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x1800461b4`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180046234`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180046234`

## string_xrefs

- `0x180046145`: `CWwanTranslator::_UpdateInternetDataRoamingType`
- `0x18004630c`: `CWwanTranslator::_UpdateInternetDataRoamingType`

## pseudocode

```c
int __fastcall CWwanTranslator::_UpdateInternetDataRoamingType(CWwanTranslator *this, const struct _GUID *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // eax
  unsigned int Interface; // eax
  int v10; // ebx
  int v11; // eax
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned int v15; // [rsp+20h] [rbp-39h]
  unsigned int *v16; // [rsp+20h] [rbp-39h]
  unsigned __int8 *v17; // [rsp+40h] [rbp-19h] BYREF
  __int64 v18; // [rsp+48h] [rbp-11h] BYREF
  unsigned __int16 *v19[2]; // [rsp+50h] [rbp-9h] BYREF
  __int64 v20; // [rsp+60h] [rbp+7h]
  unsigned int v21[2]; // [rsp+68h] [rbp+Fh] BYREF
  char v22; // [rsp+70h] [rbp+17h]
  unsigned __int16 *v23[2]; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v24; // [rsp+88h] [rbp+2Fh]
  unsigned __int16 *v25[2]; // [rsp+90h] [rbp+37h] BYREF
  __int64 v26; // [rsp+A0h] [rbp+47h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  unsigned int v28; // [rsp+D0h] [rbp+77h] BYREF
  int v29; // [rsp+D8h] [rbp+7Fh] BYREF

  *(_OWORD *)v19 = 0;
  v20 = 0;
  *(_OWORD *)v23 = 0;
  v24 = 0;
  std::vector<unsigned short>::resize(v19);
  std::vector<unsigned short>::resize(v23);
  StringCchPrintfW(v19[0], v19[1] - v19[0], L"Enter");
  v15 = 2516;
  StringCchPrintfW(v23[0], v23[1] - v23[0], L"%S(%d):%s", "CWwanTranslator::_UpdateInternetDataRoamingType");
  v4 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v4 > 5u )
  {
    *(unsigned __int16 **)v21 = v23[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)byte_1800769A3,
      v5,
      v6,
      (const unsigned __int16 **)v21);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v23);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v19);
  v18 = 0;
  v29 = 0;
  v7 = WwanOpenHandle(1, 0, &v29, &v18);
  if ( v7 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x9D6,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
             (const char *)v7,
             v15);
  *(_QWORD *)v21 = &v18;
  v22 = 1;
  v28 = 0;
  v17 = 0;
  v23[0] = (unsigned __int16 *)&v17;
  LOBYTE(v23[1]) = 1;
  v16 = &v28;
  Interface = WwanQueryInterface(v18, a2, 16);
  if ( Interface )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x9E2,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
            (const char *)Interface,
            (unsigned int)&v28);
  }
  else
  {
    v11 = CWwanTranslator::_ProcessRoamingPolicyChange(this, a2, v17, v28);
    v10 = v11;
    if ( v11 >= 0 )
    {
      *(_OWORD *)v25 = 0;
      v26 = 0;
      *(_OWORD *)v19 = 0;
      v20 = 0;
      std::vector<unsigned short>::resize(v25);
      std::vector<unsigned short>::resize(v19);
      StringCchPrintfW(v25[0], v25[1] - v25[0], L"Exit");
      LODWORD(v16) = 2534;
      StringCchPrintfW(
        v19[0],
        v19[1] - v19[0],
        L"%S(%d):%s",
        "CWwanTranslator::_UpdateInternetDataRoamingType",
        v16,
        v25[0],
        0,
        0);
      v12 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v12 > 5u )
      {
        *(unsigned __int16 **)v21 = v19[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v12,
          (__int64)qword_180076980,
          v13,
          v14,
          (const unsigned __int16 **)v21);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v19);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v25);
      if ( v17 )
        WwanFreeMemory(v17);
      v10 = 0;
      goto LABEL_16;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E4,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
      (const char *)(unsigned int)v11,
      (int)&v28);
  }
  if ( v17 )
    WwanFreeMemory(v17);
LABEL_16:
  WwanCloseHandle(v18, 0);
  return v10;
}

```

## disassembly

```asm
0x1800460c0  mov     [rsp-8+arg_0], rbx
0x1800460c5  mov     [rsp-8+arg_8], rdi
0x1800460ca  push    rbp
0x1800460cb  lea     rbp, [rsp-57h]
0x1800460d0  sub     rsp, 0B0h
0x1800460d7  mov     rbx, rdx
0x1800460da  mov     rdi, rcx
0x1800460dd  xorps   xmm0, xmm0
0x1800460e0  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x1800460e5  mov     [rbp+57h+var_50], 0
0x1800460ed  movdqu  xmmword ptr [rbp+57h+var_38], xmm0
0x1800460f2  mov     [rbp+57h+var_28], 0
0x1800460fa  lea     rcx, [rbp+57h+var_60]
0x1800460fe  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180046103  lea     rcx, [rbp+57h+var_38]
0x180046107  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004610c  mov     rdx, [rbp+57h+var_60+8]
0x180046110  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x180046114  sub     rdx, rcx
0x180046117  sar     rdx, 1; unsigned __int64
0x18004611a  lea     r8, aEnter; "Enter"
0x180046121  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046126  mov     rdx, [rbp+57h+var_38+8]
0x18004612a  mov     rcx, [rbp+57h+var_38]; unsigned __int16 *
0x18004612e  sub     rdx, rcx
0x180046131  sar     rdx, 1; unsigned __int64
0x180046134  mov     rax, [rbp+57h+var_60]
0x180046138  mov     [rsp+0B0h+var_88], rax
0x18004613d  mov     [rsp+0B0h+var_90], 9D4h
0x180046145  lea     r9, aCwwantranslato_49; "CWwanTranslator::_UpdateInternetDataRoa"...
0x18004614c  lea     r8, aSDS; "%S(%d):%s"
0x180046153  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046158  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004615d  mov     ecx, [rax]
0x18004615f  cmp     ecx, 5
0x180046162  jbe     short loc_180046185
0x180046164  mov     rcx, [rbp+57h+var_38]
0x180046168  mov     qword ptr [rbp+57h+var_48], rcx
0x18004616c  lea     rcx, [rbp+57h+var_48]
0x180046170  mov     qword ptr [rsp+0B0h+var_90], rcx; unsigned int
0x180046175  lea     rdx, byte_1800769A3
0x18004617c  mov     rcx, rax
0x18004617f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180046184  nop
0x180046185  lea     rcx, [rbp+57h+var_38]
0x180046189  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004618e  nop
0x18004618f  lea     rcx, [rbp+57h+var_60]
0x180046193  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180046198  mov     [rbp+57h+var_68], 0
0x1800461a0  mov     [rbp+57h+arg_18], 0
0x1800461a7  lea     r9, [rbp+57h+var_68]
0x1800461ab  lea     r8, [rbp+57h+arg_18]
0x1800461af  xor     edx, edx
0x1800461b1  lea     ecx, [rdx+1]
0x1800461b4  call    cs:__imp_WwanOpenHandle
0x1800461ba  test    eax, eax
0x1800461bc  jz      short loc_1800461DB
0x1800461be  mov     rcx, [rbp+5Fh]; this
0x1800461c2  mov     r9d, eax; char *
0x1800461c5  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x1800461cc  mov     edx, 9D6h; void *
0x1800461d1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800461d6  jmp     loc_18004637F
0x1800461db  lea     rax, [rbp+57h+var_68]
0x1800461df  mov     qword ptr [rbp+57h+var_48], rax
0x1800461e3  mov     [rbp+57h+var_40], 1
0x1800461e7  mov     [rbp+57h+arg_10], 0
0x1800461ee  mov     [rbp+57h+var_70], 0
0x1800461f6  lea     rax, [rbp+57h+var_70]
0x1800461fa  mov     [rbp+57h+var_38], rax
0x1800461fe  mov     byte ptr [rbp+57h+var_38+8], 1
0x180046202  mov     [rsp+0B0h+var_78], 0
0x18004620b  mov     [rsp+0B0h+var_80], 0
0x180046214  lea     rax, [rbp+57h+var_70]
0x180046218  mov     [rsp+0B0h+var_88], rax
0x18004621d  lea     rax, [rbp+57h+arg_10]
0x180046221  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x180046226  xor     r9d, r9d
0x180046229  lea     r8d, [r9+10h]
0x18004622d  mov     rdx, rbx
0x180046230  mov     rcx, [rbp+57h+var_68]
0x180046234  call    cs:__imp_WwanQueryInterface
0x18004623a  test    eax, eax
0x18004623c  jz      short loc_18004625A
0x18004623e  mov     rcx, [rbp+5Fh]; this
0x180046242  mov     r9d, eax; char *
0x180046245  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004624c  mov     edx, 9E2h; void *
0x180046251  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180046256  mov     ebx, eax
0x180046258  jmp     short loc_18004628C
0x18004625a  mov     r9d, [rbp+57h+arg_10]; unsigned int
0x18004625e  mov     r8, [rbp+57h+var_70]; unsigned __int8 *
0x180046262  mov     rdx, rbx; struct _GUID *
0x180046265  mov     rcx, rdi; this
0x180046268  call    ?_ProcessRoamingPolicyChange@CWwanTranslator@@AEAAJAEBU_GUID@@PEAEI@Z; CWwanTranslator::_ProcessRoamingPolicyChange(_GUID const &,uchar *,uint)
0x18004626d  mov     ebx, eax
0x18004626f  test    eax, eax
0x180046271  jns     short loc_1800462A4
0x180046273  mov     rcx, [rbp+5Fh]; this
0x180046277  mov     r9d, eax; char *
0x18004627a  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180046281  mov     edx, 9E4h; void *
0x180046286  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004628b  nop
0x18004628c  mov     rcx, [rbp+57h+var_70]
0x180046290  test    rcx, rcx
0x180046293  jz      loc_180046371
0x180046299  call    cs:__imp_WwanFreeMemory
0x18004629f  jmp     loc_180046371
0x1800462a4  xorps   xmm0, xmm0
0x1800462a7  movdqu  xmmword ptr [rbp+57h+var_20], xmm0
0x1800462ac  mov     [rbp+57h+var_10], 0
0x1800462b4  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x1800462b9  mov     [rbp+57h+var_50], 0
0x1800462c1  lea     rcx, [rbp+57h+var_20]
0x1800462c5  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800462ca  lea     rcx, [rbp+57h+var_60]
0x1800462ce  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800462d3  mov     rdx, [rbp+57h+var_20+8]
0x1800462d7  mov     rcx, [rbp+57h+var_20]; unsigned __int16 *
0x1800462db  sub     rdx, rcx
0x1800462de  sar     rdx, 1; unsigned __int64
0x1800462e1  lea     r8, aExit; "Exit"
0x1800462e8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800462ed  mov     rdx, [rbp+57h+var_60+8]
0x1800462f1  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x1800462f5  sub     rdx, rcx
0x1800462f8  sar     rdx, 1; unsigned __int64
0x1800462fb  mov     rax, [rbp+57h+var_20]
0x1800462ff  mov     [rsp+0B0h+var_88], rax
0x180046304  mov     [rsp+0B0h+var_90], 9E6h
0x18004630c  lea     r9, aCwwantranslato_49; "CWwanTranslator::_UpdateInternetDataRoa"...
0x180046313  lea     r8, aSDS; "%S(%d):%s"
0x18004631a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004631f  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180046324  mov     ecx, [rax]
0x180046326  cmp     ecx, 5
0x180046329  jbe     short loc_18004634C
0x18004632b  mov     rcx, [rbp+57h+var_60]
0x18004632f  mov     qword ptr [rbp+57h+var_48], rcx
0x180046333  lea     rcx, [rbp+57h+var_48]
0x180046337  mov     qword ptr [rsp+0B0h+var_90], rcx
0x18004633c  lea     rdx, qword_180076980
0x180046343  mov     rcx, rax
0x180046346  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004634b  nop
0x18004634c  lea     rcx, [rbp+57h+var_60]
0x180046350  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180046355  nop
0x180046356  lea     rcx, [rbp+57h+var_20]
0x18004635a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004635f  nop
0x180046360  mov     rcx, [rbp+57h+var_70]
0x180046364  test    rcx, rcx
0x180046367  jz      short loc_18004636F
0x180046369  call    cs:__imp_WwanFreeMemory
0x18004636f  xor     ebx, ebx
0x180046371  xor     edx, edx
0x180046373  mov     rcx, [rbp+57h+var_68]
0x180046377  call    cs:__imp_WwanCloseHandle
0x18004637d  mov     eax, ebx
0x18004637f  lea     r11, [rsp+0B0h+var_s0]
0x180046387  mov     rbx, [r11+10h]
0x18004638b  mov     rdi, [r11+18h]
0x18004638f  mov     rsp, r11
0x180046392  pop     rbp
0x180046393  retn
```
