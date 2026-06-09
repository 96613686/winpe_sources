# InitXMLDOMDoc(ushort const *,ushort const *,IXMLDOMDocument2 * *)

- ea: `0x18005d01c`
- end: `0x18005d20e`
- name: `?InitXMLDOMDoc@@YAJPEBG0PEAPEAUIXMLDOMDocument2@@@Z`
- size: `498`
- prototype: `__int64 __fastcall(OLECHAR *psz, OLECHAR *, LPVOID *ppv)`
- caller_count: `9`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800141d0`
- `0x180016530`
- `0x180050884`
- `0x18005a1cc`
- `0x18005a950`
- `0x18005ab64`
- `0x18005b110`
- `0x18005bc28`
- `0x18005d2ac`

## callees

- `0x1800140d0`
- `0x18001aec8`
- `0x18005d01c`
- `0x180072698`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005d0a2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005d0a2`
- `OLEAUT32!__imp_SysAllocString` at `0x18005d06f`
- `OLEAUT32!__imp_SysAllocString` at `0x18005d145`
- `OLEAUT32!__imp_SysAllocString` at `0x18005d15a`
- `OLEAUT32!__imp_SysAllocString` at `0x18005d06f`
- `OLEAUT32!__imp_SysAllocString` at `0x18005d145`
- `OLEAUT32!__imp_SysAllocString` at `0x18005d15a`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d1c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d1c9`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d1c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d1c9`
- `OLEAUT32!__imp_VariantInit` at `0x18005d052`
- `OLEAUT32!__imp_VariantInit` at `0x18005d052`
- `OLEAUT32!__imp_VariantClear` at `0x18005d1d3`
- `OLEAUT32!__imp_VariantClear` at `0x18005d1ea`
- `OLEAUT32!__imp_VariantClear` at `0x18005d1d3`
- `OLEAUT32!__imp_VariantClear` at `0x18005d1ea`

## string_xrefs

- `0x18005d059`: `InitXMLDOMDoc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InitXMLDOMDoc(OLECHAR *psz, OLECHAR *a2, LPVOID *ppv)
{
  __int64 v6; // rdx
  OLECHAR *v7; // r15
  unsigned int v8; // ebx
  OLECHAR *v9; // rsi
  BSTR v10; // rax
  LPVOID v11; // rcx
  CEnrollmentLogger *Logger; // rax
  int Instance; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v15[2]; // [rsp+38h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG v17; // [rsp+60h] [rbp-20h] BYREF
  __int16 v18; // [rsp+C8h] [rbp+48h] BYREF

  Instance = 0;
  v18 = 0;
  VariantInit(&pvarg);
  v15[0] = "InitXMLDOMDoc";
  v15[1] = &Instance;
  v7 = SysAllocString(psz);
  if ( v7 )
  {
    v9 = 0;
    Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, ppv);
    if ( Instance >= 0 )
    {
      if ( *ppv )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*ppv + 504LL))(*ppv, 0);
        if ( Instance < 0 )
          goto LABEL_15;
        Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*ppv + 544LL))(*ppv, 0);
        if ( Instance < 0 )
          goto LABEL_15;
        Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*ppv + 560LL))(*ppv, 0);
        if ( Instance < 0 )
          goto LABEL_15;
        Instance = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int16 *))(*(_QWORD *)*ppv + 520LL))(*ppv, v7, &v18);
        if ( Instance < 0 )
          goto LABEL_15;
        if ( !a2 )
          goto LABEL_16;
        v9 = SysAllocString(L"SelectionNamespaces");
        pvarg.vt = 8;
        v10 = SysAllocString(a2);
        pvarg.llVal = (LONGLONG)v10;
        if ( v9 && v10 )
        {
          v11 = *ppv;
          v17 = pvarg;
          Instance = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(*(_QWORD *)v11 + 640LL))(
                       v11,
                       v9,
                       &v17);
          if ( Instance < 0 )
            goto LABEL_15;
LABEL_16:
          SysFreeString(v7);
          SysFreeString(v9);
          VariantClear(&pvarg);
          v8 = Instance;
          goto LABEL_17;
        }
      }
      Instance = -2147024882;
    }
LABEL_15:
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollServerMessageParsingError(Logger, Instance, "InitXMLDOMDoc");
    goto LABEL_16;
  }
  v8 = -2147024882;
LABEL_17:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v15, v6);
  VariantClear(&pvarg);
  return v8;
}

```

## disassembly

