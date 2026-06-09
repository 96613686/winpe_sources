# PlaiIncrementCollectors(_SET_INSTANCE *,ulong *)

- ea: `0x1800ea8fc`
- end: `0x1800eb213`
- name: `?PlaiIncrementCollectors@@YAJPEAU_SET_INSTANCE@@PEAK@Z`
- size: `2327`
- prototype: `__int64 __fastcall(struct _SET_INSTANCE *, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180075de0`
- `0x1801334e8`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180024ea0`
- `0x180026850`
- `0x1800b4b44`
- `0x1800ea8fc`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800eb1b3`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800eb1b3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800eab45`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800eab45`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800eb1a1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800eb1a1`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800eaaba`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800eaaba`

## pseudocode

```c
__int64 __fastcall PlaiIncrementCollectors(struct _SET_INSTANCE *a1, unsigned int *a2)
{
  SAFEARRAY *v3; // r12
  __int64 v5; // rsi
  int v6; // eax
  int v7; // edi
  __int64 v8; // rbx
  int *v9; // r9
  int *v10; // rcx
  int v11; // eax
  __int64 v12; // rbx
  ULONG v13; // r8d
  SAFEARRAY *Vector; // rax
  __int64 v15; // rbx
  HRESULT v16; // eax
  __int64 v17; // rbx
  int v18; // eax
  __int64 v19; // rbx
  int v20; // eax
  __int64 v21; // rbx
  __int64 v22; // rbx
  unsigned int i; // eax
  __int64 v24; // rax
  unsigned int v25; // edx
  int v26; // eax
  int updated; // eax
  __int64 v28; // rbx
  int v30; // [rsp+70h] [rbp-90h] BYREF
  int v31; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v32; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v33; // [rsp+84h] [rbp-7Ch] BYREF
  void *ppvData; // [rsp+88h] [rbp-78h] BYREF
  __int64 v35; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v36; // [rsp+98h] [rbp-68h] BYREF
  struct tagVARIANT v37; // [rsp+A0h] [rbp-60h] BYREF
  struct tagVARIANT v38; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v39[64]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v40[64]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v41[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int16 v42[64]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v43[64]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 v44[64]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int16 v45[64]; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned __int16 v46[64]; // [rsp+460h] [rbp+360h] BYREF
  unsigned __int16 v47[64]; // [rsp+4E0h] [rbp+3E0h] BYREF
  unsigned __int16 v48[64]; // [rsp+560h] [rbp+460h] BYREF
  unsigned __int16 v49[64]; // [rsp+5E0h] [rbp+4E0h] BYREF
  unsigned __int16 v50[64]; // [rsp+660h] [rbp+560h] BYREF
  unsigned __int16 v51[64]; // [rsp+6E0h] [rbp+5E0h] BYREF

  v32 = 0;
  v33 = 0;
  ppvData = 0;
  v35 = 0;
  v3 = 0;
  v36 = 0;
  memset(&v37, 0, sizeof(v37));
  PlaiVariantInit(&v37);
  v5 = *((_QWORD *)a1 + 15);
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v5 + 56LL))(v5, &v36);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v36 + 56))(v36, &v32);
    v7 = v11;
    if ( v11 >= 0 )
    {
      v13 = v32 + 1;
      if ( v32 + 1 < v32 )
      {
        v7 = -2147024362;
        v30 = -2147024362;
        v32 = -1;
        v31 = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v51, 0x4000000000000800uLL);
          v28 = -1;
          do
            ++v28;
          while ( v51[v28] );
          v9 = &v30;
          v10 = &v31;
          goto LABEL_99;
        }
        goto LABEL_100;
      }
      ++v32;
      Vector = SafeArrayCreateVector(8u, 0, v13);
      v3 = Vector;
      if ( Vector )
      {
        v16 = SafeArrayAccessData(Vector, &ppvData);
        v7 = v16;
        if ( v16 >= 0 )
        {
          --v32;
          v18 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v5 + 168LL))(v5, ppvData);
          v7 = v18;
          if ( v18 >= 0 )
          {
            v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 152LL))(v5, *(_QWORD *)ppvData);
            v7 = v20;
            if ( v20 >= 0 )
            {
              v22 = -1;
              v37.vt = 19;
              for ( i = 0; ; i = v37.lVal + 1 )
              {
                v37.lVal = i;
                if ( i >= v32 )
                  break;
                if ( v35 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
                  v35 = 0;
                }
                v24 = *v36;
                v38 = v37;
                v7 = (*(__int64 (__fastcall **)(__int64 *, struct tagVARIANT *, __int64 *))(v24 + 64))(v36, &v38, &v35);
                if ( v7 < 0 )
                {
                  v31 = 0;
                  v30 = v7;
                  if ( (_DWORD)xmmword_180169738
                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                  {
                    PlaiWhoAmI(v47, 0x4000000000000800uLL);
                    do
                      ++v22;
                    while ( v47[v22] );
                    goto LABEL_14;
                  }
                  goto LABEL_100;
                }
                v7 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v35 + 248LL))(
                       v35,
                       0xFFFFFFFFLL,
                       (char *)ppvData + 8 * (unsigned int)(v37.lVal + 1));
                if ( v7 < 0 )
                {
                  v31 = 0;
                  v30 = v7;
                  if ( (_DWORD)xmmword_180169738
                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                  {
                    PlaiWhoAmI(v46, 0x4000000000000800uLL);
                    do
                      ++v22;
                    while ( v46[v22] );
                    goto LABEL_14;
                  }
                  goto LABEL_100;
                }
                v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v35 + 136LL))(
                       v35,
                       *((_QWORD *)ppvData + (unsigned int)(v37.lVal + 1)));
                if ( v7 < 0 )
                {
                  v31 = 0;
                  v30 = v7;
                  if ( (_DWORD)xmmword_180169738
                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                  {
                    PlaiWhoAmI(v45, 0x4000000000000800uLL);
                    do
                      ++v22;
                    while ( v45[v22] );
                    goto LABEL_14;
                  }
                  goto LABEL_100;
                }
              }
              v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 240LL))(v5, &v33);
              if ( v7 >= 0 )
              {
                v25 = v33;
                if ( a2 )
                  *a2 = v33;
                v33 = v25 + 1;
                v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 248LL))(v5);
                v7 = v26;
                if ( v26 >= 0 )
                {
                  updated = PlaiUpdateMetadata(a1, v3, v33);
                  v7 = updated;
                  if ( updated < 0 )
                  {
                    v31 = 0;
                    v30 = updated;
                    if ( (_DWORD)xmmword_180169738 )
                    {
                      if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                      {
                        PlaiWhoAmI(v50, 0x4000000000000800uLL);
                        do
                          ++v22;
                        while ( v50[v22] );
                        goto LABEL_14;
                      }
                    }
                  }
                }
                else
                {
                  v31 = 0;
                  v30 = v26;
                  if ( (_DWORD)xmmword_180169738
                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                  {
                    PlaiWhoAmI(v49, 0x4000000000000800uLL);
                    do
                      ++v22;
                    while ( v49[v22] );
                    goto LABEL_14;
                  }
                }
              }
              else
              {
                v31 = 0;
                v30 = v7;
                if ( (_DWORD)xmmword_180169738
                  && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                {
                  PlaiWhoAmI(v48, 0x4000000000000800uLL);
                  do
                    ++v22;
                  while ( v48[v22] );
                  goto LABEL_14;
                }
              }
              goto LABEL_100;
            }
            v31 = 0;
            v30 = v20;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_100;
            }
            PlaiWhoAmI(v44, 0x4000000000000800uLL);
            v21 = -1;
            do
              ++v21;
            while ( v44[v21] );
          }
          else
          {
            v31 = 0;
            v30 = v18;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_100;
            }
            PlaiWhoAmI(v43, 0x4000000000000800uLL);
            v19 = -1;
            do
              ++v19;
            while ( v43[v19] );
          }
        }
        else
        {
          v31 = 0;
          v30 = v16;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_100;
          }
          PlaiWhoAmI(v42, 0x4000000000000800uLL);
          v17 = -1;
          do
            ++v17;
          while ( v42[v17] );
        }
      }
      else
      {
        v7 = -2147024882;
        v30 = -2147024882;
        v31 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_100;
        }
        PlaiWhoAmI(v41, 0x4000000000000800uLL);
        v15 = -1;
        do
          ++v15;
        while ( v41[v15] );
      }
    }
    else
    {
      v31 = 0;
      v30 = v11;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_100;
      }
      PlaiWhoAmI(v40, 0x4000000000000800uLL);
      v12 = -1;
      do
        ++v12;
      while ( v40[v12] );
    }
