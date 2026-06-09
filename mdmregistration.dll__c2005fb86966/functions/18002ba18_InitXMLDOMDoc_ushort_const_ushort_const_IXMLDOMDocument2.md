# InitXMLDOMDoc(ushort const *,ushort const *,IXMLDOMDocument2 * *)

- ea: `0x18002ba18`
- end: `0x18002bc49`
- name: `?InitXMLDOMDoc@@YAJPEBG0PEAPEAUIXMLDOMDocument2@@@Z`
- size: `561`
- prototype: `__int64 __fastcall(OLECHAR *psz, OLECHAR *, LPVOID *ppv)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800226a4`
- `0x180022948`
- `0x180022e74`
- `0x1800284a0`
- `0x180028728`
- `0x180028ee8`
- `0x180029ac4`
- `0x18002bcdc`

## callees

- `0x1800141b0`
- `0x18002ba18`
- `0x180041410`
- `0x1800438ac`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002baaa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002baaa`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ba71`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bb5b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bb76`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ba71`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bb5b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bb76`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bbe2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bbf1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bbe2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bbf1`
- `OLEAUT32!__imp_VariantInit` at `0x18002ba4e`
- `OLEAUT32!__imp_VariantInit` at `0x18002ba4e`
- `OLEAUT32!__imp_VariantClear` at `0x18002bc01`
- `OLEAUT32!__imp_VariantClear` at `0x18002bc1e`
- `OLEAUT32!__imp_VariantClear` at `0x18002bc01`
- `OLEAUT32!__imp_VariantClear` at `0x18002bc1e`

## string_xrefs

- `0x18002ba5b`: `InitXMLDOMDoc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InitXMLDOMDoc(OLECHAR *psz, OLECHAR *a2, LPVOID *ppv)
{
  OLECHAR *v6; // r15
  unsigned int v7; // ebx
  OLECHAR *v8; // rsi
  BSTR v9; // rax
  LPVOID v10; // rcx
  CEnrollmentLogger *Logger; // rax
  int Instance; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v14[2]; // [rsp+38h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG v16; // [rsp+60h] [rbp-20h] BYREF
  __int16 v17; // [rsp+C8h] [rbp+48h] BYREF

  Instance = 0;
  v17 = 0;
  VariantInit(&pvarg);
  v14[0] = "InitXMLDOMDoc";
  v14[1] = &Instance;
  v6 = SysAllocString(psz);
  if ( v6 )
  {
    v8 = 0;
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
        Instance = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int16 *))(*(_QWORD *)*ppv + 520LL))(*ppv, v6, &v17);
        if ( Instance < 0 )
          goto LABEL_15;
        if ( !a2 )
          goto LABEL_16;
        v8 = SysAllocString(L"SelectionNamespaces");
        pvarg.vt = 8;
        v9 = SysAllocString(a2);
        pvarg.llVal = (LONGLONG)v9;
        if ( v8 && v9 )
        {
          v10 = *ppv;
          v16 = pvarg;
          Instance = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(*(_QWORD *)v10 + 640LL))(
                       v10,
                       v8,
                       &v16);
          if ( Instance < 0 )
            goto LABEL_15;
LABEL_16:
          SysFreeString(v6);
          SysFreeString(v8);
          VariantClear(&pvarg);
          v7 = Instance;
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
  v7 = -2147024882;
LABEL_17:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v14);
  VariantClear(&pvarg);
  return v7;
}

```

## disassembly

