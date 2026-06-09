# CExposedDocFile::EnumElements(ulong,void *,ulong,IEnumSTATSTG * *)

- ea: `0x180024020`
- end: `0x1800241bd`
- name: `?EnumElements@CExposedDocFile@@UEAAJKPEAXKPEAPEAUIEnumSTATSTG@@@Z`
- size: `413`
- prototype: `__int64 __fastcall(CExposedDocFile *__hidden this, unsigned int, void *, unsigned int, struct IEnumSTATSTG **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180015f30`
- `0x180016810`
- `0x18001c01c`
- `0x180024020`
- `0x1800241c4`
- `0x1800241f8`
- `0x18003dc44`
- `0x180042800`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800240f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800240f8`

## pseudocode

```c
__int64 __fastcall CExposedDocFile::EnumElements(
        CExposedDocFile *this,
        unsigned int a2,
        void *a3,
        unsigned int a4,
        struct IEnumSTATSTG **a5)
{
  _QWORD *v5; // rsi
  int v7; // ebx
  __int64 v8; // rax
  _QWORD *v9; // rcx
  CExposedIterator *v10; // rax
  struct IConnectionPointContainer *v11; // rax
  struct IEnumSTATSTG *v12; // rsi
  int v14; // [rsp+30h] [rbp-A8h] BYREF
  _QWORD *v15; // [rsp+38h] [rbp-A0h]
  __int128 v16; // [rsp+40h] [rbp-98h]
  _BYTE v17[64]; // [rsp+50h] [rbp-88h] BYREF
  __int16 v18; // [rsp+90h] [rbp-48h]

