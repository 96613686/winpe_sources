# GetTuneXmlSchema(IXMLDOMSchemaCollection2 * *)

- ea: `0x1800544a8`
- end: `0x180054779`
- name: `?GetTuneXmlSchema@@YAJPEAPEAUIXMLDOMSchemaCollection2@@@Z`
- size: `721`
- prototype: `__int64 __fastcall(struct IXMLDOMSchemaCollection2 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180053a28`
- `0x1800540b8`

## callees

- `0x180004b28`
- `0x180004d20`
- `0x180004d88`
- `0x180006b38`
- `0x18001424c`
- `0x180014568`
- `0x180032f40`
- `0x1800544a8`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800544f0`
- `ole32!CoCreateInstance` at `0x18005461a`
- `ole32!CoCreateInstance` at `0x1800544f0`
- `ole32!CoCreateInstance` at `0x18005461a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800545f3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800545f3`
- `OLEAUT32!__imp_SysStringLen` at `0x18005453a`
- `OLEAUT32!__imp_SysStringLen` at `0x18005453a`
- `OLEAUT32!__imp_VariantClear` at `0x1800546f3`
- `OLEAUT32!__imp_VariantClear` at `0x1800546f3`
- `KERNEL32!SizeofResource` at `0x1800545a3`
- `KERNEL32!SizeofResource` at `0x1800545a3`
- `KERNEL32!LockResource` at `0x18005458f`
- `KERNEL32!LockResource` at `0x18005458f`
- `KERNEL32!LoadResource` at `0x180054581`
- `KERNEL32!LoadResource` at `0x180054581`
- `KERNEL32!FindResourceW` at `0x18005456d`
- `KERNEL32!FindResourceW` at `0x18005456d`
- `KERNEL32!GetLastError` at `0x1800545ad`
- `KERNEL32!GetLastError` at `0x1800545ad`
- `KERNEL32!GetModuleHandleW` at `0x18005454f`
- `KERNEL32!GetModuleHandleW` at `0x18005454f`

## string_xrefs

- `0x180054548`: `msvidctl.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetTuneXmlSchema(struct IXMLDOMSchemaCollection2 **a1)
{
  int v3; // edi
  struct IDispatch *v4; // rbx
  HMODULE ModuleHandleW; // rax
  HMODULE v6; // rdi
  HRSRC ResourceW; // rax
  HRSRC v8; // rsi
  HGLOBAL Resource; // rax
  const CHAR *v10; // r14
  DWORD v11; // eax
  signed int LastError; // eax
  OLECHAR *v13; // rbx
  int v14; // eax
  LPVOID v15; // rsi
  __int64 (__fastcall *v16)(LPVOID, OLECHAR *, __int128 *); // rdi
  __int64 v17; // rax
  int v18; // ebx
  struct IXMLDOMSchemaCollection2 *v19; // rax
  OLECHAR *v20; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-38h] BYREF
  __int128 v22; // [rsp+50h] [rbp-20h] BYREF
  __int64 v23; // [rsp+60h] [rbp-10h]
  __int16 v24; // [rsp+B0h] [rbp+40h] BYREF
  LPVOID v25; // [rsp+B8h] [rbp+48h] BYREF
  LPVOID ppv; // [rsp+C0h] [rbp+50h] BYREF
  struct IDispatch *v27; // [rsp+C8h] [rbp+58h] BYREF

  if ( !a1 )
    return 2147500035LL;
  ppv = 0;
  v3 = CoCreateInstance(&CLSID_XMLSchemaCache60, 0, 0x17u, &GUID_50ea08b0_dd1b_4664_9a50_c2f40f4bd79a, &ppv);
  if ( v3 >= 0 )
  {
    v4 = 0;
    v27 = 0;
    if ( dword_18021D990 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_18021D990);
      if ( dword_18021D990 == -1 )
      {
        pbstr = 0;
        atexit(GetTuneXmlSchemaFromResource_::_2_::_dynamic_atexit_destructor_for__g_bstrSchema__);
        Init_thread_footer(&dword_18021D990);
      }
    }
    if ( !pbstr || !SysStringLen(pbstr) )
    {
      ModuleHandleW = GetModuleHandleW(L"msvidctl.dll");
      v6 = ModuleHandleW;
      if ( !ModuleHandleW
        || (ResourceW = FindResourceW(ModuleHandleW, L"Tuning.xsd", (LPCWSTR)0x17), (v8 = ResourceW) == 0)
        || (Resource = LoadResource(v6, ResourceW)) == 0
        || (v10 = (const CHAR *)LockResource(Resource)) == 0
        || (v11 = SizeofResource(v6, v8)) == 0 )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 < 0 )
          goto LABEL_25;
