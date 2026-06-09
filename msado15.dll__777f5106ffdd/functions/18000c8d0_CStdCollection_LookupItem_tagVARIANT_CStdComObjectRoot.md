# CStdCollection::LookupItem(tagVARIANT &,CStdComObjectRoot * *)

- ea: `0x18000c8d0`
- end: `0x18000cd79`
- name: `?LookupItem@CStdCollection@@UEAAJAEAUtagVARIANT@@PEAPEAVCStdComObjectRoot@@@Z`
- size: `1193`
- prototype: `int(CStdCollection *__hidden this, struct tagVARIANT *, struct CStdComObjectRoot **)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b830`
- `0x180081760`
- `0x180087eb0`

## callees

- `0x18000c8d0`
- `0x18000d2a0`
- `0x1800c8f34`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x18000c919`
- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x18000c919`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x18000c9a0`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x18000c9a0`
- `MSDART!MpHeapFree` at `0x18000cae8`
- `MSDART!MpHeapFree` at `0x18000cc78`
- `MSDART!MpHeapFree` at `0x18000cca1`
- `MSDART!MpHeapFree` at `0x18000cae8`
- `MSDART!MpHeapFree` at `0x18000cc78`
- `MSDART!MpHeapFree` at `0x18000cca1`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000cd14`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000cd14`

## pseudocode

