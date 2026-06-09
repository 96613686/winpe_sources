# CWwanTranslator::_CheckIsDmConfigProfileExisted(_GUID const &,ushort *,bool &)

- ea: `0x18003c7d4`
- end: `0x18003cafd`
- name: `?_CheckIsDmConfigProfileExisted@CWwanTranslator@@AEAAJAEBU_GUID@@PEAGAEA_N@Z`
- size: `809`
- prototype: `int __fastcall(CWwanTranslator *this, const struct _GUID *, unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180033978`

## callees

- `0x18000178c`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x18003c7d4`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003cae2`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003cae2`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003c93d`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003c93d`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18003c8ce`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18003c8ce`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfile` at `0x18003c917`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfile` at `0x18003c917`

## string_xrefs

- `0x18003c85c`: `CWwanTranslator::_CheckIsDmConfigProfileExisted`
- `0x18003c9d2`: `CWwanTranslator::_CheckIsDmConfigProfileExisted`
- `0x18003ca87`: `CWwanTranslator::_CheckIsDmConfigProfileExisted`
- `0x18003c9a7`: `Error in _CheckIsDmConfigProfileExisted. Hr=0x%x`

## pseudocode

```c
int __fastcall CWwanTranslator::_CheckIsDmConfigProfileExisted(
        CWwanTranslator *this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        bool *a4)
{
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // eax
  int DMConfigProfile; // eax
  int v13; // ebx
  signed int v14; // eax
  unsigned int v15; // edi
  __int64 v16; // r9
  const struct _tlgProvider_t *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  const struct _tlgProvider_t *v20; // rax
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned int v23[2]; // [rsp+20h] [rbp-60h]
  __int64 v24; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v25[2]; // [rsp+38h] [rbp-48h] BYREF
  char v26; // [rsp+40h] [rbp-40h]
  unsigned __int16 *v27[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v28; // [rsp+58h] [rbp-28h]
  unsigned __int16 *v29[2]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v30; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  CWwanTranslator *v32; // [rsp+A0h] [rbp+20h] BYREF
  __int64 v33; // [rsp+B8h] [rbp+38h] BYREF

  v32 = this;
  *(_OWORD *)v29 = 0;
  v30 = 0;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  std::vector<unsigned short>::resize(v29);
  std::vector<unsigned short>::resize(v27);
  StringCchPrintfW(v29[0], v29[1] - v29[0], L"Enter");
  v23[0] = 2883;
  StringCchPrintfW(v27[0], v27[1] - v27[0], L"%S(%d):%s", "CWwanTranslator::_CheckIsDmConfigProfileExisted");
  v7 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v7 > 5u )
  {
    *(unsigned __int16 **)v25 = v27[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v7,
      (__int64)byte_1800766EB,
      v8,
      v9,
      (const unsigned __int16 **)v25);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v27);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v29);
  *a4 = 0;
  v33 = 0;
  LODWORD(v32) = 0;
  v10 = WwanOpenHandle(1, 0, &v32, &v33);
  if ( v10 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xB48,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
             (const char *)v10,
             v23[0]);
  *(_QWORD *)v25 = &v33;
  v26 = 1;
  v24 = 0;
  DMConfigProfile = WwanGetDMConfigProfile(v33, a2, a3, &v24);
  v13 = DMConfigProfile;
  if ( DMConfigProfile )
  {
    if ( DMConfigProfile == 1168 )
    {
      *a4 = 0;
      v13 = 0;
    }
  }
  else
  {
    *a4 = 1;
  }
  if ( v24 )
    WwanFreeMemory(v24);
  if ( v13 > 0 )
    v14 = (unsigned __int16)v13 | 0x80070000;
  else
    v14 = v13;
  v28 = 0;
  *(_OWORD *)v27 = 0;
  if ( v14 >= 0 )
  {
    *(_OWORD *)v29 = 0;
    v30 = 0;
    std::vector<unsigned short>::resize(v27);
    std::vector<unsigned short>::resize(v29);
    StringCchPrintfW(v27[0], v27[1] - v27[0], L"Exit");
    v23[0] = 2914;
    StringCchPrintfW(
      v29[0],
      v29[1] - v29[0],
      L"%S(%d):%s",
      "CWwanTranslator::_CheckIsDmConfigProfileExisted",
      *(_QWORD *)v23,
      v27[0]);
    v20 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v20 > 5u )
    {
      *(unsigned __int16 **)v25 = v29[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v20,
        (__int64)byte_1800766A5,
        v21,
        v22,
        (const unsigned __int16 **)v25);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v29);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v27);
    v15 = 0;
  }
  else
  {
    v15 = (unsigned __int16)v13 | 0x80070000;
    *(_OWORD *)v29 = 0;
    v30 = 0;
    std::vector<unsigned short>::resize(v27);
    std::vector<unsigned short>::resize(v29);
    v16 = v15;
    if ( v13 <= 0 )
      v16 = (unsigned int)v13;
    StringCchPrintfW(v27[0], v27[1] - v27[0], L"Error in _CheckIsDmConfigProfileExisted. Hr=0x%x", v16);
    v23[0] = 2910;
    StringCchPrintfW(
      v29[0],
      v29[1] - v29[0],
      L"%S(%d):%s",
      "CWwanTranslator::_CheckIsDmConfigProfileExisted",
      *(_QWORD *)v23,
      v27[0]);
    v17 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v17 > 2u )
    {
      *(unsigned __int16 **)v25 = v29[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v17,
        (__int64)&dword_180076684,
        v18,
        v19,
        (const unsigned __int16 **)v25);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v29);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v27);
    if ( v13 <= 0 )
      v15 = v13;
  }
  WwanCloseHandle(v33, 0);
  return v15;
}

