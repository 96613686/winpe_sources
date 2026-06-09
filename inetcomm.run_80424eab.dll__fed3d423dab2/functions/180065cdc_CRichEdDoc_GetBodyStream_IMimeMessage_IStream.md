# CRichEdDoc::_GetBodyStream(IMimeMessage *,IStream * *)

- ea: `0x180065cdc`
- end: `0x18006600e`
- name: `?_GetBodyStream@CRichEdDoc@@AEAAJPEAUIMimeMessage@@PEAPEAUIStream@@@Z`
- size: `818`
- prototype: `__int64 __fastcall(CRichEdDoc *__hidden this, struct IMimeMessage *, struct IStream **)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180064ec0`

## callees

- `0x180002098`
- `0x180005748`
- `0x18002d690`
- `0x180065cdc`
- `0x1800660bc`
- `0x180066220`
- `0x18006f720`
- `0x1800cc9a2`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `msvcrt!free` at `0x180065f84`
- `msvcrt!free` at `0x180065f84`
- `msvcrt!calloc` at `0x180065ee0`
- `msvcrt!calloc` at `0x180065ee0`
- `MSOERT2!HrCopyStream` at `0x180065e65`
- `MSOERT2!HrCopyStream` at `0x180065e65`
- `MSOERT2!HrLPSZCPToBSTR` at `0x180065f29`
- `MSOERT2!HrLPSZCPToBSTR` at `0x180065f29`
- `MSOERT2!HrStreamToByte` at `0x180065e8e`
- `MSOERT2!HrStreamToByte` at `0x180065e8e`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x180065ddf`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x180065ddf`
- `SHLWAPI!__imp_IStream_Reset` at `0x180065e4a`
- `SHLWAPI!__imp_IStream_Reset` at `0x180065e4a`
- `OLEAUT32!__imp_SysFreeString` at `0x180065f74`
- `OLEAUT32!__imp_SysFreeString` at `0x180065f74`

## pseudocode

```c
__int64 __fastcall CRichEdDoc::_GetBodyStream(
        CRichEdDoc *this,
        __int64 (__fastcall ***a2)(struct IMimeMessage *, GUID *, struct IMimeMessageW **),
        struct IStream **a3)
{
  __int64 (__fastcall **v4)(struct IMimeMessage *, GUID *, struct IMimeMessageW **); // rax
  __int64 (__fastcall *v7)(struct IMimeMessage *, GUID *, struct IMimeMessageW **); // rax
  HRESULT WebPageOptions; // ebx
  IStream *v9; // rax
  struct IStream *v10; // rsi
  void *v11; // r14
  unsigned __int64 v12; // r15
  void *v13; // rax
  void *v14; // rdi
  __int64 v15; // r8
  void *Src; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h] BYREF
  IStream *pstm; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  IStream *v21; // [rsp+50h] [rbp-B0h] BYREF
  struct IMimeMessageW *v22; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  size_t Size; // [rsp+68h] [rbp-98h] BYREF
  __int128 v25; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+80h] [rbp-80h]
  _BYTE v27[140]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v28; // [rsp+11Ch] [rbp+1Ch]

  v26 = 0;
  v4 = *a2;
  v20 = 0;
  pstm = 0;
  v21 = 0;
  v7 = *v4;
  LODWORD(Src) = 0;
  v25 = 0;
  LODWORD(bstrString) = 0;
  v22 = 0;
  v23 = 0;
  WebPageOptions = v7((struct IMimeMessage *)a2, &IID_IMimeMessageW, &v22);
  if ( WebPageOptions >= 0 )
  {
    WebPageOptions = CRichEdDoc::_GetWebPageOptions(
                       this,
                       (struct tagWEBPAGEOPTIONS *)&v25,
                       (int *)&Src,
                       (unsigned int *)&bstrString);
    if ( WebPageOptions >= 0 )
    {
      if ( (_DWORD)Src )
      {
        WebPageOptions = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(struct IMimeMessage *, GUID *, struct IMimeMessageW **), _QWORD, __int128 *, _QWORD, __int64 *))(*a2)[38])(
                           a2,
                           0,
                           &v25,
                           0,
                           &v23);
        if ( WebPageOptions >= 0 )
        {
          WebPageOptions = GetStreamFromMoniker(v23, &v20);
          if ( WebPageOptions >= 0 )
          {
            v9 = SHCreateMemStream(0, 0);
            v21 = v9;
            v10 = v9;
            if ( v9 )
            {
              if ( !(_DWORD)bstrString
                || (WebPageOptions = ((__int64 (__fastcall *)(IStream *, const char *, __int64, _QWORD))v9->lpVtbl->Write)(
                                       v9,
                                       "\r\n\r\n",
                                       4,
                                       0),
                    WebPageOptions >= 0)
                && (WebPageOptions = GetHeaderTable(v22, 0, 0x81000000, &pstm), WebPageOptions >= 0)
                && (WebPageOptions = IStream_Reset(pstm), WebPageOptions >= 0)
                && (WebPageOptions = HrCopyStream(v10, pstm, 0), WebPageOptions >= 0) )
              {
                Src = 0;
                Size = 0;
                WebPageOptions = HrStreamToByte(v20, &Src, &Size);
                if ( WebPageOptions >= 0 )
                {
                  v11 = Src;
                  if ( Src )
                  {
                    v12 = Size;
                    if ( Size )
                    {
                      memset_0(v27, 0, 0x98u);
                      if ( v12 + 1 >= v12 && (v13 = calloc(v12 + 2, 1u), (v14 = v13) != 0) )
                      {
                        memcpy_0(v13, v11, v12);
                        WebPageOptions = MimeOleGetCharsetInfo(*((_QWORD *)this + 94), v27);
                        if ( WebPageOptions >= 0 )
                        {
                          bstrString = 0;
                          if ( (int)HrLPSZCPToBSTR(v28, v14, &bstrString) >= 0 && bstrString )
                          {
                            v15 = -1;
                            do
                              ++v15;
                            while ( bstrString[v15] );
                            WebPageOptions = ((__int64 (__fastcall *)(struct IStream *, BSTR, _QWORD, _QWORD))v10->lpVtbl->Write)(
                                               v10,
                                               bstrString,
                                               (unsigned int)(2 * v15),
                                               0);
                            if ( WebPageOptions >= 0 )
                            {
                              *a3 = v10;
                              v21 = 0;
                            }
                            SysFreeString(bstrString);
                          }
                          else
                          {
                            WebPageOptions = -2147024882;
                          }
                        }
                        free(v14);
                        v11 = Src;
                      }
                      else
                      {
                        WebPageOptions = -2147024882;
                      }
                      ((void (__fastcall *)(LPMALLOC, void *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v11);
                    }
                  }
                }
              }
            }
            else
            {
              WebPageOptions = -2147024882;
            }
          }
        }
      }
    }
  }
  OE_SafeReleaseAndNullPtr<IStream>(&v20);
  OE_SafeReleaseAndNullPtr<IStream>(&pstm);
  OE_SafeReleaseAndNullPtr<IStream>(&v21);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v22);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v23);
  return (unsigned int)WebPageOptions;
}

```

