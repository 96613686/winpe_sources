# _ParseSecurityUrl

- ea: `0x180037bf8`
- end: `0x180037f84`
- name: `_ParseSecurityUrl`
- size: `908`
- prototype: `__int64 __fastcall(STRW *this, STRW *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800204f0`

## callees

- `0x180002098`
- `0x180004d60`
- `0x180004f40`
- `0x180012590`
- `0x180015858`
- `0x180021a14`
- `0x18002c47c`
- `0x180037348`
- `0x180037bf8`
- `0x1800cc996`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `SHLWAPI!StrCmpNIW` at `0x180037db2`
- `SHLWAPI!StrCmpNIW` at `0x180037db2`
- `urlmon!CoInternetCreateSecurityManager` at `0x180037ca9`
- `urlmon!CoInternetCreateSecurityManager` at `0x180037ca9`
- `urlmon!__imp_GetZoneAgnosticSecurityIdFromUrl` at `0x180037cd7`
- `urlmon!__imp_GetZoneAgnosticSecurityIdFromUrl` at `0x180037d5e`
- `urlmon!__imp_GetZoneAgnosticSecurityIdFromUrl` at `0x180037cd7`
- `urlmon!__imp_GetZoneAgnosticSecurityIdFromUrl` at `0x180037d5e`
- `ole32!StringFromGUID2` at `0x180037ead`
- `ole32!StringFromGUID2` at `0x180037ead`
- `ole32!CoCreateGuid` at `0x180037e92`
- `ole32!CoCreateGuid` at `0x180037e92`

## pseudocode

