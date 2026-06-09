# NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180015030`
- end: `0x18001518e`
- name: `?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z`
- size: `350`
- prototype: `__int64 __fastcall(NgcUtils *this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014380`
- `0x180017070`
- `0x180017b4c`
- `0x18001aae8`
- `0x18001b0b4`
- `0x180022ef4`

## callees

- `0x18000b0fc`
- `0x18000b7c8`
- `0x18000b854`
- `0x18000db5c`
- `0x180014e40`
- `0x180015030`
- `0x180015314`

## string_xrefs

- `0x180015074`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180015120`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`

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
  char *v12; // rsi
  unsigned __int16 *v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // r9
  int v16; // eax
  unsigned __int16 *v18; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int64 v19; // [rsp+28h] [rbp-20h] BYREF
  unsigned __int64 v20[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]

  v20[0] = 0;
  v8 = StringCchLengthW((const unsigned __int16 *)this, 0x104u, v20);
  if ( v8 >= 0 )
  {
    v18 = v9;
    v8 = StringCchLengthW(a2, 0x104u, (unsigned __int64 *)&v18);
    if ( v8 < 0 )
    {
      v10 = 185;
      goto LABEL_3;
    }
    v19 = v11;
    v8 = StringCchLengthW(a3, 0x104u, &v19);
    if ( v8 < 0 )
    {
      v10 = 191;
      goto LABEL_3;
    }
    v12 = (char *)v18 + v19 + v20[0] + 1;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v18,
      0,
      v12);
    v13 = v18;
    if ( v18 )
    {
      v16 = StringCchCopyW(v18, (unsigned __int64)v12, (const unsigned __int16 *)this);
      v8 = v16;
      if ( v16 >= 0 )
      {
        v16 = StringCchCatW(v13, (unsigned __int64)v12, a2);
        v8 = v16;
        if ( v16 >= 0 )
        {
          v16 = StringCchCatW(v13, (unsigned __int64)v12, a3);
          v8 = v16;
          if ( v16 >= 0 )
          {
            v18 = 0;
            v8 = 0;
            *(_QWORD *)a4 = v13;
            goto LABEL_19;
          }
          v14 = 215;
        }
        else
        {
          v14 = 210;
        }
      }
      else
      {
        v14 = 205;
      }
      v15 = (unsigned int)v16;
    }
    else
    {
      v8 = -2147024882;
      v14 = 199;
      v15 = 2147942414LL;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)v15,
      (int)v18);
LABEL_19:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v18);
    return (unsigned int)v8;
  }
  v10 = 179;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
    (const char *)(unsigned int)v8,
    (int)v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180015030  push    rbp
0x180015032  push    rbx
0x180015033  push    rsi
0x180015034  push    rdi
0x180015035  push    r12
0x180015037  push    r13
0x180015039  push    r14
0x18001503b  push    r15
0x18001503d  mov     rbp, rsp
0x180015040  sub     rsp, 48h
0x180015044  mov     r14, rdx
0x180015047  mov     edi, 104h
0x18001504c  mov     r15, r8
0x18001504f  xor     r11d, r11d
0x180015052  mov     edx, edi; unsigned __int64
0x180015054  mov     [rbp+var_18], r11
0x180015058  lea     r8, [rbp+var_18]; unsigned __int64 *
0x18001505c  mov     r12, r9
0x18001505f  mov     r13, rcx
0x180015062  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180015067  mov     ebx, eax
0x180015069  test    eax, eax
0x18001506b  jns     short loc_180015088
0x18001506d  lea     edx, [rdi-51h]; void *
0x180015070  mov     rcx, [rbp+40h]; this
0x180015074  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001507b  mov     r9d, ebx; char *
0x18001507e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015083  jmp     loc_18001517B
0x180015088  lea     r8, [rbp+var_28]; unsigned __int64 *
0x18001508c  mov     [rbp+var_28], r11
0x180015090  mov     rdx, rdi; unsigned __int64
0x180015093  mov     rcx, r14; unsigned __int16 *
0x180015096  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001509b  mov     ebx, eax
0x18001509d  test    eax, eax
0x18001509f  jns     short loc_1800150A8
0x1800150a1  mov     edx, 0B9h
0x1800150a6  jmp     short loc_180015070
0x1800150a8  lea     r8, [rbp+var_20]; unsigned __int64 *
0x1800150ac  mov     [rbp+var_20], r11
0x1800150b0  mov     rdx, rdi; unsigned __int64
0x1800150b3  mov     rcx, r15; unsigned __int16 *
0x1800150b6  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800150bb  mov     ebx, eax
0x1800150bd  test    eax, eax
0x1800150bf  jns     short loc_1800150C8
0x1800150c1  mov     edx, 0BFh
0x1800150c6  jmp     short loc_180015070
0x1800150c8  mov     rdx, [rbp+var_20]
0x1800150cc  lea     rcx, [rbp+var_28]
0x1800150d0  add     rdx, [rbp+var_28]
0x1800150d4  mov     rsi, [rbp+var_18]
0x1800150d8  inc     rsi
0x1800150db  add     rsi, rdx
0x1800150de  xor     edx, edx
0x1800150e0  mov     r8, rsi
0x1800150e3  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800150e8  mov     rdi, [rbp+var_28]
0x1800150ec  test    rdi, rdi
0x1800150ef  jnz     short loc_180015100
0x1800150f1  mov     ebx, 8007000Eh
0x1800150f6  mov     edx, 0C7h
0x1800150fb  mov     r9d, ebx
0x1800150fe  jmp     short loc_18001511C
0x180015100  mov     r8, r13; unsigned __int16 *
0x180015103  mov     rdx, rsi; unsigned __int64
0x180015106  mov     rcx, rdi; unsigned __int16 *
0x180015109  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001510e  mov     ebx, eax
0x180015110  test    eax, eax
0x180015112  jns     short loc_18001512E
0x180015114  mov     edx, 0CDh; void *
0x180015119  mov     r9d, eax; char *
0x18001511c  mov     rcx, [rbp+40h]; this
0x180015120  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180015127  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001512c  jmp     short loc_180015172
0x18001512e  mov     r8, r14; unsigned __int16 *
0x180015131  mov     rdx, rsi; unsigned __int64
0x180015134  mov     rcx, rdi; unsigned __int16 *
0x180015137  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001513c  mov     ebx, eax
0x18001513e  test    eax, eax
0x180015140  jns     short loc_180015149
0x180015142  mov     edx, 0D2h
0x180015147  jmp     short loc_180015119
0x180015149  mov     r8, r15; unsigned __int16 *
0x18001514c  mov     rdx, rsi; unsigned __int64
0x18001514f  mov     rcx, rdi; unsigned __int16 *
0x180015152  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015157  mov     ebx, eax
0x180015159  test    eax, eax
0x18001515b  jns     short loc_180015164
0x18001515d  mov     edx, 0D7h
0x180015162  jmp     short loc_180015119
0x180015164  mov     [rbp+var_28], 0
0x18001516c  xor     ebx, ebx
0x18001516e  mov     [r12], rdi
0x180015172  lea     rcx, [rbp+var_28]
0x180015176  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001517b  mov     eax, ebx
0x18001517d  add     rsp, 48h
0x180015181  pop     r15
0x180015183  pop     r14
0x180015185  pop     r13
0x180015187  pop     r12
0x180015189  pop     rdi
0x18001518a  pop     rsi
0x18001518b  pop     rbx
0x18001518c  pop     rbp
0x18001518d  retn
```
