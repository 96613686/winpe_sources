# CNamedArguments::Create(long,ushort const * *,CNamedArguments * *)

- ea: `0x140013904`
- end: `0x140013bf1`
- name: `?Create@CNamedArguments@@SAJJPEAPEBGPEAPEAV1@@Z`
- size: `749`
- prototype: `__int64 __fastcall(int, const unsigned __int16 **, struct CNamedArguments **)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140007580`

## callees

- `0x140009c70`
- `0x140013904`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140013b47`
- `OLEAUT32!__imp_SysAllocString` at `0x140013b47`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140013acd`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140013acd`
- `OLEAUT32!__imp_VariantClear` at `0x140013b06`
- `OLEAUT32!__imp_VariantClear` at `0x140013b9c`
- `OLEAUT32!__imp_VariantClear` at `0x140013b06`
- `OLEAUT32!__imp_VariantClear` at `0x140013b9c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140013a08`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140013a24`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140013a08`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140013a24`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x140013afa`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x140013b90`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x140013afa`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x140013b90`

## pseudocode

```c
__int64 __fastcall CNamedArguments::Create(int a1, const unsigned __int16 **a2, SAFEARRAY ***a3)
{
  const unsigned __int16 **v4; // rbx
  SAFEARRAY **v5; // rax
  SAFEARRAY **v6; // rdi
  signed int v7; // r14d
  __int64 v8; // rdx
  int v9; // eax
  SAFEARRAY *v10; // rax
  SAFEARRAY *v11; // rax
  LONG v12; // ecx
  int i; // r12d
  const unsigned __int16 *v14; // rdx
  const OLECHAR *v15; // r9
  UINT v16; // r8d
  unsigned __int16 v17; // cx
  const OLECHAR *v18; // r15
  int v19; // esi
  unsigned __int16 *v20; // rdx
  HRESULT v21; // ebx
  int v22; // esi
  SHORT v23; // ax
  SAFEARRAYBOUND rgsabound; // [rsp+20h] [rbp-30h] BYREF
  BSTR v26; // [rsp+28h] [rbp-28h]
  VARIANTARG pv; // [rsp+30h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+A8h] [rbp+58h] BYREF

  rgsabound = 0;
  rgIndices = 0;
  v4 = a2;
  memset(&pv, 0, sizeof(pv));
  v5 = (SAFEARRAY **)operator new(0x58u);
  v6 = v5;
  if ( v5 )
  {
    v5[2] = (SAFEARRAY *)&CUnknown::`vftable';
    v5[5] = (SAFEARRAY *)&CUnknown::InnerUnknown::`vftable';
    *((_DWORD *)v5 + 12) = 1;
    v5[3] = (SAFEARRAY *)(v5 + 5);
    v5[4] = (SAFEARRAY *)v5;
    _InterlockedAdd(&Global::g_cObjects, 1u);
    *((_BYTE *)v5 + 64) = 0;
    v5[7] = (SAFEARRAY *)&TaUser_DescCNamedArguments;
    v5[9] = 0;
    *v5 = (SAFEARRAY *)&CNamedArguments::`vftable'{for `IWSHNamedArguments'};
    v7 = 0;
    v5[10] = 0;
    v5[1] = (SAFEARRAY *)&CUnnamedArguments::`vftable'{for `IProvideClassInfo'};
    v8 = 0;
    for ( v5[2] = (SAFEARRAY *)&CNamedArguments::`vftable'{for `CDispatch'}; (int)v8 < a1; v7 = v9 )
    {
      v9 = v7 + 1;
      if ( *v4[v8] != 47 )
        v9 = v7;
      v8 = (unsigned int)(v8 + 1);
    }
    rgsabound.lLbound = 0;
    rgsabound.cElements = v7;
    v10 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    v6[9] = v10;
    if ( v10 && (v11 = SafeArrayCreate(0xCu, 1u, &rgsabound), (v6[10] = v11) != 0) )
    {
      v12 = 0;
      rgIndices = 0;
      for ( i = 0; i < a1 && v12 < v7; ++i )
      {
        v14 = v4[i];
        if ( *v14 == 47 )
        {
          v15 = v14 + 1;
          v16 = 0;
          v17 = v14[1];
          v18 = v14 + 1;
          v19 = 0;
          while ( v17 )
          {
            v20 = (unsigned __int16 *)(v18 + 1);
            if ( v17 == 58 )
            {
              v19 = 1;
              ++v18;
              break;
            }
            if ( !*v20 && ((v17 - 43) & 0xFFFD) == 0 )
            {
              v19 = 2;
              break;
            }
            v17 = *v20;
            ++v16;
            ++v18;
          }
          pv.vt = 8;
          v26 = SysAllocStringLen(v15, v16);
          pv.llVal = (LONGLONG)v26;
          if ( !v26 )
            goto LABEL_30;
          v21 = SafeArrayPutElement(v6[9], &rgIndices, &pv);
          VariantClear(&pv);
          if ( v21 < 0 )
            goto LABEL_31;
          if ( v19 )
          {
            v22 = v19 - 1;
            if ( v22 )
            {
              if ( v22 == 1 )
              {
                pv.vt = 11;
                if ( *v18 == 43 )
                  v23 = -1;
                else
                  v23 = 0;
                pv.iVal = v23;
              }
            }
            else
            {
              pv.vt = 8;
              v26 = SysAllocString(v18);
              pv.llVal = (LONGLONG)v26;
              if ( !v26 )
                goto LABEL_30;
            }
          }
          else
          {
            pv.vt = 0;
          }
          v21 = SafeArrayPutElement(v6[10], &rgIndices, &pv);
          VariantClear(&pv);
          if ( v21 < 0 )
            goto LABEL_31;
          v4 = a2;
          v12 = ++rgIndices;
        }
      }
      v21 = 0;
      *a3 = v6;
    }
    else
    {
LABEL_30:
      v21 = -2147024882;
LABEL_31:
      ((void (__fastcall *)(SAFEARRAY **))(*v6)->pvData)(v6);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x140013904  mov     [rsp-38h+arg_0], rbx
0x140013909  mov     [rsp-38h+arg_10], r8
0x14001390e  mov     [rsp-38h+arg_8], rdx
0x140013913  push    rbp
0x140013914  push    rsi
0x140013915  push    rdi
0x140013916  push    r12
0x140013918  push    r13
0x14001391a  push    r14
0x14001391c  push    r15
0x14001391e  mov     rbp, rsp
0x140013921  sub     rsp, 50h
0x140013925  xor     eax, eax
0x140013927  mov     qword ptr [rbp+rgsabound.cElements], 0
0x14001392f  mov     r13d, ecx
0x140013932  mov     [rbp+var_10], rax
0x140013936  xorps   xmm0, xmm0
0x140013939  mov     [rbp+rgIndices], eax
0x14001393c  mov     rbx, rdx
0x14001393f  lea     ecx, [rax+58h]; Size
0x140013942  movups  [rbp+pv], xmm0
0x140013946  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001394b  mov     rdi, rax
0x14001394e  test    rax, rax
0x140013951  jz      loc_140013BD2
0x140013957  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x14001395e  mov     esi, 1
0x140013963  mov     [rdi+10h], rax
0x140013967  lea     rcx, ??_7InnerUnknown@CUnknown@@6B@; const CUnknown::InnerUnknown::`vftable'
0x14001396e  lea     rax, [rdi+28h]
0x140013972  mov     [rax], rcx
0x140013975  mov     [rax+8], esi
0x140013978  mov     [rdi+18h], rax
0x14001397c  mov     [rdi+20h], rdi
0x140013980  lock add cs:?g_cObjects@Global@@2JA, esi; long Global::g_cObjects
0x140013987  mov     byte ptr [rdi+40h], 0
0x14001398b  lea     rax, ?TaUser_DescCNamedArguments@@3UTaDescDispatch@@A; TaDescDispatch TaUser_DescCNamedArguments
0x140013992  mov     [rdi+38h], rax
0x140013996  lea     r8d, [rsi+2Eh]
0x14001399a  lea     rax, ??_7CNamedArguments@@6BIWSHNamedArguments@@@; const CNamedArguments::`vftable'{for `IWSHNamedArguments'}
0x1400139a1  mov     qword ptr [rdi+48h], 0
0x1400139a9  mov     [rdi], rax
0x1400139ac  xor     r14d, r14d
0x1400139af  lea     rax, ??_7CUnnamedArguments@@6BIProvideClassInfo@@@; const CUnnamedArguments::`vftable'{for `IProvideClassInfo'}
0x1400139b6  mov     qword ptr [rdi+50h], 0
0x1400139be  mov     [rdi+8], rax
0x1400139c2  xor     edx, edx
0x1400139c4  lea     rax, ??_7CNamedArguments@@6BCDispatch@@@; const CNamedArguments::`vftable'{for `CDispatch'}
0x1400139cb  mov     [rdi+10h], rax
0x1400139cf  test    r13d, r13d
0x1400139d2  jle     short loc_1400139EE
0x1400139d4  mov     rcx, [rbx+rdx*8]
0x1400139d8  lea     eax, [r14+1]
0x1400139dc  cmp     r8w, [rcx]
0x1400139e0  cmovnz  eax, r14d
0x1400139e4  add     edx, esi
0x1400139e6  mov     r14d, eax
0x1400139e9  cmp     edx, r13d
0x1400139ec  jl      short loc_1400139D4
0x1400139ee  mov     r15d, 0Ch
0x1400139f4  mov     [rbp+rgsabound.lLbound], 0
0x1400139fb  mov     ecx, r15d; vt
0x1400139fe  mov     [rbp+rgsabound.cElements], r14d
0x140013a02  lea     r8, [rbp+rgsabound]; rgsabound
0x140013a06  mov     edx, esi; cDims
0x140013a08  call    cs:__imp_SafeArrayCreate
0x140013a0e  mov     [rdi+48h], rax
0x140013a12  test    rax, rax
0x140013a15  jz      loc_140013B68
0x140013a1b  mov     ecx, r15d; vt
0x140013a1e  lea     r8, [rbp+rgsabound]; rgsabound
0x140013a22  mov     edx, esi; cDims
0x140013a24  call    cs:__imp_SafeArrayCreate
0x140013a2a  mov     [rdi+50h], rax
0x140013a2e  test    rax, rax
0x140013a31  jz      loc_140013B68
0x140013a37  xor     ecx, ecx
0x140013a39  lea     r10d, [r15+1Fh]
0x140013a3d  mov     [rbp+rgIndices], ecx
0x140013a40  lea     r11d, [r15-4]
0x140013a44  xor     r12d, r12d
0x140013a47  cmp     r12d, r13d
0x140013a4a  jge     loc_140013BC7
0x140013a50  cmp     ecx, r14d
0x140013a53  jge     loc_140013BC7
0x140013a59  movsxd  rax, r12d
0x140013a5c  mov     rdx, [rbx+rax*8]
0x140013a60  mov     eax, 2Fh ; '/'
0x140013a65  cmp     ax, [rdx]
0x140013a68  jnz     loc_140013BBF
0x140013a6e  lea     r9, [rdx+2]
0x140013a72  xor     r8d, r8d
0x140013a75  movzx   ecx, word ptr [r9]
0x140013a79  mov     r15, r9
0x140013a7c  xor     esi, esi
0x140013a7e  xor     eax, eax
0x140013a80  cmp     ax, cx
0x140013a83  jz      short loc_140013AC2
0x140013a85  mov     eax, 3Ah ; ':'
0x140013a8a  lea     rdx, [r15+2]
0x140013a8e  cmp     ax, cx
0x140013a91  jz      short loc_140013ABA
0x140013a93  xor     eax, eax
0x140013a95  cmp     ax, [rdx]
0x140013a98  jnz     short loc_140013AA8
0x140013a9a  sub     cx, r10w
0x140013a9e  mov     eax, 0FFFDh
0x140013aa3  test    ax, cx
0x140013aa6  jz      short loc_140013AB3
0x140013aa8  movzx   ecx, word ptr [rdx]
0x140013aab  inc     r8d
0x140013aae  mov     r15, rdx
0x140013ab1  jmp     short loc_140013A7E
0x140013ab3  mov     esi, 2
0x140013ab8  jmp     short loc_140013AC2
0x140013aba  mov     esi, 1
0x140013abf  mov     r15, rdx
0x140013ac2  mov     edx, r8d; ui
0x140013ac5  mov     word ptr [rbp+pv], r11w
0x140013aca  mov     rcx, r9; strIn
0x140013acd  call    cs:__imp_SysAllocStringLen
0x140013ad3  mov     [rbp+var_28], rax
0x140013ad7  mov     ecx, dword ptr [rbp+var_28+2]
0x140013ada  mov     dword ptr [rbp+pv+0Ah], ecx
0x140013add  movzx   ecx, word ptr [rbp+var_28+6]
0x140013ae1  mov     word ptr [rbp+pv+0Eh], cx
0x140013ae5  mov     word ptr [rbp+pv+8], ax
0x140013ae9  test    rax, rax
0x140013aec  jz      short loc_140013B68
0x140013aee  mov     rcx, [rdi+48h]; psa
0x140013af2  lea     r8, [rbp+pv]; pv
0x140013af6  lea     rdx, [rbp+rgIndices]; rgIndices
0x140013afa  call    cs:__imp_SafeArrayPutElement
0x140013b00  lea     rcx, [rbp+pv]; pvarg
0x140013b04  mov     ebx, eax
0x140013b06  call    cs:__imp_VariantClear
0x140013b0c  test    ebx, ebx
0x140013b0e  js      short loc_140013B6D
0x140013b10  test    esi, esi
0x140013b12  jz      short loc_140013B7E
0x140013b14  sub     esi, 1
0x140013b17  jz      short loc_140013B3B
0x140013b19  cmp     esi, 1
0x140013b1c  jnz     short loc_140013B84
0x140013b1e  lea     eax, [rsi+0Ah]
0x140013b21  mov     word ptr [rbp+pv], ax
0x140013b25  lea     eax, [rsi+2Ah]
0x140013b28  cmp     ax, [r15]
0x140013b2c  jnz     short loc_140013B33
0x140013b2e  or      eax, 0FFFFFFFFh
0x140013b31  jmp     short loc_140013B35
0x140013b33  xor     eax, eax
0x140013b35  mov     word ptr [rbp+pv+8], ax
0x140013b39  jmp     short loc_140013B84
0x140013b3b  mov     eax, 8
0x140013b40  mov     rcx, r15; psz
0x140013b43  mov     word ptr [rbp+pv], ax
0x140013b47  call    cs:__imp_SysAllocString
0x140013b4d  mov     [rbp+var_28], rax
0x140013b51  mov     ecx, dword ptr [rbp+var_28+2]
0x140013b54  mov     dword ptr [rbp+pv+0Ah], ecx
0x140013b57  movzx   ecx, word ptr [rbp+var_28+6]
0x140013b5b  mov     word ptr [rbp+pv+0Eh], cx
0x140013b5f  mov     word ptr [rbp+pv+8], ax
0x140013b63  test    rax, rax
0x140013b66  jnz     short loc_140013B84
0x140013b68  mov     ebx, 8007000Eh
0x140013b6d  mov     rax, [rdi]
0x140013b70  mov     rcx, rdi
0x140013b73  mov     rax, [rax+10h]
0x140013b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013b7c  jmp     short loc_140013BD7
0x140013b7e  xor     eax, eax
0x140013b80  mov     word ptr [rbp+pv], ax
0x140013b84  mov     rcx, [rdi+50h]; psa
0x140013b88  lea     r8, [rbp+pv]; pv
0x140013b8c  lea     rdx, [rbp+rgIndices]; rgIndices
0x140013b90  call    cs:__imp_SafeArrayPutElement
0x140013b96  lea     rcx, [rbp+pv]; pvarg
0x140013b9a  mov     ebx, eax
0x140013b9c  call    cs:__imp_VariantClear
0x140013ba2  test    ebx, ebx
0x140013ba4  js      short loc_140013B6D
0x140013ba6  mov     ecx, [rbp+rgIndices]
0x140013ba9  mov     esi, 1
0x140013bae  mov     rbx, [rbp+arg_8]
0x140013bb2  add     ecx, esi
0x140013bb4  mov     [rbp+rgIndices], ecx
0x140013bb7  lea     r10d, [rsi+2Ah]
0x140013bbb  lea     r11d, [rsi+7]
0x140013bbf  add     r12d, esi
0x140013bc2  jmp     loc_140013A47
0x140013bc7  mov     rax, [rbp+arg_10]
0x140013bcb  xor     ebx, ebx
0x140013bcd  mov     [rax], rdi
0x140013bd0  jmp     short loc_140013BD7
0x140013bd2  mov     ebx, 8007000Eh
0x140013bd7  mov     eax, ebx
0x140013bd9  mov     rbx, [rsp+50h+arg_0]
0x140013be1  add     rsp, 50h
0x140013be5  pop     r15
0x140013be7  pop     r14
0x140013be9  pop     r13
0x140013beb  pop     r12
0x140013bed  pop     rdi
0x140013bee  pop     rsi
0x140013bef  pop     rbp
0x140013bf0  retn
```