```

## disassembly

```asm
0x18003c7d4  mov     [rsp-18h+arg_8], rbx
0x18003c7d9  mov     [rsp-18h+arg_0], rcx
0x18003c7de  push    rbp
0x18003c7df  push    rsi
0x18003c7e0  push    rdi
0x18003c7e1  mov     rbp, rsp
0x18003c7e4  sub     rsp, 80h
0x18003c7eb  mov     rdi, r9
0x18003c7ee  mov     rbx, r8
0x18003c7f1  mov     rsi, rdx
0x18003c7f4  xorps   xmm0, xmm0
0x18003c7f7  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18003c7fc  mov     [rbp+var_10], 0
0x18003c804  movdqu  xmmword ptr [rbp+var_38], xmm0
0x18003c809  mov     [rbp+var_28], 0
0x18003c811  lea     rcx, [rbp+var_20]
0x18003c815  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003c81a  lea     rcx, [rbp+var_38]
0x18003c81e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003c823  mov     rdx, [rbp+var_20+8]
0x18003c827  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x18003c82b  sub     rdx, rcx
0x18003c82e  sar     rdx, 1; unsigned __int64
0x18003c831  lea     r8, aEnter; "Enter"
0x18003c838  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c83d  mov     rdx, [rbp+var_38+8]
0x18003c841  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x18003c845  sub     rdx, rcx
0x18003c848  sar     rdx, 1; unsigned __int64
0x18003c84b  mov     rax, [rbp+var_20]
0x18003c84f  mov     [rsp+80h+var_58], rax
0x18003c854  mov     [rsp+80h+var_60], 0B43h
0x18003c85c  lea     r9, aCwwantranslato_13; "CWwanTranslator::_CheckIsDmConfigProfil"...
0x18003c863  lea     r8, aSDS; "%S(%d):%s"
0x18003c86a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c86f  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003c874  mov     ecx, [rax]
0x18003c876  cmp     ecx, 5
0x18003c879  jbe     short loc_18003C89C
0x18003c87b  mov     rcx, [rbp+var_38]
0x18003c87f  mov     qword ptr [rbp+var_48], rcx
0x18003c883  lea     rcx, [rbp+var_48]
0x18003c887  mov     qword ptr [rsp+80h+var_60], rcx; unsigned int
0x18003c88c  lea     rdx, byte_1800766EB
0x18003c893  mov     rcx, rax
0x18003c896  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003c89b  nop
0x18003c89c  lea     rcx, [rbp+var_38]
0x18003c8a0  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003c8a5  nop
0x18003c8a6  lea     rcx, [rbp+var_20]
0x18003c8aa  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003c8af  mov     byte ptr [rdi], 0
0x18003c8b2  mov     [rbp+arg_18], 0
0x18003c8ba  mov     dword ptr [rbp+arg_0], 0
0x18003c8c1  lea     r9, [rbp+arg_18]
0x18003c8c5  lea     r8, [rbp+arg_0]
0x18003c8c9  xor     edx, edx
0x18003c8cb  lea     ecx, [rdx+1]
0x18003c8ce  call    cs:__imp_WwanOpenHandle
0x18003c8d4  test    eax, eax
0x18003c8d6  jz      short loc_18003C8F5
0x18003c8d8  mov     rcx, [rbp+18h]; this
0x18003c8dc  mov     r9d, eax; char *
0x18003c8df  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18003c8e6  mov     edx, 0B48h; void *
0x18003c8eb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003c8f0  jmp     loc_18003CAEA
0x18003c8f5  lea     rax, [rbp+arg_18]
0x18003c8f9  mov     qword ptr [rbp+var_48], rax
0x18003c8fd  mov     [rbp+var_40], 1
0x18003c901  mov     [rbp+var_50], 0
0x18003c909  lea     r9, [rbp+var_50]
0x18003c90d  mov     r8, rbx
0x18003c910  mov     rdx, rsi
0x18003c913  mov     rcx, [rbp+arg_18]
0x18003c917  call    cs:__imp_WwanGetDMConfigProfile
0x18003c91d  mov     ebx, eax
0x18003c91f  test    eax, eax
0x18003c921  jnz     short loc_18003C928
0x18003c923  mov     byte ptr [rdi], 1
0x18003c926  jmp     short loc_18003C934
0x18003c928  cmp     eax, 490h
0x18003c92d  jnz     short loc_18003C934
0x18003c92f  mov     byte ptr [rdi], 0
0x18003c932  xor     ebx, ebx
0x18003c934  mov     rcx, [rbp+var_50]
0x18003c938  test    rcx, rcx
0x18003c93b  jz      short loc_18003C943
0x18003c93d  call    cs:__imp_WwanFreeMemory
0x18003c943  movzx   edi, bx
0x18003c946  mov     ecx, 80070000h
0x18003c94b  test    ebx, ebx
0x18003c94d  jg      short loc_18003C953
0x18003c94f  mov     eax, ebx
0x18003c951  jmp     short loc_18003C957
0x18003c953  mov     eax, edi
0x18003c955  or      eax, ecx
0x18003c957  xorps   xmm0, xmm0
0x18003c95a  mov     [rbp+var_28], 0
0x18003c962  movdqu  xmmword ptr [rbp+var_38], xmm0
0x18003c967  test    eax, eax
0x18003c969  jns     loc_18003CA2F
0x18003c96f  or      edi, ecx
0x18003c971  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18003c976  mov     [rbp+var_10], 0
0x18003c97e  lea     rcx, [rbp+var_38]
0x18003c982  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003c987  lea     rcx, [rbp+var_20]
0x18003c98b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003c990  mov     r9d, edi
0x18003c993  test    ebx, ebx
0x18003c995  cmovle  r9d, ebx
0x18003c999  mov     rdx, [rbp+var_38+8]
0x18003c99d  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x18003c9a1  sub     rdx, rcx
0x18003c9a4  sar     rdx, 1; unsigned __int64
0x18003c9a7  lea     r8, aErrorInCheckis; "Error in _CheckIsDmConfigProfileExisted"...
0x18003c9ae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c9b3  mov     rdx, [rbp+var_20+8]
0x18003c9b7  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x18003c9bb  sub     rdx, rcx
0x18003c9be  sar     rdx, 1; unsigned __int64
0x18003c9c1  mov     rax, [rbp+var_38]
0x18003c9c5  mov     [rsp+80h+var_58], rax
0x18003c9ca  mov     [rsp+80h+var_60], 0B5Eh
0x18003c9d2  lea     r9, aCwwantranslato_13; "CWwanTranslator::_CheckIsDmConfigProfil"...
0x18003c9d9  lea     r8, aSDS; "%S(%d):%s"
0x18003c9e0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c9e5  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003c9ea  mov     ecx, [rax]
0x18003c9ec  cmp     ecx, 2
0x18003c9ef  jbe     short loc_18003CA12
0x18003c9f1  mov     rcx, [rbp+var_20]
0x18003c9f5  mov     qword ptr [rbp+var_48], rcx
0x18003c9f9  lea     rcx, [rbp+var_48]
0x18003c9fd  mov     qword ptr [rsp+80h+var_60], rcx
0x18003ca02  lea     rdx, dword_180076684
0x18003ca09  mov     rcx, rax
0x18003ca0c  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003ca11  nop
0x18003ca12  lea     rcx, [rbp+var_20]
0x18003ca16  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003ca1b  nop
0x18003ca1c  lea     rcx, [rbp+var_38]
0x18003ca20  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003ca25  test    ebx, ebx
0x18003ca27  cmovle  edi, ebx
0x18003ca2a  jmp     loc_18003CADC
0x18003ca2f  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18003ca34  mov     [rbp+var_10], 0
0x18003ca3c  lea     rcx, [rbp+var_38]
0x18003ca40  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003ca45  lea     rcx, [rbp+var_20]
0x18003ca49  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003ca4e  mov     rdx, [rbp+var_38+8]
0x18003ca52  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x18003ca56  sub     rdx, rcx
0x18003ca59  sar     rdx, 1; unsigned __int64
0x18003ca5c  lea     r8, aExit; "Exit"
0x18003ca63  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ca68  mov     rdx, [rbp+var_20+8]
0x18003ca6c  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x18003ca70  sub     rdx, rcx
0x18003ca73  sar     rdx, 1; unsigned __int64
0x18003ca76  mov     rax, [rbp+var_38]
0x18003ca7a  mov     [rsp+80h+var_58], rax
0x18003ca7f  mov     [rsp+80h+var_60], 0B62h
0x18003ca87  lea     r9, aCwwantranslato_13; "CWwanTranslator::_CheckIsDmConfigProfil"...
0x18003ca8e  lea     r8, aSDS; "%S(%d):%s"
0x18003ca95  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ca9a  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003ca9f  mov     ecx, [rax]
0x18003caa1  cmp     ecx, 5
0x18003caa4  jbe     short loc_18003CAC7
0x18003caa6  mov     rcx, [rbp+var_20]
0x18003caaa  mov     qword ptr [rbp+var_48], rcx
0x18003caae  lea     rcx, [rbp+var_48]
0x18003cab2  mov     qword ptr [rsp+80h+var_60], rcx
0x18003cab7  lea     rdx, byte_1800766A5
0x18003cabe  mov     rcx, rax
0x18003cac1  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003cac6  nop
0x18003cac7  lea     rcx, [rbp+var_20]
0x18003cacb  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003cad0  nop
0x18003cad1  lea     rcx, [rbp+var_38]
0x18003cad5  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003cada  xor     edi, edi
0x18003cadc  xor     edx, edx
0x18003cade  mov     rcx, [rbp+arg_18]
0x18003cae2  call    cs:__imp_WwanCloseHandle
0x18003cae8  mov     eax, edi
0x18003caea  mov     rbx, [rsp+80h+arg_8]
0x18003caf2  add     rsp, 80h
0x18003caf9  pop     rdi
0x18003cafa  pop     rsi
0x18003cafb  pop     rbp
0x18003cafc  retn
```
