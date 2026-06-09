# _lambda_3471a46f8bb692a3571eca95c36b00cf_::operator()

- ea: `0x1800032fc`
- end: `0x18000342e`
- name: `_lambda_3471a46f8bb692a3571eca95c36b00cf_::operator()`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003198`

## callees

- `0x1800032fc`
- `0x180003524`
- `0x180004148`
- `0x180004544`
- `0x1800045b0`
- `0x180025dd4`
- `0x1800698e0`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800033ac`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800033ac`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x18000330b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x18000330b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000341d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000341d`

## string_xrefs

- `0x180003337`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`
- `0x1800033fb`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`

## pseudocode

```c
__int64 __fastcall lambda_3471a46f8bb692a3571eca95c36b00cf_::operator()(const unsigned __int16 **a1)
{
  int v2; // eax
  const unsigned __int16 *v3; // r8
  __int64 v4; // r9
  const unsigned __int16 *v5; // rbx
  int v6; // ebp
  __int64 v7; // rdx
  int v8; // eax
  unsigned int v9; // esi
  int *v11; // rdx
  HKEY *v12; // rcx
  const unsigned __int16 *v13; // rdx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // r9
  __int64 v17; // rdx
  WCHAR *v18; // rbx
  int v19; // [rsp+20h] [rbp-48h]
  int v20; // [rsp+20h] [rbp-48h]
  LPCWSTR pszStr2; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v22[48]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = StrToIntW(*a1);
  v5 = a1[1];
  v6 = v2;
  v7 = *((_QWORD *)v5 + 1);
  if ( v7 == *((_QWORD *)v5 + 3) )
  {
    v8 = CTSimpleArray<unsigned int,4294967294,CTPolicyCoTaskMem<unsigned int>,CSimpleArrayStandardCompareHelper<unsigned int>,CSimpleArrayStandardMergeHelper<unsigned int>>::_EnsureCapacity(
           a1[1],
           v7 + 1);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA8,
        (unsigned int)"onecoreuap\\shell\\propsys\\schemacachehelpers.cpp",
        (const char *)(unsigned int)v8,
        v19);
      return v9;
    }
  }
  v11 = (int *)(*(_QWORD *)v5 + 4 * (*((_QWORD *)v5 + 1))++);
  if ( v11 )
    *v11 = v6;
  v12 = (HKEY *)a1[2];
  v13 = *a1;
  pszStr2 = 0;
  v14 = SHRegAllocData(*v12, v13, v3, v4, (void **)&pszStr2);
  v15 = v14;
  if ( v14 < 0 )
  {
    v16 = (unsigned int)v14;
    v17 = 173;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\shell\\propsys\\schemacachehelpers.cpp",
      (const char *)v16,
      v20);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszStr2);
    return v15;
  }
  v18 = (WCHAR *)pszStr2;
  if ( !StrCmpICW(*(LPCWSTR *)a1[3], pszStr2) )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      v22,
      *a1,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      a1[4],
      v22);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v22);
    if ( !*(_QWORD *)a1[4] )
    {
      v15 = -2147024882;
      v17 = 180;
      v16 = 2147942414LL;
      goto LABEL_11;
    }
  }
  if ( v18 )
    CoTaskMemFree(v18);
  return 0;
}

```

## disassembly

