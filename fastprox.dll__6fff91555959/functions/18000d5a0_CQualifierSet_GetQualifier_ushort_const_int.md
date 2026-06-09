# CQualifierSet::GetQualifier(ushort const *,int &)

- ea: `0x18000d5a0`
- end: `0x18000ddd7`
- name: `?GetQualifier@CQualifierSet@@QEAAPEAUCQualifier@@PEBGAEAH@Z`
- size: `2103`
- prototype: `struct CQualifier *__fastcall(CQualifierSet *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `20`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002580`
- `0x180002600`
- `0x180007530`
- `0x18000b9a0`
- `0x180045fc0`
- `0x180059d70`
- `0x18005a240`
- `0x18005e7c0`
- `0x18005eeb0`
- `0x18005ef50`
- `0x18005f380`
- `0x18005f5a0`
- `0x180067b60`
- `0x180068ad0`
- `0x18006b8a0`
- `0x18006ca50`
- `0x180074550`
- `0x180078ae0`
- `0x1800814e0`
- `0x180081a40`

## callees

- `0x18000d5a0`
- `0x18000dde0`
- `0x180035b08`
- `0x18006fa4c`
- `0x180071c50`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000d77a`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000d7d0`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000d827`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000d9c1`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000da18`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000dca9`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000d77a`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000d7d0`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000d827`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000d9c1`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000da18`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000dca9`
- `wbemcomn!GetMemLogObject` at `0x18000dcf4`
- `wbemcomn!GetMemLogObject` at `0x18000dd77`
- `wbemcomn!GetMemLogObject` at `0x18000dcf4`
- `wbemcomn!GetMemLogObject` at `0x18000dd77`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000dd02`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000dd85`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000dd02`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000dd85`

## pseudocode

