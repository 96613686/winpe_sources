# CSessionBaseRW::Initialize(IFhConfigMgrPriv *,IFhCatalog *)

- ea: `0x18000eed8`
- end: `0x18000f555`
- name: `?Initialize@CSessionBaseRW@@IEAAJPEAUIFhConfigMgrPriv@@PEAUIFhCatalog@@@Z`
- size: `1661`
- prototype: `__int64 __fastcall(CSessionBaseRW *this, struct IUnknown *, struct IUnknown *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019dd0`
- `0x1800235e0`

## callees

- `0x180007818`
- `0x1800093a8`
- `0x1800094ec`
- `0x18000ac60`
- `0x18000d348`
- `0x18000e078`
- `0x18000eed8`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000eff7`
- `KERNEL32!GetLastError` at `0x18000eff7`
- `KERNEL32!PowerCreateRequest` at `0x18000ef3b`
- `KERNEL32!PowerCreateRequest` at `0x18000ef3b`
- `KERNEL32!CreateEventW` at `0x18000efe5`
- `KERNEL32!CreateEventW` at `0x18000efe5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f094`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f114`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f194`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f209`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f285`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f30c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f094`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f114`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f194`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f209`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f285`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f30c`

## string_xrefs

- `0x18000f1c9`: `RetentionIncomplete`

## pseudocode

```c
__int64 __fastcall CSessionBaseRW::Initialize(CSessionBaseRW *this, struct IUnknown *a2, struct IUnknown *a3)
{
  CSessionBaseRW *v5; // r14
  HANDLE v6; // rax
  _QWORD *v7; // r13
  int NewBackupSet; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  int v12; // r12d
  HANDLE EventW; // rax
  signed int LastError; // eax
  __int64 v15; // r9
  __int64 v16; // rbx
  _QWORD *v17; // rax
  __int64 v18; // rbx
  _QWORD *v19; // rax
  __int64 v20; // rbx
  _QWORD *v21; // rax
  __int64 v22; // rbx
  _QWORD *v23; // rax
  __int64 v24; // rbx
  _QWORD *v25; // rax
  __int64 v26; // rbx
  _QWORD *v27; // rax
  int v28; // eax
  int v29; // eax
  BSTR v31; // [rsp+30h] [rbp-78h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-70h] BYREF
  int v33; // [rsp+40h] [rbp-68h]
  unsigned __int64 v34; // [rsp+48h] [rbp-60h] BYREF
  int v35; // [rsp+50h] [rbp-58h] BYREF
  _QWORD *v36; // [rsp+58h] [rbp-50h]
  struct _REASON_CONTEXT v37; // [rsp+60h] [rbp-48h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp+8h] BYREF
  int v39; // [rsp+C8h] [rbp+20h] BYREF

  SystemTimeAsFileTime = (struct _FILETIME)this;
  v5 = this;
  v34 = 0;
  v39 = 0;
  v37.Version = 0;
  v37.Flags = 2;
  v37.Reason.Detailed.LocalizedReasonModule = g_hInstance;
  *(_OWORD *)(&v37.Reason.SimpleReasonString + 1) = 0xC8u;
  v6 = PowerCreateRequest(&v37);
  *((_QWORD *)v5 + 34) = v6;
  if ( v6 == (HANDLE)-1LL && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
      "m_PowerRequest != INVALID_HANDLE_VALUE");
  v7 = (_QWORD *)((char *)v5 + 8);
  v36 = (_QWORD *)((char *)v5 + 8);
  NewBackupSet = CSessionBaseRO::Initialize((OLECHAR *)v5 + 4, a2, a3);
  v9 = NewBackupSet;
  if ( NewBackupSet < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 12;
LABEL_67:
      v15 = (unsigned int)NewBackupSet;
      goto LABEL_68;
    }
    return v9;
  }
  v12 = 0;
  v33 = 0;
  EventW = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)v5 + 20) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 13;
      v15 = v9;
