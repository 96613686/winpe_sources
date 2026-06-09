# CMsftRawCDImageCreator::get_ExpectedTableOfContents(tagSAFEARRAY * *)

- ea: `0x18003e4d0`
- end: `0x18003e74e`
- name: `?get_ExpectedTableOfContents@CMsftRawCDImageCreator@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `638`
- prototype: `__int64 __fastcall(CMsftRawCDImageCreator *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002fc8`
- `0x18000f334`
- `0x180016778`
- `0x18001cb0c`
- `0x18003e4d0`
- `0x180049832`
- `0x18004984a`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18003e6d8`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18003e6d8`

## pseudocode

```c
__int64 __fastcall CMsftRawCDImageCreator::get_ExpectedTableOfContents(
        CMsftRawCDImageCreator *this,
        struct tagSAFEARRAY **a2)
{
  signed int v4; // ebx
  struct tagSAFEARRAY **v5; // rdx
  PVOID *v6; // rcx
  const struct _GUID *v7; // r8
  unsigned int v9; // esi
  char v10; // r13
  ULONG v11; // r12d
  __int64 v12; // r15
  __int64 v13; // rdi
  int v14; // edx
  int v15; // eax
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v17; // rdi
  _BYTE v18[8]; // [rsp+20h] [rbp-E0h] BYREF
  __int16 v19; // [rsp+28h] [rbp-D8h]
  char v20; // [rsp+2Ah] [rbp-D6h]
  SAFEARRAY *v21; // [rsp+30h] [rbp-D0h] BYREF
  struct tagSAFEARRAY **v22; // [rsp+38h] [rbp-C8h]
  _BYTE Src[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v24; // [rsp+42h] [rbp-BEh]
  char v25; // [rsp+43h] [rbp-BDh]
  char v26; // [rsp+44h] [rbp-BCh] BYREF
  char v27; // [rsp+45h] [rbp-BBh]
  char v28; // [rsp+46h] [rbp-BAh]
  char v29; // [rsp+48h] [rbp-B8h]
  __int16 v30; // [rsp+49h] [rbp-B7h]
  char v31; // [rsp+4Bh] [rbp-B5h]

  v22 = a2;
  v4 = 0;
  memset_0(&v26, 0, 0x320u);
  v5 = 0;
  v21 = 0;
  if ( *((_DWORD *)this + 27) )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 87), 80, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
      v5 = 0;
    }
    v4 = -2136339965;
  }
  if ( !a2 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 708) & 0x10) != 0 && *((_BYTE *)v6 + 705) >= 3u )
      WPP_SF_(v6[87], 81, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids);
    v4 = -2147467261;
    goto LABEL_14;
  }
  *a2 = 0;
  if ( v4 < 0 )
  {
LABEL_14:
    Imapi2Utility::SafeArrayDestroyAndNull((Imapi2Utility *)&v21, v5);
    goto LABEL_15;
  }
  v9 = 0;
  v10 = v27;
  v11 = 8 * *((_DWORD *)this + 27) + 12;
  v24 = *((_BYTE *)this + 104);
  v25 = *((_BYTE *)this + 108) + v24 - 1;
  Src[0] = BYTE1(v11);
  Src[1] = v11;
  while ( v9 < *((_DWORD *)this + 30) )
  {
    v12 = *((_QWORD *)this + 14);
    v13 = 32LL * v9;
    if ( (!*(_DWORD *)(v13 + v12) || *(_DWORD *)(v13 + v12) == 170 || *(_DWORD *)(v13 + v12 + 4) == 1)
      && (v20 = 0,
          v14 = *(_DWORD *)(v13 + v12 + 8),
          v19 = 0,
          v15 = Imapi2Utility::CMinutesSecondsFramesAddress::Init(
                  (Imapi2Utility::CMinutesSecondsFramesAddress *)v18,
                  v14),
          v5 = 0,
          v4 = v15,
          v15 >= 0) )
    {
      v30 = v19;
      v10 = (v10 & 0xF | 0x10) ^ (*(_BYTE *)(v13 + v12 + 24) ^ (v10 & 0xF | 0x10)) & 0xF;
      ++v9;
      v28 = *(_BYTE *)(v13 + v12);
      v29 = 0;
      v31 = v20;
      v27 = v10;
    }
    else
    {
      ++v9;
      if ( v4 < 0 )
        goto LABEL_14;
    }
  }
  Vector = SafeArrayCreateVector(0x11u, 0, v11);
  v21 = Vector;
  v17 = Vector;
  if ( !Vector )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 87), 82, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids);
    }
    v4 = -2147024882;
    goto LABEL_14;
  }
  memcpy_0(Vector->pvData, Src, v11);
  *v22 = v17;
