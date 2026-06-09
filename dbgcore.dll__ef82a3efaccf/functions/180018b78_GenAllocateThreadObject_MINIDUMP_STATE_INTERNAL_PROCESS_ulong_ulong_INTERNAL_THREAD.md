# GenAllocateThreadObject(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,ulong,ulong,_INTERNAL_THREAD * *)

- ea: `0x180018b78`
- end: `0x180019514`
- name: `?GenAllocateThreadObject@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@KKPEAPEAU_INTERNAL_THREAD@@@Z`
- size: `2460`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS *, unsigned int, unsigned int, struct _INTERNAL_THREAD **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18001ad48`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180016b74`
- `0x180018b78`
- `0x18002c010`

## string_xrefs

- `0x180018c82`: `GenAllocateThreadObject.Open(0x%x) failed, 0x%08x`
- `0x180018d9e`: `GenAllocateThreadObject.GetContext(0x%x) failed, 0x%08x`
- `0x180018e5d`: `GenAllocateThreadObject.GetTebInfo(0x%x) failed, 0x%08x`
- `0x180018f26`: `ThreadToken(%d,%I64x,%d,%d)`
- `0x180018fd6`: `ThreadToken_SessionId(0x%08X,%d,%d,%d)`
- `0x18001907c`: `ThreadToken_User(0x%08X,%d,%d,%d)`
- `0x180019122`: `ThreadToken_Group(0x%08X,%d,%d,%d)`
- `0x1800191c8`: `ThreadToken_PrimaryGroup(0x%08X,%d,%d,%d)`
- `0x18001926e`: `ThreadToken_Privileges(0x%08X,%d,%d,%d)`
- `0x180019314`: `ThreadToken_Statistics(0x%08X,%d,%d,%d)`
- `0x1800193b8`: `ThreadToken_RestrictedSids(0x%08X,%d,%d,%d)`

## pseudocode

