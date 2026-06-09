# NotifyComponent(ushort const *,PROF_NOTIFY_EVENT_FLAGS,PROF_NOTIFY_PARAM *,PROF_NOTIFY_FLAGS,void *)

- ea: `0x1800156ec`
- end: `0x180015c18`
- name: `?NotifyComponent@@YAJPEBGW4PROF_NOTIFY_EVENT_FLAGS@@PEAUPROF_NOTIFY_PARAM@@W4PROF_NOTIFY_FLAGS@@PEAX@Z`
- size: `1324`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180014e90`

## callees

- `0x180005dd0`
- `0x1800073c0`
- `0x180007b58`
- `0x1800156ec`
- `0x180016ea0`
- `0x180017370`
- `0x180027960`
- `0x180030ad0`
- `0x180035860`
- `0x18003bc70`
- `0x180040bcc`
- `0x180043ed8`
- `0x180043f90`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180015747`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180015b42`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180015747`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180015b42`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800157e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800157e7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001577b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001577b`

## string_xrefs

- `0x180015794`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x180015816`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x180015857`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x1800158cc`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x1800159b9`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x180015b08`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x180015b75`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x180015bed`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x180015736`: `NotifyComponent`
- `0x18001572f`: `CLSID:%ws, NotifyEventFlags:0x%08x, NotifyFlags:0x%08x`
- `0x180015807`: `CLSID: %ws`
- `0x180015953`: `CLSID: %ws`
- `0x1800159aa`: `CLSID: %ws`
- `0x180015a22`: `CLSID: %ws`
- `0x180015a6f`: `CLSID: %ws`
- `0x180015ab5`: `CLSID: %ws`
- `0x180015af4`: `CLSID: %ws`

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
    wil::com_ptr_t<IProfileNotify,wil::err_exception_policy>::~com_ptr_t<IProfileNotify,wil::err_exception_policy>(&pProxy);
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
      wil::com_ptr_t<IProfileNotify,wil::err_exception_policy>::~com_ptr_t<IProfileNotify,wil::err_exception_policy>(&pProxy);
      goto LABEL_48;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
      v19 < TickCount64 ? (const char *)0x80070216LL : 0,
      ppva);
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
0x1800156ec  push    rbp
0x1800156ee  push    rbx
0x1800156ef  push    rsi
0x1800156f0  push    rdi
0x1800156f1  push    r12
0x1800156f3  push    r14
0x1800156f5  push    r15
0x1800156f7  lea     rbp, [rsp-1Fh]
0x1800156fc  sub     rsp, 0E0h
0x180015703  mov     rax, cs:__security_cookie
0x18001570a  xor     rax, rsp
0x18001570d  mov     [rbp+4Fh+var_40], rax
0x180015711  mov     r15d, r9d
0x180015714  mov     rbx, r8
0x180015717  mov     [rsp+110h+lpsz], rcx
0x18001571c  mov     [rbp+4Fh+var_C0], edx
0x18001571f  mov     r12, [rbp+4Fh+arg_20]
0x180015723  mov     dword ptr [rsp+110h+var_E8], r9d
0x180015728  mov     dword ptr [rsp+110h+ppv], edx; int
0x18001572c  mov     r9, rcx
0x18001572f  lea     r8, aClsidWsNotifye; "CLSID:%ws, NotifyEventFlags:0x%08x, Not"...
0x180015736  lea     rdx, aNotifycomponen; "NotifyComponent"
0x18001573d  lea     rcx, [rbp+4Fh+var_A0]
0x180015741  call    ?WatchCurrentThread@ProfileTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; ProfileTelemetry::WatchCurrentThread(char const *,char const *,...)
0x180015746  nop
0x180015747  call    cs:__imp_GetTickCount64
0x18001574e  nop     dword ptr [rax+rax+00h]
0x180015753  mov     rsi, rax
0x180015756  lea     rax, [rbp+4Fh+var_C0]
0x18001575a  mov     [rbp+4Fh+var_B8], rax
0x18001575e  lea     rax, [rsp+110h+lpsz]
0x180015763  mov     [rbp+4Fh+var_B0], rax
0x180015767  mov     [rbp+4Fh+var_A8], 1
0x18001576b  xorps   xmm0, xmm0
0x18001576e  movups  xmmword ptr [rbp+4Fh+pclsid.Data1], xmm0
0x180015772  lea     rdx, [rbp+4Fh+pclsid]; pclsid
0x180015776  mov     rcx, [rsp+110h+lpsz]; lpsz
0x18001577b  call    cs:__imp_CLSIDFromString
0x180015782  nop     dword ptr [rax+rax+00h]
0x180015787  mov     edi, eax
0x180015789  test    eax, eax
0x18001578b  jns     short loc_1800157AA
0x18001578d  mov     rcx, [rbp+57h]; this
0x180015791  mov     r9d, eax; char *
0x180015794  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001579b  mov     edx, 85h; void *
0x1800157a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800157a5  jmp     loc_180015B2F
0x1800157aa  mov     r14d, r15d
0x1800157ad  and     r14d, 1
0x1800157b1  mov     eax, r14d
0x1800157b4  neg     eax
0x1800157b6  sbb     r8d, r8d
0x1800157b9  and     r8d, 0FFFEFFFDh
0x1800157c0  add     r8d, 10004h; dwClsContext
0x1800157c7  mov     [rsp+110h+pProxy], 0
0x1800157d0  lea     rax, [rsp+110h+pProxy]
0x1800157d5  mov     [rsp+110h+ppv], rax; int
0x1800157da  lea     r9, _GUID_e10f6c3a_f1ae_4adc_aa9d_2fe65525666e; riid
0x1800157e1  xor     edx, edx; pUnkOuter
0x1800157e3  lea     rcx, [rbp+4Fh+pclsid]; rclsid
0x1800157e7  call    cs:__imp_CoCreateInstance
0x1800157ee  nop     dword ptr [rax+rax+00h]
0x1800157f3  mov     edi, eax
0x1800157f5  test    eax, eax
0x1800157f7  jns     short loc_18001582C
0x1800157f9  mov     rcx, [rbp+57h]; this
0x1800157fd  mov     rdx, [rsp+110h+lpsz]
0x180015802  mov     [rsp+110h+var_E8], rdx; char *
0x180015807  lea     rdx, aClsidWs; "CLSID: %ws"
0x18001580e  mov     [rsp+110h+ppv], rdx; int
0x180015813  mov     r9d, eax; char *
0x180015816  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001581d  mov     edx, 8Ah; void *
0x180015822  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180015827  jmp     loc_180015B24
0x18001582c  mov     [rsp+110h+var_D0], 0
0x180015835  mov     [rbp+4Fh+var_C8], 0
0x180015839  test    r15b, 2
0x18001583d  jz      short loc_18001586F
0x18001583f  mov     rdx, r12; void *
0x180015842  lea     rcx, [rsp+110h+var_D0]; this
0x180015847  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x18001584c  mov     edi, eax
0x18001584e  test    eax, eax
0x180015850  jns     short loc_18001586F
0x180015852  mov     edx, 8Fh; void *
0x180015857  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001585e  mov     r9d, eax; char *
0x180015861  mov     rcx, [rbp+57h]; this
0x180015865  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001586a  jmp     loc_180015B19
0x18001586f  test    r14d, r14d
0x180015872  jnz     short loc_18001588B
0x180015874  mov     rcx, [rsp+110h+pProxy]; pProxy
0x180015879  call    ?SetProxySecurity@@YAJPEAUIUnknown@@@Z; SetProxySecurity(IUnknown *)
0x18001587e  mov     edi, eax
0x180015880  test    eax, eax
0x180015882  jns     short loc_18001588B
0x180015884  mov     edx, 94h
0x180015889  jmp     short loc_180015857
0x18001588b  mov     ecx, [rbp+4Fh+var_C0]
0x18001588e  sub     ecx, 1
0x180015891  jz      loc_180015AC8
0x180015897  sub     ecx, 1
0x18001589a  jz      loc_180015A85
0x1800158a0  sub     ecx, 6
0x1800158a3  jz      loc_180015A38
0x1800158a9  sub     ecx, 8
0x1800158ac  jz      loc_1800159F2
0x1800158b2  sub     ecx, 10h
0x1800158b5  jz      loc_180015969
0x1800158bb  cmp     ecx, 20h ; ' '
0x1800158be  jz      short loc_180015917
0x1800158c0  mov     rcx, [rbp+57h]; this
0x1800158c4  mov     edi, 80070057h
0x1800158c9  mov     r9d, edi; char *
0x1800158cc  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800158d3  mov     edx, 0BCh; void *
0x1800158d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800158dd  nop
0x1800158de  cmp     [rbp+4Fh+var_C8], 0
0x1800158e2  jz      short loc_1800158FB
0x1800158e4  lea     rcx, [rsp+110h+var_D0]; void **
0x1800158e9  call    ?RevertToUser@@YAJPEAPEAX@Z; RevertToUser(void * *)
0x1800158ee  mov     [rsp+110h+var_D0], 0
0x1800158f7  mov     [rbp+4Fh+var_C8], 0
0x1800158fb  mov     rcx, [rsp+110h+pProxy]
0x180015900  test    rcx, rcx
0x180015903  jz      short loc_180015912
0x180015905  mov     rax, [rcx]
0x180015908  mov     rax, [rax+10h]
0x18001590c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015911  nop
0x180015912  jmp     loc_180015B2F
0x180015917  mov     rcx, [rsp+110h+pProxy]
0x18001591c  mov     rax, [rcx]
0x18001591f  xor     edx, edx
0x180015921  cmp     [rbx+1Ch], edx
0x180015924  setz    dl
0x180015927  mov     dword ptr [rsp+110h+ppv], edx; int
0x18001592b  mov     r9d, [rbx+18h]
0x18001592f  mov     r8, [rbx+8]
0x180015933  mov     rdx, [rbx]
0x180015936  mov     rax, [rax+40h]
0x18001593a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001593f  mov     edi, eax
0x180015941  test    eax, eax
0x180015943  jns     loc_180015B3E
0x180015949  mov     rdx, [rsp+110h+lpsz]
0x18001594e  mov     [rsp+110h+var_E8], rdx
0x180015953  lea     rdx, aClsidWs; "CLSID: %ws"
0x18001595a  mov     [rsp+110h+ppv], rdx
0x18001595f  mov     edx, 0B9h
0x180015964  jmp     loc_180015B05
0x180015969  mov     rcx, [rsp+110h+pProxy]
0x18001596e  mov     rax, [rcx]
0x180015971  xor     edx, edx
0x180015973  cmp     dword ptr [rbx+1Ch], 1
0x180015977  setz    dl
0x18001597a  mov     dword ptr [rsp+110h+ppv], edx
0x18001597e  mov     r9d, [rbx+18h]
0x180015982  mov     r8, [rbx+8]
0x180015986  mov     rdx, [rbx]
0x180015989  mov     rax, [rax+38h]
0x18001598d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015992  mov     edi, eax
0x180015994  test    eax, eax
0x180015996  jns     loc_180015B3E
0x18001599c  mov     rcx, [rbp+57h]; this
0x1800159a0  mov     rdx, [rsp+110h+lpsz]
0x1800159a5  mov     [rsp+110h+var_E8], rdx; char *
0x1800159aa  lea     rdx, aClsidWs; "CLSID: %ws"
0x1800159b1  mov     [rsp+110h+ppv], rdx; int
0x1800159b6  mov     r9d, eax; char *
0x1800159b9  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800159c0  mov     edx, 0B3h; void *
0x1800159c5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800159ca  nop
0x1800159cb  lea     rcx, [rsp+110h+var_D0]; this
0x1800159d0  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x1800159d5  nop
0x1800159d6  mov     rcx, [rsp+110h+pProxy]
0x1800159db  test    rcx, rcx
0x1800159de  jz      short loc_1800159ED
0x1800159e0  mov     rax, [rcx]
0x1800159e3  mov     rax, [rax+10h]
0x1800159e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159ec  nop
0x1800159ed  jmp     loc_180015B2F
0x1800159f2  mov     rcx, [rsp+110h+pProxy]
0x1800159f7  mov     rax, [rcx]
0x1800159fa  mov     r9d, [rbx+18h]
0x1800159fe  mov     r8, [rbx+8]
0x180015a02  mov     rdx, [rbx]
0x180015a05  mov     rax, [rax+30h]
0x180015a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a0e  mov     edi, eax
0x180015a10  test    eax, eax
0x180015a12  jns     loc_180015B3E
0x180015a18  mov     rdx, [rsp+110h+lpsz]
0x180015a1d  mov     [rsp+110h+var_E8], rdx
0x180015a22  lea     rdx, aClsidWs; "CLSID: %ws"
0x180015a29  mov     [rsp+110h+ppv], rdx
0x180015a2e  mov     edx, 0ADh
0x180015a33  jmp     loc_180015B05
0x180015a38  mov     rcx, [rsp+110h+pProxy]
0x180015a3d  mov     rax, [rcx]
0x180015a40  mov     edx, [rbx+18h]
0x180015a43  mov     dword ptr [rsp+110h+ppv], edx
0x180015a47  mov     r9, [rbx+8]
0x180015a4b  mov     r8, [rbx]
0x180015a4e  mov     rdx, [rbx+10h]
0x180015a52  mov     rax, [rax+28h]
0x180015a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a5b  mov     edi, eax
0x180015a5d  test    eax, eax
0x180015a5f  jns     loc_180015B3E
0x180015a65  mov     rdx, [rsp+110h+lpsz]
0x180015a6a  mov     [rsp+110h+var_E8], rdx
0x180015a6f  lea     rdx, aClsidWs; "CLSID: %ws"
0x180015a76  mov     [rsp+110h+ppv], rdx
0x180015a7b  mov     edx, 0A8h
0x180015a80  jmp     loc_180015B05
0x180015a85  mov     rcx, [rsp+110h+pProxy]
0x180015a8a  mov     rax, [rcx]
0x180015a8d  mov     r9d, [rbx+18h]
0x180015a91  mov     r8, [rbx+8]
0x180015a95  mov     rdx, [rbx]
0x180015a98  mov     rax, [rax+20h]
0x180015a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015aa1  mov     edi, eax
0x180015aa3  test    eax, eax
0x180015aa5  jns     loc_180015B3E
0x180015aab  mov     rdx, [rsp+110h+lpsz]
0x180015ab0  mov     [rsp+110h+var_E8], rdx
0x180015ab5  lea     rdx, aClsidWs; "CLSID: %ws"
0x180015abc  mov     [rsp+110h+ppv], rdx
0x180015ac1  mov     edx, 0A2h
0x180015ac6  jmp     short loc_180015B05
0x180015ac8  mov     rcx, [rsp+110h+pProxy]
0x180015acd  mov     rax, [rcx]
0x180015ad0  mov     r9d, [rbx+18h]
0x180015ad4  mov     r8, [rbx+8]
0x180015ad8  mov     rdx, [rbx]
0x180015adb  mov     rax, [rax+18h]
0x180015adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ae4  mov     edi, eax
0x180015ae6  test    eax, eax
0x180015ae8  jns     short loc_180015B3E
0x180015aea  mov     rdx, [rsp+110h+lpsz]
0x180015aef  mov     [rsp+110h+var_E8], rdx; char *
0x180015af4  lea     rdx, aClsidWs; "CLSID: %ws"
0x180015afb  mov     [rsp+110h+ppv], rdx; int
0x180015b00  mov     edx, 9Dh; void *
0x180015b05  mov     r9d, eax; char *
0x180015b08  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x180015b0f  mov     rcx, [rbp+57h]; this
0x180015b13  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180015b18  nop
0x180015b19  lea     rcx, [rsp+110h+var_D0]; this
0x180015b1e  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180015b23  nop
0x180015b24  lea     rcx, [rsp+110h+pProxy]
0x180015b29  call    ??1?$com_ptr_t@UIProfileNotify@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IProfileNotify,wil::err_exception_policy>::~com_ptr_t<IProfileNotify,wil::err_exception_policy>(void)
0x180015b2e  nop
0x180015b2f  mov     [rbp+4Fh+var_A8], 0
0x180015b33  lea     rcx, [rbp+4Fh+var_B8]
0x180015b37  call    _lambda_1be2c144ba64295bdaab4f8abb3c8f9a___operator__
0x180015b3c  jmp     short loc_180015BAE
0x180015b3e  mov     [rbp+4Fh+var_A8], 0
0x180015b42  call    cs:__imp_GetTickCount64
0x180015b49  nop     dword ptr [rax+rax+00h]
0x180015b4e  cmp     rax, rsi
0x180015b51  jb      short loc_180015B5B
0x180015b53  mov     rcx, rax
0x180015b56  sub     rcx, rsi
0x180015b59  jmp     short loc_180015B5F
0x180015b5b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180015b5f  cmp     rax, rsi
0x180015b62  sbb     r9d, r9d
0x180015b65  and     r9d, 80070216h; char *
0x180015b6c  mov     r10, [rbp+57h]
0x180015b70  cmp     rax, rsi
0x180015b73  jnb     short loc_180015BD8
0x180015b75  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x180015b7c  mov     edx, 0C3h; void *
0x180015b81  mov     rcx, r10; this
0x180015b84  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015b89  nop
0x180015b8a  lea     rcx, [rsp+110h+var_D0]; this
0x180015b8f  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180015b94  nop
0x180015b95  mov     rcx, [rsp+110h+pProxy]
0x180015b9a  test    rcx, rcx
0x180015b9d  jz      short loc_180015BAC
0x180015b9f  mov     rax, [rcx]
0x180015ba2  mov     rax, [rax+10h]
0x180015ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bab  nop
  ... truncated ...
```