LABEL_15:
  if ( (v4 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v4, (__int64)&CLSID_MsftRawCDImageCreator, v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003e4d0  mov     [rsp-8+arg_10], rbx
0x18003e4d5  push    rbp
0x18003e4d6  push    rsi
0x18003e4d7  push    rdi
0x18003e4d8  push    r12
0x18003e4da  push    r13
0x18003e4dc  push    r14
0x18003e4de  push    r15
0x18003e4e0  lea     rbp, [rsp-270h]
0x18003e4e8  sub     rsp, 370h
0x18003e4ef  mov     r15, rdx
0x18003e4f2  mov     [rsp+3A0h+var_368], rdx
0x18003e4f7  mov     r14, rcx
0x18003e4fa  xor     edx, edx; Val
0x18003e4fc  lea     rcx, [rsp+3A0h+var_35C]; void *
0x18003e501  mov     r8d, 320h; Size
0x18003e507  xor     ebx, ebx
0x18003e509  call    memset_0
0x18003e50e  xor     edx, edx
0x18003e510  lea     rax, WPP_GLOBAL_Control
0x18003e517  mov     [rsp+3A0h+var_370], rdx
0x18003e51c  cmp     [r14+6Ch], edx
0x18003e520  jnz     short loc_18003E56D
0x18003e522  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e529  cmp     rcx, rax
0x18003e52c  jz      short loc_18003E566
0x18003e52e  test    byte ptr [rcx+2C4h], 10h
0x18003e535  jz      short loc_18003E566
0x18003e537  cmp     byte ptr [rcx+2C1h], 3
0x18003e53e  jb      short loc_18003E566
0x18003e540  mov     rcx, [rcx+2B8h]
0x18003e547  lea     edx, [rbx+50h]
0x18003e54a  lea     r8, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003e551  call    WPP_SF_
0x18003e556  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e55d  lea     rax, WPP_GLOBAL_Control
0x18003e564  xor     edx, edx
0x18003e566  mov     ebx, 80AA0A03h
0x18003e56b  jmp     short loc_18003E574
0x18003e56d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e574  test    r15, r15
0x18003e577  jnz     short loc_18003E5EF
0x18003e579  cmp     rcx, rax
0x18003e57c  jz      short loc_18003E5A7
0x18003e57e  test    byte ptr [rcx+2C4h], 10h
0x18003e585  jz      short loc_18003E5A7
0x18003e587  cmp     byte ptr [rcx+2C1h], 3
0x18003e58e  jb      short loc_18003E5A7
0x18003e590  mov     rcx, [rcx+2B8h]
0x18003e597  lea     edx, [r15+51h]
0x18003e59b  lea     r8, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003e5a2  call    WPP_SF_
0x18003e5a7  mov     ebx, 80004003h
0x18003e5ac  lea     rcx, [rsp+3A0h+var_370]; this
0x18003e5b1  call    ?SafeArrayDestroyAndNull@Imapi2Utility@@YAXAEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::SafeArrayDestroyAndNull(tagSAFEARRAY * &)
0x18003e5b6  mov     eax, ebx
0x18003e5b8  and     eax, 80FF0000h
0x18003e5bd  cmp     eax, 80AA0000h
0x18003e5c2  jnz     short loc_18003E5D2
0x18003e5c4  lea     rdx, CLSID_MsftRawCDImageCreator; int
0x18003e5cb  mov     ecx, ebx; dwMessageId
0x18003e5cd  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18003e5d2  mov     eax, ebx
0x18003e5d4  mov     rbx, [rsp+3A0h+arg_10]
0x18003e5dc  add     rsp, 370h
0x18003e5e3  pop     r15
0x18003e5e5  pop     r14
0x18003e5e7  pop     r13
0x18003e5e9  pop     r12
0x18003e5eb  pop     rdi
0x18003e5ec  pop     rsi
0x18003e5ed  pop     rbp
0x18003e5ee  retn
0x18003e5ef  mov     [r15], rdx
0x18003e5f2  test    ebx, ebx
0x18003e5f4  js      short loc_18003E5AC
0x18003e5f6  mov     eax, [r14+6Ch]
0x18003e5fa  mov     esi, edx
0x18003e5fc  mov     r13b, [rsp+3A0h+var_35B]
0x18003e601  lea     r12d, ds:0Ch[rax*8]
0x18003e609  mov     al, [r14+68h]
0x18003e60d  mov     [rsp+3A0h+var_35E], al
0x18003e611  dec     al
0x18003e613  add     al, [r14+6Ch]
0x18003e617  mov     [rsp+3A0h+var_35D], al
0x18003e61b  mov     eax, r12d
0x18003e61e  shr     eax, 8
0x18003e621  mov     [rsp+3A0h+Src], al
0x18003e625  mov     [rsp+3A0h+var_35F], r12b
0x18003e62a  cmp     esi, [r14+78h]
0x18003e62e  jnb     loc_18003E6CE
0x18003e634  mov     r15, [r14+70h]
0x18003e638  mov     edi, esi
0x18003e63a  shl     rdi, 5
0x18003e63e  cmp     [rdi+r15], edx
0x18003e642  jz      short loc_18003E656
0x18003e644  cmp     dword ptr [rdi+r15], 0AAh
0x18003e64c  jz      short loc_18003E656
0x18003e64e  cmp     dword ptr [rdi+r15+4], 1
0x18003e654  jnz     short loc_18003E6BF
0x18003e656  mov     [rsp+3A0h+var_376], dl
0x18003e65a  lea     rcx, [rsp+3A0h+var_380]; this
0x18003e65f  mov     edx, [rdi+r15+8]; int
0x18003e664  mov     [rsp+3A0h+var_378], 0
0x18003e66b  call    ?Init@CMinutesSecondsFramesAddress@Imapi2Utility@@QEAAJJ@Z; Imapi2Utility::CMinutesSecondsFramesAddress::Init(long)
0x18003e670  xor     edx, edx
0x18003e672  mov     ebx, eax
0x18003e674  test    eax, eax
0x18003e676  js      short loc_18003E6BF
0x18003e678  mov     cl, byte ptr [rsp+3A0h+var_378]
0x18003e67c  and     r13b, 0Fh
0x18003e680  or      r13b, 10h
0x18003e684  mov     byte ptr [rsp+3A0h+var_357], cl
0x18003e688  mov     cl, byte ptr [rsp+3A0h+var_378+1]
0x18003e68c  mov     al, r13b
0x18003e68f  xor     r13b, [rdi+r15+18h]
0x18003e694  and     r13b, 0Fh
0x18003e698  mov     byte ptr [rsp+3A0h+var_357+1], cl
0x18003e69c  mov     cl, [rsp+3A0h+var_376]
0x18003e6a0  xor     r13b, al
0x18003e6a3  mov     al, [rdi+r15]
0x18003e6a7  inc     esi
0x18003e6a9  mov     [rsp+3A0h+var_35A], al
0x18003e6ad  mov     [rsp+3A0h+var_358], dl
0x18003e6b1  mov     [rsp+3A0h+var_355], cl
0x18003e6b5  mov     [rsp+3A0h+var_35B], r13b
0x18003e6ba  jmp     loc_18003E62A
0x18003e6bf  inc     esi
0x18003e6c1  test    ebx, ebx
0x18003e6c3  jns     loc_18003E62A
0x18003e6c9  jmp     loc_18003E5AC
0x18003e6ce  mov     ecx, 11h; vt
0x18003e6d3  mov     r8d, r12d; cElements
0x18003e6d6  xor     edx, edx; lLbound
0x18003e6d8  call    cs:__imp_SafeArrayCreateVector
0x18003e6de  mov     [rsp+3A0h+var_370], rax
0x18003e6e3  mov     rdi, rax
0x18003e6e6  test    rax, rax
0x18003e6e9  jnz     short loc_18003E730
0x18003e6eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e6f2  lea     rax, WPP_GLOBAL_Control
0x18003e6f9  cmp     rcx, rax
0x18003e6fc  jz      short loc_18003E726
0x18003e6fe  test    byte ptr [rcx+2C4h], 10h
0x18003e705  jz      short loc_18003E726
0x18003e707  cmp     byte ptr [rcx+2C1h], 3
0x18003e70e  jb      short loc_18003E726
0x18003e710  mov     rcx, [rcx+2B8h]
0x18003e717  lea     edx, [rdi+52h]
0x18003e71a  lea     r8, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003e721  call    WPP_SF_
0x18003e726  mov     ebx, 8007000Eh
0x18003e72b  jmp     loc_18003E5AC
0x18003e730  mov     rcx, [rax+10h]; void *
0x18003e734  lea     rdx, [rsp+3A0h+Src]; Src
0x18003e739  mov     r8d, r12d; Size
0x18003e73c  call    memcpy_0
0x18003e741  mov     rax, [rsp+3A0h+var_368]
0x18003e746  mov     [rax], rdi
0x18003e749  jmp     loc_18003E5B6
```
