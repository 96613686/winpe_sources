# ContainerSessionServer::AskForSession(_GUID)

- ea: `0x18008b4d0`
- end: `0x18008b960`
- name: `?AskForSession@ContainerSessionServer@@QEAAJU_GUID@@@Z`
- size: `1168`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, IID *rclsid)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180092040`

## callees

- `0x180001874`
- `0x18001fc20`
- `0x180021254`
- `0x18002d31c`
- `0x180045788`
- `0x18004ae6c`
- `0x18004b460`
- `0x18004b830`
- `0x18004b8b4`
- `0x180061228`
- `0x18008b3ec`
- `0x18008b4d0`
- `0x18008b968`
- `0x18008bbac`
- `0x18008bcbc`
- `0x180091f48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008b76d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008b76d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008b915`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008b915`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b693`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b693`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18008b54e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18008b54e`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsCloseComputeSystem` at `0x18008b752`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsCloseComputeSystem` at `0x18008b7a9`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsCloseComputeSystem` at `0x18008b8cd`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsCloseComputeSystem` at `0x18008b752`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsCloseComputeSystem` at `0x18008b7a9`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsCloseComputeSystem` at `0x18008b8cd`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsOpenComputeSystem` at `0x18008b63e`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsOpenComputeSystem` at `0x18008b63e`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsRegisterComputeSystemCallback` at `0x18008b860`
- `ext-ms-win-hyperv-compute-legacy-l1-1-0!HcsRegisterComputeSystemCallback` at `0x18008b860`

## string_xrefs

- `0x18008b655`: `OpenComputeSystem returned`
- `0x18008b6b3`: `HcsRegisterComputeSystemCallback failed, so we can't track the container.`
- `0x18008b87d`: `HcsRegisterComputeSystemCallback failed, so we can't track the container.`

## pseudocode

```c
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
  if ( (unsigned int)dword_1800DA020 > 5 )
  {
    lpsz = (LPOLESTR)"Got asked for a session";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_1800DA020,
      (unsigned int)&word_1800CB0DE,
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
      std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
    v5 = v27 - 1;
    if ( v27 - 1 >= (unsigned __int64)(v27 - 2) )
      v5 = v27 - 2;
    v6 = id;
    if ( v28 > 7 )
      v6 = (PCWSTR *)id[0];
    std::wstring::_Construct<1,unsigned short const *>(&v23, (char *)v6 + 2, v5);
    std::wstring::operator=(id, &v23);
    std::wstring::_Tidy_deallocate(&v23);
    if ( (unsigned int)dword_1800DA020 > 5 )
    {
      *(_QWORD *)v19 = lpsz;
      *(_QWORD *)&v23.Data1 = "Got asked for a session and it was by this GUID";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v7,
        (unsigned int)&word_1800CB076,
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
    if ( (unsigned int)dword_1800DA020 > 5 )
    {
      v19[0] = v11;
      *(_QWORD *)&v23.Data1 = "OpenComputeSystem returned";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800DA020,
        (unsigned int)word_1800CB102,
        0,
        0,
        (__int64)&v23,
        (__int64)v19);
    }
    CoTaskMemFree(lpsz);
    if ( v12 < 0 && LODWORD(this->DebugInfo) )
    {
      if ( (unsigned int)dword_1800DA020 > 2 )
      {
        v19[0] = v12;
        *(_QWORD *)&v23.Data1 = "HcsRegisterComputeSystemCallback failed, so we can't track the container.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800DA020,
          (unsigned int)byte_1800CB489,
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
      if ( (unsigned int)dword_1800DA020 > 2 )
      {
        *(_QWORD *)&v23.Data1 = "Reached max limit of sessions on the host";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&dword_1800DA020,
          (unsigned int)word_1800CB052,
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
        if ( (unsigned int)dword_1800DA020 > 2 )
        {
          v19[0] = v17;
          *(_QWORD *)&v23.Data1 = "HcsRegisterComputeSystemCallback failed, so we can't track the container.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800DA020,
            (unsigned int)byte_1800CB029,
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
        if ( (unsigned int)dword_1800DA020 > 2 )
        {
          *(_QWORD *)&v23.Data1 = "Reached max limit of sessions per container";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&dword_1800DA020,
            (unsigned int)word_1800CB2CA,
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
    if ( (unsigned int)dword_1800DA020 > 2 )
    {
      v19[0] = v22;
      *(_QWORD *)&v23.Data1 = "Failed askforsession";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800DA020,
        (unsigned int)qword_1800CB350,
        0,
        0,
        (__int64)&v23,
        (__int64)v19);
    }
    return 1359;
  }
  std::wstring::wstring(id, lpsz);
}

```

