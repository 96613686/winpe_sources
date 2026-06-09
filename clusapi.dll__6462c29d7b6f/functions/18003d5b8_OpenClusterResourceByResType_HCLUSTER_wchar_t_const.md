# OpenClusterResourceByResType(_HCLUSTER *,wchar_t const *)

- ea: `0x18003d5b8`
- end: `0x18003d766`
- name: `?OpenClusterResourceByResType@@YAPEAU_HRESOURCE@@PEAU_HCLUSTER@@PEB_W@Z`
- size: `430`
- prototype: `struct _HRESOURCE *__fastcall(struct _HCLUSTER *, const wchar_t *)`
- caller_count: `10`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18003abe0`
- `0x18003bfc4`
- `0x1800451b0`
- `0x18008cf4c`
- `0x18008d258`
- `0x18008dab8`
- `0x18008ddfc`
- `0x18008e110`
- `0x18008e50c`
- `0x18008ea7c`

## callees

- `0x18001a9cc`
- `0x18001cf80`
- `0x18001fe7c`
- `0x1800294f0`
- `0x18003d5b8`
- `0x18006b64c`
- `0x18006b834`
- `0x18006c3e0`
- `0x18006c4e0`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d5eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d6f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d5eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d6f1`

## string_xrefs

- `0x18003d5f5`: `ClusterResourceTypeOpenEnum failed , status = %d`
- `0x18003d607`: `OpenClusterResourceByResType`
- `0x18003d6a7`: `OpenClusterResourceByResType`
- `0x18003d716`: `OpenClusterResourceByResType`
- `0x18003d695`: `Resource was not found during enumeration resources in %ws, status = %d`
- `0x18003d704`: `Can't open resource resName = %ws, status = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct _HRESOURCE *__fastcall OpenClusterResourceByResType(struct _HCLUSTER *a1, const wchar_t *a2)
{
  HRESTYPEENUM v4; // rbx
  DWORD v6; // eax
  struct _HRESOURCE *v7; // rsi
  DWORD LastError; // [rsp+28h] [rbp-48h]
  DWORD v9; // [rsp+30h] [rbp-40h]
  DWORD dwType; // [rsp+40h] [rbp-30h] BYREF
  HRESTYPEENUM v11; // [rsp+48h] [rbp-28h]
  LPWSTR lpszName[4]; // [rsp+50h] [rbp-20h] BYREF
  struct _HRESOURCE *v13; // [rsp+A0h] [rbp+30h] BYREF
  DWORD cchName; // [rsp+A8h] [rbp+38h] BYREF

  v4 = ClusterResourceTypeOpenEnum(a1, a2, 2u);
  v11 = v4;
  if ( (((unsigned __int64)v4 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    TraceMsg(
      2,
      0,
      L"OpenClusterResourceByResType",
      10925,
      L"ClusterResourceTypeOpenEnum failed , status = %d",
      LastError);
    if ( (unsigned __int64)v4 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      return 0;
LABEL_3:
    ClusterResourceTypeCloseEnumCommon(v4, 1);
    return 0;
  }
  cchName = 64;
  std::vector<wchar_t>::vector<wchar_t>(lpszName, 64, &v13);
  while ( 1 )
  {
    v6 = ClusterResourceTypeEnum(v4, 0, &dwType, lpszName[0], &cchName);
    if ( v6 != 234 )
      break;
    std::vector<wchar_t>::_Resize<std::_Value_init_tag>(lpszName, ++cchName, &v13);
  }
  if ( v6 )
  {
    TraceMsg(
      2,
      0,
      L"OpenClusterResourceByResType",
      10951,
      L"Resource was not found during enumeration resources in %ws, status = %d",
      a2,
      v6);
    std::vector<wchar_t>::_Tidy(lpszName);
    goto LABEL_3;
  }
  v7 = OpenClusterResourceImpl(a1, lpszName[0], 0x10000000u, 0, 1);
  v13 = v7;
  if ( v7 )
  {
    v13 = 0;
  }
  else
  {
    v9 = GetLastError();
    TraceMsg(
      2,
      0,
      L"OpenClusterResourceByResType",
      10958,
      L"Can't open resource resName = %ws, status = %d",
      lpszName[0],
      v9);
  }
  cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>::Close(&v13);
  std::vector<wchar_t>::_Tidy(lpszName);
  ClusterResourceTypeCloseEnumCommon(v4, 1);
  return v7;
}

```

## disassembly

