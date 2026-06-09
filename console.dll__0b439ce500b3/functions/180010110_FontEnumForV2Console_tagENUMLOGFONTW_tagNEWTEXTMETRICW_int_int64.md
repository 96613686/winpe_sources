# FontEnumForV2Console(tagENUMLOGFONTW *,tagNEWTEXTMETRICW *,int,__int64)

- ea: `0x180010110`
- end: `0x1800102ed`
- name: `?FontEnumForV2Console@@YAHPEAUtagENUMLOGFONTW@@PEAUtagNEWTEXTMETRICW@@H_J@Z`
- size: `477`
- prototype: `__int64 __fastcall(LOGFONTW *lplf, struct tagNEWTEXTMETRICW *, int, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000b224`
- `0x18000b254`
- `0x18000f400`
- `0x18000f4b0`
- `0x180010110`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800101c2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800101c2`

## string_xrefs

- `0x180010137`: `onecore\windows\core\console\open\src\propsheet\misc.cpp`

## pseudocode

```c
char __fastcall FontEnumForV2Console(LOGFONTW *lplf, struct tagNEWTEXTMETRICW *a2, int a3, __int64 a4)
{
  __int64 v8; // rcx
  __int64 v9; // r9
  char v10; // al
  int v11; // ecx
  bool v12; // zf
  int v13; // eax
  unsigned __int8 v14; // al
  BOOL v15; // eax
  unsigned __int8 v16; // al
  unsigned __int8 v17; // al
  struct tagFACENODE *v18; // rax
  struct tagFACENODE *v19; // rbp
  unsigned int v20; // eax
  int v21; // edx
  __int64 i; // r14
  int v23; // eax
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !(unsigned int)ShouldAllowAllMonoTTFonts() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1D6,
      (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\misc.cpp",
      (const char *)v9);
  v10 = *(_BYTE *)(v8 + 27);
  if ( (v10 & 1) == 0 )
    goto LABEL_7;
  v11 = 323;
  if ( a3 == 4 )
  {
    if ( (v10 & 0xF0) != 0x30 || lplf->lfItalic )
      goto LABEL_7;
  }
  else
  {
    v14 = lplf->lfCharSet + 0x80;
    if ( (v14 > 8u || !_bittest(&v11, v14)) && lplf->lfCharSet != 0xFF )
      goto LABEL_22;
  }
  if ( lplf->lfFaceName[0] == 64 )
  {
LABEL_7:
    v12 = *(_DWORD *)(v9 + 8) == 0;
LABEL_8:
    LOBYTE(v13) = !v12;
    return v13;
  }
  v15 = g_fEastAsianSystem;
  if ( !g_fEastAsianSystem )
    goto LABEL_25;
  if ( a3 != 4 )
  {
    if ( lstrcmpW(lplf->lfFaceName, L"Terminal") )
    {
      v12 = *(_DWORD *)(a4 + 8) == 0;
      goto LABEL_8;
    }
    v15 = g_fEastAsianSystem;
    v11 = 323;
  }
  if ( v15 )
  {
    if ( a3 == 4 )
    {
      v16 = lplf->lfCharSet + 0x80;
      if ( v16 > 8u || !_bittest(&v11, v16) )
      {
LABEL_22:
        LOBYTE(v13) = 1;
        return v13;
      }
    }
  }
  else
  {
LABEL_25:
    if ( a3 == 4 )
    {
      v17 = lplf->lfCharSet + 0x80;
      if ( v17 <= 8u )
      {
        if ( _bittest(&v11, v17) )
          goto LABEL_22;
      }
    }
  }
  v18 = AddFaceNode(lplf->lfFaceName);
  v19 = v18;
  if ( !v18 )
  {
LABEL_42:
    LOBYTE(v13) = 0;
    return v13;
  }
  if ( *(_DWORD *)(a4 + 8) )
  {
    if ( a3 == 4 )
    {
      v20 = 17;
    }
    else
    {
      v20 = 1;
      if ( a3 == 1 )
        v20 = 9;
    }
    *((_DWORD *)v19 + 2) |= v20;
    LOBYTE(v20) = lplf->lfCharSet + 0x80;
    if ( (unsigned __int8)v20 <= 8u )
    {
      v21 = 323;
      if ( _bittest(&v21, v20) )
        *((_DWORD *)v19 + 2) |= 0x40u;
    }
    goto LABEL_22;
  }
  if ( (a3 & 4) != 0 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a4 + 24); i = (unsigned int)(i + 1) )
    {
      lplf->lfHeight = *(__int16 *)(*(_QWORD *)(a4 + 16) + 2 * i);
      lplf->lfWidth = 0;
      lplf->lfWeight = a2->tmWeight;
      v23 = AddFont(lplf, a2, a3, *(HDC *)a4, v19);
      v12 = (v23 | *(_DWORD *)(a4 + 12)) == 0;
      *(_DWORD *)(a4 + 12) |= v23;
      if ( v12 )
        goto LABEL_42;
    }
    LOBYTE(v13) = 2;
  }
  else
  {
    *(_DWORD *)(a4 + 12) |= AddFont(lplf, a2, a3, *(HDC *)a4, v18);
    return *(_DWORD *)(a4 + 12) != 0 ? 2 : 0;
  }
  return v13;
}

