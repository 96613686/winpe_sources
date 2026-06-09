# CreateNewFilterBlob(ushort,_EAPTLS_HASH *,ushort,_EAPTLS_EKU_NODE *,_EAPTLS_EKU_NODE *,uchar * *,ulong *)

- ea: `0x18001d4e0`
- end: `0x18001dd1a`
- name: `?CreateNewFilterBlob@@YAKGPEAU_EAPTLS_HASH@@GPEAU_EAPTLS_EKU_NODE@@1PEAPEAEPEAK@Z`
- size: `2106`
- prototype: `unsigned int __fastcall(unsigned __int16, struct _EAPTLS_HASH *, unsigned __int16, struct _EAPTLS_EKU_NODE *, struct _EAPTLS_EKU_NODE *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000f750`
- `0x180066c8c`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18001d4e0`
- `0x1800201b8`
- `0x180020420`
- `0x18002d1a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001db5c`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001db9c`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001db5c`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001db9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d86d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d86d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da1e`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18001d73e`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18001d73e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d59e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001da10`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d59e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001da10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d5b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d878`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dc9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dcb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d5b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d878`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dc9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dcb3`
- `rtutils!TraceDumpExA` at `0x18001dc96`
- `rtutils!TraceDumpExA` at `0x18001dc96`

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
0x18001d4e0  mov     [rsp+arg_18], r9
0x18001d4e5  mov     [rsp+arg_10], r8w
0x18001d4eb  mov     [rsp+arg_8], rdx
0x18001d4f0  push    rbx
0x18001d4f1  push    rbp
0x18001d4f2  push    rdi
0x18001d4f3  push    r14
0x18001d4f5  push    r15
0x18001d4f7  sub     rsp, 80h
0x18001d4fe  mov     rdi, r9
0x18001d501  movzx   ebp, r8w
0x18001d505  movzx   r14d, cx
0x18001d509  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d510  lea     rax, WPP_GLOBAL_Control
0x18001d517  cmp     rcx, rax
0x18001d51a  jz      short loc_18001D531
0x18001d51c  mov     rcx, [rcx+10h]
0x18001d520  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18001d527  mov     edx, 0EAh
0x18001d52c  call    WPP_SF_
0x18001d531  mov     rax, [rsp+0A8h+arg_30]
0x18001d539  xor     r15d, r15d
0x18001d53c  mov     rbx, [rsp+0A8h+arg_20]
0x18001d544  mov     [rax], r15d
0x18001d547  mov     rax, [rsp+0A8h+arg_28]
0x18001d54f  mov     [rax], r15
0x18001d552  mov     eax, 0FFEFh
0x18001d557  and     r14w, ax
0x18001d55b  mov     [rsp+0A8h+arg_0], r14w
0x18001d564  test    rbx, rbx
0x18001d567  jnz     short loc_18001D58A
0x18001d569  test    rdi, rdi
0x18001d56c  jnz     short loc_18001D58A
0x18001d56e  test    bp, bp
0x18001d571  jnz     short loc_18001D58A
0x18001d573  test    r14w, r14w
0x18001d577  jnz     short loc_18001D58A
0x18001d579  xor     eax, eax
0x18001d57b  add     rsp, 80h
0x18001d582  pop     r15
0x18001d584  pop     r14
0x18001d586  pop     rdi
0x18001d587  pop     rbp
0x18001d588  pop     rbx
0x18001d589  retn
0x18001d58a  mov     [rsp+0A8h+var_30], rsi
0x18001d58f  mov     edx, 800h; uBytes
0x18001d594  mov     ecx, 40h ; '@'; uFlags
0x18001d599  mov     [rsp+0A8h+var_38], r12
0x18001d59e  call    cs:__imp_LocalAlloc
0x18001d5a4  mov     r12, rax
0x18001d5a7  test    rax, rax
0x18001d5aa  jnz     short loc_18001D5C2
0x18001d5ac  call    cs:__imp_GetLastError
0x18001d5b2  mov     rcx, r12; hMem
0x18001d5b5  mov     esi, eax
0x18001d5b7  call    cs:__imp_LocalFree
0x18001d5bd  jmp     loc_18001DCD0
0x18001d5c2  mov     [rsp+0A8h+var_40], r13
0x18001d5c7  mov     esi, r15d
0x18001d5ca  mov     dword ptr [rsp+0A8h+var_54], r15d
0x18001d5cf  mov     r9d, ebp
0x18001d5d2  test    bp, bp
0x18001d5d5  jz      short loc_18001D62C
0x18001d5d7  lea     ecx, ds:0[rbp*4]
0x18001d5de  add     ecx, ebp
0x18001d5e0  shl     ecx, 2; unsigned __int16
0x18001d5e3  cmp     ecx, 0FFFFh
0x18001d5e9  ja      loc_18001DCAB
0x18001d5ef  mov     edx, 4; unsigned __int16
0x18001d5f4  mov     word ptr [rsp+0A8h+uBytes], cx
0x18001d5f9  lea     r8, [rsp+0A8h+uBytes]; unsigned __int16 *
0x18001d5fe  call    ?UShortAdd@@YAJGGPEAG@Z; UShortAdd(ushort,ushort,ushort *)
0x18001d603  mov     ebx, eax
0x18001d605  test    eax, eax
0x18001d607  js      loc_18001DC9C
0x18001d60d  movzx   eax, word ptr [rsp+0A8h+uBytes]
0x18001d612  add     eax, 6
0x18001d615  mov     dword ptr [rsp+0A8h+uBytes], eax
0x18001d619  cmp     eax, 6
0x18001d61c  jb      loc_18001DCAB
0x18001d622  mov     rbx, [rsp+0A8h+arg_20]
0x18001d62a  jmp     short loc_18001D634
0x18001d62c  mov     dword ptr [rsp+0A8h+uBytes], 6
0x18001d634  mov     r10, cs:WPP_GLOBAL_Control
0x18001d63b  lea     rax, WPP_GLOBAL_Control
0x18001d642  xor     r8d, r8d
0x18001d645  mov     dword ptr [rsp+0A8h+uBytes+4], r15d
0x18001d64a  mov     [rsp+0A8h+var_58], r15d
0x18001d64f  mov     edx, 100h
0x18001d654  mov     [rsp+0A8h+var_60], r8d
0x18001d659  mov     r11d, r15d
0x18001d65c  mov     [rsp+0A8h+var_5C], edx
0x18001d660  mov     r13d, r15d
0x18001d663  cmp     r10, rax
0x18001d666  jz      short loc_18001D691
0x18001d668  mov     rcx, [r10+10h]
0x18001d66c  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18001d673  mov     edx, 0EBh
0x18001d678  call    WPP_SF_d
0x18001d67d  mov     r10, cs:WPP_GLOBAL_Control
0x18001d684  mov     r11d, r15d
0x18001d687  mov     r8d, [rsp+0A8h+var_60]
0x18001d68c  mov     edx, 100h
0x18001d691  xor     ebp, ebp
0x18001d693  cmp     bp, 2
0x18001d697  jnb     loc_18001D883
0x18001d69d  test    bp, bp
0x18001d6a0  cmovnz  rbx, rdi
0x18001d6a4  test    rbx, rbx
0x18001d6a7  jz      loc_18001D855
0x18001d6ad  mov     rbx, [rbx]
0x18001d6b0  test    rbx, rbx
0x18001d6b3  jz      loc_18001D855
0x18001d6b9  cmp     bp, 1
0x18001d6bd  jz      short loc_18001D6C9
0x18001d6bf  cmp     [rbx+24h], esi
0x18001d6c2  jnz     short loc_18001D6C9
0x18001d6c4  cmp     [rbx+28h], esi
0x18001d6c7  jz      short loc_18001D6AD
0x18001d6c9  xor     r14d, r14d
0x18001d6cc  movzx   eax, r11w
0x18001d6d0  cmp     [rbx+24h], esi
0x18001d6d3  setnz   r14b
0x18001d6d7  xor     r15d, r15d
0x18001d6da  cmp     [rbx+28h], esi
0x18001d6dd  mov     [r12+rax*8], rbx
0x18001d6e1  setnz   r15b
0x18001d6e5  inc     r11w
0x18001d6e9  mov     dword ptr [rsp+0A8h+uBytes+4], r11d
0x18001d6ee  cmp     r11w, dx
0x18001d6f2  jnz     short loc_18001D762
0x18001d6f4  add     dx, dx
0x18001d6f7  mov     rdi, r12
0x18001d6fa  mov     [rsp+0A8h+var_5C], edx
0x18001d6fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d705  lea     r8, WPP_GLOBAL_Control
0x18001d70c  cmp     rcx, r8
0x18001d70f  jz      short loc_18001D72E
0x18001d711  mov     rcx, [rcx+10h]
0x18001d715  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18001d71c  movzx   r9d, dx
0x18001d720  mov     edx, 0ECh
0x18001d725  call    WPP_SF_d
0x18001d72a  mov     edx, [rsp+0A8h+var_5C]
0x18001d72e  movzx   edx, dx
0x18001d731  mov     r8d, 40h ; '@'; uFlags
0x18001d737  shl     rdx, 3; uBytes
0x18001d73b  mov     rcx, r12; hMem
0x18001d73e  call    cs:__imp_LocalReAlloc
0x18001d744  mov     r12, rax
0x18001d747  test    rax, rax
0x18001d74a  jz      loc_18001D86D
0x18001d750  mov     eax, [rsp+0A8h+var_5C]
0x18001d754  mov     r8d, [rsp+0A8h+var_60]
0x18001d759  mov     r11d, dword ptr [rsp+0A8h+uBytes+4]
0x18001d75e  mov     [rsp+0A8h+var_5C], eax
0x18001d762  add     r15w, word ptr [rsp+0A8h+var_58]
0x18001d768  lea     rax, WPP_GLOBAL_Control
0x18001d76f  mov     r10, cs:WPP_GLOBAL_Control
0x18001d776  add     r14w, r13w
0x18001d77a  cmp     r10, rax
0x18001d77d  jz      short loc_18001D7BD
0x18001d77f  mov     r9, [rbx+8]
0x18001d783  movzx   eax, r15w
0x18001d787  mov     [rsp+0A8h+var_70], eax
0x18001d78b  mov     rax, [rbx+10h]
0x18001d78f  movzx   ecx, r14w
0x18001d793  mov     dword ptr [rsp+0A8h+lpszPrefix], ecx
0x18001d797  mov     rcx, [r10+10h]
0x18001d79b  movzx   edx, bp
0x18001d79e  mov     [rsp+0A8h+bAddressPrefix], edx
0x18001d7a2  mov     qword ptr [rsp+0A8h+dwGroupSize], rax
0x18001d7a7  call    WPP_SF_SSddd
0x18001d7ac  mov     r10, cs:WPP_GLOBAL_Control
0x18001d7b3  mov     r8d, [rsp+0A8h+var_60]
0x18001d7b8  mov     r11d, dword ptr [rsp+0A8h+uBytes+4]
0x18001d7bd  mov     rcx, [rbx+8]
0x18001d7c1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001d7c8  nop     dword ptr [rax+rax+00000000h]
0x18001d7d0  inc     rax
0x18001d7d3  cmp     [rcx+rax*2], si
0x18001d7d7  jnz     short loc_18001D7D0
0x18001d7d9  movzx   edx, ax
0x18001d7dc  add     edx, edx
0x18001d7de  cmp     edx, 0FFFFh
0x18001d7e4  ja      loc_18001DCAB
0x18001d7ea  add     dx, r8w
0x18001d7ee  cmp     dx, r8w
0x18001d7f2  jb      loc_18001DCAB
0x18001d7f8  mov     rcx, [rbx+10h]
0x18001d7fc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001d803  inc     rax
0x18001d806  cmp     [rcx+rax*2], si
0x18001d80a  jnz     short loc_18001D803
0x18001d80c  movzx   ecx, ax
0x18001d80f  add     ecx, ecx
0x18001d811  cmp     ecx, 0FFFFh
0x18001d817  ja      loc_18001DCAB
0x18001d81d  add     cx, dx
0x18001d820  cmp     cx, dx
0x18001d823  jb      loc_18001DCAB
0x18001d829  lea     eax, [rcx+4]
0x18001d82c  mov     dword ptr [rsp+0A8h+uBytes+4], r11d
0x18001d831  cmp     ax, cx
0x18001d834  jb      loc_18001DCAB
0x18001d83a  mov     edx, [rsp+0A8h+var_5C]
0x18001d83e  movzx   r8d, ax
0x18001d842  mov     [rsp+0A8h+var_60], r8d
0x18001d847  movzx   r13d, r14w
0x18001d84b  mov     [rsp+0A8h+var_58], r15d
0x18001d850  jmp     loc_18001D6AD
0x18001d855  mov     rbx, [rsp+0A8h+arg_20]
0x18001d85d  inc     bp
0x18001d860  mov     rdi, [rsp+0A8h+arg_18]
0x18001d868  jmp     loc_18001D693
0x18001d86d  call    cs:__imp_GetLastError
0x18001d873  mov     rcx, rdi; hMem
0x18001d876  mov     esi, eax
0x18001d878  call    cs:__imp_LocalFree
0x18001d87e  jmp     loc_18001DCCB
0x18001d883  lea     rax, WPP_GLOBAL_Control
0x18001d88a  movzx   edi, r13w
0x18001d88e  cmp     r10, rax
0x18001d891  jz      short loc_18001D8C2
0x18001d893  mov     rcx, [r10+10h]
0x18001d897  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18001d89e  movzx   eax, r15w
0x18001d8a2  mov     edx, 0EEh
0x18001d8a7  mov     [rsp+0A8h+bAddressPrefix], eax
0x18001d8ab  movzx   r9d, r11w
0x18001d8af  mov     [rsp+0A8h+dwGroupSize], edi
0x18001d8b3  call    WPP_SF_DDD
0x18001d8b8  mov     r8d, [rsp+0A8h+var_60]
0x18001d8bd  mov     r11d, dword ptr [rsp+0A8h+uBytes+4]
0x18001d8c2  test    r11w, r11w
0x18001d8c6  jnz     short loc_18001D910
0x18001d8c8  test    r13w, r13w
0x18001d8cc  jnz     short loc_18001D947
0x18001d8ce  test    r15w, r15w
0x18001d8d2  jnz     loc_18001D9A2
0x18001d8d8  movzx   ebp, [rsp+0A8h+arg_10]
0x18001d8e0  xor     ebx, ebx
0x18001d8e2  movzx   edi, [rsp+0A8h+arg_0]
0x18001d8ea  mov     dword ptr [rsp+0A8h+arg_20], ebx
0x18001d8f1  test    bp, bp
0x18001d8f4  jnz     short loc_18001D906
0x18001d8f6  test    di, di
0x18001d8f9  jz      loc_18001DC9C
0x18001d8ff  mov     dword ptr [rsp+0A8h+arg_20], ebx
0x18001d906  mov     r10d, dword ptr [rsp+0A8h+uBytes]
0x18001d90b  jmp     loc_18001DA08
0x18001d910  lea     eax, [r8+4]
0x18001d914  cmp     ax, r8w
0x18001d918  jb      loc_18001DCAB
0x18001d91e  movzx   ecx, ax
0x18001d921  add     ecx, dword ptr [rsp+0A8h+uBytes]
0x18001d925  cmp     ecx, dword ptr [rsp+0A8h+uBytes]
0x18001d929  jb      loc_18001DCAB
0x18001d92f  xor     ebx, ebx
0x18001d931  mov     dword ptr [rsp+0A8h+uBytes], ecx
0x18001d935  mov     dword ptr [rsp+0A8h+arg_20], ebx
0x18001d93c  mov     r10d, ecx
0x18001d93f  test    r13w, r13w
0x18001d943  jnz     short loc_18001D94C
0x18001d945  jmp     short loc_18001D99A
0x18001d947  mov     r10d, dword ptr [rsp+0A8h+uBytes]
0x18001d94c  lea     ecx, [rdi+rdi]; unsigned __int16
0x18001d94f  cmp     ecx, 0FFFFh
0x18001d955  ja      loc_18001DCAB
0x18001d95b  mov     edx, 4; unsigned __int16
0x18001d960  mov     word ptr [rsp+0A8h+uBytes], cx
0x18001d965  lea     r8, [rsp+0A8h+uBytes]; unsigned __int16 *
0x18001d96a  call    ?UShortAdd@@YAJGGPEAG@Z; UShortAdd(ushort,ushort,ushort *)
0x18001d96f  mov     ebx, eax
0x18001d971  test    eax, eax
0x18001d973  js      loc_18001DC9C
0x18001d979  movzx   ecx, word ptr [rsp+0A8h+uBytes]
0x18001d97e  add     ecx, r10d
0x18001d981  cmp     ecx, r10d
0x18001d984  jb      loc_18001DCAB
0x18001d98a  xor     ebx, ebx
0x18001d98c  mov     dword ptr [rsp+0A8h+uBytes], ecx
0x18001d990  mov     dword ptr [rsp+0A8h+arg_20], ebx
0x18001d997  mov     r10d, ecx
0x18001d99a  test    r15w, r15w
0x18001d99e  jnz     short loc_18001D9A7
0x18001d9a0  jmp     short loc_18001D9F8
0x18001d9a2  mov     r10d, dword ptr [rsp+0A8h+uBytes]
0x18001d9a7  movzx   ecx, r15w
0x18001d9ab  add     ecx, ecx; unsigned __int16
0x18001d9ad  cmp     ecx, 0FFFFh
0x18001d9b3  ja      loc_18001DCAB
0x18001d9b9  mov     edx, 4; unsigned __int16
0x18001d9be  mov     word ptr [rsp+0A8h+uBytes], cx
0x18001d9c3  lea     r8, [rsp+0A8h+uBytes]; unsigned __int16 *
0x18001d9c8  call    ?UShortAdd@@YAJGGPEAG@Z; UShortAdd(ushort,ushort,ushort *)
0x18001d9cd  mov     ebx, eax
0x18001d9cf  test    eax, eax
0x18001d9d1  js      loc_18001DC9C
  ... truncated ...
```
