# NotifyComponent(ushort const *,PROF_NOTIFY_EVENT_FLAGS,PROF_NOTIFY_PARAM *,PROF_NOTIFY_FLAGS,void *)

- ea: `0x180013048`
- end: `0x18001355b`
- name: `?NotifyComponent@@YAJPEBGW4PROF_NOTIFY_EVENT_FLAGS@@PEAUPROF_NOTIFY_PARAM@@W4PROF_NOTIFY_FLAGS@@PEAX@Z`
- size: `1299`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800128b0`

## callees

- `0x180008200`
- `0x180009b70`
- `0x18000a320`
- `0x180011e80`
- `0x180012320`
- `0x180013048`
- `0x180025274`
- `0x18002d2d8`
- `0x18002f8e0`
- `0x18003a730`
- `0x18003f42c`
- `0x18004248c`
- `0x180042544`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800130a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001348c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800130a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001348c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013137`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013137`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800130d1`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800130d1`

## string_xrefs

- `0x1800130e4`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x180013160`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x1800131a1`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x180013216`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x180013303`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x180013452`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x1800134b9`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x180013530`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x180013092`: `NotifyComponent`
- `0x18001308b`: `CLSID:%ws, NotifyEventFlags:0x%08x, NotifyFlags:0x%08x`
- `0x180013151`: `CLSID: %ws`
- `0x18001329d`: `CLSID: %ws`
- `0x1800132f4`: `CLSID: %ws`
- `0x18001336c`: `CLSID: %ws`
- `0x1800133b9`: `CLSID: %ws`
- `0x1800133ff`: `CLSID: %ws`
- `0x18001343e`: `CLSID: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NotifyComponent(const OLECHAR *a1, int a2, _QWORD *a3, char a4, void *a5)
{
  ULONGLONG TickCount64; // rsi
  HRESULT v8; // eax
  unsigned int v9; // edi
  HRESULT v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  ULONGLONG v19; // rax
  unsigned __int64 v20; // rcx
  int ppva; // [rsp+20h] [rbp-A1h]
  IUnknown *pProxy; // [rsp+30h] [rbp-91h] BYREF
  LPCOLESTR lpsz; // [rsp+38h] [rbp-89h] BYREF
  void *v26; // [rsp+40h] [rbp-81h] BYREF
  char v27; // [rsp+48h] [rbp-79h]
  int v28; // [rsp+50h] [rbp-71h] BYREF
  _QWORD v29[2]; // [rsp+58h] [rbp-69h] BYREF
  char v30; // [rsp+68h] [rbp-59h]
  _BYTE v31[80]; // [rsp+70h] [rbp-51h] BYREF
  GUID pclsid; // [rsp+C0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  lpsz = a1;
  v28 = a2;
  ProfileTelemetry::WatchCurrentThread(
    v31,
    "NotifyComponent",
    "CLSID:%ws, NotifyEventFlags:0x%08x, NotifyFlags:0x%08x",
    a1);
  TickCount64 = GetTickCount64();
  v29[0] = &v28;
  v29[1] = &lpsz;
  v30 = 1;
  pclsid = 0;
  v8 = CLSIDFromString(lpsz, &pclsid);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
      (const char *)(unsigned int)v8,
      a2);
LABEL_39:
    v30 = 0;
    lambda_1be2c144ba64295bdaab4f8abb3c8f9a_::operator()(v29);
    goto LABEL_48;
  }
  pProxy = 0;
  v10 = CoCreateInstance(
          &pclsid,
          0,
          (a4 & 1) != 0 ? 1 : 65540,
          &GUID_e10f6c3a_f1ae_4adc_aa9d_2fe65525666e,
          (LPVOID *)&pProxy);
  v9 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
      (const char *)(unsigned int)v10,
      (int)"CLSID: %ws",
      (const char *)lpsz);
