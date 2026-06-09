# I_GetDefaultCngContainer

- ea: `0x18000a050`
- end: `0x18000a975`
- name: `I_GetDefaultCngContainer`
- size: `2341`
- prototype: `__int64 __fastcall(_QWORD *, BYTE **)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180010d90`

## callees

- `0x180004600`
- `0x180006010`
- `0x18000a050`
- `0x18000a980`
- `0x18000af90`
- `0x18000b010`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`
- `0x180024380`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a344`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a344`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a8d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a8d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a084`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a3bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a472`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a084`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a3bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a472`
- `ncrypt!NCryptFreeObject` at `0x18000a46c`
- `ncrypt!NCryptFreeObject` at `0x18000a46c`
- `ncrypt!NCryptGetProperty` at `0x18000a323`
- `ncrypt!NCryptGetProperty` at `0x18000a379`
- `ncrypt!NCryptGetProperty` at `0x18000a323`
- `ncrypt!NCryptGetProperty` at `0x18000a379`
- `ncrypt!NCryptOpenKey` at `0x18000a2f0`
- `ncrypt!NCryptOpenKey` at `0x18000a2f0`

## pseudocode

```c
__int64 __fastcall I_GetDefaultCngContainer(_QWORD *a1, BYTE **a2)
{
  WCHAR *p_pcbResult; // rbx
  DWORD CurrentThreadId; // eax
  char *v5; // rcx
  int v6; // r8d
  size_t *v7; // rdx
  int v8; // r13d
  const char *v9; // r9
  int v10; // r11d
  STRSAFE_LPSTR v11; // r10
  unsigned int Property; // r15d
  __int64 v13; // r14
  char *v14; // r8
  __int64 v15; // rcx
  char *v16; // rax
  __int64 v17; // rax
  size_t *v18; // rax
  __int64 v19; // rax
  unsigned __int64 v20; // rdi
  unsigned __int64 v21; // rcx
  WCHAR *v22; // rax
  int v23; // r10d
  bool v24; // zf
  int v25; // edx
  __int64 v26; // rdx
  __int64 v27; // rcx
  DWORD v28; // edi
  __int64 v29; // rcx
  __int64 v30; // rcx
  BYTE *v31; // rsi
  __int64 v32; // rcx
  DWORD v33; // eax
  size_t i; // rdx
  unsigned __int64 v35; // rcx
  int v36; // r10d
  int v37; // esi
  DWORD v38; // eax
  char *j; // rcx
  int v40; // r10d
  size_t v41; // rdx
  int v42; // ebx
  STRSAFE_LPSTR v43; // r11
  char *v44; // rax
  char *v45; // r12
  const char *v46; // rax
  __int64 v47; // rdx
  char *v48; // rax
  __int64 v50; // rcx
  bool v51; // zf
  int v52; // r8d
  unsigned int v53; // r10d
  bool v54; // zf
  int v55; // r9d
  __int64 v56; // rcx
  void *v57; // rsp
  void *v58; // rsp
  int v59; // ebx
  int v60; // r11d
  int v61; // r10d
  int v62; // r11d
  STRSAFE_LPSTR v63; // rcx
  int v64; // edx
  char v65; // al
  __int64 v66; // [rsp+0h] [rbp-30h] BYREF
  DWORD dwFlags[2]; // [rsp+20h] [rbp-10h]
  DWORD pcbResult; // [rsp+30h] [rbp+0h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+38h] [rbp+8h] BYREF
  BYTE **v70; // [rsp+40h] [rbp+10h]

  p_pcbResult = 0;
  v70 = a2;
  pcbResult = 0;
  phKey = 0;
  CurrentThreadId = GetCurrentThreadId();
  v6 = `WppTraceIndent'::`2'::idxCurrentThread;
  v7 = &`WppTraceIndent'::`2'::ThreadTable;
  v8 = -1;
  v9 = (const char *)CurrentThreadId;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v6 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = CurrentThreadId;
    dword_180031404 = 0;
LABEL_7:
    v10 = ++*((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v6 + 1);
    goto LABEL_8;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread != -2
    && *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) == CurrentThreadId )
  {
    goto LABEL_4;
  }
  v23 = -1;
  v5 = 0;
  while ( 1 )
  {
    v24 = (_DWORD)v5 == 32;
    if ( (unsigned int)v5 >= 0x20 )
      break;
    v25 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)v5);
    if ( v25 == CurrentThreadId )
    {
      v6 = (int)v5;
      `WppTraceIndent'::`2'::idxCurrentThread = (int)v5;
      v7 = &`WppTraceIndent'::`2'::ThreadTable;
      v24 = (_DWORD)v5 == 32;
      break;
    }
    if ( v23 == -1 && !v25 )
      v23 = (int)v5;
    v5 = (char *)(unsigned int)((_DWORD)v5 + 1);
    v7 = &`WppTraceIndent'::`2'::ThreadTable;
  }
  if ( !v24 )
  {
LABEL_4:
    if ( v6 < 0 )
    {
      v10 = 0;
      goto LABEL_8;
    }
    goto LABEL_7;
  }
  if ( v23 != -1 )
  {
    v6 = v23;
    `WppTraceIndent'::`2'::idxCurrentThread = v23;
    *(&`WppTraceIndent'::`2'::ThreadTable + v23) = CurrentThreadId;
    goto LABEL_4;
  }
  `WppTraceIndent'::`2'::idxCurrentThread = -2;
  v10 = 0;
LABEL_8:
  v11 = WPP_GLOBAL_Control;
  Property = 0;
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (WPP_GLOBAL_Control[28] & 2) != 0 && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    v59 = 1;
    if ( v10 >= 1 )
    {
      do
      {
        if ( StringCbCatA(v5, (size_t)v7, "..") )
          break;
        ++v59;
      }
      while ( v59 <= v60 );
      v11 = WPP_GLOBAL_Control;
    }
    p_pcbResult = 0;
  }
  v13 = 256;
  v14 = &`WppTraceIndent'::`2'::szIndentPrefix;
  v15 = 256;
  v16 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( *v16 )
  {
    ++v16;
    if ( !--v15 )
      goto LABEL_18;
  }
  v9 = ">";
  v7 = (size_t *)((char *)HotPatchSpareGlobals - v15);
  v17 = 2147483646;
  do
  {
    if ( !v17 )
      break;
    if ( !*v9 )
      break;
    *(_BYTE *)v7 = *v9++;
    v7 = (size_t *)((char *)v7 + 1);
    --v17;
    --v15;
  }
  while ( v15 );
  v14 = &`WppTraceIndent'::`2'::szIndentPrefix;
  v18 = (size_t *)((char *)v7 - 1);
  if ( v15 )
    v18 = v7;
  *(_BYTE *)v18 = 0;