```c
struct CQualifier *__fastcall CQualifierSet::GetQualifier(unsigned int **this, unsigned __int16 *a2, int *a3)
{
  unsigned __int16 *v3; // r14
  unsigned int *v4; // rsi
  int v5; // edx
  int v6; // r12d
  int v7; // r15d
  _BYTE *j; // rbx
  WCHAR v9; // di
  unsigned int v10; // ecx
  unsigned int *v11; // r13
  __int64 v12; // rbx
  char * near *v13; // rcx
  unsigned __int16 *v14; // rdi
  int i; // r15d
  unsigned __int16 v16; // bx
  int v17; // ebx
  int v18; // ebx
  int v19; // ecx
  int v20; // eax
  unsigned int v21; // ecx
  __int64 v22; // rsi
  _QWORD *v23; // r13
  unsigned __int16 *v24; // r15
  unsigned __int64 v25; // r12
  __int64 v26; // rbx
  char * near *v27; // rcx
  unsigned __int16 *v28; // r14
  WCHAR *v29; // r15
  int v30; // edi
  WCHAR v31; // bx
  int v32; // ebx
  int v33; // ebx
  int v34; // ecx
  int v35; // eax
  unsigned int v36; // ecx
  int v38; // ecx
  int v39; // eax
  unsigned __int16 *k; // rdi
  int v41; // ebx
  int v42; // ebx
  unsigned __int64 v43; // rdx
  int v44; // ecx
  int v45; // eax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v47; // rax
  WCHAR DestStr; // [rsp+30h] [rbp-20h] BYREF
  unsigned int *v49; // [rsp+38h] [rbp-18h]
  CQualifierSet *pExceptionObject; // [rsp+90h] [rbp+40h] BYREF
  const unsigned __int16 *v51; // [rsp+98h] [rbp+48h]
  int *v52; // [rsp+A0h] [rbp+50h]
  WCHAR SrcStr; // [rsp+A8h] [rbp+58h] BYREF

  v52 = a3;
  v51 = a2;
  pExceptionObject = (CQualifierSet *)this;
  v3 = a2;
  v4 = this[2];
  v49 = this[3];
  if ( !mstatic_nNumStrings )
    mstatic_nNumStrings = 11;
  v5 = 1;
  v6 = 1;
LABEL_4:
  if ( v6 >= mstatic_nNumStrings )
  {
    v6 = -1;
    v11 = (unsigned int *)((char *)v4 + *(v4 - 1) - 4);
LABEL_18:
    while ( v4 < v11 )
    {
      v12 = *v4;
      if ( CFastHeap::IsFakeAddress(*v4) )
      {
        if ( !mstatic_nNumStrings )
          mstatic_nNumStrings = 11;
        LODWORD(v12) = v12 & 0x7FFFFFFF;
        if ( (unsigned int)v12 >= 0xB )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, -2);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              10,
              WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids,
              "CX_Exception()");
          }
          throw (CX_Exception *)&pExceptionObject;
        }
        _mm_lfence();
        v13 = (&mstatic_aszStrings)[v12];
      }
      else
      {
        if ( (unsigned int)v12 > *(_DWORD *)(*((_QWORD *)v49 + 1) + 4LL) )
          throw (CX_Exception *)&pExceptionObject;
        v13 = (char * near *)(*(_QWORD *)v49 + (unsigned int)v12);
      }
      v14 = (unsigned __int16 *)((char *)v13 + 1);
      if ( *(_BYTE *)v13 == 1 )
      {
        while ( *v14 || *v3 )
        {
          v42 = wbem_towlower(*v14);
          v18 = v42 - wbem_towlower(*v3);
          if ( v18 )
            goto LABEL_32;
          ++v14;
          ++v3;
        }
        v18 = 0;
      }
      else
      {
        for ( i = 117440512; i && (*(_BYTE *)v14 || *v3); --i )
        {
          v16 = *v3;
          if ( *v3 > 0x7Fu )
          {
            SrcStr = *v3;
            DestStr = 0;
            if ( LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, &DestStr, 1) )
              v16 = DestStr;
            else
              v16 = SrcStr;
          }
          else if ( (unsigned __int16)(v16 - 65) <= 0x19u )
          {
            v16 += 32;
          }
          v21 = *(unsigned __int8 *)v14;
          if ( v21 > 0x7F )
          {
            SrcStr = *(unsigned __int8 *)v14;
            DestStr = 0;
            if ( LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, &DestStr, 1) )
              LOWORD(v21) = DestStr;
            else
              LOWORD(v21) = SrcStr;
          }
          else if ( (unsigned __int16)(v21 - 65) <= 0x19u )
          {
            LOWORD(v21) = v21 + 32;
          }
          v17 = v16 - (unsigned __int16)v21;
          if ( v17 )
            goto LABEL_31;
          v14 = (unsigned __int16 *)((char *)v14 + 1);
          ++v3;
        }
        v17 = 0;
LABEL_31:
        v18 = -v17;
      }
LABEL_32:
      if ( !v18 )
        goto LABEL_56;
      v19 = *(unsigned int *)((char *)v4 + 5);
      if ( (v19 & 0xFFFu) > 0x7F )
      {
        v20 = 0;
      }
      else if ( (v19 & 0x2000) != 0 )
      {
        v20 = 4;
      }
      else
      {
        v20 = *((_DWORD *)&m_staticLengths + (v19 & 0xFFF));
      }
      v3 = (unsigned __int16 *)v51;
      v4 = (unsigned int *)((char *)v4 + (unsigned int)(v20 + 4) + 5);
    }
    v4 = 0;
LABEL_56:
    v5 = 1;
  }
  else
  {
    v7 = 117440512;
    for ( j = (char *)(&mstatic_aszStrings)[v6] + 1; v7 && (*j || *v3); ++j )
    {
      v9 = *v3;
      if ( *v3 > 0x7Fu )
      {
        DestStr = 0;
        SrcStr = v9;
        if ( LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, &DestStr, 1) )
          v9 = DestStr;
        else
          v9 = SrcStr;
      }
      else if ( (unsigned __int16)(v9 - 65) <= 0x19u )
      {
        v9 += 32;
      }
      v10 = (unsigned __int8)*j;
      if ( v10 > 0x7F )
      {
        DestStr = 0;
        SrcStr = v10;
        if ( LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, &DestStr, 1) )
          LOWORD(v10) = DestStr;
        else
          LOWORD(v10) = SrcStr;
      }
      else if ( (unsigned __int16)(v10 - 65) <= 0x19u )
      {
        LOWORD(v10) = v10 + 32;
      }
      v5 = 1;
      if ( v9 != (_WORD)v10 )
      {
        v3 = (unsigned __int16 *)v51;
        ++v6;
        goto LABEL_4;
      }
      --v7;
      ++v3;
    }
    v11 = (unsigned int *)((char *)v4 + *(v4 - 1) - 4);
    if ( v6 < 0 )
    {
      v3 = (unsigned __int16 *)v51;
      goto LABEL_18;
    }
    while ( v4 < v11 )
    {
      if ( v6 == (*v4 ^ 0x80000000) )
        goto LABEL_57;
      v38 = *(unsigned int *)((char *)v4 + 5);
      if ( (v38 & 0xFFFu) > 0x7F )
      {
        v4 = (unsigned int *)((char *)v4 + 9);
      }
      else
      {
        if ( (v38 & 0x2000) != 0 )
          v39 = 4;
        else
          v39 = *((_DWORD *)&m_staticLengths + (v38 & 0xFFF));
        v4 = (unsigned int *)((char *)v4 + (unsigned int)(v39 + 4) + 5);
      }
    }
    v4 = 0;
  }
LABEL_57:
  if ( !v4 )
  {
    if ( *((_DWORD *)pExceptionObject + 8) == 2 )
      return 0;
    v22 = *((_QWORD *)pExceptionObject + 7);
    if ( v6 >= 0 )
    {
      v4 = *(unsigned int **)(v22 + 8);
      v43 = (unsigned __int64)v4 + *(v4 - 1) - 4;
      while ( (unsigned __int64)v4 < v43 )
      {
        if ( v6 == (*v4 ^ 0x80000000) )
          goto LABEL_94;
        v44 = *(unsigned int *)((char *)v4 + 5);
        if ( (v44 & 0xFFFu) > 0x7F )
        {
          v4 = (unsigned int *)((char *)v4 + 9);
        }
        else
        {
          if ( (v44 & 0x2000) != 0 )
            v45 = 4;
          else
            v45 = *((_DWORD *)&m_staticLengths + (v44 & 0xFFF));
          v4 = (unsigned int *)((char *)v4 + (unsigned int)(v45 + 4) + 5);
        }
      }
    }
    else
    {
      v23 = *(_QWORD **)(v22 + 16);
      v4 = *(unsigned int **)(v22 + 8);
      v24 = (unsigned __int16 *)v51;
      v25 = (unsigned __int64)v4 + *(v4 - 1) - 4;
      v49 = (unsigned int *)v25;
      while ( (unsigned __int64)v4 < v25 )
      {
        v26 = *v4;
        if ( CFastHeap::IsFakeAddress(*v4) )
        {
          if ( !mstatic_nNumStrings )
            mstatic_nNumStrings = 11;
          LODWORD(v26) = v26 & 0x7FFFFFFF;
          if ( (unsigned int)v26 >= 0xB )
          {
            v47 = GetMemLogObject();
            CMemoryLog::Write(v47, -2);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                10,
                WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids,
                "CX_Exception()");
            }
            throw (CX_Exception *)&pExceptionObject;
          }
          _mm_lfence();
          v27 = (&mstatic_aszStrings)[v26];
        }
        else
        {
          if ( (unsigned int)v26 > *(_DWORD *)(v23[1] + 4LL) )
            throw (CX_Exception *)&pExceptionObject;
          v27 = (char * near *)(*v23 + (unsigned int)v26);
        }
        v28 = (unsigned __int16 *)((char *)v27 + 1);
        if ( *(_BYTE *)v27 == 1 )
        {
          for ( k = v24; *v28 || *k; ++k )
          {
            v41 = wbem_towlower(*v28);
            v33 = v41 - wbem_towlower(*k);
            if ( v33 )
              goto LABEL_75;
            ++v28;
          }
          v33 = 0;
        }
        else
        {
          v29 = (WCHAR *)v51;
          v30 = 117440512;
          v25 = (unsigned __int64)v49;
          while ( v30 && (*(_BYTE *)v28 || *v29) )
          {
            v31 = *v29;
            if ( *v29 > 0x7Fu )
            {
              SrcStr = *v29;
              DestStr = 0;
              if ( LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, &DestStr, 1) )
                v31 = DestStr;
              else
                v31 = SrcStr;
            }
            else if ( (unsigned __int16)(v31 - 65) <= 0x19u )
            {
              v31 += 32;
            }
            v36 = *(unsigned __int8 *)v28;
            if ( v36 > 0x7F )
            {
              SrcStr = *(unsigned __int8 *)v28;
              DestStr = 0;
              if ( LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, &DestStr, 1) )
                LOWORD(v36) = DestStr;
              else
                LOWORD(v36) = SrcStr;
            }
            else if ( (unsigned __int16)(v36 - 65) <= 0x19u )
            {
              LOWORD(v36) = v36 + 32;
            }
            v32 = v31 - (unsigned __int16)v36;
            if ( v32 )
              goto LABEL_74;
            --v30;
            v28 = (unsigned __int16 *)((char *)v28 + 1);
            ++v29;
          }
          v32 = 0;
LABEL_74:
          v24 = (unsigned __int16 *)v51;
          v33 = -v32;
        }
LABEL_75:
        if ( !v33 )
          goto LABEL_94;
        v34 = *(unsigned int *)((char *)v4 + 5);
        if ( (v34 & 0xFFFu) > 0x7F )
        {
          v35 = 0;
        }
        else if ( (v34 & 0x2000) != 0 )
        {
          v35 = 4;
        }
        else
        {
          v35 = *((_DWORD *)&m_staticLengths + (v34 & 0xFFF));
        }
        v4 = (unsigned int *)((char *)v4 + (unsigned int)(v35 + 4) + 5);
      }
    }
    v4 = 0;
LABEL_94:
    if ( !v4 || ((_BYTE)v4[1] & *((_BYTE *)pExceptionObject + 32)) == 0 )
      return 0;
    v5 = 0;
  }
  *v52 = v5;
  return (struct CQualifier *)v4;
}

```