```c
__int64 __fastcall ParseSecurityUrl(STRW *this, STRW *a2)
{
  const WCHAR *v4; // rsi
  const WCHAR *v5; // r15
  const WCHAR *v6; // rcx
  HRESULT ZoneAgnosticSecurityIdFromUrl; // ebx
  int v8; // eax
  const unsigned __int16 *v9; // rdx
  size_t Size; // [rsp+38h] [rbp-C8h] BYREF
  int v12; // [rsp+40h] [rbp-C0h] BYREF
  IInternetSecurityManager *ppSM; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v14; // [rsp+50h] [rbp-B0h] BYREF
  void *v15; // [rsp+58h] [rbp-A8h]
  PCWSTR psz1[4]; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR sz; // [rsp+90h] [rbp-70h] BYREF
  char v18; // [rsp+92h] [rbp-6Eh] BYREF
  __int16 v19; // [rsp+DAh] [rbp-26h]
  unsigned __int16 v20[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE Buf2[1024]; // [rsp+4B0h] [rbp+3B0h] BYREF
  _BYTE Buf1[1024]; // [rsp+8B0h] [rbp+7B0h] BYREF

  ppSM = 0;
  Size = 0x40000000400LL;
  v4 = 0;
  psz1[0] = 0;
  STRW::STRW((STRW *)&v14, v20, 0x104u);
  v5 = &cchOriginalDestLength;
  v12 = 4;
  v6 = &cchOriginalDestLength;
  if ( *(_DWORD *)this )
    v6 = (const WCHAR *)*((_QWORD *)this + 1);
  ZoneAgnosticSecurityIdFromUrl = MimeOleParseMhtmlUrlW(v6);
  if ( ZoneAgnosticSecurityIdFromUrl >= 0 )
  {
    ZoneAgnosticSecurityIdFromUrl = CoInternetCreateSecurityManager(0, &ppSM, 0);
    if ( ZoneAgnosticSecurityIdFromUrl >= 0 )
    {
      ZoneAgnosticSecurityIdFromUrl = GetZoneAgnosticSecurityIdFromUrl(ppSM, 0, Buf1, &Size, 0);
      if ( ZoneAgnosticSecurityIdFromUrl >= 0 )
      {
        ZoneAgnosticSecurityIdFromUrl = STRW::UrlUnescapeA(this);
        if ( ZoneAgnosticSecurityIdFromUrl >= 0 )
        {
          if ( *(_DWORD *)this )
            v5 = (const WCHAR *)*((_QWORD *)this + 1);
          ZoneAgnosticSecurityIdFromUrl = MimeOleParseMhtmlUrlW(v5);
          if ( ZoneAgnosticSecurityIdFromUrl < 0 )
          {
            v4 = psz1[0];
            goto LABEL_31;
          }
          v8 = GetZoneAgnosticSecurityIdFromUrl(ppSM, 0, Buf2, (char *)&Size + 4, 0);
          v4 = psz1[0];
          ZoneAgnosticSecurityIdFromUrl = v8;
          if ( v8 < 0 )
            goto LABEL_31;
          if ( (_DWORD)Size == HIDWORD(Size)
            && !memcmp_0(Buf1, Buf2, (unsigned int)Size)
            && (!v4 || StrCmpNIW(v4, L"x-usc:", 6)) )
          {
            v9 = 0;
          }
          else
          {
            *(_OWORD *)psz1 = 0;
            memset_0(&sz, 0, 0x208u);
            ZoneAgnosticSecurityIdFromUrl = CoCreateGuid((GUID *)psz1);
            if ( ZoneAgnosticSecurityIdFromUrl < 0 )
              goto LABEL_31;
            ZoneAgnosticSecurityIdFromUrl = StringFromGUID2((const GUID *const)psz1, &sz, 260);
            if ( ZoneAgnosticSecurityIdFromUrl < 0 )
              goto LABEL_31;
            v19 = 0;
            ZoneAgnosticSecurityIdFromUrl = STRW::Append((STRW *)&v14, L"about:restricted.");
            if ( ZoneAgnosticSecurityIdFromUrl < 0 )
              goto LABEL_31;
            v9 = (const unsigned __int16 *)&v18;
          }
          ZoneAgnosticSecurityIdFromUrl = STRW::Append((STRW *)&v14, v9);
          if ( ZoneAgnosticSecurityIdFromUrl >= 0 )
          {
            ZoneAgnosticSecurityIdFromUrl = ((__int64 (__fastcall *)(IInternetSecurityManager *, _QWORD, int *, _QWORD))ppSM->lpVtbl->MapUrlToZone)(
                                              ppSM,
                                              0,
                                              &v12,
                                              0);
            if ( ZoneAgnosticSecurityIdFromUrl >= 0 )
            {
              if ( !v12 )
              {
                STRW::STRW((STRW *)psz1, &sz, 0x104u);
                if ( (int)GetContentLocationFromMIME(0, v4, psz1) >= 0 )
                {
                  memset_0(v15, 0, 2LL * v14);
                  v14 = 0;
                  ZoneAgnosticSecurityIdFromUrl = STRW::Append((STRW *)&v14, (const struct STRW *)psz1);
                  if ( ZoneAgnosticSecurityIdFromUrl < 0 )
                  {
                    STRW::~STRW((STRW *)psz1);
                    goto LABEL_31;
                  }
                }
                STRW::~STRW((STRW *)psz1);
              }
              ZoneAgnosticSecurityIdFromUrl = STRW::Append(a2, (const struct STRW *)&v14);
              if ( ZoneAgnosticSecurityIdFromUrl >= 0 )
                ZoneAgnosticSecurityIdFromUrl = 0;
            }
          }
        }
      }
    }
  }
LABEL_31:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&ppSM);
  if ( v4 )
    ((void (__fastcall *)(LPMALLOC, const WCHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v4);
  STRW::~STRW((STRW *)&v14);
  return (unsigned int)ZoneAgnosticSecurityIdFromUrl;
}

```

## disassembly

