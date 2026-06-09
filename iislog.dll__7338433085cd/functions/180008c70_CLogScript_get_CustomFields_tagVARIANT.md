# CLogScript::get_CustomFields(tagVARIANT *)

- ea: `0x180008c70`
- end: `0x180008dca`
- name: `?get_CustomFields@CLogScript@@UEAAJPEAUtagVARIANT@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(CLogScript *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002034`
- `0x180008c70`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180008cef`
- `OLEAUT32!__imp_VariantInit` at `0x180008d54`
- `OLEAUT32!__imp_VariantInit` at `0x180008cef`
- `OLEAUT32!__imp_VariantInit` at `0x180008d54`
- `OLEAUT32!__imp_VariantClear` at `0x180008d31`
- `OLEAUT32!__imp_VariantClear` at `0x180008d95`
- `OLEAUT32!__imp_VariantClear` at `0x180008d31`
- `OLEAUT32!__imp_VariantClear` at `0x180008d95`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180008cc4`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180008cc4`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180008d25`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180008d89`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180008d25`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180008d89`

## pseudocode

```c
__int64 __fastcall CLogScript::get_CustomFields(CLogScript *this, struct tagVARIANT *a2)
{
  int v2; // r14d
  HRESULT v3; // esi
  ULONG v6; // eax
  SAFEARRAY *v7; // r15
  unsigned int v8; // ebx
  int v9; // edx
  LONG v10; // ebx
  int v11; // edx
  SAFEARRAYBOUND rgsabound; // [rsp+20h] [rbp-30h] BYREF
  __int64 v14; // [rsp+28h] [rbp-28h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+80h] [rbp+30h] BYREF
  int v17; // [rsp+84h] [rbp+34h]

  v2 = *((_DWORD *)this + 68);
  v3 = 0;
  a2->vt = 1;
  if ( v2 > 0 )
  {
    v6 = *((_DWORD *)this + 68);
    v14 = 2;
    rgsabound.lLbound = 0;
    rgsabound.cElements = v6;
    v7 = SafeArrayCreate(0xCu, 2u, &rgsabound);
    if ( v7 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      v8 = 0;
      v17 = 0;
      while ( 1 )
      {
        VariantInit(&pvarg);
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)A2WBSTR((LPCCH)this + 40 * v8 + 280, v9);
        rgIndices = v8;
        v3 = SafeArrayPutElement(v7, &rgIndices, &pvarg);
        VariantClear(&pvarg);
        if ( v3 < 0 )
          break;
        if ( (int)++v8 >= v2 )
        {
          v17 = 1;
          v10 = 0;
          while ( 1 )
          {
            VariantInit(&pvarg);
            pvarg.vt = 8;
            pvarg.llVal = (LONGLONG)A2WBSTR(*((LPCCH *)this + 5 * v10 + 39), v11);
            rgIndices = v10;
            v3 = SafeArrayPutElement(v7, &rgIndices, &pvarg);
            VariantClear(&pvarg);
            if ( v3 < 0 )
              return (unsigned int)v3;
            if ( ++v10 >= v2 )
              goto LABEL_9;
          }
        }
      }
    }
    else
    {
LABEL_9:
      a2->vt = 8204;
      a2->llVal = (LONGLONG)v7;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008c70  mov     [rsp-28h+arg_8], rbx
0x180008c75  mov     [rsp-28h+arg_10], rsi
0x180008c7a  push    rbp
0x180008c7b  push    rdi
0x180008c7c  push    r13
0x180008c7e  push    r14
0x180008c80  push    r15
0x180008c82  mov     rbp, rsp
0x180008c85  sub     rsp, 50h
0x180008c89  mov     r14d, [rcx+110h]
0x180008c90  xor     esi, esi
0x180008c92  mov     word ptr [rdx], 1
0x180008c97  mov     rdi, rdx
0x180008c9a  mov     r13, rcx
0x180008c9d  test    r14d, r14d
0x180008ca0  jle     loc_180008DAF
0x180008ca6  mov     eax, [rcx+110h]
0x180008cac  lea     edx, [rsi+2]; cDims
0x180008caf  lea     ecx, [rsi+0Ch]; vt
0x180008cb2  mov     [rbp+var_28], 2
0x180008cba  lea     r8, [rbp+rgsabound]; rgsabound
0x180008cbe  mov     [rbp+rgsabound.lLbound], esi
0x180008cc1  mov     [rbp+rgsabound.cElements], eax
0x180008cc4  call    cs:__imp_SafeArrayCreate
0x180008cca  mov     r15, rax
0x180008ccd  test    rax, rax
0x180008cd0  jz      loc_180008DA6
0x180008cd6  xor     eax, eax
0x180008cd8  xorps   xmm0, xmm0
0x180008cdb  movups  xmmword ptr [rbp+pvarg], xmm0
0x180008cdf  mov     qword ptr [rbp+pvarg+10h], rax
0x180008ce3  xor     ebx, ebx
0x180008ce5  mov     [rbp+arg_4], eax
0x180008ce8  lea     esi, [rax+8]
0x180008ceb  lea     rcx, [rbp+pvarg]; pvarg
0x180008cef  call    cs:__imp_VariantInit
0x180008cf5  mov     eax, ebx
0x180008cf7  add     rax, 7
0x180008cfb  mov     word ptr [rbp+pvarg], si
0x180008cff  lea     rcx, [rax+rax*4]
0x180008d03  lea     rcx, ds:0[rcx*8]
0x180008d0b  add     rcx, r13; lpMultiByteStr
0x180008d0e  call    ?A2WBSTR@@YAPEAGPEBDH@Z; A2WBSTR(char const *,int)
0x180008d13  lea     r8, [rbp+pvarg]; pv
0x180008d17  mov     qword ptr [rbp+pvarg+8], rax
0x180008d1b  lea     rdx, [rbp+rgIndices]; rgIndices
0x180008d1f  mov     [rbp+rgIndices], ebx
0x180008d22  mov     rcx, r15; psa
0x180008d25  call    cs:__imp_SafeArrayPutElement
0x180008d2b  lea     rcx, [rbp+pvarg]; pvarg
0x180008d2f  mov     esi, eax
0x180008d31  call    cs:__imp_VariantClear
0x180008d37  test    esi, esi
0x180008d39  js      short loc_180008DAF
0x180008d3b  inc     ebx
0x180008d3d  mov     esi, 8
0x180008d42  cmp     ebx, r14d
0x180008d45  jl      short loc_180008CEB
0x180008d47  mov     [rbp+arg_4], 1
0x180008d4e  xor     ebx, ebx
0x180008d50  lea     rcx, [rbp+pvarg]; pvarg
0x180008d54  call    cs:__imp_VariantInit
0x180008d5a  mov     eax, 8
0x180008d5f  mov     word ptr [rbp+pvarg], ax
0x180008d63  movsxd  rax, ebx
0x180008d66  lea     rcx, [rax+rax*4]
0x180008d6a  mov     rcx, [r13+rcx*8+138h]; lpMultiByteStr
0x180008d72  call    ?A2WBSTR@@YAPEAGPEBDH@Z; A2WBSTR(char const *,int)
0x180008d77  lea     r8, [rbp+pvarg]; pv
0x180008d7b  mov     qword ptr [rbp+pvarg+8], rax
0x180008d7f  lea     rdx, [rbp+rgIndices]; rgIndices
0x180008d83  mov     [rbp+rgIndices], ebx
0x180008d86  mov     rcx, r15; psa
0x180008d89  call    cs:__imp_SafeArrayPutElement
0x180008d8f  lea     rcx, [rbp+pvarg]; pvarg
0x180008d93  mov     esi, eax
0x180008d95  call    cs:__imp_VariantClear
0x180008d9b  test    esi, esi
0x180008d9d  js      short loc_180008DAF
0x180008d9f  inc     ebx
0x180008da1  cmp     ebx, r14d
0x180008da4  jl      short loc_180008D50
0x180008da6  mov     word ptr [rdi], 200Ch
0x180008dab  mov     [rdi+8], r15
0x180008daf  lea     r11, [rsp+50h+var_s0]
0x180008db4  mov     eax, esi
0x180008db6  mov     rbx, [r11+38h]
0x180008dba  mov     rsi, [r11+40h]
0x180008dbe  mov     rsp, r11
0x180008dc1  pop     r15
0x180008dc3  pop     r14
0x180008dc5  pop     r13
0x180008dc7  pop     rdi
0x180008dc8  pop     rbp
0x180008dc9  retn
```
