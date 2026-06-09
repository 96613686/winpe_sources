# TestForOOBEInfoFileLocalized(ushort const *,ushort,ushort * *)

- ea: `0x1800221d8`
- end: `0x18002249b`
- name: `?TestForOOBEInfoFileLocalized@@YAJPEBGGPEAPEAG@Z`
- size: `707`
- prototype: `int(const unsigned __int16 *, unsigned __int16, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180023000`
- `0x18003f474`
- `0x18003fe30`

## callees

- `0x180003470`
- `0x180008b98`
- `0x18001e47c`
- `0x18001e508`
- `0x18001ecec`
- `0x18001f348`
- `0x180022154`
- `0x1800221d8`
- `0x1800b8834`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x180022277`
- `SHELL32!SHGetFolderPathEx` at `0x180022277`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x18002221d`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x18002221d`

## string_xrefs

- `0x1800223d9`: `Failed to get set localized path with hr=0x%08X`
- `0x18002240e`: `GetSetLocalizedPathFailed`
- `0x18002241a`: `Failed to get system folder path with hr=0x%08X`
- `0x18002244f`: `GetSystemFolderPathFailed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TestForOOBEInfoFileLocalized(const unsigned __int16 *a1, unsigned __int16 a2, unsigned __int16 **a3)
{
  int v4; // esi
  GEOID UserGeoID; // r15d
  int v7; // eax
  int v8; // ebx
  const unsigned __int16 *v9; // rax
  __int64 v10; // rcx
  const wchar_t *v11; // rdx
  __int64 v13; // [rsp+20h] [rbp-E0h]
  __int64 v14; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v15; // [rsp+40h] [rbp-C0h] BYREF
  void **v16; // [rsp+48h] [rbp-B8h] BYREF
  int v17; // [rsp+50h] [rbp-B0h]
  __int128 v18; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v19[264]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v20[528]; // [rsp+280h] [rbp+180h] BYREF

  v4 = a2;
  *a3 = 0;
  UserGeoID = GetUserGeoID(0x10u);
  if ( UserGeoID == -1 )
    UserGeoID = 244;
  if ( (_WORD)v4 == 0xFFFF )
  {
    UnattendLogW(2, L"Language ID not set.  Unable to search for language specific OEM Eula.");
    CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[29],unsigned short const (&)[20]>();
  }
  v7 = SHGetFolderPathEx(&FOLDERID_System, 0x4000, -1, v20, 260);
  v8 = v7;
  if ( v7 < 0 )
  {
    UnattendLogW(1, L"Failed to get system folder path with hr=0x%08X", (unsigned int)v7);
    v16 = &_com_error::`vftable';
    v17 = v8;
    v18 = 0;
    v9 = _com_error::ErrorMessage((_com_error *)&v16);
    v11 = L"GetSystemFolderPathFailed";
    goto LABEL_20;
  }
  if ( (_WORD)v4 == 0xFFFF
    || (LODWORD(v13) = UserGeoID, StringCchPrintfW(v19, 0x104u, L"%s\\oobe\\info\\%li\\%i\\%s", v20, v13, v4, a1) < 0)
    || (v8 = Details::TestForFile(v19, a3), v8 < 0) )
  {
    LODWORD(v13) = UserGeoID;
    v8 = StringCchPrintfW(v19, 0x104u, L"%s\\oobe\\info\\%li\\%s", v20, v13, a1);
    if ( v8 < 0
      || (v8 = Details::TestForFile(v19, a3), v8 < 0)
      && ((_WORD)v4 == 0xFFFF
       || (LODWORD(v14) = v4, StringCchPrintfW(v19, 0x104u, L"%s\\oobe\\info\\default\\%i\\%s", v20, v14, a1) < 0)
       || (v8 = Details::TestForFile(v19, a3), v8 < 0))
      && ((v8 = StringCchPrintfW(v19, 0x104u, L"%s\\oobe\\info\\default\\%s", v20, a1), v8 < 0)
       || (v8 = Details::TestForFile(v19, a3), v8 < 0)
       && ((v8 = StringCchPrintfW(v19, 0x104u, L"%s\\oobe\\info\\%s", v20, a1), v8 < 0)
        || (v8 = Details::TestForFile(v19, a3), v8 < 0))) )
    {
      UnattendLogW(2, L"Failed to get set localized path with hr=0x%08X", (unsigned int)v8);
      v16 = &_com_error::`vftable';
      v17 = v8;
      v18 = 0;
      v9 = _com_error::ErrorMessage((_com_error *)&v16);
      v11 = L"GetSetLocalizedPathFailed";
LABEL_20:
      v15 = v9;
      CloudExperienceHostCoreTelemetry::CoreEvent2<char const (&)[29],unsigned short const (&)[26],unsigned short const *>(
        v10,
        v11,
        &v15);
      _com_error::~_com_error((_com_error *)&v16);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800221d8  mov     [rsp-8+arg_18], rbx
0x1800221dd  push    rbp
0x1800221de  push    rsi
0x1800221df  push    rdi
0x1800221e0  push    r12
0x1800221e2  push    r13
0x1800221e4  push    r14
0x1800221e6  push    r15
0x1800221e8  lea     rbp, [rsp-3A0h]
0x1800221f0  sub     rsp, 4A0h
0x1800221f7  mov     rax, cs:__security_cookie
0x1800221fe  xor     rax, rsp
0x180022201  mov     [rbp+3D0h+var_40], rax
0x180022208  mov     rdi, r8
0x18002220b  movzx   esi, dx
0x18002220e  mov     r14, rcx
0x180022211  mov     qword ptr [r8], 0
0x180022218  mov     ecx, 10h; GeoClass
0x18002221d  call    cs:__imp_GetUserGeoID
0x180022223  mov     r15d, eax
0x180022226  mov     eax, 0F4h
0x18002222b  cmp     r15d, 0FFFFFFFFh
0x18002222f  cmovz   r15d, eax
0x180022233  mov     r13d, 0FFFFh
0x180022239  cmp     si, r13w
0x18002223d  jnz     short loc_180022255
0x18002223f  lea     rdx, aLanguageIdNotS; "Language ID not set.  Unable to search "...
0x180022246  mov     ecx, 2
0x18002224b  call    UnattendLogW
0x180022250  call    ??$CoreEvent1@AEAY0BN@$$CBDAEAY0BE@$$CBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0BN@$$CBDAEAY0BE@$$CBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[29],ushort const (&)[20]>(char const (&)[29],ushort const (&)[20])
0x180022255  mov     r12d, 104h
0x18002225b  mov     dword ptr [rsp+4D0h+var_4B0], r12d
0x180022260  lea     r9, [rbp+3D0h+var_250]
0x180022267  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002226b  mov     edx, 4000h
0x180022270  lea     rcx, FOLDERID_System
0x180022277  call    cs:__imp_SHGetFolderPathEx
0x18002227d  mov     ebx, eax
0x18002227f  test    eax, eax
0x180022281  js      loc_180022417
0x180022287  cmp     si, r13w
0x18002228b  jz      short loc_1800222D1
0x18002228d  mov     [rsp+4D0h+var_4A0], r14
0x180022292  mov     dword ptr [rsp+4D0h+var_4A8], esi
0x180022296  mov     dword ptr [rsp+4D0h+var_4B0], r15d
0x18002229b  lea     r9, [rbp+3D0h+var_250]
0x1800222a2  lea     r8, aSOobeInfoLiIS; "%s\\oobe\\info\\%li\\%i\\%s"
0x1800222a9  mov     edx, r12d; unsigned __int64
0x1800222ac  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x1800222b1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800222b6  test    eax, eax
0x1800222b8  js      short loc_1800222D1
0x1800222ba  mov     rdx, rdi; unsigned __int16 **
0x1800222bd  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x1800222c2  call    ?TestForFile@Details@@YAJPEBGPEAPEAG@Z; Details::TestForFile(ushort const *,ushort * *)
0x1800222c7  mov     ebx, eax
0x1800222c9  test    eax, eax
0x1800222cb  jns     loc_18002246F
0x1800222d1  mov     [rsp+4D0h+var_4A8], r14
0x1800222d6  mov     dword ptr [rsp+4D0h+var_4B0], r15d
0x1800222db  lea     r9, [rbp+3D0h+var_250]
0x1800222e2  lea     r8, aSOobeInfoLiS; "%s\\oobe\\info\\%li\\%s"
0x1800222e9  mov     rdx, r12; unsigned __int64
0x1800222ec  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x1800222f1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800222f6  mov     ebx, eax
0x1800222f8  test    eax, eax
0x1800222fa  js      loc_1800223D6
0x180022300  mov     rdx, rdi; unsigned __int16 **
0x180022303  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x180022308  call    ?TestForFile@Details@@YAJPEBGPEAPEAG@Z; Details::TestForFile(ushort const *,ushort * *)
0x18002230d  mov     ebx, eax
0x18002230f  test    eax, eax
0x180022311  jns     loc_18002246F
0x180022317  cmp     si, r13w
0x18002231b  jz      short loc_18002235C
0x18002231d  mov     [rsp+4D0h+var_4A8], r14
0x180022322  mov     dword ptr [rsp+4D0h+var_4B0], esi
0x180022326  lea     r9, [rbp+3D0h+var_250]
0x18002232d  lea     r8, aSOobeInfoDefau_0; "%s\\oobe\\info\\default\\%i\\%s"
0x180022334  mov     rdx, r12; unsigned __int64
0x180022337  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x18002233c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022341  test    eax, eax
0x180022343  js      short loc_18002235C
0x180022345  mov     rdx, rdi; unsigned __int16 **
0x180022348  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x18002234d  call    ?TestForFile@Details@@YAJPEBGPEAPEAG@Z; Details::TestForFile(ushort const *,ushort * *)
0x180022352  mov     ebx, eax
0x180022354  test    eax, eax
0x180022356  jns     loc_18002246F
0x18002235c  mov     [rsp+4D0h+var_4B0], r14
0x180022361  lea     r9, [rbp+3D0h+var_250]
0x180022368  lea     r8, aSOobeInfoDefau; "%s\\oobe\\info\\default\\%s"
0x18002236f  mov     rdx, r12; unsigned __int64
0x180022372  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x180022377  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002237c  mov     ebx, eax
0x18002237e  test    eax, eax
0x180022380  js      short loc_1800223D6
0x180022382  mov     rdx, rdi; unsigned __int16 **
0x180022385  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x18002238a  call    ?TestForFile@Details@@YAJPEBGPEAPEAG@Z; Details::TestForFile(ushort const *,ushort * *)
0x18002238f  mov     ebx, eax
0x180022391  test    eax, eax
0x180022393  jns     loc_18002246F
0x180022399  mov     [rsp+4D0h+var_4B0], r14
0x18002239e  lea     r9, [rbp+3D0h+var_250]
0x1800223a5  lea     r8, aSOobeInfoS; "%s\\oobe\\info\\%s"
0x1800223ac  mov     rdx, r12; unsigned __int64
0x1800223af  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x1800223b4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800223b9  mov     ebx, eax
0x1800223bb  test    eax, eax
0x1800223bd  js      short loc_1800223D6
0x1800223bf  mov     rdx, rdi; unsigned __int16 **
0x1800223c2  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x1800223c7  call    ?TestForFile@Details@@YAJPEBGPEAPEAG@Z; Details::TestForFile(ushort const *,ushort * *)
0x1800223cc  mov     ebx, eax
0x1800223ce  test    eax, eax
0x1800223d0  jns     loc_18002246F
0x1800223d6  mov     r8d, ebx
0x1800223d9  lea     rdx, aFailedToGetSet; "Failed to get set localized path with h"...
0x1800223e0  mov     ecx, 2
0x1800223e5  call    UnattendLogW
0x1800223ea  nop
0x1800223eb  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800223f2  mov     [rsp+4D0h+var_488], rax
0x1800223f7  mov     [rsp+4D0h+var_480], ebx
0x1800223fb  xorps   xmm0, xmm0
0x1800223fe  movdqu  [rsp+4D0h+var_478], xmm0
0x180022404  lea     rcx, [rsp+4D0h+var_488]; this
0x180022409  call    ?ErrorMessage@_com_error@@QEBAPEBGXZ; _com_error::ErrorMessage(void)
0x18002240e  lea     rdx, aGetsetlocalize; "GetSetLocalizedPathFailed"
0x180022415  jmp     short loc_180022456
0x180022417  mov     r8d, ebx
0x18002241a  lea     rdx, aFailedToGetSys; "Failed to get system folder path with h"...
0x180022421  mov     ecx, 1
0x180022426  call    UnattendLogW
0x18002242b  nop
0x18002242c  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180022433  mov     [rsp+4D0h+var_488], rax
0x180022438  mov     [rsp+4D0h+var_480], ebx
0x18002243c  xorps   xmm0, xmm0
0x18002243f  movdqu  [rsp+4D0h+var_478], xmm0
0x180022445  lea     rcx, [rsp+4D0h+var_488]; this
0x18002244a  call    ?ErrorMessage@_com_error@@QEBAPEBGXZ; _com_error::ErrorMessage(void)
0x18002244f  lea     rdx, aGetsystemfolde; "GetSystemFolderPathFailed"
0x180022456  mov     [rsp+4D0h+var_490], rax
0x18002245b  lea     r8, [rsp+4D0h+var_490]
0x180022460  call    ??$CoreEvent2@AEAY0BN@$$CBDAEAY0BK@$$CBGPEBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0BN@$$CBDAEAY0BK@$$CBG$$QEAPEBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent2<char const (&)[29],ushort const (&)[26],ushort const *>(char const (&)[29],ushort const (&)[26],ushort const * &&)
0x180022465  lea     rcx, [rsp+4D0h+var_488]; this
0x18002246a  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x18002246f  mov     eax, ebx
0x180022471  mov     rcx, [rbp+3D0h+var_40]
0x180022478  xor     rcx, rsp; StackCookie
0x18002247b  call    __security_check_cookie
0x180022480  mov     rbx, [rsp+4D0h+arg_18]
0x180022488  add     rsp, 4A0h
0x18002248f  pop     r15
0x180022491  pop     r14
0x180022493  pop     r13
0x180022495  pop     r12
0x180022497  pop     rdi
0x180022498  pop     rsi
0x180022499  pop     rbp
0x18002249a  retn
```
