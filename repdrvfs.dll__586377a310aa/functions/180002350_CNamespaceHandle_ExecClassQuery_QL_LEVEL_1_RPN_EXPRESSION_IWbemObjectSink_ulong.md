# CNamespaceHandle::ExecClassQuery(QL_LEVEL_1_RPN_EXPRESSION *,IWbemObjectSink *,ulong)

- ea: `0x180002350`
- end: `0x180002adf`
- name: `?ExecClassQuery@CNamespaceHandle@@IEAAJPEAUQL_LEVEL_1_RPN_EXPRESSION@@PEAUIWbemObjectSink@@K@Z`
- size: `1935`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, struct QL_LEVEL_1_RPN_EXPRESSION *, struct IWbemObjectSink *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180001750`

## callees

- `0x180001274`
- `0x1800012b8`
- `0x1800014b0`
- `0x180002350`
- `0x180006000`
- `0x180007770`
- `0x180048010`

## import_xrefs

- `wbemcomn!?GetStringAt@CPropertyName@@QEBAPEBGJ@Z` at `0x1800023cf`
- `wbemcomn!?GetStringAt@CPropertyName@@QEBAPEBGJ@Z` at `0x18000251a`
- `wbemcomn!?GetStringAt@CPropertyName@@QEBAPEBGJ@Z` at `0x18000253c`
- `wbemcomn!?GetStringAt@CPropertyName@@QEBAPEBGJ@Z` at `0x180002606`
- `wbemcomn!?GetStringAt@CPropertyName@@QEBAPEBGJ@Z` at `0x180002713`
- `wbemcomn!?GetStringAt@CPropertyName@@QEBAPEBGJ@Z` at `0x1800023cf`
- `wbemcomn!?GetStringAt@CPropertyName@@QEBAPEBGJ@Z` at `0x18000251a`
- `wbemcomn!?GetStringAt@CPropertyName@@QEBAPEBGJ@Z` at `0x18000253c`
- `wbemcomn!?GetStringAt@CPropertyName@@QEBAPEBGJ@Z` at `0x180002606`
- `wbemcomn!?GetStringAt@CPropertyName@@QEBAPEBGJ@Z` at `0x180002713`
- `wbemcomn!GetMemLogObject` at `0x1800026df`
- `wbemcomn!GetMemLogObject` at `0x180002793`
- `wbemcomn!GetMemLogObject` at `0x18000292b`
- `wbemcomn!GetMemLogObject` at `0x1800029a8`
- `wbemcomn!GetMemLogObject` at `0x180002a5a`
- `wbemcomn!GetMemLogObject` at `0x180002aa5`
- `wbemcomn!GetMemLogObject` at `0x1800026df`
- `wbemcomn!GetMemLogObject` at `0x180002793`
- `wbemcomn!GetMemLogObject` at `0x18000292b`
- `wbemcomn!GetMemLogObject` at `0x1800029a8`
- `wbemcomn!GetMemLogObject` at `0x180002a5a`
- `wbemcomn!GetMemLogObject` at `0x180002aa5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800026ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000279e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002936`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800029b3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002a65`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002ab0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800026ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000279e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002936`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800029b3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002a65`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002ab0`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180002457`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180002499`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180002687`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800026c9`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180002457`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180002499`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180002687`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800026c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CNamespaceHandle::ExecClassQuery(
        CNamespaceHandle *this,
        struct QL_LEVEL_1_RPN_EXPRESSION *a2,
        struct IWbemObjectSink *a3,
        int a4)
{
  struct IWbemObjectSink *v4; // rsi
  CNamespaceHandle *v6; // rdi
  const unsigned __int16 *v7; // r12
  const unsigned __int16 *v8; // r15
  bool v9; // r13
  int v10; // eax
  __int64 v11; // r14
  const wchar_t *v12; // rdi
  const unsigned __int16 *i; // rsi
  WCHAR v14; // bx
  WCHAR v15; // cx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rbx
  const unsigned __int16 *StringAt; // rax
  const unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rax
  __int64 v22; // r8
  int v23; // edx
  int v24; // ecx
  int ClassDirect; // ebx
  const unsigned __int16 *v27; // rdi
  const unsigned __int16 *v28; // rsi
  WCHAR v29; // bx
  WCHAR v30; // cx
  int v31; // eax
  int v32; // eax
  CMemoryLog *MemLogObject; // rax
  const unsigned __int16 *v34; // rax
  const unsigned __int16 *v35; // rdx
  CMemoryLog *v36; // rax
  const unsigned __int16 *v37; // rdx
  CMemoryLog *v38; // rax
  CVarObjHeap *v39; // rcx
  __int64 v40; // rdx
  void *v41; // rbx
  int v42; // edi
  CMemoryLog *v43; // rax
  CMemoryLog *v44; // rax
  CMemoryLog *v45; // rax
  bool lpDestStr; // [rsp+20h] [rbp-50h]
  WCHAR DestStr; // [rsp+50h] [rbp-20h] BYREF
  WCHAR SrcStr; // [rsp+58h] [rbp-18h] BYREF
  void *v49[2]; // [rsp+60h] [rbp-10h] BYREF

  v4 = a3;
  v6 = this;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 450, a3, a3);
  }
  if ( g_bShuttingDown )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217357);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 451, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749939LL);
    }
    return 2147749939LL;
  }
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = *((_DWORD *)a2 + 2);
  if ( v10 != 1 )
  {
    if ( v10 == 3 )
    {
      v18 = *((_QWORD *)a2 + 2);
      if ( *(_DWORD *)v18 == 4
        && *(_DWORD *)(v18 + 128) == 4
        && *(_DWORD *)(v18 + 256) == 2
        && *(_DWORD *)(v18 + 40) == 9
        && *(_DWORD *)(v18 + 168) == 2 )
      {
        StringAt = CPropertyName::GetStringAt((CPropertyName *)(v18 + 8), 0);
        if ( (unsigned int)wbem_wcsicmp(StringAt, L"__THIS") )
          goto LABEL_41;
        v20 = CPropertyName::GetStringAt((CPropertyName *)(v18 + 136), 0);
        if ( (unsigned int)wbem_wcsicmp(v20, L"__CLASS") )
          goto LABEL_41;
        v21 = *(unsigned __int16 **)(v18 + 56);
        v22 = *(_QWORD *)(v18 + 184) - (_QWORD)v21;
        do
        {
          v23 = *(unsigned __int16 *)((char *)v21 + v22);
          v24 = *v21 - v23;
          if ( v24 )
            break;
          ++v21;
        }
        while ( v23 );
        v6 = this;
        if ( !v24 )
        {
          v8 = *(const unsigned __int16 **)(v18 + 56);
          v9 = 1;
        }
      }
    }
LABEL_42:
    if ( (a4 & 0x200000) == 0 )
      goto LABEL_43;
    v49[0] = 0;
    if ( v7 )
    {
      v37 = v7;
    }
    else
    {
      if ( !v8 )
        goto LABEL_43;
      v37 = v8;
    }
    ClassDirect = CNamespaceHandle::GetClassDirect(v6, v37, &IID__IWmiObject, v49, 0, 0, 0, 0, 0);
    if ( ClassDirect < 0 )
    {
      v44 = GetMemLogObject();
      CMemoryLog::Write(v44, ClassDirect);
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)ClassDirect;
      }
      v40 = 457;
      goto LABEL_98;
    }
    if ( v49[0] )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v49[0] + 16LL))(v49[0]);
