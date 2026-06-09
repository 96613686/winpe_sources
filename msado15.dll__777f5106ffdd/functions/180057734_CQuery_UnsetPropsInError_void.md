# CQuery::UnsetPropsInError(void)

- ea: `0x180057734`
- end: `0x180057931`
- name: `?UnsetPropsInError@CQuery@@QEAAJXZ`
- size: `509`
- prototype: `__int64 __fastcall(CQuery *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18005275c`

## callees

- `0x180057734`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800578ea`
- `ole32!CoTaskMemFree` at `0x180057904`
- `ole32!CoTaskMemFree` at `0x1800578ea`
- `ole32!CoTaskMemFree` at `0x180057904`
- `OLEAUT32!__imp_VariantClear` at `0x180057857`
- `OLEAUT32!__imp_VariantClear` at `0x1800578d0`
- `OLEAUT32!__imp_VariantClear` at `0x180057857`
- `OLEAUT32!__imp_VariantClear` at `0x1800578d0`

## pseudocode

```c
__int64 __fastcall CQuery::UnsetPropsInError(CQuery *this)
{
  unsigned int v1; // r12d
  __int64 v3; // rcx
  int v4; // r15d
  unsigned int BidObjectID; // eax
  unsigned int v6; // edi
  char v7; // al
  char *v8; // rbx
  unsigned int v9; // esi
  unsigned int v10; // r15d
  __int64 v11; // r14
  int v12; // eax
  unsigned int i; // r14d
  __int64 v14; // rsi
  __int64 v16; // [rsp+20h] [rbp-58h]
  int v17; // [rsp+28h] [rbp-50h]
  unsigned int v18; // [rsp+30h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-40h] BYREF
  __int64 v20; // [rsp+40h] [rbp-38h] BYREF
  int v21; // [rsp+48h] [rbp-30h]
  GUID v22; // [rsp+4Ch] [rbp-2Ch]
  int v23; // [rsp+5Ch] [rbp-1Ch]

  v1 = 0;
  v23 = 0;
  v3 = *((_QWORD *)this + 12);
  pv = 0;
  v18 = 0;
  v21 = 0;
  v20 = 0;
  v22 = DBPROPSET_PROPERTIESINERROR;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, unsigned int *, LPVOID *))(*(_QWORD *)v3 + 24LL))(
         v3,
         1,
         &v20,
         &v18,
         &pv);
  if ( v4 >= 0 )
  {
    v6 = v18;
    v7 = 0;
    v8 = (char *)pv;
    v9 = 0;
    if ( !v18 )
      goto LABEL_13;
    do
    {
      v10 = 0;
      v11 = 32LL * v9;
      if ( *(_DWORD *)&v8[v11 + 8] )
      {
        do
        {
          VariantClear((VARIANTARG *)(*(_QWORD *)&v8[v11] + 8 * (9LL * v10 + 6)));
          v8 = (char *)pv;
          ++v10;
          v7 = 1;
        }
        while ( v10 < *(_DWORD *)((char *)pv + v11 + 8) );
        v6 = v18;
      }
      ++v9;
    }
    while ( v9 < v6 );
    if ( v7 )
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)this + 12) + 32LL))(
              *((_QWORD *)this + 12),
              v6,
              v8);
      v8 = (char *)pv;
      v4 = v12;
      v6 = v18;
    }
    else
    {
LABEL_13:
      v4 = 1;
    }
    if ( v6 )
    {
      for ( i = 0; i < v6; ++i )
      {
        v14 = 32LL * i;
        if ( *(_DWORD *)&v8[v14 + 8] )
        {
          do
            VariantClear((VARIANTARG *)(*(_QWORD *)&v8[v14] + 8 * (9LL * v1++ + 6)));
          while ( v1 < *(_DWORD *)&v8[v14 + 8] );
          CoTaskMemFree(*(LPVOID *)&v8[v14]);
          v1 = 0;
        }
      }
      CoTaskMemFree(v8);
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CQuery *)((char *)this + 64)) == -1 )
    {
      LODWORD(v16) = 4737;
      bidTraceW(
        off_18012A1E0[0],
        4850697,
        L"<CQuery::UnsetPropsInError|ADO|ERR> 0x%08x{HRESULT} line %d\n",
        (unsigned int)v4,
        v16);
    }
    else
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CQuery *)((char *)this + 64));
      v17 = 4737;
      LODWORD(v16) = v4;
      bidTraceW(
        off_18012A1E0[0],
        4850697,
        L"<CQuery::UnsetPropsInError|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        BidObjectID,
        v16,
        v17);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180057734  push    rbp
