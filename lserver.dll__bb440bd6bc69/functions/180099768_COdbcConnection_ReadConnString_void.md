# COdbcConnection::ReadConnString(void)

- ea: `0x180099768`
- end: `0x180099eef`
- name: `?ReadConnString@COdbcConnection@@AEAAJXZ`
- size: `1927`
- prototype: `__int64 __fastcall(COdbcConnection *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180098b60`

## callees

- `0x18000cff0`
- `0x18001ad74`
- `0x180077e9c`
- `0x180078198`
- `0x180086574`
- `0x180088e68`
- `0x180098314`
- `0x1800983d0`
- `0x18009872c`
- `0x180099768`
- `0x18009f46c`
- `0x18009f51c`
- `0x18009f600`
- `0x18009fd9c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180099c21`
- `OLEAUT32!__imp_SysFreeString` at `0x180099dcd`
- `OLEAUT32!__imp_SysFreeString` at `0x180099eb8`
- `OLEAUT32!__imp_SysFreeString` at `0x180099ecd`
- `OLEAUT32!__imp_SysFreeString` at `0x180099c21`
- `OLEAUT32!__imp_SysFreeString` at `0x180099dcd`
- `OLEAUT32!__imp_SysFreeString` at `0x180099eb8`
- `OLEAUT32!__imp_SysFreeString` at `0x180099ecd`
- `KERNEL32!LeaveCriticalSection` at `0x180099b01`
- `KERNEL32!LeaveCriticalSection` at `0x180099b7d`
- `KERNEL32!LeaveCriticalSection` at `0x180099c06`
- `KERNEL32!LeaveCriticalSection` at `0x180099cb6`
- `KERNEL32!LeaveCriticalSection` at `0x180099dae`
- `KERNEL32!LeaveCriticalSection` at `0x180099dff`
- `KERNEL32!LeaveCriticalSection` at `0x180099b01`
- `KERNEL32!LeaveCriticalSection` at `0x180099b7d`
- `KERNEL32!LeaveCriticalSection` at `0x180099c06`
- `KERNEL32!LeaveCriticalSection` at `0x180099cb6`
- `KERNEL32!LeaveCriticalSection` at `0x180099dae`
- `KERNEL32!LeaveCriticalSection` at `0x180099dff`
- `KERNEL32!EnterCriticalSection` at `0x180099a0d`
- `KERNEL32!EnterCriticalSection` at `0x180099a0d`
- `KERNEL32!LocalAlloc` at `0x180099913`
- `KERNEL32!LocalAlloc` at `0x180099a91`
- `KERNEL32!LocalAlloc` at `0x180099c43`
- `KERNEL32!LocalAlloc` at `0x180099913`
- `KERNEL32!LocalAlloc` at `0x180099a91`
- `KERNEL32!LocalAlloc` at `0x180099c43`
- `KERNEL32!LocalFree` at `0x180099e8b`
- `KERNEL32!LocalFree` at `0x180099ea3`
- `KERNEL32!LocalFree` at `0x180099e8b`
- `KERNEL32!LocalFree` at `0x180099ea3`

## string_xrefs

