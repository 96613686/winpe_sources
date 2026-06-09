# CreateNewFilterBlob(ushort,_EAPTLS_HASH *,ushort,_EAPTLS_EKU_NODE *,_EAPTLS_EKU_NODE *,uchar * *,ulong *)

- ea: `0x18001f0b0`
- end: `0x18001f930`
- name: `?CreateNewFilterBlob@@YAKGPEAU_EAPTLS_HASH@@GPEAU_EAPTLS_EKU_NODE@@1PEAPEAEPEAK@Z`
- size: `2176`
- prototype: `unsigned int __fastcall(unsigned __int16, struct _EAPTLS_HASH *, unsigned __int16, struct _EAPTLS_EKU_NODE *, struct _EAPTLS_EKU_NODE *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180010580`
- `0x18006aae8`

## callees

- `0x180005010`
- `0x180007d00`
- `0x18001f0b0`
- `0x180021f7c`
- `0x18002206c`
- `0x18002f71c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001f74e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001f791`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001f74e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001f791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f183`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f44e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f183`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f44e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f611`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18001f321`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18001f321`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f16f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f5fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f16f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f5fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f194`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f45f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f8a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f8ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f194`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f45f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f8a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f8ba`
- `rtutils!TraceDumpExA` at `0x18001f891`
- `rtutils!TraceDumpExA` at `0x18001f891`

## pseudocode

