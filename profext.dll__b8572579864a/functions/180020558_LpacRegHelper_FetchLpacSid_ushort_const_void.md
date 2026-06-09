# LpacRegHelper::FetchLpacSid(ushort const *,void * *)

- ea: `0x180020558`
- end: `0x18002065b`
- name: `?FetchLpacSid@LpacRegHelper@@SAJPEBGPEAPEAX@Z`
- size: `259`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001d970`

## callees

- `0x1800044e0`
- `0x180004594`
- `0x18000c7d4`
- `0x18000f5b0`
- `0x18001f2b0`
- `0x180020558`

## import_xrefs

- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x1800205f2`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x1800205f2`

## string_xrefs

- `0x18002057c`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x1800205c0`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x180020618`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x1800205b1`: `LPAC API registry entry doesn't exist`

## pseudocode

```c
__int64 __fastcall LpacRegHelper::FetchLpacSid(const unsigned __int16 *a1, void **a2)
{
  __int64 v4; // rdx
  unsigned int v5; // ebx
  int v6; // edi
  int v8; // [rsp+20h] [rbp-18h]
  const char *v9; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *v11; // [rsp+40h] [rbp+8h] BYREF

  if ( !a1 )
  {
    v4 = 754;
LABEL_3:
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)0x80070057LL,
      v8);
    return v5;
  }
  if ( !a2 )
  {
    v4 = 755;
    goto LABEL_3;
  }
  v6 = LpacRegHelper::CheckLpacRegExists(a1);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2F8,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)(unsigned int)v6,
      (int)"LPAC API registry entry doesn't exist",
      v9);
    return (unsigned int)v6;
  }
  v11 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v11,
    0);
  v5 = DeriveAppContainerSidFromAppContainerName(a1, &v11);
  if ( (v5 & 0x80000000) == 0 )
  {
    v5 = 0;
    *a2 = v11;
    v11 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2FE,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)v5,
      (int)"Base container isn't instantiated",
      v9);
  }
  wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v11);
  return v5;
}

```

## disassembly

```asm
0x180020558  mov     [rsp+arg_8], rbx
0x18002055d  mov     [rsp+arg_10], rsi
0x180020562  push    rdi
0x180020563  sub     rsp, 30h
0x180020567  mov     rsi, rdx
0x18002056a  mov     rbx, rcx
0x18002056d  test    rcx, rcx
0x180020570  jnz     short loc_180020595
0x180020572  mov     edx, 2F2h; void *
0x180020577  mov     rcx, [rsp+38h]; this
0x18002057c  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180020583  mov     ebx, 80070057h
0x180020588  mov     r9d, ebx; char *
0x18002058b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020590  jmp     loc_180020648
0x180020595  test    rsi, rsi
0x180020598  jnz     short loc_1800205A1
0x18002059a  mov     edx, 2F3h
0x18002059f  jmp     short loc_180020577
0x1800205a1  call    ?CheckLpacRegExists@LpacRegHelper@@SAJPEBG@Z; LpacRegHelper::CheckLpacRegExists(ushort const *)
0x1800205a6  mov     edi, eax
0x1800205a8  test    eax, eax
0x1800205aa  jns     short loc_1800205D5
0x1800205ac  mov     rcx, [rsp+38h]; this
0x1800205b1  lea     rax, aLpacApiRegistr; "LPAC API registry entry doesn't exist"
0x1800205b8  mov     r9d, edi; char *
0x1800205bb  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800205c0  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800205c7  mov     edx, 2F8h; void *
0x1800205cc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800205d1  mov     eax, edi
0x1800205d3  jmp     short loc_18002064A
0x1800205d5  xor     edx, edx
0x1800205d7  mov     [rsp+38h+arg_0], 0
0x1800205e0  lea     rcx, [rsp+38h+arg_0]
0x1800205e5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800205ea  lea     rdx, [rsp+38h+arg_0]
0x1800205ef  mov     rcx, rbx
0x1800205f2  call    cs:__imp_DeriveAppContainerSidFromAppContainerName
0x1800205f9  nop     dword ptr [rax+rax+00h]
0x1800205fe  mov     ebx, eax
0x180020600  test    eax, eax
0x180020602  jns     short loc_18002062B
0x180020604  mov     rcx, [rsp+38h]; this
0x180020609  lea     rax, aBaseContainerI; "Base container isn't instantiated"
0x180020610  mov     r9d, ebx; char *
0x180020613  mov     qword ptr [rsp+38h+var_18], rax; int
0x180020618  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002061f  mov     edx, 2FEh; void *
0x180020624  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180020629  jmp     short loc_18002063E
0x18002062b  mov     rax, [rsp+38h+arg_0]
0x180020630  xor     ebx, ebx
0x180020632  mov     [rsi], rax
0x180020635  mov     [rsp+38h+arg_0], 0
0x18002063e  lea     rcx, [rsp+38h+arg_0]
0x180020643  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x180020648  mov     eax, ebx
0x18002064a  mov     rbx, [rsp+38h+arg_8]
0x18002064f  mov     rsi, [rsp+38h+arg_10]
0x180020654  add     rsp, 30h
0x180020658  pop     rdi
0x180020659  retn
```
