# CWwanTranslator::_ProcessRoamingPolicyChange(_GUID const &,uchar *,uint)

- ea: `0x1800431f0`
- end: `0x18004382b`
- name: `?_ProcessRoamingPolicyChange@CWwanTranslator@@AEAAJAEBU_GUID@@PEAEI@Z`
- size: `1595`
- prototype: `int __fastcall(CWwanTranslator *this, const struct _GUID *, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18003812c`
- `0x1800460c0`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x18003994c`
- `0x1800431f0`
- `0x18005c010`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004368b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x1800437b8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x1800437f9`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004368b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x1800437b8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x1800437f9`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004357a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004367d`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800437aa`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800437eb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004357a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004367d`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800437aa`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800437eb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x1800432f5`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x1800432f5`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004336e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004336e`

## pseudocode

```c
int __fastcall CWwanTranslator::_ProcessRoamingPolicyChange(
        CWwanTranslator *this,
        const struct _GUID *a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  __int64 v4; // rbx
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // eax
  unsigned int Interface; // eax
  int v14; // ebx
  __int64 v15; // rdx
  char v16; // r9
  unsigned int v17; // r8d
  __int64 v18; // rbx
  int v19; // ecx
  int v20; // ecx
  _QWORD *v21; // rcx
  _QWORD *v22; // rdx
  const struct _tlgProvider_t *v23; // rax
  __int64 v24; // r8
  __int64 v25; // r9
  const struct _tlgProvider_t *v26; // rax
  __int64 v27; // r8
  __int64 v28; // r9
  const struct _tlgProvider_t *v29; // rax
  __int64 v30; // r8
  __int64 v31; // r9
  unsigned int v32; // [rsp+20h] [rbp-E0h]
  unsigned int *v33; // [rsp+20h] [rbp-E0h]
  unsigned int v34[2]; // [rsp+20h] [rbp-E0h]
  unsigned int v35[2]; // [rsp+20h] [rbp-E0h]
  _DWORD *v36; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v37[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v39[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v41[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h]
  unsigned int v43; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v44; // [rsp+90h] [rbp-70h] BYREF
  int v45; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v46[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v47; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v48[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v49; // [rsp+C8h] [rbp-38h]
  _QWORD v50[7]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v51; // [rsp+108h] [rbp+8h]
  _QWORD v52[7]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD *v53; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v4 = a4;
  *(_OWORD *)v46 = 0;
  v47 = 0;
  *(_OWORD *)v48 = 0;
  v49 = 0;
  std::vector<unsigned short>::resize(v46);
  std::vector<unsigned short>::resize(v48);
  StringCchPrintfW(v46[0], v46[1] - v46[0], L"Enter");
  v32 = 2546;
  StringCchPrintfW(v48[0], v48[1] - v48[0], L"%S(%d):%s", "CWwanTranslator::_ProcessRoamingPolicyChange");
  v8 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v8 > 5u )
  {
    *(unsigned __int16 **)v37 = v48[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v8,
      (__int64)byte_18007695D,
      v9,
      v10,
      (const unsigned __int16 **)v37);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v48);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v46);
  v38 = 0;
  v45 = 0;
  v11 = WwanOpenHandle(1, 0, &v45, &v38);
  if ( v11 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x9F4,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
             (const char *)v11,
             v32);
  v46[0] = (unsigned __int16 *)&v38;
  LOBYTE(v46[1]) = 1;
  v43 = 0;
  v36 = 0;
  v48[0] = (unsigned __int16 *)&v36;
  LOBYTE(v48[1]) = 1;
  v33 = &v43;
  Interface = WwanQueryInterface(v38, a2, 28);
  if ( !Interface )
  {
    if ( v43 != 4 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA03,
        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
        (const char *)0x80004005LL,
        (int)&v43);
      if ( v36 )
        WwanFreeMemory(v36);
      WwanCloseHandle(v38, 0);
      return -2147467259;
    }
    if ( v36 && *v36 == 1 )
    {
      v15 = *(unsigned int *)a3;
      if ( 20 * v15 + 4 != v4 )
      {
        v14 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA12,
          (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
          (const char *)0x8007000ELL,
          (int)&v43);
        goto LABEL_34;
      }
      v37[0] = 0;
      v16 = 0;
      v17 = 0;
      if ( (_DWORD)v15 )
      {
        do
        {
          v18 = 5LL * v17;
          if ( WWAN_PROFILE_SET_GUID_INTERNET_AO == *(_OWORD *)&a3[20 * v17 + 4]
            || WWAN_PROFILE_SET_GUID_ALL_HOST_PROFILES == *(_QWORD *)&a3[20 * v17 + 4]
            && *(_QWORD *)&a3[20 * v17 + 12] == 0x5770A73BA7DDA38FLL )
          {
            v16 = 1;
            v19 = *(_DWORD *)&a3[20 * v17 + 20];
            if ( v19 )
            {
              v20 = v19 - 1;
              if ( v20 )
              {
                if ( v20 != 1 )
                {
                  *(_OWORD *)v41 = 0;
                  v42 = 0;
                  *(_OWORD *)v39 = 0;
                  v40 = 0;
                  std::vector<unsigned short>::resize(v41);
                  std::vector<unsigned short>::resize(v39);
                  StringCchPrintfW(
                    v41[0],
                    v41[1] - v41[0],
                    L"WwanSvc returns invalid Internet roamControlState 0x%x",
                    *(unsigned int *)&a3[4 * v18 + 20],
                    &v43,
                    &v36,
                    0,
                    0);
                  v34[0] = 2603;
                  StringCchPrintfW(
                    v39[0],
                    v39[1] - v39[0],
                    L"%S(%d):%s",
                    "CWwanTranslator::_ProcessRoamingPolicyChange",
                    *(_QWORD *)v34,
                    v41[0]);
                  v23 = MbaeApiLogging::Provider();
                  if ( *(_DWORD *)v23 > 2u )
                  {
                    v44 = v39[0];
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                      (__int64)v23,
                      (__int64)byte_180076919,
                      v24,
                      v25,
                      (const unsigned __int16 **)&v44);
                  }
                  std::vector<unsigned short>::~vector<unsigned short>((char **)v39);
                  std::vector<unsigned short>::~vector<unsigned short>((char **)v41);
                  if ( v36 )
                    WwanFreeMemory(v36);
                  v14 = -2147467259;
                  goto LABEL_36;
                }
                v37[0] = 2;
              }
              else
              {
                v37[0] = 1;
              }
            }
            else
            {
              v37[0] = 0;
            }
          }
          ++v17;
        }
        while ( v17 < (unsigned int)v15 );
        if ( !v16 )
          goto LABEL_30;
        v50[0] = off_18005ED98;
        v50[1] = this;
        v50[2] = a2;
        v50[3] = v37;
        v51 = v50;
        CWwanTranslator::SafelyNotify(this, v50);
        v21 = v51;
        if ( v51 )
        {
          v22 = v50;
          goto LABEL_39;
        }
      }
      else
      {
LABEL_30:
        *(_OWORD *)v39 = 0;
        v40 = 0;
        *(_OWORD *)v41 = 0;
        v42 = 0;
        std::vector<unsigned short>::resize(v39);
        std::vector<unsigned short>::resize(v41);
        StringCchPrintfW(
          v39[0],
          v39[1] - v39[0],
          L"WwanSvc returns no valid roaming profile types. dwNumberOfItems is %d",
          *(unsigned int *)a3,
          &v43,
          &v36,
          0,
          0);
        v35[0] = 2619;
        StringCchPrintfW(
          v41[0],
          v41[1] - v41[0],
          L"%S(%d):%s",
          "CWwanTranslator::_ProcessRoamingPolicyChange",
          *(_QWORD *)v35,
          v39[0]);
        v26 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v26 > 3u )
        {
          v44 = v41[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v26,
            (__int64)word_18007693A,
            v27,
            v28,
            (const unsigned __int16 **)&v44);
        }
        std::vector<unsigned short>::~vector<unsigned short>((char **)v41);
        std::vector<unsigned short>::~vector<unsigned short>((char **)v39);
      }
    }
    else
    {
      v52[0] = off_18005EDC8;
      v52[1] = this;
      v52[2] = a2;
      v53 = v52;
      CWwanTranslator::SafelyNotify(this, v52);
      v21 = v53;
      if ( v53 )
      {
        v22 = v52;
LABEL_39:
        LOBYTE(v22) = v21 != v22;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v21 + 32LL))(v21, v22);
      }
    }
    *(_OWORD *)v39 = 0;
    v40 = 0;
    *(_OWORD *)v41 = 0;
    v42 = 0;
    std::vector<unsigned short>::resize(v39);
    std::vector<unsigned short>::resize(v41);
    StringCchPrintfW(v39[0], v39[1] - v39[0], L"Exit");
    LODWORD(v33) = 2630;
    StringCchPrintfW(v41[0], v41[1] - v41[0], L"%S(%d):%s", "CWwanTranslator::_ProcessRoamingPolicyChange", v33, v39[0]);
    v29 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v29 > 5u )
    {
      v44 = v41[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v29,
        (__int64)byte_1800768D3,
        v30,
        v31,
        (const unsigned __int16 **)&v44);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v41);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v39);
    if ( v36 )
      WwanFreeMemory(v36);
    WwanCloseHandle(v38, 0);
    return 0;
  }
  v14 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0xA01,
          (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
          (const char *)Interface,
          (unsigned int)&v43);
LABEL_34:
  if ( v36 )
    WwanFreeMemory(v36);
LABEL_36:
  WwanCloseHandle(v38, 0);
  return v14;
}

```