LABEL_43:
    ClassDirect = CNamespaceHandle::EnumerateClasses(v6, v4, v7, v8, lpDestStr, v9);
    if ( ClassDirect < 0 )
    {
      if ( ClassDirect == -2147217406 )
        return 2147749890LL;
      v45 = GetMemLogObject();
      CMemoryLog::Write(v45, ClassDirect);
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)ClassDirect;
      }
      v40 = 458;
      goto LABEL_98;
    }
    return 0;
  }
  v11 = *((_QWORD *)a2 + 2);
  v12 = L"__SUPERCLASS";
  for ( i = CPropertyName::GetStringAt((CPropertyName *)(v11 + 8), 0); ; ++i )
  {
    v14 = *i;
    if ( !*i )
      break;
    if ( v14 > 0x7Fu )
    {
      SrcStr = *i;
      DestStr = 0;
      v16 = LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, &DestStr, 1);
      v14 = DestStr;
      if ( !v16 )
        v14 = SrcStr;
    }
    else if ( (unsigned __int16)(v14 - 65) <= 0x19u )
    {
      v14 += 32;
    }
LABEL_10:
    v15 = *v12;
    if ( *v12 > 0x7Fu )
    {
      DestStr = *v12;
      SrcStr = 0;
      v17 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, &SrcStr, 1);
      v15 = SrcStr;
      if ( !v17 )
        v15 = DestStr;
    }
    else if ( (unsigned __int16)(v15 - 65) <= 0x19u )
    {
      v15 += 32;
    }
    if ( v14 != v15 )
      goto LABEL_45;
    ++v12;
  }
  if ( *v12 )
    goto LABEL_10;
  if ( *(_DWORD *)(v11 + 40) == 1 )
  {
    v7 = *(const unsigned __int16 **)(v11 + 56);
    goto LABEL_40;
  }
