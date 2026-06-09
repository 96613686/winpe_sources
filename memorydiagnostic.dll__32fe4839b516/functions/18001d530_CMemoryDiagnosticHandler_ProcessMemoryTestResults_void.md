# CMemoryDiagnosticHandler::ProcessMemoryTestResults(void)

- ea: `0x18001d530`
- end: `0x18001dd4c`
- name: `?ProcessMemoryTestResults@CMemoryDiagnosticHandler@@AEAAJXZ`
- size: `2076`
- prototype: `__int64 __fastcall(CMemoryDiagnosticHandler *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ead0`

## callees

- `0x180002b0c`
- `0x180002b4c`
- `0x18001b550`
- `0x18001d310`
- `0x18001d530`
- `0x18001dd54`
- `0x18001f560`
- `0x18001f594`
- `0x18001f5dc`
- `0x18001f624`
- `0x18001f6d4`
- `0x180021ffc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_bsearch` at `0x18001d8ef`
- `api-ms-win-crt-private-l1-1-0!_o_bsearch` at `0x18001d8ef`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001d72d`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001d72d`
- `bcd!BcdSetElementData` at `0x18001db73`
- `bcd!BcdSetElementData` at `0x18001db73`
- `bcd!BcdCloseObject` at `0x18001d7e4`
- `bcd!BcdCloseObject` at `0x18001dbf6`
- `bcd!BcdCloseObject` at `0x18001d7e4`
- `bcd!BcdCloseObject` at `0x18001dbf6`
- `bcd!BcdOpenSystemStore` at `0x18001d597`
- `bcd!BcdOpenSystemStore` at `0x18001dab8`
- `bcd!BcdOpenSystemStore` at `0x18001d597`
- `bcd!BcdOpenSystemStore` at `0x18001dab8`
- `bcd!BcdOpenObject` at `0x18001d5e3`
- `bcd!BcdOpenObject` at `0x18001db14`
- `bcd!BcdOpenObject` at `0x18001d5e3`
- `bcd!BcdOpenObject` at `0x18001db14`
- `bcd!BcdGetElementData` at `0x18001d629`
- `bcd!BcdGetElementData` at `0x18001d681`
- `bcd!BcdGetElementData` at `0x18001d629`
- `bcd!BcdGetElementData` at `0x18001d681`
- `bcd!BcdCloseStore` at `0x18001d803`
- `bcd!BcdCloseStore` at `0x18001dc15`
- `bcd!BcdCloseStore` at `0x18001d803`
- `bcd!BcdCloseStore` at `0x18001dc15`

## pseudocode