- `0x180099a2e`: `{password_replaced}`
- `0x180099b98`: `System\CurrentControlSet\Services\Tssdis\Parameters\Secrets`
- `0x180099d40`: `System\CurrentControlSet\Services\Tssdis\Parameters\Secrets`
- `0x180099b5a`: `StringCchCopy regValue`
- `0x180099e0e`: `DRIVER=Windows Internal Database;SERVER=\\.\pipe\Microsoft##WID\tsql\query;Trusted_Connection=Yes;APP=Remote Desktop Services Connection Broker;DATABASE=RdCms;`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall COdbcConnection::ReadConnString(COdbcConnection *this, const unsigned __int16 *a2, HKEY a3, int a4)
{
  int DbConnectionStringWithPassword; // edi
  unsigned __int16 *v5; // r13
  BSTR *v6; // r12
  unsigned int v7; // eax
  bool v8; // sf
  unsigned int CurrentThreadActivityIdPrefix; // eax
  PVOID *v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned __int16 *v13; // rax
  bool v14; // sf
  unsigned int v15; // eax
  __int64 v16; // rax
  int v17; // ebx
  unsigned int v18; // eax
  unsigned __int16 *v19; // rax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned __int16 *v22; // rax
  unsigned __int16 *v23; // rbx
  bool v24; // sf
  unsigned int v25; // eax
  unsigned int v26; // eax
  OLECHAR *v27; // rcx
  BSTR v28; // rdx
  BSTR *v29; // rcx
  unsigned int v31; // [rsp+20h] [rbp-59h]
  BSTR v32; // [rsp+40h] [rbp-39h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-31h]
  HKEY phkResult; // [rsp+50h] [rbp-29h] BYREF
  int v35; // [rsp+58h] [rbp-21h]
  _BYTE v36[88]; // [rsp+78h] [rbp-1h] BYREF
  _RTL_CRITICAL_SECTION *v38; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned int v39; // [rsp+F0h] [rbp+77h] BYREF
  BSTR bstrString; // [rsp+F8h] [rbp+7Fh] BYREF

  DbConnectionStringWithPassword = 0;
  LODWORD(v38) = 1024;
  v39 = 1024;
  bstrString = 0;
  v32 = 0;
  v5 = 0;
  hMem = 0;
  v6 = (BSTR *)((char *)this + 80);
  if ( !*((_QWORD *)this + 10) )
  {
    CTSRegEntry::CTSRegEntry(&phkResult, a2, a3, a4, v31);
    DbConnectionStringWithPassword = v35;
    v8 = v35 < 0;
    if ( v35 > 0 )
    {
      DbConnectionStringWithPassword = (unsigned __int16)v35 | 0x80070000;
      v8 = 1;
    }
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)&WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"regConnStr",
          DbConnectionStringWithPassword);
      }
LABEL_13:
      CTSRegEntry::~CTSRegEntry((CTSRegEntry *)&phkResult);
      goto LABEL_102;
    }
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids, v11);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !COdbcConnection::m_sRegConnString )
    {
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 && *((_BYTE *)v10 + 25) >= 4u )
      {
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids, v12);
      }
      v13 = (unsigned __int16 *)LocalAlloc(0, 0x802u);
      COdbcConnection::m_sRegConnString = v13;
      if ( !v13 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DssD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"m_sRegConnString", (__int64)"m_sRegConnString", 14);
        }
        DbConnectionStringWithPassword = -2147024882;
        goto LABEL_13;
      }
      CTSRegEntry::GetString((CTSRegEntry *)&phkResult, L"DBConnString", v13, (unsigned int *)&v38);
      DbConnectionStringWithPassword = v35;
      v14 = v35 < 0;
      if ( v35 > 0 )
      {
        DbConnectionStringWithPassword = (unsigned __int16)v35 | 0x80070000;
        v14 = 1;
      }
      if ( v14 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v15 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids, v15);
        }
        DbConnectionStringWithPassword = 0;
      }
      else
      {
        COdbcConnection::m_sRegConnStringLen = (unsigned int)v38;
      }
    }
    if ( COdbcConnection::m_sRegConnStringLen <= 1 )
    {
      ATL::CComBSTR::operator=(
        v6,
        L"DRIVER=Windows Internal Database;SERVER=\\\\.\\pipe\\Microsoft##WID\\tsql\\query;Trusted_Connection=Yes;APP=Remo"
         "te Desktop Services Connection Broker;DATABASE=RdCms;");
LABEL_92:
      if ( !*v6 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DssD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"m_ConnString", (__int64)"m_ConnString", 14);
        }
        DbConnectionStringWithPassword = -2147024882;
      }
      goto LABEL_98;
    }
    v38 = &COdbcConnection::m_DecryptPswdLock;
    EnterCriticalSection(&COdbcConnection::m_DecryptPswdLock);
    v16 = CBaseStringT<unsigned short>::CBaseStringT<unsigned short>(v36, COdbcConnection::m_sRegConnString);
    v17 = CBaseStringT<unsigned short>::Contains(v16, L"{password_replaced}", 0);
    CBaseStringT<unsigned short>::~CBaseStringT<unsigned short>(v36);
    if ( v17 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids, v18);
      }
      v19 = (unsigned __int16 *)LocalAlloc(0, 0x802u);
      v5 = v19;
      if ( !v19 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DssD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"regConnStrValue", (__int64)"regConnStrValue", 14);
        }
        DbConnectionStringWithPassword = -2147024882;
        LeaveCriticalSection(&COdbcConnection::m_DecryptPswdLock);
        goto LABEL_13;
      }
      DbConnectionStringWithPassword = StringCchCopyW(v19, 0x400u, COdbcConnection::m_sRegConnString);
      if ( DbConnectionStringWithPassword < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v20 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            (unsigned int)&WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids,
            v20,
            (__int64)"StringCchCopy regValue",
            DbConnectionStringWithPassword);
        }
