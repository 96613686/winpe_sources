# DocStream::New(tagSAFEARRAY *,IStream * *)

- ea: `0x1800508e4`
- end: `0x180050980`
- name: `?New@DocStream@@SAJPEAUtagSAFEARRAY@@PEAPEAUIStream@@@Z`
- size: `156`
- prototype: `HRESULT __fastcall(tagSAFEARRAY *psa, IStream **ppDS)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18007f7e0`

## callees

- `0x1800508e4`
- `0x180050c90`
- `0x1800c55c8`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180050904`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180050904`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180050941`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180050941`

## pseudocode

```c
__int64 __fastcall DocStream::New(tagSAFEARRAY *psa, IStream **ppDS)
{
  DocStream *v4; // rax
  IStream *v5; // rbx
  __int64 v6; // rax

  v4 = (DocStream *)HeapAlloc(g_hMsxmlHeap, 8u, 0x60u);
  if ( !v4 )
  {
    failure_tracing::record();
    v5 = 0;
LABEL_4:
    LODWORD(psa) = -2147024882;
    goto $CleanUp_33;
  }
  DocStream::DocStream(v4);
  v5 = (IStream *)v6;
  if ( !v6 )
    goto LABEL_4;
  if ( psa )
  {
    LODWORD(psa) = SafeArrayCopy(psa, (SAFEARRAY **)(v6 + 80));
    if ( (int)psa < 0 )
    {
      v5->Release(v5);
      v5 = 0;
    }
    else
    {
      LODWORD(v5[6].__vftable) = v5[10].Read;
    }
  }
$CleanUp_33:
  *ppDS = v5;
  return (unsigned int)psa;
}

```

## disassembly

```asm
0x1800508e4  push    rbx
0x1800508e6  push    rsi
0x1800508e7  push    rdi
0x1800508e8  push    r14
0x1800508ea  sub     rsp, 28h
0x1800508ee  mov     r14, ppDS
0x1800508f1  mov     rdi, psa
0x1800508f4  mov     psa, cs:?g_hMsxmlHeap@@3PEAXEA; hHeap
0x1800508fb  mov     edx, 8; dwFlags
0x180050900  lea     r8d, [ppDS+58h]; dwBytes
0x180050904  call    cs:__imp_HeapAlloc
0x18005090b  nop     dword ptr [rax+rax+00h]
0x180050910  test    rax, rax
0x180050913  jnz     short loc_18005091E
0x180050915  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x18005091a  xor     ebx, ebx
0x18005091c  jmp     short loc_18005092E
0x18005091e  mov     psa, rax; this
0x180050921  call    ??0DocStream@@IEAA@XZ; DocStream::DocStream(void)
0x180050926  mov     rbx, rax
0x180050929  test    rax, rax
0x18005092c  jnz     short loc_180050935
0x18005092e  mov     edi, 8007000Eh
0x180050933  jmp     short $CleanUp_33
0x180050935  test    rdi, rdi
0x180050938  jz      short $CleanUp_33
0x18005093a  lea     ppDS, [rax+50h]; ppsaOut
0x18005093e  mov     psa, rdi; psa
0x180050941  call    cs:__imp_SafeArrayCopy
0x180050948  nop     dword ptr [rax+rax+00h]
0x18005094d  mov     edi, eax
0x18005094f  test    eax, eax
0x180050951  js      short loc_18005095F
0x180050953  mov     psa, [rbx+50h]
0x180050957  mov     edx, [psa+18h]
0x18005095a  mov     [rbx+30h], edx
0x18005095d  jmp     short $CleanUp_33
0x18005095f  mov     rax, [rbx]
0x180050962  mov     psa, rbx
0x180050965  mov     rax, [rax+10h]
0x180050969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005096e  xor     ebx, ebx
0x180050970  mov     [r14], rbx
0x180050973  mov     eax, edi
0x180050975  add     rsp, 28h
0x180050979  pop     r14
0x18005097b  pop     rdi
0x18005097c  pop     rsi
0x18005097d  pop     rbx
0x18005097e  retn
```
