# I_ReaderMonitorHandleStatusChangeEvent

- ea: `0x180004900`
- end: `0x180004f92`
- name: `I_ReaderMonitorHandleStatusChangeEvent`
- size: `1682`
- prototype: `__int64 __fastcall(__int64, __int64 *, unsigned int *, int *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180003510`

## callees

- `0x180004600`
- `0x180004900`
- `0x180005830`
- `0x18000af90`
- `0x18000c8f0`
- `0x18000e888`
- `0x1800151e4`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004924`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004924`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a6d`

## pseudocode

```c
__int64 __fastcall I_ReaderMonitorHandleStatusChangeEvent(__int64 a1, __int64 *a2, unsigned int *a3, int *a4, int *a5)
{
  DWORD CurrentThreadId; // eax
  char *i; // rcx
  const char *v9; // r9
  int v10; // r10d
  int v11; // r14d
  int v12; // r10d
  STRSAFE_LPSTR v13; // r11
  size_t v14; // rdx
  __int64 v15; // rbp
  char *v16; // r8
  __int64 v17; // rcx
  char *v18; // rax
  char *v19; // rdx
  __int64 v20; // rax
  char *v21; // rax
  unsigned int j; // esi
  int v23; // edi
  int v24; // eax
  DWORD v25; // eax
  size_t v26; // rdx
  int v27; // r10d
  int v28; // r11d
  STRSAFE_LPSTR v29; // rcx
  char *v30; // rax
  char *v31; // r15
  const char *v32; // rax
  __int64 v33; // r8
  char *v34; // rax
  __int64 v36; // rcx
  __int64 v37; // rdi
  __int64 v38; // rdi
  __int64 v39; // rax
  __int64 v40; // rdx
  int v41; // edx
  bool v42; // zf
  int v43; // r8d
  unsigned int k; // ecx
  bool v45; // zf
  __int64 v46; // rcx
  unsigned __int16 *v47; // r10
  __int64 v48; // r11
  unsigned __int16 *v49; // rax
  int v50; // edx
  unsigned int v51; // eax
  int v52; // edi
  int v53; // r10d
  unsigned int updated; // eax
  int m; // r15d
  int v56; // r11d
  SIZE_T dwBytes; // [rsp+20h] [rbp-58h]
  unsigned int v58; // [rsp+30h] [rbp-48h]
  int v59; // [rsp+34h] [rbp-44h]
  int v60; // [rsp+38h] [rbp-40h]

  CurrentThreadId = GetCurrentThreadId();
  v10 = `WppTraceIndent'::`2'::idxCurrentThread;
  v11 = -1;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v10 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = CurrentThreadId;
    dword_180031404 = 0;
LABEL_7:
    v12 = ++*((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v10 + 1);
    goto LABEL_8;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
    || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != CurrentThreadId )
  {
    v41 = -1;
    for ( i = 0; ; i = (char *)(unsigned int)((_DWORD)i + 1) )
    {
      v42 = (_DWORD)i == 32;
      if ( (unsigned int)i >= 0x20 )
        break;
      v43 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)i);
      if ( v43 == CurrentThreadId )
      {
        v10 = (int)i;
        `WppTraceIndent'::`2'::idxCurrentThread = (int)i;
        v42 = (_DWORD)i == 32;
        break;
      }
      if ( v41 == -1 && !v43 )
        v41 = (int)i;
    }
    if ( v42 )
    {
      if ( v41 == -1 )
      {
        `WppTraceIndent'::`2'::idxCurrentThread = -2;
        v12 = 0;
        goto LABEL_8;
      }
      v10 = v41;
      `WppTraceIndent'::`2'::idxCurrentThread = v41;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v41) = CurrentThreadId;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v41 + 1) = 0;
    }
  }
  if ( v10 >= 0 )
    goto LABEL_7;
  v12 = 0;
