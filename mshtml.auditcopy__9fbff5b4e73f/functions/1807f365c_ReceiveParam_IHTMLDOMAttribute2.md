# ReceiveParam_IHTMLDOMAttribute2_

- ea: `0x1807f365c`
- end: `0x1807f3e0f`
- name: `ReceiveParam_IHTMLDOMAttribute2_`
- size: `1971`
- prototype: `void __fastcall(PCNZWCH lpString1, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1808e039c`

## callees

- `0x1807f365c`
- `0x181104010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1807f371c`
- `KERNEL32!CompareStringW` at `0x1807f3802`
- `KERNEL32!CompareStringW` at `0x1807f38cc`
- `KERNEL32!CompareStringW` at `0x1807f39b2`
- `KERNEL32!CompareStringW` at `0x1807f3a65`
- `KERNEL32!CompareStringW` at `0x1807f3b13`
- `KERNEL32!CompareStringW` at `0x1807f3bb4`
- `KERNEL32!CompareStringW` at `0x1807f3c55`
- `KERNEL32!CompareStringW` at `0x1807f3cf6`
- `KERNEL32!CompareStringW` at `0x1807f3d9e`
- `KERNEL32!CompareStringW` at `0x1807f371c`
- `KERNEL32!CompareStringW` at `0x1807f3802`
- `KERNEL32!CompareStringW` at `0x1807f38cc`
- `KERNEL32!CompareStringW` at `0x1807f39b2`
- `KERNEL32!CompareStringW` at `0x1807f3a65`
- `KERNEL32!CompareStringW` at `0x1807f3b13`
- `KERNEL32!CompareStringW` at `0x1807f3bb4`
- `KERNEL32!CompareStringW` at `0x1807f3c55`
- `KERNEL32!CompareStringW` at `0x1807f3cf6`
- `KERNEL32!CompareStringW` at `0x1807f3d9e`
- `OLEAUT32!__imp_SysFreeString` at `0x1807f3827`
- `OLEAUT32!__imp_SysFreeString` at `0x1807f3827`
- `OLEAUT32!__imp_SysStringLen` at `0x1807f3765`
- `OLEAUT32!__imp_SysStringLen` at `0x1807f3915`
- `OLEAUT32!__imp_SysStringLen` at `0x1807f3de7`
- `OLEAUT32!__imp_SysStringLen` at `0x1807f3765`
- `OLEAUT32!__imp_SysStringLen` at `0x1807f3915`
- `OLEAUT32!__imp_SysStringLen` at `0x1807f3de7`

## string_xrefs

- `0x1807f3848`: `allowscriptaccess`

## pseudocode

