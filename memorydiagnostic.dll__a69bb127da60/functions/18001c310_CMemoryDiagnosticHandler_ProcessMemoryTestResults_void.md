# CMemoryDiagnosticHandler::ProcessMemoryTestResults(void)

- ea: `0x18001c310`
- end: `0x18001cadc`
- name: `?ProcessMemoryTestResults@CMemoryDiagnosticHandler@@AEAAJXZ`
- size: `1996`
- prototype: `__int64 __fastcall(unsigned __int64 **this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d7a0`

## callees

- `0x180003294`
- `0x1800032cc`
- `0x180003928`
- `0x18001a5a0`
- `0x18001c100`
- `0x18001c310`
- `0x18001cae4`
- `0x18001e21c`
- `0x18001e24c`
- `0x18001e290`
- `0x18001e2d4`
- `0x18001e37c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_bsearch` at `0x18001c69f`
- `api-ms-win-crt-private-l1-1-0!_o_bsearch` at `0x18001c69f`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001c4fc`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001c4fc`
- `bcd!BcdCloseObject` at `0x18001c5ac`
- `bcd!BcdCloseObject` at `0x18001c997`
- `bcd!BcdCloseObject` at `0x18001c5ac`
- `bcd!BcdCloseObject` at `0x18001c997`
- `bcd!BcdOpenSystemStore` at `0x18001c36b`
- `bcd!BcdOpenSystemStore` at `0x18001c860`
- `bcd!BcdOpenSystemStore` at `0x18001c36b`
- `bcd!BcdOpenSystemStore` at `0x18001c860`
- `bcd!BcdCloseStore` at `0x18001c5c5`
- `bcd!BcdCloseStore` at `0x18001c9b0`
- `bcd!BcdCloseStore` at `0x18001c5c5`
- `bcd!BcdCloseStore` at `0x18001c9b0`
- `bcd!BcdGetElementData` at `0x18001c409`
- `bcd!BcdGetElementData` at `0x18001c45e`
- `bcd!BcdGetElementData` at `0x18001c409`
- `bcd!BcdGetElementData` at `0x18001c45e`
- `bcd!BcdOpenObject` at `0x18001c3c9`
- `bcd!BcdOpenObject` at `0x18001c8bd`
- `bcd!BcdOpenObject` at `0x18001c3c9`
- `bcd!BcdOpenObject` at `0x18001c8bd`
- `bcd!BcdSetElementData` at `0x18001c912`
- `bcd!BcdSetElementData` at `0x18001c912`

## pseudocode