LABEL_14:
    v9 = &v30;
    v10 = &v31;
LABEL_99:
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      v9,
      4,
      qword_180147320,
      1,
      v10,
      4,
      "PlaiIncrementCollectors",
      24);
    goto LABEL_100;
  }
  v30 = 0;
  v31 = v6;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v39, 0x4000000000000800uLL);
    v8 = -1;
    do
      ++v8;
    while ( v39[v8] );
    v9 = &v31;
    v10 = &v30;
    goto LABEL_99;
  }
LABEL_100:
  PlaiVariantClear(&v37);
  if ( ppvData )
  {
    SafeArrayUnaccessData(v3);
    ppvData = 0;
  }
  if ( v3 )
    SafeArrayDestroy(v3);
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v35 = 0;
  }
  if ( v36 )
    (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800ea8fc  mov     [rsp-8+arg_10], rbx
0x1800ea901  push    rbp
0x1800ea902  push    rsi
0x1800ea903  push    rdi
0x1800ea904  push    r12
0x1800ea906  push    r13
0x1800ea908  push    r14
0x1800ea90a  push    r15
0x1800ea90c  lea     rbp, [rsp-670h]
0x1800ea914  sub     rsp, 770h
0x1800ea91b  mov     rax, cs:__security_cookie
0x1800ea922  xor     rax, rsp
0x1800ea925  mov     [rbp+6A0h+var_40], rax
0x1800ea92c  xor     r14d, r14d
0x1800ea92f  mov     r13, rcx
0x1800ea932  xorps   xmm0, xmm0
0x1800ea935  mov     [rbp+6A0h+var_720], r14d
0x1800ea939  xor     eax, eax
0x1800ea93b  mov     [rbp+6A0h+var_71C], r14d
0x1800ea93f  lea     rcx, [rbp+6A0h+var_700]; struct tagVARIANT *
0x1800ea943  mov     [rbp+6A0h+ppvData], r14
0x1800ea947  mov     [rbp+6A0h+var_710], r14
0x1800ea94b  mov     r12d, r14d
0x1800ea94e  mov     [rbp+6A0h+var_708], r14
0x1800ea952  mov     r15, rdx
0x1800ea955  movups  xmmword ptr [rbp+6A0h+var_700], xmm0
0x1800ea959  mov     qword ptr [rbp+6A0h+var_700+10h], rax
0x1800ea95d  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800ea962  mov     rsi, [r13+78h]
0x1800ea966  lea     rdx, [rbp+6A0h+var_708]
0x1800ea96a  mov     rcx, rsi
0x1800ea96d  mov     rax, [rsi]
0x1800ea970  mov     rax, [rax+38h]
0x1800ea974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea979  mov     edi, eax
0x1800ea97b  test    eax, eax
0x1800ea97d  jns     short loc_1800EA9FD
0x1800ea97f  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800ea986  mov     [rsp+7A0h+var_730], r14d
0x1800ea98b  mov     [rsp+7A0h+var_728], eax
0x1800ea98f  jz      loc_1800EB18F
0x1800ea995  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ea99f  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ea9a6  jz      loc_1800EB18F
0x1800ea9ac  mov     rax, cs:qword_180169748
0x1800ea9b3  and     rax, rdx
0x1800ea9b6  cmp     cs:qword_180169748, rax
0x1800ea9bd  jnz     loc_1800EB18F
0x1800ea9c3  lea     rcx, [rbp+6A0h+var_6C0]; unsigned __int16 *
0x1800ea9c7  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ea9cc  lea     rax, [rbp+6A0h+var_6C0]
0x1800ea9d0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800ea9d4  inc     rbx
0x1800ea9d7  cmp     [rax+rbx*2], r14w
0x1800ea9dc  jnz     short loc_1800EA9D4
0x1800ea9de  lea     ecx, [rbx+rbx]
0x1800ea9e1  add     rcx, 2
0x1800ea9e5  lea     rax, [rbp+6A0h+var_6C0]
0x1800ea9e9  mov     [rsp+7A0h+var_740], rcx
0x1800ea9ee  lea     r9, [rsp+7A0h+var_728]
0x1800ea9f3  lea     rcx, [rsp+7A0h+var_730]
0x1800ea9f8  jmp     loc_1800EB130
0x1800ea9fd  mov     rcx, [rbp+6A0h+var_708]
0x1800eaa01  lea     rdx, [rbp+6A0h+var_720]
0x1800eaa05  mov     rax, [rcx]
0x1800eaa08  mov     rax, [rax+38h]
0x1800eaa0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eaa11  mov     edi, eax
0x1800eaa13  test    eax, eax
0x1800eaa15  jns     loc_1800EAA9F
0x1800eaa1b  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800eaa22  mov     [rsp+7A0h+var_728], r14d
0x1800eaa27  mov     [rsp+7A0h+var_730], eax
0x1800eaa2b  jz      loc_1800EB18F
0x1800eaa31  mov     rdx, 4000000000000800h; unsigned __int64
0x1800eaa3b  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800eaa42  jz      loc_1800EB18F
0x1800eaa48  mov     rax, cs:qword_180169748
0x1800eaa4f  and     rax, rdx
0x1800eaa52  cmp     cs:qword_180169748, rax
0x1800eaa59  jnz     loc_1800EB18F
0x1800eaa5f  lea     rcx, [rbp+6A0h+var_640]; unsigned __int16 *
0x1800eaa63  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800eaa68  lea     rax, [rbp+6A0h+var_640]
0x1800eaa6c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800eaa70  inc     rbx
0x1800eaa73  cmp     [rax+rbx*2], r14w
0x1800eaa78  jnz     short loc_1800EAA70
0x1800eaa7a  lea     rax, [rbp+6A0h+var_640]
0x1800eaa7e  mov     r14d, 1
0x1800eaa84  lea     ecx, [rbx+rbx]
0x1800eaa87  add     rcx, 2
0x1800eaa8b  lea     r9, [rsp+7A0h+var_730]
0x1800eaa90  mov     [rsp+7A0h+var_740], rcx
0x1800eaa95  lea     rcx, [rsp+7A0h+var_728]
0x1800eaa9a  jmp     loc_1800EB136
0x1800eaa9f  mov     eax, [rbp+6A0h+var_720]
0x1800eaaa2  lea     r8d, [rax+1]; cElements
0x1800eaaa6  cmp     r8d, eax
0x1800eaaa9  jb      loc_1800EB0A2
0x1800eaaaf  mov     ecx, 8; vt
0x1800eaab4  mov     [rbp+6A0h+var_720], r8d
0x1800eaab8  xor     edx, edx; lLbound
0x1800eaaba  call    cs:__imp_SafeArrayCreateVector
0x1800eaac0  mov     r12, rax
0x1800eaac3  test    rax, rax
0x1800eaac6  jnz     short loc_1800EAB3E
0x1800eaac8  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800eaacf  mov     edi, 8007000Eh
0x1800eaad4  mov     [rsp+7A0h+var_730], edi
0x1800eaad8  mov     [rsp+7A0h+var_728], r14d
0x1800eaadd  jz      loc_1800EB18F
0x1800eaae3  mov     rdx, 4000000000000800h; unsigned __int64
0x1800eaaed  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800eaaf4  jz      loc_1800EB18F
0x1800eaafa  mov     rax, cs:qword_180169748
0x1800eab01  and     rax, rdx
0x1800eab04  cmp     cs:qword_180169748, rax
0x1800eab0b  jnz     loc_1800EB18F
0x1800eab11  lea     rcx, [rbp+6A0h+var_5C0]; unsigned __int16 *
0x1800eab18  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800eab1d  lea     rax, [rbp+6A0h+var_5C0]
0x1800eab24  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800eab28  inc     rbx
0x1800eab2b  cmp     [rax+rbx*2], r14w
0x1800eab30  jnz     short loc_1800EAB28
0x1800eab32  lea     rax, [rbp+6A0h+var_5C0]
0x1800eab39  jmp     loc_1800EAA7E
0x1800eab3e  lea     rdx, [rbp+6A0h+ppvData]; ppvData
0x1800eab42  mov     rcx, r12; psa
0x1800eab45  call    cs:__imp_SafeArrayAccessData
0x1800eab4b  mov     edi, eax
0x1800eab4d  test    eax, eax
0x1800eab4f  jns     short loc_1800EABC2
0x1800eab51  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800eab58  mov     [rsp+7A0h+var_728], r14d
0x1800eab5d  mov     [rsp+7A0h+var_730], eax
0x1800eab61  jz      loc_1800EB18F
0x1800eab67  mov     rdx, 4000000000000800h; unsigned __int64
0x1800eab71  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800eab78  jz      loc_1800EB18F
0x1800eab7e  mov     rax, cs:qword_180169748
0x1800eab85  and     rax, rdx
0x1800eab88  cmp     cs:qword_180169748, rax
0x1800eab8f  jnz     loc_1800EB18F
0x1800eab95  lea     rcx, [rbp+6A0h+var_540]; unsigned __int16 *
0x1800eab9c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800eaba1  lea     rax, [rbp+6A0h+var_540]
0x1800eaba8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800eabac  inc     rbx
0x1800eabaf  cmp     [rax+rbx*2], r14w
0x1800eabb4  jnz     short loc_1800EABAC
0x1800eabb6  lea     rax, [rbp+6A0h+var_540]
0x1800eabbd  jmp     loc_1800EAA7E
0x1800eabc2  dec     [rbp+6A0h+var_720]
0x1800eabc5  mov     rcx, rsi
0x1800eabc8  mov     rax, [rsi]
0x1800eabcb  mov     rdx, [rbp+6A0h+ppvData]
0x1800eabcf  mov     rax, [rax+0A8h]
0x1800eabd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eabdb  mov     edi, eax
0x1800eabdd  test    eax, eax
0x1800eabdf  jns     short loc_1800EAC52
0x1800eabe1  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800eabe8  mov     [rsp+7A0h+var_728], r14d
0x1800eabed  mov     [rsp+7A0h+var_730], eax
0x1800eabf1  jz      loc_1800EB18F
0x1800eabf7  mov     rdx, 4000000000000800h; unsigned __int64
0x1800eac01  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800eac08  jz      loc_1800EB18F
0x1800eac0e  mov     rax, cs:qword_180169748
0x1800eac15  and     rax, rdx
0x1800eac18  cmp     cs:qword_180169748, rax
0x1800eac1f  jnz     loc_1800EB18F
0x1800eac25  lea     rcx, [rbp+6A0h+var_4C0]; unsigned __int16 *
0x1800eac2c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800eac31  lea     rax, [rbp+6A0h+var_4C0]
0x1800eac38  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800eac3c  inc     rbx
0x1800eac3f  cmp     [rax+rbx*2], r14w
0x1800eac44  jnz     short loc_1800EAC3C
0x1800eac46  lea     rax, [rbp+6A0h+var_4C0]
0x1800eac4d  jmp     loc_1800EAA7E
0x1800eac52  mov     rax, [rsi]
0x1800eac55  mov     rcx, rsi
0x1800eac58  mov     rdx, [rbp+6A0h+ppvData]
0x1800eac5c  mov     rax, [rax+98h]
0x1800eac63  mov     rdx, [rdx]
0x1800eac66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eac6b  mov     edi, eax
0x1800eac6d  test    eax, eax
0x1800eac6f  jns     short loc_1800EACE2
0x1800eac71  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800eac78  mov     [rsp+7A0h+var_728], r14d
0x1800eac7d  mov     [rsp+7A0h+var_730], eax
0x1800eac81  jz      loc_1800EB18F
0x1800eac87  mov     rdx, 4000000000000800h; unsigned __int64
0x1800eac91  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800eac98  jz      loc_1800EB18F
0x1800eac9e  mov     rax, cs:qword_180169748
0x1800eaca5  and     rax, rdx
0x1800eaca8  cmp     cs:qword_180169748, rax
0x1800eacaf  jnz     loc_1800EB18F
0x1800eacb5  lea     rcx, [rbp+6A0h+var_440]; unsigned __int16 *
0x1800eacbc  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800eacc1  lea     rax, [rbp+6A0h+var_440]
0x1800eacc8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800eaccc  inc     rbx
0x1800eaccf  cmp     [rax+rbx*2], r14w
0x1800eacd4  jnz     short loc_1800EACCC
0x1800eacd6  lea     rax, [rbp+6A0h+var_440]
0x1800eacdd  jmp     loc_1800EAA7E
0x1800eace2  mov     eax, 13h
0x1800eace7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800eaceb  mov     word ptr [rbp+6A0h+var_700], ax
0x1800eacef  mov     eax, r14d
0x1800eacf2  lea     r14d, [rbx+2]
0x1800eacf6  mov     dword ptr [rbp+6A0h+var_700+8], eax
0x1800eacf9  cmp     eax, [rbp+6A0h+var_720]
0x1800eacfc  jnb     loc_1800EAF00
0x1800ead02  mov     rcx, [rbp+6A0h+var_710]
0x1800ead06  xor     edi, edi
0x1800ead08  test    rcx, rcx
0x1800ead0b  jz      short loc_1800EAD1D
0x1800ead0d  mov     rax, [rcx]
0x1800ead10  mov     rax, [rax+10h]
0x1800ead14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ead19  mov     [rbp+6A0h+var_710], rdi
0x1800ead1d  mov     rcx, [rbp+6A0h+var_708]
0x1800ead21  lea     r8, [rbp+6A0h+var_710]
0x1800ead25  movups  xmm0, xmmword ptr [rbp+6A0h+var_700]
0x1800ead29  lea     rdx, [rbp+6A0h+var_6E0]
0x1800ead2d  movsd   xmm1, qword ptr [rbp+6A0h+var_700+10h]
0x1800ead32  mov     rax, [rcx]
0x1800ead35  movaps  [rbp+6A0h+var_6E0], xmm0
0x1800ead39  movsd   [rbp+6A0h+var_6D0], xmm1
0x1800ead3e  mov     rax, [rax+40h]
0x1800ead42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ead47  mov     edi, eax
0x1800ead49  xor     eax, eax
0x1800ead4b  test    edi, edi
0x1800ead4d  js      loc_1800EAE94
0x1800ead53  mov     ecx, dword ptr [rbp+6A0h+var_700+8]
0x1800ead56  mov     edx, ebx
0x1800ead58  mov     r10, [rbp+6A0h+var_710]
0x1800ead5c  inc     ecx
0x1800ead5e  mov     rax, [rbp+6A0h+ppvData]
0x1800ead62  mov     r9, [r10]
0x1800ead65  lea     r8, [rax+rcx*8]
0x1800ead69  mov     rcx, r10
0x1800ead6c  mov     rax, [r9+0F8h]
0x1800ead73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ead78  mov     edi, eax
0x1800ead7a  xor     eax, eax
0x1800ead7c  test    edi, edi
0x1800ead7e  js      loc_1800EAE28
0x1800ead84  mov     r9, [rbp+6A0h+var_710]
0x1800ead88  mov     r8d, dword ptr [rbp+6A0h+var_700+8]
0x1800ead8c  mov     rdx, [rbp+6A0h+ppvData]
0x1800ead90  inc     r8d
0x1800ead93  mov     rcx, [r9]
0x1800ead96  mov     rdx, [rdx+r8*8]
0x1800ead9a  mov     rax, [rcx+88h]
0x1800eada1  mov     rcx, r9
0x1800eada4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eada9  mov     edi, eax
0x1800eadab  xor     eax, eax
0x1800eadad  test    edi, edi
0x1800eadaf  js      short loc_1800EADBC
0x1800eadb1  mov     eax, dword ptr [rbp+6A0h+var_700+8]
0x1800eadb4  add     eax, r14d
0x1800eadb7  jmp     loc_1800EACF6
0x1800eadbc  cmp     dword ptr cs:xmmword_180169738, eax
0x1800eadc2  mov     [rsp+7A0h+var_728], eax
0x1800eadc6  mov     [rsp+7A0h+var_730], edi
0x1800eadca  jz      loc_1800EB18C
0x1800eadd0  mov     rdx, 4000000000000800h; unsigned __int64
0x1800eadda  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800eade1  jz      loc_1800EB18C
0x1800eade7  mov     rax, cs:qword_180169748
0x1800eadee  and     rax, rdx
0x1800eadf1  cmp     cs:qword_180169748, rax
0x1800eadf8  jnz     loc_1800EB18C
0x1800eadfe  lea     rcx, [rbp+6A0h+var_3C0]; unsigned __int16 *
0x1800eae05  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800eae0a  lea     rcx, [rbp+6A0h+var_3C0]
0x1800eae11  xor     eax, eax
0x1800eae13  inc     rbx
0x1800eae16  cmp     [rcx+rbx*2], ax
0x1800eae1a  jnz     short loc_1800EAE13
0x1800eae1c  lea     rax, [rbp+6A0h+var_3C0]
0x1800eae23  jmp     loc_1800EAA84
0x1800eae28  cmp     dword ptr cs:xmmword_180169738, eax
0x1800eae2e  mov     [rsp+7A0h+var_728], eax
0x1800eae32  mov     [rsp+7A0h+var_730], edi
0x1800eae36  jz      loc_1800EB18C
0x1800eae3c  mov     rdx, 4000000000000800h; unsigned __int64
0x1800eae46  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800eae4d  jz      loc_1800EB18C
0x1800eae53  mov     rax, cs:qword_180169748
  ... truncated ...
```