```asm
0x18002ba18  mov     [rsp-28h+arg_0], rbx
0x18002ba1d  mov     [rsp-28h+arg_8], rsi
0x18002ba22  push    rbp
0x18002ba23  push    rdi
0x18002ba24  push    r12
0x18002ba26  push    r14
0x18002ba28  push    r15
0x18002ba2a  mov     rbp, rsp
0x18002ba2d  sub     rsp, 80h
0x18002ba34  mov     rdi, r8
0x18002ba37  mov     r14, rdx
0x18002ba3a  mov     rbx, rcx
0x18002ba3d  mov     [rbp+var_50], 0
0x18002ba44  xor     eax, eax
0x18002ba46  mov     [rbp+arg_18], ax
0x18002ba4a  lea     rcx, [rbp+pvarg]; pvarg
0x18002ba4e  call    cs:__imp_VariantInit
0x18002ba55  nop     dword ptr [rax+rax+00h]
0x18002ba5a  nop
0x18002ba5b  lea     r12, aInitxmldomdoc; "InitXMLDOMDoc"
0x18002ba62  mov     [rbp+var_48], r12
0x18002ba66  lea     rax, [rbp+var_50]
0x18002ba6a  mov     [rbp+var_40], rax
0x18002ba6e  mov     rcx, rbx; psz
0x18002ba71  call    cs:__imp_SysAllocString
0x18002ba78  nop     dword ptr [rax+rax+00h]
0x18002ba7d  mov     r15, rax
0x18002ba80  test    rax, rax
0x18002ba83  jnz     short loc_18002BA8F
0x18002ba85  mov     ebx, 8007000Eh
0x18002ba8a  jmp     loc_18002BC10
0x18002ba8f  xor     esi, esi
0x18002ba91  mov     [rsp+80h+ppv], rdi; ppv
0x18002ba96  lea     r9, IID_IXMLDOMDocument2; riid
0x18002ba9d  xor     edx, edx; pUnkOuter
0x18002ba9f  lea     r8d, [rsi+1]; dwClsContext
0x18002baa3  lea     rcx, CLSID_DOMDocument60; rclsid
0x18002baaa  call    cs:__imp_CoCreateInstance
0x18002bab1  nop     dword ptr [rax+rax+00h]
0x18002bab6  mov     [rbp+var_50], eax
0x18002bab9  test    eax, eax
0x18002babb  js      loc_18002BBCC
0x18002bac1  mov     rcx, [rdi]
0x18002bac4  test    rcx, rcx
0x18002bac7  jz      loc_18002BBC4
0x18002bacd  mov     rax, [rcx]
0x18002bad0  xor     edx, edx
0x18002bad2  mov     rax, [rax+1F8h]
0x18002bad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bade  mov     [rbp+var_50], eax
0x18002bae1  test    eax, eax
0x18002bae3  js      loc_18002BBCC
0x18002bae9  mov     rcx, [rdi]
0x18002baec  mov     rax, [rcx]
0x18002baef  xor     edx, edx
0x18002baf1  mov     rax, [rax+220h]
0x18002baf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bafd  mov     [rbp+var_50], eax
0x18002bb00  test    eax, eax
0x18002bb02  js      loc_18002BBCC
0x18002bb08  mov     rcx, [rdi]
0x18002bb0b  mov     rax, [rcx]
0x18002bb0e  xor     edx, edx
0x18002bb10  mov     rax, [rax+230h]
0x18002bb17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb1c  mov     [rbp+var_50], eax
0x18002bb1f  test    eax, eax
0x18002bb21  js      loc_18002BBCC
0x18002bb27  mov     rcx, [rdi]
0x18002bb2a  mov     rax, [rcx]
0x18002bb2d  lea     r8, [rbp+arg_18]
0x18002bb31  mov     rdx, r15
0x18002bb34  mov     rax, [rax+208h]
0x18002bb3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb40  mov     [rbp+var_50], eax
0x18002bb43  test    eax, eax
0x18002bb45  js      loc_18002BBCC
0x18002bb4b  test    r14, r14
0x18002bb4e  jz      loc_18002BBDF
0x18002bb54  lea     rcx, aSelectionnames; "SelectionNamespaces"
0x18002bb5b  call    cs:__imp_SysAllocString
0x18002bb62  nop     dword ptr [rax+rax+00h]
0x18002bb67  mov     rsi, rax
0x18002bb6a  mov     eax, 8
0x18002bb6f  mov     word ptr [rbp+pvarg], ax
0x18002bb73  mov     rcx, r14; psz
0x18002bb76  call    cs:__imp_SysAllocString
0x18002bb7d  nop     dword ptr [rax+rax+00h]
0x18002bb82  mov     qword ptr [rbp+pvarg+8], rax
0x18002bb86  test    rsi, rsi
0x18002bb89  jz      short loc_18002BBC4
0x18002bb8b  test    rax, rax
0x18002bb8e  jz      short loc_18002BBC4
0x18002bb90  mov     rcx, [rdi]
0x18002bb93  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18002bb97  movaps  [rbp+var_20], xmm0
0x18002bb9b  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18002bba0  movsd   [rbp+var_10], xmm1
0x18002bba5  mov     rax, [rcx]
0x18002bba8  lea     r8, [rbp+var_20]
0x18002bbac  mov     rdx, rsi
0x18002bbaf  mov     rax, [rax+280h]
0x18002bbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbbb  mov     [rbp+var_50], eax
0x18002bbbe  test    eax, eax
0x18002bbc0  jns     short loc_18002BBDF
0x18002bbc2  jmp     short loc_18002BBCC
0x18002bbc4  mov     ebx, 8007000Eh
0x18002bbc9  mov     [rbp+var_50], ebx
0x18002bbcc  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18002bbd1  mov     r8, r12; char *
0x18002bbd4  mov     edx, [rbp+var_50]; int
0x18002bbd7  mov     rcx, rax; this
0x18002bbda  call    ?LogEnrollServerMessageParsingError@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollServerMessageParsingError(long,char const *)
0x18002bbdf  mov     rcx, r15; bstrString
0x18002bbe2  call    cs:__imp_SysFreeString
0x18002bbe9  nop     dword ptr [rax+rax+00h]
0x18002bbee  mov     rcx, rsi; bstrString
0x18002bbf1  call    cs:__imp_SysFreeString
0x18002bbf8  nop     dword ptr [rax+rax+00h]
0x18002bbfd  lea     rcx, [rbp+pvarg]; pvarg
0x18002bc01  call    cs:__imp_VariantClear
0x18002bc08  nop     dword ptr [rax+rax+00h]
0x18002bc0d  mov     ebx, [rbp+var_50]
0x18002bc10  lea     rcx, [rbp+var_48]; this
0x18002bc14  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002bc19  nop
0x18002bc1a  lea     rcx, [rbp+pvarg]; pvarg
0x18002bc1e  call    cs:__imp_VariantClear
0x18002bc25  nop     dword ptr [rax+rax+00h]
0x18002bc2a  mov     eax, ebx
0x18002bc2c  lea     r11, [rsp+80h+var_s0]
0x18002bc34  mov     rbx, [r11+30h]
0x18002bc38  mov     rsi, [r11+38h]
0x18002bc3c  mov     rsp, r11
0x18002bc3f  pop     r15
0x18002bc41  pop     r14
0x18002bc43  pop     r12
0x18002bc45  pop     rdi
0x18002bc46  pop     rbp
0x18002bc47  retn
```