LABEL_38:
    wil::com_ptr_t<IProfileNotify,wil::err_exception_policy>::~com_ptr_t<IProfileNotify,wil::err_exception_policy>((__int64 *)&pProxy);
    goto LABEL_39;
  }
  v26 = 0;
  v27 = 0;
  if ( (a4 & 2) != 0 )
  {
    v11 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v26, a5);
    v9 = v11;
    if ( v11 < 0 )
    {
      v12 = 143;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
        (const char *)(unsigned int)v11,
        ppva);
LABEL_37:
      CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v26);
      goto LABEL_38;
    }
  }
  if ( (a4 & 1) == 0 )
  {
    v11 = SetProxySecurity(pProxy);
    v9 = v11;
    if ( v11 < 0 )
    {
      v12 = 148;
      goto LABEL_8;
    }
  }
  switch ( v28 )
  {
    case 1:
      v18 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD, _QWORD))pProxy->lpVtbl[1].QueryInterface)(
              pProxy,
              *a3,
              a3[1],
              *((unsigned int *)a3 + 6));
      v9 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x9D,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
          (const char *)(unsigned int)v18,
          (int)"CLSID: %ws",
          (const char *)lpsz);
        goto LABEL_37;
      }
      break;
    case 2:
      v17 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD, _QWORD))pProxy->lpVtbl[1].AddRef)(
              pProxy,
              *a3,
              a3[1],
              *((unsigned int *)a3 + 6));
      v9 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xA2,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
          (const char *)(unsigned int)v17,
          (int)"CLSID: %ws",
          (const char *)lpsz);
        goto LABEL_37;
      }
      break;
    case 8:
      ppva = *((_DWORD *)a3 + 6);
      v16 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD, _QWORD))pProxy->lpVtbl[1].Release)(
              pProxy,
              a3[2],
              *a3,
              a3[1]);
      v9 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xA8,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
          (const char *)(unsigned int)v16,
          (int)"CLSID: %ws",
          (const char *)lpsz);
        goto LABEL_37;
      }
      break;
    case 16:
      v15 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD, _QWORD))pProxy->lpVtbl[2].QueryInterface)(
              pProxy,
              *a3,
              a3[1],
              *((unsigned int *)a3 + 6));
      v9 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xAD,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
          (const char *)(unsigned int)v15,
          (int)"CLSID: %ws",
          (const char *)lpsz);
        goto LABEL_37;
      }
      break;
    case 32:
      ppva = *((_DWORD *)a3 + 7) == 1;
      v14 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD, _QWORD))pProxy->lpVtbl[2].AddRef)(
              pProxy,
              *a3,
              a3[1],
              *((unsigned int *)a3 + 6));
      v9 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xB3,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
          (const char *)(unsigned int)v14,
          (int)"CLSID: %ws",
          (const char *)lpsz);
        CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v26);
        if ( pProxy )
          ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
        goto LABEL_39;
      }
      break;
    case 64:
      ppva = *((_DWORD *)a3 + 7) == 0;
      v13 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD, _QWORD))pProxy->lpVtbl[2].Release)(
              pProxy,
              *a3,
              a3[1],
              *((unsigned int *)a3 + 6));
      v9 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xB9,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
          (const char *)(unsigned int)v13,
          (int)"CLSID: %ws",
          (const char *)lpsz);
        goto LABEL_37;
      }
      break;
    default:
      v9 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBC,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
        (const char *)0x80070057LL,
        ppva);
      if ( v27 )
      {
        RevertToUser(&v26);
        v26 = 0;
        v27 = 0;
      }
      if ( pProxy )
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      goto LABEL_39;
  }
  v30 = 0;
  v19 = GetTickCount64();
  if ( v19 < TickCount64 )
    v20 = -1;
  else
    v20 = v19 - TickCount64;
  if ( v19 >= TickCount64 )
  {
    if ( v20 > 0x3E8 )
    {
      v9 = -2147023436;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
        (const char *)0x800705B4LL,
        ppva);
      CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v26);
      wil::com_ptr_t<IProfileNotify,wil::err_exception_policy>::~com_ptr_t<IProfileNotify,wil::err_exception_policy>((__int64 *)&pProxy);
      goto LABEL_48;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC3,
      (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
      v19 < TickCount64 ? (const char *)0x80070216LL : 0);
  }
  CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v26);
  if ( pProxy )
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  v9 = 0;
LABEL_48:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v31);
  return v9;
}

