# GetPackagedAppContext(_CONSENTUI_PARAM_PACKAGED_APP *,uchar *,_CREDUI_CONTEXT *)

- ea: `0x14000eee4`
- end: `0x14000f1fa`
- name: `?GetPackagedAppContext@@YAXPEAU_CONSENTUI_PARAM_PACKAGED_APP@@PEAEPEAU_CREDUI_CONTEXT@@@Z`
- size: `790`
- prototype: `void __fastcall(struct _CONSENTUI_PARAM_PACKAGED_APP *, unsigned __int8 *, LPWSTR *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003040`

## callees

- `0x14000a7b0`
- `0x14000e5e4`
- `0x14000eee4`
- `0x14000f200`
- `0x14000fbec`
- `0x140019038`
- `0x140019634`
- `0x14001f010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14000ef32`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14000ef32`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14000f154`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14000f154`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000efe4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000f030`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000f0ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000efe4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000f030`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000f0ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000f009`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000f055`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000f009`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000f055`
- `SHLWAPI!SHStrDupW` at `0x14000f016`
- `SHLWAPI!SHStrDupW` at `0x14000f062`
- `SHLWAPI!SHStrDupW` at `0x14000f1ce`
- `SHLWAPI!SHStrDupW` at `0x14000f016`
- `SHLWAPI!SHStrDupW` at `0x14000f062`
- `SHLWAPI!SHStrDupW` at `0x14000f1ce`
- `SHLWAPI!PathRemoveBlanksW` at `0x14000f1d8`
- `SHLWAPI!PathRemoveBlanksW` at `0x14000f1d8`

## pseudocode

```c
void __fastcall GetPackagedAppContext(struct _CONSENTUI_PARAM_PACKAGED_APP *a1, unsigned __int8 *a2, LPWSTR *a3)
{
  __int64 v6; // r12
  int PackagedAppPackage; // eax
  int v8; // r8d
  int PackagedResourceResolvers; // edi
  HSTRING v10; // rcx
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rdi
  const WCHAR *StringRawBuffer; // rax
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rdi
  const WCHAR *v16; // rax
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  struct Windows::Internal::StateRepository::IPackage *v20; // rcx
  struct Windows::Internal::StateRepository::IApplication *v21; // rcx
  __int64 v22; // [rsp+30h] [rbp-18h] BYREF
  __int64 v23; // [rsp+38h] [rbp-10h] BYREF
  struct Windows::Internal::StateRepository::IPackage *v24; // [rsp+90h] [rbp+48h] BYREF
  HSTRING string; // [rsp+98h] [rbp+50h] BYREF
  struct Windows::Internal::StateRepository::IPackage *v26; // [rsp+A0h] [rbp+58h] BYREF
  struct Windows::Internal::StateRepository::IApplication *v27; // [rsp+A8h] [rbp+60h] BYREF

  v6 = *((_QWORD *)a1 + 25);
  if ( !v6 )
    v6 = *((_QWORD *)a1 + 26);
  *(_DWORD *)a3 = 1;
  *a2 = 0;
  if ( *((_QWORD *)a1 + 28) && ImpersonateLoggedOnUser(*((HANDLE *)a1 + 3)) )
  {
    v27 = 0;
    v26 = 0;
    PackagedAppPackage = GetPackagedAppPackage(*((PCWSTR *)a1 + 28), &v27, &v26);
    LOBYTE(PackagedResourceResolvers) = PackagedAppPackage;
    v23 = 0;
    v22 = 0;
    if ( PackagedAppPackage < 0 )
      goto LABEL_32;
    v24 = v26;
    if ( v26 )
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *))(*(_QWORD *)v26 + 8LL))(v26);
    string = (HSTRING)v27;
    if ( v27 )
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IApplication *))(*(_QWORD *)v27 + 8LL))(v27);
    PackagedResourceResolvers = GetPackagedResourceResolvers(&string, &v24, &v23, &v22);
    if ( PackagedResourceResolvers < 0 || !v26 )
    {
LABEL_32:
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_SD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, v8, *((_QWORD *)a1 + 28), PackagedResourceResolvers);
      goto LABEL_34;
    }
    v10 = 0;
    string = 0;
    v11 = v22;
    if ( v22 )
    {
      v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22 + 56LL);
      WindowsDeleteString(0);
      string = 0;
      PackagedResourceResolvers = v12(v11, &string);
      if ( PackagedResourceResolvers < 0 )
        goto LABEL_16;
      v10 = string;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(v10, 0);
    SHStrDupW(StringRawBuffer, a3 + 3);
