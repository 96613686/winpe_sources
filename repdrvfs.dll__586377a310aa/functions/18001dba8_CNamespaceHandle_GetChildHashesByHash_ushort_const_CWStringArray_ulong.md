# CNamespaceHandle::GetChildHashesByHash(ushort const *,CWStringArray &,ulong)

- ea: `0x18001dba8`
- end: `0x18001e12b`
- name: `?GetChildHashesByHash@CNamespaceHandle@@IEAAJPEBGAEAVCWStringArray@@K@Z`
- size: `1411`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, unsigned __int16 *, struct CWStringArray *, int)`
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001d844`
- `0x18001dba8`
- `0x180021adc`
- `0x1800355a8`
- `0x180035908`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180009920`
- `0x18000c500`
- `0x18001dba8`
- `0x18001e134`
- `0x180023528`
- `0x1800443f7`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001dbe9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001dd80`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001dbe9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001dd80`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001de6c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001de76`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001de93`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001de9d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001df8f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001df99`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001dff3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001e05d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001e067`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001e115`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001e11f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001de6c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001de76`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001de93`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001de9d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001df8f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001df99`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001dff3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001e05d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001e067`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001e115`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001e11f`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18001def2`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18001def2`
- `wbemcomn!GetMemLogObject` at `0x18001df2e`
- `wbemcomn!GetMemLogObject` at `0x18001dfa7`
- `wbemcomn!GetMemLogObject` at `0x18001e011`
- `wbemcomn!GetMemLogObject` at `0x18001e073`
- `wbemcomn!GetMemLogObject` at `0x18001df2e`
- `wbemcomn!GetMemLogObject` at `0x18001dfa7`
- `wbemcomn!GetMemLogObject` at `0x18001e011`
- `wbemcomn!GetMemLogObject` at `0x18001e073`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001df39`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001dfb7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001e021`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001e083`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001df39`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001dfb7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001e021`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001e083`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x18001de2e`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x18001de2e`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::GetChildHashesByHash(
        CNamespaceHandle *this,
        unsigned __int16 *a2,
        struct CWStringArray *a3,
        int a4)
{
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rbx
  __int64 v10; // r10
  __int64 v11; // rcx
  unsigned __int16 *v12; // r9
  __int64 v13; // rdx
  unsigned __int16 v14; // r11
  unsigned __int16 *v15; // rcx
  unsigned __int64 v16; // r9
  unsigned __int16 *v17; // rdx
  __int64 v18; // rax
  const wchar_t *v19; // rcx
  wchar_t v20; // r11
  unsigned __int16 *v21; // rcx
  unsigned __int64 v22; // r9
  unsigned __int16 *v23; // rdx
  __int64 v24; // rax
  unsigned __int16 v25; // cx
  unsigned __int16 *v26; // rcx
  __int64 v27; // rdx
  unsigned __int16 *v28; // rax
  __int64 v29; // r9
  const wchar_t *v30; // rcx
  __int64 v31; // r8
  unsigned __int16 *v32; // rax
  wchar_t v33; // dx
  unsigned __int16 *v34; // rdx
  unsigned __int16 *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  unsigned __int16 *v38; // rsi
  unsigned int v39; // eax
  unsigned int v40; // edi
  unsigned int v41; // edi
  const wchar_t *v43; // rax
  int ChildHashesByHash; // ebx
  CMemoryLog *v45; // rax
  CMemoryLog *v46; // rax
  CMemoryLog *v47; // rax
  CMemoryLog *MemLogObject; // rax
  void *v49; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v50[10]; // [rsp+28h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 397, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  if ( a4 == 2
    || !g_pSystemClassNamespace
    || (v43 = (const wchar_t *)WString::operator unsigned short *((char *)this + 32), !wcscmp_0(v43, L"__SYSTEMCLASS"))
    || (ChildHashesByHash = CNamespaceHandle::GetChildHashesByHash(g_pSystemClassNamespace, a2, a3, 0),
        ChildHashesByHash >= 0) )
  {
    v8 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x2E6u);
    v9 = v8;
    v50[1] = v8;
    if ( v8 )
    {
      *v8 = 0;
      v10 = 2147483646;
      v11 = 2147483646;
      v12 = (unsigned __int16 *)*((_QWORD *)this + 7);
      v13 = 371;
      do
      {
        if ( !v11 )
          break;
        v14 = *v12;
        if ( !*v12 )
          break;
        ++v12;
        *v8++ = v14;
        --v11;
        --v13;
      }
      while ( v13 );
      v15 = v8 - 1;
      if ( v13 )
        v15 = v8;
      *v15 = 0;
      v16 = (unsigned int)(371 - *((_DWORD *)this + 16));
      if ( *((_DWORD *)this + 16) != 371 )
      {
        v17 = &v9[*((int *)this + 16)];
        if ( v16 > 0x7FFFFFFF )
        {
          *v17 = 0;
        }
        else
        {
          v18 = 2147483646;
          v19 = L"\\CR_";
          do
          {
            if ( !v18 )
              break;
            v20 = *v19;
            if ( !*v19 )
              break;
            ++v19;
            *v17++ = v20;
            --v18;
            --v16;
          }
          while ( v16 );
          v21 = v17 - 1;
          if ( v16 )
            v21 = v17;
          *v21 = 0;
        }
      }
      v22 = (unsigned int)(370 - *((_DWORD *)this + 16)) - 3LL;
      if ( *((_DWORD *)this + 16) != 367 )
      {
        v23 = &v9[*((int *)this + 16) + 4];
        if ( v22 > 0x7FFFFFFF )
        {
          *v23 = 0;
        }
        else
        {
          v24 = 2147483646;
          do
          {
            if ( !v24 )
              break;
            v25 = *a2;
            if ( !*a2 )
              break;
            ++a2;
            *v23++ = v25;
            --v24;
            --v22;
          }
          while ( v22 );
          v26 = v23 - 1;
          if ( v22 )
            v26 = v23;
          *v26 = 0;
        }
      }
      v27 = 371;
      v28 = v9;
      do
      {
        if ( !*v28 )
          break;
        ++v28;
        --v27;
      }
      while ( v27 );
      v29 = (371 - v27) & -(__int64)(v27 != 0);
      if ( v27 )
      {
        v30 = L"\\C_";
        v31 = 371 - v29;
        v32 = &v9[v29];
        if ( 371 != v29 )
        {
          do
          {
            if ( !v10 )
              break;
            v33 = *v30;
            if ( !*v30 )
              break;
            ++v30;
            *v32++ = v33;
            --v10;
            --v31;
          }
          while ( v31 );
        }
        v34 = v32 - 1;
        if ( v31 )
          v34 = v32;
        *v34 = 0;
      }
      v49 = 0;
      v35 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x2E6u);
      v38 = v35;
      v50[0] = v35;
      if ( v35 )
      {
        *v35 = 0;
        if ( !dword_180058AFC || g_bShuttingDown )
        {
          v40 = 1255;
        }
        else if ( dword_180058F00 )
        {
          v39 = CBtrIndex::IndexEnumerationBegin((CBtrIndex *)&dword_180058F18, v9, &v49);
          v40 = v39;
          if ( v39 == 2 )
          {
            if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 402, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 0);
            }
LABEL_71:
            CWin32DefaultArena::WbemMemFree(v38);
            CWin32DefaultArena::WbemMemFree(v9);
            return 0;
          }
          if ( !v39 )
          {
            while ( 1 )
            {
              if ( !dword_180058AFC )
              {
                v40 = 1255;
                goto LABEL_56;
              }
              if ( g_bShuttingDown )
                break;
              v40 = CObjectHeap::IndexEnumerationNext((CObjectHeap *)&qword_180058EF8, v49, (struct CFileName *)v50, 0);
              if ( v40 )
                goto LABEL_50;
              if ( CWStringArray::Add(a3, v38 + 2) )
              {
                v40 = 14;
                goto LABEL_50;
              }
            }
            v40 = 1255;
LABEL_50:
            if ( dword_180058AFC )
            {
              if ( !g_bShuttingDown )
                CObjectHeap::IndexEnumerationEnd((CObjectHeap *)&qword_180058EF8, v49);
            }
            if ( v40 == 18 )
              goto LABEL_71;
          }
        }
        else
        {
          MemLogObject = GetMemLogObject();
          v40 = 4317;
          CMemoryLog::Write(MemLogObject, 4317);
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 4317);
          }
        }
