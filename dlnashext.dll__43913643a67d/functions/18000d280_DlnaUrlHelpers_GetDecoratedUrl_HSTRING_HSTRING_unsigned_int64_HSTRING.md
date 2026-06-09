# DlnaUrlHelpers::GetDecoratedUrl(HSTRING__ *,HSTRING__ *,unsigned __int64,HSTRING__ * *)

- ea: `0x18000d280`
- end: `0x18000d648`
- name: `?GetDecoratedUrl@DlnaUrlHelpers@@YAJPEAUHSTRING__@@0_KPEAPEAU2@@Z`
- size: `968`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING, HSTRING, unsigned __int64, HSTRING *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18002b708`

## callees

- `0x1800097c0`
- `0x18000d280`
- `0x18000d650`
- `0x18000d990`
- `0x18000d9bc`
- `0x18000f040`
- `0x180011930`
- `0x18001afc8`
- `0x18001bbe0`
- `0x18001bfc0`
- `0x18001c648`
- `0x18001d41c`
- `0x18002b67c`
- `0x1800333e8`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d2e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d2e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000d3ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000d3ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000d5e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000d5e1`

## pseudocode

```c
__int64 __fastcall DlnaUrlHelpers::GetDecoratedUrl(HSTRING string, HSTRING a2, HSTRING a3, HSTRING *a4)
{
  PCWSTR StringRawBuffer; // rax
  WCHAR *v8; // r12
  const unsigned __int16 (*v9)[23]; // rdx
  HSTRING *v10; // rax
  int v11; // edi
  PCWSTR v12; // rax
  PCWSTR v13; // r14
  unsigned __int64 v14; // rcx
  __int64 v15; // rsi
  HRESULT v16; // eax
  UINT32 v17; // ebx
  BOOL IsStringEmpty; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rsi
  const wchar_t *v22; // rdx
  UINT32 v23; // ebx
  __int64 v24; // rdx
  __int64 v25; // r9
  __int64 v26; // rsi
  UINT32 v27; // ebx
  __int64 v28; // rsi
  UINT32 v29; // ebx
  const WCHAR *v30; // rax
  __int64 v31; // rcx
  int v33; // [rsp+20h] [rbp-59h] BYREF
  int v34; // [rsp+28h] [rbp-51h] BYREF
  UINT32 v35[2]; // [rsp+2Ch] [rbp-4Dh]
  int v36; // [rsp+34h] [rbp-45h]
  __int64 v37; // [rsp+38h] [rbp-41h]
  UINT32 length; // [rsp+40h] [rbp-39h] BYREF
  __int64 v39; // [rsp+48h] [rbp-31h] BYREF
  HSTRING stringa; // [rsp+50h] [rbp-29h] BYREF
  __int64 v41; // [rsp+58h] [rbp-21h] BYREF
  HSTRING v42; // [rsp+60h] [rbp-19h] BYREF
  HSTRING v43; // [rsp+68h] [rbp-11h] BYREF

  v34 &= 0xFFFFFFF8;
  v41 = 0;
  v39 = 0;
  stringa = 0;
  v42 = 0;
  *(_QWORD *)v35 = 0;
  v37 = 0;
  v36 = 0;
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, &length);
  *a4 = 0;
  v8 = (WCHAR *)StringRawBuffer;
  v10 = Windows::Internal::StringReference::StringReference(&v43, v9);
  v11 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
          *v10,
          &v41);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v41 + 48LL))(v41, string, &v39);
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 112LL))(v39, &stringa);
      if ( v11 >= 0 )
      {
        v12 = WindowsGetStringRawBuffer(string, 0);
        v33 = -1;
        v13 = v12;
        v11 = -2147024785;
        if ( v12 )
        {
          v14 = -1;
          do
            ++v14;
          while ( v12[v14] );
          if ( (int)UIntPtrToLong(v14, &v33) < 0 )
          {
            v35[0] = -2147024785;
            goto LABEL_50;
          }
          v15 = v33;
          if ( (unsigned int)v33 > 0x4000000 )
          {
            v35[0] = -2147024785;
            v16 = -2147024785;
          }
          else if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(&v34, (unsigned int)v33) >= 0 )
          {
            v17 = v35[1];
            memcpy_0((void *)(v37 + 2LL * (int)v35[1]), v13, 2 * v15);
            CMFBaseStringT<unsigned short>::ReleaseBuffer(&v34, v17 + (unsigned int)v15);
            v16 = 0;
          }
          else
          {
            v16 = v35[0];
          }
          if ( v16 < 0 )
          {
LABEL_49:
            v11 = v16;
            goto LABEL_50;
          }
        }
        IsStringEmpty = WindowsIsStringEmpty(stringa);
        v33 = -1;
        if ( IsStringEmpty )
        {
          if ( (int)UIntPtrToLong(8u, &v33) >= 0 )
          {
            if ( (v35[0] & 0x80000000) != 0 )
              goto LABEL_28;
            v21 = v33;
            if ( (unsigned int)v33 <= 0x4000000 )
            {
              if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(&v34, v33 + v35[1]) >= 0 )
              {
                v22 = L"?WMHME=1";
LABEL_26:
                v23 = v35[1];
                memcpy_0((void *)(v37 + 2LL * (int)v35[1]), v22, 2 * v21);
                CMFBaseStringT<unsigned short>::ReleaseBuffer(&v34, v23 + (unsigned int)v21);
                goto LABEL_28;
              }
              goto LABEL_28;
            }
          }
        }
        else if ( (int)UIntPtrToLong(8u, &v33) >= 0 )
        {
          if ( (v35[0] & 0x80000000) != 0 )
            goto LABEL_28;
          v21 = v33;
          if ( (unsigned int)v33 <= 0x4000000 )
          {
            if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(&v34, v33 + v35[1]) >= 0 )
            {
              v22 = L"&WMHME=1";
              goto LABEL_26;
            }
LABEL_28:
            if ( length <= 1 && (length != 1 || *v8 == 42) )
            {
LABEL_39:
              if ( !a3 )
              {
LABEL_47:
                v11 = v35[0];
                if ( (v35[0] & 0x80000000) != 0 )
                  goto LABEL_50;
                v30 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents(&v34, v19, v20);
                v16 = WindowsCreateString(v30, v35[1], a4);
                goto LABEL_49;
              }
              v33 = -1;
              if ( (int)UIntPtrToLong(0xCu, &v33) >= 0 )
              {
                if ( (v35[0] & 0x80000000) != 0 )
                {
LABEL_46:
                  CMFBaseStringT<unsigned short>::AppendUInt64(&v34, a3);
                  goto LABEL_47;
                }
                v28 = v33;
                if ( (unsigned int)v33 <= 0x4000000 )
                {
                  if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(&v34, v33 + v35[1]) >= 0 )
                  {
                    v29 = v35[1];
                    memcpy_0((void *)(v37 + 2LL * (int)v35[1]), L"&WMDuration=", 2 * v28);
                    CMFBaseStringT<unsigned short>::ReleaseBuffer(&v34, v29 + (unsigned int)v28);
                  }
                  goto LABEL_46;
                }
              }
              v35[0] = -2147024785;
              goto LABEL_46;
            }
            v33 = -1;
            if ( (int)UIntPtrToLong(0x13u, &v33) >= 0 )
            {
              if ( (v35[0] & 0x80000000) != 0 )
              {
LABEL_38:
                CMFBaseStringT<unsigned short>::Append(&v34, v24, v8, v25);
                goto LABEL_39;
              }
              v26 = v33;
              if ( (unsigned int)v33 <= 0x4000000 )
              {
                if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(&v34, v33 + v35[1]) >= 0 )
                {
                  v27 = v35[1];
                  memcpy_0((void *)(v37 + 2LL * (int)v35[1]), L"&WMContentFeatures=", 2 * v26);
                  CMFBaseStringT<unsigned short>::ReleaseBuffer(&v34, v27 + (unsigned int)v26);
                }
                v25 = length;
                goto LABEL_38;
              }
            }
            v35[0] = -2147024785;
            goto LABEL_38;
          }
        }
        v35[0] = -2147024785;
        goto LABEL_28;
      }
    }
  }
LABEL_50:
  CMFBaseStringT<unsigned short>::~CMFBaseStringT<unsigned short>(&v34);
  Windows::Internal::String::~String(&v42);
  Windows::Internal::String::~String(&stringa);
  v31 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v41);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000d280  push    rbp
0x18000d282  push    rbx
0x18000d283  push    rsi
0x18000d284  push    rdi
0x18000d285  push    r12
0x18000d287  push    r13
0x18000d289  push    r14
0x18000d28b  push    r15
0x18000d28d  lea     rbp, [rsp-1Fh]
0x18000d292  sub     rsp, 98h
0x18000d299  mov     rax, cs:__security_cookie
0x18000d2a0  xor     rax, rsp
0x18000d2a3  mov     [rbp+57h+var_48], rax
0x18000d2a7  and     [rbp+57h+var_A8], 0FFFFFFF8h
0x18000d2ab  xor     r14d, r14d
0x18000d2ae  mov     rax, rdx
0x18000d2b1  mov     [rbp+57h+var_78], r14
0x18000d2b5  mov     rbx, rcx
0x18000d2b8  mov     [rbp+57h+var_88], r14
0x18000d2bc  mov     rcx, rax; string
0x18000d2bf  mov     [rbp+57h+string], r14
0x18000d2c3  lea     rdx, [rbp+57h+length]; length
0x18000d2c7  mov     [rbp+57h+var_70], r14
0x18000d2cb  mov     r13, r9
0x18000d2ce  mov     qword ptr [rbp+57h+var_A4], r14
0x18000d2d2  mov     r15, r8
0x18000d2d5  mov     [rbp+57h+var_98], r14
0x18000d2d9  mov     [rbp+57h+var_9C], r14d
0x18000d2dd  mov     [rbp+57h+length], r14d
0x18000d2e1  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d2e7  lea     rcx, [rbp+57h+var_68]; string
0x18000d2eb  mov     [r13+0], r14
0x18000d2ef  mov     r12, rax
0x18000d2f2  call    ??$?0$0BH@@StringReference@Internal@Windows@@QEAA@AEAY0BH@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[23])
0x18000d2f7  lea     rdx, [rbp+57h+var_78]
0x18000d2fb  mov     rcx, [rax]
0x18000d2fe  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x18000d303  mov     edi, eax
0x18000d305  test    eax, eax
0x18000d307  js      loc_18000D5E9
0x18000d30d  mov     r9, [rbp+57h+var_78]
0x18000d311  lea     r8, [rbp+57h+var_88]
0x18000d315  mov     rdx, rbx
0x18000d318  mov     rcx, [r9]
0x18000d31b  mov     rax, [rcx+30h]
0x18000d31f  mov     rcx, r9
0x18000d322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d327  mov     edi, eax
0x18000d329  test    eax, eax
0x18000d32b  js      loc_18000D5E9
0x18000d331  mov     rcx, [rbp+57h+var_88]
0x18000d335  lea     rdx, [rbp+57h+string]
0x18000d339  mov     rax, [rcx]
0x18000d33c  mov     rax, [rax+70h]
0x18000d340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d345  mov     edi, eax
0x18000d347  test    eax, eax
0x18000d349  js      loc_18000D5E9
0x18000d34f  xor     edx, edx; length
0x18000d351  mov     rcx, rbx; string
0x18000d354  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d35a  xor     ebx, ebx
0x18000d35c  mov     [rbp+57h+var_B0], 0FFFFFFFFh
0x18000d363  mov     r14, rax
0x18000d366  mov     edi, 8007006Fh
0x18000d36b  test    rax, rax
0x18000d36e  jz      loc_18000D3F8
0x18000d374  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d378  inc     rcx; unsigned __int64
0x18000d37b  cmp     [rax+rcx*2], bx
0x18000d37f  jnz     short loc_18000D378
0x18000d381  lea     rdx, [rbp+57h+var_B0]; int *
0x18000d385  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x18000d38a  test    eax, eax
0x18000d38c  jns     short loc_18000D399
0x18000d38e  mov     [rbp+57h+var_A4], edi
0x18000d391  xor     r14d, r14d
0x18000d394  jmp     loc_18000D5E9
0x18000d399  movsxd  rsi, [rbp+57h+var_B0]
0x18000d39d  cmp     esi, 4000000h
0x18000d3a3  ja      short loc_18000D3E7
0x18000d3a5  mov     edx, esi
0x18000d3a7  lea     rcx, [rbp+57h+var_A8]
0x18000d3ab  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x18000d3b0  test    eax, eax
0x18000d3b2  jns     short loc_18000D3B9
0x18000d3b4  mov     eax, [rbp+57h+var_A4]
0x18000d3b7  jmp     short loc_18000D3EC
0x18000d3b9  mov     rax, [rbp+57h+var_98]
0x18000d3bd  mov     r8, rsi
0x18000d3c0  movsxd  rbx, [rbp+57h+var_A4+4]
0x18000d3c4  add     r8, r8; Size
0x18000d3c7  mov     rdx, r14; Src
0x18000d3ca  lea     rcx, [rax+rbx*2]; void *
0x18000d3ce  call    memcpy_0
0x18000d3d3  lea     edx, [rbx+rsi]
0x18000d3d6  lea     rcx, [rbp+57h+var_A8]
0x18000d3da  call    ?ReleaseBuffer@?$CMFBaseStringT@G@@QEAAJJ@Z; CMFBaseStringT<ushort>::ReleaseBuffer(long)
0x18000d3df  xor     r14d, r14d
0x18000d3e2  mov     eax, r14d
0x18000d3e5  jmp     short loc_18000D3EF
0x18000d3e7  mov     [rbp+57h+var_A4], edi
0x18000d3ea  mov     eax, edi
0x18000d3ec  xor     r14d, r14d
0x18000d3ef  test    eax, eax
0x18000d3f1  jns     short loc_18000D3FB
0x18000d3f3  jmp     loc_18000D5E7
0x18000d3f8  xor     r14d, r14d
0x18000d3fb  mov     rcx, [rbp+57h+string]; string
0x18000d3ff  call    cs:__imp_WindowsIsStringEmpty
0x18000d405  mov     [rbp+57h+var_B0], 0FFFFFFFFh
0x18000d40c  lea     rdx, [rbp+57h+var_B0]; int *
0x18000d410  mov     ecx, 8; unsigned __int64
0x18000d415  test    eax, eax
0x18000d417  jz      short loc_18000D457
0x18000d419  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x18000d41e  test    eax, eax
0x18000d420  js      loc_18000D4B0
0x18000d426  cmp     [rbp+57h+var_A4], r14d
0x18000d42a  jl      loc_18000D4B3
0x18000d430  movsxd  rsi, [rbp+57h+var_B0]
0x18000d434  cmp     esi, 4000000h
0x18000d43a  ja      short loc_18000D4B0
0x18000d43c  mov     edx, [rbp+57h+var_A4+4]
0x18000d43f  lea     rcx, [rbp+57h+var_A8]
0x18000d443  add     edx, esi
0x18000d445  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x18000d44a  test    eax, eax
0x18000d44c  js      short loc_18000D4B3
0x18000d44e  lea     rdx, aWmhme1; "?WMHME=1"
0x18000d455  jmp     short loc_18000D48B
0x18000d457  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x18000d45c  test    eax, eax
0x18000d45e  js      short loc_18000D4B0
0x18000d460  cmp     [rbp+57h+var_A4], r14d
0x18000d464  jl      short loc_18000D4B3
0x18000d466  movsxd  rsi, [rbp+57h+var_B0]
0x18000d46a  cmp     esi, 4000000h
0x18000d470  ja      short loc_18000D4B0
0x18000d472  mov     edx, [rbp+57h+var_A4+4]
0x18000d475  lea     rcx, [rbp+57h+var_A8]
0x18000d479  add     edx, esi
0x18000d47b  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x18000d480  test    eax, eax
0x18000d482  js      short loc_18000D4B3
0x18000d484  lea     rdx, aWmhme1_0; "&WMHME=1"
0x18000d48b  mov     rax, [rbp+57h+var_98]
0x18000d48f  mov     r8, rsi
0x18000d492  movsxd  rbx, [rbp+57h+var_A4+4]
0x18000d496  add     r8, r8; Size
0x18000d499  lea     rcx, [rax+rbx*2]; void *
0x18000d49d  call    memcpy_0
0x18000d4a2  lea     edx, [rbx+rsi]
0x18000d4a5  lea     rcx, [rbp+57h+var_A8]
0x18000d4a9  call    ?ReleaseBuffer@?$CMFBaseStringT@G@@QEAAJJ@Z; CMFBaseStringT<ushort>::ReleaseBuffer(long)
0x18000d4ae  jmp     short loc_18000D4B3
0x18000d4b0  mov     [rbp+57h+var_A4], edi
0x18000d4b3  mov     r9d, [rbp+57h+length]
0x18000d4b7  cmp     r9d, 1
0x18000d4bb  ja      short loc_18000D4CF
0x18000d4bd  jnz     loc_18000D54B
0x18000d4c3  mov     eax, 2Ah ; '*'
0x18000d4c8  cmp     ax, [r12]
0x18000d4cd  jz      short loc_18000D54B
0x18000d4cf  lea     rdx, [rbp+57h+var_B0]; int *
0x18000d4d3  mov     [rbp+57h+var_B0], 0FFFFFFFFh
0x18000d4da  mov     ecx, 13h; unsigned __int64
0x18000d4df  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x18000d4e4  test    eax, eax
0x18000d4e6  js      short loc_18000D53C
0x18000d4e8  cmp     [rbp+57h+var_A4], r14d
0x18000d4ec  jl      short loc_18000D53F
0x18000d4ee  movsxd  rsi, [rbp+57h+var_B0]
0x18000d4f2  cmp     esi, 4000000h
0x18000d4f8  ja      short loc_18000D53C
0x18000d4fa  mov     edx, [rbp+57h+var_A4+4]
0x18000d4fd  lea     rcx, [rbp+57h+var_A8]
0x18000d501  add     edx, esi
0x18000d503  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x18000d508  test    eax, eax
0x18000d50a  js      short loc_18000D536
0x18000d50c  mov     rax, [rbp+57h+var_98]
0x18000d510  lea     rdx, aWmcontentfeatu; "&WMContentFeatures="
0x18000d517  movsxd  rbx, [rbp+57h+var_A4+4]
0x18000d51b  mov     r8, rsi
0x18000d51e  add     r8, r8; Size
0x18000d521  lea     rcx, [rax+rbx*2]; void *
0x18000d525  call    memcpy_0
0x18000d52a  lea     edx, [rbx+rsi]
0x18000d52d  lea     rcx, [rbp+57h+var_A8]
0x18000d531  call    ?ReleaseBuffer@?$CMFBaseStringT@G@@QEAAJJ@Z; CMFBaseStringT<ushort>::ReleaseBuffer(long)
0x18000d536  mov     r9d, [rbp+57h+length]
0x18000d53a  jmp     short loc_18000D53F
0x18000d53c  mov     [rbp+57h+var_A4], edi
0x18000d53f  mov     r8, r12
0x18000d542  lea     rcx, [rbp+57h+var_A8]
0x18000d546  call    ?Append@?$CMFBaseStringT@G@@QEAAJIPEBGJ@Z; CMFBaseStringT<ushort>::Append(uint,ushort const *,long)
0x18000d54b  test    r15, r15
0x18000d54e  jz      short loc_18000D5C8
0x18000d550  lea     rdx, [rbp+57h+var_B0]; int *
0x18000d554  mov     [rbp+57h+var_B0], 0FFFFFFFFh
0x18000d55b  mov     ecx, 0Ch; unsigned __int64
0x18000d560  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x18000d565  test    eax, eax
0x18000d567  js      short loc_18000D5B9
0x18000d569  cmp     [rbp+57h+var_A4], r14d
0x18000d56d  jl      short loc_18000D5BC
0x18000d56f  movsxd  rsi, [rbp+57h+var_B0]
0x18000d573  cmp     esi, 4000000h
0x18000d579  ja      short loc_18000D5B9
0x18000d57b  mov     edx, [rbp+57h+var_A4+4]
0x18000d57e  lea     rcx, [rbp+57h+var_A8]
0x18000d582  add     edx, esi
0x18000d584  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x18000d589  test    eax, eax
0x18000d58b  js      short loc_18000D5BC
0x18000d58d  mov     rax, [rbp+57h+var_98]
0x18000d591  lea     rdx, aWmduration; "&WMDuration="
0x18000d598  movsxd  rbx, [rbp+57h+var_A4+4]
0x18000d59c  mov     r8, rsi
0x18000d59f  add     r8, r8; Size
0x18000d5a2  lea     rcx, [rax+rbx*2]; void *
0x18000d5a6  call    memcpy_0
0x18000d5ab  lea     edx, [rbx+rsi]
0x18000d5ae  lea     rcx, [rbp+57h+var_A8]
0x18000d5b2  call    ?ReleaseBuffer@?$CMFBaseStringT@G@@QEAAJJ@Z; CMFBaseStringT<ushort>::ReleaseBuffer(long)
0x18000d5b7  jmp     short loc_18000D5BC
0x18000d5b9  mov     [rbp+57h+var_A4], edi
0x18000d5bc  mov     rdx, r15
0x18000d5bf  lea     rcx, [rbp+57h+var_A8]
0x18000d5c3  call    ?AppendUInt64@?$CMFBaseStringT@G@@QEAAJ_KH@Z; CMFBaseStringT<ushort>::AppendUInt64(unsigned __int64,int)
0x18000d5c8  mov     edi, [rbp+57h+var_A4]
0x18000d5cb  test    edi, edi
0x18000d5cd  js      short loc_18000D5E9
0x18000d5cf  lea     rcx, [rbp+57h+var_A8]
0x18000d5d3  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18000d5d8  mov     edx, [rbp+57h+var_A4+4]; length
0x18000d5db  mov     rcx, rax; sourceString
0x18000d5de  mov     r8, r13; string
0x18000d5e1  call    cs:__imp_WindowsCreateString
0x18000d5e7  mov     edi, eax
0x18000d5e9  lea     rcx, [rbp+57h+var_A8]
0x18000d5ed  call    ??1?$CMFBaseStringT@G@@QEAA@XZ; CMFBaseStringT<ushort>::~CMFBaseStringT<ushort>(void)
0x18000d5f2  lea     rcx, [rbp+57h+var_70]; this
0x18000d5f6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18000d5fb  lea     rcx, [rbp+57h+string]; this
0x18000d5ff  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18000d604  mov     rcx, [rbp+57h+var_88]
0x18000d608  test    rcx, rcx
0x18000d60b  jz      short loc_18000D61D
0x18000d60d  mov     [rbp+57h+var_88], r14
0x18000d611  mov     rax, [rcx]
0x18000d614  mov     rax, [rax+10h]
0x18000d618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d61d  lea     rcx, [rbp+57h+var_78]
0x18000d621  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18000d626  mov     eax, edi
0x18000d628  mov     rcx, [rbp+57h+var_48]
0x18000d62c  xor     rcx, rsp; StackCookie
0x18000d62f  call    __security_check_cookie
0x18000d634  add     rsp, 98h
0x18000d63b  pop     r15
0x18000d63d  pop     r14
0x18000d63f  pop     r13
0x18000d641  pop     r12
0x18000d643  pop     rdi
0x18000d644  pop     rsi
0x18000d645  pop     rbx
0x18000d646  pop     rbp
0x18000d647  retn
```
