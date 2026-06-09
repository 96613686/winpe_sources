# PolicyManagerScopeData::~PolicyManagerScopeData(void)

- ea: `0x1800457c8`
- end: `0x1800459a2`
- name: `??1PolicyManagerScopeData@@QEAA@XZ`
- size: `474`
- prototype: `void __fastcall(PolicyManagerScopeData *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800456b8`

## callees

- `0x1800091b0`
- `0x1800456fc`
- `0x1800457c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800458a3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800458bb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800458a3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800458bb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800457dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800457f2`
- `OLEAUT32!__imp_SysFreeString` at `0x180045807`
- `OLEAUT32!__imp_SysFreeString` at `0x18004581c`
- `OLEAUT32!__imp_SysFreeString` at `0x180045831`
- `OLEAUT32!__imp_SysFreeString` at `0x180045846`
- `OLEAUT32!__imp_SysFreeString` at `0x18004585b`
- `OLEAUT32!__imp_SysFreeString` at `0x180045870`
- `OLEAUT32!__imp_SysFreeString` at `0x1800457dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800457f2`
- `OLEAUT32!__imp_SysFreeString` at `0x180045807`
- `OLEAUT32!__imp_SysFreeString` at `0x18004581c`
- `OLEAUT32!__imp_SysFreeString` at `0x180045831`
- `OLEAUT32!__imp_SysFreeString` at `0x180045846`
- `OLEAUT32!__imp_SysFreeString` at `0x18004585b`
- `OLEAUT32!__imp_SysFreeString` at `0x180045870`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800458d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800458e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045919`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045929`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004595d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045970`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800458d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800458e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045919`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045929`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004595d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045970`

## pseudocode

```c
void __fastcall PolicyManagerScopeData::~PolicyManagerScopeData(PolicyManagerScopeData *this)
{
  OLECHAR *v2; // rcx
  OLECHAR *v3; // rcx
  OLECHAR *v4; // rcx
  OLECHAR *v5; // rcx
  OLECHAR *v6; // rcx
  OLECHAR *v7; // rcx
  OLECHAR *v8; // rcx
  OLECHAR *v9; // rcx
  void *v10; // rbx
  HMODULE v11; // rcx
  HMODULE v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rbx

  v2 = *(OLECHAR **)this;
  if ( v2 )
    SysFreeString(v2);
  v3 = (OLECHAR *)*((_QWORD *)this + 2);
  if ( v3 )
    SysFreeString(v3);
  v4 = (OLECHAR *)*((_QWORD *)this + 3);
  if ( v4 )
    SysFreeString(v4);
  v5 = (OLECHAR *)*((_QWORD *)this + 4);
  if ( v5 )
    SysFreeString(v5);
  v6 = (OLECHAR *)*((_QWORD *)this + 1);
  if ( v6 )
    SysFreeString(v6);
  v7 = (OLECHAR *)*((_QWORD *)this + 5);
  if ( v7 )
    SysFreeString(v7);
  v8 = (OLECHAR *)*((_QWORD *)this + 6);
  if ( v8 )
    SysFreeString(v8);
  v9 = (OLECHAR *)*((_QWORD *)this + 7);
  if ( v9 )
    SysFreeString(v9);
  v10 = (void *)*((_QWORD *)this + 12);
  if ( v10 )
  {
    PolicyManagerPolicyMetaData::~PolicyManagerPolicyMetaData(*((PolicyManagerPolicyMetaData **)this + 12));
    operator delete(v10);
  }
  v11 = (HMODULE)*((_QWORD *)this + 13);
  if ( v11 )
    FreeLibrary(v11);
  v12 = (HMODULE)*((_QWORD *)this + 18);
  if ( v12 )
    FreeLibrary(v12);
  v13 = *((_QWORD *)this + 14);
  if ( v13 )
  {
    do
    {
      v14 = *(_QWORD *)(v13 + 16);
      CoTaskMemFree(*(LPVOID *)(v13 + 8));
      CoTaskMemFree(*((LPVOID *)this + 14));
      *((_QWORD *)this + 14) = v14;
      v13 = v14;
    }
    while ( v14 );
  }
  v15 = *((_QWORD *)this + 15);
  *((_QWORD *)this + 14) = 0;
  if ( v15 )
  {
    do
    {
      v16 = *(_QWORD *)(v15 + 16);
      CoTaskMemFree(*(LPVOID *)(v15 + 8));
      CoTaskMemFree(*((LPVOID *)this + 15));
      *((_QWORD *)this + 15) = v16;
      v15 = v16;
    }
    while ( v16 );
  }
  v17 = *((_QWORD *)this + 16);
  *((_QWORD *)this + 15) = 0;
  if ( v17 )
  {
    do
    {
      v18 = *(_QWORD *)(v17 + 16);
      CoTaskMemFree(*(LPVOID *)(v17 + 8));
      CoTaskMemFree(*((LPVOID *)this + 16));
      *((_QWORD *)this + 16) = v18;
      v17 = v18;
    }
    while ( v18 );
  }
  *((_QWORD *)this + 16) = 0;
}

```

## disassembly

