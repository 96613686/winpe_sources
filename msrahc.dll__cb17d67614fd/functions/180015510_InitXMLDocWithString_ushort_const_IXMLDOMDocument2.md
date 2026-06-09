# InitXMLDocWithString(ushort * const,IXMLDOMDocument2 * *)

- ea: `0x180015510`
- end: `0x180015776`
- name: `?InitXMLDocWithString@@YAJQEAGPEAPEAUIXMLDOMDocument2@@@Z`
- size: `614`
- prototype: `__int64 __fastcall(unsigned __int16 *const, struct IXMLDOMDocument2 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001577c`
- `0x180015f1c`

## callees

- `0x180008924`
- `0x180014660`
- `0x180015510`
- `0x18001c010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800155d6`
- `OLEAUT32!__imp_VariantClear` at `0x18001562a`
- `OLEAUT32!__imp_VariantClear` at `0x180015683`
- `OLEAUT32!__imp_VariantClear` at `0x1800155d6`
- `OLEAUT32!__imp_VariantClear` at `0x18001562a`
- `OLEAUT32!__imp_VariantClear` at `0x180015683`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001555d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001555d`

## string_xrefs

- `0x180015571`: `InitXMLDocWithString`
- `0x18001557d`: `base\diagnosis\ra\racommon\src\xmlutils.cpp`

## pseudocode

```c
__int64 __fastcall InitXMLDocWithString(unsigned __int16 *const a1, struct IXMLDOMDocument2 **a2)
{
  HRESULT v4; // eax
  const struct _EVENT_DESCRIPTOR *v5; // rdx
  CEventLogger *v6; // rcx
  signed int v7; // ebx
  __int64 v8; // rax
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CEventLogger *v10; // rcx
  __int64 v11; // rax
  const struct _EVENT_DESCRIPTOR *v12; // rdx
  CEventLogger *v13; // rcx
  __int64 v14; // rax
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  CEventLogger *v16; // rcx
  struct IXMLDOMDocument2 *v17; // rax
  LPVOID ppv; // [rsp+30h] [rbp-50h] BYREF
  __int64 v20; // [rsp+38h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-40h] BYREF
  VARIANTARG v22; // [rsp+60h] [rbp-20h] BYREF
  __int16 v23; // [rsp+C0h] [rbp+40h] BYREF
  int v24; // [rsp+C8h] [rbp+48h] BYREF

  v23 = 0;
  v20 = 0;
  ppv = 0;
  v24 = 0;
  v4 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, &ppv);
  v7 = v4;
  if ( v4 < 0 )
  {
    CEventLogger::LogError(
      v6,
      v5,
      L"base\\diagnosis\\ra\\racommon\\src\\xmlutils.cpp",
      0x3Eu,
      L"InitXMLDocWithString",
      v4);
    goto LABEL_19;
  }
  v8 = *(_QWORD *)ppv;
  pvarg.vt = 11;
  pvarg.iVal = -1;
  v22 = pvarg;
  v7 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v8 + 640))(ppv, L"ProhibitDTD", &v22);
  VariantClear(&pvarg);
  if ( v7 < 0 )
  {
    CEventLogger::LogError(
      v10,
      v9,
      L"base\\diagnosis\\ra\\racommon\\src\\xmlutils.cpp",
      0x40u,
      L"InitXMLDocWithString",
      v7);
    goto LABEL_19;
  }
  v11 = *(_QWORD *)ppv;
  pvarg.vt = 11;
  pvarg.iVal = 0;
  v22 = pvarg;
  v7 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v11 + 640))(ppv, L"AllowXsltScript", &v22);
  VariantClear(&pvarg);
  if ( v7 < 0 )
  {
    CEventLogger::LogError(
      v13,
      v12,
      L"base\\diagnosis\\ra\\racommon\\src\\xmlutils.cpp",
      0x41u,
      L"InitXMLDocWithString",
      v7);
    goto LABEL_19;
  }
  v14 = *(_QWORD *)ppv;
  pvarg.vt = 11;
  pvarg.iVal = 0;
  v22 = pvarg;
  v7 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v14 + 640))(
         ppv,
         L"AllowDocumentFunction",
         &v22);
  VariantClear(&pvarg);
  if ( v7 < 0 )
  {
    CEventLogger::LogError(
      v16,
      v15,
      L"base\\diagnosis\\ra\\racommon\\src\\xmlutils.cpp",
      0x42u,
      L"InitXMLDocWithString",
      v7);
    goto LABEL_19;
  }
  v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 560LL))(ppv, 0);
    if ( v7 >= 0 )
    {
      if ( (*(int (__fastcall **)(LPVOID, unsigned __int16 *const, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, a1, &v23) < 0
        || !v23 )
      {
        goto LABEL_18;
      }
      v7 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 480LL))(ppv, &v20);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 56LL))(v20, &v24);
        if ( v7 >= 0 )
        {
          if ( !v24 )
          {
            v17 = (struct IXMLDOMDocument2 *)ppv;
            ppv = 0;
            *a2 = v17;
            goto LABEL_19;
          }
LABEL_18:
          v7 = -2147467259;
        }
      }
    }
  }
