# FwProduct::put_RuleCategories(tagVARIANT)

- ea: `0x18001b620`
- end: `0x18001b867`
- name: `?put_RuleCategories@FwProduct@@UEAAJUtagVARIANT@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(FwProduct *this, struct tagVARIANT *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001b620`
- `0x1800294b0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001b7b1`
- `OLEAUT32!__imp_VariantClear` at `0x18001b7b1`
- `OLEAUT32!__imp_VariantCopy` at `0x18001b797`
- `OLEAUT32!__imp_VariantCopy` at `0x18001b797`
- `fwbase!FwBaseFree` at `0x18001b753`
- `fwbase!FwBaseFree` at `0x18001b812`
- `fwbase!FwBaseFree` at `0x18001b753`
- `fwbase!FwBaseFree` at `0x18001b812`
- `fwbase!FwAllocArray` at `0x18001b6bc`
- `fwbase!FwAllocArray` at `0x18001b6bc`
- `fwbase!FwReportReturnError` at `0x18001b744`
- `fwbase!FwReportReturnError` at `0x18001b803`
- `fwbase!FwReportReturnError` at `0x18001b827`
- `fwbase!FwReportReturnError` at `0x18001b854`
- `fwbase!FwReportReturnError` at `0x18001b744`
- `fwbase!FwReportReturnError` at `0x18001b803`
- `fwbase!FwReportReturnError` at `0x18001b827`
- `fwbase!FwReportReturnError` at `0x18001b854`

## pseudocode

