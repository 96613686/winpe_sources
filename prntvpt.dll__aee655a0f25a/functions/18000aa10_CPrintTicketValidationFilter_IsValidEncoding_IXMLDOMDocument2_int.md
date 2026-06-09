# CPrintTicketValidationFilter::IsValidEncoding(IXMLDOMDocument2 *,int *)

- ea: `0x18000aa10`
- end: `0x18000ac23`
- name: `?IsValidEncoding@CPrintTicketValidationFilter@@IEAAJPEAUIXMLDOMDocument2@@PEAH@Z`
- size: `531`
- prototype: `__int64 __fastcall(CPrintTicketValidationFilter *__hidden this, struct IXMLDOMDocument2 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180002c80`

## callees

- `0x18000aa10`
- `0x180022594`
- `0x180023010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000ab6f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000ab84`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000ab6f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000ab84`
- `OLEAUT32!__imp_SysFreeString` at `0x18000abe1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000abe1`
- `OLEAUT32!__imp_VariantInit` at `0x18000ab3d`
- `OLEAUT32!__imp_VariantInit` at `0x18000ab3d`
- `OLEAUT32!__imp_VariantClear` at `0x18000ab98`
- `OLEAUT32!__imp_VariantClear` at `0x18000ab98`

## pseudocode

```c
__int64 __fastcall CPrintTicketValidationFilter::IsValidEncoding(
        CPrintTicketValidationFilter *this,
        struct IXMLDOMDocument2 *a2,
        int *a3)
{
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  int v6; // ebx
  wchar_t *String1; // [rsp+20h] [rbp-30h] BYREF
  __int64 v8; // [rsp+28h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  CPrintTicketValidationFilter *v10; // [rsp+70h] [rbp+20h] BYREF
  __int64 v11; // [rsp+80h] [rbp+30h] BYREF
  __int64 v12; // [rsp+88h] [rbp+38h] BYREF

  v10 = this;
  v8 = 0;
  v11 = 0;
  if ( !a3 )
    return 2147942487LL;
  lpVtbl = a2->lpVtbl;
  *a3 = 1;
  v6 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64 *))lpVtbl->get_firstChild)(a2, &v8);
  if ( v6 >= 0
    && (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v8)(v8, &IID_IXMLDOMProcessingInstruction, &v11) >= 0 )
  {
    String1 = 0;
    v12 = 0;
    v10 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v11 + 56LL))(v11, &String1);
    if ( v6 >= 0 )
    {
      if ( !String1
        || wcscmp_0(String1, L"xml")
        || (v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 136LL))(v11, &v12), v6 >= 0) )
      {
        if ( !v12
          || (v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, CPrintTicketValidationFilter **))(*(_QWORD *)v12 + 56LL))(
                     v12,
                     L"encoding",
                     &v10),
              v6 >= 0) )
        {
          if ( !v10 )
          {
LABEL_20:
            if ( v12 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
              v12 = 0;
            }
            if ( String1 )
              SysFreeString(String1);
            goto LABEL_24;
          }
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          v6 = (*(__int64 (__fastcall **)(CPrintTicketValidationFilter *, VARIANTARG *))(*(_QWORD *)v10 + 64LL))(
                 v10,
                 &pvarg);
          if ( v6 >= 0
            && pvarg.vt == 8
            && (unsigned int)_o__wcsicmp(pvarg.llVal, L"UTF-8")
            && (unsigned int)_o__wcsicmp(pvarg.llVal, L"UTF-16") )
          {
            *a3 = 0;
          }
          VariantClear(&pvarg);
        }
      }
    }
    if ( v10 )
    {
      (*(void (__fastcall **)(CPrintTicketValidationFilter *))(*(_QWORD *)v10 + 16LL))(v10);
      v10 = 0;
    }
    goto LABEL_20;
  }