```c
void __fastcall ReceiveParam_IHTMLDOMAttribute2_(PCNZWCH lpString1, __int64 *a2, __int64 a3)
{
  const WCHAR *lpString2; // r9
  PCNZWCH v5; // r8
  PCNZWCH v7; // rbx
  WCHAR v8; // dx
  WCHAR v9; // cx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rax
  BSTR v13; // r8
  const wchar_t *v14; // r9
  WCHAR v15; // dx
  WCHAR v16; // cx
  int v17; // eax
  int v18; // eax
  OLECHAR *v19; // rcx
  const WCHAR *v20; // r8
  const WCHAR *v21; // r9
  WCHAR v22; // dx
  WCHAR v23; // cx
  int v24; // eax
  int v25; // eax
  __int64 v26; // rax
  BSTR v27; // r8
  const WCHAR *v28; // r9
  WCHAR v29; // dx
  WCHAR v30; // cx
  int v31; // eax
  int v32; // eax
  BSTR v33; // r8
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
  __int64 v68; // rax
  BSTR v69; // rax
  BSTR pbstr; // [rsp+80h] [rbp+48h] BYREF

  if ( !lpString1 )
    return;
  lpString2 = L"allowfullscreen";
  v5 = lpString1;
  v7 = lpString1;
  while ( 1 )
  {
    v8 = *v5;
    v9 = *lpString2;
    if ( !*v5 )
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
        v10 = CompareStringW(0, 0x31001u, v5, -1, lpString2, -1);
        if ( v10 > 0 )
        {
          v11 = v10 - 2;
          goto LABEL_16;
        }
      }
      goto LABEL_39;
    }
LABEL_11:
    ++v5;
    ++lpString2;
  }
  v11 = -(v9 != 0);
LABEL_16:
  if ( !v11 )
  {
    v12 = *a2;
    pbstr = 0;
    if ( (*(int (__fastcall **)(__int64 *, BSTR *))(v12 + 72))(a2, &pbstr) < 0 )
      goto LABEL_36;
    if ( !SysStringLen(pbstr) )
      goto LABEL_36;
    v13 = pbstr;
    if ( !pbstr )
      goto LABEL_36;
    v14 = L"true";
    while ( 2 )
    {
      v15 = *v13;
      v16 = *v14;
      if ( !*v13 )
      {
        v18 = -(v16 != 0);
LABEL_34:
        if ( !v18 )
          *(_BYTE *)a3 = 1;
        goto LABEL_36;
      }
      if ( v15 != v16 )
      {
        if ( (unsigned __int16)(v15 - 65) > 0x19u )
        {
          if ( (unsigned __int16)(v16 - 65) > 0x19u )
            goto LABEL_30;
LABEL_27:
          v16 += 32;
        }
        else
        {
          v15 += 32;
          if ( (unsigned __int16)(v16 - 65) <= 0x19u )
            goto LABEL_27;
        }
        if ( v15 != v16 )
        {
LABEL_30:
          if ( ((v15 | v16) & 0xFF80) != 0 )
          {
            v17 = CompareStringW(0, 0x31001u, v13, -1, v14, -1);
            if ( v17 > 0 )
            {
              v18 = v17 - 2;
              goto LABEL_34;
            }
          }
LABEL_36:
          v19 = pbstr;
          goto LABEL_37;
        }
      }
      ++v13;
      ++v14;
      continue;
    }
  }
LABEL_39:
  v20 = v7;
  v21 = L"allowscriptaccess";
  while ( 2 )
  {
    v22 = *v20;
    v23 = *v21;
    if ( *v20 )
    {
      if ( v22 != v23 )
      {
        if ( (unsigned __int16)(v22 - 65) > 0x19u )
        {
          if ( (unsigned __int16)(v23 - 65) > 0x19u )
            goto LABEL_49;
LABEL_46:
          v23 += 32;
        }
        else
        {
          v22 += 32;
          if ( (unsigned __int16)(v23 - 65) <= 0x19u )
            goto LABEL_46;
        }
        if ( v22 != v23 )
        {
LABEL_49:
          if ( ((v22 | v23) & 0xFF80) != 0 )
          {
            v24 = CompareStringW(0, 0x31001u, v20, -1, v21, -1);
            if ( v24 > 0 )
            {
              v25 = v24 - 2;
              goto LABEL_53;
            }
          }
          goto LABEL_89;
        }
      }
      ++v20;
      ++v21;
      continue;
    }
    break;
  }
  v25 = -(v23 != 0);
LABEL_53:
  if ( !v25 )
  {
    v26 = *a2;
    pbstr = 0;
    if ( (*(int (__fastcall **)(__int64 *, BSTR *))(v26 + 72))(a2, &pbstr) < 0 || !SysStringLen(pbstr) )
      goto LABEL_36;
    v27 = pbstr;
    if ( !pbstr )
      goto LABEL_72;
    v28 = L"always";
    while ( 2 )
    {
      v29 = *v27;
      v30 = *v28;
      if ( !*v27 )
      {
        v32 = -(v30 != 0);
        goto LABEL_71;
      }
      if ( v29 != v30 )
      {
        if ( (unsigned __int16)(v29 - 65) > 0x19u )
        {
          if ( (unsigned __int16)(v30 - 65) > 0x19u )
            goto LABEL_67;
LABEL_64:
          v30 += 32;
        }
        else
        {
          v29 += 32;
          if ( (unsigned __int16)(v30 - 65) <= 0x19u )
            goto LABEL_64;
        }
        if ( v29 != v30 )
        {
LABEL_67:
          if ( ((v29 | v30) & 0xFF80) != 0 )
          {
            v31 = CompareStringW(0, 0x31001u, v27, -1, v28, -1);
            if ( v31 > 0 )
            {
              v32 = v31 - 2;
LABEL_71:
              if ( !v32 )
                goto LABEL_88;
            }
          }
LABEL_72:
          v33 = pbstr;
          if ( !pbstr )
            goto LABEL_36;
          v34 = L"samedomain";
          while ( 2 )
          {
            v35 = *v33;
            v36 = *v34;
            if ( !*v33 )
            {
              v38 = -(v36 != 0);
              goto LABEL_87;
            }
            if ( v35 != v36 )
            {
              if ( (unsigned __int16)(v35 - 65) > 0x19u )
              {
                if ( (unsigned __int16)(v36 - 65) > 0x19u )
                  goto LABEL_83;
LABEL_80:
                v36 += 32;
              }
              else
              {
                v35 += 32;
                if ( (unsigned __int16)(v36 - 65) <= 0x19u )
                  goto LABEL_80;
              }
              if ( v35 != v36 )
              {
LABEL_83:
                if ( ((v35 | v36) & 0xFF80) == 0 )
                  goto LABEL_36;
                v37 = CompareStringW(0, 0x31001u, v33, -1, v34, -1);
                if ( v37 <= 0 )
                  goto LABEL_36;
                v38 = v37 - 2;
LABEL_87:
                if ( v38 )
                  goto LABEL_36;
LABEL_88:
                *(_BYTE *)(a3 + 1) = 1;
                goto LABEL_36;
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
LABEL_89:
  v39 = v7;
  v40 = L"movie";
  while ( 2 )
  {
    v41 = *v39;
    v42 = *v40;
    if ( !*v39 )
    {
      v44 = -(v42 != 0);
      goto LABEL_103;
    }
    if ( v41 == v42 )
      goto LABEL_98;
    if ( (unsigned __int16)(v41 - 65) > 0x19u )
    {
      if ( (unsigned __int16)(v42 - 65) > 0x19u )
        break;
LABEL_96:
      v42 += 32;
    }
    else
    {
      v41 += 32;
      if ( (unsigned __int16)(v42 - 65) <= 0x19u )
        goto LABEL_96;
    }
    if ( v41 == v42 )
    {
LABEL_98:
      ++v39;
      ++v40;
      continue;
    }
    break;
  }
  if ( ((v41 | v42) & 0xFF80) == 0 )
    goto LABEL_104;
  v43 = CompareStringW(0, 0x31001u, v39, -1, v40, -1);
  if ( v43 <= 0 )
    goto LABEL_104;
  v44 = v43 - 2;
LABEL_103:
  if ( !v44 )
    goto LABEL_164;
LABEL_104:
  v45 = v7;
  v46 = L"src";
  while ( 2 )
  {
    v47 = *v45;
    v48 = *v46;
    if ( !*v45 )
    {
      v50 = -(v48 != 0);
      goto LABEL_118;
    }
    if ( v47 == v48 )
      goto LABEL_113;
    if ( (unsigned __int16)(v47 - 65) > 0x19u )
    {
      if ( (unsigned __int16)(v48 - 65) > 0x19u )
        break;
LABEL_111:
      v48 += 32;
    }
    else
    {
      v47 += 32;
      if ( (unsigned __int16)(v48 - 65) <= 0x19u )
        goto LABEL_111;
    }
    if ( v47 == v48 )
    {
LABEL_113:
      ++v45;
      ++v46;
      continue;
    }
    break;
  }
  if ( ((v47 | v48) & 0xFF80) == 0 )
    goto LABEL_119;
  v49 = CompareStringW(0, 0x31001u, v45, -1, v46, -1);
  if ( v49 <= 0 )
    goto LABEL_119;
  v50 = v49 - 2;
LABEL_118:
  if ( !v50 )
    goto LABEL_164;
LABEL_119:
  v51 = v7;
  v52 = L"filename";
  while ( 2 )
  {
    v53 = *v51;
    v54 = *v52;
    if ( !*v51 )
    {
      v56 = -(v54 != 0);
      goto LABEL_133;
    }
    if ( v53 == v54 )
      goto LABEL_128;
    if ( (unsigned __int16)(v53 - 65) > 0x19u )
    {
      if ( (unsigned __int16)(v54 - 65) > 0x19u )
        break;
LABEL_126:
      v54 += 32;
    }
    else
    {
      v53 += 32;
      if ( (unsigned __int16)(v54 - 65) <= 0x19u )
        goto LABEL_126;
    }
    if ( v53 == v54 )
    {
LABEL_128:
      ++v51;
      ++v52;
      continue;
    }
    break;
  }
  if ( ((v53 | v54) & 0xFF80) == 0 )
    goto LABEL_134;
  v55 = CompareStringW(0, 0x31001u, v51, -1, v52, -1);
  if ( v55 <= 0 )
    goto LABEL_134;
  v56 = v55 - 2;
LABEL_133:
  if ( !v56 )
    goto LABEL_164;
LABEL_134:
  v57 = v7;
  v58 = L"url";
  while ( 2 )
  {
    v59 = *v57;
    v60 = *v58;
    if ( !*v57 )
    {
      v62 = -(v60 != 0);
      goto LABEL_148;
    }
    if ( v59 == v60 )
      goto LABEL_143;
    if ( (unsigned __int16)(v59 - 65) > 0x19u )
    {
      if ( (unsigned __int16)(v60 - 65) > 0x19u )
        break;
LABEL_141:
      v60 += 32;
    }
    else
    {
      v59 += 32;
      if ( (unsigned __int16)(v60 - 65) <= 0x19u )
        goto LABEL_141;
    }
    if ( v59 == v60 )
    {
LABEL_143:
      ++v57;
      ++v58;
      continue;
    }
    break;
  }
  if ( ((v59 | v60) & 0xFF80) == 0 )
    goto LABEL_149;
  v61 = CompareStringW(0, 0x31001u, v57, -1, v58, -1);
  if ( v61 <= 0 )
    goto LABEL_149;
  v62 = v61 - 2;
LABEL_148:
  if ( !v62 )
    goto LABEL_164;
LABEL_149:
  v63 = L"source";
  while ( 2 )
  {
    v64 = *v7;
    v65 = *v63;
    if ( !*v7 )
    {
      v67 = -(v65 != 0);
      goto LABEL_163;
    }
    if ( v64 == v65 )
      goto LABEL_158;
    if ( (unsigned __int16)(v64 - 65) > 0x19u )
    {
      if ( (unsigned __int16)(v65 - 65) > 0x19u )
        break;
LABEL_156:
      v65 += 32;
    }
    else
    {
      v64 += 32;
      if ( (unsigned __int16)(v65 - 65) <= 0x19u )
        goto LABEL_156;
    }
    if ( v64 == v65 )
    {
LABEL_158:
      ++v7;
      ++v63;
      continue;
    }
    break;
  }
  if ( ((v64 | v65) & 0xFF80) == 0 )
    return;
  v66 = CompareStringW(0, 0x31001u, v7, -1, v63, -1);
  if ( v66 <= 0 )
    return;
  v67 = v66 - 2;
LABEL_163:
  if ( v67 )
    return;
LABEL_164:
  v68 = *a2;
  pbstr = 0;
  if ( (*(int (__fastcall **)(__int64 *, BSTR *))(v68 + 72))(a2, &pbstr) < 0 || !SysStringLen(pbstr) )
    goto LABEL_36;
  v69 = pbstr;
  v19 = 0;
  pbstr = 0;
  *(_QWORD *)(a3 + 8) = v69;
LABEL_37:
  SysFreeString(v19);
}

```

