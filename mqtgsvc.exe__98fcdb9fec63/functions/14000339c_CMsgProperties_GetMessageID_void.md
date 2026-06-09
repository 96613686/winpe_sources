# CMsgProperties::GetMessageID(void)

- ea: `0x14000339c`
- end: `0x14000346b`
- name: `?GetMessageID@CMsgProperties@@QEBA?AV_variant_t@@XZ`
- size: `207`
- prototype: `VARIANTARG *__fastcall(__int64, VARIANTARG *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000858c`

## callees

- `0x14000339c`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1400033c5`
- `OLEAUT32!__imp_VariantInit` at `0x1400033c5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1400033ea`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1400033ea`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140003416`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14000344c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140003416`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14000344c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140003409`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140003409`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14000343f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14000343f`

## pseudocode

```c
VARIANTARG *__fastcall CMsgProperties::GetMessageID(__int64 a1, VARIANTARG *a2)
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
      v6 = *(_QWORD *)(a1 + 120);
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
0x14000339c  mov     [rsp+arg_8], rdx
0x1400033a1  push    rbx
0x1400033a2  push    rsi
0x1400033a3  push    rdi
0x1400033a4  push    r14
0x1400033a6  sub     rsp, 28h
0x1400033aa  mov     rbx, rdx
0x1400033ad  mov     rsi, rcx
0x1400033b0  mov     edi, 1
0x1400033b5  mov     [rsp+48h+arg_0], edi
0x1400033b9  mov     qword ptr [rsp+48h+rgsabound.cElements], 14h
0x1400033c2  mov     rcx, rdx; pvarg
0x1400033c5  call    cs:__imp_VariantInit
0x1400033cb  nop
0x1400033cc  mov     [rsp+48h+arg_0], edi
0x1400033d0  lea     r14d, [rdi+9]
0x1400033d4  mov     [rbx], r14w
0x1400033d8  mov     qword ptr [rbx+8], 0
0x1400033e0  lea     ecx, [rdi+10h]; vt
0x1400033e3  lea     r8, [rsp+48h+rgsabound]; rgsabound
0x1400033e8  mov     edx, edi; cDims
0x1400033ea  call    cs:__imp_SafeArrayCreate
0x1400033f0  mov     rdi, rax
0x1400033f3  test    rax, rax
0x1400033f6  jz      short loc_14000345E
0x1400033f8  mov     [rsp+48h+ppvData], 0
0x140003401  lea     rdx, [rsp+48h+ppvData]; ppvData
0x140003406  mov     rcx, rax; psa
0x140003409  call    cs:__imp_SafeArrayAccessData
0x14000340f  test    eax, eax
0x140003411  jns     short loc_14000341E
0x140003413  mov     rcx, rdi; psa
0x140003416  call    cs:__imp_SafeArrayDestroy
0x14000341c  jmp     short loc_14000345E
0x14000341e  mov     rax, [rsi+78h]
0x140003422  mov     rcx, [rsp+48h+ppvData]
0x140003427  movups  xmm0, xmmword ptr [rax]
0x14000342a  movups  xmmword ptr [rcx], xmm0
0x14000342d  mov     eax, [rax+10h]
0x140003430  mov     [rcx+10h], eax
0x140003433  mov     word ptr [rbx], 2011h
0x140003438  mov     [rbx+8], rdi
0x14000343c  mov     rcx, rdi; psa
0x14000343f  call    cs:__imp_SafeArrayUnaccessData
0x140003445  test    eax, eax
0x140003447  jns     short loc_14000345E
0x140003449  mov     rcx, rdi; psa
0x14000344c  call    cs:__imp_SafeArrayDestroy
0x140003452  mov     [rbx], r14w
0x140003456  mov     qword ptr [rbx+8], 0
0x14000345e  mov     rax, rbx
0x140003461  add     rsp, 28h
0x140003465  pop     r14
0x140003467  pop     rdi
0x140003468  pop     rsi
0x140003469  pop     rbx
0x14000346a  retn
```