```c
__int64 __fastcall CMemoryDiagnosticHandler::ProcessMemoryTestResults(unsigned __int64 **this)
{
  unsigned __int64 *v1; // r14
  unsigned __int64 v3; // r12
  int BadPageList; // ebx
  __int64 *v5; // rsi
  int v6; // eax
  __int64 v7; // r8
  int v8; // ebx
  CMemoryDiagnosticHandler *v9; // rcx
  __int64 v10; // rdx
  int ElementData; // eax
  __int64 v12; // r8
  int v13; // edi
  __int64 v14; // rdx
  size_t v15; // rdi
  __int64 v16; // r14
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  unsigned __int64 v20; // rcx
  size_t i; // r14
  CMemoryDiagnosticHandler **v22; // r8
  unsigned __int64 v23; // rdx
  _QWORD *v24; // r13
  unsigned __int64 v25; // rsi
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // r8
  int v28; // edi
  unsigned __int64 *v29; // rax
  int v30; // r14d
  unsigned __int64 v31; // rbx
  CMemoryDiagnosticHandler *v32; // rcx
  __int64 v33; // rdx
  unsigned __int64 j; // rcx
  int v35; // r14d
  int v36; // eax
  __int64 v37; // rdx
  unsigned __int64 v38; // rdx
  unsigned __int64 v39; // rax
  unsigned __int64 v40; // rdx
  CMemoryDiagnosticHandler *v41; // rcx
  CMemoryDiagnosticHandler *v42; // rcx
  __int64 v44; // [rsp+30h] [rbp-48h] BYREF
  void *Src[2]; // [rsp+38h] [rbp-40h]
  void *Block[2]; // [rsp+50h] [rbp-28h]
  unsigned __int64 v47; // [rsp+C0h] [rbp+48h] BYREF
  void *v48; // [rsp+C8h] [rbp+50h] BYREF
  unsigned __int64 v49; // [rsp+D0h] [rbp+58h]
  __int64 v50; // [rsp+D8h] [rbp+60h] BYREF

  v1 = (unsigned __int64 *)(this + 14);
  v49 = 0;
  *(_OWORD *)Src = 0;
  *(_OWORD *)Block = 0;
  v3 = 0;
  BadPageList = CMemoryDiagnosticHandler::QueryBadPageList(
                  (CMemoryDiagnosticHandler *)this,
                  this + 15,
                  (unsigned __int64 *)this + 14);
  if ( BadPageList < 0 )
    goto LABEL_139;
  v44 = 0;
  v50 = 0;
  v5 = 0;
  LODWORD(v47) = 0;
  v6 = BcdOpenSystemStore(&v44);
  v8 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_22;
    }
    v10 = 62;
    goto LABEL_6;
  }
  v6 = BcdOpenObject(v44, &GUID_BAD_MEMORY_GROUP, &v50);
  v8 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_22;
    }
    v10 = 63;
LABEL_6:
    WPP_SF_d(*((_QWORD *)v9 + 2), v10, v7, (unsigned int)v6);
    v9 = WPP_GLOBAL_Control;
    goto LABEL_22;
  }
  BadPageList = 0;
  ElementData = BcdGetElementData(v50, 385875978, 0, &v47);
  v13 = ElementData;
  if ( ElementData == -1073741275 )
    goto LABEL_25;
  if ( ElementData == -1073741789 )
  {
    v5 = (__int64 *)operator new[]((unsigned int)v47);
    v13 = BcdGetElementData(v50, 385875978, v5, &v47);
    if ( v13 >= 0 )
    {
      v15 = (unsigned __int64)(unsigned int)v47 >> 3;
      Src[0] = v5;
      v48 = (void *)v15;
      v16 = 1;
      v49 = 1;
      qsort(v5, v15, 8u, CMemoryDiagnosticHandler::static_PageNumberCompare);
      v19 = *v5;
      v20 = 1;
      if ( v15 > 1 )
      {
        do
        {
          if ( v5[v20] > (unsigned __int64)(v19 + 1) )
            ++v16;
          v19 = v5[v20++];
        }
        while ( v20 < v15 );
        v49 = v16;
      }
      v9 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control )
        {
          WPP_SF_PP(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v18, v15, v16);
          v9 = WPP_GLOBAL_Control;
        }
        for ( i = 0; i < v15; ++i )
        {
          if ( v9 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
          {
            WPP_SF_P(*((_QWORD *)v9 + 2), 68, v18, v5[i]);
            v9 = WPP_GLOBAL_Control;
          }
        }
      }
      v1 = (unsigned __int64 *)(this + 14);
      goto LABEL_41;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_21;
    }
    v14 = 66;
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_21;
    }
    v14 = 64;
  }
  WPP_SF_d(*((_QWORD *)v9 + 2), v14, v12, (unsigned int)v13);
  v9 = WPP_GLOBAL_Control;
LABEL_21:
  v8 = v13;
LABEL_22:
  BadPageList = v8 | 0x10000000;
  if ( BadPageList >= 0 || !v5 )
  {
    v15 = (size_t)Src[1];
    v48 = Src[1];
    goto LABEL_41;
  }
  operator delete(v5);
LABEL_25:
  v15 = (size_t)Src[1];
  v9 = WPP_GLOBAL_Control;
  v48 = Src[1];
LABEL_41:
  if ( v50 )
  {
    BcdCloseObject(v50);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v44 )
  {
    BcdCloseStore(v44);
    v9 = WPP_GLOBAL_Control;
  }
  if ( BadPageList < 0 )
  {
    v22 = &WPP_GLOBAL_Control;
    if ( v9 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
    {
LABEL_121:
      WPP_SF_d(*((_QWORD *)v9 + 2), 10, v22, (unsigned int)BadPageList);
      goto LABEL_139;
    }
  }
  if ( BadPageList < 0 )
    goto LABEL_139;
  v23 = *v1 + v15;
  if ( v23 < *v1 )
  {
    if ( v9 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v9 + 2), 51);
    BadPageList = -2147024362;
    goto LABEL_139;
  }
  if ( !v23 )
  {
    if ( v9 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)v9 + 2), 52);
    BadPageList = 0;
    goto LABEL_139;
  }
  LODWORD(v47) = 0;
  Block[0] = operator new[](saturated_mul(v23, 8u));
  v24 = Block[0];
  v25 = v15;
  memcpy_0(Block[0], Src[0], 8 * v15);
  BadPageList = 0;
  if ( !this[14] )
  {
    v32 = WPP_GLOBAL_Control;
    goto LABEL_89;
  }
  v28 = 0;
  do
  {
    if ( _o_bsearch(&this[15][v3], this[11], this[10], 8, CMemoryDiagnosticHandler::static_PageNumberCompare) )
      goto LABEL_85;
    ++*((_DWORD *)this + 36);
    if ( v25 < *((unsigned int *)this + 15) )
    {
      v29 = this[15];
      v30 = 1;
      v31 = v29[v3];
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, v27, v29[v3]);
        v32 = WPP_GLOBAL_Control;
      }
      v26 = 0;
      if ( v25 )
      {
        while ( 1 )
        {
          v27 = v24[v26];
          if ( v27 == v31 )
            break;
          if ( v27 > v31 )
          {
            if ( v27 == v31 + 1 )
              --v30;
            goto LABEL_68;
          }
          if ( v27 == v31 - 1 )
            --v30;
          if ( ++v26 >= v25 )
            goto LABEL_68;
        }
        if ( v32 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 4) != 0 )
        {
          v33 = 49;
          goto LABEL_77;
        }
        goto LABEL_78;
      }
LABEL_68:
      v27 = v30 + v49;
      if ( v27 > 0x80 )
      {
        if ( v32 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 4) != 0 )
        {
          v33 = 50;
LABEL_77:
          WPP_SF_P(*((_QWORD *)v32 + 2), v33, v27, v31);
          v32 = WPP_GLOBAL_Control;
        }
LABEL_78:
        BadPageList = 0;
        goto LABEL_86;
      }
      v49 += v30;
      for ( j = v25; j > v26; --j )
        v24[j] = v24[j - 1];
      ++v25;
      v24[v26] = v31;
      ++v28;
      BadPageList = 0;
      goto LABEL_85;
    }
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, v27, this[15][v3]);
LABEL_85:
      v32 = WPP_GLOBAL_Control;
    }
LABEL_86:
    ++v3;
  }
  while ( v3 < (unsigned __int64)this[14] );
  LODWORD(v47) = v28;
  v15 = (size_t)v48;
LABEL_89:
  if ( v32 == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control || (*((_BYTE *)v32 + 28) & 4) == 0 )
  {
    v35 = v47;
  }
  else
  {
    v35 = v47;
    WPP_SF_II(*((_QWORD *)v32 + 2), v26, v27, *((unsigned int *)this + 36), (unsigned int)v47);
    v32 = WPP_GLOBAL_Control;
  }
  if ( !v35 || v25 <= v15 )
    goto LABEL_124;
  v50 = 0;
  v48 = 0;
  v36 = BcdOpenSystemStore(&v50);
  if ( v36 < 0 )
  {
    BadPageList = v36 | 0x10000000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v37 = 81;
      goto LABEL_99;
    }
    goto LABEL_114;
  }
  v36 = BcdOpenObject(v50, &GUID_BAD_MEMORY_GROUP, &v48);
  if ( v36 < 0 )
  {
    BadPageList = v36 | 0x10000000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_114;
    }
    v37 = 82;
LABEL_99:
    WPP_SF_d(*((_QWORD *)v9 + 2), v37, v22, (unsigned int)v36);
    v9 = WPP_GLOBAL_Control;
    goto LABEL_114;
  }
  if ( 8 * (unsigned __int64)(unsigned int)v25 > 0xFFFFFFFF )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83);
      v9 = WPP_GLOBAL_Control;
    }
    BadPageList = -2147024362;
    goto LABEL_114;
  }
  v36 = BcdSetElementData(v48, 385875978, v24);
  BadPageList = 0;
  if ( v36 >= 0 )
  {
    v9 = WPP_GLOBAL_Control;
    goto LABEL_114;
  }
  BadPageList = v36 | 0x10000000;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v37 = 84;
    goto LABEL_99;
  }
LABEL_114:
  if ( v48 )
  {
    BcdCloseObject(v48);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v50 )
  {
    BcdCloseStore(v50);
    v9 = WPP_GLOBAL_Control;
  }
  if ( BadPageList >= 0 )
  {
    v38 = (unsigned int)v47;
    *((_DWORD *)this + 37) = v47;
    CMemoryDiagnosticHandler::LogPageRetiredEvent(v9, v38, 0);
    v32 = WPP_GLOBAL_Control;
LABEL_124:
    v39 = *((unsigned int *)this + 15);
    if ( v25 >= v39 )
    {
      *((_DWORD *)this + 27) |= 0x10u;
      v32 = WPP_GLOBAL_Control;
    }
    v40 = v49;
    if ( v49 >= 0x80 )
    {
      *((_DWORD *)this + 27) |= 0x20u;
      v32 = WPP_GLOBAL_Control;
    }
    if ( v25 >= v39 || v40 >= 0x80 )
    {
      if ( v32 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)v32 + 2), 56);
      CMemoryDiagnosticHandler::LogPageRetiredEvent(v32, v25, 1);
      BadPageList = CMemoryDiagnosticHandler::ConfigureMemoryDiagnosticTask(v41, L"RunFullMemoryDiagnostic");
      if ( BadPageList >= 0 )
        BadPageList = CMemoryDiagnosticHandler::ConfigureMemoryDiagnosticTask(v42, L"ProcessMemoryDiagnosticEvents");
    }
    goto LABEL_139;
  }
  if ( v9 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
    goto LABEL_121;
LABEL_139:
  if ( Src[0] )
    operator delete(Src[0]);
  if ( Block[0] )
    operator delete(Block[0]);
  return (unsigned int)BadPageList;
}

```