LABEL_8:
  v13 = WPP_GLOBAL_Control;
  v14 = 1;
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  v58 = 0;
  v60 = 0;
  v59 = 0;
  if ( (WPP_GLOBAL_Control[28] & 2) != 0 && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    v52 = 1;
    if ( v12 >= 1 )
    {
      do
      {
        if ( StringCbCatA(i, v14, "..") )
          break;
        ++v52;
      }
      while ( v52 <= v53 );
      v13 = WPP_GLOBAL_Control;
    }
  }
  v15 = 256;
  v16 = &`WppTraceIndent'::`2'::szIndentPrefix;
  v17 = 256;
  v18 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( *v18 )
  {
    ++v18;
    if ( !--v17 )
      goto LABEL_18;
  }
  v9 = ">";
  v19 = (char *)HotPatchSpareGlobals - v17;
  v20 = 2147483646;
  do
  {
    if ( !v20 )
      break;
    if ( !*v9 )
      break;
    *v19++ = *v9++;
    --v20;
    --v17;
  }
  while ( v17 );
  v16 = &`WppTraceIndent'::`2'::szIndentPrefix;
  v21 = v19 - 1;
  if ( v17 )
    v21 = v19;
  *v21 = 0;
LABEL_18:
  WPP_pszIndent = (__int64)&`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v13 != (STRSAFE_LPSTR)&WPP_GLOBAL_Control && (v13[28] & 2) != 0 && (unsigned __int8)v13[25] >= 5u )
    WPP_SF_s(
      *((_QWORD *)v13 + 2),
      228,
      &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      &`WppTraceIndent'::`2'::szIndentPrefix);
  for ( j = 0; j < *a3; ++j )
  {
    if ( j )
    {
      v37 = j;
    }
    else
    {
      v36 = *a2;
      v37 = 0;
      if ( (*(_BYTE *)(*a2 + 20) & 2) != 0 )
        goto LABEL_107;
    }
    v36 = *a2;
    if ( (*(_BYTE *)((v37 << 6) + *a2 + 20) & 8) != 0 )
LABEL_107:
      v60 = 1;
    v38 = v37 << 6;
    if ( (*(_BYTE *)(v36 + v38 + 16) & 0x10) == 0 || (*(_BYTE *)(v36 + v38 + 20) & 0x20) == 0 )
      goto LABEL_48;
    I_ReaderMonitorSetProcessingEvent(a1, 1, v16, v9);
    v47 = *(unsigned __int16 **)(a1 + 112);
    if ( !v47 )
    {
LABEL_93:
      v58 = 1168;
LABEL_94:
      WppTraceIndent(v46, 2);
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          229,
          (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent,
          v58);
      }
      goto LABEL_48;
    }
    v48 = v38 + *a2;
    while ( 1 )
    {
      v49 = *(unsigned __int16 **)v47;
      do
      {
        v46 = *(unsigned __int16 *)((char *)v49 + *(_QWORD *)v48 - *(_QWORD *)v47);
        v50 = *v49 - (_DWORD)v46;
        if ( v50 )
          break;
        ++v49;
      }
      while ( (_DWORD)v46 );
      if ( !v50 )
        break;
      v47 = (unsigned __int16 *)*((_QWORD *)v47 + 30);
      if ( !v47 )
        goto LABEL_93;
    }
    LODWORD(dwBytes) = *(_DWORD *)(v48 + 24);
    v51 = I_ReaderListAsyncProcessReader(a1, (int)v47, *(_DWORD *)(v48 + 20) & 0xFFFF0000, (int)v48 + 28, dwBytes);
    v58 = v51;
    if ( v51 )
    {
      if ( v51 == 8 )
      {
        v23 = 1;
        goto LABEL_22;
      }
      goto LABEL_94;
    }
