# CQuery::GetProperty(_GUID const &,ulong,tagVARIANT *)

- ea: `0x180084380`
- end: `0x180084560`
- name: `?GetProperty@CQuery@@UEAAJAEBU_GUID@@KPEAUtagVARIANT@@@Z`
- size: `480`
- prototype: `int(CQuery *__hidden this, const struct _GUID *, unsigned int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180049070`
- `0x18006a22c`
- `0x180084380`
- `0x1800c8f34`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180084430`
- `OLEAUT32!__imp_VariantInit` at `0x180084430`
- `OLEAUT32!__imp_VariantCopy` at `0x1800844d2`
- `OLEAUT32!__imp_VariantCopy` at `0x1800844d2`

## pseudocode

```c
__int64 __fastcall CQuery::GetProperty(CQuery *this, const struct _GUID *a2, int a3, struct tagVARIANT *a4)
{
  HRESULT v7; // ebx
  unsigned int BidObjectID; // eax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int128 v11; // xmm0
  __int64 v12; // rcx
  __int64 v14; // [rsp+20h] [rbp-58h]
  int v15; // [rsp+28h] [rbp-50h]
  __int64 v16; // [rsp+30h] [rbp-48h] BYREF
  __int64 v17; // [rsp+38h] [rbp-40h] BYREF
  struct tagDBPROPSET *v18; // [rsp+40h] [rbp-38h] BYREF
  _OWORD v19[2]; // [rsp+48h] [rbp-30h] BYREF

  LODWORD(v17) = a3;
  v18 = 0;
  LODWORD(v16) = 0;
  memset(v19, 0, sizeof(v19));
  if ( a4 )
  {
    VariantInit(a4);
    v11 = (__int128)*a2;
    v12 = *((_QWORD *)this + 12);
    DWORD2(v19[0]) = 1;
    *(_QWORD *)&v19[0] = &v17;
    *(_OWORD *)((char *)v19 + 12) = v11;
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, _OWORD *, __int64 *, struct tagDBPROPSET **))(*(_QWORD *)v12 + 24LL))(
           v12,
           1,
           v19,
           &v16,
           &v18);
    if ( v7 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_18;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CQuery *)((char *)this + 64)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CQuery *)((char *)this + 64));
        v9 = 4969481;
        v15 = 4853;
        goto LABEL_5;
      }
      LODWORD(v14) = 4853;
      v10 = 4969481;
LABEL_17:
      bidTraceW(
        off_18012A1E0[0],
        v10,
        L"<CQuery::GetProperty|ADO|ERR> 0x%08x{HRESULT} line %d\n",
        (unsigned int)v7,
        v14);
      goto LABEL_18;
    }
    v7 = VariantCopy(a4, &v18->rgProperties->vValue);
    if ( v7 < 0 && (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CQuery *)((char *)this + 64)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CQuery *)((char *)this + 64));
        v9 = 4973577;
        v15 = 4857;
        goto LABEL_5;
      }
      LODWORD(v14) = 4857;
      v10 = 4973577;
      goto LABEL_17;
    }
  }
  else
  {
    v7 = -2146825287;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CQuery *)((char *)this + 64)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CQuery *)((char *)this + 64));
        v9 = 4956169;
        v15 = 4840;
LABEL_5:
        LODWORD(v14) = v7;
        bidTraceW(
          off_18012A1E0[0],
          v9,
          L"<CQuery::GetProperty|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          BidObjectID,
          v14,
          v15,
          v16,
          v17);
        goto LABEL_18;
      }
      LODWORD(v14) = 4840;
      v10 = 4956169;
      goto LABEL_17;
    }
  }
LABEL_18:
  FreeDbPropSet(v16, v18, 1);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180084380  push    rbp
