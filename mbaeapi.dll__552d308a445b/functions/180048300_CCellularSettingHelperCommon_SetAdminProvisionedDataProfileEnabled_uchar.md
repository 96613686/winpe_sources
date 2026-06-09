# CCellularSettingHelperCommon::SetAdminProvisionedDataProfileEnabled(uchar)

- ea: `0x180048300`
- end: `0x18004861f`
- name: `?SetAdminProvisionedDataProfileEnabled@CCellularSettingHelperCommon@@UEAAJE@Z`
- size: `799`
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
- `0x180048300`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004860c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004860c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x1800484b8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x1800484b8`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x18004851f`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x18004851f`

## string_xrefs

- `0x1800484c6`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004852d`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x180048360`: `CCellularSettingHelperCommon::SetAdminProvisionedDataProfileEnabled`
- `0x180048430`: `CCellularSettingHelperCommon::SetAdminProvisionedDataProfileEnabled`
- `0x180048598`: `CCellularSettingHelperCommon::SetAdminProvisionedDataProfileEnabled`

## pseudocode

```c
int __fastcall CCellularSettingHelperCommon::SetAdminProvisionedDataProfileEnabled(
        CCellularSettingHelperCommon *this,
        char a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  const wchar_t *v7; // r9
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // eax
  unsigned int v13; // eax
  int v14; // ebx
  const struct _tlgProvider_t *v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned int v18; // [rsp+20h] [rbp-60h]
  unsigned int *v19; // [rsp+20h] [rbp-60h]
  unsigned int v20[2]; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 *v21[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v22; // [rsp+58h] [rbp-28h]
  unsigned __int16 *v23[2]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v24; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  int v26; // [rsp+A8h] [rbp+28h] BYREF
  unsigned int v27; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v28; // [rsp+B8h] [rbp+38h] BYREF

  v24 = 0;
  v22 = 0;
  *(_OWORD *)v23 = 0;
  *(_OWORD *)v21 = 0;
  std::vector<unsigned short>::resize(v23);
  std::vector<unsigned short>::resize(v21);
  StringCchPrintfW(v23[0], v23[1] - v23[0], L"Enter");
  StringCchPrintfW(
    v21[0],
    v21[1] - v21[0],
    L"%S(%d):%s",
    "CCellularSettingHelperCommon::SetAdminProvisionedDataProfileEnabled",
    941,
    v23[0]);
  v4 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v4 > 5u )
  {
    *(unsigned __int16 **)v20 = v21[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)&byte_180078AD7,
      v5,
      v6,
      (const unsigned __int16 **)v20);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v21);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v23);
  v22 = 0;
  v24 = 0;
  *(_OWORD *)v21 = 0;
  *(_OWORD *)v23 = 0;
  std::vector<unsigned short>::resize(v21);
  std::vector<unsigned short>::resize(v23);
  v7 = L"true";
  if ( !a2 )
    v7 = L"false";
  StringCchPrintfW(v21[0], v21[1] - v21[0], L"Set Enabled %s", v7);
  v18 = 942;
  StringCchPrintfW(
    v23[0],
    v23[1] - v23[0],
    L"%S(%d):%s",
    "CCellularSettingHelperCommon::SetAdminProvisionedDataProfileEnabled");
  v8 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v8 > 4u )
  {
    *(unsigned __int16 **)v20 = v23[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v8,
      (__int64)byte_180078A71,
      v9,
      v10,
      (const unsigned __int16 **)v20);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v23);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v21);
  v28 = 0;
  v26 = 0;
  v11 = WwanOpenHandle(1, 0, &v26, &v28);
  if ( v11 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x3B1,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
             (const char *)v11,
             v18);
  v27 = a2 != 0;
  v19 = &v27;
  v13 = WwanSetInterface(v28, (char *)this + 8, 33, 4);
  if ( v13 )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x3B7,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
            (const char *)v13,
            (unsigned int)&v27);
  }
  else
  {
    v22 = 0;
    v24 = 0;
    *(_OWORD *)v21 = 0;
    *(_OWORD *)v23 = 0;
    std::vector<unsigned short>::resize(v21);
    std::vector<unsigned short>::resize(v23);
    StringCchPrintfW(v21[0], v21[1] - v21[0], L"Exit");
    LODWORD(v19) = 953;
    StringCchPrintfW(
      v23[0],
      v23[1] - v23[0],
      L"%S(%d):%s",
      "CCellularSettingHelperCommon::SetAdminProvisionedDataProfileEnabled",
      v19,
      v21[0],
      0,
      0);
    v15 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v15 > 5u )
    {
      *(unsigned __int16 **)v20 = v23[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v15,
        (__int64)byte_180078A91,
        v16,
        v17,
        (const unsigned __int16 **)v20);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v23);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v21);
    v14 = 0;
  }
  WwanCloseHandle(v28, 0);
  return v14;
}