LABEL_48:
    v39 = *a2;
    if ( (*(_BYTE *)(*a2 + v38 + 16) & 0x20) != 0 && (*(_BYTE *)(v39 + v38 + 20) & 0x10) != 0 )
    {
      v58 = I_ReaderListClearReader(a1, *(_QWORD *)(v39 + v38), 0);
      v59 = 1;
    }
    *(_QWORD *)(*a2 + v38 + 16) = *(unsigned int *)(*a2 + v38 + 20);
  }
  v23 = 0;
  if ( !v60 )
  {
LABEL_22:
    v24 = v59;
    goto LABEL_23;
  }
  updated = I_UpdateReaderStateArray(a1, a2, a3, v9);
  v58 = updated;
  if ( updated )
  {
    if ( updated == -2146435054 || updated == -2146435043 || updated == -2146435042 )
      v24 = 1;
    else
      v24 = v59;
    v23 = 1;
  }
  else
  {
    v24 = 1;
  }
LABEL_23:
  *a4 = v24;
  *a5 = v23;
  v25 = GetCurrentThreadId();
  v27 = `WppTraceIndent'::`2'::idxCurrentThread;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v27 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = v25;
    dword_180031404 = 0;
LABEL_29:
    v28 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v27 + 1);
    goto LABEL_30;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread != -2
    && *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) == v25 )
  {
    goto LABEL_26;
  }
  for ( k = 0; ; ++k )
  {
    v45 = k == 32;
    if ( k >= 0x20 )
      break;
    v26 = *((unsigned int *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)k);
    if ( (_DWORD)v26 == v25 )
    {
      v27 = k;
      `WppTraceIndent'::`2'::idxCurrentThread = k;
      v45 = k == 32;
      break;
    }
    if ( v11 == -1 && !(_DWORD)v26 )
      v11 = k;
  }
  if ( !v45 )
  {
LABEL_26:
    if ( v27 < 0 )
    {
      v28 = 0;
      goto LABEL_30;
    }
    goto LABEL_29;
  }
  if ( v11 != -1 )
  {
    v27 = v11;
    `WppTraceIndent'::`2'::idxCurrentThread = v11;
    *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v11) = v25;
    *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v11 + 1) = 0;
    goto LABEL_26;
  }
  v27 = -2;
  v28 = 0;
  `WppTraceIndent'::`2'::idxCurrentThread = -2;
LABEL_30:
  v29 = WPP_GLOBAL_Control;
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (WPP_GLOBAL_Control[28] & 2) != 0 && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u && v28 >= 1 )
  {
    for ( m = 1; m <= v56; ++m )
    {
      if ( StringCbCatA(v29, v26, "..") )
        break;
    }
    v29 = WPP_GLOBAL_Control;
  }
  v30 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( *v30 )
  {
    ++v30;
    if ( !--v15 )
      goto LABEL_40;
  }
  v31 = (char *)HotPatchSpareGlobals - v15;
  v32 = "<";
  v33 = 2147483646;
  do
  {
    if ( !v33 )
      break;
    if ( !*v32 )
      break;
    *v31++ = *v32++;
    --v33;
    --v15;
  }
  while ( v15 );
  v34 = v31 - 1;
  if ( v15 )
    v34 = v31;
  *v34 = 0;
LABEL_40:
  if ( v27 >= 0 )
  {
    v40 = 8LL * v27;
    v42 = (*(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v40 + 4))-- == 1;
    if ( v42 )
      *(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v40) = 0;
  }
  WPP_pszIndent = (__int64)&`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v29 == (STRSAFE_LPSTR)&WPP_GLOBAL_Control || (v29[28] & 2) == 0 || (unsigned __int8)v29[25] < 5u )
    return v58;
  WPP_SF_sD(
    *((_QWORD *)v29 + 2),
    230,
    (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
    (unsigned int)&`WppTraceIndent'::`2'::szIndentPrefix,
    v58);
  return v58;
}

