# FwQueryConditionMatchObject

- ea: `0x180004810`
- end: `0x1800051db`
- name: `FwQueryConditionMatchObject`
- size: `2507`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004314`
- `0x1800043f0`

## callees

- `0x180004810`
- `0x18000521c`
- `0x180005260`
- `0x1800052a0`
- `0x18000af3c`
- `0x1800670c0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004a73`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004c75`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004c8d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004a73`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004c75`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004c8d`

## string_xrefs

- `0x180004c9d`: `mpssvc.dll`
- `0x180004cb1`: `mpssvc.dll`
- `0x180004cd6`: `mpssvc.dll`
- `0x180004d19`: `mpssvc.dll`
- `0x180004d5c`: `mpssvc.dll`
- `0x180004d9f`: `mpssvc.dll`
- `0x180004dea`: `mpssvc.dll`
- `0x180004e5f`: `mpssvc.dll`
- `0x180004f00`: `mpssvc.dll`
- `0x180004f43`: `mpssvc.dll`
- `0x180004f8e`: `mpssvc.dll`
- `0x180004ffa`: `mpssvc.dll`
- `0x18000505e`: `mpssvc.dll`
- `0x1800050c2`: `mpssvc.dll`
- `0x180005105`: `mpssvc.dll`
- `0x180005145`: `mpssvc.dll`
- `0x180005185`: `mpssvc.dll`

## pseudocode

```c
int __fastcall FwQueryConditionMatchObject(__int64 a1, __int64 a2, unsigned int a3, _QWORD *a4)
{
  __int64 v4; // rbp
  int v8; // ecx
  int v9; // edi
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  __int64 v16; // rdx
  unsigned __int16 v17; // cx
  __int64 v18; // rdx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rdx
  unsigned __int16 v31; // cx
  bool v32; // zf
  __int64 v33; // rdx
  __int64 v34; // rcx
  int v35; // edx
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  const WCHAR *v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // rax
  bool v42; // zf
  __int64 v43; // rdx
  unsigned __int16 v44; // cx
  __int64 v45; // rdx
  const WCHAR *v46; // rsi
  __int64 v47; // rdx
  const unsigned __int16 *v48; // rdx
  const unsigned __int16 *v49; // rcx
  __int64 v50; // rdx
  bool v51; // zf
  __int64 v52; // rdx
  __int64 v53; // rdx
  __int64 v54; // rdx
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // rdx
  __int64 v59; // rdx
  __int64 v60; // rdx
  __int64 v61; // rdx

  v4 = (int)a3;
  if ( a3 > 5 )
    return 0;
  v8 = *(_DWORD *)a1;
  if ( v8 > 8 )
  {
    v19 = v8 - 9;
    if ( !v19 )
    {
      v45 = *(unsigned int *)(a1 + 8);
      if ( (_DWORD)v45 != 5 )
        MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v45, 0);
      if ( *(_DWORD *)(a1 + 8) != 5 )
      {
        v56 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          return 0;
        v57 = 19;
        goto LABEL_175;
      }
      _mm_lfence();
      v9 = 0;
      v46 = *(const WCHAR **)(LODWORD(g_FwObjectHandler[11 * v4 + 2]) + a2);
      if ( !v46 || !lstrcmpiW(*(LPCWSTR *)(a1 + 16), v46) )
        return 1;
      v32 = lstrcmpiW(L"*", v46) == 0;
      goto LABEL_43;
    }
    v20 = v19 - 1;
    if ( v20 )
    {
      v21 = v20 - 1;
      if ( !v21 )
      {
        v37 = *(unsigned int *)(a1 + 8);
        if ( (_DWORD)v37 != 5 )
          MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v37, 0);
        if ( *(_DWORD *)(a1 + 8) != 5 )
        {
          v56 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            return 0;
          v57 = 21;
          goto LABEL_175;
        }
        v38 = 11 * v4;
        v35 = 1;
        v32 = *(_DWORD *)(a1 + 4) == 1;
        _mm_lfence();
        if ( v32 )
        {
          v36 = LODWORD(g_FwObjectHandler[v38 + 7]);
LABEL_55:
          v39 = *(const WCHAR **)(a1 + 16);
          if ( v39 )
          {
            if ( *(_QWORD *)(v36 + a2) )
              return lstrcmpiW(v39, *(LPCWSTR *)(v36 + a2)) == 0;
          }
          else if ( !*(_QWORD *)(v36 + a2) )
          {
            return v35;
          }
          return 0;
        }
        v47 = LODWORD(g_FwObjectHandler[v38 + 7]);
LABEL_76:
        v48 = *(const unsigned __int16 **)(v47 + a2);
        v49 = *(const unsigned __int16 **)(a1 + 16);
        return FwQueryOperatorAppPathMatchTraffic(v49, v48);
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        v50 = *(unsigned int *)(a1 + 8);
        if ( (_DWORD)v50 != 5 )
          MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v50, 0);
        if ( *(_DWORD *)(a1 + 8) != 5 )
        {
          v56 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            return 0;
          v57 = 22;
          goto LABEL_175;
        }
        v51 = *(_DWORD *)(a1 + 4) == 1;
        _mm_lfence();
        v52 = HIDWORD(g_FwObjectHandler[11 * v4 + 7]);
        goto LABEL_82;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        v61 = *(unsigned int *)(a1 + 8);
        if ( (_DWORD)v61 != 5 )
          MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v61, 0);
        if ( *(_DWORD *)(a1 + 8) != 5 )
        {
          v56 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            return 0;
          v57 = 24;
          goto LABEL_175;
        }
        v51 = *(_DWORD *)(a1 + 4) == 1;
        _mm_lfence();
        v52 = LODWORD(g_FwObjectHandler[11 * v4 + 8]);
        goto LABEL_82;
      }
      v24 = v23 - 1;
      if ( v24 )
      {
        v25 = v24 - 1;
        if ( v25 )
        {
          if ( v25 != 1 )
            return 0;
          v33 = *(unsigned int *)(a1 + 8);
          if ( (_DWORD)v33 != 5 )
            MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v33, 0);
          if ( *(_DWORD *)(a1 + 8) != 5 )
          {
            v56 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              return 0;
            }
            v57 = 23;
            goto LABEL_175;
          }
          v34 = 11 * v4;
          v35 = 1;
          v32 = *(_DWORD *)(a1 + 4) == 1;
          _mm_lfence();
          if ( v32 )
          {
            v36 = HIDWORD(g_FwObjectHandler[v34 + 9]);
            goto LABEL_55;
          }
          v47 = HIDWORD(g_FwObjectHandler[v34 + 9]);
          goto LABEL_76;
        }
        v59 = *(unsigned int *)(a1 + 8);
        if ( (_DWORD)v59 != 5 )
          MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v59, 0);
        if ( *(_DWORD *)(a1 + 8) != 5 )
        {
          v56 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            return 0;
          v57 = 26;
          goto LABEL_175;
        }
        v51 = *(_DWORD *)(a1 + 4) == 1;
        _mm_lfence();
        v52 = LODWORD(g_FwObjectHandler[11 * v4 + 9]);
