# NPrintTicketUtil::CPrintTicketWrapper::GetValueAsLong(IXMLDOMElement *,int,long *,int *)

- ea: `0x18001dc8c`
- end: `0x18001ddbd`
- name: `?GetValueAsLong@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@HPEAJPEAH@Z`
- size: `305`
- prototype: `__int64 __usercall@<rax>(NPrintTicketUtil::CPrintTicketWrapper *__hidden this@<rcx>, struct IXMLDOMElement *@<rdx>, int@<r8d>, int *@<r9>, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001b9f0`
- `0x18001d7c0`

## callees

- `0x1800056e0`
- `0x18001d878`
- `0x18001dc8c`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001dd2b`
- `OLEAUT32!__imp_VariantInit` at `0x18001dd2b`
- `OLEAUT32!__imp_VariantClear` at `0x18001dd87`
- `OLEAUT32!__imp_VariantClear` at `0x18001dd87`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001dd6c`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001dd6c`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::GetValueAsLong(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        __int64 a3,
        int *a4,
        int *a5)
{
  int *v8; // rbx
  HRESULT ValueAsBSTR; // edi
  unsigned __int16 *v10; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v13; // [rsp+78h] [rbp+28h] BYREF

  v13 = 0;
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v13);
  v13 = 0;
  if ( a2 && a4 && (v8 = a5) != 0 )
  {
    *a5 = 0;
    ValueAsBSTR = NPrintTicketUtil::CPrintTicketWrapper::GetValueAsBSTR(this, a2, &v13, 0, 0, 1);
    if ( ValueAsBSTR >= 0 && v13 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v10 = 0;
      pvarg.vt = 8;
      if ( v13 )
      {
        v10 = v13;
        v13 = 0;
      }
      pvarg.llVal = (LONGLONG)v10;
      ValueAsBSTR = VariantChangeType(&pvarg, &pvarg, 4u, 3u);
      if ( ValueAsBSTR >= 0 )
      {
        *a4 = pvarg.lVal;
        *v8 = 1;
      }
      VariantClear(&pvarg);
    }
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v13);
    return (unsigned int)ValueAsBSTR;
  }
  else
  {
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v13);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18001dc8c  mov     [rsp-18h+arg_0], rbx
0x18001dc91  mov     [rsp-18h+arg_10], rsi
0x18001dc96  push    rbp
0x18001dc97  push    rdi
0x18001dc98  push    r14
0x18001dc9a  mov     rbp, rsp
0x18001dc9d  sub     rsp, 50h
0x18001dca1  mov     r14, rcx
0x18001dca4  mov     [rbp+arg_8], 0
0x18001dcac  lea     rcx, [rbp+arg_8]
0x18001dcb0  mov     rsi, r9
0x18001dcb3  mov     rdi, rdx
0x18001dcb6  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001dcbb  mov     [rbp+arg_8], 0
0x18001dcc3  test    rdi, rdi
0x18001dcc6  jz      loc_18001DD9A
0x18001dccc  test    rsi, rsi
0x18001dccf  jz      loc_18001DD9A
0x18001dcd5  mov     rbx, [rbp+arg_20]
0x18001dcd9  test    rbx, rbx
0x18001dcdc  jz      loc_18001DD9A
0x18001dce2  mov     [rsp+50h+var_28], 1; int
0x18001dcea  lea     r8, [rbp+arg_8]; unsigned __int16 **
0x18001dcee  xor     r9d, r9d; unsigned __int16 **
0x18001dcf1  mov     [rsp+50h+var_30], 0; unsigned __int16 **
0x18001dcfa  mov     rdx, rdi; struct IXMLDOMElement *
0x18001dcfd  mov     dword ptr [rbx], 0
0x18001dd03  mov     rcx, r14; this
0x18001dd06  call    ?GetValueAsBSTR@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG11H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetValueAsBSTR(IXMLDOMElement *,ushort * *,ushort * *,ushort * *,int)
0x18001dd0b  mov     edi, eax
0x18001dd0d  test    eax, eax
0x18001dd0f  js      short loc_18001DD8D
0x18001dd11  mov     rcx, [rbp+arg_8]
0x18001dd15  test    rcx, rcx
0x18001dd18  jz      short loc_18001DD8D
0x18001dd1a  xorps   xmm0, xmm0
0x18001dd1d  lea     rcx, [rbp+pvarg]; pvarg
0x18001dd21  xor     eax, eax
0x18001dd23  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001dd27  mov     qword ptr [rbp+pvarg+10h], rax
0x18001dd2b  call    cs:__imp_VariantInit
0x18001dd31  mov     eax, 8
0x18001dd36  xor     ecx, ecx
0x18001dd38  mov     word ptr [rbp+pvarg], ax
0x18001dd3c  mov     rax, [rbp+arg_8]
0x18001dd40  test    rax, rax
0x18001dd43  jz      short loc_18001DD50
0x18001dd45  mov     rcx, rax
0x18001dd48  mov     [rbp+arg_8], 0
0x18001dd50  mov     dword ptr [rbp+pvarg+8], ecx
0x18001dd53  lea     rdx, [rbp+pvarg]; pvarSrc
0x18001dd57  sar     rcx, 20h
0x18001dd5b  mov     r9d, 3; vt
0x18001dd61  mov     dword ptr [rbp+pvarg+0Ch], ecx
0x18001dd64  lea     rcx, [rbp+pvarg]; pvargDest
0x18001dd68  lea     r8d, [r9+1]; wFlags
0x18001dd6c  call    cs:__imp_VariantChangeType
0x18001dd72  mov     edi, eax
0x18001dd74  test    eax, eax
0x18001dd76  js      short loc_18001DD83
0x18001dd78  mov     eax, dword ptr [rbp+pvarg+8]
0x18001dd7b  mov     [rsi], eax
0x18001dd7d  mov     dword ptr [rbx], 1
0x18001dd83  lea     rcx, [rbp+pvarg]; pvarg
0x18001dd87  call    cs:__imp_VariantClear
0x18001dd8d  lea     rcx, [rbp+arg_8]
0x18001dd91  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001dd96  mov     eax, edi
0x18001dd98  jmp     short loc_18001DDA8
0x18001dd9a  lea     rcx, [rbp+arg_8]
0x18001dd9e  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001dda3  mov     eax, 80070057h
0x18001dda8  lea     r11, [rsp+50h+var_s0]
0x18001ddad  mov     rbx, [r11+20h]
0x18001ddb1  mov     rsi, [r11+30h]
0x18001ddb5  mov     rsp, r11
0x18001ddb8  pop     r14
0x18001ddba  pop     rdi
0x18001ddbb  pop     rbp
0x18001ddbc  retn
```
