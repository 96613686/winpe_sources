# CCdsObjectMapper::_ComputeMimeType(HSTRING__ *,IPropertyStore *,HSTRING__ * *)

- ea: `0x18000cfd4`
- end: `0x18000d27a`
- name: `?_ComputeMimeType@CCdsObjectMapper@@AEAAJPEAUHSTRING__@@PEAUIPropertyStore@@PEAPEAU2@@Z`
- size: `678`
- prototype: `int(CCdsObjectMapper *__hidden this, HSTRING, struct IPropertyStore *, HSTRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002cfb4`

## callees

- `0x1800097c0`
- `0x18000cfd4`
- `0x18000d650`
- `0x18000d990`
- `0x18000f040`
- `0x180011930`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d21d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d21d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d0f2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d177`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d0f2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d177`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d140`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d140`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d10b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d10b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18000d1ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18000d1ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000d19a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000d1d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000d210`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000d19a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000d1d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000d210`

## pseudocode

```c
__int64 __fastcall CCdsObjectMapper::_ComputeMimeType(
        CCdsObjectMapper *this,
        const unsigned __int16 *a2,
        struct IPropertyStore *a3,
        HSTRING *a4)
{
  _QWORD *v7; // rax
  HRESULT v8; // ebx
  char v9; // si
  int v10; // eax
  __int64 v11; // rdi
  unsigned int i; // ebx
  const WCHAR *v13; // rcx
  const WCHAR *StringRawBuffer; // rax
  __int64 v15; // rcx
  HSTRING string2; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string1; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h] BYREF
  PROPVARIANT pvar; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v24; // [rsp+88h] [rbp-78h] BYREF
  WCHAR String1[6]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR sourceString[98]; // [rsp+BCh] [rbp-44h] BYREF

  pcbData = 200;
  v22 = 0;
  v19 = 0;
  string = 0;
  memset(&pvar, 0, sizeof(pvar));
  *a4 = 0;
  v7 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v24, (const unsigned __int16 (*)[23])a2);
  v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
         *v7,
         &v22);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v22 + 48LL))(
           v22,
           a2,
           &v19);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 72LL))(v19, &string);
      if ( v8 >= 0 )
      {
        v9 = 0;
        v10 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a3->lpVtbl->GetValue)(
                a3,
                &PKEY_Kind,
                &pvar);
        v11 = -1;
        if ( v10 >= 0 && pvar.vt == 4127 )
        {
          for ( i = 0; i < pvar.lVal; ++i )
          {
            v13 = *(const WCHAR **)&pvar.bstrblobVal.pData[8 * i];
            if ( v13 && CompareStringOrdinal(v13, -1, L"music", -1, 0) == 2 )
            {
              v9 = 1;
              break;
            }
          }
        }
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        if ( RegGetValueW(HKEY_CLASSES_ROOT, StringRawBuffer, L"Content Type", 2u, 0, String1, &pcbData) )
        {
          v8 = -2147467259;
        }
        else if ( v9 && CompareStringOrdinal(String1, 6, L"video/", 6, 0) == 2 )
        {
          string1 = 0;
          string2 = 0;
          v8 = WindowsCreateString(L"audio/", 6u, &string1);
          if ( v8 >= 0 )
          {
            do
              ++v11;
            while ( String1[v11] );
            v8 = WindowsCreateString(sourceString, v11 - 6, &string2);
            if ( v8 >= 0 )
              v8 = WindowsConcatString(string1, string2, a4);
          }
          Windows::Internal::String::~String((Windows::Internal::String *)&string2);
          Windows::Internal::String::~String((Windows::Internal::String *)&string1);
        }
        else
        {
          do
            ++v11;
          while ( String1[v11] );
          v8 = WindowsCreateString(String1, v11, a4);
        }
      }
    }
  }
  PropVariantClear(&pvar);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  v15 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000cfd4  mov     [rsp-8+arg_0], rbx
0x18000cfd9  push    rbp
0x18000cfda  push    rsi
0x18000cfdb  push    rdi
0x18000cfdc  push    r14
0x18000cfde  push    r15
0x18000cfe0  lea     rbp, [rsp-90h]
0x18000cfe8  sub     rsp, 190h
0x18000cfef  mov     rax, cs:__security_cookie
0x18000cff6  xor     rax, rsp
0x18000cff9  mov     [rbp+0B0h+var_30], rax
0x18000d000  xor     r15d, r15d
0x18000d003  mov     [rsp+1B0h+var_158], 0C8h
0x18000d00b  xorps   xmm0, xmm0
0x18000d00e  mov     [rsp+1B0h+var_148], r15
0x18000d013  xor     eax, eax
0x18000d015  mov     [rsp+1B0h+var_160], r15
0x18000d01a  lea     rcx, [rbp+0B0h+var_128]; string
0x18000d01e  mov     [rsp+1B0h+string], r15
0x18000d023  movups  xmmword ptr [rsp+1B0h+pvar], xmm0
0x18000d028  mov     qword ptr [rbp+0B0h+pvar+10h], rax
0x18000d02c  mov     r14, r9
0x18000d02f  mov     [r9], r15
0x18000d032  mov     rdi, r8
0x18000d035  mov     rsi, rdx
0x18000d038  call    ??$?0$0BH@@StringReference@Internal@Windows@@QEAA@AEAY0BH@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[23])
0x18000d03d  lea     rdx, [rsp+1B0h+var_148]
0x18000d042  mov     rcx, [rax]
0x18000d045  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x18000d04a  mov     ebx, eax
0x18000d04c  test    eax, eax
0x18000d04e  js      loc_18000D218
0x18000d054  mov     rcx, [rsp+1B0h+var_148]
0x18000d059  lea     r8, [rsp+1B0h+var_160]
0x18000d05e  mov     rdx, rsi
0x18000d061  mov     rax, [rcx]
0x18000d064  mov     rax, [rax+30h]
0x18000d068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d06d  mov     ebx, eax
0x18000d06f  test    eax, eax
0x18000d071  js      loc_18000D218
0x18000d077  mov     rcx, [rsp+1B0h+var_160]
0x18000d07c  lea     rdx, [rsp+1B0h+string]
0x18000d081  mov     rax, [rcx]
0x18000d084  mov     rax, [rax+48h]
0x18000d088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d08d  mov     ebx, eax
0x18000d08f  test    eax, eax
0x18000d091  js      loc_18000D218
0x18000d097  mov     rax, [rdi]
0x18000d09a  lea     r8, [rsp+1B0h+pvar]
0x18000d09f  lea     rdx, PKEY_Kind
0x18000d0a6  mov     rcx, rdi
0x18000d0a9  mov     sil, r15b
0x18000d0ac  mov     rax, [rax+28h]
0x18000d0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0b5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000d0b9  test    eax, eax
0x18000d0bb  js      short loc_18000D104
0x18000d0bd  mov     eax, 101Fh
0x18000d0c2  cmp     word ptr [rsp+1B0h+pvar], ax
0x18000d0c7  jnz     short loc_18000D104
0x18000d0c9  mov     ebx, r15d
0x18000d0cc  cmp     ebx, dword ptr [rsp+1B0h+pvar+8]
0x18000d0d0  jnb     short loc_18000D104
0x18000d0d2  mov     rax, qword ptr [rbp+0B0h+pvar+10h]
0x18000d0d6  mov     ecx, ebx
0x18000d0d8  mov     rcx, [rax+rcx*8]; lpString1
0x18000d0dc  test    rcx, rcx
0x18000d0df  jz      short loc_18000D0FD
0x18000d0e1  mov     r9d, edi; cchCount2
0x18000d0e4  mov     [rsp+1B0h+bIgnoreCase], r15d; bIgnoreCase
0x18000d0e9  lea     r8, aMusic; "music"
0x18000d0f0  mov     edx, edi; cchCount1
0x18000d0f2  call    cs:__imp_CompareStringOrdinal
0x18000d0f8  cmp     eax, 2
0x18000d0fb  jz      short loc_18000D101
0x18000d0fd  inc     ebx
0x18000d0ff  jmp     short loc_18000D0CC
0x18000d101  mov     sil, 1
0x18000d104  mov     rcx, [rsp+1B0h+string]; string
0x18000d109  xor     edx, edx; length
0x18000d10b  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d111  lea     rcx, [rsp+1B0h+var_158]
0x18000d116  mov     r9d, 2; dwFlags
0x18000d11c  mov     [rsp+1B0h+pcbData], rcx; pcbData
0x18000d121  lea     r8, Value; "Content Type"
0x18000d128  lea     rcx, [rbp+0B0h+String1]
0x18000d12c  mov     rdx, rax; lpSubKey
0x18000d12f  mov     [rsp+1B0h+pvData], rcx; pvData
0x18000d134  mov     rcx, 0FFFFFFFF80000000h; hkey
0x18000d13b  mov     qword ptr [rsp+1B0h+bIgnoreCase], r15; pdwType
0x18000d140  call    cs:__imp_RegGetValueW
0x18000d146  test    eax, eax
0x18000d148  jz      short loc_18000D154
0x18000d14a  mov     ebx, 80004005h
0x18000d14f  jmp     loc_18000D218
0x18000d154  test    sil, sil
0x18000d157  jz      loc_18000D1F9
0x18000d15d  mov     ebx, 6
0x18000d162  mov     [rsp+1B0h+bIgnoreCase], r15d; bIgnoreCase
0x18000d167  mov     r9d, ebx; cchCount2
0x18000d16a  lea     r8, aVideo; "video/"
0x18000d171  mov     edx, ebx; cchCount1
0x18000d173  lea     rcx, [rbp+0B0h+String1]; lpString1
0x18000d177  call    cs:__imp_CompareStringOrdinal
0x18000d17d  cmp     eax, 2
0x18000d180  jnz     short loc_18000D1F9
0x18000d182  lea     r8, [rsp+1B0h+string1]; string
0x18000d187  mov     [rsp+1B0h+string1], r15
0x18000d18c  mov     edx, ebx; length
0x18000d18e  mov     [rsp+1B0h+string2], r15
0x18000d193  lea     rcx, aAudio; "audio/"
0x18000d19a  call    cs:__imp_WindowsCreateString
0x18000d1a0  mov     ebx, eax
0x18000d1a2  test    eax, eax
0x18000d1a4  jns     short loc_18000D1BC
0x18000d1a6  lea     rcx, [rsp+1B0h+string2]; this
0x18000d1ab  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18000d1b0  lea     rcx, [rsp+1B0h+string1]; this
0x18000d1b5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18000d1ba  jmp     short loc_18000D218
0x18000d1bc  lea     rax, [rbp+0B0h+String1]
0x18000d1c0  inc     rdi
0x18000d1c3  cmp     [rax+rdi*2], r15w
0x18000d1c8  jnz     short loc_18000D1C0
0x18000d1ca  lea     edx, [rdi-6]; length
0x18000d1cd  lea     r8, [rsp+1B0h+string2]; string
0x18000d1d2  lea     rcx, [rbp+0B0h+sourceString]; sourceString
0x18000d1d6  call    cs:__imp_WindowsCreateString
0x18000d1dc  mov     ebx, eax
0x18000d1de  test    eax, eax
0x18000d1e0  js      short loc_18000D1A6
0x18000d1e2  mov     rdx, [rsp+1B0h+string2]; string2
0x18000d1e7  mov     r8, r14; newString
0x18000d1ea  mov     rcx, [rsp+1B0h+string1]; string1
0x18000d1ef  call    cs:__imp_WindowsConcatString
0x18000d1f5  mov     ebx, eax
0x18000d1f7  jmp     short loc_18000D1A6
0x18000d1f9  lea     rax, [rbp+0B0h+String1]
0x18000d1fd  inc     rdi
0x18000d200  cmp     [rax+rdi*2], r15w
0x18000d205  jnz     short loc_18000D1FD
0x18000d207  mov     edx, edi; length
0x18000d209  lea     rcx, [rbp+0B0h+String1]; sourceString
0x18000d20d  mov     r8, r14; string
0x18000d210  call    cs:__imp_WindowsCreateString
0x18000d216  mov     ebx, eax
0x18000d218  lea     rcx, [rsp+1B0h+pvar]; pvar
0x18000d21d  call    cs:__imp_PropVariantClear
0x18000d223  lea     rcx, [rsp+1B0h+string]; this
0x18000d228  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18000d22d  mov     rcx, [rsp+1B0h+var_160]
0x18000d232  test    rcx, rcx
0x18000d235  jz      short loc_18000D248
0x18000d237  mov     [rsp+1B0h+var_160], r15
0x18000d23c  mov     rax, [rcx]
0x18000d23f  mov     rax, [rax+10h]
0x18000d243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d248  lea     rcx, [rsp+1B0h+var_148]
0x18000d24d  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18000d252  mov     eax, ebx
0x18000d254  mov     rcx, [rbp+0B0h+var_30]
0x18000d25b  xor     rcx, rsp; StackCookie
0x18000d25e  call    __security_check_cookie
0x18000d263  mov     rbx, [rsp+1B0h+arg_0]
0x18000d26b  add     rsp, 190h
0x18000d272  pop     r15
0x18000d274  pop     r14
0x18000d276  pop     rdi
0x18000d277  pop     rsi
0x18000d278  pop     rbp
0x18000d279  retn
```