```c
__int64 __fastcall CreateNewFilterBlob(
        __int16 a1,
        struct _EAPTLS_HASH *a2,
        unsigned __int16 a3,
        struct _EAPTLS_EKU_NODE *a4,
        struct _EAPTLS_EKU_NODE *a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  struct _EAPTLS_EKU_NODE *v7; // rdi
  unsigned int v8; // ebp
  int v10; // r15d
  struct _EAPTLS_EKU_NODE *v11; // rbx
  __int16 v12; // r14
  _QWORD *v14; // r12
  const CHAR *lpszPrefix; // rsi
  __int64 v16; // r9
  int v17; // ebx
  struct _EAPTLS_CONTROL_BLOCK *v18; // r10
  int v19; // r8d
  int v20; // edx
  int v21; // r11d
  unsigned __int16 v22; // r13
  unsigned __int16 i; // bp
  __int16 v24; // r14
  bool v25; // zf
  void *v26; // rdi
  __int16 v27; // r14
  __int64 v28; // rax
  unsigned int v29; // edx
  unsigned __int16 v30; // dx
  __int64 v31; // rax
  unsigned int v32; // ecx
  unsigned __int16 v33; // cx
  unsigned __int16 v34; // ax
  unsigned __int16 v35; // bp
  __int16 v36; // di
  unsigned int v37; // r10d
  unsigned int v38; // ecx
  unsigned int v39; // r10d
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // r10d
  unsigned int v43; // ecx
  unsigned __int8 *v44; // r14
  LPBYTE *v45; // r10
  DWORD *v46; // r9
  unsigned int v47; // eax
  __int64 v48; // r14
  unsigned __int16 v49; // dx
  __int64 v50; // rax
  unsigned __int16 v51; // bx
  unsigned __int16 v52; // bp
  __int16 v53; // ax
  char *v54; // r15
  __int64 v55; // r8
  __int64 v56; // rax
  __int64 v57; // rdi
  __int64 v58; // r14
  __int64 v59; // r8
  __int64 v60; // rax
  __int64 v61; // rdi
  unsigned __int16 v62; // r8
  unsigned __int16 v63; // cx
  unsigned __int16 v64; // dx
  unsigned __int16 v65; // cx
  unsigned __int16 *v66; // r14
  unsigned __int16 v67; // dx
  unsigned int uBytes; // [rsp+40h] [rbp-68h] BYREF
  int uBytes_4; // [rsp+44h] [rbp-64h]
  int v70; // [rsp+48h] [rbp-60h]
  int v71; // [rsp+4Ch] [rbp-5Ch]
  int v72; // [rsp+50h] [rbp-58h]
  LPCSTR v73; // [rsp+54h] [rbp-54h]
  __int16 v74; // [rsp+B0h] [rbp+8h]

  v7 = a4;
  v8 = a3;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
  LOWORD(v10) = 0;
  v11 = a5;
  *a7 = 0;
  *a6 = 0;
  v12 = a1 & 0xFFEF;
  v74 = v12;
  if ( !a5 && !v7 && !(_WORD)v8 && !v12 )
    return 0;
  v14 = LocalAlloc(0x40u, 0x800u);
  if ( v14 )
  {
    LODWORD(lpszPrefix) = 0;
    LODWORD(v73) = 0;
    v16 = v8;
    if ( (_WORD)v8 )
    {
      if ( 20 * v8 > 0xFFFF )
        goto LABEL_95;
      LOWORD(uBytes) = 20 * v8;
      v17 = UShortAdd(20 * (unsigned __int16)v8, 4u, (unsigned __int16 *)&uBytes);
      if ( v17 < 0 )
        goto LABEL_93;
      uBytes = (unsigned __int16)uBytes + 6;
      if ( uBytes < 6 )
        goto LABEL_95;
      v11 = a5;
    }
    else
    {
      uBytes = 6;
    }
    v18 = WPP_GLOBAL_Control;
    v19 = 0;
    uBytes_4 = 0;
    v72 = 0;
    v20 = 256;
    v70 = 0;
    v21 = 0;
    v71 = 256;
    v22 = 0;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 235, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, v16);
      v18 = WPP_GLOBAL_Control;
      v21 = 0;
      v19 = v70;
      v20 = 256;
    }
    for ( i = 0; i < 2u; ++i )
    {
      if ( i )
        v11 = v7;
      if ( v11 )
      {
        while ( 1 )
        {
          v11 = *(struct _EAPTLS_EKU_NODE **)v11;
          if ( !v11 )
            break;
          if ( i == 1 || *((_DWORD *)v11 + 9) || *((_DWORD *)v11 + 10) )
          {
            v24 = *((_DWORD *)v11 + 9) != 0;
            v25 = *((_DWORD *)v11 + 10) == 0;
            v14[(unsigned __int16)v21] = v11;
            v10 = !v25;
            LOWORD(v21) = v21 + 1;
            uBytes_4 = v21;
            if ( (_WORD)v21 == (_WORD)v20 )
            {
              LOWORD(v20) = 2 * v20;
              v26 = v14;
              v71 = v20;
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  236,
                  &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids,
                  (unsigned __int16)v20);
                LOWORD(v20) = v71;
              }
              v14 = LocalReAlloc(v14, 8LL * (unsigned __int16)v20, 0x40u);
              if ( !v14 )
              {
                LODWORD(lpszPrefix) = GetLastError();
                LocalFree(v26);
                goto LABEL_98;
              }
              v19 = v70;
              v21 = uBytes_4;
            }
            LOWORD(v10) = v72 + v10;
            v18 = WPP_GLOBAL_Control;
            v27 = v22 + v24;
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            {
              WPP_SF_SSddd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                i,
                v19,
                *((_QWORD *)v11 + 1),
                *((_QWORD *)v11 + 2),
                i,
                v27,
                v10);
              v18 = WPP_GLOBAL_Control;
              LOWORD(v19) = v70;
              v21 = uBytes_4;
            }
            v28 = -1;
            do
              ++v28;
            while ( *(_WORD *)(*((_QWORD *)v11 + 1) + 2 * v28) );
            v29 = 2 * (unsigned __int16)v28;
            if ( v29 > 0xFFFF )
              goto LABEL_95;
            v30 = v19 + v29;
            if ( v30 < (unsigned __int16)v19 )
              goto LABEL_95;
            v31 = -1;
            do
              ++v31;
            while ( *(_WORD *)(*((_QWORD *)v11 + 2) + 2 * v31) );
            v32 = 2 * (unsigned __int16)v31;
            if ( v32 > 0xFFFF )
              goto LABEL_95;
            v33 = v30 + v32;
            if ( v33 < v30 )
              goto LABEL_95;
            v34 = v33 + 4;
            uBytes_4 = v21;
            if ( (unsigned __int16)(v33 + 4) < v33 )
              goto LABEL_95;
            v20 = v71;
            v19 = v34;
            v70 = v34;
            v22 = v27;
            v72 = v10;
          }
        }
      }
      v11 = a5;
      v7 = a4;
    }
    if ( v18 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      WPP_SF_DDD(
        *((_QWORD *)v18 + 2),
        238,
        &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids,
        (unsigned __int16)v21,
        v22,
        (unsigned __int16)v10);
      LOWORD(v19) = v70;
      LOWORD(v21) = uBytes_4;
    }
    if ( (_WORD)v21 )
    {
      if ( (unsigned __int16)(v19 + 4) < (unsigned __int16)v19 )
        goto LABEL_95;
      v38 = uBytes + (unsigned __int16)(v19 + 4);
      if ( v38 < uBytes )
        goto LABEL_95;
      v17 = 0;
      uBytes += (unsigned __int16)(v19 + 4);
      v37 = v38;
      if ( !v22 )
      {
LABEL_61:
        if ( !(_WORD)v10 )
        {
LABEL_66:
          v35 = a3;
          v36 = v74;
          goto LABEL_67;
        }
        goto LABEL_62;
      }
    }
    else if ( !v22 )
    {
      if ( !(_WORD)v10 )
      {
        v35 = a3;
        v17 = 0;
        v36 = v74;
        if ( !a3 && !v74 )
          goto LABEL_93;
        v37 = uBytes;
LABEL_67:
        v44 = (unsigned __int8 *)LocalAlloc(0x40u, v37);
        if ( v44 )
        {
          v45 = a6;
          v46 = a7;
          v47 = uBytes;
          *a6 = v44;
          *a7 = v47;
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, v47);
            v46 = a7;
            v45 = a6;
          }
          *(_DWORD *)v44 = 393470;
          *((_WORD *)v44 + 2) = v36;
          v48 = (__int64)(v44 + 6);
          if ( v35 )
          {
            *(_WORD *)v48 = 253;
            v49 = 0;
            *(_WORD *)(v48 + 2) = 20 * v35 + 4;
            v48 += 4;
            do
            {
              v50 = v49++;
              *(_OWORD *)v48 = *(_OWORD *)((char *)a2 + 24 * v50 + 4);
              *(_DWORD *)(v48 + 16) = *((_DWORD *)a2 + 6 * v50 + 5);
              v48 += 20;
            }
            while ( v49 < v35 );
          }
          v51 = uBytes_4;
          if ( (_WORD)uBytes_4 )
          {
            v52 = 0;
            v53 = v70 + 4;
            *(_WORD *)v48 = 252;
            *(_WORD *)(v48 + 2) = v53;
            v48 += 4;
            do
            {
              v54 = (char *)&v14[v52];
              v55 = *(_QWORD *)(*(_QWORD *)v54 + 8LL);
              v56 = -1;
              do
                ++v56;
              while ( *(_WORD *)(v55 + 2 * v56) );
              v57 = (unsigned __int16)v56;
              _o_wcsncpy_s(v48, (unsigned __int16)v56 + 1LL, v55, -1);
              *(_WORD *)(v48 + 2 * v57) = 59;
              v58 = v48 + 2 * v57 + 2;
              v59 = *(_QWORD *)(*(_QWORD *)v54 + 16LL);
              v60 = -1;
              do
                ++v60;
              while ( *(_WORD *)(v59 + 2 * v60) );
              v61 = (unsigned __int16)v60;
              _o_wcsncpy_s(v58, (unsigned __int16)v60 + 1LL, v59, -1);
              *(_WORD *)(v58 + 2 * v61) = 59;
              ++v52;
              v48 = v58 + 2 * v61 + 2;
            }
            while ( v52 < v51 );
            LOWORD(v10) = v72;
            v46 = a7;
            v45 = a6;
          }
          v17 = 0;
          lpszPrefix = (const CHAR *)(unsigned int)v73;
          v62 = uBytes_4;
          if ( v22 )
          {
            *(_WORD *)v48 = 251;
            v63 = 0;
            *(_WORD *)(v48 + 2) = 2 * (v22 + 2);
            v48 += 4;
            if ( v62 )
            {
              do
              {
                v64 = v63 + 1;
                if ( *(_DWORD *)(v14[v63] + 36LL) != (_DWORD)lpszPrefix )
                {
                  *(_WORD *)v48 = v64;
                  v48 += 2;
                }
                ++v63;
              }
              while ( v64 < v62 );
            }
          }
          if ( (_WORD)v10 )
          {
            *(_WORD *)v48 = 250;
            v65 = 0;
            *(_WORD *)(v48 + 2) = 2 * (v10 + 2);
            v66 = (unsigned __int16 *)(v48 + 4);
            if ( v62 )
            {
              do
              {
                v67 = v65 + 1;
                if ( *(_DWORD *)(v14[v65] + 40LL) != (_DWORD)lpszPrefix )
                  *v66++ = v67;
                ++v65;
              }
              while ( v67 < v62 );
            }
          }
          TraceDumpExA(g_dwEapTlsTraceId, 1u, *v45, *v46, 1u, 1, lpszPrefix);
        }
        else
        {
          LODWORD(lpszPrefix) = GetLastError();
        }
LABEL_93:
        LocalFree(v14);
        if ( !v17 )
          goto LABEL_98;
LABEL_96:
        LODWORD(lpszPrefix) = (unsigned __int16)v17;
        if ( (v17 & 0x1FFF0000) != 0x70000 )
          LODWORD(lpszPrefix) = v17;
        goto LABEL_98;
      }
LABEL_62:
      v41 = 2 * (unsigned __int16)v10;
      if ( v41 <= 0xFFFF )
      {
        LOWORD(uBytes) = 2 * v10;
        v17 = UShortAdd(v41, 4u, (unsigned __int16 *)&uBytes);
        if ( v17 < 0 )
          goto LABEL_93;
        v43 = v42 + (unsigned __int16)uBytes;
        if ( v43 >= v42 )
        {
          v17 = 0;
          uBytes = v42 + (unsigned __int16)uBytes;
          v37 = v43;
          goto LABEL_66;
        }
      }
LABEL_95:
      v17 = -2147024362;
      LocalFree(v14);
      goto LABEL_96;
    }
    if ( 2 * (unsigned int)v22 > 0xFFFF )
      goto LABEL_95;
    LOWORD(uBytes) = 2 * v22;
    v17 = UShortAdd(2 * v22, 4u, (unsigned __int16 *)&uBytes);
    if ( v17 < 0 )
      goto LABEL_93;
    v40 = v39 + (unsigned __int16)uBytes;
    if ( v40 < v39 )
      goto LABEL_95;
    v17 = 0;
    uBytes = v39 + (unsigned __int16)uBytes;
    v37 = v40;
    goto LABEL_61;
  }
  LODWORD(lpszPrefix) = GetLastError();
  LocalFree(0);
LABEL_98:
  if ( (_DWORD)lpszPrefix )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        240,
        &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids,
        (unsigned int)lpszPrefix);
  }
  return (unsigned int)lpszPrefix;
}

```

