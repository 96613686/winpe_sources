# CSpJobMgr::CreateJob(ushort const *,SM_CONSTANTS::JOB_TYPE,SpSubsystemType,int,_SP_OBJECT_ID *,WSP_OBJECT_TYPE,ushort const *,_GUID *)

- ea: `0x18005cfec`
- end: `0x18005d2e8`
- name: `?CreateJob@CSpJobMgr@@QEAAHPEBGW4JOB_TYPE@SM_CONSTANTS@@W4SpSubsystemType@@HPEAU_SP_OBJECT_ID@@W4WSP_OBJECT_TYPE@@0PEAU_GUID@@@Z`
- size: `764`
- prototype: ``
- caller_count: `11`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001489c`
- `0x180072968`
- `0x1800729bc`
- `0x180072a1c`
- `0x1800c19e0`
- `0x1800c35f8`
- `0x1800c3658`
- `0x1800c36b8`
- `0x1800e4270`
- `0x1800e64fc`
- `0x1800f5114`

## callees

- `0x1800011b0`
- `0x1800015b8`
- `0x180006290`
- `0x1800175f0`
- `0x18001a5e4`
- `0x180028f84`
- `0x18003902c`
- `0x18005cfec`
- `0x18005e020`
- `0x1800668f8`
- `0x1800aff8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d257`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d257`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005d17d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005d17d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d243`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d243`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d280`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d280`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18005d0a8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18005d0a8`

## string_xrefs

- `0x18005d021`: `CSpJobMgr::CreateJob`
- `0x18005d134`: `CSpJobMgr::CreateJob`
- `0x18005d1c9`: `CSpJobMgr::CreateJob`
- `0x18005d239`: `CSpJobMgr::CreateJob`
- `0x18005d25d`: `CSpJobMgr::CreateJob`

## pseudocode

```c
_BOOL8 __fastcall CSpJobMgr::CreateJob(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        const char *a6,
        int a7,
        const char *a8,
        GUID *a9)
{
  unsigned int v10; // r13d
  unsigned int v11; // r14d
  unsigned int *v13; // rbx
  int v14; // edi
  enum _MI_Result v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // esi
  DWORD v20; // ecx
  int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  int v27; // [rsp+20h] [rbp-99h]
  HLOCAL hMem; // [rsp+50h] [rbp-69h] BYREF
  int v29; // [rsp+58h] [rbp-61h]
  const char *v30; // [rsp+60h] [rbp-59h] BYREF
  const char *v31; // [rsp+68h] [rbp-51h] BYREF
  _DWORD v32[2]; // [rsp+70h] [rbp-49h] BYREF
  char v33; // [rsp+78h] [rbp-41h]
  GUID *v34; // [rsp+80h] [rbp-39h] BYREF
  GUID v35; // [rsp+90h] [rbp-29h] BYREF
  GUID pguid; // [rsp+A0h] [rbp-19h] BYREF

  v30 = a6;
  v10 = a4;
  v31 = a8;
  v11 = a3;
  v34 = a9;
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v29 = 160;
    hMem = "CSpJobMgr::CreateJob";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"CSpJobMgr::CreateJob",
      (__int64)byte_18030A6D3,
      a3,
      a4,
      &hMem);
  }
  v13 = 0;
  hMem = 0;
  pguid = 0;
  v32[1] = 0;
  v14 = 0;
  v33 = 0;
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 )
  {
    v19 = 0;
    if ( v15 == MI_RESULT_SERVER_IS_SHUTTING_DOWN )
    {
      v20 = 1115;
      goto LABEL_18;
    }
  }
  else
  {
    v19 = 1;
    v32[0] = CoCreateGuid(&pguid);
    v14 = v32[0];
    if ( v32[0] < 0 )
    {
      v20 = _status_t::ToWin32((_status_t *)v32);
LABEL_18:
      SetLastError(v20);
      goto LABEL_19;
    }
    v35 = pguid;
    v21 = CreateSuexJob(a2, v11, &v35, v10, a5, v30, a7, v31, &hMem);
    _status_t::SetBoolGle((_status_t *)v32, v21);
    v14 = v32[0];
    if ( v32[0] >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
      v13 = (unsigned int *)hMem;
      v35 = pguid;
      v22 = CSuMap<_MI_Instance *>::Insert(a1 + 80, &v35, hMem);
      _status_t::SetBoolGle((_status_t *)v32, v22);
      v14 = v32[0];
      if ( v32[0] >= 0 )
      {
        LOWORD(v27) = 0;
        CSpIndication::SendIndication(2, 0, 0, L"Storage Job Arrival", v27, L"SPACES_StorageJob", (char *)v13 + v13[14]);
        v13 = 0;
        *v34 = pguid;
      }
      else if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v31) = v32[0];
        LODWORD(hMem) = 214;
        v30 = "CSpJobMgr::CreateJob";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v23,
          (__int64)byte_180309D45,
          v24,
          v25,
          &v30);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    }
    else
    {
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        v29 = v32[0];
        LODWORD(v30) = 203;
        v31 = "CSpJobMgr::CreateJob";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v16,
          (__int64)&dword_18030A274,
          v17,
          v18,
          &v31);
      }
      v13 = (unsigned int *)hMem;
    }
  }
