# CEditSessionObject::CompClauseToResultClause(CWCompClause &,uint)

- ea: `0x18003c9cc`
- end: `0x18003cbab`
- name: `?CompClauseToResultClause@CEditSessionObject@@IEAAJAEAVCWCompClause@@I@Z`
- size: `479`
- prototype: `int(CEditSessionObject *__hidden this, struct CWCompClause *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013a70`
- `0x18003b014`

## callees

- `0x1800139a4`
- `0x1800185f0`
- `0x18001a460`
- `0x18003c9cc`
- `0x18003cbb4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003cb21`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003cb21`
- `IMM32!ImmLockIMC` at `0x18003ca14`
- `IMM32!ImmLockIMC` at `0x18003ca14`
- `IMM32!ImmUnlockIMC` at `0x18003ca64`
- `IMM32!ImmUnlockIMC` at `0x18003cb87`
- `IMM32!ImmUnlockIMC` at `0x18003ca64`
- `IMM32!ImmUnlockIMC` at `0x18003cb87`
- `IMM32!ImmLockIMCC` at `0x18003ca99`
- `IMM32!ImmLockIMCC` at `0x18003ca99`
- `ext-ms-win-imm-l1-1-0!ImmGetCompositionStringW` at `0x18003caef`
- `ext-ms-win-imm-l1-1-0!ImmGetCompositionStringW` at `0x18003cb42`
- `ext-ms-win-imm-l1-1-0!ImmGetCompositionStringW` at `0x18003caef`
- `ext-ms-win-imm-l1-1-0!ImmGetCompositionStringW` at `0x18003cb42`

## pseudocode

```c
__int64 __fastcall CEditSessionObject::CompClauseToResultClause(
        CEditSessionObject *this,
        struct CWCompClause *a2,
        int a3)
{
  HIMC v3; // rsi
  LPINPUTCONTEXT v7; // rax
  LPINPUTCONTEXT v8; // rdi
  HIMCC hCompStr; // rcx
  unsigned int *v11; // rax
  unsigned int *v12; // rdx
  unsigned int v13; // ecx
  LONG CompositionStringW; // eax
  unsigned __int64 v15; // r14
  unsigned __int64 v16; // rax
  _DWORD *v17; // rax
  _DWORD *v18; // rbx
  unsigned __int64 v19; // r8
  void **v20; // [rsp+20h] [rbp-48h] BYREF
  unsigned int *v21; // [rsp+28h] [rbp-40h]
  HIMCC v22; // [rsp+30h] [rbp-38h]
  unsigned int v23; // [rsp+38h] [rbp-30h]
  void **v24; // [rsp+40h] [rbp-28h] BYREF
  LPINPUTCONTEXT v25; // [rsp+48h] [rbp-20h]
  HIMC v26; // [rsp+50h] [rbp-18h]
  __int64 v27; // [rsp+58h] [rbp-10h]

  v3 = (HIMC)*((_QWORD *)this + 4);
  v26 = v3;
  v25 = 0;
  v27 = 0;
  v24 = &IMCLock::`vftable';
  if ( !v3 )
    goto LABEL_4;
  v7 = ImmLockIMC(v3);
  v25 = v7;
  v8 = v7;
  if ( !v7 )
  {
    LODWORD(v27) = -2147467259;
LABEL_4:
    IMCLock::~IMCLock((IMCLock *)&v24);
    return 2147500037LL;
  }
  hCompStr = v7->hCompStr;
  v21 = 0;
  v22 = hCompStr;
  v23 = 0;
  if ( hCompStr )
  {
    v11 = (unsigned int *)ImmLockIMCC(hCompStr);
    v12 = v11;
    v21 = v11;
    v23 = v11 == 0 ? 0x80004005 : 0;
  }
  else
  {
    v12 = 0;
    v11 = 0;
  }
  v20 = &IMCCLock<tagCANDIDATEINFO>::`vftable';
  if ( !v12 )
  {
    InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v20);
    if ( v8 )
      ImmUnlockIMC(v3);
    return 2147500037LL;
  }
  v13 = v11[10];
  if ( v13 > *v11 || v11[9] + v13 > *v11 )
  {
    InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v20);
    goto LABEL_4;
  }
  CompositionStringW = ImmGetCompositionStringW(*((HIMC *)this + 4), 0x20u, 0, 0);
  v15 = CompositionStringW;
  if ( CompositionStringW )
  {
    v16 = 4 * ((unsigned __int64)CompositionStringW >> 2);
    if ( !is_mul_ok(v15 >> 2, 4u) )
      LODWORD(v16) = -1;
    v17 = LocalAlloc(0x40u, (unsigned int)v16);
    v18 = v17;
    if ( v17 )
    {
      v19 = (unsigned __int64)ImmGetCompositionStringW(*((HIMC *)this + 4), 0x20u, v17, v15) >> 2;
      if ( (int)v19 > 1 )
      {
        if ( v18[(int)v19 - 1] != a3 )
        {
          *v18 = 0;
          LODWORD(v19) = 2;
          v18[1] = a3;
        }
        CompData<unsigned long>::WriteCompData(a2, v18, v19);
      }
      cicMemFree(v18);
    }
  }
  InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v20);
  if ( v8 )
    ImmUnlockIMC(v3);
  return 0;
}

