# DispatchHelper::MarshalJsVarToVariant(void *,tagVARIANT *)

- ea: `0x180068980`
- end: `0x180068c5c`
- name: `?MarshalJsVarToVariant@DispatchHelper@@SAJPEAXPEAUtagVARIANT@@@Z`
- size: `732`
- prototype: `__int64 __fastcall(void *, struct tagVARIANT *)`
- caller_count: `9`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180067cec`
- `0x1800680f4`
- `0x18006817c`
- `0x18019bf50`
- `0x1801f4a30`
- `0x1801f7010`
- `0x1801f91d8`
- `0x1801fad2c`
- `0x180201114`

## callees

- `0x180068980`
- `0x18017f3d0`
- `0x180180650`
- `0x180199be8`
- `0x18035e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180068a4f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180068a4f`
- `OLEAUT32!__imp_VariantInit` at `0x18006899b`
- `OLEAUT32!__imp_VariantInit` at `0x18006899b`
- `OLEAUT32!__imp_VariantCopy` at `0x180068bdc`
- `OLEAUT32!__imp_VariantCopy` at `0x180068bdc`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180068b77`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180068b77`

## pseudocode

```c
__int64 __fastcall DispatchHelper::MarshalJsVarToVariant(unsigned __int64 a1, struct tagVARIANT *a2)
{
  unsigned int v3; // esi
  __int64 v4; // rdx
  int v5; // ecx
  __int64 result; // rax
  UINT v7; // ebp
  BSTR v8; // rax
  __int64 v9; // rcx
  double v10; // xmm0_8
  __int64 v11; // rax
  struct IDispatch *Dispatch; // rax
  __int64 v13; // rcx
  const VARIANTARG *v14; // rdx

  v3 = 0;
  VariantInit(a2);
  if ( !a1 )
  {
LABEL_7:
    a2->vt = 1;
    return v3;
  }
  if ( HIWORD(a1) == 1 )
  {
LABEL_5:
    a2->vt = 3;
    a2->lVal = a1;
    return v3;
  }
  if ( a1 < 0x4000000000000LL )
  {
    v5 = **(_DWORD **)(a1 + 8);
    if ( v5 != 3 )
    {
      switch ( v5 )
      {
        case 0:
          a2->vt = 0;
          return 0;
        case 1:
          goto LABEL_7;
        case 2:
          a2->vt = 11;
          result = 0;
          a2->iVal = -(*(_DWORD *)(a1 + 16) != 0);
          return result;
        case 4:
          goto LABEL_15;
        case 5:
          a2->vt = 5;
          result = 0;
          a2->dblVal = (double)(int)*(_QWORD *)(a1 + 16);
          return result;
        case 6:
          a2->vt = 5;
          v9 = *(_QWORD *)(a1 + 16);
          if ( v9 < 0 )
          {
            v11 = *(_QWORD *)(a1 + 16) & 1LL | (*(_QWORD *)(a1 + 16) >> 1);
            v10 = (double)(int)v11 + (double)(int)v11;
          }
          else
          {
            v10 = (double)(int)v9;
          }
          a2->dblVal = v10;
          return 0;
        case 7:
          if ( a1 == *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 3224LL) )
          {
            a2->llVal = 0;
            result = 0;
            a2->vt = 8;
          }
          else
          {
            v7 = *(_DWORD *)(a1 + 16);
            if ( !*(_QWORD *)(a1 + 24) )
              (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)a1 + 704LL))(a1);
            v8 = SysAllocStringLen(*(const OLECHAR **)(a1 + 24), v7);
            a2->llVal = (LONGLONG)v8;
            a2->vt = 8;
            if ( !v8 )
              return (unsigned int)-2147024882;
            return v3;
          }
          return result;
        case 9:
          v3 = SafeArrayCopy(*(SAFEARRAY **)(a1 + 24), &a2->parray);
          if ( (v3 & 0x80000000) == 0 )
            a2->vt = *(_WORD *)(a1 + 16);
          return v3;
        case 10:
          a2->vt = 7;
          a2->llVal = *(_QWORD *)(a1 + 16);
          return v3;
        case 11:
          Dispatch = HostDispatch::GetDispatch((HostDispatch *)a1);
          if ( Dispatch )
          {
            a2->vt = 9;
            a2->llVal = (LONGLONG)Dispatch;
          }
          else
          {
            v13 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL);
            v14 = (const VARIANTARG *)(v13 + 16);
            if ( !v13 )
              v14 = 0;
            if ( v14 )
              return (unsigned int)VariantCopy(a2, v14);
            else
              return (unsigned int)MapHr(-2147024891, 0);
          }
          return v3;
        case 12:
        case 13:
        case 14:
        case 16:
        case 17:
        case 18:
        case 19:
        case 20:
        case 21:
        case 22:
        case 23:
        case 24:
        case 25:
        case 26:
        case 27:
        case 28:
        case 29:
        case 30:
        case 32:
        case 33:
        case 34:
        case 35:
        case 36:
        case 37:
        case 38:
        case 39:
        case 40:
        case 41:
        case 42:
        case 43:
        case 44:
        case 45:
        case 46:
        case 47:
        case 48:
        case 49:
        case 51:
          goto LABEL_24;
        default:
          if ( (*(unsigned int (__fastcall **)(unsigned __int64, __int64))(*(_QWORD *)a1 + 504LL))(a1, v4) )
          {
LABEL_24:
            DispatchHelper::MarshalJsVarToDispatchVariant((void *)a1, a2);
            return 0;
          }
          v3 = -2147467263;
          break;
      }
      return v3;
    }
    goto LABEL_5;
  }
