# CNamespaceHandle::FileToClass(ushort const *,_IWmiObject * *,bool,__int64 *,bool *,ulong)

- ea: `0x1800178e0`
- end: `0x1800180b7`
- name: `?FileToClass@CNamespaceHandle@@IEAAJPEBGPEAPEAU_IWmiObject@@_NPEA_JPEA_NK@Z`
- size: `2007`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION ***this, const unsigned __int16 *, struct _IWmiObject **, char, __int64 *, bool *, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180006000`
- `0x18000a350`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180006000`
- `0x18000a350`
- `0x18000b650`
- `0x18000bf70`
- `0x1800178e0`
- `0x1800180c0`
- `0x18001e134`
- `0x180026124`
- `0x18002b7b6`
- `0x1800443f7`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180017b41`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180017b41`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180017ceb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180017d9c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180017df9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180018023`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180017ceb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180017d9c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180017df9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180018023`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x1800179a4`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180017a76`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180017bec`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x1800179a4`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180017a76`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180017bec`
- `wbemcomn!GetMemLogObject` at `0x180017d18`
- `wbemcomn!GetMemLogObject` at `0x180017d59`
- `wbemcomn!GetMemLogObject` at `0x180017db9`
- `wbemcomn!GetMemLogObject` at `0x180017e52`
- `wbemcomn!GetMemLogObject` at `0x180017edc`
- `wbemcomn!GetMemLogObject` at `0x180017f3b`
- `wbemcomn!GetMemLogObject` at `0x180017fd1`
- `wbemcomn!GetMemLogObject` at `0x180017d18`
- `wbemcomn!GetMemLogObject` at `0x180017d59`
- `wbemcomn!GetMemLogObject` at `0x180017db9`
- `wbemcomn!GetMemLogObject` at `0x180017e52`
- `wbemcomn!GetMemLogObject` at `0x180017edc`
- `wbemcomn!GetMemLogObject` at `0x180017f3b`
- `wbemcomn!GetMemLogObject` at `0x180017fd1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017d26`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017d67`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017dc4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017e5d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017eea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017f49`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017fdf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017d26`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017d67`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017dc4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017e5d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017eea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017f49`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017fdf`
- `OLEAUT32!__imp_VariantClear` at `0x180017ae1`
- `OLEAUT32!__imp_VariantClear` at `0x180017ccc`
- `OLEAUT32!__imp_VariantClear` at `0x180017ae1`
- `OLEAUT32!__imp_VariantClear` at `0x180017ccc`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::FileToClass(
        struct _RTL_CRITICAL_SECTION ***this,
        const unsigned __int16 *a2,
        struct _IWmiObject **a3,
        char a4,
        __int64 *a5,
        bool *a6,
        unsigned int a7)
{
  int v11; // eax
  unsigned int v12; // edi
  const wchar_t *v13; // rax
  __int64 v14; // rax
  int ClassByHash; // ebx
  int v16; // esi
  struct _IWmiObject *v17; // rdi
  void (__fastcall *v18)(struct _IWmiObject *, int *, __int64); // rbx
  __int64 v19; // rax
  unsigned __int8 *v21; // rsi
  struct MemoryPage *v22; // r15
  __int64 v23; // rbx
  void *v24; // rax
  void *v25; // r12
  void *v26; // rbx
  __int64 (__fastcall *v27)(void *, _QWORD, _QWORD, char *, int *, __int64, struct _IWmiObject **); // rdi
  __int64 v28; // rax
  int v29; // edi
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  CMemoryLog *v33; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v35; // rax
  CMemoryLog *v36; // rax
  bool v37; // [rsp+50h] [rbp-81h] BYREF
  unsigned int v38; // [rsp+54h] [rbp-7Dh] BYREF
  __int64 v39; // [rsp+58h] [rbp-79h] BYREF
  struct MemoryPage *p_pvarg; // [rsp+60h] [rbp-71h] BYREF
  unsigned __int8 *v41; // [rsp+68h] [rbp-69h] BYREF
  struct _IWmiObject *v42; // [rsp+70h] [rbp-61h] BYREF
  void *v43; // [rsp+78h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-51h] BYREF
  __int64 v45; // [rsp+98h] [rbp-39h] BYREF
  _BYTE v46[8]; // [rsp+A0h] [rbp-31h] BYREF
  void (__fastcall *v47)(struct MemoryPage *, unsigned __int8 *); // [rsp+A8h] [rbp-29h]
  struct MemoryPage *v48; // [rsp+B0h] [rbp-21h]
  unsigned __int8 *v49; // [rsp+B8h] [rbp-19h]
  void *v50; // [rsp+C0h] [rbp-11h]
  void *v51; // [rsp+C8h] [rbp-9h]

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v39 = 0;
  v38 = 0;
  v41 = 0;
  p_pvarg = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( !dword_180058AFC || g_bShuttingDown )
  {
    v12 = 1255;
    return A51TranslateErrorCode(v12, (__int64)a2, (__int64)a3);
  }
  v11 = CObjectHeap::ReadObject((CObjectHeap *)&qword_180058EF8, a2, &v38, &v41, &p_pvarg);
  v12 = v11;
  if ( v11 )
  {
    if ( v11 == 2 )
    {
      if ( g_pSystemClassNamespace )
      {
        if ( a7 != 2 )
        {
          v13 = (const wchar_t *)WString::operator unsigned short *(this + 4);
          if ( wcscmp_0(v13, L"__SYSTEMCLASS") )
          {
            v14 = -1;
            do
              ++v14;
            while ( a2[v14] );
            ClassByHash = CNamespaceHandle::GetClassByHash(g_pSystemClassNamespace, &a2[v14 - 64], 1, a3, &v39, 0, 0, 0);
            if ( ClassByHash >= 0 )
            {
              if ( a5 )
                *a5 = v39;
              v16 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)*a3 + 32LL))(
                      *a3,
                      L"__CLASS",
                      0,
                      &pvarg,
                      0,
                      0);
              if ( v16 >= 0 && pvarg.vt == 8 )
              {
                p_pvarg = (struct MemoryPage *)&pvarg;
                v17 = *a3;
                v18 = *(void (__fastcall **)(struct _IWmiObject *, int *, __int64))(*(_QWORD *)*a3 + 608LL);
                v19 = WString::operator unsigned short *(this + 4);
                v18(v17, &dword_1800599AC, v19);
                CHierarchyCache::AssertClass(this[11], *a3, pvarg.bstrVal, a4, v39, 1);
                if ( a6 )
                  *a6 = 1;
                if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    162,
                    WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
                    (unsigned int)v16);
                }
                VariantClear(&pvarg);
                return (unsigned int)v16;
              }
              MemLogObject = GetMemLogObject();
              CMemoryLog::Write(MemLogObject, -2147217393);
              if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  161,
                  WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
                  2147749903LL);
              }
              return 2147749903LL;
            }
            if ( ClassByHash == -2147217406 )
              return 2147749890LL;
            v33 = GetMemLogObject();
            CMemoryLog::Write(v33, ClassByHash);
            if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                160,
                WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
                (unsigned int)ClassByHash);
            }
            return (unsigned int)ClassByHash;
          }
        }
      }
    }
    return A51TranslateErrorCode(v12, (__int64)a2, (__int64)a3);
  }
  v21 = v41;
  v22 = p_pvarg;
  v46[0] = 0;
  v47 = CleanupReadObjectMemory;
  v48 = p_pvarg;
  v49 = v41;
  if ( v38 <= 8 )
  {
    v35 = GetMemLogObject();
    CMemoryLog::Write(v35, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 163, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    ScopeGuardImpl2<void (*)(MemoryPage *,unsigned char *),MemoryPage *,unsigned char *>::~ScopeGuardImpl2<void (*)(MemoryPage *,unsigned char *),MemoryPage *,unsigned char *>(v46);
    return 2147749894LL;
  }
  else
  {
    v23 = *(unsigned int *)v41;
    v24 = CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v23 + 1), 2u));
    v25 = v24;
    if ( v24 )
    {
      v50 = v24;
      *((_WORD *)v24 + v23) = 0;
      memcpy_0(v24, v21 + 4, 2 * v23);
      LODWORD(v41) = 2 * v23 + 4;
      p_pvarg = (struct MemoryPage *)&v21[(unsigned int)v41];
      v39 = *(_QWORD *)p_pvarg;
      v43 = 0;
      v45 = 0;
      v37 = 0;
      if ( CNamespaceHandle::GetClassDirect(
             (CNamespaceHandle *)this,
             (const unsigned __int16 *)v25,
             &IID__IWmiObject,
             &v43,
             0,
             &v45,
             &v37,
             0,
             0) < 0 )
      {
        v36 = GetMemLogObject();
        CMemoryLog::Write(v36, -2147217398);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            165,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            2147749898LL);
        }
        CWin32DefaultArena::WbemMemFree(v25);
        ScopeGuardImpl2<void (*)(MemoryPage *,unsigned char *),MemoryPage *,unsigned char *>::~ScopeGuardImpl2<void (*)(MemoryPage *,unsigned char *),MemoryPage *,unsigned char *>(v46);
        return 2147749898LL;
      }
      else
      {
        v26 = v43;
        v51 = v43;
        v42 = 0;
        v27 = *(__int64 (__fastcall **)(void *, _QWORD, _QWORD, char *, int *, __int64, struct _IWmiObject **))(*(_QWORD *)v43 + 768LL);
        v28 = WString::operator unsigned short *(this + 4);
        v29 = v27(v43, 0, v38 - (unsigned int)v41 - 8, (char *)p_pvarg + 8, &dword_1800599AC, v28, &v42);
        if ( v29 < 0 )
        {
          v32 = GetMemLogObject();
          CMemoryLog::Write(v32, v29);
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              166,
              WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
              (unsigned int)v29);
          }
          if ( v26 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v26 + 16LL))(v26);
          CWin32DefaultArena::WbemMemFree(v25);
          CleanupReadObjectMemory(v22, v21);
          return (unsigned int)v29;
        }
        else
        {
          if ( (*(int (__fastcall **)(struct _IWmiObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v42 + 32LL))(
                 v42,
                 L"__CLASS",
                 0,
                 &pvarg,
                 0,
                 0) < 0
            || pvarg.vt != 8 )
          {
            v31 = GetMemLogObject();
            CMemoryLog::Write(v31, -2147217393);
            if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                167,
                WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
                2147749903LL);
            }
            if ( v26 )
              (*(void (__fastcall **)(void *))(*(_QWORD *)v26 + 16LL))(v26);
            CWin32DefaultArena::WbemMemFree(v25);
            CleanupReadObjectMemory(v22, v21);
            return 2147749903LL;
          }
          p_pvarg = (struct MemoryPage *)&pvarg;
          CHierarchyCache::AssertClass(this[11], v42, pvarg.bstrVal, a4, v39, 0);
          *a3 = v42;
          if ( a5 )
            *a5 = v39;
          if ( a6 )
            *a6 = 0;
          VariantClear(&pvarg);
          if ( v26 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v26 + 16LL))(v26);
          CWin32DefaultArena::WbemMemFree(v25);
          CleanupReadObjectMemory(v22, v21);
          return 0;
        }
      }
    }
    else
    {
      v30 = GetMemLogObject();
      CMemoryLog::Write(v30, -2147217402);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          164,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          2147749894LL);
      }
      CleanupReadObjectMemory(v22, v21);
      return 2147749894LL;
    }
  }
}

