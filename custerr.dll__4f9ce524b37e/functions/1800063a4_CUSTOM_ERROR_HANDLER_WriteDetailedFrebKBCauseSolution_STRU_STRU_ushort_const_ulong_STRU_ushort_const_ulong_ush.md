# CUSTOM_ERROR_HANDLER::WriteDetailedFrebKBCauseSolution(STRU *,STRU *,ushort const *,ulong,STRU *,ushort const *,ulong,ushort const *,ulong,STRU *)

- ea: `0x1800063a4`
- end: `0x180006506`
- name: `?WriteDetailedFrebKBCauseSolution@CUSTOM_ERROR_HANDLER@@AEAAJPEAVSTRU@@0PEBGK01K1K0@Z`
- size: `354`
- prototype: `__int64 __fastcall(CUSTOM_ERROR_HANDLER *__hidden this, struct STRU *, struct STRU *, const unsigned __int16 *, unsigned int, struct STRU *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, struct STRU *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005988`

## callees

- `0x1800063a4`

## import_xrefs

- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x18000641f`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x18000649a`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x1800064d6`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x18000641f`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x18000649a`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x1800064d6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006430`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000643c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006430`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000643c`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800063f8`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800063f8`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180006462`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180006472`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180006462`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180006472`
- `iisutil!SAFE_snwprintf` at `0x18000644f`
- `iisutil!SAFE_snwprintf` at `0x1800064af`
- `iisutil!SAFE_snwprintf` at `0x1800064f3`
- `iisutil!SAFE_snwprintf` at `0x18000644f`
- `iisutil!SAFE_snwprintf` at `0x1800064af`
- `iisutil!SAFE_snwprintf` at `0x1800064f3`

## pseudocode

```c
int __fastcall CUSTOM_ERROR_HANDLER::WriteDetailedFrebKBCauseSolution(
        const char **this,
        struct STRU *a2,
        struct STRU *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        struct STRU *a6,
        const unsigned __int16 *a7,
        unsigned int a8,
        const unsigned __int16 *a9,
        unsigned int a10,
        struct STRU *a11)
{
  int result; // eax
  unsigned __int16 *Str; // rbx
  unsigned __int16 *v17; // rax
  const unsigned __int16 *v18; // [rsp+30h] [rbp-28h] BYREF
  const unsigned __int16 *v19; // [rsp+38h] [rbp-20h] BYREF
  const unsigned __int16 *v20; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v21; // [rsp+98h] [rbp+40h] BYREF

  v18 = 0;
  a8 = 0;
  v19 = 0;
  a10 = 0;
  v20 = 0;
  v21 = 0;
  if ( !a2 || STRU::IsEmpty(a2) )
  {
    STRU::Reset(a3);
  }
  else
  {
    result = LANG_STRING::GetString((LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString, 0x2F90u, this[4], &v18, &a8);
    if ( result < 0 )
      return result;
    Str = STRU::QueryStr(a2);
    v17 = STRU::QueryStr(a2);
    result = SAFE_snwprintf(a3, v18, v17, Str);
    if ( result < 0 )
      return result;
  }
  if ( a5 == 1 )
  {
    STRU::Reset(a6);
LABEL_11:
    result = LANG_STRING::GetString((LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString, 0x2F8Fu, this[4], &v20, &v21);
    if ( result >= 0 )
      return SAFE_snwprintf(a11, v20, a7, a9);
    return result;
  }
  result = LANG_STRING::GetString((LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString, 0x2F8Eu, this[4], &v19, &a10);
  if ( result >= 0 )
  {
    result = SAFE_snwprintf(a6, v19, a4);
    if ( result >= 0 )
      goto LABEL_11;
  }
  return result;
}

```

## disassembly

```asm
0x1800063a4  push    rbp
0x1800063a6  push    rbx
0x1800063a7  push    rsi
0x1800063a8  push    rdi
0x1800063a9  push    r14
0x1800063ab  push    r15
0x1800063ad  mov     rbp, rsp
0x1800063b0  sub     rsp, 58h
0x1800063b4  mov     [rbp+var_28], 0
0x1800063bc  mov     r15, r9
0x1800063bf  mov     [rbp+arg_38], 0
0x1800063c6  mov     r14, r8
0x1800063c9  mov     [rbp+var_20], 0
0x1800063d1  mov     rdi, rdx
0x1800063d4  mov     [rbp+arg_48], 0
0x1800063de  mov     rsi, rcx
0x1800063e1  mov     [rbp+var_18], 0
0x1800063e9  mov     [rbp+arg_8], 0
0x1800063f0  test    rdx, rdx
0x1800063f3  jz      short loc_18000645F
0x1800063f5  mov     rcx, rdx
0x1800063f8  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x1800063fe  test    al, al
0x180006400  jnz     short loc_18000645F
0x180006402  mov     r8, [rsi+20h]
0x180006406  lea     rax, [rbp+arg_38]
0x18000640a  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x180006411  lea     r9, [rbp+var_28]
0x180006415  mov     edx, 2F90h
0x18000641a  mov     [rsp+58h+var_38], rax
0x18000641f  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x180006425  test    eax, eax
0x180006427  js      loc_1800064F9
0x18000642d  mov     rcx, rdi
0x180006430  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180006436  mov     rcx, rdi
0x180006439  mov     rbx, rax
0x18000643c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180006442  mov     rdx, [rbp+var_28]
0x180006446  mov     r9, rbx
0x180006449  mov     r8, rax
0x18000644c  mov     rcx, r14
0x18000644f  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180006455  test    eax, eax
0x180006457  js      loc_1800064F9
0x18000645d  jmp     short loc_180006468
0x18000645f  mov     rcx, r14
0x180006462  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x180006468  cmp     [rbp+arg_20], 1
0x18000646c  jnz     short loc_18000647A
0x18000646e  mov     rcx, [rbp+arg_28]
0x180006472  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x180006478  jmp     short loc_1800064B9
0x18000647a  mov     r8, [rsi+20h]
0x18000647e  lea     rax, [rbp+arg_48]
0x180006485  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x18000648c  lea     r9, [rbp+var_20]
0x180006490  mov     edx, 2F8Eh
0x180006495  mov     [rsp+58h+var_38], rax
0x18000649a  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x1800064a0  test    eax, eax
0x1800064a2  js      short loc_1800064F9
0x1800064a4  mov     rdx, [rbp+var_20]
0x1800064a8  mov     r8, r15
0x1800064ab  mov     rcx, [rbp+arg_28]
0x1800064af  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x1800064b5  test    eax, eax
0x1800064b7  js      short loc_1800064F9
0x1800064b9  mov     r8, [rsi+20h]
0x1800064bd  lea     rax, [rbp+arg_8]
0x1800064c1  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x1800064c8  lea     r9, [rbp+var_18]
0x1800064cc  mov     edx, 2F8Fh
0x1800064d1  mov     [rsp+58h+var_38], rax
0x1800064d6  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x1800064dc  test    eax, eax
0x1800064de  js      short loc_1800064F9
0x1800064e0  mov     r9, [rbp+arg_40]
0x1800064e4  mov     r8, [rbp+arg_30]
0x1800064e8  mov     rdx, [rbp+var_18]
0x1800064ec  mov     rcx, [rbp+arg_50]
0x1800064f3  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x1800064f9  add     rsp, 58h
0x1800064fd  pop     r15
0x1800064ff  pop     r14
0x180006501  pop     rdi
0x180006502  pop     rsi
0x180006503  pop     rbx
0x180006504  pop     rbp
0x180006505  retn
```
