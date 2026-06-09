# PlaiReadXmlGuid(ushort const *,IXMLDOMNode *,_GUID *)

- ea: `0x180045608`
- end: `0x18004585d`
- name: `?PlaiReadXmlGuid@@YAJPEBGPEAUIXMLDOMNode@@PEAU_GUID@@@Z`
- size: `597`
- prototype: `int(const unsigned __int16 *, struct IXMLDOMNode *, struct _GUID *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180014310`
- `0x180044924`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800182a4`
- `0x180040840`
- `0x180045608`
- `0x18005179c`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800457e6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800457e6`
- `OLEAUT32!__imp_SysFreeString` at `0x180045831`
- `OLEAUT32!__imp_SysFreeString` at `0x180045831`
- `OLEAUT32!__imp_VariantInit` at `0x18004565e`
- `OLEAUT32!__imp_VariantInit` at `0x18004566c`
- `OLEAUT32!__imp_VariantInit` at `0x18004565e`
- `OLEAUT32!__imp_VariantInit` at `0x18004566c`
- `OLEAUT32!__imp_VariantClear` at `0x180045810`
- `OLEAUT32!__imp_VariantClear` at `0x18004581e`
- `OLEAUT32!__imp_VariantClear` at `0x180045810`
- `OLEAUT32!__imp_VariantClear` at `0x18004581e`

## string_xrefs

- `0x180045717`: `PlaiReadXmlGuid`

## pseudocode

```c
__int64 __fastcall PlaiReadXmlGuid(const unsigned __int16 *a1, struct IXMLDOMNode *a2, struct _GUID *a3)
{
  const char *v5; // r8
  int v6; // r9d
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rcx
  HRESULT (__stdcall *get_namespaceURI)(IXMLDOMNode *, BSTR *); // rbx
  __int64 v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  __int64 v17; // [rsp+70h] [rbp-90h] BYREF
  int v18; // [rsp+78h] [rbp-88h] BYREF
  int v19; // [rsp+80h] [rbp-80h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v21; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 v23[64]; // [rsp+C0h] [rbp-40h] BYREF

  v17 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  bstrString = 0;
  memset(&v21, 0, sizeof(v21));
  VariantInit(&pvarg);
  pvarg.llVal = 0;
  VariantInit(&v21);
  v21.llVal = 0;
  v7 = PlaiSetVariantEx(L"Guid", &pvarg, v5, v6);
  v8 = v7;
  if ( v7 < 0 )
  {
    v18 = 0;
    v19 = v7;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v23, 0x4000000000000800uLL);
      v9 = -1;
      do
        ++v9;
      while ( v23[v9] );
      EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v19, 4, qword_180147320, 1, &v18, 4, "PlaiReadXmlGuid", 16);
    }
    goto LABEL_8;
  }
  get_namespaceURI = a2->lpVtbl->get_namespaceURI;
  v12 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&bstrString);
  v13 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64))get_namespaceURI)(a2, v12);
  if ( v13 != 1 )
    MicrosoftTelemetryAssertTriggeredArgs(v14, v13);
  v15 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, LONGLONG, __int64 *))a2->lpVtbl->selectSingleNode)(
          a2,
          pvarg.llVal,
          &v17);
  v10 = v17;
  if ( v15 >= 0 && v17 )
  {
    v21.vt = 8;
    v8 = (*(__int64 (__fastcall **)(__int64, CY *))(*(_QWORD *)v17 + 208LL))(v17, &v21.cyVal);
    CLSIDFromString(v21.bstrVal, a3);
LABEL_8:
    v10 = v17;
    goto LABEL_15;
  }
  v8 = -2147024637;
LABEL_15:
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v17 = 0;
  }
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  VariantClear(&v21);
  v21.llVal = 0;
  if ( bstrString )
    SysFreeString(bstrString);
  return v8;
}

```

## disassembly