LABEL_27:
        v15 = ppv;
        v16 = *(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int128 *))(*(_QWORD *)ppv + 56LL);
        v17 = ATL::CComVariant::CComVariant((ATL::CComVariant *)&pvarg, v4);
        v22 = *(_OWORD *)v17;
        v23 = *(_QWORD *)(v17 + 16);
        v18 = v16(v15, g_bstrTuneXmlNamespace, &v22);
        if ( pvarg.vt == 4095 )
          pvarg.vt = 8;
        VariantClear(&pvarg);
        if ( !v18 )
        {
          v19 = (struct IXMLDOMSchemaCollection2 *)ppv;
          ppv = 0;
          *a1 = v19;
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v27);
          v3 = 0;
          goto LABEL_34;
        }
        v3 = -2147467259;
        if ( v18 < 0 )
          v3 = v18;
        goto LABEL_25;
      }
      v13 = A2WBSTR(v10, v11);
      v20 = v13;
      ATL::CComBSTR::operator=(&pbstr, &v20);
      SysFreeString(v13);
    }
    v25 = 0;
    v3 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x17u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &v25);
    if ( v3 >= 0 )
    {
      v24 = 0;
      v14 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int16 *))(*(_QWORD *)v25 + 520LL))(v25, pbstr, &v24);
      if ( !v14 )
      {
        if ( v24 )
        {
          v4 = (struct IDispatch *)v25;
          v25 = 0;
          v27 = v4;
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v25);
          goto LABEL_27;
        }
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v25);
        v3 = -2147467259;
LABEL_25:
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v27);
        goto LABEL_34;
      }
      v3 = -2147467259;
      if ( v14 < 0 )
        v3 = v14;
    }
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v25);
    goto LABEL_25;
  }
