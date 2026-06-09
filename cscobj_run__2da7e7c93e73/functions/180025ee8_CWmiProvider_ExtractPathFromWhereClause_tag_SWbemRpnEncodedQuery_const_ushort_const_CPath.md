# CWmiProvider::_ExtractPathFromWhereClause(tag_SWbemRpnEncodedQuery const &,ushort const *,CPath *)

- ea: `0x180025ee8`
- end: `0x180025fdb`
- name: `?_ExtractPathFromWhereClause@CWmiProvider@@AEAAJAEBUtag_SWbemRpnEncodedQuery@@PEBGPEAVCPath@@@Z`
- size: `243`
- prototype: `int(CWmiProvider *__hidden this, const struct tag_SWbemRpnEncodedQuery *, const unsigned __int16 *, struct CPath *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180025fe4`

## callees

- `0x1800083f0`
- `0x180014068`
- `0x180025ee8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025f7a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025f7a`

## pseudocode

```c
__int64 __fastcall CWmiProvider::_ExtractPathFromWhereClause(
        CWmiProvider *this,
        const struct tag_SWbemRpnEncodedQuery *a2,
        const unsigned __int16 *a3,
        struct CPath *a4)
{
  unsigned int v7; // esi
  __int64 i; // rdi
  SWbemRpnQueryToken *v9; // rbx
  SWbemQueryQualifiedName *m_pLeftIdent; // rax

  v7 = CPath::Copy(a4, &qword_18003ADA8);
  for ( i = 0; (unsigned int)i < a2->m_uWhereClauseSize; i = (unsigned int)(i + 1) )
  {
    v9 = a2->m_ppRpnWhereClause[i];
    if ( v9->m_uTokenType == 1
      && (v9->m_uSubexpressionShape & 0x19) == 0x19
      && v9->m_uOperator == 1
      && v9->m_uConstApparentType == 31 )
    {
      m_pLeftIdent = v9->m_pLeftIdent;
      if ( !m_pLeftIdent )
        continue;
    }
    else
    {
      m_pLeftIdent = v9->m_pLeftIdent;
      if ( !m_pLeftIdent || m_pLeftIdent->m_uNameListSize != 1 )
        continue;
    }
    if ( CompareStringW(0x7Fu, 1u, a3, -1, *m_pLeftIdent->m_ppszNameList, -1) == 2 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
      {
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_S)(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          74,
          WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids,
          (SWbemRpnConst)v9->m_Const.m_lVal64);
      }
      return (unsigned int)CPath::Copy(a4, v9->m_Const.m_pszStrVal);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180025ee8  push    rbx
0x180025eea  push    rbp
0x180025eeb  push    rsi
0x180025eec  push    rdi
0x180025eed  push    r14
0x180025eef  push    r15
0x180025ef1  sub     rsp, 38h
0x180025ef5  mov     rbp, rdx
0x180025ef8  mov     rcx, r9; this
0x180025efb  lea     rdx, qword_18003ADA8; unsigned __int16 *
0x180025f02  mov     r14, r9
0x180025f05  mov     r15, r8
0x180025f08  call    ?Copy@CPath@@QEAAJPEBG@Z; CPath::Copy(ushort const *)
0x180025f0d  mov     esi, eax
0x180025f0f  xor     edi, edi
0x180025f11  cmp     edi, [rbp+50h]
0x180025f14  jnb     loc_180025FCC
0x180025f1a  mov     rcx, [rbp+58h]
0x180025f1e  mov     rbx, [rcx+rdi*8]
0x180025f22  cmp     dword ptr [rbx+4], 1
0x180025f26  jnz     short loc_180025F49
0x180025f28  mov     eax, [rbx+8]
0x180025f2b  and     eax, 19h
0x180025f2e  cmp     al, 19h
0x180025f30  jnz     short loc_180025F49
0x180025f32  cmp     dword ptr [rbx+0Ch], 1
0x180025f36  jnz     short loc_180025F49
0x180025f38  cmp     dword ptr [rbx+20h], 1Fh
0x180025f3c  jnz     short loc_180025F49
0x180025f3e  mov     rax, [rbx+18h]
0x180025f42  test    rax, rax
0x180025f45  jz      short loc_180025F85
0x180025f47  jmp     short loc_180025F58
0x180025f49  mov     rax, [rbx+18h]
0x180025f4d  test    rax, rax
0x180025f50  jz      short loc_180025F85
0x180025f52  cmp     dword ptr [rax+8], 1
0x180025f56  jnz     short loc_180025F85
0x180025f58  mov     rax, [rax+10h]
0x180025f5c  or      r9d, 0FFFFFFFFh; cchCount1
0x180025f60  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x180025f68  mov     r8, r15; lpString1
0x180025f6b  mov     rax, [rax]
0x180025f6e  lea     edx, [r9+2]; dwCmpFlags
0x180025f72  lea     ecx, [rdx+7Eh]; Locale
0x180025f75  mov     [rsp+68h+lpString2], rax; lpString2
0x180025f7a  call    cs:__imp_CompareStringW
0x180025f80  cmp     eax, 2
0x180025f83  jz      short loc_180025F89
0x180025f85  inc     edi
0x180025f87  jmp     short loc_180025F11
0x180025f89  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f90  lea     rax, WPP_GLOBAL_Control
0x180025f97  cmp     rcx, rax
0x180025f9a  jz      short loc_180025FBE
0x180025f9c  test    dword ptr [rcx+1Ch], 4000000h
0x180025fa3  jz      short loc_180025FBE
0x180025fa5  mov     r9, [rbx+28h]
0x180025fa9  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x180025fb0  mov     rcx, [rcx+10h]
0x180025fb4  mov     edx, 4Ah ; 'J'
0x180025fb9  call    WPP_SF_S
0x180025fbe  mov     rdx, [rbx+28h]; unsigned __int16 *
0x180025fc2  mov     rcx, r14; this
0x180025fc5  call    ?Copy@CPath@@QEAAJPEBG@Z; CPath::Copy(ushort const *)
0x180025fca  mov     esi, eax
0x180025fcc  mov     eax, esi
0x180025fce  add     rsp, 38h
0x180025fd2  pop     r15
0x180025fd4  pop     r14
0x180025fd6  pop     rdi
0x180025fd7  pop     rsi
0x180025fd8  pop     rbp
0x180025fd9  pop     rbx
0x180025fda  retn
```
