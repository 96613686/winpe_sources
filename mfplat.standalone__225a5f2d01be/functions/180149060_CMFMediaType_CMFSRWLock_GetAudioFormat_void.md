# CMFMediaType<CMFSRWLock>::GetAudioFormat(void)

- ea: `0x180149060`
- end: `0x180149158`
- name: `?GetAudioFormat@?$CMFMediaType@VCMFSRWLock@@@@UEAAPEBUtWAVEFORMATEX@@XZ`
- size: `248`
- prototype: `__int64 __fastcall(IMFMediaType *pMFType)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180040e20`
- `0x180120ecc`
- `0x180121581`
- `0x180149060`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801490bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180149109`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014912d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801490bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180149109`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014912d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18014908e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18014908e`

## pseudocode

```c
signed __int64 __fastcall CMFMediaType<CMFSRWLock>::GetAudioFormat(IMFMediaType *pMFType)
{
  volatile signed __int64 v2; // rbp
  volatile signed __int64 *v3; // rsi
  void *v4; // rax
  void *v5; // rdi
  IMFMediaType *v6; // rdi
  WAVEFORMATEX *v7; // rcx
  UINT32 pcbSize; // [rsp+40h] [rbp+8h] BYREF
  WAVEFORMATEX *ppWF; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  pMFType->LockStore(pMFType);
  v3 = (volatile signed __int64 *)&pMFType[9];
  if ( pMFType[9].__vftable )
  {
    v6 = pMFType + 9;
  }
  else
  {
    v4 = CoTaskMemAlloc(0xA8u);
    v5 = v4;
    if ( !v4 )
      goto LABEL_13;
    memset_0(v4, 0, 0xA8u);
    if ( _InterlockedCompareExchange64(v3, (signed __int64)v5, 0) )
      CoTaskMemFree(v5);
    v6 = pMFType + 9;
    _InterlockedExchange((volatile __int32 *)&pMFType[6], 1);
  }
  if ( !LODWORD(pMFType[6].__vftable) )
    goto LABEL_12;
  ppWF = 0;
  pcbSize = 0;
  if ( MFCreateWaveFormatExFromMFMediaType(pMFType, &ppWF, &pcbSize, 0) >= 0 )
  {
    if ( pcbSize > 0xA8 )
    {
      CoTaskMemFree((LPVOID)ppWF);
      goto LABEL_13;
    }
    memcpy_0(v6->__vftable, ppWF, pcbSize);
    v7 = ppWF;
    _InterlockedExchange((volatile __int32 *)&pMFType[6], 0);
    CoTaskMemFree((LPVOID)v7);
LABEL_12:
    v2 = *v3;
  }
LABEL_13:
  pMFType->UnlockStore(pMFType);
  return v2;
}

```

## disassembly

```asm
0x180149060  mov     [rsp+arg_10], rbx
0x180149065  push    rbp
0x180149066  push    rsi
0x180149067  push    rdi
0x180149068  sub     rsp, 20h
0x18014906c  mov     rax, [rcx]
0x18014906f  mov     rbx, rcx
0x180149072  xor     ebp, ebp
0x180149074  mov     rax, [rax+0E0h]
0x18014907b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149080  lea     rsi, [rbx+48h]
0x180149084  cmp     [rsi], rbp
0x180149087  jnz     short loc_1801490D0
0x180149089  mov     ecx, 0A8h; cb
0x18014908e  call    cs:__imp_CoTaskMemAlloc
0x180149094  mov     rdi, rax
0x180149097  test    rax, rax
0x18014909a  jz      loc_180149136
0x1801490a0  xor     edx, edx; Val
0x1801490a2  mov     r8d, 0A8h; Size
0x1801490a8  mov     rcx, rax; void *
0x1801490ab  call    memset_0
0x1801490b0  xor     eax, eax
0x1801490b2  lock cmpxchg [rsi], rdi
0x1801490b7  jz      short loc_1801490C2
0x1801490b9  mov     rcx, rdi; pv
0x1801490bc  call    cs:__imp_CoTaskMemFree
0x1801490c2  mov     eax, 1
0x1801490c7  lea     rdi, [rbx+48h]
0x1801490cb  xchg    eax, [rbx+30h]
0x1801490ce  jmp     short loc_1801490D3
0x1801490d0  mov     rdi, rsi
0x1801490d3  cmp     [rbx+30h], ebp
0x1801490d6  jz      short loc_180149133
0x1801490d8  xor     r9d, r9d; Flags
0x1801490db  mov     [rsp+38h+ppWF], rbp
0x1801490e0  lea     r8, [rsp+38h+pcbSize]; pcbSize
0x1801490e5  mov     [rsp+38h+pcbSize], ebp
0x1801490e9  lea     rdx, [rsp+38h+ppWF]; ppWF
0x1801490ee  mov     rcx, rbx; pMFType
0x1801490f1  call    MFCreateWaveFormatExFromMFMediaType
0x1801490f6  test    eax, eax
0x1801490f8  js      short loc_180149136
0x1801490fa  cmp     [rsp+38h+pcbSize], 0A8h
0x180149102  jbe     short loc_180149111
0x180149104  mov     rcx, [rsp+38h+ppWF]; pv
0x180149109  call    cs:__imp_CoTaskMemFree
0x18014910f  jmp     short loc_180149136
0x180149111  mov     r8d, [rsp+38h+pcbSize]; Size
0x180149116  mov     rdx, [rsp+38h+ppWF]; Src
0x18014911b  mov     rcx, [rdi]; void *
0x18014911e  call    memcpy_0
0x180149123  mov     rcx, [rsp+38h+ppWF]; pv
0x180149128  xor     eax, eax
0x18014912a  xchg    eax, [rbx+30h]
0x18014912d  call    cs:__imp_CoTaskMemFree
0x180149133  mov     rbp, [rsi]
0x180149136  mov     rcx, [rbx]
0x180149139  mov     rax, [rcx+0E8h]
0x180149140  mov     rcx, rbx
0x180149143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149148  mov     rbx, [rsp+38h+arg_10]
0x18014914d  mov     rax, rbp
0x180149150  add     rsp, 20h
0x180149154  pop     rdi
0x180149155  pop     rsi
0x180149156  pop     rbp
0x180149157  retn
```
