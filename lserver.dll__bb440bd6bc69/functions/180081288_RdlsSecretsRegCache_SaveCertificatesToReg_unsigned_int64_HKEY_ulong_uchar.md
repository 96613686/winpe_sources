# RdlsSecretsRegCache::SaveCertificatesToReg(unsigned __int64,HKEY__ *,ulong,uchar *)

- ea: `0x180081288`
- end: `0x18008135f`
- name: `?SaveCertificatesToReg@RdlsSecretsRegCache@@AEAAK_KPEAUHKEY__@@KPEAE@Z`
- size: `215`
- prototype: `unsigned int(RdlsSecretsRegCache *__hidden this, unsigned __int64, HKEY, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180080fb0`

## callees

- `0x180044f1c`
- `0x180081288`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x1800812ca`
- `CRYPT32!CertOpenStore` at `0x1800812fc`
- `CRYPT32!CertOpenStore` at `0x1800812ca`
- `CRYPT32!CertOpenStore` at `0x1800812fc`
- `CRYPT32!CertCloseStore` at `0x18008132c`
- `CRYPT32!CertCloseStore` at `0x180081340`
- `CRYPT32!CertCloseStore` at `0x18008132c`
- `CRYPT32!CertCloseStore` at `0x180081340`

## pseudocode

```c
__int64 __fastcall RdlsSecretsRegCache::SaveCertificatesToReg(
        RdlsSecretsRegCache *this,
        HCRYPTPROV_LEGACY a2,
        HKEY a3,
        int a4,
        unsigned __int8 *a5)
{
  HCERTSTORE v7; // rsi
  unsigned int v8; // ebx
  HCERTSTORE v9; // rax
  void *v10; // rdi
  _DWORD pvPara[2]; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int8 *v13; // [rsp+38h] [rbp-10h]

  pvPara[1] = 0;
  pvPara[0] = a4;
  v13 = a5;
  v7 = CertOpenStore((LPCSTR)5, 0x10001u, a2, 1u, pvPara);
  if ( v7 )
  {
    v9 = CertOpenStore((LPCSTR)4, 0x10001u, a2, 1u, a3);
    v10 = v9;
    if ( v9 )
    {
      v8 = TransferCertFromStoreToStore(v7, v9);
      CertCloseStore(v10, 1u);
    }
    else
    {
      v8 = -1073676256;
    }
    CertCloseStore(v7, 1u);
  }
  else
  {
    return (unsigned int)-1073676256;
  }
  return v8;
}

```

## disassembly

```asm
0x180081288  mov     r11, rsp
0x18008128b  mov     [r11+8], rbx
0x18008128f  mov     [r11+10h], rsi
0x180081293  push    rdi
0x180081294  sub     rsp, 40h
0x180081298  and     [rsp+48h+var_14], 0
0x18008129d  mov     rdi, r8
0x1800812a0  mov     rax, [rsp+48h+arg_20]
0x1800812a5  mov     rbx, rdx
0x1800812a8  mov     [r11-18h], r9d
0x1800812ac  mov     r8, rdx; hCryptProv
0x1800812af  mov     r9d, 1; dwFlags
0x1800812b5  mov     [r11-10h], rax
0x1800812b9  lea     rax, [r11-18h]
0x1800812bd  mov     edx, 10001h; dwEncodingType
0x1800812c2  mov     [r11-28h], rax
0x1800812c6  lea     ecx, [r9+4]; lpszStoreProvider
0x1800812ca  call    cs:__imp_CertOpenStore
0x1800812d1  nop     dword ptr [rax+rax+00h]
0x1800812d6  mov     rsi, rax
0x1800812d9  test    rax, rax
0x1800812dc  jnz     short loc_1800812E5
0x1800812de  mov     ebx, 0C0010020h
0x1800812e3  jmp     short loc_18008134C
0x1800812e5  mov     r9d, 1; dwFlags
0x1800812eb  mov     [rsp+48h+pvPara], rdi; pvPara
0x1800812f0  mov     r8, rbx; hCryptProv
0x1800812f3  mov     edx, 10001h; dwEncodingType
0x1800812f8  lea     ecx, [r9+3]; lpszStoreProvider
0x1800812fc  call    cs:__imp_CertOpenStore
0x180081303  nop     dword ptr [rax+rax+00h]
0x180081308  mov     rdi, rax
0x18008130b  test    rax, rax
0x18008130e  jnz     short loc_180081317
0x180081310  mov     ebx, 0C0010020h
0x180081315  jmp     short loc_180081338
0x180081317  mov     rdx, rdi; HCERTSTORE
0x18008131a  mov     rcx, rsi; hCertStore
0x18008131d  call    TransferCertFromStoreToStore
0x180081322  mov     ebx, eax
0x180081324  mov     edx, 1; dwFlags
0x180081329  mov     rcx, rdi; hCertStore
0x18008132c  call    cs:__imp_CertCloseStore
0x180081333  nop     dword ptr [rax+rax+00h]
0x180081338  mov     edx, 1; dwFlags
0x18008133d  mov     rcx, rsi; hCertStore
0x180081340  call    cs:__imp_CertCloseStore
0x180081347  nop     dword ptr [rax+rax+00h]
0x18008134c  mov     rsi, [rsp+48h+arg_8]
0x180081351  mov     eax, ebx
0x180081353  mov     rbx, [rsp+48h+arg_0]
0x180081358  add     rsp, 40h
0x18008135c  pop     rdi
0x18008135d  retn
```
