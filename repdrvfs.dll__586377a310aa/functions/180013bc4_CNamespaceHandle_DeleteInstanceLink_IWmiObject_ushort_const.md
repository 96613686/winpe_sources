# CNamespaceHandle::DeleteInstanceLink(_IWmiObject *,ushort const *)

- ea: `0x180013bc4`
- end: `0x180013f0d`
- name: `?DeleteInstanceLink@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@PEBG@Z`
- size: `841`
- prototype: `__int64 __fastcall(CNamespaceHandle *__hidden this, struct _IWmiObject *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001404c`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180013974`
- `0x180013bc4`
- `0x180013f90`
- `0x18001e134`
- `0x180020228`
- `0x180048010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180013e2d`
- `msvcrt!wcsrchr` at `0x180013e2d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013cd0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013cd0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013d37`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013d9d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013e81`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013ed1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013edd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013d37`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013d9d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013e81`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013ed1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013edd`
- `wbemcomn!GetMemLogObject` at `0x180013c70`
- `wbemcomn!GetMemLogObject` at `0x180013cef`
- `wbemcomn!GetMemLogObject` at `0x180013d5c`
- `wbemcomn!GetMemLogObject` at `0x180013e38`
- `wbemcomn!GetMemLogObject` at `0x180013c70`
- `wbemcomn!GetMemLogObject` at `0x180013cef`
- `wbemcomn!GetMemLogObject` at `0x180013d5c`
- `wbemcomn!GetMemLogObject` at `0x180013e38`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013c80`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013cff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013d67`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013e48`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013c80`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013cff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013d67`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013e48`
- `OLEAUT32!__imp_VariantInit` at `0x180013c2e`
- `OLEAUT32!__imp_VariantInit` at `0x180013c2e`
- `OLEAUT32!__imp_VariantClear` at `0x180013eec`
- `OLEAUT32!__imp_VariantClear` at `0x180013eec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNamespaceHandle::DeleteInstanceLink(
        CNamespaceHandle *this,
        struct _IWmiObject *a2,
        const unsigned __int16 *a3)
{
  CMemoryLog *MemLogObject; // rax
  int v7; // ebx
  const unsigned __int16 *bstrVal; // rbx
  char *v9; // rax
  char *v10; // rdi
  CMemoryLog *v11; // rax
  CMemoryLog *v12; // rax
  __int64 v13; // rdx
  _WORD *v14; // rax
  __int64 v15; // r8
  __int64 v16; // rcx
  const wchar_t *v17; // r9
  __int64 v18; // rax
  wchar_t *v19; // rdx
  wchar_t v20; // r8
  wchar_t *v21; // rcx
  wchar_t *v22; // rax
  CMemoryLog *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  unsigned int v26; // eax
  VARIANTARG pvarg; // [rsp+40h] [rbp-48h] BYREF
  char *v29; // [rsp+98h] [rbp+10h] BYREF
  VARIANTARG *p_pvarg; // [rsp+A8h] [rbp+20h]

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 338, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  p_pvarg = &pvarg;
  if ( (*(int (__fastcall **)(struct _IWmiObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)a2 + 32LL))(
         a2,
         L"__CLASS",
         0,
         &pvarg,
         0,
         0) < 0 )
  {
    MemLogObject = GetMemLogObject();
    v7 = -2147217393;
    CMemoryLog::Write(MemLogObject, -2147217393);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 339, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749903LL);
    }
    goto LABEL_46;
  }
  bstrVal = pvarg.bstrVal;
  v9 = (char *)CWin32DefaultArena::WbemMemAlloc(0x2E6u);
  v10 = v9;
  v29 = v9;
  if ( v9 )
  {
    *(_WORD *)v9 = 0;
    v7 = CNamespaceHandle::ConstructLinkDirFromClass(this, (struct CFileName *)&v29, bstrVal);
    if ( v7 < 0 )
    {
      v12 = GetMemLogObject();
      CMemoryLog::Write(v12, v7);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          341,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          (unsigned int)v7);
      }
