# VsUI::CDpiAwareness::IsDotNetSupportedVersion(void)

- ea: `0x1400128e0`
- end: `0x140012ad8`
- name: `?IsDotNetSupportedVersion@CDpiAwareness@VsUI@@CA_NXZ`
- size: `504`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14001ca30`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140002dd0`
- `0x1400128e0`
- `0x140027c20`
- `0x140033ab0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140012a56`
- `ADVAPI32!RegCloseKey` at `0x140012a93`
- `ADVAPI32!RegCloseKey` at `0x140012a56`
- `ADVAPI32!RegCloseKey` at `0x140012a93`
- `ADVAPI32!RegOpenKeyExW` at `0x14001293d`
- `ADVAPI32!RegOpenKeyExW` at `0x14001293d`
- `VCRUNTIME140!wcsstr` at `0x140012a07`
- `VCRUNTIME140!wcsstr` at `0x140012a07`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400129c9`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400129c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool VsUI::CDpiAwareness::IsDotNetSupportedVersion(void)
{
  HKEY v0; // rbx
  struct ATL::IAtlStringMgr *Instance; // rax
  __int64 v2; // rax
  unsigned __int16 *v3; // r8
  int v4; // ebx
  wchar_t *v5; // rcx
  int v6; // eax
  wchar_t *v7; // rcx
  wchar_t *v8; // rax
  __int64 v9; // rax
  bool v10; // si
  wchar_t *v11; // rdx
  unsigned int v13; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v15; // [rsp+48h] [rbp-18h]
  wchar_t *Source; // [rsp+50h] [rbp-10h] BYREF

  *(_OWORD *)hKey = 0;
  v0 = 0;
  LODWORD(hKey[1]) = 0;
  v15 = 0;
  Source = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full",
         0,
         0x20019u,
         (PHKEY)&Source) )
  {
LABEL_22:
    v10 = 0;
    goto LABEL_23;
  }
  hKey[0] = (HKEY)Source;
  LODWORD(hKey[1]) = 0;
  Source = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v2 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance);
  v3 = (unsigned __int16 *)(v2 + 24);
  Source = (wchar_t *)(v2 + 24);
  v13 = 260;
  if ( ((1 - *(_DWORD *)(v2 + 16)) | (*(_DWORD *)(v2 + 12) - 260)) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&Source, 260);
    v3 = Source;
  }
  v4 = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)hKey, L"Version", v3, &v13);
  v5 = Source;
  if ( Source )
  {
    v6 = wcsnlen(Source, *((int *)Source - 3));
    if ( v6 < 0 )
      goto LABEL_27;
    v5 = Source;
  }
  else
  {
    v6 = 0;
  }
  if ( v6 > *((_DWORD *)v5 - 3) )
LABEL_27:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)v5 - 4) = v6;
  Source[v6] = 0;
  if ( v4 )
  {
    v0 = hKey[0];
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      v0 = 0;
      hKey[0] = 0;
    }
    LODWORD(hKey[1]) = 0;
    v11 = Source - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Source - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
    }
    goto LABEL_22;
  }
  v7 = Source;
  if ( *((int *)Source - 4) >= 0 && (v8 = wcsstr(Source, L"4.8"), v7 = Source, v8) )
    v9 = v8 - Source;
  else
    LODWORD(v9) = -1;
  v10 = (_DWORD)v9 == 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3) + 8LL))(*((_QWORD *)v7 - 3));
  }
  v0 = hKey[0];
LABEL_23:
  if ( v0 )
    RegCloseKey(v0);
  return v10;
}

```

## disassembly

