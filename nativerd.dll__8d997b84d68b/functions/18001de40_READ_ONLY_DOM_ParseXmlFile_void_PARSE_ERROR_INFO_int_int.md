# READ_ONLY_DOM::ParseXmlFile(void *,PARSE_ERROR_INFO *,int,int)

- ea: `0x18001de40`
- end: `0x18001e0a9`
- name: `?ParseXmlFile@READ_ONLY_DOM@@UEAAJPEAXPEAVPARSE_ERROR_INFO@@HH@Z`
- size: `617`
- prototype: `__int64 __fastcall(READ_ONLY_DOM *this, void *, struct PARSE_ERROR_INFO *, int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000f9fc`
- `0x1800100d0`
- `0x180010870`
- `0x18001c250`
- `0x18001d870`
- `0x18001de40`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dea1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001deab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dea1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001deab`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001de94`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001de94`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001df3d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001df3d`
- `XmlLite!CreateXmlReader` at `0x18001df54`
- `XmlLite!CreateXmlReader` at `0x18001df54`

## pseudocode

```c
__int64 __fastcall READ_ONLY_DOM::ParseXmlFile(
        READ_ONLY_DOM *this,
        void *a2,
        struct PARSE_ERROR_INFO *a3,
        int a4,
        int a5)
{
  int XmlReader; // ebx
  DWORD FileSize; // esi
  signed int LastError; // eax
  XML_READ_STREAM *v11; // rax
  XML_READ_STREAM *v12; // rax
  _QWORD *v13; // rsi
  int v14; // eax
  _DWORD *v15; // rax
  enum XmlNodeType v17; // [rsp+40h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v19[3]; // [rsp+50h] [rbp-18h] BYREF
  DWORD FileSizeHigh; // [rsp+A8h] [rbp+40h] BYREF

  FileSizeHigh = 0;
  v19[0] = 0;
  ppv = 0;
  v17 = XmlNodeType_None;
  if ( a2 && a3 )
  {
    if ( a4 )
      return (unsigned int)-2147024846;
    FileSize = GetFileSize(a2, &FileSizeHigh);
    if ( FileSize == -1 && GetLastError() )
    {
      LastError = GetLastError();
      XmlReader = LastError;
      if ( LastError > 0 )
        XmlReader = (unsigned __int16)LastError | 0x80070000;
    }
    else if ( FileSizeHigh
           || a5
           && *(_DWORD *)&g_dwMaxWebConfigFileSizeInKb
           && *(_DWORD *)&g_dwMaxWebConfigFileSizeInKb << 10 < FileSize )
    {
      XmlReader = -2147024846;
      PARSE_ERROR_INFO::SetErrorInfo(a3, 2147942450LL, 3, 3221228260LL, v19, 0, 0, 0, v17, ppv);
    }
    else
    {
      v11 = (XML_READ_STREAM *)operator new(0x38u);
      if ( v11 )
        v12 = XML_READ_STREAM::XML_READ_STREAM(v11, a2);
      else
        v12 = 0;
      *((_QWORD *)this + 4) = v12;
      if ( v12 )
      {
        CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage3, &ppv);
        v13 = (_QWORD *)((char *)this + 16);
        XmlReader = CreateXmlReader(&riid, (void **)this + 2, 0);
        if ( XmlReader >= 0 )
        {
          XmlReader = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v13 + 24LL))(*v13, *((_QWORD *)this + 4));
          if ( XmlReader >= 0 )
          {
            XmlReader = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID))(*(_QWORD *)*v13 + 40LL))(*v13, 0, ppv);
            if ( XmlReader >= 0 )
            {
              while ( 1 )
              {
                v14 = READ_ONLY_DOM::Read(this, &v17, a3);
                XmlReader = v14;
                if ( v14 < 0 || v14 == 1 )
                  break;
                if ( v17 == XmlNodeType_Element )
                {
                  v15 = operator new(0x70u);
                  if ( v15 )
                  {
                    v15[5] &= 0xFFFFFFF8;
                    *(_QWORD *)v15 = &READ_ONLY_DOM_NODE::`vftable'{for `IArrayListEntry'};
                    *((_QWORD *)v15 + 1) = &READ_ONLY_DOM_NODE::`vftable'{for `IConfigDomNode'};
                    v15[4] = 1;
                    *((_QWORD *)v15 + 3) = this;
                    *((_QWORD *)v15 + 4) = 0;
                    *((_QWORD *)v15 + 5) = 0;
                    *((_QWORD *)v15 + 6) = &DICTIONARY_LIST::`vftable';
                    v15[14] = 8;
                    *((_QWORD *)v15 + 8) = 0;
                    *((_QWORD *)v15 + 9) = 0;
                    *((_QWORD *)v15 + 10) = 0;
                    *((_QWORD *)v15 + 11) = 0;
                    *((_QWORD *)v15 + 12) = 0;
                    *((_QWORD *)v15 + 13) = 0;
                  }
                  else
                  {
                    v15 = 0;
                  }
                  *((_QWORD *)this + 3) = v15;
                  if ( v15 )
                  {
                    XmlReader = READ_ONLY_DOM_NODE::Create((READ_ONLY_DOM_NODE *)v15);
                    break;
                  }
                  goto LABEL_17;
                }
              }
            }
          }
        }
      }
      else
      {
LABEL_17:
        XmlReader = -2147024888;
      }
    }
  }
  else
  {
    XmlReader = -2147024809;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)XmlReader;
}

```

