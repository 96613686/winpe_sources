# CMsgProperties::GetCorrelationID(void)

- ea: `0x1400032a0`
- end: `0x140003372`
- name: `?GetCorrelationID@CMsgProperties@@QEBA?AV_variant_t@@XZ`
- size: `210`
- prototype: `VARIANTARG *__fastcall(__int64, VARIANTARG *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000858c`

## callees

- `0x1400032a0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1400032c9`
- `OLEAUT32!__imp_VariantInit` at `0x1400032c9`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1400032ee`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1400032ee`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14000331a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140003353`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14000331a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140003353`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14000330d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14000330d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140003346`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140003346`

## pseudocode

```c
VARIANTARG *__fastcall CMsgProperties::GetCorrelationID(__int64 a1, VARIANTARG *a2)
{
  SAFEARRAY *v4; // rax
  SAFEARRAY *v5; // rdi
  __int64 v6; // rax
  _DWORD *v7; // rcx
  SAFEARRAYBOUND rgsabound; // [rsp+60h] [rbp+18h] BYREF
  void *ppvData; // [rsp+68h] [rbp+20h] BYREF

  rgsabound = (SAFEARRAYBOUND)20LL;
  VariantInit(a2);
  a2->vt = 10;
  a2->llVal = 0;
  v4 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v5 = v4;
  if ( v4 )
  {
    ppvData = 0;
    if ( SafeArrayAccessData(v4, &ppvData) >= 0 )
    {
      v6 = *(_QWORD *)(a1 + 144);
      v7 = ppvData;
      *(_OWORD *)ppvData = *(_OWORD *)v6;
      v7[4] = *(_DWORD *)(v6 + 16);
      a2->vt = 8209;
      a2->llVal = (LONGLONG)v5;
      if ( SafeArrayUnaccessData(v5) < 0 )
      {
        SafeArrayDestroy(v5);
        a2->vt = 10;
        a2->llVal = 0;
      }
    }
    else
    {
      SafeArrayDestroy(v5);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1400032a0  mov     [rsp+arg_8], rdx
0x1400032a5  push    rbx
0x1400032a6  push    rsi
0x1400032a7  push    rdi
0x1400032a8  push    r14
0x1400032aa  sub     rsp, 28h
0x1400032ae  mov     rbx, rdx
0x1400032b1  mov     rsi, rcx
0x1400032b4  mov     edi, 1
0x1400032b9  mov     [rsp+48h+arg_0], edi
0x1400032bd  mov     qword ptr [rsp+48h+rgsabound.cElements], 14h
0x1400032c6  mov     rcx, rdx; pvarg
0x1400032c9  call    cs:__imp_VariantInit
0x1400032cf  nop
0x1400032d0  mov     [rsp+48h+arg_0], edi
0x1400032d4  lea     r14d, [rdi+9]
0x1400032d8  mov     [rbx], r14w
0x1400032dc  mov     qword ptr [rbx+8], 0
0x1400032e4  lea     ecx, [rdi+10h]; vt
0x1400032e7  lea     r8, [rsp+48h+rgsabound]; rgsabound
0x1400032ec  mov     edx, edi; cDims
0x1400032ee  call    cs:__imp_SafeArrayCreate
0x1400032f4  mov     rdi, rax
0x1400032f7  test    rax, rax
0x1400032fa  jz      short loc_140003365
0x1400032fc  mov     [rsp+48h+ppvData], 0
0x140003305  lea     rdx, [rsp+48h+ppvData]; ppvData
0x14000330a  mov     rcx, rax; psa
0x14000330d  call    cs:__imp_SafeArrayAccessData
0x140003313  test    eax, eax
0x140003315  jns     short loc_140003322
0x140003317  mov     rcx, rdi; psa
0x14000331a  call    cs:__imp_SafeArrayDestroy
0x140003320  jmp     short loc_140003365
0x140003322  mov     rax, [rsi+90h]
0x140003329  mov     rcx, [rsp+48h+ppvData]
0x14000332e  movups  xmm0, xmmword ptr [rax]
0x140003331  movups  xmmword ptr [rcx], xmm0
0x140003334  mov     eax, [rax+10h]
0x140003337  mov     [rcx+10h], eax
0x14000333a  mov     word ptr [rbx], 2011h
0x14000333f  mov     [rbx+8], rdi
0x140003343  mov     rcx, rdi; psa
0x140003346  call    cs:__imp_SafeArrayUnaccessData
0x14000334c  test    eax, eax
0x14000334e  jns     short loc_140003365
0x140003350  mov     rcx, rdi; psa
0x140003353  call    cs:__imp_SafeArrayDestroy
0x140003359  mov     [rbx], r14w
0x14000335d  mov     qword ptr [rbx+8], 0
0x140003365  mov     rax, rbx
0x140003368  add     rsp, 28h
0x14000336c  pop     r14
0x14000336e  pop     rdi
0x14000336f  pop     rsi
0x140003370  pop     rbx
0x140003371  retn
```