```asm
0x1400128e0  mov     r11, rsp
0x1400128e3  mov     [r11+8], rbx
0x1400128e7  mov     [r11+10h], rsi
0x1400128eb  mov     [r11+18h], r14
0x1400128ef  push    rbp
0x1400128f0  mov     rbp, rsp
0x1400128f3  sub     rsp, 60h
0x1400128f7  mov     rax, cs:__security_cookie
0x1400128fe  xor     rax, rsp
0x140012901  mov     [rbp+var_8], rax
0x140012905  xorps   xmm0, xmm0
0x140012908  movups  xmmword ptr [rbp+hKey], xmm0
0x14001290c  xor     r14d, r14d
0x14001290f  mov     ebx, r14d
0x140012912  mov     dword ptr [rbp+hKey+8], r14d
0x140012916  mov     [rbp+var_18], r14
0x14001291a  mov     [rbp+Source], r14
0x14001291e  lea     rax, [rbp+Source]
0x140012922  mov     [r11-48h], rax
0x140012926  mov     r9d, 20019h; samDesired
0x14001292c  xor     r8d, r8d; ulOptions
0x14001292f  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\NET Framework Setu"...
0x140012936  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001293d  call    cs:__imp_RegOpenKeyExW
0x140012943  test    eax, eax
0x140012945  jnz     loc_140012A88
0x14001294b  mov     rax, [rbp+Source]
0x14001294f  mov     [rbp+hKey], rax
0x140012953  mov     dword ptr [rbp+hKey+8], r14d
0x140012957  mov     [rbp+Source], r14
0x14001295b  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140012960  mov     rcx, rax
0x140012963  test    rax, rax
0x140012966  jz      loc_140012ABE
0x14001296c  mov     rax, [rax]
0x14001296f  call    qword ptr [rax+18h]
0x140012972  lea     r8, [rax+18h]
0x140012976  mov     [rbp+Source], r8
0x14001297a  mov     edx, 104h
0x14001297f  mov     [rbp+var_30], edx
0x140012982  lea     ecx, [r14+1]
0x140012986  sub     ecx, [r8-8]
0x14001298a  mov     eax, [r8-0Ch]
0x14001298e  sub     eax, edx
0x140012990  or      eax, ecx
0x140012992  jge     short loc_1400129A1
0x140012994  lea     rcx, [rbp+Source]
0x140012998  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14001299d  mov     r8, [rbp+Source]; unsigned __int16 *
0x1400129a1  lea     r9, [rbp+var_30]; unsigned int *
0x1400129a5  lea     rdx, aVersion_0; "Version"
0x1400129ac  lea     rcx, [rbp+hKey]; this
0x1400129b0  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x1400129b5  mov     ebx, eax
0x1400129b7  mov     rcx, [rbp+Source]; Source
0x1400129bb  test    rcx, rcx
0x1400129be  jnz     short loc_1400129C5
0x1400129c0  mov     eax, r14d
0x1400129c3  jmp     short loc_1400129DB
0x1400129c5  movsxd  rdx, dword ptr [rcx-0Ch]; MaxCount
0x1400129c9  call    cs:__imp_wcsnlen
0x1400129cf  test    eax, eax
0x1400129d1  js      loc_140012ACD
0x1400129d7  mov     rcx, [rbp+Source]
0x1400129db  cmp     eax, [rcx-0Ch]
0x1400129de  jg      loc_140012ACD
0x1400129e4  mov     [rcx-10h], eax
0x1400129e7  mov     ecx, eax
0x1400129e9  mov     rax, [rbp+Source]
0x1400129ed  mov     [rax+rcx*2], r14w
0x1400129f2  test    ebx, ebx
0x1400129f4  jnz     short loc_140012A4A
0x1400129f6  mov     rcx, [rbp+Source]; Str
0x1400129fa  cmp     [rcx-10h], r14d
0x1400129fe  jl      short loc_140012A16
0x140012a00  lea     rdx, a48; "4.8"
0x140012a07  call    cs:__imp_wcsstr
0x140012a0d  mov     rcx, [rbp+Source]
0x140012a11  test    rax, rax
0x140012a14  jnz     short loc_140012A1B
0x140012a16  or      eax, 0FFFFFFFFh
0x140012a19  jmp     short loc_140012A21
0x140012a1b  sub     rax, rcx
0x140012a1e  sar     rax, 1
0x140012a21  test    eax, eax
0x140012a23  setz    sil
0x140012a27  lea     rdx, [rcx-18h]
0x140012a2b  or      eax, 0FFFFFFFFh
0x140012a2e  lock xadd [rdx+10h], eax
0x140012a33  sub     eax, 1
0x140012a36  jg      short loc_140012A44
0x140012a38  lfence
0x140012a3b  mov     rcx, [rdx]
0x140012a3e  mov     rax, [rcx]
0x140012a41  call    qword ptr [rax+8]
0x140012a44  mov     rbx, [rbp+hKey]
0x140012a48  jmp     short loc_140012A8B
0x140012a4a  mov     rbx, [rbp+hKey]
0x140012a4e  test    rbx, rbx
0x140012a51  jz      short loc_140012A63
0x140012a53  mov     rcx, rbx; hKey
0x140012a56  call    cs:__imp_RegCloseKey
0x140012a5c  mov     rbx, r14
0x140012a5f  mov     [rbp+hKey], rbx
0x140012a63  mov     dword ptr [rbp+hKey+8], r14d
0x140012a67  mov     rdx, [rbp+Source]
0x140012a6b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140012a6f  or      eax, 0FFFFFFFFh
0x140012a72  lock xadd [rdx+10h], eax
0x140012a77  sub     eax, 1
0x140012a7a  jg      short loc_140012A88
0x140012a7c  lfence
0x140012a7f  mov     rcx, [rdx]
0x140012a82  mov     rax, [rcx]
0x140012a85  call    qword ptr [rax+8]
0x140012a88  mov     sil, r14b
0x140012a8b  test    rbx, rbx
0x140012a8e  jz      short loc_140012A99
0x140012a90  mov     rcx, rbx; hKey
0x140012a93  call    cs:__imp_RegCloseKey
0x140012a99  mov     al, sil
0x140012a9c  mov     rcx, [rbp+var_8]
0x140012aa0  xor     rcx, rsp; StackCookie
0x140012aa3  call    __security_check_cookie
0x140012aa8  lea     r11, [rsp+60h+var_s0]
0x140012aad  mov     rbx, [r11+10h]
0x140012ab1  mov     rsi, [r11+18h]
0x140012ab5  mov     r14, [r11+20h]
0x140012ab9  mov     rsp, r11
0x140012abc  pop     rbp
0x140012abd  retn
0x140012abe  mov     ecx, 80004005h; int
0x140012ac3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140012ac9  jmp     short loc_140012ACC
0x140012acc  nop
0x140012acd  mov     ecx, 80070057h; int
0x140012ad2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