```c
__int64 __fastcall CStdCollection::LookupItem(
        CStdCollection *this,
        struct tagVARIANT *pvarVal,
        struct CStdComObjectRoot **a3)
{
  CReaderWriterLock3AR *v6; // rbp
  bool v7; // al
  VARTYPE vt; // dx
  bool i; // r15
  __int64 lVal; // rcx
  __int64 v11; // rdx
  int v12; // ebx
  __int64 result; // rax
  const WCHAR *bstrVal; // rcx
  __int16 v15; // dx
  LONGLONG llVal; // rax
  __int64 v17; // rdi
  char v18; // r9
  unsigned __int8 *v19; // r11
  unsigned __int8 *v20; // rax
  __int16 v21; // cx
  unsigned int v22; // r10d
  __int64 v23; // r8
  unsigned __int8 *v24; // rax
  __int64 v25; // r9
  int v26; // ecx
  int v27; // edx
  unsigned int v28; // esi
  unsigned __int8 v29; // r9
  unsigned __int8 *v30; // rax
  int v31; // r8d
  _WORD *v32; // rdx
  HRESULT v33; // eax
  unsigned __int8 *v34; // [rsp+30h] [rbp-468h] BYREF
  VARIANTARG pvargDest; // [rsp+38h] [rbp-460h] BYREF
  char v36[1024]; // [rsp+50h] [rbp-448h] BYREF
  __int64 v37; // [rsp+450h] [rbp-48h]

  if ( !*((_DWORD *)this + 21)
    || (result = (*(__int64 (__fastcall **)(CStdCollection *, _QWORD, __int64))(*(_QWORD *)this + 128LL))(this, 0, 1),
        v28 = result,
        (int)result >= 0) )
  {
    v6 = (CStdCollection *)((char *)this + 72);
    v7 = CReaderWriterLock3AR::ReadOrWriteLock((CStdCollection *)((char *)this + 72));
    vt = pvarVal->vt;
    for ( i = v7; pvarVal->vt == 16396; vt = pvarVal->vt )
      pvarVal = pvarVal->pvarVal;
    if ( (vt & 0xBFFF) == 8 )
    {
      bstrVal = pvarVal->bstrVal;
      v15 = vt & 0x4000;
      if ( v15 )
        llVal = *(_QWORD *)bstrVal;
      else
        llVal = pvarVal->llVal;
      if ( llVal )
      {
        v17 = *((_QWORD *)this + 8);
        if ( v15 )
          bstrVal = *(const WCHAR **)bstrVal;
        v18 = *(_BYTE *)(v17 + 44);
        v37 = 0;
        v34 = 0;
        v12 = CSortKey::Create((CSortKey *)v36, bstrVal, &v34, v18, 0);
        if ( v12 < 0 )
        {
          if ( v37 )
            MpHeapFree(g_hHeapHandle, v37);
          goto LABEL_9;
        }
        v19 = v34;
        v20 = v34;
        if ( v34 )
        {
          v21 = *v34;
          LODWORD(v34) = 0;
          if ( (_BYTE)v21 )
          {
            v29 = v20[1];
            v30 = v20 + 1;
            LOWORD(v34) = v21;
            WORD1(v34) = v21;
            if ( v29 )
            {
              v31 = 1;
              do
              {
                v32 = (_WORD *)&v34 + v31;
                v31 ^= 1u;
                ++v30;
                *v32 += v29;
                v29 = *v30;
              }
              while ( *v30 );
            }
          }
          v22 = (unsigned int)v34;
        }
        else
        {
          v22 = 0;
        }
        v23 = *(_QWORD *)(*(_QWORD *)(v17 + 32) + 8LL * (v22 % *(_DWORD *)(v17 + 24)));
        if ( v23 )
        {
          while ( v23 )
          {
            if ( *(_DWORD *)v23 == v22 )
            {
              if ( v19 )
              {
                v24 = *(unsigned __int8 **)(v23 + 32);
                if ( v24 )
                {
                  v25 = v19 - v24;
                  do
                  {
                    v26 = v24[v25];
                    v27 = *v24 - v26;
                    if ( v27 )
                      break;
                    ++v24;
                  }
                  while ( v26 );
                  if ( !v27 )
                    goto LABEL_30;
                }
              }
              if ( v19 == *(unsigned __int8 **)(v23 + 32) )
              {
LABEL_30:
                v12 = 0;
                *a3 = *(struct CStdComObjectRoot **)(v23 + 24);
                goto LABEL_31;
              }
            }
            v23 = *(_QWORD *)(v23 + 40);
          }
          v12 = 1;
LABEL_31:
          if ( v37 )
            MpHeapFree(g_hHeapHandle, v37);
          if ( v12 == 1 )
            v12 = -2146825023;
          goto LABEL_9;
        }
        if ( v37 )
        {
          MpHeapFree(g_hHeapHandle, v37);
          v12 = -2146825023;
          goto LABEL_9;
        }
      }
      goto LABEL_51;
    }
    memset(&pvargDest, 0, sizeof(pvargDest));
    if ( vt == 3 )
    {
      lVal = pvarVal->lVal;
      goto LABEL_6;
    }
    if ( vt <= 0x4002u )
    {
      if ( vt == 16386 )
      {
        lVal = *pvarVal->piVal;
        goto LABEL_6;
      }
      if ( vt == 2 )
      {
        lVal = pvarVal->iVal;
        goto LABEL_6;
      }
      if ( vt != 4 && vt != 5 )
      {
        if ( vt == 16 )
        {
          lVal = pvarVal->bVal;
        }
        else
        {
          if ( vt != 20 )
            goto LABEL_51;
          lVal = pvarVal->llVal;
        }
LABEL_6:
        if ( lVal >= 0 )
        {
          v11 = *((_QWORD *)this + 8);
          if ( lVal < (unsigned __int64)*(unsigned int *)(v11 + 16) )
          {
            v12 = 0;
            *a3 = *(struct CStdComObjectRoot **)(*(_QWORD *)(v11 + 8) + 8 * lVal);
LABEL_9:
            CReaderWriterLock3AR::ReadOrWriteUnlock(v6, i);
            return (unsigned int)v12;
          }
          *a3 = 0;
        }
LABEL_51:
        v12 = -2146825023;
        goto LABEL_9;
      }
    }
    else
    {
      if ( vt == 16387 )
      {
        lVal = *pvarVal->plVal;
        goto LABEL_6;
      }
      if ( vt != 16388 && vt != 16389 )
      {
        if ( vt == 16400 )
        {
          lVal = *pvarVal->pbVal;
        }
        else
        {
          if ( vt != 16404 )
            goto LABEL_51;
          lVal = *pvarVal->pllVal;
        }
        goto LABEL_6;
      }
    }
    v33 = VariantChangeType(&pvargDest, pvarVal, 0, 0x14u);
    v12 = v33;
    if ( v33 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceW(
          off_18012A1B8[0],
          551945,
          L"<CStdCollection::LookupItem|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)v33,
          539);
      goto LABEL_9;
    }
    lVal = pvargDest.llVal;
    goto LABEL_6;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    bidTraceW(
      off_18012A1B8[0],
      459785,
      L"<CStdCollection::LookupItem|ADO|ERR> 0x%08x{HRESULT} line %d\n",
      (unsigned int)result,
      449);
    return v28;
  }
  return result;
}

```

