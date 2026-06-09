# _GetUserNameAndDomainSlowly(void *,ushort * *,ushort * *)

- ea: `0x18000b9c4`
- end: `0x18000bb52`
- name: `?_GetUserNameAndDomainSlowly@@YAJPEAXPEAPEAG1@Z`
- size: `398`
- prototype: `__int64 __fastcall(PSID Sid, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006de0`

## callees

- `0x180005b60`
- `0x1800063e0`
- `0x18000a6d0`
- `0x18000b9c4`
- `0x18000dc34`
- `0x1800166c4`

## import_xrefs

- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18000ba0d`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18000baed`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18000ba0d`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18000baed`

## pseudocode

```c
__int64 __fastcall _GetUserNameAndDomainSlowly(PSID Sid, unsigned __int16 **a2, unsigned __int16 **a3)
{
  BOOL v6; // eax
  __int64 result; // rax
  unsigned int LastError; // ebx
  __int64 v9; // rdx
  unsigned __int16 *v10; // rdi
  int v11; // eax
  unsigned __int16 *v12; // rbx
  const char *v13; // r9
  int cchReferencedDomainName; // [rsp+20h] [rbp-38h]
  DWORD cchName; // [rsp+30h] [rbp-28h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+34h] [rbp-24h] BYREF
  LPWSTR Name; // [rsp+38h] [rbp-20h] BYREF
  LPWSTR v18[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  DWORD v20; // [rsp+A8h] [rbp+50h] BYREF

  cchName = 0;
  v20 = 0;
  peUse = 0;
  v6 = LookupAccountSidLocalW(Sid, 0, &cchName, 0, &v20, &peUse);
  result = ResultFromWin32Bool(v6);
  LastError = result;
  if ( (int)result >= 0 )
  {
    LastError = -2147418113;
    v9 = 466;
    goto LABEL_3;
  }
  if ( (_DWORD)result != -2147024891 && (_DWORD)result != -2147023174 )
  {
    if ( (_DWORD)result == -2147024774 )
    {
      Name = 0;
      LastError = ResultFromHeapAllocArray<unsigned short>(cchName, &Name);
      if ( (LastError & 0x80000000) == 0 )
      {
        v10 = Name;
        v18[0] = Name;
        Name = 0;
        v11 = ResultFromHeapAllocArray<unsigned short>(v20, &Name);
        LastError = v11;
        if ( v11 >= 0 )
        {
          v12 = Name;
          if ( LookupAccountSidLocalW(Sid, v10, &cchName, Name, &v20, &peUse) )
          {
            *a2 = v10;
            *a3 = v12;
            v18[0] = 0;
            Name = 0;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Name);
            LastError = 0;
          }
          else
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x1E3,
                          (unsigned int)"minio\\profapi\\env.cpp",
                          v13);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Name);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1DB,
            (unsigned int)"minio\\profapi\\env.cpp",
            (const char *)(unsigned int)v11,
            cchReferencedDomainName);
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v18);
        return LastError;
      }
      v9 = 471;
    }
    else
    {
      v9 = 468;
    }
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"minio\\profapi\\env.cpp",
      (const char *)LastError,
      cchReferencedDomainName);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x18000b9c4  push    rbp
0x18000b9c6  push    rbx
0x18000b9c7  push    rsi
0x18000b9c8  push    rdi
0x18000b9c9  push    r14
0x18000b9cb  push    r15
0x18000b9cd  mov     rbp, rsp
0x18000b9d0  sub     rsp, 58h
0x18000b9d4  lea     rax, [rbp+var_24]
0x18000b9d8  mov     [rbp+cchName], 0
0x18000b9df  mov     [rsp+58h+peUse], rax; peUse
0x18000b9e4  mov     rsi, r8
0x18000b9e7  lea     rax, [rbp+arg_18]
0x18000b9eb  mov     [rbp+arg_18], 0
0x18000b9f2  mov     r14, rdx
0x18000b9f5  mov     [rsp+58h+cchReferencedDomainName], rax; int
0x18000b9fa  xor     r9d, r9d; ReferencedDomainName
0x18000b9fd  mov     [rbp+var_24], 0
0x18000ba04  lea     r8, [rbp+cchName]; cchName
0x18000ba08  xor     edx, edx; Name
0x18000ba0a  mov     r15, rcx
0x18000ba0d  call    cs:__imp_LookupAccountSidLocalW
0x18000ba13  mov     ecx, eax; int
0x18000ba15  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18000ba1a  mov     ebx, eax
0x18000ba1c  test    eax, eax
0x18000ba1e  js      short loc_18000BA42
0x18000ba20  mov     ebx, 8000FFFFh
0x18000ba25  mov     edx, 1D2h; void *
0x18000ba2a  mov     rcx, [rbp+30h]; this
0x18000ba2e  lea     r8, aMinioProfapiEn; "minio\\profapi\\env.cpp"
0x18000ba35  mov     r9d, ebx; char *
0x18000ba38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba3d  jmp     loc_18000BB43
0x18000ba42  cmp     ebx, 80070005h
0x18000ba48  jz      loc_18000BB45
0x18000ba4e  cmp     ebx, 800706BAh
0x18000ba54  jz      loc_18000BB45
0x18000ba5a  cmp     ebx, 8007007Ah
0x18000ba60  jz      short loc_18000BA69
0x18000ba62  mov     edx, 1D4h
0x18000ba67  jmp     short loc_18000BA2A
0x18000ba69  mov     ecx, [rbp+cchName]
0x18000ba6c  lea     rdx, [rbp+Name]
0x18000ba70  mov     [rbp+Name], 0
0x18000ba78  call    ??$ResultFromHeapAllocArray@G@@YAJ_KPEAPEAG@Z; ResultFromHeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x18000ba7d  mov     ebx, eax
0x18000ba7f  test    eax, eax
0x18000ba81  jns     short loc_18000BA8A
0x18000ba83  mov     edx, 1D7h
0x18000ba88  jmp     short loc_18000BA2A
0x18000ba8a  mov     rdi, [rbp+Name]
0x18000ba8e  lea     rdx, [rbp+Name]
0x18000ba92  mov     ecx, [rbp+arg_18]
0x18000ba95  mov     [rbp+var_18], rdi
0x18000ba99  mov     [rbp+Name], 0
0x18000baa1  call    ??$ResultFromHeapAllocArray@G@@YAJ_KPEAPEAG@Z; ResultFromHeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x18000baa6  mov     ebx, eax
0x18000baa8  test    eax, eax
0x18000baaa  jns     short loc_18000BAC6
0x18000baac  mov     rcx, [rbp+30h]; this
0x18000bab0  lea     r8, aMinioProfapiEn; "minio\\profapi\\env.cpp"
0x18000bab7  mov     r9d, eax; char *
0x18000baba  mov     edx, 1DBh; void *
0x18000babf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bac4  jmp     short loc_18000BB3A
0x18000bac6  mov     rbx, [rbp+Name]
0x18000baca  lea     rax, [rbp+var_24]
0x18000bace  mov     [rsp+58h+peUse], rax; peUse
0x18000bad3  lea     r8, [rbp+cchName]; cchName
0x18000bad7  lea     rax, [rbp+arg_18]
0x18000badb  mov     [rbp+Name], rbx
0x18000badf  mov     r9, rbx; ReferencedDomainName
0x18000bae2  mov     [rsp+58h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000bae7  mov     rdx, rdi; Name
0x18000baea  mov     rcx, r15; Sid
0x18000baed  call    cs:__imp_LookupAccountSidLocalW
0x18000baf3  test    eax, eax
0x18000baf5  jnz     short loc_18000BB19
0x18000baf7  mov     rcx, [rbp+30h]; this
0x18000bafb  lea     r8, aMinioProfapiEn; "minio\\profapi\\env.cpp"
0x18000bb02  mov     edx, 1E3h; void *
0x18000bb07  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bb0c  lea     rcx, [rbp+Name]
0x18000bb10  mov     ebx, eax
0x18000bb12  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bb17  jmp     short loc_18000BB3A
0x18000bb19  mov     [r14], rdi
0x18000bb1c  lea     rcx, [rbp+Name]
0x18000bb20  mov     [rsi], rbx
0x18000bb23  mov     [rbp+var_18], 0
0x18000bb2b  mov     [rbp+Name], 0
0x18000bb33  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bb38  xor     ebx, ebx
0x18000bb3a  lea     rcx, [rbp+var_18]
0x18000bb3e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bb43  mov     eax, ebx
0x18000bb45  add     rsp, 58h
0x18000bb49  pop     r15
0x18000bb4b  pop     r14
0x18000bb4d  pop     rdi
0x18000bb4e  pop     rsi
0x18000bb4f  pop     rbx
0x18000bb50  pop     rbp
0x18000bb51  retn
```
