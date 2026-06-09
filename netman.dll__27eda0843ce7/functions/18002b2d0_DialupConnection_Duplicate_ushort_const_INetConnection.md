# DialupConnection::Duplicate(ushort const *,INetConnection * *)

- ea: `0x18002b2d0`
- end: `0x18002b798`
- name: `?Duplicate@DialupConnection@@UEAAJPEBGPEAPEAUINetConnection@@@Z`
- size: `1224`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, const unsigned __int16 *, struct INetConnection **)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180001710`
- `0x18000538c`
- `0x1800084fc`
- `0x180020db0`
- `0x18002aebc`
- `0x18002b2d0`
- `0x18002c748`
- `0x18002cd44`
- `0x18002cf50`
- `0x18002cf80`
- `0x18002d69c`
- `0x1800306f8`
- `0x180030a00`
- `0x180030a50`
- `0x18003286c`
- `0x180032c3c`
- `0x180036010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002b308`
- `KERNEL32!EnterCriticalSection` at `0x18002b308`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b63c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b6d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b63c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b6d1`
- `RASAPI32!DwCloneEntry` at `0x18002b3ce`
- `RASAPI32!DwCloneEntry` at `0x18002b3ce`
- `RASAPI32!RasValidateEntryNameW` at `0x18002b37f`
- `RASAPI32!RasValidateEntryNameW` at `0x18002b37f`

## pseudocode

