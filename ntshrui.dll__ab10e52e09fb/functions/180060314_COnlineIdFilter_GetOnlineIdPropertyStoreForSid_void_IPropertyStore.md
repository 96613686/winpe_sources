# COnlineIdFilter::_GetOnlineIdPropertyStoreForSid(void *,IPropertyStore * *)

- ea: `0x180060314`
- end: `0x1800604ff`
- name: `?_GetOnlineIdPropertyStoreForSid@COnlineIdFilter@@AEAAJPEAXPEAPEAUIPropertyStore@@@Z`
- size: `491`
- prototype: `int(COnlineIdFilter *__hidden this, void *, struct IPropertyStore **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180060160`
- `0x180060180`

## callees

- `0x180011e68`
- `0x180019454`
- `0x1800194e8`
- `0x18001a1a4`
- `0x18001d1dc`
- `0x180022c18`
- `0x1800254e0`
- `0x180060314`
- `0x180078010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18006047b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18006047b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060497`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800604a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060497`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800604a6`

## pseudocode

```c
__int64 __fastcall COnlineIdFilter::_GetOnlineIdPropertyStoreForSid(
        COnlineIdFilter *this,
        void *a2,
        struct IPropertyStore **a3)
{
  const struct _GUID *v6; // rdx
  int OnlineIdPropertyStoreEnum; // ebx
  bool v8; // zf
  __int64 v9; // rdx
  __int64 v10; // rcx
  void *v11; // rcx
  unsigned __int16 v12; // r14
  PSID v13; // rsi
  unsigned __int16 v15; // [rsp+40h] [rbp-40h] BYREF
  void *v16; // [rsp+48h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-30h] BYREF
  struct IEnumUnknown *v18; // [rsp+58h] [rbp-28h] BYREF
  PSID pSid1; // [rsp+60h] [rbp-20h] BYREF
  __int128 v20; // [rsp+68h] [rbp-18h] BYREF

  *a3 = 0;
  v18 = 0;
  OnlineIdPropertyStoreEnum = COnlineIdFilter::_GetOnlineIdPropertyStoreEnum(this, &v18);
  if ( OnlineIdPropertyStoreEnum >= 0 )
  {
    v8 = *a3 == 0;
    v16 = 0;
    if ( v8 )
    {
      do
      {
        if ( OnlineIdPropertyStoreEnum < 0 || (int)SHNextObjectFromEnumUnknown(v18, v6, &v16) < 0 )
          break;
        v20 = 0;
        OnlineIdPropertyStoreEnum = IPropertyStore_GetCLSID(v16, v9, &v20);
        if ( OnlineIdPropertyStoreEnum >= 0 )
        {
          pv = 0;
          OnlineIdPropertyStoreEnum = IPropertyStore_GetString(v16, &PKEY_Identity_UniqueID, &pv);
          if ( OnlineIdPropertyStoreEnum >= 0 )
          {
            v10 = *((_QWORD *)this + 2);
            v15 = 0;
            OnlineIdPropertyStoreEnum = (*(__int64 (__fastcall **)(__int64, LPVOID, __int128 *))(*(_QWORD *)v10 + 48LL))(
                                          v10,
                                          pv,
                                          &v20);
            if ( ((OnlineIdPropertyStoreEnum + 0x80000000) & 0x80000000) != 0
              || OnlineIdPropertyStoreEnum == -2147024774 )
            {
              v12 = v15;
              pSid1 = 0;
              OnlineIdPropertyStoreEnum = CTCoAllocPolicy::Alloc(v11, 1u, v15, &pSid1);
              if ( OnlineIdPropertyStoreEnum >= 0 )
              {
                v13 = pSid1;
                OnlineIdPropertyStoreEnum = (*(__int64 (__fastcall **)(_QWORD, LPVOID, __int128 *, _QWORD, PSID, unsigned __int16 *))(**((_QWORD **)this + 2) + 48LL))(
                                              *((_QWORD *)this + 2),
                                              pv,
                                              &v20,
                                              v12,
                                              pSid1,
                                              &v15);
                if ( OnlineIdPropertyStoreEnum >= 0 && EqualSid(v13, a2) )
                {
                  *a3 = (struct IPropertyStore *)v16;
                  v16 = 0;
                }
                CoTaskMemFree(v13);
              }
            }
            CoTaskMemFree(pv);
          }
        }
        SafeRelease<IShellItemArray>(&v16);
      }
      while ( !*a3 );
    }
    ((void (__fastcall *)(struct IEnumUnknown *))v18->lpVtbl->Release)(v18);
    if ( OnlineIdPropertyStoreEnum >= 0 && !*a3 )
      return (unsigned int)-2147023728;
  }
  return (unsigned int)OnlineIdPropertyStoreEnum;
}

```

## disassembly

