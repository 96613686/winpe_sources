# CSpJobMgr::CreateJob(ushort const *,SM_CONSTANTS::JOB_TYPE,SpSubsystemType,int,_SP_OBJECT_ID *,WSP_OBJECT_TYPE,ushort const *,_GUID *)

- ea: `0x18005ee20`
- end: `0x18005f13b`
- name: `?CreateJob@CSpJobMgr@@QEAAHPEBGW4JOB_TYPE@SM_CONSTANTS@@W4SpSubsystemType@@HPEAU_SP_OBJECT_ID@@W4WSP_OBJECT_TYPE@@0PEAU_GUID@@@Z`
- size: `795`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180014bd4`
- `0x180074d10`
- `0x180074d64`
- `0x180074dc4`
- `0x1800c4ad0`
- `0x1800c6610`
- `0x1800c6670`
- `0x1800c66d0`
- `0x1800e78d0`
- `0x1800e9a48`
- `0x1800f8904`

## callees

- `0x1800011c4`
- `0x1800015d8`
- `0x180006350`
- `0x1800179c0`
- `0x18001aa70`
- `0x180029b04`
- `0x18003a1c8`
- `0x18005ee20`
- `0x18005fed4`
- `0x180068a28`
- `0x1800b2bc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f09d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f09d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005efb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005efb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f083`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f083`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f0cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f0cc`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18005eedc`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18005eedc`

## string_xrefs

- `0x18005ee55`: `CSpJobMgr::CreateJob`
- `0x18005ef6e`: `CSpJobMgr::CreateJob`
- `0x18005f009`: `CSpJobMgr::CreateJob`
- `0x18005f079`: `CSpJobMgr::CreateJob`
- `0x18005f0a9`: `CSpJobMgr::CreateJob`

## pseudocode

```c
_BOOL8 __fastcall CSpJobMgr::CreateJob(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        const char *a6,
        int a7,
        const char *a8,
        GUID *a9)
{
  unsigned int *v13; // rbx
  int v14; // edi
  enum _MI_Result v15; // eax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // esi
  DWORD v20; // ecx
  int v21; // eax
  int v22; // eax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int v27; // [rsp+20h] [rbp-99h]
  HLOCAL hMem; // [rsp+50h] [rbp-69h] BYREF
  int v29; // [rsp+58h] [rbp-61h] BYREF
  const char *v30; // [rsp+60h] [rbp-59h] BYREF
  const char *v31; // [rsp+68h] [rbp-51h] BYREF
  _DWORD v32[2]; // [rsp+70h] [rbp-49h] BYREF
  char v33; // [rsp+78h] [rbp-41h]
  GUID *v34; // [rsp+80h] [rbp-39h] BYREF
  GUID v35; // [rsp+90h] [rbp-29h] BYREF
  GUID pguid; // [rsp+A0h] [rbp-19h] BYREF

  v30 = a6;
  v31 = a8;
  v34 = a9;
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v29 = 160;
    hMem = "CSpJobMgr::CreateJob";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"CSpJobMgr::CreateJob",
      (unsigned int)byte_18031165B,
      a3,
      a4,
      (__int64)&hMem,
      (__int64)&v29);
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
    v21 = CreateSuexJob(a2, a3, &v35, a4, a5, v30, a7, v31, &hMem);
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
      else if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v31) = v32[0];
        LODWORD(hMem) = 214;
        v30 = "CSpJobMgr::CreateJob";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v23,
          (unsigned int)byte_180310CCD,
          v24,
          v25,
          (__int64)&v30,
          (__int64)&hMem,
          (__int64)&v31);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    }
    else
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v29 = v32[0];
        LODWORD(v30) = 203;
        v31 = "CSpJobMgr::CreateJob";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v16,
          (unsigned int)&dword_1803111FC,
          v17,
          v18,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&v29);
      }
      v13 = (unsigned int *)hMem;
    }
  }
LABEL_19:
  if ( v14 < 0 && v19 )
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  if ( v13 )
    LocalFree(v13);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(hMem) = 248;
    v34 = (GUID *)"CSpJobMgr::CreateJob";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v16,
      (unsigned int)word_18031135A,
      v17,
      v18,
      (__int64)&v34,
      (__int64)&hMem);
  }
  return v14 >= 0;
}

