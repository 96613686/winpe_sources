# MapFont(IMLangFontLink *,HDC__ *,ulong,HFONT__ *,HFONT__ * *,int *)

- ea: `0x180101bb8`
- end: `0x180101d5a`
- name: `?MapFont@@YAJPEAUIMLangFontLink@@PEAUHDC__@@KPEAUHFONT__@@PEAPEAU3@PEAH@Z`
- size: `418`
- prototype: `int(struct IMLangFontLink *, HDC, unsigned int, HFONT, HFONT *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180101d90`
- `0x180102088`

## callees

- `0x18009ead2`
- `0x18009eaea`
- `0x180101bb8`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180101d06`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180101d06`
- `GDI32!DeleteObject` at `0x180101d32`
- `GDI32!DeleteObject` at `0x180101d32`
- `GDI32!GetObjectW` at `0x180101c53`
- `GDI32!GetObjectW` at `0x180101c7a`
- `GDI32!GetObjectW` at `0x180101cf3`
- `GDI32!GetObjectW` at `0x180101c53`
- `GDI32!GetObjectW` at `0x180101c7a`
- `GDI32!GetObjectW` at `0x180101cf3`
- `GDI32!CreateFontIndirectW` at `0x180101cda`
- `GDI32!CreateFontIndirectW` at `0x180101cda`

## pseudocode

