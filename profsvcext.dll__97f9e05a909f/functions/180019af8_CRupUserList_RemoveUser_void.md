# CRupUserList::RemoveUser(void *)

- ea: `0x180019af8`
- end: `0x180019c39`
- name: `?RemoveUser@CRupUserList@@QEAAJPEAX@Z`
- size: `321`
- prototype: `__int64 __fastcall(CRupUserList *this, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800029d0`

## callees

- `0x180006a9c`
- `0x180011478`
- `0x180011514`
- `0x180015534`
- `0x180018950`
- `0x180018a04`
- `0x180019634`
- `0x180019af8`
- `0x18001a46c`
- `0x18001a4c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019b11`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019b11`

## string_xrefs

- `0x180019b4c`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
__int64 __fastcall CRupUserList::RemoveUser(CRupUserList *this, void *a2)
{
  int SidString; // eax
  unsigned int v4; // ebx
  unsigned int v5; // r8d
  const char *v6; // r9
  __int64 result; // rax
  CRupUser *i; // rbx
  CRupUser *v9; // rdi
  CRupUser *v11; // rsi
  CRupUser *v12; // rdi
  int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned __int16 *v15; // [rsp+50h] [rbp+18h] BYREF
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+20h] BYREF

  AcquireSRWLockExclusive(&g_RupUserList);
  v16 = &g_RupUserList;
  v15 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v15,
    0);
  try
  {
    SidString = GetSidString(a2, &v15);
    v4 = SidString;
    if ( SidString >= 0 )
    {
      v9 = *(&xmmword_18002DF98 + 1);
      for ( i = xmmword_18002DF98;
            i != v9 && !StringIsEqual(v15, *((const unsigned __int16 **)i + 1));
            i = (CRupUser *)((char *)i + 24) )
      {
        ;
      }
      if ( i != *(&xmmword_18002DF98 + 1) && (*((_DWORD *)i + 4))-- == 1 )
      {
        v11 = *(&xmmword_18002DF98 + 1);
        v12 = (CRupUser *)((char *)i + 24);
        if ( (CRupUser *)((char *)i + 24) != *(&xmmword_18002DF98 + 1) )
        {
          do
          {
            if ( i != v12 )
            {
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
                i,
                *(_QWORD *)v12);
              *(_QWORD *)v12 = 0;
            }
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              (char *)i + 8,
              (char *)v12 + 8);
            *((_DWORD *)i + 4) = *((_DWORD *)v12 + 4);
            i = (CRupUser *)((char *)i + 24);
            v12 = (CRupUser *)((char *)v12 + 24);
          }
          while ( v12 != v11 );
          v11 = *(&xmmword_18002DF98 + 1);
        }
        CRupUser::~CRupUser((CRupUser *)((char *)v11 - 24));
        *(&xmmword_18002DF98 + 1) = (CRupUser *)((char *)*(&xmmword_18002DF98 + 1) - 24);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
        (const char *)(unsigned int)SidString,
        v13);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
      result = v4;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x6C, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180019af8  mov     [rsp+arg_0], rcx
0x180019afd  push    rbx
0x180019afe  push    rsi
0x180019aff  push    rdi; int
0x180019b00  sub     rsp, 20h
0x180019b04  mov     rbx, rdx
0x180019b07  lea     rdi, ?g_RupUserList@@3VCRupUserList@@A; CRupUserList g_RupUserList
0x180019b0e  mov     rcx, rdi; SRWLock
0x180019b11  call    cs:__imp_AcquireSRWLockExclusive
0x180019b17  mov     [rsp+38h+arg_18], rdi
0x180019b1c  mov     [rsp+38h+arg_10], 0
0x180019b25  xor     edx, edx
0x180019b27  lea     rcx, [rsp+38h+arg_10]
0x180019b2c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180019b31  lea     rdx, [rsp+38h+arg_10]; unsigned __int16 **
0x180019b36  mov     rcx, rbx; void *
0x180019b39  call    ?GetSidString@@YAJPEAXPEAPEAG@Z; GetSidString(void *,ushort * *)
0x180019b3e  mov     ebx, eax
0x180019b40  test    eax, eax
0x180019b42  jns     short loc_180019B7A
0x180019b44  mov     rcx, [rsp+38h]; this
0x180019b49  mov     r9d, eax; char *
0x180019b4c  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x180019b53  mov     edx, 5Bh ; '['; void *
0x180019b58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019b5d  nop
0x180019b5e  lea     rcx, [rsp+38h+arg_10]
0x180019b63  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180019b68  nop
0x180019b69  lea     rcx, [rsp+38h+arg_18]
0x180019b6e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180019b73  mov     eax, ebx
0x180019b75  jmp     loc_180019C30
0x180019b7a  mov     rbx, qword ptr cs:xmmword_18002DF98
0x180019b81  mov     rdi, qword ptr cs:xmmword_18002DF98+8
0x180019b88  jmp     short loc_180019BA0
0x180019b8a  mov     rdx, [rbx+8]; unsigned __int16 *
0x180019b8e  mov     rcx, [rsp+38h+arg_10]; unsigned __int16 *
0x180019b93  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x180019b98  test    eax, eax
0x180019b9a  jnz     short loc_180019BA5
0x180019b9c  add     rbx, 18h
0x180019ba0  cmp     rbx, rdi
0x180019ba3  jnz     short loc_180019B8A
0x180019ba5  cmp     rbx, qword ptr cs:xmmword_18002DF98+8
0x180019bac  jz      short loc_180019C13
0x180019bae  add     dword ptr [rbx+10h], 0FFFFFFFFh
0x180019bb2  jnz     short loc_180019C13
0x180019bb4  mov     rsi, qword ptr cs:xmmword_18002DF98+8
0x180019bbb  lea     rdi, [rbx+18h]
0x180019bbf  cmp     rdi, rsi
0x180019bc2  jz      short loc_180019C02
0x180019bc4  cmp     rbx, rdi
0x180019bc7  jz      short loc_180019BDB
0x180019bc9  mov     rdx, [rdi]
0x180019bcc  mov     rcx, rbx
0x180019bcf  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180019bd4  mov     qword ptr [rdi], 0
0x180019bdb  lea     rdx, [rdi+8]
0x180019bdf  lea     rcx, [rbx+8]
0x180019be3  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180019be8  mov     eax, [rdi+10h]
0x180019beb  mov     [rbx+10h], eax
0x180019bee  add     rbx, 18h
0x180019bf2  add     rdi, 18h
0x180019bf6  cmp     rdi, rsi
0x180019bf9  jnz     short loc_180019BC4
0x180019bfb  mov     rsi, qword ptr cs:xmmword_18002DF98+8
0x180019c02  lea     rcx, [rsi-18h]; this
0x180019c06  call    ??1CRupUser@@QEAA@XZ; CRupUser::~CRupUser(void)
0x180019c0b  sub     qword ptr cs:xmmword_18002DF98+8, 18h
0x180019c13  lea     rcx, [rsp+38h+arg_10]
0x180019c18  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180019c1d  nop
0x180019c1e  lea     rcx, [rsp+38h+arg_18]
0x180019c23  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180019c28  xor     eax, eax
0x180019c2a  jmp     short loc_180019C30
0x180019c2c  mov     eax, dword ptr [rsp+38h+arg_0]
0x180019c30  add     rsp, 20h
0x180019c34  pop     rdi
0x180019c35  pop     rsi
0x180019c36  pop     rbx
0x180019c37  retn
```