## disassembly

```asm
0x18001f0b0  mov     [rsp+arg_18], r9
0x18001f0b5  mov     [rsp+arg_10], r8w
0x18001f0bb  mov     [rsp+arg_8], rdx
0x18001f0c0  push    rbx
0x18001f0c1  push    rbp
0x18001f0c2  push    rdi
0x18001f0c3  push    r14
0x18001f0c5  push    r15
0x18001f0c7  sub     rsp, 80h
0x18001f0ce  mov     rdi, r9
0x18001f0d1  movzx   ebp, r8w
0x18001f0d5  movzx   r14d, cx
0x18001f0d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f0e0  lea     rax, WPP_GLOBAL_Control
0x18001f0e7  cmp     rcx, rax
0x18001f0ea  jz      short loc_18001F101
0x18001f0ec  mov     rcx, [rcx+10h]
0x18001f0f0  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18001f0f7  mov     edx, 0EAh
0x18001f0fc  call    WPP_SF_
0x18001f101  mov     rax, [rsp+0A8h+arg_30]
0x18001f109  xor     r15d, r15d
0x18001f10c  mov     rbx, [rsp+0A8h+arg_20]
0x18001f114  mov     [rax], r15d
0x18001f117  mov     rax, [rsp+0A8h+arg_28]
0x18001f11f  mov     [rax], r15
0x18001f122  mov     eax, 0FFEFh
0x18001f127  and     r14w, ax
0x18001f12b  mov     [rsp+0A8h+arg_0], r14w
0x18001f134  test    rbx, rbx
0x18001f137  jnz     short loc_18001F15B
0x18001f139  test    rdi, rdi
0x18001f13c  jnz     short loc_18001F15B
0x18001f13e  test    bp, bp
0x18001f141  jnz     short loc_18001F15B
0x18001f143  test    r14w, r14w
0x18001f147  jnz     short loc_18001F15B
0x18001f149  xor     eax, eax
0x18001f14b  add     rsp, 80h
0x18001f152  pop     r15
0x18001f154  pop     r14
0x18001f156  pop     rdi
0x18001f157  pop     rbp
0x18001f158  pop     rbx
0x18001f159  retn
0x18001f15b  mov     [rsp+0A8h+var_30], rsi
0x18001f160  mov     edx, 800h; uBytes
0x18001f165  mov     ecx, 40h ; '@'; uFlags
0x18001f16a  mov     [rsp+0A8h+var_38], r12
0x18001f16f  call    cs:__imp_LocalAlloc
0x18001f176  nop     dword ptr [rax+rax+00h]
0x18001f17b  mov     r12, rax
0x18001f17e  test    rax, rax
0x18001f181  jnz     short loc_18001F1A5
0x18001f183  call    cs:__imp_GetLastError
0x18001f18a  nop     dword ptr [rax+rax+00h]
0x18001f18f  mov     rcx, r12; hMem
0x18001f192  mov     esi, eax
0x18001f194  call    cs:__imp_LocalFree
0x18001f19b  nop     dword ptr [rax+rax+00h]
0x18001f1a0  jmp     loc_18001F8DD
0x18001f1a5  mov     [rsp+0A8h+var_40], r13
0x18001f1aa  mov     esi, r15d
0x18001f1ad  mov     dword ptr [rsp+0A8h+var_54], r15d
0x18001f1b2  mov     r9d, ebp
0x18001f1b5  test    bp, bp
0x18001f1b8  jz      short loc_18001F20F
0x18001f1ba  lea     ecx, ds:0[rbp*4]
0x18001f1c1  add     ecx, ebp
0x18001f1c3  shl     ecx, 2; unsigned __int16
0x18001f1c6  cmp     ecx, 0FFFFh
0x18001f1cc  ja      loc_18001F8B2
0x18001f1d2  mov     edx, 4; unsigned __int16
0x18001f1d7  mov     word ptr [rsp+0A8h+uBytes], cx
0x18001f1dc  lea     r8, [rsp+0A8h+uBytes]; unsigned __int16 *
0x18001f1e1  call    ?UShortAdd@@YAJGGPEAG@Z; UShortAdd(ushort,ushort,ushort *)
0x18001f1e6  mov     ebx, eax
0x18001f1e8  test    eax, eax
0x18001f1ea  js      loc_18001F89D
0x18001f1f0  movzx   eax, word ptr [rsp+0A8h+uBytes]
0x18001f1f5  add     eax, 6
0x18001f1f8  mov     dword ptr [rsp+0A8h+uBytes], eax
0x18001f1fc  cmp     eax, 6
0x18001f1ff  jb      loc_18001F8B2
0x18001f205  mov     rbx, [rsp+0A8h+arg_20]
0x18001f20d  jmp     short loc_18001F217
0x18001f20f  mov     dword ptr [rsp+0A8h+uBytes], 6
0x18001f217  mov     r10, cs:WPP_GLOBAL_Control
0x18001f21e  lea     rax, WPP_GLOBAL_Control
0x18001f225  xor     r8d, r8d
0x18001f228  mov     dword ptr [rsp+0A8h+uBytes+4], r15d
0x18001f22d  mov     [rsp+0A8h+var_58], r15d
0x18001f232  mov     edx, 100h
0x18001f237  mov     [rsp+0A8h+var_60], r8d
0x18001f23c  mov     r11d, r15d
0x18001f23f  mov     [rsp+0A8h+var_5C], edx
0x18001f243  mov     r13d, r15d
0x18001f246  cmp     r10, rax
0x18001f249  jz      short loc_18001F274
0x18001f24b  mov     rcx, [r10+10h]
0x18001f24f  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18001f256  mov     edx, 0EBh
0x18001f25b  call    WPP_SF_d
0x18001f260  mov     r10, cs:WPP_GLOBAL_Control
0x18001f267  mov     r11d, r15d
0x18001f26a  mov     r8d, [rsp+0A8h+var_60]
0x18001f26f  mov     edx, 100h
0x18001f274  xor     ebp, ebp
0x18001f276  cmp     bp, 2
0x18001f27a  jnb     loc_18001F470
0x18001f280  test    bp, bp
0x18001f283  cmovnz  rbx, rdi
0x18001f287  test    rbx, rbx
0x18001f28a  jz      loc_18001F436
0x18001f290  mov     rbx, [rbx]
0x18001f293  test    rbx, rbx
0x18001f296  jz      loc_18001F436
0x18001f29c  cmp     bp, 1
0x18001f2a0  jz      short loc_18001F2AC
0x18001f2a2  cmp     [rbx+24h], esi
0x18001f2a5  jnz     short loc_18001F2AC
0x18001f2a7  cmp     [rbx+28h], esi
0x18001f2aa  jz      short loc_18001F290
0x18001f2ac  xor     r14d, r14d
0x18001f2af  movzx   eax, r11w
0x18001f2b3  cmp     [rbx+24h], esi
0x18001f2b6  setnz   r14b
0x18001f2ba  xor     r15d, r15d
0x18001f2bd  cmp     [rbx+28h], esi
0x18001f2c0  mov     [r12+rax*8], rbx
0x18001f2c4  setnz   r15b
0x18001f2c8  inc     r11w
0x18001f2cc  mov     dword ptr [rsp+0A8h+uBytes+4], r11d
0x18001f2d1  cmp     r11w, dx
0x18001f2d5  jnz     short loc_18001F34B
0x18001f2d7  add     dx, dx
0x18001f2da  mov     rdi, r12
0x18001f2dd  mov     [rsp+0A8h+var_5C], edx
0x18001f2e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2e8  lea     r8, WPP_GLOBAL_Control
0x18001f2ef  cmp     rcx, r8
0x18001f2f2  jz      short loc_18001F311
0x18001f2f4  mov     rcx, [rcx+10h]
0x18001f2f8  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18001f2ff  movzx   r9d, dx
0x18001f303  mov     edx, 0ECh
0x18001f308  call    WPP_SF_d
0x18001f30d  mov     edx, [rsp+0A8h+var_5C]
0x18001f311  movzx   edx, dx
0x18001f314  mov     r8d, 40h ; '@'; uFlags
0x18001f31a  shl     rdx, 3; uBytes
0x18001f31e  mov     rcx, r12; hMem
0x18001f321  call    cs:__imp_LocalReAlloc
0x18001f328  nop     dword ptr [rax+rax+00h]
0x18001f32d  mov     r12, rax
0x18001f330  test    rax, rax
0x18001f333  jz      loc_18001F44E
0x18001f339  mov     eax, [rsp+0A8h+var_5C]
0x18001f33d  mov     r8d, [rsp+0A8h+var_60]
0x18001f342  mov     r11d, dword ptr [rsp+0A8h+uBytes+4]
0x18001f347  mov     [rsp+0A8h+var_5C], eax
0x18001f34b  add     r15w, word ptr [rsp+0A8h+var_58]
0x18001f351  lea     rax, WPP_GLOBAL_Control
0x18001f358  mov     r10, cs:WPP_GLOBAL_Control
0x18001f35f  add     r14w, r13w
0x18001f363  cmp     r10, rax
0x18001f366  jz      short loc_18001F3A6
0x18001f368  mov     r9, [rbx+8]
0x18001f36c  movzx   eax, r15w
0x18001f370  mov     [rsp+0A8h+var_70], eax
0x18001f374  mov     rax, [rbx+10h]
0x18001f378  movzx   ecx, r14w
0x18001f37c  mov     dword ptr [rsp+0A8h+lpszPrefix], ecx
0x18001f380  mov     rcx, [r10+10h]
0x18001f384  movzx   edx, bp
0x18001f387  mov     [rsp+0A8h+bAddressPrefix], edx
0x18001f38b  mov     qword ptr [rsp+0A8h+dwGroupSize], rax
0x18001f390  call    WPP_SF_SSddd
0x18001f395  mov     r10, cs:WPP_GLOBAL_Control
0x18001f39c  mov     r8d, [rsp+0A8h+var_60]
0x18001f3a1  mov     r11d, dword ptr [rsp+0A8h+uBytes+4]
0x18001f3a6  mov     rcx, [rbx+8]
0x18001f3aa  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001f3b1  inc     rax
0x18001f3b4  cmp     [rcx+rax*2], si
0x18001f3b8  jnz     short loc_18001F3B1
0x18001f3ba  movzx   edx, ax
0x18001f3bd  add     edx, edx
0x18001f3bf  cmp     edx, 0FFFFh
0x18001f3c5  ja      loc_18001F8B2
0x18001f3cb  add     dx, r8w
0x18001f3cf  cmp     dx, r8w
0x18001f3d3  jb      loc_18001F8B2
0x18001f3d9  mov     rcx, [rbx+10h]
0x18001f3dd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001f3e4  inc     rax
0x18001f3e7  cmp     [rcx+rax*2], si
0x18001f3eb  jnz     short loc_18001F3E4
0x18001f3ed  movzx   ecx, ax
0x18001f3f0  add     ecx, ecx
0x18001f3f2  cmp     ecx, 0FFFFh
0x18001f3f8  ja      loc_18001F8B2
0x18001f3fe  add     cx, dx
0x18001f401  cmp     cx, dx
0x18001f404  jb      loc_18001F8B2
0x18001f40a  lea     eax, [rcx+4]
0x18001f40d  mov     dword ptr [rsp+0A8h+uBytes+4], r11d
0x18001f412  cmp     ax, cx
0x18001f415  jb      loc_18001F8B2
0x18001f41b  mov     edx, [rsp+0A8h+var_5C]
0x18001f41f  movzx   r8d, ax
0x18001f423  mov     [rsp+0A8h+var_60], r8d
0x18001f428  movzx   r13d, r14w
0x18001f42c  mov     [rsp+0A8h+var_58], r15d
0x18001f431  jmp     loc_18001F290
0x18001f436  mov     rbx, [rsp+0A8h+arg_20]
0x18001f43e  inc     bp
0x18001f441  mov     rdi, [rsp+0A8h+arg_18]
0x18001f449  jmp     loc_18001F276
0x18001f44e  call    cs:__imp_GetLastError
0x18001f455  nop     dword ptr [rax+rax+00h]
0x18001f45a  mov     rcx, rdi; hMem
0x18001f45d  mov     esi, eax
0x18001f45f  call    cs:__imp_LocalFree
0x18001f466  nop     dword ptr [rax+rax+00h]
0x18001f46b  jmp     loc_18001F8D8
0x18001f470  lea     rax, WPP_GLOBAL_Control
0x18001f477  movzx   edi, r13w
0x18001f47b  cmp     r10, rax
0x18001f47e  jz      short loc_18001F4AF
0x18001f480  mov     rcx, [r10+10h]
0x18001f484  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18001f48b  movzx   eax, r15w
0x18001f48f  mov     edx, 0EEh
0x18001f494  mov     [rsp+0A8h+bAddressPrefix], eax
0x18001f498  movzx   r9d, r11w
0x18001f49c  mov     [rsp+0A8h+dwGroupSize], edi
0x18001f4a0  call    WPP_SF_DDD
0x18001f4a5  mov     r8d, [rsp+0A8h+var_60]
0x18001f4aa  mov     r11d, dword ptr [rsp+0A8h+uBytes+4]
0x18001f4af  test    r11w, r11w
0x18001f4b3  jnz     short loc_18001F4FD
0x18001f4b5  test    r13w, r13w
0x18001f4b9  jnz     short loc_18001F534
0x18001f4bb  test    r15w, r15w
0x18001f4bf  jnz     loc_18001F58F
0x18001f4c5  movzx   ebp, [rsp+0A8h+arg_10]
0x18001f4cd  xor     ebx, ebx
0x18001f4cf  movzx   edi, [rsp+0A8h+arg_0]
0x18001f4d7  mov     dword ptr [rsp+0A8h+arg_20], ebx
0x18001f4de  test    bp, bp
0x18001f4e1  jnz     short loc_18001F4F3
0x18001f4e3  test    di, di
0x18001f4e6  jz      loc_18001F89D
0x18001f4ec  mov     dword ptr [rsp+0A8h+arg_20], ebx
0x18001f4f3  mov     r10d, dword ptr [rsp+0A8h+uBytes]
0x18001f4f8  jmp     loc_18001F5F5
0x18001f4fd  lea     eax, [r8+4]
0x18001f501  cmp     ax, r8w
0x18001f505  jb      loc_18001F8B2
0x18001f50b  movzx   ecx, ax
0x18001f50e  add     ecx, dword ptr [rsp+0A8h+uBytes]
0x18001f512  cmp     ecx, dword ptr [rsp+0A8h+uBytes]
0x18001f516  jb      loc_18001F8B2
0x18001f51c  xor     ebx, ebx
0x18001f51e  mov     dword ptr [rsp+0A8h+uBytes], ecx
0x18001f522  mov     dword ptr [rsp+0A8h+arg_20], ebx
0x18001f529  mov     r10d, ecx
0x18001f52c  test    r13w, r13w
0x18001f530  jnz     short loc_18001F539
0x18001f532  jmp     short loc_18001F587
0x18001f534  mov     r10d, dword ptr [rsp+0A8h+uBytes]
0x18001f539  lea     ecx, [rdi+rdi]; unsigned __int16
0x18001f53c  cmp     ecx, 0FFFFh
0x18001f542  ja      loc_18001F8B2
0x18001f548  mov     edx, 4; unsigned __int16
0x18001f54d  mov     word ptr [rsp+0A8h+uBytes], cx
0x18001f552  lea     r8, [rsp+0A8h+uBytes]; unsigned __int16 *
0x18001f557  call    ?UShortAdd@@YAJGGPEAG@Z; UShortAdd(ushort,ushort,ushort *)
0x18001f55c  mov     ebx, eax
0x18001f55e  test    eax, eax
0x18001f560  js      loc_18001F89D
0x18001f566  movzx   ecx, word ptr [rsp+0A8h+uBytes]
0x18001f56b  add     ecx, r10d
0x18001f56e  cmp     ecx, r10d
0x18001f571  jb      loc_18001F8B2
0x18001f577  xor     ebx, ebx
0x18001f579  mov     dword ptr [rsp+0A8h+uBytes], ecx
0x18001f57d  mov     dword ptr [rsp+0A8h+arg_20], ebx
0x18001f584  mov     r10d, ecx
0x18001f587  test    r15w, r15w
0x18001f58b  jnz     short loc_18001F594
0x18001f58d  jmp     short loc_18001F5E5
0x18001f58f  mov     r10d, dword ptr [rsp+0A8h+uBytes]
0x18001f594  movzx   ecx, r15w
0x18001f598  add     ecx, ecx; unsigned __int16
0x18001f59a  cmp     ecx, 0FFFFh
0x18001f5a0  ja      loc_18001F8B2
0x18001f5a6  mov     edx, 4; unsigned __int16
0x18001f5ab  mov     word ptr [rsp+0A8h+uBytes], cx
  ... truncated ...
```