```asm
0x18003d5b8  mov     [rsp-18h+arg_0], rbx
0x18003d5bd  push    rbp
0x18003d5be  push    rsi
0x18003d5bf  push    r14
0x18003d5c1  mov     rbp, rsp
0x18003d5c4  sub     rsp, 70h
0x18003d5c8  mov     r14, rdx
0x18003d5cb  mov     rsi, rcx
0x18003d5ce  mov     r8d, 2; dwType
0x18003d5d4  call    ClusterResourceTypeOpenEnum
0x18003d5d9  mov     rbx, rax
0x18003d5dc  mov     [rbp+var_28], rax
0x18003d5e0  inc     rax
0x18003d5e3  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003d5e9  jnz     short loc_18003D637
0x18003d5eb  call    cs:__imp_GetLastError
0x18003d5f1  mov     dword ptr [rsp+70h+var_48], eax
0x18003d5f5  lea     rax, aClusterresourc_19; "ClusterResourceTypeOpenEnum failed , st"...
0x18003d5fc  mov     [rsp+70h+lpcchName], rax
0x18003d601  mov     r9d, 2AADh
0x18003d607  lea     r8, aOpenclusterres_3; "OpenClusterResourceByResType"
0x18003d60e  xor     edx, edx
0x18003d610  lea     ecx, [rdx+2]
0x18003d613  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003d618  nop
0x18003d619  lea     rax, [rbx-1]
0x18003d61d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003d621  ja      short loc_18003D630
0x18003d623  mov     edx, 1; int
0x18003d628  mov     rcx, rbx; hMem
0x18003d62b  call    ?ClusterResourceTypeCloseEnumCommon@@YAKPEAU_HRESTYPEENUM@@H@Z; ClusterResourceTypeCloseEnumCommon(_HRESTYPEENUM *,int)
0x18003d630  xor     eax, eax
0x18003d632  jmp     loc_18003D755
0x18003d637  mov     edx, 40h ; '@'
0x18003d63c  mov     [rbp+cchName], edx
0x18003d63f  lea     r8, [rbp+arg_10]
0x18003d643  lea     rcx, [rbp+lpszName]
0x18003d647  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x18003d64c  nop
0x18003d64d  jmp     short loc_18003D666
0x18003d64f  mov     eax, [rbp+cchName]
0x18003d652  inc     eax
0x18003d654  mov     [rbp+cchName], eax
0x18003d657  mov     edx, eax
0x18003d659  lea     r8, [rbp+arg_10]
0x18003d65d  lea     rcx, [rbp+lpszName]
0x18003d661  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18003d666  lea     rax, [rbp+cchName]
0x18003d66a  mov     [rsp+70h+lpcchName], rax; lpcchName
0x18003d66f  mov     r9, [rbp+lpszName]; lpszName
0x18003d673  lea     r8, [rbp+dwType]; lpdwType
0x18003d677  xor     edx, edx; dwIndex
0x18003d679  mov     rcx, rbx; hResTypeEnum
0x18003d67c  call    ClusterResourceTypeEnum
0x18003d681  cmp     eax, 0EAh
0x18003d686  jz      short loc_18003D64F
0x18003d688  test    eax, eax
0x18003d68a  jz      short loc_18003D6C8
0x18003d68c  mov     [rsp+70h+var_40], eax
0x18003d690  mov     [rsp+70h+var_48], r14
0x18003d695  lea     rax, aResourceWasNot; "Resource was not found during enumerati"...
0x18003d69c  mov     [rsp+70h+lpcchName], rax
0x18003d6a1  mov     r9d, 2AC7h
0x18003d6a7  lea     r8, aOpenclusterres_3; "OpenClusterResourceByResType"
0x18003d6ae  xor     edx, edx
0x18003d6b0  lea     ecx, [rdx+2]
0x18003d6b3  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003d6b8  nop
0x18003d6b9  lea     rcx, [rbp+lpszName]
0x18003d6bd  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x18003d6c2  nop
0x18003d6c3  jmp     loc_18003D623
0x18003d6c8  mov     dword ptr [rsp+70h+lpcchName], 1; int
0x18003d6d0  xor     r9d, r9d; unsigned int *
0x18003d6d3  mov     r8d, 10000000h; unsigned int
0x18003d6d9  mov     rdx, [rbp+lpszName]; wchar_t *
0x18003d6dd  mov     rcx, rsi; struct _HCLUSTER *
0x18003d6e0  call    ?OpenClusterResourceImpl@@YAPEAU_HRESOURCE@@PEAU_HCLUSTER@@PEB_WKPEAKH@Z; OpenClusterResourceImpl(_HCLUSTER *,wchar_t const *,ulong,ulong *,int)
0x18003d6e5  mov     rsi, rax
0x18003d6e8  mov     [rbp+arg_10], rax
0x18003d6ec  test    rax, rax
0x18003d6ef  jnz     short loc_18003D729
0x18003d6f1  call    cs:__imp_GetLastError
0x18003d6f7  mov     [rsp+70h+var_40], eax
0x18003d6fb  mov     rax, [rbp+lpszName]
0x18003d6ff  mov     [rsp+70h+var_48], rax
0x18003d704  lea     rax, aCanTOpenResour; "Can't open resource resName = %ws, stat"...
0x18003d70b  mov     [rsp+70h+lpcchName], rax
0x18003d710  mov     r9d, 2ACEh
0x18003d716  lea     r8, aOpenclusterres_3; "OpenClusterResourceByResType"
0x18003d71d  xor     edx, edx
0x18003d71f  lea     ecx, [rsi+2]
0x18003d722  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003d727  jmp     short loc_18003D731
0x18003d729  mov     [rbp+arg_10], 0
0x18003d731  lea     rcx, [rbp+arg_10]
0x18003d735  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x18003d73a  nop
0x18003d73b  lea     rcx, [rbp+lpszName]
0x18003d73f  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x18003d744  nop
0x18003d745  mov     edx, 1; int
0x18003d74a  mov     rcx, rbx; hMem
0x18003d74d  call    ?ClusterResourceTypeCloseEnumCommon@@YAKPEAU_HRESTYPEENUM@@H@Z; ClusterResourceTypeCloseEnumCommon(_HRESTYPEENUM *,int)
0x18003d752  mov     rax, rsi
0x18003d755  mov     rbx, [rsp+70h+arg_0]
0x18003d75d  add     rsp, 70h
0x18003d761  pop     r14
0x18003d763  pop     rsi
0x18003d764  pop     rbp
0x18003d765  retn
```
