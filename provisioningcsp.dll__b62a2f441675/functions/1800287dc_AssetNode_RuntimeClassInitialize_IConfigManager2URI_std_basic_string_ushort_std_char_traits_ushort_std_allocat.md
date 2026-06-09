# AssetNode::RuntimeClassInitialize(IConfigManager2URI *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::unique_ptr<IElement,ProvReleaser<IElement>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,int,int)

- ea: `0x1800287dc`
- end: `0x180028eb4`
- name: `?RuntimeClassInitialize@AssetNode@@QEAAJPEAUIConfigManager2URI@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_ptr@UIElement@@U?$ProvReleaser@UIElement@@@@@4@V34@HH@Z`
- size: `1752`
- prototype: `__int64 __fastcall(int, int, int, int, LPCWSTR lpFileName, int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180026840`

## callees

- `0x180001b14`
- `0x180001cf0`
- `0x180006974`
- `0x18000848c`
- `0x180009eb0`
- `0x18000fd40`
- `0x180028360`
- `0x180028514`
- `0x1800287dc`
- `0x180028ee8`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180028ad4`
- `msvcrt!_wcsicmp` at `0x180028ad4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028866`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800288bb`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028920`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002898e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028a7d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028aa9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028b31`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028b5d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028c2d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028c59`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028cd1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028cfd`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028d35`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028dd5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028e0d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028e39`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028e68`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028866`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800288bb`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028920`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002898e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028a7d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028aa9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028b31`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028b5d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028c2d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028c59`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028cd1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028cfd`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028d35`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028dd5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028e0d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028e39`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028e68`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180028c8b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180028c8b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180028cab`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180028cab`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall AssetNode::RuntimeClassInitialize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        WCHAR *lpFileName,
        unsigned int a6,
        int a7)
{
  int v9; // eax
  unsigned int v10; // esi
  __int64 result; // rax
  int v12; // eax
  unsigned int v13; // esi
  int v14; // eax
  unsigned int v15; // esi
  WCHAR *v16; // rsi
  __int64 v17; // r12
  void *v18; // r14
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // r8
  int v22; // r9d
  unsigned int v23; // r15d
  int v24; // eax
  unsigned int v25; // r15d
  int HasAccess; // eax
  unsigned int v27; // r15d
  WCHAR *v28; // r8
  int v29; // eax
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  unsigned int v33; // r15d
  WCHAR *v34; // rax
  const WCHAR *v35; // rcx
  DWORD FileAttributesW; // eax
  const WCHAR *v37; // rcx
  unsigned int v38; // esi
  unsigned int v39; // [rsp+20h] [rbp-A8h]
  WCHAR *v40; // [rsp+30h] [rbp-98h] BYREF
  int v41; // [rsp+38h] [rbp-90h] BYREF
  wchar_t *String1; // [rsp+40h] [rbp-88h] BYREF
  WCHAR *v43; // [rsp+48h] [rbp-80h] BYREF
  unsigned int v44[2]; // [rsp+50h] [rbp-78h] BYREF
  unsigned __int64 v45; // [rsp+58h] [rbp-70h] BYREF
  __int128 v46; // [rsp+60h] [rbp-68h] BYREF
  __int64 v47; // [rsp+70h] [rbp-58h]
  WCHAR *v48; // [rsp+78h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  *(_QWORD *)v44 = a1;
  v48 = lpFileName;
  String1 = 0;
  v41 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 136LL))(a2, &v41);
  v10 = v9;
  if ( v9 >= 0 )
  {
    if ( v41 == 1 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t **))(*(_QWORD *)a2 + 88LL))(a2, 0, &String1);
      v13 = v12;
      if ( v12 >= 0 )
      {
        v43 = 0;
        v40 = 0;
        v14 = (*(__int64 (__fastcall **)(_QWORD, WCHAR **))(*(_QWORD *)*a4 + 64LL))(*a4, &v40);
        v15 = v14;
        if ( v14 >= 0 )
        {
          v16 = 0;
          if ( v40 )
            v16 = v40;
          v43 = v16;
          v46 = 0;
          v17 = 0;
          v47 = 0;
          v45 = 0;
          v18 = 0;
          do
          {
            v19 = (**(__int64 (__fastcall ***)(WCHAR *, unsigned __int64 *))v16)(v16, &v45);
            v23 = v19;
            if ( v19 < 0 )
            {
              if ( v19 == -2147024637 )
              {
                if ( v18 )
                  operator delete(v18);
                if ( v16 )
                  (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v16 + 16LL))(v16);
                if ( (unsigned int)dword_1800495B0 > 2
                  && (qword_1800495C0 & 0x400000000000LL) != 0
                  && (qword_1800495C8 & 0x400000000000LL) == qword_1800495C8 )
                {
                  *(_QWORD *)v44 = String1;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                    qword_1800495C8,
                    (unsigned int)byte_18004176D,
                    v21,
                    v22,
                    (__int64)v44);
                }
                v38 = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0xAA,
                        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetnode.cpp",
                        (const char *)2,
                        v39);
                if ( *((_QWORD *)lpFileName + 3) >= 8u )
                  operator delete(*(void **)lpFileName);
                result = v38;
                *((_QWORD *)lpFileName + 3) = 7;
                *((_QWORD *)lpFileName + 2) = 0;
                *lpFileName = 0;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xA1,
                  (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetnode.cpp",
                  (const char *)(unsigned int)v19,
                  v39);
                if ( v18 )
                  operator delete(v18);
                if ( v16 )
                  (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v16 + 16LL))(v16);
                if ( *((_QWORD *)lpFileName + 3) >= 8u )
                  operator delete(*(void **)lpFileName);
                *((_QWORD *)lpFileName + 3) = 7;
                *((_QWORD *)lpFileName + 2) = 0;
                *lpFileName = 0;
                return v23;
              }
              return result;
            }
            if ( v45 > (v17 - (__int64)v18) >> 1 )
            {
              if ( v45 > 0x7FFFFFFFFFFFFFFFLL )
                std::vector<std::unique_ptr<ProvPackage>>::_Xlen(v20, v45, v21);
              std::vector<unsigned short>::_Reallocate(&v46, v45);
              v17 = v47;
              v18 = (void *)v46;
            }
            v24 = (*(__int64 (__fastcall **)(WCHAR *, void *, __int64))(*(_QWORD *)v16 + 8LL))(
                    v16,
                    v18,
                    (v17 - (__int64)v18) >> 1);
            v25 = v24;
            if ( v24 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x84,
                (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetnode.cpp",
                (const char *)(unsigned int)v24,
                v39);
              if ( v18 )
                operator delete(v18);
              if ( v16 )
                (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v16 + 16LL))(v16);
              if ( *((_QWORD *)lpFileName + 3) >= 8u )
                operator delete(*(void **)lpFileName);
              *((_QWORD *)lpFileName + 3) = 7;
              *((_QWORD *)lpFileName + 2) = 0;
              *lpFileName = 0;
              return v25;
            }
          }
          while ( _wcsicmp(String1, (const wchar_t *)v18) );
          EnsureDirectoryExists((__int64)lpFileName);
          if ( a7 )
          {
            HasAccess = EnsureSessionUserHasAccess();
            v27 = HasAccess;
            if ( HasAccess < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x8B,
                (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetnode.cpp",
                (const char *)(unsigned int)HasAccess,
                v39);
              if ( v18 )
                operator delete(v18);
              if ( v16 )
                (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v16 + 16LL))(v16);
              if ( *((_QWORD *)lpFileName + 3) >= 8u )
                operator delete(*(void **)lpFileName);
              *((_QWORD *)lpFileName + 3) = 7;
              *((_QWORD *)lpFileName + 2) = 0;
              *lpFileName = 0;
              return v27;
            }
          }
          if ( *((_QWORD *)lpFileName + 3) < 8u )
            v28 = lpFileName;
          else
            v28 = *(WCHAR **)lpFileName;
          v29 = (*(__int64 (__fastcall **)(_QWORD, void *, WCHAR *, _QWORD))(*(_QWORD *)*a4 + 48LL))(*a4, v18, v28, a6);
          v33 = v29;
          if ( v29 == -2147024816 )
          {
            if ( (unsigned int)dword_1800495B0 > 3 )
            {
              LODWORD(v40) = -2147024816;
              if ( *((_QWORD *)lpFileName + 3) < 8u )
                v34 = lpFileName;
              else
                v34 = *(WCHAR **)lpFileName;
              v43 = v34;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                v30,
                (unsigned int)word_1800417AA,
                v31,
                v32,
                (__int64)&v43,
                (__int64)&v40);
            }
            v33 = 1;
            goto LABEL_60;
          }
          if ( v29 >= 0 )
          {
LABEL_60:
            if ( *((_QWORD *)lpFileName + 3) < 8u )
              v35 = lpFileName;
            else
              v35 = *(const WCHAR **)lpFileName;
            FileAttributesW = GetFileAttributesW(v35);
            if ( *((_QWORD *)lpFileName + 3) < 8u )
              v37 = lpFileName;
            else
              v37 = *(const WCHAR **)lpFileName;
            SetFileAttributesW(v37, FileAttributesW | 1);
            std::wstring::operator=((void *)(*(_QWORD *)v44 + 24LL), lpFileName);
            if ( v18 )
              operator delete(v18);
            if ( v16 )
              (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v16 + 16LL))(v16);
            if ( *((_QWORD *)lpFileName + 3) >= 8u )
              operator delete(*(void **)lpFileName);
            *((_QWORD *)lpFileName + 3) = 7;
            *((_QWORD *)lpFileName + 2) = 0;
            *lpFileName = 0;
            return v33;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x98,
            (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetnode.cpp",
            (const char *)(unsigned int)v29,
            v39);
          if ( v18 )
            operator delete(v18);
          if ( v16 )
            (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v16 + 16LL))(v16);
          if ( *((_QWORD *)lpFileName + 3) >= 8u )
            operator delete(*(void **)lpFileName);
          *((_QWORD *)lpFileName + 3) = 7;
          *((_QWORD *)lpFileName + 2) = 0;
          *lpFileName = 0;
          return v33;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x75,
            (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetnode.cpp",
            (const char *)(unsigned int)v14,
            v39);
          if ( *((_QWORD *)lpFileName + 3) >= 8u )
            operator delete(*(void **)lpFileName);
          *((_QWORD *)lpFileName + 3) = 7;
          *((_QWORD *)lpFileName + 2) = 0;
          *lpFileName = 0;
          return v15;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6F,
          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetnode.cpp",
          (const char *)(unsigned int)v12,
          v39);
        if ( *((_QWORD *)lpFileName + 3) >= 8u )
          operator delete(*(void **)lpFileName);
        *((_QWORD *)lpFileName + 3) = 7;
        *((_QWORD *)lpFileName + 2) = 0;
        *lpFileName = 0;
        return v13;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetnode.cpp",
        (const char *)0x80070057LL,
        v39);
      if ( *((_QWORD *)lpFileName + 3) >= 8u )
        operator delete(*(void **)lpFileName);
      *((_QWORD *)lpFileName + 3) = 7;
      *((_QWORD *)lpFileName + 2) = 0;
      *lpFileName = 0;
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetnode.cpp",
      (const char *)(unsigned int)v9,
      v39);
    if ( *((_QWORD *)lpFileName + 3) >= 8u )
      operator delete(*(void **)lpFileName);
    *((_QWORD *)lpFileName + 3) = 7;
    *((_QWORD *)lpFileName + 2) = 0;
    *lpFileName = 0;
    return v10;
  }
}

