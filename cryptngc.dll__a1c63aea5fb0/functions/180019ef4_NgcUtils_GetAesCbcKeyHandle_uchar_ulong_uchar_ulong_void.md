# NgcUtils::GetAesCbcKeyHandle(uchar *,ulong,uchar *,ulong,void * *)

- ea: `0x180019ef4`
- end: `0x180019fd1`
- name: `?GetAesCbcKeyHandle@NgcUtils@@YAJPEAEK0KPEAPEAX@Z`
- size: `221`
- prototype: `int(NgcUtils *__hidden this, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002cf74`

## callees

- `0x180019ef4`
- `0x180028380`
- `0x18002d08c`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x180019f2b`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180019f2b`
- `bcrypt!BCryptDestroyKey` at `0x180019f5a`
- `bcrypt!BCryptDestroyKey` at `0x180019f5a`
- `bcrypt!BCryptSetProperty` at `0x180019f83`
- `bcrypt!BCryptSetProperty` at `0x180019f83`

## string_xrefs

- `0x180019f3a`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180019f92`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::GetAesCbcKeyHandle(
        UCHAR *this,
        unsigned __int8 *a2,
        UCHAR *a3,
        unsigned __int8 *a4,
        BCRYPT_KEY_HANDLE *a5)
{
  ULONG v5; // edi
  NTSTATUS SymmetricKey; // eax
  unsigned int v8; // ebx
  NTSTATUS v10; // eax
  ULONG dwFlags; // [rsp+20h] [rbp-38h]
  ULONG dwFlagsa; // [rsp+20h] [rbp-38h]
  BCRYPT_KEY_HANDLE hKey[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v5 = (unsigned int)a4;
  hKey[0] = 0;
  SymmetricKey = BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x1A1, hKey, 0, 0, this, (ULONG)a2, 0);
  if ( SymmetricKey < 0 )
  {
    v8 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x1B5,
           (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
           (const char *)(unsigned int)SymmetricKey,
           dwFlags);
    if ( hKey[0] )
      BCryptDestroyKey(hKey[0]);
    return v8;
  }
  if ( a3 )
  {
    v10 = BCryptSetProperty(hKey[0], L"IV", a3, v5, 0);
    if ( v10 < 0 )
    {
      v8 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x1BE,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
             (const char *)(unsigned int)v10,
             dwFlagsa);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(hKey);
      return v8;
    }
  }
  *a5 = hKey[0];
  return 0;
}

```

## disassembly

```asm
0x180019ef4  mov     rax, rsp
0x180019ef7  mov     [rax+8], rbx
0x180019efb  push    rdi
0x180019efc  sub     rsp, 50h
0x180019f00  mov     dword ptr [rax-28h], 0
0x180019f07  mov     edi, r9d
0x180019f0a  mov     [rax-30h], edx
0x180019f0d  mov     rbx, r8
0x180019f10  mov     [rax-38h], rcx
0x180019f14  lea     rdx, [rax-18h]; phKey
0x180019f18  mov     ecx, 1A1h; hAlgorithm
0x180019f1d  mov     qword ptr [rax-18h], 0
0x180019f25  xor     r9d, r9d; cbKeyObject
0x180019f28  xor     r8d, r8d; pbKeyObject
0x180019f2b  call    cs:__imp_BCryptGenerateSymmetricKey
0x180019f31  test    eax, eax
0x180019f33  jns     short loc_180019F64
0x180019f35  mov     rcx, [rsp+58h]; this
0x180019f3a  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180019f41  mov     r9d, eax; char *
0x180019f44  mov     edx, 1B5h; void *
0x180019f49  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180019f4e  mov     rcx, [rsp+58h+hKey]; hKey
0x180019f53  mov     ebx, eax
0x180019f55  test    rcx, rcx
0x180019f58  jz      short loc_180019F60
0x180019f5a  call    cs:__imp_BCryptDestroyKey
0x180019f60  mov     eax, ebx
0x180019f62  jmp     short loc_180019FC6
0x180019f64  test    rbx, rbx
0x180019f67  jz      short loc_180019FB4
0x180019f69  mov     rcx, [rsp+58h+hKey]; hObject
0x180019f6e  lea     rdx, aIv; "IV"
0x180019f75  mov     r9d, edi; cbInput
0x180019f78  mov     [rsp+58h+dwFlags], 0; int
0x180019f80  mov     r8, rbx; pbInput
0x180019f83  call    cs:__imp_BCryptSetProperty
0x180019f89  test    eax, eax
0x180019f8b  jns     short loc_180019FB4
0x180019f8d  mov     rcx, [rsp+58h]; this
0x180019f92  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180019f99  mov     r9d, eax; char *
0x180019f9c  mov     edx, 1BEh; void *
0x180019fa1  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180019fa6  lea     rcx, [rsp+58h+hKey]
0x180019fab  mov     ebx, eax
0x180019fad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180019fb2  jmp     short loc_180019F60
0x180019fb4  mov     rax, [rsp+58h+hKey]
0x180019fb9  mov     rcx, qword ptr [rsp+58h+arg_20]
0x180019fc1  mov     [rcx], rax
0x180019fc4  xor     eax, eax
0x180019fc6  mov     rbx, [rsp+58h+arg_0]
0x180019fcb  add     rsp, 50h
0x180019fcf  pop     rdi
0x180019fd0  retn
```