```

## disassembly

```asm
0x180013048  push    rbp
0x18001304a  push    rbx
0x18001304b  push    rsi
0x18001304c  push    rdi
0x18001304d  push    r12
0x18001304f  push    r14
0x180013051  push    r15
0x180013053  lea     rbp, [rsp-1Fh]
0x180013058  sub     rsp, 0E0h
0x18001305f  mov     rax, cs:__security_cookie
0x180013066  xor     rax, rsp
0x180013069  mov     [rbp+4Fh+var_40], rax
0x18001306d  mov     r15d, r9d
0x180013070  mov     rbx, r8
0x180013073  mov     [rsp+110h+lpsz], rcx
0x180013078  mov     [rbp+4Fh+var_C0], edx
0x18001307b  mov     r12, [rbp+4Fh+arg_20]
0x18001307f  mov     dword ptr [rsp+110h+var_E8], r9d
0x180013084  mov     dword ptr [rsp+110h+ppv], edx; int
0x180013088  mov     r9, rcx
0x18001308b  lea     r8, aClsidWsNotifye; "CLSID:%ws, NotifyEventFlags:0x%08x, Not"...
0x180013092  lea     rdx, aNotifycomponen; "NotifyComponent"
0x180013099  lea     rcx, [rbp+4Fh+var_A0]
0x18001309d  call    ?WatchCurrentThread@ProfileTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; ProfileTelemetry::WatchCurrentThread(char const *,char const *,...)
0x1800130a2  nop
0x1800130a3  call    cs:__imp_GetTickCount64
0x1800130a9  mov     rsi, rax
0x1800130ac  lea     rax, [rbp+4Fh+var_C0]
0x1800130b0  mov     [rbp+4Fh+var_B8], rax
0x1800130b4  lea     rax, [rsp+110h+lpsz]
0x1800130b9  mov     [rbp+4Fh+var_B0], rax
0x1800130bd  mov     [rbp+4Fh+var_A8], 1
0x1800130c1  xorps   xmm0, xmm0
0x1800130c4  movups  xmmword ptr [rbp+4Fh+pclsid.Data1], xmm0
0x1800130c8  lea     rdx, [rbp+4Fh+pclsid]; pclsid
0x1800130cc  mov     rcx, [rsp+110h+lpsz]; lpsz
0x1800130d1  call    cs:__imp_CLSIDFromString
0x1800130d7  mov     edi, eax
0x1800130d9  test    eax, eax
0x1800130db  jns     short loc_1800130FA
0x1800130dd  mov     rcx, [rbp+57h]; this
0x1800130e1  mov     r9d, eax; char *
0x1800130e4  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800130eb  mov     edx, 85h; void *
0x1800130f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800130f5  jmp     loc_180013479
0x1800130fa  mov     r14d, r15d
0x1800130fd  and     r14d, 1
0x180013101  mov     eax, r14d
0x180013104  neg     eax
0x180013106  sbb     r8d, r8d
0x180013109  and     r8d, 0FFFEFFFDh
0x180013110  add     r8d, 10004h; dwClsContext
0x180013117  mov     [rsp+110h+pProxy], 0
0x180013120  lea     rax, [rsp+110h+pProxy]
0x180013125  mov     [rsp+110h+ppv], rax; int
0x18001312a  lea     r9, _GUID_e10f6c3a_f1ae_4adc_aa9d_2fe65525666e; riid
0x180013131  xor     edx, edx; pUnkOuter
0x180013133  lea     rcx, [rbp+4Fh+pclsid]; rclsid
0x180013137  call    cs:__imp_CoCreateInstance
0x18001313d  mov     edi, eax
0x18001313f  test    eax, eax
0x180013141  jns     short loc_180013176
0x180013143  mov     rcx, [rbp+57h]; this
0x180013147  mov     rdx, [rsp+110h+lpsz]
0x18001314c  mov     [rsp+110h+var_E8], rdx; char *
0x180013151  lea     rdx, aClsidWs; "CLSID: %ws"
0x180013158  mov     [rsp+110h+ppv], rdx; int
0x18001315d  mov     r9d, eax; char *
0x180013160  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x180013167  mov     edx, 8Ah; void *
0x18001316c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180013171  jmp     loc_18001346E
0x180013176  mov     [rsp+110h+var_D0], 0
0x18001317f  mov     [rbp+4Fh+var_C8], 0
0x180013183  test    r15b, 2
0x180013187  jz      short loc_1800131B9
0x180013189  mov     rdx, r12; void *
0x18001318c  lea     rcx, [rsp+110h+var_D0]; this
0x180013191  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x180013196  mov     edi, eax
0x180013198  test    eax, eax
0x18001319a  jns     short loc_1800131B9
0x18001319c  mov     edx, 8Fh; void *
0x1800131a1  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800131a8  mov     r9d, eax; char *
0x1800131ab  mov     rcx, [rbp+57h]; this
0x1800131af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800131b4  jmp     loc_180013463
0x1800131b9  test    r14d, r14d
0x1800131bc  jnz     short loc_1800131D5
0x1800131be  mov     rcx, [rsp+110h+pProxy]; pProxy
0x1800131c3  call    ?SetProxySecurity@@YAJPEAUIUnknown@@@Z; SetProxySecurity(IUnknown *)
0x1800131c8  mov     edi, eax
0x1800131ca  test    eax, eax
0x1800131cc  jns     short loc_1800131D5
0x1800131ce  mov     edx, 94h
0x1800131d3  jmp     short loc_1800131A1
0x1800131d5  mov     ecx, [rbp+4Fh+var_C0]
0x1800131d8  sub     ecx, 1
0x1800131db  jz      loc_180013412
0x1800131e1  sub     ecx, 1
0x1800131e4  jz      loc_1800133CF
0x1800131ea  sub     ecx, 6
0x1800131ed  jz      loc_180013382
0x1800131f3  sub     ecx, 8
0x1800131f6  jz      loc_18001333C
0x1800131fc  sub     ecx, 10h
0x1800131ff  jz      loc_1800132B3
0x180013205  cmp     ecx, 20h ; ' '
0x180013208  jz      short loc_180013261
0x18001320a  mov     rcx, [rbp+57h]; this
0x18001320e  mov     edi, 80070057h
0x180013213  mov     r9d, edi; char *
0x180013216  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001321d  mov     edx, 0BCh; void *
0x180013222  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013227  nop
0x180013228  cmp     [rbp+4Fh+var_C8], 0
0x18001322c  jz      short loc_180013245
0x18001322e  lea     rcx, [rsp+110h+var_D0]; void **
0x180013233  call    ?RevertToUser@@YAJPEAPEAX@Z; RevertToUser(void * *)
0x180013238  mov     [rsp+110h+var_D0], 0
0x180013241  mov     [rbp+4Fh+var_C8], 0
0x180013245  mov     rcx, [rsp+110h+pProxy]
0x18001324a  test    rcx, rcx
0x18001324d  jz      short loc_18001325C
0x18001324f  mov     rax, [rcx]
0x180013252  mov     rax, [rax+10h]
0x180013256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001325b  nop
0x18001325c  jmp     loc_180013479
0x180013261  mov     rcx, [rsp+110h+pProxy]
0x180013266  mov     rax, [rcx]
0x180013269  xor     edx, edx
0x18001326b  cmp     [rbx+1Ch], edx
0x18001326e  setz    dl
0x180013271  mov     dword ptr [rsp+110h+ppv], edx; int
0x180013275  mov     r9d, [rbx+18h]
0x180013279  mov     r8, [rbx+8]
0x18001327d  mov     rdx, [rbx]
0x180013280  mov     rax, [rax+40h]
0x180013284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013289  mov     edi, eax
0x18001328b  test    eax, eax
0x18001328d  jns     loc_180013488
0x180013293  mov     rdx, [rsp+110h+lpsz]
0x180013298  mov     [rsp+110h+var_E8], rdx
0x18001329d  lea     rdx, aClsidWs; "CLSID: %ws"
0x1800132a4  mov     [rsp+110h+ppv], rdx
0x1800132a9  mov     edx, 0B9h
0x1800132ae  jmp     loc_18001344F
0x1800132b3  mov     rcx, [rsp+110h+pProxy]
0x1800132b8  mov     rax, [rcx]
0x1800132bb  xor     edx, edx
0x1800132bd  cmp     dword ptr [rbx+1Ch], 1
0x1800132c1  setz    dl
0x1800132c4  mov     dword ptr [rsp+110h+ppv], edx
0x1800132c8  mov     r9d, [rbx+18h]
0x1800132cc  mov     r8, [rbx+8]
0x1800132d0  mov     rdx, [rbx]
0x1800132d3  mov     rax, [rax+38h]
0x1800132d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132dc  mov     edi, eax
0x1800132de  test    eax, eax
0x1800132e0  jns     loc_180013488
0x1800132e6  mov     rcx, [rbp+57h]; this
0x1800132ea  mov     rdx, [rsp+110h+lpsz]
0x1800132ef  mov     [rsp+110h+var_E8], rdx; char *
0x1800132f4  lea     rdx, aClsidWs; "CLSID: %ws"
0x1800132fb  mov     [rsp+110h+ppv], rdx; int
0x180013300  mov     r9d, eax; char *
0x180013303  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001330a  mov     edx, 0B3h; void *
0x18001330f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180013314  nop
0x180013315  lea     rcx, [rsp+110h+var_D0]; this
0x18001331a  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18001331f  nop
0x180013320  mov     rcx, [rsp+110h+pProxy]
0x180013325  test    rcx, rcx
0x180013328  jz      short loc_180013337
0x18001332a  mov     rax, [rcx]
0x18001332d  mov     rax, [rax+10h]
0x180013331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013336  nop
0x180013337  jmp     loc_180013479
0x18001333c  mov     rcx, [rsp+110h+pProxy]
0x180013341  mov     rax, [rcx]
0x180013344  mov     r9d, [rbx+18h]
0x180013348  mov     r8, [rbx+8]
0x18001334c  mov     rdx, [rbx]
0x18001334f  mov     rax, [rax+30h]
0x180013353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013358  mov     edi, eax
0x18001335a  test    eax, eax
0x18001335c  jns     loc_180013488
0x180013362  mov     rdx, [rsp+110h+lpsz]
0x180013367  mov     [rsp+110h+var_E8], rdx
0x18001336c  lea     rdx, aClsidWs; "CLSID: %ws"
0x180013373  mov     [rsp+110h+ppv], rdx
0x180013378  mov     edx, 0ADh
0x18001337d  jmp     loc_18001344F
0x180013382  mov     rcx, [rsp+110h+pProxy]
0x180013387  mov     rax, [rcx]
0x18001338a  mov     edx, [rbx+18h]
0x18001338d  mov     dword ptr [rsp+110h+ppv], edx
0x180013391  mov     r9, [rbx+8]
0x180013395  mov     r8, [rbx]
0x180013398  mov     rdx, [rbx+10h]
0x18001339c  mov     rax, [rax+28h]
0x1800133a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133a5  mov     edi, eax
0x1800133a7  test    eax, eax
0x1800133a9  jns     loc_180013488
0x1800133af  mov     rdx, [rsp+110h+lpsz]
0x1800133b4  mov     [rsp+110h+var_E8], rdx
0x1800133b9  lea     rdx, aClsidWs; "CLSID: %ws"
0x1800133c0  mov     [rsp+110h+ppv], rdx
0x1800133c5  mov     edx, 0A8h
0x1800133ca  jmp     loc_18001344F
0x1800133cf  mov     rcx, [rsp+110h+pProxy]
0x1800133d4  mov     rax, [rcx]
0x1800133d7  mov     r9d, [rbx+18h]
0x1800133db  mov     r8, [rbx+8]
0x1800133df  mov     rdx, [rbx]
0x1800133e2  mov     rax, [rax+20h]
0x1800133e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133eb  mov     edi, eax
0x1800133ed  test    eax, eax
0x1800133ef  jns     loc_180013488
0x1800133f5  mov     rdx, [rsp+110h+lpsz]
0x1800133fa  mov     [rsp+110h+var_E8], rdx
0x1800133ff  lea     rdx, aClsidWs; "CLSID: %ws"
0x180013406  mov     [rsp+110h+ppv], rdx
0x18001340b  mov     edx, 0A2h
0x180013410  jmp     short loc_18001344F
0x180013412  mov     rcx, [rsp+110h+pProxy]
0x180013417  mov     rax, [rcx]
0x18001341a  mov     r9d, [rbx+18h]
0x18001341e  mov     r8, [rbx+8]
0x180013422  mov     rdx, [rbx]
0x180013425  mov     rax, [rax+18h]
0x180013429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001342e  mov     edi, eax
0x180013430  test    eax, eax
0x180013432  jns     short loc_180013488
0x180013434  mov     rdx, [rsp+110h+lpsz]
0x180013439  mov     [rsp+110h+var_E8], rdx; char *
0x18001343e  lea     rdx, aClsidWs; "CLSID: %ws"
0x180013445  mov     [rsp+110h+ppv], rdx; int
0x18001344a  mov     edx, 9Dh; void *
0x18001344f  mov     r9d, eax; char *
0x180013452  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x180013459  mov     rcx, [rbp+57h]; this
0x18001345d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180013462  nop
0x180013463  lea     rcx, [rsp+110h+var_D0]; this
0x180013468  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18001346d  nop
0x18001346e  lea     rcx, [rsp+110h+pProxy]
0x180013473  call    ??1?$com_ptr_t@UIProfileNotify@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IProfileNotify,wil::err_exception_policy>::~com_ptr_t<IProfileNotify,wil::err_exception_policy>(void)
0x180013478  nop
0x180013479  mov     [rbp+4Fh+var_A8], 0
0x18001347d  lea     rcx, [rbp+4Fh+var_B8]
0x180013481  call    _lambda_1be2c144ba64295bdaab4f8abb3c8f9a___operator__
0x180013486  jmp     short loc_1800134F2
0x180013488  mov     [rbp+4Fh+var_A8], 0
0x18001348c  call    cs:__imp_GetTickCount64
0x180013492  cmp     rax, rsi
0x180013495  jb      short loc_18001349F
0x180013497  mov     rcx, rax
0x18001349a  sub     rcx, rsi
0x18001349d  jmp     short loc_1800134A3
0x18001349f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800134a3  cmp     rax, rsi
0x1800134a6  sbb     r9d, r9d
0x1800134a9  and     r9d, 80070216h; char *
0x1800134b0  mov     r10, [rbp+57h]
0x1800134b4  cmp     rax, rsi
0x1800134b7  jnb     short loc_18001351B
0x1800134b9  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800134c0  mov     edx, 0C3h; void *
0x1800134c5  mov     rcx, r10; this
0x1800134c8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800134cd  nop
0x1800134ce  lea     rcx, [rsp+110h+var_D0]; this
0x1800134d3  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x1800134d8  nop
0x1800134d9  mov     rcx, [rsp+110h+pProxy]
0x1800134de  test    rcx, rcx
0x1800134e1  jz      short loc_1800134F0
0x1800134e3  mov     rax, [rcx]
0x1800134e6  mov     rax, [rax+10h]
0x1800134ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134ef  nop
0x1800134f0  xor     edi, edi
0x1800134f2  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800134f6  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800134fb  mov     eax, edi
  ... truncated ...
```
