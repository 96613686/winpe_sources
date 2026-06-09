# IIS_MODULE::GetString(uint,ushort const * *,ulong *)

- ea: `0x18000bd94`
- end: `0x18000be15`
- name: `?GetString@IIS_MODULE@@AEAAJIPEAPEBGPEAK@Z`
- size: `129`
- prototype: `__int64 __fastcall(IIS_MODULE *__hidden this, unsigned int, const unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bb5c`
- `0x18000d370`

## callees

- `0x18000bd94`
- `0x180010010`

## import_xrefs

- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x18000be06`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x18000be06`

## pseudocode

```c
int __fastcall IIS_MODULE::GetString(IIS_MODULE *this, unsigned int a2, const unsigned __int16 **a3, unsigned int *a4)
{
  __int64 v4; // rcx
  const char *v5; // rbx
  __int64 v9; // rax
  unsigned __int16 v11; // [rsp+60h] [rbp+8h] BYREF

  v4 = *((_QWORD *)this + 21);
  v5 = 0;
  v11 = 0;
  if ( v4 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 24LL))(v4);
    if ( v9 )
      v5 = (const char *)(*(__int64 (__fastcall **)(__int64, const char *, unsigned __int16 *))(*(_QWORD *)v9 + 24LL))(
                           v9,
                           "Accept-Language",
                           &v11);
  }
  return LANG_STRING::GetString(*(LANG_STRING **)&g_pLangString, v5, v11, a2, a3, a4);
}

```

## disassembly

```asm
0x18000bd94  push    rbx
0x18000bd96  push    rbp
0x18000bd97  push    rsi
0x18000bd98  push    rdi
0x18000bd99  sub     rsp, 38h
0x18000bd9d  mov     rcx, [rcx+0A8h]
0x18000bda4  xor     eax, eax
0x18000bda6  xor     ebx, ebx
0x18000bda8  mov     [rsp+58h+arg_0], ax
0x18000bdad  mov     rdi, r9
0x18000bdb0  mov     rsi, r8
0x18000bdb3  mov     ebp, edx
0x18000bdb5  test    rcx, rcx
0x18000bdb8  jz      short loc_18000BDE9
0x18000bdba  mov     rax, [rcx]
0x18000bdbd  mov     rax, [rax+18h]
0x18000bdc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdc6  mov     rcx, rax
0x18000bdc9  test    rax, rax
0x18000bdcc  jz      short loc_18000BDE9
0x18000bdce  mov     rax, [rax]
0x18000bdd1  lea     r8, [rsp+58h+arg_0]
0x18000bdd6  lea     rdx, aAcceptLanguage; "Accept-Language"
0x18000bddd  mov     rax, [rax+18h]
0x18000bde1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bde6  mov     rbx, rax
0x18000bde9  movzx   r8d, [rsp+58h+arg_0]
0x18000bdef  mov     r9d, ebp
0x18000bdf2  mov     rcx, cs:?g_pLangString@@3PEAVLANG_STRING@@EA; LANG_STRING * g_pLangString
0x18000bdf9  mov     rdx, rbx
0x18000bdfc  mov     [rsp+58h+var_30], rdi
0x18000be01  mov     [rsp+58h+var_38], rsi
0x18000be06  call    cs:__imp_?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z; LANG_STRING::GetString(char const *,ulong,uint,ushort const * *,ulong *)
0x18000be0c  add     rsp, 38h
0x18000be10  pop     rdi
0x18000be11  pop     rsi
0x18000be12  pop     rbp
0x18000be13  pop     rbx
0x18000be14  retn
```
