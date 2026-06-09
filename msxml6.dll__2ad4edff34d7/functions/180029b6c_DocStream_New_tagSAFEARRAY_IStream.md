# DocStream::New(tagSAFEARRAY *,IStream * *)

- ea: `0x180029b6c`
- end: `0x180029bfb`
- name: `?New@DocStream@@SAJPEAUtagSAFEARRAY@@PEAPEAUIStream@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(tagSAFEARRAY *psa, IStream **ppDS)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800804a0`

## callees

- `0x180029b6c`
- `0x180029efc`
- `0x1800c3c0c`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029b8c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029b8c`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180029bc3`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180029bc3`

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
    goto $CleanUp_23;
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
$CleanUp_23:
  *ppDS = v5;
  return (unsigned int)psa;
}

```

## disassembly

```asm
0x180029b6c  push    rbx
0x180029b6e  push    rsi
0x180029b6f  push    rdi
0x180029b70  push    r14
0x180029b72  sub     rsp, 28h
0x180029b76  mov     r14, ppDS
0x180029b79  mov     rdi, psa
0x180029b7c  mov     psa, cs:?g_hMsxmlHeap@@3PEAXEA; hHeap
0x180029b83  mov     edx, 8; dwFlags
0x180029b88  lea     r8d, [ppDS+58h]; dwBytes
0x180029b8c  call    cs:__imp_HeapAlloc
0x180029b92  test    rax, rax
0x180029b95  jnz     short loc_180029BA0
0x180029b97  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x180029b9c  xor     ebx, ebx
0x180029b9e  jmp     short loc_180029BB0
0x180029ba0  mov     psa, rax; this
0x180029ba3  call    ??0DocStream@@IEAA@XZ; DocStream::DocStream(void)
0x180029ba8  mov     rbx, rax
0x180029bab  test    rax, rax
0x180029bae  jnz     short loc_180029BB7
0x180029bb0  mov     edi, 8007000Eh
0x180029bb5  jmp     short $CleanUp_23
0x180029bb7  test    rdi, rdi
0x180029bba  jz      short $CleanUp_23
0x180029bbc  lea     ppDS, [rax+50h]; ppsaOut
0x180029bc0  mov     psa, rdi; psa
0x180029bc3  call    cs:__imp_SafeArrayCopy
0x180029bc9  mov     edi, eax
0x180029bcb  test    eax, eax
0x180029bcd  js      short loc_180029BDB
0x180029bcf  mov     psa, [rbx+50h]
0x180029bd3  mov     edx, [psa+18h]
0x180029bd6  mov     [rbx+30h], edx
0x180029bd9  jmp     short $CleanUp_23
0x180029bdb  mov     rax, [rbx]
0x180029bde  mov     psa, rbx
0x180029be1  mov     rax, [rax+10h]
0x180029be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bea  xor     ebx, ebx
0x180029bec  mov     [r14], rbx
0x180029bef  mov     eax, edi
0x180029bf1  add     rsp, 28h
0x180029bf5  pop     r14
0x180029bf7  pop     rdi
0x180029bf8  pop     rsi
0x180029bf9  pop     rbx
0x180029bfa  retn
```