## disassembly

```asm
0x1807f365c  test    rcx, rcx
0x1807f365f  jz      locret_1807F3843
0x1807f3665  push    rbp
0x1807f3666  push    rbx
0x1807f3667  push    rsi
0x1807f3668  push    rdi
0x1807f3669  push    r12
0x1807f366b  push    r13
0x1807f366d  push    r14
0x1807f366f  push    r15
0x1807f3671  mov     rbp, rsp
0x1807f3674  sub     rsp, 38h
0x1807f3678  mov     rsi, r8
0x1807f367b  lea     r9, aAllowfullscree_0; "allowfullscreen"
0x1807f3682  mov     r8, rcx; lpString1
0x1807f3685  mov     rdi, rdx
0x1807f3688  mov     rbx, rcx
0x1807f368b  xor     r14d, r14d
0x1807f368e  mov     r12w, 41h ; 'A'
0x1807f3693  mov     r13w, 19h
0x1807f3698  mov     r15w, 20h ; ' '
0x1807f369d  movzx   edx, word ptr [r8]
0x1807f36a1  or      r10d, 0FFFFFFFFh
0x1807f36a5  movzx   ecx, word ptr [r9]
0x1807f36a9  test    dx, dx
0x1807f36ac  jz      loc_1807F3735
0x1807f36b2  cmp     dx, cx
0x1807f36b5  jz      short loc_1807F36EA
0x1807f36b7  movzx   eax, dx
0x1807f36ba  sub     ax, r12w
0x1807f36be  cmp     ax, r13w
0x1807f36c2  movzx   eax, cx
0x1807f36c5  ja      short loc_1807F36D7
0x1807f36c7  add     dx, r15w
0x1807f36cb  sub     ax, r12w
0x1807f36cf  cmp     ax, r13w
0x1807f36d3  ja      short loc_1807F36E5
0x1807f36d5  jmp     short loc_1807F36E1
0x1807f36d7  sub     ax, r12w
0x1807f36db  cmp     ax, r13w
0x1807f36df  ja      short loc_1807F36F4
0x1807f36e1  add     cx, r15w
0x1807f36e5  cmp     dx, cx
0x1807f36e8  jnz     short loc_1807F36F4
0x1807f36ea  add     r8, 2
0x1807f36ee  add     r9, 2
0x1807f36f2  jmp     short loc_1807F369D
0x1807f36f4  movzx   ecx, cx
0x1807f36f7  movzx   eax, dx
0x1807f36fa  or      ecx, eax
0x1807f36fc  test    ecx, 0FFFFFF80h
0x1807f3702  jz      loc_1807F3845
0x1807f3708  mov     [rsp+38h+cchCount2], r10d; cchCount2
0x1807f370d  mov     edx, 31001h; dwCmpFlags
0x1807f3712  mov     [rsp+38h+lpString2], r9; lpString2
0x1807f3717  xor     ecx, ecx; Locale
0x1807f3719  mov     r9d, r10d; cchCount1
0x1807f371c  call    cs:__imp_CompareStringW
0x1807f3723  nop     dword ptr [rax+rax+00h]
0x1807f3728  test    eax, eax
0x1807f372a  jle     loc_1807F3845
0x1807f3730  add     eax, 0FFFFFFFEh
0x1807f3733  jmp     short loc_1807F373A
0x1807f3735  neg     cx
0x1807f3738  sbb     eax, eax
0x1807f373a  test    eax, eax
0x1807f373c  jnz     loc_1807F3845
0x1807f3742  mov     rax, [rdi]
0x1807f3745  lea     rdx, [rbp+pbstr]
0x1807f3749  mov     rcx, rdi
0x1807f374c  mov     [rbp+pbstr], r14
0x1807f3750  mov     rax, [rax+48h]
0x1807f3754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807f3759  test    eax, eax
0x1807f375b  js      loc_1807F3823
0x1807f3761  mov     rcx, [rbp+pbstr]; pbstr
0x1807f3765  call    cs:__imp_SysStringLen
0x1807f376c  nop     dword ptr [rax+rax+00h]
0x1807f3771  test    eax, eax
0x1807f3773  jz      loc_1807F3823
0x1807f3779  mov     r8, [rbp+pbstr]; lpString1
0x1807f377d  test    r8, r8
0x1807f3780  jz      loc_1807F3823
0x1807f3786  lea     r9, aTrue; "true"
0x1807f378d  movzx   edx, word ptr [r8]
0x1807f3791  movzx   ecx, word ptr [r9]
0x1807f3795  test    dx, dx
0x1807f3798  jz      short loc_1807F3817
0x1807f379a  cmp     dx, cx
0x1807f379d  jz      short loc_1807F37D2
0x1807f379f  movzx   eax, dx
0x1807f37a2  sub     ax, r12w
0x1807f37a6  cmp     ax, r13w
0x1807f37aa  movzx   eax, cx
0x1807f37ad  ja      short loc_1807F37BF
0x1807f37af  add     dx, r15w
0x1807f37b3  sub     ax, r12w
0x1807f37b7  cmp     ax, r13w
0x1807f37bb  ja      short loc_1807F37CD
0x1807f37bd  jmp     short loc_1807F37C9
0x1807f37bf  sub     ax, r12w
0x1807f37c3  cmp     ax, r13w
0x1807f37c7  ja      short loc_1807F37DC
0x1807f37c9  add     cx, r15w
0x1807f37cd  cmp     dx, cx
0x1807f37d0  jnz     short loc_1807F37DC
0x1807f37d2  add     r8, 2
0x1807f37d6  add     r9, 2
0x1807f37da  jmp     short loc_1807F378D
0x1807f37dc  movzx   ecx, cx
0x1807f37df  movzx   eax, dx
0x1807f37e2  or      ecx, eax
0x1807f37e4  test    ecx, 0FFFFFF80h
0x1807f37ea  jz      short loc_1807F3823
0x1807f37ec  or      eax, 0FFFFFFFFh
0x1807f37ef  mov     edx, 31001h; dwCmpFlags
0x1807f37f4  mov     [rsp+38h+cchCount2], eax; cchCount2
0x1807f37f8  xor     ecx, ecx; Locale
0x1807f37fa  mov     [rsp+38h+lpString2], r9; lpString2
0x1807f37ff  mov     r9d, eax; cchCount1
0x1807f3802  call    cs:__imp_CompareStringW
0x1807f3809  nop     dword ptr [rax+rax+00h]
0x1807f380e  test    eax, eax
0x1807f3810  jle     short loc_1807F3823
0x1807f3812  add     eax, 0FFFFFFFEh
0x1807f3815  jmp     short loc_1807F381C
0x1807f3817  neg     cx
0x1807f381a  sbb     eax, eax
0x1807f381c  test    eax, eax
0x1807f381e  jnz     short loc_1807F3823
0x1807f3820  mov     byte ptr [rsi], 1
0x1807f3823  mov     rcx, [rbp+pbstr]; bstrString
0x1807f3827  call    cs:__imp_SysFreeString
0x1807f382e  nop     dword ptr [rax+rax+00h]
0x1807f3833  add     rsp, 38h
0x1807f3837  pop     r15
0x1807f3839  pop     r14
0x1807f383b  pop     r13
0x1807f383d  pop     r12
0x1807f383f  pop     rdi
0x1807f3840  pop     rsi
0x1807f3841  pop     rbx
0x1807f3842  pop     rbp
0x1807f3843  retn
0x1807f3845  mov     r8, rbx; lpString1
0x1807f3848  lea     r9, aAllowscriptacc; "allowscriptaccess"
0x1807f384f  movzx   edx, word ptr [r8]
0x1807f3853  movzx   ecx, word ptr [r9]
0x1807f3857  test    dx, dx
0x1807f385a  jz      loc_1807F38E5
0x1807f3860  cmp     dx, cx
0x1807f3863  jz      short loc_1807F3898
0x1807f3865  movzx   eax, dx
0x1807f3868  sub     ax, r12w
0x1807f386c  cmp     ax, r13w
0x1807f3870  movzx   eax, cx
0x1807f3873  ja      short loc_1807F3885
0x1807f3875  add     dx, r15w
0x1807f3879  sub     ax, r12w
0x1807f387d  cmp     ax, r13w
0x1807f3881  ja      short loc_1807F3893
0x1807f3883  jmp     short loc_1807F388F
0x1807f3885  sub     ax, r12w
0x1807f3889  cmp     ax, r13w
0x1807f388d  ja      short loc_1807F38A2
0x1807f388f  add     cx, r15w
0x1807f3893  cmp     dx, cx
0x1807f3896  jnz     short loc_1807F38A2
0x1807f3898  add     r8, 2
0x1807f389c  add     r9, 2
0x1807f38a0  jmp     short loc_1807F384F
0x1807f38a2  movzx   ecx, cx
0x1807f38a5  movzx   eax, dx
0x1807f38a8  or      ecx, eax
0x1807f38aa  test    ecx, 0FFFFFF80h
0x1807f38b0  jz      loc_1807F3A94
0x1807f38b6  or      eax, 0FFFFFFFFh
0x1807f38b9  mov     edx, 31001h; dwCmpFlags
0x1807f38be  mov     [rsp+38h+cchCount2], eax; cchCount2
0x1807f38c2  xor     ecx, ecx; Locale
0x1807f38c4  mov     [rsp+38h+lpString2], r9; lpString2
0x1807f38c9  mov     r9d, eax; cchCount1
0x1807f38cc  call    cs:__imp_CompareStringW
0x1807f38d3  nop     dword ptr [rax+rax+00h]
0x1807f38d8  test    eax, eax
0x1807f38da  jle     loc_1807F3A94
0x1807f38e0  add     eax, 0FFFFFFFEh
0x1807f38e3  jmp     short loc_1807F38EA
0x1807f38e5  neg     cx
0x1807f38e8  sbb     eax, eax
0x1807f38ea  test    eax, eax
0x1807f38ec  jnz     loc_1807F3A94
0x1807f38f2  mov     rax, [rdi]
0x1807f38f5  lea     rdx, [rbp+pbstr]
0x1807f38f9  mov     rcx, rdi
0x1807f38fc  mov     [rbp+pbstr], r14
0x1807f3900  mov     rax, [rax+48h]
0x1807f3904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807f3909  test    eax, eax
0x1807f390b  js      loc_1807F3823
0x1807f3911  mov     rcx, [rbp+pbstr]; pbstr
0x1807f3915  call    cs:__imp_SysStringLen
0x1807f391c  nop     dword ptr [rax+rax+00h]
0x1807f3921  test    eax, eax
0x1807f3923  jz      loc_1807F3823
0x1807f3929  mov     r8, [rbp+pbstr]; lpString1
0x1807f392d  test    r8, r8
0x1807f3930  jz      loc_1807F39D4
0x1807f3936  lea     r9, aAlways; "always"
0x1807f393d  movzx   edx, word ptr [r8]
0x1807f3941  movzx   ecx, word ptr [r9]
0x1807f3945  test    dx, dx
0x1807f3948  jz      short loc_1807F39C7
0x1807f394a  cmp     dx, cx
0x1807f394d  jz      short loc_1807F3982
0x1807f394f  movzx   eax, dx
0x1807f3952  sub     ax, r12w
0x1807f3956  cmp     ax, r13w
0x1807f395a  movzx   eax, cx
0x1807f395d  ja      short loc_1807F396F
0x1807f395f  add     dx, r15w
0x1807f3963  sub     ax, r12w
0x1807f3967  cmp     ax, r13w
0x1807f396b  ja      short loc_1807F397D
0x1807f396d  jmp     short loc_1807F3979
0x1807f396f  sub     ax, r12w
0x1807f3973  cmp     ax, r13w
0x1807f3977  ja      short loc_1807F398C
0x1807f3979  add     cx, r15w
0x1807f397d  cmp     dx, cx
0x1807f3980  jnz     short loc_1807F398C
0x1807f3982  add     r8, 2
0x1807f3986  add     r9, 2
0x1807f398a  jmp     short loc_1807F393D
0x1807f398c  movzx   ecx, cx
0x1807f398f  movzx   eax, dx
0x1807f3992  or      ecx, eax
0x1807f3994  test    ecx, 0FFFFFF80h
0x1807f399a  jz      short loc_1807F39D4
0x1807f399c  or      eax, 0FFFFFFFFh
0x1807f399f  mov     edx, 31001h; dwCmpFlags
0x1807f39a4  mov     [rsp+38h+cchCount2], eax; cchCount2
0x1807f39a8  xor     ecx, ecx; Locale
0x1807f39aa  mov     [rsp+38h+lpString2], r9; lpString2
0x1807f39af  mov     r9d, eax; cchCount1
0x1807f39b2  call    cs:__imp_CompareStringW
0x1807f39b9  nop     dword ptr [rax+rax+00h]
0x1807f39be  test    eax, eax
0x1807f39c0  jle     short loc_1807F39D4
0x1807f39c2  add     eax, 0FFFFFFFEh
0x1807f39c5  jmp     short loc_1807F39CC
0x1807f39c7  neg     cx
0x1807f39ca  sbb     eax, eax
0x1807f39cc  test    eax, eax
0x1807f39ce  jz      loc_1807F3A8B
0x1807f39d4  mov     r8, [rbp+pbstr]; lpString1
0x1807f39d8  test    r8, r8
0x1807f39db  jz      loc_1807F3823
0x1807f39e1  lea     r9, aSamedomain; "samedomain"
0x1807f39e8  movzx   edx, word ptr [r8]
0x1807f39ec  movzx   ecx, word ptr [r9]
0x1807f39f0  test    dx, dx
0x1807f39f3  jz      loc_1807F3A7E
0x1807f39f9  cmp     dx, cx
0x1807f39fc  jz      short loc_1807F3A31
0x1807f39fe  movzx   eax, dx
0x1807f3a01  sub     ax, r12w
0x1807f3a05  cmp     ax, r13w
0x1807f3a09  movzx   eax, cx
0x1807f3a0c  ja      short loc_1807F3A1E
0x1807f3a0e  add     dx, r15w
0x1807f3a12  sub     ax, r12w
0x1807f3a16  cmp     ax, r13w
0x1807f3a1a  ja      short loc_1807F3A2C
0x1807f3a1c  jmp     short loc_1807F3A28
0x1807f3a1e  sub     ax, r12w
0x1807f3a22  cmp     ax, r13w
0x1807f3a26  ja      short loc_1807F3A3B
0x1807f3a28  add     cx, r15w
0x1807f3a2c  cmp     dx, cx
0x1807f3a2f  jnz     short loc_1807F3A3B
0x1807f3a31  add     r8, 2
0x1807f3a35  add     r9, 2
0x1807f3a39  jmp     short loc_1807F39E8
0x1807f3a3b  movzx   ecx, cx
0x1807f3a3e  movzx   eax, dx
0x1807f3a41  or      ecx, eax
0x1807f3a43  test    ecx, 0FFFFFF80h
0x1807f3a49  jz      loc_1807F3823
0x1807f3a4f  or      eax, 0FFFFFFFFh
0x1807f3a52  mov     edx, 31001h; dwCmpFlags
0x1807f3a57  mov     [rsp+38h+cchCount2], eax; cchCount2
0x1807f3a5b  xor     ecx, ecx; Locale
0x1807f3a5d  mov     [rsp+38h+lpString2], r9; lpString2
0x1807f3a62  mov     r9d, eax; cchCount1
0x1807f3a65  call    cs:__imp_CompareStringW
0x1807f3a6c  nop     dword ptr [rax+rax+00h]
0x1807f3a71  test    eax, eax
0x1807f3a73  jle     loc_1807F3823
0x1807f3a79  add     eax, 0FFFFFFFEh
  ... truncated ...
```