## disassembly

```asm
0x180065cdc  mov     [rsp-8+arg_18], rbx
0x180065ce1  push    rbp
0x180065ce2  push    rsi
0x180065ce3  push    rdi
0x180065ce4  push    r12
0x180065ce6  push    r13
0x180065ce8  push    r14
0x180065cea  push    r15
0x180065cec  lea     rbp, [rsp-40h]
0x180065cf1  sub     rsp, 140h
0x180065cf8  mov     rax, cs:__security_cookie
0x180065cff  xor     rax, rsp
0x180065d02  mov     [rbp+70h+var_40], rax
0x180065d06  xor     r15d, r15d
0x180065d09  xor     eax, eax
0x180065d0b  mov     [rbp+70h+var_F0], eax
0x180065d0e  mov     rdi, rdx
0x180065d11  mov     rax, [rdx]
0x180065d14  mov     r12, r8
0x180065d17  mov     r13, rcx
0x180065d1a  mov     [rsp+170h+var_128], r15
0x180065d1f  xorps   xmm0, xmm0
0x180065d22  mov     [rsp+170h+pstm], r15
0x180065d27  lea     r8, [rsp+170h+var_118]
0x180065d2c  mov     [rsp+170h+var_120], r15
0x180065d31  mov     rax, [rax]
0x180065d34  lea     rdx, IID_IMimeMessageW
0x180065d3b  mov     rcx, rdi
0x180065d3e  mov     dword ptr [rsp+170h+Src], r15d
0x180065d43  movups  [rsp+170h+var_100], xmm0
0x180065d48  mov     dword ptr [rsp+170h+bstrString], r15d
0x180065d4d  mov     [rsp+170h+var_118], r15
0x180065d52  mov     [rsp+170h+var_110], r15
0x180065d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d5c  mov     ebx, eax
0x180065d5e  test    eax, eax
0x180065d60  js      loc_180065FB3
0x180065d66  lea     r9, [rsp+170h+bstrString]; unsigned int *
0x180065d6b  mov     rcx, r13; this
0x180065d6e  lea     r8, [rsp+170h+Src]; int *
0x180065d73  lea     rdx, [rsp+170h+var_100]; struct tagWEBPAGEOPTIONS *
0x180065d78  call    ?_GetWebPageOptions@CRichEdDoc@@AEAAJPEAUtagWEBPAGEOPTIONS@@PEAHPEAK@Z; CRichEdDoc::_GetWebPageOptions(tagWEBPAGEOPTIONS *,int *,ulong *)
0x180065d7d  mov     ebx, eax
0x180065d7f  test    eax, eax
0x180065d81  js      loc_180065FB3
0x180065d87  cmp     dword ptr [rsp+170h+Src], r15d
0x180065d8c  jz      loc_180065FB3
0x180065d92  mov     rax, [rdi]
0x180065d95  lea     rcx, [rsp+170h+var_110]
0x180065d9a  mov     [rsp+170h+var_150], rcx
0x180065d9f  lea     r8, [rsp+170h+var_100]
0x180065da4  xor     r9d, r9d
0x180065da7  xor     edx, edx
0x180065da9  mov     rcx, rdi
0x180065dac  mov     rax, [rax+130h]
0x180065db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065db8  mov     ebx, eax
0x180065dba  test    eax, eax
0x180065dbc  js      loc_180065FB3
0x180065dc2  mov     rcx, [rsp+170h+var_110]
0x180065dc7  lea     rdx, [rsp+170h+var_128]
0x180065dcc  call    _GetStreamFromMoniker
0x180065dd1  mov     ebx, eax
0x180065dd3  test    eax, eax
0x180065dd5  js      loc_180065FB3
0x180065ddb  xor     edx, edx; cbInit
0x180065ddd  xor     ecx, ecx; pInit
0x180065ddf  call    cs:__imp_SHCreateMemStream
0x180065de5  mov     [rsp+170h+var_120], rax
0x180065dea  mov     rsi, rax
0x180065ded  test    rax, rax
0x180065df0  jz      loc_180065FAE
0x180065df6  cmp     dword ptr [rsp+170h+bstrString], r15d
0x180065dfb  jz      short loc_180065E75
0x180065dfd  mov     rcx, [rax]
0x180065e00  lea     r8d, [r15+4]
0x180065e04  xor     r9d, r9d
0x180065e07  lea     rdx, asc_1800DCCD8; "\r\n\r\n"
0x180065e0e  mov     rax, [rcx+20h]
0x180065e12  mov     rcx, rsi
0x180065e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e1a  mov     ebx, eax
0x180065e1c  test    eax, eax
0x180065e1e  js      loc_180065FB3
0x180065e24  mov     rcx, [rsp+170h+var_118]; struct IMimeMessageW *
0x180065e29  lea     r9, [rsp+170h+pstm]; struct IStream **
0x180065e2e  xor     edx, edx; unsigned __int16 *
0x180065e30  mov     r8d, 81000000h; unsigned int
0x180065e36  call    ?GetHeaderTable@@YAJPEAUIMimeMessageW@@PEAGKPEAPEAUIStream@@@Z; GetHeaderTable(IMimeMessageW *,ushort *,ulong,IStream * *)
0x180065e3b  mov     ebx, eax
0x180065e3d  test    eax, eax
0x180065e3f  js      loc_180065FB3
0x180065e45  mov     rcx, [rsp+170h+pstm]; pstm
0x180065e4a  call    cs:__imp_IStream_Reset
0x180065e50  mov     ebx, eax
0x180065e52  test    eax, eax
0x180065e54  js      loc_180065FB3
0x180065e5a  mov     rdx, [rsp+170h+pstm]
0x180065e5f  xor     r8d, r8d
0x180065e62  mov     rcx, rsi
0x180065e65  call    cs:__imp_HrCopyStream
0x180065e6b  mov     ebx, eax
0x180065e6d  test    eax, eax
0x180065e6f  js      loc_180065FB3
0x180065e75  mov     rcx, [rsp+170h+var_128]
0x180065e7a  lea     r8, [rsp+170h+Size]
0x180065e7f  lea     rdx, [rsp+170h+Src]
0x180065e84  mov     [rsp+170h+Src], r15
0x180065e89  mov     [rsp+170h+Size], r15
0x180065e8e  call    cs:__imp_HrStreamToByte
0x180065e94  mov     ebx, eax
0x180065e96  test    eax, eax
0x180065e98  js      loc_180065FB3
0x180065e9e  mov     r14, [rsp+170h+Src]
0x180065ea3  test    r14, r14
0x180065ea6  jz      loc_180065FB3
0x180065eac  mov     r15, [rsp+170h+Size]
0x180065eb1  test    r15, r15
0x180065eb4  jz      loc_180065FB3
0x180065eba  xor     edx, edx; Val
0x180065ebc  lea     rcx, [rbp+70h+var_E0]; void *
0x180065ec0  mov     r8d, 98h; Size
0x180065ec6  call    memset_0
0x180065ecb  lea     rcx, [r15+1]
0x180065ecf  cmp     rcx, r15
0x180065ed2  jbe     loc_180065F91
0x180065ed8  inc     rcx; Count
0x180065edb  mov     edx, 1; Size
0x180065ee0  call    cs:__imp_calloc
0x180065ee6  mov     rdi, rax
0x180065ee9  test    rax, rax
0x180065eec  jz      loc_180065F91
0x180065ef2  mov     r8, r15; Size
0x180065ef5  mov     rdx, r14; Src
0x180065ef8  mov     rcx, rax; void *
0x180065efb  call    memcpy_0
0x180065f00  mov     rcx, [r13+2F0h]
0x180065f07  lea     rdx, [rbp+70h+var_E0]
0x180065f0b  call    MimeOleGetCharsetInfo
0x180065f10  xor     r14d, r14d
0x180065f13  mov     ebx, eax
0x180065f15  test    eax, eax
0x180065f17  js      short loc_180065F81
0x180065f19  mov     ecx, [rbp+70h+var_54]
0x180065f1c  lea     r8, [rsp+170h+bstrString]
0x180065f21  mov     rdx, rdi
0x180065f24  mov     [rsp+170h+bstrString], r14
0x180065f29  call    cs:__imp_HrLPSZCPToBSTR
0x180065f2f  test    eax, eax
0x180065f31  js      short loc_180065F7C
0x180065f33  mov     rdx, [rsp+170h+bstrString]
0x180065f38  test    rdx, rdx
0x180065f3b  jz      short loc_180065F7C
0x180065f3d  mov     rax, [rsi]
0x180065f40  or      r8, 0FFFFFFFFFFFFFFFFh
0x180065f44  inc     r8
0x180065f47  cmp     [rdx+r8*2], r14w
0x180065f4c  jnz     short loc_180065F44
0x180065f4e  mov     rax, [rax+20h]
0x180065f52  add     r8d, r8d
0x180065f55  xor     r9d, r9d
0x180065f58  mov     rcx, rsi
0x180065f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065f60  mov     ebx, eax
0x180065f62  test    eax, eax
0x180065f64  js      short loc_180065F6F
0x180065f66  mov     [r12], rsi
0x180065f6a  mov     [rsp+170h+var_120], r14
0x180065f6f  mov     rcx, [rsp+170h+bstrString]; bstrString
0x180065f74  call    cs:__imp_SysFreeString
0x180065f7a  jmp     short loc_180065F81
0x180065f7c  mov     ebx, 8007000Eh
0x180065f81  mov     rcx, rdi; Block
0x180065f84  call    cs:__imp_free
0x180065f8a  mov     r14, [rsp+170h+Src]
0x180065f8f  jmp     short loc_180065F96
0x180065f91  mov     ebx, 8007000Eh
0x180065f96  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180065f9d  mov     rdx, r14
0x180065fa0  mov     rax, [rcx]
0x180065fa3  mov     rax, [rax+28h]
0x180065fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065fac  jmp     short loc_180065FB3
0x180065fae  mov     ebx, 8007000Eh
0x180065fb3  lea     rcx, [rsp+170h+var_128]
0x180065fb8  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x180065fbd  lea     rcx, [rsp+170h+pstm]
0x180065fc2  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x180065fc7  lea     rcx, [rsp+170h+var_120]
0x180065fcc  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x180065fd1  lea     rcx, [rsp+170h+var_118]
0x180065fd6  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180065fdb  lea     rcx, [rsp+170h+var_110]
0x180065fe0  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180065fe5  mov     eax, ebx
0x180065fe7  mov     rcx, [rbp+70h+var_40]
0x180065feb  xor     rcx, rsp; StackCookie
0x180065fee  call    __security_check_cookie
0x180065ff3  mov     rbx, [rsp+170h+arg_18]
0x180065ffb  add     rsp, 140h
0x180066002  pop     r15
0x180066004  pop     r14
0x180066006  pop     r13
0x180066008  pop     r12
0x18006600a  pop     rdi
0x18006600b  pop     rsi
0x18006600c  pop     rbp
0x18006600d  retn
```
