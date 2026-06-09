# _ValidateCaExchangeCertificate(bool,_CERT_CONTEXT const *,void *)

- ea: `0x180005910`
- end: `0x18000596e`
- name: `?_ValidateCaExchangeCertificate@@YAJ_NPEBU_CERT_CONTEXT@@PEAX@Z`
- size: `94`
- prototype: `__int64 __fastcall(char, const struct _CERT_CONTEXT *, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004ed0`
- `0x180005380`

## callees

- `0x180001140`
- `0x180003750`
- `0x180005910`

## pseudocode

```c
__int64 __fastcall _ValidateCaExchangeCertificate(char a1, const struct _CERT_CONTEXT *a2, void *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  const CERT_CHAIN_CONTEXT *v6; // [rsp+20h] [rbp-28h]
  char *v7[3]; // [rsp+30h] [rbp-18h] BYREF

  v7[0] = "1.3.6.1.4.1.311.21.5";
  v7[1] = "1.3.6.1.4.1.311.21.36";
  v3 = _VerifyCertContext(a1, a2, 2u, v7, v6, a3);
  v4 = v3;
  if ( !v3 )
    return 0;
  ekTraceFmt(0x22912C3u, 1u, "ERROR: _VerifyCertContext. Hr=%x\n", v3);
  return v4;
}

```

## disassembly

```asm
0x180005910  push    rbx
0x180005912  sub     rsp, 40h
0x180005916  lea     rax, a136141311215; "1.3.6.1.4.1.311.21.5"
0x18000591d  mov     [rsp+48h+var_20], r8; void *
0x180005922  mov     [rsp+48h+var_18], rax
0x180005927  lea     r9, [rsp+48h+var_18]; char **
0x18000592c  lea     rax, a1361413112136; "1.3.6.1.4.1.311.21.36"
0x180005933  mov     r8d, 2; unsigned int
0x180005939  mov     [rsp+48h+var_10], rax
0x18000593e  call    ?_VerifyCertContext@@YAJ_NPEBU_CERT_CONTEXT@@KPEBQEBDPEAX3@Z; _VerifyCertContext(bool,_CERT_CONTEXT const *,ulong,char const * const *,void *,void *)
0x180005943  mov     ebx, eax
0x180005945  test    eax, eax
0x180005947  jz      short loc_180005966
0x180005949  mov     r9d, eax
0x18000594c  lea     r8, aErrorVerifycer; "ERROR: _VerifyCertContext. Hr=%x\n"
0x180005953  mov     edx, 1; unsigned int
0x180005958  mov     ecx, 22912C3h; unsigned int
0x18000595d  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180005962  mov     eax, ebx
0x180005964  jmp     short loc_180005968
0x180005966  xor     eax, eax
0x180005968  add     rsp, 40h
0x18000596c  pop     rbx
0x18000596d  retn
```