LABEL_82:
        v48 = *(const unsigned __int16 **)(v52 + a2);
        v49 = *(const unsigned __int16 **)(a1 + 16);
        if ( !v51 )
          return FwQueryOperatorAppPathMatchTraffic(v49, v48);
        return FwQueryOperatorObjectIDEqual(v49, v48);
      }
      v60 = *(unsigned int *)(a1 + 8);
      if ( (_DWORD)v60 != 3 )
        MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v60, 0);
      if ( *(_DWORD *)(a1 + 8) != 3 )
      {
        v56 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          return 0;
        v57 = 25;
        goto LABEL_175;
      }
      _mm_lfence();
      v41 = HIDWORD(g_FwObjectHandler[11 * v4 + 8]);
    }
    else
    {
      v40 = *(unsigned int *)(a1 + 8);
      if ( (_DWORD)v40 != 3 )
        MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v40, 0);
      if ( *(_DWORD *)(a1 + 8) != 3 )
      {
        v56 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          return 0;
        v57 = 20;
        goto LABEL_175;
      }
      _mm_lfence();
      v41 = HIDWORD(g_FwObjectHandler[11 * v4 + 6]);
    }
    v9 = 0;
    v42 = *(_DWORD *)(a1 + 16) == *(_DWORD *)(v41 + a2);
