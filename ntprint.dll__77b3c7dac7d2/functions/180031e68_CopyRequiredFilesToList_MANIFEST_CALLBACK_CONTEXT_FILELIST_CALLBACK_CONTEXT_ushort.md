# CopyRequiredFilesToList(_MANIFEST_CALLBACK_CONTEXT *,_FILELIST_CALLBACK_CONTEXT *,ushort *)

- ea: `0x180031e68`
- end: `0x180032162`
- name: `?CopyRequiredFilesToList@@YAJPEAU_MANIFEST_CALLBACK_CONTEXT@@PEAU_FILELIST_CALLBACK_CONTEXT@@PEAG@Z`
- size: `762`
- prototype: `__int64 __fastcall(struct _MANIFEST_CALLBACK_CONTEXT *, struct _FILELIST_CALLBACK_CONTEXT *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x180033398`

## callees

- `0x180002300`
- `0x180007944`
- `0x18000d290`
- `0x18000d57c`
- `0x180023eb4`
- `0x180026498`
- `0x1800318d8`
- `0x180031e68`
- `0x180032210`
- `0x180033e28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031f26`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031f3a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031f54`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031f68`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031f7c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031f26`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031f3a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031f54`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031f68`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031f7c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180031edb`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180031f08`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003204b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180031edb`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180031f08`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003204b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180031fb3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180031fb3`

## string_xrefs

- `0x180032076`: `CopyRequiredFilesToList`
- `0x18003206c`: `Error while copying required file '%ws' to dependent files list: hr: 0x%x`
- `0x1800320d3`: `ntprint4|V3HostingFilter-pipelineconfig.xml`
- `0x180031f5e`: `Unires.dll`
- `0x180031f72`: `xpssvcs.dll`
- `0x180031f30`: `V3HostingFilter-pipelineconfig.xml`
- `0x1800320aa`: `ntprint4|V3HostingFilter.dll`
- `0x180031f1c`: `V3HostingFilter.dll`
- `0x180032125`: `ntprint|unires.dll`

## pseudocode