```c
__int64 __fastcall DialupConnection::Duplicate(
        struct _RTL_CRITICAL_SECTION *this,
        const unsigned __int16 *a2,
        struct INetConnection **a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  int InstanceFromPbkFileAndEntryName; // ebx
  const WCHAR *v8; // rax
  DWORD v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  const unsigned __int16 *v12; // rbx
  const unsigned __int16 *v13; // rax
  unsigned int v14; // eax
  const unsigned __int16 *v15; // rax
  const struct _GUID *v16; // r8
  struct IUnknown *v17; // rsi
  void *v18; // rdx
  __int64 v19; // rdx
  void *v20; // rdx
  struct IUnknown *v21; // rcx
  int v22; // eax
  struct _RTL_CRITICAL_SECTION *v24; // [rsp+30h] [rbp-39h] BYREF
  struct IUnknown *v25; // [rsp+38h] [rbp-31h] BYREF
  struct IUnknown *i; // [rsp+40h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-21h] BYREF
  struct IUnknown *v28; // [rsp+50h] [rbp-19h] BYREF
  struct IUnknown *v29; // [rsp+58h] [rbp-11h] BYREF
  struct IUnknown *v30; // [rsp+60h] [rbp-9h] BYREF
  int v31; // [rsp+6Ch] [rbp+3h]
  struct IUnknown *v32; // [rsp+70h] [rbp+7h] BYREF
  char v33; // [rsp+78h] [rbp+Fh] BYREF
  char v34[3]; // [rsp+79h] [rbp+10h] BYREF
  int v35; // [rsp+7Ch] [rbp+13h] BYREF

  v3 = this + 8;
  EnterCriticalSection(this + 8);
  v24 = v3;
  if ( !a2 || !a3 )
  {
    InstanceFromPbkFileAndEntryName = -2147467261;
    goto LABEL_60;
  }
  if ( !LODWORD(this[2].LockSemaphore) )
  {
    InstanceFromPbkFileAndEntryName = -2147418113;
    goto LABEL_60;
  }
  *a3 = 0;
  v30 = (struct IUnknown *)0x100000000LL;
  v31 = 0;
  InstanceFromPbkFileAndEntryName = CAutoImpersonate::Impersonate((CAutoImpersonate *)&v30);
  if ( InstanceFromPbkFileAndEntryName >= 0 )
  {
    InstanceFromPbkFileAndEntryName = RasConnectionBase::HrEnsureEntryPropertiesCached((RasConnectionBase *)&this[2].LockSemaphore);
    if ( InstanceFromPbkFileAndEntryName >= 0 )
    {
      v8 = RasConnectionBase::PszwPbkFile((RasConnectionBase *)&this[2].LockSemaphore);
      v9 = RasValidateEntryNameW(v8, a2);
      InstanceFromPbkFileAndEntryName = HrFromRasError(v9);
      if ( InstanceFromPbkFileAndEntryName >= 0 )
      {
        v12 = RasConnectionBase::PszwEntryName((RasConnectionBase *)&this[2].LockSemaphore);
        v13 = RasConnectionBase::PszwPbkFile((RasConnectionBase *)&this[2].LockSemaphore);
        v14 = DwCloneEntry(v13, v12, a2);
        InstanceFromPbkFileAndEntryName = HrFromRasError(v14);
        if ( InstanceFromPbkFileAndEntryName >= 0 )
          goto LABEL_16;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_16;
        v11 = 20;
      }
      else
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_16;
        v11 = 19;
      }
      WPP_SF_d(
        v10[2],
        v11,
        &WPP_72e8a2b6c4a334b644d76a8a8dce3e8a_Traceguids,
        (unsigned int)InstanceFromPbkFileAndEntryName);
    }
  }
LABEL_16:
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v30);
  if ( InstanceFromPbkFileAndEntryName >= 0 )
  {
    v15 = RasConnectionBase::PszwPbkFile((RasConnectionBase *)&this[2].LockSemaphore);
    InstanceFromPbkFileAndEntryName = DialupConnection::CreateInstanceFromPbkFileAndEntryName(v15, a2, v16, (void **)a3);
    if ( InstanceFromPbkFileAndEntryName >= 0 )
    {
      InstanceFromPbkFileAndEntryName = DialupConnection::HrEnsureHNetPropertiesCached((DialupConnection *)this);
      if ( InstanceFromPbkFileAndEntryName >= 0 )
      {
        if ( !BYTE5(this[7].LockSemaphore) && !BYTE6(this[7].LockSemaphore) )
          goto LABEL_63;
        v30 = 0;
        InstanceFromPbkFileAndEntryName = HrGetHNetCfgMgr((struct IHNetCfgMgr **)&v30);
        if ( InstanceFromPbkFileAndEntryName >= 0 )
        {
          v17 = v30;
          v18 = *a3;
          v29 = 0;
          InstanceFromPbkFileAndEntryName = ((__int64 (__fastcall *)(struct IUnknown *, void *, struct IUnknown **))v30->lpVtbl[1].QueryInterface)(
                                              v30,
                                              v18,
                                              &v29);
          if ( InstanceFromPbkFileAndEntryName < 0 )
            goto LABEL_57;
          v32 = 0;
          InstanceFromPbkFileAndEntryName = DialupConnection::HrGetIHNetConnection(
                                              (DialupConnection *)this,
                                              (struct IHNetConnection **)&v32);
          if ( InstanceFromPbkFileAndEntryName < 0 )
          {
LABEL_56:
            ReleaseObj(v29);
LABEL_57:
            ReleaseObj(v17);
            if ( InstanceFromPbkFileAndEntryName >= 0 )
              goto LABEL_63;
            goto LABEL_60;
          }
          v30 = 0;
          if ( ((int (__fastcall *)(struct IUnknown *, _QWORD, struct IUnknown **))v29->lpVtbl[4].AddRef)(v29, 0, &v30) >= 0 )
          {
            v35 = 0;
            for ( i = 0;
                  !((unsigned int (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **, int *))v30->lpVtbl[1].QueryInterface)(
                     v30,
                     1,
                     &i,
                     &v35);
                  ReleaseObj(i) )
            {
              if ( v35 != 1 )
                MicrosoftTelemetryAssertTriggeredNoArgs();
              v25 = 0;
              if ( ((int (__fastcall *)(struct IUnknown *, struct IUnknown **))i->lpVtbl[1].AddRef)(i, &v25) >= 0 )
              {
                v28 = 0;
                if ( ((int (__fastcall *)(struct IUnknown *, struct IUnknown *, struct IUnknown **))v32->lpVtbl[4].Release)(
                       v32,
                       v25,
                       &v28) >= 0 )
                {
                  v33 = 0;
                  if ( ((int (__fastcall *)(struct IUnknown *, char *))v28->lpVtbl[1].Release)(v28, &v33) >= 0 )
                  {
                    if ( v33 != 1
                      || (LOBYTE(v19) = 1,
                          ((int (__fastcall *)(struct IUnknown *, __int64))i->lpVtbl[2].QueryInterface)(i, v19) >= 0) )
                    {
                      LODWORD(pv) = 0;
                      if ( ((int (__fastcall *)(struct IUnknown *, LPVOID *))v28->lpVtbl[3].AddRef)(v28, &pv) >= 0
                        && (!(_DWORD)pv || ((int (__fastcall *)(struct IUnknown *))i->lpVtbl[3].Release)(i) >= 0) )
                      {
                        v34[0] = 0;
                        if ( ((int (__fastcall *)(struct IUnknown *, char *))v28->lpVtbl[2].AddRef)(v28, v34) >= 0
                          && v34[0] == 1 )
                        {
                          pv = 0;
                          if ( ((int (__fastcall *)(struct IUnknown *, LPVOID *))v28->lpVtbl[2].Release)(v28, &pv) >= 0 )
                          {
                            v20 = pv;
                            if ( *(_WORD *)pv )
                            {
                              ((void (__fastcall *)(struct IUnknown *))i->lpVtbl[3].QueryInterface)(i);
                              v20 = pv;
                            }
                            CoTaskMemFree(v20);
                          }
                        }
                      }
                    }
                  }
                  ReleaseObj(v28);
                }
                ReleaseObj(v25);
              }
            }
            ReleaseObj(v30);
          }
          if ( BYTE5(this[7].LockSemaphore) )
          {
            i = 0;
            InstanceFromPbkFileAndEntryName = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v29->lpVtbl[3].QueryInterface)(
                                                v29,
                                                &i);
            if ( InstanceFromPbkFileAndEntryName >= 0 )
            {
              v25 = 0;
              InstanceFromPbkFileAndEntryName = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v32->lpVtbl[5].QueryInterface)(
                                                  v32,
                                                  &v25);
              if ( InstanceFromPbkFileAndEntryName >= 0 )
              {
                InstanceFromPbkFileAndEntryName = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown *))v29->lpVtbl[5].AddRef)(
                                                    v29,
                                                    v25);
                CoTaskMemFree(v25);
              }
              v21 = i;
              goto LABEL_54;
            }
          }
          else
          {
            v25 = 0;
            InstanceFromPbkFileAndEntryName = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v29->lpVtbl[2].Release)(
                                                v29,
                                                &GUID_85d18b72_3032_11d4_9348_00c04f8eeb71,
                                                &v25);
            if ( InstanceFromPbkFileAndEntryName >= 0 )
            {
              v22 = ((__int64 (__fastcall *)(struct IUnknown *))v25->lpVtbl[1].QueryInterface)(v25);
              v21 = v25;
              InstanceFromPbkFileAndEntryName = v22;
LABEL_54:
              ReleaseObj(v21);
            }
          }
          ReleaseObj(v32);
          goto LABEL_56;
        }
      }
    }
  }
LABEL_60:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      &WPP_72e8a2b6c4a334b644d76a8a8dce3e8a_Traceguids,
      (unsigned int)InstanceFromPbkFileAndEntryName);
LABEL_63:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v24);
  return (unsigned int)InstanceFromPbkFileAndEntryName;
}

```

