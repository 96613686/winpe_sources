# CMultilingualSpeller::CalculateUserMultilingualLanguages(void)

- ea: `0x1802773c0`
- end: `0x18027768c`
- name: `?CalculateUserMultilingualLanguages@CMultilingualSpeller@@QEAAJXZ`
- size: `716`
- prototype: `__int64 __fastcall(CMultilingualSpeller *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180277fb4`

## callees

- `0x18006ad18`
- `0x1800facf0`
- `0x180111748`
- `0x180114790`
- `0x18013ce80`
- `0x18013d268`
- `0x18013dcda`
- `0x180277398`
- `0x1802773c0`
- `0x180277718`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18027761b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18027761b`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x18027752d`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x18027752d`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180277548`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180277548`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180277435`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180277435`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180277513`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180277513`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802774de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180277649`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802774de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180277649`

## pseudocode

```c
__int64 __fastcall CMultilingualSpeller::CalculateUserMultilingualLanguages(CMultilingualSpeller *this)
{
  CMultilingualSpeller *v1; // rsi
  __int64 v2; // rbx
  int ActivationFactory; // ebx
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64 *); // rbx
  int v6; // eax
  HSTRING v7; // rcx
  unsigned int v8; // r15d
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  LCID v12; // eax
  int v13; // r14d
  CSpellCheckScripts *v14; // r13
  __int64 v15; // rdi
  __int64 v16; // rcx
  unsigned int v17; // esi
  int v18; // eax
  unsigned int v19; // edx
  unsigned int v20; // eax
  CSpellerGlobalState *v21; // rcx
  signed int LastError; // eax
  unsigned int v24; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING string; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v28; // [rsp+40h] [rbp-C0h] BYREF
  CMultilingualSpeller *v29; // [rsp+48h] [rbp-B8h]
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h]
  WCHAR LocaleName[88]; // [rsp+70h] [rbp-90h] BYREF

  v29 = this;
  v1 = this;
  v27 = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.UserProfile.GlobalizationPreferences",
    0x34u,
    0x33u);
  v2 = v31;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  ActivationFactory = RoGetActivationFactory(v2, &GUID_01bf4326_ed37_4e96_b0e9_c1340d1ea158, &v27);
  if ( ActivationFactory >= 0 )
  {
    v4 = v27;
    v26 = 0;
    v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 72LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    ActivationFactory = v5(v4, &v26);
    if ( ActivationFactory >= 0 )
    {
      v24 = 0;
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v26 + 56LL))(v26, &v24);
      if ( ActivationFactory >= 0 )
      {
        v6 = v24;
        if ( v24 > 4 )
        {
          v6 = 4;
          v24 = 4;
        }
        v7 = 0;
        v8 = 0;
        string = 0;
        if ( v6 )
        {
          do
          {
            if ( ActivationFactory < 0 )
              break;
            v9 = v26;
            v10 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v26 + 48LL);
            WindowsDeleteString(v7);
            string = 0;
            ActivationFactory = v10(v9, v8, &string);
            if ( ActivationFactory >= 0 )
            {
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              if ( !ResolveLocaleName(StringRawBuffer, LocaleName, 85)
                || (v12 = LocaleNameToLCID(LocaleName, 0), (v13 = v12) == 0) )
              {
                LastError = GetLastError();
                ActivationFactory = LastError;
                if ( LastError > 0 )
                  ActivationFactory = (unsigned __int16)LastError | 0x80070000;
                goto LABEL_22;
              }
              v28 = 0;
              ActivationFactory = CMultilingualSpeller::GetScript(v12, &v28, LocaleName);
              if ( ActivationFactory >= 0 )
              {
                v14 = (CSpellCheckScripts *)operator new(0x10u);
                *((_QWORD *)v14 + 1) = v28;
                *(_DWORD *)v14 = v13;
                v15 = *(_QWORD *)v1;
                v16 = *(_QWORD *)v1;
                v17 = *(_DWORD *)(*(_QWORD *)v1 + 4LL);
                v18 = CSpellArray<CSpellCheckScripts *>::EnsureSize(v16, v17 + 1);
                ActivationFactory = v18;
                if ( !v18 )
                {
                  v20 = *(_DWORD *)(v15 + 4);
                  if ( v17 < v20 )
                    memmove_0(
                      (void *)(*(_QWORD *)(v15 + 16) + (v17 + 1) * *(_DWORD *)(v15 + 8)),
                      (const void *)(*(_QWORD *)(v15 + 16) + v17 * *(_DWORD *)(v15 + 8)),
                      *(_DWORD *)(v15 + 8) * (v20 - v17));
                  *(_QWORD *)(*(_DWORD *)(v15 + 8) * v17 + *(_QWORD *)(v15 + 16)) = v14;
                  ++*(_DWORD *)(v15 + 4);
LABEL_16:
                  v1 = v29;
                  v21 = (CSpellerGlobalState *)*((_QWORD *)v29 + 1);
                  if ( v21 )
                    ActivationFactory = CSpellerGlobalState::AddNewInputMethod(v21, v13, &string);
                  goto LABEL_22;
                }
                if ( v18 >= 0 )
                  goto LABEL_16;
                CSpellCheckScripts::`scalar deleting destructor'(v14, v19);
                v1 = v29;
              }
            }
LABEL_22:
            v7 = string;
            ++v8;
          }
          while ( v8 < v24 );
        }
        WindowsDeleteString(v7);
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1802773c0  push    rbp
0x1802773c2  push    rbx
0x1802773c3  push    rsi
0x1802773c4  push    rdi
0x1802773c5  push    r12
0x1802773c7  push    r13
0x1802773c9  push    r14
0x1802773cb  push    r15
0x1802773cd  lea     rbp, [rsp-38h]
0x1802773d2  sub     rsp, 138h
0x1802773d9  mov     rax, cs:__security_cookie
0x1802773e0  xor     rax, rsp
0x1802773e3  mov     [rbp+70h+var_50], rax
0x1802773e7  xor     r12d, r12d
0x1802773ea  mov     [rsp+170h+var_128], rcx
0x1802773ef  mov     rsi, rcx
0x1802773f2  mov     [rsp+170h+var_138], r12
0x1802773f7  lea     rdx, ?RuntimeClass_Windows_System_UserProfile_GlobalizationPreferences@@3QBGB; "Windows.System.UserProfile.Globalizatio"...
0x1802773fe  mov     [rsp+170h+var_108], r12
0x180277403  lea     rcx, [rsp+170h+hstringHeader]; hstringHeader
0x180277408  lea     r9d, [r12+33h]; unsigned int
0x18027740d  lea     r8d, [r12+34h]; unsigned int
0x180277412  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180277417  mov     rbx, [rsp+170h+var_108]
0x18027741c  lea     rcx, [rsp+170h+var_138]
0x180277421  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180277426  lea     r8, [rsp+170h+var_138]
0x18027742b  mov     rcx, rbx
0x18027742e  lea     rdx, _GUID_01bf4326_ed37_4e96_b0e9_c1340d1ea158
0x180277435  call    cs:__imp_RoGetActivationFactory
0x18027743c  nop     dword ptr [rax+rax+00h]
0x180277441  mov     ebx, eax
0x180277443  test    eax, eax
0x180277445  js      loc_18027765F
0x18027744b  mov     rdi, [rsp+170h+var_138]
0x180277450  lea     rcx, [rsp+170h+var_140]
0x180277455  mov     [rsp+170h+var_140], r12
0x18027745a  mov     rax, [rdi]
0x18027745d  mov     rbx, [rax+48h]
0x180277461  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180277466  lea     rdx, [rsp+170h+var_140]
0x18027746b  mov     rcx, rdi
0x18027746e  mov     rax, rbx
0x180277471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180277476  mov     ebx, eax
0x180277478  test    eax, eax
0x18027747a  js      loc_180277655
0x180277480  mov     rcx, [rsp+170h+var_140]
0x180277485  lea     rdx, [rsp+170h+var_150]
0x18027748a  mov     [rsp+170h+var_150], r12d
0x18027748f  mov     rax, [rcx]
0x180277492  mov     rax, [rax+38h]
0x180277496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027749b  mov     ebx, eax
0x18027749d  test    eax, eax
0x18027749f  js      loc_180277655
0x1802774a5  mov     eax, [rsp+170h+var_150]
0x1802774a9  cmp     eax, 4
0x1802774ac  jbe     short loc_1802774B7
0x1802774ae  lea     eax, [r12+4]
0x1802774b3  mov     [rsp+170h+var_150], eax
0x1802774b7  mov     rcx, r12; string
0x1802774ba  mov     r15d, r12d
0x1802774bd  mov     [rsp+170h+string], rcx
0x1802774c2  test    eax, eax
0x1802774c4  jz      loc_180277649
0x1802774ca  test    ebx, ebx
0x1802774cc  js      loc_180277649
0x1802774d2  mov     rdi, [rsp+170h+var_140]
0x1802774d7  mov     rax, [rdi]
0x1802774da  mov     rbx, [rax+30h]
0x1802774de  call    cs:__imp_WindowsDeleteString
0x1802774e5  nop     dword ptr [rax+rax+00h]
0x1802774ea  lea     r8, [rsp+170h+string]
0x1802774ef  mov     [rsp+170h+string], r12
0x1802774f4  mov     edx, r15d
0x1802774f7  mov     rcx, rdi
0x1802774fa  mov     rax, rbx
0x1802774fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180277502  mov     ebx, eax
0x180277504  test    eax, eax
0x180277506  js      loc_180277636
0x18027750c  mov     rcx, [rsp+170h+string]; string
0x180277511  xor     edx, edx; length
0x180277513  call    cs:__imp_WindowsGetStringRawBuffer
0x18027751a  nop     dword ptr [rax+rax+00h]
0x18027751f  mov     r8d, 55h ; 'U'; cchLocaleName
0x180277525  lea     rdx, [rsp+170h+LocaleName]; lpLocaleName
0x18027752a  mov     rcx, rax; lpNameToResolve
0x18027752d  call    cs:__imp_ResolveLocaleName
0x180277534  nop     dword ptr [rax+rax+00h]
0x180277539  test    eax, eax
0x18027753b  jz      loc_18027761B
0x180277541  xor     edx, edx; dwFlags
0x180277543  lea     rcx, [rsp+170h+LocaleName]; lpName
0x180277548  call    cs:__imp_LocaleNameToLCID
0x18027754f  nop     dword ptr [rax+rax+00h]
0x180277554  mov     r14d, eax
0x180277557  test    eax, eax
0x180277559  jz      loc_18027761B
0x18027755f  lea     r8, [rsp+170h+LocaleName]; unsigned __int16 *
0x180277564  mov     [rsp+170h+var_130], r12
0x180277569  lea     rdx, [rsp+170h+var_130]; unsigned __int16 **
0x18027756e  mov     ecx, eax; unsigned int
0x180277570  call    ?GetScript@CMultilingualSpeller@@SAJKPEAPEAGPEAG@Z; CMultilingualSpeller::GetScript(ulong,ushort * *,ushort *)
0x180277575  mov     ebx, eax
0x180277577  test    eax, eax
0x180277579  js      loc_180277636
0x18027757f  mov     ecx, 10h; Size
0x180277584  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180277589  mov     rcx, [rsp+170h+var_130]
0x18027758e  mov     r13, rax
0x180277591  mov     [rax+8], rcx
0x180277595  mov     [rax], r14d
0x180277598  mov     rdi, [rsi]
0x18027759b  mov     rcx, rdi
0x18027759e  mov     esi, [rdi+4]
0x1802775a1  lea     edx, [rsi+1]
0x1802775a4  call    ?EnsureSize@?$CSpellArray@PEAVCSpellCheckScripts@@@@AEAAJJ@Z; CSpellArray<CSpellCheckScripts *>::EnsureSize(long)
0x1802775a9  mov     ebx, eax
0x1802775ab  test    eax, eax
0x1802775ad  jnz     short loc_18027760A
0x1802775af  mov     eax, [rdi+4]
0x1802775b2  cmp     esi, eax
0x1802775b4  jnb     short loc_1802775D9
0x1802775b6  mov     ecx, [rdi+8]
0x1802775b9  sub     eax, esi
0x1802775bb  imul    eax, ecx
0x1802775be  mov     edx, ecx
0x1802775c0  imul    edx, esi
0x1802775c3  mov     r8d, eax; Size
0x1802775c6  lea     eax, [rsi+1]
0x1802775c9  add     rdx, [rdi+10h]; Src
0x1802775cd  imul    ecx, eax
0x1802775d0  add     rcx, [rdi+10h]; void *
0x1802775d4  call    memmove_0
0x1802775d9  imul    esi, [rdi+8]
0x1802775dd  mov     rax, [rdi+10h]
0x1802775e1  mov     [rsi+rax], r13
0x1802775e5  inc     dword ptr [rdi+4]
0x1802775e8  xor     r12d, r12d
0x1802775eb  mov     rsi, [rsp+170h+var_128]
0x1802775f0  mov     rcx, [rsi+8]; this
0x1802775f4  test    rcx, rcx
0x1802775f7  jz      short loc_180277636
0x1802775f9  lea     r8, [rsp+170h+string]; struct Microsoft::WRL::Wrappers::HString *
0x1802775fe  mov     edx, r14d; unsigned int
0x180277601  call    ?AddNewInputMethod@CSpellerGlobalState@@QEAAJKPEAVHString@Wrappers@WRL@Microsoft@@@Z; CSpellerGlobalState::AddNewInputMethod(ulong,Microsoft::WRL::Wrappers::HString *)
0x180277606  mov     ebx, eax
0x180277608  jmp     short loc_180277636
0x18027760a  jns     short loc_1802775EB
0x18027760c  mov     rcx, r13; this
0x18027760f  call    ??_GCSpellCheckScripts@@QEAAPEAXI@Z; CSpellCheckScripts::`scalar deleting destructor'(uint)
0x180277614  mov     rsi, [rsp+170h+var_128]
0x180277619  jmp     short loc_180277636
0x18027761b  call    cs:__imp_GetLastError
0x180277622  nop     dword ptr [rax+rax+00h]
0x180277627  mov     ebx, eax
0x180277629  test    eax, eax
0x18027762b  jle     short loc_180277636
0x18027762d  movzx   ebx, ax
0x180277630  or      ebx, 80070000h
0x180277636  mov     rcx, [rsp+170h+string]; string
0x18027763b  inc     r15d
0x18027763e  cmp     r15d, [rsp+170h+var_150]
0x180277643  jb      loc_1802774CA
0x180277649  call    cs:__imp_WindowsDeleteString
0x180277650  nop     dword ptr [rax+rax+00h]
0x180277655  lea     rcx, [rsp+170h+var_140]
0x18027765a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027765f  lea     rcx, [rsp+170h+var_138]
0x180277664  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180277669  mov     eax, ebx
0x18027766b  mov     rcx, [rbp+70h+var_50]
0x18027766f  xor     rcx, rsp; StackCookie
0x180277672  call    __security_check_cookie
0x180277677  add     rsp, 138h
0x18027767e  pop     r15
0x180277680  pop     r14
0x180277682  pop     r13
0x180277684  pop     r12
0x180277686  pop     rdi
0x180277687  pop     rsi
0x180277688  pop     rbx
0x180277689  pop     rbp
0x18027768a  retn
```
