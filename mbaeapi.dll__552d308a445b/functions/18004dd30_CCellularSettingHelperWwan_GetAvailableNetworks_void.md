# CCellularSettingHelperWwan::GetAvailableNetworks(void)

- ea: `0x18004dd30`
- end: `0x18004dfdd`
- name: `?GetAvailableNetworks@CCellularSettingHelperWwan@@UEAAJXZ`
- size: `685`
- prototype: `__int64 __fastcall(CCellularSettingHelperWwan *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800016ec`
- `0x18000178c`
- `0x1800024e0`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x18004dd30`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004dfb8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004dfb8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004de85`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004de85`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanScan` at `0x18004decb`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanScan` at `0x18004decb`

## pseudocode

```c
int __fastcall CCellularSettingHelperWwan::GetAvailableNetworks(CCellularSettingHelperWwan *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // eax
  unsigned int v7; // eax
  int v8; // ebx
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // [rsp+20h] [rbp-19h]
  unsigned __int16 *v13[2]; // [rsp+30h] [rbp-9h] BYREF
  __int64 v14; // [rsp+40h] [rbp+7h]
  int v15; // [rsp+48h] [rbp+Fh] BYREF
  int v16; // [rsp+4Ch] [rbp+13h] BYREF
  __int64 v17; // [rsp+50h] [rbp+17h] BYREF
  unsigned __int16 *v18; // [rsp+58h] [rbp+1Fh] BYREF
  unsigned __int16 *v19[2]; // [rsp+60h] [rbp+27h] BYREF
  __int64 v20; // [rsp+70h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  v20 = 0;
  v14 = 0;
  *(_OWORD *)v19 = 0;
  *(_OWORD *)v13 = 0;
  std::vector<unsigned short>::resize(v19);
  std::vector<unsigned short>::resize(v13);
  StringCchPrintfW(v19[0], v19[1] - v19[0], L"Enter");
  v12 = 454;
  StringCchPrintfW(v13[0], v13[1] - v13[0], L"%S(%d):%s", "CCellularSettingHelperWwan::GetAvailableNetworks");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    v18 = v13[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)byte_1800794ED,
      v3,
      v4,
      (const unsigned __int16 **)&v18);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v13);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v19);
  if ( (unsigned int)dword_180084238 > 5
    && (qword_180084248 & 0x400000000000LL) != 0
    && (qword_180084250 & 0x400000000000LL) == qword_180084250 )
  {
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)&dword_180084238,
      (unsigned __int8 *)&unk_180079510,
      0,
      0,
      2u,
      (PEVENT_DATA_DESCRIPTOR)v19);
  }
  v17 = 0;
  v15 = 0;
  v5 = WwanOpenHandle(1, 0, &v15, &v17);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1CB,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
             (const char *)v5,
             v12);
  v16 = 0;
  v7 = WwanScan(v17, (char *)this + 8, &v16, 0);
  if ( v7 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1CE,
           (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
           (const char *)v7,
           0);
  }
  else
  {
    v14 = 0;
    v20 = 0;
    *(_OWORD *)v13 = 0;
    *(_OWORD *)v19 = 0;
    std::vector<unsigned short>::resize(v13);
    std::vector<unsigned short>::resize(v19);
    StringCchPrintfW(v13[0], v13[1] - v13[0], L"Exit");
    StringCchPrintfW(
      v19[0],
      v19[1] - v19[0],
      L"%S(%d):%s",
      "CCellularSettingHelperWwan::GetAvailableNetworks",
      464,
      v13[0]);
    v9 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v9 > 5u )
    {
      v18 = v19[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v9,
        (__int64)word_1800794CA,
        v10,
        v11,
        (const unsigned __int16 **)&v18);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v19);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v13);
    v8 = 0;
  }
  WwanCloseHandle(v17, 0);
  return v8;
}