## disassembly

```asm
0x18008b4d0  mov     r11, rsp
0x18008b4d3  mov     [r11+18h], rbx
0x18008b4d7  mov     [r11+20h], rdi
0x18008b4db  push    r12
0x18008b4dd  push    r14
0x18008b4df  push    r15
0x18008b4e1  sub     rsp, 0A0h
0x18008b4e8  mov     rax, cs:__security_cookie
0x18008b4ef  xor     rax, rsp
0x18008b4f2  mov     [rsp+0B8h+var_28], rax
0x18008b4fa  mov     r14, rdx
0x18008b4fd  mov     rdi, rcx
0x18008b500  mov     eax, cs:dword_1800DA020
0x18008b506  mov     ebx, 5
0x18008b50b  cmp     eax, ebx
0x18008b50d  jbe     short loc_18008B53D
0x18008b50f  lea     rax, aGotAskedForASe_0; "Got asked for a session"
0x18008b516  mov     [r11-80h], rax
0x18008b51a  lea     rax, [r11-80h]
0x18008b51e  mov     [rsp+0B8h+var_98], rax
0x18008b523  xor     r9d, r9d
0x18008b526  xor     r8d, r8d
0x18008b529  lea     rdx, word_1800CB0DE
0x18008b530  lea     rcx, dword_1800DA020
0x18008b537  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008b53c  nop
0x18008b53d  mov     [rsp+0B8h+lpsz], 0
0x18008b546  lea     rdx, [rsp+0B8h+lpsz]; lplpsz
0x18008b54b  mov     rcx, r14; rclsid
0x18008b54e  call    cs:__imp_StringFromCLSID
0x18008b554  mov     rdx, [rsp+0B8h+lpsz]
0x18008b559  lea     rcx, [rsp+0B8h+id]
0x18008b55e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008b563  nop
0x18008b564  xorps   xmm0, xmm0
0x18008b567  movups  xmmword ptr [rsp+0B8h+var_68.Data1], xmm0
0x18008b56c  mov     [rsp+0B8h+var_58], 0
0x18008b575  mov     [rsp+0B8h+var_50], 0
0x18008b57e  mov     r8, [rsp+0B8h+var_38]
0x18008b586  cmp     r8, 1
0x18008b58a  jb      loc_18008B959
0x18008b590  lea     rax, [r8-2]
0x18008b594  dec     r8
0x18008b597  cmp     r8, rax
0x18008b59a  cmovnb  r8, rax
0x18008b59e  lea     rdx, [rsp+0B8h+id]
0x18008b5a3  cmp     [rsp+0B8h+var_30], 7
0x18008b5ac  cmova   rdx, [rsp+0B8h+id]
0x18008b5b2  add     rdx, 2
0x18008b5b6  lea     rcx, [rsp+0B8h+var_68]
0x18008b5bb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18008b5c0  lea     rdx, [rsp+0B8h+var_68]
0x18008b5c5  lea     rcx, [rsp+0B8h+id]
0x18008b5ca  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18008b5cf  lea     rcx, [rsp+0B8h+var_68]
0x18008b5d4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008b5d9  mov     eax, cs:dword_1800DA020
0x18008b5df  cmp     eax, ebx
0x18008b5e1  jbe     short loc_18008B619
0x18008b5e3  mov     rax, [rsp+0B8h+lpsz]
0x18008b5e8  mov     qword ptr [rsp+0B8h+var_88], rax
0x18008b5ed  lea     rax, aGotAskedForASe; "Got asked for a session and it was by t"...
0x18008b5f4  mov     qword ptr [rsp+0B8h+var_68.Data1], rax
0x18008b5f9  lea     rax, [rsp+0B8h+var_88]
0x18008b5fe  mov     [rsp+0B8h+var_90], rax
0x18008b603  lea     rax, [rsp+0B8h+var_68]
0x18008b608  mov     [rsp+0B8h+var_98], rax
0x18008b60d  lea     rdx, word_1800CB076
0x18008b614  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18008b619  mov     qword ptr [rsp+0B8h+requestedAccess], 0
0x18008b622  lea     rcx, [rsp+0B8h+id]
0x18008b627  cmp     [rsp+0B8h+var_30], 7
0x18008b630  cmova   rcx, [rsp+0B8h+id]; id
0x18008b636  xor     r8d, r8d; computeSystem
0x18008b639  lea     rdx, [rsp+0B8h+requestedAccess]; requestedAccess
0x18008b63e  call    cs:__imp_HcsOpenComputeSystem
0x18008b644  mov     r15d, eax
0x18008b647  mov     ecx, cs:dword_1800DA020
0x18008b64d  cmp     ecx, ebx
0x18008b64f  jbe     short loc_18008B68E
0x18008b651  mov     [rsp+0B8h+var_88], eax
0x18008b655  lea     rax, aOpencomputesys; "OpenComputeSystem returned"
0x18008b65c  mov     qword ptr [rsp+0B8h+var_68.Data1], rax
0x18008b661  lea     rax, [rsp+0B8h+var_88]
0x18008b666  mov     [rsp+0B8h+var_90], rax
0x18008b66b  lea     rax, [rsp+0B8h+var_68]
0x18008b670  mov     [rsp+0B8h+var_98], rax
0x18008b675  xor     r9d, r9d
0x18008b678  xor     r8d, r8d
0x18008b67b  lea     rdx, word_1800CB102
0x18008b682  lea     rcx, dword_1800DA020
0x18008b689  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008b68e  mov     rcx, [rsp+0B8h+lpsz]; pv
0x18008b693  call    cs:__imp_CoTaskMemFree
0x18008b699  test    r15d, r15d
0x18008b69c  jns     short loc_18008B6FD
0x18008b69e  cmp     dword ptr [rdi], 0
0x18008b6a1  jz      short loc_18008B6FD
0x18008b6a3  mov     eax, cs:dword_1800DA020
0x18008b6a9  cmp     eax, 2
0x18008b6ac  jbe     short loc_18008B6ED
0x18008b6ae  mov     [rsp+0B8h+var_88], r15d
0x18008b6b3  lea     rax, aHcsregistercom_0; "HcsRegisterComputeSystemCallback failed"...
0x18008b6ba  mov     qword ptr [rsp+0B8h+var_68.Data1], rax
0x18008b6bf  lea     rax, [rsp+0B8h+var_88]
0x18008b6c4  mov     [rsp+0B8h+var_90], rax
0x18008b6c9  lea     rax, [rsp+0B8h+var_68]
0x18008b6ce  mov     [rsp+0B8h+var_98], rax
0x18008b6d3  xor     r9d, r9d
0x18008b6d6  xor     r8d, r8d
0x18008b6d9  lea     rdx, byte_1800CB489
0x18008b6e0  lea     rcx, dword_1800DA020
0x18008b6e7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008b6ec  nop
0x18008b6ed  lea     rcx, [rsp+0B8h+id]
0x18008b6f2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008b6f7  nop
0x18008b6f8  jmp     loc_18008B92D
0x18008b6fd  mov     rcx, rdi; this
0x18008b700  call    ?IncreaseTotalSessionCount@ContainerSessionServer@@QEAAHXZ; ContainerSessionServer::IncreaseTotalSessionCount(void)
0x18008b705  test    eax, eax
0x18008b707  jnz     short loc_18008B769
0x18008b709  mov     eax, cs:dword_1800DA020
0x18008b70f  cmp     eax, 2
0x18008b712  jbe     short loc_18008B743
0x18008b714  lea     rax, aReachedMaxLimi_0; "Reached max limit of sessions on the ho"...
0x18008b71b  mov     qword ptr [rsp+0B8h+var_68.Data1], rax
0x18008b720  lea     rax, [rsp+0B8h+var_68]
0x18008b725  mov     [rsp+0B8h+var_98], rax
0x18008b72a  xor     r9d, r9d
0x18008b72d  xor     r8d, r8d
0x18008b730  lea     rdx, word_1800CB052
0x18008b737  lea     rcx, dword_1800DA020
0x18008b73e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008b743  mov     ebx, 161h
0x18008b748  mov     rcx, qword ptr [rsp+0B8h+requestedAccess]; computeSystem
0x18008b74d  test    rcx, rcx
0x18008b750  jz      short loc_18008B759
0x18008b752  call    cs:__imp_HcsCloseComputeSystem
0x18008b758  nop
0x18008b759  lea     rcx, [rsp+0B8h+id]
0x18008b75e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008b763  nop
0x18008b764  jmp     loc_18008B92D
0x18008b769  lea     rcx, [rdi+28h]; lpCriticalSection
0x18008b76d  call    cs:__imp_EnterCriticalSection
0x18008b773  mov     [rsp+0B8h+var_88], 0
0x18008b77b  movups  xmm0, xmmword ptr [r14]
0x18008b77f  movdqu  xmmword ptr [rsp+0B8h+var_68.Data1], xmm0
0x18008b785  lea     r8, [rsp+0B8h+var_88]; unsigned int *
0x18008b78a  lea     rdx, [rsp+0B8h+var_68]; struct _GUID
0x18008b78f  mov     rcx, rdi; this
0x18008b792  call    ?GetContainerSessionCount@ContainerSessionServer@@QEAAJU_GUID@@PEAI@Z; ContainerSessionServer::GetContainerSessionCount(_GUID,uint *)
0x18008b797  test    eax, eax
0x18008b799  jnz     loc_18008B823
0x18008b79f  mov     rcx, qword ptr [rsp+0B8h+requestedAccess]; computeSystem
0x18008b7a4  test    rcx, rcx
0x18008b7a7  jz      short loc_18008B7AF
0x18008b7a9  call    cs:__imp_HcsCloseComputeSystem
0x18008b7af  cmp     [rsp+0B8h+var_88], 2
0x18008b7b4  jb      short loc_18008B807
0x18008b7b6  mov     eax, cs:dword_1800DA020
0x18008b7bc  cmp     eax, 2
0x18008b7bf  jbe     short loc_18008B7F0
0x18008b7c1  lea     rax, aReachedMaxLimi; "Reached max limit of sessions per conta"...
0x18008b7c8  mov     qword ptr [rsp+0B8h+var_68.Data1], rax
0x18008b7cd  lea     rax, [rsp+0B8h+var_68]
0x18008b7d2  mov     [rsp+0B8h+var_98], rax
0x18008b7d7  xor     r9d, r9d
0x18008b7da  xor     r8d, r8d
0x18008b7dd  lea     rdx, word_1800CB2CA
0x18008b7e4  lea     rcx, dword_1800DA020
0x18008b7eb  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008b7f0  mov     edx, 1; unsigned int
0x18008b7f5  mov     rcx, rdi; this
0x18008b7f8  call    ?DecreaseTotalSessionCount@ContainerSessionServer@@QEAAXI@Z; ContainerSessionServer::DecreaseTotalSessionCount(uint)
0x18008b7fd  mov     ebx, 161h
0x18008b802  jmp     loc_18008B911
0x18008b807  lea     rcx, [rdi+18h]
0x18008b80b  mov     r8, r14
0x18008b80e  lea     rdx, [rsp+0B8h+var_68]
0x18008b813  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@IUGUIDComparer@@V?$allocator@U?$pair@$$CBU_GUID@@I@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@I@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,uint,GUIDComparer,std::allocator<std::pair<_GUID const,uint>>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x18008b818  mov     rax, [rax]
0x18008b81b  inc     dword ptr [rax+2Ch]
0x18008b81e  jmp     loc_18008B90F
0x18008b823  mov     ecx, 18h; Size
0x18008b828  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008b82d  mov     rbx, rax
0x18008b830  mov     ecx, 8; Size
0x18008b835  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008b83a  mov     r15, rax
0x18008b83d  movups  xmm0, xmmword ptr [r14]
0x18008b841  movdqu  xmmword ptr [rbx], xmm0
0x18008b845  mov     [rbx+10h], rax
0x18008b849  movdqu  xmmword ptr [r14], xmm0
0x18008b84e  mov     r9, rax
0x18008b851  mov     r8, rbx
0x18008b854  lea     rdx, ?NotificationWatcher@@YAXKPEAXJPEBG@Z; NotificationWatcher(ulong,void *,long,ushort const *)
0x18008b85b  mov     rcx, qword ptr [rsp+0B8h+requestedAccess]
0x18008b860  call    cs:__imp_HcsRegisterComputeSystemCallback
0x18008b866  test    eax, eax
0x18008b868  jns     loc_18008B8F4
0x18008b86e  mov     ecx, cs:dword_1800DA020
0x18008b874  cmp     ecx, 2
0x18008b877  jbe     short loc_18008B8B6
0x18008b879  mov     [rsp+0B8h+var_88], eax
0x18008b87d  lea     rax, aHcsregistercom_0; "HcsRegisterComputeSystemCallback failed"...
0x18008b884  mov     qword ptr [rsp+0B8h+var_68.Data1], rax
0x18008b889  lea     rax, [rsp+0B8h+var_88]
0x18008b88e  mov     [rsp+0B8h+var_90], rax
0x18008b893  lea     rax, [rsp+0B8h+var_68]
0x18008b898  mov     [rsp+0B8h+var_98], rax
0x18008b89d  xor     r9d, r9d
0x18008b8a0  xor     r8d, r8d
0x18008b8a3  lea     rdx, byte_1800CB029
0x18008b8aa  lea     rcx, dword_1800DA020
0x18008b8b1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008b8b6  mov     edx, 1; unsigned int
0x18008b8bb  mov     rcx, rdi; this
0x18008b8be  call    ?DecreaseTotalSessionCount@ContainerSessionServer@@QEAAXI@Z; ContainerSessionServer::DecreaseTotalSessionCount(uint)
0x18008b8c3  mov     rcx, qword ptr [rsp+0B8h+requestedAccess]; computeSystem
0x18008b8c8  test    rcx, rcx
0x18008b8cb  jz      short loc_18008B8D3
0x18008b8cd  call    cs:__imp_HcsCloseComputeSystem
0x18008b8d3  mov     edx, 18h; struct std::nothrow_t *
0x18008b8d8  mov     rcx, rbx; void *
0x18008b8db  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008b8e0  mov     edx, 8; struct std::nothrow_t *
0x18008b8e5  mov     rcx, r15; void *
0x18008b8e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008b8ed  mov     ebx, 54Fh
0x18008b8f2  jmp     short loc_18008B911
0x18008b8f4  lea     rcx, [rdi+18h]
0x18008b8f8  mov     r8, r14
0x18008b8fb  lea     rdx, [rsp+0B8h+var_68]
0x18008b900  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@IUGUIDComparer@@V?$allocator@U?$pair@$$CBU_GUID@@I@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@I@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,uint,GUIDComparer,std::allocator<std::pair<_GUID const,uint>>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x18008b905  mov     rax, [rax]
0x18008b908  mov     dword ptr [rax+2Ch], 1
0x18008b90f  xor     ebx, ebx
0x18008b911  lea     rcx, [rdi+28h]; lpCriticalSection
0x18008b915  call    cs:__imp_LeaveCriticalSection
0x18008b91b  nop
0x18008b91c  lea     rcx, [rsp+0B8h+id]
0x18008b921  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008b926  nop
0x18008b927  jmp     short loc_18008B92D
0x18008b929  mov     ebx, [rsp+0B8h+var_88]
0x18008b92d  mov     eax, ebx
0x18008b92f  mov     rcx, [rsp+0B8h+var_28]
0x18008b937  xor     rcx, rsp; StackCookie
0x18008b93a  call    __security_check_cookie
0x18008b93f  lea     r11, [rsp+0B8h+var_18]
0x18008b947  mov     rbx, [r11+30h]
0x18008b94b  mov     rdi, [r11+38h]
0x18008b94f  mov     rsp, r11
0x18008b952  pop     r15
0x18008b954  pop     r14
0x18008b956  pop     r12
0x18008b958  retn
0x18008b959  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
