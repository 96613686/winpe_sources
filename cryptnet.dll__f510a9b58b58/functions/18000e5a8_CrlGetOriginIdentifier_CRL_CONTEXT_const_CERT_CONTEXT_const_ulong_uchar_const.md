# CrlGetOriginIdentifier(_CRL_CONTEXT const *,_CERT_CONTEXT const *,ulong,uchar * const)

- ea: `0x18000e5a8`
- end: `0x18000e604`
- name: `?CrlGetOriginIdentifier@@YAHPEBU_CRL_CONTEXT@@PEBU_CERT_CONTEXT@@KQEAE@Z`
- size: `92`
- prototype: `int __fastcall(const struct _CRL_CONTEXT *, const struct _CERT_CONTEXT *, __int64, unsigned __int8 *const)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000cfa0`
- `0x180018ff8`

## callees

- `0x180017c34`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x18000e5d2`
- `CRYPT32!CertFindExtension` at `0x18000e5d2`

## pseudocode

```c
int __fastcall CrlGetOriginIdentifier(
        const struct _CRL_CONTEXT *a1,
        const struct _CERT_CONTEXT *a2,
        __int64 a3,
        unsigned __int8 *const a4)
{
  PCERT_EXTENSION Extension; // rax

  Extension = CertFindExtension("2.5.29.27", a1->pCrlInfo->cExtension, a1->pCrlInfo->rgExtension);
  return CrlGetOriginIdentifierFromCrlIssuer(a2, &a1->pCrlInfo->Issuer, Extension != 0, a4);
}

```

## disassembly

```asm
0x18000e5a8  mov     [rsp+arg_0], rbx
0x18000e5ad  mov     [rsp+arg_8], rsi
0x18000e5b2  push    rdi
0x18000e5b3  sub     rsp, 20h
0x18000e5b7  mov     rsi, rdx
0x18000e5ba  mov     rbx, rcx
0x18000e5bd  mov     rdx, [rcx+18h]
0x18000e5c1  mov     rdi, r9
0x18000e5c4  lea     rcx, a252927; "2.5.29.27"
0x18000e5cb  mov     r8, [rdx+58h]; rgExtensions
0x18000e5cf  mov     edx, [rdx+50h]; cExtensions
0x18000e5d2  call    cs:__imp_CertFindExtension
0x18000e5d8  mov     rdx, [rbx+18h]
0x18000e5dc  xor     r8d, r8d
0x18000e5df  test    rax, rax
0x18000e5e2  mov     r9, rdi; unsigned __int8 *
0x18000e5e5  mov     rcx, rsi; struct _CERT_CONTEXT *
0x18000e5e8  setnz   r8b; int
0x18000e5ec  add     rdx, 20h ; ' '; struct _CRYPTOAPI_BLOB *
0x18000e5f0  mov     rbx, [rsp+28h+arg_0]
0x18000e5f5  mov     rsi, [rsp+28h+arg_8]
0x18000e5fa  add     rsp, 20h
0x18000e5fe  pop     rdi
0x18000e5ff  jmp     ?CrlGetOriginIdentifierFromCrlIssuer@@YAHPEBU_CERT_CONTEXT@@PEAU_CRYPTOAPI_BLOB@@HQEAE@Z; CrlGetOriginIdentifierFromCrlIssuer(_CERT_CONTEXT const *,_CRYPTOAPI_BLOB *,int,uchar * const)
```
