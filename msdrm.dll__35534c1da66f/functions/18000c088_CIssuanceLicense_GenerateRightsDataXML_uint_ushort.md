# CIssuanceLicense::GenerateRightsDataXML(uint *,ushort * *)

- ea: `0x18000c088`
- end: `0x18000c40c`
- name: `?GenerateRightsDataXML@CIssuanceLicense@@AEAAJPEAIPEAPEAG@Z`
- size: `900`
- prototype: `__int64 __fastcall(CIssuanceLicense *__hidden this, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18000cd4c`

## callees

- `0x180001284`
- `0x180001290`
- `0x180004654`
- `0x18000c088`
- `0x180011800`
- `0x180017358`
- `0x18001ef30`
- `0x18001ffd8`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c3dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c3dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c0d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c0d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIssuanceLicense::GenerateRightsDataXML(
        CIssuanceLicense *this,
        unsigned int *a2,
        unsigned __int16 **a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  unsigned __int16 *v6; // r12
  int XML; // edi
  void *v8; // r15
  unsigned int v9; // ecx
  int v10; // r14d
  unsigned int v11; // r15d
  __int64 v12; // rax
  CRight *v13; // rsi
  __int64 v14; // r14
  _WORD *v15; // rax
  unsigned int v16; // r15d
  unsigned int v17; // edi
  CDRMCBase *v18; // rcx
  __int64 v19; // rcx
  void *v20; // r11
  unsigned __int16 **v21; // r13
  unsigned __int16 *v22; // rax
  unsigned int v24; // [rsp+28h] [rbp-E0h]
  _WORD *v25; // [rsp+30h] [rbp-D8h]
  unsigned int v26[2]; // [rsp+38h] [rbp-D0h] BYREF
  void *Block; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int16 **v28; // [rsp+48h] [rbp-C0h]
  unsigned int *v29; // [rsp+50h] [rbp-B8h]
  __int64 v30; // [rsp+58h] [rbp-B0h]
  char *v31; // [rsp+60h] [rbp-A8h]
  _OWORD v32[9]; // [rsp+68h] [rbp-A0h] BYREF
  int v33; // [rsp+F8h] [rbp-10h]

  v30 = -2;
  v28 = a3;
  v29 = a2;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  v31 = (char *)this + 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v6 = 0;
  v32[0] = *(_OWORD *)L"<RIGHTSGROUP name=\"Main-Rights\"><RIGHTSLIST>%s</RIGHTSLIST></RIGHTSGROUP>";
  v32[1] = *(_OWORD *)L"ROUP name=\"Main-Rights\"><RIGHTSLIST>%s</RIGHTSLIST></RIGHTSGROUP>";
  v32[2] = *(_OWORD *)L"e=\"Main-Rights\"><RIGHTSLIST>%s</RIGHTSLIST></RIGHTSGROUP>";
  v32[3] = *(_OWORD *)L"Rights\"><RIGHTSLIST>%s</RIGHTSLIST></RIGHTSGROUP>";
  v32[4] = *(_OWORD *)L"<RIGHTSLIST>%s</RIGHTSLIST></RIGHTSGROUP>";
  v32[5] = *(_OWORD *)L"IST>%s</RIGHTSLIST></RIGHTSGROUP>";
  v32[6] = *(_OWORD *)L"RIGHTSLIST></RIGHTSGROUP>";
  v32[7] = *(_OWORD *)L"ST></RIGHTSGROUP>";
  v32[8] = *(_OWORD *)L"HTSGROUP>";
  v33 = *(_DWORD *)L">";
  Block = 0;
  if ( !a2 )
  {
    XML = -2147024809;
LABEL_3:
    v8 = 0;
    goto LABEL_39;
  }
  v24 = *((_DWORD *)this + 34);
  v9 = v24;
  *a2 = 0;
  if ( !v24 )
  {
    XML = -2147168430;
    goto LABEL_3;
  }
  XML = 0;
  v10 = 0;
  v11 = 0;
  do
  {
    if ( v11 < *((_DWORD *)this + 34) )
    {
      v12 = *((_QWORD *)this + 16);
      if ( *(_QWORD *)(v12 + 8LL * v11) )
      {
        CDRMCBase::AddRef(*(CDRMCBase **)(v12 + 8LL * v11));
        v13 = *(CRight **)(*((_QWORD *)this + 16) + 8LL * v11);
        if ( v13 )
        {
          v26[0] = 0;
          XML = CRight::GetXML(v13, v26, 0);
          if ( XML < 0 )
          {
            v8 = 0;
LABEL_38:
            CDRMCBase::Release(v13);
            goto LABEL_39;
          }
          v10 += v26[0];
          CDRMCBase::Release(v13);
        }
        v9 = v24;
      }
    }
    ++v11;
  }
  while ( v11 < v9 );
  v14 = (unsigned int)(v10 + 1);
  if ( !v28 )
  {
    LODWORD(v14) = v14 + 71;
    v8 = 0;
LABEL_35:
    *v29 = v14;
    v6 = 0;
    goto LABEL_39;
  }
  v15 = operator new[](saturated_mul((unsigned int)v14, 2u));
  v25 = v15;
  if ( !v15 )
  {
    XML = -2147024882;
    v8 = 0;
    goto LABEL_39;
  }
  memset_0(v15, 0, 2 * v14);
  v16 = 0;
  v17 = v24;
  do
  {
    if ( v16 < *((_DWORD *)this + 34) )
    {
      v18 = *(CDRMCBase **)(*((_QWORD *)this + 16) + 8LL * v16);
      if ( v18 )
      {
        CDRMCBase::AddRef(v18);
        v13 = *(CRight **)(*((_QWORD *)this + 16) + 8LL * v16);
        if ( v13 )
        {
          XML = CRight::GetXML(v13, v26, (unsigned __int16 **)&Block);
          if ( XML < 0 )
            goto LABEL_29;
          v19 = -1;
          do
            ++v19;
          while ( v25[v19] );
          XML = StringCchCopyW(&v25[(unsigned int)v19], (unsigned int)(v14 - v19), (unsigned __int16 *)Block);
          if ( XML < 0 )
          {
LABEL_29:
            v8 = v25;
            goto LABEL_38;
          }
          operator delete(v20);
          Block = 0;
          CDRMCBase::Release(v13);
          v17 = v24;
        }
      }
    }
    ++v16;
  }
  while ( v16 < v17 );
  v14 = (unsigned int)(v14 + 71);
  v21 = v28;
  v22 = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)v14, 2u));
  v6 = v22;
  if ( !v22 )
  {
    XML = -2147024882;
    v8 = v25;
    goto LABEL_39;
  }
  memset_0(v22, 0, 2 * v14);
  v8 = v25;
  XML = StringCchPrintfW(v6, (unsigned int)v14, (const unsigned __int16 *)v32, v25);
  if ( XML >= 0 )
  {
    *v21 = v6;
    goto LABEL_35;
  }