```

## disassembly

```asm
0x180004900  mov     [rsp+arg_8], rbx
0x180004905  mov     [rsp+arg_18], r9
0x18000490a  mov     qword ptr [rsp+arg_0], rcx
0x18000490f  push    rbp
0x180004910  push    rsi
0x180004911  push    rdi
0x180004912  push    r12
0x180004914  push    r13
0x180004916  push    r14
0x180004918  push    r15
0x18000491a  sub     rsp, 40h
0x18000491e  mov     r12, r8
0x180004921  mov     r13, rdx
0x180004924  call    cs:__imp_GetCurrentThreadId
0x18000492a  movsxd  r10, cs:?idxCurrentThread@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::idxCurrentThread
0x180004931  lea     r8, ?ThreadTable@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::ThreadTable
0x180004938  mov     r14d, 0FFFFFFFFh
0x18000493e  xor     ebx, ebx
0x180004940  mov     r11d, eax
0x180004943  cmp     r10d, r14d
0x180004946  jz      short loc_180004966
0x180004948  cmp     r10d, 0FFFFFFFEh
0x18000494c  jz      loc_180004BFA
0x180004952  cmp     [r8+r10*8], eax
0x180004956  jnz     loc_180004BFA
0x18000495c  test    r10d, r10d
0x18000495f  jns     short loc_18000497C
0x180004961  mov     r10d, ebx
0x180004964  jmp     short loc_180004989
0x180004966  mov     r10d, ebx
0x180004969  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ebx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000496f  mov     cs:?ThreadTable@?1??WppTraceIndent@@9@9, r11d; `WppTraceIndent'::`2'::ThreadTable
0x180004976  mov     cs:dword_180031404, ebx
0x18000497c  movsxd  rax, r10d
0x18000497f  inc     dword ptr [r8+rax*8+4]
0x180004984  mov     r10d, [r8+rax*8+4]
0x180004989  mov     r11, cs:WPP_GLOBAL_Control
0x180004990  mov     edx, 1; cbDest
0x180004995  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@9@9, 0; `WppTraceIndent'::`2'::szIndentPrefix
0x18000499c  mov     [rsp+78h+var_48], ebx
0x1800049a0  mov     [rsp+78h+var_40], ebx
0x1800049a4  test    byte ptr [r11+1Ch], 2
0x1800049a9  mov     [rsp+78h+var_44], ebx
0x1800049ad  jnz     loc_180004E89
0x1800049b3  mov     ebp, 100h
0x1800049b8  lea     r8, ?szIndentPrefix@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::szIndentPrefix
0x1800049bf  mov     ecx, ebp
0x1800049c1  mov     rax, r8
0x1800049c4  cmp     byte ptr [rax], 0
0x1800049c7  lea     r15, HotPatchSpareGlobals
0x1800049ce  jnz     loc_180004E65
0x1800049d4  mov     rdx, r15
0x1800049d7  lea     r9, asc_180027E34; ">"
0x1800049de  sub     rdx, rcx
0x1800049e1  mov     eax, 7FFFFFFEh
0x1800049e6  test    rcx, rcx
0x1800049e9  jz      short loc_180004A12
0x1800049eb  test    rax, rax
0x1800049ee  jz      short loc_180004A0B
0x1800049f0  movzx   r8d, byte ptr [r9]
0x1800049f4  test    r8b, r8b
0x1800049f7  jz      short loc_180004A0B
0x1800049f9  mov     [rdx], r8b
0x1800049fc  inc     r9
0x1800049ff  inc     rdx
0x180004a02  dec     rax
0x180004a05  sub     rcx, 1
0x180004a09  jnz     short loc_1800049EB
0x180004a0b  lea     r8, ?szIndentPrefix@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::szIndentPrefix
0x180004a12  lea     rax, [rdx-1]
0x180004a16  test    rcx, rcx
0x180004a19  cmovnz  rax, rdx
0x180004a1d  mov     edx, 1
0x180004a22  mov     byte ptr [rax], 0
0x180004a25  mov     cs:WPP_pszIndent, r8
0x180004a2c  lea     rax, WPP_GLOBAL_Control
0x180004a33  cmp     r11, rax
0x180004a36  jnz     loc_180004CBC
0x180004a3c  mov     esi, ebx
0x180004a3e  cmp     esi, [r12]
0x180004a42  jb      loc_180004B73
0x180004a48  cmp     [rsp+78h+var_40], 0
0x180004a4d  mov     edi, ebx
0x180004a4f  jnz     loc_180004ED0
0x180004a55  mov     eax, [rsp+78h+var_44]
0x180004a59  mov     rcx, [rsp+78h+arg_18]
0x180004a61  mov     [rcx], eax
0x180004a63  mov     rax, [rsp+78h+arg_20]
0x180004a6b  mov     [rax], edi
0x180004a6d  call    cs:__imp_GetCurrentThreadId
0x180004a73  movsxd  r10, cs:?idxCurrentThread@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::idxCurrentThread
0x180004a7a  lea     rdi, ?ThreadTable@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::ThreadTable
0x180004a81  mov     r8d, eax
0x180004a84  cmp     r10d, r14d
0x180004a87  jz      short loc_180004AA7
0x180004a89  cmp     r10d, 0FFFFFFFEh
0x180004a8d  jz      loc_180004C27
0x180004a93  cmp     [rdi+r10*8], eax
0x180004a97  jnz     loc_180004C27
0x180004a9d  test    r10d, r10d
0x180004aa0  jns     short loc_180004ABD
0x180004aa2  mov     r11d, ebx
0x180004aa5  jmp     short loc_180004AC5
0x180004aa7  mov     r10d, ebx
0x180004aaa  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ebx; `WppTraceIndent'::`2'::idxCurrentThread
0x180004ab0  mov     cs:?ThreadTable@?1??WppTraceIndent@@9@9, r8d; `WppTraceIndent'::`2'::ThreadTable
0x180004ab7  mov     cs:dword_180031404, ebx
0x180004abd  movsxd  rax, r10d
0x180004ac0  mov     r11d, [rdi+rax*8+4]
0x180004ac5  mov     rcx, cs:WPP_GLOBAL_Control; pszDest
0x180004acc  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@9@9, 0; `WppTraceIndent'::`2'::szIndentPrefix
0x180004ad3  test    byte ptr [rcx+1Ch], 2
0x180004ad7  jnz     loc_180004F1F
0x180004add  lea     r9, ?szIndentPrefix@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::szIndentPrefix
0x180004ae4  mov     rax, r9
0x180004ae7  cmp     byte ptr [rax], 0
0x180004aea  jnz     loc_180004E77
0x180004af0  sub     r15, rbp
0x180004af3  lea     rax, asc_180027E38; "<"
0x180004afa  test    rbp, rbp
0x180004afd  jz      short loc_180004B23
0x180004aff  mov     r8d, 7FFFFFFEh
0x180004b05  test    r8, r8
0x180004b08  jz      short loc_180004B23
0x180004b0a  movzx   edx, byte ptr [rax]
0x180004b0d  test    dl, dl
0x180004b0f  jz      short loc_180004B23
0x180004b11  mov     [r15], dl
0x180004b14  inc     rax
0x180004b17  inc     r15
0x180004b1a  dec     r8
0x180004b1d  sub     rbp, 1
0x180004b21  jnz     short loc_180004B05
0x180004b23  test    rbp, rbp
0x180004b26  lea     rax, [r15-1]
0x180004b2a  cmovnz  rax, r15
0x180004b2e  mov     byte ptr [rax], 0
0x180004b31  test    r10d, r10d
0x180004b34  jns     loc_180004BDC
0x180004b3a  mov     cs:WPP_pszIndent, r9
0x180004b41  lea     rax, WPP_GLOBAL_Control
0x180004b48  cmp     rcx, rax
0x180004b4b  jz      short loc_180004B57
0x180004b4d  test    byte ptr [rcx+1Ch], 2
0x180004b51  jnz     loc_180004F64
0x180004b57  mov     eax, [rsp+78h+var_48]
0x180004b5b  mov     rbx, [rsp+78h+arg_8]
0x180004b63  add     rsp, 40h
0x180004b67  pop     r15
0x180004b69  pop     r14
0x180004b6b  pop     r13
0x180004b6d  pop     r12
0x180004b6f  pop     rdi
0x180004b70  pop     rsi
0x180004b71  pop     rbp
0x180004b72  retn
0x180004b73  test    esi, esi
0x180004b75  jnz     loc_180004CB5
0x180004b7b  mov     rcx, [r13+0]
0x180004b7f  mov     rdi, rbx
0x180004b82  test    byte ptr [rcx+14h], 2
0x180004b86  jnz     loc_180004EC7
0x180004b8c  mov     rcx, [r13+0]
0x180004b90  mov     rax, rdi
0x180004b93  shl     rax, 6
0x180004b97  test    byte ptr [rax+rcx+14h], 8
0x180004b9c  jnz     loc_180004EC7
0x180004ba2  shl     rdi, 6
0x180004ba6  test    byte ptr [rcx+rdi+10h], 10h
0x180004bab  jnz     loc_180004D24
0x180004bb1  mov     rax, [r13+0]
0x180004bb5  test    byte ptr [rax+rdi+10h], 20h
0x180004bba  jnz     loc_180004CF4
0x180004bc0  mov     rcx, [r13+0]
0x180004bc4  inc     esi
0x180004bc6  mov     edx, 1
0x180004bcb  mov     eax, [rcx+rdi+14h]
0x180004bcf  mov     [rcx+rdi+10h], eax
0x180004bd3  mov     [rcx+rdi+14h], ebx
0x180004bd7  jmp     loc_180004A3E
0x180004bdc  movsxd  rax, r10d
0x180004bdf  lea     rdx, ds:0[rax*8]
0x180004be7  sub     dword ptr [rdx+rdi+4], 1
0x180004bec  jnz     loc_180004B3A
0x180004bf2  mov     [rdx+rdi], ebx
0x180004bf5  jmp     loc_180004B3A
0x180004bfa  mov     edx, r14d
0x180004bfd  mov     ecx, ebx
0x180004bff  nop
0x180004c00  cmp     ecx, 20h ; ' '
0x180004c03  jnb     short loc_180004C63
0x180004c05  movsxd  rax, ecx
0x180004c08  mov     r8d, [r8+rax*8]
0x180004c0c  cmp     r8d, r11d
0x180004c0f  jz      short loc_180004C50
0x180004c11  cmp     edx, r14d
0x180004c14  jnz     short loc_180004C1C
0x180004c16  test    r8d, r8d
0x180004c19  cmovz   edx, ecx
0x180004c1c  inc     ecx
0x180004c1e  lea     r8, ?ThreadTable@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::ThreadTable
0x180004c25  jmp     short loc_180004C00
0x180004c27  mov     ecx, ebx
0x180004c29  nop     dword ptr [rax+00000000h]
0x180004c30  cmp     ecx, 20h ; ' '
0x180004c33  jnb     short loc_180004C90
0x180004c35  movsxd  rax, ecx
0x180004c38  mov     edx, [rdi+rax*8]
0x180004c3b  cmp     edx, r8d
0x180004c3e  jz      short loc_180004C84
0x180004c40  cmp     r14d, 0FFFFFFFFh
0x180004c44  jnz     short loc_180004C4C
0x180004c46  test    edx, edx
0x180004c48  cmovz   r14d, ecx
0x180004c4c  inc     ecx
0x180004c4e  jmp     short loc_180004C30
0x180004c50  mov     r10d, ecx
0x180004c53  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ecx; `WppTraceIndent'::`2'::idxCurrentThread
0x180004c59  lea     r8, ?ThreadTable@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::ThreadTable
0x180004c60  cmp     ecx, 20h ; ' '
0x180004c63  jnz     loc_18000495C
0x180004c69  cmp     edx, r14d
0x180004c6c  jnz     loc_180004DBB
0x180004c72  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, 0FFFFFFFEh; `WppTraceIndent'::`2'::idxCurrentThread
0x180004c7c  mov     r10d, ebx
0x180004c7f  jmp     loc_180004989
0x180004c84  mov     r10d, ecx
0x180004c87  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ecx; `WppTraceIndent'::`2'::idxCurrentThread
0x180004c8d  cmp     ecx, 20h ; ' '
0x180004c90  jnz     loc_180004A9D
0x180004c96  cmp     r14d, 0FFFFFFFFh
0x180004c9a  jnz     loc_180004DD5
0x180004ca0  mov     r10d, 0FFFFFFFEh
0x180004ca6  mov     r11d, ebx
0x180004ca9  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, r10d; `WppTraceIndent'::`2'::idxCurrentThread
0x180004cb0  jmp     loc_180004AC5
0x180004cb5  mov     edi, esi
0x180004cb7  jmp     loc_180004B8C
0x180004cbc  test    byte ptr [r11+1Ch], 2
0x180004cc1  jz      loc_180004A3C
0x180004cc7  cmp     byte ptr [r11+19h], 5
0x180004ccc  jb      loc_180004A3C
0x180004cd2  mov     rcx, [r11+10h]
0x180004cd6  mov     r9, r8
0x180004cd9  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180004ce0  mov     edx, 0E4h
0x180004ce5  call    WPP_SF_s
0x180004cea  mov     edx, 1
0x180004cef  jmp     loc_180004A3C
0x180004cf4  test    byte ptr [rax+rdi+14h], 10h
0x180004cf9  jz      loc_180004BC0
0x180004cff  mov     rdx, [rax+rdi]
0x180004d03  xor     r8d, r8d
0x180004d06  mov     rcx, qword ptr [rsp+78h+arg_0]
0x180004d0e  call    I_ReaderListClearReader
0x180004d13  mov     [rsp+78h+var_48], eax
0x180004d17  mov     [rsp+78h+var_44], 1
0x180004d1f  jmp     loc_180004BC0
0x180004d24  test    byte ptr [rcx+rdi+14h], 20h
0x180004d29  jz      loc_180004BB1
0x180004d2f  mov     rcx, qword ptr [rsp+78h+arg_0]
0x180004d37  call    I_ReaderMonitorSetProcessingEvent
0x180004d3c  mov     rax, qword ptr [rsp+78h+arg_0]
0x180004d44  mov     r10, [rax+70h]
0x180004d48  test    r10, r10
0x180004d4b  jz      loc_180004DFF
0x180004d51  mov     r11, [r13+0]
0x180004d55  add     r11, rdi
0x180004d58  mov     rax, [r10]
0x180004d5b  mov     r8, [r11]
0x180004d5e  sub     r8, rax
0x180004d61  movzx   edx, word ptr [rax]
0x180004d64  movzx   ecx, word ptr [rax+r8]
0x180004d69  sub     edx, ecx
0x180004d6b  jnz     short loc_180004D75
0x180004d6d  add     rax, 2
0x180004d71  test    ecx, ecx
0x180004d73  jnz     short loc_180004D61
0x180004d75  test    edx, edx
0x180004d77  jnz     short loc_180004DEF
0x180004d79  mov     r8d, [r11+14h]
0x180004d7d  lea     r9, [r11+1Ch]; int
0x180004d81  mov     eax, [r11+18h]
0x180004d85  and     r8d, 0FFFF0000h; int
0x180004d8c  mov     rcx, qword ptr [rsp+78h+arg_0]; int
0x180004d94  mov     rdx, r10; int
0x180004d97  mov     dword ptr [rsp+78h+dwBytes], eax; dwBytes
0x180004d9b  call    I_ReaderListAsyncProcessReader
0x180004da0  mov     [rsp+78h+var_48], eax
0x180004da4  test    eax, eax
0x180004da6  jz      loc_180004BB1
0x180004dac  cmp     eax, 8
0x180004daf  jnz     short loc_180004E07
0x180004db1  mov     edi, 1
0x180004db6  jmp     loc_180004A55
0x180004dbb  movsxd  rax, edx
0x180004dbe  mov     r10d, edx
0x180004dc1  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, edx; `WppTraceIndent'::`2'::idxCurrentThread
0x180004dc7  mov     [r8+rax*8], r11d
0x180004dcb  mov     [r8+rax*8+4], ebx
  ... truncated ...
```
