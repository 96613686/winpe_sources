# TestForOOBEInfoFileLocalized(ushort const *,ushort,ushort * *)

- ea: `0x1800455ac`
- end: `0x18004586f`
- name: `?TestForOOBEInfoFileLocalized@@YAJPEBGGPEAPEAG@Z`
- size: `707`
- prototype: `int(const unsigned __int16 *, unsigned __int16, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180039ef8`

## callees

- `0x180002b60`
- `0x180007d34`
- `0x180038d14`
- `0x180038da0`
- `0x180039eb4`
- `0x18003a7a0`
- `0x180045528`
- `0x1800455ac`
- `0x180069304`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x1800455f1`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x1800455f1`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetFolderPathEx` at `0x18004564b`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetFolderPathEx` at `0x18004564b`

## string_xrefs

- `0x1800457ad`: `Failed to get set localized path with hr=0x%08X`
- `0x1800457ee`: `Failed to get system folder path with hr=0x%08X`
- `0x1800457e2`: `GetSetLocalizedPathFailed`
- `0x180045823`: `GetSystemFolderPathFailed`

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
0x1800455ac  mov     [rsp-8+arg_18], rbx
0x1800455b1  push    rbp
0x1800455b2  push    rsi
0x1800455b3  push    rdi
0x1800455b4  push    r12
0x1800455b6  push    r13
0x1800455b8  push    r14
0x1800455ba  push    r15
0x1800455bc  lea     rbp, [rsp-3A0h]
0x1800455c4  sub     rsp, 4A0h
0x1800455cb  mov     rax, cs:__security_cookie
0x1800455d2  xor     rax, rsp
0x1800455d5  mov     [rbp+3D0h+var_40], rax
0x1800455dc  mov     rdi, r8
0x1800455df  movzx   esi, dx
0x1800455e2  mov     r14, rcx
0x1800455e5  mov     qword ptr [r8], 0
0x1800455ec  mov     ecx, 10h; GeoClass
0x1800455f1  call    cs:__imp_GetUserGeoID
0x1800455f7  mov     r15d, eax
0x1800455fa  mov     eax, 0F4h
0x1800455ff  cmp     r15d, 0FFFFFFFFh
0x180045603  cmovz   r15d, eax
0x180045607  mov     r13d, 0FFFFh
0x18004560d  cmp     si, r13w
0x180045611  jnz     short loc_180045629
0x180045613  lea     rdx, aLanguageIdNotS; "Language ID not set.  Unable to search "...
0x18004561a  mov     ecx, 2
0x18004561f  call    UnattendLogW
0x180045624  call    ??$CoreEvent1@AEAY0BN@$$CBDAEAY0BE@$$CBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0BN@$$CBDAEAY0BE@$$CBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[29],ushort const (&)[20]>(char const (&)[29],ushort const (&)[20])
0x180045629  mov     r12d, 104h
0x18004562f  mov     dword ptr [rsp+4D0h+var_4B0], r12d
0x180045634  lea     r9, [rbp+3D0h+var_250]
0x18004563b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004563f  mov     edx, 4000h
0x180045644  lea     rcx, FOLDERID_System
0x18004564b  call    cs:__imp_SHGetFolderPathEx
0x180045651  mov     ebx, eax
0x180045653  test    eax, eax
0x180045655  js      loc_1800457EB
0x18004565b  cmp     si, r13w
0x18004565f  jz      short loc_1800456A5
0x180045661  mov     [rsp+4D0h+var_4A0], r14
0x180045666  mov     dword ptr [rsp+4D0h+var_4A8], esi
0x18004566a  mov     dword ptr [rsp+4D0h+var_4B0], r15d
0x18004566f  lea     r9, [rbp+3D0h+var_250]
0x180045676  lea     r8, aSOobeInfoLiIS; "%s\\oobe\\info\\%li\\%i\\%s"
0x18004567d  mov     edx, r12d; unsigned __int64
0x180045680  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x180045685  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004568a  test    eax, eax
0x18004568c  js      short loc_1800456A5
0x18004568e  mov     rdx, rdi; unsigned __int16 **
0x180045691  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x180045696  call    ?TestForFile@Details@@YAJPEBGPEAPEAG@Z; Details::TestForFile(ushort const *,ushort * *)
0x18004569b  mov     ebx, eax
0x18004569d  test    eax, eax
0x18004569f  jns     loc_180045843
0x1800456a5  mov     [rsp+4D0h+var_4A8], r14
0x1800456aa  mov     dword ptr [rsp+4D0h+var_4B0], r15d
0x1800456af  lea     r9, [rbp+3D0h+var_250]
0x1800456b6  lea     r8, aSOobeInfoLiS; "%s\\oobe\\info\\%li\\%s"
0x1800456bd  mov     rdx, r12; unsigned __int64
0x1800456c0  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x1800456c5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800456ca  mov     ebx, eax
0x1800456cc  test    eax, eax
0x1800456ce  js      loc_1800457AA
0x1800456d4  mov     rdx, rdi; unsigned __int16 **
0x1800456d7  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x1800456dc  call    ?TestForFile@Details@@YAJPEBGPEAPEAG@Z; Details::TestForFile(ushort const *,ushort * *)
0x1800456e1  mov     ebx, eax
0x1800456e3  test    eax, eax
0x1800456e5  jns     loc_180045843
0x1800456eb  cmp     si, r13w
0x1800456ef  jz      short loc_180045730
0x1800456f1  mov     [rsp+4D0h+var_4A8], r14
0x1800456f6  mov     dword ptr [rsp+4D0h+var_4B0], esi
0x1800456fa  lea     r9, [rbp+3D0h+var_250]
0x180045701  lea     r8, aSOobeInfoDefau_0; "%s\\oobe\\info\\default\\%i\\%s"
0x180045708  mov     rdx, r12; unsigned __int64
0x18004570b  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x180045710  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180045715  test    eax, eax
0x180045717  js      short loc_180045730
0x180045719  mov     rdx, rdi; unsigned __int16 **
0x18004571c  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x180045721  call    ?TestForFile@Details@@YAJPEBGPEAPEAG@Z; Details::TestForFile(ushort const *,ushort * *)
0x180045726  mov     ebx, eax
0x180045728  test    eax, eax
0x18004572a  jns     loc_180045843
0x180045730  mov     [rsp+4D0h+var_4B0], r14
0x180045735  lea     r9, [rbp+3D0h+var_250]
0x18004573c  lea     r8, aSOobeInfoDefau; "%s\\oobe\\info\\default\\%s"
0x180045743  mov     rdx, r12; unsigned __int64
0x180045746  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x18004574b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180045750  mov     ebx, eax
0x180045752  test    eax, eax
0x180045754  js      short loc_1800457AA
0x180045756  mov     rdx, rdi; unsigned __int16 **
0x180045759  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x18004575e  call    ?TestForFile@Details@@YAJPEBGPEAPEAG@Z; Details::TestForFile(ushort const *,ushort * *)
0x180045763  mov     ebx, eax
0x180045765  test    eax, eax
0x180045767  jns     loc_180045843
0x18004576d  mov     [rsp+4D0h+var_4B0], r14
0x180045772  lea     r9, [rbp+3D0h+var_250]
0x180045779  lea     r8, aSOobeInfoS; "%s\\oobe\\info\\%s"
0x180045780  mov     rdx, r12; unsigned __int64
0x180045783  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x180045788  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004578d  mov     ebx, eax
0x18004578f  test    eax, eax
0x180045791  js      short loc_1800457AA
0x180045793  mov     rdx, rdi; unsigned __int16 **
0x180045796  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x18004579b  call    ?TestForFile@Details@@YAJPEBGPEAPEAG@Z; Details::TestForFile(ushort const *,ushort * *)
0x1800457a0  mov     ebx, eax
0x1800457a2  test    eax, eax
0x1800457a4  jns     loc_180045843
0x1800457aa  mov     r8d, ebx
0x1800457ad  lea     rdx, aFailedToGetSet; "Failed to get set localized path with h"...
0x1800457b4  mov     ecx, 2
0x1800457b9  call    UnattendLogW
0x1800457be  nop
0x1800457bf  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800457c6  mov     [rsp+4D0h+var_488], rax
0x1800457cb  mov     [rsp+4D0h+var_480], ebx
0x1800457cf  xorps   xmm0, xmm0
0x1800457d2  movdqu  [rsp+4D0h+var_478], xmm0
0x1800457d8  lea     rcx, [rsp+4D0h+var_488]; this
0x1800457dd  call    ?ErrorMessage@_com_error@@QEBAPEBGXZ; _com_error::ErrorMessage(void)
0x1800457e2  lea     rdx, aGetsetlocalize; "GetSetLocalizedPathFailed"
0x1800457e9  jmp     short loc_18004582A
0x1800457eb  mov     r8d, ebx
0x1800457ee  lea     rdx, aFailedToGetSys; "Failed to get system folder path with h"...
0x1800457f5  mov     ecx, 1
0x1800457fa  call    UnattendLogW
0x1800457ff  nop
0x180045800  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180045807  mov     [rsp+4D0h+var_488], rax
0x18004580c  mov     [rsp+4D0h+var_480], ebx
0x180045810  xorps   xmm0, xmm0
0x180045813  movdqu  [rsp+4D0h+var_478], xmm0
0x180045819  lea     rcx, [rsp+4D0h+var_488]; this
0x18004581e  call    ?ErrorMessage@_com_error@@QEBAPEBGXZ; _com_error::ErrorMessage(void)
0x180045823  lea     rdx, aGetsystemfolde; "GetSystemFolderPathFailed"
0x18004582a  mov     [rsp+4D0h+var_490], rax
0x18004582f  lea     r8, [rsp+4D0h+var_490]
0x180045834  call    ??$CoreEvent2@AEAY0BN@$$CBDAEAY0BK@$$CBGPEBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0BN@$$CBDAEAY0BK@$$CBG$$QEAPEBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent2<char const (&)[29],ushort const (&)[26],ushort const *>(char const (&)[29],ushort const (&)[26],ushort const * &&)
0x180045839  lea     rcx, [rsp+4D0h+var_488]; this
0x18004583e  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x180045843  mov     eax, ebx
0x180045845  mov     rcx, [rbp+3D0h+var_40]
0x18004584c  xor     rcx, rsp; StackCookie
0x18004584f  call    __security_check_cookie
0x180045854  mov     rbx, [rsp+4D0h+arg_18]
0x18004585c  add     rsp, 4A0h
0x180045863  pop     r15
0x180045865  pop     r14
0x180045867  pop     r13
0x180045869  pop     r12
0x18004586b  pop     rdi
0x18004586c  pop     rsi
0x18004586d  pop     rbp
0x18004586e  retn
```
