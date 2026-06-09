# CopyDispParam(tagDISPPARAMS *,tagDISPPARAMS const *)

- ea: `0x18007c884`
- end: `0x18007ca43`
- name: `?CopyDispParam@@YAJPEAUtagDISPPARAMS@@PEBU1@@Z`
- size: `447`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, const struct tagDISPPARAMS *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180024380`
- `0x18007d870`

## callees

- `0x180013870`
- `0x18001b034`
- `0x180029560`
- `0x18002ec26`
- `0x18007c884`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18007c8de`
- `OLEAUT32!__imp_VariantInit` at `0x18007c8de`
- `OLEAUT32!__imp_VariantCopy` at `0x18007c8f2`
- `OLEAUT32!__imp_VariantCopy` at `0x18007c8f2`
- `ole32!CoTaskMemAlloc` at `0x18007c8b3`
- `ole32!CoTaskMemAlloc` at `0x18007c977`
- `ole32!CoTaskMemAlloc` at `0x18007c8b3`
- `ole32!CoTaskMemAlloc` at `0x18007c977`

## string_xrefs

- `0x18007c918`: `<CopyDispParam|OLEDB|ERR> `
- `0x18007c944`: `<CopyDispParam|OLEDB|ERR> `
- `0x18007c9b4`: `<CopyDispParam|Trace|HR> `
- `0x18007c9e5`: `<CopyDispParam|Trace|HR> `
- `0x18007ca1e`: `<CopyDispParam|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CopyDispParam(struct tagDISPPARAMS *a1, const struct tagDISPPARAMS *a2)
{
  VARIANTARG *v4; // rax
  __int64 i; // rbp
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  DISPID *v9; // rax

  *(_OWORD *)&a1->rgvarg = 0;
  *(_QWORD *)&a1->cArgs = 0;
  if ( !a2->cArgs )
  {
LABEL_12:
    if ( !a2->cNamedArgs )
      goto LABEL_15;
    v9 = (DISPID *)CoTaskMemAlloc(4LL * a2->cNamedArgs);
    a1->rgdispidNamedArgs = v9;
    if ( v9 )
    {
      memcpy_0(v9, a2->rgdispidNamedArgs, 4LL * a2->cNamedArgs);
      a1->cNamedArgs = a2->cNamedArgs;
LABEL_15:
      if ( (bidGblFlags & 2) != 0 )
        return bidTraceHR(off_1800C8540[0], 538633, L"<CopyDispParam|Trace|HR> ", 0);
      else
        return 0;
    }
    if ( (bidGblFlags & 2) == 0 )
    {
      v7 = -2147024882;
      goto LABEL_21;
    }
    v8 = 532489;
    goto LABEL_19;
  }
  v4 = (VARIANTARG *)CoTaskMemAlloc(24LL * a2->cArgs);
  a1->rgvarg = v4;
  if ( v4 )
  {
    for ( i = 0; (unsigned int)i < a2->cArgs; i = (unsigned int)(i + 1) )
    {
      VariantInit(&a1->rgvarg[i]);
      v6 = VariantCopy(&a1->rgvarg[i], &a2->rgvarg[i]);
      v7 = v6;
      if ( v6 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v6, L"<CopyDispParam|OLEDB|ERR> ", 0x1E9u);
        goto LABEL_21;
      }
      ++a1->cArgs;
    }
    goto LABEL_12;
  }
  v7 = -2147024882;
  if ( (bidGblFlags & 2) != 0 )
  {
    OLEDBTraceErr(-2147024882, L"<CopyDispParam|OLEDB|ERR> ", 0x1F2u);
    if ( (bidGblFlags & 2) != 0 )
    {
      v8 = 510985;
LABEL_19:
      v7 = bidTraceHR(off_1800C8540[0], v8, L"<CopyDispParam|Trace|HR> ", 2147942414LL);
    }
  }
LABEL_21:
  ClearDispParams(a1);
  *(_OWORD *)&a1->rgvarg = 0;
  *(_QWORD *)&a1->cArgs = 0;
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C8540[0], 543753, L"<CopyDispParam|Trace|HR> ", v7);
  return v7;
}

```

## disassembly