LABEL_45:
  v27 = L"__THIS";
  v28 = CPropertyName::GetStringAt((CPropertyName *)(v11 + 8), 0);
  while ( 2 )
  {
    v29 = *v28;
    if ( *v28 )
    {
      if ( v29 > 0x7Fu )
      {
        DestStr = *v28;
        SrcStr = 0;
        v31 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, &SrcStr, 1);
        v29 = SrcStr;
        if ( !v31 )
          v29 = DestStr;
      }
      else if ( (unsigned __int16)(v29 - 65) <= 0x19u )
      {
        v29 += 32;
      }
      goto LABEL_50;
    }
    if ( *v27 )
    {
LABEL_50:
      v30 = *v27;
      if ( *v27 > 0x7Fu )
      {
        DestStr = *v27;
        SrcStr = 0;
        v32 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, &SrcStr, 1);
        v30 = SrcStr;
        if ( !v32 )
          v30 = DestStr;
      }
      else if ( (unsigned __int16)(v30 - 65) <= 0x19u )
      {
        v30 += 32;
      }
      if ( v29 != v30 )
        goto LABEL_63;
      ++v28;
      ++v27;
      continue;
    }
    break;
  }
  if ( *(_DWORD *)(v11 + 40) == 9 )
  {
    v8 = *(const unsigned __int16 **)(v11 + 56);
    goto LABEL_40;
  }
LABEL_63:
  v34 = CPropertyName::GetStringAt((CPropertyName *)(v11 + 8), 0);
  if ( (unsigned int)wbem_wcsicmp(v34, L"__CLASS")
    || *(_DWORD *)(v11 + 40) != 1
    || (v35 = *(const unsigned __int16 **)(v11 + 56)) == 0 )
  {
LABEL_40:
    v4 = a3;
LABEL_41:
    v6 = this;
    goto LABEL_42;
  }
  v49[0] = 0;
  ClassDirect = CNamespaceHandle::GetClassDirect(this, v35, &IID__IWmiObject, v49, 1, 0, 0, 0, 0);
  if ( ClassDirect != -2147217406 )
  {
    if ( ClassDirect < 0 )
    {
      v38 = GetMemLogObject();
      CMemoryLog::Write(v38, ClassDirect);
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)ClassDirect;
      }
      v40 = 454;
LABEL_98:
      WPP_SF_d(*((_QWORD *)v39 + 2), v40, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, (unsigned int)ClassDirect);
      return (unsigned int)ClassDirect;
    }
    v41 = v49[0];
    v49[1] = v49[0];
    v42 = ((__int64 (__fastcall *)(struct IWbemObjectSink *, __int64, void **))a3->lpVtbl->Indicate)(a3, 1, v49);
    if ( v42 < 0 )
    {
      v43 = GetMemLogObject();
      CMemoryLog::Write(v43, v42);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          455,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          (unsigned int)v42);
      }
      if ( v41 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v41 + 16LL))(v41);
      return (unsigned int)v42;
    }
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 456, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 0);
    }
    if ( v41 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v41 + 16LL))(v41);
    return 0;
  }
  if ( (a4 & 0x200000) == 0 )
  {
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 453, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 0);
    }
    return 0;
  }
  v36 = GetMemLogObject();
  CMemoryLog::Write(v36, ClassDirect);
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 452, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749890LL);
  }
  return 2147749890LL;
}

