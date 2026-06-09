# MXXMLWriter::Init(void)

- ea: `0x1800c6a90`
- end: `0x1800c7043`
- name: `?Init@MXXMLWriter@@MEAAJXZ`
- size: `1459`
- prototype: `__int64 __fastcall(MXXMLWriter *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callees

- `0x180012000`
- `0x18005f9b8`
- `0x180064034`
- `0x180078194`
- `0x1800c6a90`
- `0x1800ca338`
- `0x1800d29a8`
- `0x1800d3620`
- `0x1800d39bc`
- `0x1800d4174`
- `0x1800d4748`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800c6ea5`
- `msvcrt!_resetstkoflw` at `0x1800c6ea5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c6ef8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c6ef8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c6e93`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c6f24`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c6e93`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c6f24`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c6b39`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c6b8c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c6b39`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c6b8c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c7029`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c7029`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6bb2`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6bb2`

## pseudocode

```c
__int64 __fastcall MXXMLWriter::Init(MXXMLWriter *this)
{
  unsigned __int16 *v2; // r14
  BSTR v3; // rax
  int v4; // edi
  char *v5; // r15
  char *v6; // r13
  char *v7; // r12
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  void *v14; // [rsp+30h] [rbp-88h]
  void *v15; // [rsp+38h] [rbp-80h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-78h] BYREF
  struct tagVARIANT v17; // [rsp+60h] [rbp-58h] BYREF
  void *v18; // [rsp+C8h] [rbp+10h]
  void *v19; // [rsp+D0h] [rbp+18h]
  void *v20; // [rsp+D8h] [rbp+20h]

  v18 = (void *)(((unsigned __int64)this + 56) & -(__int64)(this != 0));
  v19 = (void *)(((unsigned __int64)this + 64) & -(__int64)(this != 0));
  v20 = (void *)(((unsigned __int64)this + 72) & -(__int64)(this != 0));
  v14 = (void *)(((unsigned __int64)this + 80) & -(__int64)(this != 0));
  v15 = (void *)(((unsigned __int64)this + 88) & -(__int64)(this != 0));
  v2 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v3 = SysAllocString(L"1.0");
  *((_QWORD *)this + 41) = v3;
  if ( v3 )
  {
    v4 = CachingStream::New((struct CachingStream **)this + 34);
    if ( v4 >= 0 )
    {
      *((_DWORD *)this + 66) = 1;
      *((_BYTE *)this + 178) = 1;
      v2 = SysAllocString(L"UTF-16");
      if ( v2 )
      {
        VariantInit(&pvarg);
        pvarg.vt = 1;
        v17 = pvarg;
        v4 = MXXMLWriter::putOutput(this, &v17, v2);
        if ( v4 >= 0 )
        {
          v5 = (char *)this + 184;
          v4 = ContentHandlerWrapper::newContentHandlerWrapper(
                 (struct IUnknown *)this,
                 (struct ContentHandlerWrapper **)this + 23);
          if ( v4 >= 0 )
          {
            v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))(*(_QWORD *)v5 + 56LL))(
                   *(_QWORD *)v5 + 56LL,
                   &IID_IVBSAXContentHandler,
                   (char *)this + 192);
            if ( v4 >= 0 )
            {
              (*(void (__fastcall **)(MXXMLWriter *))(*(_QWORD *)this + 16LL))(this);
              v4 = DeclHandlerWrapper::newDeclHandlerWrapper(
                     (struct IUnknown *)this,
                     (struct DeclHandlerWrapper **)this + 25);
              if ( v4 >= 0 )
              {
                v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))(*((_QWORD *)this + 25) + 56LL))(
                       *((_QWORD *)this + 25) + 56LL,
                       &IID_IVBSAXDeclHandler,
                       (char *)this + 208);
                if ( v4 >= 0 )
                {
                  (*(void (__fastcall **)(MXXMLWriter *))(*(_QWORD *)this + 16LL))(this);
                  v4 = DTDHandlerWrapper::newDTDHandlerWrapper(
                         (struct IUnknown *)this,
                         (struct DTDHandlerWrapper **)this + 27);
                  if ( v4 >= 0 )
                  {
                    v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))(*((_QWORD *)this + 27) + 56LL))(
                           *((_QWORD *)this + 27) + 56LL,
                           &IID_IVBSAXDTDHandler,
                           (char *)this + 224);
                    if ( v4 >= 0 )
                    {
                      (*(void (__fastcall **)(MXXMLWriter *))(*(_QWORD *)this + 16LL))(this);
                      v6 = (char *)this + 232;
                      v4 = ErrorHandlerWrapper::newErrorHandlerWrapper(
                             (struct IUnknown *)this,
                             (struct ErrorHandlerWrapper **)this + 29);
                      if ( v4 >= 0 )
                      {
                        v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))(*(_QWORD *)v6 + 56LL))(
                               *(_QWORD *)v6 + 56LL,
                               &IID_IVBSAXErrorHandler,
                               (char *)this + 240);
                        if ( v4 >= 0 )
                        {
                          (*(void (__fastcall **)(MXXMLWriter *))(*(_QWORD *)this + 16LL))(this);
                          v7 = (char *)this + 248;
                          v4 = LexicalHandlerWrapper::newLexicalHandlerWrapper(
                                 (struct IUnknown *)this,
                                 (struct LexicalHandlerWrapper **)this + 31);
                          if ( v4 >= 0 )
                          {
                            v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))(*(_QWORD *)v7 + 56LL))(
                                   *(_QWORD *)v7 + 56LL,
                                   &IID_IVBSAXLexicalHandler,
                                   (char *)this + 256);
                            if ( v4 >= 0 )
                            {
                              (*(void (__fastcall **)(MXXMLWriter *))(*(_QWORD *)this + 16LL))(this);
                              assign((struct IUnknown **)(*(_QWORD *)v5 + 72LL), v18);
                              (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
                              assign((struct IUnknown **)(*((_QWORD *)this + 25) + 72LL), v19);
                              (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
                              assign((struct IUnknown **)(*((_QWORD *)this + 27) + 72LL), v20);
                              (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
                              assign((struct IUnknown **)(*(_QWORD *)v6 + 72LL), v14);
                              (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
                              assign((struct IUnknown **)(*(_QWORD *)v7 + 72LL), v15);
                              (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        v4 = -2147024882;
      }
    }
  }
  else
  {
    v4 = -2147024882;
  }
  if ( v4 < 0 )
  {
    v8 = *((_QWORD *)this + 23);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(v8 + 56) + 16LL))(v8 + 56);
      *((_QWORD *)this + 23) = 0;
    }
    v9 = *((_QWORD *)this + 25);
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(v9 + 56) + 16LL))(v9 + 56);
      *((_QWORD *)this + 25) = 0;
    }
    v10 = *((_QWORD *)this + 27);
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(v10 + 56) + 16LL))(v10 + 56);
      *((_QWORD *)this + 27) = 0;
    }
    v11 = *((_QWORD *)this + 29);
    if ( v11 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(v11 + 56) + 16LL))(v11 + 56);
      *((_QWORD *)this + 29) = 0;
    }
    v12 = *((_QWORD *)this + 31);
    if ( v12 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(v12 + 56) + 16LL))(v12 + 56);
      *((_QWORD *)this + 31) = 0;
    }
  }
  SysFreeString(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800c6a90  mov     [rsp+arg_0], rcx
0x1800c6a95  push    rbx
0x1800c6a96  push    rdi
0x1800c6a97  push    r12
0x1800c6a99  push    r13
0x1800c6a9b  push    r14
0x1800c6a9d  push    r15
0x1800c6a9f  sub     rsp, 88h
0x1800c6aa6  mov     rbx, rcx
0x1800c6aa9  mov     rax, rcx
0x1800c6aac  lea     rdx, [rcx+38h]
0x1800c6ab0  neg     rax
0x1800c6ab3  sbb     rax, rax
0x1800c6ab6  and     rax, rdx
0x1800c6ab9  mov     [rsp+0B8h+arg_8], rax
0x1800c6ac1  mov     rax, rcx
0x1800c6ac4  lea     rdx, [rcx+40h]
0x1800c6ac8  neg     rax
0x1800c6acb  sbb     rax, rax
0x1800c6ace  and     rax, rdx
0x1800c6ad1  mov     [rsp+0B8h+arg_10], rax
0x1800c6ad9  mov     rax, rcx
0x1800c6adc  add     rcx, 48h ; 'H'
0x1800c6ae0  neg     rax
0x1800c6ae3  sbb     rax, rax
0x1800c6ae6  and     rax, rcx
0x1800c6ae9  mov     [rsp+0B8h+arg_18], rax
0x1800c6af1  mov     rax, rbx
0x1800c6af4  lea     rcx, [rbx+50h]
0x1800c6af8  neg     rax
0x1800c6afb  sbb     rax, rax
0x1800c6afe  and     rax, rcx
0x1800c6b01  mov     [rsp+0B8h+var_88], rax
0x1800c6b06  mov     rax, rbx
0x1800c6b09  lea     rcx, [rbx+58h]
0x1800c6b0d  neg     rax
0x1800c6b10  sbb     rax, rax
0x1800c6b13  and     rax, rcx
0x1800c6b16  mov     [rsp+0B8h+var_80], rax
0x1800c6b1b  xor     r14d, r14d
0x1800c6b1e  mov     [rsp+0B8h+var_90], r14
0x1800c6b23  xorps   xmm0, xmm0
0x1800c6b26  xor     eax, eax
0x1800c6b28  movups  xmmword ptr [rsp+0B8h+pvarg], xmm0
0x1800c6b2d  mov     qword ptr [rsp+0B8h+pvarg+10h], rax
0x1800c6b32  lea     rcx, a10; "1.0"
0x1800c6b39  call    cs:__imp_SysAllocString
0x1800c6b3f  mov     [rbx+148h], rax
0x1800c6b46  test    rax, rax
0x1800c6b49  jnz     short loc_1800C6B59
0x1800c6b4b  mov     edi, 8007000Eh
0x1800c6b50  mov     [rsp+0B8h+var_98], edi
0x1800c6b54  jmp     loc_1800C6F5B
0x1800c6b59  lea     rcx, [rbx+110h]; struct CachingStream **
0x1800c6b60  call    ?New@CachingStream@@SAJPEAPEAV1@@Z; CachingStream::New(CachingStream * *)
0x1800c6b65  mov     edi, eax
0x1800c6b67  mov     [rsp+0B8h+var_98], eax
0x1800c6b6b  test    eax, eax
0x1800c6b6d  js      loc_1800C6F5B
0x1800c6b73  mov     edi, 1
0x1800c6b78  mov     [rbx+108h], edi
0x1800c6b7e  mov     [rbx+0B2h], dil
0x1800c6b85  lea     rcx, String1; "UTF-16"
0x1800c6b8c  call    cs:__imp_SysAllocString
0x1800c6b92  mov     r14, rax
0x1800c6b95  mov     [rsp+0B8h+var_90], rax
0x1800c6b9a  test    rax, rax
0x1800c6b9d  jnz     short loc_1800C6BAD
0x1800c6b9f  mov     edi, 8007000Eh
0x1800c6ba4  mov     [rsp+0B8h+var_98], edi
0x1800c6ba8  jmp     loc_1800C6F5B
0x1800c6bad  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x1800c6bb2  call    cs:__imp_VariantInit
0x1800c6bb8  mov     word ptr [rsp+0B8h+pvarg], di
0x1800c6bbd  movups  xmm0, xmmword ptr [rsp+0B8h+pvarg]
0x1800c6bc2  movaps  xmmword ptr [rsp+0B8h+var_58], xmm0
0x1800c6bc7  movsd   xmm1, qword ptr [rsp+0B8h+pvarg+10h]
0x1800c6bcd  movsd   qword ptr [rsp+0B8h+var_58+10h], xmm1
0x1800c6bd3  mov     r8, r14; unsigned __int16 *
0x1800c6bd6  lea     rdx, [rsp+0B8h+var_58]; struct tagVARIANT
0x1800c6bdb  mov     rcx, rbx; this
0x1800c6bde  call    ?putOutput@MXXMLWriter@@AEAAJUtagVARIANT@@PEAG@Z; MXXMLWriter::putOutput(tagVARIANT,ushort *)
0x1800c6be3  mov     edi, eax
0x1800c6be5  mov     [rsp+0B8h+var_98], eax
0x1800c6be9  test    eax, eax
0x1800c6beb  js      loc_1800C6F5B
0x1800c6bf1  lea     r15, [rbx+0B8h]
0x1800c6bf8  mov     rdx, r15; struct ContentHandlerWrapper **
0x1800c6bfb  mov     rcx, rbx; struct IUnknown *
0x1800c6bfe  call    ?newContentHandlerWrapper@ContentHandlerWrapper@@SAJPEAUIUnknown@@PEAPEAV1@@Z; ContentHandlerWrapper::newContentHandlerWrapper(IUnknown *,ContentHandlerWrapper * *)
0x1800c6c03  mov     edi, eax
0x1800c6c05  mov     [rsp+0B8h+var_98], eax
0x1800c6c09  test    eax, eax
0x1800c6c0b  js      loc_1800C6F5B
0x1800c6c11  mov     rcx, [r15]
0x1800c6c14  add     rcx, 38h ; '8'
0x1800c6c18  mov     rax, [rcx]
0x1800c6c1b  lea     r8, [rbx+0C0h]
0x1800c6c22  lea     rdx, IID_IVBSAXContentHandler
0x1800c6c29  mov     rax, [rax]
0x1800c6c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6c31  mov     edi, eax
0x1800c6c33  mov     [rsp+0B8h+var_98], eax
0x1800c6c37  test    eax, eax
0x1800c6c39  js      loc_1800C6F5B
0x1800c6c3f  mov     rax, [rbx]
0x1800c6c42  mov     rcx, rbx
0x1800c6c45  mov     rax, [rax+10h]
0x1800c6c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6c4e  lea     r12, [rbx+0C8h]
0x1800c6c55  mov     rdx, r12; struct DeclHandlerWrapper **
0x1800c6c58  mov     rcx, rbx; struct IUnknown *
0x1800c6c5b  call    ?newDeclHandlerWrapper@DeclHandlerWrapper@@SAJPEAUIUnknown@@PEAPEAV1@@Z; DeclHandlerWrapper::newDeclHandlerWrapper(IUnknown *,DeclHandlerWrapper * *)
0x1800c6c60  mov     edi, eax
0x1800c6c62  mov     [rsp+0B8h+var_98], eax
0x1800c6c66  test    eax, eax
0x1800c6c68  js      loc_1800C6F5B
0x1800c6c6e  mov     rcx, [r12]
0x1800c6c72  add     rcx, 38h ; '8'
0x1800c6c76  mov     rax, [rcx]
0x1800c6c79  lea     r8, [rbx+0D0h]
0x1800c6c80  lea     rdx, IID_IVBSAXDeclHandler
0x1800c6c87  mov     rax, [rax]
0x1800c6c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6c8f  mov     edi, eax
0x1800c6c91  mov     [rsp+0B8h+var_98], eax
0x1800c6c95  test    eax, eax
0x1800c6c97  js      loc_1800C6F5B
0x1800c6c9d  mov     rax, [rbx]
0x1800c6ca0  mov     rcx, rbx
0x1800c6ca3  mov     rax, [rax+10h]
0x1800c6ca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6cac  lea     r12, [rbx+0D8h]
0x1800c6cb3  mov     rdx, r12; struct DTDHandlerWrapper **
0x1800c6cb6  mov     rcx, rbx; struct IUnknown *
0x1800c6cb9  call    ?newDTDHandlerWrapper@DTDHandlerWrapper@@SAJPEAUIUnknown@@PEAPEAV1@@Z; DTDHandlerWrapper::newDTDHandlerWrapper(IUnknown *,DTDHandlerWrapper * *)
0x1800c6cbe  mov     edi, eax
0x1800c6cc0  mov     [rsp+0B8h+var_98], eax
0x1800c6cc4  test    eax, eax
0x1800c6cc6  js      loc_1800C6F5B
0x1800c6ccc  mov     rcx, [r12]
0x1800c6cd0  add     rcx, 38h ; '8'
0x1800c6cd4  mov     rax, [rcx]
0x1800c6cd7  lea     r8, [rbx+0E0h]
0x1800c6cde  lea     rdx, IID_IVBSAXDTDHandler
0x1800c6ce5  mov     rax, [rax]
0x1800c6ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6ced  mov     edi, eax
0x1800c6cef  mov     [rsp+0B8h+var_98], eax
0x1800c6cf3  test    eax, eax
0x1800c6cf5  js      loc_1800C6F5B
0x1800c6cfb  mov     rax, [rbx]
0x1800c6cfe  mov     rcx, rbx
0x1800c6d01  mov     rax, [rax+10h]
0x1800c6d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6d0a  lea     r13, [rbx+0E8h]
0x1800c6d11  mov     rdx, r13; struct ErrorHandlerWrapper **
0x1800c6d14  mov     rcx, rbx; struct IUnknown *
0x1800c6d17  call    ?newErrorHandlerWrapper@ErrorHandlerWrapper@@SAJPEAUIUnknown@@PEAPEAV1@@Z; ErrorHandlerWrapper::newErrorHandlerWrapper(IUnknown *,ErrorHandlerWrapper * *)
0x1800c6d1c  mov     edi, eax
0x1800c6d1e  mov     [rsp+0B8h+var_98], eax
0x1800c6d22  test    eax, eax
0x1800c6d24  js      loc_1800C6F5B
0x1800c6d2a  mov     rcx, [r13+0]
0x1800c6d2e  add     rcx, 38h ; '8'
0x1800c6d32  mov     rax, [rcx]
0x1800c6d35  lea     r8, [rbx+0F0h]
0x1800c6d3c  lea     rdx, IID_IVBSAXErrorHandler
0x1800c6d43  mov     rax, [rax]
0x1800c6d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6d4b  mov     edi, eax
0x1800c6d4d  mov     [rsp+0B8h+var_98], eax
0x1800c6d51  test    eax, eax
0x1800c6d53  js      loc_1800C6F5B
0x1800c6d59  mov     rax, [rbx]
0x1800c6d5c  mov     rcx, rbx
0x1800c6d5f  mov     rax, [rax+10h]
0x1800c6d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6d68  lea     r12, [rbx+0F8h]
0x1800c6d6f  mov     rdx, r12; struct LexicalHandlerWrapper **
0x1800c6d72  mov     rcx, rbx; struct IUnknown *
0x1800c6d75  call    ?newLexicalHandlerWrapper@LexicalHandlerWrapper@@SAJPEAUIUnknown@@PEAPEAV1@@Z; LexicalHandlerWrapper::newLexicalHandlerWrapper(IUnknown *,LexicalHandlerWrapper * *)
0x1800c6d7a  mov     edi, eax
0x1800c6d7c  mov     [rsp+0B8h+var_98], eax
0x1800c6d80  test    eax, eax
0x1800c6d82  js      loc_1800C6F5B
0x1800c6d88  mov     rcx, [r12]
0x1800c6d8c  add     rcx, 38h ; '8'
0x1800c6d90  mov     rax, [rcx]
0x1800c6d93  lea     r8, [rbx+100h]
0x1800c6d9a  lea     rdx, IID_IVBSAXLexicalHandler
0x1800c6da1  mov     rax, [rax]
0x1800c6da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6da9  mov     edi, eax
0x1800c6dab  mov     [rsp+0B8h+var_98], eax
0x1800c6daf  test    eax, eax
0x1800c6db1  js      loc_1800C6F5B
0x1800c6db7  mov     rax, [rbx]
0x1800c6dba  mov     rcx, rbx
0x1800c6dbd  mov     rax, [rax+10h]
0x1800c6dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6dc6  mov     rcx, [r15]
0x1800c6dc9  add     rcx, 48h ; 'H'; struct IUnknown **
0x1800c6dcd  mov     r15, [rsp+0B8h+arg_8]
0x1800c6dd5  mov     rdx, r15; void *
0x1800c6dd8  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800c6ddd  mov     rax, [r15]
0x1800c6de0  mov     rcx, r15
0x1800c6de3  mov     rax, [rax+10h]
0x1800c6de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6dec  mov     rcx, [rbx+0C8h]
0x1800c6df3  add     rcx, 48h ; 'H'; struct IUnknown **
0x1800c6df7  mov     r15, [rsp+0B8h+arg_10]
0x1800c6dff  mov     rdx, r15; void *
0x1800c6e02  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800c6e07  mov     rax, [r15]
0x1800c6e0a  mov     rcx, r15
0x1800c6e0d  mov     rax, [rax+10h]
0x1800c6e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6e16  mov     rcx, [rbx+0D8h]
0x1800c6e1d  add     rcx, 48h ; 'H'; struct IUnknown **
0x1800c6e21  mov     r15, [rsp+0B8h+arg_18]
0x1800c6e29  mov     rdx, r15; void *
0x1800c6e2c  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800c6e31  mov     rax, [r15]
0x1800c6e34  mov     rcx, r15
0x1800c6e37  mov     rax, [rax+10h]
0x1800c6e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6e40  mov     rcx, [r13+0]
0x1800c6e44  add     rcx, 48h ; 'H'; struct IUnknown **
0x1800c6e48  mov     r15, [rsp+0B8h+var_88]
0x1800c6e4d  mov     rdx, r15; void *
0x1800c6e50  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800c6e55  mov     rax, [r15]
0x1800c6e58  mov     rcx, r15
0x1800c6e5b  mov     rax, [rax+10h]
0x1800c6e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6e64  mov     rcx, [r12]
0x1800c6e68  add     rcx, 48h ; 'H'; struct IUnknown **
0x1800c6e6c  mov     r15, [rsp+0B8h+var_80]
0x1800c6e71  mov     rdx, r15; void *
0x1800c6e74  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800c6e79  mov     rax, [r15]
0x1800c6e7c  mov     rcx, r15
0x1800c6e7f  mov     rax, [rax+10h]
0x1800c6e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6e88  jmp     loc_1800C6F5B
0x1800c6e8d  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800c6e93  call    cs:__imp_TlsGetValue
0x1800c6e99  mov     rbx, rax
0x1800c6e9c  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800c6ea3  jnz     short loc_1800C6F1E
0x1800c6ea5  call    cs:__imp__resetstkoflw
0x1800c6eab  test    eax, eax
0x1800c6ead  jnz     short loc_1800C6F00
0x1800c6eaf  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800c6eb6  test    rcx, rcx
0x1800c6eb9  jz      short loc_1800C6ECD
0x1800c6ebb  cmp     [rcx+50h], rbx
0x1800c6ebf  jnz     short loc_1800C6ECD
0x1800c6ec1  mov     rax, [rcx]
0x1800c6ec4  mov     rax, [rax+20h]
0x1800c6ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6ecd  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800c6ed4  test    rcx, rcx
0x1800c6ed7  jz      short loc_1800C6EEB
0x1800c6ed9  cmp     [rcx+50h], rbx
0x1800c6edd  jnz     short loc_1800C6EEB
0x1800c6edf  mov     rax, [rcx]
0x1800c6ee2  mov     rax, [rax+20h]
0x1800c6ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6eeb  xor     r9d, r9d; lpArguments
0x1800c6eee  xor     r8d, r8d; nNumberOfArguments
0x1800c6ef1  xor     edx, edx; dwExceptionFlags
0x1800c6ef3  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800c6ef8  call    cs:__imp_RaiseException
0x1800c6efe  jmp     short loc_1800C6F1E
0x1800c6f00  mov     rax, [rbx+60h]
0x1800c6f04  mov     [rbx+68h], rax
0x1800c6f08  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x1800c6f0f  mov     [rbx+60h], rax
0x1800c6f13  mov     dword ptr [rbx+54h], 800703E9h
0x1800c6f1a  mov     byte ptr [rbx+78h], 0
0x1800c6f1e  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800c6f24  call    cs:__imp_TlsGetValue
0x1800c6f2a  mov     rcx, [rax+60h]; struct Exception *
0x1800c6f2e  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x1800c6f33  mov     rdx, rax
0x1800c6f36  mov     rcx, [rax]
0x1800c6f39  mov     rax, [rcx+80h]
0x1800c6f40  mov     rcx, rdx
0x1800c6f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6f48  mov     edi, eax
0x1800c6f4a  mov     [rsp+0B8h+var_98], eax
0x1800c6f4e  mov     rbx, [rsp+0B8h+arg_0]
0x1800c6f56  mov     r14, [rsp+0B8h+var_90]
0x1800c6f5b  test    edi, edi
0x1800c6f5d  jns     loc_1800C7026
0x1800c6f63  mov     rcx, [rbx+0B8h]
0x1800c6f6a  test    rcx, rcx
  ... truncated ...
```