LABEL_19:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180015510  mov     [rsp-28h+arg_0], rbx
0x180015515  push    rbp
0x180015516  push    rsi
0x180015517  push    rdi
0x180015518  push    r14
0x18001551a  push    r15
0x18001551c  mov     rbp, rsp
0x18001551f  sub     rsp, 80h
0x180015526  mov     rdi, rdx
0x180015529  mov     rsi, rcx
0x18001552c  xor     r14d, r14d
0x18001552f  mov     [rbp+arg_10], r14w
0x180015534  mov     [rbp+var_48], r14
0x180015538  mov     [rbp+var_50], r14
0x18001553c  mov     [rbp+arg_18], r14d
0x180015540  lea     rax, [rbp+var_50]
0x180015544  mov     [rsp+80h+ppv], rax; ppv
0x180015549  lea     r9, IID_IXMLDOMDocument; riid
0x180015550  xor     edx, edx; pUnkOuter
0x180015552  lea     r8d, [r14+1]; dwClsContext
0x180015556  lea     rcx, CLSID_DOMDocument60; rclsid
0x18001555d  call    cs:__imp_CoCreateInstance
0x180015563  mov     ebx, eax
0x180015565  test    eax, eax
0x180015567  jns     short loc_18001558E
0x180015569  mov     [rsp+80h+var_58], eax; unsigned int
0x18001556d  lea     r9d, [r14+3Eh]; unsigned int
0x180015571  lea     rax, aInitxmldocwith; "InitXMLDocWithString"
0x180015578  mov     [rsp+80h+ppv], rax; unsigned __int16 *
0x18001557d  lea     r8, aBaseDiagnosisR_6; "base\\diagnosis\\ra\\racommon\\src\\xml"...
0x180015584  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180015589  jmp     loc_18001574A
0x18001558e  mov     rcx, [rbp+var_50]
0x180015592  mov     rax, [rcx]
0x180015595  mov     r15d, 0Bh
0x18001559b  mov     word ptr [rbp+pvarg], r15w
0x1800155a0  or      edx, 0FFFFFFFFh
0x1800155a3  mov     word ptr [rbp+pvarg+8], dx
0x1800155a7  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800155ab  movaps  [rbp+var_20], xmm0
0x1800155af  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800155b4  movsd   [rbp+var_10], xmm1
0x1800155b9  lea     r8, [rbp+var_20]
0x1800155bd  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x1800155c4  mov     rax, [rax+280h]
0x1800155cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155d0  mov     ebx, eax
0x1800155d2  lea     rcx, [rbp+pvarg]; pvarg
0x1800155d6  call    cs:__imp_VariantClear
0x1800155dc  test    ebx, ebx
0x1800155de  jns     short loc_1800155EA
0x1800155e0  mov     [rsp+80h+var_58], ebx
0x1800155e4  lea     r9d, [r15+35h]
0x1800155e8  jmp     short loc_180015571
0x1800155ea  mov     rcx, [rbp+var_50]
0x1800155ee  mov     rax, [rcx]
0x1800155f1  mov     word ptr [rbp+pvarg], r15w
0x1800155f6  mov     word ptr [rbp+pvarg+8], r14w
0x1800155fb  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800155ff  movaps  [rbp+var_20], xmm0
0x180015603  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180015608  movsd   [rbp+var_10], xmm1
0x18001560d  lea     r8, [rbp+var_20]
0x180015611  lea     rdx, aAllowxsltscrip; "AllowXsltScript"
0x180015618  mov     rax, [rax+280h]
0x18001561f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015624  mov     ebx, eax
0x180015626  lea     rcx, [rbp+pvarg]; pvarg
0x18001562a  call    cs:__imp_VariantClear
0x180015630  test    ebx, ebx
0x180015632  jns     short loc_180015643
0x180015634  mov     [rsp+80h+var_58], ebx
0x180015638  mov     r9d, 41h ; 'A'
0x18001563e  jmp     loc_180015571
0x180015643  mov     rcx, [rbp+var_50]
0x180015647  mov     rax, [rcx]
0x18001564a  mov     word ptr [rbp+pvarg], r15w
0x18001564f  mov     word ptr [rbp+pvarg+8], r14w
0x180015654  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180015658  movaps  [rbp+var_20], xmm0
0x18001565c  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180015661  movsd   [rbp+var_10], xmm1
0x180015666  lea     r8, [rbp+var_20]
0x18001566a  lea     rdx, aAllowdocumentf; "AllowDocumentFunction"
0x180015671  mov     rax, [rax+280h]
0x180015678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001567d  mov     ebx, eax
0x18001567f  lea     rcx, [rbp+pvarg]; pvarg
0x180015683  call    cs:__imp_VariantClear
0x180015689  test    ebx, ebx
0x18001568b  jns     short loc_18001569C
0x18001568d  mov     [rsp+80h+var_58], ebx
0x180015691  mov     r9d, 42h ; 'B'
0x180015697  jmp     loc_180015571
0x18001569c  mov     rcx, [rbp+var_50]
0x1800156a0  mov     rax, [rcx]
0x1800156a3  xor     edx, edx
0x1800156a5  mov     rax, [rax+1F8h]
0x1800156ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156b1  mov     ebx, eax
0x1800156b3  test    eax, eax
0x1800156b5  js      loc_18001574A
0x1800156bb  mov     rcx, [rbp+var_50]
0x1800156bf  mov     rax, [rcx]
0x1800156c2  xor     edx, edx
0x1800156c4  mov     rax, [rax+230h]
0x1800156cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156d0  mov     ebx, eax
0x1800156d2  test    eax, eax
0x1800156d4  js      short loc_18001574A
0x1800156d6  mov     rcx, [rbp+var_50]
0x1800156da  mov     rax, [rcx]
0x1800156dd  lea     r8, [rbp+arg_10]
0x1800156e1  mov     rdx, rsi
0x1800156e4  mov     rax, [rax+208h]
0x1800156eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156f0  test    eax, eax
0x1800156f2  js      short loc_180015745
0x1800156f4  cmp     [rbp+arg_10], r14w
0x1800156f9  jz      short loc_180015745
0x1800156fb  mov     rcx, [rbp+var_50]
0x1800156ff  mov     rax, [rcx]
0x180015702  lea     rdx, [rbp+var_48]
0x180015706  mov     rax, [rax+1E0h]
0x18001570d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015712  mov     ebx, eax
0x180015714  test    eax, eax
0x180015716  js      short loc_18001574A
0x180015718  mov     rcx, [rbp+var_48]
0x18001571c  mov     rax, [rcx]
0x18001571f  lea     rdx, [rbp+arg_18]
0x180015723  mov     rax, [rax+38h]
0x180015727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001572c  mov     ebx, eax
0x18001572e  test    eax, eax
0x180015730  js      short loc_18001574A
0x180015732  cmp     [rbp+arg_18], r14d
0x180015736  jnz     short loc_180015745
0x180015738  mov     rax, [rbp+var_50]
0x18001573c  mov     [rbp+var_50], r14
0x180015740  mov     [rdi], rax
0x180015743  jmp     short loc_18001574A
0x180015745  mov     ebx, 80004005h
0x18001574a  lea     rcx, [rbp+var_50]
0x18001574e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180015753  nop
0x180015754  lea     rcx, [rbp+var_48]
0x180015758  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001575d  mov     eax, ebx
0x18001575f  mov     rbx, [rsp+80h+arg_0]
0x180015767  add     rsp, 80h
0x18001576e  pop     r15
0x180015770  pop     r14
0x180015772  pop     rdi
0x180015773  pop     rsi
0x180015774  pop     rbp
0x180015775  retn
```
