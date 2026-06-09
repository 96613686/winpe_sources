# DiagnosisTextParserImpl::GetParameters(std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>> &,DiagnosisTextParser::DiagnosisParameter * *,ulong *)

- ea: `0x18001dbb4`
- end: `0x18001dd05`
- name: `?GetParameters@DiagnosisTextParserImpl@@AEAAJAEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@PEAPEAUDiagnosisParameter@DiagnosisTextParser@@PEAK@Z`
- size: `337`
- prototype: `__int64 __fastcall(__int64, __int64 **, LPVOID **, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180015de0`
- `0x180015f90`
- `0x18001a884`

## callees

- `0x180007ee4`
- `0x18001ad20`
- `0x18001d808`
- `0x18001dbb4`
- `0x18001f652`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18001dbf3`
- `ole32!CoTaskMemAlloc` at `0x18001dbf3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DiagnosisTextParserImpl::GetParameters(__int64 a1, __int64 **a2, LPVOID **a3, unsigned int *a4)
{
  unsigned __int64 v4; // rcx
  unsigned int v8; // eax
  SIZE_T v9; // rbx
  unsigned int v10; // esi
  LPVOID *v11; // rax
  LPVOID *v12; // rbp
  int v13; // edi
  unsigned int v14; // r14d
  __int64 *v15; // rbx
  __int64 *i; // rax
  __int64 *v17; // rcx

  v4 = (unsigned __int64)a2[1];
  if ( !v4 )
    return 1;
  v8 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v4);
  v9 = 16LL * v8;
  v10 = v8;
  v11 = (LPVOID *)CoTaskMemAlloc(v9);
  v12 = v11;
  if ( v11 )
  {
    v13 = 0;
    memset_0(v11, 0, v9);
    v14 = 0;
    v15 = (__int64 *)**a2;
    if ( !v10 )
    {
LABEL_21:
      *a3 = v12;
      *a4 = v10;
      return (unsigned int)v13;
    }
    while ( 1 )
    {
      if ( v13 < 0 )
      {
LABEL_23:
        FreeDiagnosisParameters(v12, v10);
        return (unsigned int)v13;
      }
      if ( v15 == *a2 )
      {
        v13 = -2147467259;
        goto LABEL_23;
      }
      v13 = UtilStringCopyWithAlloc(
              (unsigned __int16 **)&v12[2 * v14],
              *(_DWORD *)(v15[4] - 16) + 1,
              (const unsigned __int16 *)v15[4]);
      if ( v13 >= 0 )
        v13 = UtilStringCopyWithAlloc(
                (unsigned __int16 **)&v12[2 * v14 + 1],
                *(_DWORD *)(v15[5] - 16) + 1,
                (const unsigned __int16 *)v15[5]);
      ++v14;
      if ( !*((_BYTE *)v15 + 25) )
      {
        i = (__int64 *)v15[2];
        if ( *((_BYTE *)i + 25) )
        {
          for ( i = (__int64 *)v15[1]; !*((_BYTE *)i + 25) && v15 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v15 = i;
        }
        else
        {
          v17 = (__int64 *)*i;
          if ( !*(_BYTE *)(*i + 25) )
          {
            do
            {
              v15 = v17;
              v17 = (__int64 *)*v17;
            }
            while ( !*((_BYTE *)v17 + 25) );
            goto LABEL_19;
          }
        }
        v15 = i;
      }
LABEL_19:
      if ( v14 >= v10 )
      {
        if ( v13 >= 0 )
          goto LABEL_21;
        goto LABEL_23;
      }
    }
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x18001dbb4  mov     [rsp+arg_10], r8
0x18001dbb9  push    rbx
0x18001dbba  push    rbp
0x18001dbbb  push    rsi
0x18001dbbc  push    rdi
0x18001dbbd  push    r12
0x18001dbbf  push    r13
0x18001dbc1  push    r14
0x18001dbc3  push    r15
0x18001dbc5  sub     rsp, 28h
0x18001dbc9  mov     rcx, [rdx+8]
0x18001dbcd  xor     r15d, r15d
0x18001dbd0  mov     r13, r9
0x18001dbd3  mov     r12, rdx
0x18001dbd6  test    rcx, rcx
0x18001dbd9  jnz     short loc_18001DBE3
0x18001dbdb  lea     eax, [rcx+1]
0x18001dbde  jmp     loc_18001DCF4
0x18001dbe3  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001dbe8  mov     ebx, eax
0x18001dbea  shl     rbx, 4
0x18001dbee  mov     rcx, rbx; cb
0x18001dbf1  mov     esi, eax
0x18001dbf3  call    cs:__imp_CoTaskMemAlloc
0x18001dbf9  mov     rbp, rax
0x18001dbfc  test    rax, rax
0x18001dbff  jz      loc_18001DCED
0x18001dc05  mov     r8, rbx; Size
0x18001dc08  xor     edx, edx; Val
0x18001dc0a  mov     rcx, rax; void *
0x18001dc0d  mov     edi, r15d
0x18001dc10  call    memset_0
0x18001dc15  mov     rbx, [r12]
0x18001dc19  mov     r14d, r15d
0x18001dc1c  mov     rbx, [rbx]
0x18001dc1f  test    esi, esi
0x18001dc21  jz      loc_18001DCCB
0x18001dc27  test    edi, edi
0x18001dc29  js      loc_18001DCE1
0x18001dc2f  cmp     rbx, [r12]
0x18001dc33  jz      loc_18001DCDC
0x18001dc39  mov     r8, [rbx+20h]; unsigned __int16 *
0x18001dc3d  mov     r15d, r14d
0x18001dc40  shl     r15, 4
0x18001dc44  add     r15, rbp
0x18001dc47  mov     edx, [r8-10h]
0x18001dc4b  mov     rcx, r15; unsigned __int16 **
0x18001dc4e  inc     edx; unsigned int
0x18001dc50  call    ?UtilStringCopyWithAlloc@@YAJPEAPEAGIPEBG@Z; UtilStringCopyWithAlloc(ushort * *,uint,ushort const *)
0x18001dc55  mov     edi, eax
0x18001dc57  test    eax, eax
0x18001dc59  js      short loc_18001DC70
0x18001dc5b  mov     r8, [rbx+28h]; unsigned __int16 *
0x18001dc5f  lea     rcx, [r15+8]; unsigned __int16 **
0x18001dc63  mov     edx, [r8-10h]
0x18001dc67  inc     edx; unsigned int
0x18001dc69  call    ?UtilStringCopyWithAlloc@@YAJPEAPEAGIPEBG@Z; UtilStringCopyWithAlloc(ushort * *,uint,ushort const *)
0x18001dc6e  mov     edi, eax
0x18001dc70  inc     r14d
0x18001dc73  xor     r15d, r15d
0x18001dc76  mov     edx, edi
0x18001dc78  cmp     [rbx+19h], r15b
0x18001dc7c  jnz     short loc_18001DCBE
0x18001dc7e  mov     rax, [rbx+10h]
0x18001dc82  cmp     [rax+19h], r15b
0x18001dc86  jnz     short loc_18001DCA2
0x18001dc88  mov     rcx, [rax]
0x18001dc8b  cmp     [rcx+19h], r15b
0x18001dc8f  jnz     short loc_18001DCBB
0x18001dc91  mov     rax, [rcx]
0x18001dc94  mov     rbx, rcx
0x18001dc97  mov     rcx, rax
0x18001dc9a  cmp     [rax+19h], r15b
0x18001dc9e  jz      short loc_18001DC91
0x18001dca0  jmp     short loc_18001DCBE
0x18001dca2  mov     rax, [rbx+8]
0x18001dca6  jmp     short loc_18001DCB5
0x18001dca8  cmp     rbx, [rax+10h]
0x18001dcac  jnz     short loc_18001DCBB
0x18001dcae  mov     rbx, rax
0x18001dcb1  mov     rax, [rax+8]
0x18001dcb5  cmp     [rax+19h], r15b
0x18001dcb9  jz      short loc_18001DCA8
0x18001dcbb  mov     rbx, rax
0x18001dcbe  cmp     r14d, esi
0x18001dcc1  jb      loc_18001DC27
0x18001dcc7  test    edx, edx
0x18001dcc9  js      short loc_18001DCE1
0x18001dccb  mov     rax, [rsp+68h+arg_10]
0x18001dcd3  mov     [rax], rbp
0x18001dcd6  mov     [r13+0], esi
0x18001dcda  jmp     short loc_18001DCF2
0x18001dcdc  mov     edi, 80004005h
0x18001dce1  mov     edx, esi; unsigned int
0x18001dce3  mov     rcx, rbp; struct DiagnosisTextParser::DiagnosisParameter *
0x18001dce6  call    ?FreeDiagnosisParameters@@YAXPEAUDiagnosisParameter@DiagnosisTextParser@@K@Z; FreeDiagnosisParameters(DiagnosisTextParser::DiagnosisParameter *,ulong)
0x18001dceb  jmp     short loc_18001DCF2
0x18001dced  mov     edi, 8007000Eh
0x18001dcf2  mov     eax, edi
0x18001dcf4  add     rsp, 28h
0x18001dcf8  pop     r15
0x18001dcfa  pop     r14
0x18001dcfc  pop     r13
0x18001dcfe  pop     r12
0x18001dd00  pop     rdi
0x18001dd01  pop     rsi
0x18001dd02  pop     rbp
0x18001dd03  pop     rbx
0x18001dd04  retn
```
