# CZDPTask::_BeginAsyncSearch(IUpdateSearcher *,void *,ISearchJob * *)

- ea: `0x180057108`
- end: `0x1800573d7`
- name: `?_BeginAsyncSearch@CZDPTask@@AEAAJPEAUIUpdateSearcher@@PEAXPEAPEAUISearchJob@@@Z`
- size: `719`
- prototype: `__int64 __fastcall(CZDPTask *__hidden this, struct IUpdateSearcher *, void *, struct ISearchJob **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180057f88`

## callees

- `0x180003470`
- `0x180005d99`
- `0x180007bbc`
- `0x180008b98`
- `0x180019a08`
- `0x180019a38`
- `0x180055900`
- `0x180057108`
- `0x180057ea8`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800571e9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18005724c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800571e9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18005724c`
- `OLEAUT32!__imp_SysAllocString` at `0x18005729f`
- `OLEAUT32!__imp_SysAllocString` at `0x18005729f`
- `OLEAUT32!__imp_SysFreeString` at `0x18005737d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005737d`
- `OLEAUT32!__imp_VariantInit` at `0x180057312`
- `OLEAUT32!__imp_VariantInit` at `0x180057312`
- `OLEAUT32!__imp_VariantClear` at `0x180057374`
- `OLEAUT32!__imp_VariantClear` at `0x180057374`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800571b6`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800571b6`

## string_xrefs

- `0x18005727c`: `IsInstalled = 0 AND DeploymentAction = 'Installation' AND CategoryIDs contains '%s'`
- `0x1800572b1`: `CZDPTask setting OOBE_GLOBAL_SETTING_ZDPSTATUS ZDP_Scanning.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CZDPTask::_BeginAsyncSearch(
        CZDPTask *this,
        struct IUpdateSearcher *a2,
        void *a3,
        struct ISearchJob **a4)
{
  int v7; // ebx
  HRESULT v8; // eax
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rbx
  OLECHAR *v12; // rdi
  __int64 v13; // rcx
  int v14; // eax
  LPOLESTR lpsz; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v17; // [rsp+38h] [rbp-C8h]
  __int64 v18; // [rsp+40h] [rbp-C0h]
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG v20; // [rsp+50h] [rbp-B0h] BYREF
  void *v21; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  OLECHAR psz[264]; // [rsp+90h] [rbp-70h] BYREF