LABEL_68:
      WPP_SF_d(v10[2], v11, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v15);
      return v9;
    }
    return v9;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v39 = 8;
    v16 = *((_QWORD *)v5 + 2);
    v31 = *(BSTR *)(*(_QWORD *)v16 + 176LL);
    v17 = (_QWORD *)((_QWORD (__stdcall *)(ATL::CComBSTR *, const unsigned __int16 *))ATL::CComBSTR::CComBSTR)(
                      (ATL::CComBSTR *)&bstrString,
                      L"TotalBytesInStaging");
    LODWORD(v16) = ((__int64 (__fastcall *)(__int64, _QWORD, char *, __int64, int *))v31)(
                     v16,
                     *v17,
                     (char *)v5 + 168,
                     8,
                     &v39);
    SysFreeString(bstrString);
    if ( (int)v16 < 0 || v39 != 8 )
      *((_QWORD *)v5 + 21) = 0;
    v39 = 8;
    v18 = *((_QWORD *)v5 + 2);
    bstrString = *(BSTR *)(*(_QWORD *)v18 + 176LL);
    v19 = (_QWORD *)((_QWORD (__stdcall *)(ATL::CComBSTR *, const unsigned __int16 *))ATL::CComBSTR::CComBSTR)(
                      (ATL::CComBSTR *)&v31,
                      L"TotalBytesOnDefaultTarget");
    LODWORD(v18) = ((__int64 (__fastcall *)(__int64, _QWORD, char *, __int64, int *))bstrString)(
                     v18,
                     *v19,
                     (char *)v5 + 176,
                     8,
                     &v39);
    SysFreeString(v31);
    if ( (int)v18 < 0 || v39 != 8 )
      *((_QWORD *)v5 + 22) = 0;
    v39 = 4;
    v20 = *((_QWORD *)v5 + 2);
    bstrString = *(BSTR *)(*(_QWORD *)v20 + 176LL);
    v21 = (_QWORD *)((_QWORD (__stdcall *)(ATL::CComBSTR *, const unsigned __int16 *))ATL::CComBSTR::CComBSTR)(
                      (ATL::CComBSTR *)&v31,
                      L"OldestPresentBSet");
    LODWORD(v20) = ((__int64 (__fastcall *)(__int64, _QWORD, char *, __int64, int *))bstrString)(
                     v20,
                     *v21,
                     (char *)v5 + 184,
                     4,
                     &v39);
    SysFreeString(v31);
    if ( (int)v20 < 0 || v39 != 4 )
      *((_DWORD *)v5 + 46) = 1;
    v39 = 1;
    v22 = *((_QWORD *)v5 + 2);
    bstrString = *(BSTR *)(*(_QWORD *)v22 + 176LL);
    v23 = (_QWORD *)((_QWORD (__stdcall *)(ATL::CComBSTR *, const unsigned __int16 *))ATL::CComBSTR::CComBSTR)(
                      (ATL::CComBSTR *)&v31,
                      L"RetentionIncomplete");
    LODWORD(v22) = ((__int64 (__fastcall *)(__int64, _QWORD, char *, __int64, int *))bstrString)(
                     v22,
                     *v23,
                     (char *)v5 + 188,
                     1,
                     &v39);
    SysFreeString(v31);
    if ( (int)v22 < 0 || v39 != 1 )
      *((_BYTE *)v5 + 188) = 0;
    v39 = 4;
    v24 = *((_QWORD *)v5 + 2);
    bstrString = *(BSTR *)(*(_QWORD *)v24 + 176LL);
    v25 = (_QWORD *)((_QWORD (__stdcall *)(ATL::CComBSTR *, const unsigned __int16 *))ATL::CComBSTR::CComBSTR)(
                      (ATL::CComBSTR *)&v31,
                      L"LastCatalogBackup");
    LODWORD(v24) = ((__int64 (__fastcall *)(__int64, _QWORD, char *, __int64, int *))bstrString)(
                     v24,
                     *v25,
                     (char *)v5 + 192,
                     4,
                     &v39);
    SysFreeString(v31);
    if ( (int)v24 < 0 || v39 != 4 )
    {
      v12 = 1;
      v33 = 1;
      *((_DWORD *)v5 + 48) = 0;
    }
    v39 = 8;
    v26 = *((_QWORD *)v5 + 2);
    bstrString = *(BSTR *)(*(_QWORD *)v26 + 176LL);
    v27 = (_QWORD *)((_QWORD (__stdcall *)(ATL::CComBSTR *, const unsigned __int16 *))ATL::CComBSTR::CComBSTR)(
                      (ATL::CComBSTR *)&v31,
                      L"LastCatalogBackupTime");
    LODWORD(v26) = ((__int64 (__fastcall *)(__int64, _QWORD, char *, __int64, int *))bstrString)(
                     v26,
                     *v27,
                     (char *)v5 + 200,
                     8,
                     &v39);
    SysFreeString(v31);
    if ( (int)v26 < 0 || v39 != 8 )
    {
      v12 = 1;
      v33 = 1;
      *((_QWORD *)v5 + 25) = 0;
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v35) )
    {
      LODWORD(v31) = v35;
      if ( v35 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            (unsigned int)v35);
        v9 = (unsigned int)v31;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000F334);
        return v9;
      }
      v5 = (CSessionBaseRW *)SystemTimeAsFileTime;
      v12 = v33;
      v7 = v36;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000F33D);
    }
  }
  NewBackupSet = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v7 + 64LL))(*v7, 3, (char *)v5 + 208);
  v9 = NewBackupSet;
  if ( NewBackupSet >= 0 )
  {
    NewBackupSet = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v7 + 64LL))(
                     *v7,
                     4,
                     (char *)v5 + 216);
    v9 = NewBackupSet;
    if ( NewBackupSet < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 16;
        goto LABEL_67;
      }
      return v9;
    }
    NewBackupSet = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int64 *))(*(_QWORD *)*v7 + 64LL))(
                     *v7,
                     1,
                     &v34);
    v9 = NewBackupSet;
    if ( NewBackupSet < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 17;
        goto LABEL_67;
      }
      return v9;
    }
    if ( v34 )
    {
      if ( v34 == 1 )
      {
        v28 = 0;
        goto LABEL_58;
      }
      if ( v34 == 2 )
      {
        NewBackupSet = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int64 *))(*(_QWORD *)*v7 + 64LL))(
                         *v7,
                         2,
                         &v34);
        v9 = NewBackupSet;
        if ( NewBackupSet < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 18;
            goto LABEL_67;
          }
          return v9;
        }
        v28 = -1;
        if ( v34 <= 0xFFFFFFFF )
          v28 = v34;
