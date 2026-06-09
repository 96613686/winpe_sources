# MapNameToPropId(CPropertySetStream *,ushort,tagPROPSPEC const * const,ulong,ulong,ulong,long *)

- ea: `0x180059670`
- end: `0x1800597c0`
- name: `?MapNameToPropId@@YAKPEAVCPropertySetStream@@GQEBUtagPROPSPEC@@KKKPEAJ@Z`
- size: `336`
- prototype: `unsigned int __usercall@<eax>(struct CPropertySetStream *this@<rcx>, unsigned __int16@<dx>, const struct tagPROPSPEC *const@<r8>, unsigned int@<r9d>, unsigned int, unsigned int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026f60`

## callees

- `0x180025c28`
- `0x180025f10`
- `0x1800269c0`
- `0x180029bc8`
- `0x180059670`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005972e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800597a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005972e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800597a6`

## pseudocode

```c
__int64 __fastcall MapNameToPropId(
        struct CPropertySetStream *this,
        __int16 a2,
        const struct tagPROPSPEC *const a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int16 *lpwstr)
{
  int *v7; // rbx
  __int64 v10; // rax
  unsigned int v12; // eax
  unsigned int i; // edi
  bool v14; // zf
  unsigned int Propid; // eax
  bool v16; // sf
  const struct tagSERIALIZEDPROPERTYVALUE *Value; // rax
  unsigned int v19; // [rsp+68h] [rbp+38h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+40h] BYREF

  LOWORD(v19) = a2;
  v7 = (int *)lpwstr;
  v10 = a5;
  pv = 0;
  *(_DWORD *)lpwstr = 0;
  lpwstr = a3[v10].lpwstr;
  v12 = a6;
  while ( 2 )
  {
    v19 = v12;
    if ( v12 < 2 )
    {
      *v7 = -1073741811;
      goto LABEL_22;
    }
    for ( i = 0; i < a4; ++i )
    {
      if ( i == a5 )
        continue;
      if ( a3[i].ulKind == 1 )
      {
        v14 = a3[i].propid == v19;
        goto LABEL_10;
      }
      if ( !a3[i].ulKind )
      {
        Propid = CPropertySetStream::QueryPropid(this, a3[i].lpwstr, v7);
        v14 = Propid == v19;
LABEL_10:
        if ( v14 )
          goto LABEL_18;
      }
      if ( *v7 < 0 )
        goto LABEL_22;
    }
    if ( CPropertySetStream::QueryPropertyNames(this, 1u, &v19, (unsigned __int16 **const)&pv, v7) )
    {
      CoTaskMemFree(pv);
      pv = 0;
LABEL_18:
      v12 = v19 + 1;
      continue;
    }
    break;
  }
  v16 = *v7 < 0;
  a6 = 0;
  if ( !v16 )
  {
    Value = CPropertySetStream::GetValue(this, v19, &a6, v7);
    if ( *v7 >= 0 )
    {
      if ( Value )
        goto LABEL_18;
      CPropertySetStream::SetPropertyNames(this, 1u, &v19, (const unsigned __int16 **)&lpwstr, v7);
      if ( *v7 >= 0 )
        *v7 = 0;
    }
  }
LABEL_22:
  if ( pv )
    CoTaskMemFree(pv);
  return v19;
}