## disassembly

```asm
0x18002b2d0  push    rbp
0x18002b2d2  push    rbx
0x18002b2d3  push    rsi
0x18002b2d4  push    rdi
0x18002b2d5  push    r12
0x18002b2d7  push    r14
0x18002b2d9  push    r15
0x18002b2db  lea     rbp, [rsp-27h]
0x18002b2e0  sub     rsp, 90h
0x18002b2e7  mov     rax, cs:__security_cookie
0x18002b2ee  xor     rax, rsp
0x18002b2f1  mov     [rbp+57h+var_40], rax
0x18002b2f5  lea     rbx, [rcx+140h]
0x18002b2fc  mov     rdi, rcx
0x18002b2ff  mov     rcx, rbx; lpCriticalSection
0x18002b302  mov     r14, r8
0x18002b305  mov     r15, rdx
0x18002b308  call    cs:__imp_EnterCriticalSection
0x18002b30e  xor     r12d, r12d
0x18002b311  mov     [rbp+57h+var_90], rbx
0x18002b315  test    r15, r15
0x18002b318  jz      loc_18002B739
0x18002b31e  test    r14, r14
0x18002b321  jz      loc_18002B739
0x18002b327  lea     rsi, [rdi+68h]
0x18002b32b  cmp     [rsi], r12d
0x18002b32e  jnz     short loc_18002B33A
0x18002b330  mov     ebx, 8000FFFFh
0x18002b335  jmp     loc_18002B73E
0x18002b33a  lea     rcx, [rbp+57h+var_60]; this
0x18002b33e  mov     [r14], r12
0x18002b341  mov     dword ptr [rbp+57h+var_60+4], 1
0x18002b348  mov     dword ptr [rbp+57h+var_60], r12d
0x18002b34c  mov     [rbp+57h+var_54], r12d
0x18002b350  call    ?Impersonate@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::Impersonate(void)
0x18002b355  mov     ebx, eax
0x18002b357  test    eax, eax
0x18002b359  js      loc_18002B412
0x18002b35f  mov     rcx, rsi; this
0x18002b362  call    ?HrEnsureEntryPropertiesCached@RasConnectionBase@@IEAAJXZ; RasConnectionBase::HrEnsureEntryPropertiesCached(void)
0x18002b367  mov     ebx, eax
0x18002b369  test    eax, eax
0x18002b36b  js      loc_18002B412
0x18002b371  mov     rcx, rsi; this
0x18002b374  call    ?PszwPbkFile@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwPbkFile(void)
0x18002b379  mov     rcx, rax; LPCWSTR
0x18002b37c  mov     rdx, r15; LPCWSTR
0x18002b37f  call    cs:__imp_RasValidateEntryNameW
0x18002b385  mov     ecx, eax; unsigned int
0x18002b387  call    ?HrFromRasError@@YAJK@Z; HrFromRasError(ulong)
0x18002b38c  mov     ebx, eax
0x18002b38e  test    eax, eax
0x18002b390  jns     short loc_18002B3B2
0x18002b392  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b399  lea     rax, WPP_GLOBAL_Control
0x18002b3a0  cmp     rcx, rax
0x18002b3a3  jz      short loc_18002B412
0x18002b3a5  test    byte ptr [rcx+1Ch], 1
0x18002b3a9  jz      short loc_18002B412
0x18002b3ab  mov     edx, 13h
0x18002b3b0  jmp     short loc_18002B3FF
0x18002b3b2  mov     rcx, rsi; this
0x18002b3b5  call    ?PszwEntryName@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwEntryName(void)
0x18002b3ba  mov     rcx, rsi; this
0x18002b3bd  mov     rbx, rax
0x18002b3c0  call    ?PszwPbkFile@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwPbkFile(void)
0x18002b3c5  mov     r8, r15
0x18002b3c8  mov     rdx, rbx
0x18002b3cb  mov     rcx, rax
0x18002b3ce  call    cs:__imp_DwCloneEntry
0x18002b3d4  mov     ecx, eax; unsigned int
0x18002b3d6  call    ?HrFromRasError@@YAJK@Z; HrFromRasError(ulong)
0x18002b3db  mov     ebx, eax
0x18002b3dd  test    eax, eax
0x18002b3df  jns     short loc_18002B412
0x18002b3e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3e8  lea     rax, WPP_GLOBAL_Control
0x18002b3ef  cmp     rcx, rax
0x18002b3f2  jz      short loc_18002B412
0x18002b3f4  test    byte ptr [rcx+1Ch], 1
0x18002b3f8  jz      short loc_18002B412
0x18002b3fa  mov     edx, 14h
0x18002b3ff  mov     rcx, [rcx+10h]
0x18002b403  lea     r8, WPP_72e8a2b6c4a334b644d76a8a8dce3e8a_Traceguids
0x18002b40a  mov     r9d, ebx
0x18002b40d  call    WPP_SF_d
0x18002b412  lea     rcx, [rbp+57h+var_60]; this
0x18002b416  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18002b41b  test    ebx, ebx
0x18002b41d  js      loc_18002B73E
0x18002b423  mov     rcx, rsi; this
0x18002b426  call    ?PszwPbkFile@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwPbkFile(void)
0x18002b42b  mov     r9, r14; void **
0x18002b42e  mov     rdx, r15; unsigned __int16 *
0x18002b431  mov     rcx, rax; unsigned __int16 *
0x18002b434  call    ?CreateInstanceFromPbkFileAndEntryName@DialupConnection@@SAJPEBG0AEBU_GUID@@PEAPEAX@Z; DialupConnection::CreateInstanceFromPbkFileAndEntryName(ushort const *,ushort const *,_GUID const &,void * *)
0x18002b439  mov     ebx, eax
0x18002b43b  test    eax, eax
0x18002b43d  js      loc_18002B73E
0x18002b443  mov     rcx, rdi; this
0x18002b446  call    ?HrEnsureHNetPropertiesCached@DialupConnection@@QEAAJXZ; DialupConnection::HrEnsureHNetPropertiesCached(void)
0x18002b44b  mov     ebx, eax
0x18002b44d  test    eax, eax
0x18002b44f  js      loc_18002B73E
0x18002b455  cmp     [rdi+135h], r12b
0x18002b45c  jnz     short loc_18002B46B
0x18002b45e  cmp     [rdi+136h], r12b
0x18002b465  jz      loc_18002B76F
0x18002b46b  lea     rcx, [rbp+57h+var_60]; struct IHNetCfgMgr **
0x18002b46f  mov     [rbp+57h+var_60], r12
0x18002b473  call    ?HrGetHNetCfgMgr@@YAJPEAPEAUIHNetCfgMgr@@@Z; HrGetHNetCfgMgr(IHNetCfgMgr * *)
0x18002b478  mov     ebx, eax
0x18002b47a  test    eax, eax
0x18002b47c  js      loc_18002B73E
0x18002b482  mov     rsi, [rbp+57h+var_60]
0x18002b486  lea     r8, [rbp+57h+var_68]
0x18002b48a  mov     rdx, [r14]
0x18002b48d  mov     rcx, rsi
0x18002b490  mov     [rbp+57h+var_68], r12
0x18002b494  mov     rax, [rsi]
0x18002b497  mov     rax, [rax+18h]
0x18002b49b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4a0  mov     ebx, eax
0x18002b4a2  test    eax, eax
0x18002b4a4  js      loc_18002B72B
0x18002b4aa  lea     rdx, [rbp+57h+var_50]; struct IHNetConnection **
0x18002b4ae  mov     [rbp+57h+var_50], r12
0x18002b4b2  mov     rcx, rdi; this
0x18002b4b5  call    ?HrGetIHNetConnection@DialupConnection@@QEAAJPEAPEAUIHNetConnection@@@Z; DialupConnection::HrGetIHNetConnection(IHNetConnection * *)
0x18002b4ba  mov     ebx, eax
0x18002b4bc  test    eax, eax
0x18002b4be  js      loc_18002B722
0x18002b4c4  mov     rcx, [rbp+57h+var_68]
0x18002b4c8  lea     r8, [rbp+57h+var_60]
0x18002b4cc  mov     [rbp+57h+var_60], r12
0x18002b4d0  xor     edx, edx
0x18002b4d2  mov     rax, [rcx]
0x18002b4d5  mov     rax, [rax+68h]
0x18002b4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4de  test    eax, eax
0x18002b4e0  js      loc_18002B66B
0x18002b4e6  mov     [rbp+57h+var_44], r12d
0x18002b4ea  mov     [rbp+57h+var_80], r12
0x18002b4ee  mov     rcx, [rbp+57h+var_60]
0x18002b4f2  lea     r9, [rbp+57h+var_44]
0x18002b4f6  lea     r8, [rbp+57h+var_80]
0x18002b4fa  mov     edx, 1
0x18002b4ff  mov     rax, [rcx]
0x18002b502  mov     rax, [rax+18h]
0x18002b506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b50b  test    eax, eax
0x18002b50d  jnz     loc_18002B662
0x18002b513  cmp     [rbp+57h+var_44], 1
0x18002b517  jz      short loc_18002B51E
0x18002b519  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002b51e  mov     rcx, [rbp+57h+var_80]
0x18002b522  lea     rdx, [rbp+57h+var_88]
0x18002b526  mov     [rbp+57h+var_88], r12
0x18002b52a  mov     rax, [rcx]
0x18002b52d  mov     rax, [rax+20h]
0x18002b531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b536  test    eax, eax
0x18002b538  js      loc_18002B654
0x18002b53e  mov     rcx, [rbp+57h+var_50]
0x18002b542  lea     r8, [rbp+57h+var_70]
0x18002b546  mov     rdx, [rbp+57h+var_88]
0x18002b54a  mov     [rbp+57h+var_70], r12
0x18002b54e  mov     rax, [rcx]
0x18002b551  mov     rax, [rax+70h]
0x18002b555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b55a  test    eax, eax
0x18002b55c  js      loc_18002B64B
0x18002b562  mov     rcx, [rbp+57h+var_70]
0x18002b566  lea     rdx, [rbp+57h+var_48]
0x18002b56a  mov     [rbp+57h+var_48], r12b
0x18002b56e  mov     rax, [rcx]
0x18002b571  mov     rax, [rax+28h]
0x18002b575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b57a  test    eax, eax
0x18002b57c  js      loc_18002B642
0x18002b582  cmp     [rbp+57h+var_48], 1
0x18002b586  jnz     short loc_18002B5A2
0x18002b588  mov     rcx, [rbp+57h+var_80]
0x18002b58c  mov     dl, 1
0x18002b58e  mov     rax, [rcx]
0x18002b591  mov     rax, [rax+30h]
0x18002b595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b59a  test    eax, eax
0x18002b59c  js      loc_18002B642
0x18002b5a2  mov     rcx, [rbp+57h+var_70]
0x18002b5a6  lea     rdx, [rbp+57h+pv]
0x18002b5aa  mov     dword ptr [rbp+57h+pv], r12d
0x18002b5ae  mov     rax, [rcx]
0x18002b5b1  mov     rax, [rax+50h]
0x18002b5b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5ba  test    eax, eax
0x18002b5bc  js      loc_18002B642
0x18002b5c2  mov     edx, dword ptr [rbp+57h+pv]
0x18002b5c5  test    edx, edx
0x18002b5c7  jz      short loc_18002B5DD
0x18002b5c9  mov     rcx, [rbp+57h+var_80]
0x18002b5cd  mov     rax, [rcx]
0x18002b5d0  mov     rax, [rax+58h]
0x18002b5d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5d9  test    eax, eax
0x18002b5db  js      short loc_18002B642
0x18002b5dd  mov     rcx, [rbp+57h+var_70]
0x18002b5e1  lea     rdx, [rbp+57h+var_47]
0x18002b5e5  mov     [rbp+57h+var_47], r12b
0x18002b5e9  mov     rax, [rcx]
0x18002b5ec  mov     rax, [rax+38h]
0x18002b5f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5f5  test    eax, eax
0x18002b5f7  js      short loc_18002B642
0x18002b5f9  cmp     [rbp+57h+var_47], 1
0x18002b5fd  jnz     short loc_18002B642
0x18002b5ff  mov     rcx, [rbp+57h+var_70]
0x18002b603  lea     rdx, [rbp+57h+pv]
0x18002b607  mov     [rbp+57h+pv], r12
0x18002b60b  mov     rax, [rcx]
0x18002b60e  mov     rax, [rax+40h]
0x18002b612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b617  test    eax, eax
0x18002b619  js      short loc_18002B642
0x18002b61b  mov     rdx, [rbp+57h+pv]
0x18002b61f  cmp     r12w, [rdx]
0x18002b623  jz      short loc_18002B639
0x18002b625  mov     rcx, [rbp+57h+var_80]
0x18002b629  mov     rax, [rcx]
0x18002b62c  mov     rax, [rax+48h]
0x18002b630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b635  mov     rdx, [rbp+57h+pv]
0x18002b639  mov     rcx, rdx; pv
0x18002b63c  call    cs:__imp_CoTaskMemFree
0x18002b642  mov     rcx, [rbp+57h+var_70]; struct IUnknown *
0x18002b646  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002b64b  mov     rcx, [rbp+57h+var_88]; struct IUnknown *
0x18002b64f  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002b654  mov     rcx, [rbp+57h+var_80]; struct IUnknown *
0x18002b658  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002b65d  jmp     loc_18002B4EE
0x18002b662  mov     rcx, [rbp+57h+var_60]; struct IUnknown *
0x18002b666  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002b66b  mov     rcx, [rbp+57h+var_68]
0x18002b66f  cmp     [rdi+135h], r12b
0x18002b676  jz      short loc_18002B6DD
0x18002b678  mov     [rbp+57h+var_80], r12
0x18002b67c  lea     rdx, [rbp+57h+var_80]
0x18002b680  mov     rax, [rcx]
0x18002b683  mov     rax, [rax+48h]
0x18002b687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b68c  mov     ebx, eax
0x18002b68e  test    eax, eax
0x18002b690  js      loc_18002B719
0x18002b696  mov     rcx, [rbp+57h+var_50]
0x18002b69a  lea     rdx, [rbp+57h+var_88]
0x18002b69e  mov     [rbp+57h+var_88], r12
0x18002b6a2  mov     rax, [rcx]
0x18002b6a5  mov     rax, [rax+78h]
0x18002b6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6ae  mov     ebx, eax
0x18002b6b0  test    eax, eax
0x18002b6b2  js      short loc_18002B6D7
0x18002b6b4  mov     rcx, [rbp+57h+var_68]
0x18002b6b8  mov     rdx, [rbp+57h+var_88]
0x18002b6bc  mov     rax, [rcx]
0x18002b6bf  mov     rax, [rax+80h]
0x18002b6c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6cb  mov     rcx, [rbp+57h+var_88]; pv
0x18002b6cf  mov     ebx, eax
0x18002b6d1  call    cs:__imp_CoTaskMemFree
0x18002b6d7  mov     rcx, [rbp+57h+var_80]
0x18002b6db  jmp     short loc_18002B714
0x18002b6dd  mov     [rbp+57h+var_88], r12
0x18002b6e1  lea     r8, [rbp+57h+var_88]
0x18002b6e5  mov     rax, [rcx]
0x18002b6e8  lea     rdx, _GUID_85d18b72_3032_11d4_9348_00c04f8eeb71
0x18002b6ef  mov     rax, [rax+40h]
0x18002b6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6f8  mov     ebx, eax
0x18002b6fa  test    eax, eax
0x18002b6fc  js      short loc_18002B719
0x18002b6fe  mov     rcx, [rbp+57h+var_88]
0x18002b702  mov     rax, [rcx]
0x18002b705  mov     rax, [rax+18h]
0x18002b709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b70e  mov     rcx, [rbp+57h+var_88]; struct IUnknown *
0x18002b712  mov     ebx, eax
0x18002b714  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002b719  mov     rcx, [rbp+57h+var_50]; struct IUnknown *
0x18002b71d  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002b722  mov     rcx, [rbp+57h+var_68]; struct IUnknown *
0x18002b726  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002b72b  mov     rcx, rsi; struct IUnknown *
0x18002b72e  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002b733  test    ebx, ebx
0x18002b735  jns     short loc_18002B76F
0x18002b737  jmp     short loc_18002B73E
0x18002b739  mov     ebx, 80004003h
0x18002b73e  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
