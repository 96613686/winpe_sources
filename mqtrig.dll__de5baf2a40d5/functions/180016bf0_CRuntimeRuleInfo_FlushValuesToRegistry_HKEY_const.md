# CRuntimeRuleInfo::FlushValuesToRegistry(HKEY__ * const &)

- ea: `0x180016bf0`
- end: `0x180016d87`
- name: `?FlushValuesToRegistry@CRuntimeRuleInfo@@QEAAXAEBQEAUHKEY__@@@Z`
- size: `407`
- prototype: `void __fastcall(CRuntimeRuleInfo *__hidden this, HKEY *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180016944`
- `0x1800173dc`

## callees

- `0x180005740`
- `0x18001519c`
- `0x1800156d4`
- `0x180016bf0`

## pseudocode

```c
void __fastcall CRuntimeRuleInfo::FlushValuesToRegistry(CRuntimeRuleInfo *this, HKEY *a2)
{
  __int64 v3; // rax
  const wchar_t **v4; // rdx
  const wchar_t *v6; // rdx
  const wchar_t **v7; // rdx
  const wchar_t *v8; // rdx
  const wchar_t **v9; // rdx
  const wchar_t *v10; // rdx
  const wchar_t **v11; // rdx
  const wchar_t *v12; // rdx
  const wchar_t **v13; // rax
  const wchar_t *v14; // rdx
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-38h] BYREF
  __int64 v17; // [rsp+28h] [rbp-30h]
  const wchar_t *v18; // [rsp+30h] [rbp-28h]
  int v19; // [rsp+38h] [rbp-20h]
  __int64 v20; // [rsp+40h] [rbp-18h]
  BOOL Data; // [rsp+90h] [rbp+38h] BYREF

  v18 = L"Name";
  v3 = (__int64)*a2;
  v4 = (const wchar_t **)*((_QWORD *)this + 1);
  v16 = 1;
  v17 = 0;
  v19 = 0;
  v20 = v3;
  if ( v4 )
    v6 = *v4;
  else
    v6 = 0;
  CmSetValue((const struct RegEntry *)&v16, v6);
  v7 = (const wchar_t **)*((_QWORD *)this + 2);
  v18 = L"Description";
  v20 = (__int64)*a2;
  v16 = 1;
  v17 = 0;
  v19 = 0;
  if ( v7 )
    v8 = *v7;
  else
    v8 = 0;
  CmSetValue((const struct RegEntry *)&v16, v8);
  _bstr_t::operator=((char *)this + 24, L"MSQMTriggerObjects.MSMQRuleHandler");
  v9 = (const wchar_t **)*((_QWORD *)this + 3);
  v18 = L"ImplementationProgID";
  v20 = (__int64)*a2;
  v16 = 1;
  v17 = 0;
  v19 = 0;
  if ( v9 )
    v10 = *v9;
  else
    v10 = 0;
  CmSetValue((const struct RegEntry *)&v16, v10);
  v11 = (const wchar_t **)*((_QWORD *)this + 5);
  v18 = L"Condition";
  v20 = (__int64)*a2;
  v16 = 1;
  v17 = 0;
  v19 = 0;
  if ( v11 )
    v12 = *v11;
  else
    v12 = 0;
  CmSetValue((const struct RegEntry *)&v16, v12);
  v16 = 1;
  v18 = L"Action";
  v20 = (__int64)*a2;
  v13 = (const wchar_t **)*((_QWORD *)this + 4);
  v17 = 0;
  v19 = 0;
  if ( v13 )
    v14 = *v13;
  else
    v14 = 0;
  CmSetValue((const struct RegEntry *)&v16, v14);
  v15 = *((_BYTE *)this + 1072) == 0;
  v18 = L"ShowWindow";
  v20 = (__int64)*a2;
  v16 = 1;
  v17 = 0;
  Data = !v15;
  v19 = 0;
  SetValueInternal((struct RegEntry *)&v16, 4u, (BYTE *)&Data, 4u);
}

```

## disassembly