```asm
0x18005d01c  mov     [rsp-28h+arg_0], rbx
0x18005d021  mov     [rsp-28h+arg_8], rsi
0x18005d026  push    rbp
0x18005d027  push    rdi
0x18005d028  push    r12
0x18005d02a  push    r14
0x18005d02c  push    r15
0x18005d02e  mov     rbp, rsp
0x18005d031  sub     rsp, 80h
0x18005d038  mov     rdi, r8
0x18005d03b  mov     r14, rdx
0x18005d03e  mov     rbx, rcx
0x18005d041  mov     [rbp+var_50], 0
0x18005d048  xor     eax, eax
0x18005d04a  mov     [rbp+arg_18], ax
0x18005d04e  lea     rcx, [rbp+pvarg]; pvarg
0x18005d052  call    cs:__imp_VariantInit
0x18005d058  nop
0x18005d059  lea     r12, aInitxmldomdoc; "InitXMLDOMDoc"
0x18005d060  mov     [rbp+var_48], r12
0x18005d064  lea     rax, [rbp+var_50]
0x18005d068  mov     [rbp+var_40], rax
0x18005d06c  mov     rcx, rbx; psz
0x18005d06f  call    cs:__imp_SysAllocString
0x18005d075  mov     r15, rax
0x18005d078  test    rax, rax
0x18005d07b  jnz     short loc_18005D087
0x18005d07d  mov     ebx, 8007000Eh
0x18005d082  jmp     loc_18005D1DC
0x18005d087  xor     esi, esi
0x18005d089  mov     [rsp+80h+ppv], rdi; ppv
0x18005d08e  lea     r9, IID_IXMLDOMDocument2; riid
0x18005d095  xor     edx, edx; pUnkOuter
0x18005d097  lea     r8d, [rsi+1]; dwClsContext
0x18005d09b  lea     rcx, CLSID_DOMDocument60; rclsid
0x18005d0a2  call    cs:__imp_CoCreateInstance
0x18005d0a8  mov     [rbp+var_50], eax
0x18005d0ab  test    eax, eax
0x18005d0ad  js      loc_18005D1AA
0x18005d0b3  mov     rcx, [rdi]
0x18005d0b6  test    rcx, rcx
0x18005d0b9  jz      loc_18005D1A2
0x18005d0bf  mov     rax, [rcx]
0x18005d0c2  xor     edx, edx
0x18005d0c4  mov     rax, [rax+1F8h]
0x18005d0cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d0d0  mov     [rbp+var_50], eax
0x18005d0d3  test    eax, eax
0x18005d0d5  js      loc_18005D1AA
0x18005d0db  mov     rcx, [rdi]
0x18005d0de  mov     rax, [rcx]
0x18005d0e1  xor     edx, edx
0x18005d0e3  mov     rax, [rax+220h]
0x18005d0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d0ef  mov     [rbp+var_50], eax
0x18005d0f2  test    eax, eax
0x18005d0f4  js      loc_18005D1AA
0x18005d0fa  mov     rcx, [rdi]
0x18005d0fd  mov     rax, [rcx]
0x18005d100  xor     edx, edx
0x18005d102  mov     rax, [rax+230h]
0x18005d109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d10e  mov     [rbp+var_50], eax
0x18005d111  test    eax, eax
0x18005d113  js      loc_18005D1AA
0x18005d119  mov     rcx, [rdi]
0x18005d11c  mov     rax, [rcx]
0x18005d11f  lea     r8, [rbp+arg_18]
0x18005d123  mov     rdx, r15
0x18005d126  mov     rax, [rax+208h]
0x18005d12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d132  mov     [rbp+var_50], eax
0x18005d135  test    eax, eax
0x18005d137  js      short loc_18005D1AA
0x18005d139  test    r14, r14
0x18005d13c  jz      short loc_18005D1BD
0x18005d13e  lea     rcx, aSelectionnames; "SelectionNamespaces"
0x18005d145  call    cs:__imp_SysAllocString
0x18005d14b  mov     rsi, rax
0x18005d14e  mov     eax, 8
0x18005d153  mov     word ptr [rbp+pvarg], ax
0x18005d157  mov     rcx, r14; psz
0x18005d15a  call    cs:__imp_SysAllocString
0x18005d160  mov     qword ptr [rbp+pvarg+8], rax
0x18005d164  test    rsi, rsi
0x18005d167  jz      short loc_18005D1A2
0x18005d169  test    rax, rax
0x18005d16c  jz      short loc_18005D1A2
0x18005d16e  mov     rcx, [rdi]
0x18005d171  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18005d175  movaps  [rbp+var_20], xmm0
0x18005d179  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18005d17e  movsd   [rbp+var_10], xmm1
0x18005d183  mov     rax, [rcx]
0x18005d186  lea     r8, [rbp+var_20]
0x18005d18a  mov     rdx, rsi
0x18005d18d  mov     rax, [rax+280h]
0x18005d194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d199  mov     [rbp+var_50], eax
0x18005d19c  test    eax, eax
0x18005d19e  jns     short loc_18005D1BD
0x18005d1a0  jmp     short loc_18005D1AA
0x18005d1a2  mov     ebx, 8007000Eh
0x18005d1a7  mov     [rbp+var_50], ebx
0x18005d1aa  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18005d1af  mov     r8, r12; char *
0x18005d1b2  mov     edx, [rbp+var_50]; int
0x18005d1b5  mov     rcx, rax; this
0x18005d1b8  call    ?LogEnrollServerMessageParsingError@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollServerMessageParsingError(long,char const *)
0x18005d1bd  mov     rcx, r15; bstrString
0x18005d1c0  call    cs:__imp_SysFreeString
0x18005d1c6  mov     rcx, rsi; bstrString
0x18005d1c9  call    cs:__imp_SysFreeString
0x18005d1cf  lea     rcx, [rbp+pvarg]; pvarg
0x18005d1d3  call    cs:__imp_VariantClear
0x18005d1d9  mov     ebx, [rbp+var_50]
0x18005d1dc  lea     rcx, [rbp+var_48]; this
0x18005d1e0  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18005d1e5  nop
0x18005d1e6  lea     rcx, [rbp+pvarg]; pvarg
0x18005d1ea  call    cs:__imp_VariantClear
0x18005d1f0  mov     eax, ebx
0x18005d1f2  lea     r11, [rsp+80h+var_s0]
0x18005d1fa  mov     rbx, [r11+30h]
0x18005d1fe  mov     rsi, [r11+38h]
0x18005d202  mov     rsp, r11
0x18005d205  pop     r15
0x18005d207  pop     r14
0x18005d209  pop     r12
0x18005d20b  pop     rdi
0x18005d20c  pop     rbp
0x18005d20d  retn
```
