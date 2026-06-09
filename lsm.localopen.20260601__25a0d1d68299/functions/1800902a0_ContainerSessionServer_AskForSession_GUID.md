# ContainerSessionServer::AskForSession(_GUID)

- ea: `0x1800902a0`
- end: `0x180090767`
- name: `?AskForSession@ContainerSessionServer@@QEAAJU_GUID@@@Z`
- size: `1223`
- prototype: `__int64 __fastcall(ContainerSessionServer *__hidden this, IID *rclsid)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800973d0`

## callees

- `0x18000187c`
- `0x180022080`
- `0x1800236a8`
- `0x18002f26c`
- `0x180048788`
- `0x18004e24c`
- `0x18004e850`
- `0x18004ec20`
- `0x18004eca4`
- `0x180064d64`
- `0x1800901b4`
- `0x1800902a0`
- `0x180090770`
- `0x1800909d0`
- `0x180090ae4`
- `0x180097294`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180090555`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180090555`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180090715`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180090715`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009046f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009046f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18009031e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18009031e`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsCloseComputeSystem` at `0x180090534`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsCloseComputeSystem` at `0x180090597`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsCloseComputeSystem` at `0x1800906c7`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsCloseComputeSystem` at `0x180090534`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsCloseComputeSystem` at `0x180090597`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsCloseComputeSystem` at `0x1800906c7`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsOpenComputeSystem` at `0x180090414`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsOpenComputeSystem` at `0x180090414`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsRegisterComputeSystemCallback` at `0x180090654`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsRegisterComputeSystemCallback` at `0x180090654`

## string_xrefs

- `0x180090431`: `OpenComputeSystem returned`
- `0x180090495`: `HcsRegisterComputeSystemCallback failed, so we can't track the container.`
- `0x180090677`: `HcsRegisterComputeSystemCallback failed, so we can't track the container.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ContainerSessionServer::AskForSession(struct _RTL_CRITICAL_SECTION *this, IID *rclsid)
{
  unsigned int v4; // ebx
  __int64 v5; // r8
  PCWSTR *v6; // rdx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  const WCHAR *v10; // rcx
  HRESULT v11; // eax
  int v12; // r15d
  __int64 v13; // rax
  IID *v14; // rbx
  void *v15; // r15
  IID v16; // xmm0
  int v17; // eax
  unsigned int v19[2]; // [rsp+30h] [rbp-88h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-80h] BYREF
  DWORD requestedAccess[2]; // [rsp+40h] [rbp-78h] BYREF
  unsigned int v22; // [rsp+48h] [rbp-70h] BYREF
  struct _GUID v23; // [rsp+50h] [rbp-68h] BYREF
  __int64 v24; // [rsp+60h] [rbp-58h]
  __int64 v25; // [rsp+68h] [rbp-50h]
  PCWSTR id[2]; // [rsp+70h] [rbp-48h] BYREF
  __int64 v27; // [rsp+80h] [rbp-38h]
  unsigned __int64 v28; // [rsp+88h] [rbp-30h]

  v4 = 5;
  if ( (unsigned int)dword_1800DF020 > 5 )
  {
    lpsz = (LPOLESTR)"Got asked for a session";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_1800DF020,
      (unsigned int)&word_1800D022E,
      0,
      0,
      (__int64)&lpsz);
  }
  lpsz = 0;
  StringFromCLSID(rclsid, &lpsz);
  try
  {
    std::wstring::wstring(id, lpsz);
    v23 = 0;
    v24 = 0;
    v25 = 0;
    if ( !v27 )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
      __debugbreak();
      JUMPOUT(0x180090767LL);
    }
    v5 = v27 - 1;
    if ( v27 - 1 >= (unsigned __int64)(v27 - 2) )
      v5 = v27 - 2;
    v6 = id;
    if ( v28 > 7 )
      v6 = (PCWSTR *)id[0];
    std::wstring::_Construct<1,unsigned short const *>(&v23, (char *)v6 + 2, v5);
    std::wstring::operator=(id, &v23);
    std::wstring::_Tidy_deallocate(&v23);
    if ( (unsigned int)dword_1800DF020 > 5 )
    {
      *(_QWORD *)v19 = lpsz;
      *(_QWORD *)&v23.Data1 = "Got asked for a session and it was by this GUID";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v7,
        (unsigned int)&word_1800D01FE,
        v8,
        v9,
        (__int64)&v23,
        (__int64)v19);
    }
    *(_QWORD *)requestedAccess = 0;
    v10 = (const WCHAR *)id;
    if ( v28 > 7 )
      v10 = id[0];
    v11 = HcsOpenComputeSystem(v10, (DWORD)requestedAccess, 0);
    v12 = v11;
    if ( (unsigned int)dword_1800DF020 > 5 )
    {
      v19[0] = v11;
      *(_QWORD *)&v23.Data1 = "OpenComputeSystem returned";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800DF020,
        (unsigned int)byte_1800D02DB,
        0,
        0,
        (__int64)&v23,
        (__int64)v19);
    }
    CoTaskMemFree(lpsz);
    if ( v12 < 0 && LODWORD(this->DebugInfo) )
    {
      if ( (unsigned int)dword_1800DF020 > 2 )
      {
        v19[0] = v12;
        *(_QWORD *)&v23.Data1 = "HcsRegisterComputeSystemCallback failed, so we can't track the container.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800DF020,
          (unsigned int)qword_1800D0640,
          0,
          0,
          (__int64)&v23,
          (__int64)v19);
      }
LABEL_19:
      std::wstring::_Tidy_deallocate(id);
      return v4;
    }
    if ( !(unsigned int)ContainerSessionServer::IncreaseTotalSessionCount((ContainerSessionServer *)this) )
    {
      if ( (unsigned int)dword_1800DF020 > 2 )
      {
        *(_QWORD *)&v23.Data1 = "Reached max limit of sessions on the host";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&dword_1800DF020,
          (unsigned int)byte_1800D01B1,
          0,
          0,
          (__int64)&v23);
      }
      v4 = 353;
      if ( *(_QWORD *)requestedAccess )
        HcsCloseComputeSystem(*(HCS_SYSTEM *)requestedAccess);
      goto LABEL_19;
    }
    EnterCriticalSection(this + 1);
    v19[0] = 0;
    v23 = *rclsid;
    if ( (unsigned int)ContainerSessionServer::GetContainerSessionCount((ContainerSessionServer *)this, &v23, v19) )
    {
      v14 = (IID *)operator new(0x18u);
      v15 = operator new(8u);
      v16 = *rclsid;
      *v14 = *rclsid;
      *(_QWORD *)&v14[1].Data1 = v15;
      *rclsid = v16;
      v17 = HcsRegisterComputeSystemCallback(*(_QWORD *)requestedAccess, NotificationWatcher, v14, v15);
      if ( v17 < 0 )
      {
        if ( (unsigned int)dword_1800DF020 > 2 )
        {
          v19[0] = v17;
          *(_QWORD *)&v23.Data1 = "HcsRegisterComputeSystemCallback failed, so we can't track the container.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800DF020,
            (unsigned int)byte_1800D01D5,
            0,
            0,
            (__int64)&v23,
            (__int64)v19);
        }
        ContainerSessionServer::DecreaseTotalSessionCount((ContainerSessionServer *)this, 1u);
        if ( *(_QWORD *)requestedAccess )
          HcsCloseComputeSystem(*(HCS_SYSTEM *)requestedAccess);
        operator delete(v14, (const struct std::nothrow_t *)0x18);
        operator delete(v15, (const struct std::nothrow_t *)8);
        v4 = 1359;
        goto LABEL_42;
      }
      *(_DWORD *)(*(_QWORD *)std::map<_GUID,unsigned int,GUIDComparer,std::allocator<std::pair<_GUID const,unsigned int>>>::_Try_emplace<_GUID const &,>(
                               &this->LockSemaphore,
                               &v23,
                               rclsid)
                + 44LL) = 1;
    }
    else
    {
      if ( *(_QWORD *)requestedAccess )
        HcsCloseComputeSystem(*(HCS_SYSTEM *)requestedAccess);
      if ( v19[0] >= 2 )
      {
        if ( (unsigned int)dword_1800DF020 > 2 )
        {
          *(_QWORD *)&v23.Data1 = "Reached max limit of sessions per container";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&dword_1800DF020,
            (unsigned int)&dword_1800D04B4,
            0,
            0,
            (__int64)&v23);
        }
        ContainerSessionServer::DecreaseTotalSessionCount((ContainerSessionServer *)this, 1u);
        v4 = 353;
        goto LABEL_42;
      }
      v13 = std::map<_GUID,unsigned int,GUIDComparer,std::allocator<std::pair<_GUID const,unsigned int>>>::_Try_emplace<_GUID const &,>(
              &this->LockSemaphore,
              &v23,
              rclsid);
      ++*(_DWORD *)(*(_QWORD *)v13 + 44LL);
    }
    v4 = 0;
LABEL_42:
    LeaveCriticalSection(this + 1);
    std::wstring::_Tidy_deallocate(id);
  }
  catch ( int v22 )
  {
    if ( (unsigned int)dword_1800DF020 > 2 )
    {
      v19[0] = v22;
      *(_QWORD *)&v23.Data1 = "Failed askforsession";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800DF020,
        (unsigned int)qword_1800D04D8,
        0,
        0,
        (__int64)&v23,
        (__int64)v19);
    }
    return 1359;
  }
  return v4;
}

```

