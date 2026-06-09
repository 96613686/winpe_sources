# ReceiveParam_CParamElement_

- ea: `0x1808df490`
- end: `0x1808dfc3e`
- name: `ReceiveParam_CParamElement_`
- size: `1966`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, CParamElement *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1808e039c`

## callees

- `0x1808df490`
- `0x180e70a10`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1808df54e`
- `KERNEL32!CompareStringW` at `0x1808df641`
- `KERNEL32!CompareStringW` at `0x1808df6f4`
- `KERNEL32!CompareStringW` at `0x1808df7df`
- `KERNEL32!CompareStringW` at `0x1808df88f`
- `KERNEL32!CompareStringW` at `0x1808df93b`
- `KERNEL32!CompareStringW` at `0x1808df9da`
- `KERNEL32!CompareStringW` at `0x1808dfa79`
- `KERNEL32!CompareStringW` at `0x1808dfb18`
- `KERNEL32!CompareStringW` at `0x1808dfbbe`
- `KERNEL32!CompareStringW` at `0x1808df54e`
- `KERNEL32!CompareStringW` at `0x1808df641`
- `KERNEL32!CompareStringW` at `0x1808df6f4`
- `KERNEL32!CompareStringW` at `0x1808df7df`
- `KERNEL32!CompareStringW` at `0x1808df88f`
- `KERNEL32!CompareStringW` at `0x1808df93b`
- `KERNEL32!CompareStringW` at `0x1808df9da`
- `KERNEL32!CompareStringW` at `0x1808dfa79`
- `KERNEL32!CompareStringW` at `0x1808dfb18`
- `KERNEL32!CompareStringW` at `0x1808dfbbe`
- `OLEAUT32!__imp_SysFreeString` at `0x1808dfc20`
- `OLEAUT32!__imp_SysFreeString` at `0x1808dfc20`
- `OLEAUT32!__imp_SysStringLen` at `0x1808df59f`
- `OLEAUT32!__imp_SysStringLen` at `0x1808df745`
- `OLEAUT32!__imp_SysStringLen` at `0x1808dfc03`
- `OLEAUT32!__imp_SysStringLen` at `0x1808df59f`
- `OLEAUT32!__imp_SysStringLen` at `0x1808df745`
- `OLEAUT32!__imp_SysStringLen` at `0x1808dfc03`

## string_xrefs

- `0x1808df672`: `allowscriptaccess`

## pseudocode