LABEL_16:
    v14 = v23;
    if ( v23 )
    {
      v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 48LL);
      WindowsDeleteString(string);
      string = 0;
      PackagedResourceResolvers = v15(v14, &string);
    }
    if ( PackagedResourceResolvers >= 0 )
    {
      v16 = WindowsGetStringRawBuffer(string, 0);
      SHStrDupW(v16, a3 + 2);
    }
    LODWORD(v24) = 0;
    v17 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *, struct Windows::Internal::StateRepository::IPackage **))(*(_QWORD *)v26 + 1000LL))(
            v26,
            &v24);
    *(_DWORD *)a3 = 1;
    if ( v17 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_D(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          24,
          WPP_bed9811735e730a365d52877ff824444_Traceguids,
          (unsigned int)v17);
      goto LABEL_30;
    }
    if ( (_DWORD)v24 == 3 )
    {
      *(_DWORD *)a3 = 3;
    }
    else
    {
      if ( (((_DWORD)v24 - 1) & 0xFFFFFFFC) != 0 || (_DWORD)v24 == 3 )
        goto LABEL_30;
      *(_DWORD *)a3 = 2;
    }
    *a2 = 1;
LABEL_30:
    WindowsDeleteString(string);
LABEL_34:
    if ( (unsigned int)(*(_DWORD *)a3 - 2) <= 1 && v27 )
    {
      v24 = v27;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IApplication *))(*(_QWORD *)v27 + 8LL))(v27);
      GetPackagedAppIcon(&v24, a3);
    }
    RevertToSelf();
    v18 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IApplication *))(*(_QWORD *)v21 + 16LL))(v21);
    }
  }
  SHStrDupW(*((LPCWSTR *)a1 + 26), a3 + 4);
  PathRemoveBlanksW(a3[4]);
  *((_DWORD *)a3 + 15) = CuiGetBinaryLocation(v6);
}