```c
__int64 __fastcall CMemoryDiagnosticHandler::ProcessMemoryTestResults(unsigned __int64 **this)
{
  unsigned __int64 *v1; // r14
  unsigned __int64 v2; // r12
  unsigned __int64 v4; // rdx
  int BadPageList; // ebx
  int v6; // edi
  __int64 *v7; // r15
  int ElementData; // eax
  __int64 v9; // r8
  int v10; // ebx
  CMemoryDiagnosticHandler *v11; // rcx
  __int64 v12; // rdx
  size_t v13; // rsi
  __int64 v14; // r14
  __int64 v15; // r8
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  size_t i; // rbx
  CMemoryDiagnosticHandler **v19; // r8
  __int64 v20; // rdx
  unsigned __int64 v21; // r14
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // r8
  unsigned __int64 v24; // rsi
  unsigned int v25; // r15d
  unsigned __int64 *v26; // rax
  int v27; // edi
  unsigned __int64 v28; // rbx
  CMemoryDiagnosticHandler *v29; // rcx
  _QWORD *v30; // r9
  __int64 v31; // rdx
  unsigned __int64 j; // rcx
  unsigned int v33; // edi
  int v34; // eax
  int v35; // edi
  __int64 v36; // rdx
  unsigned __int64 v37; // rax
  CMemoryDiagnosticHandler *v38; // rcx
  CMemoryDiagnosticHandler *v39; // rcx
  void *v41; // [rsp+30h] [rbp-39h]
  __int64 *v42; // [rsp+38h] [rbp-31h]
  __int64 v43; // [rsp+40h] [rbp-29h] BYREF
  void *Src[2]; // [rsp+48h] [rbp-21h]
  void *v45[2]; // [rsp+60h] [rbp-9h]
  unsigned int v46; // [rsp+D0h] [rbp+67h]
  unsigned __int64 v47; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned __int64 v48; // [rsp+E0h] [rbp+77h]
  __int64 v49; // [rsp+E8h] [rbp+7Fh] BYREF

  v1 = (unsigned __int64 *)(this + 14);
  v48 = 0;
  v2 = 0;
  v46 = 0;
  *(_OWORD *)Src = 0;
  *(_OWORD *)v45 = 0;
  BadPageList = CMemoryDiagnosticHandler::QueryBadPageList(
                  (CMemoryDiagnosticHandler *)this,
                  this + 15,
                  (unsigned __int64 *)this + 14);
  if ( BadPageList < 0 )
  {
    v7 = (__int64 *)Src[0];
    goto LABEL_137;
  }
  v43 = 0;
  v6 = 0;
  v49 = 0;
  v7 = 0;
  LODWORD(v47) = 0;
  ElementData = BcdOpenSystemStore(&v43);
  v10 = ElementData;
  if ( ElementData >= 0 )
  {
    ElementData = BcdOpenObject(v43, &GUID_BAD_MEMORY_GROUP, &v49);
    v10 = ElementData;
    if ( ElementData >= 0 )
    {
      ElementData = BcdGetElementData(v49, 385875978, 0, &v47);
      v10 = ElementData;
      if ( ElementData == -1073741275 )
        goto LABEL_23;
      if ( ElementData == -1073741789 )
      {
        v42 = (__int64 *)operator new[]((unsigned int)v47);
        v7 = v42;
        ElementData = BcdGetElementData(v49, 385875978, v42, &v47);
        v10 = ElementData;
        if ( ElementData >= 0 )
        {
          v13 = (unsigned __int64)(unsigned int)v47 >> 3;
          v41 = (void *)v13;
          v48 = 1;
          v14 = 1;
          qsort(v42, v13, 8u, CMemoryDiagnosticHandler::static_PageNumberCompare);
          v16 = *v42;
          v17 = 1;
          if ( v13 > 1 )
          {
            do
            {
              if ( v42[v17] > (unsigned __int64)(v16 + 1) )
                ++v14;
              v16 = v42[v17++];
            }
            while ( v17 < v13 );
            v48 = v14;
          }
          v11 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control )
            {
              WPP_SF_PP(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v15, v13, v14);
              v11 = WPP_GLOBAL_Control;
            }
            for ( i = 0; i < v13; ++i )
            {
              if ( v11 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
              {
                WPP_SF_P(*((_QWORD *)v11 + 2), 68, v15, v42[i]);
                v11 = WPP_GLOBAL_Control;
              }
            }
          }
          v1 = (unsigned __int64 *)(this + 14);
          goto LABEL_39;
        }
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_20;
        }
        v12 = 66;
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_20;
        }
        v12 = 64;
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_20;
      }
      v12 = 63;
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_20;
    }
    v12 = 62;
  }
  WPP_SF_D(*((_QWORD *)v11 + 2), v12, v9, (unsigned int)ElementData);
  v11 = WPP_GLOBAL_Control;
LABEL_20:
  v6 = v10 | 0x10000000;
  if ( v10 >= 0 || !v7 )
  {
    v13 = (size_t)Src[1];
    v7 = (__int64 *)Src[0];
    v41 = Src[1];
    v42 = (__int64 *)Src[0];
    goto LABEL_39;
  }
  operator delete(v7, v4);
LABEL_23:
  v13 = (size_t)Src[1];
  v7 = (__int64 *)Src[0];
  v11 = WPP_GLOBAL_Control;
  v41 = Src[1];
  v42 = (__int64 *)Src[0];
LABEL_39:
  BadPageList = v6;
  if ( v49 )
  {
    BcdCloseObject(v49);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v43 )
  {
    BcdCloseStore(v43);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v6 < 0 )
  {
    v19 = &WPP_GLOBAL_Control;
    if ( v11 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
      goto LABEL_119;
  }
  BadPageList = v6;
  if ( v6 < 0 )
    goto LABEL_137;
  v4 = *v1 + v13;
  if ( v4 < *v1 )
  {
    BadPageList = -2147024362;
    if ( v11 == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
      goto LABEL_137;
    v20 = 51;
LABEL_52:
    WPP_SF_(*((_QWORD *)v11 + 2), v20);
    goto LABEL_137;
  }
  BadPageList = 0;
  if ( !v4 )
  {
    if ( v11 == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 2) == 0 )
      goto LABEL_137;
    v20 = 52;
    goto LABEL_52;
  }
  v45[0] = operator new[](saturated_mul(v4, 8u));
  v21 = v13;
  memcpy_0(v45[0], v7, 8 * v13);
  if ( !this[14] )
  {
    v29 = WPP_GLOBAL_Control;
    goto LABEL_87;
  }
  v24 = v48;
  v25 = 0;
  do
  {
    if ( _o_bsearch(&this[15][v2], this[11], this[10], 8, CMemoryDiagnosticHandler::static_PageNumberCompare) )
      goto LABEL_83;
    ++*((_DWORD *)this + 36);
    if ( v21 < *((unsigned int *)this + 15) )
    {
      v26 = this[15];
      v27 = 1;
      v28 = v26[v2];
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, v23, v26[v2]);
        v29 = WPP_GLOBAL_Control;
      }
      v30 = v45[0];
      v23 = 0;
      if ( v21 )
      {
        while ( 1 )
        {
          v22 = *((_QWORD *)v45[0] + v23);
          if ( v22 == v28 )
            break;
          if ( v22 > v28 )
          {
            if ( v22 == v28 + 1 )
              --v27;
            goto LABEL_66;
          }
          if ( v22 == v28 - 1 )
            --v27;
          if ( ++v23 >= v21 )
            goto LABEL_66;
        }
        if ( v29 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 4) != 0 )
        {
          v31 = 49;
          goto LABEL_75;
        }
        goto LABEL_76;
      }
LABEL_66:
      if ( v24 + v27 > 0x80 )
      {
        if ( v29 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 4) != 0 )
        {
          v31 = 50;
LABEL_75:
          WPP_SF_P(*((_QWORD *)v29 + 2), v31, v23, v28);
          v29 = WPP_GLOBAL_Control;
        }
LABEL_76:
        BadPageList = 0;
        goto LABEL_84;
      }
      for ( j = v21; j > v23; --j )
        v30[j] = v30[j - 1];
      ++v21;
      v24 += v27;
      v30[v23] = v28;
      ++v25;
      BadPageList = 0;
      goto LABEL_83;
    }
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, v23, this[15][v2]);
LABEL_83:
      v29 = WPP_GLOBAL_Control;
    }
LABEL_84:
    ++v2;
  }
  while ( v2 < (unsigned __int64)this[14] );
  v46 = v25;
  v7 = v42;
  v48 = v24;
  v13 = (size_t)v41;
LABEL_87:
  if ( v29 == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control || (*((_BYTE *)v29 + 28) & 4) == 0 )
  {
    v33 = v46;
  }
  else
  {
    v33 = v46;
    WPP_SF_II(*((_QWORD *)v29 + 2), v22, v23, *((unsigned int *)this + 36), v46);
    v29 = WPP_GLOBAL_Control;
  }
  if ( !v33 || v21 <= v13 )
  {
LABEL_122:
    v4 = *((unsigned int *)this + 15);
    if ( v21 >= v4 )
    {
      *((_DWORD *)this + 27) |= 0x10u;
      v29 = WPP_GLOBAL_Control;
    }
    v37 = v48;
    if ( v48 >= 0x80 )
    {
      *((_DWORD *)this + 27) |= 0x20u;
      v29 = WPP_GLOBAL_Control;
    }
    if ( v21 >= v4 || v37 >= 0x80 )
    {
      if ( v29 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)v29 + 2), 56);
      CMemoryDiagnosticHandler::LogPageRetiredEvent(v29, v21, 1);
      BadPageList = CMemoryDiagnosticHandler::ConfigureMemoryDiagnosticTask(v38, L"RunFullMemoryDiagnostic");
      if ( BadPageList >= 0 )
        BadPageList = CMemoryDiagnosticHandler::ConfigureMemoryDiagnosticTask(v39, L"ProcessMemoryDiagnosticEvents");
    }
    goto LABEL_137;
  }
  v49 = 0;
  v47 = 0;
  v34 = BcdOpenSystemStore(&v49);
  if ( v34 >= 0 )
  {
    v34 = BcdOpenObject(v49, &GUID_BAD_MEMORY_GROUP, &v47);
    if ( v34 >= 0 )
    {
      if ( 8 * (unsigned __int64)(unsigned int)v21 > 0xFFFFFFFF )
      {
        v35 = -2147024362;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_112;
        }
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83);
LABEL_111:
        v11 = WPP_GLOBAL_Control;
        goto LABEL_112;
      }
      v35 = 0;
      v34 = BcdSetElementData(v47, 385875978, v45[0]);
      if ( v34 >= 0 )
        goto LABEL_111;
      v35 = v34 | 0x10000000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_112;
      }
      v36 = 84;
    }
    else
    {
      v35 = v34 | 0x10000000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_112;
      }
      v36 = 82;
    }
LABEL_97:
    WPP_SF_D(*((_QWORD *)v11 + 2), v36, v19, (unsigned int)v34);
    goto LABEL_111;
  }
  v35 = v34 | 0x10000000;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v36 = 81;
    goto LABEL_97;
  }
LABEL_112:
  BadPageList = v35;
  if ( v47 )
  {
    BcdCloseObject(v47);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v49 )
  {
    BcdCloseStore(v49);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v35 < 0 && v11 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
  {
LABEL_119:
    WPP_SF_D(*((_QWORD *)v11 + 2), 10, v19, (unsigned int)BadPageList);
    goto LABEL_137;
  }
  BadPageList = v35;
  if ( v35 >= 0 )
  {
    *((_DWORD *)this + 37) = v46;
    CMemoryDiagnosticHandler::LogPageRetiredEvent(v11, v46, 0);
    v29 = WPP_GLOBAL_Control;
    goto LABEL_122;
  }
LABEL_137:
  if ( v7 )
    operator delete(v7, v4);
  if ( v45[0] )
    operator delete(v45[0], v4);
  return (unsigned int)BadPageList;
}

```