```c
void __fastcall ReceiveParam_CParamElement_(PCNZWCH lpString1, CParamElement *this, __int64 a3)
{
  const WCHAR *lpString2; // r9
  PCNZWCH v6; // rbx
  PCNZWCH i; // r8
  WCHAR v8; // dx
  WCHAR v9; // cx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  OLECHAR *v13; // rbx
  const WCHAR *v14; // r8
  const wchar_t *v15; // r9
  WCHAR v16; // dx
  WCHAR v17; // cx
  int v18; // eax
  int v19; // eax
  const WCHAR *v20; // r8
  const WCHAR *j; // r9
  WCHAR v22; // dx
  WCHAR v23; // cx
  int v24; // eax
  int v25; // eax
  int value; // eax
  const WCHAR *v27; // r8
  const WCHAR *v28; // r9
  WCHAR v29; // dx
  WCHAR v30; // cx
  int v31; // eax
  int v32; // eax
  const WCHAR *v33; // r8
  const WCHAR *v34; // r9
  WCHAR v35; // dx
  WCHAR v36; // cx
  int v37; // eax
  int v38; // eax
  const WCHAR *v39; // r8
  const WCHAR *v40; // r9
  WCHAR v41; // dx
  WCHAR v42; // cx
  int v43; // eax
  int v44; // eax
  const WCHAR *v45; // r8
  const WCHAR *v46; // r9
  WCHAR v47; // dx
  WCHAR v48; // cx
  int v49; // eax
  int v50; // eax
  const WCHAR *v51; // r8
  const WCHAR *v52; // r9
  WCHAR v53; // dx
  WCHAR v54; // cx
  int v55; // eax
  int v56; // eax
  const WCHAR *v57; // r8
  const WCHAR *v58; // r9
  WCHAR v59; // dx
  WCHAR v60; // cx
  int v61; // eax
  int v62; // eax
  const WCHAR *v63; // r8
  WCHAR v64; // dx
  WCHAR v65; // cx
  int v66; // eax
  int v67; // eax
  int v68; // eax
  OLECHAR *v69; // rax
  BSTR pbstr; // [rsp+80h] [rbp+8h] BYREF

  if ( !lpString1 )
    return;
  lpString2 = L"allowfullscreen";
  v6 = lpString1;
  for ( i = lpString1; ; ++i )
  {
    v8 = *i;
    v9 = *lpString2;
    if ( !*i )
      break;
    if ( v8 == v9 )
      goto LABEL_11;
    if ( (unsigned __int16)(v8 - 65) > 0x19u )
    {
      if ( (unsigned __int16)(v9 - 65) > 0x19u )
        goto LABEL_12;
    }
    else
    {
      v8 += 32;
      if ( (unsigned __int16)(v9 - 65) > 0x19u )
        goto LABEL_10;
    }
    v9 += 32;
LABEL_10:
    if ( v8 != v9 )
    {
LABEL_12:
      if ( ((v8 | v9) & 0xFF80) != 0 )
      {
        v10 = CompareStringW(0, 0x31001u, i, -1, lpString2, -1);
        if ( v10 > 0 )
        {
          v11 = v10 - 2;
          goto LABEL_16;
        }
      }
      goto LABEL_36;
    }
LABEL_11:
    ++lpString2;
  }
  v11 = -(v9 != 0);
LABEL_16:
  if ( v11 )
  {
LABEL_36:
    v20 = v6;
    for ( j = L"allowscriptaccess"; ; ++j )
    {
      v22 = *v20;
      v23 = *j;
      if ( !*v20 )
      {
        v25 = -(v23 != 0);
LABEL_50:
        if ( !v25 )
        {
          pbstr = 0;
          value = CParamElement::get_value(this, &pbstr);
          v13 = pbstr;
          if ( value < 0 || !SysStringLen(pbstr) )
            goto LABEL_164;
          v27 = v13;
          if ( !v13 )
            goto LABEL_69;
          v28 = L"always";
          while ( 2 )
          {
            v29 = *v27;
            v30 = *v28;
            if ( !*v27 )
            {
              v32 = -(v30 != 0);
              goto LABEL_68;
            }
            if ( v29 != v30 )
            {
              if ( (unsigned __int16)(v29 - 65) > 0x19u )
              {
                if ( (unsigned __int16)(v30 - 65) > 0x19u )
                  goto LABEL_64;
LABEL_61:
                v30 += 32;
              }
              else
              {
                v29 += 32;
                if ( (unsigned __int16)(v30 - 65) <= 0x19u )
                  goto LABEL_61;
              }
              if ( v29 != v30 )
              {
LABEL_64:
                if ( ((v29 | v30) & 0xFF80) != 0 )
                {
                  v31 = CompareStringW(0, 0x31001u, v27, -1, v28, -1);
                  if ( v31 > 0 )
                  {
                    v32 = v31 - 2;
LABEL_68:
                    if ( !v32 )
                      goto LABEL_85;
                  }
                }
LABEL_69:
                v33 = v13;
                if ( !v13 )
                  goto LABEL_164;
                v34 = L"samedomain";
                while ( 2 )
                {
                  v35 = *v33;
                  v36 = *v34;
                  if ( !*v33 )
                  {
                    v38 = -(v36 != 0);
                    goto LABEL_84;
                  }
                  if ( v35 != v36 )
                  {
                    if ( (unsigned __int16)(v35 - 65) > 0x19u )
                    {
                      if ( (unsigned __int16)(v36 - 65) > 0x19u )
                        goto LABEL_80;
LABEL_77:
                      v36 += 32;
                    }
                    else
                    {
                      v35 += 32;
                      if ( (unsigned __int16)(v36 - 65) <= 0x19u )
                        goto LABEL_77;
                    }
                    if ( v35 != v36 )
                    {
LABEL_80:
                      if ( ((v35 | v36) & 0xFF80) == 0 )
                        goto LABEL_164;
                      v37 = CompareStringW(0, 0x31001u, v33, -1, v34, -1);
                      if ( v37 <= 0 )
                        goto LABEL_164;
                      v38 = v37 - 2;
LABEL_84:
                      if ( v38 )
                        goto LABEL_164;
LABEL_85:
                      *(_BYTE *)(a3 + 1) = 1;
                      goto LABEL_164;
                    }
                  }
                  ++v33;
                  ++v34;
                  continue;
                }
              }
            }
            ++v27;
            ++v28;
            continue;
          }
        }
LABEL_86:
        v39 = v6;
        v40 = L"movie";
        while ( 2 )
        {
          v41 = *v39;
          v42 = *v40;
          if ( !*v39 )
          {
            v44 = -(v42 != 0);
            goto LABEL_100;
          }
          if ( v41 != v42 )
          {
            if ( (unsigned __int16)(v41 - 65) > 0x19u )
            {
              if ( (unsigned __int16)(v42 - 65) > 0x19u )
                goto LABEL_96;
LABEL_93:
              v42 += 32;
            }
            else
            {
              v41 += 32;
              if ( (unsigned __int16)(v42 - 65) <= 0x19u )
                goto LABEL_93;
            }
            if ( v41 != v42 )
            {
LABEL_96:
              if ( ((v41 | v42) & 0xFF80) != 0 )
              {
                v43 = CompareStringW(0, 0x31001u, v39, -1, v40, -1);
                if ( v43 > 0 )
                {
                  v44 = v43 - 2;
LABEL_100:
                  if ( !v44 )
                    goto LABEL_161;
                }
              }
              v45 = v6;
              v46 = L"src";
              while ( 2 )
              {
                v47 = *v45;
                v48 = *v46;
                if ( !*v45 )
                {
                  v50 = -(v48 != 0);
                  goto LABEL_115;
                }
                if ( v47 != v48 )
                {
                  if ( (unsigned __int16)(v47 - 65) > 0x19u )
                  {
                    if ( (unsigned __int16)(v48 - 65) > 0x19u )
                      goto LABEL_111;
LABEL_108:
                    v48 += 32;
                  }
                  else
                  {
                    v47 += 32;
                    if ( (unsigned __int16)(v48 - 65) <= 0x19u )
                      goto LABEL_108;
                  }
                  if ( v47 != v48 )
                  {
LABEL_111:
                    if ( ((v47 | v48) & 0xFF80) != 0 )
                    {
                      v49 = CompareStringW(0, 0x31001u, v45, -1, v46, -1);
                      if ( v49 > 0 )
                      {
                        v50 = v49 - 2;
LABEL_115:
                        if ( !v50 )
                          goto LABEL_161;
                      }
                    }
                    v51 = v6;
                    v52 = L"filename";
                    while ( 2 )
                    {
                      v53 = *v51;
                      v54 = *v52;
                      if ( !*v51 )
                      {
                        v56 = -(v54 != 0);
                        goto LABEL_130;
                      }
                      if ( v53 != v54 )
                      {
                        if ( (unsigned __int16)(v53 - 65) > 0x19u )
                        {
                          if ( (unsigned __int16)(v54 - 65) > 0x19u )
                            goto LABEL_126;
LABEL_123:
                          v54 += 32;
                        }
                        else
                        {
                          v53 += 32;
                          if ( (unsigned __int16)(v54 - 65) <= 0x19u )
                            goto LABEL_123;
                        }
                        if ( v53 != v54 )
                        {
LABEL_126:
                          if ( ((v53 | v54) & 0xFF80) != 0 )
                          {
                            v55 = CompareStringW(0, 0x31001u, v51, -1, v52, -1);
                            if ( v55 > 0 )
                            {
                              v56 = v55 - 2;
LABEL_130:
                              if ( !v56 )
                                goto LABEL_161;
                            }
                          }
                          v57 = v6;
                          v58 = L"url";
                          while ( 2 )
                          {
                            v59 = *v57;
                            v60 = *v58;
                            if ( !*v57 )
                            {
                              v62 = -(v60 != 0);
                              goto LABEL_145;
                            }
                            if ( v59 != v60 )
                            {
                              if ( (unsigned __int16)(v59 - 65) > 0x19u )
                              {
                                if ( (unsigned __int16)(v60 - 65) > 0x19u )
                                  goto LABEL_141;
LABEL_138:
                                v60 += 32;
                              }
                              else
                              {
                                v59 += 32;
                                if ( (unsigned __int16)(v60 - 65) <= 0x19u )
                                  goto LABEL_138;
                              }
                              if ( v59 != v60 )
                              {
LABEL_141:
                                if ( ((v59 | v60) & 0xFF80) != 0 )
                                {
                                  v61 = CompareStringW(0, 0x31001u, v57, -1, v58, -1);
                                  if ( v61 > 0 )
                                  {
                                    v62 = v61 - 2;
LABEL_145:
                                    if ( !v62 )
                                      goto LABEL_161;
                                  }
                                }
                                v63 = L"source";
                                while ( 2 )
                                {
                                  v64 = *v6;
                                  v65 = *v63;
                                  if ( !*v6 )
                                  {
                                    v67 = -(v65 != 0);
                                    goto LABEL_160;
                                  }
                                  if ( v64 != v65 )
                                  {
                                    if ( (unsigned __int16)(v64 - 65) > 0x19u )
                                    {
                                      if ( (unsigned __int16)(v65 - 65) > 0x19u )
                                        goto LABEL_156;
LABEL_153:
                                      v65 += 32;
                                    }
                                    else
                                    {
                                      v64 += 32;
                                      if ( (unsigned __int16)(v65 - 65) <= 0x19u )
                                        goto LABEL_153;
                                    }
                                    if ( v64 != v65 )
                                    {
LABEL_156:
                                      if ( ((v64 | v65) & 0xFF80) == 0 )
                                        return;
                                      v66 = CompareStringW(0, 0x31001u, v6, -1, v63, -1);
                                      if ( v66 <= 0 )
                                        return;
                                      v67 = v66 - 2;
LABEL_160:
                                      if ( v67 )
                                        return;
LABEL_161:
                                      pbstr = 0;
                                      v68 = CParamElement::get_value(this, &pbstr);
                                      v13 = pbstr;
                                      if ( v68 >= 0 && SysStringLen(pbstr) )
                                      {
                                        v69 = v13;
                                        v13 = 0;
                                        *(_QWORD *)(a3 + 8) = v69;
                                      }
                                      goto LABEL_164;
                                    }
                                  }
                                  ++v6;
                                  ++v63;
                                  continue;
                                }
                              }
                            }
                            ++v57;
                            ++v58;
                            continue;
                          }
                        }
                      }
                      ++v51;
                      ++v52;
                      continue;
                    }
                  }
                }
                ++v45;
                ++v46;
                continue;
              }
            }
          }
          ++v39;
          ++v40;
          continue;
        }
      }
      if ( v22 != v23 )
        break;
LABEL_45:
      ++v20;
    }
    if ( (unsigned __int16)(v22 - 65) > 0x19u )
    {
      if ( (unsigned __int16)(v23 - 65) > 0x19u )
        goto LABEL_46;
    }
    else
    {
      v22 += 32;
      if ( (unsigned __int16)(v23 - 65) > 0x19u )
        goto LABEL_44;
    }
    v23 += 32;
LABEL_44:
    if ( v22 != v23 )
    {
LABEL_46:
      if ( ((v22 | v23) & 0xFF80) != 0 )
      {
        v24 = CompareStringW(0, 0x31001u, v20, -1, j, -1);
        if ( v24 > 0 )
        {
          v25 = v24 - 2;
          goto LABEL_50;
        }
      }
      goto LABEL_86;
    }
    goto LABEL_45;
  }
  pbstr = 0;
  v12 = CParamElement::get_value(this, &pbstr);
  v13 = pbstr;
  if ( v12 < 0 )
    goto LABEL_164;
  if ( !SysStringLen(pbstr) )
    goto LABEL_164;
  v14 = v13;
  if ( !v13 )
    goto LABEL_164;
  v15 = L"true";
  while ( 2 )
  {
    v16 = *v14;
    v17 = *v15;
    if ( !*v14 )
    {
      v19 = -(v17 != 0);
LABEL_34:
      if ( !v19 )
        *(_BYTE *)a3 = 1;
      goto LABEL_164;
    }
    if ( v16 == v17 )
      goto LABEL_29;
    if ( (unsigned __int16)(v16 - 65) > 0x19u )
    {
      if ( (unsigned __int16)(v17 - 65) > 0x19u )
        break;
LABEL_27:
      v17 += 32;
    }
    else
    {
      v16 += 32;
      if ( (unsigned __int16)(v17 - 65) <= 0x19u )
        goto LABEL_27;
    }
    if ( v16 == v17 )
    {
LABEL_29:
      ++v14;
      ++v15;
      continue;
    }
    break;
  }
  if ( ((v16 | v17) & 0xFF80) != 0 )
  {
    v18 = CompareStringW(0, 0x31001u, v14, -1, v15, -1);
    if ( v18 > 0 )
    {
      v19 = v18 - 2;
      goto LABEL_34;
    }
  }
LABEL_164:
  SysFreeString(v13);
}

```

