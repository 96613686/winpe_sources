# _FreeCacheFileEntries

- ea: `0x18000251c`
- end: `0x1800025c0`
- name: `_FreeCacheFileEntries`
- size: `164`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003aa0`
- `0x180004998`

## callees

- `0x18000251c`
- `0x1800068b0`

## import_xrefs

- `CRYPT32!I_CryptReleaseLruEntry` at `0x18000259e`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x18000259e`
- `CRYPT32!I_CryptWalkAllLruCacheEntries` at `0x180002557`
- `CRYPT32!I_CryptWalkAllLruCacheEntries` at `0x180002557`
- `CRYPT32!I_CryptRemoveLruEntry` at `0x180002594`
- `CRYPT32!I_CryptRemoveLruEntry` at `0x180002594`

## pseudocode

```c
void __fastcall FreeCacheFileEntries(__int64 a1, unsigned int a2)
{
  __int64 v2; // rcx
  _QWORD *v3; // rbx
  __int64 v4; // rax
  HLOCAL hMem[4]; // [rsp+20h] [rbp-20h] BYREF

  v2 = *(_QWORD *)(a1 + 104);
  if ( v2 )
  {
    hMem[1] = hMem;
    hMem[2] = (HLOCAL)a2;
    hMem[0] = hMem;
    I_CryptWalkAllLruCacheEntries(v2, WalkFreeCacheFileEntryCallback, hMem);
    while ( 1 )
    {
      v3 = hMem[0];
      if ( hMem[0] == hMem )
        break;
      if ( *((HLOCAL **)hMem[0] + 1) != hMem
        || (v4 = *(_QWORD *)hMem[0], *(HLOCAL *)(*(_QWORD *)hMem[0] + 8LL) != hMem[0]) )
      {
        __fastfail(3u);
      }
      hMem[0] = *(HLOCAL *)hMem[0];
      *(_QWORD *)(v4 + 8) = hMem;
      I_CryptRemoveLruEntry(v3[2], 4);
      I_CryptReleaseLruEntry(v3[2]);
      PkiFree(v3);
    }
  }
}

```

## disassembly

```asm
0x18000251c  mov     [rsp-8+arg_0], rbx
0x180002521  push    rbp
0x180002522  mov     rbp, rsp
0x180002525  sub     rsp, 40h
0x180002529  mov     rcx, [rcx+68h]
0x18000252d  test    rcx, rcx
0x180002530  jz      short loc_1800025AE
0x180002532  xorps   xmm0, xmm0
0x180002535  lea     rax, [rbp+hMem]
0x180002539  movups  [rbp+var_18], xmm0
0x18000253d  mov     qword ptr [rbp+var_18], rax
0x180002541  lea     r8, [rbp+hMem]
0x180002545  lea     rax, [rbp+hMem]
0x180002549  mov     dword ptr [rbp+var_18+8], edx
0x18000254c  lea     rdx, _WalkFreeCacheFileEntryCallback
0x180002553  mov     [rbp+hMem], rax
0x180002557  call    cs:__imp_I_CryptWalkAllLruCacheEntries
0x18000255d  mov     rbx, [rbp+hMem]
0x180002561  lea     rax, [rbp+hMem]
0x180002565  cmp     rbx, rax
0x180002568  jz      short loc_1800025AE
0x18000256a  lea     rax, [rbp+hMem]
0x18000256e  cmp     [rbx+8], rax
0x180002572  jnz     short loc_1800025B9
0x180002574  mov     rax, [rbx]
0x180002577  cmp     [rax+8], rbx
0x18000257b  jnz     short loc_1800025B9
0x18000257d  mov     [rbp+hMem], rax
0x180002581  lea     rcx, [rbp+hMem]
0x180002585  xor     r8d, r8d
0x180002588  mov     [rax+8], rcx
0x18000258c  mov     rcx, [rbx+10h]
0x180002590  lea     edx, [r8+4]
0x180002594  call    cs:__imp_I_CryptRemoveLruEntry
0x18000259a  mov     rcx, [rbx+10h]
0x18000259e  call    cs:__imp_I_CryptReleaseLruEntry
0x1800025a4  mov     rcx, rbx; hMem
0x1800025a7  call    PkiFree
0x1800025ac  jmp     short loc_18000255D
0x1800025ae  mov     rbx, [rsp+40h+arg_0]
0x1800025b3  add     rsp, 40h
0x1800025b7  pop     rbp
0x1800025b8  retn
0x1800025b9  mov     ecx, 3
0x1800025be  int     29h; Win8: RtlFailFast(ecx)
```