LABEL_34:
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800544a8  push    rbp
0x1800544aa  push    rbx
0x1800544ab  push    rsi
0x1800544ac  push    rdi
0x1800544ad  push    r12
0x1800544af  push    r14
0x1800544b1  push    r15
0x1800544b3  mov     rbp, rsp
0x1800544b6  sub     rsp, 70h
0x1800544ba  mov     r15, rcx
0x1800544bd  xor     r12d, r12d
0x1800544c0  test    rcx, rcx
0x1800544c3  jnz     short loc_1800544CF
0x1800544c5  mov     eax, 80004003h
0x1800544ca  jmp     loc_18005472C
0x1800544cf  mov     [rbp+arg_10], r12
0x1800544d3  lea     rax, [rbp+arg_10]
0x1800544d7  mov     [rsp+70h+ppv], rax; ppv
0x1800544dc  lea     r9, _GUID_50ea08b0_dd1b_4664_9a50_c2f40f4bd79a; riid
0x1800544e3  xor     edx, edx; pUnkOuter
0x1800544e5  lea     r8d, [rdx+17h]; dwClsContext
0x1800544e9  lea     rcx, CLSID_XMLSchemaCache60; rclsid
0x1800544f0  call    cs:__imp_CoCreateInstance
0x1800544f6  mov     edi, eax
0x1800544f8  test    eax, eax
0x1800544fa  js      loc_180054721
0x180054500  mov     rbx, r12
0x180054503  mov     [rbp+arg_18], rbx
0x180054507  mov     ecx, cs:_tls_index
0x18005450d  mov     rax, gs:58h
0x180054516  mov     edx, 4
0x18005451b  mov     rax, [rax+rcx*8]
0x18005451f  mov     eax, [rdx+rax]
0x180054522  cmp     cs:dword_18021D990, eax
0x180054528  jg      loc_18005473B
0x18005452e  mov     rcx, cs:pbstr; pbstr
0x180054535  test    rcx, rcx
0x180054538  jz      short loc_180054548
0x18005453a  call    cs:__imp_SysStringLen
0x180054540  test    eax, eax
0x180054542  jnz     loc_1800545F9
0x180054548  lea     rcx, aMsvidctlDll_0; "msvidctl.dll"
0x18005454f  call    cs:__imp_GetModuleHandleW
0x180054555  mov     rdi, rax
0x180054558  test    rax, rax
0x18005455b  jz      short loc_1800545AD
0x18005455d  mov     r8d, 17h; lpType
0x180054563  lea     rdx, Name; "Tuning.xsd"
0x18005456a  mov     rcx, rax; hModule
0x18005456d  call    cs:__imp_FindResourceW
0x180054573  mov     rsi, rax
0x180054576  test    rax, rax
0x180054579  jz      short loc_1800545AD
0x18005457b  mov     rdx, rax; hResInfo
0x18005457e  mov     rcx, rdi; hModule
0x180054581  call    cs:__imp_LoadResource
0x180054587  test    rax, rax
0x18005458a  jz      short loc_1800545AD
0x18005458c  mov     rcx, rax; hResData
0x18005458f  call    cs:__imp_LockResource
0x180054595  mov     r14, rax
0x180054598  test    rax, rax
0x18005459b  jz      short loc_1800545AD
0x18005459d  mov     rdx, rsi; hResInfo
0x1800545a0  mov     rcx, rdi; hModule
0x1800545a3  call    cs:__imp_SizeofResource
0x1800545a9  test    eax, eax
0x1800545ab  jnz     short loc_1800545CF
0x1800545ad  call    cs:__imp_GetLastError
0x1800545b3  mov     edi, eax
0x1800545b5  test    eax, eax
0x1800545b7  jle     short loc_1800545C2
0x1800545b9  movzx   edi, ax
0x1800545bc  or      edi, 80070000h
0x1800545c2  test    edi, edi
0x1800545c4  jns     loc_18005469A
0x1800545ca  jmp     loc_180054677
0x1800545cf  mov     edx, eax; cbMultiByte
0x1800545d1  mov     rcx, r14; lpMultiByteStr
0x1800545d4  call    ?A2WBSTR@@YAPEAGPEBDH@Z; A2WBSTR(char const *,int)
0x1800545d9  mov     rbx, rax
0x1800545dc  mov     [rbp+var_40], rax
0x1800545e0  lea     rdx, [rbp+var_40]
0x1800545e4  lea     rcx, pbstr
0x1800545eb  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x1800545f0  mov     rcx, rbx; bstrString
0x1800545f3  call    cs:__imp_SysFreeString
0x1800545f9  mov     [rbp+arg_8], r12
0x1800545fd  lea     rax, [rbp+arg_8]
0x180054601  mov     [rsp+70h+ppv], rax; ppv
0x180054606  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18005460d  xor     edx, edx; pUnkOuter
0x18005460f  lea     r8d, [rdx+17h]; dwClsContext
0x180054613  lea     rcx, CLSID_DOMDocument60; rclsid
0x18005461a  call    cs:__imp_CoCreateInstance
0x180054620  mov     edi, eax
0x180054622  test    eax, eax
0x180054624  jns     short loc_180054631
0x180054626  lea     rcx, [rbp+arg_8]
0x18005462a  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18005462f  jmp     short loc_180054677
0x180054631  mov     [rbp+arg_0], r12w
0x180054636  mov     rcx, [rbp+arg_8]
0x18005463a  mov     rax, [rcx]
0x18005463d  lea     r8, [rbp+arg_0]
0x180054641  mov     rdx, cs:pbstr
0x180054648  mov     rax, [rax+208h]
0x18005464f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054654  test    eax, eax
0x180054656  jz      short loc_180054662
0x180054658  mov     edi, 80004005h
0x18005465d  cmovs   edi, eax
0x180054660  jmp     short loc_180054626
0x180054662  cmp     [rbp+arg_0], r12w
0x180054667  jnz     short loc_180054685
0x180054669  lea     rcx, [rbp+arg_8]
0x18005466d  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180054672  mov     edi, 80004005h
0x180054677  lea     rcx, [rbp+arg_18]
0x18005467b  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180054680  jmp     loc_180054721
0x180054685  mov     rbx, [rbp+arg_8]
0x180054689  mov     [rbp+arg_8], r12
0x18005468d  mov     [rbp+arg_18], rbx
0x180054691  lea     rcx, [rbp+arg_8]
0x180054695  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18005469a  mov     rsi, [rbp+arg_10]
0x18005469e  mov     rax, [rsi]
0x1800546a1  mov     rdi, [rax+38h]
0x1800546a5  mov     rdx, rbx; struct IDispatch *
0x1800546a8  lea     rcx, [rbp+pvarg]; this
0x1800546ac  call    ??0CComVariant@ATL@@QEAA@PEAUIDispatch@@@Z; ATL::CComVariant::CComVariant(IDispatch *)
0x1800546b1  nop
0x1800546b2  movups  xmm0, xmmword ptr [rax]
0x1800546b5  movaps  [rbp+var_20], xmm0
0x1800546b9  movsd   xmm1, qword ptr [rax+10h]
0x1800546be  movsd   [rbp+var_10], xmm1
0x1800546c3  lea     r8, [rbp+var_20]
0x1800546c7  mov     rdx, cs:?g_bstrTuneXmlNamespace@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrTuneXmlNamespace
0x1800546ce  mov     rcx, rsi
0x1800546d1  mov     rax, rdi
0x1800546d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800546d9  mov     ebx, eax
0x1800546db  mov     eax, 0FFFh
0x1800546e0  cmp     word ptr [rbp+pvarg], ax
0x1800546e4  jnz     short loc_1800546EF
0x1800546e6  mov     eax, 8
0x1800546eb  mov     word ptr [rbp+pvarg], ax
0x1800546ef  lea     rcx, [rbp+pvarg]; pvarg
0x1800546f3  call    cs:__imp_VariantClear
0x1800546f9  test    ebx, ebx
0x1800546fb  jz      short loc_18005470A
0x1800546fd  mov     edi, 80004005h
0x180054702  cmovs   edi, ebx
0x180054705  jmp     loc_180054677
0x18005470a  mov     rax, [rbp+arg_10]
0x18005470e  mov     [rbp+arg_10], r12
0x180054712  mov     [r15], rax
0x180054715  lea     rcx, [rbp+arg_18]
0x180054719  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18005471e  mov     edi, r12d
0x180054721  lea     rcx, [rbp+arg_10]
0x180054725  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18005472a  mov     eax, edi
0x18005472c  add     rsp, 70h
0x180054730  pop     r15
0x180054732  pop     r14
0x180054734  pop     r12
0x180054736  pop     rdi
0x180054737  pop     rsi
0x180054738  pop     rbx
0x180054739  pop     rbp
0x18005473a  retn
0x18005473b  lea     rcx, dword_18021D990
0x180054742  call    _Init_thread_header
0x180054747  cmp     cs:dword_18021D990, 0FFFFFFFFh
0x18005474e  jnz     loc_18005452E
0x180054754  mov     cs:pbstr, r12
0x18005475b  lea     rcx, _GetTuneXmlSchemaFromResource____2____dynamic_atexit_destructor_for__g_bstrSchema__; void (__cdecl *)()
0x180054762  call    atexit
0x180054767  lea     rcx, dword_18021D990
0x18005476e  call    _Init_thread_footer
0x180054773  jmp     loc_18005452E
```
