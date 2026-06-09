# GetPageFontMetrics(PROPDATA *,PAGEFONTDATA const *)

- ea: `0x1800bc474`
- end: `0x1800bc663`
- name: `?GetPageFontMetrics@@YAHPEAUPROPDATA@@PEBUPAGEFONTDATA@@@Z`
- size: `495`
- prototype: `__int64 __fastcall(struct PROPDATA *, const struct PAGEFONTDATA *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800bb5fc`
- `0x1800bbbac`

## callees

- `0x1800a2df8`
- `0x1800bc474`
- `0x180114520`
- `0x180114ebc`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800bc553`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800bc553`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800bc586`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800bc586`
- `GDI32!DeleteObject` at `0x1800bc5ed`
- `GDI32!DeleteObject` at `0x1800bc5ed`
- `GDI32!SelectObject` at `0x1800bc5c1`
- `GDI32!SelectObject` at `0x1800bc5e4`
- `GDI32!SelectObject` at `0x1800bc5c1`
- `GDI32!SelectObject` at `0x1800bc5e4`
- `GDI32!CreateFontIndirectW` at `0x1800bc5ad`
- `GDI32!CreateFontIndirectW` at `0x1800bc5ad`
- `USER32!GetDC` at `0x1800bc568`
- `USER32!GetDC` at `0x1800bc568`
- `USER32!ReleaseDC` at `0x1800bc634`
- `USER32!ReleaseDC` at `0x1800bc634`

## pseudocode

