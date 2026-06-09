# Details::TryGetRedirectionKeyPath(ushort const *,ushort const *,ushort * *,bool *)

- ea: `0x18000ae3c`
- end: `0x18000af46`
- name: `?TryGetRedirectionKeyPath@Details@@YAJPEBG0PEAPEAGPEA_N@Z`
- size: `266`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009b90`
- `0x1800125b0`

## callees

- `0x1800076d4`
- `0x180009814`
- `0x18000ae3c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000af0f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000af0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ae8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ae8d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000ae7c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000aed5`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000ae7c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000aed5`

## pseudocode

```c
__int64 __fastcall Details::TryGetRedirectionKeyPath(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        LPCWCH *a3,
        bool *a4)
{
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rbx
  unsigned int v10; // ebx
  bool v11; // bl
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  SIZE_T cb; // [rsp+60h] [rbp+18h] BYREF
  unsigned __int16 *v15; // [rsp+68h] [rbp+20h] BYREF

  *a4 = 0;
  LODWORD(cb) = 0;
  *a3 = 0;
  if ( (unsigned int)GetPersistedRegistryLocationW(a1, a2, 0, 0) == 234 )
  {
    v8 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)cb);
    v15 = v8;
    v9 = v8;
    if ( !v8 )
    {
      v10 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
        (const char *)0x8007000ELL,
        (int)&cb);
LABEL_11:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
      return v10;
    }
    if ( (unsigned int)GetPersistedRegistryLocationW(a1, a2, v8, (unsigned int)cb) )
    {
      *a4 = 0;
      v10 = 0;
      goto LABEL_11;
    }
    v15 = 0;
    *a3 = v9;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
  }
  if ( !*a3 || (v11 = 1, CompareStringOrdinal(a2, -1, *a3, -1, 1) == 2) )
    v11 = 0;
  *a4 = v11;
  return 0;
}

```

## disassembly

```asm
0x18000ae3c  mov     rax, rsp
0x18000ae3f  mov     [rax+8], rbx
0x18000ae43  mov     [rax+10h], rbp
0x18000ae47  push    rsi
0x18000ae48  push    rdi
0x18000ae49  push    r14
0x18000ae4b  sub     rsp, 30h
0x18000ae4f  mov     byte ptr [r9], 0
0x18000ae53  mov     rdi, r9
0x18000ae56  mov     dword ptr [rax+18h], 0
0x18000ae5d  lea     rax, [rax+18h]
0x18000ae61  mov     qword ptr [r8], 0
0x18000ae68  mov     rsi, r8
0x18000ae6b  xor     r8d, r8d
0x18000ae6e  mov     qword ptr [rsp+48h+bIgnoreCase], rax; int
0x18000ae73  xor     r9d, r9d
0x18000ae76  mov     rbp, rdx
0x18000ae79  mov     r14, rcx
0x18000ae7c  call    cs:__imp_GetPersistedRegistryLocationW
0x18000ae82  cmp     eax, 0EAh
0x18000ae87  jnz     short loc_18000AEF5
0x18000ae89  mov     ecx, dword ptr [rsp+48h+cb]; cb
0x18000ae8d  call    cs:__imp_CoTaskMemAlloc
0x18000ae93  mov     [rsp+48h+arg_18], rax
0x18000ae98  mov     rbx, rax
0x18000ae9b  test    rax, rax
0x18000ae9e  jnz     short loc_18000AEBE
0x18000aea0  mov     rcx, [rsp+48h]; this
0x18000aea5  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x18000aeac  mov     ebx, 8007000Eh
0x18000aeb1  lea     edx, [rax+2Dh]; void *
0x18000aeb4  mov     r9d, ebx; char *
0x18000aeb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aebc  jmp     short loc_18000AF38
0x18000aebe  mov     r9d, dword ptr [rsp+48h+cb]
0x18000aec3  mov     r8, rbx
0x18000aec6  mov     rdx, rbp
0x18000aec9  mov     qword ptr [rsp+48h+bIgnoreCase], 0
0x18000aed2  mov     rcx, r14
0x18000aed5  call    cs:__imp_GetPersistedRegistryLocationW
0x18000aedb  test    eax, eax
0x18000aedd  jnz     short loc_18000AF33
0x18000aedf  lea     rcx, [rsp+48h+arg_18]
0x18000aee4  mov     [rsp+48h+arg_18], 0
0x18000aeed  mov     [rsi], rbx
0x18000aef0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000aef5  mov     r8, [rsi]; lpString2
0x18000aef8  test    r8, r8
0x18000aefb  jz      short loc_18000AF1A
0x18000aefd  or      edx, 0FFFFFFFFh; cchCount1
0x18000af00  mov     ebx, 1
0x18000af05  mov     r9d, edx; cchCount2
0x18000af08  mov     [rsp+48h+bIgnoreCase], ebx; bIgnoreCase
0x18000af0c  mov     rcx, rbp; lpString1
0x18000af0f  call    cs:__imp_CompareStringOrdinal
0x18000af15  cmp     eax, 2
0x18000af18  jnz     short loc_18000AF1C
0x18000af1a  xor     bl, bl
0x18000af1c  mov     [rdi], bl
0x18000af1e  xor     eax, eax
0x18000af20  mov     rbx, [rsp+48h+arg_0]
0x18000af25  mov     rbp, [rsp+48h+arg_8]
0x18000af2a  add     rsp, 30h
0x18000af2e  pop     r14
0x18000af30  pop     rdi
0x18000af31  pop     rsi
0x18000af32  retn
0x18000af33  mov     byte ptr [rdi], 0
0x18000af36  xor     ebx, ebx
0x18000af38  lea     rcx, [rsp+48h+arg_18]
0x18000af3d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000af42  mov     eax, ebx
0x18000af44  jmp     short loc_18000AF20
```