LABEL_58:
        *((_DWORD *)v5 + 56) = v28;
        if ( v12 )
        {
          SystemTimeAsFileTime.dwLowDateTime = 0;
          v29 = CSessionBaseRW::FlushAndBackupCatalog(v5, 1, 0, (int *)v5 + 38, (struct _FILETIME)&SystemTimeAsFileTime);
          if ( v29 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19,
              &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
              (unsigned int)v29);
        }
        NewBackupSet = CSessionBaseRW::CreateNewBackupSet(v5);
        v9 = NewBackupSet;
        if ( NewBackupSet < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 20;
            goto LABEL_67;
          }
        }
        return v9;
      }
    }
    v28 = -1;
    goto LABEL_58;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 15;
    goto LABEL_67;
  }
  return v9;
}

```

## disassembly

```asm
0x18000eed8  mov     r11, rsp
0x18000eedb  mov     [r11+10h], rbx
0x18000eedf  mov     [r11+8], rcx
0x18000eee3  push    rsi
0x18000eee4  push    r12
0x18000eee6  push    r13
0x18000eee8  push    r14
0x18000eeea  push    r15
0x18000eeec  sub     rsp, 80h
0x18000eef3  mov     rbx, r8
0x18000eef6  mov     rsi, rdx
0x18000eef9  mov     r14, rcx
0x18000eefc  mov     qword ptr [r11-60h], 0
0x18000ef04  mov     dword ptr [r11+20h], 0
0x18000ef0c  mov     [rsp+0A8h+var_48], 0
0x18000ef14  mov     [rsp+0A8h+var_44], 2
0x18000ef1c  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18000ef23  mov     [r11-40h], rax
0x18000ef27  mov     qword ptr [r11-38h], 0C8h
0x18000ef2f  mov     qword ptr [r11-30h], 0
0x18000ef37  lea     rcx, [r11-48h]; Context
0x18000ef3b  call    cs:__imp_PowerCreateRequest
0x18000ef41  mov     [r14+110h], rax
0x18000ef48  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ef4c  jnz     short loc_18000EF83
0x18000ef4e  lea     r15, WPP_GLOBAL_Control
0x18000ef55  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef5c  cmp     rcx, r15
0x18000ef5f  jz      short loc_18000EF8A
0x18000ef61  test    byte ptr [rcx+1Ch], 4
0x18000ef65  jz      short loc_18000EF8A
0x18000ef67  lea     edx, [rax+0Ch]
0x18000ef6a  lea     r9, aMPowerrequestI; "m_PowerRequest != INVALID_HANDLE_VALUE"
0x18000ef71  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000ef78  mov     rcx, [rcx+10h]
0x18000ef7c  call    WPP_SF_s
0x18000ef81  jmp     short loc_18000EF8A
0x18000ef83  lea     r15, WPP_GLOBAL_Control
0x18000ef8a  lea     r13, [r14+8]
0x18000ef8e  mov     [rsp+0A8h+var_50], r13
0x18000ef93  mov     r8, rbx; struct IFhCatalog *
0x18000ef96  mov     rdx, rsi; struct IFhConfigMgrPriv *
0x18000ef99  mov     rcx, r13; this
0x18000ef9c  call    ?Initialize@CSessionBaseRO@@IEAAJPEAUIFhConfigMgrPriv@@PEAUIFhCatalog@@@Z; CSessionBaseRO::Initialize(IFhConfigMgrPriv *,IFhCatalog *)
0x18000efa1  mov     ebx, eax
0x18000efa3  test    eax, eax
0x18000efa5  jns     short loc_18000EFCE
0x18000efa7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efae  cmp     rcx, r15
0x18000efb1  jz      loc_18000F53A
0x18000efb7  mov     esi, 1
0x18000efbc  test    [rcx+1Ch], sil
0x18000efc0  jz      loc_18000F53A
0x18000efc6  lea     edx, [rsi+0Bh]
0x18000efc9  jmp     loc_18000F527
0x18000efce  xor     r12d, r12d
0x18000efd1  mov     [rsp+0A8h+var_68], r12d
0x18000efd6  xor     r9d, r9d; lpName
0x18000efd9  lea     esi, [r12+1]
0x18000efde  mov     r8d, esi; bInitialState
0x18000efe1  mov     edx, esi; bManualReset
0x18000efe3  xor     ecx, ecx; lpEventAttributes
0x18000efe5  call    cs:__imp_CreateEventW
0x18000efeb  mov     [r14+0A0h], rax
0x18000eff2  test    rax, rax
0x18000eff5  jnz     short loc_18000F033
0x18000eff7  call    cs:__imp_GetLastError
0x18000effd  mov     ebx, eax
0x18000efff  test    eax, eax
0x18000f001  jle     short loc_18000F00C
0x18000f003  movzx   ebx, ax
0x18000f006  or      ebx, 80070000h
0x18000f00c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f013  cmp     rcx, r15
0x18000f016  jz      loc_18000F53A
0x18000f01c  test    [rcx+1Ch], sil
0x18000f020  jz      loc_18000F53A
0x18000f026  mov     edx, 0Dh
0x18000f02b  mov     r9d, ebx
0x18000f02e  jmp     loc_18000F52A
0x18000f033  mov     [rsp+0A8h+arg_18], 8
0x18000f03e  mov     rbx, [r14+10h]
0x18000f042  mov     rax, [rbx]
0x18000f045  mov     rax, [rax+0B0h]
0x18000f04c  mov     [rsp+0A8h+var_78], rax
0x18000f051  lea     rdx, aTotalbytesinst; "TotalBytesInStaging"
0x18000f058  lea     rcx, [rsp+0A8h+bstrString]; this
0x18000f05d  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000f062  nop
0x18000f063  lea     r8, [r14+0A8h]
0x18000f06a  lea     rcx, [rsp+0A8h+arg_18]
0x18000f072  mov     qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18000f077  mov     r9d, 8
0x18000f07d  mov     rdx, [rax]
0x18000f080  mov     rcx, rbx
0x18000f083  mov     rax, [rsp+0A8h+var_78]
0x18000f088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f08d  mov     ebx, eax
0x18000f08f  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x18000f094  call    cs:__imp_SysFreeString
0x18000f09a  test    ebx, ebx
0x18000f09c  js      short loc_18000F0A8
0x18000f09e  cmp     [rsp+0A8h+arg_18], 8
0x18000f0a6  jz      short loc_18000F0B3
0x18000f0a8  mov     qword ptr [r14+0A8h], 0
0x18000f0b3  mov     [rsp+0A8h+arg_18], 8
0x18000f0be  mov     rbx, [r14+10h]
0x18000f0c2  mov     rax, [rbx]
0x18000f0c5  mov     rax, [rax+0B0h]
0x18000f0cc  mov     [rsp+0A8h+bstrString], rax
0x18000f0d1  lea     rdx, aTotalbytesonde; "TotalBytesOnDefaultTarget"
0x18000f0d8  lea     rcx, [rsp+0A8h+var_78]; this
0x18000f0dd  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000f0e2  nop
0x18000f0e3  lea     r8, [r14+0B0h]
0x18000f0ea  lea     rcx, [rsp+0A8h+arg_18]
0x18000f0f2  mov     qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18000f0f7  mov     r9d, 8
0x18000f0fd  mov     rdx, [rax]
0x18000f100  mov     rcx, rbx
0x18000f103  mov     rax, [rsp+0A8h+bstrString]
0x18000f108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f10d  mov     ebx, eax
0x18000f10f  mov     rcx, [rsp+0A8h+var_78]; bstrString
0x18000f114  call    cs:__imp_SysFreeString
0x18000f11a  test    ebx, ebx
0x18000f11c  js      short loc_18000F128
0x18000f11e  cmp     [rsp+0A8h+arg_18], 8
0x18000f126  jz      short loc_18000F133
0x18000f128  mov     qword ptr [r14+0B0h], 0
0x18000f133  mov     [rsp+0A8h+arg_18], 4
0x18000f13e  mov     rbx, [r14+10h]
0x18000f142  mov     rax, [rbx]
0x18000f145  mov     rax, [rax+0B0h]
0x18000f14c  mov     [rsp+0A8h+bstrString], rax
0x18000f151  lea     rdx, aOldestpresentb; "OldestPresentBSet"
0x18000f158  lea     rcx, [rsp+0A8h+var_78]; this
0x18000f15d  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000f162  nop
0x18000f163  lea     r8, [r14+0B8h]
0x18000f16a  lea     rcx, [rsp+0A8h+arg_18]
0x18000f172  mov     qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18000f177  mov     r9d, 4
0x18000f17d  mov     rdx, [rax]
0x18000f180  mov     rcx, rbx
0x18000f183  mov     rax, [rsp+0A8h+bstrString]
0x18000f188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f18d  mov     ebx, eax
0x18000f18f  mov     rcx, [rsp+0A8h+var_78]; bstrString
0x18000f194  call    cs:__imp_SysFreeString
0x18000f19a  test    ebx, ebx
0x18000f19c  js      short loc_18000F1A8
0x18000f19e  cmp     [rsp+0A8h+arg_18], 4
0x18000f1a6  jz      short loc_18000F1AF
0x18000f1a8  mov     [r14+0B8h], esi
0x18000f1af  mov     [rsp+0A8h+arg_18], esi
0x18000f1b6  mov     rbx, [r14+10h]
0x18000f1ba  mov     rax, [rbx]
0x18000f1bd  mov     rax, [rax+0B0h]
0x18000f1c4  mov     [rsp+0A8h+bstrString], rax
0x18000f1c9  lea     rdx, aRetentionincom; "RetentionIncomplete"
0x18000f1d0  lea     rcx, [rsp+0A8h+var_78]; this
0x18000f1d5  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000f1da  nop
0x18000f1db  lea     r8, [r14+0BCh]
0x18000f1e2  lea     rcx, [rsp+0A8h+arg_18]
0x18000f1ea  mov     qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18000f1ef  mov     r9d, esi
0x18000f1f2  mov     rdx, [rax]
0x18000f1f5  mov     rcx, rbx
0x18000f1f8  mov     rax, [rsp+0A8h+bstrString]
0x18000f1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f202  mov     ebx, eax
0x18000f204  mov     rcx, [rsp+0A8h+var_78]; bstrString
0x18000f209  call    cs:__imp_SysFreeString
0x18000f20f  test    ebx, ebx
0x18000f211  js      short loc_18000F21C
0x18000f213  cmp     [rsp+0A8h+arg_18], esi
0x18000f21a  jz      short loc_18000F224
0x18000f21c  mov     byte ptr [r14+0BCh], 0
0x18000f224  mov     [rsp+0A8h+arg_18], 4
0x18000f22f  mov     rbx, [r14+10h]
0x18000f233  mov     rax, [rbx]
0x18000f236  mov     rax, [rax+0B0h]
0x18000f23d  mov     [rsp+0A8h+bstrString], rax
0x18000f242  lea     rdx, aLastcatalogbac; "LastCatalogBackup"
0x18000f249  lea     rcx, [rsp+0A8h+var_78]; this
0x18000f24e  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000f253  nop
0x18000f254  lea     r8, [r14+0C0h]
0x18000f25b  lea     rcx, [rsp+0A8h+arg_18]
0x18000f263  mov     qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18000f268  mov     r9d, 4
0x18000f26e  mov     rdx, [rax]
0x18000f271  mov     rcx, rbx
0x18000f274  mov     rax, [rsp+0A8h+bstrString]
0x18000f279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f27e  mov     ebx, eax
0x18000f280  mov     rcx, [rsp+0A8h+var_78]; bstrString
0x18000f285  call    cs:__imp_SysFreeString
0x18000f28b  test    ebx, ebx
0x18000f28d  js      short loc_18000F299
0x18000f28f  cmp     [rsp+0A8h+arg_18], 4
0x18000f297  jz      short loc_18000F2AB
0x18000f299  mov     r12d, esi
0x18000f29c  mov     [rsp+0A8h+var_68], esi
0x18000f2a0  mov     dword ptr [r14+0C0h], 0
0x18000f2ab  mov     [rsp+0A8h+arg_18], 8
0x18000f2b6  mov     rbx, [r14+10h]
0x18000f2ba  mov     rax, [rbx]
0x18000f2bd  mov     rax, [rax+0B0h]
0x18000f2c4  mov     [rsp+0A8h+bstrString], rax
0x18000f2c9  lea     rdx, aLastcatalogbac_0; "LastCatalogBackupTime"
0x18000f2d0  lea     rcx, [rsp+0A8h+var_78]; this
0x18000f2d5  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000f2da  nop
0x18000f2db  lea     r8, [r14+0C8h]
0x18000f2e2  lea     rcx, [rsp+0A8h+arg_18]
0x18000f2ea  mov     qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18000f2ef  mov     r9d, 8
0x18000f2f5  mov     rdx, [rax]
0x18000f2f8  mov     rcx, rbx
0x18000f2fb  mov     rax, [rsp+0A8h+bstrString]
0x18000f300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f305  mov     ebx, eax
0x18000f307  mov     rcx, [rsp+0A8h+var_78]; bstrString
0x18000f30c  call    cs:__imp_SysFreeString
0x18000f312  test    ebx, ebx
0x18000f314  js      short loc_18000F320
0x18000f316  cmp     [rsp+0A8h+arg_18], 8
0x18000f31e  jz      short loc_18000F332
0x18000f320  mov     r12d, esi
0x18000f323  mov     [rsp+0A8h+var_68], esi
0x18000f327  mov     qword ptr [r14+0C8h], 0
0x18000f332  jmp     short loc_18000F35B
0x18000f334  mov     ebx, dword ptr [rsp+0A8h+var_78]
0x18000f338  jmp     loc_18000F53A
0x18000f33d  lea     r15, WPP_GLOBAL_Control
0x18000f344  mov     esi, 1
0x18000f349  mov     r14, qword ptr [rsp+0A8h+arg_0.dwLowDateTime]
0x18000f351  mov     r12d, [rsp+0A8h+var_68]
0x18000f356  mov     r13, [rsp+0A8h+var_50]
0x18000f35b  mov     rcx, [r13+0]
0x18000f35f  mov     rax, [rcx]
0x18000f362  lea     r8, [r14+0D0h]
0x18000f369  mov     edx, 3
0x18000f36e  mov     rax, [rax+40h]
0x18000f372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f377  mov     ebx, eax
0x18000f379  test    eax, eax
0x18000f37b  jns     short loc_18000F3A1
0x18000f37d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f384  cmp     rcx, r15
0x18000f387  jz      loc_18000F53A
0x18000f38d  test    [rcx+1Ch], sil
0x18000f391  jz      loc_18000F53A
0x18000f397  mov     edx, 0Fh
0x18000f39c  jmp     loc_18000F527
0x18000f3a1  mov     rcx, [r13+0]
0x18000f3a5  mov     rax, [rcx]
0x18000f3a8  lea     r8, [r14+0D8h]
0x18000f3af  mov     edx, 4
0x18000f3b4  mov     rax, [rax+40h]
0x18000f3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3bd  mov     ebx, eax
0x18000f3bf  test    eax, eax
0x18000f3c1  jns     short loc_18000F3E7
0x18000f3c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3ca  cmp     rcx, r15
0x18000f3cd  jz      loc_18000F53A
0x18000f3d3  test    [rcx+1Ch], sil
0x18000f3d7  jz      loc_18000F53A
0x18000f3dd  mov     edx, 10h
0x18000f3e2  jmp     loc_18000F527
0x18000f3e7  mov     rcx, [r13+0]
0x18000f3eb  mov     rax, [rcx]
0x18000f3ee  lea     r8, [rsp+0A8h+var_60]
0x18000f3f3  mov     edx, esi
0x18000f3f5  mov     rax, [rax+40h]
0x18000f3f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3fe  mov     ebx, eax
0x18000f400  test    eax, eax
0x18000f402  jns     short loc_18000F428
0x18000f404  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f40b  cmp     rcx, r15
0x18000f40e  jz      loc_18000F53A
0x18000f414  test    [rcx+1Ch], sil
0x18000f418  jz      loc_18000F53A
0x18000f41e  mov     edx, 11h
0x18000f423  jmp     loc_18000F527
0x18000f428  mov     rax, [rsp+0A8h+var_60]
0x18000f42d  test    rax, rax
0x18000f430  jz      short loc_18000F497
0x18000f432  sub     rax, 1
0x18000f436  jz      short loc_18000F493
0x18000f438  cmp     rax, 1
0x18000f43c  jnz     short loc_18000F497
0x18000f43e  mov     rcx, [r13+0]
0x18000f442  mov     rax, [rcx]
0x18000f445  lea     r8, [rsp+0A8h+var_60]
  ... truncated ...
```