```c
__int64 __fastcall CopyRequiredFilesToList(
        const WCHAR *a1,
        struct _FILELIST_CALLBACK_CONTEXT *a2,
        unsigned __int16 *a3)
{
  int StringFromManifest; // esi
  unsigned __int16 *v6; // r14
  unsigned __int16 *v7; // rax
  const unsigned __int16 *v8; // r14
  DWORD FileAttributesW; // eax
  __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  unsigned __int16 *v12; // rcx
  NCoreLibrary::TString *v13; // rcx
  NCoreLibrary::TString *v14; // rcx
  __int64 result; // rax
  wchar_t *Context; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpFileName; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t String[784]; // [rsp+40h] [rbp-C0h] BYREF

  StringFromManifest = GetStringFromManifest(L"RequiredFiles", String, 0x30Cu, a1 + 1);
  if ( StringFromManifest >= 0 )
  {
    Context = 0;
    v6 = wcstok_s(String, L",", &Context);
    while ( v6 )
    {
      v7 = StripWhitespaceAndQuotes(v6);
      v8 = v7;
      if ( !*v7
        || *((_BYTE *)a2 + 42)
        && (!(unsigned int)_o__wcsicmp(v7, L"V3HostingFilter.dll")
         || !(unsigned int)_o__wcsicmp(v8, L"V3HostingFilter-pipelineconfig.xml"))
        || *((_BYTE *)a2 + 43)
        && (!(unsigned int)_o__wcsicmp(v8, L"StdNames.gpd") || !(unsigned int)_o__wcsicmp(v8, L"Unires.dll"))
        || !(unsigned int)_o__wcsicmp(v8, L"xpssvcs.dll") )
      {
        v6 = wcstok_s(0, L",", &Context);
        continue;
      }
      NCoreLibrary::TString::TString((NCoreLibrary::TString *)&lpFileName, (const unsigned __int16 *)a2 + 576);
      StringFromManifest = NCoreLibrary::TString::Cat((NCoreLibrary::TString *)&lpFileName, v8);
      if ( StringFromManifest >= 0 )
      {
        FileAttributesW = GetFileAttributesW(lpFileName);
        v10 = *((_QWORD *)a2 + 8);
        v11 = *((unsigned int *)a2 + 12) - v10;
        v12 = &a3[v10];
        if ( FileAttributesW == -1 )
        {
          StringFromManifest = StringCchCopyW(v12, v11, L"ntprint4|");
          if ( StringFromManifest < 0 )
            goto LABEL_19;
          *((_QWORD *)a2 + 8) += 9LL;
        }
        else
        {
          StringFromManifest = StringCchCopyW(v12, v11, L"ntprint|");
          if ( StringFromManifest < 0 )
            goto LABEL_19;
          *((_QWORD *)a2 + 8) += 8LL;
        }
        StringFromManifest = StringCchCopyW(
                               &a3[*((_QWORD *)a2 + 8)],
                               *((unsigned int *)a2 + 12) - *((_QWORD *)a2 + 8),
                               v8);
      }
LABEL_19:
      v18 = 0;
      if ( StringFromManifest < 0 || (StringFromManifest = StringCchLengthW(v8, 0x104u, &v18), StringFromManifest < 0) )
      {
        ClassInstallerTelemetry::WriteDbgTraceError(
          "CopyRequiredFilesToList",
          L"Error while copying required file '%ws' to dependent files list: hr: 0x%x",
          v8,
          (unsigned int)StringFromManifest);
        NCoreLibrary::TString::vFree(v14, (void *)lpFileName);
        break;
      }
      *((_QWORD *)a2 + 8) += v18 + 1;
      v6 = wcstok_s(0, L",", &Context);
      NCoreLibrary::TString::vFree(v13, (void *)lpFileName);
    }
  }
  result = 0;
  if ( StringFromManifest != -2147024894 )
    result = (unsigned int)StringFromManifest;
  if ( (int)result >= 0 )
  {
    if ( *((_BYTE *)a2 + 42) )
    {
      result = StringCchCopyW(
                 &a3[*((_QWORD *)a2 + 8)],
                 *((unsigned int *)a2 + 12) - *((_QWORD *)a2 + 8),
                 L"ntprint4|V3HostingFilter.dll");
      *((_QWORD *)a2 + 8) += 29LL;
      if ( (int)result < 0 )
        return result;
      if ( *((_BYTE *)a2 + 42) )
      {
        result = StringCchCopyW(
                   &a3[*((_QWORD *)a2 + 8)],
                   *((unsigned int *)a2 + 12) - *((_QWORD *)a2 + 8),
                   L"ntprint4|V3HostingFilter-pipelineconfig.xml");
        *((_QWORD *)a2 + 8) += 44LL;
      }
    }
    if ( (int)result >= 0 )
    {
      if ( *((_BYTE *)a2 + 43) )
      {
        result = StringCchCopyW(
                   &a3[*((_QWORD *)a2 + 8)],
                   *((unsigned int *)a2 + 12) - *((_QWORD *)a2 + 8),
                   L"ntprint|StdNames.gpd");
        *((_QWORD *)a2 + 8) += 21LL;
        if ( (int)result >= 0 )
        {
          if ( *((_BYTE *)a2 + 43) )
          {
            result = StringCchCopyW(
                       &a3[*((_QWORD *)a2 + 8)],
                       *((unsigned int *)a2 + 12) - *((_QWORD *)a2 + 8),
                       L"ntprint|unires.dll");
            *((_QWORD *)a2 + 8) += 19LL;
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
0x180031e68  push    rbp
0x180031e6a  push    rsi
0x180031e6b  push    rdi
0x180031e6c  push    r12
0x180031e6e  push    r13
0x180031e70  push    r14
0x180031e72  push    r15
0x180031e74  lea     rbp, [rsp-570h]
0x180031e7c  sub     rsp, 670h
0x180031e83  mov     rax, cs:__security_cookie
0x180031e8a  xor     rax, rsp
0x180031e8d  mov     [rbp+5A0h+var_40], rax
0x180031e94  mov     r15, r8
0x180031e97  lea     r9, [rcx+2]; lpFileName
0x180031e9b  mov     rdi, rdx
0x180031e9e  lea     rcx, aRequiredfiles; "RequiredFiles"
0x180031ea5  mov     r8d, 30Ch; nSize
0x180031eab  lea     rdx, [rsp+6A0h+String]; lpReturnedString
0x180031eb0  call    ?GetStringFromManifest@@YAJPEBGPEAGK0@Z; GetStringFromManifest(ushort const *,ushort *,ulong,ushort const *)
0x180031eb5  xor     r12d, r12d
0x180031eb8  mov     esi, eax
0x180031eba  test    eax, eax
0x180031ebc  js      loc_18003208C
0x180031ec2  lea     r13, Delimiter; ","
0x180031ec9  mov     [rsp+6A0h+Context], r12
0x180031ece  mov     rdx, r13; Delimiter
0x180031ed1  lea     r8, [rsp+6A0h+Context]; Context
0x180031ed6  lea     rcx, [rsp+6A0h+String]; String
0x180031edb  call    cs:__imp_wcstok_s
0x180031ee1  mov     r14, rax
0x180031ee4  test    rax, rax
0x180031ee7  jz      loc_18003208C
0x180031eed  mov     rcx, r14; unsigned __int16 *
0x180031ef0  call    ?StripWhitespaceAndQuotes@@YAPEAGPEAG@Z; StripWhitespaceAndQuotes(ushort *)
0x180031ef5  mov     r14, rax
0x180031ef8  cmp     [rax], r12w
0x180031efc  jnz     short loc_180031F16
0x180031efe  lea     r8, [rsp+6A0h+Context]; Context
0x180031f03  mov     rdx, r13; Delimiter
0x180031f06  xor     ecx, ecx; String
0x180031f08  call    cs:__imp_wcstok_s
0x180031f0e  mov     r14, rax
0x180031f11  jmp     loc_18003205E
0x180031f16  cmp     [rdi+2Ah], r12b
0x180031f1a  jz      short loc_180031F44
0x180031f1c  lea     rdx, aV3hostingfilte; "V3HostingFilter.dll"
0x180031f23  mov     rcx, r14
0x180031f26  call    cs:__imp__o__wcsicmp
0x180031f2c  test    eax, eax
0x180031f2e  jz      short loc_180031EFE
0x180031f30  lea     rdx, aV3hostingfilte_0; "V3HostingFilter-pipelineconfig.xml"
0x180031f37  mov     rcx, r14
0x180031f3a  call    cs:__imp__o__wcsicmp
0x180031f40  test    eax, eax
0x180031f42  jz      short loc_180031EFE
0x180031f44  cmp     [rdi+2Bh], r12b
0x180031f48  jz      short loc_180031F72
0x180031f4a  lea     rdx, aStdnamesGpd; "StdNames.gpd"
0x180031f51  mov     rcx, r14
0x180031f54  call    cs:__imp__o__wcsicmp
0x180031f5a  test    eax, eax
0x180031f5c  jz      short loc_180031EFE
0x180031f5e  lea     rdx, aUniresDll; "Unires.dll"
0x180031f65  mov     rcx, r14
0x180031f68  call    cs:__imp__o__wcsicmp
0x180031f6e  test    eax, eax
0x180031f70  jz      short loc_180031EFE
0x180031f72  lea     rdx, aXpssvcsDll; "xpssvcs.dll"
0x180031f79  mov     rcx, r14
0x180031f7c  call    cs:__imp__o__wcsicmp
0x180031f82  test    eax, eax
0x180031f84  jz      loc_180031EFE
0x180031f8a  lea     rdx, [rdi+480h]; unsigned __int16 *
0x180031f91  lea     rcx, [rsp+6A0h+lpFileName]; this
0x180031f96  call    ??0TString@NCoreLibrary@@QEAA@PEBG@Z; NCoreLibrary::TString::TString(ushort const *)
0x180031f9b  mov     rdx, r14; unsigned __int16 *
0x180031f9e  lea     rcx, [rsp+6A0h+lpFileName]; this
0x180031fa3  call    ?Cat@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Cat(ushort const *)
0x180031fa8  mov     esi, eax
0x180031faa  test    eax, eax
0x180031fac  js      short loc_180032014
0x180031fae  mov     rcx, [rsp+6A0h+lpFileName]; lpFileName
0x180031fb3  call    cs:__imp_GetFileAttributesW
0x180031fb9  mov     rcx, [rdi+40h]
0x180031fbd  mov     edx, [rdi+30h]
0x180031fc0  sub     rdx, rcx; unsigned __int64
0x180031fc3  lea     rcx, [r15+rcx*2]; unsigned __int16 *
0x180031fc7  cmp     eax, 0FFFFFFFFh
0x180031fca  jz      short loc_180031FE5
0x180031fcc  lea     r8, aNtprint; "ntprint|"
0x180031fd3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031fd8  mov     esi, eax
0x180031fda  test    eax, eax
0x180031fdc  js      short loc_180032014
0x180031fde  add     qword ptr [rdi+40h], 8
0x180031fe3  jmp     short loc_180031FFC
0x180031fe5  lea     r8, aNtprint4; "ntprint4|"
0x180031fec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031ff1  mov     esi, eax
0x180031ff3  test    eax, eax
0x180031ff5  js      short loc_180032014
0x180031ff7  add     qword ptr [rdi+40h], 9
0x180031ffc  mov     rax, [rdi+40h]
0x180032000  mov     r8, r14; unsigned __int16 *
0x180032003  mov     edx, [rdi+30h]
0x180032006  sub     rdx, rax; unsigned __int64
0x180032009  lea     rcx, [r15+rax*2]; unsigned __int16 *
0x18003200d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180032012  mov     esi, eax
0x180032014  mov     [rsp+6A0h+var_670], r12
0x180032019  test    esi, esi
0x18003201b  js      short loc_180032069
0x18003201d  lea     r8, [rsp+6A0h+var_670]; unsigned __int64 *
0x180032022  mov     edx, 104h; unsigned __int64
0x180032027  mov     rcx, r14; unsigned __int16 *
0x18003202a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003202f  mov     esi, eax
0x180032031  test    eax, eax
0x180032033  js      short loc_180032069
0x180032035  mov     rax, [rsp+6A0h+var_670]
0x18003203a  lea     r8, [rsp+6A0h+Context]; Context
0x18003203f  inc     rax
0x180032042  mov     rdx, r13; Delimiter
0x180032045  add     [rdi+40h], rax
0x180032049  xor     ecx, ecx; String
0x18003204b  call    cs:__imp_wcstok_s
0x180032051  mov     rdx, [rsp+6A0h+lpFileName]; void *
0x180032056  mov     r14, rax
0x180032059  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x18003205e  test    r14, r14
0x180032061  jnz     loc_180031EED
0x180032067  jmp     short loc_18003208C
0x180032069  mov     r9d, esi
0x18003206c  lea     rdx, aErrorWhileCopy; "Error while copying required file '%ws'"...
0x180032073  mov     r8, r14
0x180032076  lea     rcx, aCopyrequiredfi; "CopyRequiredFilesToList"
0x18003207d  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180032082  mov     rdx, [rsp+6A0h+lpFileName]; void *
0x180032087  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x18003208c  cmp     esi, 80070002h
0x180032092  mov     eax, r12d
0x180032095  cmovnz  eax, esi
0x180032098  test    eax, eax
0x18003209a  js      loc_180032140
0x1800320a0  cmp     [rdi+2Ah], r12b
0x1800320a4  jz      short loc_1800320EE
0x1800320a6  mov     rax, [rdi+40h]
0x1800320aa  lea     r8, aNtprint4V3host; "ntprint4|V3HostingFilter.dll"
0x1800320b1  mov     edx, [rdi+30h]
0x1800320b4  sub     rdx, rax; unsigned __int64
0x1800320b7  lea     rcx, [r15+rax*2]; unsigned __int16 *
0x1800320bb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800320c0  add     qword ptr [rdi+40h], 1Dh
0x1800320c5  test    eax, eax
0x1800320c7  js      short loc_180032140
0x1800320c9  cmp     [rdi+2Ah], r12b
0x1800320cd  jz      short loc_1800320EE
0x1800320cf  mov     rax, [rdi+40h]
0x1800320d3  lea     r8, aNtprint4V3host_0; "ntprint4|V3HostingFilter-pipelineconfig"...
0x1800320da  mov     edx, [rdi+30h]
0x1800320dd  sub     rdx, rax; unsigned __int64
0x1800320e0  lea     rcx, [r15+rax*2]; unsigned __int16 *
0x1800320e4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800320e9  add     qword ptr [rdi+40h], 2Ch ; ','
0x1800320ee  test    eax, eax
0x1800320f0  js      short loc_180032140
0x1800320f2  cmp     [rdi+2Bh], r12b
0x1800320f6  jz      short loc_180032140
0x1800320f8  mov     rax, [rdi+40h]
0x1800320fc  lea     r8, aNtprintStdname; "ntprint|StdNames.gpd"
0x180032103  mov     edx, [rdi+30h]
0x180032106  sub     rdx, rax; unsigned __int64
0x180032109  lea     rcx, [r15+rax*2]; unsigned __int16 *
0x18003210d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180032112  add     qword ptr [rdi+40h], 15h
0x180032117  test    eax, eax
0x180032119  js      short loc_180032140
0x18003211b  cmp     [rdi+2Bh], r12b
0x18003211f  jz      short loc_180032140
0x180032121  mov     rax, [rdi+40h]
0x180032125  lea     r8, aNtprintUniresD; "ntprint|unires.dll"
0x18003212c  mov     edx, [rdi+30h]
0x18003212f  sub     rdx, rax; unsigned __int64
0x180032132  lea     rcx, [r15+rax*2]; unsigned __int16 *
0x180032136  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003213b  add     qword ptr [rdi+40h], 13h
0x180032140  mov     rcx, [rbp+5A0h+var_40]
0x180032147  xor     rcx, rsp; StackCookie
0x18003214a  call    __security_check_cookie
0x18003214f  add     rsp, 670h
0x180032156  pop     r15
0x180032158  pop     r14
0x18003215a  pop     r13
0x18003215c  pop     r12
0x18003215e  pop     rdi
0x18003215f  pop     rsi
0x180032160  pop     rbp
0x180032161  retn
```