```

## disassembly

```asm
0x18005ee20  mov     [rsp-8+arg_10], rbx
0x18005ee25  push    rbp
0x18005ee26  push    rsi
0x18005ee27  push    rdi
0x18005ee28  push    r12
0x18005ee2a  push    r13
0x18005ee2c  push    r14
0x18005ee2e  push    r15
0x18005ee30  lea     rbp, [rsp-7]
0x18005ee35  sub     rsp, 0C0h
0x18005ee3c  mov     rax, cs:__security_cookie
0x18005ee43  xor     rax, rsp
0x18005ee46  mov     [rbp+37h+var_40], rax
0x18005ee4a  mov     rax, [rbp+37h+arg_28]
0x18005ee4e  mov     r15, rcx
0x18005ee51  mov     [rbp+37h+var_90], rax
0x18005ee55  lea     rcx, aCspjobmgrCreat_0; "CSpJobMgr::CreateJob"
0x18005ee5c  mov     rax, [rbp+37h+arg_38]
0x18005ee60  mov     r13d, r9d
0x18005ee63  mov     [rbp+37h+var_88], rax
0x18005ee67  mov     r14d, r8d
0x18005ee6a  mov     rax, [rbp+37h+arg_40]
0x18005ee71  mov     r12, rdx
0x18005ee74  mov     [rbp+37h+var_70], rax
0x18005ee78  mov     eax, cs:dword_18039EB68
0x18005ee7e  cmp     eax, 5
0x18005ee81  jbe     short loc_18005EEAC
0x18005ee83  lea     rax, [rbp+37h+var_98]
0x18005ee87  mov     [rbp+37h+var_98], 0A0h
0x18005ee8e  mov     [rsp+0F0h+var_C8], rax
0x18005ee93  lea     rdx, byte_18031165B
0x18005ee9a  lea     rax, [rbp+37h+hMem]
0x18005ee9e  mov     [rbp+37h+hMem], rcx
0x18005eea2  mov     [rsp+0F0h+var_D0], rax
0x18005eea7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005eeac  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18005eeb3  xor     ebx, ebx
0x18005eeb5  xorps   xmm0, xmm0
0x18005eeb8  mov     [rbp+37h+hMem], rbx
0x18005eebc  movups  xmmword ptr [rbp+37h+pguid.Data1], xmm0
0x18005eec0  mov     [rbp+37h+var_7C], ebx
0x18005eec3  xor     edi, edi
0x18005eec5  mov     [rbp+37h+var_78], bl
0x18005eec8  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18005eecd  test    eax, eax
0x18005eecf  jnz     loc_18005F091
0x18005eed5  lea     rcx, [rbp+37h+pguid]; pguid
0x18005eed9  lea     esi, [rbx+1]
0x18005eedc  call    cs:__imp_CoCreateGuid
0x18005eee3  nop     dword ptr [rax+rax+00h]
0x18005eee8  mov     [rbp+37h+var_80], eax
0x18005eeeb  mov     edi, eax
0x18005eeed  test    eax, eax
0x18005eeef  jns     short loc_18005EF01
0x18005eef1  lea     rcx, [rbp+37h+var_80]; this
0x18005eef5  call    ?ToWin32@_status_t@@QEAAKXZ; _status_t::ToWin32(void)
0x18005eefa  mov     ecx, eax
0x18005eefc  jmp     loc_18005F09D
0x18005ef01  movaps  xmm0, xmmword ptr [rbp+37h+pguid.Data1]
0x18005ef05  lea     rax, [rbp+37h+hMem]
0x18005ef09  mov     [rsp+0F0h+var_B0], rax
0x18005ef0e  lea     r8, [rbp+37h+var_60]
0x18005ef12  mov     rax, [rbp+37h+var_88]
0x18005ef16  mov     r9d, r13d
0x18005ef19  mov     [rsp+0F0h+var_B8], rax
0x18005ef1e  mov     edx, r14d
0x18005ef21  mov     eax, [rbp+37h+arg_30]
0x18005ef24  mov     rcx, r12
0x18005ef27  mov     dword ptr [rsp+0F0h+var_C0], eax
0x18005ef2b  mov     rax, [rbp+37h+var_90]
0x18005ef2f  mov     [rsp+0F0h+var_C8], rax
0x18005ef34  mov     eax, [rbp+37h+arg_20]
0x18005ef37  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18005ef3b  movdqa  [rbp+37h+var_60], xmm0
0x18005ef40  call    ?CreateSuexJob@@YAHPEBGW4JOB_TYPE@SM_CONSTANTS@@U_GUID@@W4SpSubsystemType@@HPEAU_SP_OBJECT_ID@@W4WSP_OBJECT_TYPE@@0PEAPEAU_SUEX_JOB_OBJECT@@@Z; CreateSuexJob(ushort const *,SM_CONSTANTS::JOB_TYPE,_GUID,SpSubsystemType,int,_SP_OBJECT_ID *,WSP_OBJECT_TYPE,ushort const *,_SUEX_JOB_OBJECT * *)
0x18005ef45  mov     edx, eax; int
0x18005ef47  lea     rcx, [rbp+37h+var_80]; this
0x18005ef4b  call    ?SetBoolGle@_status_t@@QEAAJH@Z; _status_t::SetBoolGle(int)
0x18005ef50  mov     edi, [rbp+37h+var_80]
0x18005ef53  test    edi, edi
0x18005ef55  jns     short loc_18005EFB0
0x18005ef57  mov     eax, cs:dword_18039EB68
0x18005ef5d  cmp     eax, 2
0x18005ef60  jbe     short loc_18005EFA7
0x18005ef62  lea     rax, [rbp+37h+var_98]
0x18005ef66  mov     [rbp+37h+var_98], edi
0x18005ef69  mov     [rsp+0F0h+var_C0], rax
0x18005ef6e  lea     r15, aCspjobmgrCreat_0; "CSpJobMgr::CreateJob"
0x18005ef75  lea     rax, [rbp+37h+var_90]
0x18005ef79  mov     dword ptr [rbp+37h+var_90], 0CBh
0x18005ef80  mov     [rsp+0F0h+var_C8], rax
0x18005ef85  lea     rdx, dword_1803111FC
0x18005ef8c  lea     rax, [rbp+37h+var_88]
0x18005ef90  mov     [rbp+37h+var_88], r15
0x18005ef94  mov     [rsp+0F0h+var_D0], rax
0x18005ef99  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005ef9e  mov     rbx, [rbp+37h+hMem]
0x18005efa2  jmp     loc_18005F0B0
0x18005efa7  mov     rbx, [rbp+37h+hMem]
0x18005efab  jmp     loc_18005F0A9
0x18005efb0  lea     r14, [r15+8]
0x18005efb4  mov     rcx, r14; lpCriticalSection
0x18005efb7  call    cs:__imp_EnterCriticalSection
0x18005efbe  nop     dword ptr [rax+rax+00h]
0x18005efc3  movaps  xmm0, xmmword ptr [rbp+37h+pguid.Data1]
0x18005efc7  lea     rcx, [r15+50h]
0x18005efcb  mov     rbx, [rbp+37h+hMem]
0x18005efcf  lea     rdx, [rbp+37h+var_60]
0x18005efd3  mov     r8, rbx
0x18005efd6  movdqa  [rbp+37h+var_60], xmm0
0x18005efdb  call    ?Insert@?$CSuMap@PEAU_MI_Instance@@@@QEAAHU_GUID@@PEAU_MI_Instance@@@Z; CSuMap<_MI_Instance *>::Insert(_GUID,_MI_Instance *)
0x18005efe0  mov     edx, eax; int
0x18005efe2  lea     rcx, [rbp+37h+var_80]; this
0x18005efe6  call    ?SetBoolGle@_status_t@@QEAAJH@Z; _status_t::SetBoolGle(int)
0x18005efeb  mov     edi, [rbp+37h+var_80]
0x18005efee  test    edi, edi
0x18005eff0  jns     short loc_18005F03B
0x18005eff2  mov     eax, cs:dword_18039EB68
0x18005eff8  cmp     eax, 2
0x18005effb  jbe     short loc_18005F079
0x18005effd  lea     rax, [rbp+37h+var_88]
0x18005f001  mov     dword ptr [rbp+37h+var_88], edi
0x18005f004  mov     [rsp+0F0h+var_C0], rax
0x18005f009  lea     r15, aCspjobmgrCreat_0; "CSpJobMgr::CreateJob"
0x18005f010  lea     rax, [rbp+37h+hMem]
0x18005f014  mov     dword ptr [rbp+37h+hMem], 0D6h
0x18005f01b  mov     [rsp+0F0h+var_C8], rax
0x18005f020  lea     rdx, byte_180310CCD
0x18005f027  lea     rax, [rbp+37h+var_90]
0x18005f02b  mov     [rbp+37h+var_90], r15
0x18005f02f  mov     [rsp+0F0h+var_D0], rax
0x18005f034  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005f039  jmp     short loc_18005F080
0x18005f03b  mov     eax, [rbx+38h]
0x18005f03e  lea     r9, aStorageJobArri; "Storage Job Arrival"
0x18005f045  add     rax, rbx
0x18005f048  xor     edx, edx
0x18005f04a  mov     [rsp+0F0h+var_C0], rax
0x18005f04f  xor     r8d, r8d
0x18005f052  lea     rax, aSpacesStoragej_11; "SPACES_StorageJob"
0x18005f059  mov     [rsp+0F0h+var_C8], rax
0x18005f05e  lea     ecx, [rdx+2]
0x18005f061  mov     word ptr [rsp+0F0h+var_D0], dx
0x18005f066  call    ?SendIndication@CSpIndication@@SA?AW4_MI_Result@@W4INDICATION_TYPE@SP_CONSTANTS@@HGPEBGG11@Z; CSpIndication::SendIndication(SP_CONSTANTS::INDICATION_TYPE,int,ushort,ushort const *,ushort,ushort const *,ushort const *)
0x18005f06b  mov     rax, [rbp+37h+var_70]
0x18005f06f  xor     ebx, ebx
0x18005f071  movaps  xmm0, xmmword ptr [rbp+37h+pguid.Data1]
0x18005f075  movdqu  xmmword ptr [rax], xmm0
0x18005f079  lea     r15, aCspjobmgrCreat_0; "CSpJobMgr::CreateJob"
0x18005f080  mov     rcx, r14; lpCriticalSection
0x18005f083  call    cs:__imp_LeaveCriticalSection
0x18005f08a  nop     dword ptr [rax+rax+00h]
0x18005f08f  jmp     short loc_18005F0B0
0x18005f091  xor     esi, esi
0x18005f093  cmp     eax, 1Ch
0x18005f096  jnz     short loc_18005F0A9
0x18005f098  mov     ecx, 45Bh; dwErrCode
0x18005f09d  call    cs:__imp_SetLastError
0x18005f0a4  nop     dword ptr [rax+rax+00h]
0x18005f0a9  lea     r15, aCspjobmgrCreat_0; "CSpJobMgr::CreateJob"
0x18005f0b0  test    edi, edi
0x18005f0b2  jns     short loc_18005F0C4
0x18005f0b4  test    esi, esi
0x18005f0b6  jz      short loc_18005F0C4
0x18005f0b8  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18005f0bf  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18005f0c4  test    rbx, rbx
0x18005f0c7  jz      short loc_18005F0D8
0x18005f0c9  mov     rcx, rbx; hMem
0x18005f0cc  call    cs:__imp_LocalFree
0x18005f0d3  nop     dword ptr [rax+rax+00h]
0x18005f0d8  mov     eax, cs:dword_18039EB68
0x18005f0de  cmp     eax, 5
0x18005f0e1  jbe     short loc_18005F10C
0x18005f0e3  lea     rax, [rbp+37h+hMem]
0x18005f0e7  mov     dword ptr [rbp+37h+hMem], 0F8h
0x18005f0ee  mov     [rsp+0F0h+var_C8], rax
0x18005f0f3  lea     rdx, word_18031135A
0x18005f0fa  lea     rax, [rbp+37h+var_70]
0x18005f0fe  mov     [rbp+37h+var_70], r15
0x18005f102  mov     [rsp+0F0h+var_D0], rax
0x18005f107  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005f10c  xor     eax, eax
0x18005f10e  test    edi, edi
0x18005f110  setns   al
0x18005f113  mov     rcx, [rbp+37h+var_40]
0x18005f117  xor     rcx, rsp; StackCookie
0x18005f11a  call    __security_check_cookie
0x18005f11f  mov     rbx, [rsp+0F0h+arg_10]
0x18005f127  add     rsp, 0C0h
0x18005f12e  pop     r15
0x18005f130  pop     r14
0x18005f132  pop     r13
0x18005f134  pop     r12
0x18005f136  pop     rdi
0x18005f137  pop     rsi
0x18005f138  pop     rbp
0x18005f139  retn
```