LABEL_18:
  WPP_pszIndent = (__int64)&`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v11 != (STRSAFE_LPSTR)&WPP_GLOBAL_Control && (v11[28] & 2) != 0 && (unsigned __int8)v11[25] >= 5u )
    WPP_SF_s(
      *((_QWORD *)v11 + 2),
      121,
      &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      &`WppTraceIndent'::`2'::szIndentPrefix);
  v19 = -1;
  do
    v24 = *(_WORD *)(*a1 + 2 * v19++ + 2) == 0;
  while ( !v24 );
  v20 = 2 * v19 + 12;
  if ( 2 * v19 == -12 )
    goto LABEL_169;
  if ( v20 > g_ulMaxStackAllocSize )
    goto LABEL_169;
  v21 = v20 + g_ulAdditionalProbeSize + 8;
  if ( v21 < v20 || !(unsigned int)VerifyStackAvailable(v21, v7, v14) )
    goto LABEL_169;
  v56 = v20 + 23;
  if ( v20 + 23 <= v20 + 8 )
    v56 = 0xFFFFFFFFFFFFFF0LL;
  v57 = alloca(v56 & 0xFFFFFFFFFFFFFFF0uLL);
  v58 = alloca(v56 & 0xFFFFFFFFFFFFFFF0uLL);
  p_pcbResult = (WCHAR *)&pcbResult;
  if ( &v66 == (__int64 *)-48LL || (pcbResult = 1801679955, (p_pcbResult = (WCHAR *)&phKey) == 0) )
  {
LABEL_169:
    if ( v20 + 8 >= v20 )
    {
      v22 = (WCHAR *)((__int64 (__fastcall *)(unsigned __int64, size_t *, char *, const char *))g_pfnAllocate)(
                       v20 + 8,
                       v7,
                       v14,
                       v9);
      p_pcbResult = v22;
      if ( v22 )
      {
        *(_DWORD *)v22 = 1885431112;
        p_pcbResult = v22 + 4;
      }
    }
  }
  if ( !p_pcbResult )
  {
    v33 = GetCurrentThreadId();
    v35 = `WppTraceIndent'::`2'::idxCurrentThread;
    if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
    {
      v35 = 0;
      LODWORD(`WppTraceIndent'::`2'::ThreadTable) = v33;
      `WppTraceIndent'::`2'::idxCurrentThread = 0;
      dword_180031404 = 0;
    }
    else
    {
      if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
        || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != v33 )
      {
        v53 = -1;
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          v54 = (_DWORD)i == 32;
          if ( (unsigned int)i >= 0x20 )
            break;
          v55 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)i);
          if ( v55 == v33 )
          {
            v35 = (unsigned int)i;
            `WppTraceIndent'::`2'::idxCurrentThread = i;
            v54 = (_DWORD)i == 32;
            break;
          }
          if ( v53 == -1 && !v55 )
            v53 = i;
        }
        if ( v54 )
        {
          if ( v53 == -1 )
          {
            `WppTraceIndent'::`2'::idxCurrentThread = -2;
            v36 = 0;
LABEL_61:
            v37 = 1;
            `WppTraceIndent'::`2'::szIndentPrefix = 0;
            if ( (WPP_GLOBAL_Control[28] & 2) != 0 && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u && v36 >= 1 )
            {
              while ( !StringCbCatA((STRSAFE_LPSTR)v35, i, "..") && v62 + 1 <= v61 )
                ;
            }
            StringCbCatA((STRSAFE_LPSTR)v35, i, " ");
            v28 = 8;
            WPP_pszIndent = (__int64)&`WppTraceIndent'::`2'::szIndentPrefix;
            if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[28] & 1) != 0
              && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                122,
                &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
                &`WppTraceIndent'::`2'::szIndentPrefix);
            }
            goto LABEL_63;
          }
          v35 = v53;
          `WppTraceIndent'::`2'::idxCurrentThread = v53;
          *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)v53) = v33;
          *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)v53 + 1) = 0;
        }
      }
      if ( (v35 & 0x80000000) != 0LL )
      {
        v36 = 0;
        goto LABEL_61;
      }
    }
    v36 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)v35 + 1);
    goto LABEL_61;
  }
  v26 = -1;
  do
    ++v26;
  while ( *(_WORD *)(*a1 + 2 * v26) );
  if ( StringCchPrintfW(p_pcbResult, v26 + 6, L"\\\\.\\%s\\") < 0 )
  {
    v28 = 0;
    Property = 8;
  }
  else
  {
    v28 = I_SetupNCryptStorageProvider((__int64)a1);
    if ( v28 )
    {
      WppTraceIndent(v27, 2);
      v63 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_154;
      }
      v64 = 123;
      dwFlags[0] = v28;
      goto LABEL_140;
    }
    Property = NCryptOpenKey(a1[17], &phKey, p_pcbResult, 0, 0x40u);
    if ( !Property )
    {
      Property = NCryptGetProperty(phKey, L"Unique Name", 0, 0, &pcbResult, 0x40u);
      if ( !Property )
      {
        v31 = (BYTE *)HeapAlloc(hHeap, 8u, pcbResult);
        if ( v31 )
        {
          Property = NCryptGetProperty(phKey, L"Unique Name", v31, pcbResult, &pcbResult, 0x40u);
          if ( Property )
          {
            WppTraceIndent(v32, 2);
            if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[28] & 1) != 0
              && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
            {
              WPP_SF_sD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                126,
                (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
                WPP_pszIndent,
                Property);
            }
            HeapFree(hHeap, 0, v31);
          }
          else
          {
            *v70 = v31;
          }
        }
        else
        {
          WppTraceIndent(v30, 2);
          v28 = 8;
          if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[28] & 1) != 0
            && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              125,
              &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
              WPP_pszIndent);
          }
        }
        goto LABEL_154;
      }
      WppTraceIndent(v29, 2);
      v63 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        v64 = 124;
        dwFlags[0] = Property;