## disassembly

```asm
0x18001c310  push    rbp
0x18001c312  push    rbx
0x18001c313  push    rsi
0x18001c314  push    rdi
0x18001c315  push    r12
0x18001c317  push    r13
0x18001c319  push    r14
0x18001c31b  push    r15
0x18001c31d  mov     rbp, rsp
0x18001c320  sub     rsp, 78h
0x18001c324  lea     r14, [rcx+70h]
0x18001c328  xorps   xmm0, xmm0
0x18001c32b  xor     eax, eax
0x18001c32d  lea     rdx, [rcx+78h]; unsigned __int64 **
0x18001c331  xorps   xmm1, xmm1
0x18001c334  mov     [rbp+arg_10], rax
0x18001c338  mov     r8, r14; unsigned __int64 *
0x18001c33b  mov     r15, rcx
0x18001c33e  movups  xmmword ptr [rbp+Src], xmm0
0x18001c342  movups  xmmword ptr [rbp+Block], xmm1
0x18001c346  call    ?QueryBadPageList@CMemoryDiagnosticHandler@@AEAAJPEAPEA_KPEA_K@Z; CMemoryDiagnosticHandler::QueryBadPageList(unsigned __int64 * *,unsigned __int64 *)
0x18001c34b  xor     r12d, r12d
0x18001c34e  mov     ebx, eax
0x18001c350  test    eax, eax
0x18001c352  js      loc_18001CAAD
0x18001c358  lea     rcx, [rbp+var_48]
0x18001c35c  mov     [rbp+var_48], r12
0x18001c360  mov     [rbp+arg_18], r12
0x18001c364  mov     esi, r12d
0x18001c367  mov     dword ptr [rbp+arg_0], r12d
0x18001c36b  call    cs:__imp_BcdOpenSystemStore
0x18001c371  lea     rdi, WPP_GLOBAL_Control
0x18001c378  mov     ebx, eax
0x18001c37a  lea     r13d, [r12+1]
0x18001c37f  test    eax, eax
0x18001c381  jns     short loc_18001C3BA
0x18001c383  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c38a  cmp     rcx, rdi
0x18001c38d  jz      loc_18001C49D
0x18001c393  test    [rcx+1Ch], r13b
0x18001c397  jz      loc_18001C49D
0x18001c39d  lea     edx, [r12+3Eh]
0x18001c3a2  mov     rcx, [rcx+10h]
0x18001c3a6  mov     r9d, eax
0x18001c3a9  call    WPP_SF_d
0x18001c3ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c3b5  jmp     loc_18001C49D
0x18001c3ba  mov     rcx, [rbp+var_48]
0x18001c3be  lea     r8, [rbp+arg_18]
0x18001c3c2  lea     rdx, GUID_BAD_MEMORY_GROUP
0x18001c3c9  call    cs:__imp_BcdOpenObject
0x18001c3cf  mov     ebx, eax
0x18001c3d1  test    eax, eax
0x18001c3d3  jns     short loc_18001C3F6
0x18001c3d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c3dc  cmp     rcx, rdi
0x18001c3df  jz      loc_18001C49D
0x18001c3e5  test    [rcx+1Ch], r13b
0x18001c3e9  jz      loc_18001C49D
0x18001c3ef  mov     edx, 3Fh ; '?'
0x18001c3f4  jmp     short loc_18001C3A2
0x18001c3f6  mov     rcx, [rbp+arg_18]
0x18001c3fa  lea     r9, [rbp+arg_0]
0x18001c3fe  xor     r8d, r8d
0x18001c401  mov     edx, 1700000Ah
0x18001c406  mov     ebx, r12d
0x18001c409  call    cs:__imp_BcdGetElementData
0x18001c40f  mov     edi, eax
0x18001c411  cmp     eax, 0C0000225h
0x18001c416  jz      loc_18001C4B2
0x18001c41c  cmp     eax, 0C0000023h
0x18001c421  jz      short loc_18001C443
0x18001c423  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c42a  lea     rax, WPP_GLOBAL_Control
0x18001c431  cmp     rcx, rax
0x18001c434  jz      short loc_18001C49B
0x18001c436  test    [rcx+1Ch], r13b
0x18001c43a  jz      short loc_18001C49B
0x18001c43c  mov     edx, 40h ; '@'
0x18001c441  jmp     short loc_18001C488
0x18001c443  mov     ecx, dword ptr [rbp+arg_0]; unsigned __int64
0x18001c446  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001c44b  mov     rcx, [rbp+arg_18]
0x18001c44f  lea     r9, [rbp+arg_0]
0x18001c453  mov     r8, rax
0x18001c456  mov     edx, 1700000Ah
0x18001c45b  mov     rsi, rax
0x18001c45e  call    cs:__imp_BcdGetElementData
0x18001c464  mov     edi, eax
0x18001c466  test    eax, eax
0x18001c468  jns     short loc_18001C4D3
0x18001c46a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c471  lea     rax, WPP_GLOBAL_Control
0x18001c478  cmp     rcx, rax
0x18001c47b  jz      short loc_18001C49B
0x18001c47d  test    [rcx+1Ch], r13b
0x18001c481  jz      short loc_18001C49B
0x18001c483  mov     edx, 42h ; 'B'
0x18001c488  mov     rcx, [rcx+10h]
0x18001c48c  mov     r9d, edi
0x18001c48f  call    WPP_SF_d
0x18001c494  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c49b  mov     ebx, edi
0x18001c49d  or      ebx, 10000000h
0x18001c4a3  jge     short loc_18001C4C6
0x18001c4a5  test    rsi, rsi
0x18001c4a8  jz      short loc_18001C4C6
0x18001c4aa  mov     rcx, rsi; Block
0x18001c4ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c4b2  mov     rdi, [rbp+Src+8]
0x18001c4b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4bd  mov     [rbp+arg_8], rdi
0x18001c4c1  jmp     loc_18001C5A0
0x18001c4c6  mov     rdi, [rbp+Src+8]
0x18001c4ca  mov     [rbp+arg_8], rdi
0x18001c4ce  jmp     loc_18001C5A0
0x18001c4d3  mov     edi, dword ptr [rbp+arg_0]
0x18001c4d6  lea     r9, ?static_PageNumberCompare@CMemoryDiagnosticHandler@@CAHPEBX0@Z; CompareFunction
0x18001c4dd  shr     rdi, 3
0x18001c4e1  mov     r8d, 8; SizeOfElements
0x18001c4e7  mov     rdx, rdi; NumOfElements
0x18001c4ea  mov     [rbp+Src], rsi
0x18001c4ee  mov     rcx, rsi; Base
0x18001c4f1  mov     [rbp+arg_8], rdi
0x18001c4f5  mov     r14, r13
0x18001c4f8  mov     [rbp+arg_10], r13
0x18001c4fc  call    cs:__imp_qsort
0x18001c502  mov     rax, [rsi]
0x18001c505  mov     rcx, r13
0x18001c508  cmp     rdi, r13
0x18001c50b  jbe     short loc_18001C529
0x18001c50d  inc     rax
0x18001c510  cmp     [rsi+rcx*8], rax
0x18001c514  jbe     short loc_18001C519
0x18001c516  add     r14, r13
0x18001c519  mov     rax, [rsi+rcx*8]
0x18001c51d  add     rcx, r13
0x18001c520  cmp     rcx, rdi
0x18001c523  jb      short loc_18001C50D
0x18001c525  mov     [rbp+arg_10], r14
0x18001c529  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c530  test    byte ptr [rcx+1Ch], 4
0x18001c534  jz      short loc_18001C59C
0x18001c536  lea     rax, WPP_GLOBAL_Control
0x18001c53d  cmp     rcx, rax
0x18001c540  jz      short loc_18001C561
0x18001c542  mov     rcx, [rcx+10h]
0x18001c546  mov     r9, rdi
0x18001c549  mov     [rsp+78h+var_58], r14
0x18001c54e  call    WPP_SF_PP
0x18001c553  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c55a  lea     rax, WPP_GLOBAL_Control
0x18001c561  mov     r14, r12
0x18001c564  test    rdi, rdi
0x18001c567  jz      short loc_18001C59C
0x18001c569  cmp     rcx, rax
0x18001c56c  jz      short loc_18001C594
0x18001c56e  test    byte ptr [rcx+1Ch], 4
0x18001c572  jz      short loc_18001C594
0x18001c574  mov     r9, [rsi+r14*8]
0x18001c578  mov     edx, 44h ; 'D'
0x18001c57d  mov     rcx, [rcx+10h]
0x18001c581  call    WPP_SF_P
0x18001c586  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c58d  lea     rax, WPP_GLOBAL_Control
0x18001c594  add     r14, r13
0x18001c597  cmp     r14, rdi
0x18001c59a  jb      short loc_18001C569
0x18001c59c  lea     r14, [r15+70h]
0x18001c5a0  mov     rax, [rbp+arg_18]
0x18001c5a4  test    rax, rax
0x18001c5a7  jz      short loc_18001C5B9
0x18001c5a9  mov     rcx, rax
0x18001c5ac  call    cs:__imp_BcdCloseObject
0x18001c5b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5b9  mov     rax, [rbp+var_48]
0x18001c5bd  test    rax, rax
0x18001c5c0  jz      short loc_18001C5D2
0x18001c5c2  mov     rcx, rax
0x18001c5c5  call    cs:__imp_BcdCloseStore
0x18001c5cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5d2  test    ebx, ebx
0x18001c5d4  jns     short loc_18001C5ED
0x18001c5d6  lea     r8, WPP_GLOBAL_Control
0x18001c5dd  cmp     rcx, r8
0x18001c5e0  jz      short loc_18001C5F4
0x18001c5e2  test    [rcx+1Ch], r13b
0x18001c5e6  jz      short loc_18001C5F4
0x18001c5e8  jmp     loc_18001C9CC
0x18001c5ed  lea     r8, WPP_GLOBAL_Control
0x18001c5f4  test    ebx, ebx
0x18001c5f6  js      loc_18001CAAD
0x18001c5fc  mov     rax, [r14]
0x18001c5ff  lea     rdx, [rax+rdi]
0x18001c603  cmp     rdx, rax
0x18001c606  jb      loc_18001CA8F
0x18001c60c  test    rdx, rdx
0x18001c60f  jnz     short loc_18001C632
0x18001c611  cmp     rcx, r8
0x18001c614  jz      short loc_18001C62A
0x18001c616  test    byte ptr [rcx+1Ch], 2
0x18001c61a  jz      short loc_18001C62A
0x18001c61c  mov     rcx, [rcx+10h]
0x18001c620  mov     edx, 34h ; '4'
0x18001c625  call    WPP_SF_
0x18001c62a  mov     ebx, r12d
0x18001c62d  jmp     loc_18001CAAD
0x18001c632  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001c639  mov     dword ptr [rbp+arg_0], r12d
0x18001c63d  mov     eax, 8
0x18001c642  mul     rdx
0x18001c645  cmovb   rax, rcx
0x18001c649  mov     rcx, rax; unsigned __int64
0x18001c64c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001c651  mov     rdx, [rbp+Src]; Src
0x18001c655  lea     r8, ds:0[rdi*8]; Size
0x18001c65d  mov     rcx, rax; void *
0x18001c660  mov     [rbp+Block], rax
0x18001c664  mov     r13, rax
0x18001c667  mov     rsi, rdi
0x18001c66a  call    memcpy_0
0x18001c66f  xor     ebx, ebx
0x18001c671  cmp     [r15+70h], rbx
0x18001c675  jbe     loc_18001C800
0x18001c67b  mov     edi, ebx
0x18001c67d  mov     rax, [r15+78h]
0x18001c681  mov     r9d, 8
0x18001c687  mov     r8, [r15+50h]
0x18001c68b  mov     rdx, [r15+58h]
0x18001c68f  lea     rcx, [rax+r12*8]
0x18001c693  lea     rax, ?static_PageNumberCompare@CMemoryDiagnosticHandler@@CAHPEBX0@Z; CMemoryDiagnosticHandler::static_PageNumberCompare(void const *,void const *)
0x18001c69a  mov     [rsp+78h+var_58], rax
0x18001c69f  call    cs:__imp__o_bsearch
0x18001c6a5  test    rax, rax
0x18001c6a8  jnz     loc_18001C7E3
0x18001c6ae  inc     dword ptr [r15+90h]
0x18001c6b5  mov     eax, [r15+3Ch]
0x18001c6b9  cmp     rsi, rax
0x18001c6bc  jnb     loc_18001C7B4
0x18001c6c2  mov     rax, [r15+78h]
0x18001c6c6  mov     r14d, 1
0x18001c6cc  mov     rbx, [rax+r12*8]
0x18001c6d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c6d7  lea     r9, WPP_GLOBAL_Control
0x18001c6de  cmp     rcx, r9
0x18001c6e1  jz      short loc_18001C707
0x18001c6e3  test    byte ptr [rcx+1Ch], 4
0x18001c6e7  jz      short loc_18001C707
0x18001c6e9  mov     rcx, [rcx+10h]
0x18001c6ed  lea     edx, [r14+2Fh]
0x18001c6f1  mov     r9, rbx
0x18001c6f4  call    WPP_SF_P
0x18001c6f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c700  lea     r9, WPP_GLOBAL_Control
0x18001c707  xor     edx, edx
0x18001c709  test    rsi, rsi
0x18001c70c  jz      short loc_18001C72E
0x18001c70e  mov     r8, [r13+rdx*8+0]
0x18001c713  cmp     r8, rbx
0x18001c716  jz      short loc_18001C761
0x18001c718  ja      short loc_18001C753
0x18001c71a  lea     rax, [rbx-1]
0x18001c71e  cmp     r8, rax
0x18001c721  jnz     short loc_18001C726
0x18001c723  dec     r14d
0x18001c726  inc     rdx
0x18001c729  cmp     rdx, rsi
0x18001c72c  jb      short loc_18001C70E
0x18001c72e  mov     r8, [rbp+arg_10]
0x18001c732  movsxd  rax, r14d
0x18001c735  add     r8, rax
0x18001c738  cmp     r8, 80h
0x18001c73f  jbe     short loc_18001C788
0x18001c741  cmp     rcx, r9
0x18001c744  jz      short loc_18001C784
0x18001c746  test    byte ptr [rcx+1Ch], 4
0x18001c74a  jz      short loc_18001C784
0x18001c74c  mov     edx, 32h ; '2'
0x18001c751  jmp     short loc_18001C771
0x18001c753  lea     rax, [rbx+1]
0x18001c757  cmp     r8, rax
0x18001c75a  jnz     short loc_18001C72E
0x18001c75c  dec     r14d
0x18001c75f  jmp     short loc_18001C72E
0x18001c761  cmp     rcx, r9
0x18001c764  jz      short loc_18001C784
0x18001c766  test    byte ptr [rcx+1Ch], 4
0x18001c76a  jz      short loc_18001C784
0x18001c76c  mov     edx, 31h ; '1'
0x18001c771  mov     rcx, [rcx+10h]
0x18001c775  mov     r9, rbx
0x18001c778  call    WPP_SF_P
0x18001c77d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c784  xor     ebx, ebx
0x18001c786  jmp     short loc_18001C7EA
0x18001c788  mov     [rbp+arg_10], r8
0x18001c78c  mov     rcx, rsi
0x18001c78f  cmp     rsi, rdx
0x18001c792  jbe     short loc_18001C7A6
0x18001c794  mov     rax, [r13+rcx*8-8]
  ... truncated ...
```
