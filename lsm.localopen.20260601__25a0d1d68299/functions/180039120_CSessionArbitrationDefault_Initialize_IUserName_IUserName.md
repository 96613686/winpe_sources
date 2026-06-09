# CSessionArbitrationDefault::Initialize(IUserName *,IUserName *)

- ea: `0x180039120`
- end: `0x1800392cb`
- name: `?Initialize@CSessionArbitrationDefault@@UEAAJPEAUIUserName@@0@Z`
- size: `427`
- prototype: `int(CSessionArbitrationDefault *__hidden this, struct IUserName *, struct IUserName *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800077a0`
- `0x1800135e4`
- `0x180018ce4`
- `0x18002772c`
- `0x180039120`
- `0x18004ec5c`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003929c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800392b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003929c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800392b1`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x180039183`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x180039183`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    if ( (unsigned int)dword_1800DF020 > 5 )
    {
      LODWORD(v17) = IsCandidateUser;
      v16 = "CamIsCandidate user failed, assuming false";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_1800DF020,
        (unsigned int)&dword_1800CBF84,
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
0x180039120  push    rbp
0x180039122  push    rbx
0x180039123  push    rsi
0x180039124  push    rdi
0x180039125  push    r14
0x180039127  mov     rbp, rsp
0x18003912a  sub     rsp, 40h
0x18003912e  mov     r14, r8
0x180039131  mov     rdi, rdx
0x180039134  mov     rsi, rcx
0x180039137  mov     [rbp+var_10], 0
0x18003913f  mov     [rbp+pv], 0
0x180039147  mov     [rbp+arg_18], 0
0x18003914f  mov     rax, [rdx]
0x180039152  lea     rdx, [rbp+arg_18]
0x180039156  mov     rcx, rdi
0x180039159  mov     rax, [rax+48h]
0x18003915d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039162  mov     rax, [rdi]
0x180039165  lea     rdx, [rbp+pv]
0x180039169  mov     rcx, rdi
0x18003916c  mov     rax, [rax+28h]
0x180039170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039175  lea     rbx, [rsi+660h]
0x18003917c  mov     rdx, rbx
0x18003917f  mov     rcx, [rbp+arg_18]
0x180039183  call    cs:__imp_CamIsCandidateUser
0x18003918a  nop     dword ptr [rax+rax+00h]
0x18003918f  test    eax, eax
0x180039191  jns     short loc_1800391D0
0x180039193  mov     ecx, cs:dword_1800DF020
0x180039199  cmp     ecx, 5
0x18003919c  jbe     short loc_1800391CA
0x18003919e  mov     dword ptr [rbp+arg_0], eax
0x1800391a1  lea     rax, aCamiscandidate_0; "CamIsCandidate user failed, assuming fa"...
0x1800391a8  mov     [rbp+var_8], rax
0x1800391ac  lea     rax, [rbp+arg_0]
0x1800391b0  mov     [rsp+40h+var_18], rax
0x1800391b5  lea     rax, [rbp+var_8]
0x1800391b9  mov     [rsp+40h+var_20], rax
0x1800391be  lea     rdx, dword_1800CBF84
0x1800391c5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800391ca  mov     dword ptr [rbx], 0
0x1800391d0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800391d7  mov     ecx, 648h; unsigned __int64
0x1800391dc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800391e1  mov     [rbp+arg_0], rax
0x1800391e5  test    rax, rax
0x1800391e8  jz      short loc_1800391F9
0x1800391ea  mov     r8, r14; struct IUserName *
0x1800391ed  mov     rdx, rdi; struct IUserName *
0x1800391f0  mov     rcx, rax; this
0x1800391f3  call    ??0CSessionArbitrationHelper@@QEAA@PEAUIUserName@@0@Z; CSessionArbitrationHelper::CSessionArbitrationHelper(IUserName *,IUserName *)
0x1800391f8  nop
0x1800391f9  lea     rbx, [rsi+638h]
0x180039200  mov     rdx, rax
0x180039203  mov     rcx, rbx
0x180039206  call    ??4?$SmartPtr@VCSessionArbitrationHelper@@@@QEAAAEAV0@PEAVCSessionArbitrationHelper@@@Z; SmartPtr<CSessionArbitrationHelper>::operator=(CSessionArbitrationHelper *)
0x18003920b  cmp     qword ptr [rbx], 0
0x18003920f  jnz     short loc_180039218
0x180039211  mov     ebx, 8007000Eh
0x180039216  jmp     short loc_180039293
0x180039218  mov     rax, [rdi]
0x18003921b  lea     rdx, [rsi+65Ch]
0x180039222  mov     rcx, rdi
0x180039225  mov     rax, [rax+70h]
0x180039229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003922e  mov     ebx, eax
0x180039230  test    eax, eax
0x180039232  jns     short loc_18003923D
0x180039234  lea     rdx, aFailedToGetSes_2; "Failed to get session ID of request use"...
0x18003923b  jmp     short loc_18003927F
0x18003923d  mov     rax, [rdi]
0x180039240  lea     rdx, [rbp+pv]
0x180039244  mov     rcx, rdi
0x180039247  mov     rax, [rax+28h]
0x18003924b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039250  mov     ebx, eax
0x180039252  test    eax, eax
0x180039254  jns     short loc_18003925F
0x180039256  lea     rdx, aCanTGetUseName; "can't get use name failed: 0x%x in %s"
0x18003925d  jmp     short loc_18003927F
0x18003925f  mov     rax, [rdi]
0x180039262  lea     rdx, [rbp+var_10]
0x180039266  mov     rcx, rdi
0x180039269  mov     rax, [rax+30h]
0x18003926d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039272  mov     ebx, eax
0x180039274  test    eax, eax
0x180039276  jns     short loc_180039293
0x180039278  lea     rdx, aCanTGetUsePszd; "can't get use pszDomain name failed: 0x"...
0x18003927f  lea     r9, aCsessionarbitr_13; "CSessionArbitrationDefault::Initialize"
0x180039286  mov     r8d, eax
0x180039289  mov     ecx, 8; int
0x18003928e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180039293  mov     rcx, [rbp+pv]; pv
0x180039297  test    rcx, rcx
0x18003929a  jz      short loc_1800392A8
0x18003929c  call    cs:__imp_CoTaskMemFree
0x1800392a3  nop     dword ptr [rax+rax+00h]
0x1800392a8  mov     rcx, [rbp+var_10]; pv
0x1800392ac  test    rcx, rcx
0x1800392af  jz      short loc_1800392BD
0x1800392b1  call    cs:__imp_CoTaskMemFree
0x1800392b8  nop     dword ptr [rax+rax+00h]
0x1800392bd  mov     eax, ebx
0x1800392bf  add     rsp, 40h
0x1800392c3  pop     r14
0x1800392c5  pop     rdi
0x1800392c6  pop     rsi
0x1800392c7  pop     rbx
0x1800392c8  pop     rbp
0x1800392c9  retn
```
