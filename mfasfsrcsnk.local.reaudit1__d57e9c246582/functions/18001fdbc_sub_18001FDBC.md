# sub_18001FDBC

- ea: `0x18001fdbc`
- end: `0x18002050f`
- name: `sub_18001FDBC`
- size: `1875`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180004560`

## callees

- `0x1800018b0`
- `0x18001fdbc`
- `0x1800402b4`
- `0x1800402d8`
- `0x180051e44`
- `0x1800839f8`
- `0x180083a48`
- `0x1801468f0`
- `0x180146950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800203f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002041d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800203f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002041d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fe3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020496`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fe3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020496`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fe21`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020407`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fe21`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800204e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800204e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001fe98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ff92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180020029`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800201dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180020349`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180020439`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001fe98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ff92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180020029`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800201dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180020349`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180020439`

## string_xrefs

- `0x18001fdf1`: `CMFPropVariant::Compare`
- `0x18001fe51`: `CMFPropVariant::Compare`

## pseudocode

```c
__int64 __fastcall sub_18001FDBC(const void **a1, const void **a2, int *a3, __int64 a4)
{
  __int64 v7; // rbx
  __int64 v8; // rbp
  DWORD LastError; // r15d
  LPVOID Value; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 (__fastcall ***v14)(); // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned int v17; // ebp
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  int v27; // edx
  int v28; // edx
  int v29; // edx
  double v30; // xmm0_8
  double v31; // xmm1_8
  bool v32; // zf
  float v33; // xmm0_4
  float v34; // xmm1_4
  int v35; // eax
  __int16 v36; // cx
  bool v37; // zf
  bool v38; // sf
  bool v39; // of
  bool v40; // cc
  _BYTE *v41; // rcx
  int v42; // edx
  int v43; // edx
  int v44; // edx
  bool v45; // cf
  int v46; // edx
  int v47; // edx
  int v48; // edx
  __int64 v49; // rax
  unsigned int v50; // eax
  bool v51; // cc
  unsigned __int16 v52; // ax
  unsigned __int8 v53; // al
  char v54; // cl
  int v55; // eax
  unsigned __int64 v56; // rax
  int v57; // edx
  int v58; // edx
  int v59; // edx
  int v60; // ecx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rbx
  __int64 v65; // rdi
  DWORD v66; // esi
  LPVOID v67; // rax
  __int64 v68; // rdx
  __int64 (__fastcall ***v69)(); // rcx
  __int64 v70; // rax
  __int64 v71; // rax
  int v72; // eax
  int v73; // eax

  if ( !qword_180171350 )
    sub_1800839F8(a1, a2, a3, a4);
  v7 = qword_180171350;
  if ( *(_BYTE *)(qword_180171350 + 8) )
  {
    v8 = qword_180171350 + 208;
    LastError = GetLastError();
    Value = TlsGetValue(*(_DWORD *)(v7 + 12));
    if ( Value )
    {
      v8 = (__int64)Value;
    }
    else if ( !GetLastError() )
    {
      v14 = (__int64 (__fastcall ***)())qword_180171350;
      if ( !qword_180171350 )
      {
        v15 = MFGetCallStackTracingWeakReference(0, v13);
        qword_180171350 = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 (__fastcall ***)())qword_180171350;
        }
        else
        {
          v14 = &off_1801703B0;
          qword_180171350 = (__int64)&off_1801703B0;
        }
      }
      v16 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)()))**v14)(v14);
      if ( v16 )
        v8 = v16;
    }
    SetLastError(LastError);
    v11 = *(unsigned int *)(v8 + 1988);
    if ( (unsigned int)v11 < *(_DWORD *)(v8 + 1992) )
    {
      v12 = 2 * v11;
      *(_QWORD *)(v8 + 8 * v12) = "CMFPropVariant::Compare";
      *(_DWORD *)(v8 + 8 * v12 + 8) = 1414;
    }
    ++*(_DWORD *)(v8 + 1988);
  }
  if ( a1 == a2 )
  {
    v17 = -2147467261;
    if ( !qword_180171350 )
      sub_1800839F8(a1, a2, a3, a4);
    if ( *(_BYTE *)(qword_180171350 + 8) )
    {
      v18 = sub_1800018B0(qword_180171350);
      if ( *(_DWORD *)(v18 + 1996) != -2147467261 )
        sub_180083A48(v18, "CMFPropVariant::Compare", 1423, 2147500035LL);
    }
    if ( byte_1801712C8 )
    {
      v19 = 86;
LABEL_120:
      sub_180051E44(*((_QWORD *)RequestContext + 2), v19, qword_18015C208, a1, v17);
      goto LABEL_121;
    }
    goto LABEL_121;
  }
  *a3 = 0;
  v20 = *(unsigned __int16 *)a1;
  v21 = (unsigned __int16)v20;
  LOWORD(v21) = v20 & 0x1000;
  if ( (v20 & 0x1000) == 0 )
  {
    if ( *(_WORD *)a2 != (_WORD)v20 )
    {
      v17 = -1072875801;
      if ( !qword_180171350 )
      {
        v24 = MFGetCallStackTracingWeakReference(v21, v20);
        qword_180171350 = v24;
        if ( !v24 || !(*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          qword_180171350 = (__int64)&off_1801703B0;
      }
      if ( *(_BYTE *)(qword_180171350 + 8) )
      {
        v25 = sub_1800018B0(qword_180171350);
        if ( *(_DWORD *)(v25 + 1996) != -1072875801 )
          sub_180083A48(v25, "CMFPropVariant::Compare", 1444, 3222091495LL);
      }
      if ( byte_1801712C8 )
      {
        v19 = 88;
        goto LABEL_120;
      }
      goto LABEL_121;
    }
    v26 = v20 & 0xFFF;
    if ( (unsigned int)v26 > 0x48 )
      goto LABEL_79;
    v17 = 0;
    if ( (_DWORD)v26 == 72 )
    {
      v45 = memcmp(a2[1], a1[1], 0x10u) != 0;
      goto LABEL_105;
    }
    if ( (unsigned int)v26 <= 0xD )
    {
      if ( (_DWORD)v26 == 13 )
        goto LABEL_71;
      if ( (unsigned int)v26 <= 6 )
      {
        if ( (_DWORD)v26 != 6 )
        {
          if ( !(_DWORD)v26 )
            goto LABEL_121;
          v27 = v26 - 1;
          if ( !v27 )
            goto LABEL_121;
          v28 = v27 - 1;
          if ( !v28 )
          {
            v36 = *((_WORD *)a2 + 4);
            v39 = __OFSUB__(v36, *((_WORD *)a1 + 4));
            v37 = v36 == *((_WORD *)a1 + 4);
            v38 = (__int16)(v36 - *((_WORD *)a1 + 4)) < 0;
            v40 = v36 < *((_WORD *)a1 + 4);
            goto LABEL_89;
          }
          v29 = v28 - 1;
          if ( v29 )
          {
            v26 = (unsigned int)(v29 - 1);
            if ( !(_DWORD)v26 )
            {
              v33 = *((float *)a1 + 2);
              v34 = *((float *)a2 + 2);
              if ( v33 <= v34 )
              {
                v32 = v34 == v33;
                goto LABEL_62;
              }
LABEL_90:
              v55 = -1;
LABEL_102:
              *a3 = v55;
              goto LABEL_121;
            }
            if ( (_DWORD)v26 == 1 )
            {
LABEL_58:
              v30 = *((double *)a1 + 1);
              v31 = *((double *)a2 + 1);
              if ( v30 <= v31 )
              {
                v32 = v31 == v30;
LABEL_62:
                v35 = v32;
LABEL_92:
                v55 = v35 - 1;
                goto LABEL_102;
              }
              goto LABEL_90;
            }
LABEL_79:
            v17 = -1072875800;
            if ( !qword_180171350 )
            {
              v49 = MFGetCallStackTracingWeakReference(v21, v26);
              qword_180171350 = v49;
              v21 = v49;
              if ( !v49 || !(*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
                qword_180171350 = (__int64)&off_1801703B0;
            }
            if ( *(_BYTE *)(qword_180171350 + 8) )
            {
              v61 = sub_1800018B0(qword_180171350);
              if ( *(_DWORD *)(v61 + 1996) != -1072875800 )
                sub_180083A48(v61, "CMFPropVariant::Compare", 1483, 3222091496LL);
            }
            if ( byte_1801712C8 )
              sub_180051E44(*((_QWORD *)RequestContext + 2), 89, qword_18015C208, a1, -1072875800);
            if ( !qword_180171350 )
            {
              v62 = MFGetCallStackTracingWeakReference(v21, v26);
              qword_180171350 = v62;
              if ( !v62 || !(*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
                qword_180171350 = (__int64)&off_1801703B0;
            }
            if ( *(_BYTE *)(qword_180171350 + 8) )
            {
              v63 = sub_1800018B0(qword_180171350);
              if ( *(_DWORD *)(v63 + 1996) != -1072875800 )
                sub_180083A48(v63, "CMFPropVariant::Compare", 1486, 3222091496LL);
            }
            if ( byte_1801712C8 )
            {
              v19 = 90;
              goto LABEL_120;
            }
            goto LABEL_121;
          }
          goto LABEL_103;
        }
LABEL_64:
        v41 = a2[1];
        v39 = __OFSUB__(v41, a1[1]);
        v37 = v41 == a1[1];
        v38 = v41 - (_BYTE *)a1[1] < 0;
        v40 = (__int64)v41 < (__int64)a1[1];
        goto LABEL_89;
      }
      v42 = v26 - 7;
      if ( !v42 )
        goto LABEL_58;
      v43 = v42 - 1;
      if ( v43 )
      {
        v44 = v43 - 1;
        if ( v44 )
        {
          v26 = (unsigned int)(v44 - 1);
          if ( (_DWORD)v26 )
          {
            if ( (_DWORD)v26 != 1 )
              goto LABEL_79;
            v45 = *((_WORD *)a1 + 4) != *((_WORD *)a2 + 4);
LABEL_105:
            v55 = -v45;
            goto LABEL_102;
          }
LABEL_103:
          v60 = *((_DWORD *)a2 + 2);
          v39 = __OFSUB__(v60, *((_DWORD *)a1 + 2));
          v37 = v60 == *((_DWORD *)a1 + 2);
          v38 = v60 - *((_DWORD *)a1 + 2) < 0;
          v40 = v60 < *((_DWORD *)a1 + 2);
LABEL_89:
          if ( !v40 )
          {
            v35 = v38 ^ v39 | v37;
            goto LABEL_92;
          }
          goto LABEL_90;
        }
LABEL_71:
        v45 = a1[1] != a2[1];
        goto LABEL_105;
      }
LABEL_100:
      v55 = o__wcsicmp(a2[1], a1[1]);
      goto LABEL_102;
    }
    if ( (unsigned int)v26 <= 0x15 )
    {
      if ( (_DWORD)v26 == 21 )
      {
        v56 = (unsigned __int64)a2[1];
        v45 = (unsigned __int64)a1[1] < v56;
        v51 = (unsigned __int64)a1[1] <= v56;
      }
      else
      {
        v46 = v26 - 16;
        if ( !v46 )
        {
          v54 = *((_BYTE *)a2 + 8);
          v39 = __OFSUB__(v54, *((_BYTE *)a1 + 8));
          v37 = v54 == *((_BYTE *)a1 + 8);
          v38 = (char)(v54 - *((_BYTE *)a1 + 8)) < 0;
          v40 = v54 < *((_BYTE *)a1 + 8);
          goto LABEL_89;
        }
        v47 = v46 - 1;
        if ( v47 )
        {
          v48 = v47 - 1;
          if ( v48 )
          {
            v26 = (unsigned int)(v48 - 1);
            if ( (_DWORD)v26 )
            {
              if ( (_DWORD)v26 != 1 )
                goto LABEL_79;
              goto LABEL_64;
            }
LABEL_83:
            v50 = *((_DWORD *)a2 + 2);
            v45 = *((_DWORD *)a1 + 2) < v50;
            v51 = *((_DWORD *)a1 + 2) <= v50;
            goto LABEL_86;
          }
          v52 = *((_WORD *)a2 + 4);
          v45 = *((_WORD *)a1 + 4) < v52;
          v51 = *((_WORD *)a1 + 4) <= v52;
        }
        else
        {
          v53 = *((_BYTE *)a2 + 8);
          v45 = *((_BYTE *)a1 + 8) < v53;
          v51 = *((_BYTE *)a1 + 8) <= v53;
        }
      }
LABEL_86:
      if ( !v51 )
        goto LABEL_90;
      goto LABEL_105;
    }
    v57 = v26 - 22;
    if ( !v57 )
      goto LABEL_103;
    v58 = v57 - 1;
    if ( v58 )
    {
      v59 = v58 - 7;
      if ( !v59 )
      {
        v55 = o__stricmp(a2[1], a1[1]);
        goto LABEL_102;
      }
      v26 = (unsigned int)(v59 - 1);
      if ( (_DWORD)v26 )
      {
        if ( (_DWORD)v26 == 33 )
        {
          v55 = memcmp(a2 + 1, a1 + 1, 8u);
          goto LABEL_102;
        }
        goto LABEL_79;
      }
      goto LABEL_100;
    }
    goto LABEL_83;
  }
  v17 = -1072875797;
  if ( !qword_180171350 )
  {
    v22 = MFGetCallStackTracingWeakReference(v21, v20);
    qword_180171350 = v22;
    if ( !v22 || !(*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
      qword_180171350 = (__int64)&off_1801703B0;
  }
  if ( *(_BYTE *)(qword_180171350 + 8) )
  {
    v23 = sub_1800018B0(qword_180171350);
    if ( *(_DWORD *)(v23 + 1996) != -1072875797 )
      sub_180083A48(v23, "CMFPropVariant::Compare", 1436, 3222091499LL);
  }
  if ( byte_1801712C8 )
  {
    v19 = 87;
    goto LABEL_120;
  }
LABEL_121:
  v64 = qword_180171350;
  if ( *(_BYTE *)(qword_180171350 + 8) )
  {
    v65 = qword_180171350 + 208;
    v66 = GetLastError();
    v67 = TlsGetValue(*(_DWORD *)(v64 + 12));
    if ( v67 )
    {
      v65 = (__int64)v67;
    }
    else if ( !GetLastError() )
    {
      v69 = (__int64 (__fastcall ***)())qword_180171350;
      if ( !qword_180171350 )
      {
        v70 = MFGetCallStackTracingWeakReference(0, v68);
        qword_180171350 = v70;
        if ( v70 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
        {
          v69 = (__int64 (__fastcall ***)())qword_180171350;
        }
        else
        {
          v69 = &off_1801703B0;
          qword_180171350 = (__int64)&off_1801703B0;
        }
      }
      v71 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)()))**v69)(v69);
      if ( v71 )
        v65 = v71;
    }
    SetLastError(v66);
    v72 = *(_DWORD *)(v65 + 1988);
    if ( v72 )
    {
      v73 = v72 - 1;
      *(_DWORD *)(v65 + 1988) = v73;
      if ( !v73 )
      {
        *(_DWORD *)(v65 + 1988) = 0;
        *(_QWORD *)(v65 + 2016) = 0;
        *(_DWORD *)(v65 + 1996) = 0;
        *(GUID *)(v65 + 2000) = Buf1;
        *(_DWORD *)(v65 + 2024) = 0;
        *(_DWORD *)(v65 + 1984) = GetCurrentThreadId();
      }
    }
  }
  return v17;
}

```

## disassembly

```asm
0x18001fdbc  mov     [rsp+arg_18], rbx
0x18001fdc1  push    rbp
0x18001fdc2  push    rsi
0x18001fdc3  push    rdi
0x18001fdc4  push    r12
0x18001fdc6  push    r13
0x18001fdc8  push    r14
0x18001fdca  push    r15
0x18001fdcc  sub     rsp, 30h
0x18001fdd0  xor     r12d, r12d
0x18001fdd3  mov     r14, r8
0x18001fdd6  cmp     cs:qword_180171350, r12
0x18001fddd  mov     rdi, rdx
0x18001fde0  mov     rsi, rcx
0x18001fde3  jnz     short loc_18001FDEA
0x18001fde5  call    sub_1800839F8
0x18001fdea  mov     rbx, cs:qword_180171350
0x18001fdf1  lea     r15, aCmfpropvariant_9; "CMFPropVariant::Compare"
0x18001fdf8  mov     r13d, 1
0x18001fdfe  cmp     [rbx+8], r12b
0x18001fe02  jz      loc_18001FF02
0x18001fe08  lea     rbp, [rbx+0D0h]
0x18001fe0f  call    cs:GetLastError
0x18001fe16  nop     dword ptr [rax+rax+00h]
0x18001fe1b  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18001fe1e  mov     r15d, eax
0x18001fe21  call    cs:TlsGetValue
0x18001fe28  nop     dword ptr [rax+rax+00h]
0x18001fe2d  test    rax, rax
0x18001fe30  jz      short loc_18001FE7C
0x18001fe32  mov     rbp, rax
0x18001fe35  lea     rbx, off_1801703B0
0x18001fe3c  mov     ecx, r15d; dwErrCode
0x18001fe3f  call    cs:SetLastError
0x18001fe46  nop     dword ptr [rax+rax+00h]
0x18001fe4b  mov     eax, [rbp+7C4h]
0x18001fe51  lea     r15, aCmfpropvariant_9; "CMFPropVariant::Compare"
0x18001fe58  cmp     eax, [rbp+7C8h]
0x18001fe5e  jnb     short loc_18001FE70
0x18001fe60  add     rax, rax
0x18001fe63  mov     [rbp+rax*8+0], r15
0x18001fe68  mov     dword ptr [rbp+rax*8+8], 586h
0x18001fe70  add     [rbp+7C4h], r13d
0x18001fe77  jmp     loc_18001FF09
0x18001fe7c  call    cs:GetLastError
0x18001fe83  nop     dword ptr [rax+rax+00h]
0x18001fe88  test    eax, eax
0x18001fe8a  jnz     short loc_18001FE35
0x18001fe8c  mov     rcx, cs:qword_180171350
0x18001fe93  test    rcx, rcx
0x18001fe96  jnz     short loc_18001FED0
0x18001fe98  call    cs:MFGetCallStackTracingWeakReference
0x18001fe9f  nop     dword ptr [rax+rax+00h]
0x18001fea4  mov     cs:qword_180171350, rax
0x18001feab  mov     rcx, rax
0x18001feae  test    rax, rax
0x18001feb1  jz      short loc_18001FEEF
0x18001feb3  mov     rax, [rax]
0x18001feb6  mov     edx, 7F0h
0x18001febb  mov     rax, [rax+8]
0x18001febf  call    cs:__guard_dispatch_icall_fptr
0x18001fec5  test    eax, eax
0x18001fec7  jz      short loc_18001FEEF
0x18001fec9  mov     rcx, cs:qword_180171350
0x18001fed0  lea     rbx, off_1801703B0
0x18001fed7  mov     rax, [rcx]
0x18001feda  mov     rax, [rax]
0x18001fedd  call    cs:__guard_dispatch_icall_fptr
0x18001fee3  test    rax, rax
0x18001fee6  cmovnz  rbp, rax
0x18001feea  jmp     loc_18001FE3C
0x18001feef  lea     rbx, off_1801703B0
0x18001fef6  mov     rcx, rbx
0x18001fef9  mov     cs:qword_180171350, rbx
0x18001ff00  jmp     short loc_18001FED7
0x18001ff02  lea     rbx, off_1801703B0
0x18001ff09  cmp     rsi, rdi
0x18001ff0c  jnz     short loc_18001FF69
0x18001ff0e  cmp     cs:qword_180171350, r12
0x18001ff15  mov     ebp, 80004003h
0x18001ff1a  jnz     short loc_18001FF21
0x18001ff1c  call    sub_1800839F8
0x18001ff21  mov     rbx, cs:qword_180171350
0x18001ff28  cmp     [rbx+8], r12b
0x18001ff2c  jz      short loc_18001FF52
0x18001ff2e  mov     rcx, rbx
0x18001ff31  call    sub_1800018B0
0x18001ff36  cmp     [rax+7CCh], ebp
0x18001ff3c  jz      short loc_18001FF52
0x18001ff3e  mov     r9d, ebp
0x18001ff41  mov     r8d, 58Fh
0x18001ff47  mov     rdx, r15
0x18001ff4a  mov     rcx, rax
0x18001ff4d  call    sub_180083A48
0x18001ff52  cmp     cs:byte_1801712C8, r13b
0x18001ff59  jb      loc_1800203DE
0x18001ff5f  mov     edx, 56h ; 'V'
0x18001ff64  jmp     loc_1800203C0
0x18001ff69  mov     [r14], r12d
0x18001ff6c  mov     eax, 1000h
0x18001ff71  movzx   edx, word ptr [rsi]
0x18001ff74  movzx   ecx, dx
0x18001ff77  and     cx, ax
0x18001ff7a  cmp     r12w, cx
0x18001ff7e  jz      loc_180020012
0x18001ff84  cmp     cs:qword_180171350, r12
0x18001ff8b  mov     ebp, 0C00D36EBh
0x18001ff90  jnz     short loc_18001FFCA
0x18001ff92  call    cs:MFGetCallStackTracingWeakReference
0x18001ff99  nop     dword ptr [rax+rax+00h]
0x18001ff9e  mov     cs:qword_180171350, rax
0x18001ffa5  mov     rcx, rax
0x18001ffa8  test    rax, rax
0x18001ffab  jz      short loc_18001FFC3
0x18001ffad  mov     rax, [rax]
0x18001ffb0  mov     edx, 7F0h
0x18001ffb5  mov     rax, [rax+8]
0x18001ffb9  call    cs:__guard_dispatch_icall_fptr
0x18001ffbf  test    eax, eax
0x18001ffc1  jnz     short loc_18001FFCA
0x18001ffc3  mov     cs:qword_180171350, rbx
0x18001ffca  mov     rbx, cs:qword_180171350
0x18001ffd1  cmp     [rbx+8], r12b
0x18001ffd5  jz      short loc_18001FFFB
0x18001ffd7  mov     rcx, rbx
0x18001ffda  call    sub_1800018B0
0x18001ffdf  cmp     [rax+7CCh], ebp
0x18001ffe5  jz      short loc_18001FFFB
0x18001ffe7  mov     r9d, ebp
0x18001ffea  mov     r8d, 59Ch
0x18001fff0  mov     rdx, r15
0x18001fff3  mov     rcx, rax
0x18001fff6  call    sub_180083A48
0x18001fffb  cmp     cs:byte_1801712C8, r13b
0x180020002  jb      loc_1800203DE
0x180020008  mov     edx, 57h ; 'W'
0x18002000d  jmp     loc_1800203C0
0x180020012  cmp     [rdi], dx
0x180020015  jz      loc_1800200A9
0x18002001b  cmp     cs:qword_180171350, r12
0x180020022  mov     ebp, 0C00D36E7h
0x180020027  jnz     short loc_180020061
0x180020029  call    cs:MFGetCallStackTracingWeakReference
0x180020030  nop     dword ptr [rax+rax+00h]
0x180020035  mov     cs:qword_180171350, rax
0x18002003c  mov     rcx, rax
0x18002003f  test    rax, rax
0x180020042  jz      short loc_18002005A
0x180020044  mov     rax, [rax]
0x180020047  mov     edx, 7F0h
0x18002004c  mov     rax, [rax+8]
0x180020050  call    cs:__guard_dispatch_icall_fptr
0x180020056  test    eax, eax
0x180020058  jnz     short loc_180020061
0x18002005a  mov     cs:qword_180171350, rbx
0x180020061  mov     rbx, cs:qword_180171350
0x180020068  cmp     [rbx+8], r12b
0x18002006c  jz      short loc_180020092
0x18002006e  mov     rcx, rbx
0x180020071  call    sub_1800018B0
0x180020076  cmp     [rax+7CCh], ebp
0x18002007c  jz      short loc_180020092
0x18002007e  mov     r9d, ebp
0x180020081  mov     r8d, 5A4h
0x180020087  mov     rdx, r15
0x18002008a  mov     rcx, rax
0x18002008d  call    sub_180083A48
0x180020092  cmp     cs:byte_1801712C8, r13b
0x180020099  jb      loc_1800203DE
0x18002009f  mov     edx, 58h ; 'X'
0x1800200a4  jmp     loc_1800203C0
0x1800200a9  and     edx, 0FFFh
0x1800200af  cmp     edx, 48h ; 'H'
0x1800200b2  ja      loc_1800201CA
0x1800200b8  mov     ebp, r12d
0x1800200bb  jz      loc_1800202C3
0x1800200c1  cmp     edx, 0Dh
0x1800200c4  ja      loc_18002019E
0x1800200ca  jz      loc_18002018E
0x1800200d0  cmp     edx, 6
0x1800200d3  ja      loc_18002015D
0x1800200d9  jz      short loc_180020150
0x1800200db  test    edx, edx
0x1800200dd  jz      loc_1800203DE
0x1800200e3  sub     edx, r13d
0x1800200e6  jz      loc_1800203DE
0x1800200ec  sub     edx, r13d
0x1800200ef  jz      short loc_180020143
0x1800200f1  sub     edx, r13d
0x1800200f4  jz      loc_1800202BB
0x1800200fa  sub     edx, r13d
0x1800200fd  jz      short loc_180020122
0x1800200ff  cmp     edx, r13d
0x180020102  jnz     loc_1800201CA
0x180020108  movsd   xmm0, qword ptr [rsi+8]
0x18002010d  movsd   xmm1, qword ptr [rdi+8]
0x180020112  comisd  xmm0, xmm1
0x180020116  ja      loc_18002024B
0x18002011c  comisd  xmm1, xmm0
0x180020120  jmp     short loc_180020138
0x180020122  movss   xmm0, dword ptr [rsi+8]
0x180020127  movss   xmm1, dword ptr [rdi+8]
0x18002012c  comiss  xmm0, xmm1
0x18002012f  ja      loc_18002024B
0x180020135  comiss  xmm1, xmm0
0x180020138  mov     eax, r12d
0x18002013b  setbe   al
0x18002013e  jmp     loc_180020256
0x180020143  movzx   ecx, word ptr [rdi+8]
0x180020147  cmp     cx, [rsi+8]
0x18002014b  jmp     loc_180020249
0x180020150  mov     rcx, [rdi+8]
0x180020154  cmp     rcx, [rsi+8]
0x180020158  jmp     loc_180020249
0x18002015d  sub     edx, 7
0x180020160  jz      short loc_180020108
0x180020162  sub     edx, r13d
0x180020165  jz      loc_180020297
0x18002016b  sub     edx, r13d
0x18002016e  jz      short loc_18002018E
0x180020170  sub     edx, r13d
0x180020173  jz      loc_1800202BB
0x180020179  cmp     edx, r13d
0x18002017c  jnz     short loc_1800201CA
0x18002017e  movzx   eax, word ptr [rdi+8]
0x180020182  sub     ax, [rsi+8]
0x180020186  neg     ax
0x180020189  jmp     loc_1800202D8
0x18002018e  mov     rax, [rdi+8]
0x180020192  sub     rax, [rsi+8]
0x180020196  neg     rax
0x180020199  jmp     loc_1800202D8
0x18002019e  cmp     edx, 15h
0x1800201a1  ja      loc_180020265
0x1800201a7  jz      loc_18002025B
0x1800201ad  sub     edx, 10h
0x1800201b0  jz      loc_180020243
0x1800201b6  sub     edx, r13d
0x1800201b9  jz      short loc_180020236
0x1800201bb  sub     edx, r13d
0x1800201be  jz      short loc_18002022C
0x1800201c0  sub     edx, r13d
0x1800201c3  jz      short loc_180020224
0x1800201c5  cmp     edx, r13d
0x1800201c8  jz      short loc_180020150
0x1800201ca  cmp     cs:qword_180171350, r12
0x1800201d1  mov     ebp, 0C00D36E8h
0x1800201d6  jnz     loc_1800202DC
0x1800201dc  call    cs:MFGetCallStackTracingWeakReference
0x1800201e3  nop     dword ptr [rax+rax+00h]
0x1800201e8  mov     cs:qword_180171350, rax
0x1800201ef  mov     rcx, rax
0x1800201f2  test    rax, rax
0x1800201f5  jz      short loc_180020211
0x1800201f7  mov     rax, [rax]
0x1800201fa  mov     edx, 7F0h
0x1800201ff  mov     rax, [rax+8]
0x180020203  call    cs:__guard_dispatch_icall_fptr
0x180020209  test    eax, eax
0x18002020b  jnz     loc_1800202DC
0x180020211  lea     rdi, off_1801703B0
0x180020218  mov     cs:qword_180171350, rdi
0x18002021f  jmp     loc_1800202E3
0x180020224  mov     eax, [rdi+8]
0x180020227  cmp     [rsi+8], eax
0x18002022a  jmp     short loc_18002023C
0x18002022c  movzx   eax, word ptr [rdi+8]
0x180020230  cmp     [rsi+8], ax
0x180020234  jmp     short loc_18002023C
0x180020236  mov     al, [rdi+8]
0x180020239  cmp     [rsi+8], al
0x18002023c  ja      short loc_18002024B
0x18002023e  jmp     loc_1800202D8
0x180020243  mov     cl, [rdi+8]
0x180020246  cmp     cl, [rsi+8]
0x180020249  jge     short loc_180020250
0x18002024b  or      eax, 0FFFFFFFFh
0x18002024e  jmp     short loc_1800202B3
0x180020250  mov     eax, r12d
0x180020253  setle   al
0x180020256  sub     eax, r13d
0x180020259  jmp     short loc_1800202B3
0x18002025b  mov     rax, [rdi+8]
0x18002025f  cmp     [rsi+8], rax
0x180020263  jmp     short loc_18002023C
0x180020265  sub     edx, 16h
0x180020268  jz      short loc_1800202BB
0x18002026a  sub     edx, r13d
0x18002026d  jz      short loc_180020224
0x18002026f  sub     edx, 7
0x180020272  jz      short loc_1800202A6
0x180020274  sub     edx, r13d
0x180020277  jz      short loc_180020297
0x180020279  cmp     edx, 21h ; '!'
0x18002027c  jnz     loc_1800201CA
0x180020282  lea     rdx, [rsi+8]; Buf2
0x180020286  mov     r8d, 8; Size
0x18002028c  lea     rcx, [rdi+8]; Buf1
0x180020290  call    memcmp
0x180020295  jmp     short loc_1800202B3
  ... truncated ...
```