```asm
0x180045608  mov     [rsp-8+arg_0], rbx
0x18004560d  mov     [rsp-8+arg_18], rsi
0x180045612  push    rbp
0x180045613  push    rdi
0x180045614  push    r14
0x180045616  lea     rbp, [rsp-50h]
0x18004561b  sub     rsp, 150h
0x180045622  mov     rax, cs:__security_cookie
0x180045629  xor     rax, rsp
0x18004562c  mov     [rbp+60h+var_20], rax
0x180045630  xor     eax, eax
0x180045632  lea     rcx, [rbp+60h+pvarg]; pvarg
0x180045636  xor     r14d, r14d
0x180045639  mov     qword ptr [rbp+60h+pvarg+10h], rax
0x18004563d  xorps   xmm0, xmm0
0x180045640  mov     [rsp+160h+var_F0], r14
0x180045645  xorps   xmm1, xmm1
0x180045648  mov     qword ptr [rbp+60h+var_D0+10h], rax
0x18004564c  movups  xmmword ptr [rbp+60h+pvarg], xmm0
0x180045650  mov     [rbp+60h+bstrString], r14
0x180045654  mov     rsi, r8
0x180045657  movups  xmmword ptr [rbp+60h+var_D0], xmm1
0x18004565b  mov     rdi, rdx
0x18004565e  call    cs:__imp_VariantInit
0x180045664  lea     rcx, [rbp+60h+var_D0]; pvarg
0x180045668  mov     qword ptr [rbp+60h+pvarg+8], r14
0x18004566c  call    cs:__imp_VariantInit
0x180045672  lea     rdx, [rbp+60h+pvarg]; pvarg
0x180045676  mov     qword ptr [rbp+60h+var_D0+8], r14
0x18004567a  lea     rcx, aGuid; "Guid"
0x180045681  call    ?PlaiSetVariantEx@@YAJPEBGPEAUtagVARIANT@@PEBDH@Z; PlaiSetVariantEx(ushort const *,tagVARIANT *,char const *,int)
0x180045686  mov     ebx, eax
0x180045688  test    eax, eax
0x18004568a  jns     loc_18004576B
0x180045690  cmp     dword ptr cs:xmmword_180169738, r14d
0x180045697  mov     [rsp+160h+var_E8], r14d
0x18004569c  mov     [rbp+60h+var_E0], eax
0x18004569f  jz      loc_180045761
0x1800456a5  mov     rdx, 4000000000000800h; unsigned __int64
0x1800456af  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800456b6  jz      loc_180045761
0x1800456bc  mov     rax, cs:qword_180169748
0x1800456c3  and     rax, rdx
0x1800456c6  cmp     cs:qword_180169748, rax
0x1800456cd  jnz     loc_180045761
0x1800456d3  lea     rcx, [rbp+60h+var_A0]; unsigned __int16 *
0x1800456d7  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800456dc  lea     rcx, [rbp+60h+var_A0]
0x1800456e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800456e4  inc     rax
0x1800456e7  cmp     [rcx+rax*2], r14w
0x1800456ec  jnz     short loc_1800456E4
0x1800456ee  lea     ecx, [rax+rax]
0x1800456f1  add     rcx, 2
0x1800456f5  lea     rax, [rbp+60h+var_A0]
0x1800456f9  mov     [rsp+160h+var_100], rcx
0x1800456fe  lea     r9, [rbp+60h+var_E0]
0x180045702  mov     [rsp+160h+var_108], rax
0x180045707  lea     rdx, PLA_EVENT_ERROR
0x18004570e  mov     [rsp+160h+var_110], 10h
0x180045717  lea     rax, aPlaireadxmlgui; "PlaiReadXmlGuid"
0x18004571e  mov     [rsp+160h+var_118], rax
0x180045723  mov     ecx, 4
0x180045728  mov     [rsp+160h+var_120], rcx
0x18004572d  lea     rax, [rsp+160h+var_E8]
0x180045732  mov     [rsp+160h+var_128], rax
0x180045737  lea     rax, qword_180147320
0x18004573e  mov     [rsp+160h+var_130], 1
0x180045747  mov     [rsp+160h+var_138], rax
0x18004574c  lea     r8d, [rcx+1]
0x180045750  mov     [rsp+160h+var_140], rcx
0x180045755  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004575c  call    EventingWriteEvent
0x180045761  mov     rcx, [rsp+160h+var_F0]
0x180045766  jmp     loc_1800457F6
0x18004576b  mov     rax, [rdi]
0x18004576e  lea     rcx, [rbp+60h+bstrString]
0x180045772  mov     rbx, [rax+138h]
0x180045779  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18004577e  mov     rdx, rax
0x180045781  mov     rcx, rdi
0x180045784  mov     rax, rbx
0x180045787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004578c  cmp     eax, 1
0x18004578f  jz      short loc_180045798
0x180045791  mov     edx, eax
0x180045793  call    MicrosoftTelemetryAssertTriggeredArgs
0x180045798  mov     rax, [rdi]
0x18004579b  lea     r8, [rsp+160h+var_F0]
0x1800457a0  mov     rdx, qword ptr [rbp+60h+pvarg+8]
0x1800457a4  mov     rcx, rdi
0x1800457a7  mov     rax, [rax+128h]
0x1800457ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800457b3  mov     rcx, [rsp+160h+var_F0]
0x1800457b8  test    eax, eax
0x1800457ba  js      short loc_1800457F1
0x1800457bc  test    rcx, rcx
0x1800457bf  jz      short loc_1800457F1
0x1800457c1  mov     eax, 8
0x1800457c6  lea     rdx, [rbp+60h+var_D0+8]
0x1800457ca  mov     word ptr [rbp+60h+var_D0], ax
0x1800457ce  mov     rax, [rcx]
0x1800457d1  mov     rax, [rax+0D0h]
0x1800457d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800457dd  mov     rcx, qword ptr [rbp+60h+var_D0+8]; lpsz
0x1800457e1  mov     rdx, rsi; pclsid
0x1800457e4  mov     ebx, eax
0x1800457e6  call    cs:__imp_CLSIDFromString
0x1800457ec  jmp     loc_180045761
0x1800457f1  mov     ebx, 80070103h
0x1800457f6  test    rcx, rcx
0x1800457f9  jz      short loc_18004580C
0x1800457fb  mov     rax, [rcx]
0x1800457fe  mov     rax, [rax+10h]
0x180045802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045807  mov     [rsp+160h+var_F0], r14
0x18004580c  lea     rcx, [rbp+60h+pvarg]; pvarg
0x180045810  call    cs:__imp_VariantClear
0x180045816  lea     rcx, [rbp+60h+var_D0]; pvarg
0x18004581a  mov     qword ptr [rbp+60h+pvarg+8], r14
0x18004581e  call    cs:__imp_VariantClear
0x180045824  mov     rcx, [rbp+60h+bstrString]; bstrString
0x180045828  mov     qword ptr [rbp+60h+var_D0+8], r14
0x18004582c  test    rcx, rcx
0x18004582f  jz      short loc_180045837
0x180045831  call    cs:__imp_SysFreeString
0x180045837  mov     eax, ebx
0x180045839  mov     rcx, [rbp+60h+var_20]
0x18004583d  xor     rcx, rsp; StackCookie
0x180045840  call    __security_check_cookie
0x180045845  lea     r11, [rsp+160h+var_10]
0x18004584d  mov     rbx, [r11+20h]
0x180045851  mov     rsi, [r11+38h]
0x180045855  mov     rsp, r11
0x180045858  pop     r14
0x18004585a  pop     rdi
0x18004585b  pop     rbp
0x18004585c  retn
```