## disassembly

```asm
0x1808df490  test    rcx, rcx
0x1808df493  jz      locret_1808DFC3C
0x1808df499  push    rbx
0x1808df49a  push    rbp
0x1808df49b  push    rsi
0x1808df49c  push    rdi
0x1808df49d  push    r12
0x1808df49f  push    r13
0x1808df4a1  push    r14
0x1808df4a3  push    r15
0x1808df4a5  sub     rsp, 38h
0x1808df4a9  xor     ebp, ebp
0x1808df4ab  lea     r9, aAllowfullscree_0; "allowfullscreen"
0x1808df4b2  mov     rsi, r8
0x1808df4b5  mov     rdi, rdx
0x1808df4b8  mov     rbx, rcx
0x1808df4bb  mov     r8, rcx; lpString1
0x1808df4be  mov     r15w, 41h ; 'A'
0x1808df4c3  mov     r12w, 19h
0x1808df4c8  lea     r13d, [rbp+2]
0x1808df4cc  mov     r14w, 20h ; ' '
0x1808df4d1  movzx   edx, word ptr [r8]
0x1808df4d5  or      r10d, 0FFFFFFFFh
0x1808df4d9  movzx   ecx, word ptr [r9]
0x1808df4dd  test    dx, dx
0x1808df4e0  jz      loc_1808DF567
0x1808df4e6  cmp     dx, cx
0x1808df4e9  jz      short loc_1808DF51E
0x1808df4eb  movzx   eax, dx
0x1808df4ee  sub     ax, r15w
0x1808df4f2  cmp     ax, r12w
0x1808df4f6  movzx   eax, cx
0x1808df4f9  ja      short loc_1808DF50B
0x1808df4fb  add     dx, r14w
0x1808df4ff  sub     ax, r15w
0x1808df503  cmp     ax, r12w
0x1808df507  ja      short loc_1808DF519
0x1808df509  jmp     short loc_1808DF515
0x1808df50b  sub     ax, r15w
0x1808df50f  cmp     ax, r12w
0x1808df513  ja      short loc_1808DF526
0x1808df515  add     cx, r14w
0x1808df519  cmp     dx, cx
0x1808df51c  jnz     short loc_1808DF526
0x1808df51e  add     r8, r13
0x1808df521  add     r9, r13
0x1808df524  jmp     short loc_1808DF4D1
0x1808df526  movzx   ecx, cx
0x1808df529  movzx   eax, dx
0x1808df52c  or      ecx, eax
0x1808df52e  test    ecx, 0FFFFFF80h
0x1808df534  jz      loc_1808DF66F
0x1808df53a  mov     [rsp+78h+cchCount2], r10d; cchCount2
0x1808df53f  mov     edx, 31001h; dwCmpFlags
0x1808df544  mov     [rsp+78h+lpString2], r9; lpString2
0x1808df549  xor     ecx, ecx; Locale
0x1808df54b  mov     r9d, r10d; cchCount1
0x1808df54e  call    cs:__imp_CompareStringW
0x1808df555  nop     dword ptr [rax+rax+00h]
0x1808df55a  test    eax, eax
0x1808df55c  jle     loc_1808DF66F
0x1808df562  add     eax, 0FFFFFFFEh
0x1808df565  jmp     short loc_1808DF56C
0x1808df567  neg     cx
0x1808df56a  sbb     eax, eax
0x1808df56c  test    eax, eax
0x1808df56e  jnz     loc_1808DF66F
0x1808df574  lea     rdx, [rsp+78h+pbstr]; unsigned __int16 **
0x1808df57c  mov     [rsp+78h+pbstr], rbp
0x1808df584  mov     rcx, rdi; this
0x1808df587  call    ?get_value@CParamElement@@QEAAJPEAPEAG@Z; CParamElement::get_value(ushort * *)
0x1808df58c  mov     rbx, [rsp+78h+pbstr]
0x1808df594  test    eax, eax
0x1808df596  js      loc_1808DFC1D
0x1808df59c  mov     rcx, rbx; pbstr
0x1808df59f  call    cs:__imp_SysStringLen
0x1808df5a6  nop     dword ptr [rax+rax+00h]
0x1808df5ab  test    eax, eax
0x1808df5ad  jz      loc_1808DFC1D
0x1808df5b3  mov     r8, rbx; lpString1
0x1808df5b6  test    rbx, rbx
0x1808df5b9  jz      loc_1808DFC1D
0x1808df5bf  lea     r9, aTrue; "true"
0x1808df5c6  movzx   edx, word ptr [r8]
0x1808df5ca  movzx   ecx, word ptr [r9]
0x1808df5ce  test    dx, dx
0x1808df5d1  jz      loc_1808DF65A
0x1808df5d7  cmp     dx, cx
0x1808df5da  jz      short loc_1808DF60F
0x1808df5dc  movzx   eax, dx
0x1808df5df  sub     ax, r15w
0x1808df5e3  cmp     ax, r12w
0x1808df5e7  movzx   eax, cx
0x1808df5ea  ja      short loc_1808DF5FC
0x1808df5ec  add     dx, r14w
0x1808df5f0  sub     ax, r15w
0x1808df5f4  cmp     ax, r12w
0x1808df5f8  ja      short loc_1808DF60A
0x1808df5fa  jmp     short loc_1808DF606
0x1808df5fc  sub     ax, r15w
0x1808df600  cmp     ax, r12w
0x1808df604  ja      short loc_1808DF617
0x1808df606  add     cx, r14w
0x1808df60a  cmp     dx, cx
0x1808df60d  jnz     short loc_1808DF617
0x1808df60f  add     r8, r13
0x1808df612  add     r9, r13
0x1808df615  jmp     short loc_1808DF5C6
0x1808df617  movzx   ecx, cx
0x1808df61a  movzx   eax, dx
0x1808df61d  or      ecx, eax
0x1808df61f  test    ecx, 0FFFFFF80h
0x1808df625  jz      loc_1808DFC1D
0x1808df62b  or      eax, 0FFFFFFFFh
0x1808df62e  mov     edx, 31001h; dwCmpFlags
0x1808df633  mov     [rsp+78h+cchCount2], eax; cchCount2
0x1808df637  xor     ecx, ecx; Locale
0x1808df639  mov     [rsp+78h+lpString2], r9; lpString2
0x1808df63e  mov     r9d, eax; cchCount1
0x1808df641  call    cs:__imp_CompareStringW
0x1808df648  nop     dword ptr [rax+rax+00h]
0x1808df64d  test    eax, eax
0x1808df64f  jle     loc_1808DFC1D
0x1808df655  add     eax, 0FFFFFFFEh
0x1808df658  jmp     short loc_1808DF65F
0x1808df65a  neg     cx
0x1808df65d  sbb     eax, eax
0x1808df65f  test    eax, eax
0x1808df661  jnz     loc_1808DFC1D
0x1808df667  mov     byte ptr [rsi], 1
0x1808df66a  jmp     loc_1808DFC1D
0x1808df66f  mov     r8, rbx; lpString1
0x1808df672  lea     r9, aAllowscriptacc; "allowscriptaccess"
0x1808df679  movzx   edx, word ptr [r8]
0x1808df67d  movzx   ecx, word ptr [r9]
0x1808df681  test    dx, dx
0x1808df684  jz      loc_1808DF70D
0x1808df68a  cmp     dx, cx
0x1808df68d  jz      short loc_1808DF6C2
0x1808df68f  movzx   eax, dx
0x1808df692  sub     ax, r15w
0x1808df696  cmp     ax, r12w
0x1808df69a  movzx   eax, cx
0x1808df69d  ja      short loc_1808DF6AF
0x1808df69f  add     dx, r14w
0x1808df6a3  sub     ax, r15w
0x1808df6a7  cmp     ax, r12w
0x1808df6ab  ja      short loc_1808DF6BD
0x1808df6ad  jmp     short loc_1808DF6B9
0x1808df6af  sub     ax, r15w
0x1808df6b3  cmp     ax, r12w
0x1808df6b7  ja      short loc_1808DF6CA
0x1808df6b9  add     cx, r14w
0x1808df6bd  cmp     dx, cx
0x1808df6c0  jnz     short loc_1808DF6CA
0x1808df6c2  add     r8, r13
0x1808df6c5  add     r9, r13
0x1808df6c8  jmp     short loc_1808DF679
0x1808df6ca  movzx   ecx, cx
0x1808df6cd  movzx   eax, dx
0x1808df6d0  or      ecx, eax
0x1808df6d2  test    ecx, 0FFFFFF80h
0x1808df6d8  jz      loc_1808DF8BE
0x1808df6de  or      eax, 0FFFFFFFFh
0x1808df6e1  mov     edx, 31001h; dwCmpFlags
0x1808df6e6  mov     [rsp+78h+cchCount2], eax; cchCount2
0x1808df6ea  xor     ecx, ecx; Locale
0x1808df6ec  mov     [rsp+78h+lpString2], r9; lpString2
0x1808df6f1  mov     r9d, eax; cchCount1
0x1808df6f4  call    cs:__imp_CompareStringW
0x1808df6fb  nop     dword ptr [rax+rax+00h]
0x1808df700  test    eax, eax
0x1808df702  jle     loc_1808DF8BE
0x1808df708  add     eax, 0FFFFFFFEh
0x1808df70b  jmp     short loc_1808DF712
0x1808df70d  neg     cx
0x1808df710  sbb     eax, eax
0x1808df712  test    eax, eax
0x1808df714  jnz     loc_1808DF8BE
0x1808df71a  lea     rdx, [rsp+78h+pbstr]; unsigned __int16 **
0x1808df722  mov     [rsp+78h+pbstr], rbp
0x1808df72a  mov     rcx, rdi; this
0x1808df72d  call    ?get_value@CParamElement@@QEAAJPEAPEAG@Z; CParamElement::get_value(ushort * *)
0x1808df732  mov     rbx, [rsp+78h+pbstr]
0x1808df73a  test    eax, eax
0x1808df73c  js      loc_1808DFC1D
0x1808df742  mov     rcx, rbx; pbstr
0x1808df745  call    cs:__imp_SysStringLen
0x1808df74c  nop     dword ptr [rax+rax+00h]
0x1808df751  test    eax, eax
0x1808df753  jz      loc_1808DFC1D
0x1808df759  mov     r8, rbx; lpString1
0x1808df75c  test    rbx, rbx
0x1808df75f  jz      loc_1808DF801
0x1808df765  lea     r9, aAlways; "always"
0x1808df76c  movzx   edx, word ptr [r8]
0x1808df770  movzx   ecx, word ptr [r9]
0x1808df774  test    dx, dx
0x1808df777  jz      short loc_1808DF7F4
0x1808df779  cmp     dx, cx
0x1808df77c  jz      short loc_1808DF7B1
0x1808df77e  movzx   eax, dx
0x1808df781  sub     ax, r15w
0x1808df785  cmp     ax, r12w
0x1808df789  movzx   eax, cx
0x1808df78c  ja      short loc_1808DF79E
0x1808df78e  add     dx, r14w
0x1808df792  sub     ax, r15w
0x1808df796  cmp     ax, r12w
0x1808df79a  ja      short loc_1808DF7AC
0x1808df79c  jmp     short loc_1808DF7A8
0x1808df79e  sub     ax, r15w
0x1808df7a2  cmp     ax, r12w
0x1808df7a6  ja      short loc_1808DF7B9
0x1808df7a8  add     cx, r14w
0x1808df7ac  cmp     dx, cx
0x1808df7af  jnz     short loc_1808DF7B9
0x1808df7b1  add     r8, r13
0x1808df7b4  add     r9, r13
0x1808df7b7  jmp     short loc_1808DF76C
0x1808df7b9  movzx   ecx, cx
0x1808df7bc  movzx   eax, dx
0x1808df7bf  or      ecx, eax
0x1808df7c1  test    ecx, 0FFFFFF80h
0x1808df7c7  jz      short loc_1808DF801
0x1808df7c9  or      eax, 0FFFFFFFFh
0x1808df7cc  mov     edx, 31001h; dwCmpFlags
0x1808df7d1  mov     [rsp+78h+cchCount2], eax; cchCount2
0x1808df7d5  xor     ecx, ecx; Locale
0x1808df7d7  mov     [rsp+78h+lpString2], r9; lpString2
0x1808df7dc  mov     r9d, eax; cchCount1
0x1808df7df  call    cs:__imp_CompareStringW
0x1808df7e6  nop     dword ptr [rax+rax+00h]
0x1808df7eb  test    eax, eax
0x1808df7ed  jle     short loc_1808DF801
0x1808df7ef  add     eax, 0FFFFFFFEh
0x1808df7f2  jmp     short loc_1808DF7F9
0x1808df7f4  neg     cx
0x1808df7f7  sbb     eax, eax
0x1808df7f9  test    eax, eax
0x1808df7fb  jz      loc_1808DF8B5
0x1808df801  mov     r8, rbx; lpString1
0x1808df804  test    rbx, rbx
0x1808df807  jz      loc_1808DFC1D
0x1808df80d  lea     r9, aSamedomain; "samedomain"
0x1808df814  movzx   edx, word ptr [r8]
0x1808df818  movzx   ecx, word ptr [r9]
0x1808df81c  test    dx, dx
0x1808df81f  jz      loc_1808DF8A8
0x1808df825  cmp     dx, cx
0x1808df828  jz      short loc_1808DF85D
0x1808df82a  movzx   eax, dx
0x1808df82d  sub     ax, r15w
0x1808df831  cmp     ax, r12w
0x1808df835  movzx   eax, cx
0x1808df838  ja      short loc_1808DF84A
0x1808df83a  add     dx, r14w
0x1808df83e  sub     ax, r15w
0x1808df842  cmp     ax, r12w
0x1808df846  ja      short loc_1808DF858
0x1808df848  jmp     short loc_1808DF854
0x1808df84a  sub     ax, r15w
0x1808df84e  cmp     ax, r12w
0x1808df852  ja      short loc_1808DF865
0x1808df854  add     cx, r14w
0x1808df858  cmp     dx, cx
0x1808df85b  jnz     short loc_1808DF865
0x1808df85d  add     r8, r13
0x1808df860  add     r9, r13
0x1808df863  jmp     short loc_1808DF814
0x1808df865  movzx   ecx, cx
0x1808df868  movzx   eax, dx
0x1808df86b  or      ecx, eax
0x1808df86d  test    ecx, 0FFFFFF80h
0x1808df873  jz      loc_1808DFC1D
0x1808df879  or      eax, 0FFFFFFFFh
0x1808df87c  mov     edx, 31001h; dwCmpFlags
0x1808df881  mov     [rsp+78h+cchCount2], eax; cchCount2
0x1808df885  xor     ecx, ecx; Locale
0x1808df887  mov     [rsp+78h+lpString2], r9; lpString2
0x1808df88c  mov     r9d, eax; cchCount1
0x1808df88f  call    cs:__imp_CompareStringW
0x1808df896  nop     dword ptr [rax+rax+00h]
0x1808df89b  test    eax, eax
0x1808df89d  jle     loc_1808DFC1D
0x1808df8a3  add     eax, 0FFFFFFFEh
0x1808df8a6  jmp     short loc_1808DF8AD
0x1808df8a8  neg     cx
0x1808df8ab  sbb     eax, eax
0x1808df8ad  test    eax, eax
0x1808df8af  jnz     loc_1808DFC1D
0x1808df8b5  mov     byte ptr [rsi+1], 1
0x1808df8b9  jmp     loc_1808DFC1D
0x1808df8be  mov     r8, rbx; lpString1
0x1808df8c1  lea     r9, aMovie; "movie"
0x1808df8c8  movzx   edx, word ptr [r8]
0x1808df8cc  movzx   ecx, word ptr [r9]
0x1808df8d0  test    dx, dx
0x1808df8d3  jz      short loc_1808DF950
0x1808df8d5  cmp     dx, cx
  ... truncated ...
```
