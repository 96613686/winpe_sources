# CESimSettingServer::UpdateESimProfileCache(__MIDL_imports_0034 *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x180026e74`
- end: `0x1800273e1`
- name: `?UpdateESimProfileCache@CESimSettingServer@@AEAAXPEAU__MIDL_imports_0034@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `1389`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180023770`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x1800028b0`
- `0x180009ffc`
- `0x18001105c`
- `0x1800171b8`
- `0x1800172bc`
- `0x18001dd10`
- `0x18001e0d0`
- `0x18001ee30`
- `0x180020994`
- `0x180020b40`
- `0x18002163c`
- `0x180026e74`
- `0x180028910`
- `0x18005c010`

## string_xrefs

- `0x180026f11`: `CESimSettingServer::UpdateESimProfileCache`
- `0x1800271e3`: `CESimSettingServer::UpdateESimProfileCache`
- `0x1800272c5`: `CESimSettingServer::UpdateESimProfileCache`
- `0x180026fc0`: `UpdateESimProfileCache for profile {%ls}, at eSim {%ls}, with state %d`
- `0x18002729a`: `The eSim profile does not exist in cache. profileId = %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CESimSettingServer::UpdateESimProfileCache(
        __int64 a1,
        unsigned int *a2,
        const unsigned __int16 *a3,
        char a4)
{
  const unsigned __int16 *v4; // r15
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // eax
  char *v11; // r12
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // r14
  void **v16; // r9
  void **i; // rbx
  char *v18; // rdi
  unsigned __int16 *v19; // rax
  int v20; // ecx
  int v21; // edx
  unsigned __int64 v22; // rsi
  char **v23; // r15
  __int64 AdapterSlotPair; // rax
  const struct _tlgProvider_t *v25; // rax
  __int64 v26; // r8
  __int64 v27; // r9
  const struct _tlgProvider_t *v28; // rax
  __int64 v29; // r8
  __int64 v30; // r9
  const struct _tlgProvider_t *v31; // rax
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // [rsp+20h] [rbp-49h]
  __int64 v35; // [rsp+20h] [rbp-49h]
  __int64 v36; // [rsp+20h] [rbp-49h]
  __int64 v37; // [rsp+28h] [rbp-41h]
  unsigned __int16 *v39[2]; // [rsp+38h] [rbp-31h] BYREF
  __int64 v40; // [rsp+48h] [rbp-21h]
  unsigned __int16 *v41; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int16 *v42; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int16 *v43[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v44; // [rsp+70h] [rbp+7h]
  __int64 v45; // [rsp+78h] [rbp+Fh]

  v4 = a3;
  v41 = (unsigned __int16 *)a3;
  *(_OWORD *)v43 = 0;
  v44 = 0;
  *(_OWORD *)v39 = 0;
  v40 = 0;
  std::vector<unsigned short>::resize(v43);
  std::vector<unsigned short>::resize(v39);
  StringCchPrintfW(v43[0], v43[1] - v43[0], L"Enter");
  StringCchPrintfW(v39[0], v39[1] - v39[0], L"%S(%d):%s", "CESimSettingServer::UpdateESimProfileCache", 878, v43[0]);
  v7 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v7 > 5u )
  {
    v42 = v39[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v7,
      (__int64)&word_18007582E,
      v8,
      v9,
      (const unsigned __int16 **)&v42);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v39);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v43);
  v10 = *a2 & 7;
  v40 = 0;
  *(_OWORD *)v39 = 0;
  if ( (_BYTE)v10 == 7 )
  {
    *(_OWORD *)v43 = 0;
    v44 = 0;
    std::vector<unsigned short>::resize(v39);
    std::vector<unsigned short>::resize(v43);
    v11 = (char *)(a2 + 1);
    LODWORD(v37) = a2[12];
    StringCchPrintfW(
      v39[0],
      v39[1] - v39[0],
      L"UpdateESimProfileCache for profile {%ls}, at eSim {%ls}, with state %d",
      a2 + 1,
      a2 + 13,
      v37);
    LODWORD(v35) = 890;
    StringCchPrintfW(v43[0], v43[1] - v43[0], L"%S(%d):%s", "CESimSettingServer::UpdateESimProfileCache", v35, v39[0]);
    v12 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v12 > 4u )
    {
      v42 = v43[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v12,
        (__int64)&word_1800757EE,
        v13,
        v14,
        (const unsigned __int16 **)&v42);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v43);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v39);
    v15 = *(_QWORD *)(CESimSettingServer::GetAdapterSlotData(a1, v4) + 16);
    if ( v15 )
    {
      v16 = *(void ***)(v15 + 568);
      for ( i = (void **)*v16; ; i = (void **)*i )
      {
        if ( i == v16 )
          goto LABEL_29;
        v18 = (char *)i[2];
        v19 = (unsigned __int16 *)v18;
        do
        {
          v20 = *(unsigned __int16 *)((char *)v19 + v11 - v18);
          v21 = *v19 - v20;
          if ( v21 )
            break;
          ++v19;
        }
        while ( v20 );
        if ( !v21 )
          break;
      }
      if ( !v18 )
        goto LABEL_29;
      if ( a2[12] == 2 )
      {
        *(_QWORD *)i[1] = *i;
        *((_QWORD *)*i + 1) = i[1];
        v22 = -1;
        --*(_QWORD *)(v15 + 576);
        v23 = (char **)i[2];
        if ( v23 )
        {
          std::vector<unsigned char>::~vector<unsigned char>(v23 + 113);
          operator delete(v23);
        }
        operator delete(i);
        *(_OWORD *)v43 = 0;
        v44 = 0;
        v45 = 0;
        do
          ++v22;
        while ( *(_WORD *)&v11[2 * v22] );
        std::wstring::_Construct<1,unsigned short const *>((char **)v43, v11, v22);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(
          v15 + 584,
          v43);
        std::wstring::~wstring((char **)v43);
        LODWORD(v4) = (_DWORD)v41;
        AdapterSlotPair = CESimSettingServer::GetAdapterSlotPair(a1, v41);
        (*(void (__fastcall **)(__int64, __int64, _QWORD, char *))(*(_QWORD *)(a1 + 8) + 72LL))(
          a1 + 8,
          AdapterSlotPair,
          *(unsigned int *)(AdapterSlotPair + 16),
          v11);
      }
      else if ( (*(_BYTE *)a2 & 2) != 0 && v18[42] != (a2[12] == 1) )
      {
        v18[42] = a2[12] == 1;
LABEL_22:
        LOBYTE(v16) = 1;
        CESimSettingServer::NotifyESimProfile(a1, (_DWORD)v4, (_DWORD)v18, (_DWORD)v16, 0);
LABEL_23:
        *(_OWORD *)v39 = 0;
        v40 = 0;
        *(_OWORD *)v43 = 0;
        v44 = 0;
        std::vector<unsigned short>::resize(v39);
        std::vector<unsigned short>::resize(v43);
        StringCchPrintfW(v39[0], v39[1] - v39[0], L"Exit");
        LODWORD(v36) = 939;
        StringCchPrintfW(
          v43[0],
          v43[1] - v43[0],
          L"%S(%d):%s",
          "CESimSettingServer::UpdateESimProfileCache",
          v36,
          v39[0]);
        v25 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v25 > 5u )
        {
          v41 = v43[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v25,
            (__int64)word_1800757AA,
            v26,
            v27,
            (const unsigned __int16 **)&v41);
        }
        goto LABEL_34;
      }
      if ( !a4 )
        goto LABEL_23;
      goto LABEL_22;
    }
