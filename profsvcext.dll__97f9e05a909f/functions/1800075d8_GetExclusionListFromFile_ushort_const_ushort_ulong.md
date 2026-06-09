# GetExclusionListFromFile(ushort const *,ushort * *,ulong *)

- ea: `0x1800075d8`
- end: `0x180007798`
- name: `?GetExclusionListFromFile@@YAJPEBGPEAPEAGPEAK@Z`
- size: `448`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180007468`

## callees

- `0x180005234`
- `0x180005424`
- `0x180006a80`
- `0x180006a9c`
- `0x1800075d8`
- `0x18000a520`
- `0x1800139ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800076b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800076b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000776d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000776d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180007658`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180007658`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800076f3`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800076f3`

## string_xrefs

- `0x18000767d`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180007714`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
__int64 __fastcall GetExclusionListFromFile(const unsigned __int16 *a1, unsigned __int16 **a2, unsigned int *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  const WCHAR *v8; // rsi
  DWORD v9; // edi
  HANDLE ProcessHeap; // rax
  WCHAR *v11; // rax
  const unsigned __int16 *v12; // rbx
  int v13; // eax
  signed int LastError; // eax
  DWORD nSize; // [rsp+20h] [rbp-60h]
  DWORD nSizea; // [rsp+20h] [rbp-60h]
  WCHAR *v18; // [rsp+30h] [rbp-50h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+38h] [rbp-48h] BYREF
  __int128 FileInformation; // [rsp+50h] [rbp-30h] BYREF
  __int128 v21; // [rsp+60h] [rbp-20h]
  unsigned int v22; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *a2 = 0;
  memset(lpFileName, 0, sizeof(lpFileName));
  v4 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         lpFileName,
         L"%s\\%s",
         a1,
         L"ntuser.ini");
  v5 = v4;
  if ( v4 >= 0 )
  {
    v8 = lpFileName[0];
    v22 = 0;
    FileInformation = 0;
    v21 = 0;
    if ( GetFileAttributesExW(lpFileName[0], GetFileExInfoStandard, &FileInformation) )
    {
      if ( HIDWORD(v21) )
      {
        v5 = -2147024883;
        v7 = 2310;
LABEL_6:
        v6 = v5;
        goto LABEL_7;
      }
      v9 = v22 >> 1;
      if ( !(v22 >> 1) )
        v9 = 1;
      ProcessHeap = GetProcessHeap();
      v11 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 2LL * v9);
      v12 = v11;
      if ( !v11 )
      {
        v5 = -2147024882;
        v7 = 2319;
        goto LABEL_6;
      }
      v18 = v11;
      *v11 = 0;
      GetPrivateProfileStringW(L"General", L"ExclusionList", &word_1800223E8, v11, v9, v8);
      if ( *v12 )
      {
        v13 = HeapAllocString(v12, a2);
        v5 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x91F,
            (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
            (const char *)(unsigned int)v13,
            nSizea);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v18);
          goto LABEL_17;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v18);
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 != -2147024894 )
      {
        if ( (v5 & 0x80000000) == 0 )
          goto LABEL_17;
        v7 = 2345;
        goto LABEL_6;
      }
    }
    v5 = 0;
    goto LABEL_17;
  }
  v6 = (unsigned int)v4;
  v7 = 2292;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
    (const char *)v6,
    nSize);
LABEL_17:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
  return v5;
}

```

## disassembly