LABEL_64:
    LOBYTE(v9) = v42;
    return v9;
  }
  if ( v8 == 8 )
  {
    v54 = *(unsigned int *)(a1 + 8);
    if ( (_DWORD)v54 != 5 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v54, 0);
    if ( *(_DWORD *)(a1 + 8) != 5 )
    {
      v56 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        return 0;
      v57 = 18;
      goto LABEL_175;
    }
    v51 = *(_DWORD *)(a1 + 4) == 1;
    _mm_lfence();
    v52 = LODWORD(g_FwObjectHandler[11 * v4 + 4]);
    goto LABEL_82;
  }
  v9 = 0;
  if ( !v8 )
  {
    v27 = *(unsigned int *)(a1 + 8);
    if ( (_DWORD)v27 != 3 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v27, 0);
    if ( *(_DWORD *)(a1 + 8) != 3 )
    {
      v56 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        return 0;
      v57 = 10;
      goto LABEL_175;
    }
    _mm_lfence();
    v28 = HIDWORD(g_FwObjectHandler[11 * v4]);
    goto LABEL_32;
  }
  v10 = v8 - 1;
  if ( !v10 )
  {
    v29 = *(unsigned int *)(a1 + 8);
    if ( (_DWORD)v29 != 3 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v29, 0);
    if ( *(_DWORD *)(a1 + 8) != 3 )
    {
      v56 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        return 0;
      v57 = 11;
      goto LABEL_175;
    }
    _mm_lfence();
    v28 = LODWORD(g_FwObjectHandler[11 * v4 + 1]);
LABEL_32:
    LOBYTE(v9) = (*(_DWORD *)(v28 + a2) & *(_DWORD *)(a1 + 16)) != 0;
    return v9;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    v53 = *(unsigned int *)(a1 + 8);
    if ( (_DWORD)v53 != 5 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v53, 0);
    if ( *(_DWORD *)(a1 + 8) != 5 )
    {
      v56 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        return 0;
      v57 = 12;
      goto LABEL_175;
    }
    _mm_lfence();
    v49 = *(const unsigned __int16 **)(a1 + 16);
    v48 = *(const unsigned __int16 **)(LODWORD(g_FwObjectHandler[11 * v4]) + a2);
    return FwQueryOperatorObjectIDEqual(v49, v48);
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    v58 = *(unsigned int *)(a1 + 8);
    if ( (_DWORD)v58 != 4 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v58, 0);
    if ( *(_DWORD *)(a1 + 8) != 4 )
    {
      v56 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        return 0;
      v57 = 13;
      goto LABEL_175;
    }
    if ( !a4 )
    {
      _mm_lfence();
      a4 = *(_QWORD **)(HIDWORD(g_FwObjectHandler[11 * v4 + 5]) + a2);
      if ( !a4 )
        return 0;
    }
    v42 = *(_QWORD *)(a1 + 16) == *a4;
    goto LABEL_64;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v55 = *(unsigned int *)(a1 + 8);
    if ( (_DWORD)v55 != 5 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v55, 0);
    if ( *(_DWORD *)(a1 + 8) != 5 )
    {
      v56 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        return 0;
      v57 = 14;
      goto LABEL_175;
    }
    _mm_lfence();
    v47 = HIDWORD(g_FwObjectHandler[11 * v4 + 1]);
    goto LABEL_76;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    v30 = *(unsigned int *)(a1 + 8);
    if ( (_DWORD)v30 != 2 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v30, 0);
    if ( *(_DWORD *)(a1 + 8) != 2 )
    {
      v56 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        return 0;
      v57 = 15;
      goto LABEL_175;
    }
    _mm_lfence();
    v31 = *(_WORD *)(HIDWORD(g_FwObjectHandler[11 * v4 + 2]) + a2);
    if ( v31 >= 0x100u )
      return 1;
    v32 = *(_WORD *)(a1 + 16) == v31;
LABEL_43:
    if ( v32 )
      return 1;
    return v9;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    v43 = *(unsigned int *)(a1 + 8);
    if ( (_DWORD)v43 != 2 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v43, 0);
    if ( *(_DWORD *)(a1 + 8) == 2 )
    {
      _mm_lfence();
      v44 = *(_WORD *)(HIDWORD(g_FwObjectHandler[11 * v4 + 2]) + a2);
      if ( v44 >= 0x100u )
        return 1;
      if ( v44 == 6 || v44 == 17 )
      {
        v18 = LODWORD(g_FwObjectHandler[11 * v4 + 3]);
        return FwQueryOperatorPortMatchTraffic(*(_WORD *)(a1 + 16), (struct _tag_FW_PORTS *)(a2 + v18));
      }
      return 0;
    }
    v56 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      return 0;
    v57 = 16;
LABEL_175:
    WPP_SF_d(*(_QWORD *)(v56 + 16), v57, WPP_02386b686afe3419827457afd5f67a60_Traceguids, 87);
    return 0;
  }
  if ( v15 != 1 )
    return 0;
  v16 = *(unsigned int *)(a1 + 8);
  if ( (_DWORD)v16 != 2 )
    MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v16, 0);
  if ( *(_DWORD *)(a1 + 8) != 2 )
  {
    v56 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      return 0;
    v57 = 17;
    goto LABEL_175;
  }
  _mm_lfence();
  v17 = *(_WORD *)(HIDWORD(g_FwObjectHandler[11 * v4 + 2]) + a2);
  if ( v17 >= 0x100u )
    return 1;
  if ( v17 != 6 && v17 != 17 )
    return 0;
  v18 = HIDWORD(g_FwObjectHandler[11 * v4 + 3]);
  return FwQueryOperatorPortMatchTraffic(*(_WORD *)(a1 + 16), (struct _tag_FW_PORTS *)(a2 + v18));
}

