# ExpeditedUpdateCallbacksHelper::CreateJsonString(CloudExperienceHostAPI::OobeExpeditedUpdateStatus,uint,long,tagDownloadSubPhase,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,ushort const *,ushort const *)

- ea: `0x180066018`
- end: `0x18006613a`
- name: `?CreateJsonString@ExpeditedUpdateCallbacksHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@W4OobeExpeditedUpdateStatus@CloudExperienceHostAPI@@IJW4tagDownloadSubPhase@@_K222PEBG3@Z`
- size: `290`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180063c08`
- `0x180063d2c`
- `0x1800a72c8`
- `0x1800a76ac`
- `0x1800a785c`

## callees

- `0x1800230b0`
- `0x1800415f0`
- `0x1800418d8`
- `0x180043c58`
- `0x180063f50`
- `0x180066018`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800660cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800660cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800660f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800660f4`

## string_xrefs

- `0x180066113`: `Expedited update event [%s]`
- `0x1800660dd`: `shell\oobe\machine\plugins\adapters\inc\expeditedupdatecallbackshelper.h`
- `0x1800660b4`: `{"ExpeditedUpdateStatus":0,"DownloadInstallProgress":0,"StatusCode":0x80070057,"DownloadSubPhase":0,"TotalBytesDownloaded":0,"TotalBytesToDownload":0,"CurrentUpdateBytesDownloaded":0,"CurrentUpdateBytesToDownload":0}`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall ExpeditedUpdateCallbacksHelper::CreateJsonString(
        _QWORD *a1,
        int a2,
        int a3,
        int a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10,
        char a11)
{
  __int64 v12; // rdx
  HRESULT v13; // eax
  char *StringRawBuffer; // rax
  const char *v15; // r9
  HSTRING string; // [rsp+30h] [rbp-59h] BYREF
  _QWORD v18[14]; // [rsp+38h] [rbp-51h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+27h]
  int v20; // [rsp+C0h] [rbp+37h] BYREF
  int v21; // [rsp+C8h] [rbp+3Fh] BYREF
  int v22; // [rsp+D0h] [rbp+47h] BYREF

  v22 = a4;
  v21 = a3;
  v20 = a2;
  string = 0;
  v18[0] = &v20;
  v18[1] = &v21;
  v18[2] = &v22;
  v18[3] = &a5;
  v18[4] = &a6;
  v18[5] = &a7;
  v18[6] = &a8;
  v18[7] = &a9;
  v18[8] = &a10;
  v18[9] = &a11;
  v18[10] = &string;
  if ( (int)_lambda_d8c50c42e0be286d672e824af5d026fe_::operator()(v18) < 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &string,
      0);
    v12 = -1;
    do
      ++v12;
    while ( aExpeditedupdat_71[v12] );
    v13 = WindowsCreateString(
            L"{\"ExpeditedUpdateStatus\":0,\"DownloadInstallProgress\":0,\"StatusCode\":0x80070057,\"DownloadSubPhase\":0,"
             "\"TotalBytesDownloaded\":0,\"TotalBytesToDownload\":0,\"CurrentUpdateBytesDownloaded\":0,\"CurrentUpdateByt"
             "esToDownload\":0}",
            v12,
            &string);
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\expeditedupdatecallbackshelper.h",
        (const char *)(unsigned int)v13,
        0);
  }
  StringRawBuffer = (char *)WindowsGetStringRawBuffer(string, 0);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    a1,
    StringRawBuffer,
    0xFFFFFFFFFFFFFFFFuLL,
    v15);
  UnattendLogW(0, L"Expedited update event [%s]", *a1);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  return a1;
}

