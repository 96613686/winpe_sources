# NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)

- ea: `0x180006f80`
- end: `0x1800070d5`
- name: `?CreateXMLElement@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z`
- size: `341`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *__hidden this, struct IXMLDOMElement *, const unsigned __int16 *, const unsigned __int16 *, struct IXMLDOMElement **)`
- caller_count: `14`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006130`
- `0x180006b10`
- `0x180006c74`
- `0x1800077f0`
- `0x180007a04`
- `0x180009da8`
- `0x18000c224`
- `0x18000e084`
- `0x18000e460`
- `0x18001c060`
- `0x18001c2b0`
- `0x18001c514`
- `0x180020710`
- `0x180020bd0`

## callees

- `0x180006f80`
- `0x1800070e0`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180006fdb`
- `OLEAUT32!__imp_SysFreeString` at `0x180006fdb`
- `OLEAUT32!__imp_VariantInit` at `0x180007021`
- `OLEAUT32!__imp_VariantInit` at `0x180007021`
- `OLEAUT32!__imp_VariantClear` at `0x18000707a`
- `OLEAUT32!__imp_VariantClear` at `0x18000707a`

## string_xrefs

- `0x180006fb9`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x180007034`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(
        __int64 **this,
        struct IXMLDOMElement *a2,
        struct IXMLDOMElement *a3,
        const unsigned __int16 *a4,
        struct IXMLDOMElement **a5)
{
  int QName; // ebx
  __int64 *v9; // rcx
  __int64 v10; // rax
  __int64 (__fastcall *v11)(__int64 *, __int128 *, BSTR, const unsigned __int16 *, __int64 *); // rax
  unsigned __int16 **v12; // [rsp+28h] [rbp-48h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  __int128 v14; // [rsp+50h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-10h]
  __int64 v16; // [rsp+98h] [rbp+28h] BYREF
  BSTR bstrString; // [rsp+A8h] [rbp+38h] BYREF

  v16 = 0;
  bstrString = 0;
  if ( a2 && a3 )
  {
    QName = NPrintTicketUtil::CreateQName(
              (NPrintTicketUtil *)this,
              a2,
              a3,
              L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
              (const unsigned __int16 *)&bstrString,
              v12,
              *(const unsigned __int16 **)&pvarg.vt);
    if ( QName >= 0 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v9 = this[1];
      pvarg.vt = 3;
      pvarg.lVal = 1;
      v10 = *v9;
      pRecInfo = pvarg.pRecInfo;
      v11 = *(__int64 (__fastcall **)(__int64 *, __int128 *, BSTR, const unsigned __int16 *, __int64 *))(v10 + 448);
      v14 = *(_OWORD *)&pvarg.vt;
      QName = v11(
                v9,
                &v14,
                bstrString,
                L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
                &v16);
      VariantClear(&pvarg);
      if ( QName >= 0 )
      {
        QName = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64, _QWORD))a2->lpVtbl->appendChild)(a2, v16, 0);
        if ( QName >= 0 )
        {
          if ( a5 )
            QName = (**(__int64 (__fastcall ***)(__int64, GUID *))v16)(v16, &IID_IXMLDOMElement);
        }
      }
    }
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)QName;
}

```

## disassembly

```asm
0x180006f80  mov     [rsp-18h+arg_0], rbx
0x180006f85  mov     [rsp-18h+bstrString], r9
0x180006f8a  push    rbp
0x180006f8b  push    rsi
0x180006f8c  push    r14
0x180006f8e  mov     rbp, rsp
0x180006f91  sub     rsp, 70h
0x180006f95  mov     [rbp+arg_8], 0
0x180006f9d  mov     rsi, rdx
0x180006fa0  mov     [rbp+bstrString], 0
0x180006fa8  mov     r14, rcx
0x180006fab  test    rdx, rdx
0x180006fae  jz      short loc_180007009
0x180006fb0  test    r8, r8
0x180006fb3  jz      short loc_180007009
0x180006fb5  lea     rax, [rbp+bstrString]
0x180006fb9  lea     r9, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x180006fc0  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x180006fc5  call    ?CreateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEBG2PEAPEAG2@Z; NPrintTicketUtil::CreateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort const *,ushort * *,ushort const *)
0x180006fca  mov     ebx, eax
0x180006fcc  test    eax, eax
0x180006fce  jns     short loc_180007010
0x180006fd0  cmp     [rbp+bstrString], 0
0x180006fd5  jz      short loc_180006FE1
0x180006fd7  mov     rcx, [rbp+bstrString]; bstrString
0x180006fdb  call    cs:__imp_SysFreeString
0x180006fe1  mov     rcx, [rbp+arg_8]
0x180006fe5  test    rcx, rcx
0x180006fe8  jz      short loc_180006FF6
0x180006fea  mov     rax, [rcx]
0x180006fed  mov     rax, [rax+10h]
0x180006ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ff6  mov     eax, ebx
0x180006ff8  mov     rbx, [rsp+70h+arg_0]
0x180007000  add     rsp, 70h
0x180007004  pop     r14
0x180007006  pop     rsi
0x180007007  pop     rbp
0x180007008  retn
0x180007009  mov     ebx, 80070057h
0x18000700e  jmp     short loc_180006FF6
0x180007010  xorps   xmm0, xmm0
0x180007013  lea     rcx, [rbp+pvarg]; pvarg
0x180007017  xor     eax, eax
0x180007019  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000701d  mov     qword ptr [rbp+pvarg+10h], rax
0x180007021  call    cs:__imp_VariantInit
0x180007027  mov     rcx, [r14+8]
0x18000702b  lea     rdx, [rbp+arg_8]
0x18000702f  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180007034  lea     r9, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x18000703b  mov     r8, [rbp+bstrString]
0x18000703f  mov     eax, 3
0x180007044  mov     word ptr [rbp+pvarg], ax
0x180007048  mov     dword ptr [rbp+pvarg+8], 1
0x18000704f  mov     rax, [rcx]
0x180007052  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180007056  mov     [rsp+70h+var_50], rdx
0x18000705b  lea     rdx, [rbp+var_20]
0x18000705f  movsd   [rbp+var_10], xmm1
0x180007064  mov     rax, [rax+1C0h]
0x18000706b  movaps  [rbp+var_20], xmm0
0x18000706f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007074  lea     rcx, [rbp+pvarg]; pvarg
0x180007078  mov     ebx, eax
0x18000707a  call    cs:__imp_VariantClear
0x180007080  test    ebx, ebx
0x180007082  js      loc_180006FD0
0x180007088  mov     rax, [rsi]
0x18000708b  xor     r8d, r8d
0x18000708e  mov     rdx, [rbp+arg_8]
0x180007092  mov     rcx, rsi
0x180007095  mov     rax, [rax+0A8h]
0x18000709c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070a1  mov     ebx, eax
0x1800070a3  test    eax, eax
0x1800070a5  js      loc_180006FD0
0x1800070ab  mov     r8, [rbp+arg_20]
0x1800070af  test    r8, r8
0x1800070b2  jz      loc_180006FD0
0x1800070b8  mov     rcx, [rbp+arg_8]
0x1800070bc  lea     rdx, IID_IXMLDOMElement
0x1800070c3  mov     rax, [rcx]
0x1800070c6  mov     rax, [rax]
0x1800070c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070ce  mov     ebx, eax
0x1800070d0  jmp     loc_180006FD0
```
