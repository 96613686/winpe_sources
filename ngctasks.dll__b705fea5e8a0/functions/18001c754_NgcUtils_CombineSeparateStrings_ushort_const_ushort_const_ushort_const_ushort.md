# NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x18001c754`
- end: `0x18001c8b6`
- name: `?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z`
- size: `354`
- prototype: `__int64 __fastcall(NgcUtils *this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015748`
- `0x18001c9ac`
- `0x18001d85c`

## callees

- `0x18000cc34`
- `0x18000de7c`
- `0x18000df08`
- `0x18000ff9c`
- `0x180010310`
- `0x18001c754`
- `0x18001c928`

## string_xrefs

- `0x18001c798`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x18001c844`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::CombineSeparateStrings(
        NgcUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  int v8; // ebx
  unsigned __int16 *v9; // r11
  __int64 v10; // rdx
  unsigned __int64 v11; // r11
  const char *v12; // r9
  char *v13; // rdi
  unsigned __int16 *v14; // rsi
  __int64 v15; // rdx
  __int64 v16; // r9
  int v17; // eax
  unsigned __int16 *v19; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int64 v20; // [rsp+28h] [rbp-20h] BYREF
  unsigned __int64 v21[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]

  v21[0] = 0;
  v8 = StringCchLengthW((const unsigned __int16 *)this, 0x104u, v21);
  if ( v8 >= 0 )
  {
    v19 = v9;
    v8 = StringCchLengthW(a2, 0x104u, (unsigned __int64 *)&v19);
    if ( v8 < 0 )
    {
      v10 = 185;
      goto LABEL_3;
    }
    v20 = v11;
    v8 = StringCchLengthW(a3, 0x104u, &v20);
    if ( v8 < 0 )
    {
      v10 = 191;
      goto LABEL_3;
    }
    v13 = (char *)v19 + v20 + v21[0] + 1;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v19,
      0,
      (unsigned __int64)v13,
      v12);
    v14 = v19;
    if ( v19 )
    {
      v17 = StringCchCopyW(v19, (unsigned __int64)v13, (const unsigned __int16 *)this);
      v8 = v17;
      if ( v17 >= 0 )
      {
        v17 = StringCchCatW(v14, (unsigned __int64)v13, a2);
        v8 = v17;
        if ( v17 >= 0 )
        {
          v17 = StringCchCatW(v14, (unsigned __int64)v13, a3);
          v8 = v17;
          if ( v17 >= 0 )
          {
            v8 = 0;
            *(_QWORD *)a4 = v19;
            v19 = 0;
            goto LABEL_19;
          }
          v15 = 215;
        }
        else
        {
          v15 = 210;
        }
      }
      else
      {
        v15 = 205;
      }
      v16 = (unsigned int)v17;
    }
    else
    {
      v8 = -2147024882;
      v15 = 199;
      v16 = 2147942414LL;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)v16,
      (int)v19);
LABEL_19:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v19);
    return (unsigned int)v8;
  }
  v10 = 179;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
    (const char *)(unsigned int)v8,
    (int)v19);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001c754  push    rbp
0x18001c756  push    rbx
0x18001c757  push    rsi
0x18001c758  push    rdi
0x18001c759  push    r12
0x18001c75b  push    r13
0x18001c75d  push    r14
0x18001c75f  push    r15
0x18001c761  mov     rbp, rsp
0x18001c764  sub     rsp, 48h
0x18001c768  mov     r14, rdx
0x18001c76b  mov     edi, 104h
0x18001c770  mov     r15, r8
0x18001c773  xor     r11d, r11d
0x18001c776  mov     edx, edi; unsigned __int64
0x18001c778  mov     [rbp+var_18], r11
0x18001c77c  lea     r8, [rbp+var_18]; unsigned __int64 *
0x18001c780  mov     r12, r9
0x18001c783  mov     r13, rcx
0x18001c786  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001c78b  mov     ebx, eax
0x18001c78d  test    eax, eax
0x18001c78f  jns     short loc_18001C7AC
0x18001c791  lea     edx, [rdi-51h]; void *
0x18001c794  mov     rcx, [rbp+40h]; this
0x18001c798  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001c79f  mov     r9d, ebx; char *
0x18001c7a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c7a7  jmp     loc_18001C8A3
0x18001c7ac  lea     r8, [rbp+var_28]; unsigned __int64 *
0x18001c7b0  mov     [rbp+var_28], r11
0x18001c7b4  mov     rdx, rdi; unsigned __int64
0x18001c7b7  mov     rcx, r14; unsigned __int16 *
0x18001c7ba  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001c7bf  mov     ebx, eax
0x18001c7c1  test    eax, eax
0x18001c7c3  jns     short loc_18001C7CC
0x18001c7c5  mov     edx, 0B9h
0x18001c7ca  jmp     short loc_18001C794
0x18001c7cc  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18001c7d0  mov     [rbp+var_20], r11
0x18001c7d4  mov     rdx, rdi; unsigned __int64
0x18001c7d7  mov     rcx, r15; unsigned __int16 *
0x18001c7da  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001c7df  mov     ebx, eax
0x18001c7e1  test    eax, eax
0x18001c7e3  jns     short loc_18001C7EC
0x18001c7e5  mov     edx, 0BFh
0x18001c7ea  jmp     short loc_18001C794
0x18001c7ec  mov     rdx, [rbp+var_20]
0x18001c7f0  lea     rcx, [rbp+var_28]
0x18001c7f4  add     rdx, [rbp+var_28]
0x18001c7f8  mov     rdi, [rbp+var_18]
0x18001c7fc  inc     rdi
0x18001c7ff  add     rdi, rdx
0x18001c802  xor     edx, edx
0x18001c804  mov     r8, rdi
0x18001c807  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001c80c  mov     rsi, [rbp+var_28]
0x18001c810  test    rsi, rsi
0x18001c813  jnz     short loc_18001C824
0x18001c815  mov     ebx, 8007000Eh
0x18001c81a  mov     edx, 0C7h
0x18001c81f  mov     r9d, ebx
0x18001c822  jmp     short loc_18001C840
0x18001c824  mov     r8, r13; unsigned __int16 *
0x18001c827  mov     rdx, rdi; unsigned __int64
0x18001c82a  mov     rcx, rsi; unsigned __int16 *
0x18001c82d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c832  mov     ebx, eax
0x18001c834  test    eax, eax
0x18001c836  jns     short loc_18001C852
0x18001c838  mov     edx, 0CDh; void *
0x18001c83d  mov     r9d, eax; char *
0x18001c840  mov     rcx, [rbp+40h]; this
0x18001c844  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001c84b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c850  jmp     short loc_18001C89A
0x18001c852  mov     r8, r14; unsigned __int16 *
0x18001c855  mov     rdx, rdi; unsigned __int64
0x18001c858  mov     rcx, rsi; unsigned __int16 *
0x18001c85b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001c860  mov     ebx, eax
0x18001c862  test    eax, eax
0x18001c864  jns     short loc_18001C86D
0x18001c866  mov     edx, 0D2h
0x18001c86b  jmp     short loc_18001C83D
0x18001c86d  mov     r8, r15; unsigned __int16 *
0x18001c870  mov     rdx, rdi; unsigned __int64
0x18001c873  mov     rcx, rsi; unsigned __int16 *
0x18001c876  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001c87b  mov     ebx, eax
0x18001c87d  test    eax, eax
0x18001c87f  jns     short loc_18001C888
0x18001c881  mov     edx, 0D7h
0x18001c886  jmp     short loc_18001C83D
0x18001c888  mov     rax, [rbp+var_28]
0x18001c88c  xor     ebx, ebx
0x18001c88e  mov     [r12], rax
0x18001c892  mov     [rbp+var_28], 0
0x18001c89a  lea     rcx, [rbp+var_28]
0x18001c89e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001c8a3  mov     eax, ebx
0x18001c8a5  add     rsp, 48h
0x18001c8a9  pop     r15
0x18001c8ab  pop     r14
0x18001c8ad  pop     r13
0x18001c8af  pop     r12
0x18001c8b1  pop     rdi
0x18001c8b2  pop     rsi
0x18001c8b3  pop     rbx
0x18001c8b4  pop     rbp
0x18001c8b5  retn
```
