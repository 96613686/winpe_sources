# CTSSession::GetSessionDialogObject(void * *)

- ea: `0x18006d490`
- end: `0x18006d66d`
- name: `?GetSessionDialogObject@CTSSession@@AEAAJPEAPEAX@Z`
- size: `477`
- prototype: `__int64 __fastcall(CTSSession *__hidden this, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180072360`

## callees

- `0x1800077a0`
- `0x18000c17c`
- `0x18000c684`
- `0x180028bd8`
- `0x18004e850`
- `0x18004ec20`
- `0x18004ec80`
- `0x18006d490`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006d623`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006d623`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18006d50a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18006d50a`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x18006d5c2`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x18006d5c2`

## string_xrefs

- `0x18006d4d1`: `Session:%d!clsid:%s`
- `0x18006d51c`: `StringFromCLSID failed: 0x%x in %s`
- `0x18006d5ff`: `ptrClassFactory->CreateInstance failed: 0x%x in %s`

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
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&ppv);
  return v6;
}

```

## disassembly

```asm
0x18006d490  mov     [rsp-18h+arg_10], rbx
0x18006d495  mov     [rsp-18h+arg_18], rsi
0x18006d49a  push    rbp
0x18006d49b  push    rdi
0x18006d49c  push    r14
0x18006d49e  mov     rbp, rsp
0x18006d4a1  sub     rsp, 80h
0x18006d4a8  mov     rax, cs:__security_cookie
0x18006d4af  xor     rax, rsp
0x18006d4b2  mov     [rbp+var_10], rax
0x18006d4b6  mov     r14, rdx
0x18006d4b9  mov     [rbp+ppv], 0
0x18006d4c1  mov     [rbp+lpsz], 0
0x18006d4c9  mov     [rbp+var_40], 0
0x18006d4d1  movups  xmm0, xmmword ptr cs:aSessionDClsidS; "Session:%d!clsid:%s"
0x18006d4d8  movups  xmmword ptr [rbp+var_38], xmm0
0x18006d4dc  movups  xmm1, xmmword ptr cs:aSessionDClsidS+10h; "%d!clsid:%s"
0x18006d4e3  movups  [rbp+var_28], xmm1
0x18006d4e7  movsd   xmm0, qword ptr cs:aSessionDClsidS+20h; ":%s"
0x18006d4ef  movsd   [rbp+var_18], xmm0
0x18006d4f4  xor     edi, edi
0x18006d4f6  mov     [rdx], rdi
0x18006d4f9  mov     esi, [rcx+6D0h]
0x18006d4ff  lea     rdx, [rbp+lpsz]; lplpsz
0x18006d503  lea     rcx, CLSID_SessionDialog; rclsid
0x18006d50a  call    cs:__imp_StringFromCLSID
0x18006d511  nop     dword ptr [rax+rax+00h]
0x18006d516  mov     ebx, eax
0x18006d518  test    eax, eax
0x18006d51a  jns     short loc_18006D528
0x18006d51c  lea     rdx, aStringfromclsi; "StringFromCLSID failed: 0x%x in %s"
0x18006d523  jmp     loc_18006D606
0x18006d528  lea     r8, [rbp+var_40]; unsigned __int64 *
0x18006d52c  mov     edx, 27h ; '''; unsigned __int64
0x18006d531  mov     rcx, [rbp+lpsz]; unsigned __int16 *
0x18006d535  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006d53a  mov     ebx, eax
0x18006d53c  test    eax, eax
0x18006d53e  jns     short loc_18006D54C
0x18006d540  lea     rdx, aStringcchlengt; "StringCchLength failed: 0x%x in %s"
0x18006d547  jmp     loc_18006D606
0x18006d54c  mov     rbx, [rbp+var_40]
0x18006d550  add     rbx, 1Eh
0x18006d554  mov     eax, 2
0x18006d559  mul     rbx
0x18006d55c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006d563  cmovb   rax, rcx
0x18006d567  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006d56e  mov     rcx, rax; unsigned __int64
0x18006d571  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006d576  mov     rdi, rax
0x18006d579  test    rax, rax
0x18006d57c  jnz     short loc_18006D588
0x18006d57e  mov     ebx, 8007000Eh
0x18006d583  jmp     loc_18006D61A
0x18006d588  mov     rax, [rbp+lpsz]
0x18006d58c  mov     [rsp+80h+var_60], rax
0x18006d591  mov     r9d, esi
0x18006d594  lea     r8, [rbp+var_38]; unsigned __int16 *
0x18006d598  mov     rdx, rbx; unsigned __int64
0x18006d59b  mov     rcx, rdi; unsigned __int16 *
0x18006d59e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006d5a3  mov     ebx, eax
0x18006d5a5  test    eax, eax
0x18006d5a7  jns     short loc_18006D5B2
0x18006d5a9  lea     rdx, aStringcchprint_3; "StringCchPrintfW failed: 0x%x in %s"
0x18006d5b0  jmp     short loc_18006D606
0x18006d5b2  lea     r9, [rbp+ppv]; ppv
0x18006d5b6  lea     r8, IID_IClassFactory; riid
0x18006d5bd  xor     edx, edx; pBindOptions
0x18006d5bf  mov     rcx, rdi; pszName
0x18006d5c2  call    cs:__imp_CoGetObject
0x18006d5c9  nop     dword ptr [rax+rax+00h]
0x18006d5ce  mov     ebx, eax
0x18006d5d0  test    eax, eax
0x18006d5d2  jns     short loc_18006D5DD
0x18006d5d4  lea     rdx, aCogetobjectFai; "CoGetObject failed: 0x%x in %s"
0x18006d5db  jmp     short loc_18006D606
0x18006d5dd  mov     rcx, [rbp+ppv]
0x18006d5e1  mov     rax, [rcx]
0x18006d5e4  mov     r9, r14
0x18006d5e7  lea     r8, IID_ISessionDialog
0x18006d5ee  xor     edx, edx
0x18006d5f0  mov     rax, [rax+18h]
0x18006d5f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d5f9  mov     ebx, eax
0x18006d5fb  test    eax, eax
0x18006d5fd  jns     short loc_18006D61A
0x18006d5ff  lea     rdx, aPtrclassfactor; "ptrClassFactory->CreateInstance failed:"...
0x18006d606  lea     r9, aCtssessionGets_0; "CTSSession::GetSessionDialogObject"
0x18006d60d  mov     r8d, eax
0x18006d610  mov     ecx, 8; int
0x18006d615  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006d61a  mov     rcx, [rbp+lpsz]; pv
0x18006d61e  test    rcx, rcx
0x18006d621  jz      short loc_18006D62F
0x18006d623  call    cs:__imp_CoTaskMemFree
0x18006d62a  nop     dword ptr [rax+rax+00h]
0x18006d62f  test    rdi, rdi
0x18006d632  jz      short loc_18006D63D
0x18006d634  mov     rcx, rdi; void *
0x18006d637  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006d63c  nop
0x18006d63d  lea     rcx, [rbp+ppv]
0x18006d641  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18006d646  mov     eax, ebx
0x18006d648  mov     rcx, [rbp+var_10]
0x18006d64c  xor     rcx, rsp; StackCookie
0x18006d64f  call    __security_check_cookie
0x18006d654  lea     r11, [rsp+80h+var_s0]
0x18006d65c  mov     rbx, [r11+30h]
0x18006d660  mov     rsi, [r11+38h]
0x18006d664  mov     rsp, r11
0x18006d667  pop     r14
0x18006d669  pop     rdi
0x18006d66a  pop     rbp
0x18006d66b  retn
```