```

## disassembly

```asm
0x180048300  push    rbp
0x180048302  push    rbx
0x180048303  push    rdi
0x180048304  mov     rbp, rsp
0x180048307  sub     rsp, 80h
0x18004830e  xorps   xmm0, xmm0
0x180048311  mov     [rbp+var_10], 0
0x180048319  mov     rdi, rcx
0x18004831c  mov     [rbp+var_28], 0
0x180048324  lea     rcx, [rbp+var_20]
0x180048328  mov     bl, dl
0x18004832a  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18004832f  movdqu  xmmword ptr [rbp+var_38], xmm0
0x180048334  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180048339  lea     rcx, [rbp+var_38]
0x18004833d  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180048342  mov     rdx, [rbp+var_20+8]
0x180048346  lea     r8, aEnter; "Enter"
0x18004834d  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x180048351  sub     rdx, rcx
0x180048354  sar     rdx, 1; unsigned __int64
0x180048357  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004835c  mov     rdx, [rbp+var_38+8]
0x180048360  lea     r9, aCcellularsetti_25; "CCellularSettingHelperCommon::SetAdminP"...
0x180048367  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x18004836b  lea     r8, aSDS; "%S(%d):%s"
0x180048372  mov     rax, [rbp+var_20]
0x180048376  sub     rdx, rcx
0x180048379  mov     [rsp+80h+var_58], rax
0x18004837e  sar     rdx, 1; unsigned __int64
0x180048381  mov     [rsp+80h+var_60], 3ADh
0x180048389  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004838e  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180048393  mov     ecx, [rax]
0x180048395  cmp     ecx, 5
0x180048398  jbe     short loc_1800483BA
0x18004839a  mov     rcx, [rbp+var_38]
0x18004839e  lea     rdx, byte_180078AD7
0x1800483a5  mov     qword ptr [rbp+var_40], rcx
0x1800483a9  lea     rcx, [rbp+var_40]
0x1800483ad  mov     qword ptr [rsp+80h+var_60], rcx
0x1800483b2  mov     rcx, rax
0x1800483b5  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800483ba  lea     rcx, [rbp+var_38]
0x1800483be  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800483c3  lea     rcx, [rbp+var_20]
0x1800483c7  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800483cc  xorps   xmm0, xmm0
0x1800483cf  mov     [rbp+var_28], 0
0x1800483d7  xorps   xmm1, xmm1
0x1800483da  mov     [rbp+var_10], 0
0x1800483e2  lea     rcx, [rbp+var_38]
0x1800483e6  movdqu  xmmword ptr [rbp+var_38], xmm0
0x1800483eb  movdqu  xmmword ptr [rbp+var_20], xmm1
0x1800483f0  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800483f5  lea     rcx, [rbp+var_20]
0x1800483f9  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800483fe  mov     rdx, [rbp+var_38+8]
0x180048402  lea     rax, aFalse; "false"
0x180048409  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x18004840d  lea     r9, aTrue; "true"
0x180048414  test    bl, bl
0x180048416  lea     r8, aSetEnabledS; "Set Enabled %s"
0x18004841d  cmovz   r9, rax
0x180048421  sub     rdx, rcx
0x180048424  sar     rdx, 1; unsigned __int64
0x180048427  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004842c  mov     rdx, [rbp+var_20+8]
0x180048430  lea     r9, aCcellularsetti_25; "CCellularSettingHelperCommon::SetAdminP"...
0x180048437  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x18004843b  lea     r8, aSDS; "%S(%d):%s"
0x180048442  mov     rax, [rbp+var_38]
0x180048446  sub     rdx, rcx
0x180048449  mov     [rsp+80h+var_58], rax
0x18004844e  sar     rdx, 1; unsigned __int64
0x180048451  mov     [rsp+80h+var_60], 3AEh
0x180048459  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004845e  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180048463  mov     ecx, [rax]
0x180048465  cmp     ecx, 4
0x180048468  jbe     short loc_18004848A
0x18004846a  mov     rcx, [rbp+var_20]
0x18004846e  lea     rdx, byte_180078A71
0x180048475  mov     qword ptr [rbp+var_40], rcx
0x180048479  lea     rcx, [rbp+var_40]
0x18004847d  mov     qword ptr [rsp+80h+var_60], rcx; unsigned int
0x180048482  mov     rcx, rax
0x180048485  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004848a  lea     rcx, [rbp+var_20]
0x18004848e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180048493  lea     rcx, [rbp+var_38]
0x180048497  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004849c  xor     edx, edx
0x18004849e  mov     [rbp+arg_18], 0
0x1800484a6  lea     r9, [rbp+arg_18]
0x1800484aa  mov     [rbp+arg_8], 0
0x1800484b1  lea     r8, [rbp+arg_8]
0x1800484b5  lea     ecx, [rdx+1]
0x1800484b8  call    cs:__imp_WwanOpenHandle
0x1800484be  test    eax, eax
0x1800484c0  jz      short loc_1800484DF
0x1800484c2  mov     rcx, [rbp+18h]; this
0x1800484c6  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x1800484cd  mov     r9d, eax; char *
0x1800484d0  mov     edx, 3B1h; void *
0x1800484d5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800484da  jmp     loc_180048614
0x1800484df  mov     rcx, [rbp+arg_18]
0x1800484e3  lea     rdx, [rdi+8]
0x1800484e7  xor     eax, eax
0x1800484e9  mov     [rsp+80h+var_48], 0
0x1800484f2  mov     r9d, 4
0x1800484f8  mov     [rsp+80h+var_50], 0
0x180048501  test    bl, bl
0x180048503  mov     [rsp+80h+var_58], 0
0x18004850c  setnz   al
0x18004850f  mov     [rbp+arg_10], eax
0x180048512  lea     r8d, [r9+1Dh]
0x180048516  lea     rax, [rbp+arg_10]
0x18004851a  mov     qword ptr [rsp+80h+var_60], rax; unsigned int
0x18004851f  call    cs:__imp_WwanSetInterface
0x180048525  test    eax, eax
0x180048527  jz      short loc_180048548
0x180048529  mov     rcx, [rbp+18h]; this
0x18004852d  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180048534  mov     r9d, eax; char *
0x180048537  mov     edx, 3B7h; void *
0x18004853c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180048541  mov     ebx, eax
0x180048543  jmp     loc_180048606
0x180048548  xorps   xmm0, xmm0
0x18004854b  mov     [rbp+var_28], 0
0x180048553  xorps   xmm1, xmm1
0x180048556  mov     [rbp+var_10], 0
0x18004855e  lea     rcx, [rbp+var_38]
0x180048562  movdqu  xmmword ptr [rbp+var_38], xmm0
0x180048567  movdqu  xmmword ptr [rbp+var_20], xmm1
0x18004856c  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180048571  lea     rcx, [rbp+var_20]
0x180048575  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004857a  mov     rdx, [rbp+var_38+8]
0x18004857e  lea     r8, aExit; "Exit"
0x180048585  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x180048589  sub     rdx, rcx
0x18004858c  sar     rdx, 1; unsigned __int64
0x18004858f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048594  mov     rdx, [rbp+var_20+8]
0x180048598  lea     r9, aCcellularsetti_25; "CCellularSettingHelperCommon::SetAdminP"...
0x18004859f  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x1800485a3  lea     r8, aSDS; "%S(%d):%s"
0x1800485aa  mov     rax, [rbp+var_38]
0x1800485ae  sub     rdx, rcx
0x1800485b1  mov     [rsp+80h+var_58], rax
0x1800485b6  sar     rdx, 1; unsigned __int64
0x1800485b9  mov     [rsp+80h+var_60], 3B9h
0x1800485c1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800485c6  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800485cb  mov     ecx, [rax]
0x1800485cd  cmp     ecx, 5
0x1800485d0  jbe     short loc_1800485F2
0x1800485d2  mov     rcx, [rbp+var_20]
0x1800485d6  lea     rdx, byte_180078A91
0x1800485dd  mov     qword ptr [rbp+var_40], rcx
0x1800485e1  lea     rcx, [rbp+var_40]
0x1800485e5  mov     qword ptr [rsp+80h+var_60], rcx
0x1800485ea  mov     rcx, rax
0x1800485ed  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800485f2  lea     rcx, [rbp+var_20]
0x1800485f6  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800485fb  lea     rcx, [rbp+var_38]
0x1800485ff  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180048604  xor     ebx, ebx
0x180048606  mov     rcx, [rbp+arg_18]
0x18004860a  xor     edx, edx
0x18004860c  call    cs:__imp_WwanCloseHandle
0x180048612  mov     eax, ebx
0x180048614  add     rsp, 80h
0x18004861b  pop     rdi
0x18004861c  pop     rbx
0x18004861d  pop     rbp
0x18004861e  retn
```