```asm
0x180060314  push    rbp
0x180060316  push    rbx
0x180060317  push    rsi
0x180060318  push    rdi
0x180060319  push    r12
0x18006031b  push    r14
0x18006031d  push    r15
0x18006031f  mov     rbp, rsp
0x180060322  sub     rsp, 80h
0x180060329  mov     rax, cs:__security_cookie
0x180060330  xor     rax, rsp
0x180060333  mov     [rbp+var_8], rax
0x180060337  mov     r12, rdx
0x18006033a  mov     qword ptr [r8], 0
0x180060341  lea     rdx, [rbp+var_28]; struct IEnumUnknown **
0x180060345  mov     [rbp+var_28], 0
0x18006034d  mov     rdi, r8
0x180060350  mov     r15, rcx
0x180060353  call    ?_GetOnlineIdPropertyStoreEnum@COnlineIdFilter@@AEAAJPEAPEAUIEnumUnknown@@@Z; COnlineIdFilter::_GetOnlineIdPropertyStoreEnum(IEnumUnknown * *)
0x180060358  mov     ebx, eax
0x18006035a  test    eax, eax
0x18006035c  js      loc_1800604DF
0x180060362  cmp     qword ptr [rdi], 0
0x180060366  mov     [rbp+var_38], 0
0x18006036e  jnz     loc_1800604BF
0x180060374  mov     esi, 80000000h
0x180060379  test    ebx, ebx
0x18006037b  js      loc_1800604BF
0x180060381  mov     rcx, [rbp+var_28]; struct IEnumUnknown *
0x180060385  lea     r8, [rbp+var_38]; void **
0x180060389  call    ?SHNextObjectFromEnumUnknown@@YAJPEAUIEnumUnknown@@AEBU_GUID@@PEAPEAX@Z; SHNextObjectFromEnumUnknown(IEnumUnknown *,_GUID const &,void * *)
0x18006038e  test    eax, eax
0x180060390  js      loc_1800604BF
0x180060396  mov     rcx, [rbp+var_38]
0x18006039a  lea     r8, [rbp+var_18]
0x18006039e  xorps   xmm0, xmm0
0x1800603a1  movups  [rbp+var_18], xmm0
0x1800603a5  call    IPropertyStore_GetCLSID
0x1800603aa  mov     ebx, eax
0x1800603ac  test    eax, eax
0x1800603ae  js      loc_1800604AC
0x1800603b4  mov     rcx, [rbp+var_38]
0x1800603b8  lea     r8, [rbp+pv]
0x1800603bc  lea     rdx, PKEY_Identity_UniqueID
0x1800603c3  mov     [rbp+pv], 0
0x1800603cb  call    IPropertyStore_GetString
0x1800603d0  mov     ebx, eax
0x1800603d2  test    eax, eax
0x1800603d4  js      loc_1800604AC
0x1800603da  mov     rcx, [r15+10h]
0x1800603de  lea     rdx, [rbp+var_40]
0x1800603e2  xor     eax, eax
0x1800603e4  mov     [rsp+80h+var_58], rdx
0x1800603e9  mov     rdx, [rbp+pv]
0x1800603ed  lea     r8, [rbp+var_18]
0x1800603f1  mov     [rbp+var_40], ax
0x1800603f5  xor     r9d, r9d
0x1800603f8  mov     rax, [rcx]
0x1800603fb  mov     [rsp+80h+var_60], r9
0x180060400  mov     rax, [rax+30h]
0x180060404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060409  mov     ebx, eax
0x18006040b  add     eax, esi
0x18006040d  test    esi, eax
0x18006040f  jnz     short loc_18006041D
0x180060411  cmp     ebx, 8007007Ah
0x180060417  jnz     loc_1800604A2
0x18006041d  movzx   r14d, [rbp+var_40]
0x180060422  lea     r9, [rbp+pSid1]; void **
0x180060426  mov     r8d, r14d; unsigned __int64
0x180060429  mov     [rbp+pSid1], 0
0x180060431  mov     edx, 1; unsigned int
0x180060436  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18006043b  mov     ebx, eax
0x18006043d  test    eax, eax
0x18006043f  js      short loc_1800604A2
0x180060441  mov     rcx, [r15+10h]
0x180060445  lea     rdx, [rbp+var_40]
0x180060449  mov     rsi, [rbp+pSid1]
0x18006044d  lea     r8, [rbp+var_18]
0x180060451  mov     [rsp+80h+var_58], rdx
0x180060456  movzx   r9d, r14w
0x18006045a  mov     rdx, [rbp+pv]
0x18006045e  mov     rax, [rcx]
0x180060461  mov     [rsp+80h+var_60], rsi
0x180060466  mov     rax, [rax+30h]
0x18006046a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006046f  mov     ebx, eax
0x180060471  test    eax, eax
0x180060473  js      short loc_180060494
0x180060475  mov     rdx, r12; pSid2
0x180060478  mov     rcx, rsi; pSid1
0x18006047b  call    cs:__imp_EqualSid
0x180060481  test    eax, eax
0x180060483  jz      short loc_180060494
0x180060485  mov     rax, [rbp+var_38]
0x180060489  mov     [rdi], rax
0x18006048c  mov     [rbp+var_38], 0
0x180060494  mov     rcx, rsi; pv
0x180060497  call    cs:__imp_CoTaskMemFree
0x18006049d  mov     esi, 80000000h
0x1800604a2  mov     rcx, [rbp+pv]; pv
0x1800604a6  call    cs:__imp_CoTaskMemFree
0x1800604ac  lea     rcx, [rbp+var_38]
0x1800604b0  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1800604b5  cmp     qword ptr [rdi], 0
0x1800604b9  jz      loc_180060379
0x1800604bf  mov     rcx, [rbp+var_28]
0x1800604c3  mov     rax, [rcx]
0x1800604c6  mov     rax, [rax+10h]
0x1800604ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800604cf  test    ebx, ebx
0x1800604d1  js      short loc_1800604DF
0x1800604d3  cmp     qword ptr [rdi], 0
0x1800604d7  mov     eax, 80070490h
0x1800604dc  cmovz   ebx, eax
0x1800604df  mov     eax, ebx
0x1800604e1  mov     rcx, [rbp+var_8]
0x1800604e5  xor     rcx, rsp; StackCookie
0x1800604e8  call    __security_check_cookie
0x1800604ed  add     rsp, 80h
0x1800604f4  pop     r15
0x1800604f6  pop     r14
0x1800604f8  pop     r12
0x1800604fa  pop     rdi
0x1800604fb  pop     rsi
0x1800604fc  pop     rbx
0x1800604fd  pop     rbp
0x1800604fe  retn
```