0x180084382  push    rbx
0x180084383  push    rsi
0x180084384  push    rdi
0x180084385  mov     rbp, rsp
0x180084388  sub     rsp, 78h
0x18008438c  mov     rax, cs:__security_cookie
0x180084393  xor     rax, rsp
0x180084396  mov     [rbp+var_10], rax
0x18008439a  mov     dword ptr [rbp+var_40], r8d
0x18008439e  xorps   xmm0, xmm0
0x1800843a1  mov     [rbp+var_38], 0
0x1800843a9  mov     rsi, r9
0x1800843ac  mov     dword ptr [rbp+var_48], 0
0x1800843b3  mov     rbx, rdx
0x1800843b6  mov     rdi, rcx
0x1800843b9  movups  [rbp+var_30], xmm0
0x1800843bd  movups  [rbp+var_20], xmm0
0x1800843c1  test    r9, r9
0x1800843c4  jnz     short loc_18008442D
0x1800843c6  test    byte ptr cs:_bidGblFlags, 2
0x1800843cd  mov     ebx, 800A0BB9h
0x1800843d2  jz      loc_180084539
0x1800843d8  add     rcx, 40h ; '@'; this
0x1800843dc  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800843e1  cmp     eax, 0FFFFFFFFh
0x1800843e4  jz      short loc_18008441B
0x1800843e6  lea     rcx, [rdi+40h]; this
0x1800843ea  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800843ef  mov     edx, 4BA009h
0x1800843f4  mov     [rsp+78h+var_50], 12E8h
0x1800843fc  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180084403  lea     r8, aCqueryGetprope; "<CQuery::GetProperty|ADO|ERR> %u#,0x%08"...
0x18008440a  mov     r9d, eax
0x18008440d  mov     dword ptr [rsp+78h+var_58], ebx
0x180084411  call    _bidTraceW
0x180084416  jmp     loc_180084539
0x18008441b  mov     dword ptr [rsp+78h+var_58], 12E8h
0x180084423  mov     edx, 4BA009h
0x180084428  jmp     loc_180084523
0x18008442d  mov     rcx, rsi; pvarg
0x180084430  call    cs:__imp_VariantInit
0x180084437  nop     dword ptr [rax+rax+00h]
0x18008443c  movups  xmm0, xmmword ptr [rbx]
0x18008443f  mov     rcx, [rdi+60h]
0x180084443  lea     rdx, [rbp+var_38]
0x180084447  lea     rax, [rbp+var_40]
0x18008444b  mov     dword ptr [rbp+var_30+8], 1
0x180084452  mov     qword ptr [rbp+var_30], rax
0x180084456  lea     r9, [rbp+var_48]
0x18008445a  movdqu  [rbp+var_30+0Ch], xmm0
0x18008445f  mov     rax, [rcx]
0x180084462  lea     r8, [rbp+var_30]
0x180084466  mov     [rsp+78h+var_58], rdx
0x18008446b  mov     edx, 1
0x180084470  mov     rax, [rax+18h]
0x180084474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084479  mov     ebx, eax
0x18008447b  test    eax, eax
0x18008447d  jns     short loc_1800844C4
0x18008447f  test    byte ptr cs:_bidGblFlags, 2
0x180084486  jz      loc_180084539
0x18008448c  lea     rcx, [rdi+40h]; this
0x180084490  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180084495  cmp     eax, 0FFFFFFFFh
0x180084498  jz      short loc_1800844B5
0x18008449a  lea     rcx, [rdi+40h]; this
0x18008449e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800844a3  mov     edx, 4BD409h
0x1800844a8  mov     [rsp+78h+var_50], 12F5h
0x1800844b0  jmp     loc_1800843FC
0x1800844b5  mov     dword ptr [rsp+78h+var_58], 12F5h
0x1800844bd  mov     edx, 4BD409h
0x1800844c2  jmp     short loc_180084523
0x1800844c4  mov     rax, [rbp+var_38]
0x1800844c8  mov     rcx, rsi; pvargDest
0x1800844cb  mov     rdx, [rax]
0x1800844ce  add     rdx, 30h ; '0'; pvargSrc
0x1800844d2  call    cs:__imp_VariantCopy
0x1800844d9  nop     dword ptr [rax+rax+00h]
0x1800844de  mov     ebx, eax
0x1800844e0  test    eax, eax
0x1800844e2  jns     short loc_180084539
0x1800844e4  test    byte ptr cs:_bidGblFlags, 2
0x1800844eb  jz      short loc_180084539
0x1800844ed  lea     rcx, [rdi+40h]; this
0x1800844f1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800844f6  cmp     eax, 0FFFFFFFFh
0x1800844f9  jz      short loc_180084516
0x1800844fb  lea     rcx, [rdi+40h]; this
0x1800844ff  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180084504  mov     edx, 4BE409h
0x180084509  mov     [rsp+78h+var_50], 12F9h
0x180084511  jmp     loc_1800843FC
0x180084516  mov     dword ptr [rsp+78h+var_58], 12F9h
0x18008451e  mov     edx, 4BE409h
0x180084523  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008452a  lea     r8, aCqueryGetprope_0; "<CQuery::GetProperty|ADO|ERR> 0x%08x{HR"...
0x180084531  mov     r9d, ebx
0x180084534  call    _bidTraceW
0x180084539  mov     rdx, [rbp+var_38]; struct tagDBPROPSET *
0x18008453d  mov     r8b, 1; bool
0x180084540  mov     ecx, dword ptr [rbp+var_48]; unsigned int
0x180084543  call    ?FreeDbPropSet@@YAXKPEAUtagDBPROPSET@@_N@Z; FreeDbPropSet(ulong,tagDBPROPSET *,bool)
0x180084548  mov     eax, ebx
0x18008454a  mov     rcx, [rbp+var_10]
0x18008454e  xor     rcx, rsp; StackCookie
0x180084551  call    __security_check_cookie
0x180084556  add     rsp, 78h
0x18008455a  pop     rdi
0x18008455b  pop     rsi
0x18008455c  pop     rbx
0x18008455d  pop     rbp
0x18008455e  retn
```
