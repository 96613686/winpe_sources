# AdvertisingIdHelpers::GetUserAdvertisingRegPath

- ea: `0x180005f54`
- end: `0x1800060b7`
- name: `AdvertisingIdHelpers::GetUserAdvertisingRegPath`
- size: `355`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001af0`
- `0x180004b20`
- `0x180004f00`
- `0x180005e44`

## callees

- `0x180004600`
- `0x180004680`
- `0x180004ab0`
- `0x180004ea0`
- `0x180005f34`
- `0x180005f54`
- `0x180006324`
- `0x1800094f8`
- `0x18000954c`
- `0x180009a00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005fff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005fff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005fc7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005fc7`

## pseudocode

```c
__int64 __fastcall AdvertisingIdHelpers::GetUserAdvertisingRegPath(unsigned __int16 *a1, const wchar_t **a2)
{
  int v4; // eax
  void *v5; // rdx
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int v8; // ebx
  unsigned __int64 v10; // rbx
  const wchar_t *v11; // rax
  const wchar_t *v12; // rdi
  unsigned __int16 *v13; // r14
  HRESULT v14; // edi
  size_t v15; // r9
  __int64 v16; // rdx
  const wchar_t *v17; // rcx
  __int64 v18; // r10
  size_t v19; // [rsp+20h] [rbp-28h]
  _QWORD v20[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  size_t pcchDestLength; // [rsp+90h] [rbp+48h] BYREF

  pcchDestLength = 0;
  v4 = StringCchLengthW(a1, 0x7FFFFFFFu, &pcchDestLength);
  v8 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x350,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)(unsigned int)v4,
      v19);
    return v8;
  }
  v10 = pcchDestLength + 59;
  if ( pcchDestLength == -60 )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, v5, v6, v7);
  v11 = (const wchar_t *)LocalAlloc(0, 2 * v10 + 2);
  v12 = v11;
  if ( v11 )
  {
    *v11 = 0;
    v11[v10] = 0;
  }
  v20[0] = v11;
  if ( a2 != v20 )
  {
    v13 = (unsigned __int16 *)*a2;
    if ( *a2 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&pcchDestLength);
      LocalFree(v13);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&pcchDestLength);
    }
    *a2 = v12;
    v20[0] = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v20);
  if ( !*a2 )
    return 2147942414LL;
  v14 = StringCchCopyW((unsigned __int16 *)*a2, v10, a1);
  if ( v14 >= 0 )
  {
    v17 = *a2;
    pcchDestLength = 0;
    v14 = StringValidateDestAndLengthW(v17, v10, &pcchDestLength, v15);
    if ( v14 >= 0 )
    {
      v14 = StringCopyWorkerW(
              (STRSAFE_LPWSTR)(v18 + 2 * pcchDestLength),
              v10 - pcchDestLength,
              0,
              L"\\Software\\Microsoft\\Windows\\CurrentVersion\\AdvertisingInfo",
              v19);
      if ( v14 >= 0 )
        return 0;
    }
    v16 = 856;
  }
  else
  {
    v16 = 855;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
    (const char *)(unsigned int)v14,
    v19);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180005f54  push    rbp
