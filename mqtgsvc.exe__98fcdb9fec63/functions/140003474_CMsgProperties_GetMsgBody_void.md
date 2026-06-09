# CMsgProperties::GetMsgBody(void)

- ea: `0x140003474`
- end: `0x140003527`
- name: `?GetMsgBody@CMsgProperties@@QEBA?AV_variant_t@@XZ`
- size: `179`
- prototype: `VARIANTARG *__fastcall(__int64, VARIANTARG *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000858c`

## callees

- `0x140003474`
- `0x14001cece`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x140003491`
- `OLEAUT32!__imp_VariantInit` at `0x140003491`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1400034c4`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1400034c4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140003510`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140003510`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1400034d5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1400034d5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140003503`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140003503`

## pseudocode

```c
VARIANTARG *__fastcall CMsgProperties::GetMsgBody(__int64 a1, VARIANTARG *a2)
{
  SAFEARRAY *v4; // rdi
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp+8h] BYREF
  VARIANTARG *v7; // [rsp+58h] [rbp+10h]
  void *ppvData; // [rsp+60h] [rbp+18h] BYREF

  v7 = a2;
  VariantInit(a2);
  ppvData = 0;
  rgsabound.lLbound = 0;
  rgsabound.cElements = *(_DWORD *)(a1 + 160);
  v4 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  if ( SafeArrayAccessData(v4, &ppvData) < 0 )
    goto LABEL_4;
  memcpy_0(ppvData, *(const void **)(a1 + 192), *(int *)(a1 + 160));
  a2->vt = 8209;
  a2->llVal = (LONGLONG)v4;
  if ( SafeArrayUnaccessData(v4) < 0 )
  {
    SafeArrayDestroy(v4);
LABEL_4:
    a2->vt = 10;
  }
  return a2;
}

```

## disassembly

```asm
0x140003474  mov     [rsp+arg_8], rdx
0x140003479  push    rbx
0x14000347a  push    rsi
0x14000347b  push    rdi
0x14000347c  sub     rsp, 30h
0x140003480  mov     rbx, rdx
0x140003483  mov     rsi, rcx
0x140003486  mov     [rsp+48h+var_28], 0
0x14000348e  mov     rcx, rdx; pvarg
0x140003491  call    cs:__imp_VariantInit
0x140003497  nop
0x140003498  mov     edx, 1; cDims
0x14000349d  mov     [rsp+48h+var_28], edx
0x1400034a1  mov     [rsp+48h+ppvData], 0
0x1400034aa  mov     [rsp+48h+rgsabound.lLbound], 0
0x1400034b2  mov     eax, [rsi+0A0h]
0x1400034b8  mov     [rsp+48h+rgsabound.cElements], eax
0x1400034bc  lea     ecx, [rdx+10h]; vt
0x1400034bf  lea     r8, [rsp+48h+rgsabound]; rgsabound
0x1400034c4  call    cs:__imp_SafeArrayCreate
0x1400034ca  mov     rdi, rax
0x1400034cd  lea     rdx, [rsp+48h+ppvData]; ppvData
0x1400034d2  mov     rcx, rax; psa
0x1400034d5  call    cs:__imp_SafeArrayAccessData
0x1400034db  test    eax, eax
0x1400034dd  js      short loc_140003516
0x1400034df  movsxd  r8, dword ptr [rsi+0A0h]; Size
0x1400034e6  mov     rdx, [rsi+0C0h]; Src
0x1400034ed  mov     rcx, [rsp+48h+ppvData]; void *
0x1400034f2  call    memcpy_0
0x1400034f7  mov     word ptr [rbx], 2011h
0x1400034fc  mov     [rbx+8], rdi
0x140003500  mov     rcx, rdi; psa
0x140003503  call    cs:__imp_SafeArrayUnaccessData
0x140003509  test    eax, eax
0x14000350b  jns     short loc_14000351B
0x14000350d  mov     rcx, rdi; psa
0x140003510  call    cs:__imp_SafeArrayDestroy
0x140003516  mov     word ptr [rbx], 0Ah
0x14000351b  mov     rax, rbx
0x14000351e  add     rsp, 30h
0x140003522  pop     rdi
0x140003523  pop     rsi
0x140003524  pop     rbx
0x140003525  retn
```
