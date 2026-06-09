# CQuery::IsRequiredPropInError(ulong,tagDBPROPSET *)

- ea: `0x180052830`
- end: `0x180052ab7`
- name: `?IsRequiredPropInError@CQuery@@QEAAJKPEAUtagDBPROPSET@@@Z`
- size: `647`
- prototype: `__int64 __fastcall(CQuery *__hidden this, unsigned int, struct tagDBPROPSET *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18005275c`

## callees

- `0x180052830`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180052a74`
- `ole32!CoTaskMemFree` at `0x180052a8a`
- `ole32!CoTaskMemFree` at `0x180052a74`
- `ole32!CoTaskMemFree` at `0x180052a8a`
- `OLEAUT32!__imp_VariantClear` at `0x180052a5a`
- `OLEAUT32!__imp_VariantClear` at `0x180052a5a`

## pseudocode

```c
__int64 __fastcall CQuery::IsRequiredPropInError(CQuery *this, unsigned int a2, struct tagDBPROPSET *a3)
{
  unsigned int v3; // ebx
  __int64 *v5; // rcx
  __int64 v6; // rax
  int v7; // r12d
  unsigned int BidObjectID; // eax
  struct tagDBPROPSET *v9; // rcx
  unsigned int v10; // edx
  __int64 v11; // r8
  __int64 v12; // r11
  __int64 v13; // rsi
  unsigned int v14; // r9d
  __int64 v15; // r10
  __int64 v16; // rbx
  __int64 v17; // r9
  unsigned int v18; // r14d
  char *v19; // rdi
  unsigned int v20; // esi
  __int64 v21; // rbx
  __int64 v22; // r15
  __int64 v24; // [rsp+20h] [rbp-58h]
  int v25; // [rsp+28h] [rbp-50h]
  unsigned int v26; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v27; // [rsp+34h] [rbp-44h]
  struct tagDBPROPSET *v28; // [rsp+38h] [rbp-40h]
  LPVOID pv; // [rsp+40h] [rbp-38h] BYREF
  __int64 v30; // [rsp+48h] [rbp-30h] BYREF
  int v31; // [rsp+50h] [rbp-28h]
  GUID v32; // [rsp+54h] [rbp-24h]
  int v33; // [rsp+64h] [rbp-14h]

  v3 = a2;
  v27 = a2;
  v33 = 0;
  pv = 0;
  v5 = (__int64 *)*((_QWORD *)this + 12);
  v26 = 0;
  v31 = 0;
  v30 = 0;
  v32 = DBPROPSET_PROPERTIESINERROR;
  v6 = *v5;
  v28 = a3;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *, unsigned int *, LPVOID *))(v6 + 24))(
         v5,
         1,
         &v30,
         &v26,
         &pv);
  if ( v7 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CQuery *)((char *)this + 64)) == -1 )
      {
        LODWORD(v24) = 2942;
        bidTraceW(
          off_18012A1E0[0],
          3012617,
          L"<CQuery::IsRequiredPropInError|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)v7,
          v24);
      }
      else
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CQuery *)((char *)this + 64));
        v25 = 2942;
        LODWORD(v24) = v7;
        bidTraceW(
          off_18012A1E0[0],
          3012617,
          L"<CQuery::IsRequiredPropInError|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          BidObjectID,
          v24,
          v25);
      }
    }
    goto LABEL_26;
  }
  v9 = v28;
  v10 = 0;
LABEL_8:
  if ( v10 < v26 )
  {
    v11 = 0;
    v12 = 32LL * v10;
    while ( 1 )
    {
      if ( (unsigned int)v11 >= *(_DWORD *)((char *)pv + v12 + 8) )
      {
        ++v10;
        goto LABEL_8;
      }
      v13 = *(_QWORD *)((char *)pv + v12);
      v14 = 0;
LABEL_12:
      if ( v14 >= v3 )
      {
        if ( !*(_DWORD *)(v13 + 72 * v11 + 4) )
        {
          v7 = 1;
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CQuery *)((char *)this + 64)) == -1 )
            {
              bidTraceW(off_18012A1E0[0], 3036169, L"<CQuery::IsRequiredPropInError|ADO|ERR>  line %d\n", 2965);
            }
            else
            {
              v17 = (unsigned int)CBidGenericBase::GetBidObjectID((CQuery *)((char *)this + 64));
              LODWORD(v24) = 2965;
              bidTraceW(off_18012A1E0[0], 3036169, L"<CQuery::IsRequiredPropInError|ADO|ERR> %u#, line %d\n", v17, v24);
            }
          }
          break;
        }
      }
      else
      {
        v15 = 0;
        v16 = v14;
        while ( 1 )
        {
          if ( (unsigned int)v15 >= v9[v16].cProperties )
          {
            v3 = v27;
            ++v14;
            goto LABEL_12;
          }
          v9 = v28;
          if ( *(_DWORD *)(v13 + 72 * v11) == v28[v16].rgProperties[v15].dwPropertyID )
            break;
          v15 = (unsigned int)(v15 + 1);
        }
        v3 = v27;
      }
      v11 = (unsigned int)(v11 + 1);
    }
  }