LABEL_29:
    *(_OWORD *)v39 = 0;
    v40 = 0;
    *(_OWORD *)v43 = 0;
    v44 = 0;
    std::vector<unsigned short>::resize(v39);
    std::vector<unsigned short>::resize(v43);
    StringCchPrintfW(v39[0], v39[1] - v39[0], L"The eSim profile does not exist in cache. profileId = %ls", a2 + 1);
    LODWORD(v36) = 912;
    StringCchPrintfW(v43[0], v43[1] - v43[0], L"%S(%d):%s", "CESimSettingServer::UpdateESimProfileCache", v36, v39[0]);
    v28 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v28 > 2u )
    {
      v41 = v43[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v28,
        (__int64)byte_1800757CD,
        v29,
        v30,
        (const unsigned __int16 **)&v41);
    }
  }
  else
  {
    *(_OWORD *)v43 = 0;
    v44 = 0;
    std::vector<unsigned short>::resize(v39);
    std::vector<unsigned short>::resize(v43);
    StringCchPrintfW(v39[0], v39[1] - v39[0], L"Profile has incorrect dwParams {%d}", *a2);
    LODWORD(v34) = 882;
    StringCchPrintfW(v43[0], v43[1] - v43[0], L"%S(%d):%s", "CESimSettingServer::UpdateESimProfileCache", v34, v39[0]);
    v31 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v31 > 4u )
    {
      v41 = v43[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v31,
        (__int64)&word_18007580E,
        v32,
        v33,
        (const unsigned __int16 **)&v41);
    }
  }
