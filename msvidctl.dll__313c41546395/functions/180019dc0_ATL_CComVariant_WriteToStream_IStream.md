# ATL::CComVariant::WriteToStream(IStream *)

- ea: `0x180019dc0`
- end: `0x18001a03e`
- name: `?WriteToStream@CComVariant@ATL@@QEAAJPEAUIStream@@@Z`
- size: `638`
- prototype: `__int64 __fastcall(VARIANTARG *pvarSrc, LPSTREAM pStm)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015510`
- `0x18001a044`

## callees

- `0x180006b38`
- `0x180019dc0`
- `0x1800f8010`

## import_xrefs

- `ole32!OleSaveToStream` at `0x180019e96`
- `ole32!OleSaveToStream` at `0x180019e96`
- `ole32!WriteClassStm` at `0x18001a017`
- `ole32!WriteClassStm` at `0x18001a017`
- `OLEAUT32!__imp_SysFreeString` at `0x180019f43`
- `OLEAUT32!__imp_SysFreeString` at `0x180019fdb`
- `OLEAUT32!__imp_SysFreeString` at `0x180019f43`
- `OLEAUT32!__imp_SysFreeString` at `0x180019fdb`
- `OLEAUT32!__imp_VariantClear` at `0x180019f3a`
- `OLEAUT32!__imp_VariantClear` at `0x180019fd2`
- `OLEAUT32!__imp_VariantClear` at `0x180019f3a`
- `OLEAUT32!__imp_VariantClear` at `0x180019fd2`
- `OLEAUT32!__imp_VariantChangeType` at `0x180019f1f`
- `OLEAUT32!__imp_VariantChangeType` at `0x180019f1f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180019f6b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180019f6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CComVariant::WriteToStream(VARIANTARG *pvarSrc, LPSTREAM pStm)
{
  __int64 result; // rax
  unsigned int v5; // edi
  unsigned int vt; // edx
  unsigned int v7; // ecx
  __int64 (__fastcall ***llVal)(_QWORD, GUID *, LPPERSISTSTREAM *); // rcx
  HRESULT v9; // ebx
  HRESULT v10; // eax
  OLECHAR *bstrVal; // rbx
  UINT v12; // eax
  int v13; // r14d
  VARIANTARG pvargDest; // [rsp+30h] [rbp-20h] BYREF
  LPPERSISTSTREAM pPStm; // [rsp+88h] [rbp+38h] BYREF
  int v16; // [rsp+90h] [rbp+40h] BYREF
  OLECHAR *v17; // [rsp+98h] [rbp+48h]

  if ( !pStm )
    return 2147942487LL;
  v5 = 2;
  result = ((__int64 (__fastcall *)(LPSTREAM, VARIANTARG *, __int64))pStm->lpVtbl->Write)(pStm, pvarSrc, 2);
  if ( (int)result < 0 )
    return result;
  vt = pvarSrc->vt;
  if ( vt > 0xB )
  {
    switch ( vt )
    {
      case 0xDu:
        goto LABEL_13;
      case 0x10u:
      case 0x11u:
        v5 = 1;
        return ((__int64 (__fastcall *)(LPSTREAM, ULONG *, _QWORD, _QWORD))pStm->lpVtbl->Write)(
                 pStm,
                 &pvarSrc->decVal.Lo32,
                 v5,
                 0);
      case 0x12u:
        return ((__int64 (__fastcall *)(LPSTREAM, ULONG *, _QWORD, _QWORD))pStm->lpVtbl->Write)(
                 pStm,
                 &pvarSrc->decVal.Lo32,
                 v5,
                 0);
    }
    if ( vt != 19 )
    {
      if ( vt == 20 )
      {
LABEL_17:
        v5 = 8;
        return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))pStm->lpVtbl->Write)(
                 pStm,
                 &pvarSrc->decVal.Lo32,
                 v5,
                 0);
      }
      v7 = vt - 22;
      if ( vt != 22 )
        goto LABEL_25;
    }
LABEL_44:
    v5 = 4;
    return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))pStm->lpVtbl->Write)(
             pStm,
             &pvarSrc->decVal.Lo32,
             v5,
             0);
  }
  switch ( vt )
  {
    case 0xBu:
    case 2u:
      return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))pStm->lpVtbl->Write)(
               pStm,
               &pvarSrc->decVal.Lo32,
               v5,
               0);
    case 3u:
    case 4u:
      goto LABEL_44;
    case 5u:
    case 6u:
    case 7u:
      goto LABEL_17;
  }
  v7 = vt - 9;
  if ( vt == 9 )
  {
LABEL_13:
    pPStm = 0;
    llVal = (__int64 (__fastcall ***)(_QWORD, GUID *, LPPERSISTSTREAM *))pvarSrc->llVal;
    if ( !llVal )
      goto LABEL_47;
    v9 = (**llVal)(llVal, &IID_IPersistStream, &pPStm);
    if ( v9 < 0 )
    {
LABEL_49:
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&pPStm);
      return (unsigned int)v9;
    }
    if ( pPStm )
      v10 = OleSaveToStream(pPStm, pStm);
    else
LABEL_47:
      v10 = WriteClassStm(pStm, &GUID_NULL);
    v9 = v10;
    goto LABEL_49;
  }
LABEL_25:
  if ( v7 == 1 )
    goto LABEL_44;
  memset(&pvargDest, 0, sizeof(pvargDest));
  pvargDest.vt = 0;
  if ( (_WORD)vt == 8 || (_WORD)vt == 4095 )
  {
    bstrVal = pvarSrc->bstrVal;
  }
  else
  {
    v9 = VariantChangeType(&pvargDest, pvarSrc, 1u, 8u);
    if ( v9 < 0 )
    {
      if ( pvargDest.vt == 4095 )
        pvargDest.vt = 8;
      VariantClear(&pvargDest);
      SysFreeString(0);
      return (unsigned int)v9;
    }
    bstrVal = pvargDest.bstrVal;
  }
  v17 = bstrVal;
  v16 = 0;
  if ( bstrVal )
    v12 = SysStringByteLen(bstrVal);
  else
    v12 = 0;
  LODWORD(pPStm) = v12;
  v13 = ((__int64 (__fastcall *)(LPSTREAM, LPPERSISTSTREAM *, __int64, int *))pStm->lpVtbl->Write)(
          pStm,
          &pPStm,
          4,
          &v16);
  if ( v13 >= 0 )
  {
    if ( (_DWORD)pPStm )
      v13 = ((__int64 (__fastcall *)(LPSTREAM, OLECHAR *, _QWORD, int *))pStm->lpVtbl->Write)(
              pStm,
              bstrVal,
              (unsigned int)pPStm,
              &v16);
    else
      v13 = 0;
  }
  if ( pvargDest.vt == 4095 )
    pvargDest.vt = 8;
  VariantClear(&pvargDest);
  SysFreeString(0);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180019dc0  mov     [rsp-28h+arg_0], rbx
0x180019dc5  push    rbp
0x180019dc6  push    rsi
0x180019dc7  push    rdi
0x180019dc8  push    r14
0x180019dca  push    r15
0x180019dcc  mov     rbp, rsp
0x180019dcf  sub     rsp, 50h
0x180019dd3  mov     rsi, rdx
0x180019dd6  mov     rbx, rcx
0x180019dd9  test    rdx, rdx
0x180019ddc  jnz     short loc_180019DE8
0x180019dde  mov     eax, 80070057h
0x180019de3  jmp     loc_18001A02A
0x180019de8  mov     rax, [rdx]
0x180019deb  xor     r9d, r9d
0x180019dee  lea     edi, [r9+2]
0x180019df2  mov     r8d, edi
0x180019df5  mov     rdx, rbx
0x180019df8  mov     rcx, rsi
0x180019dfb  mov     rax, [rax+20h]
0x180019dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e04  test    eax, eax
0x180019e06  js      loc_18001A02A
0x180019e0c  movzx   edx, word ptr [rbx]
0x180019e0f  cmp     edx, 0Bh
0x180019e12  ja      loc_180019EAB
0x180019e18  jz      loc_180019FF2
0x180019e1e  mov     ecx, edx
0x180019e20  sub     ecx, edi
0x180019e22  jz      loc_180019FF2
0x180019e28  sub     ecx, 1
0x180019e2b  jz      loc_180019FE6
0x180019e31  sub     ecx, 1
0x180019e34  jz      loc_180019FE6
0x180019e3a  sub     ecx, 1
0x180019e3d  jz      short loc_180019EA1
0x180019e3f  sub     ecx, 1
0x180019e42  jz      short loc_180019EA1
0x180019e44  sub     ecx, 1
0x180019e47  jz      short loc_180019EA1
0x180019e49  sub     ecx, edi
0x180019e4b  jnz     loc_180019EE3
0x180019e51  mov     [rbp+pPStm], 0
0x180019e59  mov     rcx, [rbx+8]
0x180019e5d  test    rcx, rcx
0x180019e60  jz      loc_18001A00D
0x180019e66  mov     rax, [rcx]
0x180019e69  lea     r8, [rbp+pPStm]
0x180019e6d  lea     rdx, IID_IPersistStream
0x180019e74  mov     rax, [rax]
0x180019e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e7c  mov     ebx, eax
0x180019e7e  test    eax, eax
0x180019e80  js      loc_18001A01F
0x180019e86  mov     rcx, [rbp+pPStm]; pPStm
0x180019e8a  test    rcx, rcx
0x180019e8d  jz      loc_18001A00D
0x180019e93  mov     rdx, rsi; pStm
0x180019e96  call    cs:__imp_OleSaveToStream
0x180019e9c  jmp     loc_18001A01D
0x180019ea1  mov     edi, 8
0x180019ea6  jmp     loc_180019FF2
0x180019eab  mov     ecx, edx
0x180019ead  sub     ecx, 0Dh
0x180019eb0  jz      short loc_180019E51
0x180019eb2  sub     ecx, 3
0x180019eb5  jz      loc_180019FED
0x180019ebb  sub     ecx, 1
0x180019ebe  jz      loc_180019FED
0x180019ec4  sub     ecx, 1
0x180019ec7  jz      loc_180019FF2
0x180019ecd  sub     ecx, 1
0x180019ed0  jz      loc_180019FE6
0x180019ed6  sub     ecx, 1
0x180019ed9  jz      short loc_180019EA1
0x180019edb  sub     ecx, edi
0x180019edd  jz      loc_180019FE6
0x180019ee3  cmp     ecx, 1
0x180019ee6  jz      loc_180019FE6
0x180019eec  xorps   xmm0, xmm0
0x180019eef  xor     eax, eax
0x180019ef1  movups  xmmword ptr [rbp+pvargDest], xmm0
0x180019ef5  mov     qword ptr [rbp+pvargDest+10h], rax
0x180019ef9  mov     word ptr [rbp+pvargDest], ax
0x180019efd  lea     edi, [rax+8]
0x180019f00  mov     r15d, 0FFFh
0x180019f06  cmp     dx, di
0x180019f09  jz      short loc_180019F54
0x180019f0b  cmp     dx, r15w
0x180019f0f  jz      short loc_180019F54
0x180019f11  mov     r9d, edi; vt
0x180019f14  lea     r8d, [rax+1]; wFlags
0x180019f18  mov     rdx, rbx; pvarSrc
0x180019f1b  lea     rcx, [rbp+pvargDest]; pvargDest
0x180019f1f  call    cs:__imp_VariantChangeType
0x180019f25  mov     ebx, eax
0x180019f27  test    eax, eax
0x180019f29  jns     short loc_180019F4E
0x180019f2b  cmp     word ptr [rbp+pvargDest], r15w
0x180019f30  jnz     short loc_180019F36
0x180019f32  mov     word ptr [rbp+pvargDest], di
0x180019f36  lea     rcx, [rbp+pvargDest]; pvarg
0x180019f3a  call    cs:__imp_VariantClear
0x180019f40  nop
0x180019f41  xor     ecx, ecx; bstrString
0x180019f43  call    cs:__imp_SysFreeString
0x180019f49  jmp     loc_18001A028
0x180019f4e  mov     rbx, qword ptr [rbp+pvargDest+8]
0x180019f52  jmp     short loc_180019F58
0x180019f54  mov     rbx, [rbx+8]
0x180019f58  mov     [rbp+arg_18], rbx
0x180019f5c  mov     [rbp+arg_10], 0
0x180019f63  test    rbx, rbx
0x180019f66  jz      short loc_180019F73
0x180019f68  mov     rcx, rbx; bstr
0x180019f6b  call    cs:__imp_SysStringByteLen
0x180019f71  jmp     short loc_180019F75
0x180019f73  xor     eax, eax
0x180019f75  mov     dword ptr [rbp+pPStm], eax
0x180019f78  mov     rax, [rsi]
0x180019f7b  lea     r9, [rbp+arg_10]
0x180019f7f  mov     r8d, 4
0x180019f85  lea     rdx, [rbp+pPStm]
0x180019f89  mov     rcx, rsi
0x180019f8c  mov     rax, [rax+20h]
0x180019f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f95  mov     r14d, eax
0x180019f98  test    eax, eax
0x180019f9a  js      short loc_180019FC3
0x180019f9c  mov     r8d, dword ptr [rbp+pPStm]
0x180019fa0  test    r8d, r8d
0x180019fa3  jz      short loc_180019FC0
0x180019fa5  mov     rax, [rsi]
0x180019fa8  lea     r9, [rbp+arg_10]
0x180019fac  mov     rdx, rbx
0x180019faf  mov     rcx, rsi
0x180019fb2  mov     rax, [rax+20h]
0x180019fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fbb  mov     r14d, eax
0x180019fbe  jmp     short loc_180019FC3
0x180019fc0  xor     r14d, r14d
0x180019fc3  cmp     word ptr [rbp+pvargDest], r15w
0x180019fc8  jnz     short loc_180019FCE
0x180019fca  mov     word ptr [rbp+pvargDest], di
0x180019fce  lea     rcx, [rbp+pvargDest]; pvarg
0x180019fd2  call    cs:__imp_VariantClear
0x180019fd8  nop
0x180019fd9  xor     ecx, ecx; bstrString
0x180019fdb  call    cs:__imp_SysFreeString
0x180019fe1  mov     eax, r14d
0x180019fe4  jmp     short loc_18001A02A
0x180019fe6  mov     edi, 4
0x180019feb  jmp     short loc_180019FF2
0x180019fed  mov     edi, 1
0x180019ff2  mov     rax, [rsi]
0x180019ff5  lea     rdx, [rbx+8]
0x180019ff9  xor     r9d, r9d
0x180019ffc  mov     r8d, edi
0x180019fff  mov     rcx, rsi
0x18001a002  mov     rax, [rax+20h]
0x18001a006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a00b  jmp     short loc_18001A02A
0x18001a00d  lea     rdx, GUID_NULL; rclsid
0x18001a014  mov     rcx, rsi; pStm
0x18001a017  call    cs:__imp_WriteClassStm
0x18001a01d  mov     ebx, eax
0x18001a01f  lea     rcx, [rbp+pPStm]
0x18001a023  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18001a028  mov     eax, ebx
0x18001a02a  mov     rbx, [rsp+50h+arg_0]
0x18001a032  add     rsp, 50h
0x18001a036  pop     r15
0x18001a038  pop     r14
0x18001a03a  pop     rdi
0x18001a03b  pop     rsi
0x18001a03c  pop     rbp
0x18001a03d  retn
```
