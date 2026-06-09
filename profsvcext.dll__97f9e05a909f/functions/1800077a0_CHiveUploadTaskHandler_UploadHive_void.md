# CHiveUploadTaskHandler::_UploadHive(void *)

- ea: `0x1800077a0`
- end: `0x1800078cd`
- name: `?_UploadHive@CHiveUploadTaskHandler@@AEAAJPEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(CHiveUploadTaskHandler *__hidden this, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180017f4c`

## callees

- `0x180006a9c`
- `0x1800077a0`
- `0x18000f220`
- `0x18000f4b0`
- `0x18000f530`
- `0x180011134`
- `0x180011478`
- `0x180018a3c`
- `0x180019634`
- `0x18001a4c4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000787a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000787a`
- `PROFSVC!GetUserPreferenceValue` at `0x180007808`
- `PROFSVC!GetUserPreferenceValue` at `0x180007808`

## string_xrefs

- `0x180007888`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
__int64 __fastcall CHiveUploadTaskHandler::_UploadHive(CHiveUploadTaskHandler *this, void *a2)
{
  char v3; // di
  int SidString; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  signed int v11; // eax
  const wchar_t **v12; // rax
  __int64 v13; // rcx
  const wchar_t *v14; // r9
  int v16[8]; // [rsp+20h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  void *v18; // [rsp+68h] [rbp+28h] BYREF
  unsigned __int16 *v19; // [rsp+70h] [rbp+30h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+38h] BYREF

  v18 = a2;
  v3 = 0;
  v19 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v19,
    0);
  SidString = GetSidString(v18, &v19);
  v6 = SidString;
  if ( SidString < 0 )
  {
    v7 = (unsigned int)SidString;
    v8 = 607;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
      (const char *)v7,
      v16[0]);
    goto LABEL_18;
  }
  if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) != 0 )
    McTemplateU0z_EtwEventWriteTransfer(v5, EVENT_UPLOAD_HIVE_START, v19);
  if ( GetUserPreferenceValue(v18) )
  {
    v10 = lambda_28508da440a647ba9fa7458939195a49_::_lambda_28508da440a647ba9fa7458939195a49_(v16, this, &v19, &v18);
    v11 = lambda_28508da440a647ba9fa7458939195a49_::operator()(v10);
    v6 = v11;
    if ( v11 < 0 )
    {
      if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 0x10) != 0 )
      {
        v12 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, v11);
        v3 = 1;
        v14 = L"???";
        if ( *v12 )
          v14 = *v12;
        McTemplateU0zz_EtwEventWriteTransfer(v13, EVENT_UPLOAD_HIVE_FAILED, v19, v14);
      }
      if ( (v3 & 1) != 0 )
        LocalFree(hMem);
      v7 = v6;
      v8 = 651;
      goto LABEL_14;
    }
  }
  if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) != 0 )
    McTemplateU0z_EtwEventWriteTransfer(v9, EVENT_UPLOAD_HIVE_SUCCEEDED, v19);
  v6 = 0;
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
  return v6;
}

```

## disassembly

```asm
0x1800077a0  mov     [rsp-18h+arg_0], rbx
0x1800077a5  mov     [rsp-18h+arg_8], rdx
0x1800077aa  push    rbp
0x1800077ab  push    rsi
0x1800077ac  push    rdi
0x1800077ad  mov     rbp, rsp
0x1800077b0  sub     rsp, 40h
0x1800077b4  mov     rsi, rcx
0x1800077b7  xor     edi, edi
0x1800077b9  mov     dword ptr [rbp+arg_10], edi
0x1800077bc  mov     [rbp+arg_10], rdi
0x1800077c0  xor     edx, edx
0x1800077c2  lea     rcx, [rbp+arg_10]
0x1800077c6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800077cb  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x1800077cf  mov     rcx, [rbp+arg_8]; void *
0x1800077d3  call    ?GetSidString@@YAJPEAXPEAPEAG@Z; GetSidString(void *,ushort * *)
0x1800077d8  mov     ebx, eax
0x1800077da  test    eax, eax
0x1800077dc  jns     short loc_1800077EB
0x1800077de  mov     r9d, eax
0x1800077e1  mov     edx, 25Fh
0x1800077e6  jmp     loc_180007888
0x1800077eb  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x1800077f2  jz      short loc_180007804
0x1800077f4  mov     r8, [rbp+arg_10]
0x1800077f8  lea     rdx, EVENT_UPLOAD_HIVE_START
0x1800077ff  call    McTemplateU0z_EtwEventWriteTransfer
0x180007804  mov     rcx, [rbp+arg_8]
0x180007808  call    cs:__imp_?GetUserPreferenceValue@@YAKPEAX@Z; GetUserPreferenceValue(void *)
0x18000780e  test    eax, eax
0x180007810  jz      loc_18000789A
0x180007816  lea     r9, [rbp+arg_8]
0x18000781a  lea     r8, [rbp+arg_10]
0x18000781e  mov     rdx, rsi
0x180007821  lea     rcx, [rbp+var_20]
0x180007825  call    _lambda_28508da440a647ba9fa7458939195a49____lambda_28508da440a647ba9fa7458939195a49_
0x18000782a  mov     rcx, rax
0x18000782d  call    _lambda_28508da440a647ba9fa7458939195a49___operator__
0x180007832  mov     ebx, eax
0x180007834  test    eax, eax
0x180007836  jns     short loc_18000789A
0x180007838  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 10h
0x18000783f  jz      short loc_180007870
0x180007841  mov     edx, eax; dwMessageId
0x180007843  lea     rcx, [rbp+hMem]; lpBuffer
0x180007847  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x18000784c  mov     edi, 1
0x180007851  lea     r9, asc_180022B10; "???"
0x180007858  cmp     qword ptr [rax], 0
0x18000785c  cmovnz  r9, [rax]
0x180007860  mov     r8, [rbp+arg_10]
0x180007864  lea     rdx, EVENT_UPLOAD_HIVE_FAILED
0x18000786b  call    McTemplateU0zz_EtwEventWriteTransfer
0x180007870  test    dil, 1
0x180007874  jz      short loc_180007880
0x180007876  mov     rcx, [rbp+hMem]; hMem
0x18000787a  call    cs:__imp_LocalFree
0x180007880  mov     r9d, ebx; char *
0x180007883  mov     edx, 28Bh; void *
0x180007888  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x18000788f  mov     rcx, [rbp+18h]; this
0x180007893  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007898  jmp     short loc_1800078B5
0x18000789a  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x1800078a1  jz      short loc_1800078B3
0x1800078a3  mov     r8, [rbp+arg_10]
0x1800078a7  lea     rdx, EVENT_UPLOAD_HIVE_SUCCEEDED
0x1800078ae  call    McTemplateU0z_EtwEventWriteTransfer
0x1800078b3  xor     ebx, ebx
0x1800078b5  lea     rcx, [rbp+arg_10]
0x1800078b9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800078be  mov     eax, ebx
0x1800078c0  mov     rbx, [rsp+40h+arg_0]
0x1800078c5  add     rsp, 40h
0x1800078c9  pop     rdi
0x1800078ca  pop     rsi
0x1800078cb  pop     rbp
0x1800078cc  retn
```
