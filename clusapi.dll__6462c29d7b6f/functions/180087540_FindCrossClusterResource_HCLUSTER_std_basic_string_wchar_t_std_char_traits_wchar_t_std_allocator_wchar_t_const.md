# FindCrossClusterResource(_HCLUSTER *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,_HRESOURCE * *,_HGROUP * *,_HGROUPSET * *)

- ea: `0x180087540`
- end: `0x1800877cc`
- name: `?FindCrossClusterResource@@YAKPEAU_HCLUSTER@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1PEAPEAU_HRESOURCE@@PEAPEAU_HGROUP@@PEAPEAU_HGROUPSET@@@Z`
- size: `652`
- prototype: `__int64 __usercall@<rax>(struct _HCLUSTER *@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1800877d4`

## callees

- `0x180002f50`
- `0x18001cc2c`
- `0x180028f30`
- `0x180029578`
- `0x1800298cc`
- `0x18004b424`
- `0x18004b900`
- `0x18006b834`
- `0x18006c5e0`
- `0x18006f910`
- `0x1800868e0`
- `0x180086e60`
- `0x180087120`
- `0x180087540`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800876b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008773c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800876b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008773c`

## string_xrefs

- `0x18008761f`: `Found CCO resource %ws but failed to open group`
- `0x180087678`: `Found CCO resource %ws but failed to open group set`
- `0x1800876bc`: `Failed to create CCO resource with error %d`
- `0x180087711`: `Failed to create CCO group with error %d`
- `0x180087748`: `Failed to create CCO group set with error %d`
- `0x180087774`: `Created new CCO resource '%ws'`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FindCrossClusterResource(
        struct _HCLUSTER *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        struct _HGROUP **a5,
        __int64 *a6)
{
  const wchar_t *v10; // rax
  struct _HRESOURCE *v11; // rbx
  const wchar_t *v12; // rdx
  struct _HGROUP *v13; // rax
  DWORD LastError; // ebx
  __int64 v15; // rax
  __int64 v16; // rax
  struct _HGROUP *ClusterGroup; // rbx
  wchar_t *v18; // rax
  int v19; // r9d
  unsigned __int8 v20; // cl
  __int64 v21; // rax
  __int64 ClusterResource; // rax
  const wchar_t *v23; // rax
  _DWORD *ClusterGroupSet; // rax
  __int64 v26; // [rsp+28h] [rbp-58h]
  __int64 v27; // [rsp+28h] [rbp-58h]
  __int64 v28; // [rsp+28h] [rbp-58h]
  DWORD v29[2]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v30[32]; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v31[32]; // [rsp+58h] [rbp-28h] BYREF

  std::wstring::wstring(v31, L"CCO Group for ");
  std::wstring::append(v31, a3);
  std::wstring::wstring(v30, L"CCO GroupSet for ");
  std::wstring::append(v30, a3);
  v10 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  v11 = OpenClusterResourceImpl(a1, v10, 0x10000000u, 0, 1);
  *a4 = v11;
  v12 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v31);
  if ( !v11 )
  {
    v29[0] = 1;
    v29[1] = 121;
    ClusterGroup = (struct _HGROUP *)CreateClusterGroupEx((__int64)a1, v12, v29);
    *a5 = ClusterGroup;
    if ( ClusterGroup )
    {
      v21 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
      ClusterResource = CreateClusterResourceEx(
                          ClusterGroup,
                          v21,
                          L"Cross Cluster Dependency Orchestrator",
                          0,
                          L"clusapi!FindCrossClusterResource");
      *a4 = ClusterResource;
      if ( ClusterResource )
      {
        v23 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v30);
        ClusterGroupSet = CreateClusterGroupSet((__int64)a1, v23);
        *a6 = (__int64)ClusterGroupSet;
        if ( ClusterGroupSet )
        {
          LastError = ClusterAddGroupToGroupSet(ClusterGroupSet, *a5);
          v26 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
          v18 = L"Created new CCO resource '%ws'";
          v19 = 129;
          v20 = 4;
          goto LABEL_16;
        }
        LastError = GetLastError();
        LODWORD(v26) = LastError;
        v18 = L"Failed to create CCO group set with error %d";
        v19 = 123;
      }
      else
      {
        LastError = GetLastError();
        LODWORD(v26) = LastError;
        v18 = L"Failed to create CCO group with error %d";
        v19 = 115;
      }
    }
    else
    {
      LastError = GetLastError();
      LODWORD(v26) = LastError;
      v18 = L"Failed to create CCO resource with error %d";
      v19 = 107;
    }
    v20 = 2;
LABEL_16:
    TraceMsg(v20, 0, (__int64)L"FindCrossClusterResource", v19, v18, v26);
    goto LABEL_17;
  }
  v13 = OpenClusterGroupImpl(a1, v12, 0x10000000u, 0, 1);
  *a5 = v13;
  if ( v13 )
  {
    v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v30);
    v16 = OpenClusterGroupSet(a1, v15);
    *a6 = v16;
    if ( v16 )
    {
      LastError = 0;
      goto LABEL_17;
    }
    v28 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
    TraceMsg(
      2u,
      0,
      (__int64)L"FindCrossClusterResource",
      92,
      L"Found CCO resource %ws but failed to open group set",
      v28);
  }
  else
  {
    v27 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
    TraceMsg(2u, 0, (__int64)L"FindCrossClusterResource", 84, L"Found CCO resource %ws but failed to open group", v27);
  }
  LastError = GetLastError();
LABEL_17:
  std::wstring::_Tidy_deallocate(v30);
  std::wstring::_Tidy_deallocate(v31);
  return LastError;
}

```

