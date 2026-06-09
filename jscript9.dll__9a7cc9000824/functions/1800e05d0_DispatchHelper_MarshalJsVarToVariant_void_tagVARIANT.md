# DispatchHelper::MarshalJsVarToVariant(void *,tagVARIANT *)

- ea: `0x1800e05d0`
- end: `0x1800e08d0`
- name: `?MarshalJsVarToVariant@DispatchHelper@@SAJPEAXPEAUtagVARIANT@@@Z`
- size: `768`
- prototype: `__int64 __fastcall(unsigned __int64, struct tagVARIANT *)`
- caller_count: `9`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800df8a0`
- `0x1800dfce4`
- `0x1800dfd74`
- `0x18019dfa0`
- `0x1801f7f70`
- `0x1801fa5f0`
- `0x1801fc808`
- `0x1801fe37c`
- `0x180204494`

## callees

- `0x1800e05d0`
- `0x18017fac8`
- `0x180181384`
- `0x18019bca4`
- `0x180364010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800e06aa`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800e06aa`
- `OLEAUT32!__imp_VariantInit` at `0x1800e05eb`
- `OLEAUT32!__imp_VariantInit` at `0x1800e05eb`
- `OLEAUT32!__imp_VariantCopy` at `0x1800e084b`
- `OLEAUT32!__imp_VariantCopy` at `0x1800e084b`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800e07e0`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800e07e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x1800e05d0  mov     [rsp+pvarg], rdx
0x1800e05d5  mov     [rsp+arg_0], rcx
0x1800e05da  push    rbx
0x1800e05db  push    rsi
0x1800e05dc  push    rdi
0x1800e05dd  sub     rsp, 20h
0x1800e05e1  mov     rdi, [rsp+38h+pvarg]
0x1800e05e6  xor     esi, esi
0x1800e05e8  mov     rcx, rdi; pvarg
0x1800e05eb  call    cs:__imp_VariantInit
0x1800e05f2  nop     dword ptr [rax+rax+00h]
0x1800e05f7  mov     rbx, [rsp+38h+arg_0]
0x1800e05fc  test    rbx, rbx
0x1800e05ff  jz      short loc_1800E0640; jumptable 00000001800E0669 case 1
0x1800e0601  mov     rax, rbx
0x1800e0604  shr     rax, 30h
0x1800e0608  cmp     rax, 1
0x1800e060c  jz      short loc_1800E062D
0x1800e060e  mov     rax, 4000000000000h
0x1800e0618  cmp     rbx, rax
0x1800e061b  jnb     loc_1800E06DA; jumptable 00000001800E0669 case 4
0x1800e0621  mov     rax, [rbx+8]
0x1800e0625  movsxd  rcx, dword ptr [rax]
0x1800e0628  cmp     ecx, 3
0x1800e062b  jnz     short loc_1800E0647
0x1800e062d  mov     word ptr [rdi], 3
0x1800e0632  mov     [rdi+8], ebx
0x1800e0635  mov     eax, esi
0x1800e0637  add     rsp, 20h
0x1800e063b  pop     rdi
0x1800e063c  pop     rsi
0x1800e063d  pop     rbx
0x1800e063e  retn
0x1800e0640  mov     word ptr [rdi], 1; jumptable 00000001800E0669 case 1
0x1800e0645  jmp     short loc_1800E0635
0x1800e0647  cmp     ecx, 33h; switch 52 cases
0x1800e064a  ja      def_1800E0669; jumptable 00000001800E0669 default case, cases 3,8,15,31,50
0x1800e0650  lea     rdx, __ImageBase
0x1800e0657  movzx   eax, ds:(byte_1800E089C - 180000000h)[rdx+rcx]
0x1800e065f  mov     ecx, ds:(jpt_1800E0669 - 180000000h)[rdx+rax*4]
0x1800e0666  add     rcx, rdx
0x1800e0669  jmp     rcx; switch jump
0x1800e066f  mov     rax, [rbx+8]; jumptable 00000001800E0669 case 7
0x1800e0673  mov     rcx, [rax+8]
0x1800e0677  cmp     rbx, [rcx+0C98h]
0x1800e067e  jz      loc_1800E0729
0x1800e0684  mov     [rsp+38h+arg_10], rbp
0x1800e0689  mov     ebp, [rbx+10h]
0x1800e068c  cmp     [rbx+18h], rsi
0x1800e0690  jnz     short loc_1800E06A4
0x1800e0692  mov     rax, [rbx]
0x1800e0695  mov     rcx, rbx
0x1800e0698  mov     rax, [rax+2C0h]
0x1800e069f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e06a4  mov     rcx, [rbx+18h]; strIn
0x1800e06a8  mov     edx, ebp; ui
0x1800e06aa  call    cs:__imp_SysAllocStringLen
0x1800e06b1  nop     dword ptr [rax+rax+00h]
0x1800e06b6  mov     rbp, [rsp+38h+arg_10]
0x1800e06bb  mov     ecx, 8007000Eh
0x1800e06c0  test    rax, rax
0x1800e06c3  mov     [rdi+8], rax
0x1800e06c7  mov     word ptr [rdi], 8
0x1800e06cc  cmovz   esi, ecx
0x1800e06cf  mov     eax, esi
0x1800e06d1  add     rsp, 20h
0x1800e06d5  pop     rdi
0x1800e06d6  pop     rsi
0x1800e06d7  pop     rbx
0x1800e06d8  retn
0x1800e06da  mov     rax, 0FFFC000000000000h; jumptable 00000001800E0669 case 4
0x1800e06e4  mov     word ptr [rdi], 5
0x1800e06e9  xor     rbx, rax
0x1800e06ec  mov     eax, esi
0x1800e06ee  mov     [rdi+8], rbx
0x1800e06f2  add     rsp, 20h
0x1800e06f6  pop     rdi
0x1800e06f7  pop     rsi
0x1800e06f8  pop     rbx
0x1800e06f9  retn
0x1800e06fb  xor     eax, eax; jumptable 00000001800E0669 case 0
0x1800e06fd  mov     [rdi], ax
0x1800e0700  mov     eax, esi
0x1800e0702  add     rsp, 20h
0x1800e0706  pop     rdi
0x1800e0707  pop     rsi
0x1800e0708  pop     rbx
0x1800e0709  retn
0x1800e070b  xorps   xmm0, xmm0; jumptable 00000001800E0669 case 5
0x1800e070e  mov     word ptr [rdi], 5
0x1800e0713  cvtsi2sd xmm0, qword ptr [rbx+10h]
0x1800e0719  mov     eax, esi
0x1800e071b  movsd   qword ptr [rdi+8], xmm0
0x1800e0720  add     rsp, 20h
0x1800e0724  pop     rdi
0x1800e0725  pop     rsi
0x1800e0726  pop     rbx
0x1800e0727  retn
0x1800e0729  mov     [rdi+8], rsi
0x1800e072d  mov     eax, esi
0x1800e072f  mov     word ptr [rdi], 8
0x1800e0734  add     rsp, 20h
0x1800e0738  pop     rdi
0x1800e0739  pop     rsi
0x1800e073a  pop     rbx
0x1800e073b  retn
0x1800e073d  mov     word ptr [rdi], 5; jumptable 00000001800E0669 case 6
0x1800e0742  xorps   xmm0, xmm0
0x1800e0745  mov     rcx, [rbx+10h]
0x1800e0749  test    rcx, rcx
0x1800e074c  js      short loc_1800E07AF
0x1800e074e  cvtsi2sd xmm0, rcx
0x1800e0753  movsd   qword ptr [rdi+8], xmm0
0x1800e0758  mov     eax, esi
0x1800e075a  add     rsp, 20h
0x1800e075e  pop     rdi
0x1800e075f  pop     rsi
0x1800e0760  pop     rbx
0x1800e0761  retn
0x1800e0763  mov     word ptr [rdi], 0Bh; jumptable 00000001800E0669 case 2
0x1800e0768  mov     eax, [rbx+10h]
0x1800e076b  neg     eax
0x1800e076d  mov     eax, esi
0x1800e076f  sbb     cx, cx
0x1800e0772  mov     [rdi+8], cx
0x1800e0776  add     rsp, 20h
0x1800e077a  pop     rdi
0x1800e077b  pop     rsi
0x1800e077c  pop     rbx
0x1800e077d  retn
0x1800e077f  mov     rax, [rbx]; jumptable 00000001800E0669 default case, cases 3,8,15,31,50
0x1800e0782  mov     rcx, rbx
0x1800e0785  mov     rax, [rax+1F8h]
0x1800e078c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0791  test    eax, eax
0x1800e0793  jz      loc_1800E085E
0x1800e0799  mov     rdx, rdi; jumptable 00000001800E0669 cases 12-14,16-30,32-49,51
0x1800e079c  mov     rcx, rbx; void *
0x1800e079f  call    ?MarshalJsVarToDispatchVariant@DispatchHelper@@CAXPEAXPEAUtagVARIANT@@@Z; DispatchHelper::MarshalJsVarToDispatchVariant(void *,tagVARIANT *)
0x1800e07a4  mov     eax, esi
0x1800e07a6  add     rsp, 20h
0x1800e07aa  pop     rdi
0x1800e07ab  pop     rsi
0x1800e07ac  pop     rbx
0x1800e07ad  retn
0x1800e07af  mov     rax, rcx
0x1800e07b2  and     ecx, 1
0x1800e07b5  shr     rax, 1
0x1800e07b8  or      rax, rcx
0x1800e07bb  cvtsi2sd xmm0, rax
0x1800e07c0  addsd   xmm0, xmm0
0x1800e07c4  jmp     short loc_1800E0753
0x1800e07c6  mov     word ptr [rdi], 7; jumptable 00000001800E0669 case 10
0x1800e07cb  mov     rax, [rbx+10h]
0x1800e07cf  mov     [rdi+8], rax
0x1800e07d3  jmp     loc_1800E0635
0x1800e07d8  mov     rcx, [rbx+18h]; jumptable 00000001800E0669 case 9
0x1800e07dc  lea     rdx, [rdi+8]; ppsaOut
0x1800e07e0  call    cs:__imp_SafeArrayCopy
0x1800e07e7  nop     dword ptr [rax+rax+00h]
0x1800e07ec  mov     esi, eax
0x1800e07ee  test    eax, eax
0x1800e07f0  js      loc_1800E0635
0x1800e07f6  movzx   ecx, word ptr [rbx+10h]
0x1800e07fa  mov     [rdi], cx
0x1800e07fd  jmp     loc_1800E0635
0x1800e0802  mov     rcx, rbx; jumptable 00000001800E0669 case 11
0x1800e0805  call    ?GetDispatch@HostDispatch@@QEAAPEAUIDispatch@@XZ; HostDispatch::GetDispatch(void)
0x1800e080a  test    rax, rax
0x1800e080d  jz      short loc_1800E081D
0x1800e080f  mov     word ptr [rdi], 9
0x1800e0814  mov     [rdi+8], rax
0x1800e0818  jmp     loc_1800E0635
0x1800e081d  mov     rax, [rbx+18h]
0x1800e0821  mov     rcx, [rax+10h]
0x1800e0825  xor     eax, eax
0x1800e0827  test    rcx, rcx
0x1800e082a  lea     rdx, [rcx+10h]
0x1800e082e  cmovz   rdx, rax; enum ErrorTypeEnum *
0x1800e0832  test    rdx, rdx
0x1800e0835  jnz     short loc_1800E0848
0x1800e0837  mov     ecx, 80070005h; int
0x1800e083c  call    ?MapHr@@YAJJPEAW4ErrorTypeEnum@@@Z; MapHr(long,ErrorTypeEnum *)
0x1800e0841  mov     esi, eax
0x1800e0843  jmp     loc_1800E0635
0x1800e0848  mov     rcx, rdi; pvargDest
0x1800e084b  call    cs:__imp_VariantCopy
0x1800e0852  nop     dword ptr [rax+rax+00h]
0x1800e0857  mov     esi, eax
0x1800e0859  jmp     loc_1800E0635
0x1800e085e  mov     esi, 80004001h
0x1800e0863  jmp     loc_1800E0635
```
