# AEFreeCertArray

- ea: `0x180004bf0`
- end: `0x180004c36`
- name: `AEFreeCertArray`
- size: `70`
- prototype: `HLOCAL __fastcall(_QWORD *hMem, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d90`
- `0x180002f50`
- `0x180006974`

## callees

- `0x180004bf0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004c25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004c25`
- `CRYPT32!CertFreeCertificateContext` at `0x180004c17`
- `CRYPT32!CertFreeCertificateContext` at `0x180004c17`

## pseudocode

```c
HLOCAL __fastcall AEFreeCertArray(_QWORD *hMem, __int64 a2)
{
  __int64 i; // rdi
  const CERT_CONTEXT *v4; // rcx
  HLOCAL result; // rax

  if ( hMem )
  {
    for ( i = a2; i; --i )
    {
      v4 = (const CERT_CONTEXT *)hMem[i - 1];
      if ( v4 )
        CertFreeCertificateContext(v4);
    }
    return LocalFree(hMem);
  }
  return result;
}

```

## disassembly

```asm
0x180004bf0  test    rcx, rcx
0x180004bf3  jz      short locret_180004C35
0x180004bf5  mov     [rsp+arg_0], rbx
0x180004bfa  push    rdi
0x180004bfb  sub     rsp, 20h
0x180004bff  mov     rdi, rdx
0x180004c02  mov     rbx, rcx
0x180004c05  test    rdx, rdx
0x180004c08  jz      short loc_180004C22
0x180004c0a  mov     rcx, [rbx+rdi*8-8]; pCertContext
0x180004c0f  dec     rdi
0x180004c12  test    rcx, rcx
0x180004c15  jz      short loc_180004C1D
0x180004c17  call    cs:__imp_CertFreeCertificateContext
0x180004c1d  test    rdi, rdi
0x180004c20  jnz     short loc_180004C0A
0x180004c22  mov     rcx, rbx; hMem
0x180004c25  call    cs:__imp_LocalFree
0x180004c2b  mov     rbx, [rsp+28h+arg_0]
0x180004c30  add     rsp, 20h
0x180004c34  pop     rdi
0x180004c35  retn
```