## disassembly

```asm
0x18001de40  push    rbp
0x18001de42  push    rbx
0x18001de43  push    rsi
0x18001de44  push    rdi
0x18001de45  push    r14
0x18001de47  push    r15
0x18001de49  mov     rbp, rsp
0x18001de4c  sub     rsp, 68h
0x18001de50  xor     r15d, r15d
0x18001de53  mov     r14, r8
0x18001de56  mov     [rbp+FileSizeHigh], r15d
0x18001de5a  mov     rbx, rdx
0x18001de5d  mov     [rbp+var_18], r15
0x18001de61  mov     rdi, rcx
0x18001de64  mov     [rbp+var_20], r15
0x18001de68  mov     [rbp+var_28], r15d
0x18001de6c  test    rdx, rdx
0x18001de6f  jz      loc_18001E080
0x18001de75  test    r8, r8
0x18001de78  jz      loc_18001E080
0x18001de7e  test    r9d, r9d
0x18001de81  jz      short loc_18001DE8D
0x18001de83  mov     ebx, 80070032h
0x18001de88  jmp     loc_18001E09A
0x18001de8d  lea     rdx, [rbp+FileSizeHigh]; lpFileSizeHigh
0x18001de91  mov     rcx, rbx; hFile
0x18001de94  call    cs:__imp_GetFileSize
0x18001de9a  mov     esi, eax
0x18001de9c  cmp     eax, 0FFFFFFFFh
0x18001de9f  jnz     short loc_18001DEC9
0x18001dea1  call    cs:__imp_GetLastError
0x18001dea7  test    eax, eax
0x18001dea9  jz      short loc_18001DEC9
0x18001deab  call    cs:__imp_GetLastError
0x18001deb1  mov     ebx, eax
0x18001deb3  test    eax, eax
0x18001deb5  jle     loc_18001E085
0x18001debb  movzx   ebx, ax
0x18001debe  or      ebx, 80070000h
0x18001dec4  jmp     loc_18001E085
0x18001dec9  cmp     [rbp+FileSizeHigh], r15d
0x18001decd  jnz     loc_18001E04B
0x18001ded3  cmp     [rbp+arg_20], r15d
0x18001ded7  jz      short loc_18001DEEE
0x18001ded9  mov     eax, cs:?g_dwMaxWebConfigFileSizeInKb@@3KA; ulong g_dwMaxWebConfigFileSizeInKb
0x18001dedf  test    eax, eax
0x18001dee1  jz      short loc_18001DEEE
0x18001dee3  shl     eax, 0Ah
0x18001dee6  cmp     eax, esi
0x18001dee8  jb      loc_18001E04B
0x18001deee  mov     ecx, 38h ; '8'; Size
0x18001def3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001def8  test    rax, rax
0x18001defb  jz      short loc_18001DF0A
0x18001defd  mov     rdx, rbx; void *
0x18001df00  mov     rcx, rax; this
0x18001df03  call    ??0XML_READ_STREAM@@QEAA@PEAX@Z; XML_READ_STREAM::XML_READ_STREAM(void *)
0x18001df08  jmp     short loc_18001DF0D
0x18001df0a  mov     rax, r15
0x18001df0d  mov     [rdi+20h], rax
0x18001df11  test    rax, rax
0x18001df14  jnz     short loc_18001DF20
0x18001df16  mov     ebx, 80070008h
0x18001df1b  jmp     loc_18001E085
0x18001df20  xor     edx, edx; pUnkOuter
0x18001df22  lea     rax, [rbp+var_20]
0x18001df26  lea     r9, IID_IMultiLanguage3; riid
0x18001df2d  mov     [rsp+68h+ppv], rax; ppv
0x18001df32  lea     rcx, CLSID_CMultiLanguage; rclsid
0x18001df39  lea     r8d, [rdx+1]; dwClsContext
0x18001df3d  call    cs:__imp_CoCreateInstance
0x18001df43  lea     rsi, [rdi+10h]
0x18001df47  xor     r8d, r8d; pMalloc
0x18001df4a  mov     rdx, rsi; ppvObject
0x18001df4d  lea     rcx, riid; riid
0x18001df54  call    cs:__imp_CreateXmlReader
0x18001df5a  mov     ebx, eax
0x18001df5c  test    eax, eax
0x18001df5e  js      loc_18001E085
0x18001df64  mov     rcx, [rsi]
0x18001df67  mov     rdx, [rdi+20h]
0x18001df6b  mov     rax, [rcx]
0x18001df6e  mov     rax, [rax+18h]
0x18001df72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df77  mov     ebx, eax
0x18001df79  test    eax, eax
0x18001df7b  js      loc_18001E085
0x18001df81  mov     rcx, [rsi]
0x18001df84  xor     edx, edx
0x18001df86  mov     r8, [rbp+var_20]
0x18001df8a  mov     rax, [rcx]
0x18001df8d  mov     rax, [rax+28h]
0x18001df91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df96  mov     ebx, eax
0x18001df98  test    eax, eax
0x18001df9a  js      loc_18001E085
0x18001dfa0  mov     r8, r14; struct PARSE_ERROR_INFO *
0x18001dfa3  lea     rdx, [rbp+var_28]; enum XmlNodeType *
0x18001dfa7  mov     rcx, rdi; this
0x18001dfaa  call    ?Read@READ_ONLY_DOM@@QEAAJPEAW4XmlNodeType@@PEAVPARSE_ERROR_INFO@@@Z; READ_ONLY_DOM::Read(XmlNodeType *,PARSE_ERROR_INFO *)
0x18001dfaf  mov     ebx, eax
0x18001dfb1  test    eax, eax
0x18001dfb3  js      loc_18001E085
0x18001dfb9  cmp     eax, 1
0x18001dfbc  jz      loc_18001E085
0x18001dfc2  cmp     [rbp+var_28], 1
0x18001dfc6  jnz     short loc_18001DFA0
0x18001dfc8  mov     ecx, 70h ; 'p'; Size
0x18001dfcd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dfd2  test    rax, rax
0x18001dfd5  jz      short loc_18001E02F
0x18001dfd7  and     dword ptr [rax+14h], 0FFFFFFF8h
0x18001dfdb  lea     rcx, ??_7READ_ONLY_DOM_NODE@@6BIArrayListEntry@@@; const READ_ONLY_DOM_NODE::`vftable'{for `IArrayListEntry'}
0x18001dfe2  mov     [rax], rcx
0x18001dfe5  lea     rcx, ??_7READ_ONLY_DOM_NODE@@6BIConfigDomNode@@@; const READ_ONLY_DOM_NODE::`vftable'{for `IConfigDomNode'}
0x18001dfec  mov     [rax+8], rcx
0x18001dff0  lea     rcx, ??_7DICTIONARY_LIST@@6B@; const DICTIONARY_LIST::`vftable'
0x18001dff7  mov     dword ptr [rax+10h], 1
0x18001dffe  mov     [rax+18h], rdi
0x18001e002  mov     [rax+20h], r15
0x18001e006  mov     [rax+28h], r15
0x18001e00a  mov     [rax+30h], rcx
0x18001e00e  mov     dword ptr [rax+38h], 8
0x18001e015  mov     [rax+40h], r15
0x18001e019  mov     [rax+48h], r15
0x18001e01d  mov     [rax+50h], r15
0x18001e021  mov     [rax+58h], r15
0x18001e025  mov     [rax+60h], r15
0x18001e029  mov     [rax+68h], r15
0x18001e02d  jmp     short loc_18001E032
0x18001e02f  mov     rax, r15
0x18001e032  mov     [rdi+18h], rax
0x18001e036  test    rax, rax
0x18001e039  jz      loc_18001DF16
0x18001e03f  mov     rcx, rax; this
0x18001e042  call    ?Create@READ_ONLY_DOM_NODE@@QEAAJXZ; READ_ONLY_DOM_NODE::Create(void)
0x18001e047  mov     ebx, eax
0x18001e049  jmp     short loc_18001E085
0x18001e04b  mov     [rsp+68h+var_30], r15
0x18001e050  lea     rax, [rbp+var_18]
0x18001e054  mov     [rsp+68h+var_38], r15
0x18001e059  mov     ebx, 80070032h
0x18001e05e  mov     [rsp+68h+var_40], r15d
0x18001e063  mov     edx, ebx
0x18001e065  mov     r9d, 0C0000AE4h
0x18001e06b  mov     [rsp+68h+ppv], rax
0x18001e070  mov     r8d, 3
0x18001e076  mov     rcx, r14
0x18001e079  call    ?SetErrorInfo@PARSE_ERROR_INFO@@QEAAJJW4PARSE_ERROR_TYPE@@KQEAPEBDKPEAVIConfigDom@@PEAVIConfigDomNode@@@Z; PARSE_ERROR_INFO::SetErrorInfo(long,PARSE_ERROR_TYPE,ulong,char const * * const,ulong,IConfigDom *,IConfigDomNode *)
0x18001e07e  jmp     short loc_18001E085
0x18001e080  mov     ebx, 80070057h
0x18001e085  mov     rcx, [rbp+var_20]
0x18001e089  test    rcx, rcx
0x18001e08c  jz      short loc_18001E09A
0x18001e08e  mov     rax, [rcx]
0x18001e091  mov     rax, [rax+10h]
0x18001e095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e09a  mov     eax, ebx
0x18001e09c  add     rsp, 68h
0x18001e0a0  pop     r15
0x18001e0a2  pop     r14
0x18001e0a4  pop     rdi
0x18001e0a5  pop     rsi
0x18001e0a6  pop     rbx
0x18001e0a7  pop     rbp
0x18001e0a8  retn
```