```

## disassembly

```asm
0x1800287dc  push    rbx
0x1800287de  push    rsi
0x1800287df  push    rdi
0x1800287e0  push    r12
0x1800287e2  push    r13
0x1800287e4  push    r14
0x1800287e6  push    r15
0x1800287e8  sub     rsp, 90h
0x1800287ef  mov     rax, cs:__security_cookie
0x1800287f6  xor     rax, rsp
0x1800287f9  mov     [rsp+0C8h+var_48], rax
0x180028801  mov     r13, r9
0x180028804  mov     r14, rdx
0x180028807  mov     qword ptr [rsp+0C8h+var_78], rcx
0x18002880c  mov     rdi, [rsp+0C8h+lpFileName]
0x180028814  mov     [rsp+0C8h+var_50], rdi
0x180028819  xor     ebx, ebx
0x18002881b  mov     [rsp+0C8h+String1], rbx
0x180028820  mov     [rsp+0C8h+var_90], ebx
0x180028824  mov     rax, [rdx]
0x180028827  lea     rdx, [rsp+0C8h+var_90]
0x18002882c  mov     rcx, r14
0x18002882f  mov     rax, [rax+88h]
0x180028836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002883b  mov     esi, eax
0x18002883d  test    eax, eax
0x18002883f  jns     short loc_180028888
0x180028841  mov     rcx, [rsp+0C8h]; this
0x180028849  mov     r9d, eax; char *
0x18002884c  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180028853  lea     edx, [rbx+6Dh]; void *
0x180028856  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002885b  nop
0x18002885c  cmp     qword ptr [rdi+18h], 8
0x180028861  jb      short loc_180028872
0x180028863  mov     rcx, [rdi]
0x180028866  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002886d  nop     dword ptr [rax+rax+00h]
0x180028872  mov     qword ptr [rdi+18h], 7
0x18002887a  mov     [rdi+10h], rbx
0x18002887e  mov     [rdi], bx
0x180028881  mov     eax, esi
0x180028883  jmp     loc_180028E89
0x180028888  cmp     [rsp+0C8h+var_90], 1
0x18002888d  jz      short loc_1800288DD
0x18002888f  mov     rcx, [rsp+0C8h]; this
0x180028897  mov     esi, 80070057h
0x18002889c  mov     r9d, esi; char *
0x18002889f  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x1800288a6  mov     edx, 6Eh ; 'n'; void *
0x1800288ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800288b0  nop
0x1800288b1  cmp     qword ptr [rdi+18h], 8
0x1800288b6  jb      short loc_1800288C7
0x1800288b8  mov     rcx, [rdi]
0x1800288bb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800288c2  nop     dword ptr [rax+rax+00h]
0x1800288c7  mov     qword ptr [rdi+18h], 7
0x1800288cf  mov     [rdi+10h], rbx
0x1800288d3  mov     [rdi], bx
0x1800288d6  mov     eax, esi
0x1800288d8  jmp     loc_180028E89
0x1800288dd  mov     rax, [r14]
0x1800288e0  lea     r8, [rsp+0C8h+String1]
0x1800288e5  xor     edx, edx
0x1800288e7  mov     rcx, r14
0x1800288ea  mov     rax, [rax+58h]
0x1800288ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288f3  mov     esi, eax
0x1800288f5  test    eax, eax
0x1800288f7  jns     short loc_180028942
0x1800288f9  mov     rcx, [rsp+0C8h]; this
0x180028901  mov     r9d, eax; char *
0x180028904  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x18002890b  mov     edx, 6Fh ; 'o'; void *
0x180028910  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028915  nop
0x180028916  cmp     qword ptr [rdi+18h], 8
0x18002891b  jb      short loc_18002892C
0x18002891d  mov     rcx, [rdi]
0x180028920  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180028927  nop     dword ptr [rax+rax+00h]
0x18002892c  mov     qword ptr [rdi+18h], 7
0x180028934  mov     [rdi+10h], rbx
0x180028938  mov     [rdi], bx
0x18002893b  mov     eax, esi
0x18002893d  jmp     loc_180028E89
0x180028942  mov     [rsp+0C8h+var_80], rbx
0x180028947  mov     [rsp+0C8h+var_98], rbx
0x18002894c  mov     rcx, [r13+0]
0x180028950  mov     rax, [rcx]
0x180028953  lea     rdx, [rsp+0C8h+var_98]
0x180028958  mov     rax, [rax+40h]
0x18002895c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028961  mov     esi, eax
0x180028963  test    eax, eax
0x180028965  jns     short loc_1800289B0
0x180028967  mov     rcx, [rsp+0C8h]; this
0x18002896f  mov     r9d, eax; char *
0x180028972  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180028979  mov     edx, 75h ; 'u'; void *
0x18002897e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028983  nop
0x180028984  cmp     qword ptr [rdi+18h], 8
0x180028989  jb      short loc_18002899A
0x18002898b  mov     rcx, [rdi]
0x18002898e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180028995  nop     dword ptr [rax+rax+00h]
0x18002899a  mov     qword ptr [rdi+18h], 7
0x1800289a2  mov     [rdi+10h], rbx
0x1800289a6  mov     [rdi], bx
0x1800289a9  mov     eax, esi
0x1800289ab  jmp     loc_180028E89
0x1800289b0  mov     rsi, rbx
0x1800289b3  cmp     [rsp+0C8h+var_98], rbx
0x1800289b8  cmovnz  rsi, [rsp+0C8h+var_98]
0x1800289be  mov     [rsp+0C8h+var_80], rsi
0x1800289c3  xorps   xmm0, xmm0
0x1800289c6  movdqu  [rsp+0C8h+var_68], xmm0
0x1800289cc  mov     r12, rbx
0x1800289cf  mov     [rsp+0C8h+var_58], rbx
0x1800289d4  mov     [rsp+0C8h+var_70], rbx
0x1800289d9  movq    r14, xmm0
0x1800289de  mov     rax, [rsi]
0x1800289e1  lea     rdx, [rsp+0C8h+var_70]
0x1800289e6  mov     rcx, rsi
0x1800289e9  mov     rax, [rax]
0x1800289ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289f1  mov     r15d, eax
0x1800289f4  test    eax, eax
0x1800289f6  js      loc_180028D20
0x1800289fc  mov     rax, r12
0x1800289ff  sub     rax, r14
0x180028a02  sar     rax, 1
0x180028a05  mov     rdx, [rsp+0C8h+var_70]
0x180028a0a  cmp     rdx, rax
0x180028a0d  jbe     short loc_180028A36
0x180028a0f  mov     rax, 7FFFFFFFFFFFFFFFh
0x180028a19  cmp     rdx, rax
0x180028a1c  ja      loc_180028EAD
0x180028a22  lea     rcx, [rsp+0C8h+var_68]
0x180028a27  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x180028a2c  mov     r12, [rsp+0C8h+var_58]
0x180028a31  mov     r14, qword ptr [rsp+0C8h+var_68]
0x180028a36  mov     rax, [rsi]
0x180028a39  mov     r8, r12
0x180028a3c  sub     r8, r14
0x180028a3f  sar     r8, 1
0x180028a42  mov     rdx, r14
0x180028a45  mov     rcx, rsi
0x180028a48  mov     rax, [rax+8]
0x180028a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a51  mov     r15d, eax
0x180028a54  test    eax, eax
0x180028a56  jns     short loc_180028ACC
0x180028a58  mov     rcx, [rsp+0C8h]; this
0x180028a60  mov     r9d, eax; char *
0x180028a63  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180028a6a  mov     edx, 84h; void *
0x180028a6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028a74  nop
0x180028a75  test    r14, r14
0x180028a78  jz      short loc_180028A8A
0x180028a7a  mov     rcx, r14
0x180028a7d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180028a84  nop     dword ptr [rax+rax+00h]
0x180028a89  nop
0x180028a8a  test    rsi, rsi
0x180028a8d  jz      short loc_180028A9F
0x180028a8f  mov     rax, [rsi]
0x180028a92  mov     rcx, rsi
0x180028a95  mov     rax, [rax+10h]
0x180028a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a9e  nop
0x180028a9f  cmp     qword ptr [rdi+18h], 8
0x180028aa4  jb      short loc_180028AB5
0x180028aa6  mov     rcx, [rdi]
0x180028aa9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180028ab0  nop     dword ptr [rax+rax+00h]
0x180028ab5  mov     qword ptr [rdi+18h], 7
0x180028abd  mov     [rdi+10h], rbx
0x180028ac1  mov     [rdi], bx
0x180028ac4  mov     eax, r15d
0x180028ac7  jmp     loc_180028E89
0x180028acc  mov     rdx, r14; String2
0x180028acf  mov     rcx, [rsp+0C8h+String1]; String1
0x180028ad4  call    cs:__imp__wcsicmp
0x180028adb  nop     dword ptr [rax+rax+00h]
0x180028ae0  test    eax, eax
0x180028ae2  jnz     loc_1800289DE
0x180028ae8  mov     rcx, rdi
0x180028aeb  call    EnsureDirectoryExists
0x180028af0  cmp     [rsp+0C8h+arg_30], ebx
0x180028af7  jz      loc_180028B80
0x180028afd  mov     rcx, rdi
0x180028b00  call    EnsureSessionUserHasAccess
0x180028b05  mov     r15d, eax
0x180028b08  test    eax, eax
0x180028b0a  jns     short loc_180028B80
0x180028b0c  mov     rcx, [rsp+0C8h]; this
0x180028b14  mov     r9d, eax; char *
0x180028b17  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180028b1e  mov     edx, 8Bh; void *
0x180028b23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028b28  nop
0x180028b29  test    r14, r14
0x180028b2c  jz      short loc_180028B3E
0x180028b2e  mov     rcx, r14
0x180028b31  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180028b38  nop     dword ptr [rax+rax+00h]
0x180028b3d  nop
0x180028b3e  test    rsi, rsi
0x180028b41  jz      short loc_180028B53
0x180028b43  mov     rax, [rsi]
0x180028b46  mov     rcx, rsi
0x180028b49  mov     rax, [rax+10h]
0x180028b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b52  nop
0x180028b53  cmp     qword ptr [rdi+18h], 8
0x180028b58  jb      short loc_180028B69
0x180028b5a  mov     rcx, [rdi]
0x180028b5d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180028b64  nop     dword ptr [rax+rax+00h]
0x180028b69  mov     qword ptr [rdi+18h], 7
0x180028b71  mov     [rdi+10h], rbx
0x180028b75  mov     [rdi], bx
0x180028b78  mov     eax, r15d
0x180028b7b  jmp     loc_180028E89
0x180028b80  mov     rcx, [r13+0]
0x180028b84  mov     rax, [rcx]
0x180028b87  cmp     qword ptr [rdi+18h], 8
0x180028b8c  jb      short loc_180028B93
0x180028b8e  mov     r8, [rdi]
0x180028b91  jmp     short loc_180028B96
0x180028b93  mov     r8, rdi
0x180028b96  mov     r9d, [rsp+0C8h+arg_28]
0x180028b9e  mov     rdx, r14
0x180028ba1  mov     rax, [rax+30h]
0x180028ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028baa  mov     r15d, eax
0x180028bad  cmp     eax, 80070050h
0x180028bb2  jnz     short loc_180028C03
0x180028bb4  mov     eax, cs:dword_1800495B0
0x180028bba  cmp     eax, 3
0x180028bbd  jbe     short loc_180028BFB
0x180028bbf  mov     dword ptr [rsp+0C8h+var_98], 80070050h
0x180028bc7  cmp     qword ptr [rdi+18h], 8
0x180028bcc  jb      short loc_180028BD3
0x180028bce  mov     rax, [rdi]
0x180028bd1  jmp     short loc_180028BD6
0x180028bd3  mov     rax, rdi
0x180028bd6  mov     [rsp+0C8h+var_80], rax
0x180028bdb  lea     rax, [rsp+0C8h+var_98]
0x180028be0  mov     [rsp+0C8h+var_A0], rax
0x180028be5  lea     rax, [rsp+0C8h+var_80]
0x180028bea  mov     qword ptr [rsp+0C8h+var_A8], rax
0x180028bef  lea     rdx, word_1800417AA
0x180028bf6  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180028bfb  mov     r15d, 1
0x180028c01  jmp     short loc_180028C7C
0x180028c03  test    r15d, r15d
0x180028c06  jns     short loc_180028C7C
0x180028c08  mov     rcx, [rsp+0C8h]; this
0x180028c10  mov     r9d, r15d; char *
0x180028c13  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180028c1a  mov     edx, 98h; void *
0x180028c1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028c24  nop
0x180028c25  test    r14, r14
0x180028c28  jz      short loc_180028C3A
0x180028c2a  mov     rcx, r14
0x180028c2d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180028c34  nop     dword ptr [rax+rax+00h]
0x180028c39  nop
0x180028c3a  test    rsi, rsi
0x180028c3d  jz      short loc_180028C4F
0x180028c3f  mov     rax, [rsi]
0x180028c42  mov     rcx, rsi
0x180028c45  mov     rax, [rax+10h]
0x180028c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c4e  nop
0x180028c4f  cmp     qword ptr [rdi+18h], 8
0x180028c54  jb      short loc_180028C65
0x180028c56  mov     rcx, [rdi]
0x180028c59  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180028c60  nop     dword ptr [rax+rax+00h]
0x180028c65  mov     qword ptr [rdi+18h], 7
0x180028c6d  mov     [rdi+10h], rbx
0x180028c71  mov     [rdi], bx
0x180028c74  mov     eax, r15d
0x180028c77  jmp     loc_180028E89
0x180028c7c  cmp     qword ptr [rdi+18h], 8
0x180028c81  jb      short loc_180028C88
0x180028c83  mov     rcx, [rdi]
0x180028c86  jmp     short loc_180028C8B
0x180028c88  mov     rcx, rdi; lpFileName
0x180028c8b  call    cs:__imp_GetFileAttributesW
0x180028c92  nop     dword ptr [rax+rax+00h]
0x180028c97  cmp     qword ptr [rdi+18h], 8
0x180028c9c  jb      short loc_180028CA3
  ... truncated ...
```
