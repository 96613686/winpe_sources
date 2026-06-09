# CSMime::HrGetCertsFromThumbprints(tagBLOB * const,tagX509CERTRESULT * const)

- ea: `0x18003b2dc`
- end: `0x18003b3c2`
- name: `?HrGetCertsFromThumbprints@CSMime@@SAJQEAUtagBLOB@@QEAUtagX509CERTRESULT@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(struct tagBLOB *const, struct tagX509CERTRESULT *const)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003b108`

## callees

- `0x18002d520`
- `0x18003b2dc`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x18003b317`
- `CRYPT32!CertOpenStore` at `0x18003b345`
- `CRYPT32!CertOpenStore` at `0x18003b317`
- `CRYPT32!CertOpenStore` at `0x18003b345`
- `CRYPT32!CertCloseStore` at `0x18003b375`
- `CRYPT32!CertCloseStore` at `0x18003b3af`
- `CRYPT32!CertCloseStore` at `0x18003b375`
- `CRYPT32!CertCloseStore` at `0x18003b3af`

## pseudocode

```c
__int64 __fastcall CSMime::HrGetCertsFromThumbprints(struct tagBLOB *const a1, struct tagX509CERTRESULT *const a2)
{
  unsigned int CertsFromThumbprints; // edi
  void *v5; // rbp
  void *v6; // rsi
  __int64 i; // r8
  HCERTSTORE v9; // [rsp+30h] [rbp-38h] BYREF
  HCERTSTORE v10; // [rsp+38h] [rbp-30h]

  CertsFromThumbprints = -2147467259;
  v9 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x11000u, L"My");
  v5 = v9;
  if ( v9 )
  {
    v10 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x11000u, L"AddressBook");
    v6 = v10;
    if ( v10 )
    {
      CertsFromThumbprints = MimeOleGetCertsFromThumbprints(a1, a2, &v9, 2);
      CertCloseStore(v6, 0);
    }
    else
    {
      for ( i = 0; (unsigned int)i < *(_DWORD *)a2; i = (unsigned int)(i + 1) )
      {
        *(_QWORD *)(*((_QWORD *)a2 + 2) + 8 * i) = 0;
        *(_DWORD *)(*((_QWORD *)a2 + 1) + 4 * i) = 9;
      }
      CertsFromThumbprints = 839347;
    }
    CertCloseStore(v5, 0);
  }
  return CertsFromThumbprints;
}

```

## disassembly

```asm
0x18003b2dc  push    rbx
0x18003b2de  push    rbp
0x18003b2df  push    rsi
0x18003b2e0  push    rdi
0x18003b2e1  push    r14
0x18003b2e3  sub     rsp, 40h
0x18003b2e7  mov     rbx, rdx
0x18003b2ea  mov     [rsp+68h+var_38], 0
0x18003b2f3  xor     edx, edx; dwEncodingType
0x18003b2f5  lea     rax, aMy; "My"
0x18003b2fc  mov     r14, rcx
0x18003b2ff  mov     [rsp+68h+pvPara], rax; pvPara
0x18003b304  mov     esi, 11000h
0x18003b309  xor     r8d, r8d; hCryptProv
0x18003b30c  mov     r9d, esi; dwFlags
0x18003b30f  mov     edi, 80004005h
0x18003b314  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18003b317  call    cs:__imp_CertOpenStore
0x18003b31d  mov     [rsp+68h+var_38], rax
0x18003b322  mov     rbp, rax
0x18003b325  test    rax, rax
0x18003b328  jz      loc_18003B3B5
0x18003b32e  xor     edx, edx; dwEncodingType
0x18003b330  lea     rax, aAddressbook; "AddressBook"
0x18003b337  mov     r9d, esi; dwFlags
0x18003b33a  mov     [rsp+68h+pvPara], rax; pvPara
0x18003b33f  xor     r8d, r8d; hCryptProv
0x18003b342  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18003b345  call    cs:__imp_CertOpenStore
0x18003b34b  mov     [rsp+68h+var_30], rax
0x18003b350  mov     rsi, rax
0x18003b353  test    rax, rax
0x18003b356  jz      short loc_18003B37D
0x18003b358  mov     r9d, 2
0x18003b35e  lea     r8, [rsp+68h+var_38]
0x18003b363  mov     rdx, rbx
0x18003b366  mov     rcx, r14
0x18003b369  call    MimeOleGetCertsFromThumbprints
0x18003b36e  xor     edx, edx; dwFlags
0x18003b370  mov     rcx, rsi; hCertStore
0x18003b373  mov     edi, eax
0x18003b375  call    cs:__imp_CertCloseStore
0x18003b37b  jmp     short loc_18003B3AA
0x18003b37d  xor     r8d, r8d
0x18003b380  cmp     [rbx], r8d
0x18003b383  jbe     short loc_18003B3A5
0x18003b385  mov     rax, [rbx+10h]
0x18003b389  mov     qword ptr [rax+r8*8], 0
0x18003b391  mov     rax, [rbx+8]
0x18003b395  mov     dword ptr [rax+r8*4], 9
0x18003b39d  inc     r8d
0x18003b3a0  cmp     r8d, [rbx]
0x18003b3a3  jb      short loc_18003B385
0x18003b3a5  mov     edi, 0CCEB3h
0x18003b3aa  xor     edx, edx; dwFlags
0x18003b3ac  mov     rcx, rbp; hCertStore
0x18003b3af  call    cs:__imp_CertCloseStore
0x18003b3b5  mov     eax, edi
0x18003b3b7  add     rsp, 40h
0x18003b3bb  pop     r14
0x18003b3bd  pop     rdi
0x18003b3be  pop     rsi
0x18003b3bf  pop     rbp
0x18003b3c0  pop     rbx
0x18003b3c1  retn
```