```asm
0x1800075d8  mov     [rsp-28h+arg_10], rbx
0x1800075dd  push    rbp
0x1800075de  push    rsi
0x1800075df  push    rdi
0x1800075e0  push    r14
0x1800075e2  push    r15
0x1800075e4  mov     rbp, rsp
0x1800075e7  sub     rsp, 80h
0x1800075ee  mov     rax, cs:__security_cookie
0x1800075f5  xor     rax, rsp
0x1800075f8  mov     [rbp+var_8], rax
0x1800075fc  xor     r15d, r15d
0x1800075ff  lea     r9, ?c_szNTUserIni@@3QBGB; "ntuser.ini"
0x180007606  mov     [rdx], r15
0x180007609  mov     r14, rdx
0x18000760c  mov     r8, rcx
0x18000760f  mov     [rbp+lpFileName], r15
0x180007613  lea     rdx, aSS; "%s\\%s"
0x18000761a  mov     [rbp+var_40], r15
0x18000761e  lea     rcx, [rbp+lpFileName]
0x180007622  mov     [rbp+var_38], r15
0x180007626  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000762b  mov     ebx, eax
0x18000762d  test    eax, eax
0x18000762f  jns     short loc_18000763B
0x180007631  mov     r9d, eax
0x180007634  mov     edx, 8F4h
0x180007639  jmp     short loc_180007679
0x18000763b  mov     rsi, [rbp+lpFileName]
0x18000763f  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180007643  xorps   xmm0, xmm0
0x180007646  xor     eax, eax
0x180007648  mov     rcx, rsi; lpFileName
0x18000764b  mov     [rbp+var_10], eax
0x18000764e  xor     edx, edx; fInfoLevelId
0x180007650  movups  [rbp+FileInformation], xmm0
0x180007654  movups  [rbp+var_20], xmm0
0x180007658  call    cs:__imp_GetFileAttributesExW
0x18000765e  test    eax, eax
0x180007660  jz      loc_18000776D
0x180007666  cmp     dword ptr [rbp+var_20+0Ch], r15d
0x18000766a  jbe     short loc_18000768E
0x18000766c  mov     ebx, 8007000Dh
0x180007671  mov     edx, 906h; void *
0x180007676  mov     r9d, ebx; char *
0x180007679  mov     rcx, [rbp+28h]; this
0x18000767d  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180007684  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007689  jmp     loc_18000773F
0x18000768e  mov     edi, [rbp+var_10]
0x180007691  mov     eax, 1
0x180007696  shr     edi, 1
0x180007698  cmp     edi, eax
0x18000769a  cmovb   edi, eax
0x18000769d  mov     ebx, edi
0x18000769f  add     rbx, rbx
0x1800076a2  call    cs:__imp_GetProcessHeap
0x1800076a8  mov     r8, rbx; dwBytes
0x1800076ab  xor     edx, edx; dwFlags
0x1800076ad  mov     rcx, rax; hHeap
0x1800076b0  call    cs:__imp_HeapAlloc
0x1800076b6  mov     rbx, rax
0x1800076b9  test    rax, rax
0x1800076bc  jnz     short loc_1800076CA
0x1800076be  mov     ebx, 8007000Eh
0x1800076c3  mov     edx, 90Fh
0x1800076c8  jmp     short loc_180007676
0x1800076ca  mov     [rsp+80h+var_58], rsi; lpFileName
0x1800076cf  lea     r8, word_1800223E8; lpDefault
0x1800076d6  mov     r9, rbx; lpReturnedString
0x1800076d9  mov     [rsp+80h+nSize], edi; int
0x1800076dd  lea     rdx, aExclusionlist; "ExclusionList"
0x1800076e4  mov     [rbp+var_50], rbx
0x1800076e8  lea     rcx, aGeneral; "General"
0x1800076ef  mov     [rax], r15w
0x1800076f3  call    cs:__imp_GetPrivateProfileStringW
0x1800076f9  cmp     [rbx], r15w
0x1800076fd  jz      short loc_180007733
0x1800076ff  mov     rdx, r14; unsigned __int16 **
0x180007702  mov     rcx, rbx; unsigned __int16 *
0x180007705  call    ?HeapAllocString@@YAJPEBGPEAPEAG@Z; HeapAllocString(ushort const *,ushort * *)
0x18000770a  mov     ebx, eax
0x18000770c  test    eax, eax
0x18000770e  jns     short loc_180007733
0x180007710  mov     rcx, [rbp+28h]; this
0x180007714  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x18000771b  mov     r9d, eax; char *
0x18000771e  mov     edx, 91Fh; void *
0x180007723  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007728  lea     rcx, [rbp+var_50]
0x18000772c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180007731  jmp     short loc_18000773F
0x180007733  lea     rcx, [rbp+var_50]
0x180007737  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000773c  mov     ebx, r15d
0x18000773f  lea     rcx, [rbp+lpFileName]
0x180007743  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180007748  mov     eax, ebx
0x18000774a  mov     rcx, [rbp+var_8]
0x18000774e  xor     rcx, rsp; StackCookie
0x180007751  call    __security_check_cookie
0x180007756  mov     rbx, [rsp+80h+arg_10]
0x18000775e  add     rsp, 80h
0x180007765  pop     r15
0x180007767  pop     r14
0x180007769  pop     rdi
0x18000776a  pop     rsi
0x18000776b  pop     rbp
0x18000776c  retn
0x18000776d  call    cs:__imp_GetLastError
0x180007773  mov     ebx, eax
0x180007775  test    eax, eax
0x180007777  jle     short loc_180007782
0x180007779  movzx   ebx, ax
0x18000777c  or      ebx, 80070000h
0x180007782  cmp     ebx, 80070002h
0x180007788  jz      short loc_18000773C
0x18000778a  test    ebx, ebx
0x18000778c  jns     short loc_18000773F
0x18000778e  mov     edx, 929h
0x180007793  jmp     loc_180007676
```
