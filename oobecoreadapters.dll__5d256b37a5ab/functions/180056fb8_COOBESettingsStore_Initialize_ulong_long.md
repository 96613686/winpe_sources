# COOBESettingsStore::Initialize(ulong,long)

- ea: `0x180056fb8`
- end: `0x180057101`
- name: `?Initialize@COOBESettingsStore@@QEAAJKJ@Z`
- size: `329`
- prototype: `__int64 __fastcall(COOBESettingsStore *__hidden this, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180056aac`

## callees

- `0x180002b60`
- `0x180007d34`
- `0x180007de0`
- `0x180056fb8`
- `0x180057510`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x180056fde`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x180056fde`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180056ff1`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180056ff1`

## string_xrefs

- `0x180056ffc`: `oobe.xml`
- `0x180057030`: `default\oobe.xml`
- `0x1800570c0`: `%li\%i\oobe.xml`
- `0x180057064`: `%li\oobe.xml`
- `0x180057090`: `default\%i\oobe.xml`

## pseudocode

```c
int __fastcall COOBESettingsStore::Initialize(struct CXMLFile **this)
{
  unsigned int UserGeoID; // esi
  unsigned int ThreadUILanguage; // edi
  size_t *v4; // r8
  int result; // eax
  COOBESettingsStore *v6; // rcx
  size_t *v7; // r8
  COOBESettingsStore *v8; // rcx
  COOBESettingsStore *v9; // rcx
  COOBESettingsStore *v10; // rcx
  COOBESettingsStore *v11; // rcx
  size_t v12; // [rsp+20h] [rbp-258h]
  size_t v13; // [rsp+20h] [rbp-258h]
  __int64 v14; // [rsp+20h] [rbp-258h]
  wchar_t pszDest[264]; // [rsp+30h] [rbp-248h] BYREF

  UserGeoID = GetUserGeoID(0x10u);
  if ( UserGeoID == -1 )
    UserGeoID = 244;
  ThreadUILanguage = GetThreadUILanguage();
  result = StringCopyWorkerW(pszDest, 0x104u, v4, L"oobe.xml", v12);
  if ( result >= 0 )
  {
    result = COOBESettingsStore::_LoadXMLFile(v6, pszDest, this + 6);
    if ( result >= 0 )
    {
      result = StringCopyWorkerW(pszDest, 0x104u, v7, L"default\\oobe.xml", v13);
      if ( result >= 0 )
      {
        result = COOBESettingsStore::_LoadXMLFile(v8, pszDest, this + 5);
        if ( result >= 0 )
        {
          result = StringCchPrintfW(pszDest, 0x104u, L"%li\\oobe.xml", UserGeoID);
          if ( result >= 0 )
          {
            result = COOBESettingsStore::_LoadXMLFile(v9, pszDest, this + 3);
            if ( result >= 0 )
            {
              result = StringCchPrintfW(pszDest, 0x104u, L"default\\%i\\oobe.xml", ThreadUILanguage);
              if ( result >= 0 )
              {
                result = COOBESettingsStore::_LoadXMLFile(v10, pszDest, this + 4);
                if ( result >= 0 )
                {
                  LODWORD(v14) = ThreadUILanguage;
                  result = StringCchPrintfW(pszDest, 0x104u, L"%li\\%i\\oobe.xml", UserGeoID, v14);
                  if ( result >= 0 )
                    return COOBESettingsStore::_LoadXMLFile(v11, pszDest, this + 2);
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180056fb8  push    rbx
0x180056fba  push    rbp
0x180056fbb  push    rsi
0x180056fbc  push    rdi
0x180056fbd  sub     rsp, 258h
0x180056fc4  mov     rax, cs:__security_cookie
0x180056fcb  xor     rax, rsp
0x180056fce  mov     [rsp+278h+var_38], rax
0x180056fd6  mov     rbx, rcx
0x180056fd9  mov     ecx, 10h; GeoClass
0x180056fde  call    cs:__imp_GetUserGeoID
0x180056fe4  mov     esi, eax
0x180056fe6  mov     eax, 0F4h
0x180056feb  cmp     esi, 0FFFFFFFFh
0x180056fee  cmovz   esi, eax
0x180056ff1  call    cs:__imp_GetThreadUILanguage
0x180056ff7  mov     ebp, 104h
0x180056ffc  lea     r9, aOobeXml; "oobe.xml"
0x180057003  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180057008  movzx   edi, ax
0x18005700b  mov     edx, ebp; cchDest
0x18005700d  call    StringCopyWorkerW
0x180057012  test    eax, eax
0x180057014  js      loc_1800570E5
0x18005701a  lea     r8, [rbx+30h]; struct CXMLFile **
0x18005701e  lea     rdx, [rsp+278h+pszDest]; unsigned __int16 *
0x180057023  call    ?_LoadXMLFile@COOBESettingsStore@@AEAAJPEBGPEAPEAVCXMLFile@@@Z; COOBESettingsStore::_LoadXMLFile(ushort const *,CXMLFile * *)
0x180057028  test    eax, eax
0x18005702a  js      loc_1800570E5
0x180057030  lea     r9, aDefaultOobeXml; "default\\oobe.xml"
0x180057037  mov     edx, ebp; cchDest
0x180057039  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18005703e  call    StringCopyWorkerW
0x180057043  test    eax, eax
0x180057045  js      loc_1800570E5
0x18005704b  lea     r8, [rbx+28h]; struct CXMLFile **
0x18005704f  lea     rdx, [rsp+278h+pszDest]; unsigned __int16 *
0x180057054  call    ?_LoadXMLFile@COOBESettingsStore@@AEAAJPEBGPEAPEAVCXMLFile@@@Z; COOBESettingsStore::_LoadXMLFile(ushort const *,CXMLFile * *)
0x180057059  test    eax, eax
0x18005705b  js      loc_1800570E5
0x180057061  mov     r9d, esi
0x180057064  lea     r8, aLiOobeXml; "%li\\oobe.xml"
0x18005706b  mov     edx, ebp; unsigned __int64
0x18005706d  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180057072  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180057077  test    eax, eax
0x180057079  js      short loc_1800570E5
0x18005707b  lea     r8, [rbx+18h]; struct CXMLFile **
0x18005707f  lea     rdx, [rsp+278h+pszDest]; unsigned __int16 *
0x180057084  call    ?_LoadXMLFile@COOBESettingsStore@@AEAAJPEBGPEAPEAVCXMLFile@@@Z; COOBESettingsStore::_LoadXMLFile(ushort const *,CXMLFile * *)
0x180057089  test    eax, eax
0x18005708b  js      short loc_1800570E5
0x18005708d  mov     r9d, edi
0x180057090  lea     r8, aDefaultIOobeXm; "default\\%i\\oobe.xml"
0x180057097  mov     edx, ebp; unsigned __int64
0x180057099  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18005709e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800570a3  test    eax, eax
0x1800570a5  js      short loc_1800570E5
0x1800570a7  lea     r8, [rbx+20h]; struct CXMLFile **
0x1800570ab  lea     rdx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800570b0  call    ?_LoadXMLFile@COOBESettingsStore@@AEAAJPEBGPEAPEAVCXMLFile@@@Z; COOBESettingsStore::_LoadXMLFile(ushort const *,CXMLFile * *)
0x1800570b5  test    eax, eax
0x1800570b7  js      short loc_1800570E5
0x1800570b9  mov     r9d, esi
0x1800570bc  mov     dword ptr [rsp+278h+var_258], edi
0x1800570c0  lea     r8, aLiIOobeXml; "%li\\%i\\oobe.xml"
0x1800570c7  mov     edx, ebp; unsigned __int64
0x1800570c9  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800570ce  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800570d3  test    eax, eax
0x1800570d5  js      short loc_1800570E5
0x1800570d7  lea     r8, [rbx+10h]; struct CXMLFile **
0x1800570db  lea     rdx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800570e0  call    ?_LoadXMLFile@COOBESettingsStore@@AEAAJPEBGPEAPEAVCXMLFile@@@Z; COOBESettingsStore::_LoadXMLFile(ushort const *,CXMLFile * *)
0x1800570e5  mov     rcx, [rsp+278h+var_38]
0x1800570ed  xor     rcx, rsp; StackCookie
0x1800570f0  call    __security_check_cookie
0x1800570f5  add     rsp, 258h
0x1800570fc  pop     rdi
0x1800570fd  pop     rsi
0x1800570fe  pop     rbp
0x1800570ff  pop     rbx
0x180057100  retn
```
