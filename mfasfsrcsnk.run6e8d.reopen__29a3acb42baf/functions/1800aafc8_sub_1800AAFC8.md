# sub_1800AAFC8

- ea: `0x1800aafc8`
- end: `0x1800ab974`
- name: `sub_1800AAFC8`
- size: `2476`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x18002b3b0`
- `0x1800abab0`

## callees

- `0x180001870`
- `0x180005880`
- `0x18000a580`
- `0x18003d740`
- `0x18004f390`
- `0x18004f3fc`
- `0x18007fdd0`
- `0x1800aa194`
- `0x1800aa2e8`
- `0x1800aadc4`
- `0x1800aafc8`
- `0x1800ac27c`
- `0x18013e280`
- `0x18013e2e0`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800ab3f2`
- `MFPlat!MFCreateMediaType` at `0x1800ab499`
- `MFPlat!MFCreateMediaType` at `0x1800ab3f2`
- `MFPlat!MFCreateMediaType` at `0x1800ab499`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab062`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab11a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab26a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab328`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab40f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab4b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab56b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab61e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab782`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab838`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab062`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab11a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab26a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab328`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab40f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab4b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab56b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab61e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab782`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab838`

## pseudocode

```c
__int64 __fastcall sub_1800AAFC8(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int v6; // r15d
  __int64 v7; // rdx
  __int64 (__fastcall ***v8)(); // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 (__fastcall ***v12)(); // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  HRESULT v18; // r14d
  __int64 (__fastcall ***v19)(); // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 (__fastcall ***v23)(); // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 (__fastcall ***v27)(); // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 (__fastcall ***v31)(); // rcx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 (__fastcall ***v35)(); // rcx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rdx
  int v39; // esi
  __int64 (__fastcall ***v40)(); // rcx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 (__fastcall ***v44)(); // rcx
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 (__fastcall ***v48)(); // rcx
  __int64 v49; // rax
  __int64 v50; // rax
  int v52; // [rsp+20h] [rbp-E0h]
  _BYTE v53[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v54; // [rsp+34h] [rbp-CCh] BYREF
  IMFMediaType *ppMFType; // [rsp+38h] [rbp-C8h] BYREF
  IMFMediaType *v56; // [rsp+40h] [rbp-C0h] BYREF
  int v57; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v58[192]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v59[192]; // [rsp+110h] [rbp+10h] BYREF
  __int128 Buf2; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v61; // [rsp+1E0h] [rbp+E0h] BYREF

  v54 = 0;
  ppMFType = 0;
  v56 = 0;
  v57 = 0;
  v6 = 0;
  Buf2 = 0;
  v61 = 0;
  sub_18000A580(v53, "CMFASFSinkMediaTypeHandler::MatchesOurMediaType", 328);
  v7 = *(_QWORD *)(a1 + 80);
  if ( !v7 )
  {
    v8 = (__int64 (__fastcall ***)())qword_180169350;
    if ( !qword_180169350 )
    {
      v9 = MFGetCallStackTracingWeakReference(0, 0);
      qword_180169350 = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 (__fastcall ***)())qword_180169350;
      }
      else
      {
        v8 = &off_1801683B0;
        qword_180169350 = (__int64)&off_1801683B0;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v10 = sub_180001870(v8);
      if ( *(_DWORD *)(v10 + 1996) != -2147467261 )
        sub_18007FDD0(v10, "CMFASFSinkMediaTypeHandler::MatchesOurMediaType", 328, 2147500035LL);
    }
    if ( byte_1801692C8 )
    {
      v11 = 22;
LABEL_12:
      v52 = -2147467261;
LABEL_13:
      sub_18004F390(*((_QWORD *)RequestContext + 2), v11, qword_1801560C0, a1, v52);
      goto LABEL_125;
    }
    goto LABEL_125;
  }
  if ( a2 )
  {
    sub_1800AA194(v59);
    sub_1800AA194(v58);
    if ( (unsigned __int8)byte_1801692CA >= 0x10u )
    {
      v15 = sub_1800AADC4(v59, 0);
      sub_1800AC27C(*((_QWORD *)RequestContext + 12), 24, (unsigned int)qword_1801560C0, a1, v15);
      if ( (unsigned __int8)byte_1801692CA >= 0x10u )
      {
        v16 = sub_1800AADC4(v58, 0);
        sub_1800AC27C(*((_QWORD *)RequestContext + 12), 25, (unsigned int)qword_1801560C0, a1, v16);
      }
    }
    sub_1800AA2E8(v58);
    sub_1800AA2E8(v59);
    v18 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(a1 + 80) + 264LL))(*(_QWORD *)(a1 + 80), &Buf2);
    if ( v18 < 0 )
    {
      v19 = (__int64 (__fastcall ***)())qword_180169350;
      if ( !qword_180169350 )
      {
        v20 = MFGetCallStackTracingWeakReference(0, v17);
        qword_180169350 = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (__int64 (__fastcall ***)())qword_180169350;
        }
        else
        {
          v19 = &off_1801683B0;
          qword_180169350 = (__int64)&off_1801683B0;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = sub_180001870(v19);
        if ( *(_DWORD *)(v21 + 1996) != v18 )
          sub_18007FDD0(v21, "CMFASFSinkMediaTypeHandler::MatchesOurMediaType", 344, (unsigned int)v18);
      }
      if ( !byte_1801692C8 )
        goto LABEL_125;
      v11 = 26;
      goto LABEL_39;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 264LL))(a2, &v61);
    if ( v18 < 0 )
    {
      v23 = (__int64 (__fastcall ***)())qword_180169350;
      if ( !qword_180169350 )
      {
        v24 = MFGetCallStackTracingWeakReference(0, v22);
        qword_180169350 = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (__int64 (__fastcall ***)())qword_180169350;
        }
        else
        {
          v23 = &off_1801683B0;
          qword_180169350 = (__int64)&off_1801683B0;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = sub_180001870(v23);
        if ( *(_DWORD *)(v25 + 1996) != v18 )
          sub_18007FDD0(v25, "CMFASFSinkMediaTypeHandler::MatchesOurMediaType", 345, (unsigned int)v18);
      }
      if ( !byte_1801692C8 )
        goto LABEL_125;
      v11 = 27;
      goto LABEL_39;
    }
    if ( !memcmp("vids", &Buf2, 0x10u) && !memcmp("vids", &v61, 0x10u) )
    {
      v18 = MFCreateMediaType(&ppMFType);
      if ( v18 < 0 )
      {
        v27 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v28 = MFGetCallStackTracingWeakReference(0, v26);
          qword_180169350 = v28;
          if ( v28 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
          {
            v27 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v27 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v27 + 8) )
        {
          v29 = sub_180001870(v27);
          if ( *(_DWORD *)(v29 + 1996) != v18 )
            sub_18007FDD0(v29, "CMFASFSinkMediaTypeHandler::MatchesOurMediaType", 366, (unsigned int)v18);
        }
        if ( !byte_1801692C8 )
          goto LABEL_125;
        v11 = 29;
        goto LABEL_39;
      }
      v18 = MFCreateMediaType(&v56);
      if ( v18 < 0 )
      {
        v31 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v32 = MFGetCallStackTracingWeakReference(0, v30);
          qword_180169350 = v32;
          if ( v32 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
          {
            v31 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v31 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v31 + 8) )
        {
          v33 = sub_180001870(v31);
          if ( *(_DWORD *)(v33 + 1996) != v18 )
            sub_18007FDD0(v33, "CMFASFSinkMediaTypeHandler::MatchesOurMediaType", 367, (unsigned int)v18);
        }
        if ( !byte_1801692C8 )
          goto LABEL_125;
        v11 = 30;
        goto LABEL_39;
      }
      v18 = (*(__int64 (__fastcall **)(_QWORD, IMFMediaType *))(**(_QWORD **)(a1 + 80) + 256LL))(
              *(_QWORD *)(a1 + 80),
              ppMFType);
      if ( v18 < 0 )
      {
        v35 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v36 = MFGetCallStackTracingWeakReference(0, v34);
          qword_180169350 = v36;
          if ( v36 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
          {
            v35 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v35 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v35 + 8) )
        {
          v37 = sub_180001870(v35);
          if ( *(_DWORD *)(v37 + 1996) != v18 )
            sub_18007FDD0(v37, "CMFASFSinkMediaTypeHandler::MatchesOurMediaType", 368, (unsigned int)v18);
        }
        if ( !byte_1801692C8 )
          goto LABEL_125;
        v11 = 31;
LABEL_39:
        v52 = v18;
        goto LABEL_13;
      }
      v39 = (*(__int64 (__fastcall **)(__int64, IMFMediaType *))(*(_QWORD *)a2 + 256LL))(a2, v56);
      if ( v39 < 0 )
      {
        v40 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v41 = MFGetCallStackTracingWeakReference(0, v38);
          qword_180169350 = v41;
          if ( v41 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
          {
            v40 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v40 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v40 + 8) )
        {
          v42 = sub_180001870(v40);
          if ( *(_DWORD *)(v42 + 1996) != v39 )
            sub_18007FDD0(v42, "CMFASFSinkMediaTypeHandler::MatchesOurMediaType", 369, (unsigned int)v39);
        }
        if ( !byte_1801692C8 )
          goto LABEL_125;
        v11 = 32;
        goto LABEL_122;
      }
      ((void (__fastcall *)(IMFMediaType *, __int64 *))ppMFType->lpVtbl->DeleteItem)(ppMFType, qword_18014EBD0);
      ((void (__fastcall *)(IMFMediaType *, __int64 *))v56->lpVtbl->DeleteItem)(v56, qword_18014EBD0);
      if ( ((int (__fastcall *)(IMFMediaType *, __int64 *, int *))ppMFType->lpVtbl->GetUINT32)(
             ppMFType,
             qword_18014EAF0,
             &v57) < 0
        || ((int (__fastcall *)(IMFMediaType *, __int64 *, int *))v56->lpVtbl->GetUINT32)(v56, qword_18014EAF0, &v57) < 0 )
      {
        ((void (__fastcall *)(IMFMediaType *, __int64 *))ppMFType->lpVtbl->DeleteItem)(ppMFType, qword_18014EAF0);
        ((void (__fastcall *)(IMFMediaType *, __int64 *))v56->lpVtbl->DeleteItem)(v56, qword_18014EAF0);
      }
      v39 = ((__int64 (__fastcall *)(IMFMediaType *, IMFMediaType *, unsigned int *))ppMFType->lpVtbl->IsEqual)(
              ppMFType,
              v56,
              &v54);
      if ( v39 < 0 )
      {
        v44 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v45 = MFGetCallStackTracingWeakReference(0, v43);
          qword_180169350 = v45;
          if ( v45 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
          {
            v44 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v44 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v44 + 8) )
        {
          v46 = sub_180001870(v44);
          if ( *(_DWORD *)(v46 + 1996) != v39 )
            sub_18007FDD0(v46, "CMFASFSinkMediaTypeHandler::MatchesOurMediaType", 383, (unsigned int)v39);
        }
        if ( !byte_1801692C8 )
          goto LABEL_125;
        v11 = 33;
        goto LABEL_122;
      }
    }
    else
    {
      v39 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *))(**(_QWORD **)(a1 + 80) + 280LL))(
              *(_QWORD *)(a1 + 80),
              a2,
              &v54);
      if ( v39 < 0 )
      {
        v48 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v49 = MFGetCallStackTracingWeakReference(0, v47);
          qword_180169350 = v49;
          if ( v49 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
          {
            v48 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v48 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v48 + 8) )
        {
          v50 = sub_180001870(v48);
          if ( *(_DWORD *)(v50 + 1996) != v39 )
            sub_18007FDD0(v50, "CMFASFSinkMediaTypeHandler::MatchesOurMediaType", 350, (unsigned int)v39);
        }
        if ( !byte_1801692C8 )
          goto LABEL_125;
        v11 = 28;
LABEL_122:
        v52 = v39;
        goto LABEL_13;
      }
    }
    v6 = (v54 >> 2) & 1;
    if ( (unsigned __int8)byte_1801692CA >= 0x10u )
      sub_18004F3FC(*((_QWORD *)RequestContext + 12), 34, qword_1801560C0, a1, v54, (v54 >> 2) & 1);
    goto LABEL_125;
  }
  v12 = (__int64 (__fastcall ***)())qword_180169350;
  if ( !qword_180169350 )
  {
    v13 = MFGetCallStackTracingWeakReference(0, v7);
    qword_180169350 = v13;
    if ( v13 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
    {
      v12 = (__int64 (__fastcall ***)())qword_180169350;
    }
    else
    {
      v12 = &off_1801683B0;
      qword_180169350 = (__int64)&off_1801683B0;
    }
  }
  if ( *((_BYTE *)v12 + 8) )
  {
    v14 = sub_180001870(v12);
    if ( *(_DWORD *)(v14 + 1996) != -2147467261 )
      sub_18007FDD0(v14, "CMFASFSinkMediaTypeHandler::MatchesOurMediaType", 329, 2147500035LL);
  }
  if ( byte_1801692C8 )
  {
    v11 = 23;
    goto LABEL_12;
  }
LABEL_125:
  if ( ppMFType )
  {
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
    ppMFType = 0;
  }
  if ( v56 )
  {
    ((void (__fastcall *)(IMFMediaType *))v56->lpVtbl->Release)(v56);
    v56 = 0;
  }
  if ( a3 )
    *a3 = v54;
  sub_180005880(v53);
  return v6;
}

```

