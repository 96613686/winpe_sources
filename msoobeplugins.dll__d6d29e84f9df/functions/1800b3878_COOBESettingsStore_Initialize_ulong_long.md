# COOBESettingsStore::Initialize(ulong,long)

- ea: `0x1800b3878`
- end: `0x1800b39c1`
- name: `?Initialize@COOBESettingsStore@@QEAAJKJ@Z`
- size: `329`
- prototype: `__int64 __fastcall(COOBESettingsStore *__hidden this, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800b3c08`

## callees

- `0x180003470`
- `0x180008b54`
- `0x180008b98`
- `0x1800b3878`
- `0x1800b3a34`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x1800b38b1`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x1800b38b1`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x1800b389e`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x1800b389e`

## string_xrefs

- `0x1800b38bc`: `oobe.xml`
- `0x1800b3924`: `%li\oobe.xml`
- `0x1800b38f0`: `default\oobe.xml`
- `0x1800b3980`: `%li\%i\oobe.xml`
- `0x1800b3950`: `default\%i\oobe.xml`

## pseudocode

```c
int __fastcall COOBESettingsStore::Initialize(struct CXMLFile **this)
{
  unsigned int UserGeoID; // esi
  unsigned int ThreadUILanguage; // edi
  int result; // eax
  COOBESettingsStore *v5; // rcx
  COOBESettingsStore *v6; // rcx
  COOBESettingsStore *v7; // rcx
  COOBESettingsStore *v8; // rcx
  COOBESettingsStore *v9; // rcx
  unsigned __int16 v10[264]; // [rsp+30h] [rbp-248h] BYREF

  UserGeoID = GetUserGeoID(0x10u);
  if ( UserGeoID == -1 )
    UserGeoID = 244;
  ThreadUILanguage = GetThreadUILanguage();
  result = StringCchCopyW(v10, 0x104u, L"oobe.xml");
  if ( result >= 0 )
  {
    result = COOBESettingsStore::_LoadXMLFile(v5, v10, this + 6);
    if ( result >= 0 )
    {
      result = StringCchCopyW(v10, 0x104u, L"default\\oobe.xml");
      if ( result >= 0 )
      {
        result = COOBESettingsStore::_LoadXMLFile(v6, v10, this + 5);
        if ( result >= 0 )
        {
          result = StringCchPrintfW(v10, 0x104u, L"%li\\oobe.xml", UserGeoID);
          if ( result >= 0 )
          {
            result = COOBESettingsStore::_LoadXMLFile(v7, v10, this + 3);
            if ( result >= 0 )
            {
              result = StringCchPrintfW(v10, 0x104u, L"default\\%i\\oobe.xml", ThreadUILanguage);
              if ( result >= 0 )
              {
                result = COOBESettingsStore::_LoadXMLFile(v8, v10, this + 4);
                if ( result >= 0 )
                {
                  result = StringCchPrintfW(v10, 0x104u, L"%li\\%i\\oobe.xml", UserGeoID, ThreadUILanguage);
                  if ( result >= 0 )
                    return COOBESettingsStore::_LoadXMLFile(v9, v10, this + 2);
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
0x1800b3878  push    rbx
0x1800b387a  push    rbp
0x1800b387b  push    rsi
0x1800b387c  push    rdi
0x1800b387d  sub     rsp, 258h
0x1800b3884  mov     rax, cs:__security_cookie
0x1800b388b  xor     rax, rsp
0x1800b388e  mov     [rsp+278h+var_38], rax
0x1800b3896  mov     rbx, rcx
0x1800b3899  mov     ecx, 10h; GeoClass
0x1800b389e  call    cs:__imp_GetUserGeoID
0x1800b38a4  mov     esi, eax
0x1800b38a6  mov     eax, 0F4h
0x1800b38ab  cmp     esi, 0FFFFFFFFh
0x1800b38ae  cmovz   esi, eax
0x1800b38b1  call    cs:__imp_GetThreadUILanguage
0x1800b38b7  mov     ebp, 104h
0x1800b38bc  lea     r8, aOobeXml; "oobe.xml"
0x1800b38c3  lea     rcx, [rsp+278h+var_248]; unsigned __int16 *
0x1800b38c8  movzx   edi, ax
0x1800b38cb  mov     edx, ebp; unsigned __int64
0x1800b38cd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b38d2  test    eax, eax
0x1800b38d4  js      loc_1800B39A5
0x1800b38da  lea     r8, [rbx+30h]; struct CXMLFile **
0x1800b38de  lea     rdx, [rsp+278h+var_248]; unsigned __int16 *
0x1800b38e3  call    ?_LoadXMLFile@COOBESettingsStore@@AEAAJPEBGPEAPEAVCXMLFile@@@Z; COOBESettingsStore::_LoadXMLFile(ushort const *,CXMLFile * *)
0x1800b38e8  test    eax, eax
0x1800b38ea  js      loc_1800B39A5
0x1800b38f0  lea     r8, aDefaultOobeXml; "default\\oobe.xml"
0x1800b38f7  mov     edx, ebp; unsigned __int64
0x1800b38f9  lea     rcx, [rsp+278h+var_248]; unsigned __int16 *
0x1800b38fe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b3903  test    eax, eax
0x1800b3905  js      loc_1800B39A5
0x1800b390b  lea     r8, [rbx+28h]; struct CXMLFile **
0x1800b390f  lea     rdx, [rsp+278h+var_248]; unsigned __int16 *
0x1800b3914  call    ?_LoadXMLFile@COOBESettingsStore@@AEAAJPEBGPEAPEAVCXMLFile@@@Z; COOBESettingsStore::_LoadXMLFile(ushort const *,CXMLFile * *)
0x1800b3919  test    eax, eax
0x1800b391b  js      loc_1800B39A5
0x1800b3921  mov     r9d, esi
0x1800b3924  lea     r8, aLiOobeXml; "%li\\oobe.xml"
0x1800b392b  mov     edx, ebp; unsigned __int64
0x1800b392d  lea     rcx, [rsp+278h+var_248]; unsigned __int16 *
0x1800b3932  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b3937  test    eax, eax
0x1800b3939  js      short loc_1800B39A5
0x1800b393b  lea     r8, [rbx+18h]; struct CXMLFile **
0x1800b393f  lea     rdx, [rsp+278h+var_248]; unsigned __int16 *
0x1800b3944  call    ?_LoadXMLFile@COOBESettingsStore@@AEAAJPEBGPEAPEAVCXMLFile@@@Z; COOBESettingsStore::_LoadXMLFile(ushort const *,CXMLFile * *)
0x1800b3949  test    eax, eax
0x1800b394b  js      short loc_1800B39A5
0x1800b394d  mov     r9d, edi
0x1800b3950  lea     r8, aDefaultIOobeXm; "default\\%i\\oobe.xml"
0x1800b3957  mov     edx, ebp; unsigned __int64
0x1800b3959  lea     rcx, [rsp+278h+var_248]; unsigned __int16 *
0x1800b395e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b3963  test    eax, eax
0x1800b3965  js      short loc_1800B39A5
0x1800b3967  lea     r8, [rbx+20h]; struct CXMLFile **
0x1800b396b  lea     rdx, [rsp+278h+var_248]; unsigned __int16 *
0x1800b3970  call    ?_LoadXMLFile@COOBESettingsStore@@AEAAJPEBGPEAPEAVCXMLFile@@@Z; COOBESettingsStore::_LoadXMLFile(ushort const *,CXMLFile * *)
0x1800b3975  test    eax, eax
0x1800b3977  js      short loc_1800B39A5
0x1800b3979  mov     r9d, esi
0x1800b397c  mov     [rsp+278h+var_258], edi
0x1800b3980  lea     r8, aLiIOobeXml; "%li\\%i\\oobe.xml"
0x1800b3987  mov     edx, ebp; unsigned __int64
0x1800b3989  lea     rcx, [rsp+278h+var_248]; unsigned __int16 *
0x1800b398e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b3993  test    eax, eax
0x1800b3995  js      short loc_1800B39A5
0x1800b3997  lea     r8, [rbx+10h]; struct CXMLFile **
0x1800b399b  lea     rdx, [rsp+278h+var_248]; unsigned __int16 *
0x1800b39a0  call    ?_LoadXMLFile@COOBESettingsStore@@AEAAJPEBGPEAPEAVCXMLFile@@@Z; COOBESettingsStore::_LoadXMLFile(ushort const *,CXMLFile * *)
0x1800b39a5  mov     rcx, [rsp+278h+var_38]
0x1800b39ad  xor     rcx, rsp; StackCookie
0x1800b39b0  call    __security_check_cookie
0x1800b39b5  add     rsp, 258h
0x1800b39bc  pop     rdi
0x1800b39bd  pop     rsi
0x1800b39be  pop     rbp
0x1800b39bf  pop     rbx
0x1800b39c0  retn
```
