# CMemStream::Write(void const *,ulong,ulong *)

- ea: `0x180049c80`
- end: `0x180049f3e`
- name: `?Write@CMemStream@@UEAAJPEBXKPEAK@Z`
- size: `702`
- prototype: `int(CMemStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180049c80`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800cdad2`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x180049d22`
- `MSDART!MpHeapAlloc` at `0x180049e2a`
- `MSDART!MpHeapAlloc` at `0x180049d22`
- `MSDART!MpHeapAlloc` at `0x180049e2a`

## string_xrefs

- `0x180049ef0`: `<CMemStream::Write|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180049def`: `<CMemStream::Write|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180049f1d`: `<CMemStream::Write|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
__int64 __fastcall CMemStream::Write(CMemStream *this, char *a2, unsigned int a3, unsigned int *a4)
{
  char *v6; // r15
  int v8; // esi
  unsigned int v9; // ebp
  unsigned int v10; // r14d
  unsigned int v11; // ecx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // r14d
  __int64 v17; // rcx
  unsigned int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdx
  unsigned int BidObjectID; // eax
  __int64 v23; // [rsp+20h] [rbp-38h]
  int v24; // [rsp+20h] [rbp-38h]
  int v25; // [rsp+68h] [rbp+10h]

  v6 = a2;
  if ( a2 )
  {
    v8 = *((_DWORD *)this + 17);
    v9 = 0;
    v25 = *((_DWORD *)this + 18);
LABEL_3:
    v10 = 0;
    if ( !a3 )
    {
      v11 = v25 + (v8 << 13) + v9;
      if ( v11 > *((_DWORD *)this + 16) )
        *((_DWORD *)this + 16) = v11;
      if ( a4 )
        *a4 = v9;
      return v10;
    }
    if ( *((_QWORD *)this + 6) )
    {
      while ( 1 )
      {
        if ( *((_DWORD *)this + 18) < 0x2000u )
        {
          v15 = *((_DWORD *)this + 18);
          if ( v15 < 0x2000 )
          {
            v16 = 0x2000 - v15;
            if ( 0x2000 - v15 > a3 )
              v16 = a3;
            memcpy_0((void *)(*((_QWORD *)this + 7) + v15), v6, v16);
            *((_DWORD *)this + 18) += v16;
            v17 = *((_QWORD *)this + 7);
            v18 = *((_DWORD *)this + 18);
            if ( *(_DWORD *)(v17 + 8200) < v18 )
              *(_DWORD *)(v17 + 8200) = v18;
            a3 -= v16;
            v6 += v16;
            v9 += v16;
          }
          goto LABEL_3;
        }
        v14 = *((_QWORD *)this + 7);
        if ( !*(_QWORD *)(v14 + 0x2000) )
        {
          v19 = MpHeapAlloc(g_hHeapHandle, 10485760, 8208);
          v20 = v19;
          if ( v19 )
          {
            *(_DWORD *)(v19 + 8200) = 0;
            *(_QWORD *)(v19 + 0x2000) = 0;
          }
          else
          {
            v20 = 0;
          }
          *(_QWORD *)(*((_QWORD *)this + 7) + 0x2000LL) = v20;
          v14 = *((_QWORD *)this + 7);
          if ( !*(_QWORD *)(v14 + 0x2000) )
            break;
        }
        *((_DWORD *)this + 18) -= 0x2000;
        ++*((_DWORD *)this + 17);
        v13 = *(_QWORD *)(v14 + 0x2000);
LABEL_12:
        *((_QWORD *)this + 7) = v13;
      }
      v10 = -2147024882;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_34;
      v24 = 403;
      v21 = 412681;
    }
    else
    {
      v13 = MpHeapAlloc(g_hHeapHandle, 10485760, 8208);
      if ( v13 )
      {
        *(_DWORD *)(v13 + 8200) = 0;
        *(_QWORD *)(v13 + 0x2000) = 0;
        *((_QWORD *)this + 6) = v13;
        *(_QWORD *)((char *)this + 68) = 0;
        goto LABEL_12;
      }
      *((_QWORD *)this + 6) = 0;
      v10 = -2147024882;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_34;
      v24 = 381;
      v21 = 390153;
    }
    bidTraceW(
      off_18012A230[0],
      v21,
      L"<CMemStream::AdvanceCurrentBlock|ADO|ERR> 0x%08x{HRESULT} line %d\n",
      2147942414LL,
      v24);
LABEL_34:
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CMemStream *)((char *)this + 32)) == -1 )
      {
        LODWORD(v23) = 669;
        bidTraceW(off_18012A230[0], 685065, L"<CMemStream::Write|ADO|ERR> 0x%08x{HRESULT} line %d\n", 2147942414LL, v23);
      }
      else
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CMemStream *)((char *)this + 32));
        LODWORD(v23) = -2147024882;
        bidTraceW(
          off_18012A230[0],
          685065,
          L"<CMemStream::Write|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          BidObjectID,
          v23,
          669);
      }
    }
    return v10;
  }
  if ( (bidGblFlags & 2) != 0 )
    bidTraceW(off_18012A230[0], 677897, L"<CMemStream::Write|ADO|ERR> 0x%08x{HRESULT} line %d\n", 2147680265LL, 662);
  return 2147680265LL;
}

```

