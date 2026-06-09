# CErrors::LookupItem(tagVARIANT &,CStdComObjectRoot * *)

- ea: `0x18001c470`
- end: `0x18001c889`
- name: `?LookupItem@CErrors@@UEAAJAEAUtagVARIANT@@PEAPEAVCStdComObjectRoot@@@Z`
- size: `1049`
- prototype: `__int64 __fastcall(CErrors *__hidden this, struct tagVARIANT *, struct CStdComObjectRoot **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000bbc0`
- `0x18001a750`
- `0x18001c470`
- `0x18001c890`
- `0x180020fc0`
- `0x180042a04`
- `0x180057b30`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001c55c`
- `KERNEL32!GetCurrentThreadId` at `0x18001c55c`
- `KERNEL32!TlsSetValue` at `0x18001c4fb`
- `KERNEL32!TlsSetValue` at `0x18001c851`
- `KERNEL32!TlsSetValue` at `0x18001c4fb`
- `KERNEL32!TlsSetValue` at `0x18001c851`
- `KERNEL32!TlsGetValue` at `0x18001c4b7`
- `KERNEL32!TlsGetValue` at `0x18001c4b7`
- `OLEAUT32!__imp_VariantInit` at `0x18001c52f`
- `OLEAUT32!__imp_VariantInit` at `0x18001c6d8`
- `OLEAUT32!__imp_VariantInit` at `0x18001c52f`
- `OLEAUT32!__imp_VariantInit` at `0x18001c6d8`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001c6f2`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001c6f2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001c81b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001c81b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CErrors::LookupItem(unsigned __int64 this, struct tagVARIANT *a2, struct CStdComObjectRoot **a3)
{
  _DWORD *Value; // rax
  __int64 v6; // r9
  __int64 v7; // rdx
  unsigned int v8; // r12d
  VARTYPE vt; // dx
  LONGLONG v10; // rcx
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rax
  char v12; // r14
  __int16 iVal; // cx
  int v14; // r9d
  unsigned int i; // edx
  __int64 v16; // rax
  struct CStdComObjectRoot *v17; // r8
  __int64 v18; // rax
  unsigned int v19; // ebx
  _DWORD *v21; // rax
  IErrorInfo *v22; // rdx
  VARIANTARG pvargDest; // [rsp+20h] [rbp-59h] BYREF
  void **v25; // [rsp+38h] [rbp-41h] BYREF
  __int64 v26; // [rsp+40h] [rbp-39h]
  VARIANTARG pvarg; // [rsp+48h] [rbp-31h] BYREF
  __int64 v28; // [rsp+60h] [rbp-19h]
  _DWORD *TlsValue; // [rsp+68h] [rbp-11h] BYREF
  int v30; // [rsp+70h] [rbp-9h]
  __int64 v31; // [rsp+78h] [rbp-1h]
  int v32; // [rsp+80h] [rbp+7h]
  __int16 v33; // [rsp+84h] [rbp+Bh]
  char v34; // [rsp+86h] [rbp+Dh]
  unsigned __int64 v35; // [rsp+88h] [rbp+Fh]
  int v36; // [rsp+90h] [rbp+17h]
  int v37; // [rsp+94h] [rbp+1Bh]
  int v38; // [rsp+E0h] [rbp+67h] BYREF
  DWORD CurrentThreadId; // [rsp+F8h] [rbp+7Fh]

  v35 = this & -(__int64)(this != 24);
  v37 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v36 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v30 = 1;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v25 = &CVar::`vftable';
  LOBYTE(v26) = 4;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.vt = 10;
  pvarg.lVal = -2147352572;
  v28 = 0;
  CVar::operator=((CVar *)&v25);
  CurrentThreadId = GetCurrentThreadId();
  (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)(this - 8) + 40LL))(this - 8);
  if ( (v26 & 4) == 0 )
  {
    v36 = -2147024882;
    if ( (unsigned int)CContext::PushError((CContext *)&TlsValue) )
    {
      if ( v36 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_52;
        v6 = 7016;
        v7 = 7184393;
        goto LABEL_9;
      }
    }
  }
  v36 = CStdCollection::Refresh((CCollectionList **)this, 0, 1u);
  if ( v36 < 0 )
  {
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) != 0 )
    {
      v6 = 7019;
      v7 = 7187465;
LABEL_9:
      bidTraceW(
        off_18012A1C0[0],
        v7,
        L"<CErrors::LookupItem|ADO|ERR>  line %d\n",
        v6,
        *(_OWORD *)&pvargDest.vt,
        pvargDest.pRecInfo,
        v25,
        v26);
      goto LABEL_52;
    }
    goto LABEL_52;
  }
  v8 = *(_DWORD *)(*(_QWORD *)(this + 64) + 16LL);
  *a3 = 0;
  vt = pvarg.vt;
  if ( pvarg.vt > 1u && pvarg.vt != 10 )
  {
LABEL_19:
    memset(&pvargDest, 0, sizeof(pvargDest));
    if ( (vt & 0xBFFF) == 2 )
      goto LABEL_37;
    if ( (vt & 0xBFFF) == 8 )
    {
      if ( (*(_BYTE *)(v28 + 8) & 4) != 0 )
        v10 = *(_QWORD *)v28;
      else
        v10 = 0;
    }
    else
    {
      if ( (vt & 0x2000) == 0 )
        goto LABEL_29;
      v10 = *(_QWORD *)(v28 + 16);
    }
    p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarg.llVal;
    if ( (vt & 0x4000) != 0 )
      p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)pvarg.llVal;
    p_llVal->llVal = v10;
LABEL_29:
    VariantInit(&pvargDest);
    if ( VariantChangeType(&pvargDest, &pvarg, 0, 2u) >= 0 )
    {
      v12 = v26;
      LOBYTE(v26) = v26 & 0xFE;
      CVar::operator=((CVar *)&v25);
      if ( (v26 & 4) != 0 )
      {
        LOBYTE(v26) = v12;
LABEL_36:
        vt = pvarg.vt;
LABEL_37:
        if ( (vt & 0x4000) != 0 )
          iVal = *pvarg.bstrVal;
        else
          iVal = pvarg.iVal;
        v14 = iVal;
        for ( i = 0; i < v8; ++i )
        {
          v16 = *(_QWORD *)(this + 64);
          if ( i >= *(_DWORD *)(v16 + 16) )
            break;
          v17 = *(struct CStdComObjectRoot **)(*(_QWORD *)(v16 + 8) + 8LL * i);
          v18 = (__int64)v17 + 140;
          if ( !v17 )
            v18 = 156;
          if ( CurrentThreadId == *(_DWORD *)v18 )
          {
            if ( !v14 )
            {
              *a3 = v17;
              break;
            }
            --v14;
          }
        }
        if ( !*a3 )
          CContext::LookupFailed((CContext *)&TlsValue, 0);
        goto LABEL_52;
      }
    }
    else
    {
      LOBYTE(v26) = v26 & 0xFB;
    }
    v38 = -2146824867;
    if ( (unsigned int)CContext::FailedPushWarning((CContext *)&TlsValue, &v38) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v6 = 7030;
        v7 = 7198729;
        goto LABEL_9;
      }
      goto LABEL_52;
    }
    goto LABEL_36;
  }
  v38 = -2146825023;
  if ( !(unsigned int)CContext::FailedPushWarning((CContext *)&TlsValue, &v38) )
  {
    vt = pvarg.vt;
    goto LABEL_19;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    v6 = 7027;
    v7 = 7195657;
    goto LABEL_9;
  }
LABEL_52:
  (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)(this - 8) + 48LL))(this - 8);
  v19 = v36;
  v25 = &CVar::`vftable';
  CVar::Clear((CVar *)&v25);
  if ( TlsValue[2]-- == 1 )
  {
    v21 = TlsValue;
    v22 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v22 )
    {
      SetErrorInfo(0, v22);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v21 = TlsValue;
    }
    if ( *((_BYTE *)v21 + 30) )
    {
      *((_QWORD *)v21 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v19;
}

```

## disassembly

```asm
0x18001c470  mov     [rsp-8+arg_8], rbx
0x18001c475  push    rbp
0x18001c476  push    rsi
0x18001c477  push    rdi
0x18001c478  push    r12
0x18001c47a  push    r13
0x18001c47c  push    r14
0x18001c47e  push    r15
0x18001c480  lea     rbp, [rsp-27h]
0x18001c485  sub     rsp, 0A0h
0x18001c48c  mov     r15, r8
0x18001c48f  mov     rbx, rdx
0x18001c492  mov     rsi, rcx
0x18001c495  lea     rax, [rcx-18h]
0x18001c499  neg     rax
0x18001c49c  sbb     r9, r9
0x18001c49f  and     r9, rcx
0x18001c4a2  mov     [rbp+57h+var_48], r9
0x18001c4a6  xor     r14d, r14d
0x18001c4a9  mov     [rbp+57h+var_3C], r14d
0x18001c4ad  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18001c4b4  mov     ecx, [rcx+14h]; dwTlsIndex
0x18001c4b7  call    cs:__imp_TlsGetValue
0x18001c4be  nop     dword ptr [rax+rax+00h]
0x18001c4c3  mov     [rbp+57h+TlsValue], rax
0x18001c4c7  mov     [rbp+57h+var_40], r14d
0x18001c4cb  lea     edi, [r14+1]
0x18001c4cf  test    rax, rax
0x18001c4d2  jz      short loc_18001C4D9
0x18001c4d4  add     [rax+8], edi
0x18001c4d7  jmp     short loc_18001C50F
0x18001c4d9  mov     [rbp+57h+var_60], edi
0x18001c4dc  mov     [rbp+57h+var_58], r14
0x18001c4e0  mov     [rbp+57h+var_50], r14d
0x18001c4e4  mov     [rbp+57h+var_4C], r14w
0x18001c4e9  mov     [rbp+57h+var_4A], r14b
0x18001c4ed  lea     rdx, [rbp+57h+TlsValue]; lpTlsValue
0x18001c4f1  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18001c4f8  mov     ecx, [rcx+14h]; dwTlsIndex
0x18001c4fb  call    cs:__imp_TlsSetValue
0x18001c502  nop     dword ptr [rax+rax+00h]
0x18001c507  lea     rax, [rbp+57h+TlsValue]
0x18001c50b  mov     [rbp+57h+TlsValue], rax
0x18001c50f  lea     rax, ??_7CVar@@6B@; const CVar::`vftable'
0x18001c516  mov     [rbp+57h+var_98], rax
0x18001c51a  mov     byte ptr [rbp+57h+var_90], 4
0x18001c51e  xorps   xmm0, xmm0
0x18001c521  xor     eax, eax
0x18001c523  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001c527  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001c52b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001c52f  call    cs:__imp_VariantInit
0x18001c536  nop     dword ptr [rax+rax+00h]
0x18001c53b  mov     eax, 0Ah
0x18001c540  mov     word ptr [rbp+57h+pvarg], ax
0x18001c544  mov     dword ptr [rbp+57h+pvarg+8], 80020004h
0x18001c54b  mov     [rbp+57h+var_70], r14
0x18001c54f  mov     rdx, rbx
0x18001c552  lea     rcx, [rbp+57h+var_98]; this
0x18001c556  call    ??4CVar@@QEAAAEBV0@AEBUtagVARIANT@@@Z; CVar::operator=(tagVARIANT const &)
0x18001c55b  nop
0x18001c55c  call    cs:__imp_GetCurrentThreadId
0x18001c563  nop     dword ptr [rax+rax+00h]
0x18001c568  mov     [rbp+57h+arg_18], eax
0x18001c56b  lea     r13, [rsi-8]
0x18001c56f  mov     rcx, [r13+0]
0x18001c573  mov     rax, [rcx+28h]
0x18001c577  mov     rcx, r13
0x18001c57a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c57f  test    byte ptr [rbp+57h+var_90], 4
0x18001c583  jnz     short loc_18001C5D3
0x18001c585  mov     [rbp+57h+var_40], 8007000Eh
0x18001c58c  lea     rcx, [rbp+57h+TlsValue]; this
0x18001c590  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18001c595  test    eax, eax
0x18001c597  jz      short loc_18001C5D3
0x18001c599  cmp     [rbp+57h+var_40], r14d
0x18001c59d  jz      short loc_18001C5D3
0x18001c59f  mov     ebx, 2
0x18001c5a4  test    byte ptr cs:_bidGblFlags, bl
0x18001c5aa  jz      loc_18001C7DA
0x18001c5b0  mov     r9d, 1B68h
0x18001c5b6  mov     edx, 6DA009h
0x18001c5bb  lea     r8, aCerrorsLookupi; "<CErrors::LookupItem|ADO|ERR>  line %d"...
0x18001c5c2  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001c5c9  call    _bidTraceW
0x18001c5ce  jmp     loc_18001C7DA
0x18001c5d3  mov     r8d, edi; __int16
0x18001c5d6  xor     edx, edx; void *
0x18001c5d8  mov     rcx, rsi; this
0x18001c5db  call    ?Refresh@CStdCollection@@UEAAJPEAXF@Z; CStdCollection::Refresh(void *,short)
0x18001c5e0  mov     [rbp+57h+var_40], eax
0x18001c5e3  test    eax, eax
0x18001c5e5  jns     short loc_18001C60E
0x18001c5e7  lea     rcx, [rbp+57h+TlsValue]; this
0x18001c5eb  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18001c5f0  mov     ebx, 2
0x18001c5f5  test    byte ptr cs:_bidGblFlags, bl
0x18001c5fb  jz      loc_18001C7DA
0x18001c601  mov     r9d, 1B6Bh
0x18001c607  mov     edx, 6DAC09h
0x18001c60c  jmp     short loc_18001C5BB
0x18001c60e  mov     rax, [rsi+40h]
0x18001c612  mov     r12d, [rax+10h]
0x18001c616  mov     [r15], r14
0x18001c619  movzx   edx, word ptr [rbp+57h+pvarg]
0x18001c61d  cmp     dx, di
0x18001c620  jbe     short loc_18001C62C
0x18001c622  mov     eax, 0Ah
0x18001c627  cmp     dx, ax
0x18001c62a  jnz     short loc_18001C669
0x18001c62c  mov     [rbp+57h+arg_0], 800A0CC1h
0x18001c633  lea     rdx, [rbp+57h+arg_0]; int *
0x18001c637  lea     rcx, [rbp+57h+TlsValue]; this
0x18001c63b  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x18001c640  test    eax, eax
0x18001c642  jz      short loc_18001C665
0x18001c644  mov     ebx, 2
0x18001c649  test    byte ptr cs:_bidGblFlags, bl
0x18001c64f  jz      loc_18001C7DA
0x18001c655  mov     r9d, 1B73h
0x18001c65b  mov     edx, 6DCC09h
0x18001c660  jmp     loc_18001C5BB
0x18001c665  movzx   edx, word ptr [rbp+57h+pvarg]
0x18001c669  xorps   xmm0, xmm0
0x18001c66c  xor     eax, eax
0x18001c66e  movups  xmmword ptr [rbp+57h+pvargDest], xmm0
0x18001c672  mov     qword ptr [rbp+57h+pvargDest+10h], rax
0x18001c676  movzx   eax, dx
0x18001c679  mov     ecx, 0BFFFh
0x18001c67e  and     ax, cx
0x18001c681  mov     ebx, 2
0x18001c686  mov     r8d, 4000h
0x18001c68c  cmp     ax, bx
0x18001c68f  jz      loc_18001C76F
0x18001c695  movzx   eax, dx
0x18001c698  btr     eax, 0Eh
0x18001c69c  cmp     eax, 8
0x18001c69f  jnz     short loc_18001C6B5
0x18001c6a1  mov     rax, [rbp+57h+var_70]
0x18001c6a5  test    byte ptr [rax+8], 4
0x18001c6a9  jz      short loc_18001C6B0
0x18001c6ab  mov     rcx, [rax]
0x18001c6ae  jmp     short loc_18001C6C4
0x18001c6b0  mov     rcx, r14
0x18001c6b3  jmp     short loc_18001C6C4
0x18001c6b5  bt      dx, 0Dh
0x18001c6ba  jnb     short loc_18001C6D4
0x18001c6bc  mov     rax, [rbp+57h+var_70]
0x18001c6c0  mov     rcx, [rax+10h]
0x18001c6c4  lea     rax, [rbp+57h+pvarg+8]
0x18001c6c8  test    r8w, dx
0x18001c6cc  cmovnz  rax, qword ptr [rbp+57h+pvarg+8]
0x18001c6d1  mov     [rax], rcx
0x18001c6d4  lea     rcx, [rbp+57h+pvargDest]; pvarg
0x18001c6d8  call    cs:__imp_VariantInit
0x18001c6df  nop     dword ptr [rax+rax+00h]
0x18001c6e4  mov     r9d, ebx; vt
0x18001c6e7  xor     r8d, r8d; wFlags
0x18001c6ea  lea     rdx, [rbp+57h+pvarg]; pvarSrc
0x18001c6ee  lea     rcx, [rbp+57h+pvargDest]; pvargDest
0x18001c6f2  call    cs:__imp_VariantChangeType
0x18001c6f9  nop     dword ptr [rax+rax+00h]
0x18001c6fe  test    eax, eax
0x18001c700  jns     short loc_18001C708
0x18001c702  and     byte ptr [rbp+57h+var_90], 0FBh
0x18001c706  jmp     short loc_18001C72A
0x18001c708  mov     r14b, byte ptr [rbp+57h+var_90]
0x18001c70c  mov     al, r14b
0x18001c70f  and     al, 0FEh
0x18001c711  mov     byte ptr [rbp+57h+var_90], al
0x18001c714  lea     rdx, [rbp+57h+pvargDest]
0x18001c718  lea     rcx, [rbp+57h+var_98]; this
0x18001c71c  call    ??4CVar@@QEAAAEBV0@AEBUtagVARIANT@@@Z; CVar::operator=(tagVARIANT const &)
0x18001c721  test    byte ptr [rbp+57h+var_90], 4
0x18001c725  jnz     short loc_18001C75E
0x18001c727  xor     r14d, r14d
0x18001c72a  mov     [rbp+57h+arg_0], 800A0D5Dh
0x18001c731  lea     rdx, [rbp+57h+arg_0]; int *
0x18001c735  lea     rcx, [rbp+57h+TlsValue]; this
0x18001c739  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x18001c73e  test    eax, eax
0x18001c740  jz      short loc_18001C765
0x18001c742  test    byte ptr cs:_bidGblFlags, bl
0x18001c748  jz      loc_18001C7DA
0x18001c74e  mov     r9d, 1B76h
0x18001c754  mov     edx, 6DD809h
0x18001c759  jmp     loc_18001C5BB
0x18001c75e  mov     byte ptr [rbp+57h+var_90], r14b
0x18001c762  xor     r14d, r14d
0x18001c765  mov     r8d, 4000h
0x18001c76b  movzx   edx, word ptr [rbp+57h+pvarg]
0x18001c76f  test    r8w, dx
0x18001c773  jz      short loc_18001C77E
0x18001c775  mov     rax, qword ptr [rbp+57h+pvarg+8]
0x18001c779  movzx   ecx, word ptr [rax]
0x18001c77c  jmp     short loc_18001C782
0x18001c77e  movzx   ecx, word ptr [rbp+57h+pvarg+8]
0x18001c782  movsx   r9d, cx
0x18001c786  mov     edx, r14d
0x18001c789  mov     r10d, [rbp+57h+arg_18]
0x18001c78d  cmp     edx, r12d
0x18001c790  jnb     short loc_18001C7CA
0x18001c792  mov     rax, [rsi+40h]
0x18001c796  cmp     edx, [rax+10h]
0x18001c799  jnb     short loc_18001C7CA
0x18001c79b  mov     ecx, edx
0x18001c79d  mov     rax, [rax+8]
0x18001c7a1  mov     r8, [rax+rcx*8]
0x18001c7a5  test    r8, r8
0x18001c7a8  lea     rax, [r8+8Ch]
0x18001c7af  jnz     short loc_18001C7B6
0x18001c7b1  mov     eax, 9Ch
0x18001c7b6  cmp     r10d, [rax]
0x18001c7b9  jnz     short loc_18001C7C3
0x18001c7bb  test    r9d, r9d
0x18001c7be  jz      short loc_18001C7C7
0x18001c7c0  dec     r9d
0x18001c7c3  add     edx, edi
0x18001c7c5  jmp     short loc_18001C78D
0x18001c7c7  mov     [r15], r8
0x18001c7ca  cmp     [r15], r14
0x18001c7cd  jnz     short loc_18001C7DA
0x18001c7cf  xor     edx, edx; int
0x18001c7d1  lea     rcx, [rbp+57h+TlsValue]; this
0x18001c7d5  call    ?LookupFailed@CContext@@QEAAHH@Z; CContext::LookupFailed(int)
0x18001c7da  mov     rax, [r13+0]
0x18001c7de  mov     rcx, r13
0x18001c7e1  mov     rax, [rax+30h]
0x18001c7e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7ea  mov     ebx, [rbp+57h+var_40]
0x18001c7ed  lea     rax, ??_7CVar@@6B@; const CVar::`vftable'
0x18001c7f4  mov     [rbp+57h+var_98], rax
0x18001c7f8  lea     rcx, [rbp+57h+var_98]; this
0x18001c7fc  call    ?Clear@CVar@@QEAAXXZ; CVar::Clear(void)
0x18001c801  nop
0x18001c802  mov     rax, [rbp+57h+TlsValue]
0x18001c806  add     dword ptr [rax+8], 0FFFFFFFFh
0x18001c80a  jnz     short loc_18001C86B
0x18001c80c  mov     rax, [rbp+57h+TlsValue]
0x18001c810  mov     rdx, [rax+10h]; perrinfo
0x18001c814  test    rdx, rdx
0x18001c817  jz      short loc_18001C83F
0x18001c819  xor     ecx, ecx; dwReserved
0x18001c81b  call    cs:__imp_SetErrorInfo
0x18001c822  nop     dword ptr [rax+rax+00h]
0x18001c827  mov     rax, [rbp+57h+TlsValue]
0x18001c82b  mov     rcx, [rax+10h]
0x18001c82f  mov     rax, [rcx]
0x18001c832  mov     rax, [rax+10h]
0x18001c836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c83b  mov     rax, [rbp+57h+TlsValue]
0x18001c83f  cmp     [rax+1Eh], r14b
0x18001c843  jnz     short loc_18001C85F
0x18001c845  xor     edx, edx; lpTlsValue
0x18001c847  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18001c84e  mov     ecx, [rcx+14h]; dwTlsIndex
0x18001c851  call    cs:__imp_TlsSetValue
0x18001c858  nop     dword ptr [rax+rax+00h]
0x18001c85d  jmp     short loc_18001C86B
0x18001c85f  mov     [rax+10h], r14
0x18001c863  mov     rcx, [rbp+57h+TlsValue]
0x18001c867  mov     [rcx+18h], r14d
0x18001c86b  mov     eax, ebx
0x18001c86d  mov     rbx, [rsp+0D0h+arg_8]
0x18001c875  add     rsp, 0A0h
0x18001c87c  pop     r15
0x18001c87e  pop     r14
0x18001c880  pop     r13
0x18001c882  pop     r12
0x18001c884  pop     rdi
0x18001c885  pop     rsi
0x18001c886  pop     rbp
0x18001c887  retn
```