LABEL_55:
        LeaveCriticalSection(&COdbcConnection::m_DecryptPswdLock);
LABEL_98:
        CTSRegEntry::~CTSRegEntry((CTSRegEntry *)&phkResult);
        if ( v5 )
          LocalFree(v5);
        if ( hMem )
          LocalFree(hMem);
        goto LABEL_102;
      }
      DbConnectionStringWithPassword = RdCentralDbUtils::GetDbConnectionStringWithPassword(
                                         (wchar_t *)L"PrimaryConnectionString",
                                         0,
                                         v5,
                                         L"System\\CurrentControlSet\\Services\\Tssdis\\Parameters\\Secrets",
                                         &bstrString);
      if ( DbConnectionStringWithPassword < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            (unsigned int)&WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids,
            v21,
            (__int64)"RdCentralDbUtils::GetDbConnectionStringWithPassword",
            DbConnectionStringWithPassword);
        }
        goto LABEL_55;
      }
      if ( *v6 )
      {
        SysFreeString(*v6);
        *v6 = 0;
      }
      ATL::CComBSTR::operator=(v6, bstrString);
      v22 = (unsigned __int16 *)LocalAlloc(0, 0x802u);
      v23 = v22;
      hMem = v22;
      if ( !v22 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DssD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (__int64)"regSecConnStrValue",
            (__int64)"regSecConnStrValue",
            14);
        }
        DbConnectionStringWithPassword = -2147024882;
        LeaveCriticalSection(&COdbcConnection::m_DecryptPswdLock);
        goto LABEL_98;
      }
      CTSRegEntry::GetString((CTSRegEntry *)&phkResult, L"DBSecondaryConnString", v22, &v39);
      DbConnectionStringWithPassword = v35;
      v24 = v35 < 0;
      if ( v35 > 0 )
      {
        DbConnectionStringWithPassword = (unsigned __int16)v35 | 0x80070000;
        v24 = 1;
      }
      if ( v24 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v25 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids, v25);
        }
        DbConnectionStringWithPassword = 0;
      }
      if ( v39 <= 1 )
        goto LABEL_90;
      DbConnectionStringWithPassword = RdCentralDbUtils::GetDbConnectionStringWithPassword(
                                         (wchar_t *)L"SecondaryConnectionString",
                                         0,
                                         v23,
                                         L"System\\CurrentControlSet\\Services\\Tssdis\\Parameters\\Secrets",
                                         &v32);
      if ( DbConnectionStringWithPassword < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v26 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            (unsigned int)&WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids,
            v26,
            (__int64)"RdCentralDbUtils::GetDbConnectionStringWithPassword",
            DbConnectionStringWithPassword);
        }
        LeaveCriticalSection(&COdbcConnection::m_DecryptPswdLock);
        goto LABEL_98;
      }
      v27 = (OLECHAR *)*((_QWORD *)this + 11);
      if ( v27 )
      {
        SysFreeString(v27);
        *((_QWORD *)this + 11) = 0;
      }
      v28 = v32;
      v29 = (BSTR *)((char *)this + 88);
    }
    else
    {
      v28 = COdbcConnection::m_sRegConnString;
      v29 = v6;
    }
    ATL::CComBSTR::operator=(v29, v28);
LABEL_90:
    LeaveCriticalSection(&COdbcConnection::m_DecryptPswdLock);
    goto LABEL_92;
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    return (unsigned int)DbConnectionStringWithPassword;
  }
  v7 = RdpWppGetCurrentThreadActivityIdPrefix();
  WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids, v7);
LABEL_102:
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v32 )
    SysFreeString(v32);
  return (unsigned int)DbConnectionStringWithPassword;
}