```asm
0x180037bf8  mov     [rsp-8+arg_10], rbx
0x180037bfd  mov     [rsp-8+arg_18], rsi
0x180037c02  push    rbp
0x180037c03  push    rdi
0x180037c04  push    r12
0x180037c06  push    r14
0x180037c08  push    r15
0x180037c0a  lea     rbp, [rsp-0BC0h]
0x180037c12  sub     rsp, 0CC0h
0x180037c19  mov     rax, cs:__security_cookie
0x180037c20  xor     rax, rsp
0x180037c23  mov     [rbp+0BE0h+var_30], rax
0x180037c2a  mov     eax, 400h
0x180037c2f  mov     [rsp+0CE0h+ppSM], 0
0x180037c38  mov     r12, rdx
0x180037c3b  mov     dword ptr [rsp+0CE0h+Size], eax
0x180037c3f  mov     r14, rcx
0x180037c42  mov     dword ptr [rsp+0CE0h+Size+4], eax
0x180037c46  xor     esi, esi
0x180037c48  mov     [rsp+0CE0h+var_CB0], 0
0x180037c51  lea     rdx, [rbp+0BE0h+var_A40]; unsigned __int16 *
0x180037c58  mov     [rsp+0CE0h+psz1], rsi
0x180037c5d  lea     rcx, [rsp+0CE0h+var_C90]; this
0x180037c62  mov     r8d, 104h; unsigned int
0x180037c68  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180037c6d  lea     r15, cchOriginalDestLength
0x180037c74  mov     [rsp+0CE0h+var_CA0], 4
0x180037c7c  mov     rcx, r15
0x180037c7f  cmp     [r14], esi
0x180037c82  jz      short loc_180037C88
0x180037c84  mov     rcx, [r14+8]; psz1
0x180037c88  xor     r8d, r8d
0x180037c8b  lea     rdx, [rsp+0CE0h+var_CB0]
0x180037c90  call    MimeOleParseMhtmlUrlW
0x180037c95  mov     ebx, eax
0x180037c97  test    eax, eax
0x180037c99  js      loc_180037F08
0x180037c9f  xor     r8d, r8d; dwReserved
0x180037ca2  lea     rdx, [rsp+0CE0h+ppSM]; ppSM
0x180037ca7  xor     ecx, ecx; pSP
0x180037ca9  call    cs:__imp_CoInternetCreateSecurityManager
0x180037caf  mov     ebx, eax
0x180037cb1  test    eax, eax
0x180037cb3  js      loc_180037F08
0x180037cb9  mov     rdi, [rsp+0CE0h+var_CB0]
0x180037cbe  lea     r9, [rsp+0CE0h+Size]
0x180037cc3  mov     rcx, [rsp+0CE0h+ppSM]
0x180037cc8  lea     r8, [rbp+0BE0h+Buf1]
0x180037ccf  mov     rdx, rdi
0x180037cd2  mov     [rsp+0CE0h+var_CC0], rsi
0x180037cd7  call    cs:__imp_GetZoneAgnosticSecurityIdFromUrl
0x180037cdd  mov     ebx, eax
0x180037cdf  test    eax, eax
0x180037ce1  js      loc_180037F0D
0x180037ce7  test    rdi, rdi
0x180037cea  jz      short loc_180037D09
0x180037cec  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180037cf3  mov     rdx, rdi
0x180037cf6  mov     rax, [rcx]
0x180037cf9  mov     rax, [rax+28h]
0x180037cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d02  xor     edi, edi
0x180037d04  mov     [rsp+0CE0h+var_CB0], rdi
0x180037d09  mov     rcx, r14; this
0x180037d0c  call    ?UrlUnescapeA@STRW@@QEAAJXZ; STRW::UrlUnescapeA(void)
0x180037d11  mov     ebx, eax
0x180037d13  test    eax, eax
0x180037d15  js      loc_180037F0D
0x180037d1b  cmp     [r14], esi
0x180037d1e  jz      short loc_180037D24
0x180037d20  mov     r15, [r14+8]
0x180037d24  lea     r8, [rsp+0CE0h+psz1]
0x180037d29  mov     rcx, r15; psz1
0x180037d2c  lea     rdx, [rsp+0CE0h+var_CB0]
0x180037d31  call    MimeOleParseMhtmlUrlW
0x180037d36  mov     rdi, [rsp+0CE0h+var_CB0]
0x180037d3b  mov     ebx, eax
0x180037d3d  test    eax, eax
0x180037d3f  js      loc_180037F01
0x180037d45  mov     rcx, [rsp+0CE0h+ppSM]
0x180037d4a  lea     r9, [rsp+0CE0h+Size+4]
0x180037d4f  lea     r8, [rbp+0BE0h+Buf2]
0x180037d56  mov     [rsp+0CE0h+var_CC0], rsi
0x180037d5b  mov     rdx, rdi
0x180037d5e  call    cs:__imp_GetZoneAgnosticSecurityIdFromUrl
0x180037d64  mov     rsi, [rsp+0CE0h+psz1]
0x180037d69  mov     ebx, eax
0x180037d6b  test    eax, eax
0x180037d6d  js      loc_180037F0D
0x180037d73  mov     eax, dword ptr [rsp+0CE0h+Size]
0x180037d77  cmp     eax, dword ptr [rsp+0CE0h+Size+4]
0x180037d7b  jnz     loc_180037E74
0x180037d81  mov     r8d, eax; Size
0x180037d84  lea     rdx, [rbp+0BE0h+Buf2]; Buf2
0x180037d8b  lea     rcx, [rbp+0BE0h+Buf1]; Buf1
0x180037d92  call    memcmp_0
0x180037d97  test    eax, eax
0x180037d99  jnz     loc_180037E74
0x180037d9f  test    rsi, rsi
0x180037da2  jz      short loc_180037DC0
0x180037da4  lea     r8d, [rax+6]; nChar
0x180037da8  mov     rcx, rsi; psz1
0x180037dab  lea     rdx, aXUsc; "x-usc:"
0x180037db2  call    cs:__imp_StrCmpNIW
0x180037db8  test    eax, eax
0x180037dba  jz      loc_180037E74
0x180037dc0  mov     rdx, rdi; unsigned __int16 *
0x180037dc3  lea     rcx, [rsp+0CE0h+var_C90]; this
0x180037dc8  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180037dcd  mov     ebx, eax
0x180037dcf  test    eax, eax
0x180037dd1  js      loc_180037F0D
0x180037dd7  mov     rcx, [rsp+0CE0h+ppSM]
0x180037ddc  lea     r8, [rsp+0CE0h+var_CA0]
0x180037de1  xor     r9d, r9d
0x180037de4  mov     rdx, rdi
0x180037de7  mov     rax, [rcx]
0x180037dea  mov     rax, [rax+28h]
0x180037dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037df3  mov     ebx, eax
0x180037df5  test    eax, eax
0x180037df7  js      loc_180037F0D
0x180037dfd  cmp     [rsp+0CE0h+var_CA0], 0
0x180037e02  jnz     loc_180037EE9
0x180037e08  mov     r8d, 104h; unsigned int
0x180037e0e  lea     rdx, [rbp+0BE0h+sz]; unsigned __int16 *
0x180037e12  lea     rcx, [rsp+0CE0h+psz1]; this
0x180037e17  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180037e1c  lea     r8, [rsp+0CE0h+psz1]
0x180037e21  mov     rdx, rsi
0x180037e24  mov     rcx, rdi
0x180037e27  call    _GetContentLocationFromMIME
0x180037e2c  test    eax, eax
0x180037e2e  js      loc_180037EDF
0x180037e34  mov     r8d, [rsp+0CE0h+var_C90]
0x180037e39  xor     edx, edx; Val
0x180037e3b  mov     rcx, [rsp+0CE0h+var_C88]; void *
0x180037e40  add     r8, r8; Size
0x180037e43  call    memset_0
0x180037e48  lea     rdx, [rsp+0CE0h+psz1]; struct STRW *
0x180037e4d  mov     [rsp+0CE0h+var_C90], 0
0x180037e55  lea     rcx, [rsp+0CE0h+var_C90]; this
0x180037e5a  call    ?Append@STRW@@QEAAJPEBV1@@Z; STRW::Append(STRW const *)
0x180037e5f  mov     ebx, eax
0x180037e61  test    eax, eax
0x180037e63  jns     short loc_180037EDF
0x180037e65  lea     rcx, [rsp+0CE0h+psz1]; this
0x180037e6a  call    ??1STRW@@QEAA@XZ; STRW::~STRW(void)
0x180037e6f  jmp     loc_180037F0D
0x180037e74  xorps   xmm0, xmm0
0x180037e77  lea     rcx, [rbp+0BE0h+sz]; void *
0x180037e7b  xor     edx, edx; Val
0x180037e7d  mov     r8d, 208h; Size
0x180037e83  movups  xmmword ptr [rsp+0CE0h+psz1], xmm0
0x180037e88  call    memset_0
0x180037e8d  lea     rcx, [rsp+0CE0h+psz1]; pguid
0x180037e92  call    cs:__imp_CoCreateGuid
0x180037e98  mov     ebx, eax
0x180037e9a  test    eax, eax
0x180037e9c  js      short loc_180037F0D
0x180037e9e  mov     r8d, 104h; cchMax
0x180037ea4  lea     rdx, [rbp+0BE0h+sz]; lpsz
0x180037ea8  lea     rcx, [rsp+0CE0h+psz1]; rguid
0x180037ead  call    cs:__imp_StringFromGUID2
0x180037eb3  mov     ebx, eax
0x180037eb5  test    eax, eax
0x180037eb7  js      short loc_180037F0D
0x180037eb9  xor     eax, eax
0x180037ebb  lea     rdx, aAboutRestricte; "about:restricted."
0x180037ec2  lea     rcx, [rsp+0CE0h+var_C90]; this
0x180037ec7  mov     [rbp+0BE0h+var_C06], ax
0x180037ecb  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180037ed0  mov     ebx, eax
0x180037ed2  test    eax, eax
0x180037ed4  js      short loc_180037F0D
0x180037ed6  lea     rdx, [rbp+0BE0h+var_C4E]
0x180037eda  jmp     loc_180037DC3
0x180037edf  lea     rcx, [rsp+0CE0h+psz1]; this
0x180037ee4  call    ??1STRW@@QEAA@XZ; STRW::~STRW(void)
0x180037ee9  lea     rdx, [rsp+0CE0h+var_C90]; struct STRW *
0x180037eee  mov     rcx, r12; this
0x180037ef1  call    ?Append@STRW@@QEAAJPEBV1@@Z; STRW::Append(STRW const *)
0x180037ef6  mov     ebx, eax
0x180037ef8  xor     eax, eax
0x180037efa  test    ebx, ebx
0x180037efc  cmovns  ebx, eax
0x180037eff  jmp     short loc_180037F0D
0x180037f01  mov     rsi, [rsp+0CE0h+psz1]
0x180037f06  jmp     short loc_180037F0D
0x180037f08  mov     rdi, [rsp+0CE0h+var_CB0]
0x180037f0d  lea     rcx, [rsp+0CE0h+ppSM]
0x180037f12  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180037f17  test    rdi, rdi
0x180037f1a  jz      short loc_180037F32
0x180037f1c  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180037f23  mov     rdx, rdi
0x180037f26  mov     rax, [rcx]
0x180037f29  mov     rax, [rax+28h]
0x180037f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f32  test    rsi, rsi
0x180037f35  jz      short loc_180037F4D
0x180037f37  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180037f3e  mov     rdx, rsi
0x180037f41  mov     rax, [rcx]
0x180037f44  mov     rax, [rax+28h]
0x180037f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f4d  lea     rcx, [rsp+0CE0h+var_C90]; this
0x180037f52  call    ??1STRW@@QEAA@XZ; STRW::~STRW(void)
0x180037f57  mov     eax, ebx
0x180037f59  mov     rcx, [rbp+0BE0h+var_30]
0x180037f60  xor     rcx, rsp; StackCookie
0x180037f63  call    __security_check_cookie
0x180037f68  lea     r11, [rsp+0CE0h+var_20]
0x180037f70  mov     rbx, [r11+40h]
0x180037f74  mov     rsi, [r11+48h]
0x180037f78  mov     rsp, r11
0x180037f7b  pop     r15
0x180037f7d  pop     r14
0x180037f7f  pop     r12
0x180037f81  pop     rdi
0x180037f82  pop     rbp
0x180037f83  retn
```