```

## disassembly

```asm
0x14000eee4  push    rbp
0x14000eee6  push    rbx
0x14000eee7  push    rsi
0x14000eee8  push    rdi
0x14000eee9  push    r12
0x14000eeeb  push    r13
0x14000eeed  push    r14
0x14000eeef  push    r15
0x14000eef1  mov     rbp, rsp
0x14000eef4  sub     rsp, 48h
0x14000eef8  mov     rsi, r8
0x14000eefb  mov     r15, rdx
0x14000eefe  mov     r14, rcx
0x14000ef01  mov     r12, [rcx+0C8h]
0x14000ef08  xor     r13d, r13d
0x14000ef0b  test    r12, r12
0x14000ef0e  jnz     short loc_14000EF17
0x14000ef10  mov     r12, [rcx+0D0h]
0x14000ef17  mov     dword ptr [r8], 1
0x14000ef1e  mov     [rdx], r13b
0x14000ef21  cmp     [rcx+0E0h], r13
0x14000ef28  jz      loc_14000F1C3
0x14000ef2e  mov     rcx, [rcx+18h]; hToken
0x14000ef32  call    cs:__imp_ImpersonateLoggedOnUser
0x14000ef38  test    eax, eax
0x14000ef3a  jz      loc_14000F1C3
0x14000ef40  mov     [rbp+arg_18], r13
0x14000ef44  mov     [rbp+arg_10], r13
0x14000ef48  lea     r8, [rbp+arg_10]; struct Windows::Internal::StateRepository::IPackage **
0x14000ef4c  lea     rdx, [rbp+arg_18]; struct Windows::Internal::StateRepository::IApplication **
0x14000ef50  mov     rcx, [r14+0E0h]; sourceString
0x14000ef57  call    ?GetPackagedAppPackage@@YAJPEBGPEAPEAUIApplication@StateRepository@Internal@Windows@@PEAPEAUIPackage@234@@Z; GetPackagedAppPackage(ushort const *,Windows::Internal::StateRepository::IApplication * *,Windows::Internal::StateRepository::IPackage * *)
0x14000ef5c  mov     edi, eax
0x14000ef5e  mov     [rbp+var_10], r13
0x14000ef62  mov     [rbp+var_18], r13
0x14000ef66  test    eax, eax
0x14000ef68  js      loc_14000F0F2
0x14000ef6e  mov     rcx, [rbp+arg_10]
0x14000ef72  mov     [rbp+arg_0], rcx
0x14000ef76  test    rcx, rcx
0x14000ef79  jz      short loc_14000EF88
0x14000ef7b  mov     rax, [rcx]
0x14000ef7e  mov     rax, [rax+8]
0x14000ef82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef87  nop
0x14000ef88  mov     rcx, [rbp+arg_18]
0x14000ef8c  mov     [rbp+string], rcx
0x14000ef90  test    rcx, rcx
0x14000ef93  jz      short loc_14000EFA2
0x14000ef95  mov     rax, [rcx]
0x14000ef98  mov     rax, [rax+8]
0x14000ef9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000efa1  nop
0x14000efa2  lea     r9, [rbp+var_18]
0x14000efa6  lea     r8, [rbp+var_10]
0x14000efaa  lea     rdx, [rbp+arg_0]
0x14000efae  lea     rcx, [rbp+string]
0x14000efb2  call    ?GetPackagedResourceResolvers@@YAJV?$ComPtr@UIApplication@StateRepository@Internal@Windows@@@WRL@Microsoft@@V?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@23@PEAPEAUIApplicationResourceResolver@StateRepository@Internal@Windows@@PEAPEAUIPackageResourceResolver@678@@Z; GetPackagedResourceResolvers(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplication>,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>,Windows::Internal::StateRepository::IApplicationResourceResolver * *,Windows::Internal::StateRepository::IPackageResourceResolver * *)
0x14000efb7  mov     edi, eax
0x14000efb9  test    eax, eax
0x14000efbb  js      loc_14000F0F2
0x14000efc1  cmp     [rbp+arg_10], r13
0x14000efc5  jz      loc_14000F0F2
0x14000efcb  mov     rcx, r13
0x14000efce  mov     [rbp+string], rcx
0x14000efd2  mov     rbx, [rbp+var_18]
0x14000efd6  test    rbx, rbx
0x14000efd9  jz      short loc_14000F007
0x14000efdb  mov     rax, [rbx]
0x14000efde  mov     rdi, [rax+38h]
0x14000efe2  xor     ecx, ecx; string
0x14000efe4  call    cs:__imp_WindowsDeleteString
0x14000efea  mov     [rbp+string], r13
0x14000efee  lea     rdx, [rbp+string]
0x14000eff2  mov     rcx, rbx
0x14000eff5  mov     rax, rdi
0x14000eff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000effd  mov     edi, eax
0x14000efff  test    eax, eax
0x14000f001  js      short loc_14000F01C
0x14000f003  mov     rcx, [rbp+string]; string
0x14000f007  xor     edx, edx; length
0x14000f009  call    cs:__imp_WindowsGetStringRawBuffer
0x14000f00f  mov     rcx, rax; psz
0x14000f012  lea     rdx, [rsi+18h]; ppwsz
0x14000f016  call    cs:__imp_SHStrDupW
0x14000f01c  mov     rbx, [rbp+var_10]
0x14000f020  test    rbx, rbx
0x14000f023  jz      short loc_14000F04B
0x14000f025  mov     rax, [rbx]
0x14000f028  mov     rdi, [rax+30h]
0x14000f02c  mov     rcx, [rbp+string]; string
0x14000f030  call    cs:__imp_WindowsDeleteString
0x14000f036  mov     [rbp+string], r13
0x14000f03a  lea     rdx, [rbp+string]
0x14000f03e  mov     rcx, rbx
0x14000f041  mov     rax, rdi
0x14000f044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f049  mov     edi, eax
0x14000f04b  test    edi, edi
0x14000f04d  js      short loc_14000F068
0x14000f04f  xor     edx, edx; length
0x14000f051  mov     rcx, [rbp+string]; string
0x14000f055  call    cs:__imp_WindowsGetStringRawBuffer
0x14000f05b  mov     rcx, rax; psz
0x14000f05e  lea     rdx, [rsi+10h]; ppwsz
0x14000f062  call    cs:__imp_SHStrDupW
0x14000f068  mov     dword ptr [rbp+arg_0], r13d
0x14000f06c  mov     rcx, [rbp+arg_10]
0x14000f070  mov     rax, [rcx]
0x14000f073  lea     rdx, [rbp+arg_0]
0x14000f077  mov     rax, [rax+3E8h]
0x14000f07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f083  mov     r9d, eax
0x14000f086  mov     dword ptr [rsi], 1
0x14000f08c  test    eax, eax
0x14000f08e  js      short loc_14000F0B7
0x14000f090  mov     ecx, dword ptr [rbp+arg_0]
0x14000f093  cmp     ecx, 3
0x14000f096  jnz     short loc_14000F09C
0x14000f098  mov     [rsi], ecx
0x14000f09a  jmp     short loc_14000F0B1
0x14000f09c  lea     eax, [rcx-1]
0x14000f09f  test    eax, 0FFFFFFFCh
0x14000f0a4  jnz     short loc_14000F0E6
0x14000f0a6  cmp     ecx, 3
0x14000f0a9  jz      short loc_14000F0E6
0x14000f0ab  mov     dword ptr [rsi], 2
0x14000f0b1  mov     byte ptr [r15], 1
0x14000f0b5  jmp     short loc_14000F0E6
0x14000f0b7  lea     rax, WPP_GLOBAL_Control
0x14000f0be  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f0c5  cmp     rcx, rax
0x14000f0c8  jz      short loc_14000F0E6
0x14000f0ca  test    byte ptr [rcx+1Ch], 2
0x14000f0ce  jz      short loc_14000F0E6
0x14000f0d0  mov     edx, 18h
0x14000f0d5  lea     r8, WPP_bed9811735e730a365d52877ff824444_Traceguids
0x14000f0dc  mov     rcx, [rcx+10h]
0x14000f0e0  call    WPP_SF_D
0x14000f0e5  nop
0x14000f0e6  mov     rcx, [rbp+string]; string
0x14000f0ea  call    cs:__imp_WindowsDeleteString
0x14000f0f0  jmp     short loc_14000F124
0x14000f0f2  lea     rax, WPP_GLOBAL_Control
0x14000f0f9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f100  cmp     rcx, rax
0x14000f103  jz      short loc_14000F124
0x14000f105  test    byte ptr [rcx+1Ch], 2
0x14000f109  jz      short loc_14000F124
0x14000f10b  mov     edx, 19h
0x14000f110  mov     [rsp+48h+var_28], edi
0x14000f114  mov     r9, [r14+0E0h]
0x14000f11b  mov     rcx, [rcx+10h]
0x14000f11f  call    WPP_SF_SD
0x14000f124  mov     eax, [rsi]
0x14000f126  sub     eax, 2
0x14000f129  cmp     eax, 1
0x14000f12c  ja      short loc_14000F154
0x14000f12e  mov     rcx, [rbp+arg_18]
0x14000f132  test    rcx, rcx
0x14000f135  jz      short loc_14000F154
0x14000f137  mov     [rbp+arg_0], rcx
0x14000f13b  mov     rax, [rcx]
0x14000f13e  mov     rax, [rax+8]
0x14000f142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f147  nop
0x14000f148  mov     rdx, rsi
0x14000f14b  lea     rcx, [rbp+arg_0]
0x14000f14f  call    ?GetPackagedAppIcon@@YAXV?$ComPtr@UIApplication@StateRepository@Internal@Windows@@@WRL@Microsoft@@PEAU_CREDUI_CONTEXT@@@Z; GetPackagedAppIcon(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplication>,_CREDUI_CONTEXT *)
0x14000f154  call    cs:__imp_RevertToSelf
0x14000f15a  nop
0x14000f15b  mov     rcx, [rbp+var_18]
0x14000f15f  test    rcx, rcx
0x14000f162  jz      short loc_14000F175
0x14000f164  mov     [rbp+var_18], r13
0x14000f168  mov     rax, [rcx]
0x14000f16b  mov     rax, [rax+10h]
0x14000f16f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f174  nop
0x14000f175  mov     rcx, [rbp+var_10]
0x14000f179  test    rcx, rcx
0x14000f17c  jz      short loc_14000F18F
0x14000f17e  mov     [rbp+var_10], r13
0x14000f182  mov     rax, [rcx]
0x14000f185  mov     rax, [rax+10h]
0x14000f189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f18e  nop
0x14000f18f  mov     rcx, [rbp+arg_10]
0x14000f193  test    rcx, rcx
0x14000f196  jz      short loc_14000F1A9
0x14000f198  mov     [rbp+arg_10], r13
0x14000f19c  mov     rax, [rcx]
0x14000f19f  mov     rax, [rax+10h]
0x14000f1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f1a8  nop
0x14000f1a9  mov     rcx, [rbp+arg_18]
0x14000f1ad  test    rcx, rcx
0x14000f1b0  jz      short loc_14000F1C3
0x14000f1b2  mov     [rbp+arg_18], r13
0x14000f1b6  mov     rax, [rcx]
0x14000f1b9  mov     rax, [rax+10h]
0x14000f1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f1c2  nop
0x14000f1c3  lea     rdx, [rsi+20h]; ppwsz
0x14000f1c7  mov     rcx, [r14+0D0h]; psz
0x14000f1ce  call    cs:__imp_SHStrDupW
0x14000f1d4  mov     rcx, [rsi+20h]; pszPath
0x14000f1d8  call    cs:__imp_PathRemoveBlanksW
0x14000f1de  mov     rcx, r12
0x14000f1e1  call    ?CuiGetBinaryLocation@@YA?AW4_CONTEXT_FILE_LOCATION@@PEBG@Z; CuiGetBinaryLocation(ushort const *)
0x14000f1e6  mov     [rsi+3Ch], eax
0x14000f1e9  add     rsp, 48h
0x14000f1ed  pop     r15
0x14000f1ef  pop     r14
0x14000f1f1  pop     r13
0x14000f1f3  pop     r12
0x14000f1f5  pop     rdi
0x14000f1f6  pop     rsi
0x14000f1f7  pop     rbx
0x14000f1f8  pop     rbp
0x14000f1f9  retn
```
