# CConnection::getLiteralString(ulong,CSysString &,int *)

- ea: `0x180075554`
- end: `0x18007581c`
- name: `?getLiteralString@CConnection@@QEAAJKAEAVCSysString@@PEAH@Z`
- size: `712`
- prototype: `int(CConnection *__hidden this, unsigned int, struct CSysString *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180072708`

## callees

- `0x18006a22c`
- `0x180075554`
- `0x1800c8f34`
- `0x1800cbaf8`
- `0x1800d0010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800757ca`
- `ole32!CoTaskMemFree` at `0x1800757df`
- `ole32!CoTaskMemFree` at `0x1800757ca`
- `ole32!CoTaskMemFree` at `0x1800757df`
- `OLEAUT32!__imp_SysFreeString` at `0x18007579d`
- `OLEAUT32!__imp_SysFreeString` at `0x18007579d`

## pseudocode

```c
__int64 __fastcall CConnection::getLiteralString(CConnection *this, int a2, struct CSysString *a3, int *a4)
{
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  int v8; // ebx
  __int64 v9; // r9
  unsigned int BidObjectID; // eax
  __int64 v11; // rdx
  __int64 v12; // rdx
  const unsigned __int16 *v13; // rdx
  __int64 v14; // r8
  int v15; // ecx
  __int64 v17; // [rsp+20h] [rbp-40h]
  __int64 v18; // [rsp+28h] [rbp-38h]
  LPVOID pv; // [rsp+40h] [rbp-20h] BYREF
  __int64 v20; // [rsp+48h] [rbp-18h] BYREF
  LPVOID v21[2]; // [rsp+50h] [rbp-10h] BYREF
  int v22; // [rsp+90h] [rbp+30h] BYREF
  int v23; // [rsp+98h] [rbp+38h] BYREF

  v23 = a2;
  v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 121);
  v20 = 0;
  v22 = 0;
  pv = 0;
  v21[0] = 0;
  if ( v5 )
  {
    v8 = (**v5)(v5, &IID_IDBInfo, &v20);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, LPVOID *, LPVOID *))(*(_QWORD *)v20 + 32LL))(
             v20,
             1,
             &v23,
             &v22,
             &pv,
             v21);
      if ( v8 >= 0 )
      {
        v13 = *(const unsigned __int16 **)pv;
        if ( *(_QWORD *)pv )
        {
          v14 = -1;
          do
            ++v14;
          while ( v13[v14] );
          v8 = CSysString::Set(a3, v13, v14);
          if ( v8 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_32;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
            {
              BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
              v11 = 3589129;
              LODWORD(v18) = 3505;
              goto LABEL_10;
            }
            LODWORD(v17) = 3505;
            v12 = 3589129;
            goto LABEL_12;
          }
        }
        else
        {
          SysFreeString(*(BSTR *)a3);
          *(_QWORD *)a3 = 0;
        }
        v15 = *((_DWORD *)pv + 7);
        if ( !v15 )
          v8 = 1;
        if ( a4 )
          *a4 = v15;
        goto LABEL_32;
      }
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_32;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        v11 = 3584009;
        LODWORD(v18) = 3500;
        goto LABEL_10;
      }
      LODWORD(v17) = 3500;
      v12 = 3584009;
    }
    else
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_32;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        v11 = 3582985;
        LODWORD(v18) = 3499;
LABEL_10:
        LODWORD(v17) = v8;
        bidTraceW(
          off_18012A1C0[0],
          v11,
          L"<CConnection::getLiteralString|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          BidObjectID,
          v17,
          v18);
        goto LABEL_32;
      }
      LODWORD(v17) = 3499;
      v12 = 3582985;
    }
LABEL_12:
    bidTraceW(
      off_18012A1C0[0],
      v12,
      L"<CConnection::getLiteralString|ADO|ERR> 0x%08x{HRESULT} line %d\n",
      (unsigned int)v8,
      v17);
    goto LABEL_32;
  }
  v8 = -2146825037;
  if ( (bidGblFlags & 2) == 0 )
    return (unsigned int)v8;
  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) == -1 )
  {
    bidTraceW(off_18012A1C0[0], 3580937, L"<CConnection::getLiteralString|ADO|ERR>  line %d\n", 3497);
  }
  else
  {
    v9 = (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
    bidTraceW(off_18012A1C0[0], 3580937, L"<CConnection::getLiteralString|ADO|ERR> %u#, line %d\n", v9, 3497);
  }
LABEL_32:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v21[0] )
    CoTaskMemFree(v21[0]);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180075554  mov     [rsp-28h+arg_10], rbx
0x180075559  mov     [rsp-28h+arg_18], rsi
0x18007555e  mov     [rsp-28h+arg_8], edx
0x180075562  push    rbp
0x180075563  push    rdi
0x180075564  push    r12
0x180075566  push    r14
0x180075568  push    r15
0x18007556a  mov     rbp, rsp
0x18007556d  sub     rsp, 60h
0x180075571  xor     r15d, r15d
0x180075574  mov     rdi, rcx
0x180075577  mov     rcx, [rcx+3C8h]
0x18007557e  mov     r14, r9
0x180075581  mov     [rbp+var_18], r15
0x180075585  mov     rsi, r8
0x180075588  mov     [rbp+arg_0], r15d
0x18007558c  mov     [rbp+pv], r15
0x180075590  mov     [rbp+var_10], r15
0x180075594  test    rcx, rcx
0x180075597  jnz     short loc_180075607
0x180075599  test    byte ptr cs:_bidGblFlags, 2
0x1800755a0  mov     ebx, 800A0CB3h
0x1800755a5  jz      loc_180075800
0x1800755ab  lea     rcx, [rdi+100h]; this
0x1800755b2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800755b7  cmp     eax, 0FFFFFFFFh
0x1800755ba  jz      short loc_1800755E4
0x1800755bc  lea     rcx, [rdi+100h]; this
0x1800755c3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800755c8  mov     r9d, eax
0x1800755cb  mov     dword ptr [rsp+60h+var_40], 0DA9h
0x1800755d3  lea     r8, aCconnectionGet_6; "<CConnection::getLiteralString|ADO|ERR>"...
0x1800755da  mov     edx, 36A409h
0x1800755df  jmp     loc_180075690
0x1800755e4  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800755eb  lea     r8, aCconnectionGet_7; "<CConnection::getLiteralString|ADO|ERR>"...
0x1800755f2  mov     r9d, 0DA9h
0x1800755f8  mov     edx, 36A409h
0x1800755fd  call    _bidTraceW
0x180075602  jmp     loc_1800757C1
0x180075607  mov     rax, [rcx]
0x18007560a  lea     r8, [rbp+var_18]
0x18007560e  lea     rdx, IID_IDBInfo
0x180075615  mov     rax, [rax]
0x180075618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007561d  mov     ebx, eax
0x18007561f  test    eax, eax
0x180075621  jns     short loc_1800756A1
0x180075623  test    byte ptr cs:_bidGblFlags, 2
0x18007562a  jz      loc_1800757C1
0x180075630  lea     rcx, [rdi+100h]; this
0x180075637  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007563c  cmp     eax, 0FFFFFFFFh
0x18007563f  jz      short loc_180075679
0x180075641  lea     rcx, [rdi+100h]; this
0x180075648  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007564d  mov     edx, 36AC09h
0x180075652  mov     dword ptr [rsp+60h+var_38], 0DABh
0x18007565a  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180075661  lea     r8, aCconnectionGet_27; "<CConnection::getLiteralString|ADO|ERR>"...
0x180075668  mov     r9d, eax
0x18007566b  mov     dword ptr [rsp+60h+var_40], ebx
0x18007566f  call    _bidTraceW
0x180075674  jmp     loc_1800757C1
0x180075679  mov     dword ptr [rsp+60h+var_40], 0DABh
0x180075681  mov     edx, 36AC09h
0x180075686  mov     r9d, ebx
0x180075689  lea     r8, aCconnectionGet_13; "<CConnection::getLiteralString|ADO|ERR>"...
0x180075690  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180075697  call    _bidTraceW
0x18007569c  jmp     loc_1800757C1
0x1800756a1  mov     rcx, [rbp+var_18]
0x1800756a5  lea     rdx, [rbp+var_10]
0x1800756a9  mov     [rsp+60h+var_38], rdx
0x1800756ae  lea     r9, [rbp+arg_0]
0x1800756b2  lea     rdx, [rbp+pv]
0x1800756b6  mov     r12d, 1
0x1800756bc  mov     [rsp+60h+var_40], rdx
0x1800756c1  lea     r8, [rbp+arg_8]
0x1800756c5  mov     rax, [rcx]
0x1800756c8  mov     edx, r12d
0x1800756cb  mov     rax, [rax+20h]
0x1800756cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800756d4  mov     ebx, eax
0x1800756d6  test    eax, eax
0x1800756d8  jns     short loc_180075728
0x1800756da  test    byte ptr cs:_bidGblFlags, 2
0x1800756e1  jz      loc_1800757C1
0x1800756e7  lea     rcx, [rdi+100h]; this
0x1800756ee  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800756f3  cmp     eax, 0FFFFFFFFh
0x1800756f6  jz      short loc_180075716
0x1800756f8  lea     rcx, [rdi+100h]; this
0x1800756ff  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180075704  mov     edx, 36B009h
0x180075709  mov     dword ptr [rsp+60h+var_38], 0DACh
0x180075711  jmp     loc_18007565A
0x180075716  mov     dword ptr [rsp+60h+var_40], 0DACh
0x18007571e  mov     edx, 36B009h
0x180075723  jmp     loc_180075686
0x180075728  mov     rax, [rbp+pv]
0x18007572c  mov     rdx, [rax]; unsigned __int16 *
0x18007572f  test    rdx, rdx
0x180075732  jz      short loc_18007579A
0x180075734  or      r8, 0FFFFFFFFFFFFFFFFh
0x180075738  inc     r8; unsigned int
0x18007573b  cmp     [rdx+r8*2], r15w
0x180075740  jnz     short loc_180075738
0x180075742  mov     rcx, rsi; this
0x180075745  call    ?Set@CSysString@@QEAAJPEBGK@Z; CSysString::Set(ushort const *,ulong)
0x18007574a  mov     ebx, eax
0x18007574c  test    eax, eax
0x18007574e  jns     short loc_1800757AC
0x180075750  test    byte ptr cs:_bidGblFlags, 2
0x180075757  jz      short loc_1800757C1
0x180075759  lea     rcx, [rdi+100h]; this
0x180075760  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180075765  cmp     eax, 0FFFFFFFFh
0x180075768  jz      short loc_180075788
0x18007576a  lea     rcx, [rdi+100h]; this
0x180075771  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180075776  mov     edx, 36C409h
0x18007577b  mov     dword ptr [rsp+60h+var_38], 0DB1h
0x180075783  jmp     loc_18007565A
0x180075788  mov     dword ptr [rsp+60h+var_40], 0DB1h
0x180075790  mov     edx, 36C409h
0x180075795  jmp     loc_180075686
0x18007579a  mov     rcx, [rsi]; bstrString
0x18007579d  call    cs:__imp_SysFreeString
0x1800757a4  nop     dword ptr [rax+rax+00h]
0x1800757a9  mov     [rsi], r15
0x1800757ac  mov     rax, [rbp+pv]
0x1800757b0  mov     ecx, [rax+1Ch]
0x1800757b3  test    ecx, ecx
0x1800757b5  cmovz   ebx, r12d
0x1800757b9  test    r14, r14
0x1800757bc  jz      short loc_1800757C1
0x1800757be  mov     [r14], ecx
0x1800757c1  mov     rcx, [rbp+pv]; pv
0x1800757c5  test    rcx, rcx
0x1800757c8  jz      short loc_1800757D6
0x1800757ca  call    cs:__imp_CoTaskMemFree
0x1800757d1  nop     dword ptr [rax+rax+00h]
0x1800757d6  mov     rcx, [rbp+var_10]; pv
0x1800757da  test    rcx, rcx
0x1800757dd  jz      short loc_1800757EB
0x1800757df  call    cs:__imp_CoTaskMemFree
0x1800757e6  nop     dword ptr [rax+rax+00h]
0x1800757eb  mov     rcx, [rbp+var_18]
0x1800757ef  test    rcx, rcx
0x1800757f2  jz      short loc_180075800
0x1800757f4  mov     rax, [rcx]
0x1800757f7  mov     rax, [rax+10h]
0x1800757fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075800  lea     r11, [rsp+60h+var_s0]
0x180075805  mov     eax, ebx
0x180075807  mov     rbx, [r11+40h]
0x18007580b  mov     rsi, [r11+48h]
0x18007580f  mov     rsp, r11
0x180075812  pop     r15
0x180075814  pop     r14
0x180075816  pop     r12
0x180075818  pop     rdi
0x180075819  pop     rbp
0x18007581a  retn
```