## disassembly

```asm
0x1800902a0  mov     r11, rsp
0x1800902a3  mov     [r11+18h], rbx
0x1800902a7  mov     [r11+20h], rdi
0x1800902ab  push    r12
0x1800902ad  push    r14
0x1800902af  push    r15
0x1800902b1  sub     rsp, 0A0h
0x1800902b8  mov     rax, cs:__security_cookie
0x1800902bf  xor     rax, rsp
0x1800902c2  mov     [rsp+0B8h+var_28], rax
0x1800902ca  mov     r14, rdx
0x1800902cd  mov     rdi, rcx
0x1800902d0  mov     eax, cs:dword_1800DF020
0x1800902d6  mov     ebx, 5
0x1800902db  cmp     eax, ebx
0x1800902dd  jbe     short loc_18009030D
0x1800902df  lea     rax, aGotAskedForASe_0; "Got asked for a session"
0x1800902e6  mov     [r11-80h], rax
0x1800902ea  lea     rax, [r11-80h]
0x1800902ee  mov     [rsp+0B8h+var_98], rax
0x1800902f3  xor     r9d, r9d
0x1800902f6  xor     r8d, r8d
0x1800902f9  lea     rdx, word_1800D022E
0x180090300  lea     rcx, dword_1800DF020
0x180090307  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009030c  nop
0x18009030d  mov     [rsp+0B8h+lpsz], 0
0x180090316  lea     rdx, [rsp+0B8h+lpsz]; lplpsz
0x18009031b  mov     rcx, r14; rclsid
0x18009031e  call    cs:__imp_StringFromCLSID
0x180090325  nop     dword ptr [rax+rax+00h]
0x18009032a  mov     rdx, [rsp+0B8h+lpsz]
0x18009032f  lea     rcx, [rsp+0B8h+id]
0x180090334  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180090339  nop
0x18009033a  xorps   xmm0, xmm0
0x18009033d  movups  xmmword ptr [rsp+0B8h+var_68.Data1], xmm0
0x180090342  mov     [rsp+0B8h+var_58], 0
0x18009034b  mov     [rsp+0B8h+var_50], 0
0x180090354  mov     r8, [rsp+0B8h+var_38]
0x18009035c  cmp     r8, 1
0x180090360  jb      loc_180090760
0x180090366  lea     rax, [r8-2]
0x18009036a  dec     r8
0x18009036d  cmp     r8, rax
0x180090370  cmovnb  r8, rax
0x180090374  lea     rdx, [rsp+0B8h+id]
0x180090379  cmp     [rsp+0B8h+var_30], 7
0x180090382  cmova   rdx, [rsp+0B8h+id]
0x180090388  add     rdx, 2
0x18009038c  lea     rcx, [rsp+0B8h+var_68]
0x180090391  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180090396  lea     rdx, [rsp+0B8h+var_68]
0x18009039b  lea     rcx, [rsp+0B8h+id]
0x1800903a0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800903a5  lea     rcx, [rsp+0B8h+var_68]
0x1800903aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800903af  mov     eax, cs:dword_1800DF020
0x1800903b5  cmp     eax, ebx
0x1800903b7  jbe     short loc_1800903EF
0x1800903b9  mov     rax, [rsp+0B8h+lpsz]
0x1800903be  mov     qword ptr [rsp+0B8h+var_88], rax
0x1800903c3  lea     rax, aGotAskedForASe; "Got asked for a session and it was by t"...
0x1800903ca  mov     qword ptr [rsp+0B8h+var_68.Data1], rax
0x1800903cf  lea     rax, [rsp+0B8h+var_88]
0x1800903d4  mov     [rsp+0B8h+var_90], rax
0x1800903d9  lea     rax, [rsp+0B8h+var_68]
0x1800903de  mov     [rsp+0B8h+var_98], rax
0x1800903e3  lea     rdx, word_1800D01FE
0x1800903ea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800903ef  mov     qword ptr [rsp+0B8h+requestedAccess], 0
0x1800903f8  lea     rcx, [rsp+0B8h+id]
0x1800903fd  cmp     [rsp+0B8h+var_30], 7
0x180090406  cmova   rcx, [rsp+0B8h+id]; id
0x18009040c  xor     r8d, r8d; computeSystem
0x18009040f  lea     rdx, [rsp+0B8h+requestedAccess]; requestedAccess
0x180090414  call    cs:__imp_HcsOpenComputeSystem
0x18009041b  nop     dword ptr [rax+rax+00h]
0x180090420  mov     r15d, eax
0x180090423  mov     ecx, cs:dword_1800DF020
0x180090429  cmp     ecx, ebx
0x18009042b  jbe     short loc_18009046A
0x18009042d  mov     [rsp+0B8h+var_88], eax
0x180090431  lea     rax, aOpencomputesys; "OpenComputeSystem returned"
0x180090438  mov     qword ptr [rsp+0B8h+var_68.Data1], rax
0x18009043d  lea     rax, [rsp+0B8h+var_88]
0x180090442  mov     [rsp+0B8h+var_90], rax
0x180090447  lea     rax, [rsp+0B8h+var_68]
0x18009044c  mov     [rsp+0B8h+var_98], rax
0x180090451  xor     r9d, r9d
0x180090454  xor     r8d, r8d
0x180090457  lea     rdx, byte_1800D02DB
0x18009045e  lea     rcx, dword_1800DF020
0x180090465  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009046a  mov     rcx, [rsp+0B8h+lpsz]; pv
0x18009046f  call    cs:__imp_CoTaskMemFree
0x180090476  nop     dword ptr [rax+rax+00h]
0x18009047b  test    r15d, r15d
0x18009047e  jns     short loc_1800904DF
0x180090480  cmp     dword ptr [rdi], 0
0x180090483  jz      short loc_1800904DF
0x180090485  mov     eax, cs:dword_1800DF020
0x18009048b  cmp     eax, 2
0x18009048e  jbe     short loc_1800904CF
0x180090490  mov     [rsp+0B8h+var_88], r15d
0x180090495  lea     rax, aHcsregistercom_0; "HcsRegisterComputeSystemCallback failed"...
0x18009049c  mov     qword ptr [rsp+0B8h+var_68.Data1], rax
0x1800904a1  lea     rax, [rsp+0B8h+var_88]
0x1800904a6  mov     [rsp+0B8h+var_90], rax
0x1800904ab  lea     rax, [rsp+0B8h+var_68]
0x1800904b0  mov     [rsp+0B8h+var_98], rax
0x1800904b5  xor     r9d, r9d
0x1800904b8  xor     r8d, r8d
0x1800904bb  lea     rdx, qword_1800D0640
0x1800904c2  lea     rcx, dword_1800DF020
0x1800904c9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800904ce  nop
0x1800904cf  lea     rcx, [rsp+0B8h+id]
0x1800904d4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800904d9  nop
0x1800904da  jmp     loc_180090733
0x1800904df  mov     rcx, rdi; this
0x1800904e2  call    ?IncreaseTotalSessionCount@ContainerSessionServer@@QEAAHXZ; ContainerSessionServer::IncreaseTotalSessionCount(void)
0x1800904e7  test    eax, eax
0x1800904e9  jnz     short loc_180090551
0x1800904eb  mov     eax, cs:dword_1800DF020
0x1800904f1  cmp     eax, 2
0x1800904f4  jbe     short loc_180090525
0x1800904f6  lea     rax, aReachedMaxLimi_0; "Reached max limit of sessions on the ho"...
0x1800904fd  mov     qword ptr [rsp+0B8h+var_68.Data1], rax
0x180090502  lea     rax, [rsp+0B8h+var_68]
0x180090507  mov     [rsp+0B8h+var_98], rax
0x18009050c  xor     r9d, r9d
0x18009050f  xor     r8d, r8d
0x180090512  lea     rdx, byte_1800D01B1
0x180090519  lea     rcx, dword_1800DF020
0x180090520  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180090525  mov     ebx, 161h
0x18009052a  mov     rcx, qword ptr [rsp+0B8h+requestedAccess]; computeSystem
0x18009052f  test    rcx, rcx
0x180090532  jz      short loc_180090541
0x180090534  call    cs:__imp_HcsCloseComputeSystem
0x18009053b  nop     dword ptr [rax+rax+00h]
0x180090540  nop
0x180090541  lea     rcx, [rsp+0B8h+id]
0x180090546  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009054b  nop
0x18009054c  jmp     loc_180090733
0x180090551  lea     rcx, [rdi+28h]; lpCriticalSection
0x180090555  call    cs:__imp_EnterCriticalSection
0x18009055c  nop     dword ptr [rax+rax+00h]
0x180090561  mov     [rsp+0B8h+var_88], 0
0x180090569  movups  xmm0, xmmword ptr [r14]
0x18009056d  movdqu  xmmword ptr [rsp+0B8h+var_68.Data1], xmm0
0x180090573  lea     r8, [rsp+0B8h+var_88]; unsigned int *
0x180090578  lea     rdx, [rsp+0B8h+var_68]; struct _GUID
0x18009057d  mov     rcx, rdi; this
0x180090580  call    ?GetContainerSessionCount@ContainerSessionServer@@QEAAJU_GUID@@PEAI@Z; ContainerSessionServer::GetContainerSessionCount(_GUID,uint *)
0x180090585  test    eax, eax
0x180090587  jnz     loc_180090617
0x18009058d  mov     rcx, qword ptr [rsp+0B8h+requestedAccess]; computeSystem
0x180090592  test    rcx, rcx
0x180090595  jz      short loc_1800905A3
0x180090597  call    cs:__imp_HcsCloseComputeSystem
0x18009059e  nop     dword ptr [rax+rax+00h]
0x1800905a3  cmp     [rsp+0B8h+var_88], 2
0x1800905a8  jb      short loc_1800905FB
0x1800905aa  mov     eax, cs:dword_1800DF020
0x1800905b0  cmp     eax, 2
0x1800905b3  jbe     short loc_1800905E4
0x1800905b5  lea     rax, aReachedMaxLimi; "Reached max limit of sessions per conta"...
0x1800905bc  mov     qword ptr [rsp+0B8h+var_68.Data1], rax
0x1800905c1  lea     rax, [rsp+0B8h+var_68]
0x1800905c6  mov     [rsp+0B8h+var_98], rax
0x1800905cb  xor     r9d, r9d
0x1800905ce  xor     r8d, r8d
0x1800905d1  lea     rdx, dword_1800D04B4
0x1800905d8  lea     rcx, dword_1800DF020
0x1800905df  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800905e4  mov     edx, 1; unsigned int
0x1800905e9  mov     rcx, rdi; this
0x1800905ec  call    ?DecreaseTotalSessionCount@ContainerSessionServer@@QEAAXI@Z; ContainerSessionServer::DecreaseTotalSessionCount(uint)
0x1800905f1  mov     ebx, 161h
0x1800905f6  jmp     loc_180090711
0x1800905fb  lea     rcx, [rdi+18h]
0x1800905ff  mov     r8, r14
0x180090602  lea     rdx, [rsp+0B8h+var_68]
0x180090607  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@IUGUIDComparer@@V?$allocator@U?$pair@$$CBU_GUID@@I@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@I@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,uint,GUIDComparer,std::allocator<std::pair<_GUID const,uint>>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x18009060c  mov     rax, [rax]
0x18009060f  inc     dword ptr [rax+2Ch]
0x180090612  jmp     loc_18009070F
0x180090617  mov     ecx, 18h; Size
0x18009061c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180090621  mov     rbx, rax
0x180090624  mov     ecx, 8; Size
0x180090629  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009062e  mov     r15, rax
0x180090631  movups  xmm0, xmmword ptr [r14]
0x180090635  movdqu  xmmword ptr [rbx], xmm0
0x180090639  mov     [rbx+10h], rax
0x18009063d  movdqu  xmmword ptr [r14], xmm0
0x180090642  mov     r9, rax
0x180090645  mov     r8, rbx
0x180090648  lea     rdx, ?NotificationWatcher@@YAXKPEAXJPEBG@Z; NotificationWatcher(ulong,void *,long,ushort const *)
0x18009064f  mov     rcx, qword ptr [rsp+0B8h+requestedAccess]
0x180090654  call    cs:__imp_HcsRegisterComputeSystemCallback
0x18009065b  nop     dword ptr [rax+rax+00h]
0x180090660  test    eax, eax
0x180090662  jns     loc_1800906F4
0x180090668  mov     ecx, cs:dword_1800DF020
0x18009066e  cmp     ecx, 2
0x180090671  jbe     short loc_1800906B0
0x180090673  mov     [rsp+0B8h+var_88], eax
0x180090677  lea     rax, aHcsregistercom_0; "HcsRegisterComputeSystemCallback failed"...
0x18009067e  mov     qword ptr [rsp+0B8h+var_68.Data1], rax
0x180090683  lea     rax, [rsp+0B8h+var_88]
0x180090688  mov     [rsp+0B8h+var_90], rax
0x18009068d  lea     rax, [rsp+0B8h+var_68]
0x180090692  mov     [rsp+0B8h+var_98], rax
0x180090697  xor     r9d, r9d
0x18009069a  xor     r8d, r8d
0x18009069d  lea     rdx, byte_1800D01D5
0x1800906a4  lea     rcx, dword_1800DF020
0x1800906ab  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800906b0  mov     edx, 1; unsigned int
0x1800906b5  mov     rcx, rdi; this
0x1800906b8  call    ?DecreaseTotalSessionCount@ContainerSessionServer@@QEAAXI@Z; ContainerSessionServer::DecreaseTotalSessionCount(uint)
0x1800906bd  mov     rcx, qword ptr [rsp+0B8h+requestedAccess]; computeSystem
0x1800906c2  test    rcx, rcx
0x1800906c5  jz      short loc_1800906D3
0x1800906c7  call    cs:__imp_HcsCloseComputeSystem
0x1800906ce  nop     dword ptr [rax+rax+00h]
0x1800906d3  mov     edx, 18h; struct std::nothrow_t *
0x1800906d8  mov     rcx, rbx; void *
0x1800906db  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800906e0  mov     edx, 8; struct std::nothrow_t *
0x1800906e5  mov     rcx, r15; void *
0x1800906e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800906ed  mov     ebx, 54Fh
0x1800906f2  jmp     short loc_180090711
0x1800906f4  lea     rcx, [rdi+18h]
0x1800906f8  mov     r8, r14
0x1800906fb  lea     rdx, [rsp+0B8h+var_68]
0x180090700  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@IUGUIDComparer@@V?$allocator@U?$pair@$$CBU_GUID@@I@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@I@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,uint,GUIDComparer,std::allocator<std::pair<_GUID const,uint>>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x180090705  mov     rax, [rax]
0x180090708  mov     dword ptr [rax+2Ch], 1
0x18009070f  xor     ebx, ebx
0x180090711  lea     rcx, [rdi+28h]; lpCriticalSection
0x180090715  call    cs:__imp_LeaveCriticalSection
0x18009071c  nop     dword ptr [rax+rax+00h]
0x180090721  nop
0x180090722  lea     rcx, [rsp+0B8h+id]
0x180090727  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009072c  nop
0x18009072d  jmp     short loc_180090733
0x18009072f  mov     ebx, [rsp+0B8h+var_88]
0x180090733  mov     eax, ebx
0x180090735  mov     rcx, [rsp+0B8h+var_28]
0x18009073d  xor     rcx, rsp; StackCookie
0x180090740  call    __security_check_cookie
0x180090745  lea     r11, [rsp+0B8h+var_18]
0x18009074d  mov     rbx, [r11+30h]
0x180090751  mov     rdi, [r11+38h]
0x180090755  mov     rsp, r11
0x180090758  pop     r15
0x18009075a  pop     r14
0x18009075c  pop     r12
0x18009075e  retn
0x180090760  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
0x180090765  nop
0x180090766  int     3; Trap to Debugger
```