## disassembly

```asm
0x18000d5a0  mov     [rsp-38h+arg_10], r8
0x18000d5a5  mov     [rsp-38h+arg_8], rdx
0x18000d5aa  mov     [rsp-38h+pExceptionObject], rcx
0x18000d5af  push    rbp
0x18000d5b0  push    rbx
0x18000d5b1  push    rsi
0x18000d5b2  push    rdi
0x18000d5b3  push    r12
0x18000d5b5  push    r14
0x18000d5b7  push    r15
0x18000d5b9  mov     rbp, rsp
0x18000d5bc  sub     rsp, 50h
0x18000d5c0  cmp     cs:?mstatic_nNumStrings@@3HA, 0; int mstatic_nNumStrings
0x18000d5c7  mov     r14, rdx
0x18000d5ca  mov     rax, [rcx+18h]
0x18000d5ce  mov     rsi, [rcx+10h]
0x18000d5d2  mov     [rbp+var_18], rax
0x18000d5d6  jz      loc_18000DC27
0x18000d5dc  mov     edx, 1
0x18000d5e1  mov     [rsp+50h+var_8], r13
0x18000d5e6  mov     r12d, edx
0x18000d5e9  cmp     r12d, cs:?mstatic_nNumStrings@@3HA; int mstatic_nNumStrings
0x18000d5f0  lea     rdi, __ImageBase
0x18000d5f7  jge     loc_18000D680
0x18000d5fd  movsxd  rax, r12d
0x18000d600  mov     r15d, 7000000h
0x18000d606  mov     rbx, ds:rva ?mstatic_aszStrings@@3PAPEADA[rdi+rax*8]; char * near * mstatic_aszStrings ...
0x18000d60e  inc     rbx
0x18000d611  test    r15d, r15d
0x18000d614  jz      short loc_18000D65F
0x18000d616  cmp     byte ptr [rbx], 0
0x18000d619  jnz     short loc_18000D622
0x18000d61b  cmp     word ptr [r14], 0
0x18000d620  jz      short loc_18000D65F
0x18000d622  movzx   edi, word ptr [r14]
0x18000d626  cmp     di, 7Fh
0x18000d62a  ja      loc_18000DC81
0x18000d630  lea     eax, [rdi-41h]
0x18000d633  cmp     ax, 19h
0x18000d637  ja      short loc_18000D63D
0x18000d639  add     di, 20h ; ' '
0x18000d63d  movzx   ecx, byte ptr [rbx]
0x18000d640  cmp     ecx, 7Fh
0x18000d643  ja      loc_18000D7FF
0x18000d649  lea     eax, [rcx-41h]
0x18000d64c  cmp     ax, 19h
0x18000d650  ja      loc_18000D839
0x18000d656  add     cx, 20h ; ' '
0x18000d65a  jmp     loc_18000D839
0x18000d65f  mov     r13d, [rsi-4]
0x18000d663  lea     rdi, __ImageBase
0x18000d66a  add     r13, 0FFFFFFFFFFFFFFFCh
0x18000d66e  add     r13, rsi
0x18000d671  test    r12d, r12d
0x18000d674  jns     loc_18000DA97
0x18000d67a  mov     r14, [rbp+arg_8]
0x18000d67e  jmp     short loc_18000D691
0x18000d680  mov     r13d, [rsi-4]
0x18000d684  mov     r12d, 0FFFFFFFFh
0x18000d68a  add     r13, 0FFFFFFFFFFFFFFFCh
0x18000d68e  add     r13, rsi
0x18000d691  cmp     rsi, r13
0x18000d694  jnb     loc_18000D88E
0x18000d69a  mov     ebx, [rsi]
0x18000d69c  mov     ecx, ebx; unsigned int
0x18000d69e  call    ?IsFakeAddress@CFastHeap@@SA_NK@Z; CFastHeap::IsFakeAddress(ulong)
0x18000d6a3  test    al, al
0x18000d6a5  jnz     loc_18000D852
0x18000d6ab  mov     rdi, [rbp+var_18]
0x18000d6af  mov     rax, [rdi+8]
0x18000d6b3  cmp     ebx, [rax+4]
0x18000d6b6  ja      loc_18000DC16
0x18000d6bc  mov     ecx, ebx
0x18000d6be  add     rcx, [rdi]
0x18000d6c1  cmp     byte ptr [rcx], 1
0x18000d6c4  lea     rdi, [rcx+1]
0x18000d6c8  jz      loc_18000DB70
0x18000d6ce  mov     r15d, 7000000h
0x18000d6d4  test    r15d, r15d
0x18000d6d7  jz      short loc_18000D705
0x18000d6d9  cmp     byte ptr [rdi], 0
0x18000d6dc  jnz     short loc_18000D6E5
0x18000d6de  cmp     word ptr [r14], 0
0x18000d6e3  jz      short loc_18000D705
0x18000d6e5  movzx   ebx, word ptr [r14]
0x18000d6e9  cmp     bx, 7Fh
0x18000d6ed  ja      short loc_18000D74D
0x18000d6ef  lea     eax, [rbx-41h]
0x18000d6f2  cmp     ax, 19h
0x18000d6f6  ja      loc_18000D78C
0x18000d6fc  add     bx, 20h ; ' '
0x18000d700  jmp     loc_18000D78C
0x18000d705  xor     ebx, ebx
0x18000d707  neg     ebx
0x18000d709  test    ebx, ebx
0x18000d70b  jz      loc_18000DC36
0x18000d711  mov     ecx, [rsi+5]
0x18000d714  mov     eax, ecx
0x18000d716  and     eax, 0FFFh
0x18000d71b  cmp     eax, 7Fh
0x18000d71e  ja      loc_18000DC58
0x18000d724  bt      ecx, 0Dh
0x18000d728  jnb     loc_18000DAFA
0x18000d72e  mov     eax, 4
0x18000d733  mov     r14, [rbp+arg_8]
0x18000d737  lea     ecx, [rax+4]
0x18000d73a  add     rsi, 5
0x18000d73e  lea     rdi, __ImageBase
0x18000d745  add     rsi, rcx
0x18000d748  jmp     loc_18000D691
0x18000d74d  xor     eax, eax
0x18000d74f  mov     [rbp+SrcStr], bx
0x18000d753  lea     rcx, [rbp+DestStr]
0x18000d757  mov     [rbp+DestStr], ax
0x18000d75b  mov     eax, 1
0x18000d760  lea     r8, [rbp+SrcStr]; lpSrcStr
0x18000d764  mov     [rsp+50h+cchDest], eax; cchDest
0x18000d768  mov     r9d, eax; cchSrc
0x18000d76b  mov     [rsp+50h+lpDestStr], rcx; lpDestStr
0x18000d770  mov     edx, 100h; dwMapFlags
0x18000d775  mov     ecx, 7Fh; Locale
0x18000d77a  call    cs:__imp_LCMapStringW
0x18000d780  test    eax, eax
0x18000d782  jnz     loc_18000DCE2
0x18000d788  movzx   ebx, [rbp+SrcStr]
0x18000d78c  movzx   ecx, byte ptr [rdi]
0x18000d78f  cmp     ecx, 7Fh
0x18000d792  ja      short loc_18000D7A3
0x18000d794  lea     eax, [rcx-41h]
0x18000d797  cmp     ax, 19h
0x18000d79b  ja      short loc_18000D7E2
0x18000d79d  add     cx, 20h ; ' '
0x18000d7a1  jmp     short loc_18000D7E2
0x18000d7a3  xor     eax, eax
0x18000d7a5  mov     [rbp+SrcStr], cx
0x18000d7a9  lea     rcx, [rbp+DestStr]
0x18000d7ad  mov     [rbp+DestStr], ax
0x18000d7b1  mov     eax, 1
0x18000d7b6  lea     r8, [rbp+SrcStr]; lpSrcStr
0x18000d7ba  mov     [rsp+50h+cchDest], eax; cchDest
0x18000d7be  mov     r9d, eax; cchSrc
0x18000d7c1  mov     [rsp+50h+lpDestStr], rcx; lpDestStr
0x18000d7c6  mov     edx, 100h; dwMapFlags
0x18000d7cb  mov     ecx, 7Fh; Locale
0x18000d7d0  call    cs:__imp_LCMapStringW
0x18000d7d6  test    eax, eax
0x18000d7d8  jnz     loc_18000DCEB
0x18000d7de  movzx   ecx, [rbp+SrcStr]
0x18000d7e2  movzx   eax, cx
0x18000d7e5  movzx   ebx, bx
0x18000d7e8  sub     ebx, eax
0x18000d7ea  jnz     loc_18000D707
0x18000d7f0  dec     r15d
0x18000d7f3  inc     rdi
0x18000d7f6  add     r14, 2
0x18000d7fa  jmp     loc_18000D6D4
0x18000d7ff  xor     eax, eax
0x18000d801  mov     [rsp+50h+cchDest], edx; cchDest
0x18000d805  mov     [rbp+DestStr], ax
0x18000d809  lea     r8, [rbp+SrcStr]; lpSrcStr
0x18000d80d  lea     rax, [rbp+DestStr]
0x18000d811  mov     [rbp+SrcStr], cx
0x18000d815  mov     r9d, edx; cchSrc
0x18000d818  mov     [rsp+50h+lpDestStr], rax; lpDestStr
0x18000d81d  mov     edx, 100h; dwMapFlags
0x18000d822  mov     ecx, 7Fh; Locale
0x18000d827  call    cs:__imp_LCMapStringW
0x18000d82d  test    eax, eax
0x18000d82f  jnz     loc_18000DCC7
0x18000d835  movzx   ecx, [rbp+SrcStr]
0x18000d839  mov     edx, 1
0x18000d83e  cmp     di, cx
0x18000d841  jnz     short loc_18000D882
0x18000d843  dec     r15d
0x18000d846  inc     rbx
0x18000d849  add     r14, 2
0x18000d84d  jmp     loc_18000D611
0x18000d852  cmp     cs:?mstatic_nNumStrings@@3HA, 0; int mstatic_nNumStrings
0x18000d859  jnz     short loc_18000D865
0x18000d85b  mov     cs:?mstatic_nNumStrings@@3HA, 0Bh; int mstatic_nNumStrings
0x18000d865  btr     ebx, 1Fh
0x18000d869  cmp     ebx, 0Bh
0x18000d86c  jnb     loc_18000DCF4
0x18000d872  lfence
0x18000d875  mov     rcx, ds:rva ?mstatic_aszStrings@@3PAPEADA[rdi+rbx*8]; char * near * mstatic_aszStrings ...
0x18000d87d  jmp     loc_18000D6C1
0x18000d882  mov     r14, [rbp+arg_8]
0x18000d886  inc     r12d
0x18000d889  jmp     loc_18000D5E9
0x18000d88e  xor     esi, esi
0x18000d890  mov     edx, 1
0x18000d895  test    rsi, rsi
0x18000d898  jnz     loc_18000DB26
0x18000d89e  mov     rcx, [rbp+pExceptionObject]
0x18000d8a2  cmp     dword ptr [rcx+20h], 2
0x18000d8a6  jz      loc_18000DA81
0x18000d8ac  mov     rsi, [rcx+38h]
0x18000d8b0  test    r12d, r12d
0x18000d8b3  jns     loc_18000DBA2
0x18000d8b9  mov     r13, [rsi+10h]
0x18000d8bd  mov     rsi, [rsi+8]
0x18000d8c1  mov     r12d, [rsi-4]
0x18000d8c5  lea     rax, [rsi-4]
0x18000d8c9  mov     r15, [rbp+arg_8]
0x18000d8cd  add     r12, rax
0x18000d8d0  mov     [rbp+var_18], r12
0x18000d8d4  cmp     rsi, r12
0x18000d8d7  jnb     loc_18000DA76
0x18000d8dd  mov     ebx, [rsi]
0x18000d8df  mov     ecx, ebx; unsigned int
0x18000d8e1  call    ?IsFakeAddress@CFastHeap@@SA_NK@Z; CFastHeap::IsFakeAddress(ulong)
0x18000d8e6  test    al, al
0x18000d8e8  jnz     loc_18000DA46
0x18000d8ee  mov     rax, [r13+8]
0x18000d8f2  cmp     ebx, [rax+4]
0x18000d8f5  ja      loc_18000DC05
0x18000d8fb  mov     ecx, ebx
0x18000d8fd  add     rcx, [r13+0]
0x18000d901  cmp     byte ptr [rcx], 1
0x18000d904  lea     r14, [rcx+1]
0x18000d908  jz      loc_18000DB34
0x18000d90e  mov     r15, [rbp+arg_8]
0x18000d912  mov     edi, 7000000h
0x18000d917  mov     r12, [rbp+var_18]
0x18000d91b  test    edi, edi
0x18000d91d  jz      short loc_18000D94C
0x18000d91f  cmp     byte ptr [r14], 0
0x18000d923  jnz     short loc_18000D92C
0x18000d925  cmp     word ptr [r15], 0
0x18000d92a  jz      short loc_18000D94C
0x18000d92c  movzx   ebx, word ptr [r15]
0x18000d930  cmp     bx, 7Fh
0x18000d934  ja      short loc_18000D994
0x18000d936  lea     eax, [rbx-41h]
0x18000d939  cmp     ax, 19h
0x18000d93d  ja      loc_18000D9D3
0x18000d943  add     bx, 20h ; ' '
0x18000d947  jmp     loc_18000D9D3
0x18000d94c  xor     ebx, ebx
0x18000d94e  mov     r15, [rbp+arg_8]
0x18000d952  neg     ebx
0x18000d954  test    ebx, ebx
0x18000d956  jz      loc_18000DA78
0x18000d95c  mov     ecx, [rsi+5]
0x18000d95f  mov     eax, ecx
0x18000d961  and     eax, 0FFFh
0x18000d966  cmp     eax, 7Fh
0x18000d969  ja      loc_18000DC51
0x18000d96f  bt      ecx, 0Dh
0x18000d973  jnb     loc_18000DAE1
0x18000d979  mov     eax, 4
0x18000d97e  lea     ecx, [rax+4]
0x18000d981  add     rsi, 5
0x18000d985  add     rsi, rcx
0x18000d988  lea     rdi, __ImageBase
0x18000d98f  jmp     loc_18000D8D4
0x18000d994  xor     eax, eax
0x18000d996  mov     [rbp+SrcStr], bx
0x18000d99a  lea     rcx, [rbp+DestStr]
0x18000d99e  mov     [rbp+DestStr], ax
0x18000d9a2  mov     eax, 1
0x18000d9a7  lea     r8, [rbp+SrcStr]; lpSrcStr
0x18000d9ab  mov     [rsp+50h+cchDest], eax; cchDest
0x18000d9af  mov     r9d, eax; cchSrc
0x18000d9b2  mov     [rsp+50h+lpDestStr], rcx; lpDestStr
0x18000d9b7  mov     edx, 100h; dwMapFlags
0x18000d9bc  mov     ecx, 7Fh; Locale
0x18000d9c1  call    cs:__imp_LCMapStringW
0x18000d9c7  test    eax, eax
0x18000d9c9  jnz     loc_18000DD65
0x18000d9cf  movzx   ebx, [rbp+SrcStr]
0x18000d9d3  movzx   ecx, byte ptr [r14]
0x18000d9d7  cmp     ecx, 7Fh
0x18000d9da  ja      short loc_18000D9EB
0x18000d9dc  lea     eax, [rcx-41h]
0x18000d9df  cmp     ax, 19h
0x18000d9e3  ja      short loc_18000DA2A
0x18000d9e5  add     cx, 20h ; ' '
0x18000d9e9  jmp     short loc_18000DA2A
0x18000d9eb  xor     eax, eax
0x18000d9ed  mov     [rbp+SrcStr], cx
0x18000d9f1  lea     rcx, [rbp+DestStr]
0x18000d9f5  mov     [rbp+DestStr], ax
0x18000d9f9  mov     eax, 1
0x18000d9fe  lea     r8, [rbp+SrcStr]; lpSrcStr
0x18000da02  mov     [rsp+50h+cchDest], eax; cchDest
0x18000da06  mov     r9d, eax; cchSrc
0x18000da09  mov     [rsp+50h+lpDestStr], rcx; lpDestStr
0x18000da0e  mov     edx, 100h; dwMapFlags
0x18000da13  mov     ecx, 7Fh; Locale
0x18000da18  call    cs:__imp_LCMapStringW
0x18000da1e  test    eax, eax
0x18000da20  jnz     loc_18000DD6E
0x18000da26  movzx   ecx, [rbp+SrcStr]
0x18000da2a  movzx   eax, cx
0x18000da2d  movzx   ebx, bx
0x18000da30  sub     ebx, eax
0x18000da32  jnz     loc_18000D94E
0x18000da38  dec     edi
0x18000da3a  inc     r14
  ... truncated ...
```