## disassembly

```asm
0x1800431f0  mov     [rsp-8+arg_18], rbx
0x1800431f5  push    rbp
0x1800431f6  push    rsi
0x1800431f7  push    rdi
0x1800431f8  push    r12
0x1800431fa  push    r13
0x1800431fc  push    r14
0x1800431fe  push    r15
0x180043200  lea     rbp, [rsp-60h]
0x180043205  sub     rsp, 160h
0x18004320c  mov     rax, cs:__security_cookie
0x180043213  xor     rax, rsp
0x180043216  mov     [rbp+90h+var_40], rax
0x18004321a  mov     ebx, r9d
0x18004321d  mov     rdi, r8
0x180043220  mov     r14, rdx
0x180043223  mov     rsi, rcx
0x180043226  xorps   xmm0, xmm0
0x180043229  movdqu  xmmword ptr [rbp+90h+var_F0], xmm0
0x18004322e  xor     r13d, r13d
0x180043231  mov     [rbp+90h+var_E0], r13
0x180043235  movdqu  xmmword ptr [rbp+90h+var_D8], xmm0
0x18004323a  mov     [rbp+90h+var_C8], r13
0x18004323e  lea     rcx, [rbp+90h+var_F0]
0x180043242  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180043247  lea     rcx, [rbp+90h+var_D8]
0x18004324b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180043250  mov     rdx, [rbp+90h+var_F0+8]
0x180043254  mov     rcx, [rbp+90h+var_F0]; unsigned __int16 *
0x180043258  sub     rdx, rcx
0x18004325b  sar     rdx, 1; unsigned __int64
0x18004325e  lea     r8, aEnter; "Enter"
0x180043265  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004326a  mov     rdx, [rbp+90h+var_D8+8]
0x18004326e  mov     rcx, [rbp+90h+var_D8]; unsigned __int16 *
0x180043272  sub     rdx, rcx
0x180043275  sar     rdx, 1; unsigned __int64
0x180043278  mov     rax, [rbp+90h+var_F0]
0x18004327c  mov     [rsp+190h+var_168], rax
0x180043281  mov     [rsp+190h+var_170], 9F2h
0x180043289  lea     r9, aCwwantranslato_54; "CWwanTranslator::_ProcessRoamingPolicyC"...
0x180043290  lea     r8, aSDS; "%S(%d):%s"
0x180043297  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004329c  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800432a1  mov     ecx, [rax]
0x1800432a3  cmp     ecx, 5
0x1800432a6  jbe     short loc_1800432CB
0x1800432a8  mov     rcx, [rbp+90h+var_D8]
0x1800432ac  mov     qword ptr [rsp+190h+var_148], rcx
0x1800432b1  lea     rcx, [rsp+190h+var_148]
0x1800432b6  mov     qword ptr [rsp+190h+var_170], rcx; unsigned int
0x1800432bb  lea     rdx, byte_18007695D
0x1800432c2  mov     rcx, rax
0x1800432c5  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800432ca  nop
0x1800432cb  lea     rcx, [rbp+90h+var_D8]
0x1800432cf  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800432d4  nop
0x1800432d5  lea     rcx, [rbp+90h+var_F0]
0x1800432d9  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800432de  mov     [rsp+190h+var_140], r13
0x1800432e3  mov     [rbp+90h+var_F8], r13d
0x1800432e7  lea     r9, [rsp+190h+var_140]
0x1800432ec  lea     r8, [rbp+90h+var_F8]
0x1800432f0  xor     edx, edx
0x1800432f2  lea     ecx, [rdx+1]
0x1800432f5  call    cs:__imp_WwanOpenHandle
0x1800432fb  test    eax, eax
0x1800432fd  jz      short loc_18004331F
0x1800432ff  mov     rcx, [rbp+98h]; this
0x180043306  mov     r9d, eax; char *
0x180043309  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180043310  mov     edx, 9F4h; void *
0x180043315  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004331a  jmp     loc_180043804
0x18004331f  lea     rax, [rsp+190h+var_140]
0x180043324  mov     [rbp+90h+var_F0], rax
0x180043328  mov     byte ptr [rbp+90h+var_F0+8], 1
0x18004332c  mov     [rbp+90h+var_108], r13d
0x180043330  mov     [rsp+190h+var_150], r13
0x180043335  lea     rax, [rsp+190h+var_150]
0x18004333a  mov     [rbp+90h+var_D8], rax
0x18004333e  mov     byte ptr [rbp+90h+var_D8+8], 1
0x180043342  mov     [rsp+190h+var_158], r13
0x180043347  mov     [rsp+190h+var_160], r13
0x18004334c  lea     rax, [rsp+190h+var_150]
0x180043351  mov     [rsp+190h+var_168], rax
0x180043356  lea     rax, [rbp+90h+var_108]
0x18004335a  mov     qword ptr [rsp+190h+var_170], rax; int
0x18004335f  xor     r9d, r9d
0x180043362  lea     r8d, [r9+1Ch]
0x180043366  mov     rdx, r14
0x180043369  mov     rcx, [rsp+190h+var_140]
0x18004336e  call    cs:__imp_WwanQueryInterface
0x180043374  test    eax, eax
0x180043376  jz      short loc_18004339A
0x180043378  mov     rcx, [rbp+98h]; this
0x18004337f  mov     r9d, eax; char *
0x180043382  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180043389  mov     edx, 0A01h; void *
0x18004338e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180043393  mov     ebx, eax
0x180043395  jmp     loc_180043673
0x18004339a  cmp     [rbp+90h+var_108], 4
0x18004339e  jnz     loc_1800437C2
0x1800433a4  mov     rax, [rsp+190h+var_150]
0x1800433a9  test    rax, rax
0x1800433ac  jz      loc_180043698
0x1800433b2  cmp     dword ptr [rax], 1
0x1800433b5  jnz     loc_180043698
0x1800433bb  mov     edx, [rdi]
0x1800433bd  lea     rax, [rdx+rdx*4]
0x1800433c1  lea     rcx, ds:4[rax*4]
0x1800433c9  cmp     rcx, rbx
0x1800433cc  jnz     loc_180043652
0x1800433d2  mov     [rsp+190h+var_148], r13d
0x1800433d7  mov     r9b, r13b
0x1800433da  mov     r8d, r13d
0x1800433dd  test    edx, edx
0x1800433df  jz      loc_18004358A
0x1800433e5  mov     r10, qword ptr cs:WWAN_PROFILE_SET_GUID_INTERNET_AO+8
0x1800433ec  mov     r12, qword ptr cs:WWAN_PROFILE_SET_GUID_INTERNET_AO
0x1800433f3  mov     r11, cs:qword_18006C008
0x1800433fa  mov     r15, cs:WWAN_PROFILE_SET_GUID_ALL_HOST_PROFILES
0x180043401  mov     eax, r8d
0x180043404  lea     rbx, [rax+rax*4]
0x180043408  cmp     r12, [rdi+rbx*4+4]
0x18004340d  jnz     short loc_180043416
0x18004340f  cmp     r10, [rdi+rbx*4+0Ch]
0x180043414  jz      short loc_180043424
0x180043416  cmp     r15, [rdi+rbx*4+4]
0x18004341b  jnz     short loc_180043452
0x18004341d  cmp     r11, [rdi+rbx*4+0Ch]
0x180043422  jnz     short loc_180043452
0x180043424  mov     r9b, 1
0x180043427  mov     ecx, [rdi+rbx*4+14h]
0x18004342b  test    ecx, ecx
0x18004342d  jz      short loc_18004344D
0x18004342f  sub     ecx, 1
0x180043432  jz      short loc_180043443
0x180043434  cmp     ecx, 1
0x180043437  jnz     short loc_1800434AA
0x180043439  mov     [rsp+190h+var_148], 2
0x180043441  jmp     short loc_180043452
0x180043443  mov     [rsp+190h+var_148], 1
0x18004344b  jmp     short loc_180043452
0x18004344d  mov     [rsp+190h+var_148], r13d
0x180043452  inc     r8d
0x180043455  cmp     r8d, edx
0x180043458  jb      short loc_180043401
0x18004345a  test    r9b, r9b
0x18004345d  jz      loc_18004358A
0x180043463  lea     rax, off_18005ED98
0x18004346a  mov     [rbp+90h+var_C0], rax
0x18004346e  mov     [rbp+90h+var_B8], rsi
0x180043472  mov     [rbp+90h+var_B0], r14
0x180043476  lea     rax, [rsp+190h+var_148]
0x18004347b  mov     [rbp+90h+var_A8], rax
0x18004347f  lea     rax, [rbp+90h+var_C0]
0x180043483  mov     [rbp+90h+var_88], rax
0x180043487  lea     rdx, [rbp+90h+var_C0]
0x18004348b  mov     rcx, rsi
0x18004348e  call    ?SafelyNotify@CWwanTranslator@@AEAAJ$$QEAV?$function@$$A6AXXZ@std@@@Z; CWwanTranslator::SafelyNotify(std::function<void (void)> &&)
0x180043493  nop
0x180043494  mov     rcx, [rbp+90h+var_88]
0x180043498  test    rcx, rcx
0x18004349b  jz      loc_1800436DF
0x1800434a1  lea     rdx, [rbp+90h+var_C0]
0x1800434a5  jmp     loc_1800436CD
0x1800434aa  xorps   xmm0, xmm0
0x1800434ad  movdqu  xmmword ptr [rsp+190h+var_120], xmm0
0x1800434b3  mov     [rbp+90h+var_110], r13
0x1800434b7  movdqu  xmmword ptr [rsp+190h+var_138], xmm0
0x1800434bd  mov     [rsp+190h+var_128], r13
0x1800434c2  lea     rcx, [rsp+190h+var_120]
0x1800434c7  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800434cc  lea     rcx, [rsp+190h+var_138]
0x1800434d1  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800434d6  mov     rdx, [rsp+190h+var_120+8]
0x1800434db  mov     rcx, [rsp+190h+var_120]; unsigned __int16 *
0x1800434e0  sub     rdx, rcx
0x1800434e3  sar     rdx, 1; unsigned __int64
0x1800434e6  mov     r9d, [rdi+rbx*4+14h]
0x1800434eb  lea     r8, aWwansvcReturns; "WwanSvc returns invalid Internet roamCo"...
0x1800434f2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800434f7  mov     rdx, [rsp+190h+var_138+8]
0x1800434fc  mov     rcx, [rsp+190h+var_138]; unsigned __int16 *
0x180043501  sub     rdx, rcx
0x180043504  sar     rdx, 1; unsigned __int64
0x180043507  mov     rax, [rsp+190h+var_120]
0x18004350c  mov     [rsp+190h+var_168], rax
0x180043511  mov     [rsp+190h+var_170], 0A2Bh
0x180043519  lea     r9, aCwwantranslato_54; "CWwanTranslator::_ProcessRoamingPolicyC"...
0x180043520  lea     r8, aSDS; "%S(%d):%s"
0x180043527  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004352c  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180043531  mov     ecx, [rax]
0x180043533  cmp     ecx, 2
0x180043536  jbe     short loc_18004355A
0x180043538  mov     rcx, [rsp+190h+var_138]
0x18004353d  mov     [rbp+90h+var_100], rcx
0x180043541  lea     rcx, [rbp+90h+var_100]
0x180043545  mov     qword ptr [rsp+190h+var_170], rcx
0x18004354a  lea     rdx, byte_180076919
0x180043551  mov     rcx, rax
0x180043554  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180043559  nop
0x18004355a  lea     rcx, [rsp+190h+var_138]
0x18004355f  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180043564  nop
0x180043565  lea     rcx, [rsp+190h+var_120]
0x18004356a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004356f  nop
0x180043570  mov     rcx, [rsp+190h+var_150]
0x180043575  test    rcx, rcx
0x180043578  jz      short loc_180043580
0x18004357a  call    cs:__imp_WwanFreeMemory
0x180043580  mov     ebx, 80004005h
0x180043585  jmp     loc_180043684
0x18004358a  xorps   xmm0, xmm0
0x18004358d  movdqu  xmmword ptr [rsp+190h+var_138], xmm0
0x180043593  mov     [rsp+190h+var_128], r13
0x180043598  movdqu  xmmword ptr [rsp+190h+var_120], xmm0
0x18004359e  mov     [rbp+90h+var_110], r13
0x1800435a2  lea     rcx, [rsp+190h+var_138]
0x1800435a7  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800435ac  lea     rcx, [rsp+190h+var_120]
0x1800435b1  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800435b6  mov     rdx, [rsp+190h+var_138+8]
0x1800435bb  mov     rcx, [rsp+190h+var_138]; unsigned __int16 *
0x1800435c0  sub     rdx, rcx
0x1800435c3  sar     rdx, 1; unsigned __int64
0x1800435c6  mov     r9d, [rdi]
0x1800435c9  lea     r8, aWwansvcReturns_0; "WwanSvc returns no valid roaming profil"...
0x1800435d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800435d5  mov     rdx, [rsp+190h+var_120+8]
0x1800435da  mov     rcx, [rsp+190h+var_120]; unsigned __int16 *
0x1800435df  sub     rdx, rcx
0x1800435e2  sar     rdx, 1; unsigned __int64
0x1800435e5  mov     rax, [rsp+190h+var_138]
0x1800435ea  mov     [rsp+190h+var_168], rax
0x1800435ef  mov     [rsp+190h+var_170], 0A3Bh
0x1800435f7  lea     r9, aCwwantranslato_54; "CWwanTranslator::_ProcessRoamingPolicyC"...
0x1800435fe  lea     r8, aSDS; "%S(%d):%s"
0x180043605  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004360a  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004360f  mov     ecx, [rax]
0x180043611  cmp     ecx, 3
0x180043614  jbe     short loc_180043638
0x180043616  mov     rcx, [rsp+190h+var_120]
0x18004361b  mov     [rbp+90h+var_100], rcx
0x18004361f  lea     rcx, [rbp+90h+var_100]
0x180043623  mov     qword ptr [rsp+190h+var_170], rcx
0x180043628  lea     rdx, word_18007693A
0x18004362f  mov     rcx, rax
0x180043632  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180043637  nop
0x180043638  lea     rcx, [rsp+190h+var_120]
0x18004363d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180043642  nop
0x180043643  lea     rcx, [rsp+190h+var_138]
0x180043648  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004364d  jmp     loc_1800436DF
0x180043652  mov     rcx, [rbp+98h]; this
0x180043659  mov     ebx, 8007000Eh
0x18004365e  mov     r9d, ebx; char *
0x180043661  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180043668  mov     edx, 0A12h; void *
0x18004366d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043672  nop
0x180043673  mov     rcx, [rsp+190h+var_150]
0x180043678  test    rcx, rcx
0x18004367b  jz      short loc_180043684
0x18004367d  call    cs:__imp_WwanFreeMemory
0x180043683  nop
0x180043684  xor     edx, edx
0x180043686  mov     rcx, [rsp+190h+var_140]
0x18004368b  call    cs:__imp_WwanCloseHandle
0x180043691  mov     eax, ebx
0x180043693  jmp     loc_180043804
0x180043698  lea     rax, off_18005EDC8
0x18004369f  mov     [rbp+90h+var_80], rax
0x1800436a3  mov     [rbp+90h+var_78], rsi
0x1800436a7  mov     [rbp+90h+var_70], r14
0x1800436ab  lea     rax, [rbp+90h+var_80]
0x1800436af  mov     [rbp+90h+var_48], rax
0x1800436b3  lea     rdx, [rbp+90h+var_80]
0x1800436b7  mov     rcx, rsi
0x1800436ba  call    ?SafelyNotify@CWwanTranslator@@AEAAJ$$QEAV?$function@$$A6AXXZ@std@@@Z; CWwanTranslator::SafelyNotify(std::function<void (void)> &&)
0x1800436bf  nop
0x1800436c0  mov     rcx, [rbp+90h+var_48]
0x1800436c4  test    rcx, rcx
0x1800436c7  jz      short loc_1800436DF
0x1800436c9  lea     rdx, [rbp+90h+var_80]
0x1800436cd  cmp     rcx, rdx
0x1800436d0  mov     rax, [rcx]
0x1800436d3  setnz   dl
0x1800436d6  mov     rax, [rax+20h]
0x1800436da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436df  xorps   xmm0, xmm0
  ... truncated ...
```
