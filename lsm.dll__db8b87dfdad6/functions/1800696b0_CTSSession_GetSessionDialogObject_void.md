# CTSSession::GetSessionDialogObject(void * *)

- ea: `0x1800696b0`
- end: `0x18006987a`
- name: `?GetSessionDialogObject@CTSSession@@AEAAJPEAPEAX@Z`
- size: `458`
- prototype: `__int64 __fastcall(CTSSession *__hidden this, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18006e3f0`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x180018200`
- `0x180026e00`
- `0x18004b460`
- `0x18004b830`
- `0x18004b890`
- `0x1800696b0`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069837`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069837`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18006972a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18006972a`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x1800697dc`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x1800697dc`

## string_xrefs

- `0x1800696f1`: `Session:%d!clsid:%s`
- `0x180069736`: `StringFromCLSID failed: 0x%x in %s`
- `0x180069813`: `ptrClassFactory->CreateInstance failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTSSession::GetSessionDialogObject(CTSSession *this, void **a2)
{
  unsigned __int16 *v3; // rdi
  unsigned int v4; // esi
  HRESULT v5; // eax
  unsigned int v6; // ebx
  const struct std::nothrow_t *v7; // rdx
  int v8; // eax
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rax
  int v11; // eax
  HRESULT Object; // eax
  int v13; // eax
  LPOLESTR lpsz; // [rsp+30h] [rbp-50h] BYREF
  void *ppv; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int64 v17; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 v18[8]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v19; // [rsp+58h] [rbp-28h]
  __int64 v20; // [rsp+68h] [rbp-18h]

  ppv = 0;
  lpsz = 0;
  v17 = 0;
  *(_OWORD *)v18 = *(_OWORD *)L"Session:%d!clsid:%s";
  v19 = *(_OWORD *)L"%d!clsid:%s";
  v20 = *(_QWORD *)L":%s";
  v3 = 0;
  *a2 = 0;
  v4 = *((_DWORD *)this + 436);
  v5 = StringFromCLSID(&CLSID_SessionDialog, &lpsz);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v8 = StringCchLengthW(lpsz, 0x27u, &v17);
    v6 = v8;
    if ( v8 >= 0 )
    {
      v9 = v17 + 30;
      v10 = 2 * (v17 + 30);
      if ( !is_mul_ok(v17 + 30, 2u) )
        v10 = -1;
      v3 = (unsigned __int16 *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
      if ( v3 )
      {
        v11 = StringCchPrintfW(v3, v9, v18, v4, lpsz);
        v6 = v11;
        if ( v11 >= 0 )
        {
          Object = CoGetObject(v3, 0, &IID_IClassFactory, &ppv);
          v6 = Object;
          if ( Object >= 0 )
          {
            v13 = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, void **))(*(_QWORD *)ppv + 24LL))(
                    ppv,
                    0,
                    &IID_ISessionDialog,
                    a2);
            v6 = v13;
            if ( v13 < 0 )
              _DbgPrintMessage(
                8,
                "ptrClassFactory->CreateInstance failed: 0x%x in %s",
                (unsigned int)v13,
                "CTSSession::GetSessionDialogObject");
          }
          else
          {
            _DbgPrintMessage(
              8,
              "CoGetObject failed: 0x%x in %s",
              (unsigned int)Object,
              "CTSSession::GetSessionDialogObject");
          }
        }
        else
        {
          _DbgPrintMessage(
            8,
            "StringCchPrintfW failed: 0x%x in %s",
            (unsigned int)v11,
            "CTSSession::GetSessionDialogObject");
        }
      }
      else
      {
        v6 = -2147024882;
      }
    }
    else
    {
      _DbgPrintMessage(8, "StringCchLength failed: 0x%x in %s", (unsigned int)v8, "CTSSession::GetSessionDialogObject");
    }
  }
  else
  {
    _DbgPrintMessage(8, "StringFromCLSID failed: 0x%x in %s", (unsigned int)v5, "CTSSession::GetSessionDialogObject");
  }
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( v3 )
    operator delete(v3, v7);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>((__int64 *)&ppv);
  return v6;
}

```

## disassembly

