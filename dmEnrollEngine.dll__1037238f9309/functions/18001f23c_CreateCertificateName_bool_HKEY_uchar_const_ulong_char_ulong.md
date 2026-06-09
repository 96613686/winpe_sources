# CreateCertificateName(bool,HKEY__ *,uchar const *,ulong,char *,ulong *)

- ea: `0x18001f23c`
- end: `0x18001f415`
- name: `?CreateCertificateName@@YAJ_NPEAUHKEY__@@PEBEKPEADPEAK@Z`
- size: `473`
- prototype: `__int64 __fastcall(unsigned __int8, HKEY, const char *, unsigned int, char *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001b3ac`
- `0x180056d24`

## callees

- `0x18001f23c`
- `0x18001f41c`
- `0x180057ca8`
- `0x180057cfc`
- `0x180058b78`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f2fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f2fe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f30c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f30c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f2e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f2e3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001f2d7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001f35d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001f2d7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001f35d`
- `DMCmnUtils!OmDmRegistryAllocAndGetString` at `0x18001f292`
- `DMCmnUtils!OmDmRegistryAllocAndGetString` at `0x18001f292`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateCertificateName(
        unsigned __int8 a1,
        HKEY a2,
        const char *a3,
        unsigned int a4,
        char *a5,
        unsigned int *a6)
{
  int v8; // r14d
  unsigned int v9; // ebp
  int String; // ebx
  unsigned int v11; // eax
  SIZE_T cbMultiByte; // rdi
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  LPVOID v15; // rax
  const char *v16; // rbx
  int v17; // edx
  unsigned int v18; // edx
  unsigned int v19; // ecx
  LPCWCH lpWideCharStr; // [rsp+40h] [rbp-48h] BYREF
  LPSTR lpMultiByteStr[8]; // [rsp+48h] [rbp-40h] BYREF

  v8 = a1;
  lpWideCharStr = 0;
  lpMultiByteStr[0] = 0;
  v9 = 61;
  if ( a4 <= 0x3D )
    v9 = a4;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpWideCharStr,
    0);
  String = OmDmRegistryAllocAndGetString(a2, L"EnrollmentID", 1, &lpWideCharStr);
  if ( String >= 0 )
  {
    v11 = WideCharToMultiByte(0, 0x400u, lpWideCharStr, -1, 0, 0, 0, 0);
    cbMultiByte = v11;
    if ( !v11 )
      goto LABEL_5;
    ProcessHeap = GetProcessHeap();
    v15 = HeapAlloc(ProcessHeap, 0, cbMultiByte);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      lpMultiByteStr,
      v15);
    v16 = lpMultiByteStr[0];
    if ( lpMultiByteStr[0] )
    {
      v17 = WideCharToMultiByte(0, 0x400u, lpWideCharStr, -1, lpMultiByteStr[0], cbMultiByte, 0, 0);
      if ( v17 )
      {
        v18 = 4 * v8 + v9 + 2 + v17;
        v19 = 4 * v8 + 65;
        if ( v18 <= v19 )
          v19 = v18;
        *a6 = v19;
        if ( !(_BYTE)v8 || (LastError = StringCbCatA(a5, v19, qword_18008A2C8), LastError >= 0) )
        {
          LastError = StringCbCatNA(a5, *a6, v16, 63 - v9);
          if ( LastError >= 0 )
          {
            LastError = StringCbCatA(a5, *a6, "!");
            if ( LastError >= 0 )
              LastError = StringCbCatNA(a5, *a6, a3, v9);
          }
        }
        goto LABEL_17;
      }
LABEL_5:
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_17:
      String = LastError;
      goto LABEL_18;
    }
    String = -2147024882;
  }
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(lpMultiByteStr);
  wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(&lpWideCharStr);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18001f23c  push    rbx
0x18001f23e  push    rbp
0x18001f23f  push    rsi
0x18001f240  push    rdi
0x18001f241  push    r14
0x18001f243  push    r15
0x18001f245  sub     rsp, 58h
0x18001f249  mov     r15, r8
0x18001f24c  mov     rbx, rdx
0x18001f24f  movzx   r14d, cl
0x18001f253  mov     [rsp+88h+lpWideCharStr], 0
0x18001f25c  mov     [rsp+88h+var_40], 0
0x18001f265  mov     ebp, 3Dh ; '='
0x18001f26a  cmp     r9d, ebp
0x18001f26d  cmovbe  ebp, r9d
0x18001f271  xor     edx, edx
0x18001f273  lea     rcx, [rsp+88h+lpWideCharStr]
0x18001f278  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AHPEAX@Z$1?SafeHeapFree@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001f27d  lea     r9, [rsp+88h+lpWideCharStr]
0x18001f282  mov     r8d, 1
0x18001f288  lea     rdx, aEnrollmentid; "EnrollmentID"
0x18001f28f  mov     rcx, rbx
0x18001f292  call    cs:__imp_?OmDmRegistryAllocAndGetString@@YAJPEAUHKEY__@@PEBGW4AllocFunction@@PEAPEAG@Z; OmDmRegistryAllocAndGetString(HKEY__ *,ushort const *,AllocFunction,ushort * *)
0x18001f298  mov     ebx, eax
0x18001f29a  test    eax, eax
0x18001f29c  js      loc_18001F3F1
0x18001f2a2  mov     [rsp+88h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001f2ab  mov     [rsp+88h+lpDefaultChar], 0; lpDefaultChar
0x18001f2b4  mov     [rsp+88h+cbMultiByte], 0; cbMultiByte
0x18001f2bc  mov     [rsp+88h+lpMultiByteStr], 0; lpMultiByteStr
0x18001f2c5  or      esi, 0FFFFFFFFh
0x18001f2c8  mov     r9d, esi; cchWideChar
0x18001f2cb  mov     r8, [rsp+88h+lpWideCharStr]; lpWideCharStr
0x18001f2d0  mov     edx, 400h; dwFlags
0x18001f2d5  xor     ecx, ecx; CodePage
0x18001f2d7  call    cs:__imp_WideCharToMultiByte
0x18001f2dd  mov     edi, eax
0x18001f2df  test    eax, eax
0x18001f2e1  jnz     short loc_18001F2FE
0x18001f2e3  call    cs:__imp_GetLastError
0x18001f2e9  test    eax, eax
0x18001f2eb  jle     loc_18001F3EF
0x18001f2f1  movzx   eax, ax
0x18001f2f4  or      eax, 80070000h
0x18001f2f9  jmp     loc_18001F3EF
0x18001f2fe  call    cs:__imp_GetProcessHeap
0x18001f304  mov     rcx, rax; hHeap
0x18001f307  mov     r8, rdi; dwBytes
0x18001f30a  xor     edx, edx; dwFlags
0x18001f30c  call    cs:__imp_HeapAlloc
0x18001f312  mov     rdx, rax
0x18001f315  lea     rcx, [rsp+88h+var_40]
0x18001f31a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AHPEAX@Z$1?SafeHeapFree@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001f31f  mov     rbx, [rsp+88h+var_40]
0x18001f324  test    rbx, rbx
0x18001f327  jnz     short loc_18001F333
0x18001f329  mov     ebx, 8007000Eh
0x18001f32e  jmp     loc_18001F3F1
0x18001f333  mov     [rsp+88h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001f33c  mov     [rsp+88h+lpDefaultChar], 0; lpDefaultChar
0x18001f345  mov     [rsp+88h+cbMultiByte], edi; cbMultiByte
0x18001f349  mov     [rsp+88h+lpMultiByteStr], rbx; lpMultiByteStr
0x18001f34e  mov     r9d, esi; cchWideChar
0x18001f351  mov     r8, [rsp+88h+lpWideCharStr]; lpWideCharStr
0x18001f356  mov     edx, 400h; dwFlags
0x18001f35b  xor     ecx, ecx; CodePage
0x18001f35d  call    cs:__imp_WideCharToMultiByte
0x18001f363  mov     edx, eax
0x18001f365  test    eax, eax
0x18001f367  jz      loc_18001F2E3
0x18001f36d  lea     ecx, ds:0[r14*4]
0x18001f375  lea     eax, [rbp+2]
0x18001f378  add     eax, ecx
0x18001f37a  add     edx, eax
0x18001f37c  add     ecx, 41h ; 'A'
0x18001f37f  cmp     edx, ecx
0x18001f381  cmovbe  ecx, edx
0x18001f384  mov     rsi, [rsp+88h+arg_28]
0x18001f38c  mov     [rsi], ecx
0x18001f38e  mov     rdi, [rsp+88h+arg_20]
0x18001f396  test    r14b, r14b
0x18001f399  jz      short loc_18001F3B0
0x18001f39b  mov     edx, ecx; unsigned __int64
0x18001f39d  lea     r8, qword_18008A2C8; char *
0x18001f3a4  mov     rcx, rdi; char *
0x18001f3a7  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x18001f3ac  test    eax, eax
0x18001f3ae  js      short loc_18001F3EF
0x18001f3b0  mov     r9d, 3Fh ; '?'
0x18001f3b6  sub     r9d, ebp; unsigned __int64
0x18001f3b9  mov     edx, [rsi]; unsigned __int64
0x18001f3bb  mov     r8, rbx; char *
0x18001f3be  mov     rcx, rdi; char *
0x18001f3c1  call    ?StringCbCatNA@@YAJPEAD_KPEBD1@Z; StringCbCatNA(char *,unsigned __int64,char const *,unsigned __int64)
0x18001f3c6  test    eax, eax
0x18001f3c8  js      short loc_18001F3EF
0x18001f3ca  mov     edx, [rsi]; unsigned __int64
0x18001f3cc  lea     r8, asc_1800882D4; "!"
0x18001f3d3  mov     rcx, rdi; char *
0x18001f3d6  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x18001f3db  test    eax, eax
0x18001f3dd  js      short loc_18001F3EF
0x18001f3df  mov     r9d, ebp; unsigned __int64
0x18001f3e2  mov     edx, [rsi]; unsigned __int64
0x18001f3e4  mov     r8, r15; char *
0x18001f3e7  mov     rcx, rdi; char *
0x18001f3ea  call    ?StringCbCatNA@@YAJPEAD_KPEBD1@Z; StringCbCatNA(char *,unsigned __int64,char const *,unsigned __int64)
0x18001f3ef  mov     ebx, eax
0x18001f3f1  lea     rcx, [rsp+88h+var_40]
0x18001f3f6  call    ??1?$unique_storage@U?$resource_policy@PEAU_CERT_PUBLIC_KEY_INFO@@P6AHPEAX@Z$1?SafeHeapFree@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(void)
0x18001f3fb  nop
0x18001f3fc  lea     rcx, [rsp+88h+lpWideCharStr]
0x18001f401  call    ??1?$unique_storage@U?$resource_policy@PEAU_CERT_PUBLIC_KEY_INFO@@P6AHPEAX@Z$1?SafeHeapFree@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(void)
0x18001f406  mov     eax, ebx
0x18001f408  add     rsp, 58h
0x18001f40c  pop     r15
0x18001f40e  pop     r14
0x18001f410  pop     rdi
0x18001f411  pop     rsi
0x18001f412  pop     rbp
0x18001f413  pop     rbx
0x18001f414  retn
```
