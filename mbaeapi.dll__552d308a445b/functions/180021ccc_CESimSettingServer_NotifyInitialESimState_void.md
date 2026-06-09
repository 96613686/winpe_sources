# CESimSettingServer::NotifyInitialESimState(void)

- ea: `0x180021ccc`
- end: `0x18002229c`
- name: `?NotifyInitialESimState@CESimSettingServer@@AEAAJXZ`
- size: `1488`
- prototype: `__int64 __fastcall(CESimSettingServer *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f234`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x180002efc`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x18001f104`
- `0x180020fa0`
- `0x180021330`
- `0x180021ccc`
- `0x18005c010`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180021e2f`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180022269`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180021e2f`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180022269`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180021e85`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180021ebf`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180022255`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180021e85`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180021ebf`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180022255`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180021dfb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180021dfb`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x180021e61`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x180021e61`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CESimSettingServer::NotifyInitialESimState(CESimSettingServer *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int v8; // ebx
  __int64 v9; // rcx
  unsigned int *v10; // rcx
  unsigned int v11; // esi
  unsigned int *v12; // rax
  char *v13; // rbx
  unsigned int *v14; // rdi
  __int64 v15; // rcx
  char IsESimInserted; // al
  void (__fastcall *v17)(char *, unsigned int *, _QWORD, __int64, _BYTE *); // r10
  char *v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  _OWORD *v21; // rax
  _OWORD *v22; // rcx
  __int64 v23; // rdx
  char v24; // al
  void (__fastcall *v25)(char *, unsigned int *, __int64, __int64, _BYTE *); // r10
  char *v26; // rcx
  __int64 v27; // rcx
  _OWORD *v28; // rax
  _OWORD *v29; // rcx
  __int64 v30; // rdx
  const struct _tlgProvider_t *v31; // rax
  __int64 v32; // r8
  __int64 v33; // r9
  unsigned int *v34; // rcx
  unsigned int v35[2]; // [rsp+20h] [rbp-E0h]
  __int64 v36; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int *v37; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v38[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h]
  int v40; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v41[912]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v42[912]; // [rsp+3F0h] [rbp+2F0h] BYREF
  unsigned __int16 *v43[2]; // [rsp+780h] [rbp+680h] BYREF
  __int64 v44; // [rsp+790h] [rbp+690h]
  unsigned int v45[4]; // [rsp+798h] [rbp+698h] BYREF
  _BYTE v46[80]; // [rsp+7B0h] [rbp+6B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+838h] [rbp+738h]

  *(_OWORD *)v38 = 0;
  v39 = 0;
  *(_OWORD *)v43 = 0;
  v44 = 0;
  std::vector<unsigned short>::resize(v38);
  std::vector<unsigned short>::resize(v43);
  StringCchPrintfW(v38[0], v38[1] - v38[0], L"Enter");
  v35[0] = 267;
  StringCchPrintfW(v43[0], v43[1] - v43[0], L"%S(%d):%s", "CESimSettingServer::NotifyInitialESimState");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    *(unsigned __int16 **)v45 = v43[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)&word_180075C56,
      v3,
      v4,
      (const unsigned __int16 **)v45);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v43);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v38);
  v40 = 0;
  v36 = -1;
  v5 = WwanOpenHandle(1, 0, &v40, &v36);
  if ( v5 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x10F,
           (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\esimsettingserver.cpp",
           (const char *)v5,
           v35[0]);
LABEL_5:
    if ( v36 != -1 )
      WwanCloseHandle(v36, 0);
    return v6;
  }
  v37 = 0;
  v38[0] = (unsigned __int16 *)&v37;
  v38[1] = 0;
  LOBYTE(v39) = 1;
  v8 = WwanEnumerateInterfaces(v36, 0, &v38[1]);
  if ( (_BYTE)v39 )
  {
    v9 = *(_QWORD *)v38[0];
    *(_QWORD *)v38[0] = v38[1];
    if ( v9 )
      WwanFreeMemory(v9);
  }
  if ( v8 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x112,
           (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\esimsettingserver.cpp",
           (const char *)v8,
           v35[0]);
    v10 = v37;
    v37 = 0;
    if ( v10 )
      WwanFreeMemory(v10);
    goto LABEL_5;
  }
  v11 = 0;
  v12 = v37;
  if ( *v37 )
  {
    v13 = (char *)this + 8;
    do
    {
      v14 = &v12[147 * v11 + 1];
      memset_0(v46, 0, 0x42u);
      *(_OWORD *)v45 = 0;
      memset_0(v41, 0, sizeof(v41));
      v41[888] = 1;
      IsESimInserted = CESimSettingServer::IsESimInserted(v15, v14, 0, &v36);
      v17 = *(void (__fastcall **)(char *, unsigned int *, _QWORD, __int64, _BYTE *))(*(_QWORD *)v13 + 56LL);
      v18 = (char *)this + 8;
      if ( IsESimInserted )
      {
        v17(v18, v14, 0, 2, v46);
        if ( (unsigned __int8)CESimSettingServer::IsProfileActive(v19, v14, 0, &v36) )
        {
          v21 = v42;
          v22 = v41;
          v23 = 7;
          do
          {
            *v21 = *v22;
            v21[1] = v22[1];
            v21[2] = v22[2];
            v21[3] = v22[3];
            v21[4] = v22[4];
            v21[5] = v22[5];
            v21[6] = v22[6];
            v21[7] = v22[7];
            v21 += 8;
            v22 += 8;
            --v23;
          }
          while ( v23 );
          *v21 = *v22;
          (*(void (__fastcall **)(char *, unsigned int *, _QWORD, const unsigned __int16 *, _BYTE *))(*(_QWORD *)v13 + 64LL))(
            (char *)this + 8,
            v45,
            0,
            &dword_1800684AC,
            v42);
          *(_OWORD *)v43 = *(_OWORD *)v14;
          LODWORD(v44) = 0;
          *(_BYTE *)std::map<std::pair<_GUID,enum SimSlot>,bool,AdapterSlot_COMP,std::allocator<std::pair<std::pair<_GUID,enum SimSlot> const,bool>>>::operator[](
                      (__int64 *)this + 17,
                      v43) = 1;
        }
      }
      else
      {
        v17(v18, v14, 0, 1, v46);
      }
      v24 = CESimSettingServer::IsESimInserted(v20, v14, 1, &v36);
      v25 = *(void (__fastcall **)(char *, unsigned int *, __int64, __int64, _BYTE *))(*(_QWORD *)v13 + 56LL);
      v26 = (char *)this + 8;
      if ( v24 )
      {
        v25(v26, v14, 1, 2, v46);
        if ( (unsigned __int8)CESimSettingServer::IsProfileActive(v27, v14, 1, &v36) )
        {
          v28 = v42;
          v29 = v41;
          v30 = 7;
          do
          {
            *v28 = *v29;
            v28[1] = v29[1];
            v28[2] = v29[2];
            v28[3] = v29[3];
            v28[4] = v29[4];
            v28[5] = v29[5];
            v28[6] = v29[6];
            v28[7] = v29[7];
            v28 += 8;
            v29 += 8;
            --v30;
          }
          while ( v30 );
          *v28 = *v29;
          (*(void (__fastcall **)(char *, unsigned int *, __int64, const unsigned __int16 *, _BYTE *))(*(_QWORD *)v13 + 64LL))(
            (char *)this + 8,
            v45,
            1,
            &dword_1800684AC,
            v42);
          *(_OWORD *)v43 = *(_OWORD *)v45;
          LODWORD(v44) = 1;
          *(_BYTE *)std::map<std::pair<_GUID,enum SimSlot>,bool,AdapterSlot_COMP,std::allocator<std::pair<std::pair<_GUID,enum SimSlot> const,bool>>>::operator[](
                      (__int64 *)this + 17,
                      v43) = 1;
        }
      }
      else
      {
        v25(v26, v14, 1, 1, v46);
      }
      ++v11;
      v12 = v37;
    }
    while ( v11 < *v37 );
  }
  *(_OWORD *)v43 = 0;
  v44 = 0;
  *(_OWORD *)v38 = 0;
  v39 = 0;
  std::vector<unsigned short>::resize(v43);
  std::vector<unsigned short>::resize(v38);
  StringCchPrintfW(v43[0], v43[1] - v43[0], L"Exit");
  v35[0] = 328;
  StringCchPrintfW(
    v38[0],
    v38[1] - v38[0],
    L"%S(%d):%s",
    "CESimSettingServer::NotifyInitialESimState",
    *(_QWORD *)v35,
    v43[0]);
  v31 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v31 > 5u )
  {
    *(unsigned __int16 **)v45 = v38[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v31,
      (__int64)byte_180075C33,
      v32,
      v33,
      (const unsigned __int16 **)v45);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v38);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v43);
  v34 = v37;
  v37 = 0;
  if ( v34 )
    WwanFreeMemory(v34);
  if ( v36 != -1 )
    WwanCloseHandle(v36, 0);
  return 0;
}

```

