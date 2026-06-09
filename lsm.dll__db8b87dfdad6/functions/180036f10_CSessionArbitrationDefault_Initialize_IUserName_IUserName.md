# CSessionArbitrationDefault::Initialize(IUserName *,IUserName *)

- ea: `0x180036f10`
- end: `0x1800370a8`
- name: `?Initialize@CSessionArbitrationDefault@@UEAAJPEAUIUserName@@0@Z`
- size: `408`
- prototype: `__int64 __fastcall(CSessionArbitrationDefault *this, struct IUserName *, struct IUserName *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800074c0`
- `0x18000f9c4`
- `0x18001aac4`
- `0x180025890`
- `0x180036f10`
- `0x18004b86c`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037086`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037095`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037086`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037095`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x180036f73`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x180036f73`

## pseudocode

```c
__int64 __fastcall CSessionArbitrationDefault::Initialize(
        CSessionArbitrationDefault *this,
        struct IUserName *a2,
        struct IUserName *a3)
{
  int IsCandidateUser; // eax
  int v7; // r8d
  int v8; // r9d
  CSessionArbitrationHelper *v9; // rax
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  LPVOID v15; // [rsp+30h] [rbp-10h] BYREF
  const char *v16; // [rsp+38h] [rbp-8h] BYREF
  CSessionArbitrationHelper *v17; // [rsp+70h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+38h] BYREF
  __int64 v19; // [rsp+88h] [rbp+48h] BYREF

  v15 = 0;
  pv = 0;
  v19 = 0;
  (*(void (__fastcall **)(struct IUserName *, __int64 *))(*(_QWORD *)a2 + 72LL))(a2, &v19);
  (*(void (__fastcall **)(struct IUserName *, LPVOID *))(*(_QWORD *)a2 + 40LL))(a2, &pv);
  IsCandidateUser = CamIsCandidateUser(v19, (char *)this + 1632);
  if ( IsCandidateUser < 0 )
  {
    if ( (unsigned int)dword_1800DA020 > 5 )
    {
      LODWORD(v17) = IsCandidateUser;
      v16 = "CamIsCandidate user failed, assuming false";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_1800DA020,
        (unsigned int)&dword_1800C6DFC,
        v7,
        v8,
        (__int64)&v16,
        (__int64)&v17);
    }
    *((_DWORD *)this + 408) = 0;
  }
  v9 = (CSessionArbitrationHelper *)operator new(0x648u, (const struct std::nothrow_t *)&std::nothrow);
  v17 = v9;
  if ( v9 )
    v9 = CSessionArbitrationHelper::CSessionArbitrationHelper(v9, a2, a3);
  SmartPtr<CSessionArbitrationHelper>::operator=((char *)this + 1592, v9);
  if ( *((_QWORD *)this + 199) )
  {
    v11 = (*(__int64 (__fastcall **)(struct IUserName *, char *))(*(_QWORD *)a2 + 112LL))(a2, (char *)this + 1628);
    v10 = v11;
    if ( v11 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(struct IUserName *, LPVOID *))(*(_QWORD *)a2 + 40LL))(a2, &pv);
      v10 = v12;
      if ( v12 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(struct IUserName *, LPVOID *))(*(_QWORD *)a2 + 48LL))(a2, &v15);
        v10 = v13;
        if ( v13 < 0 )
          _DbgPrintMessage(
            8,
            "can't get use pszDomain name failed: 0x%x in %s",
            (unsigned int)v13,
            "CSessionArbitrationDefault::Initialize");
      }
      else
      {
        _DbgPrintMessage(
          8,
          "can't get use name failed: 0x%x in %s",
          (unsigned int)v12,
          "CSessionArbitrationDefault::Initialize");
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "Failed to get session ID of request user failed: 0x%x in %s",
        (unsigned int)v11,
        "CSessionArbitrationDefault::Initialize");
    }
  }
  else
  {
    v10 = -2147024882;
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v15 )
    CoTaskMemFree(v15);
  return v10;
}

```

## disassembly