```

## disassembly

```asm
0x18004dd30  mov     [rsp-8+arg_8], rbx
0x18004dd35  push    rbp
0x18004dd36  lea     rbp, [rsp-57h]
0x18004dd3b  sub     rsp, 90h
0x18004dd42  mov     rax, cs:__security_cookie
0x18004dd49  xor     rax, rsp
0x18004dd4c  mov     [rbp+57h+var_10], rax
0x18004dd50  xorps   xmm0, xmm0
0x18004dd53  mov     [rbp+57h+var_20], 0
0x18004dd5b  mov     rbx, rcx
0x18004dd5e  mov     [rbp+57h+var_50], 0
0x18004dd66  lea     rcx, [rbp+57h+var_30]
0x18004dd6a  movdqu  xmmword ptr [rbp+57h+var_30], xmm0
0x18004dd6f  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18004dd74  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004dd79  lea     rcx, [rbp+57h+var_60]
0x18004dd7d  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004dd82  mov     rdx, [rbp+57h+var_30+8]
0x18004dd86  lea     r8, aEnter; "Enter"
0x18004dd8d  mov     rcx, [rbp+57h+var_30]; unsigned __int16 *
0x18004dd91  sub     rdx, rcx
0x18004dd94  sar     rdx, 1; unsigned __int64
0x18004dd97  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004dd9c  mov     rdx, [rbp+57h+var_60+8]
0x18004dda0  lea     r9, aCcellularsetti_24; "CCellularSettingHelperWwan::GetAvailabl"...
0x18004dda7  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18004ddab  lea     r8, aSDS; "%S(%d):%s"
0x18004ddb2  mov     rax, [rbp+57h+var_30]
0x18004ddb6  sub     rdx, rcx
0x18004ddb9  mov     [rsp+90h+var_68], rax
0x18004ddbe  sar     rdx, 1; unsigned __int64
0x18004ddc1  mov     [rsp+90h+var_70], 1C6h
0x18004ddc9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004ddce  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004ddd3  mov     ecx, [rax]
0x18004ddd5  cmp     ecx, 5
0x18004ddd8  jbe     short loc_18004DDFA
0x18004ddda  mov     rcx, [rbp+57h+var_60]
0x18004ddde  lea     rdx, byte_1800794ED
0x18004dde5  mov     [rbp+57h+var_38], rcx
0x18004dde9  lea     rcx, [rbp+57h+var_38]
0x18004dded  mov     qword ptr [rsp+90h+var_70], rcx
0x18004ddf2  mov     rcx, rax
0x18004ddf5  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004ddfa  lea     rcx, [rbp+57h+var_60]
0x18004ddfe  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004de03  lea     rcx, [rbp+57h+var_30]
0x18004de07  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004de0c  mov     eax, cs:dword_180084238
0x18004de12  cmp     eax, 5
0x18004de15  jbe     short loc_18004DE69
0x18004de17  mov     rcx, cs:qword_180084250
0x18004de1e  mov     rdx, 400000000000h
0x18004de28  mov     rax, cs:qword_180084248
0x18004de2f  test    rdx, rax
0x18004de32  jz      short loc_18004DE69
0x18004de34  mov     rax, rcx
0x18004de37  and     rax, rdx
0x18004de3a  cmp     rax, rcx
0x18004de3d  jnz     short loc_18004DE69
0x18004de3f  lea     rax, [rbp+57h+var_30]
0x18004de43  xor     r9d, r9d
0x18004de46  mov     [rsp+90h+var_68], rax
0x18004de4b  lea     rdx, unk_180079510
0x18004de52  xor     r8d, r8d
0x18004de55  mov     [rsp+90h+var_70], 2; unsigned int
0x18004de5d  lea     rcx, dword_180084238
0x18004de64  call    _tlgWriteTransfer_EventWriteTransfer
0x18004de69  xor     edx, edx
0x18004de6b  mov     [rbp+57h+var_40], 0
0x18004de73  lea     r9, [rbp+57h+var_40]
0x18004de77  mov     [rbp+57h+var_48], 0
0x18004de7e  lea     r8, [rbp+57h+var_48]
0x18004de82  lea     ecx, [rdx+1]
0x18004de85  call    cs:__imp_WwanOpenHandle
0x18004de8b  test    eax, eax
0x18004de8d  jz      short loc_18004DEAC
0x18004de8f  mov     rcx, [rbp+5Fh]; this
0x18004de93  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004de9a  mov     r9d, eax; char *
0x18004de9d  mov     edx, 1CBh; void *
0x18004dea2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004dea7  jmp     loc_18004DFC0
0x18004deac  mov     rcx, [rbp+57h+var_40]
0x18004deb0  lea     rdx, [rbx+8]
0x18004deb4  xor     r9d, r9d
0x18004deb7  mov     [rbp+57h+var_44], 0
0x18004debe  lea     r8, [rbp+57h+var_44]
0x18004dec2  mov     qword ptr [rsp+90h+var_70], 0; unsigned int
0x18004decb  call    cs:__imp_WwanScan
0x18004ded1  test    eax, eax
0x18004ded3  jz      short loc_18004DEF4
0x18004ded5  mov     rcx, [rbp+5Fh]; this
0x18004ded9  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004dee0  mov     r9d, eax; char *
0x18004dee3  mov     edx, 1CEh; void *
0x18004dee8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004deed  mov     ebx, eax
0x18004deef  jmp     loc_18004DFB2
0x18004def4  xorps   xmm0, xmm0
0x18004def7  mov     [rbp+57h+var_50], 0
0x18004deff  xorps   xmm1, xmm1
0x18004df02  mov     [rbp+57h+var_20], 0
0x18004df0a  lea     rcx, [rbp+57h+var_60]
0x18004df0e  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18004df13  movdqu  xmmword ptr [rbp+57h+var_30], xmm1
0x18004df18  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004df1d  lea     rcx, [rbp+57h+var_30]
0x18004df21  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004df26  mov     rdx, [rbp+57h+var_60+8]
0x18004df2a  lea     r8, aExit; "Exit"
0x18004df31  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18004df35  sub     rdx, rcx
0x18004df38  sar     rdx, 1; unsigned __int64
0x18004df3b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004df40  mov     rdx, [rbp+57h+var_30+8]
0x18004df44  lea     r9, aCcellularsetti_24; "CCellularSettingHelperWwan::GetAvailabl"...
0x18004df4b  mov     rcx, [rbp+57h+var_30]; unsigned __int16 *
0x18004df4f  lea     r8, aSDS; "%S(%d):%s"
0x18004df56  mov     rax, [rbp+57h+var_60]
0x18004df5a  sub     rdx, rcx
0x18004df5d  mov     [rsp+90h+var_68], rax
0x18004df62  sar     rdx, 1; unsigned __int64
0x18004df65  mov     [rsp+90h+var_70], 1D0h
0x18004df6d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004df72  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004df77  mov     ecx, [rax]
0x18004df79  cmp     ecx, 5
0x18004df7c  jbe     short loc_18004DF9E
0x18004df7e  mov     rcx, [rbp+57h+var_30]
0x18004df82  lea     rdx, word_1800794CA
0x18004df89  mov     [rbp+57h+var_38], rcx
0x18004df8d  lea     rcx, [rbp+57h+var_38]
0x18004df91  mov     qword ptr [rsp+90h+var_70], rcx
0x18004df96  mov     rcx, rax
0x18004df99  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004df9e  lea     rcx, [rbp+57h+var_30]
0x18004dfa2  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004dfa7  lea     rcx, [rbp+57h+var_60]
0x18004dfab  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004dfb0  xor     ebx, ebx
0x18004dfb2  mov     rcx, [rbp+57h+var_40]
0x18004dfb6  xor     edx, edx
0x18004dfb8  call    cs:__imp_WwanCloseHandle
0x18004dfbe  mov     eax, ebx
0x18004dfc0  mov     rcx, [rbp+57h+var_10]
0x18004dfc4  xor     rcx, rsp; StackCookie
0x18004dfc7  call    __security_check_cookie
0x18004dfcc  mov     rbx, [rsp+90h+arg_8]
0x18004dfd4  add     rsp, 90h
0x18004dfdb  pop     rbp
0x18004dfdc  retn
```