## disassembly

```asm
0x180049c80  push    rbx
0x180049c82  push    rdi
0x180049c83  push    r12
0x180049c85  push    r15
0x180049c87  sub     rsp, 38h
0x180049c8b  mov     r12, r9
0x180049c8e  mov     edi, r8d
0x180049c91  mov     r15, rdx
0x180049c94  mov     rbx, rcx
0x180049c97  test    rdx, rdx
0x180049c9a  jz      loc_180049DDF
0x180049ca0  mov     eax, [rcx+48h]
0x180049ca3  mov     [rsp+58h+arg_0], rbp
0x180049ca8  mov     [rsp+58h+arg_10], rsi
0x180049cad  mov     esi, [rcx+44h]
0x180049cb0  mov     [rsp+58h+arg_18], r13
0x180049cb5  xor     r13d, r13d
0x180049cb8  mov     ebp, r13d
0x180049cbb  mov     [rsp+58h+var_28], r14
0x180049cc0  mov     [rsp+58h+arg_8], eax
0x180049cc4  mov     r14d, r13d
0x180049cc7  test    edi, edi
0x180049cc9  jnz     short loc_180049D09
0x180049ccb  shl     esi, 0Dh
0x180049cce  add     esi, [rsp+58h+arg_8]
0x180049cd2  lea     ecx, [rsi+rbp]
0x180049cd5  cmp     ecx, [rbx+40h]
0x180049cd8  jbe     short loc_180049CDD
0x180049cda  mov     [rbx+40h], ecx
0x180049cdd  test    r12, r12
0x180049ce0  jz      short loc_180049CE6
0x180049ce2  mov     [r12], ebp
0x180049ce6  mov     r13, [rsp+58h+arg_18]
0x180049ceb  mov     eax, r14d
0x180049cee  mov     r14, [rsp+58h+var_28]
0x180049cf3  mov     rsi, [rsp+58h+arg_10]
0x180049cf8  mov     rbp, [rsp+58h+arg_0]
0x180049cfd  add     rsp, 38h
0x180049d01  pop     r15
0x180049d03  pop     r12
0x180049d05  pop     rdi
0x180049d06  pop     rbx
0x180049d07  retn
0x180049d09  cmp     qword ptr [rbx+30h], 0
0x180049d0e  jnz     short loc_180049D55
0x180049d10  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180049d17  mov     edx, 0A00000h
0x180049d1c  mov     r8d, 2010h
0x180049d22  call    cs:__imp_MpHeapAlloc
0x180049d29  nop     dword ptr [rax+rax+00h]
0x180049d2e  test    rax, rax
0x180049d31  jz      loc_180049E8C
0x180049d37  mov     [rax+2008h], r13d
0x180049d3e  mov     [rax+2000h], r13
0x180049d45  mov     [rbx+30h], rax
0x180049d49  mov     qword ptr [rbx+44h], 0
0x180049d51  mov     [rbx+38h], rax
0x180049d55  cmp     dword ptr [rbx+48h], 2000h
0x180049d5c  jb      short loc_180049D83
0x180049d5e  mov     rax, [rbx+38h]
0x180049d62  cmp     qword ptr [rax+2000h], 0
0x180049d6a  jz      loc_180049E18
0x180049d70  add     dword ptr [rbx+48h], 0FFFFE000h
0x180049d77  inc     dword ptr [rbx+44h]
0x180049d7a  mov     rax, [rax+2000h]
0x180049d81  jmp     short loc_180049D51
0x180049d83  mov     eax, [rbx+48h]
0x180049d86  cmp     eax, 2000h
0x180049d8b  jnb     loc_180049CC4
0x180049d91  mov     ecx, eax
0x180049d93  mov     r14d, 2000h
0x180049d99  sub     r14d, eax
0x180049d9c  mov     rdx, r15; Src
0x180049d9f  cmp     r14d, edi
0x180049da2  cmova   r14d, edi
0x180049da6  add     rcx, [rbx+38h]; void *
0x180049daa  mov     r8d, r14d; Size
0x180049dad  mov     r13d, r14d
0x180049db0  call    memcpy_0
0x180049db5  add     [rbx+48h], r14d
0x180049db9  mov     rcx, [rbx+38h]
0x180049dbd  mov     eax, [rbx+48h]
0x180049dc0  cmp     [rcx+2008h], eax
0x180049dc6  jnb     short loc_180049DCE
0x180049dc8  mov     [rcx+2008h], eax
0x180049dce  sub     edi, r14d
0x180049dd1  add     r15, r13
0x180049dd4  add     ebp, r14d
0x180049dd7  xor     r13d, r13d
0x180049dda  jmp     loc_180049CC4
0x180049ddf  test    byte ptr cs:_bidGblFlags, 2
0x180049de6  jz      short loc_180049E0E
0x180049de8  mov     rcx, cs:off_18012A230; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180049def  lea     r8, aCmemstreamWrit; "<CMemStream::Write|ADO|ERR> 0x%08x{HRES"...
0x180049df6  mov     r9d, 80030009h
0x180049dfc  mov     dword ptr [rsp+58h+var_38], 296h
0x180049e04  mov     edx, 0A5809h
0x180049e09  call    _bidTraceW
0x180049e0e  mov     eax, 80030009h
0x180049e13  jmp     loc_180049CFD
0x180049e18  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180049e1f  mov     edx, 0A00000h
0x180049e24  mov     r8d, 2010h
0x180049e2a  call    cs:__imp_MpHeapAlloc
0x180049e31  nop     dword ptr [rax+rax+00h]
0x180049e36  mov     rcx, rax
0x180049e39  test    rax, rax
0x180049e3c  jz      short loc_180049E4E
0x180049e3e  mov     [rax+2008h], r13d
0x180049e45  mov     [rax+2000h], r13
0x180049e4c  jmp     short loc_180049E51
0x180049e4e  mov     rcx, r13
0x180049e51  mov     rax, [rbx+38h]
0x180049e55  mov     [rax+2000h], rcx
0x180049e5c  mov     rax, [rbx+38h]
0x180049e60  cmp     qword ptr [rax+2000h], 0
0x180049e68  jnz     loc_180049D70
0x180049e6e  test    byte ptr cs:_bidGblFlags, 2
0x180049e75  mov     r14d, 8007000Eh
0x180049e7b  jz      short loc_180049EC2
0x180049e7d  mov     dword ptr [rsp+58h+var_38], 193h
0x180049e85  mov     edx, 64C09h
0x180049e8a  jmp     short loc_180049EAC
0x180049e8c  mov     [rbx+30h], r13
0x180049e90  mov     r14d, 8007000Eh
0x180049e96  test    byte ptr cs:_bidGblFlags, 2
0x180049e9d  jz      short loc_180049EC2
0x180049e9f  mov     dword ptr [rsp+58h+var_38], 17Dh
0x180049ea7  mov     edx, 5F409h
0x180049eac  mov     rcx, cs:off_18012A230; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180049eb3  lea     r8, aCmemstreamAdva; "<CMemStream::AdvanceCurrentBlock|ADO|ER"...
0x180049eba  mov     r9d, r14d
0x180049ebd  call    _bidTraceW
0x180049ec2  test    byte ptr cs:_bidGblFlags, 2
0x180049ec9  mov     edi, r14d
0x180049ecc  jz      loc_180049CE6
0x180049ed2  lea     rcx, [rbx+20h]; this
0x180049ed6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180049edb  cmp     eax, 0FFFFFFFFh
0x180049ede  jz      short loc_180049F16
0x180049ee0  lea     rcx, [rbx+20h]; this
0x180049ee4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180049ee9  mov     rcx, cs:off_18012A230; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180049ef0  lea     r8, aCmemstreamWrit_0; "<CMemStream::Write|ADO|ERR> %u#,0x%08x{"...
0x180049ef7  mov     r9d, eax
0x180049efa  mov     [rsp+58h+var_30], 29Dh
0x180049f02  mov     edx, 0A7409h
0x180049f07  mov     dword ptr [rsp+58h+var_38], r14d
0x180049f0c  call    _bidTraceW
0x180049f11  jmp     loc_180049CE6
0x180049f16  mov     rcx, cs:off_18012A230; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180049f1d  lea     r8, aCmemstreamWrit; "<CMemStream::Write|ADO|ERR> 0x%08x{HRES"...
0x180049f24  mov     r9d, edi
0x180049f27  mov     dword ptr [rsp+58h+var_38], 29Dh
0x180049f2f  mov     edx, 0A7409h
0x180049f34  call    _bidTraceW
0x180049f39  jmp     loc_180049CE6
```