```

## disassembly

```asm
0x180004810  push    rbx
0x180004812  push    rbp
0x180004813  push    rsi
0x180004814  push    rdi
0x180004815  push    r14
0x180004817  push    r15
0x180004819  sub     rsp, 28h
0x18000481d  movsxd  rbp, r8d
0x180004820  mov     r15d, 5
0x180004826  mov     r14, r9
0x180004829  mov     rsi, rdx
0x18000482c  mov     rbx, rcx
0x18000482f  cmp     ebp, r15d
0x180004832  ja      loc_18000492F
0x180004838  mov     ecx, [rcx]
0x18000483a  cmp     ecx, 8
0x18000483d  jg      loc_1800048E7
0x180004843  jz      loc_180004C0A
0x180004849  xor     edi, edi
0x18000484b  test    ecx, ecx
0x18000484d  jz      loc_18000493E
0x180004853  sub     ecx, 1
0x180004856  jz      loc_180004975
0x18000485c  sub     ecx, 1
0x18000485f  jz      loc_180004B9C
0x180004865  sub     ecx, 1
0x180004868  jz      loc_180004DDF
0x18000486e  sub     ecx, 1
0x180004871  jz      loc_180004C40
0x180004877  sub     ecx, 1
0x18000487a  jz      loc_1800049A0
0x180004880  sub     ecx, 1
0x180004883  jz      loc_180004AC1
0x180004889  cmp     ecx, 1
0x18000488c  jnz     loc_18000492F
0x180004892  mov     edx, [rbx+8]
0x180004895  cmp     edx, 2
0x180004898  jnz     loc_180004CD3
0x18000489e  cmp     dword ptr [rbx+8], 2
0x1800048a2  jnz     loc_180004CE7
0x1800048a8  lfence
0x1800048ab  imul    rdx, rbp, 58h ; 'X'
0x1800048af  lea     r8, g_FwObjectHandler
0x1800048b6  mov     eax, [rdx+r8+14h]
0x1800048bb  movzx   ecx, word ptr [rax+rsi]
0x1800048bf  mov     eax, 100h
0x1800048c4  cmp     cx, ax
0x1800048c7  jnb     loc_180004AFC
0x1800048cd  cmp     cx, 6
0x1800048d1  jz      short loc_1800048DD
0x1800048d3  mov     eax, 11h
0x1800048d8  cmp     cx, ax
0x1800048db  jnz     short loc_18000492F
0x1800048dd  mov     edx, [rdx+r8+1Ch]
0x1800048e2  jmp     loc_180004BF9
0x1800048e7  sub     ecx, 9
0x1800048ea  jz      loc_180004B06
0x1800048f0  sub     ecx, 1
0x1800048f3  jz      loc_180004A87
0x1800048f9  sub     ecx, 1
0x1800048fc  jz      loc_180004A1F
0x180004902  sub     ecx, 1
0x180004905  jz      loc_180004B5F
0x18000490b  sub     ecx, 1
0x18000490e  jz      loc_180005053
0x180004914  sub     ecx, 1
0x180004917  jz      loc_180004FEF
0x18000491d  sub     ecx, 1
0x180004920  jz      loc_180004F83
0x180004926  cmp     ecx, 1
0x180004929  jz      loc_1800049E6
0x18000492f  xor     eax, eax
0x180004931  add     rsp, 28h
0x180004935  pop     r15
0x180004937  pop     r14
0x180004939  pop     rdi
0x18000493a  pop     rsi
0x18000493b  pop     rbp
0x18000493c  pop     rbx
0x18000493d  retn
0x18000493e  mov     edx, [rbx+8]
0x180004941  cmp     edx, 3
0x180004944  jnz     loc_180004C9A
0x18000494a  cmp     dword ptr [rbx+8], 3
0x18000494e  jnz     loc_180004ECE
0x180004954  lfence
0x180004957  imul    rcx, rbp, 58h ; 'X'
0x18000495b  lea     r8, g_FwObjectHandler
0x180004962  mov     eax, [rcx+r8+4]
0x180004967  mov     ecx, [rax+rsi]
0x18000496a  test    [rbx+10h], ecx
0x18000496d  setnz   dil
0x180004971  mov     eax, edi
0x180004973  jmp     short loc_180004931
0x180004975  mov     edx, [rbx+8]
0x180004978  cmp     edx, 3
0x18000497b  jnz     loc_180004CAE
0x180004981  cmp     dword ptr [rbx+8], 3
0x180004985  jnz     loc_180004E9F
0x18000498b  lfence
0x18000498e  imul    rcx, rbp, 58h ; 'X'
0x180004992  lea     r8, g_FwObjectHandler
0x180004999  mov     eax, [rcx+r8+8]
0x18000499e  jmp     short loc_180004967
0x1800049a0  mov     edx, [rbx+8]
0x1800049a3  cmp     edx, 2
0x1800049a6  jnz     loc_180004D59
0x1800049ac  cmp     dword ptr [rbx+8], 2
0x1800049b0  jnz     loc_180004D6D
0x1800049b6  lfence
0x1800049b9  imul    rcx, rbp, 58h ; 'X'
0x1800049bd  lea     r8, g_FwObjectHandler
0x1800049c4  mov     eax, [rcx+r8+14h]
0x1800049c9  movzx   ecx, word ptr [rax+rsi]
0x1800049cd  mov     eax, 100h
0x1800049d2  cmp     cx, ax
0x1800049d5  jnb     loc_180004B3E
0x1800049db  cmp     [rbx+10h], cx
0x1800049df  jnz     short loc_180004971
0x1800049e1  jmp     loc_180004B3E
0x1800049e6  mov     edx, [rbx+8]
0x1800049e9  cmp     edx, r15d
0x1800049ec  jnz     loc_180004F40
0x1800049f2  cmp     [rbx+8], r15d
0x1800049f6  jnz     loc_180004F54
0x1800049fc  imul    rcx, rbp, 58h ; 'X'
0x180004a00  mov     edx, 1
0x180004a05  lea     r8, g_FwObjectHandler
0x180004a0c  cmp     [rbx+4], edx
0x180004a0f  lfence
0x180004a12  jnz     loc_180004B48
0x180004a18  mov     eax, [rcx+r8+4Ch]
0x180004a1d  jmp     short loc_180004A56
0x180004a1f  mov     edx, [rbx+8]
0x180004a22  cmp     edx, r15d
0x180004a25  jnz     loc_180005102
0x180004a2b  cmp     [rbx+8], r15d
0x180004a2f  jnz     loc_180005116
0x180004a35  imul    rcx, rbp, 58h ; 'X'
0x180004a39  mov     edx, 1
0x180004a3e  lea     r8, g_FwObjectHandler
0x180004a45  cmp     [rbx+4], edx
0x180004a48  lfence
0x180004a4b  jnz     loc_180004BD6
0x180004a51  mov     eax, [rcx+r8+38h]
0x180004a56  mov     rcx, [rbx+10h]; lpString1
0x180004a5a  xor     edi, edi
0x180004a5c  test    rcx, rcx
0x180004a5f  jz      loc_180004CC2
0x180004a65  cmp     [rax+rsi], rdi
0x180004a69  jz      loc_180004CCC
0x180004a6f  mov     rdx, [rax+rsi]; lpString2
0x180004a73  call    cs:__imp_lstrcmpiW
0x180004a79  test    eax, eax
0x180004a7b  mov     edx, edi
0x180004a7d  setz    dl
0x180004a80  mov     eax, edx
0x180004a82  jmp     loc_180004931
0x180004a87  mov     edx, [rbx+8]
0x180004a8a  cmp     edx, 3
0x180004a8d  jnz     loc_180005142
0x180004a93  cmp     dword ptr [rbx+8], 3
0x180004a97  jnz     loc_180005156
0x180004a9d  lfence
0x180004aa0  imul    rcx, rbp, 58h ; 'X'
0x180004aa4  lea     r8, g_FwObjectHandler
0x180004aab  mov     eax, [rcx+r8+34h]
0x180004ab0  mov     eax, [rax+rsi]
0x180004ab3  xor     edi, edi
0x180004ab5  cmp     [rbx+10h], eax
0x180004ab8  setz    dil
0x180004abc  jmp     loc_180004971
0x180004ac1  mov     edx, [rbx+8]
0x180004ac4  cmp     edx, 2
0x180004ac7  jnz     loc_180004D16
0x180004acd  cmp     dword ptr [rbx+8], 2
0x180004ad1  jnz     loc_180004D2A
0x180004ad7  lfence
0x180004ada  imul    rdx, rbp, 58h ; 'X'
0x180004ade  lea     r8, g_FwObjectHandler
0x180004ae5  mov     eax, [rdx+r8+14h]
0x180004aea  movzx   ecx, word ptr [rax+rsi]
0x180004aee  mov     eax, 100h
0x180004af3  cmp     cx, ax
0x180004af6  jb      loc_180004BE0
0x180004afc  mov     eax, 1
0x180004b01  jmp     loc_180004931
0x180004b06  mov     edx, [rbx+8]
0x180004b09  cmp     edx, r15d
0x180004b0c  jnz     loc_180005182
0x180004b12  cmp     [rbx+8], r15d
0x180004b16  jnz     loc_180005196
0x180004b1c  lfence
0x180004b1f  imul    rcx, rbp, 58h ; 'X'
0x180004b23  lea     r8, g_FwObjectHandler
0x180004b2a  xor     edi, edi
0x180004b2c  mov     eax, [rcx+r8+10h]
0x180004b31  mov     rsi, [rax+rsi]
0x180004b35  test    rsi, rsi
0x180004b38  jnz     loc_180004C6E
0x180004b3e  mov     edi, 1
0x180004b43  jmp     loc_180004971
0x180004b48  mov     edx, [rcx+r8+4Ch]
0x180004b4d  mov     rdx, [rdx+rsi]; unsigned __int16 *
0x180004b51  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180004b55  call    ?FwQueryOperatorAppPathMatchTraffic@@YAHPEBG0@Z; FwQueryOperatorAppPathMatchTraffic(ushort const *,ushort const *)
0x180004b5a  jmp     loc_180004931
0x180004b5f  mov     edx, [rbx+8]
0x180004b62  cmp     edx, r15d
0x180004b65  jnz     loc_1800050BF
0x180004b6b  cmp     [rbx+8], r15d
0x180004b6f  jnz     loc_1800050D3
0x180004b75  imul    rcx, rbp, 58h ; 'X'
0x180004b79  mov     edx, 1
0x180004b7e  lea     r8, g_FwObjectHandler
0x180004b85  cmp     [rbx+4], edx
0x180004b88  lfence
0x180004b8b  mov     edx, [rcx+r8+3Ch]
0x180004b90  mov     rdx, [rdx+rsi]
0x180004b94  mov     rcx, [rbx+10h]
0x180004b98  jnz     short loc_180004B55
0x180004b9a  jmp     short loc_180004BCC
0x180004b9c  mov     edx, [rbx+8]
0x180004b9f  cmp     edx, r15d
0x180004ba2  jnz     loc_180004E5C
0x180004ba8  cmp     [rbx+8], r15d
0x180004bac  jnz     loc_180004E70
0x180004bb2  lfence
0x180004bb5  imul    rcx, rbp, 58h ; 'X'
0x180004bb9  lea     r8, g_FwObjectHandler
0x180004bc0  mov     edx, [rcx+r8]
0x180004bc4  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180004bc8  mov     rdx, [rdx+rsi]; unsigned __int16 *
0x180004bcc  call    ?FwQueryOperatorObjectIDEqual@@YAHPEBG0@Z; FwQueryOperatorObjectIDEqual(ushort const *,ushort const *)
0x180004bd1  jmp     loc_180004931
0x180004bd6  mov     edx, [rcx+r8+38h]
0x180004bdb  jmp     loc_180004B4D
0x180004be0  cmp     cx, 6
0x180004be4  jz      short loc_180004BF4
0x180004be6  mov     eax, 11h
0x180004beb  cmp     cx, ax
0x180004bee  jnz     loc_18000492F
0x180004bf4  mov     edx, [rdx+r8+18h]
0x180004bf9  movzx   ecx, word ptr [rbx+10h]; unsigned __int16
0x180004bfd  add     rdx, rsi; struct _tag_FW_PORTS *
0x180004c00  call    ?FwQueryOperatorPortMatchTraffic@@YAHGPEAU_tag_FW_PORTS@@@Z; FwQueryOperatorPortMatchTraffic(ushort,_tag_FW_PORTS *)
0x180004c05  jmp     loc_180004931
0x180004c0a  mov     edx, [rbx+8]
0x180004c0d  cmp     edx, r15d
0x180004c10  jnz     loc_180004EFD
0x180004c16  cmp     [rbx+8], r15d
0x180004c1a  jnz     loc_180004F11
0x180004c20  imul    rcx, rbp, 58h ; 'X'
0x180004c24  mov     edx, 1
0x180004c29  lea     r8, g_FwObjectHandler
0x180004c30  cmp     [rbx+4], edx
0x180004c33  lfence
0x180004c36  mov     edx, [rcx+r8+20h]
0x180004c3b  jmp     loc_180004B90
0x180004c40  mov     edx, [rbx+8]
0x180004c43  cmp     edx, r15d
0x180004c46  jnz     loc_180004D9C
0x180004c4c  cmp     [rbx+8], r15d
0x180004c50  jnz     loc_180004DB0
0x180004c56  lfence
0x180004c59  imul    rcx, rbp, 58h ; 'X'
0x180004c5d  lea     r8, g_FwObjectHandler
0x180004c64  mov     edx, [rcx+r8+0Ch]
0x180004c69  jmp     loc_180004B4D
0x180004c6e  mov     rcx, [rbx+10h]; lpString1
0x180004c72  mov     rdx, rsi; lpString2
0x180004c75  call    cs:__imp_lstrcmpiW
0x180004c7b  test    eax, eax
0x180004c7d  jz      loc_180004B3E
0x180004c83  mov     rdx, rsi; lpString2
0x180004c86  lea     rcx, String1; "*"
0x180004c8d  call    cs:__imp_lstrcmpiW
0x180004c93  test    eax, eax
0x180004c95  jmp     loc_1800049DF
0x180004c9a  xor     r8d, r8d
0x180004c9d  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180004ca4  call    MicrosoftTelemetryAssertTriggeredArgs
0x180004ca9  jmp     loc_18000494A
0x180004cae  xor     r8d, r8d
0x180004cb1  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180004cb8  call    MicrosoftTelemetryAssertTriggeredArgs
0x180004cbd  jmp     loc_180004981
0x180004cc2  cmp     [rax+rsi], rdi
0x180004cc6  jz      loc_180004A80
0x180004ccc  mov     edx, edi
0x180004cce  jmp     loc_180004A80
0x180004cd3  xor     r8d, r8d
0x180004cd6  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180004cdd  call    MicrosoftTelemetryAssertTriggeredArgs
0x180004ce2  jmp     loc_18000489E
0x180004ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cee  lea     rax, WPP_GLOBAL_Control
0x180004cf5  cmp     rcx, rax
0x180004cf8  jz      loc_18000492F
0x180004cfe  mov     edx, 1
  ... truncated ...
```
