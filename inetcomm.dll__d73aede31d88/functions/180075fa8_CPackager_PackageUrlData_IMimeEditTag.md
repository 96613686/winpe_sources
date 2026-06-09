# CPackager::_PackageUrlData(IMimeEditTag *)

- ea: `0x180075fa8`
- end: `0x18007639a`
- name: `?_PackageUrlData@CPackager@@AEAAJPEAUIMimeEditTag@@@Z`
- size: `1010`
- prototype: `__int64 __fastcall(CPackager *__hidden this, struct IMimeEditTag *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180075ef0`

## callees

- `0x1800055bc`
- `0x180021a14`
- `0x1800227b0`
- `0x18002d4b0`
- `0x18002e9b0`
- `0x180052178`
- `0x18006a438`
- `0x18007515c`
- `0x180075e30`
- `0x180075fa8`
- `0x18007643c`
- `0x1800cd010`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x1800762b0`
- `SHLWAPI!PathFindFileNameW` at `0x1800762b0`
- `ole32!CoTaskMemFree` at `0x1800762e2`
- `ole32!CoTaskMemFree` at `0x1800762e2`
- `OLEAUT32!__imp_SysFreeString` at `0x180076350`
- `OLEAUT32!__imp_SysFreeString` at `0x18007637a`
- `OLEAUT32!__imp_SysFreeString` at `0x180076350`
- `OLEAUT32!__imp_SysFreeString` at `0x18007637a`

## pseudocode

```c
__int64 __fastcall CPackager::_PackageUrlData(CPackager *this, struct IMimeEditTag *a2)
{
  __int64 result; // rax
  int v5; // ebx
  unsigned __int16 *v6; // r15
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // r11
  __int64 v10; // rcx
  CPackager *v11; // rcx
  __int64 v12; // rcx
  struct HBODY__ *v13; // r13
  CPackager *v14; // rcx
  __int64 v15; // rsi
  struct IStream *v16; // rbx
  __int64 (__fastcall *v17)(__int64, _QWORD, unsigned __int16 *, _QWORD, struct IStream *, unsigned __int16 **, struct HBODY__ **); // rdi
  int v18; // eax
  CPackager *v19; // rcx
  __int64 v20; // rsi
  struct IStream *v21; // rbx
  __int64 (__fastcall *v22)(__int64, _QWORD, unsigned __int16 *, _QWORD, struct IStream *, unsigned __int16 **, struct HBODY__ **); // rdi
  int ShouldUseContentId; // eax
  LPWSTR FileNameW; // rax
  LPCWSTR pszPath; // [rsp+40h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-18h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int16 *v28; // [rsp+58h] [rbp-8h]
  struct HBODY__ *v29; // [rsp+A8h] [rbp+48h] BYREF
  struct IStream *v30; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int16 *v31; // [rsp+B8h] [rbp+58h] BYREF

  v30 = 0;
  v29 = 0;
  v31 = 0;
  v28 = 0;
  pszPath = 0;
  bstrString = 0;
  pv = 0;
  if ( !a2 )
    return 2147942487LL;
  result = (*(__int64 (__fastcall **)(struct IMimeEditTag *, LPCWSTR *))(*(_QWORD *)a2 + 24LL))(a2, &pszPath);
  v5 = result;
  if ( (int)result >= 0 )
  {
    v6 = (unsigned __int16 *)pszPath;
    if ( pszPath )
    {
      v7 = -1;
      do
        ++v7;
      while ( pszPath[v7] );
      v8 = *((_QWORD *)this + 5);
      if ( !v8
        || (*(unsigned int (__fastcall **)(__int64, LPCWSTR, _QWORD, struct HBODY__ **))(*(_QWORD *)v8 + 40LL))(
             v8,
             pszPath,
             0,
             &v29) )
      {
        if ( (unsigned int)IsMHTMLUrlW(v6) )
        {
          if ( (int)MimeOleParseMhtmlUrlW(v6) >= 0 )
          {
            StringCchCopyW(v6, (unsigned int)(v7 + 1), v28);
            if ( v9 )
              ((void (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Free)(g_pMalloc, v9);
          }
        }
        v10 = *((_QWORD *)this + 4);
        if ( !v10
          || (*(unsigned int (__fastcall **)(__int64, unsigned __int16 *, _QWORD, struct HBODY__ **))(*(_QWORD *)v10 + 40LL))(
               v10,
               v6,
               0,
               &v29) )
        {
          v12 = *((_QWORD *)this + 2);
          if ( !v12
            || (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 *, _DWORD, struct HBODY__ **))(*(_QWORD *)v12 + 504LL))(
                 v12,
                 0,
                 0,
                 v6,
                 0,
                 &v29) )
          {
            v5 = HrOpenUrlViaCache(v6, &v30);
            if ( v5 >= 0 )
            {
              v5 = SniffStreamForMimeType(v30, (unsigned __int16 **)&pv);
              if ( v5 >= 0 )
              {
                if ( (*(unsigned int (__fastcall **)(struct IMimeEditTag *, LPVOID))(*(_QWORD *)a2 + 80LL))(a2, pv) )
                {
                  v5 = -2147467259;
                }
                else
                {
                  v20 = *((_QWORD *)this + 3);
                  v21 = v30;
                  v22 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, _QWORD, struct IStream *, unsigned __int16 **, struct HBODY__ **))(*(_QWORD *)v20 + 488LL);
                  ShouldUseContentId = CPackager::_ShouldUseContentId(v19, v6);
                  v5 = v22(v20, 0, v6, ShouldUseContentId != 0 ? 4 : 6, v21, &v31, &v29);
                  if ( v5 >= 0 )
                  {
                    FileNameW = PathFindFileNameW(pszPath);
                    if ( FileNameW )
                      MimeOleSetBodyPropW(
                        *((_QWORD *)this + 3),
                        (_DWORD)v29,
                        (unsigned int)"par:content-disposition:filename",
                        0,
                        (__int64)FileNameW);
                  }
                }
                CoTaskMemFree(pv);
              }
              ((void (__fastcall *)(struct IStream *))v30->lpVtbl->Release)(v30);
            }
          }
          else
          {
            v13 = v29;
            if ( !(*(unsigned int (__fastcall **)(_QWORD, struct HBODY__ *, GUID *, struct IStream **))(**((_QWORD **)this + 2) + 128LL))(
                    *((_QWORD *)this + 2),
                    v29,
                    &IID_IStream,
                    &v30) )
            {
              v15 = *((_QWORD *)this + 3);
              v16 = v30;
              v17 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, _QWORD, struct IStream *, unsigned __int16 **, struct HBODY__ **))(*(_QWORD *)v15 + 488LL);
              v18 = CPackager::_ShouldUseContentId(v14, v6);
              v5 = v17(v15, 0, v6, v18 != 0 ? 4 : 6, v16, &v31, &v29);
              ((void (__fastcall *)(struct IStream *))v30->lpVtbl->Release)(v30);
            }
            HrCopyHeader(
              *((struct IMimeMessage **)this + 3),
              v29,
              *((struct IMimeMessage **)this + 2),
              v13,
              (const char *)0x12);
            HrCopyHeader(
              *((struct IMimeMessage **)this + 3),
              v29,
              *((struct IMimeMessage **)this + 2),
              v13,
              (const char *)0x18);
            HrCopyHeader(
              *((struct IMimeMessage **)this + 3),
              v29,
              *((struct IMimeMessage **)this + 2),
              v13,
              "par:content-disposition:filename");
          }
          v11 = (CPackager *)*((_QWORD *)this + 4);
          if ( v11 && v5 >= 0 && v29 )
            v5 = (*(__int64 (__fastcall **)(CPackager *, unsigned __int16 *, struct HBODY__ *, _QWORD))(*(_QWORD *)v11 + 24LL))(
                   v11,
                   v6,
                   v29,
                   0);
        }
        else
        {
          MimeOleGetBodyPropW(*((_QWORD *)this + 3), (_DWORD)v29, 20, 0, (__int64)&v31);
        }
        if ( v31 )
        {
          if ( !CPackager::_CanonicaliseContentId(v11, v31, &bstrString) )
          {
            (*(void (__fastcall **)(struct IMimeEditTag *, BSTR))(*(_QWORD *)a2 + 48LL))(a2, bstrString);
            SysFreeString(bstrString);
          }
          if ( v31 )
          {
            ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
            v31 = 0;
          }
        }
      }
      else
      {
        v5 = 0;
      }
      SysFreeString((BSTR)pszPath);
      return (unsigned int)v5;
    }
    else
    {
      return 2147549183LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180075fa8  mov     [rsp-38h+arg_0], rbx
0x180075fad  push    rbp
0x180075fae  push    rsi
0x180075faf  push    rdi
0x180075fb0  push    r12
0x180075fb2  push    r13
0x180075fb4  push    r14
0x180075fb6  push    r15
0x180075fb8  mov     rbp, rsp
0x180075fbb  sub     rsp, 60h
0x180075fbf  xor     esi, esi
0x180075fc1  mov     r12, rdx
0x180075fc4  mov     [rbp+arg_10], rsi
0x180075fc8  mov     r14, rcx
0x180075fcb  mov     [rbp+arg_8], rsi
0x180075fcf  mov     [rbp+arg_18], rsi
0x180075fd3  mov     [rbp+var_8], rsi
0x180075fd7  mov     [rbp+pszPath], rsi
0x180075fdb  mov     [rbp+bstrString], rsi
0x180075fdf  mov     [rbp+pv], rsi
0x180075fe3  test    rdx, rdx
0x180075fe6  jnz     short loc_180075FF2
0x180075fe8  mov     eax, 80070057h
0x180075fed  jmp     loc_180076382
0x180075ff2  mov     rax, [rdx]
0x180075ff5  mov     rcx, r12
0x180075ff8  lea     rdx, [rbp+pszPath]
0x180075ffc  mov     rax, [rax+18h]
0x180076000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076005  mov     ebx, eax
0x180076007  test    eax, eax
0x180076009  js      loc_180076382
0x18007600f  mov     r15, [rbp+pszPath]
0x180076013  test    r15, r15
0x180076016  jnz     short loc_180076022
0x180076018  mov     eax, 8000FFFFh
0x18007601d  jmp     loc_180076382
0x180076022  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180076026  inc     rdi
0x180076029  cmp     [r15+rdi*2], si
0x18007602e  jnz     short loc_180076026
0x180076030  mov     rcx, [r14+28h]
0x180076034  test    rcx, rcx
0x180076037  jz      short loc_18007605A
0x180076039  mov     rax, [rcx]
0x18007603c  lea     r9, [rbp+arg_8]
0x180076040  xor     r8d, r8d
0x180076043  mov     rdx, r15
0x180076046  mov     rax, [rax+28h]
0x18007604a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007604f  test    eax, eax
0x180076051  jnz     short loc_18007605A
0x180076053  mov     ebx, esi
0x180076055  jmp     loc_180076376
0x18007605a  mov     rcx, r15; psz1
0x18007605d  call    ?IsMHTMLUrlW@@YAHPEBG@Z; IsMHTMLUrlW(ushort const *)
0x180076062  test    eax, eax
0x180076064  jz      short loc_1800760A5
0x180076066  lea     r8, [rbp+var_8]
0x18007606a  xor     edx, edx
0x18007606c  mov     rcx, r15; psz1
0x18007606f  call    MimeOleParseMhtmlUrlW
0x180076074  test    eax, eax
0x180076076  js      short loc_1800760A5
0x180076078  mov     r11, [rbp+var_8]
0x18007607c  lea     edx, [rdi+1]; unsigned __int64
0x18007607f  mov     r8, r11; unsigned __int16 *
0x180076082  mov     rcx, r15; unsigned __int16 *
0x180076085  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007608a  test    r11, r11
0x18007608d  jz      short loc_1800760A5
0x18007608f  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180076096  mov     rdx, r11
0x180076099  mov     rax, [rcx]
0x18007609c  mov     rax, [rax+28h]
0x1800760a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800760a5  mov     rcx, [r14+20h]
0x1800760a9  test    rcx, rcx
0x1800760ac  jz      short loc_1800760EA
0x1800760ae  mov     rax, [rcx]
0x1800760b1  lea     r9, [rbp+arg_8]
0x1800760b5  xor     r8d, r8d
0x1800760b8  mov     rdx, r15
0x1800760bb  mov     rax, [rax+28h]
0x1800760bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800760c4  test    eax, eax
0x1800760c6  jnz     short loc_1800760EA
0x1800760c8  mov     rdx, [rbp+arg_8]
0x1800760cc  lea     rax, [rbp+arg_18]
0x1800760d0  mov     rcx, [r14+18h]
0x1800760d4  xor     r9d, r9d
0x1800760d7  mov     [rsp+60h+var_40], rax
0x1800760dc  lea     r8d, [r9+14h]
0x1800760e0  call    MimeOleGetBodyPropW
0x1800760e5  jmp     loc_180076322
0x1800760ea  mov     rcx, [r14+10h]
0x1800760ee  test    rcx, rcx
0x1800760f1  jz      loc_18007620D
0x1800760f7  mov     rax, [rcx]
0x1800760fa  lea     rdx, [rbp+arg_8]
0x1800760fe  mov     [rsp+60h+var_38], rdx
0x180076103  mov     r9, r15
0x180076106  xor     r8d, r8d
0x180076109  mov     dword ptr [rsp+60h+var_40], esi
0x18007610d  xor     edx, edx
0x18007610f  mov     rax, [rax+1F8h]
0x180076116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007611b  test    eax, eax
0x18007611d  jnz     loc_18007620D
0x180076123  mov     rcx, [r14+10h]
0x180076127  lea     r9, [rbp+arg_10]
0x18007612b  mov     r13, [rbp+arg_8]
0x18007612f  lea     r8, IID_IStream
0x180076136  mov     rdx, r13
0x180076139  mov     rax, [rcx]
0x18007613c  mov     rax, [rax+80h]
0x180076143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076148  test    eax, eax
0x18007614a  jnz     short loc_1800761AE
0x18007614c  mov     rsi, [r14+18h]
0x180076150  mov     rdx, r15; unsigned __int16 *
0x180076153  mov     rbx, [rbp+arg_10]
0x180076157  mov     rax, [rsi]
0x18007615a  mov     rdi, [rax+1E8h]
0x180076161  call    ?_ShouldUseContentId@CPackager@@AEAAJPEBG@Z; CPackager::_ShouldUseContentId(ushort const *)
0x180076166  neg     eax
0x180076168  mov     r8, r15
0x18007616b  lea     rax, [rbp+arg_8]
0x18007616f  mov     rcx, rsi
0x180076172  mov     [rsp+60h+var_30], rax
0x180076177  sbb     r9d, r9d
0x18007617a  lea     rax, [rbp+arg_18]
0x18007617e  and     r9d, 0FFFFFFFEh
0x180076182  mov     [rsp+60h+var_38], rax
0x180076187  add     r9d, 6
0x18007618b  mov     rax, rdi
0x18007618e  mov     [rsp+60h+var_40], rbx
0x180076193  xor     edx, edx
0x180076195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007619a  mov     rcx, [rbp+arg_10]
0x18007619e  mov     ebx, eax
0x1800761a0  mov     rax, [rcx]
0x1800761a3  mov     rax, [rax+10h]
0x1800761a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800761ac  xor     esi, esi
0x1800761ae  mov     r8, [r14+10h]; struct IMimeMessage *
0x1800761b2  mov     r9, r13; struct HBODY__ *
0x1800761b5  mov     rdx, [rbp+arg_8]; struct HBODY__ *
0x1800761b9  mov     rcx, [r14+18h]; struct IMimeMessage *
0x1800761bd  mov     [rsp+60h+var_40], 12h; char *
0x1800761c6  call    ?HrCopyHeader@@YAJPEAUIMimeMessage@@PEAUHBODY__@@01PEBD@Z; HrCopyHeader(IMimeMessage *,HBODY__ *,IMimeMessage *,HBODY__ *,char const *)
0x1800761cb  mov     r8, [r14+10h]; struct IMimeMessage *
0x1800761cf  mov     r9, r13; struct HBODY__ *
0x1800761d2  mov     rdx, [rbp+arg_8]; struct HBODY__ *
0x1800761d6  mov     rcx, [r14+18h]; struct IMimeMessage *
0x1800761da  mov     [rsp+60h+var_40], 18h; char *
0x1800761e3  call    ?HrCopyHeader@@YAJPEAUIMimeMessage@@PEAUHBODY__@@01PEBD@Z; HrCopyHeader(IMimeMessage *,HBODY__ *,IMimeMessage *,HBODY__ *,char const *)
0x1800761e8  mov     rdx, [rbp+arg_8]; struct HBODY__ *
0x1800761ec  lea     r8, STR_PAR_FILENAME; "par:content-disposition:filename"
0x1800761f3  mov     rcx, [r14+18h]; struct IMimeMessage *
0x1800761f7  mov     r9, r13; struct HBODY__ *
0x1800761fa  mov     [rsp+60h+var_40], r8; char *
0x1800761ff  mov     r8, [r14+10h]; struct IMimeMessage *
0x180076203  call    ?HrCopyHeader@@YAJPEAUIMimeMessage@@PEAUHBODY__@@01PEBD@Z; HrCopyHeader(IMimeMessage *,HBODY__ *,IMimeMessage *,HBODY__ *,char const *)
0x180076208  jmp     loc_1800762F8
0x18007620d  lea     rdx, [rbp+arg_10]; struct IStream **
0x180076211  mov     rcx, r15; unsigned __int16 *
0x180076214  call    ?HrOpenUrlViaCache@@YAJPEBGPEAPEAUIStream@@@Z; HrOpenUrlViaCache(ushort const *,IStream * *)
0x180076219  mov     ebx, eax
0x18007621b  test    eax, eax
0x18007621d  js      loc_1800762F8
0x180076223  mov     rcx, [rbp+arg_10]; struct IStream *
0x180076227  lea     rdx, [rbp+pv]; unsigned __int16 **
0x18007622b  call    ?SniffStreamForMimeType@@YAJPEAUIStream@@PEAPEAG@Z; SniffStreamForMimeType(IStream *,ushort * *)
0x180076230  mov     ebx, eax
0x180076232  test    eax, eax
0x180076234  js      loc_1800762E8
0x18007623a  mov     rax, [r12]
0x18007623e  mov     rcx, r12
0x180076241  mov     rdx, [rbp+pv]
0x180076245  mov     rax, [rax+50h]
0x180076249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007624e  test    eax, eax
0x180076250  jnz     loc_1800762D9
0x180076256  mov     rsi, [r14+18h]
0x18007625a  mov     rdx, r15; unsigned __int16 *
0x18007625d  mov     rbx, [rbp+arg_10]
0x180076261  mov     rax, [rsi]
0x180076264  mov     rdi, [rax+1E8h]
0x18007626b  call    ?_ShouldUseContentId@CPackager@@AEAAJPEBG@Z; CPackager::_ShouldUseContentId(ushort const *)
0x180076270  neg     eax
0x180076272  mov     r8, r15
0x180076275  lea     rax, [rbp+arg_8]
0x180076279  mov     rcx, rsi
0x18007627c  mov     [rsp+60h+var_30], rax
0x180076281  sbb     r9d, r9d
0x180076284  lea     rax, [rbp+arg_18]
0x180076288  and     r9d, 0FFFFFFFEh
0x18007628c  mov     [rsp+60h+var_38], rax
0x180076291  add     r9d, 6
0x180076295  mov     rax, rdi
0x180076298  mov     [rsp+60h+var_40], rbx
0x18007629d  xor     edx, edx
0x18007629f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800762a4  xor     esi, esi
0x1800762a6  mov     ebx, eax
0x1800762a8  test    eax, eax
0x1800762aa  js      short loc_1800762DE
0x1800762ac  mov     rcx, [rbp+pszPath]; pszPath
0x1800762b0  call    cs:__imp_PathFindFileNameW
0x1800762b6  test    rax, rax
0x1800762b9  jz      short loc_1800762DE
0x1800762bb  mov     rdx, [rbp+arg_8]
0x1800762bf  lea     r8, STR_PAR_FILENAME; "par:content-disposition:filename"
0x1800762c6  mov     rcx, [r14+18h]
0x1800762ca  xor     r9d, r9d
0x1800762cd  mov     [rsp+60h+var_40], rax
0x1800762d2  call    MimeOleSetBodyPropW
0x1800762d7  jmp     short loc_1800762DE
0x1800762d9  mov     ebx, 80004005h
0x1800762de  mov     rcx, [rbp+pv]; pv
0x1800762e2  call    cs:__imp_CoTaskMemFree
0x1800762e8  mov     rcx, [rbp+arg_10]
0x1800762ec  mov     rax, [rcx]
0x1800762ef  mov     rax, [rax+10h]
0x1800762f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800762f8  mov     rcx, [r14+20h]
0x1800762fc  test    rcx, rcx
0x1800762ff  jz      short loc_180076322
0x180076301  test    ebx, ebx
0x180076303  js      short loc_180076322
0x180076305  mov     r8, [rbp+arg_8]
0x180076309  test    r8, r8
0x18007630c  jz      short loc_180076322
0x18007630e  mov     rax, [rcx]
0x180076311  xor     r9d, r9d
0x180076314  mov     rdx, r15
0x180076317  mov     rax, [rax+18h]
0x18007631b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076320  mov     ebx, eax
0x180076322  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x180076326  test    rdx, rdx
0x180076329  jz      short loc_180076376
0x18007632b  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x18007632f  call    ?_CanonicaliseContentId@CPackager@@AEAAJPEAGPEAPEAG@Z; CPackager::_CanonicaliseContentId(ushort *,ushort * *)
0x180076334  test    eax, eax
0x180076336  jnz     short loc_180076356
0x180076338  mov     rax, [r12]
0x18007633c  mov     rcx, r12
0x18007633f  mov     rdx, [rbp+bstrString]
0x180076343  mov     rax, [rax+30h]
0x180076347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007634c  mov     rcx, [rbp+bstrString]; bstrString
0x180076350  call    cs:__imp_SysFreeString
0x180076356  mov     rdx, [rbp+arg_18]
0x18007635a  test    rdx, rdx
0x18007635d  jz      short loc_180076376
0x18007635f  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180076366  mov     rax, [rcx]
0x180076369  mov     rax, [rax+28h]
0x18007636d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076372  mov     [rbp+arg_18], rsi
0x180076376  mov     rcx, [rbp+pszPath]; bstrString
0x18007637a  call    cs:__imp_SysFreeString
0x180076380  mov     eax, ebx
0x180076382  mov     rbx, [rsp+60h+arg_0]
0x18007638a  add     rsp, 60h
0x18007638e  pop     r15
0x180076390  pop     r14
0x180076392  pop     r13
0x180076394  pop     r12
0x180076396  pop     rdi
0x180076397  pop     rsi
0x180076398  pop     rbp
0x180076399  retn
```