```

## disassembly

```asm
0x180099768  mov     [rsp-8+arg_0], rcx
0x18009976d  push    rbp
0x18009976e  push    rbx
0x18009976f  push    rdi
0x180099770  push    r12
0x180099772  push    r13
0x180099774  push    r14
0x180099776  push    r15
0x180099778  lea     rbp, [rsp-27h]
0x18009977d  sub     rsp, 0A0h
0x180099784  xor     edi, edi
0x180099786  mov     dword ptr [rbp+57h+arg_8], 400h
0x18009978d  mov     [rbp+57h+arg_10], 400h
0x180099794  and     [rbp+57h+bstrString], rdi
0x180099798  and     [rbp+57h+var_90], rdi
0x18009979c  xor     r13d, r13d
0x18009979f  and     [rbp+57h+hMem], rdi
0x1800997a3  lea     r12, [rcx+50h]
0x1800997a7  cmp     [r12], rdi
0x1800997ab  jz      short loc_1800997FF
0x1800997ad  lea     r14, WPP_GLOBAL_Control
0x1800997b4  mov     rax, cs:WPP_GLOBAL_Control
0x1800997bb  cmp     rax, r14
0x1800997be  jz      loc_180099ED9
0x1800997c4  test    byte ptr [rax+1Ch], 8
0x1800997c8  jz      loc_180099ED9
0x1800997ce  cmp     byte ptr [rax+19h], 4
0x1800997d2  jb      loc_180099ED9
0x1800997d8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800997dd  lea     edx, [rdi+13h]
0x1800997e0  mov     r9d, eax
0x1800997e3  lea     r8, WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids
0x1800997ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800997f1  mov     rcx, [rcx+10h]
0x1800997f5  call    WPP_SF_D
0x1800997fa  jmp     loc_180099EAF
0x1800997ff  lea     rcx, [rbp+57h+phkResult]; phkResult
0x180099803  call    ??0CTSRegEntry@@QEAA@PEBGPEAUHKEY__@@HK@Z; CTSRegEntry::CTSRegEntry(ushort const *,HKEY__ *,int,ulong)
0x180099808  nop
0x180099809  mov     ebx, 80070000h
0x18009980e  mov     edi, [rbp+57h+var_78]
0x180099811  test    edi, edi
0x180099813  jle     short loc_18009981C
0x180099815  movzx   edi, di
0x180099818  or      edi, ebx
0x18009981a  test    edi, edi
0x18009981c  jns     short loc_180099880
0x18009981e  lea     r14, WPP_GLOBAL_Control
0x180099825  mov     rax, cs:WPP_GLOBAL_Control
0x18009982c  cmp     rax, r14
0x18009982f  jz      short loc_180099872
0x180099831  test    byte ptr [rax+1Ch], 8
0x180099835  jz      short loc_180099872
0x180099837  cmp     byte ptr [rax+19h], 2
0x18009983b  jb      short loc_180099872
0x18009983d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180099842  mov     r9d, eax
0x180099845  mov     rax, cs:WPP_GLOBAL_Control
0x18009984c  mov     edx, 14h
0x180099851  mov     dword ptr [rsp+0D0h+var_A8], edi
0x180099855  lea     rcx, aRegconnstr; "regConnStr"
0x18009985c  mov     [rsp+0D0h+var_B0], rcx
0x180099861  lea     r8, WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids
0x180099868  mov     rcx, [rax+10h]
0x18009986c  call    WPP_SF_DsD
0x180099871  nop
0x180099872  lea     rcx, [rbp+57h+phkResult]; this
0x180099876  call    ??1CTSRegEntry@@QEAA@XZ; CTSRegEntry::~CTSRegEntry(void)
0x18009987b  jmp     loc_180099EAF
0x180099880  lea     r14, WPP_GLOBAL_Control
0x180099887  lea     r15, WPP_b3cfdbbee2fe34db05ba190773897d01_Traceguids
0x18009988e  mov     rax, cs:WPP_GLOBAL_Control
0x180099895  cmp     rax, r14
0x180099898  jz      short loc_1800998CD
0x18009989a  test    byte ptr [rax+1Ch], 8
0x18009989e  jz      short loc_1800998CD
0x1800998a0  cmp     byte ptr [rax+19h], 4
0x1800998a4  jb      short loc_1800998CD
0x1800998a6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800998ab  mov     r9d, eax
0x1800998ae  mov     rax, cs:WPP_GLOBAL_Control
0x1800998b5  mov     edx, 15h
0x1800998ba  mov     r8, r15
0x1800998bd  mov     rcx, [rax+10h]
0x1800998c1  call    WPP_SF_D
0x1800998c6  mov     rax, cs:WPP_GLOBAL_Control
0x1800998cd  cmp     cs:?m_sRegConnString@COdbcConnection@@0PEAGEA, 0; ushort * COdbcConnection::m_sRegConnString
0x1800998d5  jnz     loc_1800999F2
0x1800998db  cmp     rax, r14
0x1800998de  jz      short loc_18009990C
0x1800998e0  test    byte ptr [rax+1Ch], 8
0x1800998e4  jz      short loc_18009990C
0x1800998e6  cmp     byte ptr [rax+19h], 4
0x1800998ea  jb      short loc_18009990C
0x1800998ec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800998f1  mov     r9d, eax
0x1800998f4  mov     rax, cs:WPP_GLOBAL_Control
0x1800998fb  mov     edx, 16h
0x180099900  mov     r8, r15
0x180099903  mov     rcx, [rax+10h]
0x180099907  call    WPP_SF_D
0x18009990c  mov     edx, 802h; uBytes
0x180099911  xor     ecx, ecx; uFlags
0x180099913  call    cs:__imp_LocalAlloc
0x18009991a  nop     dword ptr [rax+rax+00h]
0x18009991f  mov     cs:?m_sRegConnString@COdbcConnection@@0PEAGEA, rax; ushort * COdbcConnection::m_sRegConnString
0x180099926  test    rax, rax
0x180099929  jnz     short loc_180099986
0x18009992b  mov     rax, cs:WPP_GLOBAL_Control
0x180099932  cmp     rax, r14
0x180099935  jz      short loc_18009997C
0x180099937  test    byte ptr [rax+1Ch], 8
0x18009993b  jz      short loc_18009997C
0x18009993d  cmp     byte ptr [rax+19h], 2
0x180099941  jb      short loc_18009997C
0x180099943  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180099948  mov     r9d, eax
0x18009994b  mov     rax, cs:WPP_GLOBAL_Control
0x180099952  mov     edx, 17h
0x180099957  mov     dword ptr [rsp+0D0h+var_A0], 8007000Eh; char
0x18009995f  lea     rcx, aMSregconnstrin; "m_sRegConnString"
0x180099966  mov     [rsp+0D0h+var_A8], rcx; __int64
0x18009996b  mov     [rsp+0D0h+var_B0], rcx; __int64
0x180099970  mov     r8, r15
0x180099973  mov     rcx, [rax+10h]; LoggerHandle
0x180099977  call    WPP_SF_DssD
0x18009997c  mov     edi, 8007000Eh
0x180099981  jmp     loc_180099872
0x180099986  lea     r9, [rbp+57h+arg_8]; unsigned int *
0x18009998a  mov     r8, rax; unsigned __int16 *
0x18009998d  lea     rdx, aDbconnstring; "DBConnString"
0x180099994  lea     rcx, [rbp+57h+phkResult]; this
0x180099998  call    ?GetString@CTSRegEntry@@QEAAXPEBGPEAGPEAK@Z; CTSRegEntry::GetString(ushort const *,ushort *,ulong *)
0x18009999d  mov     edi, [rbp+57h+var_78]
0x1800999a0  test    edi, edi
0x1800999a2  jle     short loc_1800999AB
0x1800999a4  movzx   edi, di
0x1800999a7  or      edi, ebx
0x1800999a9  test    edi, edi
0x1800999ab  jns     short loc_1800999E9
0x1800999ad  mov     rax, cs:WPP_GLOBAL_Control
0x1800999b4  cmp     rax, r14
0x1800999b7  jz      short loc_1800999E5
0x1800999b9  test    byte ptr [rax+1Ch], 8
0x1800999bd  jz      short loc_1800999E5
0x1800999bf  cmp     byte ptr [rax+19h], 3
0x1800999c3  jb      short loc_1800999E5
0x1800999c5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800999ca  mov     r9d, eax
0x1800999cd  mov     rax, cs:WPP_GLOBAL_Control
0x1800999d4  mov     edx, 18h
0x1800999d9  mov     r8, r15
0x1800999dc  mov     rcx, [rax+10h]
0x1800999e0  call    WPP_SF_D
0x1800999e5  xor     edi, edi
0x1800999e7  jmp     short loc_1800999F2
0x1800999e9  mov     eax, dword ptr [rbp+57h+arg_8]
0x1800999ec  mov     cs:?m_sRegConnStringLen@COdbcConnection@@0KA, eax; ulong COdbcConnection::m_sRegConnStringLen
0x1800999f2  cmp     cs:?m_sRegConnStringLen@COdbcConnection@@0KA, 1; ulong COdbcConnection::m_sRegConnStringLen
0x1800999f9  jbe     loc_180099E0E
0x1800999ff  lea     rax, ?m_DecryptPswdLock@COdbcConnection@@0VCCSLock@@A; CCSLock COdbcConnection::m_DecryptPswdLock
0x180099a06  mov     [rbp+57h+arg_8], rax
0x180099a0a  mov     rcx, rax; lpCriticalSection
0x180099a0d  call    cs:__imp_EnterCriticalSection
0x180099a14  nop     dword ptr [rax+rax+00h]
0x180099a19  nop
0x180099a1a  mov     rdx, cs:?m_sRegConnString@COdbcConnection@@0PEAGEA; ushort * COdbcConnection::m_sRegConnString
0x180099a21  lea     rcx, [rbp+57h+var_58]
0x180099a25  call    ??0?$CBaseStringT@G@@QEAA@PEBG@Z; CBaseStringT<ushort>::CBaseStringT<ushort>(ushort const *)
0x180099a2a  nop
0x180099a2b  xor     r8d, r8d
0x180099a2e  lea     rdx, aPasswordReplac; "{password_replaced}"
0x180099a35  mov     rcx, rax
0x180099a38  call    ?Contains@?$CBaseStringT@G@@QEBAHPEBGH@Z; CBaseStringT<ushort>::Contains(ushort const *,int)
0x180099a3d  mov     ebx, eax
0x180099a3f  lea     rcx, [rbp+57h+var_58]
0x180099a43  call    ??1?$CBaseStringT@G@@QEAA@XZ; CBaseStringT<ushort>::~CBaseStringT<ushort>(void)
0x180099a48  test    ebx, ebx
0x180099a4a  jz      loc_180099DE8
0x180099a50  mov     rax, cs:WPP_GLOBAL_Control
0x180099a57  cmp     rax, r14
0x180099a5a  jz      short loc_180099A88
0x180099a5c  test    byte ptr [rax+1Ch], 8
0x180099a60  jz      short loc_180099A88
0x180099a62  cmp     byte ptr [rax+19h], 4
0x180099a66  jb      short loc_180099A88
0x180099a68  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180099a6d  mov     r9d, eax
0x180099a70  mov     rax, cs:WPP_GLOBAL_Control
0x180099a77  mov     edx, 19h
0x180099a7c  mov     r8, r15
0x180099a7f  mov     rcx, [rax+10h]
0x180099a83  call    WPP_SF_D
0x180099a88  mov     ebx, 802h
0x180099a8d  mov     edx, ebx; uBytes
0x180099a8f  xor     ecx, ecx; uFlags
0x180099a91  call    cs:__imp_LocalAlloc
0x180099a98  nop     dword ptr [rax+rax+00h]
0x180099a9d  mov     r13, rax
0x180099aa0  test    rax, rax
0x180099aa3  jnz     short loc_180099B13
0x180099aa5  mov     rax, cs:WPP_GLOBAL_Control
0x180099aac  cmp     rax, r14
0x180099aaf  jz      short loc_180099AF5
0x180099ab1  test    byte ptr [rax+1Ch], 8
0x180099ab5  jz      short loc_180099AF5
0x180099ab7  cmp     byte ptr [rax+19h], 2
0x180099abb  jb      short loc_180099AF5
0x180099abd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180099ac2  mov     r9d, eax
0x180099ac5  mov     rax, cs:WPP_GLOBAL_Control
0x180099acc  lea     edx, [r13+1Ah]
0x180099ad0  mov     dword ptr [rsp+0D0h+var_A0], 8007000Eh; char
0x180099ad8  lea     r8, aRegconnstrvalu; "regConnStrValue"
0x180099adf  mov     [rsp+0D0h+var_A8], r8; __int64
0x180099ae4  mov     [rsp+0D0h+var_B0], r8; __int64
0x180099ae9  mov     r8, r15
0x180099aec  mov     rcx, [rax+10h]; LoggerHandle
0x180099af0  call    WPP_SF_DssD
0x180099af5  mov     edi, 8007000Eh
0x180099afa  lea     rcx, ?m_DecryptPswdLock@COdbcConnection@@0VCCSLock@@A; lpCriticalSection
0x180099b01  call    cs:__imp_LeaveCriticalSection
0x180099b08  nop     dword ptr [rax+rax+00h]
0x180099b0d  nop
0x180099b0e  jmp     loc_180099872
0x180099b13  mov     r8, cs:?m_sRegConnString@COdbcConnection@@0PEAGEA; unsigned __int16 *
0x180099b1a  mov     edx, 400h; unsigned __int64
0x180099b1f  mov     rcx, r13; unsigned __int16 *
0x180099b22  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180099b27  mov     edi, eax
0x180099b29  test    eax, eax
0x180099b2b  jns     short loc_180099B8F
0x180099b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180099b34  cmp     rcx, r14
0x180099b37  jz      short loc_180099B76
0x180099b39  test    byte ptr [rcx+1Ch], 8
0x180099b3d  jz      short loc_180099B76
0x180099b3f  cmp     byte ptr [rcx+19h], 2
0x180099b43  jb      short loc_180099B76
0x180099b45  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180099b4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180099b51  mov     edx, 1Bh
0x180099b56  mov     dword ptr [rsp+0D0h+var_A8], edi
0x180099b5a  lea     r8, aStringcchcopyR; "StringCchCopy regValue"
0x180099b61  mov     [rsp+0D0h+var_B0], r8
0x180099b66  mov     r9d, eax
0x180099b69  mov     r8, r15
0x180099b6c  mov     rcx, [rcx+10h]
0x180099b70  call    WPP_SF_DsD
0x180099b75  nop
0x180099b76  lea     rcx, ?m_DecryptPswdLock@COdbcConnection@@0VCCSLock@@A; lpCriticalSection
0x180099b7d  call    cs:__imp_LeaveCriticalSection
0x180099b84  nop     dword ptr [rax+rax+00h]
0x180099b89  nop
0x180099b8a  jmp     loc_180099E7A
0x180099b8f  lea     rax, [rbp+57h+bstrString]
0x180099b93  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 **
0x180099b98  lea     r9, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Ts"...
0x180099b9f  mov     r8, r13; unsigned __int16 *
0x180099ba2  xor     edx, edx; unsigned __int16 *
0x180099ba4  lea     rcx, aPrimaryconnect; "PrimaryConnectionString"
0x180099bab  call    ?GetDbConnectionStringWithPassword@RdCentralDbUtils@@SAJPEAG000PEAPEAG@Z; RdCentralDbUtils::GetDbConnectionStringWithPassword(ushort *,ushort *,ushort *,ushort *,ushort * *)
0x180099bb0  mov     edi, eax
0x180099bb2  test    eax, eax
0x180099bb4  jns     short loc_180099C18
0x180099bb6  mov     rax, cs:WPP_GLOBAL_Control
0x180099bbd  cmp     rax, r14
0x180099bc0  jz      short loc_180099BFF
0x180099bc2  test    byte ptr [rax+1Ch], 8
0x180099bc6  jz      short loc_180099BFF
0x180099bc8  cmp     byte ptr [rax+19h], 2
0x180099bcc  jb      short loc_180099BFF
0x180099bce  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180099bd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180099bda  mov     edx, 1Ch
0x180099bdf  mov     dword ptr [rsp+0D0h+var_A8], edi
0x180099be3  lea     r8, aRdcentraldbuti; "RdCentralDbUtils::GetDbConnectionString"...
0x180099bea  mov     [rsp+0D0h+var_B0], r8
0x180099bef  mov     r9d, eax
0x180099bf2  mov     r8, r15
0x180099bf5  mov     rcx, [rcx+10h]
0x180099bf9  call    WPP_SF_DsD
0x180099bfe  nop
0x180099bff  lea     rcx, ?m_DecryptPswdLock@COdbcConnection@@0VCCSLock@@A; lpCriticalSection
0x180099c06  call    cs:__imp_LeaveCriticalSection
0x180099c0d  nop     dword ptr [rax+rax+00h]
0x180099c12  nop
0x180099c13  jmp     loc_180099E7A
0x180099c18  mov     rcx, [r12]; bstrString
0x180099c1c  test    rcx, rcx
0x180099c1f  jz      short loc_180099C32
0x180099c21  call    cs:__imp_SysFreeString
0x180099c28  nop     dword ptr [rax+rax+00h]
0x180099c2d  and     qword ptr [r12], 0
0x180099c32  mov     rdx, [rbp+57h+bstrString]
0x180099c36  mov     rcx, r12
0x180099c39  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180099c3e  mov     rdx, rbx; uBytes
0x180099c41  xor     ecx, ecx; uFlags
0x180099c43  call    cs:__imp_LocalAlloc
  ... truncated ...
```