```asm
0x1800457c8  mov     [rsp+arg_0], rbx
0x1800457cd  push    rdi
0x1800457ce  sub     rsp, 20h
0x1800457d2  mov     rdi, rcx
0x1800457d5  mov     rcx, [rcx]; bstrString
0x1800457d8  test    rcx, rcx
0x1800457db  jz      short loc_1800457E9
0x1800457dd  call    cs:__imp_SysFreeString
0x1800457e4  nop     dword ptr [rax+rax+00h]
0x1800457e9  mov     rcx, [rdi+10h]; bstrString
0x1800457ed  test    rcx, rcx
0x1800457f0  jz      short loc_1800457FE
0x1800457f2  call    cs:__imp_SysFreeString
0x1800457f9  nop     dword ptr [rax+rax+00h]
0x1800457fe  mov     rcx, [rdi+18h]; bstrString
0x180045802  test    rcx, rcx
0x180045805  jz      short loc_180045813
0x180045807  call    cs:__imp_SysFreeString
0x18004580e  nop     dword ptr [rax+rax+00h]
0x180045813  mov     rcx, [rdi+20h]; bstrString
0x180045817  test    rcx, rcx
0x18004581a  jz      short loc_180045828
0x18004581c  call    cs:__imp_SysFreeString
0x180045823  nop     dword ptr [rax+rax+00h]
0x180045828  mov     rcx, [rdi+8]; bstrString
0x18004582c  test    rcx, rcx
0x18004582f  jz      short loc_18004583D
0x180045831  call    cs:__imp_SysFreeString
0x180045838  nop     dword ptr [rax+rax+00h]
0x18004583d  mov     rcx, [rdi+28h]; bstrString
0x180045841  test    rcx, rcx
0x180045844  jz      short loc_180045852
0x180045846  call    cs:__imp_SysFreeString
0x18004584d  nop     dword ptr [rax+rax+00h]
0x180045852  mov     rcx, [rdi+30h]; bstrString
0x180045856  test    rcx, rcx
0x180045859  jz      short loc_180045867
0x18004585b  call    cs:__imp_SysFreeString
0x180045862  nop     dword ptr [rax+rax+00h]
0x180045867  mov     rcx, [rdi+38h]; bstrString
0x18004586b  test    rcx, rcx
0x18004586e  jz      short loc_18004587C
0x180045870  call    cs:__imp_SysFreeString
0x180045877  nop     dword ptr [rax+rax+00h]
0x18004587c  mov     rbx, [rdi+60h]
0x180045880  test    rbx, rbx
0x180045883  jz      short loc_18004589A
0x180045885  mov     rcx, rbx; this
0x180045888  call    ??1PolicyManagerPolicyMetaData@@QEAA@XZ; PolicyManagerPolicyMetaData::~PolicyManagerPolicyMetaData(void)
0x18004588d  mov     edx, 78h ; 'x'
0x180045892  mov     rcx, rbx; Block
0x180045895  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004589a  mov     rcx, [rdi+68h]; hLibModule
0x18004589e  test    rcx, rcx
0x1800458a1  jz      short loc_1800458AF
0x1800458a3  call    cs:__imp_FreeLibrary
0x1800458aa  nop     dword ptr [rax+rax+00h]
0x1800458af  mov     rcx, [rdi+90h]; hLibModule
0x1800458b6  test    rcx, rcx
0x1800458b9  jz      short loc_1800458C7
0x1800458bb  call    cs:__imp_FreeLibrary
0x1800458c2  nop     dword ptr [rax+rax+00h]
0x1800458c7  mov     rcx, [rdi+70h]
0x1800458cb  test    rcx, rcx
0x1800458ce  jz      short loc_180045900
0x1800458d0  mov     rbx, [rcx+10h]
0x1800458d4  mov     rcx, [rcx+8]; pv
0x1800458d8  call    cs:__imp_CoTaskMemFree
0x1800458df  nop     dword ptr [rax+rax+00h]
0x1800458e4  mov     rcx, [rdi+70h]; pv
0x1800458e8  call    cs:__imp_CoTaskMemFree
0x1800458ef  nop     dword ptr [rax+rax+00h]
0x1800458f4  mov     [rdi+70h], rbx
0x1800458f8  mov     rcx, rbx
0x1800458fb  test    rbx, rbx
0x1800458fe  jnz     short loc_1800458D0
0x180045900  mov     rcx, [rdi+78h]
0x180045904  mov     qword ptr [rdi+70h], 0
0x18004590c  test    rcx, rcx
0x18004590f  jz      short loc_180045941
0x180045911  mov     rbx, [rcx+10h]
0x180045915  mov     rcx, [rcx+8]; pv
0x180045919  call    cs:__imp_CoTaskMemFree
0x180045920  nop     dword ptr [rax+rax+00h]
0x180045925  mov     rcx, [rdi+78h]; pv
0x180045929  call    cs:__imp_CoTaskMemFree
0x180045930  nop     dword ptr [rax+rax+00h]
0x180045935  mov     [rdi+78h], rbx
0x180045939  mov     rcx, rbx
0x18004593c  test    rbx, rbx
0x18004593f  jnz     short loc_180045911
0x180045941  mov     rcx, [rdi+80h]
0x180045948  mov     qword ptr [rdi+78h], 0
0x180045950  test    rcx, rcx
0x180045953  jz      short loc_18004598B
0x180045955  mov     rbx, [rcx+10h]
0x180045959  mov     rcx, [rcx+8]; pv
0x18004595d  call    cs:__imp_CoTaskMemFree
0x180045964  nop     dword ptr [rax+rax+00h]
0x180045969  mov     rcx, [rdi+80h]; pv
0x180045970  call    cs:__imp_CoTaskMemFree
0x180045977  nop     dword ptr [rax+rax+00h]
0x18004597c  mov     [rdi+80h], rbx
0x180045983  mov     rcx, rbx
0x180045986  test    rbx, rbx
0x180045989  jnz     short loc_180045955
0x18004598b  mov     rbx, [rsp+28h+arg_0]
0x180045990  mov     qword ptr [rdi+80h], 0
0x18004599b  add     rsp, 20h
0x18004599f  pop     rdi
0x1800459a0  retn
```
