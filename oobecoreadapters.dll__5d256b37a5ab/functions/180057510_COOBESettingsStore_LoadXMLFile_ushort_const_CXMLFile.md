# COOBESettingsStore::_LoadXMLFile(ushort const *,CXMLFile * *)

- ea: `0x180057510`
- end: `0x1800576b4`
- name: `?_LoadXMLFile@COOBESettingsStore@@AEAAJPEBGPEAPEAVCXMLFile@@@Z`
- size: `420`
- prototype: `int(COOBESettingsStore *__hidden this, const unsigned __int16 *, struct CXMLFile **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180056fb8`

## callees

- `0x180002b60`
- `0x1800036e4`
- `0x180003ffc`
- `0x180039eb4`
- `0x18003a7a0`
- `0x1800564ac`
- `0x18005654c`
- `0x1800569c0`
- `0x180057510`
- `0x180069304`
- `0x18006a9b8`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18005757b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180057591`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18005757b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180057591`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetFolderPathEx` at `0x18005755f`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetFolderPathEx` at `0x18005755f`

## string_xrefs

- `0x180057613`: `Successfully loaded oobe.xml file at %s`
- `0x18005762e`: `Failed to load oobe.xml file at %s with hr=0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COOBESettingsStore::_LoadXMLFile(
        COOBESettingsStore *this,
        const unsigned __int16 *a2,
        struct CXMLFile **a3)
{
  int v5; // edi
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rbx
  const struct _GUID *v8; // r8
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned int v14; // edx
  const unsigned __int16 *v16; // [rsp+30h] [rbp-D0h] BYREF
  void **v17; // [rsp+38h] [rbp-C8h] BYREF
  int v18; // [rsp+40h] [rbp-C0h]
  __int128 v19; // [rsp+48h] [rbp-B8h]
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF

  *a3 = 0;
  v5 = SHGetFolderPathEx(&FOLDERID_System, 0, -1, pszPath, 260);
  if ( v5 >= 0 )
  {
    if ( PathAppendW(pszPath, L"oobe\\info") && PathAppendW(pszPath, a2) )
    {
      v5 = -2147024882;
      v6 = (unsigned __int16 *)operator new(0x220u, (const struct std::nothrow_t *)&std::nothrow);
      v7 = v6;
      v16 = v6;
      if ( v6 )
      {
        memset_0(v6, 0, 0x220u);
        *(_QWORD *)v7 = 0;
        *((_QWORD *)v7 + 1) = 0;
        *((_QWORD *)v7 + 2) = 0;
        v9 = CXMLFile::Open((struct IUnknown **)v7, pszPath, v8);
        v5 = v9;
        if ( v9 < 0 )
        {
          UnattendLogW(0, L"Failed to load oobe.xml file at %s with hr=0x%08X", pszPath, (unsigned int)v9);
          v17 = &_com_error::`vftable';
          v18 = v5;
          v19 = 0;
          v16 = _com_error::ErrorMessage((_com_error *)&v17);
          CloudExperienceHostCoreTelemetry::CoreEvent3<char const (&)[33],unsigned short const (&)[22],unsigned short (&)[260],unsigned short const *>(
            v13,
            v12,
            pszPath,
            &v16);
          _com_error::~_com_error((_com_error *)&v17);
          v5 = 1;
          CXMLFile::`scalar deleting destructor'((CXMLFile *)v7, v14);
        }
        else
        {
          *a3 = (struct CXMLFile *)v7;
          UnattendLogW(0, L"Successfully loaded oobe.xml file at %s", pszPath);
          CloudExperienceHostCoreTelemetry::CoreEvent2<char const (&)[33],unsigned short const (&)[25],unsigned short (&)[260]>(
            v11,
            v10,
            pszPath);
        }
      }
    }
    else
    {
      return (unsigned int)-2147418113;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180057510  mov     [rsp-8+arg_0], rbx
0x180057515  push    rbp
0x180057516  push    rsi
0x180057517  push    rdi
0x180057518  lea     rbp, [rsp-180h]
0x180057520  sub     rsp, 280h
0x180057527  mov     rax, cs:__security_cookie
0x18005752e  xor     rax, rsp
0x180057531  mov     [rbp+190h+var_20], rax
0x180057538  mov     rsi, r8
0x18005753b  mov     rbx, rdx
0x18005753e  mov     qword ptr [r8], 0
0x180057545  mov     [rsp+290h+var_270], 104h
0x18005754d  lea     r9, [rsp+290h+pszPath]
0x180057552  or      r8, 0FFFFFFFFFFFFFFFFh
0x180057556  xor     edx, edx
0x180057558  lea     rcx, FOLDERID_System
0x18005755f  call    cs:__imp_SHGetFolderPathEx
0x180057565  mov     edi, eax
0x180057567  test    eax, eax
0x180057569  js      loc_180057690
0x18005756f  lea     rdx, aOobeInfo; "oobe\\info"
0x180057576  lea     rcx, [rsp+290h+pszPath]; pszPath
0x18005757b  call    cs:__imp_PathAppendW
0x180057581  test    eax, eax
0x180057583  jz      loc_18005768B
0x180057589  mov     rdx, rbx; pszMore
0x18005758c  lea     rcx, [rsp+290h+pszPath]; pszPath
0x180057591  call    cs:__imp_PathAppendW
0x180057597  test    eax, eax
0x180057599  jz      loc_18005768B
0x18005759f  mov     edi, 8007000Eh
0x1800575a4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800575ab  mov     ecx, 220h; unsigned __int64
0x1800575b0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800575b5  mov     rbx, rax
0x1800575b8  mov     [rsp+290h+var_260], rax
0x1800575bd  test    rax, rax
0x1800575c0  jz      loc_180057690
0x1800575c6  xor     edx, edx; Val
0x1800575c8  mov     r8d, 220h; Size
0x1800575ce  mov     rcx, rax; void *
0x1800575d1  call    memset_0
0x1800575d6  mov     qword ptr [rbx], 0
0x1800575dd  mov     qword ptr [rbx+8], 0
0x1800575e5  mov     qword ptr [rbx+10h], 0
0x1800575ed  test    rbx, rbx
0x1800575f0  jz      loc_180057690
0x1800575f6  lea     rdx, [rsp+290h+pszPath]; pszSrc
0x1800575fb  mov     rcx, rbx; this
0x1800575fe  call    ?Open@CXMLFile@@QEAAJPEBGAEBU_GUID@@@Z; CXMLFile::Open(ushort const *,_GUID const &)
0x180057603  mov     edi, eax
0x180057605  lea     r8, [rsp+290h+pszPath]
0x18005760a  xor     ecx, ecx
0x18005760c  test    eax, eax
0x18005760e  js      short loc_18005762B
0x180057610  mov     [rsi], rbx
0x180057613  lea     rdx, aSuccessfullyLo; "Successfully loaded oobe.xml file at %s"
0x18005761a  call    UnattendLogW
0x18005761f  lea     r8, [rsp+290h+pszPath]
0x180057624  call    ??$CoreEvent2@AEAY0CB@$$CBDAEAY0BJ@$$CBGAEAY0BAE@G@CloudExperienceHostCoreTelemetry@@SAXAEAY0CB@$$CBDAEAY0BJ@$$CBGAEAY0BAE@G@Z; CloudExperienceHostCoreTelemetry::CoreEvent2<char const (&)[33],ushort const (&)[25],ushort (&)[260]>(char const (&)[33],ushort const (&)[25],ushort (&)[260])
0x180057629  jmp     short loc_180057690
0x18005762b  mov     r9d, edi
0x18005762e  lea     rdx, aFailedToLoadOo; "Failed to load oobe.xml file at %s with"...
0x180057635  call    UnattendLogW
0x18005763a  nop
0x18005763b  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180057642  mov     [rsp+290h+var_258], rax
0x180057647  mov     [rsp+290h+var_250], edi
0x18005764b  xorps   xmm0, xmm0
0x18005764e  movdqu  [rsp+290h+var_248], xmm0
0x180057654  lea     rcx, [rsp+290h+var_258]; this
0x180057659  call    ?ErrorMessage@_com_error@@QEBAPEBGXZ; _com_error::ErrorMessage(void)
0x18005765e  mov     [rsp+290h+var_260], rax
0x180057663  lea     r9, [rsp+290h+var_260]
0x180057668  lea     r8, [rsp+290h+pszPath]
0x18005766d  call    ??$CoreEvent3@AEAY0CB@$$CBDAEAY0BG@$$CBGAEAY0BAE@GPEBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0CB@$$CBDAEAY0BG@$$CBGAEAY0BAE@G$$QEAPEBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent3<char const (&)[33],ushort const (&)[22],ushort (&)[260],ushort const *>(char const (&)[33],ushort const (&)[22],ushort (&)[260],ushort const * &&)
0x180057672  lea     rcx, [rsp+290h+var_258]; this
0x180057677  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x18005767c  mov     edi, 1
0x180057681  mov     rcx, rbx; this
0x180057684  call    ??_GCXMLFile@@QEAAPEAXI@Z; CXMLFile::`scalar deleting destructor'(uint)
0x180057689  jmp     short loc_180057690
0x18005768b  mov     edi, 8000FFFFh
0x180057690  mov     eax, edi
0x180057692  mov     rcx, [rbp+190h+var_20]
0x180057699  xor     rcx, rsp; StackCookie
0x18005769c  call    __security_check_cookie
0x1800576a1  mov     rbx, [rsp+290h+arg_0]
0x1800576a9  add     rsp, 280h
0x1800576b0  pop     rdi
0x1800576b1  pop     rsi
0x1800576b2  pop     rbp
0x1800576b3  retn
```