LABEL_26:
  v18 = v26;
  if ( v26 )
  {
    v19 = (char *)pv;
    v20 = 0;
    do
    {
      v21 = 32LL * v20;
      if ( *(_DWORD *)&v19[v21 + 8] )
      {
        v22 = 0;
        do
        {
          VariantClear((VARIANTARG *)(*(_QWORD *)&v19[v21] + 8 * (v22 + 8 * v22 + 6)));
          v22 = (unsigned int)(v22 + 1);
        }
        while ( (unsigned int)v22 < *(_DWORD *)&v19[v21 + 8] );
        CoTaskMemFree(*(LPVOID *)&v19[v21]);
      }
      ++v20;
    }
    while ( v20 < v18 );
    CoTaskMemFree(v19);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180052830  push    rbp
0x180052832  push    rbx
0x180052833  push    rsi
0x180052834  push    rdi
0x180052835  push    r12
0x180052837  push    r13
0x180052839  push    r14
0x18005283b  push    r15
0x18005283d  mov     rbp, rsp
0x180052840  sub     rsp, 78h
0x180052844  mov     rax, cs:__security_cookie
0x18005284b  xor     rax, rsp
0x18005284e  mov     [rbp+var_10], rax
0x180052852  movups  xmm0, xmmword ptr cs:DBPROPSET_PROPERTIESINERROR.Data1
0x180052859  mov     ebx, edx
0x18005285b  mov     [rbp+var_44], edx
0x18005285e  lea     rdx, [rbp+pv]
0x180052862  mov     [rbp+var_14], 0
0x180052869  mov     r15, rcx
0x18005286c  mov     [rbp+pv], 0
0x180052874  mov     rcx, [rcx+60h]
0x180052878  lea     r9, [rbp+var_48]
0x18005287c  mov     [rbp+var_48], 0
0x180052883  mov     [rbp+var_28], 0
0x18005288a  mov     [rbp+var_30], 0
0x180052892  movdqu  [rbp+var_24], xmm0
0x180052897  mov     rax, [rcx]
0x18005289a  mov     [rbp+var_40], r8
0x18005289e  lea     r8, [rbp+var_30]
0x1800528a2  mov     [rsp+78h+var_58], rdx
0x1800528a7  mov     edx, 1
0x1800528ac  mov     rax, [rax+18h]
0x1800528b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800528b5  mov     r12d, eax
0x1800528b8  test    eax, eax
0x1800528ba  jns     short loc_180052935
0x1800528bc  test    byte ptr cs:_bidGblFlags, 2
0x1800528c3  jz      loc_180052A1E
0x1800528c9  lea     rcx, [r15+40h]; this
0x1800528cd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800528d2  cmp     eax, 0FFFFFFFFh
0x1800528d5  jz      short loc_18005290D
0x1800528d7  lea     rcx, [r15+40h]; this
0x1800528db  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800528e0  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800528e7  lea     r8, aCqueryIsrequir_0; "<CQuery::IsRequiredPropInError|ADO|ERR>"...
0x1800528ee  mov     r9d, eax
0x1800528f1  mov     [rsp+78h+var_50], 0B7Eh
0x1800528f9  mov     edx, 2DF809h
0x1800528fe  mov     dword ptr [rsp+78h+var_58], r12d
0x180052903  call    _bidTraceW
0x180052908  jmp     loc_180052A1E
0x18005290d  mov     dword ptr [rsp+78h+var_58], 0B7Eh
0x180052915  lea     r8, aCqueryIsrequir; "<CQuery::IsRequiredPropInError|ADO|ERR>"...
0x18005291c  mov     r9d, r12d
0x18005291f  mov     edx, 2DF809h
0x180052924  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18005292b  call    _bidTraceW
0x180052930  jmp     loc_180052A1E
0x180052935  mov     rcx, [rbp+var_40]
0x180052939  xor     edx, edx
0x18005293b  cmp     edx, [rbp+var_48]
0x18005293e  jnb     loc_180052A1E
0x180052944  mov     r14, [rbp+pv]
0x180052948  xor     r8d, r8d
0x18005294b  mov     r11d, edx
0x18005294e  shl     r11, 5
0x180052952  cmp     r8d, [r11+r14+8]
0x180052957  jnb     loc_1800529F9
0x18005295d  mov     rsi, [r11+r14]
0x180052961  lea     rdi, [r8+r8*8]
0x180052965  xor     r9d, r9d
0x180052968  mov     r13d, [rsi+rdi*8]
0x18005296c  cmp     r9d, ebx
0x18005296f  jnb     short loc_1800529A5
0x180052971  xor     r10d, r10d
0x180052974  mov     ebx, r9d
0x180052977  shl     rbx, 5
0x18005297b  cmp     r10d, [rbx+rcx+8]
0x180052980  jnb     short loc_18005299D
0x180052982  mov     rax, [rbp+var_40]
0x180052986  lea     rcx, [r10+r10*8]
0x18005298a  mov     rax, [rbx+rax]
0x18005298e  cmp     r13d, [rax+rcx*8]
0x180052992  mov     rcx, [rbp+var_40]
0x180052996  jz      short loc_1800529EE
0x180052998  inc     r10d
0x18005299b  jmp     short loc_18005297B
0x18005299d  mov     ebx, [rbp+var_44]
0x1800529a0  inc     r9d
0x1800529a3  jmp     short loc_18005296C
0x1800529a5  cmp     dword ptr [rsi+rdi*8+4], 0
0x1800529aa  jnz     short loc_1800529F1
0x1800529ac  test    byte ptr cs:_bidGblFlags, 2
0x1800529b3  mov     r12d, 1
0x1800529b9  jz      short loc_180052A1E
0x1800529bb  lea     rcx, [r15+40h]; this
0x1800529bf  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800529c4  cmp     eax, 0FFFFFFFFh
0x1800529c7  jz      short loc_180052A00
0x1800529c9  lea     rcx, [r15+40h]; this
0x1800529cd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800529d2  mov     r9d, eax
0x1800529d5  mov     dword ptr [rsp+78h+var_58], 0B95h
0x1800529dd  lea     r8, aCqueryIsrequir_2; "<CQuery::IsRequiredPropInError|ADO|ERR>"...
0x1800529e4  mov     edx, 2E5409h
0x1800529e9  jmp     loc_180052924
0x1800529ee  mov     ebx, [rbp+var_44]
0x1800529f1  inc     r8d
0x1800529f4  jmp     loc_180052952
0x1800529f9  inc     edx
0x1800529fb  jmp     loc_18005293B
0x180052a00  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180052a07  lea     r8, aCqueryIsrequir_1; "<CQuery::IsRequiredPropInError|ADO|ERR>"...
0x180052a0e  mov     r9d, 0B95h
0x180052a14  mov     edx, 2E5409h
0x180052a19  call    _bidTraceW
0x180052a1e  mov     r14d, [rbp+var_48]
0x180052a22  test    r14d, r14d
0x180052a25  jz      short loc_180052A96
0x180052a27  mov     rdi, [rbp+pv]
0x180052a2b  xor     esi, esi
0x180052a2d  test    r14d, r14d
0x180052a30  jz      short loc_180052A87
0x180052a32  mov     ebx, esi
0x180052a34  shl     rbx, 5
0x180052a38  mov     eax, [rbx+rdi+8]
0x180052a3c  test    eax, eax
0x180052a3e  jz      short loc_180052A80
0x180052a40  xor     r15d, r15d
0x180052a43  test    eax, eax
0x180052a45  jz      short loc_180052A70
0x180052a47  mov     rax, [rbx+rdi]
0x180052a4b  lea     rcx, ds:6[r15*8]
0x180052a53  add     rcx, r15
0x180052a56  lea     rcx, [rax+rcx*8]; pvarg
0x180052a5a  call    cs:__imp_VariantClear
0x180052a61  nop     dword ptr [rax+rax+00h]
0x180052a66  inc     r15d
0x180052a69  cmp     r15d, [rbx+rdi+8]
0x180052a6e  jb      short loc_180052A47
0x180052a70  mov     rcx, [rbx+rdi]; pv
0x180052a74  call    cs:__imp_CoTaskMemFree
0x180052a7b  nop     dword ptr [rax+rax+00h]
0x180052a80  inc     esi
0x180052a82  cmp     esi, r14d
0x180052a85  jb      short loc_180052A32
0x180052a87  mov     rcx, rdi; pv
0x180052a8a  call    cs:__imp_CoTaskMemFree
0x180052a91  nop     dword ptr [rax+rax+00h]
0x180052a96  mov     eax, r12d
0x180052a99  mov     rcx, [rbp+var_10]
0x180052a9d  xor     rcx, rsp; StackCookie
0x180052aa0  call    __security_check_cookie
0x180052aa5  add     rsp, 78h
0x180052aa9  pop     r15
0x180052aab  pop     r14
0x180052aad  pop     r13
0x180052aaf  pop     r12
0x180052ab1  pop     rdi
0x180052ab2  pop     rsi
0x180052ab3  pop     rbx
0x180052ab4  pop     rbp
0x180052ab5  retn
```