```

## disassembly

```asm
0x180059670  mov     [rsp-28h+arg_0], rbx
0x180059675  mov     word ptr [rsp-28h+arg_8], dx
0x18005967a  push    rbp
0x18005967b  push    rsi
0x18005967c  push    rdi
0x18005967d  push    r14
0x18005967f  push    r15
0x180059681  mov     rbp, rsp
0x180059684  sub     rsp, 30h
0x180059688  mov     rbx, [rbp+arg_30]
0x18005968c  mov     r15d, r9d
0x18005968f  mov     eax, [rbp+arg_20]
0x180059692  mov     r14, r8
0x180059695  add     rax, rax
0x180059698  mov     [rbp+pv], 0
0x1800596a0  mov     rsi, rcx
0x1800596a3  mov     dword ptr [rbx], 0
0x1800596a9  mov     rax, [r8+rax*8+8]
0x1800596ae  mov     [rbp+arg_30], rax
0x1800596b2  mov     eax, [rbp+arg_28]
0x1800596b5  mov     [rbp+arg_8], eax
0x1800596b8  cmp     eax, 2
0x1800596bb  jb      loc_180059797
0x1800596c1  xor     edi, edi
0x1800596c3  cmp     edi, r15d
0x1800596c6  jnb     short loc_18005970C
0x1800596c8  cmp     edi, [rbp+arg_20]
0x1800596cb  jz      short loc_180059708
0x1800596cd  mov     edx, edi
0x1800596cf  add     rdx, rdx
0x1800596d2  cmp     dword ptr [r14+rdx*8], 1
0x1800596d7  jnz     short loc_1800596E3
0x1800596d9  mov     eax, [rbp+arg_8]
0x1800596dc  cmp     [r14+rdx*8+8], eax
0x1800596e1  jmp     short loc_1800596FD
0x1800596e3  cmp     dword ptr [r14+rdx*8], 0
0x1800596e8  jnz     short loc_1800596FF
0x1800596ea  mov     rdx, [r14+rdx*8+8]; lpString1
0x1800596ef  mov     r8, rbx; int *
0x1800596f2  mov     rcx, rsi; this
0x1800596f5  call    ?QueryPropid@CPropertySetStream@@QEAAKPEBGPEAJ@Z; CPropertySetStream::QueryPropid(ushort const *,long *)
0x1800596fa  cmp     eax, [rbp+arg_8]
0x1800596fd  jz      short loc_180059766
0x1800596ff  cmp     dword ptr [rbx], 0
0x180059702  jl      loc_18005979D
0x180059708  inc     edi
0x18005970a  jmp     short loc_1800596C3
0x18005970c  lea     r9, [rbp+pv]; unsigned __int16 **
0x180059710  mov     [rsp+30h+var_10], rbx; int *
0x180059715  lea     r8, [rbp+arg_8]; unsigned int *
0x180059719  mov     edx, 1; unsigned int
0x18005971e  mov     rcx, rsi; this
0x180059721  call    ?QueryPropertyNames@CPropertySetStream@@QEAAEKPEBKQEAPEAGPEAJ@Z; CPropertySetStream::QueryPropertyNames(ulong,ulong const *,ushort * * const,long *)
0x180059726  test    al, al
0x180059728  jz      short loc_18005973E
0x18005972a  mov     rcx, [rbp+pv]; pv
0x18005972e  call    cs:__imp_CoTaskMemFree
0x180059734  mov     [rbp+pv], 0
0x18005973c  jmp     short loc_180059766
0x18005973e  cmp     dword ptr [rbx], 0
0x180059741  mov     [rbp+arg_28], 0
0x180059748  jl      short loc_18005979D
0x18005974a  mov     edx, [rbp+arg_8]; unsigned int
0x18005974d  lea     r8, [rbp+arg_28]; unsigned int *
0x180059751  mov     r9, rbx; int *
0x180059754  mov     rcx, rsi; this
0x180059757  call    ?GetValue@CPropertySetStream@@QEAAPEBUtagSERIALIZEDPROPERTYVALUE@@KPEAKPEAJ@Z; CPropertySetStream::GetValue(ulong,ulong *,long *)
0x18005975c  cmp     dword ptr [rbx], 0
0x18005975f  jl      short loc_18005979D
0x180059761  test    rax, rax
0x180059764  jz      short loc_180059770
0x180059766  mov     eax, [rbp+arg_8]
0x180059769  inc     eax
0x18005976b  jmp     loc_1800596B5
0x180059770  lea     r9, [rbp+arg_30]; unsigned __int16 **
0x180059774  mov     [rsp+30h+var_10], rbx; int *
0x180059779  lea     r8, [rbp+arg_8]; unsigned int *
0x18005977d  mov     edx, 1; unsigned int
0x180059782  mov     rcx, rsi; this
0x180059785  call    ?SetPropertyNames@CPropertySetStream@@QEAAXKPEBKQEBQEBGPEAJ@Z; CPropertySetStream::SetPropertyNames(ulong,ulong const *,ushort const * const * const,long *)
0x18005978a  cmp     dword ptr [rbx], 0
0x18005978d  jl      short loc_18005979D
0x18005978f  mov     dword ptr [rbx], 0
0x180059795  jmp     short loc_18005979D
0x180059797  mov     dword ptr [rbx], 0C000000Dh
0x18005979d  mov     rcx, [rbp+pv]; pv
0x1800597a1  test    rcx, rcx
0x1800597a4  jz      short loc_1800597AC
0x1800597a6  call    cs:__imp_CoTaskMemFree
0x1800597ac  mov     eax, [rbp+arg_8]
0x1800597af  mov     rbx, [rsp+30h+arg_0]
0x1800597b4  add     rsp, 30h
0x1800597b8  pop     r15
0x1800597ba  pop     r14
0x1800597bc  pop     rdi
0x1800597bd  pop     rsi
0x1800597be  pop     rbp
0x1800597bf  retn
```