LABEL_15:
  a2->vt = 5;
  result = 0;
  a2->llVal = a1 ^ 0xFFFC000000000000uLL;
  return result;
}

```

## disassembly

```asm
0x180068980  mov     [rsp+pvarg], rdx
0x180068985  mov     [rsp+arg_0], rcx
0x18006898a  push    rbx
0x18006898b  push    rsi
0x18006898c  push    rdi
0x18006898d  sub     rsp, 20h
0x180068991  mov     rdi, [rsp+38h+pvarg]
0x180068996  xor     esi, esi
0x180068998  mov     rcx, rdi; pvarg
0x18006899b  call    cs:__imp_VariantInit
0x1800689a1  mov     rbx, [rsp+38h+arg_0]
0x1800689a6  test    rbx, rbx
0x1800689a9  jz      short loc_1800689E9; jumptable 0000000180068A12 case 1
0x1800689ab  mov     rax, rbx
0x1800689ae  shr     rax, 30h
0x1800689b2  cmp     rax, 1
0x1800689b6  jz      short loc_1800689D7
0x1800689b8  mov     rax, 4000000000000h
0x1800689c2  cmp     rbx, rax
0x1800689c5  jnb     loc_180068A78; jumptable 0000000180068A12 case 4
0x1800689cb  mov     rax, [rbx+8]
0x1800689cf  movsxd  rcx, dword ptr [rax]
0x1800689d2  cmp     ecx, 3
0x1800689d5  jnz     short loc_1800689F0
0x1800689d7  mov     word ptr [rdi], 3
0x1800689dc  mov     [rdi+8], ebx
0x1800689df  mov     eax, esi
0x1800689e1  add     rsp, 20h
0x1800689e5  pop     rdi
0x1800689e6  pop     rsi
0x1800689e7  pop     rbx
0x1800689e8  retn
0x1800689e9  mov     word ptr [rdi], 1; jumptable 0000000180068A12 case 1
0x1800689ee  jmp     short loc_1800689DF
0x1800689f0  cmp     ecx, 33h; switch 52 cases
0x1800689f3  ja      def_180068A12; jumptable 0000000180068A12 default case, cases 3,8,15,31,50
0x1800689f9  lea     rdx, __ImageBase
0x180068a00  movzx   eax, ds:(byte_180068C28 - 180000000h)[rdx+rcx]
0x180068a08  mov     ecx, ds:(jpt_180068A12 - 180000000h)[rdx+rax*4]
0x180068a0f  add     rcx, rdx
0x180068a12  jmp     rcx; switch jump
0x180068a14  mov     rax, [rbx+8]; jumptable 0000000180068A12 case 7
0x180068a18  mov     rcx, [rax+8]
0x180068a1c  cmp     rbx, [rcx+0C98h]
0x180068a23  jz      loc_180068AC4
0x180068a29  mov     [rsp+38h+arg_10], rbp
0x180068a2e  mov     ebp, [rbx+10h]
0x180068a31  cmp     [rbx+18h], rsi
0x180068a35  jnz     short loc_180068A49
0x180068a37  mov     rax, [rbx]
0x180068a3a  mov     rcx, rbx
0x180068a3d  mov     rax, [rax+2C0h]
0x180068a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068a49  mov     rcx, [rbx+18h]; strIn
0x180068a4d  mov     edx, ebp; ui
0x180068a4f  call    cs:__imp_SysAllocStringLen
0x180068a55  mov     rbp, [rsp+38h+arg_10]
0x180068a5a  mov     ecx, 8007000Eh
0x180068a5f  test    rax, rax
0x180068a62  mov     [rdi+8], rax
0x180068a66  mov     word ptr [rdi], 8
0x180068a6b  cmovz   esi, ecx
0x180068a6e  mov     eax, esi
0x180068a70  add     rsp, 20h
0x180068a74  pop     rdi
0x180068a75  pop     rsi
0x180068a76  pop     rbx
0x180068a77  retn
0x180068a78  mov     rax, 0FFFC000000000000h; jumptable 0000000180068A12 case 4
0x180068a82  mov     word ptr [rdi], 5
0x180068a87  xor     rbx, rax
0x180068a8a  mov     eax, esi
0x180068a8c  mov     [rdi+8], rbx
0x180068a90  add     rsp, 20h
0x180068a94  pop     rdi
0x180068a95  pop     rsi
0x180068a96  pop     rbx
0x180068a97  retn
0x180068a98  xor     eax, eax; jumptable 0000000180068A12 case 0
0x180068a9a  mov     [rdi], ax
0x180068a9d  mov     eax, esi
0x180068a9f  add     rsp, 20h
0x180068aa3  pop     rdi
0x180068aa4  pop     rsi
0x180068aa5  pop     rbx
0x180068aa6  retn
0x180068aa7  xorps   xmm0, xmm0; jumptable 0000000180068A12 case 5
0x180068aaa  mov     word ptr [rdi], 5
0x180068aaf  cvtsi2sd xmm0, qword ptr [rbx+10h]
0x180068ab5  mov     eax, esi
0x180068ab7  movsd   qword ptr [rdi+8], xmm0
0x180068abc  add     rsp, 20h
0x180068ac0  pop     rdi
0x180068ac1  pop     rsi
0x180068ac2  pop     rbx
0x180068ac3  retn
0x180068ac4  mov     [rdi+8], rsi
0x180068ac8  mov     eax, esi
0x180068aca  mov     word ptr [rdi], 8
0x180068acf  add     rsp, 20h
0x180068ad3  pop     rdi
0x180068ad4  pop     rsi
0x180068ad5  pop     rbx
0x180068ad6  retn
0x180068ad7  mov     word ptr [rdi], 5; jumptable 0000000180068A12 case 6
0x180068adc  xorps   xmm0, xmm0
0x180068adf  mov     rcx, [rbx+10h]
0x180068ae3  test    rcx, rcx
0x180068ae6  js      short loc_180068B46
0x180068ae8  cvtsi2sd xmm0, rcx
0x180068aed  movsd   qword ptr [rdi+8], xmm0
0x180068af2  mov     eax, esi
0x180068af4  add     rsp, 20h
0x180068af8  pop     rdi
0x180068af9  pop     rsi
0x180068afa  pop     rbx
0x180068afb  retn
0x180068afc  mov     word ptr [rdi], 0Bh; jumptable 0000000180068A12 case 2
0x180068b01  mov     eax, [rbx+10h]
0x180068b04  neg     eax
0x180068b06  mov     eax, esi
0x180068b08  sbb     cx, cx
0x180068b0b  mov     [rdi+8], cx
0x180068b0f  add     rsp, 20h
0x180068b13  pop     rdi
0x180068b14  pop     rsi
0x180068b15  pop     rbx
0x180068b16  retn
0x180068b17  mov     rax, [rbx]; jumptable 0000000180068A12 default case, cases 3,8,15,31,50
0x180068b1a  mov     rcx, rbx
0x180068b1d  mov     rax, [rax+1F8h]
0x180068b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068b29  test    eax, eax
0x180068b2b  jz      loc_180068BE9
0x180068b31  mov     rdx, rdi; jumptable 0000000180068A12 cases 12-14,16-30,32-49,51
0x180068b34  mov     rcx, rbx; void *
0x180068b37  call    ?MarshalJsVarToDispatchVariant@DispatchHelper@@CAXPEAXPEAUtagVARIANT@@@Z; DispatchHelper::MarshalJsVarToDispatchVariant(void *,tagVARIANT *)
0x180068b3c  mov     eax, esi
0x180068b3e  add     rsp, 20h
0x180068b42  pop     rdi
0x180068b43  pop     rsi
0x180068b44  pop     rbx
0x180068b45  retn
0x180068b46  mov     rax, rcx
0x180068b49  and     ecx, 1
0x180068b4c  shr     rax, 1
0x180068b4f  or      rax, rcx
0x180068b52  cvtsi2sd xmm0, rax
0x180068b57  addsd   xmm0, xmm0
0x180068b5b  jmp     short loc_180068AED
0x180068b5d  mov     word ptr [rdi], 7; jumptable 0000000180068A12 case 10
0x180068b62  mov     rax, [rbx+10h]
0x180068b66  mov     [rdi+8], rax
0x180068b6a  jmp     loc_1800689DF
0x180068b6f  mov     rcx, [rbx+18h]; jumptable 0000000180068A12 case 9
0x180068b73  lea     rdx, [rdi+8]; ppsaOut
0x180068b77  call    cs:__imp_SafeArrayCopy
0x180068b7d  mov     esi, eax
0x180068b7f  test    eax, eax
0x180068b81  js      loc_1800689DF
0x180068b87  movzx   ecx, word ptr [rbx+10h]
0x180068b8b  mov     [rdi], cx
0x180068b8e  jmp     loc_1800689DF
0x180068b93  mov     rcx, rbx; jumptable 0000000180068A12 case 11
0x180068b96  call    ?GetDispatch@HostDispatch@@QEAAPEAUIDispatch@@XZ; HostDispatch::GetDispatch(void)
0x180068b9b  test    rax, rax
0x180068b9e  jz      short loc_180068BAE
0x180068ba0  mov     word ptr [rdi], 9
0x180068ba5  mov     [rdi+8], rax
0x180068ba9  jmp     loc_1800689DF
0x180068bae  mov     rax, [rbx+18h]
0x180068bb2  mov     rcx, [rax+10h]
0x180068bb6  xor     eax, eax
0x180068bb8  test    rcx, rcx
0x180068bbb  lea     rdx, [rcx+10h]
0x180068bbf  cmovz   rdx, rax; enum ErrorTypeEnum *
0x180068bc3  test    rdx, rdx
0x180068bc6  jnz     short loc_180068BD9
0x180068bc8  mov     ecx, 80070005h; int
0x180068bcd  call    ?MapHr@@YAJJPEAW4ErrorTypeEnum@@@Z; MapHr(long,ErrorTypeEnum *)
0x180068bd2  mov     esi, eax
0x180068bd4  jmp     loc_1800689DF
0x180068bd9  mov     rcx, rdi; pvargDest
0x180068bdc  call    cs:__imp_VariantCopy
0x180068be2  mov     esi, eax
0x180068be4  jmp     loc_1800689DF
0x180068be9  mov     esi, 80004001h
0x180068bee  jmp     loc_1800689DF
```