LABEL_56:
        v41 = A51TranslateErrorCode(v40, v36, v37);
        CWin32DefaultArena::WbemMemFree(v38);
        CWin32DefaultArena::WbemMemFree(v9);
      }
      else
      {
        v47 = GetMemLogObject();
        v41 = -2147217402;
        CMemoryLog::Write(v47, -2147217402);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            401,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            2147749894LL);
        }
        CWin32DefaultArena::WbemMemFree(0);
        CWin32DefaultArena::WbemMemFree(v9);
      }
    }
    else
    {
      v46 = GetMemLogObject();
      v41 = -2147217402;
      CMemoryLog::Write(v46, -2147217402);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          399,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          2147749894LL);
      }
      CWin32DefaultArena::WbemMemFree(0);
    }
    return v41;
  }
  v45 = GetMemLogObject();
  CMemoryLog::Write(v45, ChildHashesByHash);
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      398,
      WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
      (unsigned int)ChildHashesByHash);
  }
  return (unsigned int)ChildHashesByHash;
}

```

## disassembly

```asm
0x18001dba8  push    rbx
0x18001dbaa  push    rbp
0x18001dbab  push    rsi
0x18001dbac  push    rdi
0x18001dbad  push    r13
0x18001dbaf  push    r14
0x18001dbb1  sub     rsp, 48h
0x18001dbb5  mov     ebx, r9d
0x18001dbb8  mov     rbp, r8
0x18001dbbb  mov     rsi, rdx
0x18001dbbe  mov     rdi, rcx
0x18001dbc1  lea     r13, WPP_GLOBAL_Control
0x18001dbc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dbcf  cmp     rcx, r13
0x18001dbd2  jnz     loc_18001DEB3
0x18001dbd8  xor     r14d, r14d
0x18001dbdb  cmp     ebx, 2
0x18001dbde  jnz     loc_18001DEE1
0x18001dbe4  mov     ecx, 2E6h
0x18001dbe9  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001dbef  mov     rbx, rax
0x18001dbf2  mov     [rsp+78h+var_48], rax
0x18001dbf7  test    rax, rax
0x18001dbfa  jz      short loc_18001DC00
0x18001dbfc  mov     [rax], r14w
0x18001dc00  test    rbx, rbx
0x18001dc03  jz      loc_18001DFA7
0x18001dc09  mov     r10d, 7FFFFFFEh
0x18001dc0f  mov     ecx, r10d
0x18001dc12  mov     r9, [rdi+38h]
0x18001dc16  mov     r8d, 173h
0x18001dc1c  mov     edx, r8d
0x18001dc1f  test    rcx, rcx
0x18001dc22  jz      short loc_18001DC43
0x18001dc24  movzx   r11d, word ptr [r9]
0x18001dc28  test    r11w, r11w
0x18001dc2c  jz      short loc_18001DC43
0x18001dc2e  add     r9, 2
0x18001dc32  mov     [rax], r11w
0x18001dc36  add     rax, 2
0x18001dc3a  dec     rcx
0x18001dc3d  sub     rdx, 1
0x18001dc41  jnz     short loc_18001DC1F
0x18001dc43  lea     rcx, [rax-2]
0x18001dc47  test    rdx, rdx
0x18001dc4a  cmovnz  rcx, rax
0x18001dc4e  mov     [rcx], r14w
0x18001dc52  mov     r9d, r8d
0x18001dc55  sub     r9d, [rdi+40h]
0x18001dc59  jz      short loc_18001DCAD
0x18001dc5b  movsxd  rax, dword ptr [rdi+40h]
0x18001dc5f  lea     rdx, [rbx+rax*2]
0x18001dc63  cmp     r9, 7FFFFFFFh
0x18001dc6a  ja      loc_18001DFFF
0x18001dc70  mov     rax, r10
0x18001dc73  lea     rcx, aCr; "\\CR_"
0x18001dc7a  test    rax, rax
0x18001dc7d  jz      short loc_18001DC9E
0x18001dc7f  movzx   r11d, word ptr [rcx]
0x18001dc83  test    r11w, r11w
0x18001dc87  jz      short loc_18001DC9E
0x18001dc89  add     rcx, 2
0x18001dc8d  mov     [rdx], r11w
0x18001dc91  add     rdx, 2
0x18001dc95  dec     rax
0x18001dc98  sub     r9, 1
0x18001dc9c  jnz     short loc_18001DC7A
0x18001dc9e  lea     rcx, [rdx-2]
0x18001dca2  test    r9, r9
0x18001dca5  cmovnz  rcx, rdx
0x18001dca9  mov     [rcx], r14w
0x18001dcad  mov     r9d, 172h
0x18001dcb3  sub     r9d, [rdi+40h]
0x18001dcb7  add     r9, 0FFFFFFFFFFFFFFFDh
0x18001dcbb  jz      short loc_18001DD09
0x18001dcbd  movsxd  rdx, dword ptr [rdi+40h]
0x18001dcc1  add     rdx, 4
0x18001dcc5  lea     rdx, [rbx+rdx*2]
0x18001dcc9  cmp     r9, 7FFFFFFFh
0x18001dcd0  ja      loc_18001E008
0x18001dcd6  mov     rax, r10
0x18001dcd9  test    rax, rax
0x18001dcdc  jz      short loc_18001DCFA
0x18001dcde  movzx   ecx, word ptr [rsi]
0x18001dce1  test    cx, cx
0x18001dce4  jz      short loc_18001DCFA
0x18001dce6  add     rsi, 2
0x18001dcea  mov     [rdx], cx
0x18001dced  add     rdx, 2
0x18001dcf1  dec     rax
0x18001dcf4  sub     r9, 1
0x18001dcf8  jnz     short loc_18001DCD9
0x18001dcfa  lea     rcx, [rdx-2]
0x18001dcfe  test    r9, r9
0x18001dd01  cmovnz  rcx, rdx
0x18001dd05  mov     [rcx], r14w
0x18001dd09  mov     rdx, r8
0x18001dd0c  mov     rax, rbx
0x18001dd0f  cmp     [rax], r14w
0x18001dd13  jz      short loc_18001DD1F
0x18001dd15  add     rax, 2
0x18001dd19  sub     rdx, 1
0x18001dd1d  jnz     short loc_18001DD0F
0x18001dd1f  mov     rax, rdx
0x18001dd22  mov     rcx, r8
0x18001dd25  sub     rcx, rdx
0x18001dd28  neg     rax
0x18001dd2b  sbb     r9, r9
0x18001dd2e  and     r9, rcx
0x18001dd31  test    rdx, rdx
0x18001dd34  jz      short loc_18001DD76
0x18001dd36  lea     rcx, aC; "\\C_"
0x18001dd3d  sub     r8, r9
0x18001dd40  lea     rax, [rbx+r9*2]
0x18001dd44  jz      short loc_18001DD67
0x18001dd46  test    r10, r10
0x18001dd49  jz      short loc_18001DD67
0x18001dd4b  movzx   edx, word ptr [rcx]
0x18001dd4e  test    dx, dx
0x18001dd51  jz      short loc_18001DD67
0x18001dd53  add     rcx, 2
0x18001dd57  mov     [rax], dx
0x18001dd5a  add     rax, 2
0x18001dd5e  dec     r10
0x18001dd61  sub     r8, 1
0x18001dd65  jnz     short loc_18001DD46
0x18001dd67  lea     rdx, [rax-2]
0x18001dd6b  test    r8, r8
0x18001dd6e  cmovnz  rdx, rax
0x18001dd72  mov     [rdx], r14w
0x18001dd76  mov     [rsp+78h+var_58], r14
0x18001dd7b  mov     ecx, 2E6h
0x18001dd80  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001dd86  mov     rsi, rax
0x18001dd89  mov     [rsp+78h+var_50], rax
0x18001dd8e  test    rax, rax
0x18001dd91  jz      short loc_18001DD97
0x18001dd93  mov     [rax], r14w
0x18001dd97  test    rsi, rsi
0x18001dd9a  jz      loc_18001E011
0x18001dda0  cmp     cs:dword_180058AFC, r14d
0x18001dda7  jz      loc_18001DE82
0x18001ddad  cmp     cs:?g_bShuttingDown@@3_NA, r14b; bool g_bShuttingDown
0x18001ddb4  jnz     loc_18001DE82
0x18001ddba  cmp     cs:dword_180058F00, r14d
0x18001ddc1  jz      loc_18001E073
0x18001ddc7  lea     r8, [rsp+78h+var_58]; void **
0x18001ddcc  mov     rdx, rbx; unsigned __int16 *
0x18001ddcf  lea     rcx, dword_180058F18; this
0x18001ddd6  call    ?IndexEnumerationBegin@CBtrIndex@@QEAAJPEBGPEAPEAX@Z; CBtrIndex::IndexEnumerationBegin(ushort const *,void * *)
0x18001dddb  mov     edi, eax
0x18001dddd  cmp     eax, 2
0x18001dde0  jz      loc_18001DF76
0x18001dde6  test    eax, eax
0x18001dde8  jnz     loc_18001DE87
0x18001ddee  cmp     cs:dword_180058AFC, r14d
0x18001ddf5  jz      loc_18001E104
0x18001ddfb  cmp     cs:?g_bShuttingDown@@3_NA, r14b; bool g_bShuttingDown
0x18001de02  jnz     loc_18001E0F1
0x18001de08  xor     r9d, r9d; bool
0x18001de0b  lea     r8, [rsp+78h+var_50]; struct CFileName *
0x18001de10  mov     rdx, [rsp+78h+var_58]; void *
0x18001de15  lea     rcx, qword_180058EF8; this
0x18001de1c  call    ?IndexEnumerationNext@CObjectHeap@@QEAAJPEAXAEAVCFileName@@_N@Z; CObjectHeap::IndexEnumerationNext(void *,CFileName &,bool)
0x18001de21  mov     edi, eax
0x18001de23  test    eax, eax
0x18001de25  jnz     short loc_18001DE3D
0x18001de27  lea     rdx, [rsi+4]
0x18001de2b  mov     rcx, rbp
0x18001de2e  call    cs:__imp_?Add@CWStringArray@@QEAAHPEBG@Z; CWStringArray::Add(ushort const *)
0x18001de34  test    eax, eax
0x18001de36  jz      short loc_18001DDEE
0x18001de38  mov     edi, 0Eh
0x18001de3d  cmp     cs:dword_180058AFC, r14d
0x18001de44  jz      short loc_18001DE60
0x18001de46  cmp     cs:?g_bShuttingDown@@3_NA, r14b; bool g_bShuttingDown
0x18001de4d  jnz     short loc_18001DE60
0x18001de4f  mov     rdx, [rsp+78h+var_58]; void *
0x18001de54  lea     rcx, qword_180058EF8; this
0x18001de5b  call    ?IndexEnumerationEnd@CObjectHeap@@QEAAJPEAX@Z; CObjectHeap::IndexEnumerationEnd(void *)
0x18001de60  cmp     edi, 12h
0x18001de63  jnz     loc_18001E0FB
0x18001de69  mov     rcx, rsi
0x18001de6c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001de72  nop
0x18001de73  mov     rcx, rbx
0x18001de76  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001de7c  nop
0x18001de7d  jmp     loc_18001DFA0
0x18001de82  mov     edi, 4E7h
0x18001de87  mov     ecx, edi; int
0x18001de89  call    ?A51TranslateErrorCode@@YAJJ@Z; A51TranslateErrorCode(long)
0x18001de8e  mov     edi, eax
0x18001de90  mov     rcx, rsi
0x18001de93  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001de99  nop
0x18001de9a  mov     rcx, rbx
0x18001de9d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001dea3  nop
0x18001dea4  mov     eax, edi
0x18001dea6  add     rsp, 48h
0x18001deaa  pop     r14
0x18001deac  pop     r13
0x18001deae  pop     rdi
0x18001deaf  pop     rsi
0x18001deb0  pop     rbp
0x18001deb1  pop     rbx
0x18001deb2  retn
0x18001deb3  test    byte ptr [rcx+1Ch], 1
0x18001deb7  jz      loc_18001DBD8
0x18001debd  cmp     byte ptr [rcx+19h], 5
0x18001dec1  jb      loc_18001DBD8
0x18001dec7  mov     edx, 18Dh
0x18001decc  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001ded3  mov     rcx, [rcx+10h]
0x18001ded7  call    WPP_SF_
0x18001dedc  jmp     loc_18001DBD8
0x18001dee1  cmp     cs:?g_pSystemClassNamespace@@3PEAVCNamespaceHandle@@EA, r14; CNamespaceHandle * g_pSystemClassNamespace
0x18001dee8  jz      loc_18001DBE4
0x18001deee  lea     rcx, [rdi+20h]
0x18001def2  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x18001def8  mov     rcx, rax; String1
0x18001defb  lea     rdx, aSystemclass; "__SYSTEMCLASS"
0x18001df02  call    wcscmp_0
0x18001df07  test    eax, eax
0x18001df09  jz      loc_18001DBE4
0x18001df0f  xor     r9d, r9d; unsigned int
0x18001df12  mov     r8, rbp; struct CWStringArray *
0x18001df15  mov     rdx, rsi; unsigned __int16 *
0x18001df18  mov     rcx, cs:?g_pSystemClassNamespace@@3PEAVCNamespaceHandle@@EA; this
0x18001df1f  call    ?GetChildHashesByHash@CNamespaceHandle@@IEAAJPEBGAEAVCWStringArray@@K@Z; CNamespaceHandle::GetChildHashesByHash(ushort const *,CWStringArray &,ulong)
0x18001df24  mov     ebx, eax
0x18001df26  test    eax, eax
0x18001df28  jns     loc_18001DBE4
0x18001df2e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001df34  mov     edx, ebx
0x18001df36  mov     rcx, rax
0x18001df39  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001df3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df46  cmp     rcx, r13
0x18001df49  jz      short loc_18001DF6F
0x18001df4b  test    byte ptr [rcx+1Ch], 1
0x18001df4f  jz      short loc_18001DF6F
0x18001df51  cmp     byte ptr [rcx+19h], 2
0x18001df55  jb      short loc_18001DF6F
0x18001df57  mov     edx, 18Eh
0x18001df5c  mov     r9d, ebx
0x18001df5f  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001df66  mov     rcx, [rcx+10h]
0x18001df6a  call    WPP_SF_d
0x18001df6f  mov     eax, ebx
0x18001df71  jmp     loc_18001DEA6
0x18001df76  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df7d  cmp     rcx, r13
0x18001df80  jz      short loc_18001DF8C
0x18001df82  test    byte ptr [rcx+1Ch], 1
0x18001df86  jnz     loc_18001E0CA
0x18001df8c  mov     rcx, rsi
0x18001df8f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001df95  nop
0x18001df96  mov     rcx, rbx
0x18001df99  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001df9f  nop
0x18001dfa0  xor     eax, eax
0x18001dfa2  jmp     loc_18001DEA6
0x18001dfa7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001dfad  mov     edi, 80041006h
0x18001dfb2  mov     edx, edi
0x18001dfb4  mov     rcx, rax
0x18001dfb7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001dfbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dfc4  cmp     rcx, r13
0x18001dfc7  jz      short loc_18001DFF1
0x18001dfc9  test    byte ptr [rcx+1Ch], 1
0x18001dfcd  jz      short loc_18001DFF1
0x18001dfcf  cmp     byte ptr [rcx+19h], 2
0x18001dfd3  jb      short loc_18001DFF1
0x18001dfd5  mov     edx, 18Fh
0x18001dfda  mov     r9d, 80041006h
0x18001dfe0  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001dfe7  mov     rcx, [rcx+10h]
0x18001dfeb  call    WPP_SF_d
0x18001dff0  nop
0x18001dff1  xor     ecx, ecx
0x18001dff3  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001dff9  nop
0x18001dffa  jmp     loc_18001DEA4
0x18001dfff  mov     [rdx], r14w
0x18001e003  jmp     loc_18001DCAD
0x18001e008  mov     [rdx], r14w
0x18001e00c  jmp     loc_18001DD09
0x18001e011  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001e017  mov     edi, 80041006h
0x18001e01c  mov     edx, edi
0x18001e01e  mov     rcx, rax
0x18001e021  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001e027  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e02e  cmp     rcx, r13
0x18001e031  jz      short loc_18001E05B
0x18001e033  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