LABEL_39:
  operator delete(Block);
  operator delete(v8);
  operator delete(v6);
  LeaveCriticalSection(v5);
  return (unsigned int)XML;
}

```

## disassembly

```asm
0x18000c088  mov     rax, rsp
0x18000c08b  push    rbp
0x18000c08c  push    rsi
0x18000c08d  push    rdi
0x18000c08e  push    r12
0x18000c090  push    r13
0x18000c092  push    r14
0x18000c094  push    r15
0x18000c096  lea     rbp, [rax-48h]
0x18000c09a  sub     rsp, 110h
0x18000c0a1  mov     [rsp+140h+var_F0], 0FFFFFFFFFFFFFFFEh
0x18000c0aa  mov     [rax+20h], rbx
0x18000c0ae  mov     rax, cs:__security_cookie
0x18000c0b5  xor     rax, rsp
0x18000c0b8  mov     [rbp+40h+var_40], rax
0x18000c0bc  mov     [rsp+140h+var_100], r8
0x18000c0c1  mov     rdi, rdx
0x18000c0c4  mov     [rsp+140h+var_F8], rdx
0x18000c0c9  mov     r13, rcx
0x18000c0cc  lea     rbx, [rcx+58h]
0x18000c0d0  mov     qword ptr [rsp+140h+var_E8], rbx
0x18000c0d5  mov     rcx, rbx; lpCriticalSection
0x18000c0d8  call    cs:__imp_EnterCriticalSection
0x18000c0de  nop
0x18000c0df  xor     edx, edx
0x18000c0e1  mov     r12d, edx
0x18000c0e4  movaps  xmm0, xmmword ptr cs:aRightsgroupNam; "<RIGHTSGROUP name=\"Main-Rights\"><RIGH"...
0x18000c0eb  movups  xmmword ptr [rsp+140h+var_E8+8], xmm0
0x18000c0f0  movaps  xmm1, xmmword ptr cs:aRightsgroupNam+10h; "ROUP name=\"Main-Rights\"><RIGHTSLIST>%"...
0x18000c0f7  movups  [rsp+140h+var_D8+8], xmm1
0x18000c0fc  movaps  xmm0, xmmword ptr cs:aRightsgroupNam+20h; "e=\"Main-Rights\"><RIGHTSLIST>%s</RIGHT"...
0x18000c103  movups  [rbp+40h+var_C0], xmm0
0x18000c107  movaps  xmm1, xmmword ptr cs:aRightsgroupNam+30h; "Rights\"><RIGHTSLIST>%s</RIGHTSLIST></R"...
0x18000c10e  movups  [rbp+40h+var_B0], xmm1
0x18000c112  movaps  xmm0, xmmword ptr cs:aRightsgroupNam+40h; "<RIGHTSLIST>%s</RIGHTSLIST></RIGHTSGROU"...
0x18000c119  movups  [rbp+40h+var_A0], xmm0
0x18000c11d  movaps  xmm1, xmmword ptr cs:aRightsgroupNam+50h; "IST>%s</RIGHTSLIST></RIGHTSGROUP>"
0x18000c124  movups  [rbp+40h+var_90], xmm1
0x18000c128  movaps  xmm0, xmmword ptr cs:aRightsgroupNam+60h; "RIGHTSLIST></RIGHTSGROUP>"
0x18000c12f  movups  [rbp+40h+var_80], xmm0
0x18000c133  movaps  xmm1, xmmword ptr cs:aRightsgroupNam+70h; "ST></RIGHTSGROUP>"
0x18000c13a  movups  [rbp+40h+var_70], xmm1
0x18000c13e  movaps  xmm0, xmmword ptr cs:aRightsgroupNam+80h; "HTSGROUP>"
0x18000c145  movups  [rbp+40h+var_60], xmm0
0x18000c149  mov     eax, dword ptr cs:aRightsgroupNam+90h; ">"
0x18000c14f  mov     [rbp+40h+var_50], eax
0x18000c152  mov     [rsp+140h+var_118], rdx
0x18000c157  mov     [rsp+140h+Block], rdx
0x18000c15c  test    rdi, rdi
0x18000c15f  jnz     short loc_18000C16E
0x18000c161  mov     edi, 80070057h
0x18000c166  mov     r15, rdx
0x18000c169  jmp     loc_18000C3BF
0x18000c16e  mov     ecx, [r13+88h]
0x18000c175  mov     dword ptr [rsp+140h+var_120], ecx
0x18000c179  mov     [rdi], edx
0x18000c17b  test    ecx, ecx
0x18000c17d  jnz     short loc_18000C186
0x18000c17f  mov     edi, 8004CF52h
0x18000c184  jmp     short loc_18000C166
0x18000c186  mov     rsi, rdx
0x18000c189  mov     edi, edx
0x18000c18b  mov     r14d, edx
0x18000c18e  mov     r15d, edx
0x18000c191  test    ecx, ecx
0x18000c193  jz      short loc_18000C209
0x18000c195  cmp     r15d, [r13+88h]
0x18000c19c  jb      short loc_18000C1A3
0x18000c19e  mov     rsi, rdx
0x18000c1a1  jmp     short loc_18000C201
0x18000c1a3  mov     esi, r15d
0x18000c1a6  mov     rax, [r13+80h]
0x18000c1ad  cmp     [rax+rsi*8], rdx
0x18000c1b1  jz      short loc_18000C19E
0x18000c1b3  mov     rcx, [rax+rsi*8]; this
0x18000c1b7  call    ?AddRef@CDRMCBase@@QEAAKXZ; CDRMCBase::AddRef(void)
0x18000c1bc  mov     rax, [r13+80h]
0x18000c1c3  mov     rsi, [rax+rsi*8]
0x18000c1c7  xor     edx, edx
0x18000c1c9  test    rsi, rsi
0x18000c1cc  jz      short loc_18000C1FD
0x18000c1ce  mov     [rsp+140h+var_110], edx
0x18000c1d2  xor     r8d, r8d; unsigned __int16 **
0x18000c1d5  lea     rdx, [rsp+140h+var_110]; unsigned int *
0x18000c1da  mov     rcx, rsi; this
0x18000c1dd  call    ?GetXML@CRight@@QEAAJPEAIPEAPEAG@Z; CRight::GetXML(uint *,ushort * *)
0x18000c1e2  mov     edi, eax
0x18000c1e4  test    eax, eax
0x18000c1e6  js      loc_18000C3B4
0x18000c1ec  add     r14d, [rsp+140h+var_110]
0x18000c1f1  mov     rcx, rsi; this
0x18000c1f4  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18000c1f9  xor     edx, edx
0x18000c1fb  mov     esi, edx
0x18000c1fd  mov     ecx, dword ptr [rsp+140h+var_120]
0x18000c201  inc     r15d
0x18000c204  cmp     r15d, ecx
0x18000c207  jb      short loc_18000C195
0x18000c209  inc     r14d
0x18000c20c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000c210  cmp     [rsp+140h+var_100], rdx
0x18000c215  jz      loc_18000C329
0x18000c21b  mov     r15d, r14d
0x18000c21e  lea     eax, [rcx+3]
0x18000c221  mul     r15
0x18000c224  cmovb   rax, rcx
0x18000c228  mov     rcx, rax; unsigned __int64
0x18000c22b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c230  mov     [rsp+140h+var_118], rax
0x18000c235  xor     edx, edx; Val
0x18000c237  test    rax, rax
0x18000c23a  jnz     short loc_18000C249
0x18000c23c  mov     edi, 8007000Eh
0x18000c241  mov     r15, rax
0x18000c244  jmp     loc_18000C3AD
0x18000c249  lea     r8, [r14+r14]; Size
0x18000c24d  mov     rcx, rax; void *
0x18000c250  call    memset_0
0x18000c255  xor     edx, edx
0x18000c257  mov     r15d, edx
0x18000c25a  cmp     dword ptr [rsp+140h+var_120], edx
0x18000c25e  jbe     loc_18000C329
0x18000c264  mov     edi, dword ptr [rsp+140h+var_120]
0x18000c268  cmp     r15d, [r13+88h]
0x18000c26f  jnb     loc_18000C305
0x18000c275  mov     esi, r15d
0x18000c278  mov     rax, [r13+80h]
0x18000c27f  mov     rcx, [rax+rsi*8]; this
0x18000c283  test    rcx, rcx
0x18000c286  jz      short loc_18000C305
0x18000c288  call    ?AddRef@CDRMCBase@@QEAAKXZ; CDRMCBase::AddRef(void)
0x18000c28d  mov     rax, [r13+80h]
0x18000c294  mov     rsi, [rax+rsi*8]
0x18000c298  xor     edx, edx
0x18000c29a  test    rsi, rsi
0x18000c29d  jz      short loc_18000C308
0x18000c29f  lea     r8, [rsp+140h+Block]; unsigned __int16 **
0x18000c2a4  lea     rdx, [rsp+140h+var_110]; unsigned int *
0x18000c2a9  mov     rcx, rsi; this
0x18000c2ac  call    ?GetXML@CRight@@QEAAJPEAIPEAPEAG@Z; CRight::GetXML(uint *,ushort * *)
0x18000c2b1  mov     edi, eax
0x18000c2b3  xor     eax, eax
0x18000c2b5  test    edi, edi
0x18000c2b7  js      short loc_18000C31F
0x18000c2b9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000c2bd  mov     r8, [rsp+140h+var_118]
0x18000c2c2  inc     rcx
0x18000c2c5  cmp     [r8+rcx*2], ax
0x18000c2ca  jnz     short loc_18000C2C2
0x18000c2cc  mov     edx, r14d
0x18000c2cf  sub     edx, ecx; unsigned __int64
0x18000c2d1  mov     eax, ecx
0x18000c2d3  lea     rcx, [r8+rax*2]; unsigned __int16 *
0x18000c2d7  mov     r11, [rsp+140h+Block]
0x18000c2dc  mov     r8, r11; unsigned __int16 *
0x18000c2df  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c2e4  mov     edi, eax
0x18000c2e6  test    eax, eax
0x18000c2e8  js      short loc_18000C31F
0x18000c2ea  mov     rcx, r11; Block
0x18000c2ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c2f2  mov     [rsp+140h+Block], r12
0x18000c2f7  mov     rcx, rsi; this
0x18000c2fa  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18000c2ff  xor     edx, edx
0x18000c301  mov     edi, dword ptr [rsp+140h+var_120]
0x18000c305  mov     rsi, rdx
0x18000c308  inc     r15d
0x18000c30b  cmp     r15d, edi
0x18000c30e  jb      loc_18000C268
0x18000c314  add     r14d, 47h ; 'G'
0x18000c318  mov     r13, [rsp+140h+var_100]
0x18000c31d  jmp     short loc_18000C337
0x18000c31f  mov     r15, [rsp+140h+var_118]
0x18000c324  jmp     loc_18000C3B7
0x18000c329  add     r14d, 47h ; 'G'
0x18000c32d  mov     r13, [rsp+140h+var_100]
0x18000c332  test    r13, r13
0x18000c335  jz      short loc_18000C39D
0x18000c337  mov     edi, r14d
0x18000c33a  mov     eax, 2
0x18000c33f  mul     rdi
0x18000c342  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c349  cmovb   rax, rcx
0x18000c34d  mov     rcx, rax; unsigned __int64
0x18000c350  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c355  mov     r12, rax
0x18000c358  xor     edx, edx; Val
0x18000c35a  test    rax, rax
0x18000c35d  jnz     short loc_18000C36B
0x18000c35f  mov     edi, 8007000Eh
0x18000c364  mov     r15, [rsp+140h+var_118]
0x18000c369  jmp     short loc_18000C3AD
0x18000c36b  lea     r8, [r14+r14]; Size
0x18000c36f  mov     rcx, r12; void *
0x18000c372  call    memset_0
0x18000c377  mov     r15, [rsp+140h+var_118]
0x18000c37c  mov     r9, r15
0x18000c37f  lea     r8, [rsp+140h+var_E8+8]; unsigned __int16 *
0x18000c384  mov     rdx, rdi; unsigned __int64
0x18000c387  mov     rcx, r12; unsigned __int16 *
0x18000c38a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c38f  mov     edi, eax
0x18000c391  xor     edx, edx
0x18000c393  test    eax, eax
0x18000c395  js      short loc_18000C3AD
0x18000c397  mov     [r13+0], r12
0x18000c39b  jmp     short loc_18000C3A2
0x18000c39d  mov     r15, [rsp+140h+var_118]
0x18000c3a2  mov     rax, [rsp+140h+var_F8]
0x18000c3a7  mov     [rax], r14d
0x18000c3aa  mov     r12, rdx
0x18000c3ad  test    rsi, rsi
0x18000c3b0  jz      short loc_18000C3BF
0x18000c3b2  jmp     short loc_18000C3B7
0x18000c3b4  mov     r15, r12
0x18000c3b7  mov     rcx, rsi; this
0x18000c3ba  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18000c3bf  mov     rcx, [rsp+140h+Block]; Block
0x18000c3c4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c3c9  mov     rcx, r15; Block
0x18000c3cc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c3d1  mov     rcx, r12; Block
0x18000c3d4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c3d9  nop
0x18000c3da  mov     rcx, rbx; lpCriticalSection
0x18000c3dd  call    cs:__imp_LeaveCriticalSection
0x18000c3e3  mov     eax, edi
0x18000c3e5  mov     rcx, [rbp+40h+var_40]
0x18000c3e9  xor     rcx, rsp; StackCookie
0x18000c3ec  call    __security_check_cookie
0x18000c3f1  mov     rbx, [rsp+140h+arg_18]
0x18000c3f9  add     rsp, 110h
0x18000c400  pop     r15
0x18000c402  pop     r14
0x18000c404  pop     r13
0x18000c406  pop     r12
0x18000c408  pop     rdi
0x18000c409  pop     rsi
0x18000c40a  pop     rbp
0x18000c40b  retn
```
