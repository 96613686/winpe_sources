# Windows::Isolation::Implementation::Rtl::RtlpIsolatedRegistry_Direct_DeleteValue(Windows::Isolation::RegProv::Rtl::_ISOLATED_REGISTRY_PROVIDER *,Windows::Isolation::RegProv::Rtl::_PROVIDER_ISOLATED_KEY,_LUNICODE_STRING const *,_RTL_ALTERNATE_STATUS *)

- ea: `0x1800242e0`
- end: `0x18002444c`
- name: `?RtlpIsolatedRegistry_Direct_DeleteValue@Rtl@Implementation@Isolation@Windows@@YAJPEAU_ISOLATED_REGISTRY_PROVIDER@1RegProv@34@T_PROVIDER_ISOLATED_KEY@1634@PEBU_LUNICODE_STRING@@PEAU_RTL_ALTERNATE_STATUS@@@Z`
- size: `364`
- prototype: `int __high(struct Windows::Isolation::RegProv::Rtl::_ISOLATED_REGISTRY_PROVIDER *, union Windows::Isolation::RegProv::Rtl::_PROVIDER_ISOLATED_KEY, const struct _LUNICODE_STRING *, struct _RTL_ALTERNATE_STATUS *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012950`
- `0x180018b30`
- `0x1800242e0`
- `0x180056968`
- `0x1800b8b0c`
- `0x1800fe440`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800243a2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800243a2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800243d7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800243d7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024391`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800243c6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024391`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800243c6`

## string_xrefs

- `0x180024303`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\win32\isoreg_direct.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::Implementation::Rtl::RtlpIsolatedRegistry_Direct_DeleteValue(
        void *a1,
        __int64 a2,
        const struct _LUNICODE_STRING *a3,
        struct _RTL_ALTERNATE_STATUS *a4)
{
  int v6; // edi
  HKEY v7; // rbx
  __int64 v8; // rdx
  LSTATUS v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  int v12; // r9d
  void *v13; // rcx
  void *v14; // rcx
  const char *v16; // [rsp+20h] [rbp-39h] BYREF
  int v17; // [rsp+28h] [rbp-31h]
  unsigned int v18; // [rsp+30h] [rbp-29h]
  __int64 v19; // [rsp+40h] [rbp-19h] BYREF
  __int64 v20; // [rsp+48h] [rbp-11h]
  void *v21; // [rsp+50h] [rbp-9h]
  __int64 v22; // [rsp+58h] [rbp-1h]
  __int64 v23; // [rsp+60h] [rbp+7h]
  void *lpMem; // [rsp+68h] [rbp+Fh]
  __int64 v25; // [rsp+70h] [rbp+17h]
  int v26; // [rsp+78h] [rbp+1Fh]

  v18 = -1073741595;
  v16 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isoreg_direct.cpp";
  if ( a1 == &Windows::Isolation::Implementation::Rtl::RtlpDirectIsolatedRegistry )
  {
    v20 = 0;
    v19 = 0;
    v21 = 0;
    v23 = 0;
    v22 = 0;
    lpMem = 0;
    v25 = 0;
    v26 = 0;
    v6 = Windows::Isolation::Implementation::Rtl::CWin32FullPath::Initialize(
           (Windows::Isolation::Implementation::Rtl::CWin32FullPath *)&v19,
           a3);
    if ( v6 >= 0 )
    {
      v7 = *(HKEY *)(a2 + 64);
      if ( v26 == 1 )
      {
        v8 = v25;
        if ( !v25 )
        {
          RaiseException(0xC00000E5, 1u, 0, 0);
          v8 = v25;
        }
        v9 = RegDeleteValueA(v7, *(LPCSTR *)(v8 + 16));
      }
      else
      {
        if ( v26 != 2 || (v10 = v25) == 0 )
        {
          RaiseException(0xC00000E5, 1u, 0, 0);
          v10 = v25;
        }
        v9 = RegDeleteValueW(v7, *(LPCWSTR *)(v10 + 16));
      }
      if ( v9 && (v11 = isowin32private_Win32ErrorAltStatusHelper(v9, a4), v6 = v11, v11 < 0) )
        Windows::ErrorHandling::COM::ReportNtErrorOrigination(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isoreg_direct.cpp",
          (const char *)0x2C6,
          v11,
          v12);
      else
        v6 = 0;
    }
    v13 = lpMem;
    if ( lpMem )
    {
      v23 = 0;
      v22 = 0;
      lpMem = 0;
      IsolationFreeStringRoutine(v13);
    }
    v14 = v21;
    if ( v21 )
    {
      v21 = 0;
      v19 = 0;
      v20 = 0;
      IsolationFreeStringRoutine(v14);
    }
  }
  else
  {
    v17 = 699;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v16,
      &v16);
    return v18;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800242e0  push    rbp
0x1800242e2  push    rbx
0x1800242e3  push    rsi
0x1800242e4  push    rdi
0x1800242e5  push    r14
0x1800242e7  push    r15
0x1800242e9  lea     rbp, [rsp-2Fh]
0x1800242ee  sub     rsp, 88h
0x1800242f5  lea     rax, ?RtlpDirectIsolatedRegistry@Rtl@Implementation@Isolation@Windows@@3U_ISOLATED_REGISTRY_PROVIDER@1RegProv@34@B; Windows::Isolation::RegProv::Rtl::_ISOLATED_REGISTRY_PROVIDER const Windows::Isolation::Implementation::Rtl::RtlpDirectIsolatedRegistry
0x1800242fc  mov     [rbp+57h+var_80], 0C00000E5h
0x180024303  lea     r15, aOnecoreComNetf_92; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18002430a  mov     rsi, r9
0x18002430d  mov     [rbp+57h+var_90], r15
0x180024311  mov     rbx, rdx
0x180024314  cmp     rcx, rax
0x180024317  jz      short loc_180024335
0x180024319  mov     [rbp+57h+var_88], 2BBh
0x180024320  lea     rdx, [rbp+57h+var_90]
0x180024324  lea     rcx, [rbp+57h+var_90]
0x180024328  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18002432d  mov     edi, [rbp+57h+var_80]
0x180024330  jmp     loc_18002443A
0x180024335  xor     r14d, r14d
0x180024338  lea     rcx, [rbp+57h+var_70]; this
0x18002433c  mov     rdx, r8; struct _LUNICODE_STRING *
0x18002433f  mov     [rbp+57h+var_68], r14
0x180024343  mov     [rbp+57h+var_70], r14
0x180024347  mov     [rbp+57h+var_60], r14
0x18002434b  mov     [rbp+57h+var_50], r14
0x18002434f  mov     [rbp+57h+var_58], r14
0x180024353  mov     [rbp+57h+lpMem], r14
0x180024357  mov     [rbp+57h+var_40], r14
0x18002435b  mov     [rbp+57h+var_38], r14d
0x18002435f  call    ?Initialize@CWin32FullPath@Rtl@Implementation@Isolation@Windows@@QEAAJAEBU_LUNICODE_STRING@@@Z; Windows::Isolation::Implementation::Rtl::CWin32FullPath::Initialize(_LUNICODE_STRING const &)
0x180024364  mov     edi, eax
0x180024366  test    eax, eax
0x180024368  js      loc_180024406
0x18002436e  mov     rbx, [rbx+40h]
0x180024372  lea     eax, [r14+1]
0x180024376  cmp     [rbp+57h+var_38], eax
0x180024379  jnz     short loc_1800243AA
0x18002437b  mov     rdx, [rbp+57h+var_40]
0x18002437f  test    rdx, rdx
0x180024382  jnz     short loc_18002439B
0x180024384  xor     r9d, r9d; lpArguments
0x180024387  xor     r8d, r8d; nNumberOfArguments
0x18002438a  mov     edx, eax; dwExceptionFlags
0x18002438c  mov     ecx, 0C00000E5h; dwExceptionCode
0x180024391  call    cs:__imp_RaiseException
0x180024397  mov     rdx, [rbp+57h+var_40]
0x18002439b  mov     rdx, [rdx+10h]; lpValueName
0x18002439f  mov     rcx, rbx; hKey
0x1800243a2  call    cs:__imp_RegDeleteValueA
0x1800243a8  jmp     short loc_1800243DD
0x1800243aa  cmp     [rbp+57h+var_38], 2
0x1800243ae  jnz     short loc_1800243B9
0x1800243b0  mov     rdx, [rbp+57h+var_40]
0x1800243b4  test    rdx, rdx
0x1800243b7  jnz     short loc_1800243D0
0x1800243b9  xor     r9d, r9d; lpArguments
0x1800243bc  xor     r8d, r8d; nNumberOfArguments
0x1800243bf  mov     edx, eax; dwExceptionFlags
0x1800243c1  mov     ecx, 0C00000E5h; dwExceptionCode
0x1800243c6  call    cs:__imp_RaiseException
0x1800243cc  mov     rdx, [rbp+57h+var_40]
0x1800243d0  mov     rdx, [rdx+10h]; lpValueName
0x1800243d4  mov     rcx, rbx; hKey
0x1800243d7  call    cs:__imp_RegDeleteValueW
0x1800243dd  test    eax, eax
0x1800243df  jz      short loc_180024403
0x1800243e1  mov     rdx, rsi; struct _RTL_ALTERNATE_STATUS *
0x1800243e4  mov     ecx, eax; unsigned int
0x1800243e6  call    ?isowin32private_Win32ErrorAltStatusHelper@@YAJKPEAU_RTL_ALTERNATE_STATUS@@@Z; isowin32private_Win32ErrorAltStatusHelper(ulong,_RTL_ALTERNATE_STATUS *)
0x1800243eb  mov     edi, eax
0x1800243ed  test    eax, eax
0x1800243ef  jns     short loc_180024403
0x1800243f1  mov     r8d, eax; int
0x1800243f4  mov     edx, 2C6h; char *
0x1800243f9  mov     rcx, r15; this
0x1800243fc  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x180024401  jmp     short loc_180024406
0x180024403  mov     edi, r14d
0x180024406  mov     rcx, [rbp+57h+lpMem]; lpMem
0x18002440a  test    rcx, rcx
0x18002440d  jz      short loc_180024420
0x18002440f  mov     [rbp+57h+var_50], r14
0x180024413  mov     [rbp+57h+var_58], r14
0x180024417  mov     [rbp+57h+lpMem], r14
0x18002441b  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180024420  mov     rcx, [rbp+57h+var_60]; lpMem
0x180024424  test    rcx, rcx
0x180024427  jz      short loc_18002443A
0x180024429  mov     [rbp+57h+var_60], r14
0x18002442d  mov     [rbp+57h+var_70], r14
0x180024431  mov     [rbp+57h+var_68], r14
0x180024435  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x18002443a  mov     eax, edi
0x18002443c  add     rsp, 88h
0x180024443  pop     r15
0x180024445  pop     r14
0x180024447  pop     rdi
0x180024448  pop     rsi
0x180024449  pop     rbx
0x18002444a  pop     rbp
0x18002444b  retn
```