```

## disassembly

```asm
0x180066018  mov     rax, rsp
0x18006601b  mov     [rax+20h], r9d
0x18006601f  mov     [rax+18h], r8d
0x180066023  mov     [rax+10h], edx
0x180066026  mov     [rax+8], rcx
0x18006602a  push    rbp
0x18006602b  push    rbx
0x18006602c  push    rdi
0x18006602d  lea     rbp, [rax-27h]
0x180066031  sub     rsp, 90h
0x180066038  mov     rbx, rcx
0x18006603b  xor     edi, edi
0x18006603d  mov     [rbp+1Fh+var_80], edi
0x180066040  mov     [rbp+1Fh+string], rdi
0x180066044  lea     rax, [rbp+1Fh+arg_8]
0x180066048  mov     [rbp+1Fh+var_70], rax
0x18006604c  lea     rax, [rbp+1Fh+arg_10]
0x180066050  mov     [rbp+1Fh+var_68], rax
0x180066054  lea     rax, [rbp+1Fh+arg_18]
0x180066058  mov     [rbp+1Fh+var_60], rax
0x18006605c  lea     rax, [rbp+1Fh+arg_20]
0x180066060  mov     [rbp+1Fh+var_58], rax
0x180066064  lea     rax, [rbp+1Fh+arg_28]
0x180066068  mov     [rbp+1Fh+var_50], rax
0x18006606c  lea     rax, [rbp+1Fh+arg_30]
0x180066070  mov     [rbp+1Fh+var_48], rax
0x180066074  lea     rax, [rbp+1Fh+arg_38]
0x180066078  mov     [rbp+1Fh+var_40], rax
0x18006607c  lea     rax, [rbp+1Fh+arg_40]
0x180066080  mov     [rbp+1Fh+var_38], rax
0x180066084  lea     rax, [rbp+1Fh+arg_48]
0x180066088  mov     [rbp+1Fh+var_30], rax
0x18006608c  lea     rax, [rbp+1Fh+arg_50]
0x180066090  mov     [rbp+1Fh+var_28], rax
0x180066094  lea     rax, [rbp+1Fh+string]
0x180066098  mov     [rbp+1Fh+var_20], rax
0x18006609c  lea     rcx, [rbp+1Fh+var_70]
0x1800660a0  call    ??R_lambda_d8c50c42e0be286d672e824af5d026fe_@@QEBA@XZ; _lambda_d8c50c42e0be286d672e824af5d026fe_::operator()(void)
0x1800660a5  test    eax, eax
0x1800660a7  jns     short loc_1800660EE
0x1800660a9  xor     edx, edx
0x1800660ab  lea     rcx, [rbp+1Fh+string]
0x1800660af  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800660b4  lea     rcx, aExpeditedupdat_71; "{\"ExpeditedUpdateStatus\":0,\"Download"...
0x1800660bb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800660bf  inc     rdx; length
0x1800660c2  cmp     [rcx+rdx*2], di
0x1800660c6  jnz     short loc_1800660BF
0x1800660c8  lea     r8, [rbp+1Fh+string]; string
0x1800660cc  call    cs:__imp_WindowsCreateString
0x1800660d2  mov     rcx, [rbp+27h]; this
0x1800660d6  test    eax, eax
0x1800660d8  jns     short loc_1800660EE
0x1800660da  mov     r9d, eax; char *
0x1800660dd  lea     r8, aShellOobeMachi_5; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800660e4  mov     edx, 8Fh; void *
0x1800660e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800660ee  xor     edx, edx; length
0x1800660f0  mov     rcx, [rbp+1Fh+string]; string
0x1800660f4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800660fa  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800660fe  mov     rdx, rax
0x180066101  mov     rcx, rbx
0x180066104  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180066109  mov     [rbp+1Fh+var_80], 1
0x180066110  mov     r8, [rbx]
0x180066113  lea     rdx, aExpeditedUpdat_9; "Expedited update event [%s]"
0x18006611a  xor     ecx, ecx
0x18006611c  call    UnattendLogW
0x180066121  nop
0x180066122  lea     rcx, [rbp+1Fh+string]; this
0x180066126  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006612b  mov     rax, rbx
0x18006612e  add     rsp, 90h
0x180066135  pop     rdi
0x180066136  pop     rbx
0x180066137  pop     rbp
0x180066138  retn
```
