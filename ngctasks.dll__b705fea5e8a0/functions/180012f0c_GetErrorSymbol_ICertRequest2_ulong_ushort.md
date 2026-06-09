# GetErrorSymbol(ICertRequest2 *,ulong,ushort * *)

- ea: `0x180012f0c`
- end: `0x180012fe8`
- name: `?GetErrorSymbol@@YAXPEAUICertRequest2@@KPEAPEAG@Z`
- size: `220`
- prototype: `void __fastcall(struct ICertRequest2 *, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013310`

## callees

- `0x18000ebc0`
- `0x180012f0c`
- `0x18001c8bc`
- `0x180022010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180012f59`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180012f59`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180012fbf`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180012fbf`
- `OLEAUT32!__imp_SysFreeString` at `0x180012fd2`
- `OLEAUT32!__imp_SysFreeString` at `0x180012fd2`

## string_xrefs

- `0x180012fa4`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
void __fastcall GetErrorSymbol(struct ICertRequest2 *a1, __int64 a2, unsigned __int16 **a3)
{
  wchar_t *v4; // rax
  unsigned __int16 **v5; // r8
  const char *v6; // r9
  NgcUtils *v7; // rax
  NgcUtils *v8; // rcx
  __int16 i; // dx
  int v10; // eax
  wchar_t *v11; // rax
  wchar_t *Str; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a3 = 0;
  Str = 0;
  if ( (_DWORD)a2 )
  {
    if ( a1 )
    {
      if ( !((unsigned int (__fastcall *)(struct ICertRequest2 *, __int64, __int64, wchar_t **))a1->lpVtbl->GetErrorMessageText)(
              a1,
              a2,
              1,
              &Str) )
      {
        v4 = wcsrchr(Str, 0x28u);
        if ( v4 )
        {
          v7 = (NgcUtils *)(v4 + 1);
          v8 = v7;
          for ( i = *(_WORD *)v7; i && i != 41; i = *(_WORD *)v8 )
          {
            v8 = (NgcUtils *)((char *)v8 + 2);
            if ( i == 32 )
              v7 = v8;
          }
          v10 = NgcUtils::DuplicateString(v7, (unsigned __int16 *)a3, v5, v6);
          if ( v10 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x3B4,
              (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
              (const char *)(unsigned int)v10);
          if ( *a3 )
          {
            v11 = wcschr(*a3, 0x29u);
            if ( v11 )
              *v11 = 0;
          }
        }
      }
    }
  }
  SysFreeString(Str);
}

```

## disassembly

```asm
0x180012f0c  mov     r11, rsp
0x180012f0f  mov     [r11+8], rbx
0x180012f13  mov     [r11+10h], rsi
0x180012f17  push    rdi
0x180012f18  sub     rsp, 40h
0x180012f1c  mov     rbx, r8
0x180012f1f  xor     edi, edi
0x180012f21  mov     [r8], rdi
0x180012f24  mov     [r11-18h], rdi
0x180012f28  test    edx, edx
0x180012f2a  jz      loc_180012FCD
0x180012f30  test    rcx, rcx
0x180012f33  jz      loc_180012FCD
0x180012f39  mov     rax, [rcx]
0x180012f3c  lea     r9, [r11-18h]
0x180012f40  lea     r8d, [rdi+1]
0x180012f44  mov     rax, [rax+78h]
0x180012f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f4d  test    eax, eax
0x180012f4f  jnz     short loc_180012FCD
0x180012f51  lea     edx, [rdi+28h]; Ch
0x180012f54  mov     rcx, [rsp+48h+Str]; Str
0x180012f59  call    cs:__imp_wcsrchr
0x180012f5f  test    rax, rax
0x180012f62  jz      short loc_180012FCD
0x180012f64  add     rax, 2
0x180012f68  mov     rcx, rax
0x180012f6b  movzx   edx, word ptr [rax]
0x180012f6e  lea     esi, [rdi+29h]
0x180012f71  jmp     short loc_180012F88
0x180012f73  cmp     dx, si
0x180012f76  jz      short loc_180012F8D
0x180012f78  add     rcx, 2
0x180012f7c  cmp     dx, 20h ; ' '
0x180012f80  jnz     short loc_180012F85
0x180012f82  mov     rax, rcx
0x180012f85  movzx   edx, word ptr [rcx]
0x180012f88  test    dx, dx
0x180012f8b  jnz     short loc_180012F73
0x180012f8d  mov     rdx, rbx; unsigned __int16 *
0x180012f90  mov     rcx, rax; this
0x180012f93  call    ?DuplicateString@NgcUtils@@YAJPEBGPEAPEAG@Z; NgcUtils::DuplicateString(ushort const *,ushort * *)
0x180012f98  mov     rcx, [rsp+48h]; this
0x180012f9d  test    eax, eax
0x180012f9f  jns     short loc_180012FB5
0x180012fa1  mov     r9d, eax; char *
0x180012fa4  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180012fab  mov     edx, 3B4h; void *
0x180012fb0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012fb5  mov     rcx, [rbx]; Str
0x180012fb8  test    rcx, rcx
0x180012fbb  jz      short loc_180012FCD
0x180012fbd  mov     edx, esi; Ch
0x180012fbf  call    cs:__imp_wcschr
0x180012fc5  test    rax, rax
0x180012fc8  jz      short loc_180012FCD
0x180012fca  mov     [rax], di
0x180012fcd  mov     rcx, [rsp+48h+Str]; bstrString
0x180012fd2  call    cs:__imp_SysFreeString
0x180012fd8  mov     rbx, [rsp+48h+arg_0]
0x180012fdd  mov     rsi, [rsp+48h+arg_8]
0x180012fe2  add     rsp, 40h
0x180012fe6  pop     rdi
0x180012fe7  retn
```