LABEL_34:
  std::vector<unsigned short>::~vector<unsigned short>((char **)v43);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v39);
}

```

## disassembly

```asm
0x180026e74  mov     [rsp-8+arg_18], rbx
0x180026e79  push    rbp
0x180026e7a  push    rsi
0x180026e7b  push    rdi
0x180026e7c  push    r12
0x180026e7e  push    r13
0x180026e80  push    r14
0x180026e82  push    r15
0x180026e84  lea     rbp, [rsp-27h]
0x180026e89  sub     rsp, 90h
0x180026e90  mov     rax, cs:__security_cookie
0x180026e97  xor     rax, rsp
0x180026e9a  mov     [rbp+57h+var_40], rax
0x180026e9e  mov     [rbp+57h+var_90], r9b
0x180026ea2  mov     r15, r8
0x180026ea5  mov     [rbp+57h+var_70], r8
0x180026ea9  mov     rsi, rdx
0x180026eac  mov     r13, rcx
0x180026eaf  xorps   xmm0, xmm0
0x180026eb2  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x180026eb7  xor     edi, edi
0x180026eb9  mov     [rbp+57h+var_50], rdi
0x180026ebd  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x180026ec2  mov     [rbp+57h+var_78], rdi
0x180026ec6  lea     rcx, [rbp+57h+var_60]
0x180026eca  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180026ecf  lea     rcx, [rbp+57h+var_88]
0x180026ed3  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180026ed8  mov     rdx, [rbp+57h+var_60+8]
0x180026edc  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x180026ee0  sub     rdx, rcx
0x180026ee3  sar     rdx, 1; unsigned __int64
0x180026ee6  lea     r8, aEnter; "Enter"
0x180026eed  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026ef2  mov     rdx, [rbp+57h+var_88+8]
0x180026ef6  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x180026efa  sub     rdx, rcx
0x180026efd  sar     rdx, 1; unsigned __int64
0x180026f00  mov     rax, [rbp+57h+var_60]
0x180026f04  mov     [rsp+0C0h+var_98], rax
0x180026f09  mov     dword ptr [rsp+0C0h+var_A0], 36Eh
0x180026f11  lea     r14, aCesimsettingse_29; "CESimSettingServer::UpdateESimProfileCa"...
0x180026f18  mov     r9, r14
0x180026f1b  lea     r8, aSDS; "%S(%d):%s"
0x180026f22  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026f27  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180026f2c  mov     ecx, [rax]
0x180026f2e  cmp     ecx, 5
0x180026f31  jbe     short loc_180026F54
0x180026f33  mov     rcx, [rbp+57h+var_88]
0x180026f37  mov     [rbp+57h+var_68], rcx
0x180026f3b  lea     rcx, [rbp+57h+var_68]
0x180026f3f  mov     [rsp+0C0h+var_A0], rcx
0x180026f44  lea     rdx, word_18007582E
0x180026f4b  mov     rcx, rax
0x180026f4e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180026f53  nop
0x180026f54  lea     rcx, [rbp+57h+var_88]
0x180026f58  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180026f5d  nop
0x180026f5e  lea     rcx, [rbp+57h+var_60]
0x180026f62  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180026f67  mov     eax, [rsi]
0x180026f69  and     eax, 7
0x180026f6c  xorps   xmm0, xmm0
0x180026f6f  mov     [rbp+57h+var_78], rdi
0x180026f73  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x180026f78  cmp     al, 7
0x180026f7a  jnz     loc_180027314
0x180026f80  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x180026f85  mov     [rbp+57h+var_50], rdi
0x180026f89  lea     rcx, [rbp+57h+var_88]
0x180026f8d  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180026f92  lea     rcx, [rbp+57h+var_60]
0x180026f96  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180026f9b  lea     r12, [rsi+4]
0x180026f9f  lea     r8, [rsi+34h]
0x180026fa3  mov     rdx, [rbp+57h+var_88+8]
0x180026fa7  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x180026fab  sub     rdx, rcx
0x180026fae  sar     rdx, 1; unsigned __int64
0x180026fb1  mov     eax, [rsi+30h]
0x180026fb4  mov     dword ptr [rsp+0C0h+var_98], eax
0x180026fb8  mov     [rsp+0C0h+var_A0], r8
0x180026fbd  mov     r9, r12
0x180026fc0  lea     r8, aUpdateesimprof; "UpdateESimProfileCache for profile {%ls"...
0x180026fc7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026fcc  mov     rdx, [rbp+57h+var_60+8]
0x180026fd0  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x180026fd4  sub     rdx, rcx
0x180026fd7  sar     rdx, 1; unsigned __int64
0x180026fda  mov     rax, [rbp+57h+var_88]
0x180026fde  mov     [rsp+0C0h+var_98], rax
0x180026fe3  mov     dword ptr [rsp+0C0h+var_A0], 37Ah
0x180026feb  mov     r9, r14
0x180026fee  lea     r8, aSDS; "%S(%d):%s"
0x180026ff5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026ffa  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180026fff  mov     ecx, [rax]
0x180027001  cmp     ecx, 4
0x180027004  jbe     short loc_180027027
0x180027006  mov     rcx, [rbp+57h+var_60]
0x18002700a  mov     [rbp+57h+var_68], rcx
0x18002700e  lea     rcx, [rbp+57h+var_68]
0x180027012  mov     [rsp+0C0h+var_A0], rcx
0x180027017  lea     rdx, word_1800757EE
0x18002701e  mov     rcx, rax
0x180027021  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180027026  nop
0x180027027  lea     rcx, [rbp+57h+var_60]
0x18002702b  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180027030  nop
0x180027031  lea     rcx, [rbp+57h+var_88]
0x180027035  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002703a  mov     rdx, r15
0x18002703d  mov     rcx, r13
0x180027040  call    ?GetAdapterSlotData@CESimSettingServer@@AEAAPEAUAdapterSlotData@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CESimSettingServer::GetAdapterSlotData(std::wstring const &)
0x180027045  mov     r14, [rax+10h]
0x180027049  test    r14, r14
0x18002704c  jz      loc_180027262
0x180027052  mov     r9, [r14+238h]
0x180027059  mov     rbx, [r9]
0x18002705c  cmp     rbx, r9
0x18002705f  jz      loc_180027260
0x180027065  mov     rdi, [rbx+10h]
0x180027069  mov     rax, rdi
0x18002706c  mov     r8, r12
0x18002706f  sub     r8, rdi
0x180027072  movzx   edx, word ptr [rax]
0x180027075  movzx   ecx, word ptr [rax+r8]
0x18002707a  sub     edx, ecx
0x18002707c  jnz     short loc_180027086
0x18002707e  add     rax, 2
0x180027082  test    ecx, ecx
0x180027084  jnz     short loc_180027072
0x180027086  xor     r8d, r8d
0x180027089  test    edx, edx
0x18002708b  jz      short loc_180027092
0x18002708d  mov     rbx, [rbx]
0x180027090  jmp     short loc_18002705C
0x180027092  test    rdi, rdi
0x180027095  jz      loc_180027260
0x18002709b  cmp     dword ptr [rsi+30h], 2
0x18002709f  jnz     loc_180027232
0x1800270a5  mov     rcx, [rbx+8]
0x1800270a9  mov     rax, [rbx]
0x1800270ac  mov     [rcx], rax
0x1800270af  mov     rcx, [rbx]
0x1800270b2  mov     rax, [rbx+8]
0x1800270b6  mov     [rcx+8], rax
0x1800270ba  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800270be  add     [r14+240h], rsi
0x1800270c5  mov     r15, [rbx+10h]
0x1800270c9  test    r15, r15
0x1800270cc  jz      short loc_1800270E7
0x1800270ce  lea     rcx, [r15+388h]
0x1800270d5  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1800270da  mov     edx, 3A0h
0x1800270df  mov     rcx, r15; Block
0x1800270e2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800270e7  mov     edx, 18h
0x1800270ec  mov     rcx, rbx; Block
0x1800270ef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800270f4  xorps   xmm0, xmm0
0x1800270f7  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1800270fb  xor     eax, eax
0x1800270fd  mov     [rbp+57h+var_50], rax
0x180027101  mov     [rbp+57h+var_48], rax
0x180027105  inc     rsi
0x180027108  cmp     [r12+rsi*2], ax
0x18002710d  jnz     short loc_180027105
0x18002710f  mov     r8, rsi
0x180027112  mov     rdx, r12
0x180027115  lea     rcx, [rbp+57h+var_60]
0x180027119  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002711e  lea     rdx, [rbp+57h+var_60]
0x180027122  lea     rcx, [r14+248h]
0x180027129  call    ?erase@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(std::wstring const &)
0x18002712e  lea     rcx, [rbp+57h+var_60]
0x180027132  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027137  mov     r15, [rbp+57h+var_70]
0x18002713b  mov     rdx, r15
0x18002713e  mov     rcx, r13
0x180027141  call    ?GetAdapterSlotPair@CESimSettingServer@@AEAAPEBU?$pair@U_GUID@@W4SimSlot@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; CESimSettingServer::GetAdapterSlotPair(std::wstring const &)
0x180027146  mov     rdx, rax
0x180027149  mov     rcx, [r13+8]
0x18002714d  mov     rax, [rcx+48h]
0x180027151  mov     r9, r12
0x180027154  mov     r8d, [rdx+10h]
0x180027158  lea     rcx, [r13+8]
0x18002715c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027161  xor     r8d, r8d
0x180027164  cmp     [rbp+57h+var_90], r8b
0x180027168  jz      short loc_180027183
0x18002716a  mov     [rsp+0C0h+var_A0], r8
0x18002716f  mov     r9b, 1
0x180027172  mov     r8, rdi
0x180027175  mov     rdx, r15
0x180027178  mov     rcx, r13
0x18002717b  call    ?NotifyESimProfile@CESimSettingServer@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUESimProfileData@@_NPEAU__MIDL_imports_0043@@@Z; CESimSettingServer::NotifyESimProfile(std::wstring const &,ESimProfileData *,bool,__MIDL_imports_0043 *)
0x180027180  xor     r8d, r8d
0x180027183  xorps   xmm0, xmm0
0x180027186  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18002718b  mov     [rbp+57h+var_78], r8
0x18002718f  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x180027194  mov     [rbp+57h+var_50], r8
0x180027198  lea     rcx, [rbp+57h+var_88]
0x18002719c  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800271a1  lea     rcx, [rbp+57h+var_60]
0x1800271a5  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800271aa  mov     rdx, [rbp+57h+var_88+8]
0x1800271ae  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x1800271b2  sub     rdx, rcx
0x1800271b5  sar     rdx, 1; unsigned __int64
0x1800271b8  lea     r8, aExit; "Exit"
0x1800271bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800271c4  mov     rdx, [rbp+57h+var_60+8]
0x1800271c8  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x1800271cc  sub     rdx, rcx
0x1800271cf  sar     rdx, 1; unsigned __int64
0x1800271d2  mov     rax, [rbp+57h+var_88]
0x1800271d6  mov     [rsp+0C0h+var_98], rax
0x1800271db  mov     dword ptr [rsp+0C0h+var_A0], 3ABh
0x1800271e3  lea     r9, aCesimsettingse_29; "CESimSettingServer::UpdateESimProfileCa"...
0x1800271ea  lea     r8, aSDS; "%S(%d):%s"
0x1800271f1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800271f6  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800271fb  mov     ecx, [rax]
0x1800271fd  cmp     ecx, 5
0x180027200  jbe     short loc_180027223
0x180027202  mov     rcx, [rbp+57h+var_60]
0x180027206  mov     [rbp+57h+var_70], rcx
0x18002720a  lea     rcx, [rbp+57h+var_70]
0x18002720e  mov     [rsp+0C0h+var_A0], rcx
0x180027213  lea     rdx, word_1800757AA
0x18002721a  mov     rcx, rax
0x18002721d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180027222  nop
0x180027223  lea     rcx, [rbp+57h+var_60]
0x180027227  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002722c  nop
0x18002722d  jmp     loc_1800273B1
0x180027232  test    byte ptr [rsi], 2
0x180027235  jz      loc_180027164
0x18002723b  mov     ecx, r8d
0x18002723e  cmp     dword ptr [rsi+30h], 1
0x180027242  setz    cl
0x180027245  movzx   eax, byte ptr [rdi+2Ah]
0x180027249  cmp     eax, ecx
0x18002724b  jz      loc_180027164
0x180027251  cmp     dword ptr [rsi+30h], 1
0x180027255  setz    al
0x180027258  mov     [rdi+2Ah], al
0x18002725b  jmp     loc_18002716A
0x180027260  xor     edi, edi
0x180027262  xorps   xmm0, xmm0
0x180027265  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18002726a  mov     [rbp+57h+var_78], rdi
0x18002726e  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x180027273  mov     [rbp+57h+var_50], rdi
0x180027277  lea     rcx, [rbp+57h+var_88]
0x18002727b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180027280  lea     rcx, [rbp+57h+var_60]
0x180027284  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180027289  mov     rdx, [rbp+57h+var_88+8]
0x18002728d  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x180027291  sub     rdx, rcx
0x180027294  sar     rdx, 1; unsigned __int64
0x180027297  mov     r9, r12
0x18002729a  lea     r8, aTheEsimProfile; "The eSim profile does not exist in cach"...
0x1800272a1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800272a6  mov     rdx, [rbp+57h+var_60+8]
0x1800272aa  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x1800272ae  sub     rdx, rcx
0x1800272b1  sar     rdx, 1; unsigned __int64
0x1800272b4  mov     rax, [rbp+57h+var_88]
0x1800272b8  mov     [rsp+0C0h+var_98], rax
0x1800272bd  mov     dword ptr [rsp+0C0h+var_A0], 390h
0x1800272c5  lea     r9, aCesimsettingse_29; "CESimSettingServer::UpdateESimProfileCa"...
0x1800272cc  lea     r8, aSDS; "%S(%d):%s"
0x1800272d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800272d8  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800272dd  mov     ecx, [rax]
0x1800272df  cmp     ecx, 2
0x1800272e2  jbe     short loc_180027305
0x1800272e4  mov     rcx, [rbp+57h+var_60]
0x1800272e8  mov     [rbp+57h+var_70], rcx
0x1800272ec  lea     rcx, [rbp+57h+var_70]
0x1800272f0  mov     [rsp+0C0h+var_A0], rcx
0x1800272f5  lea     rdx, byte_1800757CD
0x1800272fc  mov     rcx, rax
0x1800272ff  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180027304  nop
0x180027305  lea     rcx, [rbp+57h+var_60]
0x180027309  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002730e  nop
0x18002730f  jmp     loc_1800273B1
0x180027314  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x180027319  mov     [rbp+57h+var_50], rdi
0x18002731d  lea     rcx, [rbp+57h+var_88]
  ... truncated ...
```
