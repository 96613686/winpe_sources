# SHRegFindNextAvailableKeyName

- ea: `0x180093068`
- end: `0x1800931a4`
- name: `SHRegFindNextAvailableKeyName`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800926e8`

## callees

- `0x180003198`
- `0x180004148`
- `0x180025dd4`
- `0x1800698e0`
- `0x18006ed20`
- `0x180092aa4`
- `0x180093068`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093100`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093164`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093100`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093164`

## string_xrefs

- `0x1800930e8`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`

## pseudocode

```c
__int64 __fastcall SHRegFindNextAvailableKeyName(__int64 a1, __int64 a2, _QWORD *a3)
{
  int ExistingKeyName; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rax
  void *v10; // rcx
  __int64 v11; // rax
  void *v12; // rcx
  __int64 v14; // [rsp+20h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-28h] BYREF
  __int64 v16; // [rsp+30h] [rbp-20h]
  __int64 v17; // [rsp+38h] [rbp-18h]
  __int64 v18; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  *a3 = 0;
  v14 = 0;
  pv = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  ExistingKeyName = CTSimpleArray<unsigned int,4294967294,CTPolicyCoTaskMem<unsigned int>,CSimpleArrayStandardCompareHelper<unsigned int>,CSimpleArrayStandardMergeHelper<unsigned int>>::_EnsureCapacity(
                      &pv,
                      8);
  v7 = ExistingKeyName;
  if ( ExistingKeyName < 0 )
  {
    v8 = 269;
    goto LABEL_5;
  }
  ExistingKeyName = TryFindExistingKeyName(a1, a2, &pv, &v14);
  v7 = ExistingKeyName;
  if ( ExistingKeyName < 0 )
  {
    v8 = 271;
    goto LABEL_5;
  }
  v9 = v14;
  if ( v14 )
  {
    v10 = pv;
    v14 = 0;
    *a3 = v9;
    if ( v10 )
    {
      CoTaskMemFree(v10);
      pv = 0;
    }
    v7 = 1;
  }
  else
  {
    ExistingKeyName = CreateNewKeyNameFromRegistry(&pv, &v14);
    v7 = ExistingKeyName;
    if ( ExistingKeyName < 0 )
    {
      v8 = 281;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\shell\\propsys\\schemacachehelpers.cpp",
        (const char *)(unsigned int)ExistingKeyName,
        v14);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      goto LABEL_16;
    }
    v11 = v14;
    v12 = pv;
    v14 = 0;
    *a3 = v11;
    if ( v12 )
    {
      CoTaskMemFree(v12);
      pv = 0;
    }
    v7 = 0;
  }
LABEL_16:
  v16 = 0;
  v18 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
  return v7;
}

```

## disassembly