```asm
0x1800032fc  push    rbx
0x1800032fe  push    rbp
0x1800032ff  push    rsi
0x180003300  push    rdi
0x180003301  sub     rsp, 48h
0x180003305  mov     rdi, rcx
0x180003308  mov     rcx, [rcx]; pszSrc
0x18000330b  call    cs:__imp_StrToIntW
0x180003311  mov     rbx, [rdi+8]
0x180003315  mov     ebp, eax
0x180003317  mov     rdx, [rbx+8]
0x18000331b  cmp     rdx, [rbx+18h]
0x18000331f  jnz     short loc_180003352
0x180003321  inc     rdx
0x180003324  mov     rcx, rbx
0x180003327  call    ?_EnsureCapacity@?$CTSimpleArray@I$0PPPPPPPO@V?$CTPolicyCoTaskMem@I@@V?$CSimpleArrayStandardCompareHelper@I@@V?$CSimpleArrayStandardMergeHelper@I@@@@QEAAJ_K0@Z; CTSimpleArray<uint,4294967294,CTPolicyCoTaskMem<uint>,CSimpleArrayStandardCompareHelper<uint>,CSimpleArrayStandardMergeHelper<uint>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18000332c  mov     esi, eax
0x18000332e  test    eax, eax
0x180003330  jns     short loc_180003352
0x180003332  mov     rcx, [rsp+68h]; this
0x180003337  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\propsys\\schemacache"...
0x18000333e  mov     r9d, eax; char *
0x180003341  mov     edx, 0A8h; void *
0x180003346  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000334b  mov     eax, esi
0x18000334d  jmp     loc_180003425
0x180003352  inc     qword ptr [rbx+8]
0x180003356  mov     rdx, [rbx+8]
0x18000335a  mov     rax, [rbx]
0x18000335d  dec     rdx
0x180003360  lea     rdx, [rax+rdx*4]
0x180003364  test    rdx, rdx
0x180003367  jz      short loc_18000336B
0x180003369  mov     [rdx], ebp
0x18000336b  mov     rcx, [rdi+10h]
0x18000336f  lea     rax, [rsp+68h+pszStr2]
0x180003374  mov     rdx, [rdi]; unsigned __int16 *
0x180003377  mov     [rsp+68h+pszStr2], 0
0x180003380  mov     qword ptr [rsp+68h+var_48], rax; int
0x180003385  mov     rcx, [rcx]; HKEY
0x180003388  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18000338d  mov     ebx, eax
0x18000338f  test    eax, eax
0x180003391  jns     short loc_18000339D
0x180003393  mov     r9d, eax
0x180003396  mov     edx, 0ADh
0x18000339b  jmp     short loc_1800033F6
0x18000339d  mov     rcx, [rdi+18h]
0x1800033a1  mov     rbx, [rsp+68h+pszStr2]
0x1800033a6  mov     rdx, rbx; pszStr2
0x1800033a9  mov     rcx, [rcx]; pszStr1
0x1800033ac  call    cs:__imp_StrCmpICW
0x1800033b2  test    eax, eax
0x1800033b4  jnz     short loc_180003415
0x1800033b6  mov     rdx, [rdi]
0x1800033b9  lea     rcx, [rsp+68h+var_30]
0x1800033be  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800033c2  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800033c7  mov     rcx, [rdi+20h]
0x1800033cb  lea     rdx, [rsp+68h+var_30]
0x1800033d0  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800033d5  lea     rcx, [rsp+68h+var_30]
0x1800033da  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800033df  mov     rax, [rdi+20h]
0x1800033e3  cmp     qword ptr [rax], 0
0x1800033e7  jnz     short loc_180003415
0x1800033e9  mov     ebx, 8007000Eh
0x1800033ee  mov     edx, 0B4h; void *
0x1800033f3  mov     r9d, ebx; char *
0x1800033f6  mov     rcx, [rsp+68h]; this
0x1800033fb  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\propsys\\schemacache"...
0x180003402  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003407  lea     rcx, [rsp+68h+pszStr2]
0x18000340c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180003411  mov     eax, ebx
0x180003413  jmp     short loc_180003425
0x180003415  test    rbx, rbx
0x180003418  jz      short loc_180003423
0x18000341a  mov     rcx, rbx; pv
0x18000341d  call    cs:__imp_CoTaskMemFree
0x180003423  xor     eax, eax
0x180003425  add     rsp, 48h
0x180003429  pop     rdi
0x18000342a  pop     rsi
0x18000342b  pop     rbp
0x18000342c  pop     rbx
0x18000342d  retn
```