LABEL_140:
        WPP_SF_sD(
          *((_QWORD *)v63 + 2),
          v64,
          (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent,
          dwFlags[0]);
      }
    }
  }
LABEL_154:
  if ( *((_DWORD *)p_pcbResult - 2) == 1885431112 )
    ((void (__fastcall *)(WCHAR *))g_pfnFree)(p_pcbResult - 4);
  v37 = 1;
LABEL_63:
  if ( phKey )
    NCryptFreeObject(phKey);
  v38 = GetCurrentThreadId();
  v40 = `WppTraceIndent'::`2'::idxCurrentThread;
  v41 = v38;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v40 = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = v38;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    dword_180031404 = 0;
LABEL_71:
    v42 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v40 + 1);
    goto LABEL_72;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread != -2
    && *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) == v38 )
  {
    goto LABEL_68;
  }
  for ( j = 0; ; j = (char *)(unsigned int)((_DWORD)j + 1) )
  {
    v51 = (_DWORD)j == 32;
    if ( (unsigned int)j >= 0x20 )
      break;
    v52 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)j);
    if ( v52 == v38 )
    {
      v40 = (int)j;
      `WppTraceIndent'::`2'::idxCurrentThread = (int)j;
      v51 = (_DWORD)j == 32;
      break;
    }
    if ( v8 == -1 && !v52 )
      v8 = (int)j;
  }
  if ( !v51 )
  {
LABEL_68:
    if ( v40 < 0 )
    {
      v42 = 0;
      goto LABEL_72;
    }
    goto LABEL_71;
  }
  if ( v8 != -1 )
  {
    v40 = v8;
    `WppTraceIndent'::`2'::idxCurrentThread = v8;
    *(&`WppTraceIndent'::`2'::ThreadTable + v8) = v38;
    goto LABEL_68;
  }
  v40 = -2;
  v42 = 0;
  `WppTraceIndent'::`2'::idxCurrentThread = -2;
LABEL_72:
  v43 = WPP_GLOBAL_Control;
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (WPP_GLOBAL_Control[28] & 2) != 0 && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u && v42 >= 1 )
  {
    do
    {
      if ( StringCbCatA(j, v41, "..") )
        break;
      ++v37;
    }
    while ( v37 <= v42 );
    v43 = WPP_GLOBAL_Control;
  }
  v44 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( *v44 )
  {
    ++v44;
    if ( !--v13 )
      goto LABEL_82;
  }
  v45 = (char *)HotPatchSpareGlobals - v13;
  v46 = "<";
  v47 = 2147483646;
  do
  {
    if ( !v47 )
      break;
    if ( !*v46 )
      break;
    *v45++ = *v46++;
    --v47;
    --v13;
  }
  while ( v13 );
  v48 = v45 - 1;
  if ( v13 )
    v48 = v45;
  *v48 = 0;