  v21 = a3;
  *a4 = 0;
  CZDPTask::_OptInToSearchDriverSets(this, a2);
  v19 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  v7 = Microsoft::WRL::Details::MakeAndInitialize<COOBEWUCompletionCallback,ISearchCompletedCallback,void * &>(
         &v19,
         &v21);
  if ( v7 >= 0 )
  {
    lpsz = 0;
    v17 = 0;
    v18 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
    v17 = -1;
    v18 = -1;
    v8 = StringFromCLSID(&categoryWUZeroDayPriority, &lpsz);
    v7 = v8;
    if ( v8 < 0 )
    {
      UnattendLogW(1, L"Failed to get string for categoryWUZeroDayPriority GUID [hr=0x%08X]", (unsigned int)v8);
    }
    else
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpsz);
      v9 = 0;
      if ( v17 )
      {
        do
        {
          if ( !wcschr(L"{", lpsz[v9]) )
            break;
          ++v9;
        }
        while ( v9 < v17 );
        if ( v9 )
        {
          memmove_0(lpsz, &lpsz[v9], 2 * (v17 - v9) + 2);
          v17 -= v9;
        }
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpsz);
      v10 = v17;
      v11 = v17;
      if ( v17 )
      {
        do
        {
          if ( !wcschr(L"}", lpsz[v11 - 1]) )
            break;
          --v11;
        }
        while ( v11 );
        v10 = v17;
      }
      if ( v11 != v10 )
      {
        lpsz[v11] = 0;
        v17 = v11;
      }
      v7 = StringCchPrintfW(
             psz,
             0x104u,
             L"IsInstalled = 0 AND DeploymentAction = 'Installation' AND CategoryIDs contains '%s'",
             lpsz);
      if ( v7 >= 0 )
      {
        v12 = SysAllocString(psz);
        if ( v12 )
        {
          UnattendLogW(0, L"CZDPTask setting OOBE_GLOBAL_SETTING_ZDPSTATUS ZDP_Scanning.");
          v13 = *((_QWORD *)this + 71);
          memset(&v20, 0, sizeof(v20));
          v20.vt = 19;
          v20.lVal = 1;
          (*(void (__fastcall **)(__int64, const WCHAR *, VARIANTARG *))(*(_QWORD *)v13 + 32LL))(
            v13,
            L"ZDPSTATUS",
            &v20);
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          v20 = pvarg;
          v14 = ((__int64 (__fastcall *)(struct IUpdateSearcher *, OLECHAR *, __int64, VARIANTARG *, struct ISearchJob **))a2->lpVtbl->BeginSearch)(
                  a2,
                  v12,
                  v19,
                  &v20,
                  a4);
          v7 = v14;
          if ( v14 < 0 )
          {
            *a4 = 0;
            UnattendLogW(1, L"Failed to begin WU ZDP search [hr=0x%08X]", (unsigned int)v14);
          }
          VariantClear(&pvarg);
          SysFreeString(v12);
        }
        else
        {
          v7 = -2147024882;
        }
      }
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180057108  push    rbp
0x18005710a  push    rbx
0x18005710b  push    rsi
0x18005710c  push    rdi
0x18005710d  push    r14
0x18005710f  push    r15
0x180057111  lea     rbp, [rsp-1B8h]
0x180057119  sub     rsp, 2B8h
0x180057120  mov     rax, cs:__security_cookie
0x180057127  xor     rax, rsp
0x18005712a  mov     [rbp+1E0h+var_40], rax
0x180057131  mov     rsi, r9
0x180057134  mov     r14, rdx
0x180057137  mov     r15, rcx
0x18005713a  mov     [rsp+2E0h+var_270], r8
0x18005713f  mov     qword ptr [r9], 0
0x180057146  call    ?_OptInToSearchDriverSets@CZDPTask@@AEAAXPEAUIUpdateSearcher@@@Z; CZDPTask::_OptInToSearchDriverSets(IUpdateSearcher *)
0x18005714b  mov     [rsp+2E0h+var_298], 0
0x180057154  lea     rcx, [rsp+2E0h+var_298]
0x180057159  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005715e  lea     rdx, [rsp+2E0h+var_270]
0x180057163  lea     rcx, [rsp+2E0h+var_298]
0x180057168  call    ??$MakeAndInitialize@VCOOBEWUCompletionCallback@@UISearchCompletedCallback@@AEAPEAX@Details@WRL@Microsoft@@YAJPEAPEAUISearchCompletedCallback@@AEAPEAX@Z; Microsoft::WRL::Details::MakeAndInitialize<COOBEWUCompletionCallback,ISearchCompletedCallback,void * &>(ISearchCompletedCallback * *,void * &)
0x18005716d  mov     ebx, eax
0x18005716f  test    eax, eax
0x180057171  js      loc_1800573AC
0x180057177  mov     [rsp+2E0h+lpsz], 0
0x180057180  mov     [rsp+2E0h+var_2A8], 0
0x180057189  mov     [rsp+2E0h+var_2A0], 0
0x180057192  lea     rcx, [rsp+2E0h+lpsz]
0x180057197  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005719c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800571a0  mov     [rsp+2E0h+var_2A8], rax
0x1800571a5  mov     [rsp+2E0h+var_2A0], rax
0x1800571aa  lea     rdx, [rsp+2E0h+lpsz]; lplpsz
0x1800571af  lea     rcx, categoryWUZeroDayPriority; rclsid
0x1800571b6  call    cs:__imp_StringFromCLSID
0x1800571bc  mov     ebx, eax
0x1800571be  test    eax, eax
0x1800571c0  js      loc_18005738C
0x1800571c6  lea     rcx, [rsp+2E0h+lpsz]
0x1800571cb  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1800571d0  xor     ebx, ebx
0x1800571d2  cmp     [rsp+2E0h+var_2A8], rbx
0x1800571d7  jbe     short loc_180057224
0x1800571d9  mov     rdx, [rsp+2E0h+lpsz]
0x1800571de  movzx   edx, word ptr [rdx+rbx*2]; Ch
0x1800571e2  lea     rcx, Str; "{"
0x1800571e9  call    cs:__imp_wcschr
0x1800571ef  mov     r8, [rsp+2E0h+var_2A8]
0x1800571f4  test    rax, rax
0x1800571f7  jz      short loc_180057201
0x1800571f9  inc     rbx
0x1800571fc  cmp     rbx, r8
0x1800571ff  jb      short loc_1800571D9
0x180057201  test    rbx, rbx
0x180057204  jz      short loc_180057224
0x180057206  sub     r8, rbx
0x180057209  lea     r8, ds:2[r8*2]; Size
0x180057211  mov     rcx, [rsp+2E0h+lpsz]; void *
0x180057216  lea     rdx, [rcx+rbx*2]; Src
0x18005721a  call    memmove_0
0x18005721f  sub     [rsp+2E0h+var_2A8], rbx
0x180057224  lea     rcx, [rsp+2E0h+lpsz]
0x180057229  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18005722e  mov     rcx, [rsp+2E0h+var_2A8]
0x180057233  mov     rbx, rcx
0x180057236  test    rcx, rcx
0x180057239  jz      short loc_180057262
0x18005723b  mov     rdx, [rsp+2E0h+lpsz]
0x180057240  movzx   edx, word ptr [rdx+rbx*2-2]; Ch
0x180057245  lea     rcx, asc_1800EA9F8; "}"
0x18005724c  call    cs:__imp_wcschr
0x180057252  test    rax, rax
0x180057255  jz      short loc_18005725D
0x180057257  sub     rbx, 1
0x18005725b  jnz     short loc_18005723B
0x18005725d  mov     rcx, [rsp+2E0h+var_2A8]
0x180057262  cmp     rbx, rcx
0x180057265  jz      short loc_180057277
0x180057267  xor     ecx, ecx
0x180057269  mov     rax, [rsp+2E0h+lpsz]
0x18005726e  mov     [rax+rbx*2], cx
0x180057272  mov     [rsp+2E0h+var_2A8], rbx
0x180057277  mov     r9, [rsp+2E0h+lpsz]
0x18005727c  lea     r8, aIsinstalled0An; "IsInstalled = 0 AND DeploymentAction = "...
0x180057283  mov     edx, 104h; unsigned __int64
0x180057288  lea     rcx, [rbp+1E0h+psz]; unsigned __int16 *
0x18005728c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180057291  mov     ebx, eax
0x180057293  test    eax, eax
0x180057295  js      loc_1800573A1
0x18005729b  lea     rcx, [rbp+1E0h+psz]; psz
0x18005729f  call    cs:__imp_SysAllocString
0x1800572a5  mov     rdi, rax
0x1800572a8  test    rax, rax
0x1800572ab  jz      loc_180057385
0x1800572b1  lea     rdx, aCzdptaskSettin_0; "CZDPTask setting OOBE_GLOBAL_SETTING_ZD"...
0x1800572b8  xor     ecx, ecx
0x1800572ba  call    UnattendLogW
0x1800572bf  mov     rcx, [r15+238h]
0x1800572c6  xorps   xmm0, xmm0
0x1800572c9  xor     eax, eax
0x1800572cb  movups  [rsp+2E0h+var_290], xmm0
0x1800572d0  mov     [rsp+2E0h+var_280], rax
0x1800572d5  mov     eax, 13h
0x1800572da  mov     word ptr [rsp+2E0h+var_290], ax
0x1800572df  mov     dword ptr [rsp+2E0h+var_290+8], 1
0x1800572e7  mov     rax, [rcx]
0x1800572ea  lea     r8, [rsp+2E0h+var_290]
0x1800572ef  lea     rdx, aZdpstatus; "ZDPSTATUS"
0x1800572f6  mov     rax, [rax+20h]
0x1800572fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800572ff  xorps   xmm0, xmm0
0x180057302  xor     eax, eax
0x180057304  movups  xmmword ptr [rsp+2E0h+pvarg], xmm0
0x180057309  mov     qword ptr [rbp+1E0h+pvarg+10h], rax
0x18005730d  lea     rcx, [rsp+2E0h+pvarg]; pvarg
0x180057312  call    cs:__imp_VariantInit
0x180057318  movups  xmm0, xmmword ptr [rsp+2E0h+pvarg]
0x18005731d  movsd   xmm1, qword ptr [rbp+1E0h+pvarg+10h]
0x180057322  movaps  [rsp+2E0h+var_290], xmm0
0x180057327  movsd   [rsp+2E0h+var_280], xmm1
0x18005732d  mov     rax, [r14]
0x180057330  mov     [rsp+2E0h+var_2C0], rsi
0x180057335  lea     r9, [rsp+2E0h+var_290]
0x18005733a  mov     r8, [rsp+2E0h+var_298]
0x18005733f  mov     rdx, rdi
0x180057342  mov     rcx, r14
0x180057345  mov     rax, [rax+78h]
0x180057349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005734e  mov     ebx, eax
0x180057350  test    eax, eax
0x180057352  jns     short loc_18005736F
0x180057354  mov     qword ptr [rsi], 0
0x18005735b  mov     r8d, eax
0x18005735e  lea     rdx, aFailedToBeginW; "Failed to begin WU ZDP search [hr=0x%08"...
0x180057365  mov     ecx, 1
0x18005736a  call    UnattendLogW
0x18005736f  lea     rcx, [rsp+2E0h+pvarg]; pvarg
0x180057374  call    cs:__imp_VariantClear
0x18005737a  mov     rcx, rdi; bstrString
0x18005737d  call    cs:__imp_SysFreeString
0x180057383  jmp     short loc_1800573A1
0x180057385  mov     ebx, 8007000Eh
0x18005738a  jmp     short loc_1800573A1
0x18005738c  mov     r8d, eax
0x18005738f  lea     rdx, aFailedToGetStr; "Failed to get string for categoryWUZero"...
0x180057396  mov     ecx, 1
0x18005739b  call    UnattendLogW
0x1800573a0  nop
0x1800573a1  lea     rcx, [rsp+2E0h+lpsz]
0x1800573a6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800573ab  nop
0x1800573ac  lea     rcx, [rsp+2E0h+var_298]
0x1800573b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800573b6  mov     eax, ebx
0x1800573b8  mov     rcx, [rbp+1E0h+var_40]
0x1800573bf  xor     rcx, rsp; StackCookie
0x1800573c2  call    __security_check_cookie
0x1800573c7  add     rsp, 2B8h
0x1800573ce  pop     r15
0x1800573d0  pop     r14
0x1800573d2  pop     rdi
0x1800573d3  pop     rsi
0x1800573d4  pop     rbx
0x1800573d5  pop     rbp
0x1800573d6  retn
```
