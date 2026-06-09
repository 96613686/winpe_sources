# ATL::CComEnumImpl<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::Init(tagVARIANT *,tagVARIANT *,IUnknown *,ATL::CComEnumFlags)

- ea: `0x1800245e0`
- end: `0x180024705`
- name: `?Init@?$CComEnumImpl@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@BUtagVARIANT@@V?$_Copy@UtagVARIANT@@@ATL@@V?$CComEnum@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@BUtagVARIANT@@V?$_Copy@UtagVARIANT@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@QEAAJPEAUtagVARIANT@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z`
- size: `293`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002443c`
- `0x180024f10`

## callees

- `0x18000173c`
- `0x18000178c`
- `0x1800095d4`
- `0x1800245e0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180024695`
- `OLEAUT32!__imp_VariantClear` at `0x180024695`
- `OLEAUT32!__imp_VariantCopy` at `0x18002466d`
- `OLEAUT32!__imp_VariantCopy` at `0x18002466d`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::Init(
        __int64 a1,
        const VARIANTARG *a2,
        __int64 a3,
        struct IUnknown *a4,
        int a5)
{
  __int64 v6; // rsi
  const VARIANTARG *v7; // rdi
  unsigned __int64 v9; // r14
  _WORD *v10; // rax
  _WORD *v11; // rcx
  __int64 result; // rax
  HRESULT v13; // ebp
  VARIANTARG *i; // rdi
  VARIANTARG *v15; // rcx

  v6 = a3;
  v7 = a2;
  if ( a5 == 3 )
  {
    v9 = 0xAAAAAAAAAAAAAAABuLL * ((a3 - (__int64)a2) >> 3);
    v10 = operator new(saturated_mul(-1431655765 * (unsigned int)((a3 - (__int64)a2) >> 3), 0x18u));
    *(_QWORD *)(a1 + 16) = v10;
    v11 = v10;
    *(_QWORD *)(a1 + 32) = v10;
    if ( v10 )
    {
      while ( 1 )
      {
        if ( v7 == (const VARIANTARG *)v6 )
        {
          v6 = *(_QWORD *)(a1 + 16) + 24 * v9;
          goto LABEL_13;
        }
        *v11 = 0;
        v13 = VariantCopy(*(VARIANTARG **)(a1 + 32), v7);
        if ( v13 < 0 )
          break;
        *(_QWORD *)(a1 + 32) += 24LL;
        v11 = *(_WORD **)(a1 + 32);
        ++v7;
      }
      for ( i = *(VARIANTARG **)(a1 + 16); (unsigned __int64)i < *(_QWORD *)(a1 + 32); ++i )
      {
        v15 = i;
        VariantClear(v15);
      }
      operator delete(*(void **)(a1 + 16));
      result = (unsigned int)v13;
      *(_QWORD *)(a1 + 32) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      *(_QWORD *)(a1 + 16) = 0;
    }
    else
    {
      return 2147942414LL;
    }
  }
  else
  {
    *(_QWORD *)(a1 + 16) = a2;
LABEL_13:
    *(_QWORD *)(a1 + 24) = v6;
    ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 8), a4);
    *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 16);
    result = 0;
    *(_DWORD *)(a1 + 40) = a5;
  }
  return result;
}

```

## disassembly

```asm
0x1800245e0  push    rbx
0x1800245e2  push    rbp
0x1800245e3  push    rsi
0x1800245e4  push    rdi
0x1800245e5  push    r12
0x1800245e7  push    r14
0x1800245e9  push    r15
0x1800245eb  sub     rsp, 20h
0x1800245ef  mov     r15d, [rsp+58h+arg_20]
0x1800245f7  mov     r12, r9
0x1800245fa  mov     rsi, r8
0x1800245fd  mov     rdi, rdx
0x180024600  mov     rbx, rcx
0x180024603  cmp     r15d, 3
0x180024607  jnz     loc_1800246D4
0x18002460d  mov     rax, 0AAAAAAAAAAAAAAABh
0x180024617  mov     r14, r8
0x18002461a  sub     r14, rdx
0x18002461d  sar     r14, 3
0x180024621  imul    r14, rax
0x180024625  lea     eax, [r15+15h]
0x180024629  mov     ecx, r14d
0x18002462c  mul     rcx
0x18002462f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180024636  cmovb   rax, rcx
0x18002463a  mov     rcx, rax; Size
0x18002463d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024642  mov     [rbx+10h], rax
0x180024646  mov     rcx, rax
0x180024649  mov     [rbx+20h], rax
0x18002464d  test    rax, rax
0x180024650  jnz     short loc_18002465C
0x180024652  mov     eax, 8007000Eh
0x180024657  jmp     loc_1800246F6
0x18002465c  cmp     rdi, rsi
0x18002465f  jz      short loc_1800246C6
0x180024661  xor     eax, eax
0x180024663  mov     rdx, rdi; pvargSrc
0x180024666  mov     [rcx], ax
0x180024669  mov     rcx, [rbx+20h]; pvargDest
0x18002466d  call    cs:__imp_VariantCopy
0x180024673  mov     ebp, eax
0x180024675  test    eax, eax
0x180024677  js      short loc_180024688
0x180024679  add     qword ptr [rbx+20h], 18h
0x18002467e  mov     rcx, [rbx+20h]
0x180024682  add     rdi, 18h
0x180024686  jmp     short loc_18002465C
0x180024688  mov     rdi, [rbx+10h]
0x18002468c  jmp     short loc_18002469B
0x18002468e  mov     rcx, rdi; pvarg
0x180024691  add     rdi, 18h
0x180024695  call    cs:__imp_VariantClear
0x18002469b  cmp     rdi, [rbx+20h]
0x18002469f  jb      short loc_18002468E
0x1800246a1  mov     rcx, [rbx+10h]; Block
0x1800246a5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800246aa  mov     eax, ebp
0x1800246ac  mov     qword ptr [rbx+20h], 0
0x1800246b4  mov     qword ptr [rbx+18h], 0
0x1800246bc  mov     qword ptr [rbx+10h], 0
0x1800246c4  jmp     short loc_1800246F6
0x1800246c6  mov     rax, [rbx+10h]
0x1800246ca  lea     rcx, [r14+r14*2]
0x1800246ce  lea     rsi, [rax+rcx*8]
0x1800246d2  jmp     short loc_1800246D8
0x1800246d4  mov     [rcx+10h], rdx
0x1800246d8  lea     rcx, [rbx+8]; struct IUnknown **
0x1800246dc  mov     [rbx+18h], rsi
0x1800246e0  mov     rdx, r12; struct IUnknown *
0x1800246e3  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800246e8  mov     rax, [rbx+10h]
0x1800246ec  mov     [rbx+20h], rax
0x1800246f0  xor     eax, eax
0x1800246f2  mov     [rbx+28h], r15d
0x1800246f6  add     rsp, 20h
0x1800246fa  pop     r15
0x1800246fc  pop     r14
0x1800246fe  pop     r12
0x180024700  pop     rdi
0x180024701  pop     rsi
0x180024702  pop     rbp
0x180024703  pop     rbx
0x180024704  retn
```