```c
__int64 __fastcall GenAllocateThreadObject(
        struct _MINIDUMP_STATE *a1,
        struct _INTERNAL_PROCESS *a2,
        unsigned int a3,
        unsigned int a4,
        struct _INTERNAL_THREAD **a5)
{
  struct _INTERNAL_PROCESS *v5; // r13
  unsigned int v6; // edx
  char *v11; // rax
  unsigned int *v12; // rbx
  _QWORD *v13; // r12
  int v14; // eax
  int v15; // esi
  int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // r8
  unsigned int v19; // eax
  unsigned int v20; // esi
  __int64 v21; // rcx
  __int64 v22; // rcx
  _DWORD *v23; // r14
  unsigned int v24; // eax
  unsigned int v25; // esi
  __int64 v26; // rcx
  __int64 v27; // r9
  __int64 v28; // r8
  unsigned int *v29; // rax
  unsigned int *v30; // r14
  unsigned int v31; // esi
  __int64 v32; // rdx
  unsigned int v33; // eax
  unsigned int v34; // r12d
  __int64 v35; // r8
  int v36; // edx
  __int64 v37; // rdx
  unsigned int v38; // r8d
  __int64 v39; // rdx
  unsigned int v40; // r8d
  __int64 v41; // rdx
  unsigned int v42; // r8d
  __int64 v43; // rdx
  unsigned int v44; // r8d
  __int64 v45; // rdx
  unsigned int v46; // r8d
  __int64 v47; // rdx
  unsigned int v48; // r8d
  __int64 v49; // rax
  unsigned int v50; // esi
  _WORD *v51; // rax
  _WORD *v52; // rdx
  __int64 v53; // rax
  __int64 v54; // r8
  _WORD *v55; // rcx
  _WORD *v56; // rcx
  __int64 v57; // [rsp+20h] [rbp-E0h]
  __int64 v58; // [rsp+20h] [rbp-E0h]
  __int64 v59; // [rsp+20h] [rbp-E0h]
  __int64 v60; // [rsp+20h] [rbp-E0h]
  __int64 v61; // [rsp+20h] [rbp-E0h]
  __int64 v62; // [rsp+20h] [rbp-E0h]
  __int64 v63; // [rsp+20h] [rbp-E0h]
  __int64 v64; // [rsp+20h] [rbp-E0h]
  __int64 v65; // [rsp+20h] [rbp-E0h]
  __int64 v66; // [rsp+20h] [rbp-E0h]
  __int64 v67; // [rsp+20h] [rbp-E0h]
  __int64 v68; // [rsp+28h] [rbp-D8h]
  __int64 v69; // [rsp+28h] [rbp-D8h]
  __int64 v70; // [rsp+28h] [rbp-D8h]
  __int64 v71; // [rsp+28h] [rbp-D8h]
  __int64 v72; // [rsp+28h] [rbp-D8h]
  __int64 v73; // [rsp+28h] [rbp-D8h]
  __int64 v74; // [rsp+28h] [rbp-D8h]
  __int64 v75; // [rsp+30h] [rbp-D0h]
  __int64 v76; // [rsp+30h] [rbp-D0h]
  __int64 v77; // [rsp+30h] [rbp-D0h]
  __int64 v78; // [rsp+30h] [rbp-D0h]
  __int64 v79; // [rsp+30h] [rbp-D0h]
  __int64 v80; // [rsp+30h] [rbp-D0h]
  __int64 v81; // [rsp+30h] [rbp-D0h]
  __int64 v82; // [rsp+70h] [rbp-90h] BYREF
  __int64 v83; // [rsp+78h] [rbp-88h] BYREF
  __int64 v84; // [rsp+80h] [rbp-80h] BYREF
  __int64 v85; // [rsp+88h] [rbp-78h] BYREF
  struct _INTERNAL_PROCESS *v86; // [rsp+90h] [rbp-70h]
  _WORD v87[1024]; // [rsp+A0h] [rbp-60h] BYREF

  v5 = a2;
  v86 = a2;
  v6 = *((_DWORD *)a1 + 35);
  v85 = 0;
  v84 = 0;
  if ( v6 > 0x100000 )
    return 2147942487LL;
  v11 = (char *)AllocMemory(a1, v6 + 232);
  v12 = (unsigned int *)v11;
  if ( !v11 )
    return 2147942414LL;
  *((_QWORD *)v11 + 14) = v11 + 232;
  *a5 = (struct _INTERNAL_THREAD *)v11;
  *(_DWORD *)v11 = a3;
  *((_QWORD *)v11 + 28) = 0;
  v13 = v11 + 8;
  *((_DWORD *)v11 + 6) = -1;
  v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, char *))(**((_QWORD **)a1 + 2) + 144LL))(
          *((_QWORD *)a1 + 2),
          0x1FFFFF,
          0,
          a3,
          v11 + 8);
  v15 = v14;
  if ( v14 )
  {
    if ( v14 >= 0 || v14 == -2147024809 || v14 == -2147024894 || v14 == -805306357 )
    {
      v16 = 4;
    }
    else
    {
      *((_DWORD *)a1 + 44) |= 4u;
      v16 = 1;
    }
    v12[4] = v16;
    LODWORD(v57) = v15;
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      2,
      "GenAllocateThreadObject.Open(0x%x) failed, 0x%08x",
      *v12,
      v57);
    v12[5] = v15;
    *v13 = 0;
    v12[44] = a4 & 0x40 | 1;
    return 0;
  }
  if ( *v12 == (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 2) + 160LL))(*((_QWORD *)a1 + 2)) )
  {
    v12[4] |= 2u;
    v17 = 0;
  }
  else
  {
    v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *))(**((_QWORD **)a1 + 2) + 168LL))(
            *((_QWORD *)a1 + 2),
            *v13,
            v12 + 56);
  }
  v12[6] = v17;
  v18 = *v13;
  v12[8] = 64;
  v12[44] = a4;
  v12[11] = 259;
  if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)a1 + 2) + 208LL))(
         *((_QWORD *)a1 + 2),
         *((_QWORD *)v5 + 8),
         v18) )
  {
    v12[4] |= 8u;
    v12[44] &= ~0x40u;
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, unsigned int *, unsigned int *, __int64 *, _DWORD, _BYTE))(**((_QWORD **)a1 + 2) + 504LL))(
          *((_QWORD *)a1 + 2),
          *(_QWORD *)a1,
          *v13,
          *((_QWORD *)v12 + 14),
          *((_DWORD *)a1 + 35),
          v12 + 30,
          v12 + 34,
          &v84,
          *((_DWORD *)a1 + 14),
          0);
  v20 = v19;
  if ( !v19 )
  {
    v22 = *((_QWORD *)a1 + 2);
    v83 = 0;
    v23 = v12 + 38;
    v24 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, __int64 *, unsigned int *, __int64 *, _BYTE))(*(_QWORD *)v22 + 200LL))(
            v22,
            *(_QWORD *)a1,
            *v13,
            v12 + 24,
            v12 + 26,
            v12 + 32,
            v12 + 36,
            v12 + 38,
            &v85,
            v12 + 42,
            &v83,
            0);
    v25 = v24;
    if ( v24 )
    {
      LODWORD(v59) = v24;
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        2,
        "GenAllocateThreadObject.GetTebInfo(0x%x) failed, 0x%08x",
        *v12,
        v59);
      v12[5] = v25;
      v12[4] |= 0x20u;
      v12[44] &= 0xFFFFFFD5;
      return 0;
    }
    if ( v83 )
      *((_DWORD *)a1 + 34) = 1;
    if ( (*((_DWORD *)a1 + 14) & 0x40000) == 0
      || (v26 = *((_QWORD *)a1 + 2),
          v27 = *v13,
          v28 = *v12,
          v82 = 0,
          (*(unsigned int (__fastcall **)(__int64, _QWORD, __int64, __int64, __int64 *))(*(_QWORD *)v26 + 456LL))(
            v26,
            0,
            v28,
            v27,
            &v82))
      || !v82 )
    {
      *((_QWORD *)v12 + 25) = 0;
LABEL_70:
      if ( (v12[4] & 5) == 0
        && (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, _WORD *, int))(**((_QWORD **)a1 + 2) + 552LL))(
             *((_QWORD *)a1 + 2),
             *((_QWORD *)v5 + 8),
             *v13,
             v87,
             1024) >= 0 )
      {
        if ( v87[0] )
        {
          v49 = -1;
          do
            ++v49;
          while ( v87[v49] );
          v50 = v49 + 1;
          v51 = AllocMemory(a1, 2 * ((int)v49 + 1));
          *((_QWORD *)v12 + 26) = v51;
          v52 = v51;
          if ( v51 )
          {
            v53 = v50;
            v54 = 2147483646;
            if ( v50 - 1 > 0x7FFFFFFE )
            {
              if ( v50 )
                *v52 = 0;
            }
            else
            {
              v55 = v87;
              do
              {
                if ( !v54 )
                  break;
                if ( !*v55 )
                  break;
                *v52++ = *v55++;
                --v54;
                --v53;
              }
              while ( v53 );
              v56 = v52 - 1;
              if ( v53 )
                v56 = v52;
              *v56 = 0;
            }
          }
        }
      }
      if ( *((_DWORD *)a1 + 26) )
        v12[40] = v84 - *v23;
      else
        v12[40] = 0;
      return 0;
    }
    v29 = (unsigned int *)AllocMemory(a1, 0x10000u);
    *((_QWORD *)v12 + 25) = v29;
    v30 = v29;
    if ( !v29 )
    {
LABEL_68:
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a1 + 2) + 472LL))(*((_QWORD *)a1 + 2), v82);
      v5 = v86;
      v23 = v12 + 38;
      goto LABEL_70;
    }
    memset_0(v29, 0, 0x10000u);
    v30[1] = *v12;
    v31 = 72;
    v32 = *v13;
    *((_QWORD *)v30 + 1) = *v13;
    HIDWORD(v60) = HIDWORD(v32);
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      1,
      "ThreadToken(%d,%I64x,%d,%d)");
    LODWORD(v60) = 65464;
    v33 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64, __int64, unsigned int *))(**((_QWORD **)a1 + 2)
                                                                                                + 464LL))(
            *((_QWORD *)a1 + 2),
            v82,
            12,
            *((_QWORD *)v12 + 25) + 72LL,
            v60,
            v30 + 5);
    v34 = v33;
    if ( v33 )
    {
      LODWORD(v35) = 0;
      v30[5] = 0;
      v36 = 0;
    }
    else
    {
      v35 = v30[5];
      v36 = 72;
      v31 = 8 * ((unsigned __int64)(v35 + 7) >> 3) + 72;
    }
    v30[4] = v36;
    LODWORD(v75) = v31;
    LODWORD(v68) = v35;
    LODWORD(v61) = v36;
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      1,
      "ThreadToken_SessionId(0x%08X,%d,%d,%d)",
      v33,
      v61,
      v68,
      v75);
    if ( v31 >= 0x10000 )
    {
      v30[7] = 0;
    }
    else
    {
      v34 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, unsigned int, unsigned int *))(**((_QWORD **)a1 + 2) + 464LL))(
              *((_QWORD *)a1 + 2),
              v82,
              1,
              *((_QWORD *)v12 + 25) + v31,
              0x10000 - v31,
              v30 + 7);
      if ( !v34 )
      {
        v37 = v30[7];
        v38 = v31;
        v31 += 8 * ((unsigned __int64)(v37 + 7) >> 3);
        goto LABEL_37;
      }
      v30[7] = 0;
    }
    LODWORD(v37) = 0;
    v38 = 0;
LABEL_37:
    LODWORD(v76) = v31;
    LODWORD(v69) = v37;
    LODWORD(v62) = v38;
    v30[6] = v38;
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      1,
      "ThreadToken_User(0x%08X,%d,%d,%d)",
      v34,
      v62,
      v69,
      v76);
    if ( v31 >= 0x10000 )
    {
      v30[9] = 0;
    }
    else
    {
      v34 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, unsigned int, unsigned int *))(**((_QWORD **)a1 + 2) + 464LL))(
              *((_QWORD *)a1 + 2),
              v82,
              2,
              *((_QWORD *)v12 + 25) + v31,
              0x10000 - v31,
              v30 + 9);
      if ( !v34 )
      {
        v39 = v30[9];
        v40 = v31;
        v31 += 8 * ((unsigned __int64)(v39 + 7) >> 3);
        goto LABEL_43;
      }
      v30[9] = 0;
    }
    LODWORD(v39) = 0;
    v40 = 0;
LABEL_43:
    LODWORD(v77) = v31;
    LODWORD(v70) = v39;
    LODWORD(v63) = v40;
    v30[8] = v40;
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      1,
      "ThreadToken_Group(0x%08X,%d,%d,%d)",
      v34,
      v63,
      v70,
      v77);
    if ( v31 >= 0x10000 )
    {
      v30[11] = 0;
    }
    else
    {
      v34 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, unsigned int, unsigned int *))(**((_QWORD **)a1 + 2) + 464LL))(
              *((_QWORD *)a1 + 2),
              v82,
              5,
              *((_QWORD *)v12 + 25) + v31,
              0x10000 - v31,
              v30 + 11);
      if ( !v34 )
      {
        v41 = v30[11];
        v42 = v31;
        v31 += 8 * ((unsigned __int64)(v41 + 7) >> 3);
        goto LABEL_49;
      }
      v30[11] = 0;
    }
    LODWORD(v41) = 0;
    v42 = 0;
LABEL_49:
    LODWORD(v78) = v31;
    LODWORD(v71) = v41;
    LODWORD(v64) = v42;
    v30[10] = v42;
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      1,
      "ThreadToken_PrimaryGroup(0x%08X,%d,%d,%d)",
      v34,
      v64,
      v71,
      v78);
    if ( v31 >= 0x10000 )
    {
      v30[13] = 0;
    }
    else
    {
      v34 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, unsigned int, unsigned int *))(**((_QWORD **)a1 + 2) + 464LL))(
              *((_QWORD *)a1 + 2),
              v82,
              3,
              *((_QWORD *)v12 + 25) + v31,
              0x10000 - v31,
              v30 + 13);
      if ( !v34 )
      {
        v43 = v30[13];
        v44 = v31;
        v31 += 8 * ((unsigned __int64)(v43 + 7) >> 3);
        goto LABEL_55;
      }
      v30[13] = 0;
    }
    LODWORD(v43) = 0;
    v44 = 0;
LABEL_55:
    LODWORD(v79) = v31;
    LODWORD(v72) = v43;
    LODWORD(v65) = v44;
    v30[12] = v44;
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      1,
      "ThreadToken_Privileges(0x%08X,%d,%d,%d)",
      v34,
      v65,
      v72,
      v79);
    if ( v31 >= 0x10000 )
    {
      v30[15] = 0;
    }
    else
    {
      v34 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, unsigned int, unsigned int *))(**((_QWORD **)a1 + 2) + 464LL))(
              *((_QWORD *)a1 + 2),
              v82,
              10,
              *((_QWORD *)v12 + 25) + v31,
              0x10000 - v31,
              v30 + 15);
      if ( !v34 )
      {
        v45 = v30[15];
        v46 = v31;
        v31 += 8 * ((unsigned __int64)(v45 + 7) >> 3);
        goto LABEL_61;
      }
      v30[15] = 0;
    }
    LODWORD(v45) = 0;
    v46 = 0;
LABEL_61:
    LODWORD(v80) = v31;
    LODWORD(v73) = v45;
    LODWORD(v66) = v46;
    v30[14] = v46;
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      1,
      "ThreadToken_Statistics(0x%08X,%d,%d,%d)",
      v34,
      v66,
      v73,
      v80);
    if ( v31 >= 0x10000 )
    {
      v30[17] = 0;
    }
    else
    {
      v34 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, unsigned int, unsigned int *))(**((_QWORD **)a1 + 2) + 464LL))(
              *((_QWORD *)a1 + 2),
              v82,
              11,
              *((_QWORD *)v12 + 25) + v31,
              0x10000 - v31,
              v30 + 17);
      if ( !v34 )
      {
        v47 = v30[17];
        v48 = v31;
        v31 += 8 * ((unsigned __int64)(v47 + 7) >> 3);
LABEL_67:
        LODWORD(v81) = v31;
        LODWORD(v74) = v47;
        LODWORD(v67) = v48;
        v30[16] = v48;
        (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
          *((_QWORD *)a1 + 5),
          1,
          "ThreadToken_RestrictedSids(0x%08X,%d,%d,%d)",
          v34,
          v67,
          v74,
          v81);
        *v30 = v31;
        v13 = v12 + 2;
        goto LABEL_68;
      }
      v30[17] = 0;
    }
    LODWORD(v47) = 0;
    v48 = 0;
    goto LABEL_67;
  }
  v21 = *((_QWORD *)a1 + 5);
  LODWORD(v58) = v19;
  *((_DWORD *)a1 + 44) |= 4u;
  (*(void (**)(__int64, __int64, const char *, ...))(*(_QWORD *)v21 + 8LL))(
    v21,
    2,
    "GenAllocateThreadObject.GetContext(0x%x) failed, 0x%08x",
    *v12,
    v58);
  v12[4] |= 0x10u;
  v12[44] &= 0xFFFFFFC1;
  v12[5] = v20;
  return 0;
}

```