## disassembly

```asm
0x18000c8d0  push    rbx
0x18000c8d2  push    rsi
0x18000c8d3  push    rdi
0x18000c8d4  push    r14
0x18000c8d6  sub     rsp, 478h
0x18000c8dd  mov     rax, cs:__security_cookie
0x18000c8e4  xor     rax, rsp
0x18000c8e7  mov     [rsp+498h+var_38], rax
0x18000c8ef  cmp     dword ptr [rcx+54h], 0
0x18000c8f3  mov     r14, r8
0x18000c8f6  mov     rbx, rdx
0x18000c8f9  mov     rdi, rcx
0x18000c8fc  jnz     loc_18000CB07
0x18000c902  mov     [rsp+498h+arg_18], rbp
0x18000c90a  lea     rbp, [rdi+48h]
0x18000c90e  mov     rcx, rbp
0x18000c911  mov     [rsp+498h+var_28], r15
0x18000c919  call    cs:__imp_?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ; CReaderWriterLock3AR::ReadOrWriteLock(void)
0x18000c920  nop     dword ptr [rax+rax+00h]
0x18000c925  movzx   edx, word ptr [rbx]
0x18000c928  movzx   r15d, al
0x18000c92c  mov     eax, 400Ch
0x18000c931  cmp     dx, ax
0x18000c934  jz      loc_18000CB60
0x18000c93a  movzx   ecx, dx
0x18000c93d  mov     eax, ecx
0x18000c93f  btr     eax, 0Eh
0x18000c943  cmp     eax, 8
0x18000c946  jz      loc_18000C9DC
0x18000c94c  xor     esi, esi
0x18000c94e  xor     eax, eax
0x18000c950  mov     dword ptr [rsp+498h+pvargDest], esi
0x18000c954  xorps   xmm0, xmm0
0x18000c957  mov     word ptr [rsp+498h+pvargDest+4], si
0x18000c95c  mov     word ptr [rsp+498h+pvargDest+16h], ax
0x18000c961  movups  xmmword ptr [rsp+498h+pvargDest+6], xmm0
0x18000c966  cmp     ecx, 3
0x18000c969  jnz     loc_18000CC16
0x18000c96f  movsxd  rcx, dword ptr [rbx+8]
0x18000c973  test    rcx, rcx
0x18000c976  js      loc_18000CC04
0x18000c97c  mov     rdx, [rdi+40h]
0x18000c980  mov     eax, [rdx+10h]
0x18000c983  cmp     rcx, rax
0x18000c986  jnb     loc_18000CD71
0x18000c98c  mov     rax, [rdx+8]
0x18000c990  mov     ebx, esi
0x18000c992  mov     rcx, [rax+rcx*8]
0x18000c996  mov     [r14], rcx
0x18000c999  movzx   edx, r15b
0x18000c99d  mov     rcx, rbp
0x18000c9a0  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z; CReaderWriterLock3AR::ReadOrWriteUnlock(bool)
0x18000c9a7  nop     dword ptr [rax+rax+00h]
0x18000c9ac  mov     r15, [rsp+498h+var_28]
0x18000c9b4  mov     eax, ebx
0x18000c9b6  mov     rbp, [rsp+498h+arg_18]
0x18000c9be  mov     rcx, [rsp+498h+var_38]
0x18000c9c6  xor     rcx, rsp; StackCookie
0x18000c9c9  call    __security_check_cookie
0x18000c9ce  add     rsp, 478h
0x18000c9d5  pop     r14
0x18000c9d7  pop     rdi
0x18000c9d8  pop     rsi
0x18000c9d9  pop     rbx
0x18000c9da  retn
0x18000c9dc  mov     rcx, [rbx+8]
0x18000c9e0  mov     eax, 4000h
0x18000c9e5  and     dx, ax
0x18000c9e8  jnz     loc_18000CC0E
0x18000c9ee  mov     rax, rcx
0x18000c9f1  test    rax, rax
0x18000c9f4  jz      loc_18000CC04
0x18000c9fa  mov     rdi, [rdi+40h]
0x18000c9fe  test    dx, dx
0x18000ca01  jnz     loc_18000CCB7
0x18000ca07  movzx   r9d, byte ptr [rdi+2Ch]; bool
0x18000ca0c  lea     r8, [rsp+498h+var_468]; unsigned __int8 **
0x18000ca11  xor     esi, esi
0x18000ca13  mov     rdx, rcx; lpSrcStr
0x18000ca16  lea     rcx, [rsp+498h+var_448]; this
0x18000ca1b  mov     [rsp+498h+var_48], rsi
0x18000ca23  mov     [rsp+498h+var_468], rsi
0x18000ca28  mov     [rsp+498h+var_478], sil; bool
0x18000ca2d  call    ?Create@CSortKey@@QEAAJQEAGPEAPEAE_N2@Z; CSortKey::Create(ushort * const,uchar * *,bool,bool)
0x18000ca32  mov     ebx, eax
0x18000ca34  test    eax, eax
0x18000ca36  js      loc_18000CC60
0x18000ca3c  mov     r11, [rsp+498h+var_468]
0x18000ca41  mov     rax, r11
0x18000ca44  test    r11, r11
0x18000ca47  jz      loc_18000CBC9
0x18000ca4d  movzx   ecx, byte ptr [r11]
0x18000ca51  mov     dword ptr [rsp+498h+var_468], esi
0x18000ca55  test    cl, cl
0x18000ca57  jnz     loc_18000CB72
0x18000ca5d  mov     r10d, dword ptr [rsp+498h+var_468]
0x18000ca62  xor     edx, edx
0x18000ca64  mov     eax, r10d
0x18000ca67  div     dword ptr [rdi+18h]
0x18000ca6a  mov     rax, [rdi+20h]
0x18000ca6e  mov     r8, [rax+rdx*8]
0x18000ca72  test    r8, r8
0x18000ca75  jz      loc_18000CC89
0x18000ca7b  test    r8, r8
0x18000ca7e  jz      loc_18000CC56
0x18000ca84  cmp     [r8], r10d
0x18000ca87  jz      short loc_18000CA8F
0x18000ca89  mov     r8, [r8+28h]
0x18000ca8d  jmp     short loc_18000CA7B
0x18000ca8f  test    r11, r11
0x18000ca92  jz      loc_18000CCBF
0x18000ca98  mov     rax, [r8+20h]
0x18000ca9c  test    rax, rax
0x18000ca9f  jz      loc_18000CCBF
0x18000caa5  mov     r9, r11
0x18000caa8  sub     r9, rax
0x18000caab  nop     dword ptr [rax+rax+00h]
0x18000cab0  movzx   edx, byte ptr [rax]
0x18000cab3  movzx   ecx, byte ptr [rax+r9]
0x18000cab8  sub     edx, ecx
0x18000caba  jnz     short loc_18000CAC3
0x18000cabc  inc     rax
0x18000cabf  test    ecx, ecx
0x18000cac1  jnz     short loc_18000CAB0
0x18000cac3  test    edx, edx
0x18000cac5  jnz     loc_18000CCBF
0x18000cacb  mov     rax, [r8+18h]
0x18000cacf  mov     ebx, esi
0x18000cad1  mov     [r14], rax
0x18000cad4  mov     rdx, [rsp+498h+var_48]
0x18000cadc  test    rdx, rdx
0x18000cadf  jz      short loc_18000CAF4
0x18000cae1  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000cae8  call    cs:__imp_MpHeapFree
0x18000caef  nop     dword ptr [rax+rax+00h]
0x18000caf4  cmp     ebx, 1
0x18000caf7  jnz     loc_18000C999
0x18000cafd  mov     ebx, 800A0CC1h
0x18000cb02  jmp     loc_18000C999
0x18000cb07  mov     rax, [rcx]
0x18000cb0a  xor     edx, edx
0x18000cb0c  mov     r8d, 1
0x18000cb12  mov     rax, [rax+80h]
0x18000cb19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb1e  mov     esi, eax
0x18000cb20  test    eax, eax
0x18000cb22  jns     loc_18000C902
0x18000cb28  test    byte ptr cs:_bidGblFlags, 2
0x18000cb2f  jz      loc_18000C9BE
0x18000cb35  mov     rcx, cs:off_18012A1B8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000cb3c  lea     r8, aCstdcollection_1; "<CStdCollection::LookupItem|ADO|ERR> 0x"...
0x18000cb43  mov     r9d, eax
0x18000cb46  mov     dword ptr [rsp+498h+var_478], 1C1h
0x18000cb4e  mov     edx, 70409h
0x18000cb53  call    _bidTraceW
0x18000cb58  mov     eax, esi
0x18000cb5a  jmp     loc_18000C9BE
0x18000cb60  mov     rbx, [rbx+8]
0x18000cb64  movzx   edx, word ptr [rbx]
0x18000cb67  cmp     dx, ax
0x18000cb6a  jnz     loc_18000C93A
0x18000cb70  jmp     short loc_18000CB60
0x18000cb72  movzx   r9d, byte ptr [rax+1]
0x18000cb77  inc     rax
0x18000cb7a  mov     word ptr [rsp+498h+var_468], cx
0x18000cb7f  mov     word ptr [rsp+498h+var_468+2], cx
0x18000cb84  test    r9b, r9b
0x18000cb87  jz      loc_18000CA5D
0x18000cb8d  mov     r8d, 1
0x18000cb93  nop     dword ptr [rax+00h]
0x18000cb97  nop     word ptr [rax+rax+00000000h]
0x18000cba0  movsxd  rcx, r8d
0x18000cba3  lea     rdx, [rsp+498h+var_468]
0x18000cba8  lea     rdx, [rdx+rcx*2]
0x18000cbac  xor     r8d, 1
0x18000cbb0  movzx   ecx, r9b
0x18000cbb4  lea     rax, [rax+1]
0x18000cbb8  add     [rdx], cx
0x18000cbbb  movzx   r9d, byte ptr [rax]
0x18000cbbf  test    r9b, r9b
0x18000cbc2  jnz     short loc_18000CBA0
0x18000cbc4  jmp     loc_18000CA5D
0x18000cbc9  mov     r10d, esi
0x18000cbcc  jmp     loc_18000CA62
0x18000cbd1  jz      loc_18000CCEA
0x18000cbd7  sub     ecx, 2
0x18000cbda  jz      loc_18000CCE0
0x18000cbe0  sub     ecx, 2
0x18000cbe3  jz      loc_18000CD03
0x18000cbe9  sub     ecx, 1
0x18000cbec  jz      loc_18000CD03
0x18000cbf2  sub     ecx, 0Bh
0x18000cbf5  jz      loc_18000CCD7
0x18000cbfb  cmp     ecx, 4
0x18000cbfe  jz      loc_18000CCCE
0x18000cc04  mov     ebx, 800A0CC1h
0x18000cc09  jmp     loc_18000C999
0x18000cc0e  mov     rax, [rcx]
0x18000cc11  jmp     loc_18000C9F1
0x18000cc16  cmp     ecx, 4002h
0x18000cc1c  jbe     short loc_18000CBD1
0x18000cc1e  sub     ecx, 4003h
0x18000cc24  jz      loc_18000CD65
0x18000cc2a  sub     ecx, 1
0x18000cc2d  jz      loc_18000CD03
0x18000cc33  sub     ecx, 1
0x18000cc36  jz      loc_18000CD03
0x18000cc3c  sub     ecx, 0Bh
0x18000cc3f  jz      loc_18000CCF7
0x18000cc45  cmp     ecx, 4
0x18000cc48  jnz     short loc_18000CC04
0x18000cc4a  mov     rax, [rbx+8]
0x18000cc4e  mov     rcx, [rax]
0x18000cc51  jmp     loc_18000C973
0x18000cc56  mov     ebx, 1
0x18000cc5b  jmp     loc_18000CAD4
0x18000cc60  mov     rdx, [rsp+498h+var_48]
0x18000cc68  test    rdx, rdx
0x18000cc6b  jz      loc_18000C999
0x18000cc71  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000cc78  call    cs:__imp_MpHeapFree
0x18000cc7f  nop     dword ptr [rax+rax+00h]
0x18000cc84  jmp     loc_18000C999
0x18000cc89  mov     rdx, [rsp+498h+var_48]
0x18000cc91  test    rdx, rdx
0x18000cc94  jz      loc_18000CC04
0x18000cc9a  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000cca1  call    cs:__imp_MpHeapFree
0x18000cca8  nop     dword ptr [rax+rax+00h]
0x18000ccad  mov     ebx, 800A0CC1h
0x18000ccb2  jmp     loc_18000C999
0x18000ccb7  mov     rcx, [rcx]
0x18000ccba  jmp     loc_18000CA07
0x18000ccbf  cmp     r11, [r8+20h]
0x18000ccc3  jz      loc_18000CACB
0x18000ccc9  jmp     loc_18000CA89
0x18000ccce  mov     rcx, [rbx+8]
0x18000ccd2  jmp     loc_18000C973
0x18000ccd7  movzx   ecx, byte ptr [rbx+8]
0x18000ccdb  jmp     loc_18000C973
0x18000cce0  movsx   rcx, word ptr [rbx+8]
0x18000cce5  jmp     loc_18000C973
0x18000ccea  mov     rax, [rbx+8]
0x18000ccee  movsx   rcx, word ptr [rax]
0x18000ccf2  jmp     loc_18000C973
0x18000ccf7  mov     rax, [rbx+8]
0x18000ccfb  movzx   ecx, byte ptr [rax]
0x18000ccfe  jmp     loc_18000C973
0x18000cd03  mov     r9d, 14h; vt
0x18000cd09  lea     rcx, [rsp+498h+pvargDest]; pvargDest
0x18000cd0e  xor     r8d, r8d; wFlags
0x18000cd11  mov     rdx, rbx; pvarSrc
0x18000cd14  call    cs:__imp_VariantChangeType
0x18000cd1b  nop     dword ptr [rax+rax+00h]
0x18000cd20  mov     ebx, eax
0x18000cd22  test    eax, eax
0x18000cd24  jns     short loc_18000CD5B
0x18000cd26  test    byte ptr cs:_bidGblFlags, 2
0x18000cd2d  jz      loc_18000C999
0x18000cd33  mov     rcx, cs:off_18012A1B8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000cd3a  lea     r8, aCstdcollection_1; "<CStdCollection::LookupItem|ADO|ERR> 0x"...
0x18000cd41  mov     r9d, eax
0x18000cd44  mov     dword ptr [rsp+498h+var_478], 21Bh
0x18000cd4c  mov     edx, 86C09h
0x18000cd51  call    _bidTraceW
0x18000cd56  jmp     loc_18000C999
0x18000cd5b  mov     rcx, qword ptr [rsp+498h+pvargDest+8]
0x18000cd60  jmp     loc_18000C973
0x18000cd65  mov     rax, [rbx+8]
0x18000cd69  movsxd  rcx, dword ptr [rax]
0x18000cd6c  jmp     loc_18000C973
0x18000cd71  mov     [r14], rsi
0x18000cd74  jmp     loc_18000CC04
```
