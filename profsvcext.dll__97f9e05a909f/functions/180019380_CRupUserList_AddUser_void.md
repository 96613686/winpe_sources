# CRupUserList::AddUser(void *)

- ea: `0x180019380`
- end: `0x1800194c3`
- name: `?AddUser@CRupUserList@@QEAAJPEAX@Z`
- size: `323`
- prototype: `__int64 __fastcall(CRupUserList *this, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800029d0`

## callees

- `0x180006a9c`
- `0x180011478`
- `0x180011514`
- `0x180015534`
- `0x180018430`
- `0x1800184c8`
- `0x180018808`
- `0x180018950`
- `0x180019380`
- `0x180019634`
- `0x18001a4c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800193a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800193a1`

## string_xrefs

- `0x1800193dc`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
__int64 __fastcall CRupUserList::AddUser(CRupUserList *this, void *a2)
{
  int SidString; // eax
  unsigned int v4; // ebx
  unsigned int v5; // r8d
  const char *v6; // r9
  __int64 result; // rax
  CRupUser *i; // rbx
  CRupUser *v9; // rdi
  CRupUser *v10; // rax
  void *phNewToken[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned __int16 *v13; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v14; // [rsp+60h] [rbp+18h] BYREF

  v13 = (unsigned __int16 *)this;
  AcquireSRWLockExclusive(&g_RupUserList);
  v14 = &g_RupUserList;
  v13 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v13,
    0);
  try
  {
    SidString = GetSidString(a2, &v13);
    v4 = SidString;
    if ( SidString >= 0 )
    {
      v9 = *(&xmmword_18002DF98 + 1);
      for ( i = xmmword_18002DF98;
            i != v9 && !StringIsEqual(v13, *((const unsigned __int16 **)i + 1));
            i = (CRupUser *)((char *)i + 24) )
      {
        ;
      }
      if ( i == *(&xmmword_18002DF98 + 1) )
      {
        v10 = CRupUser::CRupUser(phNewToken, a2, v13);
        if ( *(&xmmword_18002DF98 + 1) == (CRupUser *)qword_18002DFA8 )
        {
          std::vector<CRupUser>::_Emplace_reallocate<CRupUser>(&xmmword_18002DF98, *(&xmmword_18002DF98 + 1), v10);
        }
        else
        {
          std::_Construct_in_place<CRupUser,CRupUser>(*(&xmmword_18002DF98 + 1), v10);
          *(&xmmword_18002DF98 + 1) = (CRupUser *)((char *)*(&xmmword_18002DF98 + 1) + 24);
        }
        CRupUser::~CRupUser((CRupUser *)phNewToken);
      }
      else
      {
        ++*((_DWORD *)i + 4);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
        (const char *)(unsigned int)SidString,
        (int)phNewToken[0]);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
      result = v4;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x55, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180019380  mov     [rsp+arg_8], rbx
0x180019385  mov     [rsp+arg_18], rsi
0x18001938a  mov     [rsp+arg_0], rcx
0x18001938f  push    rdi
0x180019390  sub     rsp, 40h
0x180019394  mov     rsi, rdx
0x180019397  lea     rbx, ?g_RupUserList@@3VCRupUserList@@A; CRupUserList g_RupUserList
0x18001939e  mov     rcx, rbx; SRWLock
0x1800193a1  call    cs:__imp_AcquireSRWLockExclusive
0x1800193a7  mov     [rsp+48h+arg_10], rbx
0x1800193ac  mov     [rsp+48h+arg_0], 0
0x1800193b5  xor     edx, edx
0x1800193b7  lea     rcx, [rsp+48h+arg_0]
0x1800193bc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800193c1  lea     rdx, [rsp+48h+arg_0]; unsigned __int16 **
0x1800193c6  mov     rcx, rsi; void *
0x1800193c9  call    ?GetSidString@@YAJPEAXPEAPEAG@Z; GetSidString(void *,ushort * *)
0x1800193ce  mov     ebx, eax
0x1800193d0  test    eax, eax
0x1800193d2  jns     short loc_18001940A
0x1800193d4  mov     rcx, [rsp+48h]; this
0x1800193d9  mov     r9d, eax; char *
0x1800193dc  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x1800193e3  mov     edx, 42h ; 'B'; void *
0x1800193e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800193ed  nop
0x1800193ee  lea     rcx, [rsp+48h+arg_0]
0x1800193f3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800193f8  nop
0x1800193f9  lea     rcx, [rsp+48h+arg_10]
0x1800193fe  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180019403  mov     eax, ebx
0x180019405  jmp     loc_1800194B2
0x18001940a  mov     rbx, qword ptr cs:xmmword_18002DF98
0x180019411  mov     rdi, qword ptr cs:xmmword_18002DF98+8
0x180019418  jmp     short loc_180019430
0x18001941a  mov     rdx, [rbx+8]; unsigned __int16 *
0x18001941e  mov     rcx, [rsp+48h+arg_0]; unsigned __int16 *
0x180019423  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x180019428  test    eax, eax
0x18001942a  jnz     short loc_180019435
0x18001942c  add     rbx, 18h
0x180019430  cmp     rbx, rdi
0x180019433  jnz     short loc_18001941A
0x180019435  cmp     rbx, qword ptr cs:xmmword_18002DF98+8
0x18001943c  jz      short loc_180019443
0x18001943e  inc     dword ptr [rbx+10h]
0x180019441  jmp     short loc_180019495
0x180019443  mov     r8, [rsp+48h+arg_0]; unsigned __int16 *
0x180019448  mov     rdx, rsi; hExistingToken
0x18001944b  lea     rcx, [rsp+48h+phNewToken]; phNewToken
0x180019450  call    ??0CRupUser@@QEAA@PEAXPEAG@Z; CRupUser::CRupUser(void *,ushort *)
0x180019455  mov     rdx, rax
0x180019458  mov     rcx, qword ptr cs:xmmword_18002DF98+8
0x18001945f  cmp     rcx, cs:qword_18002DFA8
0x180019466  jz      short loc_180019477
0x180019468  call    ??$_Construct_in_place@VCRupUser@@V1@@std@@YAXAEAVCRupUser@@$$QEAV1@@Z; std::_Construct_in_place<CRupUser,CRupUser>(CRupUser &,CRupUser &&)
0x18001946d  add     qword ptr cs:xmmword_18002DF98+8, 18h
0x180019475  jmp     short loc_18001948A
0x180019477  mov     r8, rdx
0x18001947a  mov     rdx, rcx
0x18001947d  lea     rcx, xmmword_18002DF98
0x180019484  call    ??$_Emplace_reallocate@VCRupUser@@@?$vector@VCRupUser@@V?$allocator@VCRupUser@@@std@@@std@@AEAAPEAVCRupUser@@QEAV2@$$QEAV2@@Z; std::vector<CRupUser>::_Emplace_reallocate<CRupUser>(CRupUser * const,CRupUser &&)
0x180019489  nop
0x18001948a  lea     rcx, [rsp+48h+phNewToken]; this
0x18001948f  call    ??1CRupUser@@QEAA@XZ; CRupUser::~CRupUser(void)
0x180019494  nop
0x180019495  lea     rcx, [rsp+48h+arg_0]
0x18001949a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001949f  nop
0x1800194a0  lea     rcx, [rsp+48h+arg_10]
0x1800194a5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800194aa  xor     eax, eax
0x1800194ac  jmp     short loc_1800194B2
0x1800194ae  mov     eax, dword ptr [rsp+48h+arg_0]
0x1800194b2  mov     rbx, [rsp+48h+arg_8]
0x1800194b7  mov     rsi, [rsp+48h+arg_18]
0x1800194bc  add     rsp, 40h
0x1800194c0  pop     rdi
0x1800194c1  retn
```
