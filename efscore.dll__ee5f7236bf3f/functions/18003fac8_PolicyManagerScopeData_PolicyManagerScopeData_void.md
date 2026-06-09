# PolicyManagerScopeData::~PolicyManagerScopeData(void)

- ea: `0x18003fac8`
- end: `0x18003fc3d`
- name: `??1PolicyManagerScopeData@@QEAA@XZ`
- size: `373`
- prototype: `void __fastcall(PolicyManagerScopeData *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18003fc44`
- `0x18003ff18`
- `0x1800de633`

## callees

- `0x18003fa2c`
- `0x18003fac8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003fb60`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003fb60`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003fb6f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003fb81`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003fb6f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003fb81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fb98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fba2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fbcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fbd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fc05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fc12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fb98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fba2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fbcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fbd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fc05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fc12`
- `OLEAUT32!__imp_SysFreeString` at `0x18003fadd`
- `OLEAUT32!__imp_SysFreeString` at `0x18003faec`
- `OLEAUT32!__imp_SysFreeString` at `0x18003fafb`
- `OLEAUT32!__imp_SysFreeString` at `0x18003fb0a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003fb19`
- `OLEAUT32!__imp_SysFreeString` at `0x18003fb28`
- `OLEAUT32!__imp_SysFreeString` at `0x18003fb37`
- `OLEAUT32!__imp_SysFreeString` at `0x18003fb46`
- `OLEAUT32!__imp_SysFreeString` at `0x18003fadd`
- `OLEAUT32!__imp_SysFreeString` at `0x18003faec`
- `OLEAUT32!__imp_SysFreeString` at `0x18003fafb`
- `OLEAUT32!__imp_SysFreeString` at `0x18003fb0a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003fb19`
- `OLEAUT32!__imp_SysFreeString` at `0x18003fb28`
- `OLEAUT32!__imp_SysFreeString` at `0x18003fb37`
- `OLEAUT32!__imp_SysFreeString` at `0x18003fb46`

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
0x18003fac8  mov     [rsp+arg_0], rbx
0x18003facd  push    rdi
0x18003face  sub     rsp, 20h
0x18003fad2  mov     rdi, rcx
0x18003fad5  mov     rcx, [rcx]; bstrString
0x18003fad8  test    rcx, rcx
0x18003fadb  jz      short loc_18003FAE3
0x18003fadd  call    cs:__imp_SysFreeString
0x18003fae3  mov     rcx, [rdi+10h]; bstrString
0x18003fae7  test    rcx, rcx
0x18003faea  jz      short loc_18003FAF2
0x18003faec  call    cs:__imp_SysFreeString
0x18003faf2  mov     rcx, [rdi+18h]; bstrString
0x18003faf6  test    rcx, rcx
0x18003faf9  jz      short loc_18003FB01
0x18003fafb  call    cs:__imp_SysFreeString
0x18003fb01  mov     rcx, [rdi+20h]; bstrString
0x18003fb05  test    rcx, rcx
0x18003fb08  jz      short loc_18003FB10
0x18003fb0a  call    cs:__imp_SysFreeString
0x18003fb10  mov     rcx, [rdi+8]; bstrString
0x18003fb14  test    rcx, rcx
0x18003fb17  jz      short loc_18003FB1F
0x18003fb19  call    cs:__imp_SysFreeString
0x18003fb1f  mov     rcx, [rdi+28h]; bstrString
0x18003fb23  test    rcx, rcx
0x18003fb26  jz      short loc_18003FB2E
0x18003fb28  call    cs:__imp_SysFreeString
0x18003fb2e  mov     rcx, [rdi+30h]; bstrString
0x18003fb32  test    rcx, rcx
0x18003fb35  jz      short loc_18003FB3D
0x18003fb37  call    cs:__imp_SysFreeString
0x18003fb3d  mov     rcx, [rdi+38h]; bstrString
0x18003fb41  test    rcx, rcx
0x18003fb44  jz      short loc_18003FB4C
0x18003fb46  call    cs:__imp_SysFreeString
0x18003fb4c  mov     rbx, [rdi+60h]
0x18003fb50  test    rbx, rbx
0x18003fb53  jz      short loc_18003FB66
0x18003fb55  mov     rcx, rbx; this
0x18003fb58  call    ??1PolicyManagerPolicyMetaData@@QEAA@XZ; PolicyManagerPolicyMetaData::~PolicyManagerPolicyMetaData(void)
0x18003fb5d  mov     rcx, rbx
0x18003fb60  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003fb66  mov     rcx, [rdi+68h]; hLibModule
0x18003fb6a  test    rcx, rcx
0x18003fb6d  jz      short loc_18003FB75
0x18003fb6f  call    cs:__imp_FreeLibrary
0x18003fb75  mov     rcx, [rdi+90h]; hLibModule
0x18003fb7c  test    rcx, rcx
0x18003fb7f  jz      short loc_18003FB87
0x18003fb81  call    cs:__imp_FreeLibrary
0x18003fb87  mov     rcx, [rdi+70h]
0x18003fb8b  test    rcx, rcx
0x18003fb8e  jz      short loc_18003FBB4
0x18003fb90  mov     rbx, [rcx+10h]
0x18003fb94  mov     rcx, [rcx+8]; pv
0x18003fb98  call    cs:__imp_CoTaskMemFree
0x18003fb9e  mov     rcx, [rdi+70h]; pv
0x18003fba2  call    cs:__imp_CoTaskMemFree
0x18003fba8  mov     [rdi+70h], rbx
0x18003fbac  mov     rcx, rbx
0x18003fbaf  test    rbx, rbx
0x18003fbb2  jnz     short loc_18003FB90
0x18003fbb4  mov     rcx, [rdi+78h]
0x18003fbb8  mov     qword ptr [rdi+70h], 0
0x18003fbc0  test    rcx, rcx
0x18003fbc3  jz      short loc_18003FBE9
0x18003fbc5  mov     rbx, [rcx+10h]
0x18003fbc9  mov     rcx, [rcx+8]; pv
0x18003fbcd  call    cs:__imp_CoTaskMemFree
0x18003fbd3  mov     rcx, [rdi+78h]; pv
0x18003fbd7  call    cs:__imp_CoTaskMemFree
0x18003fbdd  mov     [rdi+78h], rbx
0x18003fbe1  mov     rcx, rbx
0x18003fbe4  test    rbx, rbx
0x18003fbe7  jnz     short loc_18003FBC5
0x18003fbe9  mov     rcx, [rdi+80h]
0x18003fbf0  mov     qword ptr [rdi+78h], 0
0x18003fbf8  test    rcx, rcx
0x18003fbfb  jz      short loc_18003FC27
0x18003fbfd  mov     rbx, [rcx+10h]
0x18003fc01  mov     rcx, [rcx+8]; pv
0x18003fc05  call    cs:__imp_CoTaskMemFree
0x18003fc0b  mov     rcx, [rdi+80h]; pv
0x18003fc12  call    cs:__imp_CoTaskMemFree
0x18003fc18  mov     [rdi+80h], rbx
0x18003fc1f  mov     rcx, rbx
0x18003fc22  test    rbx, rbx
0x18003fc25  jnz     short loc_18003FBFD
0x18003fc27  mov     rbx, [rsp+28h+arg_0]
0x18003fc2c  mov     qword ptr [rdi+80h], 0
0x18003fc37  add     rsp, 20h
0x18003fc3b  pop     rdi
0x18003fc3c  retn
```