LABEL_82:
  if ( v40 >= 0 )
  {
    v50 = 8LL * v40;
    v24 = (*(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v50 + 4))-- == 1;
    if ( v24 )
      *(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v50) = 0;
  }
  WPP_pszIndent = (__int64)&`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v43 != (STRSAFE_LPSTR)&WPP_GLOBAL_Control && (v43[28] & 2) != 0 && (unsigned __int8)v43[25] >= 5u )
  {
    v65 = Property;
    if ( v28 )
      v65 = v28;
    WPP_SF_sD(
      *((_QWORD *)v43 + 2),
      127,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      (unsigned int)&`WppTraceIndent'::`2'::szIndentPrefix,
      v65);
  }
  if ( v28 )
    return v28;
  return Property;
}

```

## disassembly

```asm
0x18000a050  push    rbp
0x18000a052  push    rbx
0x18000a053  push    rsi
0x18000a054  push    rdi
0x18000a055  push    r12
0x18000a057  push    r13
0x18000a059  push    r14
0x18000a05b  push    r15
0x18000a05d  sub     rsp, 68h
0x18000a061  lea     rbp, [rsp+30h]
0x18000a066  mov     rax, cs:__security_cookie
0x18000a06d  xor     rax, rbp
0x18000a070  mov     [rbp+70h+var_50], rax
0x18000a074  xor     ebx, ebx
0x18000a076  mov     [rbp+70h+var_60], rdx
0x18000a07a  mov     [rbp+70h+pcbResult], ebx
0x18000a07d  mov     rsi, rcx
0x18000a080  mov     [rbp+70h+phKey], rbx
0x18000a084  call    cs:__imp_GetCurrentThreadId
0x18000a08a  movsxd  r8, cs:?idxCurrentThread@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::idxCurrentThread
0x18000a091  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@9@9; cbDest
0x18000a098  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000a09f  mov     r9d, eax
0x18000a0a2  cmp     r8d, r13d
0x18000a0a5  jz      short loc_18000A0C5
0x18000a0a7  cmp     r8d, 0FFFFFFFEh
0x18000a0ab  jz      loc_18000A206
0x18000a0b1  cmp     [rdx+r8*8], eax
0x18000a0b5  jnz     loc_18000A206
0x18000a0bb  test    r8d, r8d
0x18000a0be  jns     short loc_18000A0DB
0x18000a0c0  mov     r11d, ebx
0x18000a0c3  jmp     short loc_18000A0E7
0x18000a0c5  mov     r8d, ebx
0x18000a0c8  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ebx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000a0ce  mov     cs:?ThreadTable@?1??WppTraceIndent@@9@9, r9d; `WppTraceIndent'::`2'::ThreadTable
0x18000a0d5  mov     cs:dword_180031404, ebx
0x18000a0db  movsxd  rax, r8d
0x18000a0de  inc     dword ptr [rdx+rax*8+4]
0x18000a0e2  mov     r11d, [rdx+rax*8+4]
0x18000a0e7  mov     r10, cs:WPP_GLOBAL_Control
0x18000a0ee  mov     r15d, ebx
0x18000a0f1  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@9@9, bl; `WppTraceIndent'::`2'::szIndentPrefix
0x18000a0f7  test    byte ptr [r10+1Ch], 2
0x18000a0fc  jnz     loc_18000A6B3
0x18000a102  mov     r14d, 100h
0x18000a108  lea     r8, ?szIndentPrefix@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::szIndentPrefix
0x18000a10f  mov     ecx, r14d
0x18000a112  mov     rax, r8
0x18000a115  lea     r12, HotPatchSpareGlobals
0x18000a11c  cmp     [rax], r15b
0x18000a11f  jnz     loc_18000A280
0x18000a125  mov     rdx, r12
0x18000a128  lea     r9, asc_180027E34; ">"
0x18000a12f  sub     rdx, rcx
0x18000a132  mov     eax, 7FFFFFFEh
0x18000a137  test    rcx, rcx
0x18000a13a  jz      short loc_18000A163
0x18000a13c  test    rax, rax
0x18000a13f  jz      short loc_18000A15C
0x18000a141  movzx   r8d, byte ptr [r9]
0x18000a145  test    r8b, r8b
0x18000a148  jz      short loc_18000A15C
0x18000a14a  mov     [rdx], r8b
0x18000a14d  inc     r9
0x18000a150  inc     rdx
0x18000a153  dec     rax
0x18000a156  sub     rcx, 1
0x18000a15a  jnz     short loc_18000A13C
0x18000a15c  lea     r8, ?szIndentPrefix@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::szIndentPrefix
0x18000a163  test    rcx, rcx
0x18000a166  lea     rax, [rdx-1]
0x18000a16a  cmovnz  rax, rdx
0x18000a16e  mov     [rax], r15b
0x18000a171  mov     cs:WPP_pszIndent, r8
0x18000a178  lea     rax, WPP_GLOBAL_Control
0x18000a17f  cmp     r10, rax
0x18000a182  jnz     loc_18000A6ED
0x18000a188  mov     rcx, [rsi]
0x18000a18b  mov     rax, r13
0x18000a18e  xchg    ax, ax
0x18000a190  cmp     [rcx+rax*2+2], r15w
0x18000a196  lea     rax, [rax+1]
0x18000a19a  jnz     short loc_18000A190
0x18000a19c  lea     rdi, ds:0Ch[rax*2]
0x18000a1a4  test    rdi, rdi
0x18000a1a7  jz      short loc_18000A1D2
0x18000a1a9  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18000a1b0  ja      short loc_18000A1D2
0x18000a1b2  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000a1b9  add     rcx, 8
0x18000a1bd  add     rcx, rdi
0x18000a1c0  cmp     rcx, rdi
0x18000a1c3  jb      short loc_18000A1D2
0x18000a1c5  call    VerifyStackAvailable
0x18000a1ca  test    eax, eax
0x18000a1cc  jnz     loc_18000A67A
0x18000a1d2  lea     rcx, [rdi+8]
0x18000a1d6  cmp     rcx, rdi
0x18000a1d9  jb      loc_18000A3B3
0x18000a1df  mov     rax, cs:g_pfnAllocate
0x18000a1e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1eb  mov     rbx, rax
0x18000a1ee  test    rax, rax
0x18000a1f1  jz      loc_18000A3B3
0x18000a1f7  mov     dword ptr [rax], 70616548h
0x18000a1fd  add     rbx, 8
0x18000a201  jmp     loc_18000A3B3
0x18000a206  mov     r10d, r13d
0x18000a209  mov     ecx, ebx
0x18000a20b  nop     dword ptr [rax+rax+00h]
0x18000a210  cmp     ecx, 20h ; ' '
0x18000a213  jnb     short loc_18000A249
0x18000a215  movsxd  rax, ecx
0x18000a218  mov     edx, [rdx+rax*8]
0x18000a21b  cmp     edx, r9d
0x18000a21e  jz      short loc_18000A236
0x18000a220  cmp     r10d, r13d
0x18000a223  jnz     short loc_18000A22B
0x18000a225  test    edx, edx
0x18000a227  cmovz   r10d, ecx
0x18000a22b  inc     ecx
0x18000a22d  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::ThreadTable
0x18000a234  jmp     short loc_18000A210
0x18000a236  mov     r8d, ecx
0x18000a239  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ecx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000a23f  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::ThreadTable
0x18000a246  cmp     ecx, 20h ; ' '
0x18000a249  jnz     loc_18000A0BB
0x18000a24f  cmp     r10d, r13d
0x18000a252  jnz     short loc_18000A266
0x18000a254  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, 0FFFFFFFEh; `WppTraceIndent'::`2'::idxCurrentThread
0x18000a25e  mov     r11d, ebx
0x18000a261  jmp     loc_18000A0E7
0x18000a266  movsxd  rax, r10d
0x18000a269  mov     r8d, r10d
0x18000a26c  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, r10d; `WppTraceIndent'::`2'::idxCurrentThread
0x18000a273  mov     [rdx+rax*8], r9d
0x18000a277  mov     [rdx+rax*8+4], ebx
0x18000a27b  jmp     loc_18000A0BB
0x18000a280  inc     rax
0x18000a283  sub     rcx, 1
0x18000a287  jnz     loc_18000A115
0x18000a28d  jmp     loc_18000A171
0x18000a292  mov     r9, [rsi]
0x18000a295  mov     rdx, r13
0x18000a298  nop     dword ptr [rax+rax+00000000h]
0x18000a2a0  inc     rdx
0x18000a2a3  cmp     [r9+rdx*2], r15w
0x18000a2a8  jnz     short loc_18000A2A0
0x18000a2aa  add     rdx, 6; cchDest
0x18000a2ae  lea     r8, aS_0; "\\\\.\\%s\\"
0x18000a2b5  mov     rcx, rbx; pszDest
0x18000a2b8  call    StringCchPrintfW
0x18000a2bd  test    eax, eax
0x18000a2bf  js      loc_18000A396
0x18000a2c5  mov     rcx, rsi
0x18000a2c8  call    I_SetupNCryptStorageProvider
0x18000a2cd  mov     edi, eax
0x18000a2cf  test    eax, eax
0x18000a2d1  jnz     loc_18000A785
0x18000a2d7  mov     rcx, [rsi+88h]; hProvider
0x18000a2de  lea     rdx, [rbp+70h+phKey]; phKey
0x18000a2e2  xor     r9d, r9d; dwLegacyKeySpec
0x18000a2e5  mov     [rsp+0A0h+dwFlags], 40h ; '@'; dwFlags
0x18000a2ed  mov     r8, rbx; pszKeyName
0x18000a2f0  call    cs:__imp_NCryptOpenKey
0x18000a2f6  mov     r15d, eax
0x18000a2f9  test    eax, eax
0x18000a2fb  jnz     loc_18000A8D6
0x18000a301  mov     rcx, [rbp+70h+phKey]; hObject
0x18000a305  lea     rax, [rbp+70h+pcbResult]
0x18000a309  mov     [rsp+0A0h+var_78], 40h ; '@'; dwFlags
0x18000a311  lea     rdx, aUniqueName; "Unique Name"
0x18000a318  xor     r9d, r9d; cbOutput
0x18000a31b  mov     qword ptr [rsp+0A0h+dwFlags], rax; pcbResult
0x18000a320  xor     r8d, r8d; pbOutput
0x18000a323  call    cs:__imp_NCryptGetProperty
0x18000a329  mov     r15d, eax
0x18000a32c  test    eax, eax
0x18000a32e  jnz     loc_18000A7EB
0x18000a334  mov     r8d, [rbp+70h+pcbResult]; dwBytes
0x18000a338  mov     edx, 8; dwFlags
0x18000a33d  mov     rcx, cs:hHeap; hHeap
0x18000a344  call    cs:__imp_HeapAlloc
0x18000a34a  mov     rsi, rax
0x18000a34d  test    rax, rax
0x18000a350  jz      loc_18000A822
0x18000a356  mov     r9d, [rbp+70h+pcbResult]; cbOutput
0x18000a35a  lea     rax, [rbp+70h+pcbResult]
0x18000a35e  mov     rcx, [rbp+70h+phKey]; hObject
0x18000a362  lea     rdx, aUniqueName; "Unique Name"
0x18000a369  mov     [rsp+0A0h+var_78], 40h ; '@'; dwFlags
0x18000a371  mov     r8, rsi; pbOutput
0x18000a374  mov     qword ptr [rsp+0A0h+dwFlags], rax; pcbResult
0x18000a379  call    cs:__imp_NCryptGetProperty
0x18000a37f  mov     r15d, eax
0x18000a382  test    eax, eax
0x18000a384  jnz     loc_18000A87A
0x18000a38a  mov     rax, [rbp+70h+var_60]
0x18000a38e  mov     [rax], rsi
0x18000a391  jmp     loc_18000A8D6
0x18000a396  xor     edi, edi
0x18000a398  mov     r15d, 8
0x18000a39e  jmp     loc_18000A8D6
0x18000a3a3  mov     dword ptr [rbx], 6B637453h
0x18000a3a9  add     rbx, 8
0x18000a3ad  jz      loc_18000A1D2
0x18000a3b3  test    rbx, rbx
0x18000a3b6  jnz     loc_18000A292
0x18000a3bc  call    cs:__imp_GetCurrentThreadId
0x18000a3c2  movsxd  rcx, cs:?idxCurrentThread@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::idxCurrentThread
0x18000a3c9  lea     rbx, ?ThreadTable@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::ThreadTable
0x18000a3d0  mov     r8d, eax
0x18000a3d3  cmp     ecx, r13d
0x18000a3d6  jz      short loc_18000A3F3
0x18000a3d8  cmp     ecx, 0FFFFFFFEh
0x18000a3db  jz      loc_18000A5E3
0x18000a3e1  cmp     [rbx+rcx*8], eax
0x18000a3e4  jnz     loc_18000A5E3
0x18000a3ea  test    ecx, ecx
0x18000a3ec  jns     short loc_18000A408
0x18000a3ee  xor     r10d, r10d
0x18000a3f1  jmp     short loc_18000A410
0x18000a3f3  xor     ecx, ecx; pszDest
0x18000a3f5  mov     cs:?ThreadTable@?1??WppTraceIndent@@9@9, r8d; `WppTraceIndent'::`2'::ThreadTable
0x18000a3fc  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ecx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000a402  mov     cs:dword_180031404, ecx
0x18000a408  movsxd  rax, ecx
0x18000a40b  mov     r10d, [rbx+rax*8+4]
0x18000a410  mov     rax, cs:WPP_GLOBAL_Control
0x18000a417  mov     esi, 1
0x18000a41c  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@9@9, r15b; `WppTraceIndent'::`2'::szIndentPrefix
0x18000a423  test    byte ptr [rax+1Ch], 2
0x18000a427  jnz     loc_18000A720
0x18000a42d  lea     r8, asc_180027F18; " "
0x18000a434  call    StringCbCatA
0x18000a439  lea     r9, ?szIndentPrefix@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::szIndentPrefix
0x18000a440  mov     edi, 8
0x18000a445  mov     cs:WPP_pszIndent, r9
0x18000a44c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a453  lea     rax, WPP_GLOBAL_Control
0x18000a45a  cmp     rcx, rax
0x18000a45d  jnz     loc_18000A757
0x18000a463  mov     rcx, [rbp+70h+phKey]; hObject
0x18000a467  test    rcx, rcx
0x18000a46a  jz      short loc_18000A472
0x18000a46c  call    cs:__imp_NCryptFreeObject
0x18000a472  call    cs:__imp_GetCurrentThreadId
0x18000a478  movsxd  r10, cs:?idxCurrentThread@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::idxCurrentThread
0x18000a47f  mov     edx, eax; cbDest
0x18000a481  cmp     r10d, r13d
0x18000a484  jz      short loc_18000A4A3
0x18000a486  cmp     r10d, 0FFFFFFFEh
0x18000a48a  jz      loc_18000A593
0x18000a490  cmp     [rbx+r10*8], eax
0x18000a494  jnz     loc_18000A593
0x18000a49a  test    r10d, r10d
0x18000a49d  jns     short loc_18000A4BA
0x18000a49f  xor     ebx, ebx
0x18000a4a1  jmp     short loc_18000A4C1
0x18000a4a3  xor     r10d, r10d
0x18000a4a6  mov     cs:?ThreadTable@?1??WppTraceIndent@@9@9, edx; `WppTraceIndent'::`2'::ThreadTable
0x18000a4ac  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, r10d; `WppTraceIndent'::`2'::idxCurrentThread
0x18000a4b3  mov     cs:dword_180031404, r10d
0x18000a4ba  movsxd  rax, r10d
0x18000a4bd  mov     ebx, [rbx+rax*8+4]
0x18000a4c1  mov     r11, cs:WPP_GLOBAL_Control
0x18000a4c8  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@9@9, 0; `WppTraceIndent'::`2'::szIndentPrefix
0x18000a4cf  test    byte ptr [r11+1Ch], 2
0x18000a4d4  jnz     loc_18000A900
0x18000a4da  lea     r8, ?szIndentPrefix@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::szIndentPrefix
0x18000a4e1  mov     rax, r8
0x18000a4e4  cmp     byte ptr [rax], 0
0x18000a4e7  jnz     loc_18000A668
0x18000a4ed  sub     r12, r14
0x18000a4f0  lea     rax, asc_180027E38; "<"
0x18000a4f7  test    r14, r14
0x18000a4fa  jz      short loc_18000A520
0x18000a4fc  mov     edx, 7FFFFFFEh
0x18000a501  test    rdx, rdx
0x18000a504  jz      short loc_18000A520
0x18000a506  movzx   ecx, byte ptr [rax]
0x18000a509  test    cl, cl
0x18000a50b  jz      short loc_18000A520
0x18000a50d  mov     [r12], cl
0x18000a511  inc     rax
0x18000a514  inc     r12
0x18000a517  dec     rdx
0x18000a51a  sub     r14, 1
0x18000a51e  jnz     short loc_18000A501
0x18000a520  test    r14, r14
0x18000a523  lea     rax, [r12-1]
0x18000a528  cmovnz  rax, r12
0x18000a52c  mov     byte ptr [rax], 0
0x18000a52f  test    r10d, r10d
0x18000a532  jns     short loc_18000A571
0x18000a534  mov     cs:WPP_pszIndent, r8
0x18000a53b  lea     rax, WPP_GLOBAL_Control
0x18000a542  cmp     r11, rax
  ... truncated ...
```