```

## disassembly

```asm
0x18003c9cc  push    rbp
0x18003c9ce  push    rbx
0x18003c9cf  push    rsi
0x18003c9d0  push    rdi
0x18003c9d1  push    r12
0x18003c9d3  push    r13
0x18003c9d5  push    r14
0x18003c9d7  push    r15
0x18003c9d9  mov     rbp, rsp
0x18003c9dc  sub     rsp, 68h
0x18003c9e0  mov     rsi, [rcx+20h]
0x18003c9e4  lea     rax, ??_7IMCLock@@6B@; const IMCLock::`vftable'
0x18003c9eb  xor     r14d, r14d
0x18003c9ee  mov     [rbp+var_18], rsi
0x18003c9f2  mov     [rbp+var_20], r14
0x18003c9f6  mov     r12d, r8d
0x18003c9f9  mov     [rbp+var_10], r14
0x18003c9fd  mov     r13, rdx
0x18003ca00  mov     [rbp+var_28], rax
0x18003ca04  mov     r15, rcx
0x18003ca07  mov     ebx, 80004005h
0x18003ca0c  test    rsi, rsi
0x18003ca0f  jz      short loc_18003CA29
0x18003ca11  mov     rcx, rsi; HIMC
0x18003ca14  call    cs:__imp_ImmLockIMC
0x18003ca1a  mov     [rbp+var_20], rax
0x18003ca1e  mov     rdi, rax
0x18003ca21  test    rax, rax
0x18003ca24  jnz     short loc_18003CA7D
0x18003ca26  mov     dword ptr [rbp+var_10], ebx
0x18003ca29  lea     rcx, [rbp+var_28]; this
0x18003ca2d  call    ??1IMCLock@@UEAA@XZ; IMCLock::~IMCLock(void)
0x18003ca32  mov     eax, ebx
0x18003ca34  jmp     short loc_18003CA6C
0x18003ca36  mov     dword ptr [rbx], 0
0x18003ca3c  mov     r8d, 2; int
0x18003ca42  mov     [rbx+4], r12d
0x18003ca46  call    ?WriteCompData@?$CompData@K@@QEAAKPEBKK@Z; CompData<ulong>::WriteCompData(ulong const *,ulong)
0x18003ca4b  mov     rcx, rbx
0x18003ca4e  call    cicMemFree
0x18003ca53  lea     rcx, [rbp+var_48]; this
0x18003ca57  call    ??1InternalIMCCLock@@UEAA@XZ; InternalIMCCLock::~InternalIMCCLock(void)
0x18003ca5c  test    rdi, rdi
0x18003ca5f  jz      short loc_18003CA6A
0x18003ca61  mov     rcx, rsi; HIMC
0x18003ca64  call    cs:__imp_ImmUnlockIMC
0x18003ca6a  xor     eax, eax
0x18003ca6c  add     rsp, 68h
0x18003ca70  pop     r15
0x18003ca72  pop     r14
0x18003ca74  pop     r13
0x18003ca76  pop     r12
0x18003ca78  pop     rdi
0x18003ca79  pop     rsi
0x18003ca7a  pop     rbx
0x18003ca7b  pop     rbp
0x18003ca7c  retn
0x18003ca7d  mov     rcx, [rax+120h]; HIMCC
0x18003ca84  mov     [rbp+var_40], r14
0x18003ca88  mov     [rbp+var_38], rcx
0x18003ca8c  mov     [rbp+var_30], r14d
0x18003ca90  test    rcx, rcx
0x18003ca93  jz      loc_18003CB92
0x18003ca99  call    cs:__imp_ImmLockIMCC
0x18003ca9f  mov     rdx, rax
0x18003caa2  mov     [rbp+var_40], rax
0x18003caa6  neg     rax
0x18003caa9  mov     rax, rdx
0x18003caac  sbb     ecx, ecx
0x18003caae  not     ecx
0x18003cab0  and     ecx, ebx
0x18003cab2  mov     [rbp+var_30], ecx
0x18003cab5  lea     rcx, ??_7?$IMCCLock@UtagCANDIDATEINFO@@@@6B@; const IMCCLock<tagCANDIDATEINFO>::`vftable'
0x18003cabc  mov     [rbp+var_48], rcx
0x18003cac0  test    rdx, rdx
0x18003cac3  jz      loc_18003CB72
0x18003cac9  mov     edx, [rax]
0x18003cacb  mov     ecx, [rax+28h]
0x18003cace  cmp     ecx, edx
0x18003cad0  ja      loc_18003CB9D
0x18003cad6  add     ecx, [rax+24h]
0x18003cad9  cmp     ecx, edx
0x18003cadb  ja      loc_18003CB9D
0x18003cae1  mov     rcx, [r15+20h]; HIMC
0x18003cae5  xor     r9d, r9d; dwBufLen
0x18003cae8  xor     r8d, r8d; lpBuf
0x18003caeb  lea     edx, [r9+20h]; DWORD
0x18003caef  call    cs:__imp_ImmGetCompositionStringW
0x18003caf5  movsxd  r14, eax
0x18003caf8  test    eax, eax
0x18003cafa  jz      loc_18003CA53
0x18003cb00  mov     rcx, r14
0x18003cb03  mov     eax, 4
0x18003cb08  shr     rcx, 2
0x18003cb0c  mul     rcx
0x18003cb0f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003cb16  cmovb   rax, rcx
0x18003cb1a  mov     ecx, 40h ; '@'; uFlags
0x18003cb1f  mov     edx, eax; uBytes
0x18003cb21  call    cs:__imp_LocalAlloc
0x18003cb27  mov     rbx, rax
0x18003cb2a  test    rax, rax
0x18003cb2d  jz      loc_18003CA53
0x18003cb33  mov     rcx, [r15+20h]; HIMC
0x18003cb37  mov     r9d, r14d; dwBufLen
0x18003cb3a  mov     r8, rax; lpBuf
0x18003cb3d  mov     edx, 20h ; ' '; DWORD
0x18003cb42  call    cs:__imp_ImmGetCompositionStringW
0x18003cb48  movsxd  r8, eax
0x18003cb4b  shr     r8, 2
0x18003cb4f  cmp     r8d, 1
0x18003cb53  jle     loc_18003CA4B
0x18003cb59  movsxd  rax, r8d
0x18003cb5c  mov     rdx, rbx; Src
0x18003cb5f  mov     rcx, r13; this
0x18003cb62  cmp     [rbx+rax*4-4], r12d
0x18003cb67  jz      loc_18003CA46
0x18003cb6d  jmp     loc_18003CA36
0x18003cb72  lea     rcx, [rbp+var_48]; this
0x18003cb76  call    ??1InternalIMCCLock@@UEAA@XZ; InternalIMCCLock::~InternalIMCCLock(void)
0x18003cb7b  test    rdi, rdi
0x18003cb7e  jz      loc_18003CA32
0x18003cb84  mov     rcx, rsi; HIMC
0x18003cb87  call    cs:__imp_ImmUnlockIMC
0x18003cb8d  jmp     loc_18003CA32
0x18003cb92  mov     rdx, r14
0x18003cb95  mov     rax, r14
0x18003cb98  jmp     loc_18003CAB5
0x18003cb9d  lea     rcx, [rbp+var_48]; this
0x18003cba1  call    ??1InternalIMCCLock@@UEAA@XZ; InternalIMCCLock::~InternalIMCCLock(void)
0x18003cba6  jmp     loc_18003CA29
```