## disassembly

```asm
0x180087540  push    rbp
0x180087542  push    rbx
0x180087543  push    rsi
0x180087544  push    rdi
0x180087545  push    r12
0x180087547  push    r14
0x180087549  push    r15
0x18008754b  mov     rbp, rsp
0x18008754e  sub     rsp, 80h
0x180087555  mov     rax, cs:__security_cookie
0x18008755c  xor     rax, rsp
0x18008755f  mov     [rbp+var_8], rax
0x180087563  mov     r12, r9
0x180087566  mov     rbx, r8
0x180087569  mov     rsi, rdx
0x18008756c  mov     rdi, rcx
0x18008756f  mov     r14, [rbp+arg_20]
0x180087573  mov     r15, [rbp+arg_28]
0x180087577  lea     rdx, aCcoGroupFor; "CCO Group for "
0x18008757e  lea     rcx, [rbp+var_28]
0x180087582  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180087587  nop
0x180087588  mov     rdx, rbx
0x18008758b  lea     rcx, [rbp+var_28]
0x18008758f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180087594  lea     rdx, aCcoGroupsetFor; "CCO GroupSet for "
0x18008759b  lea     rcx, [rbp+var_48]
0x18008759f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800875a4  nop
0x1800875a5  mov     rdx, rbx
0x1800875a8  lea     rcx, [rbp+var_48]
0x1800875ac  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800875b1  mov     rcx, rsi
0x1800875b4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800875b9  mov     [rsp+80h+var_60], 1; int
0x1800875c1  xor     r9d, r9d; unsigned int *
0x1800875c4  mov     r8d, 10000000h; unsigned int
0x1800875ca  mov     rdx, rax; wchar_t *
0x1800875cd  mov     rcx, rdi; struct _HCLUSTER *
0x1800875d0  call    ?OpenClusterResourceImpl@@YAPEAU_HRESOURCE@@PEAU_HCLUSTER@@PEB_WKPEAKH@Z; OpenClusterResourceImpl(_HCLUSTER *,wchar_t const *,ulong,ulong *,int)
0x1800875d5  mov     rbx, rax
0x1800875d8  mov     [r12], rax
0x1800875dc  lea     rcx, [rbp+var_28]
0x1800875e0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800875e5  mov     rdx, rax; wchar_t *
0x1800875e8  mov     rcx, rdi; struct _HCLUSTER *
0x1800875eb  test    rbx, rbx
0x1800875ee  jz      loc_18008768E
0x1800875f4  mov     [rsp+80h+var_60], 1; int
0x1800875fc  xor     r9d, r9d; unsigned int *
0x1800875ff  mov     r8d, 10000000h; unsigned int
0x180087605  call    ?OpenClusterGroupImpl@@YAPEAU_HGROUP@@PEAU_HCLUSTER@@PEB_WKPEAKH@Z; OpenClusterGroupImpl(_HCLUSTER *,wchar_t const *,ulong,ulong *,int)
0x18008760a  mov     [r14], rax
0x18008760d  test    rax, rax
0x180087610  jnz     short loc_18008764F
0x180087612  mov     rcx, rsi
0x180087615  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18008761a  mov     [rsp+80h+var_58], rax
0x18008761f  lea     rax, aFoundCcoResour; "Found CCO resource %ws but failed to op"...
0x180087626  mov     r9d, 54h ; 'T'
0x18008762c  mov     qword ptr [rsp+80h+var_60], rax
0x180087631  lea     r8, aFindcrossclust; "FindCrossClusterResource"
0x180087638  xor     edx, edx
0x18008763a  lea     ecx, [rdx+2]
0x18008763d  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180087642  call    cs:__imp_GetLastError
0x180087648  mov     ebx, eax
0x18008764a  jmp     loc_180087799
0x18008764f  lea     rcx, [rbp+var_48]
0x180087653  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180087658  mov     rdx, rax
0x18008765b  mov     rcx, rdi
0x18008765e  call    OpenClusterGroupSet
0x180087663  mov     [r15], rax
0x180087666  test    rax, rax
0x180087669  jnz     short loc_180087687
0x18008766b  mov     rcx, rsi
0x18008766e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180087673  mov     [rsp+80h+var_58], rax
0x180087678  lea     rax, aFoundCcoResour_0; "Found CCO resource %ws but failed to op"...
0x18008767f  mov     r9d, 5Ch ; '\'
0x180087685  jmp     short loc_18008762C
0x180087687  xor     ebx, ebx
0x180087689  jmp     loc_180087799
0x18008768e  mov     [rbp+var_50], 1
0x180087695  mov     [rbp+var_4C], 79h ; 'y'
0x18008769c  lea     r8, [rbp+var_50]
0x1800876a0  call    CreateClusterGroupEx
0x1800876a5  mov     rbx, rax
0x1800876a8  mov     [r14], rax
0x1800876ab  test    rax, rax
0x1800876ae  jnz     short loc_1800876D3
0x1800876b0  call    cs:__imp_GetLastError
0x1800876b6  mov     ebx, eax
0x1800876b8  mov     dword ptr [rsp+80h+var_58], eax
0x1800876bc  lea     rax, aFailedToCreate_23; "Failed to create CCO resource with erro"...
0x1800876c3  mov     r9d, 6Bh ; 'k'
0x1800876c9  mov     ecx, 2
0x1800876ce  jmp     loc_180087785
0x1800876d3  mov     rcx, rsi
0x1800876d6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800876db  lea     rcx, aClusapiFindcro; "clusapi!FindCrossClusterResource"
0x1800876e2  mov     qword ptr [rsp+80h+var_60], rcx
0x1800876e7  xor     r9d, r9d
0x1800876ea  lea     r8, aCrossClusterDe; "Cross Cluster Dependency Orchestrator"
0x1800876f1  mov     rdx, rax
0x1800876f4  mov     rcx, rbx
0x1800876f7  call    CreateClusterResourceEx
0x1800876fc  mov     [r12], rax
0x180087700  test    rax, rax
0x180087703  jnz     short loc_180087720
0x180087705  call    cs:__imp_GetLastError
0x18008770b  mov     ebx, eax
0x18008770d  mov     dword ptr [rsp+80h+var_58], eax
0x180087711  lea     rax, aFailedToCreate_10; "Failed to create CCO group with error %"...
0x180087718  mov     r9d, 73h ; 's'
0x18008771e  jmp     short loc_1800876C9
0x180087720  lea     rcx, [rbp+var_48]
0x180087724  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180087729  mov     rdx, rax
0x18008772c  mov     rcx, rdi
0x18008772f  call    CreateClusterGroupSet
0x180087734  mov     [r15], rax
0x180087737  test    rax, rax
0x18008773a  jnz     short loc_18008775A
0x18008773c  call    cs:__imp_GetLastError
0x180087742  mov     ebx, eax
0x180087744  mov     dword ptr [rsp+80h+var_58], eax
0x180087748  lea     rax, aFailedToCreate_5; "Failed to create CCO group set with err"...
0x18008774f  mov     r9d, 7Bh ; '{'
0x180087755  jmp     loc_1800876C9
0x18008775a  mov     rdx, [r14]
0x18008775d  mov     rcx, rax
0x180087760  call    ClusterAddGroupToGroupSet
0x180087765  mov     ebx, eax
0x180087767  mov     rcx, rsi
0x18008776a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18008776f  mov     [rsp+80h+var_58], rax
0x180087774  lea     rax, aCreatedNewCcoR; "Created new CCO resource '%ws'"
0x18008777b  mov     r9d, 81h
0x180087781  lea     ecx, [r9-7Dh]
0x180087785  mov     qword ptr [rsp+80h+var_60], rax
0x18008778a  lea     r8, aFindcrossclust; "FindCrossClusterResource"
0x180087791  xor     edx, edx
0x180087793  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180087798  nop
0x180087799  lea     rcx, [rbp+var_48]
0x18008779d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800877a2  nop
0x1800877a3  lea     rcx, [rbp+var_28]
0x1800877a7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800877ac  mov     eax, ebx
0x1800877ae  mov     rcx, [rbp+var_8]
0x1800877b2  xor     rcx, rsp; StackCookie
0x1800877b5  call    __security_check_cookie
0x1800877ba  add     rsp, 80h
0x1800877c1  pop     r15
0x1800877c3  pop     r14
0x1800877c5  pop     r12
0x1800877c7  pop     rdi
0x1800877c8  pop     rsi
0x1800877c9  pop     rbx
0x1800877ca  pop     rbp
0x1800877cb  retn
```