```asm
0x180036f10  push    rbp
0x180036f12  push    rbx
0x180036f13  push    rsi
0x180036f14  push    rdi
0x180036f15  push    r14
0x180036f17  mov     rbp, rsp
0x180036f1a  sub     rsp, 40h
0x180036f1e  mov     r14, r8
0x180036f21  mov     rdi, rdx
0x180036f24  mov     rsi, rcx
0x180036f27  mov     [rbp+var_10], 0
0x180036f2f  mov     [rbp+pv], 0
0x180036f37  mov     [rbp+arg_18], 0
0x180036f3f  mov     rax, [rdx]
0x180036f42  lea     rdx, [rbp+arg_18]
0x180036f46  mov     rcx, rdi
0x180036f49  mov     rax, [rax+48h]
0x180036f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f52  mov     rax, [rdi]
0x180036f55  lea     rdx, [rbp+pv]
0x180036f59  mov     rcx, rdi
0x180036f5c  mov     rax, [rax+28h]
0x180036f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f65  lea     rbx, [rsi+660h]
0x180036f6c  mov     rdx, rbx
0x180036f6f  mov     rcx, [rbp+arg_18]
0x180036f73  call    cs:__imp_CamIsCandidateUser
0x180036f79  test    eax, eax
0x180036f7b  jns     short loc_180036FBA
0x180036f7d  mov     ecx, cs:dword_1800DA020
0x180036f83  cmp     ecx, 5
0x180036f86  jbe     short loc_180036FB4
0x180036f88  mov     dword ptr [rbp+arg_0], eax
0x180036f8b  lea     rax, aCamiscandidate_0; "CamIsCandidate user failed, assuming fa"...
0x180036f92  mov     [rbp+var_8], rax
0x180036f96  lea     rax, [rbp+arg_0]
0x180036f9a  mov     [rsp+40h+var_18], rax
0x180036f9f  lea     rax, [rbp+var_8]
0x180036fa3  mov     [rsp+40h+var_20], rax
0x180036fa8  lea     rdx, dword_1800C6DFC
0x180036faf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180036fb4  mov     dword ptr [rbx], 0
0x180036fba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180036fc1  mov     ecx, 648h; unsigned __int64
0x180036fc6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180036fcb  mov     [rbp+arg_0], rax
0x180036fcf  test    rax, rax
0x180036fd2  jz      short loc_180036FE3
0x180036fd4  mov     r8, r14; struct IUserName *
0x180036fd7  mov     rdx, rdi; struct IUserName *
0x180036fda  mov     rcx, rax; this
0x180036fdd  call    ??0CSessionArbitrationHelper@@QEAA@PEAUIUserName@@0@Z; CSessionArbitrationHelper::CSessionArbitrationHelper(IUserName *,IUserName *)
0x180036fe2  nop
0x180036fe3  lea     rbx, [rsi+638h]
0x180036fea  mov     rdx, rax
0x180036fed  mov     rcx, rbx
0x180036ff0  call    ??4?$SmartPtr@VCSessionArbitrationHelper@@@@QEAAAEAV0@PEAVCSessionArbitrationHelper@@@Z; SmartPtr<CSessionArbitrationHelper>::operator=(CSessionArbitrationHelper *)
0x180036ff5  cmp     qword ptr [rbx], 0
0x180036ff9  jnz     short loc_180037002
0x180036ffb  mov     ebx, 8007000Eh
0x180037000  jmp     short loc_18003707D
0x180037002  mov     rax, [rdi]
0x180037005  lea     rdx, [rsi+65Ch]
0x18003700c  mov     rcx, rdi
0x18003700f  mov     rax, [rax+70h]
0x180037013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037018  mov     ebx, eax
0x18003701a  test    eax, eax
0x18003701c  jns     short loc_180037027
0x18003701e  lea     rdx, aFailedToGetSes_2; "Failed to get session ID of request use"...
0x180037025  jmp     short loc_180037069
0x180037027  mov     rax, [rdi]
0x18003702a  lea     rdx, [rbp+pv]
0x18003702e  mov     rcx, rdi
0x180037031  mov     rax, [rax+28h]
0x180037035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003703a  mov     ebx, eax
0x18003703c  test    eax, eax
0x18003703e  jns     short loc_180037049
0x180037040  lea     rdx, aCanTGetUseName; "can't get use name failed: 0x%x in %s"
0x180037047  jmp     short loc_180037069
0x180037049  mov     rax, [rdi]
0x18003704c  lea     rdx, [rbp+var_10]
0x180037050  mov     rcx, rdi
0x180037053  mov     rax, [rax+30h]
0x180037057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003705c  mov     ebx, eax
0x18003705e  test    eax, eax
0x180037060  jns     short loc_18003707D
0x180037062  lea     rdx, aCanTGetUsePszd; "can't get use pszDomain name failed: 0x"...
0x180037069  lea     r9, aCsessionarbitr_13; "CSessionArbitrationDefault::Initialize"
0x180037070  mov     r8d, eax
0x180037073  mov     ecx, 8; int
0x180037078  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003707d  mov     rcx, [rbp+pv]; pv
0x180037081  test    rcx, rcx
0x180037084  jz      short loc_18003708C
0x180037086  call    cs:__imp_CoTaskMemFree
0x18003708c  mov     rcx, [rbp+var_10]; pv
0x180037090  test    rcx, rcx
0x180037093  jz      short loc_18003709B
0x180037095  call    cs:__imp_CoTaskMemFree
0x18003709b  mov     eax, ebx
0x18003709d  add     rsp, 40h
0x1800370a1  pop     r14
0x1800370a3  pop     rdi
0x1800370a4  pop     rsi
0x1800370a5  pop     rbx
0x1800370a6  pop     rbp
0x1800370a7  retn
```