```c
__int64 __fastcall GetPageFontMetrics(struct PROPDATA *a1, const struct PAGEFONTDATA *a2)
{
  unsigned int v4; // ebp
  __int16 v5; // r14
  const WCHAR *v6; // rsi
  __int64 v7; // rcx
  __int64 v8; // rdx
  const WCHAR *v9; // r8
  WCHAR *lfFaceName; // rax
  WCHAR *v11; // rcx
  int v12; // eax
  HDC DC; // rsi
  int v14; // eax
  HFONT v15; // rax
  HFONT v16; // r14
  HGDIOBJ v17; // rbp
  LOGFONTW lf; // [rsp+20h] [rbp-98h] BYREF

  v4 = 0;
  if ( a2 )
  {
    v5 = *(_WORD *)a2;
    if ( *(__int16 *)a2 > 0 )
    {
      v6 = (const WCHAR *)((char *)a2 + 2);
      if ( *((_WORD *)a2 + 1) )
      {
        memset_0(&lf, 0, sizeof(lf));
        v7 = 2147483646;
        v8 = 32;
        v9 = v6;
        lfFaceName = lf.lfFaceName;
        do
        {
          if ( !v7 )
            break;
          if ( !*v9 )
            break;
          *lfFaceName++ = *v9++;
          --v7;
          --v8;
        }
        while ( v8 );
        v11 = lfFaceName - 1;
        if ( v8 )
          v11 = lfFaceName;
        v12 = *((_DWORD *)a1 + 76);
        *v11 = 0;
        if ( *((_DWORD *)a2 + 18) == v12
          && *((_DWORD *)a2 + 17) == *((_DWORD *)a1 + 75)
          && v5 == *((_WORD *)a1 + 116)
          && *((_DWORD *)a2 + 19) == *((_DWORD *)a1 + 77)
          && !lstrcmpiW(v6, (LPCWSTR)a1 + 117) )
        {
          return 1;
        }
        else
        {
          DC = GetDC(*(HWND *)a1);
          if ( DC )
          {
            v14 = MulDiv(*(__int16 *)a2, *((_DWORD *)a2 + 19), 72);
            lf.lfCharSet = *((_BYTE *)a2 + 72);
            lf.lfItalic = *((_BYTE *)a2 + 68);
            lf.lfHeight = -v14;
            lf.lfWeight = 400;
            v15 = CreateFontIndirectW(&lf);
            v16 = v15;
            if ( v15 )
            {
              v17 = SelectObject(DC, v15);
              GetCharDimensions(DC, (LPSIZE)a1 + 39);
              if ( v17 )
                SelectObject(DC, v17);
              DeleteObject(v16);
              v4 = 1;
              *(_OWORD *)((char *)a1 + 232) = *(_OWORD *)a2;
              *(_OWORD *)((char *)a1 + 248) = *((_OWORD *)a2 + 1);
              *(_OWORD *)((char *)a1 + 264) = *((_OWORD *)a2 + 2);
              *(_OWORD *)((char *)a1 + 280) = *((_OWORD *)a2 + 3);
              *(_OWORD *)((char *)a1 + 296) = *((_OWORD *)a2 + 4);
            }
            ReleaseDC(*(HWND *)a1, DC);
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800bc474  mov     [rsp+arg_10], rbx
0x1800bc479  push    rbp
0x1800bc47a  push    rsi
0x1800bc47b  push    rdi
0x1800bc47c  push    r14
0x1800bc47e  push    r15
0x1800bc480  sub     rsp, 90h
0x1800bc487  mov     rax, cs:__security_cookie
0x1800bc48e  xor     rax, rsp
0x1800bc491  mov     [rsp+0B8h+var_38], rax
0x1800bc499  xor     r15d, r15d
0x1800bc49c  mov     rdi, rdx
0x1800bc49f  mov     rbx, rcx
0x1800bc4a2  mov     ebp, r15d
0x1800bc4a5  test    rdx, rdx
0x1800bc4a8  jz      loc_1800BC63A
0x1800bc4ae  movzx   r14d, word ptr [rdx]
0x1800bc4b2  test    r14w, r14w
0x1800bc4b6  jle     loc_1800BC63A
0x1800bc4bc  lea     rsi, [rdx+2]
0x1800bc4c0  cmp     [rsi], r15w
0x1800bc4c4  jz      loc_1800BC63A
0x1800bc4ca  xor     edx, edx; Val
0x1800bc4cc  lea     r8d, [r15+5Ch]; Size
0x1800bc4d0  lea     rcx, [rsp+0B8h+lf]; void *
0x1800bc4d5  call    memset_0
0x1800bc4da  mov     ecx, 7FFFFFFEh
0x1800bc4df  lea     edx, [r15+20h]
0x1800bc4e3  mov     r8, rsi
0x1800bc4e6  lea     rax, [rsp+0B8h+lf.lfFaceName]
0x1800bc4eb  test    rcx, rcx
0x1800bc4ee  jz      short loc_1800BC50F
0x1800bc4f0  movzx   r9d, word ptr [r8]
0x1800bc4f4  test    r9w, r9w
0x1800bc4f8  jz      short loc_1800BC50F
0x1800bc4fa  mov     [rax], r9w
0x1800bc4fe  add     r8, 2
0x1800bc502  add     rax, 2
0x1800bc506  dec     rcx
0x1800bc509  sub     rdx, 1
0x1800bc50d  jnz     short loc_1800BC4EB
0x1800bc50f  test    rdx, rdx
0x1800bc512  lea     rcx, [rax-2]
0x1800bc516  cmovnz  rcx, rax
0x1800bc51a  mov     eax, [rbx+130h]
0x1800bc520  mov     [rcx], r15w
0x1800bc524  cmp     [rdi+48h], eax
0x1800bc527  jnz     short loc_1800BC565
0x1800bc529  mov     eax, [rbx+12Ch]
0x1800bc52f  cmp     [rdi+44h], eax
0x1800bc532  jnz     short loc_1800BC565
0x1800bc534  cmp     r14w, [rbx+0E8h]
0x1800bc53c  jnz     short loc_1800BC565
0x1800bc53e  mov     eax, [rbx+134h]
0x1800bc544  cmp     [rdi+4Ch], eax
0x1800bc547  jnz     short loc_1800BC565
0x1800bc549  lea     rdx, [rbx+0EAh]; lpString2
0x1800bc550  mov     rcx, rsi; lpString1
0x1800bc553  call    cs:__imp_lstrcmpiW
0x1800bc559  test    eax, eax
0x1800bc55b  jnz     short loc_1800BC565
0x1800bc55d  lea     ebp, [rax+1]
0x1800bc560  jmp     loc_1800BC63A
0x1800bc565  mov     rcx, [rbx]; hWnd
0x1800bc568  call    cs:__imp_GetDC
0x1800bc56e  mov     rsi, rax
0x1800bc571  test    rax, rax
0x1800bc574  jz      loc_1800BC63A
0x1800bc57a  movsx   ecx, word ptr [rdi]; nNumber
0x1800bc57d  mov     r8d, 48h ; 'H'; nDenominator
0x1800bc583  mov     edx, [rdi+4Ch]; nNumerator
0x1800bc586  call    cs:__imp_MulDiv
0x1800bc58c  mov     cl, [rdi+48h]
0x1800bc58f  neg     eax
0x1800bc591  mov     [rsp+0B8h+lf.lfCharSet], cl
0x1800bc595  mov     cl, [rdi+44h]
0x1800bc598  mov     [rsp+0B8h+lf.lfItalic], cl
0x1800bc59c  lea     rcx, [rsp+0B8h+lf]; lplf
0x1800bc5a1  mov     [rsp+0B8h+lf.lfHeight], eax
0x1800bc5a5  mov     [rsp+0B8h+lf.lfWeight], 190h
0x1800bc5ad  call    cs:__imp_CreateFontIndirectW
0x1800bc5b3  mov     r14, rax
0x1800bc5b6  test    rax, rax
0x1800bc5b9  jz      short loc_1800BC62E
0x1800bc5bb  mov     rdx, rax; h
0x1800bc5be  mov     rcx, rsi; hdc
0x1800bc5c1  call    cs:__imp_SelectObject
0x1800bc5c7  lea     rdx, [rbx+138h]; psizl
0x1800bc5ce  mov     rcx, rsi; hdc
0x1800bc5d1  mov     rbp, rax
0x1800bc5d4  call    GetCharDimensions
0x1800bc5d9  test    rbp, rbp
0x1800bc5dc  jz      short loc_1800BC5EA
0x1800bc5de  mov     rdx, rbp; h
0x1800bc5e1  mov     rcx, rsi; hdc
0x1800bc5e4  call    cs:__imp_SelectObject
0x1800bc5ea  mov     rcx, r14; ho
0x1800bc5ed  call    cs:__imp_DeleteObject
0x1800bc5f3  movaps  xmm0, xmmword ptr [rdi]
0x1800bc5f6  mov     ebp, 1
0x1800bc5fb  movups  xmmword ptr [rbx+0E8h], xmm0
0x1800bc602  movaps  xmm1, xmmword ptr [rdi+10h]
0x1800bc606  movups  xmmword ptr [rbx+0F8h], xmm1
0x1800bc60d  movaps  xmm0, xmmword ptr [rdi+20h]
0x1800bc611  movups  xmmword ptr [rbx+108h], xmm0
0x1800bc618  movaps  xmm1, xmmword ptr [rdi+30h]
0x1800bc61c  movups  xmmword ptr [rbx+118h], xmm1
0x1800bc623  movaps  xmm0, xmmword ptr [rdi+40h]
0x1800bc627  movups  xmmword ptr [rbx+128h], xmm0
0x1800bc62e  mov     rcx, [rbx]; hWnd
0x1800bc631  mov     rdx, rsi; hDC
0x1800bc634  call    cs:__imp_ReleaseDC
0x1800bc63a  mov     eax, ebp
0x1800bc63c  mov     rcx, [rsp+0B8h+var_38]
0x1800bc644  xor     rcx, rsp; StackCookie
0x1800bc647  call    __security_check_cookie
0x1800bc64c  mov     rbx, [rsp+0B8h+arg_10]
0x1800bc654  add     rsp, 90h
0x1800bc65b  pop     r15
0x1800bc65d  pop     r14
0x1800bc65f  pop     rdi
0x1800bc660  pop     rsi
0x1800bc661  pop     rbp
0x1800bc662  retn
```
