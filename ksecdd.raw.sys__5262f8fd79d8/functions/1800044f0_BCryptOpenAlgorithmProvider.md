# BCryptOpenAlgorithmProvider

- ea: `0x1800044f0`
- end: `0x18000451e`
- name: `BCryptOpenAlgorithmProvider`
- size: `46`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE *phAlgorithm, LPCWSTR pszAlgId, LPCWSTR pszImplementation, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800044f0`
- `0x180010980`

## pseudocode

```c
NTSTATUS __stdcall BCryptOpenAlgorithmProvider(
        BCRYPT_ALG_HANDLE *phAlgorithm,
        LPCWSTR pszAlgId,
        LPCWSTR pszImplementation,
        ULONG dwFlags)
{
  __int64 (__fastcall *v4)(BCRYPT_ALG_HANDLE *, LPCWSTR, LPCWSTR, ULONG); // rax

  if ( *(_QWORD *)&WPP_MAIN_CB.SectorSize
    && (v4 = *(__int64 (__fastcall **)(BCRYPT_ALG_HANDLE *, LPCWSTR, LPCWSTR, ULONG))(*(_QWORD *)&WPP_MAIN_CB.SectorSize
                                                                                    + 224LL)) != 0 )
  {
    return v4(phAlgorithm, pszAlgId, pszImplementation, dwFlags);
  }
  else
  {
    return -1073741822;
  }
}

```

## disassembly

```asm
0x1800044f0  sub     rsp, 38h
0x1800044f4  mov     rax, qword ptr cs:WPP_MAIN_CB.SectorSize
0x1800044fb  test    rax, rax
0x1800044fe  jz      short loc_18000450C
0x180004500  mov     rax, [rax+0E0h]
0x180004507  test    rax, rax
0x18000450a  jnz     short loc_180004517
0x18000450c  mov     eax, 0C0000002h
0x180004511  add     rsp, 38h
0x180004515  retn
0x180004517  call    _guard_dispatch_icall
0x18000451c  jmp     short loc_180004511
```