```c
__int64 __fastcall FwProduct::put_RuleCategories(FwProduct *this, struct tagVARIANT *a2, __int64 a3)
{
  __int64 v5; // r14
  unsigned int v6; // r15d
  __int64 v7; // rsi
  LONGLONG llVal; // rbx
  unsigned int v9; // edi
  __int64 v10; // r8
  unsigned int i; // ecx
  __int64 v12; // rdx
  int v13; // eax
  int v14; // r8d
  unsigned int j; // edx
  int v16; // ecx
  int v17; // edi
  __int64 v18; // rdx
  HRESULT v20; // eax
  IRecordInfo *pRecInfo; // xmm1_8
  unsigned int v22; // ebx
  __int64 v23; // rdx
  VARIANTARG pvargDest; // [rsp+20h] [rbp-58h] BYREF

  memset(&pvargDest, 0, sizeof(pvargDest));
  v5 = 0;
  if ( *((_QWORD *)this + 12) )
  {
    v17 = -2147024891;
    v18 = 2147942405LL;
LABEL_19:
    FwReportReturnError("FwProduct::put_RuleCategories", v18);
    goto LABEL_20;
  }
  v6 = 0;
  if ( a2->vt )
  {
    v7 = 0;
    if ( a2->vt == 8204 && (llVal = a2->llVal) != 0 && *(_WORD *)llVal == 1 )
    {
      v9 = *(_DWORD *)(llVal + 24);
      if ( !v9 )
        goto LABEL_13;
      v7 = FwAllocArray(v9, 4, a3, 2147942487LL);
      if ( v7 )
      {
        v10 = *(_QWORD *)(llVal + 16);
        for ( i = 0; ; ++i )
        {
          if ( i >= v9 )
          {
            v6 = v9;
            v5 = v7;
            goto LABEL_13;
          }
          v12 = i;
          if ( *(_WORD *)(v10 + 24LL * i) != 3 )
            break;
          v13 = *(_DWORD *)(v10 + 24LL * i + 8);
          *(_DWORD *)(v7 + 4 * v12) = v13;
        }
        v23 = 2147942487LL;
        v22 = -2147024809;
      }
      else
      {
        v22 = -2147024882;
        v23 = 2147942414LL;
      }
    }
    else
    {
      v22 = -2147024809;
      v23 = 2147942487LL;
    }
    FwReportReturnError("FwVariantToArrayOfLongs", v23);
    FwBaseFree(v7);
    v20 = FwReportReturnError("FwVariantToArrayOfLongs", v22);
    v17 = v20;
    if ( v20 < 0 )
    {
LABEL_30:
      v18 = (unsigned int)v20;
      goto LABEL_19;
    }
  }
LABEL_13:
  v14 = 0;
  for ( j = 0; j < v6; ++j )
  {
    v16 = *(_DWORD *)(v5 + 4LL * j);
    if ( v16 >= 4 || ((1 << v16) & v14) != 0 )
    {
      v17 = -2147024809;
      v18 = 2147942487LL;
      goto LABEL_19;
    }
    v14 |= 1 << v16;
  }
  v20 = VariantCopy(&pvargDest, a2);
  v17 = v20;
  if ( v20 < 0 )
    goto LABEL_30;
  VariantClear((VARIANTARG *)((char *)this + 64));
  pRecInfo = pvargDest.pRecInfo;
  *((_OWORD *)this + 4) = *(_OWORD *)&pvargDest.vt;
  *((_QWORD *)this + 10) = pRecInfo;
LABEL_20:
  FwBaseFree(v5);
  if ( v17 < 0 )
    return (unsigned int)FwReportReturnError("FwProduct::put_RuleCategories", (unsigned int)v17);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18001b620  mov     [rsp+arg_10], rbx
0x18001b625  push    rbp
0x18001b626  push    rsi
0x18001b627  push    rdi
0x18001b628  push    r12
0x18001b62a  push    r13
0x18001b62c  push    r14
0x18001b62e  push    r15
0x18001b630  sub     rsp, 40h
0x18001b634  mov     rax, cs:__security_cookie
0x18001b63b  xor     rax, rsp
0x18001b63e  mov     [rsp+78h+var_40], rax
0x18001b643  xor     r12d, r12d
0x18001b646  xor     eax, eax
0x18001b648  xorps   xmm0, xmm0
0x18001b64b  mov     rbp, rdx
0x18001b64e  mov     r13, rcx
0x18001b651  mov     word ptr [rsp+78h+pvargDest], r12w
0x18001b657  mov     r14d, r12d
0x18001b65a  movups  xmmword ptr [rsp+78h+pvargDest+2], xmm0
0x18001b65f  mov     qword ptr [rsp+78h+pvargDest+10h], rax
0x18001b664  cmp     [rcx+60h], r12
0x18001b668  jnz     loc_18001B7D8
0x18001b66e  lea     r10d, [r12+1]
0x18001b673  mov     r15d, r12d
0x18001b676  mov     r9d, 80070057h
0x18001b67c  cmp     [rdx], r12w
0x18001b680  jz      loc_18001B70F
0x18001b686  mov     eax, 200Ch
0x18001b68b  mov     esi, r12d
0x18001b68e  cmp     [rdx], ax
0x18001b691  jnz     loc_18001B7F6
0x18001b697  mov     rbx, [rdx+8]
0x18001b69b  test    rbx, rbx
0x18001b69e  jz      loc_18001B7F6
0x18001b6a4  cmp     [rbx], r10w
0x18001b6a8  jnz     loc_18001B7F6
0x18001b6ae  mov     edi, [rbx+18h]
0x18001b6b1  test    edi, edi
0x18001b6b3  jz      short loc_18001B70F
0x18001b6b5  mov     ecx, edi
0x18001b6b7  lea     edx, [r12+4]
0x18001b6bc  call    cs:__imp_FwAllocArray
0x18001b6c3  nop     dword ptr [rax+rax+00h]
0x18001b6c8  mov     rsi, rax
0x18001b6cb  test    rax, rax
0x18001b6ce  jz      loc_18001B7E4
0x18001b6d4  mov     r8, [rbx+10h]
0x18001b6d8  lea     r10d, [r12+1]
0x18001b6dd  mov     ecx, r12d
0x18001b6e0  cmp     ecx, edi
0x18001b6e2  jnb     short loc_18001B703
0x18001b6e4  mov     edx, ecx
0x18001b6e6  lea     rax, [rdx+rdx*2]
0x18001b6ea  cmp     word ptr [r8+rax*8], 3
0x18001b6f0  jnz     loc_18001B7ED
0x18001b6f6  mov     eax, [r8+rax*8+8]
0x18001b6fb  add     ecx, r10d
0x18001b6fe  mov     [rsi+rdx*4], eax
0x18001b701  jmp     short loc_18001B6E0
0x18001b703  mov     r15d, edi
0x18001b706  mov     r14, rsi
0x18001b709  mov     r9d, 80070057h
0x18001b70f  mov     r8d, r12d
0x18001b712  mov     edx, r12d
0x18001b715  cmp     edx, r15d
0x18001b718  jnb     short loc_18001B78F
0x18001b71a  mov     eax, edx
0x18001b71c  mov     ecx, [r14+rax*4]
0x18001b720  cmp     ecx, 4
0x18001b723  jge     short loc_18001B737
0x18001b725  mov     eax, r10d
0x18001b728  shl     eax, cl
0x18001b72a  test    r8d, eax
0x18001b72d  jnz     short loc_18001B737
0x18001b72f  or      r8d, eax
0x18001b732  add     edx, r10d
0x18001b735  jmp     short loc_18001B715
0x18001b737  mov     edi, r9d
0x18001b73a  mov     edx, r9d
0x18001b73d  lea     rcx, aFwproductPutRu; "FwProduct::put_RuleCategories"
0x18001b744  call    cs:__imp_FwReportReturnError
0x18001b74b  nop     dword ptr [rax+rax+00h]
0x18001b750  mov     rcx, r14
0x18001b753  call    cs:__imp_FwBaseFree
0x18001b75a  nop     dword ptr [rax+rax+00h]
0x18001b75f  test    edi, edi
0x18001b761  js      loc_18001B84B
0x18001b767  mov     eax, edi
0x18001b769  mov     rcx, [rsp+78h+var_40]
0x18001b76e  xor     rcx, rsp; StackCookie
0x18001b771  call    __security_check_cookie
0x18001b776  mov     rbx, [rsp+78h+arg_10]
0x18001b77e  add     rsp, 40h
0x18001b782  pop     r15
0x18001b784  pop     r14
0x18001b786  pop     r13
0x18001b788  pop     r12
0x18001b78a  pop     rdi
0x18001b78b  pop     rsi
0x18001b78c  pop     rbp
0x18001b78d  retn
0x18001b78f  mov     rdx, rbp; pvargSrc
0x18001b792  lea     rcx, [rsp+78h+pvargDest]; pvargDest
0x18001b797  call    cs:__imp_VariantCopy
0x18001b79e  nop     dword ptr [rax+rax+00h]
0x18001b7a3  mov     edi, eax
0x18001b7a5  test    eax, eax
0x18001b7a7  js      loc_18001B844
0x18001b7ad  lea     rcx, [r13+40h]; pvarg
0x18001b7b1  call    cs:__imp_VariantClear
0x18001b7b8  nop     dword ptr [rax+rax+00h]
0x18001b7bd  movups  xmm0, xmmword ptr [rsp+78h+pvargDest]
0x18001b7c2  movsd   xmm1, qword ptr [rsp+78h+pvargDest+10h]
0x18001b7c8  movups  xmmword ptr [r13+40h], xmm0
0x18001b7cd  movsd   qword ptr [r13+50h], xmm1
0x18001b7d3  jmp     loc_18001B750
0x18001b7d8  mov     edi, 80070005h
0x18001b7dd  mov     edx, edi
0x18001b7df  jmp     loc_18001B73D
0x18001b7e4  mov     ebx, 8007000Eh
0x18001b7e9  mov     edx, ebx
0x18001b7eb  jmp     short loc_18001B7FC
0x18001b7ed  mov     edx, 80070057h
0x18001b7f2  mov     ebx, edx
0x18001b7f4  jmp     short loc_18001B7FC
0x18001b7f6  mov     ebx, r9d
0x18001b7f9  mov     edx, r9d
0x18001b7fc  lea     rcx, aFwvarianttoarr; "FwVariantToArrayOfLongs"
0x18001b803  call    cs:__imp_FwReportReturnError
0x18001b80a  nop     dword ptr [rax+rax+00h]
0x18001b80f  mov     rcx, rsi
0x18001b812  call    cs:__imp_FwBaseFree
0x18001b819  nop     dword ptr [rax+rax+00h]
0x18001b81e  mov     edx, ebx
0x18001b820  lea     rcx, aFwvarianttoarr; "FwVariantToArrayOfLongs"
0x18001b827  call    cs:__imp_FwReportReturnError
0x18001b82e  nop     dword ptr [rax+rax+00h]
0x18001b833  mov     edi, eax
0x18001b835  test    eax, eax
0x18001b837  js      short loc_18001B844
0x18001b839  mov     r10d, 1
0x18001b83f  jmp     loc_18001B709
0x18001b844  mov     edx, eax
0x18001b846  jmp     loc_18001B73D
0x18001b84b  mov     edx, edi
0x18001b84d  lea     rcx, aFwproductPutRu; "FwProduct::put_RuleCategories"
0x18001b854  call    cs:__imp_FwReportReturnError
0x18001b85b  nop     dword ptr [rax+rax+00h]
0x18001b860  mov     edi, eax
0x18001b862  jmp     loc_18001B767
```