```

## disassembly

```asm
0x180002350  mov     [rsp-38h+arg_8], rbx
0x180002355  mov     [rsp-38h+arg_18], r9d
0x18000235a  mov     [rsp-38h+arg_10], r8
0x18000235f  mov     [rsp-38h+arg_0], rcx
0x180002364  push    rbp
0x180002365  push    rsi
0x180002366  push    rdi
0x180002367  push    r12
0x180002369  push    r13
0x18000236b  push    r14
0x18000236d  push    r15
0x18000236f  mov     rbp, rsp
0x180002372  sub     rsp, 70h
0x180002376  mov     rsi, r8
0x180002379  mov     rbx, rdx
0x18000237c  mov     rdi, rcx
0x18000237f  lea     r14, WPP_GLOBAL_Control
0x180002386  mov     rcx, cs:WPP_GLOBAL_Control
0x18000238d  cmp     rcx, r14
0x180002390  jz      short loc_18000239C
0x180002392  test    byte ptr [rcx+1Ch], 1
0x180002396  jnz     loc_18000288B
0x18000239c  cmp     cs:?g_bShuttingDown@@3_NA, 0; bool g_bShuttingDown
0x1800023a3  jnz     loc_1800026DF
0x1800023a9  xor     r12d, r12d
0x1800023ac  xor     r15d, r15d
0x1800023af  xor     r13b, r13b
0x1800023b2  mov     eax, [rbx+8]
0x1800023b5  cmp     eax, 1
0x1800023b8  jnz     loc_1800024CD
0x1800023be  mov     r14, [rbx+10h]
0x1800023c2  lea     rcx, [r14+8]
0x1800023c6  lea     rdi, aSuperclass; "__SUPERCLASS"
0x1800023cd  xor     edx, edx
0x1800023cf  call    cs:__imp_?GetStringAt@CPropertyName@@QEBAPEBGJ@Z; CPropertyName::GetStringAt(long)
0x1800023d5  mov     rsi, rax
0x1800023d8  nop     dword ptr [rax+rax+00000000h]
0x1800023e0  movzx   ebx, word ptr [rsi]
0x1800023e3  test    bx, bx
0x1800023e6  jz      loc_1800024AF
0x1800023ec  cmp     bx, 7Fh
0x1800023f0  ja      short loc_180002428
0x1800023f2  lea     eax, [rbx-41h]
0x1800023f5  cmp     ax, 19h
0x1800023f9  ja      short loc_1800023FF
0x1800023fb  add     bx, 20h ; ' '
0x1800023ff  movzx   ecx, word ptr [rdi]
0x180002402  cmp     cx, 7Fh
0x180002406  ja      short loc_18000246A
0x180002408  lea     eax, [rcx-41h]
0x18000240b  cmp     ax, 19h
0x18000240f  ja      short loc_180002415
0x180002411  add     cx, 20h ; ' '
0x180002415  cmp     bx, cx
0x180002418  jnz     loc_1800025F9
0x18000241e  add     rsi, 2
0x180002422  add     rdi, 2
0x180002426  jmp     short loc_1800023E0
0x180002428  mov     [rbp+SrcStr], bx
0x18000242c  xor     eax, eax
0x18000242e  mov     [rbp+DestStr], ax
0x180002432  mov     [rsp+70h+cchDest], 1; cchDest
0x18000243a  lea     rax, [rbp+DestStr]
0x18000243e  mov     [rsp+70h+lpDestStr], rax; lpDestStr
0x180002443  mov     r9d, 1; cchSrc
0x180002449  lea     r8, [rbp+SrcStr]; lpSrcStr
0x18000244d  mov     edx, 100h; dwMapFlags
0x180002452  mov     ecx, 7Fh; Locale
0x180002457  call    cs:__imp_LCMapStringW
0x18000245d  movzx   ebx, [rbp+DestStr]
0x180002461  test    eax, eax
0x180002463  cmovz   bx, [rbp+SrcStr]
0x180002468  jmp     short loc_1800023FF
0x18000246a  mov     [rbp+DestStr], cx
0x18000246e  xor     eax, eax
0x180002470  mov     [rbp+SrcStr], ax
0x180002474  mov     [rsp+70h+cchDest], 1; cchDest
0x18000247c  lea     rax, [rbp+SrcStr]
0x180002480  mov     [rsp+70h+lpDestStr], rax; lpDestStr
0x180002485  mov     r9d, 1; cchSrc
0x18000248b  lea     r8, [rbp+DestStr]; lpSrcStr
0x18000248f  mov     edx, 100h; dwMapFlags
0x180002494  mov     ecx, 7Fh; Locale
0x180002499  call    cs:__imp_LCMapStringW
0x18000249f  movzx   ecx, [rbp+SrcStr]
0x1800024a3  test    eax, eax
0x1800024a5  cmovz   cx, [rbp+DestStr]
0x1800024aa  jmp     loc_180002415
0x1800024af  cmp     [rdi], r12w
0x1800024b3  jnz     loc_1800023FF
0x1800024b9  cmp     dword ptr [r14+28h], 1
0x1800024be  jnz     loc_1800025F9
0x1800024c4  mov     r12, [r14+38h]
0x1800024c8  jmp     loc_1800025A3
0x1800024cd  cmp     eax, 3
0x1800024d0  jnz     loc_1800025B2
0x1800024d6  mov     rbx, [rbx+10h]
0x1800024da  cmp     dword ptr [rbx], 4
0x1800024dd  jnz     loc_1800025B2
0x1800024e3  cmp     dword ptr [rbx+80h], 4
0x1800024ea  jnz     loc_1800025B2
0x1800024f0  cmp     dword ptr [rbx+100h], 2
0x1800024f7  jnz     loc_1800025B2
0x1800024fd  cmp     dword ptr [rbx+28h], 9
0x180002501  jnz     loc_1800025B2
0x180002507  cmp     dword ptr [rbx+0A8h], 2
0x18000250e  jnz     loc_1800025B2
0x180002514  lea     rcx, [rbx+8]
0x180002518  xor     edx, edx
0x18000251a  call    cs:__imp_?GetStringAt@CPropertyName@@QEBAPEBGJ@Z; CPropertyName::GetStringAt(long)
0x180002520  mov     rcx, rax; unsigned __int16 *
0x180002523  lea     rdx, aThis; "__THIS"
0x18000252a  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x18000252f  test    eax, eax
0x180002531  jnz     short loc_1800025AE
0x180002533  lea     rcx, [rbx+88h]
0x18000253a  xor     edx, edx
0x18000253c  call    cs:__imp_?GetStringAt@CPropertyName@@QEBAPEBGJ@Z; CPropertyName::GetStringAt(long)
0x180002542  mov     rcx, rax; unsigned __int16 *
0x180002545  lea     rdx, aClass; "__CLASS"
0x18000254c  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180002551  test    eax, eax
0x180002553  jnz     short loc_1800025AE
0x180002555  mov     r9, [rbx+38h]
0x180002559  mov     rax, r9
0x18000255c  mov     r8, [rbx+0B8h]
0x180002563  sub     r8, r9
0x180002566  movzx   ecx, word ptr [rax]
0x180002569  movzx   edx, word ptr [rax+r8]
0x18000256e  sub     ecx, edx
0x180002570  jnz     short loc_18000257A
0x180002572  add     rax, 2
0x180002576  test    edx, edx
0x180002578  jnz     short loc_180002566
0x18000257a  mov     rdi, [rbp+arg_0]
0x18000257e  test    ecx, ecx
0x180002580  jnz     short loc_1800025B2
0x180002582  mov     r15, r9
0x180002585  mov     r13b, 1
0x180002588  jmp     short loc_1800025B2
0x18000258a  cmp     [rdi], r12w
0x18000258e  jnz     loc_18000262F
0x180002594  cmp     dword ptr [r14+28h], 9
0x180002599  jnz     loc_18000270D
0x18000259f  mov     r15, [r14+38h]
0x1800025a3  mov     rsi, [rbp+arg_10]
0x1800025a7  lea     r14, WPP_GLOBAL_Control
0x1800025ae  mov     rdi, [rbp+arg_0]
0x1800025b2  test    [rbp+arg_18], 200000h
0x1800025b9  jnz     loc_1800027E8
0x1800025bf  mov     byte ptr [rsp+70h+cchDest], r13b; bool
0x1800025c4  mov     r9, r15; unsigned __int16 *
0x1800025c7  mov     r8, r12; unsigned __int16 *
0x1800025ca  mov     rdx, rsi; struct IWbemObjectSink *
0x1800025cd  mov     rcx, rdi; this
0x1800025d0  call    ?EnumerateClasses@CNamespaceHandle@@IEAAJPEAUIWbemObjectSink@@PEBG1_N2@Z; CNamespaceHandle::EnumerateClasses(IWbemObjectSink *,ushort const *,ushort const *,bool,bool)
0x1800025d5  mov     ebx, eax
0x1800025d7  test    eax, eax
0x1800025d9  js      loc_180002A99
0x1800025df  xor     eax, eax
0x1800025e1  mov     rbx, [rsp+70h+arg_8]
0x1800025e9  add     rsp, 70h
0x1800025ed  pop     r15
0x1800025ef  pop     r14
0x1800025f1  pop     r13
0x1800025f3  pop     r12
0x1800025f5  pop     rdi
0x1800025f6  pop     rsi
0x1800025f7  pop     rbp
0x1800025f8  retn
0x1800025f9  lea     rdi, aThis; "__THIS"
0x180002600  xor     edx, edx
0x180002602  lea     rcx, [r14+8]
0x180002606  call    cs:__imp_?GetStringAt@CPropertyName@@QEBAPEBGJ@Z; CPropertyName::GetStringAt(long)
0x18000260c  mov     rsi, rax
0x18000260f  nop
0x180002610  movzx   ebx, word ptr [rsi]
0x180002613  test    bx, bx
0x180002616  jz      loc_18000258A
0x18000261c  cmp     bx, 7Fh
0x180002620  ja      short loc_180002658
0x180002622  lea     eax, [rbx-41h]
0x180002625  cmp     ax, 19h
0x180002629  ja      short loc_18000262F
0x18000262b  add     bx, 20h ; ' '
0x18000262f  movzx   ecx, word ptr [rdi]
0x180002632  cmp     cx, 7Fh
0x180002636  ja      short loc_18000269A
0x180002638  lea     eax, [rcx-41h]
0x18000263b  cmp     ax, 19h
0x18000263f  ja      short loc_180002645
0x180002641  add     cx, 20h ; ' '
0x180002645  cmp     bx, cx
0x180002648  jnz     loc_18000270D
0x18000264e  add     rsi, 2
0x180002652  add     rdi, 2
0x180002656  jmp     short loc_180002610
0x180002658  mov     [rbp+DestStr], bx
0x18000265c  xor     eax, eax
0x18000265e  mov     [rbp+SrcStr], ax
0x180002662  mov     [rsp+70h+cchDest], 1; cchDest
0x18000266a  lea     rax, [rbp+SrcStr]
0x18000266e  mov     [rsp+70h+lpDestStr], rax; lpDestStr
0x180002673  mov     r9d, 1; cchSrc
0x180002679  lea     r8, [rbp+DestStr]; lpSrcStr
0x18000267d  mov     edx, 100h; dwMapFlags
0x180002682  mov     ecx, 7Fh; Locale
0x180002687  call    cs:__imp_LCMapStringW
0x18000268d  movzx   ebx, [rbp+SrcStr]
0x180002691  test    eax, eax
0x180002693  cmovz   bx, [rbp+DestStr]
0x180002698  jmp     short loc_18000262F
0x18000269a  mov     [rbp+DestStr], cx
0x18000269e  xor     eax, eax
0x1800026a0  mov     [rbp+SrcStr], ax
0x1800026a4  mov     [rsp+70h+cchDest], 1; cchDest
0x1800026ac  lea     rax, [rbp+SrcStr]
0x1800026b0  mov     [rsp+70h+lpDestStr], rax; lpDestStr
0x1800026b5  mov     r9d, 1; cchSrc
0x1800026bb  lea     r8, [rbp+DestStr]; lpSrcStr
0x1800026bf  mov     edx, 100h; dwMapFlags
0x1800026c4  mov     ecx, 7Fh; Locale
0x1800026c9  call    cs:__imp_LCMapStringW
0x1800026cf  movzx   ecx, [rbp+SrcStr]
0x1800026d3  test    eax, eax
0x1800026d5  cmovz   cx, [rbp+DestStr]
0x1800026da  jmp     loc_180002645
0x1800026df  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800026e5  mov     edx, 80041033h
0x1800026ea  mov     rcx, rax
0x1800026ed  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800026f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026fa  cmp     rcx, r14
0x1800026fd  jnz     loc_1800028AB
0x180002703  mov     eax, 80041033h
0x180002708  jmp     loc_1800025E1
0x18000270d  xor     edx, edx
0x18000270f  lea     rcx, [r14+8]
0x180002713  call    cs:__imp_?GetStringAt@CPropertyName@@QEBAPEBGJ@Z; CPropertyName::GetStringAt(long)
0x180002719  mov     rcx, rax; unsigned __int16 *
0x18000271c  lea     rdx, aClass; "__CLASS"
0x180002723  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180002728  test    eax, eax
0x18000272a  jnz     loc_1800025A3
0x180002730  cmp     dword ptr [r14+28h], 1
0x180002735  jnz     loc_1800025A3
0x18000273b  mov     rdx, [r14+38h]; unsigned __int16 *
0x18000273f  test    rdx, rdx
0x180002742  jz      loc_1800025A3
0x180002748  mov     [rbp+var_10], r12
0x18000274c  mov     [rsp+70h+var_30], r12d; unsigned int
0x180002751  mov     [rsp+70h+var_38], r12; bool *
0x180002756  mov     [rsp+70h+var_40], r12; bool *
0x18000275b  mov     qword ptr [rsp+70h+cchDest], r12; __int64 *
0x180002760  mov     byte ptr [rsp+70h+lpDestStr], 1; bool
0x180002765  lea     r9, [rbp+var_10]; void **
0x180002769  lea     r8, IID__IWmiObject; struct _GUID *
0x180002770  mov     rcx, [rbp+arg_0]; this
0x180002774  call    ?GetClassDirect@CNamespaceHandle@@IEAAJPEBGAEBU_GUID@@PEAPEAX_NPEA_JPEA_N5K@Z; CNamespaceHandle::GetClassDirect(ushort const *,_GUID const &,void * *,bool,__int64 *,bool *,bool *,ulong)
0x180002779  mov     ebx, eax
0x18000277b  cmp     eax, 80041002h
0x180002780  jnz     loc_180002927
0x180002786  test    [rbp+arg_18], 200000h
0x18000278d  jz      loc_1800028DF
0x180002793  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180002799  mov     edx, ebx
0x18000279b  mov     rcx, rax
0x18000279e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800027a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027ab  lea     rax, WPP_GLOBAL_Control
0x1800027b2  cmp     rcx, rax
0x1800027b5  jz      short loc_1800027DE
0x1800027b7  test    byte ptr [rcx+1Ch], 1
0x1800027bb  jz      short loc_1800027DE
0x1800027bd  cmp     byte ptr [rcx+19h], 2
0x1800027c1  jb      short loc_1800027DE
0x1800027c3  mov     edx, 1C4h
0x1800027c8  mov     r9d, 80041002h
0x1800027ce  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800027d5  mov     rcx, [rcx+10h]
0x1800027d9  call    WPP_SF_d
0x1800027de  mov     eax, 80041002h
0x1800027e3  jmp     loc_1800025E1
0x1800027e8  mov     [rbp+var_10], 0
0x1800027f0  test    r12, r12
0x1800027f3  jz      loc_180002A49
0x1800027f9  mov     rdx, r12; unsigned __int16 *
0x1800027fc  xor     eax, eax
0x1800027fe  xor     r10d, r10d
0x180002801  lea     r9, [rbp+var_10]; void **
0x180002805  lea     r8, IID__IWmiObject; struct _GUID *
0x18000280c  mov     rcx, rdi; this
0x18000280f  mov     [rsp+70h+var_30], r10d; unsigned int
0x180002814  mov     [rsp+70h+var_38], rax; bool *
0x180002819  mov     [rsp+70h+var_40], rax; bool *
0x18000281e  mov     qword ptr [rsp+70h+cchDest], rax; __int64 *
0x180002823  mov     byte ptr [rsp+70h+lpDestStr], r10b; bool
0x180002828  call    ?GetClassDirect@CNamespaceHandle@@IEAAJPEBGAEBU_GUID@@PEAPEAX_NPEA_JPEA_N5K@Z; CNamespaceHandle::GetClassDirect(ushort const *,_GUID const &,void * *,bool,__int64 *,bool *,bool *,ulong)
0x18000282d  mov     ebx, eax
0x18000282f  test    eax, eax
  ... truncated ...
```
