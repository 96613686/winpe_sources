# COOBESettingsStore::_LoadXMLFile(ushort const *,CXMLFile * *)

- ea: `0x1800b3a34`
- end: `0x1800b3bc9`
- name: `?_LoadXMLFile@COOBESettingsStore@@AEAAJPEBGPEAPEAVCXMLFile@@@Z`
- size: `405`
- prototype: `int(COOBESettingsStore *__hidden this, const unsigned __int16 *, struct CXMLFile **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b3878`

## callees

- `0x180003470`
- `0x180003968`
- `0x180003ffc`
- `0x18001ecec`
- `0x18001f348`
- `0x180043fc0`
- `0x1800b3358`
- `0x1800b33f8`
- `0x1800b3510`
- `0x1800b3a34`
- `0x1800b8834`
- `0x1800be0a8`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x1800b3a83`
- `SHELL32!SHGetFolderPathEx` at `0x1800b3a83`
- `SHLWAPI!PathAppendW` at `0x1800b3a9f`
- `SHLWAPI!PathAppendW` at `0x1800b3ab5`
- `SHLWAPI!PathAppendW` at `0x1800b3a9f`
- `SHLWAPI!PathAppendW` at `0x1800b3ab5`

## string_xrefs

- `0x1800b3b43`: `Failed to load oobe.xml file at %s with hr=0x%08X`
- `0x1800b3b28`: `Successfully loaded oobe.xml file at %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COOBESettingsStore::_LoadXMLFile(
        COOBESettingsStore *this,
        const unsigned __int16 *a2,
        struct CXMLFile **a3)
{
  int v5; // edi
  CXMLDOMNode *v6; // rax
  CXMLDOMNode *v7; // rbx
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
      v6 = (CXMLDOMNode *)operator new(0x220u, (const struct std::nothrow_t *)&std::nothrow);
      v7 = v6;
      v16 = (const unsigned __int16 *)v6;
      if ( v6 )
      {
        memset_0(v6, 0, 0x220u);
        CXMLDOMNode::CXMLDOMNode(v7);
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
            (__int64)pszPath,
            (__int64 *)&v16);
          _com_error::~_com_error((_com_error *)&v17);
          v5 = 1;
          CXMLFile::`scalar deleting destructor'(v7, v14);
        }
        else
        {
          *a3 = v7;
          UnattendLogW(0, L"Successfully loaded oobe.xml file at %s", pszPath);
          CloudExperienceHostCoreTelemetry::CoreEvent2<char const (&)[33],unsigned short const (&)[25],unsigned short (&)[260]>(
            v11,
            v10,
            (__int64)pszPath);
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
0x1800b3a34  mov     [rsp-8+arg_0], rbx
0x1800b3a39  push    rbp
0x1800b3a3a  push    rsi
0x1800b3a3b  push    rdi
0x1800b3a3c  lea     rbp, [rsp-180h]
0x1800b3a44  sub     rsp, 280h
0x1800b3a4b  mov     rax, cs:__security_cookie
0x1800b3a52  xor     rax, rsp
0x1800b3a55  mov     [rbp+190h+var_20], rax
0x1800b3a5c  mov     rsi, r8
0x1800b3a5f  mov     rbx, rdx
0x1800b3a62  mov     qword ptr [r8], 0
0x1800b3a69  mov     [rsp+290h+var_270], 104h
0x1800b3a71  lea     r9, [rsp+290h+pszPath]
0x1800b3a76  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b3a7a  xor     edx, edx
0x1800b3a7c  lea     rcx, FOLDERID_System
0x1800b3a83  call    cs:__imp_SHGetFolderPathEx
0x1800b3a89  mov     edi, eax
0x1800b3a8b  test    eax, eax
0x1800b3a8d  js      loc_1800B3BA5
0x1800b3a93  lea     rdx, pszMore; "oobe\\info"
0x1800b3a9a  lea     rcx, [rsp+290h+pszPath]; pszPath
0x1800b3a9f  call    cs:__imp_PathAppendW
0x1800b3aa5  test    eax, eax
0x1800b3aa7  jz      loc_1800B3BA0
0x1800b3aad  mov     rdx, rbx; pszMore
0x1800b3ab0  lea     rcx, [rsp+290h+pszPath]; pszPath
0x1800b3ab5  call    cs:__imp_PathAppendW
0x1800b3abb  test    eax, eax
0x1800b3abd  jz      loc_1800B3BA0
0x1800b3ac3  mov     edi, 8007000Eh
0x1800b3ac8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b3acf  mov     ecx, 220h; unsigned __int64
0x1800b3ad4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b3ad9  mov     rbx, rax
0x1800b3adc  mov     [rsp+290h+var_260], rax
0x1800b3ae1  test    rax, rax
0x1800b3ae4  jz      loc_1800B3BA5
0x1800b3aea  xor     edx, edx; Val
0x1800b3aec  mov     r8d, 220h; Size
0x1800b3af2  mov     rcx, rax; void *
0x1800b3af5  call    memset_0
0x1800b3afa  mov     rcx, rbx; this
0x1800b3afd  call    ??0CXMLDOMNode@@QEAA@XZ; CXMLDOMNode::CXMLDOMNode(void)
0x1800b3b02  test    rbx, rbx
0x1800b3b05  jz      loc_1800B3BA5
0x1800b3b0b  lea     rdx, [rsp+290h+pszPath]; unsigned __int16 *
0x1800b3b10  mov     rcx, rbx; this
0x1800b3b13  call    ?Open@CXMLFile@@QEAAJPEBGAEBU_GUID@@@Z; CXMLFile::Open(ushort const *,_GUID const &)
0x1800b3b18  mov     edi, eax
0x1800b3b1a  lea     r8, [rsp+290h+pszPath]
0x1800b3b1f  xor     ecx, ecx
0x1800b3b21  test    eax, eax
0x1800b3b23  js      short loc_1800B3B40
0x1800b3b25  mov     [rsi], rbx
0x1800b3b28  lea     rdx, aSuccessfullyLo; "Successfully loaded oobe.xml file at %s"
0x1800b3b2f  call    UnattendLogW
0x1800b3b34  lea     r8, [rsp+290h+pszPath]
0x1800b3b39  call    ??$CoreEvent2@AEAY0CB@$$CBDAEAY0BJ@$$CBGAEAY0BAE@G@CloudExperienceHostCoreTelemetry@@SAXAEAY0CB@$$CBDAEAY0BJ@$$CBGAEAY0BAE@G@Z; CloudExperienceHostCoreTelemetry::CoreEvent2<char const (&)[33],ushort const (&)[25],ushort (&)[260]>(char const (&)[33],ushort const (&)[25],ushort (&)[260])
0x1800b3b3e  jmp     short loc_1800B3BA5
0x1800b3b40  mov     r9d, edi
0x1800b3b43  lea     rdx, aFailedToLoadOo; "Failed to load oobe.xml file at %s with"...
0x1800b3b4a  call    UnattendLogW
0x1800b3b4f  nop
0x1800b3b50  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800b3b57  mov     [rsp+290h+var_258], rax
0x1800b3b5c  mov     [rsp+290h+var_250], edi
0x1800b3b60  xorps   xmm0, xmm0
0x1800b3b63  movdqu  [rsp+290h+var_248], xmm0
0x1800b3b69  lea     rcx, [rsp+290h+var_258]; this
0x1800b3b6e  call    ?ErrorMessage@_com_error@@QEBAPEBGXZ; _com_error::ErrorMessage(void)
0x1800b3b73  mov     [rsp+290h+var_260], rax
0x1800b3b78  lea     r9, [rsp+290h+var_260]
0x1800b3b7d  lea     r8, [rsp+290h+pszPath]
0x1800b3b82  call    ??$CoreEvent3@AEAY0CB@$$CBDAEAY0BG@$$CBGAEAY0BAE@GPEBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0CB@$$CBDAEAY0BG@$$CBGAEAY0BAE@G$$QEAPEBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent3<char const (&)[33],ushort const (&)[22],ushort (&)[260],ushort const *>(char const (&)[33],ushort const (&)[22],ushort (&)[260],ushort const * &&)
0x1800b3b87  lea     rcx, [rsp+290h+var_258]; this
0x1800b3b8c  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x1800b3b91  mov     edi, 1
0x1800b3b96  mov     rcx, rbx; this
0x1800b3b99  call    ??_GCXMLFile@@QEAAPEAXI@Z; CXMLFile::`scalar deleting destructor'(uint)
0x1800b3b9e  jmp     short loc_1800B3BA5
0x1800b3ba0  mov     edi, 8000FFFFh
0x1800b3ba5  mov     eax, edi
0x1800b3ba7  mov     rcx, [rbp+190h+var_20]
0x1800b3bae  xor     rcx, rsp; StackCookie
0x1800b3bb1  call    __security_check_cookie
0x1800b3bb6  mov     rbx, [rsp+290h+arg_0]
0x1800b3bbe  add     rsp, 280h
0x1800b3bc5  pop     rdi
0x1800b3bc6  pop     rsi
0x1800b3bc7  pop     rbp
0x1800b3bc8  retn
```