```asm
0x180093068  mov     [rsp-28h+arg_18], rbx
0x18009306d  push    rbp
0x18009306e  push    rsi
0x18009306f  push    rdi
0x180093070  push    r14
0x180093072  push    r15
0x180093074  mov     rbp, rsp
0x180093077  sub     rsp, 50h
0x18009307b  mov     rax, cs:__security_cookie
0x180093082  xor     rax, rsp
0x180093085  mov     [rbp+var_8], rax
0x180093089  xor     r15d, r15d
0x18009308c  mov     r14, rdx
0x18009308f  mov     rsi, rcx
0x180093092  mov     [r8], r15
0x180093095  lea     rcx, [rbp+pv]
0x180093099  mov     [rbp+var_30], r15
0x18009309d  mov     rdi, r8
0x1800930a0  mov     [rbp+pv], r15
0x1800930a4  lea     edx, [r15+8]
0x1800930a8  mov     [rbp+var_20], r15
0x1800930ac  mov     [rbp+var_18], r15
0x1800930b0  mov     [rbp+var_10], r15
0x1800930b4  call    ?_EnsureCapacity@?$CTSimpleArray@I$0PPPPPPPO@V?$CTPolicyCoTaskMem@I@@V?$CSimpleArrayStandardCompareHelper@I@@V?$CSimpleArrayStandardMergeHelper@I@@@@QEAAJ_K0@Z; CTSimpleArray<uint,4294967294,CTPolicyCoTaskMem<uint>,CSimpleArrayStandardCompareHelper<uint>,CSimpleArrayStandardMergeHelper<uint>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1800930b9  mov     ebx, eax
0x1800930bb  test    eax, eax
0x1800930bd  jns     short loc_1800930C6
0x1800930bf  mov     edx, 10Dh
0x1800930c4  jmp     short loc_1800930E4
0x1800930c6  lea     r9, [rbp+var_30]
0x1800930ca  mov     rdx, r14
0x1800930cd  lea     r8, [rbp+pv]
0x1800930d1  mov     rcx, rsi
0x1800930d4  call    ?TryFindExistingKeyName@@YAJPEAUHKEY__@@PEBGAEAV?$CCoSimpleArray@I$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@I@@@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; TryFindExistingKeyName(HKEY__ *,ushort const *,CCoSimpleArray<uint,4294967294,CSimpleArrayStandardCompareHelper<uint>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800930d9  mov     ebx, eax
0x1800930db  test    eax, eax
0x1800930dd  jns     short loc_18009310C
0x1800930df  mov     edx, 10Fh; void *
0x1800930e4  mov     rcx, [rbp+28h]; this
0x1800930e8  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\propsys\\schemacache"...
0x1800930ef  mov     r9d, eax; char *
0x1800930f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800930f7  mov     rcx, [rbp+pv]; pv
0x1800930fb  test    rcx, rcx
0x1800930fe  jz      short loc_180093171
0x180093100  call    cs:__imp_CoTaskMemFree
0x180093106  mov     [rbp+pv], r15
0x18009310a  jmp     short loc_180093171
0x18009310c  mov     rax, [rbp+var_30]
0x180093110  test    rax, rax
0x180093113  jz      short loc_180093136
0x180093115  mov     rcx, [rbp+pv]; pv
0x180093119  mov     [rbp+var_30], r15
0x18009311d  mov     [rdi], rax
0x180093120  test    rcx, rcx
0x180093123  jz      short loc_18009312F
0x180093125  call    cs:__imp_CoTaskMemFree
0x18009312b  mov     [rbp+pv], r15
0x18009312f  mov     ebx, 1
0x180093134  jmp     short loc_180093171
0x180093136  lea     rdx, [rbp+var_30]
0x18009313a  lea     rcx, [rbp+pv]
0x18009313e  call    ?CreateNewKeyNameFromRegistry@@YAJAEAV?$CCoSimpleArray@I$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@I@@@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; CreateNewKeyNameFromRegistry(CCoSimpleArray<uint,4294967294,CSimpleArrayStandardCompareHelper<uint>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180093143  mov     ebx, eax
0x180093145  test    eax, eax
0x180093147  jns     short loc_180093150
0x180093149  mov     edx, 119h
0x18009314e  jmp     short loc_1800930E4
0x180093150  mov     rax, [rbp+var_30]
0x180093154  mov     rcx, [rbp+pv]; pv
0x180093158  mov     [rbp+var_30], r15
0x18009315c  mov     [rdi], rax
0x18009315f  test    rcx, rcx
0x180093162  jz      short loc_18009316E
0x180093164  call    cs:__imp_CoTaskMemFree
0x18009316a  mov     [rbp+pv], r15
0x18009316e  mov     ebx, r15d
0x180093171  lea     rcx, [rbp+var_30]
0x180093175  mov     [rbp+var_20], r15
0x180093179  mov     [rbp+var_10], r15
0x18009317d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180093182  mov     eax, ebx
0x180093184  mov     rcx, [rbp+var_8]
0x180093188  xor     rcx, rsp; StackCookie
0x18009318b  call    __security_check_cookie
0x180093190  mov     rbx, [rsp+50h+arg_18]
0x180093198  add     rsp, 50h
0x18009319c  pop     r15
0x18009319e  pop     r14
0x1800931a0  pop     rdi
0x1800931a1  pop     rsi
0x1800931a2  pop     rbp
0x1800931a3  retn
```