LABEL_19:
  if ( v14 < 0 && v19 )
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  if ( v13 )
    LocalFree(v13);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(hMem) = 248;
    v34 = (GUID *)"CSpJobMgr::CreateJob";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v16,
      (__int64)word_18030A3D2,
      v17,
      v18,
      &v34);
  }
  return v14 >= 0;
}

```

## disassembly

```asm
0x18005cfec  mov     [rsp-8+arg_10], rbx
0x18005cff1  push    rbp
0x18005cff2  push    rsi
0x18005cff3  push    rdi
0x18005cff4  push    r12
0x18005cff6  push    r13
0x18005cff8  push    r14
0x18005cffa  push    r15
0x18005cffc  lea     rbp, [rsp-7]
0x18005d001  sub     rsp, 0C0h
0x18005d008  mov     rax, cs:__security_cookie
0x18005d00f  xor     rax, rsp
0x18005d012  mov     [rbp+37h+var_40], rax
0x18005d016  mov     rax, [rbp+37h+arg_28]
0x18005d01a  mov     r15, rcx
0x18005d01d  mov     [rbp+37h+var_90], rax
0x18005d021  lea     rcx, aCspjobmgrCreat_0; "CSpJobMgr::CreateJob"
0x18005d028  mov     rax, [rbp+37h+arg_38]
0x18005d02c  mov     r13d, r9d
0x18005d02f  mov     [rbp+37h+var_88], rax
0x18005d033  mov     r14d, r8d
0x18005d036  mov     rax, [rbp+37h+arg_40]
0x18005d03d  mov     r12, rdx
0x18005d040  mov     [rbp+37h+var_70], rax
0x18005d044  mov     eax, cs:dword_180397B68
0x18005d04a  cmp     eax, 5
0x18005d04d  jbe     short loc_18005D078
0x18005d04f  lea     rax, [rbp+37h+var_98]
0x18005d053  mov     [rbp+37h+var_98], 0A0h
0x18005d05a  mov     [rsp+0F0h+var_C8], rax
0x18005d05f  lea     rdx, byte_18030A6D3
0x18005d066  lea     rax, [rbp+37h+hMem]
0x18005d06a  mov     [rbp+37h+hMem], rcx
0x18005d06e  mov     [rsp+0F0h+var_D0], rax
0x18005d073  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005d078  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18005d07f  xor     ebx, ebx
0x18005d081  xorps   xmm0, xmm0
0x18005d084  mov     [rbp+37h+hMem], rbx
0x18005d088  movups  xmmword ptr [rbp+37h+pguid.Data1], xmm0
0x18005d08c  mov     [rbp+37h+var_7C], ebx
0x18005d08f  xor     edi, edi
0x18005d091  mov     [rbp+37h+var_78], bl
0x18005d094  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18005d099  test    eax, eax
0x18005d09b  jnz     loc_18005D24B
0x18005d0a1  lea     rcx, [rbp+37h+pguid]; pguid
0x18005d0a5  lea     esi, [rbx+1]
0x18005d0a8  call    cs:__imp_CoCreateGuid
0x18005d0ae  mov     [rbp+37h+var_80], eax
0x18005d0b1  mov     edi, eax
0x18005d0b3  test    eax, eax
0x18005d0b5  jns     short loc_18005D0C7
0x18005d0b7  lea     rcx, [rbp+37h+var_80]; this
0x18005d0bb  call    ?ToWin32@_status_t@@QEAAKXZ; _status_t::ToWin32(void)
0x18005d0c0  mov     ecx, eax
0x18005d0c2  jmp     loc_18005D257
0x18005d0c7  movaps  xmm0, xmmword ptr [rbp+37h+pguid.Data1]
0x18005d0cb  lea     rax, [rbp+37h+hMem]
0x18005d0cf  mov     [rsp+0F0h+var_B0], rax
0x18005d0d4  lea     r8, [rbp+37h+var_60]
0x18005d0d8  mov     rax, [rbp+37h+var_88]
0x18005d0dc  mov     r9d, r13d
0x18005d0df  mov     [rsp+0F0h+var_B8], rax
0x18005d0e4  mov     edx, r14d
0x18005d0e7  mov     eax, [rbp+37h+arg_30]
0x18005d0ea  mov     rcx, r12
0x18005d0ed  mov     dword ptr [rsp+0F0h+var_C0], eax
0x18005d0f1  mov     rax, [rbp+37h+var_90]
0x18005d0f5  mov     [rsp+0F0h+var_C8], rax
0x18005d0fa  mov     eax, [rbp+37h+arg_20]
0x18005d0fd  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18005d101  movdqa  [rbp+37h+var_60], xmm0
0x18005d106  call    ?CreateSuexJob@@YAHPEBGW4JOB_TYPE@SM_CONSTANTS@@U_GUID@@W4SpSubsystemType@@HPEAU_SP_OBJECT_ID@@W4WSP_OBJECT_TYPE@@0PEAPEAU_SUEX_JOB_OBJECT@@@Z; CreateSuexJob(ushort const *,SM_CONSTANTS::JOB_TYPE,_GUID,SpSubsystemType,int,_SP_OBJECT_ID *,WSP_OBJECT_TYPE,ushort const *,_SUEX_JOB_OBJECT * *)
0x18005d10b  mov     edx, eax; int
0x18005d10d  lea     rcx, [rbp+37h+var_80]; this
0x18005d111  call    ?SetBoolGle@_status_t@@QEAAJH@Z; _status_t::SetBoolGle(int)
0x18005d116  mov     edi, [rbp+37h+var_80]
0x18005d119  test    edi, edi
0x18005d11b  jns     short loc_18005D176
0x18005d11d  mov     eax, cs:dword_180397B68
0x18005d123  cmp     eax, 2
0x18005d126  jbe     short loc_18005D16D
0x18005d128  lea     rax, [rbp+37h+var_98]
0x18005d12c  mov     [rbp+37h+var_98], edi
0x18005d12f  mov     [rsp+0F0h+var_C0], rax
0x18005d134  lea     r15, aCspjobmgrCreat_0; "CSpJobMgr::CreateJob"
0x18005d13b  lea     rax, [rbp+37h+var_90]
0x18005d13f  mov     dword ptr [rbp+37h+var_90], 0CBh
0x18005d146  mov     [rsp+0F0h+var_C8], rax
0x18005d14b  lea     rdx, dword_18030A274
0x18005d152  lea     rax, [rbp+37h+var_88]
0x18005d156  mov     [rbp+37h+var_88], r15
0x18005d15a  mov     [rsp+0F0h+var_D0], rax
0x18005d15f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005d164  mov     rbx, [rbp+37h+hMem]
0x18005d168  jmp     loc_18005D264
0x18005d16d  mov     rbx, [rbp+37h+hMem]
0x18005d171  jmp     loc_18005D25D
0x18005d176  lea     r14, [r15+8]
0x18005d17a  mov     rcx, r14; lpCriticalSection
0x18005d17d  call    cs:__imp_EnterCriticalSection
0x18005d183  movaps  xmm0, xmmword ptr [rbp+37h+pguid.Data1]
0x18005d187  lea     rcx, [r15+50h]
0x18005d18b  mov     rbx, [rbp+37h+hMem]
0x18005d18f  lea     rdx, [rbp+37h+var_60]
0x18005d193  mov     r8, rbx
0x18005d196  movdqa  [rbp+37h+var_60], xmm0
0x18005d19b  call    ?Insert@?$CSuMap@PEAU_MI_Instance@@@@QEAAHU_GUID@@PEAU_MI_Instance@@@Z; CSuMap<_MI_Instance *>::Insert(_GUID,_MI_Instance *)
0x18005d1a0  mov     edx, eax; int
0x18005d1a2  lea     rcx, [rbp+37h+var_80]; this
0x18005d1a6  call    ?SetBoolGle@_status_t@@QEAAJH@Z; _status_t::SetBoolGle(int)
0x18005d1ab  mov     edi, [rbp+37h+var_80]
0x18005d1ae  test    edi, edi
0x18005d1b0  jns     short loc_18005D1FB
0x18005d1b2  mov     eax, cs:dword_180397B68
0x18005d1b8  cmp     eax, 2
0x18005d1bb  jbe     short loc_18005D239
0x18005d1bd  lea     rax, [rbp+37h+var_88]
0x18005d1c1  mov     dword ptr [rbp+37h+var_88], edi
0x18005d1c4  mov     [rsp+0F0h+var_C0], rax
0x18005d1c9  lea     r15, aCspjobmgrCreat_0; "CSpJobMgr::CreateJob"
0x18005d1d0  lea     rax, [rbp+37h+hMem]
0x18005d1d4  mov     dword ptr [rbp+37h+hMem], 0D6h
0x18005d1db  mov     [rsp+0F0h+var_C8], rax
0x18005d1e0  lea     rdx, byte_180309D45
0x18005d1e7  lea     rax, [rbp+37h+var_90]
0x18005d1eb  mov     [rbp+37h+var_90], r15
0x18005d1ef  mov     [rsp+0F0h+var_D0], rax
0x18005d1f4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005d1f9  jmp     short loc_18005D240
0x18005d1fb  mov     eax, [rbx+38h]
0x18005d1fe  lea     r9, aStorageJobArri; "Storage Job Arrival"
0x18005d205  add     rax, rbx
0x18005d208  xor     edx, edx
0x18005d20a  mov     [rsp+0F0h+var_C0], rax
0x18005d20f  xor     r8d, r8d
0x18005d212  lea     rax, aSpacesStoragej_11; "SPACES_StorageJob"
0x18005d219  mov     [rsp+0F0h+var_C8], rax
0x18005d21e  lea     ecx, [rdx+2]
0x18005d221  mov     word ptr [rsp+0F0h+var_D0], dx
0x18005d226  call    ?SendIndication@CSpIndication@@SA?AW4_MI_Result@@W4INDICATION_TYPE@SP_CONSTANTS@@HGPEBGG11@Z; CSpIndication::SendIndication(SP_CONSTANTS::INDICATION_TYPE,int,ushort,ushort const *,ushort,ushort const *,ushort const *)
0x18005d22b  mov     rax, [rbp+37h+var_70]
0x18005d22f  xor     ebx, ebx
0x18005d231  movaps  xmm0, xmmword ptr [rbp+37h+pguid.Data1]
0x18005d235  movdqu  xmmword ptr [rax], xmm0
0x18005d239  lea     r15, aCspjobmgrCreat_0; "CSpJobMgr::CreateJob"
0x18005d240  mov     rcx, r14; lpCriticalSection
0x18005d243  call    cs:__imp_LeaveCriticalSection
0x18005d249  jmp     short loc_18005D264
0x18005d24b  xor     esi, esi
0x18005d24d  cmp     eax, 1Ch
0x18005d250  jnz     short loc_18005D25D
0x18005d252  mov     ecx, 45Bh; dwErrCode
0x18005d257  call    cs:__imp_SetLastError
0x18005d25d  lea     r15, aCspjobmgrCreat_0; "CSpJobMgr::CreateJob"
0x18005d264  test    edi, edi
0x18005d266  jns     short loc_18005D278
0x18005d268  test    esi, esi
0x18005d26a  jz      short loc_18005D278
0x18005d26c  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18005d273  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18005d278  test    rbx, rbx
0x18005d27b  jz      short loc_18005D286
0x18005d27d  mov     rcx, rbx; hMem
0x18005d280  call    cs:__imp_LocalFree
0x18005d286  mov     eax, cs:dword_180397B68
0x18005d28c  cmp     eax, 5
0x18005d28f  jbe     short loc_18005D2BA
0x18005d291  lea     rax, [rbp+37h+hMem]
0x18005d295  mov     dword ptr [rbp+37h+hMem], 0F8h
0x18005d29c  mov     [rsp+0F0h+var_C8], rax
0x18005d2a1  lea     rdx, word_18030A3D2
0x18005d2a8  lea     rax, [rbp+37h+var_70]
0x18005d2ac  mov     [rbp+37h+var_70], r15
0x18005d2b0  mov     [rsp+0F0h+var_D0], rax
0x18005d2b5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005d2ba  xor     eax, eax
0x18005d2bc  test    edi, edi
0x18005d2be  setns   al
0x18005d2c1  mov     rcx, [rbp+37h+var_40]
0x18005d2c5  xor     rcx, rsp; StackCookie
0x18005d2c8  call    __security_check_cookie
0x18005d2cd  mov     rbx, [rsp+0F0h+arg_10]
0x18005d2d5  add     rsp, 0C0h
0x18005d2dc  pop     r15
0x18005d2de  pop     r14
0x18005d2e0  pop     r13
0x18005d2e2  pop     r12
0x18005d2e4  pop     rdi
0x18005d2e5  pop     rsi
0x18005d2e6  pop     rbp
0x18005d2e7  retn
```