## disassembly

```asm
0x180021ccc  mov     [rsp-8+arg_8], rbx
0x180021cd1  mov     [rsp-8+arg_10], rsi
0x180021cd6  push    rbp
0x180021cd7  push    rdi
0x180021cd8  push    r12
0x180021cda  push    r14
0x180021cdc  push    r15
0x180021cde  lea     rbp, [rsp-710h]
0x180021ce6  sub     rsp, 810h
0x180021ced  mov     rax, cs:__security_cookie
0x180021cf4  xor     rax, rsp
0x180021cf7  mov     [rbp+730h+var_30], rax
0x180021cfe  mov     r14, rcx
0x180021d01  xorps   xmm0, xmm0
0x180021d04  movdqu  xmmword ptr [rsp+830h+var_7F0], xmm0
0x180021d0a  xor     r15d, r15d
0x180021d0d  mov     [rsp+830h+var_7E0], r15
0x180021d12  movdqu  xmmword ptr [rbp+730h+var_B0], xmm0
0x180021d1a  mov     [rbp+730h+var_A0], r15
0x180021d21  lea     rcx, [rsp+830h+var_7F0]
0x180021d26  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180021d2b  lea     rcx, [rbp+730h+var_B0]
0x180021d32  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180021d37  mov     rdx, [rsp+830h+var_7F0+8]
0x180021d3c  mov     rcx, [rsp+830h+var_7F0]; unsigned __int16 *
0x180021d41  sub     rdx, rcx
0x180021d44  sar     rdx, 1; unsigned __int64
0x180021d47  lea     r8, aEnter; "Enter"
0x180021d4e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021d53  mov     rdx, [rbp+730h+var_B0+8]
0x180021d5a  mov     rcx, [rbp+730h+var_B0]; unsigned __int16 *
0x180021d61  sub     rdx, rcx
0x180021d64  sar     rdx, 1; unsigned __int64
0x180021d67  mov     rax, [rsp+830h+var_7F0]
0x180021d6c  mov     [rsp+830h+var_808], rax
0x180021d71  mov     [rsp+830h+var_810], 10Bh
0x180021d79  lea     r9, aCesimsettingse_28; "CESimSettingServer::NotifyInitialESimSt"...
0x180021d80  lea     r8, aSDS; "%S(%d):%s"
0x180021d87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021d8c  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180021d91  mov     ecx, [rax]
0x180021d93  cmp     ecx, 5
0x180021d96  jbe     short loc_180021DC2
0x180021d98  mov     rcx, [rbp+730h+var_B0]
0x180021d9f  mov     qword ptr [rbp+730h+var_98], rcx
0x180021da6  lea     rcx, [rbp+730h+var_98]
0x180021dad  mov     qword ptr [rsp+830h+var_810], rcx; unsigned int
0x180021db2  lea     rdx, word_180075C56
0x180021db9  mov     rcx, rax
0x180021dbc  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180021dc1  nop
0x180021dc2  lea     rcx, [rbp+730h+var_B0]
0x180021dc9  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180021dce  nop
0x180021dcf  lea     rcx, [rsp+830h+var_7F0]
0x180021dd4  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180021dd9  nop
0x180021dda  mov     [rsp+830h+var_7D8], r15d
0x180021ddf  mov     [rsp+830h+var_800], 0FFFFFFFFFFFFFFFFh
0x180021de8  lea     r9, [rsp+830h+var_800]
0x180021ded  lea     r8, [rsp+830h+var_7D8]
0x180021df2  xor     edx, edx
0x180021df4  lea     r12d, [rdx+1]
0x180021df8  mov     ecx, r12d
0x180021dfb  call    cs:__imp_WwanOpenHandle
0x180021e01  test    eax, eax
0x180021e03  jz      short loc_180021E3C
0x180021e05  mov     rcx, [rbp+738h]; this
0x180021e0c  mov     r9d, eax; char *
0x180021e0f  lea     r8, aOnecoreuapNetM_5; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180021e16  mov     edx, 10Fh; void *
0x180021e1b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180021e20  mov     ebx, eax
0x180021e22  mov     rcx, [rsp+830h+var_800]
0x180021e27  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180021e2b  jz      short loc_180021E35
0x180021e2d  xor     edx, edx
0x180021e2f  call    cs:__imp_WwanCloseHandle
0x180021e35  mov     eax, ebx
0x180021e37  jmp     loc_180022271
0x180021e3c  mov     [rsp+830h+var_7F8], r15
0x180021e41  lea     rax, [rsp+830h+var_7F8]
0x180021e46  mov     [rsp+830h+var_7F0], rax
0x180021e4b  mov     [rsp+830h+var_7F0+8], r15
0x180021e50  mov     byte ptr [rsp+830h+var_7E0], r12b
0x180021e55  lea     r8, [rsp+830h+var_7F0+8]
0x180021e5a  xor     edx, edx
0x180021e5c  mov     rcx, [rsp+830h+var_800]
0x180021e61  call    cs:__imp_WwanEnumerateInterfaces
0x180021e67  mov     ebx, eax
0x180021e69  cmp     byte ptr [rsp+830h+var_7E0], r15b
0x180021e6e  jz      short loc_180021E8B
0x180021e70  mov     r8, [rsp+830h+var_7F0]
0x180021e75  mov     rcx, [r8]
0x180021e78  mov     rdx, [rsp+830h+var_7F0+8]
0x180021e7d  mov     [r8], rdx
0x180021e80  test    rcx, rcx
0x180021e83  jz      short loc_180021E8B
0x180021e85  call    cs:__imp_WwanFreeMemory
0x180021e8b  test    ebx, ebx
0x180021e8d  jz      short loc_180021ECA
0x180021e8f  mov     rcx, [rbp+738h]; this
0x180021e96  mov     r9d, ebx; char *
0x180021e99  lea     r8, aOnecoreuapNetM_5; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180021ea0  mov     edx, 112h; void *
0x180021ea5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180021eaa  mov     ebx, eax
0x180021eac  mov     rcx, [rsp+830h+var_7F8]
0x180021eb1  mov     [rsp+830h+var_7F8], r15
0x180021eb6  test    rcx, rcx
0x180021eb9  jz      loc_180021E22
0x180021ebf  call    cs:__imp_WwanFreeMemory
0x180021ec5  jmp     loc_180021E22
0x180021eca  mov     esi, r15d
0x180021ecd  mov     rax, [rsp+830h+var_7F8]
0x180021ed2  cmp     [rax], r15d
0x180021ed5  jbe     loc_180022170
0x180021edb  lea     rbx, [r14+8]
0x180021edf  mov     ecx, esi
0x180021ee1  imul    rdx, rcx, 24Ch
0x180021ee8  lea     rdi, [rax+4]
0x180021eec  add     rdi, rdx
0x180021eef  xor     edx, edx; Val
0x180021ef1  lea     r8d, [rdx+42h]; Size
0x180021ef5  lea     rcx, [rbp+730h+var_80]; void *
0x180021efc  call    memset_0
0x180021f01  xorps   xmm0, xmm0
0x180021f04  movups  xmmword ptr [rbp+730h+var_98], xmm0
0x180021f0b  xor     edx, edx; Val
0x180021f0d  mov     r8d, 390h; Size
0x180021f13  lea     rcx, [rsp+830h+var_7D0]; void *
0x180021f18  call    memset_0
0x180021f1d  mov     [rbp+730h+var_458], r12b
0x180021f24  lea     r9, [rsp+830h+var_800]
0x180021f29  xor     r8d, r8d
0x180021f2c  mov     rdx, rdi
0x180021f2f  call    ?IsESimInserted@CESimSettingServer@@AEAA_NAEBU_GUID@@W4SimSlot@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@@wil@@@Z; CESimSettingServer::IsESimInserted(_GUID const &,SimSlot,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>> &)
0x180021f34  mov     rcx, [rbx]
0x180021f37  mov     r10, [rcx+38h]
0x180021f3b  xor     r8d, r8d
0x180021f3e  mov     rdx, rdi
0x180021f41  mov     rcx, rbx
0x180021f44  test    al, al
0x180021f46  lea     rax, [rbp+730h+var_80]
0x180021f4d  mov     qword ptr [rsp+830h+var_810], rax
0x180021f52  mov     rax, r10
0x180021f55  jz      loc_180022037
0x180021f5b  lea     r9d, [r8+2]
0x180021f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f64  lea     r9, [rsp+830h+var_800]
0x180021f69  xor     r8d, r8d
0x180021f6c  mov     rdx, rdi
0x180021f6f  call    ?IsProfileActive@CESimSettingServer@@AEAA_NAEBU_GUID@@W4SimSlot@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@@wil@@@Z; CESimSettingServer::IsProfileActive(_GUID const &,SimSlot,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>> &)
0x180021f74  test    al, al
0x180021f76  jz      loc_18002203F
0x180021f7c  lea     rax, [rbp+730h+var_440]
0x180021f83  lea     rcx, [rsp+830h+var_7D0]
0x180021f88  mov     edx, 7
0x180021f8d  lea     r8d, [rdx+79h]
0x180021f91  movups  xmm0, xmmword ptr [rcx]
0x180021f94  movups  xmmword ptr [rax], xmm0
0x180021f97  movups  xmm1, xmmword ptr [rcx+10h]
0x180021f9b  movups  xmmword ptr [rax+10h], xmm1
0x180021f9f  movups  xmm0, xmmword ptr [rcx+20h]
0x180021fa3  movups  xmmword ptr [rax+20h], xmm0
0x180021fa7  movups  xmm1, xmmword ptr [rcx+30h]
0x180021fab  movups  xmmword ptr [rax+30h], xmm1
0x180021faf  movups  xmm0, xmmword ptr [rcx+40h]
0x180021fb3  movups  xmmword ptr [rax+40h], xmm0
0x180021fb7  movups  xmm1, xmmword ptr [rcx+50h]
0x180021fbb  movups  xmmword ptr [rax+50h], xmm1
0x180021fbf  movups  xmm0, xmmword ptr [rcx+60h]
0x180021fc3  movups  xmmword ptr [rax+60h], xmm0
0x180021fc7  movups  xmm1, xmmword ptr [rcx+70h]
0x180021fcb  movups  xmmword ptr [rax+70h], xmm1
0x180021fcf  add     rax, r8
0x180021fd2  add     rcx, r8
0x180021fd5  sub     rdx, 1
0x180021fd9  jnz     short loc_180021F91
0x180021fdb  movups  xmm0, xmmword ptr [rcx]
0x180021fde  movups  xmmword ptr [rax], xmm0
0x180021fe1  mov     rax, [rbx]
0x180021fe4  lea     rcx, [rbp+730h+var_440]
0x180021feb  mov     qword ptr [rsp+830h+var_810], rcx
0x180021ff0  lea     r9, dword_1800684AC
0x180021ff7  xor     r8d, r8d
0x180021ffa  lea     rdx, [rbp+730h+var_98]
0x180022001  mov     rcx, rbx
0x180022004  mov     rax, [rax+40h]
0x180022008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002200d  movups  xmm0, xmmword ptr [rdi]
0x180022010  movdqu  xmmword ptr [rbp+730h+var_B0], xmm0
0x180022018  mov     dword ptr [rbp+730h+var_A0], r15d
0x18002201f  lea     rcx, [r14+88h]
0x180022026  lea     rdx, [rbp+730h+var_B0]
0x18002202d  call    ??A?$map@U?$pair@U_GUID@@W4SimSlot@@@std@@_NUAdapterSlot_COMP@@V?$allocator@U?$pair@$$CBU?$pair@U_GUID@@W4SimSlot@@@std@@_N@std@@@2@@std@@QEAAAEA_NAEBU?$pair@U_GUID@@W4SimSlot@@@1@@Z; std::map<std::pair<_GUID,SimSlot>,bool,AdapterSlot_COMP,std::allocator<std::pair<std::pair<_GUID,SimSlot> const,bool>>>::operator[](std::pair<_GUID,SimSlot> const &)
0x180022032  mov     [rax], r12b
0x180022035  jmp     short loc_18002203F
0x180022037  mov     r9d, r12d
0x18002203a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002203f  lea     r9, [rsp+830h+var_800]
0x180022044  mov     r8d, r12d
0x180022047  mov     rdx, rdi
0x18002204a  call    ?IsESimInserted@CESimSettingServer@@AEAA_NAEBU_GUID@@W4SimSlot@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@@wil@@@Z; CESimSettingServer::IsESimInserted(_GUID const &,SimSlot,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>> &)
0x18002204f  mov     rcx, [rbx]
0x180022052  mov     r10, [rcx+38h]
0x180022056  mov     r8d, r12d
0x180022059  mov     rdx, rdi
0x18002205c  mov     rcx, rbx
0x18002205f  test    al, al
0x180022061  lea     rax, [rbp+730h+var_80]
0x180022068  mov     qword ptr [rsp+830h+var_810], rax
0x18002206d  mov     rax, r10
0x180022070  jz      loc_180022158
0x180022076  mov     r9d, 2
0x18002207c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022081  lea     r9, [rsp+830h+var_800]
0x180022086  mov     r8d, r12d
0x180022089  mov     rdx, rdi
0x18002208c  call    ?IsProfileActive@CESimSettingServer@@AEAA_NAEBU_GUID@@W4SimSlot@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@@wil@@@Z; CESimSettingServer::IsProfileActive(_GUID const &,SimSlot,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>> &)
0x180022091  test    al, al
0x180022093  jz      loc_180022160
0x180022099  lea     rax, [rbp+730h+var_440]
0x1800220a0  lea     rcx, [rsp+830h+var_7D0]
0x1800220a5  mov     edx, 7
0x1800220aa  lea     r8d, [rdx+79h]
0x1800220ae  movups  xmm0, xmmword ptr [rcx]
0x1800220b1  movups  xmmword ptr [rax], xmm0
0x1800220b4  movups  xmm1, xmmword ptr [rcx+10h]
0x1800220b8  movups  xmmword ptr [rax+10h], xmm1
0x1800220bc  movups  xmm0, xmmword ptr [rcx+20h]
0x1800220c0  movups  xmmword ptr [rax+20h], xmm0
0x1800220c4  movups  xmm1, xmmword ptr [rcx+30h]
0x1800220c8  movups  xmmword ptr [rax+30h], xmm1
0x1800220cc  movups  xmm0, xmmword ptr [rcx+40h]
0x1800220d0  movups  xmmword ptr [rax+40h], xmm0
0x1800220d4  movups  xmm1, xmmword ptr [rcx+50h]
0x1800220d8  movups  xmmword ptr [rax+50h], xmm1
0x1800220dc  movups  xmm0, xmmword ptr [rcx+60h]
0x1800220e0  movups  xmmword ptr [rax+60h], xmm0
0x1800220e4  movups  xmm1, xmmword ptr [rcx+70h]
0x1800220e8  movups  xmmword ptr [rax+70h], xmm1
0x1800220ec  add     rax, r8
0x1800220ef  add     rcx, r8
0x1800220f2  sub     rdx, 1
0x1800220f6  jnz     short loc_1800220AE
0x1800220f8  movups  xmm0, xmmword ptr [rcx]
0x1800220fb  movups  xmmword ptr [rax], xmm0
0x1800220fe  mov     rax, [rbx]
0x180022101  lea     rcx, [rbp+730h+var_440]
0x180022108  mov     qword ptr [rsp+830h+var_810], rcx
0x18002210d  lea     r9, dword_1800684AC
0x180022114  mov     r8d, r12d
0x180022117  lea     rdx, [rbp+730h+var_98]
0x18002211e  mov     rcx, rbx
0x180022121  mov     rax, [rax+40h]
0x180022125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002212a  movups  xmm0, xmmword ptr [rbp+730h+var_98]
0x180022131  movdqu  xmmword ptr [rbp+730h+var_B0], xmm0
0x180022139  mov     dword ptr [rbp+730h+var_A0], r12d
0x180022140  lea     rcx, [r14+88h]
0x180022147  lea     rdx, [rbp+730h+var_B0]
0x18002214e  call    ??A?$map@U?$pair@U_GUID@@W4SimSlot@@@std@@_NUAdapterSlot_COMP@@V?$allocator@U?$pair@$$CBU?$pair@U_GUID@@W4SimSlot@@@std@@_N@std@@@2@@std@@QEAAAEA_NAEBU?$pair@U_GUID@@W4SimSlot@@@1@@Z; std::map<std::pair<_GUID,SimSlot>,bool,AdapterSlot_COMP,std::allocator<std::pair<std::pair<_GUID,SimSlot> const,bool>>>::operator[](std::pair<_GUID,SimSlot> const &)
0x180022153  mov     [rax], r12b
0x180022156  jmp     short loc_180022160
0x180022158  mov     r9d, r12d
0x18002215b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022160  add     esi, r12d
0x180022163  mov     rax, [rsp+830h+var_7F8]
0x180022168  cmp     esi, [rax]
0x18002216a  jb      loc_180021EDF
0x180022170  xorps   xmm0, xmm0
0x180022173  movdqu  xmmword ptr [rbp+730h+var_B0], xmm0
0x18002217b  mov     [rbp+730h+var_A0], r15
0x180022182  movdqu  xmmword ptr [rsp+830h+var_7F0], xmm0
0x180022188  mov     [rsp+830h+var_7E0], r15
0x18002218d  lea     rcx, [rbp+730h+var_B0]
0x180022194  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180022199  lea     rcx, [rsp+830h+var_7F0]
0x18002219e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800221a3  mov     rdx, [rbp+730h+var_B0+8]
0x1800221aa  mov     rcx, [rbp+730h+var_B0]; unsigned __int16 *
0x1800221b1  sub     rdx, rcx
0x1800221b4  sar     rdx, 1; unsigned __int64
0x1800221b7  lea     r8, aExit; "Exit"
0x1800221be  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800221c3  mov     rdx, [rsp+830h+var_7F0+8]
0x1800221c8  mov     rcx, [rsp+830h+var_7F0]; unsigned __int16 *
0x1800221cd  sub     rdx, rcx
0x1800221d0  sar     rdx, 1; unsigned __int64
0x1800221d3  mov     rax, [rbp+730h+var_B0]
0x1800221da  mov     [rsp+830h+var_808], rax
0x1800221df  mov     [rsp+830h+var_810], 148h
0x1800221e7  lea     r9, aCesimsettingse_28; "CESimSettingServer::NotifyInitialESimSt"...
0x1800221ee  lea     r8, aSDS; "%S(%d):%s"
0x1800221f5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800221fa  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800221ff  mov     ecx, [rax]
0x180022201  cmp     ecx, 5
0x180022204  jbe     short loc_18002222E
  ... truncated ...
```