  v5 = (_QWORD *)*((_QWORD *)this + 22);
  v14 = -2147286784;
  v15 = v5;
  v18 = 0;
  v16 = 0;
  v7 = CExpParameterValidate::EnumElements(a2, a3, a4, a5);
  if ( v7 >= 0 )
  {
    v7 = CExposedDocFile::Validate(this);
    if ( v7 >= 0 )
    {
      v7 = CSafeSem::Take((CSafeSem *)&v14);
      if ( v7 >= 0 )
      {
        v8 = *((_QWORD *)this + 20);
        if ( (*(_BYTE *)(v8 + 20) & 0x40) != 0 )
        {
          if ( (*(_BYTE *)(v8 + 20) & 0x20) != 0 )
          {
            v7 = -2147286782;
          }
          else
          {
            v9 = (_QWORD *)*((_QWORD *)this + 21);
            v9[4] = v5[2];
            v9[5] = v5[3];
            v9[6] = v5[4];
            v10 = (CExposedIterator *)CoTaskMemAlloc(0x98u);
            if ( v10
              && (v11 = (struct IConnectionPointContainer *)CExposedIterator::CExposedIterator(
                                                              v10,
                                                              *((struct CPubDocFile **)this + 20),
                                                              (struct CDfName *)v17,
                                                              *((struct CDFBasis **)this + 21),
                                                              *((struct CPerContext **)this + 22)),
                  (v12 = (struct IEnumSTATSTG *)v11) != 0) )
            {
              v7 = 0;
              _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 22) + 56LL));
              if ( *((_QWORD *)this + 13)
                && (v7 = CAsyncConnection::Init(
                           (CAsyncConnection *)&v11[2],
                           v11 + 1,
                           (CExposedDocFile *)((char *)this + 88)),
                    v7 < 0) )
              {
                ((void (__fastcall *)(struct IEnumSTATSTG *))v12->lpVtbl->Release)(v12);
                ((void (__fastcall *)(struct IEnumSTATSTG *))v12->lpVtbl->Release)(v12);
              }
              else
              {
                *a5 = v12;
              }
            }
            else
            {
              v7 = -2147287032;
            }
          }
        }
        else
        {
          v7 = -2147287035;
        }
      }
    }
  }
  CSafeSem::Release((CSafeSem *)&v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180024020  push    rbx
0x180024022  push    rsi
0x180024023  push    rdi
0x180024024  push    r14
0x180024026  sub     rsp, 0B8h
0x18002402d  mov     rax, cs:__security_cookie
0x180024034  xor     rax, rsp
0x180024037  mov     [rsp+0D8h+var_38], rax
0x18002403f  mov     rsi, [rcx+0B0h]
0x180024046  mov     r11, r8
0x180024049  mov     r14, [rsp+0D8h+arg_20]
0x180024051  mov     r10d, r9d
0x180024054  mov     ebx, edx
0x180024056  mov     [rsp+0D8h+var_A8], 80030100h
0x18002405e  xor     eax, eax
0x180024060  mov     [rsp+0D8h+var_A0], rsi
0x180024065  mov     rdi, rcx
0x180024068  mov     [rsp+0D8h+var_48], ax
0x180024070  xorps   xmm0, xmm0
0x180024073  mov     r9, r14; struct IEnumSTATSTG **
0x180024076  mov     r8d, r10d; unsigned int
0x180024079  mov     rdx, r11; void *
0x18002407c  mov     ecx, ebx; unsigned int
0x18002407e  movdqu  [rsp+0D8h+var_98], xmm0
0x180024084  call    ?EnumElements@CExpParameterValidate@@SAJKPEAXKPEAPEAUIEnumSTATSTG@@@Z; CExpParameterValidate::EnumElements(ulong,void *,ulong,IEnumSTATSTG * *)
0x180024089  mov     ebx, eax
0x18002408b  test    eax, eax
0x18002408d  js      loc_18002414C
0x180024093  mov     rcx, rdi; this
0x180024096  call    ?Validate@CExposedDocFile@@QEBAJXZ; CExposedDocFile::Validate(void)
0x18002409b  mov     ebx, eax
0x18002409d  test    eax, eax
0x18002409f  js      loc_18002414C
0x1800240a5  lea     rcx, [rsp+0D8h+var_A8]; this
0x1800240aa  call    ?Take@CSafeSem@@QEAAJXZ; CSafeSem::Take(void)
0x1800240af  mov     ebx, eax
0x1800240b1  test    eax, eax
0x1800240b3  js      loc_18002414C
0x1800240b9  mov     rax, [rdi+0A0h]
0x1800240c0  test    byte ptr [rax+14h], 40h
0x1800240c4  jz      loc_18002417C
0x1800240ca  test    byte ptr [rax+14h], 20h
0x1800240ce  jnz     loc_180024183
0x1800240d4  mov     rcx, [rdi+0A8h]
0x1800240db  mov     rax, [rsi+10h]
0x1800240df  mov     [rcx+20h], rax
0x1800240e3  mov     rax, [rsi+18h]
0x1800240e7  mov     [rcx+28h], rax
0x1800240eb  mov     rax, [rsi+20h]
0x1800240ef  mov     [rcx+30h], rax
0x1800240f3  mov     ecx, 98h; cb
0x1800240f8  call    cs:__imp_CoTaskMemAlloc
0x1800240fe  test    rax, rax
0x180024101  jz      short loc_180024175
0x180024103  mov     rcx, [rdi+0B0h]
0x18002410a  lea     r8, [rsp+0D8h+var_88]; struct CDfName *
0x18002410f  mov     r9, [rdi+0A8h]; struct CDFBasis *
0x180024116  mov     rdx, [rdi+0A0h]; struct CPubDocFile *
0x18002411d  mov     [rsp+0D8h+var_B8], rcx; struct CPerContext *
0x180024122  mov     rcx, rax; this
0x180024125  call    ??0CExposedIterator@@QEAA@PEAVCPubDocFile@@PEAVCDfName@@PEAVCDFBasis@@PEAVCPerContext@@@Z; CExposedIterator::CExposedIterator(CPubDocFile *,CDfName *,CDFBasis *,CPerContext *)
0x18002412a  mov     rsi, rax
0x18002412d  test    rax, rax
0x180024130  jz      short loc_180024175
0x180024132  mov     rcx, [rdi+0B0h]
0x180024139  xor     ebx, ebx
0x18002413b  lock inc dword ptr [rcx+38h]
0x18002413f  lea     r8, [rdi+58h]; struct CAsyncConnection *
0x180024143  cmp     [r8+10h], rbx
0x180024147  jnz     short loc_18002418A
0x180024149  mov     [r14], rsi
0x18002414c  lea     rcx, [rsp+0D8h+var_A8]; this
0x180024151  call    ?Release@CSafeSem@@QEAAXXZ; CSafeSem::Release(void)
0x180024156  mov     eax, ebx
0x180024158  mov     rcx, [rsp+0D8h+var_38]
0x180024160  xor     rcx, rsp; StackCookie
0x180024163  call    __security_check_cookie
0x180024168  add     rsp, 0B8h
0x18002416f  pop     r14
0x180024171  pop     rdi
0x180024172  pop     rsi
0x180024173  pop     rbx
0x180024174  retn
0x180024175  mov     ebx, 80030008h
0x18002417a  jmp     short loc_18002414C
0x18002417c  mov     ebx, 80030005h
0x180024181  jmp     short loc_18002414C
0x180024183  mov     ebx, 80030102h
0x180024188  jmp     short loc_18002414C
0x18002418a  lea     rdx, [rax+8]; struct IConnectionPointContainer *
0x18002418e  lea     rcx, [rdx+8]; this
0x180024192  call    ?Init@CAsyncConnection@@QEAAJPEAUIConnectionPointContainer@@PEAV1@@Z; CAsyncConnection::Init(IConnectionPointContainer *,CAsyncConnection *)
0x180024197  mov     ebx, eax
0x180024199  test    eax, eax
0x18002419b  jns     short loc_180024149
0x18002419d  mov     rax, [rsi]
0x1800241a0  mov     rcx, rsi
0x1800241a3  mov     rax, [rax+10h]
0x1800241a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241ac  mov     rax, [rsi]
0x1800241af  mov     rcx, rsi
0x1800241b2  mov     rax, [rax+10h]
0x1800241b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241bb  jmp     short loc_18002414C
```