## disassembly

```asm
0x18001d530  push    rbp
0x18001d532  push    rbx
0x18001d533  push    rsi
0x18001d534  push    rdi
0x18001d535  push    r12
0x18001d537  push    r13
0x18001d539  push    r14
0x18001d53b  push    r15
0x18001d53d  lea     rbp, [rsp-1Fh]
0x18001d542  sub     rsp, 88h
0x18001d549  lea     r14, [rcx+70h]
0x18001d54d  xorps   xmm0, xmm0
0x18001d550  xor     eax, eax
0x18001d552  lea     rdx, [rcx+78h]; unsigned __int64 **
0x18001d556  xorps   xmm1, xmm1
0x18001d559  mov     [rbp+57h+arg_10], rax
0x18001d55d  xor     r12d, r12d
0x18001d560  mov     r8, r14; unsigned __int64 *
0x18001d563  mov     r13, rcx
0x18001d566  mov     dword ptr [rbp+57h+arg_0], r12d
0x18001d56a  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18001d56e  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x18001d572  call    ?QueryBadPageList@CMemoryDiagnosticHandler@@AEAAJPEAPEA_KPEA_K@Z; CMemoryDiagnosticHandler::QueryBadPageList(unsigned __int64 * *,unsigned __int64 *)
0x18001d577  mov     ebx, eax
0x18001d579  test    eax, eax
0x18001d57b  js      loc_18001DD16
0x18001d581  lea     rcx, [rbp+57h+var_80]
0x18001d585  mov     [rbp+57h+var_80], r12
0x18001d589  mov     edi, r12d
0x18001d58c  mov     [rbp+57h+arg_18], r12
0x18001d590  mov     r15d, r12d
0x18001d593  mov     dword ptr [rbp+57h+arg_8], r12d
0x18001d597  call    cs:__imp_BcdOpenSystemStore
0x18001d59e  nop     dword ptr [rax+rax+00h]
0x18001d5a3  lea     rsi, WPP_GLOBAL_Control
0x18001d5aa  mov     ebx, eax
0x18001d5ac  test    eax, eax
0x18001d5ae  jns     short loc_18001D5D4
0x18001d5b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5b7  cmp     rcx, rsi
0x18001d5ba  jz      loc_18001D6BD
0x18001d5c0  test    byte ptr [rcx+1Ch], 1
0x18001d5c4  jz      loc_18001D6BD
0x18001d5ca  lea     edx, [r12+3Eh]
0x18001d5cf  jmp     loc_18001D6AA
0x18001d5d4  mov     rcx, [rbp+57h+var_80]
0x18001d5d8  lea     r8, [rbp+57h+arg_18]
0x18001d5dc  lea     rdx, GUID_BAD_MEMORY_GROUP
0x18001d5e3  call    cs:__imp_BcdOpenObject
0x18001d5ea  nop     dword ptr [rax+rax+00h]
0x18001d5ef  mov     ebx, eax
0x18001d5f1  test    eax, eax
0x18001d5f3  jns     short loc_18001D619
0x18001d5f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5fc  cmp     rcx, rsi
0x18001d5ff  jz      loc_18001D6BD
0x18001d605  test    byte ptr [rcx+1Ch], 1
0x18001d609  jz      loc_18001D6BD
0x18001d60f  mov     edx, 3Fh ; '?'
0x18001d614  jmp     loc_18001D6AA
0x18001d619  mov     rcx, [rbp+57h+arg_18]
0x18001d61d  lea     r9, [rbp+57h+arg_8]
0x18001d621  xor     r8d, r8d
0x18001d624  mov     edx, 1700000Ah
0x18001d629  call    cs:__imp_BcdGetElementData
0x18001d630  nop     dword ptr [rax+rax+00h]
0x18001d635  mov     ebx, eax
0x18001d637  cmp     eax, 0C0000225h
0x18001d63c  jz      loc_18001D6D4
0x18001d642  cmp     eax, 0C0000023h
0x18001d647  jz      short loc_18001D662
0x18001d649  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d650  cmp     rcx, rsi
0x18001d653  jz      short loc_18001D6BD
0x18001d655  test    byte ptr [rcx+1Ch], 1
0x18001d659  jz      short loc_18001D6BD
0x18001d65b  mov     edx, 40h ; '@'
0x18001d660  jmp     short loc_18001D6AA
0x18001d662  mov     ecx, dword ptr [rbp+57h+arg_8]; unsigned __int64
0x18001d665  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001d66a  mov     rcx, [rbp+57h+arg_18]
0x18001d66e  lea     r9, [rbp+57h+arg_8]
0x18001d672  mov     r8, rax
0x18001d675  mov     [rbp+57h+var_88], rax
0x18001d679  mov     edx, 1700000Ah
0x18001d67e  mov     r15, rax
0x18001d681  call    cs:__imp_BcdGetElementData
0x18001d688  nop     dword ptr [rax+rax+00h]
0x18001d68d  mov     ebx, eax
0x18001d68f  test    eax, eax
0x18001d691  jns     short loc_18001D705
0x18001d693  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d69a  cmp     rcx, rsi
0x18001d69d  jz      short loc_18001D6BD
0x18001d69f  test    byte ptr [rcx+1Ch], 1
0x18001d6a3  jz      short loc_18001D6BD
0x18001d6a5  mov     edx, 42h ; 'B'
0x18001d6aa  mov     rcx, [rcx+10h]
0x18001d6ae  mov     r9d, eax
0x18001d6b1  call    WPP_SF_D
0x18001d6b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6bd  or      ebx, 10000000h
0x18001d6c3  mov     edi, ebx
0x18001d6c5  jge     short loc_18001D6F0
0x18001d6c7  test    r15, r15
0x18001d6ca  jz      short loc_18001D6F0
0x18001d6cc  mov     rcx, r15; void *
0x18001d6cf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d6d4  mov     rsi, [rbp+57h+Src+8]
0x18001d6d8  mov     r15, [rbp+57h+Src]
0x18001d6dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6e3  mov     [rbp+57h+var_90], rsi
0x18001d6e7  mov     [rbp+57h+var_88], r15
0x18001d6eb  jmp     loc_18001D7D6
0x18001d6f0  mov     rsi, [rbp+57h+Src+8]
0x18001d6f4  mov     r15, [rbp+57h+Src]
0x18001d6f8  mov     [rbp+57h+var_90], rsi
0x18001d6fc  mov     [rbp+57h+var_88], r15
0x18001d700  jmp     loc_18001D7D6
0x18001d705  mov     esi, dword ptr [rbp+57h+arg_8]
0x18001d708  lea     r9, ?static_PageNumberCompare@CMemoryDiagnosticHandler@@CAHPEBX0@Z; CompareFunction
0x18001d70f  mov     ebx, 1
0x18001d714  shr     rsi, 3
0x18001d718  mov     rdx, rsi; NumOfElements
0x18001d71b  mov     [rbp+57h+var_90], rsi
0x18001d71f  mov     rcx, r15; Base
0x18001d722  mov     [rbp+57h+arg_10], rbx
0x18001d726  mov     r14d, ebx
0x18001d729  lea     r8d, [rbx+7]; SizeOfElements
0x18001d72d  call    cs:__imp_qsort
0x18001d734  nop     dword ptr [rax+rax+00h]
0x18001d739  mov     rax, [r15]
0x18001d73c  mov     ecx, ebx
0x18001d73e  cmp     rsi, rbx
0x18001d741  jbe     short loc_18001D75F
0x18001d743  inc     rax
0x18001d746  cmp     [r15+rcx*8], rax
0x18001d74a  jbe     short loc_18001D74F
0x18001d74c  add     r14, rbx
0x18001d74f  mov     rax, [r15+rcx*8]
0x18001d753  add     rcx, rbx
0x18001d756  cmp     rcx, rsi
0x18001d759  jb      short loc_18001D743
0x18001d75b  mov     [rbp+57h+arg_10], r14
0x18001d75f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d766  test    byte ptr [rcx+1Ch], 4
0x18001d76a  jz      short loc_18001D7D2
0x18001d76c  lea     rax, WPP_GLOBAL_Control
0x18001d773  cmp     rcx, rax
0x18001d776  jz      short loc_18001D797
0x18001d778  mov     rcx, [rcx+10h]
0x18001d77c  mov     r9, rsi
0x18001d77f  mov     [rsp+0C0h+var_A0], r14
0x18001d784  call    WPP_SF_PP
0x18001d789  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d790  lea     rax, WPP_GLOBAL_Control
0x18001d797  mov     rbx, r12
0x18001d79a  test    rsi, rsi
0x18001d79d  jz      short loc_18001D7D2
0x18001d79f  cmp     rcx, rax
0x18001d7a2  jz      short loc_18001D7CA
0x18001d7a4  test    byte ptr [rcx+1Ch], 4
0x18001d7a8  jz      short loc_18001D7CA
0x18001d7aa  mov     r9, [r15+rbx*8]
0x18001d7ae  mov     edx, 44h ; 'D'
0x18001d7b3  mov     rcx, [rcx+10h]
0x18001d7b7  call    WPP_SF_P
0x18001d7bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7c3  lea     rax, WPP_GLOBAL_Control
0x18001d7ca  inc     rbx
0x18001d7cd  cmp     rbx, rsi
0x18001d7d0  jb      short loc_18001D79F
0x18001d7d2  lea     r14, [r13+70h]
0x18001d7d6  mov     rax, [rbp+57h+arg_18]
0x18001d7da  mov     ebx, edi
0x18001d7dc  test    rax, rax
0x18001d7df  jz      short loc_18001D7F7
0x18001d7e1  mov     rcx, rax
0x18001d7e4  call    cs:__imp_BcdCloseObject
0x18001d7eb  nop     dword ptr [rax+rax+00h]
0x18001d7f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7f7  mov     rax, [rbp+57h+var_80]
0x18001d7fb  test    rax, rax
0x18001d7fe  jz      short loc_18001D816
0x18001d800  mov     rcx, rax
0x18001d803  call    cs:__imp_BcdCloseStore
0x18001d80a  nop     dword ptr [rax+rax+00h]
0x18001d80f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d816  test    edi, edi
0x18001d818  jns     short loc_18001D831
0x18001d81a  lea     r8, WPP_GLOBAL_Control
0x18001d821  cmp     rcx, r8
0x18001d824  jz      short loc_18001D838
0x18001d826  test    byte ptr [rcx+1Ch], 1
0x18001d82a  jz      short loc_18001D838
0x18001d82c  jmp     loc_18001DC37
0x18001d831  lea     r8, WPP_GLOBAL_Control
0x18001d838  mov     ebx, edi
0x18001d83a  test    edi, edi
0x18001d83c  js      loc_18001DD1A
0x18001d842  mov     rax, [r14]
0x18001d845  lea     rdx, [rax+rsi]
0x18001d849  cmp     rdx, rax
0x18001d84c  jb      loc_18001DCFC
0x18001d852  mov     ebx, r12d
0x18001d855  test    rdx, rdx
0x18001d858  jnz     short loc_18001D880
0x18001d85a  cmp     rcx, r8
0x18001d85d  jz      loc_18001DD1A
0x18001d863  test    byte ptr [rcx+1Ch], 2
0x18001d867  jz      loc_18001DD1A
0x18001d86d  mov     edx, 34h ; '4'
0x18001d872  mov     rcx, [rcx+10h]
0x18001d876  call    WPP_SF_
0x18001d87b  jmp     loc_18001DD1A
0x18001d880  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d887  mov     eax, 8
0x18001d88c  mul     rdx
0x18001d88f  cmovo   rax, rcx
0x18001d893  mov     rcx, rax; unsigned __int64
0x18001d896  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001d89b  lea     r8, ds:0[rsi*8]; Size
0x18001d8a3  mov     [rbp+57h+var_60], rax
0x18001d8a7  mov     rdx, r15; Src
0x18001d8aa  mov     rcx, rax; void *
0x18001d8ad  mov     r14, rsi
0x18001d8b0  call    memcpy_0
0x18001d8b5  lea     rdi, WPP_GLOBAL_Control
0x18001d8bc  cmp     [r13+70h], rbx
0x18001d8c0  jbe     loc_18001DA62
0x18001d8c6  mov     rsi, [rbp+57h+arg_10]
0x18001d8ca  mov     r15d, ebx
0x18001d8cd  mov     rax, [r13+78h]
0x18001d8d1  mov     r9d, 8
0x18001d8d7  mov     r8, [r13+50h]
0x18001d8db  mov     rdx, [r13+58h]
0x18001d8df  lea     rcx, [rax+r12*8]
0x18001d8e3  lea     rax, ?static_PageNumberCompare@CMemoryDiagnosticHandler@@CAHPEBX0@Z; CMemoryDiagnosticHandler::static_PageNumberCompare(void const *,void const *)
0x18001d8ea  mov     [rsp+0C0h+var_A0], rax
0x18001d8ef  call    cs:__imp__o_bsearch
0x18001d8f6  nop     dword ptr [rax+rax+00h]
0x18001d8fb  test    rax, rax
0x18001d8fe  jnz     loc_18001DA3C
0x18001d904  inc     dword ptr [r13+90h]
0x18001d90b  mov     eax, [r13+3Ch]
0x18001d90f  cmp     r14, rax
0x18001d912  jnb     loc_18001DA14
0x18001d918  mov     rax, [r13+78h]
0x18001d91c  mov     edi, 1
0x18001d921  mov     rbx, [rax+r12*8]
0x18001d925  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d92c  lea     r10, WPP_GLOBAL_Control
0x18001d933  cmp     rcx, r10
0x18001d936  jz      short loc_18001D95B
0x18001d938  test    byte ptr [rcx+1Ch], 4
0x18001d93c  jz      short loc_18001D95B
0x18001d93e  mov     rcx, [rcx+10h]
0x18001d942  lea     edx, [rdi+2Fh]
0x18001d945  mov     r9, rbx
0x18001d948  call    WPP_SF_P
0x18001d94d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d954  lea     r10, WPP_GLOBAL_Control
0x18001d95b  mov     r9, [rbp+57h+var_60]
0x18001d95f  xor     r8d, r8d
0x18001d962  test    r14, r14
0x18001d965  jz      short loc_18001D985
0x18001d967  mov     rdx, [r9+r8*8]
0x18001d96b  cmp     rdx, rbx
0x18001d96e  jz      short loc_18001D9B2
0x18001d970  ja      short loc_18001D9A5
0x18001d972  lea     rax, [rbx-1]
0x18001d976  cmp     rdx, rax
0x18001d979  jnz     short loc_18001D97D
0x18001d97b  dec     edi
0x18001d97d  inc     r8
0x18001d980  cmp     r8, r14
0x18001d983  jb      short loc_18001D967
0x18001d985  movsxd  rax, edi
0x18001d988  add     rax, rsi
0x18001d98b  cmp     rax, 80h
0x18001d991  jbe     short loc_18001D9E0
0x18001d993  cmp     rcx, r10
0x18001d996  jz      short loc_18001D9D5
0x18001d998  test    byte ptr [rcx+1Ch], 4
0x18001d99c  jz      short loc_18001D9D5
0x18001d99e  mov     edx, 32h ; '2'
0x18001d9a3  jmp     short loc_18001D9C2
0x18001d9a5  lea     rax, [rbx+1]
0x18001d9a9  cmp     rdx, rax
0x18001d9ac  jnz     short loc_18001D985
0x18001d9ae  dec     edi
0x18001d9b0  jmp     short loc_18001D985
0x18001d9b2  cmp     rcx, r10
0x18001d9b5  jz      short loc_18001D9D5
0x18001d9b7  test    byte ptr [rcx+1Ch], 4
0x18001d9bb  jz      short loc_18001D9D5
0x18001d9bd  mov     edx, 31h ; '1'
0x18001d9c2  mov     rcx, [rcx+10h]
0x18001d9c6  mov     r9, rbx
0x18001d9c9  call    WPP_SF_P
  ... truncated ...
```