## disassembly

```asm
0x1800aafc8  mov     [rsp-8+arg_18], rbx
0x1800aafcd  push    rbp
0x1800aafce  push    rsi
0x1800aafcf  push    rdi
0x1800aafd0  push    r12
0x1800aafd2  push    r13
0x1800aafd4  push    r14
0x1800aafd6  push    r15
0x1800aafd8  lea     rbp, [rsp-100h]
0x1800aafe0  sub     rsp, 200h
0x1800aafe7  mov     rax, cs:__security_cookie
0x1800aafee  xor     rax, rsp
0x1800aaff1  mov     [rbp+130h+var_40], rax
0x1800aaff8  xor     r13d, r13d
0x1800aaffb  lea     r14, aCmfasfsinkmedi_1; "CMFASFSinkMediaTypeHandler::MatchesOurM"...
0x1800ab002  mov     r12, r8
0x1800ab005  mov     [rsp+230h+var_1FC], r13d
0x1800ab00a  mov     rsi, rdx
0x1800ab00d  mov     [rsp+230h+ppMFType], r13
0x1800ab012  mov     rdi, rcx
0x1800ab015  mov     [rsp+230h+var_1F0], r13
0x1800ab01a  xorps   xmm0, xmm0
0x1800ab01d  mov     [rsp+230h+var_1E8], r13d
0x1800ab022  xorps   xmm1, xmm1
0x1800ab025  lea     rcx, [rsp+230h+var_200]
0x1800ab02a  mov     rdx, r14
0x1800ab02d  mov     r8d, 148h
0x1800ab033  mov     r15d, r13d
0x1800ab036  movups  [rbp+130h+Buf2], xmm0
0x1800ab03d  movups  [rbp+130h+var_50], xmm1
0x1800ab044  call    sub_18000A580
0x1800ab049  mov     rdx, [rdi+50h]
0x1800ab04d  test    rdx, rdx
0x1800ab050  jnz     loc_1800AB105
0x1800ab056  mov     rcx, cs:qword_180169350
0x1800ab05d  test    rcx, rcx
0x1800ab060  jnz     short loc_1800AB0A4
0x1800ab062  call    cs:MFGetCallStackTracingWeakReference
0x1800ab068  mov     cs:qword_180169350, rax
0x1800ab06f  mov     rcx, rax
0x1800ab072  test    rax, rax
0x1800ab075  jz      short loc_1800AB096
0x1800ab077  mov     rax, [rax]
0x1800ab07a  mov     edx, 7F0h
0x1800ab07f  mov     rax, [rax+8]
0x1800ab083  call    cs:__guard_dispatch_icall_fptr
0x1800ab089  test    eax, eax
0x1800ab08b  jz      short loc_1800AB096
0x1800ab08d  mov     rcx, cs:qword_180169350
0x1800ab094  jmp     short loc_1800AB0A4
0x1800ab096  lea     rcx, off_1801683B0
0x1800ab09d  mov     cs:qword_180169350, rcx
0x1800ab0a4  mov     ebx, 80004003h
0x1800ab0a9  cmp     [rcx+8], r13b
0x1800ab0ad  jz      short loc_1800AB0D0
0x1800ab0af  call    sub_180001870
0x1800ab0b4  cmp     [rax+7CCh], ebx
0x1800ab0ba  jz      short loc_1800AB0D0
0x1800ab0bc  mov     r9d, ebx
0x1800ab0bf  mov     r8d, 148h
0x1800ab0c5  mov     rdx, r14
0x1800ab0c8  mov     rcx, rax
0x1800ab0cb  call    sub_18007FDD0
0x1800ab0d0  cmp     cs:byte_1801692C8, 1
0x1800ab0d7  jb      loc_1800AB8F8
0x1800ab0dd  mov     edx, 16h
0x1800ab0e2  mov     dword ptr [rsp+230h+var_210], ebx
0x1800ab0e6  lea     r8, qword_1801560C0
0x1800ab0ed  mov     rcx, cs:RequestContext
0x1800ab0f4  mov     r9, rdi
0x1800ab0f7  mov     rcx, [rcx+10h]
0x1800ab0fb  call    sub_18004F390
0x1800ab100  jmp     loc_1800AB8F8
0x1800ab105  test    rsi, rsi
0x1800ab108  jnz     loc_1800AB19F
0x1800ab10e  mov     rcx, cs:qword_180169350
0x1800ab115  test    rcx, rcx
0x1800ab118  jnz     short loc_1800AB15C
0x1800ab11a  call    cs:MFGetCallStackTracingWeakReference
0x1800ab120  mov     cs:qword_180169350, rax
0x1800ab127  mov     rcx, rax
0x1800ab12a  test    rax, rax
0x1800ab12d  jz      short loc_1800AB14E
0x1800ab12f  mov     rax, [rax]
0x1800ab132  mov     edx, 7F0h
0x1800ab137  mov     rax, [rax+8]
0x1800ab13b  call    cs:__guard_dispatch_icall_fptr
0x1800ab141  test    eax, eax
0x1800ab143  jz      short loc_1800AB14E
0x1800ab145  mov     rcx, cs:qword_180169350
0x1800ab14c  jmp     short loc_1800AB15C
0x1800ab14e  lea     rcx, off_1801683B0
0x1800ab155  mov     cs:qword_180169350, rcx
0x1800ab15c  mov     ebx, 80004003h
0x1800ab161  cmp     [rcx+8], r13b
0x1800ab165  jz      short loc_1800AB188
0x1800ab167  call    sub_180001870
0x1800ab16c  cmp     [rax+7CCh], ebx
0x1800ab172  jz      short loc_1800AB188
0x1800ab174  mov     r9d, ebx
0x1800ab177  mov     r8d, 149h
0x1800ab17d  mov     rdx, r14
0x1800ab180  mov     rcx, rax
0x1800ab183  call    sub_18007FDD0
0x1800ab188  cmp     cs:byte_1801692C8, 1
0x1800ab18f  jb      loc_1800AB8F8
0x1800ab195  mov     edx, 17h
0x1800ab19a  jmp     loc_1800AB0E2
0x1800ab19f  lea     rcx, [rbp+130h+var_120]
0x1800ab1a3  call    sub_1800AA194
0x1800ab1a8  mov     rdx, rsi
0x1800ab1ab  lea     rcx, [rsp+230h+var_1E0]
0x1800ab1b0  call    sub_1800AA194
0x1800ab1b5  cmp     cs:byte_1801692CA, 10h
0x1800ab1bc  lea     rbx, qword_1801560C0
0x1800ab1c3  jb      short loc_1800AB225
0x1800ab1c5  xor     edx, edx
0x1800ab1c7  lea     rcx, [rbp+130h+var_120]
0x1800ab1cb  call    sub_1800AADC4
0x1800ab1d0  mov     rcx, cs:RequestContext
0x1800ab1d7  mov     edx, 18h
0x1800ab1dc  mov     r9, rdi
0x1800ab1df  mov     [rsp+230h+var_210], rax
0x1800ab1e4  mov     r8, rbx
0x1800ab1e7  mov     rcx, [rcx+60h]
0x1800ab1eb  call    sub_1800AC27C
0x1800ab1f0  cmp     cs:byte_1801692CA, 10h
0x1800ab1f7  jb      short loc_1800AB225
0x1800ab1f9  xor     edx, edx
0x1800ab1fb  lea     rcx, [rsp+230h+var_1E0]
0x1800ab200  call    sub_1800AADC4
0x1800ab205  mov     rcx, cs:RequestContext
0x1800ab20c  mov     edx, 19h
0x1800ab211  mov     r9, rdi
0x1800ab214  mov     [rsp+230h+var_210], rax
0x1800ab219  mov     r8, rbx
0x1800ab21c  mov     rcx, [rcx+60h]
0x1800ab220  call    sub_1800AC27C
0x1800ab225  lea     rcx, [rsp+230h+var_1E0]
0x1800ab22a  call    sub_1800AA2E8
0x1800ab22f  lea     rcx, [rbp+130h+var_120]
0x1800ab233  call    sub_1800AA2E8
0x1800ab238  mov     rcx, [rdi+50h]
0x1800ab23c  lea     rdx, [rbp+130h+Buf2]
0x1800ab243  mov     rax, [rcx]
0x1800ab246  mov     rax, [rax+108h]
0x1800ab24d  call    cs:__guard_dispatch_icall_fptr
0x1800ab253  mov     r14d, eax
0x1800ab256  test    eax, eax
0x1800ab258  jns     loc_1800AB2F7
0x1800ab25e  mov     rcx, cs:qword_180169350
0x1800ab265  test    rcx, rcx
0x1800ab268  jnz     short loc_1800AB2AC
0x1800ab26a  call    cs:MFGetCallStackTracingWeakReference
0x1800ab270  mov     cs:qword_180169350, rax
0x1800ab277  mov     rcx, rax
0x1800ab27a  test    rax, rax
0x1800ab27d  jz      short loc_1800AB29E
0x1800ab27f  mov     rax, [rax]
0x1800ab282  mov     edx, 7F0h
0x1800ab287  mov     rax, [rax+8]
0x1800ab28b  call    cs:__guard_dispatch_icall_fptr
0x1800ab291  test    eax, eax
0x1800ab293  jz      short loc_1800AB29E
0x1800ab295  mov     rcx, cs:qword_180169350
0x1800ab29c  jmp     short loc_1800AB2AC
0x1800ab29e  lea     rcx, off_1801683B0
0x1800ab2a5  mov     cs:qword_180169350, rcx
0x1800ab2ac  cmp     [rcx+8], r13b
0x1800ab2b0  jz      short loc_1800AB2D8
0x1800ab2b2  call    sub_180001870
0x1800ab2b7  cmp     [rax+7CCh], r14d
0x1800ab2be  jz      short loc_1800AB2D8
0x1800ab2c0  mov     r9d, r14d
0x1800ab2c3  lea     rdx, aCmfasfsinkmedi_1; "CMFASFSinkMediaTypeHandler::MatchesOurM"...
0x1800ab2ca  mov     r8d, 158h
0x1800ab2d0  mov     rcx, rax
0x1800ab2d3  call    sub_18007FDD0
0x1800ab2d8  cmp     cs:byte_1801692C8, 1
0x1800ab2df  jb      loc_1800AB8F8
0x1800ab2e5  mov     edx, 1Ah
0x1800ab2ea  mov     dword ptr [rsp+230h+var_210], r14d
0x1800ab2ef  mov     r8, rbx
0x1800ab2f2  jmp     loc_1800AB0ED
0x1800ab2f7  mov     rax, [rsi]
0x1800ab2fa  lea     rdx, [rbp+130h+var_50]
0x1800ab301  mov     rcx, rsi
0x1800ab304  mov     rax, [rax+108h]
0x1800ab30b  call    cs:__guard_dispatch_icall_fptr
0x1800ab311  mov     r14d, eax
0x1800ab314  test    eax, eax
0x1800ab316  jns     loc_1800AB3AD
0x1800ab31c  mov     rcx, cs:qword_180169350
0x1800ab323  test    rcx, rcx
0x1800ab326  jnz     short loc_1800AB36A
0x1800ab328  call    cs:MFGetCallStackTracingWeakReference
0x1800ab32e  mov     cs:qword_180169350, rax
0x1800ab335  mov     rcx, rax
0x1800ab338  test    rax, rax
0x1800ab33b  jz      short loc_1800AB35C
0x1800ab33d  mov     rax, [rax]
0x1800ab340  mov     edx, 7F0h
0x1800ab345  mov     rax, [rax+8]
0x1800ab349  call    cs:__guard_dispatch_icall_fptr
0x1800ab34f  test    eax, eax
0x1800ab351  jz      short loc_1800AB35C
0x1800ab353  mov     rcx, cs:qword_180169350
0x1800ab35a  jmp     short loc_1800AB36A
0x1800ab35c  lea     rcx, off_1801683B0
0x1800ab363  mov     cs:qword_180169350, rcx
0x1800ab36a  cmp     [rcx+8], r13b
0x1800ab36e  jz      short loc_1800AB396
0x1800ab370  call    sub_180001870
0x1800ab375  cmp     [rax+7CCh], r14d
0x1800ab37c  jz      short loc_1800AB396
0x1800ab37e  mov     r9d, r14d
0x1800ab381  lea     rdx, aCmfasfsinkmedi_1; "CMFASFSinkMediaTypeHandler::MatchesOurM"...
0x1800ab388  mov     r8d, 159h
0x1800ab38e  mov     rcx, rax
0x1800ab391  call    sub_18007FDD0
0x1800ab396  cmp     cs:byte_1801692C8, 1
0x1800ab39d  jb      loc_1800AB8F8
0x1800ab3a3  mov     edx, 1Bh
0x1800ab3a8  jmp     loc_1800AB2EA
0x1800ab3ad  mov     r8d, 10h; Size
0x1800ab3b3  lea     rdx, [rbp+130h+Buf2]; Buf2
0x1800ab3ba  lea     rcx, aVids; "vids"
0x1800ab3c1  call    memcmp
0x1800ab3c6  test    eax, eax
0x1800ab3c8  jnz     loc_1800AB806
0x1800ab3ce  lea     r8d, [rax+10h]; Size
0x1800ab3d2  lea     rdx, [rbp+130h+var_50]; Buf2
0x1800ab3d9  lea     rcx, aVids; "vids"
0x1800ab3e0  call    memcmp
0x1800ab3e5  test    eax, eax
0x1800ab3e7  jnz     loc_1800AB806
0x1800ab3ed  lea     rcx, [rsp+230h+ppMFType]; ppMFType
0x1800ab3f2  call    cs:MFCreateMediaType
0x1800ab3f8  mov     r14d, eax
0x1800ab3fb  test    eax, eax
0x1800ab3fd  jns     loc_1800AB494
0x1800ab403  mov     rcx, cs:qword_180169350
0x1800ab40a  test    rcx, rcx
0x1800ab40d  jnz     short loc_1800AB451
0x1800ab40f  call    cs:MFGetCallStackTracingWeakReference
0x1800ab415  mov     cs:qword_180169350, rax
0x1800ab41c  mov     rcx, rax
0x1800ab41f  test    rax, rax
0x1800ab422  jz      short loc_1800AB443
0x1800ab424  mov     rax, [rax]
0x1800ab427  mov     edx, 7F0h
0x1800ab42c  mov     rax, [rax+8]
0x1800ab430  call    cs:__guard_dispatch_icall_fptr
0x1800ab436  test    eax, eax
0x1800ab438  jz      short loc_1800AB443
0x1800ab43a  mov     rcx, cs:qword_180169350
0x1800ab441  jmp     short loc_1800AB451
0x1800ab443  lea     rcx, off_1801683B0
0x1800ab44a  mov     cs:qword_180169350, rcx
0x1800ab451  cmp     [rcx+8], r13b
0x1800ab455  jz      short loc_1800AB47D
0x1800ab457  call    sub_180001870
0x1800ab45c  cmp     [rax+7CCh], r14d
0x1800ab463  jz      short loc_1800AB47D
0x1800ab465  mov     r9d, r14d
0x1800ab468  lea     rdx, aCmfasfsinkmedi_1; "CMFASFSinkMediaTypeHandler::MatchesOurM"...
0x1800ab46f  mov     r8d, 16Eh
0x1800ab475  mov     rcx, rax
0x1800ab478  call    sub_18007FDD0
0x1800ab47d  cmp     cs:byte_1801692C8, 1
0x1800ab484  jb      loc_1800AB8F8
0x1800ab48a  mov     edx, 1Dh
0x1800ab48f  jmp     loc_1800AB2EA
0x1800ab494  lea     rcx, [rsp+230h+var_1F0]; ppMFType
0x1800ab499  call    cs:MFCreateMediaType
0x1800ab49f  mov     r14d, eax
0x1800ab4a2  test    eax, eax
0x1800ab4a4  jns     loc_1800AB53B
0x1800ab4aa  mov     rcx, cs:qword_180169350
0x1800ab4b1  test    rcx, rcx
0x1800ab4b4  jnz     short loc_1800AB4F8
0x1800ab4b6  call    cs:MFGetCallStackTracingWeakReference
0x1800ab4bc  mov     cs:qword_180169350, rax
0x1800ab4c3  mov     rcx, rax
0x1800ab4c6  test    rax, rax
0x1800ab4c9  jz      short loc_1800AB4EA
0x1800ab4cb  mov     rax, [rax]
0x1800ab4ce  mov     edx, 7F0h
0x1800ab4d3  mov     rax, [rax+8]
0x1800ab4d7  call    cs:__guard_dispatch_icall_fptr
0x1800ab4dd  test    eax, eax
0x1800ab4df  jz      short loc_1800AB4EA
0x1800ab4e1  mov     rcx, cs:qword_180169350
0x1800ab4e8  jmp     short loc_1800AB4F8
0x1800ab4ea  lea     rcx, off_1801683B0
0x1800ab4f1  mov     cs:qword_180169350, rcx
0x1800ab4f8  cmp     [rcx+8], r13b
0x1800ab4fc  jz      short loc_1800AB524
0x1800ab4fe  call    sub_180001870
0x1800ab503  cmp     [rax+7CCh], r14d
  ... truncated ...
```