```asm
0x18007c884  push    rbx
0x18007c886  push    rbp
0x18007c887  push    rsi
0x18007c888  push    rdi
0x18007c889  sub     rsp, 28h
0x18007c88d  xor     eax, eax
0x18007c88f  xorps   xmm0, xmm0
0x18007c892  movups  xmmword ptr [rcx], xmm0
0x18007c895  mov     [rcx+10h], rax
0x18007c899  mov     rsi, rdx
0x18007c89c  mov     rdi, rcx
0x18007c89f  cmp     [rdx+10h], eax
0x18007c8a2  jz      loc_18007C96A
0x18007c8a8  mov     eax, [rdx+10h]
0x18007c8ab  lea     rcx, [rax+rax*2]
0x18007c8af  shl     rcx, 3; cb
0x18007c8b3  call    cs:__imp_CoTaskMemAlloc
0x18007c8b9  mov     [rdi], rax
0x18007c8bc  test    rax, rax
0x18007c8bf  jz      short loc_18007C92B
0x18007c8c1  xor     ebp, ebp
0x18007c8c3  cmp     ebp, [rsi+10h]
0x18007c8c6  jnb     loc_18007C96A
0x18007c8cc  mov     rax, [rdi]
0x18007c8cf  lea     rbx, ds:0[rbp*2]
0x18007c8d7  add     rbx, rbp
0x18007c8da  lea     rcx, [rax+rbx*8]; pvarg
0x18007c8de  call    cs:__imp_VariantInit
0x18007c8e4  mov     rax, [rsi]
0x18007c8e7  lea     rdx, [rax+rbx*8]; pvargSrc
0x18007c8eb  mov     rax, [rdi]
0x18007c8ee  lea     rcx, [rax+rbx*8]; pvargDest
0x18007c8f2  call    cs:__imp_VariantCopy
0x18007c8f8  mov     ebx, eax
0x18007c8fa  test    eax, eax
0x18007c8fc  js      short loc_18007C905
0x18007c8fe  inc     dword ptr [rdi+10h]
0x18007c901  inc     ebp
0x18007c903  jmp     short loc_18007C8C3
0x18007c905  test    byte ptr cs:_bidGblFlags, 2
0x18007c90c  jz      loc_18007C9FA
0x18007c912  mov     r8d, 1E9h; unsigned int
0x18007c918  lea     rdx, aCopydispparamO; "<CopyDispParam|OLEDB|ERR> "
0x18007c91f  mov     ecx, eax; int
0x18007c921  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007c926  jmp     loc_18007C9FA
0x18007c92b  mov     eax, cs:_bidGblFlags
0x18007c931  mov     ebx, 8007000Eh
0x18007c936  test    al, 2
0x18007c938  jz      loc_18007C9FA
0x18007c93e  mov     r8d, 1F2h; unsigned int
0x18007c944  lea     rdx, aCopydispparamO; "<CopyDispParam|OLEDB|ERR> "
0x18007c94b  mov     ecx, ebx; int
0x18007c94d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007c952  mov     eax, cs:_bidGblFlags
0x18007c958  test    al, 2
0x18007c95a  jz      loc_18007C9FA
0x18007c960  mov     r9d, ebx
0x18007c963  mov     edx, 7CC09h
0x18007c968  jmp     short loc_18007C9DE
0x18007c96a  cmp     dword ptr [rsi+14h], 0
0x18007c96e  jz      short loc_18007C9A0
0x18007c970  mov     ecx, [rsi+14h]
0x18007c973  shl     rcx, 2; cb
0x18007c977  call    cs:__imp_CoTaskMemAlloc
0x18007c97d  mov     [rdi+8], rax
0x18007c981  test    rax, rax
0x18007c984  jz      short loc_18007C9CA
0x18007c986  mov     r8d, [rsi+14h]
0x18007c98a  mov     rcx, rax; void *
0x18007c98d  mov     rdx, [rsi+8]; Src
0x18007c991  shl     r8, 2; Size
0x18007c995  call    memcpy_0
0x18007c99a  mov     eax, [rsi+14h]
0x18007c99d  mov     [rdi+14h], eax
0x18007c9a0  test    byte ptr cs:_bidGblFlags, 2
0x18007c9a7  jz      loc_18007CA38
0x18007c9ad  mov     rcx, cs:off_1800C8540; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18007c9b4  lea     r8, aCopydispparamT; "<CopyDispParam|Trace|HR> "
0x18007c9bb  xor     r9d, r9d
0x18007c9be  mov     edx, 83809h
0x18007c9c3  call    _bidTraceHR
0x18007c9c8  jmp     short loc_18007CA3A
0x18007c9ca  test    byte ptr cs:_bidGblFlags, 2
0x18007c9d1  jz      short loc_18007C9F5
0x18007c9d3  mov     r9d, 8007000Eh
0x18007c9d9  mov     edx, 82009h
0x18007c9de  mov     rcx, cs:off_1800C8540; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18007c9e5  lea     r8, aCopydispparamT; "<CopyDispParam|Trace|HR> "
0x18007c9ec  call    _bidTraceHR
0x18007c9f1  mov     ebx, eax
0x18007c9f3  jmp     short loc_18007C9FA
0x18007c9f5  mov     ebx, 8007000Eh
0x18007c9fa  mov     rcx, rdi; struct tagDISPPARAMS *
0x18007c9fd  call    ?ClearDispParams@@YAXPEAUtagDISPPARAMS@@@Z; ClearDispParams(tagDISPPARAMS *)
0x18007ca02  xor     eax, eax
0x18007ca04  xorps   xmm0, xmm0
0x18007ca07  movups  xmmword ptr [rdi], xmm0
0x18007ca0a  mov     [rdi+10h], rax
0x18007ca0e  test    byte ptr cs:_bidGblFlags, 2
0x18007ca15  jz      short loc_18007CA34
0x18007ca17  mov     rcx, cs:off_1800C8540; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18007ca1e  lea     r8, aCopydispparamT; "<CopyDispParam|Trace|HR> "
0x18007ca25  mov     r9d, ebx
0x18007ca28  mov     edx, 84C09h
0x18007ca2d  call    _bidTraceHR
0x18007ca32  mov     ebx, eax
0x18007ca34  mov     eax, ebx
0x18007ca36  jmp     short loc_18007CA3A
0x18007ca38  xor     eax, eax
0x18007ca3a  add     rsp, 28h
0x18007ca3e  pop     rdi
0x18007ca3f  pop     rsi
0x18007ca40  pop     rbp
0x18007ca41  pop     rbx
0x18007ca42  retn
```