```

## disassembly

```asm
0x180010110  push    rbx
0x180010112  push    rbp
0x180010113  push    rsi
0x180010114  push    rdi
0x180010115  push    r14
0x180010117  push    r15
0x180010119  sub     rsp, 48h
0x18001011d  mov     rbx, r9
0x180010120  mov     esi, r8d
0x180010123  mov     r15, rdx
0x180010126  mov     rdi, rcx
0x180010129  call    ?ShouldAllowAllMonoTTFonts@@YAHXZ; ShouldAllowAllMonoTTFonts(void)
0x18001012e  test    eax, eax
0x180010130  jnz     short loc_180010149
0x180010132  mov     rcx, [rsp+78h]; this
0x180010137  lea     r8, aOnecoreWindows_4; "onecore\\windows\\core\\console\\open\\"...
0x18001013e  mov     edx, 1D6h; void *
0x180010143  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180010149  mov     al, [rcx+1Bh]
0x18001014c  test    al, 1
0x18001014e  jz      short loc_18001016C
0x180010150  mov     r14d, 4
0x180010156  mov     ecx, 143h
0x18001015b  cmp     esi, r14d
0x18001015e  jnz     short loc_180010183
0x180010160  and     al, 0F0h
0x180010162  cmp     al, 30h ; '0'
0x180010164  jnz     short loc_18001016C
0x180010166  cmp     byte ptr [rdi+14h], 0
0x18001016a  jz      short loc_18001019A
0x18001016c  xor     eax, eax
0x18001016e  cmp     [r9+8], eax
0x180010172  setnz   al
0x180010175  add     rsp, 48h
0x180010179  pop     r15
0x18001017b  pop     r14
0x18001017d  pop     rdi
0x18001017e  pop     rsi
0x18001017f  pop     rbp
0x180010180  pop     rbx
0x180010181  retn
0x180010183  mov     al, [rdi+17h]
0x180010186  sub     al, 80h
0x180010188  cmp     al, 8
0x18001018a  ja      short loc_180010194
0x18001018c  movzx   eax, al
0x18001018f  bt      ecx, eax
0x180010192  jb      short loc_18001019A
0x180010194  cmp     byte ptr [rdi+17h], 0FFh
0x180010198  jnz     short loc_1800101FE
0x18001019a  lea     rbp, [rdi+1Ch]
0x18001019e  mov     eax, 40h ; '@'
0x1800101a3  cmp     [rbp+0], ax
0x1800101a7  jz      short loc_18001016C
0x1800101a9  mov     eax, cs:?g_fEastAsianSystem@@3HA; int g_fEastAsianSystem
0x1800101af  test    eax, eax
0x1800101b1  jz      short loc_180010208
0x1800101b3  cmp     esi, r14d
0x1800101b6  jz      short loc_1800101E4
0x1800101b8  lea     rdx, aTerminal; "Terminal"
0x1800101bf  mov     rcx, rbp; lpString1
0x1800101c2  call    cs:__imp_lstrcmpW
0x1800101c9  nop     dword ptr [rax+rax+00h]
0x1800101ce  test    eax, eax
0x1800101d0  jz      short loc_1800101D9
0x1800101d2  xor     eax, eax
0x1800101d4  cmp     [rbx+8], eax
0x1800101d7  jmp     short loc_180010172
0x1800101d9  mov     eax, cs:?g_fEastAsianSystem@@3HA; int g_fEastAsianSystem
0x1800101df  mov     ecx, 143h
0x1800101e4  test    eax, eax
0x1800101e6  jz      short loc_180010208
0x1800101e8  cmp     esi, r14d
0x1800101eb  jnz     short loc_18001021E
0x1800101ed  mov     al, [rdi+17h]
0x1800101f0  sub     al, 80h
0x1800101f2  cmp     al, 8
0x1800101f4  ja      short loc_1800101FE
0x1800101f6  movzx   eax, al
0x1800101f9  bt      ecx, eax
0x1800101fc  jb      short loc_18001021E
0x1800101fe  mov     eax, 1
0x180010203  jmp     loc_180010175
0x180010208  cmp     esi, r14d
0x18001020b  jnz     short loc_18001021E
0x18001020d  mov     al, [rdi+17h]
0x180010210  sub     al, 80h
0x180010212  cmp     al, 8
0x180010214  ja      short loc_18001021E
0x180010216  movzx   eax, al
0x180010219  bt      ecx, eax
0x18001021c  jb      short loc_1800101FE
0x18001021e  mov     rcx, rbp; wchar_t *
0x180010221  call    ?AddFaceNode@@YAPEAUtagFACENODE@@PEB_W@Z; AddFaceNode(wchar_t const *)
0x180010226  mov     rbp, rax
0x180010229  test    rax, rax
0x18001022c  jz      loc_1800102E6
0x180010232  cmp     dword ptr [rbx+8], 0
0x180010236  jz      short loc_18001026D
0x180010238  cmp     esi, r14d
0x18001023b  jnz     short loc_180010244
0x18001023d  mov     eax, 11h
0x180010242  jmp     short loc_180010251
0x180010244  mov     eax, 1
0x180010249  cmp     esi, eax
0x18001024b  lea     ecx, [rax+8]
0x18001024e  cmovz   eax, ecx
0x180010251  or      [rbp+8], eax
0x180010254  mov     al, [rdi+17h]
0x180010257  sub     al, 80h
0x180010259  cmp     al, 8
0x18001025b  ja      short loc_1800101FE
0x18001025d  mov     edx, 143h
0x180010262  bt      edx, eax
0x180010265  jnb     short loc_1800101FE
0x180010267  or      dword ptr [rbp+8], 40h
0x18001026b  jmp     short loc_1800101FE
0x18001026d  test    r14b, sil
0x180010270  jz      short loc_1800102BE
0x180010272  xor     r14d, r14d
0x180010275  cmp     r14d, [rbx+18h]
0x180010279  jnb     short loc_1800102B4
0x18001027b  mov     rax, [rbx+10h]
0x18001027f  mov     r8d, esi; int
0x180010282  mov     rdx, r15; struct tagNEWTEXTMETRICW *
0x180010285  mov     [rsp+78h+var_58], rbp; struct tagFACENODE *
0x18001028a  movsx   ecx, word ptr [rax+r14*2]
0x18001028f  mov     [rdi], ecx
0x180010291  mov     rcx, rdi; lplf
0x180010294  mov     dword ptr [rdi+4], 0
0x18001029b  mov     eax, [r15+1Ch]
0x18001029f  mov     [rdi+10h], eax
0x1800102a2  mov     r9, [rbx]; HDC
0x1800102a5  call    ?AddFont@@YAHPEAUtagENUMLOGFONTW@@PEAUtagNEWTEXTMETRICW@@HPEAUHDC__@@PEAUtagFACENODE@@@Z; AddFont(tagENUMLOGFONTW *,tagNEWTEXTMETRICW *,int,HDC__ *,tagFACENODE *)
0x1800102aa  or      [rbx+0Ch], eax
0x1800102ad  jz      short loc_1800102E6
0x1800102af  inc     r14d
0x1800102b2  jmp     short loc_180010275
0x1800102b4  mov     eax, 2
0x1800102b9  jmp     loc_180010175
0x1800102be  mov     r9, [rbx]; HDC
0x1800102c1  mov     r8d, esi; int
0x1800102c4  mov     rdx, r15; struct tagNEWTEXTMETRICW *
0x1800102c7  mov     [rsp+78h+var_58], rbp; struct tagFACENODE *
0x1800102cc  mov     rcx, rdi; lplf
0x1800102cf  call    ?AddFont@@YAHPEAUtagENUMLOGFONTW@@PEAUtagNEWTEXTMETRICW@@HPEAUHDC__@@PEAUtagFACENODE@@@Z; AddFont(tagENUMLOGFONTW *,tagNEWTEXTMETRICW *,int,HDC__ *,tagFACENODE *)
0x1800102d4  or      [rbx+0Ch], eax
0x1800102d7  mov     eax, [rbx+0Ch]
0x1800102da  neg     eax
0x1800102dc  sbb     eax, eax
0x1800102de  and     eax, 2
0x1800102e1  jmp     loc_180010175
0x1800102e6  xor     eax, eax
0x1800102e8  jmp     loc_180010175
```
