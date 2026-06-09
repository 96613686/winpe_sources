# PolicyManagerScopeData::~PolicyManagerScopeData(void)

- ea: `0x18002bee8`
- end: `0x18002c0c2`
- name: `??1PolicyManagerScopeData@@QEAA@XZ`
- size: `474`
- prototype: `void __fastcall(PolicyManagerScopeData *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002ca78`
- `0x18002fac2`

## callees

- `0x1800146e4`
- `0x18002be1c`
- `0x18002bee8`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002befd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bf12`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bf27`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bf3c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bf51`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bf66`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bf7b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bf90`
- `OLEAUT32!__imp_SysFreeString` at `0x18002befd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bf12`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bf27`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bf3c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bf51`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bf66`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bf7b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bf90`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002bfc3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002bfdb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002bfc3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002bfdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bff8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c008`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c039`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c049`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c07d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c090`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bff8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c008`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c039`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c049`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c07d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c090`

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
    operator delete(v10, (const struct std::nothrow_t *)0x78);
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
0x18002bee8  mov     [rsp+arg_0], rbx
0x18002beed  push    rdi
0x18002beee  sub     rsp, 20h
0x18002bef2  mov     rdi, rcx
0x18002bef5  mov     rcx, [rcx]; bstrString
0x18002bef8  test    rcx, rcx
0x18002befb  jz      short loc_18002BF09
0x18002befd  call    cs:__imp_SysFreeString
0x18002bf04  nop     dword ptr [rax+rax+00h]
0x18002bf09  mov     rcx, [rdi+10h]; bstrString
0x18002bf0d  test    rcx, rcx
0x18002bf10  jz      short loc_18002BF1E
0x18002bf12  call    cs:__imp_SysFreeString
0x18002bf19  nop     dword ptr [rax+rax+00h]
0x18002bf1e  mov     rcx, [rdi+18h]; bstrString
0x18002bf22  test    rcx, rcx
0x18002bf25  jz      short loc_18002BF33
0x18002bf27  call    cs:__imp_SysFreeString
0x18002bf2e  nop     dword ptr [rax+rax+00h]
0x18002bf33  mov     rcx, [rdi+20h]; bstrString
0x18002bf37  test    rcx, rcx
0x18002bf3a  jz      short loc_18002BF48
0x18002bf3c  call    cs:__imp_SysFreeString
0x18002bf43  nop     dword ptr [rax+rax+00h]
0x18002bf48  mov     rcx, [rdi+8]; bstrString
0x18002bf4c  test    rcx, rcx
0x18002bf4f  jz      short loc_18002BF5D
0x18002bf51  call    cs:__imp_SysFreeString
0x18002bf58  nop     dword ptr [rax+rax+00h]
0x18002bf5d  mov     rcx, [rdi+28h]; bstrString
0x18002bf61  test    rcx, rcx
0x18002bf64  jz      short loc_18002BF72
0x18002bf66  call    cs:__imp_SysFreeString
0x18002bf6d  nop     dword ptr [rax+rax+00h]
0x18002bf72  mov     rcx, [rdi+30h]; bstrString
0x18002bf76  test    rcx, rcx
0x18002bf79  jz      short loc_18002BF87
0x18002bf7b  call    cs:__imp_SysFreeString
0x18002bf82  nop     dword ptr [rax+rax+00h]
0x18002bf87  mov     rcx, [rdi+38h]; bstrString
0x18002bf8b  test    rcx, rcx
0x18002bf8e  jz      short loc_18002BF9C
0x18002bf90  call    cs:__imp_SysFreeString
0x18002bf97  nop     dword ptr [rax+rax+00h]
0x18002bf9c  mov     rbx, [rdi+60h]
0x18002bfa0  test    rbx, rbx
0x18002bfa3  jz      short loc_18002BFBA
0x18002bfa5  mov     rcx, rbx; this
0x18002bfa8  call    ??1PolicyManagerPolicyMetaData@@QEAA@XZ; PolicyManagerPolicyMetaData::~PolicyManagerPolicyMetaData(void)
0x18002bfad  mov     edx, 78h ; 'x'; struct std::nothrow_t *
0x18002bfb2  mov     rcx, rbx; void *
0x18002bfb5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002bfba  mov     rcx, [rdi+68h]; hLibModule
0x18002bfbe  test    rcx, rcx
0x18002bfc1  jz      short loc_18002BFCF
0x18002bfc3  call    cs:__imp_FreeLibrary
0x18002bfca  nop     dword ptr [rax+rax+00h]
0x18002bfcf  mov     rcx, [rdi+90h]; hLibModule
0x18002bfd6  test    rcx, rcx
0x18002bfd9  jz      short loc_18002BFE7
0x18002bfdb  call    cs:__imp_FreeLibrary
0x18002bfe2  nop     dword ptr [rax+rax+00h]
0x18002bfe7  mov     rcx, [rdi+70h]
0x18002bfeb  test    rcx, rcx
0x18002bfee  jz      short loc_18002C020
0x18002bff0  mov     rbx, [rcx+10h]
0x18002bff4  mov     rcx, [rcx+8]; pv
0x18002bff8  call    cs:__imp_CoTaskMemFree
0x18002bfff  nop     dword ptr [rax+rax+00h]
0x18002c004  mov     rcx, [rdi+70h]; pv
0x18002c008  call    cs:__imp_CoTaskMemFree
0x18002c00f  nop     dword ptr [rax+rax+00h]
0x18002c014  mov     [rdi+70h], rbx
0x18002c018  mov     rcx, rbx
0x18002c01b  test    rbx, rbx
0x18002c01e  jnz     short loc_18002BFF0
0x18002c020  mov     rcx, [rdi+78h]
0x18002c024  mov     qword ptr [rdi+70h], 0
0x18002c02c  test    rcx, rcx
0x18002c02f  jz      short loc_18002C061
0x18002c031  mov     rbx, [rcx+10h]
0x18002c035  mov     rcx, [rcx+8]; pv
0x18002c039  call    cs:__imp_CoTaskMemFree
0x18002c040  nop     dword ptr [rax+rax+00h]
0x18002c045  mov     rcx, [rdi+78h]; pv
0x18002c049  call    cs:__imp_CoTaskMemFree
0x18002c050  nop     dword ptr [rax+rax+00h]
0x18002c055  mov     [rdi+78h], rbx
0x18002c059  mov     rcx, rbx
0x18002c05c  test    rbx, rbx
0x18002c05f  jnz     short loc_18002C031
0x18002c061  mov     rcx, [rdi+80h]
0x18002c068  mov     qword ptr [rdi+78h], 0
0x18002c070  test    rcx, rcx
0x18002c073  jz      short loc_18002C0AB
0x18002c075  mov     rbx, [rcx+10h]
0x18002c079  mov     rcx, [rcx+8]; pv
0x18002c07d  call    cs:__imp_CoTaskMemFree
0x18002c084  nop     dword ptr [rax+rax+00h]
0x18002c089  mov     rcx, [rdi+80h]; pv
0x18002c090  call    cs:__imp_CoTaskMemFree
0x18002c097  nop     dword ptr [rax+rax+00h]
0x18002c09c  mov     [rdi+80h], rbx
0x18002c0a3  mov     rcx, rbx
0x18002c0a6  test    rbx, rbx
0x18002c0a9  jnz     short loc_18002C075
0x18002c0ab  mov     rbx, [rsp+28h+arg_0]
0x18002c0b0  mov     qword ptr [rdi+80h], 0
0x18002c0bb  add     rsp, 20h
0x18002c0bf  pop     rdi
0x18002c0c0  retn
```
