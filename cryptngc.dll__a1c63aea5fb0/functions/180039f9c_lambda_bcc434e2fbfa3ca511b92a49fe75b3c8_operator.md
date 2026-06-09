# _lambda_bcc434e2fbfa3ca511b92a49fe75b3c8_::operator()

- ea: `0x180039f9c`
- end: `0x18003a0ad`
- name: `_lambda_bcc434e2fbfa3ca511b92a49fe75b3c8_::operator()`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180038e24`

## callees

- `0x180006538`
- `0x18000ea60`
- `0x18000f280`
- `0x180018790`
- `0x180039f9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18003a026`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18003a026`
- `ntdll!RtlIsMultiSessionSku` at `0x18003a02f`
- `ntdll!RtlIsMultiSessionSku` at `0x18003a02f`

## string_xrefs

- `0x180039fc9`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x18003a06e`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
__int64 __fastcall lambda_bcc434e2fbfa3ca511b92a49fe75b3c8_::operator()(__int64 **a1)
{
  __int64 v2; // rdx
  __int64 v3; // rdx
  unsigned int v4; // ebx
  __int64 v5; // rbx
  wchar_t *v6; // rbp
  __int64 v7; // rdx
  __int64 v8; // r9
  unsigned __int16 *v9; // rsi
  int v10; // eax
  wchar_t ***v11; // rax
  int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  wchar_t *Str; // [rsp+40h] [rbp+8h] BYREF

  v2 = **a1;
  if ( v2 )
  {
    if ( !*a1[1] )
    {
      v3 = 1578;
      goto LABEL_3;
    }
    v5 = -1;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &Str,
      v2,
      -1);
    v6 = Str;
    if ( Str )
    {
      v9 = wcsstr(Str, L"CA00CFA8-EB0F-42BA-A707-A3A43CDA5BD9");
      if ( !(unsigned __int8)RtlIsMultiSessionSku() || !v9 )
        goto LABEL_14;
      do
        ++v5;
      while ( v9[v5] );
      v10 = StringCchCopyW(v9, v5 + 1, L"9DDC52DB-DC02-4A8C-B892-38DEF4FA748F");
      v4 = v10;
      if ( v10 >= 0 )
      {
LABEL_14:
        v11 = (wchar_t ***)a1[1];
        v4 = 0;
        Str = 0;
        **v11 = v6;
        goto LABEL_15;
      }
      v8 = (unsigned int)v10;
      v7 = 1591;
    }
    else
    {
      v4 = -2147024882;
      v7 = 1581;
      v8 = 2147942414LL;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)v8,
      v13);
LABEL_15:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Str);
    return v4;
  }
  v3 = 1577;
LABEL_3:
  v4 = -2146893785;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
    (const char *)0x80090027LL,
    v13);
  return v4;
}

```

## disassembly

```asm
0x180039f9c  mov     [rsp+arg_8], rbx
0x180039fa1  mov     [rsp+arg_10], rbp
0x180039fa6  push    rsi
0x180039fa7  push    rdi
0x180039fa8  push    r14; int
0x180039faa  sub     rsp, 20h
0x180039fae  mov     rax, [rcx]
0x180039fb1  xor     r14d, r14d
0x180039fb4  mov     rdi, rcx
0x180039fb7  mov     rdx, [rax]
0x180039fba  test    rdx, rdx
0x180039fbd  jnz     short loc_180039FE2
0x180039fbf  mov     edx, 629h; void *
0x180039fc4  mov     rcx, [rsp+38h]; this
0x180039fc9  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180039fd0  mov     ebx, 80090027h
0x180039fd5  mov     r9d, ebx; char *
0x180039fd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039fdd  jmp     loc_18003A098
0x180039fe2  mov     rax, [rcx+8]
0x180039fe6  cmp     [rax], r14
0x180039fe9  jnz     short loc_180039FF2
0x180039feb  mov     edx, 62Ah
0x180039ff0  jmp     short loc_180039FC4
0x180039ff2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180039ff6  lea     rcx, [rsp+38h+Str]
0x180039ffb  mov     r8, rbx
0x180039ffe  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003a003  mov     rbp, [rsp+38h+Str]
0x18003a008  test    rbp, rbp
0x18003a00b  jnz     short loc_18003A01C
0x18003a00d  mov     ebx, 8007000Eh
0x18003a012  mov     edx, 62Dh
0x18003a017  mov     r9d, ebx
0x18003a01a  jmp     short loc_18003A069
0x18003a01c  lea     rdx, aCa00cfa8Eb0f42; "CA00CFA8-EB0F-42BA-A707-A3A43CDA5BD9"
0x18003a023  mov     rcx, rbp; Str
0x18003a026  call    cs:__imp_wcsstr
0x18003a02c  mov     rsi, rax
0x18003a02f  call    cs:__imp_RtlIsMultiSessionSku
0x18003a035  test    al, al
0x18003a037  jz      short loc_18003A07C
0x18003a039  test    rsi, rsi
0x18003a03c  jz      short loc_18003A07C
0x18003a03e  inc     rbx
0x18003a041  cmp     [rsi+rbx*2], r14w
0x18003a046  jnz     short loc_18003A03E
0x18003a048  lea     rdx, [rbx+1]; unsigned __int64
0x18003a04c  mov     rcx, rsi; unsigned __int16 *
0x18003a04f  lea     r8, a9ddc52dbDc024a; "9DDC52DB-DC02-4A8C-B892-38DEF4FA748F"
0x18003a056  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003a05b  mov     ebx, eax
0x18003a05d  test    eax, eax
0x18003a05f  jns     short loc_18003A07C
0x18003a061  mov     r9d, eax; char *
0x18003a064  mov     edx, 637h; void *
0x18003a069  mov     rcx, [rsp+38h]; this
0x18003a06e  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18003a075  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a07a  jmp     short loc_18003A08E
0x18003a07c  mov     rax, [rdi+8]
0x18003a080  mov     ebx, r14d
0x18003a083  mov     [rsp+38h+Str], r14
0x18003a088  mov     rcx, [rax]
0x18003a08b  mov     [rcx], rbp
0x18003a08e  lea     rcx, [rsp+38h+Str]; void *
0x18003a093  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18003a098  mov     rbp, [rsp+38h+arg_10]
0x18003a09d  mov     eax, ebx
0x18003a09f  mov     rbx, [rsp+38h+arg_8]
0x18003a0a4  add     rsp, 20h
0x18003a0a8  pop     r14
0x18003a0aa  pop     rdi
0x18003a0ab  pop     rsi
0x18003a0ac  retn
```
