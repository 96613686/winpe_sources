# CDefaultExtractIcon::_GetIconLocation_File(ushort *,uint,int *)

- ea: `0x1800396c0`
- end: `0x1800397c2`
- name: `?_GetIconLocation_File@CDefaultExtractIcon@@AEAAJPEAGIPEAH@Z`
- size: `258`
- prototype: `int(CDefaultExtractIcon *__hidden this, unsigned __int16 *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180039630`

## callees

- `0x18000735c`
- `0x1800173cc`
- `0x180026280`
- `0x1800329ec`
- `0x1800396c0`

## import_xrefs

- `SHLWAPI!AssocQueryStringW` at `0x180039713`
- `SHLWAPI!AssocQueryStringW` at `0x180039713`
- `SHLWAPI!PathParseIconLocationW` at `0x180039722`
- `SHLWAPI!PathParseIconLocationW` at `0x180039722`

## pseudocode

```c
__int64 __fastcall CDefaultExtractIcon::_GetIconLocation_File(
        CDefaultExtractIcon *this,
        unsigned __int16 *a2,
        __int64 a3,
        int *a4)
{
  CPath *v4; // rbp
  const unsigned __int16 *ConstBuffer; // rax
  const WCHAR *Extension; // rsi
  DWORD v9; // r10d
  HRESULT v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  __int64 v13; // r10
  char v14; // r8
  DWORD pcchOut; // [rsp+60h] [rbp+18h] BYREF

  v4 = (CDefaultExtractIcon *)((char *)this + 24);
  ConstBuffer = CPath::_GetConstBuffer((CDefaultExtractIcon *)((char *)this + 24));
  Extension = CscPath_FindExtension(ConstBuffer);
  pcchOut = v9;
  v10 = AssocQueryStringW(4u, ASSOCSTR_DEFAULTICON, Extension, 0, a2, &pcchOut);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_5fe987ea1b1f3d929bb98d819c20dc91_Traceguids,
        v10,
        (__int64)Extension);
    }
  }
  else
  {
    *a4 = PathParseIconLocationW(a2);
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      v12 = (unsigned int)CPath::_GetConstBuffer(v4);
      WPP_SF_SSD(
        *(_QWORD *)(v13 + 16),
        13,
        (unsigned int)WPP_5fe987ea1b1f3d929bb98d819c20dc91_Traceguids,
        v12,
        (__int64)a2,
        v14);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x1800396c0  mov     [rsp+arg_0], rbx
0x1800396c5  mov     [rsp+arg_8], rbp
0x1800396ca  push    rsi
0x1800396cb  push    rdi
0x1800396cc  push    r14
0x1800396ce  sub     rsp, 30h
0x1800396d2  lea     rbp, [rcx+18h]
0x1800396d6  mov     r14, r9
0x1800396d9  mov     rcx, rbp; this
0x1800396dc  mov     r10d, r8d
0x1800396df  mov     rdi, rdx
0x1800396e2  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x1800396e7  mov     rcx, rax; unsigned __int16 *
0x1800396ea  call    ?CscPath_FindExtension@@YAPEAGPEBG@Z; CscPath_FindExtension(ushort const *)
0x1800396ef  mov     rsi, rax
0x1800396f2  mov     [rsp+48h+arg_10], r10d
0x1800396f7  xor     r9d, r9d; pszExtra
0x1800396fa  lea     rax, [rsp+48h+arg_10]
0x1800396ff  mov     [rsp+48h+pcchOut], rax; pcchOut
0x180039704  mov     r8, rsi; pszAssoc
0x180039707  mov     [rsp+48h+pszOut], rdi; pszOut
0x18003970c  lea     edx, [r9+0Fh]; str
0x180039710  lea     ecx, [rdx-0Bh]; flags
0x180039713  call    cs:__imp_AssocQueryStringW
0x180039719  mov     ebx, eax
0x18003971b  test    eax, eax
0x18003971d  js      short loc_180039777
0x18003971f  mov     rcx, rdi; pszIconFile
0x180039722  call    cs:__imp_PathParseIconLocationW
0x180039728  mov     r8d, eax
0x18003972b  mov     [r14], eax
0x18003972e  mov     r10, cs:WPP_GLOBAL_Control
0x180039735  lea     rdx, WPP_GLOBAL_Control
0x18003973c  cmp     r10, rdx
0x18003973f  jz      short loc_1800397AD
0x180039741  test    dword ptr [r10+1Ch], 2000000h
0x180039749  jz      short loc_1800397AD
0x18003974b  mov     rcx, rbp; this
0x18003974e  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x180039753  mov     rcx, [r10+10h]
0x180039757  mov     r9, rax
0x18003975a  mov     dword ptr [rsp+48h+pcchOut], r8d
0x18003975f  mov     edx, 0Dh
0x180039764  lea     r8, WPP_5fe987ea1b1f3d929bb98d819c20dc91_Traceguids
0x18003976b  mov     [rsp+48h+pszOut], rdi
0x180039770  call    WPP_SF_SSD
0x180039775  jmp     short loc_1800397AD
0x180039777  mov     rcx, cs:WPP_GLOBAL_Control
0x18003977e  lea     rdx, WPP_GLOBAL_Control
0x180039785  cmp     rcx, rdx
0x180039788  jz      short loc_1800397AD
0x18003978a  test    byte ptr [rcx+1Ch], 2
0x18003978e  jz      short loc_1800397AD
0x180039790  mov     rcx, [rcx+10h]
0x180039794  lea     r8, WPP_5fe987ea1b1f3d929bb98d819c20dc91_Traceguids
0x18003979b  mov     edx, 0Eh
0x1800397a0  mov     [rsp+48h+pszOut], rsi
0x1800397a5  mov     r9d, ebx
0x1800397a8  call    WPP_SF_DS
0x1800397ad  mov     rbp, [rsp+48h+arg_8]
0x1800397b2  mov     eax, ebx
0x1800397b4  mov     rbx, [rsp+48h+arg_0]
0x1800397b9  add     rsp, 30h
0x1800397bd  pop     r14
0x1800397bf  pop     rdi
0x1800397c0  pop     rsi
0x1800397c1  retn
```