LABEL_22:
      CWin32DefaultArena::WbemMemFree(v10);
      goto LABEL_46;
    }
    v13 = 371;
    v14 = v10;
    do
    {
      if ( !*v14 )
        break;
      ++v14;
      --v13;
    }
    while ( v13 );
    v15 = (371 - v13) & -(__int64)(v13 != 0);
    if ( v13 )
    {
      v16 = 2147483646;
      v17 = L"\\IL_";
      v18 = 371 - v15;
      v19 = (wchar_t *)&v10[2 * v15];
      if ( v15 != 371 )
      {
        do
        {
          if ( !v16 )
            break;
          v20 = *v17;
          if ( !*v17 )
            break;
          ++v17;
          *v19++ = v20;
          --v16;
          --v18;
        }
        while ( v18 );
      }
      v21 = v19 - 1;
      if ( v18 )
        v21 = v19;
      *v21 = 0;
    }
    v22 = wcsrchr(a3, 0x5Fu);
    if ( !v22 )
    {
      v23 = GetMemLogObject();
      v7 = -2147217398;
      CMemoryLog::Write(v23, -2147217398);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          342,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          2147749898LL);
      }
      goto LABEL_22;
    }
    StringCchCatW((unsigned __int16 *)v10, 0x173u, v22 + 1);
    if ( !dword_180058AFC || g_bShuttingDown )
    {
      v26 = 1255;
    }
    else
    {
      v26 = CObjectHeap::DeleteLink((CObjectHeap *)&qword_180058EF8, (const unsigned __int16 *)v10);
      if ( !v26 )
      {
        CWin32DefaultArena::WbemMemFree(v10);
        v7 = 0;
        goto LABEL_46;
      }
    }
    v7 = A51TranslateErrorCode(v26, v24, v25);
    CWin32DefaultArena::WbemMemFree(v10);
  }
  else
  {
    v11 = GetMemLogObject();
    v7 = -2147217402;
    CMemoryLog::Write(v11, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 340, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    CWin32DefaultArena::WbemMemFree(0);
  }
LABEL_46:
  VariantClear(&pvarg);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180013bc4  mov     [rsp+arg_0], rbx
0x180013bc9  mov     [rsp+arg_10], rbp
0x180013bce  push    rsi
0x180013bcf  push    rdi
0x180013bd0  push    r12
0x180013bd2  push    r14
0x180013bd4  push    r15
0x180013bd6  sub     rsp, 60h
0x180013bda  mov     rbp, r8
0x180013bdd  mov     rbx, rdx
0x180013be0  mov     rsi, rcx
0x180013be3  lea     r12, WPP_GLOBAL_Control
0x180013bea  lea     r15, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180013bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180013bf8  cmp     rcx, r12
0x180013bfb  jz      short loc_180013C1A
0x180013bfd  test    byte ptr [rcx+1Ch], 1
0x180013c01  jz      short loc_180013C1A
0x180013c03  cmp     byte ptr [rcx+19h], 5
0x180013c07  jb      short loc_180013C1A
0x180013c09  mov     edx, 152h
0x180013c0e  mov     r8, r15
0x180013c11  mov     rcx, [rcx+10h]
0x180013c15  call    WPP_SF_
0x180013c1a  xorps   xmm0, xmm0
0x180013c1d  xor     eax, eax
0x180013c1f  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x180013c24  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x180013c29  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180013c2e  call    cs:__imp_VariantInit
0x180013c34  lea     rax, [rsp+88h+pvarg]
0x180013c39  mov     [rsp+88h+arg_18], rax
0x180013c41  mov     rax, [rbx]
0x180013c44  xor     r14d, r14d
0x180013c47  mov     [rsp+88h+var_60], r14
0x180013c4c  mov     [rsp+88h+var_68], r14
0x180013c51  lea     r9, [rsp+88h+pvarg]
0x180013c56  xor     r8d, r8d
0x180013c59  lea     rdx, aClass; "__CLASS"
0x180013c60  mov     rcx, rbx
0x180013c63  mov     rax, [rax+20h]
0x180013c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c6c  test    eax, eax
0x180013c6e  jns     short loc_180013CC6
0x180013c70  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180013c76  mov     ebx, 8004100Fh
0x180013c7b  mov     edx, ebx
0x180013c7d  mov     rcx, rax
0x180013c80  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013c86  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c8d  cmp     rcx, r12
0x180013c90  jz      loc_180013EE7
0x180013c96  test    byte ptr [rcx+1Ch], 1
0x180013c9a  jz      loc_180013EE7
0x180013ca0  cmp     byte ptr [rcx+19h], 2
0x180013ca4  jb      loc_180013EE7
0x180013caa  mov     edx, 153h
0x180013caf  mov     r9d, 8004100Fh
0x180013cb5  mov     r8, r15
0x180013cb8  mov     rcx, [rcx+10h]
0x180013cbc  call    WPP_SF_d
0x180013cc1  jmp     loc_180013EE7
0x180013cc6  mov     rbx, qword ptr [rsp+88h+pvarg+8]
0x180013ccb  mov     ecx, 2E6h
0x180013cd0  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180013cd6  mov     rdi, rax
0x180013cd9  mov     [rsp+88h+arg_8], rax
0x180013ce1  test    rax, rax
0x180013ce4  jz      short loc_180013CEA
0x180013ce6  mov     [rax], r14w
0x180013cea  test    rdi, rdi
0x180013ced  jnz     short loc_180013D43
0x180013cef  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180013cf5  mov     ebx, 80041006h
0x180013cfa  mov     edx, ebx
0x180013cfc  mov     rcx, rax
0x180013cff  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013d05  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d0c  cmp     rcx, r12
0x180013d0f  jz      short loc_180013D35
0x180013d11  test    byte ptr [rcx+1Ch], 1
0x180013d15  jz      short loc_180013D35
0x180013d17  cmp     byte ptr [rcx+19h], 2
0x180013d1b  jb      short loc_180013D35
0x180013d1d  mov     edx, 154h
0x180013d22  mov     r9d, 80041006h
0x180013d28  mov     r8, r15
0x180013d2b  mov     rcx, [rcx+10h]
0x180013d2f  call    WPP_SF_d
0x180013d34  nop
0x180013d35  xor     ecx, ecx
0x180013d37  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013d3d  nop
0x180013d3e  jmp     loc_180013EE7
0x180013d43  mov     r8, rbx; unsigned __int16 *
0x180013d46  lea     rdx, [rsp+88h+arg_8]; struct CFileName *
0x180013d4e  mov     rcx, rsi; this
0x180013d51  call    ?ConstructLinkDirFromClass@CNamespaceHandle@@IEAAJAEAVCFileName@@PEBG@Z; CNamespaceHandle::ConstructLinkDirFromClass(CFileName &,ushort const *)
0x180013d56  mov     ebx, eax
0x180013d58  test    eax, eax
0x180013d5a  jns     short loc_180013DA9
0x180013d5c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180013d62  mov     edx, ebx
0x180013d64  mov     rcx, rax
0x180013d67  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013d6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d74  cmp     rcx, r12
0x180013d77  jz      short loc_180013D9A
0x180013d79  test    byte ptr [rcx+1Ch], 1
0x180013d7d  jz      short loc_180013D9A
0x180013d7f  cmp     byte ptr [rcx+19h], 2
0x180013d83  jb      short loc_180013D9A
0x180013d85  mov     edx, 155h
0x180013d8a  mov     r9d, ebx
0x180013d8d  mov     r8, r15
0x180013d90  mov     rcx, [rcx+10h]
0x180013d94  call    WPP_SF_d
0x180013d99  nop
0x180013d9a  mov     rcx, rdi
0x180013d9d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013da3  nop
0x180013da4  jmp     loc_180013EE7
0x180013da9  mov     ebx, 173h
0x180013dae  mov     edx, ebx
0x180013db0  mov     rax, rdi
0x180013db3  cmp     [rax], r14w
0x180013db7  jz      short loc_180013DC3
0x180013db9  add     rax, 2
0x180013dbd  sub     rdx, 1
0x180013dc1  jnz     short loc_180013DB3
0x180013dc3  mov     rax, rdx
0x180013dc6  mov     rcx, rbx
0x180013dc9  sub     rcx, rdx
0x180013dcc  neg     rax
0x180013dcf  sbb     r8, r8
0x180013dd2  and     r8, rcx
0x180013dd5  test    rdx, rdx
0x180013dd8  jz      short loc_180013E25
0x180013dda  mov     ecx, 7FFFFFFEh
0x180013ddf  lea     r9, aIl; "\\IL_"
0x180013de6  mov     rax, rbx
0x180013de9  sub     rax, r8
0x180013dec  lea     rdx, [rdi+r8*2]
0x180013df0  jz      short loc_180013E16
0x180013df2  test    rcx, rcx
0x180013df5  jz      short loc_180013E16
0x180013df7  movzx   r8d, word ptr [r9]
0x180013dfb  test    r8w, r8w
0x180013dff  jz      short loc_180013E16
0x180013e01  add     r9, 2
0x180013e05  mov     [rdx], r8w
0x180013e09  add     rdx, 2
0x180013e0d  dec     rcx
0x180013e10  sub     rax, 1
0x180013e14  jnz     short loc_180013DF2
0x180013e16  lea     rcx, [rdx-2]
0x180013e1a  test    rax, rax
0x180013e1d  cmovnz  rcx, rdx
0x180013e21  mov     [rcx], r14w
0x180013e25  mov     edx, 5Fh ; '_'; Ch
0x180013e2a  mov     rcx, rbp; Str
0x180013e2d  call    cs:__imp_wcsrchr
0x180013e33  test    rax, rax
0x180013e36  jnz     short loc_180013E8A
0x180013e38  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180013e3e  mov     ebx, 8004100Ah
0x180013e43  mov     edx, ebx
0x180013e45  mov     rcx, rax
0x180013e48  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e55  cmp     rcx, r12
0x180013e58  jz      short loc_180013E7E
0x180013e5a  test    byte ptr [rcx+1Ch], 1
0x180013e5e  jz      short loc_180013E7E
0x180013e60  cmp     byte ptr [rcx+19h], 2
0x180013e64  jb      short loc_180013E7E
0x180013e66  mov     edx, 156h
0x180013e6b  mov     r9d, 8004100Ah
0x180013e71  mov     r8, r15
0x180013e74  mov     rcx, [rcx+10h]
0x180013e78  call    WPP_SF_d
0x180013e7d  nop
0x180013e7e  mov     rcx, rdi
0x180013e81  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013e87  nop
0x180013e88  jmp     short loc_180013EE7
0x180013e8a  lea     r8, [rax+2]; unsigned __int16 *
0x180013e8e  mov     rdx, rbx; unsigned __int64
0x180013e91  mov     rcx, rdi; unsigned __int16 *
0x180013e94  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013e99  cmp     cs:dword_180058AFC, r14d
0x180013ea0  jnz     short loc_180013EA9
0x180013ea2  mov     eax, 4E7h
0x180013ea7  jmp     short loc_180013EC5
0x180013ea9  cmp     cs:?g_bShuttingDown@@3_NA, r14b; bool g_bShuttingDown
0x180013eb0  jnz     short loc_180013EA2
0x180013eb2  mov     rdx, rdi; unsigned __int16 *
0x180013eb5  lea     rcx, qword_180058EF8; this
0x180013ebc  call    ?DeleteLink@CObjectHeap@@QEAAJPEBG@Z; CObjectHeap::DeleteLink(ushort const *)
0x180013ec1  test    eax, eax
0x180013ec3  jz      short loc_180013EDA
0x180013ec5  mov     ecx, eax; int
0x180013ec7  call    ?A51TranslateErrorCode@@YAJJ@Z; A51TranslateErrorCode(long)
0x180013ecc  mov     ebx, eax
0x180013ece  mov     rcx, rdi
0x180013ed1  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013ed7  nop
0x180013ed8  jmp     short loc_180013EE7
0x180013eda  mov     rcx, rdi
0x180013edd  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013ee3  nop
0x180013ee4  mov     ebx, r14d
0x180013ee7  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180013eec  call    cs:__imp_VariantClear
0x180013ef2  mov     eax, ebx
0x180013ef4  lea     r11, [rsp+88h+var_28]
0x180013ef9  mov     rbx, [r11+30h]
0x180013efd  mov     rbp, [r11+40h]
0x180013f01  mov     rsp, r11
0x180013f04  pop     r15
0x180013f06  pop     r14
0x180013f08  pop     r12
0x180013f0a  pop     rdi
0x180013f0b  pop     rsi
0x180013f0c  retn
```