0x180057736  push    rbx
0x180057737  push    rsi
0x180057738  push    rdi
0x180057739  push    r12
0x18005773b  push    r13
0x18005773d  push    r14
0x18005773f  push    r15
0x180057741  mov     rbp, rsp
0x180057744  sub     rsp, 78h
0x180057748  mov     rax, cs:__security_cookie
0x18005774f  xor     rax, rsp
0x180057752  mov     [rbp+var_18], rax
0x180057756  movups  xmm0, xmmword ptr cs:DBPROPSET_PROPERTIESINERROR.Data1
0x18005775d  xor     r12d, r12d
0x180057760  lea     rdx, [rbp+pv]
0x180057764  mov     r13, rcx
0x180057767  mov     [rbp+var_1C], r12d
0x18005776b  mov     rcx, [rcx+60h]
0x18005776f  lea     r9, [rbp+var_48]
0x180057773  mov     [rbp+pv], r12
0x180057777  lea     r8, [rbp+var_38]
0x18005777b  mov     [rbp+var_48], r12d
0x18005777f  mov     [rbp+var_30], r12d
0x180057783  mov     [rbp+var_38], r12
0x180057787  movdqu  [rbp+var_2C], xmm0
0x18005778c  mov     rax, [rcx]
0x18005778f  mov     [rsp+78h+var_58], rdx
0x180057794  lea     edx, [r12+1]
0x180057799  mov     rax, [rax+18h]
0x18005779d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800577a2  mov     r15d, eax
0x1800577a5  test    eax, eax
0x1800577a7  jns     short loc_180057822
0x1800577a9  test    byte ptr cs:_bidGblFlags, 2
0x1800577b0  jz      loc_180057910
0x1800577b6  lea     rcx, [r13+40h]; this
0x1800577ba  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800577bf  cmp     eax, 0FFFFFFFFh
0x1800577c2  jz      short loc_1800577FA
0x1800577c4  lea     rcx, [r13+40h]; this
0x1800577c8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800577cd  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800577d4  lea     r8, aCqueryUnsetpro_0; "<CQuery::UnsetPropsInError|ADO|ERR> %u#"...
0x1800577db  mov     r9d, eax
0x1800577de  mov     [rsp+78h+var_50], 1281h
0x1800577e6  mov     edx, 4A0409h
0x1800577eb  mov     dword ptr [rsp+78h+var_58], r15d
0x1800577f0  call    _bidTraceW
0x1800577f5  jmp     loc_180057910
0x1800577fa  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180057801  lea     r8, aCqueryUnsetpro; "<CQuery::UnsetPropsInError|ADO|ERR> 0x%"...
0x180057808  mov     r9d, r15d
0x18005780b  mov     dword ptr [rsp+78h+var_58], 1281h
0x180057813  mov     edx, 4A0409h
0x180057818  call    _bidTraceW
0x18005781d  jmp     loc_180057910
0x180057822  mov     edi, [rbp+var_48]
0x180057825  mov     al, r12b
0x180057828  mov     rbx, [rbp+pv]
0x18005782c  mov     esi, r12d
0x18005782f  test    edi, edi
0x180057831  jz      short loc_1800578A1
0x180057833  mov     r14d, esi
0x180057836  mov     r15d, r12d
0x180057839  shl     r14, 5
0x18005783d  cmp     [r14+rbx+8], r12d
0x180057842  jbe     short loc_180057876
0x180057844  mov     eax, r15d
0x180057847  lea     rcx, [rax+rax*8]
0x18005784b  mov     rax, [r14+rbx]
0x18005784f  lea     rcx, [rcx+6]
0x180057853  lea     rcx, [rax+rcx*8]; pvarg
0x180057857  call    cs:__imp_VariantClear
0x18005785e  nop     dword ptr [rax+rax+00h]
0x180057863  mov     rbx, [rbp+pv]
0x180057867  inc     r15d
0x18005786a  mov     al, 1
0x18005786c  cmp     r15d, [r14+rbx+8]
0x180057871  jb      short loc_180057844
0x180057873  mov     edi, [rbp+var_48]
0x180057876  inc     esi
0x180057878  cmp     esi, edi
0x18005787a  jb      short loc_180057833
0x18005787c  test    al, al
0x18005787e  jz      short loc_1800578A1
0x180057880  mov     rcx, [r13+60h]
0x180057884  mov     r8, rbx
0x180057887  mov     edx, edi
0x180057889  mov     rax, [rcx]
0x18005788c  mov     rax, [rax+20h]
0x180057890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057895  mov     rbx, [rbp+pv]
0x180057899  mov     r15d, eax
0x18005789c  mov     edi, [rbp+var_48]
0x18005789f  jmp     short loc_1800578A7
0x1800578a1  mov     r15d, 1
0x1800578a7  test    edi, edi
0x1800578a9  jz      short loc_180057910
0x1800578ab  mov     r14d, r12d
0x1800578ae  mov     esi, r14d
0x1800578b1  shl     rsi, 5
0x1800578b5  mov     eax, [rsi+rbx+8]
0x1800578b9  test    eax, eax
0x1800578bb  jz      short loc_1800578F9
0x1800578bd  mov     eax, r12d
0x1800578c0  lea     rcx, [rax+rax*8]
0x1800578c4  mov     rax, [rsi+rbx]
0x1800578c8  lea     rcx, [rcx+6]
0x1800578cc  lea     rcx, [rax+rcx*8]; pvarg
0x1800578d0  call    cs:__imp_VariantClear
0x1800578d7  nop     dword ptr [rax+rax+00h]
0x1800578dc  inc     r12d
0x1800578df  cmp     r12d, [rsi+rbx+8]
0x1800578e4  jb      short loc_1800578BD
0x1800578e6  mov     rcx, [rsi+rbx]; pv
0x1800578ea  call    cs:__imp_CoTaskMemFree
0x1800578f1  nop     dword ptr [rax+rax+00h]
0x1800578f6  xor     r12d, r12d
0x1800578f9  inc     r14d
0x1800578fc  cmp     r14d, edi
0x1800578ff  jb      short loc_1800578AE
0x180057901  mov     rcx, rbx; pv
0x180057904  call    cs:__imp_CoTaskMemFree
0x18005790b  nop     dword ptr [rax+rax+00h]
0x180057910  mov     eax, r15d
0x180057913  mov     rcx, [rbp+var_18]
0x180057917  xor     rcx, rsp; StackCookie
0x18005791a  call    __security_check_cookie
0x18005791f  add     rsp, 78h
0x180057923  pop     r15
0x180057925  pop     r14
0x180057927  pop     r13
0x180057929  pop     r12
0x18005792b  pop     rdi
0x18005792c  pop     rsi
0x18005792d  pop     rbx
0x18005792e  pop     rbp
0x18005792f  retn
```
