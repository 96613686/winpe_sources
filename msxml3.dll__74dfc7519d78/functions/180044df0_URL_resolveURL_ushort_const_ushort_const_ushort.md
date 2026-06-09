# URL::resolveURL(ushort const *,ushort const *,ushort * *)

- ea: `0x180044df0`
- end: `0x180044f6e`
- name: `?resolveURL@URL@@SAJPEBG0PEAPEAG@Z`
- size: `382`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180044d2c`
- `0x1800585d8`
- `0x180093df0`
- `0x1800ef160`
- `0x1800f3bac`

## callees

- `0x18000912c`
- `0x18001f080`
- `0x18003ab34`
- `0x180044df0`
- `0x18006aa08`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSearchAndQualifyW` at `0x180044f0f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSearchAndQualifyW` at `0x180044f0f`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x180044f2a`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x180044f2a`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x180044edc`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x180044edc`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x180044e92`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x180044e92`
- `urlmon!CreateURLMonikerEx` at `0x180044e33`
- `urlmon!CreateURLMonikerEx` at `0x180044e51`
- `urlmon!CreateURLMonikerEx` at `0x180044e33`
- `urlmon!CreateURLMonikerEx` at `0x180044e51`

## pseudocode

```c
__int64 __fastcall URL::resolveURL(WCHAR *Src, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  HRESULT v5; // ebx
  unsigned __int16 *v6; // rax
  HRESULT v7; // eax
  WCHAR *v8; // rax
  WCHAR *v9; // rsi
  WCHAR *v10; // rdx
  LPMONIKER v12; // [rsp+48h] [rbp+28h] BYREF
  LPMONIKER ppmk; // [rsp+50h] [rbp+30h] BYREF

  *a3 = 0;
  if ( a2 && *a2 )
  {
    ppmk = 0;
    v12 = 0;
    v5 = CreateURLMonikerEx(0, a2, &ppmk, 1u);
    if ( v5 >= 0 )
    {
      v5 = CreateURLMonikerEx(ppmk, Src, &v12, 1u);
      if ( v5 >= 0 )
      {
        v5 = URL::resolveURL(v12, 0, a3);
        ((void (__fastcall *)(LPMONIKER))v12->lpVtbl->Release)(v12);
      }
      ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
LABEL_19:
      if ( v5 >= 0 )
        return (unsigned int)v5;
    }
  }
  else
  {
    if ( PathIsURLW(Src) )
    {
      v5 = allocStrWHR(Src, a3);
      goto LABEL_19;
    }
    v6 = (unsigned __int16 *)new_array_ne<unsigned short>(4096);
    *a3 = v6;
    if ( v6 )
    {
      LODWORD(v12) = 4096;
      v7 = UrlUnescapeW(Src, v6, (DWORD *)&v12, 0);
      v5 = v7;
      if ( v7 < 0 )
      {
        if ( v7 == -2147467261 )
          v5 = -2147024809;
        goto LABEL_20;
      }
      v8 = (WCHAR *)new_array_ne<unsigned short>(4096);
      v9 = v8;
      if ( v8 )
      {
        if ( PathSearchAndQualifyW(*a3, v8, 0x1000u) )
        {
          v10 = *a3;
          LODWORD(v12) = 4096;
          v5 = UrlCreateFromPathW(v9, v10, (DWORD *)&v12, 0);
        }
        else
        {
          v5 = -2147024809;
        }
        MemFreeObject(v9);
        goto LABEL_19;
      }
    }
    v5 = -2147024882;
  }
LABEL_20:
  if ( *a3 )
  {
    MemFreeObject(*a3);
    *a3 = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180044df0  mov     [rsp-18h+arg_0], rbx
0x180044df5  mov     [rsp-18h+arg_18], rsi
0x180044dfa  push    rbp
0x180044dfb  push    rdi
0x180044dfc  push    r15
0x180044dfe  mov     rbp, rsp
0x180044e01  sub     rsp, 20h
0x180044e05  mov     qword ptr [r8], 0
0x180044e0c  mov     rdi, r8
0x180044e0f  mov     rsi, rcx
0x180044e12  test    rdx, rdx
0x180044e15  jz      short loc_180044E92
0x180044e17  xor     eax, eax
0x180044e19  cmp     ax, [rdx]
0x180044e1c  jz      short loc_180044E92
0x180044e1e  lea     r15d, [rax+1]
0x180044e22  mov     [rbp+ppmk], rax
0x180044e26  mov     r9d, r15d; dwFlags
0x180044e29  mov     [rbp+arg_8], rax
0x180044e2d  lea     r8, [rbp+ppmk]; ppmk
0x180044e31  xor     ecx, ecx; pMkCtx
0x180044e33  call    cs:__imp_CreateURLMonikerEx
0x180044e39  mov     ebx, eax
0x180044e3b  test    eax, eax
0x180044e3d  js      loc_180044F45
0x180044e43  mov     rcx, [rbp+ppmk]; pMkCtx
0x180044e47  lea     r8, [rbp+arg_8]; ppmk
0x180044e4b  mov     r9d, r15d; dwFlags
0x180044e4e  mov     rdx, rsi; szURL
0x180044e51  call    cs:__imp_CreateURLMonikerEx
0x180044e57  mov     ebx, eax
0x180044e59  test    eax, eax
0x180044e5b  js      short loc_180044E7D
0x180044e5d  mov     rcx, [rbp+arg_8]; struct IMoniker *
0x180044e61  mov     r8, rdi; unsigned __int16 **
0x180044e64  xor     edx, edx; struct IBindCtx *
0x180044e66  call    ?resolveURL@URL@@SAJPEAUIMoniker@@PEAUIBindCtx@@PEAPEAG@Z; URL::resolveURL(IMoniker *,IBindCtx *,ushort * *)
0x180044e6b  mov     rcx, [rbp+arg_8]
0x180044e6f  mov     ebx, eax
0x180044e71  mov     rax, [rcx]
0x180044e74  mov     rax, [rax+10h]
0x180044e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e7d  mov     rcx, [rbp+ppmk]
0x180044e81  mov     rax, [rcx]
0x180044e84  mov     rax, [rax+10h]
0x180044e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e8d  jmp     loc_180044F41
0x180044e92  call    cs:__imp_PathIsURLW
0x180044e98  test    eax, eax
0x180044e9a  jz      short loc_180044EAE
0x180044e9c  mov     rdx, rdi; unsigned __int16 **
0x180044e9f  mov     rcx, rsi; Src
0x180044ea2  call    ?allocStrWHR@@YAJPEBGPEAPEAG@Z; allocStrWHR(ushort const *,ushort * *)
0x180044ea7  mov     ebx, eax
0x180044ea9  jmp     loc_180044F41
0x180044eae  mov     r15d, 1000h
0x180044eb4  mov     ecx, r15d
0x180044eb7  call    ??$new_array_ne@G@@YAPEAG_J@Z; new_array_ne<ushort>(__int64)
0x180044ebc  mov     [rdi], rax
0x180044ebf  test    rax, rax
0x180044ec2  jnz     short loc_180044ECB
0x180044ec4  mov     ebx, 8007000Eh
0x180044ec9  jmp     short loc_180044F45
0x180044ecb  xor     r9d, r9d; dwFlags
0x180044ece  mov     dword ptr [rbp+arg_8], r15d
0x180044ed2  lea     r8, [rbp+arg_8]; pcchUnescaped
0x180044ed6  mov     rdx, rax; pszUnescaped
0x180044ed9  mov     rcx, rsi; pszUrl
0x180044edc  call    cs:__imp_UrlUnescapeW
0x180044ee2  mov     ebx, eax
0x180044ee4  test    eax, eax
0x180044ee6  jns     short loc_180044EF6
0x180044ee8  cmp     eax, 80004003h
0x180044eed  jnz     short loc_180044F45
0x180044eef  mov     ebx, 80070057h
0x180044ef4  jmp     short loc_180044F45
0x180044ef6  mov     rcx, r15
0x180044ef9  call    ??$new_array_ne@G@@YAPEAG_J@Z; new_array_ne<ushort>(__int64)
0x180044efe  mov     rsi, rax
0x180044f01  test    rax, rax
0x180044f04  jz      short loc_180044EC4
0x180044f06  mov     rcx, [rdi]; pszPath
0x180044f09  mov     r8d, r15d; cchBuf
0x180044f0c  mov     rdx, rax; pszBuf
0x180044f0f  call    cs:__imp_PathSearchAndQualifyW
0x180044f15  test    eax, eax
0x180044f17  jz      short loc_180044F34
0x180044f19  mov     rdx, [rdi]; pszUrl
0x180044f1c  lea     r8, [rbp+arg_8]; pcchUrl
0x180044f20  xor     r9d, r9d; dwFlags
0x180044f23  mov     dword ptr [rbp+arg_8], r15d
0x180044f27  mov     rcx, rsi; pszPath
0x180044f2a  call    cs:__imp_UrlCreateFromPathW
0x180044f30  mov     ebx, eax
0x180044f32  jmp     short loc_180044F39
0x180044f34  mov     ebx, 80070057h
0x180044f39  mov     rcx, rsi; void *
0x180044f3c  call    ?MemFreeObject@@YAXPEAX@Z; MemFreeObject(void *)
0x180044f41  test    ebx, ebx
0x180044f43  jns     short loc_180044F59
0x180044f45  mov     rcx, [rdi]; void *
0x180044f48  test    rcx, rcx
0x180044f4b  jz      short loc_180044F59
0x180044f4d  call    ?MemFreeObject@@YAXPEAX@Z; MemFreeObject(void *)
0x180044f52  mov     qword ptr [rdi], 0
0x180044f59  mov     rsi, [rsp+20h+arg_18]
0x180044f5e  mov     eax, ebx
0x180044f60  mov     rbx, [rsp+20h+arg_0]
0x180044f65  add     rsp, 20h
0x180044f69  pop     r15
0x180044f6b  pop     rdi
0x180044f6c  pop     rbp
0x180044f6d  retn
```