0x180005f56  push    rbx
0x180005f57  push    rsi
0x180005f58  push    rdi
0x180005f59  push    r14
0x180005f5b  push    r15
0x180005f5d  mov     rbp, rsp
0x180005f60  sub     rsp, 48h
0x180005f64  mov     rsi, rdx
0x180005f67  mov     [rbp+pcchDestLength], 0
0x180005f6f  mov     edx, 7FFFFFFFh; unsigned __int64
0x180005f74  lea     r8, [rbp+pcchDestLength]; unsigned __int64 *
0x180005f78  mov     r15, rcx
0x180005f7b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180005f80  mov     ebx, eax
0x180005f82  test    eax, eax
0x180005f84  jns     short loc_180005FA5
0x180005f86  mov     rcx, [rbp+30h]; this
0x180005f8a  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180005f91  mov     r9d, eax; char *
0x180005f94  mov     edx, 350h; void *
0x180005f99  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005f9e  mov     eax, ebx
0x180005fa0  jmp     loc_1800060AA
0x180005fa5  mov     rbx, [rbp+pcchDestLength]
0x180005fa9  add     rbx, 3Bh ; ';'
0x180005fad  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180005fb1  jnz     short loc_180005FBD
0x180005fb3  mov     rcx, [rbp+30h]; this
0x180005fb7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180005fbd  lea     rdx, ds:2[rbx*2]; uBytes
0x180005fc5  xor     ecx, ecx; uFlags
0x180005fc7  call    cs:__imp_LocalAlloc
0x180005fcd  mov     rdi, rax
0x180005fd0  test    rax, rax
0x180005fd3  jz      short loc_180005FDE
0x180005fd5  xor     ecx, ecx
0x180005fd7  mov     [rax], cx
0x180005fda  mov     [rax+rbx*2], cx
0x180005fde  lea     rax, [rbp+var_18]
0x180005fe2  mov     [rbp+var_18], rdi
0x180005fe6  cmp     rsi, rax
0x180005fe9  jz      short loc_180006019
0x180005feb  mov     r14, [rsi]
0x180005fee  test    r14, r14
0x180005ff1  jz      short loc_18000600E
0x180005ff3  lea     rcx, [rbp+pcchDestLength]; this
0x180005ff7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180005ffc  mov     rcx, r14; hMem
0x180005fff  call    cs:__imp_LocalFree
0x180006005  lea     rcx, [rbp+pcchDestLength]; this
0x180006009  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000600e  mov     [rsi], rdi
0x180006011  mov     [rbp+var_18], 0
0x180006019  lea     rcx, [rbp+var_18]
0x18000601d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006022  mov     rcx, [rsi]; unsigned __int16 *
0x180006025  test    rcx, rcx
0x180006028  jnz     short loc_180006031
0x18000602a  mov     eax, 8007000Eh
0x18000602f  jmp     short loc_1800060AA
0x180006031  mov     r8, r15; unsigned __int16 *
0x180006034  mov     rdx, rbx; unsigned __int64
0x180006037  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000603c  mov     edi, eax
0x18000603e  test    eax, eax
0x180006040  jns     short loc_180006049
0x180006042  mov     edx, 357h
0x180006047  jmp     short loc_180006095
0x180006049  mov     r10, [rsi]
0x18000604c  lea     r8, [rbp+pcchDestLength]; pcchDestLength
0x180006050  mov     rcx, r10; pszDest
0x180006053  mov     [rbp+pcchDestLength], 0
0x18000605b  mov     rdx, rbx; cchDest
0x18000605e  call    StringValidateDestAndLengthW
0x180006063  mov     edi, eax
0x180006065  test    eax, eax
0x180006067  js      short loc_180006090
0x180006069  mov     rax, [rbp+pcchDestLength]
0x18000606d  lea     r9, aSoftwareMicros; "\\Software\\Microsoft\\Windows\\Current"...
0x180006074  sub     rbx, rax
0x180006077  xor     r8d, r8d; pcchNewDestLength
0x18000607a  mov     rdx, rbx; cchDest
0x18000607d  lea     rcx, [r10+rax*2]; pszDest
0x180006081  call    StringCopyWorkerW
0x180006086  mov     edi, eax
0x180006088  test    eax, eax
0x18000608a  js      short loc_180006090
0x18000608c  xor     eax, eax
0x18000608e  jmp     short loc_1800060AA
0x180006090  mov     edx, 358h; void *
0x180006095  mov     rcx, [rbp+30h]; this
0x180006099  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x1800060a0  mov     r9d, edi; char *
0x1800060a3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800060a8  mov     eax, edi
0x1800060aa  add     rsp, 48h
0x1800060ae  pop     r15
0x1800060b0  pop     r14
0x1800060b2  pop     rdi
0x1800060b3  pop     rsi
0x1800060b4  pop     rbx
0x1800060b5  pop     rbp
0x1800060b6  retn
```
