# CClipboardMobileDataObject::GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x1801faa00`
- end: `0x1801fad94`
- name: `?GetData@CClipboardMobileDataObject@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `916`
- prototype: `__int64 __fastcall(CClipboardMobileDataObject *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18006ad18`
- `0x18013ce80`
- `0x18013dcce`
- `0x180150d6c`
- `0x1801fa44c`
- `0x1801fa6e0`
- `0x1801faa00`
- `0x1801fb230`
- `0x1801fb2f4`
- `0x1801fb364`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1801faa9d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1801faa9d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1801fabac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1801fabac`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1801face7`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1801face7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801fabce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801fabce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fad49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fad62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fad49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fad62`

## pseudocode

```c
__int64 __fastcall CClipboardMobileDataObject::GetData(
        CClipboardMobileDataObject *this,
        struct tagFORMATETC *a2,
        struct tagSTGMEDIUM *a3)
{
  unsigned int v5; // ebx
  __int16 v6; // r14
  __int64 *v7; // rax
  __int64 v8; // rsi
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  PCWSTR StringRawBuffer; // rax
  PCWSTR v12; // rbx
  int v13; // ecx
  _QWORD *v14; // rdx
  _QWORD *v15; // rdx
  HBITMAP v16; // rdi
  UINT32 v17; // r14d
  HBITMAP v18; // rax
  __int64 v20; // [rsp+30h] [rbp-99h] BYREF
  HANDLE hHandle; // [rsp+38h] [rbp-91h] BYREF
  UINT32 length; // [rsp+40h] [rbp-89h] BYREF
  HSTRING string; // [rsp+48h] [rbp-81h] BYREF
  HSTRING v24; // [rsp+50h] [rbp-79h] BYREF
  __int64 v25; // [rsp+58h] [rbp-71h] BYREF
  _QWORD v26[2]; // [rsp+60h] [rbp-69h] BYREF
  _QWORD v27[7]; // [rsp+70h] [rbp-59h] BYREF
  _QWORD *v28; // [rsp+A8h] [rbp-21h]
  _QWORD v29[7]; // [rsp+B0h] [rbp-19h] BYREF
  _QWORD *v30; // [rsp+E8h] [rbp+1Fh]

  *(_OWORD *)&a3->tymed = 0;
  a3->pUnkForRelease = 0;
  v24 = 0;
  string = 0;
  v5 = CClipboardMobileDataObject::SupportsFormatEtc(this, a2, (struct Microsoft::WRL::Wrappers::HString *)&v24);
  if ( !v5 )
  {
    v6 = SupportedFormat(v24);
    if ( v6 == 1038 )
    {
      v5 = (*(__int64 (__fastcall **)(CClipboardMobileDataObject *, struct tagSTGMEDIUM *))(*(_QWORD *)this + 96LL))(
             this,
             a3);
      goto LABEL_34;
    }
    hHandle = CreateEventExW(0, 0, 1u, 0x1F0003u);
    if ( !hHandle )
    {
      CEventWrapper::~CEventWrapper((CEventWrapper *)&hHandle);
      v5 = -2147418113;
      goto LABEL_34;
    }
    v20 = 0;
    v26[0] = &hHandle;
    v26[1] = &string;
    v7 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_HSTRING_____::___Windows::Foundation::IAsyncOperation_HSTRING________enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::IAsyncOperationCompletedHandler_HSTRING______Microsoft::WRL::FtmBase___lambda_3e59cf71de9fa25b6f7d6f3697c38bba_____1_Windows::Foundation::IAsyncOperation_HSTRING________enum_ABI::Windows::Foundation::AsyncStatus___lambda_3e59cf71de9fa25b6f7d6f3697c38bba____(
                      &v25,
                      v26);
    v8 = *v7;
    *v7 = 0;
    if ( v25 )
    {
      v25 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>>::Release();
    }
    if ( !v8 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
      CEventWrapper::~CEventWrapper((CEventWrapper *)&hHandle);
      v5 = -2147467259;
      goto LABEL_34;
    }
    if ( v6 == 13 )
    {
      v9 = *((_QWORD *)this + 1);
      v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 96LL);
    }
    else
    {
      if ( v6 != 1026 )
      {
LABEL_15:
        v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 48LL))(v20, v8);
        if ( !v5 )
        {
          WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
          v26[0] = 0;
          length = 0;
          StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
          v12 = StringRawBuffer;
          if ( !StringRawBuffer )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
            CEventWrapper::~CEventWrapper((CEventWrapper *)&hHandle);
            v5 = -2147024882;
            goto LABEL_34;
          }
          if ( v6 == 13 )
            goto LABEL_29;
          if ( length < 3 )
            goto LABEL_23;
          v13 = 1953651835 - *(_DWORD *)StringRawBuffer;
          if ( *(_DWORD *)StringRawBuffer == 1953651835 )
            v13 = 12646 - StringRawBuffer[2];
          if ( !v13 )
          {
LABEL_29:
            v17 = 2 * length + 2;
            v18 = (HBITMAP)GlobalAlloc(0x40u, (int)v17);
            v16 = v18;
            if ( !v18 )
            {
              v5 = -2147024882;
              goto LABEL_33;
            }
            memcpy_0(v18, v12, v17 - 2LL);
          }
          else
          {
LABEL_23:
            v29[0] = off_18028BF58;
            v30 = v29;
            v27[0] = off_18028BF28;
            v28 = v27;
            StringUtil::ConvertFromUnicodeRtf(
              (_DWORD)StringRawBuffer,
              length,
              (unsigned int)v26,
              (unsigned int)v27,
              (__int64)v29);
            if ( v28 )
            {
              v14 = v27;
              LOBYTE(v14) = v28 != v27;
              (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v28 + 32LL))(v28, v14);
              v28 = 0;
            }
            if ( v30 )
            {
              v15 = v29;
              LOBYTE(v15) = v30 != v29;
              (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v30 + 32LL))(v30, v15);
            }
            v16 = (HBITMAP)v26[0];
            if ( !v26[0] )
            {
              v5 = -2147467259;
              goto LABEL_33;
            }
          }
          v5 = 0;
          a3->tymed = 1;
          a3->hBitmap = v16;
        }
LABEL_33:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
        CEventWrapper::~CEventWrapper((CEventWrapper *)&hHandle);
        goto LABEL_34;
      }
      v9 = *((_QWORD *)this + 1);
      v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 136LL);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    v5 = v10(v9, &v20);
    if ( v5 )
      goto LABEL_33;
    goto LABEL_15;
  }
LABEL_34:
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v24);
  return v5;
}

```

## disassembly

```asm
0x1801faa00  mov     [rsp-8+arg_8], rbx
0x1801faa05  push    rbp
0x1801faa06  push    rsi
0x1801faa07  push    rdi
0x1801faa08  push    r14
0x1801faa0a  push    r15
0x1801faa0c  lea     rbp, [rsp-37h]
0x1801faa11  sub     rsp, 100h
0x1801faa18  mov     rax, cs:__security_cookie
0x1801faa1f  xor     rax, rsp
0x1801faa22  mov     [rbp+57h+var_30], rax
0x1801faa26  xor     eax, eax
0x1801faa28  xorps   xmm0, xmm0
0x1801faa2b  movups  xmmword ptr [r8], xmm0
0x1801faa2f  mov     [r8+10h], rax
0x1801faa33  mov     r15, r8
0x1801faa36  lea     r8, [rbp+57h+var_D0]; struct Microsoft::WRL::Wrappers::HString *
0x1801faa3a  mov     [rbp+57h+var_D0], rax
0x1801faa3e  mov     rdi, rcx
0x1801faa41  mov     [rsp+120h+string], rax
0x1801faa46  call    ?SupportsFormatEtc@CClipboardMobileDataObject@@AEAAJPEBUtagFORMATETC@@AEAVHString@Wrappers@WRL@Microsoft@@@Z; CClipboardMobileDataObject::SupportsFormatEtc(tagFORMATETC const *,Microsoft::WRL::Wrappers::HString &)
0x1801faa4b  mov     ebx, eax
0x1801faa4d  test    eax, eax
0x1801faa4f  jnz     loc_1801FAD44
0x1801faa55  mov     rcx, [rbp+57h+var_D0]
0x1801faa59  call    SupportedFormat
0x1801faa5e  movzx   r14d, ax
0x1801faa62  mov     eax, 40Eh
0x1801faa67  cmp     r14w, ax
0x1801faa6b  jnz     short loc_1801FAA86
0x1801faa6d  mov     rax, [rdi]
0x1801faa70  mov     rdx, r15
0x1801faa73  mov     rcx, rdi
0x1801faa76  mov     rax, [rax+60h]
0x1801faa7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801faa7f  mov     ebx, eax
0x1801faa81  jmp     loc_1801FAD44
0x1801faa86  xor     edx, edx; lpName
0x1801faa88  mov     [rsp+120h+hHandle], 0
0x1801faa91  xor     ecx, ecx; lpEventAttributes
0x1801faa93  mov     r9d, 1F0003h; dwDesiredAccess
0x1801faa99  lea     r8d, [rdx+1]; dwFlags
0x1801faa9d  call    cs:__imp_CreateEventExW
0x1801faaa4  nop     dword ptr [rax+rax+00h]
0x1801faaa9  mov     [rsp+120h+hHandle], rax
0x1801faaae  test    rax, rax
0x1801faab1  jnz     short loc_1801FAAC7
0x1801faab3  lea     rcx, [rsp+120h+hHandle]; this
0x1801faab8  call    ??1CEventWrapper@@QEAA@XZ; CEventWrapper::~CEventWrapper(void)
0x1801faabd  mov     ebx, 8000FFFFh
0x1801faac2  jmp     loc_1801FAD44
0x1801faac7  lea     rax, [rsp+120h+hHandle]
0x1801faacc  mov     [rsp+120h+var_F0], 0
0x1801faad5  mov     [rbp+57h+var_C0], rax
0x1801faad9  lea     rdx, [rbp+57h+var_C0]
0x1801faadd  lea     rax, [rsp+120h+string]
0x1801faae2  lea     rcx, [rbp+57h+var_C8]
0x1801faae6  mov     [rbp+57h+var_B8], rax
0x1801faaea  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__IAsyncOperationCompletedHandler_impl_HSTRING__________Windows__Foundation__IAsyncOperation_HSTRING________enum_ABI__Windows__Foundation__AsyncStatus____DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__Foundation__IAsyncOperationCompletedHandler_HSTRING______Microsoft__WRL__FtmBase___lambda_3e59cf71de9fa25b6f7d6f3697c38bba_____1_Windows__Foundation__IAsyncOperation_HSTRING________enum_ABI__Windows__Foundation__AsyncStatus___lambda_3e59cf71de9fa25b6f7d6f3697c38bba____
0x1801faaef  mov     rsi, [rax]
0x1801faaf2  mov     qword ptr [rax], 0
0x1801faaf9  mov     rcx, [rbp+57h+var_C8]
0x1801faafd  test    rcx, rcx
0x1801fab00  jz      short loc_1801FAB0F
0x1801fab02  mov     [rbp+57h+var_C8], 0
0x1801fab0a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>>::Release(void)
0x1801fab0f  test    rsi, rsi
0x1801fab12  jnz     short loc_1801FAB32
0x1801fab14  lea     rcx, [rsp+120h+var_F0]
0x1801fab19  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fab1e  lea     rcx, [rsp+120h+hHandle]; this
0x1801fab23  call    ??1CEventWrapper@@QEAA@XZ; CEventWrapper::~CEventWrapper(void)
0x1801fab28  mov     ebx, 80004005h
0x1801fab2d  jmp     loc_1801FAD44
0x1801fab32  cmp     r14w, 0Dh
0x1801fab37  jz      short loc_1801FAB54
0x1801fab39  mov     eax, 402h
0x1801fab3e  cmp     r14w, ax
0x1801fab42  jnz     short loc_1801FAB83
0x1801fab44  mov     rdi, [rdi+8]
0x1801fab48  mov     rax, [rdi]
0x1801fab4b  mov     rbx, [rax+88h]
0x1801fab52  jmp     short loc_1801FAB5F
0x1801fab54  mov     rdi, [rdi+8]
0x1801fab58  mov     rax, [rdi]
0x1801fab5b  mov     rbx, [rax+60h]
0x1801fab5f  lea     rcx, [rsp+120h+var_F0]
0x1801fab64  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fab69  lea     rdx, [rsp+120h+var_F0]
0x1801fab6e  mov     rcx, rdi
0x1801fab71  mov     rax, rbx
0x1801fab74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fab79  mov     ebx, eax
0x1801fab7b  test    eax, eax
0x1801fab7d  jnz     loc_1801FAD21
0x1801fab83  mov     rcx, [rsp+120h+var_F0]
0x1801fab88  mov     rdx, rsi
0x1801fab8b  mov     rax, [rcx]
0x1801fab8e  mov     rax, [rax+30h]
0x1801fab92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fab97  mov     ebx, eax
0x1801fab99  test    eax, eax
0x1801fab9b  jnz     loc_1801FAD21
0x1801faba1  mov     rcx, [rsp+120h+hHandle]; hHandle
0x1801faba6  xor     r8d, r8d; bAlertable
0x1801faba9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1801fabac  call    cs:__imp_WaitForSingleObjectEx
0x1801fabb3  nop     dword ptr [rax+rax+00h]
0x1801fabb8  mov     rcx, [rsp+120h+string]; string
0x1801fabbd  lea     rdx, [rsp+120h+length]; length
0x1801fabc2  mov     [rbp+57h+var_C0], 0
0x1801fabca  mov     [rsp+120h+length], ebx
0x1801fabce  call    cs:__imp_WindowsGetStringRawBuffer
0x1801fabd5  nop     dword ptr [rax+rax+00h]
0x1801fabda  mov     rbx, rax
0x1801fabdd  test    rax, rax
0x1801fabe0  jnz     short loc_1801FAC0F
0x1801fabe2  mov     rax, [rsi]
0x1801fabe5  mov     rcx, rsi
0x1801fabe8  mov     rax, [rax+10h]
0x1801fabec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fabf1  lea     rcx, [rsp+120h+var_F0]
0x1801fabf6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fabfb  lea     rcx, [rsp+120h+hHandle]; this
0x1801fac00  call    ??1CEventWrapper@@QEAA@XZ; CEventWrapper::~CEventWrapper(void)
0x1801fac05  mov     ebx, 8007000Eh
0x1801fac0a  jmp     loc_1801FAD44
0x1801fac0f  mov     edx, [rsp+120h+length]
0x1801fac13  cmp     r14w, 0Dh
0x1801fac18  jz      loc_1801FACD7
0x1801fac1e  cmp     edx, 3
0x1801fac21  jb      short loc_1801FAC42
0x1801fac23  mov     ecx, cs:dword_1802C41F8
0x1801fac29  sub     ecx, [rax]
0x1801fac2b  jnz     short loc_1801FAC3A
0x1801fac2d  movzx   ecx, cs:word_1802C41FC
0x1801fac34  movzx   eax, word ptr [rax+4]
0x1801fac38  sub     ecx, eax
0x1801fac3a  test    ecx, ecx
0x1801fac3c  jz      loc_1801FACD7
0x1801fac42  lea     rax, off_18028BF58
0x1801fac49  mov     rcx, rbx
0x1801fac4c  mov     [rbp+57h+var_70], rax
0x1801fac50  lea     r9, [rbp+57h+var_B0]
0x1801fac54  lea     rax, [rbp+57h+var_70]
0x1801fac58  mov     [rbp+57h+var_38], rax
0x1801fac5c  lea     r8, [rbp+57h+var_C0]
0x1801fac60  lea     rax, off_18028BF28
0x1801fac67  mov     [rbp+57h+var_B0], rax
0x1801fac6b  lea     rax, [rbp+57h+var_B0]
0x1801fac6f  mov     [rbp+57h+var_78], rax
0x1801fac73  lea     rax, [rbp+57h+var_70]
0x1801fac77  mov     [rsp+120h+var_100], rax
0x1801fac7c  call    ?ConvertFromUnicodeRtf@StringUtil@@SAXPEBGIPEAPEADAEBV?$function@$$A6APEADAEBI@Z@std@@AEBV?$function@$$A6AXPEAD@Z@3@@Z; StringUtil::ConvertFromUnicodeRtf(ushort const *,uint,char * *,std::function<char * (uint const &)> const &,std::function<void (char *)> const &)
0x1801fac81  mov     rcx, [rbp+57h+var_78]
0x1801fac85  test    rcx, rcx
0x1801fac88  jz      short loc_1801FACA8
0x1801fac8a  mov     rax, [rcx]
0x1801fac8d  lea     rdx, [rbp+57h+var_B0]
0x1801fac91  cmp     rcx, rdx
0x1801fac94  setnz   dl
0x1801fac97  mov     rax, [rax+20h]
0x1801fac9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801faca0  mov     [rbp+57h+var_78], 0
0x1801faca8  mov     rcx, [rbp+57h+var_38]
0x1801facac  test    rcx, rcx
0x1801facaf  jz      short loc_1801FACC7
0x1801facb1  mov     rax, [rcx]
0x1801facb4  lea     rdx, [rbp+57h+var_70]
0x1801facb8  cmp     rcx, rdx
0x1801facbb  setnz   dl
0x1801facbe  mov     rax, [rax+20h]
0x1801facc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801facc7  mov     rdi, [rbp+57h+var_C0]
0x1801faccb  test    rdi, rdi
0x1801facce  jnz     short loc_1801FAD14
0x1801facd0  mov     ebx, 80004005h
0x1801facd5  jmp     short loc_1801FAD21
0x1801facd7  lea     r14d, ds:2[rdx*2]
0x1801facdf  mov     ecx, 40h ; '@'; uFlags
0x1801face4  movsxd  rdx, r14d; dwBytes
0x1801face7  call    cs:__imp_GlobalAlloc
0x1801facee  nop     dword ptr [rax+rax+00h]
0x1801facf3  mov     rdi, rax
0x1801facf6  test    rax, rax
0x1801facf9  jnz     short loc_1801FAD02
0x1801facfb  mov     ebx, 8007000Eh
0x1801fad00  jmp     short loc_1801FAD21
0x1801fad02  mov     r8d, r14d
0x1801fad05  mov     rdx, rbx; Src
0x1801fad08  sub     r8, 2; Size
0x1801fad0c  mov     rcx, rax; void *
0x1801fad0f  call    memcpy_0
0x1801fad14  xor     ebx, ebx
0x1801fad16  mov     dword ptr [r15], 1
0x1801fad1d  mov     [r15+8], rdi
0x1801fad21  mov     rax, [rsi]
0x1801fad24  mov     rcx, rsi
0x1801fad27  mov     rax, [rax+10h]
0x1801fad2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fad30  lea     rcx, [rsp+120h+var_F0]
0x1801fad35  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fad3a  lea     rcx, [rsp+120h+hHandle]; this
0x1801fad3f  call    ??1CEventWrapper@@QEAA@XZ; CEventWrapper::~CEventWrapper(void)
0x1801fad44  mov     rcx, [rsp+120h+string]; string
0x1801fad49  call    cs:__imp_WindowsDeleteString
0x1801fad50  nop     dword ptr [rax+rax+00h]
0x1801fad55  mov     rcx, [rbp+57h+var_D0]; string
0x1801fad59  mov     [rsp+120h+string], 0
0x1801fad62  call    cs:__imp_WindowsDeleteString
0x1801fad69  nop     dword ptr [rax+rax+00h]
0x1801fad6e  mov     eax, ebx
0x1801fad70  mov     rcx, [rbp+57h+var_30]
0x1801fad74  xor     rcx, rsp; StackCookie
0x1801fad77  call    __security_check_cookie
0x1801fad7c  mov     rbx, [rsp+120h+arg_8]
0x1801fad84  add     rsp, 100h
0x1801fad8b  pop     r15
0x1801fad8d  pop     r14
0x1801fad8f  pop     rdi
0x1801fad90  pop     rsi
0x1801fad91  pop     rbp
0x1801fad92  retn
```
