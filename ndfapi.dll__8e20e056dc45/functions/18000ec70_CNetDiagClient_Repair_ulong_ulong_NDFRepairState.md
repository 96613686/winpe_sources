# CNetDiagClient::Repair(ulong,ulong,NDFRepairState)

- ea: `0x18000ec70`
- end: `0x18000eecf`
- name: `?Repair@CNetDiagClient@@IEAAJKKW4NDFRepairState@@@Z`
- size: `607`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001a6b4`

## callees

- `0x18000cd4c`
- `0x18000eb28`
- `0x18000ec70`
- `0x18000f590`
- `0x18001f646`
- `0x18001f690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ee2c`
- `KERNEL32!GetLastError` at `0x18000ee2c`
- `wdi!WdiGetResult` at `0x18000ee0e`
- `wdi!WdiGetResult` at `0x18000ee0e`
- `wdi!WdiAddParameter` at `0x18000ecf9`
- `wdi!WdiAddParameter` at `0x18000ed5b`
- `wdi!WdiAddParameter` at `0x18000ed88`
- `wdi!WdiAddParameter` at `0x18000edb1`
- `wdi!WdiAddParameter` at `0x18000ecf9`
- `wdi!WdiAddParameter` at `0x18000ed5b`
- `wdi!WdiAddParameter` at `0x18000ed88`
- `wdi!WdiAddParameter` at `0x18000edb1`
- `wdi!WdiGetParameterByName` at `0x18000ecc9`
- `wdi!WdiGetParameterByName` at `0x18000ecc9`
- `wdi!WdiResolve` at `0x18000edca`
- `wdi!WdiResolve` at `0x18000edca`

## string_xrefs

- `0x18000ecad`: `SplitRepairAndValidate`
- `0x18000ece9`: `SplitRepairAndValidate`
- `0x18000ed52`: `RepairState`
- `0x18000ed72`: `SelectedRepairGUID`

## pseudocode

```c
__int64 __fastcall CNetDiagClient::Repair(__int64 a1, unsigned int a2, DWORD a3, int a4)
{
  __int64 v5; // rdi
  __int64 v7; // rcx
  __int64 v8; // rcx
  signed int v9; // ecx
  struct _GUID *v10; // rdi
  unsigned int *Data4; // rsi
  int v12; // eax
  __int64 v13; // r8
  DWORD v14; // eax
  bool v15; // sf
  signed int LastError; // eax
  unsigned int v17; // eax
  int v19; // [rsp+30h] [rbp-40h] BYREF
  int v20; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v21; // [rsp+40h] [rbp-30h] BYREF
  int v22; // [rsp+44h] [rbp-2Ch] BYREF
  __int64 v23; // [rsp+48h] [rbp-28h] BYREF
  __int128 Buf2; // [rsp+50h] [rbp-20h] BYREF

  v5 = a2;
  v20 = a4;
  v7 = *(_QWORD *)(a1 + 128);
  v19 = 0;
  v21 = 0;
  v23 = 0;
  Buf2 = 0;
  if ( (int)WdiGetParameterByName(v7, 0, L"SplitRepairAndValidate", &v23) < 0 )
  {
    v8 = *(_QWORD *)(a1 + 128);
    v22 = 1;
    v9 = WdiAddParameter(v8, 0, L"SplitRepairAndValidate", 4, &v22);
    if ( v9 < 0 )
      return (unsigned int)v9;
  }
  v10 = (struct _GUID *)(a1 + 152 * v5 + 168);
  Data4 = (unsigned int *)v10[6].Data4;
  if ( !v20 )
  {
    v9 = CNetDiagClient::StoreRepairExecution((CNetDiagClient *)a1, v10, *Data4);
    if ( v9 < 0 )
      return (unsigned int)v9;
  }
  v9 = WdiAddParameter(*(_QWORD *)(a1 + 128), 0, L"RepairState", 4, &v20);
  if ( v9 < 0 )
    return (unsigned int)v9;
  v9 = WdiAddParameter(*(_QWORD *)(a1 + 128), 0, L"SelectedRepairGUID", 16, v10);
  if ( v9 < 0 )
    return (unsigned int)v9;
  v9 = WdiAddParameter(*(_QWORD *)(a1 + 128), 0, L"RootCauseIndex", 4, Data4);
  if ( v9 < 0 )
    return (unsigned int)v9;
  v12 = WdiResolve(*(_QWORD *)(a1 + 128), 0);
  v9 = v12;
  if ( v12 < 0 )
    return (unsigned int)v9;
  v14 = NetDiagClientWaitForObjects((unsigned int)v12, (void *const *)(a1 + 3104), v13, a3);
  switch ( v14 )
  {
    case 0u:
      if ( !*(_DWORD *)(a1 + 3276) )
      {
        v9 = WdiGetResult(*(_QWORD *)(a1 + 128), &Buf2, &v19, &v21);
        v15 = v9 < 0;
        goto LABEL_17;
      }
      return (unsigned int)-2147467260;
    case 0x80u:
      return (unsigned int)-2147467260;
    case 0x102u:
      return (unsigned int)-2147024638;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  v15 = v9 < 0;
LABEL_17:
  if ( v15 )
    return (unsigned int)v9;
  if ( memcmp_0(NetDiagModuleId, &Buf2, 0x10u) || v21 < 2 )
    return (unsigned int)-2147467259;
  if ( v21 != 2 )
  {
    if ( v21 == 4 )
    {
      v17 = v19;
      if ( v19 == -2147023673 )
        return (unsigned int)-2147467260;
      return v17;
    }
    return (unsigned int)-2147467259;
  }
  v9 = v19;
  if ( v19 >= 0 )
  {
    CNetDiagClient::GetCallResult((CNetDiagClient *)a1, &v19);
    return (unsigned int)v19;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000ec70  push    rbp
0x18000ec72  push    rbx
0x18000ec73  push    rsi
0x18000ec74  push    rdi
0x18000ec75  push    r14
0x18000ec77  mov     rbp, rsp
0x18000ec7a  sub     rsp, 70h
0x18000ec7e  mov     rax, cs:__security_cookie
0x18000ec85  xor     rax, rsp
0x18000ec88  mov     [rbp+var_10], rax
0x18000ec8c  mov     r14d, r8d
0x18000ec8f  mov     edi, edx
0x18000ec91  mov     rbx, rcx
0x18000ec94  mov     [rbp+var_38], r9d
0x18000ec98  mov     rcx, [rcx+80h]
0x18000ec9f  lea     r9, [rbp+var_28]
0x18000eca3  xorps   xmm0, xmm0
0x18000eca6  mov     [rbp+var_40], 0
0x18000ecad  lea     r8, aSplitrepairand; "SplitRepairAndValidate"
0x18000ecb4  mov     [rbp+var_30], 0
0x18000ecbb  xor     edx, edx
0x18000ecbd  mov     [rbp+var_28], 0
0x18000ecc5  movups  [rbp+Buf2], xmm0
0x18000ecc9  call    cs:__imp_WdiGetParameterByName
0x18000eccf  test    eax, eax
0x18000ecd1  jns     short loc_18000ED09
0x18000ecd3  mov     rcx, [rbx+80h]
0x18000ecda  lea     rax, [rbp+var_2C]
0x18000ecde  mov     r9d, 4
0x18000ece4  mov     [rsp+70h+var_50], rax
0x18000ece9  lea     r8, aSplitrepairand; "SplitRepairAndValidate"
0x18000ecf0  mov     [rbp+var_2C], 1
0x18000ecf7  xor     edx, edx
0x18000ecf9  call    cs:__imp_WdiAddParameter
0x18000ecff  mov     ecx, eax
0x18000ed01  test    eax, eax
0x18000ed03  js      loc_18000EEB6
0x18000ed09  imul    rdi, 98h
0x18000ed10  add     rdi, 0A8h
0x18000ed17  add     rdi, rbx
0x18000ed1a  cmp     [rbp+var_38], 0
0x18000ed1e  lea     rsi, [rdi+68h]
0x18000ed22  jnz     short loc_18000ED3C
0x18000ed24  mov     r8d, [rsi]; unsigned int
0x18000ed27  mov     rdx, rdi; struct _GUID *
0x18000ed2a  mov     rcx, rbx; this
0x18000ed2d  call    ?StoreRepairExecution@CNetDiagClient@@IEAAJAEAU_GUID@@I@Z; CNetDiagClient::StoreRepairExecution(_GUID &,uint)
0x18000ed32  mov     ecx, eax
0x18000ed34  test    eax, eax
0x18000ed36  js      loc_18000EEB6
0x18000ed3c  mov     rcx, [rbx+80h]
0x18000ed43  lea     rax, [rbp+var_38]
0x18000ed47  mov     r9d, 4
0x18000ed4d  mov     [rsp+70h+var_50], rax
0x18000ed52  lea     r8, aRepairstate; "RepairState"
0x18000ed59  xor     edx, edx
0x18000ed5b  call    cs:__imp_WdiAddParameter
0x18000ed61  mov     ecx, eax
0x18000ed63  test    eax, eax
0x18000ed65  js      loc_18000EEB6
0x18000ed6b  mov     rcx, [rbx+80h]
0x18000ed72  lea     r8, aSelectedrepair; "SelectedRepairGUID"
0x18000ed79  mov     [rsp+70h+var_50], rdi
0x18000ed7e  xor     edx, edx
0x18000ed80  mov     edi, 10h
0x18000ed85  mov     r9d, edi
0x18000ed88  call    cs:__imp_WdiAddParameter
0x18000ed8e  mov     ecx, eax
0x18000ed90  test    eax, eax
0x18000ed92  js      loc_18000EEB6
0x18000ed98  mov     rcx, [rbx+80h]
0x18000ed9f  lea     r9d, [rdi-0Ch]
0x18000eda3  lea     r8, aRootcauseindex; "RootCauseIndex"
0x18000edaa  mov     [rsp+70h+var_50], rsi
0x18000edaf  xor     edx, edx
0x18000edb1  call    cs:__imp_WdiAddParameter
0x18000edb7  mov     ecx, eax
0x18000edb9  test    eax, eax
0x18000edbb  js      loc_18000EEB6
0x18000edc1  mov     rcx, [rbx+80h]
0x18000edc8  xor     edx, edx
0x18000edca  call    cs:__imp_WdiResolve
0x18000edd0  mov     ecx, eax; unsigned int
0x18000edd2  test    eax, eax
0x18000edd4  js      loc_18000EEB6
0x18000edda  lea     rdx, [rbx+0C20h]; void **
0x18000ede1  mov     r9d, r14d; unsigned int
0x18000ede4  call    ?NetDiagClientWaitForObjects@@YAKKPEBQEAXHK@Z; NetDiagClientWaitForObjects(ulong,void * const *,int,ulong)
0x18000ede9  test    eax, eax
0x18000edeb  jnz     short loc_18000EE1A
0x18000eded  mov     eax, [rbx+0CCCh]
0x18000edf3  test    eax, eax
0x18000edf5  jnz     loc_18000EEB1
0x18000edfb  mov     rcx, [rbx+80h]
0x18000ee02  lea     r9, [rbp+var_30]
0x18000ee06  lea     r8, [rbp+var_40]
0x18000ee0a  lea     rdx, [rbp+Buf2]
0x18000ee0e  call    cs:__imp_WdiGetResult
0x18000ee14  mov     ecx, eax
0x18000ee16  test    eax, eax
0x18000ee18  jmp     short loc_18000EE43
0x18000ee1a  cmp     eax, 80h
0x18000ee1f  jz      loc_18000EEB1
0x18000ee25  cmp     eax, 102h
0x18000ee2a  jz      short loc_18000EEAA
0x18000ee2c  call    cs:__imp_GetLastError
0x18000ee32  mov     ecx, eax
0x18000ee34  test    eax, eax
0x18000ee36  jle     short loc_18000EE41
0x18000ee38  movzx   ecx, ax
0x18000ee3b  or      ecx, 80070000h
0x18000ee41  test    ecx, ecx
0x18000ee43  js      short loc_18000EEB6
0x18000ee45  mov     r8, rdi; Size
0x18000ee48  lea     rdx, [rbp+Buf2]; Buf2
0x18000ee4c  lea     rcx, NetDiagModuleId; Buf1
0x18000ee53  call    memcmp_0
0x18000ee58  test    eax, eax
0x18000ee5a  jz      short loc_18000EE63
0x18000ee5c  mov     ecx, 80004005h
0x18000ee61  jmp     short loc_18000EEB6
0x18000ee63  mov     ecx, [rbp+var_30]
0x18000ee66  test    ecx, ecx
0x18000ee68  jz      short loc_18000EE5C
0x18000ee6a  sub     ecx, 1
0x18000ee6d  jz      short loc_18000EE5C
0x18000ee6f  sub     ecx, 1
0x18000ee72  jz      short loc_18000EE92
0x18000ee74  sub     ecx, 1
0x18000ee77  jz      short loc_18000EE5C
0x18000ee79  cmp     ecx, 1
0x18000ee7c  jnz     short loc_18000EE5C
0x18000ee7e  mov     eax, [rbp+var_40]
0x18000ee81  mov     ecx, 80004004h
0x18000ee86  cmp     eax, 800704C7h
0x18000ee8b  cmovz   eax, ecx
0x18000ee8e  mov     ecx, eax
0x18000ee90  jmp     short loc_18000EEB6
0x18000ee92  mov     ecx, [rbp+var_40]
0x18000ee95  test    ecx, ecx
0x18000ee97  js      short loc_18000EEB6
0x18000ee99  lea     rdx, [rbp+var_40]; void *
0x18000ee9d  mov     rcx, rbx; this
0x18000eea0  call    ?GetCallResult@CNetDiagClient@@QEAAJPEAJ@Z; CNetDiagClient::GetCallResult(long *)
0x18000eea5  mov     ecx, [rbp+var_40]
0x18000eea8  jmp     short loc_18000EEB6
0x18000eeaa  mov     ecx, 80070102h
0x18000eeaf  jmp     short loc_18000EEB6
0x18000eeb1  mov     ecx, 80004004h
0x18000eeb6  mov     eax, ecx
0x18000eeb8  mov     rcx, [rbp+var_10]
0x18000eebc  xor     rcx, rsp; StackCookie
0x18000eebf  call    __security_check_cookie
0x18000eec4  add     rsp, 70h
0x18000eec8  pop     r14
0x18000eeca  pop     rdi
0x18000eecb  pop     rsi
0x18000eecc  pop     rbx
0x18000eecd  pop     rbp
0x18000eece  retn
```