```asm
0x180016bf0  push    rbp
0x180016bf2  push    rbx
0x180016bf3  push    rsi
0x180016bf4  push    rdi
0x180016bf5  push    r14
0x180016bf7  push    r15
0x180016bf9  mov     rbp, rsp
0x180016bfc  sub     rsp, 58h
0x180016c00  xor     r14d, r14d
0x180016c03  lea     rax, aName; "Name"
0x180016c0a  mov     [rbp+var_28], rax
0x180016c0e  mov     rdi, rdx
0x180016c11  mov     rax, [rdx]
0x180016c14  mov     r15d, 1
0x180016c1a  mov     rdx, [rcx+8]
0x180016c1e  mov     rsi, rcx
0x180016c21  mov     [rbp+var_38], r15d
0x180016c25  mov     [rbp+var_30], r14
0x180016c29  mov     [rbp+var_20], r14d
0x180016c2d  mov     [rbp+var_18], rax
0x180016c31  test    rdx, rdx
0x180016c34  jz      short loc_180016C3B
0x180016c36  mov     rdx, [rdx]
0x180016c39  jmp     short loc_180016C3E
0x180016c3b  mov     rdx, r14; lpData
0x180016c3e  lea     rcx, [rbp+var_38]; struct RegEntry *
0x180016c42  call    ?CmSetValue@@YAXAEBVRegEntry@@PEB_W@Z; CmSetValue(RegEntry const &,wchar_t const *)
0x180016c47  mov     rdx, [rsi+10h]
0x180016c4b  lea     rax, aDescription; "Description"
0x180016c52  mov     [rbp+var_28], rax
0x180016c56  mov     rax, [rdi]
0x180016c59  mov     [rbp+var_18], rax
0x180016c5d  mov     [rbp+var_38], r15d
0x180016c61  mov     [rbp+var_30], r14
0x180016c65  mov     [rbp+var_20], r14d
0x180016c69  test    rdx, rdx
0x180016c6c  jz      short loc_180016C73
0x180016c6e  mov     rdx, [rdx]
0x180016c71  jmp     short loc_180016C76
0x180016c73  mov     rdx, r14; lpData
0x180016c76  lea     rcx, [rbp+var_38]; struct RegEntry *
0x180016c7a  call    ?CmSetValue@@YAXAEBVRegEntry@@PEB_W@Z; CmSetValue(RegEntry const &,wchar_t const *)
0x180016c7f  lea     rdx, aMsqmtriggerobj; "MSQMTriggerObjects.MSMQRuleHandler"
0x180016c86  lea     rcx, [rsi+18h]
0x180016c8a  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x180016c8f  mov     rdx, [rsi+18h]
0x180016c93  lea     rax, aImplementation; "ImplementationProgID"
0x180016c9a  mov     [rbp+var_28], rax
0x180016c9e  mov     rax, [rdi]
0x180016ca1  mov     [rbp+var_18], rax
0x180016ca5  mov     [rbp+var_38], r15d
0x180016ca9  mov     [rbp+var_30], r14
0x180016cad  mov     [rbp+var_20], r14d
0x180016cb1  test    rdx, rdx
0x180016cb4  jz      short loc_180016CBB
0x180016cb6  mov     rdx, [rdx]
0x180016cb9  jmp     short loc_180016CBE
0x180016cbb  mov     rdx, r14; lpData
0x180016cbe  lea     rcx, [rbp+var_38]; struct RegEntry *
0x180016cc2  call    ?CmSetValue@@YAXAEBVRegEntry@@PEB_W@Z; CmSetValue(RegEntry const &,wchar_t const *)
0x180016cc7  mov     rdx, [rsi+28h]
0x180016ccb  lea     rax, aCondition; "Condition"
0x180016cd2  mov     [rbp+var_28], rax
0x180016cd6  mov     rax, [rdi]
0x180016cd9  mov     [rbp+var_18], rax
0x180016cdd  mov     [rbp+var_38], r15d
0x180016ce1  mov     [rbp+var_30], r14
0x180016ce5  mov     [rbp+var_20], r14d
0x180016ce9  test    rdx, rdx
0x180016cec  jz      short loc_180016CF3
0x180016cee  mov     rdx, [rdx]
0x180016cf1  jmp     short loc_180016CF6
0x180016cf3  mov     rdx, r14; lpData
0x180016cf6  lea     rcx, [rbp+var_38]; struct RegEntry *
0x180016cfa  call    ?CmSetValue@@YAXAEBVRegEntry@@PEB_W@Z; CmSetValue(RegEntry const &,wchar_t const *)
0x180016cff  lea     rax, aAction; "Action"
0x180016d06  mov     [rbp+var_38], r15d
0x180016d0a  mov     [rbp+var_28], rax
0x180016d0e  mov     rax, [rdi]
0x180016d11  mov     [rbp+var_18], rax
0x180016d15  mov     rax, [rsi+20h]
0x180016d19  mov     [rbp+var_30], r14
0x180016d1d  mov     [rbp+var_20], r14d
0x180016d21  test    rax, rax
0x180016d24  jz      short loc_180016D2B
0x180016d26  mov     rdx, [rax]
0x180016d29  jmp     short loc_180016D2E
0x180016d2b  mov     rdx, r14; lpData
0x180016d2e  lea     rcx, [rbp+var_38]; struct RegEntry *
0x180016d32  call    ?CmSetValue@@YAXAEBVRegEntry@@PEB_W@Z; CmSetValue(RegEntry const &,wchar_t const *)
0x180016d37  cmp     [rsi+430h], r14b
0x180016d3e  lea     rax, aShowwindow; "ShowWindow"
0x180016d45  mov     [rbp+var_28], rax
0x180016d49  lea     r8, [rbp+Data]; lpData
0x180016d4d  mov     rax, [rdi]
0x180016d50  lea     rcx, [rbp+var_38]; struct RegEntry *
0x180016d54  mov     [rbp+var_18], rax
0x180016d58  mov     edx, 4; dwType
0x180016d5d  mov     eax, r14d
0x180016d60  mov     [rbp+var_38], r15d
0x180016d64  setnz   al
0x180016d67  mov     [rbp+var_30], r14
0x180016d6b  mov     r9d, edx; cbData
0x180016d6e  mov     [rbp+Data], eax
0x180016d71  mov     [rbp+var_20], r14d
0x180016d75  call    SetValueInternal
0x180016d7a  add     rsp, 58h
0x180016d7e  pop     r15
0x180016d80  pop     r14
0x180016d82  pop     rdi
0x180016d83  pop     rsi
0x180016d84  pop     rbx
0x180016d85  pop     rbp
0x180016d86  retn
```