LABEL_24:
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000aa10  mov     [rsp-18h+arg_0], rcx
0x18000aa15  push    rbp
0x18000aa16  push    rbx
0x18000aa17  push    rdi
0x18000aa18  mov     rbp, rsp
0x18000aa1b  sub     rsp, 50h
0x18000aa1f  mov     rdi, r8
0x18000aa22  mov     [rbp+var_28], 0
0x18000aa2a  mov     [rbp+arg_10], 0
0x18000aa32  mov     r8, rdx
0x18000aa35  test    rdi, rdi
0x18000aa38  jnz     short loc_18000AA44
0x18000aa3a  mov     eax, 80070057h
0x18000aa3f  jmp     loc_18000AC1B
0x18000aa44  mov     rax, [rdx]
0x18000aa47  mov     rcx, r8
0x18000aa4a  lea     rdx, [rbp+var_28]
0x18000aa4e  mov     dword ptr [rdi], 1
0x18000aa54  mov     rax, [rax+68h]
0x18000aa58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa5d  mov     ebx, eax
0x18000aa5f  test    eax, eax
0x18000aa61  js      loc_18000ABE7
0x18000aa67  mov     rcx, [rbp+var_28]
0x18000aa6b  lea     r8, [rbp+arg_10]
0x18000aa6f  mov     rdx, [rcx]
0x18000aa72  mov     rax, [rdx]
0x18000aa75  lea     rdx, IID_IXMLDOMProcessingInstruction
0x18000aa7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa81  test    eax, eax
0x18000aa83  js      loc_18000ABE7
0x18000aa89  mov     rcx, [rbp+arg_10]
0x18000aa8d  lea     rdx, [rbp+String1]
0x18000aa91  mov     [rbp+String1], 0
0x18000aa99  mov     [rbp+arg_18], 0
0x18000aaa1  mov     [rbp+arg_0], 0
0x18000aaa9  mov     rax, [rcx]
0x18000aaac  mov     rax, [rax+38h]
0x18000aab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aab5  mov     ebx, eax
0x18000aab7  test    eax, eax
0x18000aab9  js      loc_18000AB9E
0x18000aabf  mov     rcx, [rbp+String1]; String1
0x18000aac3  test    rcx, rcx
0x18000aac6  jz      short loc_18000AAF9
0x18000aac8  lea     rdx, aXml; "xml"
0x18000aacf  call    wcscmp_0
0x18000aad4  test    eax, eax
0x18000aad6  jnz     short loc_18000AAF9
0x18000aad8  mov     rcx, [rbp+arg_10]
0x18000aadc  lea     rdx, [rbp+arg_18]
0x18000aae0  mov     rax, [rcx]
0x18000aae3  mov     rax, [rax+88h]
0x18000aaea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaef  mov     ebx, eax
0x18000aaf1  test    eax, eax
0x18000aaf3  js      loc_18000AB9E
0x18000aaf9  mov     rcx, [rbp+arg_18]
0x18000aafd  test    rcx, rcx
0x18000ab00  jz      short loc_18000AB1F
0x18000ab02  mov     rax, [rcx]
0x18000ab05  lea     r8, [rbp+arg_0]
0x18000ab09  lea     rdx, aEncoding; "encoding"
0x18000ab10  mov     rax, [rax+38h]
0x18000ab14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab19  mov     ebx, eax
0x18000ab1b  test    eax, eax
0x18000ab1d  js      short loc_18000AB9E
0x18000ab1f  mov     rcx, [rbp+arg_0]
0x18000ab23  test    rcx, rcx
0x18000ab26  jz      loc_18000ABBB
0x18000ab2c  xorps   xmm0, xmm0
0x18000ab2f  lea     rcx, [rbp+pvarg]; pvarg
0x18000ab33  xor     eax, eax
0x18000ab35  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000ab39  mov     qword ptr [rbp+pvarg+10h], rax
0x18000ab3d  call    cs:__imp_VariantInit
0x18000ab43  mov     rcx, [rbp+arg_0]
0x18000ab47  lea     rdx, [rbp+pvarg]
0x18000ab4b  mov     rax, [rcx]
0x18000ab4e  mov     rax, [rax+40h]
0x18000ab52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab57  mov     ebx, eax
0x18000ab59  test    eax, eax
0x18000ab5b  js      short loc_18000AB94
0x18000ab5d  cmp     word ptr [rbp+pvarg], 8
0x18000ab62  jnz     short loc_18000AB94
0x18000ab64  mov     rcx, qword ptr [rbp+pvarg+8]
0x18000ab68  lea     rdx, aUtf8; "UTF-8"
0x18000ab6f  call    cs:__imp__o__wcsicmp
0x18000ab75  test    eax, eax
0x18000ab77  jz      short loc_18000AB94
0x18000ab79  mov     rcx, qword ptr [rbp+pvarg+8]
0x18000ab7d  lea     rdx, aUtf16; "UTF-16"
0x18000ab84  call    cs:__imp__o__wcsicmp
0x18000ab8a  test    eax, eax
0x18000ab8c  jz      short loc_18000AB94
0x18000ab8e  mov     dword ptr [rdi], 0
0x18000ab94  lea     rcx, [rbp+pvarg]; pvarg
0x18000ab98  call    cs:__imp_VariantClear
0x18000ab9e  mov     rcx, [rbp+arg_0]
0x18000aba2  test    rcx, rcx
0x18000aba5  jz      short loc_18000ABBB
0x18000aba7  mov     rax, [rcx]
0x18000abaa  mov     rax, [rax+10h]
0x18000abae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abb3  mov     [rbp+arg_0], 0
0x18000abbb  mov     rcx, [rbp+arg_18]
0x18000abbf  test    rcx, rcx
0x18000abc2  jz      short loc_18000ABD8
0x18000abc4  mov     rax, [rcx]
0x18000abc7  mov     rax, [rax+10h]
0x18000abcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abd0  mov     [rbp+arg_18], 0
0x18000abd8  mov     rcx, [rbp+String1]; bstrString
0x18000abdc  test    rcx, rcx
0x18000abdf  jz      short loc_18000ABE7
0x18000abe1  call    cs:__imp_SysFreeString
0x18000abe7  mov     rcx, [rbp+arg_10]
0x18000abeb  test    rcx, rcx
0x18000abee  jz      short loc_18000AC04
0x18000abf0  mov     rax, [rcx]
0x18000abf3  mov     rax, [rax+10h]
0x18000abf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abfc  mov     [rbp+arg_10], 0
0x18000ac04  mov     rcx, [rbp+var_28]
0x18000ac08  test    rcx, rcx
0x18000ac0b  jz      short loc_18000AC19
0x18000ac0d  mov     rax, [rcx]
0x18000ac10  mov     rax, [rax+10h]
0x18000ac14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac19  mov     eax, ebx
0x18000ac1b  add     rsp, 50h
0x18000ac1f  pop     rdi
0x18000ac20  pop     rbx
0x18000ac21  pop     rbp
0x18000ac22  retn
```
