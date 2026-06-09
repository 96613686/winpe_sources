# p_GetAlgHandle

- ea: `0x140012834`
- end: `0x1400128a4`
- name: `p_GetAlgHandle`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140041b84`

## callees

- `0x140012834`

## import_xrefs

- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14001288e`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14001288e`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140012862`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140012862`

## pseudocode

```c
signed __int64 __fastcall p_GetAlgHandle(volatile signed __int64 *a1, void *a2, ULONG a3)
{
  bool v3; // zf
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+38h] [rbp+10h] BYREF

  phAlgorithm = a2;
  v3 = *a1 == 0;
  phAlgorithm = 0;
  if ( v3 )
  {
    if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"MD5", 0, a3) < 0 )
      __fastfail(7u);
    if ( _InterlockedCompareExchange64(a1, (signed __int64)phAlgorithm, 0) )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  }
  return *a1;
}

```

## disassembly

```asm
0x140012834  mov     [rsp+phAlgorithm], rdx
0x140012839  push    rbx
0x14001283a  sub     rsp, 20h
0x14001283e  cmp     qword ptr [rcx], 0
0x140012842  mov     rbx, rcx
0x140012845  mov     [rsp+28h+phAlgorithm], 0
0x14001284e  jnz     short loc_14001289A
0x140012850  mov     r9d, r8d; dwFlags
0x140012853  lea     rdx, pszAlgId; "MD5"
0x14001285a  xor     r8d, r8d; pszImplementation
0x14001285d  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x140012862  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140012869  nop     dword ptr [rax+rax+00h]
0x14001286e  test    eax, eax
0x140012870  jns     short loc_140012879
0x140012872  mov     ecx, 7
0x140012877  int     29h; Win8: RtlFailFast(ecx)
0x140012879  mov     rcx, [rsp+28h+phAlgorithm]
0x14001287e  xor     eax, eax
0x140012880  lock cmpxchg [rbx], rcx
0x140012885  jz      short loc_14001289A
0x140012887  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x14001288c  xor     edx, edx; dwFlags
0x14001288e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140012895  nop     dword ptr [rax+rax+00h]
0x14001289a  mov     rax, [rbx]
0x14001289d  add     rsp, 20h
0x1400128a1  pop     rbx
0x1400128a2  retn
```
