# CCalcFileName::PrefetchData(void)

- ea: `0x18001bd70`
- end: `0x18001bfb3`
- name: `?PrefetchData@CCalcFileName@@UEAAJXZ`
- size: `579`
- prototype: `__int64 __fastcall(CCalcFileName *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001bd70`
- `0x18001bfbc`
- `0x18006ed20`
- `0x18006fb98`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18001bf48`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18001bf48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bdcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bdcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bdff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bdff`
- `SHCORE!__imp_StrRetToStrW` at `0x18001bf33`
- `SHCORE!__imp_StrRetToStrW` at `0x18001bf33`

## pseudocode

```c
__int64 __fastcall CCalcFileName::PrefetchData(CCalcFileName *this)
{
  __int64 v2; // rcx
  HRESULT v3; // ebx
  _WORD *v5; // rax
  _WORD *v6; // rdx
  unsigned __int64 v7; // r8
  __int64 v8; // rcx
  LPWSTR FileNameW; // r14
  unsigned __int64 v10; // rdi
  __int64 v11; // r9
  _WORD *v12; // rcx
  __int64 v13; // rsi
  bool v14; // cf
  const ITEMIDLIST *v15; // rsi
  __int64 v16; // rbx
  _QWORD *v17; // rbx
  unsigned __int64 v18; // rsi
  LPVOID pv; // [rsp+38h] [rbp-150h] BYREF
  int v20[4]; // [rsp+40h] [rbp-148h] BYREF
  STRRET pstr; // [rsp+50h] [rbp-138h] BYREF

  v2 = *((_QWORD *)this + 3);
  v20[0] = 0x40000000;
  if ( v2
    && *((_QWORD *)this + 4)
    && (*(int (__fastcall **)(__int64, __int64, char *, int *))(*(_QWORD *)v2 + 72LL))(v2, 1, (char *)this + 32, v20) >= 0
    && (v20[0] & 0x40000000) != 0 )
  {
    v15 = (const ITEMIDLIST *)*((_QWORD *)this + 4);
    v16 = *((_QWORD *)this + 3);
    pv = 0;
    memset_0(&pstr, 0, sizeof(pstr));
    v3 = (*(__int64 (__fastcall **)(__int64, const ITEMIDLIST *, __int64, STRRET *))(*(_QWORD *)v16 + 88LL))(
           v16,
           v15,
           0x8000,
           &pstr);
    if ( v3 >= 0 )
      v3 = StrRetToStrW(&pstr, v15, (LPWSTR *)&pv);
    if ( v3 >= 0 )
    {
      FileNameW = PathFindFileNameW((LPCWSTR)pv);
      if ( FileNameW )
      {
        v17 = (_QWORD *)((char *)this + 72);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 72);
        v10 = -1;
        v17[1] = -1;
        v17[2] = -1;
        do
          ++v10;
        while ( FileNameW[v10] );
        v18 = v10 + 1;
        *v17 = 0;
        if ( v10 + 1 >= v10 && is_mul_ok(v18, 2u) )
        {
          v5 = CoTaskMemAlloc(2 * v18);
          *v17 = v5;
          v6 = v5;
          v3 = v5 == 0 ? 0x8007000E : 0;
          if ( v5 )
          {
            if ( v18 > 0x7FFFFFFF )
              goto LABEL_34;
            if ( v10 < 0x7FFFFFFF )
            {
              v7 = v10 + 1;
              v8 = 0;
              do
              {
                if ( !v10 )
                  break;
                if ( !*FileNameW )
                  break;
                *v5++ = *FileNameW++;
                --v10;
                ++v8;
                --v7;
              }
              while ( v7 );
              v11 = v8 - 1;
              if ( v7 )
                v11 = v8;
              v12 = v5 - 1;
              if ( v7 )
                v12 = v5;
              *v12 = 0;
              if ( v7 )
              {
                v14 = v18 == v11;
                v13 = v18 - v11;
                if ( !v14 && v13 != 1 && (unsigned __int64)(2 * v13) > 2 )
                  memset_0(&v6[v11 + 1], 0, 2 * v13 - 2);
              }
              goto LABEL_5;
            }
            if ( v10 != -1 )
LABEL_34:
              *v5 = 0;
          }
        }
        else
        {
          v3 = -2147024362;
        }
      }
LABEL_5:
      CoTaskMemFree(pv);
    }
  }
  else
  {
    return 1;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001bd70  mov     [rsp+arg_8], rbx
0x18001bd75  mov     [rsp+arg_10], rbp
0x18001bd7a  push    rsi
0x18001bd7b  push    rdi
0x18001bd7c  push    r14
0x18001bd7e  sub     rsp, 170h
0x18001bd85  mov     rax, cs:__security_cookie
0x18001bd8c  xor     rax, rsp
0x18001bd8f  mov     [rsp+188h+var_28], rax
0x18001bd97  mov     rdi, rcx
0x18001bd9a  xor     ebp, ebp
0x18001bd9c  mov     rcx, [rcx+18h]
0x18001bda0  mov     esi, 40000000h
0x18001bda5  mov     [rsp+188h+var_148], esi
0x18001bda9  test    rcx, rcx
0x18001bdac  jz      short loc_18001BDBB
0x18001bdae  lea     rbx, [rdi+20h]
0x18001bdb2  cmp     [rbx], rbp
0x18001bdb5  jnz     loc_18001BEBA
0x18001bdbb  mov     ebx, 1
0x18001bdc0  jmp     short loc_18001BDD2
0x18001bdc2  mov     ebx, 80070216h
0x18001bdc7  mov     rcx, [rsp+188h+pv]; pv
0x18001bdcc  call    cs:__imp_CoTaskMemFree
0x18001bdd2  mov     eax, ebx
0x18001bdd4  mov     rcx, [rsp+188h+var_28]
0x18001bddc  xor     rcx, rsp; StackCookie
0x18001bddf  call    __security_check_cookie
0x18001bde4  lea     r11, [rsp+188h+var_18]
0x18001bdec  mov     rbx, [r11+28h]
0x18001bdf0  mov     rbp, [r11+30h]
0x18001bdf4  mov     rsp, r11
0x18001bdf7  pop     r14
0x18001bdf9  pop     rdi
0x18001bdfa  pop     rsi
0x18001bdfb  retn
0x18001bdfc  mov     rcx, rax; cb
0x18001bdff  call    cs:__imp_CoTaskMemAlloc
0x18001be05  mov     [rbx], rax
0x18001be08  mov     rcx, rax
0x18001be0b  neg     rcx
0x18001be0e  mov     rdx, rax
0x18001be11  sbb     ebx, ebx
0x18001be13  not     ebx
0x18001be15  and     ebx, 8007000Eh
0x18001be1b  test    rax, rax
0x18001be1e  jz      short loc_18001BDC7
0x18001be20  mov     eax, 7FFFFFFFh
0x18001be25  cmp     rsi, rax
0x18001be28  ja      loc_18001BFAB
0x18001be2e  cmp     rdi, rax
0x18001be31  jnb     loc_18001BFA2
0x18001be37  test    rsi, rsi
0x18001be3a  jz      short loc_18001BDC7
0x18001be3c  mov     r8, rsi
0x18001be3f  mov     rax, rdx
0x18001be42  mov     rcx, rbp
0x18001be45  test    rdi, rdi
0x18001be48  jz      short loc_18001BE6C
0x18001be4a  movzx   r9d, word ptr [r14]
0x18001be4e  test    r9w, r9w
0x18001be52  jz      short loc_18001BE6C
0x18001be54  mov     [rax], r9w
0x18001be58  add     r14, 2
0x18001be5c  add     rax, 2
0x18001be60  dec     rdi
0x18001be63  inc     rcx
0x18001be66  sub     r8, 1
0x18001be6a  jnz     short loc_18001BE45
0x18001be6c  lea     r9, [rcx-1]
0x18001be70  test    r8, r8
0x18001be73  cmovnz  r9, rcx
0x18001be77  lea     rcx, [rax-2]
0x18001be7b  cmovnz  rcx, rax
0x18001be7f  mov     [rcx], bp
0x18001be82  jz      loc_18001BDC7
0x18001be88  sub     rsi, r9
0x18001be8b  cmp     rsi, 1
0x18001be8f  jbe     loc_18001BDC7
0x18001be95  lea     r8, [rsi+rsi]
0x18001be99  cmp     r8, 2
0x18001be9d  jbe     loc_18001BDC7
0x18001bea3  inc     r9
0x18001bea6  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18001beaa  lea     rcx, [rdx+r9*2]; void *
0x18001beae  xor     edx, edx; Val
0x18001beb0  call    memset_0
0x18001beb5  jmp     loc_18001BDC7
0x18001beba  mov     rax, [rcx]
0x18001bebd  lea     r9, [rsp+188h+var_148]
0x18001bec2  mov     r8, rbx
0x18001bec5  mov     edx, 1
0x18001beca  mov     rax, [rax+48h]
0x18001bece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bed3  test    eax, eax
0x18001bed5  js      loc_18001BDBB
0x18001bedb  test    [rsp+188h+var_148], esi
0x18001bedf  jz      loc_18001BDBB
0x18001bee5  mov     rsi, [rbx]
0x18001bee8  lea     rcx, [rsp+188h+pstr]; void *
0x18001beed  mov     rbx, [rdi+18h]
0x18001bef1  xor     edx, edx; Val
0x18001bef3  mov     r8d, 110h; Size
0x18001bef9  mov     [rsp+188h+pv], rbp
0x18001befe  call    memset_0
0x18001bf03  mov     rax, [rbx]
0x18001bf06  lea     r9, [rsp+188h+pstr]
0x18001bf0b  mov     r8d, 8000h
0x18001bf11  mov     rdx, rsi
0x18001bf14  mov     rcx, rbx
0x18001bf17  mov     rax, [rax+58h]
0x18001bf1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf20  mov     ebx, eax
0x18001bf22  test    eax, eax
0x18001bf24  js      short loc_18001BF3B
0x18001bf26  lea     r8, [rsp+188h+pv]; ppsz
0x18001bf2b  mov     rdx, rsi; pidl
0x18001bf2e  lea     rcx, [rsp+188h+pstr]; pstr
0x18001bf33  call    cs:__imp_StrRetToStrW
0x18001bf39  mov     ebx, eax
0x18001bf3b  test    ebx, ebx
0x18001bf3d  js      loc_18001BDD2
0x18001bf43  mov     rcx, [rsp+188h+pv]; pszPath
0x18001bf48  call    cs:__imp_PathFindFileNameW
0x18001bf4e  mov     r14, rax
0x18001bf51  test    rax, rax
0x18001bf54  jz      loc_18001BDC7
0x18001bf5a  lea     rbx, [rdi+48h]
0x18001bf5e  mov     rcx, rbx
0x18001bf61  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001bf66  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001bf6a  mov     [rbx+8], rdi
0x18001bf6e  mov     [rbx+10h], rdi
0x18001bf72  inc     rdi
0x18001bf75  cmp     [r14+rdi*2], bp
0x18001bf7a  jnz     short loc_18001BF72
0x18001bf7c  lea     rsi, [rdi+1]
0x18001bf80  mov     [rbx], rbp
0x18001bf83  cmp     rsi, rdi
0x18001bf86  jb      loc_18001BDC2
0x18001bf8c  mov     eax, 2
0x18001bf91  mul     rsi
0x18001bf94  test    rdx, rdx
0x18001bf97  jnz     loc_18001BDC2
0x18001bf9d  jmp     loc_18001BDFC
0x18001bfa2  test    rsi, rsi
0x18001bfa5  jz      loc_18001BDC7
0x18001bfab  mov     [rdx], bp
0x18001bfae  jmp     loc_18001BDC7
```
