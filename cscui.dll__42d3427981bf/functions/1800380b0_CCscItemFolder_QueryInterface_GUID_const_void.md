# CCscItemFolder::QueryInterface(_GUID const &,void * *)

- ea: `0x1800380b0`
- end: `0x180038157`
- name: `?QueryInterface@CCscItemFolder@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `167`
- prototype: `int(CCscItemFolder *__hidden this, const struct _GUID *, void **)`
- caller_count: `8`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038160`
- `0x180038170`
- `0x180038180`
- `0x180038190`
- `0x1800381a0`
- `0x1800381b0`
- `0x1800381c0`
- `0x1800381d0`

## callees

- `0x180013dfc`
- `0x1800380b0`
- `0x18003833c`

## import_xrefs

- `SHLWAPI!__imp_QISearch` at `0x1800380d5`
- `SHLWAPI!__imp_QISearch` at `0x1800380d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003813f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003813f`

## pseudocode

```c
__int64 __fastcall CCscItemFolder::QueryInterface(CCscItemFolder *this, const struct _GUID *a2, void **a3)
{
  char v4; // di
  HRESULT v5; // ebx
  unsigned int v6; // eax
  const struct _GUID *v8; // [rsp+30h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-10h]

  v4 = 0;
  v5 = QISearch(this, &pqit, a2, a3);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = a2;
      pv = 0;
      v6 = (unsigned int)CStringIID::Text((CStringIID *)&v8);
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_5fe987ea1b1f3d929bb98d819c20dc91_Traceguids,
        v6,
        v5);
      v4 = 1;
    }
    if ( (v4 & 1) != 0 )
      CoTaskMemFree(pv);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800380b0  mov     [rsp+arg_0], rbx
0x1800380b5  mov     [rsp+arg_8], rsi
0x1800380ba  push    rdi
0x1800380bb  sub     rsp, 40h
0x1800380bf  mov     r9, r8; ppv
0x1800380c2  mov     rsi, rdx
0x1800380c5  mov     r8, rdx; riid
0x1800380c8  xor     edi, edi
0x1800380ca  lea     rdx, pqit; pqit
0x1800380d1  mov     [rsp+48h+arg_18], edi
0x1800380d5  call    cs:__imp_QISearch
0x1800380db  mov     ebx, eax
0x1800380dd  test    eax, eax
0x1800380df  jns     short loc_180038145
0x1800380e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800380e8  lea     rax, WPP_GLOBAL_Control
0x1800380ef  cmp     rcx, rax
0x1800380f2  jz      short loc_180038134
0x1800380f4  test    byte ptr [rcx+1Ch], 2
0x1800380f8  jz      short loc_180038134
0x1800380fa  lea     rcx, [rsp+48h+var_18]; this
0x1800380ff  mov     [rsp+48h+var_18], rsi
0x180038104  mov     [rsp+48h+pv], rdi
0x180038109  call    ?Text@CStringIID@@QEAAPEBGXZ; CStringIID::Text(void)
0x18003810e  mov     rcx, cs:WPP_GLOBAL_Control
0x180038115  lea     edx, [rdi+0Fh]
0x180038118  mov     r9, rax
0x18003811b  mov     [rsp+48h+var_28], ebx
0x18003811f  lea     r8, WPP_5fe987ea1b1f3d929bb98d819c20dc91_Traceguids
0x180038126  mov     rcx, [rcx+10h]
0x18003812a  call    WPP_SF_Sd
0x18003812f  mov     edi, 1
0x180038134  test    dil, 1
0x180038138  jz      short loc_180038145
0x18003813a  mov     rcx, [rsp+48h+pv]; pv
0x18003813f  call    cs:__imp_CoTaskMemFree
0x180038145  mov     rsi, [rsp+48h+arg_8]
0x18003814a  mov     eax, ebx
0x18003814c  mov     rbx, [rsp+48h+arg_0]
0x180038151  add     rsp, 40h
0x180038155  pop     rdi
0x180038156  retn
```