```asm
0x1800696b0  mov     [rsp-18h+arg_10], rbx
0x1800696b5  mov     [rsp-18h+arg_18], rsi
0x1800696ba  push    rbp
0x1800696bb  push    rdi
0x1800696bc  push    r14
0x1800696be  mov     rbp, rsp
0x1800696c1  sub     rsp, 80h
0x1800696c8  mov     rax, cs:__security_cookie
0x1800696cf  xor     rax, rsp
0x1800696d2  mov     [rbp+var_10], rax
0x1800696d6  mov     r14, rdx
0x1800696d9  mov     [rbp+ppv], 0
0x1800696e1  mov     [rbp+lpsz], 0
0x1800696e9  mov     [rbp+var_40], 0
0x1800696f1  movups  xmm0, xmmword ptr cs:aSessionDClsidS; "Session:%d!clsid:%s"
0x1800696f8  movups  xmmword ptr [rbp+var_38], xmm0
0x1800696fc  movups  xmm1, xmmword ptr cs:aSessionDClsidS+10h; "%d!clsid:%s"
0x180069703  movups  [rbp+var_28], xmm1
0x180069707  movsd   xmm0, qword ptr cs:aSessionDClsidS+20h; ":%s"
0x18006970f  movsd   [rbp+var_18], xmm0
0x180069714  xor     edi, edi
0x180069716  mov     [rdx], rdi
0x180069719  mov     esi, [rcx+6D0h]
0x18006971f  lea     rdx, [rbp+lpsz]; lplpsz
0x180069723  lea     rcx, CLSID_SessionDialog; rclsid
0x18006972a  call    cs:__imp_StringFromCLSID
0x180069730  mov     ebx, eax
0x180069732  test    eax, eax
0x180069734  jns     short loc_180069742
0x180069736  lea     rdx, aStringfromclsi; "StringFromCLSID failed: 0x%x in %s"
0x18006973d  jmp     loc_18006981A
0x180069742  lea     r8, [rbp+var_40]; unsigned __int64 *
0x180069746  mov     edx, 27h ; '''; unsigned __int64
0x18006974b  mov     rcx, [rbp+lpsz]; unsigned __int16 *
0x18006974f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180069754  mov     ebx, eax
0x180069756  test    eax, eax
0x180069758  jns     short loc_180069766
0x18006975a  lea     rdx, aStringcchlengt; "StringCchLength failed: 0x%x in %s"
0x180069761  jmp     loc_18006981A
0x180069766  mov     rbx, [rbp+var_40]
0x18006976a  add     rbx, 1Eh
0x18006976e  mov     eax, 2
0x180069773  mul     rbx
0x180069776  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006977d  cmovb   rax, rcx
0x180069781  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180069788  mov     rcx, rax; unsigned __int64
0x18006978b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180069790  mov     rdi, rax
0x180069793  test    rax, rax
0x180069796  jnz     short loc_1800697A2
0x180069798  mov     ebx, 8007000Eh
0x18006979d  jmp     loc_18006982E
0x1800697a2  mov     rax, [rbp+lpsz]
0x1800697a6  mov     [rsp+80h+var_60], rax
0x1800697ab  mov     r9d, esi
0x1800697ae  lea     r8, [rbp+var_38]; unsigned __int16 *
0x1800697b2  mov     rdx, rbx; unsigned __int64
0x1800697b5  mov     rcx, rdi; unsigned __int16 *
0x1800697b8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800697bd  mov     ebx, eax
0x1800697bf  test    eax, eax
0x1800697c1  jns     short loc_1800697CC
0x1800697c3  lea     rdx, aStringcchprint_3; "StringCchPrintfW failed: 0x%x in %s"
0x1800697ca  jmp     short loc_18006981A
0x1800697cc  lea     r9, [rbp+ppv]; ppv
0x1800697d0  lea     r8, IID_IClassFactory; riid
0x1800697d7  xor     edx, edx; pBindOptions
0x1800697d9  mov     rcx, rdi; pszName
0x1800697dc  call    cs:__imp_CoGetObject
0x1800697e2  mov     ebx, eax
0x1800697e4  test    eax, eax
0x1800697e6  jns     short loc_1800697F1
0x1800697e8  lea     rdx, aCogetobjectFai; "CoGetObject failed: 0x%x in %s"
0x1800697ef  jmp     short loc_18006981A
0x1800697f1  mov     rcx, [rbp+ppv]
0x1800697f5  mov     rax, [rcx]
0x1800697f8  mov     r9, r14
0x1800697fb  lea     r8, IID_ISessionDialog
0x180069802  xor     edx, edx
0x180069804  mov     rax, [rax+18h]
0x180069808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006980d  mov     ebx, eax
0x18006980f  test    eax, eax
0x180069811  jns     short loc_18006982E
0x180069813  lea     rdx, aPtrclassfactor; "ptrClassFactory->CreateInstance failed:"...
0x18006981a  lea     r9, aCtssessionGets_0; "CTSSession::GetSessionDialogObject"
0x180069821  mov     r8d, eax
0x180069824  mov     ecx, 8; int
0x180069829  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006982e  mov     rcx, [rbp+lpsz]; pv
0x180069832  test    rcx, rcx
0x180069835  jz      short loc_18006983D
0x180069837  call    cs:__imp_CoTaskMemFree
0x18006983d  test    rdi, rdi
0x180069840  jz      short loc_18006984B
0x180069842  mov     rcx, rdi; void *
0x180069845  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006984a  nop
0x18006984b  lea     rcx, [rbp+ppv]
0x18006984f  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180069854  mov     eax, ebx
0x180069856  mov     rcx, [rbp+var_10]
0x18006985a  xor     rcx, rsp; StackCookie
0x18006985d  call    __security_check_cookie
0x180069862  lea     r11, [rsp+80h+var_s0]
0x18006986a  mov     rbx, [r11+30h]
0x18006986e  mov     rsi, [r11+38h]
0x180069872  mov     rsp, r11
0x180069875  pop     r14
0x180069877  pop     rdi
0x180069878  pop     rbp
0x180069879  retn
```