```

## disassembly

```asm
0x1800178e0  mov     [rsp-8+arg_18], r9b
0x1800178e5  push    rbp
0x1800178e6  push    rbx
0x1800178e7  push    rsi
0x1800178e8  push    rdi
0x1800178e9  push    r12
0x1800178eb  push    r13
0x1800178ed  push    r14
0x1800178ef  push    r15
0x1800178f1  lea     rbp, [rsp-7]
0x1800178f6  sub     rsp, 0D8h
0x1800178fd  movzx   r12d, r9b
0x180017901  mov     r14, r8
0x180017904  mov     rbx, rdx
0x180017907  mov     r13, rcx
0x18001790a  lea     rax, WPP_GLOBAL_Control
0x180017911  mov     rcx, cs:WPP_GLOBAL_Control
0x180017918  cmp     rcx, rax
0x18001791b  jnz     loc_180017E13
0x180017921  xor     esi, esi
0x180017923  mov     [rbp+3Fh+var_B8], rsi
0x180017927  mov     [rbp+3Fh+var_BC], esi
0x18001792a  mov     [rbp+3Fh+var_A8], rsi
0x18001792e  mov     [rbp+3Fh+var_B0], rsi
0x180017932  xorps   xmm0, xmm0
0x180017935  xor     eax, eax
0x180017937  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x18001793b  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x18001793f  cmp     cs:dword_180058AFC, eax
0x180017945  jz      loc_180017E41
0x18001794b  cmp     cs:?g_bShuttingDown@@3_NA, al; bool g_bShuttingDown
0x180017951  jnz     loc_180017E41
0x180017957  lea     rax, [rbp+3Fh+var_B0]
0x18001795b  mov     [rsp+110h+var_F0], rax; struct MemoryPage **
0x180017960  lea     r9, [rbp+3Fh+var_A8]; unsigned __int8 **
0x180017964  lea     r8, [rbp+3Fh+var_BC]; unsigned int *
0x180017968  mov     rdx, rbx; unsigned __int16 *
0x18001796b  lea     rcx, qword_180058EF8; this
0x180017972  call    ?ReadObject@CObjectHeap@@QEAAJPEBGPEAKPEAPEAEPEAPEAVMemoryPage@@@Z; CObjectHeap::ReadObject(ushort const *,ulong *,uchar * *,MemoryPage * *)
0x180017977  mov     edi, eax
0x180017979  test    eax, eax
0x18001797b  jz      loc_180017AFD
0x180017981  cmp     eax, 2
0x180017984  jnz     loc_180017E46
0x18001798a  cmp     cs:?g_pSystemClassNamespace@@3PEAVCNamespaceHandle@@EA, rsi; CNamespaceHandle * g_pSystemClassNamespace
0x180017991  jz      loc_180017E46
0x180017997  cmp     [rbp+3Fh+arg_30], eax
0x18001799a  jz      loc_180017E46
0x1800179a0  lea     rcx, [r13+20h]
0x1800179a4  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x1800179aa  mov     rcx, rax; String1
0x1800179ad  lea     rdx, aSystemclass; "__SYSTEMCLASS"
0x1800179b4  call    wcscmp_0
0x1800179b9  test    eax, eax
0x1800179bb  jz      loc_180017E46
0x1800179c1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800179c8  nop     dword ptr [rax+rax+00000000h]
0x1800179d0  inc     rax
0x1800179d3  cmp     [rbx+rax*2], si
0x1800179d7  jnz     short loc_1800179D0
0x1800179d9  add     rax, 0FFFFFFFFFFFFFFC0h
0x1800179dd  lea     rdx, [rbx+rax*2]; unsigned __int16 *
0x1800179e1  mov     dword ptr [rsp+110h+var_D8], esi; unsigned int
0x1800179e5  mov     [rsp+110h+var_E0], rsi; bool *
0x1800179ea  mov     [rsp+110h+var_E8], rsi; bool *
0x1800179ef  lea     rax, [rbp+3Fh+var_B8]
0x1800179f3  mov     [rsp+110h+var_F0], rax; __int64 *
0x1800179f8  mov     r9, r14; struct _IWmiObject **
0x1800179fb  mov     r8b, 1; bool
0x1800179fe  mov     rcx, cs:?g_pSystemClassNamespace@@3PEAVCNamespaceHandle@@EA; this
0x180017a05  call    ?GetClassByHash@CNamespaceHandle@@IEAAJPEBG_NPEAPEAU_IWmiObject@@PEA_JPEA_N4K@Z; CNamespaceHandle::GetClassByHash(ushort const *,bool,_IWmiObject * *,__int64 *,bool *,bool *,ulong)
0x180017a0a  mov     ebx, eax
0x180017a0c  test    eax, eax
0x180017a0e  js      loc_180017D05
0x180017a14  mov     rcx, [rbp+3Fh+arg_20]
0x180017a18  test    rcx, rcx
0x180017a1b  jnz     loc_180017EA1
0x180017a21  mov     rcx, [r14]
0x180017a24  mov     rax, [rcx]
0x180017a27  mov     [rsp+110h+var_E8], rsi
0x180017a2c  mov     [rsp+110h+var_F0], rsi
0x180017a31  lea     r9, [rbp+3Fh+pvarg]
0x180017a35  xor     r8d, r8d
0x180017a38  lea     rdx, aClass; "__CLASS"
0x180017a3f  mov     rax, [rax+20h]
0x180017a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a48  mov     esi, eax
0x180017a4a  test    eax, eax
0x180017a4c  js      loc_180017EDC
0x180017a52  cmp     word ptr [rbp+3Fh+pvarg], 8
0x180017a57  jnz     loc_180017EDC
0x180017a5d  lea     rax, [rbp+3Fh+pvarg]
0x180017a61  mov     [rbp+3Fh+var_B0], rax
0x180017a65  mov     rdi, [r14]
0x180017a68  mov     rdx, [rdi]
0x180017a6b  mov     rbx, [rdx+260h]
0x180017a72  lea     rcx, [r13+20h]
0x180017a76  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x180017a7c  mov     r8, rax
0x180017a7f  lea     rdx, dword_1800599AC
0x180017a86  mov     rcx, rdi
0x180017a89  mov     rax, rbx
0x180017a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a91  mov     byte ptr [rsp+110h+var_E8], 1; bool
0x180017a96  mov     rax, [rbp+3Fh+var_B8]
0x180017a9a  mov     [rsp+110h+var_F0], rax; __int64
0x180017a9f  movzx   r9d, r12b; bool
0x180017aa3  mov     r8, qword ptr [rbp+3Fh+pvarg+8]; unsigned __int16 *
0x180017aa7  mov     rdx, [r14]; struct _IWmiObject *
0x180017aaa  mov     rcx, [r13+58h]; this
0x180017aae  call    ?AssertClass@CHierarchyCache@@QEAAJPEAU_IWmiObject@@PEBG_N_J2@Z; CHierarchyCache::AssertClass(_IWmiObject *,ushort const *,bool,__int64,bool)
0x180017ab3  mov     rax, [rbp+3Fh+arg_28]
0x180017ab7  test    rax, rax
0x180017aba  jnz     loc_180017EAD
0x180017ac0  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ac7  lea     rax, WPP_GLOBAL_Control
0x180017ace  cmp     rcx, rax
0x180017ad1  jz      short loc_180017ADD
0x180017ad3  test    byte ptr [rcx+1Ch], 1
0x180017ad7  jnz     loc_180017EB5
0x180017add  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x180017ae1  call    cs:__imp_VariantClear
0x180017ae7  mov     eax, esi
0x180017ae9  add     rsp, 0D8h
0x180017af0  pop     r15
0x180017af2  pop     r14
0x180017af4  pop     r13
0x180017af6  pop     r12
0x180017af8  pop     rdi
0x180017af9  pop     rsi
0x180017afa  pop     rbx
0x180017afb  pop     rbp
0x180017afc  retn
0x180017afd  mov     rsi, [rbp+3Fh+var_A8]
0x180017b01  mov     r15, [rbp+3Fh+var_B0]
0x180017b05  mov     [rbp+3Fh+var_70], 0
0x180017b09  lea     rax, ?CleanupReadObjectMemory@@YAXPEAVMemoryPage@@PEAE@Z; CleanupReadObjectMemory(MemoryPage *,uchar *)
0x180017b10  mov     [rbp+3Fh+var_68], rax
0x180017b14  mov     [rbp+3Fh+var_60], r15
0x180017b18  mov     [rbp+3Fh+var_58], rsi
0x180017b1c  cmp     [rbp+3Fh+var_BC], 8
0x180017b20  jbe     loc_180017F3B
0x180017b26  mov     ebx, [rsi]
0x180017b28  lea     ecx, [rbx+1]
0x180017b2b  mov     eax, 2
0x180017b30  mul     rcx
0x180017b33  mov     rcx, rax
0x180017b36  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180017b3d  cmovb   rcx, rax
0x180017b41  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180017b47  mov     r12, rax
0x180017b4a  test    rax, rax
0x180017b4d  jz      loc_180017D18
0x180017b53  mov     [rbp+3Fh+var_50], rax
0x180017b57  lea     r8, [rbx+rbx]; Size
0x180017b5b  xor     edi, edi
0x180017b5d  mov     [r8+rax], di
0x180017b62  lea     rdx, [rsi+4]; Src
0x180017b66  mov     rcx, rax; void *
0x180017b69  call    memcpy_0
0x180017b6e  lea     eax, ds:4[rbx*2]
0x180017b75  mov     dword ptr [rbp+3Fh+var_A8], eax
0x180017b78  add     rax, rsi
0x180017b7b  mov     [rbp+3Fh+var_B0], rax
0x180017b7f  mov     rax, [rax]
0x180017b82  mov     [rbp+3Fh+var_B8], rax
0x180017b86  mov     [rbp+3Fh+var_98], rdi
0x180017b8a  mov     [rbp+3Fh+var_78], rdi
0x180017b8e  mov     [rsp+110h+var_C0], dil
0x180017b93  mov     [rsp+110h+var_D0], edi; unsigned int
0x180017b97  mov     [rsp+110h+var_D8], rdi; bool *
0x180017b9c  lea     rax, [rsp+110h+var_C0]
0x180017ba1  mov     [rsp+110h+var_E0], rax; bool *
0x180017ba6  lea     rax, [rbp+3Fh+var_78]
0x180017baa  mov     [rsp+110h+var_E8], rax; __int64 *
0x180017baf  mov     byte ptr [rsp+110h+var_F0], dil; bool
0x180017bb4  lea     r9, [rbp+3Fh+var_98]; void **
0x180017bb8  lea     r8, IID__IWmiObject; struct _GUID *
0x180017bbf  mov     rdx, r12; unsigned __int16 *
0x180017bc2  mov     rcx, r13; this
0x180017bc5  call    ?GetClassDirect@CNamespaceHandle@@IEAAJPEBGAEBU_GUID@@PEAPEAX_NPEA_JPEA_N5K@Z; CNamespaceHandle::GetClassDirect(ushort const *,_GUID const &,void * *,bool,__int64 *,bool *,bool *,ulong)
0x180017bca  test    eax, eax
0x180017bcc  js      loc_180017FD1
0x180017bd2  mov     rbx, [rbp+3Fh+var_98]
0x180017bd6  mov     [rbp+3Fh+var_48], rbx
0x180017bda  mov     [rbp+3Fh+var_A0], rdi
0x180017bde  mov     rax, [rbx]
0x180017be1  mov     rdi, [rax+300h]
0x180017be8  lea     rcx, [r13+20h]
0x180017bec  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x180017bf2  mov     r9, [rbp+3Fh+var_B0]
0x180017bf6  add     r9, 8
0x180017bfa  mov     r8d, [rbp+3Fh+var_BC]
0x180017bfe  sub     r8d, dword ptr [rbp+3Fh+var_A8]
0x180017c02  sub     r8d, 8
0x180017c06  lea     rdx, [rbp+3Fh+var_A0]
0x180017c0a  mov     [rsp+110h+var_E0], rdx
0x180017c0f  mov     [rsp+110h+var_E8], rax
0x180017c14  lea     rax, dword_1800599AC
0x180017c1b  mov     [rsp+110h+var_F0], rax
0x180017c20  xor     edx, edx
0x180017c22  mov     rcx, [rbp+3Fh+var_98]
0x180017c26  mov     rax, rdi
0x180017c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c2e  mov     edi, eax
0x180017c30  test    eax, eax
0x180017c32  js      loc_180017DB9
0x180017c38  mov     rcx, [rbp+3Fh+var_A0]
0x180017c3c  mov     rax, [rcx]
0x180017c3f  mov     [rsp+110h+var_E8], 0
0x180017c48  mov     [rsp+110h+var_F0], 0
0x180017c51  lea     r9, [rbp+3Fh+pvarg]
0x180017c55  xor     r8d, r8d
0x180017c58  lea     rdx, aClass; "__CLASS"
0x180017c5f  mov     rax, [rax+20h]
0x180017c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c68  test    eax, eax
0x180017c6a  js      loc_180017D59
0x180017c70  cmp     word ptr [rbp+3Fh+pvarg], 8
0x180017c75  jnz     loc_180017D59
0x180017c7b  lea     rax, [rbp+3Fh+pvarg]
0x180017c7f  mov     [rbp+3Fh+var_B0], rax
0x180017c83  mov     byte ptr [rsp+110h+var_E8], 0; bool
0x180017c88  mov     rax, [rbp+3Fh+var_B8]
0x180017c8c  mov     [rsp+110h+var_F0], rax; __int64
0x180017c91  movzx   r9d, [rbp+3Fh+arg_18]; bool
0x180017c96  mov     r8, qword ptr [rbp+3Fh+pvarg+8]; unsigned __int16 *
0x180017c9a  mov     rdx, [rbp+3Fh+var_A0]; struct _IWmiObject *
0x180017c9e  mov     rcx, [r13+58h]; this
0x180017ca2  call    ?AssertClass@CHierarchyCache@@QEAAJPEAU_IWmiObject@@PEBG_N_J2@Z; CHierarchyCache::AssertClass(_IWmiObject *,ushort const *,bool,__int64,bool)
0x180017ca7  mov     rax, [rbp+3Fh+var_A0]
0x180017cab  mov     [r14], rax
0x180017cae  mov     rcx, [rbp+3Fh+arg_20]
0x180017cb2  test    rcx, rcx
0x180017cb5  jnz     loc_18001806E
0x180017cbb  mov     rax, [rbp+3Fh+arg_28]
0x180017cbf  test    rax, rax
0x180017cc2  jnz     loc_18001807A
0x180017cc8  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x180017ccc  call    cs:__imp_VariantClear
0x180017cd2  nop
0x180017cd3  test    rbx, rbx
0x180017cd6  jz      short loc_180017CE8
0x180017cd8  mov     rax, [rbx]
0x180017cdb  mov     rcx, rbx
0x180017cde  mov     rax, [rax+10h]
0x180017ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ce7  nop
0x180017ce8  mov     rcx, r12
0x180017ceb  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180017cf1  nop
0x180017cf2  mov     rdx, rsi; unsigned __int8 *
0x180017cf5  mov     rcx, r15; struct MemoryPage *
0x180017cf8  call    ?CleanupReadObjectMemory@@YAXPEAVMemoryPage@@PEAE@Z; CleanupReadObjectMemory(MemoryPage *,uchar *)
0x180017cfd  nop
0x180017cfe  xor     eax, eax
0x180017d00  jmp     loc_180017AE9
0x180017d05  cmp     ebx, 80041002h
0x180017d0b  jnz     loc_180017E52
0x180017d11  mov     eax, ebx
0x180017d13  jmp     loc_180017AE9
0x180017d18  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180017d1e  mov     edx, 80041006h
0x180017d23  mov     rcx, rax
0x180017d26  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180017d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d33  lea     rax, WPP_GLOBAL_Control
0x180017d3a  cmp     rcx, rax
0x180017d3d  jnz     loc_180017F9D
0x180017d43  mov     rdx, rsi; unsigned __int8 *
0x180017d46  mov     rcx, r15; struct MemoryPage *
0x180017d49  call    ?CleanupReadObjectMemory@@YAXPEAVMemoryPage@@PEAE@Z; CleanupReadObjectMemory(MemoryPage *,uchar *)
0x180017d4e  nop
0x180017d4f  mov     eax, 80041006h
0x180017d54  jmp     loc_180017AE9
0x180017d59  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180017d5f  mov     edx, 8004100Fh
0x180017d64  mov     rcx, rax
0x180017d67  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180017d6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d74  lea     rax, WPP_GLOBAL_Control
0x180017d7b  cmp     rcx, rax
0x180017d7e  jnz     loc_180018082
0x180017d84  test    rbx, rbx
0x180017d87  jz      short loc_180017D99
0x180017d89  mov     rax, [rbx]
0x180017d8c  mov     rcx, rbx
0x180017d8f  mov     rax, [rax+10h]
0x180017d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d98  nop
0x180017d99  mov     rcx, r12
0x180017d9c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180017da2  nop
0x180017da3  mov     rdx, rsi; unsigned __int8 *
0x180017da6  mov     rcx, r15; struct MemoryPage *
0x180017da9  call    ?CleanupReadObjectMemory@@YAXPEAVMemoryPage@@PEAE@Z; CleanupReadObjectMemory(MemoryPage *,uchar *)
0x180017dae  nop
0x180017daf  mov     eax, 8004100Fh
0x180017db4  jmp     loc_180017AE9
0x180017db9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
  ... truncated ...
```