## disassembly

```asm
0x180018b78  mov     [rsp-8+arg_10], rbx
0x180018b7d  push    rbp
0x180018b7e  push    rsi
0x180018b7f  push    rdi
0x180018b80  push    r12
0x180018b82  push    r13
0x180018b84  push    r14
0x180018b86  push    r15
0x180018b88  lea     rbp, [rsp-7B0h]
0x180018b90  sub     rsp, 8B0h
0x180018b97  mov     rax, cs:__security_cookie
0x180018b9e  xor     rax, rsp
0x180018ba1  mov     [rbp+7E0h+var_40], rax
0x180018ba8  mov     r15, [rbp+7E0h+arg_20]
0x180018baf  xor     r12d, r12d
0x180018bb2  mov     r13, rdx
0x180018bb5  mov     [rbp+7E0h+var_850], rdx
0x180018bb9  mov     edx, [rcx+8Ch]
0x180018bbf  mov     r14d, r9d
0x180018bc2  mov     [rbp+7E0h+var_858], r12
0x180018bc6  mov     esi, r8d
0x180018bc9  mov     [rbp+7E0h+var_860], r12
0x180018bcd  mov     rdi, rcx
0x180018bd0  cmp     edx, 100000h
0x180018bd6  jbe     short loc_180018BE2
0x180018bd8  mov     eax, 80070057h
0x180018bdd  jmp     loc_1800194EA
0x180018be2  add     edx, 0E8h; unsigned int
0x180018be8  call    ?AllocMemory@@YAPEAXPEAU_MINIDUMP_STATE@@K@Z; AllocMemory(_MINIDUMP_STATE *,ulong)
0x180018bed  mov     rbx, rax
0x180018bf0  test    rax, rax
0x180018bf3  jnz     short loc_180018BFF
0x180018bf5  mov     eax, 8007000Eh
0x180018bfa  jmp     loc_1800194EA
0x180018bff  add     rax, 0E8h
0x180018c05  mov     r9d, esi
0x180018c08  mov     [rbx+70h], rax
0x180018c0c  xor     r8d, r8d
0x180018c0f  mov     [r15], rbx
0x180018c12  mov     edx, 1FFFFFh
0x180018c17  mov     [rbx], esi
0x180018c19  lea     r15, [rbx+0E0h]
0x180018c20  mov     [r15], r12
0x180018c23  lea     r12, [rbx+8]
0x180018c27  mov     dword ptr [rbx+18h], 0FFFFFFFFh
0x180018c2e  mov     rcx, [rdi+10h]
0x180018c32  mov     [rsp+8E0h+var_8C0], r12
0x180018c37  mov     rax, [rcx]
0x180018c3a  mov     rax, [rax+90h]
0x180018c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c46  mov     esi, eax
0x180018c48  test    eax, eax
0x180018c4a  jz      short loc_180018CC3
0x180018c4c  mov     r15d, 1
0x180018c52  test    eax, eax
0x180018c54  jns     short loc_180018C7A
0x180018c56  cmp     eax, 80070057h
0x180018c5b  jz      short loc_180018C7A
0x180018c5d  cmp     eax, 80070002h
0x180018c62  jz      short loc_180018C7A
0x180018c64  cmp     eax, 0D000000Bh
0x180018c69  jz      short loc_180018C7A
0x180018c6b  lea     eax, [r15+3]
0x180018c6f  or      [rdi+0B0h], eax
0x180018c75  mov     eax, r15d
0x180018c78  jmp     short loc_180018C7F
0x180018c7a  mov     eax, 4
0x180018c7f  mov     [rbx+10h], eax
0x180018c82  lea     r8, aGenallocatethr_1; "GenAllocateThreadObject.Open(0x%x) fail"...
0x180018c89  mov     rcx, [rdi+28h]
0x180018c8d  mov     edx, 2
0x180018c92  mov     r9d, [rbx]
0x180018c95  mov     dword ptr [rsp+8E0h+var_8C0], esi
0x180018c99  mov     rax, [rcx]
0x180018c9c  mov     rax, [rax+8]
0x180018ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ca5  and     r14d, 40h
0x180018ca9  mov     [rbx+14h], esi
0x180018cac  or      r14d, r15d
0x180018caf  mov     qword ptr [r12], 0
0x180018cb7  mov     [rbx+0B0h], r14d
0x180018cbe  jmp     loc_1800194E8
0x180018cc3  mov     rcx, [rdi+10h]
0x180018cc7  mov     rax, [rcx]
0x180018cca  mov     rax, [rax+0A0h]
0x180018cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cd6  cmp     [rbx], eax
0x180018cd8  jnz     short loc_180018CE2
0x180018cda  or      dword ptr [rbx+10h], 2
0x180018cde  xor     eax, eax
0x180018ce0  jmp     short loc_180018CFC
0x180018ce2  mov     rcx, [rdi+10h]
0x180018ce6  mov     r8, r15
0x180018ce9  mov     rdx, [r12]
0x180018ced  mov     rax, [rcx]
0x180018cf0  mov     rax, [rax+0A8h]
0x180018cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cfc  mov     [rbx+18h], eax
0x180018cff  lea     r9, [rbx+20h]
0x180018d03  mov     r8, [r12]
0x180018d07  mov     dword ptr [r9], 40h ; '@'
0x180018d0e  mov     [rbx+0B0h], r14d
0x180018d15  mov     dword ptr [rbx+2Ch], 103h
0x180018d1c  mov     rcx, [rdi+10h]
0x180018d20  mov     rdx, [r13+40h]
0x180018d24  mov     rax, [rcx]
0x180018d27  mov     rax, [rax+0D0h]
0x180018d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d33  test    eax, eax
0x180018d35  jz      short loc_180018D42
0x180018d37  or      dword ptr [rbx+10h], 8
0x180018d3b  and     dword ptr [rbx+0B0h], 0FFFFFFBFh
0x180018d42  mov     edx, [rdi+38h]
0x180018d45  lea     r8, [rbx+88h]
0x180018d4c  mov     rcx, [rdi+10h]
0x180018d50  lea     r9, [rbx+78h]
0x180018d54  mov     byte ptr [rsp+8E0h+var_898], 0
0x180018d59  mov     dword ptr [rsp+8E0h+var_8A0], edx
0x180018d5d  lea     rdx, [rbp+7E0h+var_860]
0x180018d61  mov     [rsp+8E0h+var_8A8], rdx
0x180018d66  mov     edx, [rdi+8Ch]
0x180018d6c  mov     rax, [rcx]
0x180018d6f  mov     [rsp+8E0h+var_8B0], r8
0x180018d74  mov     r8, [r12]
0x180018d78  mov     [rsp+8E0h+var_8B8], r9
0x180018d7d  mov     rax, [rax+1F8h]
0x180018d84  mov     r9, [rbx+70h]
0x180018d88  mov     dword ptr [rsp+8E0h+var_8C0], edx
0x180018d8c  mov     rdx, [rdi]
0x180018d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d94  mov     esi, eax
0x180018d96  test    eax, eax
0x180018d98  jz      short loc_180018DDB
0x180018d9a  mov     rcx, [rdi+28h]
0x180018d9e  lea     r8, aGenallocatethr; "GenAllocateThreadObject.GetContext(0x%x"...
0x180018da5  mov     eax, 4
0x180018daa  mov     dword ptr [rsp+8E0h+var_8C0], esi
0x180018dae  or      [rdi+0B0h], eax
0x180018db4  mov     r9d, [rbx]
0x180018db7  mov     rdx, [rcx]
0x180018dba  mov     rax, [rdx+8]
0x180018dbe  mov     edx, 2
0x180018dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dc8  or      dword ptr [rbx+10h], 10h
0x180018dcc  and     dword ptr [rbx+0B0h], 0FFFFFFC1h
0x180018dd3  mov     [rbx+14h], esi
0x180018dd6  jmp     loc_1800194E8
0x180018ddb  mov     rcx, [rdi+10h]
0x180018ddf  lea     rdx, [rbx+0A8h]
0x180018de6  mov     [rsp+8E0h+var_888], 0
0x180018deb  lea     r8, [rbx+90h]
0x180018df2  mov     [rsp+8E0h+var_868], 0
0x180018dfb  lea     r10, [rbx+80h]
0x180018e02  lea     r11, [rbx+68h]
0x180018e06  mov     rax, [rcx]
0x180018e09  lea     rsi, [rsp+8E0h+var_868]
0x180018e0e  mov     [rsp+8E0h+var_890], rsi
0x180018e13  lea     r14, [rbx+98h]
0x180018e1a  mov     [rsp+8E0h+var_898], rdx
0x180018e1f  lea     r9, [rbx+60h]
0x180018e23  lea     rdx, [rbp+7E0h+var_858]
0x180018e27  mov     rax, [rax+0C8h]
0x180018e2e  mov     [rsp+8E0h+var_8A0], rdx
0x180018e33  mov     rdx, [rdi]
0x180018e36  mov     [rsp+8E0h+var_8A8], r14
0x180018e3b  mov     [rsp+8E0h+var_8B0], r8
0x180018e40  mov     r8, [r12]
0x180018e44  mov     [rsp+8E0h+var_8B8], r10
0x180018e49  mov     [rsp+8E0h+var_8C0], r11
0x180018e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e53  mov     esi, eax
0x180018e55  test    eax, eax
0x180018e57  jz      short loc_180018E93
0x180018e59  mov     rcx, [rdi+28h]
0x180018e5d  lea     r8, aGenallocatethr_0; "GenAllocateThreadObject.GetTebInfo(0x%x"...
0x180018e64  mov     r9d, [rbx]
0x180018e67  mov     dword ptr [rsp+8E0h+var_8C0], esi
0x180018e6b  mov     rdx, [rcx]
0x180018e6e  mov     rax, [rdx+8]
0x180018e72  mov     edx, 2
0x180018e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e7c  mov     eax, 20h ; ' '
0x180018e81  mov     [rbx+14h], esi
0x180018e84  or      [rbx+10h], eax
0x180018e87  and     dword ptr [rbx+0B0h], 0FFFFFFD5h
0x180018e8e  jmp     loc_1800194E8
0x180018e93  xor     esi, esi
0x180018e95  lea     r15d, [rsi+1]
0x180018e99  cmp     [rsp+8E0h+var_868], rsi
0x180018e9e  jz      short loc_180018EA7
0x180018ea0  mov     [rdi+88h], r15d
0x180018ea7  test    dword ptr [rdi+38h], 40000h
0x180018eae  jz      loc_1800193FB
0x180018eb4  mov     rcx, [rdi+10h]
0x180018eb8  lea     rdx, [rsp+8E0h+var_870]
0x180018ebd  mov     r9, [r12]
0x180018ec1  mov     r8d, [rbx]
0x180018ec4  mov     [rsp+8E0h+var_870], rsi
0x180018ec9  mov     rax, [rcx]
0x180018ecc  mov     [rsp+8E0h+var_8C0], rdx
0x180018ed1  xor     edx, edx
0x180018ed3  mov     rax, [rax+1C8h]
0x180018eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018edf  test    eax, eax
0x180018ee1  jnz     loc_1800193FB
0x180018ee7  cmp     [rsp+8E0h+var_870], rsi
0x180018eec  jz      loc_1800193FB
0x180018ef2  mov     r13d, 10000h
0x180018ef8  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x180018efb  mov     edx, r13d; unsigned int
0x180018efe  call    ?AllocMemory@@YAPEAXPEAU_MINIDUMP_STATE@@K@Z; AllocMemory(_MINIDUMP_STATE *,ulong)
0x180018f03  mov     [rbx+0C8h], rax
0x180018f0a  mov     r14, rax
0x180018f0d  test    rax, rax
0x180018f10  jz      loc_1800193D6
0x180018f16  mov     r8d, r13d; Size
0x180018f19  xor     edx, edx; Val
0x180018f1b  mov     rcx, rax; void *
0x180018f1e  call    memset_0
0x180018f23  mov     r9d, [rbx]
0x180018f26  lea     r8, aThreadtokenDI6; "ThreadToken(%d,%I64x,%d,%d)"
0x180018f2d  mov     [r14+4], r9d
0x180018f31  mov     esi, 48h ; 'H'
0x180018f36  mov     rdx, [r12]
0x180018f3a  mov     [r14+8], rdx
0x180018f3e  mov     rcx, [rdi+28h]
0x180018f42  mov     dword ptr [rsp+8E0h+var_8B0], r13d
0x180018f47  mov     dword ptr [rsp+8E0h+var_8B8], esi
0x180018f4b  mov     [rsp+8E0h+var_8C0], rdx
0x180018f50  mov     edx, r15d
0x180018f53  mov     rax, [rcx]
0x180018f56  mov     rax, [rax+8]
0x180018f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f5f  mov     rcx, [rdi+10h]
0x180018f63  lea     rdx, [r14+14h]
0x180018f67  mov     r9, [rbx+0C8h]
0x180018f6e  lea     r8d, [rsi-3Ch]
0x180018f72  mov     [rsp+8E0h+var_8B8], rdx
0x180018f77  add     r9, rsi
0x180018f7a  mov     rdx, [rsp+8E0h+var_870]
0x180018f7f  mov     rax, [rcx]
0x180018f82  mov     dword ptr [rsp+8E0h+var_8C0], 0FFB8h
0x180018f8a  mov     rax, [rax+1D0h]
0x180018f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f96  mov     r12d, eax
0x180018f99  test    eax, eax
0x180018f9b  jnz     short loc_180018FB5
0x180018f9d  mov     r8d, [r14+14h]
0x180018fa1  lea     edx, [rax+48h]
0x180018fa4  lea     rcx, [r8+7]
0x180018fa8  shr     rcx, 3
0x180018fac  lea     esi, ds:48h[rcx*8]
0x180018fb3  jmp     short loc_180018FC2
0x180018fb5  xor     r8d, r8d
0x180018fb8  mov     dword ptr [r14+14h], 0
0x180018fc0  xor     edx, edx
0x180018fc2  mov     [r14+10h], edx
0x180018fc6  mov     r9d, r12d
0x180018fc9  mov     rcx, [rdi+28h]
0x180018fcd  mov     dword ptr [rsp+8E0h+var_8B0], esi
0x180018fd1  mov     dword ptr [rsp+8E0h+var_8B8], r8d
0x180018fd6  lea     r8, aThreadtokenSes; "ThreadToken_SessionId(0x%08X,%d,%d,%d)"
0x180018fdd  mov     dword ptr [rsp+8E0h+var_8C0], edx
0x180018fe1  mov     edx, r15d
0x180018fe4  mov     rax, [rcx]
0x180018fe7  mov     rax, [rax+8]
0x180018feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ff0  lea     r8, [r14+1Ch]
0x180018ff4  cmp     esi, r13d
0x180018ff7  jnb     short loc_180019051
0x180018ff9  mov     rcx, [rdi+10h]
0x180018ffd  mov     edx, r13d
0x180019000  sub     edx, esi
0x180019002  mov     [rsp+8E0h+var_8B8], r8
0x180019007  mov     dword ptr [rsp+8E0h+var_8C0], edx
0x18001900b  mov     r8d, r15d
0x18001900e  mov     rdx, [rsp+8E0h+var_870]
0x180019013  mov     rax, [rcx]
0x180019016  mov     r9d, esi
0x180019019  add     r9, [rbx+0C8h]
0x180019020  mov     rax, [rax+1D0h]
0x180019027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001902c  mov     r12d, eax
0x18001902f  test    eax, eax
0x180019031  jnz     short loc_180019047
0x180019033  mov     edx, [r14+1Ch]
0x180019037  mov     r8d, esi
0x18001903a  lea     rax, [rdx+7]
0x18001903e  shr     rax, 3
0x180019042  lea     esi, [rsi+rax*8]
0x180019045  jmp     short loc_18001905D
0x180019047  mov     dword ptr [r14+1Ch], 0
0x18001904f  jmp     short loc_180019058
0x180019051  mov     dword ptr [r8], 0
0x180019058  xor     edx, edx
0x18001905a  xor     r8d, r8d
0x18001905d  mov     eax, 18h
0x180019062  mov     dword ptr [rsp+8E0h+var_8B0], esi
0x180019066  mov     dword ptr [rsp+8E0h+var_8B8], edx
0x18001906a  mov     rcx, r14
  ... truncated ...
```