```c
__int64 __fastcall MapFont(struct IMLangFontLink *a1, HDC a2, unsigned int a3, HFONT a4, HFONT *a5, int *a6)
{
  __int64 result; // rax
  HFONT v11; // rax
  HFONT v12; // rbx
  LOGFONTW lf; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE pv[28]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v15; // [rsp+ACh] [rbp-54h]
  WCHAR String1[8]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v17; // [rsp+100h] [rbp+0h]
  __int128 v18; // [rsp+110h] [rbp+10h]
  __int128 v19; // [rsp+120h] [rbp+20h]

  memset_0(pv, 0, 0x5Cu);
  memset_0(&lf, 0, sizeof(lf));
  *a6 = 0;
  result = ((__int64 (__fastcall *)(struct IMLangFontLink *, HDC, _QWORD, HFONT, HFONT *))a1->lpVtbl->MapFont)(
             a1,
             a2,
             a3,
             a4,
             a5);
  if ( !(_DWORD)result )
  {
    if ( GetObjectW(a4, 92, pv) )
    {
      if ( v15 == 64 )
      {
        if ( GetObjectW(*a5, 92, &lf) )
        {
          if ( lf.lfFaceName[0] != 64 )
          {
            memmove_0(&lf.lfFaceName[1], lf.lfFaceName, 0x1Eu);
            lf.lfFaceName[0] = 64;
            v17 = *(_OWORD *)&lf.lfFaceName[8];
            *(_OWORD *)String1 = *(_OWORD *)lf.lfFaceName;
            lf.lfFaceName[31] = 0;
            v18 = *(_OWORD *)&lf.lfFaceName[16];
            v19 = *(_OWORD *)&lf.lfFaceName[24];
            v11 = CreateFontIndirectW(&lf);
            v12 = v11;
            if ( v11 )
            {
              if ( !GetObjectW(v11, 92, &lf) || lstrcmpW(String1, lf.lfFaceName) )
              {
                DeleteObject(v12);
              }
              else
              {
                ((void (__fastcall *)(struct IMLangFontLink *, _QWORD))a1->lpVtbl->ReleaseFont)(a1, *a5);
                *a5 = v12;
                *a6 = 1;
              }
            }
          }
        }
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180101bb8  push    rbp
0x180101bba  push    rbx
0x180101bbb  push    rsi
0x180101bbc  push    rdi
0x180101bbd  push    r12
0x180101bbf  push    r13
0x180101bc1  push    r14
0x180101bc3  push    r15
0x180101bc5  lea     rbp, [rsp-48h]
0x180101bca  sub     rsp, 148h
0x180101bd1  mov     rax, cs:__security_cookie
0x180101bd8  xor     rax, rsp
0x180101bdb  mov     [rbp+80h+var_50], rax
0x180101bdf  mov     rsi, [rbp+80h+arg_20]
0x180101be6  mov     edi, r8d
0x180101be9  mov     r12, [rbp+80h+arg_28]
0x180101bf0  mov     rbx, rdx
0x180101bf3  mov     r14, rcx
0x180101bf6  mov     r13d, 5Ch ; '\'
0x180101bfc  mov     r8d, r13d; Size
0x180101bff  lea     rcx, [rbp+80h+pv]; void *
0x180101c03  xor     edx, edx; Val
0x180101c05  mov     r15, r9
0x180101c08  call    memset_0
0x180101c0d  mov     r8d, r13d; Size
0x180101c10  lea     rcx, [rsp+180h+lf]; void *
0x180101c15  xor     edx, edx; Val
0x180101c17  call    memset_0
0x180101c1c  mov     dword ptr [r12], 0
0x180101c24  mov     r9, r15
0x180101c27  mov     rax, [r14]
0x180101c2a  mov     r8d, edi
0x180101c2d  mov     rdx, rbx
0x180101c30  mov     [rsp+180h+var_160], rsi
0x180101c35  mov     rcx, r14
0x180101c38  mov     rax, [rax+40h]
0x180101c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101c41  test    eax, eax
0x180101c43  jnz     loc_180101D3A
0x180101c49  lea     r8, [rbp+80h+pv]; pv
0x180101c4d  mov     edx, r13d; c
0x180101c50  mov     rcx, r15; h
0x180101c53  call    cs:__imp_GetObjectW
0x180101c59  test    eax, eax
0x180101c5b  jz      loc_180101D38
0x180101c61  lea     ebx, [r13-1Ch]
0x180101c65  cmp     [rbp+80h+var_D4], bx
0x180101c69  jnz     loc_180101D38
0x180101c6f  mov     rcx, [rsi]; h
0x180101c72  lea     r8, [rsp+180h+lf]; pv
0x180101c77  mov     edx, r13d; c
0x180101c7a  call    cs:__imp_GetObjectW
0x180101c80  test    eax, eax
0x180101c82  jz      loc_180101D38
0x180101c88  cmp     [rsp+180h+lf.lfFaceName], bx
0x180101c8d  jz      loc_180101D38
0x180101c93  lea     r8d, [r13-3Eh]; Size
0x180101c97  lea     rdx, [rsp+180h+lf.lfFaceName]; Src
0x180101c9c  lea     rcx, [rsp+180h+lf.lfFaceName+2]; void *
0x180101ca1  call    memmove_0
0x180101ca6  movups  xmm1, xmmword ptr [rsp+180h+lf.lfFaceName+10h]
0x180101cab  mov     [rsp+180h+lf.lfFaceName], bx
0x180101cb0  lea     rcx, [rsp+180h+lf]; lplf
0x180101cb5  movups  xmm0, xmmword ptr [rsp+180h+lf.lfFaceName]
0x180101cba  xor     eax, eax
0x180101cbc  movaps  [rbp+80h+var_80], xmm1
0x180101cc0  movaps  xmmword ptr [rbp+80h+String1], xmm0
0x180101cc4  movups  xmm0, xmmword ptr [rsp+180h+lf.lfFaceName+20h]
0x180101cc9  mov     [rbp+80h+lf.lfFaceName+3Eh], ax
0x180101ccd  movups  xmm1, xmmword ptr [rsp+7Ch]
0x180101cd2  movaps  [rbp+80h+var_70], xmm0
0x180101cd6  movaps  [rbp+80h+var_60], xmm1
0x180101cda  call    cs:__imp_CreateFontIndirectW
0x180101ce0  mov     rbx, rax
0x180101ce3  test    rax, rax
0x180101ce6  jz      short loc_180101D38
0x180101ce8  lea     r8, [rsp+180h+lf]; pv
0x180101ced  mov     edx, r13d; c
0x180101cf0  mov     rcx, rax; h
0x180101cf3  call    cs:__imp_GetObjectW
0x180101cf9  test    eax, eax
0x180101cfb  jz      short loc_180101D2F
0x180101cfd  lea     rdx, [rsp+180h+lf.lfFaceName]; lpString2
0x180101d02  lea     rcx, [rbp+80h+String1]; lpString1
0x180101d06  call    cs:__imp_lstrcmpW
0x180101d0c  test    eax, eax
0x180101d0e  jnz     short loc_180101D2F
0x180101d10  mov     rax, [r14]
0x180101d13  mov     rcx, r14
0x180101d16  mov     rdx, [rsi]
0x180101d19  mov     rax, [rax+48h]
0x180101d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101d22  mov     [rsi], rbx
0x180101d25  mov     dword ptr [r12], 1
0x180101d2d  jmp     short loc_180101D38
0x180101d2f  mov     rcx, rbx; ho
0x180101d32  call    cs:__imp_DeleteObject
0x180101d38  xor     eax, eax
0x180101d3a  mov     rcx, [rbp+80h+var_50]
0x180101d3e  xor     rcx, rsp; StackCookie
0x180101d41  call    __security_check_cookie
0x180101d46  add     rsp, 148h
0x180101d4d  pop     r15
0x180101d4f  pop     r14
0x180101d51  pop     r13
0x180101d53  pop     r12
0x180101d55  pop     rdi
0x180101d56  pop     rsi
0x180101d57  pop     rbx
0x180101d58  pop     rbp
0x180101d59  retn
```
